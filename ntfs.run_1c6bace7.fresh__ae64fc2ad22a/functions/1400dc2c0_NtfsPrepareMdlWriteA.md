# NtfsPrepareMdlWriteA

- ea: `0x1400dc2c0`
- end: `0x1400dcc1b`
- name: `NtfsPrepareMdlWriteA`
- size: `2395`
- prototype: `__int64 __usercall@<rax>(PFILE_OBJECT FileObject@<rcx>, PLARGE_INTEGER FileOffset@<rdx>, ULONG Length@<r8d>, PMDL *MdlChain, PIO_STATUS_BLOCK)`
- caller_count: `0`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140007ea0`
- `0x140008740`
- `0x140009af0`
- `0x140012b50`
- `0x140017030`
- `0x14001cd10`
- `0x140021590`
- `0x1400235d0`
- `0x1400290d0`
- `0x140059250`
- `0x1400596c0`
- `0x1400dc2c0`
- `0x140181b60`
- `0x1401e9e20`
- `0x14022eed4`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1400dc561`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400dc561`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400dcbe3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400dcbe3`
- `ntoskrnl!CcPrepareMdlWrite` at `0x1400dc396`
- `ntoskrnl!CcPrepareMdlWrite` at `0x1400dc864`
- `ntoskrnl!CcPrepareMdlWrite` at `0x1400dc396`
- `ntoskrnl!CcPrepareMdlWrite` at `0x1400dc864`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1400dc754`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1400dc79b`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1400dc93e`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1400dc754`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1400dc79b`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1400dc93e`
- `ntoskrnl!CcCopyWriteWontFlush` at `0x1400dc457`
- `ntoskrnl!CcCopyWriteWontFlush` at `0x1400dc457`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x1400dc718`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x1400dcbbc`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x1400dc718`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x1400dcbbc`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x1400dc650`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x1400dc7cd`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x1400dc995`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x1400dc650`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x1400dc7cd`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x1400dc995`
- `ntoskrnl!CcCanIWrite` at `0x1400dc43a`
- `ntoskrnl!CcCanIWrite` at `0x1400dc43a`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1402c1f8b`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1402c1fb5`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1402c1f8b`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1402c1fb5`

## pseudocode

