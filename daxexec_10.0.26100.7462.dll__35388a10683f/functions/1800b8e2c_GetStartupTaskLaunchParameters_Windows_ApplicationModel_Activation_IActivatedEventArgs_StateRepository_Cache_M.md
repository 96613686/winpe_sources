# GetStartupTaskLaunchParameters(Windows::ApplicationModel::Activation::IActivatedEventArgs *,StateRepository::Cache::Manager_NoThrow &,__int64,ActivationProperties &)

- ea: `0x1800b8e2c`
- end: `0x1800b9664`
- name: `?GetStartupTaskLaunchParameters@@YA_NPEAUIActivatedEventArgs@Activation@ApplicationModel@Windows@@AEAVManager_NoThrow@Cache@StateRepository@@_JAEAUActivationProperties@@@Z`
- size: `2104`
- prototype: `bool(struct Windows::ApplicationModel::Activation::IActivatedEventArgs *, struct StateRepository::Cache::Manager_NoThrow *, __int64, struct ActivationProperties *)`
- caller_count: `1`
- callee_count: `25`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800b6398`

## callees

- `0x1800053a0`
- `0x18000697a`
- `0x18000e234`
- `0x180010a84`
- `0x180010cb8`
- `0x180011300`
- `0x180011820`
- `0x180011a64`
- `0x180038f68`
- `0x18003b244`
- `0x1800671a0`
- `0x18006b744`
- `0x1800b0dfc`
- `0x1800b17ac`
- `0x1800b3b14`
- `0x1800b4e4c`
- `0x1800b5f44`
- `0x1800b8d50`
- `0x1800b8e2c`
- `0x1800b966c`
- `0x1800b9898`
- `0x1800b9c4c`
- `0x1800baac0`
- `0x1800bb46c`
- `0x1800cc010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800b8f84`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800b8f84`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800b927f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800b927f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b8eb7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b90d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b9553`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b8eb7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b90d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b9553`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b8ef6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b9247`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b8ef6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b9247`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b94cf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b94cf`

## string_xrefs

- `0x1800b93ec`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x1800b95a9`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800b95cb`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800b95e0`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800b9610`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800b9628`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800b963d`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800b9652`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800b91a1`: `StartupTask`
- `0x1800b920c`: `@TaskId`
- `0x1800b8fb5`: `Windows.StartupTask`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
char __fastcall GetStartupTaskLaunchParameters(
        struct Windows::ApplicationModel::Activation::IActivatedEventArgs *a1,
        struct StateRepository::Cache::Manager_NoThrow *a2,
        __int64 a3,
        struct ActivationProperties *a4)
{
  __int64 v7; // r15
  int v8; // eax
  __int64 v9; // rbx
  __int64 (__fastcall *v10)(__int64, HSTRING *); // rdi
  int v11; // eax
  PCWSTR StringRawBuffer; // rax
  const unsigned __int16 *v13; // rdi
  __int64 v14; // rdx
  char *v15; // rcx
  int v16; // eax
  int v17; // esi
  unsigned int v18; // esi
  const unsigned __int16 *v19; // r8
  __int64 v20; // rcx
  unsigned int v22; // r14d
  UINT32 v23; // eax
  __int64 v24; // rbx
  int v25; // esi
  int v26; // eax
  const WCHAR *v27; // rax
  const WCHAR *v28; // rcx
  int v29; // eax
  int v30; // eax
  __int64 v31; // rcx
  int bIgnoreCase; // [rsp+20h] [rbp-E0h]
  char v33; // [rsp+30h] [rbp-D0h]
  UINT32 length; // [rsp+34h] [rbp-CCh] BYREF
  HSTRING string; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v36; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v37; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v38; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v39; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v40; // [rsp+60h] [rbp-A0h] BYREF
  void (__fastcall ***v41)(_QWORD, void *, __int64 *); // [rsp+68h] [rbp-98h] BYREF
  _BYTE v42[24]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v43; // [rsp+90h] [rbp-70h] BYREF
  __int64 v44; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v45; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v46; // [rsp+B0h] [rbp-50h]
  LPVOID pv; // [rsp+B8h] [rbp-48h] BYREF
  int v48; // [rsp+C0h] [rbp-40h]
  _OWORD v49[2]; // [rsp+D0h] [rbp-30h] BYREF
  _DWORD *v50; // [rsp+F0h] [rbp-10h] BYREF
  _DWORD v51[4]; // [rsp+F8h] [rbp-8h] BYREF
  char *v52; // [rsp+108h] [rbp+8h]
  _DWORD *v53; // [rsp+110h] [rbp+10h] BYREF
  _DWORD v54[4]; // [rsp+118h] [rbp+18h] BYREF
  const WCHAR *v55; // [rsp+128h] [rbp+28h]
  __int128 v56; // [rsp+130h] [rbp+30h]
  _QWORD v57[15]; // [rsp+140h] [rbp+40h] BYREF
  int v58; // [rsp+1B8h] [rbp+B8h] BYREF
  __int128 v59; // [rsp+1C0h] [rbp+C0h]
  __int64 v60[2]; // [rsp+1D0h] [rbp+D0h] BYREF
  __int64 v61; // [rsp+1E0h] [rbp+E0h]
  __int64 v62; // [rsp+1E8h] [rbp+E8h]
  __int128 v63; // [rsp+1F0h] [rbp+F0h]
  __int128 v64; // [rsp+200h] [rbp+100h]
  __int128 v65; // [rsp+210h] [rbp+110h]
  __int128 v66; // [rsp+220h] [rbp+120h]
  LPCWCH lpString1[2]; // [rsp+230h] [rbp+130h] BYREF
  int cchCount1[4]; // [rsp+240h] [rbp+140h]
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v46 = a3;
  v7 = 0;
  LODWORD(v43) = 0;
  v36 = 0;
  v8 = (**(__int64 (__fastcall ***)(struct Windows::ApplicationModel::Activation::IActivatedEventArgs *, GUID *, __int64 *))a1)(
         a1,
         &GUID_03b11a58_5276_4d91_8621_54611864d5fa,
         &v36);
  if ( v8 == -2147467262 )
  {
LABEL_24:
    v20 = v36;
    if ( v36 )
    {
      v36 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    }
    return 0;
  }
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x35F,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\aamextensions.cpp",
      (const char *)(unsigned int)v8,
      bIgnoreCase);
  string = 0;
  v9 = v36;
  v10 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v36 + 48LL);
  WindowsDeleteString(0);
  string = 0;
  v11 = v10(v9, &string);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x362,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\aamextensions.cpp",
      (const char *)(unsigned int)v11,
      bIgnoreCase);
  length = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(string, &length);
  *(_OWORD *)lpString1 = 0;
  *(_OWORD *)cchCount1 = 0;
  std::wstring::_Construct<1,unsigned short const *>(lpString1, StringRawBuffer, length);
  std::wstring::operator=((char *)a4 + 328, lpString1);
  std::wstring::~wstring(lpString1);
  GetStateRepositoryUser(&v39, *((_QWORD *)a4 + 39));
  v13 = (const unsigned __int16 *)((char *)a4 + 64);
  v14 = *((_QWORD *)a4 + 10);
  v15 = (char *)a4 + 64;
  if ( *((_QWORD *)a4 + 11) > 7u )
    v15 = *(char **)v13;
  if ( (_DWORD)v14 )
  {
    if ( *(_WORD *)&v15[2 * (unsigned int)v14] )
      abort();
    v51[0] = 1;
    v51[1] = v14;
    v52 = v15;
    v50 = v51;
  }
  else
  {
    v50 = 0;
  }
  v54[0] = 1;
  v54[1] = 19;
  v55 = L"Windows.StartupTask";
  v53 = v54;
  v57[0] = &v39;
  v57[1] = &v53;
  v57[2] = &v50;
  v57[14] = &qword_180108278;
  _InterlockedIncrement64(&qword_180108278);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Internal::StateRepository::ApplicationExtension,winrt::Windows::Internal::StateRepository::IApplicationExtensionStatics> )
  {
    v44 = 0;
    v58 = 0;
    v59 = 0;
    v16 = (*(__int64 (__fastcall **)(__int64, __int64, _DWORD *, _DWORD *, __int64 *))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Windows::Internal::StateRepository::ApplicationExtension,winrt::Windows::Internal::StateRepository::IApplicationExtensionStatics>
                                                                                     + 176LL))(
            winrt::impl::factory_cache_entry_v<winrt::Windows::Internal::StateRepository::ApplicationExtension,winrt::Windows::Internal::StateRepository::IApplicationExtensionStatics>,
            v39,
            v53,
            v50,
            &v44);
    if ( v16 < 0 )
      winrt::throw_hresult((unsigned int)v16, &v58);
    v38 = v44;
    LODWORD(v43) = 29;
    _InterlockedDecrement64(&qword_180108278);
    v17 = 29;
  }
  else
  {
    _InterlockedDecrement64(&qword_180108278);
    winrt::impl::factory_cache_entry<winrt::Windows::Internal::StateRepository::ApplicationExtension,winrt::Windows::Internal::StateRepository::IApplicationExtensionStatics>::call<_lambda_73b12a83ab77ddd70b39cd532287b8fc_ &>(
      0,
      &v38,
      v57);
    v17 = 5;
  }
  v18 = v17 | 2;
  if ( !(unsigned int)winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::StateRepository::SharedPackageContainer>,winrt::Windows::Internal::StateRepository::SharedPackageContainer>::Size(&v38) )
  {
    v19 = (const unsigned __int16 *)((char *)a4 + 64);
    if ( *((_QWORD *)a4 + 11) > 7u )
      v19 = *(const unsigned __int16 **)v13;
    if ( IsRuntimeBehaviorUniversal(a2, a3, v19) )
    {
      if ( v38 )
        winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v38);
      if ( v39 )
        winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v39);
      WindowsDeleteString(string);
      string = 0;
      goto LABEL_24;
    }
  }
  v22 = 0;
  v23 = winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::StateRepository::SharedPackageContainer>,winrt::Windows::Internal::StateRepository::SharedPackageContainer>::Size(&v38);
  length = v23;
  v24 = v38;
  while ( v22 != v23 )
  {
    v37 = 0;
    v25 = v18 | 0x40;
    LODWORD(v43) = v25;
    *(_DWORD *)v42 = 0;
    *(_OWORD *)&v42[8] = 0;
    v26 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v24 + 48LL))(v24, v22, &v37);
    if ( v26 < 0 )
      winrt::throw_hresult((unsigned int)v26, v42);
    v18 = v25 & 0xFFFFFF9F | 0x20;
    v43 = *(_OWORD *)winrt::impl::consume_Windows_Internal_StateRepository_IApplicationExtension<winrt::Windows::Internal::StateRepository::IApplicationExtension>::Get_Dictionary(
                       &v37,
                       &pv);
    SRDictionaryToPropertySet(&v41, &v43);
    if ( pv )
    {
      CoTaskMemFree_0(pv);
      pv = 0;
      v48 = 0;
    }
    *(_QWORD *)&v56 = L"StartupTask";
    *((_QWORD *)&v56 + 1) = 11;
    if ( v41 )
    {
      v45 = 0;
      (**v41)(
        v41,
        &winrt::impl::guid_v<winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Windows::Foundation::IInspectable>>,
        &v45);
      v7 = v45;
    }
    *(_QWORD *)&v43 = v7;
    *(_OWORD *)v42 = v56;
    GetSingleChildElement(&v40, &v43, v42);
    if ( v7 )
      winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v43);
    *(_QWORD *)&v49[0] = L"@TaskId";
    *((_QWORD *)&v49[0] + 1) = 7;
    *(_OWORD *)v42 = v49[0];
    GetAttribute(lpString1, &v40, v42);
    v27 = WindowsGetStringRawBuffer(string, 0);
    v28 = (const WCHAR *)lpString1;
    if ( *(_QWORD *)&cchCount1[2] > 7u )
      v28 = lpString1[0];
    v7 = 0;
    if ( CompareStringOrdinal(v28, cchCount1[0], v27, -1, 0) == 2 )
    {
      length = 0;
      LODWORD(v49[0]) = 0;
      *(_OWORD *)((char *)v49 + 8) = 0;
      v29 = (*(__int64 (__fastcall **)(__int64, UINT32 *))(*(_QWORD *)v37 + 80LL))(v37, &length);
      if ( v29 >= 0 )
      {
        v33 = 0;
        *(_OWORD *)v60 = 0;
        v61 = 0;
        v62 = 0;
        v63 = 0;
        v64 = 0;
        v65 = 0;
        v66 = 0;
        if ( *((_QWORD *)a4 + 11) > 7u )
          v13 = *(const unsigned __int16 **)v13;
        v30 = StateRepository::Cache::Entity::Application_NoThrow::GetByUserAndApplicationUserModelId(a2, v46, v13, 0);
        if ( v30 >= 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x382,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\aamextensions.cpp",
            (const char *)0x80070490LL,
            (int)v60);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x381,
          (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\aamextensions.cpp",
          (const char *)(unsigned int)v30,
          (int)v60);
      }
      winrt::throw_hresult((unsigned int)v29, v49);
    }
    std::wstring::~wstring(lpString1);
    if ( v40 )
      winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v40);
    if ( v41 )
      winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v41);
    if ( v37 )
      winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v37);
    ++v22;
    v23 = length;
  }
  if ( v24 )
    winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v38);
  if ( v39 )
    winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v39);
  WindowsDeleteString(string);
  string = 0;
  v31 = v36;
  if ( v36 )
  {
    v36 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
  }
  return 1;
}

```

