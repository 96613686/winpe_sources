# RefsDismountVolume

- ea: `0x1402ab528`
- end: `0x1402ac000`
- name: `RefsDismountVolume`
- size: `2776`
- prototype: `__int64 __fastcall(struct _IRP_CONTEXT *, PIRP Irp)`
- caller_count: `1`
- callee_count: `21`
- tags: `broker_com_uri`

## callers

- `0x140320e78`

## callees

- `0x140041b40`
- `0x140081670`
- `0x140087ee0`
- `0x14008c400`
- `0x14008dbd0`
- `0x1400ca788`
- `0x1400f130c`
- `0x1400f2328`
- `0x1400f24d0`
- `0x1400f2e64`
- `0x140113aec`
- `0x1401e9ce0`
- `0x140286ebc`
- `0x140287d0c`
- `0x1402ab528`
- `0x1402bc3c8`
- `0x1402d9c90`
- `0x1402e6f54`
- `0x140327ba0`
- `0x140332ea0`
- `0x140334a20`

## import_xrefs

- `ntoskrnl!IoGetActivityIdThread` at `0x1402ab670`
- `ntoskrnl!IoGetActivityIdThread` at `0x1402ab670`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x1402ab915`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x1402abecf`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x140344a79`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x1402ab915`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x1402abecf`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x140344a79`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1402ab747`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1402ab921`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1402ab747`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1402ab921`
- `ntoskrnl!FsRtlDismountComplete` at `0x1402abe32`
- `ntoskrnl!FsRtlDismountComplete` at `0x140344996`
- `ntoskrnl!FsRtlDismountComplete` at `0x1402abe32`
- `ntoskrnl!FsRtlDismountComplete` at `0x140344996`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402ab73b`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402ab73b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402abe95`
- `ntoskrnl!ExFreePoolWithTag` at `0x140344a14`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402abe95`
- `ntoskrnl!ExFreePoolWithTag` at `0x140344a14`

## pseudocode

```c
__int64 __fastcall RefsDismountVolume(struct _IRP_CONTEXT *a1, PIRP Irp)
{
  char v4; // r13
  struct _FILE_OBJECT *v5; // rbx
  __int64 v6; // rdx
  _QWORD *v7; // rcx
  __int64 v8; // r8
  __int64 v9; // rax
  _QWORD *ActivityIdThread; // rax
  char v11; // bl
  struct _VCB *v12; // rdi
  ULONGLONG UnbiasedInterruptTime; // rbx
  const CHAR *v14; // r13
  __int64 v15; // rdx
  __int64 v16; // r8
  int v17; // edx
  char v18; // r8
  __int64 v19; // r10
  __int64 v20; // r11
  __int64 v21; // rcx
  __int64 v22; // rcx
  int v23; // ecx
  unsigned __int64 v24; // rbx
  __int64 v25; // rdx
  __int64 v26; // r8
  int v27; // edx
  char v28; // r8
  __int64 v29; // r10
  __int64 v30; // r11
  __int64 v31; // rcx
  __int64 v32; // rcx
  int v33; // ecx
  __int64 v34; // rax
  int v35; // edx
  unsigned int v36; // ebx
  __int64 v37; // rcx
  unsigned int v38; // r8d
  __int64 v39; // rcx
  unsigned int v40; // r9d
  void *v41; // rcx
  __int64 v43; // [rsp+D0h] [rbp-138h] BYREF
  __int64 v44; // [rsp+D8h] [rbp-130h] BYREF
  struct _VCB *v45; // [rsp+E0h] [rbp-128h] BYREF
  PFILE_OBJECT FileObject; // [rsp+E8h] [rbp-120h]
  __int64 v47; // [rsp+F0h] [rbp-118h]
  __int64 v48; // [rsp+F8h] [rbp-110h]
  __int64 v49; // [rsp+100h] [rbp-108h]
  __int64 v50; // [rsp+108h] [rbp-100h]
  __int64 v51; // [rsp+110h] [rbp-F8h]
  __int64 v52; // [rsp+118h] [rbp-F0h]
  struct _IRP_CONTEXT *v53; // [rsp+120h] [rbp-E8h]
  ULONGLONG v54; // [rsp+128h] [rbp-E0h]
  struct _FILE_OBJECT *v55; // [rsp+130h] [rbp-D8h] BYREF
  ULONGLONG v56; // [rsp+138h] [rbp-D0h]
  PIRP Irpa; // [rsp+140h] [rbp-C8h]
  __int128 v58; // [rsp+148h] [rbp-C0h] BYREF
  __int64 v59; // [rsp+158h] [rbp-B0h]
  _BYTE v60[112]; // [rsp+160h] [rbp-A8h] BYREF

  Irpa = Irp;
  v53 = a1;
  v4 = 0;
  v45 = 0;
  v44 = 0;
  v43 = 0;
  v58 = 0;
  v59 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 54, WPP_9a30568c93c333a296ab3c507849cc83_Traceguids, 3221225473LL);
  }
  if ( (_BYTE)RefsStatusDebugEnabled )
    RefsStatusDebug(-1073741823, 0, "FsCtrl.c", 0xF58u);
  *((_QWORD *)a1 + 1) &= ~8uLL;
  v5 = Irp->Tail.Overlay.CurrentStackLocation->FileObject;
  FileObject = v5;
  RefsDecodeFileObject(a1, v5, &v45, &v55);
  if ( a1 )
  {
    v7 = (_QWORD *)*((_QWORD *)a1 + 10);
    if ( v7 )
    {
      *((_QWORD *)&v58 + 1) = *v7;
      v9 = v7[1];
LABEL_12:
      v59 = v9;
      *(_QWORD *)&v58 = (char *)&v58 + 8;
      goto LABEL_14;
    }
  }
  ActivityIdThread = (_QWORD *)IoGetActivityIdThread(v7, v6);
  if ( ActivityIdThread )
  {
    *((_QWORD *)&v58 + 1) = *ActivityIdThread;
    v9 = ActivityIdThread[1];
    goto LABEL_12;
  }
  *(_QWORD *)&v58 = 0;
