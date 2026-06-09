# FatMoveFile

- ea: `0x1400412a8`
- end: `0x140041fd3`
- name: `FatMoveFile`
- size: `3371`
- prototype: `__int64 __fastcall(int, PIRP Irp)`
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x140042ac0`

## callees

- `0x1400019b8`
- `0x14000c680`
- `0x140020734`
- `0x1400210d0`
- `0x140022870`
- `0x140023df4`
- `0x14002486c`
- `0x1400319bc`
- `0x140038eb4`
- `0x14003d880`
- `0x14003e40c`
- `0x14003e78c`
- `0x14003ea88`
- `0x14003eb84`
- `0x14003ed04`
- `0x14003ee98`
- `0x14003f50c`
- `0x1400412a8`
- `0x140041fdc`
- `0x1400426ec`
- `0x1400465f4`
- `0x14004a1d4`

## import_xrefs

- `ntoskrnl!FsRtlNumberOfRunsInLargeMcb` at `0x140041923`
- `ntoskrnl!FsRtlNumberOfRunsInLargeMcb` at `0x140041923`
- `ntoskrnl!KeInitializeEvent` at `0x14004165f`
- `ntoskrnl!KeInitializeEvent` at `0x140041a4a`
- `ntoskrnl!KeInitializeEvent` at `0x14004165f`
- `ntoskrnl!KeInitializeEvent` at `0x140041a4a`
- `ntoskrnl!KeClearEvent` at `0x140041b29`
- `ntoskrnl!KeClearEvent` at `0x140041edc`
- `ntoskrnl!KeClearEvent` at `0x140041b29`
- `ntoskrnl!KeClearEvent` at `0x140041edc`
- `ntoskrnl!IoBuildSynchronousFsdRequest` at `0x140041a8f`
- `ntoskrnl!IoBuildSynchronousFsdRequest` at `0x140041b6e`
- `ntoskrnl!IoBuildSynchronousFsdRequest` at `0x140041a8f`
- `ntoskrnl!IoBuildSynchronousFsdRequest` at `0x140041b6e`
- `ntoskrnl!IofCallDriver` at `0x140041abe`
- `ntoskrnl!IofCallDriver` at `0x140041ba8`
- `ntoskrnl!IofCallDriver` at `0x140041abe`
- `ntoskrnl!IofCallDriver` at `0x140041ba8`
- `ntoskrnl!KeWaitForSingleObject` at `0x140041ae6`
- `ntoskrnl!KeWaitForSingleObject` at `0x140041bd0`
- `ntoskrnl!KeWaitForSingleObject` at `0x140041ae6`
- `ntoskrnl!KeWaitForSingleObject` at `0x140041bd0`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x140041b07`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x140041bf1`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x140041d73`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x140041b07`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x140041bf1`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x140041d73`
- `ntoskrnl!KeSetEvent` at `0x140041de2`
- `ntoskrnl!KeSetEvent` at `0x14005f056`
- `ntoskrnl!KeSetEvent` at `0x14005f175`
- `ntoskrnl!KeSetEvent` at `0x140041de2`
- `ntoskrnl!KeSetEvent` at `0x14005f056`
- `ntoskrnl!KeSetEvent` at `0x14005f175`
- `ntoskrnl!IoIs32bitProcess` at `0x1400413d8`
- `ntoskrnl!IoIs32bitProcess` at `0x1400413d8`
- `ntoskrnl!ObfReferenceObject` at `0x1400416dd`
- `ntoskrnl!ObfReferenceObject` at `0x1400416dd`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400414be`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400414be`
- `ntoskrnl!IoFileObjectType` at `0x1400414af`
- `ntoskrnl!CcCanIWrite` at `0x140041779`
- `ntoskrnl!CcCanIWrite` at `0x140041779`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400419e1`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140041df4`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005f06c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005f18b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400419e1`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140041df4`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005f06c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005f18b`
- `ntoskrnl!ExReleaseResourceLite` at `0x140041703`
- `ntoskrnl!ExReleaseResourceLite` at `0x140041a05`
- `ntoskrnl!ExReleaseResourceLite` at `0x140041e10`
- `ntoskrnl!ExReleaseResourceLite` at `0x140041e20`
- `ntoskrnl!ExReleaseResourceLite` at `0x140041f9d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005f087`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005f0a2`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005f1a6`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005f1c1`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005f28b`
- `ntoskrnl!ExReleaseResourceLite` at `0x140041703`
- `ntoskrnl!ExReleaseResourceLite` at `0x140041a05`
- `ntoskrnl!ExReleaseResourceLite` at `0x140041e10`
- `ntoskrnl!ExReleaseResourceLite` at `0x140041e20`
- `ntoskrnl!ExReleaseResourceLite` at `0x140041f9d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005f087`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005f0a2`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005f1a6`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005f1c1`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005f28b`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x140041f6d`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x140041f88`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x14005efe8`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x14005f002`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x14005f107`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x14005f121`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x14005f221`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x14005f23b`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x140041f6d`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x140041f88`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x14005efe8`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x14005f002`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x14005f107`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x14005f121`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x14005f221`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x14005f23b`
- `ntoskrnl!FsRtlInitializeLargeMcb` at `0x140041678`
- `ntoskrnl!FsRtlInitializeLargeMcb` at `0x140041696`
- `ntoskrnl!FsRtlInitializeLargeMcb` at `0x140041678`
- `ntoskrnl!FsRtlInitializeLargeMcb` at `0x140041696`
- `ntoskrnl!CcUnpinData` at `0x140041cc3`
- `ntoskrnl!CcUnpinData` at `0x140041f49`
- `ntoskrnl!CcUnpinData` at `0x14005efc7`
- `ntoskrnl!CcUnpinData` at `0x14005f0e6`
- `ntoskrnl!CcUnpinData` at `0x14005f200`
- `ntoskrnl!CcUnpinData` at `0x140041cc3`
- `ntoskrnl!CcUnpinData` at `0x140041f49`
- `ntoskrnl!CcUnpinData` at `0x14005efc7`
- `ntoskrnl!CcUnpinData` at `0x14005f0e6`
- `ntoskrnl!CcUnpinData` at `0x14005f200`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041f0c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005ef8c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041f0c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005ef8c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400417e3`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400417e3`
- `ntoskrnl!ExRaiseStatus` at `0x140041aa8`
- `ntoskrnl!ExRaiseStatus` at `0x140041b15`
- `ntoskrnl!ExRaiseStatus` at `0x140041b8a`
- `ntoskrnl!ExRaiseStatus` at `0x140041bff`
- `ntoskrnl!ExRaiseStatus` at `0x140041d81`
- `ntoskrnl!ExRaiseStatus` at `0x140041aa8`
- `ntoskrnl!ExRaiseStatus` at `0x140041b15`
- `ntoskrnl!ExRaiseStatus` at `0x140041b8a`
- `ntoskrnl!ExRaiseStatus` at `0x140041bff`
- `ntoskrnl!ExRaiseStatus` at `0x140041d81`
- `ntoskrnl!ObfDereferenceObject` at `0x1400414f4`
- `ntoskrnl!ObfDereferenceObject` at `0x1400416ee`
- `ntoskrnl!ObfDereferenceObject` at `0x140041fae`
- `ntoskrnl!ObfDereferenceObject` at `0x14005f0b3`
- `ntoskrnl!ObfDereferenceObject` at `0x14005f1d2`
- `ntoskrnl!ObfDereferenceObject` at `0x14005f29c`
- `ntoskrnl!ObfDereferenceObject` at `0x1400414f4`
- `ntoskrnl!ObfDereferenceObject` at `0x1400416ee`
- `ntoskrnl!ObfDereferenceObject` at `0x140041fae`
- `ntoskrnl!ObfDereferenceObject` at `0x14005f0b3`
- `ntoskrnl!ObfDereferenceObject` at `0x14005f1d2`
- `ntoskrnl!ObfDereferenceObject` at `0x14005f29c`

