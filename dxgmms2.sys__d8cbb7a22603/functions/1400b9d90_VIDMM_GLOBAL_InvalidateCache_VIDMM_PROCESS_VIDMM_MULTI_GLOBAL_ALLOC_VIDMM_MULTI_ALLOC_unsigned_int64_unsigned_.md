# VIDMM_GLOBAL::InvalidateCache(VIDMM_PROCESS *,VIDMM_MULTI_GLOBAL_ALLOC *,VIDMM_MULTI_ALLOC *,unsigned __int64,unsigned __int64)

- ea: `0x1400b9d90`
- end: `0x1400ba0ff`
- name: `?InvalidateCache@VIDMM_GLOBAL@@QEAAJPEAVVIDMM_PROCESS@@PEAUVIDMM_MULTI_GLOBAL_ALLOC@@PEAUVIDMM_MULTI_ALLOC@@_K3@Z`
- size: `879`
- prototype: `__int64 __fastcall(VIDMM_GLOBAL *__hidden this, struct VIDMM_PROCESS *, struct VIDMM_MULTI_GLOBAL_ALLOC *, struct VIDMM_MULTI_ALLOC *, unsigned __int64, ULONG Length)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1400472d0`

## callees

- `0x140004268`
- `0x14002d810`
- `0x14002da90`
- `0x140031434`
- `0x14003196c`
- `0x14003a734`
- `0x140058f50`
- `0x1400b3544`
- `0x1400b9d90`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400ba031`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400ba031`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400b9f3d`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400b9f3d`
- `watchdog!WdLogSingleEntry0` at `0x1400b9df7`
- `watchdog!WdLogSingleEntry0` at `0x1400b9e20`
- `watchdog!WdLogSingleEntry0` at `0x1400b9ea2`
- `watchdog!WdLogSingleEntry0` at `0x1400b9f0f`
- `watchdog!WdLogSingleEntry0` at `0x1400b9df7`
- `watchdog!WdLogSingleEntry0` at `0x1400b9e20`
- `watchdog!WdLogSingleEntry0` at `0x1400b9ea2`
- `watchdog!WdLogSingleEntry0` at `0x1400b9f0f`
- `watchdog!WdLogSingleEntry1` at `0x1400b9f76`
- `watchdog!WdLogSingleEntry1` at `0x1400b9fac`
- `watchdog!WdLogSingleEntry1` at `0x1400ba04e`
- `watchdog!WdLogSingleEntry1` at `0x1400b9f76`
- `watchdog!WdLogSingleEntry1` at `0x1400b9fac`
- `watchdog!WdLogSingleEntry1` at `0x1400ba04e`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400b9f29`

## string_xrefs

- `0x1400b9e31`: `Both pAlloc and pGlobalAlloc null in InvalidateCache`
- `0x1400b9eb3`: `pProcess is NULL when pAlloc is NULL in InvalidateCache`
- `0x1400b9f20`: `unable to find local allocation in InvalidateCache`
- `0x1400b9f8c`: `Offset passed to InvalidateCache must not overflow the allocation. SizeInSegment=%I64d`
- `0x1400b9fc2`: `Length passed to InvalidateCache must not overflow the allocation. SizeInSegment=%I64d`

## pseudocode

```c
__int64 __fastcall VIDMM_GLOBAL::InvalidateCache(
        VIDMM_GLOBAL *this,
        struct VIDMM_PROCESS *a2,
        struct VIDMM_MULTI_GLOBAL_ALLOC *a3,
        struct VIDMM_MULTI_GLOBAL_ALLOC ***a4,
        unsigned __int64 a5,
        unsigned __int64 Length)
{
  struct VIDMM_MULTI_GLOBAL_ALLOC *v7; // rdi
  __int64 result; // rax
  int v10; // ecx
  int v11; // r8d
  struct VIDMM_MULTI_GLOBAL_ALLOC **v12; // r14
  __int64 v13; // r15
  __int64 v14; // rcx
  int v15; // ecx
  int v16; // r8d
  __int64 v17; // rax
  const wchar_t *v18; // r9
  _QWORD *i; // rax
  unsigned __int64 v20; // rbp
  _QWORD *v21; // rax
  unsigned __int64 v22; // rdx
  bool v23; // r8
  char *v24; // rsi
  __int64 *v25; // rcx
  __int64 v26; // rcx
  int v27; // ecx
  int v28; // r8d
  unsigned int v29; // ebx
  __int64 v30; // r8
  _BYTE v31[16]; // [rsp+50h] [rbp-98h] BYREF
  _BYTE v32[64]; // [rsp+60h] [rbp-88h] BYREF

  v7 = a3;
  if ( !*((_BYTE *)this + 3203) && (!a2 || (*(_DWORD *)(*((_QWORD *)a2 + 10) + 408LL) & 0x1000) == 0) )
  {
    WdLogSingleEntry0(4);
    result = 0;
    WdLogGlobalForLineNumber = 29926;
    return result;
  }
  if ( a4 )
  {
    v12 = *a4;
    v7 = **a4;
  }
  else
  {
    if ( !a3 )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 29937;
      DxgkLogInternalTriageEvent(
        v10,
        0x40000,
        v11,
        (unsigned int)L"Both pAlloc and pGlobalAlloc null in InvalidateCache",
        29937,
        0,
        0,
        0);
      return 3221225485LL;
    }
    v12 = 0;
  }
  v13 = *(_QWORD *)v7;
  DXGAUTOMUTEX::DXGAUTOMUTEX((DXGAUTOMUTEX *)v31, (struct VIDMM_MULTI_GLOBAL_ALLOC *)((char *)v7 + 136), 0);
  DXGAUTOMUTEX::Acquire((DXGAUTOMUTEX *)v31);
  if ( !a4 )
  {
    if ( !a2 )
    {
      WdLogSingleEntry0(1);
      v17 = 29961;
      v18 = L"pProcess is NULL when pAlloc is NULL in InvalidateCache";
LABEL_14:
      WdLogGlobalForLineNumber = v17;
LABEL_15:
      DxgkLogInternalTriageEvent(v15, 0x40000, v16, (_DWORD)v18, v17, 0, 0, 0);
      DXGAUTOMUTEX::~DXGAUTOMUTEX((DXGAUTOMUTEX *)v31);
      return 3221225485LL;
    }
    for ( i = (_QWORD *)*((_QWORD *)v7 + 14); i != (_QWORD *)((char *)v7 + 112); i = (_QWORD *)*i )
    {
      if ( (struct VIDMM_PROCESS *)*(i - 5) == a2 )
      {
        v12 = (struct VIDMM_MULTI_GLOBAL_ALLOC **)(i - 6);
        break;
      }
    }
    if ( !v12 )
    {
      WdLogSingleEntry0(1);
      v17 = 29982;
      v18 = L"unable to find local allocation in InvalidateCache";
      goto LABEL_14;
    }
  }
  v20 = Length;
  if ( g_IsInternalReleaseOrDbg )
  {
    v21 = (_QWORD *)WdLogNewEntry5_WdTrace(v14);
    v21[3] = a4;
    v21[4] = a5;
    v21[5] = Length;
    WdLogGlobalForLineNumber = 29991;
  }
  if ( !Length )
    v20 = *(_QWORD *)(v13 + 16);
  v22 = *(_QWORD *)(v13 + 16);
  if ( a5 >= v22 )
  {
    WdLogSingleEntry1(1, v22);
    WdLogGlobalForLineNumber = 30005;
    v18 = L"Offset passed to InvalidateCache must not overflow the allocation. SizeInSegment=%I64d";
    v17 = *(_QWORD *)(v13 + 16);
    goto LABEL_15;
  }
  if ( v20 > v22 - a5 )
  {
    WdLogSingleEntry1(1, v22);
    WdLogGlobalForLineNumber = 30013;
    v18 = L"Length passed to InvalidateCache must not overflow the allocation. SizeInSegment=%I64d";
    v17 = *(_QWORD *)(v13 + 16);
    goto LABEL_15;
  }
  if ( (*((_DWORD *)v7 + 7) & 0x50) != 0 )
  {
    v25 = (__int64 *)*((_QWORD *)v7 + 30);
    if ( (v25[4] & 3) != 0 )
    {
      v26 = *v25;
      if ( (*(_BYTE *)(v26 + 10) & 5) != 0 )
        v24 = *(char **)(v26 + 24);
      else
        v24 = (char *)MmMapLockedPagesSpecifyCache((PMDL)v26, 0, MmCached, 0, 0, 0x40000010u);
    }
    else
    {
      v24 = 0;
    }
    v23 = 1;
  }
  else
  {
    v23 = 0;
    if ( (**((_DWORD **)v7 + 49) & 8) != 0 )
      v24 = (char *)*((_QWORD *)v7 + 28);
    else
      v24 = (char *)v12[2];
  }
  if ( v24 )
  {
    v29 = 0;
    if ( *((_DWORD *)v7 + 18) == 2 && (*(_DWORD *)(v13 + 64) & 4) != 0 )
    {
      VIDMM_PROCESS_AUTOATTACH::VIDMM_PROCESS_AUTOATTACH((VIDMM_PROCESS_AUTOATTACH *)v32, v12[1], v23);
      v29 = VidMmFlushCpuCacheWorker(&v24[a5], v20, v30);
      VIDMM_PROCESS_AUTOATTACH::~VIDMM_PROCESS_AUTOATTACH((VIDMM_PROCESS_AUTOATTACH *)v32);
    }
  }
  else
  {
    WdLogSingleEntry1(1, v7);
    WdLogGlobalForLineNumber = 30063;
    DxgkLogInternalTriageEvent(
      v27,
      0x40000,
      v28,
      (unsigned int)L"VIDMM_GLOBAL_ALLOC 0x%.16I64x is not CPU visible or has no mapped virtual address",
      (__int64)v7,
      0,
      0,
      0);
    v29 = -1073741811;
  }
  DXGAUTOMUTEX::~DXGAUTOMUTEX((DXGAUTOMUTEX *)v31);
  return v29;
}

