# TryGetTypeInfoFromIID(_GUID const &,ITypeInfo * *,long *)

- ea: `0x1800168f8`
- end: `0x180016b0a`
- name: `?TryGetTypeInfoFromIID@@YAJAEBU_GUID@@PEAPEAUITypeInfo@@PEAJ@Z`
- size: `530`
- prototype: `HRESULT __fastcall(const _GUID *iidIntercepted, ITypeInfo **pptypeinfo, HRESULT *reasonForNoTypeInfo)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180016114`

## callees

- `0x1800168f8`
- `0x180016b10`
- `0x1800185ec`
- `0x18001b0e4`
- `0x1800514bc`
- `0x1800ce010`

## import_xrefs

- `OLEAUT32!__imp_LoadTypeLibEx` at `0x180016ab4`
- `OLEAUT32!__imp_LoadTypeLibEx` at `0x180016ab4`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18001694e`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18001694e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001697d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001697d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016a8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016af4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016aff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016a8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016af4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016aff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180016aa2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180016aa2`

## string_xrefs

- `0x1800169ee`: `com\ole32\com\txf\callframe\typeinfo.cpp`
- `0x180016a1f`: `com\ole32\com\txf\callframe\typeinfo.cpp`
- `0x180016a6d`: `com\ole32\com\txf\callframe\typeinfo.cpp`

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
  const OLECHAR *StringRawBuffer; // rax
  int v11; // eax
  unsigned int v12; // edx
  _APTTYPE aptTypeIgnored; // [rsp+30h] [rbp-20h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (__cdecl*)(HSTRING__ *),&WindowsDeleteString,wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t> > > packagedTypeLibPath; // [rsp+38h] [rbp-18h] BYREF
  wil::com_ptr_t<ITypeLib,wil::err_returncode_policy> typeLib; // [rsp+40h] [rbp-10h] BYREF
  wil::com_ptr_t<IPackagedComProxyStubCatalogInternal,wil::err_returncode_policy> packagedComCatalog; // [rsp+48h] [rbp-8h] BYREF
  void *retaddr; // [rsp+68h] [rbp+18h]
  _APTTYPEQUALIFIER aptTypeQualifierIgnored; // [rsp+88h] [rbp+38h] BYREF

  TypeInfoFromIIDViaRegistry = TryGetTypeInfoFromIIDViaRegistry(iidIntercepted, pptypeinfo, reasonForNoTypeInfo);
  v7 = TypeInfoFromIIDViaRegistry;
  if ( TypeInfoFromIIDViaRegistry < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x25Cu,
      "com\\ole32\\com\\txf\\callframe\\typeinfo.cpp",
      TypeInfoFromIIDViaRegistry);
    return v7;
  }
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
  packagedTypeLibPath.m_ptr = 0;
  if ( ((unsigned int (__fastcall *)(IPackagedComProxyStubCatalogInternal *, const _GUID *, wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (__cdecl*)(HSTRING__ *),&WindowsDeleteString,wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t> > > *))packagedComCatalog.m_ptr->lpVtbl[1].Release)(
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
  v11 = LoadTypeLibEx(StringRawBuffer, REGKIND_NONE, &typeLib.m_ptr);
  v7 = v11;
  if ( v11 >= 0 )
  {
    v11 = ((__int64 (__fastcall *)(ITypeLib *, const _GUID *, ITypeInfo **))typeLib.m_ptr->lpVtbl[2].QueryInterface)(
            typeLib.m_ptr,
            iidIntercepted,
            pptypeinfo);
    v7 = v11;
    if ( v11 >= 0 )
    {
      wil::com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>::~com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>((wil::com_ptr_t<IProxyServerIdentity,wil::err_returncode_policy> *)&typeLib);
      if ( packagedTypeLibPath.m_ptr )
        WindowsDeleteString(packagedTypeLibPath.m_ptr);
      v7 = 0;
      goto LABEL_18;
    }
    v12 = 638;
  }
  else
  {
    v12 = 637;
  }
  wil::details::in1diag3::Return_Hr(retaddr, v12, "com\\ole32\\com\\txf\\callframe\\typeinfo.cpp", v11);
  wil::com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>::~com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>((wil::com_ptr_t<IProxyServerIdentity,wil::err_returncode_policy> *)&typeLib);
  if ( packagedTypeLibPath.m_ptr )
    WindowsDeleteString(packagedTypeLibPath.m_ptr);
LABEL_18:
  wil::com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>::~com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>((wil::com_ptr_t<IProxyServerIdentity,wil::err_returncode_policy> *)&packagedComCatalog);
  return v7;
}

```

## disassembly

```asm
0x1800168f8  mov     [rsp-18h+arg_0], rbx
0x1800168fd  mov     [rsp-18h+arg_8], rsi
0x180016902  push    rbp
0x180016903  push    rdi
0x180016904  push    r14
0x180016906  mov     rbp, rsp
0x180016909  sub     rsp, 50h
0x18001690d  mov     rdi, reasonForNoTypeInfo
0x180016910  mov     rsi, pptypeinfo
0x180016913  mov     r14, iidIntercepted
0x180016916  call    ?TryGetTypeInfoFromIIDViaRegistry@@YAJAEBU_GUID@@PEAPEAUITypeInfo@@PEAJ@Z; TryGetTypeInfoFromIIDViaRegistry(_GUID const &,ITypeInfo * *,long *)
0x18001691b  mov     ebx, eax
0x18001691d  test    eax, eax
0x18001691f  js      loc_180016A69
0x180016925  cmp     qword ptr [rsi], 0
0x180016929  jnz     loc_1800169D5
0x18001692f  cmp     dword ptr [rdi], 0
0x180016932  jge     loc_180016A83
0x180016938  lea     pptypeinfo, [rbp+aptTypeQualifierIgnored]; pAptQualifier
0x18001693c  mov     [rbp+aptTypeIgnored], 0
0x180016943  lea     iidIntercepted, [rbp+aptTypeIgnored]; pAptType
0x180016947  mov     [rbp+aptTypeQualifierIgnored], 0
0x18001694e  call    cs:__imp_CoGetApartmentType
0x180016954  test    eax, eax
0x180016956  js      short loc_1800169D5
0x180016958  xor     edx, edx; pUnkOuter
0x18001695a  mov     [rbp+packagedComCatalog.m_ptr], 0
0x180016962  lea     rax, [rbp+packagedComCatalog]
0x180016966  lea     r9, _GUID_419c4e35_36bc_4780_845d_a05c51d9f770; riid
0x18001696d  mov     [rsp+50h+ppv], rax; ppv
0x180016972  lea     iidIntercepted, _GUID_00000346_0000_0000_c000_000000000046; rclsid
0x180016979  lea     r8d, [pptypeinfo+1]; dwClsContext
0x18001697d  call    cs:__imp_CoCreateInstance
0x180016983  mov     ebx, eax
0x180016985  test    eax, eax
0x180016987  js      short loc_1800169EA
0x180016989  mov     iidIntercepted, [rbp+packagedComCatalog.m_ptr]
0x18001698d  lea     reasonForNoTypeInfo, [rbp+packagedTypeLibPath]
0x180016991  mov     [rbp+packagedTypeLibPath.m_ptr], 0
0x180016999  mov     pptypeinfo, r14
0x18001699c  mov     rax, [iidIntercepted]
0x18001699f  mov     rax, [rax+28h]
0x1800169a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800169a8  mov     iidIntercepted, [rbp+packagedTypeLibPath.m_ptr]; string
0x1800169ac  cmp     eax, 8002801Dh
0x1800169b1  jnz     loc_180016A98
0x1800169b7  test    iidIntercepted, iidIntercepted
0x1800169ba  jnz     loc_180016A8D
0x1800169c0  mov     iidIntercepted, [rbp+packagedComCatalog.m_ptr]
0x1800169c4  test    iidIntercepted, iidIntercepted
0x1800169c7  jz      short loc_1800169D5
0x1800169c9  mov     rax, [iidIntercepted]
0x1800169cc  mov     rax, [rax+10h]
0x1800169d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800169d5  xor     eax, eax
0x1800169d7  mov     rbx, [rsp+50h+arg_0]
0x1800169dc  mov     rsi, [rsp+50h+arg_8]
0x1800169e1  add     rsp, 50h
0x1800169e5  pop     r14
0x1800169e7  pop     rdi
0x1800169e8  pop     rbp
0x1800169e9  retn
0x1800169ea  mov     iidIntercepted, [rbp+18h]; callerReturnAddress
0x1800169ee  lea     reasonForNoTypeInfo, aComOle32ComTxf_3; "com\\ole32\\com\\txf\\callframe\\typein"...
0x1800169f5  mov     r9d, ebx; hr
0x1800169f8  mov     edx, 26Dh; lineNumber
0x1800169fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016a02  mov     iidIntercepted, [rbp+packagedComCatalog.m_ptr]
0x180016a06  test    iidIntercepted, iidIntercepted
0x180016a09  jz      short loc_180016A17
0x180016a0b  mov     pptypeinfo, [iidIntercepted]
0x180016a0e  mov     rax, [pptypeinfo+10h]
0x180016a12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a17  mov     eax, ebx
0x180016a19  jmp     short loc_1800169D7
0x180016a1b  mov     iidIntercepted, [rbp+18h]; callerReturnAddress
0x180016a1f  lea     reasonForNoTypeInfo, aComOle32ComTxf_3; "com\\ole32\\com\\txf\\callframe\\typein"...
0x180016a26  mov     r9d, eax; hr
0x180016a29  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016a2e  lea     iidIntercepted, [rbp+typeLib]; this
0x180016a32  call    ??1?$com_ptr_t@UICallFrameEvents@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>::~com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>(void)
0x180016a37  mov     iidIntercepted, [rbp+packagedTypeLibPath.m_ptr]; string
0x180016a3b  test    iidIntercepted, iidIntercepted
0x180016a3e  jnz     loc_180016AF4
0x180016a44  lea     iidIntercepted, [rbp+packagedComCatalog]; this
0x180016a48  call    ??1?$com_ptr_t@UICallFrameEvents@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>::~com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>(void)
0x180016a4d  jmp     short loc_180016A17
0x180016a4f  lea     iidIntercepted, [rbp+typeLib]; this
0x180016a53  call    ??1?$com_ptr_t@UICallFrameEvents@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>::~com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>(void)
0x180016a58  mov     iidIntercepted, [rbp+packagedTypeLibPath.m_ptr]; string
0x180016a5c  test    iidIntercepted, iidIntercepted
0x180016a5f  jnz     loc_180016AFF
0x180016a65  xor     ebx, ebx
0x180016a67  jmp     short loc_180016A44
0x180016a69  mov     iidIntercepted, [rbp+18h]; callerReturnAddress
0x180016a6d  lea     reasonForNoTypeInfo, aComOle32ComTxf_3; "com\\ole32\\com\\txf\\callframe\\typein"...
0x180016a74  mov     r9d, ebx; hr
0x180016a77  mov     edx, 25Ch; lineNumber
0x180016a7c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016a81  jmp     short loc_180016A17
0x180016a83  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "FAILED(*reasonForNoTypeInfo)")
0x180016a88  jmp     loc_180016938
0x180016a8d  call    cs:__imp_WindowsDeleteString
0x180016a93  jmp     loc_1800169C0
0x180016a98  xor     edx, edx; length
0x180016a9a  mov     [rbp+typeLib.m_ptr], 0
0x180016aa2  call    cs:__imp_WindowsGetStringRawBuffer
0x180016aa8  lea     reasonForNoTypeInfo, [rbp+typeLib]; pptlib
0x180016aac  mov     edx, 2; regkind
0x180016ab1  mov     iidIntercepted, rax; szFile
0x180016ab4  call    cs:__imp_LoadTypeLibEx
0x180016aba  mov     ebx, eax
0x180016abc  test    eax, eax
0x180016abe  jns     short loc_180016ACA
0x180016ac0  mov     edx, 27Dh; lineNumber
0x180016ac5  jmp     loc_180016A1B
0x180016aca  mov     iidIntercepted, [rbp+typeLib.m_ptr]
0x180016ace  mov     reasonForNoTypeInfo, rsi
0x180016ad1  mov     pptypeinfo, r14
0x180016ad4  mov     rax, [iidIntercepted]
0x180016ad7  mov     rax, [rax+30h]
0x180016adb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ae0  mov     ebx, eax
0x180016ae2  test    eax, eax
0x180016ae4  jns     loc_180016A4F
0x180016aea  mov     edx, 27Eh
0x180016aef  jmp     loc_180016A1B
0x180016af4  call    cs:__imp_WindowsDeleteString
0x180016afa  jmp     loc_180016A44
0x180016aff  call    cs:__imp_WindowsDeleteString
0x180016b05  jmp     loc_180016A65
```
