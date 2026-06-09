# Windows::ApplicationModel::Internal::FullTrustProcessLauncherInternal::RetrieveManifestParameterGroup(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18004c680`
- end: `0x18004cc21`
- name: `?RetrieveManifestParameterGroup@FullTrustProcessLauncherInternal@Internal@ApplicationModel@Windows@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV56@1@Z`
- size: `1441`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004ba10`

## callees

- `0x1800053a0`
- `0x18000c37c`
- `0x180010a84`
- `0x18003a6f8`
- `0x18003ddd0`
- `0x18004a61c`
- `0x18004ab58`
- `0x18004b240`
- `0x18004c028`
- `0x18004c680`
- `0x1800cc010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18004cae9`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18004cb77`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18004cae9`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18004cb77`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004c79f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004c79f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004c71a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ca80`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004c71a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ca80`
- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-3!SRDictionaryToPropertySet` at `0x18004c735`
- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-3!SRDictionaryToPropertySet` at `0x18004c735`

## pseudocode

```c
// Hidden C++ exception states: #wind=30
_QWORD *__fastcall Windows::ApplicationModel::Internal::FullTrustProcessLauncherInternal::RetrieveManifestParameterGroup(
        __int64 a1,
        _QWORD *a2,
        const WCHAR **a3,
        _QWORD *a4,
        HSTRING a5)
{
  __int64 v6; // rax
  int v7; // eax
  void *v8; // rcx
  int v9; // eax
  int v10; // eax
  __int64 v11; // rbx
  int (__fastcall *v12)(__int64, HSTRING, _QWORD); // rsi
  HRESULT v13; // eax
  int v14; // edx
  unsigned int v15; // r8d
  const unsigned __int16 *v16; // rdx
  int v17; // eax
  int v18; // eax
  int v19; // eax
  int v20; // eax
  char v21; // bl
  int v22; // eax
  unsigned int i; // esi
  const unsigned __int16 *v24; // rdx
  int v25; // eax
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 (__fastcall ***v28)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rcx
  __int64 (__fastcall ***v32)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v33; // rcx
  __int64 (__fastcall ***v34)(_QWORD, GUID *, _QWORD *); // rcx
  void *v35; // rcx
  __int64 v36; // rcx
  Microsoft::WRL::Wrappers::HStringReference *v38; // rax
  HSTRING v39; // rax
  unsigned int v40; // eax
  Microsoft::WRL::Wrappers::HStringReference *v41; // rax
  HSTRING v42; // rax
  unsigned int v43; // eax
  __int64 v44; // [rsp+20h] [rbp-71h] BYREF
  __int64 v45; // [rsp+28h] [rbp-69h] BYREF
  unsigned int v46; // [rsp+30h] [rbp-61h] BYREF
  __int64 (__fastcall ***v47)(_QWORD, GUID *, __int64 *); // [rsp+38h] [rbp-59h] BYREF
  __int64 v48; // [rsp+40h] [rbp-51h] BYREF
  __int64 v49; // [rsp+48h] [rbp-49h] BYREF
  __int64 v50; // [rsp+50h] [rbp-41h] BYREF
  __int64 (__fastcall ***v51)(_QWORD, GUID *, __int64 *); // [rsp+58h] [rbp-39h] BYREF
  __int64 v52; // [rsp+60h] [rbp-31h] BYREF
  __int64 (__fastcall ***v53)(_QWORD, GUID *, __int64 *); // [rsp+68h] [rbp-29h] BYREF
  LPVOID pv; // [rsp+70h] [rbp-21h] BYREF
  int v55; // [rsp+78h] [rbp-19h]
  __int64 v56; // [rsp+80h] [rbp-11h] BYREF
  _QWORD v57[2]; // [rsp+88h] [rbp-9h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+98h] [rbp+7h] BYREF
  HSTRING string; // [rsp+B0h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+57h]

  v57[1] = a2;
  v55 = 0;
  Windows::ApplicationModel::Internal::FullTrustProcessLauncherInternal::GetFullTrustExtension(a1, v57, a3, a4);
  v46 = 0;
  pv = 0;
  v6 = *(_QWORD *)v57[0];
  hstringHeader.Reserved.Reserved1 = &pv;
  *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = 0;
  hstringHeader.Reserved.Reserved2[16] = 1;
  v7 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *, char *))(v6 + 512))(
         v57[0],
         &v46,
         &hstringHeader.Reserved.Reserved2[8]);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x114,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\fulltrustprocesslauncher.cpp",
      (const char *)(unsigned int)v7,
      v44);
  if ( hstringHeader.Reserved.Reserved2[16] )
  {
    v8 = *(void **)hstringHeader.Reserved.Reserved1;
    *(_QWORD *)hstringHeader.Reserved.Reserved1 = *(_QWORD *)&hstringHeader.Reserved.Reserved2[8];
    if ( v8 )
      CoTaskMemFree(v8);
  }
  v53 = 0;
  v9 = SRDictionaryToPropertySet(v46, pv, &v53);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x116,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\fulltrustprocesslauncher.cpp",
      (const char *)(unsigned int)v9,
      v44);
  v52 = 0;
  v10 = (**v53)(v53, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v52);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x119,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\fulltrustprocesslauncher.cpp",
      (const char *)(unsigned int)v10,
      v44);
  v51 = 0;
  v11 = v52;
  v12 = *(int (__fastcall **)(__int64, HSTRING, _QWORD))(*(_QWORD *)v52 + 48LL);
  string = 0;
  v13 = WindowsCreateStringReference(L"FullTrustProcess", 0x10u, &hstringHeader, &string);
  if ( v13 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v13, v14, v15);
    __debugbreak();
  }
  if ( v12(v11, string, &v51) < 0 )
  {
    v41 = (Microsoft::WRL::Wrappers::HStringReference *)Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                                                          &hstringHeader,
                                                          (const unsigned __int16 (*)[27])v16);
    v42 = Microsoft::WRL::Wrappers::HStringReference::Get(v41);
    RoOriginateError(2147942487LL, v42);
    v43 = wil::verify_hresult(2147942487LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x11E,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\fulltrustprocesslauncher.cpp",
      (const char *)v43,
      v44);
  }
  v50 = 0;
  v45 = 0;
  v17 = (**v51)(v51, &GUID_fe2f3d47_5d47_5499_8374_430c7cda0204, &v50);
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x124,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\fulltrustprocesslauncher.cpp",
      (const char *)(unsigned int)v17,
      v44);
  v18 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v50 + 48LL))(v50, &v45);
  if ( v18 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x125,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\fulltrustprocesslauncher.cpp",
      (const char *)(unsigned int)v18,
      v44);
  v49 = 0;
  v19 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v45 + 48LL))(v45, &v49);
  if ( v19 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x128,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\fulltrustprocesslauncher.cpp",
      (const char *)(unsigned int)v19,
      v44);
  v47 = 0;
  v20 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v49 + 56LL))(
          v49,
          &v47);
  if ( v20 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x12A,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\fulltrustprocesslauncher.cpp",
      (const char *)(unsigned int)v20,
      v44);
  *(_OWORD *)a2 = 0;
  a2[2] = 0;
  a2[3] = 7;
  *(_WORD *)a2 = 0;
  v55 = 1;
  v21 = 0;
  v48 = 0;
  if ( (int)(**v47)(v47, &GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62, &v48) < 0 )
  {
    v44 = 0;
    v25 = (**v47)(v47, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, &v44);
    if ( v25 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x149,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\fulltrustprocesslauncher.cpp",
        (const char *)(unsigned int)v25,
        v44);
    v21 = Windows::ApplicationModel::Internal::FullTrustProcessLauncherInternal::Match(v44, a5, a2);
    v26 = v44;
    if ( v44 )
    {
      v44 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    }
  }
  else
  {
    LODWORD(v44) = 0;
    v56 = 0;
    v22 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64 *))(*(_QWORD *)v48 + 304LL))(v48, &v44, &v56);
    if ( v22 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x133,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\fulltrustprocesslauncher.cpp",
        (const char *)(unsigned int)v22,
        v44);
    hstringHeader.Reserved.Reserved1 = &v44;
    *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = &v56;
    hstringHeader.Reserved.Reserved2[16] = 1;
    for ( i = 0;
          i < (unsigned int)v44;
          v21 = Windows::ApplicationModel::Internal::FullTrustProcessLauncherInternal::Match(
                  *(_QWORD *)(v56 + 8LL * i++),
                  a5,
                  a2) )
    {
      if ( v21 )
        break;
    }
    wil::details::ScopeExitFn<_lambda_ffadca1a5de8736345fafc00de69ade1_>::~ScopeExitFn<_lambda_ffadca1a5de8736345fafc00de69ade1_>(&hstringHeader);
  }
  if ( !v21 )
  {
    v38 = (Microsoft::WRL::Wrappers::HStringReference *)Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                                                          &hstringHeader,
                                                          (const unsigned __int16 (*)[27])v24);
    v39 = Microsoft::WRL::Wrappers::HStringReference::Get(v38);
    RoOriginateError(2147942487LL, v39);
    v40 = wil::verify_hresult(2147942487LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x150,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\fulltrustprocesslauncher.cpp",
      (const char *)v40,
      v44);
  }
  v27 = v48;
  if ( v48 )
  {
    v48 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  }
  v28 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v47;
  if ( v47 )
  {
    v47 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v28)[2])(v28);
  }
  v29 = v49;
  if ( v49 )
  {
    v49 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  }
  v30 = v45;
  if ( v45 )
  {
    v45 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  }
  v31 = v50;
  if ( v50 )
  {
    v50 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
  }
  v32 = v51;
  if ( v51 )
  {
    v51 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v32)[2])(v32);
  }
  v33 = v52;
  if ( v52 )
  {
    v52 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
  }
  v34 = v53;
  if ( v53 )
  {
    v53 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v34)[2])(v34);
  }
  v35 = pv;
  pv = 0;
  if ( v35 )
    CoTaskMemFree(v35);
  v36 = v57[0];
  if ( v57[0] )
  {
    v57[0] = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
  }
  return a2;
}

```

