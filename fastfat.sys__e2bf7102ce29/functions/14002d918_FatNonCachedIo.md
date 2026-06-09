# FatNonCachedIo

- ea: `0x14002d918`
- end: `0x14002e0c4`
- name: `FatNonCachedIo`
- size: `1964`
- prototype: `__int64 __fastcall(int, int, int, int, SIZE_T NumberOfBytes, int, char)`
- caller_count: `4`
- callee_count: `14`
- tags: `installer_update`

## callers

- `0x14002e0cc`
- `0x140037240`
- `0x14004573c`
- `0x14004af08`

## callees

- `0x140002cb0`
- `0x140002dec`
- `0x140002e24`
- `0x14000c230`
- `0x14000c680`
- `0x14002221c`
- `0x14002d4a8`
- `0x14002d5a8`
- `0x14002d610`
- `0x14002d918`
- `0x14002e6ac`
- `0x14002e95c`
- `0x14003958c`
- `0x14003f50c`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14002db81`
- `ntoskrnl!KeInitializeEvent` at `0x14002db81`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002dae9`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002dae9`
- `ntoskrnl!IoFreeMdl` at `0x14002e058`
- `ntoskrnl!IoFreeMdl` at `0x14002e058`
- `ntoskrnl!IoAllocateMdl` at `0x14002da85`
- `ntoskrnl!IoAllocateMdl` at `0x14002dc14`
- `ntoskrnl!IoAllocateMdl` at `0x14002da85`
- `ntoskrnl!IoAllocateMdl` at `0x14002dc14`
- `ntoskrnl!IoBuildPartialMdl` at `0x14002daac`
- `ntoskrnl!IoBuildPartialMdl` at `0x14002daac`
- `ntoskrnl!IoGetFsZeroingOffset` at `0x14002da29`
- `ntoskrnl!IoGetFsZeroingOffset` at `0x14002da29`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14002dc2b`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14002dc2b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002dfb2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e06e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005cd55`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002dfb2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e06e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005cd55`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002dbc8`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002de25`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002dbc8`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002de25`
- `ntoskrnl!ExRaiseStatus` at `0x14002db57`
- `ntoskrnl!ExRaiseStatus` at `0x14002dc90`
- `ntoskrnl!ExRaiseStatus` at `0x14002e0b7`
- `ntoskrnl!ExRaiseStatus` at `0x14002db57`
- `ntoskrnl!ExRaiseStatus` at `0x14002dc90`
- `ntoskrnl!ExRaiseStatus` at `0x14002e0b7`

## pseudocode