## disassembly

```asm
0x1800b8e2c  push    rbp
0x1800b8e2e  push    rbx
0x1800b8e2f  push    rsi
0x1800b8e30  push    rdi
0x1800b8e31  push    r12
0x1800b8e33  push    r13
0x1800b8e35  push    r14
0x1800b8e37  push    r15
0x1800b8e39  lea     rbp, [rsp-168h]
0x1800b8e41  sub     rsp, 268h
0x1800b8e48  mov     rax, cs:__security_cookie
0x1800b8e4f  xor     rax, rsp
0x1800b8e52  mov     [rbp+1A0h+var_50], rax
0x1800b8e59  mov     r13, r9
0x1800b8e5c  mov     r14, r8
0x1800b8e5f  mov     [rbp+1A0h+var_1F0], r8
0x1800b8e63  mov     r12, rdx
0x1800b8e66  xor     r15d, r15d
0x1800b8e69  mov     dword ptr [rbp+1A0h+var_210], r15d
0x1800b8e6d  mov     [rsp+2A0h+var_260], r15
0x1800b8e72  mov     rax, [rcx]
0x1800b8e75  lea     r8, [rsp+2A0h+var_260]
0x1800b8e7a  lea     rdx, _GUID_03b11a58_5276_4d91_8621_54611864d5fa
0x1800b8e81  mov     rax, [rax]
0x1800b8e84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b8e89  cmp     eax, 80004002h
0x1800b8e8e  jnz     short loc_1800B8E95
0x1800b8e90  jmp     loc_1800B90E5
0x1800b8e95  mov     rcx, [rbp+1A8h]; this
0x1800b8e9c  test    eax, eax
0x1800b8e9e  js      loc_1800B95C8
0x1800b8ea4  mov     [rsp+2A0h+string], r15
0x1800b8ea9  mov     rbx, [rsp+2A0h+var_260]
0x1800b8eae  mov     rax, [rbx]
0x1800b8eb1  mov     rdi, [rax+30h]
0x1800b8eb5  xor     ecx, ecx; string
0x1800b8eb7  call    cs:__imp_WindowsDeleteString
0x1800b8ebe  nop     dword ptr [rax+rax+00h]
0x1800b8ec3  mov     [rsp+2A0h+string], r15
0x1800b8ec8  lea     rdx, [rsp+2A0h+string]
0x1800b8ecd  mov     rcx, rbx
0x1800b8ed0  mov     rax, rdi
0x1800b8ed3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b8ed8  mov     rcx, [rbp+1A8h]; this
0x1800b8edf  test    eax, eax
0x1800b8ee1  js      loc_1800B95DD
0x1800b8ee7  mov     [rsp+2A0h+length], r15d
0x1800b8eec  lea     rdx, [rsp+2A0h+length]; length
0x1800b8ef1  mov     rcx, [rsp+2A0h+string]; string
0x1800b8ef6  call    cs:__imp_WindowsGetStringRawBuffer
0x1800b8efd  nop     dword ptr [rax+rax+00h]
0x1800b8f02  mov     r8d, [rsp+2A0h+length]
0x1800b8f07  xorps   xmm0, xmm0
0x1800b8f0a  movups  xmmword ptr [rbp+1A0h+lpString1], xmm0
0x1800b8f11  xorps   xmm1, xmm1
0x1800b8f14  movdqu  xmmword ptr [rbp+1A0h+cchCount1], xmm1
0x1800b8f1c  mov     rdx, rax
0x1800b8f1f  lea     rcx, [rbp+1A0h+lpString1]
0x1800b8f26  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800b8f2b  lea     rcx, [r13+148h]
0x1800b8f32  lea     rdx, [rbp+1A0h+lpString1]
0x1800b8f39  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800b8f3e  lea     rcx, [rbp+1A0h+lpString1]; void *
0x1800b8f45  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800b8f4a  mov     rdx, [r13+138h]
0x1800b8f51  lea     rcx, [rsp+2A0h+var_248]
0x1800b8f56  call    ?GetStateRepositoryUser@@YA?AUUser@StateRepository@Internal@Windows@winrt@@QEAX@Z; GetStateRepositoryUser(void * const)
0x1800b8f5b  nop
0x1800b8f5c  lea     rdi, [r13+40h]
0x1800b8f60  mov     rdx, [rdi+10h]
0x1800b8f64  mov     rcx, rdi
0x1800b8f67  cmp     qword ptr [rdi+18h], 7
0x1800b8f6c  jbe     short loc_1800B8F71
0x1800b8f6e  mov     rcx, [rdi]
0x1800b8f71  test    edx, edx
0x1800b8f73  jnz     short loc_1800B8F7B
0x1800b8f75  mov     [rbp+1A0h+var_1B0], r15
0x1800b8f79  jmp     short loc_1800B8FA7
0x1800b8f7b  mov     eax, edx
0x1800b8f7d  cmp     [rcx+rax*2], r15w
0x1800b8f82  jz      short loc_1800B8F91
0x1800b8f84  call    cs:__imp_abort
0x1800b8f91  mov     [rbp+1A0h+var_1A8], 1
0x1800b8f98  mov     [rbp+1A0h+var_1A4], edx
0x1800b8f9b  mov     [rbp+1A0h+var_198], rcx
0x1800b8f9f  lea     rax, [rbp+1A0h+var_1A8]
0x1800b8fa3  mov     [rbp+1A0h+var_1B0], rax
0x1800b8fa7  mov     [rbp+1A0h+var_188], 1
0x1800b8fae  mov     [rbp+1A0h+var_184], 13h
0x1800b8fb5  lea     rax, aWindowsStartup; "Windows.StartupTask"
0x1800b8fbc  mov     [rbp+1A0h+var_178], rax
0x1800b8fc0  lea     rax, [rbp+1A0h+var_188]
0x1800b8fc4  mov     [rbp+1A0h+var_190], rax
0x1800b8fc8  lea     rax, [rsp+2A0h+var_248]
0x1800b8fcd  mov     [rbp+1A0h+var_160], rax
0x1800b8fd1  lea     rax, [rbp+1A0h+var_190]
0x1800b8fd5  mov     [rbp+1A0h+var_158], rax
0x1800b8fd9  lea     rax, [rbp+1A0h+var_1B0]
0x1800b8fdd  mov     [rbp+1A0h+var_150], rax
0x1800b8fe1  lea     rax, qword_180108278
0x1800b8fe8  mov     [rbp+1A0h+var_F0], rax
0x1800b8fef  lock inc cs:qword_180108278
0x1800b8ff7  mov     rcx, cs:??$factory_cache_entry_v@UApplicationExtension@StateRepository@Internal@Windows@winrt@@UIApplicationExtensionStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UApplicationExtension@StateRepository@Internal@Windows@winrt@@UIApplicationExtensionStatics@2345@@12@A; factory_cache_entry<winrt::Windows::Internal::StateRepository::ApplicationExtension,winrt::Windows::Internal::StateRepository::IApplicationExtensionStatics>::winrt::factory_cache_entry<winrt::Windows::Internal::StateRepository::ApplicationExtension,winrt::Windows::Internal::StateRepository::IApplicationExtensionStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Internal::StateRepository::ApplicationExtension,winrt::Windows::Internal::StateRepository::IApplicationExtensionStatics>
0x1800b8ffe  test    rcx, rcx
0x1800b9001  jz      short loc_1800B9063
0x1800b9003  mov     [rbp+1A0h+var_200], r15
0x1800b9007  mov     [rbp+1A0h+var_E8], r15d
0x1800b900e  xorps   xmm0, xmm0
0x1800b9011  movdqu  [rbp+1A0h+var_E0], xmm0
0x1800b9019  mov     rax, [rcx]
0x1800b901c  lea     rdx, [rbp+1A0h+var_200]
0x1800b9020  mov     qword ptr [rsp+2A0h+bIgnoreCase], rdx
0x1800b9025  mov     r9, [rbp+1A0h+var_1B0]
0x1800b9029  mov     r8, [rbp+1A0h+var_190]
0x1800b902d  mov     rdx, [rsp+2A0h+var_248]
0x1800b9032  mov     rax, [rax+0B0h]
0x1800b9039  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b903e  test    eax, eax
0x1800b9040  js      loc_1800B95F2
0x1800b9046  mov     rax, [rbp+1A0h+var_200]
0x1800b904a  mov     [rsp+2A0h+var_250], rax
0x1800b904f  mov     dword ptr [rbp+1A0h+var_210], 1Dh
0x1800b9056  lock dec cs:qword_180108278
0x1800b905e  mov     esi, dword ptr [rbp+1A0h+var_210]
0x1800b9061  jmp     short loc_1800B907E
0x1800b9063  lock dec cs:qword_180108278
0x1800b906b  lea     r8, [rbp+1A0h+var_160]
0x1800b906f  lea     rdx, [rsp+2A0h+var_250]
0x1800b9074  call    ??$call@AEAV_lambda_73b12a83ab77ddd70b39cd532287b8fc_@@@?$factory_cache_entry@UApplicationExtension@StateRepository@Internal@Windows@winrt@@UIApplicationExtensionStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_73b12a83ab77ddd70b39cd532287b8fc_@@@Z
0x1800b9079  mov     esi, 5
0x1800b907e  or      esi, 2
0x1800b9081  lea     rcx, [rsp+2A0h+var_250]
0x1800b9086  call    ?Size@?$consume_Windows_Foundation_Collections_IVectorView@U?$IVectorView@USharedPackageContainer@StateRepository@Internal@Windows@winrt@@@Collections@Foundation@Windows@winrt@@USharedPackageContainer@StateRepository@Internal@45@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::StateRepository::SharedPackageContainer>,winrt::Windows::Internal::StateRepository::SharedPackageContainer>::Size(void)
0x1800b908b  test    eax, eax
0x1800b908d  jnz     short loc_1800B9108
0x1800b908f  mov     r8, rdi
0x1800b9092  cmp     qword ptr [rdi+18h], 7
0x1800b9097  jbe     short loc_1800B909C
0x1800b9099  mov     r8, [rdi]; unsigned __int16 *
0x1800b909c  mov     rdx, r14; __int64
0x1800b909f  mov     rcx, r12; struct StateRepository::Cache::Manager_NoThrow *
0x1800b90a2  call    ?IsRuntimeBehaviorUniversal@@YA_NAEAVManager_NoThrow@Cache@StateRepository@@_JPEBG@Z; IsRuntimeBehaviorUniversal(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *)
0x1800b90a7  test    al, al
0x1800b90a9  jz      short loc_1800B9108
0x1800b90ab  cmp     [rsp+2A0h+var_250], r15
0x1800b90b0  jz      short loc_1800B90BD
0x1800b90b2  lea     rcx, [rsp+2A0h+var_250]
0x1800b90b7  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x1800b90bc  nop
0x1800b90bd  cmp     [rsp+2A0h+var_248], r15
0x1800b90c2  jz      short loc_1800B90CF
0x1800b90c4  lea     rcx, [rsp+2A0h+var_248]
0x1800b90c9  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x1800b90ce  nop
0x1800b90cf  mov     rcx, [rsp+2A0h+string]; string
0x1800b90d4  call    cs:__imp_WindowsDeleteString
0x1800b90db  nop     dword ptr [rax+rax+00h]
0x1800b90e0  mov     [rsp+2A0h+string], r15
0x1800b90e5  mov     rcx, [rsp+2A0h+var_260]
0x1800b90ea  test    rcx, rcx
0x1800b90ed  jz      short loc_1800B9101
0x1800b90ef  mov     [rsp+2A0h+var_260], r15
0x1800b90f4  mov     rax, [rcx]
0x1800b90f7  mov     rax, [rax+10h]
0x1800b90fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9100  nop
0x1800b9101  xor     al, al
0x1800b9103  jmp     loc_1800B9582
0x1800b9108  mov     r14d, r15d
0x1800b910b  lea     rcx, [rsp+2A0h+var_250]
0x1800b9110  call    ?Size@?$consume_Windows_Foundation_Collections_IVectorView@U?$IVectorView@USharedPackageContainer@StateRepository@Internal@Windows@winrt@@@Collections@Foundation@Windows@winrt@@USharedPackageContainer@StateRepository@Internal@45@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::StateRepository::SharedPackageContainer>,winrt::Windows::Internal::StateRepository::SharedPackageContainer>::Size(void)
0x1800b9115  mov     [rsp+2A0h+length], eax
0x1800b9119  mov     rbx, [rsp+2A0h+var_250]
0x1800b911e  cmp     r14d, eax
0x1800b9121  jz      loc_1800B952C
0x1800b9127  mov     [rsp+2A0h+var_258], r15
0x1800b912c  or      esi, 40h
0x1800b912f  mov     dword ptr [rbp+1A0h+var_210], esi
0x1800b9132  mov     dword ptr [rsp+2A0h+var_230], r15d
0x1800b9137  xorps   xmm0, xmm0
0x1800b913a  movdqu  [rsp+2A0h+var_230+8], xmm0
0x1800b9140  mov     rax, [rbx]
0x1800b9143  lea     r8, [rsp+2A0h+var_258]
0x1800b9148  mov     edx, r14d
0x1800b914b  mov     rcx, rbx
0x1800b914e  mov     rax, [rax+30h]
0x1800b9152  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9157  test    eax, eax
0x1800b9159  js      loc_1800B95BB
0x1800b915f  and     esi, 0FFFFFFBFh
0x1800b9162  or      esi, 20h
0x1800b9165  lea     rdx, [rbp+1A0h+pv]
0x1800b9169  lea     rcx, [rsp+2A0h+var_258]
0x1800b916e  call    ?Get_Dictionary@?$consume_Windows_Internal_StateRepository_IApplicationExtension@UIApplicationExtension@StateRepository@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_StateRepository_IApplicationExtension<winrt::Windows::Internal::StateRepository::IApplicationExtension>::Get_Dictionary(void)
0x1800b9173  nop
0x1800b9174  movups  xmm0, xmmword ptr [rax]
0x1800b9177  movdqu  [rbp+1A0h+var_210], xmm0
0x1800b917c  lea     rdx, [rbp+1A0h+var_210]
0x1800b9180  lea     rcx, [rsp+2A0h+var_238]
0x1800b9185  call    ?SRDictionaryToPropertySet@@YA?AUIPropertySet@Collections@Foundation@Windows@winrt@@U?$array_view@E@5@@Z; SRDictionaryToPropertySet(winrt::array_view<uchar>)
0x1800b918a  nop
0x1800b918b  mov     rcx, [rbp+1A0h+pv]; pv
0x1800b918f  test    rcx, rcx
0x1800b9192  jz      short loc_1800B91A1
0x1800b9194  call    CoTaskMemFree_0
0x1800b9199  mov     [rbp+1A0h+pv], r15
0x1800b919d  mov     [rbp+1A0h+var_1E0], r15d
0x1800b91a1  lea     rax, aStartuptask; "StartupTask"
0x1800b91a8  mov     qword ptr [rbp+1A0h+var_170], rax
0x1800b91ac  mov     qword ptr [rbp+1A0h+var_170+8], 0Bh
0x1800b91b4  mov     rcx, [rsp+2A0h+var_238]
0x1800b91b9  test    rcx, rcx
0x1800b91bc  jz      short loc_1800B91DC
0x1800b91be  mov     [rbp+1A0h+var_1F8], r15
0x1800b91c2  mov     rax, [rcx]
0x1800b91c5  lea     r8, [rbp+1A0h+var_1F8]
0x1800b91c9  lea     rdx, ??$guid_v@U?$IMap@Uhstring@winrt@@UIInspectable@Foundation@Windows@2@@Collections@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Windows::Foundation::IInspectable>>
0x1800b91d0  mov     rax, [rax]
0x1800b91d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b91d8  mov     r15, [rbp+1A0h+var_1F8]
0x1800b91dc  mov     qword ptr [rbp+1A0h+var_210], r15
0x1800b91e0  movaps  xmm0, [rbp+1A0h+var_170]
0x1800b91e4  movdqa  [rsp+2A0h+var_230], xmm0
0x1800b91ea  lea     r8, [rsp+2A0h+var_230]
0x1800b91ef  lea     rdx, [rbp+1A0h+var_210]
0x1800b91f3  lea     rcx, [rsp+2A0h+var_240]
0x1800b91f8  call    ?GetSingleChildElement@@YA?AU?$IMap@Uhstring@winrt@@UIInspectable@Foundation@Windows@2@@Collections@Foundation@Windows@winrt@@AEBU12345@V?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; GetSingleChildElement(winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Windows::Foundation::IInspectable> const &,std::basic_string_view<ushort>)
0x1800b91fd  nop
0x1800b91fe  test    r15, r15
0x1800b9201  jz      short loc_1800B920C
0x1800b9203  lea     rcx, [rbp+1A0h+var_210]
0x1800b9207  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x1800b920c  lea     rax, aTaskid; "@TaskId"
0x1800b9213  mov     qword ptr [rbp+1A0h+var_1D0], rax
0x1800b9217  mov     qword ptr [rbp+1A0h+var_1D0+8], 7
0x1800b921f  movaps  xmm0, xmmword ptr [rbp+1A0h+var_1D0]
0x1800b9223  movdqa  [rsp+2A0h+var_230], xmm0
0x1800b9229  lea     r8, [rsp+2A0h+var_230]
0x1800b922e  lea     rdx, [rsp+2A0h+var_240]
0x1800b9233  lea     rcx, [rbp+1A0h+lpString1]
0x1800b923a  call    ?GetAttribute@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU?$IMap@Uhstring@winrt@@UIInspectable@Foundation@Windows@2@@Collections@Foundation@Windows@winrt@@V?$basic_string_view@GU?$char_traits@G@std@@@2@@Z; GetAttribute(winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Windows::Foundation::IInspectable> const &,std::basic_string_view<ushort>)
0x1800b923f  nop
0x1800b9240  xor     edx, edx; length
0x1800b9242  mov     rcx, [rsp+2A0h+string]; string
0x1800b9247  call    cs:__imp_WindowsGetStringRawBuffer
0x1800b924e  nop     dword ptr [rax+rax+00h]
0x1800b9253  lea     rcx, [rbp+1A0h+lpString1]
0x1800b925a  cmp     qword ptr [rbp+1A0h+cchCount1+8], 7
0x1800b9262  cmova   rcx, [rbp+1A0h+lpString1]; lpString1
0x1800b926a  xor     r15d, r15d
0x1800b926d  mov     [rsp+2A0h+bIgnoreCase], r15d; bIgnoreCase
0x1800b9272  or      r9d, 0FFFFFFFFh; cchCount2
0x1800b9276  mov     r8, rax; lpString2
0x1800b9279  mov     edx, [rbp+1A0h+cchCount1]; cchCount1
0x1800b927f  call    cs:__imp_CompareStringOrdinal
0x1800b9286  nop     dword ptr [rax+rax+00h]
0x1800b928b  cmp     eax, 2
0x1800b928e  jz      short loc_1800B92DE
0x1800b9290  lea     rcx, [rbp+1A0h+lpString1]; void *
0x1800b9297  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800b929c  nop
0x1800b929d  cmp     [rsp+2A0h+var_240], r15
0x1800b92a2  jz      short loc_1800B92AF
0x1800b92a4  lea     rcx, [rsp+2A0h+var_240]
0x1800b92a9  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x1800b92ae  nop
0x1800b92af  cmp     [rsp+2A0h+var_238], r15
0x1800b92b4  jz      short loc_1800B92C1
0x1800b92b6  lea     rcx, [rsp+2A0h+var_238]
0x1800b92bb  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x1800b92c0  nop
0x1800b92c1  cmp     [rsp+2A0h+var_258], r15
0x1800b92c6  jz      short loc_1800B92D2
0x1800b92c8  lea     rcx, [rsp+2A0h+var_258]
0x1800b92cd  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x1800b92d2  inc     r14d
0x1800b92d5  mov     eax, [rsp+2A0h+length]
0x1800b92d9  jmp     loc_1800B911E
0x1800b92de  mov     [rsp+2A0h+length], r15d
0x1800b92e3  mov     dword ptr [rbp+1A0h+var_1D0], r15d
0x1800b92e7  xorps   xmm0, xmm0
0x1800b92ea  movdqu  xmmword ptr [rbp+1A0h+var_1D0+8], xmm0
0x1800b92ef  mov     rcx, [rsp+2A0h+var_258]
0x1800b92f4  mov     rax, [rcx]
0x1800b92f7  lea     rdx, [rsp+2A0h+length]
0x1800b92fc  mov     rax, [rax+50h]
0x1800b9300  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9305  test    eax, eax
0x1800b9307  js      loc_1800B9601
0x1800b930d  mov     [rsp+2A0h+var_270], r15b
0x1800b9312  xorps   xmm0, xmm0
0x1800b9315  movdqa  xmmword ptr [rbp+1A0h+var_D0], xmm0
0x1800b931d  mov     [rbp+1A0h+var_C0], r15
0x1800b9324  mov     [rbp+1A0h+var_B8], r15
0x1800b932b  movdqa  [rbp+1A0h+var_B0], xmm0
0x1800b9333  xorps   xmm1, xmm1
0x1800b9336  movdqa  [rbp+1A0h+var_A0], xmm1
0x1800b933e  movdqa  [rbp+1A0h+var_90], xmm0
0x1800b9346  movdqa  [rbp+1A0h+var_80], xmm1
0x1800b934e  cmp     qword ptr [rdi+18h], 7
  ... truncated ...
```
