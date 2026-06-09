# SystemSleepDiagnostics::ProcessUmpoSmartUserPresenceIntervalsRundownEvent(_EVENT_RECORD *)

- ea: `0x180089e44`
- end: `0x18008a059`
- name: `?ProcessUmpoSmartUserPresenceIntervalsRundownEvent@SystemSleepDiagnostics@@QEAAXPEAU_EVENT_RECORD@@@Z`
- size: `533`
- prototype: `void(SystemSleepDiagnostics *__hidden this, struct _EVENT_RECORD *)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180089afc`
- `0x18008a060`

## callees

- `0x180004e20`
- `0x180008740`
- `0x18000ae78`
- `0x180027bcc`
- `0x180027f10`
- `0x180030c38`
- `0x18004ca90`
- `0x18004d8fc`
- `0x18005eaa4`
- `0x180087668`
- `0x180087f84`
- `0x180089e44`

## import_xrefs

- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x180089f9b`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x180089f9b`

## string_xrefs

- `0x180089ea3`: `UserSid`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall SystemSleepDiagnostics::ProcessUmpoSmartUserPresenceIntervalsRundownEvent(
        SystemSleepDiagnostics *this,
        struct _EVENT_RECORD *a2)
{
  const unsigned __int16 *v4; // rdx
  unsigned int i; // ebx
  const unsigned __int16 *v6; // rdx
  unsigned int v7; // [rsp+40h] [rbp-69h] BYREF
  unsigned __int64 v8[2]; // [rsp+48h] [rbp-61h] BYREF
  BYTE pBuffer[8]; // [rsp+58h] [rbp-51h] BYREF
  _BYTE v10[68]; // [rsp+60h] [rbp-49h] BYREF
  unsigned int v11; // [rsp+A4h] [rbp-5h] BYREF
  __int64 v12; // [rsp+A8h] [rbp-1h] BYREF
  _OWORD *v13; // [rsp+B0h] [rbp+7h]
  _OWORD *v14; // [rsp+B8h] [rbp+Fh]
  PROPERTY_DATA_DESCRIPTOR pPropertyData; // [rsp+C0h] [rbp+17h] BYREF
  const wchar_t *v16; // [rsp+D0h] [rbp+27h]
  int v17; // [rsp+D8h] [rbp+2Fh]

