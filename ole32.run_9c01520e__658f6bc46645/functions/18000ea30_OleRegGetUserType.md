# OleRegGetUserType

- ea: `0x18000ea30`
- end: `0x18000ee88`
- name: `OleRegGetUserType`
- size: `1112`
- prototype: `HRESULT __stdcall(const IID *const clsid, DWORD dwFormOfType, LPOLESTR *pszUserType)`
- caller_count: `6`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180077928`
- `0x18007ed20`
- `0x180098360`
- `0x1800a4640`
- `0x1800a758c`
- `0x1800aa690`

## callees

- `0x18000e860`
- `0x18000ea30`
- `0x18000f358`
- `0x180010fac`
- `0x18001217c`
- `0x18002a618`
- `0x18002fcd8`
- `0x180033bb0`
- `0x18003a700`
- `0x180046460`
- `0x180047484`
- `0x18009a630`
- `0x18009a6a8`
- `0x1800d8010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000eca4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ecec`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000eca4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ecec`
- `api-ms-win-core-registry-l1-1-0!RegLoadMUIStringW` at `0x18000ed24`
- `api-ms-win-core-registry-l1-1-0!RegLoadMUIStringW` at `0x18000edaf`
- `api-ms-win-core-registry-l1-1-0!RegLoadMUIStringW` at `0x18000ed24`
- `api-ms-win-core-registry-l1-1-0!RegLoadMUIStringW` at `0x18000edaf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ee0b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ee26`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ee41`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ee0b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ee26`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ee41`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ed7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ede8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ed7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ede8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000eb6d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000eb6d`
- `api-ms-win-core-com-private-l1-3-1!InternalRegOpenClassKey` at `0x18000ec3a`
- `api-ms-win-core-com-private-l1-3-1!InternalRegOpenClassKey` at `0x18000ec3a`

## string_xrefs

- `0x18000eaf8`: `com\ole32\ole232\stdimpl\olereg.cpp`
- `0x18000eba1`: `com\ole32\ole232\stdimpl\olereg.cpp`
- `0x18000ec05`: `com\ole32\ole232\stdimpl\olereg.cpp`
- `0x18000ec53`: `com\ole32\ole232\stdimpl\olereg.cpp`

## pseudocode

