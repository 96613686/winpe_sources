# FatAddEaSet

- ea: `0x140034678`
- end: `0x1400350e7`
- name: `FatAddEaSet`
- size: `2671`
- prototype: `void __fastcall(__int64, __int64, int, __int64, __int64, unsigned __int16 *, _WORD **)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x140035234`

## callees

- `0x1400019b8`
- `0x14000c680`
- `0x140020734`
- `0x1400210d0`
- `0x140022740`
- `0x14002393c`
- `0x140034678`
- `0x1400367d8`
- `0x14003685c`
- `0x140036c78`

## import_xrefs

- `ntoskrnl!CcFlushCache` at `0x140034af4`
- `ntoskrnl!CcFlushCache` at `0x140034af4`
- `ntoskrnl!CcPurgeCacheSection` at `0x140034b1a`
- `ntoskrnl!CcPurgeCacheSection` at `0x140034b1a`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x140034c49`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x140034ca3`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x140034d18`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x140034d67`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x140035079`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x140035093`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x1400350ad`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x1400350c7`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x14005d662`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x14005d67c`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x14005d696`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x14005d6b0`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x140034c49`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x140034ca3`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x140034d18`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x140034d67`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x140035079`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x140035093`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x1400350ad`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x1400350c7`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x14005d662`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x14005d67c`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x14005d696`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x14005d6b0`
- `ntoskrnl!FsRtlInitializeLargeMcb` at `0x1400349d8`
- `ntoskrnl!FsRtlInitializeLargeMcb` at `0x140034a3a`
- `ntoskrnl!FsRtlInitializeLargeMcb` at `0x140034b7a`
- `ntoskrnl!FsRtlInitializeLargeMcb` at `0x140034bda`
- `ntoskrnl!FsRtlInitializeLargeMcb` at `0x140034c62`
- `ntoskrnl!FsRtlInitializeLargeMcb` at `0x140034cbc`
- `ntoskrnl!FsRtlInitializeLargeMcb` at `0x140034d31`
- `ntoskrnl!FsRtlInitializeLargeMcb` at `0x140034d82`
- `ntoskrnl!FsRtlInitializeLargeMcb` at `0x1400349d8`
- `ntoskrnl!FsRtlInitializeLargeMcb` at `0x140034a3a`
- `ntoskrnl!FsRtlInitializeLargeMcb` at `0x140034b7a`
- `ntoskrnl!FsRtlInitializeLargeMcb` at `0x140034bda`
- `ntoskrnl!FsRtlInitializeLargeMcb` at `0x140034c62`
- `ntoskrnl!FsRtlInitializeLargeMcb` at `0x140034cbc`
- `ntoskrnl!FsRtlInitializeLargeMcb` at `0x140034d31`
- `ntoskrnl!FsRtlInitializeLargeMcb` at `0x140034d82`
- `ntoskrnl!CcSetFileSizes` at `0x140034de2`
- `ntoskrnl!CcSetFileSizes` at `0x14005d4d9`
- `ntoskrnl!CcSetFileSizes` at `0x140034de2`
- `ntoskrnl!CcSetFileSizes` at `0x14005d4d9`
- `ntoskrnl!ExRaiseStatus` at `0x140034928`
- `ntoskrnl!ExRaiseStatus` at `0x1400349c1`
- `ntoskrnl!ExRaiseStatus` at `0x140034b43`
- `ntoskrnl!ExRaiseStatus` at `0x140034928`
- `ntoskrnl!ExRaiseStatus` at `0x1400349c1`
- `ntoskrnl!ExRaiseStatus` at `0x140034b43`
- `ntoskrnl!ObfDereferenceObject` at `0x14005d5fe`
- `ntoskrnl!ObfDereferenceObject` at `0x14005d5fe`

## pseudocode

