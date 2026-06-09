# AOMDHandler::DoWork(void)

- ea: `0x18000a7e4`
- end: `0x18000ad4d`
- name: `?DoWork@AOMDHandler@@AEAAJXZ`
- size: `1385`
- prototype: `__int64 __fastcall(AOMDHandler *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180015cd0`

## callees

- `0x180001008`
- `0x180007944`
- `0x180009504`
- `0x180009f8c`
- `0x18000a7e4`
- `0x18000b014`
- `0x18000df2c`
- `0x18000f144`
- `0x1800113a4`
- `0x180012024`
- `0x1800121a0`
- `0x1800156b4`
- `0x180015880`
- `0x18001634c`
- `0x180020c20`
- `0x180021868`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x18000ab07`
- `KERNEL32!WaitForSingleObject` at `0x18000ab07`

## string_xrefs

- `0x18000abbc`: `"%windir%\System32\mdsched.exe" /qd`
- `0x18000ac56`: `"%windir%\System32\mdsched.exe" /qm`
- `0x18000ace8`: `"%windir%\System32\mdsched.exe" /qm`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AOMDHandler::DoWork(AOMDHandler *this)
{
  __int64 result; // rax
  const struct _tlgProvider_t *v3; // rax
  int v4; // r8d
  const char *v5; // r9
  int v6; // eax
  unsigned int v7; // edi
  int v8; // eax
  unsigned int v9; // edi
  const struct _tlgProvider_t *v10; // rax
  int v11; // r8d
  int v12; // eax
  unsigned int v13; // edi
  const struct _tlgProvider_t *v14; // rax
  int v15; // r8d
  const struct _tlgProvider_t *v16; // rax
  int v17; // r8d
  int v18; // r9d
  int updated; // eax
  unsigned int v20; // esi
  int v21; // eax
  unsigned int v22; // esi
  const struct _tlgProvider_t *v23; // rax
  int v24; // r8d
  int v25; // r9d
  const struct _tlgProvider_t *v26; // rax
  int v27; // r8d
  int v28; // r9d
  __int64 v29; // rdx
  __int64 v30; // rcx
  __int64 v31; // r8
  __int64 v32; // r9
  const struct _tlgProvider_t *v33; // rax
  int v34; // r8d
  int v35; // r9d
  int started; // eax
  unsigned int v37; // r8d
  wil::details::in1diag3 *v38; // rcx
  __int64 v39; // rdx
  const struct _tlgProvider_t *v40; // rax
  int v41; // r8d
  int v42; // r9d
  const struct _tlgProvider_t *v43; // rax
  int v44; // r8d
  int v45; // r9d
  int v46; // [rsp+20h] [rbp-58h]
  int v47[2]; // [rsp+30h] [rbp-48h] BYREF
  const wchar_t *v48; // [rsp+38h] [rbp-40h] BYREF
  const wchar_t *v49; // [rsp+40h] [rbp-38h] BYREF
  __int64 v50; // [rsp+48h] [rbp-30h]
  AOMDHandler *v51; // [rsp+50h] [rbp-28h] BYREF
  char v52; // [rsp+58h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  const wchar_t *v54; // [rsp+88h] [rbp+10h] BYREF
  bool v55; // [rsp+90h] [rbp+18h] BYREF
  bool v56; // [rsp+98h] [rbp+20h] BYREF

  if ( !g_exitEvent )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6C7,
      (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
      (const char *)0x8000FFFFLL,
      v46);
    return 2147549183LL;
  }
  try
  {
    if ( AOMDHandler::ShouldExitEarly(this) )
    {
      v3 = TlgHelper::Provider();
      if ( *(_DWORD *)v3 > 4u && (*((_BYTE *)v3 + 16) & 2) != 0 && (*((_QWORD *)v3 + 3) & 2LL) == *((_QWORD *)v3 + 3) )
      {
        v54 = L"DoWork_ExitingEarly";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (_DWORD)v3,
          (unsigned int)&unk_18002AB01,
          v4,
          (_DWORD)v5,
          (__int64)&v54);
      }
      return 0;
    }
    AOMDHandler::InitializeConfig(this);
    LOBYTE(v54) = 0;
    v6 = AOMDHandler::CalcEffectiveLookbackTime(this, (bool *)&v54);
    v7 = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6D3,
        (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
        (const char *)(unsigned int)v6,
        v46);
      return v7;
    }
    if ( (_BYTE)v54 )
      return 0;
    v55 = 0;
    v8 = AOMDHandler::EventScanCriteriaMet(this, &v55);
    v9 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6D9,
        (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
        (const char *)(unsigned int)v8,
        v46);
      return v9;
    }
    if ( !v55 )
    {
      v10 = TlgHelper::Provider();
      if ( *(_DWORD *)v10 > 4u
        && (*((_BYTE *)v10 + 16) & 2) != 0
        && (*((_QWORD *)v10 + 3) & 2LL) == *((_QWORD *)v10 + 3) )
      {
        v54 = L"DoWork_ThresholdNotMetSkippingTest";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (_DWORD)v10,
          (unsigned int)&unk_18002AB01,
          v11,
          (_DWORD)v5,
          (__int64)&v54);
      }
      return 0;
    }
    v56 = 0;
    v12 = BitLockerCompatibilityCheck(&v56);
    v13 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6E1,
        (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
        (const char *)(unsigned int)v12,
        v46);
      return v13;
    }
    if ( !v56 )
    {
      v14 = TlgHelper::Provider();
      if ( *(_DWORD *)v14 > 4u
        && (*((_BYTE *)v14 + 16) & 2) != 0
        && (*((_QWORD *)v14 + 3) & 2LL) == *((_QWORD *)v14 + 3) )
      {
        v54 = L"DoWork_BitLockerCheckFailed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (_DWORD)v14,
          (unsigned int)&unk_18002AB01,
          v15,
          (_DWORD)v5,
          (__int64)&v54);
      }
      return 0;
    }
    v16 = TlgHelper::Provider();
    if ( *(_DWORD *)v16 > 4u && (*((_BYTE *)v16 + 16) & 2) != 0 && (*((_QWORD *)v16 + 3) & 2LL) == *((_QWORD *)v16 + 3) )
    {
      *(_QWORD *)v47 = L"DoWork_RequestingUserInput";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (_DWORD)v16,
        (unsigned int)&unk_18002AB01,
        v17,
        v18,
        (__int64)v47);
    }
    v51 = this;
    v52 = 1;
    updated = AOMDHandler::UpdateStatsOnThresholdMet(this);
    v20 = updated;
    if ( updated < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6F0,
        (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
        (const char *)(unsigned int)updated,
        v46);
      wil::details::lambda_call__lambda_2aa38bc2c6f84c9baa4bf19977ae0f94___::_lambda_call__lambda_2aa38bc2c6f84c9baa4bf19977ae0f94___(&v51);
      return v20;
    }
    v21 = AOMDHandler::ShowToast(this);
    v22 = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6F2,
        (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
        (const char *)(unsigned int)v21,
        v46);
      wil::details::lambda_call__lambda_2aa38bc2c6f84c9baa4bf19977ae0f94___::_lambda_call__lambda_2aa38bc2c6f84c9baa4bf19977ae0f94___(&v51);
      return v22;
    }
    v23 = TlgHelper::Provider();
    if ( *(_DWORD *)v23 > 4u && (*((_BYTE *)v23 + 16) & 1) != 0 && (*((_QWORD *)v23 + 3) & 1LL) == *((_QWORD *)v23 + 3) )
    {
      v48 = L"DoWork_WaitingForExitEventSignled";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (_DWORD)v23,
        (unsigned int)&unk_18002AF12,
        v24,
        v25,
        (__int64)&v48);
    }
    WaitForSingleObject(g_exitEvent, 0xFFFFFFFF);
    v26 = TlgHelper::Provider();
    if ( *(_DWORD *)v26 > 4u && (*((_BYTE *)v26 + 16) & 1) != 0 && (*((_QWORD *)v26 + 3) & 1LL) == *((_QWORD *)v26 + 3) )
    {
      v49 = L"DoWork_ExitEventSignled";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (_DWORD)v26,
        (unsigned int)&unk_18002AF12,
        v27,
        v28,
        (__int64)&v49);
    }
    g_isTaskShuttingDown = 1;
    AOMDHandler::UnsubscribeFromToastEventCallbacks(this);
    if ( g_aomdPromptResult == 10 )
    {
      v33 = TlgHelper::Provider();
      if ( *(_DWORD *)v33 > 4u
        && (*((_BYTE *)v33 + 16) & 2) != 0
        && (*((_QWORD *)v33 + 3) & 2LL) == *((_QWORD *)v33 + 3) )
      {
        v54 = L"DoWork_ProcessingUserChoiceYes";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (_DWORD)v33,
          (unsigned int)&unk_18002AB01,
          v34,
          v35,
          (__int64)&v54);
      }
      v49 = L"\"%windir%\\System32\\mdsched.exe\" /qd";
      v50 = 35;
      started = Utils::OS::StartChildProcess((__int64)&v49);
      v38 = retaddr;
      if ( started >= 0 )
        goto LABEL_69;
      v39 = 1792;
    }
    else if ( g_aomdPromptResult == 13 )
    {
      v40 = TlgHelper::Provider();
      if ( *(_DWORD *)v40 > 4u
        && (*((_BYTE *)v40 + 16) & 2) != 0
        && (*((_QWORD *)v40 + 3) & 2LL) == *((_QWORD *)v40 + 3) )
      {
        v54 = L"DoWork_ProcessingUserChoiceBodyClick";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (_DWORD)v40,
          (unsigned int)&unk_18002AB01,
          v41,
          v42,
          (__int64)&v54);
      }
      v49 = L"\"%windir%\\System32\\mdsched.exe\" /qm";
      v50 = 35;
      started = Utils::OS::StartChildProcess((__int64)&v49);
      v38 = retaddr;
      if ( started >= 0 )
        goto LABEL_69;
      v39 = 1807;
    }
    else
    {
      if ( g_aomdPromptResult != 12 )
      {
        if ( !g_aomdPromptResult )
          MicrosoftTelemetryAssertTriggeredNoArgs(v30, v29, v31, v32);
        goto LABEL_69;
      }
      v43 = TlgHelper::Provider();
      if ( *(_DWORD *)v43 > 4u
        && (*((_BYTE *)v43 + 16) & 2) != 0
        && (*((_QWORD *)v43 + 3) & 2LL) == *((_QWORD *)v43 + 3) )
      {
        v54 = L"DoWork_ProcessingUserChoiceLearnMore";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (_DWORD)v43,
          (unsigned int)&unk_18002AB01,
          v44,
          v45,
          (__int64)&v54);
      }
      v49 = L"\"%windir%\\System32\\mdsched.exe\" /qm";
      v50 = 35;
      started = Utils::OS::StartChildProcess((__int64)&v49);
      v38 = retaddr;
      if ( started >= 0 )
      {
LABEL_69:
        wil::details::lambda_call__lambda_2aa38bc2c6f84c9baa4bf19977ae0f94___::_lambda_call__lambda_2aa38bc2c6f84c9baa4bf19977ae0f94___(&v51);
        return 0;
      }
      v39 = 1815;
    }
    wil::details::in1diag3::_Log_Hr(v38, (void *)v39, v37, (const char *)(unsigned int)started, v46);
    goto LABEL_69;
  }
  catch ( ... )
  {
    LODWORD(v54) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0x71E,
                     (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
                     v5);
    return (unsigned int)v54;
  }
  return result;
}

```

