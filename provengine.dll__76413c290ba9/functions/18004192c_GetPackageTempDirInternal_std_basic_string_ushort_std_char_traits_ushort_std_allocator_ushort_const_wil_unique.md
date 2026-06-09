# GetPackageTempDirInternal(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)

- ea: `0x18004192c`
- end: `0x180041ce3`
- name: `?GetPackageTempDirInternal@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `951`
- prototype: `__int64 __fastcall(const WCHAR *pszMore, HLOCAL *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800318a4`
- `0x180041e04`

## callees

- `0x1800098dc`
- `0x18004192c`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180041b71`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180041c61`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180041b71`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180041c61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041b5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041c4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041b5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041c4e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180041969`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180041969`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041a68`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041b15`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041be6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041c92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041a68`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041b15`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041be6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041c92`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041af6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041b05`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041b69`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041bc7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041bd6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041c59`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041c73`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041c82`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041af6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041b05`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041b69`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041bc7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041bd6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041c59`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041c73`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041c82`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180041ac5`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180041b96`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180041ac5`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180041b96`

## string_xrefs

- `0x180041aba`: `Temp\ProvisioningPkgTmp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
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
0x18004192c  mov     [rsp-28h+arg_0], rbx
0x180041931  push    rbp
0x180041932  push    rsi
0x180041933  push    rdi
0x180041934  push    r14
0x180041936  push    r15
0x180041938  mov     rbp, rsp
0x18004193b  sub     rsp, 50h
0x18004193f  mov     rsi, rdx
0x180041942  mov     rdi, rcx
0x180041945  xor     r15d, r15d
0x180041948  mov     [rbp+arg_10], r15
0x18004194c  lea     rax, [rbp+arg_10]
0x180041950  mov     qword ptr [rsp+50h+ppv], rax; int
0x180041955  lea     r9, _GUID_8be2d872_86aa_4d47_b776_32cca40c7018; riid
0x18004195c  xor     edx, edx; pUnkOuter
0x18004195e  lea     r8d, [r15+1]; dwClsContext
0x180041962  lea     rcx, CLSID_KnownFolderManager; rclsid
0x180041969  call    cs:__imp_CoCreateInstance
0x18004196f  mov     ebx, eax
0x180041971  test    eax, eax
0x180041973  jns     short loc_1800419AE
0x180041975  mov     rcx, [rbp+28h]; this
0x180041979  mov     r9d, eax; char *
0x18004197c  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\prov\\lib\\provpacka"...
0x180041983  lea     edx, [r15+18h]; void *
0x180041987  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004198c  nop
0x18004198d  mov     rcx, [rbp+arg_10]
0x180041991  test    rcx, rcx
0x180041994  jz      short loc_1800419A7
0x180041996  mov     [rbp+arg_10], r15
0x18004199a  mov     rax, [rcx]
0x18004199d  mov     rax, [rax+10h]
0x1800419a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800419a6  nop
0x1800419a7  mov     eax, ebx
0x1800419a9  jmp     loc_180041CCF
0x1800419ae  mov     [rbp+arg_18], r15
0x1800419b2  mov     rcx, [rbp+arg_10]
0x1800419b6  mov     rax, [rcx]
0x1800419b9  lea     r8, [rbp+arg_18]
0x1800419bd  lea     rdx, FOLDERID_LocalAppData
0x1800419c4  mov     rax, [rax+30h]
0x1800419c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800419cd  mov     ebx, eax
0x1800419cf  test    eax, eax
0x1800419d1  jns     short loc_180041A22
0x1800419d3  mov     rcx, [rbp+28h]; this
0x1800419d7  mov     r9d, eax; char *
0x1800419da  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\prov\\lib\\provpacka"...
0x1800419e1  mov     edx, 1Ah; void *
0x1800419e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800419eb  nop
0x1800419ec  mov     rcx, [rbp+arg_18]
0x1800419f0  test    rcx, rcx
0x1800419f3  jz      short loc_180041A06
0x1800419f5  mov     [rbp+arg_18], r15
0x1800419f9  mov     rax, [rcx]
0x1800419fc  mov     rax, [rax+10h]
0x180041a00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041a05  nop
0x180041a06  mov     rcx, [rbp+arg_10]
0x180041a0a  test    rcx, rcx
0x180041a0d  jz      short loc_180041A20
0x180041a0f  mov     [rbp+arg_10], r15
0x180041a13  mov     rax, [rcx]
0x180041a16  mov     rax, [rax+10h]
0x180041a1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041a1f  nop
0x180041a20  jmp     short loc_1800419A7
0x180041a22  mov     [rbp+pv], r15
0x180041a26  mov     rcx, [rbp+arg_18]
0x180041a2a  mov     rax, [rcx]
0x180041a2d  mov     [rbp+pv], r15
0x180041a31  lea     r8, [rbp+pv]
0x180041a35  xor     edx, edx
0x180041a37  mov     rax, [rax+30h]
0x180041a3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041a40  mov     ebx, eax
0x180041a42  test    eax, eax
0x180041a44  jns     short loc_180041AA8
0x180041a46  mov     rcx, [rbp+28h]; this
0x180041a4a  mov     r9d, eax; char *
0x180041a4d  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\prov\\lib\\provpacka"...
0x180041a54  mov     edx, 1Ch; void *
0x180041a59  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041a5e  nop
0x180041a5f  mov     rcx, [rbp+pv]; pv
0x180041a63  test    rcx, rcx
0x180041a66  jz      short loc_180041A6F
0x180041a68  call    cs:__imp_CoTaskMemFree
0x180041a6e  nop
0x180041a6f  mov     rcx, [rbp+arg_18]
0x180041a73  test    rcx, rcx
0x180041a76  jz      short loc_180041A89
0x180041a78  mov     [rbp+arg_18], r15
0x180041a7c  mov     rax, [rcx]
0x180041a7f  mov     rax, [rax+10h]
0x180041a83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041a88  nop
0x180041a89  mov     rcx, [rbp+arg_10]
0x180041a8d  test    rcx, rcx
0x180041a90  jz      short loc_180041AA3
0x180041a92  mov     [rbp+arg_10], r15
0x180041a96  mov     rax, [rcx]
0x180041a99  mov     rax, [rax+10h]
0x180041a9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041aa2  nop
0x180041aa3  jmp     loc_1800419A7
0x180041aa8  mov     [rbp+hMem], r15
0x180041aac  mov     [rbp+ppszPathOut], r15
0x180041ab0  lea     r9, [rbp+ppszPathOut]; ppszPathOut
0x180041ab4  mov     r8d, 1; dwFlags
0x180041aba  lea     rdx, pszMore; "Temp\\ProvisioningPkgTmp"
0x180041ac1  mov     rcx, [rbp+pv]; pszPathIn
0x180041ac5  call    cs:__imp_PathAllocCombine
0x180041acb  mov     ebx, eax
0x180041acd  test    eax, eax
0x180041acf  jns     loc_180041B55
0x180041ad5  mov     rcx, [rbp+28h]; this
0x180041ad9  mov     r9d, eax; char *
0x180041adc  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\prov\\lib\\provpacka"...
0x180041ae3  mov     edx, 20h ; ' '; void *
0x180041ae8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041aed  mov     rcx, [rbp+hMem]; hMem
0x180041af1  test    rcx, rcx
0x180041af4  jz      short loc_180041AFC
0x180041af6  call    cs:__imp_LocalFree
0x180041afc  mov     rcx, [rbp+ppszPathOut]; hMem
0x180041b00  test    rcx, rcx
0x180041b03  jz      short loc_180041B0C
0x180041b05  call    cs:__imp_LocalFree
0x180041b0b  nop
0x180041b0c  mov     rcx, [rbp+pv]; pv
0x180041b10  test    rcx, rcx
0x180041b13  jz      short loc_180041B1C
0x180041b15  call    cs:__imp_CoTaskMemFree
0x180041b1b  nop
0x180041b1c  mov     rcx, [rbp+arg_18]
0x180041b20  test    rcx, rcx
0x180041b23  jz      short loc_180041B36
0x180041b25  mov     [rbp+arg_18], r15
0x180041b29  mov     rax, [rcx]
0x180041b2c  mov     rax, [rax+10h]
0x180041b30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041b35  nop
0x180041b36  mov     rcx, [rbp+arg_10]
0x180041b3a  test    rcx, rcx
0x180041b3d  jz      short loc_180041B50
0x180041b3f  mov     [rbp+arg_10], r15
0x180041b43  mov     rax, [rcx]
0x180041b46  mov     rax, [rax+10h]
0x180041b4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041b4f  nop
0x180041b50  jmp     loc_1800419A7
0x180041b55  mov     r14, [rbp+hMem]
0x180041b59  test    r14, r14
0x180041b5c  jz      short loc_180041B77
0x180041b5e  call    cs:__imp_GetLastError
0x180041b64  mov     ebx, eax
0x180041b66  mov     rcx, r14; hMem
0x180041b69  call    cs:__imp_LocalFree
0x180041b6f  mov     ecx, ebx; dwErrCode
0x180041b71  call    cs:__imp_SetLastError
0x180041b77  mov     [rbp+hMem], r15
0x180041b7b  cmp     qword ptr [rdi+18h], 8
0x180041b80  jb      short loc_180041B85
0x180041b82  mov     rdi, [rdi]
0x180041b85  lea     r9, [rbp+hMem]; ppszPathOut
0x180041b89  mov     r8d, 1; dwFlags
0x180041b8f  mov     rdx, rdi; pszMore
0x180041b92  mov     rcx, [rbp+ppszPathOut]; pszPathIn
0x180041b96  call    cs:__imp_PathAllocCombine
0x180041b9c  mov     ebx, eax
0x180041b9e  test    eax, eax
0x180041ba0  jns     loc_180041C26
0x180041ba6  mov     rcx, [rbp+28h]; this
0x180041baa  mov     r9d, eax; char *
0x180041bad  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\prov\\lib\\provpacka"...
0x180041bb4  mov     edx, 21h ; '!'; void *
0x180041bb9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041bbe  mov     rcx, [rbp+hMem]; hMem
0x180041bc2  test    rcx, rcx
0x180041bc5  jz      short loc_180041BCD
0x180041bc7  call    cs:__imp_LocalFree
0x180041bcd  mov     rcx, [rbp+ppszPathOut]; hMem
0x180041bd1  test    rcx, rcx
0x180041bd4  jz      short loc_180041BDD
0x180041bd6  call    cs:__imp_LocalFree
0x180041bdc  nop
0x180041bdd  mov     rcx, [rbp+pv]; pv
0x180041be1  test    rcx, rcx
0x180041be4  jz      short loc_180041BED
0x180041be6  call    cs:__imp_CoTaskMemFree
0x180041bec  nop
0x180041bed  mov     rcx, [rbp+arg_18]
0x180041bf1  test    rcx, rcx
0x180041bf4  jz      short loc_180041C07
0x180041bf6  mov     [rbp+arg_18], r15
0x180041bfa  mov     rax, [rcx]
0x180041bfd  mov     rax, [rax+10h]
0x180041c01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041c06  nop
0x180041c07  mov     rcx, [rbp+arg_10]
0x180041c0b  test    rcx, rcx
0x180041c0e  jz      short loc_180041C21
0x180041c10  mov     [rbp+arg_10], r15
0x180041c14  mov     rax, [rcx]
0x180041c17  mov     rax, [rax+10h]
0x180041c1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041c20  nop
0x180041c21  jmp     loc_1800419A7
0x180041c26  mov     rdi, [rsi]
0x180041c29  mov     [rsi], r15
0x180041c2c  lea     rax, [rbp+hMem]
0x180041c30  cmp     rsi, rax
0x180041c33  jz      short loc_180041C45
0x180041c35  mov     rax, [rbp+hMem]
0x180041c39  mov     [rsi], rax
0x180041c3c  mov     rbx, r15
0x180041c3f  mov     [rbp+hMem], rbx
0x180041c43  jmp     short loc_180041C49
0x180041c45  mov     rbx, [rbp+hMem]
0x180041c49  test    rbx, rbx
0x180041c4c  jz      short loc_180041C67
0x180041c4e  call    cs:__imp_GetLastError
0x180041c54  mov     esi, eax
0x180041c56  mov     rcx, rbx; hMem
0x180041c59  call    cs:__imp_LocalFree
0x180041c5f  mov     ecx, esi; dwErrCode
0x180041c61  call    cs:__imp_SetLastError
0x180041c67  mov     [rbp+hMem], rdi
0x180041c6b  test    rdi, rdi
0x180041c6e  jz      short loc_180041C79
0x180041c70  mov     rcx, rdi; hMem
0x180041c73  call    cs:__imp_LocalFree
0x180041c79  mov     rcx, [rbp+ppszPathOut]; hMem
0x180041c7d  test    rcx, rcx
0x180041c80  jz      short loc_180041C89
0x180041c82  call    cs:__imp_LocalFree
0x180041c88  nop
0x180041c89  mov     rcx, [rbp+pv]; pv
0x180041c8d  test    rcx, rcx
0x180041c90  jz      short loc_180041C99
0x180041c92  call    cs:__imp_CoTaskMemFree
0x180041c98  nop
0x180041c99  mov     rcx, [rbp+arg_18]
0x180041c9d  test    rcx, rcx
0x180041ca0  jz      short loc_180041CB3
0x180041ca2  mov     [rbp+arg_18], r15
0x180041ca6  mov     rax, [rcx]
0x180041ca9  mov     rax, [rax+10h]
0x180041cad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041cb2  nop
0x180041cb3  mov     rcx, [rbp+arg_10]
0x180041cb7  test    rcx, rcx
0x180041cba  jz      short loc_180041CCD
0x180041cbc  mov     [rbp+arg_10], r15
0x180041cc0  mov     rax, [rcx]
0x180041cc3  mov     rax, [rax+10h]
0x180041cc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041ccc  nop
0x180041ccd  xor     eax, eax
0x180041ccf  mov     rbx, [rsp+50h+arg_0]
0x180041cd7  add     rsp, 50h
0x180041cdb  pop     r15
0x180041cdd  pop     r14
0x180041cdf  pop     rdi
0x180041ce0  pop     rsi
0x180041ce1  pop     rbp
0x180041ce2  retn
```