  *(_OWORD *)v8 = 0;
  *(_QWORD *)pBuffer = 0;
  v7 = 0;
  memset_0(v10, 0, sizeof(v10));
  v11 = 0;
  std::vector<ServicePowerRequest>::vector<ServicePowerRequest>(&v12);
  if ( GetEventProperty(a2, L"UserSid", v10, 0x44u) || GetEventProperty(a2, L"Flags", &v11) )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  else if ( GetEventProperty(a2, L"IntervalCount", &v7) )
  {
LABEL_5:
    MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  else
  {
    for ( i = 0; i < v7; ++i )
    {
      if ( GetEventPropertyStructField(a2, v4, L"WeeklyStartOffsetInUs", i, v8) )
        goto LABEL_5;
      if ( GetEventPropertyStructField(a2, v6, L"WeeklyEndOffsetInUs", i, &v8[1]) )
        goto LABEL_5;
      pPropertyData.ArrayIndex = i;
      pPropertyData.PropertyName = (ULONGLONG)L"AwayIntervals";
      v17 = -1;
      v16 = L"Confidence";
      if ( TdhGetProperty(a2, 0, 0, 2u, &pPropertyData, 1u, pBuffer) )
        goto LABEL_5;
      v4 = (const unsigned __int16 *)v13;
      if ( v13 == v14 )
      {
        std::vector<UserPresencePredictionInterval>::_Emplace_reallocate<UserPresencePredictionInterval const &>(
          &v12,
          v13,
          v8);
      }
      else
      {
        *v13 = *(_OWORD *)v8;
        *((_QWORD *)v4 + 2) = *(_QWORD *)pBuffer;
        v13 = (_OWORD *)((char *)v13 + 24);
      }
      *(_OWORD *)v8 = 0;
      *(_QWORD *)pBuffer = 0;
    }
    if ( *((_QWORD *)this + 153) == *((_QWORD *)this + 154) )
    {
      std::vector<UserPresencePredictionIntervals>::_Emplace_reallocate<UserPresencePredictionIntervals const &>(
        (char *)this + 1216,
        *((_QWORD *)this + 153),
        v10);
    }
    else
    {
      UserPresencePredictionIntervals::UserPresencePredictionIntervals(
        *((UserPresencePredictionIntervals **)this + 153),
        (const struct UserPresencePredictionIntervals *)v10);
      *((_QWORD *)this + 153) += 96LL;
    }
  }
  std::vector<ImageMapping>::_Tidy(&v12);
}

```

## disassembly

```asm
0x180089e44  mov     [rsp-8+arg_10], rbx
0x180089e49  push    rbp
0x180089e4a  push    rsi
0x180089e4b  push    rdi
0x180089e4c  lea     rbp, [rsp-47h]
0x180089e51  sub     rsp, 0F0h
0x180089e58  mov     rax, cs:__security_cookie
0x180089e5f  xor     rax, rsp
0x180089e62  mov     [rbp+57h+var_20], rax
0x180089e66  mov     rdi, rdx
0x180089e69  mov     rsi, rcx
0x180089e6c  xorps   xmm0, xmm0
0x180089e6f  xor     eax, eax
0x180089e71  movups  xmmword ptr [rbp+57h+var_B8], xmm0
0x180089e75  mov     qword ptr [rbp+57h+var_A8], rax
0x180089e79  mov     [rbp+57h+var_C0], eax
0x180089e7c  lea     ebx, [rax+44h]
0x180089e7f  mov     r8d, ebx; Size
0x180089e82  xor     edx, edx; Val
0x180089e84  lea     rcx, [rbp+57h+var_A0]; void *
0x180089e88  call    memset_0
0x180089e8d  xor     eax, eax
0x180089e8f  mov     [rbp+57h+var_5C], eax
0x180089e92  lea     rcx, [rbp+57h+var_58]; void *
0x180089e96  call    ??0?$vector@VServicePowerRequest@@V?$allocator@VServicePowerRequest@@@std@@@std@@QEAA@XZ; std::vector<ServicePowerRequest>::vector<ServicePowerRequest>(void)
0x180089e9b  nop
0x180089e9c  mov     r9d, ebx; unsigned int
0x180089e9f  lea     r8, [rbp+57h+var_A0]; void *
0x180089ea3  lea     rdx, aUsersid; "UserSid"
0x180089eaa  mov     rcx, rdi; struct _EVENT_RECORD *
0x180089ead  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGPEAXK@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,void *,ulong)
0x180089eb2  test    eax, eax
0x180089eb4  jz      short loc_180089EC0
0x180089eb6  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180089ebb  jmp     loc_18008A031
0x180089ec0  lea     r8, [rbp+57h+var_5C]; unsigned int *
0x180089ec4  lea     rdx, aFlags; "Flags"
0x180089ecb  mov     rcx, rdi; struct _EVENT_RECORD *
0x180089ece  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGAEAK@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,ulong &)
0x180089ed3  test    eax, eax
0x180089ed5  jz      short loc_180089EE1
0x180089ed7  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180089edc  jmp     loc_18008A031
0x180089ee1  lea     r8, [rbp+57h+var_C0]; unsigned int *
0x180089ee5  lea     rdx, aIntervalcount; "IntervalCount"
0x180089eec  mov     rcx, rdi; struct _EVENT_RECORD *
0x180089eef  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGAEAK@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,ulong &)
0x180089ef4  test    eax, eax
0x180089ef6  jz      short loc_180089F02
0x180089ef8  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180089efd  jmp     loc_18008A031
0x180089f02  xor     ebx, ebx
0x180089f04  cmp     ebx, [rbp+57h+var_C0]
0x180089f07  jnb     loc_180089FFD
0x180089f0d  lea     rax, [rbp+57h+var_B8]
0x180089f11  mov     [rsp+100h+pPropertyData], rax; unsigned __int64 *
0x180089f16  mov     r9d, ebx; unsigned int
0x180089f19  lea     r8, aWeeklystartoff_0; "WeeklyStartOffsetInUs"
0x180089f20  mov     rcx, rdi; struct _EVENT_RECORD *
0x180089f23  call    ?GetEventPropertyStructField@@YAKPEAU_EVENT_RECORD@@PEBG1KAEA_K@Z; GetEventPropertyStructField(_EVENT_RECORD *,ushort const *,ushort const *,ulong,unsigned __int64 &)
0x180089f28  test    eax, eax
0x180089f2a  jnz     loc_180089FF6
0x180089f30  lea     rax, [rbp+57h+var_B8+8]
0x180089f34  mov     [rsp+100h+pPropertyData], rax; unsigned __int64 *
0x180089f39  mov     r9d, ebx; unsigned int
0x180089f3c  lea     r8, aWeeklyendoffse_1; "WeeklyEndOffsetInUs"
0x180089f43  mov     rcx, rdi; struct _EVENT_RECORD *
0x180089f46  call    ?GetEventPropertyStructField@@YAKPEAU_EVENT_RECORD@@PEBG1KAEA_K@Z; GetEventPropertyStructField(_EVENT_RECORD *,ushort const *,ushort const *,ulong,unsigned __int64 &)
0x180089f4b  test    eax, eax
0x180089f4d  jnz     loc_180089FEF
0x180089f53  mov     [rbp+57h+var_40.ArrayIndex], ebx
0x180089f56  lea     rax, aAwayintervals; "AwayIntervals"
0x180089f5d  mov     [rbp+57h+var_40.PropertyName], rax
0x180089f61  mov     [rbp+57h+var_28], 0FFFFFFFFh
0x180089f68  lea     rax, aConfidence; "Confidence"
0x180089f6f  mov     [rbp+57h+var_30], rax
0x180089f73  lea     rax, [rbp+57h+var_A8]
0x180089f77  mov     [rsp+100h+pBuffer], rax; pBuffer
0x180089f7c  mov     [rsp+100h+BufferSize], 1; BufferSize
0x180089f84  lea     rax, [rbp+57h+var_40]
0x180089f88  mov     [rsp+100h+pPropertyData], rax; pPropertyData
0x180089f8d  mov     r9d, 2; PropertyDataCount
0x180089f93  xor     r8d, r8d; pTdhContext
0x180089f96  xor     edx, edx; TdhContextCount
0x180089f98  mov     rcx, rdi; pEvent
0x180089f9b  call    cs:__imp_TdhGetProperty
0x180089fa1  test    eax, eax
0x180089fa3  jnz     short loc_180089FE8
0x180089fa5  mov     rdx, [rbp+57h+var_50]
0x180089fa9  cmp     rdx, [rbp+57h+var_48]
0x180089fad  jz      short loc_180089FC7
0x180089faf  movups  xmm0, xmmword ptr [rbp+57h+var_B8]
0x180089fb3  movups  xmmword ptr [rdx], xmm0
0x180089fb6  movsd   xmm1, qword ptr [rbp+57h+var_A8]
0x180089fbb  movsd   qword ptr [rdx+10h], xmm1
0x180089fc0  add     [rbp+57h+var_50], 18h
0x180089fc5  jmp     short loc_180089FD4
0x180089fc7  lea     r8, [rbp+57h+var_B8]
0x180089fcb  lea     rcx, [rbp+57h+var_58]
0x180089fcf  call    ??$_Emplace_reallocate@AEBUUserPresencePredictionInterval@@@?$vector@UUserPresencePredictionInterval@@V?$allocator@UUserPresencePredictionInterval@@@std@@@std@@AEAAPEAUUserPresencePredictionInterval@@QEAU2@AEBU2@@Z; std::vector<UserPresencePredictionInterval>::_Emplace_reallocate<UserPresencePredictionInterval const &>(UserPresencePredictionInterval * const,UserPresencePredictionInterval const &)
0x180089fd4  xorps   xmm0, xmm0
0x180089fd7  xor     eax, eax
0x180089fd9  movups  xmmword ptr [rbp+57h+var_B8], xmm0
0x180089fdd  mov     qword ptr [rbp+57h+var_A8], rax
0x180089fe1  inc     ebx
0x180089fe3  jmp     loc_180089F04
0x180089fe8  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180089fed  jmp     short loc_18008A031
0x180089fef  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180089ff4  jmp     short loc_18008A031
0x180089ff6  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180089ffb  jmp     short loc_18008A031
0x180089ffd  lea     rbx, [rsi+4C0h]
0x18008a004  mov     rax, [rbx+8]
0x18008a008  cmp     rax, [rbx+10h]
0x18008a00c  jz      short loc_18008A021
0x18008a00e  lea     rdx, [rbp+57h+var_A0]; struct UserPresencePredictionIntervals *
0x18008a012  mov     rcx, rax; this
0x18008a015  call    ??0UserPresencePredictionIntervals@@QEAA@AEBU0@@Z; UserPresencePredictionIntervals::UserPresencePredictionIntervals(UserPresencePredictionIntervals const &)
0x18008a01a  add     qword ptr [rbx+8], 60h ; '`'
0x18008a01f  jmp     short loc_18008A031
0x18008a021  lea     r8, [rbp+57h+var_A0]
0x18008a025  mov     rdx, rax
0x18008a028  mov     rcx, rbx
0x18008a02b  call    ??$_Emplace_reallocate@AEBUUserPresencePredictionIntervals@@@?$vector@UUserPresencePredictionIntervals@@V?$allocator@UUserPresencePredictionIntervals@@@std@@@std@@AEAAPEAUUserPresencePredictionIntervals@@QEAU2@AEBU2@@Z; std::vector<UserPresencePredictionIntervals>::_Emplace_reallocate<UserPresencePredictionIntervals const &>(UserPresencePredictionIntervals * const,UserPresencePredictionIntervals const &)
0x18008a030  nop
0x18008a031  lea     rcx, [rbp+57h+var_58]
0x18008a035  call    ?_Tidy@?$vector@VImageMapping@@V?$allocator@VImageMapping@@@std@@@std@@AEAAXXZ; std::vector<ImageMapping>::_Tidy(void)
0x18008a03a  mov     rcx, [rbp+57h+var_20]
0x18008a03e  xor     rcx, rsp; StackCookie
0x18008a041  call    __security_check_cookie
0x18008a046  mov     rbx, [rsp+100h+arg_10]
0x18008a04e  add     rsp, 0F0h
0x18008a055  pop     rdi
0x18008a056  pop     rsi
0x18008a057  pop     rbp
0x18008a058  retn
```
