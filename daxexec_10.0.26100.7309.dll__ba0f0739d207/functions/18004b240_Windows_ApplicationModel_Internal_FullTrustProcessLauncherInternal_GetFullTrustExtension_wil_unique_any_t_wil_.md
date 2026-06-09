# Windows::ApplicationModel::Internal::FullTrustProcessLauncherInternal::GetFullTrustExtension(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18004b240`
- end: `0x18004b6e6`
- name: `?GetFullTrustExtension@FullTrustProcessLauncherInternal@Internal@ApplicationModel@Windows@@AEAA?AV?$ComPtr@UIApplicationExtension@StateRepository@Internal@Windows@@@WRL@Microsoft@@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `1190`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004b790`
- `0x18004c680`

## callees

- `0x1800053a0`
- `0x180010a84`
- `0x180038318`
- `0x18003ddd0`
- `0x18004b240`
- `0x1800cc010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004b295`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004b31b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004b36a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004b40f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004b491`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004b295`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004b31b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004b36a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004b40f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004b491`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18004b2b8`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18004b38d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18004b44f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18004b2b8`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18004b38d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18004b44f`

## string_xrefs

- `0x18004b408`: `Windows.Internal.StateRepository.ApplicationExtension`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
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
  __int64 v13; // rbx
  __int64 (__fastcall *v14)(__int64, HSTRING, __int64 *); // r15
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
  __int64 v27; // rbx
  __int64 (__fastcall *v28)(__int64, __int64, _QWORD, __int64 *); // r14
  __int64 v29; // rax
  int v30; // eax
  HRESULT v31; // eax
  int v32; // edx
  unsigned int v33; // r8d
  int v34; // eax
  wil::details::in1diag3 *v35; // rcx
  __int64 v36; // rbx
  __int64 (__fastcall *v37)(__int64, __int64, HSTRING, __int64 *); // rdi
  HRESULT v38; // eax
  int v39; // edx
  unsigned int v40; // r8d
  int v41; // eax
  wil::details::in1diag3 *v42; // rcx
  int v43; // eax
  int v44; // eax
  __int64 v45; // rcx
  __int64 v46; // rcx
  __int64 v47; // rcx
  __int64 v48; // rcx
  __int64 v49; // rcx
  __int64 v50; // rcx
  int v52; // [rsp+20h] [rbp-69h]
  __int64 v53; // [rsp+30h] [rbp-59h] BYREF
  int v54; // [rsp+38h] [rbp-51h] BYREF
  __int64 v55; // [rsp+40h] [rbp-49h] BYREF
  __int64 v56; // [rsp+48h] [rbp-41h] BYREF
  __int64 v57; // [rsp+50h] [rbp-39h] BYREF
  __int64 v58; // [rsp+58h] [rbp-31h] BYREF
  __int64 v59; // [rsp+60h] [rbp-29h] BYREF
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
  v14 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v59 + 176LL);
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
LABEL_39:
    wil::details::in1diag3::Throw_Hr(
      v21,
      (void *)0xDA,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\fulltrustprocesslauncher.cpp",
      (const char *)(unsigned int)v20,
      v52);
  }
  v20 = v14(v13, string, &v58);
  v21 = retaddr;
  if ( v20 < 0 )
    goto LABEL_39;
  v57 = 0;
  string = 0;
  v22 = WindowsCreateStringReference(L"Windows.Internal.StateRepository.Application", 0x2Cu, &hstringHeader, &string);
  if ( v22 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v22, v23, v24);
LABEL_41:
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
    goto LABEL_41;
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
LABEL_44:
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
    goto LABEL_44;
  v55 = 0;
  v36 = v53;
  v37 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING, __int64 *))(*(_QWORD *)v53 + 136LL);
  string = 0;
  v38 = WindowsCreateStringReference(L"windows.fullTrustProcess", 0x18u, &hstringHeader, &string);
  if ( v38 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v38, v39, v40);
