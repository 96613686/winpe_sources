# Exception::GetHRSymbolicName(long)

- ea: `0x18003b5fc`
- end: `0x18003c65d`
- name: `?GetHRSymbolicName@Exception@@SAPEBDJ@Z`
- size: `4193`
- prototype: `const char *__fastcall(int)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18003b45c`

## callees

- `0x18003b5fc`

## string_xrefs

- `0x18003c12a`: `E_ACCESSDENIED`
- `0x18003b674`: `CO_E_INIT_CLASS_CACHE`
- `0x18003b6bc`: `CO_E_INIT_ONLY_SINGLE_THREADED`
- `0x18003bd19`: `OLE_E_NOCACHE`
- `0x18003bd59`: `OLE_E_WRONGCOMPOBJ`
- `0x18003beaf`: `DRAGDROP_E_ALREADYREGISTERED`
- `0x18003be87`: `REGDB_E_READREGDB`
- `0x18003be75`: `REGDB_E_WRITEREGDB`
- `0x18003bf46`: `CACHE_E_NOCACHE_UPDATED`
- `0x18003bfc2`: `CLIPBRD_E_CANT_OPEN`
- `0x18003c05a`: `MK_E_INVALIDEXTENSION`
- `0x18003c07a`: `MK_E_CANTOPENFILE`
- `0x18003c0b2`: `CO_E_ALREADYINITIALIZED`
- `0x18003c0ea`: `CO_E_DLLNOTFOUND`
- `0x18003c0f2`: `CO_E_ERRORINDLL`
- `0x18003c5bf`: `VIEW_S_ALREADY_FROZEN`
- `0x18003c5b7`: `CACHE_S_FORMATETC_NOTSUPPORTED`
- `0x18003c5af`: `CACHE_S_SAMECACHE`
- `0x18003c5a7`: `CACHE_S_SOMECACHES_NOTUPDATED`
- `0x18003c61d`: `MK_S_MONIKERALREADYREGISTERED`
- `0x18003c1e3`: `CO_E_CLASS_CREATE_FAILED`
- `0x18003c1cb`: `CO_E_BAD_PATH`
- `0x18003c28b`: `MEM_E_INVALID_LINK`
- `0x18003b9c7`: `TYPE_E_INVDATAREAD`
- `0x18003b9b7`: `TYPE_E_REGISTRYACCESS`
- `0x18003ba01`: `TYPE_E_DLLFUNCTIONNOTFOUND`
- `0x18003bab2`: `TYPE_E_CANTCREATETMPFILE`
- `0x18003bb16`: `TYPE_E_CANTLOADLIBRARY`
- `0x18003bae4`: `STG_E_PATHNOTFOUND`
- `0x18003bb1e`: `STG_E_TOOMANYOPENFILES`
- `0x18003bba0`: `STG_E_ACCESSDENIED`
- `0x18003bb6e`: `STG_E_DISKISWRITEPROTECTED`
- `0x18003bc0c`: `STG_E_WRITEFAULT`
- `0x18003bc04`: `STG_E_READFAULT`
- `0x18003bbec`: `STG_E_FILEALREADYEXISTS`
- `0x18003bc99`: `STG_E_OLDDLL`
- `0x18003b7dc`: `RPC_E_ATTEMPTED_MULTITHREAD`
- `0x18003b83c`: `RPC_E_WRONG_THREAD`
- `0x18003b844`: `RPC_E_THREAD_NOT_INIT`
- `0x18003c349`: `CTL_E_FILEALREADYOPEN`
- `0x18003c339`: `CTL_E_FILEALREADYEXISTS`
- `0x18003c3d5`: `CTL_E_DISKNOTREADY`
- `0x18003c3cd`: `CTL_E_PATHFILEACCESSERROR`
- `0x18003c3c5`: `CTL_E_PATHNOTFOUND`
- `0x18003c548`: `CTL_E_CANTSAVEFILETOTEMP`
- `0x18003c538`: `CTL_E_REPLACEMENTSTOOLONG`

## pseudocode

