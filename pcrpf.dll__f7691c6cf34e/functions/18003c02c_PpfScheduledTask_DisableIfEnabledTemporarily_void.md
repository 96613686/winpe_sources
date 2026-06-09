# PpfScheduledTask::DisableIfEnabledTemporarily(void)

- ea: `0x18003c02c`
- end: `0x18003c277`
- name: `?DisableIfEnabledTemporarily@PpfScheduledTask@@QEAAJXZ`
- size: `587`
- prototype: `__int64 __fastcall(PpfScheduledTask *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18000fec8`
- `0x18003beec`

## callees

- `0x180009c64`
- `0x18000b5c8`
- `0x18002d5ec`
- `0x18003c02c`
- `0x18003c52c`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18003c13f`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18003c1cb`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18003c228`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18003c13f`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18003c1cb`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18003c228`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18003c0d3`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18003c0d3`

## string_xrefs

- `0x18003c0c2`: `onecore\base\ngscb\pcrpf\helperlib\task.cpp`
- `0x18003c109`: `onecore\base\ngscb\pcrpf\helperlib\task.cpp`
- `0x18003c195`: `onecore\base\ngscb\pcrpf\helperlib\task.cpp`
- `0x18003c265`: `onecore\base\ngscb\pcrpf\helperlib\task.cpp`
- `0x18003c03b`: `PpfScheduledTask::DisableIfEnabledTemporarily`
- `0x18003c0b3`: `Disabling PPF scheduled task %ws since it was temporarily enabled`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall PpfScheduledTask::DisableIfEnabledTemporarily(PpfScheduledTask *this)
{
  const char *v2; // r9
  int v3; // ebx
  int Task; // eax
  unsigned int v5; // esi
  struct IRegisteredTask *v6; // rcx
  int v8; // eax
  struct IRegisteredTask *v9; // rcx
  struct IRegisteredTask *v10; // rcx
  int v11[2]; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  struct IRegisteredTask *v13; // [rsp+68h] [rbp+10h] BYREF
  const char *v14; // [rsp+70h] [rbp+18h]

  v14 = "PpfScheduledTask::DisableIfEnabledTemporarily";
  PpfTraceLogFormat(
    "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
    0x84u,
    "PpfTraceFunctionEntryExit::PpfTraceFunctionEntryExit",
    "Entering %hs",
    "PpfScheduledTask::DisableIfEnabledTemporarily");
  if ( *((_BYTE *)this + 3) )
  {
    if ( !*((_BYTE *)this + 2) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xE2,
        (int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\task.cpp",
        v2);
    *(_QWORD *)v11 = *((_QWORD *)this + 1);
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\helperlib\\task.cpp",
      0xE4u,
      "PpfScheduledTask::DisableIfEnabledTemporarily",
      "Disabling PPF scheduled task %ws since it was temporarily enabled");
    v3 = RoInitialize(1);
    v13 = 0;
    Task = PpfScheduledTask::GetTask((const unsigned __int16 **)this, &v13);
    v5 = Task;
    if ( Task < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE7,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\task.cpp",
        (const char *)(unsigned int)Task,
        v11[0]);
      v6 = v13;
      if ( v13 )
      {
        v13 = 0;
        ((void (__fastcall *)(struct IRegisteredTask *))v6->lpVtbl->Release)(v6);
      }
      if ( v3 >= 0 )
        RoUninitialize();
LABEL_8:
      PpfTraceLogFormat(
        "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
        0x89u,
        "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
        "Leaving %hs",
        "PpfScheduledTask::DisableIfEnabledTemporarily");
      return v5;
    }
    v8 = ((__int64 (__fastcall *)(struct IRegisteredTask *, _QWORD))v13->lpVtbl->put_Enabled)(v13, 0);
    v5 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE8,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\task.cpp",
        (const char *)(unsigned int)v8,
        v11[0]);
      v9 = v13;
      if ( v13 )
      {
        v13 = 0;
        ((void (__fastcall *)(struct IRegisteredTask *))v9->lpVtbl->Release)(v9);
      }
      if ( v3 >= 0 )
        RoUninitialize();
      goto LABEL_8;
    }
    *((_WORD *)this + 1) = 256;
    v10 = v13;
    if ( v13 )
    {
      v13 = 0;
      ((void (__fastcall *)(struct IRegisteredTask *))v10->lpVtbl->Release)(v10);
    }
    if ( v3 >= 0 )
      RoUninitialize();
  }
  PpfTraceLogFormat(
    "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
    0x89u,
    "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
    "Leaving %hs",
    "PpfScheduledTask::DisableIfEnabledTemporarily");
  return 0;
}

