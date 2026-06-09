# PpfCancelTransformInt(ushort const *,ushort const *,uint)

- ea: `0x180013ef4`
- end: `0x1800141ed`
- name: `?PpfCancelTransformInt@@YAJPEBG0I@Z`
- size: `761`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001b0d0`
- `0x18001b110`

## callees

- `0x180003270`
- `0x180009c64`
- `0x18000f300`
- `0x18000f5dc`
- `0x18000fec8`
- `0x1800107e8`
- `0x180013ef4`
- `0x18001b5a0`
- `0x18001c0a0`
- `0x18002d5ec`
- `0x180035b18`
- `0x180038a4c`

## string_xrefs

- `0x180013f76`: `onecore\base\ngscb\pcrpf\dll\pcrpfcpp.h`
- `0x180013f8e`: `onecore\base\ngscb\pcrpf\dll\pcrpf.cpp`
- `0x180014002`: `onecore\base\ngscb\pcrpf\dll\pcrpf.cpp`
- `0x180014039`: `onecore\base\ngscb\pcrpf\dll\pcrpf.cpp`
- `0x1800140a5`: `onecore\base\ngscb\pcrpf\dll\pcrpf.cpp`
- `0x180014117`: `onecore\base\ngscb\pcrpf\dll\pcrpf.cpp`
- `0x180014178`: `onecore\base\ngscb\pcrpf\dll\pcrpf.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall PpfCancelTransformInt(const unsigned __int16 *a1, const unsigned __int16 *a2, int a3)
{
  int v6; // eax
  unsigned int v7; // edi
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // [rsp+20h] [rbp-E0h]
  int v13; // [rsp+20h] [rbp-E0h]
  __int64 v14; // [rsp+30h] [rbp-D0h] BYREF
  char v15; // [rsp+38h] [rbp-C8h]
  const char *v16; // [rsp+40h] [rbp-C0h]
  _BYTE v17[16]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v18[192]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  v16 = "PpfCancelTransformInt";
  PpfTraceLogFormat(
    "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
    0x84u,
    "PpfTraceFunctionEntryExit::PpfTraceFunctionEntryExit",
    "Entering %hs",
    "PpfCancelTransformInt");
  v14 = 0;
  v15 = 0;
  v6 = PpfLock(&v14);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x11,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\dll\\pcrpfcpp.h",
      (const char *)(unsigned int)v6,
      v12);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x41A,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf.cpp",
      (const char *)v7,
      v13);
    if ( v15 )
      PpfUnlock(&v14);
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
      0x89u,
      "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
      "Leaving %hs",
      "PpfCancelTransformInt");
    return v7;
  }
  v15 = 1;
  PpfTraceLogFormat(
    "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf.cpp",
    0x41Cu,
    "PpfCancelTransformInt",
    "Cancelling transform %ws for instance %ws");
  PpfState::PpfState((PpfState *)v17);
  v9 = PpfState::Initialize((PpfState *)v17, 0xFFFFFFFF, 0, a1);
  v7 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x41F,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf.cpp",
      (const char *)(unsigned int)v9,
      (int)a2);
    PpfState::~PpfState((PpfState *)v17);
    PpfUnlock(&v14);
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
      0x89u,
      "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
      "Leaving %hs",
      "PpfCancelTransformInt");
    return v7;
  }
  v10 = PpfTransformStore::DeleteTransform((PpfTransformStore *)v18, a2);
  v7 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x421,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf.cpp",
      (const char *)(unsigned int)v10,
      (int)a2);
    PpfState::~PpfState((PpfState *)v17);
    PpfUnlock(&v14);
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
      0x89u,
      "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
      "Leaving %hs",
      "PpfCancelTransformInt");
    return v7;
  }
  v11 = PpfState::Commit(v17, a3, 1u, 0);
  v7 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x423,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf.cpp",
      (const char *)(unsigned int)v11,
      (int)a2);
    PpfState::~PpfState((PpfState *)v17);
    PpfUnlock(&v14);
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
      0x89u,
      "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
      "Leaving %hs",
      "PpfCancelTransformInt");
    return v7;
  }
  PpfTraceLogFormat(
    "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf.cpp",
    0x425u,
    "PpfCancelTransformInt",
    "Transform cancelled");
  PpfhLogEventTransformCancelled(a2, a1);
  PpfState::~PpfState((PpfState *)v17);
  PpfUnlock(&v14);
  PpfTraceLogFormat(
    "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
    0x89u,
    "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
    "Leaving %hs",
    "PpfCancelTransformInt");
  return 0;
}

