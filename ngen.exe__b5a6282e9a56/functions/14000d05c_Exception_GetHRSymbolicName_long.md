# Exception::GetHRSymbolicName(long)

- ea: `0x14000d05c`
- end: `0x14000e0bd`
- name: `?GetHRSymbolicName@Exception@@SAPEBDJ@Z`
- size: `4193`
- prototype: `const char *__fastcall(int)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14000e748`

## callees

- `0x14000d05c`

## string_xrefs

- `0x14000db8a`: `E_ACCESSDENIED`
- `0x14000d0d4`: `CO_E_INIT_CLASS_CACHE`
- `0x14000d11c`: `CO_E_INIT_ONLY_SINGLE_THREADED`
- `0x14000d779`: `OLE_E_NOCACHE`
- `0x14000d7b9`: `OLE_E_WRONGCOMPOBJ`
- `0x14000d90f`: `DRAGDROP_E_ALREADYREGISTERED`
- `0x14000d8e7`: `REGDB_E_READREGDB`
- `0x14000d8df`: `REGDB_E_WRITEREGDB`
- `0x14000d9a6`: `CACHE_E_NOCACHE_UPDATED`
- `0x14000da22`: `CLIPBRD_E_CANT_OPEN`
- `0x14000daba`: `MK_E_INVALIDEXTENSION`
- `0x14000dada`: `MK_E_CANTOPENFILE`
- `0x14000db12`: `CO_E_ALREADYINITIALIZED`
- `0x14000db4a`: `CO_E_DLLNOTFOUND`
- `0x14000db52`: `CO_E_ERRORINDLL`
- `0x14000e01f`: `VIEW_S_ALREADY_FROZEN`
- `0x14000e017`: `CACHE_S_FORMATETC_NOTSUPPORTED`
- `0x14000e00f`: `CACHE_S_SAMECACHE`
- `0x14000e007`: `CACHE_S_SOMECACHES_NOTUPDATED`
- `0x14000e07d`: `MK_S_MONIKERALREADYREGISTERED`
- `0x14000dc43`: `CO_E_CLASS_CREATE_FAILED`
- `0x14000dc2b`: `CO_E_BAD_PATH`
- `0x14000dceb`: `MEM_E_INVALID_LINK`
- `0x14000d427`: `TYPE_E_INVDATAREAD`
- `0x14000d417`: `TYPE_E_REGISTRYACCESS`
- `0x14000d46b`: `TYPE_E_DLLFUNCTIONNOTFOUND`
- `0x14000d512`: `TYPE_E_CANTCREATETMPFILE`
- `0x14000d576`: `TYPE_E_CANTLOADLIBRARY`
- `0x14000d54e`: `STG_E_PATHNOTFOUND`
- `0x14000d57e`: `STG_E_TOOMANYOPENFILES`
- `0x14000d600`: `STG_E_ACCESSDENIED`
- `0x14000d5d8`: `STG_E_DISKISWRITEPROTECTED`
- `0x14000d66c`: `STG_E_WRITEFAULT`
- `0x14000d664`: `STG_E_READFAULT`
- `0x14000d64c`: `STG_E_FILEALREADYEXISTS`
- `0x14000d6f9`: `STG_E_OLDDLL`
- `0x14000d23c`: `RPC_E_ATTEMPTED_MULTITHREAD`
- `0x14000d29c`: `RPC_E_WRONG_THREAD`
- `0x14000d2a4`: `RPC_E_THREAD_NOT_INIT`
- `0x14000dda9`: `CTL_E_FILEALREADYOPEN`
- `0x14000dd99`: `CTL_E_FILEALREADYEXISTS`
- `0x14000de35`: `CTL_E_DISKNOTREADY`
- `0x14000de2d`: `CTL_E_PATHFILEACCESSERROR`
- `0x14000de25`: `CTL_E_PATHNOTFOUND`
- `0x14000dfa8`: `CTL_E_CANTSAVEFILETOTEMP`
- `0x14000df98`: `CTL_E_REPLACEMENTSTOOLONG`

## pseudocode

