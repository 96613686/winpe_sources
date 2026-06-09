# TryGetTypeInfoFromIID(_GUID const &,ITypeInfo * *,long *)

- ea: `0x180013d68`
- end: `0x180013f4c`
- name: `?TryGetTypeInfoFromIID@@YAJAEBU_GUID@@PEAPEAUITypeInfo@@PEAJ@Z`
- size: `484`
- prototype: `HRESULT __fastcall(const _GUID *iidIntercepted, ITypeInfo **pptypeinfo, HRESULT *reasonForNoTypeInfo)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180013414`

## callees

- `0x18001217c`
- `0x180013d68`
- `0x180013f54`
- `0x18002fcd8`
- `0x180033bb0`
- `0x1800c8f98`
- `0x1800d8010`

## import_xrefs

- `OLEAUT32!__imp_LoadTypeLibEx` at `0x180013edb`
- `OLEAUT32!__imp_LoadTypeLibEx` at `0x180013edb`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x180013db8`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x180013db8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013dee`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013dee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180013e30`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180013e30`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180013ec3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180013ec3`

## string_xrefs

- `0x180013e6b`: `com\ole32\com\txf\callframe\typeinfo.cpp`
- `0x180013e9c`: `com\ole32\com\txf\callframe\typeinfo.cpp`
- `0x180013f19`: `com\ole32\com\txf\callframe\typeinfo.cpp`

## pseudocode

```c
__int64 __fastcall TryGetTypeInfoFromIID(
        const _GUID *iidIntercepted,
        ITypeInfo **pptypeinfo,
        HRESULT *reasonForNoTypeInfo)
{
  HRESULT TypeInfoFromIIDViaRegistry; // eax
  unsigned int v7; // ebx
  int Instance; // eax
  struct IUnknownVtbl *lpVtbl; // rax
  const OLECHAR *StringRawBuffer; // rax
  int v12; // eax
  unsigned int v13; // edx
  _APTTYPE aptTypeIgnored; // [rsp+30h] [rbp-20h] BYREF
  wil::com_ptr_t<IPackagedComProxyStubCatalogInternal,wil::err_returncode_policy> packagedComCatalog; // [rsp+38h] [rbp-18h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (__cdecl*)(HSTRING__ *),&WindowsDeleteString,wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t> > > packagedTypeLibPath; // [rsp+40h] [rbp-10h] BYREF
  wil::com_ptr_t<ITypeLib,wil::err_returncode_policy> typeLib; // [rsp+48h] [rbp-8h] BYREF
  void *retaddr; // [rsp+68h] [rbp+18h]
  _APTTYPEQUALIFIER aptTypeQualifierIgnored; // [rsp+88h] [rbp+38h] BYREF

  TypeInfoFromIIDViaRegistry = TryGetTypeInfoFromIIDViaRegistry(iidIntercepted, pptypeinfo, reasonForNoTypeInfo);
  v7 = TypeInfoFromIIDViaRegistry;
  if ( TypeInfoFromIIDViaRegistry >= 0 )
  {
    if ( *pptypeinfo )
      return 0;
    if ( *reasonForNoTypeInfo >= 0 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    aptTypeIgnored = APTTYPE_STA;
    aptTypeQualifierIgnored = APTTYPEQUALIFIER_NONE;
    if ( CoGetApartmentType(&aptTypeIgnored, &aptTypeQualifierIgnored) < 0 )
      return 0;
    packagedComCatalog.m_ptr = 0;
    Instance = CoCreateInstance(
                 &GUID_00000346_0000_0000_c000_000000000046,
                 0,
                 1u,
                 &GUID_419c4e35_36bc_4780_845d_a05c51d9f770,
                 (LPVOID *)&packagedComCatalog.m_ptr);
    v7 = Instance;
    if ( Instance < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, 0x26Du, "com\\ole32\\com\\txf\\callframe\\typeinfo.cpp", Instance);
      if ( packagedComCatalog.m_ptr )
        ((void (__fastcall *)(IPackagedComProxyStubCatalogInternal *))packagedComCatalog.m_ptr->lpVtbl->Release)(packagedComCatalog.m_ptr);
      return v7;
    }
    lpVtbl = packagedComCatalog.m_ptr->lpVtbl;
    packagedTypeLibPath.m_ptr = 0;
    if ( ((unsigned int (__fastcall *)(IPackagedComProxyStubCatalogInternal *, const _GUID *, wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (__cdecl*)(HSTRING__ *),&WindowsDeleteString,wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t> > > *))lpVtbl[1].Release)(
           packagedComCatalog.m_ptr,
           iidIntercepted,
           &packagedTypeLibPath) == -2147319779 )
    {
      if ( packagedTypeLibPath.m_ptr )
        WindowsDeleteString(packagedTypeLibPath.m_ptr);
      if ( packagedComCatalog.m_ptr )
        ((void (__fastcall *)(IPackagedComProxyStubCatalogInternal *))packagedComCatalog.m_ptr->lpVtbl->Release)(packagedComCatalog.m_ptr);
      return 0;
    }
    typeLib.m_ptr = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(packagedTypeLibPath.m_ptr, 0);
    v12 = LoadTypeLibEx(StringRawBuffer, REGKIND_NONE, &typeLib.m_ptr);
    v7 = v12;
    if ( v12 >= 0 )
    {
      v12 = ((__int64 (__fastcall *)(ITypeLib *, const _GUID *, ITypeInfo **))typeLib.m_ptr->lpVtbl[2].QueryInterface)(
              typeLib.m_ptr,
              iidIntercepted,
              pptypeinfo);
      v7 = v12;
      if ( v12 >= 0 )
      {
        v7 = 0;
        goto LABEL_23;
      }
      v13 = 638;
    }
    else
    {
      v13 = 637;
    }
    wil::details::in1diag3::Return_Hr(retaddr, v13, "com\\ole32\\com\\txf\\callframe\\typeinfo.cpp", v12);
LABEL_23:
    wil::com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>::~com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>((wil::com_ptr_t<IProxyServerIdentity,wil::err_returncode_policy> *)&typeLib);
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&packagedTypeLibPath);
    wil::com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>::~com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>((wil::com_ptr_t<IProxyServerIdentity,wil::err_returncode_policy> *)&packagedComCatalog);
    return v7;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    0x25Cu,
    "com\\ole32\\com\\txf\\callframe\\typeinfo.cpp",
    TypeInfoFromIIDViaRegistry);
  return v7;
}

