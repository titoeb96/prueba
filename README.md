 public List list(){
        List<Usuario> lista=new ArrayList<Usuario>();
        con.setSeleccion("select * from usuarios");
        Usuario user;
        try{
            while(con.getRs().next()){
                user=new Usuario();
                user.setUsuario_id(con.getRs().getInt("usuario_id"));
                user.setNombre(con.getRs().getString("nombre"));
                user.setApellido(con.getRs().getString("apellido"));
                lista.add(user);
            }
        }catch(Exception ex){
            System.out.println("ERROr"+ex.getMessage());
        }
        return lista;
    }
