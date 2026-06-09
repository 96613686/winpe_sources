# RealtimeProtection::DlpTelemetry::DlpTelemetryCacheInternal::Initialize(void)

- ea: `0x180163ce4`
- end: `0x180163e91`
- name: `?Initialize@DlpTelemetryCacheInternal@DlpTelemetry@RealtimeProtection@@QEAAJXZ`
- size: `429`
- prototype: `__int64 __fastcall(RealtimeProtection::DlpTelemetry::DlpTelemetryCacheInternal *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180163634`

## callees

- `0x180028a10`
- `0x1800809d0`
- `0x180104a60`
- `0x18010cb40`
- `0x180163ce4`

## import_xrefs

- `KERNEL32!DeleteTimerQueueTimer` at `0x180163e03`
- `KERNEL32!DeleteTimerQueueTimer` at `0x180163e21`
- `KERNEL32!DeleteTimerQueueTimer` at `0x180163e44`
- `KERNEL32!DeleteTimerQueueTimer` at `0x180163e68`
- `KERNEL32!DeleteTimerQueueTimer` at `0x180163e03`
- `KERNEL32!DeleteTimerQueueTimer` at `0x180163e21`
- `KERNEL32!DeleteTimerQueueTimer` at `0x180163e44`
- `KERNEL32!DeleteTimerQueueTimer` at `0x180163e68`

## pseudocode

```c
__int64 __fastcall RealtimeProtection::DlpTelemetry::DlpTelemetryCacheInternal::Initialize(
        RealtimeProtection::DlpTelemetry::DlpTelemetryCacheInternal *this)
{
  unsigned int Value; // eax
  int TimerQueueTimer; // eax
  unsigned int v4; // esi
  HANDLE v5; // rdx
  int v6; // eax
  void *v7; // rdx
  void *v9; // [rsp+28h] [rbp-28h]
  void *v10; // [rsp+28h] [rbp-28h]
  HANDLE v11; // [rsp+30h] [rbp-20h] BYREF
  HANDLE Timer; // [rsp+38h] [rbp-18h] BYREF

  Value = Dlp::FeatureControl::GetValue(198);
  LODWORD(v9) = 0;
  TimerQueueTimer = CommonUtil::UtilCreateTimerQueueTimer(
                      (CommonUtil *)&v11,
                      (void **)Value,
                      Value,
                      (unsigned int)RealtimeProtection::DlpTelemetry::DlpTelemetryCacheInternal::ReportTelemetryTimerCallback,
                      (void (*)(void *, unsigned __int8))this,
                      v9,
                      0);
  v4 = TimerQueueTimer;
  if ( TimerQueueTimer >= 0 )
  {
    LODWORD(v10) = 0;
    Timer = 0;
    v6 = CommonUtil::UtilCreateTimerQueueTimer(
           (CommonUtil *)&Timer,
           (void **)0x7530,
           0x7530u,
           (unsigned int)RealtimeProtection::DlpTelemetry::DlpTelemetryCacheInternal::ReportTelemetryLazyQueueTimerCallback,
           (void (*)(void *, unsigned __int8))this,
           v10,
           (unsigned int)v11);
    v4 = v6;
    if ( v6 >= 0 )
    {
      v7 = (void *)*((_QWORD *)this + 1);
      if ( v7 )
        DeleteTimerQueueTimer(0, v7, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
      v5 = 0;
      *((_QWORD *)this + 1) = v11;
      v11 = 0;
      if ( *((_QWORD *)this + 2) )
      {
        DeleteTimerQueueTimer(0, *((HANDLE *)this + 2), (HANDLE)0xFFFFFFFFFFFFFFFFLL);
        v5 = v11;
      }
      *((_QWORD *)this + 2) = Timer;
      Timer = 0;
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          WPP_0c4fd8f2dcfe300db428647fc0b3042c_Traceguids,
          (unsigned int)v6);
      if ( Timer )
        DeleteTimerQueueTimer(0, Timer, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
      v5 = v11;
    }
    if ( v5 )
      goto LABEL_20;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        WPP_0c4fd8f2dcfe300db428647fc0b3042c_Traceguids,
        (unsigned int)TimerQueueTimer);
    v5 = v11;
    if ( v11 )
LABEL_20:
      DeleteTimerQueueTimer(0, v5, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  }
  return v4;
}

```

## disassembly

