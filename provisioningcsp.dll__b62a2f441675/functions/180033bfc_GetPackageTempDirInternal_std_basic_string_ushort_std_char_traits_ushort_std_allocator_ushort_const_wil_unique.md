# GetPackageTempDirInternal(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)

- ea: `0x180033bfc`
- end: `0x180034026`
- name: `?GetPackageTempDirInternal@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `1066`
- prototype: `__int64 __fastcall(PCWSTR pszMore)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180027a00`

## callees

- `0x180006974`
- `0x180033bfc`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033e52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033f6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033e52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033f6c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180033e71`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180033f8b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180033e71`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180033f8b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180033c39`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180033c39`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033d3e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033e03`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033efe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033fce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033d3e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033e03`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033efe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033fce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033dd8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033ded`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033e63`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033ed3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033ee8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033f7d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033fa3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033fb8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033dd8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033ded`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033e63`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033ed3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033ee8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033f7d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033fa3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033fb8`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180033da1`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180033e9c`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180033da1`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180033e9c`

## string_xrefs

- `0x180033d96`: `Temp\ProvisioningPkgTmp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall GetPackageTempDirInternal(const WCHAR *pszMore, HLOCAL *a2)
{
  HRESULT v4; // eax
  unsigned int v5; // ebx
  LPVOID v6; // rcx
  int v8; // eax
  _QWORD *v9; // rcx
  LPVOID v10; // rcx
  __int64 v11; // rax
  int v12; // eax
  _QWORD *v13; // rcx
  LPVOID v14; // rcx
  HRESULT v15; // eax
  _QWORD *v16; // rcx
  LPVOID v17; // rcx
  HRESULT v18; // eax
  _QWORD *v19; // rcx
  LPVOID v20; // rcx
  HLOCAL v21; // rdi
  HLOCAL v22; // rbx
  DWORD LastError; // esi
  _QWORD *v24; // rcx
  LPVOID v25; // rcx
  int ppv; // [rsp+20h] [rbp-30h]
  HLOCAL hMem; // [rsp+30h] [rbp-20h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-18h] BYREF
  PWSTR ppszPathOut; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  LPVOID v31; // [rsp+90h] [rbp+40h] BYREF
  _QWORD *v32; // [rsp+98h] [rbp+48h] BYREF

  v31 = 0;
  v4 = CoCreateInstance(&CLSID_KnownFolderManager, 0, 1u, &GUID_8be2d872_86aa_4d47_b776_32cca40c7018, &v31);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\provpackage.cpp",
      (const char *)(unsigned int)v4,
      ppv);
    v6 = v31;
    if ( v31 )
    {
      v31 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v6 + 16LL))(v6);
    }
    return v5;
  }
  v32 = 0;
  v8 = (*(__int64 (__fastcall **)(LPVOID, const GUID *, _QWORD **))(*(_QWORD *)v31 + 48LL))(
         v31,
         &FOLDERID_LocalAppData,
         &v32);
  v5 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\provpackage.cpp",
      (const char *)(unsigned int)v8,
      ppv);
    v9 = v32;
    if ( v32 )
    {
      v32 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v9 + 16LL))(v9);
    }
    v10 = v31;
    if ( v31 )
    {
      v31 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v10 + 16LL))(v10);
    }
    return v5;
  }
  pv = 0;
  v11 = *v32;
  pv = 0;
  v12 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD, LPVOID *))(v11 + 48))(v32, 0, &pv);
  v5 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\provpackage.cpp",
      (const char *)(unsigned int)v12,
      ppv);
    if ( pv )
      CoTaskMemFree(pv);
    v13 = v32;
    if ( v32 )
    {
      v32 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v13 + 16LL))(v13);
    }
    v14 = v31;
    if ( v31 )
    {
      v31 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v14 + 16LL))(v14);
    }
    return v5;
  }
  hMem = 0;
  ppszPathOut = 0;
  v15 = PathAllocCombine((PCWSTR)pv, L"Temp\\ProvisioningPkgTmp", 1u, &ppszPathOut);
  v5 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x20,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\provpackage.cpp",
      (const char *)(unsigned int)v15,
      ppv);
    if ( ppszPathOut )
      LocalFree(ppszPathOut);
    if ( pv )
      CoTaskMemFree(pv);
    v16 = v32;
    if ( v32 )
    {
      v32 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v16 + 16LL))(v16);
    }
    v17 = v31;
    if ( v31 )
    {
      v31 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v17 + 16LL))(v17);
    }
    return v5;
  }
  hMem = 0;
  if ( *((_QWORD *)pszMore + 3) >= 8u )
    pszMore = *(const WCHAR **)pszMore;
  v18 = PathAllocCombine(ppszPathOut, pszMore, 1u, (PWSTR *)&hMem);
  v5 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x21,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\provpackage.cpp",
      (const char *)(unsigned int)v18,
      ppv);
    if ( hMem )
      LocalFree(hMem);
    if ( ppszPathOut )
      LocalFree(ppszPathOut);
    if ( pv )
      CoTaskMemFree(pv);
    v19 = v32;
    if ( v32 )
    {
      v32 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v19 + 16LL))(v19);
    }
    v20 = v31;
    if ( v31 )
    {
      v31 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v20 + 16LL))(v20);
    }
    return v5;
  }
  v21 = *a2;
  *a2 = 0;
  if ( a2 == &hMem )
  {
    v22 = hMem;
  }
  else
  {
    *a2 = hMem;
    v22 = 0;
    hMem = 0;
  }
  if ( v22 )
  {
    LastError = GetLastError();
    LocalFree(v22);
    SetLastError(LastError);
  }
  hMem = v21;
  if ( v21 )
    LocalFree(v21);
  if ( ppszPathOut )
    LocalFree(ppszPathOut);
  if ( pv )
    CoTaskMemFree(pv);
  v24 = v32;
  if ( v32 )
  {
    v32 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v24 + 16LL))(v24);
  }
  v25 = v31;
  if ( v31 )
  {
    v31 = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v25 + 16LL))(v25);
  }
  return 0;
}

```

