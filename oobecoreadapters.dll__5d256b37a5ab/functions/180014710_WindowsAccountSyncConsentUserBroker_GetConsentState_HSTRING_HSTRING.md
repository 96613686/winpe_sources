# WindowsAccountSyncConsentUserBroker::GetConsentState(HSTRING__ *,HSTRING__ * *)

- ea: `0x180014710`
- end: `0x180014b94`
- name: `?GetConsentState@WindowsAccountSyncConsentUserBroker@@UEAAJPEAUHSTRING__@@PEAPEAU2@@Z`
- size: `1156`
- prototype: `int(WindowsAccountSyncConsentUserBroker *__hidden this, HSTRING, HSTRING *)`
- caller_count: `0`
- callee_count: `20`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180002b60`
- `0x1800076d4`
- `0x18000851c`
- `0x180013c40`
- `0x180014200`
- `0x180014250`
- `0x18001430c`
- `0x180014574`
- `0x1800146a4`
- `0x180014710`
- `0x180014b9c`
- `0x180014e58`
- `0x180014ea8`
- `0x180014ef8`
- `0x180014f48`
- `0x1800152e0`
- `0x1800153e4`
- `0x180015544`
- `0x180015728`
- `0x180015750`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180014858`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180014935`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180014b09`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180014858`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180014935`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180014b09`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800148be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800148be`

## string_xrefs

