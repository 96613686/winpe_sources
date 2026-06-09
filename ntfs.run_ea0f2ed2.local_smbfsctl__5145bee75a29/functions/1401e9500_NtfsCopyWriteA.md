# NtfsCopyWriteA

- ea: `0x1401e9500`
- end: `0x1401e9e17`
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
- `0x140059250`
- `0x1400596c0`
- `0x140181b60`
- `0x1401e9500`
- `0x1401e9e20`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1401e96a3`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401e96a3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401e9ae1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401e9ae1`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1401e98c2`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1401e99da`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1401e9b38`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1401e98c2`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1401e99da`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1401e9b38`
- `ntoskrnl!CcCopyWriteWontFlush` at `0x1401e95dc`
- `ntoskrnl!CcCopyWriteWontFlush` at `0x1401e95dc`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x1401e982d`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x1401e9876`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x1401e9aa3`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x1401e982d`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x1401e9876`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x1401e9aa3`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x1401e97c7`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x1401e9a30`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x1401e9b60`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x1401e9d60`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x1401e9d7a`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x1401e97c7`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x1401e9a30`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x1401e9b60`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x1401e9d60`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x1401e9d7a`
- `ntoskrnl!CcCanIWrite` at `0x1401e95c3`
- `ntoskrnl!CcCanIWrite` at `0x1401e95c3`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1402b135d`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1402b135d`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401e9ac9`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401e9ac9`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1401e9572`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1401e9572`
- `ntoskrnl!CcCopyWriteEx` at `0x1401e98fc`
- `ntoskrnl!CcCopyWriteEx` at `0x1401e98fc`

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
  char *v38; // rdx
  char *v39; // rcx
  __int64 v40; // r12
  __int64 v41; // rdx
  signed __int64 v42; // r9
  signed __int64 v43; // rdx
  int v44; // r8d
  signed __int64 v45; // r9
  signed __int64 v46; // r10
  signed __int64 v47; // r8
  signed __int64 v48; // r10
  signed __int64 v49; // r9
  signed __int32 v50[8]; // [rsp+0h] [rbp-348h] BYREF
  char v51; // [rsp+30h] [rbp-318h] BYREF
  BOOLEAN v52; // [rsp+31h] [rbp-317h]
  char v53; // [rsp+32h] [rbp-316h]
  LONGLONG v54; // [rsp+38h] [rbp-310h] BYREF
  char *i; // [rsp+40h] [rbp-308h]
  ULONG v56; // [rsp+48h] [rbp-300h]
  _BYTE *v57; // [rsp+50h] [rbp-2F8h] BYREF
  PLARGE_INTEGER v58; // [rsp+58h] [rbp-2F0h]
  __int64 v59; // [rsp+60h] [rbp-2E8h]
  PFILE_OBJECT v60; // [rsp+68h] [rbp-2E0h]
  __int64 v61; // [rsp+70h] [rbp-2D8h]
  _WORD *v62; // [rsp+78h] [rbp-2D0h]
  LONGLONG v63; // [rsp+80h] [rbp-2C8h]
  PVOID FsContext2; // [rsp+88h] [rbp-2C0h]
  _DWORD *v65; // [rsp+90h] [rbp-2B8h]
  __int64 v66; // [rsp+98h] [rbp-2B0h]
  char *v67; // [rsp+A0h] [rbp-2A8h]
  __int64 v68; // [rsp+A8h] [rbp-2A0h]
  PFILE_OBJECT v69; // [rsp+B0h] [rbp-298h]
  char *v70; // [rsp+B8h] [rbp-290h]
  PVOID v71; // [rsp+C0h] [rbp-288h]
  char *v72; // [rsp+C8h] [rbp-280h]
  _BYTE v73[560]; // [rsp+D0h] [rbp-278h] BYREF

  v52 = Wait;
  v8 = Length;
  v56 = Length;
  v58 = FileOffset;
  v60 = FileObject;
  v69 = FileObject;
  v66 = a6;
  v54 = 0;
  v51 = 0;
  if ( !IoGetTopLevelIrp() )
  {
    FsContext = (char *)FileObject->FsContext;
    v67 = FsContext;
    if ( (*((_DWORD *)FsContext + 128) & 0x10000000) == 0 )
    {
      FsContext2 = FileObject->FsContext2;
      v71 = FsContext2;
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
      v65 = FsContext + 200;
      if ( (*((_DWORD *)FsContext + 50) & 0x10) != 0 )
      {
        v13 = *((_QWORD *)FsContext + 23);
        v14 = *(_QWORD *)(v13 + 328);
        if ( (!v14 || !*(_QWORD *)(v14 + 24)) && (*(_DWORD *)(v13 + 4) & 0x20020100) == 0x20000000 )
          return 0;
      }
      v72 = FsContext + 288;
      if ( FileObject->SectionObjectPointer != (PSECTION_OBJECT_POINTERS)(*((_QWORD *)FsContext + 36) + 16LL) )
        return 0;
      *(_DWORD *)a7 = 0;
      v17 = v8;
      v61 = v8;
      *(_QWORD *)(a7 + 8) = v8;
      if ( !(_DWORD)v8 )
        return 1;
      v70 = FsContext + 200;
      KeEnterCriticalRegion();
      v57 = v73;
      memset(v73, 0, 0x228u);
      NtfsInitializeIrpContextInternal(0, 1, 1, (__int64 *)&v57);
      v19 = *(_QWORD *)(*((_QWORD *)FsContext + 23) + 96LL);
      v20 = (__int64)v57;
      *((_QWORD *)v57 + 13) = v19;
      if ( v19 && (*(_DWORD *)(v19 + 24) & 0x20000) != 0 )
        *(_QWORD *)(v20 + 16) |= 0x100000uLL;
      else
        *(_QWORD *)(v20 + 16) &= ~0x100000uLL;
      QuadPart = FileOffset->QuadPart;
      v54 = FileOffset->QuadPart;
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
      LOBYTE(v18) = v52;
      v15 = NtfsCheckCompressAndAcquirePagingResource(v20, FsContext, v18);
      if ( !v15 )
      {
LABEL_56:
        NtfsCleanupIrpContext((__int64)v57, 0, v18);
        KeLeaveCriticalRegion();
        return v15;
      }
      v22 = 0;
      v63 = 0;
      v62 = FsContext;
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
      v68 = v17;
      v26 = QuadPart + v17;
      v59 = QuadPart + v17;
      if ( v58->QuadPart < 0 || (v27 = 0, v26 > *((_QWORD *)FsContext + 5)) )
      {
        FsRtlAcquireHeaderMutex(FsContext + 120, FsContext + 160);
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
              FsRtlAcquireHeaderMutex(FsContext + 120, v30);
              v29 = 1;
            }
            v32 = *((_QWORD *)FsContext + 5);
            v33 = FsContext + 160;
            if ( v29 )
              break;
            _InterlockedOr(v50, 0);
            if ( j == *v33 )
              goto LABEL_35;
            v30 = FsContext + 160;
          }
          FsRtlReleaseHeaderMutex(FsContext + 120, v33);
LABEL_35:
          v28 = i;
        }
        if ( v58->QuadPart >= 0 && v26 <= v32 )
          break;
        if ( v27 )
        {
          v40 = v61;
          NtfsGetIoAtEof((_DWORD)v57, (_DWORD)FsContext, v58->QuadPart, v61, 1, (__int64)&v51);
          if ( v51 )
          {
            if ( v58->QuadPart < 0 )
              v54 = *((_QWORD *)FsContext + 4);
            v26 = v40 + v54;
            v59 = v40 + v54;
            v22 = *((_QWORD *)FsContext + 4);
            v63 = v22;
            if ( v40 + v54 > v22 && ((*((_DWORD *)FsContext + 50) & 8) != 0 || v26 > *((_QWORD *)FsContext + 3)) )
            {
              v26 = 0x7FFFFFFFFFFFFFFFLL;
              v59 = 0x7FFFFFFFFFFFFFFFLL;
            }
          }
          break;
        }
        FsRtlAcquireHeaderMutex(v28, FsContext + 160);
        v27 = 1;
      }
      if ( v27 )
        FsRtlReleaseHeaderMutex(i, FsContext + 160);
      v34 = v60;
      if ( !v60->PrivateCacheMap
        || !FsContext[5]
        || v26 > *((_QWORD *)FsContext + 3)
        || (v35 = (__int64 *)(FsContext + 40), v58 = (PLARGE_INTEGER)(FsContext + 40), v54 > *((_QWORD *)FsContext + 5)) )
      {
LABEL_61:
        v15 = 0;
        if ( !v51 )
          goto LABEL_53;
        FsRtlAcquireHeaderMutex(FsContext + 120, FsContext + 160);
        if ( (*((_DWORD *)FsContext + 50) & 0x20000) == 0 || *((_QWORD *)FsContext + 4) >= v22 )
          goto LABEL_63;
        v43 = *((_QWORD *)FsContext + 58);
        if ( v22 < v43 )
          v43 = v22;
        if ( v43 <= *((_QWORD *)FsContext + 5) )
          goto LABEL_63;
        if ( (*((_DWORD *)FsContext + 50) & 0x20000) != 0 )
        {
          v48 = *((_QWORD *)FsContext + 58);
          if ( v48 < v43 )
          {
LABEL_132:
            *((_QWORD *)FsContext + 58) = v43;
            goto LABEL_133;
          }
          if ( *((_QWORD *)FsContext + 5) > v43 )
          {
            if ( *(_QWORD *)(*((_QWORD *)FsContext + 36) + 16LL) && v43 != 0x7FFFFFFFFFFFFFFFLL )
            {
              v49 = (v43 + 4095) & 0xFFFFFFFFFFFFF000uLL;
              if ( v49 < v48 )
                *((_QWORD *)FsContext + 58) = v49;
              goto LABEL_133;
            }
            goto LABEL_132;
          }
        }
LABEL_133:
        *((_QWORD *)FsContext + 5) = v43;
LABEL_63:
        *((_QWORD *)FsContext + 4) = v22;
        v38 = FsContext + 160;
        v39 = FsContext + 120;
        goto LABEL_52;
      }
      IoSetTopLevelIrp((PIRP)4);
      if ( FsContext[5] == 2 && !(unsigned __int8)NtfsFastIoCheckIfPossibleInternal((_DWORD)v57, v34, a5, 0) )
      {
        IoSetTopLevelIrp(0);
        goto LABEL_61;
      }
      LOBYTE(v36) = v52;
      v15 = CcCopyWriteEx(v34, &v54, v56, v36, v66, 0);
      v53 = v15;
      IoSetTopLevelIrp(0);
      if ( !v15 )
        goto LABEL_61;
      v37 = v60;
      NtfsUpdateFileTimestampsForModification(v60, *((_QWORD *)FsContext + 23), FsContext2);
      v37->CurrentByteOffset.QuadPart = v54 + v61;
      if ( !v51 )
      {
LABEL_53:
        if ( *v62 != 1794 )
          FsContext = (char *)*((_QWORD *)FsContext + 23);
        ExReleaseResourceLite(*((PERESOURCE *)FsContext + 14));
        goto LABEL_56;
      }
      FsRtlAcquireHeaderMutex(i, FsContext + 160);
      v37->Flags |= 0x2000u;
      if ( v26 <= *((_QWORD *)FsContext + 4) )
      {
LABEL_48:
        if ( (*v65 & 0x20000) != 0 && v26 <= *v35 )
          goto LABEL_51;
        if ( (*v65 & 0x20000) == 0 )
        {
LABEL_50:
          *((_QWORD *)FsContext + 5) = v26;
LABEL_51:
          *((_QWORD *)v37->SectionObjectPointer->SharedCacheMap + 1) = *((_QWORD *)FsContext + 4);
          v38 = FsContext + 160;
          v39 = i;
LABEL_52:
          FsRtlReleaseHeaderMutex(v39, v38);
          goto LABEL_53;
        }
        v42 = *((_QWORD *)FsContext + 58);
        if ( v42 >= v26 )
        {
          if ( *v35 <= v26 )
            goto LABEL_50;
          if ( *(_QWORD *)(*((_QWORD *)FsContext + 36) + 16LL) && v26 != 0x7FFFFFFFFFFFFFFFLL )
          {
            v47 = (v26 + 4095) & 0xFFFFFFFFFFFFF000uLL;
            if ( v47 < v42 )
              *((_QWORD *)FsContext + 58) = v47;
            goto LABEL_50;
          }
        }
        *((_QWORD *)FsContext + 58) = v26;
        goto LABEL_50;
      }
      if ( (*((_DWORD *)FsContext + 50) & 0x20000) == 0 )
        goto LABEL_77;
      v41 = *((_QWORD *)FsContext + 58);
      if ( v26 < v41 )
        v41 = v26;
      if ( v41 <= *((_QWORD *)FsContext + 5) )
      {
LABEL_77:
        *((_QWORD *)FsContext + 4) = v26;
        goto LABEL_48;
      }
      v44 = *((_DWORD *)FsContext + 50);
      if ( (v44 & 0x20000) != 0 )
      {
        v45 = *((_QWORD *)FsContext + 58);
        if ( v45 < v41 )
        {
LABEL_117:
          *((_QWORD *)FsContext + 58) = v41;
          goto LABEL_118;
        }
        if ( *v35 > v41 )
        {
          if ( *(_QWORD *)(*(_QWORD *)v72 + 16LL) && v41 != 0x7FFFFFFFFFFFFFFFLL )
          {
            v46 = (v41 + 4095) & 0xFFFFFFFFFFFFF000uLL;
            if ( v46 < v45 )
              *((_QWORD *)FsContext + 58) = v46;
            goto LABEL_118;
          }
          goto LABEL_117;
        }
      }
