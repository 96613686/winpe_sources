# RefsCopyWriteInternal

- ea: `0x1c01bdf74`
- end: `0x1c01be58f`
- name: `RefsCopyWriteInternal`
- size: `1563`
- prototype: `__int64 __usercall@<rax>(PFILE_OBJECT FileObject@<rcx>, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1c01bdf00`
- `0x1c01be930`

## callees

- `0x1c000440c`
- `0x1c0005768`
- `0x1c000f480`
- `0x1c0014110`
- `0x1c005c650`
- `0x1c0062928`
- `0x1c0068960`
- `0x1c006af80`
- `0x1c00921c8`
- `0x1c00a04e8`
- `0x1c00a0534`
- `0x1c00aae9c`
- `0x1c00ab0cc`
- `0x1c01bdf74`
- `0x1c01c1b80`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x1c01be2f9`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c01be2f9`
- `ntoskrnl!ExAcquireFastMutex` at `0x1c01be183`
- `ntoskrnl!ExAcquireFastMutex` at `0x1c01be27a`
- `ntoskrnl!ExAcquireFastMutex` at `0x1c01be38d`
- `ntoskrnl!ExAcquireFastMutex` at `0x1c01be183`
- `ntoskrnl!ExAcquireFastMutex` at `0x1c01be27a`
- `ntoskrnl!ExAcquireFastMutex` at `0x1c01be38d`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c01be256`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c01be2d6`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c01be329`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c01be41d`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c01be256`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c01be2d6`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c01be329`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c01be41d`
- `ntoskrnl!CcPrepareMdlWrite` at `0x1c01be490`
- `ntoskrnl!CcPrepareMdlWrite` at `0x1c01be490`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1c01be53c`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1c01be573`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1c01be53c`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1c01be573`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1c01bdffe`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1c01bdffe`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1c01be439`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1c01be4c4`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1c01be439`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1c01be4c4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c01be0ee`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c01be0ee`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c01be311`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c01be311`
- `ntoskrnl!CcCopyWrite` at `0x1c01be46c`
- `ntoskrnl!CcCopyWrite` at `0x1c01be46c`
- `ntoskrnl!CcCanIWrite` at `0x1c01be03f`
- `ntoskrnl!CcCanIWrite` at `0x1c01be03f`
- `ntoskrnl!CcCopyWriteWontFlush` at `0x1c01be061`
- `ntoskrnl!CcCopyWriteWontFlush` at `0x1c01be061`

## pseudocode

```c
char __fastcall RefsCopyWriteInternal(
        PFILE_OBJECT FileObject,
        union _LARGE_INTEGER *a2,
        BOOLEAN a3,
        int a4,
        void *a5,
        PMDL *a6,
        struct _IO_STATUS_BLOCK *a7)
{
  char v10; // r13
  char *FsContext; // rbx
  union _LARGE_INTEGER *v13; // r12
  PIO_STATUS_BLOCK v14; // rcx
  __int64 v15; // r8
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  char v19; // al
  __int64 v20; // rdx
  __int64 v21; // r8
  BOOLEAN v22; // si
  volatile signed __int32 *v23; // rsi
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 HighestPendingFileSize; // r9
  __int64 v27; // rax
  union _LARGE_INTEGER v28; // r8
  __int64 v29; // r8
  __int64 v30; // rcx
  __int64 v31; // rcx
  ULONG LowPart; // r8d
  char v33; // [rsp+30h] [rbp-1D8h] BYREF
  char v34; // [rsp+31h] [rbp-1D7h]
  char v35; // [rsp+32h] [rbp-1D6h]
  BOOLEAN Wait; // [rsp+33h] [rbp-1D5h]
  char v37; // [rsp+34h] [rbp-1D4h]
  BOOLEAN v38; // [rsp+38h] [rbp-1D0h]
  _BYTE *v39; // [rsp+40h] [rbp-1C8h] BYREF
  int v40; // [rsp+48h] [rbp-1C0h]
  PVOID Buffer; // [rsp+50h] [rbp-1B8h]
  PIO_STATUS_BLOCK IoStatus; // [rsp+58h] [rbp-1B0h]
  PMDL *MdlChain; // [rsp+60h] [rbp-1A8h]
  char *v44; // [rsp+68h] [rbp-1A0h]
  PFILE_OBJECT v45; // [rsp+70h] [rbp-198h]
  union _LARGE_INTEGER *v46; // [rsp+78h] [rbp-190h]
  char *v47; // [rsp+88h] [rbp-180h]
  union _LARGE_INTEGER *v48; // [rsp+90h] [rbp-178h]
  union _LARGE_INTEGER *v49; // [rsp+98h] [rbp-170h]
  __int128 v50; // [rsp+B0h] [rbp-158h] BYREF
  __int64 v51; // [rsp+C0h] [rbp-148h]
  _BYTE v52[256]; // [rsp+D0h] [rbp-138h] BYREF