## disassembly

```asm
0x180033bfc  mov     [rsp-28h+arg_0], rbx
0x180033c01  push    rbp
0x180033c02  push    rsi
0x180033c03  push    rdi
0x180033c04  push    r14
0x180033c06  push    r15
0x180033c08  mov     rbp, rsp
0x180033c0b  sub     rsp, 50h
0x180033c0f  mov     rsi, rdx
0x180033c12  mov     rdi, rcx
0x180033c15  xor     r15d, r15d
0x180033c18  mov     [rbp+arg_10], r15
0x180033c1c  lea     rax, [rbp+arg_10]
0x180033c20  mov     qword ptr [rsp+50h+ppv], rax; int
0x180033c25  lea     r9, _GUID_8be2d872_86aa_4d47_b776_32cca40c7018; riid
0x180033c2c  xor     edx, edx; pUnkOuter
0x180033c2e  lea     r8d, [r15+1]; dwClsContext
0x180033c32  lea     rcx, CLSID_KnownFolderManager; rclsid
0x180033c39  call    cs:__imp_CoCreateInstance
0x180033c40  nop     dword ptr [rax+rax+00h]
0x180033c45  mov     ebx, eax
0x180033c47  test    eax, eax
0x180033c49  jns     short loc_180033C84
0x180033c4b  mov     rcx, [rbp+28h]; this
0x180033c4f  mov     r9d, eax; char *
0x180033c52  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\prov\\lib\\provpacka"...
0x180033c59  lea     edx, [r15+18h]; void *
0x180033c5d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033c62  nop
0x180033c63  mov     rcx, [rbp+arg_10]
0x180033c67  test    rcx, rcx
0x180033c6a  jz      short loc_180033C7D
0x180033c6c  mov     [rbp+arg_10], r15
0x180033c70  mov     rax, [rcx]
0x180033c73  mov     rax, [rax+10h]
0x180033c77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033c7c  nop
0x180033c7d  mov     eax, ebx
0x180033c7f  jmp     loc_180034011
0x180033c84  mov     [rbp+arg_18], r15
0x180033c88  mov     rcx, [rbp+arg_10]
0x180033c8c  mov     rax, [rcx]
0x180033c8f  lea     r8, [rbp+arg_18]
0x180033c93  lea     rdx, FOLDERID_LocalAppData
0x180033c9a  mov     rax, [rax+30h]
0x180033c9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033ca3  mov     ebx, eax
0x180033ca5  test    eax, eax
0x180033ca7  jns     short loc_180033CF8
0x180033ca9  mov     rcx, [rbp+28h]; this
0x180033cad  mov     r9d, eax; char *
0x180033cb0  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\prov\\lib\\provpacka"...
0x180033cb7  mov     edx, 1Ah; void *
0x180033cbc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033cc1  nop
0x180033cc2  mov     rcx, [rbp+arg_18]
0x180033cc6  test    rcx, rcx
0x180033cc9  jz      short loc_180033CDC
0x180033ccb  mov     [rbp+arg_18], r15
0x180033ccf  mov     rax, [rcx]
0x180033cd2  mov     rax, [rax+10h]
0x180033cd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033cdb  nop
0x180033cdc  mov     rcx, [rbp+arg_10]
0x180033ce0  test    rcx, rcx
0x180033ce3  jz      short loc_180033CF6
0x180033ce5  mov     [rbp+arg_10], r15
0x180033ce9  mov     rax, [rcx]
0x180033cec  mov     rax, [rax+10h]
0x180033cf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033cf5  nop
0x180033cf6  jmp     short loc_180033C7D
0x180033cf8  mov     [rbp+pv], r15
0x180033cfc  mov     rcx, [rbp+arg_18]
0x180033d00  mov     rax, [rcx]
0x180033d03  mov     [rbp+pv], r15
0x180033d07  lea     r8, [rbp+pv]
0x180033d0b  xor     edx, edx
0x180033d0d  mov     rax, [rax+30h]
0x180033d11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033d16  mov     ebx, eax
0x180033d18  test    eax, eax
0x180033d1a  jns     short loc_180033D84
0x180033d1c  mov     rcx, [rbp+28h]; this
0x180033d20  mov     r9d, eax; char *
0x180033d23  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\prov\\lib\\provpacka"...
0x180033d2a  mov     edx, 1Ch; void *
0x180033d2f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033d34  nop
0x180033d35  mov     rcx, [rbp+pv]; pv
0x180033d39  test    rcx, rcx
0x180033d3c  jz      short loc_180033D4B
0x180033d3e  call    cs:__imp_CoTaskMemFree
0x180033d45  nop     dword ptr [rax+rax+00h]
0x180033d4a  nop
0x180033d4b  mov     rcx, [rbp+arg_18]
0x180033d4f  test    rcx, rcx
0x180033d52  jz      short loc_180033D65
0x180033d54  mov     [rbp+arg_18], r15
0x180033d58  mov     rax, [rcx]
0x180033d5b  mov     rax, [rax+10h]
0x180033d5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033d64  nop
0x180033d65  mov     rcx, [rbp+arg_10]
0x180033d69  test    rcx, rcx
0x180033d6c  jz      short loc_180033D7F
0x180033d6e  mov     [rbp+arg_10], r15
0x180033d72  mov     rax, [rcx]
0x180033d75  mov     rax, [rax+10h]
0x180033d79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033d7e  nop
0x180033d7f  jmp     loc_180033C7D
0x180033d84  mov     [rbp+hMem], r15
0x180033d88  mov     [rbp+ppszPathOut], r15
0x180033d8c  lea     r9, [rbp+ppszPathOut]; ppszPathOut
0x180033d90  mov     r8d, 1; dwFlags
0x180033d96  lea     rdx, aTempProvisioni; "Temp\\ProvisioningPkgTmp"
0x180033d9d  mov     rcx, [rbp+pv]; pszPathIn
0x180033da1  call    cs:__imp_PathAllocCombine
0x180033da8  nop     dword ptr [rax+rax+00h]
0x180033dad  mov     ebx, eax
0x180033daf  test    eax, eax
0x180033db1  jns     loc_180033E49
0x180033db7  mov     rcx, [rbp+28h]; this
0x180033dbb  mov     r9d, eax; char *
0x180033dbe  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\prov\\lib\\provpacka"...
0x180033dc5  mov     edx, 20h ; ' '; void *
0x180033dca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033dcf  mov     rcx, [rbp+hMem]; hMem
0x180033dd3  test    rcx, rcx
0x180033dd6  jz      short loc_180033DE4
0x180033dd8  call    cs:__imp_LocalFree
0x180033ddf  nop     dword ptr [rax+rax+00h]
0x180033de4  mov     rcx, [rbp+ppszPathOut]; hMem
0x180033de8  test    rcx, rcx
0x180033deb  jz      short loc_180033DFA
0x180033ded  call    cs:__imp_LocalFree
0x180033df4  nop     dword ptr [rax+rax+00h]
0x180033df9  nop
0x180033dfa  mov     rcx, [rbp+pv]; pv
0x180033dfe  test    rcx, rcx
0x180033e01  jz      short loc_180033E10
0x180033e03  call    cs:__imp_CoTaskMemFree
0x180033e0a  nop     dword ptr [rax+rax+00h]
0x180033e0f  nop
0x180033e10  mov     rcx, [rbp+arg_18]
0x180033e14  test    rcx, rcx
0x180033e17  jz      short loc_180033E2A
0x180033e19  mov     [rbp+arg_18], r15
0x180033e1d  mov     rax, [rcx]
0x180033e20  mov     rax, [rax+10h]
0x180033e24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033e29  nop
0x180033e2a  mov     rcx, [rbp+arg_10]
0x180033e2e  test    rcx, rcx
0x180033e31  jz      short loc_180033E44
0x180033e33  mov     [rbp+arg_10], r15
0x180033e37  mov     rax, [rcx]
0x180033e3a  mov     rax, [rax+10h]
0x180033e3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033e43  nop
0x180033e44  jmp     loc_180033C7D
0x180033e49  mov     r14, [rbp+hMem]
0x180033e4d  test    r14, r14
0x180033e50  jz      short loc_180033E7D
0x180033e52  call    cs:__imp_GetLastError
0x180033e59  nop     dword ptr [rax+rax+00h]
0x180033e5e  mov     ebx, eax
0x180033e60  mov     rcx, r14; hMem
0x180033e63  call    cs:__imp_LocalFree
0x180033e6a  nop     dword ptr [rax+rax+00h]
0x180033e6f  mov     ecx, ebx; dwErrCode
0x180033e71  call    cs:__imp_SetLastError
0x180033e78  nop     dword ptr [rax+rax+00h]
0x180033e7d  mov     [rbp+hMem], r15
0x180033e81  cmp     qword ptr [rdi+18h], 8
0x180033e86  jb      short loc_180033E8B
0x180033e88  mov     rdi, [rdi]
0x180033e8b  lea     r9, [rbp+hMem]; ppszPathOut
0x180033e8f  mov     r8d, 1; dwFlags
0x180033e95  mov     rdx, rdi; pszMore
0x180033e98  mov     rcx, [rbp+ppszPathOut]; pszPathIn
0x180033e9c  call    cs:__imp_PathAllocCombine
0x180033ea3  nop     dword ptr [rax+rax+00h]
0x180033ea8  mov     ebx, eax
0x180033eaa  test    eax, eax
0x180033eac  jns     loc_180033F44
0x180033eb2  mov     rcx, [rbp+28h]; this
0x180033eb6  mov     r9d, eax; char *
0x180033eb9  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\prov\\lib\\provpacka"...
0x180033ec0  mov     edx, 21h ; '!'; void *
0x180033ec5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033eca  mov     rcx, [rbp+hMem]; hMem
0x180033ece  test    rcx, rcx
0x180033ed1  jz      short loc_180033EDF
0x180033ed3  call    cs:__imp_LocalFree
0x180033eda  nop     dword ptr [rax+rax+00h]
0x180033edf  mov     rcx, [rbp+ppszPathOut]; hMem
0x180033ee3  test    rcx, rcx
0x180033ee6  jz      short loc_180033EF5
0x180033ee8  call    cs:__imp_LocalFree
0x180033eef  nop     dword ptr [rax+rax+00h]
0x180033ef4  nop
0x180033ef5  mov     rcx, [rbp+pv]; pv
0x180033ef9  test    rcx, rcx
0x180033efc  jz      short loc_180033F0B
0x180033efe  call    cs:__imp_CoTaskMemFree
0x180033f05  nop     dword ptr [rax+rax+00h]
0x180033f0a  nop
0x180033f0b  mov     rcx, [rbp+arg_18]
0x180033f0f  test    rcx, rcx
0x180033f12  jz      short loc_180033F25
0x180033f14  mov     [rbp+arg_18], r15
0x180033f18  mov     rax, [rcx]
0x180033f1b  mov     rax, [rax+10h]
0x180033f1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033f24  nop
0x180033f25  mov     rcx, [rbp+arg_10]
0x180033f29  test    rcx, rcx
0x180033f2c  jz      short loc_180033F3F
0x180033f2e  mov     [rbp+arg_10], r15
0x180033f32  mov     rax, [rcx]
0x180033f35  mov     rax, [rax+10h]
0x180033f39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033f3e  nop
0x180033f3f  jmp     loc_180033C7D
0x180033f44  mov     rdi, [rsi]
0x180033f47  mov     [rsi], r15
0x180033f4a  lea     rax, [rbp+hMem]
0x180033f4e  cmp     rsi, rax
0x180033f51  jz      short loc_180033F63
0x180033f53  mov     rax, [rbp+hMem]
0x180033f57  mov     [rsi], rax
0x180033f5a  mov     rbx, r15
0x180033f5d  mov     [rbp+hMem], rbx
0x180033f61  jmp     short loc_180033F67
0x180033f63  mov     rbx, [rbp+hMem]
0x180033f67  test    rbx, rbx
0x180033f6a  jz      short loc_180033F97
0x180033f6c  call    cs:__imp_GetLastError
0x180033f73  nop     dword ptr [rax+rax+00h]
0x180033f78  mov     esi, eax
0x180033f7a  mov     rcx, rbx; hMem
0x180033f7d  call    cs:__imp_LocalFree
0x180033f84  nop     dword ptr [rax+rax+00h]
0x180033f89  mov     ecx, esi; dwErrCode
0x180033f8b  call    cs:__imp_SetLastError
0x180033f92  nop     dword ptr [rax+rax+00h]
0x180033f97  mov     [rbp+hMem], rdi
0x180033f9b  test    rdi, rdi
0x180033f9e  jz      short loc_180033FAF
0x180033fa0  mov     rcx, rdi; hMem
0x180033fa3  call    cs:__imp_LocalFree
0x180033faa  nop     dword ptr [rax+rax+00h]
0x180033faf  mov     rcx, [rbp+ppszPathOut]; hMem
0x180033fb3  test    rcx, rcx
0x180033fb6  jz      short loc_180033FC5
0x180033fb8  call    cs:__imp_LocalFree
0x180033fbf  nop     dword ptr [rax+rax+00h]
0x180033fc4  nop
0x180033fc5  mov     rcx, [rbp+pv]; pv
0x180033fc9  test    rcx, rcx
0x180033fcc  jz      short loc_180033FDB
0x180033fce  call    cs:__imp_CoTaskMemFree
0x180033fd5  nop     dword ptr [rax+rax+00h]
0x180033fda  nop
0x180033fdb  mov     rcx, [rbp+arg_18]
0x180033fdf  test    rcx, rcx
0x180033fe2  jz      short loc_180033FF5
0x180033fe4  mov     [rbp+arg_18], r15
0x180033fe8  mov     rax, [rcx]
0x180033feb  mov     rax, [rax+10h]
0x180033fef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033ff4  nop
0x180033ff5  mov     rcx, [rbp+arg_10]
0x180033ff9  test    rcx, rcx
0x180033ffc  jz      short loc_18003400F
0x180033ffe  mov     [rbp+arg_10], r15
0x180034002  mov     rax, [rcx]
0x180034005  mov     rax, [rax+10h]
0x180034009  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003400e  nop
0x18003400f  xor     eax, eax
0x180034011  mov     rbx, [rsp+50h+arg_0]
0x180034019  add     rsp, 50h
0x18003401d  pop     r15
0x18003401f  pop     r14
0x180034021  pop     rdi
0x180034022  pop     rsi
0x180034023  pop     rbp
0x180034024  retn
```