## pseudocode

```c
__int64 __fastcall FatMoveFile(_DWORD *a1, PIRP Irp)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rsi
  unsigned int Options; // esi
  struct _IRP *MasterIrp; // rbx
  __int64 Flags; // r12
  unsigned int v8; // eax
  LONG IrpCount; // edx
  __int64 v10; // r14
  unsigned int v11; // r8d
  NTSTATUS v12; // esi
  PVOID v14; // rcx
  unsigned int v15; // ebx
  int v16; // eax
  int v17; // r13d
  _WORD *v18; // rsi
  __int64 v19; // r14
  unsigned __int8 v20; // cl
  LONG v21; // ebx
  void *v22; // r12
  char v23; // r13
  void *v24; // rbx
  ULONG v25; // edx
  ULONG v26; // ebx
  PVOID PoolWithTag; // rax
  unsigned int v28; // ebx
  ULONG v29; // ebx
  IRP *v30; // rax
  int Status; // eax
  NTSTATUS v32; // eax
  PIRP v33; // rax
  int v34; // eax
  NTSTATUS v35; // eax
  unsigned int v36; // ebx
  __int64 v37; // r9
  unsigned int v38; // ebx
  __int64 v39; // rcx
  __int64 v40; // rdx
  __int64 v41; // r8
  __int64 v42; // r9
  __int64 v43; // rcx
  NTSTATUS v44; // eax
  NTSTATUS v45; // eax
  __int64 v46; // rdx
  __int64 v47; // r8
  __int64 v48; // r9
  char v49; // [rsp+51h] [rbp-187h]
  char v50; // [rsp+52h] [rbp-186h]
  char v51; // [rsp+53h] [rbp-185h]
  PVOID Bcb; // [rsp+58h] [rbp-180h] BYREF
  _WORD *v53; // [rsp+60h] [rbp-178h] BYREF
  int v54[2]; // [rsp+68h] [rbp-170h] BYREF
  PVOID Object; // [rsp+70h] [rbp-168h] BYREF
  int v56; // [rsp+78h] [rbp-160h]
  unsigned int v57; // [rsp+7Ch] [rbp-15Ch] BYREF
  unsigned int v58; // [rsp+80h] [rbp-158h] BYREF
  unsigned int v59; // [rsp+84h] [rbp-154h]
  int v60; // [rsp+88h] [rbp-150h]
  unsigned int v61; // [rsp+8Ch] [rbp-14Ch]
  LONG v62; // [rsp+90h] [rbp-148h]
  LONG v63; // [rsp+94h] [rbp-144h] BYREF
  ULONG NumberOfBytes; // [rsp+98h] [rbp-140h]
  ULONG NumberOfBytes_4; // [rsp+9Ch] [rbp-13Ch] BYREF
  unsigned int v66; // [rsp+A0h] [rbp-138h] BYREF
  unsigned int v67; // [rsp+A4h] [rbp-134h] BYREF
  __int64 v68; // [rsp+A8h] [rbp-130h] BYREF
  union _LARGE_INTEGER v69; // [rsp+B0h] [rbp-128h] BYREF
  int v70; // [rsp+B8h] [rbp-120h] BYREF
  unsigned int v71; // [rsp+BCh] [rbp-11Ch]
  __int64 v72; // [rsp+C0h] [rbp-118h] BYREF
  union _LARGE_INTEGER v73; // [rsp+C8h] [rbp-110h]
  void *v74; // [rsp+D0h] [rbp-108h]
  LARGE_MCB v75; // [rsp+D8h] [rbp-100h] BYREF
  __int64 v76; // [rsp+F8h] [rbp-E0h] BYREF
  union _LARGE_INTEGER StartingOffset; // [rsp+100h] [rbp-D8h] BYREF
  struct _KEVENT v78; // [rsp+108h] [rbp-D0h] BYREF
  struct _KEVENT Event; // [rsp+120h] [rbp-B8h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+138h] [rbp-A0h] BYREF
  LARGE_MCB Mcb; // [rsp+148h] [rbp-90h] BYREF
  union _LARGE_INTEGER v82; // [rsp+168h] [rbp-70h]
  unsigned int v83; // [rsp+170h] [rbp-68h]
  __int128 v84; // [rsp+178h] [rbp-60h] BYREF
  __int128 v85; // [rsp+188h] [rbp-50h]
  unsigned int v86; // [rsp+1E8h] [rbp+10h] BYREF
  unsigned int v87; // [rsp+1F0h] [rbp+18h]
  unsigned int v88; // [rsp+1F8h] [rbp+20h] BYREF

  Object = 0;
  *(_QWORD *)v54 = 0;
  v53 = 0;
  v68 = 0;
  StartingOffset.QuadPart = 0;
  v69.QuadPart = 0;
  NumberOfBytes_4 = 0;
  v86 = 0;
  v67 = 0;
  v58 = 0;
  v57 = 0;
  v66 = 0;
  memset(&Mcb, 0, sizeof(Mcb));
  memset(&v75, 0, sizeof(v75));
  memset(&Event, 0, sizeof(Event));
  v49 = 0;
  v50 = 0;
  v51 = 0;
  v72 = 0;
  Bcb = 0;
  v59 = a1[17];
  v84 = 0;
  v85 = 0;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  a1[17] = v59 | 2;
  if ( (unsigned int)FatDecodeFileObject(CurrentStackLocation->FileObject, v54, &v53, &v68) == 4
    && v68
    && (*(_DWORD *)(v68 + 4) & 0x20000) != 0 )
  {
    Options = CurrentStackLocation->Parameters.Create.Options;
    MasterIrp = Irp->AssociatedIrp.MasterIrp;
    if ( IoIs32bitProcess(Irp) )
    {
      if ( MasterIrp && Options >= 0x20 )
      {
        *(_QWORD *)&v84 = *(int *)&MasterIrp->Type;
        *((_QWORD *)&v84 + 1) = MasterIrp->MdlAddress;
        *(_QWORD *)&v85 = *(_QWORD *)&MasterIrp->Flags;
        DWORD2(v85) = MasterIrp->AssociatedIrp.IrpCount;
        MasterIrp = (struct _IRP *)&v84;
        goto LABEL_10;
      }
    }
    else if ( MasterIrp && Options >= 0x20 )
    {
LABEL_10:
      if ( !HIDWORD(MasterIrp->MdlAddress) && !*(&MasterIrp->Flags + 1) )
      {
        Flags = MasterIrp->Flags;
        v8 = Flags + 2;
        v61 = Flags + 2;
        if ( (unsigned int)Flags < 0xFFFFFFFE )
        {
          IrpCount = MasterIrp->AssociatedIrp.IrpCount;
          if ( IrpCount + v8 >= v8 )
          {
            v10 = *(_QWORD *)v54;
            v11 = *(_DWORD *)(*(_QWORD *)v54 + 364LL);
            if ( IrpCount + v8 <= v11 + 2 && LODWORD(MasterIrp->MdlAddress) < v11 && IrpCount )
            {
              v12 = ObReferenceObjectByHandle(
                      *(HANDLE *)&MasterIrp->Type,
                      0,
                      (POBJECT_TYPE)IoFileObjectType,
                      Irp->RequestorMode,
                      &Object,
                      0);
              if ( v12 < 0 )
              {
                FatCompleteRequest_Real(a1, Irp);
                return (unsigned int)v12;
              }
              v14 = Object;
              if ( *((_QWORD *)Object + 2) == *(_QWORD *)(v10 + 192) )
              {
                v16 = FatDecodeFileObject(Object, v54, &v53, &v68);
                v17 = v16;
                if ( (unsigned int)(v16 - 2) <= 1 )
                {
                  v18 = v53;
                  v19 = *(_QWORD *)v54;
                  if ( v16 != 3 || (*v53 != 1284 || *(_BYTE *)(*(_QWORD *)v54 + 376LL) == 32) && MasterIrp->MdlAddress )
                  {
                    v74 = 0;
                    v59 &= 0xCu;
                    v56 = 0;
                    FatMoveFileNeedsWriteThrough(a1, v53, v59);
                    if ( (*(_DWORD *)(v19 + 200) & 0x400000) != 0 && (*((_DWORD *)v18 + 48) & 0x8000) != 0 )
                      a1[17] |= 0x4000u;
                    a1[17] |= 0x80000000;
                    v20 = *(_BYTE *)(v19 + 378);
                    v60 = v20;
                    v87 = LODWORD(MasterIrp->MdlAddress) << v20;
                    v71 = v87;
                    v21 = MasterIrp->AssociatedIrp.IrpCount << v20;
                    v62 = v21;
                    v63 = v21;
                    v73.QuadPart = *(_QWORD *)(v19 + 352) + (Flags << v20);
                    v82 = v73;
                    v69 = v73;
                    v22 = 0;
                    v74 = 0;
                    if ( v21 + v87 >= v87 )
                    {
                      KeInitializeEvent(&Event, NotificationEvent, 0);
                      FsRtlInitializeLargeMcb(&Mcb, PagedPool);
                      v49 = 1;
                      FsRtlInitializeLargeMcb(&v75, PagedPool);
                      v50 = 1;
                      if ( v17 == 3 )
                      {
                        FatAcquireExclusiveFcb(a1, v18);
                        FatVerifyFcb(a1, v18);
                        FatOpenDirectoryFile(a1);
                        v24 = (void *)*((_QWORD *)v18 + 43);
                        ObfReferenceObject(v24);
                        ObfDereferenceObject(Object);
                        Object = v24;
                        ExReleaseResourceLite(*((PERESOURCE *)v18 + 1));
                        v23 = 0;
                        v21 = v62;
                      }
                      else
                      {
                        v23 = 0;
                      }
                      v25 = 0x10000;
                      if ( (unsigned int)(1 << v60) > 0x10000 )
                        v25 = 1 << v60;
                      for ( NumberOfBytes = v25; v21; v25 = NumberOfBytes )
                      {
                        v70 = 0;
                        v76 = 0;
                        v88 = 0;
                        CcCanIWrite((PFILE_OBJECT)Object, v25, 1u, 0);
                        FatAcquireExclusiveFcb(a1, v18);
                        v23 = 1;
                        FatVerifyFcb(a1, v18);
                        if ( (*((_DWORD *)v18 + 48) & 0x4000) != 0 && (*(_DWORD *)(v68 + 4) & 0x80000) == 0 )
                        {
                          v15 = -1073741790;
                          goto LABEL_86;
                        }
                        if ( !v22 )
                        {
                          v26 = NumberOfBytes;
                          PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)1552, NumberOfBytes, 0x47746146u);
                          v22 = PoolWithTag;
                          if ( !ExPoolZeroingNativelySupported && PoolWithTag )
                            memset(PoolWithTag, 0, v26);
                          v74 = v22;
                        }
                        FatComputeMoveFileParameter(
                          (_DWORD)a1,
                          (_DWORD)v18,
                          NumberOfBytes,
                          v87,
                          (__int64)&v63,
                          (__int64)&v86,
                          (__int64)&NumberOfBytes_4,
                          (__int64)&StartingOffset);
                        v62 = v63;
                        if ( !v63 )
                          break;
                        v28 = v61;
                        FatComputeMoveFileSplicePoints(
                          (_DWORD)a1,
                          (_DWORD)v18,
                          v87,
                          v61,
                          v86,
                          (__int64)&v67,
                          (__int64)&v58,
                          (__int64)&v57,
                          (__int64)&v66,
                          (__int64)&Mcb);
                        v88 = v86;
                        FatAllocateDiskSpace((int)a1, v19, 1, (__int64)&v75);
                        v51 = 1;
                        if ( FsRtlNumberOfRunsInLargeMcb(&v75) != 1
                          || !(unsigned __int8)FatGetNextMcbEntry(v19, &v75, 0, &v70, &v76, &v88)
                          || (unsigned int)((v76 - *(_QWORD *)(v19 + 352)) >> *(_BYTE *)(v19 + 378)) + 2 != v28
                          || v88 != v86 )
                        {
                          v15 = -1073741811;
                          goto LABEL_86;
                        }
                        v23 = 0;
                        if ( *((_QWORD *)v18 + 5) || *v18 != 1282 )
                          FatFlushFatEntries(a1, v19, v28, v86 >> v60);
                        ExAcquireResourceExclusiveLite(*((PERESOURCE *)v18 + 2), 1u);
                        *((_QWORD *)v18 + 78) = &Event;
                        ExReleaseResourceLite(*((PERESOURCE *)v18 + 2));
                        v29 = NumberOfBytes_4;
                        if ( NumberOfBytes_4 )
                        {
                          memset(&v78, 0, sizeof(v78));
                          IoStatusBlock = 0;
                          KeInitializeEvent(&v78, NotificationEvent, 0);
                          v30 = IoBuildSynchronousFsdRequest(
                                  3u,
                                  *(PDEVICE_OBJECT *)(v19 + 136),
                                  v22,
                                  v29,
                                  &StartingOffset,
                                  &v78,
                                  &IoStatusBlock);
                          if ( !v30 )
                          {
                            a1[18] = -1073741670;
                            ExRaiseStatus(-1073741670);
                          }
                          Status = IofCallDriver(*(PDEVICE_OBJECT *)(v19 + 136), v30);
                          if ( Status == 259 )
                          {
                            KeWaitForSingleObject(&v78, Executive, 0, 0, 0);
                            Status = IoStatusBlock.Status;
                          }
                          if ( Status < 0 )
                          {
                            a1[18] = Status;
                            v32 = FsRtlNormalizeNtstatus(Status, -1073741591);
                            ExRaiseStatus(v32);
                          }
                          KeClearEvent(&v78);
                          v33 = IoBuildSynchronousFsdRequest(
                                  4u,
                                  *(PDEVICE_OBJECT *)(v19 + 136),
                                  v22,
                                  v29,
                                  &v69,
                                  &v78,
                                  &IoStatusBlock);
                          if ( !v33 )
                          {
                            a1[18] = -1073741670;
                            ExRaiseStatus(-1073741670);
                          }
                          v33->Tail.Overlay.CurrentStackLocation[-1].Flags |= 4u;
                          v34 = IofCallDriver(*(PDEVICE_OBJECT *)(v19 + 136), v33);
                          if ( v34 == 259 )
                          {
                            KeWaitForSingleObject(&v78, Executive, 0, 0, 0);
                            v34 = IoStatusBlock.Status;
                          }
                          if ( v34 < 0 )
                          {
                            a1[18] = v34;
                            v35 = FsRtlNormalizeNtstatus(v34, -1073741591);
                            ExRaiseStatus(v35);
                          }
                        }
                        FatSetFatEntry(a1, v19, v57, v66);
                        if ( *((_QWORD *)v18 + 5) || *v18 != 1282 )
                          FatFlushFatEntries(a1, v19, v57, 1);
                        v36 = v67;
                        if ( v67 )
                        {
                          FatSetFatEntry(a1, v19, v67, v58);
                          if ( *((_QWORD *)v18 + 5) || *v18 != 1282 )
                            FatFlushFatEntries(a1, v19, v36, 1);
                        }
                        else
                        {
                          FatGetDirentFromFcbOrDcb((_DWORD)a1, (_DWORD)v18, 0, (unsigned int)&v72, (__int64)&Bcb);
                          v38 = v58;
                          *(_WORD *)(v72 + 26) = v58;
                          if ( *(_BYTE *)(v19 + 376) == 32 )
                            *(_WORD *)(v72 + 20) = HIWORD(v38);
                          LOBYTE(v37) = 1;
                          FatSetDirtyBcb(a1, Bcb, v19, v37);
                          if ( Bcb )
                          {
                            CcUnpinData(Bcb);
                            Bcb = 0;
                          }
                          Bcb = 0;
                          FatFlushDirentForFile(a1, v18);
                          *((_DWORD *)v18 + 32) = v38;
                        }
                        v51 = 0;
                        FatMoveFileNeedsWriteThrough(a1, v18, v59);
                        FatDeallocateDiskSpace(v39, v19, &Mcb, 0);
                        FatUnpinRepinnedBcbs(a1, v40, v41, v42);
                        v44 = FatHijackIrpAndFlushDevice(v43, Irp, *(_QWORD *)(v19 + 136));
                        if ( v44 < 0 )
                        {
                          a1[18] = v44;
                          v45 = FsRtlNormalizeNtstatus(v44, -1073741591);
                          ExRaiseStatus(v45);
                        }
                        FatRemoveMcbEntry(v19, v18 + 144, v87, v86);
                        ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD))FatAddMcbEntry)(
                          v19,
                          v18 + 144,
                          v87,
                          (union _LARGE_INTEGER)v73.QuadPart,
                          v86);
                        KeSetEvent(&Event, 0, 0);
                        ExAcquireResourceExclusiveLite(*((PERESOURCE *)v18 + 2), 1u);
                        *((_QWORD *)v18 + 78) = 0;
                        ExReleaseResourceLite(*((PERESOURCE *)v18 + 2));
                        ExReleaseResourceLite(*((PERESOURCE *)v18 + 1));
                        v61 += v86 >> v60;
                        v83 = v61;
                        v87 += v86;
                        v71 = v87;
                        v73.QuadPart += v86;
                        v82 = v73;
                        v21 = v62 - v86;
                        v63 = v62 - v86;
                        v69.QuadPart += v86;
                        FatRemoveMcbEntry(v19, &Mcb, 0, 0xFFFFFFFFLL);
                        FatRemoveMcbEntry(v19, &v75, 0, 0xFFFFFFFFLL);
                        KeClearEvent(&Event);
                      }
                      v15 = 0;
                    }
                    else
                    {
                      v15 = -1073741811;
                      v23 = 0;
                    }
LABEL_86:
                    a1[17] &= ~0x80000000;
                    if ( v22 )
                      ExFreePoolWithTag(v22, 0);
                    if ( v51 )
                    {
                      FatDeallocateDiskSpace(a1, v19, &v75, 0);
                      FatUnpinRepinnedBcbs(a1, v46, v47, v48);
                    }
                    if ( Bcb )
                    {
                      CcUnpinData(Bcb);
                      Bcb = 0;
                    }
                    if ( v49 )
                      FsRtlUninitializeLargeMcb(&Mcb);
                    if ( v50 )
                      FsRtlUninitializeLargeMcb(&v75);
                    if ( v23 )
                      ExReleaseResourceLite(*((PERESOURCE *)v18 + 1));
                    ObfDereferenceObject(Object);
                    goto LABEL_22;
                  }
                }
                v14 = Object;
              }
              ObfDereferenceObject(v14);
            }
          }
        }
      }
      goto LABEL_21;
    }
    v15 = -1073741789;
    goto LABEL_22;
  }
LABEL_21:
  v15 = -1073741811;
LABEL_22:
  FatCompleteRequest_Real(a1, Irp);
  return v15;
}

```

