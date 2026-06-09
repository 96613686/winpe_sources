# PpfScheduledTask::~PpfScheduledTask(void)

- ea: `0x18003beec`
- end: `0x18003bf5e`
- name: `??1PpfScheduledTask@@QEAA@XZ`
- size: `114`
- prototype: `void __fastcall(PpfScheduledTask *__hidden this)`
- caller_count: `6`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18000f5dc`
- `0x180052134`
- `0x180053280`
- `0x18005766a`
- `0x180058921`
- `0x1800589e7`

## callees

- `0x18002d5ec`
- `0x18003c02c`

## string_xrefs

- `0x18003bef9`: `PpfScheduledTask::~PpfScheduledTask`

## pseudocode

```c
void __fastcall PpfScheduledTask::~PpfScheduledTask(PpfScheduledTask *this)
{
  PpfTraceLogFormat(
    "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
    0x84u,
    "PpfTraceFunctionEntryExit::PpfTraceFunctionEntryExit",
    "Entering %hs",
    "PpfScheduledTask::~PpfScheduledTask");
  PpfScheduledTask::DisableIfEnabledTemporarily(this);
  PpfTraceLogFormat(
    "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
    0x89u,
    "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
    "Leaving %hs",
    "PpfScheduledTask::~PpfScheduledTask");
}

```

## disassembly

```asm
0x18003beec  mov     [rsp+arg_0], rbx
0x18003bef1  push    rdi
0x18003bef2  sub     rsp, 30h
0x18003bef6  mov     rbx, rcx
0x18003bef9  lea     rdi, aPpfscheduledta_5; "PpfScheduledTask::~PpfScheduledTask"
0x18003bf00  mov     [rsp+38h+var_18], rdi
0x18003bf05  lea     r9, aEnteringHs; "Entering %hs"
0x18003bf0c  lea     r8, aPpftracefuncti; "PpfTraceFunctionEntryExit::PpfTraceFunc"...
0x18003bf13  mov     edx, 84h; unsigned int
0x18003bf18  lea     rcx, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18003bf1f  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18003bf24  mov     rcx, rbx; this
0x18003bf27  call    ?DisableIfEnabledTemporarily@PpfScheduledTask@@QEAAJXZ; PpfScheduledTask::DisableIfEnabledTemporarily(void)
0x18003bf2c  nop
0x18003bf2d  mov     [rsp+38h+var_18], rdi
0x18003bf32  lea     r9, aLeavingHs; "Leaving %hs"
0x18003bf39  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x18003bf40  mov     edx, 89h; unsigned int
0x18003bf45  lea     rcx, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18003bf4c  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18003bf51  nop
0x18003bf52  mov     rbx, [rsp+38h+arg_0]
0x18003bf57  add     rsp, 30h
0x18003bf5b  pop     rdi
0x18003bf5c  retn
```
