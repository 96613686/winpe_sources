# OleStdGetUserTypeOfClass(_GUID const &,ushort *,uint,HKEY__ *)

- ea: `0x18009b6c8`
- end: `0x18009b97b`
- name: `?OleStdGetUserTypeOfClass@@YAJAEBU_GUID@@PEAGIPEAUHKEY__@@@Z`
- size: `691`
- prototype: `HRESULT __fastcall(const _GUID *clsid, wchar_t *userType, unsigned int clsid, HKEY__ *userType)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18009bdc0`

## callees

- `0x18000e924`
- `0x18000f358`
- `0x18000fc2c`
- `0x18001217c`
- `0x18001a630`
- `0x180027274`
- `0x18002a618`
- `0x18002fcd8`
- `0x180033bb0`
- `0x18003a394`
- `0x18003bee0`
- `0x180042ffc`
- `0x180046460`
- `0x18009b6c8`
- `0x18009ba88`
- `0x18009bb14`
- `0x1800d8010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!ProgIDFromCLSID` at `0x18009b898`
- `api-ms-win-core-com-l1-1-0!ProgIDFromCLSID` at `0x18009b898`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009b746`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009b746`
- `api-ms-win-core-com-private-l1-3-1!CoIsOle1Class` at `0x18009b86a`
- `api-ms-win-core-com-private-l1-3-1!CoIsOle1Class` at `0x18009b86a`

## string_xrefs

- `0x18009b7dd`: `CLSID\`
- `0x18009b776`: `com\ole32\ole232\stdimpl\icon.cpp`
- `0x18009b802`: `com\ole32\ole232\stdimpl\icon.cpp`
- `0x18009b8b1`: `com\ole32\ole232\stdimpl\icon.cpp`
- `0x18009b8f9`: `com\ole32\ole232\stdimpl\icon.cpp`
- `0x18009b92f`: `com\ole32\ole232\stdimpl\icon.cpp`

## pseudocode

```c
__int64 __fastcall OleStdGetUserTypeOfClass(const _GUID *clsid, wchar_t *userType, unsigned int a3, HKEY__ *a4)
{
  struct IUnknownVtbl *lpVtbl; // rax
  int v7; // ebx
  const wchar_t *StringRawBuffer; // rax
  HRESULT v9; // eax
  unsigned int v10; // eax
  unsigned int v11; // r9d
  unsigned int v12; // edx
  HKEY__ *m_ptr; // r14
  HRESULT v14; // eax
  unsigned __int64 v15; // r10
  unsigned int v16; // edx
  int v17; // ebx
  int v18; // eax
  unsigned int v19; // eax
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (__cdecl*)(HKEY__ *),&RegCloseKey,wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t> > > openedKey; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int valueSize; // [rsp+38h] [rbp-C8h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (__cdecl*)(void *),&CoTaskMemFree,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > > progId; // [rsp+40h] [rbp-C0h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (__cdecl*)(HSTRING__ *),&WindowsDeleteString,wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t> > > displayNameStringOrResourceReference; // [rsp+48h] [rbp-B8h] BYREF
  wil::com_ptr_t<IOleClassInfo,wil::err_returncode_policy> oleClassInfo; // [rsp+50h] [rbp-B0h] BYREF
  GuidString clsidString; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t szKey[128]; // [rsp+B0h] [rbp-50h] BYREF
  void *retaddr; // [rsp+1D8h] [rbp+D8h]

  oleClassInfo.m_ptr = 0;
  if ( GetClassInfoWithInprocOrLocalServer(
         clsid,
         0,
         &GUID_e942fe11_d674_da46_8c4f_c9568fc9d593,
         (void **)&oleClassInfo.m_ptr) < 0 )
  {
    openedKey.m_ptr = 0;
    v10 = OpenClassesRootKeyExW(0, 0x2000000u, &openedKey.m_ptr);
    if ( v10 )
    {
      v11 = v10;
      v12 = 1710;
LABEL_24:
      v7 = wil::details::in1diag3::Return_Win32(retaddr, v12, "com\\ole32\\ole232\\stdimpl\\icon.cpp", v11);
      goto LABEL_25;
    }
    m_ptr = openedKey.m_ptr;
    GuidString::GuidString(&clsidString, clsid);
    v14 = StringCchCopyW(szKey, 0x80u, L"CLSID\\");
    v7 = v14;
    if ( v14 < 0 )
    {
      v16 = 1717;
LABEL_11:
      wil::details::in1diag3::Return_Hr(retaddr, v16, "com\\ole32\\ole232\\stdimpl\\icon.cpp", v14);
LABEL_25:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&openedKey);
      goto LABEL_26;
    }
    v14 = StringCchCatW(szKey, v15, clsidString.m_string);
    v7 = v14;
    if ( v14 < 0 )
    {
      v16 = 1718;
      goto LABEL_11;
    }
    valueSize = 84;
    v17 = wRegQueryValue(m_ptr, szKey, userType, &valueSize);
    if ( !v17 )
    {
LABEL_15:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&openedKey);
      v7 = 0;
      goto LABEL_26;
    }
    if ( !CoIsOle1Class(clsid) )
    {
      v11 = v17;
      v12 = 1741;
      goto LABEL_24;
    }
    progId.m_ptr = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &progId,
      0);
    v18 = ProgIDFromCLSID(clsid, &progId.m_ptr);
    v7 = v18;
    if ( v18 >= 0 )
    {
      valueSize = 84;
      v19 = wRegQueryValue(m_ptr, progId.m_ptr, userType, &valueSize);
      if ( !v19 )
      {
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&progId);
        goto LABEL_15;
      }
      v7 = wil::details::in1diag3::Return_Win32(retaddr, 0x6C8u, "com\\ole32\\ole232\\stdimpl\\icon.cpp", v19);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(retaddr, 0x6C5u, "com\\ole32\\ole232\\stdimpl\\icon.cpp", v18);
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&progId);
    goto LABEL_25;
  }
  lpVtbl = oleClassInfo.m_ptr->lpVtbl;
  displayNameStringOrResourceReference.m_ptr = 0;
  v7 = ((__int64 (__fastcall *)(IOleClassInfo *, wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (__cdecl*)(HSTRING__ *),&WindowsDeleteString,wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t> > > *))lpVtbl[1].Release)(
         oleClassInfo.m_ptr,
         &displayNameStringOrResourceReference);
  if ( v7 >= 0 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(displayNameStringOrResourceReference.m_ptr, 0);
    v9 = ResolveStringOrResourceReference(0, 0, StringRawBuffer, 0x2Au, userType);
    v7 = v9;
    if ( v9 >= 0 )
      v7 = 0;
    else
      wil::details::in1diag3::Return_Hr(retaddr, 0x6A5u, "com\\ole32\\ole232\\stdimpl\\icon.cpp", v9);
  }
  wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&displayNameStringOrResourceReference);
