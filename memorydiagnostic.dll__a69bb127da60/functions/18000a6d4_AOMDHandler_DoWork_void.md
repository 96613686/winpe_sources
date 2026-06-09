# AOMDHandler::DoWork(void)

- ea: `0x18000a6d4`
- end: `0x18000ac1a`
- name: `?DoWork@AOMDHandler@@AEAAJXZ`
- size: `1350`
- prototype: `__int64 __fastcall(AOMDHandler *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180015010`

## callees

- `0x180001008`
- `0x180007944`
- `0x1800094d4`
- `0x180009e94`
- `0x18000a6d4`
- `0x18000aed0`
- `0x18000d77c`
- `0x18000e7ec`
- `0x1800109d4`
- `0x1800115f8`
- `0x180011760`
- `0x18001488c`
- `0x180014a4c`
- `0x180015668`
- `0x18001f6ec`
- `0x1800200f8`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x18000a9f4`
- `KERNEL32!WaitForSingleObject` at `0x18000a9f4`

## string_xrefs

- `0x18000aaab`: `"%windir%\System32\mdsched.exe" /qd`
- `0x18000ab37`: `"%windir%\System32\mdsched.exe" /qm`
- `0x18000abbb`: `"%windir%\System32\mdsched.exe" /qm`

## pseudocode

```c
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
  const struct _tlgProvider_t *v29; // rax
  __int64 v30; // rdx
  int v31; // r8d
  int v32; // r9d
  int started; // eax
  unsigned int v34; // r8d
  wil::details::in1diag3 *v35; // rcx
  __int64 v36; // rdx
  const struct _tlgProvider_t *v37; // rax
  __int64 v38; // rdx
  int v39; // r8d
  int v40; // r9d
  const struct _tlgProvider_t *v41; // rax
  __int64 v42; // rdx
  int v43; // r8d
  int v44; // r9d
  int v45; // [rsp+20h] [rbp-38h]
  AOMDHandler *v46; // [rsp+30h] [rbp-28h] BYREF
  char v47; // [rsp+38h] [rbp-20h]
  const wchar_t *v48; // [rsp+40h] [rbp-18h] BYREF
  __int64 v49; // [rsp+48h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  const wchar_t *v51; // [rsp+68h] [rbp+10h] BYREF
  bool v52; // [rsp+70h] [rbp+18h] BYREF

  if ( !g_exitEvent )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x64A,
      (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
      (const char *)0x8000FFFFLL,
      v45);
    return 2147549183LL;
  }
  try
  {
    if ( AOMDHandler::ShouldExitEarly(this) )
    {
      v3 = TlgHelper::Provider();
      if ( *(_DWORD *)v3 > 4u && (*((_QWORD *)v3 + 2) & 2) != 0 && (*((_QWORD *)v3 + 3) & 2LL) == *((_QWORD *)v3 + 3) )
      {
        v51 = L"DoWork_ExitingEarly";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (_DWORD)v3,
          (unsigned int)qword_180029C70,
          v4,
          (_DWORD)v5,
          (__int64)&v51);
      }
      return 0;
    }
    AOMDHandler::InitializeConfig(this);
    LOBYTE(v51) = 0;
    v6 = AOMDHandler::CalcEffectiveLookbackTime(this, (bool *)&v51);
    v7 = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x656,
        (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
        (const char *)(unsigned int)v6,
        v45);
      return v7;
    }
    if ( (_BYTE)v51 )
      return 0;
    LOBYTE(v51) = 0;
    v8 = AOMDHandler::EventScanCriteriaMet(this, (bool *)&v51);
    v9 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x65C,
        (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
        (const char *)(unsigned int)v8,
        v45);
      return v9;
    }
    if ( !(_BYTE)v51 )
    {
      v10 = TlgHelper::Provider();
      if ( *(_DWORD *)v10 > 4u
        && (*((_QWORD *)v10 + 2) & 2) != 0
        && (*((_QWORD *)v10 + 3) & 2LL) == *((_QWORD *)v10 + 3) )
      {
        v51 = L"DoWork_ThresholdNotMetSkippingTest";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (_DWORD)v10,
          (unsigned int)word_18002A342,
          v11,
          (_DWORD)v5,
          (__int64)&v51);
      }
      return 0;
    }
    v52 = 0;
    v12 = BitLockerCompatibilityCheck(&v52);
    v13 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x664,
        (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
        (const char *)(unsigned int)v12,
        v45);
      return v13;
    }
    if ( !v52 )
    {
      v14 = TlgHelper::Provider();
      if ( *(_DWORD *)v14 > 4u
        && (*((_QWORD *)v14 + 2) & 2) != 0
        && (*((_QWORD *)v14 + 3) & 2LL) == *((_QWORD *)v14 + 3) )
      {
        v51 = L"DoWork_BitLockerCheckFailed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (_DWORD)v14,
          (unsigned int)qword_18002A260,
          v15,
          (_DWORD)v5,
          (__int64)&v51);
      }
      return 0;
    }
    v16 = TlgHelper::Provider();
    if ( *(_DWORD *)v16 > 4u && (*((_QWORD *)v16 + 2) & 2) != 0 && (*((_QWORD *)v16 + 3) & 2LL) == *((_QWORD *)v16 + 3) )
    {
      v51 = L"DoWork_RequestingUserInput";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (_DWORD)v16,
        (unsigned int)byte_180029A61,
        v17,
        v18,
        (__int64)&v51);
    }
    v46 = this;
    v47 = 1;
    updated = AOMDHandler::UpdateStatsOnThresholdMet(this);
    v20 = updated;
    if ( updated < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x673,
        (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
        (const char *)(unsigned int)updated,
        v45);
      wil::details::lambda_call__lambda_75ef670ad458ff9214a69029830e7dab___::_lambda_call__lambda_75ef670ad458ff9214a69029830e7dab___(&v46);
      return v20;
    }
    v21 = AOMDHandler::ShowToast(this);
    v22 = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x675,
        (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
        (const char *)(unsigned int)v21,
        v45);
      wil::details::lambda_call__lambda_75ef670ad458ff9214a69029830e7dab___::_lambda_call__lambda_75ef670ad458ff9214a69029830e7dab___(&v46);
      return v22;
    }
    v23 = TlgHelper::Provider();
    if ( *(_DWORD *)v23 > 4u && (*((_QWORD *)v23 + 2) & 1) != 0 && (*((_QWORD *)v23 + 3) & 1LL) == *((_QWORD *)v23 + 3) )
    {
      v51 = L"DoWork_WaitingForExitEventSignled";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (_DWORD)v23,
        (unsigned int)&dword_18002A17C,
        v24,
        v25,
        (__int64)&v51);
    }
    WaitForSingleObject(g_exitEvent, 0xFFFFFFFF);
    v26 = TlgHelper::Provider();
    if ( *(_DWORD *)v26 > 4u && (*((_QWORD *)v26 + 2) & 1) != 0 && (*((_QWORD *)v26 + 3) & 1LL) == *((_QWORD *)v26 + 3) )
    {
      v51 = L"DoWork_ExitEventSignled";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (_DWORD)v26,
        (unsigned int)&word_18002A35E,
        v27,
        v28,
        (__int64)&v51);
    }
    g_isTaskShuttingDown = 1;
    AOMDHandler::UnsubscribeFromToastEventCallbacks(this);
    if ( g_aomdPromptResult == 10 )
    {
      v29 = TlgHelper::Provider();
      if ( *(_DWORD *)v29 > 4u )
      {
        v30 = *((_QWORD *)v29 + 3);
        if ( (*((_QWORD *)v29 + 2) & 2) != 0 && (*((_QWORD *)v29 + 3) & 2LL) == v30 )
        {
          v51 = L"DoWork_ProcessingUserChoiceYes";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            (_DWORD)v29,
            (unsigned int)byte_18002A0DB,
            v31,
            v32,
            (__int64)&v51);
        }
      }
      v48 = L"\"%windir%\\System32\\mdsched.exe\" /qd";
      v49 = 35;
      started = Utils::OS::StartChildProcess(&v48, v30);
      v35 = retaddr;
      if ( started >= 0 )
        goto LABEL_69;
      v36 = 1667;
    }
    else if ( g_aomdPromptResult == 13 )
    {
      v37 = TlgHelper::Provider();
      if ( *(_DWORD *)v37 > 4u )
      {
        v38 = *((_QWORD *)v37 + 3);
        if ( (*((_QWORD *)v37 + 2) & 2) != 0 && (*((_QWORD *)v37 + 3) & 2LL) == v38 )
        {
          v51 = L"DoWork_ProcessingUserChoiceBodyClick";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            (_DWORD)v37,
            (unsigned int)word_180029ACA,
            v39,
            v40,
            (__int64)&v51);
        }
      }
      v48 = L"\"%windir%\\System32\\mdsched.exe\" /qm";
      v49 = 35;
      started = Utils::OS::StartChildProcess(&v48, v38);
      v35 = retaddr;
      if ( started >= 0 )
        goto LABEL_69;
      v36 = 1682;
    }
    else
    {
      if ( g_aomdPromptResult != 12 )
      {
        if ( !g_aomdPromptResult )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        goto LABEL_69;
      }
      v41 = TlgHelper::Provider();
      if ( *(_DWORD *)v41 > 4u )
      {
        v42 = *((_QWORD *)v41 + 3);
        if ( (*((_QWORD *)v41 + 2) & 2) != 0 && (*((_QWORD *)v41 + 3) & 2LL) == v42 )
        {
          v51 = L"DoWork_ProcessingUserChoiceLearnMore";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            (_DWORD)v41,
            (unsigned int)word_180029ACA,
            v43,
            v44,
            (__int64)&v51);
        }
      }
      v48 = L"\"%windir%\\System32\\mdsched.exe\" /qm";
      v49 = 35;
      started = Utils::OS::StartChildProcess(&v48, v42);
      v35 = retaddr;
      if ( started >= 0 )
      {
LABEL_69:
        wil::details::lambda_call__lambda_75ef670ad458ff9214a69029830e7dab___::_lambda_call__lambda_75ef670ad458ff9214a69029830e7dab___(&v46);
        return 0;
      }
      v36 = 1690;
    }
    wil::details::in1diag3::_Log_Hr(v35, (void *)v36, v34, (const char *)(unsigned int)started, v45);
    goto LABEL_69;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x6A1,
                           (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
                           v5);
  }
  return result;
}

