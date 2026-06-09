# NtfsCommonClose

- ea: `0x14013b870`
- end: `0x14013c2c3`
- name: `NtfsCommonClose`
- size: `2643`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x14013a200`
- `0x14013af10`

## callees

- `0x140007ea0`
- `0x1400082b0`
- `0x14000c290`
- `0x14000cb80`
- `0x14000d1e0`
- `0x140010b88`
- `0x140012e70`
- `0x14001c2e0`
- `0x14001ebf0`
- `0x140020820`
- `0x140020de0`
- `0x140021220`
- `0x14013b870`
- `0x14013c2d0`
- `0x140140380`
- `0x1401879b0`
- `0x1401d2c34`
- `0x1401e72e8`

## import_xrefs

- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14013baaa`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14013baaa`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1402a6f14`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1402a6f14`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14013bdd5`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14013be23`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14013bdd5`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14013be23`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14013bd37`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14013bd37`
- `ntoskrnl!CcUnpinData` at `0x14013b90a`
- `ntoskrnl!CcUnpinData` at `0x14013b90a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14013bd57`
- `ntoskrnl!ExReleaseResourceLite` at `0x14013bfe9`
- `ntoskrnl!ExReleaseResourceLite` at `0x14013bd57`
- `ntoskrnl!ExReleaseResourceLite` at `0x14013bfe9`
- `ntoskrnl!ExAcquireFastMutex` at `0x14013b9d7`
- `ntoskrnl!ExAcquireFastMutex` at `0x14013bb41`
- `ntoskrnl!ExAcquireFastMutex` at `0x14013b9d7`
- `ntoskrnl!ExAcquireFastMutex` at `0x14013bb41`
- `ntoskrnl!ExReleaseFastMutex` at `0x14013ba1a`
- `ntoskrnl!ExReleaseFastMutex` at `0x14013bb93`
- `ntoskrnl!ExReleaseFastMutex` at `0x14013c2a8`
- `ntoskrnl!ExReleaseFastMutex` at `0x1402a6faf`
- `ntoskrnl!ExReleaseFastMutex` at `0x14013ba1a`
- `ntoskrnl!ExReleaseFastMutex` at `0x14013bb93`
- `ntoskrnl!ExReleaseFastMutex` at `0x14013c2a8`
- `ntoskrnl!ExReleaseFastMutex` at `0x1402a6faf`
- `ntoskrnl!MmCanFileBeTruncated` at `0x14013c059`
- `ntoskrnl!MmCanFileBeTruncated` at `0x14013c059`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14013b944`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14013b944`

## pseudocode

```c
__int64 __fastcall NtfsCommonClose(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int16 **a5,
        __int64 a6,
        int a7,
        char a8,
        char a9)
{
  __int64 v9; // rdi
  __int64 v11; // r15
  int v13; // esi
  BOOLEAN v14; // di
  int i; // eax
  unsigned int v16; // eax
  void *v17; // rcx
  int v18; // r9d
  bool v19; // si
  bool v20; // di
  __int64 v21; // rax
  __int16 *v22; // rcx
  __int64 v23; // r15
  __int64 v24; // r14
  __int64 v25; // rcx
  __int64 v26; // r8
  __int64 v27; // r15
  __int64 v28; // rcx
  __int64 v29; // r13
  __int64 v30; // rax
  __int64 v31; // rdx
  _QWORD *v32; // rcx
  __int64 v33; // rsi
  unsigned int v34; // r14d
  __int64 v35; // rax
  _QWORD *v36; // rdx
  __int64 *v37; // rdx
  _QWORD *v38; // rdi
  _QWORD *v39; // rcx
  _QWORD *v40; // rax
  __int64 v41; // rcx
  __int64 v42; // rdx
  __int64 v43; // rax
  __int64 v44; // rcx
  _QWORD *v45; // rdx
  struct _ERESOURCE *v46; // rcx
  SECTION_OBJECT_POINTERS *v47; // rcx
  __int64 v48; // r9
  int v50; // eax
  char v51; // [rsp+41h] [rbp-57h]
  char v52; // [rsp+42h] [rbp-56h] BYREF
  char v53; // [rsp+43h] [rbp-55h]
  char v54; // [rsp+44h] [rbp-54h]
  int v55; // [rsp+48h] [rbp-50h]
  __int64 v56; // [rsp+50h] [rbp-48h]

  v9 = a4;
  v11 = a2;
  v51 = 0;
  v52 = 0;
  v55 = 0;
  LODWORD(v56) = 2 * ((*(_DWORD *)(a1 + 12) & 1) == 0) + 9;
  while ( (*(_DWORD *)(v9 + 4) & 0x800) != 0 )
  {
    if ( !(unsigned __int8)NtfsAcquireExclusiveVcb(a1, v9, 0) )
      return 259;
    v51 = 1;
LABEL_11:
    if ( !(unsigned __int8)NtfsAcquireExclusiveFcb(a1, a3, 0, (unsigned int)v56) )
      goto LABEL_116;
    v19 = 0;
    v54 = 1;
    if ( (*(_DWORD *)(v11 + 512) & 0x90000) == 0x80000
      && (*(_BYTE *)(v9 + 4) & 2) == 0
      && *(_WORD *)(a3 + 188)
      && (*(_DWORD *)(v11 + 512) & 0x1000040) == 0 )
    {
      NtfsReleaseFcbEx(a1, a3, 0);
      *(_DWORD *)(a1 + 4) |= 0x10000u;
      if ( !(unsigned __int8)NtfsAcquireFcbWithPaging(a1, a3, 0, (unsigned int)v56) )
      {
LABEL_116:
        NtfsReleaseVcb(a1, v9);
        return 259;
      }
      v54 = 1;
      v50 = *(_DWORD *)(v11 + 512);
      if ( (v50 & 0x80000) != 0 && *(_WORD *)(a3 + 188) )
        v19 = (v50 & 0x1000040) == 0;
    }
    if ( v51 || (*(_DWORD *)(v9 + 4) & 0x800) == 0 )
    {
      v20 = 0;
      *(_DWORD *)(a1 + 12) |= 1u;
      if ( !*(_QWORD *)(a3 + 296) )
        goto LABEL_19;
      ExAcquireFastMutex((PFAST_MUTEX)(*(_QWORD *)(a3 + 104) + 8LL));
      v21 = *(_QWORD *)(a3 + 296);
      if ( v21 )
        v20 = *(_DWORD *)(v21 + 248) != 0;
      ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(a3 + 104) + 8LL));
      if ( *(_DWORD *)(a3 + 20) )
        goto LABEL_18;
      v35 = *(_QWORD *)(a3 + 328);
      if ( v35 )
      {
        if ( *(_QWORD *)(v35 + 24) )
          goto LABEL_18;
      }
      if ( !v20
        || (*(_BYTE *)(a1 + 12) & 4) != 0
        || (*(_DWORD *)(a2 + 512) & 0x1010000) != 0
        || (*(_BYTE *)(a4 + 4) & 2) != 0 )
      {
        goto LABEL_18;
      }
      v38 = 0;
      while ( 1 )
      {
        v39 = (_QWORD *)(a3 + 64);
        if ( v38 )
          v40 = (_QWORD *)v38[21];
        else
          v40 = (_QWORD *)*v39;
        v38 = v40 - 21;
        if ( v40 == v39 )
          v38 = 0;
        if ( !v38 )
          break;
        if ( *((_DWORD *)v38 + 64) == 128 )
        {
          v47 = (SECTION_OBJECT_POINTERS *)(v38[36] + 16LL);
          if ( v47->DataSectionObject )
          {
            if ( !MmCanFileBeTruncated(v47, &NtfsLarge0) )
              goto LABEL_18;
          }
        }
      }
      if ( (v56 & 2) != 0 )
      {
        v34 = 259;
        v55 = 259;
        v33 = a4;
      }
      else
      {
        NtfsWriteUsnCloseRecordAndCheckpointTransaction(a1, a3);
        *(_DWORD *)(a1 + 4) &= ~0x2000u;
        while ( 1 )
        {
          v41 = a1 + 152;
          v42 = *(_QWORD *)(a1 + 152);
          v43 = a3 + 80;
          if ( v42 == a1 + 152 )
            break;
          if ( v43 == v42 )
          {
            v44 = *(_QWORD *)v43;
            if ( *(_QWORD *)(*(_QWORD *)v43 + 8LL) != v43 )
              goto LABEL_61;
            v45 = *(_QWORD **)(a3 + 88);
            if ( *v45 != v43 )
              goto LABEL_61;
            *v45 = v44;
            *(_QWORD *)(v44 + 8) = v45;
            *(_QWORD *)v43 = 0;
          }
          else
          {
            NtfsReleaseFcbEx(a1, v42 - 80, 0);
          }
        }
        if ( !*(_QWORD *)v43 )
        {
          v37 = *(__int64 **)(a1 + 160);
          if ( *v37 != v41 )
            goto LABEL_61;
          *(_QWORD *)v43 = v41;
          *(_QWORD *)(a3 + 88) = v37;
          *v37 = v43;
          *(_QWORD *)(a1 + 160) = v43;
        }
LABEL_18:
        v11 = a2;
LABEL_19:
        if ( v19 )
        {
          LOBYTE(v18) = 1;
          NtfsWriteFileSizes(a1, v11, 0, v18, 1, 0);
          NtfsCheckpointCurrentTransaction(a1);
          *(_DWORD *)(v11 + 512) &= ~0x80000u;
        }
        if ( *(_DWORD *)(a1 + 28) )
          NtfsCheckpointCurrentTransaction(a1);
        if ( a6 )
        {
          v22 = *a5;
          v23 = *(_QWORD *)(v11 + 184);
          v56 = v23;
          if ( v22 )
          {
            if ( (*((_DWORD *)v22 + 2) & 1) != 0 )
            {
LABEL_26:
              v24 = 0;
              if ( v22 && (*((_DWORD *)v22 + 2) & 1) != 0 )
                _InterlockedAnd((volatile signed __int32 *)v22 + 2, 0xFFFFFFFE);
              if ( ExIsResourceAcquiredSharedLite((PERESOURCE)(*(_QWORD *)(v23 + 104) + 64LL)) )
              {
                v53 = 0;
              }
              else
              {
                LOBYTE(v26) = 1;
                v53 = NtfsAcquireResourceShared(v25, v23, v26);
              }
              v27 = a6 - 16;
              v28 = a2;
              v29 = *(_QWORD *)(a2 + 528);
              if ( v29 )
              {
                v24 = *(_QWORD *)(v29 + 64);
                ExAcquireResourceExclusiveLite(*(PERESOURCE *)(v24 + 136), 1u);
                v28 = a2;
              }
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v27 + 64), 0xFFFFFFFF) == 1
                && a6 != *(_QWORD *)(v28 + 288) + 16LL )
              {
                if ( (*(_DWORD *)(v27 + 68) & 1) != 0 )
                  *(_WORD *)v27 = 0;
                else
                  ExFreeToLookasideListEx(&NtfsScbNonpagedLookasideList, (PVOID)(a6 - 16));
                if ( v29 )
                {
                  v36 = *(_QWORD **)(v29 + 112);
                  if ( v36 )
                  {
                    if ( *v36 == v27 )
                    {
                      ExFreeToLookasideListEx(&TxfDefaultReaderSectionLookasideList, v36);
                      *(_QWORD *)(v29 + 112) = 0;
                    }
                  }
                }
              }
              if ( v24 )
                ExReleaseResourceLite(*(PERESOURCE *)(v24 + 136));
              if ( v53 )
              {
                if ( *(_WORD *)v56 == 1794 )
                  v46 = (struct _ERESOURCE *)(*(_QWORD *)(v56 + 104) + 64LL);
                else
                  v46 = *(struct _ERESOURCE **)(v56 + 8);
                ExReleaseResourceLite(v46);
              }
            }
          }
          else if ( (*(_DWORD *)(v23 + 4) & 4) == 0 )
          {
            goto LABEL_26;
          }
        }
        if ( *a5 )
        {
          ExAcquireFastMutex((PFAST_MUTEX)(*(_QWORD *)(a3 + 104) + 8LL));
          if ( *((_QWORD *)*a5 + 9) )
          {
            v30 = (__int64)(*a5 + 28);
            v31 = *(_QWORD *)v30;
            if ( *(_QWORD *)(*(_QWORD *)v30 + 8LL) != v30 || (v32 = (_QWORD *)*((_QWORD *)*a5 + 8), *v32 != v30) )
LABEL_61:
              __fastfail(3u);
            *v32 = v31;
            *(_QWORD *)(v31 + 8) = v32;
            *((_QWORD *)*a5 + 9) = 0;
          }
          ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(a3 + 104) + 8LL));
          NtfsDeleteCcb(a3, a5);
        }
        NtfsDecrementCloseCounts(a1, a2, a8, 0, (__int64)&v52);
        v33 = a4;
        v34 = v55;
        if ( a9 )
          _InterlockedDecrement((volatile signed __int32 *)(a4 + 4904));
      }
      if ( !v52 )
        NtfsReleaseFcbWithPaging(a1, a3);
      if ( v51 )
        NtfsReleaseVcbCheckDelete(a1, v33);
      else
        NtfsReleaseVcb(a1, v33);
      if ( v34 != 259 )
      {
        if ( NtfsStatusDebugFlags
          && v34
          && v34 != 294
          && v34 - 298 > 1
          && v34 < 0xFFFFFFED
          && v34 != -1073741802
          && v34 != -1073741807
          && v34 + 2147483643 > 1
          && v34 != -1073741608 )
        {
          NtfsStatusTraceAndDebugInternal(a1, v34, 526163);
        }
        LOBYTE(v48) = 1;
        NtfsExtendedCompleteRequestInternal(a1, 0, v34, v48, 1);
      }
      return v34;
    }
    NtfsReleaseFcbWithPaging(a1, a3);
    NtfsReleaseVcb(a1, v9);
  }
  if ( (*(_DWORD *)(a1 + 12) & 1) != 0 )
  {
    v13 = 0;
    v14 = 1;
  }
  else
  {
    v13 = 2;
    v14 = 0;
  }
  for ( i = *(_DWORD *)(a1 + 296); i; i = *(_DWORD *)(a1 + 296) )
  {
    v16 = i - 1;
    *(_DWORD *)(a1 + 296) = v16;
    v17 = *(void **)(a1 + 16LL * v16 + 312);
    if ( v17 )
    {
      CcUnpinData(v17);
      *(_QWORD *)(a1 + 16LL * *(unsigned int *)(a1 + 296) + 312) = 0;
    }
  }
  if ( ExAcquireResourceSharedLite((PERESOURCE)(a4 + 2160), v14) )
  {
    v9 = a4;
    goto LABEL_11;
  }
  if ( !v13 )
  {
    NtfsRaiseStatusInternal(a1, -1073741608, 0, 0, 1901753);
    __debugbreak();
  }
  return 259;
}