  v40 = a4;
  Wait = a3;
  v45 = FileObject;
  v46 = a2;
  v49 = a2;
  v38 = a3;
  Buffer = a5;
  MdlChain = a6;
  IoStatus = a7;
  v33 = 0;
  v10 = 0;
  v37 = 0;
  v35 = 0;
  if ( IoGetTopLevelIrp() )
    return 0;
  a2[1].QuadPart = (LONGLONG)a2;
  a2->QuadPart = (LONGLONG)a2;
  FsContext = (char *)FileObject->FsContext;
  v44 = FsContext;
  if ( (FileObject->Flags & 0x10) != 0 )
    return 0;
  if ( !CcCanIWrite(FileObject, a2[4].LowPart, a3, 0) )
    return 0;
  v13 = a2 + 2;
  if ( !CcCopyWriteWontFlush(FileObject, a2 + 2, a2[4].LowPart)
    || *(_DWORD *)(*((_QWORD *)FsContext + 16) + 468LL)
    || !*((_QWORD *)FsContext + 2)
    || FileObject->SectionObjectPointer != (PSECTION_OBJECT_POINTERS)(*((_QWORD *)FsContext + 30) + 8LL) )
  {
    return 0;
  }
  v14 = IoStatus;
  IoStatus->Status = 0;
  if ( Buffer )
    v14->Information = a2[4].LowPart;
  if ( !a2[4].LowPart )
    return 1;
  memset(v52, 0, sizeof(v52));
  v39 = v52;
  KeEnterCriticalRegion();
  LOBYTE(v15) = 1;
  LOBYTE(v16) = 1;
  RefsInitializeIrpContext(0, v16, v15, &v39);
  v17 = *(_QWORD *)(*((_QWORD *)FsContext + 15) + 88LL);
  *((_QWORD *)v39 + 8) = v17;
  LOBYTE(v18) = a3;
  if ( v13->QuadPart >= 0 )
    v19 = RefsAcquirePagingResourceShared(v17, FsContext, v18);
  else
    v19 = RefsAcquirePagingResourceExclusive(v17, FsContext, v18);
  v22 = v19;
  v34 = v19;
  if ( v19 )
  {
    if ( FileObject->PrivateCacheMap
      && FsContext[5]
      && (unsigned __int8)RefsIsFileOpen(*((_QWORD *)FsContext + 15), v20, v21) )
    {
      v48 = a2 + 2;
      a2[3].QuadPart = v13->QuadPart + a2[4].LowPart;
      ExAcquireFastMutex(*((PFAST_MUTEX *)FsContext + 6));
      v23 = (volatile signed __int32 *)(FsContext + 156);
      v47 = FsContext + 156;
      _InterlockedIncrement((volatile signed __int32 *)FsContext + 39);
      if ( v13->QuadPart >= 0 && a2[3].QuadPart <= *((_QWORD *)FsContext + 4) )
        goto LABEL_40;
      RefsGetIoAtEof((_DWORD)v39, (_DWORD)FsContext, v13->QuadPart, a2[4].LowPart, (__int64)&v33);
      if ( !v33 )
        goto LABEL_40;
      HighestPendingFileSize = RefsGetHighestPendingFileSize(v24, FsContext);
      if ( v13->QuadPart < 0 )
      {
        *((_DWORD *)v39 + 2) |= 0x20000u;
        v27 = RefsGetHighestPendingFileSize(v25, FsContext);
        v13->QuadPart = v27;
        a2[3].QuadPart = v27 + a2[4].LowPart;
      }
      if ( (*((_DWORD *)FsContext + 34) & 8) != 0
        || (v28 = a2[3], v28.QuadPart > *((_QWORD *)FsContext + 3))
        || (*(unsigned int *)(*((_QWORD *)FsContext + 16) + 456LL) + HighestPendingFileSize) >> *(_BYTE *)(*((_QWORD *)FsContext + 16) + 464LL) < (*(unsigned int *)(*((_QWORD *)FsContext + 16) + 456LL) + v28.QuadPart) >> *(_BYTE *)(*((_QWORD *)FsContext + 16) + 464LL) )
      {
        _InterlockedIncrement(v23);
        ExReleaseFastMutex(*((PFAST_MUTEX *)FsContext + 6));
      }
      else
      {
LABEL_40:
        _InterlockedIncrement(v23);
        ExReleaseFastMutex(*((PFAST_MUTEX *)FsContext + 6));
        if ( FsContext[5] != 2
          || (unsigned __int8)RefsFastIoCheckIfPossibleInternal(v39, FileObject, &a2[2], a2[4].LowPart, v40, 0) )
        {
          if ( !v33 )
            goto LABEL_54;
          v50 = *(_OWORD *)(FsContext + 24);
          v51 = *((_QWORD *)FsContext + 5);
          ExAcquireFastMutex(*((PFAST_MUTEX *)FsContext + 6));
          _InterlockedIncrement(v23);
          LOBYTE(v29) = 1;
          RefsInitiateFileSizeExtension(FsContext, a2, v29);
          *((_QWORD *)&v50 + 1) = RefsGetHighestPendingFileSize(v30, FsContext);
          RefsSetBothCacheSizes(v31, FileObject, &v50, FsContext);
          RefsFinishIoAtEof(v39, FsContext);
          v33 = 0;
          v10 = 1;
          v37 = 1;
          _InterlockedIncrement(v23);
          ExReleaseFastMutex(*((PFAST_MUTEX *)FsContext + 6));
          if ( !v35 )
          {
LABEL_54:
            IoSetTopLevelIrp((PIRP)4);
            LowPart = v49[4].LowPart;
            if ( Buffer )
            {
              v22 = CcCopyWrite(FileObject, v13, LowPart, Wait, Buffer);
              v34 = v22;
            }
            else
            {
              CcPrepareMdlWrite(FileObject, v13, LowPart, MdlChain, IoStatus);
              v22 = 1;
              v34 = 1;
            }
            IoSetTopLevelIrp(0);
            if ( v22 )
            {
              FileObject->Flags |= 0x1000u;
              FileObject->CurrentByteOffset = a2[3];
LABEL_29:
              if ( v10 || v33 )
              {
                ExAcquireFastMutex(*((PFAST_MUTEX *)FsContext + 6));
                _InterlockedIncrement((volatile signed __int32 *)FsContext + 39);
                if ( v10 )
                  RefsCompleteFileSizeExtension(
                    (_DWORD)v39,
                    (_DWORD)FileObject,
                    (_DWORD)FsContext,
                    (_DWORD)a2,
                    v34,
                    (__int64)&v33);
                if ( v33 )
                  RefsFinishIoAtEof(v39, FsContext);
                _InterlockedIncrement((volatile signed __int32 *)FsContext + 39);
                ExReleaseFastMutex(*((PFAST_MUTEX *)FsContext + 6));
                v22 = v34;
              }
              if ( *(_WORD *)FsContext != 2050 )
                FsContext = (char *)*((_QWORD *)FsContext + 15);
              ExReleaseResourceLite(*((PERESOURCE *)FsContext + 13));
              goto LABEL_39;
            }
          }
        }
      }
    }
    v22 = 0;
    v34 = 0;
    goto LABEL_29;
  }
LABEL_39:
  RefsCleanupIrpContext(v39, 0);
  KeLeaveCriticalRegion();
  return v22;
}