## disassembly

```asm
0x1400412a8  mov     r11, rsp
0x1400412ab  mov     [r11+8], rcx
0x1400412af  push    rbx
0x1400412b0  push    rsi
0x1400412b1  push    rdi
0x1400412b2  push    r12
0x1400412b4  push    r13
0x1400412b6  push    r14
0x1400412b8  push    r15
0x1400412ba  sub     rsp, 1A0h
0x1400412c1  mov     r15, rdx
0x1400412c4  mov     rdi, rcx
0x1400412c7  xor     r13d, r13d
0x1400412ca  mov     [rsp+1D8h+var_168], r13
0x1400412cf  mov     qword ptr [rsp+1D8h+var_170], r13
0x1400412d4  mov     [rsp+1D8h+var_178], r13
0x1400412d9  mov     [r11-130h], r13
0x1400412e0  mov     [r11-0D8h], r13
0x1400412e7  mov     [r11-128h], r13
0x1400412ee  mov     [r11-13Ch], r13d
0x1400412f5  mov     [r11+10h], r13d
0x1400412f9  mov     [r11-134h], r13d
0x140041300  mov     [r11-158h], r13d
0x140041307  mov     [rsp+1D8h+var_15C], r13d
0x14004130c  mov     [r11-138h], r13d
0x140041313  xorps   xmm0, xmm0
0x140041316  movups  xmmword ptr [rsp+1D8h+Mcb.GuardedMutex], xmm0
0x14004131e  movups  xmmword ptr [r11-80h], xmm0
0x140041323  xorps   xmm1, xmm1
0x140041326  movups  xmmword ptr [rsp+1D8h+var_100.GuardedMutex], xmm1
0x14004132e  movups  xmmword ptr [rsp+1D8h+var_100.BaseMcb.PoolType], xmm1
0x140041336  xor     eax, eax
0x140041338  movups  xmmword ptr [rsp+1D8h+Event.Header], xmm0
0x140041340  mov     [r11-0A8h], rax
0x140041347  mov     [rsp+1D8h+var_187], r13b
0x14004134c  mov     [rsp+1D8h+var_186], r13b
0x140041351  mov     [rsp+1D8h+var_188], r13b
0x140041356  mov     [rsp+1D8h+var_184], r13b
0x14004135b  mov     [rsp+1D8h+var_185], r13b
0x140041360  mov     [r11-118h], r13
0x140041367  mov     [rsp+1D8h+Bcb], r13
0x14004136c  mov     eax, [rcx+44h]
0x14004136f  mov     [rsp+1D8h+var_154], eax
0x140041376  movups  xmmword ptr [r11-60h], xmm0
0x14004137b  movups  xmmword ptr [r11-50h], xmm0
0x140041380  mov     rsi, [rdx+0B8h]
0x140041387  or      eax, 2
0x14004138a  mov     [rcx+44h], eax
0x14004138d  lea     r9, [r11-130h]
0x140041394  lea     r8, [rsp+1D8h+var_178]
0x140041399  lea     rdx, [rsp+1D8h+var_170]
0x14004139e  mov     rcx, [rsi+30h]
0x1400413a2  call    FatDecodeFileObject
0x1400413a7  cmp     eax, 4
0x1400413aa  jnz     loc_140041500
0x1400413b0  mov     rax, [rsp+1D8h+var_130]
0x1400413b8  test    rax, rax
0x1400413bb  jz      loc_140041500
0x1400413c1  test    dword ptr [rax+4], 20000h
0x1400413c8  jz      loc_140041500
0x1400413ce  mov     esi, [rsi+10h]
0x1400413d1  mov     rbx, [r15+18h]
0x1400413d5  mov     rcx, r15; Irp
0x1400413d8  call    cs:__imp_IoIs32bitProcess
0x1400413df  nop     dword ptr [rax+rax+00h]
0x1400413e4  test    al, al
0x1400413e6  jz      short loc_140041431
0x1400413e8  test    rbx, rbx
0x1400413eb  jz      loc_140041FC9
0x1400413f1  cmp     esi, 20h ; ' '
0x1400413f4  jb      loc_140041FC9
0x1400413fa  movsxd  rax, dword ptr [rbx]
0x1400413fd  mov     [rsp+1D8h+var_60], rax
0x140041405  mov     rax, [rbx+8]
0x140041409  mov     [rsp+1D8h+var_58], rax
0x140041411  mov     rax, [rbx+10h]
0x140041415  mov     [rsp+1D8h+var_50], rax
0x14004141d  mov     eax, [rbx+18h]
0x140041420  mov     [rsp+1D8h+var_48], eax
0x140041427  lea     rbx, [rsp+1D8h+var_60]
0x14004142f  jmp     short loc_140041443
0x140041431  test    rbx, rbx
0x140041434  jz      loc_140041FC9
0x14004143a  cmp     esi, 20h ; ' '
0x14004143d  jb      loc_140041FC9
0x140041443  cmp     [rbx+0Ch], r13d
0x140041447  jnz     loc_140041500
0x14004144d  cmp     [rbx+14h], r13d
0x140041451  jnz     loc_140041500
0x140041457  mov     r12d, [rbx+10h]
0x14004145b  lea     eax, [r12+2]
0x140041460  mov     [rsp+1D8h+var_14C], eax
0x140041467  cmp     eax, 2
0x14004146a  jb      loc_140041500
0x140041470  mov     edx, [rbx+18h]
0x140041473  lea     ecx, [rdx+rax]
0x140041476  cmp     ecx, eax
0x140041478  jb      loc_140041500
0x14004147e  mov     r14, qword ptr [rsp+1D8h+var_170]
0x140041483  mov     r8d, [r14+16Ch]
0x14004148a  lea     eax, [r8+2]
0x14004148e  cmp     ecx, eax
0x140041490  ja      short loc_140041500
0x140041492  cmp     [rbx+8], r8d
0x140041496  jnb     short loc_140041500
0x140041498  test    edx, edx
0x14004149a  jz      short loc_140041500
0x14004149c  mov     [rsp+1D8h+HandleInformation], r13; HandleInformation
0x1400414a1  lea     rax, [rsp+1D8h+var_168]
0x1400414a6  mov     [rsp+1D8h+Object], rax; Object
0x1400414ab  mov     r9b, [r15+40h]; AccessMode
0x1400414af  mov     r8, cs:__imp_IoFileObjectType
0x1400414b6  mov     r8, [r8]; ObjectType
0x1400414b9  xor     edx, edx; DesiredAccess
0x1400414bb  mov     rcx, [rbx]; Handle
0x1400414be  call    cs:__imp_ObReferenceObjectByHandle
0x1400414c5  nop     dword ptr [rax+rax+00h]
0x1400414ca  mov     esi, eax
0x1400414cc  test    eax, eax
0x1400414ce  jns     short loc_1400414E2
0x1400414d0  mov     r8d, eax
0x1400414d3  mov     rdx, r15; Irp
0x1400414d6  mov     rcx, rdi; Entry
0x1400414d9  call    FatCompleteRequest_Real
0x1400414de  mov     eax, esi
0x1400414e0  jmp     short loc_140041515
0x1400414e2  mov     rax, [r14+0C0h]
0x1400414e9  mov     rcx, [rsp+1D8h+var_168]; Object
0x1400414ee  cmp     [rcx+10h], rax
0x1400414f2  jz      short loc_140041529
0x1400414f4  call    cs:__imp_ObfDereferenceObject
0x1400414fb  nop     dword ptr [rax+rax+00h]
0x140041500  mov     ebx, 0C000000Dh
0x140041505  mov     r8d, ebx
0x140041508  mov     rdx, r15; Irp
0x14004150b  mov     rcx, rdi; Entry
0x14004150e  call    FatCompleteRequest_Real
0x140041513  mov     eax, ebx
0x140041515  add     rsp, 1A0h
0x14004151c  pop     r15
0x14004151e  pop     r14
0x140041520  pop     r13
0x140041522  pop     r12
0x140041524  pop     rdi
0x140041525  pop     rsi
0x140041526  pop     rbx
0x140041527  retn
0x140041529  lea     r9, [rsp+1D8h+var_130]
0x140041531  lea     r8, [rsp+1D8h+var_178]
0x140041536  lea     rdx, [rsp+1D8h+var_170]
0x14004153b  call    FatDecodeFileObject
0x140041540  mov     r13d, eax
0x140041543  lea     ecx, [rax-2]
0x140041546  cmp     ecx, 1
0x140041549  ja      loc_140041FBF
0x14004154f  mov     rsi, [rsp+1D8h+var_178]
0x140041554  mov     r14, qword ptr [rsp+1D8h+var_170]
0x140041559  cmp     eax, 3
0x14004155c  jnz     short loc_140041581
0x14004155e  mov     eax, 504h
0x140041563  cmp     [rsi], ax
0x140041566  jnz     short loc_140041576
0x140041568  cmp     byte ptr [r14+178h], 20h ; ' '
0x140041570  jnz     loc_140041FBF
0x140041576  cmp     qword ptr [rbx+8], 0
0x14004157b  jz      loc_140041FBF
0x140041581  mov     [rsp+1D8h+var_108], 0
0x14004158d  mov     eax, [rsp+1D8h+var_154]
0x140041594  and     eax, 0Ch
0x140041597  mov     [rsp+1D8h+var_154], eax
0x14004159e  mov     [rsp+1D8h+var_160], 0
0x1400415a6  mov     r8d, eax
0x1400415a9  mov     rdx, rsi
0x1400415ac  mov     rcx, rdi
0x1400415af  call    FatMoveFileNeedsWriteThrough
0x1400415b4  mov     ecx, [r14+0C8h]
0x1400415bb  bt      ecx, 16h
0x1400415bf  jnb     short loc_1400415D2
0x1400415c1  test    dword ptr [rsi+0C0h], 8000h
0x1400415cb  jz      short loc_1400415D2
0x1400415cd  bts     dword ptr [rdi+44h], 0Eh
0x1400415d2  bts     dword ptr [rdi+44h], 1Fh
0x1400415d7  movzx   ecx, byte ptr [r14+17Ah]
0x1400415df  mov     [rsp+1D8h+var_150], ecx
0x1400415e6  mov     edx, [rbx+8]
0x1400415e9  shl     edx, cl
0x1400415eb  mov     [rsp+1D8h+arg_10], edx
0x1400415f2  mov     [rsp+1D8h+var_11C], edx
0x1400415f9  mov     ebx, [rbx+18h]
0x1400415fc  shl     ebx, cl
0x1400415fe  mov     [rsp+1D8h+var_148], ebx
0x140041605  mov     [rsp+1D8h+var_144], ebx
0x14004160c  mov     rax, r12
0x14004160f  shl     rax, cl
0x140041612  add     rax, [r14+160h]
0x140041619  mov     [rsp+1D8h+var_110], rax
0x140041621  mov     [rsp+1D8h+var_70], rax
0x140041629  mov     qword ptr [rsp+1D8h+var_128], rax
0x140041631  xor     r12d, r12d
0x140041634  mov     [rsp+1D8h+var_108], r12
0x14004163c  lea     eax, [rbx+rdx]
0x14004163f  cmp     eax, edx
0x140041641  jnb     short loc_140041652
0x140041643  mov     ebx, 0C000000Dh
0x140041648  mov     r13b, [rsp+1D8h+var_188]
0x14004164d  jmp     loc_140041EFD
0x140041652  xor     r8d, r8d; State
0x140041655  xor     edx, edx; Type
0x140041657  lea     rcx, [rsp+1D8h+Event]; Event
0x14004165f  call    cs:__imp_KeInitializeEvent
0x140041666  nop     dword ptr [rax+rax+00h]
0x14004166b  mov     edx, 1; PoolType
0x140041670  lea     rcx, [rsp+1D8h+Mcb]; Mcb
0x140041678  call    cs:__imp_FsRtlInitializeLargeMcb
0x14004167f  nop     dword ptr [rax+rax+00h]
0x140041684  mov     [rsp+1D8h+var_187], 1
0x140041689  mov     edx, 1; PoolType
0x14004168e  lea     rcx, [rsp+1D8h+var_100]; Mcb
0x140041696  call    cs:__imp_FsRtlInitializeLargeMcb
0x14004169d  nop     dword ptr [rax+rax+00h]
0x1400416a2  mov     [rsp+1D8h+var_186], 1
0x1400416a7  cmp     r13d, 3
0x1400416ab  jnz     short loc_140041720
0x1400416ad  mov     rdx, rsi
0x1400416b0  mov     rcx, rdi
0x1400416b3  call    FatAcquireExclusiveFcb
0x1400416b8  mov     [rsp+1D8h+var_188], 1
0x1400416bd  mov     rdx, rsi
0x1400416c0  mov     rcx, rdi
0x1400416c3  call    FatVerifyFcb
0x1400416c8  mov     rdx, rsi
0x1400416cb  mov     rcx, rdi
0x1400416ce  call    FatOpenDirectoryFile
0x1400416d3  mov     rbx, [rsi+158h]
0x1400416da  mov     rcx, rbx; Object
0x1400416dd  call    cs:__imp_ObfReferenceObject
0x1400416e4  nop     dword ptr [rax+rax+00h]
0x1400416e9  mov     rcx, [rsp+1D8h+var_168]; Object
0x1400416ee  call    cs:__imp_ObfDereferenceObject
0x1400416f5  nop     dword ptr [rax+rax+00h]
0x1400416fa  mov     [rsp+1D8h+var_168], rbx
0x1400416ff  mov     rcx, [rsi+8]; Resource
0x140041703  call    cs:__imp_ExReleaseResourceLite
0x14004170a  nop     dword ptr [rax+rax+00h]
0x14004170f  xor     r13b, r13b
0x140041712  mov     [rsp+1D8h+var_188], r13b
0x140041717  mov     ebx, [rsp+1D8h+var_148]
0x14004171e  jmp     short loc_140041725
0x140041720  mov     r13b, [rsp+1D8h+var_188]
0x140041725  mov     edx, 10000h
0x14004172a  mov     ecx, [rsp+1D8h+var_150]
0x140041731  mov     eax, 1
0x140041736  shl     eax, cl
0x140041738  cmp     eax, edx
0x14004173a  cmova   edx, eax; BytesToWrite
0x14004173d  mov     dword ptr [rsp+1D8h+NumberOfBytes], edx
0x140041744  test    ebx, ebx
0x140041746  jz      loc_140041EFB
0x14004174c  mov     [rsp+1D8h+var_120], 0
0x140041757  mov     [rsp+1D8h+var_E0], 0
0x140041763  mov     [rsp+1D8h+arg_18], 0
0x14004176e  xor     r9d, r9d; Retrying
0x140041771  mov     r8b, 1; Wait
0x140041774  mov     rcx, [rsp+1D8h+var_168]; FileObject
0x140041779  call    cs:__imp_CcCanIWrite
0x140041780  nop     dword ptr [rax+rax+00h]
0x140041785  mov     rdx, rsi
0x140041788  mov     rcx, rdi
0x14004178b  call    FatAcquireExclusiveFcb
0x140041790  mov     r13b, 1
0x140041793  mov     [rsp+1D8h+var_188], r13b
0x140041798  mov     rdx, rsi
0x14004179b  mov     rcx, rdi
0x14004179e  call    FatVerifyFcb
0x1400417a3  test    dword ptr [rsi+0C0h], 4000h
0x1400417ad  jz      short loc_1400417CA
0x1400417af  mov     rax, [rsp+1D8h+var_130]
0x1400417b7  mov     eax, [rax+4]
0x1400417ba  bt      eax, 13h
0x1400417be  jb      short loc_1400417CA
0x1400417c0  mov     ebx, 0C0000022h
0x1400417c5  jmp     loc_140041EFD
0x1400417ca  test    r12, r12
0x1400417cd  jnz     short loc_140041815
0x1400417cf  mov     ebx, dword ptr [rsp+1D8h+NumberOfBytes]
0x1400417d6  mov     r8d, 47746146h; Tag
0x1400417dc  mov     edx, ebx; NumberOfBytes
0x1400417de  mov     ecx, 610h; PoolType
0x1400417e3  call    cs:__imp_ExAllocatePoolWithTag
0x1400417ea  nop     dword ptr [rax+rax+00h]
0x1400417ef  mov     r12, rax
0x1400417f2  cmp     cs:ExPoolZeroingNativelySupported, 0
0x1400417f9  jnz     short loc_14004180D
0x1400417fb  test    rax, rax
0x1400417fe  jz      short loc_14004180D
0x140041800  mov     r8d, ebx; Size
0x140041803  xor     edx, edx; Val
0x140041805  mov     rcx, rax; void *
0x140041808  call    memset
0x14004180d  mov     [rsp+1D8h+var_108], r12
  ... truncated ...
```
