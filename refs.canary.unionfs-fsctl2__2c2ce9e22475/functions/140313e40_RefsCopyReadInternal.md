# RefsCopyReadInternal

- ea: `0x140313e40`
- end: `0x140314683`
- name: `RefsCopyReadInternal`
- size: `2115`
- prototype: `__int64 __usercall@<rax>(struct _FILE_OBJECT *@<rcx>, PLARGE_INTEGER FileOffset@<rdx>, __int64, __int64, PIO_STATUS_BLOCK)`
- caller_count: `2`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1402cdde0`
- `0x140313dc0`

## callees

- `0x140039b60`
- `0x140069750`
- `0x14007e870`
- `0x14008a460`
- `0x14008dbd0`
- `0x14008e360`
- `0x14008e3c0`
- `0x140092e30`
- `0x1400a6a10`
- `0x1400ac2dc`
- `0x1400ac5c8`
- `0x1400ad64c`
- `0x1400ca788`
- `0x1401e9ce0`
- `0x140313e40`
- `0x14031468c`

## import_xrefs

- `ntoskrnl!IoGetTopLevelIrp` at `0x140313e9b`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140313e9b`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14031402e`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1403142cb`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14031402e`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1403142cb`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140313ed6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140313ed6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140314327`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140314327`
- `ntoskrnl!IoGetCurrentProcess` at `0x1403144c9`
- `ntoskrnl!IoGetCurrentProcess` at `0x1403144c9`
- `ntoskrnl!CcCopyRead` at `0x14031406c`
- `ntoskrnl!CcCopyRead` at `0x14031406c`
- `ntoskrnl!FsRtlFastCheckLockForRead` at `0x1403144f5`
- `ntoskrnl!FsRtlFastCheckLockForRead` at `0x1403144f5`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140314366`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140314366`
- `ntoskrnl!FsRtlIncrementCcFastReadWait` at `0x140313f24`
- `ntoskrnl!FsRtlIncrementCcFastReadWait` at `0x140313f24`
- `ntoskrnl!FsRtlIncrementCcFastReadNoWait` at `0x1403145df`
- `ntoskrnl!FsRtlIncrementCcFastReadNoWait` at `0x1403145df`
- `ntoskrnl!FsRtlIncrementCcFastMdlReadWait` at `0x1403143c6`
- `ntoskrnl!FsRtlIncrementCcFastMdlReadWait` at `0x1403143c6`
- `ntoskrnl!FsRtlIncrementCcFastReadResourceMiss` at `0x1403145f3`
- `ntoskrnl!FsRtlIncrementCcFastReadResourceMiss` at `0x1403145f3`
- `ntoskrnl!FsRtlIncrementCcFastReadNotPossible` at `0x140314509`
- `ntoskrnl!FsRtlIncrementCcFastReadNotPossible` at `0x140314604`
- `ntoskrnl!FsRtlIncrementCcFastReadNotPossible` at `0x140314509`
- `ntoskrnl!FsRtlIncrementCcFastReadNotPossible` at `0x140314604`
- `ntoskrnl!CcMdlRead` at `0x140314238`
- `ntoskrnl!CcMdlRead` at `0x140314238`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140314375`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140314375`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14034020e`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14034020e`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140314389`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140314389`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140314395`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140314395`

## string_xrefs

- `0x140314569`: `Read.c`

## pseudocode