- `0x18001486f`: `shellcommon\shell\oobe\core\components\com\consentcoordinator.cpp`
- `0x18001494c`: `shellcommon\shell\oobe\core\components\com\consentcoordinator.cpp`
- `0x180014b81`: `shellcommon\shell\oobe\core\components\com\consentcoordinator.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall WindowsAccountSyncConsentUserBroker::GetConsentState(
        WindowsAccountSyncConsentUserBroker *this,
        HSTRING a2,
        HSTRING *a3)
{
  __int64 v5; // rdx
  HRESULT v6; // eax
  unsigned int v7; // ebx
  const char *v8; // r9
  __int64 result; // rax
  const unsigned __int16 *StringRawBuffer; // rdx
  struct winrt::impl::hstring_header *v11; // rdx
  __int64 v12; // rdx
  HRESULT v13; // eax
  unsigned int v14; // ebx
  __int64 BooleanValue; // rdi
  __int64 v16; // rdi
  __int64 v17; // rdi
  __int64 v18; // rdi
  UINT32 v19; // edx
  const WCHAR *v20; // rcx
  HRESULT String; // eax
  bool v22[8]; // [rsp+20h] [rbp-158h] BYREF
  __int64 v23; // [rsp+28h] [rbp-150h] BYREF
  __int64 v24; // [rsp+30h] [rbp-148h] BYREF
  _BYTE v25[8]; // [rsp+38h] [rbp-140h] BYREF
  _BYTE v26[8]; // [rsp+40h] [rbp-138h] BYREF
  winrt::impl *v27; // [rsp+48h] [rbp-130h] BYREF
  __int64 v28; // [rsp+50h] [rbp-128h] BYREF
  _QWORD v29[4]; // [rsp+58h] [rbp-120h] BYREF
  wchar_t v30[4]; // [rsp+78h] [rbp-100h] BYREF
  WCHAR sourceString[112]; // [rsp+80h] [rbp-F8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+0h]

  wcscpy(v30, L"{}");
  wcscpy(
    sourceString,
    L"{\"IsApplicable\":false,\"IsAvailable\":false,\"IsConsentAccepted\":false,\"IsSystemInitiatedPromptAllowed\":false}");
  try
  {
    winrt::WindowsUdk::Services::UnifiedConsent::WindowsAccountSyncConsentCoordinator::GetForDefaultAccountAsync();
    winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::WindowsUdk::Services::UnifiedConsent::WindowsAccountSyncConsentCoordinator>,winrt::WindowsUdk::Services::UnifiedConsent::WindowsAccountSyncConsentCoordinator>::get(
      v26,
      &v24);
    if ( v24 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
      winrt::hstring::hstring((winrt::hstring *)&v27, StringRawBuffer);
      *(_QWORD *)v22 = winrt::impl::duplicate_hstring(v27, v11);
      v29[0] = *(_QWORD *)v22;
      winrt::impl::consume_WindowsUdk_Services_UnifiedConsent_IWindowsAccountSyncConsentCoordinator<winrt::WindowsUdk::Services::UnifiedConsent::IWindowsAccountSyncConsentCoordinator>::GetConsentState(
        &v24,
        &v23,
        v29);
      winrt::handle_type<winrt::impl::hstring_traits>::close(v22);
      winrt::handle_type<winrt::impl::hstring_traits>::close(&v27);
      if ( v23 )
      {
        winrt::Windows::Data::Json::JsonObject::JsonObject((winrt::Windows::Data::Json::JsonObject *)v25);
        winrt::impl::consume_WindowsUdk_Services_UnifiedConsent_IWindowsAccountSyncConsentState<winrt::WindowsUdk::Services::UnifiedConsent::IWindowsAccountSyncConsentState>::IsApplicable(&v23);
        BooleanValue = winrt::Windows::Data::Json::JsonValue::CreateBooleanValue((bool)v22);
        winrt::param::hstring::hstring((winrt::param::hstring *)v29, L"IsApplicable");
        winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
          v25,
          v29,
          BooleanValue);
        winrt::Windows::Storage::IStorageFolder::~IStorageFolder((winrt::Windows::Storage::IStorageFolder *)v22);
        winrt::impl::consume_WindowsUdk_Services_UnifiedConsent_IWindowsAccountSyncConsentState<winrt::WindowsUdk::Services::UnifiedConsent::IWindowsAccountSyncConsentState>::IsAvailable(&v23);
        v16 = winrt::Windows::Data::Json::JsonValue::CreateBooleanValue((bool)v22);
        winrt::param::hstring::hstring((winrt::param::hstring *)v29, L"IsAvailable");
        winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
          v25,
          v29,
          v16);
        winrt::Windows::Storage::IStorageFolder::~IStorageFolder((winrt::Windows::Storage::IStorageFolder *)v22);
        winrt::impl::consume_WindowsUdk_Services_UnifiedConsent_IWindowsAccountSyncConsentState<winrt::WindowsUdk::Services::UnifiedConsent::IWindowsAccountSyncConsentState>::IsConsentAccepted(&v23);
        v17 = winrt::Windows::Data::Json::JsonValue::CreateBooleanValue((bool)v22);
        winrt::param::hstring::hstring((winrt::param::hstring *)v29, L"IsConsentAccepted");
        winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
          v25,
          v29,
          v17);
        winrt::Windows::Storage::IStorageFolder::~IStorageFolder((winrt::Windows::Storage::IStorageFolder *)v22);
        winrt::impl::consume_WindowsUdk_Services_UnifiedConsent_IWindowsAccountSyncConsentState<winrt::WindowsUdk::Services::UnifiedConsent::IWindowsAccountSyncConsentState>::IsSystemInitiatedPromptAllowed(&v23);
        v18 = winrt::Windows::Data::Json::JsonValue::CreateBooleanValue((bool)v22);
        winrt::param::hstring::hstring((winrt::param::hstring *)v29, L"IsSystemInitiatedPromptAllowed");
        winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
          v25,
          v29,
          v18);
        winrt::Windows::Storage::IStorageFolder::~IStorageFolder((winrt::Windows::Storage::IStorageFolder *)v22);
        winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonObject>::Stringify(v25, &v28);
        if ( v28 )
          v19 = *(_DWORD *)(v28 + 4);
        else
          v19 = 0;
        if ( v28 )
          v20 = *(const WCHAR **)(v28 + 16);
        else
          v20 = &::sourceString;
        String = WindowsCreateString(v20, v19, a3);
        if ( String < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x47,
            (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\com\\consentcoordinator.cpp",
            (const char *)(unsigned int)String,
            *(int *)v22);
        winrt::handle_type<winrt::impl::hstring_traits>::close(&v28);
        winrt::Windows::Storage::IStorageFolder::~IStorageFolder((winrt::Windows::Storage::IStorageFolder *)v25);
        winrt::Windows::Storage::IStorageFolder::~IStorageFolder((winrt::Windows::Storage::IStorageFolder *)&v23);
        winrt::Windows::Storage::IStorageFolder::~IStorageFolder((winrt::Windows::Storage::IStorageFolder *)&v24);
        winrt::Windows::Storage::IStorageFolder::~IStorageFolder((winrt::Windows::Storage::IStorageFolder *)v26);
        result = 0;
      }
      else
      {
        v12 = -1;
        do
          ++v12;
        while ( v30[v12] );
        v13 = WindowsCreateString(v30, v12, a3);
        v14 = v13;
        if ( v13 >= 0 )
        {
          winrt::Windows::Storage::IStorageFolder::~IStorageFolder((winrt::Windows::Storage::IStorageFolder *)&v23);
          winrt::Windows::Storage::IStorageFolder::~IStorageFolder((winrt::Windows::Storage::IStorageFolder *)&v24);
          winrt::Windows::Storage::IStorageFolder::~IStorageFolder((winrt::Windows::Storage::IStorageFolder *)v26);
          result = 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3B,
            (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\com\\consentcoordinator.cpp",
            (const char *)(unsigned int)v13,
            *(int *)v22);
          winrt::Windows::Storage::IStorageFolder::~IStorageFolder((winrt::Windows::Storage::IStorageFolder *)&v23);
          winrt::Windows::Storage::IStorageFolder::~IStorageFolder((winrt::Windows::Storage::IStorageFolder *)&v24);
          winrt::Windows::Storage::IStorageFolder::~IStorageFolder((winrt::Windows::Storage::IStorageFolder *)v26);
          result = v14;
        }
      }
    }
    else
    {
      v5 = -1;
      do
        ++v5;
      while ( sourceString[v5] );
      v6 = WindowsCreateString(sourceString, v5, a3);
      v7 = v6;
      if ( v6 >= 0 )
      {
        winrt::Windows::Storage::IStorageFolder::~IStorageFolder((winrt::Windows::Storage::IStorageFolder *)&v24);
        winrt::Windows::Storage::IStorageFolder::~IStorageFolder((winrt::Windows::Storage::IStorageFolder *)v26);
        result = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x32,
          (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\com\\consentcoordinator.cpp",
          (const char *)(unsigned int)v6,
          *(int *)v22);
        winrt::Windows::Storage::IStorageFolder::~IStorageFolder((winrt::Windows::Storage::IStorageFolder *)&v24);
        winrt::Windows::Storage::IStorageFolder::~IStorageFolder((winrt::Windows::Storage::IStorageFolder *)v26);
        result = v7;
      }
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x4A,
                           (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\com\\consentcoordinator.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x180014710  mov     r11, rsp
0x180014713  mov     [r11+8], rbx
0x180014717  mov     [r11+20h], rsi
0x18001471b  push    rdi
0x18001471c  sub     rsp, 170h
0x180014723  mov     rax, cs:__security_cookie
0x18001472a  xor     rax, rsp
0x18001472d  mov     [rsp+178h+var_18], rax
0x180014735  mov     rbx, r8
0x180014738  mov     rdi, rdx
0x18001473b  mov     eax, dword ptr cs:asc_18008C7F0; "{}"
0x180014741  mov     dword ptr [rsp+178h+var_100], eax
0x180014745  movzx   eax, word ptr cs:asc_18008C7F0+4; ""
0x18001474c  mov     word ptr [rsp+178h+var_100+4], ax
0x180014751  movaps  xmm0, xmmword ptr cs:aIsapplicableFa; "{\"IsApplicable\":false,\"IsAvailable\""...
0x180014758  movups  xmmword ptr [rsp+178h+sourceString], xmm0
0x180014760  movaps  xmm1, xmmword ptr cs:aIsapplicableFa+10h; "icable\":false,\"IsAvailable\":false,\""...
0x180014767  movups  [rsp+178h+var_E8], xmm1
0x18001476f  movaps  xmm0, xmmword ptr cs:aIsapplicableFa+20h; "false,\"IsAvailable\":false,\"IsConsent"...
0x180014776  movups  [rsp+178h+var_D8], xmm0
0x18001477e  movaps  xmm1, xmmword ptr cs:aIsapplicableFa+30h; "sAvailable\":false,\"IsConsentAccepted"...
0x180014785  movups  [rsp+178h+var_C8], xmm1
0x18001478d  movaps  xmm0, xmmword ptr cs:aIsapplicableFa+40h; "le\":false,\"IsConsentAccepted\":false,"...
0x180014794  movups  [rsp+178h+var_B8], xmm0
0x18001479c  movaps  xmm1, xmmword ptr cs:aIsapplicableFa+50h; "e,\"IsConsentAccepted\":false,\"IsSyste"...
0x1800147a3  movups  [rsp+178h+var_A8], xmm1
0x1800147ab  movaps  xmm0, xmmword ptr cs:aIsapplicableFa+60h; "sentAccepted\":false,\"IsSystemInitiate"...
0x1800147b2  movups  [rsp+178h+var_98], xmm0
0x1800147ba  movaps  xmm1, xmmword ptr cs:aIsapplicableFa+70h; "pted\":false,\"IsSystemInitiatedPromptA"...
0x1800147c1  movups  [rsp+178h+var_88], xmm1
0x1800147c9  movaps  xmm0, xmmword ptr cs:aIsapplicableFa+80h; "lse,\"IsSystemInitiatedPromptAllowed\":"...
0x1800147d0  movups  xmmword ptr [r11-78h], xmm0
0x1800147d5  movaps  xmm1, xmmword ptr cs:aIsapplicableFa+90h; "ystemInitiatedPromptAllowed\":false}"
0x1800147dc  movups  xmmword ptr [r11-68h], xmm1
0x1800147e1  movaps  xmm0, xmmword ptr cs:aIsapplicableFa+0A0h; "tiatedPromptAllowed\":false}"
0x1800147e8  movups  xmmword ptr [r11-58h], xmm0
0x1800147ed  movaps  xmm1, xmmword ptr cs:aIsapplicableFa+0B0h; "omptAllowed\":false}"
0x1800147f4  movups  xmmword ptr [r11-48h], xmm1
0x1800147f9  movaps  xmm0, xmmword ptr cs:aIsapplicableFa+0C0h; "wed\":false}"
0x180014800  movups  xmmword ptr [r11-38h], xmm0
0x180014805  mov     rax, qword ptr cs:aIsapplicableFa+0D0h; "se}"
0x18001480c  mov     [r11-28h], rax
0x180014810  lea     rcx, [rsp+178h+var_138]
0x180014815  call    ?GetForDefaultAccountAsync@WindowsAccountSyncConsentCoordinator@UnifiedConsent@Services@WindowsUdk@winrt@@SA@XZ; winrt::WindowsUdk::Services::UnifiedConsent::WindowsAccountSyncConsentCoordinator::GetForDefaultAccountAsync(void)
0x18001481a  nop
0x18001481b  lea     rdx, [rsp+178h+var_148]
0x180014820  lea     rcx, [rsp+178h+var_138]
0x180014825  call    ?get@?$consume_Windows_Foundation_IAsyncOperation@U?$IAsyncOperation@UWindowsAccountSyncConsentCoordinator@UnifiedConsent@Services@WindowsUdk@winrt@@@Foundation@Windows@winrt@@UWindowsAccountSyncConsentCoordinator@UnifiedConsent@Services@WindowsUdk@4@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::WindowsUdk::Services::UnifiedConsent::WindowsAccountSyncConsentCoordinator>,winrt::WindowsUdk::Services::UnifiedConsent::WindowsAccountSyncConsentCoordinator>::get(void)
0x18001482a  nop
0x18001482b  xor     esi, esi
0x18001482d  cmp     [rsp+178h+var_148], rsi
0x180014832  jnz     loc_1800148B9
0x180014838  lea     rax, [rsp+178h+sourceString]
0x180014840  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180014844  inc     rdx; length
0x180014847  cmp     [rax+rdx*2], si
0x18001484b  jnz     short loc_180014844
0x18001484d  mov     r8, rbx; string
0x180014850  lea     rcx, [rsp+178h+sourceString]; sourceString
0x180014858  call    cs:__imp_WindowsCreateString
0x18001485e  mov     ebx, eax
0x180014860  test    eax, eax
0x180014862  jns     short loc_18001489D
0x180014864  mov     rcx, [rsp+178h]; this
0x18001486c  mov     r9d, eax; char *
0x18001486f  lea     r8, aShellcommonShe_3; "shellcommon\\shell\\oobe\\core\\compone"...
0x180014876  mov     edx, 32h ; '2'; void *
0x18001487b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014880  nop
0x180014881  lea     rcx, [rsp+178h+var_148]; this
0x180014886  call    ??1IStorageFolder@Storage@Windows@winrt@@QEAA@XZ; winrt::Windows::Storage::IStorageFolder::~IStorageFolder(void)
0x18001488b  nop
0x18001488c  lea     rcx, [rsp+178h+var_138]; this
0x180014891  call    ??1IStorageFolder@Storage@Windows@winrt@@QEAA@XZ; winrt::Windows::Storage::IStorageFolder::~IStorageFolder(void)
0x180014896  mov     eax, ebx
0x180014898  jmp     loc_180014B59
0x18001489d  lea     rcx, [rsp+178h+var_148]; this
0x1800148a2  call    ??1IStorageFolder@Storage@Windows@winrt@@QEAA@XZ; winrt::Windows::Storage::IStorageFolder::~IStorageFolder(void)
0x1800148a7  nop
0x1800148a8  lea     rcx, [rsp+178h+var_138]; this
0x1800148ad  call    ??1IStorageFolder@Storage@Windows@winrt@@QEAA@XZ; winrt::Windows::Storage::IStorageFolder::~IStorageFolder(void)
0x1800148b2  xor     eax, eax
0x1800148b4  jmp     loc_180014B59
0x1800148b9  xor     edx, edx; length
0x1800148bb  mov     rcx, rdi; string
0x1800148be  call    cs:__imp_WindowsGetStringRawBuffer
0x1800148c4  mov     rdx, rax; unsigned __int16 *
0x1800148c7  lea     rcx, [rsp+178h+var_130]; this
0x1800148cc  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x1800148d1  nop
0x1800148d2  mov     rcx, [rsp+178h+var_130]; this
0x1800148d7  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x1800148dc  mov     qword ptr [rsp+178h+var_158], rax; int
0x1800148e1  mov     [rsp+178h+var_120], rax
0x1800148e6  lea     r8, [rsp+178h+var_120]
0x1800148eb  lea     rdx, [rsp+178h+var_150]
0x1800148f0  lea     rcx, [rsp+178h+var_148]
0x1800148f5  call    ?GetConsentState@?$consume_WindowsUdk_Services_UnifiedConsent_IWindowsAccountSyncConsentCoordinator@UIWindowsAccountSyncConsentCoordinator@UnifiedConsent@Services@WindowsUdk@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_WindowsUdk_Services_UnifiedConsent_IWindowsAccountSyncConsentCoordinator<winrt::WindowsUdk::Services::UnifiedConsent::IWindowsAccountSyncConsentCoordinator>::GetConsentState(winrt::param::hstring const &)
0x1800148fa  nop
0x1800148fb  lea     rcx, [rsp+178h+var_158]
0x180014900  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180014905  nop
0x180014906  lea     rcx, [rsp+178h+var_130]
0x18001490b  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180014910  cmp     [rsp+178h+var_150], rsi
0x180014915  jnz     loc_1800149AC
0x18001491b  lea     rax, [rsp+178h+var_100]
0x180014920  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180014924  inc     rdx; length
0x180014927  cmp     [rax+rdx*2], si
0x18001492b  jnz     short loc_180014924
0x18001492d  mov     r8, rbx; string
0x180014930  lea     rcx, [rsp+178h+var_100]; sourceString
0x180014935  call    cs:__imp_WindowsCreateString
0x18001493b  mov     ebx, eax
0x18001493d  test    eax, eax
0x18001493f  jns     short loc_180014985
0x180014941  mov     rcx, [rsp+178h]; this
0x180014949  mov     r9d, eax; char *
0x18001494c  lea     r8, aShellcommonShe_3; "shellcommon\\shell\\oobe\\core\\compone"...
0x180014953  mov     edx, 3Bh ; ';'; void *
0x180014958  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001495d  nop
0x18001495e  lea     rcx, [rsp+178h+var_150]; this
0x180014963  call    ??1IStorageFolder@Storage@Windows@winrt@@QEAA@XZ; winrt::Windows::Storage::IStorageFolder::~IStorageFolder(void)
0x180014968  nop
0x180014969  lea     rcx, [rsp+178h+var_148]; this
0x18001496e  call    ??1IStorageFolder@Storage@Windows@winrt@@QEAA@XZ; winrt::Windows::Storage::IStorageFolder::~IStorageFolder(void)
0x180014973  nop
0x180014974  lea     rcx, [rsp+178h+var_138]; this
0x180014979  call    ??1IStorageFolder@Storage@Windows@winrt@@QEAA@XZ; winrt::Windows::Storage::IStorageFolder::~IStorageFolder(void)
0x18001497e  mov     eax, ebx
0x180014980  jmp     loc_180014B59
0x180014985  lea     rcx, [rsp+178h+var_150]; this
0x18001498a  call    ??1IStorageFolder@Storage@Windows@winrt@@QEAA@XZ; winrt::Windows::Storage::IStorageFolder::~IStorageFolder(void)
0x18001498f  nop
0x180014990  lea     rcx, [rsp+178h+var_148]; this
0x180014995  call    ??1IStorageFolder@Storage@Windows@winrt@@QEAA@XZ; winrt::Windows::Storage::IStorageFolder::~IStorageFolder(void)
0x18001499a  nop
0x18001499b  lea     rcx, [rsp+178h+var_138]; this
0x1800149a0  call    ??1IStorageFolder@Storage@Windows@winrt@@QEAA@XZ; winrt::Windows::Storage::IStorageFolder::~IStorageFolder(void)
0x1800149a5  xor     eax, eax
0x1800149a7  jmp     loc_180014B59
0x1800149ac  lea     rcx, [rsp+178h+var_140]; this
0x1800149b1  call    ??0JsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::JsonObject::JsonObject(void)
0x1800149b6  nop
0x1800149b7  lea     rcx, [rsp+178h+var_150]
0x1800149bc  call    ?IsApplicable@?$consume_WindowsUdk_Services_UnifiedConsent_IWindowsAccountSyncConsentState@UIWindowsAccountSyncConsentState@UnifiedConsent@Services@WindowsUdk@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_WindowsUdk_Services_UnifiedConsent_IWindowsAccountSyncConsentState<winrt::WindowsUdk::Services::UnifiedConsent::IWindowsAccountSyncConsentState>::IsApplicable(void)
0x1800149c1  mov     dl, al
0x1800149c3  lea     rcx, [rsp+178h+var_158]; bool
0x1800149c8  call    ?CreateBooleanValue@JsonValue@Json@Data@Windows@winrt@@SA@_N@Z; winrt::Windows::Data::Json::JsonValue::CreateBooleanValue(bool)
0x1800149cd  mov     rdi, rax
0x1800149d0  lea     rdx, aIsapplicable; "IsApplicable"
0x1800149d7  lea     rcx, [rsp+178h+var_120]; this
0x1800149dc  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x1800149e1  mov     r8, rdi
0x1800149e4  lea     rdx, [rsp+178h+var_120]
0x1800149e9  lea     rcx, [rsp+178h+var_140]
0x1800149ee  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x1800149f3  nop
0x1800149f4  lea     rcx, [rsp+178h+var_158]; this
0x1800149f9  call    ??1IStorageFolder@Storage@Windows@winrt@@QEAA@XZ; winrt::Windows::Storage::IStorageFolder::~IStorageFolder(void)
0x1800149fe  lea     rcx, [rsp+178h+var_150]
0x180014a03  call    ?IsAvailable@?$consume_WindowsUdk_Services_UnifiedConsent_IWindowsAccountSyncConsentState@UIWindowsAccountSyncConsentState@UnifiedConsent@Services@WindowsUdk@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_WindowsUdk_Services_UnifiedConsent_IWindowsAccountSyncConsentState<winrt::WindowsUdk::Services::UnifiedConsent::IWindowsAccountSyncConsentState>::IsAvailable(void)
0x180014a08  mov     dl, al
0x180014a0a  lea     rcx, [rsp+178h+var_158]; bool
0x180014a0f  call    ?CreateBooleanValue@JsonValue@Json@Data@Windows@winrt@@SA@_N@Z; winrt::Windows::Data::Json::JsonValue::CreateBooleanValue(bool)
0x180014a14  mov     rdi, rax
0x180014a17  lea     rdx, aIsavailable; "IsAvailable"
0x180014a1e  lea     rcx, [rsp+178h+var_120]; this
0x180014a23  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180014a28  mov     r8, rdi
0x180014a2b  lea     rdx, [rsp+178h+var_120]
0x180014a30  lea     rcx, [rsp+178h+var_140]
0x180014a35  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x180014a3a  nop
0x180014a3b  lea     rcx, [rsp+178h+var_158]; this
0x180014a40  call    ??1IStorageFolder@Storage@Windows@winrt@@QEAA@XZ; winrt::Windows::Storage::IStorageFolder::~IStorageFolder(void)
0x180014a45  lea     rcx, [rsp+178h+var_150]
0x180014a4a  call    ?IsConsentAccepted@?$consume_WindowsUdk_Services_UnifiedConsent_IWindowsAccountSyncConsentState@UIWindowsAccountSyncConsentState@UnifiedConsent@Services@WindowsUdk@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_WindowsUdk_Services_UnifiedConsent_IWindowsAccountSyncConsentState<winrt::WindowsUdk::Services::UnifiedConsent::IWindowsAccountSyncConsentState>::IsConsentAccepted(void)
0x180014a4f  mov     dl, al
0x180014a51  lea     rcx, [rsp+178h+var_158]; bool
0x180014a56  call    ?CreateBooleanValue@JsonValue@Json@Data@Windows@winrt@@SA@_N@Z; winrt::Windows::Data::Json::JsonValue::CreateBooleanValue(bool)
0x180014a5b  mov     rdi, rax
0x180014a5e  lea     rdx, aIsconsentaccep; "IsConsentAccepted"
0x180014a65  lea     rcx, [rsp+178h+var_120]; this
0x180014a6a  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180014a6f  mov     r8, rdi
0x180014a72  lea     rdx, [rsp+178h+var_120]
0x180014a77  lea     rcx, [rsp+178h+var_140]
0x180014a7c  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x180014a81  nop
0x180014a82  lea     rcx, [rsp+178h+var_158]; this
0x180014a87  call    ??1IStorageFolder@Storage@Windows@winrt@@QEAA@XZ; winrt::Windows::Storage::IStorageFolder::~IStorageFolder(void)
0x180014a8c  lea     rcx, [rsp+178h+var_150]
0x180014a91  call    ?IsSystemInitiatedPromptAllowed@?$consume_WindowsUdk_Services_UnifiedConsent_IWindowsAccountSyncConsentState@UIWindowsAccountSyncConsentState@UnifiedConsent@Services@WindowsUdk@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_WindowsUdk_Services_UnifiedConsent_IWindowsAccountSyncConsentState<winrt::WindowsUdk::Services::UnifiedConsent::IWindowsAccountSyncConsentState>::IsSystemInitiatedPromptAllowed(void)
0x180014a96  mov     dl, al
0x180014a98  lea     rcx, [rsp+178h+var_158]; bool
0x180014a9d  call    ?CreateBooleanValue@JsonValue@Json@Data@Windows@winrt@@SA@_N@Z; winrt::Windows::Data::Json::JsonValue::CreateBooleanValue(bool)
0x180014aa2  mov     rdi, rax
0x180014aa5  lea     rdx, aIssysteminitia; "IsSystemInitiatedPromptAllowed"
0x180014aac  lea     rcx, [rsp+178h+var_120]; this
0x180014ab1  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180014ab6  mov     r8, rdi
0x180014ab9  lea     rdx, [rsp+178h+var_120]
0x180014abe  lea     rcx, [rsp+178h+var_140]
0x180014ac3  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x180014ac8  nop
0x180014ac9  lea     rcx, [rsp+178h+var_158]; this
0x180014ace  call    ??1IStorageFolder@Storage@Windows@winrt@@QEAA@XZ; winrt::Windows::Storage::IStorageFolder::~IStorageFolder(void)
0x180014ad3  lea     rdx, [rsp+178h+var_128]
0x180014ad8  lea     rcx, [rsp+178h+var_140]
0x180014add  call    ?Stringify@?$consume_Windows_Data_Json_IJsonValue@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonObject>::Stringify(void)
0x180014ae2  nop
0x180014ae3  mov     rax, [rsp+178h+var_128]
0x180014ae8  test    rax, rax
0x180014aeb  jz      short loc_180014AF2
0x180014aed  mov     edx, [rax+4]
0x180014af0  jmp     short loc_180014AF4
0x180014af2  mov     edx, esi; length
0x180014af4  test    rax, rax
0x180014af7  jz      short loc_180014AFF
0x180014af9  mov     rcx, [rax+10h]
0x180014afd  jmp     short loc_180014B06
0x180014aff  lea     rcx, sourceString; sourceString
0x180014b06  mov     r8, rbx; string
0x180014b09  call    cs:__imp_WindowsCreateString
0x180014b0f  mov     rcx, [rsp+178h]; this
0x180014b17  test    eax, eax
0x180014b19  js      short loc_180014B7E
0x180014b1b  lea     rcx, [rsp+178h+var_128]
0x180014b20  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180014b25  nop
0x180014b26  lea     rcx, [rsp+178h+var_140]; this
0x180014b2b  call    ??1IStorageFolder@Storage@Windows@winrt@@QEAA@XZ; winrt::Windows::Storage::IStorageFolder::~IStorageFolder(void)
0x180014b30  nop
0x180014b31  lea     rcx, [rsp+178h+var_150]; this
0x180014b36  call    ??1IStorageFolder@Storage@Windows@winrt@@QEAA@XZ; winrt::Windows::Storage::IStorageFolder::~IStorageFolder(void)
0x180014b3b  nop
0x180014b3c  lea     rcx, [rsp+178h+var_148]; this
0x180014b41  call    ??1IStorageFolder@Storage@Windows@winrt@@QEAA@XZ; winrt::Windows::Storage::IStorageFolder::~IStorageFolder(void)
0x180014b46  nop
0x180014b47  lea     rcx, [rsp+178h+var_138]; this
0x180014b4c  call    ??1IStorageFolder@Storage@Windows@winrt@@QEAA@XZ; winrt::Windows::Storage::IStorageFolder::~IStorageFolder(void)
0x180014b51  xor     eax, eax
0x180014b53  jmp     short loc_180014B59
0x180014b55  mov     eax, dword ptr [rsp+178h+var_100]
0x180014b59  mov     rcx, [rsp+178h+var_18]
0x180014b61  xor     rcx, rsp; StackCookie
0x180014b64  call    __security_check_cookie
0x180014b69  lea     r11, [rsp+178h+var_8]
0x180014b71  mov     rbx, [r11+10h]
0x180014b75  mov     rsi, [r11+28h]
0x180014b79  mov     rsp, r11
0x180014b7c  pop     rdi
0x180014b7d  retn
0x180014b7e  mov     r9d, eax; char *
0x180014b81  lea     r8, aShellcommonShe_3; "shellcommon\\shell\\oobe\\core\\compone"...
0x180014b88  mov     edx, 47h ; 'G'; void *
0x180014b8d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