```asm
0x180163ce4  mov     [rsp-8+arg_8], rbx
0x180163ce9  mov     [rsp-8+arg_10], rsi
0x180163cee  mov     [rsp-8+arg_18], rdi
0x180163cf3  push    rbp
0x180163cf4  mov     rbp, rsp
0x180163cf7  sub     rsp, 50h
0x180163cfb  mov     rax, cs:__security_cookie
0x180163d02  xor     rax, rsp
0x180163d05  mov     [rbp+var_10], rax
0x180163d09  mov     rdi, rcx
0x180163d0c  mov     ecx, 0C6h
0x180163d11  call    ?GetValue@FeatureControl@Dlp@@YAIW4FeatureControlEnum@@@Z; Dlp::FeatureControl::GetValue(FeatureControlEnum)
0x180163d16  lea     r9, ?ReportTelemetryTimerCallback@DlpTelemetryCacheInternal@DlpTelemetry@RealtimeProtection@@CAXPEAXE@Z; unsigned int
0x180163d1d  mov     dword ptr [rsp+50h+var_28], 0; void *
0x180163d25  mov     r8d, eax; unsigned int
0x180163d28  mov     [rbp+var_20], 0
0x180163d30  mov     edx, eax; void **
0x180163d32  mov     [rsp+50h+var_30], rdi; void (*)(void *, unsigned __int8)
0x180163d37  lea     rcx, [rbp+var_20]; this
0x180163d3b  call    ?UtilCreateTimerQueueTimer@CommonUtil@@YAJPEAPEAXKKP6AXPEAXE@Z1K@Z; CommonUtil::UtilCreateTimerQueueTimer(void * *,ulong,ulong,void (*)(void *,uchar),void *,ulong)
0x180163d40  mov     esi, eax
0x180163d42  test    eax, eax
0x180163d44  jns     short loc_180163D8D
0x180163d46  mov     rcx, cs:WPP_GLOBAL_Control
0x180163d4d  lea     rdx, WPP_GLOBAL_Control
0x180163d54  cmp     rcx, rdx
0x180163d57  jz      short loc_180163D77
0x180163d59  test    byte ptr [rcx+1Ch], 1
0x180163d5d  jz      short loc_180163D77
0x180163d5f  mov     rcx, [rcx+10h]
0x180163d63  lea     r8, WPP_0c4fd8f2dcfe300db428647fc0b3042c_Traceguids
0x180163d6a  mov     edx, 0Ch
0x180163d6f  mov     r9d, eax
0x180163d72  call    WPP_SF_d
0x180163d77  mov     rdx, [rbp+var_20]
0x180163d7b  test    rdx, rdx
0x180163d7e  jz      loc_180163E6E
0x180163d84  or      r8, 0FFFFFFFFFFFFFFFFh
0x180163d88  jmp     loc_180163E66
0x180163d8d  mov     edx, 7530h; void **
0x180163d92  mov     dword ptr [rsp+50h+var_28], 0; void *
0x180163d9a  mov     r8d, edx; unsigned int
0x180163d9d  mov     [rbp+Timer], 0
0x180163da5  lea     r9, ?ReportTelemetryLazyQueueTimerCallback@DlpTelemetryCacheInternal@DlpTelemetry@RealtimeProtection@@CAXPEAXE@Z; unsigned int
0x180163dac  mov     [rsp+50h+var_30], rdi; void (*)(void *, unsigned __int8)
0x180163db1  lea     rcx, [rbp+Timer]; this
0x180163db5  call    ?UtilCreateTimerQueueTimer@CommonUtil@@YAJPEAPEAXKKP6AXPEAXE@Z1K@Z; CommonUtil::UtilCreateTimerQueueTimer(void * *,ulong,ulong,void (*)(void *,uchar),void *,ulong)
0x180163dba  mov     esi, eax
0x180163dbc  test    eax, eax
0x180163dbe  jns     short loc_180163E0F
0x180163dc0  mov     rcx, cs:WPP_GLOBAL_Control
0x180163dc7  lea     rdx, WPP_GLOBAL_Control
0x180163dce  cmp     rcx, rdx
0x180163dd1  jz      short loc_180163DF1
0x180163dd3  test    byte ptr [rcx+1Ch], 1
0x180163dd7  jz      short loc_180163DF1
0x180163dd9  mov     rcx, [rcx+10h]
0x180163ddd  lea     r8, WPP_0c4fd8f2dcfe300db428647fc0b3042c_Traceguids
0x180163de4  mov     edx, 0Dh
0x180163de9  mov     r9d, eax
0x180163dec  call    WPP_SF_d
0x180163df1  mov     rdx, [rbp+Timer]; Timer
0x180163df5  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180163df9  test    rdx, rdx
0x180163dfc  jz      short loc_180163E09
0x180163dfe  mov     r8, rbx; CompletionEvent
0x180163e01  xor     ecx, ecx; TimerQueue
0x180163e03  call    cs:__imp_DeleteTimerQueueTimer
0x180163e09  mov     rdx, [rbp+var_20]
0x180163e0d  jmp     short loc_180163E5E
0x180163e0f  mov     rdx, [rdi+8]; Timer
0x180163e13  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180163e17  test    rdx, rdx
0x180163e1a  jz      short loc_180163E27
0x180163e1c  mov     r8, rbx; CompletionEvent
0x180163e1f  xor     ecx, ecx; TimerQueue
0x180163e21  call    cs:__imp_DeleteTimerQueueTimer
0x180163e27  mov     rax, [rbp+var_20]
0x180163e2b  xor     edx, edx
0x180163e2d  mov     [rdi+8], rax
0x180163e31  mov     [rbp+var_20], rdx
0x180163e35  cmp     [rdi+10h], rdx
0x180163e39  jz      short loc_180163E4E
0x180163e3b  mov     rdx, [rdi+10h]; Timer
0x180163e3f  mov     r8, rbx; CompletionEvent
0x180163e42  xor     ecx, ecx; TimerQueue
0x180163e44  call    cs:__imp_DeleteTimerQueueTimer
0x180163e4a  mov     rdx, [rbp+var_20]; Timer
0x180163e4e  mov     rax, [rbp+Timer]
0x180163e52  mov     [rdi+10h], rax
0x180163e56  mov     [rbp+Timer], 0
0x180163e5e  test    rdx, rdx
0x180163e61  jz      short loc_180163E6E
0x180163e63  mov     r8, rbx; CompletionEvent
0x180163e66  xor     ecx, ecx; TimerQueue
0x180163e68  call    cs:__imp_DeleteTimerQueueTimer
0x180163e6e  mov     eax, esi
0x180163e70  mov     rcx, [rbp+var_10]
0x180163e74  xor     rcx, rsp; StackCookie
0x180163e77  call    __security_check_cookie
0x180163e7c  mov     rbx, [rsp+50h+arg_8]
0x180163e81  mov     rsi, [rsp+50h+arg_10]
0x180163e86  mov     rdi, [rsp+50h+arg_18]
0x180163e8b  add     rsp, 50h
0x180163e8f  pop     rbp
0x180163e90  retn
```
