# NtfsReleaseAllResources

- ea: `0x14000d840`
- end: `0x14000e158`
- name: `NtfsReleaseAllResources`
- size: `2328`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `10`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x1400cafac`
- `0x140109ea8`
- `0x14010f570`
- `0x140134aa8`
- `0x1401aa72c`
- `0x1401aaeb0`
- `0x1401ba744`
- `0x1401f6448`
- `0x1402266e0`
- `0x140288558`

## callees

- `0x14000d840`
- `0x14000e220`
- `0x14000ea70`
- `0x140059740`
- `0x14025125c`

## import_xrefs

- `ntoskrnl!FsRtlReleaseEofLock` at `0x14000d916`
- `ntoskrnl!FsRtlReleaseEofLock` at `0x14000d916`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x14000da9a`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x14000de28`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x14000df33`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x14000da9a`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x14000de28`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x14000df33`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x14000da74`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x14000de02`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x14000df09`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x14000da74`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x14000de02`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x14000df09`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14000dcec`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14000dd46`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14000dcec`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14000dd46`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000dadd`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000de6b`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000df76`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000dadd`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000de6b`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000df76`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e00c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e00c`
- `ntoskrnl!CcUnpinData` at `0x14000d87a`
- `ntoskrnl!CcUnpinData` at `0x14000d87a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000d9e0`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000db9e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000dc01`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000dc5b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000e0e5`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000d9e0`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000db9e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000dc01`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000dc5b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000e0e5`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14000dbd8`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14000dc35`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14000dbd8`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14000dc35`

## pseudocode

```c
__int64 *__fastcall NtfsReleaseAllResources(__int64 a1)
{
  int i; // eax
  unsigned int v3; // eax
  void *v4; // rcx
  __int64 v5; // rcx
  int v6; // eax
  __int64 v7; // rsi
  __int64 j; // rdi
  __int64 v9; // rbp
  __int64 **v10; // rsi
  __int64 v11; // r8
  __int64 *result; // rax
  __int64 v13; // rcx
  __int64 *v14; // rdi
  __int64 **v15; // rdx
  _QWORD *v16; // r15
  _QWORD *v17; // rax
  _QWORD *v18; // rbp
  struct _ERESOURCE *v19; // rcx
  _QWORD *v20; // r14
  _QWORD *v21; // r12
  _QWORD *k; // rax
  __int64 v23; // rcx
  _QWORD *v24; // rax
  _QWORD *v25; // rcx
  _QWORD *v26; // rdi
  int v27; // esi
  __int64 v28; // rcx
  void *v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rcx
  struct _ERESOURCE *v32; // rcx
  struct _ERESOURCE *v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // r8
  _QWORD *v36; // r15
  _QWORD *v37; // rax
  __int64 v38; // r13
  _QWORD *v39; // rbp
  __int64 v40; // r8
  _QWORD *v41; // rsi
  _QWORD *v42; // rax
  _QWORD *v43; // rbp
  _QWORD *v44; // r14
  _QWORD *v45; // r15
  _QWORD *v46; // rax
  __int64 v47; // rcx
  _QWORD *v48; // rcx
  _QWORD *v49; // rax
  _QWORD *v50; // r12
  _QWORD *v51; // r14
  _QWORD *v52; // rax
  __int64 v53; // rcx
  _QWORD *v54; // rcx
  _QWORD *v55; // rax
  __int64 v56; // rdx
  __int64 v57; // rdx

  for ( i = *(_DWORD *)(a1 + 296); i; i = *(_DWORD *)(a1 + 296) )
  {
    v3 = i - 1;
    *(_DWORD *)(a1 + 296) = v3;
    v4 = *(void **)(a1 + 16LL * v3 + 312);
    if ( v4 )
    {
      CcUnpinData(v4);
      *(_QWORD *)(a1 + 16LL * *(unsigned int *)(a1 + 296) + 312) = 0;
    }
  }
  v5 = *(_QWORD *)(a1 + 104);
  if ( v5 && (*(_DWORD *)(a1 + 4) & 0x20000) != 0 )
  {
    ExReleaseResourceLite((PERESOURCE)(v5 + 10688));
    *(_DWORD *)(a1 + 4) &= ~0x20000u;
  }
  v6 = *(unsigned __int16 *)(a1 + 34);
  if ( !(_WORD)v6 )
    goto LABEL_9;
  v26 = *(_QWORD **)(a1 + 40);
  if ( v6 == 1 )
  {
    if ( v26 )
    {
      if ( *(_WORD *)v26 == 1805 )
      {
        NtfsReleaseQuotaControl(a1, *(_QWORD *)(a1 + 40));
        *(_QWORD *)(a1 + 40) = 0;
        *(_WORD *)(a1 + 34) = 0;
        goto LABEL_9;
      }
      if ( ExIsResourceAcquiredExclusiveLite((PERESOURCE)(v26[13] + 64LL)) )
      {
        if ( ExIsResourceAcquiredSharedLite((PERESOURCE)(v26[13] + 64LL)) == 1 )
        {
          v41 = (_QWORD *)(a1 + 280);
          v42 = *(_QWORD **)(a1 + 280);
          if ( v42 != (_QWORD *)(a1 + 280) )
          {
            v43 = 0;
            while ( v42 != v41 )
            {
              if ( *((_WORD *)v42 - 4) == 1831 )
              {
                v43 = v42 - 1;
                break;
              }
              v42 = (_QWORD *)*v42;
            }
            if ( v43 )
            {
              while ( 1 )
              {
                v44 = v43 + 1;
                v45 = 0;
                if ( (_QWORD *)*v41 != v41 )
                {
                  v46 = (_QWORD *)*v44;
                  v40 = 1831;
                  while ( 1 )
                  {
                    v44 = v43 + 1;
                    if ( v46 == v41 )
                      break;
                    if ( *((_WORD *)v46 - 4) == 1831 )
                    {
                      v45 = v46 - 1;
                      break;
                    }
                    v46 = (_QWORD *)*v46;
                  }
                }
                v47 = v43[10];
                if ( v47 )
                {
                  if ( *(_QWORD **)(v47 + 184) != v26 )
                    goto LABEL_117;
                  if ( (*(_DWORD *)(v47 + 200) & 0x2000) != 0 || (*(_DWORD *)(v47 + 512) & 0x4040) != 0 )
                  {
                    if ( *(_DWORD *)(v47 + 256) == 256 && (*(_DWORD *)(v47 + 512) & 0x40) != 0 )
                      *(_DWORD *)(v47 + 256) = 0;
                    v57 = v43[10];
                    if ( (*(_DWORD *)(v57 + 200) & 0x2000) != 0 || (*(_DWORD *)(v57 + 512) & 0x4000) != 0 )
                    {
                      ClearFlagInterlocked(v57 + 200, 0x2000);
                      *(_DWORD *)(v43[10] + 512LL) &= ~0x4000u;
                    }
                  }
                  FsRtlAcquireHeaderMutex(v43[10] + 120LL, v43[10] + 160LL, v40);
                  *(_QWORD *)(v43[10] + 496LL) = 0;
                  FsRtlReleaseHeaderMutex(v43[10] + 120LL, v43[10] + 160LL);
                }
                v48 = (_QWORD *)*v44;
                if ( *(_QWORD **)(*v44 + 8LL) != v44 || (v49 = (_QWORD *)v44[1], (_QWORD *)*v49 != v44) )
LABEL_61:
                  __fastfail(3u);
                *v49 = v48;
                v48[1] = v49;
                if ( v43 != (_QWORD *)(a1 + 552) )
                  ExFreeToLookasideListEx(&NtfsScbSnapshotLookasideList, v43);
LABEL_117:
                if ( !v45 )
                  break;
                v43 = v45;
              }
            }
          }
        }
      }
      if ( *(_WORD *)v26 == 1794 )
        v33 = (struct _ERESOURCE *)(v26[13] + 64LL);
      else
        v33 = (struct _ERESOURCE *)v26[1];
      ExReleaseResourceLite(v33);
    }
    *(_QWORD *)(a1 + 40) = 0;
    *(_WORD *)(a1 + 34) = 0;
    goto LABEL_9;
  }
  v27 = *(unsigned __int16 *)(a1 + 34);
  while ( 1 )
  {
    v28 = *v26;
    if ( !*v26 )
      goto LABEL_57;
    if ( *(_WORD *)v28 == 1805 )
    {
      NtfsReleaseQuotaControl(a1, *v26);
      *v26 = 0;
      goto LABEL_57;
    }
    if ( ExIsResourceAcquiredExclusiveLite((PERESOURCE)(*(_QWORD *)(v28 + 104) + 64LL)) )
    {
      if ( ExIsResourceAcquiredSharedLite((PERESOURCE)(*(_QWORD *)(*v26 + 104LL) + 64LL)) == 1 )
      {
        v36 = (_QWORD *)(a1 + 280);
        v37 = *(_QWORD **)(a1 + 280);
        if ( v37 != (_QWORD *)(a1 + 280) )
        {
          v38 = *v26;
          v39 = 0;
          while ( v37 != v36 )
          {
            if ( *((_WORD *)v37 - 4) == 1831 )
            {
              v39 = v37 - 1;
              break;
            }
            v37 = (_QWORD *)*v37;
          }
          if ( v39 )
          {
            do
            {
              v50 = 0;
              v51 = v39 + 1;
              if ( (_QWORD *)*v36 != v36 )
              {
                v52 = (_QWORD *)*v51;
                v35 = 1831;
                while ( 1 )
                {
                  v51 = v39 + 1;
                  if ( v52 == v36 )
                    break;
                  if ( *((_WORD *)v52 - 4) == 1831 )
                  {
                    v50 = v52 - 1;
                    break;
                  }
                  v52 = (_QWORD *)*v52;
                }
              }
              v53 = v39[10];
              if ( v53 )
              {
                if ( v38 && *(_QWORD *)(v53 + 184) != v38 )
                  goto LABEL_134;
                if ( (*(_DWORD *)(v53 + 200) & 0x2000) != 0 || (*(_DWORD *)(v53 + 512) & 0x4040) != 0 )
                {
                  if ( *(_DWORD *)(v53 + 256) == 256 && (*(_DWORD *)(v53 + 512) & 0x40) != 0 )
                    *(_DWORD *)(v53 + 256) = 0;
                  v56 = v39[10];
                  if ( (*(_DWORD *)(v56 + 200) & 0x2000) != 0 || (*(_DWORD *)(v56 + 512) & 0x4000) != 0 )
                  {
                    ClearFlagInterlocked(v56 + 200, 0x2000);
                    *(_DWORD *)(v39[10] + 512LL) &= ~0x4000u;
                  }
                }
                FsRtlAcquireHeaderMutex(v39[10] + 120LL, v39[10] + 160LL, v35);
                *(_QWORD *)(v39[10] + 496LL) = 0;
                FsRtlReleaseHeaderMutex(v39[10] + 120LL, v39[10] + 160LL);
              }
              v54 = (_QWORD *)*v51;
              if ( *(_QWORD **)(*v51 + 8LL) != v51 )
                goto LABEL_61;
              v55 = (_QWORD *)v51[1];
              if ( (_QWORD *)*v55 != v51 )
                goto LABEL_61;
              *v55 = v54;
              v54[1] = v55;
              if ( v39 != (_QWORD *)(a1 + 552) )
                ExFreeToLookasideListEx(&NtfsScbSnapshotLookasideList, v39);
LABEL_134:
              v39 = v50;
            }
            while ( v50 );
          }
        }
      }
    }
    v31 = *v26;
    v32 = *(_WORD *)*v26 == 1794
        ? (struct _ERESOURCE *)(*(_QWORD *)(v31 + 104) + 64LL)
        : *(struct _ERESOURCE **)(v31 + 8);
    ExReleaseResourceLite(v32);
    *v26 = 0;
LABEL_57:
    if ( !--v27 )
      break;
    ++v26;
  }
  v29 = *(void **)(a1 + 40);
  if ( *(_BYTE *)(a1 + 32) == 18 )
  {
    memset(v29, 0, 8LL * *(unsigned __int16 *)(a1 + 34));
  }
  else
  {
    ExFreePoolWithTag(v29, 0);
    *(_QWORD *)(a1 + 40) = 0;
    *(_WORD *)(a1 + 34) = 0;
  }
LABEL_9:
  v7 = *(_QWORD *)(a1 + 64);
  for ( j = 0; j != 2; ++j )
  {
    v9 = *(_QWORD *)(a1 + 8 * j + 48);
    if ( v9 )
    {
      if ( *(_WORD *)v9 == 1794 )
        v30 = *(_QWORD *)(a1 + 8 * j + 48);
      else
        v30 = *(_QWORD *)(v9 + 184);
      ExReleaseResourceLite(*(PERESOURCE *)(v30 + 112));
      if ( *(_QWORD *)(a1 + 48) == v9 )
        *(_QWORD *)(a1 + 48) = 0;
      if ( *(_QWORD *)(a1 + 56) == v9 )
        *(_QWORD *)(a1 + 56) = 0;
    }
  }
  if ( v7 )
  {
    *(_QWORD *)(a1 + 64) = 0;
    FsRtlReleaseEofLock(v7 + 120, v7 + 160);
    *(_QWORD *)(a1 + 64) = 0;
  }
  if ( *(_QWORD *)(a1 + 80) )
  {
    NtfsReleaseRangeInternal(a1 + 72);
    *(_QWORD *)(a1 + 80) = 0;
  }
  *(_DWORD *)(a1 + 4) &= ~0x2000u;
  v10 = (__int64 **)(a1 + 152);
LABEL_17:
  v11 = 0xFFFF;
  while ( 1 )
  {
    result = *v10;
    if ( *v10 == (__int64 *)v10 )
      return result;
    v13 = *result;
    v14 = result - 10;
    if ( !*result )
      goto LABEL_33;
    if ( *((_WORD *)v14 + 16) != 1 )
      goto LABEL_32;
    if ( !*(_DWORD *)(a1 + 28) )
    {
      if ( *(__int64 **)(v13 + 8) != result )
        goto LABEL_61;
      v15 = (__int64 **)result[1];
      if ( *v15 != result )
        goto LABEL_61;
      *v15 = (__int64 *)v13;
      v16 = (_QWORD *)(a1 + 280);
      *(_QWORD *)(v13 + 8) = v15;
      *result = 0;
      v17 = *(_QWORD **)(a1 + 280);
      if ( v17 != (_QWORD *)(a1 + 280) )
      {
        v18 = 0;
        while ( v17 != v16 )
        {
          if ( *((_WORD *)v17 - 4) == 1831 )
          {
            v18 = v17 - 1;
            break;
          }
          v17 = (_QWORD *)*v17;
        }
        if ( v18 )
        {
          do
          {
            v20 = v18 + 1;
            v21 = 0;
            if ( (_QWORD *)*v16 != v16 )
            {
              for ( k = (_QWORD *)*v20; ; k = (_QWORD *)*k )
              {
                v20 = v18 + 1;
                if ( k == v16 )
                  break;
                v11 = 1831;
                if ( *((_WORD *)k - 4) == 1831 )
                {
                  v21 = k - 1;
                  break;
                }
              }
            }
            v23 = v18[10];
            if ( v23 )
            {
              if ( *(__int64 **)(v23 + 184) != v14 )
                goto LABEL_50;
              if ( (*(_DWORD *)(v23 + 200) & 0x2000) != 0 || (*(_DWORD *)(v23 + 512) & 0x4040) != 0 )
              {
                if ( *(_DWORD *)(v23 + 256) == 256 && (*(_DWORD *)(v23 + 512) & 0x40) != 0 )
                  *(_DWORD *)(v23 + 256) = 0;
                v34 = v18[10];
                if ( (*(_DWORD *)(v34 + 200) & 0x2000) != 0 || (*(_DWORD *)(v34 + 512) & 0x4000) != 0 )
                {
                  if ( (*(_DWORD *)(v34 + 200) & 0x2000) != 0 )
                    _InterlockedAnd((volatile signed __int32 *)(v34 + 200), 0xFFFFDFFF);
                  *(_DWORD *)(v18[10] + 512LL) &= ~0x4000u;
                }
              }
              FsRtlAcquireHeaderMutex(v18[10] + 120LL, v18[10] + 160LL, v11);
              *(_QWORD *)(v18[10] + 496LL) = 0;
              FsRtlReleaseHeaderMutex(v18[10] + 120LL, v18[10] + 160LL);
            }
            v24 = (_QWORD *)*v20;
            if ( *(_QWORD **)(*v20 + 8LL) != v20 )
              goto LABEL_61;
            v25 = (_QWORD *)v20[1];
            if ( (_QWORD *)*v25 != v20 )
              goto LABEL_61;
            *v25 = v24;
            v24[1] = v25;
            if ( v18 != (_QWORD *)(a1 + 552) )
              ExFreeToLookasideListEx(&NtfsScbSnapshotLookasideList, v18);
LABEL_50:
            v18 = v21;
          }
          while ( v21 );
        }
      }
      if ( *((int *)v14 + 44) < 0 )
        *(_DWORD *)(a1 + 436) &= ~0x8000u;
LABEL_32:
      --*((_WORD *)v14 + 16);
LABEL_33:
      if ( *(_WORD *)v14 == 1794 )
        v19 = (struct _ERESOURCE *)(v14[13] + 64);
      else
        v19 = (struct _ERESOURCE *)v14[1];
      ExReleaseResourceLite(v19);
      goto LABEL_17;
    }
  }
}