```

## disassembly

```asm
0x14013b870  mov     [rsp+arg_18], r9
0x14013b875  mov     [rsp+arg_10], r8
0x14013b87a  mov     [rsp+arg_8], rdx
0x14013b87f  mov     [rsp+arg_0], rcx
0x14013b884  push    rbx
0x14013b885  push    rsi
0x14013b886  push    rdi
0x14013b887  push    r12
0x14013b889  push    r13
0x14013b88b  push    r14
0x14013b88d  push    r15
0x14013b88f  sub     rsp, 60h
0x14013b893  mov     rdi, r9
0x14013b896  mov     r12, r8
0x14013b899  mov     r15, rdx
0x14013b89c  mov     rbx, rcx
0x14013b89f  mov     [rsp+98h+var_57], 0
0x14013b8a4  mov     [rsp+98h+var_56], 0
0x14013b8a9  xor     r13d, r13d
0x14013b8ac  mov     r14d, r13d
0x14013b8af  mov     [rsp+98h+var_50], r13d
0x14013b8b4  mov     eax, [rcx+0Ch]
0x14013b8b7  not     eax
0x14013b8b9  and     eax, 1
0x14013b8bc  lea     eax, ds:9[rax*2]
0x14013b8c3  mov     dword ptr [rsp+98h+var_48], eax
0x14013b8c7  test    dword ptr [rdi+4], 800h
0x14013b8ce  jnz     loc_14013C268
0x14013b8d4  mov     eax, [rbx+0Ch]
0x14013b8d7  test    al, 1
0x14013b8d9  jz      loc_14013C19E
0x14013b8df  mov     esi, r13d
0x14013b8e2  mov     dil, 1
0x14013b8e5  mov     eax, [rbx+128h]
0x14013b8eb  test    eax, eax
0x14013b8ed  jz      short loc_14013B931
0x14013b8ef  nop
0x14013b8f0  dec     eax
0x14013b8f2  mov     [rbx+128h], eax
0x14013b8f8  mov     ecx, eax
0x14013b8fa  add     rcx, rcx
0x14013b8fd  mov     rcx, [rbx+rcx*8+138h]; Bcb
0x14013b905  test    rcx, rcx
0x14013b908  jz      short loc_14013B927
0x14013b90a  call    cs:__imp_CcUnpinData
0x14013b911  nop     dword ptr [rax+rax+00h]
0x14013b916  mov     eax, [rbx+128h]
0x14013b91c  add     rax, rax
0x14013b91f  mov     [rbx+rax*8+138h], r13
0x14013b927  mov     eax, [rbx+128h]
0x14013b92d  test    eax, eax
0x14013b92f  jnz     short loc_14013B8F0
0x14013b931  mov     rcx, [rsp+98h+arg_18]
0x14013b939  add     rcx, 870h; Resource
0x14013b940  movzx   edx, dil; Wait
0x14013b944  call    cs:__imp_ExAcquireResourceSharedLite
0x14013b94b  nop     dword ptr [rax+rax+00h]
0x14013b950  test    al, al
0x14013b952  jz      loc_14013C240
0x14013b958  mov     rdi, [rsp+98h+arg_18]
0x14013b960  mov     r9d, dword ptr [rsp+98h+var_48]
0x14013b965  xor     r8d, r8d
0x14013b968  mov     rdx, r12
0x14013b96b  mov     rcx, rbx
0x14013b96e  call    NtfsAcquireExclusiveFcb
0x14013b973  test    al, al
0x14013b975  jz      loc_14013C284
0x14013b97b  xor     sil, sil
0x14013b97e  mov     [rsp+98h+var_54], 1
0x14013b983  mov     edx, [r15+200h]
0x14013b98a  mov     eax, edx
0x14013b98c  and     eax, 90000h
0x14013b991  cmp     eax, 80000h
0x14013b996  setz    cl
0x14013b999  test    byte ptr [rdi+4], 2
0x14013b99d  setz    al
0x14013b9a0  test    al, cl
0x14013b9a2  jnz     loc_1402C8444
0x14013b9a8  cmp     [rsp+98h+var_57], r13b
0x14013b9ad  jz      loc_14013C1AB
0x14013b9b3  mov     [rsp+98h+var_58], r13b
0x14013b9b8  xor     dil, dil
0x14013b9bb  or      dword ptr [rbx+0Ch], 1
0x14013b9bf  cmp     qword ptr [r12+128h], 0
0x14013b9c8  jz      loc_14013C07C
0x14013b9ce  mov     rcx, [r12+68h]
0x14013b9d3  add     rcx, 8; FastMutex
0x14013b9d7  call    cs:__imp_ExAcquireFastMutex
0x14013b9de  nop     dword ptr [rax+rax+00h]
0x14013b9e3  mov     [rsp+98h+var_58], 1
0x14013b9e8  mov     rax, [r12+128h]
0x14013b9f0  mov     r12d, 1
0x14013b9f6  test    rax, rax
0x14013b9f9  jz      short loc_14013BA0A
0x14013b9fb  movzx   edi, dil
0x14013b9ff  cmp     dword ptr [rax+0F8h], 0
0x14013ba06  cmovnz  edi, r12d
0x14013ba0a  mov     r15, [rsp+98h+arg_10]
0x14013ba12  mov     rcx, [r15+68h]
0x14013ba16  add     rcx, 8; FastMutex
0x14013ba1a  call    cs:__imp_ExReleaseFastMutex
0x14013ba21  nop     dword ptr [rax+rax+00h]
0x14013ba26  mov     [rsp+98h+var_58], 0
0x14013ba2b  mov     eax, [r15+14h]
0x14013ba2f  test    eax, eax
0x14013ba31  jz      loc_14013BD68
0x14013ba37  mov     r15, [rsp+98h+arg_8]
0x14013ba3f  test    sil, sil
0x14013ba42  jnz     loc_14013BC03
0x14013ba48  cmp     dword ptr [rbx+1Ch], 0
0x14013ba4c  jnz     loc_14013C087
0x14013ba52  mov     rdi, [rsp+98h+arg_28]
0x14013ba5a  mov     rsi, [rsp+98h+arg_20]
0x14013ba62  test    rdi, rdi
0x14013ba65  jz      loc_14013BB0A
0x14013ba6b  mov     rcx, [rsi]
0x14013ba6e  mov     r15, [r15+0B8h]
0x14013ba75  mov     [rsp+98h+var_48], r15
0x14013ba7a  test    rcx, rcx
0x14013ba7d  jz      loc_14013BDEA
0x14013ba83  mov     eax, [rcx+8]
0x14013ba86  test    al, 1
0x14013ba88  jz      loc_14013C027
0x14013ba8e  mov     r14, r13
0x14013ba91  test    rcx, rcx
0x14013ba94  jz      short loc_14013BAA2
0x14013ba96  mov     eax, [rcx+8]
0x14013ba99  test    al, 1
0x14013ba9b  jz      short loc_14013BAA2
0x14013ba9d  lock and dword ptr [rcx+8], 0FFFFFFFEh
0x14013baa2  mov     rcx, [r15+68h]
0x14013baa6  add     rcx, 40h ; '@'; Resource
0x14013baaa  call    cs:__imp_ExIsResourceAcquiredSharedLite
0x14013bab1  nop     dword ptr [rax+rax+00h]
0x14013bab6  test    eax, eax
0x14013bab8  jz      loc_14013BFFA
0x14013babe  mov     [rsp+98h+var_55], 0
0x14013bac3  lea     r15, [rdi-10h]
0x14013bac7  mov     rcx, [rsp+98h+arg_8]
0x14013bacf  mov     r13, [rcx+210h]
0x14013bad6  test    r13, r13
0x14013bad9  jnz     loc_14013BD2A
0x14013badf  mov     eax, 0FFFFFFFFh
0x14013bae4  lock xadd [r15+40h], eax
0x14013baea  cmp     eax, 1
0x14013baed  jz      loc_14013BD8D
0x14013baf3  test    r14, r14
0x14013baf6  jnz     loc_14013BD50
0x14013bafc  cmp     [rsp+98h+var_55], 0
0x14013bb01  jnz     loc_14013BFD2
0x14013bb07  xor     r13d, r13d
0x14013bb0a  mov     rax, [rsp+98h+arg_10]
0x14013bb12  mov     ecx, [rax+4]
0x14013bb15  test    cl, 4
0x14013bb18  jz      loc_14013BCEF
0x14013bb1e  mov     r14b, 1
0x14013bb21  mov     rax, [rsi]
0x14013bb24  test    rax, rax
0x14013bb27  jz      loc_14013BD22
0x14013bb2d  mov     rdi, [rax+48h]
0x14013bb31  mov     rax, [rsp+98h+arg_10]
0x14013bb39  mov     rcx, [rax+68h]
0x14013bb3d  add     rcx, 8; FastMutex
0x14013bb41  call    cs:__imp_ExAcquireFastMutex
0x14013bb48  nop     dword ptr [rax+rax+00h]
0x14013bb4d  mov     rax, [rsi]
0x14013bb50  cmp     qword ptr [rax+48h], 0
0x14013bb55  jz      short loc_14013BB83
0x14013bb57  add     rax, 38h ; '8'
0x14013bb5b  mov     rdx, [rax]
0x14013bb5e  cmp     [rdx+8], rax
0x14013bb62  jnz     loc_14013BE12
0x14013bb68  mov     rcx, [rax+8]
0x14013bb6c  cmp     [rcx], rax
0x14013bb6f  jnz     loc_14013BE12
0x14013bb75  mov     [rcx], rdx
0x14013bb78  mov     [rdx+8], rcx
0x14013bb7c  mov     rax, [rsi]
0x14013bb7f  mov     [rax+48h], r13
0x14013bb83  mov     r13, [rsp+98h+arg_10]
0x14013bb8b  mov     rcx, [r13+68h]
0x14013bb8f  add     rcx, 8; FastMutex
0x14013bb93  call    cs:__imp_ExReleaseFastMutex
0x14013bb9a  nop     dword ptr [rax+rax+00h]
0x14013bb9f  mov     rdx, rsi
0x14013bba2  mov     rcx, r13
0x14013bba5  call    NtfsDeleteCcb
0x14013bbaa  lea     rax, [rsp+98h+var_56]
0x14013bbaf  mov     [rsp+98h+var_68], rax
0x14013bbb4  mov     [rsp+98h+var_70], 0
0x14013bbb9  movzx   eax, [rsp+98h+arg_38]
0x14013bbc1  mov     byte ptr [rsp+98h+var_78], al
0x14013bbc5  movzx   r9d, r14b
0x14013bbc9  mov     r8, rdi
0x14013bbcc  mov     rdx, [rsp+98h+arg_8]
0x14013bbd4  mov     rcx, rbx
0x14013bbd7  call    NtfsDecrementCloseCounts
0x14013bbdc  mov     rsi, [rsp+98h+arg_18]
0x14013bbe4  mov     r14d, [rsp+98h+var_50]
0x14013bbe9  cmp     [rsp+98h+arg_40], 0
0x14013bbf1  jz      loc_14013C126
0x14013bbf7  lock dec dword ptr [rsi+1328h]
0x14013bbfe  jmp     loc_14013C126
0x14013bc03  mov     [rsp+98h+var_70], 0
0x14013bc08  mov     byte ptr [rsp+98h+var_78], 1
0x14013bc0d  mov     r9b, 1
0x14013bc10  xor     r8d, r8d
0x14013bc13  mov     rdx, r15
0x14013bc16  mov     rcx, rbx
0x14013bc19  call    NtfsWriteFileSizes
0x14013bc1e  mov     rcx, rbx
0x14013bc21  call    NtfsCheckpointCurrentTransaction
0x14013bc26  mov     eax, [r15+200h]
0x14013bc2d  btr     eax, 13h
0x14013bc31  mov     [r15+200h], eax
0x14013bc38  jmp     loc_14013BCD5
0x14013bc3d  mov     edx, eax
0x14013bc3f  movzx   ecx, cs:NtfsStatusDebugFlags
0x14013bc46  test    cl, cl
0x14013bc48  jz      short loc_14013BC99
0x14013bc4a  test    eax, eax
0x14013bc4c  jz      short loc_14013BC99
0x14013bc4e  cmp     eax, 126h
0x14013bc53  jz      short loc_14013BC99
0x14013bc55  lea     ecx, [rax-12Ah]
0x14013bc5b  cmp     ecx, 1
0x14013bc5e  jbe     short loc_14013BC99
0x14013bc60  cmp     eax, 0FFFFFFEDh
0x14013bc63  jnb     short loc_14013BC99
0x14013bc65  cmp     eax, 0C00000D8h
0x14013bc6a  jz      short loc_14013BC99
0x14013bc6c  cmp     eax, 0C0000016h
0x14013bc71  jz      short loc_14013BC99
0x14013bc73  cmp     eax, 0C0000011h
0x14013bc78  jz      short loc_14013BC99
0x14013bc7a  add     eax, 7FFFFFFBh
0x14013bc7f  cmp     eax, 1
0x14013bc82  jbe     short loc_14013BC99
0x14013bc84  cmp     edx, 103h
0x14013bc8a  jz      short loc_14013BC99
0x14013bc8c  xor     ecx, ecx
0x14013bc8e  mov     r8d, 806D2h
0x14013bc94  call    NtfsStatusTraceAndDebugInternal
0x14013bc99  mov     rbx, [rsp+98h+arg_0]
0x14013bca1  test    rbx, rbx
0x14013bca4  jz      short loc_14013BCB0
0x14013bca6  mov     eax, [rbx+4]
0x14013bca9  btr     eax, 8
0x14013bcad  mov     [rbx+4], eax
0x14013bcb0  movzx   eax, cs:NtfsStatusDebugFlags
0x14013bcb7  mov     [rsp+98h+var_50], 103h
0x14013bcbf  xor     r13d, r13d
0x14013bcc2  mov     r12d, 1
0x14013bcc8  mov     r14d, [rsp+98h+var_50]
0x14013bccd  mov     r15, [rsp+98h+arg_8]
0x14013bcd5  cmp     r14d, 103h
0x14013bcdc  jnz     loc_14013BA48
0x14013bce2  mov     rsi, [rsp+98h+arg_18]
0x14013bcea  jmp     loc_14013C126
0x14013bcef  cmp     [rsp+98h+arg_30], 5
0x14013bcf7  jz      loc_14013BB1E
0x14013bcfd  mov     rax, [rsi]
0x14013bd00  test    rax, rax
0x14013bd03  jz      short loc_14013BD1A
0x14013bd05  mov     eax, [rax+8]
0x14013bd08  test    al, 4
0x14013bd0a  jnz     loc_14013BB1E
0x14013bd10  bt      ecx, 1Eh
0x14013bd14  jb      loc_14013BB1E
0x14013bd1a  xor     r14b, r14b
0x14013bd1d  jmp     loc_14013BB21
0x14013bd22  mov     rdi, r13
0x14013bd25  jmp     loc_14013BBAA
0x14013bd2a  mov     r14, [r13+40h]
0x14013bd2e  mov     dl, 1; Wait
0x14013bd30  mov     rcx, [r14+88h]; Resource
0x14013bd37  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14013bd3e  nop     dword ptr [rax+rax+00h]
0x14013bd43  mov     rcx, [rsp+98h+arg_8]
0x14013bd4b  jmp     loc_14013BADF
0x14013bd50  mov     rcx, [r14+88h]; Resource
0x14013bd57  call    cs:__imp_ExReleaseResourceLite
0x14013bd5e  nop     dword ptr [rax+rax+00h]
0x14013bd63  jmp     loc_14013BAFC
0x14013bd68  mov     rax, [r15+148h]
0x14013bd6f  test    rax, rax
0x14013bd72  jz      short loc_14013BD7F
0x14013bd74  cmp     qword ptr [rax+18h], 0
0x14013bd79  jnz     loc_14013BA37
0x14013bd7f  test    dil, dil
0x14013bd82  jz      loc_14013BA37
0x14013bd88  jmp     loc_14013BE36
0x14013bd8d  mov     rax, [rcx+120h]
0x14013bd94  add     rax, 10h
0x14013bd98  cmp     rdi, rax
0x14013bd9b  jz      loc_14013BAF3
0x14013bda1  mov     eax, [r15+44h]
0x14013bda5  test    al, 1
0x14013bda7  jz      short loc_14013BE19
0x14013bda9  xor     edi, edi
  ... truncated ...
```
