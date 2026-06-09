# NtfsCreateLcb

- ea: `0x14019b330`
- end: `0x14019ba0a`
- name: `NtfsCreateLcb`
- size: `1754`
- prototype: `_QWORD *__fastcall(__int64, __int64, __int64, const void **, char, __int64)`
- caller_count: `17`
- callee_count: `13`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1400d2654`
- `0x14012c7bc`
- `0x1401321c0`
- `0x14014a930`
- `0x14018427c`
- `0x14018cb48`
- `0x1401991d0`
- `0x1401c3700`
- `0x14020d830`
- `0x140227518`
- `0x1402376ac`
- `0x140247554`
- `0x14024ad14`
- `0x14024c894`
- `0x14024fba4`
- `0x140258148`
- `0x140265544`

## callees

- `0x140007ea0`
- `0x140008278`
- `0x14000c290`
- `0x140021b10`
- `0x1400410a8`
- `0x1400593c0`
- `0x1400596c0`
- `0x140059be0`
- `0x14014dde0`
- `0x1401620c0`
- `0x14019a718`
- `0x14019b330`
- `0x140207e40`

## import_xrefs

- `ntoskrnl!RtlGetNtSystemRoot` at `0x14019b591`
- `ntoskrnl!RtlGetNtSystemRoot` at `0x14019b591`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x14019b7cb`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x14019b7cb`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x14019b51e`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x14019b51e`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402ac94f`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402ac94f`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14019b8fc`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14019b8fc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ac972`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ac972`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14019b467`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14019b467`
- `ntoskrnl!ExAcquireFastMutex` at `0x14019b623`
- `ntoskrnl!ExAcquireFastMutex` at `0x14019b711`
- `ntoskrnl!ExAcquireFastMutex` at `0x14019b7df`
- `ntoskrnl!ExAcquireFastMutex` at `0x14019b623`
- `ntoskrnl!ExAcquireFastMutex` at `0x14019b711`
- `ntoskrnl!ExAcquireFastMutex` at `0x14019b7df`
- `ntoskrnl!ExReleaseFastMutex` at `0x14019b5ef`
- `ntoskrnl!ExReleaseFastMutex` at `0x14019b659`
- `ntoskrnl!ExReleaseFastMutex` at `0x14019b751`
- `ntoskrnl!ExReleaseFastMutex` at `0x14019b5ef`
- `ntoskrnl!ExReleaseFastMutex` at `0x14019b659`
- `ntoskrnl!ExReleaseFastMutex` at `0x14019b751`

## pseudocode

