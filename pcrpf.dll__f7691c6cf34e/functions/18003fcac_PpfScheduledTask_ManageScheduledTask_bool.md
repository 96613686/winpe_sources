# PpfScheduledTask::ManageScheduledTask(bool)

- ea: `0x18003fcac`
- end: `0x18003ffff`
- name: `?ManageScheduledTask@PpfScheduledTask@@QEAAJ_N@Z`
- size: `851`
- prototype: `__int64 __fastcall(PpfScheduledTask *this, unsigned __int8)`
- caller_count: `3`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x18000fec8`
- `0x180052134`
- `0x180053280`

## callees

- `0x180009c64`
- `0x18000b5c8`
- `0x18002d5ec`
- `0x18003c52c`
- `0x18003fb34`
- `0x18003fcac`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18003fea4`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18003ff44`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18003ffa5`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18003fea4`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18003ff44`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18003ffa5`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18003fe29`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18003fe29`

## string_xrefs

- `0x18003fd11`: `onecore\base\ngscb\pcrpf\helperlib\task.cpp`
- `0x18003fe14`: `onecore\base\ngscb\pcrpf\helperlib\task.cpp`
- `0x18003fe68`: `onecore\base\ngscb\pcrpf\helperlib\task.cpp`
- `0x18003ff08`: `onecore\base\ngscb\pcrpf\helperlib\task.cpp`
- `0x18003ffed`: `onecore\base\ngscb\pcrpf\helperlib\task.cpp`
- `0x18003fcc9`: `PpfScheduledTask::ManageScheduledTask`
- `0x18003fe05`: `Setting PCRPF scheduled task %ws to %hs`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall PpfScheduledTask::ManageScheduledTask(PpfScheduledTask *this, unsigned __int8 a2)
{
  int v4; // eax
  const char *v5; // r9
  unsigned int v6; // ebx
  char v8; // al
  const char *v9; // rax
  int v10; // ebx
  int Task; // eax
  unsigned int v12; // ebp
  struct IRegisteredTask *v13; // rcx
  int v14; // eax
  struct IRegisteredTask *v15; // rcx
  struct IRegisteredTask *v16; // rcx
  int v17; // [rsp+20h] [rbp-48h]
  int v18; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  struct IRegisteredTask *v20; // [rsp+88h] [rbp+20h] BYREF

  PpfTraceLogFormat(
    "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
    0x84u,
    "PpfTraceFunctionEntryExit::PpfTraceFunctionEntryExit",
    "Entering %hs",
    "PpfScheduledTask::ManageScheduledTask");
  v4 = PpfScheduledTask::Initialize(this);
  v6 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9D,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\task.cpp",
      (const char *)(unsigned int)v4,
      v17);
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
      0x89u,
      "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
      "Leaving %hs",
      "PpfScheduledTask::ManageScheduledTask");
    return v6;
  }
  if ( !*((_BYTE *)this + 1) )
  {
    v8 = *((_BYTE *)this + 2);
    if ( *((_BYTE *)this + 3) )
    {
      if ( !v8 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xA6,
          (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\task.cpp",
          v5);
      *((_BYTE *)this + 3) = 0;
      PpfTraceLogFormat(
        "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
        0x89u,
        "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
        "Leaving %hs",
        "PpfScheduledTask::ManageScheduledTask");
      return 0;
    }
    if ( v8 != a2 )
    {
      v9 = "Enabled";
      if ( !a2 )
        v9 = "Disabled";
      PpfTraceLogFormat(
        "onecore\\base\\ngscb\\pcrpf\\helperlib\\task.cpp",
        0xB4u,
        "PpfScheduledTask::ManageScheduledTask",
        "Setting PCRPF scheduled task %ws to %hs",
        *((_QWORD *)this + 1),
        v9);
      v10 = RoInitialize(1);
      v20 = 0;
      Task = PpfScheduledTask::GetTask((const unsigned __int16 **)this, &v20);
      v12 = Task;
      if ( Task < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xB7,
          (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\task.cpp",
          (const char *)(unsigned int)Task,
          v18);
        v13 = v20;
        if ( v20 )
        {
          v20 = 0;
          ((void (__fastcall *)(struct IRegisteredTask *))v13->lpVtbl->Release)(v13);
        }
        if ( v10 >= 0 )
          RoUninitialize();
LABEL_16:
        PpfTraceLogFormat(
          "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
          0x89u,
          "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
          "Leaving %hs",
          "PpfScheduledTask::ManageScheduledTask");
        return v12;
      }
      v14 = ((__int64 (__fastcall *)(struct IRegisteredTask *, _QWORD))v20->lpVtbl->put_Enabled)(
              v20,
              (unsigned __int16)((a2 ^ 1) - 1));
      v12 = v14;
      if ( v14 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xB8,
          (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\task.cpp",
          (const char *)(unsigned int)v14,
          v18);
        v15 = v20;
        if ( v20 )
        {
          v20 = 0;
          ((void (__fastcall *)(struct IRegisteredTask *))v15->lpVtbl->Release)(v15);
        }
        if ( v10 >= 0 )
          RoUninitialize();
        goto LABEL_16;
      }
      *((_BYTE *)this + 2) = a2;
      v16 = v20;
      if ( v20 )
      {
        v20 = 0;
        ((void (__fastcall *)(struct IRegisteredTask *))v16->lpVtbl->Release)(v16);
      }
      if ( v10 >= 0 )
        RoUninitialize();
    }
  }
  PpfTraceLogFormat(
    "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
    0x89u,
    "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
    "Leaving %hs",
    "PpfScheduledTask::ManageScheduledTask");
  return 0;
}

```