```c
char __fastcall NtfsPrepareMdlWriteA(
        PFILE_OBJECT FileObject,
        PLARGE_INTEGER FileOffset,
        ULONG Length,
        ULONG a4,
        PMDL *MdlChain,
        PIO_STATUS_BLOCK IoStatus)
{
  ULONG_PTR v6; // rbx
  __int64 TopLevelContext; // rax
  char v11; // r15
  union _LARGE_INTEGER *FsContext; // rsi
  union _LARGE_INTEGER v13; // rax
  union _LARGE_INTEGER v14; // rcx
  __int64 v15; // rax
  union _LARGE_INTEGER v16; // rdi
  LONGLONG QuadPart; // r15
  __int64 v18; // r8
  __int64 v19; // rcx
  __int64 v20; // r8
  __int64 v21; // r9
  int v22; // edx
  __int64 v23; // rcx
  ULONG_PTR v24; // r12
  __int64 v25; // rbx
  char v26; // r15
  __int64 *v27; // r12
  ULONG v28; // r15d
  signed __int64 v29; // rdx
  signed __int64 v30; // r10
  union _LARGE_INTEGER *v31; // r8
  union _LARGE_INTEGER *v32; // rdi
  signed __int64 v33; // r8
  signed __int64 v34; // r10
  __int64 v35; // rdx
  DWORD LowPart; // r8d
  signed __int64 v37; // r10
  signed __int64 v38; // r9
  union _LARGE_INTEGER *v39; // rdx
  signed __int64 v40; // r9
  char v41; // [rsp+30h] [rbp-348h] BYREF
  char v42; // [rsp+31h] [rbp-347h]
  char v43; // [rsp+32h] [rbp-346h]
  union _LARGE_INTEGER *v44; // [rsp+38h] [rbp-340h]
  union _LARGE_INTEGER FileOffseta; // [rsp+40h] [rbp-338h] BYREF
  ULONG Lengtha; // [rsp+48h] [rbp-330h]
  _BYTE *v47; // [rsp+50h] [rbp-328h] BYREF
  PLARGE_INTEGER v48; // [rsp+58h] [rbp-320h]
  union _LARGE_INTEGER *v49; // [rsp+60h] [rbp-318h]
  ULONG v50; // [rsp+68h] [rbp-310h]
  __int64 v51; // [rsp+70h] [rbp-308h]
  PIO_STATUS_BLOCK v52; // [rsp+78h] [rbp-300h]
  LONGLONG v53; // [rsp+80h] [rbp-2F8h]
  PVOID FsContext2; // [rsp+88h] [rbp-2F0h]
  __int64 *v55; // [rsp+90h] [rbp-2E8h]
  PMDL *v56; // [rsp+98h] [rbp-2E0h]
  union _LARGE_INTEGER *v57; // [rsp+A0h] [rbp-2D8h]
  union _LARGE_INTEGER *v58; // [rsp+A8h] [rbp-2D0h]
  PFILE_OBJECT v59; // [rsp+B0h] [rbp-2C8h]
  PIO_STATUS_BLOCK v60; // [rsp+B8h] [rbp-2C0h]
  union _LARGE_INTEGER *v61; // [rsp+C0h] [rbp-2B8h]
  PVOID v62; // [rsp+C8h] [rbp-2B0h]
  ULONG_PTR v63; // [rsp+D0h] [rbp-2A8h]
  PSECTION_OBJECT_POINTERS *p_SectionObjectPointer; // [rsp+D8h] [rbp-2A0h]
  char v65[16]; // [rsp+E0h] [rbp-298h] BYREF
  __int64 v66; // [rsp+F0h] [rbp-288h]
  _BYTE v67[560]; // [rsp+100h] [rbp-278h] BYREF

  v50 = a4;
  v6 = Length;
  Lengtha = Length;
  v48 = FileOffset;
  v52 = IoStatus;
  v59 = FileObject;
  v56 = MdlChain;
  v60 = IoStatus;
  v41 = 0;
  TopLevelContext = NtfsGetTopLevelContextEx(&v41);
  if ( TopLevelContext )
  {
    if ( !v41 || (*(_DWORD *)(*(_QWORD *)(TopLevelContext + 32) + 12LL) & 0x4000000) == 0 )
      return 0;
    CcPrepareMdlWrite(FileObject, FileOffset, v6, MdlChain, IoStatus);
    v11 = 1;
    v42 = 1;
    return v11;
  }
  FsContext = (union _LARGE_INTEGER *)FileObject->FsContext;
  FsContext2 = FileObject->FsContext2;
  v62 = FsContext2;
  if ( !CcCanIWrite(FileObject, v6, 1u, 0) )
    return 0;
  if ( !CcCopyWriteWontFlush(FileObject, FileOffset, v6) )
    return 0;
  v57 = FsContext;
  if ( !FsContext[2].QuadPart )
    return 0;
  v13 = FsContext[66];
  if ( v13.QuadPart )
  {
    if ( (*(_DWORD *)(*(_QWORD *)(v13.QuadPart + 64) + 4LL) & 1) != 0 )
      return 0;
  }
  v49 = FsContext + 25;
  if ( (FsContext[25].LowPart & 0x10) != 0 )
  {
    v14 = FsContext[23];
    v15 = *(_QWORD *)(v14.QuadPart + 328);
    if ( (!v15 || !*(_QWORD *)(v15 + 24)) && (*(_DWORD *)(v14.QuadPart + 4) & 0x20020100) == 0x20000000 )
      return 0;
  }
  v44 = FsContext + 36;
  p_SectionObjectPointer = &FileObject->SectionObjectPointer;
  if ( FileObject->SectionObjectPointer != (PSECTION_OBJECT_POINTERS)(FsContext[36].QuadPart + 16) )
    return 0;
  v11 = 0;
  FileOffseta.QuadPart = 0;
  v66 = 0;
  v41 = 0;
  IoStatus->Status = 0;
  if ( (_DWORD)v6 )
  {
    v58 = FsContext + 25;
    v61 = FsContext + 36;
    v16.QuadPart = 0;
    v53 = 0;
    memset(v67, 0, 0x228u);
    v47 = v67;
    KeEnterCriticalRegion();
    memset(v67, 0, 0x228u);
    NtfsInitializeIrpContextInternal(0, 1, 1, (__int64 *)&v47);
    v55 = (__int64 *)&FsContext[23];
    NtfsSetIrpContextVcb(v47, *(_QWORD *)(FsContext[23].QuadPart + 96));
    QuadPart = FileOffset->QuadPart;
    FileOffseta = *FileOffset;
    LOBYTE(v18) = 1;
    v43 = NtfsCheckCompressAndAcquirePagingResource(v19, FsContext, v18);
    v22 = *(_DWORD *)(*v55 + 4);
    if ( (FsContext[25].LowPart & 0x10) != 0 )
    {
      v20 = *v55;
      v23 = *(_QWORD *)(*v55 + 328);
      if ( (!v23 || !*(_QWORD *)(v23 + 24))
        && (v22 & 0x20100) == 0
        && ((v22 & 0x20000000) != 0 || (v22 & 0x10000000) == 0 && (unsigned __int8)NtfsGetPurgeKernelEAState(*v55)) )
      {
        goto LABEL_46;
      }
    }
    v24 = v6;
    v63 = v6;
    v25 = QuadPart + v6;
    v51 = v25;
    if ( v48->QuadPart >= 0 )
    {
      v26 = 0;
      if ( v25 <= FsContext[5].QuadPart )
        goto LABEL_27;
    }
    while ( 1 )
    {
      FsRtlAcquireHeaderMutex(&FsContext[15], &FsContext[20]);
      v26 = 1;
LABEL_27:
      LOBYTE(v20) = v26;
      NtfsGetScbFileSizes(FsContext, v65, v20);
      v20 = v48->QuadPart;
      if ( v48->QuadPart >= 0 && v25 <= v66 )
        break;
      if ( v26 )
      {
        NtfsGetIoAtEof((_DWORD)v47, (_DWORD)FsContext, v20, v24, 1, (__int64)&v41);
        if ( v41 )
        {
          if ( v48->QuadPart < 0 )
            FileOffseta = FsContext[4];
          v25 = v24 + FileOffseta.QuadPart;
          v51 = v24 + FileOffseta.QuadPart;
          v16 = FsContext[4];
          v53 = v16.QuadPart;
          if ( (__int64)(v24 + FileOffseta.QuadPart) > v16.QuadPart )
          {
            if ( v25 > FsContext[3].QuadPart )
              v25 = 0x7FFFFFFFFFFFFFFFLL;
            v51 = v25;
          }
        }
        break;
      }
    }
    if ( v26 )
      FsRtlReleaseHeaderMutex(&FsContext[15], &FsContext[20]);
    if ( !FileObject->PrivateCacheMap
      || !BYTE5(FsContext->QuadPart)
      || v25 > FsContext[3].QuadPart
      || (v27 = (__int64 *)&FsContext[5], v48 = FsContext + 5, FileOffseta.QuadPart > FsContext[5].QuadPart) )
    {
LABEL_46:
      v11 = 0;
      if ( v41 )
      {
        FsRtlAcquireHeaderMutex(&FsContext[15], &FsContext[20]);
        if ( (v49->LowPart & 0x20000) == 0 || FsContext[4].QuadPart >= v16.QuadPart )
          goto LABEL_93;
        v29 = FsContext[58].QuadPart;
        if ( v16.QuadPart < v29 )
          v29 = v16.QuadPart;
        if ( v29 <= FsContext[5].QuadPart )
          goto LABEL_93;
        if ( (v49->LowPart & 0x20000) != 0 )
        {
          v30 = FsContext[58].QuadPart;
          if ( v30 < v29 )
          {
LABEL_91:
            FsContext[58].QuadPart = v29;
            goto LABEL_92;
          }
          if ( FsContext[5].QuadPart > v29 )
          {
            if ( *(_QWORD *)(v44->QuadPart + 16) && v29 != 0x7FFFFFFFFFFFFFFFLL )
            {
              v40 = (v29 + 4095) & 0xFFFFFFFFFFFFF000uLL;
              if ( v40 < v30 )
                FsContext[58].QuadPart = v40;
              goto LABEL_92;
            }
            goto LABEL_91;
          }
        }
LABEL_92:
        FsContext[5].QuadPart = v29;
LABEL_93:
        FsContext[4] = v16;
        v39 = FsContext + 20;
        goto LABEL_94;
      }
LABEL_95:
      if ( v43 )
        NtfsReleasePagingResourcePriv(v23, FsContext, v20, v21);
      NtfsCleanupIrpContext((__int64)v47, 0, v20);
      KeLeaveCriticalRegion();
      return v11;
    }
    IoSetTopLevelIrp((PIRP)4);
    v28 = Lengtha;
    if ( BYTE5(FsContext->QuadPart) == 2
      && !(unsigned __int8)NtfsFastIoCheckIfPossibleInternal((_DWORD)v47, FileObject, v50, 0) )
    {
      IoSetTopLevelIrp(0);
      goto LABEL_46;
    }
    CcPrepareMdlWrite(FileObject, &FileOffseta, v28, v56, v52);
    v11 = 1;
    v42 = 1;
    IoSetTopLevelIrp(0);
    NtfsUpdateFileTimestampsForModification(FileObject, *v55, FsContext2);
    v52->Information = v63;
    if ( !v41 )
      goto LABEL_95;
    FsRtlAcquireHeaderMutex(&FsContext[15], &FsContext[20]);
    FileObject->Flags |= 0x2000u;
    v31 = v49;
    if ( (v49->LowPart & 0x20000) != 0 && v25 <= *v27 )
    {
      v32 = v44;
      goto LABEL_70;
    }
    if ( (v49->LowPart & 0x20000) != 0 )
    {
      v33 = FsContext[58].QuadPart;
      if ( v33 < v25 )
      {
        v32 = v44;
LABEL_67:
        FsContext[58].QuadPart = v25;
LABEL_69:
        *v27 = v25;
        v31 = v49;
LABEL_70:
        if ( v25 <= FsContext[4].QuadPart )
        {
LABEL_85:
          *((union _LARGE_INTEGER *)(*p_SectionObjectPointer)->SharedCacheMap + 1) = FsContext[4];
          v39 = FsContext + 20;
LABEL_94:
          FsRtlReleaseHeaderMutex(&FsContext[15], v39);
          goto LABEL_95;
        }
        if ( (v31->LowPart & 0x20000) == 0 )
          goto LABEL_84;
        v35 = FsContext[58].QuadPart;
        if ( v25 < v35 )
          v35 = v25;
        if ( v35 <= *v27 )
        {
LABEL_84:
          FsContext[4].QuadPart = v25;
          goto LABEL_85;
        }
        LowPart = v31->LowPart;
        if ( (LowPart & 0x20000) != 0 )
        {
          v37 = FsContext[58].QuadPart;
          if ( v37 < v35 )
          {
LABEL_82:
            FsContext[58].QuadPart = v35;
            goto LABEL_83;
          }
          if ( *v27 > v35 )
          {
            if ( *(_QWORD *)(v32->QuadPart + 16) && v35 != 0x7FFFFFFFFFFFFFFFLL )
            {
              v38 = (v35 + 4095) & 0xFFFFFFFFFFFFF000uLL;
              if ( v38 < v37 )
                FsContext[58].QuadPart = v38;
              goto LABEL_83;
            }
            goto LABEL_82;
          }
        }
LABEL_83:
        FsContext[5].QuadPart = v35;
        goto LABEL_84;
      }
      if ( *v27 > v25 )
      {
        v32 = v44;
        if ( *(_QWORD *)(v44->QuadPart + 16) && v25 != 0x7FFFFFFFFFFFFFFFLL )
        {
          v34 = (v25 + 4095) & 0xFFFFFFFFFFFFF000uLL;
          if ( v34 < v33 )
            FsContext[58].QuadPart = v34;
          goto LABEL_69;
        }
        goto LABEL_67;
      }
    }
    v32 = v44;
    goto LABEL_69;
  }
  return v11;
}

```