```c
BOOLEAN __fastcall RefsCopyReadInternal(
        struct _FILE_OBJECT *a1,
        PLARGE_INTEGER FileOffset,
        BOOLEAN a3,
        ULONG a4,
        void *a5,
        PMDL *a6,
        PIO_STATUS_BLOCK IoStatus)
{
  char *v10; // rbx
  __int64 v11; // rax
  struct _IRP_CONTEXT *v12; // r14
  __int16 v13; // ax
  char *v14; // rdx
  __int64 v15; // r9
  __int64 v16; // rax
  __int64 v17; // r8
  __int64 v18; // rcx
  __int64 v19; // rax
  char v20; // al
  union _LARGE_INTEGER v21; // rdi
  DWORD LowPart; // r8d
  BOOLEAN v23; // di
  __int64 v24; // r8
  int v25; // ecx
  _DWORD *v26; // r15
  char v27; // r9
  __int64 v28; // rax
  unsigned int v29; // ecx
  unsigned int v30; // edx
  __int64 v31; // r11
  __int64 v32; // rax
  DWORD v33; // edx
  char v34; // r10
  unsigned int v35; // ecx
  __int64 v36; // rcx
  __int64 v37; // rdx
  __int64 v38; // rcx
  struct _FAST_MUTEX *v40; // rdi
  char *v41; // rcx
  char *v42; // rdx
  __int64 v43; // r9
  __int64 v44; // rax
  __int64 v45; // r8
  __int64 v46; // rcx
  LONGLONG QuadPart; // rax
  PEPROCESS CurrentProcess; // rax
  _DWORD *FsContext2; // [rsp+38h] [rbp-360h]
  union _LARGE_INTEGER Length; // [rsp+40h] [rbp-358h] BYREF
  struct _IRP_CONTEXT *v53; // [rsp+48h] [rbp-350h] BYREF
  PVOID Buffer; // [rsp+50h] [rbp-348h]
  union _LARGE_INTEGER StartingByte; // [rsp+58h] [rbp-340h] BYREF
  PMDL *MdlChain; // [rsp+60h] [rbp-338h]
  char *FsContext; // [rsp+68h] [rbp-330h]
  char v58; // [rsp+70h] [rbp-328h] BYREF

  Buffer = a5;
  MdlChain = a6;
  if ( !IoGetTopLevelIrp() )
  {
    if ( !FileOffset[2].LowPart )
    {
      v23 = 0;
      IoStatus->Status = 0;
      IoStatus->Information = 0;
      return v23;
    }
    v53 = (struct _IRP_CONTEXT *)&v58;
    FsContext = (char *)a1->FsContext;
    v10 = FsContext;
    FsContext2 = a1->FsContext2;
    KeEnterCriticalRegion();
    RefsInitializeIrpContext(0, 1u, 1u, &v53);
    v11 = *((_QWORD *)v10 + 18);
    v12 = v53;
    *((_QWORD *)v53 + 8) = v11;
    if ( *(_DWORD *)(v11 + 556) )
    {
      v23 = 0;
LABEL_80:
      RefsCleanupIrpContext(v12, 0);
      KeLeaveCriticalRegion();
      return v23;
    }
    if ( a6 )
    {
      FsRtlIncrementCcFastMdlReadWait();
    }
    else if ( a3 )
    {
      FsRtlIncrementCcFastReadWait();
    }
    else
    {
      FsRtlIncrementCcFastReadNoWait();
    }
    if ( !*((_QWORD *)v10 + 2) )
      goto LABEL_122;
    v13 = *(_WORD *)v10;
    if ( a1->PrivateCacheMap != (PVOID)1 )
    {
      if ( v13 == 2050 )
        v14 = v10;
      else
        v14 = (char *)*((_QWORD *)v10 + 17);
      if ( !v12 )
        goto LABEL_107;
      v15 = *((_QWORD *)v14 + 12);
      v16 = *((_QWORD *)v12 + 13);
      v17 = *(_QWORD *)(v16 + 336);
      v18 = v16 + 248;
      if ( !v17 )
      {
        *(_QWORD *)(v16 + 336) = v15;
        MsInitializeFastResourceOwnerEntry(v18);
        goto LABEL_14;
      }
      if ( v17 != v15 )
      {
        if ( *(_DWORD *)(v16 + 320) )
        {
LABEL_107:
          v18 = 0;
          goto LABEL_14;
        }
        *(_QWORD *)(v16 + 336) = v15;
      }
LABEL_14:
      v19 = *((_QWORD *)v14 + 12);
      if ( v18 )
        v20 = MsAcquireFastResourceSharedInternal<0>(v19, v18, a3);
      else
        v20 = MsAcquireFastResourceSharedLegacy<0>(v19, a3);
      if ( v20 )
        goto LABEL_17;
LABEL_122:
      v23 = 0;
LABEL_123:
      FsRtlIncrementCcFastReadResourceMiss();
      goto LABEL_80;
    }
    if ( v13 == 2050 )
      v41 = v10;
    else
      v41 = (char *)*((_QWORD *)v10 + 17);
    v23 = MsAcquireFastResourceExclusive(*((_QWORD *)v41 + 12), 0, a3);
    if ( !v23 )
      goto LABEL_123;
    v23 = RefsSetupCacheMapDuringFastIo(v12, a1, (struct DataSCB *)v10);
    if ( !v23 )
    {
      FsRtlIncrementCcFastReadNotPossible();
      goto LABEL_73;
    }
    if ( *(_WORD *)v10 == 2050 )
      v42 = v10;
    else
      v42 = (char *)*((_QWORD *)v10 + 17);
    if ( !v12 )
      goto LABEL_118;
    v43 = *((_QWORD *)v42 + 12);
    v44 = *((_QWORD *)v12 + 13);
    v45 = *(_QWORD *)(v44 + 336);
    v46 = v44 + 248;
    if ( !v45 )
    {
      *(_QWORD *)(v44 + 336) = v43;
      MsInitializeFastResourceOwnerEntry(v46);
      goto LABEL_96;
    }
    if ( v45 != v43 )
    {
      if ( *(_DWORD *)(v44 + 320) )
      {
LABEL_118:
        v46 = 0;
        goto LABEL_96;
      }
      *(_QWORD *)(v44 + 336) = v43;
    }
LABEL_96:
    if ( v46 )
      MsConvertFastResourceExclusiveToShared(*((_QWORD *)v42 + 12), v46);
    else
      MsConvertFastResourceExclusiveToSharedLegacy(*((_QWORD *)v42 + 12));
LABEL_17:
    if ( !a1->PrivateCacheMap || !v10[5] )
      goto LABEL_103;
    if ( !RefsIsFileOpen(*((const struct _FCB **)v10 + 17))
      || a1->SectionObjectPointer != (PSECTION_OBJECT_POINTERS)(*((_QWORD *)v10 + 31) + 8LL) )
    {
      goto LABEL_104;
    }
    if ( v10[5] == 2 )
    {
      StartingByte = *FileOffset;
      Length.QuadPart = FileOffset[2].LowPart;
      if ( *((_QWORD *)v10 + 48) )
      {
        CurrentProcess = IoGetCurrentProcess();
        if ( !FsRtlFastCheckLockForRead(*((PFILE_LOCK *)v10 + 48), &StartingByte, &Length, a4, a1, CurrentProcess) )
        {
LABEL_103:
          FsRtlIncrementCcFastReadNotPossible();
LABEL_104:
          v23 = 0;
          goto LABEL_73;
        }
      }
    }
    if ( (*((_DWORD *)v10 + 43) & 1) != 0 )
    {
      v40 = (struct _FAST_MUTEX *)*((_QWORD *)v10 + 6);
      KeEnterGuardedRegion();
      ExAcquireFastMutexUnsafe(v40);
      v21 = *(union _LARGE_INTEGER *)(v10 + 32);
      ExReleaseFastMutexUnsafe(*((PFAST_MUTEX *)v10 + 6));
      KeLeaveGuardedRegion();
    }
    else
    {
      v21 = *(union _LARGE_INTEGER *)(v10 + 32);
    }
    if ( FileOffset[1].QuadPart > v21.QuadPart )
    {
      QuadPart = FileOffset->QuadPart;
      if ( FileOffset->QuadPart >= v21.QuadPart )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            17,
            WPP_4825f846088e3f1b9f5b83e186ef8a59_Traceguids,
            3221225489LL);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
          RefsStatusDebug(-1073741807, 0, "Read.c", 0x2BDu);
        IoStatus->Status = -1073741807;
        IoStatus->Information = 0;
        v23 = 1;
        goto LABEL_73;
      }
      FileOffset[1] = v21;
      FileOffset[2].LowPart = v21.LowPart - QuadPart;
    }
    IoSetTopLevelIrp((PIRP)4);
    IoStatus->Status = 0;
    LowPart = FileOffset[2].LowPart;
    if ( MdlChain )
    {
      CcMdlRead(a1, FileOffset, LowPart, MdlChain, IoStatus);
      v23 = 1;
    }
    else
    {
      v23 = CcCopyRead(a1, FileOffset, LowPart, a3, Buffer, IoStatus);
      if ( !v23 )
      {
LABEL_72:
        IoSetTopLevelIrp(0);
LABEL_73:
        if ( *(_WORD *)v10 != 2050 )
          v10 = (char *)*((_QWORD *)v10 + 17);
        if ( !v12
          || (v36 = *((_QWORD *)v12 + 13), *(_QWORD *)(v36 + 336) != *((_QWORD *)v10 + 12))
          || (v37 = v36 + 248, !*(_DWORD *)(v36 + 320)) )
        {
          v37 = 0;
        }
        v38 = *((_QWORD *)v10 + 12);
        if ( v37 )
          MsReleaseFastResource(v38, v37);
        else
          MsReleaseFastResourceLegacy(v38);
        goto LABEL_80;
      }
      a1->CurrentByteOffset.QuadPart = FileOffset->QuadPart + IoStatus->Information;
    }
    v24 = *((_QWORD *)v10 + 17);
    Buffer = 0;
    v25 = *(_DWORD *)(*(_QWORD *)(v24 + 88) + 296LL);
    v26 = FsContext2;
    if ( FsContext2
      && (FsContext2[1] & 0x40) == 0
      && (((unsigned __int8)dword_1402612AC & 0x40) == 0 || BYTE1(v25)
                                                         || BYTE2(v25)
                                                         || (*(_BYTE *)(v24 + 8) & 0x10) != 0) )
    {
      v31 = MEMORY[0xFFFFF78000000014];
      Buffer = (PVOID)MEMORY[0xFFFFF78000000014];
      Length.LowPart = 0;
      v27 = 0;
      v32 = *(_QWORD *)(v24 + 88);
      v33 = *(_DWORD *)(v32 + 296);
      *(_DWORD *)(v32 + 296) = 0;
      Length.LowPart = v33;
      if ( (_BYTE)v33 || BYTE2(v33) || BYTE1(v33) )
      {
        if ( BYTE1(v33) )
        {
          *(_QWORD *)(v24 + 112) = v31;
          v27 = 1;
        }
        if ( BYTE2(v33) )
        {
          *(_QWORD *)(v24 + 120) = v31;
          v27 = 1;
        }
        if ( (_BYTE)v33
          && (((unsigned __int8)dword_1402612AC & 0x40) == 0
           || BYTE1(v33)
           || BYTE2(v33)
           || (*(_BYTE *)(v24 + 8) & 0x10) != 0) )
        {
          *(_QWORD *)(v24 + 184) = v31;
        }
        v26 = FsContext2;
      }
      if ( (_BYTE)v25 )
        goto LABEL_37;
    }
    else
    {
      v27 = 0;
      v28 = *(_QWORD *)(v24 + 88);
      v29 = *(_DWORD *)(v28 + 296);
      *(_DWORD *)(v28 + 296) = 0;
      v30 = v29 >> 8;
      if ( (_BYTE)v29 )
      {
        v34 = v29;
      }
      else
      {
        if ( !BYTE2(v29) && !BYTE1(v29) )
          goto LABEL_37;
        v34 = 0;
      }
      v31 = MEMORY[0xFFFFF78000000014];
      if ( BYTE1(v29) )
      {
        *(_QWORD *)(v24 + 112) = MEMORY[0xFFFFF78000000014];
        v27 = 1;
      }
      v35 = HIWORD(v29);
      if ( (_BYTE)v35 )
      {
        *(_QWORD *)(v24 + 120) = v31;
        v27 = 1;
      }
      if ( !v34
        || ((unsigned __int8)dword_1402612AC & 0x40) != 0
        && !(_BYTE)v30
        && !(_BYTE)v35
        && (*(_BYTE *)(v24 + 8) & 0x10) == 0 )
      {
        goto LABEL_37;
      }
    }
    *(_QWORD *)(v24 + 184) = v31;
LABEL_37:
    if ( v26 && *((_BYTE *)v26 + 80) != 4 && v27 )
      v26[1] |= 0x10000u;
    a1->Flags |= 0x80000u;
    goto LABEL_72;
  }
  return 0;
}

```

