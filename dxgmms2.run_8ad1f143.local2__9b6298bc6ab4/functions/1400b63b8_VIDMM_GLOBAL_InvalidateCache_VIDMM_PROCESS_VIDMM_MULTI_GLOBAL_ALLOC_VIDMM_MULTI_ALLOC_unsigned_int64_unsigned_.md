# VIDMM_GLOBAL::InvalidateCache(VIDMM_PROCESS *,VIDMM_MULTI_GLOBAL_ALLOC *,VIDMM_MULTI_ALLOC *,unsigned __int64,unsigned __int64)

- ea: `0x1400b63b8`
- end: `0x1400b6727`
- name: `?InvalidateCache@VIDMM_GLOBAL@@QEAAJPEAVVIDMM_PROCESS@@PEAUVIDMM_MULTI_GLOBAL_ALLOC@@PEAUVIDMM_MULTI_ALLOC@@_K3@Z`
- size: `879`
- prototype: `__int64 __fastcall(VIDMM_GLOBAL *__hidden this, struct VIDMM_PROCESS *, struct VIDMM_MULTI_GLOBAL_ALLOC *, struct VIDMM_MULTI_ALLOC *, unsigned __int64, ULONG Length)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140046fa0`

## callees

- `0x1400045ec`
- `0x14002faf0`
- `0x14002fd70`
- `0x1400335c4`
- `0x1400336b8`
- `0x14003ba24`
- `0x140058680`
- `0x1400b1f94`
- `0x1400b63b8`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400b6659`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400b6659`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400b6565`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400b6565`
- `watchdog!WdLogSingleEntry0` at `0x1400b641f`
- `watchdog!WdLogSingleEntry0` at `0x1400b6448`
- `watchdog!WdLogSingleEntry0` at `0x1400b64ca`
- `watchdog!WdLogSingleEntry0` at `0x1400b6537`
- `watchdog!WdLogSingleEntry0` at `0x1400b641f`
- `watchdog!WdLogSingleEntry0` at `0x1400b6448`
- `watchdog!WdLogSingleEntry0` at `0x1400b64ca`
- `watchdog!WdLogSingleEntry0` at `0x1400b6537`
- `watchdog!WdLogSingleEntry1` at `0x1400b659e`
- `watchdog!WdLogSingleEntry1` at `0x1400b65d4`
- `watchdog!WdLogSingleEntry1` at `0x1400b6676`
- `watchdog!WdLogSingleEntry1` at `0x1400b659e`
- `watchdog!WdLogSingleEntry1` at `0x1400b65d4`
- `watchdog!WdLogSingleEntry1` at `0x1400b6676`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400b6551`

## string_xrefs

- `0x1400b6459`: `Both pAlloc and pGlobalAlloc null in InvalidateCache`
- `0x1400b64db`: `pProcess is NULL when pAlloc is NULL in InvalidateCache`
- `0x1400b6548`: `unable to find local allocation in InvalidateCache`
- `0x1400b65b4`: `Offset passed to InvalidateCache must not overflow the allocation. SizeInSegment=%I64d`
- `0x1400b65ea`: `Length passed to InvalidateCache must not overflow the allocation. SizeInSegment=%I64d`

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
  _QWORD *v14; // rdx
  __int64 v15; // rcx
  int v16; // ecx
  int v17; // r8d
  __int64 v18; // rax
  const wchar_t *v19; // r9
  _QWORD *i; // rax
  unsigned __int64 v21; // rbp
  _QWORD *v22; // rax
  unsigned __int64 v23; // rdx
  bool v24; // r8
  char *v25; // rsi
  __int64 *v26; // rcx
  __int64 v27; // rcx
  int v28; // ecx
  int v29; // r8d
  unsigned int v30; // ebx
  __int64 v31; // r8
  _BYTE v32[16]; // [rsp+50h] [rbp-98h] BYREF
  _BYTE v33[64]; // [rsp+60h] [rbp-88h] BYREF

  v7 = a3;
  if ( !*((_BYTE *)this + 3203) && (!a2 || (*(_DWORD *)(*((_QWORD *)a2 + 9) + 408LL) & 0x1000) == 0) )
  {
    WdLogSingleEntry0(4);
    result = 0;
    WdLogGlobalForLineNumber = 29664;
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
      WdLogGlobalForLineNumber = 29675;
      DxgkLogInternalTriageEvent(
        v10,
        0x40000,
        v11,
        (unsigned int)L"Both pAlloc and pGlobalAlloc null in InvalidateCache",
        29675,
        0,
        0,
        0);
      return 3221225485LL;
    }
    v12 = 0;
  }
  v13 = *(_QWORD *)v7;
  DXGAUTOMUTEX::DXGAUTOMUTEX((DXGAUTOMUTEX *)v32, (struct VIDMM_MULTI_GLOBAL_ALLOC *)((char *)v7 + 136), 0);
  DXGAUTOMUTEX::Acquire((DXGAUTOMUTEX *)v32);
  if ( !a4 )
  {
    if ( !a2 )
    {
      WdLogSingleEntry0(1);
      v18 = 29699;
      v19 = L"pProcess is NULL when pAlloc is NULL in InvalidateCache";
LABEL_14:
      WdLogGlobalForLineNumber = v18;
LABEL_15:
      DxgkLogInternalTriageEvent(v16, 0x40000, v17, (_DWORD)v19, v18, 0, 0, 0);
      DXGAUTOMUTEX::~DXGAUTOMUTEX((DXGAUTOMUTEX *)v32);
      return 3221225485LL;
    }
    v14 = (_QWORD *)((char *)v7 + 112);
    for ( i = (_QWORD *)*((_QWORD *)v7 + 14); i != v14; i = (_QWORD *)*i )
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
      v18 = 29720;
      v19 = L"unable to find local allocation in InvalidateCache";
      goto LABEL_14;
    }
  }
  v21 = Length;
  if ( g_IsInternalReleaseOrDbg )
  {
    v22 = (_QWORD *)WdLogNewEntry5_WdTrace(v15, v14);
    v22[3] = a4;
    v22[4] = a5;
    v22[5] = Length;
    WdLogGlobalForLineNumber = 29729;
  }
  if ( !Length )
    v21 = *(_QWORD *)(v13 + 16);
  v23 = *(_QWORD *)(v13 + 16);
  if ( a5 >= v23 )
  {
    WdLogSingleEntry1(1, v23);
    WdLogGlobalForLineNumber = 29743;
    v19 = L"Offset passed to InvalidateCache must not overflow the allocation. SizeInSegment=%I64d";
    v18 = *(_QWORD *)(v13 + 16);
    goto LABEL_15;
  }
  if ( v21 > v23 - a5 )
  {
    WdLogSingleEntry1(1, v23);
    WdLogGlobalForLineNumber = 29751;
    v19 = L"Length passed to InvalidateCache must not overflow the allocation. SizeInSegment=%I64d";
    v18 = *(_QWORD *)(v13 + 16);
    goto LABEL_15;
  }
  if ( (*((_DWORD *)v7 + 7) & 0x50) != 0 )
  {
    v26 = (__int64 *)*((_QWORD *)v7 + 30);
    if ( (v26[4] & 3) != 0 )
    {
      v27 = *v26;
      if ( (*(_BYTE *)(v27 + 10) & 5) != 0 )
        v25 = *(char **)(v27 + 24);
      else
        v25 = (char *)MmMapLockedPagesSpecifyCache((PMDL)v27, 0, MmCached, 0, 0, 0x40000010u);
    }
    else
    {
      v25 = 0;
    }
    v24 = 1;
  }
  else
  {
    v24 = 0;
    if ( (**((_DWORD **)v7 + 48) & 8) != 0 )
      v25 = (char *)*((_QWORD *)v7 + 28);
    else
      v25 = (char *)v12[2];
  }
  if ( v25 )
  {
    v30 = 0;
    if ( *((_DWORD *)v7 + 18) == 2 && (*(_DWORD *)(v13 + 64) & 4) != 0 )
    {
      VIDMM_PROCESS_AUTOATTACH::VIDMM_PROCESS_AUTOATTACH((VIDMM_PROCESS_AUTOATTACH *)v33, v12[1], v24);
      v30 = VidMmFlushCpuCacheWorker(&v25[a5], v21, v31);
      VIDMM_PROCESS_AUTOATTACH::~VIDMM_PROCESS_AUTOATTACH((VIDMM_PROCESS_AUTOATTACH *)v33);
    }
  }
  else
  {
    WdLogSingleEntry1(1, v7);
    WdLogGlobalForLineNumber = 29801;
    DxgkLogInternalTriageEvent(
      v28,
      0x40000,
      v29,
      (unsigned int)L"VIDMM_GLOBAL_ALLOC 0x%.16I64x is not CPU visible or has no mapped virtual address",
      (__int64)v7,
      0,
      0,
      0);
    v30 = -1073741811;
  }
  DXGAUTOMUTEX::~DXGAUTOMUTEX((DXGAUTOMUTEX *)v32);
  return v30;
}

```

