# TxfFreeVersionInTopsStream

- ea: `0x14029afbc`
- end: `0x14029b552`
- name: `TxfFreeVersionInTopsStream`
- size: `1430`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400bc404`
- `0x140188ee0`
- `0x1401d4d18`
- `0x1401d4f40`
- `0x1401d53dc`

## callees

- `0x1400f86cc`
- `0x140100b14`
- `0x14020bb70`
- `0x14029afbc`

## import_xrefs

- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x14029b1f3`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x14029b260`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x14029b1f3`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x14029b260`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x14029b24f`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x14029b24f`
- `ntoskrnl!RtlIsGenericTableEmptyAvl` at `0x14029b05d`
- `ntoskrnl!RtlIsGenericTableEmptyAvl` at `0x14029b11e`
- `ntoskrnl!RtlIsGenericTableEmptyAvl` at `0x14029b05d`
- `ntoskrnl!RtlIsGenericTableEmptyAvl` at `0x14029b11e`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14029b15f`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14029b30f`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14029b421`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14029b43a`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14029b15f`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14029b30f`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14029b421`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14029b43a`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14029b456`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14029b456`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14029b397`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14029b397`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14029b19e`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14029b46b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14029b4bd`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14029b19e`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14029b46b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14029b4bd`
- `ntoskrnl!ExReleaseResourceLite` at `0x14029b1d0`
- `ntoskrnl!ExReleaseResourceLite` at `0x14029b32f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14029b34b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14029b509`
- `ntoskrnl!ExReleaseResourceLite` at `0x14029b526`
- `ntoskrnl!ExReleaseResourceLite` at `0x14029b1d0`
- `ntoskrnl!ExReleaseResourceLite` at `0x14029b32f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14029b34b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14029b509`
- `ntoskrnl!ExReleaseResourceLite` at `0x14029b526`
- `ntoskrnl!ExAcquireFastMutex` at `0x14029b010`
- `ntoskrnl!ExAcquireFastMutex` at `0x14029b010`
- `ntoskrnl!ExReleaseFastMutex` at `0x14029b047`
- `ntoskrnl!ExReleaseFastMutex` at `0x14029b047`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x14029b0cf`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x14029b0cf`

## pseudocode

```c
char __fastcall TxfFreeVersionInTopsStream(__int64 a1, __int64 a2, __int64 a3, int a4, char a5, char a6)
{
  __int64 v10; // r13
  int v11; // eax
  char v12; // r14
  signed __int32 v13; // eax
  __int64 v14; // rdi
  bool v15; // bp
  _QWORD *v16; // rdi
  int v17; // r12d
  __int64 v18; // r8
  _DWORD *i; // r14
  int v20; // r9d
  __int64 v21; // r12
  _QWORD *v22; // rdi
  unsigned int v23; // r15d
  int v24; // r9d
  __int64 v25; // r8
  _QWORD *v26; // rdi
  _QWORD *v27; // r14
  __int64 v28; // rax
  _QWORD *v29; // rax
  __int64 v30; // rcx
  _QWORD *v31; // rdx
  _QWORD *v32; // r8
  CLFS_LSN plsn1; // [rsp+30h] [rbp-48h] BYREF
  __int64 v35; // [rsp+38h] [rbp-40h] BYREF
  int v36; // [rsp+88h] [rbp+10h]
  __int64 v37; // [rsp+90h] [rbp+18h] BYREF

  if ( a2 )
    v10 = *(_QWORD *)(a2 + 64);
  else
    v10 = 0;
  v11 = *(_DWORD *)(a3 + 8);
  plsn1.ullOffset = 0;
  if ( (v11 & 0x20) == 0 )
  {
    v12 = 0;
    ExAcquireFastMutex(*(PFAST_MUTEX *)(a3 + 256));
    _InterlockedOr((volatile signed __int32 *)(a3 + 8), 0x800u);
    if ( _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 132), 4, 4) == 3 )
      _InterlockedOr((volatile signed __int32 *)(a3 + 8), 0x80000u);
    ExReleaseFastMutex(*(PFAST_MUTEX *)(a3 + 256));
    if ( RtlIsGenericTableEmptyAvl((PRTL_AVL_TABLE)(a3 + 152)) && !*(_QWORD *)(a3 + 288) )
    {
      while ( 1 )
      {
        v16 = *(_QWORD **)(a3 + 296);
        if ( !v16 )
          break;
        if ( *v16 )
        {
          TxfDereferenceTxfQuotaControlBlock(*(_QWORD *)(a1 + 16), *v16, 0);
          *v16 = 0;
        }
        *(_QWORD *)(a3 + 296) = v16[3];
        ExFreeToLookasideListEx(&TxfVscbQuotaInfoLookasideList, v16);
      }
      _InterlockedOr((volatile signed __int32 *)(a3 + 8), 0x28u);
      return v12;
    }
    if ( !a2
      || (v13 = _InterlockedExchangeAdd((volatile signed __int32 *)(a2 + 44), 1u),
          _InterlockedDecrement((volatile signed __int32 *)(a2 + 44)),
          !v13)
      || a4 )
    {
      v14 = 0;
      v37 = 0;
      plsn1.ullOffset = _InterlockedCompareExchange64(
                          (volatile signed __int64 *)(a1 + 408),
                          NtfsLarge0.QuadPart,
                          NtfsLarge0.QuadPart);
      v15 = ClfsLsnGreater(&plsn1, (const CLFS_LSN *)(a3 + 280))
         || a5
         || _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 132), 4, 4) == 1
         && (*(_DWORD *)(a3 + 8) & 0x200) != 0
         || _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 132), 4, 4) == 3
         || RtlIsGenericTableEmptyAvl((PRTL_AVL_TABLE)(a3 + 152));
      v17 = *(_DWORD *)(a3 + 8) & 8;
      v36 = v17;
      ExAcquireResourceExclusiveLite(*(PERESOURCE *)(a1 + 368), 1u);
      if ( v17 )
      {
        if ( !v15 )
        {
LABEL_43:
          ExReleaseResourceLite(*(PERESOURCE *)(a1 + 368));
          if ( !v17 )
          {
            ExReleaseResourceLite(*(PERESOURCE *)(*(_QWORD *)(a1 + 280) + 16LL));
            _InterlockedOr((volatile signed __int32 *)(a3 + 8), 8u);
          }
          v14 = v37;
          if ( v15 )
            _InterlockedOr((volatile signed __int32 *)(a3 + 8), 0x20u);
          goto LABEL_47;
        }
      }
      else
      {
        LOBYTE(v18) = a6;
        if ( !(unsigned __int8)NtfsAcquireScbPagingResourceExclusive(0, *(_QWORD *)(a1 + 280), v18) )
        {
          ExReleaseResourceLite(*(PERESOURCE *)(a1 + 368));
          v15 = 0;
LABEL_47:
          if ( *(_QWORD *)(a3 + 296) && (v15 || v14) )
          {
            ExAcquireFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(a1 + 16) + 6312LL));
            v26 = *(_QWORD **)(a3 + 296);
            v27 = 0;
            while ( v26 )
            {
              if ( *v26 )
                *(_QWORD *)(*v26 + 16LL) -= v26[2] << 12;
              v26[2] = 0;
              if ( v15 || !v26[1] )
              {
                if ( *v26 )
                {
                  LOBYTE(v25) = 1;
                  *(_QWORD *)(*v26 + 16LL) -= v26[1] << 12;
                  TxfDereferenceTxfQuotaControlBlock(*(_QWORD *)(a1 + 16), *v26, v25);
                  *v26 = 0;
                }
                v28 = v26[3];
                if ( v27 )
                {
                  v27[3] = v28;
                  ExFreeToLookasideListEx(&TxfVscbQuotaInfoLookasideList, v26);
                }
                else
                {
                  *(_QWORD *)(a3 + 296) = v28;
                  ExFreeToLookasideListEx(&TxfVscbQuotaInfoLookasideList, v26);
                  v26 = *(_QWORD **)(a3 + 296);
                }
              }
              else
              {
                v27 = v26;
                v26 = (_QWORD *)v26[3];
              }
            }
            ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(a1 + 16) + 6312LL));
          }
          ExAcquireResourceExclusiveLite(*(PERESOURCE *)(a1 + 368), 1u);
          v29 = (_QWORD *)(a3 + 48);
          v30 = *(_QWORD *)(a3 + 48);
          if ( v30 )
          {
            if ( *(_QWORD **)(v30 + 8) != v29 )
              goto LABEL_72;
            v31 = *(_QWORD **)(a3 + 56);
            if ( (_QWORD *)*v31 != v29 )
              goto LABEL_72;
            *v31 = v30;
            *(_QWORD *)(v30 + 8) = v31;
            *v29 = 0;
          }
          if ( v15 || (*(_DWORD *)(a3 + 8) & 0x1000) != 0 )
          {
            v12 = 0;
          }
          else
          {
            if ( v10 )
              ExAcquireResourceExclusiveLite(*(PERESOURCE *)(v10 + 136), 1u);
            _InterlockedIncrement((volatile signed __int32 *)(a3 + 4));
            _InterlockedOr((volatile signed __int32 *)(a3 + 8), 0x1000u);
            v32 = *(_QWORD **)(a1 + 400);
            if ( *v32 != a1 + 392 )
LABEL_72:
              __fastfail(3u);
            v12 = 1;
            *(_QWORD *)(a3 + 64) = a1 + 392;
            *(_QWORD *)(a3 + 72) = v32;
            *v32 = a3 + 64;
            *(_QWORD *)(a1 + 400) = a3 + 64;
            if ( v10 )
              ExReleaseResourceLite(*(PERESOURCE *)(v10 + 136));
          }
          ExReleaseResourceLite(*(PERESOURCE *)(a1 + 368));
          return v12;
        }
      }
      for ( i = RtlEnumerateGenericTableAvl((PRTL_AVL_TABLE)(a3 + 152), 1u);
            i;
            i = RtlEnumerateGenericTableAvl((PRTL_AVL_TABLE)(a3 + 152), 0) )
      {
        v20 = i[6] << 12;
        v35 = *((_QWORD *)i + 1) << 12;
        TxfFreeTopsRange(a1, 0, (unsigned int)&v35, v20, (2 * v15) | (v17 != 0 ? 32 : 49));
        if ( v15 )
          RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)(a3 + 152), i);
      }
      if ( !v17 )
      {
        v21 = v37;
        while ( 1 )
        {
          v22 = *(_QWORD **)(a3 + 288);
          if ( !v22 )
            break;
          v23 = 0;
          *(_QWORD *)(a3 + 288) = *v22;
          if ( *((_DWORD *)v22 + 2) )
          {
            do
            {
              if ( (v22[2 * v23 + 3] & 0x10000LL) == 0 )
              {
                v24 = LOWORD(v22[2 * v23 + 3]) << 12;
                v37 = v22[2 * v23 + 2] << 12;
                TxfFreeTopsRange(a1, 0, (unsigned int)&v37, v24, 51);
                v21 += LOWORD(v22[2 * v23 + 3]);
              }
              ++v23;
            }
            while ( v23 < *((_DWORD *)v22 + 2) );
            v37 = v21;
          }
          ExFreeToLookasideListEx(&TxfTopsRangeEntryLookasideList, v22);
        }
        v17 = v36;
      }
      goto LABEL_43;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14029afbc  mov     [rsp+arg_18], rbx
