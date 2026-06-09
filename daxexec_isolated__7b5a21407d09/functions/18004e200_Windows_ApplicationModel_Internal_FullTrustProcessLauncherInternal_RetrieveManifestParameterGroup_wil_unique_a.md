# Windows::ApplicationModel::Internal::FullTrustProcessLauncherInternal::RetrieveManifestParameterGroup(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18004e200`
- end: `0x18004e79e`
- name: `?RetrieveManifestParameterGroup@FullTrustProcessLauncherInternal@Internal@ApplicationModel@Windows@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV56@1@Z`
- size: `1438`
- prototype: `__int64 __fastcall(__int64, __int64, const WCHAR **, _QWORD *, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004d580`

## callees

- `0x180004f70`
- `0x18000e074`
- `0x1800125f4`
- `0x18003c394`
- `0x18003fd60`
- `0x18004c248`
- `0x18004c730`
- `0x18004cdc0`
- `0x18004db98`
- `0x18004e200`
- `0x1800cd010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18004e666`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18004e6f4`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18004e666`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18004e6f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e29a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e5fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e29a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e5fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004e31b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004e31b`
- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-3!SRDictionaryToPropertySet` at `0x18004e2b5`
- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-3!SRDictionaryToPropertySet` at `0x18004e2b5`

## pseudocode

```c
__int64 __fastcall Windows::ApplicationModel::Internal::FullTrustProcessLauncherInternal::RetrieveManifestParameterGroup(
        __int64 a1,
        __int64 a2,
        const WCHAR **a3,
        _QWORD *a4,
        __int64 a5)
{
  __int64 v6; // rax
  int v7; // eax
  void *v8; // rcx
  int v9; // eax
  int v10; // eax
  _QWORD *v11; // rbx
  __int64 v12; // rdi
  HRESULT v13; // eax
  int v14; // edx
  unsigned int v15; // r8d
  const unsigned __int16 *v16; // rdx
  int v17; // eax
  int v18; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  char v22; // bl
  unsigned int i; // edi
  const unsigned __int16 *v24; // rdx
  int v25; // eax
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 (__fastcall ***v28)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rcx
  __int64 (__fastcall ***v32)(_QWORD, GUID *, _QWORD *); // rcx
  _QWORD *v33; // rcx
  __int64 (__fastcall ***v34)(_QWORD, GUID *, _QWORD **); // rcx
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
  _QWORD *v52; // [rsp+60h] [rbp-31h] BYREF
  __int64 (__fastcall ***v53)(_QWORD, GUID *, _QWORD **); // [rsp+68h] [rbp-29h] BYREF
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
  v12 = *v52;
  string = 0;
  v13 = WindowsCreateStringReference(L"FullTrustProcess", 0x10u, &hstringHeader, &string);
  if ( v13 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v13, v14, v15);
    __debugbreak();
  }
  if ( (*(int (__fastcall **)(_QWORD *, HSTRING, _QWORD))(v12 + 48))(v11, string, &v51) < 0 )
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
  *(_QWORD *)(a2 + 16) = 0;
  *(_QWORD *)(a2 + 24) = 7;
  *(_WORD *)a2 = 0;
  v55 = 1;
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
    v22 = Windows::ApplicationModel::Internal::FullTrustProcessLauncherInternal::Match(v44, a5, a2);
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
    v21 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64 *))(*(_QWORD *)v48 + 304LL))(v48, &v44, &v56);
    if ( v21 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x133,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\fulltrustprocesslauncher.cpp",
        (const char *)(unsigned int)v21,
        v44);
    v22 = 0;
    hstringHeader.Reserved.Reserved1 = &v44;
    *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = &v56;
    hstringHeader.Reserved.Reserved2[16] = 1;
    for ( i = 0;
          i < (unsigned int)v44;
          v22 = Windows::ApplicationModel::Internal::FullTrustProcessLauncherInternal::Match(
                  *(_QWORD *)(v56 + 8LL * i++),
                  a5,
                  a2) )
    {
      if ( v22 )
        break;
    }
    wil::details::ScopeExitFn<_lambda_ffadca1a5de8736345fafc00de69ade1_>::~ScopeExitFn<_lambda_ffadca1a5de8736345fafc00de69ade1_>(&hstringHeader);
  }
  if ( !v22 )
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
    (*(void (__fastcall **)(_QWORD *))(*v33 + 16LL))(v33);
  }
  v34 = v53;
  if ( v53 )
  {
    v53 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD **)))(*v34)[2])(v34);
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
0x18004e200  mov     [rsp-8+arg_0], rbx
0x18004e205  push    rbp
0x18004e206  push    rsi
0x18004e207  push    rdi
0x18004e208  push    r14
0x18004e20a  push    r15
0x18004e20c  lea     rbp, [rsp-2Fh]
0x18004e211  sub     rsp, 0C0h
0x18004e218  mov     rax, cs:__security_cookie
0x18004e21f  xor     rax, rsp
0x18004e222  mov     [rbp+4Fh+var_28], rax
0x18004e226  mov     rsi, rdx
0x18004e229  mov     [rbp+4Fh+var_50], rdx
0x18004e22d  mov     r14, [rbp+4Fh+arg_20]
0x18004e231  xor     r15d, r15d
0x18004e234  mov     [rbp+4Fh+var_68], r15d
0x18004e238  lea     rdx, [rbp+4Fh+var_58]
0x18004e23c  call    ?GetFullTrustExtension@FullTrustProcessLauncherInternal@Internal@ApplicationModel@Windows@@AEAA?AV?$ComPtr@UIApplicationExtension@StateRepository@Internal@Windows@@@WRL@Microsoft@@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::ApplicationModel::Internal::FullTrustProcessLauncherInternal::GetFullTrustExtension(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> const &,std::wstring const &)
0x18004e241  nop
0x18004e242  mov     [rbp+4Fh+var_B0], r15d
0x18004e246  mov     [rbp+4Fh+pv], r15
0x18004e24a  mov     rcx, [rbp+4Fh+var_58]
0x18004e24e  mov     rax, [rcx]
0x18004e251  lea     rdx, [rbp+4Fh+pv]
0x18004e255  mov     qword ptr [rbp+4Fh+hstringHeader.Reserved], rdx
0x18004e259  mov     qword ptr [rbp+4Fh+hstringHeader.Reserved+8], r15
0x18004e25d  mov     byte ptr [rbp+4Fh+hstringHeader.Reserved+10h], 1
0x18004e261  lea     r8, [rbp+4Fh+hstringHeader.Reserved+8]
0x18004e265  lea     rdx, [rbp+4Fh+var_B0]
0x18004e269  mov     rax, [rax+200h]
0x18004e270  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e275  mov     rcx, [rbp+57h]; this
0x18004e279  test    eax, eax
0x18004e27b  js      loc_18004E692
0x18004e281  cmp     byte ptr [rbp+4Fh+hstringHeader.Reserved+10h], r15b
0x18004e285  jz      short loc_18004E2A6
0x18004e287  mov     rdx, qword ptr [rbp+4Fh+hstringHeader.Reserved]
0x18004e28b  mov     rcx, [rdx]; pv
0x18004e28e  mov     rax, qword ptr [rbp+4Fh+hstringHeader.Reserved+8]
0x18004e292  mov     [rdx], rax
0x18004e295  test    rcx, rcx
0x18004e298  jz      short loc_18004E2A6
0x18004e29a  call    cs:__imp_CoTaskMemFree
0x18004e2a1  nop     dword ptr [rax+rax+00h]
0x18004e2a6  mov     [rbp+4Fh+var_78], r15
0x18004e2aa  lea     r8, [rbp+4Fh+var_78]
0x18004e2ae  mov     rdx, [rbp+4Fh+pv]
0x18004e2b2  mov     ecx, [rbp+4Fh+var_B0]
0x18004e2b5  call    cs:__imp_SRDictionaryToPropertySet
0x18004e2bc  nop     dword ptr [rax+rax+00h]
0x18004e2c1  mov     rcx, [rbp+57h]; this
0x18004e2c5  test    eax, eax
0x18004e2c7  js      loc_18004E6A7
0x18004e2cd  mov     [rbp+4Fh+var_80], r15
0x18004e2d1  mov     rcx, [rbp+4Fh+var_78]
0x18004e2d5  mov     rax, [rcx]
0x18004e2d8  lea     r8, [rbp+4Fh+var_80]
0x18004e2dc  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x18004e2e3  mov     rax, [rax]
0x18004e2e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e2eb  nop
0x18004e2ec  mov     rcx, [rbp+57h]; this
0x18004e2f0  test    eax, eax
0x18004e2f2  js      loc_18004E6BC
0x18004e2f8  mov     [rbp+4Fh+var_88], r15
0x18004e2fc  mov     rbx, [rbp+4Fh+var_80]
0x18004e300  mov     rdi, [rbx]
0x18004e303  mov     [rbp+4Fh+string], r15
0x18004e307  lea     r9, [rbp+4Fh+string]; string
0x18004e30b  lea     r8, [rbp+4Fh+hstringHeader]; hstringHeader
0x18004e30f  mov     edx, 10h; length
0x18004e314  lea     rcx, aFulltrustproce; "FullTrustProcess"
0x18004e31b  call    cs:__imp_WindowsCreateStringReference
0x18004e322  nop     dword ptr [rax+rax+00h]
0x18004e327  test    eax, eax
0x18004e329  js      loc_18004E6D1
0x18004e32f  lea     r8, [rbp+4Fh+var_88]
0x18004e333  mov     rdx, [rbp+4Fh+string]
0x18004e337  mov     rcx, rbx
0x18004e33a  mov     rax, [rdi+30h]
0x18004e33e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e343  nop
0x18004e344  shr     eax, 1Fh
0x18004e347  test    al, al
0x18004e349  jnz     loc_18004E6D9
0x18004e34f  mov     [rbp+4Fh+var_90], r15
0x18004e353  mov     [rbp+4Fh+var_B8], r15
0x18004e357  mov     rcx, [rbp+4Fh+var_88]
0x18004e35b  mov     rax, [rcx]
0x18004e35e  lea     r8, [rbp+4Fh+var_90]
0x18004e362  lea     rdx, _GUID_fe2f3d47_5d47_5499_8374_430c7cda0204
0x18004e369  mov     rax, [rax]
0x18004e36c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e371  nop
0x18004e372  mov     rcx, [rbp+57h]; this
0x18004e376  test    eax, eax
0x18004e378  js      loc_18004E720
0x18004e37e  mov     rbx, [rbp+4Fh+var_90]
0x18004e382  mov     rax, [rbx]
0x18004e385  mov     rdi, [rax+30h]
0x18004e389  mov     rcx, [rbp+4Fh+var_B8]
0x18004e38d  test    rcx, rcx
0x18004e390  jz      short loc_18004E3A3
0x18004e392  mov     [rbp+4Fh+var_B8], r15
0x18004e396  mov     rax, [rcx]
0x18004e399  mov     rax, [rax+10h]
0x18004e39d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e3a2  nop
0x18004e3a3  lea     rdx, [rbp+4Fh+var_B8]
0x18004e3a7  mov     rcx, rbx
0x18004e3aa  mov     rax, rdi
0x18004e3ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e3b2  mov     rcx, [rbp+57h]; this
0x18004e3b6  test    eax, eax
0x18004e3b8  js      loc_18004E735
0x18004e3be  mov     [rbp+4Fh+var_98], r15
0x18004e3c2  mov     rcx, [rbp+4Fh+var_B8]
0x18004e3c6  mov     rax, [rcx]
0x18004e3c9  lea     rdx, [rbp+4Fh+var_98]
0x18004e3cd  mov     rax, [rax+30h]
0x18004e3d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e3d6  mov     rcx, [rbp+57h]; this
0x18004e3da  test    eax, eax
0x18004e3dc  js      loc_18004E74A
0x18004e3e2  mov     [rbp+4Fh+var_A8], r15
0x18004e3e6  mov     rcx, [rbp+4Fh+var_98]
0x18004e3ea  mov     rax, [rcx]
0x18004e3ed  lea     rdx, [rbp+4Fh+var_A8]
0x18004e3f1  mov     rax, [rax+38h]
0x18004e3f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e3fa  mov     rcx, [rbp+57h]; this
0x18004e3fe  test    eax, eax
0x18004e400  js      loc_18004E75F
0x18004e406  xorps   xmm0, xmm0
0x18004e409  movups  xmmword ptr [rsi], xmm0
0x18004e40c  mov     [rsi+10h], r15
0x18004e410  mov     qword ptr [rsi+18h], 7
0x18004e418  mov     [rsi], r15w
0x18004e41c  mov     [rbp+4Fh+var_68], 1
0x18004e423  mov     [rbp+4Fh+var_A0], r15
0x18004e427  mov     rcx, [rbp+4Fh+var_A8]
0x18004e42b  mov     rax, [rcx]
0x18004e42e  lea     r8, [rbp+4Fh+var_A0]
0x18004e432  lea     rdx, _GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62
0x18004e439  mov     rax, [rax]
0x18004e43c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e441  nop
0x18004e442  test    eax, eax
0x18004e444  js      short loc_18004E4C2
0x18004e446  mov     dword ptr [rbp+4Fh+var_C0], r15d
0x18004e44a  mov     [rbp+4Fh+var_60], r15
0x18004e44e  mov     rcx, [rbp+4Fh+var_A0]
0x18004e452  mov     rax, [rcx]
0x18004e455  lea     r8, [rbp+4Fh+var_60]
0x18004e459  lea     rdx, [rbp+4Fh+var_C0]
0x18004e45d  mov     rax, [rax+130h]
0x18004e464  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e469  mov     rcx, [rbp+57h]; this
0x18004e46d  test    eax, eax
0x18004e46f  js      loc_18004E774
0x18004e475  mov     bl, r15b
0x18004e478  lea     rax, [rbp+4Fh+var_C0]
0x18004e47c  mov     qword ptr [rbp+4Fh+hstringHeader.Reserved], rax
0x18004e480  lea     rax, [rbp+4Fh+var_60]
0x18004e484  mov     qword ptr [rbp+4Fh+hstringHeader.Reserved+8], rax
0x18004e488  mov     byte ptr [rbp+4Fh+hstringHeader.Reserved+10h], 1
0x18004e48c  mov     edi, r15d
0x18004e48f  cmp     dword ptr [rbp+4Fh+var_C0], r15d
0x18004e493  jbe     short loc_18004E4B7
0x18004e495  test    bl, bl
0x18004e497  jnz     short loc_18004E4B7
0x18004e499  mov     eax, edi
0x18004e49b  mov     r8, rsi
0x18004e49e  mov     rdx, r14
0x18004e4a1  mov     rcx, [rbp+4Fh+var_60]
0x18004e4a5  mov     rcx, [rcx+rax*8]
0x18004e4a9  call    ?Match@FullTrustProcessLauncherInternal@Internal@ApplicationModel@Windows@@CA_NPEAUIInspectable@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV67@@Z; Windows::ApplicationModel::Internal::FullTrustProcessLauncherInternal::Match(IInspectable *,std::wstring const &,std::wstring &)
0x18004e4ae  mov     bl, al
0x18004e4b0  inc     edi
0x18004e4b2  cmp     edi, dword ptr [rbp+4Fh+var_C0]
0x18004e4b5  jb      short loc_18004E495
0x18004e4b7  lea     rcx, [rbp+4Fh+hstringHeader]
0x18004e4bb  call    ??1?$ScopeExitFn@V_lambda_ffadca1a5de8736345fafc00de69ade1_@@@details@wil@@QEAA@XZ; wil::details::ScopeExitFn<_lambda_ffadca1a5de8736345fafc00de69ade1_>::~ScopeExitFn<_lambda_ffadca1a5de8736345fafc00de69ade1_>(void)
0x18004e4c0  jmp     short loc_18004E518
0x18004e4c2  mov     [rbp+4Fh+var_C0], r15
0x18004e4c6  mov     rcx, [rbp+4Fh+var_A8]
0x18004e4ca  mov     rax, [rcx]
0x18004e4cd  lea     r8, [rbp+4Fh+var_C0]
0x18004e4d1  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90
0x18004e4d8  mov     rax, [rax]
0x18004e4db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e4e0  nop
0x18004e4e1  mov     rcx, [rbp+57h]; this
0x18004e4e5  test    eax, eax
0x18004e4e7  js      loc_18004E789
0x18004e4ed  mov     r8, rsi
0x18004e4f0  mov     rdx, r14
0x18004e4f3  mov     rcx, [rbp+4Fh+var_C0]
0x18004e4f7  call    ?Match@FullTrustProcessLauncherInternal@Internal@ApplicationModel@Windows@@CA_NPEAUIInspectable@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV67@@Z; Windows::ApplicationModel::Internal::FullTrustProcessLauncherInternal::Match(IInspectable *,std::wstring const &,std::wstring &)
0x18004e4fc  mov     bl, al
0x18004e4fe  mov     rcx, [rbp+4Fh+var_C0]
0x18004e502  test    rcx, rcx
0x18004e505  jz      short loc_18004E518
0x18004e507  mov     [rbp+4Fh+var_C0], r15
0x18004e50b  mov     rax, [rcx]
0x18004e50e  mov     rax, [rax+10h]
0x18004e512  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e517  nop
0x18004e518  test    bl, bl
0x18004e51a  jz      loc_18004E64B
0x18004e520  mov     rcx, [rbp+4Fh+var_A0]
0x18004e524  test    rcx, rcx
0x18004e527  jz      short loc_18004E53A
0x18004e529  mov     [rbp+4Fh+var_A0], r15
0x18004e52d  mov     rax, [rcx]
0x18004e530  mov     rax, [rax+10h]
0x18004e534  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e539  nop
0x18004e53a  mov     rcx, [rbp+4Fh+var_A8]
0x18004e53e  test    rcx, rcx
0x18004e541  jz      short loc_18004E554
0x18004e543  mov     [rbp+4Fh+var_A8], r15
0x18004e547  mov     rax, [rcx]
0x18004e54a  mov     rax, [rax+10h]
0x18004e54e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e553  nop
0x18004e554  mov     rcx, [rbp+4Fh+var_98]
0x18004e558  test    rcx, rcx
0x18004e55b  jz      short loc_18004E56E
0x18004e55d  mov     [rbp+4Fh+var_98], r15
0x18004e561  mov     rax, [rcx]
0x18004e564  mov     rax, [rax+10h]
0x18004e568  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e56d  nop
0x18004e56e  mov     rcx, [rbp+4Fh+var_B8]
0x18004e572  test    rcx, rcx
0x18004e575  jz      short loc_18004E588
0x18004e577  mov     [rbp+4Fh+var_B8], r15
0x18004e57b  mov     rax, [rcx]
0x18004e57e  mov     rax, [rax+10h]
0x18004e582  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e587  nop
0x18004e588  mov     rcx, [rbp+4Fh+var_90]
0x18004e58c  test    rcx, rcx
0x18004e58f  jz      short loc_18004E5A2
0x18004e591  mov     [rbp+4Fh+var_90], r15
0x18004e595  mov     rax, [rcx]
0x18004e598  mov     rax, [rax+10h]
0x18004e59c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e5a1  nop
0x18004e5a2  mov     rcx, [rbp+4Fh+var_88]
0x18004e5a6  test    rcx, rcx
0x18004e5a9  jz      short loc_18004E5BC
0x18004e5ab  mov     [rbp+4Fh+var_88], r15
0x18004e5af  mov     rax, [rcx]
0x18004e5b2  mov     rax, [rax+10h]
0x18004e5b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e5bb  nop
0x18004e5bc  mov     rcx, [rbp+4Fh+var_80]
0x18004e5c0  test    rcx, rcx
0x18004e5c3  jz      short loc_18004E5D6
0x18004e5c5  mov     [rbp+4Fh+var_80], r15
0x18004e5c9  mov     rax, [rcx]
0x18004e5cc  mov     rax, [rax+10h]
0x18004e5d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e5d5  nop
0x18004e5d6  mov     rcx, [rbp+4Fh+var_78]
0x18004e5da  test    rcx, rcx
0x18004e5dd  jz      short loc_18004E5F0
0x18004e5df  mov     [rbp+4Fh+var_78], r15
0x18004e5e3  mov     rax, [rcx]
0x18004e5e6  mov     rax, [rax+10h]
0x18004e5ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e5ef  nop
0x18004e5f0  mov     rcx, [rbp+4Fh+pv]; pv
0x18004e5f4  mov     [rbp+4Fh+pv], r15
0x18004e5f8  test    rcx, rcx
0x18004e5fb  jz      short loc_18004E60A
0x18004e5fd  call    cs:__imp_CoTaskMemFree
0x18004e604  nop     dword ptr [rax+rax+00h]
0x18004e609  nop
0x18004e60a  mov     rcx, [rbp+4Fh+var_58]
0x18004e60e  test    rcx, rcx
0x18004e611  jz      short loc_18004E624
0x18004e613  mov     [rbp+4Fh+var_58], r15
0x18004e617  mov     rdx, [rcx]
0x18004e61a  mov     rax, [rdx+10h]
0x18004e61e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e623  nop
0x18004e624  mov     rax, rsi
0x18004e627  mov     rcx, [rbp+4Fh+var_28]
0x18004e62b  xor     rcx, rsp; StackCookie
0x18004e62e  call    __security_check_cookie
0x18004e633  mov     rbx, [rsp+0E0h+arg_0]
0x18004e63b  add     rsp, 0C0h
0x18004e642  pop     r15
0x18004e644  pop     r14
0x18004e646  pop     rdi
0x18004e647  pop     rsi
0x18004e648  pop     rbp
  ... truncated ...
```
