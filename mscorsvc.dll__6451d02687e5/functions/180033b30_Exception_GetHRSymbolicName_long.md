# Exception::GetHRSymbolicName(long)

- ea: `0x180033b30`
- end: `0x180034b91`
- name: `?GetHRSymbolicName@Exception@@SAPEBDJ@Z`
- size: `4193`
- prototype: `const char *__fastcall(int)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180035228`

## callees

- `0x180033b30`

## string_xrefs

- `0x18003465e`: `E_ACCESSDENIED`
- `0x180033ba8`: `CO_E_INIT_CLASS_CACHE`
- `0x180033bf0`: `CO_E_INIT_ONLY_SINGLE_THREADED`
- `0x18003424d`: `OLE_E_NOCACHE`
- `0x18003428d`: `OLE_E_WRONGCOMPOBJ`
- `0x1800343e3`: `DRAGDROP_E_ALREADYREGISTERED`
- `0x1800343bb`: `REGDB_E_READREGDB`
- `0x1800343b3`: `REGDB_E_WRITEREGDB`
- `0x18003447a`: `CACHE_E_NOCACHE_UPDATED`
- `0x1800344f6`: `CLIPBRD_E_CANT_OPEN`
- `0x18003458e`: `MK_E_INVALIDEXTENSION`
- `0x1800345ae`: `MK_E_CANTOPENFILE`
- `0x1800345e6`: `CO_E_ALREADYINITIALIZED`
- `0x18003461e`: `CO_E_DLLNOTFOUND`
- `0x180034626`: `CO_E_ERRORINDLL`
- `0x180034af3`: `VIEW_S_ALREADY_FROZEN`
- `0x180034aeb`: `CACHE_S_FORMATETC_NOTSUPPORTED`
- `0x180034ae3`: `CACHE_S_SAMECACHE`
- `0x180034adb`: `CACHE_S_SOMECACHES_NOTUPDATED`
- `0x180034b51`: `MK_S_MONIKERALREADYREGISTERED`
- `0x180034717`: `CO_E_CLASS_CREATE_FAILED`
- `0x1800346ff`: `CO_E_BAD_PATH`
- `0x1800347bf`: `MEM_E_INVALID_LINK`
- `0x180033efb`: `TYPE_E_INVDATAREAD`
- `0x180033eeb`: `TYPE_E_REGISTRYACCESS`
- `0x180033f3f`: `TYPE_E_DLLFUNCTIONNOTFOUND`
- `0x180033fe6`: `TYPE_E_CANTCREATETMPFILE`
- `0x18003404a`: `TYPE_E_CANTLOADLIBRARY`
- `0x180034022`: `STG_E_PATHNOTFOUND`
- `0x180034052`: `STG_E_TOOMANYOPENFILES`
- `0x1800340d4`: `STG_E_ACCESSDENIED`
- `0x1800340ac`: `STG_E_DISKISWRITEPROTECTED`
- `0x180034140`: `STG_E_WRITEFAULT`
- `0x180034138`: `STG_E_READFAULT`
- `0x180034120`: `STG_E_FILEALREADYEXISTS`
- `0x1800341cd`: `STG_E_OLDDLL`
- `0x180033d10`: `RPC_E_ATTEMPTED_MULTITHREAD`
- `0x180033d70`: `RPC_E_WRONG_THREAD`
- `0x180033d78`: `RPC_E_THREAD_NOT_INIT`
- `0x18003487d`: `CTL_E_FILEALREADYOPEN`
- `0x18003486d`: `CTL_E_FILEALREADYEXISTS`
- `0x180034909`: `CTL_E_DISKNOTREADY`
- `0x180034901`: `CTL_E_PATHFILEACCESSERROR`
- `0x1800348f9`: `CTL_E_PATHNOTFOUND`
- `0x180034a7c`: `CTL_E_CANTSAVEFILETOTEMP`
- `0x180034a6c`: `CTL_E_REPLACEMENTSTOOLONG`

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
0x180033b30  mov     eax, 8000FFFFh
0x180033b35  cmp     ecx, eax
0x180033b37  jg      loc_180033C00
0x180033b3d  jz      loc_180033BF8
0x180033b43  add     ecx, 7FFFBFFFh; switch 18 cases
0x180033b49  cmp     ecx, 11h
0x180033b4c  ja      def_180033B66; jumptable 0000000180033B66 default case
0x180033b52  movsxd  rax, ecx
0x180033b55  lea     rcx, __ImageBase
0x180033b5c  mov     eax, ds:(jpt_180033B66 - 180000000h)[rcx+rax*4]
0x180033b63  add     rax, rcx
0x180033b66  jmp     rax; switch jump
0x180033b68  lea     rax, aENotimpl; jumptable 0000000180033B66 case -2147467263
0x180033b6f  retn
0x180033b70  lea     rax, aENointerface; jumptable 0000000180033B66 case -2147467262
0x180033b77  retn
0x180033b78  lea     rax, aEPointer; jumptable 0000000180033B66 case -2147467261
0x180033b7f  retn
0x180033b80  lea     rax, aEAbort; jumptable 0000000180033B66 case -2147467260
0x180033b87  retn
0x180033b88  lea     rax, aEFail; jumptable 0000000180033B66 case -2147467259
0x180033b8f  retn
0x180033b90  lea     rax, aCoEInitTls; jumptable 0000000180033B66 case -2147467258
0x180033b97  retn
0x180033b98  lea     rax, aCoEInitSharedA; jumptable 0000000180033B66 case -2147467257
0x180033b9f  retn
0x180033ba0  lea     rax, aCoEInitMemoryA; jumptable 0000000180033B66 case -2147467256
0x180033ba7  retn
0x180033ba8  lea     rax, aCoEInitClassCa; jumptable 0000000180033B66 case -2147467255
0x180033baf  retn
0x180033bb0  lea     rax, aCoEInitRpcChan; jumptable 0000000180033B66 case -2147467254
0x180033bb7  retn
0x180033bb8  lea     rax, aCoEInitTlsSetC; jumptable 0000000180033B66 case -2147467253
0x180033bbf  retn
0x180033bc0  lea     rax, aCoEInitTlsChan; jumptable 0000000180033B66 case -2147467252
0x180033bc7  retn
0x180033bc8  lea     rax, aCoEInitUnaccep; jumptable 0000000180033B66 case -2147467251
0x180033bcf  retn
0x180033bd0  lea     rax, aCoEInitScmMute; jumptable 0000000180033B66 case -2147467250
0x180033bd7  retn
0x180033bd8  lea     rax, aCoEInitScmFile; jumptable 0000000180033B66 case -2147467249
0x180033bdf  retn
0x180033be0  lea     rax, aCoEInitScmMapV; jumptable 0000000180033B66 case -2147467248
0x180033be7  retn
0x180033be8  lea     rax, aCoEInitScmExec; jumptable 0000000180033B66 case -2147467247
0x180033bef  retn
0x180033bf0  lea     rax, aCoEInitOnlySin; jumptable 0000000180033B66 case -2147467246
0x180033bf7  retn
0x180033bf8  lea     rax, aEUnexpected; "E_UNEXPECTED"
0x180033bff  retn
0x180033c00  mov     eax, 80010100h
0x180033c05  cmp     ecx, eax
0x180033c07  jg      loc_180033CD0
0x180033c0d  jz      loc_180033CC8
0x180033c13  add     ecx, 7FFEFFFFh; switch 18 cases
0x180033c19  cmp     ecx, 11h
0x180033c1c  ja      def_180033B66; jumptable 0000000180033B66 default case
0x180033c22  movsxd  rax, ecx
0x180033c25  lea     rcx, __ImageBase
0x180033c2c  mov     eax, ds:(jpt_180033C36 - 180000000h)[rcx+rax*4]
0x180033c33  add     rax, rcx
0x180033c36  jmp     rax; switch jump
0x180033c38  lea     rax, aRpcECallReject; jumptable 0000000180033C36 case -2147418111
0x180033c3f  retn
0x180033c40  lea     rax, aRpcECallCancel; jumptable 0000000180033C36 case -2147418110
0x180033c47  retn
0x180033c48  lea     rax, aRpcECantpostIn; jumptable 0000000180033C36 case -2147418109
0x180033c4f  retn
0x180033c50  lea     rax, aRpcECantcallou_0; jumptable 0000000180033C36 case -2147418108
0x180033c57  retn
0x180033c58  lea     rax, aRpcECantcallou_1; jumptable 0000000180033C36 case -2147418107
0x180033c5f  retn
0x180033c60  lea     rax, aRpcEConnection; jumptable 0000000180033C36 case -2147418106
0x180033c67  retn
0x180033c68  lea     rax, aRpcEServerDied_0; jumptable 0000000180033C36 case -2147418105
0x180033c6f  retn
0x180033c70  lea     rax, aRpcEClientDied; jumptable 0000000180033C36 case -2147418104
0x180033c77  retn
0x180033c78  lea     rax, aRpcEInvalidDat; jumptable 0000000180033C36 case -2147418103
0x180033c7f  retn
0x180033c80  lea     rax, aRpcECanttransm; jumptable 0000000180033C36 case -2147418102
0x180033c87  retn
0x180033c88  lea     rax, aRpcEClientCant_0; jumptable 0000000180033C36 case -2147418101
0x180033c8f  retn
0x180033c90  lea     rax, aRpcEClientCant; jumptable 0000000180033C36 case -2147418100
0x180033c97  retn
0x180033c98  lea     rax, aRpcEServerCant; jumptable 0000000180033C36 case -2147418099
0x180033c9f  retn
0x180033ca0  lea     rax, aRpcEServerCant_0; jumptable 0000000180033C36 case -2147418098
0x180033ca7  retn
0x180033ca8  lea     rax, aRpcEInvalidDat_0; jumptable 0000000180033C36 case -2147418097
0x180033caf  retn
0x180033cb0  lea     rax, aRpcEInvalidPar; jumptable 0000000180033C36 case -2147418096
0x180033cb7  retn
0x180033cb8  lea     rax, aRpcECantcallou_2; jumptable 0000000180033C36 case -2147418095
0x180033cbf  retn
0x180033cc0  lea     rax, aRpcEServerDied; jumptable 0000000180033C36 case -2147418094
0x180033cc7  retn
0x180033cc8  lea     rax, aRpcESysCallFai; "RPC_E_SYS_CALL_FAILED"
0x180033ccf  retn
0x180033cd0  mov     eax, 8001FFFFh
0x180033cd5  cmp     ecx, eax
0x180033cd7  jg      loc_180033D88
0x180033cdd  jz      loc_180033D80
0x180033ce3  add     ecx, 7FFEFEFFh; switch 15 cases
0x180033ce9  cmp     ecx, 0Eh
0x180033cec  ja      def_180033B66; jumptable 0000000180033B66 default case
0x180033cf2  movsxd  rax, ecx
0x180033cf5  lea     rcx, __ImageBase
0x180033cfc  mov     eax, ds:(jpt_180033D06 - 180000000h)[rcx+rax*4]
0x180033d03  add     rax, rcx
0x180033d06  jmp     rax; switch jump
0x180033d08  lea     rax, aRpcEOutOfResou; jumptable 0000000180033D06 case -2147417855
0x180033d0f  retn
0x180033d10  lea     rax, aRpcEAttemptedM; jumptable 0000000180033D06 case -2147417854
0x180033d17  retn
0x180033d18  lea     rax, aRpcENotRegiste; jumptable 0000000180033D06 case -2147417853
0x180033d1f  retn
0x180033d20  lea     rax, aRpcEFault; jumptable 0000000180033D06 case -2147417852
0x180033d27  retn
0x180033d28  lea     rax, aRpcEServerfaul; jumptable 0000000180033D06 case -2147417851
0x180033d2f  retn
0x180033d30  lea     rax, aRpcEChangedMod; jumptable 0000000180033D06 case -2147417850
0x180033d37  retn
0x180033d38  lea     rax, aRpcEInvalidmet; jumptable 0000000180033D06 case -2147417849
0x180033d3f  retn
0x180033d40  lea     rax, aRpcEDisconnect; jumptable 0000000180033D06 case -2147417848
0x180033d47  retn
0x180033d48  lea     rax, aRpcERetry; jumptable 0000000180033D06 case -2147417847
0x180033d4f  retn
0x180033d50  lea     rax, aRpcEServercall_0; jumptable 0000000180033D06 case -2147417846
0x180033d57  retn
0x180033d58  lea     rax, aRpcEServercall; jumptable 0000000180033D06 case -2147417845
0x180033d5f  retn
0x180033d60  lea     rax, aRpcEInvalidCal; jumptable 0000000180033D06 case -2147417844
0x180033d67  retn
0x180033d68  lea     rax, aRpcECantcallou; jumptable 0000000180033D06 case -2147417843
0x180033d6f  retn
0x180033d70  lea     rax, aRpcEWrongThrea; jumptable 0000000180033D06 case -2147417842
0x180033d77  retn
0x180033d78  lea     rax, aRpcEThreadNotI; jumptable 0000000180033D06 case -2147417841
0x180033d7f  retn
0x180033d80  lea     rax, aRpcEUnexpected; "RPC_E_UNEXPECTED"
0x180033d87  retn
0x180033d88  mov     eax, 80028016h
0x180033d8d  cmp     ecx, eax
0x180033d8f  jg      loc_180033E48
0x180033d95  jz      loc_180033E40
0x180033d9b  add     ecx, 7FFDFFFFh; switch 17 cases
0x180033da1  cmp     ecx, 10h
0x180033da4  ja      def_180033B66; jumptable 0000000180033B66 default case
0x180033daa  movsxd  rax, ecx
0x180033dad  lea     rcx, __ImageBase
0x180033db4  mov     eax, ds:(jpt_180033DBE - 180000000h)[rcx+rax*4]
0x180033dbb  add     rax, rcx
0x180033dbe  jmp     rax; switch jump
0x180033dc0  lea     rax, aDispEUnknownin; jumptable 0000000180033DBE case -2147352575
0x180033dc7  retn
0x180033dc8  lea     rax, aDispEMembernot; jumptable 0000000180033DBE case -2147352573
0x180033dcf  retn
0x180033dd0  lea     rax, aDispEParamnotf; jumptable 0000000180033DBE case -2147352572
0x180033dd7  retn
0x180033dd8  lea     rax, aDispETypemisma; jumptable 0000000180033DBE case -2147352571
0x180033ddf  retn
0x180033de0  lea     rax, aDispEUnknownna; jumptable 0000000180033DBE case -2147352570
0x180033de7  retn
0x180033de8  lea     rax, aDispENonamedar; jumptable 0000000180033DBE case -2147352569
0x180033def  retn
0x180033df0  lea     rax, aDispEBadvartyp; jumptable 0000000180033DBE case -2147352568
0x180033df7  retn
0x180033df8  lea     rax, aDispEException; jumptable 0000000180033DBE case -2147352567
0x180033dff  retn
0x180033e00  lea     rax, aDispEOverflow; jumptable 0000000180033DBE case -2147352566
0x180033e07  retn
0x180033e08  lea     rax, aDispEBadindex; jumptable 0000000180033DBE case -2147352565
0x180033e0f  retn
0x180033e10  lea     rax, aDispEUnknownlc; jumptable 0000000180033DBE case -2147352564
0x180033e17  retn
0x180033e18  lea     rax, aDispEArrayislo; jumptable 0000000180033DBE case -2147352563
0x180033e1f  retn
0x180033e20  lea     rax, aDispEBadparamc; jumptable 0000000180033DBE case -2147352562
0x180033e27  retn
0x180033e28  lea     rax, aDispEParamnoto; jumptable 0000000180033DBE case -2147352561
0x180033e2f  retn
0x180033e30  lea     rax, aDispEBadcallee; jumptable 0000000180033DBE case -2147352560
0x180033e37  retn
0x180033e38  lea     rax, aDispENotacolle; jumptable 0000000180033DBE case -2147352559
0x180033e3f  retn
0x180033e40  lea     rax, aTypeEBuffertoo; "TYPE_E_BUFFERTOOSMALL"
0x180033e47  retn
0x180033e48  mov     eax, 800401D4h
0x180033e4d  cmp     ecx, eax
0x180033e4f  jg      loc_180034526
0x180033e55  jz      loc_18003451E
0x180033e5b  mov     eax, 80030107h
0x180033e60  cmp     ecx, eax
0x180033e62  jg      loc_1800341E5
0x180033e68  jz      loc_1800341DD
0x180033e6e  mov     eax, 80030004h
0x180033e73  cmp     ecx, eax
0x180033e75  jg      loc_18003405A
0x180033e7b  jz      loc_180034052
0x180033e81  mov     eax, 800288BDh
0x180033e86  cmp     ecx, eax
0x180033e88  jg      loc_180033F77
0x180033e8e  jz      loc_180033F6F
0x180033e94  mov     eax, 80028029h
0x180033e99  cmp     ecx, eax
0x180033e9b  jg      short loc_180033F0B
0x180033e9d  jz      short loc_180033F03
0x180033e9f  cmp     ecx, 80028018h
0x180033ea5  jz      short loc_180033EFB
0x180033ea7  cmp     ecx, 80028019h
0x180033ead  jz      short loc_180033EF3
0x180033eaf  cmp     ecx, 8002801Ch
0x180033eb5  jz      short loc_180033EEB
0x180033eb7  cmp     ecx, 8002801Dh
0x180033ebd  jz      short loc_180033EE3
0x180033ebf  cmp     ecx, 80028027h
0x180033ec5  jz      short loc_180033EDB
0x180033ec7  cmp     ecx, 80028028h
0x180033ecd  jnz     def_180033B66; jumptable 0000000180033B66 default case
0x180033ed3  lea     rax, aTypeEQualified; "TYPE_E_QUALIFIEDNAMEDISALLOWED"
0x180033eda  retn
0x180033edb  lea     rax, aTypeEUndefined; "TYPE_E_UNDEFINEDTYPE"
0x180033ee2  retn
0x180033ee3  lea     rax, aTypeELibnotreg; "TYPE_E_LIBNOTREGISTERED"
0x180033eea  retn
0x180033eeb  lea     rax, aTypeERegistrya; "TYPE_E_REGISTRYACCESS"
0x180033ef2  retn
0x180033ef3  lea     rax, aTypeEUnsupform; "TYPE_E_UNSUPFORMAT"
0x180033efa  retn
0x180033efb  lea     rax, aTypeEInvdatare; "TYPE_E_INVDATAREAD"
0x180033f02  retn
0x180033f03  lea     rax, aTypeEInvalidst; "TYPE_E_INVALIDSTATE"
0x180033f0a  retn
0x180033f0b  cmp     ecx, 8002802Ah
0x180033f11  jz      short loc_180033F67
0x180033f13  cmp     ecx, 8002802Bh
0x180033f19  jz      short loc_180033F5F
0x180033f1b  cmp     ecx, 8002802Ch
0x180033f21  jz      short loc_180033F57
0x180033f23  cmp     ecx, 8002802Dh
0x180033f29  jz      short loc_180033F4F
0x180033f2b  cmp     ecx, 8002802Eh
0x180033f31  jz      short loc_180033F47
0x180033f33  cmp     ecx, 8002802Fh
0x180033f39  jnz     def_180033B66; jumptable 0000000180033B66 default case
0x180033f3f  lea     rax, aTypeEDllfuncti; "TYPE_E_DLLFUNCTIONNOTFOUND"
0x180033f46  retn
0x180033f47  lea     rax, aTypeEUnknownlc; "TYPE_E_UNKNOWNLCID"
0x180033f4e  retn
0x180033f4f  lea     rax, aTypeENameconfl; "TYPE_E_NAMECONFLICT"
0x180033f56  retn
0x180033f57  lea     rax, aTypeEAmbiguous; "TYPE_E_AMBIGUOUSNAME"
0x180033f5e  retn
0x180033f5f  lea     rax, aTypeEElementno; "TYPE_E_ELEMENTNOTFOUND"
0x180033f66  retn
0x180033f67  lea     rax, aTypeEWrongtype; "TYPE_E_WRONGTYPEKIND"
0x180033f6e  retn
0x180033f6f  lea     rax, aTypeEBadmodule; "TYPE_E_BADMODULEKIND"
0x180033f76  retn
0x180033f77  mov     eax, 80028CA3h
0x180033f7c  cmp     ecx, eax
0x180033f7e  jg      short loc_180033FEE
0x180033f80  jz      short loc_180033FE6
0x180033f82  cmp     ecx, 800288C5h
0x180033f88  jz      short loc_180033FDE
0x180033f8a  cmp     ecx, 800288C6h
0x180033f90  jz      short loc_180033FD6
0x180033f92  cmp     ecx, 800288CFh
0x180033f98  jz      short loc_180033FCE
0x180033f9a  cmp     ecx, 80028CA0h
0x180033fa0  jz      short loc_180033FC6
0x180033fa2  cmp     ecx, 80028CA1h
0x180033fa8  jz      short loc_180033FBE
0x180033faa  cmp     ecx, 80028CA2h
0x180033fb0  jnz     def_180033B66; jumptable 0000000180033B66 default case
0x180033fb6  lea     rax, aTypeEIoerror; "TYPE_E_IOERROR"
0x180033fbd  retn
0x180033fbe  lea     rax, aTypeEOutofboun; "TYPE_E_OUTOFBOUNDS"
0x180033fc5  retn
0x180033fc6  lea     rax, aTypeETypemisma; "TYPE_E_TYPEMISMATCH"
0x180033fcd  retn
0x180033fce  lea     rax, aTypeEInvalidid; "TYPE_E_INVALIDID"
0x180033fd5  retn
0x180033fd6  lea     rax, aTypeEDuplicate; "TYPE_E_DUPLICATEID"
0x180033fdd  retn
0x180033fde  lea     rax, aTypeESizetoobi; "TYPE_E_SIZETOOBIG"
0x180033fe5  retn
0x180033fe6  lea     rax, aTypeECantcreat; "TYPE_E_CANTCREATETMPFILE"
0x180033fed  retn
0x180033fee  cmp     ecx, 80029C4Ah
0x180033ff4  jz      short loc_18003404A
0x180033ff6  cmp     ecx, 80029C83h
0x180033ffc  jz      short loc_180034042
0x180033ffe  cmp     ecx, 80029C84h
0x180034004  jz      short loc_18003403A
0x180034006  cmp     ecx, 80030001h
0x18003400c  jz      short loc_180034032
  ... truncated ...
```
