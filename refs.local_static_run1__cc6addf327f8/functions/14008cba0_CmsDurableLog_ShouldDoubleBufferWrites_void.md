# CmsDurableLog::ShouldDoubleBufferWrites(void)

- ea: `0x14008cba0`
- end: `0x14008ce26`
- name: `?ShouldDoubleBufferWrites@CmsDurableLog@@AEAAPEAU_SmsMergeState@@XZ`
- size: `646`
- prototype: `struct _SmsMergeState *__fastcall(CmsDurableLog *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1400c7fcc`

## callees

- `0x140024c60`
- `0x14008cba0`
- `0x1400ceda0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14008cdbb`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14008cdf7`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14008cdbb`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14008cdf7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14008cbb4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14008cbb4`
- `ntoskrnl!KeReleaseSpinLock` at `0x14008cc02`
- `ntoskrnl!KeReleaseSpinLock` at `0x14008cc02`
- `ntoskrnl!ExAllocatePool2` at `0x14008cc69`
- `ntoskrnl!ExAllocatePool2` at `0x14008cd13`
- `ntoskrnl!ExAllocatePool2` at `0x14008cc69`
- `ntoskrnl!ExAllocatePool2` at `0x14008cd13`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14008cc29`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14008ccd8`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14008cc29`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14008ccd8`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1402013be`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1402013d0`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1402013be`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1402013d0`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14008cdd8`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14008ce15`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14008cdd8`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14008ce15`

## string_xrefs

- `0x1402013e2`: `Lookaside list allocation must be double quad aligned.`

## pseudocode

```c
struct _SmsMergeState *__fastcall CmsDurableLog::ShouldDoubleBufferWrites(KSPIN_LOCK *this)
{
  unsigned int v2; // esi
  unsigned int v3; // edi
  KIRQL v4; // al
  KSPIN_LOCK v5; // rdx
  unsigned int v6; // r8d
  struct _SmsMergeState *result; // rax
  __int64 v8; // rbx
  __int64 v9; // r9
  __int64 v10; // rdx
  __int64 Pool2; // rax
  int v12; // ecx
  _DWORD *v13; // rbx
  unsigned int *v14; // rdi
  __int64 v15; // r9
  __int64 v16; // rdx
  __int64 v17; // rax
  int v18; // r14d
  struct _NPAGED_LOOKASIDE_LIST *v19; // rcx
  struct _NPAGED_LOOKASIDE_LIST *v20; // rcx

  v2 = 0;
  v3 = 0;
  v4 = KeAcquireSpinLockRaiseToDpc(this + 5);
  v5 = this[11];
  for ( *((_BYTE *)this + 48) = v4; v5; v2 = v6 )
  {
    v6 = v2 + *(_DWORD *)(v5 + 36);
    if ( v6 > 0x40000 )
      break;
    if ( v3 >= MsPerfParams )
      break;
    v5 = *(_QWORD *)(v5 + 48);
    ++v3;
  }
  KeReleaseSpinLock(this + 5, v4);
  if ( v3 < dword_14026914C )
    return 0;
  v8 = qword_140269450 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors);
  if ( *(_DWORD *)v8 < 0x20u )
  {
    v8 = 0;
    v10 = 48;
    goto LABEL_9;
  }
  if ( *(_BYTE *)(v8 + 8) )
  {
    v19 = (struct _NPAGED_LOOKASIDE_LIST *)(v8 + 64);
    if ( *(_BYTE *)(v8 + 9) )
      Pool2 = (__int64)ExAllocateFromNPagedLookasideList(v19);
    else
      Pool2 = (__int64)ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v19);
LABEL_17:
    if ( Pool2 )
      goto LABEL_18;
    goto LABEL_16;
  }
  if ( (int)*(_QWORD *)(v8 + 88) > (int)HIDWORD(*(_QWORD *)(v8 + 88)) )
  {
    v12 = _InterlockedDecrement((volatile signed __int32 *)(v8 + 88));
    if ( v12 >= *(_DWORD *)(v8 + 92) && v12 >= 0 )
    {
      Pool2 = (__int64)ExpInterlockedPopEntrySList((PSLIST_HEADER)(v8 + 64));
      goto LABEL_17;
    }
    _InterlockedIncrement((volatile signed __int32 *)(v8 + 88));
  }
