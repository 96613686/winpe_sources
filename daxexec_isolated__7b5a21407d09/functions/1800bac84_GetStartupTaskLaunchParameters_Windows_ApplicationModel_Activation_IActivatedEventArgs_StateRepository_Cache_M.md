# GetStartupTaskLaunchParameters(Windows::ApplicationModel::Activation::IActivatedEventArgs *,StateRepository::Cache::Manager_NoThrow &,__int64,ActivationProperties &)

- ea: `0x1800bac84`
- end: `0x1800bb4a9`
- name: `?GetStartupTaskLaunchParameters@@YA_NPEAUIActivatedEventArgs@Activation@ApplicationModel@Windows@@AEAVManager_NoThrow@Cache@StateRepository@@_JAEAUActivationProperties@@@Z`
- size: `2085`
- prototype: `bool(struct Windows::ApplicationModel::Activation::IActivatedEventArgs *, struct StateRepository::Cache::Manager_NoThrow *, __int64, struct ActivationProperties *)`
- caller_count: `1`
- callee_count: `25`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800b8250`

## callees

- `0x180004f70`
- `0x1800061ba`
- `0x18000ff24`
- `0x1800125f4`
- `0x180012828`
- `0x180012fb8`
- `0x180013510`
- `0x1800136dc`
- `0x18003ab48`
- `0x18003ce48`
- `0x180068bd8`
- `0x18006d0c4`
- `0x1800b2f14`
- `0x1800b3980`
- `0x1800b573c`
- `0x1800b6c58`
- `0x1800b7d2c`
- `0x1800babac`
- `0x1800bac84`
- `0x1800bb4b0`
- `0x1800bb734`
- `0x1800bba18`
- `0x1800bc8bc`
- `0x1800bd274`
- `0x1800cd010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800badf5`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800badf5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800bb0f8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800bb0f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bad23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800baf57`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bb399`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bad23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800baf57`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bb399`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800bad62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800bb0c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800bad62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800bb0c0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800bb31a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800bb31a`

## string_xrefs

