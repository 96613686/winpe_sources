# FatDefragDirectory

- ea: `0x140030b04`
- end: `0x140031462`
- name: `FatDefragDirectory`
- size: `2398`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x14003062c`

## callees

- `0x14000c380`
- `0x14000c680`
- `0x140024228`
- `0x14002486c`
- `0x140030b04`
- `0x140031e8c`
- `0x140032dec`
- `0x140049bd4`

## import_xrefs

- `ntoskrnl!RtlClearBits` at `0x14003116d`
- `ntoskrnl!RtlClearBits` at `0x14003116d`
- `ntoskrnl!FsRtlNumberOfRunsInLargeMcb` at `0x140030fcf`
- `ntoskrnl!FsRtlNumberOfRunsInLargeMcb` at `0x140030fcf`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14005cfdc`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14005d006`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14005cfdc`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14005d006`
- `ntoskrnl!FsRtlAddLargeMcbEntry` at `0x140030d9e`
- `ntoskrnl!FsRtlAddLargeMcbEntry` at `0x140030d9e`
- `ntoskrnl!FsRtlGetNextLargeMcbEntry` at `0x14003102a`
- `ntoskrnl!FsRtlGetNextLargeMcbEntry` at `0x14003102a`
- `ntoskrnl!RtlSetBits` at `0x14003114f`
- `ntoskrnl!RtlSetBits` at `0x14003114f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140030c0d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140030c0d`
- `ntoskrnl!ExReleaseResourceLite` at `0x140031435`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005d137`
- `ntoskrnl!ExReleaseResourceLite` at `0x140031435`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005d137`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x140031360`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x14005d03b`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x140031360`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x14005d03b`
- `ntoskrnl!FsRtlInitializeLargeMcb` at `0x140030cca`
- `ntoskrnl!FsRtlInitializeLargeMcb` at `0x140030cca`
- `ntoskrnl!CcUnpinData` at `0x140030df7`
- `ntoskrnl!CcUnpinData` at `0x140031102`
- `ntoskrnl!CcUnpinData` at `0x1400312ec`
- `ntoskrnl!CcUnpinData` at `0x140031326`
- `ntoskrnl!CcUnpinData` at `0x1400313d3`
- `ntoskrnl!CcUnpinData` at `0x140031408`
- `ntoskrnl!CcUnpinData` at `0x14005d0bc`
- `ntoskrnl!CcUnpinData` at `0x14005d0f7`
- `ntoskrnl!CcUnpinData` at `0x140030df7`
- `ntoskrnl!CcUnpinData` at `0x140031102`
- `ntoskrnl!CcUnpinData` at `0x1400312ec`
- `ntoskrnl!CcUnpinData` at `0x140031326`
- `ntoskrnl!CcUnpinData` at `0x1400313d3`
- `ntoskrnl!CcUnpinData` at `0x140031408`
- `ntoskrnl!CcUnpinData` at `0x14005d0bc`
- `ntoskrnl!CcUnpinData` at `0x14005d0f7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003111b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003137b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140031391`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400313af`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400313ef`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005d056`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005d071`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005d08c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005d0de`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003111b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003137b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140031391`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400313af`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400313ef`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005d056`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005d071`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005d08c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005d0de`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140030c88`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140030e46`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140030e90`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140030efc`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140030c88`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140030e46`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140030e90`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140030efc`

## pseudocode

