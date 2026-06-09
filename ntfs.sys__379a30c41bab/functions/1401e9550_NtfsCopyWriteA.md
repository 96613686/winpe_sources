# NtfsCopyWriteA

- ea: `0x1401e9550`
- end: `0x1401e9e67`
- name: `NtfsCopyWriteA`
- size: `2327`
- prototype: `__int64 __fastcall(PFILE_OBJECT FileObject, PLARGE_INTEGER FileOffset, ULONG Length, BOOLEAN Wait, int, __int64, __int64)`
- caller_count: `0`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140007ea0`
- `0x140008740`
- `0x140009af0`
- `0x140017030`
- `0x14001cd10`
- `0x1400235d0`
- `0x1400592c0`
- `0x140059740`
- `0x140181bb0`
- `0x1401e9550`
- `0x1401e9e70`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1401e96f3`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401e96f3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401e9b31`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401e9b31`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1401e9912`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1401e9a2a`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1401e9b88`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1401e9912`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1401e9a2a`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1401e9b88`
- `ntoskrnl!CcCopyWriteWontFlush` at `0x1401e962c`
- `ntoskrnl!CcCopyWriteWontFlush` at `0x1401e962c`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x1401e987d`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x1401e98c6`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x1401e9af3`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x1401e987d`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x1401e98c6`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x1401e9af3`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x1401e9817`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x1401e9a80`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x1401e9bb0`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x1401e9db0`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x1401e9dca`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x1401e9817`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x1401e9a80`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x1401e9bb0`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x1401e9db0`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x1401e9dca`
- `ntoskrnl!CcCanIWrite` at `0x1401e9613`
- `ntoskrnl!CcCanIWrite` at `0x1401e9613`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1402b13ad`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1402b13ad`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401e9b19`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401e9b19`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1401e95c2`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1401e95c2`
- `ntoskrnl!CcCopyWriteEx` at `0x1401e994c`
- `ntoskrnl!CcCopyWriteEx` at `0x1401e994c`

## pseudocode

