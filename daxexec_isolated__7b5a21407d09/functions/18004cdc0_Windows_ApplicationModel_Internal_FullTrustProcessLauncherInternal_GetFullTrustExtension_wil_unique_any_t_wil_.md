# Windows::ApplicationModel::Internal::FullTrustProcessLauncherInternal::GetFullTrustExtension(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18004cdc0`
- end: `0x18004d25d`
- name: `?GetFullTrustExtension@FullTrustProcessLauncherInternal@Internal@ApplicationModel@Windows@@AEAA?AV?$ComPtr@UIApplicationExtension@StateRepository@Internal@Windows@@@WRL@Microsoft@@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `1181`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, const WCHAR **, _QWORD *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004d2f0`
- `0x18004e200`

## callees

- `0x180004f70`
- `0x1800125f4`
- `0x180039d1c`
- `0x18003fd60`
- `0x18004cdc0`
- `0x1800cd010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004ce15`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004ce91`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004cee4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004cf89`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004d004`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004ce15`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004ce91`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004cee4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004cf89`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004d004`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18004ce38`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18004cf07`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18004cfc9`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18004ce38`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18004cf07`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18004cfc9`

## string_xrefs

- `0x18004cf82`: `Windows.Internal.StateRepository.ApplicationExtension`

## pseudocode

```c
// Hidden C++ exception states: #wind=11 #try_helpers=1
_QWORD *__fastcall Windows::ApplicationModel::Internal::FullTrustProcessLauncherInternal::GetFullTrustExtension(
        __int64 a1,
        _QWORD *a2,
        const WCHAR **a3,
        _QWORD *a4)
{
  HRESULT v7; // eax
  int v8; // edx
  unsigned int v9; // r8d
  int ActivationFactory; // eax
  unsigned int v11; // r8d
  wil::details::in1diag3 *v12; // rcx
  _QWORD *v13; // rdi
  __int64 v14; // r15
  const WCHAR *v15; // rcx
  unsigned __int64 v16; // rdx
  HRESULT v17; // eax
  int v18; // edx
  unsigned int v19; // r8d
  int v20; // eax
  wil::details::in1diag3 *v21; // rcx
  HRESULT v22; // eax
  int v23; // edx
  unsigned int v24; // r8d
  int v25; // eax
  wil::details::in1diag3 *v26; // rcx
  __int64 v27; // rdi
  __int64 (__fastcall *v28)(__int64, __int64, _QWORD, __int64 *); // r14
  __int64 v29; // rax
  int v30; // eax
  HRESULT v31; // eax
  int v32; // edx
  unsigned int v33; // r8d
  int v34; // eax
  wil::details::in1diag3 *v35; // rcx
  _QWORD *v36; // rbx
  __int64 v37; // rdi
  HRESULT v38; // eax
  int v39; // edx
  unsigned int v40; // r8d
  int v41; // eax
  wil::details::in1diag3 *v42; // rcx
  int v43; // eax
  int v44; // eax
  __int64 v45; // rcx
  _QWORD *v46; // rcx
  __int64 v47; // rcx
  __int64 v48; // rcx
  __int64 v49; // rcx
  _QWORD *v50; // rcx
  int v52; // [rsp+20h] [rbp-69h]
  _QWORD *v53; // [rsp+30h] [rbp-59h] BYREF
  int v54; // [rsp+38h] [rbp-51h] BYREF
  __int64 v55; // [rsp+40h] [rbp-49h] BYREF
  __int64 v56; // [rsp+48h] [rbp-41h] BYREF
  __int64 v57; // [rsp+50h] [rbp-39h] BYREF
  __int64 v58; // [rsp+58h] [rbp-31h] BYREF
  _QWORD *v59; // [rsp+60h] [rbp-29h] BYREF
  int v60; // [rsp+68h] [rbp-21h]
  _QWORD v61[2]; // [rsp+70h] [rbp-19h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+80h] [rbp-9h] BYREF
  HSTRING string; // [rsp+98h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v61[1] = a2;
  v60 = 0;
  v59 = 0;
  string = 0;
  v7 = WindowsCreateStringReference(L"Windows.Internal.StateRepository.Package", 0x28u, &hstringHeader, &string);
  if ( v7 < 0 )
    goto LABEL_36;
  ActivationFactory = RoGetActivationFactory(string, &GUID_0450ce77_af0d_40ac_93fd_1e5d48c89419, &v59);
  v12 = retaddr;
  if ( ActivationFactory < 0 )
    goto LABEL_37;
  v58 = 0;
  v13 = v59;
  v14 = *v59;
  v15 = *a3;
  string = 0;
  v16 = -1;
  do
    ++v16;
  while ( v15[v16] );
  if ( v16 > 0xFFFFFFFF )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v16, v11);