## disassembly

```asm
0x140313e40  push    rbx
0x140313e42  push    rsi
0x140313e43  push    rdi
0x140313e44  push    r12
0x140313e46  push    r13
0x140313e48  push    r14
0x140313e4a  push    r15
0x140313e4c  sub     rsp, 360h
0x140313e53  mov     rax, cs:__security_cookie
0x140313e5a  xor     rax, rsp
0x140313e5d  mov     [rsp+398h+var_48], rax
0x140313e65  mov     [rsp+398h+Key], r9d
0x140313e6a  movzx   edi, r8b
0x140313e6e  mov     [rsp+398h+var_365], r8b
0x140313e73  mov     r15, rdx
0x140313e76  mov     rsi, rcx
0x140313e79  mov     r13, [rsp+398h+arg_30]
0x140313e81  mov     rax, [rsp+398h+arg_20]
0x140313e89  mov     [rsp+398h+var_348], rax
0x140313e8e  mov     r12, [rsp+398h+arg_28]
0x140313e96  mov     [rsp+398h+MdlChain], r12
0x140313e9b  call    cs:__imp_IoGetTopLevelIrp
0x140313ea2  nop     dword ptr [rax+rax+00h]
0x140313ea7  test    rax, rax
0x140313eaa  jnz     loc_1403145D0
0x140313eb0  cmp     [r15+10h], eax
0x140313eb4  jz      loc_140314670
0x140313eba  lea     rax, [rsp+398h+var_328]
0x140313ebf  mov     [rsp+398h+var_350], rax
0x140313ec4  mov     rbx, [rsi+18h]
0x140313ec8  mov     [rsp+398h+var_330], rbx
0x140313ecd  mov     rax, [rsi+20h]
0x140313ed1  mov     [rsp+398h+var_360], rax
0x140313ed6  call    cs:__imp_KeEnterCriticalRegion
0x140313edd  nop     dword ptr [rax+rax+00h]
0x140313ee2  lea     r9, [rsp+398h+var_350]; struct _IRP_CONTEXT **
0x140313ee7  mov     r8b, 1; unsigned __int8
0x140313eea  movzx   edx, r8b; unsigned __int8
0x140313eee  xor     ecx, ecx; Irp
0x140313ef0  call    ?RefsInitializeIrpContext@@YAJPEAU_IRP@@EEPEAPEAU_IRP_CONTEXT@@@Z; RefsInitializeIrpContext(_IRP *,uchar,uchar,_IRP_CONTEXT * *)
0x140313ef5  mov     rax, [rbx+90h]
0x140313efc  mov     r14, [rsp+398h+var_350]
0x140313f01  mov     [r14+40h], rax
0x140313f05  cmp     dword ptr [rax+22Ch], 0
0x140313f0c  ja      loc_1403145D7
0x140313f12  test    r12, r12
0x140313f15  jnz     loc_1403143C6
0x140313f1b  test    dil, dil
0x140313f1e  jz      loc_1403145DF
0x140313f24  call    cs:__imp_FsRtlIncrementCcFastReadWait
0x140313f2b  nop     dword ptr [rax+rax+00h]
0x140313f30  cmp     qword ptr [rbx+10h], 0
0x140313f35  jz      loc_1403145F0
0x140313f3b  movzx   eax, word ptr [rbx]
0x140313f3e  cmp     qword ptr [rsi+30h], 1
0x140313f43  jz      loc_1403143D7
0x140313f49  mov     ecx, 802h
0x140313f4e  cmp     ax, cx
0x140313f51  jnz     loc_1403143BA
0x140313f57  mov     rdx, rbx
0x140313f5a  test    r14, r14
0x140313f5d  jz      loc_14031452D
0x140313f63  mov     r9, [rdx+60h]
0x140313f67  mov     rax, [r14+68h]
0x140313f6b  mov     r8, [rax+150h]
0x140313f72  lea     rcx, [rax+0F8h]
0x140313f79  test    r8, r8
0x140313f7c  jnz     loc_14031451A
0x140313f82  mov     [rax+150h], r9
0x140313f89  call    MsInitializeFastResourceOwnerEntry
0x140313f8e  xor     r12d, r12d
0x140313f91  mov     rax, [rdx+60h]
0x140313f95  test    rcx, rcx
0x140313f98  jz      loc_140314499
0x140313f9e  movzx   r8d, dil
0x140313fa2  mov     rdx, rcx
0x140313fa5  mov     rcx, rax
0x140313fa8  call    ??$MsAcquireFastResourceSharedInternal@$0A@@@YAEPEAU_MS_FAST_RESOURCE@@PEAU_MS_FAST_RESOURCE_OWNER_ENTRY@@E@Z; MsAcquireFastResourceSharedInternal<0>(_MS_FAST_RESOURCE *,_MS_FAST_RESOURCE_OWNER_ENTRY *,uchar)
0x140313fad  test    al, al
0x140313faf  jz      loc_1403145F0
0x140313fb5  cmp     qword ptr [rsi+30h], 0
0x140313fba  jz      loc_140314509
0x140313fc0  cmp     byte ptr [rbx+5], 0
0x140313fc4  jz      loc_140314509
0x140313fca  mov     rcx, [rbx+88h]; struct _FCB *
0x140313fd1  call    ?RefsIsFileOpen@@YAEPEBU_FCB@@@Z; RefsIsFileOpen(_FCB const *)
0x140313fd6  test    al, al
0x140313fd8  jz      loc_140314515
0x140313fde  mov     rax, [rbx+0F8h]
0x140313fe5  add     rax, 8
0x140313fe9  cmp     [rsi+28h], rax
0x140313fed  jnz     loc_140314515
0x140313ff3  cmp     byte ptr [rbx+5], 2
0x140313ff7  jz      loc_1403144AA
0x140313ffd  mov     ecx, [rbx+0ACh]
0x140314003  test    cl, 1
0x140314006  jnz     loc_140314362
0x14031400c  mov     rdi, [rbx+20h]
0x140314010  nop
0x140314011  mov     eax, [rbx+0ACh]
0x140314017  cmp     ecx, eax
0x140314019  jnz     loc_140314362
0x14031401f  cmp     [r15+8], rdi
0x140314023  jg      loc_14031447E
0x140314029  mov     ecx, 4; Irp
0x14031402e  call    cs:__imp_IoSetTopLevelIrp
0x140314035  nop     dword ptr [rax+rax+00h]
0x14031403a  nop
0x14031403b  mov     [r13+0], r12d
0x14031403f  mov     r8d, [r15+10h]; Length
0x140314043  mov     r9, [rsp+398h+MdlChain]; MdlChain
0x140314048  mov     rdx, r15; FileOffset
0x14031404b  mov     rcx, rsi; FileObject
0x14031404e  test    r9, r9
0x140314051  jnz     loc_140314233
0x140314057  mov     [rsp+398h+IoStatus], r13; IoStatus
0x14031405c  mov     rax, [rsp+398h+var_348]
0x140314061  mov     [rsp+398h+Buffer], rax; Buffer
0x140314066  movzx   r9d, [rsp+398h+var_365]; Wait
0x14031406c  call    cs:__imp_CcCopyRead
0x140314073  nop     dword ptr [rax+rax+00h]
0x140314078  movzx   edi, al
0x14031407b  mov     [rsp+398h+var_366], al
0x14031407f  test    al, al
0x140314081  jz      short loc_14031408E
0x140314083  mov     rax, [r13+8]
0x140314087  add     rax, [r15]
0x14031408a  mov     [rsi+68h], rax
0x14031408e  test    dil, dil
0x140314091  jz      loc_1403142A8
0x140314097  mov     r8, [rbx+88h]
0x14031409e  mov     [rsp+398h+var_348], r12
0x1403140a3  mov     [rsp+398h+Key], r12d
0x1403140a8  mov     rax, [r8+58h]
0x1403140ac  mov     ecx, [rax+128h]
0x1403140b2  mov     [rsp+398h+Key], ecx
0x1403140b6  mov     r15, [rsp+398h+var_360]
0x1403140bb  test    r15, r15
0x1403140be  jz      short loc_1403140EB
0x1403140c0  mov     eax, [r15+4]
0x1403140c4  test    al, 40h
0x1403140c6  jnz     short loc_1403140EB
0x1403140c8  mov     eax, cs:dword_1402612AC
0x1403140ce  test    al, 40h
0x1403140d0  jz      short loc_14031414F
0x1403140d2  mov     eax, ecx
0x1403140d4  shr     eax, 8
0x1403140d7  test    al, al
0x1403140d9  jnz     short loc_14031414F
0x1403140db  mov     eax, ecx
0x1403140dd  shr     eax, 10h
0x1403140e0  test    al, al
0x1403140e2  jnz     short loc_14031414F
0x1403140e4  test    byte ptr [r8+8], 10h
0x1403140e9  jnz     short loc_14031414F
0x1403140eb  mov     dword ptr [rsp+398h+var_360], r12d
0x1403140f0  xor     r9b, r9b
0x1403140f3  mov     [rsp+398h+var_367], r9b
0x1403140f8  mov     rax, [r8+58h]
0x1403140fc  mov     ecx, [rax+128h]
0x140314102  mov     [rax+128h], r12d
0x140314109  mov     dword ptr [rsp+398h+var_360], ecx
0x14031410d  mov     edx, ecx
0x14031410f  shr     edx, 8
0x140314112  test    cl, cl
0x140314114  jnz     loc_1403141F4
0x14031411a  mov     eax, ecx
0x14031411c  shr     eax, 10h
0x14031411f  test    al, al
0x140314121  jnz     loc_1403141A9
0x140314127  test    dl, dl
0x140314129  jnz     short loc_1403141A9
0x14031412b  test    r15, r15
0x14031412e  jz      short loc_140314140
0x140314130  cmp     byte ptr [r15+50h], 4
0x140314135  jz      short loc_140314140
0x140314137  test    r9b, r9b
0x14031413a  jnz     loc_14031429B
0x140314140  mov     eax, [rsi+50h]
0x140314143  bts     eax, 13h
0x140314147  mov     [rsi+50h], eax
0x14031414a  jmp     loc_1403142A8
0x14031414f  mov     rax, 0FFFFF78000000014h
0x140314159  mov     r11, [rax]
0x14031415c  mov     [rsp+398h+var_348], r11
0x140314161  mov     dword ptr [rsp+398h+Length], r12d
0x140314166  xor     r9b, r9b
0x140314169  mov     [rsp+398h+var_368], r9b
0x14031416e  mov     rax, [r8+58h]
0x140314172  mov     edx, [rax+128h]
0x140314178  mov     [rax+128h], r12d
0x14031417f  mov     dword ptr [rsp+398h+Length], edx
0x140314183  mov     r10d, edx
0x140314186  shr     r10d, 8
0x14031418a  test    dl, dl
0x14031418c  jnz     short loc_1403141FA
0x14031418e  mov     eax, edx
0x140314190  shr     eax, 10h
0x140314193  test    al, al
0x140314195  jnz     short loc_1403141FA
0x140314197  test    r10b, r10b
0x14031419a  jnz     short loc_1403141FA
0x14031419c  test    cl, cl
0x14031419e  jnz     short loc_14031412B
0x1403141a0  mov     [r8+0B8h], r11
0x1403141a7  jmp     short loc_14031412B
0x1403141a9  xor     r10b, r10b
0x1403141ac  mov     rax, 0FFFFF78000000014h
0x1403141b6  mov     r11, [rax]
0x1403141b9  test    dl, dl
0x1403141bb  jnz     loc_140314279
0x1403141c1  shr     ecx, 10h
0x1403141c4  test    cl, cl
0x1403141c6  jnz     loc_14031428A
0x1403141cc  test    r10b, r10b
0x1403141cf  jz      loc_14031412B
0x1403141d5  mov     eax, cs:dword_1402612AC
0x1403141db  test    al, 40h
0x1403141dd  jz      short loc_1403141A0
0x1403141df  test    dl, dl
0x1403141e1  jnz     short loc_1403141A0
0x1403141e3  test    cl, cl
0x1403141e5  jnz     short loc_1403141A0
0x1403141e7  test    byte ptr [r8+8], 10h
0x1403141ec  jz      loc_14031412B
0x1403141f2  jmp     short loc_1403141A0
0x1403141f4  movzx   r10d, cl
0x1403141f8  jmp     short loc_1403141AC
0x1403141fa  test    r10b, r10b
0x1403141fd  jnz     short loc_140314251
0x1403141ff  mov     r15d, edx
0x140314202  shr     r15d, 10h
0x140314206  test    r15b, r15b
0x140314209  jnz     short loc_14031425F
0x14031420b  test    dl, dl
0x14031420d  jz      short loc_140314229
0x14031420f  mov     eax, cs:dword_1402612AC
0x140314215  test    al, 40h
0x140314217  jnz     short loc_14031426D
0x140314219  mov     [r8+0B8h], r11
0x140314220  jmp     short loc_140314229
0x140314222  test    byte ptr [r8+8], 10h
0x140314227  jnz     short loc_140314219
0x140314229  mov     r15, [rsp+398h+var_360]
0x14031422e  jmp     loc_14031419C
0x140314233  mov     [rsp+398h+Buffer], r13; IoStatus
0x140314238  call    cs:__imp_CcMdlRead
0x14031423f  nop     dword ptr [rax+rax+00h]
0x140314244  mov     dil, 1
0x140314247  mov     [rsp+398h+var_366], dil
0x14031424c  jmp     loc_140314097
0x140314251  mov     [r8+70h], r11
0x140314255  mov     r9b, 1
0x140314258  mov     [rsp+398h+var_368], r9b
0x14031425d  jmp     short loc_1403141FF
0x14031425f  mov     [r8+78h], r11
0x140314263  mov     r9b, 1
0x140314266  mov     [rsp+398h+var_368], r9b
0x14031426b  jmp     short loc_14031420B
0x14031426d  test    r10b, r10b
0x140314270  jnz     short loc_140314219
0x140314272  test    r15b, r15b
0x140314275  jnz     short loc_140314219
0x140314277  jmp     short loc_140314222
0x140314279  mov     [r8+70h], r11
0x14031427d  mov     r9b, 1
0x140314280  mov     [rsp+398h+var_367], r9b
0x140314285  jmp     loc_1403141C1
0x14031428a  mov     [r8+78h], r11
0x14031428e  mov     r9b, 1
0x140314291  mov     [rsp+398h+var_367], r9b
0x140314296  jmp     loc_1403141CC
0x14031429b  or      dword ptr [r15+4], 10000h
0x1403142a3  jmp     loc_140314140
0x1403142a8  mov     esi, 802h
0x1403142ad  jmp     short loc_1403142C9
0x1403142af  xor     dil, dil
0x1403142b2  mov     [rsp+398h+var_366], dil
0x1403142b7  mov     esi, 802h
0x1403142bc  xor     r12d, r12d
0x1403142bf  mov     r14, [rsp+398h+var_350]
0x1403142c4  mov     rbx, [rsp+398h+var_330]
0x1403142c9  xor     ecx, ecx; Irp
0x1403142cb  call    cs:__imp_IoSetTopLevelIrp
0x1403142d2  nop     dword ptr [rax+rax+00h]
0x1403142d7  cmp     [rbx], si
0x1403142da  jnz     loc_1403143AE
0x1403142e0  test    r14, r14
0x1403142e3  jz      loc_1403143A6
0x1403142e9  mov     rcx, [r14+68h]
0x1403142ed  mov     rax, [rbx+60h]
0x1403142f1  cmp     [rcx+150h], rax
0x1403142f8  jnz     loc_1403143A6
0x1403142fe  lea     rdx, [rcx+0F8h]
0x140314305  cmp     dword ptr [rdx+48h], 0
0x140314309  jz      loc_1403143A6
0x14031430f  mov     rcx, [rbx+60h]
0x140314313  test    rdx, rdx
0x140314316  jz      short loc_14031435B
0x140314318  call    MsReleaseFastResource
  ... truncated ...
```