## disassembly

```asm
0x18004c680  mov     [rsp-8+arg_0], rbx
0x18004c685  push    rbp
0x18004c686  push    rsi
0x18004c687  push    rdi
0x18004c688  push    r14
0x18004c68a  push    r15
0x18004c68c  lea     rbp, [rsp-2Fh]
0x18004c691  sub     rsp, 0C0h
0x18004c698  mov     rax, cs:__security_cookie
0x18004c69f  xor     rax, rsp
0x18004c6a2  mov     [rbp+4Fh+var_28], rax
0x18004c6a6  mov     rdi, rdx
0x18004c6a9  mov     [rbp+4Fh+var_50], rdx
0x18004c6ad  mov     r14, [rbp+4Fh+arg_20]
0x18004c6b1  xor     r15d, r15d
0x18004c6b4  mov     [rbp+4Fh+var_68], r15d
0x18004c6b8  lea     rdx, [rbp+4Fh+var_58]
0x18004c6bc  call    ?GetFullTrustExtension@FullTrustProcessLauncherInternal@Internal@ApplicationModel@Windows@@AEAA?AV?$ComPtr@UIApplicationExtension@StateRepository@Internal@Windows@@@WRL@Microsoft@@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::ApplicationModel::Internal::FullTrustProcessLauncherInternal::GetFullTrustExtension(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> const &,std::wstring const &)
0x18004c6c1  nop
0x18004c6c2  mov     [rbp+4Fh+var_B0], r15d
0x18004c6c6  mov     [rbp+4Fh+pv], r15
0x18004c6ca  mov     rcx, [rbp+4Fh+var_58]
0x18004c6ce  mov     rax, [rcx]
0x18004c6d1  lea     rdx, [rbp+4Fh+pv]
0x18004c6d5  mov     qword ptr [rbp+4Fh+hstringHeader.Reserved], rdx
0x18004c6d9  mov     qword ptr [rbp+4Fh+hstringHeader.Reserved+8], r15
0x18004c6dd  mov     byte ptr [rbp+4Fh+hstringHeader.Reserved+10h], 1
0x18004c6e1  lea     r8, [rbp+4Fh+hstringHeader.Reserved+8]
0x18004c6e5  lea     rdx, [rbp+4Fh+var_B0]
0x18004c6e9  mov     rax, [rax+200h]
0x18004c6f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c6f5  mov     rcx, [rbp+57h]; this
0x18004c6f9  test    eax, eax
0x18004c6fb  js      loc_18004CB15
0x18004c701  cmp     byte ptr [rbp+4Fh+hstringHeader.Reserved+10h], r15b
0x18004c705  jz      short loc_18004C726
0x18004c707  mov     rdx, qword ptr [rbp+4Fh+hstringHeader.Reserved]
0x18004c70b  mov     rcx, [rdx]; pv
0x18004c70e  mov     rax, qword ptr [rbp+4Fh+hstringHeader.Reserved+8]
0x18004c712  mov     [rdx], rax
0x18004c715  test    rcx, rcx
0x18004c718  jz      short loc_18004C726
0x18004c71a  call    cs:__imp_CoTaskMemFree
0x18004c721  nop     dword ptr [rax+rax+00h]
0x18004c726  mov     [rbp+4Fh+var_78], r15
0x18004c72a  lea     r8, [rbp+4Fh+var_78]
0x18004c72e  mov     rdx, [rbp+4Fh+pv]
0x18004c732  mov     ecx, [rbp+4Fh+var_B0]
0x18004c735  call    cs:__imp_SRDictionaryToPropertySet
0x18004c73c  nop     dword ptr [rax+rax+00h]
0x18004c741  mov     rcx, [rbp+57h]; this
0x18004c745  test    eax, eax
0x18004c747  js      loc_18004CB2A
0x18004c74d  mov     [rbp+4Fh+var_80], r15
0x18004c751  mov     rcx, [rbp+4Fh+var_78]
0x18004c755  mov     rax, [rcx]
0x18004c758  lea     r8, [rbp+4Fh+var_80]
0x18004c75c  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x18004c763  mov     rax, [rax]
0x18004c766  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c76b  nop
0x18004c76c  mov     rcx, [rbp+57h]; this
0x18004c770  test    eax, eax
0x18004c772  js      loc_18004CB3F
0x18004c778  mov     [rbp+4Fh+var_88], r15
0x18004c77c  mov     rbx, [rbp+4Fh+var_80]
0x18004c780  mov     rax, [rbx]
0x18004c783  mov     rsi, [rax+30h]
0x18004c787  mov     [rbp+4Fh+string], r15
0x18004c78b  lea     r9, [rbp+4Fh+string]; string
0x18004c78f  lea     r8, [rbp+4Fh+hstringHeader]; hstringHeader
0x18004c793  mov     edx, 10h; length
0x18004c798  lea     rcx, aFulltrustproce; "FullTrustProcess"
0x18004c79f  call    cs:__imp_WindowsCreateStringReference
0x18004c7a6  nop     dword ptr [rax+rax+00h]
0x18004c7ab  test    eax, eax
0x18004c7ad  js      loc_18004CB54
0x18004c7b3  lea     r8, [rbp+4Fh+var_88]
0x18004c7b7  mov     rdx, [rbp+4Fh+string]
0x18004c7bb  mov     rcx, rbx
0x18004c7be  mov     rax, rsi
0x18004c7c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c7c6  nop
0x18004c7c7  shr     eax, 1Fh
0x18004c7ca  test    al, al
0x18004c7cc  jnz     loc_18004CB5C
0x18004c7d2  mov     [rbp+4Fh+var_90], r15
0x18004c7d6  mov     [rbp+4Fh+var_B8], r15
0x18004c7da  mov     rcx, [rbp+4Fh+var_88]
0x18004c7de  mov     rax, [rcx]
0x18004c7e1  lea     r8, [rbp+4Fh+var_90]
0x18004c7e5  lea     rdx, _GUID_fe2f3d47_5d47_5499_8374_430c7cda0204
0x18004c7ec  mov     rax, [rax]
0x18004c7ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c7f4  nop
0x18004c7f5  mov     rcx, [rbp+57h]; this
0x18004c7f9  test    eax, eax
0x18004c7fb  js      loc_18004CBA3
0x18004c801  mov     rbx, [rbp+4Fh+var_90]
0x18004c805  mov     rax, [rbx]
0x18004c808  mov     rsi, [rax+30h]
0x18004c80c  mov     rcx, [rbp+4Fh+var_B8]
0x18004c810  test    rcx, rcx
0x18004c813  jz      short loc_18004C826
0x18004c815  mov     [rbp+4Fh+var_B8], r15
0x18004c819  mov     rax, [rcx]
0x18004c81c  mov     rax, [rax+10h]
0x18004c820  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c825  nop
0x18004c826  lea     rdx, [rbp+4Fh+var_B8]
0x18004c82a  mov     rcx, rbx
0x18004c82d  mov     rax, rsi
0x18004c830  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c835  mov     rcx, [rbp+57h]; this
0x18004c839  test    eax, eax
0x18004c83b  js      loc_18004CBB8
0x18004c841  mov     [rbp+4Fh+var_98], r15
0x18004c845  mov     rcx, [rbp+4Fh+var_B8]
0x18004c849  mov     rax, [rcx]
0x18004c84c  lea     rdx, [rbp+4Fh+var_98]
0x18004c850  mov     rax, [rax+30h]
0x18004c854  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c859  mov     rcx, [rbp+57h]; this
0x18004c85d  test    eax, eax
0x18004c85f  js      loc_18004CBCD
0x18004c865  mov     [rbp+4Fh+var_A8], r15
0x18004c869  mov     rcx, [rbp+4Fh+var_98]
0x18004c86d  mov     rax, [rcx]
0x18004c870  lea     rdx, [rbp+4Fh+var_A8]
0x18004c874  mov     rax, [rax+38h]
0x18004c878  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c87d  mov     rcx, [rbp+57h]; this
0x18004c881  test    eax, eax
0x18004c883  js      loc_18004CBE2
0x18004c889  xorps   xmm0, xmm0
0x18004c88c  movups  xmmword ptr [rdi], xmm0
0x18004c88f  mov     [rdi+10h], r15
0x18004c893  mov     qword ptr [rdi+18h], 7
0x18004c89b  mov     [rdi], r15w
0x18004c89f  mov     [rbp+4Fh+var_68], 1
0x18004c8a6  mov     bl, r15b
0x18004c8a9  mov     [rbp+4Fh+var_A0], r15
0x18004c8ad  mov     rcx, [rbp+4Fh+var_A8]
0x18004c8b1  mov     rax, [rcx]
0x18004c8b4  lea     r8, [rbp+4Fh+var_A0]
0x18004c8b8  lea     rdx, _GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62
0x18004c8bf  mov     rax, [rax]
0x18004c8c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c8c7  nop
0x18004c8c8  test    eax, eax
0x18004c8ca  js      short loc_18004C945
0x18004c8cc  mov     dword ptr [rbp+4Fh+var_C0], r15d
0x18004c8d0  mov     [rbp+4Fh+var_60], r15
0x18004c8d4  mov     rcx, [rbp+4Fh+var_A0]
0x18004c8d8  mov     rax, [rcx]
0x18004c8db  lea     r8, [rbp+4Fh+var_60]
0x18004c8df  lea     rdx, [rbp+4Fh+var_C0]
0x18004c8e3  mov     rax, [rax+130h]
0x18004c8ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c8ef  mov     rcx, [rbp+57h]; this
0x18004c8f3  test    eax, eax
0x18004c8f5  js      loc_18004CBF7
0x18004c8fb  lea     rax, [rbp+4Fh+var_C0]
0x18004c8ff  mov     qword ptr [rbp+4Fh+hstringHeader.Reserved], rax
0x18004c903  lea     rax, [rbp+4Fh+var_60]
0x18004c907  mov     qword ptr [rbp+4Fh+hstringHeader.Reserved+8], rax
0x18004c90b  mov     byte ptr [rbp+4Fh+hstringHeader.Reserved+10h], 1
0x18004c90f  mov     esi, r15d
0x18004c912  cmp     dword ptr [rbp+4Fh+var_C0], r15d
0x18004c916  jbe     short loc_18004C93A
0x18004c918  test    bl, bl
0x18004c91a  jnz     short loc_18004C93A
0x18004c91c  mov     eax, esi
0x18004c91e  mov     r8, rdi
0x18004c921  mov     rdx, r14
0x18004c924  mov     rcx, [rbp+4Fh+var_60]
0x18004c928  mov     rcx, [rcx+rax*8]
0x18004c92c  call    ?Match@FullTrustProcessLauncherInternal@Internal@ApplicationModel@Windows@@CA_NPEAUIInspectable@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV67@@Z; Windows::ApplicationModel::Internal::FullTrustProcessLauncherInternal::Match(IInspectable *,std::wstring const &,std::wstring &)
0x18004c931  mov     bl, al
0x18004c933  inc     esi
0x18004c935  cmp     esi, dword ptr [rbp+4Fh+var_C0]
0x18004c938  jb      short loc_18004C918
0x18004c93a  lea     rcx, [rbp+4Fh+hstringHeader]
0x18004c93e  call    ??1?$ScopeExitFn@V_lambda_ffadca1a5de8736345fafc00de69ade1_@@@details@wil@@QEAA@XZ; wil::details::ScopeExitFn<_lambda_ffadca1a5de8736345fafc00de69ade1_>::~ScopeExitFn<_lambda_ffadca1a5de8736345fafc00de69ade1_>(void)
0x18004c943  jmp     short loc_18004C99B
0x18004c945  mov     [rbp+4Fh+var_C0], r15
0x18004c949  mov     rcx, [rbp+4Fh+var_A8]
0x18004c94d  mov     rax, [rcx]
0x18004c950  lea     r8, [rbp+4Fh+var_C0]
0x18004c954  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90
0x18004c95b  mov     rax, [rax]
0x18004c95e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c963  nop
0x18004c964  mov     rcx, [rbp+57h]; this
0x18004c968  test    eax, eax
0x18004c96a  js      loc_18004CC0C
0x18004c970  mov     r8, rdi
0x18004c973  mov     rdx, r14
0x18004c976  mov     rcx, [rbp+4Fh+var_C0]
0x18004c97a  call    ?Match@FullTrustProcessLauncherInternal@Internal@ApplicationModel@Windows@@CA_NPEAUIInspectable@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV67@@Z; Windows::ApplicationModel::Internal::FullTrustProcessLauncherInternal::Match(IInspectable *,std::wstring const &,std::wstring &)
0x18004c97f  mov     bl, al
0x18004c981  mov     rcx, [rbp+4Fh+var_C0]
0x18004c985  test    rcx, rcx
0x18004c988  jz      short loc_18004C99B
0x18004c98a  mov     [rbp+4Fh+var_C0], r15
0x18004c98e  mov     rax, [rcx]
0x18004c991  mov     rax, [rax+10h]
0x18004c995  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c99a  nop
0x18004c99b  test    bl, bl
0x18004c99d  jz      loc_18004CACE
0x18004c9a3  mov     rcx, [rbp+4Fh+var_A0]
0x18004c9a7  test    rcx, rcx
0x18004c9aa  jz      short loc_18004C9BD
0x18004c9ac  mov     [rbp+4Fh+var_A0], r15
0x18004c9b0  mov     rax, [rcx]
0x18004c9b3  mov     rax, [rax+10h]
0x18004c9b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c9bc  nop
0x18004c9bd  mov     rcx, [rbp+4Fh+var_A8]
0x18004c9c1  test    rcx, rcx
0x18004c9c4  jz      short loc_18004C9D7
0x18004c9c6  mov     [rbp+4Fh+var_A8], r15
0x18004c9ca  mov     rax, [rcx]
0x18004c9cd  mov     rax, [rax+10h]
0x18004c9d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c9d6  nop
0x18004c9d7  mov     rcx, [rbp+4Fh+var_98]
0x18004c9db  test    rcx, rcx
0x18004c9de  jz      short loc_18004C9F1
0x18004c9e0  mov     [rbp+4Fh+var_98], r15
0x18004c9e4  mov     rax, [rcx]
0x18004c9e7  mov     rax, [rax+10h]
0x18004c9eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c9f0  nop
0x18004c9f1  mov     rcx, [rbp+4Fh+var_B8]
0x18004c9f5  test    rcx, rcx
0x18004c9f8  jz      short loc_18004CA0B
0x18004c9fa  mov     [rbp+4Fh+var_B8], r15
0x18004c9fe  mov     rax, [rcx]
0x18004ca01  mov     rax, [rax+10h]
0x18004ca05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ca0a  nop
0x18004ca0b  mov     rcx, [rbp+4Fh+var_90]
0x18004ca0f  test    rcx, rcx
0x18004ca12  jz      short loc_18004CA25
0x18004ca14  mov     [rbp+4Fh+var_90], r15
0x18004ca18  mov     rax, [rcx]
0x18004ca1b  mov     rax, [rax+10h]
0x18004ca1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ca24  nop
0x18004ca25  mov     rcx, [rbp+4Fh+var_88]
0x18004ca29  test    rcx, rcx
0x18004ca2c  jz      short loc_18004CA3F
0x18004ca2e  mov     [rbp+4Fh+var_88], r15
0x18004ca32  mov     rax, [rcx]
0x18004ca35  mov     rax, [rax+10h]
0x18004ca39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ca3e  nop
0x18004ca3f  mov     rcx, [rbp+4Fh+var_80]
0x18004ca43  test    rcx, rcx
0x18004ca46  jz      short loc_18004CA59
0x18004ca48  mov     [rbp+4Fh+var_80], r15
0x18004ca4c  mov     rax, [rcx]
0x18004ca4f  mov     rax, [rax+10h]
0x18004ca53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ca58  nop
0x18004ca59  mov     rcx, [rbp+4Fh+var_78]
0x18004ca5d  test    rcx, rcx
0x18004ca60  jz      short loc_18004CA73
0x18004ca62  mov     [rbp+4Fh+var_78], r15
0x18004ca66  mov     rax, [rcx]
0x18004ca69  mov     rax, [rax+10h]
0x18004ca6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ca72  nop
0x18004ca73  mov     rcx, [rbp+4Fh+pv]; pv
0x18004ca77  mov     [rbp+4Fh+pv], r15
0x18004ca7b  test    rcx, rcx
0x18004ca7e  jz      short loc_18004CA8D
0x18004ca80  call    cs:__imp_CoTaskMemFree
0x18004ca87  nop     dword ptr [rax+rax+00h]
0x18004ca8c  nop
0x18004ca8d  mov     rcx, [rbp+4Fh+var_58]
0x18004ca91  test    rcx, rcx
0x18004ca94  jz      short loc_18004CAA7
0x18004ca96  mov     [rbp+4Fh+var_58], r15
0x18004ca9a  mov     rdx, [rcx]
0x18004ca9d  mov     rax, [rdx+10h]
0x18004caa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004caa6  nop
0x18004caa7  mov     rax, rdi
0x18004caaa  mov     rcx, [rbp+4Fh+var_28]
0x18004caae  xor     rcx, rsp; StackCookie
0x18004cab1  call    __security_check_cookie
0x18004cab6  mov     rbx, [rsp+0E0h+arg_0]
0x18004cabe  add     rsp, 0C0h
0x18004cac5  pop     r15
0x18004cac7  pop     r14
0x18004cac9  pop     rdi
0x18004caca  pop     rsi
  ... truncated ...
```