```

## disassembly

```asm
0x18000a6d4  mov     [rsp+arg_0], rbx
0x18000a6d9  mov     [rsp+arg_18], rsi
0x18000a6de  push    rdi
0x18000a6df  sub     rsp, 50h
0x18000a6e3  mov     rbx, rcx
0x18000a6e6  cmp     cs:?g_exitEvent@@3V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@A, 0
0x18000a6ee  jnz     short loc_18000A715
0x18000a6f0  mov     rcx, [rsp+58h]; this
0x18000a6f5  mov     ebx, 8000FFFFh
0x18000a6fa  mov     r9d, ebx; char *
0x18000a6fd  lea     r8, aBaseDiagnosisM_1; "base\\diagnosis\\memdiag\\onlinemd\\aom"...
0x18000a704  mov     edx, 64Ah; void *
0x18000a709  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a70e  mov     eax, ebx
0x18000a710  jmp     loc_18000AC09
0x18000a715  call    ?ShouldExitEarly@AOMDHandler@@AEAA_NXZ; AOMDHandler::ShouldExitEarly(void)
0x18000a71a  test    al, al
0x18000a71c  jz      short loc_18000A76E
0x18000a71e  call    ?Provider@TlgHelper@@SAPEBU_tlgProvider_t@@XZ; TlgHelper::Provider(void)
0x18000a723  mov     ecx, [rax]
0x18000a725  cmp     ecx, 4
0x18000a728  jbe     short loc_18000A767
0x18000a72a  mov     rdx, [rax+18h]
0x18000a72e  mov     rcx, [rax+10h]
0x18000a732  test    cl, 2
0x18000a735  jz      short loc_18000A767
0x18000a737  mov     rcx, rdx
0x18000a73a  and     ecx, 2
0x18000a73d  cmp     rcx, rdx
0x18000a740  jnz     short loc_18000A767
0x18000a742  lea     rcx, aDoworkExitinge; "DoWork_ExitingEarly"
0x18000a749  mov     [rsp+58h+arg_8], rcx
0x18000a74e  lea     rcx, [rsp+58h+arg_8]
0x18000a753  mov     qword ptr [rsp+58h+var_38], rcx
0x18000a758  lea     rdx, qword_180029C70
0x18000a75f  mov     rcx, rax
0x18000a762  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18000a767  xor     eax, eax
0x18000a769  jmp     loc_18000AC09
0x18000a76e  mov     rcx, rbx; this
0x18000a771  call    ?InitializeConfig@AOMDHandler@@AEAAXXZ; AOMDHandler::InitializeConfig(void)
0x18000a776  mov     byte ptr [rsp+58h+arg_8], 0
0x18000a77b  lea     rdx, [rsp+58h+arg_8]; bool *
0x18000a780  mov     rcx, rbx; this
0x18000a783  call    ?CalcEffectiveLookbackTime@AOMDHandler@@AEAAJAEA_N@Z; AOMDHandler::CalcEffectiveLookbackTime(bool &)
0x18000a788  mov     edi, eax
0x18000a78a  test    eax, eax
0x18000a78c  jns     short loc_18000A7AE
0x18000a78e  mov     rcx, [rsp+58h]; this
0x18000a793  mov     r9d, eax; char *
0x18000a796  lea     r8, aBaseDiagnosisM_1; "base\\diagnosis\\memdiag\\onlinemd\\aom"...
0x18000a79d  mov     edx, 656h; void *
0x18000a7a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a7a7  mov     eax, edi
0x18000a7a9  jmp     loc_18000AC09
0x18000a7ae  cmp     byte ptr [rsp+58h+arg_8], 0
0x18000a7b3  jz      short loc_18000A7BC
0x18000a7b5  xor     eax, eax
0x18000a7b7  jmp     loc_18000AC09
0x18000a7bc  mov     byte ptr [rsp+58h+arg_8], 0
0x18000a7c1  lea     rdx, [rsp+58h+arg_8]; bool *
0x18000a7c6  mov     rcx, rbx; this
0x18000a7c9  call    ?EventScanCriteriaMet@AOMDHandler@@AEAAJAEA_N@Z; AOMDHandler::EventScanCriteriaMet(bool &)
0x18000a7ce  mov     edi, eax
0x18000a7d0  test    eax, eax
0x18000a7d2  jns     short loc_18000A7F4
0x18000a7d4  mov     rcx, [rsp+58h]; this
0x18000a7d9  mov     r9d, eax; char *
0x18000a7dc  lea     r8, aBaseDiagnosisM_1; "base\\diagnosis\\memdiag\\onlinemd\\aom"...
0x18000a7e3  mov     edx, 65Ch; void *
0x18000a7e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a7ed  mov     eax, edi
0x18000a7ef  jmp     loc_18000AC09
0x18000a7f4  cmp     byte ptr [rsp+58h+arg_8], 0
0x18000a7f9  jnz     short loc_18000A84B
0x18000a7fb  call    ?Provider@TlgHelper@@SAPEBU_tlgProvider_t@@XZ; TlgHelper::Provider(void)
0x18000a800  mov     ecx, [rax]
0x18000a802  cmp     ecx, 4
0x18000a805  jbe     short loc_18000A844
0x18000a807  mov     rdx, [rax+18h]
0x18000a80b  mov     rcx, [rax+10h]
0x18000a80f  test    cl, 2
0x18000a812  jz      short loc_18000A844
0x18000a814  mov     rcx, rdx
0x18000a817  and     ecx, 2
0x18000a81a  cmp     rcx, rdx
0x18000a81d  jnz     short loc_18000A844
0x18000a81f  lea     rcx, aDoworkThreshol; "DoWork_ThresholdNotMetSkippingTest"
0x18000a826  mov     [rsp+58h+arg_8], rcx
0x18000a82b  lea     rcx, [rsp+58h+arg_8]
0x18000a830  mov     qword ptr [rsp+58h+var_38], rcx
0x18000a835  lea     rdx, word_18002A342
0x18000a83c  mov     rcx, rax
0x18000a83f  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18000a844  xor     eax, eax
0x18000a846  jmp     loc_18000AC09
0x18000a84b  mov     [rsp+58h+arg_10], 0
0x18000a850  lea     rcx, [rsp+58h+arg_10]; bool *
0x18000a855  call    ?BitLockerCompatibilityCheck@@YAJAEA_N@Z; BitLockerCompatibilityCheck(bool &)
0x18000a85a  mov     edi, eax
0x18000a85c  test    eax, eax
0x18000a85e  jns     short loc_18000A880
0x18000a860  mov     rcx, [rsp+58h]; this
0x18000a865  mov     r9d, eax; char *
0x18000a868  lea     r8, aBaseDiagnosisM_1; "base\\diagnosis\\memdiag\\onlinemd\\aom"...
0x18000a86f  mov     edx, 664h; void *
0x18000a874  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a879  mov     eax, edi
0x18000a87b  jmp     loc_18000AC09
0x18000a880  cmp     [rsp+58h+arg_10], 0
0x18000a885  jnz     short loc_18000A8D7
0x18000a887  call    ?Provider@TlgHelper@@SAPEBU_tlgProvider_t@@XZ; TlgHelper::Provider(void)
0x18000a88c  mov     ecx, [rax]
0x18000a88e  cmp     ecx, 4
0x18000a891  jbe     short loc_18000A8D0
0x18000a893  mov     rdx, [rax+18h]
0x18000a897  mov     rcx, [rax+10h]
0x18000a89b  test    cl, 2
0x18000a89e  jz      short loc_18000A8D0
0x18000a8a0  mov     rcx, rdx
0x18000a8a3  and     ecx, 2
0x18000a8a6  cmp     rcx, rdx
0x18000a8a9  jnz     short loc_18000A8D0
0x18000a8ab  lea     rcx, aDoworkBitlocke; "DoWork_BitLockerCheckFailed"
0x18000a8b2  mov     [rsp+58h+arg_8], rcx
0x18000a8b7  lea     rcx, [rsp+58h+arg_8]
0x18000a8bc  mov     qword ptr [rsp+58h+var_38], rcx
0x18000a8c1  lea     rdx, qword_18002A260
0x18000a8c8  mov     rcx, rax
0x18000a8cb  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18000a8d0  xor     eax, eax
0x18000a8d2  jmp     loc_18000AC09
0x18000a8d7  call    ?Provider@TlgHelper@@SAPEBU_tlgProvider_t@@XZ; TlgHelper::Provider(void)
0x18000a8dc  mov     ecx, [rax]
0x18000a8de  cmp     ecx, 4
0x18000a8e1  jbe     short loc_18000A920
0x18000a8e3  mov     rdx, [rax+18h]
0x18000a8e7  mov     rcx, [rax+10h]
0x18000a8eb  test    cl, 2
0x18000a8ee  jz      short loc_18000A920
0x18000a8f0  mov     rcx, rdx
0x18000a8f3  and     ecx, 2
0x18000a8f6  cmp     rcx, rdx
0x18000a8f9  jnz     short loc_18000A920
0x18000a8fb  lea     rcx, aDoworkRequesti; "DoWork_RequestingUserInput"
0x18000a902  mov     [rsp+58h+arg_8], rcx
0x18000a907  lea     rcx, [rsp+58h+arg_8]
0x18000a90c  mov     qword ptr [rsp+58h+var_38], rcx; int
0x18000a911  lea     rdx, byte_180029A61
0x18000a918  mov     rcx, rax
0x18000a91b  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18000a920  mov     [rsp+58h+var_28], rbx
0x18000a925  mov     edi, 1
0x18000a92a  mov     [rsp+58h+var_20], dil
0x18000a92f  mov     rcx, rbx; this
0x18000a932  call    ?UpdateStatsOnThresholdMet@AOMDHandler@@AEAAJXZ; AOMDHandler::UpdateStatsOnThresholdMet(void)
0x18000a937  mov     esi, eax
0x18000a939  test    eax, eax
0x18000a93b  jns     short loc_18000A968
0x18000a93d  mov     rcx, [rsp+58h]; this
0x18000a942  mov     r9d, eax; char *
0x18000a945  lea     r8, aBaseDiagnosisM_1; "base\\diagnosis\\memdiag\\onlinemd\\aom"...
0x18000a94c  mov     edx, 673h; void *
0x18000a951  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a956  nop
0x18000a957  lea     rcx, [rsp+58h+var_28]
0x18000a95c  call    wil__details__lambda_call__lambda_75ef670ad458ff9214a69029830e7dab______lambda_call__lambda_75ef670ad458ff9214a69029830e7dab___
0x18000a961  mov     eax, esi
0x18000a963  jmp     loc_18000AC09
0x18000a968  mov     rcx, rbx; this
0x18000a96b  call    ?ShowToast@AOMDHandler@@AEAAJXZ; AOMDHandler::ShowToast(void)
0x18000a970  mov     esi, eax
0x18000a972  test    eax, eax
0x18000a974  jns     short loc_18000A9A1
0x18000a976  mov     rcx, [rsp+58h]; this
0x18000a97b  mov     r9d, eax; char *
0x18000a97e  lea     r8, aBaseDiagnosisM_1; "base\\diagnosis\\memdiag\\onlinemd\\aom"...
0x18000a985  mov     edx, 675h; void *
0x18000a98a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a98f  nop
0x18000a990  lea     rcx, [rsp+58h+var_28]
0x18000a995  call    wil__details__lambda_call__lambda_75ef670ad458ff9214a69029830e7dab______lambda_call__lambda_75ef670ad458ff9214a69029830e7dab___
0x18000a99a  mov     eax, esi
0x18000a99c  jmp     loc_18000AC09
0x18000a9a1  call    ?Provider@TlgHelper@@SAPEBU_tlgProvider_t@@XZ; TlgHelper::Provider(void)
0x18000a9a6  mov     ecx, [rax]
0x18000a9a8  cmp     ecx, 4
0x18000a9ab  jbe     short loc_18000A9EA
0x18000a9ad  mov     rdx, [rax+18h]
0x18000a9b1  mov     rcx, [rax+10h]
0x18000a9b5  test    dil, cl
0x18000a9b8  jz      short loc_18000A9EA
0x18000a9ba  mov     rcx, rdx
0x18000a9bd  and     rcx, rdi
0x18000a9c0  cmp     rcx, rdx
0x18000a9c3  jnz     short loc_18000A9EA
0x18000a9c5  lea     rcx, aDoworkWaitingf; "DoWork_WaitingForExitEventSignled"
0x18000a9cc  mov     [rsp+58h+arg_8], rcx
0x18000a9d1  lea     rcx, [rsp+58h+arg_8]
0x18000a9d6  mov     qword ptr [rsp+58h+var_38], rcx
0x18000a9db  lea     rdx, dword_18002A17C
0x18000a9e2  mov     rcx, rax
0x18000a9e5  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18000a9ea  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000a9ed  mov     rcx, cs:?g_exitEvent@@3V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@A; hHandle
0x18000a9f4  call    cs:__imp_WaitForSingleObject
0x18000a9fa  call    ?Provider@TlgHelper@@SAPEBU_tlgProvider_t@@XZ; TlgHelper::Provider(void)
0x18000a9ff  mov     ecx, [rax]
0x18000aa01  cmp     ecx, 4
0x18000aa04  jbe     short loc_18000AA43
0x18000aa06  mov     rdx, [rax+18h]
0x18000aa0a  mov     rcx, [rax+10h]
0x18000aa0e  test    dil, cl
0x18000aa11  jz      short loc_18000AA43
0x18000aa13  mov     rcx, rdx
0x18000aa16  and     rcx, rdi
0x18000aa19  cmp     rcx, rdx
0x18000aa1c  jnz     short loc_18000AA43
0x18000aa1e  lea     rcx, aDoworkExiteven; "DoWork_ExitEventSignled"
0x18000aa25  mov     [rsp+58h+arg_8], rcx
0x18000aa2a  lea     rcx, [rsp+58h+arg_8]
0x18000aa2f  mov     qword ptr [rsp+58h+var_38], rcx
0x18000aa34  lea     rdx, word_18002A35E
0x18000aa3b  mov     rcx, rax
0x18000aa3e  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18000aa43  xchg    dil, cs:?g_isTaskShuttingDown@@3U?$atomic@_N@std@@A; std::atomic<bool> g_isTaskShuttingDown
0x18000aa4a  mov     rcx, rbx; this
0x18000aa4d  call    ?UnsubscribeFromToastEventCallbacks@AOMDHandler@@AEAAXXZ; AOMDHandler::UnsubscribeFromToastEventCallbacks(void)
0x18000aa52  mov     eax, cs:?g_aomdPromptResult@@3U?$atomic@W4AOMDPromptResult@@@std@@A; std::atomic<AOMDPromptResult> g_aomdPromptResult
0x18000aa58  nop
0x18000aa59  cmp     eax, 0Ah
0x18000aa5c  jnz     loc_18000AAE9
0x18000aa62  call    ?Provider@TlgHelper@@SAPEBU_tlgProvider_t@@XZ; TlgHelper::Provider(void)
0x18000aa67  mov     ecx, [rax]
0x18000aa69  cmp     ecx, 4
0x18000aa6c  jbe     short loc_18000AAAB
0x18000aa6e  mov     rdx, [rax+18h]
0x18000aa72  mov     rcx, [rax+10h]
0x18000aa76  test    cl, 2
0x18000aa79  jz      short loc_18000AAAB
0x18000aa7b  mov     rcx, rdx
0x18000aa7e  and     ecx, 2
0x18000aa81  cmp     rcx, rdx
0x18000aa84  jnz     short loc_18000AAAB
0x18000aa86  lea     rcx, aDoworkProcessi_0; "DoWork_ProcessingUserChoiceYes"
0x18000aa8d  mov     [rsp+58h+arg_8], rcx
0x18000aa92  lea     rcx, [rsp+58h+arg_8]
0x18000aa97  mov     qword ptr [rsp+58h+var_38], rcx; int
0x18000aa9c  lea     rdx, byte_18002A0DB
0x18000aaa3  mov     rcx, rax
0x18000aaa6  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18000aaab  lea     rax, aWindirSystem32_0; "\"%windir%\\System32\\mdsched.exe\" /qd"
0x18000aab2  mov     [rsp+58h+var_18], rax
0x18000aab7  mov     [rsp+58h+var_10], 23h ; '#'
0x18000aac0  lea     rcx, [rsp+58h+var_18]
0x18000aac5  call    ?StartChildProcess@OS@Utils@@YAJV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; Utils::OS::StartChildProcess(std::basic_string_view<ushort>)
0x18000aaca  mov     rcx, [rsp+58h]; this
0x18000aacf  test    eax, eax
0x18000aad1  jns     loc_18000ABF7
0x18000aad7  mov     edx, 683h; void *
0x18000aadc  mov     r9d, eax; char *
0x18000aadf  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000aae4  jmp     loc_18000ABF7
0x18000aae9  cmp     eax, 0Dh
0x18000aaec  jnz     short loc_18000AB6D
0x18000aaee  call    ?Provider@TlgHelper@@SAPEBU_tlgProvider_t@@XZ; TlgHelper::Provider(void)
0x18000aaf3  mov     ecx, [rax]
0x18000aaf5  cmp     ecx, 4
0x18000aaf8  jbe     short loc_18000AB37
0x18000aafa  mov     rdx, [rax+18h]
0x18000aafe  mov     rcx, [rax+10h]
0x18000ab02  test    cl, 2
0x18000ab05  jz      short loc_18000AB37
0x18000ab07  mov     rcx, rdx
0x18000ab0a  and     ecx, 2
0x18000ab0d  cmp     rcx, rdx
0x18000ab10  jnz     short loc_18000AB37
0x18000ab12  lea     rcx, aDoworkProcessi_1; "DoWork_ProcessingUserChoiceBodyClick"
0x18000ab19  mov     [rsp+58h+arg_8], rcx
0x18000ab1e  lea     rcx, [rsp+58h+arg_8]
0x18000ab23  mov     qword ptr [rsp+58h+var_38], rcx
0x18000ab28  lea     rdx, word_180029ACA
0x18000ab2f  mov     rcx, rax
0x18000ab32  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18000ab37  lea     rax, aWindirSystem32; "\"%windir%\\System32\\mdsched.exe\" /qm"
0x18000ab3e  mov     [rsp+58h+var_18], rax
0x18000ab43  mov     [rsp+58h+var_10], 23h ; '#'
0x18000ab4c  lea     rcx, [rsp+58h+var_18]
0x18000ab51  call    ?StartChildProcess@OS@Utils@@YAJV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; Utils::OS::StartChildProcess(std::basic_string_view<ushort>)
0x18000ab56  mov     rcx, [rsp+58h]
0x18000ab5b  test    eax, eax
0x18000ab5d  jns     loc_18000ABF7
0x18000ab63  mov     edx, 692h
0x18000ab68  jmp     loc_18000AADC
0x18000ab6d  cmp     eax, 0Ch
0x18000ab70  jnz     short loc_18000ABED
0x18000ab72  call    ?Provider@TlgHelper@@SAPEBU_tlgProvider_t@@XZ; TlgHelper::Provider(void)
0x18000ab77  mov     ecx, [rax]
0x18000ab79  cmp     ecx, 4
0x18000ab7c  jbe     short loc_18000ABBB
  ... truncated ...
```
