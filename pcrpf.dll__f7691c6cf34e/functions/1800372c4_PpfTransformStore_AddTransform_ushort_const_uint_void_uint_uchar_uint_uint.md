# PpfTransformStore::AddTransform(ushort const *,uint,void *,uint,uchar *,uint,uint)

- ea: `0x1800372c4`
- end: `0x180037719`
- name: `?AddTransform@PpfTransformStore@@QEAAJPEBGIPEAXIPEAEII@Z`
- size: `1109`
- prototype: `__int64 __fastcall(PpfTransformStore *this, const unsigned __int16 *, int, void *, unsigned int dwBytes, unsigned __int8 *, unsigned int Size, unsigned int)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops`

## callers

- `0x180016498`

## callees

- `0x180003270`
- `0x180009c64`
- `0x18000b5c8`
- `0x18000c6d0`
- `0x18000f674`
- `0x18001c48c`
- `0x18002a92c`
- `0x18002d5ec`
- `0x18002d75c`
- `0x1800370f4`
- `0x1800372c4`
- `0x18003bad0`
- `0x18003bd9c`
- `0x1800570b0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180037467`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800374ea`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180037467`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800374ea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037453`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800374d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037517`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800375a6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800375c6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037453`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800374d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037517`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800375a6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800375c6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003752b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800375ba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800375da`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003752b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800375ba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800375da`

## string_xrefs

- `0x1800373b4`: `Transform %ws already exists, replacing`

## pseudocode

```c
__int64 __fastcall PpfTransformStore::AddTransform(
        PpfTransformStore *this,
        const unsigned __int16 *a2,
        int a3,
        void *a4,
        unsigned int dwBytes,
        unsigned __int8 *a6,
        unsigned int Size,
        unsigned int a8)
{
  const char *v10; // r9
  __int64 v11; // rdi
  _QWORD *v12; // rbx
  __int64 v13; // r14
  const wchar_t *v14; // rcx
  __int64 v15; // rax
  size_t v16; // r8
  __int64 v17; // r8
  HANDLE ProcessHeap; // rax
  void *v19; // rax
  void *v20; // r14
  unsigned int v21; // ebx
  HANDLE v23; // rax
  void *v24; // rax
  void *v25; // rbx
  HANDLE v26; // rax
  int v27; // eax
  unsigned int v28; // r15d
  HANDLE v29; // rax
  HANDLE v30; // rax
  int v31; // eax
  int v32; // [rsp+20h] [rbp-60h]
  __int128 v35; // [rsp+48h] [rbp-38h] BYREF
  __int128 v36; // [rsp+58h] [rbp-28h]
  unsigned int v37; // [rsp+68h] [rbp-18h]
  unsigned int v38; // [rsp+6Ch] [rbp-14h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]

  PpfTraceLogFormat(
    "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
    0x84u,
    "PpfTraceFunctionEntryExit::PpfTraceFunctionEntryExit",
    "Entering %hs",
    "PpfTransformStore::AddTransform");
  if ( dword_180072BF8 != 1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x19E,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\txstore.cpp",
      v10);
  v11 = qword_180072C00;
  v12 = *(_QWORD **)qword_180072C00;
  v13 = -1;
  while ( v12 != (_QWORD *)v11 )
  {
    v14 = (const wchar_t *)(v12 + 2);
    v15 = -1;
    do
      ++v15;
    while ( a2[v15] );
    v16 = v12[4];
    if ( v12[5] > 7u )
      v14 = *(const wchar_t **)v14;
    if ( v16 == v15 && (!v16 || !wmemcmp(v14, a2, v16)) )
      break;
    v12 = (_QWORD *)*v12;
  }
  if ( v12 != (_QWORD *)qword_180072C00 )
  {
    v32 = (int)a2;
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\helperlib\\txstore.cpp",
      0x1A2u,
      "PpfTransformStore::AddTransform",
      "Transform %ws already exists, replacing");
    v35 = 0;
    v36 = 0;
    v17 = -1;
    do
      ++v17;
    while ( a2[v17] );
    std::wstring::_Construct<1,unsigned short const *>(&v35, a2);
    std::list<std::wstring>::remove(&qword_180072C00, &v35);
    std::wstring::~wstring(&v35);
    v35 = 0;
    v36 = 0;
    do
      ++v13;
    while ( a2[v13] );
    std::wstring::_Construct<1,unsigned short const *>(&v35, a2);
    std::_Tree<std::_Tmap_traits<std::wstring,PpfTransformInfo,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,PpfTransformInfo>>,0>>::erase(
      &qword_180072C10,
      &v35);
    std::wstring::~wstring(&v35);
  }
  ProcessHeap = GetProcessHeap();
  v19 = HeapAlloc(ProcessHeap, 0, dwBytes);
  v20 = v19;
  if ( !v19 )
  {
    v21 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A9,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\txstore.cpp",
      (const char *)0x8007000ELL,
      v32);
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
      0x89u,
      "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
      "Leaving %hs",
      "PpfTransformStore::AddTransform");
    return v21;
  }
  memcpy_0(v19, a4, dwBytes);
  v23 = GetProcessHeap();
  v24 = HeapAlloc(v23, 0, Size);
  v25 = v24;
  if ( !v24 )
  {
    v21 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1AE,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\txstore.cpp",
      (const char *)0x8007000ELL,
      v32);
    v26 = GetProcessHeap();
    HeapFree(v26, 0, v20);
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
      0x89u,
      "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
      "Leaving %hs",
      "PpfTransformStore::AddTransform");
    return v21;
  }
  memcpy_0(v24, a6, Size);
  v27 = PpfhAddToStringList(&qword_180072C00, a2);
  v28 = v27;
  if ( v27 >= 0 )
  {
    LODWORD(v35) = a3;
    *((_QWORD *)&v35 + 1) = v20;
    LODWORD(v36) = dwBytes;
    *((_QWORD *)&v36 + 1) = v25;
    v37 = Size;
    v38 = a8;
    v31 = AddToTransformMap(&qword_180072C10, a2, &v35);
    v21 = v31;
    if ( v31 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1B5,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\txstore.cpp",
        (const char *)(unsigned int)v31,
        v32);
      PpfTransformInfo::~PpfTransformInfo((PpfTransformInfo *)&v35);
      PpfTraceLogFormat(
        "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
        0x89u,
        "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
        "Leaving %hs",
        "PpfTransformStore::AddTransform");
      return v21;
    }
    *((_BYTE *)this + 96) = 1;
    PpfTransformInfo::~PpfTransformInfo((PpfTransformInfo *)&v35);
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
      0x89u,
      "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
      "Leaving %hs",
      "PpfTransformStore::AddTransform");
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B1,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\txstore.cpp",
      (const char *)(unsigned int)v27,
      v32);
    v29 = GetProcessHeap();
    HeapFree(v29, 0, v25);
    v30 = GetProcessHeap();
    HeapFree(v30, 0, v20);
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
      0x89u,
      "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
      "Leaving %hs",
      "PpfTransformStore::AddTransform");
    return v28;
  }
}

```