```c
const char *__fastcall Exception::GetHRSymbolicName(int a1)
{
  const char *result; // rax
  int v2; // ecx
  int v3; // ecx
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
    if ( a1 <= -2147024891 )
    {
      if ( a1 == -2147024891 )
        return "E_ACCESSDENIED";
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
      return result;
    }
    if ( a1 > -2146827908 )
    {
      if ( a1 > 262146 )
      {
        if ( a1 > 262529 )
        {
          v10 = a1 - 262530;
          if ( !v10 )
            return "OLEOBJ_S_INVALIDHWND";
          v11 = v10 - 30;
          if ( !v11 )
            return "INPLACE_S_TRUNCATED";
          v12 = v11 - 32;
          if ( !v12 )
            return "CONVERT10_S_NO_PRESENTATION";
          v13 = v12 - 34;
          if ( !v13 )
            return "MK_S_REDUCED_TO_SELF";
          v14 = v13 - 2;
          if ( !v14 )
            return "MK_S_ME";
          v15 = v14 - 1;
          if ( !v15 )
            return "MK_S_HIM";
          v16 = v15 - 1;
          if ( !v16 )
            return "MK_S_US";
          if ( v16 == 1 )
            return "MK_S_MONIKERALREADYREGISTERED";
        }
        else
        {
          if ( a1 == 262529 )
            return "OLEOBJ_S_CANNOT_DOVERB_NOW";
          v2 = a1 - 262400;
          if ( !v2 )
            return "DRAGDROP_S_DROP";
          v3 = v2 - 1;
          if ( !v3 )
            return "DRAGDROP_S_CANCEL";
          v4 = v3 - 1;
          if ( !v4 )
            return "DRAGDROP_S_USEDEFAULTCURSORS";
          v5 = v4 - 46;
          if ( !v5 )
            return "DATA_S_SAMEFORMATETC";
          v6 = v5 - 16;
          if ( !v6 )
            return "VIEW_S_ALREADY_FROZEN";
          v7 = v6 - 48;
          if ( !v7 )
            return "CACHE_S_FORMATETC_NOTSUPPORTED";
          v8 = v7 - 1;
          if ( !v8 )
            return "CACHE_S_SAMECACHE";
          v9 = v8 - 1;
          if ( !v9 )
            return "CACHE_S_SOMECACHES_NOTUPDATED";
          if ( v9 == 14 )
            return "OLEOBJ_S_INVALIDVERB";
        }
      }
      else
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
            case 0:
              return "S_OK";
            case 1:
              return "S_FALSE";
            case 197120:
              return "STG_S_CONVERTED";
            case 262144:
              return "OLE_S_USEREG";
            case 262145:
              return "OLE_S_STATIC";
          }
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
            case -2146827828:
              return "CTL_E_INVALIDCLIPBOARDFORMAT";
          }
        }
      }
    }
    else
    {
      if ( a1 == -2146827908 )
        return "CTL_E_INVALIDPROPERTYVALUE";
      if ( a1 > -2146828260 )
      {
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
              case -2146828194:
                return "CTL_E_INVALIDUSEOFNULL";
            }
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
              case -2146828225:
                return "CTL_E_BADRECORDNUMBER";
            }
          }
        }
      }
      else
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
            case -2146828274:
              return "CTL_E_OUTOFSTRINGSPACE";
          }
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
            case -2146959354:
              return "CO_E_OBJSRV_RPC_FAILURE";
          }
        }
      }
    }
    return 0;
  }
  if ( a1 == -2147221036 )
    return "CLIPBRD_E_CANT_CLOSE";
  if ( a1 > -2147286777 )
  {
    if ( a1 <= -2147221404 )
    {
      if ( a1 == -2147221404 )
        return "DV_E_FORMATETC";
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
      return result;
    }
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
          case -2147221037:
            return "CLIPBRD_E_BAD_DATA";
        }
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
          case -2147221055:
            return "CONVERT10_E_OLESTREAM_PUT";
        }
      }
    }
    else
    {
      if ( a1 == -2147221166 )
        return "REGDB_E_KEYMISSING";
      if ( a1 <= -2147221395 )
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
        return "DV_E_DVTARGETDEVICE_SIZE";
      }
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
        case -2147221167:
          return "REGDB_E_WRITEREGDB";
      }
    }
    return 0;
  }
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
          case -2147287037:
            return "STG_E_PATHNOTFOUND";
        }
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
          case -2147316574:
            return "TYPE_E_IOERROR";
        }
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
          case -2147319761:
            return "TYPE_E_DLLFUNCTIONNOTFOUND";
        }
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
          case -2147319768:
            return "TYPE_E_QUALIFIEDNAMEDISALLOWED";
        }
      }
    }
    return 0;
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
        case -2147286953:
          return "STG_E_INVALIDPARAMETER";
      }
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
        case -2147287021:
          return "STG_E_DISKISWRITEPROTECTED";
      }
    }
    return 0;
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
  return result;
}

```

