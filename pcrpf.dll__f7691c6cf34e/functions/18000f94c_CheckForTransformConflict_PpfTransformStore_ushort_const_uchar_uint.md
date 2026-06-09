# CheckForTransformConflict(PpfTransformStore &,ushort const *,uchar *,uint)

- ea: `0x18000f94c`
- end: `0x18000fec0`
- name: `?CheckForTransformConflict@@YAJAEAVPpfTransformStore@@PEBGPEAEI@Z`
- size: `1396`
- prototype: `__int64 __fastcall(struct PpfTransformStore *, const char *, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180016498`

## callees

- `0x18000dfa0`
- `0x18000f94c`
- `0x1800181fc`
- `0x180028c28`
- `0x180028d5c`
- `0x18002904c`
- `0x18002d5ec`
- `0x1800570a4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000f9c9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000f9c9`

## string_xrefs

- `0x18000fa15`: `onecore\base\ngscb\pcrpf\dll\pcrpf.cpp`
- `0x18000fbe7`: `onecore\base\ngscb\pcrpf\dll\pcrpf.cpp`
- `0x18000fc31`: `onecore\base\ngscb\pcrpf\dll\pcrpf.cpp`
- `0x18000fc7c`: `onecore\base\ngscb\pcrpf\dll\pcrpf.cpp`
- `0x18000fcc7`: `onecore\base\ngscb\pcrpf\dll\pcrpf.cpp`
- `0x18000fd46`: `onecore\base\ngscb\pcrpf\dll\pcrpf.cpp`
- `0x18000fd90`: `onecore\base\ngscb\pcrpf\dll\pcrpf.cpp`
- `0x18000fddb`: `onecore\base\ngscb\pcrpf\dll\pcrpf.cpp`
- `0x18000fe49`: `onecore\base\ngscb\pcrpf\dll\pcrpf.cpp`
- `0x18000fe33`: `New transform %ws already exists as %ws, will be replaced`

## pseudocode

