# PpfScheduledTask::EnableTemporarily(void)

- ea: `0x18003c280`
- end: `0x18003c526`
- name: `?EnableTemporarily@PpfScheduledTask@@QEAAJXZ`
- size: `678`
- prototype: `__int64 __fastcall(PpfScheduledTask *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x18000fec8`

## callees

- `0x180009c64`
- `0x18000b5c8`
- `0x18002d5ec`
- `0x18003c280`
- `0x18003c52c`
- `0x18003fb34`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18003c3ed`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18003c47a`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18003c4d7`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18003c3ed`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18003c47a`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18003c4d7`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18003c381`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18003c381`

## string_xrefs

- `0x18003c2e8`: `onecore\base\ngscb\pcrpf\helperlib\task.cpp`
- `0x18003c370`: `onecore\base\ngscb\pcrpf\helperlib\task.cpp`
- `0x18003c3b7`: `onecore\base\ngscb\pcrpf\helperlib\task.cpp`
- `0x18003c444`: `onecore\base\ngscb\pcrpf\helperlib\task.cpp`
- `0x18003c514`: `onecore\base\ngscb\pcrpf\helperlib\task.cpp`
- `0x18003c28f`: `PpfScheduledTask::EnableTemporarily`
- `0x18003c361`: `Enabling PPF scheduled task %ws temporarily`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall PpfScheduledTask::EnableTemporarily(PpfScheduledTask *this)
{
  const char *v2; // r9
  int v3; // eax
  unsigned int v4; // ebx
  int v6; // ebx
  int Task; // eax
  unsigned int v8; // esi
  struct IRegisteredTask *v9; // rcx
  int v10; // eax
  struct IRegisteredTask *v11; // rcx
  struct IRegisteredTask *v12; // rcx
  int v13; // [rsp+20h] [rbp-38h]
  int v14[2]; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  struct IRegisteredTask *v16; // [rsp+68h] [rbp+10h] BYREF
  const char *v17; // [rsp+70h] [rbp+18h]

  v17 = "PpfScheduledTask::EnableTemporarily";
  PpfTraceLogFormat(
    "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
    0x84u,
    "PpfTraceFunctionEntryExit::PpfTraceFunctionEntryExit",
    "Entering %hs",
    "PpfScheduledTask::EnableTemporarily");
  if ( *((_BYTE *)this + 3) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xC3,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\task.cpp",
      v2);
  v3 = PpfScheduledTask::Initialize(this);
  v4 = v3;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC5,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\task.cpp",
      (const char *)(unsigned int)v3,
      v13);
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
      0x89u,
      "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
      "Leaving %hs",
      "PpfScheduledTask::EnableTemporarily");
    return v4;
  }
  if ( !*((_BYTE *)this + 1) && !*((_BYTE *)this + 2) )
  {
    *(_QWORD *)v14 = *((_QWORD *)this + 1);
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\helperlib\\task.cpp",
      0xCDu,
      "PpfScheduledTask::EnableTemporarily",
      "Enabling PPF scheduled task %ws temporarily");
    v6 = RoInitialize(1);
    v16 = 0;
    Task = PpfScheduledTask::GetTask((const unsigned __int16 **)this, &v16);
    v8 = Task;
    if ( Task < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD0,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\task.cpp",
        (const char *)(unsigned int)Task,
        v14[0]);
      v9 = v16;
      if ( v16 )
      {
        v16 = 0;
        ((void (__fastcall *)(struct IRegisteredTask *))v9->lpVtbl->Release)(v9);
      }
      if ( v6 >= 0 )
        RoUninitialize();
LABEL_11:
      PpfTraceLogFormat(
        "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
        0x89u,
        "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
        "Leaving %hs",
        "PpfScheduledTask::EnableTemporarily");
      return v8;
    }
    v10 = ((__int64 (__fastcall *)(struct IRegisteredTask *, __int64))v16->lpVtbl->put_Enabled)(v16, 0xFFFFFFFFLL);
    v8 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD1,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\task.cpp",
        (const char *)(unsigned int)v10,
        v14[0]);
      v11 = v16;
      if ( v16 )
      {
        v16 = 0;
        ((void (__fastcall *)(struct IRegisteredTask *))v11->lpVtbl->Release)(v11);
      }
      if ( v6 >= 0 )
        RoUninitialize();
      goto LABEL_11;
    }
    *((_WORD *)this + 1) = 257;
    v12 = v16;
    if ( v16 )
    {
      v16 = 0;
      ((void (__fastcall *)(struct IRegisteredTask *))v12->lpVtbl->Release)(v12);
    }
    if ( v6 >= 0 )
      RoUninitialize();
  }
  PpfTraceLogFormat(
    "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
    0x89u,
    "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
    "Leaving %hs",
    "PpfScheduledTask::EnableTemporarily");
  return 0;
}