```c
const char *__fastcall Exception::GetHRSymbolicName(int a1)
{
  const char *result; // rax
  const char *v2; // rdx
  bool v3; // zf
  int v4; // ecx
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  int v18; // ecx

  if ( a1 <= -2147418113 )
  {
    if ( a1 == -2147418113 )
      return "E_UNEXPECTED";
    switch ( a1 )
    {
      case -2147467263:
        result = "E_NOTIMPL";
        break;
      case -2147467262:
        result = "E_NOINTERFACE";
        break;
      case -2147467261:
        result = "E_POINTER";
        break;
      case -2147467260:
        result = "E_ABORT";
        break;
      case -2147467259:
        result = "E_FAIL";
        break;
      case -2147467258:
        result = "CO_E_INIT_TLS";
        break;
      case -2147467257:
        result = "CO_E_INIT_SHARED_ALLOCATOR";
        break;
      case -2147467256:
        result = "CO_E_INIT_MEMORY_ALLOCATOR";
        break;
      case -2147467255:
        result = "CO_E_INIT_CLASS_CACHE";
        break;
      case -2147467254:
        result = "CO_E_INIT_RPC_CHANNEL";
        break;
      case -2147467253:
        result = "CO_E_INIT_TLS_SET_CHANNEL_CONTROL";
        break;
      case -2147467252:
        result = "CO_E_INIT_TLS_CHANNEL_CONTROL";
        break;
      case -2147467251:
        result = "CO_E_INIT_UNACCEPTED_USER_ALLOCATOR";
        break;
      case -2147467250:
        result = "CO_E_INIT_SCM_MUTEX_EXISTS";
        break;
      case -2147467249:
        result = "CO_E_INIT_SCM_FILE_MAPPING_EXISTS";
        break;
      case -2147467248:
        result = "CO_E_INIT_SCM_MAP_VIEW_OF_FILE";
        break;
      case -2147467247:
        result = "CO_E_INIT_SCM_EXEC_FAILURE";
        break;
      case -2147467246:
        result = "CO_E_INIT_ONLY_SINGLE_THREADED";
        break;
      default:
        return 0;
    }
    return result;
  }
  if ( a1 <= -2147417856 )
  {
    if ( a1 == -2147417856 )
      return "RPC_E_SYS_CALL_FAILED";
    switch ( a1 )
    {
      case -2147418111:
        result = "RPC_E_CALL_REJECTED";
        break;
      case -2147418110:
        result = "RPC_E_CALL_CANCELED";
        break;
      case -2147418109:
        result = "RPC_E_CANTPOST_INSENDCALL";
        break;
      case -2147418108:
        result = "RPC_E_CANTCALLOUT_INASYNCCALL";
        break;
      case -2147418107:
        result = "RPC_E_CANTCALLOUT_INEXTERNALCALL";
        break;
      case -2147418106:
        result = "RPC_E_CONNECTION_TERMINATED";
        break;
      case -2147418105:
        result = "RPC_E_SERVER_DIED";
        break;
      case -2147418104:
        result = "RPC_E_CLIENT_DIED";
        break;
      case -2147418103:
        result = "RPC_E_INVALID_DATAPACKET";
        break;
      case -2147418102:
        result = "RPC_E_CANTTRANSMIT_CALL";
        break;
      case -2147418101:
        result = "RPC_E_CLIENT_CANTMARSHAL_DATA";
        break;
      case -2147418100:
        result = "RPC_E_CLIENT_CANTUNMARSHAL_DATA";
        break;
      case -2147418099:
        result = "RPC_E_SERVER_CANTMARSHAL_DATA";
        break;
      case -2147418098:
        result = "RPC_E_SERVER_CANTUNMARSHAL_DATA";
        break;
      case -2147418097:
        result = "RPC_E_INVALID_DATA";
        break;
      case -2147418096:
        result = "RPC_E_INVALID_PARAMETER";
        break;
      case -2147418095:
        result = "RPC_E_CANTCALLOUT_AGAIN";
        break;
      case -2147418094:
        result = "RPC_E_SERVER_DIED_DNE";
        break;
      default:
        return 0;
    }
    return result;
  }
  if ( a1 <= -2147352577 )
  {
    if ( a1 == -2147352577 )
      return "RPC_E_UNEXPECTED";
    switch ( a1 )
    {
      case -2147417855:
        result = "RPC_E_OUT_OF_RESOURCES";
        break;
      case -2147417854:
        result = "RPC_E_ATTEMPTED_MULTITHREAD";
        break;
      case -2147417853:
        result = "RPC_E_NOT_REGISTERED";
        break;
      case -2147417852:
        result = "RPC_E_FAULT";
        break;
      case -2147417851:
        result = "RPC_E_SERVERFAULT";
        break;
      case -2147417850:
        result = "RPC_E_CHANGED_MODE";
        break;
      case -2147417849:
        result = "RPC_E_INVALIDMETHOD";
        break;
      case -2147417848:
        result = "RPC_E_DISCONNECTED";
        break;
      case -2147417847:
        result = "RPC_E_RETRY";
        break;
      case -2147417846:
        result = "RPC_E_SERVERCALL_RETRYLATER";
        break;
      case -2147417845:
        result = "RPC_E_SERVERCALL_REJECTED";
        break;
      case -2147417844:
        result = "RPC_E_INVALID_CALLDATA";
        break;
      case -2147417843:
        result = "RPC_E_CANTCALLOUT_ININPUTSYNCCALL";
        break;
      case -2147417842:
        result = "RPC_E_WRONG_THREAD";
        break;
      case -2147417841:
        result = "RPC_E_THREAD_NOT_INIT";
        break;
      default:
        return 0;
    }
    return result;
  }
  if ( a1 <= -2147319786 )
  {
    if ( a1 == -2147319786 )
      return "TYPE_E_BUFFERTOOSMALL";
    switch ( a1 )
    {
      case -2147352575:
        result = "DISP_E_UNKNOWNINTERFACE";
        break;
      case -2147352573:
        result = "DISP_E_MEMBERNOTFOUND";
        break;
      case -2147352572:
        result = "DISP_E_PARAMNOTFOUND";
        break;
      case -2147352571:
        result = "DISP_E_TYPEMISMATCH";
        break;
      case -2147352570:
        result = "DISP_E_UNKNOWNNAME";
        break;
      case -2147352569:
        result = "DISP_E_NONAMEDARGS";
        break;
      case -2147352568:
        result = "DISP_E_BADVARTYPE";
        break;
      case -2147352567:
        result = "DISP_E_EXCEPTION";
        break;
      case -2147352566:
        result = "DISP_E_OVERFLOW";
        break;
      case -2147352565:
        result = "DISP_E_BADINDEX";
        break;
      case -2147352564:
        result = "DISP_E_UNKNOWNLCID";
        break;
      case -2147352563:
        result = "DISP_E_ARRAYISLOCKED";
        break;
      case -2147352562:
        result = "DISP_E_BADPARAMCOUNT";
        break;
      case -2147352561:
        result = "DISP_E_PARAMNOTOPTIONAL";
        break;
      case -2147352560:
        result = "DISP_E_BADCALLEE";
        break;
      case -2147352559:
        result = "DISP_E_NOTACOLLECTION";
        break;
      default:
        return 0;
    }
    return result;
  }
  if ( a1 > -2147221036 )
  {
    if ( a1 > -2147024891 )
    {
      if ( a1 > -2146827908 )
      {
        if ( a1 <= 262146 )
        {
          if ( a1 == 262146 )
            return "OLE_S_MAC_CLIPFORMAT";
          if ( a1 > -2146827807 )
          {
            switch ( a1 )
            {
              case -2146827806:
                return "CTL_E_PRINTERERROR";
              case -2146827553:
                return "CTL_E_CANTSAVEFILETOTEMP";
              case -2146827544:
                return "CTL_E_SEARCHTEXTNOTFOUND";
              case -2146827542:
                return "CTL_E_REPLACEMENTSTOOLONG";
            }
            result = 0;
            switch ( a1 )
            {
              case 0:
                return "S_OK";
              case 1:
                return "S_FALSE";
              case 0x30200:
                return "STG_S_CONVERTED";
              case 0x40000:
                return "OLE_S_USEREG";
            }
            v2 = "OLE_S_STATIC";
            v3 = a1 == 262145;
          }
          else
          {
            switch ( a1 )
            {
              case -2146827807:
                return "CTL_E_INVALIDPICTURE";
              case -2146827907:
                return "CTL_E_INVALIDPROPERTYARRAYINDEX";
              case -2146827906:
                return "CTL_E_SETNOTSUPPORTEDATRUNTIME";
              case -2146827905:
                return "CTL_E_SETNOTSUPPORTED";
              case -2146827903:
                return "CTL_E_NEEDPROPERTYARRAYINDEX";
              case -2146827901:
                return "CTL_E_SETNOTPERMITTED";
              case -2146827895:
                return "CTL_E_GETNOTSUPPORTEDATRUNTIME";
              case -2146827894:
                return "CTL_E_GETNOTSUPPORTED";
              case -2146827866:
                return "CTL_E_PROPERTYNOTFOUND";
            }
            result = 0;
            v2 = "CTL_E_INVALIDCLIPBOARDFORMAT";
            v3 = a1 == -2146827828;
          }
          goto LABEL_428;
        }
        if ( a1 > 262529 )
        {
          v12 = a1 - 262530;
          if ( !v12 )
            return "OLEOBJ_S_INVALIDHWND";
          v13 = v12 - 30;
          if ( !v13 )
            return "INPLACE_S_TRUNCATED";
          v14 = v13 - 32;
          if ( !v14 )
            return "CONVERT10_S_NO_PRESENTATION";
          v15 = v14 - 34;
          if ( !v15 )
            return "MK_S_REDUCED_TO_SELF";
          v16 = v15 - 2;
          if ( !v16 )
            return "MK_S_ME";
          v17 = v16 - 1;
          if ( !v17 )
            return "MK_S_HIM";
          v18 = v17 - 1;
          if ( !v18 )
            return "MK_S_US";
          if ( v18 == 1 )
            return "MK_S_MONIKERALREADYREGISTERED";
        }
        else
        {
          if ( a1 == 262529 )
            return "OLEOBJ_S_CANNOT_DOVERB_NOW";
          v4 = a1 - 262400;
          if ( !v4 )
            return "DRAGDROP_S_DROP";
          v5 = v4 - 1;
          if ( !v5 )
            return "DRAGDROP_S_CANCEL";
          v6 = v5 - 1;
          if ( !v6 )
            return "DRAGDROP_S_USEDEFAULTCURSORS";
          v7 = v6 - 46;
          if ( !v7 )
            return "DATA_S_SAMEFORMATETC";
          v8 = v7 - 16;
          if ( !v8 )
            return "VIEW_S_ALREADY_FROZEN";
          v9 = v8 - 48;
          if ( !v9 )
            return "CACHE_S_FORMATETC_NOTSUPPORTED";
          v10 = v9 - 1;
          if ( !v10 )
            return "CACHE_S_SAMECACHE";
          v11 = v10 - 1;
          if ( !v11 )
            return "CACHE_S_SOMECACHES_NOTUPDATED";
          if ( v11 == 14 )
            return "OLEOBJ_S_INVALIDVERB";
        }
      }
      else
      {
        if ( a1 == -2146827908 )
          return "CTL_E_INVALIDPROPERTYVALUE";
        if ( a1 <= -2146828260 )
        {
          if ( a1 == -2146828260 )
            return "CTL_E_OUTOFSTACKSPACE";
          if ( a1 > -2146959353 )
          {
            switch ( a1 )
            {
              case -2146959352:
                return "CO_E_SERVER_STOPPING";
              case -2146959351:
                return "MEM_E_INVALID_ROOT";
              case -2146959344:
                return "MEM_E_INVALID_LINK";
              case -2146959343:
                return "MEM_E_INVALID_SIZE";
              case -2146828283:
                return "CTL_E_ILLEGALFUNCTIONCALL";
              case -2146828282:
                return "CTL_E_OVERFLOW";
              case -2146828281:
                return "CTL_E_OUTOFMEMORY";
              case -2146828277:
                return "CTL_E_DIVISIONBYZERO";
            }
            result = 0;
            v2 = "CTL_E_OUTOFSTRINGSPACE";
            v3 = a1 == -2146828274;
          }
          else
          {
            switch ( a1 )
            {
              case -2146959353:
                return "MK_E_NO_NORMALIZED";
              case -2147024890:
                return "E_HANDLE";
              case -2147024882:
                return "E_OUTOFMEMORY";
              case -2147024809:
                return "E_INVALIDARG";
              case -2146959359:
                return "CO_E_CLASS_CREATE_FAILED";
              case -2146959358:
                return "CO_E_SCM_ERROR";
              case -2146959357:
                return "CO_E_SCM_RPC_FAILURE";
              case -2146959356:
                return "CO_E_BAD_PATH";
              case -2146959355:
                return "CO_E_SERVER_EXEC_FAILURE";
            }
            result = 0;
            v2 = "CO_E_OBJSRV_RPC_FAILURE";
            v3 = a1 == -2146959354;
          }
          goto LABEL_428;
        }
        if ( a1 <= -2146827967 )
        {
          if ( a1 == -2146827967 )
            return "CTL_E_INVALIDFILEFORMAT";
          if ( a1 > -2146828224 )
          {
            switch ( a1 )
            {
              case -2146828221:
                return "CTL_E_TOOMANYFILES";
              case -2146828220:
                return "CTL_E_DEVICEUNAVAILABLE";
              case -2146828218:
                return "CTL_E_PERMISSIONDENIED";
              case -2146828217:
                return "CTL_E_DISKNOTREADY";
              case -2146828213:
                return "CTL_E_PATHFILEACCESSERROR";
              case -2146828212:
                return "CTL_E_PATHNOTFOUND";
              case -2146828195:
                return "CTL_E_INVALIDPATTERNSTRING";
            }
            result = 0;
            v2 = "CTL_E_INVALIDUSEOFNULL";
            v3 = a1 == -2146828194;
          }
          else
          {
            switch ( a1 )
            {
              case -2146828224:
                return "CTL_E_BADFILENAME";
              case -2146828236:
                return "CTL_E_BADFILENAMEORNUMBER";
              case -2146828235:
                return "CTL_E_FILENOTFOUND";
              case -2146828234:
                return "CTL_E_BADFILEMODE";
              case -2146828233:
                return "CTL_E_FILEALREADYOPEN";
              case -2146828231:
                return "CTL_E_DEVICEIOERROR";
              case -2146828230:
                return "CTL_E_FILEALREADYEXISTS";
              case -2146828229:
                return "CTL_E_BADRECORDLENGTH";
              case -2146828227:
                return "CTL_E_DISKFULL";
            }
            result = 0;
            v2 = "CTL_E_BADRECORDNUMBER";
            v3 = a1 == -2146828225;
          }
          goto LABEL_428;
        }
      }
      return 0;
    }
    if ( a1 == -2147024891 )
    {
      return "E_ACCESSDENIED";
    }
    else
    {
      switch ( a1 )
      {
        case -2147221024:
          result = "MK_E_CONNECTMANUALLY";
          break;
        case -2147221023:
          result = "MK_E_EXCEEDEDDEADLINE";
          break;
        case -2147221022:
          result = "MK_E_NEEDGENERIC";
          break;
        case -2147221021:
          result = "MK_E_UNAVAILABLE";
          break;
        case -2147221020:
          result = "MK_E_SYNTAX";
          break;
        case -2147221019:
          result = "MK_E_NOOBJECT";
          break;
        case -2147221018:
          result = "MK_E_INVALIDEXTENSION";
          break;
        case -2147221017:
          result = "MK_E_INTERMEDIATEINTERFACENOTSUPPORTED";
          break;
        case -2147221016:
          result = "MK_E_NOTBINDABLE";
          break;
        case -2147221015:
          result = "MK_E_NOTBOUND";
          break;
        case -2147221014:
          result = "MK_E_CANTOPENFILE";
          break;
        case -2147221013:
          result = "MK_E_MUSTBOTHERUSER";
          break;
        case -2147221012:
          result = "MK_E_NOINVERSE";
          break;
        case -2147221011:
          result = "MK_E_NOSTORAGE";
          break;
        case -2147221010:
          result = "MK_E_NOPREFIX";
          break;
        case -2147221009:
          result = "MK_E_ENUMERATION_FAILED";
          break;
        case -2147221008:
          result = "CO_E_NOTINITIALIZED";
          break;
        case -2147221007:
          result = "CO_E_ALREADYINITIALIZED";
          break;
        case -2147221006:
          result = "CO_E_CANTDETERMINECLASS";
          break;
        case -2147221005:
          result = "CO_E_CLASSSTRING";
          break;
        case -2147221004:
          result = "CO_E_IIDSTRING";
          break;
        case -2147221003:
          result = "CO_E_APPNOTFOUND";
          break;
        case -2147221002:
          result = "CO_E_APPSINGLEUSE";
          break;
        case -2147221001:
          result = "CO_E_ERRORINAPP";
          break;
        case -2147221000:
          result = "CO_E_DLLNOTFOUND";
          break;
        case -2147220999:
          result = "CO_E_ERRORINDLL";
          break;
        case -2147220998:
          result = "CO_E_WRONGOSFORAPP";
          break;
        case -2147220997:
          result = "CO_E_OBJNOTREG";
          break;
        case -2147220996:
          result = "CO_E_OBJISREG";
          break;
        case -2147220995:
          result = "CO_E_OBJNOTCONNECTED";
          break;
        case -2147220994:
          result = "CO_E_APPDIDNTREG";
          break;
        case -2147220993:
          result = "CO_E_RELEASED";
          break;
        default:
          return 0;
      }
    }
  }
  else
  {
    if ( a1 == -2147221036 )
      return "CLIPBRD_E_CANT_CLOSE";
    if ( a1 > -2147286777 )
    {
      if ( a1 > -2147221404 )
      {
        if ( a1 > -2147221166 )
        {
          if ( a1 > -2147221054 )
          {
            switch ( a1 )
            {
              case -2147221053:
                return "CONVERT10_E_OLESTREAM_BITMAP_TO_DIB";
              case -2147221052:
                return "CONVERT10_E_STG_FMT";
              case -2147221051:
                return "CONVERT10_E_STG_NO_STD_STREAM";
              case -2147221050:
                return "CONVERT10_E_STG_DIB_TO_BITMAP";
              case -2147221040:
                return "CLIPBRD_E_CANT_OPEN";
              case -2147221039:
                return "CLIPBRD_E_CANT_EMPTY";
              case -2147221038:
                return "CLIPBRD_E_CANT_SET";
            }
            result = 0;
            v2 = "CLIPBRD_E_BAD_DATA";
            v3 = a1 == -2147221037;
          }
          else
          {
            switch ( a1 )
            {
              case -2147221054:
                return "CONVERT10_E_OLESTREAM_FMT";
              case -2147221165:
                return "REGDB_E_INVALIDVALUE";
              case -2147221164:
                return "REGDB_E_CLASSNOTREG";
              case -2147221136:
                return "CACHE_E_NOCACHE_UPDATED";
              case -2147221120:
                return "OLEOBJ_E_NOVERBS";
              case -2147221088:
                return "INPLACE_E_NOTUNDOABLE";
              case -2147221087:
                return "INPLACE_E_NOTOOLSPACE";
              case -2147221056:
                return "CONVERT10_E_OLESTREAM_GET";
            }
            result = 0;
            v2 = "CONVERT10_E_OLESTREAM_PUT";
            v3 = a1 == -2147221055;
          }
        }
        else
        {
          if ( a1 == -2147221166 )
            return "REGDB_E_KEYMISSING";
          if ( a1 > -2147221395 )
          {
            switch ( a1 )
            {
              case -2147221248:
                return "DRAGDROP_E_NOTREGISTERED";
              case -2147221247:
                return "DRAGDROP_E_ALREADYREGISTERED";
              case -2147221246:
                return "DRAGDROP_E_INVALIDHWND";
              case -2147221232:
                return "CLASS_E_NOAGGREGATION";
              case -2147221231:
                return "CLASS_E_CLASSNOTAVAILABLE";
              case -2147221184:
                return "VIEW_E_DRAW";
              case -2147221168:
                return "REGDB_E_READREGDB";
            }
            result = 0;
            v2 = "REGDB_E_WRITEREGDB";
            v3 = a1 == -2147221167;
          }
          else
          {
            switch ( a1 )
            {
              case -2147221395:
                return "DV_E_NOIVIEWOBJECT";
              case -2147221403:
                return "DV_E_DVTARGETDEVICE";
              case -2147221402:
                return "DV_E_STGMEDIUM";
              case -2147221401:
                return "DV_E_STATDATA";
              case -2147221400:
                return "DV_E_LINDEX";
              case -2147221399:
                return "DV_E_TYMED";
              case -2147221398:
                return "DV_E_CLIPFORMAT";
              case -2147221397:
                return "DV_E_DVASPECT";
            }
            result = 0;
            v2 = "DV_E_DVTARGETDEVICE_SIZE";
            v3 = a1 == -2147221396;
          }
        }
        goto LABEL_428;
      }
      if ( a1 == -2147221404 )
      {
        return "DV_E_FORMATETC";
      }
      else
      {
        switch ( a1 )
        {
          case -2147221504:
            result = "OLE_E_OLEVERB";
            break;
          case -2147221503:
            result = "OLE_E_ADVF";
            break;
          case -2147221502:
            result = "OLE_E_ENUM_NOMORE";
            break;
          case -2147221501:
            result = "OLE_E_ADVISENOTSUPPORTED";
            break;
          case -2147221500:
            result = "OLE_E_NOCONNECTION";
            break;
          case -2147221499:
            result = "OLE_E_NOTRUNNING";
            break;
          case -2147221498:
            result = "OLE_E_NOCACHE";
            break;
          case -2147221497:
            result = "OLE_E_BLANK";
            break;
          case -2147221496:
            result = "OLE_E_CLASSDIFF";
            break;
          case -2147221495:
            result = "OLE_E_CANT_GETMONIKER";
            break;
          case -2147221494:
            result = "OLE_E_CANT_BINDTOSOURCE";
            break;
          case -2147221493:
            result = "OLE_E_STATIC";
            break;
          case -2147221492:
            result = "OLE_E_PROMPTSAVECANCELLED";
            break;
          case -2147221491:
            result = "OLE_E_INVALIDRECT";
            break;
          case -2147221490:
            result = "OLE_E_WRONGCOMPOBJ";
            break;
          case -2147221489:
            result = "OLE_E_INVALIDHWND";
            break;
          case -2147221488:
            result = "OLE_E_NOT_INPLACEACTIVE";
            break;
          case -2147221487:
            result = "OLE_E_CANTCONVERT";
            break;
          case -2147221486:
            result = "OLE_E_NOSTORAGE";
            break;
          default:
            return 0;
        }
      }
    }
    else
    {
      if ( a1 == -2147286777 )
        return "STG_E_NOTFILEBASEDSTORAGE";
      if ( a1 <= -2147287036 )
      {
        if ( a1 == -2147287036 )
          return "STG_E_TOOMANYOPENFILES";
        if ( a1 > -2147317571 )
        {
          if ( a1 > -2147316573 )
          {
            switch ( a1 )
            {
              case -2147312566:
                return "TYPE_E_CANTLOADLIBRARY";
              case -2147312509:
                return "TYPE_E_INCONSISTENTPROPFUNCS";
              case -2147312508:
                return "TYPE_E_CIRCULARTYPE";
              case -2147287039:
                return "STG_E_INVALIDFUNCTION";
              case -2147287038:
                return "STG_E_FILENOTFOUND";
            }
            result = 0;
            v2 = "STG_E_PATHNOTFOUND";
            v3 = a1 == -2147287037;
          }
          else
          {
            switch ( a1 )
            {
              case -2147316573:
                return "TYPE_E_CANTCREATETMPFILE";
              case -2147317563:
                return "TYPE_E_SIZETOOBIG";
              case -2147317562:
                return "TYPE_E_DUPLICATEID";
              case -2147317553:
                return "TYPE_E_INVALIDID";
              case -2147316576:
                return "TYPE_E_TYPEMISMATCH";
              case -2147316575:
                return "TYPE_E_OUTOFBOUNDS";
            }
            result = 0;
            v2 = "TYPE_E_IOERROR";
            v3 = a1 == -2147316574;
          }
        }
        else
        {
          if ( a1 == -2147317571 )
            return "TYPE_E_BADMODULEKIND";
          if ( a1 > -2147319767 )
          {
            switch ( a1 )
            {
              case -2147319766:
                return "TYPE_E_WRONGTYPEKIND";
              case -2147319765:
                return "TYPE_E_ELEMENTNOTFOUND";
              case -2147319764:
                return "TYPE_E_AMBIGUOUSNAME";
              case -2147319763:
                return "TYPE_E_NAMECONFLICT";
              case -2147319762:
                return "TYPE_E_UNKNOWNLCID";
            }
            result = 0;
            v2 = "TYPE_E_DLLFUNCTIONNOTFOUND";
            v3 = a1 == -2147319761;
          }
          else
          {
            switch ( a1 )
            {
              case -2147319767:
                return "TYPE_E_INVALIDSTATE";
              case -2147319784:
                return "TYPE_E_INVDATAREAD";
              case -2147319783:
                return "TYPE_E_UNSUPFORMAT";
              case -2147319780:
                return "TYPE_E_REGISTRYACCESS";
              case -2147319779:
                return "TYPE_E_LIBNOTREGISTERED";
              case -2147319769:
                return "TYPE_E_UNDEFINEDTYPE";
            }
            result = 0;
            v2 = "TYPE_E_QUALIFIEDNAMEDISALLOWED";
            v3 = a1 == -2147319768;
          }
        }
LABEL_428:
        if ( v3 )
          return v2;
        return result;
      }
      if ( a1 <= -2147286928 )
      {
        if ( a1 == -2147286928 )
          return "STG_E_MEDIUMFULL";
        if ( a1 > -2147287015 )
        {
          switch ( a1 )
          {
            case -2147287011:
              return "STG_E_WRITEFAULT";
            case -2147287010:
              return "STG_E_READFAULT";
            case -2147287008:
              return "STG_E_SHAREVIOLATION";
            case -2147287007:
              return "STG_E_LOCKVIOLATION";
            case -2147286960:
              return "STG_E_FILEALREADYEXISTS";
          }
          result = 0;
          v2 = "STG_E_INVALIDPARAMETER";
          v3 = a1 == -2147286953;
        }
        else
        {
          switch ( a1 )
          {
            case -2147287015:
              return "STG_E_SEEKERROR";
            case -2147287035:
              return "STG_E_ACCESSDENIED";
            case -2147287034:
              return "STG_E_INVALIDHANDLE";
            case -2147287032:
              return "STG_E_INSUFFICIENTMEMORY";
            case -2147287031:
              return "STG_E_INVALIDPOINTER";
            case -2147287022:
              return "STG_E_NOMOREFILES";
          }
          result = 0;
          v2 = "STG_E_DISKISWRITEPROTECTED";
          v3 = a1 == -2147287021;
        }
        goto LABEL_428;
      }
      switch ( a1 )
      {
        case -2147286790:
          result = "STG_E_ABNORMALAPIEXIT";
          break;
        case -2147286789:
          result = "STG_E_INVALIDHEADER";
          break;
        case -2147286788:
          result = "STG_E_INVALIDNAME";
          break;
        case -2147286787:
          result = "STG_E_UNKNOWN";
          break;
        case -2147286786:
          result = "STG_E_UNIMPLEMENTEDFUNCTION";
          break;
        case -2147286785:
          result = "STG_E_INVALIDFLAG";
          break;
        case -2147286784:
          result = "STG_E_INUSE";
          break;
        case -2147286783:
          result = "STG_E_NOTCURRENT";
          break;
        case -2147286782:
          result = "STG_E_REVERTED";
          break;
        case -2147286781:
          result = "STG_E_CANTSAVE";
          break;
        case -2147286780:
          result = "STG_E_OLDFORMAT";
          break;
        case -2147286779:
          result = "STG_E_OLDDLL";
          break;
        case -2147286778:
          result = "STG_E_SHAREREQUIRED";
          break;
        default:
          return 0;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18003b5fc  mov     eax, 8000FFFFh
0x18003b601  cmp     ecx, eax
0x18003b603  jg      loc_18003B6CC
0x18003b609  jz      loc_18003B6C4
0x18003b60f  add     ecx, 7FFFBFFFh; switch 18 cases
0x18003b615  cmp     ecx, 11h
0x18003b618  ja      def_18003B632; jumptable 000000018003B632 default case
0x18003b61e  movsxd  rax, ecx
0x18003b621  lea     rcx, __ImageBase
0x18003b628  mov     eax, ds:(jpt_18003B632 - 180000000h)[rcx+rax*4]
0x18003b62f  add     rax, rcx
0x18003b632  jmp     rax; switch jump
0x18003b634  lea     rax, aENotimpl; jumptable 000000018003B632 case -2147467263
0x18003b63b  retn
0x18003b63c  lea     rax, aENointerface; jumptable 000000018003B632 case -2147467262
0x18003b643  retn
0x18003b644  lea     rax, aEPointer; jumptable 000000018003B632 case -2147467261
0x18003b64b  retn
0x18003b64c  lea     rax, aEAbort; jumptable 000000018003B632 case -2147467260
0x18003b653  retn
0x18003b654  lea     rax, aEFail; jumptable 000000018003B632 case -2147467259
0x18003b65b  retn
0x18003b65c  lea     rax, aCoEInitTls; jumptable 000000018003B632 case -2147467258
0x18003b663  retn
0x18003b664  lea     rax, aCoEInitSharedA; jumptable 000000018003B632 case -2147467257
0x18003b66b  retn
0x18003b66c  lea     rax, aCoEInitMemoryA; jumptable 000000018003B632 case -2147467256
0x18003b673  retn
0x18003b674  lea     rax, aCoEInitClassCa; jumptable 000000018003B632 case -2147467255
0x18003b67b  retn
0x18003b67c  lea     rax, aCoEInitRpcChan; jumptable 000000018003B632 case -2147467254
0x18003b683  retn
0x18003b684  lea     rax, aCoEInitTlsSetC; jumptable 000000018003B632 case -2147467253
0x18003b68b  retn
0x18003b68c  lea     rax, aCoEInitTlsChan; jumptable 000000018003B632 case -2147467252
0x18003b693  retn
0x18003b694  lea     rax, aCoEInitUnaccep; jumptable 000000018003B632 case -2147467251
0x18003b69b  retn
0x18003b69c  lea     rax, aCoEInitScmMute; jumptable 000000018003B632 case -2147467250
0x18003b6a3  retn
0x18003b6a4  lea     rax, aCoEInitScmFile; jumptable 000000018003B632 case -2147467249
0x18003b6ab  retn
0x18003b6ac  lea     rax, aCoEInitScmMapV; jumptable 000000018003B632 case -2147467248
0x18003b6b3  retn
0x18003b6b4  lea     rax, aCoEInitScmExec; jumptable 000000018003B632 case -2147467247
0x18003b6bb  retn
0x18003b6bc  lea     rax, aCoEInitOnlySin; jumptable 000000018003B632 case -2147467246
0x18003b6c3  retn
0x18003b6c4  lea     rax, aEUnexpected; "E_UNEXPECTED"
0x18003b6cb  retn
0x18003b6cc  mov     eax, 80010100h
0x18003b6d1  cmp     ecx, eax
0x18003b6d3  jg      loc_18003B79C
0x18003b6d9  jz      loc_18003B794
0x18003b6df  add     ecx, 7FFEFFFFh; switch 18 cases
0x18003b6e5  cmp     ecx, 11h
0x18003b6e8  ja      def_18003B632; jumptable 000000018003B632 default case
0x18003b6ee  movsxd  rax, ecx
0x18003b6f1  lea     rcx, __ImageBase
0x18003b6f8  mov     eax, ds:(jpt_18003B702 - 180000000h)[rcx+rax*4]
0x18003b6ff  add     rax, rcx
0x18003b702  jmp     rax; switch jump
0x18003b704  lea     rax, aRpcECallReject; jumptable 000000018003B702 case -2147418111
0x18003b70b  retn
0x18003b70c  lea     rax, aRpcECallCancel; jumptable 000000018003B702 case -2147418110
0x18003b713  retn
0x18003b714  lea     rax, aRpcECantpostIn; jumptable 000000018003B702 case -2147418109
0x18003b71b  retn
0x18003b71c  lea     rax, aRpcECantcallou_0; jumptable 000000018003B702 case -2147418108
0x18003b723  retn
0x18003b724  lea     rax, aRpcECantcallou_1; jumptable 000000018003B702 case -2147418107
0x18003b72b  retn
0x18003b72c  lea     rax, aRpcEConnection; jumptable 000000018003B702 case -2147418106
0x18003b733  retn
0x18003b734  lea     rax, aRpcEServerDied_0; jumptable 000000018003B702 case -2147418105
0x18003b73b  retn
0x18003b73c  lea     rax, aRpcEClientDied; jumptable 000000018003B702 case -2147418104
0x18003b743  retn
0x18003b744  lea     rax, aRpcEInvalidDat; jumptable 000000018003B702 case -2147418103
0x18003b74b  retn
0x18003b74c  lea     rax, aRpcECanttransm; jumptable 000000018003B702 case -2147418102
0x18003b753  retn
0x18003b754  lea     rax, aRpcEClientCant_0; jumptable 000000018003B702 case -2147418101
0x18003b75b  retn
0x18003b75c  lea     rax, aRpcEClientCant; jumptable 000000018003B702 case -2147418100
0x18003b763  retn
0x18003b764  lea     rax, aRpcEServerCant; jumptable 000000018003B702 case -2147418099
0x18003b76b  retn
0x18003b76c  lea     rax, aRpcEServerCant_0; jumptable 000000018003B702 case -2147418098
0x18003b773  retn
0x18003b774  lea     rax, aRpcEInvalidDat_0; jumptable 000000018003B702 case -2147418097
0x18003b77b  retn
0x18003b77c  lea     rax, aRpcEInvalidPar; jumptable 000000018003B702 case -2147418096
0x18003b783  retn
0x18003b784  lea     rax, aRpcECantcallou_2; jumptable 000000018003B702 case -2147418095
0x18003b78b  retn
0x18003b78c  lea     rax, aRpcEServerDied; jumptable 000000018003B702 case -2147418094
0x18003b793  retn
0x18003b794  lea     rax, aRpcESysCallFai; "RPC_E_SYS_CALL_FAILED"
0x18003b79b  retn
0x18003b79c  mov     eax, 8001FFFFh
0x18003b7a1  cmp     ecx, eax
0x18003b7a3  jg      loc_18003B854
0x18003b7a9  jz      loc_18003B84C
0x18003b7af  add     ecx, 7FFEFEFFh; switch 15 cases
0x18003b7b5  cmp     ecx, 0Eh
0x18003b7b8  ja      def_18003B632; jumptable 000000018003B632 default case
0x18003b7be  movsxd  rax, ecx
0x18003b7c1  lea     rcx, __ImageBase
0x18003b7c8  mov     eax, ds:(jpt_18003B7D2 - 180000000h)[rcx+rax*4]
0x18003b7cf  add     rax, rcx
0x18003b7d2  jmp     rax; switch jump
0x18003b7d4  lea     rax, aRpcEOutOfResou; jumptable 000000018003B7D2 case -2147417855
0x18003b7db  retn
0x18003b7dc  lea     rax, aRpcEAttemptedM; jumptable 000000018003B7D2 case -2147417854
0x18003b7e3  retn
0x18003b7e4  lea     rax, aRpcENotRegiste; jumptable 000000018003B7D2 case -2147417853
0x18003b7eb  retn
0x18003b7ec  lea     rax, aRpcEFault; jumptable 000000018003B7D2 case -2147417852
0x18003b7f3  retn
0x18003b7f4  lea     rax, aRpcEServerfaul; jumptable 000000018003B7D2 case -2147417851
0x18003b7fb  retn
0x18003b7fc  lea     rax, aRpcEChangedMod; jumptable 000000018003B7D2 case -2147417850
0x18003b803  retn
0x18003b804  lea     rax, aRpcEInvalidmet; jumptable 000000018003B7D2 case -2147417849
0x18003b80b  retn
0x18003b80c  lea     rax, aRpcEDisconnect; jumptable 000000018003B7D2 case -2147417848
0x18003b813  retn
0x18003b814  lea     rax, aRpcERetry; jumptable 000000018003B7D2 case -2147417847
0x18003b81b  retn
0x18003b81c  lea     rax, aRpcEServercall_0; jumptable 000000018003B7D2 case -2147417846
0x18003b823  retn
0x18003b824  lea     rax, aRpcEServercall; jumptable 000000018003B7D2 case -2147417845
0x18003b82b  retn
0x18003b82c  lea     rax, aRpcEInvalidCal; jumptable 000000018003B7D2 case -2147417844
0x18003b833  retn
0x18003b834  lea     rax, aRpcECantcallou; jumptable 000000018003B7D2 case -2147417843
0x18003b83b  retn
0x18003b83c  lea     rax, aRpcEWrongThrea; jumptable 000000018003B7D2 case -2147417842
0x18003b843  retn
0x18003b844  lea     rax, aRpcEThreadNotI; jumptable 000000018003B7D2 case -2147417841
0x18003b84b  retn
0x18003b84c  lea     rax, aRpcEUnexpected; "RPC_E_UNEXPECTED"
0x18003b853  retn
0x18003b854  mov     eax, 80028016h
0x18003b859  cmp     ecx, eax
0x18003b85b  jg      loc_18003B914
0x18003b861  jz      loc_18003B90C
0x18003b867  add     ecx, 7FFDFFFFh; switch 17 cases
0x18003b86d  cmp     ecx, 10h
0x18003b870  ja      def_18003B632; jumptable 000000018003B632 default case
0x18003b876  movsxd  rax, ecx
0x18003b879  lea     rcx, __ImageBase
0x18003b880  mov     eax, ds:(jpt_18003B88A - 180000000h)[rcx+rax*4]
0x18003b887  add     rax, rcx
0x18003b88a  jmp     rax; switch jump
0x18003b88c  lea     rax, aDispEUnknownin; jumptable 000000018003B88A case -2147352575
0x18003b893  retn
0x18003b894  lea     rax, aDispEMembernot; jumptable 000000018003B88A case -2147352573
0x18003b89b  retn
0x18003b89c  lea     rax, aDispEParamnotf; jumptable 000000018003B88A case -2147352572
0x18003b8a3  retn
0x18003b8a4  lea     rax, aDispETypemisma; jumptable 000000018003B88A case -2147352571
0x18003b8ab  retn
0x18003b8ac  lea     rax, aDispEUnknownna; jumptable 000000018003B88A case -2147352570
0x18003b8b3  retn
0x18003b8b4  lea     rax, aDispENonamedar; jumptable 000000018003B88A case -2147352569
0x18003b8bb  retn
0x18003b8bc  lea     rax, aDispEBadvartyp; jumptable 000000018003B88A case -2147352568
0x18003b8c3  retn
0x18003b8c4  lea     rax, aDispEException; jumptable 000000018003B88A case -2147352567
0x18003b8cb  retn
0x18003b8cc  lea     rax, aDispEOverflow; jumptable 000000018003B88A case -2147352566
0x18003b8d3  retn
0x18003b8d4  lea     rax, aDispEBadindex; jumptable 000000018003B88A case -2147352565
0x18003b8db  retn
0x18003b8dc  lea     rax, aDispEUnknownlc; jumptable 000000018003B88A case -2147352564
0x18003b8e3  retn
0x18003b8e4  lea     rax, aDispEArrayislo; jumptable 000000018003B88A case -2147352563
0x18003b8eb  retn
0x18003b8ec  lea     rax, aDispEBadparamc; jumptable 000000018003B88A case -2147352562
0x18003b8f3  retn
0x18003b8f4  lea     rax, aDispEParamnoto; jumptable 000000018003B88A case -2147352561
0x18003b8fb  retn
0x18003b8fc  lea     rax, aDispEBadcallee; jumptable 000000018003B88A case -2147352560
0x18003b903  retn
0x18003b904  lea     rax, aDispENotacolle; jumptable 000000018003B88A case -2147352559
0x18003b90b  retn
0x18003b90c  lea     rax, aTypeEBuffertoo; "TYPE_E_BUFFERTOOSMALL"
0x18003b913  retn
0x18003b914  mov     eax, 800401D4h
0x18003b919  cmp     ecx, eax
0x18003b91b  jg      loc_18003BFF2
0x18003b921  jz      loc_18003BFEA
0x18003b927  mov     eax, 80030107h
0x18003b92c  cmp     ecx, eax
0x18003b92e  jg      loc_18003BCB1
0x18003b934  jz      loc_18003BCA9
0x18003b93a  mov     eax, 80030004h
0x18003b93f  cmp     ecx, eax
0x18003b941  jg      loc_18003BB26
0x18003b947  jz      loc_18003BB1E
0x18003b94d  mov     eax, 800288BDh
0x18003b952  cmp     ecx, eax
0x18003b954  jg      loc_18003BA43
0x18003b95a  jz      loc_18003BA3B
0x18003b960  mov     eax, 80028029h
0x18003b965  cmp     ecx, eax
0x18003b967  jg      short loc_18003B9D7
0x18003b969  jz      short loc_18003B9CF
0x18003b96b  cmp     ecx, 80028018h
0x18003b971  jz      short loc_18003B9C7
0x18003b973  cmp     ecx, 80028019h
0x18003b979  jz      short loc_18003B9BF
0x18003b97b  cmp     ecx, 8002801Ch
0x18003b981  jz      short loc_18003B9B7
0x18003b983  cmp     ecx, 8002801Dh
0x18003b989  jz      short loc_18003B9AF
0x18003b98b  cmp     ecx, 80028027h
0x18003b991  jz      short loc_18003B9A7
0x18003b993  xor     eax, eax
0x18003b995  lea     rdx, aTypeEQualified; "TYPE_E_QUALIFIEDNAMEDISALLOWED"
0x18003b99c  cmp     ecx, 80028028h
0x18003b9a2  jmp     loc_18003C513
0x18003b9a7  lea     rax, aTypeEUndefined; "TYPE_E_UNDEFINEDTYPE"
0x18003b9ae  retn
0x18003b9af  lea     rax, aTypeELibnotreg; "TYPE_E_LIBNOTREGISTERED"
0x18003b9b6  retn
0x18003b9b7  lea     rax, aTypeERegistrya; "TYPE_E_REGISTRYACCESS"
0x18003b9be  retn
0x18003b9bf  lea     rax, aTypeEUnsupform; "TYPE_E_UNSUPFORMAT"
0x18003b9c6  retn
0x18003b9c7  lea     rax, aTypeEInvdatare; "TYPE_E_INVDATAREAD"
0x18003b9ce  retn
0x18003b9cf  lea     rax, aTypeEInvalidst; "TYPE_E_INVALIDSTATE"
0x18003b9d6  retn
0x18003b9d7  cmp     ecx, 8002802Ah
0x18003b9dd  jz      short loc_18003BA33
0x18003b9df  cmp     ecx, 8002802Bh
0x18003b9e5  jz      short loc_18003BA2B
0x18003b9e7  cmp     ecx, 8002802Ch
0x18003b9ed  jz      short loc_18003BA23
0x18003b9ef  cmp     ecx, 8002802Dh
0x18003b9f5  jz      short loc_18003BA1B
0x18003b9f7  cmp     ecx, 8002802Eh
0x18003b9fd  jz      short loc_18003BA13
0x18003b9ff  xor     eax, eax
0x18003ba01  lea     rdx, aTypeEDllfuncti; "TYPE_E_DLLFUNCTIONNOTFOUND"
0x18003ba08  cmp     ecx, 8002802Fh
0x18003ba0e  jmp     loc_18003C513
0x18003ba13  lea     rax, aTypeEUnknownlc; "TYPE_E_UNKNOWNLCID"
0x18003ba1a  retn
0x18003ba1b  lea     rax, aTypeENameconfl; "TYPE_E_NAMECONFLICT"
0x18003ba22  retn
0x18003ba23  lea     rax, aTypeEAmbiguous; "TYPE_E_AMBIGUOUSNAME"
0x18003ba2a  retn
0x18003ba2b  lea     rax, aTypeEElementno; "TYPE_E_ELEMENTNOTFOUND"
0x18003ba32  retn
0x18003ba33  lea     rax, aTypeEWrongtype; "TYPE_E_WRONGTYPEKIND"
0x18003ba3a  retn
0x18003ba3b  lea     rax, aTypeEBadmodule; "TYPE_E_BADMODULEKIND"
0x18003ba42  retn
0x18003ba43  mov     eax, 80028CA3h
0x18003ba48  cmp     ecx, eax
0x18003ba4a  jg      short loc_18003BABA
0x18003ba4c  jz      short loc_18003BAB2
0x18003ba4e  cmp     ecx, 800288C5h
0x18003ba54  jz      short loc_18003BAAA
0x18003ba56  cmp     ecx, 800288C6h
0x18003ba5c  jz      short loc_18003BAA2
0x18003ba5e  cmp     ecx, 800288CFh
0x18003ba64  jz      short loc_18003BA9A
0x18003ba66  cmp     ecx, 80028CA0h
0x18003ba6c  jz      short loc_18003BA92
0x18003ba6e  cmp     ecx, 80028CA1h
0x18003ba74  jz      short loc_18003BA8A
0x18003ba76  xor     eax, eax
0x18003ba78  lea     rdx, aTypeEIoerror; "TYPE_E_IOERROR"
0x18003ba7f  cmp     ecx, 80028CA2h
0x18003ba85  jmp     loc_18003C513
0x18003ba8a  lea     rax, aTypeEOutofboun; "TYPE_E_OUTOFBOUNDS"
0x18003ba91  retn
0x18003ba92  lea     rax, aTypeETypemisma; "TYPE_E_TYPEMISMATCH"
0x18003ba99  retn
0x18003ba9a  lea     rax, aTypeEInvalidid; "TYPE_E_INVALIDID"
0x18003baa1  retn
0x18003baa2  lea     rax, aTypeEDuplicate; "TYPE_E_DUPLICATEID"
0x18003baa9  retn
0x18003baaa  lea     rax, aTypeESizetoobi; "TYPE_E_SIZETOOBIG"
0x18003bab1  retn
0x18003bab2  lea     rax, aTypeECantcreat; "TYPE_E_CANTCREATETMPFILE"
0x18003bab9  retn
0x18003baba  cmp     ecx, 80029C4Ah
0x18003bac0  jz      short loc_18003BB16
0x18003bac2  cmp     ecx, 80029C83h
0x18003bac8  jz      short loc_18003BB0E
0x18003baca  cmp     ecx, 80029C84h
0x18003bad0  jz      short loc_18003BB06
0x18003bad2  cmp     ecx, 80030001h
0x18003bad8  jz      short loc_18003BAFE
  ... truncated ...
```