## disassembly

```asm
0x1400b63b8  mov     [rsp+arg_0], rbx
0x1400b63bd  push    rbp
0x1400b63be  push    rsi
0x1400b63bf  push    rdi
0x1400b63c0  push    r12
0x1400b63c2  push    r13
0x1400b63c4  push    r14
0x1400b63c6  push    r15
0x1400b63c8  sub     rsp, 0B0h
0x1400b63cf  mov     rax, cs:__security_cookie
0x1400b63d6  xor     rax, rsp
0x1400b63d9  mov     [rsp+0E8h+var_48], rax
0x1400b63e1  mov     r12, [rsp+0E8h+arg_20]
0x1400b63e9  xor     r13d, r13d
0x1400b63ec  mov     rsi, r9
0x1400b63ef  mov     rdi, r8
0x1400b63f2  mov     rbx, rdx
0x1400b63f5  mov     ebp, 1
0x1400b63fa  cmp     [rcx+0C83h], r13b
0x1400b6401  jnz     short loc_1400B643C
0x1400b6403  test    rdx, rdx
0x1400b6406  jz      short loc_1400B641A
0x1400b6408  mov     rax, [rdx+48h]
0x1400b640c  mov     ecx, [rax+198h]
0x1400b6412  shr     ecx, 0Ch
0x1400b6415  test    bpl, cl
0x1400b6418  jnz     short loc_1400B643C
0x1400b641a  mov     ecx, 4
0x1400b641f  call    cs:__imp_WdLogSingleEntry0
0x1400b6426  nop     dword ptr [rax+rax+00h]
0x1400b642b  xor     eax, eax
0x1400b642d  mov     cs:WdLogGlobalForLineNumber, 73E0h
0x1400b6437  jmp     loc_1400B66FB
0x1400b643c  test    rsi, rsi
0x1400b643f  jnz     short loc_1400B6493
0x1400b6441  test    r8, r8
0x1400b6444  jnz     short loc_1400B648E
0x1400b6446  mov     ecx, ebp
0x1400b6448  call    cs:__imp_WdLogSingleEntry0
0x1400b644f  nop     dword ptr [rax+rax+00h]
0x1400b6454  mov     [rsp+0E8h+var_B0], r13
0x1400b6459  lea     r9, aBothPallocAndP; "Both pAlloc and pGlobalAlloc null in In"...
0x1400b6460  mov     eax, 73EBh
0x1400b6465  mov     [rsp+0E8h+var_B8], r13
0x1400b646a  mov     qword ptr [rsp+0E8h+Priority], r13
0x1400b646f  mov     edx, 40000h
0x1400b6474  mov     cs:WdLogGlobalForLineNumber, eax
0x1400b647a  mov     qword ptr [rsp+0E8h+BugCheckOnFailure], rax
0x1400b647f  call    DxgkLogInternalTriageEvent
0x1400b6484  mov     eax, 0C000000Dh
0x1400b6489  jmp     loc_1400B66FB
0x1400b648e  mov     r14, r13
0x1400b6491  jmp     short loc_1400B6499
0x1400b6493  mov     r14, [r9]
0x1400b6496  mov     rdi, [r14]
0x1400b6499  mov     r15, [rdi]
0x1400b649c  lea     rdx, [rdi+88h]; struct DXGFASTMUTEX *
0x1400b64a3  xor     r8d, r8d; unsigned __int8
0x1400b64a6  lea     rcx, [rsp+0E8h+var_98]; this
0x1400b64ab  call    ??0DXGAUTOMUTEX@@QEAA@QEAVDXGFASTMUTEX@@E@Z; DXGAUTOMUTEX::DXGAUTOMUTEX(DXGFASTMUTEX * const,uchar)
0x1400b64b0  lea     rcx, [rsp+0E8h+var_98]; this
0x1400b64b5  call    ?Acquire@DXGAUTOMUTEX@@QEAAXXZ; DXGAUTOMUTEX::Acquire(void)
0x1400b64ba  test    rsi, rsi
0x1400b64bd  jnz     loc_1400B6551
0x1400b64c3  test    rbx, rbx
0x1400b64c6  jnz     short loc_1400B6515
0x1400b64c8  mov     ecx, ebp
0x1400b64ca  call    cs:__imp_WdLogSingleEntry0
0x1400b64d1  nop     dword ptr [rax+rax+00h]
0x1400b64d6  mov     eax, 7403h
0x1400b64db  lea     r9, aPprocessIsNull; "pProcess is NULL when pAlloc is NULL in"...
0x1400b64e2  mov     cs:WdLogGlobalForLineNumber, eax
0x1400b64e8  mov     [rsp+0E8h+var_B0], r13
0x1400b64ed  mov     edx, 40000h
0x1400b64f2  mov     [rsp+0E8h+var_B8], r13
0x1400b64f7  mov     qword ptr [rsp+0E8h+Priority], r13
0x1400b64fc  mov     qword ptr [rsp+0E8h+BugCheckOnFailure], rax
0x1400b6501  call    DxgkLogInternalTriageEvent
0x1400b6506  lea     rcx, [rsp+0E8h+var_98]; this
0x1400b650b  call    ??1DXGAUTOMUTEX@@QEAA@XZ; DXGAUTOMUTEX::~DXGAUTOMUTEX(void)
0x1400b6510  jmp     loc_1400B6484
0x1400b6515  lea     rdx, [rdi+70h]
0x1400b6519  mov     rax, [rdx]
0x1400b651c  cmp     rax, rdx
0x1400b651f  jz      short loc_1400B6530
0x1400b6521  cmp     [rax-28h], rbx
0x1400b6525  jz      short loc_1400B652C
0x1400b6527  mov     rax, [rax]
0x1400b652a  jmp     short loc_1400B651C
0x1400b652c  lea     r14, [rax-30h]
0x1400b6530  test    r14, r14
0x1400b6533  jnz     short loc_1400B6551
0x1400b6535  mov     ecx, ebp
0x1400b6537  call    cs:__imp_WdLogSingleEntry0
0x1400b653e  nop     dword ptr [rax+rax+00h]
0x1400b6543  mov     eax, 7418h
0x1400b6548  lea     r9, aUnableToFindLo; "unable to find local allocation in Inva"...
0x1400b654f  jmp     short loc_1400B64E2
0x1400b6551  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400b6558  mov     rbp, qword ptr [rsp+0E8h+Length]
0x1400b6560  cmp     [rax], r13b
0x1400b6563  jz      short loc_1400B6587
0x1400b6565  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400b656c  nop     dword ptr [rax+rax+00h]
0x1400b6571  mov     [rax+18h], rsi
0x1400b6575  mov     [rax+20h], r12
0x1400b6579  mov     [rax+28h], rbp
0x1400b657d  mov     cs:WdLogGlobalForLineNumber, 7421h
0x1400b6587  test    rbp, rbp
0x1400b658a  jnz     short loc_1400B6590
0x1400b658c  mov     rbp, [r15+10h]
0x1400b6590  mov     rdx, [r15+10h]
0x1400b6594  cmp     r12, rdx
0x1400b6597  jb      short loc_1400B65C4
0x1400b6599  mov     ecx, 1
0x1400b659e  call    cs:__imp_WdLogSingleEntry1
0x1400b65a5  nop     dword ptr [rax+rax+00h]
0x1400b65aa  mov     cs:WdLogGlobalForLineNumber, 742Fh
0x1400b65b4  lea     r9, aOffsetPassedTo; "Offset passed to InvalidateCache must n"...
0x1400b65bb  mov     rax, [r15+10h]
0x1400b65bf  jmp     loc_1400B64E8
0x1400b65c4  mov     rax, rdx
0x1400b65c7  sub     rax, r12
0x1400b65ca  cmp     rbp, rax
0x1400b65cd  jbe     short loc_1400B65FA
0x1400b65cf  mov     ecx, 1
0x1400b65d4  call    cs:__imp_WdLogSingleEntry1
0x1400b65db  nop     dword ptr [rax+rax+00h]
0x1400b65e0  mov     cs:WdLogGlobalForLineNumber, 7437h
0x1400b65ea  lea     r9, aLengthPassedTo; "Length passed to InvalidateCache must n"...
0x1400b65f1  mov     rax, [r15+10h]
0x1400b65f5  jmp     loc_1400B64E8
0x1400b65fa  mov     eax, [rdi+1Ch]
0x1400b65fd  test    al, 50h
0x1400b65ff  jnz     short loc_1400B6621
0x1400b6601  mov     rax, [rdi+180h]
0x1400b6608  mov     r8b, r13b
0x1400b660b  mov     ecx, [rax]
0x1400b660d  test    cl, 8
0x1400b6610  jz      short loc_1400B661B
0x1400b6612  mov     rsi, [rdi+0E0h]
0x1400b6619  jmp     short loc_1400B666B
0x1400b661b  mov     rsi, [r14+10h]
0x1400b661f  jmp     short loc_1400B666B
0x1400b6621  mov     rcx, [rdi+0F0h]
0x1400b6628  mov     eax, [rcx+20h]
0x1400b662b  test    al, 3
0x1400b662d  jnz     short loc_1400B6634
0x1400b662f  mov     rsi, r13
0x1400b6632  jmp     short loc_1400B6668
0x1400b6634  mov     rcx, [rcx]; MemoryDescriptorList
0x1400b6637  test    byte ptr [rcx+0Ah], 5
0x1400b663b  jz      short loc_1400B6643
0x1400b663d  mov     rsi, [rcx+18h]
0x1400b6641  jmp     short loc_1400B6668
0x1400b6643  xor     r9d, r9d; RequestedAddress
0x1400b6646  mov     [rsp+0E8h+Priority], 40000010h; Priority
0x1400b664e  xor     edx, edx; AccessMode
0x1400b6650  mov     [rsp+0E8h+BugCheckOnFailure], r13d; BugCheckOnFailure
0x1400b6655  lea     r8d, [r9+1]; CacheType
0x1400b6659  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400b6660  nop     dword ptr [rax+rax+00h]
0x1400b6665  mov     rsi, rax
0x1400b6668  mov     r8b, 1; bool
0x1400b666b  test    rsi, rsi
0x1400b666e  jnz     short loc_1400B66B8
0x1400b6670  mov     rdx, rdi
0x1400b6673  lea     ecx, [rsi+1]
0x1400b6676  call    cs:__imp_WdLogSingleEntry1
0x1400b667d  nop     dword ptr [rax+rax+00h]
0x1400b6682  mov     [rsp+0E8h+var_B0], r13
0x1400b6687  lea     r9, aVidmmGlobalAll; "VIDMM_GLOBAL_ALLOC 0x%.16I64x is not CP"...
0x1400b668e  mov     [rsp+0E8h+var_B8], r13
0x1400b6693  mov     edx, 40000h
0x1400b6698  mov     qword ptr [rsp+0E8h+Priority], r13
0x1400b669d  mov     qword ptr [rsp+0E8h+BugCheckOnFailure], rdi
0x1400b66a2  mov     cs:WdLogGlobalForLineNumber, 7469h
0x1400b66ac  call    DxgkLogInternalTriageEvent
0x1400b66b1  mov     ebx, 0C000000Dh
0x1400b66b6  jmp     short loc_1400B66EF
0x1400b66b8  cmp     dword ptr [rdi+48h], 2
0x1400b66bc  mov     ebx, r13d
0x1400b66bf  jnz     short loc_1400B66EF
0x1400b66c1  mov     eax, [r15+40h]
0x1400b66c5  test    al, 4
0x1400b66c7  jz      short loc_1400B66EF
0x1400b66c9  mov     rdx, [r14+8]; struct VIDMM_PROCESS *
0x1400b66cd  lea     rcx, [rsp+0E8h+var_88]; this
0x1400b66d2  call    ??0VIDMM_PROCESS_AUTOATTACH@@QEAA@PEAVVIDMM_PROCESS@@_N@Z; VIDMM_PROCESS_AUTOATTACH::VIDMM_PROCESS_AUTOATTACH(VIDMM_PROCESS *,bool)
0x1400b66d7  lea     rcx, [r12+rsi]; BaseAddress
0x1400b66db  mov     rdx, rbp; Length
0x1400b66de  call    VidMmFlushCpuCacheWorker
0x1400b66e3  lea     rcx, [rsp+0E8h+var_88]; this
0x1400b66e8  mov     ebx, eax
0x1400b66ea  call    ??1VIDMM_PROCESS_AUTOATTACH@@QEAA@XZ; VIDMM_PROCESS_AUTOATTACH::~VIDMM_PROCESS_AUTOATTACH(void)
0x1400b66ef  lea     rcx, [rsp+0E8h+var_98]; this
0x1400b66f4  call    ??1DXGAUTOMUTEX@@QEAA@XZ; DXGAUTOMUTEX::~DXGAUTOMUTEX(void)
0x1400b66f9  mov     eax, ebx
0x1400b66fb  mov     rcx, [rsp+0E8h+var_48]
0x1400b6703  xor     rcx, rsp; StackCookie
0x1400b6706  call    __security_check_cookie
0x1400b670b  mov     rbx, [rsp+0E8h+arg_0]
0x1400b6713  add     rsp, 0B0h
0x1400b671a  pop     r15
0x1400b671c  pop     r14
0x1400b671e  pop     r13
0x1400b6720  pop     r12
0x1400b6722  pop     rdi
0x1400b6723  pop     rsi
0x1400b6724  pop     rbp
0x1400b6725  retn
```
