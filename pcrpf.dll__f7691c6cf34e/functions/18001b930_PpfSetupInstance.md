# PpfSetupInstance

- ea: `0x18001b930`
- end: `0x18001baa3`
- name: `PpfSetupInstance`
- size: `371`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callees

- `0x180009c64`
- `0x18001b5a0`
- `0x18001b930`
- `0x18001c0a0`
- `0x18002d5ec`
- `0x18003b0fc`

## string_xrefs

- `0x18001b994`: `onecore\base\ngscb\pcrpf\dll\pcrpfcpp.h`
- `0x18001b9ad`: `onecore\base\ngscb\pcrpf\dll\pcrpf.cpp`
- `0x18001ba20`: `onecore\base\ngscb\pcrpf\dll\pcrpf.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PpfSetupInstance(unsigned __int16 *a1, unsigned __int16 a2, unsigned int a3)
{
  int v6; // eax
  unsigned int v7; // ebx
  int v9; // eax
  int v10; // [rsp+20h] [rbp-58h]
  int v11; // [rsp+20h] [rbp-58h]
  __int64 v12; // [rsp+30h] [rbp-48h] BYREF
  char v13; // [rsp+38h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  PpfTraceLogFormat(
    "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
    0x84u,
    "PpfTraceFunctionEntryExit::PpfTraceFunctionEntryExit",
    "Entering %hs",
    "PpfSetupInstance");
  v12 = 0;
  v13 = 0;
  v6 = PpfLock(&v12);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x11,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\dll\\pcrpfcpp.h",
      (const char *)(unsigned int)v6,
      v10);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6BA,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf.cpp",
      (const char *)v7,
      v11);
    if ( v13 )
      PpfUnlock(&v12);
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
      0x89u,
      "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
      "Leaving %hs",
      "PpfSetupInstance");
    return v7;
  }
  v13 = 1;
  v9 = PpfTransformStore::SetupInstance(a1, a2, a3);
  v7 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6BC,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf.cpp",
      (const char *)(unsigned int)v9,
      v10);
    PpfUnlock(&v12);
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
      0x89u,
      "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
      "Leaving %hs",
      "PpfSetupInstance");
    return v7;
  }
  PpfUnlock(&v12);
  PpfTraceLogFormat(
    "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
    0x89u,
    "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
    "Leaving %hs",
    "PpfSetupInstance");
  return 0;
}

```

## disassembly

```asm
0x18001b930  push    rbx
0x18001b932  push    rbp
0x18001b933  push    rsi
0x18001b934  push    rdi
0x18001b935  push    r12
0x18001b937  push    r14
0x18001b939  sub     rsp, 48h
0x18001b93d  mov     edi, r8d
0x18001b940  movzx   esi, dx
0x18001b943  mov     rbp, rcx
0x18001b946  lea     r12, aPpfsetupinstan_0; "PpfSetupInstance"
0x18001b94d  mov     qword ptr [rsp+78h+var_58], r12; int
0x18001b952  lea     r9, aEnteringHs; "Entering %hs"
0x18001b959  lea     r8, aPpftracefuncti; "PpfTraceFunctionEntryExit::PpfTraceFunc"...
0x18001b960  mov     edx, 84h; unsigned int
0x18001b965  lea     rcx, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18001b96c  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18001b971  xor     eax, eax
0x18001b973  mov     [rsp+78h+var_48], rax
0x18001b978  mov     [rsp+78h+var_40], al
0x18001b97c  lea     rcx, [rsp+78h+var_48]
0x18001b981  call    PpfLock
0x18001b986  mov     ebx, eax
0x18001b988  test    eax, eax
0x18001b98a  jns     short loc_18001B9FC
0x18001b98c  mov     rcx, [rsp+78h]; this
0x18001b991  mov     r9d, eax; char *
0x18001b994  lea     r8, aOnecoreBaseNgs_10; "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf"...
0x18001b99b  mov     edx, 11h; void *
0x18001b9a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b9a5  mov     rcx, [rsp+78h]; this
0x18001b9aa  mov     r9d, ebx; char *
0x18001b9ad  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf"...
0x18001b9b4  mov     edx, 6BAh; void *
0x18001b9b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b9be  cmp     [rsp+78h+var_40], 0
0x18001b9c3  jz      short loc_18001B9D0
0x18001b9c5  lea     rcx, [rsp+78h+var_48]
0x18001b9ca  call    PpfUnlock
0x18001b9cf  nop
0x18001b9d0  mov     qword ptr [rsp+78h+var_58], r12
0x18001b9d5  lea     r9, aLeavingHs; "Leaving %hs"
0x18001b9dc  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x18001b9e3  mov     edx, 89h; unsigned int
0x18001b9e8  lea     rcx, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18001b9ef  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18001b9f4  nop
0x18001b9f5  mov     eax, ebx
0x18001b9f7  jmp     loc_18001BA95
0x18001b9fc  mov     r14b, 1
0x18001b9ff  mov     [rsp+78h+var_40], r14b
0x18001ba04  mov     r8d, edi; unsigned int
0x18001ba07  movzx   edx, si; unsigned __int16
0x18001ba0a  mov     rcx, rbp; unsigned __int16 *
0x18001ba0d  call    ?SetupInstance@PpfTransformStore@@SAJPEBGGI@Z; PpfTransformStore::SetupInstance(ushort const *,ushort,uint)
0x18001ba12  mov     ebx, eax
0x18001ba14  test    eax, eax
0x18001ba16  jns     short loc_18001BA63
0x18001ba18  mov     rcx, [rsp+78h]; this
0x18001ba1d  mov     r9d, eax; char *
0x18001ba20  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf"...
0x18001ba27  mov     edx, 6BCh; void *
0x18001ba2c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ba31  lea     rcx, [rsp+78h+var_48]
0x18001ba36  call    PpfUnlock
0x18001ba3b  nop
0x18001ba3c  mov     qword ptr [rsp+78h+var_58], r12
0x18001ba41  lea     r9, aLeavingHs; "Leaving %hs"
0x18001ba48  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x18001ba4f  mov     edx, 89h; unsigned int
0x18001ba54  lea     rcx, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18001ba5b  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18001ba60  nop
0x18001ba61  jmp     short loc_18001B9F5
0x18001ba63  lea     rcx, [rsp+78h+var_48]
0x18001ba68  call    PpfUnlock
0x18001ba6d  nop
0x18001ba6e  mov     qword ptr [rsp+78h+var_58], r12
0x18001ba73  lea     r9, aLeavingHs; "Leaving %hs"
0x18001ba7a  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x18001ba81  mov     edx, 89h; unsigned int
0x18001ba86  lea     rcx, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18001ba8d  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18001ba92  nop
0x18001ba93  xor     eax, eax
0x18001ba95  add     rsp, 48h
0x18001ba99  pop     r14
0x18001ba9b  pop     r12
0x18001ba9d  pop     rdi
0x18001ba9e  pop     rsi
0x18001ba9f  pop     rbp
0x18001baa0  pop     rbx
0x18001baa1  retn
```