LABEL_36:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v7, v8, v9);
LABEL_37:
    wil::details::in1diag3::Throw_Hr(
      v12,
      (void *)0xD7,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\fulltrustprocesslauncher.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v52);
  }
  if ( (int)v16 + 1 < (unsigned int)v16 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v16, v11);
    __debugbreak();
  }
  v17 = WindowsCreateStringReference(v15, v16, &hstringHeader, &string);
  if ( v17 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v17, v18, v19);
LABEL_40:
    wil::details::in1diag3::Throw_Hr(
      v21,
      (void *)0xDA,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\fulltrustprocesslauncher.cpp",
      (const char *)(unsigned int)v20,
      v52);
  }
  v20 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64 *))(v14 + 176))(v13, string, &v58);
  v21 = retaddr;
  if ( v20 < 0 )
    goto LABEL_40;
  v57 = 0;
  string = 0;
  v22 = WindowsCreateStringReference(L"Windows.Internal.StateRepository.Application", 0x2Cu, &hstringHeader, &string);
  if ( v22 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v22, v23, v24);
LABEL_42:
    wil::details::in1diag3::Throw_Hr(
      v26,
      (void *)0xE0,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\fulltrustprocesslauncher.cpp",
      (const char *)(unsigned int)v25,
      v52);
  }
  v25 = RoGetActivationFactory(string, &GUID_07adcc9a_e505_48c2_b471_45af8561f6af, &v57);
  v26 = retaddr;
  if ( v25 < 0 )
    goto LABEL_42;
  v56 = 0;
  v27 = v57;
  v28 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64 *))(*(_QWORD *)v57 + 104LL);
  if ( a4[3] > 7u )
    a4 = (_QWORD *)*a4;
  v61[0] = a4;
  v29 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, v61);
  v30 = v28(v27, v58, *(_QWORD *)(v29 + 24), &v56);
  if ( v30 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xE6,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\fulltrustprocesslauncher.cpp",
      (const char *)(unsigned int)v30,
      v52);
  v53 = 0;
  string = 0;
  v31 = WindowsCreateStringReference(
          L"Windows.Internal.StateRepository.ApplicationExtension",
          0x35u,
          &hstringHeader,
          &string);
  if ( v31 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v31, v32, v33);
LABEL_45:
    wil::details::in1diag3::Throw_Hr(
      v35,
      (void *)0xEC,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\fulltrustprocesslauncher.cpp",
      (const char *)(unsigned int)v34,
      v52);
  }
  v34 = RoGetActivationFactory(string, &GUID_b94b62a2_4012_4b7e_a395_f21cc665fd12, &v53);
  v35 = retaddr;
  if ( v34 < 0 )
    goto LABEL_45;
  v55 = 0;
  v36 = v53;
  v37 = *v53;
  string = 0;
  v38 = WindowsCreateStringReference(L"windows.fullTrustProcess", 0x18u, &hstringHeader, &string);
  if ( v38 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v38, v39, v40);
