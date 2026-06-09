# ToastActivatedCallback(Windows::UI::Notifications::IToastNotification *,IInspectable *)

- ea: `0x1800139d0`
- end: `0x18001401d`
- name: `?ToastActivatedCallback@@YAJPEAUIToastNotification@Notifications@UI@Windows@@PEAUIInspectable@@@Z`
- size: `1613`
- prototype: `__int64 __fastcall(struct Windows::UI::Notifications::IToastNotification *, struct IInspectable *)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001008`
- `0x180002e50`
- `0x180005ef0`
- `0x180007818`
- `0x18000e7ec`
- `0x1800109d4`
- `0x1800139d0`
- `0x180015604`
- `0x1800158a0`
- `0x180019e08`
- `0x1800200f8`
- `0x180023010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x180013a4b`
- `msvcp_win!_Mtx_unlock` at `0x180013b16`
- `msvcp_win!_Mtx_unlock` at `0x180013be9`
- `msvcp_win!_Mtx_unlock` at `0x180013f21`
- `msvcp_win!_Mtx_unlock` at `0x180013fba`
- `msvcp_win!_Mtx_unlock` at `0x180013a4b`
- `msvcp_win!_Mtx_unlock` at `0x180013b16`
- `msvcp_win!_Mtx_unlock` at `0x180013be9`
- `msvcp_win!_Mtx_unlock` at `0x180013f21`
- `msvcp_win!_Mtx_unlock` at `0x180013fba`
- `msvcp_win!_Mtx_lock` at `0x180013a06`
- `msvcp_win!_Mtx_lock` at `0x180013a06`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180013a15`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180013a36`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180013a15`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180013a36`
- `KERNEL32!SetEvent` at `0x180013afd`
- `KERNEL32!SetEvent` at `0x180013bd0`
- `KERNEL32!SetEvent` at `0x180013f08`
- `KERNEL32!SetEvent` at `0x180013fa5`
- `KERNEL32!SetEvent` at `0x180013afd`
- `KERNEL32!SetEvent` at `0x180013bd0`
- `KERNEL32!SetEvent` at `0x180013f08`
- `KERNEL32!SetEvent` at `0x180013fa5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180013b74`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180013ede`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180013f49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180013b74`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180013ede`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180013f49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180013bfd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180013bfd`

## pseudocode