- `0x1800bb24d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x1800bb3ef`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800bb413`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800bb428`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800bb455`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800bb46d`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800bb482`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800bb497`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800bb05c`: `StartupTask`
- `0x1800bb091`: `@TaskId`
- `0x1800bae35`: `Windows.StartupTask`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
char __fastcall GetStartupTaskLaunchParameters(
        struct Windows::ApplicationModel::Activation::IActivatedEventArgs *a1,
        struct StateRepository::Cache::Manager_NoThrow *a2,
        __int64 a3,
        struct ActivationProperties *a4)
{
  int v7; // eax
  __int64 v8; // rcx
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, HSTRING *); // rbx
  int v11; // eax
  PCWSTR StringRawBuffer; // rax
  const WCHAR **v13; // rdi
  __int64 v14; // rdx
  const WCHAR *v15; // rcx
  int v16; // eax
  void (__fastcall ***v17)(_QWORD, __int64 *, UINT32 *); // rbx
  int v18; // esi
  unsigned int v19; // esi
  const unsigned __int16 *v20; // r8
  bool v21; // al
  __int64 v22; // r14
  unsigned int v24; // r15d
  int v25; // eax
  int v26; // esi
  int v27; // eax
  const WCHAR *v28; // rax
  const WCHAR *v29; // rcx
  int v30; // eax
  int v31; // eax
  __int64 v32; // rcx
  int bIgnoreCase; // [rsp+20h] [rbp-E0h]
  char v34; // [rsp+30h] [rbp-D0h]
  UINT32 length[4]; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING string; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v37; // [rsp+58h] [rbp-A8h] BYREF
  void (__fastcall ***v38)(_QWORD, __int64 *, UINT32 *); // [rsp+60h] [rbp-A0h] BYREF
  __int64 v39; // [rsp+68h] [rbp-98h] BYREF
  void (__fastcall ***v40)(_QWORD, __int64 *, UINT32 *); // [rsp+70h] [rbp-90h] BYREF
  __int64 v41; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v42[2]; // [rsp+80h] [rbp-80h] BYREF
  const wchar_t *v43; // [rsp+90h] [rbp-70h] BYREF
  __int128 v44; // [rsp+98h] [rbp-68h]
  int v45; // [rsp+B0h] [rbp-50h]
  const wchar_t *v46; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v47; // [rsp+C8h] [rbp-38h] BYREF
  const WCHAR *v48; // [rsp+D8h] [rbp-28h]
  __int64 v49; // [rsp+E0h] [rbp-20h]
  LPVOID pv; // [rsp+E8h] [rbp-18h] BYREF
  int v51; // [rsp+F0h] [rbp-10h]
  __int64 v52[2]; // [rsp+150h] [rbp+50h] BYREF
  __int64 v53; // [rsp+160h] [rbp+60h]
  __int64 v54; // [rsp+168h] [rbp+68h]
  __int128 v55; // [rsp+170h] [rbp+70h]
  __int128 v56; // [rsp+180h] [rbp+80h]
  __int128 v57; // [rsp+190h] [rbp+90h]
  __int128 v58; // [rsp+1A0h] [rbp+A0h]
  LPCWCH lpString1[4]; // [rsp+1B0h] [rbp+B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+128h]

  v49 = a3;
  length[0] = 0;
  v37 = 0;
  v7 = (**(__int64 (__fastcall ***)(struct Windows::ApplicationModel::Activation::IActivatedEventArgs *, GUID *, __int64 *))a1)(
         a1,
         &GUID_03b11a58_5276_4d91_8621_54611864d5fa,
         &v37);
  if ( v7 == -2147467262 )
  {
    v8 = v37;
    if ( !v37 )
      return 0;
    v37 = 0;
LABEL_29:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    return 0;
  }
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x35F,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\aamextensions.cpp",
      (const char *)(unsigned int)v7,
      bIgnoreCase);
  string = 0;
  v9 = v37;
  v10 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v37 + 48LL);
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
  length[0] = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(string, length);
  memset(lpString1, 0, sizeof(lpString1));
  std::wstring::_Construct<1,unsigned short const *>(lpString1, StringRawBuffer, length[0]);
  std::wstring::operator=((char *)a4 + 328, lpString1);
  std::wstring::~wstring(lpString1);
  GetStateRepositoryUser(&v41, *((_QWORD *)a4 + 39));
  v13 = (const WCHAR **)((char *)a4 + 64);
  v14 = *((_QWORD *)a4 + 10);
  if ( *((_QWORD *)a4 + 11) <= 7u )
    v15 = (const WCHAR *)((char *)a4 + 64);
  else
    v15 = *v13;
  if ( (_DWORD)v14 )
  {
    if ( v15[(unsigned int)v14] )
      abort();
    LODWORD(lpString1[1]) = 1;
    HIDWORD(lpString1[1]) = v14;
    lpString1[3] = v15;
    lpString1[0] = (LPCWCH)&lpString1[1];
  }
  else
  {
    lpString1[0] = 0;
  }
  *(_QWORD *)&v47 = 0x1300000001LL;
  v48 = L"Windows.StartupTask";
  v46 = (const wchar_t *)&v47;
  v43 = (const wchar_t *)&v41;
  *(_QWORD *)&v44 = &v46;
  *((_QWORD *)&v44 + 1) = lpString1;
  v42[0] = &qword_180109E78;
  _InterlockedIncrement64(&qword_180109E78);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Internal::StateRepository::ApplicationExtension,winrt::Windows::Internal::StateRepository::IApplicationExtensionStatics> )
  {
    v38 = 0;
    LODWORD(v43) = 0;
    v44 = 0;
    v16 = (*(__int64 (__fastcall **)(__int64, __int64, const wchar_t *, LPCWCH, void (__fastcall ****)(_QWORD, __int64 *, UINT32 *)))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Windows::Internal::StateRepository::ApplicationExtension,winrt::Windows::Internal::StateRepository::IApplicationExtensionStatics> + 176LL))(
            winrt::impl::factory_cache_entry_v<winrt::Windows::Internal::StateRepository::ApplicationExtension,winrt::Windows::Internal::StateRepository::IApplicationExtensionStatics>,
            v41,
            v46,
            lpString1[0],
            &v38);
    if ( v16 < 0 )
      winrt::throw_hresult((unsigned int)v16, &v43);
    v17 = v38;
    v40 = v38;
    v18 = 29;
    _InterlockedDecrement64(&qword_180109E78);
  }
  else
  {
    _InterlockedDecrement64(&qword_180109E78);
    winrt::impl::factory_cache_entry<winrt::Windows::Internal::StateRepository::ApplicationExtension,winrt::Windows::Internal::StateRepository::IApplicationExtensionStatics>::call<_lambda_73b12a83ab77ddd70b39cd532287b8fc_ &>(
      0,
      &v40,
      &v43);
    v18 = 5;
    v17 = v40;
  }
  v19 = v18 | 2;
  if ( (unsigned int)winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::StateRepository::SharedPackageContainer>,winrt::Windows::Internal::StateRepository::SharedPackageContainer>::Size(&v40) )
  {
    v22 = 0;
  }
  else
  {
    if ( *((_QWORD *)a4 + 11) <= 7u )
      v20 = (const unsigned __int16 *)((char *)a4 + 64);
    else
      v20 = *v13;
    v21 = IsRuntimeBehaviorUniversal(a2, a3, v20);
    v22 = 0;
    if ( v21 )
    {
      if ( v17 )
        winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v40);
      if ( v41 )
        winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v41);
      WindowsDeleteString(string);
      string = 0;
      v8 = v37;
      if ( !v37 )
        return 0;
      v37 = 0;
      goto LABEL_29;
    }
  }
  v24 = 0;
  v25 = winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::StateRepository::SharedPackageContainer>,winrt::Windows::Internal::StateRepository::SharedPackageContainer>::Size(&v40);
  v45 = v25;
  while ( v24 != v25 )
  {
    v39 = 0;
    v26 = v19 | 0x40;
    length[0] = v26;
    LODWORD(lpString1[0]) = 0;
    *(_OWORD *)&lpString1[1] = 0;
    v27 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64 *))(*v17)[6])(v17, v24, &v39);
    if ( v27 < 0 )
      winrt::throw_hresult((unsigned int)v27, lpString1);
    length[0] = v26 & 0xFFFFFFBF;
    v19 = v26 & 0xFFFFFF9F | 0x20;
    *(_OWORD *)length = *(_OWORD *)winrt::impl::consume_Windows_Internal_StateRepository_IApplicationExtension<winrt::Windows::Internal::StateRepository::IApplicationExtension>::Get_Dictionary(
                                     &v39,
                                     &pv);
    SRDictionaryToPropertySet(&v38, length);
    if ( pv )
    {
      CoTaskMemFree_0(pv);
      pv = 0;
      v51 = 0;
    }
    *(_QWORD *)length = 0;
    if ( v38 )
    {
      (**v38)(
        v38,
        winrt::impl::guid_v<winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Windows::Foundation::IInspectable>>,
        length);
      v22 = *(_QWORD *)length;
    }
    v46 = L"StartupTask";
    *(_QWORD *)&v47 = 11;
    GetSingleChildElement(v42, length, &v46);
    if ( v22 )
      winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(length);
    v43 = L"@TaskId";
    *(_QWORD *)&v44 = 7;
    GetAttribute(lpString1, v42, &v43);
    v28 = WindowsGetStringRawBuffer(string, 0);
    v29 = (const WCHAR *)lpString1;
    if ( lpString1[3] > (LPCWCH)7 )
      v29 = lpString1[0];
    v22 = 0;
    if ( CompareStringOrdinal(v29, (int)lpString1[2], v28, -1, 0) == 2 )
    {
      length[0] = 0;
      LODWORD(v46) = 0;
      v47 = 0;
      v30 = (*(__int64 (__fastcall **)(__int64, UINT32 *))(*(_QWORD *)v39 + 80LL))(v39, length);
      if ( v30 >= 0 )
      {
        v34 = 0;
        *(_OWORD *)v52 = 0;
        v53 = 0;
        v54 = 0;
        v55 = 0;
        v56 = 0;
        v57 = 0;
        v58 = 0;
        if ( *((_QWORD *)a4 + 11) > 7u )
          v13 = (const WCHAR **)*v13;
        v31 = StateRepository::Cache::Entity::Application_NoThrow::GetByUserAndApplicationUserModelId(a2, v49, v13, 0);
        if ( v31 >= 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x382,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\aamextensions.cpp",
            (const char *)0x80070490LL,
            (int)v52);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x381,
          (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\aamextensions.cpp",
          (const char *)(unsigned int)v31,
          (int)v52);
      }
      winrt::throw_hresult((unsigned int)v30, &v46);
    }
    std::wstring::~wstring(lpString1);
    if ( v42[0] )
      winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(v42);
    if ( v38 )
      winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v38);
    if ( v39 )
      winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v39);
    ++v24;
    v25 = v45;
  }
  if ( v17 )
    winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v40);
  if ( v41 )
    winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v41);
  WindowsDeleteString(string);
  string = 0;
  v32 = v37;
  if ( v37 )
  {
    v37 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
  }
  return 1;
}

```

