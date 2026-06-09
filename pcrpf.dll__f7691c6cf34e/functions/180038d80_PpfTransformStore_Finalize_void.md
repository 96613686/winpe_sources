# PpfTransformStore::Finalize(void)

- ea: `0x180038d80`
- end: `0x180038f6a`
- name: `?Finalize@PpfTransformStore@@QEAAJXZ`
- size: `490`
- prototype: `__int64 __fastcall(PpfTransformStore *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000fec8`

## callees

- `0x180003270`
- `0x180009c64`
- `0x18000b5c8`
- `0x18000dfe0`
- `0x18002d5ec`
- `0x180038d80`
- `0x180039354`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180038edc`
- `ntdll!EtwEventWrite` at `0x180038edc`

## string_xrefs

- `0x180038e7f`: `Finalize: New USN if update is committed: %llu`
- `0x180038df8`: `Finalize: USN before update: %llu`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall PpfTransformStore::Finalize(PpfTransformStore *this)
{
  const char *v2; // r9
  PpfTransformStore *v3; // rcx
  int v4; // eax
  unsigned int v5; // ebx
  unsigned int v7; // eax
  int v8; // [rsp+20h] [rbp-38h]
  unsigned int v9; // [rsp+20h] [rbp-38h]
  __int64 v10; // [rsp+30h] [rbp-28h] BYREF
  _QWORD v11[2]; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  PpfTraceLogFormat(
    "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
    0x84u,
    "PpfTraceFunctionEntryExit::PpfTraceFunctionEntryExit",
    "Entering %hs",
    "PpfTransformStore::Finalize");
  if ( dword_180072BF8 != 1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x96,
      (int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\txstore.cpp",
      v2);
  if ( !*((_BYTE *)this + 96) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x97,
      (int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\txstore.cpp",
      v2);
  PpfTraceLogFormat(
    "onecore\\base\\ngscb\\pcrpf\\helperlib\\txstore.cpp",
    0x99u,
    "PpfTransformStore::Finalize",
    "Finalize: USN before update: %llu",
    *(_QWORD *)&Data);
  v4 = PpfTransformStore::MarkUpdateInProgress(v3, 0, 1);
  v5 = v4;
  if ( v4 >= 0 )
  {
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\helperlib\\txstore.cpp",
      0xA1u,
      "PpfTransformStore::Finalize",
      "Finalize: New USN if update is committed: %llu",
      ++*(_QWORD *)&Data);
    dword_180072BF8 = 2;
    v10 = *(_QWORD *)&Data;
    v11[0] = &v10;
    v11[1] = 8;
    v7 = EtwEventWrite(g_eventProvider, PCRPF_EVENT_TRANSFORMS_FINALIZED, 1, v11);
    if ( v7 )
      wil::details::in1diag3::Return_Win32(
        retaddr,
        (void *)0x1D3,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\eventlog.cpp",
        (const char *)v7,
        v9);
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
      0x89u,
      "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
      "Leaving %hs",
      "PpfTransformStore::Finalize");
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9D,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\txstore.cpp",
      (const char *)(unsigned int)v4,
      v8);
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
      0x89u,
      "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
      "Leaving %hs",
      "PpfTransformStore::Finalize");
    return v5;
  }
}

```

## disassembly