```c
__int64 __fastcall FatDefragDirectory(__int64 a1, __int64 a2, ULONG a3)
{
  unsigned int v3; // r15d
  char *v5; // r12
  _QWORD *v6; // r14
  _QWORD *i; // rbx
  unsigned int v8; // r14d
  WCHAR *PoolWithTag; // rax
  WCHAR *v10; // rbx
  unsigned int v11; // ecx
  size_t v12; // r15
  unsigned int v13; // ecx
  size_t v14; // r15
  unsigned int v15; // ebx
  char *v16; // rax
  char *v17; // r14
  PVOID v18; // rax
  void *v19; // rbx
  unsigned int v20; // r13d
  PVOID *v21; // rax
  PVOID *v22; // rsi
  unsigned int j; // ebx
  unsigned int v24; // r8d
  ULONG v25; // r9d
  void *v26; // rax
  ULONG v27; // eax
  ULONG k; // ebx
  char *v29; // rdx
  char *m; // rax
  unsigned int n; // ebx
  PVOID v32; // rcx
  _QWORD *ii; // r14
  _DWORD *v34; // rbx
  __int64 v35; // r9
  int v36; // ecx
  _QWORD *v37; // rbx
  _QWORD *v38; // rdi
  __int64 v39; // [rsp+30h] [rbp-1C8h]
  SIZE_T NumberOfBytes; // [rsp+64h] [rbp-194h] BYREF
  unsigned int v41; // [rsp+6Ch] [rbp-18Ch]
  PVOID v42; // [rsp+70h] [rbp-188h] BYREF
  unsigned int v43; // [rsp+78h] [rbp-180h]
  __int64 Vbn; // [rsp+80h] [rbp-178h] BYREF
  __int64 v45; // [rsp+88h] [rbp-170h] BYREF
  PVOID Bcb; // [rsp+90h] [rbp-168h] BYREF
  size_t Size; // [rsp+98h] [rbp-160h] BYREF
  ULONG v48; // [rsp+A0h] [rbp-158h]
  int v49; // [rsp+A4h] [rbp-154h]
  PVOID *v50; // [rsp+A8h] [rbp-150h]
  _QWORD *v51; // [rsp+B0h] [rbp-148h] BYREF
  __int64 Lbn; // [rsp+B8h] [rbp-140h] BYREF
  __int64 v53; // [rsp+C0h] [rbp-138h] BYREF
  void *Src; // [rsp+C8h] [rbp-130h]
  void *v55; // [rsp+D0h] [rbp-128h]
  void *v56; // [rsp+D8h] [rbp-120h]
  UNICODE_STRING SourceString; // [rsp+E0h] [rbp-118h] BYREF
  int v58; // [rsp+F0h] [rbp-108h]
  void *v59; // [rsp+F8h] [rbp-100h]
  ULONG NumberToClear[2]; // [rsp+100h] [rbp-F8h]
  char *v61; // [rsp+108h] [rbp-F0h]
  _QWORD **v62; // [rsp+110h] [rbp-E8h]
  int v63; // [rsp+118h] [rbp-E0h]
  char *v64; // [rsp+120h] [rbp-D8h]
  _QWORD *v65; // [rsp+128h] [rbp-D0h]
  __int64 v66; // [rsp+130h] [rbp-C8h]
  _DWORD *v67; // [rsp+138h] [rbp-C0h]
  _QWORD *v68; // [rsp+140h] [rbp-B8h]
  LARGE_MCB Mcb; // [rsp+148h] [rbp-B0h] BYREF
  void *v70; // [rsp+168h] [rbp-90h]
  int v71[34]; // [rsp+170h] [rbp-88h] BYREF

  Bcb = 0;
  v53 = 0;
  *(_QWORD *)&SourceString.Length = 0;
  SourceString.Buffer = 0;
  memset(&Mcb, 0, sizeof(Mcb));
  v3 = *(_DWORD *)(a2 + 24);
  LODWORD(Vbn) = v3;
  if ( v3 > 0x40000 )
    return 0xFFFFFFFFLL;
  v42 = 0;
  v5 = 0;
  v56 = 0;
  Src = 0;
  v55 = 0;
  v50 = 0;
  v43 = 0;
  LODWORD(NumberOfBytes) = 0;
  v67 = (_DWORD *)(a1 + 68);
  v49 = *(_DWORD *)(a1 + 68);
  *(_DWORD *)(a1 + 68) = v49 | 6;
  v6 = (_QWORD *)(a2 + 320);
  v66 = a2 + 320;
  v62 = (_QWORD **)(a2 + 320);
  v65 = (_QWORD *)(a2 + 320);
  for ( i = *(_QWORD **)(a2 + 320); i != v6; i = (_QWORD *)*i )
    ExAcquireResourceExclusiveLite((PERESOURCE)*(i - 19), 1u);
  v8 = 0;
  v58 = 0;
  LODWORD(v45) = 0;
  Size = 0;
  LODWORD(v51) = 0;
  v48 = 0;
  v61 = 0;
  memset(v71, 0, 0x50u);
  v71[1] = 16385;
  SourceString.MaximumLength = 520;
  PoolWithTag = (WCHAR *)ExAllocatePoolWithTag((POOL_TYPE)1041, 0x208u, 0x6E746146u);
  v10 = PoolWithTag;
  if ( !ExPoolZeroingNativelySupported && PoolWithTag )
    memset(PoolWithTag, 0, 0x208u);
  SourceString.Buffer = v10;
  FsRtlInitializeLargeMcb(&Mcb, PagedPool);
  do
  {
    FatLocateDirent(a1, a2, (__int64)v71, v8, 0, (PVOID *)&v53, &Bcb, (unsigned int *)&v45, 0, &SourceString, 0);
    if ( !v53 )
      break;
    Size = 32 * (unsigned int)((((unsigned __int64)SourceString.Length >> 1) + 12) / 0xD) + 32LL;
    FsRtlAddLargeMcbEntry(
      &Mcb,
      (unsigned int)v45 - 32 * (unsigned int)((((unsigned __int64)SourceString.Length >> 1) + 12) / 0xD),
      (unsigned int)v45 - 32 * (unsigned int)((((unsigned __int64)SourceString.Length >> 1) + 12) / 0xD),
      Size);
    LODWORD(NumberOfBytes) = Size + NumberOfBytes;
    v63 = NumberOfBytes;
    v8 = v45 + 32;
    v58 = v45 + 32;
    if ( !v53 )
      break;
  }
  while ( v8 < v3 );
  if ( Bcb )
  {
    CcUnpinData(Bcb);
    Bcb = 0;
  }
  v11 = v3;
  v12 = (unsigned int)NumberOfBytes;
  v13 = v11 - NumberOfBytes;
  *(_QWORD *)NumberToClear = v13 >> 5;
  if ( a3 <= NumberToClear[0] )
  {
    v15 = v13;
    v16 = (char *)ExAllocatePoolWithTag((POOL_TYPE)1041, v13, 0x44746146u);
    v5 = v16;
    if ( !ExPoolZeroingNativelySupported && v16 )
      memset(v16, 0, v15);
    v56 = v5;
    v17 = v5;
    v64 = v5;
    v18 = ExAllocatePoolWithTag((POOL_TYPE)1041, (unsigned int)NumberOfBytes, 0x44746146u);
    v19 = v18;
    Src = v18;
    if ( !ExPoolZeroingNativelySupported && v18 )
      memset(v18, 0, (unsigned int)NumberOfBytes);
    v55 = v19;
    v59 = v19;
    v20 = (unsigned int)(Vbn + 4095) >> 12;
    v43 = v20;
    v21 = (PVOID *)ExAllocatePoolWithTag((POOL_TYPE)1041, 8LL * v20, 0x62746146u);
    v22 = v21;
    if ( !ExPoolZeroingNativelySupported && v21 )
      memset(v21, 0, 8LL * ((unsigned int)(Vbn + 4095) >> 12));
    v50 = v22;
    for ( j = 0; ; ++j )
    {
      v41 = j;
      if ( j >= v20 )
        break;
      v24 = j << 12;
      if ( (j << 12) + 4096 <= (unsigned int)Vbn )
        v25 = 4096;
      else
        v25 = Vbn - v24;
      FatPrepareWriteDirectoryFile(a1, a2, v24, v25, &v22[j], (PVOID *)&v53, v39, 1, &v51);
      v26 = v42;
      if ( !j )
        v26 = (void *)v53;
      v42 = v26;
      v70 = v26;
    }
    v27 = FsRtlNumberOfRunsInLargeMcb(&Mcb);
    LODWORD(v51) = v27;
    for ( k = 0; ; ++k )
    {
      v48 = k;
      if ( k >= v27 )
        break;
      Vbn = 0;
      Lbn = 0;
      FsRtlGetNextLargeMcbEntry(&Mcb, k, &Vbn, &Lbn, (PLONGLONG)&Size);
      v29 = (char *)v42 + Vbn;
      if ( Lbn == -1 )
      {
        memmove(v17, v29, (unsigned int)Size);
        v17 += Size;
        v64 = v17;
      }
      else
      {
        memmove(v59, v29, (unsigned int)Size);
        v59 = (char *)v59 + Size;
      }
      v27 = (unsigned int)v51;
    }
    for ( m = v5; ; m += 32 )
    {
      v61 = m;
      if ( m >= v17 )
        break;
      *m = -27;
    }
    memmove(v42, Src, v12);
    memmove((char *)v42 + v12, v5, v17 - v5);
    if ( v22 )
    {
      for ( n = 0; ; ++n )
      {
        v41 = n;
        if ( n >= v20 )
          break;
        v32 = v22[n];
        if ( v32 )
        {
          CcUnpinData(v32);
          v22[n] = 0;
        }
      }
      ExFreePoolWithTag(v22, 0);
      v50 = 0;
    }
    RtlSetBits((PRTL_BITMAP)(a2 + 400), 0, (unsigned int)NumberOfBytes >> 5);
    RtlClearBits((PRTL_BITMAP)(a2 + 400), (unsigned int)NumberOfBytes >> 5, NumberToClear[0]);
    v14 = v12 >> 5;
    LODWORD(Vbn) = v14;
    FatUnpinRepinnedBcbs(a1);
    for ( ii = *v62; ; ii = (_QWORD *)*ii )
    {
      Lbn = (__int64)ii;
      if ( ii == v65 )
        break;
      v42 = 0;
      LODWORD(NumberOfBytes) = 0;
      *(_QWORD *)NumberToClear = 0;
      v34 = ii - 20;
      v51 = ii - 20;
      v68 = ii - 20;
      if ( (ii[4] & 1) == 0 || v34[57] )
      {
        FatLocateSimpleOemDirent(a1, a2, (__int64)&v42, (__int64)&NumberOfBytes);
        if ( v42 )
        {
          CcUnpinData(v42);
          v42 = 0;
          v36 = v34[61] - v34[62];
          v34[61] = NumberOfBytes;
          v34[62] = NumberOfBytes - v36;
        }
        else
        {
          LOBYTE(v35) = 1;
          FatMarkFcbCondition(0, v34, 2, v35);
        }
      }
    }
  }
  else
  {
    LODWORD(v14) = -1;
  }
  FsRtlUninitializeLargeMcb(&Mcb);
  if ( SourceString.Buffer )
    ExFreePoolWithTag(SourceString.Buffer, 0);
  if ( v5 )
    ExFreePoolWithTag(v5, 0);
  if ( Src )
    ExFreePoolWithTag(Src, 0);
  if ( Bcb )
  {
    CcUnpinData(Bcb);
    Bcb = 0;
  }
  v37 = v62;
  v38 = (_QWORD *)v66;
  while ( 1 )
  {
    v37 = (_QWORD *)*v37;
    if ( v37 == v38 )
      break;
    ExReleaseResourceLite((PERESOURCE)*(v37 - 19));
  }
  *v67 = v49;
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x140030b04  mov     rax, rsp
0x140030b07  mov     [rax+18h], r8d
0x140030b0b  mov     [rax+10h], rdx
0x140030b0f  mov     [rax+8], rcx
0x140030b13  push    rbx
0x140030b14  push    rsi
0x140030b15  push    rdi
0x140030b16  push    r12
0x140030b18  push    r13
0x140030b1a  push    r14
0x140030b1c  push    r15
0x140030b1e  sub     rsp, 1C0h
0x140030b25  xor     edi, edi
0x140030b27  mov     [rax-168h], rdi
0x140030b2e  mov     [rax-138h], rdi
0x140030b35  mov     [rax-118h], rdi
0x140030b3c  mov     [rax-110h], rdi
0x140030b43  xorps   xmm0, xmm0
0x140030b46  movups  xmmword ptr [rax-0B0h], xmm0
0x140030b4d  movups  xmmword ptr [rax-0A0h], xmm0
0x140030b54  mov     r15d, [rdx+18h]
0x140030b58  mov     dword ptr [rsp+1F8h+Vbn], r15d
0x140030b60  cmp     r15d, 40000h
0x140030b67  jbe     short loc_140030B80
0x140030b69  or      eax, 0FFFFFFFFh
0x140030b6c  add     rsp, 1C0h
0x140030b73  pop     r15
0x140030b75  pop     r14
0x140030b77  pop     r13
0x140030b79  pop     r12
0x140030b7b  pop     rdi
0x140030b7c  pop     rsi
0x140030b7d  pop     rbx
0x140030b7e  retn
0x140030b80  mov     [rsp+1F8h+var_198], dil
0x140030b85  mov     [rsp+1F8h+arg_18], dil
0x140030b8d  mov     [rsp+1F8h+var_188], rdi
0x140030b92  mov     r12, rdi
0x140030b95  mov     [rsp+1F8h+var_120], rdi
0x140030b9d  mov     rax, rdi
0x140030ba0  mov     [rsp+1F8h+Src], rax
0x140030ba8  mov     [rsp+1F8h+var_128], rax
0x140030bb0  mov     rsi, rdi
0x140030bb3  mov     [rsp+1F8h+var_150], rdi
0x140030bbb  mov     r13d, edi
0x140030bbe  mov     [rsp+1F8h+var_180], edi
0x140030bc2  mov     dword ptr [rsp+1F8h+NumberOfBytes], edi
0x140030bc6  add     rcx, 44h ; 'D'
0x140030bca  mov     [rsp+1F8h+var_C0], rcx
0x140030bd2  mov     eax, [rcx]
0x140030bd4  mov     [rsp+1F8h+var_154], eax
0x140030bdb  or      eax, 6
0x140030bde  mov     [rcx], eax
0x140030be0  lea     r14, [rdx+140h]
0x140030be7  mov     [rsp+1F8h+var_C8], r14
0x140030bef  mov     [rsp+1F8h+var_E8], r14
0x140030bf7  mov     [rsp+1F8h+var_D0], r14
0x140030bff  mov     rbx, [r14]
0x140030c02  jmp     short loc_140030C1C
0x140030c04  mov     dl, 1; Wait
0x140030c06  mov     rcx, [rbx-98h]; Resource
0x140030c0d  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140030c14  nop     dword ptr [rax+rax+00h]
0x140030c19  mov     rbx, [rbx]
0x140030c1c  cmp     rbx, r14
0x140030c1f  jnz     short loc_140030C04
0x140030c21  mov     r14d, edi
0x140030c24  mov     [rsp+1F8h+var_108], edi
0x140030c2b  mov     dword ptr [rsp+1F8h+var_170], edi
0x140030c32  mov     [rsp+1F8h+Size], rdi
0x140030c3a  mov     dword ptr [rsp+1F8h+var_148], edi
0x140030c41  mov     [rsp+1F8h+var_158], edi
0x140030c48  mov     [rsp+1F8h+var_F0], rdi
0x140030c50  xor     edx, edx; Val
0x140030c52  lea     r8d, [rdx+50h]; Size
0x140030c56  lea     rcx, [rsp+1F8h+var_88]; void *
0x140030c5e  call    memset
0x140030c63  mov     [rsp+1F8h+var_84], 4001h
0x140030c6e  mov     eax, 208h
0x140030c73  mov     [rsp+1F8h+var_118.MaximumLength], ax
0x140030c7b  mov     r8d, 6E746146h; Tag
0x140030c81  mov     edx, eax; NumberOfBytes
0x140030c83  mov     ecx, 411h; PoolType
0x140030c88  call    cs:__imp_ExAllocatePoolWithTag
0x140030c8f  nop     dword ptr [rax+rax+00h]
0x140030c94  mov     rbx, rax
0x140030c97  cmp     cs:ExPoolZeroingNativelySupported, dil
0x140030c9e  jnz     short loc_140030CB5
0x140030ca0  test    rax, rax
0x140030ca3  jz      short loc_140030CB5
0x140030ca5  xor     edx, edx; Val
0x140030ca7  mov     r8d, 208h; Size
0x140030cad  mov     rcx, rax; void *
0x140030cb0  call    memset
0x140030cb5  mov     [rsp+1F8h+var_118.Buffer], rbx
0x140030cbd  mov     edx, 1; PoolType
0x140030cc2  lea     rcx, [rsp+1F8h+Mcb]; Mcb
0x140030cca  call    cs:__imp_FsRtlInitializeLargeMcb
0x140030cd1  nop     dword ptr [rax+rax+00h]
0x140030cd6  mov     [rsp+1F8h+var_198], 1
0x140030cdb  mov     rbx, qword ptr [rsp+1F8h+arg_8]
0x140030ce3  mov     [rsp+1F8h+var_1A8], rdi; __int64
0x140030ce8  lea     rax, [rsp+1F8h+var_118]
0x140030cf0  mov     [rsp+1F8h+SourceString], rax; SourceString
0x140030cf5  mov     [rsp+1F8h+var_1B8], rdi; __int64
0x140030cfa  lea     rax, [rsp+1F8h+var_170]
0x140030d02  mov     [rsp+1F8h+var_1C0], rax; __int64
0x140030d07  lea     rax, [rsp+1F8h+Bcb]
0x140030d0f  mov     [rsp+1F8h+var_1C8], rax; __int64
0x140030d14  lea     rax, [rsp+1F8h+var_138]
0x140030d1c  mov     [rsp+1F8h+var_1D0], rax; __int64
0x140030d21  mov     [rsp+1F8h+SectorCount], rdi; __int64
0x140030d26  mov     r9d, r14d; int
0x140030d29  lea     r8, [rsp+1F8h+var_88]; int
0x140030d31  mov     rdx, rbx; int
0x140030d34  mov     rcx, qword ptr [rsp+1F8h+arg_0]; int
0x140030d3c  call    FatLocateDirent
0x140030d41  mov     rax, [rsp+1F8h+var_138]
0x140030d49  test    rax, rax
0x140030d4c  jz      loc_140030DEA
0x140030d52  movzx   ecx, [rsp+1F8h+var_118.Length]
0x140030d5a  shr     rcx, 1
0x140030d5d  add     rcx, 0Ch
0x140030d61  mov     rax, 4EC4EC4EC4EC4EC5h
0x140030d6b  mul     rcx
0x140030d6e  shr     rdx, 2
0x140030d72  shl     edx, 5
0x140030d75  mov     ecx, dword ptr [rsp+1F8h+var_170]
0x140030d7c  mov     eax, ecx
0x140030d7e  sub     eax, edx
0x140030d80  mov     edx, eax; Vbn
0x140030d82  sub     ecx, eax
0x140030d84  mov     r9d, ecx
0x140030d87  add     r9, 20h ; ' '; SectorCount
0x140030d8b  mov     [rsp+1F8h+Size], r9
0x140030d93  mov     r8d, eax; Lbn
0x140030d96  lea     rcx, [rsp+1F8h+Mcb]; Mcb
0x140030d9e  call    cs:__imp_FsRtlAddLargeMcbEntry
0x140030da5  nop     dword ptr [rax+rax+00h]
0x140030daa  mov     eax, dword ptr [rsp+1F8h+NumberOfBytes]
0x140030dae  add     eax, dword ptr [rsp+1F8h+Size]
0x140030db5  mov     dword ptr [rsp+1F8h+NumberOfBytes], eax
0x140030db9  mov     [rsp+1F8h+var_E0], eax
0x140030dc0  mov     r14d, dword ptr [rsp+1F8h+var_170]
0x140030dc8  add     r14d, 20h ; ' '
0x140030dcc  mov     [rsp+1F8h+var_108], r14d
0x140030dd4  mov     rax, [rsp+1F8h+var_138]
0x140030ddc  test    rax, rax
0x140030ddf  jz      short loc_140030DEA
0x140030de1  cmp     r14d, r15d
0x140030de4  jb      loc_140030CE3
0x140030dea  mov     rcx, [rsp+1F8h+Bcb]; Bcb
0x140030df2  test    rcx, rcx
0x140030df5  jz      short loc_140030E0B
0x140030df7  call    cs:__imp_CcUnpinData
0x140030dfe  nop     dword ptr [rax+rax+00h]
0x140030e03  mov     [rsp+1F8h+Bcb], rdi
0x140030e0b  mov     ecx, r15d
0x140030e0e  mov     r15d, dword ptr [rsp+1F8h+NumberOfBytes]
0x140030e13  sub     ecx, r15d
0x140030e16  mov     eax, ecx
0x140030e18  shr     eax, 5
0x140030e1b  mov     qword ptr [rsp+1F8h+NumberToClear], rax
0x140030e23  cmp     [rsp+1F8h+arg_10], eax
0x140030e2a  jbe     short loc_140030E35
0x140030e2c  or      r15d, 0FFFFFFFFh
0x140030e30  jmp     loc_140031358
0x140030e35  mov     ebx, ecx
0x140030e37  mov     esi, 44746146h
0x140030e3c  mov     r8d, esi; Tag
0x140030e3f  mov     edx, ecx; NumberOfBytes
0x140030e41  mov     ecx, 411h; PoolType
0x140030e46  call    cs:__imp_ExAllocatePoolWithTag
0x140030e4d  nop     dword ptr [rax+rax+00h]
0x140030e52  mov     r12, rax
0x140030e55  cmp     cs:ExPoolZeroingNativelySupported, 0
0x140030e5c  jnz     short loc_140030E70
0x140030e5e  test    rax, rax
0x140030e61  jz      short loc_140030E70
0x140030e63  mov     r8d, ebx; Size
0x140030e66  xor     edx, edx; Val
0x140030e68  mov     rcx, rax; void *
0x140030e6b  call    memset
0x140030e70  mov     [rsp+1F8h+var_120], r12
0x140030e78  mov     r14, r12
0x140030e7b  mov     [rsp+1F8h+var_D8], r12
0x140030e83  mov     r8d, esi; Tag
0x140030e86  mov     rdx, r15; NumberOfBytes
0x140030e89  mov     esi, 411h
0x140030e8e  mov     ecx, esi; PoolType
0x140030e90  call    cs:__imp_ExAllocatePoolWithTag
0x140030e97  nop     dword ptr [rax+rax+00h]
0x140030e9c  mov     rbx, rax
0x140030e9f  mov     [rsp+1F8h+Src], rax
0x140030ea7  cmp     cs:ExPoolZeroingNativelySupported, 0
0x140030eae  jnz     short loc_140030EC2
0x140030eb0  test    rax, rax
0x140030eb3  jz      short loc_140030EC2
0x140030eb5  mov     r8, r15; Size
0x140030eb8  xor     edx, edx; Val
0x140030eba  mov     rcx, rax; void *
0x140030ebd  call    memset
0x140030ec2  mov     [rsp+1F8h+var_128], rbx
0x140030eca  mov     [rsp+1F8h+var_100], rbx
0x140030ed2  mov     r13d, dword ptr [rsp+1F8h+Vbn]
0x140030eda  add     r13d, 0FFFh
0x140030ee1  shr     r13d, 0Ch
0x140030ee5  mov     [rsp+1F8h+var_180], r13d
0x140030eea  mov     ebx, r13d
0x140030eed  shl     rbx, 3
0x140030ef1  mov     r8d, 62746146h; Tag
0x140030ef7  mov     rdx, rbx; NumberOfBytes
0x140030efa  mov     ecx, esi; PoolType
0x140030efc  call    cs:__imp_ExAllocatePoolWithTag
0x140030f03  nop     dword ptr [rax+rax+00h]
0x140030f08  mov     rsi, rax
0x140030f0b  cmp     cs:ExPoolZeroingNativelySupported, 0
0x140030f12  jnz     short loc_140030F26
0x140030f14  test    rax, rax
0x140030f17  jz      short loc_140030F26
0x140030f19  mov     r8, rbx; Size
0x140030f1c  xor     edx, edx; Val
0x140030f1e  mov     rcx, rax; void *
0x140030f21  call    memset
0x140030f26  mov     [rsp+1F8h+var_150], rsi
0x140030f2e  mov     ebx, edi
0x140030f30  mov     [rsp+1F8h+var_18C], ebx
0x140030f34  cmp     ebx, r13d
0x140030f37  jnb     loc_140030FC7
0x140030f3d  mov     r8d, ebx
0x140030f40  shl     r8d, 0Ch
0x140030f44  lea     eax, [r8+1000h]
0x140030f4b  mov     ecx, dword ptr [rsp+1F8h+Vbn]
0x140030f52  cmp     eax, ecx
0x140030f54  jbe     short loc_140030F5E
0x140030f56  mov     r9d, ecx
0x140030f59  sub     r9d, r8d
0x140030f5c  jmp     short loc_140030F64
0x140030f5e  mov     r9d, 1000h
0x140030f64  mov     eax, ebx
0x140030f66  lea     rcx, [rsi+rax*8]
0x140030f6a  lea     rax, [rsp+1F8h+var_148]
0x140030f72  mov     [rsp+1F8h+var_1B8], rax
0x140030f77  mov     byte ptr [rsp+1F8h+var_1C0], 1
0x140030f7c  lea     rax, [rsp+1F8h+var_138]
0x140030f84  mov     [rsp+1F8h+var_1D0], rax
0x140030f89  mov     [rsp+1F8h+SectorCount], rcx
0x140030f8e  mov     rdx, qword ptr [rsp+1F8h+arg_8]
0x140030f96  mov     rcx, qword ptr [rsp+1F8h+arg_0]
0x140030f9e  call    FatPrepareWriteDirectoryFile
0x140030fa3  mov     rax, [rsp+1F8h+var_188]
0x140030fa8  test    ebx, ebx
0x140030faa  cmovz   rax, [rsp+1F8h+var_138]
0x140030fb3  mov     [rsp+1F8h+var_188], rax
0x140030fb8  mov     [rsp+1F8h+var_90], rax
0x140030fc0  inc     ebx
0x140030fc2  jmp     loc_140030F30
0x140030fc7  lea     rcx, [rsp+1F8h+Mcb]; Mcb
0x140030fcf  call    cs:__imp_FsRtlNumberOfRunsInLargeMcb
0x140030fd6  nop     dword ptr [rax+rax+00h]
0x140030fdb  mov     dword ptr [rsp+1F8h+var_148], eax
0x140030fe2  mov     ebx, edi
0x140030fe4  mov     [rsp+1F8h+var_158], ebx
0x140030feb  cmp     ebx, eax
0x140030fed  jnb     loc_1400310A3
0x140030ff3  mov     [rsp+1F8h+Vbn], rdi
0x140030ffb  mov     [rsp+1F8h+Lbn], rdi
0x140031003  lea     rax, [rsp+1F8h+Size]
0x14003100b  mov     [rsp+1F8h+SectorCount], rax; SectorCount
0x140031010  lea     r9, [rsp+1F8h+Lbn]; Lbn
0x140031018  lea     r8, [rsp+1F8h+Vbn]; Vbn
0x140031020  mov     edx, ebx; RunIndex
0x140031022  lea     rcx, [rsp+1F8h+Mcb]; Mcb
0x14003102a  call    cs:__imp_FsRtlGetNextLargeMcbEntry
0x140031031  nop     dword ptr [rax+rax+00h]
0x140031036  mov     r8d, dword ptr [rsp+1F8h+Size]; Size
0x14003103e  mov     rdx, [rsp+1F8h+Vbn]
0x140031046  add     rdx, [rsp+1F8h+var_188]; Src
0x14003104b  cmp     [rsp+1F8h+Lbn], 0FFFFFFFFFFFFFFFFh
0x140031054  jz      short loc_14003107D
0x140031056  mov     rcx, [rsp+1F8h+var_100]; void *
0x14003105e  call    memmove
0x140031063  mov     rax, [rsp+1F8h+var_100]
0x14003106b  add     rax, [rsp+1F8h+Size]
0x140031073  mov     [rsp+1F8h+var_100], rax
0x14003107b  jmp     short loc_140031095
0x14003107d  mov     rcx, r14; void *
0x140031080  call    memmove
0x140031085  add     r14, [rsp+1F8h+Size]
0x14003108d  mov     [rsp+1F8h+var_D8], r14
0x140031095  inc     ebx
0x140031097  mov     eax, dword ptr [rsp+1F8h+var_148]
0x14003109e  jmp     loc_140030FE4
0x1400310a3  mov     rax, r12
0x1400310a6  mov     [rsp+1F8h+var_F0], rax
0x1400310ae  cmp     rax, r14
0x1400310b1  jnb     short loc_1400310BC
0x1400310b3  mov     byte ptr [rax], 0E5h
0x1400310b6  add     rax, 20h ; ' '
0x1400310ba  jmp     short loc_1400310A6
  ... truncated ...
```
