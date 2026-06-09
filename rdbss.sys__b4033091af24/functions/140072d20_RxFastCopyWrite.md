# RxFastCopyWrite

- ea: `0x140072d20`
- end: `0x14007379a`
- name: `RxFastCopyWrite`
- size: `2682`
- prototype: `__int64 __usercall@<rax>(PFILE_OBJECT FileObject@<rcx>, PLARGE_INTEGER FileOffset@<rdx>, ULONG Length@<r8d>, int, PVOID Buffer, __int64, __int64, PIRP Irp)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x140072aa0`

## callees

- `0x140003410`
- `0x1400037e0`
- `0x140008f60`
- `0x140009ea0`
- `0x14000e770`
- `0x14001d138`
- `0x140025d00`
- `0x140072d20`

## import_xrefs

- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14007b7ae`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14007b7d8`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14007b7ae`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14007b7d8`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14007313c`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1400731e7`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140073542`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140073611`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14007313c`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1400731e7`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140073542`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140073611`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140072f1f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140072fec`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140073257`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14007330f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400733d7`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400734f7`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140073644`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400736bf`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140072f1f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140072fec`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140073257`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14007330f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400733d7`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400734f7`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140073644`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400736bf`
- `ntoskrnl!ExReleaseResourceLite` at `0x140072fd8`
- `ntoskrnl!ExReleaseResourceLite` at `0x140073283`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400733b5`
- `ntoskrnl!ExReleaseResourceLite` at `0x14007350b`
- `ntoskrnl!ExReleaseResourceLite` at `0x140073658`
- `ntoskrnl!ExReleaseResourceLite` at `0x140073714`
- `ntoskrnl!ExReleaseResourceLite` at `0x140072fd8`
- `ntoskrnl!ExReleaseResourceLite` at `0x140073283`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400733b5`
- `ntoskrnl!ExReleaseResourceLite` at `0x14007350b`
- `ntoskrnl!ExReleaseResourceLite` at `0x140073658`
- `ntoskrnl!ExReleaseResourceLite` at `0x140073714`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140072f05`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400732e7`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140072f05`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400732e7`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140073059`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140073441`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140073059`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140073441`
- `ntoskrnl!CcCanIWrite` at `0x140072d9a`
- `ntoskrnl!CcCanIWrite` at `0x140072d9a`
- `ntoskrnl!CcCopyWriteWontFlush` at `0x140072dcd`
- `ntoskrnl!CcCopyWriteWontFlush` at `0x140072dcd`
- `ntoskrnl!CcZeroData` at `0x140073179`
- `ntoskrnl!CcZeroData` at `0x140073575`
- `ntoskrnl!CcZeroData` at `0x140073179`
- `ntoskrnl!CcZeroData` at `0x140073575`
- `ntoskrnl!CcFastCopyWrite` at `0x14007319a`
- `ntoskrnl!CcFastCopyWrite` at `0x14007319a`
- `ntoskrnl!CcCopyWrite` at `0x1400735b7`
- `ntoskrnl!CcCopyWrite` at `0x1400735b7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140073736`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140073736`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140072e0c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140072e0c`

## pseudocode

