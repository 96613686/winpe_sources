# ToastActivatedCallback(Windows::UI::Notifications::IToastNotification *,IInspectable *)

- ea: `0x1800145d0`
- end: `0x180014cca`
- name: `?ToastActivatedCallback@@YAJPEAUIToastNotification@Notifications@UI@Windows@@PEAUIInspectable@@@Z`
- size: `1786`
- prototype: `__int64 __fastcall(struct Windows::UI::Notifications::IToastNotification *, struct IInspectable *)`
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001008`
- `0x1800026b0`
- `0x180005c80`
- `0x180007858`
- `0x18000f144`
- `0x1800113a4`
- `0x1800145d0`
- `0x1800162e8`
- `0x1800165dc`
- `0x180021868`
- `0x180024010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x18001465d`
- `msvcp_win!_Mtx_unlock` at `0x18001473f`
- `msvcp_win!_Mtx_unlock` at `0x18001482f`
- `msvcp_win!_Mtx_unlock` at `0x180014baa`
- `msvcp_win!_Mtx_unlock` at `0x180014c60`
- `msvcp_win!_Mtx_unlock` at `0x18001465d`
- `msvcp_win!_Mtx_unlock` at `0x18001473f`
- `msvcp_win!_Mtx_unlock` at `0x18001482f`
- `msvcp_win!_Mtx_unlock` at `0x180014baa`
- `msvcp_win!_Mtx_unlock` at `0x180014c60`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001461b`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180014642`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001461b`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180014642`
- `msvcp_win!_Mtx_lock` at `0x180014606`
- `msvcp_win!_Mtx_lock` at `0x180014606`
- `KERNEL32!SetEvent` at `0x180014720`
- `KERNEL32!SetEvent` at `0x180014810`
- `KERNEL32!SetEvent` at `0x180014b8b`
- `KERNEL32!SetEvent` at `0x180014c45`
- `KERNEL32!SetEvent` at `0x180014720`
- `KERNEL32!SetEvent` at `0x180014810`
- `KERNEL32!SetEvent` at `0x180014b8b`
- `KERNEL32!SetEvent` at `0x180014c45`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800147a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014b5b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014bd8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800147a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014b5b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014bd8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180014849`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180014849`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 __fastcall ToastActivatedCallback(
        struct Windows::UI::Notifications::IToastNotification *a1,
        struct IInspectable *a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  _QWORD *v6; // rcx
  const char *v7; // rdx
  const char *v8; // r9
  const char *v9; // rax
  unsigned int v10; // r8d
  const char *v11; // r9
  __int64 v12; // rax
  int v13; // eax
  _QWORD *v14; // rcx
  const char *v15; // rdx
  const char *v16; // r9
  const char *v17; // rax
  unsigned int v18; // r8d
  const char *v19; // r9
  PCWSTR StringRawBuffer; // rax
  __int64 v21; // r8
  const wchar_t *v22; // rdx
  __int64 v23; // rcx
  const struct _tlgProvider_t *v24; // rax
  __int64 v25; // rcx
  int v26; // r8d
  int v27; // r9d
  const char *v28; // rdx
  const char *v29; // r8
  const char *v30; // rax
  __int64 v31; // rdx
  char *v32; // r9
  __int64 v33; // r8
  signed __int64 v34; // r9
  const struct _tlgProvider_t *v35; // rax
  int v36; // r8d
  int v37; // r9d
  const char *v38; // r9
  const char *v39; // rax
  __int128 *v40; // r9
  __int64 v41; // r8
  const struct _tlgProvider_t *v42; // rax
  int v43; // r8d
  int v44; // r9d
  const char *v45; // r9
  const char *v46; // rax
  __int128 *v47; // r8
  const struct _tlgProvider_t *v48; // rax
  int v49; // r8d
  int v50; // r9d
  const char *v51; // r9
  const char *v52; // rax
  _QWORD *v53; // rcx
  unsigned int v54; // r8d
  const char *v55; // r9
  _QWORD *v56; // rcx
  const char *v57; // rdx
  const char *v58; // r9
  const char *v59; // rax
  unsigned int v60; // r8d
  const char *v61; // r9
  int v62; // [rsp+20h] [rbp-88h]
  _QWORD *v63; // [rsp+30h] [rbp-78h] BYREF
  char v64; // [rsp+39h] [rbp-6Fh]
  HSTRING string; // [rsp+40h] [rbp-68h] BYREF
  char v66; // [rsp+49h] [rbp-5Fh]
  const wchar_t *v67; // [rsp+50h] [rbp-58h] BYREF
  const wchar_t *v68; // [rsp+58h] [rbp-50h] BYREF
  const wchar_t *v69; // [rsp+60h] [rbp-48h] BYREF
  _QWORD v70[2]; // [rsp+68h] [rbp-40h] BYREF
  __int128 v71; // [rsp+78h] [rbp-30h] BYREF
  __int64 v72; // [rsp+88h] [rbp-20h]
  unsigned __int64 v73; // [rsp+90h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v70[1] = &g_toastSubscriptionMutex;
  if ( _Mtx_lock((_Mtx_t)&g_toastSubscriptionMutex) )
    std::_Throw_Cpp_error(5);
  if ( dword_180030E04 == 0x7FFFFFFF )
  {
    dword_180030E04 = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  if ( g_isTaskShuttingDown )
  {
    _Mtx_unlock((_Mtx_t)&g_toastSubscriptionMutex);
    return 0;
  }
  v66 = 1;
  v64 = 1;
  v63 = 0;
  v4 = ((__int64 (__fastcall *)(struct IInspectable *, GUID *, _QWORD **))a2->lpVtbl->QueryInterface)(
         a2,
         &GUID_e3bf92f3_c197_436f_8265_0625824f8dac,
         &v63);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2FD,
      (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
      (const char *)(unsigned int)v4,
      v62);
    v6 = v63;
    if ( v63 )
    {
      v63 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v6 + 16LL))(v6);
    }
    _InterlockedExchange(&g_aomdPromptResult, 5);
    v7 = "AOMDPromptResult::MainToastActivatedProcessingFailed";
    v8 = "AOMDPromptResult::MainToastActivatedProcessingFailed";
    LOBYTE(v6) = 65;
    do
    {
      v9 = ++v7;
      if ( (_BYTE)v6 != 58 )
        v9 = v8;
      v8 = v9;
      LOBYTE(v6) = *v7;
    }
    while ( *v7 );
    tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::complete_and_succeed(
      v6,
      5,
      v9);
    if ( !SetEvent(g_exitEvent) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D3, v10, v11);
LABEL_15:
    _Mtx_unlock((_Mtx_t)&g_toastSubscriptionMutex);
    return v5;
  }
  string = 0;
  v12 = *v63;
  string = 0;
  v13 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING *))(v12 + 48))(v63, &string);
  v5 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x300,
      (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
      (const char *)(unsigned int)v13,
      v62);
    if ( string )
      WindowsDeleteString(string);
    v14 = v63;
    if ( v63 )
    {
      v63 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v14 + 16LL))(v14);
    }
    _InterlockedExchange(&g_aomdPromptResult, 5);
    v15 = "AOMDPromptResult::MainToastActivatedProcessingFailed";
    v16 = "AOMDPromptResult::MainToastActivatedProcessingFailed";
    LOBYTE(v14) = 65;
    do
    {
      v17 = ++v15;
      if ( (_BYTE)v14 != 58 )
        v17 = v16;
      v16 = v17;
      LOBYTE(v14) = *v15;
    }
    while ( *v15 );
    tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::complete_and_succeed(
      v14,
      5,
      v17);
    if ( !SetEvent(g_exitEvent) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D3, v18, v19);
    goto LABEL_15;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v71 = 0;
  v72 = 0;
  v73 = 0;
  v21 = -1;
  do
    ++v21;
  while ( StringRawBuffer[v21] );
  std::wstring::_Construct<1,unsigned short const *>(&v71);
  v23 = v72;
  if ( v72 )
  {
    v32 = (char *)&v71;
    if ( v73 > 7 )
      v32 = (char *)v71;
    if ( v72 == 6 )
    {
      v33 = 6;
      v22 = L"id_yes";
      v34 = v32 - (char *)L"id_yes";
      while ( *(const wchar_t *)((char *)v22 + v34) == *v22 )
      {
        ++v22;
        if ( !--v33 )
        {
          v35 = TlgHelper::Provider();
          if ( *(_DWORD *)v35 > 4u && (*((_BYTE *)v35 + 16) & 2) != 0 )
          {
            v25 = *((_QWORD *)v35 + 3) & 2LL;
            if ( v25 == *((_QWORD *)v35 + 3) )
            {
              v68 = L"ToastActivatedCallback_YesButtonClicked";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
                (_DWORD)v35,
                (unsigned int)&unk_18002AB01,
                v36,
                v37,
                (__int64)&v68);
            }
          }
          v31 = 10;
          _InterlockedExchange(&g_aomdPromptResult, 10);
          v38 = "AOMDPromptResult::UserChoiceYes";
          v29 = "AOMDPromptResult::UserChoiceYes";
          LOBYTE(v25) = 65;
          do
          {
            v39 = ++v38;
            if ( (_BYTE)v25 != 58 )
              v39 = v29;
            v29 = v39;
            LOBYTE(v25) = *v38;
          }
          while ( *v38 );
          goto LABEL_83;
        }
      }
    }
    v40 = &v71;
    if ( v73 > 7 )
      v40 = (__int128 *)v71;
    if ( v72 == 18 )
    {
      v41 = 18;
      v22 = L"id_remind_me_later";
      v40 = (__int128 *)((char *)v40 - (unsigned __int64)L"id_remind_me_later");
      while ( *(_WORD *)((char *)v40 + (_QWORD)v22) == *v22 )
      {
        ++v22;
        if ( !--v41 )
        {
          v42 = TlgHelper::Provider();
          if ( *(_DWORD *)v42 > 4u && (*((_BYTE *)v42 + 16) & 2) != 0 )
          {
            v25 = *((_QWORD *)v42 + 3) & 2LL;
            if ( v25 == *((_QWORD *)v42 + 3) )
            {
              v69 = L"ToastActivatedCallback_RemindMeLaterButtonClicked";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
                (_DWORD)v42,
                (unsigned int)&unk_18002AB01,
                v43,
                v44,
                (__int64)&v69);
            }
          }
          v31 = 15;
          _InterlockedExchange(&g_aomdPromptResult, 15);
          v45 = "AOMDPromptResult::RemindMeLater";
          v29 = "AOMDPromptResult::RemindMeLater";
          LOBYTE(v25) = 65;
          do
          {
            v46 = ++v45;
            if ( (_BYTE)v25 != 58 )
              v46 = v29;
            v29 = v46;
            LOBYTE(v25) = *v45;
          }
          while ( *v45 );
          goto LABEL_83;
        }
      }
    }
    v47 = &v71;
    if ( v73 > 7 )
      v47 = (__int128 *)v71;
    if ( v72 == 13 )
    {
      v22 = L"id_learn_more";
      v47 = (__int128 *)((char *)v47 - (unsigned __int64)L"id_learn_more");
      while ( *(_WORD *)((char *)v47 + (_QWORD)v22) == *v22 )
      {
        ++v22;
        if ( !--v23 )
        {
          v48 = TlgHelper::Provider();
          if ( *(_DWORD *)v48 > 4u && (*((_BYTE *)v48 + 16) & 2) != 0 )
          {
            v25 = *((_QWORD *)v48 + 3) & 2LL;
            if ( v25 == *((_QWORD *)v48 + 3) )
            {
              v70[0] = L"ToastActivatedCallback_LearnMoreButtonClicked";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
                (_DWORD)v48,
                (unsigned int)&unk_18002AB01,
                v49,
                v50,
                (__int64)v70);
            }
          }
          v31 = 12;
          _InterlockedExchange(&g_aomdPromptResult, 12);
          v51 = "AOMDPromptResult::UserChoiceLearnMore";
          v29 = "AOMDPromptResult::UserChoiceLearnMore";
          LOBYTE(v25) = 65;
          do
          {
            v52 = ++v51;
            if ( (_BYTE)v25 != 58 )
              v52 = v29;
            v29 = v52;
            LOBYTE(v25) = *v51;
          }
          while ( *v51 );
          goto LABEL_83;
        }
      }
    }
    MicrosoftTelemetryAssertTriggeredNoArgs(v23, v22, v47, v40);
    std::wstring::~wstring(&v71);
    if ( string )
      WindowsDeleteString(string);
    v56 = v63;
    if ( v63 )
    {
      v63 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v56 + 16LL))(v56);
    }
    _InterlockedExchange(&g_aomdPromptResult, 5);
    v57 = "AOMDPromptResult::MainToastActivatedProcessingFailed";
    v58 = "AOMDPromptResult::MainToastActivatedProcessingFailed";
    LOBYTE(v56) = 65;
    do
    {
      v59 = ++v57;
      if ( (_BYTE)v56 != 58 )
        v59 = v58;
      v58 = v59;
      LOBYTE(v56) = *v57;
    }
    while ( *v57 );
    tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::complete_and_succeed(
      v56,
      5,
      v59);
    if ( !SetEvent(g_exitEvent) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D3, v60, v61);
    _Mtx_unlock((_Mtx_t)&g_toastSubscriptionMutex);
    return 2147549183LL;
  }
  else
  {
    v24 = TlgHelper::Provider();
    if ( *(_DWORD *)v24 > 4u && (*((_BYTE *)v24 + 16) & 2) != 0 )
    {
      v25 = *((_QWORD *)v24 + 3) & 2LL;
      if ( v25 == *((_QWORD *)v24 + 3) )
      {
        v67 = L"ToastActivatedCallback_ToastBodyClicked";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (_DWORD)v24,
          (unsigned int)&unk_18002AB01,
          v26,
          v27,
          (__int64)&v67);
      }
    }
    _InterlockedExchange(&g_aomdPromptResult, 13);
    v28 = "AOMDPromptResult::UserChoiceBodyClick";
    v29 = "AOMDPromptResult::UserChoiceBodyClick";
    LOBYTE(v25) = 65;
    do
    {
      v30 = ++v28;
      if ( (_BYTE)v25 != 58 )
        v30 = v29;
      v29 = v30;
      LOBYTE(v25) = *v28;
    }
    while ( *v28 );
    v31 = 13;
LABEL_83:
    tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::complete_and_succeed(
      v25,
      v31,
      v29);
    v64 = 0;
    std::wstring::~wstring(&v71);
    if ( string )
      WindowsDeleteString(string);
    v53 = v63;
    if ( v63 )
    {
      v63 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v53 + 16LL))(v53);
    }
    if ( !SetEvent(g_exitEvent) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D3, v54, v55);
    _Mtx_unlock((_Mtx_t)&g_toastSubscriptionMutex);
    return 0;
  }
}

```

