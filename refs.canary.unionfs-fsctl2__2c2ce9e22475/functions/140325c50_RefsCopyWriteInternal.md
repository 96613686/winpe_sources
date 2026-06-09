# RefsCopyWriteInternal

- ea: `0x140325c50`
- end: `0x140326457`
- name: `RefsCopyWriteInternal`
- size: `2055`
- prototype: `__int64 __usercall@<rax>(struct _FILE_OBJECT *@<rcx>, PLARGE_INTEGER FileOffset@<rdx>, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `31`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1402e98f0`
- `0x14033e9e0`

## callees

- `0x140008fd0`
- `0x140009af0`
- `0x140009c20`
- `0x140039b20`
- `0x14003d440`
- `0x14003d4cc`
- `0x140069750`
- `0x140081670`
- `0x14008dbd0`
- `0x14008e060`
- `0x14008e360`
- `0x1400913a0`
- `0x1400994e0`
- `0x140099960`
- `0x14009bb80`
- `0x14009ccb0`
- `0x1400abcb0`
- `0x1400ae1ec`
- `0x1400af96c`
- `0x1400b87a0`
- `0x1400ca788`
- `0x1400e6e2c`
- `0x1401047ec`
- `0x1401e9ce0`
- `0x1402870ec`
- `0x1402fec40`
- `0x1403000b0`
- `0x14031468c`
- `0x140325c50`
- `0x14032a910`
- `0x1403390c4`

## import_xrefs

- `ntoskrnl!IoGetTopLevelIrp` at `0x140325cbd`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140325cbd`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140325faa`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140326292`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140325faa`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140326292`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140325dba`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140325dba`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403263a3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403263a3`
- `ntoskrnl!CcCopyWrite` at `0x140326071`
- `ntoskrnl!CcCopyWrite` at `0x140326071`
- `ntoskrnl!CcMdlWriteAbort` at `0x140326174`
- `ntoskrnl!CcMdlWriteAbort` at `0x140326174`
- `ntoskrnl!CcCanIWrite` at `0x140325d05`
- `ntoskrnl!CcCanIWrite` at `0x140325d05`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1403262ed`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1403262ed`
- `ntoskrnl!CcCopyWriteWontFlush` at `0x140325d23`
- `ntoskrnl!CcCopyWriteWontFlush` at `0x140325d23`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1403262fc`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1403262fc`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14034103e`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14034103e`
- `ntoskrnl!CcPrepareMdlWrite` at `0x14032609e`
- `ntoskrnl!CcPrepareMdlWrite` at `0x14032609e`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140326367`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140326367`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140326373`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140326373`

## string_xrefs

- `0x14032614f`: `write.c`
- `0x14032642a`: `write.c`

## pseudocode