```c
__int64 __fastcall ToastActivatedCallback(
        struct Windows::UI::Notifications::IToastNotification *a1,
        struct IInspectable *a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  _QWORD *v6; // rcx
  const char *v7; // rcx
  const char *v8; // r8
  char v9; // al
  __int64 v10; // r8
  const char *v11; // r9
  __int64 v12; // rax
  int v13; // eax
  _QWORD *v14; // rcx
  const char *v15; // rcx
  const char *v16; // r8
  char v17; // al
  __int64 v18; // r8
  const char *v19; // r9
  PCWSTR StringRawBuffer; // rax
  __int64 v21; // r8
  size_t v22; // rax
  const struct _tlgProvider_t *v23; // rax
  __int64 v24; // r8
  __int64 v25; // r9
  const char *v26; // rcx
  const char *v27; // r8
  char v28; // al
  __int16 v29; // dx
  const wchar_t *v30; // rcx
  wchar_t *v31; // rdx
  unsigned __int64 v32; // r8
  const struct _tlgProvider_t *v33; // rax
  __int64 v34; // r8
  __int64 v35; // r9
  char v36; // al
  wchar_t **v37; // rcx
  const struct _tlgProvider_t *v38; // rax
  __int64 v39; // r8
  __int64 v40; // r9
  char v41; // al
  wchar_t **v42; // rcx
  const struct _tlgProvider_t *v43; // rax
  __int64 v44; // r8
  __int64 v45; // r9
  char v46; // al
  _QWORD *v47; // rcx
  __int64 v48; // r8
  const char *v49; // r9
  _QWORD *v50; // rcx
  const char *v51; // rcx
  const char *v52; // r8
  char v53; // al
  __int64 v54; // r8
  const char *v55; // r9
  _QWORD *v56; // [rsp+30h] [rbp-68h] BYREF
  char v57; // [rsp+39h] [rbp-5Fh]
  const wchar_t *v58; // [rsp+40h] [rbp-58h] BYREF
  HSTRING string; // [rsp+48h] [rbp-50h] BYREF
  char v60; // [rsp+51h] [rbp-47h]
  void *v61; // [rsp+58h] [rbp-40h]
  wchar_t *S1[2]; // [rsp+60h] [rbp-38h] BYREF
  size_t N; // [rsp+70h] [rbp-28h]
  unsigned __int64 v64; // [rsp+78h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v61 = &g_toastSubscriptionMutex;
  if ( _Mtx_lock((_Mtx_t)&g_toastSubscriptionMutex) )
    std::_Throw_Cpp_error(5);
  if ( dword_18002F42C == 0x7FFFFFFF )
  {
    dword_18002F42C = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  if ( g_isTaskShuttingDown )
  {
    _Mtx_unlock((_Mtx_t)&g_toastSubscriptionMutex);
    return 0;
  }
  v60 = 1;
  v57 = 1;
  v56 = 0;
  v4 = ((__int64 (__fastcall *)(struct IInspectable *, GUID *, _QWORD **))a2->lpVtbl->QueryInterface)(
         a2,
         &GUID_e3bf92f3_c197_436f_8265_0625824f8dac,
         &v56);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x29F,
      (int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
      (const char *)(unsigned int)v4);
    v6 = v56;
    if ( v56 )
    {
      v56 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v6 + 16LL))(v6);
    }
    _InterlockedExchange(&g_aomdPromptResult, 5);
    v7 = "AOMDPromptResult::MainToastActivatedProcessingFailed";
    v8 = "AOMDPromptResult::MainToastActivatedProcessingFailed";
    v9 = 65;
    do
    {
      ++v7;
      if ( v9 == 58 )
        v8 = v7;
      v9 = *v7;
    }
    while ( *v7 );
    tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::complete_and_succeed(
      (__int64)v7,
      5,
      (__int64)v8);
    if ( !SetEvent(g_exitEvent) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA01, v10, v11);
LABEL_15:
    _Mtx_unlock((_Mtx_t)&g_toastSubscriptionMutex);
    return v5;
  }
  string = 0;
  v12 = *v56;
  string = 0;
  v13 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING *))(v12 + 48))(v56, &string);
  v5 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A2,
      (int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
      (const char *)(unsigned int)v13);
    if ( string )
      WindowsDeleteString(string);
    v14 = v56;
    if ( v56 )
    {
      v56 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v14 + 16LL))(v14);
    }
    _InterlockedExchange(&g_aomdPromptResult, 5);
    v15 = "AOMDPromptResult::MainToastActivatedProcessingFailed";
    v16 = "AOMDPromptResult::MainToastActivatedProcessingFailed";
    v17 = 65;
    do
    {
      ++v15;
      if ( v17 == 58 )
        v16 = v15;
      v17 = *v15;
    }
    while ( *v15 );
    tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::complete_and_succeed(
      (__int64)v15,
      5,
      (__int64)v16);
    if ( !SetEvent(g_exitEvent) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA01, v18, v19);
    goto LABEL_15;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  *(_OWORD *)S1 = 0;
  N = 0;
  v64 = 0;
  v21 = -1;
  do
    ++v21;
  while ( StringRawBuffer[v21] );
  std::wstring::_Construct<1,unsigned short const *>(S1);
  v22 = N;
  if ( !N )
  {
    v23 = TlgHelper::Provider();
    if ( *(_DWORD *)v23 > 4u && (*((_QWORD *)v23 + 2) & 2) != 0 && (*((_QWORD *)v23 + 3) & 2LL) == *((_QWORD *)v23 + 3) )
    {
      v58 = L"ToastActivatedCallback_ToastBodyClicked";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v23,
        (__int64)byte_180029F51,
        v24,
        v25,
        (int **)&v58);
    }
    _InterlockedExchange(&g_aomdPromptResult, 13);
    v26 = "AOMDPromptResult::UserChoiceBodyClick";
    v27 = "AOMDPromptResult::UserChoiceBodyClick";
    v28 = 65;
    do
    {
      ++v26;
      if ( v28 == 58 )
        v27 = v26;
      v28 = *v26;
    }
    while ( *v26 );
    v29 = 13;
LABEL_79:
    tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::complete_and_succeed(
      (__int64)v26,
      v29,
      (__int64)v27);
    v57 = 0;
    std::wstring::~wstring((char **)S1);
    if ( string )
      WindowsDeleteString(string);
    v47 = v56;
    if ( v56 )
    {
      v56 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v47 + 16LL))(v47);
    }
    if ( !SetEvent(g_exitEvent) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA01, v48, v49);
    _Mtx_unlock((_Mtx_t)&g_toastSubscriptionMutex);
    return 0;
  }
  v30 = (const wchar_t *)S1;
  v31 = S1[0];
  v32 = v64;
  if ( v64 > 7 )
    v30 = S1[0];
  if ( N == 6 )
  {
    if ( !wmemcmp(v30, L"id_yes", 6u) )
    {
      v33 = TlgHelper::Provider();
      if ( *(_DWORD *)v33 > 4u
        && (*((_QWORD *)v33 + 2) & 2) != 0
        && (*((_QWORD *)v33 + 3) & 2LL) == *((_QWORD *)v33 + 3) )
      {
        v58 = L"ToastActivatedCallback_YesButtonClicked";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (__int64)v33,
          (__int64)byte_180029F51,
          v34,
          v35,
          (int **)&v58);
      }
      v29 = 10;
      _InterlockedExchange(&g_aomdPromptResult, 10);
      v26 = "AOMDPromptResult::UserChoiceYes";
      v27 = "AOMDPromptResult::UserChoiceYes";
      v36 = 65;
      do
      {
        ++v26;
        if ( v36 == 58 )
          v27 = v26;
        v36 = *v26;
      }
      while ( *v26 );
      goto LABEL_79;
    }
    v32 = v64;
    v22 = N;
    v31 = S1[0];
  }
  v37 = S1;
  if ( v32 > 7 )
    v37 = (wchar_t **)v31;
  if ( v22 == 5 )
  {
    if ( !wmemcmp((const wchar_t *)v37, L"id_no", 5u) )
    {
      v38 = TlgHelper::Provider();
      if ( *(_DWORD *)v38 > 4u
        && (*((_QWORD *)v38 + 2) & 2) != 0
        && (*((_QWORD *)v38 + 3) & 2LL) == *((_QWORD *)v38 + 3) )
      {
        v58 = L"ToastActivatedCallback_NoButtonClicked";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (__int64)v38,
          (__int64)byte_180029F35,
          v39,
          v40,
          (int **)&v58);
      }
      v29 = 11;
      _InterlockedExchange(&g_aomdPromptResult, 11);
      v26 = "AOMDPromptResult::UserChoiceNo";
      v27 = "AOMDPromptResult::UserChoiceNo";
      v41 = 65;
      do
      {
        ++v26;
        if ( v41 == 58 )
          v27 = v26;
        v41 = *v26;
      }
      while ( *v26 );
      goto LABEL_79;
    }
    v32 = v64;
    v22 = N;
    v31 = S1[0];
  }
  v42 = S1;
  if ( v32 > 7 )
    v42 = (wchar_t **)v31;
  if ( v22 == 13 && !wmemcmp((const wchar_t *)v42, L"id_learn_more", 0xDu) )
  {
    v43 = TlgHelper::Provider();
    if ( *(_DWORD *)v43 > 4u && (*((_QWORD *)v43 + 2) & 2) != 0 && (*((_QWORD *)v43 + 3) & 2LL) == *((_QWORD *)v43 + 3) )
    {
      v58 = L"ToastActivatedCallback_LearnMoreButtonClicked";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v43,
        (__int64)&dword_180029FE4,
        v44,
        v45,
        (int **)&v58);
    }
    v29 = 12;
    _InterlockedExchange(&g_aomdPromptResult, 12);
    v26 = "AOMDPromptResult::UserChoiceLearnMore";
    v27 = "AOMDPromptResult::UserChoiceLearnMore";
    v46 = 65;
    do
    {
      ++v26;
      if ( v46 == 58 )
        v27 = v26;
      v46 = *v26;
    }
    while ( *v26 );
    goto LABEL_79;
  }
  MicrosoftTelemetryAssertTriggeredNoArgs(v42);
  std::wstring::~wstring((char **)S1);
  if ( string )
    WindowsDeleteString(string);
  v50 = v56;
  if ( v56 )
  {
    v56 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v50 + 16LL))(v50);
  }
  _InterlockedExchange(&g_aomdPromptResult, 5);
  v51 = "AOMDPromptResult::MainToastActivatedProcessingFailed";
  v52 = "AOMDPromptResult::MainToastActivatedProcessingFailed";
  v53 = 65;
  do
  {
    ++v51;
    if ( v53 == 58 )
      v52 = v51;
    v53 = *v51;
  }
  while ( *v51 );
  tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::complete_and_succeed(
    (__int64)v51,
    5,
    (__int64)v52);
  if ( !SetEvent(g_exitEvent) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA01, v54, v55);
  _Mtx_unlock((_Mtx_t)&g_toastSubscriptionMutex);
  return 2147549183LL;
}

```