LABEL_47:
    wil::details::in1diag3::Throw_Hr(
      v42,
      (void *)0xF2,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\fulltrustprocesslauncher.cpp",
      (const char *)(unsigned int)v41,
      v52);
  }
  v41 = (*(__int64 (__fastcall **)(_QWORD *, __int64, HSTRING, __int64 *))(v37 + 136))(v36, v56, string, &v55);
  v42 = retaddr;
  if ( v41 < 0 )
    goto LABEL_47;
  v54 = 0;
  v43 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v55 + 56LL))(v55, &v54);
  if ( v43 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xF5,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\fulltrustprocesslauncher.cpp",
      (const char *)(unsigned int)v43,
      v52);
  if ( v54 != 1 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xF6,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\fulltrustprocesslauncher.cpp",
      (const char *)0x80080204LL,
      v52);
  *a2 = 0;
  v60 = 1;
  v44 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD *))(*(_QWORD *)v55 + 48LL))(v55, 0, a2);
  if ( v44 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xF9,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\fulltrustprocesslauncher.cpp",
      (const char *)(unsigned int)v44,
      v52);
  v45 = v55;
  if ( v55 )
  {
    v55 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
  }
  v46 = v53;
  if ( v53 )
  {
    v53 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v46 + 16LL))(v46);
  }
  v47 = v56;
  if ( v56 )
  {
    v56 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
  }
  v48 = v57;
  if ( v57 )
  {
    v57 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
  }
  v49 = v58;
  if ( v58 )
  {
    v58 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
  }
  v50 = v59;
  if ( v59 )
  {
    v59 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v50 + 16LL))(v50);
  }
  return a2;
}