```c
char __fastcall RefsCopyWriteInternal(
        struct _FILE_OBJECT *a1,
        PLARGE_INTEGER FileOffset,
        BOOLEAN a3,
        unsigned int a4,
        void *a5,
        PMDL *a6,
        struct _IO_STATUS_BLOCK *a7)
{
  char *FsContext; // rdi
  bool v12; // si
  __int64 v13; // rcx
  char v14; // r14
  __int64 v15; // rcx
  _FCB **v16; // rdx
  int v17; // eax
  unsigned int v18; // r8d
  bool v19; // bl
  unsigned int v20; // r8d
  DWORD LowPart; // r8d
  struct _CCB *v22; // rbx
  unsigned __int8 v23; // r9
  struct _FAST_MUTEX *v24; // rbx
  int v25; // [rsp+30h] [rbp-3D8h] BYREF
  __int16 v26; // [rsp+34h] [rbp-3D4h]
  unsigned int v27; // [rsp+38h] [rbp-3D0h]
  unsigned int v28; // [rsp+3Ch] [rbp-3CCh]
  PIO_STATUS_BLOCK IoStatus; // [rsp+40h] [rbp-3C8h]
  struct _CCB *FsContext2; // [rsp+48h] [rbp-3C0h]
  PFILE_OBJECT FileObject; // [rsp+50h] [rbp-3B8h]
  PVOID Buffer; // [rsp+58h] [rbp-3B0h]
  PMDL *MdlChain; // [rsp+60h] [rbp-3A8h]
  PMDL *v34; // [rsp+68h] [rbp-3A0h]
  struct _CCB *v35; // [rsp+70h] [rbp-398h]
  char *v36; // [rsp+78h] [rbp-390h]
  PLARGE_INTEGER v37; // [rsp+80h] [rbp-388h]
  struct _FCB **v38; // [rsp+90h] [rbp-378h]
  _BYTE v39[4]; // [rsp+A0h] [rbp-368h] BYREF
  __int64 v40; // [rsp+E0h] [rbp-328h]

  v28 = a4;
  IoStatus = a7;
  FileObject = a1;
  v37 = FileOffset;
  Buffer = a5;
  MdlChain = a6;
  v34 = a6;
  if ( IoGetTopLevelIrp() )
    return 0;
  FsContext = (char *)a1->FsContext;
  FsContext2 = (struct _CCB *)a1->FsContext2;
  v25 = 0;
  if ( (a1->Flags & 0x10) != 0
    || !CcCanIWrite(a1, FileOffset[2].LowPart, a3, 0)
    || !CcCopyWriteWontFlush(a1, 0, FileOffset[2].LowPart)
    || *(_DWORD *)(*((_QWORD *)FsContext + 18) + 556LL)
    || !*((_QWORD *)FsContext + 2)
    || (*((_DWORD *)FsContext + 38) & 0x10) != 0
    && (*(_QWORD *)(*((_QWORD *)FsContext + 17) + 8LL) & 0x40000100LL) == 0x40000000
    || a1->SectionObjectPointer != (PSECTION_OBJECT_POINTERS)(*((_QWORD *)FsContext + 31) + 8LL) )
  {
    return 0;
  }
  a7->Status = 0;
  if ( a5 )
    a7->Information = FileOffset[2].LowPart;
  if ( FileOffset[2].LowPart )
  {
    v36 = FsContext;
    KeEnterCriticalRegion();
    RefsInitializeLocalIrpContext(0, (struct _LARGE_IRP_CONTEXT *)v39);
    v40 = *((_QWORD *)FsContext + 18);
    if ( a1->PrivateCacheMap == (PVOID)1 )
    {
      if ( (unsigned __int8)RefsAcquirePagingResourceExclusive(v13, FsContext, a3) )
      {
        v14 = 0x80;
        if ( !RefsSetupCacheMapDuringFastIo((struct _IRP_CONTEXT *)v39, a1, (struct DataSCB *)FsContext) )
        {
          v12 = 0;
          goto LABEL_61;
        }
        if ( (*((_DWORD *)FsContext + 38) & 0x10) == 0 || !_FCB::HasPurgeableEAs(*((_FCB **)FsContext + 17)) )
          RefsConvertPagingResourceExclusiveToShared(v39, FsContext);
LABEL_31:
        v14 |= 0x80u;
        LOBYTE(v25) = v14;
        if ( a1->PrivateCacheMap )
        {
          if ( FsContext[5] )
          {
            v38 = (struct _FCB **)(FsContext + 136);
            if ( RefsIsFileOpen(*((const struct _FCB **)FsContext + 17)) )
            {
              v17 = *((_DWORD *)FsContext + 38);
              if ( (v17 & 0x80u) == 0 && ((v17 & 0x10) == 0 || !_FCB::HasPurgeableEAs(*v16)) )
              {
                if ( (int)RefsSetWriteRangeFromEof(v39, FsContext, FileOffset, &v25) < 0
                  || (v35 = FsContext2, FsContext[5] == 2)
                  && !RefsFastIoCheckIfPossibleInternal(
                        a1,
                        (struct _SCB *)FsContext,
                        FileOffset->QuadPart,
                        FileOffset[2].LowPart,
                        v28,
                        0) )
                {
                  v14 = v25;
                }
                else
                {
                  LOBYTE(v26) = 0;
                  IoSetTopLevelIrp((PIRP)4);
                  v14 = v25;
                  v18 = (v25 & 1) != 0;
                  v27 = v18;
                  v19 = (v25 & 2) != 0;
                  if ( (v25 & 2) != 0 )
                  {
                    v18 |= 2u;
                    v27 = v18;
                  }
                  RefsPostUsnChange((struct _IRP_CONTEXT *)v39, (struct _FCB *)FsContext, v18, 0);
                  if ( v19 )
                  {
                    RefsInitiateFileExtensionForWrite((struct _IRP_CONTEXT *)v39, (__int64)&v25);
                    v14 = v25;
                  }
                  if ( *((__int16 *)FsContext + 128) < 0
                    && !RefsReserveClusters(
                          (struct _IRP_CONTEXT *)v39,
                          (struct _SCB *)FsContext,
                          FileOffset->QuadPart,
                          FileOffset[2].LowPart) )
                  {
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                    {
                      WPP_SF_d(
                        WPP_GLOBAL_Control->AttachedDevice,
                        57,
                        WPP_07f6fe4c040b3e18d4debf0891266445_Traceguids,
                        3221225599LL);
                    }
                    if ( (_BYTE)RefsStatusDebugEnabled )
                      RefsStatusDebug(-1073741697, (struct _IRP_CONTEXT *)v39, "write.c", 0xDDAu);
                    RefsRaiseStatusInternal((struct _IRP_CONTEXT *)v39, -1073741697, v20);
                    __debugbreak();
                    JUMPOUT(0x140326457LL);
                  }
                  LowPart = FileOffset[2].LowPart;
                  if ( Buffer )
                  {
                    v12 = CcCopyWrite(a1, FileOffset, LowPart, a3, Buffer) != 0;
                    HIBYTE(v26) = v12;
                  }
                  else
                  {
                    CcPrepareMdlWrite(a1, FileOffset, LowPart, MdlChain, IoStatus);
                    v12 = 1;
                    v26 = 257;
                  }
                  if ( v12 )
                  {
                    RefsPostWriteProcessing((struct _IRP_CONTEXT *)v39, a1, (__int64)FileOffset, (__int64)&v25);
                    v14 = v25;
                  }
                  v22 = FsContext2;
                  IoSetTopLevelIrp(0);
                  if ( v12 )
                  {
                    RefsUpdateFileTimestampsForModification(a1, *v38, v22, v23);
                    a1->CurrentByteOffset = FileOffset[1];
LABEL_61:
                    if ( v14 < 0 )
                      RefsReleasePagingResource(v39);
                    goto LABEL_63;
                  }
                }
              }
            }
          }
        }
        v12 = 0;
        if ( (v14 & 4) != 0 || (v25 & 0x400) != 0 )
        {
          v24 = (struct _FAST_MUTEX *)*((_QWORD *)FsContext + 6);
          KeEnterGuardedRegion();
          ExAcquireFastMutexUnsafe(v24);
          _InterlockedIncrement((volatile signed __int32 *)FsContext + 43);
          if ( (v14 & 4) != 0 )
          {
            RefsCompleteFileSizeExtension((struct _IRP_CONTEXT *)v39, (struct DataSCB *)FsContext, (__int64)&v25);
            v14 = v25 & 0xFB;
          }
          if ( (v25 & 0x400) != 0 )
            RefsFinishIoAtEof((struct _IRP_CONTEXT *)v39, (struct _SCB *)FsContext);
          ++*((_DWORD *)FsContext + 43);
          ExReleaseFastMutexUnsafe(*((PFAST_MUTEX *)FsContext + 6));
          KeLeaveGuardedRegion();
        }
        goto LABEL_61;
      }
LABEL_25:
      v12 = 0;
LABEL_63:
      RefsCleanupIrpContext((struct _IRP_CONTEXT *)v39, 0);
      KeLeaveCriticalRegion();
      return v12;
    }
    if ( (*((_DWORD *)FsContext + 38) & 0x10) != 0
      && (*(_QWORD *)(*((_QWORD *)FsContext + 17) + 8LL) & 0x40000100LL) == 0x40000000 )
    {
      if ( !(unsigned __int8)RefsAcquirePagingResourceExclusive(0x40000000, FsContext, a3) )
        goto LABEL_25;
    }
    else
    {
      if ( !(unsigned __int8)RefsAcquirePagingResourceShared(v39, FsContext, a3) )
        goto LABEL_25;
      if ( (*((_DWORD *)FsContext + 38) & 0x10) != 0 && _FCB::HasPurgeableEAs(*((_FCB **)FsContext + 17)) )
      {
        RefsReleasePagingResource(v39);
        if ( !(unsigned __int8)RefsAcquirePagingResourceExclusive(v15, FsContext, a3) )
          goto LABEL_25;
      }
    }
    v14 = v25;
    goto LABEL_31;
  }
  return 1;
}

```