## disassembly

```asm
0x14000d05c  mov     eax, 8000FFFFh
0x14000d061  cmp     ecx, eax
0x14000d063  jg      loc_14000D12C
0x14000d069  jz      loc_14000D124
0x14000d06f  add     ecx, 7FFFBFFFh; switch 18 cases
0x14000d075  cmp     ecx, 11h
0x14000d078  ja      def_14000D092; jumptable 000000014000D092 default case
0x14000d07e  movsxd  rax, ecx
0x14000d081  lea     rcx, cs:140000000h
0x14000d088  mov     eax, ds:(jpt_14000D092 - 140000000h)[rcx+rax*4]
0x14000d08f  add     rax, rcx
0x14000d092  jmp     rax; switch jump
0x14000d094  lea     rax, aENotimpl; jumptable 000000014000D092 case -2147467263
0x14000d09b  retn
0x14000d09c  lea     rax, aENointerface; jumptable 000000014000D092 case -2147467262
0x14000d0a3  retn
0x14000d0a4  lea     rax, aEPointer; jumptable 000000014000D092 case -2147467261
0x14000d0ab  retn
0x14000d0ac  lea     rax, aEAbort; jumptable 000000014000D092 case -2147467260
0x14000d0b3  retn
0x14000d0b4  lea     rax, aEFail; jumptable 000000014000D092 case -2147467259
0x14000d0bb  retn
0x14000d0bc  lea     rax, aCoEInitTls; jumptable 000000014000D092 case -2147467258
0x14000d0c3  retn
0x14000d0c4  lea     rax, aCoEInitSharedA; jumptable 000000014000D092 case -2147467257
0x14000d0cb  retn
0x14000d0cc  lea     rax, aCoEInitMemoryA; jumptable 000000014000D092 case -2147467256
0x14000d0d3  retn
0x14000d0d4  lea     rax, aCoEInitClassCa; jumptable 000000014000D092 case -2147467255
0x14000d0db  retn
0x14000d0dc  lea     rax, aCoEInitRpcChan; jumptable 000000014000D092 case -2147467254
0x14000d0e3  retn
0x14000d0e4  lea     rax, aCoEInitTlsSetC; jumptable 000000014000D092 case -2147467253
0x14000d0eb  retn
0x14000d0ec  lea     rax, aCoEInitTlsChan; jumptable 000000014000D092 case -2147467252
0x14000d0f3  retn
0x14000d0f4  lea     rax, aCoEInitUnaccep; jumptable 000000014000D092 case -2147467251
0x14000d0fb  retn
0x14000d0fc  lea     rax, aCoEInitScmMute; jumptable 000000014000D092 case -2147467250
0x14000d103  retn
0x14000d104  lea     rax, aCoEInitScmFile; jumptable 000000014000D092 case -2147467249
0x14000d10b  retn
0x14000d10c  lea     rax, aCoEInitScmMapV; jumptable 000000014000D092 case -2147467248
0x14000d113  retn
0x14000d114  lea     rax, aCoEInitScmExec; jumptable 000000014000D092 case -2147467247
0x14000d11b  retn
0x14000d11c  lea     rax, aCoEInitOnlySin; jumptable 000000014000D092 case -2147467246
0x14000d123  retn
0x14000d124  lea     rax, aEUnexpected; "E_UNEXPECTED"
0x14000d12b  retn
0x14000d12c  mov     eax, 80010100h
0x14000d131  cmp     ecx, eax
0x14000d133  jg      loc_14000D1FC
0x14000d139  jz      loc_14000D1F4
0x14000d13f  add     ecx, 7FFEFFFFh; switch 18 cases
0x14000d145  cmp     ecx, 11h
0x14000d148  ja      def_14000D092; jumptable 000000014000D092 default case
0x14000d14e  movsxd  rax, ecx
0x14000d151  lea     rcx, cs:140000000h
0x14000d158  mov     eax, ds:(jpt_14000D162 - 140000000h)[rcx+rax*4]
0x14000d15f  add     rax, rcx
0x14000d162  jmp     rax; switch jump
0x14000d164  lea     rax, aRpcECallReject; jumptable 000000014000D162 case -2147418111
0x14000d16b  retn
0x14000d16c  lea     rax, aRpcECallCancel; jumptable 000000014000D162 case -2147418110
0x14000d173  retn
0x14000d174  lea     rax, aRpcECantpostIn; jumptable 000000014000D162 case -2147418109
0x14000d17b  retn
0x14000d17c  lea     rax, aRpcECantcallou_0; jumptable 000000014000D162 case -2147418108
0x14000d183  retn
0x14000d184  lea     rax, aRpcECantcallou_1; jumptable 000000014000D162 case -2147418107
0x14000d18b  retn
0x14000d18c  lea     rax, aRpcEConnection; jumptable 000000014000D162 case -2147418106
0x14000d193  retn
0x14000d194  lea     rax, aRpcEServerDied_0; jumptable 000000014000D162 case -2147418105
0x14000d19b  retn
0x14000d19c  lea     rax, aRpcEClientDied; jumptable 000000014000D162 case -2147418104
0x14000d1a3  retn
0x14000d1a4  lea     rax, aRpcEInvalidDat; jumptable 000000014000D162 case -2147418103
0x14000d1ab  retn
0x14000d1ac  lea     rax, aRpcECanttransm; jumptable 000000014000D162 case -2147418102
0x14000d1b3  retn
0x14000d1b4  lea     rax, aRpcEClientCant_0; jumptable 000000014000D162 case -2147418101
0x14000d1bb  retn
0x14000d1bc  lea     rax, aRpcEClientCant; jumptable 000000014000D162 case -2147418100
0x14000d1c3  retn
0x14000d1c4  lea     rax, aRpcEServerCant; jumptable 000000014000D162 case -2147418099
0x14000d1cb  retn
0x14000d1cc  lea     rax, aRpcEServerCant_0; jumptable 000000014000D162 case -2147418098
0x14000d1d3  retn
0x14000d1d4  lea     rax, aRpcEInvalidDat_0; jumptable 000000014000D162 case -2147418097
0x14000d1db  retn
0x14000d1dc  lea     rax, aRpcEInvalidPar; jumptable 000000014000D162 case -2147418096
0x14000d1e3  retn
0x14000d1e4  lea     rax, aRpcECantcallou_2; jumptable 000000014000D162 case -2147418095
0x14000d1eb  retn
0x14000d1ec  lea     rax, aRpcEServerDied; jumptable 000000014000D162 case -2147418094
0x14000d1f3  retn
0x14000d1f4  lea     rax, aRpcESysCallFai; "RPC_E_SYS_CALL_FAILED"
0x14000d1fb  retn
0x14000d1fc  mov     eax, 8001FFFFh
0x14000d201  cmp     ecx, eax
0x14000d203  jg      loc_14000D2B4
0x14000d209  jz      loc_14000D2AC
0x14000d20f  add     ecx, 7FFEFEFFh; switch 15 cases
0x14000d215  cmp     ecx, 0Eh
0x14000d218  ja      def_14000D092; jumptable 000000014000D092 default case
0x14000d21e  movsxd  rax, ecx
0x14000d221  lea     rcx, cs:140000000h
0x14000d228  mov     eax, ds:(jpt_14000D232 - 140000000h)[rcx+rax*4]
0x14000d22f  add     rax, rcx
0x14000d232  jmp     rax; switch jump
0x14000d234  lea     rax, aRpcEOutOfResou; jumptable 000000014000D232 case -2147417855
0x14000d23b  retn
0x14000d23c  lea     rax, aRpcEAttemptedM; jumptable 000000014000D232 case -2147417854
0x14000d243  retn
0x14000d244  lea     rax, aRpcENotRegiste; jumptable 000000014000D232 case -2147417853
0x14000d24b  retn
0x14000d24c  lea     rax, aRpcEFault; jumptable 000000014000D232 case -2147417852
0x14000d253  retn
0x14000d254  lea     rax, aRpcEServerfaul; jumptable 000000014000D232 case -2147417851
0x14000d25b  retn
0x14000d25c  lea     rax, aRpcEChangedMod; jumptable 000000014000D232 case -2147417850
0x14000d263  retn
0x14000d264  lea     rax, aRpcEInvalidmet; jumptable 000000014000D232 case -2147417849
0x14000d26b  retn
0x14000d26c  lea     rax, aRpcEDisconnect; jumptable 000000014000D232 case -2147417848
0x14000d273  retn
0x14000d274  lea     rax, aRpcERetry; jumptable 000000014000D232 case -2147417847
0x14000d27b  retn
0x14000d27c  lea     rax, aRpcEServercall_0; jumptable 000000014000D232 case -2147417846
0x14000d283  retn
0x14000d284  lea     rax, aRpcEServercall; jumptable 000000014000D232 case -2147417845
0x14000d28b  retn
0x14000d28c  lea     rax, aRpcEInvalidCal; jumptable 000000014000D232 case -2147417844
0x14000d293  retn
0x14000d294  lea     rax, aRpcECantcallou; jumptable 000000014000D232 case -2147417843
0x14000d29b  retn
0x14000d29c  lea     rax, aRpcEWrongThrea; jumptable 000000014000D232 case -2147417842
0x14000d2a3  retn
0x14000d2a4  lea     rax, aRpcEThreadNotI; jumptable 000000014000D232 case -2147417841
0x14000d2ab  retn
0x14000d2ac  lea     rax, aRpcEUnexpected; "RPC_E_UNEXPECTED"
0x14000d2b3  retn
0x14000d2b4  mov     eax, 80028016h
0x14000d2b9  cmp     ecx, eax
0x14000d2bb  jg      loc_14000D374
0x14000d2c1  jz      loc_14000D36C
0x14000d2c7  add     ecx, 7FFDFFFFh; switch 17 cases
0x14000d2cd  cmp     ecx, 10h
0x14000d2d0  ja      def_14000D092; jumptable 000000014000D092 default case
0x14000d2d6  movsxd  rax, ecx
0x14000d2d9  lea     rcx, cs:140000000h
0x14000d2e0  mov     eax, ds:(jpt_14000D2EA - 140000000h)[rcx+rax*4]
0x14000d2e7  add     rax, rcx
0x14000d2ea  jmp     rax; switch jump
0x14000d2ec  lea     rax, aDispEUnknownin; jumptable 000000014000D2EA case -2147352575
0x14000d2f3  retn
0x14000d2f4  lea     rax, aDispEMembernot; jumptable 000000014000D2EA case -2147352573
0x14000d2fb  retn
0x14000d2fc  lea     rax, aDispEParamnotf; jumptable 000000014000D2EA case -2147352572
0x14000d303  retn
0x14000d304  lea     rax, aDispETypemisma; jumptable 000000014000D2EA case -2147352571
0x14000d30b  retn
0x14000d30c  lea     rax, aDispEUnknownna; jumptable 000000014000D2EA case -2147352570
0x14000d313  retn
0x14000d314  lea     rax, aDispENonamedar; jumptable 000000014000D2EA case -2147352569
0x14000d31b  retn
0x14000d31c  lea     rax, aDispEBadvartyp; jumptable 000000014000D2EA case -2147352568
0x14000d323  retn
0x14000d324  lea     rax, aDispEException; jumptable 000000014000D2EA case -2147352567
0x14000d32b  retn
0x14000d32c  lea     rax, aDispEOverflow; jumptable 000000014000D2EA case -2147352566
0x14000d333  retn
0x14000d334  lea     rax, aDispEBadindex; jumptable 000000014000D2EA case -2147352565
0x14000d33b  retn
0x14000d33c  lea     rax, aDispEUnknownlc; jumptable 000000014000D2EA case -2147352564
0x14000d343  retn
0x14000d344  lea     rax, aDispEArrayislo; jumptable 000000014000D2EA case -2147352563
0x14000d34b  retn
0x14000d34c  lea     rax, aDispEBadparamc; jumptable 000000014000D2EA case -2147352562
0x14000d353  retn
0x14000d354  lea     rax, aDispEParamnoto; jumptable 000000014000D2EA case -2147352561
0x14000d35b  retn
0x14000d35c  lea     rax, aDispEBadcallee; jumptable 000000014000D2EA case -2147352560
0x14000d363  retn
0x14000d364  lea     rax, aDispENotacolle; jumptable 000000014000D2EA case -2147352559
0x14000d36b  retn
0x14000d36c  lea     rax, aTypeEBuffertoo; "TYPE_E_BUFFERTOOSMALL"
0x14000d373  retn
0x14000d374  mov     eax, 800401D4h
0x14000d379  cmp     ecx, eax
0x14000d37b  jg      loc_14000DA52
0x14000d381  jz      loc_14000DA4A
0x14000d387  mov     eax, 80030107h
0x14000d38c  cmp     ecx, eax
0x14000d38e  jg      loc_14000D711
0x14000d394  jz      loc_14000D709
0x14000d39a  mov     eax, 80030004h
0x14000d39f  cmp     ecx, eax
0x14000d3a1  jg      loc_14000D586
0x14000d3a7  jz      loc_14000D57E
0x14000d3ad  mov     eax, 800288BDh
0x14000d3b2  cmp     ecx, eax
0x14000d3b4  jg      loc_14000D4A3
0x14000d3ba  jz      loc_14000D49B
0x14000d3c0  mov     eax, 80028029h
0x14000d3c5  cmp     ecx, eax
0x14000d3c7  jg      short loc_14000D437
0x14000d3c9  jz      short loc_14000D42F
0x14000d3cb  cmp     ecx, 80028018h
0x14000d3d1  jz      short loc_14000D427
0x14000d3d3  cmp     ecx, 80028019h
0x14000d3d9  jz      short loc_14000D41F
0x14000d3db  cmp     ecx, 8002801Ch
0x14000d3e1  jz      short loc_14000D417
0x14000d3e3  cmp     ecx, 8002801Dh
0x14000d3e9  jz      short loc_14000D40F
0x14000d3eb  cmp     ecx, 80028027h
0x14000d3f1  jz      short loc_14000D407
0x14000d3f3  cmp     ecx, 80028028h
0x14000d3f9  jnz     def_14000D092; jumptable 000000014000D092 default case
0x14000d3ff  lea     rax, aTypeEQualified; "TYPE_E_QUALIFIEDNAMEDISALLOWED"
0x14000d406  retn
0x14000d407  lea     rax, aTypeEUndefined; "TYPE_E_UNDEFINEDTYPE"
0x14000d40e  retn
0x14000d40f  lea     rax, aTypeELibnotreg; "TYPE_E_LIBNOTREGISTERED"
0x14000d416  retn
0x14000d417  lea     rax, aTypeERegistrya; "TYPE_E_REGISTRYACCESS"
0x14000d41e  retn
0x14000d41f  lea     rax, aTypeEUnsupform; "TYPE_E_UNSUPFORMAT"
0x14000d426  retn
0x14000d427  lea     rax, aTypeEInvdatare; "TYPE_E_INVDATAREAD"
0x14000d42e  retn
0x14000d42f  lea     rax, aTypeEInvalidst; "TYPE_E_INVALIDSTATE"
0x14000d436  retn
0x14000d437  cmp     ecx, 8002802Ah
0x14000d43d  jz      short loc_14000D493
0x14000d43f  cmp     ecx, 8002802Bh
0x14000d445  jz      short loc_14000D48B
0x14000d447  cmp     ecx, 8002802Ch
0x14000d44d  jz      short loc_14000D483
0x14000d44f  cmp     ecx, 8002802Dh
0x14000d455  jz      short loc_14000D47B
0x14000d457  cmp     ecx, 8002802Eh
0x14000d45d  jz      short loc_14000D473
0x14000d45f  cmp     ecx, 8002802Fh
0x14000d465  jnz     def_14000D092; jumptable 000000014000D092 default case
0x14000d46b  lea     rax, aTypeEDllfuncti; "TYPE_E_DLLFUNCTIONNOTFOUND"
0x14000d472  retn
0x14000d473  lea     rax, aTypeEUnknownlc; "TYPE_E_UNKNOWNLCID"
0x14000d47a  retn
0x14000d47b  lea     rax, aTypeENameconfl; "TYPE_E_NAMECONFLICT"
0x14000d482  retn
0x14000d483  lea     rax, aTypeEAmbiguous; "TYPE_E_AMBIGUOUSNAME"
0x14000d48a  retn
0x14000d48b  lea     rax, aTypeEElementno; "TYPE_E_ELEMENTNOTFOUND"
0x14000d492  retn
0x14000d493  lea     rax, aTypeEWrongtype; "TYPE_E_WRONGTYPEKIND"
0x14000d49a  retn
0x14000d49b  lea     rax, aTypeEBadmodule; "TYPE_E_BADMODULEKIND"
0x14000d4a2  retn
0x14000d4a3  mov     eax, 80028CA3h
0x14000d4a8  cmp     ecx, eax
0x14000d4aa  jg      short loc_14000D51A
0x14000d4ac  jz      short loc_14000D512
0x14000d4ae  cmp     ecx, 800288C5h
0x14000d4b4  jz      short loc_14000D50A
0x14000d4b6  cmp     ecx, 800288C6h
0x14000d4bc  jz      short loc_14000D502
0x14000d4be  cmp     ecx, 800288CFh
0x14000d4c4  jz      short loc_14000D4FA
0x14000d4c6  cmp     ecx, 80028CA0h
0x14000d4cc  jz      short loc_14000D4F2
0x14000d4ce  cmp     ecx, 80028CA1h
0x14000d4d4  jz      short loc_14000D4EA
0x14000d4d6  cmp     ecx, 80028CA2h
0x14000d4dc  jnz     def_14000D092; jumptable 000000014000D092 default case
0x14000d4e2  lea     rax, aTypeEIoerror; "TYPE_E_IOERROR"
0x14000d4e9  retn
0x14000d4ea  lea     rax, aTypeEOutofboun; "TYPE_E_OUTOFBOUNDS"
0x14000d4f1  retn
0x14000d4f2  lea     rax, aTypeETypemisma; "TYPE_E_TYPEMISMATCH"
0x14000d4f9  retn
0x14000d4fa  lea     rax, aTypeEInvalidid; "TYPE_E_INVALIDID"
0x14000d501  retn
0x14000d502  lea     rax, aTypeEDuplicate; "TYPE_E_DUPLICATEID"
0x14000d509  retn
0x14000d50a  lea     rax, aTypeESizetoobi; "TYPE_E_SIZETOOBIG"
0x14000d511  retn
0x14000d512  lea     rax, aTypeECantcreat; "TYPE_E_CANTCREATETMPFILE"
0x14000d519  retn
0x14000d51a  cmp     ecx, 80029C4Ah
0x14000d520  jz      short loc_14000D576
0x14000d522  cmp     ecx, 80029C83h
0x14000d528  jz      short loc_14000D56E
0x14000d52a  cmp     ecx, 80029C84h
0x14000d530  jz      short loc_14000D566
0x14000d532  cmp     ecx, 80030001h
0x14000d538  jz      short loc_14000D55E
  ... truncated ...
```