```c
char __fastcall NtfsCopyWriteA(
        PFILE_OBJECT FileObject,
        PLARGE_INTEGER FileOffset,
        ULONG Length,
        BOOLEAN Wait,
        ULONG a5,
        __int64 a6,
        __int64 a7)
{
  __int64 v8; // r12
  char *FsContext; // rsi
  __int64 v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rax
  char v15; // r15
  __int64 v17; // r13
  __int64 v18; // r8
  __int64 v19; // rax
  __int64 v20; // r9
  LONGLONG QuadPart; // r12
  LONGLONG v22; // rdi
  int v23; // edx
  __int64 v24; // rcx
  __int64 v25; // rax
  __int64 v26; // rbx
  char v27; // r15
  char *v28; // rcx
  char v29; // cl
  char *v30; // rax
  int j; // r12d
  __int64 v32; // r13
  _DWORD *v33; // rdx
  PFILE_OBJECT v34; // r15
  __int64 *v35; // r13
  __int64 v36; // r9
  PFILE_OBJECT v37; // rdi
  __int64 v38; // r8
  char *v39; // rdx
  char *v40; // rcx
  __int64 v41; // r12
  __int64 v42; // rdx
  signed __int64 v43; // r9
  signed __int64 v44; // rdx
  int v45; // r8d
  signed __int64 v46; // r9
  signed __int64 v47; // r10
  signed __int64 v48; // r8
  signed __int64 v49; // r10
  signed __int64 v50; // r9
  signed __int32 v51[8]; // [rsp+0h] [rbp-348h] BYREF
  char v52; // [rsp+30h] [rbp-318h] BYREF
  BOOLEAN v53; // [rsp+31h] [rbp-317h]
  char v54; // [rsp+32h] [rbp-316h]
  LONGLONG v55; // [rsp+38h] [rbp-310h] BYREF
  char *i; // [rsp+40h] [rbp-308h]
  ULONG v57; // [rsp+48h] [rbp-300h]
  _BYTE *v58; // [rsp+50h] [rbp-2F8h] BYREF
  PLARGE_INTEGER v59; // [rsp+58h] [rbp-2F0h]
  __int64 v60; // [rsp+60h] [rbp-2E8h]
  PFILE_OBJECT v61; // [rsp+68h] [rbp-2E0h]
  __int64 v62; // [rsp+70h] [rbp-2D8h]
  _WORD *v63; // [rsp+78h] [rbp-2D0h]
  LONGLONG v64; // [rsp+80h] [rbp-2C8h]
  PVOID FsContext2; // [rsp+88h] [rbp-2C0h]
  _DWORD *v66; // [rsp+90h] [rbp-2B8h]
  __int64 v67; // [rsp+98h] [rbp-2B0h]
  char *v68; // [rsp+A0h] [rbp-2A8h]
  __int64 v69; // [rsp+A8h] [rbp-2A0h]
  PFILE_OBJECT v70; // [rsp+B0h] [rbp-298h]
  char *v71; // [rsp+B8h] [rbp-290h]
  PVOID v72; // [rsp+C0h] [rbp-288h]
  char *v73; // [rsp+C8h] [rbp-280h]
  _BYTE v74[560]; // [rsp+D0h] [rbp-278h] BYREF

  v53 = Wait;
  v8 = Length;
  v57 = Length;
  v59 = FileOffset;
  v61 = FileObject;
  v70 = FileObject;
  v67 = a6;
  v55 = 0;
  v52 = 0;
  if ( !IoGetTopLevelIrp() )
  {
    FsContext = (char *)FileObject->FsContext;
    v68 = FsContext;
    if ( (*((_DWORD *)FsContext + 128) & 0x10000000) == 0 )
    {
      FsContext2 = FileObject->FsContext2;
      v72 = FsContext2;
      if ( !CcCanIWrite(FileObject, v8, Wait, 0) )
        return 0;
      if ( !CcCopyWriteWontFlush(FileObject, FileOffset, v8) )
        return 0;
      if ( !*((_QWORD *)FsContext + 2) )
        return 0;
      v12 = *((_QWORD *)FsContext + 66);
      if ( v12 )
      {
        if ( (*(_DWORD *)(*(_QWORD *)(v12 + 64) + 4LL) & 1) != 0 )
          return 0;
      }
      v66 = FsContext + 200;
      if ( (*((_DWORD *)FsContext + 50) & 0x10) != 0 )
      {
        v13 = *((_QWORD *)FsContext + 23);
        v14 = *(_QWORD *)(v13 + 328);
        if ( (!v14 || !*(_QWORD *)(v14 + 24)) && (*(_DWORD *)(v13 + 4) & 0x20020100) == 0x20000000 )
          return 0;
      }
      v73 = FsContext + 288;
      if ( FileObject->SectionObjectPointer != (PSECTION_OBJECT_POINTERS)(*((_QWORD *)FsContext + 36) + 16LL) )
        return 0;
      *(_DWORD *)a7 = 0;
      v17 = v8;
      v62 = v8;
      *(_QWORD *)(a7 + 8) = v8;
      if ( !(_DWORD)v8 )
        return 1;
      v71 = FsContext + 200;
      KeEnterCriticalRegion();
      v58 = v74;
      memset(v74, 0, 0x228u);
      NtfsInitializeIrpContextInternal(0, 1, 1, (__int64 *)&v58);
      v19 = *(_QWORD *)(*((_QWORD *)FsContext + 23) + 96LL);
      v20 = (__int64)v58;
      *((_QWORD *)v58 + 13) = v19;
      if ( v19 && (*(_DWORD *)(v19 + 24) & 0x20000) != 0 )
        *(_QWORD *)(v20 + 16) |= 0x100000uLL;
      else
        *(_QWORD *)(v20 + 16) &= ~0x100000uLL;
      QuadPart = FileOffset->QuadPart;
      v55 = FileOffset->QuadPart;
      if ( (*(_DWORD *)(*((_QWORD *)FsContext + 24) + 24LL) & 0x40000) != 0
        && (*(_DWORD *)(*((_QWORD *)FsContext + 23) + 4LL) & 0x100) == 0
        && (FsContext[512] & 0x20) == 0
        && ((*((_WORD *)FsContext + 230) & 0xC0FF) != 0 || (*((_DWORD *)FsContext + 50) & 8) != 0)
        && *((_DWORD *)FsContext + 64) == 128
        && !*((_DWORD *)FsContext + 112) )
      {
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(0, 3221226650LL, 3867314);
        *(_DWORD *)a7 = -1073740646;
        *(_QWORD *)(a7 + 8) = 0;
        v15 = 0;
        goto LABEL_56;
      }
      LOBYTE(v18) = v53;
      v15 = NtfsCheckCompressAndAcquirePagingResource(v20, FsContext, v18);
      if ( !v15 )
      {
LABEL_56:
        NtfsCleanupIrpContext((__int64)v58, 0, v18);
        KeLeaveCriticalRegion();
        return v15;
      }
      v22 = 0;
      v64 = 0;
      v63 = FsContext;
      v23 = *(_DWORD *)(*((_QWORD *)FsContext + 23) + 4LL);
      if ( (*((_DWORD *)FsContext + 50) & 0x10) != 0 )
      {
        v24 = *((_QWORD *)FsContext + 23);
        v25 = *(_QWORD *)(v24 + 328);
        if ( (!v25 || !*(_QWORD *)(v25 + 24))
          && (v23 & 0x20100) == 0
          && ((v23 & 0x20000000) != 0 || (v23 & 0x10000000) == 0 && (unsigned __int8)NtfsGetPurgeKernelEAState(v24)) )
        {
          goto LABEL_61;
        }
      }
      v69 = v17;
      v26 = QuadPart + v17;
      v60 = QuadPart + v17;
      if ( v59->QuadPart < 0 || (v27 = 0, v26 > *((_QWORD *)FsContext + 5)) )
      {
        FsRtlAcquireHeaderMutex(FsContext + 120, FsContext + 160, v18);
        v27 = 1;
      }
      v28 = FsContext + 120;
      for ( i = FsContext + 120; ; v28 = i )
      {
        if ( v27 )
        {
          v32 = *((_QWORD *)FsContext + 5);
        }
        else
        {
          v29 = 0;
          v30 = FsContext + 160;
          for ( j = *((_DWORD *)FsContext + 40); ; j = 1 )
          {
            if ( (j & 1) != 0 )
            {
              FsRtlAcquireHeaderMutex(FsContext + 120, v30, v18);
              v29 = 1;
            }
            v32 = *((_QWORD *)FsContext + 5);
            v33 = FsContext + 160;
            if ( v29 )
              break;
            _InterlockedOr(v51, 0);
            if ( j == *v33 )
              goto LABEL_35;
            v30 = FsContext + 160;
          }
          FsRtlReleaseHeaderMutex(FsContext + 120, v33);
LABEL_35:
          v28 = i;
        }
        v18 = v59->QuadPart;
        if ( v59->QuadPart >= 0 && v26 <= v32 )
          break;
        if ( v27 )
        {
          v41 = v62;
          NtfsGetIoAtEof((_DWORD)v58, (_DWORD)FsContext, v18, v62, 1, (__int64)&v52);
          if ( v52 )
          {
            if ( v59->QuadPart < 0 )
              v55 = *((_QWORD *)FsContext + 4);
            v26 = v41 + v55;
            v60 = v41 + v55;
            v22 = *((_QWORD *)FsContext + 4);
            v64 = v22;
            if ( v41 + v55 > v22 && ((*((_DWORD *)FsContext + 50) & 8) != 0 || v26 > *((_QWORD *)FsContext + 3)) )
            {
              v26 = 0x7FFFFFFFFFFFFFFFLL;
              v60 = 0x7FFFFFFFFFFFFFFFLL;
            }
          }
          break;
        }
        FsRtlAcquireHeaderMutex(v28, FsContext + 160, v18);
        v27 = 1;
      }
      if ( v27 )
        FsRtlReleaseHeaderMutex(i, FsContext + 160);
      v34 = v61;
      if ( !v61->PrivateCacheMap
        || !FsContext[5]
        || v26 > *((_QWORD *)FsContext + 3)
        || (v35 = (__int64 *)(FsContext + 40), v59 = (PLARGE_INTEGER)(FsContext + 40), v55 > *((_QWORD *)FsContext + 5)) )
      {
LABEL_61:
        v15 = 0;
        if ( !v52 )
          goto LABEL_53;
        FsRtlAcquireHeaderMutex(FsContext + 120, FsContext + 160, v18);
        if ( (*((_DWORD *)FsContext + 50) & 0x20000) == 0 || *((_QWORD *)FsContext + 4) >= v22 )
          goto LABEL_63;
        v44 = *((_QWORD *)FsContext + 58);
        if ( v22 < v44 )
          v44 = v22;
        if ( v44 <= *((_QWORD *)FsContext + 5) )
          goto LABEL_63;
        if ( (*((_DWORD *)FsContext + 50) & 0x20000) != 0 )
        {
          v49 = *((_QWORD *)FsContext + 58);
          if ( v49 < v44 )
          {
LABEL_132:
            *((_QWORD *)FsContext + 58) = v44;
            goto LABEL_133;
          }
          if ( *((_QWORD *)FsContext + 5) > v44 )
          {
            if ( *(_QWORD *)(*((_QWORD *)FsContext + 36) + 16LL) && v44 != 0x7FFFFFFFFFFFFFFFLL )
            {
              v50 = (v44 + 4095) & 0xFFFFFFFFFFFFF000uLL;
              if ( v50 < v49 )
                *((_QWORD *)FsContext + 58) = v50;
              goto LABEL_133;
            }
            goto LABEL_132;
          }
        }
LABEL_133:
        *((_QWORD *)FsContext + 5) = v44;
LABEL_63:
        *((_QWORD *)FsContext + 4) = v22;
        v39 = FsContext + 160;
        v40 = FsContext + 120;
        goto LABEL_52;
      }
      IoSetTopLevelIrp((PIRP)4);
      if ( FsContext[5] == 2 && !(unsigned __int8)NtfsFastIoCheckIfPossibleInternal((_DWORD)v58, v34, a5, 0) )
      {
        IoSetTopLevelIrp(0);
        goto LABEL_61;
      }
      LOBYTE(v36) = v53;
      v15 = CcCopyWriteEx(v34, &v55, v57, v36, v67, 0);
      v54 = v15;
      IoSetTopLevelIrp(0);
      if ( !v15 )
        goto LABEL_61;
      v37 = v61;
      NtfsUpdateFileTimestampsForModification(v61, *((_QWORD *)FsContext + 23), FsContext2);
      v37->CurrentByteOffset.QuadPart = v55 + v62;
      if ( !v52 )
      {
LABEL_53:
        if ( *v63 != 1794 )
          FsContext = (char *)*((_QWORD *)FsContext + 23);
        ExReleaseResourceLite(*((PERESOURCE *)FsContext + 14));
        goto LABEL_56;
      }
      FsRtlAcquireHeaderMutex(i, FsContext + 160, v38);
      v37->Flags |= 0x2000u;
      if ( v26 <= *((_QWORD *)FsContext + 4) )
      {
LABEL_48:
        if ( (*v66 & 0x20000) != 0 && v26 <= *v35 )
          goto LABEL_51;
        if ( (*v66 & 0x20000) == 0 )
        {
LABEL_50:
          *((_QWORD *)FsContext + 5) = v26;
LABEL_51:
          *((_QWORD *)v37->SectionObjectPointer->SharedCacheMap + 1) = *((_QWORD *)FsContext + 4);
          v39 = FsContext + 160;
          v40 = i;
LABEL_52:
          FsRtlReleaseHeaderMutex(v40, v39);
          goto LABEL_53;
        }
        v43 = *((_QWORD *)FsContext + 58);
        if ( v43 >= v26 )
        {
          if ( *v35 <= v26 )
            goto LABEL_50;
          if ( *(_QWORD *)(*((_QWORD *)FsContext + 36) + 16LL) && v26 != 0x7FFFFFFFFFFFFFFFLL )
          {
            v48 = (v26 + 4095) & 0xFFFFFFFFFFFFF000uLL;
            if ( v48 < v43 )
              *((_QWORD *)FsContext + 58) = v48;
            goto LABEL_50;
          }
        }
        *((_QWORD *)FsContext + 58) = v26;
        goto LABEL_50;
      }
      if ( (*((_DWORD *)FsContext + 50) & 0x20000) == 0 )
        goto LABEL_77;
      v42 = *((_QWORD *)FsContext + 58);
      if ( v26 < v42 )
        v42 = v26;
      if ( v42 <= *((_QWORD *)FsContext + 5) )
      {
LABEL_77:
        *((_QWORD *)FsContext + 4) = v26;
        goto LABEL_48;
      }
      v45 = *((_DWORD *)FsContext + 50);
      if ( (v45 & 0x20000) != 0 )
      {
        v46 = *((_QWORD *)FsContext + 58);
        if ( v46 < v42 )
        {
LABEL_117:
          *((_QWORD *)FsContext + 58) = v42;
          goto LABEL_118;
        }
        if ( *v35 > v42 )
        {
          if ( *(_QWORD *)(*(_QWORD *)v73 + 16LL) && v42 != 0x7FFFFFFFFFFFFFFFLL )
          {
            v47 = (v42 + 4095) & 0xFFFFFFFFFFFFF000uLL;
            if ( v47 < v46 )
              *((_QWORD *)FsContext + 58) = v47;
            goto LABEL_118;
          }
          goto LABEL_117;
        }
      }
LABEL_118:
      *v35 = v42;
      goto LABEL_77;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1401e9550  push    rbx
0x1401e9552  push    rsi
0x1401e9553  push    rdi
0x1401e9554  push    r12
0x1401e9556  push    r13
0x1401e9558  push    r14
0x1401e955a  push    r15
0x1401e955c  sub     rsp, 310h
0x1401e9563  mov     rax, cs:__security_cookie
0x1401e956a  xor     rax, rsp
0x1401e956d  mov     [rsp+348h+var_48], rax
0x1401e9575  mov     r13b, r9b
0x1401e9578  mov     [rsp+348h+var_317], r9b
0x1401e957d  mov     r12d, r8d
0x1401e9580  mov     [rsp+348h+var_300], r12d
0x1401e9585  mov     r15, rdx
0x1401e9588  mov     [rsp+348h+var_2F0], rdx
0x1401e958d  mov     rdi, rcx
0x1401e9590  mov     [rsp+348h+var_2E0], rcx
0x1401e9595  mov     rbx, [rsp+348h+arg_30]
0x1401e959d  mov     [rsp+348h+var_298], rcx
0x1401e95a5  mov     rax, [rsp+348h+arg_28]
0x1401e95ad  mov     [rsp+348h+var_2B0], rax
0x1401e95b5  xor     r14d, r14d
0x1401e95b8  mov     [rsp+348h+var_310], r14
0x1401e95bd  mov     [rsp+348h+var_318], r14b
0x1401e95c2  call    cs:__imp_IoGetTopLevelIrp
0x1401e95c9  nop     dword ptr [rax+rax+00h]
0x1401e95ce  test    rax, rax
0x1401e95d1  jnz     loc_1401E9E60
0x1401e95d7  mov     rsi, [rdi+18h]
0x1401e95db  mov     [rsp+348h+var_2A8], rsi
0x1401e95e3  test    dword ptr [rsi+200h], 10000000h
0x1401e95ed  jnz     loc_1401E9E60
0x1401e95f3  mov     rax, [rdi+20h]
0x1401e95f7  mov     [rsp+348h+var_2C0], rax
0x1401e95ff  mov     [rsp+348h+var_288], rax
0x1401e9607  xor     r9d, r9d; Retrying
0x1401e960a  mov     r8b, r13b; Wait
0x1401e960d  mov     edx, r12d; BytesToWrite
0x1401e9610  mov     rcx, rdi; FileObject
0x1401e9613  call    cs:__imp_CcCanIWrite
0x1401e961a  nop     dword ptr [rax+rax+00h]
0x1401e961f  test    al, al
0x1401e9621  jz      short loc_1401E968D
0x1401e9623  mov     r8d, r12d; Length
0x1401e9626  mov     rdx, r15; FileOffset
0x1401e9629  mov     rcx, rdi; FileObject
0x1401e962c  call    cs:__imp_CcCopyWriteWontFlush
0x1401e9633  nop     dword ptr [rax+rax+00h]
0x1401e9638  test    al, al
0x1401e963a  jz      short loc_1401E968D
0x1401e963c  cmp     [rsi+10h], r14
0x1401e9640  jz      short loc_1401E968D
0x1401e9642  mov     rax, [rsi+210h]
0x1401e9649  test    rax, rax
0x1401e964c  jnz     loc_1401E9D1F
0x1401e9652  lea     rdx, [rsi+0C8h]
0x1401e9659  mov     [rsp+348h+var_2B8], rdx
0x1401e9661  mov     eax, [rdx]
0x1401e9663  test    al, 10h
0x1401e9665  jz      short loc_1401E96B7
0x1401e9667  mov     rcx, [rsi+0B8h]
0x1401e966e  mov     rax, [rcx+148h]
0x1401e9675  test    rax, rax
0x1401e9678  jnz     loc_1401E9D34
0x1401e967e  mov     eax, [rcx+4]
0x1401e9681  and     eax, 20020100h
0x1401e9686  cmp     eax, 20000000h
0x1401e968b  jnz     short loc_1401E96B7
0x1401e968d  mov     r15b, r14b
0x1401e9690  mov     al, r15b
0x1401e9693  mov     rcx, [rsp+348h+var_48]
0x1401e969b  xor     rcx, rsp; StackCookie
0x1401e969e  call    __security_check_cookie
0x1401e96a3  add     rsp, 310h
0x1401e96aa  pop     r15
0x1401e96ac  pop     r14
0x1401e96ae  pop     r13
0x1401e96b0  pop     r12
0x1401e96b2  pop     rdi
0x1401e96b3  pop     rsi
0x1401e96b4  pop     rbx
0x1401e96b5  retn
0x1401e96b7  lea     rax, [rsi+120h]
0x1401e96be  mov     [rsp+348h+var_280], rax
0x1401e96c6  mov     rax, [rax]
0x1401e96c9  add     rax, 10h
0x1401e96cd  cmp     [rdi+28h], rax
0x1401e96d1  jnz     short loc_1401E968D
0x1401e96d3  mov     [rbx], r14d
0x1401e96d6  mov     r13, r12
0x1401e96d9  mov     [rsp+348h+var_2D8], r12
0x1401e96de  mov     [rbx+8], r12
0x1401e96e2  test    r12d, r12d
0x1401e96e5  jz      loc_1401E9E58
0x1401e96eb  mov     [rsp+348h+var_290], rdx
0x1401e96f3  call    cs:__imp_KeEnterCriticalRegion
0x1401e96fa  nop     dword ptr [rax+rax+00h]
0x1401e96ff  lea     rax, [rsp+348h+var_278]
0x1401e9707  mov     [rsp+348h+var_2F8], rax
0x1401e970c  xor     edx, edx; Val
0x1401e970e  mov     r8d, 228h; Size
0x1401e9714  lea     rcx, [rsp+348h+var_278]; void *
0x1401e971c  call    memset
0x1401e9721  lea     r9, [rsp+348h+var_2F8]
0x1401e9726  mov     r8b, 1
0x1401e9729  mov     dl, r8b
0x1401e972c  xor     ecx, ecx; Irp
0x1401e972e  call    NtfsInitializeIrpContextInternal
0x1401e9733  mov     rax, [rsi+0B8h]
0x1401e973a  mov     rax, [rax+60h]
0x1401e973e  mov     r9, [rsp+348h+var_2F8]
0x1401e9743  mov     [r9+68h], rax
0x1401e9747  test    rax, rax
0x1401e974a  jz      short loc_1401E9759
0x1401e974c  test    dword ptr [rax+18h], 20000h
0x1401e9753  jnz     loc_1401E9CD3
0x1401e9759  btr     qword ptr [r9+10h], 14h
0x1401e975f  mov     r12, [r15]
0x1401e9762  mov     [rsp+348h+var_310], r12
0x1401e9767  mov     rax, [rsi+0C0h]
0x1401e976e  test    dword ptr [rax+18h], 40000h
0x1401e9775  jnz     loc_1401E9D43
0x1401e977b  mov     r8b, [rsp+348h+var_317]
0x1401e9780  mov     rdx, rsi
0x1401e9783  mov     rcx, r9
0x1401e9786  call    NtfsCheckCompressAndAcquirePagingResource
0x1401e978b  mov     r15b, al
0x1401e978e  test    al, al
0x1401e9790  jz      loc_1401E9B25
0x1401e9796  mov     rdi, r14
0x1401e9799  mov     [rsp+348h+var_2C8], r14
0x1401e97a1  mov     [rsp+348h+var_2D0], rsi
0x1401e97a6  mov     rax, [rsi+0B8h]
0x1401e97ad  mov     edx, [rax+4]
0x1401e97b0  mov     eax, [rsi+0C8h]
0x1401e97b6  test    al, 10h
0x1401e97b8  jz      short loc_1401E97ED
0x1401e97ba  mov     rcx, [rsi+0B8h]
0x1401e97c1  mov     rax, [rcx+148h]
0x1401e97c8  test    rax, rax
0x1401e97cb  jnz     loc_1401E9D9A
0x1401e97d1  test    edx, 20100h
0x1401e97d7  jnz     short loc_1401E97ED
0x1401e97d9  bt      edx, 1Dh
0x1401e97dd  jb      loc_1401E9CC4
0x1401e97e3  bt      edx, 1Ch
0x1401e97e7  jnb     loc_1401E9CB7
0x1401e97ed  mov     [rsp+348h+var_2A0], r13
0x1401e97f5  lea     rbx, [r12+r13]
0x1401e97f9  mov     [rsp+348h+var_2E8], rbx
0x1401e97fe  mov     rax, [rsp+348h+var_2F0]
0x1401e9803  cmp     [rax], r14
0x1401e9806  jge     loc_1401E9B42
0x1401e980c  lea     rdx, [rsi+0A0h]
0x1401e9813  lea     rcx, [rsi+78h]
0x1401e9817  call    cs:__imp_FsRtlAcquireHeaderMutex
0x1401e981e  nop     dword ptr [rax+rax+00h]
0x1401e9823  mov     r15b, 1
0x1401e9826  lea     rcx, [rsi+78h]
0x1401e982a  mov     [rsp+348h+var_308], rcx
0x1401e982f  test    r15b, r15b
0x1401e9832  jnz     loc_1401E9C6F
0x1401e9838  mov     cl, r15b
0x1401e983b  lea     rax, [rsi+0A0h]
0x1401e9842  mov     r12d, [rax]
0x1401e9845  test    r12b, 1
0x1401e9849  jnz     loc_1401E9DA9
0x1401e984f  mov     r13, [rsi+28h]
0x1401e9853  lea     rdx, [rsi+0A0h]
0x1401e985a  test    cl, cl
0x1401e985c  jnz     short loc_1401E9879
0x1401e985e  lock or [rsp+348h+var_348], r14d
0x1401e9863  mov     eax, [rdx]
0x1401e9865  cmp     r12d, eax
0x1401e9868  jz      short loc_1401E9889
0x1401e986a  mov     r12d, 1
0x1401e9870  lea     rax, [rsi+0A0h]
0x1401e9877  jmp     short loc_1401E9845
0x1401e9879  lea     rcx, [rsi+78h]
0x1401e987d  call    cs:__imp_FsRtlReleaseHeaderMutex
0x1401e9884  nop     dword ptr [rax+rax+00h]
0x1401e9889  mov     rcx, [rsp+348h+var_308]
0x1401e988e  mov     rdx, rsi
0x1401e9891  mov     rax, [rsp+348h+var_2F0]
0x1401e9896  mov     r8, [rax]
0x1401e9899  test    r8, r8
0x1401e989c  js      loc_1401E9BDC
0x1401e98a2  cmp     rbx, r13
0x1401e98a5  jg      loc_1401E9BDC
0x1401e98ab  mov     r12, 7FFFFFFFFFFFFFFFh
0x1401e98b5  test    r15b, r15b
0x1401e98b8  jz      short loc_1401E98D2
0x1401e98ba  lea     rdx, [rsi+0A0h]
0x1401e98c1  mov     rcx, [rsp+348h+var_308]
0x1401e98c6  call    cs:__imp_FsRtlReleaseHeaderMutex
0x1401e98cd  nop     dword ptr [rax+rax+00h]
0x1401e98d2  mov     r15, [rsp+348h+var_2E0]
0x1401e98d7  cmp     [r15+30h], r14
0x1401e98db  jz      loc_1401E9B94
0x1401e98e1  cmp     [rsi+5], r14b
0x1401e98e5  jz      loc_1401E9B94
0x1401e98eb  cmp     rbx, [rsi+18h]
0x1401e98ef  jg      loc_1401E9B94
0x1401e98f5  lea     r13, [rsi+28h]
0x1401e98f9  mov     [rsp+348h+var_2F0], r13
0x1401e98fe  mov     rax, [r13+0]
0x1401e9902  cmp     [rsp+348h+var_310], rax
0x1401e9907  jg      loc_1401E9B94
0x1401e990d  mov     ecx, 4; Irp
0x1401e9912  call    cs:__imp_IoSetTopLevelIrp
0x1401e9919  nop     dword ptr [rax+rax+00h]
0x1401e991e  cmp     byte ptr [rsi+5], 2
0x1401e9922  jz      loc_1401E9B57
0x1401e9928  mov     [rsp+348h+var_320], r14
0x1401e992d  mov     rax, [rsp+348h+var_2B0]
0x1401e9935  mov     [rsp+348h+var_328], rax
0x1401e993a  mov     r9b, [rsp+348h+var_317]
0x1401e993f  mov     r8d, [rsp+348h+var_300]
0x1401e9944  lea     rdx, [rsp+348h+var_310]
0x1401e9949  mov     rcx, r15
0x1401e994c  call    cs:__imp_CcCopyWriteEx
0x1401e9953  nop     dword ptr [rax+rax+00h]
0x1401e9958  mov     r15b, al
0x1401e995b  mov     [rsp+348h+var_316], al
0x1401e995f  jmp     loc_1401E9A28
0x1401e9964  mov     edx, eax
0x1401e9966  mov     cl, cs:NtfsStatusDebugFlags
0x1401e996c  test    cl, cl
0x1401e996e  jz      short loc_1401E99BF
0x1401e9970  test    eax, eax
0x1401e9972  jz      short loc_1401E99BF
0x1401e9974  cmp     eax, 126h
0x1401e9979  jz      short loc_1401E99BF
0x1401e997b  lea     ecx, [rax-12Ah]
0x1401e9981  cmp     ecx, 1
0x1401e9984  jbe     short loc_1401E99BF
0x1401e9986  cmp     eax, 0FFFFFFEDh
0x1401e9989  jnb     short loc_1401E99BF
0x1401e998b  cmp     eax, 0C00000D8h
0x1401e9990  jz      short loc_1401E99BF
0x1401e9992  cmp     eax, 0C0000016h
0x1401e9997  jz      short loc_1401E99BF
0x1401e9999  cmp     eax, 0C0000011h
0x1401e999e  jz      short loc_1401E99BF
0x1401e99a0  add     eax, 7FFFFFFBh
0x1401e99a5  cmp     eax, 1
0x1401e99a8  jbe     short loc_1401E99BF
0x1401e99aa  cmp     edx, 103h
0x1401e99b0  jz      short loc_1401E99BF
0x1401e99b2  xor     ecx, ecx
0x1401e99b4  mov     r8d, 3B0382h
0x1401e99ba  call    NtfsStatusTraceAndDebugInternal
0x1401e99bf  xor     r15b, r15b
0x1401e99c2  mov     [rsp+348h+var_316], r15b
0x1401e99c7  xor     r14d, r14d
0x1401e99ca  mov     r12, 7FFFFFFFFFFFFFFFh
0x1401e99d4  mov     rsi, [rsp+348h+var_2A8]
0x1401e99dc  mov     rbx, [rsp+348h+var_2E8]
0x1401e99e1  mov     rdi, [rsp+348h+var_2C8]
0x1401e99e9  mov     rax, [rsp+348h+var_2A0]
0x1401e99f1  mov     [rsp+348h+var_2D8], rax
0x1401e99f6  mov     rax, [rsp+348h+var_298]
0x1401e99fe  mov     [rsp+348h+var_2E0], rax
0x1401e9a03  mov     rax, [rsp+348h+var_290]
0x1401e9a0b  mov     [rsp+348h+var_2B8], rax
0x1401e9a13  mov     rax, [rsp+348h+var_288]
0x1401e9a1b  mov     [rsp+348h+var_2C0], rax
0x1401e9a23  mov     r13, [rsp+348h+var_2F0]
0x1401e9a28  xor     ecx, ecx; Irp
0x1401e9a2a  call    cs:__imp_IoSetTopLevelIrp
0x1401e9a31  nop     dword ptr [rax+rax+00h]
0x1401e9a36  test    r15b, r15b
0x1401e9a39  jz      loc_1401E9B94
0x1401e9a3f  mov     r8, [rsp+348h+var_2C0]
0x1401e9a47  mov     rdx, [rsi+0B8h]
0x1401e9a4e  mov     rdi, [rsp+348h+var_2E0]
0x1401e9a53  mov     rcx, rdi
0x1401e9a56  call    NtfsUpdateFileTimestampsForModification
0x1401e9a5b  mov     rax, [rsp+348h+var_2D8]
0x1401e9a60  add     rax, [rsp+348h+var_310]
0x1401e9a65  mov     [rdi+68h], rax
0x1401e9a69  cmp     [rsp+348h+var_318], r14b
0x1401e9a6e  jz      loc_1401E9AFF
0x1401e9a74  lea     rdx, [rsi+0A0h]
0x1401e9a7b  mov     rcx, [rsp+348h+var_308]
0x1401e9a80  call    cs:__imp_FsRtlAcquireHeaderMutex
0x1401e9a87  nop     dword ptr [rax+rax+00h]
0x1401e9a8c  mov     eax, [rdi+50h]
0x1401e9a8f  bts     eax, 0Dh
0x1401e9a93  mov     [rdi+50h], eax
0x1401e9a96  mov     r11d, 20000h
0x1401e9a9c  cmp     rbx, [rsi+20h]
0x1401e9aa0  jg      loc_1401E9C78
0x1401e9aa6  mov     ecx, 200h
0x1401e9aab  mov     rdx, [rsp+348h+var_2B8]
0x1401e9ab3  mov     eax, [rdx]
0x1401e9ab5  test    r11d, eax
0x1401e9ab8  jnz     loc_1401E9DFB
  ... truncated ...
```