```asm
0x180038d80  mov     [rsp+arg_8], rbx
0x180038d85  push    rdi
0x180038d86  sub     rsp, 50h
0x180038d8a  mov     rax, cs:__security_cookie
0x180038d91  xor     rax, rsp
0x180038d94  mov     [rsp+58h+var_10], rax
0x180038d99  mov     rbx, rcx
0x180038d9c  lea     rdi, aPpftransformst_10; "PpfTransformStore::Finalize"
0x180038da3  mov     qword ptr [rsp+58h+var_38], rdi
0x180038da8  lea     r9, aEnteringHs; "Entering %hs"
0x180038daf  lea     r8, aPpftracefuncti; "PpfTraceFunctionEntryExit::PpfTraceFunc"...
0x180038db6  mov     edx, 84h; unsigned int
0x180038dbb  lea     rcx, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x180038dc2  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x180038dc7  cmp     cs:dword_180072BF8, 1
0x180038dce  setnz   al
0x180038dd1  mov     rcx, [rsp+58h]; this
0x180038dd6  test    al, al
0x180038dd8  jnz     loc_180038F58
0x180038dde  mov     rcx, [rsp+58h]; this
0x180038de3  cmp     [rbx+60h], al
0x180038de6  jz      loc_180038F46
0x180038dec  mov     rax, cs:Data
0x180038df3  mov     qword ptr [rsp+58h+var_38], rax; int
0x180038df8  lea     r9, aFinalizeUsnBef; "Finalize: USN before update: %llu"
0x180038dff  mov     r8, rdi; char *
0x180038e02  mov     edx, 99h; unsigned int
0x180038e07  lea     rcx, aOnecoreBaseNgs_9; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x180038e0e  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x180038e13  mov     r8b, 1; bool
0x180038e16  xor     edx, edx; HKEY
0x180038e18  call    ?MarkUpdateInProgress@PpfTransformStore@@AEAAJPEAUHKEY__@@_N@Z; PpfTransformStore::MarkUpdateInProgress(HKEY__ *,bool)
0x180038e1d  mov     ebx, eax
0x180038e1f  test    eax, eax
0x180038e21  jns     short loc_180038E69
0x180038e23  mov     rcx, [rsp+58h]; this
0x180038e28  mov     r9d, eax; char *
0x180038e2b  lea     r8, aOnecoreBaseNgs_9; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x180038e32  mov     edx, 9Dh; void *
0x180038e37  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038e3c  nop
0x180038e3d  mov     qword ptr [rsp+58h+var_38], rdi
0x180038e42  lea     r9, aLeavingHs; "Leaving %hs"
0x180038e49  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x180038e50  mov     edx, 89h; unsigned int
0x180038e55  lea     rcx, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x180038e5c  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x180038e61  nop
0x180038e62  mov     eax, ebx
0x180038e64  jmp     loc_180038F2D
0x180038e69  mov     rax, cs:Data
0x180038e70  inc     rax
0x180038e73  mov     cs:Data, rax
0x180038e7a  mov     qword ptr [rsp+58h+var_38], rax; unsigned int
0x180038e7f  lea     r9, aFinalizeNewUsn; "Finalize: New USN if update is committe"...
0x180038e86  mov     r8, rdi; char *
0x180038e89  mov     edx, 0A1h; unsigned int
0x180038e8e  lea     rcx, aOnecoreBaseNgs_9; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x180038e95  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x180038e9a  mov     cs:dword_180072BF8, 2
0x180038ea4  mov     rax, cs:Data
0x180038eab  mov     [rsp+58h+var_28], rax
0x180038eb0  lea     rax, [rsp+58h+var_28]
0x180038eb5  mov     [rsp+58h+var_20], rax
0x180038eba  mov     [rsp+58h+var_18], 8
0x180038ec3  lea     r9, [rsp+58h+var_20]
0x180038ec8  mov     r8d, 1
0x180038ece  lea     rdx, PCRPF_EVENT_TRANSFORMS_FINALIZED
0x180038ed5  mov     rcx, cs:?g_eventProvider@@3_KA; unsigned __int64 g_eventProvider
0x180038edc  call    cs:__imp_EtwEventWrite
0x180038ee3  nop     dword ptr [rax+rax+00h]
0x180038ee8  test    eax, eax
0x180038eea  jz      short loc_180038F06
0x180038eec  mov     rcx, [rsp+58h]; this
0x180038ef1  mov     r9d, eax; char *
0x180038ef4  lea     r8, aOnecoreBaseNgs_8; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x180038efb  mov     edx, 1D3h; void *
0x180038f00  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180038f05  nop
0x180038f06  mov     qword ptr [rsp+58h+var_38], rdi
0x180038f0b  lea     r9, aLeavingHs; "Leaving %hs"
0x180038f12  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x180038f19  mov     edx, 89h; unsigned int
0x180038f1e  lea     rcx, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x180038f25  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x180038f2a  nop
0x180038f2b  xor     eax, eax
0x180038f2d  mov     rcx, [rsp+58h+var_10]
0x180038f32  xor     rcx, rsp; StackCookie
0x180038f35  call    __security_check_cookie
0x180038f3a  mov     rbx, [rsp+58h+arg_8]
0x180038f3f  add     rsp, 50h
0x180038f43  pop     rdi
0x180038f44  retn
0x180038f46  lea     r8, aOnecoreBaseNgs_9; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x180038f4d  mov     edx, 97h; void *
0x180038f52  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180038f58  lea     r8, aOnecoreBaseNgs_9; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x180038f5f  mov     edx, 96h; void *
0x180038f64  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