## disassembly

```asm
0x1800145d0  mov     [rsp+arg_0], rbx
0x1800145d5  mov     [rsp+arg_10], rsi
0x1800145da  push    rdi
0x1800145db  sub     rsp, 0A0h
0x1800145e2  mov     rax, cs:__security_cookie
0x1800145e9  xor     rax, rsp
0x1800145ec  mov     [rsp+0A8h+var_10], rax
0x1800145f4  mov     rbx, rdx
0x1800145f7  lea     rsi, ?g_toastSubscriptionMutex@@3Vmutex@std@@A; std::mutex g_toastSubscriptionMutex
0x1800145fe  mov     [rsp+0A8h+var_38], rsi
0x180014603  mov     rcx, rsi; _Mtx_t
0x180014606  call    cs:__imp__Mtx_lock
0x18001460d  nop     dword ptr [rax+rax+00h]
0x180014612  xor     edi, edi
0x180014614  test    eax, eax
0x180014616  jz      short loc_180014627
0x180014618  lea     ecx, [rdi+5]
0x18001461b  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180014622  nop     dword ptr [rax+rax+00h]
0x180014627  cmp     cs:dword_180030E04, 7FFFFFFFh
0x180014631  jnz     short loc_18001464F
0x180014633  mov     cs:dword_180030E04, 7FFFFFFEh
0x18001463d  mov     ecx, 6
0x180014642  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180014649  nop     dword ptr [rax+rax+00h]
0x18001464e  nop
0x18001464f  mov     al, cs:?g_isTaskShuttingDown@@3U?$atomic@_N@std@@A; std::atomic<bool> g_isTaskShuttingDown
0x180014655  nop
0x180014656  test    al, al
0x180014658  jz      short loc_180014670
0x18001465a  mov     rcx, rsi; _Mtx_t
0x18001465d  call    cs:__imp__Mtx_unlock
0x180014664  nop     dword ptr [rax+rax+00h]
0x180014669  xor     eax, eax
0x18001466b  jmp     loc_180014C77
0x180014670  mov     [rsp+0A8h+var_5F], 1
0x180014675  mov     [rsp+0A8h+var_6F], 1
0x18001467a  mov     [rsp+0A8h+var_78], rdi
0x18001467f  mov     rax, [rbx]
0x180014682  lea     r8, [rsp+0A8h+var_78]
0x180014687  lea     rdx, _GUID_e3bf92f3_c197_436f_8265_0625824f8dac
0x18001468e  mov     rcx, rbx
0x180014691  mov     rax, [rax]
0x180014694  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014699  mov     ebx, eax
0x18001469b  test    eax, eax
0x18001469d  jns     loc_180014752
0x1800146a3  mov     rcx, [rsp+0A8h]; this
0x1800146ab  mov     r9d, eax; char *
0x1800146ae  lea     r8, aBaseDiagnosisM_1; "base\\diagnosis\\memdiag\\onlinemd\\aom"...
0x1800146b5  mov     edx, 2FDh; void *
0x1800146ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800146bf  nop
0x1800146c0  mov     rcx, [rsp+0A8h+var_78]
0x1800146c5  test    rcx, rcx
0x1800146c8  jz      short loc_1800146DC
0x1800146ca  mov     [rsp+0A8h+var_78], rdi
0x1800146cf  mov     rax, [rcx]
0x1800146d2  mov     rax, [rax+10h]
0x1800146d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800146db  nop
0x1800146dc  mov     r8d, 5
0x1800146e2  mov     eax, r8d
0x1800146e5  xchg    eax, cs:?g_aomdPromptResult@@3U?$atomic@W4AOMDPromptResult@@@std@@A; std::atomic<AOMDPromptResult> g_aomdPromptResult
0x1800146eb  lea     rdx, aAomdpromptresu_7; "AOMDPromptResult::MainToastActivatedPro"...
0x1800146f2  mov     r9, rdx
0x1800146f5  mov     cl, 41h ; 'A'
0x1800146f7  inc     rdx
0x1800146fa  mov     rax, rdx
0x1800146fd  cmp     cl, 3Ah ; ':'
0x180014700  cmovnz  rax, r9
0x180014704  mov     r9, rax
0x180014707  mov     cl, [rdx]
0x180014709  test    cl, cl
0x18001470b  jnz     short loc_1800146F7
0x18001470d  mov     edx, r8d
0x180014710  mov     r8, rax
0x180014713  call    ?complete_and_succeed@?$tip_test@V?$merged_data@U_tip_AOMDUsageTipTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::complete_and_succeed(ushort,char const *)
0x180014718  nop
0x180014719  mov     rcx, cs:?g_exitEvent@@3V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@A; hEvent
0x180014720  call    cs:__imp_SetEvent
0x180014727  nop     dword ptr [rax+rax+00h]
0x18001472c  mov     rcx, [rsp+0A8h]; this
0x180014734  test    eax, eax
0x180014736  jz      loc_180014C9D
0x18001473c  mov     rcx, rsi; _Mtx_t
0x18001473f  call    cs:__imp__Mtx_unlock
0x180014746  nop     dword ptr [rax+rax+00h]
0x18001474b  mov     eax, ebx
0x18001474d  jmp     loc_180014C77
0x180014752  mov     [rsp+0A8h+string], rdi
0x180014757  mov     rcx, [rsp+0A8h+var_78]
0x18001475c  mov     rax, [rcx]
0x18001475f  mov     [rsp+0A8h+string], rdi
0x180014764  lea     rdx, [rsp+0A8h+string]
0x180014769  mov     rax, [rax+30h]
0x18001476d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014772  mov     ebx, eax
0x180014774  test    eax, eax
0x180014776  jns     loc_180014842
0x18001477c  mov     rcx, [rsp+0A8h]; this
0x180014784  mov     r9d, eax; char *
0x180014787  lea     r8, aBaseDiagnosisM_1; "base\\diagnosis\\memdiag\\onlinemd\\aom"...
0x18001478e  mov     edx, 300h; void *
0x180014793  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014798  nop
0x180014799  mov     rcx, [rsp+0A8h+string]; string
0x18001479e  test    rcx, rcx
0x1800147a1  jz      short loc_1800147B0
0x1800147a3  call    cs:__imp_WindowsDeleteString
0x1800147aa  nop     dword ptr [rax+rax+00h]
0x1800147af  nop
0x1800147b0  mov     rcx, [rsp+0A8h+var_78]
0x1800147b5  test    rcx, rcx
0x1800147b8  jz      short loc_1800147CC
0x1800147ba  mov     [rsp+0A8h+var_78], rdi
0x1800147bf  mov     rax, [rcx]
0x1800147c2  mov     rax, [rax+10h]
0x1800147c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800147cb  nop
0x1800147cc  mov     r8d, 5
0x1800147d2  mov     eax, r8d
0x1800147d5  xchg    eax, cs:?g_aomdPromptResult@@3U?$atomic@W4AOMDPromptResult@@@std@@A; std::atomic<AOMDPromptResult> g_aomdPromptResult
0x1800147db  lea     rdx, aAomdpromptresu_7; "AOMDPromptResult::MainToastActivatedPro"...
0x1800147e2  mov     r9, rdx
0x1800147e5  mov     cl, 41h ; 'A'
0x1800147e7  inc     rdx
0x1800147ea  mov     rax, rdx
0x1800147ed  cmp     cl, 3Ah ; ':'
0x1800147f0  cmovnz  rax, r9
0x1800147f4  mov     r9, rax
0x1800147f7  mov     cl, [rdx]
0x1800147f9  test    cl, cl
0x1800147fb  jnz     short loc_1800147E7
0x1800147fd  mov     edx, r8d
0x180014800  mov     r8, rax
0x180014803  call    ?complete_and_succeed@?$tip_test@V?$merged_data@U_tip_AOMDUsageTipTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::complete_and_succeed(ushort,char const *)
0x180014808  nop
0x180014809  mov     rcx, cs:?g_exitEvent@@3V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@A; hEvent
0x180014810  call    cs:__imp_SetEvent
0x180014817  nop     dword ptr [rax+rax+00h]
0x18001481c  mov     rcx, [rsp+0A8h]; this
0x180014824  test    eax, eax
0x180014826  jz      loc_180014CA8
0x18001482c  mov     rcx, rsi; _Mtx_t
0x18001482f  call    cs:__imp__Mtx_unlock
0x180014836  nop     dword ptr [rax+rax+00h]
0x18001483b  mov     eax, ebx
0x18001483d  jmp     loc_180014C77
0x180014842  xor     edx, edx; length
0x180014844  mov     rcx, [rsp+0A8h+string]; string
0x180014849  call    cs:__imp_WindowsGetStringRawBuffer
0x180014850  nop     dword ptr [rax+rax+00h]
0x180014855  xorps   xmm0, xmm0
0x180014858  movups  [rsp+0A8h+var_30], xmm0
0x18001485d  mov     [rsp+0A8h+var_20], rdi
0x180014865  mov     [rsp+0A8h+var_18], rdi
0x18001486d  or      r8, 0FFFFFFFFFFFFFFFFh
0x180014871  inc     r8
0x180014874  cmp     [rax+r8*2], di
0x180014879  jnz     short loc_180014871
0x18001487b  mov     rdx, rax
0x18001487e  lea     rcx, [rsp+0A8h+var_30]
0x180014883  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180014888  nop
0x180014889  mov     rcx, [rsp+0A8h+var_20]
0x180014891  test    rcx, rcx
0x180014894  jnz     short loc_18001490F
0x180014896  call    ?Provider@TlgHelper@@SAPEBU_tlgProvider_t@@XZ; TlgHelper::Provider(void)
0x18001489b  cmp     dword ptr [rax], 4
0x18001489e  jbe     short loc_1800148D8
0x1800148a0  test    byte ptr [rax+10h], 2
0x1800148a4  jz      short loc_1800148D8
0x1800148a6  mov     rcx, [rax+18h]
0x1800148aa  and     ecx, 2
0x1800148ad  cmp     rcx, [rax+18h]
0x1800148b1  jnz     short loc_1800148D8
0x1800148b3  lea     rcx, aToastactivated_2; "ToastActivatedCallback_ToastBodyClicked"
0x1800148ba  mov     [rsp+0A8h+var_58], rcx
0x1800148bf  lea     rcx, [rsp+0A8h+var_58]
0x1800148c4  mov     qword ptr [rsp+0A8h+var_88], rcx
0x1800148c9  lea     rdx, byte_18002AB01
0x1800148d0  mov     rcx, rax
0x1800148d3  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800148d8  mov     eax, 0Dh
0x1800148dd  xchg    eax, cs:?g_aomdPromptResult@@3U?$atomic@W4AOMDPromptResult@@@std@@A; std::atomic<AOMDPromptResult> g_aomdPromptResult
0x1800148e3  lea     rdx, aAomdpromptresu_4; "AOMDPromptResult::UserChoiceBodyClick"
0x1800148ea  mov     r8, rdx
0x1800148ed  mov     cl, 41h ; 'A'
0x1800148ef  inc     rdx
0x1800148f2  mov     rax, rdx
0x1800148f5  cmp     cl, 3Ah ; ':'
0x1800148f8  cmovnz  rax, r8
0x1800148fc  mov     r8, rax
0x1800148ff  mov     cl, [rdx]
0x180014901  test    cl, cl
0x180014903  jnz     short loc_1800148EF
0x180014905  mov     edx, 0Dh
0x18001490a  jmp     loc_180014B3C
0x18001490f  lea     r9, [rsp+0A8h+var_30]
0x180014914  mov     r10, qword ptr [rsp+0A8h+var_30]
0x180014919  mov     r11, [rsp+0A8h+var_18]
0x180014921  cmp     r11, 7
0x180014925  cmova   r9, r10
0x180014929  cmp     rcx, 6
0x18001492d  jnz     loc_1800149D4
0x180014933  mov     r8, rcx
0x180014936  lea     rdx, aIdYes; "id_yes"
0x18001493d  test    rcx, rcx
0x180014940  jz      short loc_18001495D
0x180014942  sub     r9, rdx
0x180014945  movzx   eax, word ptr [rdx+r9]
0x18001494a  cmp     ax, [rdx]
0x18001494d  jnz     loc_1800149D4
0x180014953  add     rdx, 2
0x180014957  sub     r8, 1
0x18001495b  jnz     short loc_180014945
0x18001495d  call    ?Provider@TlgHelper@@SAPEBU_tlgProvider_t@@XZ; TlgHelper::Provider(void)
0x180014962  cmp     dword ptr [rax], 4
0x180014965  jbe     short loc_18001499F
0x180014967  test    byte ptr [rax+10h], 2
0x18001496b  jz      short loc_18001499F
0x18001496d  mov     rcx, [rax+18h]
0x180014971  and     ecx, 2
0x180014974  cmp     rcx, [rax+18h]
0x180014978  jnz     short loc_18001499F
0x18001497a  lea     rcx, aToastactivated_1; "ToastActivatedCallback_YesButtonClicked"
0x180014981  mov     [rsp+0A8h+var_50], rcx
0x180014986  lea     rcx, [rsp+0A8h+var_50]
0x18001498b  mov     qword ptr [rsp+0A8h+var_88], rcx
0x180014990  lea     rdx, byte_18002AB01
0x180014997  mov     rcx, rax
0x18001499a  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18001499f  mov     edx, 0Ah
0x1800149a4  mov     eax, edx
0x1800149a6  xchg    eax, cs:?g_aomdPromptResult@@3U?$atomic@W4AOMDPromptResult@@@std@@A; std::atomic<AOMDPromptResult> g_aomdPromptResult
0x1800149ac  lea     r9, aAomdpromptresu_12; "AOMDPromptResult::UserChoiceYes"
0x1800149b3  mov     r8, r9
0x1800149b6  mov     cl, 41h ; 'A'
0x1800149b8  inc     r9
0x1800149bb  mov     rax, r9
0x1800149be  cmp     cl, 3Ah ; ':'
0x1800149c1  cmovnz  rax, r8
0x1800149c5  mov     r8, rax
0x1800149c8  mov     cl, [r9]
0x1800149cb  test    cl, cl
0x1800149cd  jnz     short loc_1800149B8
0x1800149cf  jmp     loc_180014B3C
0x1800149d4  lea     r9, [rsp+0A8h+var_30]
0x1800149d9  cmp     r11, 7
0x1800149dd  cmova   r9, r10
0x1800149e1  cmp     rcx, 12h
0x1800149e5  jnz     loc_180014A8C
0x1800149eb  mov     r8, rcx
0x1800149ee  lea     rdx, aIdRemindMeLate; "id_remind_me_later"
0x1800149f5  test    rcx, rcx
0x1800149f8  jz      short loc_180014A15
0x1800149fa  sub     r9, rdx
0x1800149fd  movzx   eax, word ptr [rdx+r9]
0x180014a02  cmp     ax, [rdx]
0x180014a05  jnz     loc_180014A8C
0x180014a0b  add     rdx, 2
0x180014a0f  sub     r8, 1
0x180014a13  jnz     short loc_1800149FD
0x180014a15  call    ?Provider@TlgHelper@@SAPEBU_tlgProvider_t@@XZ; TlgHelper::Provider(void)
0x180014a1a  cmp     dword ptr [rax], 4
0x180014a1d  jbe     short loc_180014A57
0x180014a1f  test    byte ptr [rax+10h], 2
0x180014a23  jz      short loc_180014A57
0x180014a25  mov     rcx, [rax+18h]
0x180014a29  and     ecx, 2
0x180014a2c  cmp     rcx, [rax+18h]
0x180014a30  jnz     short loc_180014A57
0x180014a32  lea     rcx, aToastactivated_0; "ToastActivatedCallback_RemindMeLaterBut"...
0x180014a39  mov     [rsp+0A8h+var_48], rcx
0x180014a3e  lea     rcx, [rsp+0A8h+var_48]
0x180014a43  mov     qword ptr [rsp+0A8h+var_88], rcx
0x180014a48  lea     rdx, byte_18002AB01
0x180014a4f  mov     rcx, rax
0x180014a52  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180014a57  mov     edx, 0Fh
0x180014a5c  mov     eax, edx
0x180014a5e  xchg    eax, cs:?g_aomdPromptResult@@3U?$atomic@W4AOMDPromptResult@@@std@@A; std::atomic<AOMDPromptResult> g_aomdPromptResult
0x180014a64  lea     r9, aAomdpromptresu_3; "AOMDPromptResult::RemindMeLater"
0x180014a6b  mov     r8, r9
0x180014a6e  mov     cl, 41h ; 'A'
0x180014a70  inc     r9
0x180014a73  mov     rax, r9
0x180014a76  cmp     cl, 3Ah ; ':'
0x180014a79  cmovnz  rax, r8
0x180014a7d  mov     r8, rax
0x180014a80  mov     cl, [r9]
0x180014a83  test    cl, cl
0x180014a85  jnz     short loc_180014A70
0x180014a87  jmp     loc_180014B3C
0x180014a8c  lea     r8, [rsp+0A8h+var_30]
0x180014a91  cmp     r11, 7
0x180014a95  cmova   r8, r10
0x180014a99  cmp     rcx, 0Dh
0x180014a9d  jnz     loc_180014BBD
  ... truncated ...
```
