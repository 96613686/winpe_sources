# PpfCleanupInstance

- ea: `0x18001b140`
- end: `0x18001b2a1`
- name: `PpfCleanupInstance`
- size: `353`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x180009c64`
- `0x18001b140`
- `0x18001b5a0`
- `0x18001c0a0`
- `0x18002d5ec`
- `0x180037720`

## string_xrefs

- `0x18001b19b`: `onecore\base\ngscb\pcrpf\dll\pcrpfcpp.h`
- `0x18001b1b4`: `onecore\base\ngscb\pcrpf\dll\pcrpf.cpp`
- `0x18001b221`: `onecore\base\ngscb\pcrpf\dll\pcrpf.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PpfCleanupInstance(unsigned __int16 *a1)
{
  int v2; // eax
  unsigned int v3; // ebx
  int v5; // eax
  __int64 v6; // [rsp+30h] [rbp-38h] BYREF
  char v7; // [rsp+38h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  PpfTraceLogFormat(
    "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
    0x84u,
    "PpfTraceFunctionEntryExit::PpfTraceFunctionEntryExit",
    "Entering %hs",
    "PpfCleanupInstance");
  v6 = 0;
  v7 = 0;
  v2 = PpfLock(&v6);
  v3 = v2;
  if ( v2 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x11,
      (int)"onecore\\base\\ngscb\\pcrpf\\dll\\pcrpfcpp.h",
      (const char *)(unsigned int)v2);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6C8,
      (int)"onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf.cpp",
      (const char *)v3);
    if ( v7 )
      PpfUnlock(&v6);
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
      0x89u,
      "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
      "Leaving %hs",
      "PpfCleanupInstance");
    return v3;
  }
  v7 = 1;
  v5 = PpfTransformStore::CleanupInstance(a1);
  v3 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6CA,
      (int)"onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf.cpp",
      (const char *)(unsigned int)v5);
    PpfUnlock(&v6);
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
      0x89u,
      "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
      "Leaving %hs",
      "PpfCleanupInstance");
    return v3;
  }
  PpfUnlock(&v6);
  PpfTraceLogFormat(
    "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
    0x89u,
    "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
    "Leaving %hs",
    "PpfCleanupInstance");
  return 0;
}

```

## disassembly

```asm
0x18001b140  push    rbx
0x18001b142  push    rsi
0x18001b143  push    rdi
0x18001b144  push    r14
0x18001b146  sub     rsp, 48h
0x18001b14a  mov     rdi, rcx
0x18001b14d  lea     r14, aPpfcleanupinst_0; "PpfCleanupInstance"
0x18001b154  mov     qword ptr [rsp+68h+var_48], r14; int
0x18001b159  lea     r9, aEnteringHs; "Entering %hs"
0x18001b160  lea     r8, aPpftracefuncti; "PpfTraceFunctionEntryExit::PpfTraceFunc"...
0x18001b167  mov     edx, 84h; unsigned int
0x18001b16c  lea     rcx, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18001b173  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18001b178  xor     eax, eax
0x18001b17a  mov     [rsp+68h+var_38], rax
0x18001b17f  mov     [rsp+68h+var_30], al
0x18001b183  lea     rcx, [rsp+68h+var_38]
0x18001b188  call    PpfLock
0x18001b18d  mov     ebx, eax
0x18001b18f  test    eax, eax
0x18001b191  jns     short loc_18001B203
0x18001b193  mov     rcx, [rsp+68h]; this
0x18001b198  mov     r9d, eax; char *
0x18001b19b  lea     r8, aOnecoreBaseNgs_10; "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf"...
0x18001b1a2  mov     edx, 11h; void *
0x18001b1a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b1ac  mov     rcx, [rsp+68h]; this
0x18001b1b1  mov     r9d, ebx; char *
0x18001b1b4  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf"...
0x18001b1bb  mov     edx, 6C8h; void *
0x18001b1c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b1c5  cmp     [rsp+68h+var_30], 0
0x18001b1ca  jz      short loc_18001B1D7
0x18001b1cc  lea     rcx, [rsp+68h+var_38]
0x18001b1d1  call    PpfUnlock
0x18001b1d6  nop
0x18001b1d7  mov     qword ptr [rsp+68h+var_48], r14
0x18001b1dc  lea     r9, aLeavingHs; "Leaving %hs"
0x18001b1e3  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x18001b1ea  mov     edx, 89h; unsigned int
0x18001b1ef  lea     rcx, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18001b1f6  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18001b1fb  nop
0x18001b1fc  mov     eax, ebx
0x18001b1fe  jmp     loc_18001B296
0x18001b203  mov     sil, 1
0x18001b206  mov     [rsp+68h+var_30], sil
0x18001b20b  mov     rcx, rdi; unsigned __int16 *
0x18001b20e  call    ?CleanupInstance@PpfTransformStore@@SAJPEBG@Z; PpfTransformStore::CleanupInstance(ushort const *)
0x18001b213  mov     ebx, eax
0x18001b215  test    eax, eax
0x18001b217  jns     short loc_18001B264
0x18001b219  mov     rcx, [rsp+68h]; this
0x18001b21e  mov     r9d, eax; char *
0x18001b221  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf"...
0x18001b228  mov     edx, 6CAh; void *
0x18001b22d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b232  lea     rcx, [rsp+68h+var_38]
0x18001b237  call    PpfUnlock
0x18001b23c  nop
0x18001b23d  mov     qword ptr [rsp+68h+var_48], r14
0x18001b242  lea     r9, aLeavingHs; "Leaving %hs"
0x18001b249  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x18001b250  mov     edx, 89h; unsigned int
0x18001b255  lea     rcx, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18001b25c  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18001b261  nop
0x18001b262  jmp     short loc_18001B1FC
0x18001b264  lea     rcx, [rsp+68h+var_38]
0x18001b269  call    PpfUnlock
0x18001b26e  nop
0x18001b26f  mov     qword ptr [rsp+68h+var_48], r14
0x18001b274  lea     r9, aLeavingHs; "Leaving %hs"
0x18001b27b  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x18001b282  mov     edx, 89h; unsigned int
0x18001b287  lea     rcx, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18001b28e  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18001b293  nop
0x18001b294  xor     eax, eax
0x18001b296  add     rsp, 48h
0x18001b29a  pop     r14
0x18001b29c  pop     rdi
0x18001b29d  pop     rsi
0x18001b29e  pop     rbx
0x18001b29f  retn
```