## disassembly

```asm
0x1800bac84  push    rbp
0x1800bac86  push    rbx
0x1800bac87  push    rsi
0x1800bac88  push    rdi
0x1800bac89  push    r12
0x1800bac8b  push    r13
0x1800bac8d  push    r14
0x1800bac8f  push    r15
0x1800bac91  lea     rbp, [rsp-0E8h]
0x1800bac99  sub     rsp, 1E8h
0x1800baca0  mov     rax, cs:__security_cookie
0x1800baca7  xor     rax, rsp
0x1800bacaa  mov     [rbp+120h+var_50], rax
0x1800bacb1  mov     r13, r9
0x1800bacb4  mov     r14, r8
0x1800bacb7  mov     [rbp+120h+var_140], r8
0x1800bacbb  mov     r12, rdx
0x1800bacbe  xor     r15d, r15d
0x1800bacc1  mov     [rsp+220h+length], r15d
0x1800bacc6  mov     [rsp+220h+var_1C8], r15
0x1800baccb  mov     rax, [rcx]
0x1800bacce  lea     r8, [rsp+220h+var_1C8]
0x1800bacd3  lea     rdx, _GUID_03b11a58_5276_4d91_8621_54611864d5fa
0x1800bacda  mov     rax, [rax]
0x1800bacdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bace2  cmp     eax, 80004002h
0x1800bace7  jnz     short loc_1800BAD01
0x1800bace9  mov     rcx, [rsp+220h+var_1C8]
0x1800bacee  test    rcx, rcx
0x1800bacf1  jz      loc_1800BAF84
0x1800bacf7  mov     [rsp+220h+var_1C8], r15
0x1800bacfc  jmp     loc_1800BAF77
0x1800bad01  mov     rcx, [rbp+128h]; this
0x1800bad08  test    eax, eax
0x1800bad0a  js      loc_1800BB410
0x1800bad10  mov     [rsp+220h+string], r15
0x1800bad15  mov     rdi, [rsp+220h+var_1C8]
0x1800bad1a  mov     rax, [rdi]
0x1800bad1d  mov     rbx, [rax+30h]
0x1800bad21  xor     ecx, ecx; string
0x1800bad23  call    cs:__imp_WindowsDeleteString
0x1800bad2a  nop     dword ptr [rax+rax+00h]
0x1800bad2f  mov     [rsp+220h+string], r15
0x1800bad34  lea     rdx, [rsp+220h+string]
0x1800bad39  mov     rcx, rdi
0x1800bad3c  mov     rax, rbx
0x1800bad3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bad44  mov     rcx, [rbp+128h]; this
0x1800bad4b  test    eax, eax
0x1800bad4d  js      loc_1800BB425
0x1800bad53  mov     [rsp+220h+length], r15d
0x1800bad58  lea     rdx, [rsp+220h+length]; length
0x1800bad5d  mov     rcx, [rsp+220h+string]; string
0x1800bad62  call    cs:__imp_WindowsGetStringRawBuffer
0x1800bad69  nop     dword ptr [rax+rax+00h]
0x1800bad6e  xorps   xmm0, xmm0
0x1800bad71  movups  xmmword ptr [rbp+120h+lpString1], xmm0
0x1800bad78  xorps   xmm1, xmm1
0x1800bad7b  movdqu  xmmword ptr [rbp+120h+cchCount1], xmm1
0x1800bad83  mov     r8d, [rsp+220h+length]
0x1800bad88  mov     rdx, rax
0x1800bad8b  lea     rcx, [rbp+120h+lpString1]
0x1800bad92  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800bad97  lea     rcx, [r13+148h]
0x1800bad9e  lea     rdx, [rbp+120h+lpString1]
0x1800bada5  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800badaa  lea     rcx, [rbp+120h+lpString1]; void *
0x1800badb1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800badb6  mov     rdx, [r13+138h]
0x1800badbd  lea     rcx, [rsp+220h+var_1A8]
0x1800badc2  call    ?GetStateRepositoryUser@@YA?AUUser@StateRepository@Internal@Windows@winrt@@QEAX@Z; GetStateRepositoryUser(void * const)
0x1800badc7  nop
0x1800badc8  lea     rdi, [r13+40h]
0x1800badcc  mov     rdx, [rdi+10h]
0x1800badd0  cmp     qword ptr [rdi+18h], 7
0x1800badd5  jbe     short loc_1800BADDC
0x1800badd7  mov     rcx, [rdi]
0x1800badda  jmp     short loc_1800BADDF
0x1800baddc  mov     rcx, rdi
0x1800baddf  test    edx, edx
0x1800bade1  jnz     short loc_1800BADEC
0x1800bade3  mov     [rbp+120h+lpString1], r15
0x1800badea  jmp     short loc_1800BAE27
0x1800badec  mov     eax, edx
0x1800badee  cmp     [rcx+rax*2], r15w
0x1800badf3  jz      short loc_1800BAE02
0x1800badf5  call    cs:__imp_abort
0x1800bae02  mov     dword ptr [rbp+120h+lpString1+8], 1
0x1800bae0c  mov     dword ptr [rbp+120h+lpString1+0Ch], edx
0x1800bae12  mov     qword ptr [rbp+120h+cchCount1+8], rcx
0x1800bae19  lea     rax, [rbp+120h+lpString1+8]
0x1800bae20  mov     [rbp+120h+lpString1], rax
0x1800bae27  mov     dword ptr [rbp+120h+var_158], 1
0x1800bae2e  mov     dword ptr [rbp+120h+var_158+4], 13h
0x1800bae35  lea     rax, aWindowsStartup; "Windows.StartupTask"
0x1800bae3c  mov     [rbp+120h+var_148], rax
0x1800bae40  lea     rax, [rbp+120h+var_158]
0x1800bae44  mov     [rbp+120h+var_160], rax
0x1800bae48  lea     rax, [rsp+220h+var_1A8]
0x1800bae4d  mov     [rbp+120h+var_190], rax
0x1800bae51  lea     rax, [rbp+120h+var_160]
0x1800bae55  mov     qword ptr [rbp+120h+var_188], rax
0x1800bae59  lea     rax, [rbp+120h+lpString1]
0x1800bae60  mov     qword ptr [rbp+120h+var_188+8], rax
0x1800bae64  lea     rax, qword_180109E78
0x1800bae6b  mov     [rbp+120h+var_1A0], rax
0x1800bae6f  lock inc cs:qword_180109E78
0x1800bae77  mov     rcx, cs:??$factory_cache_entry_v@UApplicationExtension@StateRepository@Internal@Windows@winrt@@UIApplicationExtensionStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UApplicationExtension@StateRepository@Internal@Windows@winrt@@UIApplicationExtensionStatics@2345@@12@A; factory_cache_entry<winrt::Windows::Internal::StateRepository::ApplicationExtension,winrt::Windows::Internal::StateRepository::IApplicationExtensionStatics>::winrt::factory_cache_entry<winrt::Windows::Internal::StateRepository::ApplicationExtension,winrt::Windows::Internal::StateRepository::IApplicationExtensionStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Internal::StateRepository::ApplicationExtension,winrt::Windows::Internal::StateRepository::IApplicationExtensionStatics>
0x1800bae7e  test    rcx, rcx
0x1800bae81  jz      short loc_1800BAEDE
0x1800bae83  mov     [rsp+220h+var_1C0], r15
0x1800bae88  mov     dword ptr [rbp+120h+var_190], r15d
0x1800bae8c  xorps   xmm0, xmm0
0x1800bae8f  movdqu  [rbp+120h+var_188], xmm0
0x1800bae94  mov     rax, [rcx]
0x1800bae97  lea     rdx, [rsp+220h+var_1C0]
0x1800bae9c  mov     qword ptr [rsp+220h+bIgnoreCase], rdx
0x1800baea1  mov     r9, [rbp+120h+lpString1]
0x1800baea8  mov     r8, [rbp+120h+var_160]
0x1800baeac  mov     rdx, [rsp+220h+var_1A8]
0x1800baeb1  mov     rax, [rax+0B0h]
0x1800baeb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800baebd  test    eax, eax
0x1800baebf  js      loc_1800BB43A
0x1800baec5  mov     rbx, [rsp+220h+var_1C0]
0x1800baeca  mov     [rsp+220h+var_1B0], rbx
0x1800baecf  mov     esi, 1Dh
0x1800baed4  lock dec cs:qword_180109E78
0x1800baedc  jmp     short loc_1800BAEFE
0x1800baede  lock dec cs:qword_180109E78
0x1800baee6  lea     r8, [rbp+120h+var_190]
0x1800baeea  lea     rdx, [rsp+220h+var_1B0]
0x1800baeef  call    ??$call@AEAV_lambda_73b12a83ab77ddd70b39cd532287b8fc_@@@?$factory_cache_entry@UApplicationExtension@StateRepository@Internal@Windows@winrt@@UIApplicationExtensionStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_73b12a83ab77ddd70b39cd532287b8fc_@@@Z
0x1800baef4  mov     esi, 5
0x1800baef9  mov     rbx, [rsp+220h+var_1B0]
0x1800baefe  or      esi, 2
0x1800baf01  lea     rcx, [rsp+220h+var_1B0]
0x1800baf06  call    ?Size@?$consume_Windows_Foundation_Collections_IVectorView@U?$IVectorView@USharedPackageContainer@StateRepository@Internal@Windows@winrt@@@Collections@Foundation@Windows@winrt@@USharedPackageContainer@StateRepository@Internal@45@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::StateRepository::SharedPackageContainer>,winrt::Windows::Internal::StateRepository::SharedPackageContainer>::Size(void)
0x1800baf0b  test    eax, eax
0x1800baf0d  jnz     short loc_1800BAF8B
0x1800baf0f  cmp     qword ptr [rdi+18h], 7
0x1800baf14  jbe     short loc_1800BAF1B
0x1800baf16  mov     r8, [rdi]
0x1800baf19  jmp     short loc_1800BAF1E
0x1800baf1b  mov     r8, rdi; unsigned __int16 *
0x1800baf1e  mov     rdx, r14; __int64
0x1800baf21  mov     rcx, r12; struct StateRepository::Cache::Manager_NoThrow *
0x1800baf24  call    ?IsRuntimeBehaviorUniversal@@YA_NAEAVManager_NoThrow@Cache@StateRepository@@_JPEBG@Z; IsRuntimeBehaviorUniversal(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *)
0x1800baf29  xor     r14d, r14d
0x1800baf2c  test    al, al
0x1800baf2e  jz      short loc_1800BAF8E
0x1800baf30  test    rbx, rbx
0x1800baf33  jz      short loc_1800BAF40
0x1800baf35  lea     rcx, [rsp+220h+var_1B0]
0x1800baf3a  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x1800baf3f  nop
0x1800baf40  cmp     [rsp+220h+var_1A8], r14
0x1800baf45  jz      short loc_1800BAF52
0x1800baf47  lea     rcx, [rsp+220h+var_1A8]
0x1800baf4c  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x1800baf51  nop
0x1800baf52  mov     rcx, [rsp+220h+string]; string
0x1800baf57  call    cs:__imp_WindowsDeleteString
0x1800baf5e  nop     dword ptr [rax+rax+00h]
0x1800baf63  mov     [rsp+220h+string], r14
0x1800baf68  mov     rcx, [rsp+220h+var_1C8]
0x1800baf6d  test    rcx, rcx
0x1800baf70  jz      short loc_1800BAF84
0x1800baf72  mov     [rsp+220h+var_1C8], r14
0x1800baf77  mov     rax, [rcx]
0x1800baf7a  mov     rax, [rax+10h]
0x1800baf7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800baf83  nop
0x1800baf84  xor     al, al
0x1800baf86  jmp     loc_1800BB3C8
0x1800baf8b  xor     r14d, r14d
0x1800baf8e  mov     r15d, r14d
0x1800baf91  lea     rcx, [rsp+220h+var_1B0]
0x1800baf96  call    ?Size@?$consume_Windows_Foundation_Collections_IVectorView@U?$IVectorView@USharedPackageContainer@StateRepository@Internal@Windows@winrt@@@Collections@Foundation@Windows@winrt@@USharedPackageContainer@StateRepository@Internal@45@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::StateRepository::SharedPackageContainer>,winrt::Windows::Internal::StateRepository::SharedPackageContainer>::Size(void)
0x1800baf9b  mov     [rbp+120h+var_170], eax
0x1800baf9e  cmp     r15d, eax
0x1800bafa1  jz      loc_1800BB372
0x1800bafa7  mov     [rsp+220h+var_1B8], r14
0x1800bafac  or      esi, 40h
0x1800bafaf  mov     [rsp+220h+length], esi
0x1800bafb3  mov     dword ptr [rbp+120h+lpString1], r14d
0x1800bafba  xorps   xmm0, xmm0
0x1800bafbd  movdqu  xmmword ptr [rbp+120h+lpString1+8], xmm0
0x1800bafc5  mov     rax, [rbx]
0x1800bafc8  lea     r8, [rsp+220h+var_1B8]
0x1800bafcd  mov     edx, r15d
0x1800bafd0  mov     rcx, rbx
0x1800bafd3  mov     rax, [rax+30h]
0x1800bafd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bafdc  test    eax, eax
0x1800bafde  js      loc_1800BB401
0x1800bafe4  and     esi, 0FFFFFFBFh
0x1800bafe7  mov     [rsp+220h+length], esi
0x1800bafeb  or      esi, 20h
0x1800bafee  lea     rdx, [rbp+120h+pv]
0x1800baff2  lea     rcx, [rsp+220h+var_1B8]
0x1800baff7  call    ?Get_Dictionary@?$consume_Windows_Internal_StateRepository_IApplicationExtension@UIApplicationExtension@StateRepository@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_StateRepository_IApplicationExtension<winrt::Windows::Internal::StateRepository::IApplicationExtension>::Get_Dictionary(void)
0x1800baffc  nop
0x1800baffd  movups  xmm0, xmmword ptr [rax]
0x1800bb000  movdqu  xmmword ptr [rsp+220h+length], xmm0
0x1800bb006  lea     rdx, [rsp+220h+length]
0x1800bb00b  lea     rcx, [rsp+220h+var_1C0]
0x1800bb010  call    ?SRDictionaryToPropertySet@@YA?AUIPropertySet@Collections@Foundation@Windows@winrt@@U?$array_view@E@5@@Z; SRDictionaryToPropertySet(winrt::array_view<uchar>)
0x1800bb015  nop
0x1800bb016  mov     rcx, [rbp+120h+pv]; pv
0x1800bb01a  test    rcx, rcx
0x1800bb01d  jz      short loc_1800BB02C
0x1800bb01f  call    CoTaskMemFree_0
0x1800bb024  mov     [rbp+120h+pv], r14
0x1800bb028  mov     [rbp+120h+var_130], r14d
0x1800bb02c  mov     rcx, [rsp+220h+var_1C0]
0x1800bb031  mov     qword ptr [rsp+220h+length], r14
0x1800bb036  test    rcx, rcx
0x1800bb039  jz      short loc_1800BB05C
0x1800bb03b  mov     rax, [rcx]
0x1800bb03e  lea     r8, [rsp+220h+length]
0x1800bb043  lea     rdx, ??$guid_v@U?$IMap@Uhstring@winrt@@UIInspectable@Foundation@Windows@2@@Collections@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Windows::Foundation::IInspectable>>
0x1800bb04a  mov     rax, [rax]
0x1800bb04d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb052  mov     r14, qword ptr [rsp+220h+length]
0x1800bb057  mov     qword ptr [rsp+220h+length], r14
0x1800bb05c  lea     rax, aStartuptask; "StartupTask"
0x1800bb063  mov     [rbp+120h+var_160], rax
0x1800bb067  mov     qword ptr [rbp+120h+var_158], 0Bh
0x1800bb06f  lea     r8, [rbp+120h+var_160]
0x1800bb073  lea     rdx, [rsp+220h+length]
0x1800bb078  lea     rcx, [rbp+120h+var_1A0]
0x1800bb07c  call    ?GetSingleChildElement@@YA?AU?$IMap@Uhstring@winrt@@UIInspectable@Foundation@Windows@2@@Collections@Foundation@Windows@winrt@@AEBU12345@V?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; GetSingleChildElement(winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Windows::Foundation::IInspectable> const &,std::basic_string_view<ushort>)
0x1800bb081  nop
0x1800bb082  test    r14, r14
0x1800bb085  jz      short loc_1800BB091
0x1800bb087  lea     rcx, [rsp+220h+length]
0x1800bb08c  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x1800bb091  lea     rax, aTaskid; "@TaskId"
0x1800bb098  mov     [rbp+120h+var_190], rax
0x1800bb09c  mov     qword ptr [rbp+120h+var_188], 7
0x1800bb0a4  lea     r8, [rbp+120h+var_190]
0x1800bb0a8  lea     rdx, [rbp+120h+var_1A0]
0x1800bb0ac  lea     rcx, [rbp+120h+lpString1]
0x1800bb0b3  call    ?GetAttribute@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU?$IMap@Uhstring@winrt@@UIInspectable@Foundation@Windows@2@@Collections@Foundation@Windows@winrt@@V?$basic_string_view@GU?$char_traits@G@std@@@2@@Z; GetAttribute(winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Windows::Foundation::IInspectable> const &,std::basic_string_view<ushort>)
0x1800bb0b8  nop
0x1800bb0b9  xor     edx, edx; length
0x1800bb0bb  mov     rcx, [rsp+220h+string]; string
0x1800bb0c0  call    cs:__imp_WindowsGetStringRawBuffer
0x1800bb0c7  nop     dword ptr [rax+rax+00h]
0x1800bb0cc  lea     rcx, [rbp+120h+lpString1]
0x1800bb0d3  cmp     qword ptr [rbp+120h+cchCount1+8], 7
0x1800bb0db  cmova   rcx, [rbp+120h+lpString1]; lpString1
0x1800bb0e3  xor     r14d, r14d
0x1800bb0e6  mov     [rsp+220h+bIgnoreCase], r14d; bIgnoreCase
0x1800bb0eb  or      r9d, 0FFFFFFFFh; cchCount2
0x1800bb0ef  mov     r8, rax; lpString2
0x1800bb0f2  mov     edx, [rbp+120h+cchCount1]; cchCount1
0x1800bb0f8  call    cs:__imp_CompareStringOrdinal
0x1800bb0ff  nop     dword ptr [rax+rax+00h]
0x1800bb104  cmp     eax, 2
0x1800bb107  jz      short loc_1800BB154
0x1800bb109  lea     rcx, [rbp+120h+lpString1]; void *
0x1800bb110  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800bb115  nop
0x1800bb116  cmp     [rbp+120h+var_1A0], r14
0x1800bb11a  jz      short loc_1800BB126
0x1800bb11c  lea     rcx, [rbp+120h+var_1A0]
0x1800bb120  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x1800bb125  nop
0x1800bb126  cmp     [rsp+220h+var_1C0], r14
0x1800bb12b  jz      short loc_1800BB138
0x1800bb12d  lea     rcx, [rsp+220h+var_1C0]
0x1800bb132  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x1800bb137  nop
0x1800bb138  cmp     [rsp+220h+var_1B8], r14
0x1800bb13d  jz      short loc_1800BB149
0x1800bb13f  lea     rcx, [rsp+220h+var_1B8]
0x1800bb144  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x1800bb149  inc     r15d
0x1800bb14c  mov     eax, [rbp+120h+var_170]
0x1800bb14f  jmp     loc_1800BAF9E
0x1800bb154  mov     [rsp+220h+length], r14d
0x1800bb159  mov     rcx, [rsp+220h+var_1B8]
0x1800bb15e  mov     dword ptr [rbp+120h+var_160], r14d
0x1800bb162  xorps   xmm0, xmm0
0x1800bb165  movdqu  [rbp+120h+var_158], xmm0
0x1800bb16a  mov     rax, [rcx]
0x1800bb16d  lea     rdx, [rsp+220h+length]
0x1800bb172  mov     rax, [rax+50h]
0x1800bb176  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb17b  test    eax, eax
0x1800bb17d  js      loc_1800BB446
0x1800bb183  mov     [rsp+220h+var_1F0], r14b
0x1800bb188  xorps   xmm0, xmm0
0x1800bb18b  movdqa  xmmword ptr [rbp+120h+var_D0], xmm0
0x1800bb190  mov     [rbp+120h+var_C0], r14
0x1800bb194  mov     [rbp+120h+var_B8], r14
0x1800bb198  movdqa  [rbp+120h+var_B0], xmm0
0x1800bb19d  xorps   xmm1, xmm1
  ... truncated ...
```