## disassembly

```asm
0x18003fcac  mov     rax, rsp
0x18003fcaf  mov     [rax+8], rbx
0x18003fcb3  mov     [rax+10h], rbp
0x18003fcb7  push    rsi
0x18003fcb8  push    rdi
0x18003fcb9  push    r12
0x18003fcbb  push    r13
0x18003fcbd  push    r15
0x18003fcbf  sub     rsp, 40h
0x18003fcc3  mov     sil, dl
0x18003fcc6  mov     rdi, rcx
0x18003fcc9  lea     r15, aPpfscheduledta_3; "PpfScheduledTask::ManageScheduledTask"
0x18003fcd0  mov     [rax-38h], r15
0x18003fcd4  mov     [rax-48h], r15
0x18003fcd8  lea     r9, aEnteringHs; "Entering %hs"
0x18003fcdf  lea     r8, aPpftracefuncti; "PpfTraceFunctionEntryExit::PpfTraceFunc"...
0x18003fce6  mov     edx, 84h; unsigned int
0x18003fceb  lea     r12, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18003fcf2  mov     rcx, r12; char *
0x18003fcf5  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18003fcfa  nop
0x18003fcfb  mov     rcx, rdi; this
0x18003fcfe  call    ?Initialize@PpfScheduledTask@@QEAAJXZ; PpfScheduledTask::Initialize(void)
0x18003fd03  mov     ebx, eax
0x18003fd05  test    eax, eax
0x18003fd07  jns     short loc_18003FD4B
0x18003fd09  mov     rcx, [rsp+68h]; this
0x18003fd0e  mov     r9d, eax; char *
0x18003fd11  lea     r8, aOnecoreBaseNgs_5; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18003fd18  mov     edx, 9Dh; void *
0x18003fd1d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003fd22  nop
0x18003fd23  mov     qword ptr [rsp+68h+var_48], r15
0x18003fd28  lea     r9, aLeavingHs; "Leaving %hs"
0x18003fd2f  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x18003fd36  mov     edx, 89h; unsigned int
0x18003fd3b  mov     rcx, r12; char *
0x18003fd3e  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18003fd43  nop
0x18003fd44  mov     eax, ebx
0x18003fd46  jmp     loc_18003FFD5
0x18003fd4b  cmp     byte ptr [rdi+1], 0
0x18003fd4f  jz      short loc_18003FD77
0x18003fd51  mov     qword ptr [rsp+68h+var_48], r15
0x18003fd56  lea     r9, aLeavingHs; "Leaving %hs"
0x18003fd5d  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x18003fd64  mov     edx, 89h; unsigned int
0x18003fd69  mov     rcx, r12; char *
0x18003fd6c  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18003fd71  nop
0x18003fd72  jmp     loc_18003FFD3
0x18003fd77  mov     al, [rdi+2]
0x18003fd7a  cmp     byte ptr [rdi+3], 0
0x18003fd7e  jz      short loc_18003FDB7
0x18003fd80  mov     rcx, [rsp+68h]; this
0x18003fd85  test    al, al
0x18003fd87  jz      loc_18003FFED
0x18003fd8d  mov     byte ptr [rdi+3], 0
0x18003fd91  mov     qword ptr [rsp+68h+var_48], r15
0x18003fd96  lea     r9, aLeavingHs; "Leaving %hs"
0x18003fd9d  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x18003fda4  mov     edx, 89h; unsigned int
0x18003fda9  mov     rcx, r12; char *
0x18003fdac  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18003fdb1  nop
0x18003fdb2  jmp     loc_18003FFD3
0x18003fdb7  cmp     al, sil
0x18003fdba  jnz     short loc_18003FDE2
0x18003fdbc  mov     qword ptr [rsp+68h+var_48], r15
0x18003fdc1  lea     r9, aLeavingHs; "Leaving %hs"
0x18003fdc8  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x18003fdcf  mov     edx, 89h; unsigned int
0x18003fdd4  mov     rcx, r12; char *
0x18003fdd7  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18003fddc  nop
0x18003fddd  jmp     loc_18003FFD3
0x18003fde2  lea     rcx, aDisabled; "Disabled"
0x18003fde9  lea     rax, aEnabled; "Enabled"
0x18003fdf0  test    sil, sil
0x18003fdf3  cmovz   rax, rcx
0x18003fdf7  mov     [rsp+68h+var_40], rax
0x18003fdfc  mov     rax, [rdi+8]
0x18003fe00  mov     qword ptr [rsp+68h+var_48], rax; int
0x18003fe05  lea     r9, aSettingPcrpfSc; "Setting PCRPF scheduled task %ws to %hs"
0x18003fe0c  mov     r8, r15; char *
0x18003fe0f  mov     edx, 0B4h; unsigned int
0x18003fe14  lea     rcx, aOnecoreBaseNgs_5; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18003fe1b  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18003fe20  mov     r13d, 1
0x18003fe26  mov     ecx, r13d
0x18003fe29  call    cs:__imp_RoInitialize
0x18003fe30  nop     dword ptr [rax+rax+00h]
0x18003fe35  mov     ebx, eax
0x18003fe37  mov     [rsp+68h+arg_10], eax
0x18003fe3e  mov     [rsp+68h+arg_18], 0
0x18003fe4a  lea     rdx, [rsp+68h+arg_18]; struct IRegisteredTask **
0x18003fe52  mov     rcx, rdi; this
0x18003fe55  call    ?GetTask@PpfScheduledTask@@AEAAJPEAPEAUIRegisteredTask@@@Z; PpfScheduledTask::GetTask(IRegisteredTask * *)
0x18003fe5a  mov     ebp, eax
0x18003fe5c  test    eax, eax
0x18003fe5e  jns     short loc_18003FED9
0x18003fe60  mov     rcx, [rsp+68h]; this
0x18003fe65  mov     r9d, eax; char *
0x18003fe68  lea     r8, aOnecoreBaseNgs_5; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18003fe6f  mov     edx, 0B7h; void *
0x18003fe74  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003fe79  nop
0x18003fe7a  mov     rcx, [rsp+68h+arg_18]
0x18003fe82  test    rcx, rcx
0x18003fe85  jz      short loc_18003FEA0
0x18003fe87  mov     [rsp+68h+arg_18], 0
0x18003fe93  mov     rax, [rcx]
0x18003fe96  mov     rax, [rax+10h]
0x18003fe9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fe9f  nop
0x18003fea0  test    ebx, ebx
0x18003fea2  js      short loc_18003FEB1
0x18003fea4  call    cs:__imp_RoUninitialize
0x18003feab  nop     dword ptr [rax+rax+00h]
0x18003feb0  nop
0x18003feb1  mov     qword ptr [rsp+68h+var_48], r15
0x18003feb6  lea     r9, aLeavingHs; "Leaving %hs"
0x18003febd  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x18003fec4  mov     edx, 89h; unsigned int
0x18003fec9  mov     rcx, r12; char *
0x18003fecc  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18003fed1  nop
0x18003fed2  mov     eax, ebp
0x18003fed4  jmp     loc_18003FFD5
0x18003fed9  mov     rcx, [rsp+68h+arg_18]
0x18003fee1  mov     r8, [rcx]
0x18003fee4  mov     al, sil
0x18003fee7  xor     al, r13b
0x18003feea  movzx   edx, al
0x18003feed  sub     dx, r13w
0x18003fef1  mov     rax, [r8+58h]
0x18003fef5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fefa  mov     ebp, eax
0x18003fefc  test    eax, eax
0x18003fefe  jns     short loc_18003FF77
0x18003ff00  mov     rcx, [rsp+68h]; this
0x18003ff05  mov     r9d, eax; char *
0x18003ff08  lea     r8, aOnecoreBaseNgs_5; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18003ff0f  mov     edx, 0B8h; void *
0x18003ff14  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ff19  nop
0x18003ff1a  mov     rcx, [rsp+68h+arg_18]
0x18003ff22  test    rcx, rcx
0x18003ff25  jz      short loc_18003FF40
0x18003ff27  mov     [rsp+68h+arg_18], 0
0x18003ff33  mov     rax, [rcx]
0x18003ff36  mov     rax, [rax+10h]
0x18003ff3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ff3f  nop
0x18003ff40  test    ebx, ebx
0x18003ff42  js      short loc_18003FF51
0x18003ff44  call    cs:__imp_RoUninitialize
0x18003ff4b  nop     dword ptr [rax+rax+00h]
0x18003ff50  nop
0x18003ff51  mov     qword ptr [rsp+68h+var_48], r15
0x18003ff56  lea     r9, aLeavingHs; "Leaving %hs"
0x18003ff5d  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x18003ff64  mov     edx, 89h; unsigned int
0x18003ff69  mov     rcx, r12; char *
0x18003ff6c  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18003ff71  nop
0x18003ff72  jmp     loc_18003FED2
0x18003ff77  mov     [rdi+2], sil
0x18003ff7b  mov     rcx, [rsp+68h+arg_18]
0x18003ff83  test    rcx, rcx
0x18003ff86  jz      short loc_18003FFA1
0x18003ff88  mov     [rsp+68h+arg_18], 0
0x18003ff94  mov     rax, [rcx]
0x18003ff97  mov     rax, [rax+10h]
0x18003ff9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ffa0  nop
0x18003ffa1  test    ebx, ebx
0x18003ffa3  js      short loc_18003FFB2
0x18003ffa5  call    cs:__imp_RoUninitialize
0x18003ffac  nop     dword ptr [rax+rax+00h]
0x18003ffb1  nop
0x18003ffb2  mov     qword ptr [rsp+68h+var_48], r15
0x18003ffb7  lea     r9, aLeavingHs; "Leaving %hs"
0x18003ffbe  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x18003ffc5  mov     edx, 89h; unsigned int
0x18003ffca  mov     rcx, r12; char *
0x18003ffcd  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18003ffd2  nop
0x18003ffd3  xor     eax, eax
0x18003ffd5  mov     rbx, [rsp+68h+arg_0]
0x18003ffda  mov     rbp, [rsp+68h+arg_8]
0x18003ffdf  add     rsp, 40h
0x18003ffe3  pop     r15
0x18003ffe5  pop     r13
0x18003ffe7  pop     r12
0x18003ffe9  pop     rdi
0x18003ffea  pop     rsi
0x18003ffeb  retn
0x18003ffed  lea     r8, aOnecoreBaseNgs_5; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18003fff4  mov     edx, 0A6h; void *
0x18003fff9  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