LABEL_14:
  if ( !v43 || !_bittest16((const signed __int16 *)(v43 + 88), 9u) )
  {
    v36 = -1073741790;
    RefsCompleteRequest((PSECURITY_SUBJECT_CONTEXT *)a1, Irp, -1073741790);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 55, WPP_9a30568c93c333a296ab3c507849cc83_Traceguids, 3221225506LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741790, 0, "FsCtrl.c", 0xF6Du);
    return v36;
  }
  v55 = v5;
  v11 = 1;
  v47 = 0;
  v12 = v45;
  if ( (*((_DWORD *)a1 + 2) & 0x40000LL) == 0 )
  {
    RefsSendBeginDismountEvent(a1, v45, v8, 0, &v44, &v43, 1);
    KeWaitForSingleObject((char *)v12 + 6128, Executive, 0, 0, 0);
    UnbiasedInterruptTime = KeQueryUnbiasedInterruptTime();
    v56 = UnbiasedInterruptTime;
    v14 = &File;
    if ( (Microsoft_Windows_ReFSEnableBits & 0x400) != 0 )
    {
      v15 = (*((_DWORD *)v12 + 7) >> 29) & 1;
      LODWORD(v44) = *((_DWORD *)v12 + 1593);
      v16 = *((unsigned int *)v12 + 1572);
      if ( (unsigned int)(v16 - 1) > 0x13 )
        v16 = 0;
      v48 = *((_QWORD *)v12 + 794);
      v49 = *((_QWORD *)v12 + 792);
      v50 = *((_QWORD *)v12 + 790);
      v51 = *((_QWORD *)v12 + 788);
      v52 = *((_QWORD *)v12 + 103);
      LODWORD(v43) = RefsGetDeveloperVolumeState(v12, v15, v16);
      v21 = *((_QWORD *)v12 + 26);
      if ( v21 && (v22 = *(_QWORD *)(v21 + 16)) != 0 )
        v23 = (*(_DWORD *)(v22 + 48) >> 8) & 1;
      else
        v23 = 0;
      McTemplateK0jmzuuhtqzzzzzqjqtjs_EtwWriteTransfer(
        v23,
        v17,
        v58,
        (_DWORD)v12 + 6064,
        v20,
        *((_QWORD *)v12 + 770),
        *((_BYTE *)v12 + 792),
        *((_BYTE *)v12 + 793),
        *((_WORD *)v12 + 3364),
        v23,
        v43,
        v52,
        v51,
        v50,
        v49,
        v48,
        v18,
        (__int64)v12 + 6376,
        v44,
        v17,
        (__int64)v12 + 13280,
        v19);
    }
    FsRtlNotifyVolumeEvent(FileObject, 1u);
    v54 = KeQueryUnbiasedInterruptTime();
    v24 = (v54 - UnbiasedInterruptTime) / 0xA / 0x3E8;
    IoPerfPrintTimeInterval(v24, 2, v60);
    if ( (Microsoft_Windows_ReFSEnableBits & 0x400) != 0 )
    {
      if ( *((_QWORD *)v12 + 1310) )
        v14 = (const CHAR *)*((_QWORD *)v12 + 1310);
      v25 = (*((_DWORD *)v12 + 7) >> 29) & 1;
      LODWORD(v43) = *((_DWORD *)v12 + 1593);
      v26 = *((unsigned int *)v12 + 1572);
      if ( (unsigned int)(v26 - 1) > 0x13 )
        v26 = 0;
      v52 = *((_QWORD *)v12 + 794);
      v51 = *((_QWORD *)v12 + 792);
      v50 = *((_QWORD *)v12 + 790);
      v49 = *((_QWORD *)v12 + 788);
      v48 = *((_QWORD *)v12 + 103);
      LODWORD(v44) = RefsGetDeveloperVolumeState(v12, v25, v26);
      v31 = *((_QWORD *)v12 + 26);
      if ( v31 && (v32 = *(_QWORD *)(v31 + 16)) != 0 )
        v33 = (*(_DWORD *)(v32 + 48) >> 8) & 1;
      else
        v33 = 0;
      McTemplateK0jmzuuhtqzzzzzqjqtjszx_EtwWriteTransfer(
        v33,
        v27,
        v58,
        (_DWORD)v12 + 6064,
        v29,
        *((_QWORD *)v12 + 770),
        *((_BYTE *)v12 + 792),
        *((_BYTE *)v12 + 793),
        *((_WORD *)v12 + 3364),
        v33,
        v44,
        v48,
        v49,
        v50,
        v51,
        v52,
        v28,
        (__int64)v12 + 6376,
        v43,
        v27,
        v30,
        (__int64)v14,
        (__int64)v60,
        v24);
    }
    v34 = *((_QWORD *)a1 + 89);
    v11 = 1;
    v4 = 0;
    if ( v34 )
    {
      *(_QWORD *)(v34 + 8) = v56;
      *(_QWORD *)(v34 + 16) = v54;
    }
  }
  v47 = MEMORY[0xFFFFF78000000320];
  while ( 1 )
  {
    RefsAcquireExclusiveVcb(a1, v12, 1u);
    if ( *((_DWORD *)v12 + 58) )
    {
      if ( (*((_DWORD *)v12 + 6) & 2) != 0 )
      {
        if ( *((_DWORD *)v12 + 56) == *((_DWORD *)v12 + 55) + ~*((_DWORD *)v12 + 57) )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          {
            WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 57, WPP_9a30568c93c333a296ab3c507849cc83_Traceguids, 0);
          }
          if ( (_BYTE)RefsStatusDebugEnabled )
            RefsStatusDebug(0, 0, "FsCtrl.c", 0xFDDu);
          goto LABEL_75;
        }
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        {
          v36 = -1073741790;
        }
        else
        {
          v36 = -1073741790;
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            58,
            WPP_9a30568c93c333a296ab3c507849cc83_Traceguids,
            3221225506LL);
        }
        if ( !(_BYTE)RefsStatusDebugEnabled )
          goto LABEL_86;
        v40 = 4069;
      }
      else
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        {
          v36 = -1073741790;
        }
        else
        {
          v36 = -1073741790;
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            56,
            WPP_9a30568c93c333a296ab3c507849cc83_Traceguids,
            3221225506LL);
        }
        if ( !(_BYTE)RefsStatusDebugEnabled )
          goto LABEL_86;
        v40 = 4052;
      }
      RefsStatusDebug(-1073741790, 0, "FsCtrl.c", v40);
      goto LABEL_86;
    }
    v4 = 1;
    v35 = *((_DWORD *)v12 + 6);
    if ( (v35 & 1) == 0 )
      break;
    if ( !v11 )
    {
      v37 = *((_QWORD *)a1 + 1);
      v38 = 0x40000;
      if ( (v37 & 0x40000) == 0 && (v35 & 0x2000000) == 0 )
      {
        *((_DWORD *)a1 + 166) = 8;
        *((_QWORD *)a1 + 1) = v37 | 0x40000;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            60,
            WPP_9a30568c93c333a296ab3c507849cc83_Traceguids,
            3221225864LL);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
          RefsStatusDebug(-1073741432, a1, "FsCtrl.c", 0x1021u);
        RefsRaiseStatusInternal(a1, -1073741432, v38);
        __debugbreak();
        JUMPOUT(0x1402AC000LL);
      }
      if ( RefsUseFlushVolumeParallel )
        RefsFlushVolumeParallel(a1, v12, 95);
      else
        RefsFlushVolumeOriginal(a1, v12, 95);
      v39 = *((_QWORD *)v12 + 14);
      if ( v39 )
        MsDrainLWQueue(v39);
      RefsPerformDismountOnVcb((__int64)a1, (__int64)v12, 0, 0, 0, 0);
      *((_DWORD *)v12 + 6) |= 2u;
      *((_QWORD *)v12 + 109) = (char *)&FileObject->Type + 1;
      RefsSetDirectWritesAllowed(*((struct _VPB **)v12 + 26));
      v36 = 0;
      goto LABEL_58;
    }
    RefsReleaseVcb(a1, v12);
    v11 = 0;
  }
  if ( (v35 & 0x800000) == 0 )
  {
LABEL_75:
    v36 = 0;
    goto LABEL_76;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 59, WPP_9a30568c93c333a296ab3c507849cc83_Traceguids, 3221226094LL);
  }
  if ( (_BYTE)RefsStatusDebugEnabled )
    RefsStatusDebug(-1073741202, 0, "FsCtrl.c", 0xFFFu);
  v36 = -1073741202;