LABEL_16:
  v10 = *(unsigned int *)(v8 + 4);
LABEL_9:
  Pool2 = ExAllocatePool2(66, v10, 1766871885, v9);
  if ( (Pool2 & 0xF) != 0 )
    goto LABEL_44;
  if ( !Pool2 )
    return 0;
LABEL_18:
  *(_QWORD *)Pool2 = v8;
  v13 = (_DWORD *)(Pool2 + 16);
  if ( Pool2 == -16 )
    return 0;
  v14 = (unsigned int *)(qword_140269448 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors));
  if ( v2 > (unsigned __int64)*v14 )
  {
    v14 = 0;
    v16 = v2 + 16LL;
    goto LABEL_21;
  }
  if ( !*((_BYTE *)v14 + 8) )
  {
    if ( (int)*((_QWORD *)v14 + 11) > (int)HIDWORD(*((_QWORD *)v14 + 11)) )
    {
      v18 = _InterlockedDecrement((volatile signed __int32 *)v14 + 22);
      if ( v18 >= (int)v14[23] && v18 >= 0 )
      {
        v17 = (__int64)ExpInterlockedPopEntrySList((PSLIST_HEADER)v14 + 4);
        goto LABEL_29;
      }
      _InterlockedIncrement((volatile signed __int32 *)v14 + 22);
    }
LABEL_28:
    v16 = v14[1];
LABEL_21:
    v17 = ExAllocatePool2(66, v16, 1766871885, v15);
    if ( (v17 & 0xF) == 0 )
    {
      if ( !v17 )
        goto LABEL_31;
      goto LABEL_30;
    }
LABEL_44:
    MsUnsupportedOperationBugCheck("Lookaside list allocation must be double quad aligned.");
  }
  v20 = (struct _NPAGED_LOOKASIDE_LIST *)(v14 + 16);
  if ( *((_BYTE *)v14 + 9) )
    v17 = (__int64)ExAllocateFromNPagedLookasideList(v20);
  else
    v17 = (__int64)ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v20);
LABEL_29:
  if ( !v17 )
    goto LABEL_28;
LABEL_30:
  *(_QWORD *)v17 = v14;
  v17 += 16;
LABEL_31:
  *(_QWORD *)v13 = v17;
  if ( !v17 )
  {
    CmsLookasides::Free(v13);
    return 0;
  }
  result = (struct _SmsMergeState *)v13;
  v13[2] = v2;
  v13[6] = 0;
  v13[3] = 0;
  return result;
}

