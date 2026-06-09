# FatVerifyVolume

- ea: `0x140042ec8`
- end: `0x1400438cf`
- name: `FatVerifyVolume`
- size: `2567`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `24`
- tags: `reparse_path, installer_update, broker_com_uri`

## callers

- `0x14003ec78`

## callees

- `0x140005924`
- `0x140007408`
- `0x14000c230`
- `0x14000c680`
- `0x14000cba0`
- `0x140021f34`
- `0x140023380`
- `0x140023a5c`
- `0x140023cc4`
- `0x14002e4b0`
- `0x140038eb4`
- `0x14003dae0`
- `0x14003e4b4`
- `0x14003fff4`
- `0x14004237c`
- `0x1400427e8`
- `0x140042dcc`
- `0x140042ec8`
- `0x1400465f4`
- `0x1400466c8`
- `0x140048740`
- `0x140048ed0`
- `0x1400497f4`
- `0x140049bd4`

## import_xrefs

- `ntoskrnl!CcPurgeCacheSection` at `0x14004379e`
- `ntoskrnl!CcPurgeCacheSection` at `0x14004379e`
- `ntoskrnl!CcUninitializeCacheMap` at `0x1400436fc`
- `ntoskrnl!CcUninitializeCacheMap` at `0x1400436fc`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x1400430d4`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x14004316b`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x1400430d4`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x14004316b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140042fce`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140042fce`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004385c`
- `ntoskrnl!ExReleaseResourceLite` at `0x140043882`
- `ntoskrnl!ExReleaseResourceLite` at `0x140043895`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400438a8`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005f41f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005f449`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005f45d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005f470`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004385c`
- `ntoskrnl!ExReleaseResourceLite` at `0x140043882`
- `ntoskrnl!ExReleaseResourceLite` at `0x140043895`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400438a8`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005f41f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005f449`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005f45d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005f470`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004381b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043839`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005f3d7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005f3f2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004381b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043839`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005f3d7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005f3f2`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400431ba`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14004343d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400431ba`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14004343d`
- `ntoskrnl!ExRaiseStatus` at `0x1400430e2`
- `ntoskrnl!ExRaiseStatus` at `0x140043179`
- `ntoskrnl!ExRaiseStatus` at `0x14004361d`
- `ntoskrnl!ExRaiseStatus` at `0x1400430e2`
- `ntoskrnl!ExRaiseStatus` at `0x140043179`
- `ntoskrnl!ExRaiseStatus` at `0x14004361d`

## pseudocode

```c
__int64 __fastcall FatVerifyVolume(__int64 a1, IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  PIO_SECURITY_CONTEXT SecurityContext; // r15
  __int64 v5; // r13
  unsigned __int16 *v7; // rdi
  char v8; // si
  __int64 v9; // r8
  char v10; // r14
  char *v11; // rcx
  int v12; // r15d
  __int64 v13; // rcx
  __int64 v14; // r8
  NTSTATUS v15; // eax
  NTSTATUS v16; // eax
  __int64 v17; // rdx
  NTSTATUS v18; // eax
  NTSTATUS v19; // eax
  int v20; // eax
  SIZE_T v21; // rbx
  unsigned __int16 *PoolWithTag; // rax
  int v23; // ebx
  int v24; // esi
  int v25; // r14d
  int v26; // eax
  int v27; // edi
  __int64 v28; // rcx
  char v29; // al
  __int64 v30; // rsi
  __int64 v31; // rcx
  _QWORD *v32; // r14
  __int64 NextFcbBottomUp; // rax
  __int64 v34; // rcx
  __int64 v35; // r9
  __int64 v36; // r10
  int v37; // ecx
  PVOID v38; // rax
  PVOID v39; // r10
  unsigned __int16 v40; // ax
  int v41; // edx
  PIO_SECURITY_CONTEXT v42; // r14
  unsigned int v43; // edi
  int v44; // ebx
  char v45; // si
  PIO_SECURITY_CONTEXT v46; // r14
  int v47; // eax
  __int64 v48; // rbx
  __int64 v49; // rcx
  __int64 v50; // rax
  __int64 v51; // rcx
  _QWORD *v52; // r10
  __int64 v53; // rbx
  __int64 v54; // rcx
  __int64 v55; // rax
  __int64 v56; // rcx
  __int64 v57; // rcx
  char v58; // al
  __int64 i; // rdx
  __int64 v60; // rax
  __int64 v61; // rbx
  __int128 *v62; // [rsp+28h] [rbp-1C0h]
  __int64 v63; // [rsp+28h] [rbp-1C0h]
  int v64; // [rsp+30h] [rbp-1B8h]
  _BYTE v65[3]; // [rsp+51h] [rbp-197h] BYREF
  int v66; // [rsp+54h] [rbp-194h]
  char v67; // [rsp+58h] [rbp-190h]
  char v68; // [rsp+59h] [rbp-18Fh]
  char v69; // [rsp+5Ah] [rbp-18Eh]
  unsigned int v70; // [rsp+5Ch] [rbp-18Ch] BYREF
  unsigned __int8 v71; // [rsp+60h] [rbp-188h]
  int v72; // [rsp+64h] [rbp-184h]
  unsigned __int16 *v73; // [rsp+68h] [rbp-180h]
  int v74; // [rsp+70h] [rbp-178h]
  PVOID P; // [rsp+78h] [rbp-170h]
  PIO_SECURITY_CONTEXT v76; // [rsp+80h] [rbp-168h]
  unsigned int v77; // [rsp+88h] [rbp-160h]
  __int128 Buf1; // [rsp+90h] [rbp-158h] BYREF
  __int128 v79; // [rsp+A0h] [rbp-148h]
  __int128 v80; // [rsp+B0h] [rbp-138h]
  unsigned __int16 *v81; // [rsp+C0h] [rbp-128h]
  PVOID v82; // [rsp+C8h] [rbp-120h]
  size_t Size; // [rsp+D0h] [rbp-118h]
  PIRP Irp; // [rsp+D8h] [rbp-110h]
  __int64 v85; // [rsp+E0h] [rbp-108h]
  IRP *v86; // [rsp+E8h] [rbp-100h]
  __int64 v87; // [rsp+F0h] [rbp-F8h]
  __int128 v88; // [rsp+F8h] [rbp-F0h]
  _BYTE v89[144]; // [rsp+110h] [rbp-D8h] BYREF
  __int128 v90; // [rsp+1A0h] [rbp-48h] BYREF
  __int64 v91; // [rsp+1B0h] [rbp-38h]

  Irp = a2;
  v87 = a1;
  v86 = a2;
  v90 = 0;
  v91 = 0;
  v65[0] = 0;
  v74 = 0;
  v88 = 0;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  SecurityContext = CurrentStackLocation->Parameters.Create.SecurityContext;
  v76 = SecurityContext;
  v5 = (__int64)&CurrentStackLocation->Parameters.QueryDirectory.FileName[26];
  v85 = v5;
  *(_QWORD *)(a1 + 56) = v5;
  if ( (*(_DWORD *)(a1 + 68) & 2) == 0 )
    return FatFsdPostRequest((PVOID)a1, a2);
  v66 = 0;
  P = 0;
  v82 = 0;
  v7 = 0;
  v81 = 0;
  v69 = 0;
  v8 = 0;
  v67 = 0;
  ExAcquireResourceExclusiveLite(&Resource, 1u);
  FatAcquireExclusiveVcb_Real(a1, v5, 0);
  v10 = CurrentStackLocation->Flags & 1;
  v68 = v10;
  *(_QWORD *)(v5 + 880) = KeGetCurrentThread();
  v11 = (char *)*(unsigned int *)(*(_QWORD *)&SecurityContext->DesiredAccess + 48LL);
  if ( ((unsigned __int8)v11 & 2) != 0 )
  {
    memset(v89, 0, sizeof(v89));
    FatPerformDevIoCtrl(v13, 458824, *(_QWORD *)(v5 + 136));
    v14 = *(_QWORD *)(v5 + 136);
    if ( (*(_DWORD *)(v14 + 52) & 1) != 0 )
    {
      v15 = FatPerformDevIoCtrl(v11, 477184, v14);
      v66 = v15;
      if ( v15 < 0 )
      {
        if ( !v10 )
        {
          *(_DWORD *)(a1 + 72) = v15;
          v16 = FsRtlNormalizeNtstatus(v15, -1073741591);
          ExRaiseStatus(v16);
        }
LABEL_8:
        v12 = -1073741806;
        v66 = -1073741806;
LABEL_31:
        v9 = 0;
        goto LABEL_32;
      }
    }
    if ( *((_QWORD *)&v88 + 1) != 4 )
      v74 = 0;
    *(_DWORD *)(v5 + 1120) = v74;
    v17 = *(_QWORD *)(v5 + 136);
    if ( *(_DWORD *)(v17 + 72) == 2 && !(unsigned __int8)FatScanForDataTrack(v11, v17) )
      goto LABEL_8;
    v62 = &v90;
    v18 = FatPerformDevIoCtrl(v11, 458752, *(_QWORD *)(v5 + 136));
    v12 = v18;
    v66 = v18;
    if ( v18 < 0 )
    {
      if ( !v10 )
      {
        *(_DWORD *)(a1 + 72) = v18;
        v19 = FsRtlNormalizeNtstatus(v18, -1073741591);
        ExRaiseStatus(v19);
      }
      goto LABEL_8;
    }
    v20 = *(unsigned __int16 *)(v5 + 288);
    v72 = v20;
    if ( v20 != HIDWORD(v91) )
      goto LABEL_8;
    v21 = (v20 + 4095) & 0xFFFFF000;
    PoolWithTag = (unsigned __int16 *)ExAllocatePoolWithTag((POOL_TYPE)1556, v21, 0x73746146u);
    v7 = PoolWithTag;
    v73 = PoolWithTag;
    if ( !ExPoolZeroingNativelySupported && PoolWithTag )
      memset(PoolWithTag, 0, v21);
    v81 = v7;
    LOBYTE(v62) = v10;
    if ( !(unsigned __int8)FatPerformVerifyDiskRead(a1, v5, v7, 0, v72, v62, 24)
      || !(unsigned __int8)FatIsBootSectorFat(v7) )
    {
      goto LABEL_8;
    }
    v23 = v7[11];
    v11 = (char *)v7 + 67;
    if ( (_WORD)v23 )
      v11 = (char *)v7 + 39;
    if ( *(_DWORD *)v11 != LODWORD(v76[1].SecurityQos) )
      goto LABEL_8;
    Buf1 = 0;
    v79 = 0;
    v80 = 0;
    LOWORD(v70) = *(unsigned __int16 *)((char *)v7 + 11);
    LOWORD(Buf1) = v70;
    v71 = *((_BYTE *)v7 + 13);
    BYTE2(Buf1) = v71;
    v24 = v7[7];
    WORD2(Buf1) = v7[7];
    v25 = *((unsigned __int8 *)v7 + 16);
    BYTE6(Buf1) = *((_BYTE *)v7 + 16);
    LOWORD(v72) = *(unsigned __int16 *)((char *)v7 + 17);
    WORD4(Buf1) = v72;
    WORD5(Buf1) = *(unsigned __int16 *)((char *)v7 + 19);
    BYTE12(Buf1) = *((_BYTE *)v7 + 21);
    HIWORD(Buf1) = v23;
    *(_QWORD *)&v79 = *((_QWORD *)v7 + 3);
    v26 = *((_DWORD *)v7 + 8);
    DWORD2(v79) = v26;
    v27 = *((_DWORD *)v7 + 9);
    HIDWORD(v79) = v27;
    LOWORD(v80) = v73[20];
    WORD2(v80) = v73[21];
    v77 = *((_DWORD *)v73 + 11);
    DWORD2(v80) = v77;
    HIDWORD(v80) = *((_DWORD *)v73 + 12);
    if ( WORD5(Buf1) )
      v26 = 0;
    DWORD2(v79) = v26;
    if ( memcmp(&Buf1, (const void *)(v5 + 288), (-(__int64)((_WORD)v23 != 0) & 0xFFFFFFFFFFFFFFECuLL) + 48) )
      goto LABEL_29;
    if ( 32 * (unsigned __int16)v72 )
      v37 = 32 * (unsigned __int16)v72;
    else
      v37 = (unsigned __int16)v70 * v71;
    v72 = v37;
    Size = (v37 + 4095) & 0xFFFFF000;
    v38 = ExAllocatePoolWithTag((POOL_TYPE)1556, Size, 0x72746146u);
    v39 = v38;
    P = v38;
    v11 = 0;
    if ( !ExPoolZeroingNativelySupported && v38 )
    {
      memset(v38, 0, Size);
      v39 = P;
      v11 = 0;
    }
    v82 = v39;
    if ( v73[11] )
    {
      if ( (_WORD)v23 )
      {
        v41 = v23 * (unsigned __int16)v70;
        v40 = v70;
      }
      else
      {
        v40 = v70;
        v41 = v27 * (unsigned __int16)v70;
      }
      LOBYTE(v63) = v68;
      if ( !(unsigned __int8)FatPerformVerifyDiskRead(a1, v5, v39, v41 * v25 + v24 * (unsigned int)v40, v72, v63, v64)
        || (v42 = v76,
            v12 = FatSearchBufferForLabel((_DWORD)v11, (_DWORD)v76, (_DWORD)P, v72, (__int64)v65),
            v66 = v12,
            v12 >= 0)
        && !v65[0]
        && HIWORD(v42->SecurityQos) )
      {
LABEL_29:
        v12 = -1073741806;
        v66 = -1073741806;
LABEL_30:
        v7 = v73;
        v8 = 0;
        goto LABEL_31;
      }
    }
    else
    {
      v43 = v77;
      v70 = v77;
      v44 = v72;
      v45 = v68;
      v46 = v76;
      while ( v43 != 0xFFFFFFF )
      {
        LOBYTE(v63) = v45;
        if ( !(unsigned __int8)FatPerformVerifyDiskRead(
                                 a1,
                                 v5,
                                 v39,
                                 *(_QWORD *)(v5 + 352) + ((unsigned __int64)(v43 - 2) << *(_BYTE *)(v5 + 378)),
                                 v44,
                                 v63,
                                 v64) )
          goto LABEL_29;
        v12 = FatSearchBufferForLabel((_DWORD)v11, (_DWORD)v46, (_DWORD)P, v44, (__int64)v65);
        v66 = v12;
        if ( v12 < 0 || v65[0] )
          goto LABEL_50;
        FatVerifyLookupFatEntry(a1, v5, v43, &v70);
        v43 = v70;
        v47 = FatInterpretClusterType(v5, v70);
        if ( !v47 || (unsigned int)(v47 - 1) < 2 )
        {
          *(_DWORD *)(a1 + 72) = -1073741566;
          ExRaiseStatus(-1073741566);
        }
        v39 = P;
      }
      if ( HIWORD(v46->SecurityQos) )
        v12 = -1073741806;
      v66 = v12;
    }
LABEL_50:
    if ( !v12 )
    {
      v7 = v73;
      v8 = 0;
      goto LABEL_52;
    }
    goto LABEL_30;
  }
  v67 = 1;
  v12 = 0;
  v66 = 0;
LABEL_52:
  LOBYTE(v9) = 1;
LABEL_32:
  FatCloseEaFile(v11, v5, v9);
  v29 = v67;
  if ( v67 )
  {
    v32 = (_QWORD *)(v5 + 208);
  }
  else
  {
    v30 = 0;
    FatAcquireExclusiveVcb_Real(a1, v5, 0);
    while ( 1 )
    {
      v32 = (_QWORD *)(v5 + 208);
      NextFcbBottomUp = FatGetNextFcbBottomUp(v31, v30, *(_QWORD *)(v5 + 208));
      v30 = NextFcbBottomUp;
      if ( !NextFcbBottomUp )
        break;
      FatAcquireExclusiveFcb(a1, NextFcbBottomUp);
    }
    v8 = 1;
    LOBYTE(v35) = 1;
    FatMarkFcbCondition(v34, v36, 3, v35);
    v29 = v67;
  }
  if ( *(_DWORD *)(v5 + 204) == 2 )
  {
    v12 = -1073741806;
    v66 = -1073741806;
LABEL_87:
    v58 = v69;
    goto LABEL_88;
  }
  if ( v12 == -1073741806 )
  {
    if ( !v8 )
    {
      v48 = 0;
      FatAcquireExclusiveVcb_Real(a1, v5, 0);
      while ( 1 )
      {
        v50 = FatGetNextFcbBottomUp(v49, v48, *(_QWORD *)(v5 + 208));
        v48 = v50;
        if ( !v50 )
          break;
        FatAcquireExclusiveFcb(a1, v50);
      }
      v8 = 1;
    }
    FatPurgeReferencedFileObjects(a1, *(_QWORD *)(v5 + 208), 0);
    CcUninitializeCacheMap(*(PFILE_OBJECT *)(v5 + 728), &FatLargeZero, 0);
    FatTearDownAllocationSupport(v51, v5);
    *(_DWORD *)(v5 + 204) = 2;
    goto LABEL_89;
  }
  if ( v29 )
    goto LABEL_87;
  v52 = v32;
  if ( !v8 )
  {
    v53 = 0;
    FatAcquireExclusiveVcb_Real(a1, v5, 0);
    while ( 1 )
    {
      v55 = FatGetNextFcbBottomUp(v54, v53, *(_QWORD *)(v5 + 208));
      v53 = v55;
      if ( !v55 )
        break;
      FatAcquireExclusiveFcb(a1, v55);
    }
    v8 = 1;
  }
  FatPurgeReferencedFileObjects(a1, *v52, 1);
  FatFlushFat(a1, v5);
  CcPurgeCacheSection((PSECTION_OBJECT_POINTERS)(v5 + 736), 0, 0, 0);
  FatTearDownAllocationSupport(v56, v5);
  FatSetupAllocationSupport(a1, v5);
  FatCheckDirtyBit(a1, v5);
  if ( (unsigned __int8)FatIsMediaWriteProtected(v57, *(_QWORD *)(v5 + 136)) )
    _InterlockedOr((volatile signed __int32 *)(v5 + 200), 0x4000u);
  else
    _InterlockedAnd((volatile signed __int32 *)(v5 + 200), 0xFFFFBFFF);
  v58 = 1;
LABEL_88:
  if ( v58 )
LABEL_89:
    *(_DWORD *)(*(_QWORD *)&v76->DesiredAccess + 48LL) &= ~2u;
  if ( v7 )
    ExFreePoolWithTag(v7, 0);
  if ( P )
    ExFreePoolWithTag(P, 0);
  *(_QWORD *)(v5 + 880) = 0;
  if ( v8 )
  {
    for ( i = 0; ; i = v61 )
    {
      v60 = FatGetNextFcbBottomUp(v28, i, *v32);
      v61 = v60;
      if ( !v60 )
        break;
      ExReleaseResourceLite(*(PERESOURCE *)(v60 + 8));
    }
    ExReleaseResourceLite((PERESOURCE)(v5 + 520));
  }
  ExReleaseResourceLite((PERESOURCE)(v5 + 520));
  ExReleaseResourceLite(&Resource);
  FatCompleteRequest_Real((PVOID)a1, Irp);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140042ec8  mov     r11, rsp
0x140042ecb  mov     [r11+18h], rbx
0x140042ecf  mov     [r11+20h], rsi
0x140042ed3  push    rdi
0x140042ed4  push    r12
0x140042ed6  push    r13
0x140042ed8  push    r14
0x140042eda  push    r15
0x140042edc  sub     rsp, 1C0h
0x140042ee3  mov     rax, cs:__security_cookie
0x140042eea  xor     rax, rsp
0x140042eed  mov     [rsp+1E8h+var_30], rax
0x140042ef5  mov     [rsp+1E8h+Irp], rdx
0x140042efd  mov     r12, rcx
0x140042f00  mov     [rsp+1E8h+var_F8], rcx
0x140042f08  mov     [rsp+1E8h+var_100], rdx
0x140042f10  xorps   xmm0, xmm0
0x140042f13  xor     eax, eax
0x140042f15  movups  xmmword ptr [r11-48h], xmm0
0x140042f1a  mov     [r11-38h], rax
0x140042f1e  xor     ecx, ecx
0x140042f20  mov     [rsp+1E8h+var_197], cl
0x140042f24  mov     [rsp+1E8h+var_178], ecx
0x140042f28  movups  [rsp+1E8h+var_F0], xmm0
0x140042f30  mov     rbx, [rdx+0B8h]
0x140042f37  mov     r15, [rbx+8]
0x140042f3b  mov     [rsp+1E8h+var_168], r15
0x140042f43  mov     r13, [rbx+10h]
0x140042f47  add     r13, 1A0h
0x140042f4e  mov     [rsp+1E8h+var_108], r13
0x140042f56  mov     [r12+38h], r13
0x140042f5b  mov     eax, [r12+44h]
0x140042f60  test    al, 2
0x140042f62  jnz     short loc_140042F9A
0x140042f64  mov     rcx, r12; Context1
0x140042f67  call    FatFsdPostRequest
0x140042f6c  mov     rcx, [rsp+1E8h+var_30]
0x140042f74  xor     rcx, rsp; StackCookie
0x140042f77  call    __security_check_cookie
0x140042f7c  lea     r11, [rsp+1E8h+var_28]
0x140042f84  mov     rbx, [r11+40h]
0x140042f88  mov     rsi, [r11+48h]
0x140042f8c  mov     rsp, r11
0x140042f8f  pop     r15
0x140042f91  pop     r14
0x140042f93  pop     r13
0x140042f95  pop     r12
0x140042f97  pop     rdi
0x140042f98  retn
0x140042f9a  mov     [rsp+1E8h+var_194], ecx
0x140042f9e  mov     [rsp+1E8h+P], rcx
0x140042fa3  mov     [rsp+1E8h+var_120], rcx
0x140042fab  mov     rdi, rcx
0x140042fae  mov     [rsp+1E8h+var_128], rcx
0x140042fb6  mov     [rsp+1E8h+var_18E], cl
0x140042fba  mov     sil, cl
0x140042fbd  mov     [rsp+1E8h+var_198], cl
0x140042fc1  mov     [rsp+1E8h+var_190], cl
0x140042fc5  mov     dl, 1; Wait
0x140042fc7  lea     rcx, Resource; Resource
0x140042fce  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140042fd5  nop     dword ptr [rax+rax+00h]
0x140042fda  xor     r8d, r8d
0x140042fdd  mov     rdx, r13
0x140042fe0  mov     rcx, r12
0x140042fe3  call    FatAcquireExclusiveVcb_Real
0x140042fe8  nop
0x140042fe9  mov     r14b, [rbx+2]
0x140042fed  and     r14b, 1
0x140042ff1  mov     [rsp+1E8h+var_18F], r14b
0x140042ff6  mov     rax, gs:188h
0x140042fff  mov     [r13+370h], rax
0x140043006  mov     rax, [r15+10h]
0x14004300a  mov     ecx, [rax+30h]
0x14004300d  test    cl, 2
0x140043010  jnz     short loc_14004302A
0x140043012  mov     al, 1
0x140043014  mov     [rsp+1E8h+var_190], al
0x140043018  xor     r15d, r15d
0x14004301b  mov     [rsp+1E8h+var_194], r15d
0x140043020  mov     ebx, 0C0000012h
0x140043025  jmp     loc_140043540
0x14004302a  mov     ebx, 90h
0x14004302f  mov     r8d, ebx; Size
0x140043032  xor     edx, edx; Val
0x140043034  lea     rcx, [rsp+1E8h+var_D8]; void *
0x14004303c  call    memset
0x140043041  lea     rax, [rsp+1E8h+var_F0]
0x140043049  mov     [rsp+1E8h+var_1A0], rax
0x14004304e  mov     [rsp+1E8h+var_1B8], ebx
0x140043052  lea     rax, [rsp+1E8h+var_D8]
0x14004305a  mov     [rsp+1E8h+var_1C0], rax
0x14004305f  mov     r8, [r13+88h]
0x140043066  mov     edx, 70048h
0x14004306b  call    FatPerformDevIoCtrl
0x140043070  mov     r8, [r13+88h]
0x140043077  mov     eax, [r8+34h]
0x14004307b  test    al, 1
0x14004307d  jz      short loc_1400430EE
0x14004307f  lea     rax, [rsp+1E8h+var_F0]
0x140043087  mov     [rsp+1E8h+var_1A0], rax
0x14004308c  mov     [rsp+1E8h+var_1B8], 4
0x140043094  lea     rax, [rsp+1E8h+var_178]
0x140043099  mov     [rsp+1E8h+var_1C0], rax
0x14004309e  mov     edx, 74800h
0x1400430a3  call    FatPerformDevIoCtrl
0x1400430a8  mov     [rsp+1E8h+var_194], eax
0x1400430ac  xor     ebx, ebx
0x1400430ae  test    eax, eax
0x1400430b0  jns     short loc_1400430F0
0x1400430b2  test    r14b, r14b
0x1400430b5  jz      short loc_1400430C8
0x1400430b7  mov     ebx, 0C0000012h
0x1400430bc  mov     r15d, ebx
0x1400430bf  mov     [rsp+1E8h+var_194], ebx
0x1400430c3  jmp     loc_14004339C
0x1400430c8  mov     [r12+48h], eax
0x1400430cd  mov     edx, 0C00000E9h; GenericException
0x1400430d2  mov     ecx, eax; Exception
0x1400430d4  call    cs:__imp_FsRtlNormalizeNtstatus
0x1400430db  nop     dword ptr [rax+rax+00h]
0x1400430e0  mov     ecx, eax; Status
0x1400430e2  call    cs:__imp_ExRaiseStatus
0x1400430ee  xor     ebx, ebx
0x1400430f0  cmp     qword ptr [rsp+1E8h+var_F0+8], 4
0x1400430f9  jz      short loc_1400430FF
0x1400430fb  mov     [rsp+1E8h+var_178], ebx
0x1400430ff  mov     eax, [rsp+1E8h+var_178]
0x140043103  mov     [r13+460h], eax
0x14004310a  mov     rdx, [r13+88h]
0x140043111  cmp     dword ptr [rdx+48h], 2
0x140043115  jnz     short loc_140043120
0x140043117  call    FatScanForDataTrack
0x14004311c  test    al, al
0x14004311e  jz      short loc_1400430B7
0x140043120  mov     [rsp+1E8h+var_1A0], rbx
0x140043125  mov     [rsp+1E8h+var_1B8], 18h
0x14004312d  lea     rax, [rsp+1E8h+var_48]
0x140043135  mov     [rsp+1E8h+var_1C0], rax
0x14004313a  mov     r8, [r13+88h]
0x140043141  mov     edx, 70000h
0x140043146  call    FatPerformDevIoCtrl
0x14004314b  mov     r15d, eax
0x14004314e  mov     [rsp+1E8h+var_194], eax
0x140043152  test    eax, eax
0x140043154  jns     short loc_140043185
0x140043156  test    r14b, r14b
0x140043159  jnz     loc_1400430B7
0x14004315f  mov     [r12+48h], eax
0x140043164  mov     edx, 0C00000E9h; GenericException
0x140043169  mov     ecx, eax; Exception
0x14004316b  call    cs:__imp_FsRtlNormalizeNtstatus
0x140043172  nop     dword ptr [rax+rax+00h]
0x140043177  mov     ecx, eax; Status
0x140043179  call    cs:__imp_ExRaiseStatus
0x140043185  movzx   eax, word ptr [r13+120h]
0x14004318d  mov     [rsp+1E8h+var_184], eax
0x140043191  cmp     eax, [rsp+1E8h+var_34]
0x140043198  jnz     loc_1400430B7
0x14004319e  lea     ebx, [rax+0FFFh]
0x1400431a4  mov     eax, 0FFFFF000h
0x1400431a9  and     rbx, rax
0x1400431ac  mov     r8d, 73746146h; Tag
0x1400431b2  mov     rdx, rbx; NumberOfBytes
0x1400431b5  mov     ecx, 614h; PoolType
0x1400431ba  call    cs:__imp_ExAllocatePoolWithTag
0x1400431c1  nop     dword ptr [rax+rax+00h]
0x1400431c6  mov     rdi, rax
0x1400431c9  mov     [rsp+1E8h+var_180], rax
0x1400431ce  xor     ecx, ecx
0x1400431d0  cmp     cs:ExPoolZeroingNativelySupported, cl
0x1400431d6  jnz     short loc_1400431EA
0x1400431d8  test    rax, rax
0x1400431db  jz      short loc_1400431EA
0x1400431dd  mov     r8, rbx; Size
0x1400431e0  xor     edx, edx; Val
0x1400431e2  mov     rcx, rax; void *
0x1400431e5  call    memset
0x1400431ea  mov     [rsp+1E8h+var_128], rdi
0x1400431f2  mov     byte ptr [rsp+1E8h+var_1C0], r14b
0x1400431f7  mov     eax, [rsp+1E8h+var_184]
0x1400431fb  mov     dword ptr [rsp+1E8h+var_1C8], eax
0x1400431ff  xor     r9d, r9d
0x140043202  mov     r8, rdi
0x140043205  mov     rdx, r13
0x140043208  mov     rcx, r12
0x14004320b  call    FatPerformVerifyDiskRead
0x140043210  test    al, al
0x140043212  jz      loc_1400430B7
0x140043218  mov     rcx, rdi
0x14004321b  call    FatIsBootSectorFat
0x140043220  test    al, al
0x140043222  jz      loc_1400430B7
0x140043228  movzx   ebx, word ptr [rdi+16h]
0x14004322c  test    bx, bx
0x14004322f  lea     rcx, [rdi+43h]
0x140043233  jz      short loc_140043239
0x140043235  lea     rcx, [rdi+27h]
0x140043239  mov     r14, [rsp+1E8h+var_168]
0x140043241  mov     eax, [r14+18h]
0x140043245  cmp     [rcx], eax
0x140043247  jnz     loc_1400430B7
0x14004324d  xorps   xmm0, xmm0
0x140043250  movups  [rsp+1E8h+Buf1], xmm0
0x140043258  movups  [rsp+1E8h+var_148], xmm0
0x140043260  movups  [rsp+1E8h+var_138], xmm0
0x140043268  movzx   eax, word ptr [rdi+0Bh]
0x14004326c  mov     word ptr [rsp+1E8h+var_18C], ax
0x140043271  mov     word ptr [rsp+1E8h+Buf1], ax
0x140043279  mov     al, [rdi+0Dh]
0x14004327c  mov     [rsp+1E8h+var_188], al
0x140043280  mov     byte ptr [rsp+1E8h+Buf1+2], al
0x140043287  movzx   esi, word ptr [rdi+0Eh]
0x14004328b  mov     word ptr [rsp+1E8h+Buf1+4], si
0x140043293  movzx   r14d, byte ptr [rdi+10h]
0x140043298  mov     byte ptr [rsp+1E8h+Buf1+6], r14b
0x1400432a0  movzx   eax, word ptr [rdi+11h]
0x1400432a4  mov     word ptr [rsp+1E8h+var_184], ax
0x1400432a9  mov     word ptr [rsp+1E8h+Buf1+8], ax
0x1400432b1  movzx   r8d, word ptr [rdi+13h]
0x1400432b6  mov     word ptr [rsp+1E8h+Buf1+0Ah], r8w
0x1400432bf  mov     al, [rdi+15h]
0x1400432c2  mov     byte ptr [rsp+1E8h+Buf1+0Ch], al
0x1400432c9  mov     word ptr [rsp+1E8h+Buf1+0Eh], bx
0x1400432d1  movzx   eax, word ptr [rdi+18h]
0x1400432d5  mov     word ptr [rsp+1E8h+var_148], ax
0x1400432dd  movzx   eax, word ptr [rdi+1Ah]
0x1400432e1  mov     word ptr [rsp+1E8h+var_148+2], ax
0x1400432e9  mov     eax, [rdi+1Ch]
0x1400432ec  mov     dword ptr [rsp+1E8h+var_148+4], eax
0x1400432f3  mov     eax, [rdi+20h]
0x1400432f6  mov     dword ptr [rsp+1E8h+var_148+8], eax
0x1400432fd  mov     edi, [rdi+24h]
0x140043300  mov     dword ptr [rsp+1E8h+var_148+0Ch], edi
0x140043307  mov     rdx, [rsp+1E8h+var_180]
0x14004330c  movzx   ecx, word ptr [rdx+28h]
0x140043310  mov     word ptr [rsp+1E8h+var_138], cx
0x140043318  movzx   ecx, word ptr [rdx+2Ah]
0x14004331c  mov     word ptr [rsp+1E8h+var_138+4], cx
0x140043324  mov     ecx, [rdx+2Ch]
0x140043327  mov     [rsp+1E8h+var_160], ecx
0x14004332e  mov     dword ptr [rsp+1E8h+var_138+8], ecx
0x140043335  movzx   ecx, word ptr [rdx+30h]
0x140043339  mov     word ptr [rsp+1E8h+var_138+0Ch], cx
0x140043341  movzx   ecx, word ptr [rdx+32h]
0x140043345  mov     word ptr [rsp+1E8h+var_138+0Eh], cx
0x14004334d  xor     edx, edx
0x14004334f  test    r8w, r8w
0x140043353  cmovnz  eax, edx
0x140043356  mov     dword ptr [rsp+1E8h+var_148+8], eax
0x14004335d  movzx   eax, bx
0x140043360  neg     ax
0x140043363  sbb     r8, r8
0x140043366  and     r8, 0FFFFFFFFFFFFFFECh
0x14004336a  add     r8, 30h ; '0'; Size
0x14004336e  lea     rdx, [r13+120h]; Buf2
0x140043375  lea     rcx, [rsp+1E8h+Buf1]; Buf1
0x14004337d  call    memcmp
0x140043382  test    eax, eax
0x140043384  jz      short loc_1400433F5
0x140043386  mov     ebx, 0C0000012h
0x14004338b  mov     r15d, ebx
0x14004338e  mov     [rsp+1E8h+var_194], ebx
0x140043392  mov     rdi, [rsp+1E8h+var_180]
0x140043397  mov     sil, [rsp+1E8h+var_198]
0x14004339c  xor     r8d, r8d
0x14004339f  mov     rdx, r13
0x1400433a2  call    FatCloseEaFile
0x1400433a7  mov     al, [rsp+1E8h+var_190]
0x1400433ab  xor     r11d, r11d
0x1400433ae  test    al, al
0x1400433b0  jnz     loc_140043671
0x1400433b6  mov     esi, r11d
0x1400433b9  xor     r8d, r8d
0x1400433bc  mov     rdx, r13
0x1400433bf  mov     rcx, r12
0x1400433c2  call    FatAcquireExclusiveVcb_Real
0x1400433c7  lea     r14, [r13+0D0h]
0x1400433ce  mov     r10, [r14]
0x1400433d1  mov     r8, r10
0x1400433d4  mov     rdx, rsi
0x1400433d7  call    FatGetNextFcbBottomUp
0x1400433dc  mov     rsi, rax
0x1400433df  test    rax, rax
0x1400433e2  jz      loc_14004364F
0x1400433e8  mov     rdx, rax
0x1400433eb  mov     rcx, r12
0x1400433ee  call    FatAcquireExclusiveFcb
0x1400433f3  jmp     short loc_1400433C7
0x1400433f5  movzx   ecx, word ptr [rsp+1E8h+var_184]
0x1400433fa  mov     eax, ecx
0x1400433fc  shl     eax, 5
0x1400433ff  test    eax, eax
0x140043401  jz      short loc_140043408
0x140043403  shl     ecx, 5
0x140043406  jmp     short loc_140043415
0x140043408  movzx   ecx, [rsp+1E8h+var_188]
0x14004340d  movzx   eax, word ptr [rsp+1E8h+var_18C]
0x140043412  imul    ecx, eax
0x140043415  mov     [rsp+1E8h+var_184], ecx
  ... truncated ...
```