LABEL_58:
  if ( v36 )
    goto LABEL_86;
LABEL_76:
  if ( v4 )
    *((_DWORD *)v12 + 6) |= 0x800000u;
LABEL_86:
  FsRtlDismountComplete(*((_QWORD *)v12 + 24), v36);
  RefsTelemetryDismountTimeTracker(v47, MEMORY[0xFFFFF78000000320], v12, v36);
  RefsReleaseVcb(a1, v12);
  if ( (int)(v36 + 0x80000000) >= 0 && v36 != -1073741202 )
  {
    if ( (*((_DWORD *)a1 + 2) & 0x40000) == 0 )
    {
      v41 = (void *)*((_QWORD *)a1 + 89);
      if ( v41 )
      {
        ExFreePoolWithTag(v41, 0);
        *((_QWORD *)a1 + 89) = 0;
      }
    }
    RefsSendDismountFailedEvent(a1, v12, (struct _REFS_ACTIVITY_ID *)&v58, v36);
    FsRtlNotifyVolumeEvent(FileObject, 2u);
  }
  RefsCompleteRequest((PSECURITY_SUBJECT_CONTEXT *)a1, Irpa, v36);
  return v36;
}

```

## disassembly

```asm
0x1402ab528  mov     r11, rsp
0x1402ab52b  mov     [r11+18h], rbx
0x1402ab52f  mov     [r11+20h], rsi
0x1402ab533  push    rdi
0x1402ab534  push    r12
0x1402ab536  push    r13
0x1402ab538  push    r14
0x1402ab53a  push    r15
0x1402ab53c  sub     rsp, 1E0h
0x1402ab543  mov     rax, cs:__security_cookie
0x1402ab54a  xor     rax, rsp
0x1402ab54d  mov     [rsp+208h+var_38], rax
0x1402ab555  mov     rdi, rdx
0x1402ab558  mov     [rsp+208h+Irp], rdx
0x1402ab560  mov     rsi, rcx
0x1402ab563  mov     [rsp+208h+var_E8], rcx
0x1402ab56b  xor     r13d, r13d
0x1402ab56e  mov     [r11-128h], r13
0x1402ab575  mov     [r11-130h], r13
0x1402ab57c  mov     [r11-138h], r13
0x1402ab583  xorps   xmm0, xmm0
0x1402ab586  xor     eax, eax
0x1402ab588  movups  [rsp+208h+var_C0], xmm0
0x1402ab590  mov     [r11-0B0h], rax
0x1402ab597  lea     rax, WPP_GLOBAL_Control
0x1402ab59e  mov     rcx, cs:WPP_GLOBAL_Control
0x1402ab5a5  mov     r15d, 100h
0x1402ab5ab  mov     r14b, 4
0x1402ab5ae  cmp     rcx, rax
0x1402ab5b1  jz      short loc_1402AB5D9
0x1402ab5b3  test    [rcx+2Ch], r15d
0x1402ab5b7  jz      short loc_1402AB5D9
0x1402ab5b9  cmp     [rcx+29h], r14b
0x1402ab5bd  jb      short loc_1402AB5D9
0x1402ab5bf  lea     edx, [r13+36h]
0x1402ab5c3  mov     r9d, 0C0000001h
0x1402ab5c9  lea     r8, WPP_9a30568c93c333a296ab3c507849cc83_Traceguids
0x1402ab5d0  mov     rcx, [rcx+18h]
0x1402ab5d4  call    WPP_SF_d
0x1402ab5d9  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402ab5df  lea     r12, aFsctrlC; "FsCtrl.c"
0x1402ab5e6  test    al, al
0x1402ab5e8  jz      short loc_1402AB5FF
0x1402ab5ea  mov     r9d, 0F58h; unsigned int
0x1402ab5f0  mov     r8, r12; char *
0x1402ab5f3  xor     edx, edx; struct _IRP_CONTEXT *
0x1402ab5f5  mov     ecx, 0C0000001h; Status
0x1402ab5fa  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x1402ab5ff  and     qword ptr [rsi+8], 0FFFFFFFFFFFFFFF7h
0x1402ab604  mov     rax, [rdi+0B8h]
0x1402ab60b  mov     rbx, [rax+30h]
0x1402ab60f  mov     [rsp+208h+FileObject], rbx
0x1402ab617  mov     [rsp+208h+var_1D8], 1
0x1402ab61c  lea     rax, [rsp+208h+var_138]
0x1402ab624  mov     [rsp+208h+var_1E0], rax
0x1402ab629  lea     rax, [rsp+208h+var_130]
0x1402ab631  mov     [rsp+208h+Timeout], rax
0x1402ab636  lea     r9, [rsp+208h+var_D8]
0x1402ab63e  lea     r8, [rsp+208h+var_128]
0x1402ab646  mov     rdx, rbx
0x1402ab649  mov     rcx, rsi
0x1402ab64c  call    ?RefsDecodeFileObject@@YA?AW4_TYPE_OF_OPEN@@PEAU_IRP_CONTEXT@@PEAU_FILE_OBJECT@@PEAPEAU_VCB@@PEAPEAU_FCB@@PEAPEAU_SCB@@PEAPEAU_CCB@@E@Z; RefsDecodeFileObject(_IRP_CONTEXT *,_FILE_OBJECT *,_VCB * *,_FCB * *,_SCB * *,_CCB * *,uchar)
0x1402ab651  test    rsi, rsi
0x1402ab654  jz      short loc_1402AB670
0x1402ab656  mov     rcx, [rsi+50h]
0x1402ab65a  test    rcx, rcx
0x1402ab65d  jz      short loc_1402AB670
0x1402ab65f  mov     rax, [rcx]
0x1402ab662  mov     qword ptr [rsp+208h+var_C0+8], rax
0x1402ab66a  mov     rax, [rcx+8]
0x1402ab66e  jmp     short loc_1402AB690
0x1402ab670  call    cs:__imp_IoGetActivityIdThread
0x1402ab677  nop     dword ptr [rax+rax+00h]
0x1402ab67c  test    rax, rax
0x1402ab67f  jz      short loc_1402AB6AA
0x1402ab681  mov     rcx, [rax]
0x1402ab684  mov     qword ptr [rsp+208h+var_C0+8], rcx
0x1402ab68c  mov     rax, [rax+8]
0x1402ab690  mov     [rsp+208h+var_B0], rax
0x1402ab698  lea     rax, [rsp+208h+var_C0+8]
0x1402ab6a0  mov     qword ptr [rsp+208h+var_C0], rax
0x1402ab6a8  jmp     short loc_1402AB6B2
0x1402ab6aa  mov     qword ptr [rsp+208h+var_C0], r13
0x1402ab6b2  mov     rax, [rsp+208h+var_138]
0x1402ab6ba  test    rax, rax
0x1402ab6bd  jz      loc_1402ABEF0
0x1402ab6c3  bt      word ptr [rax+58h], 9
0x1402ab6c9  jnb     loc_1402ABEF0
0x1402ab6cf  mov     [rsp+208h+var_D8], rbx
0x1402ab6d7  mov     [rsp+208h+var_148], r13b
0x1402ab6df  mov     [rsp+208h+var_146], r13b
0x1402ab6e7  mov     bl, 1
0x1402ab6e9  mov     [rsp+208h+var_147], bl
0x1402ab6f0  mov     [rsp+208h+var_118], r13
0x1402ab6f8  mov     [rsp+208h+var_144], 0C0000001h
0x1402ab703  mov     eax, [rsi+8]
0x1402ab706  mov     rdi, [rsp+208h+var_128]
0x1402ab70e  bt      rax, 12h
0x1402ab713  jb      loc_1402ABB69
0x1402ab719  xor     r9d, r9d
0x1402ab71c  mov     rdx, rdi
0x1402ab71f  mov     rcx, rsi
0x1402ab722  call    ?RefsSendBeginDismountEvent@@YAXPEAU_IRP_CONTEXT@@PEAU_VCB@@PEAU_REFS_ACTIVITY_ID@@W4_REFS_DISMOUNT_REASON@@@Z; RefsSendBeginDismountEvent(_IRP_CONTEXT *,_VCB *,_REFS_ACTIVITY_ID *,_REFS_DISMOUNT_REASON)
0x1402ab727  lea     rcx, [rdi+17F0h]; Object
0x1402ab72e  mov     [rsp+208h+Timeout], r13; Timeout
0x1402ab733  xor     r9d, r9d; Alertable
0x1402ab736  xor     r8d, r8d; WaitMode
0x1402ab739  xor     edx, edx; WaitReason
0x1402ab73b  call    cs:__imp_KeWaitForSingleObject
0x1402ab742  nop     dword ptr [rax+rax+00h]
0x1402ab747  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x1402ab74e  nop     dword ptr [rax+rax+00h]
0x1402ab753  mov     rbx, rax
0x1402ab756  mov     [rsp+208h+var_D0], rax
0x1402ab75e  lea     r13, File
0x1402ab765  test    byte ptr cs:Microsoft_Windows_ReFSEnableBits+1, r14b
0x1402ab76c  jz      loc_1402AB908
0x1402ab772  lea     r11, [rdi+1A30h]
0x1402ab779  mov     rcx, [r11+0EC0h]
0x1402ab780  mov     r10, r13
0x1402ab783  test    rcx, rcx
0x1402ab786  cmovnz  r10, rcx
0x1402ab78a  mov     edx, [rdi+1Ch]
0x1402ab78d  shr     edx, 1Dh
0x1402ab790  and     edx, 1
0x1402ab793  mov     eax, [rdi+18E4h]
0x1402ab799  mov     dword ptr [rsp+208h+var_130], eax
0x1402ab7a0  mov     r8d, [rdi+1890h]
0x1402ab7a7  lea     ecx, [r8-1]
0x1402ab7ab  xor     eax, eax
0x1402ab7ad  cmp     ecx, 13h
0x1402ab7b0  cmova   r8d, eax
0x1402ab7b4  mov     rax, [rdi+18D0h]
0x1402ab7bb  mov     [rsp+208h+var_110], rax
0x1402ab7c3  mov     rax, [rdi+18C0h]
0x1402ab7ca  mov     [rsp+208h+var_108], rax
0x1402ab7d2  mov     rax, [rdi+18B0h]
0x1402ab7d9  mov     [rsp+208h+var_100], rax
0x1402ab7e1  mov     rax, [rdi+18A0h]
0x1402ab7e8  mov     [rsp+208h+var_F8], rax
0x1402ab7f0  mov     rax, [rdi+338h]
0x1402ab7f7  mov     [rsp+208h+var_F0], rax
0x1402ab7ff  mov     rcx, rdi
0x1402ab802  call    ?RefsGetDeveloperVolumeState@@YA?AW4REFS_DEV_VOL_STATE@@PEAU_VCB@@@Z; RefsGetDeveloperVolumeState(_VCB *)
0x1402ab807  mov     dword ptr [rsp+208h+var_138], eax
0x1402ab80e  mov     rcx, [rdi+0D0h]
0x1402ab815  test    rcx, rcx
0x1402ab818  jz      short loc_1402AB82E
0x1402ab81a  mov     rcx, [rcx+10h]
0x1402ab81e  test    rcx, rcx
0x1402ab821  jz      short loc_1402AB82E
0x1402ab823  mov     ecx, [rcx+30h]
0x1402ab826  shr     ecx, 8
0x1402ab829  and     ecx, 1
0x1402ab82c  jmp     short loc_1402AB830
0x1402ab82e  xor     ecx, ecx
0x1402ab830  lea     r9, [rdi+17B0h]
0x1402ab837  mov     [rsp+208h+var_160], r10
0x1402ab83f  lea     rax, [rdi+33E0h]
0x1402ab846  mov     [rsp+208h+var_168], rax
0x1402ab84e  mov     [rsp+208h+var_170], edx
0x1402ab855  mov     eax, dword ptr [rsp+208h+var_130]
0x1402ab85c  mov     [rsp+208h+var_178], eax
0x1402ab863  lea     rax, [rdi+18E8h]
0x1402ab86a  mov     [rsp+208h+var_180], rax
0x1402ab872  mov     [rsp+208h+var_188], r8d
0x1402ab87a  mov     rax, [rsp+208h+var_110]
0x1402ab882  mov     [rsp+208h+var_190], rax
0x1402ab887  mov     rax, [rsp+208h+var_108]
0x1402ab88f  mov     [rsp+208h+var_198], rax
0x1402ab894  mov     rax, [rsp+208h+var_100]
0x1402ab89c  mov     [rsp+208h+var_1A0], rax
0x1402ab8a1  mov     rax, [rsp+208h+var_F8]
0x1402ab8a9  mov     [rsp+208h+var_1A8], rax
0x1402ab8ae  mov     rax, [rsp+208h+var_F0]
0x1402ab8b6  mov     [rsp+208h+var_1B0], rax
0x1402ab8bb  mov     eax, dword ptr [rsp+208h+var_138]
0x1402ab8c2  mov     [rsp+208h+var_1B8], eax
0x1402ab8c6  mov     [rsp+208h+var_1C0], ecx
0x1402ab8ca  movzx   eax, word ptr [rdi+1A48h]
0x1402ab8d1  mov     [rsp+208h+var_1C8], ax
0x1402ab8d6  mov     al, [rdi+319h]
0x1402ab8dc  mov     [rsp+208h+var_1D0], al
0x1402ab8e0  mov     al, [rdi+318h]
0x1402ab8e6  mov     [rsp+208h+var_1D8], al
0x1402ab8ea  mov     rax, [rdi+1810h]
0x1402ab8f1  mov     [rsp+208h+var_1E0], rax
0x1402ab8f6  mov     [rsp+208h+Timeout], r11
0x1402ab8fb  mov     r8, qword ptr [rsp+208h+var_C0]
0x1402ab903  call    McTemplateK0jmzuuhtqzzzzzqjqtjs_EtwWriteTransfer
0x1402ab908  mov     edx, 1; EventCode
0x1402ab90d  mov     rcx, [rsp+208h+FileObject]; FileObject
0x1402ab915  call    cs:__imp_FsRtlNotifyVolumeEvent
0x1402ab91c  nop     dword ptr [rax+rax+00h]
0x1402ab921  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x1402ab928  nop     dword ptr [rax+rax+00h]
0x1402ab92d  mov     [rsp+208h+var_E0], rax
0x1402ab935  mov     rcx, rax
0x1402ab938  sub     rcx, rbx
0x1402ab93b  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1402ab945  mul     rcx
0x1402ab948  mov     rbx, rdx
0x1402ab94b  shr     rbx, 3
0x1402ab94f  mov     rax, 624DD2F1A9FBE77h
0x1402ab959  mul     rbx
0x1402ab95c  sub     rbx, rdx
0x1402ab95f  shr     rbx, 1
0x1402ab962  add     rbx, rdx
0x1402ab965  shr     rbx, 9
0x1402ab969  lea     r8, [rsp+208h+var_A8]
0x1402ab971  mov     edx, 2
0x1402ab976  mov     rcx, rbx
0x1402ab979  call    IoPerfPrintTimeInterval
0x1402ab97e  test    byte ptr cs:Microsoft_Windows_ReFSEnableBits+1, r14b
0x1402ab985  jz      loc_1402ABB36
0x1402ab98b  lea     r10, [rdi+1A30h]
0x1402ab992  mov     rax, [r10+0EC0h]
0x1402ab999  test    rax, rax
0x1402ab99c  cmovnz  r13, rax
0x1402ab9a0  lea     r11, [rdi+33E0h]
0x1402ab9a7  mov     edx, [rdi+1Ch]
0x1402ab9aa  shr     edx, 1Dh
0x1402ab9ad  and     edx, 1
0x1402ab9b0  mov     eax, [rdi+18E4h]
0x1402ab9b6  mov     dword ptr [rsp+208h+var_138], eax
0x1402ab9bd  mov     r8d, [rdi+1890h]
0x1402ab9c4  lea     ecx, [r8-1]
0x1402ab9c8  xor     eax, eax
0x1402ab9ca  cmp     ecx, 13h
0x1402ab9cd  cmova   r8d, eax
0x1402ab9d1  mov     rax, [rdi+18D0h]
0x1402ab9d8  mov     [rsp+208h+var_F0], rax
0x1402ab9e0  mov     rax, [rdi+18C0h]
0x1402ab9e7  mov     [rsp+208h+var_F8], rax
0x1402ab9ef  mov     rax, [rdi+18B0h]
0x1402ab9f6  mov     [rsp+208h+var_100], rax
0x1402ab9fe  mov     rax, [rdi+18A0h]
0x1402aba05  mov     [rsp+208h+var_108], rax
0x1402aba0d  mov     rax, [rdi+338h]
0x1402aba14  mov     [rsp+208h+var_110], rax
0x1402aba1c  mov     rcx, rdi
0x1402aba1f  call    ?RefsGetDeveloperVolumeState@@YA?AW4REFS_DEV_VOL_STATE@@PEAU_VCB@@@Z; RefsGetDeveloperVolumeState(_VCB *)
0x1402aba24  mov     dword ptr [rsp+208h+var_130], eax
0x1402aba2b  mov     rcx, [rdi+0D0h]
0x1402aba32  test    rcx, rcx
0x1402aba35  jz      short loc_1402ABA4B
0x1402aba37  mov     rcx, [rcx+10h]
0x1402aba3b  test    rcx, rcx
0x1402aba3e  jz      short loc_1402ABA4B
0x1402aba40  mov     ecx, [rcx+30h]
0x1402aba43  shr     ecx, 8
0x1402aba46  and     ecx, 1
0x1402aba49  jmp     short loc_1402ABA4D
0x1402aba4b  xor     ecx, ecx
0x1402aba4d  lea     r9, [rdi+17B0h]
0x1402aba54  mov     [rsp+208h+var_150], rbx
0x1402aba5c  lea     rax, [rsp+208h+var_A8]
0x1402aba64  mov     [rsp+208h+var_158], rax
0x1402aba6c  mov     [rsp+208h+var_160], r13
0x1402aba74  mov     [rsp+208h+var_168], r11
0x1402aba7c  mov     [rsp+208h+var_170], edx
0x1402aba83  mov     eax, dword ptr [rsp+208h+var_138]
0x1402aba8a  mov     [rsp+208h+var_178], eax
0x1402aba91  lea     rax, [rdi+18E8h]
0x1402aba98  mov     [rsp+208h+var_180], rax
0x1402abaa0  mov     [rsp+208h+var_188], r8d
0x1402abaa8  mov     rax, [rsp+208h+var_F0]
0x1402abab0  mov     [rsp+208h+var_190], rax
0x1402abab5  mov     rax, [rsp+208h+var_F8]
0x1402ababd  mov     [rsp+208h+var_198], rax
0x1402abac2  mov     rax, [rsp+208h+var_100]
0x1402abaca  mov     [rsp+208h+var_1A0], rax
0x1402abacf  mov     rax, [rsp+208h+var_108]
0x1402abad7  mov     [rsp+208h+var_1A8], rax
0x1402abadc  mov     rax, [rsp+208h+var_110]
0x1402abae4  mov     [rsp+208h+var_1B0], rax
0x1402abae9  mov     eax, dword ptr [rsp+208h+var_130]
0x1402abaf0  mov     [rsp+208h+var_1B8], eax
0x1402abaf4  mov     [rsp+208h+var_1C0], ecx
0x1402abaf8  movzx   eax, word ptr [rdi+1A48h]
0x1402abaff  mov     [rsp+208h+var_1C8], ax
0x1402abb04  mov     al, [rdi+319h]
0x1402abb0a  mov     [rsp+208h+var_1D0], al
0x1402abb0e  mov     al, [rdi+318h]
0x1402abb14  mov     [rsp+208h+var_1D8], al
0x1402abb18  mov     rax, [rdi+1810h]
0x1402abb1f  mov     [rsp+208h+var_1E0], rax
0x1402abb24  mov     [rsp+208h+Timeout], r10
0x1402abb29  mov     r8, qword ptr [rsp+208h+var_C0]
0x1402abb31  call    McTemplateK0jmzuuhtqzzzzzqjqtjszx_EtwWriteTransfer
0x1402abb36  mov     rax, [rsi+2C8h]
0x1402abb3d  mov     bl, [rsp+208h+var_147]
0x1402abb44  mov     r13b, [rsp+208h+var_146]
0x1402abb4c  test    rax, rax
0x1402abb4f  jz      short loc_1402ABB69
0x1402abb51  mov     rcx, [rsp+208h+var_D0]
0x1402abb59  mov     [rax+8], rcx
0x1402abb5d  mov     rcx, [rsp+208h+var_E0]
0x1402abb65  mov     [rax+10h], rcx
0x1402abb69  mov     rax, 0FFFFF78000000320h
  ... truncated ...
```