```c
__int64 __fastcall RxFastCopyWrite(
        PFILE_OBJECT FileObject,
        LARGE_INTEGER FileOffset,
        ULONG Length,
        BOOLEAN a4,
        int a5,
        PVOID Buffer,
        _DWORD *a7,
        __int64 a8,
        PIRP Irp)
{
  __int64 v10; // r15
  LARGE_INTEGER *QuadPart; // rdi
  bool v13; // zf
  char *v14; // rsi
  char *FsContext; // r14
  LARGE_INTEGER v16; // rdx
  __int64 v17; // r8
  _DWORD *v18; // rax
  BOOLEAN v19; // r15
  int v20; // r12d
  enum _RX_BLOCK_CONDITION *RxContext; // rax
  char v22; // bl
  char v23; // r9
  ULONG LowPart; // edi
  unsigned int v25; // ebx
  char v26; // cl
  char v27; // al
  PDEVICE_OBJECT v28; // rdx
  PFAST_IO_DISPATCH v29; // r8
  char v30; // r9
  LARGE_INTEGER v31; // rcx
  __int64 v32; // rbx
  PDEVICE_OBJECT RelatedDeviceObject; // rdx
  PFAST_IO_DISPATCH FastIoDispatch; // rax
  __int64 v35; // rdi
  struct _ERESOURCE *v36; // rcx
  __int64 v37; // rax
  struct _ERESOURCE *v38; // rcx
  struct _ERESOURCE *v39; // rcx
  __int64 v40; // r9
  char v42; // [rsp+50h] [rbp-98h]
  char v43; // [rsp+51h] [rbp-97h]
  _WORD v44[7]; // [rsp+52h] [rbp-96h] BYREF
  PLARGE_INTEGER StartOffset; // [rsp+60h] [rbp-88h]
  __int64 v46; // [rsp+68h] [rbp-80h]
  ULONG v47; // [rsp+70h] [rbp-78h]
  char *v48; // [rsp+78h] [rbp-70h]
  LARGE_INTEGER EndOffset; // [rsp+80h] [rbp-68h] BYREF
  char *v50; // [rsp+88h] [rbp-60h]
  ULONG *p_Flags; // [rsp+90h] [rbp-58h]
  _OWORD v52[5]; // [rsp+98h] [rbp-50h] BYREF
  LARGE_INTEGER FileOffseta; // [rsp+F8h] [rbp+10h] BYREF
  ULONG Lengtha; // [rsp+100h] [rbp+18h]
  BOOLEAN v55; // [rsp+108h] [rbp+20h]

  v55 = a4;
  Lengtha = Length;
  FileOffseta = FileOffset;
  v10 = Length;
  QuadPart = (LARGE_INTEGER *)FileOffset.QuadPart;
  if ( *(_DWORD *)FileOffset.QuadPart != -1 || (v13 = *(_DWORD *)(FileOffset.QuadPart + 4) == -1, LOBYTE(a8) = 1, !v13) )
    LOBYTE(a8) = 0;
  LOBYTE(v44[1]) = 0;
  v43 = 0;
  HIBYTE(v44[2]) = 0;
  v14 = 0;
  *(_QWORD *)&v44[3] = 0;
  FsContext = (char *)FileObject->FsContext;
  v50 = FsContext;
  if ( CcCanIWrite(FileObject, Length, a4, 0) )
  {
    p_Flags = &FileObject->Flags;
    if ( (FileObject->Flags & 0x10) == 0 )
    {
      if ( CcCopyWriteWontFlush(FileObject, QuadPart, v10) )
      {
        v18 = a7;
        *a7 = 0;
        v46 = v10;
        *((_QWORD *)v18 + 1) = v10;
        if ( !(_DWORD)v10 )
        {
          v19 = 1;
          v20 = 552;
          RxContext = 0;
          goto LABEL_19;
        }
        KeEnterCriticalRegion();
        LOBYTE(v44[1]) = 1;
        LOBYTE(v44[2]) = 1;
        if ( !*((_QWORD *)FsContext + 16) )
          goto LABEL_22;
        LOBYTE(v44[0]) = 0;
        if ( a4 )
        {
          RxContext = (enum _RX_BLOCK_CONDITION *)RxCreateRxContext(
                                                    0,
                                                    *(PRDBSS_DEVICE_OBJECT *)(*(_QWORD *)(*((_QWORD *)FsContext + 15)
                                                                                        + 32LL)
                                                                            + 48LL),
                                                    2u);
          *(_QWORD *)&v44[3] = RxContext;
          if ( !RxContext )
          {
            v19 = 0;
            v20 = 584;
            goto LABEL_19;
          }
        }
        else
        {
          RxContext = 0;
        }
        HIBYTE(v44[2]) = RxWaitForStableLViewOnFcbAndAcquireRundown(RxContext, (PMRX_FCB)FsContext, (__int64)v44);
        if ( HIBYTE(v44[2]) || LOBYTE(v44[0]) )
        {
LABEL_22:
          v19 = 1;
          v42 = 0;
          v20 = 0;
          if ( !a4 || *((_DWORD *)FsContext + 7) )
          {
            FileOffseta.QuadPart = 0;
            if ( (_BYTE)a8 || QuadPart->QuadPart + v46 > *((_QWORD *)FsContext + 5) )
            {
              if ( !ExAcquireResourceExclusiveLite(*((PERESOURCE *)FsContext + 1), a4) )
              {
                v20 = 930;
                goto LABEL_17;
              }
              v30 = 0;
            }
            else
            {
              if ( !ExAcquireResourceSharedLite(*((PERESOURCE *)FsContext + 1), a4) )
              {
                v20 = 944;
                goto LABEL_17;
              }
              v30 = 1;
            }
            v43 = 1;
            HIBYTE(v44[0]) = 1;
            if ( (_BYTE)a8 )
              v31 = *(LARGE_INTEGER *)(FsContext + 32);
            else
              v31 = *QuadPart;
            v32 = v31.QuadPart + v46;
            StartOffset = (PLARGE_INTEGER)(v31.QuadPart + v46);
            FileOffseta = v31;
            if ( !FileObject->PrivateCacheMap
              || (v16.QuadPart = (unsigned __int8)FsContext[5], !LOBYTE(v16.LowPart))
              || (v17 = *((_QWORD *)FsContext + 5), v31.QuadPart >= v17 + 0x2000)
              || v32 > *((_QWORD *)FsContext + 3)
              || v32 <= 0 )
            {
              v20 = 986;
              goto LABEL_17;
            }
            if ( v30 && v32 > v17 )
            {
              ExReleaseResourceLite(*((PERESOURCE *)FsContext + 1));
              v43 = 0;
              HIBYTE(v44[0]) = 0;
              if ( !ExAcquireResourceExclusiveLite(*((PERESOURCE *)FsContext + 1), v55) )
              {
                v20 = 1006;
                goto LABEL_17;
              }
              if ( (_BYTE)a8 )
              {
                FileOffseta = *(LARGE_INTEGER *)(FsContext + 32);
                v32 = FileOffseta.QuadPart + v46;
                StartOffset = (PLARGE_INTEGER)(FileOffseta.QuadPart + v46);
              }
              if ( !FileObject->PrivateCacheMap
                || (v16.QuadPart = (unsigned __int8)FsContext[5], !LOBYTE(v16.LowPart))
                || v32 > *((_QWORD *)FsContext + 3) )
              {
                v20 = 1025;
                goto LABEL_17;
              }
            }
            if ( LOBYTE(v16.LowPart) != 2 )
              goto LABEL_97;
            RelatedDeviceObject = IoGetRelatedDeviceObject(FileObject);
            FastIoDispatch = RelatedDeviceObject->DriverObject->FastIoDispatch;
            v52[0] = 0;
            if ( QuadPart->QuadPart == -1 )
              QuadPart = (LARGE_INTEGER *)(FsContext + 32);
            if ( ((unsigned __int8 (__fastcall *)(PFILE_OBJECT, LARGE_INTEGER *, _QWORD, _QWORD, int, _BYTE, _OWORD *, PDEVICE_OBJECT))FastIoDispatch->FastIoCheckIfPossible)(
                   FileObject,
                   QuadPart,
                   Lengtha,
                   v55,
                   a5,
                   0,
                   v52,
                   RelatedDeviceObject) )
            {
LABEL_97:
              v35 = *((_QWORD *)FsContext + 4);
              if ( v32 <= v35 )
              {
                v48 = 0;
                v35 = 0;
                a8 = 0;
              }
              else
              {
                v42 = 1;
                a8 = *((_QWORD *)FsContext + 4);
                v14 = (char *)*((_QWORD *)FsContext + 5);
                v48 = v14;
                if ( HIDWORD(v35) == HIDWORD(StartOffset)
                  || (v36 = (struct _ERESOURCE *)*((_QWORD *)FsContext + 2)) == 0 )
                {
                  *((_QWORD *)FsContext + 4) = v32;
                }
                else
                {
                  ExAcquireResourceExclusiveLite(v36, 1u);
                  *((_QWORD *)FsContext + 4) = v32;
                  ExReleaseResourceLite(*((PERESOURCE *)FsContext + 2));
                  *((_DWORD *)FsContext + 40) &= 0xFFBFF7FF;
                }
              }
              IoSetTopLevelIrp(Irp);
              if ( FileOffseta.QuadPart > *((_QWORD *)FsContext + 5) )
              {
                v19 = CcZeroData(FileObject, (PLARGE_INTEGER)FsContext + 5, &FileOffseta, v55);
                HIBYTE(v44[1]) = v19;
              }
              if ( v19 )
              {
                v19 = CcCopyWrite(FileObject, &FileOffseta, Lengtha, v55, Buffer);
                HIBYTE(v44[1]) = v19;
              }
              IoSetTopLevelIrp(0);
              if ( v19 )
              {
                v37 = *((_QWORD *)FsContext + 5);
                if ( v32 > v37 )
                {
                  if ( HIDWORD(v37) == HIDWORD(StartOffset)
                    || (v38 = (struct _ERESOURCE *)*((_QWORD *)FsContext + 2)) == 0 )
                  {
                    *((_QWORD *)FsContext + 5) = v32;
                  }
                  else
                  {
                    ExAcquireResourceExclusiveLite(v38, 1u);
                    *((_QWORD *)FsContext + 5) = v32;
                    ExReleaseResourceLite(*((PERESOURCE *)FsContext + 2));
                  }
                }
                v16.QuadPart = (LONGLONG)p_Flags;
                _InterlockedOr((volatile signed __int32 *)p_Flags, 0x1000u);
                if ( v42 )
                {
                  *((_QWORD *)FileObject->SectionObjectPointer->SharedCacheMap + 1) = v32;
                  _InterlockedOr((volatile signed __int32 *)v16.QuadPart, 0x2000u);
                }
                FileObject->CurrentByteOffset.QuadPart = FileOffseta.QuadPart + v46;
              }
              else if ( v42 )
              {
                v39 = (struct _ERESOURCE *)*((_QWORD *)FsContext + 2);
                if ( v39 )
                {
                  ExAcquireResourceExclusiveLite(v39, 1u);
                  *((_QWORD *)FsContext + 4) = v35;
                  *((_QWORD *)FsContext + 5) = v14;
                  ExReleaseResourceLite(*((PERESOURCE *)FsContext + 2));
                }
                else
                {
                  *((_QWORD *)FsContext + 4) = v35;
                  *((_QWORD *)FsContext + 5) = v14;
                }
              }
              goto LABEL_18;
            }
            v20 = 1073;
            goto LABEL_17;
          }
          v22 = a8;
          if ( (_BYTE)a8 || QuadPart->LowPart + Lengtha > *((_DWORD *)FsContext + 10) )
          {
            ExAcquireResourceExclusiveLite(*((PERESOURCE *)FsContext + 1), 1u);
            v23 = 0;
          }
          else
          {
            ExAcquireResourceSharedLite(*((PERESOURCE *)FsContext + 1), 1u);
            v23 = 1;
          }
          v43 = 1;
          if ( v22 )
          {
            LowPart = *((_DWORD *)FsContext + 8);
            v47 = LowPart;
            v25 = LowPart + Lengtha;
            LODWORD(v46) = LowPart + Lengtha;
            LOBYTE(v16.LowPart) = LowPart + Lengtha < LowPart;
          }
          else
          {
            LowPart = QuadPart->LowPart;
            v47 = LowPart;
            v25 = LowPart + Lengtha;
            LODWORD(v46) = LowPart + Lengtha;
            if ( LowPart + Lengtha < LowPart || (v16 = FileOffseta, *(_DWORD *)(FileOffseta.QuadPart + 4)) )
              v16.QuadPart = 1;
            else
              LOBYTE(v16.LowPart) = 0;
          }
          LOBYTE(v44[0]) = v16.LowPart;
          if ( !FileObject->PrivateCacheMap
            || (v26 = FsContext[5]) == 0
            || v25 > *((_DWORD *)FsContext + 6)
            || (StartOffset = (PLARGE_INTEGER)(FsContext + 40),
                v17 = *((unsigned int *)FsContext + 10),
                LowPart >= (int)v17 + 0x2000)
            || *((_DWORD *)FsContext + 7)
            || LOBYTE(v16.LowPart) )
          {
            v20 = 688;
          }
          else
          {
            if ( !v23 || v25 <= (unsigned int)v17 )
              goto LABEL_138;
            ExReleaseResourceLite(*((PERESOURCE *)FsContext + 1));
            ExAcquireResourceExclusiveLite(*((PERESOURCE *)FsContext + 1), 1u);
            if ( (_BYTE)a8 )
            {
              LowPart = *((_DWORD *)FsContext + 8);
              v47 = LowPart;
              v25 = LowPart + Lengtha;
              LODWORD(v46) = LowPart + Lengtha;
              v27 = LowPart + Lengtha < LowPart;
            }
            else
            {
              v27 = v44[0];
            }
            if ( !FileObject->PrivateCacheMap
              || (v26 = FsContext[5]) == 0
              || v25 > *((_DWORD *)FsContext + 6)
              || *((_DWORD *)FsContext + 7)
              || v27 )
            {
              v20 = 723;
            }
            else
            {
LABEL_138:
              if ( v26 != 2 )
                goto LABEL_56;
              v28 = IoGetRelatedDeviceObject(FileObject);
              v29 = v28->DriverObject->FastIoDispatch;
              v52[0] = 0;
              if ( *(_QWORD *)FileOffseta.QuadPart == -1 )
                FileOffseta.QuadPart = (LONGLONG)(FsContext + 32);
              if ( ((unsigned __int8 (__fastcall *)(PFILE_OBJECT, LARGE_INTEGER, _QWORD, __int64, int, _BYTE, _OWORD *, PDEVICE_OBJECT))v29->FastIoCheckIfPossible)(
                     FileObject,
                     FileOffseta,
                     Lengtha,
                     1,
                     a5,
                     0,
                     v52,
                     v28) )
              {
LABEL_56:
                *(_QWORD *)&v52[0] = StartOffset;
                FileOffseta.LowPart = 0;
                LODWORD(a8) = 0;
                v48 = FsContext + 32;
                if ( v25 > *((_DWORD *)FsContext + 8) )
                {
                  v42 = 1;
                  FileOffseta.LowPart = *((_DWORD *)FsContext + 8);
                  LODWORD(a8) = *((_DWORD *)FsContext + 10);
                  *((_DWORD *)FsContext + 8) = v25;
                  *((_DWORD *)FsContext + 40) &= 0xFFBFF7FF;
                }
                IoSetTopLevelIrp(Irp);
                if ( LowPart > StartOffset->LowPart )
                {
                  EndOffset.QuadPart = LowPart;
                  CcZeroData(FileObject, StartOffset, &EndOffset, 1u);
                }
                CcFastCopyWrite(FileObject, LowPart, Lengtha, Buffer);
                IoSetTopLevelIrp(0);
                if ( v25 > StartOffset->LowPart )
                  StartOffset->LowPart = v25;
                v16.QuadPart = (LONGLONG)p_Flags;
                _InterlockedOr((volatile signed __int32 *)p_Flags, 0x1000u);
                if ( v42 )
                {
                  *((_DWORD *)FileObject->SectionObjectPointer->SharedCacheMap + 2) = v25;
                  _InterlockedOr((volatile signed __int32 *)v16.QuadPart, 0x2000u);
                }
                FileObject->CurrentByteOffset.QuadPart = LowPart + Lengtha;
                goto LABEL_18;
              }
              v20 = 771;
            }
          }
        }
        else
        {
          v20 = 599;
        }
LABEL_17:
        v19 = 0;
LABEL_18:
        RxContext = *(enum _RX_BLOCK_CONDITION **)&v44[3];
        goto LABEL_19;
      }
    }
  }
  v19 = 0;
  v20 = 534;
  RxContext = 0;
LABEL_19:
  if ( HIBYTE(v44[2]) )
  {
    if ( RxContext )
      RxReleaseLViewRundown(RxContext);
    else
      RxReleaseRundownDerefView(FsContext);
  }
  if ( v43 )
    ExReleaseResourceLite(*((PERESOURCE *)FsContext + 1));
  if ( *(_QWORD *)&v44[3] )
    RxDereferenceAndDeleteRxContext_Real(*(PRX_CONTEXT *)&v44[3]);
  if ( LOBYTE(v44[1]) )
    KeLeaveCriticalRegion();
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v40 = 78;
    if ( v19 )
      v40 = 89;
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD))WPP_SF_dd)(
      WPP_GLOBAL_Control->AttachedDevice,
      (LARGE_INTEGER)v16.QuadPart,
      v17,
      v40,
      v20);
  }
  return v19;
}

```

