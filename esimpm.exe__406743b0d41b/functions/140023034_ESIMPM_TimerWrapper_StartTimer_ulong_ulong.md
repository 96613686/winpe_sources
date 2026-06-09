# ESIMPM::TimerWrapper::StartTimer(ulong,ulong)

- ea: `0x140023034`
- end: `0x1400230d6`
- name: `?StartTimer@TimerWrapper@ESIMPM@@QEAAKKK@Z`
- size: `162`
- prototype: `unsigned int(ESIMPM::TimerWrapper *__hidden this, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14002cfb4`

## callees

- `0x140014f64`
- `0x140023034`
- `0x140023158`
- `0x140023530`
- `0x1400350e4`
- `0x14003518c`
- `0x1400354f8`

## string_xrefs

- `0x1400230a1`: ` Timer (ID = %d) Start Completed`

## pseudocode

```c
__int64 __fastcall ESIMPM::TimerWrapper::StartTimer(ESIMPM::TimerWrapper *this, unsigned int a2, int a3)
{
  unsigned int v6; // r9d
  unsigned int started; // ebx
  const char *v9; // [rsp+20h] [rbp-18h]
  __int64 v10; // [rsp+20h] [rbp-18h]

  AcquireWriteLock(*((_QWORD *)this + 13), (__int64)this, (__int64)"ESIMPM::TimerWrapper::StartTimer", 66);
  started = ESIMPM::WwanTimerStartTimer(*((ESIMPM **)this + 13), (void *)a2, (void *)(unsigned int)(1000 * a3), v6, v9);
  ReleaseWriteLock(*((_QWORD *)this + 13), (__int64)this, (__int64)"ESIMPM::TimerWrapper::StartTimer", 68);
  if ( started )
  {
    LODWORD(v10) = started;
    ESIMPM::Log::Error("ESIMPM::TimerWrapper::StartTimer", 0, L"Timer (ID = %d) Start failed [%d]", a2, v10);
    MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  else
  {
    ESIMPM::Log::Verbose("ESIMPM::TimerWrapper::StartTimer", 0, L" Timer (ID = %d) Start Completed", a2);
  }
  return started;
}

```

## disassembly

```asm
0x140023034  mov     [rsp+arg_0], rbx
0x140023039  mov     [rsp+arg_8], rsi
0x14002303e  push    rdi
0x14002303f  sub     rsp, 30h
0x140023043  mov     esi, edx
0x140023045  mov     ebx, r8d
0x140023048  mov     rdx, rcx
0x14002304b  lea     r8, aEsimpmTimerwra; "ESIMPM::TimerWrapper::StartTimer"
0x140023052  mov     rdi, rcx
0x140023055  mov     r9d, 42h ; 'B'
0x14002305b  mov     rcx, [rcx+68h]
0x14002305f  call    AcquireWriteLock
0x140023064  mov     rcx, [rdi+68h]; this
0x140023068  mov     edx, esi; void *
0x14002306a  imul    r8d, ebx, 3E8h; void *
0x140023071  call    ?WwanTimerStartTimer@ESIMPM@@YAKPEAX0KPEBD@Z; ESIMPM::WwanTimerStartTimer(void *,void *,ulong,char const *)
0x140023076  mov     rcx, [rdi+68h]
0x14002307a  lea     r8, aEsimpmTimerwra; "ESIMPM::TimerWrapper::StartTimer"
0x140023081  mov     r9d, 44h ; 'D'
0x140023087  mov     rdx, rdi
0x14002308a  mov     ebx, eax
0x14002308c  call    ReleaseWriteLock
0x140023091  xor     edx, edx; struct _GUID *
0x140023093  lea     rcx, aEsimpmTimerwra; "ESIMPM::TimerWrapper::StartTimer"
0x14002309a  mov     r9d, esi
0x14002309d  test    ebx, ebx
0x14002309f  jnz     short loc_1400230AF
0x1400230a1  lea     r8, aTimerIdDStartC; " Timer (ID = %d) Start Completed"
0x1400230a8  call    ?Verbose@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Verbose(char const *,_GUID const *,ushort const *,...)
0x1400230ad  jmp     short loc_1400230C4
0x1400230af  lea     r8, aTimerIdDStartF; "Timer (ID = %d) Start failed [%d]"
0x1400230b6  mov     [rsp+38h+var_18], ebx
0x1400230ba  call    ?Error@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Error(char const *,_GUID const *,ushort const *,...)
0x1400230bf  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1400230c4  mov     rsi, [rsp+38h+arg_8]
0x1400230c9  mov     eax, ebx
0x1400230cb  mov     rbx, [rsp+38h+arg_0]
0x1400230d0  add     rsp, 30h
0x1400230d4  pop     rdi
0x1400230d5  retn
```