```

## disassembly

```asm
0x18004cdc0  push    rbp
0x18004cdc2  push    rbx
0x18004cdc3  push    rsi
0x18004cdc4  push    rdi
0x18004cdc5  push    r12
0x18004cdc7  push    r14
0x18004cdc9  push    r15
0x18004cdcb  lea     rbp, [rsp-27h]
0x18004cdd0  sub     rsp, 0B0h
0x18004cdd7  mov     rax, cs:__security_cookie
0x18004cdde  xor     rax, rsp
0x18004cde1  mov     [rbp+57h+var_40], rax
0x18004cde5  mov     rbx, r9
0x18004cde8  mov     r14, r8
0x18004cdeb  mov     rsi, rdx
0x18004cdee  mov     [rbp+57h+var_68], rdx
0x18004cdf2  xor     r12d, r12d
0x18004cdf5  mov     [rbp+57h+var_78], r12d
0x18004cdf9  mov     [rbp+57h+var_80], r12
0x18004cdfd  mov     [rbp+57h+string], r12
0x18004ce01  lea     r9, [rbp+57h+string]; string
0x18004ce05  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18004ce09  lea     edx, [r12+28h]; length
0x18004ce0e  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_Package@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x18004ce15  call    cs:__imp_WindowsCreateStringReference
0x18004ce1c  nop     dword ptr [rax+rax+00h]
0x18004ce21  test    eax, eax
0x18004ce23  js      loc_18004D17F
0x18004ce29  lea     r8, [rbp+57h+var_80]
0x18004ce2d  lea     rdx, _GUID_0450ce77_af0d_40ac_93fd_1e5d48c89419
0x18004ce34  mov     rcx, [rbp+57h+string]
0x18004ce38  call    cs:__imp_RoGetActivationFactory
0x18004ce3f  nop     dword ptr [rax+rax+00h]
0x18004ce44  mov     rcx, [rbp+5Fh]
0x18004ce48  test    eax, eax
0x18004ce4a  js      loc_18004D187
0x18004ce50  mov     [rbp+57h+var_88], r12
0x18004ce54  mov     rdi, [rbp+57h+var_80]
0x18004ce58  mov     r15, [rdi]
0x18004ce5b  mov     rcx, [r14]; sourceString
0x18004ce5e  mov     [rbp+57h+string], r12
0x18004ce62  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18004ce66  inc     rdx; int
0x18004ce69  cmp     [rcx+rdx*2], r12w
0x18004ce6e  jnz     short loc_18004CE66
0x18004ce70  mov     eax, 0FFFFFFFFh
0x18004ce75  cmp     rdx, rax
0x18004ce78  ja      loc_18004D174
0x18004ce7e  lea     eax, [rdx+1]
0x18004ce81  cmp     eax, edx
0x18004ce83  jb      loc_18004D19C
0x18004ce89  lea     r9, [rbp+57h+string]; string
0x18004ce8d  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18004ce91  call    cs:__imp_WindowsCreateStringReference
0x18004ce98  nop     dword ptr [rax+rax+00h]
0x18004ce9d  test    eax, eax
0x18004ce9f  js      loc_18004D1A7
0x18004cea5  lea     r8, [rbp+57h+var_88]
0x18004cea9  mov     rdx, [rbp+57h+string]
0x18004cead  mov     rcx, rdi
0x18004ceb0  mov     rax, [r15+0B0h]
0x18004ceb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cebc  mov     rcx, [rbp+5Fh]
0x18004cec0  test    eax, eax
0x18004cec2  js      loc_18004D1AF
0x18004cec8  mov     [rbp+57h+var_90], r12
0x18004cecc  mov     [rbp+57h+string], r12
0x18004ced0  lea     r9, [rbp+57h+string]; string
0x18004ced4  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18004ced8  mov     edx, 2Ch ; ','; length
0x18004cedd  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_Application@@3QBGB; "Windows.Internal.StateRepository.Applic"...
0x18004cee4  call    cs:__imp_WindowsCreateStringReference
0x18004ceeb  nop     dword ptr [rax+rax+00h]
0x18004cef0  test    eax, eax
0x18004cef2  js      loc_18004D1C4
0x18004cef8  lea     r8, [rbp+57h+var_90]
0x18004cefc  lea     rdx, _GUID_07adcc9a_e505_48c2_b471_45af8561f6af
0x18004cf03  mov     rcx, [rbp+57h+string]
0x18004cf07  call    cs:__imp_RoGetActivationFactory
0x18004cf0e  nop     dword ptr [rax+rax+00h]
0x18004cf13  mov     rcx, [rbp+5Fh]
0x18004cf17  test    eax, eax
0x18004cf19  js      loc_18004D1CC
0x18004cf1f  mov     [rbp+57h+var_98], r12
0x18004cf23  mov     rdi, [rbp+57h+var_90]
0x18004cf27  mov     rax, [rdi]
0x18004cf2a  mov     r14, [rax+68h]
0x18004cf2e  cmp     qword ptr [rbx+18h], 7
0x18004cf33  jbe     short loc_18004CF38
0x18004cf35  mov     rbx, [rbx]
0x18004cf38  mov     [rbp+57h+var_70], rbx
0x18004cf3c  lea     rdx, [rbp+57h+var_70]
0x18004cf40  lea     rcx, [rbp+57h+hstringHeader]
0x18004cf44  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18004cf49  nop
0x18004cf4a  lea     r9, [rbp+57h+var_98]
0x18004cf4e  mov     r8, [rax+18h]
0x18004cf52  mov     rdx, [rbp+57h+var_88]
0x18004cf56  mov     rcx, rdi
0x18004cf59  mov     rax, r14
0x18004cf5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cf61  mov     rcx, [rbp+5Fh]; this
0x18004cf65  test    eax, eax
0x18004cf67  js      loc_18004D1E1
0x18004cf6d  mov     [rbp+57h+var_B0], r12
0x18004cf71  mov     [rbp+57h+string], r12
0x18004cf75  lea     r9, [rbp+57h+string]; string
0x18004cf79  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18004cf7d  mov     edx, 35h ; '5'; length
0x18004cf82  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_ApplicationExtension@@3QBGB; "Windows.Internal.StateRepository.Applic"...
0x18004cf89  call    cs:__imp_WindowsCreateStringReference
0x18004cf90  nop     dword ptr [rax+rax+00h]
0x18004cf95  test    eax, eax
0x18004cf97  js      loc_18004D1F6
0x18004cf9d  mov     rbx, [rbp+57h+string]
0x18004cfa1  mov     rcx, [rbp+57h+var_B0]
0x18004cfa5  test    rcx, rcx
0x18004cfa8  jz      short loc_18004CFBB
0x18004cfaa  mov     [rbp+57h+var_B0], r12
0x18004cfae  mov     rax, [rcx]
0x18004cfb1  mov     rax, [rax+10h]
0x18004cfb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cfba  nop
0x18004cfbb  lea     r8, [rbp+57h+var_B0]
0x18004cfbf  lea     rdx, _GUID_b94b62a2_4012_4b7e_a395_f21cc665fd12
0x18004cfc6  mov     rcx, rbx
0x18004cfc9  call    cs:__imp_RoGetActivationFactory
0x18004cfd0  nop     dword ptr [rax+rax+00h]
0x18004cfd5  mov     rcx, [rbp+5Fh]
0x18004cfd9  test    eax, eax
0x18004cfdb  js      loc_18004D1FE
0x18004cfe1  mov     [rbp+57h+var_A0], r12
0x18004cfe5  mov     rbx, [rbp+57h+var_B0]
0x18004cfe9  mov     rdi, [rbx]
0x18004cfec  mov     [rbp+57h+string], r12
0x18004cff0  lea     r9, [rbp+57h+string]; string
0x18004cff4  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18004cff8  mov     edx, 18h; length
0x18004cffd  lea     rcx, aWindowsFulltru; "windows.fullTrustProcess"
0x18004d004  call    cs:__imp_WindowsCreateStringReference
0x18004d00b  nop     dword ptr [rax+rax+00h]
0x18004d010  test    eax, eax
0x18004d012  js      loc_18004D213
0x18004d018  lea     r9, [rbp+57h+var_A0]
0x18004d01c  mov     r8, [rbp+57h+string]
0x18004d020  mov     rdx, [rbp+57h+var_98]
0x18004d024  mov     rcx, rbx
0x18004d027  mov     rax, [rdi+88h]
0x18004d02e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d033  mov     rcx, [rbp+5Fh]
0x18004d037  test    eax, eax
0x18004d039  js      loc_18004D21B
0x18004d03f  mov     [rbp+57h+var_A8], r12d
0x18004d043  mov     rcx, [rbp+57h+var_A0]
0x18004d047  mov     rax, [rcx]
0x18004d04a  lea     rdx, [rbp+57h+var_A8]
0x18004d04e  mov     rax, [rax+38h]
0x18004d052  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d057  mov     rcx, [rbp+5Fh]; this
0x18004d05b  test    eax, eax
0x18004d05d  js      loc_18004D230
0x18004d063  cmp     [rbp+57h+var_A8], 1
0x18004d067  setz    al
0x18004d06a  mov     rcx, [rbp+5Fh]; this
0x18004d06e  test    al, al
0x18004d070  jz      loc_18004D245
0x18004d076  mov     [rsi], r12
0x18004d079  mov     [rbp+57h+var_78], 1
0x18004d080  mov     rcx, [rbp+57h+var_A0]
0x18004d084  mov     rax, [rcx]
0x18004d087  mov     r8, rsi
0x18004d08a  xor     edx, edx
0x18004d08c  mov     rax, [rax+30h]
0x18004d090  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d095  mov     rcx, [rbp+5Fh]; this
0x18004d099  test    eax, eax
0x18004d09b  js      loc_18004D15F
0x18004d0a1  mov     rcx, [rbp+57h+var_A0]
0x18004d0a5  test    rcx, rcx
0x18004d0a8  jz      short loc_18004D0BB
0x18004d0aa  mov     [rbp+57h+var_A0], r12
0x18004d0ae  mov     rax, [rcx]
0x18004d0b1  mov     rax, [rax+10h]
0x18004d0b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d0ba  nop
0x18004d0bb  mov     rcx, [rbp+57h+var_B0]
0x18004d0bf  test    rcx, rcx
0x18004d0c2  jz      short loc_18004D0D5
0x18004d0c4  mov     [rbp+57h+var_B0], r12
0x18004d0c8  mov     rax, [rcx]
0x18004d0cb  mov     rax, [rax+10h]
0x18004d0cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d0d4  nop
0x18004d0d5  mov     rcx, [rbp+57h+var_98]
0x18004d0d9  test    rcx, rcx
0x18004d0dc  jz      short loc_18004D0EF
0x18004d0de  mov     [rbp+57h+var_98], r12
0x18004d0e2  mov     rax, [rcx]
0x18004d0e5  mov     rax, [rax+10h]
0x18004d0e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d0ee  nop
0x18004d0ef  mov     rcx, [rbp+57h+var_90]
0x18004d0f3  test    rcx, rcx
0x18004d0f6  jz      short loc_18004D109
0x18004d0f8  mov     [rbp+57h+var_90], r12
0x18004d0fc  mov     rax, [rcx]
0x18004d0ff  mov     rax, [rax+10h]
0x18004d103  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d108  nop
0x18004d109  mov     rcx, [rbp+57h+var_88]
0x18004d10d  test    rcx, rcx
0x18004d110  jz      short loc_18004D123
0x18004d112  mov     [rbp+57h+var_88], r12
0x18004d116  mov     rax, [rcx]
0x18004d119  mov     rax, [rax+10h]
0x18004d11d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d122  nop
0x18004d123  mov     rcx, [rbp+57h+var_80]
0x18004d127  test    rcx, rcx
0x18004d12a  jz      short loc_18004D13D
0x18004d12c  mov     [rbp+57h+var_80], r12
0x18004d130  mov     rdx, [rcx]
0x18004d133  mov     rax, [rdx+10h]
0x18004d137  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d13c  nop
0x18004d13d  mov     rax, rsi
0x18004d140  mov     rcx, [rbp+57h+var_40]
0x18004d144  xor     rcx, rsp; StackCookie
0x18004d147  call    __security_check_cookie
0x18004d14c  add     rsp, 0B0h
0x18004d153  pop     r15
0x18004d155  pop     r14
0x18004d157  pop     r12
0x18004d159  pop     rdi
0x18004d15a  pop     rsi
0x18004d15b  pop     rbx
0x18004d15c  pop     rbp
0x18004d15d  retn
0x18004d15f  mov     r9d, eax; char *
0x18004d162  lea     r8, aOnecoreBaseApp_64; "onecore\\base\\appmodel\\execmodel\\des"...
0x18004d169  mov     edx, 0F9h; void *
0x18004d16e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004d174  mov     ecx, 80070216h; this
0x18004d179  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18004d17e  nop
0x18004d17f  mov     ecx, eax; this
0x18004d181  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18004d186  nop
0x18004d187  mov     r9d, eax; char *
0x18004d18a  lea     r8, aOnecoreBaseApp_64; "onecore\\base\\appmodel\\execmodel\\des"...
0x18004d191  mov     edx, 0D7h; void *
0x18004d196  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004d19c  mov     ecx, 80070216h; this
0x18004d1a1  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18004d1a6  int     3; Trap to Debugger
0x18004d1a7  mov     ecx, eax; this
0x18004d1a9  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18004d1ae  nop
0x18004d1af  mov     r9d, eax; char *
0x18004d1b2  lea     r8, aOnecoreBaseApp_64; "onecore\\base\\appmodel\\execmodel\\des"...
0x18004d1b9  mov     edx, 0DAh; void *
0x18004d1be  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004d1c4  mov     ecx, eax; this
0x18004d1c6  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18004d1cb  nop
0x18004d1cc  mov     r9d, eax; char *
0x18004d1cf  lea     r8, aOnecoreBaseApp_64; "onecore\\base\\appmodel\\execmodel\\des"...
0x18004d1d6  mov     edx, 0E0h; void *
0x18004d1db  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004d1e1  mov     r9d, eax; char *
0x18004d1e4  lea     r8, aOnecoreBaseApp_64; "onecore\\base\\appmodel\\execmodel\\des"...
0x18004d1eb  mov     edx, 0E6h; void *
0x18004d1f0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004d1f6  mov     ecx, eax; this
0x18004d1f8  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18004d1fd  nop
0x18004d1fe  mov     r9d, eax; char *
0x18004d201  lea     r8, aOnecoreBaseApp_64; "onecore\\base\\appmodel\\execmodel\\des"...
0x18004d208  mov     edx, 0ECh; void *
0x18004d20d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004d213  mov     ecx, eax; this
0x18004d215  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18004d21a  nop
0x18004d21b  mov     r9d, eax; char *
0x18004d21e  lea     r8, aOnecoreBaseApp_64; "onecore\\base\\appmodel\\execmodel\\des"...
0x18004d225  mov     edx, 0F2h; void *
0x18004d22a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004d230  mov     r9d, eax; char *
0x18004d233  lea     r8, aOnecoreBaseApp_64; "onecore\\base\\appmodel\\execmodel\\des"...
0x18004d23a  mov     edx, 0F5h; void *
0x18004d23f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004d245  mov     r9d, 80080204h; char *
0x18004d24b  lea     r8, aOnecoreBaseApp_64; "onecore\\base\\appmodel\\execmodel\\des"...
0x18004d252  mov     edx, 0F6h; void *
0x18004d257  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