## disassembly

```asm
0x140072d20  mov     [rsp+arg_18], r9b
0x140072d25  mov     [rsp+Length], r8d
0x140072d2a  mov     qword ptr [rsp+FileOffset], rdx
0x140072d2f  mov     [rsp+arg_0], rcx
0x140072d34  push    rbx
0x140072d35  push    rsi
0x140072d36  push    rdi
0x140072d37  push    r12
0x140072d39  push    r13
0x140072d3b  push    r14
0x140072d3d  push    r15
0x140072d3f  sub     rsp, 0B0h
0x140072d46  movzx   ebx, r9b
0x140072d4a  mov     r15d, r8d
0x140072d4d  mov     rdi, rdx
0x140072d50  mov     r13, rcx
0x140072d53  cmp     dword ptr [rdx], 0FFFFFFFFh
0x140072d56  jnz     short loc_140072D66
0x140072d58  cmp     dword ptr [rdx+4], 0FFFFFFFFh
0x140072d5c  mov     byte ptr [rsp+0E8h+arg_38], 1
0x140072d64  jz      short loc_140072D6E
0x140072d66  mov     byte ptr [rsp+0E8h+arg_38], 0
0x140072d6e  mov     [rsp+0E8h+var_96+2], 0
0x140072d73  mov     [rsp+0E8h+var_97], 0
0x140072d78  mov     [rsp+0E8h+var_96+5], 0
0x140072d7d  xor     esi, esi
0x140072d7f  mov     qword ptr [rsp+0E8h+var_96+6], rsi
0x140072d84  mov     r14, [rcx+18h]
0x140072d88  mov     [rsp+0E8h+var_60], r14
0x140072d90  xor     r9d, r9d; Retrying
0x140072d93  movzx   r8d, bl; Wait
0x140072d97  mov     edx, r15d; BytesToWrite
0x140072d9a  call    cs:__imp_CcCanIWrite
0x140072da1  nop     dword ptr [rax+rax+00h]
0x140072da6  test    al, al
0x140072da8  jz      loc_1400736F0
0x140072dae  lea     rax, [r13+50h]
0x140072db2  mov     [rsp+0E8h+var_58], rax
0x140072dba  mov     eax, [rax]
0x140072dbc  test    al, 10h
0x140072dbe  jnz     loc_1400736F0
0x140072dc4  mov     r8d, r15d; Length
0x140072dc7  mov     rdx, rdi; FileOffset
0x140072dca  mov     rcx, r13; FileObject
0x140072dcd  call    cs:__imp_CcCopyWriteWontFlush
0x140072dd4  nop     dword ptr [rax+rax+00h]
0x140072dd9  test    al, al
0x140072ddb  jz      loc_1400736F0
0x140072de1  mov     rax, [rsp+0E8h+arg_30]
0x140072de9  mov     [rax], esi
0x140072deb  mov     rcx, r15
0x140072dee  mov     [rsp+0E8h+var_80], rcx
0x140072df3  mov     [rax+8], rcx
0x140072df7  test    r15d, r15d
0x140072dfa  jnz     short loc_140072E0C
0x140072dfc  mov     r15b, 1
0x140072dff  mov     r12d, 228h
0x140072e05  mov     eax, esi
0x140072e07  jmp     loc_140072EA4
0x140072e0c  call    cs:__imp_KeEnterCriticalRegion
0x140072e13  nop     dword ptr [rax+rax+00h]
0x140072e18  mov     al, 1
0x140072e1a  mov     [rsp+0E8h+var_96+2], al
0x140072e1e  mov     [rsp+0E8h+var_96+4], al
0x140072e22  cmp     [r14+80h], rsi
0x140072e29  jz      loc_140072EC5
0x140072e2f  mov     [rsp+0E8h+var_96], sil
0x140072e34  test    bl, bl
0x140072e36  jz      short loc_140072E66
0x140072e38  mov     rax, [r14+78h]
0x140072e3c  mov     rdx, [rax+20h]
0x140072e40  mov     r8d, 2; InitialContextFlags
0x140072e46  mov     rdx, [rdx+30h]; RxDeviceObject
0x140072e4a  xor     ecx, ecx; Irp
0x140072e4c  call    RxCreateRxContext
0x140072e51  mov     qword ptr [rsp+0E8h+var_96+6], rax
0x140072e56  test    rax, rax
0x140072e59  jnz     short loc_140072E69
0x140072e5b  xor     r15b, r15b
0x140072e5e  mov     r12d, 248h
0x140072e64  jmp     short loc_140072EA4
0x140072e66  mov     rax, rsi
0x140072e69  test    bl, bl
0x140072e6b  setz    r8b
0x140072e6f  lea     rcx, [rsp+0E8h+var_96]
0x140072e74  mov     [rsp+0E8h+var_C8], rcx; __int64
0x140072e79  xor     r9d, r9d
0x140072e7c  mov     rdx, r14; MrxFcb
0x140072e7f  mov     rcx, rax; Condition
0x140072e82  call    RxWaitForStableLViewOnFcbAndAcquireRundown
0x140072e87  mov     [rsp+0E8h+var_96+5], al
0x140072e8b  test    al, al
0x140072e8d  jnz     short loc_140072EC5
0x140072e8f  cmp     [rsp+0E8h+var_96], sil
0x140072e94  jnz     short loc_140072EC5
0x140072e96  mov     r12d, 257h
0x140072e9c  xor     r15b, r15b
0x140072e9f  mov     rax, qword ptr [rsp+0E8h+var_96+6]
0x140072ea4  cmp     [rsp+0E8h+var_96+5], 0
0x140072ea9  jz      loc_140073709
0x140072eaf  test    rax, rax
0x140072eb2  jz      loc_140073701
0x140072eb8  mov     rcx, rax
0x140072ebb  call    RxReleaseLViewRundown
0x140072ec0  jmp     loc_140073709
0x140072ec5  mov     r15b, 1
0x140072ec8  mov     [rsp+0E8h+var_98], sil
0x140072ecd  mov     r12d, esi
0x140072ed0  test    bl, bl
0x140072ed2  jz      loc_1400732C0
0x140072ed8  cmp     [r14+1Ch], esi
0x140072edc  jnz     loc_1400732C0
0x140072ee2  movzx   ebx, byte ptr [rsp+0E8h+arg_38]
0x140072eea  test    bl, bl
0x140072eec  jnz     short loc_140072F17
0x140072eee  mov     ecx, [rsp+0E8h+Length]
0x140072ef5  add     ecx, [rdi]
0x140072ef7  cmp     ecx, [r14+28h]
0x140072efb  ja      short loc_140072F17
0x140072efd  movzx   edx, r15b; Wait
0x140072f01  mov     rcx, [r14+8]; Resource
0x140072f05  call    cs:__imp_ExAcquireResourceSharedLite
0x140072f0c  nop     dword ptr [rax+rax+00h]
0x140072f11  movzx   r9d, r15b
0x140072f15  jmp     short loc_140072F2E
0x140072f17  movzx   edx, r15b; Wait
0x140072f1b  mov     rcx, [r14+8]; Resource
0x140072f1f  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140072f26  nop     dword ptr [rax+rax+00h]
0x140072f2b  xor     r9b, r9b
0x140072f2e  mov     [rsp+0E8h+var_97], r15b
0x140072f33  test    bl, bl
0x140072f35  mov     ebx, [rsp+0E8h+Length]
0x140072f3c  jz      short loc_140072F53
0x140072f3e  mov     edi, [r14+20h]
0x140072f42  mov     [rsp+0E8h+var_78], edi
0x140072f46  add     ebx, edi
0x140072f48  mov     dword ptr [rsp+0E8h+var_80], ebx
0x140072f4c  cmp     ebx, edi
0x140072f4e  setb    dl
0x140072f51  jmp     short loc_140072F78
0x140072f53  mov     edi, [rdi]
0x140072f55  mov     [rsp+0E8h+var_78], edi
0x140072f59  add     ebx, edi
0x140072f5b  mov     dword ptr [rsp+0E8h+var_80], ebx
0x140072f5f  cmp     ebx, edi
0x140072f61  jb      short loc_140072F74
0x140072f63  mov     rdx, qword ptr [rsp+0E8h+FileOffset]
0x140072f6b  cmp     [rdx+4], esi
0x140072f6e  jnz     short loc_140072F74
0x140072f70  xor     dl, dl
0x140072f72  jmp     short loc_140072F78
0x140072f74  movzx   edx, r15b
0x140072f78  mov     [rsp+0E8h+var_96], dl
0x140072f7c  cmp     [r13+30h], rsi
0x140072f80  jz      loc_1400732B5
0x140072f86  movzx   ecx, byte ptr [r14+5]
0x140072f8b  test    cl, cl
0x140072f8d  jz      loc_1400732B5
0x140072f93  cmp     ebx, [r14+18h]
0x140072f97  ja      loc_1400732B5
0x140072f9d  lea     rax, [r14+28h]
0x140072fa1  mov     [rsp+0E8h+StartOffset], rax
0x140072fa6  mov     r8d, [rax]
0x140072fa9  lea     eax, [r8+2000h]
0x140072fb0  cmp     edi, eax
0x140072fb2  jnb     loc_1400732B5
0x140072fb8  cmp     [r14+1Ch], esi
0x140072fbc  jnz     loc_1400732B5
0x140072fc2  test    dl, dl
0x140072fc4  jnz     loc_1400732B5
0x140072fca  test    r9b, r9b
0x140072fcd  jz      short loc_14007304D
0x140072fcf  cmp     ebx, r8d
0x140072fd2  jbe     short loc_14007304D
0x140072fd4  mov     rcx, [r14+8]; Resource
0x140072fd8  call    cs:__imp_ExReleaseResourceLite
0x140072fdf  nop     dword ptr [rax+rax+00h]
0x140072fe4  movzx   edx, r15b; Wait
0x140072fe8  mov     rcx, [r14+8]; Resource
0x140072fec  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140072ff3  nop     dword ptr [rax+rax+00h]
0x140072ff8  cmp     byte ptr [rsp+0E8h+arg_38], sil
0x140073000  jz      short loc_14007301E
0x140073002  mov     edi, [r14+20h]
0x140073006  mov     [rsp+0E8h+var_78], edi
0x14007300a  mov     ebx, [rsp+0E8h+Length]
0x140073011  add     ebx, edi
0x140073013  mov     dword ptr [rsp+0E8h+var_80], ebx
0x140073017  cmp     ebx, edi
0x140073019  setb    al
0x14007301c  jmp     short loc_140073023
0x14007301e  movzx   eax, [rsp+0E8h+var_96]
0x140073023  cmp     [r13+30h], rsi
0x140073027  jz      short loc_140073042
0x140073029  movzx   ecx, byte ptr [r14+5]
0x14007302e  test    cl, cl
0x140073030  jz      short loc_140073042
0x140073032  cmp     ebx, [r14+18h]
0x140073036  ja      short loc_140073042
0x140073038  cmp     [r14+1Ch], esi
0x14007303c  jnz     short loc_140073042
0x14007303e  test    al, al
0x140073040  jz      short loc_14007304D
0x140073042  mov     r12d, 2D3h
0x140073048  jmp     loc_140072E9C
0x14007304d  cmp     cl, 2
0x140073050  jnz     loc_1400730E6
0x140073056  mov     rcx, r13; FileObject
0x140073059  call    cs:__imp_IoGetRelatedDeviceObject
0x140073060  nop     dword ptr [rax+rax+00h]
0x140073065  mov     rdx, rax
0x140073068  mov     rcx, [rax+8]
0x14007306c  mov     r8, [rcx+50h]
0x140073070  xorps   xmm0, xmm0
0x140073073  movups  [rsp+0E8h+var_50], xmm0
0x14007307b  mov     rax, qword ptr [rsp+0E8h+FileOffset]
0x140073083  cmp     qword ptr [rax], 0FFFFFFFFFFFFFFFFh
0x140073087  jnz     short loc_140073095
0x140073089  lea     rax, [r14+20h]
0x14007308d  mov     qword ptr [rsp+0E8h+FileOffset], rax
0x140073095  mov     rax, [r8+8]
0x140073099  mov     [rsp+0E8h+var_B0], rdx
0x14007309e  lea     rcx, [rsp+0E8h+var_50]
0x1400730a6  mov     [rsp+0E8h+var_B8], rcx
0x1400730ab  mov     [rsp+0E8h+var_C0], sil
0x1400730b0  mov     ecx, [rsp+0E8h+arg_20]
0x1400730b7  mov     dword ptr [rsp+0E8h+var_C8], ecx
0x1400730bb  movzx   r9d, r15b
0x1400730bf  mov     r8d, [rsp+0E8h+Length]
0x1400730c7  mov     rdx, qword ptr [rsp+0E8h+FileOffset]
0x1400730cf  mov     rcx, r13
0x1400730d2  call    _guard_dispatch_icall
0x1400730d7  test    al, al
0x1400730d9  jnz     short loc_1400730E6
0x1400730db  mov     r12d, 303h
0x1400730e1  jmp     loc_140072E9C
0x1400730e6  mov     rcx, [rsp+0E8h+StartOffset]
0x1400730eb  mov     qword ptr [rsp+0E8h+var_50], rcx
0x1400730f3  mov     dword ptr [rsp+0E8h+FileOffset], esi
0x1400730fa  mov     dword ptr [rsp+0E8h+arg_38], esi
0x140073101  lea     rax, [r14+20h]
0x140073105  mov     [rsp+0E8h+var_70], rax
0x14007310a  mov     ecx, [rax]
0x14007310c  cmp     ebx, ecx
0x14007310e  jbe     short loc_140073134
0x140073110  mov     [rsp+0E8h+var_98], r15b
0x140073115  mov     dword ptr [rsp+0E8h+FileOffset], ecx
0x14007311c  mov     ecx, [r14+28h]
0x140073120  mov     dword ptr [rsp+0E8h+arg_38], ecx
0x140073127  mov     [rax], ebx
0x140073129  and     dword ptr [r14+0A0h], 0FFBFF7FFh
0x140073134  mov     rcx, [rsp+0E8h+Irp]; Irp
0x14007313c  call    cs:__imp_IoSetTopLevelIrp
0x140073143  nop     dword ptr [rax+rax+00h]
0x140073148  nop
0x140073149  mov     rax, [rsp+0E8h+StartOffset]
0x14007314e  cmp     edi, [rax]
0x140073150  jbe     short loc_140073185
0x140073152  mov     qword ptr [rsp+0E8h+EndOffset], rsi
0x14007315a  mov     dword ptr [rsp+0E8h+EndOffset], edi
0x140073161  mov     dword ptr [rsp+0E8h+EndOffset+4], esi
0x140073168  mov     r9b, 1; Wait
0x14007316b  lea     r8, [rsp+0E8h+EndOffset]; EndOffset
0x140073173  mov     rdx, rax; StartOffset
0x140073176  mov     rcx, r13; FileObject
0x140073179  call    cs:__imp_CcZeroData
0x140073180  nop     dword ptr [rax+rax+00h]
0x140073185  mov     r9, [rsp+0E8h+Buffer]; Buffer
0x14007318d  mov     r8d, [rsp+0E8h+Length]; Length
0x140073195  mov     edx, edi; FileOffset
0x140073197  mov     rcx, r13; FileObject
0x14007319a  call    cs:__imp_CcFastCopyWrite
0x1400731a1  nop     dword ptr [rax+rax+00h]
0x1400731a6  jmp     short loc_1400731E5
0x1400731a8  xor     r15b, r15b
0x1400731ab  xor     esi, esi
0x1400731ad  mov     r12d, 345h
0x1400731b3  mov     r13, [rsp+0E8h+arg_0]
0x1400731bb  movzx   eax, [rsp+0E8h+var_96+4]
0x1400731c0  mov     [rsp+0E8h+var_96+2], al
0x1400731c4  mov     [rsp+0E8h+var_97], al
0x1400731c8  mov     edi, [rsp+0E8h+var_78]
0x1400731cc  mov     ebx, dword ptr [rsp+0E8h+var_80]
0x1400731d0  mov     rax, qword ptr [rsp+0E8h+var_50]
0x1400731d8  mov     [rsp+0E8h+StartOffset], rax
0x1400731dd  mov     r14, [rsp+0E8h+var_60]
0x1400731e5  xor     ecx, ecx; Irp
0x1400731e7  call    cs:__imp_IoSetTopLevelIrp
0x1400731ee  nop     dword ptr [rax+rax+00h]
0x1400731f3  test    r15b, r15b
0x1400731f6  jz      short loc_140073241
0x1400731f8  mov     rax, [rsp+0E8h+StartOffset]
0x1400731fd  cmp     ebx, [rax]
0x1400731ff  jbe     short loc_140073203
0x140073201  mov     [rax], ebx
0x140073203  mov     rdx, [rsp+0E8h+var_58]
0x14007320b  lock or dword ptr [rdx], 1000h
0x140073212  cmp     [rsp+0E8h+var_98], 0
0x140073217  jz      short loc_14007322B
  ... truncated ...
```