## disassembly

```asm
0x1800139d0  mov     [rsp+arg_0], rbx
0x1800139d5  mov     [rsp+arg_10], rsi
0x1800139da  push    rdi
0x1800139db  sub     rsp, 90h
0x1800139e2  mov     rax, cs:__security_cookie
0x1800139e9  xor     rax, rsp
0x1800139ec  mov     [rsp+98h+var_18], rax
0x1800139f4  mov     rbx, rdx
0x1800139f7  lea     rsi, ?g_toastSubscriptionMutex@@3Vmutex@std@@A; std::mutex g_toastSubscriptionMutex
0x1800139fe  mov     [rsp+98h+var_40], rsi
0x180013a03  mov     rcx, rsi; _Mtx_t
0x180013a06  call    cs:__imp__Mtx_lock
0x180013a0c  xor     edi, edi
0x180013a0e  test    eax, eax
0x180013a10  jz      short loc_180013A1B
0x180013a12  lea     ecx, [rdi+5]
0x180013a15  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180013a1b  cmp     cs:dword_18002F42C, 7FFFFFFFh
0x180013a25  jnz     short loc_180013A3D
0x180013a27  mov     cs:dword_18002F42C, 7FFFFFFEh
0x180013a31  mov     ecx, 6
0x180013a36  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180013a3c  nop
0x180013a3d  mov     al, cs:?g_isTaskShuttingDown@@3U?$atomic@_N@std@@A; std::atomic<bool> g_isTaskShuttingDown
0x180013a43  nop
0x180013a44  test    al, al
0x180013a46  jz      short loc_180013A58
0x180013a48  mov     rcx, rsi; _Mtx_t
0x180013a4b  call    cs:__imp__Mtx_unlock
0x180013a51  xor     eax, eax
0x180013a53  jmp     loc_180013FCB
0x180013a58  mov     [rsp+98h+var_47], 1
0x180013a5d  mov     [rsp+98h+var_5F], 1
0x180013a62  mov     [rsp+98h+var_68], rdi
0x180013a67  mov     rax, [rbx]
0x180013a6a  lea     r8, [rsp+98h+var_68]
0x180013a6f  lea     rdx, _GUID_e3bf92f3_c197_436f_8265_0625824f8dac
0x180013a76  mov     rcx, rbx
0x180013a79  mov     rax, [rax]
0x180013a7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a81  mov     ebx, eax
0x180013a83  test    eax, eax
0x180013a85  jns     loc_180013B23
0x180013a8b  mov     rcx, [rsp+98h]; this
0x180013a93  mov     r9d, eax; char *
0x180013a96  lea     r8, aBaseDiagnosisM_1; "base\\diagnosis\\memdiag\\onlinemd\\aom"...
0x180013a9d  mov     edx, 29Fh; void *
0x180013aa2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013aa7  nop
0x180013aa8  mov     rcx, [rsp+98h+var_68]
0x180013aad  test    rcx, rcx
0x180013ab0  jz      short loc_180013AC4
0x180013ab2  mov     [rsp+98h+var_68], rdi
0x180013ab7  mov     rax, [rcx]
0x180013aba  mov     rax, [rax+10h]
0x180013abe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ac3  nop
0x180013ac4  mov     eax, 5
0x180013ac9  xchg    eax, cs:?g_aomdPromptResult@@3U?$atomic@W4AOMDPromptResult@@@std@@A; std::atomic<AOMDPromptResult> g_aomdPromptResult
0x180013acf  lea     rcx, aAomdpromptresu_7; "AOMDPromptResult::MainToastActivatedPro"...
0x180013ad6  mov     r8, rcx
0x180013ad9  mov     al, 41h ; 'A'
0x180013adb  inc     rcx
0x180013ade  cmp     al, 3Ah ; ':'
0x180013ae0  jnz     short loc_180013AE5
0x180013ae2  mov     r8, rcx
0x180013ae5  mov     al, [rcx]
0x180013ae7  test    al, al
0x180013ae9  jnz     short loc_180013ADB
0x180013aeb  mov     edx, 5
0x180013af0  call    ?complete_and_succeed@?$tip_test@V?$merged_data@U_tip_AOMDUsageTipTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::complete_and_succeed(ushort,char const *)
0x180013af5  nop
0x180013af6  mov     rcx, cs:?g_exitEvent@@3V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@A; hEvent
0x180013afd  call    cs:__imp_SetEvent
0x180013b03  mov     rcx, [rsp+98h]; this
0x180013b0b  test    eax, eax
0x180013b0d  jz      loc_180013FF0
0x180013b13  mov     rcx, rsi; _Mtx_t
0x180013b16  call    cs:__imp__Mtx_unlock
0x180013b1c  mov     eax, ebx
0x180013b1e  jmp     loc_180013FCB
0x180013b23  mov     [rsp+98h+string], rdi
0x180013b28  mov     rcx, [rsp+98h+var_68]
0x180013b2d  mov     rax, [rcx]
0x180013b30  mov     [rsp+98h+string], rdi
0x180013b35  lea     rdx, [rsp+98h+string]
0x180013b3a  mov     rax, [rax+30h]
0x180013b3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b43  mov     ebx, eax
0x180013b45  test    eax, eax
0x180013b47  jns     loc_180013BF6
0x180013b4d  mov     rcx, [rsp+98h]; this
0x180013b55  mov     r9d, eax; char *
0x180013b58  lea     r8, aBaseDiagnosisM_1; "base\\diagnosis\\memdiag\\onlinemd\\aom"...
0x180013b5f  mov     edx, 2A2h; void *
0x180013b64  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013b69  nop
0x180013b6a  mov     rcx, [rsp+98h+string]; string
0x180013b6f  test    rcx, rcx
0x180013b72  jz      short loc_180013B7B
0x180013b74  call    cs:__imp_WindowsDeleteString
0x180013b7a  nop
0x180013b7b  mov     rcx, [rsp+98h+var_68]
0x180013b80  test    rcx, rcx
0x180013b83  jz      short loc_180013B97
0x180013b85  mov     [rsp+98h+var_68], rdi
0x180013b8a  mov     rax, [rcx]
0x180013b8d  mov     rax, [rax+10h]
0x180013b91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b96  nop
0x180013b97  mov     eax, 5
0x180013b9c  xchg    eax, cs:?g_aomdPromptResult@@3U?$atomic@W4AOMDPromptResult@@@std@@A; std::atomic<AOMDPromptResult> g_aomdPromptResult
0x180013ba2  lea     rcx, aAomdpromptresu_7; "AOMDPromptResult::MainToastActivatedPro"...
0x180013ba9  mov     r8, rcx
0x180013bac  mov     al, 41h ; 'A'
0x180013bae  inc     rcx
0x180013bb1  cmp     al, 3Ah ; ':'
0x180013bb3  jnz     short loc_180013BB8
0x180013bb5  mov     r8, rcx
0x180013bb8  mov     al, [rcx]
0x180013bba  test    al, al
0x180013bbc  jnz     short loc_180013BAE
0x180013bbe  mov     edx, 5
0x180013bc3  call    ?complete_and_succeed@?$tip_test@V?$merged_data@U_tip_AOMDUsageTipTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::complete_and_succeed(ushort,char const *)
0x180013bc8  nop
0x180013bc9  mov     rcx, cs:?g_exitEvent@@3V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@A; hEvent
0x180013bd0  call    cs:__imp_SetEvent
0x180013bd6  mov     rcx, [rsp+98h]; this
0x180013bde  test    eax, eax
0x180013be0  jz      loc_180013FFB
0x180013be6  mov     rcx, rsi; _Mtx_t
0x180013be9  call    cs:__imp__Mtx_unlock
0x180013bef  mov     eax, ebx
0x180013bf1  jmp     loc_180013FCB
0x180013bf6  xor     edx, edx; length
0x180013bf8  mov     rcx, [rsp+98h+string]; string
0x180013bfd  call    cs:__imp_WindowsGetStringRawBuffer
0x180013c03  xorps   xmm0, xmm0
0x180013c06  movups  xmmword ptr [rsp+98h+S1], xmm0
0x180013c0b  mov     [rsp+98h+N], rdi
0x180013c10  mov     [rsp+98h+var_20], rdi
0x180013c15  or      r8, 0FFFFFFFFFFFFFFFFh
0x180013c19  inc     r8
0x180013c1c  cmp     [rax+r8*2], di
0x180013c21  jnz     short loc_180013C19
0x180013c23  mov     rdx, rax
0x180013c26  lea     rcx, [rsp+98h+S1]
0x180013c2b  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180013c30  nop
0x180013c31  mov     rax, [rsp+98h+N]
0x180013c36  test    rax, rax
0x180013c39  jnz     short loc_180013CB5
0x180013c3b  call    ?Provider@TlgHelper@@SAPEBU_tlgProvider_t@@XZ; TlgHelper::Provider(void)
0x180013c40  mov     ecx, [rax]
0x180013c42  cmp     ecx, 4
0x180013c45  jbe     short loc_180013C84
0x180013c47  mov     rdx, [rax+18h]
0x180013c4b  mov     rcx, [rax+10h]
0x180013c4f  test    cl, 2
0x180013c52  jz      short loc_180013C84
0x180013c54  mov     rcx, rdx
0x180013c57  and     ecx, 2
0x180013c5a  cmp     rcx, rdx
0x180013c5d  jnz     short loc_180013C84
0x180013c5f  lea     rcx, aToastactivated_2; "ToastActivatedCallback_ToastBodyClicked"
0x180013c66  mov     [rsp+98h+var_58], rcx
0x180013c6b  lea     rcx, [rsp+98h+var_58]
0x180013c70  mov     [rsp+98h+var_78], rcx
0x180013c75  lea     rdx, byte_180029F51
0x180013c7c  mov     rcx, rax
0x180013c7f  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180013c84  mov     eax, 0Dh
0x180013c89  xchg    eax, cs:?g_aomdPromptResult@@3U?$atomic@W4AOMDPromptResult@@@std@@A; std::atomic<AOMDPromptResult> g_aomdPromptResult
0x180013c8f  lea     rcx, aAomdpromptresu_4; "AOMDPromptResult::UserChoiceBodyClick"
0x180013c96  mov     r8, rcx
0x180013c99  mov     al, 41h ; 'A'
0x180013c9b  inc     rcx
0x180013c9e  cmp     al, 3Ah ; ':'
0x180013ca0  jnz     short loc_180013CA5
0x180013ca2  mov     r8, rcx
0x180013ca5  mov     al, [rcx]
0x180013ca7  test    al, al
0x180013ca9  jnz     short loc_180013C9B
0x180013cab  mov     edx, 0Dh
0x180013cb0  jmp     loc_180013EBF
0x180013cb5  lea     rcx, [rsp+98h+S1]
0x180013cba  mov     rdx, [rsp+98h+S1]
0x180013cbf  mov     r8, [rsp+98h+var_20]
0x180013cc4  cmp     r8, 7
0x180013cc8  cmova   rcx, rdx; S1
0x180013ccc  cmp     rax, 6
0x180013cd0  jnz     loc_180013D6F
0x180013cd6  mov     r8, rax; N
0x180013cd9  lea     rdx, aIdYes; "id_yes"
0x180013ce0  call    wmemcmp
0x180013ce5  test    eax, eax
0x180013ce7  jnz     short loc_180013D60
0x180013ce9  call    ?Provider@TlgHelper@@SAPEBU_tlgProvider_t@@XZ; TlgHelper::Provider(void)
0x180013cee  mov     ecx, [rax]
0x180013cf0  cmp     ecx, 4
0x180013cf3  jbe     short loc_180013D32
0x180013cf5  mov     rdx, [rax+18h]
0x180013cf9  mov     rcx, [rax+10h]
0x180013cfd  test    cl, 2
0x180013d00  jz      short loc_180013D32
0x180013d02  mov     rcx, rdx
0x180013d05  and     ecx, 2
0x180013d08  cmp     rcx, rdx
0x180013d0b  jnz     short loc_180013D32
0x180013d0d  lea     rcx, aToastactivated_0; "ToastActivatedCallback_YesButtonClicked"
0x180013d14  mov     [rsp+98h+var_58], rcx
0x180013d19  lea     rcx, [rsp+98h+var_58]
0x180013d1e  mov     [rsp+98h+var_78], rcx
0x180013d23  lea     rdx, byte_180029F51
0x180013d2a  mov     rcx, rax
0x180013d2d  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180013d32  mov     edx, 0Ah
0x180013d37  mov     eax, edx
0x180013d39  xchg    eax, cs:?g_aomdPromptResult@@3U?$atomic@W4AOMDPromptResult@@@std@@A; std::atomic<AOMDPromptResult> g_aomdPromptResult
0x180013d3f  lea     rcx, aAomdpromptresu_11; "AOMDPromptResult::UserChoiceYes"
0x180013d46  mov     r8, rcx
0x180013d49  mov     al, 41h ; 'A'
0x180013d4b  inc     rcx
0x180013d4e  cmp     al, 3Ah ; ':'
0x180013d50  jnz     short loc_180013D55
0x180013d52  mov     r8, rcx
0x180013d55  mov     al, [rcx]
0x180013d57  test    al, al
0x180013d59  jnz     short loc_180013D4B
0x180013d5b  jmp     loc_180013EBF
0x180013d60  mov     r8, [rsp+98h+var_20]
0x180013d65  mov     rax, [rsp+98h+N]
0x180013d6a  mov     rdx, [rsp+98h+S1]
0x180013d6f  lea     rcx, [rsp+98h+S1]
0x180013d74  cmp     r8, 7
0x180013d78  cmova   rcx, rdx; S1
0x180013d7c  cmp     rax, 5
0x180013d80  jnz     loc_180013E1F
0x180013d86  mov     r8, rax; N
0x180013d89  lea     rdx, aIdNo; "id_no"
0x180013d90  call    wmemcmp
0x180013d95  test    eax, eax
0x180013d97  jnz     short loc_180013E10
0x180013d99  call    ?Provider@TlgHelper@@SAPEBU_tlgProvider_t@@XZ; TlgHelper::Provider(void)
0x180013d9e  mov     ecx, [rax]
0x180013da0  cmp     ecx, 4
0x180013da3  jbe     short loc_180013DE2
0x180013da5  mov     rdx, [rax+18h]
0x180013da9  mov     rcx, [rax+10h]
0x180013dad  test    cl, 2
0x180013db0  jz      short loc_180013DE2
0x180013db2  mov     rcx, rdx
0x180013db5  and     ecx, 2
0x180013db8  cmp     rcx, rdx
0x180013dbb  jnz     short loc_180013DE2
0x180013dbd  lea     rcx, aToastactivated_1; "ToastActivatedCallback_NoButtonClicked"
0x180013dc4  mov     [rsp+98h+var_58], rcx
0x180013dc9  lea     rcx, [rsp+98h+var_58]
0x180013dce  mov     [rsp+98h+var_78], rcx
0x180013dd3  lea     rdx, byte_180029F35
0x180013dda  mov     rcx, rax
0x180013ddd  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180013de2  mov     edx, 0Bh
0x180013de7  mov     eax, edx
0x180013de9  xchg    eax, cs:?g_aomdPromptResult@@3U?$atomic@W4AOMDPromptResult@@@std@@A; std::atomic<AOMDPromptResult> g_aomdPromptResult
0x180013def  lea     rcx, aAomdpromptresu; "AOMDPromptResult::UserChoiceNo"
0x180013df6  mov     r8, rcx
0x180013df9  mov     al, 41h ; 'A'
0x180013dfb  inc     rcx
0x180013dfe  cmp     al, 3Ah ; ':'
0x180013e00  jnz     short loc_180013E05
0x180013e02  mov     r8, rcx
0x180013e05  mov     al, [rcx]
0x180013e07  test    al, al
0x180013e09  jnz     short loc_180013DFB
0x180013e0b  jmp     loc_180013EBF
0x180013e10  mov     r8, [rsp+98h+var_20]
0x180013e15  mov     rax, [rsp+98h+N]
0x180013e1a  mov     rdx, [rsp+98h+S1]
0x180013e1f  lea     rcx, [rsp+98h+S1]
0x180013e24  cmp     r8, 7
0x180013e28  cmova   rcx, rdx; S1
0x180013e2c  cmp     rax, 0Dh
0x180013e30  jnz     loc_180013F2E
0x180013e36  mov     r8, rax; N
0x180013e39  lea     rdx, aIdLearnMore; "id_learn_more"
0x180013e40  call    wmemcmp
0x180013e45  test    eax, eax
0x180013e47  jnz     loc_180013F2E
0x180013e4d  call    ?Provider@TlgHelper@@SAPEBU_tlgProvider_t@@XZ; TlgHelper::Provider(void)
0x180013e52  mov     ecx, [rax]
0x180013e54  cmp     ecx, 4
0x180013e57  jbe     short loc_180013E96
0x180013e59  mov     rdx, [rax+18h]
0x180013e5d  mov     rcx, [rax+10h]
0x180013e61  test    cl, 2
0x180013e64  jz      short loc_180013E96
0x180013e66  mov     rcx, rdx
0x180013e69  and     ecx, 2
0x180013e6c  cmp     rcx, rdx
  ... truncated ...
```
