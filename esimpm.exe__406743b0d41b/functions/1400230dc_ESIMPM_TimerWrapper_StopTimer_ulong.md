# ESIMPM::TimerWrapper::StopTimer(ulong)

- ea: `0x1400230dc`
- end: `0x14002314f`
- name: `?StopTimer@TimerWrapper@ESIMPM@@QEAAXK@Z`
- size: `115`
- prototype: `void __fastcall(ESIMPM::TimerWrapper *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14002d630`

## callees

- `0x140023158`
- `0x14003518c`
- `0x1400354f8`
- `0x140035994`

## string_xrefs

- `0x140023130`: ` Timer (%d) Stop Completed`

## pseudocode

```c
void __fastcall ESIMPM::TimerWrapper::StopTimer(
        ESIMPM::TimerWrapper *this,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  AcquireWriteLock(*((_QWORD *)this + 13), (__int64)this, (__int64)"ESIMPM::TimerWrapper::StopTimer", 85);
  StopTimer(*((_QWORD *)this + 13), "ESIMPM::TimerWrapper::StopTimer");
  ReleaseWriteLock(*((_QWORD *)this + 13), (__int64)this, (__int64)"ESIMPM::TimerWrapper::StopTimer", 87);
  ESIMPM::Log::Verbose("ESIMPM::TimerWrapper::StopTimer", 0, L" Timer (%d) Stop Completed", a2, a5);
}

```

## disassembly

```asm
0x1400230dc  mov     [rsp+arg_0], rbx
0x1400230e1  push    rdi
0x1400230e2  sub     rsp, 20h
0x1400230e6  mov     edi, edx
0x1400230e8  lea     r8, aEsimpmTimerwra_1; "ESIMPM::TimerWrapper::StopTimer"
0x1400230ef  mov     rdx, rcx
0x1400230f2  mov     rbx, rcx
0x1400230f5  mov     rcx, [rcx+68h]
0x1400230f9  mov     r9d, 55h ; 'U'
0x1400230ff  call    AcquireWriteLock
0x140023104  mov     rcx, [rbx+68h]
0x140023108  lea     rdx, aEsimpmTimerwra_1; "ESIMPM::TimerWrapper::StopTimer"
0x14002310f  call    StopTimer
0x140023114  mov     rcx, [rbx+68h]
0x140023118  lea     r8, aEsimpmTimerwra_1; "ESIMPM::TimerWrapper::StopTimer"
0x14002311f  mov     r9d, 57h ; 'W'
0x140023125  mov     rdx, rbx
0x140023128  call    ReleaseWriteLock
0x14002312d  mov     r9d, edi
0x140023130  lea     r8, aTimerDStopComp; " Timer (%d) Stop Completed"
0x140023137  xor     edx, edx; struct _GUID *
0x140023139  lea     rcx, aEsimpmTimerwra_1; "ESIMPM::TimerWrapper::StopTimer"
0x140023140  mov     rbx, [rsp+28h+arg_0]
0x140023145  add     rsp, 20h
0x140023149  pop     rdi
0x14002314a  jmp     ?Verbose@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Verbose(char const *,_GUID const *,ushort const *,...)
```