LABEL_118:
      *v35 = v41;
      goto LABEL_77;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1401e9500  push    rbx
0x1401e9502  push    rsi
0x1401e9503  push    rdi
0x1401e9504  push    r12
0x1401e9506  push    r13
0x1401e9508  push    r14
0x1401e950a  push    r15
0x1401e950c  sub     rsp, 310h
0x1401e9513  mov     rax, cs:__security_cookie
0x1401e951a  xor     rax, rsp
0x1401e951d  mov     [rsp+348h+var_48], rax
0x1401e9525  mov     r13b, r9b
0x1401e9528  mov     [rsp+348h+var_317], r9b
0x1401e952d  mov     r12d, r8d
0x1401e9530  mov     [rsp+348h+var_300], r12d
0x1401e9535  mov     r15, rdx
0x1401e9538  mov     [rsp+348h+var_2F0], rdx
0x1401e953d  mov     rdi, rcx
0x1401e9540  mov     [rsp+348h+var_2E0], rcx
0x1401e9545  mov     rbx, [rsp+348h+arg_30]
0x1401e954d  mov     [rsp+348h+var_298], rcx
0x1401e9555  mov     rax, [rsp+348h+arg_28]
0x1401e955d  mov     [rsp+348h+var_2B0], rax
0x1401e9565  xor     r14d, r14d
0x1401e9568  mov     [rsp+348h+var_310], r14
0x1401e956d  mov     [rsp+348h+var_318], r14b
0x1401e9572  call    cs:__imp_IoGetTopLevelIrp
0x1401e9579  nop     dword ptr [rax+rax+00h]
0x1401e957e  test    rax, rax
0x1401e9581  jnz     loc_1401E9E10
0x1401e9587  mov     rsi, [rdi+18h]
0x1401e958b  mov     [rsp+348h+var_2A8], rsi
0x1401e9593  test    dword ptr [rsi+200h], 10000000h
0x1401e959d  jnz     loc_1401E9E10
0x1401e95a3  mov     rax, [rdi+20h]
0x1401e95a7  mov     [rsp+348h+var_2C0], rax
0x1401e95af  mov     [rsp+348h+var_288], rax
0x1401e95b7  xor     r9d, r9d; Retrying
0x1401e95ba  mov     r8b, r13b; Wait
0x1401e95bd  mov     edx, r12d; BytesToWrite
0x1401e95c0  mov     rcx, rdi; FileObject
0x1401e95c3  call    cs:__imp_CcCanIWrite
0x1401e95ca  nop     dword ptr [rax+rax+00h]
0x1401e95cf  test    al, al
0x1401e95d1  jz      short loc_1401E963D
0x1401e95d3  mov     r8d, r12d; Length
0x1401e95d6  mov     rdx, r15; FileOffset
0x1401e95d9  mov     rcx, rdi; FileObject
0x1401e95dc  call    cs:__imp_CcCopyWriteWontFlush
0x1401e95e3  nop     dword ptr [rax+rax+00h]
0x1401e95e8  test    al, al
0x1401e95ea  jz      short loc_1401E963D
0x1401e95ec  cmp     [rsi+10h], r14
0x1401e95f0  jz      short loc_1401E963D
0x1401e95f2  mov     rax, [rsi+210h]
0x1401e95f9  test    rax, rax
0x1401e95fc  jnz     loc_1401E9CCF
0x1401e9602  lea     rdx, [rsi+0C8h]
0x1401e9609  mov     [rsp+348h+var_2B8], rdx
0x1401e9611  mov     eax, [rdx]
0x1401e9613  test    al, 10h
0x1401e9615  jz      short loc_1401E9667
0x1401e9617  mov     rcx, [rsi+0B8h]
0x1401e961e  mov     rax, [rcx+148h]
0x1401e9625  test    rax, rax
0x1401e9628  jnz     loc_1401E9CE4
0x1401e962e  mov     eax, [rcx+4]
0x1401e9631  and     eax, 20020100h
0x1401e9636  cmp     eax, 20000000h
0x1401e963b  jnz     short loc_1401E9667
0x1401e963d  mov     r15b, r14b
0x1401e9640  mov     al, r15b
0x1401e9643  mov     rcx, [rsp+348h+var_48]
0x1401e964b  xor     rcx, rsp; StackCookie
0x1401e964e  call    __security_check_cookie
0x1401e9653  add     rsp, 310h
0x1401e965a  pop     r15
0x1401e965c  pop     r14
0x1401e965e  pop     r13
0x1401e9660  pop     r12
0x1401e9662  pop     rdi
0x1401e9663  pop     rsi
0x1401e9664  pop     rbx
0x1401e9665  retn
0x1401e9667  lea     rax, [rsi+120h]
0x1401e966e  mov     [rsp+348h+var_280], rax
0x1401e9676  mov     rax, [rax]
0x1401e9679  add     rax, 10h
0x1401e967d  cmp     [rdi+28h], rax
0x1401e9681  jnz     short loc_1401E963D
0x1401e9683  mov     [rbx], r14d
0x1401e9686  mov     r13, r12
0x1401e9689  mov     [rsp+348h+var_2D8], r12
0x1401e968e  mov     [rbx+8], r12
0x1401e9692  test    r12d, r12d
0x1401e9695  jz      loc_1401E9E08
0x1401e969b  mov     [rsp+348h+var_290], rdx
0x1401e96a3  call    cs:__imp_KeEnterCriticalRegion
0x1401e96aa  nop     dword ptr [rax+rax+00h]
0x1401e96af  lea     rax, [rsp+348h+var_278]
0x1401e96b7  mov     [rsp+348h+var_2F8], rax
0x1401e96bc  xor     edx, edx; Val
0x1401e96be  mov     r8d, 228h; Size
0x1401e96c4  lea     rcx, [rsp+348h+var_278]; void *
0x1401e96cc  call    memset
0x1401e96d1  lea     r9, [rsp+348h+var_2F8]
0x1401e96d6  mov     r8b, 1
0x1401e96d9  mov     dl, r8b
0x1401e96dc  xor     ecx, ecx; Irp
0x1401e96de  call    NtfsInitializeIrpContextInternal
0x1401e96e3  mov     rax, [rsi+0B8h]
0x1401e96ea  mov     rax, [rax+60h]
0x1401e96ee  mov     r9, [rsp+348h+var_2F8]
0x1401e96f3  mov     [r9+68h], rax
0x1401e96f7  test    rax, rax
0x1401e96fa  jz      short loc_1401E9709
0x1401e96fc  test    dword ptr [rax+18h], 20000h
0x1401e9703  jnz     loc_1401E9C83
0x1401e9709  btr     qword ptr [r9+10h], 14h
0x1401e970f  mov     r12, [r15]
0x1401e9712  mov     [rsp+348h+var_310], r12
0x1401e9717  mov     rax, [rsi+0C0h]
0x1401e971e  test    dword ptr [rax+18h], 40000h
0x1401e9725  jnz     loc_1401E9CF3
0x1401e972b  mov     r8b, [rsp+348h+var_317]
0x1401e9730  mov     rdx, rsi
0x1401e9733  mov     rcx, r9
0x1401e9736  call    NtfsCheckCompressAndAcquirePagingResource
0x1401e973b  mov     r15b, al
0x1401e973e  test    al, al
0x1401e9740  jz      loc_1401E9AD5
0x1401e9746  mov     rdi, r14
0x1401e9749  mov     [rsp+348h+var_2C8], r14
0x1401e9751  mov     [rsp+348h+var_2D0], rsi
0x1401e9756  mov     rax, [rsi+0B8h]
0x1401e975d  mov     edx, [rax+4]
0x1401e9760  mov     eax, [rsi+0C8h]
0x1401e9766  test    al, 10h
0x1401e9768  jz      short loc_1401E979D
0x1401e976a  mov     rcx, [rsi+0B8h]
0x1401e9771  mov     rax, [rcx+148h]
0x1401e9778  test    rax, rax
0x1401e977b  jnz     loc_1401E9D4A
0x1401e9781  test    edx, 20100h
0x1401e9787  jnz     short loc_1401E979D
0x1401e9789  bt      edx, 1Dh
0x1401e978d  jb      loc_1401E9C74
0x1401e9793  bt      edx, 1Ch
0x1401e9797  jnb     loc_1401E9C67
0x1401e979d  mov     [rsp+348h+var_2A0], r13
0x1401e97a5  lea     rbx, [r12+r13]
0x1401e97a9  mov     [rsp+348h+var_2E8], rbx
0x1401e97ae  mov     rax, [rsp+348h+var_2F0]
0x1401e97b3  cmp     [rax], r14
0x1401e97b6  jge     loc_1401E9AF2
0x1401e97bc  lea     rdx, [rsi+0A0h]
0x1401e97c3  lea     rcx, [rsi+78h]
0x1401e97c7  call    cs:__imp_FsRtlAcquireHeaderMutex
0x1401e97ce  nop     dword ptr [rax+rax+00h]
0x1401e97d3  mov     r15b, 1
0x1401e97d6  lea     rcx, [rsi+78h]
0x1401e97da  mov     [rsp+348h+var_308], rcx
0x1401e97df  test    r15b, r15b
0x1401e97e2  jnz     loc_1401E9C1F
0x1401e97e8  mov     cl, r15b
0x1401e97eb  lea     rax, [rsi+0A0h]
0x1401e97f2  mov     r12d, [rax]
0x1401e97f5  test    r12b, 1
0x1401e97f9  jnz     loc_1401E9D59
0x1401e97ff  mov     r13, [rsi+28h]
0x1401e9803  lea     rdx, [rsi+0A0h]
0x1401e980a  test    cl, cl
0x1401e980c  jnz     short loc_1401E9829
0x1401e980e  lock or [rsp+348h+var_348], r14d
0x1401e9813  mov     eax, [rdx]
0x1401e9815  cmp     r12d, eax
0x1401e9818  jz      short loc_1401E9839
0x1401e981a  mov     r12d, 1
0x1401e9820  lea     rax, [rsi+0A0h]
0x1401e9827  jmp     short loc_1401E97F5
0x1401e9829  lea     rcx, [rsi+78h]
0x1401e982d  call    cs:__imp_FsRtlReleaseHeaderMutex
0x1401e9834  nop     dword ptr [rax+rax+00h]
0x1401e9839  mov     rcx, [rsp+348h+var_308]
0x1401e983e  mov     rdx, rsi
0x1401e9841  mov     rax, [rsp+348h+var_2F0]
0x1401e9846  mov     r8, [rax]
0x1401e9849  test    r8, r8
0x1401e984c  js      loc_1401E9B8C
0x1401e9852  cmp     rbx, r13
0x1401e9855  jg      loc_1401E9B8C
0x1401e985b  mov     r12, 7FFFFFFFFFFFFFFFh
0x1401e9865  test    r15b, r15b
0x1401e9868  jz      short loc_1401E9882
0x1401e986a  lea     rdx, [rsi+0A0h]
0x1401e9871  mov     rcx, [rsp+348h+var_308]
0x1401e9876  call    cs:__imp_FsRtlReleaseHeaderMutex
0x1401e987d  nop     dword ptr [rax+rax+00h]
0x1401e9882  mov     r15, [rsp+348h+var_2E0]
0x1401e9887  cmp     [r15+30h], r14
0x1401e988b  jz      loc_1401E9B44
0x1401e9891  cmp     [rsi+5], r14b
0x1401e9895  jz      loc_1401E9B44
0x1401e989b  cmp     rbx, [rsi+18h]
0x1401e989f  jg      loc_1401E9B44
0x1401e98a5  lea     r13, [rsi+28h]
0x1401e98a9  mov     [rsp+348h+var_2F0], r13
0x1401e98ae  mov     rax, [r13+0]
0x1401e98b2  cmp     [rsp+348h+var_310], rax
0x1401e98b7  jg      loc_1401E9B44
0x1401e98bd  mov     ecx, 4; Irp
0x1401e98c2  call    cs:__imp_IoSetTopLevelIrp
0x1401e98c9  nop     dword ptr [rax+rax+00h]
0x1401e98ce  cmp     byte ptr [rsi+5], 2
0x1401e98d2  jz      loc_1401E9B07
0x1401e98d8  mov     [rsp+348h+var_320], r14
0x1401e98dd  mov     rax, [rsp+348h+var_2B0]
0x1401e98e5  mov     [rsp+348h+var_328], rax
0x1401e98ea  mov     r9b, [rsp+348h+var_317]
0x1401e98ef  mov     r8d, [rsp+348h+var_300]
0x1401e98f4  lea     rdx, [rsp+348h+var_310]
0x1401e98f9  mov     rcx, r15
0x1401e98fc  call    cs:__imp_CcCopyWriteEx
0x1401e9903  nop     dword ptr [rax+rax+00h]
0x1401e9908  mov     r15b, al
0x1401e990b  mov     [rsp+348h+var_316], al
0x1401e990f  jmp     loc_1401E99D8
0x1401e9914  mov     edx, eax
0x1401e9916  mov     cl, cs:NtfsStatusDebugFlags
0x1401e991c  test    cl, cl
0x1401e991e  jz      short loc_1401E996F
0x1401e9920  test    eax, eax
0x1401e9922  jz      short loc_1401E996F
0x1401e9924  cmp     eax, 126h
0x1401e9929  jz      short loc_1401E996F
0x1401e992b  lea     ecx, [rax-12Ah]
0x1401e9931  cmp     ecx, 1
0x1401e9934  jbe     short loc_1401E996F
0x1401e9936  cmp     eax, 0FFFFFFEDh
0x1401e9939  jnb     short loc_1401E996F
0x1401e993b  cmp     eax, 0C00000D8h
0x1401e9940  jz      short loc_1401E996F
0x1401e9942  cmp     eax, 0C0000016h
0x1401e9947  jz      short loc_1401E996F
0x1401e9949  cmp     eax, 0C0000011h
0x1401e994e  jz      short loc_1401E996F
0x1401e9950  add     eax, 7FFFFFFBh
0x1401e9955  cmp     eax, 1
0x1401e9958  jbe     short loc_1401E996F
0x1401e995a  cmp     edx, 103h
0x1401e9960  jz      short loc_1401E996F
0x1401e9962  xor     ecx, ecx
0x1401e9964  mov     r8d, 3B0382h
0x1401e996a  call    NtfsStatusTraceAndDebugInternal
0x1401e996f  xor     r15b, r15b
0x1401e9972  mov     [rsp+348h+var_316], r15b
0x1401e9977  xor     r14d, r14d
0x1401e997a  mov     r12, 7FFFFFFFFFFFFFFFh
0x1401e9984  mov     rsi, [rsp+348h+var_2A8]
0x1401e998c  mov     rbx, [rsp+348h+var_2E8]
0x1401e9991  mov     rdi, [rsp+348h+var_2C8]
0x1401e9999  mov     rax, [rsp+348h+var_2A0]
0x1401e99a1  mov     [rsp+348h+var_2D8], rax
0x1401e99a6  mov     rax, [rsp+348h+var_298]
0x1401e99ae  mov     [rsp+348h+var_2E0], rax
0x1401e99b3  mov     rax, [rsp+348h+var_290]
0x1401e99bb  mov     [rsp+348h+var_2B8], rax
0x1401e99c3  mov     rax, [rsp+348h+var_288]
0x1401e99cb  mov     [rsp+348h+var_2C0], rax
0x1401e99d3  mov     r13, [rsp+348h+var_2F0]
0x1401e99d8  xor     ecx, ecx; Irp
0x1401e99da  call    cs:__imp_IoSetTopLevelIrp
0x1401e99e1  nop     dword ptr [rax+rax+00h]
0x1401e99e6  test    r15b, r15b
0x1401e99e9  jz      loc_1401E9B44
0x1401e99ef  mov     r8, [rsp+348h+var_2C0]
0x1401e99f7  mov     rdx, [rsi+0B8h]
0x1401e99fe  mov     rdi, [rsp+348h+var_2E0]
0x1401e9a03  mov     rcx, rdi
0x1401e9a06  call    NtfsUpdateFileTimestampsForModification
0x1401e9a0b  mov     rax, [rsp+348h+var_2D8]
0x1401e9a10  add     rax, [rsp+348h+var_310]
0x1401e9a15  mov     [rdi+68h], rax
0x1401e9a19  cmp     [rsp+348h+var_318], r14b
0x1401e9a1e  jz      loc_1401E9AAF
0x1401e9a24  lea     rdx, [rsi+0A0h]
0x1401e9a2b  mov     rcx, [rsp+348h+var_308]
0x1401e9a30  call    cs:__imp_FsRtlAcquireHeaderMutex
0x1401e9a37  nop     dword ptr [rax+rax+00h]
0x1401e9a3c  mov     eax, [rdi+50h]
0x1401e9a3f  bts     eax, 0Dh
0x1401e9a43  mov     [rdi+50h], eax
0x1401e9a46  mov     r11d, 20000h
0x1401e9a4c  cmp     rbx, [rsi+20h]
0x1401e9a50  jg      loc_1401E9C28
0x1401e9a56  mov     ecx, 200h
0x1401e9a5b  mov     rdx, [rsp+348h+var_2B8]
0x1401e9a63  mov     eax, [rdx]
0x1401e9a65  test    r11d, eax
0x1401e9a68  jnz     loc_1401E9DAB
  ... truncated ...
```