```c
void __fastcall FatAddEaSet(__int64 a1, __int64 a2, int a3, __int64 a4, __int64 a5, unsigned __int16 *a6, _WORD **a7)
{
  unsigned int v9; // esi
  struct _CC_FILE_SIZES *v10; // r13
  int v11; // r12d
  unsigned __int16 v12; // di
  unsigned __int16 *v13; // rdx
  char v14; // dl
  char v15; // cl
  int v16; // ebx
  __int64 v17; // rcx
  __int64 v18; // rcx
  int v19; // eax
  int i; // eax
  bool v21; // zf
  int v22; // eax
  char v23; // al
  __int64 v24; // r9
  DWORD v25; // r8d
  struct _FILE_OBJECT *v26; // rbx
  _WORD *v27; // r15
  _WORD *v28; // rax
  _WORD *k; // rcx
  int v30; // r8d
  _WORD *j; // rdx
  int v33; // edx
  PFILE_OBJECT v35; // r14
  int v36; // esi
  _WORD *m; // rcx
  _WORD *v39; // rcx
  _WORD *v40; // rcx
  int v41; // edx
  __int64 v43; // rcx
  __int64 v44; // rcx
  SIZE_T NumberOfBytes; // [rsp+28h] [rbp-230h]
  SIZE_T NumberOfBytesb; // [rsp+28h] [rbp-230h]
  SIZE_T NumberOfBytesa; // [rsp+28h] [rbp-230h]
  SIZE_T NumberOfBytesc; // [rsp+28h] [rbp-230h]
  SIZE_T NumberOfBytesd; // [rsp+28h] [rbp-230h]
  char v50; // [rsp+40h] [rbp-218h]
  char v51; // [rsp+41h] [rbp-217h]
  char v52; // [rsp+42h] [rbp-216h]
  char v53; // [rsp+43h] [rbp-215h]
  char v54; // [rsp+44h] [rbp-214h]
  unsigned __int16 v55; // [rsp+60h] [rbp-1F8h]
  unsigned int v56; // [rsp+64h] [rbp-1F4h]
  int v57; // [rsp+6Ch] [rbp-1ECh]
  unsigned int v58; // [rsp+70h] [rbp-1E8h]
  int v59; // [rsp+80h] [rbp-1D8h]
  __int64 v60; // [rsp+80h] [rbp-1D8h]
  unsigned int v61; // [rsp+90h] [rbp-1C8h]
  union _LARGE_INTEGER FileOffset; // [rsp+98h] [rbp-1C0h] BYREF
  int v63[2]; // [rsp+A0h] [rbp-1B8h]
  PFILE_OBJECT FileObject; // [rsp+A8h] [rbp-1B0h]
  unsigned int v65; // [rsp+B0h] [rbp-1A8h]
  struct _CC_FILE_SIZES *v66; // [rsp+B8h] [rbp-1A0h]
  PFILE_OBJECT v67; // [rsp+C0h] [rbp-198h]
  LARGE_MCB Mcb; // [rsp+C8h] [rbp-190h] BYREF
  LARGE_MCB v69; // [rsp+E8h] [rbp-170h] BYREF
  LARGE_MCB v70; // [rsp+108h] [rbp-150h] BYREF
  LARGE_MCB v71; // [rsp+128h] [rbp-130h] BYREF
  struct _IO_STATUS_BLOCK IoStatus; // [rsp+148h] [rbp-110h] BYREF
  int v73[24]; // [rsp+160h] [rbp-F8h] BYREF
  int v74[38]; // [rsp+1C0h] [rbp-98h] BYREF

  v9 = 1 << *(_BYTE *)(a2 + 378);
  v65 = v9;
  FileObject = *(PFILE_OBJECT *)(a2 + 776);
  v67 = FileObject;
  v66 = *(struct _CC_FILE_SIZES **)(a2 + 784);
  v10 = v66;
  memset(&Mcb, 0, sizeof(Mcb));
  memset(&v69, 0, sizeof(v69));
  v53 = 0;
  memset(&v70, 0, sizeof(v70));
  v51 = 0;
  memset(&v71, 0, sizeof(v71));
  v52 = 0;
  FileOffset.QuadPart = 0;
  v54 = 0;
  v50 = 0;
  memset(v73, 0, sizeof(v73));
  memset(v74, 0, 0x60u);
  LODWORD(NumberOfBytes) = 512;
  FatPinEaRange(a1, FileObject, (__int64)v66, (__int64)v73, 0, NumberOfBytes, -1073741762);
  *(_QWORD *)v63 = *(_QWORD *)v73;
  v59 = *(unsigned __int16 *)(*(_QWORD *)v73 + 32LL) << *(_BYTE *)(a2 + 378);
  LODWORD(NumberOfBytesb) = v59 - 512;
  FatPinEaRange(a1, FileObject, (__int64)v66, (__int64)v74, 0x200u, NumberOfBytesb, -1073741762);
  v11 = v66[1].FileSize.LowPart >> *(_BYTE *)(a2 + 378);
  v12 = ((unsigned int)(v59 - 512) >> 1) - 1;
  v13 = (unsigned __int16 *)(*(_QWORD *)v74 + 2LL * v12);
  if ( *v13 == 0xFFFF )
    goto LABEL_7;
  while ( v12 )
  {
    if ( *(v13 - 1) == 0xFFFF )
    {
      if ( v12 != 1 )
      {
        v11 = *v13 + *(unsigned __int16 *)(*(_QWORD *)v63 + 2 * ((unsigned __int64)v12 >> 7) + 32);
        v54 = 1;
      }
      --v12;
      --v13;
LABEL_7:
      while ( v12 )
      {
        if ( *(v13 - 1) != 0xFFFF )
          goto LABEL_14;
        --v13;
        --v12;
      }
      break;
    }
    --v12;
    --v13;
  }
  if ( v13[1] == 0xFFFF )
  {
    v12 = 1;
LABEL_14:
    v14 = 0;
  }
  else
  {
    v12 = (unsigned __int16)(v59 - 512) >> 1;
    v14 = 1;
    v50 = 1;
  }
  if ( v12 > 0x77FFu )
  {
    *(_DWORD *)(a1 + 72) = -1073741670;
    ExRaiseStatus(-1073741670);
  }
  v55 = v12 >> 7;
  v15 = *(_BYTE *)(a2 + 378);
  v16 = v11 << v15;
  v63[0] = v11 << v15;
  v58 = -v9 & (v9 + a3 - 1);
  v56 = (v14 != 0 ? v9 : 0) + v58;
  if ( (0xFFFF << v15) - v66[1].FileSize.LowPart < v56 )
  {
    *(_DWORD *)(a1 + 72) = -1073741670;
    ExRaiseStatus(-1073741670);
  }
  FsRtlInitializeLargeMcb(&Mcb, PagedPool);
  FatAllocateDiskSpace(a1, a2, 0, (__int64)&Mcb);
  LOBYTE(v17) = *(_BYTE *)(a2 + 378);
  v61 = v58 >> v17;
  if ( v50 )
  {
    FsRtlInitializeLargeMcb(&v69, PagedPool);
    v53 = 1;
    FatSplitAllocation(a1, a2, (unsigned int)&Mcb, v58, (__int64)&v69);
  }
  FatUnpinEaRange(v17, v73);
  FatUnpinEaRange(v18, v74);
  v19 = v16;
  if ( v50 )
    v19 = v59;
  FileOffset.QuadPart = v19 & 0xFFFFF000;
  IoStatus = 0;
  for ( i = 5; ; i = v57 )
  {
    v21 = i == 1;
    v22 = i - 1;
    v57 = v22;
    if ( v21 )
      break;
    IoStatus.Status = 0;
    CcFlushCache(FileObject->SectionObjectPointer, 0, 0, &IoStatus);
    if ( CcPurgeCacheSection(FileObject->SectionObjectPointer, &FileOffset, 0, 0) )
    {
      v22 = v57;
      break;
    }
  }
  if ( !v22 )
  {
    *(_DWORD *)(a1 + 72) = -1073741797;
    ExRaiseStatus(-1073741797);
  }
  FileOffset.LowPart = v56 + v10[1].FileSize.LowPart;
  if ( v54 )
  {
    FsRtlInitializeLargeMcb(&v70, PagedPool);
    v51 = 1;
    FatSplitAllocation(a1, a2, (_DWORD)v10 + 288, v16, (__int64)&v70);
  }
  v23 = v50;
  if ( v50 )
  {
    if ( v16 != v59 )
    {
      FsRtlInitializeLargeMcb(&v71, PagedPool);
      v52 = 1;
      FatSplitAllocation(a1, a2, (_DWORD)v10 + 288, v59, (__int64)&v71);
      v23 = v50;
    }
    if ( v23 )
    {
      FatMergeAllocation(a1, a2, &v10[12], &v69);
      FsRtlUninitializeLargeMcb(&v69);
      FsRtlInitializeLargeMcb(&v69, PagedPool);
    }
  }
  if ( v52 )
  {
    FatMergeAllocation(a1, a2, &v10[12], &v71);
    FsRtlUninitializeLargeMcb(&v71);
    FsRtlInitializeLargeMcb(&v71, PagedPool);
  }
  if ( v50 )
  {
    LOWORD(v11) = v11 + 1;
    v63[0] = v9 + v16;
  }
  FatMergeAllocation(a1, a2, &v10[12], &Mcb);
  FsRtlUninitializeLargeMcb(&Mcb);
  FsRtlInitializeLargeMcb(&Mcb, PagedPool);
  if ( v51 )
  {
    FatMergeAllocation(a1, a2, &v10[12], &v70);
    FsRtlUninitializeLargeMcb(&v70);
    FsRtlInitializeLargeMcb(&v70, PagedPool);
  }
  v25 = v10[1].FileSize.LowPart + v56;
  v10[1].FileSize.LowPart = v25;
  v10[1].AllocationSize.QuadPart = v10[1].FileSize.QuadPart;
  *(_DWORD *)(a5 + 28) = v25;
  LOBYTE(v24) = 1;
  FatSetDirtyBcb(a1, a4, a2, v24);
  v26 = FileObject;
  CcSetFileSizes(FileObject, v10 + 1);
  memset(v73, 0, sizeof(v73));
  LODWORD(NumberOfBytesa) = 512;
  FatPinEaRange(a1, v26, (__int64)v10, (__int64)v73, 0, NumberOfBytesa, -1073741762);
  v60 = *(_QWORD *)v73;
  memset(v74, 0, 0x60u);
  LODWORD(NumberOfBytesc) = 256;
  FatPinEaRange(a1, v26, (__int64)v10, (__int64)v74, ((2 * v12) & 0xFFFFFF00) + 512, NumberOfBytesc, -1073741762);
  v27 = *(_WORD **)v74;
  LODWORD(NumberOfBytesd) = -v9 & (v9 + a3 - 1);
  FatPinEaRange(a1, v26, (__int64)v10, (__int64)a7, v63[0], NumberOfBytesd, -1073741762);
  v28 = *a7;
  *v28 = 16709;
  v28[1] = v12;
  FatMarkEaRangeDirty(a7, v26, a7);
  v30 = 239 - v55;
  for ( j = (_WORD *)(v60 + 2 * ((unsigned int)v55 + 1 + 16LL)); v30--; ++j )
    *j += v61;
  if ( v50 )
  {
    v33 = 240;
    for ( k = (_WORD *)(v60 + 32); v33--; ++k )
      ++*k;
  }
  v35 = FileObject;
  FatMarkEaRangeDirty(k, FileObject, v73);
  if ( v50 )
  {
    v36 = (v9 >> 1) - 1;
    *v27 = 0;
    for ( m = v27 + 1; v36--; ++m )
      *m = -1;
  }
  v39 = &v27[v12 & 0x7F];
  *v39 = v11 - *(_WORD *)(v60 + 2LL * v55 + 32);
  v40 = v39 + 1;
  v41 = 127 - (v12 & 0x7F);
  while ( v41-- )
  {
    if ( *v40 != 0xFFFF )
      *v40 += v61;
    ++v40;
  }
  FatMarkEaRangeDirty(v40, v35, v74);
  *a6 = v12;
  FatUnpinEaRange(v43, v73);
  FatUnpinEaRange(v44, v74);
  FsRtlUninitializeLargeMcb(&Mcb);
  if ( v53 )
    FsRtlUninitializeLargeMcb(&v69);
  if ( v51 )
    FsRtlUninitializeLargeMcb(&v70);
  if ( v52 )
    FsRtlUninitializeLargeMcb(&v71);
}

```