```c
__int64 __fastcall FatNonCachedIo(
        __int64 a1,
        IRP *a2,
        __int64 a3,
        unsigned int a4,
        SIZE_T NumberOfBytes,
        unsigned int a6,
        char a7)
{
  unsigned int v10; // r15d
  LOCK_OPERATION v11; // r8d
  unsigned __int64 v12; // rcx
  __int64 v13; // rdx
  int v14; // r13d
  bool v15; // r12
  struct _MDL *Mdl; // rax
  struct _MDL *v17; // r14
  __int64 v19; // rcx
  int v20; // eax
  PVOID v21; // r13
  PVOID PoolWithTag; // rax
  void *v23; // r14
  struct _MDL *v24; // rax
  struct _MDL *v25; // r12
  unsigned int v26; // r13d
  unsigned int v27; // r14d
  __int64 v28; // rcx
  __int64 v29; // rdx
  __int64 v30; // rcx
  char v31; // r8
  __int64 v32; // rcx
  unsigned int v33; // r12d
  int v34; // r8d
  unsigned int v35; // ecx
  unsigned int v36; // r13d
  unsigned int v37; // eax
  SIZE_T v38; // r13
  _BYTE *v39; // rax
  _BYTE *v40; // r14
  unsigned int v41; // edx
  unsigned int v42; // r9d
  __int64 v43; // rcx
  unsigned __int64 v44; // rcx
  __int64 v45; // rdx
  char v46; // r8
  char v48; // al
  bool v49; // [rsp+40h] [rbp-138h]
  char v50; // [rsp+41h] [rbp-137h] BYREF
  char v51; // [rsp+42h] [rbp-136h] BYREF
  char v52; // [rsp+43h] [rbp-135h] BYREF
  unsigned int v53; // [rsp+44h] [rbp-134h] BYREF
  unsigned int v54; // [rsp+48h] [rbp-130h] BYREF
  unsigned int v55; // [rsp+4Ch] [rbp-12Ch]
  int v56; // [rsp+50h] [rbp-128h] BYREF
  unsigned int v57; // [rsp+54h] [rbp-124h] BYREF
  unsigned int v58; // [rsp+58h] [rbp-120h]
  __int64 v59; // [rsp+60h] [rbp-118h] BYREF
  __int64 v60; // [rsp+68h] [rbp-110h] BYREF
  PVOID VirtualAddress; // [rsp+70h] [rbp-108h]
  int v62; // [rsp+78h] [rbp-100h] BYREF
  _QWORD v63[2]; // [rsp+80h] [rbp-F8h] BYREF
  _BYTE v64[160]; // [rsp+90h] [rbp-E8h] BYREF

  v55 = a4;
  v10 = NumberOfBytes;
  v11 = IoReadAccess;
  v59 = 0;
  v53 = 0;
  v51 = 0;
  v63[0] = 0;
  v56 = 0;
  v52 = 0;
  v50 = 0;
  v57 = 0;
  v54 = 0;
  v60 = 0;
  v62 = 0;
  if ( (a2->Flags & 2) == 0 )
  {
    v12 = (unsigned __int64)(KeGetCurrentProcessorNumber() % (unsigned int)dword_140017D48) << 7;
    v13 = *(_QWORD *)(*(_QWORD *)(a3 + 184) + 1024LL);
    if ( *(_BYTE *)(a1 + 64) == 3 )
    {
      ++*(_DWORD *)(v12 + v13 + 68);
      *(_DWORD *)(v12 + v13 + 72) += NumberOfBytes;
    }
    else
    {
      ++*(_DWORD *)(v12 + v13 + 76);
      *(_DWORD *)(v12 + v13 + 80) += NumberOfBytes;
    }
  }
  v14 = *(_DWORD *)(a1 + 68) & 2;
  v15 = v14 != 0;
  v49 = v14 != 0;
  if ( FatDiskAccountingEnabled )
  {
    FatUpdateDiskStats(a1, a2, NumberOfBytes);
    v11 = IoReadAccess;
  }
  LOBYTE(v11) = *(_BYTE *)(a1 + 64) == 3;
  FatLockUserBuffer(a1, a2, v11, NumberOfBytes);
  if ( (unsigned int)IoGetFsZeroingOffset(a2, &v62)
    && a6 != (_DWORD)NumberOfBytes
    && (*(_DWORD *)(a3 + 192) & 0x60000) == 0 )
  {
    VirtualAddress = (char *)a2->MdlAddress->StartVa + a2->MdlAddress->ByteOffset + a6;
    Mdl = IoAllocateMdl(VirtualAddress, (unsigned int)NumberOfBytes - a6, 0, 0, 0);
    v17 = Mdl;
    if ( !Mdl )
      goto LABEL_31;
    IoBuildPartialMdl(a2->MdlAddress, Mdl, VirtualAddress, NumberOfBytes - a6);
    *(_QWORD *)(*(_QWORD *)(a1 + 80) + 16LL) = v17;
    if ( !((v17->MdlFlags & 5) != 0
         ? v17->MappedSystemVa
         : MmMapLockedPagesSpecifyCache(v17, 0, MmCached, 0, 0, 0x40000010u)) )
      goto LABEL_31;
    v15 = v14 != 0;
  }
  v19 = *(unsigned int *)(*(_QWORD *)(a3 + 184) + 200LL);
  if ( (v19 & 0x400000) == 0
    || (*(_DWORD *)(a3 + 192) & 0x60000) == 0
    || (v20 = *(_DWORD *)(a1 + 68), (v20 & 0x4000) != 0)
    || (a7 & 2) != 0 )
  {
    v49 = v15;
    goto LABEL_33;
  }
  if ( !*(_QWORD *)(a3 + 144) )
  {
    *(_DWORD *)(a1 + 72) = -1073739760;
    ExRaiseStatus(-1073739760);
  }
  if ( !v14 )
  {
    *(_DWORD *)(a1 + 68) = v20 | 2;
    v49 = 1;
    KeInitializeEvent((PRKEVENT)(*(_QWORD *)(a1 + 80) + 24LL), NotificationEvent, 0);
  }
  v21 = FatMapUserBuffer(v19, (__int64)a2);
  *(_QWORD *)(*(_QWORD *)(a1 + 80) + 88LL) = v21;
  v60 = v55;
  if ( *(_BYTE *)(a1 + 64) != 4 )
    goto LABEL_33;
  PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)1556, (unsigned int)NumberOfBytes, 0x4F746146u);
  v23 = PoolWithTag;
  if ( !ExPoolZeroingNativelySupported )
  {
    if ( !PoolWithTag )
      goto LABEL_31;
    memset(PoolWithTag, 0, (unsigned int)NumberOfBytes);
  }
  if ( !v23 || (v24 = IoAllocateMdl(v23, NumberOfBytes, 0, 0, 0), (v25 = v24) == 0) )
  {
LABEL_31:
    *(_DWORD *)(a1 + 72) = -1073741670;
    ExRaiseStatus(-1073741670);
  }
  MmBuildMdlForNonPagedPool(v24);
  EfsBeforeWriteProcessCallback(v21, v23, &v60, (unsigned int)NumberOfBytes, *(_QWORD *)(a3 + 144));
  *(_QWORD *)(*(_QWORD *)(a1 + 80) + 96LL) = v23;
  *(_QWORD *)(*(_QWORD *)(a1 + 80) + 104LL) = v25;
  *(_QWORD *)(*(_QWORD *)(a1 + 80) + 72LL) = a2->UserBuffer;
  a2->UserBuffer = v23;
  *(_QWORD *)(*(_QWORD *)(a1 + 80) + 80LL) = a2->MdlAddress;
  a2->MdlAddress = v25;
LABEL_33:
  v26 = v55;
  FatLookupFileAllocation(a1, a3, v55, (unsigned int)&v59, (__int64)&v53, (__int64)&v51, (__int64)&v50, (__int64)&v57);
  if ( !v51 )
    goto LABEL_82;
  v27 = NumberOfBytes;
  v58 = NumberOfBytes;
  if ( v53 >= (unsigned int)NumberOfBytes - (v50 != 0) )
  {
    v28 = KeGetCurrentProcessorNumber() % (unsigned int)dword_140017D48;
    v29 = *(_QWORD *)(*(_QWORD *)(a3 + 184) + 1024LL);
    if ( (a2->Flags & 2) != 0 )
    {
      v30 = v28 << 7;
      v31 = *(_BYTE *)(a1 + 64);
      if ( (*(_DWORD *)(a1 + 68) & 0x400) != 0 )
      {
        if ( v31 == 4 )
          ++*(_DWORD *)(v30 + v29 + 28);
        else
          ++*(_DWORD *)(v30 + v29 + 16);
      }
      else if ( v31 == 4 )
      {
        ++*(_DWORD *)(v30 + v29 + 52);
      }
      else
      {
        ++*(_DWORD *)(v30 + v29 + 40);
      }
    }
    else
    {
      v32 = v28 << 7;
      if ( *(_BYTE *)(a1 + 64) == 3 )
        ++*(_DWORD *)(v32 + v29 + 84);
      else
        ++*(_DWORD *)(v32 + v29 + 88);
    }
    FatSingleAsync(a1, *(_QWORD *)(a3 + 184), v59, NumberOfBytes, (__int64)a2);
    goto LABEL_71;
  }
  FatLookupFileAllocation(
    a1,
    a3,
    NumberOfBytes + v26 - 1,
    (unsigned int)v63,
    (__int64)&v56,
    (__int64)&v52,
    (__int64)&v50,
    (__int64)&v54);
  if ( !v52 )
  {
LABEL_82:
    FatPopUpFileCorrupt(a1, a3);
    *(_DWORD *)(a1 + 72) = -1073741566;
    ExRaiseStatus(-1073741566);
  }
  v33 = 0;
  v34 = 0;
  v35 = v54;
  v36 = v57;
  v37 = v54 - v57 + 1;
  if ( v37 <= 5 )
  {
    v40 = v64;
  }
  else
  {
    v38 = 32LL * v37;
    v39 = ExAllocatePoolWithTag((POOL_TYPE)1041, v38, 0x69746146u);
    v40 = v39;
    if ( !ExPoolZeroingNativelySupported && v39 )
      memset(v39, 0, v38);
    v36 = v57;
    v35 = v54;
    v34 = 0;
  }
  VirtualAddress = v40;
  if ( v36 <= v35 )
  {
    v41 = v53;
    v42 = v55;
    do
    {
      if ( v41 > v10 )
        v41 = v10;
      v53 = v41;
      v43 = 32LL * v33;
      *(_DWORD *)&v40[v43 + 8] = v42;
      *(_QWORD *)&v40[v43] = v59;
      *(_DWORD *)&v40[v43 + 12] = v34;
      *(_DWORD *)&v40[v43 + 16] = v41;
      ++v33;
      v55 = v41 + v42;
      v56 = v41 + v34;
      v10 -= v41;
      if ( ++v36 > v54 )
        break;
      FatGetNextMcbEntry(*(_QWORD *)(a3 + 184), a3 + 288, v36, v63, &v59, &v53);
      v41 = v53;
      v34 = v56;
      v42 = v55;
    }
    while ( v36 <= v54 );
  }
  a2->IoStatus.Status = 0;
  a2->IoStatus.Information = v58;
  if ( (a2->Flags & 2) != 0 )
  {
    v44 = (unsigned __int64)(KeGetCurrentProcessorNumber() % (unsigned int)dword_140017D48) << 7;
    v45 = *(_QWORD *)(*(_QWORD *)(a3 + 184) + 1024LL);
    v46 = *(_BYTE *)(a1 + 64);
    if ( (*(_DWORD *)(a1 + 68) & 0x400) != 0 )
    {
      if ( v46 == 4 )
        *(_DWORD *)(v44 + v45 + 28) += v33;
      else
        *(_DWORD *)(v44 + v45 + 16) += v33;
    }
    else if ( v46 == 4 )
    {
      *(_DWORD *)(v44 + v45 + 52) += v33;
    }
    else
    {
      *(_DWORD *)(v44 + v45 + 40) += v33;
    }
  }
  FatMultipleAsync(a1, *(_QWORD *)(a3 + 184), a2, v33, v40);
  if ( v40 != v64 )
    ExFreePoolWithTag(v40, 0);
  v27 = v58;
LABEL_71:
  if ( !v49 )
    return 259;
  FatWaitSync(a1);
  if ( (*(_DWORD *)(*(_QWORD *)(a3 + 184) + 200LL) & 0x400000) != 0
    && (*(_DWORD *)(a3 + 192) & 0x60000) != 0
    && (*(_DWORD *)(a1 + 68) & 0x4000) == 0
    && (a7 & 2) == 0 )
  {
    v48 = *(_BYTE *)(a1 + 64);
    if ( v48 == 4 )
    {
      a2->UserBuffer = *(PVOID *)(*(_QWORD *)(a1 + 80) + 72LL);
      a2->MdlAddress = *(PMDL *)(*(_QWORD *)(a1 + 80) + 80LL);
      IoFreeMdl(*(PMDL *)(*(_QWORD *)(a1 + 80) + 104LL));
      ExFreePoolWithTag(*(PVOID *)(*(_QWORD *)(a1 + 80) + 96LL), 0);
    }
    else if ( v48 == 3 )
    {
      EfsAfterReadProcessCallback(*(_QWORD *)(*(_QWORD *)(a1 + 80) + 88LL), &v60, v27, *(_QWORD *)(a3 + 144));
    }
  }
  return (unsigned int)a2->IoStatus.Status;
}

```