0x14029afc1  push    rbp
0x14029afc2  push    rsi
0x14029afc3  push    rdi
0x14029afc4  push    r12
0x14029afc6  push    r13
0x14029afc8  push    r14
0x14029afca  push    r15
0x14029afcc  sub     rsp, 40h
0x14029afd0  xor     r12d, r12d
0x14029afd3  mov     ebp, r9d
0x14029afd6  mov     rbx, r8
0x14029afd9  mov     rdi, rdx
0x14029afdc  mov     rsi, rcx
0x14029afdf  test    rdx, rdx
0x14029afe2  jz      short loc_14029AFEA
0x14029afe4  mov     r13, [rdx+40h]
0x14029afe8  jmp     short loc_14029AFED
0x14029afea  mov     r13, r12
0x14029afed  mov     eax, [r8+8]
0x14029aff1  mov     qword ptr [rsp+78h+plsn1], r12
0x14029aff6  test    al, 20h
0x14029aff8  jnz     loc_14029B537
0x14029affe  mov     rcx, [r8+100h]; FastMutex
0x14029b005  mov     r14b, r12b
0x14029b008  mov     [rsp+78h+arg_0], r12b
0x14029b010  call    cs:__imp_ExAcquireFastMutex
0x14029b017  nop     dword ptr [rax+rax+00h]
0x14029b01c  lock or dword ptr [rbx+8], 800h
0x14029b024  mov     ecx, 4
0x14029b029  mov     eax, ecx
0x14029b02b  lock cmpxchg [rsi+84h], ecx
0x14029b033  cmp     eax, 3
0x14029b036  jnz     short loc_14029B040
0x14029b038  lock or dword ptr [rbx+8], 80000h
0x14029b040  mov     rcx, [rbx+100h]; FastMutex
0x14029b047  call    cs:__imp_ExReleaseFastMutex
0x14029b04e  nop     dword ptr [rax+rax+00h]
0x14029b053  lea     r15, [rbx+98h]
0x14029b05a  mov     rcx, r15; Table
0x14029b05d  call    cs:__imp_RtlIsGenericTableEmptyAvl
0x14029b064  nop     dword ptr [rax+rax+00h]
0x14029b069  test    al, al
0x14029b06b  jz      short loc_14029B07A
0x14029b06d  cmp     [rbx+120h], r12
0x14029b074  jz      loc_14029B16B
0x14029b07a  mov     r14d, 1
0x14029b080  test    rdi, rdi
0x14029b083  jz      short loc_14029B0A1
0x14029b085  mov     eax, r14d
0x14029b088  lock xadd [rdi+2Ch], eax
0x14029b08d  lock dec dword ptr [rdi+2Ch]
0x14029b091  add     eax, r14d
0x14029b094  cmp     eax, r14d
0x14029b097  jz      short loc_14029B0A1
0x14029b099  test    ebp, ebp
0x14029b09b  jz      loc_14029B537
0x14029b0a1  mov     rcx, qword ptr cs:NtfsLarge0
0x14029b0a8  xor     edi, edi
0x14029b0aa  mov     [rsp+78h+arg_10], rdi
0x14029b0b2  mov     rax, rcx
0x14029b0b5  lock cmpxchg [rsi+198h], rcx
0x14029b0be  lea     rdx, [rbx+118h]; plsn2
0x14029b0c5  mov     qword ptr [rsp+78h+plsn1], rax
0x14029b0ca  lea     rcx, [rsp+78h+plsn1]; plsn1
0x14029b0cf  call    cs:__imp_ClfsLsnGreater
0x14029b0d6  nop     dword ptr [rax+rax+00h]
0x14029b0db  test    al, al
0x14029b0dd  jnz     loc_14029B181
0x14029b0e3  cmp     [rsp+78h+arg_20], dil
0x14029b0eb  jnz     loc_14029B181
0x14029b0f1  lea     ecx, [rdi+4]
0x14029b0f4  mov     eax, ecx
0x14029b0f6  lock cmpxchg [rsi+84h], ecx
0x14029b0fe  cmp     eax, r14d
0x14029b101  jnz     short loc_14029B10C
0x14029b103  test    dword ptr [rbx+8], 200h
0x14029b10a  jnz     short loc_14029B181
0x14029b10c  mov     eax, ecx
0x14029b10e  lock cmpxchg [rsi+84h], ecx
0x14029b116  cmp     eax, 3
0x14029b119  jz      short loc_14029B181
0x14029b11b  mov     rcx, r15; Table
0x14029b11e  call    cs:__imp_RtlIsGenericTableEmptyAvl
0x14029b125  nop     dword ptr [rax+rax+00h]
0x14029b12a  test    al, al
0x14029b12c  jnz     short loc_14029B181
0x14029b12e  xor     bpl, bpl
0x14029b131  jmp     short loc_14029B184
0x14029b133  mov     rdx, [rdi]
0x14029b136  test    rdx, rdx
0x14029b139  jz      short loc_14029B14A
0x14029b13b  mov     rcx, [rsi+10h]
0x14029b13f  xor     r8d, r8d
0x14029b142  call    TxfDereferenceTxfQuotaControlBlock
0x14029b147  mov     [rdi], r12
0x14029b14a  mov     rax, [rdi+18h]
0x14029b14e  lea     rcx, TxfVscbQuotaInfoLookasideList; Lookaside
0x14029b155  mov     rdx, rdi; Entry
0x14029b158  mov     [rbx+128h], rax
0x14029b15f  call    cs:__imp_ExFreeToLookasideListEx
0x14029b166  nop     dword ptr [rax+rax+00h]
0x14029b16b  mov     rdi, [rbx+128h]
0x14029b172  test    rdi, rdi
0x14029b175  jnz     short loc_14029B133
0x14029b177  lock or dword ptr [rbx+8], 28h
0x14029b17c  jmp     loc_14029B532
0x14029b181  mov     bpl, r14b
0x14029b184  mov     r12d, [rbx+8]
0x14029b188  mov     dl, r14b; Wait
0x14029b18b  mov     rcx, [rsi+170h]; Resource
0x14029b192  and     r12d, 8
0x14029b196  mov     [rsp+78h+arg_8], r12d
0x14029b19e  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14029b1a5  nop     dword ptr [rax+rax+00h]
0x14029b1aa  test    r12d, r12d
0x14029b1ad  jnz     short loc_14029B1E4
0x14029b1af  mov     r8b, [rsp+78h+arg_28]
0x14029b1b7  xor     ecx, ecx
0x14029b1b9  mov     rdx, [rsi+118h]
0x14029b1c0  call    NtfsAcquireScbPagingResourceExclusive
0x14029b1c5  test    al, al
0x14029b1c7  jnz     short loc_14029B1ED
0x14029b1c9  mov     rcx, [rsi+170h]; Resource
0x14029b1d0  call    cs:__imp_ExReleaseResourceLite
0x14029b1d7  nop     dword ptr [rax+rax+00h]
0x14029b1dc  xor     bpl, bpl
0x14029b1df  jmp     loc_14029B36E
0x14029b1e4  test    bpl, bpl
0x14029b1e7  jz      loc_14029B328
0x14029b1ed  mov     dl, r14b; Restart
0x14029b1f0  mov     rcx, r15; Table
0x14029b1f3  call    cs:__imp_RtlEnumerateGenericTableAvl
0x14029b1fa  nop     dword ptr [rax+rax+00h]
0x14029b1ff  mov     r14, rax
0x14029b202  test    rax, rax
0x14029b205  jz      short loc_14029B274
0x14029b207  mov     eax, r12d
0x14029b20a  movzx   ecx, bpl
0x14029b20e  neg     eax
0x14029b210  sbb     edi, edi
0x14029b212  add     ecx, ecx
0x14029b214  and     edi, 0FFFFFFEFh
0x14029b217  add     edi, 31h ; '1'
0x14029b21a  or      edi, ecx
0x14029b21c  mov     rax, [r14+8]
0x14029b220  lea     r8, [rsp+78h+var_40]
0x14029b225  mov     r9d, [r14+18h]
0x14029b229  xor     edx, edx
0x14029b22b  shl     rax, 0Ch
0x14029b22f  mov     rcx, rsi
0x14029b232  shl     r9d, 0Ch
0x14029b236  mov     [rsp+78h+var_40], rax
0x14029b23b  mov     [rsp+78h+var_58], edi
0x14029b23f  call    TxfFreeTopsRange
0x14029b244  test    bpl, bpl
0x14029b247  jz      short loc_14029B25B
0x14029b249  mov     rdx, r14; Buffer
0x14029b24c  mov     rcx, r15; Table
0x14029b24f  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x14029b256  nop     dword ptr [rax+rax+00h]
0x14029b25b  xor     edx, edx; Restart
0x14029b25d  mov     rcx, r15; Table
0x14029b260  call    cs:__imp_RtlEnumerateGenericTableAvl
0x14029b267  nop     dword ptr [rax+rax+00h]
0x14029b26c  mov     r14, rax
0x14029b26f  test    rax, rax
0x14029b272  jnz     short loc_14029B21C
0x14029b274  test    r12d, r12d
0x14029b277  jnz     loc_14029B328
0x14029b27d  mov     r12, [rsp+78h+arg_10]
0x14029b285  mov     rdi, [rbx+120h]
0x14029b28c  test    rdi, rdi
0x14029b28f  jz      loc_14029B320
0x14029b295  mov     rax, [rdi]
0x14029b298  xor     r15d, r15d
0x14029b29b  mov     [rbx+120h], rax
0x14029b2a2  cmp     [rdi+8], r15d
0x14029b2a6  jbe     short loc_14029B305
0x14029b2a8  mov     r14d, r15d
0x14029b2ab  add     r14, r14
0x14029b2ae  test    byte ptr [rdi+r14*8+1Ah], 1
0x14029b2b4  jnz     short loc_14029B2F4
0x14029b2b6  mov     rax, [rdi+r14*8+10h]
0x14029b2bb  lea     r8, [rsp+78h+arg_10]
0x14029b2c3  movzx   r9d, word ptr [rdi+r14*8+18h]
0x14029b2c9  xor     edx, edx
0x14029b2cb  shl     rax, 0Ch
0x14029b2cf  mov     rcx, rsi
0x14029b2d2  shl     r9d, 0Ch
0x14029b2d6  mov     [rsp+78h+arg_10], rax
0x14029b2de  mov     [rsp+78h+var_58], 33h ; '3'
0x14029b2e6  call    TxfFreeTopsRange
0x14029b2eb  movzx   eax, word ptr [rdi+r14*8+18h]
0x14029b2f1  add     r12, rax
0x14029b2f4  inc     r15d
0x14029b2f7  cmp     r15d, [rdi+8]
0x14029b2fb  jb      short loc_14029B2A8
0x14029b2fd  mov     [rsp+78h+arg_10], r12
0x14029b305  mov     rdx, rdi; Entry
0x14029b308  lea     rcx, TxfTopsRangeEntryLookasideList; Lookaside
0x14029b30f  call    cs:__imp_ExFreeToLookasideListEx
0x14029b316  nop     dword ptr [rax+rax+00h]
0x14029b31b  jmp     loc_14029B285
0x14029b320  mov     r12d, [rsp+78h+arg_8]
0x14029b328  mov     rcx, [rsi+170h]; Resource
0x14029b32f  call    cs:__imp_ExReleaseResourceLite
0x14029b336  nop     dword ptr [rax+rax+00h]
0x14029b33b  test    r12d, r12d
0x14029b33e  jnz     short loc_14029B35C
0x14029b340  mov     rcx, [rsi+118h]
0x14029b347  mov     rcx, [rcx+10h]; Resource
0x14029b34b  call    cs:__imp_ExReleaseResourceLite
0x14029b352  nop     dword ptr [rax+rax+00h]
0x14029b357  lock or dword ptr [rbx+8], 8
0x14029b35c  mov     rdi, [rsp+78h+arg_10]
0x14029b364  test    bpl, bpl
0x14029b367  jz      short loc_14029B36E
0x14029b369  lock or dword ptr [rbx+8], 20h
0x14029b36e  cmp     qword ptr [rbx+128h], 0
0x14029b376  jz      loc_14029B462
0x14029b37c  test    bpl, bpl
0x14029b37f  jnz     short loc_14029B38A
0x14029b381  test    rdi, rdi
0x14029b384  jz      loc_14029B462
0x14029b38a  mov     rcx, [rsi+10h]
0x14029b38e  mov     r12d, 18A8h
0x14029b394  add     rcx, r12; FastMutex
0x14029b397  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14029b39e  nop     dword ptr [rax+rax+00h]
0x14029b3a3  mov     rdi, [rbx+128h]
0x14029b3aa  xor     r14d, r14d
0x14029b3ad  xor     r15d, r15d
0x14029b3b0  jmp     loc_14029B446
0x14029b3b5  mov     rdx, [rdi]
0x14029b3b8  test    rdx, rdx
0x14029b3bb  jz      short loc_14029B3C9
0x14029b3bd  mov     rax, [rdi+10h]
0x14029b3c1  shl     rax, 0Ch
0x14029b3c5  sub     [rdx+10h], rax
0x14029b3c9  mov     [rdi+10h], r15
0x14029b3cd  test    bpl, bpl
0x14029b3d0  jnz     short loc_14029B3E1
0x14029b3d2  cmp     [rdi+8], r15
0x14029b3d6  jz      short loc_14029B3E1
0x14029b3d8  mov     r14, rdi
0x14029b3db  mov     rdi, [rdi+18h]
0x14029b3df  jmp     short loc_14029B446
0x14029b3e1  mov     rcx, [rdi]
0x14029b3e4  test    rcx, rcx
0x14029b3e7  jz      short loc_14029B407
0x14029b3e9  mov     rax, [rdi+8]
0x14029b3ed  mov     r8b, 1
0x14029b3f0  shl     rax, 0Ch
0x14029b3f4  sub     [rcx+10h], rax
0x14029b3f8  mov     rdx, [rdi]
0x14029b3fb  mov     rcx, [rsi+10h]
0x14029b3ff  call    TxfDereferenceTxfQuotaControlBlock
0x14029b404  mov     [rdi], r15
0x14029b407  mov     rax, [rdi+18h]
0x14029b40b  mov     rdx, rdi; Entry
0x14029b40e  lea     rcx, TxfVscbQuotaInfoLookasideList; Lookaside
0x14029b415  test    r14, r14
0x14029b418  jnz     short loc_14029B436
0x14029b41a  mov     [rbx+128h], rax
0x14029b421  call    cs:__imp_ExFreeToLookasideListEx
0x14029b428  nop     dword ptr [rax+rax+00h]
0x14029b42d  mov     rdi, [rbx+128h]
0x14029b434  jmp     short loc_14029B446
0x14029b436  mov     [r14+18h], rax
0x14029b43a  call    cs:__imp_ExFreeToLookasideListEx
0x14029b441  nop     dword ptr [rax+rax+00h]
0x14029b446  test    rdi, rdi
0x14029b449  jnz     loc_14029B3B5
0x14029b44f  mov     rcx, [rsi+10h]
0x14029b453  add     rcx, r12; FastMutex
0x14029b456  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14029b45d  nop     dword ptr [rax+rax+00h]
0x14029b462  mov     rcx, [rsi+170h]; Resource
0x14029b469  mov     dl, 1; Wait
0x14029b46b  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14029b472  nop     dword ptr [rax+rax+00h]
0x14029b477  lea     rax, [rbx+30h]
0x14029b47b  mov     rcx, [rax]
0x14029b47e  test    rcx, rcx
0x14029b481  jz      short loc_14029B4A0
0x14029b483  cmp     [rcx+8], rax
0x14029b487  jnz     short loc_14029B4E1
0x14029b489  mov     rdx, [rax+8]
0x14029b48d  cmp     [rdx], rax
0x14029b490  jnz     short loc_14029B4E1
0x14029b492  mov     [rdx], rcx
0x14029b495  mov     [rcx+8], rdx
0x14029b499  mov     qword ptr [rax], 0
0x14029b4a0  test    bpl, bpl
0x14029b4a3  jnz     short loc_14029B517
0x14029b4a5  mov     edi, 1000h
0x14029b4aa  test    [rbx+8], edi
0x14029b4ad  jnz     short loc_14029B517
0x14029b4af  test    r13, r13
  ... truncated ...
```