## disassembly

```asm
0x18000a7e4  push    rbx
0x18000a7e6  push    rsi
0x18000a7e7  push    rdi
0x18000a7e8  sub     rsp, 60h
0x18000a7ec  mov     rbx, rcx
0x18000a7ef  cmp     cs:?g_exitEvent@@3V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@A, 0
0x18000a7f7  jnz     short loc_18000A81E
0x18000a7f9  mov     rcx, [rsp+78h]; this
0x18000a7fe  mov     ebx, 8000FFFFh
0x18000a803  mov     r9d, ebx; char *
0x18000a806  lea     r8, aBaseDiagnosisM_1; "base\\diagnosis\\memdiag\\onlinemd\\aom"...
0x18000a80d  mov     edx, 6C7h; void *
0x18000a812  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a817  mov     eax, ebx
0x18000a819  jmp     loc_18000AD44
0x18000a81e  call    ?ShouldExitEarly@AOMDHandler@@AEAA_NXZ; AOMDHandler::ShouldExitEarly(void)
0x18000a823  test    al, al
0x18000a825  jz      short loc_18000A876
0x18000a827  call    ?Provider@TlgHelper@@SAPEBU_tlgProvider_t@@XZ; TlgHelper::Provider(void)
0x18000a82c  cmp     dword ptr [rax], 4
0x18000a82f  jbe     short loc_18000A86F
0x18000a831  test    byte ptr [rax+10h], 2
0x18000a835  jz      short loc_18000A86F
0x18000a837  mov     rcx, [rax+18h]
0x18000a83b  and     ecx, 2
0x18000a83e  cmp     rcx, [rax+18h]
0x18000a842  jnz     short loc_18000A86F
0x18000a844  lea     rcx, aDoworkExitinge; "DoWork_ExitingEarly"
0x18000a84b  mov     [rsp+78h+arg_8], rcx
0x18000a853  lea     rcx, [rsp+78h+arg_8]
0x18000a85b  mov     qword ptr [rsp+78h+var_58], rcx
0x18000a860  lea     rdx, byte_18002AB01
0x18000a867  mov     rcx, rax
0x18000a86a  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18000a86f  xor     eax, eax
0x18000a871  jmp     loc_18000AD44
0x18000a876  mov     rcx, rbx; this
0x18000a879  call    ?InitializeConfig@AOMDHandler@@AEAAXXZ; AOMDHandler::InitializeConfig(void)
0x18000a87e  mov     byte ptr [rsp+78h+arg_8], 0
0x18000a886  lea     rdx, [rsp+78h+arg_8]; bool *
0x18000a88e  mov     rcx, rbx; this
0x18000a891  call    ?CalcEffectiveLookbackTime@AOMDHandler@@AEAAJAEA_N@Z; AOMDHandler::CalcEffectiveLookbackTime(bool &)
0x18000a896  mov     edi, eax
0x18000a898  test    eax, eax
0x18000a89a  jns     short loc_18000A8BC
0x18000a89c  mov     rcx, [rsp+78h]; this
0x18000a8a1  mov     r9d, eax; char *
0x18000a8a4  lea     r8, aBaseDiagnosisM_1; "base\\diagnosis\\memdiag\\onlinemd\\aom"...
0x18000a8ab  mov     edx, 6D3h; void *
0x18000a8b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a8b5  mov     eax, edi
0x18000a8b7  jmp     loc_18000AD44
0x18000a8bc  cmp     byte ptr [rsp+78h+arg_8], 0
0x18000a8c4  jz      short loc_18000A8CD
0x18000a8c6  xor     eax, eax
0x18000a8c8  jmp     loc_18000AD44
0x18000a8cd  mov     [rsp+78h+arg_10], 0
0x18000a8d5  lea     rdx, [rsp+78h+arg_10]; bool *
0x18000a8dd  mov     rcx, rbx; this
0x18000a8e0  call    ?EventScanCriteriaMet@AOMDHandler@@AEAAJAEA_N@Z; AOMDHandler::EventScanCriteriaMet(bool &)
0x18000a8e5  mov     edi, eax
0x18000a8e7  test    eax, eax
0x18000a8e9  jns     short loc_18000A90B
0x18000a8eb  mov     rcx, [rsp+78h]; this
0x18000a8f0  mov     r9d, eax; char *
0x18000a8f3  lea     r8, aBaseDiagnosisM_1; "base\\diagnosis\\memdiag\\onlinemd\\aom"...
0x18000a8fa  mov     edx, 6D9h; void *
0x18000a8ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a904  mov     eax, edi
0x18000a906  jmp     loc_18000AD44
0x18000a90b  cmp     [rsp+78h+arg_10], 0
0x18000a913  jnz     short loc_18000A964
0x18000a915  call    ?Provider@TlgHelper@@SAPEBU_tlgProvider_t@@XZ; TlgHelper::Provider(void)
0x18000a91a  cmp     dword ptr [rax], 4
0x18000a91d  jbe     short loc_18000A95D
0x18000a91f  test    byte ptr [rax+10h], 2
0x18000a923  jz      short loc_18000A95D
0x18000a925  mov     rcx, [rax+18h]
0x18000a929  and     ecx, 2
0x18000a92c  cmp     rcx, [rax+18h]
0x18000a930  jnz     short loc_18000A95D
0x18000a932  lea     rcx, aDoworkThreshol; "DoWork_ThresholdNotMetSkippingTest"
0x18000a939  mov     [rsp+78h+arg_8], rcx
0x18000a941  lea     rcx, [rsp+78h+arg_8]
0x18000a949  mov     qword ptr [rsp+78h+var_58], rcx
0x18000a94e  lea     rdx, byte_18002AB01
0x18000a955  mov     rcx, rax
0x18000a958  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18000a95d  xor     eax, eax
0x18000a95f  jmp     loc_18000AD44
0x18000a964  mov     [rsp+78h+arg_18], 0
0x18000a96c  lea     rcx, [rsp+78h+arg_18]; bool *
0x18000a974  call    ?BitLockerCompatibilityCheck@@YAJAEA_N@Z; BitLockerCompatibilityCheck(bool &)
0x18000a979  mov     edi, eax
0x18000a97b  test    eax, eax
0x18000a97d  jns     short loc_18000A99F
0x18000a97f  mov     rcx, [rsp+78h]; this
0x18000a984  mov     r9d, eax; char *
0x18000a987  lea     r8, aBaseDiagnosisM_1; "base\\diagnosis\\memdiag\\onlinemd\\aom"...
0x18000a98e  mov     edx, 6E1h; void *
0x18000a993  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a998  mov     eax, edi
0x18000a99a  jmp     loc_18000AD44
0x18000a99f  cmp     [rsp+78h+arg_18], 0
0x18000a9a7  jnz     short loc_18000A9F8
0x18000a9a9  call    ?Provider@TlgHelper@@SAPEBU_tlgProvider_t@@XZ; TlgHelper::Provider(void)
0x18000a9ae  cmp     dword ptr [rax], 4
0x18000a9b1  jbe     short loc_18000A9F1
0x18000a9b3  test    byte ptr [rax+10h], 2
0x18000a9b7  jz      short loc_18000A9F1
0x18000a9b9  mov     rcx, [rax+18h]
0x18000a9bd  and     ecx, 2
0x18000a9c0  cmp     rcx, [rax+18h]
0x18000a9c4  jnz     short loc_18000A9F1
0x18000a9c6  lea     rcx, aDoworkBitlocke; "DoWork_BitLockerCheckFailed"
0x18000a9cd  mov     [rsp+78h+arg_8], rcx
0x18000a9d5  lea     rcx, [rsp+78h+arg_8]
0x18000a9dd  mov     qword ptr [rsp+78h+var_58], rcx
0x18000a9e2  lea     rdx, byte_18002AB01
0x18000a9e9  mov     rcx, rax
0x18000a9ec  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18000a9f1  xor     eax, eax
0x18000a9f3  jmp     loc_18000AD44
0x18000a9f8  call    ?Provider@TlgHelper@@SAPEBU_tlgProvider_t@@XZ; TlgHelper::Provider(void)
0x18000a9fd  cmp     dword ptr [rax], 4
0x18000aa00  jbe     short loc_18000AA3A
0x18000aa02  test    byte ptr [rax+10h], 2
0x18000aa06  jz      short loc_18000AA3A
0x18000aa08  mov     rcx, [rax+18h]
0x18000aa0c  and     ecx, 2
0x18000aa0f  cmp     rcx, [rax+18h]
0x18000aa13  jnz     short loc_18000AA3A
0x18000aa15  lea     rcx, aDoworkRequesti; "DoWork_RequestingUserInput"
0x18000aa1c  mov     qword ptr [rsp+78h+var_48], rcx
0x18000aa21  lea     rcx, [rsp+78h+var_48]
0x18000aa26  mov     qword ptr [rsp+78h+var_58], rcx; int
0x18000aa2b  lea     rdx, byte_18002AB01
0x18000aa32  mov     rcx, rax
0x18000aa35  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18000aa3a  mov     [rsp+78h+var_28], rbx
0x18000aa3f  mov     edi, 1
0x18000aa44  mov     [rsp+78h+var_20], dil
0x18000aa49  mov     rcx, rbx; this
0x18000aa4c  call    ?UpdateStatsOnThresholdMet@AOMDHandler@@AEAAJXZ; AOMDHandler::UpdateStatsOnThresholdMet(void)
0x18000aa51  mov     esi, eax
0x18000aa53  test    eax, eax
0x18000aa55  jns     short loc_18000AA82
0x18000aa57  mov     rcx, [rsp+78h]; this
0x18000aa5c  mov     r9d, eax; char *
0x18000aa5f  lea     r8, aBaseDiagnosisM_1; "base\\diagnosis\\memdiag\\onlinemd\\aom"...
0x18000aa66  mov     edx, 6F0h; void *
0x18000aa6b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000aa70  nop
0x18000aa71  lea     rcx, [rsp+78h+var_28]
0x18000aa76  call    wil__details__lambda_call__lambda_2aa38bc2c6f84c9baa4bf19977ae0f94______lambda_call__lambda_2aa38bc2c6f84c9baa4bf19977ae0f94___
0x18000aa7b  mov     eax, esi
0x18000aa7d  jmp     loc_18000AD44
0x18000aa82  mov     rcx, rbx; this
0x18000aa85  call    ?ShowToast@AOMDHandler@@AEAAJXZ; AOMDHandler::ShowToast(void)
0x18000aa8a  mov     esi, eax
0x18000aa8c  test    eax, eax
0x18000aa8e  jns     short loc_18000AABB
0x18000aa90  mov     rcx, [rsp+78h]; this
0x18000aa95  mov     r9d, eax; char *
0x18000aa98  lea     r8, aBaseDiagnosisM_1; "base\\diagnosis\\memdiag\\onlinemd\\aom"...
0x18000aa9f  mov     edx, 6F2h; void *
0x18000aaa4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000aaa9  nop
0x18000aaaa  lea     rcx, [rsp+78h+var_28]
0x18000aaaf  call    wil__details__lambda_call__lambda_2aa38bc2c6f84c9baa4bf19977ae0f94______lambda_call__lambda_2aa38bc2c6f84c9baa4bf19977ae0f94___
0x18000aab4  mov     eax, esi
0x18000aab6  jmp     loc_18000AD44
0x18000aabb  call    ?Provider@TlgHelper@@SAPEBU_tlgProvider_t@@XZ; TlgHelper::Provider(void)
0x18000aac0  cmp     dword ptr [rax], 4
0x18000aac3  jbe     short loc_18000AAFD
0x18000aac5  test    [rax+10h], dil
0x18000aac9  jz      short loc_18000AAFD
0x18000aacb  mov     rcx, [rax+18h]
0x18000aacf  and     rcx, rdi
0x18000aad2  cmp     rcx, [rax+18h]
0x18000aad6  jnz     short loc_18000AAFD
0x18000aad8  lea     rcx, aDoworkWaitingf; "DoWork_WaitingForExitEventSignled"
0x18000aadf  mov     [rsp+78h+var_40], rcx
0x18000aae4  lea     rcx, [rsp+78h+var_40]
0x18000aae9  mov     qword ptr [rsp+78h+var_58], rcx
0x18000aaee  lea     rdx, byte_18002AF12
0x18000aaf5  mov     rcx, rax
0x18000aaf8  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18000aafd  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000ab00  mov     rcx, cs:?g_exitEvent@@3V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@A; hHandle
0x18000ab07  call    cs:__imp_WaitForSingleObject
0x18000ab0e  nop     dword ptr [rax+rax+00h]
0x18000ab13  call    ?Provider@TlgHelper@@SAPEBU_tlgProvider_t@@XZ; TlgHelper::Provider(void)
0x18000ab18  cmp     dword ptr [rax], 4
0x18000ab1b  jbe     short loc_18000AB55
0x18000ab1d  test    [rax+10h], dil
0x18000ab21  jz      short loc_18000AB55
0x18000ab23  mov     rcx, [rax+18h]
0x18000ab27  and     rcx, rdi
0x18000ab2a  cmp     rcx, [rax+18h]
0x18000ab2e  jnz     short loc_18000AB55
0x18000ab30  lea     rcx, aDoworkExiteven; "DoWork_ExitEventSignled"
0x18000ab37  mov     qword ptr [rsp+78h+var_38], rcx
0x18000ab3c  lea     rcx, [rsp+78h+var_38]
0x18000ab41  mov     qword ptr [rsp+78h+var_58], rcx
0x18000ab46  lea     rdx, byte_18002AF12
0x18000ab4d  mov     rcx, rax
0x18000ab50  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18000ab55  xchg    dil, cs:?g_isTaskShuttingDown@@3U?$atomic@_N@std@@A; std::atomic<bool> g_isTaskShuttingDown
0x18000ab5c  mov     rcx, rbx; this
0x18000ab5f  call    ?UnsubscribeFromToastEventCallbacks@AOMDHandler@@AEAAXXZ; AOMDHandler::UnsubscribeFromToastEventCallbacks(void)
0x18000ab64  mov     eax, cs:?g_aomdPromptResult@@3U?$atomic@W4AOMDPromptResult@@@std@@A; std::atomic<AOMDPromptResult> g_aomdPromptResult
0x18000ab6a  nop
0x18000ab6b  cmp     eax, 0Ah
0x18000ab6e  jnz     loc_18000AC05
0x18000ab74  call    ?Provider@TlgHelper@@SAPEBU_tlgProvider_t@@XZ; TlgHelper::Provider(void)
0x18000ab79  cmp     dword ptr [rax], 4
0x18000ab7c  jbe     short loc_18000ABBC
0x18000ab7e  test    byte ptr [rax+10h], 2
0x18000ab82  jz      short loc_18000ABBC
0x18000ab84  mov     rcx, [rax+18h]
0x18000ab88  and     ecx, 2
0x18000ab8b  cmp     rcx, [rax+18h]
0x18000ab8f  jnz     short loc_18000ABBC
0x18000ab91  lea     rcx, aDoworkProcessi_0; "DoWork_ProcessingUserChoiceYes"
0x18000ab98  mov     [rsp+78h+arg_8], rcx
0x18000aba0  lea     rcx, [rsp+78h+arg_8]
0x18000aba8  mov     qword ptr [rsp+78h+var_58], rcx; int
0x18000abad  lea     rdx, byte_18002AB01
0x18000abb4  mov     rcx, rax
0x18000abb7  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18000abbc  lea     rax, aWindirSystem32_0; "\"%windir%\\System32\\mdsched.exe\" /qd"
0x18000abc3  mov     qword ptr [rsp+78h+var_38], rax
0x18000abc8  mov     qword ptr [rsp+78h+var_38+8], 23h ; '#'
0x18000abd1  movaps  xmm0, [rsp+78h+var_38]
0x18000abd6  movdqa  [rsp+78h+var_38], xmm0
0x18000abdc  lea     rcx, [rsp+78h+var_38]
0x18000abe1  call    ?StartChildProcess@OS@Utils@@YAJV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; Utils::OS::StartChildProcess(std::basic_string_view<ushort>)
0x18000abe6  mov     rcx, [rsp+78h]; this
0x18000abeb  test    eax, eax
0x18000abed  jns     loc_18000AD2F
0x18000abf3  mov     edx, 700h; void *
0x18000abf8  mov     r9d, eax; char *
0x18000abfb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000ac00  jmp     loc_18000AD2F
0x18000ac05  cmp     eax, 0Dh
0x18000ac08  jnz     loc_18000AC97
0x18000ac0e  call    ?Provider@TlgHelper@@SAPEBU_tlgProvider_t@@XZ; TlgHelper::Provider(void)
0x18000ac13  cmp     dword ptr [rax], 4
0x18000ac16  jbe     short loc_18000AC56
0x18000ac18  test    byte ptr [rax+10h], 2
0x18000ac1c  jz      short loc_18000AC56
0x18000ac1e  mov     rcx, [rax+18h]
0x18000ac22  and     ecx, 2
0x18000ac25  cmp     rcx, [rax+18h]
0x18000ac29  jnz     short loc_18000AC56
0x18000ac2b  lea     rcx, aDoworkProcessi_1; "DoWork_ProcessingUserChoiceBodyClick"
0x18000ac32  mov     [rsp+78h+arg_8], rcx
0x18000ac3a  lea     rcx, [rsp+78h+arg_8]
0x18000ac42  mov     qword ptr [rsp+78h+var_58], rcx
0x18000ac47  lea     rdx, byte_18002AB01
0x18000ac4e  mov     rcx, rax
0x18000ac51  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18000ac56  lea     rax, aWindirSystem32; "\"%windir%\\System32\\mdsched.exe\" /qm"
0x18000ac5d  mov     qword ptr [rsp+78h+var_38], rax
0x18000ac62  mov     qword ptr [rsp+78h+var_38+8], 23h ; '#'
0x18000ac6b  movaps  xmm0, [rsp+78h+var_38]
0x18000ac70  movdqa  [rsp+78h+var_38], xmm0
0x18000ac76  lea     rcx, [rsp+78h+var_38]
0x18000ac7b  call    ?StartChildProcess@OS@Utils@@YAJV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; Utils::OS::StartChildProcess(std::basic_string_view<ushort>)
0x18000ac80  mov     rcx, [rsp+78h]
0x18000ac85  test    eax, eax
0x18000ac87  jns     loc_18000AD2F
0x18000ac8d  mov     edx, 70Fh
0x18000ac92  jmp     loc_18000ABF8
0x18000ac97  cmp     eax, 0Ch
0x18000ac9a  jnz     loc_18000AD25
0x18000aca0  call    ?Provider@TlgHelper@@SAPEBU_tlgProvider_t@@XZ; TlgHelper::Provider(void)
0x18000aca5  cmp     dword ptr [rax], 4
0x18000aca8  jbe     short loc_18000ACE8
0x18000acaa  test    byte ptr [rax+10h], 2
0x18000acae  jz      short loc_18000ACE8
0x18000acb0  mov     rcx, [rax+18h]
0x18000acb4  and     ecx, 2
0x18000acb7  cmp     rcx, [rax+18h]
0x18000acbb  jnz     short loc_18000ACE8
0x18000acbd  lea     rcx, aDoworkProcessi; "DoWork_ProcessingUserChoiceLearnMore"
0x18000acc4  mov     [rsp+78h+arg_8], rcx
0x18000accc  lea     rcx, [rsp+78h+arg_8]
0x18000acd4  mov     qword ptr [rsp+78h+var_58], rcx
0x18000acd9  lea     rdx, byte_18002AB01
0x18000ace0  mov     rcx, rax
0x18000ace3  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18000ace8  lea     rax, aWindirSystem32; "\"%windir%\\System32\\mdsched.exe\" /qm"
0x18000acef  mov     qword ptr [rsp+78h+var_38], rax
0x18000acf4  mov     qword ptr [rsp+78h+var_38+8], 23h ; '#'
0x18000acfd  movaps  xmm0, [rsp+78h+var_38]
0x18000ad02  movdqa  [rsp+78h+var_38], xmm0
0x18000ad08  lea     rcx, [rsp+78h+var_38]
0x18000ad0d  call    ?StartChildProcess@OS@Utils@@YAJV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; Utils::OS::StartChildProcess(std::basic_string_view<ushort>)
  ... truncated ...
```