```

## disassembly

```asm
0x18003c02c  push    rbx
0x18003c02e  push    rsi
0x18003c02f  push    rdi
0x18003c030  push    r14
0x18003c032  push    r15
0x18003c034  sub     rsp, 30h
0x18003c038  mov     rdi, rcx
0x18003c03b  lea     r14, aPpfscheduledta_7; "PpfScheduledTask::DisableIfEnabledTempo"...
0x18003c042  mov     [rsp+58h+arg_10], r14
0x18003c047  mov     qword ptr [rsp+58h+var_38], r14
0x18003c04c  lea     r9, aEnteringHs; "Entering %hs"
0x18003c053  lea     r8, aPpftracefuncti; "PpfTraceFunctionEntryExit::PpfTraceFunc"...
0x18003c05a  mov     edx, 84h; unsigned int
0x18003c05f  lea     r15, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18003c066  mov     rcx, r15; char *
0x18003c069  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18003c06e  nop
0x18003c06f  cmp     byte ptr [rdi+3], 0
0x18003c073  jnz     short loc_18003C09B
0x18003c075  mov     qword ptr [rsp+58h+var_38], r14
0x18003c07a  lea     r9, aLeavingHs; "Leaving %hs"
0x18003c081  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x18003c088  mov     edx, 89h; unsigned int
0x18003c08d  mov     rcx, r15; char *
0x18003c090  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18003c095  nop
0x18003c096  jmp     loc_18003C256
0x18003c09b  mov     rcx, [rsp+58h]; this
0x18003c0a0  cmp     byte ptr [rdi+2], 0
0x18003c0a4  jz      loc_18003C265
0x18003c0aa  mov     rax, [rdi+8]
0x18003c0ae  mov     qword ptr [rsp+58h+var_38], rax; int
0x18003c0b3  lea     r9, aDisablingPpfSc; "Disabling PPF scheduled task %ws since "...
0x18003c0ba  mov     r8, r14; char *
0x18003c0bd  mov     edx, 0E4h; unsigned int
0x18003c0c2  lea     rcx, aOnecoreBaseNgs_5; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18003c0c9  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18003c0ce  mov     ecx, 1
0x18003c0d3  call    cs:__imp_RoInitialize
0x18003c0da  nop     dword ptr [rax+rax+00h]
0x18003c0df  mov     ebx, eax
0x18003c0e1  mov     [rsp+58h+arg_0], eax
0x18003c0e5  mov     [rsp+58h+arg_8], 0
0x18003c0ee  lea     rdx, [rsp+58h+arg_8]; struct IRegisteredTask **
0x18003c0f3  mov     rcx, rdi; this
0x18003c0f6  call    ?GetTask@PpfScheduledTask@@AEAAJPEAPEAUIRegisteredTask@@@Z; PpfScheduledTask::GetTask(IRegisteredTask * *)
0x18003c0fb  mov     esi, eax
0x18003c0fd  test    eax, eax
0x18003c0ff  jns     short loc_18003C174
0x18003c101  mov     rcx, [rsp+58h]; this
0x18003c106  mov     r9d, eax; char *
0x18003c109  lea     r8, aOnecoreBaseNgs_5; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18003c110  mov     edx, 0E7h; void *
0x18003c115  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c11a  nop
0x18003c11b  mov     rcx, [rsp+58h+arg_8]
0x18003c120  test    rcx, rcx
0x18003c123  jz      short loc_18003C13B
0x18003c125  mov     [rsp+58h+arg_8], 0
0x18003c12e  mov     rax, [rcx]
0x18003c131  mov     rax, [rax+10h]
0x18003c135  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c13a  nop
0x18003c13b  test    ebx, ebx
0x18003c13d  js      short loc_18003C14C
0x18003c13f  call    cs:__imp_RoUninitialize
0x18003c146  nop     dword ptr [rax+rax+00h]
0x18003c14b  nop
0x18003c14c  mov     qword ptr [rsp+58h+var_38], r14
0x18003c151  lea     r9, aLeavingHs; "Leaving %hs"
0x18003c158  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x18003c15f  mov     edx, 89h; unsigned int
0x18003c164  mov     rcx, r15; char *
0x18003c167  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18003c16c  nop
0x18003c16d  mov     eax, esi
0x18003c16f  jmp     loc_18003C258
0x18003c174  mov     rcx, [rsp+58h+arg_8]
0x18003c179  mov     rax, [rcx]
0x18003c17c  xor     edx, edx
0x18003c17e  mov     rax, [rax+58h]
0x18003c182  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c187  mov     esi, eax
0x18003c189  test    eax, eax
0x18003c18b  jns     short loc_18003C1FE
0x18003c18d  mov     rcx, [rsp+58h]; this
0x18003c192  mov     r9d, eax; char *
0x18003c195  lea     r8, aOnecoreBaseNgs_5; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18003c19c  mov     edx, 0E8h; void *
0x18003c1a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c1a6  nop
0x18003c1a7  mov     rcx, [rsp+58h+arg_8]
0x18003c1ac  test    rcx, rcx
0x18003c1af  jz      short loc_18003C1C7
0x18003c1b1  mov     [rsp+58h+arg_8], 0
0x18003c1ba  mov     rax, [rcx]
0x18003c1bd  mov     rax, [rax+10h]
0x18003c1c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c1c6  nop
0x18003c1c7  test    ebx, ebx
0x18003c1c9  js      short loc_18003C1D8
0x18003c1cb  call    cs:__imp_RoUninitialize
0x18003c1d2  nop     dword ptr [rax+rax+00h]
0x18003c1d7  nop
0x18003c1d8  mov     qword ptr [rsp+58h+var_38], r14
0x18003c1dd  lea     r9, aLeavingHs; "Leaving %hs"
0x18003c1e4  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x18003c1eb  mov     edx, 89h; unsigned int
0x18003c1f0  mov     rcx, r15; char *
0x18003c1f3  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18003c1f8  nop
0x18003c1f9  jmp     loc_18003C16D
0x18003c1fe  mov     word ptr [rdi+2], 100h
0x18003c204  mov     rcx, [rsp+58h+arg_8]
0x18003c209  test    rcx, rcx
0x18003c20c  jz      short loc_18003C224
0x18003c20e  mov     [rsp+58h+arg_8], 0
0x18003c217  mov     rax, [rcx]
0x18003c21a  mov     rax, [rax+10h]
0x18003c21e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c223  nop
0x18003c224  test    ebx, ebx
0x18003c226  js      short loc_18003C235
0x18003c228  call    cs:__imp_RoUninitialize
0x18003c22f  nop     dword ptr [rax+rax+00h]
0x18003c234  nop
0x18003c235  mov     qword ptr [rsp+58h+var_38], r14
0x18003c23a  lea     r9, aLeavingHs; "Leaving %hs"
0x18003c241  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x18003c248  mov     edx, 89h; unsigned int
0x18003c24d  mov     rcx, r15; char *
0x18003c250  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18003c255  nop
0x18003c256  xor     eax, eax
0x18003c258  add     rsp, 30h
0x18003c25c  pop     r15
0x18003c25e  pop     r14
0x18003c260  pop     rdi
0x18003c261  pop     rsi
0x18003c262  pop     rbx
0x18003c263  retn
0x18003c265  lea     r8, aOnecoreBaseNgs_5; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18003c26c  mov     edx, 0E2h; void *
0x18003c271  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