```

## disassembly

```asm
0x1400b9d90  mov     [rsp+arg_0], rbx
0x1400b9d95  push    rbp
0x1400b9d96  push    rsi
0x1400b9d97  push    rdi
0x1400b9d98  push    r12
0x1400b9d9a  push    r13
0x1400b9d9c  push    r14
0x1400b9d9e  push    r15
0x1400b9da0  sub     rsp, 0B0h
0x1400b9da7  mov     rax, cs:__security_cookie
0x1400b9dae  xor     rax, rsp
0x1400b9db1  mov     [rsp+0E8h+var_48], rax
0x1400b9db9  mov     r12, [rsp+0E8h+arg_20]
0x1400b9dc1  xor     r13d, r13d
0x1400b9dc4  mov     rsi, r9
0x1400b9dc7  mov     rdi, r8
0x1400b9dca  mov     rbx, rdx
0x1400b9dcd  mov     ebp, 1
0x1400b9dd2  cmp     [rcx+0C83h], r13b
0x1400b9dd9  jnz     short loc_1400B9E14
0x1400b9ddb  test    rdx, rdx
0x1400b9dde  jz      short loc_1400B9DF2
0x1400b9de0  mov     rax, [rdx+50h]
0x1400b9de4  mov     ecx, [rax+198h]
0x1400b9dea  shr     ecx, 0Ch
0x1400b9ded  test    bpl, cl
0x1400b9df0  jnz     short loc_1400B9E14
0x1400b9df2  mov     ecx, 4
0x1400b9df7  call    cs:__imp_WdLogSingleEntry0
0x1400b9dfe  nop     dword ptr [rax+rax+00h]
0x1400b9e03  xor     eax, eax
0x1400b9e05  mov     cs:WdLogGlobalForLineNumber, 74E6h
0x1400b9e0f  jmp     loc_1400BA0D3
0x1400b9e14  test    rsi, rsi
0x1400b9e17  jnz     short loc_1400B9E6B
0x1400b9e19  test    r8, r8
0x1400b9e1c  jnz     short loc_1400B9E66
0x1400b9e1e  mov     ecx, ebp
0x1400b9e20  call    cs:__imp_WdLogSingleEntry0
0x1400b9e27  nop     dword ptr [rax+rax+00h]
0x1400b9e2c  mov     [rsp+0E8h+var_B0], r13
0x1400b9e31  lea     r9, aBothPallocAndP; "Both pAlloc and pGlobalAlloc null in In"...
0x1400b9e38  mov     eax, 74F1h
0x1400b9e3d  mov     [rsp+0E8h+var_B8], r13
0x1400b9e42  mov     qword ptr [rsp+0E8h+Priority], r13
0x1400b9e47  mov     edx, 40000h
0x1400b9e4c  mov     cs:WdLogGlobalForLineNumber, eax
0x1400b9e52  mov     qword ptr [rsp+0E8h+BugCheckOnFailure], rax
0x1400b9e57  call    DxgkLogInternalTriageEvent
0x1400b9e5c  mov     eax, 0C000000Dh
0x1400b9e61  jmp     loc_1400BA0D3
0x1400b9e66  mov     r14, r13
0x1400b9e69  jmp     short loc_1400B9E71
0x1400b9e6b  mov     r14, [r9]
0x1400b9e6e  mov     rdi, [r14]
0x1400b9e71  mov     r15, [rdi]
0x1400b9e74  lea     rdx, [rdi+88h]; struct DXGFASTMUTEX *
0x1400b9e7b  xor     r8d, r8d; unsigned __int8
0x1400b9e7e  lea     rcx, [rsp+0E8h+var_98]; this
0x1400b9e83  call    ??0DXGAUTOMUTEX@@QEAA@QEAVDXGFASTMUTEX@@E@Z; DXGAUTOMUTEX::DXGAUTOMUTEX(DXGFASTMUTEX * const,uchar)
0x1400b9e88  lea     rcx, [rsp+0E8h+var_98]; this
0x1400b9e8d  call    ?Acquire@DXGAUTOMUTEX@@QEAAXXZ; DXGAUTOMUTEX::Acquire(void)
0x1400b9e92  test    rsi, rsi
0x1400b9e95  jnz     loc_1400B9F29
0x1400b9e9b  test    rbx, rbx
0x1400b9e9e  jnz     short loc_1400B9EED
0x1400b9ea0  mov     ecx, ebp
0x1400b9ea2  call    cs:__imp_WdLogSingleEntry0
0x1400b9ea9  nop     dword ptr [rax+rax+00h]
0x1400b9eae  mov     eax, 7509h
0x1400b9eb3  lea     r9, aPprocessIsNull; "pProcess is NULL when pAlloc is NULL in"...
0x1400b9eba  mov     cs:WdLogGlobalForLineNumber, eax
0x1400b9ec0  mov     [rsp+0E8h+var_B0], r13
0x1400b9ec5  mov     edx, 40000h
0x1400b9eca  mov     [rsp+0E8h+var_B8], r13
0x1400b9ecf  mov     qword ptr [rsp+0E8h+Priority], r13
0x1400b9ed4  mov     qword ptr [rsp+0E8h+BugCheckOnFailure], rax
0x1400b9ed9  call    DxgkLogInternalTriageEvent
0x1400b9ede  lea     rcx, [rsp+0E8h+var_98]; this
0x1400b9ee3  call    ??1DXGAUTOMUTEX@@QEAA@XZ; DXGAUTOMUTEX::~DXGAUTOMUTEX(void)
0x1400b9ee8  jmp     loc_1400B9E5C
0x1400b9eed  lea     rdx, [rdi+70h]
0x1400b9ef1  mov     rax, [rdx]
0x1400b9ef4  cmp     rax, rdx
0x1400b9ef7  jz      short loc_1400B9F08
0x1400b9ef9  cmp     [rax-28h], rbx
0x1400b9efd  jz      short loc_1400B9F04
0x1400b9eff  mov     rax, [rax]
0x1400b9f02  jmp     short loc_1400B9EF4
0x1400b9f04  lea     r14, [rax-30h]
0x1400b9f08  test    r14, r14
0x1400b9f0b  jnz     short loc_1400B9F29
0x1400b9f0d  mov     ecx, ebp
0x1400b9f0f  call    cs:__imp_WdLogSingleEntry0
0x1400b9f16  nop     dword ptr [rax+rax+00h]
0x1400b9f1b  mov     eax, 751Eh
0x1400b9f20  lea     r9, aUnableToFindLo; "unable to find local allocation in Inva"...
0x1400b9f27  jmp     short loc_1400B9EBA
0x1400b9f29  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400b9f30  mov     rbp, qword ptr [rsp+0E8h+Length]
0x1400b9f38  cmp     [rax], r13b
0x1400b9f3b  jz      short loc_1400B9F5F
0x1400b9f3d  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400b9f44  nop     dword ptr [rax+rax+00h]
0x1400b9f49  mov     [rax+18h], rsi
0x1400b9f4d  mov     [rax+20h], r12
0x1400b9f51  mov     [rax+28h], rbp
0x1400b9f55  mov     cs:WdLogGlobalForLineNumber, 7527h
0x1400b9f5f  test    rbp, rbp
0x1400b9f62  jnz     short loc_1400B9F68
0x1400b9f64  mov     rbp, [r15+10h]
0x1400b9f68  mov     rdx, [r15+10h]
0x1400b9f6c  cmp     r12, rdx
0x1400b9f6f  jb      short loc_1400B9F9C
0x1400b9f71  mov     ecx, 1
0x1400b9f76  call    cs:__imp_WdLogSingleEntry1
0x1400b9f7d  nop     dword ptr [rax+rax+00h]
0x1400b9f82  mov     cs:WdLogGlobalForLineNumber, 7535h
0x1400b9f8c  lea     r9, aOffsetPassedTo; "Offset passed to InvalidateCache must n"...
0x1400b9f93  mov     rax, [r15+10h]
0x1400b9f97  jmp     loc_1400B9EC0
0x1400b9f9c  mov     rax, rdx
0x1400b9f9f  sub     rax, r12
0x1400b9fa2  cmp     rbp, rax
0x1400b9fa5  jbe     short loc_1400B9FD2
0x1400b9fa7  mov     ecx, 1
0x1400b9fac  call    cs:__imp_WdLogSingleEntry1
0x1400b9fb3  nop     dword ptr [rax+rax+00h]
0x1400b9fb8  mov     cs:WdLogGlobalForLineNumber, 753Dh
0x1400b9fc2  lea     r9, aLengthPassedTo; "Length passed to InvalidateCache must n"...
0x1400b9fc9  mov     rax, [r15+10h]
0x1400b9fcd  jmp     loc_1400B9EC0
0x1400b9fd2  mov     eax, [rdi+1Ch]
0x1400b9fd5  test    al, 50h
0x1400b9fd7  jnz     short loc_1400B9FF9
0x1400b9fd9  mov     rax, [rdi+188h]
0x1400b9fe0  mov     r8b, r13b
0x1400b9fe3  mov     ecx, [rax]
0x1400b9fe5  test    cl, 8
0x1400b9fe8  jz      short loc_1400B9FF3
0x1400b9fea  mov     rsi, [rdi+0E0h]
0x1400b9ff1  jmp     short loc_1400BA043
0x1400b9ff3  mov     rsi, [r14+10h]
0x1400b9ff7  jmp     short loc_1400BA043
0x1400b9ff9  mov     rcx, [rdi+0F0h]
0x1400ba000  mov     eax, [rcx+20h]
0x1400ba003  test    al, 3
0x1400ba005  jnz     short loc_1400BA00C
0x1400ba007  mov     rsi, r13
0x1400ba00a  jmp     short loc_1400BA040
0x1400ba00c  mov     rcx, [rcx]; MemoryDescriptorList
0x1400ba00f  test    byte ptr [rcx+0Ah], 5
0x1400ba013  jz      short loc_1400BA01B
0x1400ba015  mov     rsi, [rcx+18h]
0x1400ba019  jmp     short loc_1400BA040
0x1400ba01b  xor     r9d, r9d; RequestedAddress
0x1400ba01e  mov     [rsp+0E8h+Priority], 40000010h; Priority
0x1400ba026  xor     edx, edx; AccessMode
0x1400ba028  mov     [rsp+0E8h+BugCheckOnFailure], r13d; BugCheckOnFailure
0x1400ba02d  lea     r8d, [r9+1]; CacheType
0x1400ba031  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400ba038  nop     dword ptr [rax+rax+00h]
0x1400ba03d  mov     rsi, rax
0x1400ba040  mov     r8b, 1; bool
0x1400ba043  test    rsi, rsi
0x1400ba046  jnz     short loc_1400BA090
0x1400ba048  mov     rdx, rdi
0x1400ba04b  lea     ecx, [rsi+1]
0x1400ba04e  call    cs:__imp_WdLogSingleEntry1
0x1400ba055  nop     dword ptr [rax+rax+00h]
0x1400ba05a  mov     [rsp+0E8h+var_B0], r13
0x1400ba05f  lea     r9, aVidmmGlobalAll; "VIDMM_GLOBAL_ALLOC 0x%.16I64x is not CP"...
0x1400ba066  mov     [rsp+0E8h+var_B8], r13
0x1400ba06b  mov     edx, 40000h
0x1400ba070  mov     qword ptr [rsp+0E8h+Priority], r13
0x1400ba075  mov     qword ptr [rsp+0E8h+BugCheckOnFailure], rdi
0x1400ba07a  mov     cs:WdLogGlobalForLineNumber, 756Fh
0x1400ba084  call    DxgkLogInternalTriageEvent
0x1400ba089  mov     ebx, 0C000000Dh
0x1400ba08e  jmp     short loc_1400BA0C7
0x1400ba090  cmp     dword ptr [rdi+48h], 2
0x1400ba094  mov     ebx, r13d
0x1400ba097  jnz     short loc_1400BA0C7
0x1400ba099  mov     eax, [r15+40h]
0x1400ba09d  test    al, 4
0x1400ba09f  jz      short loc_1400BA0C7
0x1400ba0a1  mov     rdx, [r14+8]; struct VIDMM_PROCESS *
0x1400ba0a5  lea     rcx, [rsp+0E8h+var_88]; this
0x1400ba0aa  call    ??0VIDMM_PROCESS_AUTOATTACH@@QEAA@PEAVVIDMM_PROCESS@@_N@Z; VIDMM_PROCESS_AUTOATTACH::VIDMM_PROCESS_AUTOATTACH(VIDMM_PROCESS *,bool)
0x1400ba0af  lea     rcx, [r12+rsi]; BaseAddress
0x1400ba0b3  mov     rdx, rbp; Length
0x1400ba0b6  call    VidMmFlushCpuCacheWorker
0x1400ba0bb  lea     rcx, [rsp+0E8h+var_88]; this
0x1400ba0c0  mov     ebx, eax
0x1400ba0c2  call    ??1VIDMM_PROCESS_AUTOATTACH@@QEAA@XZ; VIDMM_PROCESS_AUTOATTACH::~VIDMM_PROCESS_AUTOATTACH(void)
0x1400ba0c7  lea     rcx, [rsp+0E8h+var_98]; this
0x1400ba0cc  call    ??1DXGAUTOMUTEX@@QEAA@XZ; DXGAUTOMUTEX::~DXGAUTOMUTEX(void)
0x1400ba0d1  mov     eax, ebx
0x1400ba0d3  mov     rcx, [rsp+0E8h+var_48]
0x1400ba0db  xor     rcx, rsp; StackCookie
0x1400ba0de  call    __security_check_cookie
0x1400ba0e3  mov     rbx, [rsp+0E8h+arg_0]
0x1400ba0eb  add     rsp, 0B0h
0x1400ba0f2  pop     r15
0x1400ba0f4  pop     r14
0x1400ba0f6  pop     r13
0x1400ba0f8  pop     r12
0x1400ba0fa  pop     rdi
0x1400ba0fb  pop     rsi
0x1400ba0fc  pop     rbp
0x1400ba0fd  retn
```