## disassembly

```asm
0x1800372c4  mov     [rsp-38h+arg_10], rbx
0x1800372c9  push    rbp
0x1800372ca  push    rsi
0x1800372cb  push    rdi
0x1800372cc  push    r12
0x1800372ce  push    r13
0x1800372d0  push    r14
0x1800372d2  push    r15
0x1800372d4  mov     rbp, rsp
0x1800372d7  sub     rsp, 80h
0x1800372de  mov     rax, cs:__security_cookie
0x1800372e5  xor     rax, rsp
0x1800372e8  mov     [rbp+var_10], rax
0x1800372ec  mov     r15, r9
0x1800372ef  mov     [rbp+var_50], r8d
0x1800372f3  mov     rsi, rdx
0x1800372f6  mov     [rbp+var_40], rcx
0x1800372fa  mov     r12d, dword ptr [rbp+dwBytes]
0x1800372fe  mov     rax, [rbp+arg_28]
0x180037302  mov     [rbp+Src], rax
0x180037306  mov     r13d, dword ptr [rbp+Size]
0x18003730a  lea     rax, aPpftransformst_8; "PpfTransformStore::AddTransform"
0x180037311  mov     qword ptr [rsp+80h+var_60], rax
0x180037316  lea     r9, aEnteringHs; "Entering %hs"
0x18003731d  lea     r8, aPpftracefuncti; "PpfTraceFunctionEntryExit::PpfTraceFunc"...
0x180037324  mov     edx, 84h; unsigned int
0x180037329  lea     rcx, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x180037330  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x180037335  cmp     cs:dword_180072BF8, 1
0x18003733c  setnz   al
0x18003733f  mov     rcx, [rbp+38h]; this
0x180037343  xor     edx, edx
0x180037345  test    al, al
0x180037347  jnz     loc_180037707
0x18003734d  mov     rdi, cs:qword_180072C00
0x180037354  mov     rbx, [rdi]
0x180037357  or      r14, 0FFFFFFFFFFFFFFFFh
0x18003735b  cmp     rbx, rdi
0x18003735e  jz      short loc_18003739B
0x180037360  lea     rcx, [rbx+10h]
0x180037364  mov     rax, r14
0x180037367  inc     rax
0x18003736a  cmp     [rsi+rax*2], dx
0x18003736e  jnz     short loc_180037367
0x180037370  mov     r8, [rbx+20h]; N
0x180037374  cmp     qword ptr [rcx+18h], 7
0x180037379  jbe     short loc_18003737E
0x18003737b  mov     rcx, [rcx]; S1
0x18003737e  cmp     r8, rax
0x180037381  jnz     short loc_180037396
0x180037383  test    r8, r8
0x180037386  jz      short loc_18003739B
0x180037388  mov     rdx, rsi; S2
0x18003738b  call    wmemcmp
0x180037390  xor     edx, edx
0x180037392  test    eax, eax
0x180037394  jz      short loc_18003739B
0x180037396  mov     rbx, [rbx]
0x180037399  jmp     short loc_18003735B
0x18003739b  lea     rdi, aOnecoreBaseNgs_9; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x1800373a2  cmp     rbx, cs:qword_180072C00
0x1800373a9  jz      loc_180037453
0x1800373af  mov     qword ptr [rsp+80h+var_60], rsi; int
0x1800373b4  lea     r9, aTransformWsAlr; "Transform %ws already exists, replacing"
0x1800373bb  lea     r8, aPpftransformst_8; "PpfTransformStore::AddTransform"
0x1800373c2  mov     edx, 1A2h; unsigned int
0x1800373c7  mov     rcx, rdi; char *
0x1800373ca  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x1800373cf  xorps   xmm0, xmm0
0x1800373d2  movups  [rbp+var_38], xmm0
0x1800373d6  xorps   xmm1, xmm1
0x1800373d9  movdqu  [rbp+var_28], xmm1
0x1800373de  mov     r8, r14
0x1800373e1  xor     ebx, ebx
0x1800373e3  inc     r8
0x1800373e6  cmp     [rsi+r8*2], bx
0x1800373eb  jnz     short loc_1800373E3
0x1800373ed  mov     rdx, rsi
0x1800373f0  lea     rcx, [rbp+var_38]
0x1800373f4  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800373f9  lea     rdx, [rbp+var_38]
0x1800373fd  lea     rcx, qword_180072C00
0x180037404  call    ?remove@?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::list<std::wstring>::remove(std::wstring const &)
0x180037409  lea     rcx, [rbp+var_38]
0x18003740d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180037412  xorps   xmm0, xmm0
0x180037415  movups  [rbp+var_38], xmm0
0x180037419  xorps   xmm1, xmm1
0x18003741c  movdqu  [rbp+var_28], xmm1
0x180037421  inc     r14
0x180037424  cmp     [rsi+r14*2], bx
0x180037429  jnz     short loc_180037421
0x18003742b  mov     r8, r14
0x18003742e  mov     rdx, rsi
0x180037431  lea     rcx, [rbp+var_38]
0x180037435  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18003743a  lea     rdx, [rbp+var_38]
0x18003743e  lea     rcx, qword_180072C10
0x180037445  call    ?erase@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VPpfTransformInfo@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VPpfTransformInfo@@@std@@@2@$0A@@std@@@std@@QEAA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,PpfTransformInfo,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,PpfTransformInfo>>,0>>::erase(std::wstring const &)
0x18003744a  lea     rcx, [rbp+var_38]
0x18003744e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180037453  call    cs:__imp_GetProcessHeap
0x18003745a  nop     dword ptr [rax+rax+00h]
0x18003745f  mov     rcx, rax; hHeap
0x180037462  mov     r8, r12; dwBytes
0x180037465  xor     edx, edx; dwFlags
0x180037467  call    cs:__imp_HeapAlloc
0x18003746e  nop     dword ptr [rax+rax+00h]
0x180037473  mov     r14, rax
0x180037476  test    rax, rax
0x180037479  jnz     short loc_1800374C8
0x18003747b  mov     rcx, [rbp+38h]; this
0x18003747f  mov     ebx, 8007000Eh
0x180037484  mov     r9d, ebx; char *
0x180037487  mov     r8, rdi; unsigned int
0x18003748a  mov     edx, 1A9h; void *
0x18003748f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037494  nop
0x180037495  lea     rax, aPpftransformst_8; "PpfTransformStore::AddTransform"
0x18003749c  mov     qword ptr [rsp+80h+var_60], rax
0x1800374a1  lea     r9, aLeavingHs; "Leaving %hs"
0x1800374a8  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x1800374af  mov     edx, 89h; unsigned int
0x1800374b4  lea     rcx, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x1800374bb  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x1800374c0  nop
0x1800374c1  mov     eax, ebx
0x1800374c3  jmp     loc_1800376DF
0x1800374c8  mov     r8, r12; Size
0x1800374cb  mov     rdx, r15; Src
0x1800374ce  mov     rcx, r14; void *
0x1800374d1  call    memcpy_0
0x1800374d6  call    cs:__imp_GetProcessHeap
0x1800374dd  nop     dword ptr [rax+rax+00h]
0x1800374e2  mov     rcx, rax; hHeap
0x1800374e5  mov     r8, r13; dwBytes
0x1800374e8  xor     edx, edx; dwFlags
0x1800374ea  call    cs:__imp_HeapAlloc
0x1800374f1  nop     dword ptr [rax+rax+00h]
0x1800374f6  mov     rbx, rax
0x1800374f9  test    rax, rax
0x1800374fc  jnz     short loc_180037569
0x1800374fe  mov     rcx, [rbp+38h]; this
0x180037502  mov     ebx, 8007000Eh
0x180037507  mov     r9d, ebx; char *
0x18003750a  mov     r8, rdi; unsigned int
0x18003750d  mov     edx, 1AEh; void *
0x180037512  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037517  call    cs:__imp_GetProcessHeap
0x18003751e  nop     dword ptr [rax+rax+00h]
0x180037523  mov     rcx, rax; hHeap
0x180037526  mov     r8, r14; lpMem
0x180037529  xor     edx, edx; dwFlags
0x18003752b  call    cs:__imp_HeapFree
0x180037532  nop     dword ptr [rax+rax+00h]
0x180037537  nop
0x180037538  lea     rax, aPpftransformst_8; "PpfTransformStore::AddTransform"
0x18003753f  mov     qword ptr [rsp+80h+var_60], rax
0x180037544  lea     r9, aLeavingHs; "Leaving %hs"
0x18003754b  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x180037552  mov     edx, 89h; unsigned int
0x180037557  lea     rcx, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18003755e  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x180037563  nop
0x180037564  jmp     loc_1800374C1
0x180037569  mov     r8, r13; Size
0x18003756c  mov     rdx, [rbp+Src]; Src
0x180037570  mov     rcx, rbx; void *
0x180037573  call    memcpy_0
0x180037578  mov     rdx, rsi
0x18003757b  lea     rcx, qword_180072C00
0x180037582  call    ?PpfhAddToStringList@@YAJAEAV?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEBG@Z; PpfhAddToStringList(std::list<std::wstring> &,ushort const *)
0x180037587  mov     r15d, eax
0x18003758a  test    eax, eax
0x18003758c  jns     loc_18003761B
0x180037592  mov     rcx, [rbp+38h]; this
0x180037596  mov     r9d, eax; char *
0x180037599  mov     r8, rdi; unsigned int
0x18003759c  mov     edx, 1B1h; void *
0x1800375a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800375a6  call    cs:__imp_GetProcessHeap
0x1800375ad  nop     dword ptr [rax+rax+00h]
0x1800375b2  mov     rcx, rax; hHeap
0x1800375b5  mov     r8, rbx; lpMem
0x1800375b8  xor     edx, edx; dwFlags
0x1800375ba  call    cs:__imp_HeapFree
0x1800375c1  nop     dword ptr [rax+rax+00h]
0x1800375c6  call    cs:__imp_GetProcessHeap
0x1800375cd  nop     dword ptr [rax+rax+00h]
0x1800375d2  mov     rcx, rax; hHeap
0x1800375d5  mov     r8, r14; lpMem
0x1800375d8  xor     edx, edx; dwFlags
0x1800375da  call    cs:__imp_HeapFree
0x1800375e1  nop     dword ptr [rax+rax+00h]
0x1800375e6  nop
0x1800375e7  lea     rax, aPpftransformst_8; "PpfTransformStore::AddTransform"
0x1800375ee  mov     qword ptr [rsp+80h+var_60], rax
0x1800375f3  lea     r9, aLeavingHs; "Leaving %hs"
0x1800375fa  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x180037601  mov     edx, 89h; unsigned int
0x180037606  lea     rcx, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18003760d  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x180037612  nop
0x180037613  mov     eax, r15d
0x180037616  jmp     loc_1800376DF
0x18003761b  mov     eax, [rbp+var_50]
0x18003761e  mov     dword ptr [rbp+var_38], eax
0x180037621  mov     qword ptr [rbp+var_38+8], r14
0x180037625  mov     dword ptr [rbp+var_28], r12d
0x180037629  mov     qword ptr [rbp+var_28+8], rbx
0x18003762d  mov     [rbp+var_18], r13d
0x180037631  mov     eax, [rbp+arg_38]
0x180037634  mov     [rbp+var_14], eax
0x180037637  lea     r8, [rbp+var_38]
0x18003763b  mov     rdx, rsi
0x18003763e  lea     rcx, qword_180072C10
0x180037645  call    ?AddToTransformMap@@YAJAEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VPpfTransformInfo@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VPpfTransformInfo@@@std@@@2@@std@@PEBGAEAVPpfTransformInfo@@@Z; AddToTransformMap(std::map<std::wstring,PpfTransformInfo> &,ushort const *,PpfTransformInfo &)
0x18003764a  mov     ebx, eax
0x18003764c  test    eax, eax
0x18003764e  jns     short loc_18003769F
0x180037650  mov     rcx, [rbp+38h]; this
0x180037654  mov     r9d, eax; char *
0x180037657  mov     r8, rdi; unsigned int
0x18003765a  mov     edx, 1B5h; void *
0x18003765f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037664  lea     rcx, [rbp+var_38]; this
0x180037668  call    ??1PpfTransformInfo@@QEAA@XZ; PpfTransformInfo::~PpfTransformInfo(void)
0x18003766d  nop
0x18003766e  lea     rax, aPpftransformst_8; "PpfTransformStore::AddTransform"
0x180037675  mov     qword ptr [rsp+80h+var_60], rax
0x18003767a  lea     r9, aLeavingHs; "Leaving %hs"
0x180037681  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x180037688  mov     edx, 89h; unsigned int
0x18003768d  lea     rcx, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x180037694  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x180037699  nop
0x18003769a  jmp     loc_1800374C1
0x18003769f  mov     rax, [rbp+var_40]
0x1800376a3  mov     byte ptr [rax+60h], 1
0x1800376a7  lea     rcx, [rbp+var_38]; this
0x1800376ab  call    ??1PpfTransformInfo@@QEAA@XZ; PpfTransformInfo::~PpfTransformInfo(void)
0x1800376b0  nop
0x1800376b1  lea     rax, aPpftransformst_8; "PpfTransformStore::AddTransform"
0x1800376b8  mov     qword ptr [rsp+80h+var_60], rax
0x1800376bd  lea     r9, aLeavingHs; "Leaving %hs"
0x1800376c4  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x1800376cb  mov     edx, 89h; unsigned int
0x1800376d0  lea     rcx, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x1800376d7  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x1800376dc  nop
0x1800376dd  xor     eax, eax
0x1800376df  mov     rcx, [rbp+var_10]
0x1800376e3  xor     rcx, rsp; StackCookie
0x1800376e6  call    __security_check_cookie
0x1800376eb  mov     rbx, [rsp+80h+arg_10]
0x1800376f3  add     rsp, 80h
0x1800376fa  pop     r15
0x1800376fc  pop     r14
0x1800376fe  pop     r13
0x180037700  pop     r12
0x180037702  pop     rdi
0x180037703  pop     rsi
0x180037704  pop     rbp
0x180037705  retn
0x180037707  lea     r8, aOnecoreBaseNgs_9; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18003770e  mov     edx, 19Eh; void *
0x180037713  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