LABEL_46:
    wil::details::in1diag3::Throw_Hr(
      v42,
      (void *)0xF2,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\fulltrustprocesslauncher.cpp",
      (const char *)(unsigned int)v41,
      v52);
  }
  v41 = v37(v36, v56, string, &v55);
  v42 = retaddr;
  if ( v41 < 0 )
    goto LABEL_46;
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
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
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
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
  }
  return a2;
}

```

## disassembly

```asm
0x18004b240  push    rbp
0x18004b242  push    rbx
0x18004b243  push    rsi
0x18004b244  push    rdi
0x18004b245  push    r12
0x18004b247  push    r14
0x18004b249  push    r15
0x18004b24b  lea     rbp, [rsp-27h]
0x18004b250  sub     rsp, 0B0h
0x18004b257  mov     rax, cs:__security_cookie
0x18004b25e  xor     rax, rsp
0x18004b261  mov     [rbp+57h+var_40], rax
0x18004b265  mov     rdi, r9
0x18004b268  mov     r14, r8
0x18004b26b  mov     rsi, rdx
0x18004b26e  mov     [rbp+57h+var_68], rdx
0x18004b272  xor     r12d, r12d
0x18004b275  mov     [rbp+57h+var_78], r12d
0x18004b279  mov     [rbp+57h+var_80], r12
0x18004b27d  mov     [rbp+57h+string], r12
0x18004b281  lea     r9, [rbp+57h+string]; string
0x18004b285  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18004b289  lea     edx, [r12+28h]; length
0x18004b28e  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_Package@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x18004b295  call    cs:__imp_WindowsCreateStringReference
0x18004b29c  nop     dword ptr [rax+rax+00h]
0x18004b2a1  test    eax, eax
0x18004b2a3  js      loc_18004B5FE
0x18004b2a9  lea     r8, [rbp+57h+var_80]
0x18004b2ad  lea     rdx, _GUID_0450ce77_af0d_40ac_93fd_1e5d48c89419
0x18004b2b4  mov     rcx, [rbp+57h+string]
0x18004b2b8  call    cs:__imp_RoGetActivationFactory
0x18004b2bf  nop     dword ptr [rax+rax+00h]
0x18004b2c4  mov     rcx, [rbp+5Fh]
0x18004b2c8  test    eax, eax
0x18004b2ca  js      loc_18004B606
0x18004b2d0  mov     [rbp+57h+var_88], r12
0x18004b2d4  mov     rbx, [rbp+57h+var_80]
0x18004b2d8  mov     rax, [rbx]
0x18004b2db  mov     r15, [rax+0B0h]
0x18004b2e2  mov     rcx, [r14]; sourceString
0x18004b2e5  mov     [rbp+57h+string], r12
0x18004b2e9  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18004b2ed  inc     rdx; int
0x18004b2f0  cmp     [rcx+rdx*2], r12w
0x18004b2f5  jnz     short loc_18004B2ED
0x18004b2f7  mov     eax, 0FFFFFFFFh
0x18004b2fc  cmp     rdx, rax
0x18004b2ff  ja      loc_18004B5F3
0x18004b305  lea     eax, [rdx+1]
0x18004b308  cmp     eax, edx
0x18004b30a  jb      loc_18004B5E8
0x18004b310  cmova   edx, edx; length
0x18004b313  lea     r9, [rbp+57h+string]; string
0x18004b317  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18004b31b  call    cs:__imp_WindowsCreateStringReference
0x18004b322  nop     dword ptr [rax+rax+00h]
0x18004b327  test    eax, eax
0x18004b329  js      loc_18004B61B
0x18004b32f  lea     r8, [rbp+57h+var_88]
0x18004b333  mov     rdx, [rbp+57h+string]
0x18004b337  mov     rcx, rbx
0x18004b33a  mov     rax, r15
0x18004b33d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b342  mov     rcx, [rbp+5Fh]
0x18004b346  test    eax, eax
0x18004b348  js      loc_18004B623
0x18004b34e  mov     [rbp+57h+var_90], r12
0x18004b352  mov     [rbp+57h+string], r12
0x18004b356  lea     r9, [rbp+57h+string]; string
0x18004b35a  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18004b35e  mov     edx, 2Ch ; ','; length
0x18004b363  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_Application@@3QBGB; "Windows.Internal.StateRepository.Applic"...
0x18004b36a  call    cs:__imp_WindowsCreateStringReference
0x18004b371  nop     dword ptr [rax+rax+00h]
0x18004b376  test    eax, eax
0x18004b378  js      loc_18004B638
0x18004b37e  lea     r8, [rbp+57h+var_90]
0x18004b382  lea     rdx, _GUID_07adcc9a_e505_48c2_b471_45af8561f6af
0x18004b389  mov     rcx, [rbp+57h+string]
0x18004b38d  call    cs:__imp_RoGetActivationFactory
0x18004b394  nop     dword ptr [rax+rax+00h]
0x18004b399  mov     rcx, [rbp+5Fh]
0x18004b39d  test    eax, eax
0x18004b39f  js      loc_18004B640
0x18004b3a5  mov     [rbp+57h+var_98], r12
0x18004b3a9  mov     rbx, [rbp+57h+var_90]
0x18004b3ad  mov     rax, [rbx]
0x18004b3b0  mov     r14, [rax+68h]
0x18004b3b4  cmp     qword ptr [rdi+18h], 7
0x18004b3b9  jbe     short loc_18004B3BE
0x18004b3bb  mov     rdi, [rdi]
0x18004b3be  mov     [rbp+57h+var_70], rdi
0x18004b3c2  lea     rdx, [rbp+57h+var_70]
0x18004b3c6  lea     rcx, [rbp+57h+hstringHeader]
0x18004b3ca  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18004b3cf  nop
0x18004b3d0  lea     r9, [rbp+57h+var_98]
0x18004b3d4  mov     r8, [rax+18h]
0x18004b3d8  mov     rdx, [rbp+57h+var_88]
0x18004b3dc  mov     rcx, rbx
0x18004b3df  mov     rax, r14
0x18004b3e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b3e7  mov     rcx, [rbp+5Fh]; this
0x18004b3eb  test    eax, eax
0x18004b3ed  js      loc_18004B655
0x18004b3f3  mov     [rbp+57h+var_B0], r12
0x18004b3f7  mov     [rbp+57h+string], r12
0x18004b3fb  lea     r9, [rbp+57h+string]; string
0x18004b3ff  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18004b403  mov     edx, 35h ; '5'; length
0x18004b408  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_ApplicationExtension@@3QBGB; "Windows.Internal.StateRepository.Applic"...
0x18004b40f  call    cs:__imp_WindowsCreateStringReference
0x18004b416  nop     dword ptr [rax+rax+00h]
0x18004b41b  test    eax, eax
0x18004b41d  js      loc_18004B66A
0x18004b423  mov     rbx, [rbp+57h+string]
0x18004b427  mov     rcx, [rbp+57h+var_B0]
0x18004b42b  test    rcx, rcx
0x18004b42e  jz      short loc_18004B441
0x18004b430  mov     [rbp+57h+var_B0], r12
0x18004b434  mov     rax, [rcx]
0x18004b437  mov     rax, [rax+10h]
0x18004b43b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b440  nop
0x18004b441  lea     r8, [rbp+57h+var_B0]
0x18004b445  lea     rdx, _GUID_b94b62a2_4012_4b7e_a395_f21cc665fd12
0x18004b44c  mov     rcx, rbx
0x18004b44f  call    cs:__imp_RoGetActivationFactory
0x18004b456  nop     dword ptr [rax+rax+00h]
0x18004b45b  mov     rcx, [rbp+5Fh]
0x18004b45f  test    eax, eax
0x18004b461  js      loc_18004B672
0x18004b467  mov     [rbp+57h+var_A0], r12
0x18004b46b  mov     rbx, [rbp+57h+var_B0]
0x18004b46f  mov     rax, [rbx]
0x18004b472  mov     rdi, [rax+88h]
0x18004b479  mov     [rbp+57h+string], r12
0x18004b47d  lea     r9, [rbp+57h+string]; string
0x18004b481  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18004b485  mov     edx, 18h; length
0x18004b48a  lea     rcx, aWindowsFulltru; "windows.fullTrustProcess"
0x18004b491  call    cs:__imp_WindowsCreateStringReference
0x18004b498  nop     dword ptr [rax+rax+00h]
0x18004b49d  test    eax, eax
0x18004b49f  js      loc_18004B687
0x18004b4a5  lea     r9, [rbp+57h+var_A0]
0x18004b4a9  mov     r8, [rbp+57h+string]
0x18004b4ad  mov     rdx, [rbp+57h+var_98]
0x18004b4b1  mov     rcx, rbx
0x18004b4b4  mov     rax, rdi
0x18004b4b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b4bc  mov     rcx, [rbp+5Fh]
0x18004b4c0  test    eax, eax
0x18004b4c2  js      loc_18004B68F
0x18004b4c8  mov     [rbp+57h+var_A8], r12d
0x18004b4cc  mov     rcx, [rbp+57h+var_A0]
0x18004b4d0  mov     rax, [rcx]
0x18004b4d3  lea     rdx, [rbp+57h+var_A8]
0x18004b4d7  mov     rax, [rax+38h]
0x18004b4db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b4e0  mov     rcx, [rbp+5Fh]; this
0x18004b4e4  test    eax, eax
0x18004b4e6  js      loc_18004B6A4
0x18004b4ec  cmp     [rbp+57h+var_A8], 1
0x18004b4f0  setz    al
0x18004b4f3  mov     rcx, [rbp+5Fh]; this
0x18004b4f7  test    al, al
0x18004b4f9  jz      loc_18004B6B9
0x18004b4ff  mov     [rsi], r12
0x18004b502  mov     [rbp+57h+var_78], 1
0x18004b509  mov     rcx, [rbp+57h+var_A0]
0x18004b50d  mov     rax, [rcx]
0x18004b510  mov     r8, rsi
0x18004b513  xor     edx, edx
0x18004b515  mov     rax, [rax+30h]
0x18004b519  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b51e  mov     rcx, [rbp+5Fh]; this
0x18004b522  test    eax, eax
0x18004b524  js      loc_18004B6D1
0x18004b52a  mov     rcx, [rbp+57h+var_A0]
0x18004b52e  test    rcx, rcx
0x18004b531  jz      short loc_18004B544
0x18004b533  mov     [rbp+57h+var_A0], r12
0x18004b537  mov     rax, [rcx]
0x18004b53a  mov     rax, [rax+10h]
0x18004b53e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b543  nop
0x18004b544  mov     rcx, [rbp+57h+var_B0]
0x18004b548  test    rcx, rcx
0x18004b54b  jz      short loc_18004B55E
0x18004b54d  mov     [rbp+57h+var_B0], r12
0x18004b551  mov     rax, [rcx]
0x18004b554  mov     rax, [rax+10h]
0x18004b558  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b55d  nop
0x18004b55e  mov     rcx, [rbp+57h+var_98]
0x18004b562  test    rcx, rcx
0x18004b565  jz      short loc_18004B578
0x18004b567  mov     [rbp+57h+var_98], r12
0x18004b56b  mov     rax, [rcx]
0x18004b56e  mov     rax, [rax+10h]
0x18004b572  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b577  nop
0x18004b578  mov     rcx, [rbp+57h+var_90]
0x18004b57c  test    rcx, rcx
0x18004b57f  jz      short loc_18004B592
0x18004b581  mov     [rbp+57h+var_90], r12
0x18004b585  mov     rax, [rcx]
0x18004b588  mov     rax, [rax+10h]
0x18004b58c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b591  nop
0x18004b592  mov     rcx, [rbp+57h+var_88]
0x18004b596  test    rcx, rcx
0x18004b599  jz      short loc_18004B5AC
0x18004b59b  mov     [rbp+57h+var_88], r12
0x18004b59f  mov     rax, [rcx]
0x18004b5a2  mov     rax, [rax+10h]
0x18004b5a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b5ab  nop
0x18004b5ac  mov     rcx, [rbp+57h+var_80]
0x18004b5b0  test    rcx, rcx
0x18004b5b3  jz      short loc_18004B5C6
0x18004b5b5  mov     [rbp+57h+var_80], r12
0x18004b5b9  mov     rdx, [rcx]
0x18004b5bc  mov     rax, [rdx+10h]
0x18004b5c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b5c5  nop
0x18004b5c6  mov     rax, rsi
0x18004b5c9  mov     rcx, [rbp+57h+var_40]
0x18004b5cd  xor     rcx, rsp; StackCookie
0x18004b5d0  call    __security_check_cookie
0x18004b5d5  add     rsp, 0B0h
0x18004b5dc  pop     r15
0x18004b5de  pop     r14
0x18004b5e0  pop     r12
0x18004b5e2  pop     rdi
0x18004b5e3  pop     rsi
0x18004b5e4  pop     rbx
0x18004b5e5  pop     rbp
0x18004b5e6  retn
0x18004b5e8  mov     ecx, 80070216h; this
0x18004b5ed  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18004b5f2  int     3; Trap to Debugger
0x18004b5f3  mov     ecx, 80070216h; this
0x18004b5f8  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18004b5fd  nop
0x18004b5fe  mov     ecx, eax; this
0x18004b600  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18004b605  nop
0x18004b606  mov     r9d, eax; char *
0x18004b609  lea     r8, aOnecoreBaseApp_63; "onecore\\base\\appmodel\\execmodel\\des"...
0x18004b610  mov     edx, 0D7h; void *
0x18004b615  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004b61b  mov     ecx, eax; this
0x18004b61d  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18004b622  nop
0x18004b623  mov     r9d, eax; char *
0x18004b626  lea     r8, aOnecoreBaseApp_63; "onecore\\base\\appmodel\\execmodel\\des"...
0x18004b62d  mov     edx, 0DAh; void *
0x18004b632  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004b638  mov     ecx, eax; this
0x18004b63a  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18004b63f  nop
0x18004b640  mov     r9d, eax; char *
0x18004b643  lea     r8, aOnecoreBaseApp_63; "onecore\\base\\appmodel\\execmodel\\des"...
0x18004b64a  mov     edx, 0E0h; void *
0x18004b64f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004b655  mov     r9d, eax; char *
0x18004b658  lea     r8, aOnecoreBaseApp_63; "onecore\\base\\appmodel\\execmodel\\des"...
0x18004b65f  mov     edx, 0E6h; void *
0x18004b664  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004b66a  mov     ecx, eax; this
0x18004b66c  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18004b671  nop
0x18004b672  mov     r9d, eax; char *
0x18004b675  lea     r8, aOnecoreBaseApp_63; "onecore\\base\\appmodel\\execmodel\\des"...
0x18004b67c  mov     edx, 0ECh; void *
0x18004b681  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004b687  mov     ecx, eax; this
0x18004b689  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18004b68e  nop
0x18004b68f  mov     r9d, eax; char *
0x18004b692  lea     r8, aOnecoreBaseApp_63; "onecore\\base\\appmodel\\execmodel\\des"...
0x18004b699  mov     edx, 0F2h; void *
0x18004b69e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004b6a4  mov     r9d, eax; char *
0x18004b6a7  lea     r8, aOnecoreBaseApp_63; "onecore\\base\\appmodel\\execmodel\\des"...
0x18004b6ae  mov     edx, 0F5h; void *
0x18004b6b3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004b6b9  mov     r9d, 80080204h; char *
0x18004b6bf  lea     r8, aOnecoreBaseApp_63; "onecore\\base\\appmodel\\execmodel\\des"...
0x18004b6c6  mov     edx, 0F6h; void *
0x18004b6cb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004b6d1  mov     r9d, eax; char *
0x18004b6d4  lea     r8, aOnecoreBaseApp_63; "onecore\\base\\appmodel\\execmodel\\des"...
0x18004b6db  mov     edx, 0F9h; void *
0x18004b6e0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