## disassembly

```asm
0x140325c50  push    rbx
0x140325c52  push    rsi
0x140325c53  push    rdi
0x140325c54  push    r12
0x140325c56  push    r13
0x140325c58  push    r14
0x140325c5a  push    r15
0x140325c5c  sub     rsp, 3D0h
0x140325c63  mov     rax, cs:__security_cookie
0x140325c6a  xor     rax, rsp
0x140325c6d  mov     [rsp+408h+var_48], rax
0x140325c75  mov     [rsp+408h+var_3CC], r9d
0x140325c7a  movzx   esi, r8b
0x140325c7e  mov     r12, rdx
0x140325c81  mov     r15, rcx
0x140325c84  mov     rbx, [rsp+408h+arg_30]
0x140325c8c  mov     [rsp+408h+IoStatus], rbx
0x140325c91  mov     [rsp+408h+FileObject], rcx
0x140325c96  mov     [rsp+408h+var_388], rdx
0x140325c9e  mov     r14, [rsp+408h+arg_20]
0x140325ca6  mov     [rsp+408h+var_3B0], r14
0x140325cab  mov     rax, [rsp+408h+arg_28]
0x140325cb3  mov     [rsp+408h+MdlChain], rax
0x140325cb8  mov     [rsp+408h+var_3A0], rax
0x140325cbd  call    cs:__imp_IoGetTopLevelIrp
0x140325cc4  nop     dword ptr [rax+rax+00h]
0x140325cc9  test    rax, rax
0x140325ccc  jz      short loc_140325CD5
0x140325cce  xor     al, al
0x140325cd0  jmp     loc_1403263B8
0x140325cd5  mov     rdi, [r15+18h]
0x140325cd9  mov     rax, [r15+20h]
0x140325cdd  mov     [rsp+408h+var_3C0], rax
0x140325ce2  xor     r13d, r13d
0x140325ce5  mov     dword ptr [rsp+408h+var_3D8], r13d
0x140325cea  mov     eax, [r15+50h]
0x140325cee  test    al, 10h
0x140325cf0  jnz     loc_1403263B1
0x140325cf6  xor     r9d, r9d; Retrying
0x140325cf9  movzx   r8d, sil; Wait
0x140325cfd  mov     edx, [r12+10h]; BytesToWrite
0x140325d02  mov     rcx, r15; FileObject
0x140325d05  call    cs:__imp_CcCanIWrite
0x140325d0c  nop     dword ptr [rax+rax+00h]
0x140325d11  test    al, al
0x140325d13  jz      loc_1403263B1
0x140325d19  mov     r8d, [r12+10h]; Length
0x140325d1e  xor     edx, edx; FileOffset
0x140325d20  mov     rcx, r15; FileObject
0x140325d23  call    cs:__imp_CcCopyWriteWontFlush
0x140325d2a  nop     dword ptr [rax+rax+00h]
0x140325d2f  test    al, al
0x140325d31  jz      loc_1403263B1
0x140325d37  mov     rax, [rdi+90h]
0x140325d3e  cmp     [rax+22Ch], r13d
0x140325d45  jnz     loc_1403263B1
0x140325d4b  cmp     [rdi+10h], r13
0x140325d4f  jz      loc_1403263B1
0x140325d55  mov     eax, [rdi+98h]
0x140325d5b  test    al, 10h
0x140325d5d  jz      short loc_140325D7D
0x140325d5f  mov     rax, [rdi+88h]
0x140325d66  mov     rcx, [rax+8]
0x140325d6a  and     ecx, 40000100h
0x140325d70  cmp     rcx, 40000000h
0x140325d77  jz      loc_1403263B1
0x140325d7d  mov     rax, [rdi+0F8h]
0x140325d84  add     rax, 8
0x140325d88  cmp     [r15+28h], rax
0x140325d8c  jnz     loc_1403263B1
0x140325d92  mov     [rbx], r13d
0x140325d95  test    r14, r14
0x140325d98  jz      short loc_140325DA3
0x140325d9a  mov     eax, [r12+10h]
0x140325d9f  mov     [rbx+8], rax
0x140325da3  cmp     [r12+10h], r13d
0x140325da8  jnz     short loc_140325DB2
0x140325daa  mov     sil, 1
0x140325dad  jmp     loc_1403263B4
0x140325db2  mov     r13, rdi
0x140325db5  mov     [rsp+408h+var_390], rdi
0x140325dba  call    cs:__imp_KeEnterCriticalRegion
0x140325dc1  nop     dword ptr [rax+rax+00h]
0x140325dc6  lea     rdx, [rsp+408h+var_368]; struct _LARGE_IRP_CONTEXT *
0x140325dce  xor     ecx, ecx; struct _IRP *
0x140325dd0  call    ?RefsInitializeLocalIrpContext@@YAJPEAU_IRP@@PEAU_LARGE_IRP_CONTEXT@@@Z; RefsInitializeLocalIrpContext(_IRP *,_LARGE_IRP_CONTEXT *)
0x140325dd5  mov     rax, [rdi+90h]
0x140325ddc  mov     [rsp+408h+var_328], rax
0x140325de4  cmp     qword ptr [r15+30h], 1
0x140325de9  jnz     short loc_140325E54
0x140325deb  movzx   r8d, sil
0x140325def  mov     rdx, rdi
0x140325df2  call    ?RefsAcquirePagingResourceExclusive@@YAEPEAU_IRP_CONTEXT@@UPFCBOrSCB@@E@Z; RefsAcquirePagingResourceExclusive(_IRP_CONTEXT *,PFCBOrSCB,uchar)
0x140325df7  test    al, al
0x140325df9  jz      loc_140325E88
0x140325dff  mov     r14b, 80h
0x140325e02  mov     r8, rdi; struct DataSCB *
0x140325e05  mov     rdx, r15; struct _FILE_OBJECT *
0x140325e08  lea     rcx, [rsp+408h+var_368]; struct _IRP_CONTEXT *
0x140325e10  call    ?RefsSetupCacheMapDuringFastIo@@YAEPEAU_IRP_CONTEXT@@PEAU_FILE_OBJECT@@AEAUDataSCB@@@Z; RefsSetupCacheMapDuringFastIo(_IRP_CONTEXT *,_FILE_OBJECT *,DataSCB &)
0x140325e15  test    al, al
0x140325e17  jnz     short loc_140325E21
0x140325e19  xor     sil, sil
0x140325e1c  jmp     loc_14032637F
0x140325e21  mov     eax, [rdi+98h]
0x140325e27  test    al, 10h
0x140325e29  jz      short loc_140325E3F
0x140325e2b  mov     rcx, [rdi+88h]; this
0x140325e32  call    ?HasPurgeableEAs@_FCB@@QEAA_NXZ; _FCB::HasPurgeableEAs(void)
0x140325e37  test    al, al
0x140325e39  jnz     loc_140325EE8
0x140325e3f  mov     rdx, rdi
0x140325e42  lea     rcx, [rsp+408h+var_368]
0x140325e4a  call    ?RefsConvertPagingResourceExclusiveToShared@@YAXPEAU_IRP_CONTEXT@@UPFCBOrSCB@@@Z; RefsConvertPagingResourceExclusiveToShared(_IRP_CONTEXT *,PFCBOrSCB)
0x140325e4f  jmp     loc_140325EE8
0x140325e54  mov     eax, [rdi+98h]
0x140325e5a  test    al, 10h
0x140325e5c  jz      short loc_140325E90
0x140325e5e  mov     rax, [rdi+88h]
0x140325e65  mov     rcx, [rax+8]
0x140325e69  and     ecx, 40000100h
0x140325e6f  cmp     rcx, 40000000h
0x140325e76  jnz     short loc_140325E90
0x140325e78  movzx   r8d, sil
0x140325e7c  mov     rdx, rdi
0x140325e7f  call    ?RefsAcquirePagingResourceExclusive@@YAEPEAU_IRP_CONTEXT@@UPFCBOrSCB@@E@Z; RefsAcquirePagingResourceExclusive(_IRP_CONTEXT *,PFCBOrSCB,uchar)
0x140325e84  test    al, al
0x140325e86  jnz     short loc_140325EE2
0x140325e88  xor     sil, sil
0x140325e8b  jmp     loc_140326394
0x140325e90  movzx   r8d, sil
0x140325e94  mov     rdx, rdi
0x140325e97  lea     rcx, [rsp+408h+var_368]
0x140325e9f  call    ?RefsAcquirePagingResourceShared@@YAEPEAU_IRP_CONTEXT@@UPFCBOrSCB@@E@Z; RefsAcquirePagingResourceShared(_IRP_CONTEXT *,PFCBOrSCB,uchar)
0x140325ea4  test    al, al
0x140325ea6  jz      short loc_140325E88
0x140325ea8  mov     eax, [rdi+98h]
0x140325eae  test    al, 10h
0x140325eb0  jz      short loc_140325EE2
0x140325eb2  mov     rcx, [rdi+88h]; this
0x140325eb9  call    ?HasPurgeableEAs@_FCB@@QEAA_NXZ; _FCB::HasPurgeableEAs(void)
0x140325ebe  test    al, al
0x140325ec0  jz      short loc_140325EE2
0x140325ec2  mov     rdx, rdi
0x140325ec5  lea     rcx, [rsp+408h+var_368]
0x140325ecd  call    ?RefsReleasePagingResource@@YAXPEAU_IRP_CONTEXT@@UPFCBOrSCB@@@Z; RefsReleasePagingResource(_IRP_CONTEXT *,PFCBOrSCB)
0x140325ed2  movzx   r8d, sil
0x140325ed6  mov     rdx, rdi
0x140325ed9  call    ?RefsAcquirePagingResourceExclusive@@YAEPEAU_IRP_CONTEXT@@UPFCBOrSCB@@E@Z; RefsAcquirePagingResourceExclusive(_IRP_CONTEXT *,PFCBOrSCB,uchar)
0x140325ede  test    al, al
0x140325ee0  jz      short loc_140325E88
0x140325ee2  movzx   r14d, byte ptr [rsp+408h+var_3D8]
0x140325ee8  or      r14b, 80h
0x140325eec  mov     byte ptr [rsp+408h+var_3D8], r14b
0x140325ef1  cmp     qword ptr [r15+30h], 0
0x140325ef6  jz      loc_1403262CD
0x140325efc  cmp     byte ptr [rdi+5], 0
0x140325f00  jz      loc_1403262CD
0x140325f06  lea     rdx, [rdi+88h]
0x140325f0d  mov     [rsp+408h+var_378], rdx
0x140325f15  mov     rcx, [rdx]; struct _FCB *
0x140325f18  call    ?RefsIsFileOpen@@YAEPEBU_FCB@@@Z; RefsIsFileOpen(_FCB const *)
0x140325f1d  test    al, al
0x140325f1f  jz      loc_1403262CD
0x140325f25  mov     eax, [rdi+98h]
0x140325f2b  test    al, al
0x140325f2d  js      loc_1403262CD
0x140325f33  test    al, 10h
0x140325f35  jz      short loc_140325F47
0x140325f37  mov     rcx, [rdx]; this
0x140325f3a  call    ?HasPurgeableEAs@_FCB@@QEAA_NXZ; _FCB::HasPurgeableEAs(void)
0x140325f3f  test    al, al
0x140325f41  jnz     loc_1403262CD
0x140325f47  lea     r9, [rsp+408h+var_3D8]
0x140325f4c  mov     r8, r12
0x140325f4f  mov     rdx, rdi
0x140325f52  lea     rcx, [rsp+408h+var_368]
0x140325f5a  call    RefsSetWriteRangeFromEof
0x140325f5f  test    eax, eax
0x140325f61  js      loc_1403262C7
0x140325f67  mov     rax, [rsp+408h+var_3C0]
0x140325f6c  mov     [rsp+408h+var_398], rax
0x140325f71  cmp     byte ptr [rdi+5], 2
0x140325f75  jnz     short loc_140325FA0
0x140325f77  mov     [rsp+408h+var_3E0], 0; unsigned __int8
0x140325f7c  mov     eax, [rsp+408h+var_3CC]
0x140325f80  mov     dword ptr [rsp+408h+Buffer], eax; unsigned int
0x140325f84  mov     r9d, [r12+10h]; unsigned int
0x140325f89  mov     r8, [r12]; __int64
0x140325f8d  mov     rdx, rdi; struct _SCB *
0x140325f90  mov     rcx, r15; FileObject
0x140325f93  call    ?RefsFastIoCheckIfPossibleInternal@@YAEPEAU_FILE_OBJECT@@AEAU_SCB@@_JKKE@Z; RefsFastIoCheckIfPossibleInternal(_FILE_OBJECT *,_SCB &,__int64,ulong,ulong,uchar)
0x140325f98  test    al, al
0x140325f9a  jz      loc_1403262C7
0x140325fa0  mov     byte ptr [rsp+408h+var_3D8+4], 0
0x140325fa5  mov     ecx, 4; Irp
0x140325faa  call    cs:__imp_IoSetTopLevelIrp
0x140325fb1  nop     dword ptr [rax+rax+00h]
0x140325fb6  nop
0x140325fb7  xor     r8d, r8d
0x140325fba  mov     [rsp+408h+var_3D0], r8d
0x140325fbf  movzx   r14d, byte ptr [rsp+408h+var_3D8]
0x140325fc5  test    r14b, 1
0x140325fc9  mov     eax, 1
0x140325fce  cmovnz  r8d, eax
0x140325fd2  mov     [rsp+408h+var_3D0], r8d
0x140325fd7  movzx   ebx, r14b
0x140325fdb  shr     bl, 1
0x140325fdd  and     bl, al
0x140325fdf  jz      short loc_140325FEA
0x140325fe1  or      r8d, 2; unsigned int
0x140325fe5  mov     [rsp+408h+var_3D0], r8d
0x140325fea  xor     r9d, r9d; struct _FILE_NAME *
0x140325fed  mov     rdx, rdi; struct _FCB *
0x140325ff0  lea     rcx, [rsp+408h+var_368]; struct _IRP_CONTEXT *
0x140325ff8  call    ?RefsPostUsnChange@@YAXPEAU_IRP_CONTEXT@@PEAXKPEBU_FILE_NAME@@@Z; RefsPostUsnChange(_IRP_CONTEXT *,void *,ulong,_FILE_NAME const *)
0x140325ffd  test    bl, bl
0x140325fff  jz      short loc_140326028
0x140326001  lea     rax, [rsp+408h+var_3D8]
0x140326006  mov     [rsp+408h+Buffer], rax; __int64
0x14032600b  mov     r9, r12
0x14032600e  mov     r8, [r15+20h]
0x140326012  mov     rdx, rdi
0x140326015  lea     rcx, [rsp+408h+var_368]; struct _IRP_CONTEXT *
0x14032601d  call    RefsInitiateFileExtensionForWrite
0x140326022  movzx   r14d, byte ptr [rsp+408h+var_3D8]
0x140326028  cmp     word ptr [rdi+100h], 0
0x140326030  jge     short loc_140326053
0x140326032  mov     r9d, [r12+10h]; unsigned int
0x140326037  mov     r8, [r12]; __int64
0x14032603b  mov     rdx, rdi; struct _SCB *
0x14032603e  lea     rcx, [rsp+408h+var_368]; struct _IRP_CONTEXT *
0x140326046  call    ?RefsReserveClusters@@YAEPEAU_IRP_CONTEXT@@PEAU_SCB@@_JK@Z; RefsReserveClusters(_IRP_CONTEXT *,_SCB *,__int64,ulong)
0x14032604b  test    al, al
0x14032604d  jz      loc_1403263DC
0x140326053  mov     r8d, [r12+10h]; Length
0x140326058  mov     rax, [rsp+408h+var_3B0]
0x14032605d  mov     rdx, r12; FileOffset
0x140326060  mov     rcx, r15; FileObject
0x140326063  test    rax, rax
0x140326066  jz      short loc_14032608F
0x140326068  mov     [rsp+408h+Buffer], rax; Buffer
0x14032606d  movzx   r9d, sil; Wait
0x140326071  call    cs:__imp_CcCopyWrite
0x140326078  nop     dword ptr [rax+rax+00h]
0x14032607d  test    al, al
0x14032607f  setnz   sil
0x140326083  mov     byte ptr [rsp+408h+var_3D8+5], sil
0x140326088  mov     rbx, [rsp+408h+IoStatus]
0x14032608d  jmp     short loc_1403260B7
0x14032608f  mov     rbx, [rsp+408h+IoStatus]
0x140326094  mov     [rsp+408h+Buffer], rbx; IoStatus
0x140326099  mov     r9, [rsp+408h+MdlChain]; MdlChain
0x14032609e  call    cs:__imp_CcPrepareMdlWrite
0x1403260a5  nop     dword ptr [rax+rax+00h]
0x1403260aa  mov     sil, 1
0x1403260ad  mov     byte ptr [rsp+408h+var_3D8+5], sil
0x1403260b2  mov     byte ptr [rsp+408h+var_3D8+4], sil
0x1403260b7  test    sil, sil
0x1403260ba  jz      short loc_1403260E7
0x1403260bc  lea     rax, [rsp+408h+var_3D8]
0x1403260c1  mov     qword ptr [rsp+408h+var_3E0], rax
0x1403260c6  mov     [rsp+408h+Buffer], r12
0x1403260cb  mov     r9, rdi
0x1403260ce  mov     r8, rbx
0x1403260d1  mov     rdx, r15
0x1403260d4  lea     rcx, [rsp+408h+var_368]
0x1403260dc  call    RefsPostWriteProcessing
0x1403260e1  movzx   r14d, byte ptr [rsp+408h+var_3D8]
0x1403260e7  mov     rbx, [rsp+408h+var_3C0]
0x1403260ec  jmp     loc_140326290
0x1403260f1  mov     ebx, eax
0x1403260f3  lea     rax, WPP_GLOBAL_Control
0x1403260fa  mov     r10, cs:WPP_GLOBAL_Control
0x140326101  cmp     r10, rax
0x140326104  jz      short loc_14032613C
0x140326106  test    dword ptr [r10+2Ch], 100h
0x14032610e  jz      short loc_14032613C
0x140326110  test    ebx, ebx
0x140326112  js      short loc_14032611D
0x140326114  cmp     byte ptr [r10+29h], 5
0x140326119  jnb     short loc_140326124
0x14032611b  jmp     short loc_14032613C
0x14032611d  cmp     byte ptr [r10+29h], 4
0x140326122  jb      short loc_14032613C
0x140326124  mov     r9d, ebx
0x140326127  mov     edx, 3Ah ; ':'
0x14032612c  lea     r8, WPP_07f6fe4c040b3e18d4debf0891266445_Traceguids
0x140326133  mov     rcx, [r10+18h]
0x140326137  call    WPP_SF_d
0x14032613c  movzx   eax, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x140326143  test    al, al
0x140326145  jz      short loc_14032615D
0x140326147  mov     ecx, ebx; Status
0x140326149  mov     r9d, 0DFBh; unsigned int
0x14032614f  lea     r8, aWriteC; "write.c"
0x140326156  xor     edx, edx; struct _IRP_CONTEXT *
0x140326158  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x14032615d  mov     r15, [rsp+408h+FileObject]
0x140326162  cmp     byte ptr [rsp+408h+var_3D8+4], 0
  ... truncated ...
```