```

## disassembly

```asm
0x18003c280  push    rbx
0x18003c282  push    rsi
0x18003c283  push    rdi
0x18003c284  push    r14
0x18003c286  push    r15
0x18003c288  sub     rsp, 30h
0x18003c28c  mov     rdi, rcx
0x18003c28f  lea     r14, aPpfscheduledta_6; "PpfScheduledTask::EnableTemporarily"
0x18003c296  mov     [rsp+58h+arg_10], r14
0x18003c29b  mov     qword ptr [rsp+58h+var_38], r14; int
0x18003c2a0  lea     r9, aEnteringHs; "Entering %hs"
0x18003c2a7  lea     r8, aPpftracefuncti; "PpfTraceFunctionEntryExit::PpfTraceFunc"...
0x18003c2ae  mov     edx, 84h; unsigned int
0x18003c2b3  lea     r15, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18003c2ba  mov     rcx, r15; char *
0x18003c2bd  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18003c2c2  nop
0x18003c2c3  mov     rcx, [rsp+58h]; this
0x18003c2c8  cmp     byte ptr [rdi+3], 0
0x18003c2cc  jnz     loc_18003C514
0x18003c2d2  mov     rcx, rdi; this
0x18003c2d5  call    ?Initialize@PpfScheduledTask@@QEAAJXZ; PpfScheduledTask::Initialize(void)
0x18003c2da  mov     ebx, eax
0x18003c2dc  test    eax, eax
0x18003c2de  jns     short loc_18003C322
0x18003c2e0  mov     rcx, [rsp+58h]; this
0x18003c2e5  mov     r9d, eax; char *
0x18003c2e8  lea     r8, aOnecoreBaseNgs_5; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18003c2ef  mov     edx, 0C5h; void *
0x18003c2f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c2f9  nop
0x18003c2fa  mov     qword ptr [rsp+58h+var_38], r14
0x18003c2ff  lea     r9, aLeavingHs; "Leaving %hs"
0x18003c306  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x18003c30d  mov     edx, 89h; unsigned int
0x18003c312  mov     rcx, r15; char *
0x18003c315  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18003c31a  nop
0x18003c31b  mov     eax, ebx
0x18003c31d  jmp     loc_18003C507
0x18003c322  cmp     byte ptr [rdi+1], 0
0x18003c326  jz      short loc_18003C34E
0x18003c328  mov     qword ptr [rsp+58h+var_38], r14
0x18003c32d  lea     r9, aLeavingHs; "Leaving %hs"
0x18003c334  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x18003c33b  mov     edx, 89h; unsigned int
0x18003c340  mov     rcx, r15; char *
0x18003c343  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18003c348  nop
0x18003c349  jmp     loc_18003C505
0x18003c34e  cmp     byte ptr [rdi+2], 0
0x18003c352  jnz     loc_18003C4E4
0x18003c358  mov     rax, [rdi+8]
0x18003c35c  mov     qword ptr [rsp+58h+var_38], rax; int
0x18003c361  lea     r9, aEnablingPpfSch; "Enabling PPF scheduled task %ws tempora"...
0x18003c368  mov     r8, r14; char *
0x18003c36b  mov     edx, 0CDh; unsigned int
0x18003c370  lea     rcx, aOnecoreBaseNgs_5; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18003c377  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18003c37c  mov     ecx, 1
0x18003c381  call    cs:__imp_RoInitialize
0x18003c388  nop     dword ptr [rax+rax+00h]
0x18003c38d  mov     ebx, eax
0x18003c38f  mov     [rsp+58h+arg_0], eax
0x18003c393  mov     [rsp+58h+arg_8], 0
0x18003c39c  lea     rdx, [rsp+58h+arg_8]; struct IRegisteredTask **
0x18003c3a1  mov     rcx, rdi; this
0x18003c3a4  call    ?GetTask@PpfScheduledTask@@AEAAJPEAPEAUIRegisteredTask@@@Z; PpfScheduledTask::GetTask(IRegisteredTask * *)
0x18003c3a9  mov     esi, eax
0x18003c3ab  test    eax, eax
0x18003c3ad  jns     short loc_18003C422
0x18003c3af  mov     rcx, [rsp+58h]; this
0x18003c3b4  mov     r9d, eax; char *
0x18003c3b7  lea     r8, aOnecoreBaseNgs_5; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18003c3be  mov     edx, 0D0h; void *
0x18003c3c3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c3c8  nop
0x18003c3c9  mov     rcx, [rsp+58h+arg_8]
0x18003c3ce  test    rcx, rcx
0x18003c3d1  jz      short loc_18003C3E9
0x18003c3d3  mov     [rsp+58h+arg_8], 0
0x18003c3dc  mov     rax, [rcx]
0x18003c3df  mov     rax, [rax+10h]
0x18003c3e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c3e8  nop
0x18003c3e9  test    ebx, ebx
0x18003c3eb  js      short loc_18003C3FA
0x18003c3ed  call    cs:__imp_RoUninitialize
0x18003c3f4  nop     dword ptr [rax+rax+00h]
0x18003c3f9  nop
0x18003c3fa  mov     qword ptr [rsp+58h+var_38], r14
0x18003c3ff  lea     r9, aLeavingHs; "Leaving %hs"
0x18003c406  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x18003c40d  mov     edx, 89h; unsigned int
0x18003c412  mov     rcx, r15; char *
0x18003c415  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18003c41a  nop
0x18003c41b  mov     eax, esi
0x18003c41d  jmp     loc_18003C507
0x18003c422  mov     rcx, [rsp+58h+arg_8]
0x18003c427  mov     rax, [rcx]
0x18003c42a  or      edx, 0FFFFFFFFh
0x18003c42d  mov     rax, [rax+58h]
0x18003c431  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c436  mov     esi, eax
0x18003c438  test    eax, eax
0x18003c43a  jns     short loc_18003C4AD
0x18003c43c  mov     rcx, [rsp+58h]; this
0x18003c441  mov     r9d, eax; char *
0x18003c444  lea     r8, aOnecoreBaseNgs_5; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18003c44b  mov     edx, 0D1h; void *
0x18003c450  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c455  nop
0x18003c456  mov     rcx, [rsp+58h+arg_8]
0x18003c45b  test    rcx, rcx
0x18003c45e  jz      short loc_18003C476
0x18003c460  mov     [rsp+58h+arg_8], 0
0x18003c469  mov     rax, [rcx]
0x18003c46c  mov     rax, [rax+10h]
0x18003c470  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c475  nop
0x18003c476  test    ebx, ebx
0x18003c478  js      short loc_18003C487
0x18003c47a  call    cs:__imp_RoUninitialize
0x18003c481  nop     dword ptr [rax+rax+00h]
0x18003c486  nop
0x18003c487  mov     qword ptr [rsp+58h+var_38], r14
0x18003c48c  lea     r9, aLeavingHs; "Leaving %hs"
0x18003c493  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x18003c49a  mov     edx, 89h; unsigned int
0x18003c49f  mov     rcx, r15; char *
0x18003c4a2  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18003c4a7  nop
0x18003c4a8  jmp     loc_18003C41B
0x18003c4ad  mov     word ptr [rdi+2], 101h
0x18003c4b3  mov     rcx, [rsp+58h+arg_8]
0x18003c4b8  test    rcx, rcx
0x18003c4bb  jz      short loc_18003C4D3
0x18003c4bd  mov     [rsp+58h+arg_8], 0
0x18003c4c6  mov     rax, [rcx]
0x18003c4c9  mov     rax, [rax+10h]
0x18003c4cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c4d2  nop
0x18003c4d3  test    ebx, ebx
0x18003c4d5  js      short loc_18003C4E4
0x18003c4d7  call    cs:__imp_RoUninitialize
0x18003c4de  nop     dword ptr [rax+rax+00h]
0x18003c4e3  nop
0x18003c4e4  mov     qword ptr [rsp+58h+var_38], r14
0x18003c4e9  lea     r9, aLeavingHs; "Leaving %hs"
0x18003c4f0  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x18003c4f7  mov     edx, 89h; unsigned int
0x18003c4fc  mov     rcx, r15; char *
0x18003c4ff  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18003c504  nop
0x18003c505  xor     eax, eax
0x18003c507  add     rsp, 30h
0x18003c50b  pop     r15
0x18003c50d  pop     r14
0x18003c50f  pop     rdi
0x18003c510  pop     rsi
0x18003c511  pop     rbx
0x18003c512  retn
0x18003c514  lea     r8, aOnecoreBaseNgs_5; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18003c51b  mov     edx, 0C3h; void *
0x18003c520  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