```

## disassembly

```asm
0x1c01bdf74  mov     [rsp+arg_18], rbx
0x1c01bdf79  push    rsi
0x1c01bdf7a  push    r12
0x1c01bdf7c  push    r13
0x1c01bdf7e  push    r14
0x1c01bdf80  push    r15
0x1c01bdf82  sub     rsp, 1E0h
0x1c01bdf89  mov     rax, cs:__security_cookie
0x1c01bdf90  xor     rax, rsp
0x1c01bdf93  mov     [rsp+208h+var_38], rax
0x1c01bdf9b  mov     [rsp+208h+var_1C0], r9d
0x1c01bdfa0  mov     sil, r8b
0x1c01bdfa3  mov     [rsp+208h+Wait], r8b
0x1c01bdfa8  mov     r14, rdx
0x1c01bdfab  mov     r15, rcx
0x1c01bdfae  mov     [rsp+208h+var_198], rcx
0x1c01bdfb3  mov     [rsp+208h+var_190], rdx
0x1c01bdfb8  mov     [rsp+208h+var_170], rdx
0x1c01bdfc0  mov     [rsp+208h+var_1D0], r8b
0x1c01bdfc5  mov     rax, [rsp+208h+arg_20]
0x1c01bdfcd  mov     [rsp+208h+var_1B8], rax
0x1c01bdfd2  mov     rax, [rsp+208h+arg_28]
0x1c01bdfda  mov     [rsp+208h+MdlChain], rax
0x1c01bdfdf  mov     rax, [rsp+208h+arg_30]
0x1c01bdfe7  mov     [rsp+208h+IoStatus], rax
0x1c01bdfec  mov     [rsp+208h+var_1D8], 0
0x1c01bdff1  xor     r13b, r13b
0x1c01bdff4  mov     [rsp+208h+var_1D4], r13b
0x1c01bdff9  mov     [rsp+208h+var_1D6], r13b
0x1c01bdffe  call    cs:__imp_IoGetTopLevelIrp
0x1c01be005  nop     dword ptr [rax+rax+00h]
0x1c01be00a  test    rax, rax
0x1c01be00d  jz      short loc_1C01BE016
0x1c01be00f  xor     al, al
0x1c01be011  jmp     loc_1C01BE4F7
0x1c01be016  mov     [r14+8], r14
0x1c01be01a  mov     [r14], r14
0x1c01be01d  mov     rbx, [r15+18h]
0x1c01be021  mov     [rsp+208h+var_1A0], rbx
0x1c01be026  mov     eax, [r15+50h]
0x1c01be02a  test    al, 10h
0x1c01be02c  jnz     loc_1C01BE4F1
0x1c01be032  xor     r9d, r9d; Retrying
0x1c01be035  mov     r8b, sil; Wait
0x1c01be038  mov     edx, [r14+20h]; BytesToWrite
0x1c01be03c  mov     rcx, r15; FileObject
0x1c01be03f  call    cs:__imp_CcCanIWrite
0x1c01be046  nop     dword ptr [rax+rax+00h]
0x1c01be04b  test    al, al
0x1c01be04d  jz      loc_1C01BE4F1
0x1c01be053  lea     r12, [r14+10h]
0x1c01be057  mov     r8d, [r14+20h]; Length
0x1c01be05b  mov     rdx, r12; FileOffset
0x1c01be05e  mov     rcx, r15; FileObject
0x1c01be061  call    cs:__imp_CcCopyWriteWontFlush
0x1c01be068  nop     dword ptr [rax+rax+00h]
0x1c01be06d  test    al, al
0x1c01be06f  jz      loc_1C01BE4F1
0x1c01be075  mov     rax, [rbx+80h]
0x1c01be07c  cmp     dword ptr [rax+1D4h], 0
0x1c01be083  jnz     loc_1C01BE4F1
0x1c01be089  cmp     qword ptr [rbx+10h], 0
0x1c01be08e  jz      loc_1C01BE4F1
0x1c01be094  mov     rax, [rbx+0F0h]
0x1c01be09b  add     rax, 8
0x1c01be09f  cmp     [r15+28h], rax
0x1c01be0a3  jnz     loc_1C01BE4F1
0x1c01be0a9  mov     rcx, [rsp+208h+IoStatus]
0x1c01be0ae  and     dword ptr [rcx], 0
0x1c01be0b1  cmp     [rsp+208h+var_1B8], 0
0x1c01be0b7  jz      short loc_1C01BE0C1
0x1c01be0b9  mov     eax, [r14+20h]
0x1c01be0bd  mov     [rcx+8], rax
0x1c01be0c1  cmp     dword ptr [r14+20h], 0
0x1c01be0c6  jz      loc_1C01BE4EC
0x1c01be0cc  xor     edx, edx; Val
0x1c01be0ce  mov     r8d, 100h; Size
0x1c01be0d4  lea     rcx, [rsp+208h+var_138]; void *
0x1c01be0dc  call    memset
0x1c01be0e1  lea     rax, [rsp+208h+var_138]
0x1c01be0e9  mov     [rsp+208h+var_1C8], rax
0x1c01be0ee  call    cs:__imp_KeEnterCriticalRegion
0x1c01be0f5  nop     dword ptr [rax+rax+00h]
0x1c01be0fa  lea     r9, [rsp+208h+var_1C8]
0x1c01be0ff  mov     r8b, 1
0x1c01be102  mov     dl, r8b
0x1c01be105  xor     ecx, ecx
0x1c01be107  call    RefsInitializeIrpContext
0x1c01be10c  mov     rax, [rbx+78h]
0x1c01be110  mov     rcx, [rax+58h]
0x1c01be114  mov     rax, [rsp+208h+var_1C8]
0x1c01be119  mov     [rax+40h], rcx
0x1c01be11d  mov     r8b, sil
0x1c01be120  mov     rdx, rbx
0x1c01be123  cmp     qword ptr [r12], 0
0x1c01be128  jge     short loc_1C01BE131
0x1c01be12a  call    RefsAcquirePagingResourceExclusive
0x1c01be12f  jmp     short loc_1C01BE136
0x1c01be131  call    RefsAcquirePagingResourceShared
0x1c01be136  mov     sil, al
0x1c01be139  mov     [rsp+208h+var_1D7], al
0x1c01be13d  test    al, al
0x1c01be13f  jz      loc_1C01BE305
0x1c01be145  cmp     qword ptr [r15+30h], 0
0x1c01be14a  jz      loc_1C01BE262
0x1c01be150  cmp     [rbx+5], r13b
0x1c01be154  jz      loc_1C01BE262
0x1c01be15a  mov     rcx, [rbx+78h]
0x1c01be15e  call    RefsIsFileOpen
0x1c01be163  test    al, al
0x1c01be165  jz      loc_1C01BE262
0x1c01be16b  mov     [rsp+208h+var_178], r12
0x1c01be173  mov     eax, [r14+20h]
0x1c01be177  add     rax, [r12]
0x1c01be17b  mov     [r14+18h], rax
0x1c01be17f  mov     rcx, [rbx+30h]; FastMutex
0x1c01be183  call    cs:__imp_ExAcquireFastMutex
0x1c01be18a  nop     dword ptr [rax+rax+00h]
0x1c01be18f  lea     rsi, [rbx+9Ch]
0x1c01be196  mov     [rsp+208h+var_180], rsi
0x1c01be19e  lock inc dword ptr [rsi]
0x1c01be1a1  mov     r8, [r12]
0x1c01be1a5  test    r8, r8
0x1c01be1a8  js      short loc_1C01BE1B8
0x1c01be1aa  mov     rax, [rbx+20h]
0x1c01be1ae  cmp     [r14+18h], rax
0x1c01be1b2  jle     loc_1C01BE322
0x1c01be1b8  lea     rax, [rsp+208h+var_1D8]
0x1c01be1bd  mov     [rsp+208h+Buffer], rax
0x1c01be1c2  mov     r9d, [r14+20h]
0x1c01be1c6  mov     rdx, rbx
0x1c01be1c9  mov     rcx, [rsp+208h+var_1C8]
0x1c01be1ce  call    RefsGetIoAtEof
0x1c01be1d3  cmp     [rsp+208h+var_1D8], r13b
0x1c01be1d8  jz      loc_1C01BE322
0x1c01be1de  mov     rdx, rbx
0x1c01be1e1  call    RefsGetHighestPendingFileSize
0x1c01be1e6  mov     r9, rax
0x1c01be1e9  cmp     qword ptr [r12], 0
0x1c01be1ee  jge     short loc_1C01BE211
0x1c01be1f0  mov     rax, [rsp+208h+var_1C8]
0x1c01be1f5  bts     dword ptr [rax+8], 11h
0x1c01be1fa  mov     rdx, rbx
0x1c01be1fd  call    RefsGetHighestPendingFileSize
0x1c01be202  mov     [r12], rax
0x1c01be206  mov     ecx, [r14+20h]
0x1c01be20a  add     rcx, rax
0x1c01be20d  mov     [r14+18h], rcx
0x1c01be211  mov     eax, [rbx+88h]
0x1c01be217  test    al, 8
0x1c01be219  jnz     short loc_1C01BE24F
0x1c01be21b  mov     r8, [r14+18h]
0x1c01be21f  cmp     r8, [rbx+18h]
0x1c01be223  jg      short loc_1C01BE24F
0x1c01be225  mov     rax, [rbx+80h]
0x1c01be22c  mov     edx, [rax+1C8h]
0x1c01be232  movsx   ecx, byte ptr [rax+1D0h]
0x1c01be239  add     r8, rdx
0x1c01be23c  sar     r8, cl
0x1c01be23f  lea     rax, [rdx+r9]
0x1c01be243  sar     rax, cl
0x1c01be246  cmp     rax, r8
0x1c01be249  jge     loc_1C01BE322
0x1c01be24f  lock inc dword ptr [rsi]
0x1c01be252  mov     rcx, [rbx+30h]; FastMutex
0x1c01be256  call    cs:__imp_ExReleaseFastMutex
0x1c01be25d  nop     dword ptr [rax+rax+00h]
0x1c01be262  xor     sil, sil
0x1c01be265  mov     [rsp+208h+var_1D7], sil
0x1c01be26a  test    r13b, r13b
0x1c01be26d  jnz     short loc_1C01BE276
0x1c01be26f  cmp     [rsp+208h+var_1D8], r13b
0x1c01be274  jz      short loc_1C01BE2E7
0x1c01be276  mov     rcx, [rbx+30h]; FastMutex
0x1c01be27a  call    cs:__imp_ExAcquireFastMutex
0x1c01be281  nop     dword ptr [rax+rax+00h]
0x1c01be286  lock inc dword ptr [rbx+9Ch]
0x1c01be28d  test    r13b, r13b
0x1c01be290  jz      short loc_1C01BE2B7
0x1c01be292  lea     rax, [rsp+208h+var_1D8]
0x1c01be297  mov     [rsp+208h+var_1E0], rax
0x1c01be29c  mov     al, [rsp+208h+var_1D7]
0x1c01be2a0  mov     byte ptr [rsp+208h+Buffer], al
0x1c01be2a4  mov     r9, r14
0x1c01be2a7  mov     r8, rbx
0x1c01be2aa  mov     rdx, r15
0x1c01be2ad  mov     rcx, [rsp+208h+var_1C8]
0x1c01be2b2  call    RefsCompleteFileSizeExtension
0x1c01be2b7  cmp     [rsp+208h+var_1D8], 0
0x1c01be2bc  jz      short loc_1C01BE2CB
0x1c01be2be  mov     rdx, rbx
0x1c01be2c1  mov     rcx, [rsp+208h+var_1C8]
0x1c01be2c6  call    RefsFinishIoAtEof
0x1c01be2cb  lock inc dword ptr [rbx+9Ch]
0x1c01be2d2  mov     rcx, [rbx+30h]; FastMutex
0x1c01be2d6  call    cs:__imp_ExReleaseFastMutex
0x1c01be2dd  nop     dword ptr [rax+rax+00h]
0x1c01be2e2  mov     sil, [rsp+208h+var_1D7]
0x1c01be2e7  mov     eax, 802h
0x1c01be2ec  cmp     ax, [rbx]
0x1c01be2ef  jz      short loc_1C01BE2F5
0x1c01be2f1  mov     rbx, [rbx+78h]
0x1c01be2f5  mov     rcx, [rbx+68h]; Resource
0x1c01be2f9  call    cs:__imp_ExReleaseResourceLite
0x1c01be300  nop     dword ptr [rax+rax+00h]
0x1c01be305  xor     edx, edx
0x1c01be307  mov     rcx, [rsp+208h+var_1C8]
0x1c01be30c  call    RefsCleanupIrpContext
0x1c01be311  call    cs:__imp_KeLeaveCriticalRegion
0x1c01be318  nop     dword ptr [rax+rax+00h]
0x1c01be31d  jmp     loc_1C01BE4F4
0x1c01be322  lock inc dword ptr [rsi]
0x1c01be325  mov     rcx, [rbx+30h]; FastMutex
0x1c01be329  call    cs:__imp_ExReleaseFastMutex
0x1c01be330  nop     dword ptr [rax+rax+00h]
0x1c01be335  cmp     byte ptr [rbx+5], 2
0x1c01be339  jnz     short loc_1C01BE364
0x1c01be33b  mov     byte ptr [rsp+208h+var_1E0], r13b
0x1c01be340  mov     eax, [rsp+208h+var_1C0]
0x1c01be344  mov     dword ptr [rsp+208h+Buffer], eax
0x1c01be348  mov     r9d, [r14+20h]
0x1c01be34c  mov     r8, r12
0x1c01be34f  mov     rdx, r15
0x1c01be352  mov     rcx, [rsp+208h+var_1C8]
0x1c01be357  call    RefsFastIoCheckIfPossibleInternal
0x1c01be35c  test    al, al
0x1c01be35e  jz      loc_1C01BE262
0x1c01be364  cmp     [rsp+208h+var_1D8], r13b
0x1c01be369  jz      loc_1C01BE434
0x1c01be36f  movups  xmm0, xmmword ptr [rbx+18h]
0x1c01be373  movups  [rsp+208h+var_158], xmm0
0x1c01be37b  movsd   xmm1, qword ptr [rbx+28h]
0x1c01be380  movsd   [rsp+208h+var_148], xmm1
0x1c01be389  mov     rcx, [rbx+30h]; FastMutex
0x1c01be38d  call    cs:__imp_ExAcquireFastMutex
0x1c01be394  nop     dword ptr [rax+rax+00h]
0x1c01be399  lock inc dword ptr [rsi]
0x1c01be39c  mov     r8b, 1
0x1c01be39f  mov     rdx, r14
0x1c01be3a2  mov     rcx, rbx
0x1c01be3a5  call    RefsInitiateFileSizeExtension
0x1c01be3aa  nop
0x1c01be3ab  mov     rdx, rbx
0x1c01be3ae  call    RefsGetHighestPendingFileSize
0x1c01be3b3  mov     qword ptr [rsp+208h+var_158+8], rax
0x1c01be3bb  mov     r9, rbx
0x1c01be3be  lea     r8, [rsp+208h+var_158]
0x1c01be3c6  mov     rdx, r15
0x1c01be3c9  call    RefsSetBothCacheSizes
0x1c01be3ce  jmp     short loc_1C01BE3FC
0x1c01be3d0  mov     [rsp+208h+var_1D6], 1
0x1c01be3d5  mov     rbx, [rsp+208h+var_1A0]
0x1c01be3da  mov     r15, [rsp+208h+var_198]
0x1c01be3df  mov     r14, [rsp+208h+var_190]
0x1c01be3e4  mov     al, [rsp+208h+var_1D0]
0x1c01be3e8  mov     [rsp+208h+Wait], al
0x1c01be3ec  mov     rsi, [rsp+208h+var_180]
0x1c01be3f4  mov     r12, [rsp+208h+var_178]
0x1c01be3fc  mov     rdx, rbx
0x1c01be3ff  mov     rcx, [rsp+208h+var_1C8]
0x1c01be404  call    RefsFinishIoAtEof
0x1c01be409  mov     [rsp+208h+var_1D8], 0
0x1c01be40e  mov     r13b, 1
0x1c01be411  mov     [rsp+208h+var_1D4], r13b
0x1c01be416  lock inc dword ptr [rsi]
0x1c01be419  mov     rcx, [rbx+30h]; FastMutex
0x1c01be41d  call    cs:__imp_ExReleaseFastMutex
0x1c01be424  nop     dword ptr [rax+rax+00h]
0x1c01be429  cmp     [rsp+208h+var_1D6], 0
0x1c01be42e  jnz     loc_1C01BE262
0x1c01be434  mov     ecx, 4; Irp
0x1c01be439  call    cs:__imp_IoSetTopLevelIrp
0x1c01be440  nop     dword ptr [rax+rax+00h]
0x1c01be445  nop
0x1c01be446  mov     rax, [rsp+208h+var_170]
0x1c01be44e  mov     r8d, [rax+20h]; Length
0x1c01be452  mov     rax, [rsp+208h+var_1B8]
0x1c01be457  mov     rdx, r12; FileOffset
0x1c01be45a  mov     rcx, r15; FileObject
0x1c01be45d  test    rax, rax
0x1c01be460  jz      short loc_1C01BE481
0x1c01be462  mov     [rsp+208h+Buffer], rax; Buffer
0x1c01be467  mov     r9b, [rsp+208h+Wait]; Wait
0x1c01be46c  call    cs:__imp_CcCopyWrite
0x1c01be473  nop     dword ptr [rax+rax+00h]
0x1c01be478  mov     sil, al
0x1c01be47b  mov     [rsp+208h+var_1D7], al
0x1c01be47f  jmp     short loc_1C01BE4A4
0x1c01be481  mov     rax, [rsp+208h+IoStatus]
0x1c01be486  mov     [rsp+208h+Buffer], rax; IoStatus
0x1c01be48b  mov     r9, [rsp+208h+MdlChain]; MdlChain
0x1c01be490  call    cs:__imp_CcPrepareMdlWrite
0x1c01be497  nop     dword ptr [rax+rax+00h]
0x1c01be49c  mov     sil, 1
0x1c01be49f  mov     [rsp+208h+var_1D7], sil
0x1c01be4a4  jmp     short loc_1C01BE4C2
0x1c01be4a6  xor     sil, sil
0x1c01be4a9  mov     [rsp+208h+var_1D7], sil
0x1c01be4ae  mov     rbx, [rsp+208h+var_1A0]
0x1c01be4b3  mov     r13b, [rsp+208h+var_1D4]
  ... truncated ...
```