```c
HRESULT __stdcall OleRegGetUserType(const IID *const clsid, DWORD dwFormOfType, LPOLESTR *pszUserType)
{
  HRESULT String; // ebx
  DWORD v7; // ebx
  DWORD v8; // ebx
  struct IUnknownVtbl *v9; // rax
  HRESULT v10; // eax
  unsigned int v11; // edx
  struct IUnknownVtbl *lpVtbl; // rax
  struct IUnknownVtbl *v13; // rax
  const wchar_t *StringRawBuffer; // rax
  HRESULT v15; // eax
  wchar_t *m_ptr; // rax
  OLECHAR *v17; // rax
  HRESULT v18; // eax
  HRESULT v19; // esi
  OLECHAR *v20; // rax
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (__cdecl*)(void *),&CoTaskMemFree,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > > allocatedDisplayNameString; // [rsp+40h] [rbp-C0h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (__cdecl*)(HSTRING__ *),&WindowsDeleteString,wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t> > > displayNameStringOrResourceReference; // [rsp+48h] [rbp-B8h] BYREF
  HKEY__ *hkeyClsid; // [rsp+50h] [rbp-B0h] BYREF
  wil::com_ptr_t<IOleClassInfo,wil::err_returncode_policy> oleClassInfo; // [rsp+58h] [rbp-A8h] BYREF
  HKEY__ *hkeyAux; // [rsp+60h] [rbp-A0h] BYREF
  HKEY__ *hkeyAuxWithIndex; // [rsp+68h] [rbp-98h] BYREF
  const wchar_t *displayNameString; // [rsp+70h] [rbp-90h] BYREF
  wchar_t szIndex[20]; // [rsp+78h] [rbp-88h] BYREF
  wchar_t szLocalized[512]; // [rsp+A0h] [rbp-60h] BYREF
  void *retaddr; // [rsp+4D8h] [rbp+3D8h]

  allocatedDisplayNameString.m_ptr = 0;
  hkeyClsid = 0;
  hkeyAux = 0;
  hkeyAuxWithIndex = 0;
  memset_0(szLocalized, 0, sizeof(szLocalized));
  if ( !pszUserType )
    return -2147024809;
  *pszUserType = 0;
  oleClassInfo.m_ptr = 0;
  if ( GetClassInfoWithInprocOrLocalServer(
         clsid,
         0,
         &GUID_e942fe11_d674_da46_8c4f_c9568fc9d593,
         (void **)&oleClassInfo.m_ptr) >= 0 )
  {
    v7 = dwFormOfType - 1;
    if ( v7 )
    {
      v8 = v7 - 1;
      if ( !v8 )
      {
        lpVtbl = oleClassInfo.m_ptr->lpVtbl;
        displayNameStringOrResourceReference.m_ptr = 0;
        v10 = ((__int64 (__fastcall *)(IOleClassInfo *, wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (__cdecl*)(HSTRING__ *),&WindowsDeleteString,wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t> > > *))lpVtbl[2].QueryInterface)(
                oleClassInfo.m_ptr,
                &displayNameStringOrResourceReference);
        String = v10;
        if ( v10 < 0 )
        {
          v11 = 323;
          goto LABEL_9;
        }
LABEL_14:
        allocatedDisplayNameString.m_ptr = 0;
        displayNameString = 0;
        StringRawBuffer = WindowsGetStringRawBuffer(displayNameStringOrResourceReference.m_ptr, 0);
        v15 = ResolveStringOrResourceReference(0, 0, StringRawBuffer, &allocatedDisplayNameString, &displayNameString);
        String = v15;
        if ( v15 >= 0 )
        {
          m_ptr = allocatedDisplayNameString.m_ptr;
          if ( allocatedDisplayNameString.m_ptr )
          {
            allocatedDisplayNameString.m_ptr = 0;
            *pszUserType = m_ptr;
          }
          else
          {
            v17 = UtDupString(displayNameString);
            *pszUserType = v17;
            if ( !v17 )
            {
              wil::details::in1diag3::Return_Hr(retaddr, 0x15Bu, "com\\ole32\\ole232\\stdimpl\\olereg.cpp", -2147024882);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&allocatedDisplayNameString);
              String = -2147024882;
              goto LABEL_19;
            }
          }
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&allocatedDisplayNameString);
          String = 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(retaddr, 0x151u, "com\\ole32\\ole232\\stdimpl\\olereg.cpp", v15);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&allocatedDisplayNameString);
        }
LABEL_19:
        wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&displayNameStringOrResourceReference);
LABEL_24:
        wil::com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>::~com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>((wil::com_ptr_t<IProxyServerIdentity,wil::err_returncode_policy> *)&oleClassInfo);
        return String;
      }
      if ( v8 == 1 )
      {
        v9 = oleClassInfo.m_ptr->lpVtbl;
        displayNameStringOrResourceReference.m_ptr = 0;
        v10 = ((__int64 (__fastcall *)(IOleClassInfo *, wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (__cdecl*)(HSTRING__ *),&WindowsDeleteString,wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t> > > *))v9[2].AddRef)(
                oleClassInfo.m_ptr,
                &displayNameStringOrResourceReference);
        String = v10;
        if ( v10 < 0 )
        {
          v11 = 326;
LABEL_9:
          wil::details::in1diag3::Return_Hr(retaddr, v11, "com\\ole32\\ole232\\stdimpl\\olereg.cpp", v10);
          goto LABEL_19;
        }
        goto LABEL_14;
      }
    }
    v13 = oleClassInfo.m_ptr->lpVtbl;
    displayNameStringOrResourceReference.m_ptr = 0;
    v10 = ((__int64 (__fastcall *)(IOleClassInfo *, wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (__cdecl*)(HSTRING__ *),&WindowsDeleteString,wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t> > > *))v13[1].Release)(
            oleClassInfo.m_ptr,
            &displayNameStringOrResourceReference);
    String = v10;
    if ( v10 < 0 )
    {
      v11 = 330;
      goto LABEL_9;
    }
    goto LABEL_14;
  }
  v18 = InternalRegOpenClassKey(clsid, 131097, &hkeyClsid);
  v19 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, 0x160u, "com\\ole32\\ole232\\stdimpl\\olereg.cpp", v18);
    String = v19;
    goto LABEL_24;
  }
  if ( dwFormOfType == 1 )
    goto $trymain;
  if ( RegOpenKeyExW(hkeyClsid, Com::Catalog::Constants::AuxUserType, 0, 0x20019u, &hkeyAux) )
    goto $trymain;
  StringCchPrintfW(szIndex, 0x14u, L"%d", dwFormOfType);
  if ( RegOpenKeyExW(hkeyAux, szIndex, 0, 0x20019u, &hkeyAuxWithIndex) )
    goto $trymain;
  if ( RegLoadMUIStringW(hkeyAuxWithIndex, L"LocalizedString", szLocalized, 0x400u, 0, 1u, 0) )
  {
    if ( OleRegGetString_0(hkeyAux, dwFormOfType, &allocatedDisplayNameString.m_ptr) >= 0 )
    {
      if ( *allocatedDisplayNameString.m_ptr )
      {
        *pszUserType = allocatedDisplayNameString.m_ptr;
        goto LABEL_39;
      }
      CoTaskMemFree(allocatedDisplayNameString.m_ptr);
      allocatedDisplayNameString.m_ptr = 0;
    }
$trymain:
    if ( !RegLoadMUIStringW(hkeyClsid, L"LocalizedString", szLocalized, 0x400u, 0, 1u, 0) )
      goto LABEL_29;
    String = OleRegGetString(hkeyClsid, 0, &allocatedDisplayNameString.m_ptr);
    if ( String )
      goto $errRtn_3;
    if ( !*allocatedDisplayNameString.m_ptr )
    {
      CoTaskMemFree(allocatedDisplayNameString.m_ptr);
      String = -2147221165;
      goto $errRtn_3;
    }
    *pszUserType = allocatedDisplayNameString.m_ptr;
LABEL_39:
    String = 0;
    goto $errRtn_3;
  }
LABEL_29:
  v20 = UtDupString(szLocalized);
  *pszUserType = v20;
  String = v20 == 0 ? 0x8007000E : 0;
$errRtn_3:
  if ( hkeyClsid )
  {
    RegCloseKey(hkeyClsid);
    hkeyClsid = 0;
  }
  if ( hkeyAux )
  {
    RegCloseKey(hkeyAux);
    hkeyAux = 0;
  }
  if ( hkeyAuxWithIndex )
  {
    RegCloseKey(hkeyAuxWithIndex);
    hkeyAuxWithIndex = 0;
  }
  if ( oleClassInfo.m_ptr )
    ((void (__fastcall *)(IOleClassInfo *))oleClassInfo.m_ptr->lpVtbl->Release)(oleClassInfo.m_ptr);
  return String;
}

```