## disassembly

```asm
0x140034678  mov     rax, rsp
0x14003467b  mov     [rax+20h], r9
0x14003467f  mov     [rax+18h], r8d
0x140034683  mov     [rax+10h], rdx
0x140034687  mov     [rax+8], rcx
0x14003468b  push    rbx
0x14003468c  push    rsi
0x14003468d  push    rdi
0x14003468e  push    r12
0x140034690  push    r13
0x140034692  push    r14
0x140034694  push    r15
0x140034696  sub     rsp, 220h
0x14003469d  mov     r15, rdx
0x1400346a0  mov     r14, rcx
0x1400346a3  mov     cl, [rdx+17Ah]
0x1400346a9  mov     esi, 1
0x1400346ae  shl     esi, cl
0x1400346b0  mov     [rsp+258h+var_1A8], esi
0x1400346b7  xor     ebx, ebx
0x1400346b9  mov     dword ptr [rsp+258h+var_1E8+4], ebx
0x1400346bd  mov     [rsp+258h+var_1F0], ebx
0x1400346c1  mov     rdi, [rdx+308h]
0x1400346c8  mov     [rsp+258h+FileObject], rdi
0x1400346d0  mov     [rsp+258h+var_198], rdi
0x1400346d8  mov     r13, [rdx+310h]
0x1400346df  mov     [rsp+258h+var_1A0], r13
0x1400346e7  xorps   xmm0, xmm0
0x1400346ea  movups  xmmword ptr [rax-190h], xmm0
0x1400346f1  movups  xmmword ptr [rax-180h], xmm0
0x1400346f8  mov     [rsp+258h+var_209], bl
0x1400346fc  mov     [rsp+258h+var_213], bl
0x140034700  mov     [rsp+258h+var_210], bl
0x140034704  movups  xmmword ptr [rax-170h], xmm0
0x14003470b  movups  xmmword ptr [rax-160h], xmm0
0x140034712  mov     [rsp+258h+var_215], bl
0x140034716  mov     [rsp+258h+var_20A], bl
0x14003471a  mov     [rsp+258h+var_20E], bl
0x14003471e  movups  xmmword ptr [rax-150h], xmm0
0x140034725  movups  xmmword ptr [rax-140h], xmm0
0x14003472c  mov     [rsp+258h+var_217], bl
0x140034730  mov     [rsp+258h+var_20C], bl
0x140034734  mov     [rsp+258h+var_211], bl
0x140034738  movups  xmmword ptr [rax-130h], xmm0
0x14003473f  movups  xmmword ptr [rax-120h], xmm0
0x140034746  mov     [rsp+258h+var_216], bl
0x14003474a  mov     [rsp+258h+var_20D], bl
0x14003474e  mov     [rsp+258h+var_20F], bl
0x140034752  mov     [rsp+258h+var_1F4], ebx
0x140034756  mov     [rax-1C0h], rbx
0x14003475d  mov     [rax-1CCh], ebx
0x140034763  mov     [rsp+258h+var_212], bl
0x140034767  mov     [rsp+258h+var_214], bl
0x14003476b  mov     [rsp+258h+var_218], bl
0x14003476f  mov     [rsp+258h+var_20B], bl
0x140034773  lea     r12d, [rbx+60h]
0x140034777  mov     r8d, r12d; Size
0x14003477a  xor     edx, edx; Val
0x14003477c  lea     rcx, [rax-0F8h]; void *
0x140034783  call    memset
0x140034788  mov     r8d, r12d; Size
0x14003478b  xor     edx, edx; Val
0x14003478d  lea     rcx, [rsp+258h+var_98]; void *
0x140034795  call    memset
0x14003479a  nop
0x14003479b  mov     r12d, 0C000003Eh
0x1400347a1  mov     [rsp+258h+Status], r12d; Status
0x1400347a6  mov     dword ptr [rsp+258h+NumberOfBytes], 200h; NumberOfBytes
0x1400347ae  mov     dword ptr [rsp+258h+var_238], ebx; int
0x1400347b2  lea     r9, [rsp+258h+var_F8]; int
0x1400347ba  mov     r8, r13; int
0x1400347bd  mov     rdx, rdi; int
0x1400347c0  mov     rcx, r14; int
0x1400347c3  call    FatPinEaRange
0x1400347c8  mov     rax, qword ptr [rsp+258h+var_F8]
0x1400347d0  mov     qword ptr [rsp+258h+var_1B8], rax
0x1400347d8  movzx   eax, word ptr [rax+20h]
0x1400347dc  mov     cl, [r15+17Ah]
0x1400347e3  shl     eax, cl
0x1400347e5  mov     dword ptr [rsp+258h+var_1D8], eax
0x1400347ec  mov     dword ptr [rsp+258h+var_1E8+4], eax
0x1400347f0  lea     ebx, [rax-200h]
0x1400347f6  mov     [rsp+258h+var_1C8], ebx
0x1400347fd  mov     [rsp+258h+Status], r12d; Status
0x140034802  mov     dword ptr [rsp+258h+NumberOfBytes], ebx; NumberOfBytes
0x140034806  mov     dword ptr [rsp+258h+var_238], 200h; int
0x14003480e  lea     r9, [rsp+258h+var_98]; int
0x140034816  mov     r8, r13; int
0x140034819  mov     rdx, rdi; int
0x14003481c  mov     rcx, r14; int
0x14003481f  call    FatPinEaRange
0x140034824  mov     cl, [r15+17Ah]
0x14003482b  mov     r12d, [r13+20h]
0x14003482f  shr     r12d, cl
0x140034832  mov     [rsp+258h+var_1D0], r12d
0x14003483a  mov     edi, ebx
0x14003483c  shr     edi, 1
0x14003483e  mov     r9d, 1
0x140034844  sub     di, r9w
0x140034848  mov     [rsp+258h+var_208], di
0x14003484d  movzx   ecx, di
0x140034850  mov     rax, qword ptr [rsp+258h+var_98]
0x140034858  lea     rdx, [rax+rcx*2]
0x14003485c  mov     [rsp+258h+var_200], rdx
0x140034861  mov     r10d, 0FFFFh
0x140034867  cmp     [rdx], r10w
0x14003486b  jz      short loc_1400348C1
0x14003486d  xor     ecx, ecx
0x14003486f  test    di, di
0x140034872  jz      loc_140034900
0x140034878  lea     rcx, [rdx-2]
0x14003487c  cmp     [rcx], r10w
0x140034880  jnz     short loc_1400348E5
0x140034882  cmp     di, r9w
0x140034886  jz      short loc_1400348B0
0x140034888  movzx   eax, di
0x14003488b  shr     rax, 7
0x14003488f  mov     r8, qword ptr [rsp+258h+var_1B8]
0x140034897  movzx   r12d, word ptr [r8+rax*2+20h]
0x14003489d  movzx   eax, word ptr [rdx]
0x1400348a0  add     r12d, eax
0x1400348a3  mov     [rsp+258h+var_1D0], r12d
0x1400348ab  mov     [rsp+258h+var_214], r9b
0x1400348b0  add     di, r10w
0x1400348b4  mov     [rsp+258h+var_208], di
0x1400348b9  mov     rdx, rcx
0x1400348bc  mov     [rsp+258h+var_200], rcx
0x1400348c1  xor     ecx, ecx
0x1400348c3  test    di, di
0x1400348c6  jz      short loc_140034900
0x1400348c8  lea     rax, [rdx-2]
0x1400348cc  cmp     [rax], r10w
0x1400348d0  jnz     short loc_1400348FB
0x1400348d2  mov     rdx, rax
0x1400348d5  mov     [rsp+258h+var_200], rax
0x1400348da  add     di, r10w
0x1400348de  mov     [rsp+258h+var_208], di
0x1400348e3  jmp     short loc_1400348C3
0x1400348e5  add     di, r10w
0x1400348e9  mov     [rsp+258h+var_208], di
0x1400348ee  mov     rdx, rcx
0x1400348f1  mov     [rsp+258h+var_200], rcx
0x1400348f6  jmp     loc_14003486D
0x1400348fb  test    di, di
0x1400348fe  jnz     short loc_140034911
0x140034900  cmp     [rdx+2], r10w
0x140034905  jnz     short loc_140034934
0x140034907  movzx   edi, r9w
0x14003490b  mov     [rsp+258h+var_208], r9w
0x140034911  mov     dl, [rsp+258h+var_218]
0x140034915  mov     eax, 77FFh
0x14003491a  cmp     di, ax
0x14003491d  jbe     short loc_140034948
0x14003491f  mov     ecx, 0C000009Ah; Status
0x140034924  mov     [r14+48h], ecx
0x140034928  call    cs:__imp_ExRaiseStatus
0x140034934  shr     bx, 1
0x140034937  movzx   edi, bx
0x14003493a  mov     [rsp+258h+var_208], bx
0x14003493f  mov     dl, r9b
0x140034942  mov     [rsp+258h+var_218], dl
0x140034946  jmp     short loc_140034915
0x140034948  movzx   eax, di
0x14003494b  shr     ax, 7
0x14003494f  mov     [rsp+258h+var_1F8], ax
0x140034954  movzx   ecx, di
0x140034957  and     cx, 7Fh
0x14003495b  mov     [rsp+258h+var_1E0], cx
0x140034960  movzx   ecx, byte ptr [r15+17Ah]
0x140034968  mov     ebx, r12d
0x14003496b  shl     ebx, cl
0x14003496d  mov     [rsp+258h+var_1B8], ebx
0x140034974  mov     [rsp+258h+var_1F0], ebx
0x140034978  mov     r8d, [rsp+258h+arg_10]
0x140034980  dec     r8d
0x140034983  add     r8d, esi
0x140034986  mov     eax, esi
0x140034988  neg     eax
0x14003498a  and     r8d, eax
0x14003498d  mov     dword ptr [rsp+258h+var_1E8], r8d
0x140034992  mov     [rsp+258h+arg_10], r8d
0x14003499a  mov     al, dl
0x14003499c  neg     al
0x14003499e  sbb     edx, edx
0x1400349a0  and     edx, esi
0x1400349a2  add     r8d, edx
0x1400349a5  mov     [rsp+258h+var_1F4], r8d
0x1400349aa  mov     eax, r10d
0x1400349ad  shl     eax, cl
0x1400349af  sub     eax, [r13+20h]
0x1400349b3  cmp     eax, r8d
0x1400349b6  jnb     short loc_1400349CD
0x1400349b8  mov     ecx, 0C000009Ah; Status
0x1400349bd  mov     [r14+48h], ecx
0x1400349c1  call    cs:__imp_ExRaiseStatus
0x1400349cd  mov     edx, r9d; PoolType
0x1400349d0  lea     rcx, [rsp+258h+Mcb]; Mcb
0x1400349d8  call    cs:__imp_FsRtlInitializeLargeMcb
0x1400349df  nop     dword ptr [rax+rax+00h]
0x1400349e4  mov     [rsp+258h+var_209], 1
0x1400349e9  lea     rax, [rsp+258h+Mcb]
0x1400349f1  mov     [rsp+258h+NumberOfBytes], rax; __int64
0x1400349f6  mov     [rsp+258h+var_238], 0; char
0x1400349fb  lea     r9, [rsp+258h+var_1F4]
0x140034a00  xor     r8d, r8d
0x140034a03  mov     rdx, r15; int
0x140034a06  mov     rcx, r14; int
0x140034a09  call    FatAllocateDiskSpace
0x140034a0e  mov     edx, 1; PoolType
0x140034a13  mov     [rsp+258h+var_213], dl
0x140034a17  mov     cl, [r15+17Ah]
0x140034a1e  mov     eax, dword ptr [rsp+258h+var_1E8]
0x140034a22  shr     eax, cl
0x140034a24  mov     [rsp+258h+var_1C8], eax
0x140034a2b  cmp     [rsp+258h+var_218], 0
0x140034a30  jz      short loc_140034A75
0x140034a32  lea     rcx, [rsp+258h+var_170]; Mcb
0x140034a3a  call    cs:__imp_FsRtlInitializeLargeMcb
0x140034a41  nop     dword ptr [rax+rax+00h]
0x140034a46  mov     [rsp+258h+var_215], 1
0x140034a4b  lea     rax, [rsp+258h+var_170]
0x140034a53  mov     qword ptr [rsp+258h+var_238], rax
0x140034a58  mov     r9d, dword ptr [rsp+258h+var_1E8]
0x140034a5d  lea     r8, [rsp+258h+Mcb]
0x140034a65  mov     rdx, r15
0x140034a68  mov     rcx, r14
0x140034a6b  call    FatSplitAllocation
0x140034a70  mov     [rsp+258h+var_20A], 1
0x140034a75  lea     rdx, [rsp+258h+var_F8]
0x140034a7d  call    FatUnpinEaRange
0x140034a82  lea     rdx, [rsp+258h+var_98]
0x140034a8a  call    FatUnpinEaRange
0x140034a8f  mov     eax, ebx
0x140034a91  xor     edx, edx
0x140034a93  cmp     [rsp+258h+var_218], dl
0x140034a97  cmovnz  eax, dword ptr [rsp+258h+var_1D8]
0x140034a9f  mov     dword ptr [rsp+258h+FileOffset], eax
0x140034aa6  mov     dword ptr [rsp+258h+FileOffset+4], edx
0x140034aad  and     eax, 0FFFFF000h
0x140034ab2  mov     dword ptr [rsp+258h+FileOffset], eax
0x140034ab9  xorps   xmm0, xmm0
0x140034abc  movups  xmmword ptr [rsp+258h+IoStatus], xmm0
0x140034ac4  lea     eax, [rdx+5]
0x140034ac7  mov     [rsp+258h+var_1EC], eax
0x140034acb  add     eax, 0FFFFFFFFh
0x140034ace  mov     [rsp+258h+var_1EC], eax
0x140034ad2  jz      short loc_140034B36
0x140034ad4  mov     dword ptr [rsp+258h+IoStatus], edx
0x140034adb  lea     r9, [rsp+258h+IoStatus]; IoStatus
0x140034ae3  xor     r8d, r8d; Length
0x140034ae6  xor     edx, edx; FileOffset
0x140034ae8  mov     rcx, [rsp+258h+FileObject]
0x140034af0  mov     rcx, [rcx+28h]; SectionObjectPointer
0x140034af4  call    cs:__imp_CcFlushCache
0x140034afb  nop     dword ptr [rax+rax+00h]
0x140034b00  xor     r9d, r9d; Flags
0x140034b03  xor     r8d, r8d; Length
0x140034b06  lea     rdx, [rsp+258h+FileOffset]; FileOffset
0x140034b0e  mov     rax, [rsp+258h+FileObject]
0x140034b16  mov     rcx, [rax+28h]; SectionObjectPointer
0x140034b1a  call    cs:__imp_CcPurgeCacheSection
0x140034b21  nop     dword ptr [rax+rax+00h]
0x140034b26  xor     edx, edx
0x140034b28  test    al, al
0x140034b2a  jnz     short loc_140034B32
0x140034b2c  mov     eax, [rsp+258h+var_1EC]
0x140034b30  jmp     short loc_140034ACB
0x140034b32  mov     eax, [rsp+258h+var_1EC]
0x140034b36  test    eax, eax
0x140034b38  jnz     short loc_140034B4F
0x140034b3a  mov     ecx, 0C000001Bh; Status
0x140034b3f  mov     [r14+48h], ecx
0x140034b43  call    cs:__imp_ExRaiseStatus
0x140034b4f  mov     r8d, 1
0x140034b55  mov     [rsp+258h+var_20B], r8b
0x140034b5a  mov     ecx, [r13+20h]
0x140034b5e  add     ecx, [rsp+258h+var_1F4]
0x140034b62  mov     dword ptr [rsp+258h+FileOffset], ecx
0x140034b69  cmp     [rsp+258h+var_214], dl
0x140034b6d  jz      short loc_140034BBA
0x140034b6f  mov     edx, r8d; PoolType
0x140034b72  lea     rcx, [rsp+258h+var_150]; Mcb
0x140034b7a  call    cs:__imp_FsRtlInitializeLargeMcb
0x140034b81  nop     dword ptr [rax+rax+00h]
0x140034b86  mov     [rsp+258h+var_217], 1
0x140034b8b  lea     r8, [r13+120h]
0x140034b92  lea     rax, [rsp+258h+var_150]
0x140034b9a  mov     qword ptr [rsp+258h+var_238], rax
0x140034b9f  mov     r9d, ebx
0x140034ba2  mov     rdx, r15
0x140034ba5  mov     rcx, r14
0x140034ba8  call    FatSplitAllocation
0x140034bad  mov     r8d, 1
0x140034bb3  mov     [rsp+258h+var_20C], r8b
0x140034bb8  xor     edx, edx
0x140034bba  mov     al, [rsp+258h+var_218]
0x140034bbe  test    al, al
0x140034bc0  jz      loc_140034C7B
0x140034bc6  cmp     ebx, dword ptr [rsp+258h+var_1D8]
0x140034bcd  jz      short loc_140034C23
  ... truncated ...
```