```

## disassembly

```asm
0x180013ef4  push    rbp
0x180013ef6  push    rsi
0x180013ef7  push    rdi
0x180013ef8  push    r12
0x180013efa  push    r13
0x180013efc  push    r14
0x180013efe  push    r15
0x180013f00  lea     rbp, [rsp-30h]
0x180013f05  sub     rsp, 130h
0x180013f0c  mov     rax, cs:__security_cookie
0x180013f13  xor     rax, rsp
0x180013f16  mov     [rbp+60h+var_40], rax
0x180013f1a  mov     r15d, r8d
0x180013f1d  mov     rsi, rdx
0x180013f20  mov     r14, rcx
0x180013f23  lea     r12, aPpfcanceltrans_1; "PpfCancelTransformInt"
0x180013f2a  mov     [rsp+160h+var_120], r12
0x180013f2f  mov     qword ptr [rsp+160h+var_140], r12; int
0x180013f34  lea     r9, aEnteringHs; "Entering %hs"
0x180013f3b  lea     r8, aPpftracefuncti; "PpfTraceFunctionEntryExit::PpfTraceFunc"...
0x180013f42  mov     edx, 84h; unsigned int
0x180013f47  lea     rcx, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x180013f4e  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x180013f53  nop
0x180013f54  xor     eax, eax
0x180013f56  mov     [rsp+160h+var_130], rax
0x180013f5b  mov     [rsp+160h+var_128], al
0x180013f5f  lea     rcx, [rsp+160h+var_130]
0x180013f64  call    PpfLock
0x180013f69  mov     edi, eax
0x180013f6b  test    eax, eax
0x180013f6d  jns     short loc_180013FDE
0x180013f6f  mov     rcx, [rbp+68h]; this
0x180013f73  mov     r9d, eax; char *
0x180013f76  lea     r8, aOnecoreBaseNgs_10; "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf"...
0x180013f7d  mov     edx, 11h; void *
0x180013f82  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013f87  mov     rcx, [rbp+68h]; this
0x180013f8b  mov     r9d, edi; char *
0x180013f8e  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf"...
0x180013f95  mov     edx, 41Ah; void *
0x180013f9a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013f9f  nop
0x180013fa0  cmp     [rsp+160h+var_128], 0
0x180013fa5  jz      short loc_180013FB2
0x180013fa7  lea     rcx, [rsp+160h+var_130]
0x180013fac  call    PpfUnlock
0x180013fb1  nop
0x180013fb2  mov     qword ptr [rsp+160h+var_140], r12
0x180013fb7  lea     r9, aLeavingHs; "Leaving %hs"
0x180013fbe  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x180013fc5  mov     edx, 89h; unsigned int
0x180013fca  lea     rcx, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x180013fd1  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x180013fd6  nop
0x180013fd7  mov     eax, edi
0x180013fd9  jmp     loc_1800141CD
0x180013fde  mov     r13d, 1
0x180013fe4  mov     [rsp+160h+var_128], r13b
0x180013fe9  mov     [rsp+160h+var_138], r14
0x180013fee  mov     qword ptr [rsp+160h+var_140], rsi; int
0x180013ff3  lea     r9, aCancellingTran; "Cancelling transform %ws for instance %"...
0x180013ffa  mov     r8, r12; char *
0x180013ffd  mov     edx, 41Ch; unsigned int
0x180014002  lea     rcx, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf"...
0x180014009  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18001400e  lea     rcx, [rsp+160h+var_110]; this
0x180014013  call    ??0PpfState@@QEAA@XZ; PpfState::PpfState(void)
0x180014018  nop
0x180014019  mov     r9, r14; unsigned __int16 *
0x18001401c  xor     r8d, r8d; bool
0x18001401f  or      edx, 0FFFFFFFFh; unsigned int
0x180014022  lea     rcx, [rsp+160h+var_110]; this
0x180014027  call    ?Initialize@PpfState@@QEAAJI_NPEBG@Z; PpfState::Initialize(uint,bool,ushort const *)
0x18001402c  mov     edi, eax
0x18001402e  test    eax, eax
0x180014030  jns     short loc_18001408B
0x180014032  mov     rcx, [rbp+68h]; this
0x180014036  mov     r9d, eax; char *
0x180014039  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf"...
0x180014040  mov     edx, 41Fh; void *
0x180014045  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001404a  nop
0x18001404b  lea     rcx, [rsp+160h+var_110]; this
0x180014050  call    ??1PpfState@@QEAA@XZ; PpfState::~PpfState(void)
0x180014055  nop
0x180014056  lea     rcx, [rsp+160h+var_130]
0x18001405b  call    PpfUnlock
0x180014060  nop
0x180014061  mov     qword ptr [rsp+160h+var_140], r12
0x180014066  lea     r9, aLeavingHs; "Leaving %hs"
0x18001406d  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x180014074  mov     edx, 89h; unsigned int
0x180014079  lea     rcx, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x180014080  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x180014085  nop
0x180014086  jmp     loc_180013FD7
0x18001408b  mov     rdx, rsi; unsigned __int16 *
0x18001408e  lea     rcx, [rsp+160h+var_100]; this
0x180014093  call    ?DeleteTransform@PpfTransformStore@@QEAAJPEBG@Z; PpfTransformStore::DeleteTransform(ushort const *)
0x180014098  mov     edi, eax
0x18001409a  test    eax, eax
0x18001409c  jns     short loc_1800140F7
0x18001409e  mov     rcx, [rbp+68h]; this
0x1800140a2  mov     r9d, eax; char *
0x1800140a5  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf"...
0x1800140ac  mov     edx, 421h; void *
0x1800140b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800140b6  nop
0x1800140b7  lea     rcx, [rsp+160h+var_110]; this
0x1800140bc  call    ??1PpfState@@QEAA@XZ; PpfState::~PpfState(void)
0x1800140c1  nop
0x1800140c2  lea     rcx, [rsp+160h+var_130]
0x1800140c7  call    PpfUnlock
0x1800140cc  nop
0x1800140cd  mov     qword ptr [rsp+160h+var_140], r12
0x1800140d2  lea     r9, aLeavingHs; "Leaving %hs"
0x1800140d9  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x1800140e0  mov     edx, 89h; unsigned int
0x1800140e5  lea     rcx, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x1800140ec  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x1800140f1  nop
0x1800140f2  jmp     loc_180013FD7
0x1800140f7  xor     r9d, r9d
0x1800140fa  mov     r8d, r13d
0x1800140fd  mov     edx, r15d
0x180014100  lea     rcx, [rsp+160h+var_110]
0x180014105  call    ?Commit@PpfState@@QEAAJIW4PPF_SUBSCRIBER_NOTIFICATION_SCENARIO@@PEBG@Z; PpfState::Commit(uint,PPF_SUBSCRIBER_NOTIFICATION_SCENARIO,ushort const *)
0x18001410a  mov     edi, eax
0x18001410c  test    eax, eax
0x18001410e  jns     short loc_180014169
0x180014110  mov     rcx, [rbp+68h]; this
0x180014114  mov     r9d, eax; char *
0x180014117  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf"...
0x18001411e  mov     edx, 423h; void *
0x180014123  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014128  nop
0x180014129  lea     rcx, [rsp+160h+var_110]; this
0x18001412e  call    ??1PpfState@@QEAA@XZ; PpfState::~PpfState(void)
0x180014133  nop
0x180014134  lea     rcx, [rsp+160h+var_130]
0x180014139  call    PpfUnlock
0x18001413e  nop
0x18001413f  mov     qword ptr [rsp+160h+var_140], r12
0x180014144  lea     r9, aLeavingHs; "Leaving %hs"
0x18001414b  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x180014152  mov     edx, 89h; unsigned int
0x180014157  lea     rcx, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18001415e  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x180014163  nop
0x180014164  jmp     loc_180013FD7
0x180014169  lea     r9, aTransformCance; "Transform cancelled"
0x180014170  mov     r8, r12; char *
0x180014173  mov     edx, 425h; unsigned int
0x180014178  lea     rcx, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf"...
0x18001417f  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x180014184  mov     rdx, r14; unsigned __int16 *
0x180014187  mov     rcx, rsi; unsigned __int16 *
0x18001418a  call    ?PpfhLogEventTransformCancelled@@YAJPEBG0@Z; PpfhLogEventTransformCancelled(ushort const *,ushort const *)
0x18001418f  nop
0x180014190  lea     rcx, [rsp+160h+var_110]; this
0x180014195  call    ??1PpfState@@QEAA@XZ; PpfState::~PpfState(void)
0x18001419a  nop
0x18001419b  lea     rcx, [rsp+160h+var_130]
0x1800141a0  call    PpfUnlock
0x1800141a5  nop
0x1800141a6  mov     qword ptr [rsp+160h+var_140], r12
0x1800141ab  lea     r9, aLeavingHs; "Leaving %hs"
0x1800141b2  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x1800141b9  mov     edx, 89h; unsigned int
0x1800141be  lea     rcx, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x1800141c5  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x1800141ca  nop
0x1800141cb  xor     eax, eax
0x1800141cd  mov     rcx, [rbp+60h+var_40]
0x1800141d1  xor     rcx, rsp; StackCookie
0x1800141d4  call    __security_check_cookie
0x1800141d9  add     rsp, 130h
0x1800141e0  pop     r15
0x1800141e2  pop     r14
0x1800141e4  pop     r13
0x1800141e6  pop     r12
0x1800141e8  pop     rdi
0x1800141e9  pop     rsi
0x1800141ea  pop     rbp
0x1800141eb  retn
```
