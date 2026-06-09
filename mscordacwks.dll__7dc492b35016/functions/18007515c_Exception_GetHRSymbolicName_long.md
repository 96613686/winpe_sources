# Exception::GetHRSymbolicName(long)

- ea: `0x18007515c`
- end: `0x1800761bd`
- name: `?GetHRSymbolicName@Exception@@SAPEBDJ@Z`
- size: `4193`
- prototype: `const char *__fastcall(int)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800767c4`

## callees

- `0x18007515c`

## string_xrefs

- `0x180075c8a`: `E_ACCESSDENIED`
- `0x1800751d4`: `CO_E_INIT_CLASS_CACHE`
- `0x18007521c`: `CO_E_INIT_ONLY_SINGLE_THREADED`
- `0x180075879`: `OLE_E_NOCACHE`
- `0x1800758b9`: `OLE_E_WRONGCOMPOBJ`
- `0x180075a0f`: `DRAGDROP_E_ALREADYREGISTERED`
- `0x1800759e7`: `REGDB_E_READREGDB`
- `0x1800759df`: `REGDB_E_WRITEREGDB`
- `0x180075aa6`: `CACHE_E_NOCACHE_UPDATED`
- `0x180075b22`: `CLIPBRD_E_CANT_OPEN`
- `0x180075bba`: `MK_E_INVALIDEXTENSION`
- `0x180075bda`: `MK_E_CANTOPENFILE`
- `0x180075c12`: `CO_E_ALREADYINITIALIZED`
- `0x180075c4a`: `CO_E_DLLNOTFOUND`
- `0x180075c52`: `CO_E_ERRORINDLL`
- `0x18007611f`: `VIEW_S_ALREADY_FROZEN`
- `0x180076117`: `CACHE_S_FORMATETC_NOTSUPPORTED`
- `0x18007610f`: `CACHE_S_SAMECACHE`
- `0x180076107`: `CACHE_S_SOMECACHES_NOTUPDATED`
- `0x18007617d`: `MK_S_MONIKERALREADYREGISTERED`
- `0x180075d43`: `CO_E_CLASS_CREATE_FAILED`
- `0x180075d2b`: `CO_E_BAD_PATH`
- `0x180075deb`: `MEM_E_INVALID_LINK`
- `0x180075527`: `TYPE_E_INVDATAREAD`
- `0x180075517`: `TYPE_E_REGISTRYACCESS`
- `0x18007556b`: `TYPE_E_DLLFUNCTIONNOTFOUND`
- `0x180075612`: `TYPE_E_CANTCREATETMPFILE`
- `0x180075676`: `TYPE_E_CANTLOADLIBRARY`
- `0x18007564e`: `STG_E_PATHNOTFOUND`
- `0x18007567e`: `STG_E_TOOMANYOPENFILES`
- `0x180075700`: `STG_E_ACCESSDENIED`
- `0x1800756d8`: `STG_E_DISKISWRITEPROTECTED`
- `0x18007576c`: `STG_E_WRITEFAULT`
- `0x180075764`: `STG_E_READFAULT`
- `0x18007574c`: `STG_E_FILEALREADYEXISTS`
- `0x1800757f9`: `STG_E_OLDDLL`
- `0x18007533c`: `RPC_E_ATTEMPTED_MULTITHREAD`
- `0x18007539c`: `RPC_E_WRONG_THREAD`
- `0x1800753a4`: `RPC_E_THREAD_NOT_INIT`
- `0x180075ea9`: `CTL_E_FILEALREADYOPEN`
- `0x180075e99`: `CTL_E_FILEALREADYEXISTS`
- `0x180075f35`: `CTL_E_DISKNOTREADY`
- `0x180075f2d`: `CTL_E_PATHFILEACCESSERROR`
- `0x180075f25`: `CTL_E_PATHNOTFOUND`
- `0x1800760a8`: `CTL_E_CANTSAVEFILETOTEMP`
- `0x180076098`: `CTL_E_REPLACEMENTSTOOLONG`

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
0x18007515c  mov     eax, 8000FFFFh
0x180075161  cmp     ecx, eax
0x180075163  jg      loc_18007522C
0x180075169  jz      loc_180075224
0x18007516f  add     ecx, 7FFFBFFFh; switch 18 cases
0x180075175  cmp     ecx, 11h
0x180075178  ja      def_180075192; jumptable 0000000180075192 default case
0x18007517e  movsxd  rax, ecx
0x180075181  lea     rcx, __ImageBase
0x180075188  mov     eax, ds:(jpt_180075192 - 180000000h)[rcx+rax*4]
0x18007518f  add     rax, rcx
0x180075192  jmp     rax; switch jump
0x180075194  lea     rax, aENotimpl; jumptable 0000000180075192 case -2147467263
0x18007519b  retn
0x18007519c  lea     rax, aENointerface; jumptable 0000000180075192 case -2147467262
0x1800751a3  retn
0x1800751a4  lea     rax, aEPointer; jumptable 0000000180075192 case -2147467261
0x1800751ab  retn
0x1800751ac  lea     rax, aEAbort; jumptable 0000000180075192 case -2147467260
0x1800751b3  retn
0x1800751b4  lea     rax, aEFail; jumptable 0000000180075192 case -2147467259
0x1800751bb  retn
0x1800751bc  lea     rax, aCoEInitTls; jumptable 0000000180075192 case -2147467258
0x1800751c3  retn
0x1800751c4  lea     rax, aCoEInitSharedA; jumptable 0000000180075192 case -2147467257
0x1800751cb  retn
0x1800751cc  lea     rax, aCoEInitMemoryA; jumptable 0000000180075192 case -2147467256
0x1800751d3  retn
0x1800751d4  lea     rax, aCoEInitClassCa; jumptable 0000000180075192 case -2147467255
0x1800751db  retn
0x1800751dc  lea     rax, aCoEInitRpcChan; jumptable 0000000180075192 case -2147467254
0x1800751e3  retn
0x1800751e4  lea     rax, aCoEInitTlsSetC; jumptable 0000000180075192 case -2147467253
0x1800751eb  retn
0x1800751ec  lea     rax, aCoEInitTlsChan; jumptable 0000000180075192 case -2147467252
0x1800751f3  retn
0x1800751f4  lea     rax, aCoEInitUnaccep; jumptable 0000000180075192 case -2147467251
0x1800751fb  retn
0x1800751fc  lea     rax, aCoEInitScmMute; jumptable 0000000180075192 case -2147467250
0x180075203  retn
0x180075204  lea     rax, aCoEInitScmFile; jumptable 0000000180075192 case -2147467249
0x18007520b  retn
0x18007520c  lea     rax, aCoEInitScmMapV; jumptable 0000000180075192 case -2147467248
0x180075213  retn
0x180075214  lea     rax, aCoEInitScmExec; jumptable 0000000180075192 case -2147467247
0x18007521b  retn
0x18007521c  lea     rax, aCoEInitOnlySin; jumptable 0000000180075192 case -2147467246
0x180075223  retn
0x180075224  lea     rax, aEUnexpected; "E_UNEXPECTED"
0x18007522b  retn
0x18007522c  mov     eax, 80010100h
0x180075231  cmp     ecx, eax
0x180075233  jg      loc_1800752FC
0x180075239  jz      loc_1800752F4
0x18007523f  add     ecx, 7FFEFFFFh; switch 18 cases
0x180075245  cmp     ecx, 11h
0x180075248  ja      def_180075192; jumptable 0000000180075192 default case
0x18007524e  movsxd  rax, ecx
0x180075251  lea     rcx, __ImageBase
0x180075258  mov     eax, ds:(jpt_180075262 - 180000000h)[rcx+rax*4]
0x18007525f  add     rax, rcx
0x180075262  jmp     rax; switch jump
0x180075264  lea     rax, aRpcECallReject; jumptable 0000000180075262 case -2147418111
0x18007526b  retn
0x18007526c  lea     rax, aRpcECallCancel; jumptable 0000000180075262 case -2147418110
0x180075273  retn
0x180075274  lea     rax, aRpcECantpostIn; jumptable 0000000180075262 case -2147418109
0x18007527b  retn
0x18007527c  lea     rax, aRpcECantcallou_0; jumptable 0000000180075262 case -2147418108
0x180075283  retn
0x180075284  lea     rax, aRpcECantcallou_1; jumptable 0000000180075262 case -2147418107
0x18007528b  retn
0x18007528c  lea     rax, aRpcEConnection; jumptable 0000000180075262 case -2147418106
0x180075293  retn
0x180075294  lea     rax, aRpcEServerDied_0; jumptable 0000000180075262 case -2147418105
0x18007529b  retn
0x18007529c  lea     rax, aRpcEClientDied; jumptable 0000000180075262 case -2147418104
0x1800752a3  retn
0x1800752a4  lea     rax, aRpcEInvalidDat; jumptable 0000000180075262 case -2147418103
0x1800752ab  retn
0x1800752ac  lea     rax, aRpcECanttransm; jumptable 0000000180075262 case -2147418102
0x1800752b3  retn
0x1800752b4  lea     rax, aRpcEClientCant_0; jumptable 0000000180075262 case -2147418101
0x1800752bb  retn
0x1800752bc  lea     rax, aRpcEClientCant; jumptable 0000000180075262 case -2147418100
0x1800752c3  retn
0x1800752c4  lea     rax, aRpcEServerCant; jumptable 0000000180075262 case -2147418099
0x1800752cb  retn
0x1800752cc  lea     rax, aRpcEServerCant_0; jumptable 0000000180075262 case -2147418098
0x1800752d3  retn
0x1800752d4  lea     rax, aRpcEInvalidDat_0; jumptable 0000000180075262 case -2147418097
0x1800752db  retn
0x1800752dc  lea     rax, aRpcEInvalidPar; jumptable 0000000180075262 case -2147418096
0x1800752e3  retn
0x1800752e4  lea     rax, aRpcECantcallou_2; jumptable 0000000180075262 case -2147418095
0x1800752eb  retn
0x1800752ec  lea     rax, aRpcEServerDied; jumptable 0000000180075262 case -2147418094
0x1800752f3  retn
0x1800752f4  lea     rax, aRpcESysCallFai; "RPC_E_SYS_CALL_FAILED"
0x1800752fb  retn
0x1800752fc  mov     eax, 8001FFFFh
0x180075301  cmp     ecx, eax
0x180075303  jg      loc_1800753B4
0x180075309  jz      loc_1800753AC
0x18007530f  add     ecx, 7FFEFEFFh; switch 15 cases
0x180075315  cmp     ecx, 0Eh
0x180075318  ja      def_180075192; jumptable 0000000180075192 default case
0x18007531e  movsxd  rax, ecx
0x180075321  lea     rcx, __ImageBase
0x180075328  mov     eax, ds:(jpt_180075332 - 180000000h)[rcx+rax*4]
0x18007532f  add     rax, rcx
0x180075332  jmp     rax; switch jump
0x180075334  lea     rax, aRpcEOutOfResou; jumptable 0000000180075332 case -2147417855
0x18007533b  retn
0x18007533c  lea     rax, aRpcEAttemptedM; jumptable 0000000180075332 case -2147417854
0x180075343  retn
0x180075344  lea     rax, aRpcENotRegiste; jumptable 0000000180075332 case -2147417853
0x18007534b  retn
0x18007534c  lea     rax, aRpcEFault; jumptable 0000000180075332 case -2147417852
0x180075353  retn
0x180075354  lea     rax, aRpcEServerfaul; jumptable 0000000180075332 case -2147417851
0x18007535b  retn
0x18007535c  lea     rax, aRpcEChangedMod; jumptable 0000000180075332 case -2147417850
0x180075363  retn
0x180075364  lea     rax, aRpcEInvalidmet; jumptable 0000000180075332 case -2147417849
0x18007536b  retn
0x18007536c  lea     rax, aRpcEDisconnect; jumptable 0000000180075332 case -2147417848
0x180075373  retn
0x180075374  lea     rax, aRpcERetry; jumptable 0000000180075332 case -2147417847
0x18007537b  retn
0x18007537c  lea     rax, aRpcEServercall_0; jumptable 0000000180075332 case -2147417846
0x180075383  retn
0x180075384  lea     rax, aRpcEServercall; jumptable 0000000180075332 case -2147417845
0x18007538b  retn
0x18007538c  lea     rax, aRpcEInvalidCal; jumptable 0000000180075332 case -2147417844
0x180075393  retn
0x180075394  lea     rax, aRpcECantcallou; jumptable 0000000180075332 case -2147417843
0x18007539b  retn
0x18007539c  lea     rax, aRpcEWrongThrea; jumptable 0000000180075332 case -2147417842
0x1800753a3  retn
0x1800753a4  lea     rax, aRpcEThreadNotI; jumptable 0000000180075332 case -2147417841
0x1800753ab  retn
0x1800753ac  lea     rax, aRpcEUnexpected; "RPC_E_UNEXPECTED"
0x1800753b3  retn
0x1800753b4  mov     eax, 80028016h
0x1800753b9  cmp     ecx, eax
0x1800753bb  jg      loc_180075474
0x1800753c1  jz      loc_18007546C
0x1800753c7  add     ecx, 7FFDFFFFh; switch 17 cases
0x1800753cd  cmp     ecx, 10h
0x1800753d0  ja      def_180075192; jumptable 0000000180075192 default case
0x1800753d6  movsxd  rax, ecx
0x1800753d9  lea     rcx, __ImageBase
0x1800753e0  mov     eax, ds:(jpt_1800753EA - 180000000h)[rcx+rax*4]
0x1800753e7  add     rax, rcx
0x1800753ea  jmp     rax; switch jump
0x1800753ec  lea     rax, aDispEUnknownin; jumptable 00000001800753EA case -2147352575
0x1800753f3  retn
0x1800753f4  lea     rax, aDispEMembernot; jumptable 00000001800753EA case -2147352573
0x1800753fb  retn
0x1800753fc  lea     rax, aDispEParamnotf; jumptable 00000001800753EA case -2147352572
0x180075403  retn
0x180075404  lea     rax, aDispETypemisma; jumptable 00000001800753EA case -2147352571
0x18007540b  retn
0x18007540c  lea     rax, aDispEUnknownna; jumptable 00000001800753EA case -2147352570
0x180075413  retn
0x180075414  lea     rax, aDispENonamedar; jumptable 00000001800753EA case -2147352569
0x18007541b  retn
0x18007541c  lea     rax, aDispEBadvartyp; jumptable 00000001800753EA case -2147352568
0x180075423  retn
0x180075424  lea     rax, aDispEException; jumptable 00000001800753EA case -2147352567
0x18007542b  retn
0x18007542c  lea     rax, aDispEOverflow; jumptable 00000001800753EA case -2147352566
0x180075433  retn
0x180075434  lea     rax, aDispEBadindex; jumptable 00000001800753EA case -2147352565
0x18007543b  retn
0x18007543c  lea     rax, aDispEUnknownlc; jumptable 00000001800753EA case -2147352564
0x180075443  retn
0x180075444  lea     rax, aDispEArrayislo; jumptable 00000001800753EA case -2147352563
0x18007544b  retn
0x18007544c  lea     rax, aDispEBadparamc; jumptable 00000001800753EA case -2147352562
0x180075453  retn
0x180075454  lea     rax, aDispEParamnoto; jumptable 00000001800753EA case -2147352561
0x18007545b  retn
0x18007545c  lea     rax, aDispEBadcallee; jumptable 00000001800753EA case -2147352560
0x180075463  retn
0x180075464  lea     rax, aDispENotacolle; jumptable 00000001800753EA case -2147352559
0x18007546b  retn
0x18007546c  lea     rax, aTypeEBuffertoo; "TYPE_E_BUFFERTOOSMALL"
0x180075473  retn
0x180075474  mov     eax, 800401D4h
0x180075479  cmp     ecx, eax
0x18007547b  jg      loc_180075B52
0x180075481  jz      loc_180075B4A
0x180075487  mov     eax, 80030107h
0x18007548c  cmp     ecx, eax
0x18007548e  jg      loc_180075811
0x180075494  jz      loc_180075809
0x18007549a  mov     eax, 80030004h
0x18007549f  cmp     ecx, eax
0x1800754a1  jg      loc_180075686
0x1800754a7  jz      loc_18007567E
0x1800754ad  mov     eax, 800288BDh
0x1800754b2  cmp     ecx, eax
0x1800754b4  jg      loc_1800755A3
0x1800754ba  jz      loc_18007559B
0x1800754c0  mov     eax, 80028029h
0x1800754c5  cmp     ecx, eax
0x1800754c7  jg      short loc_180075537
0x1800754c9  jz      short loc_18007552F
0x1800754cb  cmp     ecx, 80028018h
0x1800754d1  jz      short loc_180075527
0x1800754d3  cmp     ecx, 80028019h
0x1800754d9  jz      short loc_18007551F
0x1800754db  cmp     ecx, 8002801Ch
0x1800754e1  jz      short loc_180075517
0x1800754e3  cmp     ecx, 8002801Dh
0x1800754e9  jz      short loc_18007550F
0x1800754eb  cmp     ecx, 80028027h
0x1800754f1  jz      short loc_180075507
0x1800754f3  cmp     ecx, 80028028h
0x1800754f9  jnz     def_180075192; jumptable 0000000180075192 default case
0x1800754ff  lea     rax, aTypeEQualified; "TYPE_E_QUALIFIEDNAMEDISALLOWED"
0x180075506  retn
0x180075507  lea     rax, aTypeEUndefined; "TYPE_E_UNDEFINEDTYPE"
0x18007550e  retn
0x18007550f  lea     rax, aTypeELibnotreg; "TYPE_E_LIBNOTREGISTERED"
0x180075516  retn
0x180075517  lea     rax, aTypeERegistrya; "TYPE_E_REGISTRYACCESS"
0x18007551e  retn
0x18007551f  lea     rax, aTypeEUnsupform; "TYPE_E_UNSUPFORMAT"
0x180075526  retn
0x180075527  lea     rax, aTypeEInvdatare; "TYPE_E_INVDATAREAD"
0x18007552e  retn
0x18007552f  lea     rax, aTypeEInvalidst; "TYPE_E_INVALIDSTATE"
0x180075536  retn
0x180075537  cmp     ecx, 8002802Ah
0x18007553d  jz      short loc_180075593
0x18007553f  cmp     ecx, 8002802Bh
0x180075545  jz      short loc_18007558B
0x180075547  cmp     ecx, 8002802Ch
0x18007554d  jz      short loc_180075583
0x18007554f  cmp     ecx, 8002802Dh
0x180075555  jz      short loc_18007557B
0x180075557  cmp     ecx, 8002802Eh
0x18007555d  jz      short loc_180075573
0x18007555f  cmp     ecx, 8002802Fh
0x180075565  jnz     def_180075192; jumptable 0000000180075192 default case
0x18007556b  lea     rax, aTypeEDllfuncti; "TYPE_E_DLLFUNCTIONNOTFOUND"
0x180075572  retn
0x180075573  lea     rax, aTypeEUnknownlc; "TYPE_E_UNKNOWNLCID"
0x18007557a  retn
0x18007557b  lea     rax, aTypeENameconfl; "TYPE_E_NAMECONFLICT"
0x180075582  retn
0x180075583  lea     rax, aTypeEAmbiguous; "TYPE_E_AMBIGUOUSNAME"
0x18007558a  retn
0x18007558b  lea     rax, aTypeEElementno; "TYPE_E_ELEMENTNOTFOUND"
0x180075592  retn
0x180075593  lea     rax, aTypeEWrongtype; "TYPE_E_WRONGTYPEKIND"
0x18007559a  retn
0x18007559b  lea     rax, aTypeEBadmodule; "TYPE_E_BADMODULEKIND"
0x1800755a2  retn
0x1800755a3  mov     eax, 80028CA3h
0x1800755a8  cmp     ecx, eax
0x1800755aa  jg      short loc_18007561A
0x1800755ac  jz      short loc_180075612
0x1800755ae  cmp     ecx, 800288C5h
0x1800755b4  jz      short loc_18007560A
0x1800755b6  cmp     ecx, 800288C6h
0x1800755bc  jz      short loc_180075602
0x1800755be  cmp     ecx, 800288CFh
0x1800755c4  jz      short loc_1800755FA
0x1800755c6  cmp     ecx, 80028CA0h
0x1800755cc  jz      short loc_1800755F2
0x1800755ce  cmp     ecx, 80028CA1h
0x1800755d4  jz      short loc_1800755EA
0x1800755d6  cmp     ecx, 80028CA2h
0x1800755dc  jnz     def_180075192; jumptable 0000000180075192 default case
0x1800755e2  lea     rax, aTypeEIoerror; "TYPE_E_IOERROR"
0x1800755e9  retn
0x1800755ea  lea     rax, aTypeEOutofboun; "TYPE_E_OUTOFBOUNDS"
0x1800755f1  retn
0x1800755f2  lea     rax, aTypeETypemisma; "TYPE_E_TYPEMISMATCH"
0x1800755f9  retn
0x1800755fa  lea     rax, aTypeEInvalidid; "TYPE_E_INVALIDID"
0x180075601  retn
0x180075602  lea     rax, aTypeEDuplicate; "TYPE_E_DUPLICATEID"
0x180075609  retn
0x18007560a  lea     rax, aTypeESizetoobi; "TYPE_E_SIZETOOBIG"
0x180075611  retn
0x180075612  lea     rax, aTypeECantcreat; "TYPE_E_CANTCREATETMPFILE"
0x180075619  retn
0x18007561a  cmp     ecx, 80029C4Ah
0x180075620  jz      short loc_180075676
0x180075622  cmp     ecx, 80029C83h
0x180075628  jz      short loc_18007566E
0x18007562a  cmp     ecx, 80029C84h
0x180075630  jz      short loc_180075666
0x180075632  cmp     ecx, 80030001h
0x180075638  jz      short loc_18007565E
  ... truncated ...
```
