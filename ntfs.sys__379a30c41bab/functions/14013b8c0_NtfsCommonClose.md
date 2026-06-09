# NtfsCommonClose

- ea: `0x14013b8c0`
- end: `0x14013c313`
- name: `NtfsCommonClose`
- size: `2643`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x14013a250`
- `0x14013af60`

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
- `0x14013b8c0`
- `0x14013c320`
- `0x1401403d0`
- `0x140187a00`
- `0x1401d2c84`
- `0x1401e7338`

## import_xrefs

- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14013bafa`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14013bafa`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1402a6f64`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1402a6f64`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14013be25`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14013be73`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14013be25`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14013be73`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14013bd87`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14013bd87`
- `ntoskrnl!CcUnpinData` at `0x14013b95a`
- `ntoskrnl!CcUnpinData` at `0x14013b95a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14013bda7`
- `ntoskrnl!ExReleaseResourceLite` at `0x14013c039`
- `ntoskrnl!ExReleaseResourceLite` at `0x14013bda7`
- `ntoskrnl!ExReleaseResourceLite` at `0x14013c039`
- `ntoskrnl!ExAcquireFastMutex` at `0x14013ba27`
- `ntoskrnl!ExAcquireFastMutex` at `0x14013bb91`
- `ntoskrnl!ExAcquireFastMutex` at `0x14013ba27`
- `ntoskrnl!ExAcquireFastMutex` at `0x14013bb91`
- `ntoskrnl!ExReleaseFastMutex` at `0x14013ba6a`
- `ntoskrnl!ExReleaseFastMutex` at `0x14013bbe3`
- `ntoskrnl!ExReleaseFastMutex` at `0x14013c2f8`
- `ntoskrnl!ExReleaseFastMutex` at `0x1402a6fff`
- `ntoskrnl!ExReleaseFastMutex` at `0x14013ba6a`
- `ntoskrnl!ExReleaseFastMutex` at `0x14013bbe3`
- `ntoskrnl!ExReleaseFastMutex` at `0x14013c2f8`
- `ntoskrnl!ExReleaseFastMutex` at `0x1402a6fff`
- `ntoskrnl!MmCanFileBeTruncated` at `0x14013c0a9`
- `ntoskrnl!MmCanFileBeTruncated` at `0x14013c0a9`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14013b994`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14013b994`

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
  __int64 v27; // r9
  __int64 v28; // r15
  __int64 v29; // rcx
  __int64 v30; // r13
  __int64 v31; // rax
  __int64 v32; // rdx
  _QWORD *v33; // rcx
  __int64 v34; // rsi
  unsigned int v35; // r14d
  __int64 v36; // rax
  _QWORD *v37; // rdx
  __int64 *v38; // rdx
  _QWORD *v39; // rdi
  _QWORD *v40; // rcx
  _QWORD *v41; // rax
  __int64 v42; // rcx
  __int64 v43; // rdx
  __int64 v44; // rax
  __int64 v45; // rcx
  _QWORD *v46; // rdx
  struct _ERESOURCE *v47; // rcx
  SECTION_OBJECT_POINTERS *v48; // rcx
  __int64 v49; // r9
  int v51; // eax
  char v52; // [rsp+41h] [rbp-57h]
  char v53; // [rsp+42h] [rbp-56h] BYREF
  char v54; // [rsp+43h] [rbp-55h]
  char v55; // [rsp+44h] [rbp-54h]
  int v56; // [rsp+48h] [rbp-50h]
  __int64 v57; // [rsp+50h] [rbp-48h]

  v9 = a4;
  v11 = a2;
  v52 = 0;
  v53 = 0;
  v56 = 0;
  LODWORD(v57) = 2 * ((*(_DWORD *)(a1 + 12) & 1) == 0) + 9;
  while ( (*(_DWORD *)(v9 + 4) & 0x800) != 0 )
  {
    if ( !(unsigned __int8)NtfsAcquireExclusiveVcb(a1, v9, 0) )
      return 259;
    v52 = 1;
LABEL_11:
    if ( !(unsigned __int8)NtfsAcquireExclusiveFcb(a1, a3, 0, (unsigned int)v57) )
      goto LABEL_116;
    v19 = 0;
    v55 = 1;
    if ( (*(_DWORD *)(v11 + 512) & 0x90000) == 0x80000
      && (*(_BYTE *)(v9 + 4) & 2) == 0
      && *(_WORD *)(a3 + 188)
      && (*(_DWORD *)(v11 + 512) & 0x1000040) == 0 )
    {
      NtfsReleaseFcbEx(a1, a3, 0);
      *(_DWORD *)(a1 + 4) |= 0x10000u;
      if ( !(unsigned __int8)NtfsAcquireFcbWithPaging(a1, a3, 0, (unsigned int)v57) )
      {
LABEL_116:
        NtfsReleaseVcb(a1, v9);
        return 259;
      }
      v55 = 1;
      v51 = *(_DWORD *)(v11 + 512);
      if ( (v51 & 0x80000) != 0 && *(_WORD *)(a3 + 188) )
        v19 = (v51 & 0x1000040) == 0;
    }
    if ( v52 || (*(_DWORD *)(v9 + 4) & 0x800) == 0 )
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
      v36 = *(_QWORD *)(a3 + 328);
      if ( v36 )
      {
        if ( *(_QWORD *)(v36 + 24) )
          goto LABEL_18;
      }
      if ( !v20
        || (*(_BYTE *)(a1 + 12) & 4) != 0
        || (*(_DWORD *)(a2 + 512) & 0x1010000) != 0
        || (*(_BYTE *)(a4 + 4) & 2) != 0 )
      {
        goto LABEL_18;
      }
      v39 = 0;
      while ( 1 )
      {
        v40 = (_QWORD *)(a3 + 64);
        if ( v39 )
          v41 = (_QWORD *)v39[21];
        else
          v41 = (_QWORD *)*v40;
        v39 = v41 - 21;
        if ( v41 == v40 )
          v39 = 0;
        if ( !v39 )
          break;
        if ( *((_DWORD *)v39 + 64) == 128 )
        {
          v48 = (SECTION_OBJECT_POINTERS *)(v39[36] + 16LL);
          if ( v48->DataSectionObject )
          {
            if ( !MmCanFileBeTruncated(v48, &NtfsLarge0) )
              goto LABEL_18;
          }
        }
      }
      if ( (v57 & 2) != 0 )
      {
        v35 = 259;
        v56 = 259;
        v34 = a4;
      }
      else
      {
        NtfsWriteUsnCloseRecordAndCheckpointTransaction(a1, a3);
        *(_DWORD *)(a1 + 4) &= ~0x2000u;
        while ( 1 )
        {
          v42 = a1 + 152;
          v43 = *(_QWORD *)(a1 + 152);
          v44 = a3 + 80;
          if ( v43 == a1 + 152 )
            break;
          if ( v44 == v43 )
          {
            v45 = *(_QWORD *)v44;
            if ( *(_QWORD *)(*(_QWORD *)v44 + 8LL) != v44 )
              goto LABEL_61;
            v46 = *(_QWORD **)(a3 + 88);
            if ( *v46 != v44 )
              goto LABEL_61;
            *v46 = v45;
            *(_QWORD *)(v45 + 8) = v46;
            *(_QWORD *)v44 = 0;
          }
          else
          {
            NtfsReleaseFcbEx(a1, v43 - 80, 0);
          }
        }
        if ( !*(_QWORD *)v44 )
        {
          v38 = *(__int64 **)(a1 + 160);
          if ( *v38 != v42 )
            goto LABEL_61;
          *(_QWORD *)v44 = v42;
          *(_QWORD *)(a3 + 88) = v38;
          *v38 = v44;
          *(_QWORD *)(a1 + 160) = v44;
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
          v57 = v23;
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
                v54 = 0;
              }
              else
              {
                LOBYTE(v26) = 1;
                v54 = NtfsAcquireResourceShared(v25, v23, v26, v27);
              }
              v28 = a6 - 16;
              v29 = a2;
              v30 = *(_QWORD *)(a2 + 528);
              if ( v30 )
              {
                v24 = *(_QWORD *)(v30 + 64);
                ExAcquireResourceExclusiveLite(*(PERESOURCE *)(v24 + 136), 1u);
                v29 = a2;
              }
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v28 + 64), 0xFFFFFFFF) == 1
                && a6 != *(_QWORD *)(v29 + 288) + 16LL )
              {
                if ( (*(_DWORD *)(v28 + 68) & 1) != 0 )
                  *(_WORD *)v28 = 0;
                else
                  ExFreeToLookasideListEx(&NtfsScbNonpagedLookasideList, (PVOID)(a6 - 16));
                if ( v30 )
                {
                  v37 = *(_QWORD **)(v30 + 112);
                  if ( v37 )
                  {
                    if ( *v37 == v28 )
                    {
                      ExFreeToLookasideListEx(&TxfDefaultReaderSectionLookasideList, v37);
                      *(_QWORD *)(v30 + 112) = 0;
                    }
                  }
                }
              }
              if ( v24 )
                ExReleaseResourceLite(*(PERESOURCE *)(v24 + 136));
              if ( v54 )
              {
                if ( *(_WORD *)v57 == 1794 )
                  v47 = (struct _ERESOURCE *)(*(_QWORD *)(v57 + 104) + 64LL);
                else
                  v47 = *(struct _ERESOURCE **)(v57 + 8);
                ExReleaseResourceLite(v47);
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
            v31 = (__int64)(*a5 + 28);
            v32 = *(_QWORD *)v31;
            if ( *(_QWORD *)(*(_QWORD *)v31 + 8LL) != v31 || (v33 = (_QWORD *)*((_QWORD *)*a5 + 8), *v33 != v31) )
LABEL_61:
              __fastfail(3u);
            *v33 = v32;
            *(_QWORD *)(v32 + 8) = v33;
            *((_QWORD *)*a5 + 9) = 0;
          }
          ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(a3 + 104) + 8LL));
          NtfsDeleteCcb(a3, a5);
        }
        NtfsDecrementCloseCounts(a1, a2, a8, 0, (__int64)&v53);
        v34 = a4;
        v35 = v56;
        if ( a9 )
          _InterlockedDecrement((volatile signed __int32 *)(a4 + 4904));
      }
      if ( !v53 )
        NtfsReleaseFcbWithPaging(a1, a3);
      if ( v52 )
        NtfsReleaseVcbCheckDelete(a1, v34);
      else
        NtfsReleaseVcb(a1, v34);
      if ( v35 != 259 )
      {
        if ( NtfsStatusDebugFlags
          && v35
          && v35 != 294
          && v35 - 298 > 1
          && v35 < 0xFFFFFFED
          && v35 != -1073741802
          && v35 != -1073741807
          && v35 + 2147483643 > 1
          && v35 != -1073741608 )
        {
          NtfsStatusTraceAndDebugInternal(a1, v35, 526163);
        }
        LOBYTE(v49) = 1;
        NtfsExtendedCompleteRequestInternal(a1, 0, v35, v49, 1);
      }
      return v35;
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
0x14013b8c0  mov     [rsp+arg_18], r9
0x14013b8c5  mov     [rsp+arg_10], r8
0x14013b8ca  mov     [rsp+arg_8], rdx
0x14013b8cf  mov     [rsp+arg_0], rcx
0x14013b8d4  push    rbx
0x14013b8d5  push    rsi
0x14013b8d6  push    rdi
0x14013b8d7  push    r12
0x14013b8d9  push    r13
0x14013b8db  push    r14
0x14013b8dd  push    r15
0x14013b8df  sub     rsp, 60h
0x14013b8e3  mov     rdi, r9
0x14013b8e6  mov     r12, r8
0x14013b8e9  mov     r15, rdx
0x14013b8ec  mov     rbx, rcx
0x14013b8ef  mov     [rsp+98h+var_57], 0
0x14013b8f4  mov     [rsp+98h+var_56], 0
0x14013b8f9  xor     r13d, r13d
0x14013b8fc  mov     r14d, r13d
0x14013b8ff  mov     [rsp+98h+var_50], r13d
0x14013b904  mov     eax, [rcx+0Ch]
0x14013b907  not     eax
0x14013b909  and     eax, 1
0x14013b90c  lea     eax, ds:9[rax*2]
0x14013b913  mov     dword ptr [rsp+98h+var_48], eax
0x14013b917  test    dword ptr [rdi+4], 800h
0x14013b91e  jnz     loc_14013C2B8
0x14013b924  mov     eax, [rbx+0Ch]
0x14013b927  test    al, 1
0x14013b929  jz      loc_14013C1EE
0x14013b92f  mov     esi, r13d
0x14013b932  mov     dil, 1
0x14013b935  mov     eax, [rbx+128h]
0x14013b93b  test    eax, eax
0x14013b93d  jz      short loc_14013B981
0x14013b93f  nop
0x14013b940  dec     eax
0x14013b942  mov     [rbx+128h], eax
0x14013b948  mov     ecx, eax
0x14013b94a  add     rcx, rcx
0x14013b94d  mov     rcx, [rbx+rcx*8+138h]; Bcb
0x14013b955  test    rcx, rcx
0x14013b958  jz      short loc_14013B977
0x14013b95a  call    cs:__imp_CcUnpinData
0x14013b961  nop     dword ptr [rax+rax+00h]
0x14013b966  mov     eax, [rbx+128h]
0x14013b96c  add     rax, rax
0x14013b96f  mov     [rbx+rax*8+138h], r13
0x14013b977  mov     eax, [rbx+128h]
0x14013b97d  test    eax, eax
0x14013b97f  jnz     short loc_14013B940
0x14013b981  mov     rcx, [rsp+98h+arg_18]
0x14013b989  add     rcx, 870h; Resource
0x14013b990  movzx   edx, dil; Wait
0x14013b994  call    cs:__imp_ExAcquireResourceSharedLite
0x14013b99b  nop     dword ptr [rax+rax+00h]
0x14013b9a0  test    al, al
0x14013b9a2  jz      loc_14013C290
0x14013b9a8  mov     rdi, [rsp+98h+arg_18]
0x14013b9b0  mov     r9d, dword ptr [rsp+98h+var_48]
0x14013b9b5  xor     r8d, r8d
0x14013b9b8  mov     rdx, r12
0x14013b9bb  mov     rcx, rbx
0x14013b9be  call    NtfsAcquireExclusiveFcb
0x14013b9c3  test    al, al
0x14013b9c5  jz      loc_14013C2D4
0x14013b9cb  xor     sil, sil
0x14013b9ce  mov     [rsp+98h+var_54], 1
0x14013b9d3  mov     edx, [r15+200h]
0x14013b9da  mov     eax, edx
0x14013b9dc  and     eax, 90000h
0x14013b9e1  cmp     eax, 80000h
0x14013b9e6  setz    cl
0x14013b9e9  test    byte ptr [rdi+4], 2
0x14013b9ed  setz    al
0x14013b9f0  test    al, cl
0x14013b9f2  jnz     loc_1402C8494
0x14013b9f8  cmp     [rsp+98h+var_57], r13b
0x14013b9fd  jz      loc_14013C1FB
0x14013ba03  mov     [rsp+98h+var_58], r13b
0x14013ba08  xor     dil, dil
0x14013ba0b  or      dword ptr [rbx+0Ch], 1
0x14013ba0f  cmp     qword ptr [r12+128h], 0
0x14013ba18  jz      loc_14013C0CC
0x14013ba1e  mov     rcx, [r12+68h]
0x14013ba23  add     rcx, 8; FastMutex
0x14013ba27  call    cs:__imp_ExAcquireFastMutex
0x14013ba2e  nop     dword ptr [rax+rax+00h]
0x14013ba33  mov     [rsp+98h+var_58], 1
0x14013ba38  mov     rax, [r12+128h]
0x14013ba40  mov     r12d, 1
0x14013ba46  test    rax, rax
0x14013ba49  jz      short loc_14013BA5A
0x14013ba4b  movzx   edi, dil
0x14013ba4f  cmp     dword ptr [rax+0F8h], 0
0x14013ba56  cmovnz  edi, r12d
0x14013ba5a  mov     r15, [rsp+98h+arg_10]
0x14013ba62  mov     rcx, [r15+68h]
0x14013ba66  add     rcx, 8; FastMutex
0x14013ba6a  call    cs:__imp_ExReleaseFastMutex
0x14013ba71  nop     dword ptr [rax+rax+00h]
0x14013ba76  mov     [rsp+98h+var_58], 0
0x14013ba7b  mov     eax, [r15+14h]
0x14013ba7f  test    eax, eax
0x14013ba81  jz      loc_14013BDB8
0x14013ba87  mov     r15, [rsp+98h+arg_8]
0x14013ba8f  test    sil, sil
0x14013ba92  jnz     loc_14013BC53
0x14013ba98  cmp     dword ptr [rbx+1Ch], 0
0x14013ba9c  jnz     loc_14013C0D7
0x14013baa2  mov     rdi, [rsp+98h+arg_28]
0x14013baaa  mov     rsi, [rsp+98h+arg_20]
0x14013bab2  test    rdi, rdi
0x14013bab5  jz      loc_14013BB5A
0x14013babb  mov     rcx, [rsi]
0x14013babe  mov     r15, [r15+0B8h]
0x14013bac5  mov     [rsp+98h+var_48], r15
0x14013baca  test    rcx, rcx
0x14013bacd  jz      loc_14013BE3A
0x14013bad3  mov     eax, [rcx+8]
0x14013bad6  test    al, 1
0x14013bad8  jz      loc_14013C077
0x14013bade  mov     r14, r13
0x14013bae1  test    rcx, rcx
0x14013bae4  jz      short loc_14013BAF2
0x14013bae6  mov     eax, [rcx+8]
0x14013bae9  test    al, 1
0x14013baeb  jz      short loc_14013BAF2
0x14013baed  lock and dword ptr [rcx+8], 0FFFFFFFEh
0x14013baf2  mov     rcx, [r15+68h]
0x14013baf6  add     rcx, 40h ; '@'; Resource
0x14013bafa  call    cs:__imp_ExIsResourceAcquiredSharedLite
0x14013bb01  nop     dword ptr [rax+rax+00h]
0x14013bb06  test    eax, eax
0x14013bb08  jz      loc_14013C04A
0x14013bb0e  mov     [rsp+98h+var_55], 0
0x14013bb13  lea     r15, [rdi-10h]
0x14013bb17  mov     rcx, [rsp+98h+arg_8]
0x14013bb1f  mov     r13, [rcx+210h]
0x14013bb26  test    r13, r13
0x14013bb29  jnz     loc_14013BD7A
0x14013bb2f  mov     eax, 0FFFFFFFFh
0x14013bb34  lock xadd [r15+40h], eax
0x14013bb3a  cmp     eax, 1
0x14013bb3d  jz      loc_14013BDDD
0x14013bb43  test    r14, r14
0x14013bb46  jnz     loc_14013BDA0
0x14013bb4c  cmp     [rsp+98h+var_55], 0
0x14013bb51  jnz     loc_14013C022
0x14013bb57  xor     r13d, r13d
0x14013bb5a  mov     rax, [rsp+98h+arg_10]
0x14013bb62  mov     ecx, [rax+4]
0x14013bb65  test    cl, 4
0x14013bb68  jz      loc_14013BD3F
0x14013bb6e  mov     r14b, 1
0x14013bb71  mov     rax, [rsi]
0x14013bb74  test    rax, rax
0x14013bb77  jz      loc_14013BD72
0x14013bb7d  mov     rdi, [rax+48h]
0x14013bb81  mov     rax, [rsp+98h+arg_10]
0x14013bb89  mov     rcx, [rax+68h]
0x14013bb8d  add     rcx, 8; FastMutex
0x14013bb91  call    cs:__imp_ExAcquireFastMutex
0x14013bb98  nop     dword ptr [rax+rax+00h]
0x14013bb9d  mov     rax, [rsi]
0x14013bba0  cmp     qword ptr [rax+48h], 0
0x14013bba5  jz      short loc_14013BBD3
0x14013bba7  add     rax, 38h ; '8'
0x14013bbab  mov     rdx, [rax]
0x14013bbae  cmp     [rdx+8], rax
0x14013bbb2  jnz     loc_14013BE62
0x14013bbb8  mov     rcx, [rax+8]
0x14013bbbc  cmp     [rcx], rax
0x14013bbbf  jnz     loc_14013BE62
0x14013bbc5  mov     [rcx], rdx
0x14013bbc8  mov     [rdx+8], rcx
0x14013bbcc  mov     rax, [rsi]
0x14013bbcf  mov     [rax+48h], r13
0x14013bbd3  mov     r13, [rsp+98h+arg_10]
0x14013bbdb  mov     rcx, [r13+68h]
0x14013bbdf  add     rcx, 8; FastMutex
0x14013bbe3  call    cs:__imp_ExReleaseFastMutex
0x14013bbea  nop     dword ptr [rax+rax+00h]
0x14013bbef  mov     rdx, rsi
0x14013bbf2  mov     rcx, r13
0x14013bbf5  call    NtfsDeleteCcb
0x14013bbfa  lea     rax, [rsp+98h+var_56]
0x14013bbff  mov     [rsp+98h+var_68], rax
0x14013bc04  mov     [rsp+98h+var_70], 0
0x14013bc09  movzx   eax, [rsp+98h+arg_38]
0x14013bc11  mov     byte ptr [rsp+98h+var_78], al
0x14013bc15  movzx   r9d, r14b
0x14013bc19  mov     r8, rdi
0x14013bc1c  mov     rdx, [rsp+98h+arg_8]
0x14013bc24  mov     rcx, rbx
0x14013bc27  call    NtfsDecrementCloseCounts
0x14013bc2c  mov     rsi, [rsp+98h+arg_18]
0x14013bc34  mov     r14d, [rsp+98h+var_50]
0x14013bc39  cmp     [rsp+98h+arg_40], 0
0x14013bc41  jz      loc_14013C176
0x14013bc47  lock dec dword ptr [rsi+1328h]
0x14013bc4e  jmp     loc_14013C176
0x14013bc53  mov     [rsp+98h+var_70], 0
0x14013bc58  mov     byte ptr [rsp+98h+var_78], 1
0x14013bc5d  mov     r9b, 1
0x14013bc60  xor     r8d, r8d
0x14013bc63  mov     rdx, r15
0x14013bc66  mov     rcx, rbx
0x14013bc69  call    NtfsWriteFileSizes
0x14013bc6e  mov     rcx, rbx
0x14013bc71  call    NtfsCheckpointCurrentTransaction
0x14013bc76  mov     eax, [r15+200h]
0x14013bc7d  btr     eax, 13h
0x14013bc81  mov     [r15+200h], eax
0x14013bc88  jmp     loc_14013BD25
0x14013bc8d  mov     edx, eax
0x14013bc8f  movzx   ecx, cs:NtfsStatusDebugFlags
0x14013bc96  test    cl, cl
0x14013bc98  jz      short loc_14013BCE9
0x14013bc9a  test    eax, eax
0x14013bc9c  jz      short loc_14013BCE9
0x14013bc9e  cmp     eax, 126h
0x14013bca3  jz      short loc_14013BCE9
0x14013bca5  lea     ecx, [rax-12Ah]
0x14013bcab  cmp     ecx, 1
0x14013bcae  jbe     short loc_14013BCE9
0x14013bcb0  cmp     eax, 0FFFFFFEDh
0x14013bcb3  jnb     short loc_14013BCE9
0x14013bcb5  cmp     eax, 0C00000D8h
0x14013bcba  jz      short loc_14013BCE9
0x14013bcbc  cmp     eax, 0C0000016h
0x14013bcc1  jz      short loc_14013BCE9
0x14013bcc3  cmp     eax, 0C0000011h
0x14013bcc8  jz      short loc_14013BCE9
0x14013bcca  add     eax, 7FFFFFFBh
0x14013bccf  cmp     eax, 1
0x14013bcd2  jbe     short loc_14013BCE9
0x14013bcd4  cmp     edx, 103h
0x14013bcda  jz      short loc_14013BCE9
0x14013bcdc  xor     ecx, ecx
0x14013bcde  mov     r8d, 806D2h
0x14013bce4  call    NtfsStatusTraceAndDebugInternal
0x14013bce9  mov     rbx, [rsp+98h+arg_0]
0x14013bcf1  test    rbx, rbx
0x14013bcf4  jz      short loc_14013BD00
0x14013bcf6  mov     eax, [rbx+4]
0x14013bcf9  btr     eax, 8
0x14013bcfd  mov     [rbx+4], eax
0x14013bd00  movzx   eax, cs:NtfsStatusDebugFlags
0x14013bd07  mov     [rsp+98h+var_50], 103h
0x14013bd0f  xor     r13d, r13d
0x14013bd12  mov     r12d, 1
0x14013bd18  mov     r14d, [rsp+98h+var_50]
0x14013bd1d  mov     r15, [rsp+98h+arg_8]
0x14013bd25  cmp     r14d, 103h
0x14013bd2c  jnz     loc_14013BA98
0x14013bd32  mov     rsi, [rsp+98h+arg_18]
0x14013bd3a  jmp     loc_14013C176
0x14013bd3f  cmp     [rsp+98h+arg_30], 5
0x14013bd47  jz      loc_14013BB6E
0x14013bd4d  mov     rax, [rsi]
0x14013bd50  test    rax, rax
0x14013bd53  jz      short loc_14013BD6A
0x14013bd55  mov     eax, [rax+8]
0x14013bd58  test    al, 4
0x14013bd5a  jnz     loc_14013BB6E
0x14013bd60  bt      ecx, 1Eh
0x14013bd64  jb      loc_14013BB6E
0x14013bd6a  xor     r14b, r14b
0x14013bd6d  jmp     loc_14013BB71
0x14013bd72  mov     rdi, r13
0x14013bd75  jmp     loc_14013BBFA
0x14013bd7a  mov     r14, [r13+40h]
0x14013bd7e  mov     dl, 1; Wait
0x14013bd80  mov     rcx, [r14+88h]; Resource
0x14013bd87  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14013bd8e  nop     dword ptr [rax+rax+00h]
0x14013bd93  mov     rcx, [rsp+98h+arg_8]
0x14013bd9b  jmp     loc_14013BB2F
0x14013bda0  mov     rcx, [r14+88h]; Resource
0x14013bda7  call    cs:__imp_ExReleaseResourceLite
0x14013bdae  nop     dword ptr [rax+rax+00h]
0x14013bdb3  jmp     loc_14013BB4C
0x14013bdb8  mov     rax, [r15+148h]
0x14013bdbf  test    rax, rax
0x14013bdc2  jz      short loc_14013BDCF
0x14013bdc4  cmp     qword ptr [rax+18h], 0
0x14013bdc9  jnz     loc_14013BA87
0x14013bdcf  test    dil, dil
0x14013bdd2  jz      loc_14013BA87
0x14013bdd8  jmp     loc_14013BE86
0x14013bddd  mov     rax, [rcx+120h]
0x14013bde4  add     rax, 10h
0x14013bde8  cmp     rdi, rax
0x14013bdeb  jz      loc_14013BB43
0x14013bdf1  mov     eax, [r15+44h]
0x14013bdf5  test    al, 1
0x14013bdf7  jz      short loc_14013BE69
0x14013bdf9  xor     edi, edi
  ... truncated ...
```