```

## disassembly

```asm
0x14000d840  push    rbx
0x14000d842  push    r12
0x14000d844  push    r13
0x14000d846  push    r14
0x14000d848  sub     rsp, 28h
0x14000d84c  mov     eax, [rcx+128h]
0x14000d852  xor     r13d, r13d
0x14000d855  mov     rbx, rcx
0x14000d858  test    eax, eax
0x14000d85a  jz      short loc_14000D8A1
0x14000d85c  nop     dword ptr [rax+00h]
0x14000d860  dec     eax
0x14000d862  mov     ecx, eax
0x14000d864  add     rcx, rcx
0x14000d867  mov     [rbx+128h], eax
0x14000d86d  mov     rcx, [rbx+rcx*8+138h]; Bcb
0x14000d875  test    rcx, rcx
0x14000d878  jz      short loc_14000D897
0x14000d87a  call    cs:__imp_CcUnpinData
0x14000d881  nop     dword ptr [rax+rax+00h]
0x14000d886  mov     eax, [rbx+128h]
0x14000d88c  add     rax, rax
0x14000d88f  mov     [rbx+rax*8+138h], r13
0x14000d897  mov     eax, [rbx+128h]
0x14000d89d  test    eax, eax
0x14000d89f  jnz     short loc_14000D860
0x14000d8a1  mov     rcx, [rbx+68h]
0x14000d8a5  test    rcx, rcx
0x14000d8a8  jz      short loc_14000D8B7
0x14000d8aa  test    dword ptr [rbx+4], 20000h
0x14000d8b1  jnz     loc_14000E0DE
0x14000d8b7  movzx   eax, word ptr [rbx+22h]
0x14000d8bb  mov     r14d, 727h
0x14000d8c1  mov     [rsp+48h+arg_0], rbp
0x14000d8c6  mov     r12d, 702h
0x14000d8cc  mov     [rsp+48h+arg_8], rsi
0x14000d8d1  mov     [rsp+48h+arg_10], rdi
0x14000d8d6  mov     [rsp+48h+var_28], r15
0x14000d8db  test    ax, ax
0x14000d8de  jnz     loc_14000DB2F
0x14000d8e4  mov     rsi, [rbx+40h]
0x14000d8e8  mov     rdi, r13
0x14000d8eb  mov     rbp, [rbx+rdi*8+30h]
0x14000d8f0  test    rbp, rbp
0x14000d8f3  jnz     loc_14000DB88
0x14000d8f9  inc     rdi
0x14000d8fc  cmp     rdi, 2
0x14000d900  jnz     short loc_14000D8EB
0x14000d902  test    rsi, rsi
0x14000d905  jz      short loc_14000D926
0x14000d907  lea     rdx, [rsi+0A0h]
0x14000d90e  mov     [rbx+40h], r13
0x14000d912  lea     rcx, [rsi+78h]
0x14000d916  call    cs:__imp_FsRtlReleaseEofLock
0x14000d91d  nop     dword ptr [rax+rax+00h]
0x14000d922  mov     [rbx+40h], r13
0x14000d926  cmp     qword ptr [rbx+50h], 0
0x14000d92b  jnz     loc_14000DF9F
0x14000d931  and     dword ptr [rbx+4], 0FFFFDFFFh
0x14000d938  lea     rsi, [rbx+98h]
0x14000d93f  mov     r8d, 0FFFFh
0x14000d945  mov     rax, [rsi]
0x14000d948  cmp     rax, rsi
0x14000d94b  jz      loc_14000DB06
0x14000d951  mov     rcx, [rax]
0x14000d954  lea     rdi, [rax-50h]
0x14000d958  test    rcx, rcx
0x14000d95b  jz      short loc_14000D9CE
0x14000d95d  cmp     word ptr [rdi+20h], 1
0x14000d962  jnz     short loc_14000D9C9
0x14000d964  cmp     dword ptr [rbx+1Ch], 0
0x14000d968  jnz     short loc_14000D945
0x14000d96a  cmp     [rcx+8], rax
0x14000d96e  jnz     loc_14000DB79
0x14000d974  mov     rdx, [rax+8]
0x14000d978  cmp     [rdx], rax
0x14000d97b  jnz     loc_14000DB79
0x14000d981  mov     [rdx], rcx
0x14000d984  lea     r15, [rbx+118h]
0x14000d98b  mov     [rcx+8], rdx
0x14000d98f  mov     [rax], r13
0x14000d992  mov     rax, [r15]
0x14000d995  cmp     rax, r15
0x14000d998  jz      short loc_14000D9B6
0x14000d99a  mov     rbp, r13
0x14000d99d  cmp     rax, r15
0x14000d9a0  jz      short loc_14000D9B1
0x14000d9a2  cmp     [rax-8], r14w
0x14000d9a7  jnz     loc_14000DB27
0x14000d9ad  lea     rbp, [rax-8]
0x14000d9b1  test    rbp, rbp
0x14000d9b4  jnz     short loc_14000DA00
0x14000d9b6  cmp     dword ptr [rdi+0B0h], 0
0x14000d9bd  jge     short loc_14000D9C9
0x14000d9bf  and     dword ptr [rbx+1B4h], 0FFFF7FFFh
0x14000d9c9  add     [rdi+20h], r8w
0x14000d9ce  cmp     r12w, [rdi]
0x14000d9d2  jnz     loc_14000DFD2
0x14000d9d8  mov     rcx, [rdi+68h]
0x14000d9dc  add     rcx, 40h ; '@'; Resource
0x14000d9e0  call    cs:__imp_ExReleaseResourceLite
0x14000d9e7  nop     dword ptr [rax+rax+00h]
0x14000d9ec  mov     r14d, 727h
0x14000d9f2  jmp     loc_14000D93F
0x14000da00  lea     r14, [rbp+8]
0x14000da04  mov     r12, r13
0x14000da07  cmp     [r15], r15
0x14000da0a  jz      short loc_14000DA2F
0x14000da0c  mov     rax, [r14]
0x14000da0f  mov     rdx, r14
0x14000da12  mov     r14, rdx
0x14000da15  cmp     rax, r15
0x14000da18  jz      short loc_14000DA2F
0x14000da1a  mov     r8d, 727h
0x14000da20  cmp     [rax-8], r8w
0x14000da25  jnz     loc_14000DB80
0x14000da2b  lea     r12, [rax-8]
0x14000da2f  mov     rcx, [rbp+50h]
0x14000da33  test    rcx, rcx
0x14000da36  jz      short loc_14000DAA6
0x14000da38  cmp     [rcx+0B8h], rdi
0x14000da3f  jnz     loc_14000DAE9
0x14000da45  test    dword ptr [rcx+0C8h], 2000h
0x14000da4f  jnz     loc_14000DC75
0x14000da55  test    dword ptr [rcx+200h], 4040h
0x14000da5f  jnz     loc_14000DC75
0x14000da65  mov     rcx, [rbp+50h]
0x14000da69  lea     rdx, [rcx+0A0h]
0x14000da70  add     rcx, 78h ; 'x'
0x14000da74  call    cs:__imp_FsRtlAcquireHeaderMutex
0x14000da7b  nop     dword ptr [rax+rax+00h]
0x14000da80  mov     rax, [rbp+50h]
0x14000da84  mov     [rax+1F0h], r13
0x14000da8b  mov     rcx, [rbp+50h]
0x14000da8f  lea     rdx, [rcx+0A0h]
0x14000da96  add     rcx, 78h ; 'x'
0x14000da9a  call    cs:__imp_FsRtlReleaseHeaderMutex
0x14000daa1  nop     dword ptr [rax+rax+00h]
0x14000daa6  mov     rax, [r14]
0x14000daa9  cmp     [rax+8], r14
0x14000daad  jnz     loc_14000DB79
0x14000dab3  mov     rcx, [r14+8]
0x14000dab7  cmp     [rcx], r14
0x14000daba  jnz     loc_14000DB79
0x14000dac0  mov     [rcx], rax
0x14000dac3  mov     [rax+8], rcx
0x14000dac7  lea     rax, [rbx+228h]
0x14000dace  cmp     rbp, rax
0x14000dad1  jz      short loc_14000DAE9
0x14000dad3  mov     rdx, rbp; Entry
0x14000dad6  lea     rcx, NtfsScbSnapshotLookasideList; Lookaside
0x14000dadd  call    cs:__imp_ExFreeToLookasideListEx
0x14000dae4  nop     dword ptr [rax+rax+00h]
0x14000dae9  mov     rbp, r12
0x14000daec  test    r12, r12
0x14000daef  jnz     loc_14000DA00
0x14000daf5  mov     r12d, 702h
0x14000dafb  mov     r8d, 0FFFFh
0x14000db01  jmp     loc_14000D9B6
0x14000db06  mov     r15, [rsp+48h+var_28]
0x14000db0b  mov     rdi, [rsp+48h+arg_10]
0x14000db10  mov     rsi, [rsp+48h+arg_8]
0x14000db15  mov     rbp, [rsp+48h+arg_0]
0x14000db1a  add     rsp, 28h
0x14000db1e  pop     r14
0x14000db20  pop     r13
0x14000db22  pop     r12
0x14000db24  pop     rbx
0x14000db25  retn
0x14000db27  mov     rax, [rax]
0x14000db2a  jmp     loc_14000D99D
0x14000db2f  mov     rdi, [rbx+28h]
0x14000db33  cmp     eax, 1
0x14000db36  jz      loc_14000DC1A
0x14000db3c  mov     esi, eax
0x14000db3e  mov     eax, 70Dh
0x14000db43  mov     rcx, [rdi]
0x14000db46  test    rcx, rcx
0x14000db49  jnz     short loc_14000DBC7
0x14000db4b  add     esi, 0FFFFFFFFh
0x14000db4e  jz      short loc_14000DB56
0x14000db50  add     rdi, 8
0x14000db54  jmp     short loc_14000DB43
0x14000db56  mov     rcx, [rbx+28h]; void *
0x14000db5a  xor     edx, edx; Val
0x14000db5c  cmp     byte ptr [rbx+20h], 12h
0x14000db60  jnz     loc_14000E00C
0x14000db66  movzx   r8d, word ptr [rbx+22h]
0x14000db6b  shl     r8, 3; Size
0x14000db6f  call    memset
0x14000db74  jmp     loc_14000D8E4
0x14000db79  mov     ecx, 3
0x14000db7e  int     29h; Win8: RtlFailFast(ecx)
0x14000db80  mov     rax, [rax]
0x14000db83  jmp     loc_14000DA12
0x14000db88  cmp     r12w, [rbp+0]
0x14000db8d  jz      loc_14000DCD9
0x14000db93  mov     rcx, [rbp+0B8h]
0x14000db9a  mov     rcx, [rcx+70h]; Resource
0x14000db9e  call    cs:__imp_ExReleaseResourceLite
0x14000dba5  nop     dword ptr [rax+rax+00h]
0x14000dbaa  cmp     [rbx+30h], rbp
0x14000dbae  jnz     short loc_14000DBB4
0x14000dbb0  mov     [rbx+30h], r13
0x14000dbb4  cmp     [rbx+38h], rbp
0x14000dbb8  jnz     loc_14000D8F9
0x14000dbbe  mov     [rbx+38h], r13
0x14000dbc2  jmp     loc_14000D8F9
0x14000dbc7  cmp     [rcx], ax
0x14000dbca  jz      loc_14000DFB1
0x14000dbd0  mov     rcx, [rcx+68h]
0x14000dbd4  add     rcx, 40h ; '@'; Resource
0x14000dbd8  call    cs:__imp_ExIsResourceAcquiredExclusiveLite
0x14000dbdf  nop     dword ptr [rax+rax+00h]
0x14000dbe4  test    al, al
0x14000dbe6  jnz     loc_14000DCE1
0x14000dbec  mov     rcx, [rdi]
0x14000dbef  cmp     r12w, [rcx]
0x14000dbf3  jnz     loc_14000DFC9
0x14000dbf9  mov     rcx, [rcx+68h]
0x14000dbfd  add     rcx, 40h ; '@'; Resource
0x14000dc01  call    cs:__imp_ExReleaseResourceLite
0x14000dc08  nop     dword ptr [rax+rax+00h]
0x14000dc0d  mov     eax, 70Dh
0x14000dc12  mov     [rdi], r13
0x14000dc15  jmp     loc_14000DB4B
0x14000dc1a  test    rdi, rdi
0x14000dc1d  jz      short loc_14000DC67
0x14000dc1f  mov     eax, 70Dh
0x14000dc24  cmp     [rdi], ax
0x14000dc27  jz      loc_14000DFEB
0x14000dc2d  mov     rcx, [rdi+68h]
0x14000dc31  add     rcx, 40h ; '@'; Resource
0x14000dc35  call    cs:__imp_ExIsResourceAcquiredExclusiveLite
0x14000dc3c  nop     dword ptr [rax+rax+00h]
0x14000dc41  test    al, al
0x14000dc43  jnz     loc_14000DD3E
0x14000dc49  cmp     r12w, [rdi]
0x14000dc4d  jnz     loc_14000E118
0x14000dc53  mov     rcx, [rdi+68h]
0x14000dc57  add     rcx, 40h ; '@'; Resource
0x14000dc5b  call    cs:__imp_ExReleaseResourceLite
0x14000dc62  nop     dword ptr [rax+rax+00h]
0x14000dc67  mov     [rbx+28h], r13
0x14000dc6b  mov     [rbx+22h], r13w
0x14000dc70  jmp     loc_14000D8E4
0x14000dc75  cmp     dword ptr [rcx+100h], 100h
0x14000dc7f  jz      loc_14000E13E
0x14000dc85  mov     rcx, [rbp+50h]
0x14000dc89  test    dword ptr [rcx+0C8h], 2000h
0x14000dc93  jnz     short loc_14000DCA5
0x14000dc95  test    dword ptr [rcx+200h], 4000h
0x14000dc9f  jz      loc_14000DA65
0x14000dca5  mov     eax, [rcx+0C8h]
0x14000dcab  bt      eax, 0Dh
0x14000dcaf  jnb     short loc_14000DCBC
0x14000dcb1  lock and dword ptr [rcx+0C8h], 0FFFFDFFFh
0x14000dcbc  mov     rax, [rbp+50h]
0x14000dcc0  mov     ecx, [rax+200h]
0x14000dcc6  mov     rax, [rbp+50h]
0x14000dcca  btr     ecx, 0Eh
0x14000dcce  mov     [rax+200h], ecx
0x14000dcd4  jmp     loc_14000DA65
0x14000dcd9  mov     rcx, rbp
0x14000dcdc  jmp     loc_14000DB9A
0x14000dce1  mov     rax, [rdi]
0x14000dce4  mov     rcx, [rax+68h]
0x14000dce8  add     rcx, 40h ; '@'; Resource
0x14000dcec  call    cs:__imp_ExIsResourceAcquiredSharedLite
0x14000dcf3  nop     dword ptr [rax+rax+00h]
0x14000dcf8  cmp     eax, 1
0x14000dcfb  jnz     loc_14000DBEC
0x14000dd01  lea     r15, [rbx+118h]
0x14000dd08  mov     rax, [r15]
0x14000dd0b  cmp     rax, r15
0x14000dd0e  jz      loc_14000DBEC
0x14000dd14  mov     r13, [rdi]
0x14000dd17  xor     ebp, ebp
0x14000dd19  cmp     rax, r15
0x14000dd1c  jz      short loc_14000DD2D
0x14000dd1e  cmp     [rax-8], r14w
0x14000dd23  jnz     loc_14000DFDB
0x14000dd29  lea     rbp, [rax-8]
0x14000dd2d  test    rbp, rbp
0x14000dd30  jnz     loc_14000DE90
0x14000dd36  xor     r13d, r13d
0x14000dd39  jmp     loc_14000DBEC
0x14000dd3e  mov     rcx, [rdi+68h]
0x14000dd42  add     rcx, 40h ; '@'; Resource
0x14000dd46  call    cs:__imp_ExIsResourceAcquiredSharedLite
0x14000dd4d  nop     dword ptr [rax+rax+00h]
0x14000dd52  cmp     eax, 1
0x14000dd55  jnz     loc_14000DC49
0x14000dd5b  lea     rsi, [rbx+118h]
0x14000dd62  mov     rax, [rsi]
0x14000dd65  cmp     rax, rsi
0x14000dd68  jz      loc_14000DC49
0x14000dd6e  mov     rbp, r13
0x14000dd71  cmp     rax, rsi
0x14000dd74  jz      short loc_14000DD85
  ... truncated ...
```