```

## disassembly

```asm
0x14008cba0  push    rbx
0x14008cba2  push    rbp
0x14008cba3  push    rsi
0x14008cba4  push    rdi
0x14008cba5  sub     rsp, 28h
0x14008cba9  mov     rbx, rcx
0x14008cbac  xor     esi, esi
0x14008cbae  add     rcx, 28h ; '('; SpinLock
0x14008cbb2  xor     edi, edi
0x14008cbb4  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14008cbbb  nop     dword ptr [rax+rax+00h]
0x14008cbc0  mov     rdx, [rbx+58h]
0x14008cbc4  mov     [rbx+30h], al
0x14008cbc7  test    rdx, rdx
0x14008cbca  jz      short loc_14008CBF6
0x14008cbcc  nop     dword ptr [rax+00h]
0x14008cbd0  mov     r8d, [rdx+24h]
0x14008cbd4  add     r8d, esi
0x14008cbd7  cmp     r8d, 40000h
0x14008cbde  ja      short loc_14008CBF6
0x14008cbe0  cmp     edi, cs:MsPerfParams
0x14008cbe6  jnb     short loc_14008CBF6
0x14008cbe8  mov     rdx, [rdx+30h]
0x14008cbec  inc     edi
0x14008cbee  mov     esi, r8d
0x14008cbf1  test    rdx, rdx
0x14008cbf4  jnz     short loc_14008CBD0
0x14008cbf6  movzx   edx, al; NewIrql
0x14008cbf9  mov     [rsp+48h+arg_0], r14
0x14008cbfe  lea     rcx, [rbx+28h]; SpinLock
0x14008cc02  call    cs:__imp_KeReleaseSpinLock
0x14008cc09  nop     dword ptr [rax+rax+00h]
0x14008cc0e  cmp     edi, cs:dword_14026914C
0x14008cc14  jnb     short loc_14008CC27
0x14008cc16  xor     eax, eax
0x14008cc18  mov     r14, [rsp+48h+arg_0]
0x14008cc1d  add     rsp, 28h
0x14008cc21  pop     rdi
0x14008cc22  pop     rsi
0x14008cc23  pop     rbp
0x14008cc24  pop     rbx
0x14008cc25  retn
0x14008cc27  xor     ecx, ecx; ProcNumber
0x14008cc29  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14008cc30  nop     dword ptr [rax+rax+00h]
0x14008cc35  xor     edx, edx
0x14008cc37  mov     r14d, 0FFFFFFFFh
0x14008cc3d  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x14008cc43  lea     rbx, [rdx+rdx*2]
0x14008cc47  shl     rbx, 6
0x14008cc4b  add     rbx, cs:qword_140269450
0x14008cc52  cmp     dword ptr [rbx], 20h ; ' '
0x14008cc55  jnb     short loc_14008CC84
0x14008cc57  xor     ebx, ebx
0x14008cc59  mov     edx, 30h ; '0'
0x14008cc5e  mov     ecx, 42h ; 'B'
0x14008cc63  mov     r8d, 6950534Dh
0x14008cc69  call    cs:__imp_ExAllocatePool2
0x14008cc70  nop     dword ptr [rax+rax+00h]
0x14008cc75  test    al, 0Fh
0x14008cc77  jnz     loc_1402013E2
0x14008cc7d  test    rax, rax
0x14008cc80  jz      short loc_14008CC16
0x14008cc82  jmp     short loc_14008CCC4
0x14008cc84  cmp     byte ptr [rbx+8], 0
0x14008cc88  jnz     loc_14008CDAD
0x14008cc8e  mov     rcx, [rbx+58h]
0x14008cc92  mov     rax, rcx
0x14008cc95  shr     rax, 20h
0x14008cc99  cmp     ecx, eax
0x14008cc9b  jle     short loc_14008CCBA
0x14008cc9d  nop
0x14008cc9e  mov     ecx, r14d
0x14008cca1  lock xadd [rbx+58h], ecx
0x14008cca6  nop
0x14008cca7  dec     ecx
0x14008cca9  mov     eax, [rbx+5Ch]
0x14008ccac  cmp     ecx, eax
0x14008ccae  jge     loc_14008CDCC
0x14008ccb4  nop
0x14008ccb5  lock inc dword ptr [rbx+58h]
0x14008ccb9  nop
0x14008ccba  mov     edx, [rbx+4]
0x14008ccbd  jmp     short loc_14008CC5E
0x14008ccbf  test    rax, rax
0x14008ccc2  jz      short loc_14008CCBA
0x14008ccc4  mov     [rax], rbx
0x14008ccc7  lea     rbx, [rax+10h]
0x14008cccb  test    rbx, rbx
0x14008ccce  jz      loc_14008CC16
0x14008ccd4  xor     ecx, ecx; ProcNumber
0x14008ccd6  mov     ebp, esi
0x14008ccd8  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14008ccdf  nop     dword ptr [rax+rax+00h]
0x14008cce4  xor     edx, edx
0x14008cce6  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x14008ccec  lea     rdi, [rdx+rdx*2]
0x14008ccf0  shl     rdi, 6
0x14008ccf4  add     rdi, cs:qword_140269448
0x14008ccfb  mov     eax, [rdi]
0x14008ccfd  cmp     rbp, rax
0x14008cd00  jbe     short loc_14008CD2E
0x14008cd02  xor     edi, edi
0x14008cd04  lea     rdx, [rbp+10h]
0x14008cd08  mov     ecx, 42h ; 'B'
0x14008cd0d  mov     r8d, 6950534Dh
0x14008cd13  call    cs:__imp_ExAllocatePool2
0x14008cd1a  nop     dword ptr [rax+rax+00h]
0x14008cd1f  test    al, 0Fh
0x14008cd21  jnz     loc_1402013E2
0x14008cd27  test    rax, rax
0x14008cd2a  jz      short loc_14008CD75
0x14008cd2c  jmp     short loc_14008CD6E
0x14008cd2e  cmp     byte ptr [rdi+8], 0
0x14008cd32  jnz     loc_14008CDE9
0x14008cd38  mov     rcx, [rdi+58h]
0x14008cd3c  mov     rax, rcx
0x14008cd3f  shr     rax, 20h
0x14008cd43  cmp     ecx, eax
0x14008cd45  jle     short loc_14008CD64
0x14008cd47  nop
0x14008cd48  lock xadd [rdi+58h], r14d
0x14008cd4e  nop
0x14008cd4f  dec     r14d
0x14008cd52  mov     eax, [rdi+5Ch]
0x14008cd55  cmp     r14d, eax
0x14008cd58  jge     loc_14008CE08
0x14008cd5e  nop
0x14008cd5f  lock inc dword ptr [rdi+58h]
0x14008cd63  nop
0x14008cd64  mov     edx, [rdi+4]
0x14008cd67  jmp     short loc_14008CD08
0x14008cd69  test    rax, rax
0x14008cd6c  jz      short loc_14008CD64
0x14008cd6e  mov     [rax], rdi
0x14008cd71  add     rax, 10h
0x14008cd75  mov     [rbx], rax
0x14008cd78  test    rax, rax
0x14008cd7b  jz      short loc_14008CDA0
0x14008cd7d  mov     r14, [rsp+48h+arg_0]
0x14008cd82  mov     rax, rbx
0x14008cd85  mov     [rbx+8], esi
0x14008cd88  mov     dword ptr [rbx+18h], 0
0x14008cd8f  mov     dword ptr [rbx+0Ch], 0
0x14008cd96  add     rsp, 28h
0x14008cd9a  pop     rdi
0x14008cd9b  pop     rsi
0x14008cd9c  pop     rbp
0x14008cd9d  pop     rbx
0x14008cd9e  retn
0x14008cda0  mov     rcx, rbx; void *
0x14008cda3  call    ?Free@CmsLookasides@@SAXPEAX@Z; CmsLookasides::Free(void *)
0x14008cda8  jmp     loc_14008CC16
0x14008cdad  cmp     byte ptr [rbx+9], 0
0x14008cdb1  lea     rcx, [rbx+40h]; Lookaside
0x14008cdb5  jz      loc_1402013BE
0x14008cdbb  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14008cdc2  nop     dword ptr [rax+rax+00h]
0x14008cdc7  jmp     loc_14008CCBF
0x14008cdcc  test    ecx, ecx
0x14008cdce  js      loc_14008CCB4
0x14008cdd4  lea     rcx, [rbx+40h]; ListHead
0x14008cdd8  call    cs:__imp_ExpInterlockedPopEntrySList
0x14008cddf  nop     dword ptr [rax+rax+00h]
0x14008cde4  jmp     loc_14008CCBF
0x14008cde9  cmp     byte ptr [rdi+9], 0
0x14008cded  lea     rcx, [rdi+40h]; Lookaside
0x14008cdf1  jz      loc_1402013D0
0x14008cdf7  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14008cdfe  nop     dword ptr [rax+rax+00h]
0x14008ce03  jmp     loc_14008CD69
0x14008ce08  test    r14d, r14d
0x14008ce0b  js      loc_14008CD5E
0x14008ce11  lea     rcx, [rdi+40h]; ListHead
0x14008ce15  call    cs:__imp_ExpInterlockedPopEntrySList
0x14008ce1c  nop     dword ptr [rax+rax+00h]
0x14008ce21  jmp     loc_14008CD69
0x1402013be  call    cs:__imp_ExAllocateFromPagedLookasideList
0x1402013c5  nop     dword ptr [rax+rax+00h]
0x1402013ca  nop
0x1402013cb  jmp     loc_14008CCBF
0x1402013d0  call    cs:__imp_ExAllocateFromPagedLookasideList
0x1402013d7  nop     dword ptr [rax+rax+00h]
0x1402013dc  nop
0x1402013dd  jmp     loc_14008CD69
0x1402013e2  lea     rcx, aLookasideListA; "Lookaside list allocation must be doubl"...
0x1402013e9  call    ?MsUnsupportedOperationBugCheck@@YAXPEBD@Z; MsUnsupportedOperationBugCheck(char const *)
```