```c
__int64 __fastcall CheckForTransformConflict(
        struct PpfTransformStore *a1,
        const char *a2,
        unsigned __int8 *a3,
        unsigned int a4)
{
  __int64 *v7; // rbx
  _QWORD *v8; // rdi
  _QWORD *v9; // rdx
  int v10; // eax
  unsigned int v11; // ebx
  int Current; // eax
  int v14; // eax
  int v15; // esi
  int v16; // r14d
  int v17; // eax
  int v18; // eax
  int Next; // eax
  __int64 **v20; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  int v23; // [rsp+20h] [rbp-89h]
  char *v24; // [rsp+28h] [rbp-81h]
  _BYTE v25[4]; // [rsp+50h] [rbp-59h] BYREF
  int v26; // [rsp+54h] [rbp-55h] BYREF
  int v27; // [rsp+58h] [rbp-51h] BYREF
  void *Buf2; // [rsp+60h] [rbp-49h] BYREF
  void *Buf1; // [rsp+68h] [rbp-41h] BYREF
  _OWORD v30[2]; // [rsp+70h] [rbp-39h] BYREF
  __int64 v31; // [rsp+90h] [rbp-19h]
  _OWORD v32[2]; // [rsp+98h] [rbp-11h] BYREF
  __int64 v33; // [rsp+B8h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]
  struct PpfTransformStore *v35; // [rsp+110h] [rbp+67h] BYREF

  v35 = a1;
  PpfTraceLogFormat(
    "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
    0x84u,
    "PpfTraceFunctionEntryExit::PpfTraceFunctionEntryExit",
    "Entering %hs",
    "CheckForTransformConflict");
  v7 = *(__int64 **)qword_180072C10;
LABEL_2:
  if ( *((_BYTE *)v7 + 25) )
  {
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
      0x89u,
      "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
      "Leaving %hs",
      "CheckForTransformConflict");
    return 0;
  }
  v8 = v7 + 4;
  if ( (unsigned __int64)v7[7] <= 7 )
    v9 = v7 + 4;
  else
    v9 = (_QWORD *)*v8;
  if ( !(unsigned int)_o__wcsicmp(a2, v9) )
  {
    if ( (unsigned __int64)v7[7] > 7 )
      v8 = (_QWORD *)*v8;
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf.cpp",
      0x345u,
      "CheckForTransformConflict",
      "New transform %ws already exists as %ws, will be replaced",
      a2,
      v8);
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
      0x89u,
      "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
      "Leaving %hs",
      "CheckForTransformConflict");
    return 0;
  }
  memset(v30, 0, sizeof(v30));
  v31 = 0;
  v25[0] = 0;
  v10 = PpfEvtLogIteratorInitialize(v7[11], *((unsigned int *)v7 + 24), v30, v25);
  if ( v10 >= 0 )
  {
    while ( 1 )
    {
      if ( !v25[0] )
      {
        v20 = (__int64 **)v7[2];
        if ( *((_BYTE *)v20 + 25) )
        {
          for ( i = (__int64 *)v7[1]; !*((_BYTE *)i + 25) && v7 == (__int64 *)i[2]; i = (__int64 *)i[1] )
            v7 = i;
          v7 = i;
        }
        else
        {
          v7 = (__int64 *)v7[2];
          for ( j = *v20; !*((_BYTE *)j + 25); j = (__int64 *)*j )
            v7 = j;
        }
        goto LABEL_2;
      }
      v26 = 0;
      v27 = 0;
      Buf1 = 0;
      Current = PpfEvtLogIteratorGetCurrent(
                  (unsigned int)v30,
                  (unsigned int)&v26,
                  (unsigned int)&v27,
                  (unsigned int)&Buf1,
                  0,
                  0);
      if ( Current < 0 )
      {
        v11 = wil::details::in1diag3::Return_NtStatus(
                retaddr,
                (void *)0x354,
                (unsigned int)"onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf.cpp",
                (const char *)(unsigned int)Current,
                v23);
        PpfTraceLogFormat(
          "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
          0x89u,
          "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
          "Leaving %hs",
          "CheckForTransformConflict");
        return v11;
      }
      memset(v32, 0, sizeof(v32));
      v33 = 0;
      LOBYTE(v35) = 0;
      v14 = PpfEvtLogIteratorInitialize(a3, a4, v32, &v35);
      if ( v14 < 0 )
      {
        v11 = wil::details::in1diag3::Return_NtStatus(
                retaddr,
                (void *)0x35B,
                (unsigned int)"onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf.cpp",
                (const char *)(unsigned int)v14,
                v23);
        PpfTraceLogFormat(
          "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
          0x89u,
          "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
          "Leaving %hs",
          "CheckForTransformConflict");
        return v11;
      }
      if ( (_WORD)v31 != (_WORD)v33 )
      {
        LODWORD(v24) = (unsigned __int16)v31;
        v11 = -2147418113;
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x365,
          (unsigned int)"onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf.cpp",
          (const char *)0x8000FFFFLL,
          (int)"Digest algorithm or size mismatch between existing and new transform impacted events. existingTxDigestAlg"
               "ID = 0x%x, existingTxDigestSize = 0x%x, newTxDigestAlgID = 0x%x, newTxDigestSize = 0x%x",
          v24,
          WORD1(v31),
          (unsigned __int16)v33,
          WORD1(v33));
        PpfTraceLogFormat(
          "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
          0x89u,
          "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
          "Leaving %hs",
          "CheckForTransformConflict");
        return v11;
      }
      if ( (_BYTE)v35 )
        break;
LABEL_21:
      Next = PpfEvtLogIteratorTryGetNext(v30, v25);
      if ( Next < 0 )
      {
        v11 = wil::details::in1diag3::Return_NtStatus(
                retaddr,
                (void *)0x37D,
                (unsigned int)"onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf.cpp",
                (const char *)(unsigned int)Next,
                v23);
        PpfTraceLogFormat(
          "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
          0x89u,
          "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
          "Leaving %hs",
          "CheckForTransformConflict");
        return v11;
      }
    }
    v15 = v26;
    v16 = v27;
    while ( 1 )
    {
      v27 = 0;
      v26 = 0;
      Buf2 = 0;
      v17 = PpfEvtLogIteratorGetCurrent(
              (unsigned int)v32,
              (unsigned int)&v27,
              (unsigned int)&v26,
              (unsigned int)&Buf2,
              0,
              0);
      if ( v17 < 0 )
      {
        v11 = wil::details::in1diag3::Return_NtStatus(
                retaddr,
                (void *)0x36E,
                (unsigned int)"onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf.cpp",
                (const char *)(unsigned int)v17,
                v23);
        PpfTraceLogFormat(
          "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
          0x89u,
          "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
          "Leaving %hs",
          "CheckForTransformConflict");
        return v11;
      }
      if ( v15 == v27 && v16 == v26 && !memcmp_0(Buf1, Buf2, WORD1(v31)) )
        break;
      v18 = PpfEvtLogIteratorTryGetNext(v32, &v35);
      if ( v18 < 0 )
      {
        v11 = wil::details::in1diag3::Return_NtStatus(
                retaddr,
                (void *)0x37A,
                (unsigned int)"onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf.cpp",
                (const char *)(unsigned int)v18,
                v23);
        PpfTraceLogFormat(
          "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
          0x89u,
          "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
          "Leaving %hs",
          "CheckForTransformConflict");
        return v11;
      }
      if ( !(_BYTE)v35 )
        goto LABEL_21;
    }
    if ( (unsigned __int64)v7[7] > 7 )
      v8 = (_QWORD *)*v8;
    v11 = -920125439;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x377,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf.cpp",
      (const char *)0xC9280001LL,
      (int)"New transform %ws impacts same events in the next boot PPF event log as existing transform %ws",
      a2,
      v8);
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
      0x89u,
      "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
      "Leaving %hs",
      "CheckForTransformConflict");
  }
  else
  {
    v11 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0x34D,
            (unsigned int)"onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf.cpp",
            (const char *)(unsigned int)v10,
            v23);
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
      0x89u,
      "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
      "Leaving %hs",
      "CheckForTransformConflict");
  }
  return v11;
}

```

