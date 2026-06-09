# FatWriteRawEncrypted

- ea: `0x14003816c`
- end: `0x140038d8e`
- name: `FatWriteRawEncrypted`
- size: `3106`
- prototype: `__int64 __fastcall(PVOID Entry, PIRP Irp)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140042ac0`

## callees

- `0x1400034e0`
- `0x140005288`
- `0x14000c380`
- `0x14000c680`
- `0x140020458`
- `0x140033270`
- `0x14003816c`
- `0x140038eb4`
- `0x14003960c`
- `0x14003d880`
- `0x1400465f4`
- `0x140047d24`
- `0x14004af08`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14003891b`
- `ntoskrnl!KeInitializeEvent` at `0x14003891b`
- `ntoskrnl!KeWaitForSingleObject` at `0x140038a7d`
- `ntoskrnl!KeWaitForSingleObject` at `0x140038a7d`
- `ntoskrnl!IoFreeMdl` at `0x14003886f`
- `ntoskrnl!IoFreeMdl` at `0x14003886f`
- `ntoskrnl!CcFlushCache` at `0x1400384ab`
- `ntoskrnl!CcFlushCache` at `0x1400384ab`
- `ntoskrnl!CcPurgeCacheSection` at `0x1400384c3`
- `ntoskrnl!CcPurgeCacheSection` at `0x1400384c3`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x140038c98`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x140038cc2`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x140038d08`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x140038d2b`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x140038c98`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x140038cc2`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x140038d08`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x140038d2b`
- `ntoskrnl!IoAllocateMdl` at `0x1400387f2`
- `ntoskrnl!IoAllocateMdl` at `0x1400387f2`
- `ntoskrnl!IoIsOperationSynchronous` at `0x14003895c`
- `ntoskrnl!IoIsOperationSynchronous` at `0x14003895c`
- `ntoskrnl!IoFreeIrp` at `0x14003880a`
- `ntoskrnl!IoFreeIrp` at `0x140038886`
- `ntoskrnl!IoFreeIrp` at `0x14003880a`
- `ntoskrnl!IoFreeIrp` at `0x140038886`
- `ntoskrnl!MmProbeAndLockPages` at `0x140038830`
- `ntoskrnl!MmProbeAndLockPages` at `0x140038830`
- `ntoskrnl!MmMdlPageContentsState` at `0x140038843`
- `ntoskrnl!MmMdlPageContentsState` at `0x140038843`
- `ntoskrnl!ProbeForRead` at `0x1400382bd`
- `ntoskrnl!ProbeForRead` at `0x1400382bd`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x1400385df`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x1400385df`
- `ntoskrnl!IoBuildAsynchronousFsdRequest` at `0x1400387aa`
- `ntoskrnl!IoBuildAsynchronousFsdRequest` at `0x1400387aa`
- `ntoskrnl!CcSetFileSizesEx` at `0x140038b8e`
- `ntoskrnl!CcSetFileSizesEx` at `0x140038c30`
- `ntoskrnl!CcSetFileSizesEx` at `0x140038b8e`
- `ntoskrnl!CcSetFileSizesEx` at `0x140038c30`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14003848e`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14003848e`
- `ntoskrnl!ExReleaseResourceLite` at `0x140038c50`
- `ntoskrnl!ExReleaseResourceLite` at `0x140038c60`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005e209`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005e22a`
- `ntoskrnl!ExReleaseResourceLite` at `0x140038c50`
- `ntoskrnl!ExReleaseResourceLite` at `0x140038c60`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005e209`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005e22a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038651`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038c7f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005e248`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038651`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038c7f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005e248`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003869e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003869e`
- `ntoskrnl!ExRaiseStatus` at `0x140038cdf`
- `ntoskrnl!ExRaiseStatus` at `0x140038d41`
- `ntoskrnl!ExRaiseStatus` at `0x140038cdf`
- `ntoskrnl!ExRaiseStatus` at `0x140038d41`

## pseudocode

```c
__int64 __fastcall FatWriteRawEncrypted(_DWORD *Entry, PIRP Irp)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // r13
  union _LARGE_INTEGER *Parameters; // r12
  SIZE_T Options; // r11
  unsigned __int64 LowPart; // rdi
  DWORD v11; // r10d
  char v12; // r8
  __int16 v13; // r9
  __int64 v14; // rax
  int Status; // edi
  LONGLONG QuadPart; // r8
  int v18; // edx
  unsigned __int16 i; // r9
  unsigned __int16 v20; // cx
  int v21; // ecx
  DWORD v22; // r9d
  unsigned __int16 v23; // ax
  __int64 v24; // rdx
  size_t v25; // rbx
  unsigned int v26; // ecx
  unsigned __int64 v27; // rdi
  unsigned int v28; // r8d
  ULONG v29; // edi
  void *v30; // rax
  unsigned __int64 v31; // r9
  PVOID PoolWithTag; // rax
  PIRP v33; // rbx
  struct _MDL *Mdl; // rax
  union _LARGE_INTEGER *v35; // rcx
  struct _IO_STACK_LOCATION *v36; // rax
  __int64 v37; // rdx
  _DWORD *IrpContext; // rax
  unsigned int v39; // ebx
  unsigned int v40; // eax
  __int64 v41; // rbx
  __int64 v42; // rdx
  __int64 v43; // rcx
  LONGLONG v44; // rdx
  unsigned __int16 v45; // [rsp+40h] [rbp-168h]
  unsigned int v46; // [rsp+44h] [rbp-164h]
  union _LARGE_INTEGER StartingOffset; // [rsp+48h] [rbp-160h] BYREF
  unsigned int v48; // [rsp+50h] [rbp-158h]
  DWORD v49; // [rsp+54h] [rbp-154h]
  unsigned int HighPart; // [rsp+58h] [rbp-150h]
  void *v51; // [rsp+60h] [rbp-148h]
  char v52; // [rsp+68h] [rbp-140h]
  DWORD v53; // [rsp+6Ch] [rbp-13Ch]
  unsigned int v54; // [rsp+70h] [rbp-138h]
  int v55; // [rsp+74h] [rbp-134h]
  unsigned int v56; // [rsp+78h] [rbp-130h]
  __int64 v57; // [rsp+80h] [rbp-128h] BYREF
  PFILE_OBJECT FileObject; // [rsp+88h] [rbp-120h]
  ULONG v59; // [rsp+90h] [rbp-118h]
  unsigned int v60; // [rsp+94h] [rbp-114h]
  int v61; // [rsp+98h] [rbp-110h]
  DWORD v62; // [rsp+9Ch] [rbp-10Ch]
  void *Src; // [rsp+A0h] [rbp-108h]
  __int64 v64; // [rsp+A8h] [rbp-100h]
  PVOID P; // [rsp+B0h] [rbp-F8h]
  __int64 v66; // [rsp+B8h] [rbp-F0h] BYREF
  PIRP Irpa; // [rsp+C0h] [rbp-E8h]
  unsigned __int64 v68; // [rsp+C8h] [rbp-E0h]
  int v69; // [rsp+D0h] [rbp-D8h]
  int v70; // [rsp+D4h] [rbp-D4h]
  __int16 v71; // [rsp+D8h] [rbp-D0h]
  PVOID v72; // [rsp+E0h] [rbp-C8h]
  union _LARGE_INTEGER v73; // [rsp+E8h] [rbp-C0h]
  size_t Size; // [rsp+F0h] [rbp-B8h]
  PDEVICE_OBJECT RelatedDeviceObject; // [rsp+F8h] [rbp-B0h]
  union _IRP::$::$::$665C8370128C04AB892B069E6FB086E8::$8B5CD6CDFBAAB114E6B0B83ED2C2A4E9 *p_CurrentStackLocation; // [rsp+100h] [rbp-A8h]
  KPROCESSOR_MODE *p_RequestorMode; // [rsp+108h] [rbp-A0h]
  PFILE_OBJECT v78; // [rsp+110h] [rbp-98h]
  union _LARGE_INTEGER *v79; // [rsp+118h] [rbp-90h]
  union _LARGE_INTEGER v80; // [rsp+120h] [rbp-88h]
  union _IRP::$::$::$665C8370128C04AB892B069E6FB086E8::$8B5CD6CDFBAAB114E6B0B83ED2C2A4E9 *v81; // [rsp+128h] [rbp-80h]
  struct _KEVENT Event; // [rsp+130h] [rbp-78h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+148h] [rbp-60h] BYREF
  __int64 v84; // [rsp+1C0h] [rbp+18h] BYREF
  unsigned __int16 LowPart_high; // [rsp+1C8h] [rbp+20h]

  v66 = 0;
  v57 = 0;
  v84 = 0;
  memset(&Event, 0, sizeof(Event));
  IoStatusBlock = 0;
  StartingOffset.QuadPart = 0;
  v55 = 0;
  v62 = 0;
  v60 = 0;
  Entry[17] |= 2u;
  p_CurrentStackLocation = (union _IRP::$::$::$665C8370128C04AB892B069E6FB086E8::$8B5CD6CDFBAAB114E6B0B83ED2C2A4E9 *)&Irp->Tail.Overlay.CurrentStackLocation;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  FileObject = CurrentStackLocation->FileObject;
  v78 = FileObject;
  v5 = FatDecodeFileObject(FileObject, &v66, &v57, &v84);
  if ( (*(_DWORD *)(v66 + 200) & 0x400000) == 0 )
  {
    v6 = -1073741808;
    goto LABEL_95;
  }
  if ( v5 != 2 )
    goto LABEL_92;
  if ( (*(_DWORD *)(v66 + 200) & 0x4000) == 0 )
  {
    v7 = v57;
    if ( (*(_DWORD *)(v57 + 192) & 0x20000) == 0 )
    {
      v6 = -1073741790;
      goto LABEL_95;
    }
    Parameters = (union _LARGE_INTEGER *)CurrentStackLocation->Parameters.CreatePipe.Parameters;
    v79 = Parameters;
    Options = CurrentStackLocation->Parameters.Create.Options;
    v54 = Options;
    v70 = Options;
    if ( (unsigned int)Options < 0x20 )
    {
      v6 = -1073741789;
      goto LABEL_95;
    }
    p_RequestorMode = &Irp->RequestorMode;
    if ( Irp->RequestorMode )
    {
      ProbeForRead(Parameters, Options, 1u);
      LODWORD(Options) = v54;
    }
    LowPart = Parameters[1].LowPart;
    v56 = LowPart;
    v55 = LowPart;
    v11 = Parameters[2].LowPart;
    v49 = v11;
    v62 = v11;
    HighPart = Parameters[1].HighPart;
    v60 = HighPart;
    LowPart_high = HIWORD(Parameters[3].u.LowPart);
    v12 = BYTE1(Parameters[3].LowPart);
    v52 = v12;
    v73 = *Parameters;
    StartingOffset = v73;
    v80 = v73;
    LOBYTE(v84) = BYTE6(Parameters[2].QuadPart);
    v13 = WORD2(Parameters[2].QuadPart);
    v71 = v13;
    v14 = 4 * (unsigned int)LowPart_high + 28;
    if ( (unsigned int)v14 > (unsigned int)LowPart || (unsigned int)v14 > (unsigned int)Options )
    {
      FatCompleteRequest_Real(Entry, Irp);
      return 3221226666LL;
    }
    if ( v14 + 16 <= LowPart
      && v14 + 16 <= (unsigned __int64)(unsigned int)Options
      && *(DWORD *)((char *)&Parameters->LowPart + (unsigned int)v14) == ExtendedEncryptedDataInfoSignature )
    {
      if ( *(LONG *)((char *)&Parameters->HighPart + (unsigned int)v14) < 0x10u )
      {
        FatCompleteRequest_Real(Entry, Irp);
        return 3221225485LL;
      }
      if ( (*(DWORD *)((_BYTE *)&Parameters[1].LowPart + (unsigned int)v14) & 1) != 0 )
      {
        FatCompleteRequest_Real(Entry, Irp);
        return 3221226535LL;
      }
    }
    if ( v12 == 1 && v11 <= HighPart && !v13 )
    {
      if ( LowPart_high )
      {
        v81 = (union _IRP::$::$::$665C8370128C04AB892B069E6FB086E8::$8B5CD6CDFBAAB114E6B0B83ED2C2A4E9 *)&Irp->Tail.Overlay.CurrentStackLocation;
        if ( (unsigned int)LowPart <= (unsigned int)Options )
        {
          Status = 0;
          v72 = 0;
          v64 = 0;
          v51 = 0;
          v68 = 0;
          P = 0;
          v59 = 0;
          v48 = 1 << *(_BYTE *)(v66 + 377);
          v61 = 1 << *(_BYTE *)(v66 + 378);
          FatAcquireExclusiveFcb(Entry, v7);
          ExAcquireResourceExclusiveLite(*(PERESOURCE *)(v7 + 16), 1u);
          CcFlushCache(*(PSECTION_OBJECT_POINTERS *)(v7 + 120), 0, 0, &Irp->IoStatus);
          if ( !CcPurgeCacheSection(*(PSECTION_OBJECT_POINTERS *)(v7 + 120), 0, 0, 0) )
          {
            Status = -1073741797;
            goto LABEL_89;
          }
          QuadPart = StartingOffset.QuadPart;
          if ( StartingOffset.QuadPart <= *(_QWORD *)(v7 + 32) && StartingOffset.QuadPart >= 0 )
          {
            v18 = 0;
            for ( i = 0; ; ++i )
            {
              v20 = LowPart_high;
              if ( i >= LowPart_high )
                break;
              v21 = *(&Parameters[3].HighPart + i);
              if ( v21 )
                v18 += v21;
              else
                v18 += 1 << v84;
            }
            v22 = v49;
            if ( v49 == v18 )
            {
LABEL_38:
              v23 = 0;
              v24 = v64;
              while ( 1 )
              {
                v45 = v23;
                if ( v23 >= v20 )
                  break;
                v25 = *((unsigned int *)&Parameters[3].HighPart + v23);
                v53 = v25;
                v69 = v25;
                v46 = v25;
                if ( !(_DWORD)v25 )
                {
                  Status = -1073740761;
                  goto LABEL_89;
                }
                if ( v22 )
                {
                  v26 = v25 + v56;
                  if ( (unsigned int)v25 + v56 > v54 || v26 < v56 )
                    goto LABEL_88;
                  v27 = (unsigned __int64)Parameters + v56;
                  Src = (void *)v27;
                  v56 += v25;
                  v55 = v26;
                  RelatedDeviceObject = IoGetRelatedDeviceObject(FileObject);
                  v28 = v48;
                  if ( (unsigned int)v25 % v48 || v27 % v48 )
                  {
                    v29 = -v48 & (v25 + v48 - 1);
                    if ( v29 < (unsigned int)v25 )
                      goto LABEL_88;
                    v31 = (unsigned __int64)v51;
                    if ( !v51 )
                      goto LABEL_52;
                    if ( v59 < v29 )
                    {
                      ExFreePoolWithTag(P, 0);
                      v31 = 0;
                      v51 = 0;
                      v68 = 0;
                      P = 0;
                      v28 = v48;
                    }
                    if ( !v31 )
                    {
LABEL_52:
                      Size = v29 + v28 - 1;
                      PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)1025, (unsigned int)Size, 0x20746146u);
                      v31 = (unsigned __int64)PoolWithTag;
                      v51 = PoolWithTag;
                      if ( !ExPoolZeroingNativelySupported && PoolWithTag )
                      {
                        memset(PoolWithTag, 0, Size);
                        v31 = (unsigned __int64)v51;
                      }
                      P = (PVOID)v31;
                      if ( !v31 )
                        goto LABEL_56;
                      v68 = v31;
                      v59 = v29;
                      if ( v31 % v48 )
                      {
                        v31 = -v48 & ((int)(v48 - 1) + v31);
                        v51 = (void *)v31;
                        v68 = v31;
                      }
                    }
                    memmove((void *)v31, Src, v25);
                    memset((char *)v51 + v25, 0, v29 - (unsigned int)v25);
                    v30 = v51;
                    Src = v51;
                  }
                  else
                  {
                    v29 = v25;
                    v30 = Src;
                  }
                  v33 = IoBuildAsynchronousFsdRequest(
                          4u,
                          *(PDEVICE_OBJECT *)(*(_QWORD *)(v66 + 192) + 8LL),
                          v30,
                          v29,
                          &StartingOffset,
                          &IoStatusBlock);
                  Irpa = v33;
                  if ( !v33 )
                    goto LABEL_56;
                  if ( Src == v51 )
                  {
                    Mdl = IoAllocateMdl(Src, v29, 0, 0, 0);
                    v33->MdlAddress = Mdl;
                    if ( !Mdl )
                    {
                      IoFreeIrp(v33);
                      Irpa = 0;
LABEL_56:
                      Status = -1073741670;
                      goto LABEL_89;
                    }
                    MmProbeAndLockPages(Mdl, 0, IoWriteAccess);
                    MmMdlPageContentsState(v33->MdlAddress, 1);
                    v33->UserBuffer = Src;
                    v33->RequestorMode = 0;
                  }
                  else
                  {
                    v33->UserBuffer = Src;
                    v33->RequestorMode = *p_RequestorMode;
                  }
                  v33->Flags |= 5u;
                  v35 = (union _LARGE_INTEGER *)&v33->Tail.Overlay.CurrentStackLocation[-1];
                  v35[5].QuadPart = (LONGLONG)RelatedDeviceObject;
                  v35[3] = StartingOffset;
                  v35[1].LowPart = v53;
                  v35[6].QuadPart = (LONGLONG)FileObject;
                  v33->Tail.Overlay.CurrentStackLocation = (struct _IO_STACK_LOCATION *)v35;
                  KeInitializeEvent(&Event, NotificationEvent, 0);
                  v36 = p_CurrentStackLocation->CurrentStackLocation;
                  v36[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&FatCallSelfCompletionRoutine;
                  v36[-1].Context = &Event;
                  v36[-1].Control = 0;
                  v36[-1].Control = 64;
                  v36[-1].Control = -64;
                  v36[-1].Control = -32;
                  LOBYTE(v37) = IoIsOperationSynchronous(Irp);
                  IrpContext = (_DWORD *)FatCreateIrpContext(v33, v37);
                  v72 = IrpContext;
                  IrpContext[17] |= 0x20000u;
                  Status = FatCommonWrite((__int64)IrpContext, v33);
                  v39 = v53;
                  if ( Status == 259 )
                  {
                    Status = KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
                    if ( !Status )
                      Status = IoStatusBlock.Status;
                  }
                  v24 = v39 + v64;
                  v64 = v24;
                  QuadPart = v39 + StartingOffset.QuadPart;
                  StartingOffset.QuadPart = QuadPart;
                  if ( v39 >= 1 << v84 || HighPart <= v49 )
                  {
                    v40 = 0;
                    v46 = 0;
                  }
                  else
                  {
                    v40 = HighPart - v49;
                  }
                }
                else
                {
                  v40 = v25;
                }
                v41 = v40;
                if ( v40 )
                {
                  v42 = -v61;
                  v43 = v61 - 1;
                  RelatedDeviceObject = (PDEVICE_OBJECT)(v42 & (v43 + QuadPart));
                  Size = v42 & (QuadPart + v43 + v40);
                  if ( *(_QWORD *)(v7 + 24) < (signed __int64)Size )
                  {
                    FatAddFileAllocation((_DWORD)Entry);
                    QuadPart = StartingOffset.QuadPart;
                  }
                  if ( v41 + QuadPart > *(_QWORD *)(v7 + 32) )
                    *(_QWORD *)(v7 + 32) = v41 + QuadPart;
                  FatSetFileSizeInDirent(Entry, v7);
                  CcSetFileSizesEx(FileObject, (PCC_FILE_SIZES)(v7 + 24));
                  v24 = v41 + v64;
                  v64 += v41;
                  QuadPart = StartingOffset.QuadPart;
                }
                QuadPart += v41 + v46;
                StartingOffset.QuadPart = QuadPart;
                v23 = v45 + 1;
                v22 = v49;
                v20 = LowPart_high;
              }
              if ( Status >= 0 && (HighPart != v24 || v22 < v24) )
              {
                v44 = v73.QuadPart + v22;
                *(_DWORD *)(v7 + 32) = v73.LowPart + HighPart;
                if ( v44 < *(_QWORD *)(v7 + 40) )
                  *(_DWORD *)(v7 + 40) = v44;
                CcSetFileSizesEx(FileObject, (PCC_FILE_SIZES)(v7 + 24));
              }
              goto LABEL_89;
            }
            if ( v73.QuadPart + v49 >= *(_QWORD *)(v7 + 40) )
            {
              v20 = LowPart_high;
              goto LABEL_38;
            }
          }
LABEL_88:
          Status = -1073741811;
LABEL_89:
          ExReleaseResourceLite(*(PERESOURCE *)(v7 + 16));
          ExReleaseResourceLite(*(PERESOURCE *)(v7 + 8));
          if ( P )
            ExFreePoolWithTag(P, 0);
          goto LABEL_93;
        }
      }
    }