```

## disassembly

```asm
0x180013d68  mov     [rsp-18h+arg_0], rbx
0x180013d6d  mov     [rsp-18h+arg_8], rsi
0x180013d72  push    rbp
0x180013d73  push    rdi
0x180013d74  push    r14
0x180013d76  mov     rbp, rsp
0x180013d79  sub     rsp, 50h
0x180013d7d  mov     rdi, reasonForNoTypeInfo
0x180013d80  mov     rsi, pptypeinfo
0x180013d83  mov     r14, iidIntercepted
0x180013d86  call    ?TryGetTypeInfoFromIIDViaRegistry@@YAJAEBU_GUID@@PEAPEAUITypeInfo@@PEAJ@Z; TryGetTypeInfoFromIIDViaRegistry(_GUID const &,ITypeInfo * *,long *)
0x180013d8b  mov     ebx, eax
0x180013d8d  test    eax, eax
0x180013d8f  js      loc_180013E98
0x180013d95  cmp     qword ptr [rsi], 0
0x180013d99  jnz     loc_180013E51
0x180013d9f  cmp     dword ptr [rdi], 0
0x180013da2  jge     loc_180013EB2
0x180013da8  and     [rbp+aptTypeIgnored], 0
0x180013dac  lea     pptypeinfo, [rbp+aptTypeQualifierIgnored]; pAptQualifier
0x180013db0  and     [rbp+aptTypeQualifierIgnored], 0
0x180013db4  lea     iidIntercepted, [rbp+aptTypeIgnored]; pAptType
0x180013db8  call    cs:__imp_CoGetApartmentType
0x180013dbf  nop     dword ptr [rax+rax+00h]
0x180013dc4  test    eax, eax
0x180013dc6  js      loc_180013E51
0x180013dcc  and     [rbp+packagedComCatalog.m_ptr], 0
0x180013dd1  lea     rax, [rbp+packagedComCatalog]
0x180013dd5  xor     edx, edx; pUnkOuter
0x180013dd7  mov     [rsp+50h+ppv], rax; ppv
0x180013ddc  lea     r9, _GUID_419c4e35_36bc_4780_845d_a05c51d9f770; riid
0x180013de3  lea     iidIntercepted, _GUID_00000346_0000_0000_c000_000000000046; rclsid
0x180013dea  lea     r8d, [pptypeinfo+1]; dwClsContext
0x180013dee  call    cs:__imp_CoCreateInstance
0x180013df5  nop     dword ptr [rax+rax+00h]
0x180013dfa  mov     ebx, eax
0x180013dfc  test    eax, eax
0x180013dfe  js      short loc_180013E67
0x180013e00  mov     iidIntercepted, [rbp+packagedComCatalog.m_ptr]
0x180013e04  lea     reasonForNoTypeInfo, [rbp+packagedTypeLibPath]
0x180013e08  mov     pptypeinfo, r14
0x180013e0b  mov     rax, [iidIntercepted]
0x180013e0e  and     [rbp+packagedTypeLibPath.m_ptr], 0
0x180013e13  mov     rax, [rax+28h]
0x180013e17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e1c  mov     iidIntercepted, [rbp+packagedTypeLibPath.m_ptr]; string
0x180013e20  cmp     eax, 8002801Dh
0x180013e25  jnz     loc_180013EBC
0x180013e2b  test    iidIntercepted, iidIntercepted
0x180013e2e  jz      short loc_180013E3C
0x180013e30  call    cs:__imp_WindowsDeleteString
0x180013e37  nop     dword ptr [rax+rax+00h]
0x180013e3c  mov     iidIntercepted, [rbp+packagedComCatalog.m_ptr]
0x180013e40  test    iidIntercepted, iidIntercepted
0x180013e43  jz      short loc_180013E51
0x180013e45  mov     rax, [iidIntercepted]
0x180013e48  mov     rax, [rax+10h]
0x180013e4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e51  xor     eax, eax
0x180013e53  mov     rbx, [rsp+50h+arg_0]
0x180013e58  mov     rsi, [rsp+50h+arg_8]
0x180013e5d  add     rsp, 50h
0x180013e61  pop     r14
0x180013e63  pop     rdi
0x180013e64  pop     rbp
0x180013e65  retn
0x180013e67  mov     iidIntercepted, [rbp+18h]; callerReturnAddress
0x180013e6b  lea     reasonForNoTypeInfo, aComOle32ComTxf_3; "com\\ole32\\com\\txf\\callframe\\typein"...
0x180013e72  mov     r9d, ebx; hr
0x180013e75  mov     edx, 26Dh; lineNumber
0x180013e7a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013e7f  mov     iidIntercepted, [rbp+packagedComCatalog.m_ptr]
0x180013e83  test    iidIntercepted, iidIntercepted
0x180013e86  jz      short loc_180013E94
0x180013e88  mov     pptypeinfo, [iidIntercepted]
0x180013e8b  mov     rax, [pptypeinfo+10h]
0x180013e8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e94  mov     eax, ebx
0x180013e96  jmp     short loc_180013E53
0x180013e98  mov     iidIntercepted, [rbp+18h]; callerReturnAddress
0x180013e9c  lea     reasonForNoTypeInfo, aComOle32ComTxf_3; "com\\ole32\\com\\txf\\callframe\\typein"...
0x180013ea3  mov     r9d, ebx; hr
0x180013ea6  mov     edx, 25Ch; lineNumber
0x180013eab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013eb0  jmp     short loc_180013E94
0x180013eb2  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "FAILED(*reasonForNoTypeInfo)")
0x180013eb7  jmp     loc_180013DA8
0x180013ebc  and     [rbp+typeLib.m_ptr], 0
0x180013ec1  xor     edx, edx; length
0x180013ec3  call    cs:__imp_WindowsGetStringRawBuffer
0x180013eca  nop     dword ptr [rax+rax+00h]
0x180013ecf  lea     reasonForNoTypeInfo, [rbp+typeLib]; pptlib
0x180013ed3  mov     edx, 2; regkind
0x180013ed8  mov     iidIntercepted, rax; szFile
0x180013edb  call    cs:__imp_LoadTypeLibEx
0x180013ee2  nop     dword ptr [rax+rax+00h]
0x180013ee7  mov     ebx, eax
0x180013ee9  test    eax, eax
0x180013eeb  jns     short loc_180013EF4
0x180013eed  mov     edx, 27Dh
0x180013ef2  jmp     short loc_180013F15
0x180013ef4  mov     iidIntercepted, [rbp+typeLib.m_ptr]
0x180013ef8  mov     reasonForNoTypeInfo, rsi
0x180013efb  mov     pptypeinfo, r14
0x180013efe  mov     rax, [iidIntercepted]
0x180013f01  mov     rax, [rax+30h]
0x180013f05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f0a  mov     ebx, eax
0x180013f0c  test    eax, eax
0x180013f0e  jns     short loc_180013F2A
0x180013f10  mov     edx, 27Eh; lineNumber
0x180013f15  mov     iidIntercepted, [rbp+18h]; callerReturnAddress
0x180013f19  lea     reasonForNoTypeInfo, aComOle32ComTxf_3; "com\\ole32\\com\\txf\\callframe\\typein"...
0x180013f20  mov     r9d, eax; hr
0x180013f23  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013f28  jmp     short loc_180013F2C
0x180013f2a  xor     ebx, ebx
0x180013f2c  lea     iidIntercepted, [rbp+typeLib]; this
0x180013f30  call    ??1?$com_ptr_t@UICallFrameEvents@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>::~com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>(void)
0x180013f35  lea     iidIntercepted, [rbp+packagedTypeLibPath]; this
0x180013f39  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x180013f3e  lea     iidIntercepted, [rbp+packagedComCatalog]; this
0x180013f42  call    ??1?$com_ptr_t@UICallFrameEvents@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>::~com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>(void)
0x180013f47  jmp     loc_180013E94
```