## disassembly

```asm
0x18000ea30  push    rbp
0x18000ea32  push    rbx
0x18000ea33  push    rsi
0x18000ea34  push    rdi
0x18000ea35  push    r14
0x18000ea37  lea     rbp, [rsp-3B0h]
0x18000ea3f  sub     rsp, 4B0h
0x18000ea46  mov     rax, cs:__security_cookie
0x18000ea4d  xor     rax, rsp
0x18000ea50  mov     [rbp+3D0h+var_30], rax
0x18000ea57  xor     r14d, r14d
0x18000ea5a  mov     rdi, ppszUserType
0x18000ea5d  mov     ebx, dwFormOfType
0x18000ea5f  mov     [rsp+4D0h+allocatedDisplayNameString.m_ptr], r14
0x18000ea64  mov     rsi, clsid
0x18000ea67  mov     [rsp+4D0h+hkeyClsid], r14
0x18000ea6c  xor     dwFormOfType, dwFormOfType; Val
0x18000ea6e  mov     [rsp+4D0h+hkeyAux], r14
0x18000ea73  mov     r8d, 400h; Size
0x18000ea79  mov     [rsp+4D0h+hkeyAuxWithIndex], r14
0x18000ea7e  lea     clsid, [rbp+3D0h+szLocalized]; void *
0x18000ea82  call    memset_0
0x18000ea87  test    rdi, rdi
0x18000ea8a  jnz     short loc_18000EA96
0x18000ea8c  mov     ebx, 80070057h
0x18000ea91  jmp     loc_18000EE68
0x18000ea96  lea     r9, [rsp+4D0h+oleClassInfo]; ppv
0x18000ea9b  mov     [rdi], r14
0x18000ea9e  lea     ppszUserType, _GUID_e942fe11_d674_da46_8c4f_c9568fc9d593; riid
0x18000eaa5  mov     [rsp+4D0h+oleClassInfo.m_ptr], r14
0x18000eaaa  xor     dwFormOfType, dwFormOfType; pComCatalog
0x18000eaac  mov     clsid, rsi; clsid
0x18000eaaf  call    ?GetClassInfoWithInprocOrLocalServer@@YAJAEBU_GUID@@PEAUIComCatalogSCM@@0PEAPEAX@Z; GetClassInfoWithInprocOrLocalServer(_GUID const &,IComCatalogSCM *,_GUID const &,void * *)
0x18000eab4  test    eax, eax
0x18000eab6  js      loc_18000EC2D
0x18000eabc  sub     ebx, 1
0x18000eabf  jz      short loc_18000EB34
0x18000eac1  sub     ebx, 1
0x18000eac4  jz      short loc_18000EB0C
0x18000eac6  cmp     ebx, 1
0x18000eac9  jnz     short loc_18000EB34
0x18000eacb  mov     clsid, [rsp+4D0h+oleClassInfo.m_ptr]
0x18000ead0  lea     rdx, [rsp+4D0h+displayNameStringOrResourceReference]
0x18000ead5  mov     rax, [clsid]
0x18000ead8  mov     [rsp+4D0h+displayNameStringOrResourceReference.m_ptr], r14
0x18000eadd  mov     rax, [rax+38h]
0x18000eae1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eae6  mov     ebx, eax
0x18000eae8  test    eax, eax
0x18000eaea  jns     short loc_18000EB5C
0x18000eaec  mov     dwFormOfType, 146h; lineNumber
0x18000eaf1  mov     clsid, [rbp+3D8h]; callerReturnAddress
0x18000eaf8  lea     ppszUserType, aComOle32Ole232_5; "com\\ole32\\ole232\\stdimpl\\olereg.cpp"
0x18000eaff  mov     r9d, eax; hr
0x18000eb02  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000eb07  jmp     loc_18000EBE0
0x18000eb0c  mov     clsid, [rsp+4D0h+oleClassInfo.m_ptr]
0x18000eb11  lea     rdx, [rsp+4D0h+displayNameStringOrResourceReference]
0x18000eb16  mov     rax, [clsid]
0x18000eb19  mov     [rsp+4D0h+displayNameStringOrResourceReference.m_ptr], r14
0x18000eb1e  mov     rax, [rax+30h]
0x18000eb22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb27  mov     ebx, eax
0x18000eb29  test    eax, eax
0x18000eb2b  jns     short loc_18000EB5C
0x18000eb2d  mov     dwFormOfType, 143h
0x18000eb32  jmp     short loc_18000EAF1
0x18000eb34  mov     clsid, [rsp+4D0h+oleClassInfo.m_ptr]
0x18000eb39  lea     rdx, [rsp+4D0h+displayNameStringOrResourceReference]
0x18000eb3e  mov     rax, [clsid]
0x18000eb41  mov     [rsp+4D0h+displayNameStringOrResourceReference.m_ptr], r14
0x18000eb46  mov     rax, [rax+28h]
0x18000eb4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb4f  mov     ebx, eax
0x18000eb51  test    eax, eax
0x18000eb53  jns     short loc_18000EB5C
0x18000eb55  mov     dwFormOfType, 14Ah
0x18000eb5a  jmp     short loc_18000EAF1
0x18000eb5c  mov     clsid, [rsp+4D0h+displayNameStringOrResourceReference.m_ptr]; string
0x18000eb61  xor     dwFormOfType, dwFormOfType; length
0x18000eb63  mov     [rsp+4D0h+allocatedDisplayNameString.m_ptr], r14
0x18000eb68  mov     [rsp+4D0h+displayNameString], r14
0x18000eb6d  call    cs:__imp_WindowsGetStringRawBuffer
0x18000eb74  nop     dword ptr [rax+rax+00h]
0x18000eb79  lea     clsid, [rsp+4D0h+displayNameString]
0x18000eb7e  xor     dwFormOfType, dwFormOfType; resourceContext
0x18000eb80  mov     [rsp+4D0h+result], clsid; result
0x18000eb85  lea     r9, [rsp+4D0h+allocatedDisplayNameString]; allocatedResult
0x18000eb8a  xor     ecx, ecx; providedResourceManager
0x18000eb8c  mov     ppszUserType, rax; stringOrResourceReference
0x18000eb8f  call    ?ResolveStringOrResourceReference@@YAJPEAUIMrtResourceManager@@PEAUIResourceContext@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEAPEBG@Z; ResolveStringOrResourceReference(IMrtResourceManager *,IResourceContext *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const * *)
0x18000eb94  mov     ebx, eax
0x18000eb96  test    eax, eax
0x18000eb98  jns     short loc_18000EBC1
0x18000eb9a  mov     clsid, [rbp+3D8h]; callerReturnAddress
0x18000eba1  lea     ppszUserType, aComOle32Ole232_5; "com\\ole32\\ole232\\stdimpl\\olereg.cpp"
0x18000eba8  mov     r9d, eax; hr
0x18000ebab  mov     dwFormOfType, 151h; lineNumber
0x18000ebb0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ebb5  lea     clsid, [rsp+4D0h+allocatedDisplayNameString]; this
0x18000ebba  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000ebbf  jmp     short loc_18000EBE0
0x18000ebc1  mov     rax, [rsp+4D0h+allocatedDisplayNameString.m_ptr]
0x18000ebc6  test    rax, rax
0x18000ebc9  jz      short loc_18000EBEC
0x18000ebcb  mov     [rsp+4D0h+allocatedDisplayNameString.m_ptr], r14
0x18000ebd0  mov     [rdi], rax
0x18000ebd3  lea     clsid, [rsp+4D0h+allocatedDisplayNameString]; this
0x18000ebd8  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000ebdd  mov     ebx, r14d
0x18000ebe0  lea     clsid, [rsp+4D0h+displayNameStringOrResourceReference]; this
0x18000ebe5  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18000ebea  jmp     short loc_18000EC69
0x18000ebec  mov     clsid, [rsp+4D0h+displayNameString]; lpszIn
0x18000ebf1  call    ?UtDupString@@YAPEAGPEBG@Z; UtDupString(ushort const *)
0x18000ebf6  mov     [rdi], rax
0x18000ebf9  test    rax, rax
0x18000ebfc  jnz     short loc_18000EBD3
0x18000ebfe  mov     clsid, [rbp+3D8h]; callerReturnAddress
0x18000ec05  lea     ppszUserType, aComOle32Ole232_5; "com\\ole32\\ole232\\stdimpl\\olereg.cpp"
0x18000ec0c  mov     r9d, 8007000Eh; hr
0x18000ec12  mov     dwFormOfType, 15Bh; lineNumber
0x18000ec17  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ec1c  lea     clsid, [rsp+4D0h+allocatedDisplayNameString]; this
0x18000ec21  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000ec26  mov     ebx, 8007000Eh
0x18000ec2b  jmp     short loc_18000EBE0
0x18000ec2d  lea     ppszUserType, [rsp+4D0h+hkeyClsid]
0x18000ec32  mov     dwFormOfType, 20019h
0x18000ec37  mov     clsid, rsi
0x18000ec3a  call    cs:__imp_InternalRegOpenClassKey
0x18000ec41  nop     dword ptr [rax+rax+00h]
0x18000ec46  mov     esi, eax
0x18000ec48  test    eax, eax
0x18000ec4a  jns     short loc_18000EC78
0x18000ec4c  mov     clsid, [rbp+3D8h]; callerReturnAddress
0x18000ec53  lea     ppszUserType, aComOle32Ole232_5; "com\\ole32\\ole232\\stdimpl\\olereg.cpp"
0x18000ec5a  mov     r9d, eax; hr
0x18000ec5d  mov     dwFormOfType, 160h; lineNumber
0x18000ec62  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ec67  mov     ebx, esi
0x18000ec69  lea     clsid, [rsp+4D0h+oleClassInfo]; this
0x18000ec6e  call    ??1?$com_ptr_t@UICallFrameEvents@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>::~com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>(void)
0x18000ec73  jmp     loc_18000EE68
0x18000ec78  mov     esi, 1
0x18000ec7d  cmp     ebx, esi
0x18000ec7f  jz      $trymain
0x18000ec85  mov     clsid, [rsp+4D0h+hkeyClsid]; hKey
0x18000ec8a  lea     rax, [rsp+4D0h+hkeyAux]
0x18000ec8f  mov     r9d, 20019h; samDesired
0x18000ec95  mov     [rsp+4D0h+result], rax; phkResult
0x18000ec9a  xor     r8d, r8d; ulOptions
0x18000ec9d  lea     rdx, ?AuxUserType@Constants@Catalog@Com@@3QBGB; lpSubKey
0x18000eca4  call    cs:__imp_RegOpenKeyExW
0x18000ecab  nop     dword ptr [rax+rax+00h]
0x18000ecb0  test    eax, eax
0x18000ecb2  jnz     $trymain
0x18000ecb8  mov     r9d, ebx
0x18000ecbb  lea     ppszUserType, aD; "%d"
0x18000ecc2  lea     dwFormOfType, [rsi+13h]; cchDest
0x18000ecc5  lea     clsid, [rsp+4D0h+szIndex]; pszDest
0x18000ecca  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000eccf  mov     clsid, [rsp+4D0h+hkeyAux]; hKey
0x18000ecd4  lea     rax, [rsp+4D0h+hkeyAuxWithIndex]
0x18000ecd9  mov     r9d, 20019h; samDesired
0x18000ecdf  mov     [rsp+4D0h+result], rax; phkResult
0x18000ece4  xor     r8d, r8d; ulOptions
0x18000ece7  lea     rdx, [rsp+4D0h+szIndex]; lpSubKey
0x18000ecec  call    cs:__imp_RegOpenKeyExW
0x18000ecf3  nop     dword ptr [rax+rax+00h]
0x18000ecf8  test    eax, eax
0x18000ecfa  jnz     $trymain
0x18000ed00  mov     clsid, [rsp+4D0h+hkeyAuxWithIndex]; hKey
0x18000ed05  lea     ppszUserType, [rbp+3D0h+szLocalized]; pszOutBuf
0x18000ed09  mov     [rsp+4D0h+pszDirectory], r14; pszDirectory
0x18000ed0e  lea     rdx, aLocalizedstrin; "LocalizedString"
0x18000ed15  mov     [rsp+4D0h+Flags], esi; Flags
0x18000ed19  mov     r9d, 400h; cbOutBuf
0x18000ed1f  mov     [rsp+4D0h+result], r14; pcbData
0x18000ed24  call    cs:__imp_RegLoadMUIStringW
0x18000ed2b  nop     dword ptr [rax+rax+00h]
0x18000ed30  test    eax, eax
0x18000ed32  jnz     short loc_18000ED52
0x18000ed34  lea     clsid, [rbp+3D0h+szLocalized]; lpszIn
0x18000ed38  call    ?UtDupString@@YAPEAGPEBG@Z; UtDupString(ushort const *)
0x18000ed3d  mov     [rdi], rax
0x18000ed40  neg     rax
0x18000ed43  sbb     ebx, ebx
0x18000ed45  not     ebx
0x18000ed47  and     ebx, 8007000Eh
0x18000ed4d  jmp     $errRtn_3
0x18000ed52  mov     clsid, [rsp+4D0h+hkeyAux]; hkey
0x18000ed57  lea     ppszUserType, [rsp+4D0h+allocatedDisplayNameString]; ppszValue
0x18000ed5c  mov     dwFormOfType, ebx; dwKey
0x18000ed5e  call    OleRegGetString_0
0x18000ed63  test    eax, eax
0x18000ed65  js      short $trymain
0x18000ed67  mov     clsid, [rsp+4D0h+allocatedDisplayNameString.m_ptr]; pv
0x18000ed6c  cmp     [clsid], r14w
0x18000ed70  jz      short loc_18000ED7A
0x18000ed72  mov     [rdi], clsid
0x18000ed75  jmp     loc_18000EDFE
0x18000ed7a  call    cs:__imp_CoTaskMemFree
0x18000ed81  nop     dword ptr [rax+rax+00h]
0x18000ed86  mov     [rsp+4D0h+allocatedDisplayNameString.m_ptr], r14
0x18000ed8b  mov     clsid, [rsp+4D0h+hkeyClsid]; hKey
0x18000ed90  lea     ppszUserType, [rbp+3D0h+szLocalized]; pszOutBuf
0x18000ed94  mov     [rsp+4D0h+pszDirectory], r14; pszDirectory
0x18000ed99  lea     rdx, aLocalizedstrin; "LocalizedString"
0x18000eda0  mov     [rsp+4D0h+Flags], esi; Flags
0x18000eda4  mov     r9d, 400h; cbOutBuf
0x18000edaa  mov     [rsp+4D0h+result], r14; pcbData
0x18000edaf  call    cs:__imp_RegLoadMUIStringW
0x18000edb6  nop     dword ptr [rax+rax+00h]
0x18000edbb  test    eax, eax
0x18000edbd  jz      loc_18000ED34
0x18000edc3  mov     clsid, [rsp+4D0h+hkeyClsid]; hkey
0x18000edc8  lea     ppszUserType, [rsp+4D0h+allocatedDisplayNameString]; ppszValue
0x18000edcd  xor     dwFormOfType, dwFormOfType; szKey
0x18000edcf  call    OleRegGetString
0x18000edd4  mov     ebx, eax
0x18000edd6  test    eax, eax
0x18000edd8  jnz     short $errRtn_3
0x18000edda  mov     rax, [rsp+4D0h+allocatedDisplayNameString.m_ptr]
0x18000eddf  cmp     [rax], r14w
0x18000ede3  jnz     short loc_18000EDFB
0x18000ede5  mov     clsid, rax; pv
0x18000ede8  call    cs:__imp_CoTaskMemFree
0x18000edef  nop     dword ptr [rax+rax+00h]
0x18000edf4  mov     ebx, 80040153h
0x18000edf9  jmp     short $errRtn_3
0x18000edfb  mov     [rdi], rax
0x18000edfe  mov     ebx, r14d
0x18000ee01  mov     clsid, [rsp+4D0h+hkeyClsid]; hKey
0x18000ee06  test    clsid, clsid
0x18000ee09  jz      short loc_18000EE1C
0x18000ee0b  call    cs:__imp_RegCloseKey
0x18000ee12  nop     dword ptr [rax+rax+00h]
0x18000ee17  mov     [rsp+4D0h+hkeyClsid], r14
0x18000ee1c  mov     clsid, [rsp+4D0h+hkeyAux]; hKey
0x18000ee21  test    clsid, clsid
0x18000ee24  jz      short loc_18000EE37
0x18000ee26  call    cs:__imp_RegCloseKey
0x18000ee2d  nop     dword ptr [rax+rax+00h]
0x18000ee32  mov     [rsp+4D0h+hkeyAux], r14
0x18000ee37  mov     clsid, [rsp+4D0h+hkeyAuxWithIndex]; hKey
0x18000ee3c  test    clsid, clsid
0x18000ee3f  jz      short $safeRtn_0
0x18000ee41  call    cs:__imp_RegCloseKey
0x18000ee48  nop     dword ptr [rax+rax+00h]
0x18000ee4d  mov     [rsp+4D0h+hkeyAuxWithIndex], r14
0x18000ee52  mov     clsid, [rsp+4D0h+oleClassInfo.m_ptr]
0x18000ee57  test    clsid, clsid
0x18000ee5a  jz      short loc_18000EE68
0x18000ee5c  mov     rax, [clsid]
0x18000ee5f  mov     rax, [rax+10h]
0x18000ee63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee68  mov     eax, ebx
0x18000ee6a  mov     clsid, [rbp+3D0h+var_30]
0x18000ee71  xor     clsid, rsp; StackCookie
0x18000ee74  call    __security_check_cookie
0x18000ee79  add     rsp, 4B0h
0x18000ee80  pop     r14
0x18000ee82  pop     rdi
0x18000ee83  pop     rsi
0x18000ee84  pop     rbx
0x18000ee85  pop     rbp
0x18000ee86  retn
```