LABEL_26:
  wil::com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>::~com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>((wil::com_ptr_t<IProxyServerIdentity,wil::err_returncode_policy> *)&oleClassInfo);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18009b6c8  mov     [rsp-8+arg_10], rbx
0x18009b6cd  mov     [rsp-8+arg_18], rsi
0x18009b6d2  push    rbp
0x18009b6d3  push    rdi
0x18009b6d4  push    r14
0x18009b6d6  lea     rbp, [rsp-0C0h]
0x18009b6de  sub     rsp, 1C0h
0x18009b6e5  mov     rax, cs:__security_cookie
0x18009b6ec  xor     rax, rsp
0x18009b6ef  mov     [rbp+0D0h+var_20], rax
0x18009b6f6  and     [rsp+1D0h+oleClassInfo.m_ptr], 0
0x18009b6fc  lea     r9, [rsp+1D0h+oleClassInfo]; ppv
0x18009b701  mov     rsi, userType
0x18009b704  lea     r8, _GUID_e942fe11_d674_da46_8c4f_c9568fc9d593; riid
0x18009b70b  xor     edx, edx; pComCatalog
0x18009b70d  mov     rdi, clsid
0x18009b710  call    ?GetClassInfoWithInprocOrLocalServer@@YAJAEBU_GUID@@PEAUIComCatalogSCM@@0PEAPEAX@Z; GetClassInfoWithInprocOrLocalServer(_GUID const &,IComCatalogSCM *,_GUID const &,void * *)
0x18009b715  test    eax, eax
0x18009b717  js      loc_18009B79D
0x18009b71d  mov     clsid, [rsp+1D0h+oleClassInfo.m_ptr]
0x18009b722  lea     userType, [rsp+1D0h+displayNameStringOrResourceReference]
0x18009b727  mov     rax, [clsid]
0x18009b72a  and     [rsp+1D0h+displayNameStringOrResourceReference.m_ptr], 0
0x18009b730  mov     rax, [rax+28h]
0x18009b734  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b739  mov     ebx, eax
0x18009b73b  test    eax, eax
0x18009b73d  js      short loc_18009B78E
0x18009b73f  mov     clsid, [rsp+1D0h+displayNameStringOrResourceReference.m_ptr]; string
0x18009b744  xor     edx, edx; length
0x18009b746  call    cs:__imp_WindowsGetStringRawBuffer
0x18009b74d  nop     dword ptr [rax+rax+00h]
0x18009b752  mov     r9d, 2Ah ; '*'; bufferSize
0x18009b758  mov     [rsp+1D0h+buffer], rsi; buffer
0x18009b75d  mov     r8, rax; stringOrResourceReference
0x18009b760  xor     edx, edx; resourceContext
0x18009b762  xor     ecx, ecx; providedResourceManager
0x18009b764  call    ?ResolveStringOrResourceReference@@YAJPEAUIMrtResourceManager@@PEAUIResourceContext@@PEBG_KPEAG@Z; ResolveStringOrResourceReference(IMrtResourceManager *,IResourceContext *,ushort const *,unsigned __int64,ushort *)
0x18009b769  mov     ebx, eax
0x18009b76b  test    eax, eax
0x18009b76d  jns     short loc_18009B78C
0x18009b76f  mov     clsid, [rbp+0D8h]; callerReturnAddress
0x18009b776  lea     r8, aComOle32Ole232_6; "com\\ole32\\ole232\\stdimpl\\icon.cpp"
0x18009b77d  mov     r9d, eax; hr
0x18009b780  mov     edx, 6A5h; lineNumber
0x18009b785  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009b78a  jmp     short loc_18009B78E
0x18009b78c  xor     ebx, ebx
0x18009b78e  lea     clsid, [rsp+1D0h+displayNameStringOrResourceReference]; this
0x18009b793  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18009b798  jmp     loc_18009B947
0x18009b79d  and     [rsp+1D0h+openedKey.m_ptr], 0
0x18009b7a3  lea     r8, [rsp+1D0h+openedKey]; phkResult
0x18009b7a8  mov     edx, 2000000h; samDesired
0x18009b7ad  xor     ecx, ecx; pszSubKey
0x18009b7af  call    OpenClassesRootKeyExW
0x18009b7b4  test    eax, eax
0x18009b7b6  jz      short loc_18009B7C5
0x18009b7b8  mov     r9d, eax
0x18009b7bb  mov     edx, 6AEh
0x18009b7c0  jmp     loc_18009B928
0x18009b7c5  mov     r14, [rsp+1D0h+openedKey.m_ptr]
0x18009b7ca  lea     clsid, [rsp+1D0h+clsidString]; this
0x18009b7cf  mov     userType, rdi; guid
0x18009b7d2  call    ??0GuidString@@QEAA@AEBU_GUID@@@Z; GuidString::GuidString(_GUID const &)
0x18009b7d7  mov     r10d, 80h
0x18009b7dd  lea     r8, aClsid_0; "CLSID\\"
0x18009b7e4  mov     edx, r10d; cchDest
0x18009b7e7  lea     clsid, [rbp+0D0h+szKey]; pszDest
0x18009b7eb  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18009b7f0  mov     ebx, eax
0x18009b7f2  test    eax, eax
0x18009b7f4  jns     short loc_18009B816
0x18009b7f6  mov     edx, 6B5h; lineNumber
0x18009b7fb  mov     clsid, [rbp+0D8h]; callerReturnAddress
0x18009b802  lea     r8, aComOle32Ole232_6; "com\\ole32\\ole232\\stdimpl\\icon.cpp"
0x18009b809  mov     r9d, eax; hr
0x18009b80c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009b811  jmp     loc_18009B93D
0x18009b816  lea     r8, [rsp+1D0h+clsidString]; pszSrc
0x18009b81b  mov     userType, r10; cchDest
0x18009b81e  lea     clsid, [rbp+0D0h+szKey]; pszDest
0x18009b822  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18009b827  mov     ebx, eax
0x18009b829  test    eax, eax
0x18009b82b  jns     short loc_18009B834
0x18009b82d  mov     edx, 6B6h
0x18009b832  jmp     short loc_18009B7FB
0x18009b834  lea     r9, [rsp+1D0h+valueSize]; lpdwSize
0x18009b839  mov     [rsp+1D0h+valueSize], 54h ; 'T'
0x18009b841  mov     r8, rsi; lpValue
0x18009b844  lea     userType, [rbp+0D0h+szKey]; lpSubKey
0x18009b848  mov     clsid, r14; hKey
0x18009b84b  call    wRegQueryValue
0x18009b850  mov     ebx, eax
0x18009b852  test    eax, eax
0x18009b854  jnz     short loc_18009B867
0x18009b856  lea     clsid, [rsp+1D0h+openedKey]; this
0x18009b85b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18009b860  xor     ebx, ebx
0x18009b862  jmp     loc_18009B947
0x18009b867  mov     clsid, rdi; rclsid
0x18009b86a  call    cs:__imp_CoIsOle1Class
0x18009b871  nop     dword ptr [rax+rax+00h]
0x18009b876  test    eax, eax
0x18009b878  jz      loc_18009B920
0x18009b87e  and     [rsp+1D0h+progId.m_ptr], 0
0x18009b884  lea     clsid, [rsp+1D0h+progId]; this
0x18009b889  xor     edx, edx; ptr
0x18009b88b  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18009b890  lea     userType, [rsp+1D0h+progId]; lplpszProgID
0x18009b895  mov     clsid, rdi; clsid
0x18009b898  call    cs:__imp_ProgIDFromCLSID
0x18009b89f  nop     dword ptr [rax+rax+00h]
0x18009b8a4  mov     ebx, eax
0x18009b8a6  test    eax, eax
0x18009b8a8  jns     short loc_18009B8D1
0x18009b8aa  mov     clsid, [rbp+0D8h]; callerReturnAddress
0x18009b8b1  lea     r8, aComOle32Ole232_6; "com\\ole32\\ole232\\stdimpl\\icon.cpp"
0x18009b8b8  mov     r9d, eax; hr
0x18009b8bb  mov     edx, 6C5h; lineNumber
0x18009b8c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009b8c5  lea     clsid, [rsp+1D0h+progId]; this
0x18009b8ca  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18009b8cf  jmp     short loc_18009B93D
0x18009b8d1  mov     userType, [rsp+1D0h+progId.m_ptr]; lpSubKey
0x18009b8d6  lea     r9, [rsp+1D0h+valueSize]; lpdwSize
0x18009b8db  mov     r8, rsi; lpValue
0x18009b8de  mov     [rsp+1D0h+valueSize], 54h ; 'T'
0x18009b8e6  mov     clsid, r14; hKey
0x18009b8e9  call    wRegQueryValue
0x18009b8ee  test    eax, eax
0x18009b8f0  jz      short loc_18009B911
0x18009b8f2  mov     clsid, [rbp+0D8h]; callerReturnAddress
0x18009b8f9  lea     r8, aComOle32Ole232_6; "com\\ole32\\ole232\\stdimpl\\icon.cpp"
0x18009b900  mov     r9d, eax; err
0x18009b903  mov     edx, 6C8h; lineNumber
0x18009b908  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18009b90d  mov     ebx, eax
0x18009b90f  jmp     short loc_18009B8C5
0x18009b911  lea     clsid, [rsp+1D0h+progId]; this
0x18009b916  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18009b91b  jmp     loc_18009B856
0x18009b920  mov     r9d, ebx; err
0x18009b923  mov     edx, 6CDh; lineNumber
0x18009b928  mov     clsid, [rbp+0D8h]; callerReturnAddress
0x18009b92f  lea     r8, aComOle32Ole232_6; "com\\ole32\\ole232\\stdimpl\\icon.cpp"
0x18009b936  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18009b93b  mov     ebx, eax
0x18009b93d  lea     clsid, [rsp+1D0h+openedKey]; this
0x18009b942  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18009b947  lea     clsid, [rsp+1D0h+oleClassInfo]; this
0x18009b94c  call    ??1?$com_ptr_t@UICallFrameEvents@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>::~com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>(void)
0x18009b951  mov     eax, ebx
0x18009b953  mov     clsid, [rbp+0D0h+var_20]
0x18009b95a  xor     clsid, rsp; StackCookie
0x18009b95d  call    __security_check_cookie
0x18009b962  lea     r11, [rsp+1D0h+var_10]
0x18009b96a  mov     rbx, [r11+30h]
0x18009b96e  mov     rsi, [r11+38h]
0x18009b972  mov     rsp, r11
0x18009b975  pop     r14
0x18009b977  pop     rdi
0x18009b978  pop     rbp
0x18009b979  retn
```