```c
_QWORD *__fastcall NtfsCreateLcb(__int64 a1, __int64 a2, __int64 a3, const void **a4, char a5, __int64 a6)
{
  __int64 v9; // r13
  _BYTE *v10; // rdi
  __int64 v11; // r10
  __int64 v12; // rdx
  char v13; // r15
  _QWORD *result; // rax
  int v15; // eax
  _DWORD *v16; // rdi
  __int16 v17; // r12
  __int64 v18; // rdx
  _QWORD *PoolWithTag; // rdx
  void *v20; // rcx
  __int64 v21; // rdx
  char v22; // cl
  _QWORD *v23; // r9
  _WORD *v24; // rcx
  __int64 v25; // rax
  char v26; // r14
  int v27; // eax
  _DWORD *v28; // r9
  _QWORD *v29; // rcx
  __int64 v30; // r15
  __int64 v31; // rcx
  __int64 v32; // r15
  _QWORD *v33; // rdx
  char v34; // dl
  _DWORD *v35; // rax
  int v36; // eax
  _QWORD *v37; // [rsp+98h] [rbp+10h] BYREF

  v9 = a1;
  LOBYTE(v37) = 1;
  v10 = &v37;
  if ( a6 )
    v10 = (_BYTE *)a6;
  v11 = *(_QWORD *)(a2 + 184);
  v12 = *(_QWORD *)(v11 + 320);
  if ( v12 )
  {
    a1 = *(_QWORD *)(a3 + 320);
    if ( a1 )
    {
      if ( a1 != v12 )
      {
        if ( (*(_DWORD *)(a3 + 4) & 8) == 0
          || (v36 = *(_DWORD *)(a3 + 8), v36 != 5) && *(_DWORD *)(a1 + 88) != v36
          || v12 != *(_QWORD *)(*(_QWORD *)(v12 + 16) + 6248LL) )
        {
          NtfsAttachCorruption_BadOrOrphanFRS(v9, 2, 2239799, (__int64)a4, (_DWORD *)(v11 + 8), v11, 0);
          NtfsAttachRepairInfoPriv(v9, 256, 0, (struct _LIST_ENTRY *)0x13700222D37LL);
          if ( NtfsStatusDebugFlags )
            NtfsStatusTraceAndDebugInternal(v9, 0xC0000102, 0x222D37u);
          NtfsRaiseStatusInternal(v9, -1073741566, *(_QWORD *)(a2 + 184) + 8, *(_QWORD *)(a2 + 184), 2239799);
        }
      }
    }
  }
  v13 = a5;
  result = NtfsFindExistingLcb(a1, v11, a3, a4, a5, 1);
  if ( result )
  {
    *v10 = 1;
  }
  else if ( *v10 )
  {
    LOBYTE(a6) = 0;
    *v10 = 0;
    v15 = *(_DWORD *)(a3 + 4);
    if ( (v15 & 0x200) == 0 || (v16 = (_DWORD *)(a3 + 1144), *(_WORD *)(a3 + 1144)) )
    {
      if ( (v15 & 0x400) == 0 || (v16 = (_DWORD *)(a3 + 1352), *(_WORD *)(a3 + 1352)) )
      {
        v16 = ExAllocateFromLookasideListEx(&NtfsLcbLookasideList);
        LOBYTE(v17) = 0;
      }
      else
      {
        LOBYTE(v17) = 17;
      }
    }
    else
    {
      LOBYTE(v17) = 17;
    }
    memset(v16, 0, 0xD4u);
    *v16 = 14157579;
    v18 = *(unsigned __int16 *)a4;
    v37 = v16 + 48;
    if ( (unsigned __int8)v17 >= (unsigned __int16)((unsigned __int16)v18 >> 1) )
    {
      PoolWithTag = v16 + 36;
      *((_QWORD *)v16 + 24) = v16 + 36;
    }
    else
    {
      PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), v18 + 66, 0x7346744Eu);
      *v37 = PoolWithTag;
      v17 = *(_WORD *)a4 >> 1;
    }
    *PoolWithTag = *(_QWORD *)(*(_QWORD *)(a2 + 184) + 8LL);
    *(_BYTE *)(*((_QWORD *)v16 + 24) + 64LL) = *(_WORD *)a4 >> 1;
    *(_BYTE *)(*((_QWORD *)v16 + 24) + 65LL) = v13;
    v20 = (void *)(*((_QWORD *)v16 + 24) + 66LL);
    *((_QWORD *)v16 + 10) = v20;
    *((_WORD *)v16 + 36) = *(_WORD *)a4;
    *((_WORD *)v16 + 37) = 2 * (unsigned __int8)v17;
    memmove(v20, a4[1], *(unsigned __int16 *)a4);
    v22 = *(_BYTE *)(*((_QWORD *)v16 + 24) + 65LL) & 3;
    if ( (unsigned __int8)(v22 - 1) <= 1u )
    {
      if ( v22 == 2 )
      {
        LOBYTE(v21) = 1;
        v35 = (_DWORD *)NtfsLookupLcbByFlags(a3, v21);
        if ( v35 )
        {
          v16[9] = v35[9];
          v16[10] = v35[10];
          v16[11] = v35[11];
        }
      }
      else if ( v22 == 1 )
      {
        v28 = 0;
        v29 = *(_QWORD **)(a3 + 48);
        while ( v29 != (_QWORD *)(a3 + 48) )
        {
          if ( (*((_DWORD *)v29 - 13) & 2) != 0 )
          {
            v29 = (_QWORD *)*v29;
          }
          else
          {
            if ( *(_BYTE *)(v29[17] + 65LL) == 2 )
            {
              v28 = v29 - 7;
              break;
            }
            v29 = (_QWORD *)*v29;
          }
        }
        if ( v28 )
        {
          v16[9] = v28[9];
          v16[10] = v28[10];
          v16[11] = v28[11];
        }
      }
    }
    if ( (*(_DWORD *)(a3 + 176) & 0x10000000) != 0 )
    {
      v30 = 0;
      while ( 1 )
      {
        ExAcquireFastMutex((PFAST_MUTEX)(*(_QWORD *)(a3 + 104) + 8LL));
        if ( *(_QWORD *)(a3 + 48) != a3 + 48 )
        {
          v31 = *(_QWORD *)(a3 + 48);
          while ( 1 )
          {
            if ( v30 )
            {
              v32 = *(_QWORD *)(v30 + 56);
              if ( v32 == a3 + 48 )
                break;
              v31 = *(_QWORD *)(a3 + 48);
            }
            else
            {
              v32 = v31;
            }
            v30 = v32 - 56;
            if ( (*(_DWORD *)(v30 + 4) & 2) == 0 )
              goto LABEL_51;
          }
        }
        v30 = 0;
LABEL_51:
        ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(a3 + 104) + 8LL));
        if ( !v30 )
          break;
        if ( (*(_DWORD *)(v30 + 4) & 2) == 0 )
        {
          if ( ((v34 = *(_BYTE *)(*((_QWORD *)v16 + 24) + 65LL) & 3, v34 != 2)
             || (*(_BYTE *)(*(_QWORD *)(v30 + 192) + 65LL) & 3) != 1)
            && (v34 != 1 || (*(_BYTE *)(*(_QWORD *)(v30 + 192) + 65LL) & 3) != 2)
            || a2 != *(_QWORD *)(v30 + 24) )
          {
            a6 = 0x17600222DCFLL;
            NtfsAttachCorruptionSimple(v9, 2u, 2, 2239951, 0);
            NtfsAttachRepairInfoPriv(v9, 0, 0, (struct _LIST_ENTRY *)0x17600222DCFLL);
            if ( NtfsStatusDebugFlags )
              NtfsStatusTraceAndDebugInternal(v9, 0xC0000032, 0x222DCFu);
            NtfsRaiseStatusInternal(v9, -1073741774, 0, 0, 2239951);
          }
        }
      }
      *((_QWORD *)v16 + 17) = NtfsCreateScb(v9, a3, 160, &NtfsFileNameIndex, 1, 0, 0);
    }
    FsRtlAcquireHeaderMutex(a2 + 120, a2 + 160);
    v23 = *(_QWORD **)(a2 + 648);
    if ( *v23 != a2 + 640 )
      goto LABEL_17;
    *((_QWORD *)v16 + 1) = a2 + 640;
    *((_QWORD *)v16 + 2) = v23;
    *v23 = v16 + 2;
    *(_QWORD *)(a2 + 648) = v16 + 2;
    *((_QWORD *)v16 + 3) = a2;
    FsRtlReleaseHeaderMutex(a2 + 120, a2 + 160);
    ExAcquireFastMutex((PFAST_MUTEX)(*(_QWORD *)(a3 + 104) + 8LL));
    v33 = *(_QWORD **)(a3 + 56);
    if ( *v33 != a3 + 48 )
LABEL_17:
      __fastfail(3u);
    *((_QWORD *)v16 + 7) = a3 + 48;
    *((_QWORD *)v16 + 8) = v33;
    *v33 = v16 + 14;
    *(_QWORD *)(a3 + 56) = v16 + 14;
    *((_QWORD *)v16 + 6) = a3;
    *((_QWORD *)v16 + 16) = v16 + 30;
    *((_QWORD *)v16 + 15) = v16 + 30;
    if ( !TxfSearchingForSystemRoot )
      goto LABEL_24;
    if ( (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a3 + 96) + 248LL) + 16LL) + 48LL) & 0x100) == 0 )
      goto LABEL_24;
    if ( !*(_QWORD *)(a2 + 664) )
      goto LABEL_24;
    v24 = (_WORD *)(RtlGetNtSystemRoot() + 4);
    v25 = -1;
    do
      ++v25;
    while ( v24[v25] );
    if ( *(unsigned __int16 *)(a2 + 656) == 2 * v25 )
    {
      v27 = memcmp(v24, *(const void **)(a2 + 664), 2 * v25);
      v26 = a6;
      if ( !v27 )
        v26 = 1;
    }
    else
    {
LABEL_24:
      v26 = a6;
    }
    if ( (*(_DWORD *)(*(_QWORD *)(a2 + 184) + 4LL) & 0x1800000) != 0 )
      *(_DWORD *)(a3 + 4) |= 0x1000000u;
    ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(a3 + 104) + 8LL));
    if ( v26 )
    {
      ExAcquireFastMutex((PFAST_MUTEX)(*(_QWORD *)(*(_QWORD *)(a2 + 184) + 104LL) + 8LL));
      *(_DWORD *)(*(_QWORD *)(a2 + 184) + 4LL) |= 0x800000u;
      TxfSearchingForSystemRoot = 0;
      ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(*(_QWORD *)(a2 + 184) + 104LL) + 8LL));
    }
    return v16;
  }
  else
  {
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x14019b330  mov     rax, rsp
0x14019b333  mov     [rax+8], rbx
0x14019b337  mov     [rax+18h], rsi
0x14019b33b  push    rdi
0x14019b33c  push    r12
0x14019b33e  push    r13
0x14019b340  push    r14
0x14019b342  push    r15
0x14019b344  sub     rsp, 60h
0x14019b348  mov     r14, r9
0x14019b34b  mov     rbx, r8
0x14019b34e  mov     rsi, rdx
0x14019b351  mov     r13, rcx
0x14019b354  mov     byte ptr [rax+10h], 1
0x14019b358  xorps   xmm0, xmm0
0x14019b35b  movdqu  xmmword ptr [rax-40h], xmm0
0x14019b360  lea     rdi, [rax+10h]
0x14019b364  mov     rax, [rsp+88h+arg_28]
0x14019b36c  test    rax, rax
0x14019b36f  cmovnz  rdi, rax
0x14019b373  mov     r10, [rdx+0B8h]
0x14019b37a  mov     rdx, [r10+140h]
0x14019b381  test    rdx, rdx
0x14019b384  jz      short loc_14019B39B
0x14019b386  mov     rcx, [r8+140h]
0x14019b38d  test    rcx, rcx
0x14019b390  jz      short loc_14019B39B
0x14019b392  cmp     rcx, rdx
0x14019b395  jnz     loc_14019B94F
0x14019b39b  mov     byte ptr [rsp+88h+var_60], 1
0x14019b3a0  movzx   r15d, [rsp+88h+arg_20]
0x14019b3a9  mov     byte ptr [rsp+88h+var_68], r15b
0x14019b3ae  mov     rdx, r10
0x14019b3b1  call    NtfsFindExistingLcb
0x14019b3b6  mov     [rsp+88h+var_48], rax
0x14019b3bb  test    rax, rax
0x14019b3be  jz      short loc_14019B3DE
0x14019b3c0  mov     byte ptr [rdi], 1
0x14019b3c3  lea     r11, [rsp+88h+var_28]
0x14019b3c8  mov     rbx, [r11+30h]
0x14019b3cc  mov     rsi, [r11+40h]
0x14019b3d0  mov     rsp, r11
0x14019b3d3  pop     r15
0x14019b3d5  pop     r14
0x14019b3d7  pop     r13
0x14019b3d9  pop     r12
0x14019b3db  pop     rdi
0x14019b3dc  retn
0x14019b3de  cmp     byte ptr [rdi], 0
0x14019b3e1  jz      loc_14019B9F5
0x14019b3e7  mov     byte ptr [rsp+88h+arg_28], 0
0x14019b3ef  mov     byte ptr [rdi], 0
0x14019b3f2  mov     eax, [rbx+4]
0x14019b3f5  bt      eax, 9
0x14019b3f9  jnb     loc_14019B8D5
0x14019b3ff  lea     rdi, [rbx+478h]
0x14019b406  cmp     word ptr [rdi], 0
0x14019b40a  jnz     loc_14019B8D5
0x14019b410  mov     [rsp+88h+var_48], rdi
0x14019b415  mov     r12b, 11h
0x14019b418  xor     edx, edx; Val
0x14019b41a  mov     r8d, 0D4h; Size
0x14019b420  mov     rcx, rdi; void *
0x14019b423  call    memset
0x14019b428  mov     dword ptr [rdi], 0D8070Bh
0x14019b42e  movzx   edx, word ptr [r14]
0x14019b432  lea     r8, [rdi+0C0h]
0x14019b439  mov     [rsp+88h+arg_8], r8
0x14019b441  movzx   ecx, dx
0x14019b444  shr     cx, 1
0x14019b447  movzx   eax, r12b
0x14019b44b  cmp     ax, cx
0x14019b44e  jnb     loc_14019B68F
0x14019b454  add     rdx, 42h ; 'B'; NumberOfBytes
0x14019b458  mov     ecx, cs:PoolType
0x14019b45e  or      ecx, 10h; PoolType
0x14019b461  mov     r8d, 7346744Eh; Tag
0x14019b467  call    cs:__imp_ExAllocatePoolWithTag
0x14019b46e  nop     dword ptr [rax+rax+00h]
0x14019b473  mov     rdx, rax
0x14019b476  mov     [rsp+88h+var_38], rax
0x14019b47b  mov     rax, [rsp+88h+arg_8]
0x14019b483  mov     [rax], rdx
0x14019b486  movzx   r12d, word ptr [r14]
0x14019b48a  shr     r12w, 1
0x14019b48e  mov     rax, [rsi+0B8h]
0x14019b495  mov     rcx, [rax+8]
0x14019b499  mov     [rdx], rcx
0x14019b49c  movzx   ecx, word ptr [r14]
0x14019b4a0  shr     cx, 1
0x14019b4a3  mov     rax, [rdi+0C0h]
0x14019b4aa  mov     [rax+40h], cl
0x14019b4ad  mov     rax, [rdi+0C0h]
0x14019b4b4  mov     [rax+41h], r15b
0x14019b4b8  mov     rcx, [rdi+0C0h]
0x14019b4bf  add     rcx, 42h ; 'B'; void *
0x14019b4c3  mov     [rdi+50h], rcx
0x14019b4c7  movzx   eax, word ptr [r14]
0x14019b4cb  mov     [rdi+48h], ax
0x14019b4cf  movzx   eax, r12b
0x14019b4d3  add     ax, ax
0x14019b4d6  mov     [rdi+4Ah], ax
0x14019b4da  movzx   r8d, word ptr [r14]; Size
0x14019b4de  mov     rdx, [r14+8]; Src
0x14019b4e2  call    memmove
0x14019b4e7  mov     rax, [rdi+0C0h]
0x14019b4ee  movzx   ecx, byte ptr [rax+41h]
0x14019b4f2  and     cl, 3
0x14019b4f5  lea     eax, [rcx-1]
0x14019b4f8  cmp     al, 1
0x14019b4fa  jbe     loc_14019B69E
0x14019b500  xor     r14d, r14d
0x14019b503  test    dword ptr [rbx+0B0h], 10000000h
0x14019b50d  jnz     loc_14019B706
0x14019b513  lea     rdx, [rsi+0A0h]
0x14019b51a  lea     rcx, [rsi+78h]
0x14019b51e  call    cs:__imp_FsRtlAcquireHeaderMutex
0x14019b525  nop     dword ptr [rax+rax+00h]
0x14019b52a  lea     r8, [rsi+280h]
0x14019b531  mov     r9, [r8+8]
0x14019b535  cmp     [r9], r8
0x14019b538  jz      loc_14019B7AA
0x14019b53e  mov     ecx, 3
0x14019b543  int     29h; Win8: RtlFailFast(ecx)
0x14019b545  lea     rax, [rdi+38h]
0x14019b549  mov     [rax], rcx
0x14019b54c  mov     [rax+8], rdx
0x14019b550  mov     [rdx], rax
0x14019b553  mov     [rcx+8], rax
0x14019b557  mov     [rdi+30h], rbx
0x14019b55b  lea     rax, [rdi+78h]
0x14019b55f  mov     [rax+8], rax
0x14019b563  mov     [rax], rax
0x14019b566  cmp     cs:TxfSearchingForSystemRoot, 0
0x14019b56d  jz      short loc_14019B5CF
0x14019b56f  mov     rax, [rbx+60h]
0x14019b573  mov     rcx, [rax+0F8h]
0x14019b57a  mov     rax, [rcx+10h]
0x14019b57e  test    dword ptr [rax+30h], 100h
0x14019b585  jz      short loc_14019B5CF
0x14019b587  cmp     qword ptr [rsi+298h], 0
0x14019b58f  jz      short loc_14019B5CF
0x14019b591  call    cs:__imp_RtlGetNtSystemRoot
0x14019b598  nop     dword ptr [rax+rax+00h]
0x14019b59d  lea     rcx, [rax+4]; Buf1
0x14019b5a1  mov     rax, 0FFFFFFFFFFFFFFFFh
0x14019b5a8  nop     dword ptr [rax+rax+00000000h]
0x14019b5b0  lea     rax, [rax+1]
0x14019b5b4  cmp     word ptr [rcx+rax*2], 0
0x14019b5b9  jnz     short loc_14019B5B0
0x14019b5bb  lea     r8, [rax+rax]; Size
0x14019b5bf  movzx   eax, word ptr [rsi+290h]
0x14019b5c6  cmp     rax, r8
0x14019b5c9  jz      loc_14019B667
0x14019b5cf  mov     r14d, dword ptr [rsp+88h+arg_28]
0x14019b5d7  mov     rax, [rsi+0B8h]
0x14019b5de  test    dword ptr [rax+4], 1800000h
0x14019b5e5  jnz     short loc_14019B605
0x14019b5e7  mov     rcx, [rbx+68h]
0x14019b5eb  add     rcx, 8; FastMutex
0x14019b5ef  call    cs:__imp_ExReleaseFastMutex
0x14019b5f6  nop     dword ptr [rax+rax+00h]
0x14019b5fb  test    r14b, r14b
0x14019b5fe  jnz     short loc_14019B614
0x14019b600  jmp     loc_14019B947
0x14019b605  mov     eax, [rbx+4]
0x14019b608  bts     eax, 18h
0x14019b60c  mov     [rbx+4], eax
0x14019b60f  mov     eax, [rbx+4]
0x14019b612  jmp     short loc_14019B5E7
0x14019b614  mov     rax, [rsi+0B8h]
0x14019b61b  mov     rcx, [rax+68h]
0x14019b61f  add     rcx, 8; FastMutex
0x14019b623  call    cs:__imp_ExAcquireFastMutex
0x14019b62a  nop     dword ptr [rax+rax+00h]
0x14019b62f  mov     rcx, [rsi+0B8h]
0x14019b636  mov     eax, [rcx+4]
0x14019b639  bts     eax, 17h
0x14019b63d  mov     [rcx+4], eax
0x14019b640  mov     eax, [rcx+4]
0x14019b643  mov     cs:TxfSearchingForSystemRoot, 0
0x14019b64a  mov     rax, [rsi+0B8h]
0x14019b651  mov     rcx, [rax+68h]
0x14019b655  add     rcx, 8; FastMutex
0x14019b659  call    cs:__imp_ExReleaseFastMutex
0x14019b660  nop     dword ptr [rax+rax+00h]
0x14019b665  jmp     short loc_14019B600
0x14019b667  mov     rdx, [rsi+298h]; Buf2
0x14019b66e  call    memcmp
0x14019b673  mov     r14d, dword ptr [rsp+88h+arg_28]
0x14019b67b  movzx   r14d, r14b
0x14019b67f  mov     ecx, 1
0x14019b684  test    eax, eax
0x14019b686  cmovz   r14d, ecx
0x14019b68a  jmp     loc_14019B5D7
0x14019b68f  lea     rdx, [rdi+90h]
0x14019b696  mov     [r8], rdx
0x14019b699  jmp     loc_14019B48E
0x14019b69e  cmp     cl, 2
0x14019b6a1  jz      loc_14019B91D
0x14019b6a7  cmp     cl, 1
0x14019b6aa  jnz     loc_14019B500
0x14019b6b0  xor     r14d, r14d
0x14019b6b3  mov     r9d, r14d
0x14019b6b6  lea     r8, [rbx+30h]
0x14019b6ba  mov     rcx, [r8]
0x14019b6bd  cmp     rcx, r8
0x14019b6c0  jz      short loc_14019B6E3
0x14019b6c2  mov     eax, [rcx-34h]
0x14019b6c5  test    al, 2
0x14019b6c7  jnz     loc_14019B795
0x14019b6cd  mov     rax, [rcx+88h]
0x14019b6d4  cmp     byte ptr [rax+41h], 2
0x14019b6d8  jz      short loc_14019B6DF
0x14019b6da  mov     rcx, [rcx]
0x14019b6dd  jmp     short loc_14019B6BD
0x14019b6df  lea     r9, [rcx-38h]
0x14019b6e3  test    r9, r9
0x14019b6e6  jz      loc_14019B503
0x14019b6ec  mov     eax, [r9+24h]
0x14019b6f0  mov     [rdi+24h], eax
0x14019b6f3  mov     eax, [r9+28h]
0x14019b6f7  mov     [rdi+28h], eax
0x14019b6fa  mov     eax, [r9+2Ch]
0x14019b6fe  mov     [rdi+2Ch], eax
0x14019b701  jmp     loc_14019B503
0x14019b706  mov     r15, r14
0x14019b709  mov     rcx, [rbx+68h]
0x14019b70d  add     rcx, 8; FastMutex
0x14019b711  call    cs:__imp_ExAcquireFastMutex
0x14019b718  nop     dword ptr [rax+rax+00h]
0x14019b71d  lea     r8, [rbx+30h]
0x14019b721  mov     rdx, [r8]
0x14019b724  cmp     rdx, r8
0x14019b727  jz      short loc_14019B746
0x14019b729  mov     rcx, rdx
0x14019b72c  test    r15, r15
0x14019b72f  jnz     loc_14019B8AB
0x14019b735  mov     r15, rcx
0x14019b738  add     r15, 0FFFFFFFFFFFFFFC8h
0x14019b73c  mov     eax, [r15+4]
0x14019b740  test    al, 2
0x14019b742  jnz     short loc_14019B72C
0x14019b744  jmp     short loc_14019B749
0x14019b746  mov     r15, r14
0x14019b749  mov     rcx, [rbx+68h]
0x14019b74d  add     rcx, 8; FastMutex
0x14019b751  call    cs:__imp_ExReleaseFastMutex
0x14019b758  nop     dword ptr [rax+rax+00h]
0x14019b75d  test    r15, r15
0x14019b760  jnz     short loc_14019B79D
0x14019b762  mov     [rsp+88h+var_58], r14
0x14019b767  mov     [rsp+88h+var_60], r14
0x14019b76c  mov     byte ptr [rsp+88h+var_68], 1
0x14019b771  lea     r9, NtfsFileNameIndex
0x14019b778  mov     r8d, 0A0h
0x14019b77e  mov     rdx, rbx
0x14019b781  mov     rcx, r13
0x14019b784  call    NtfsCreateScb
0x14019b789  mov     [rdi+88h], rax
0x14019b790  jmp     loc_14019B513
0x14019b795  mov     rcx, [rcx]
0x14019b798  jmp     loc_14019B6BD
0x14019b79d  mov     eax, [r15+4]
0x14019b7a1  test    al, 2
0x14019b7a3  jz      short loc_14019B801
0x14019b7a5  jmp     loc_14019B709
0x14019b7aa  lea     rax, [rdi+8]
0x14019b7ae  mov     [rax], r8
0x14019b7b1  mov     [rax+8], r9
0x14019b7b5  mov     [r9], rax
0x14019b7b8  mov     [r8+8], rax
0x14019b7bc  mov     [rdi+18h], rsi
0x14019b7c0  lea     rdx, [rsi+0A0h]
0x14019b7c7  lea     rcx, [rsi+78h]
0x14019b7cb  call    cs:__imp_FsRtlReleaseHeaderMutex
0x14019b7d2  nop     dword ptr [rax+rax+00h]
0x14019b7d7  mov     rcx, [rbx+68h]
0x14019b7db  add     rcx, 8; FastMutex
0x14019b7df  call    cs:__imp_ExAcquireFastMutex
0x14019b7e6  nop     dword ptr [rax+rax+00h]
0x14019b7eb  lea     rcx, [rbx+30h]
0x14019b7ef  mov     rdx, [rcx+8]
0x14019b7f3  cmp     [rdx], rcx
0x14019b7f6  jnz     loc_14019B53E
0x14019b7fc  jmp     loc_14019B545
0x14019b801  mov     rax, [rdi+0C0h]
0x14019b808  movzx   edx, byte ptr [rax+41h]
0x14019b80c  and     dl, 3
0x14019b80f  cmp     dl, 2
0x14019b812  jnz     short loc_14019B827
0x14019b814  mov     rax, [r15+0C0h]
0x14019b81b  movzx   ecx, byte ptr [rax+41h]
0x14019b81f  and     cl, 3
0x14019b822  cmp     cl, 1
0x14019b825  jz      short loc_14019B83F
0x14019b827  cmp     dl, 1
0x14019b82a  jnz     short loc_14019B849
0x14019b82c  mov     rax, [r15+0C0h]
0x14019b833  movzx   ecx, byte ptr [rax+41h]
  ... truncated ...
```