## disassembly

```asm
0x18000f94c  mov     [rsp-8+arg_0], rcx
0x18000f951  push    rbp
0x18000f952  push    rbx
0x18000f953  push    rsi
0x18000f954  push    rdi
0x18000f955  push    r12
0x18000f957  push    r13
0x18000f959  push    r14
0x18000f95b  push    r15
0x18000f95d  lea     rbp, [rsp-1Fh]
0x18000f962  sub     rsp, 0C8h
0x18000f969  mov     r12d, r9d
0x18000f96c  mov     r13, r8
0x18000f96f  mov     r15, rdx
0x18000f972  lea     r14, aCheckfortransf; "CheckForTransformConflict"
0x18000f979  mov     qword ptr [rsp+100h+var_E0], r14; int
0x18000f97e  lea     r9, aEnteringHs; "Entering %hs"
0x18000f985  lea     r8, aPpftracefuncti; "PpfTraceFunctionEntryExit::PpfTraceFunc"...
0x18000f98c  mov     edx, 84h; unsigned int
0x18000f991  lea     rcx, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18000f998  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18000f99d  mov     rbx, cs:qword_180072C10
0x18000f9a4  mov     rbx, [rbx]
0x18000f9a7  xor     esi, esi
0x18000f9a9  cmp     [rbx+19h], sil
0x18000f9ad  jnz     loc_18000FE7D
0x18000f9b3  lea     rdi, [rbx+20h]
0x18000f9b7  cmp     qword ptr [rbx+38h], 7
0x18000f9bc  jbe     short loc_18000F9C3
0x18000f9be  mov     rdx, [rdi]
0x18000f9c1  jmp     short loc_18000F9C6
0x18000f9c3  mov     rdx, rdi
0x18000f9c6  mov     rcx, r15
0x18000f9c9  call    cs:__imp__o__wcsicmp
0x18000f9d0  nop     dword ptr [rax+rax+00h]
0x18000f9d5  test    eax, eax
0x18000f9d7  jz      loc_18000FE1F
0x18000f9dd  xorps   xmm0, xmm0
0x18000f9e0  xor     eax, eax
0x18000f9e2  movups  [rbp+57h+var_90], xmm0
0x18000f9e6  movups  [rbp+57h+var_80], xmm0
0x18000f9ea  mov     [rbp+57h+var_70], rax
0x18000f9ee  mov     [rbp+57h+var_B0], sil
0x18000f9f2  lea     r9, [rbp+57h+var_B0]
0x18000f9f6  lea     r8, [rbp+57h+var_90]
0x18000f9fa  mov     edx, [rbx+60h]
0x18000f9fd  mov     rcx, [rbx+58h]
0x18000fa01  call    PpfEvtLogIteratorInitialize
0x18000fa06  test    eax, eax
0x18000fa08  jns     loc_18000FB62
0x18000fa0e  mov     rcx, [rbp+5Fh]; this
0x18000fa12  mov     r9d, eax; char *
0x18000fa15  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf"...
0x18000fa1c  mov     edx, 34Dh; void *
0x18000fa21  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18000fa26  mov     ebx, eax
0x18000fa28  lea     rdi, aCheckfortransf; "CheckForTransformConflict"
0x18000fa2f  mov     qword ptr [rsp+100h+var_E0], rdi
0x18000fa34  lea     r9, aLeavingHs; "Leaving %hs"
0x18000fa3b  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x18000fa42  mov     edx, 89h; unsigned int
0x18000fa47  lea     rcx, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18000fa4e  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18000fa53  nop
0x18000fa54  mov     eax, ebx
0x18000fa56  jmp     loc_18000FEAB
0x18000fa5b  mov     [rbp+57h+var_AC], esi
0x18000fa5e  mov     [rbp+57h+var_A8], esi
0x18000fa61  mov     [rbp+57h+Buf1], rsi
0x18000fa65  mov     [rsp+100h+var_D8], rsi
0x18000fa6a  mov     qword ptr [rsp+100h+var_E0], rsi; int
0x18000fa6f  lea     r9, [rbp+57h+Buf1]
0x18000fa73  lea     r8, [rbp+57h+var_A8]
0x18000fa77  lea     rdx, [rbp+57h+var_AC]
0x18000fa7b  lea     rcx, [rbp+57h+var_90]
0x18000fa7f  call    PpfEvtLogIteratorGetCurrent
0x18000fa84  test    eax, eax
0x18000fa86  js      loc_18000FDD4
0x18000fa8c  xorps   xmm0, xmm0
0x18000fa8f  xor     eax, eax
0x18000fa91  movups  [rbp+57h+var_68], xmm0
0x18000fa95  movups  [rbp+57h+var_58], xmm0
0x18000fa99  mov     [rbp+57h+var_48], rax
0x18000fa9d  mov     byte ptr [rbp+57h+arg_0], sil
0x18000faa1  lea     r9, [rbp+57h+arg_0]
0x18000faa5  lea     r8, [rbp+57h+var_68]
0x18000faa9  mov     edx, r12d
0x18000faac  mov     rcx, r13
0x18000faaf  call    PpfEvtLogIteratorInitialize
0x18000fab4  test    eax, eax
0x18000fab6  js      loc_18000FD89
0x18000fabc  mov     rcx, [rbp+57h+var_48]
0x18000fac0  cmp     word ptr [rbp+57h+var_70], cx
0x18000fac4  jnz     loc_18000FD0B
0x18000faca  cmp     byte ptr [rbp+57h+arg_0], sil
0x18000face  jz      short loc_18000FB4D
0x18000fad0  mov     esi, [rbp+57h+var_AC]
0x18000fad3  mov     r14d, [rbp+57h+var_A8]
0x18000fad7  xor     ecx, ecx
0x18000fad9  mov     [rbp+57h+var_A8], ecx
0x18000fadc  mov     [rbp+57h+var_AC], ecx
0x18000fadf  mov     [rbp+57h+Buf2], rcx
0x18000fae3  mov     [rsp+100h+var_D8], rcx
0x18000fae8  mov     qword ptr [rsp+100h+var_E0], rcx; int
0x18000faed  lea     r9, [rbp+57h+Buf2]
0x18000faf1  lea     r8, [rbp+57h+var_AC]
0x18000faf5  lea     rdx, [rbp+57h+var_A8]
0x18000faf9  lea     rcx, [rbp+57h+var_68]
0x18000fafd  call    PpfEvtLogIteratorGetCurrent
0x18000fb02  test    eax, eax
0x18000fb04  js      loc_18000FC75
0x18000fb0a  cmp     esi, [rbp+57h+var_A8]
0x18000fb0d  jnz     short loc_18000FB2F
0x18000fb0f  cmp     r14d, [rbp+57h+var_AC]
0x18000fb13  jnz     short loc_18000FB2F
0x18000fb15  movzx   r8d, word ptr [rbp+57h+var_70+2]; Size
0x18000fb1a  mov     rdx, [rbp+57h+Buf2]; Buf2
0x18000fb1e  mov     rcx, [rbp+57h+Buf1]; Buf1
0x18000fb22  call    memcmp_0
0x18000fb27  test    eax, eax
0x18000fb29  jz      loc_18000FBBB
0x18000fb2f  lea     rdx, [rbp+57h+arg_0]
0x18000fb33  lea     rcx, [rbp+57h+var_68]
0x18000fb37  call    PpfEvtLogIteratorTryGetNext
0x18000fb3c  xor     ecx, ecx
0x18000fb3e  test    eax, eax
0x18000fb40  js      loc_18000FC2A
0x18000fb46  cmp     byte ptr [rbp+57h+arg_0], cl
0x18000fb49  jnz     short loc_18000FAD9
0x18000fb4b  xor     esi, esi
0x18000fb4d  lea     rdx, [rbp+57h+var_B0]
0x18000fb51  lea     rcx, [rbp+57h+var_90]
0x18000fb55  call    PpfEvtLogIteratorTryGetNext
0x18000fb5a  test    eax, eax
0x18000fb5c  js      loc_18000FCC0
0x18000fb62  cmp     [rbp+57h+var_B0], sil
0x18000fb66  jnz     loc_18000FA5B
0x18000fb6c  mov     rcx, [rbx+10h]
0x18000fb70  cmp     [rcx+19h], sil
0x18000fb74  jz      short loc_18000FB97
0x18000fb76  mov     rax, [rbx+8]
0x18000fb7a  jmp     short loc_18000FB89
0x18000fb7c  cmp     rbx, [rax+10h]
0x18000fb80  jnz     short loc_18000FB8F
0x18000fb82  mov     rbx, rax
0x18000fb85  mov     rax, [rax+8]
0x18000fb89  cmp     [rax+19h], sil
0x18000fb8d  jz      short loc_18000FB7C
0x18000fb8f  mov     rbx, rax
0x18000fb92  jmp     loc_18000F9A9
0x18000fb97  mov     rbx, rcx
0x18000fb9a  mov     rcx, [rcx]
0x18000fb9d  cmp     [rcx+19h], sil
0x18000fba1  jnz     loc_18000F9A9
0x18000fba7  mov     rbx, rcx
0x18000fbaa  mov     rax, [rcx]
0x18000fbad  mov     rcx, rax
0x18000fbb0  cmp     [rax+19h], sil
0x18000fbb4  jz      short loc_18000FBA7
0x18000fbb6  jmp     loc_18000F9A9
0x18000fbbb  cmp     qword ptr [rdi+18h], 7
0x18000fbc0  jbe     short loc_18000FBC5
0x18000fbc2  mov     rdi, [rdi]
0x18000fbc5  mov     rcx, [rbp+5Fh]; this
0x18000fbc9  mov     [rsp+100h+var_D0], rdi
0x18000fbce  mov     [rsp+100h+var_D8], r15; char *
0x18000fbd3  lea     rax, aNewTransformWs_0; "New transform %ws impacts same events i"...
0x18000fbda  mov     qword ptr [rsp+100h+var_E0], rax; int
0x18000fbdf  mov     ebx, 0C9280001h
0x18000fbe4  mov     r9d, ebx; char *
0x18000fbe7  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf"...
0x18000fbee  mov     edx, 377h; void *
0x18000fbf3  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000fbf8  nop
0x18000fbf9  lea     rdi, aCheckfortransf; "CheckForTransformConflict"
0x18000fc00  mov     qword ptr [rsp+100h+var_E0], rdi
0x18000fc05  lea     r9, aLeavingHs; "Leaving %hs"
0x18000fc0c  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x18000fc13  mov     edx, 89h; unsigned int
0x18000fc18  lea     rcx, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18000fc1f  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18000fc24  nop
0x18000fc25  jmp     loc_18000FA54
0x18000fc2a  mov     rcx, [rbp+5Fh]; this
0x18000fc2e  mov     r9d, eax; char *
0x18000fc31  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf"...
0x18000fc38  mov     edx, 37Ah; void *
0x18000fc3d  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18000fc42  mov     ebx, eax
0x18000fc44  lea     rdi, aCheckfortransf; "CheckForTransformConflict"
0x18000fc4b  mov     qword ptr [rsp+100h+var_E0], rdi
0x18000fc50  lea     r9, aLeavingHs; "Leaving %hs"
0x18000fc57  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x18000fc5e  mov     edx, 89h; unsigned int
0x18000fc63  lea     rcx, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18000fc6a  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18000fc6f  nop
0x18000fc70  jmp     loc_18000FA54
0x18000fc75  mov     rcx, [rbp+5Fh]; this
0x18000fc79  mov     r9d, eax; char *
0x18000fc7c  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf"...
0x18000fc83  mov     edx, 36Eh; void *
0x18000fc88  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18000fc8d  mov     ebx, eax
0x18000fc8f  lea     rdi, aCheckfortransf; "CheckForTransformConflict"
0x18000fc96  mov     qword ptr [rsp+100h+var_E0], rdi
0x18000fc9b  lea     r9, aLeavingHs; "Leaving %hs"
0x18000fca2  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x18000fca9  mov     edx, 89h; unsigned int
0x18000fcae  lea     rcx, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18000fcb5  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18000fcba  nop
0x18000fcbb  jmp     loc_18000FA54
0x18000fcc0  mov     rcx, [rbp+5Fh]; this
0x18000fcc4  mov     r9d, eax; char *
0x18000fcc7  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf"...
0x18000fcce  mov     edx, 37Dh; void *
0x18000fcd3  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18000fcd8  mov     ebx, eax
0x18000fcda  lea     rdi, aCheckfortransf; "CheckForTransformConflict"
0x18000fce1  mov     qword ptr [rsp+100h+var_E0], rdi
0x18000fce6  lea     r9, aLeavingHs; "Leaving %hs"
0x18000fced  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x18000fcf4  mov     edx, 89h; unsigned int
0x18000fcf9  lea     rcx, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18000fd00  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18000fd05  nop
0x18000fd06  jmp     loc_18000FA54
0x18000fd0b  movzx   eax, word ptr [rbp+57h+var_48+2]
0x18000fd0f  movzx   edx, cx
0x18000fd12  movzx   r8d, word ptr [rbp+57h+var_70+2]
0x18000fd17  movzx   r9d, word ptr [rbp+57h+var_70]
0x18000fd1c  mov     rcx, [rbp+5Fh]; this
0x18000fd20  mov     [rsp+100h+var_C0], eax
0x18000fd24  mov     [rsp+100h+var_C8], edx
0x18000fd28  mov     dword ptr [rsp+100h+var_D0], r8d
0x18000fd2d  mov     dword ptr [rsp+100h+var_D8], r9d; char *
0x18000fd32  lea     rax, aDigestAlgorith; "Digest algorithm or size mismatch betwe"...
0x18000fd39  mov     qword ptr [rsp+100h+var_E0], rax; int
0x18000fd3e  mov     ebx, 8000FFFFh
0x18000fd43  mov     r9d, ebx; char *
0x18000fd46  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf"...
0x18000fd4d  mov     edx, 365h; void *
0x18000fd52  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000fd57  nop
0x18000fd58  lea     rdi, aCheckfortransf; "CheckForTransformConflict"
0x18000fd5f  mov     qword ptr [rsp+100h+var_E0], rdi
0x18000fd64  lea     r9, aLeavingHs; "Leaving %hs"
0x18000fd6b  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x18000fd72  mov     edx, 89h; unsigned int
0x18000fd77  lea     rcx, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18000fd7e  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18000fd83  nop
0x18000fd84  jmp     loc_18000FA54
0x18000fd89  mov     rcx, [rbp+5Fh]; this
0x18000fd8d  mov     r9d, eax; char *
0x18000fd90  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf"...
0x18000fd97  mov     edx, 35Bh; void *
0x18000fd9c  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18000fda1  mov     ebx, eax
0x18000fda3  lea     rdi, aCheckfortransf; "CheckForTransformConflict"
0x18000fdaa  mov     qword ptr [rsp+100h+var_E0], rdi
0x18000fdaf  lea     r9, aLeavingHs; "Leaving %hs"
0x18000fdb6  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x18000fdbd  mov     edx, 89h; unsigned int
0x18000fdc2  lea     rcx, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18000fdc9  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18000fdce  nop
0x18000fdcf  jmp     loc_18000FA54
0x18000fdd4  mov     rcx, [rbp+5Fh]; this
0x18000fdd8  mov     r9d, eax; char *
0x18000fddb  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf"...
0x18000fde2  mov     edx, 354h; void *
0x18000fde7  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18000fdec  mov     ebx, eax
0x18000fdee  lea     rdi, aCheckfortransf; "CheckForTransformConflict"
0x18000fdf5  mov     qword ptr [rsp+100h+var_E0], rdi
0x18000fdfa  lea     r9, aLeavingHs; "Leaving %hs"
0x18000fe01  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x18000fe08  mov     edx, 89h; unsigned int
0x18000fe0d  lea     rcx, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18000fe14  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18000fe19  nop
0x18000fe1a  jmp     loc_18000FA54
0x18000fe1f  cmp     qword ptr [rdi+18h], 7
0x18000fe24  jbe     short loc_18000FE29
0x18000fe26  mov     rdi, [rdi]
0x18000fe29  mov     [rsp+100h+var_D8], rdi
0x18000fe2e  mov     qword ptr [rsp+100h+var_E0], r15
0x18000fe33  lea     r9, aNewTransformWs; "New transform %ws already exists as %ws"...
0x18000fe3a  lea     rdi, aCheckfortransf; "CheckForTransformConflict"
0x18000fe41  mov     r8, rdi; char *
0x18000fe44  mov     edx, 345h; unsigned int
0x18000fe49  lea     rcx, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf"...
0x18000fe50  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18000fe55  nop
0x18000fe56  mov     qword ptr [rsp+100h+var_E0], rdi
0x18000fe5b  lea     r9, aLeavingHs; "Leaving %hs"
0x18000fe62  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x18000fe69  mov     edx, 89h; unsigned int
  ... truncated ...
```