## disassembly

```asm
0x1400dc2c0  push    rbx
0x1400dc2c2  push    rsi
0x1400dc2c3  push    rdi
0x1400dc2c4  push    r12
0x1400dc2c6  push    r13
0x1400dc2c8  push    r14
0x1400dc2ca  push    r15
0x1400dc2cc  sub     rsp, 340h
0x1400dc2d3  mov     rax, cs:__security_cookie
0x1400dc2da  xor     rax, rsp
0x1400dc2dd  mov     [rsp+378h+var_48], rax
0x1400dc2e5  mov     [rsp+378h+var_310], r9d
0x1400dc2ea  mov     ebx, r8d
0x1400dc2ed  mov     [rsp+378h+Length], ebx
0x1400dc2f1  mov     r12, rdx
0x1400dc2f4  mov     [rsp+378h+var_320], rdx
0x1400dc2f9  mov     r13, rcx
0x1400dc2fc  mov     rdi, [rsp+378h+arg_28]
0x1400dc304  mov     [rsp+378h+var_300], rdi
0x1400dc309  mov     [rsp+378h+var_2C8], rcx
0x1400dc311  mov     rsi, [rsp+378h+MdlChain]
0x1400dc319  mov     [rsp+378h+var_2E0], rsi
0x1400dc321  mov     [rsp+378h+var_2C0], rdi
0x1400dc329  xor     r14d, r14d
0x1400dc32c  mov     [rsp+378h+var_348], r14b
0x1400dc331  lea     rcx, [rsp+378h+var_348]
0x1400dc336  call    NtfsGetTopLevelContextEx
0x1400dc33b  mov     r8b, [rsp+378h+var_348]
0x1400dc340  test    rax, rax
0x1400dc343  jz      loc_1400DC417
0x1400dc349  test    r8b, r8b
0x1400dc34c  jz      short loc_1400DC35B
0x1400dc34e  mov     rcx, [rax+20h]
0x1400dc352  test    dword ptr [rcx+0Ch], 4000000h
0x1400dc359  jnz     short loc_1400DC362
0x1400dc35b  xor     al, al
0x1400dc35d  jmp     loc_1400DCBF7
0x1400dc362  test    rax, rax
0x1400dc365  jz      loc_1400DC417
0x1400dc36b  test    r8b, r8b
0x1400dc36e  jz      loc_1400DC417
0x1400dc374  mov     rax, [rax+20h]
0x1400dc378  test    dword ptr [rax+0Ch], 4000000h
0x1400dc37f  jz      loc_1400DC417
0x1400dc385  mov     [rsp+378h+IoStatus], rdi; IoStatus
0x1400dc38a  mov     r9, rsi; MdlChain
0x1400dc38d  mov     r8d, ebx; Length
0x1400dc390  mov     rdx, r12; FileOffset
0x1400dc393  mov     rcx, r13; FileObject
0x1400dc396  call    cs:__imp_CcPrepareMdlWrite
0x1400dc39d  nop     dword ptr [rax+rax+00h]
0x1400dc3a2  mov     r15b, 1
0x1400dc3a5  mov     [rsp+378h+var_347], r15b
0x1400dc3aa  jmp     loc_1400DCBF4
0x1400dc3af  mov     edx, eax
0x1400dc3b1  mov     cl, cs:NtfsStatusDebugFlags
0x1400dc3b7  test    cl, cl
0x1400dc3b9  jz      short loc_1400DC40A
0x1400dc3bb  test    eax, eax
0x1400dc3bd  jz      short loc_1400DC40A
0x1400dc3bf  cmp     eax, 126h
0x1400dc3c4  jz      short loc_1400DC40A
0x1400dc3c6  lea     ecx, [rax-12Ah]
0x1400dc3cc  cmp     ecx, 1
0x1400dc3cf  jbe     short loc_1400DC40A
0x1400dc3d1  cmp     eax, 0FFFFFFEDh
0x1400dc3d4  jnb     short loc_1400DC40A
0x1400dc3d6  cmp     eax, 0C00000D8h
0x1400dc3db  jz      short loc_1400DC40A
0x1400dc3dd  cmp     eax, 0C0000016h
0x1400dc3e2  jz      short loc_1400DC40A
0x1400dc3e4  cmp     eax, 0C0000011h
0x1400dc3e9  jz      short loc_1400DC40A
0x1400dc3eb  add     eax, 7FFFFFFBh
0x1400dc3f0  cmp     eax, 1
0x1400dc3f3  jbe     short loc_1400DC40A
0x1400dc3f5  cmp     edx, 103h
0x1400dc3fb  jz      short loc_1400DC40A
0x1400dc3fd  xor     ecx, ecx
0x1400dc3ff  mov     r8d, 3B05C5h
0x1400dc405  call    NtfsStatusTraceAndDebugInternal
0x1400dc40a  xor     r15b, r15b
0x1400dc40d  mov     [rsp+378h+var_347], r15b
0x1400dc412  jmp     loc_1400DCBF4
0x1400dc417  mov     rsi, [r13+18h]
0x1400dc41b  mov     rax, [r13+20h]
0x1400dc41f  mov     [rsp+378h+var_2F0], rax
0x1400dc427  mov     [rsp+378h+var_2B0], rax
0x1400dc42f  xor     r9d, r9d; Retrying
0x1400dc432  mov     r8b, 1; Wait
0x1400dc435  mov     edx, ebx; BytesToWrite
0x1400dc437  mov     rcx, r13; FileObject
0x1400dc43a  call    cs:__imp_CcCanIWrite
0x1400dc441  nop     dword ptr [rax+rax+00h]
0x1400dc446  test    al, al
0x1400dc448  jz      loc_1400DCBF1
0x1400dc44e  mov     r8d, ebx; Length
0x1400dc451  mov     rdx, r12; FileOffset
0x1400dc454  mov     rcx, r13; FileObject
0x1400dc457  call    cs:__imp_CcCopyWriteWontFlush
0x1400dc45e  nop     dword ptr [rax+rax+00h]
0x1400dc463  test    al, al
0x1400dc465  jz      loc_1400DCBF1
0x1400dc46b  mov     [rsp+378h+var_2D8], rsi
0x1400dc473  cmp     [rsi+10h], r14
0x1400dc477  jz      loc_1400DCBF1
0x1400dc47d  mov     rax, [rsi+210h]
0x1400dc484  test    rax, rax
0x1400dc487  jz      short loc_1400DC499
0x1400dc489  mov     rax, [rax+40h]
0x1400dc48d  mov     ecx, [rax+4]
0x1400dc490  test    cl, 1
0x1400dc493  jnz     loc_1400DCBF1
0x1400dc499  lea     rdx, [rsi+0C8h]
0x1400dc4a0  mov     [rsp+378h+var_318], rdx
0x1400dc4a5  mov     eax, [rdx]
0x1400dc4a7  test    al, 10h
0x1400dc4a9  jz      short loc_1400DC4D7
0x1400dc4ab  mov     rcx, [rsi+0B8h]
0x1400dc4b2  mov     rax, [rcx+148h]
0x1400dc4b9  test    rax, rax
0x1400dc4bc  jz      short loc_1400DC4C4
0x1400dc4be  cmp     [rax+18h], r14
0x1400dc4c2  jnz     short loc_1400DC4D7
0x1400dc4c4  mov     eax, [rcx+4]
0x1400dc4c7  and     eax, 20020100h
0x1400dc4cc  cmp     eax, 20000000h
0x1400dc4d1  jz      loc_1400DCBF1
0x1400dc4d7  lea     rcx, [rsi+120h]
0x1400dc4de  mov     [rsp+378h+var_340], rcx
0x1400dc4e3  lea     r8, [r13+28h]
0x1400dc4e7  mov     [rsp+378h+var_2A0], r8
0x1400dc4ef  mov     rax, [rcx]
0x1400dc4f2  add     rax, 10h
0x1400dc4f6  cmp     [r8], rax
0x1400dc4f9  jnz     loc_1400DCBF1
0x1400dc4ff  mov     r15b, r14b
0x1400dc502  mov     qword ptr [rsp+378h+FileOffset], r14
0x1400dc507  xor     eax, eax
0x1400dc509  mov     [rsp+378h+var_288], rax
0x1400dc511  mov     [rsp+378h+var_348], r14b
0x1400dc516  mov     [rdi], r14d
0x1400dc519  test    ebx, ebx
0x1400dc51b  jz      loc_1400DCBF4
0x1400dc521  mov     [rsp+378h+var_2D0], rdx
0x1400dc529  mov     [rsp+378h+var_2B8], rcx
0x1400dc531  mov     rdi, r14
0x1400dc534  mov     [rsp+378h+var_2F8], r14
0x1400dc53c  mov     r15d, 228h
0x1400dc542  mov     r8d, r15d; Size
0x1400dc545  xor     edx, edx; Val
0x1400dc547  lea     rcx, [rsp+378h+var_278]; void *
0x1400dc54f  call    memset
0x1400dc554  lea     rax, [rsp+378h+var_278]
0x1400dc55c  mov     [rsp+378h+var_328], rax
0x1400dc561  call    cs:__imp_KeEnterCriticalRegion
0x1400dc568  nop     dword ptr [rax+rax+00h]
0x1400dc56d  mov     r8d, r15d; Size
0x1400dc570  xor     edx, edx; Val
0x1400dc572  lea     rcx, [rsp+378h+var_278]; void *
0x1400dc57a  call    memset
0x1400dc57f  lea     r9, [rsp+378h+var_328]
0x1400dc584  mov     r8b, 1
0x1400dc587  mov     dl, r8b
0x1400dc58a  xor     ecx, ecx; Irp
0x1400dc58c  call    NtfsInitializeIrpContextInternal
0x1400dc591  lea     rax, [rsi+0B8h]
0x1400dc598  mov     [rsp+378h+var_2E8], rax
0x1400dc5a0  mov     rdx, [rax]
0x1400dc5a3  mov     rdx, [rdx+60h]
0x1400dc5a7  mov     rcx, [rsp+378h+var_328]
0x1400dc5ac  call    NtfsSetIrpContextVcb
0x1400dc5b1  mov     r15, [r12]
0x1400dc5b5  mov     qword ptr [rsp+378h+FileOffset], r15
0x1400dc5ba  mov     r8b, 1
0x1400dc5bd  mov     rdx, rsi
0x1400dc5c0  call    NtfsCheckCompressAndAcquirePagingResource
0x1400dc5c5  mov     [rsp+378h+var_346], al
0x1400dc5c9  mov     rax, [rsp+378h+var_2E8]
0x1400dc5d1  mov     rcx, [rax]
0x1400dc5d4  mov     edx, [rcx+4]
0x1400dc5d7  mov     ecx, [rsi+0C8h]
0x1400dc5dd  test    cl, 10h
0x1400dc5e0  jz      short loc_1400DC61F
0x1400dc5e2  mov     r8, [rax]
0x1400dc5e5  mov     rcx, [r8+148h]
0x1400dc5ec  test    rcx, rcx
0x1400dc5ef  jz      short loc_1400DC5F7
0x1400dc5f1  cmp     [rcx+18h], r14
0x1400dc5f5  jnz     short loc_1400DC61F
0x1400dc5f7  test    edx, 20100h
0x1400dc5fd  jnz     short loc_1400DC61F
0x1400dc5ff  bt      edx, 1Dh
0x1400dc603  jb      loc_1400DC7A7
0x1400dc609  bt      edx, 1Ch
0x1400dc60d  jb      short loc_1400DC61F
0x1400dc60f  mov     rcx, r8
0x1400dc612  call    NtfsGetPurgeKernelEAState
0x1400dc617  test    al, al
0x1400dc619  jnz     loc_1400DC7A7
0x1400dc61f  mov     r12, rbx
0x1400dc622  mov     [rsp+378h+var_2A8], rbx
0x1400dc62a  add     rbx, r15
0x1400dc62d  mov     [rsp+378h+var_308], rbx
0x1400dc632  mov     rax, [rsp+378h+var_320]
0x1400dc637  cmp     [rax], r14
0x1400dc63a  jl      short loc_1400DC645
0x1400dc63c  mov     r15b, r14b
0x1400dc63f  cmp     rbx, [rsi+28h]
0x1400dc643  jle     short loc_1400DC65F
0x1400dc645  lea     rdx, [rsi+0A0h]
0x1400dc64c  lea     rcx, [rsi+78h]
0x1400dc650  call    cs:__imp_FsRtlAcquireHeaderMutex
0x1400dc657  nop     dword ptr [rax+rax+00h]
0x1400dc65c  mov     r15b, 1
0x1400dc65f  mov     r8b, r15b
0x1400dc662  lea     rdx, [rsp+378h+var_298]
0x1400dc66a  mov     rcx, rsi
0x1400dc66d  call    NtfsGetScbFileSizes
0x1400dc672  mov     rax, [rsp+378h+var_320]
0x1400dc677  mov     r8, [rax]
0x1400dc67a  test    r8, r8
0x1400dc67d  js      short loc_1400DC689
0x1400dc67f  cmp     rbx, [rsp+378h+var_288]
0x1400dc687  jle     short loc_1400DC6FE
0x1400dc689  test    r15b, r15b
0x1400dc68c  jz      short loc_1400DC645
0x1400dc68e  lea     rax, [rsp+378h+var_348]
0x1400dc693  mov     [rsp+378h+var_350], rax
0x1400dc698  mov     byte ptr [rsp+378h+IoStatus], 1
0x1400dc69d  mov     r9, r12
0x1400dc6a0  mov     rdx, rsi
0x1400dc6a3  mov     rcx, [rsp+378h+var_328]
0x1400dc6a8  call    NtfsGetIoAtEof
0x1400dc6ad  cmp     [rsp+378h+var_348], r14b
0x1400dc6b2  jz      short loc_1400DC6FE
0x1400dc6b4  mov     rax, [rsp+378h+var_320]
0x1400dc6b9  cmp     [rax], r14
0x1400dc6bc  jge     short loc_1400DC6C7
0x1400dc6be  mov     rax, [rsi+20h]
0x1400dc6c2  mov     qword ptr [rsp+378h+FileOffset], rax
0x1400dc6c7  mov     rbx, qword ptr [rsp+378h+FileOffset]
0x1400dc6cc  add     rbx, r12
0x1400dc6cf  mov     [rsp+378h+var_308], rbx
0x1400dc6d4  mov     rdi, [rsi+20h]
0x1400dc6d8  mov     [rsp+378h+var_2F8], rdi
0x1400dc6e0  cmp     rbx, rdi
0x1400dc6e3  jle     short loc_1400DC6FE
0x1400dc6e5  mov     r12, 7FFFFFFFFFFFFFFFh
0x1400dc6ef  cmp     rbx, [rsi+18h]
0x1400dc6f3  cmovg   rbx, r12
0x1400dc6f7  mov     [rsp+378h+var_308], rbx
0x1400dc6fc  jmp     short loc_1400DC708
0x1400dc6fe  mov     r12, 7FFFFFFFFFFFFFFFh
0x1400dc708  test    r15b, r15b
0x1400dc70b  jz      short loc_1400DC724
0x1400dc70d  lea     rdx, [rsi+0A0h]
0x1400dc714  lea     rcx, [rsi+78h]
0x1400dc718  call    cs:__imp_FsRtlReleaseHeaderMutex
0x1400dc71f  nop     dword ptr [rax+rax+00h]
0x1400dc724  cmp     [r13+30h], r14
0x1400dc728  jz      loc_1400DC7B1
0x1400dc72e  mov     al, [rsi+5]
0x1400dc731  test    al, al
0x1400dc733  jz      short loc_1400DC7B1
0x1400dc735  cmp     rbx, [rsi+18h]
0x1400dc739  jg      short loc_1400DC7B1
0x1400dc73b  lea     r12, [rsi+28h]
0x1400dc73f  mov     [rsp+378h+var_320], r12
0x1400dc744  mov     rax, qword ptr [rsp+378h+FileOffset]
0x1400dc749  cmp     rax, [r12]
0x1400dc74d  jg      short loc_1400DC7A7
0x1400dc74f  mov     ecx, 4; Irp
0x1400dc754  call    cs:__imp_IoSetTopLevelIrp
0x1400dc75b  nop     dword ptr [rax+rax+00h]
0x1400dc760  mov     r15d, [rsp+378h+Length]
0x1400dc765  cmp     byte ptr [rsi+5], 2
0x1400dc769  jnz     loc_1400DC847
0x1400dc76f  mov     byte ptr [rsp+378h+var_350], r14b
0x1400dc774  mov     eax, [rsp+378h+var_310]
0x1400dc778  mov     dword ptr [rsp+378h+IoStatus], eax
0x1400dc77c  mov     r9d, r15d
0x1400dc77f  lea     r8, [rsp+378h+FileOffset]
0x1400dc784  mov     rdx, r13
0x1400dc787  mov     rcx, [rsp+378h+var_328]
0x1400dc78c  call    NtfsFastIoCheckIfPossibleInternal
0x1400dc791  test    al, al
0x1400dc793  jnz     loc_1400DC847
0x1400dc799  xor     ecx, ecx; Irp
0x1400dc79b  call    cs:__imp_IoSetTopLevelIrp
0x1400dc7a2  nop     dword ptr [rax+rax+00h]
0x1400dc7a7  mov     r12, 7FFFFFFFFFFFFFFFh
0x1400dc7b1  mov     r15b, r14b
0x1400dc7b4  cmp     [rsp+378h+var_348], r14b
0x1400dc7b9  jz      loc_1400DCBC8
0x1400dc7bf  lea     rbx, [rsi+0A0h]
0x1400dc7c6  mov     rdx, rbx
0x1400dc7c9  lea     rcx, [rsi+78h]
0x1400dc7cd  call    cs:__imp_FsRtlAcquireHeaderMutex
0x1400dc7d4  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