LABEL_92:
    Status = -1073741811;
LABEL_93:
    FatCompleteRequest_Real(Entry, Irp);
    return (unsigned int)Status;
  }
  v6 = -1073741662;
LABEL_95:
  FatCompleteRequest_Real(Entry, Irp);
  return v6;
}

```

## disassembly

```asm
0x14003816c  mov     r11, rsp
0x14003816f  mov     [r11+10h], rdx
0x140038173  mov     [r11+8], rcx
0x140038177  push    rbx
0x140038178  push    rsi
0x140038179  push    rdi
0x14003817a  push    r12
0x14003817c  push    r13
0x14003817e  push    r14
0x140038180  push    r15
0x140038182  sub     rsp, 170h
0x140038189  mov     r15, rdx
0x14003818c  mov     r14, rcx
0x14003818f  xor     esi, esi
0x140038191  mov     [r11-0F0h], rsi
0x140038198  mov     [r11-128h], rsi
0x14003819f  mov     [r11+18h], rsi
0x1400381a3  xorps   xmm0, xmm0
0x1400381a6  xor     eax, eax
0x1400381a8  movups  xmmword ptr [r11-78h], xmm0
0x1400381ad  mov     [r11-68h], rax
0x1400381b1  movups  xmmword ptr [r11-60h], xmm0
0x1400381b6  mov     qword ptr [rsp+1A8h+var_160], rsi
0x1400381bb  mov     [rsp+1A8h+var_134], esi
0x1400381bf  mov     [rsp+1A8h+var_10C], esi
0x1400381c6  mov     [rsp+1A8h+var_114], esi
0x1400381cd  mov     [rsp+1A8h+var_16C], si
0x1400381d2  mov     [rsp+1A8h+var_170], sil
0x1400381d7  or      dword ptr [rcx+44h], 2
0x1400381db  lea     rax, [rdx+0B8h]
0x1400381e2  mov     [rsp+1A8h+var_A8], rax
0x1400381ea  mov     rbx, [rax]
0x1400381ed  mov     rax, [rbx+30h]
0x1400381f1  mov     [rsp+1A8h+FileObject], rax
0x1400381f9  mov     [rsp+1A8h+var_98], rax
0x140038201  lea     r9, [r11+18h]
0x140038205  lea     r8, [r11-128h]
0x14003820c  lea     rdx, [r11-0F0h]
0x140038213  mov     rcx, rax
0x140038216  call    FatDecodeFileObject
0x14003821b  mov     rdx, [rsp+1A8h+var_F0]
0x140038223  mov     ecx, [rdx+0C8h]
0x140038229  bt      ecx, 16h
0x14003822d  jnb     loc_140038D65
0x140038233  cmp     eax, 2
0x140038236  jnz     loc_140038D4E
0x14003823c  mov     eax, [rdx+0C8h]
0x140038242  bt      eax, 0Eh
0x140038246  jnb     short loc_140038252
0x140038248  mov     ebx, 0C00000A2h
0x14003824d  jmp     loc_140038D6A
0x140038252  mov     r13, [rsp+1A8h+var_128]
0x14003825a  test    dword ptr [r13+0C0h], 20000h
0x140038265  jnz     short loc_140038271
0x140038267  mov     ebx, 0C0000022h
0x14003826c  jmp     loc_140038D6A
0x140038271  mov     r12, [rbx+20h]
0x140038275  mov     [rsp+1A8h+var_90], r12
0x14003827d  mov     r11d, [rbx+10h]
0x140038281  mov     [rsp+1A8h+var_138], r11d
0x140038286  mov     [rsp+1A8h+var_D4], r11d
0x14003828e  cmp     r11d, 20h ; ' '
0x140038292  jnb     short loc_14003829E
0x140038294  mov     ebx, 0C0000023h
0x140038299  jmp     loc_140038D6A
0x14003829e  lea     rax, [r15+40h]
0x1400382a2  mov     [rsp+1A8h+var_A0], rax
0x1400382aa  mov     ebx, 1
0x1400382af  cmp     [rax], sil
0x1400382b2  jz      short loc_1400382CE
0x1400382b4  mov     rdx, r11; Length
0x1400382b7  mov     r8d, ebx; Alignment
0x1400382ba  mov     rcx, r12; Address
0x1400382bd  call    cs:__imp_ProbeForRead
0x1400382c4  nop     dword ptr [rax+rax+00h]
0x1400382c9  mov     r11d, [rsp+1A8h+var_138]
0x1400382ce  mov     edi, [r12+8]
0x1400382d3  mov     [rsp+1A8h+var_130], edi
0x1400382d7  mov     [rsp+1A8h+var_134], edi
0x1400382db  mov     r10d, [r12+10h]
0x1400382e0  mov     [rsp+1A8h+var_154], r10d
0x1400382e5  mov     [rsp+1A8h+var_10C], r10d
0x1400382ed  mov     eax, [r12+0Ch]
0x1400382f2  mov     [rsp+1A8h+var_150], eax
0x1400382f6  mov     [rsp+1A8h+var_114], eax
0x1400382fd  movzx   ecx, word ptr [r12+1Ah]
0x140038303  mov     [rsp+1A8h+arg_18], cx
0x14003830b  mov     [rsp+1A8h+var_16C], cx
0x140038310  mov     r8b, [r12+19h]
0x140038315  mov     [rsp+1A8h+var_140], r8b
0x14003831a  mov     rax, [r12]
0x14003831e  mov     [rsp+1A8h+var_C0], rax
0x140038326  mov     qword ptr [rsp+1A8h+var_160], rax
0x14003832b  mov     [rsp+1A8h+var_88], rax
0x140038333  mov     al, [r12+16h]
0x140038338  mov     byte ptr [rsp+1A8h+arg_10], al
0x14003833f  mov     [rsp+1A8h+var_170], al
0x140038343  movzx   r9d, word ptr [r12+14h]
0x140038349  mov     [rsp+1A8h+var_D0], r9w
0x140038352  lea     eax, ds:1Ch[rcx*4]
0x140038359  cmp     eax, edi
0x14003835b  ja      loc_140038CED
0x140038361  cmp     eax, r11d
0x140038364  ja      loc_140038CED
0x14003836a  mov     ecx, eax
0x14003836c  lea     rdx, [rax+10h]
0x140038370  cmp     rdx, rdi
0x140038373  ja      short loc_1400383CE
0x140038375  mov     eax, r11d
0x140038378  cmp     rdx, rax
0x14003837b  ja      short loc_1400383CE
0x14003837d  mov     eax, cs:ExtendedEncryptedDataInfoSignature
0x140038383  cmp     [rcx+r12], eax
0x140038387  jnz     short loc_1400383CE
0x140038389  cmp     dword ptr [rcx+r12+4], 10h
0x14003838f  jnb     short loc_1400383AB
0x140038391  mov     edi, 0C000000Dh
0x140038396  mov     r8d, edi
0x140038399  mov     rdx, r15; Irp
0x14003839c  mov     rcx, r14; Entry
0x14003839f  call    FatCompleteRequest_Real
0x1400383a4  mov     eax, edi
0x1400383a6  jmp     loc_140038D7A
0x1400383ab  mov     eax, [rcx+r12+8]
0x1400383b0  test    bl, al
0x1400383b2  jz      short loc_1400383CE
0x1400383b4  mov     edi, 0C0000427h
0x1400383b9  mov     r8d, edi
0x1400383bc  mov     rdx, r15; Irp
0x1400383bf  mov     rcx, r14; Entry
0x1400383c2  call    FatCompleteRequest_Real
0x1400383c7  mov     eax, edi
0x1400383c9  jmp     loc_140038D7A
0x1400383ce  cmp     r8b, bl
0x1400383d1  jnz     loc_140038D4E
0x1400383d7  cmp     r10d, [rsp+1A8h+var_150]
0x1400383dc  ja      loc_140038D4E
0x1400383e2  test    r9w, r9w
0x1400383e6  jnz     loc_140038D4E
0x1400383ec  cmp     [rsp+1A8h+arg_18], si
0x1400383f4  jz      loc_140038D4E
0x1400383fa  lea     rax, [r15+0B8h]
0x140038401  mov     [rsp+1A8h+var_80], rax
0x140038409  cmp     edi, r11d
0x14003840c  ja      loc_140038D4E
0x140038412  mov     edi, esi
0x140038414  mov     [rsp+1A8h+var_C8], rsi
0x14003841c  mov     [rsp+1A8h+var_176], sil
0x140038421  mov     [rsp+1A8h+var_177], sil
0x140038426  mov     [rsp+1A8h+var_178], sil
0x14003842b  mov     [rsp+1A8h+var_100], rsi
0x140038433  mov     rax, rsi
0x140038436  mov     [rsp+1A8h+var_148], rax
0x14003843b  mov     [rsp+1A8h+var_E0], rax
0x140038443  mov     [rsp+1A8h+P], rsi
0x14003844b  mov     [rsp+1A8h+var_118], esi
0x140038452  mov     rdx, [rsp+1A8h+var_F0]
0x14003845a  mov     cl, [rdx+179h]
0x140038460  mov     eax, ebx
0x140038462  shl     eax, cl
0x140038464  mov     [rsp+1A8h+var_158], eax
0x140038468  mov     cl, [rdx+17Ah]
0x14003846e  mov     eax, ebx
0x140038470  shl     eax, cl
0x140038472  mov     [rsp+1A8h+var_110], eax
0x140038479  mov     rdx, r13
0x14003847c  mov     rcx, r14
0x14003847f  call    FatAcquireExclusiveFcb
0x140038484  mov     [rsp+1A8h+var_176], bl
0x140038488  mov     dl, bl; Wait
0x14003848a  mov     rcx, [r13+10h]; Resource
0x14003848e  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140038495  nop     dword ptr [rax+rax+00h]
0x14003849a  mov     [rsp+1A8h+var_177], bl
0x14003849e  lea     r9, [r15+30h]; IoStatus
0x1400384a2  xor     r8d, r8d; Length
0x1400384a5  xor     edx, edx; FileOffset
0x1400384a7  mov     rcx, [r13+78h]; SectionObjectPointer
0x1400384ab  call    cs:__imp_CcFlushCache
0x1400384b2  nop     dword ptr [rax+rax+00h]
0x1400384b7  xor     r9d, r9d; Flags
0x1400384ba  xor     r8d, r8d; Length
0x1400384bd  xor     edx, edx; FileOffset
0x1400384bf  mov     rcx, [r13+78h]; SectionObjectPointer
0x1400384c3  call    cs:__imp_CcPurgeCacheSection
0x1400384ca  nop     dword ptr [rax+rax+00h]
0x1400384cf  test    al, al
0x1400384d1  jnz     short loc_1400384DD
0x1400384d3  mov     edi, 0C000001Bh
0x1400384d8  jmp     loc_140038C48
0x1400384dd  mov     r8, qword ptr [rsp+1A8h+var_160]
0x1400384e2  cmp     r8, [r13+20h]
0x1400384e6  jg      loc_140038C43
0x1400384ec  test    r8, r8
0x1400384ef  js      loc_140038C43
0x1400384f5  mov     edx, esi
0x1400384f7  mov     [rsp+1A8h+var_164], edx
0x1400384fb  movzx   r9d, si
0x1400384ff  mov     r10b, byte ptr [rsp+1A8h+arg_10]
0x140038507  movzx   ecx, [rsp+1A8h+arg_18]
0x14003850f  cmp     r9w, cx
0x140038513  jnb     short loc_140038539
0x140038515  movzx   eax, r9w
0x140038519  mov     ecx, [r12+rax*4+1Ch]
0x14003851e  test    ecx, ecx
0x140038520  jnz     short loc_14003852D
0x140038522  mov     cl, r10b
0x140038525  mov     eax, ebx
0x140038527  shl     eax, cl
0x140038529  add     edx, eax
0x14003852b  jmp     short loc_14003852F
0x14003852d  add     edx, ecx
0x14003852f  mov     [rsp+1A8h+var_164], edx
0x140038533  add     r9w, bx
0x140038537  jmp     short loc_140038507
0x140038539  mov     r9d, [rsp+1A8h+var_154]
0x14003853e  cmp     r9d, edx
0x140038541  jz      short loc_140038560
0x140038543  mov     eax, r9d
0x140038546  add     rax, [rsp+1A8h+var_C0]
0x14003854e  cmp     rax, [r13+28h]
0x140038552  jl      loc_140038C43
0x140038558  movzx   ecx, [rsp+1A8h+arg_18]
0x140038560  movzx   eax, si
0x140038563  mov     rdx, [rsp+1A8h+var_100]
0x14003856b  mov     [rsp+1A8h+var_168], ax
0x140038570  cmp     ax, cx
0x140038573  jnb     loc_140038BE5
0x140038579  mov     [rsp+1A8h+var_178], bl
0x14003857d  movzx   eax, ax
0x140038580  mov     ebx, [r12+rax*4+1Ch]
0x140038585  mov     [rsp+1A8h+var_13C], ebx
0x140038589  mov     [rsp+1A8h+var_D8], ebx
0x140038590  mov     [rsp+1A8h+var_164], ebx
0x140038594  mov     [rsp+1A8h+var_178], sil
0x140038599  test    ebx, ebx
0x14003859b  jz      loc_140038AF0
0x1400385a1  test    r9d, r9d
0x1400385a4  jz      loc_140038AEC
0x1400385aa  mov     eax, [rsp+1A8h+var_130]
0x1400385ae  lea     ecx, [rbx+rax]
0x1400385b1  cmp     ecx, [rsp+1A8h+var_138]
0x1400385b5  ja      loc_140038C43
0x1400385bb  cmp     ecx, eax
0x1400385bd  jb      loc_140038C43
0x1400385c3  lea     rdi, [r12+rax]
0x1400385c7  mov     [rsp+1A8h+Src], rdi
0x1400385cf  mov     [rsp+1A8h+var_130], ecx
0x1400385d3  mov     [rsp+1A8h+var_134], ecx
0x1400385d7  mov     rcx, [rsp+1A8h+FileObject]; FileObject
0x1400385df  call    cs:__imp_IoGetRelatedDeviceObject
0x1400385e6  nop     dword ptr [rax+rax+00h]
0x1400385eb  mov     [rsp+1A8h+var_B0], rax
0x1400385f3  xor     edx, edx
0x1400385f5  mov     eax, ebx
0x1400385f7  mov     r8d, [rsp+1A8h+var_158]
0x1400385fc  div     r8d
0x1400385ff  test    edx, edx
0x140038601  jnz     short loc_14003861F
0x140038603  xor     edx, edx
0x140038605  mov     rax, rdi
0x140038608  div     r8
0x14003860b  test    rdx, rdx
0x14003860e  jnz     short loc_14003861F
0x140038610  mov     edi, ebx
0x140038612  mov     rax, [rsp+1A8h+Src]
0x14003861a  jmp     loc_140038770
0x14003861f  lea     edi, [r8-1]
0x140038623  add     edi, ebx
0x140038625  mov     eax, r8d
0x140038628  neg     eax
0x14003862a  and     edi, eax
0x14003862c  cmp     edi, ebx
0x14003862e  jb      loc_140038C43
0x140038634  mov     r9, [rsp+1A8h+var_148]
0x140038639  test    r9, r9
0x14003863c  jz      short loc_140038683
0x14003863e  cmp     [rsp+1A8h+var_118], edi
0x140038645  jnb     short loc_14003867A
0x140038647  xor     edx, edx; Tag
0x140038649  mov     rcx, [rsp+1A8h+P]; P
0x140038651  call    cs:__imp_ExFreePoolWithTag
0x140038658  nop     dword ptr [rax+rax+00h]
0x14003865d  mov     r9, rsi
0x140038660  mov     [rsp+1A8h+var_148], rsi
0x140038665  mov     [rsp+1A8h+var_E0], rsi
0x14003866d  mov     [rsp+1A8h+P], rsi
0x140038675  mov     r8d, [rsp+1A8h+var_158]
0x14003867a  test    r9, r9
0x14003867d  jnz     loc_140038731
0x140038683  lea     eax, [r8-1]
0x140038687  add     eax, edi
0x140038689  mov     [rsp+1A8h+Size], rax
0x140038691  mov     r8d, 20746146h; Tag
0x140038697  mov     edx, eax; NumberOfBytes
0x140038699  mov     ecx, 401h; PoolType
0x14003869e  call    cs:__imp_ExAllocatePoolWithTag
0x1400386a5  nop     dword ptr [rax+rax+00h]
0x1400386aa  mov     r9, rax
0x1400386ad  mov     [rsp+1A8h+var_148], rax
  ... truncated ...
```