## disassembly

```asm
0x14002d918  push    rbx
0x14002d91a  push    rsi
0x14002d91b  push    rdi
0x14002d91c  push    r12
0x14002d91e  push    r13
0x14002d920  push    r14
0x14002d922  push    r15
0x14002d924  sub     rsp, 140h
0x14002d92b  mov     rax, cs:__security_cookie
0x14002d932  xor     rax, rsp
0x14002d935  mov     [rsp+178h+var_48], rax
0x14002d93d  mov     [rsp+178h+var_12C], r9d
0x14002d942  mov     rdi, r8
0x14002d945  mov     rsi, rdx
0x14002d948  mov     rbx, rcx
0x14002d94b  mov     r15d, dword ptr [rsp+178h+NumberOfBytes]
0x14002d953  mov     r14d, [rsp+178h+arg_28]
0x14002d95b  xor     r8d, r8d
0x14002d95e  mov     [rsp+178h+var_118], r8
0x14002d963  mov     [rsp+178h+var_134], r8d
0x14002d968  mov     [rsp+178h+var_136], r8b
0x14002d96d  mov     [rsp+178h+var_F8], r8
0x14002d975  mov     [rsp+178h+var_128], r8d
0x14002d97a  mov     [rsp+178h+var_135], r8b
0x14002d97f  mov     [rsp+178h+var_137], r8b
0x14002d984  mov     [rsp+178h+var_124], r8d
0x14002d989  mov     [rsp+178h+var_130], r8d
0x14002d98e  mov     [rsp+178h+var_110], r8
0x14002d993  mov     [rsp+178h+var_100], r8d
0x14002d998  mov     eax, [rdx+10h]
0x14002d99b  test    al, 2
0x14002d99d  jnz     short loc_14002D9E0
0x14002d99f  mov     al, gs:184h
0x14002d9a7  movzx   eax, al
0x14002d9aa  xor     edx, edx
0x14002d9ac  div     cs:dword_140017D48
0x14002d9b2  mov     ecx, edx
0x14002d9b4  shl     rcx, 7
0x14002d9b8  mov     rax, [rdi+0B8h]
0x14002d9bf  mov     rdx, [rax+400h]
0x14002d9c6  cmp     byte ptr [rbx+40h], 3
0x14002d9ca  jnz     short loc_14002D9D7
0x14002d9cc  inc     dword ptr [rcx+rdx+44h]
0x14002d9d0  add     [rcx+rdx+48h], r15d
0x14002d9d5  jmp     short loc_14002D9E0
0x14002d9d7  inc     dword ptr [rcx+rdx+4Ch]
0x14002d9db  add     [rcx+rdx+50h], r15d
0x14002d9e0  mov     r13d, [rbx+44h]
0x14002d9e4  and     r13d, 2
0x14002d9e8  setnz   r12b
0x14002d9ec  mov     [rsp+178h+var_138], r12b
0x14002d9f1  cmp     cs:FatDiskAccountingEnabled, r8d
0x14002d9f8  jz      short loc_14002DA0B
0x14002d9fa  mov     r8d, r15d
0x14002d9fd  mov     rdx, rsi
0x14002da00  mov     rcx, rbx
0x14002da03  call    FatUpdateDiskStats
0x14002da08  xor     r8d, r8d
0x14002da0b  cmp     byte ptr [rbx+40h], 3
0x14002da0f  setz    r8b
0x14002da13  mov     r9d, r15d
0x14002da16  mov     rdx, rsi
0x14002da19  mov     rcx, rbx
0x14002da1c  call    FatLockUserBuffer
0x14002da21  lea     rdx, [rsp+178h+var_100]
0x14002da26  mov     rcx, rsi
0x14002da29  call    cs:__imp_IoGetFsZeroingOffset
0x14002da30  nop     dword ptr [rax+rax+00h]
0x14002da35  test    eax, eax
0x14002da37  jz      loc_14002DB03
0x14002da3d  cmp     r14d, r15d
0x14002da40  jz      loc_14002DB03
0x14002da46  test    dword ptr [rdi+0C0h], 60000h
0x14002da50  jnz     loc_14002DB03
0x14002da56  mov     rax, [rsi+8]
0x14002da5a  mov     r12d, r15d
0x14002da5d  sub     r12d, r14d
0x14002da60  mov     ecx, [rax+2Ch]
0x14002da63  add     rcx, [rax+20h]
0x14002da67  lea     rax, [rcx+r14]
0x14002da6b  mov     [rsp+178h+VirtualAddress], rax
0x14002da70  mov     [rsp+178h+Irp], 0; Irp
0x14002da79  xor     r9d, r9d; ChargeQuota
0x14002da7c  xor     r8d, r8d; SecondaryBuffer
0x14002da7f  mov     edx, r12d; Length
0x14002da82  mov     rcx, rax; VirtualAddress
0x14002da85  call    cs:__imp_IoAllocateMdl
0x14002da8c  nop     dword ptr [rax+rax+00h]
0x14002da91  mov     r14, rax
0x14002da94  test    rax, rax
0x14002da97  jz      loc_14002DC88
0x14002da9d  mov     r9d, r12d; Length
0x14002daa0  mov     r8, [rsp+178h+VirtualAddress]; VirtualAddress
0x14002daa5  mov     rdx, rax; TargetMdl
0x14002daa8  mov     rcx, [rsi+8]; SourceMdl
0x14002daac  call    cs:__imp_IoBuildPartialMdl
0x14002dab3  nop     dword ptr [rax+rax+00h]
0x14002dab8  mov     rcx, [rbx+50h]
0x14002dabc  mov     [rcx+10h], r14
0x14002dac0  test    byte ptr [r14+0Ah], 5
0x14002dac5  jz      short loc_14002DACD
0x14002dac7  mov     rax, [r14+18h]
0x14002dacb  jmp     short loc_14002DAF5
0x14002dacd  mov     [rsp+178h+Priority], 40000010h; Priority
0x14002dad5  mov     dword ptr [rsp+178h+Irp], 0; BugCheckOnFailure
0x14002dadd  xor     r9d, r9d; RequestedAddress
0x14002dae0  xor     edx, edx; AccessMode
0x14002dae2  lea     r8d, [r9+1]; CacheType
0x14002dae6  mov     rcx, r14; MemoryDescriptorList
0x14002dae9  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14002daf0  nop     dword ptr [rax+rax+00h]
0x14002daf5  test    rax, rax
0x14002daf8  jz      loc_14002DC88
0x14002dafe  mov     r12b, [rsp+178h+var_138]
0x14002db03  mov     rax, [rdi+0B8h]
0x14002db0a  mov     ecx, [rax+0C8h]
0x14002db10  bt      ecx, 16h
0x14002db14  jnb     loc_14002DC9D
0x14002db1a  test    dword ptr [rdi+0C0h], 60000h
0x14002db24  jz      loc_14002DC9D
0x14002db2a  mov     eax, [rbx+44h]
0x14002db2d  bt      eax, 0Eh
0x14002db31  jb      loc_14002DC9D
0x14002db37  test    [rsp+178h+arg_30], 2
0x14002db3f  jnz     loc_14002DC9D
0x14002db45  cmp     qword ptr [rdi+90h], 0
0x14002db4d  jnz     short loc_14002DB64
0x14002db4f  mov     ecx, 0C0000810h; Status
0x14002db54  mov     [rbx+48h], ecx
0x14002db57  call    cs:__imp_ExRaiseStatus
0x14002db64  test    r13d, r13d
0x14002db67  jnz     short loc_14002DB8D
0x14002db69  or      eax, 2
0x14002db6c  mov     [rbx+44h], eax
0x14002db6f  mov     [rsp+178h+var_138], 1
0x14002db74  mov     rcx, [rbx+50h]
0x14002db78  add     rcx, 18h; Event
0x14002db7c  xor     r8d, r8d; State
0x14002db7f  xor     edx, edx; Type
0x14002db81  call    cs:__imp_KeInitializeEvent
0x14002db88  nop     dword ptr [rax+rax+00h]
0x14002db8d  mov     rdx, rsi
0x14002db90  call    FatMapUserBuffer
0x14002db95  mov     r13, rax
0x14002db98  mov     rcx, [rbx+50h]
0x14002db9c  mov     [rcx+58h], rax
0x14002dba0  mov     dword ptr [rsp+178h+var_110+4], 0
0x14002dba8  mov     eax, [rsp+178h+var_12C]
0x14002dbac  mov     dword ptr [rsp+178h+var_110], eax
0x14002dbb0  cmp     byte ptr [rbx+40h], 4
0x14002dbb4  jnz     loc_14002DCA2
0x14002dbba  mov     r8d, 4F746146h; Tag
0x14002dbc0  mov     rdx, r15; NumberOfBytes
0x14002dbc3  mov     ecx, 614h; PoolType
0x14002dbc8  call    cs:__imp_ExAllocatePoolWithTag
0x14002dbcf  nop     dword ptr [rax+rax+00h]
0x14002dbd4  mov     r14, rax
0x14002dbd7  cmp     cs:ExPoolZeroingNativelySupported, 0
0x14002dbde  jnz     short loc_14002DBF6
0x14002dbe0  test    rax, rax
0x14002dbe3  jz      loc_14002DC88
0x14002dbe9  mov     r8, r15; Size
0x14002dbec  xor     edx, edx; Val
0x14002dbee  mov     rcx, rax; void *
0x14002dbf1  call    memset
0x14002dbf6  test    r14, r14
0x14002dbf9  jz      loc_14002DC88
0x14002dbff  mov     [rsp+178h+Irp], 0; Irp
0x14002dc08  xor     r9d, r9d; ChargeQuota
0x14002dc0b  xor     r8d, r8d; SecondaryBuffer
0x14002dc0e  mov     edx, r15d; Length
0x14002dc11  mov     rcx, r14; VirtualAddress
0x14002dc14  call    cs:__imp_IoAllocateMdl
0x14002dc1b  nop     dword ptr [rax+rax+00h]
0x14002dc20  mov     r12, rax
0x14002dc23  test    rax, rax
0x14002dc26  jz      short loc_14002DC88
0x14002dc28  mov     rcx, rax; MemoryDescriptorList
0x14002dc2b  call    cs:__imp_MmBuildMdlForNonPagedPool
0x14002dc32  nop     dword ptr [rax+rax+00h]
0x14002dc37  mov     rcx, [rdi+90h]
0x14002dc3e  mov     [rsp+178h+Irp], rcx
0x14002dc43  mov     r9d, r15d
0x14002dc46  lea     r8, [rsp+178h+var_110]
0x14002dc4b  mov     rdx, r14
0x14002dc4e  mov     rcx, r13
0x14002dc51  call    EfsBeforeWriteProcessCallback
0x14002dc56  mov     rcx, [rbx+50h]
0x14002dc5a  mov     [rcx+60h], r14
0x14002dc5e  mov     rax, [rbx+50h]
0x14002dc62  mov     [rax+68h], r12
0x14002dc66  mov     rcx, [rbx+50h]
0x14002dc6a  mov     rax, [rsi+70h]
0x14002dc6e  mov     [rcx+48h], rax
0x14002dc72  mov     [rsi+70h], r14
0x14002dc76  mov     rcx, [rbx+50h]
0x14002dc7a  mov     rax, [rsi+8]
0x14002dc7e  mov     [rcx+50h], rax
0x14002dc82  mov     [rsi+8], r12
0x14002dc86  jmp     short loc_14002DCA2
0x14002dc88  mov     ecx, 0C000009Ah; Status
0x14002dc8d  mov     [rbx+48h], ecx
0x14002dc90  call    cs:__imp_ExRaiseStatus
0x14002dc9d  mov     [rsp+178h+var_138], r12b
0x14002dca2  lea     rax, [rsp+178h+var_124]
0x14002dca7  mov     [rsp+178h+var_140], rax
0x14002dcac  lea     rax, [rsp+178h+var_137]
0x14002dcb1  mov     [rsp+178h+var_148], rax
0x14002dcb6  lea     rax, [rsp+178h+var_136]
0x14002dcbb  mov     qword ptr [rsp+178h+Priority], rax
0x14002dcc0  lea     rax, [rsp+178h+var_134]
0x14002dcc5  mov     [rsp+178h+Irp], rax
0x14002dcca  lea     r9, [rsp+178h+var_118]
0x14002dccf  mov     r13d, [rsp+178h+var_12C]
0x14002dcd4  mov     r8d, r13d
0x14002dcd7  mov     rdx, rdi
0x14002dcda  mov     rcx, rbx
0x14002dcdd  call    FatLookupFileAllocation
0x14002dce2  cmp     [rsp+178h+var_136], 0
0x14002dce7  jz      loc_14002E0A4
0x14002dced  mov     r14d, r15d
0x14002dcf0  mov     [rsp+178h+var_120], r15d
0x14002dcf5  xor     ecx, ecx
0x14002dcf7  cmp     [rsp+178h+var_137], cl
0x14002dcfb  setnz   cl
0x14002dcfe  mov     eax, r15d
0x14002dd01  sub     eax, ecx
0x14002dd03  mov     ecx, [rsp+178h+var_134]
0x14002dd07  mov     [rsp+178h+var_134], ecx
0x14002dd0b  cmp     ecx, eax
0x14002dd0d  jb      loc_14002DDA8
0x14002dd13  mov     al, gs:184h
0x14002dd1b  movzx   eax, al
0x14002dd1e  mov     ecx, [rsi+10h]
0x14002dd21  xor     edx, edx
0x14002dd23  div     cs:dword_140017D48
0x14002dd29  mov     rax, [rdi+0B8h]
0x14002dd30  test    cl, 2
0x14002dd33  mov     ecx, edx
0x14002dd35  mov     rdx, [rax+400h]
0x14002dd3c  jz      short loc_14002DD73
0x14002dd3e  shl     rcx, 7
0x14002dd42  mov     r8b, [rbx+40h]
0x14002dd46  test    dword ptr [rbx+44h], 400h
0x14002dd4d  jz      short loc_14002DD61
0x14002dd4f  cmp     r8b, 4
0x14002dd53  jnz     short loc_14002DD5B
0x14002dd55  inc     dword ptr [rcx+rdx+1Ch]
0x14002dd59  jmp     short loc_14002DD87
0x14002dd5b  inc     dword ptr [rcx+rdx+10h]
0x14002dd5f  jmp     short loc_14002DD87
0x14002dd61  cmp     r8b, 4
0x14002dd65  jnz     short loc_14002DD6D
0x14002dd67  inc     dword ptr [rcx+rdx+34h]
0x14002dd6b  jmp     short loc_14002DD87
0x14002dd6d  inc     dword ptr [rcx+rdx+28h]
0x14002dd71  jmp     short loc_14002DD87
0x14002dd73  shl     rcx, 7
0x14002dd77  cmp     byte ptr [rbx+40h], 3
0x14002dd7b  jnz     short loc_14002DD83
0x14002dd7d  inc     dword ptr [rcx+rdx+54h]
0x14002dd81  jmp     short loc_14002DD87
0x14002dd83  inc     dword ptr [rcx+rdx+58h]
0x14002dd87  mov     [rsp+178h+Irp], rsi
0x14002dd8c  mov     r9d, r15d
0x14002dd8f  mov     r8, [rsp+178h+var_118]
0x14002dd94  mov     rdx, [rdi+0B8h]
0x14002dd9b  mov     rcx, rbx
0x14002dd9e  call    FatSingleAsync
0x14002dda3  jmp     loc_14002DFC3
0x14002dda8  lea     r8d, [r13-1]
0x14002ddac  add     r8d, r15d
0x14002ddaf  lea     rax, [rsp+178h+var_130]
0x14002ddb4  mov     [rsp+178h+var_140], rax
0x14002ddb9  lea     rax, [rsp+178h+var_137]
0x14002ddbe  mov     [rsp+178h+var_148], rax
0x14002ddc3  lea     rax, [rsp+178h+var_135]
0x14002ddc8  mov     qword ptr [rsp+178h+Priority], rax
0x14002ddcd  lea     rax, [rsp+178h+var_128]
0x14002ddd2  mov     [rsp+178h+Irp], rax
0x14002ddd7  lea     r9, [rsp+178h+var_F8]
0x14002dddf  mov     rdx, rdi
0x14002dde2  mov     rcx, rbx
0x14002dde5  call    FatLookupFileAllocation
0x14002ddea  cmp     [rsp+178h+var_135], 0
0x14002ddef  jz      loc_14002E0A4
0x14002ddf5  xor     r12d, r12d
0x14002ddf8  xor     r8d, r8d
0x14002ddfb  mov     ecx, [rsp+178h+var_130]
0x14002ddff  mov     eax, ecx
0x14002de01  mov     r13d, [rsp+178h+var_124]
0x14002de06  sub     eax, r13d
0x14002de09  inc     eax
0x14002de0b  cmp     eax, 5
0x14002de0e  jbe     short loc_14002DE5D
0x14002de10  mov     r13d, eax
0x14002de13  shl     r13, 5
0x14002de17  mov     r8d, 69746146h; Tag
0x14002de1d  mov     rdx, r13; NumberOfBytes
0x14002de20  mov     ecx, 411h; PoolType
  ... truncated ...
```
