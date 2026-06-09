# NdisAllocateNetBuffer

- ea: `0x140032ee0`
- end: `0x14003322c`
- name: `NdisAllocateNetBuffer`
- size: `844`
- prototype: `PNET_BUFFER __stdcall(NDIS_HANDLE PoolHandle, PMDL MdlChain, ULONG DataOffset, SIZE_T DataLength)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140030bc0`
- `0x140031090`

## callees

- `0x140032ee0`
- `0x140033510`

## import_xrefs

- `ntoskrnl!DbgPrint` at `0x1400331f1`
- `ntoskrnl!DbgPrint` at `0x1400331f1`
- `ntoskrnl!ExAllocatePool2` at `0x140033167`
- `ntoskrnl!ExAllocatePool2` at `0x140033167`
- `ntoskrnl!KeReleaseSpinLock` at `0x140032fdc`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400330e8`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400331d3`
- `ntoskrnl!KeReleaseSpinLock` at `0x140032fdc`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400330e8`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400331d3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140032f62`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400330b1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140033194`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140032f62`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400330b1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140033194`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x140032fbe`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x140032fbe`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140032ff3`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400330fb`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140033130`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140032ff3`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400330fb`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140033130`
- `ntoskrnl!ExQueryDepthSList` at `0x140033209`
- `ntoskrnl!ExQueryDepthSList` at `0x140033209`

## pseudocode

```c
PNET_BUFFER __stdcall NdisAllocateNetBuffer(NDIS_HANDLE PoolHandle, PMDL MdlChain, ULONG DataOffset, SIZE_T DataLength)
{
  int v4; // r12d
  PSLIST_ENTRY v8; // rbx
  unsigned int Number; // edi
  unsigned __int64 v10; // rbx
  char *v11; // rdi
  KIRQL v12; // r13
  ULONG v13; // edx
  PMDL v14; // rcx
  ULONG ByteCount; // eax
  KIRQL v17; // al
  __int64 v18; // rdx
  unsigned __int64 v19; // rax
  struct _SLIST_ENTRY *Pool2; // rax
  KIRQL v21; // al
  __int64 v22; // rdx
  _QWORD *v23; // rcx
  KIRQL v24; // r8
  _QWORD *v25; // rax
  unsigned int v26; // [rsp+90h] [rbp+8h]

  v4 = DataLength;
  v8 = 0;
  if ( !PoolHandle )
    return (PNET_BUFFER)v8;
  if ( (*((_DWORD *)PoolHandle + 20) & 1) != 0 )
  {
    DbgPrint("NdisAllocateNetBuffer: Pool %p wrong pool type.\n", PoolHandle);
    return (PNET_BUFFER)v8;
  }
  if ( (*((_DWORD *)PoolHandle + 1) & 1) != 0 )
  {
    v8 = (PSLIST_ENTRY)ndisPplAllocateFromSpecialPool((const struct _NDIS_POOL_HEADER *)PoolHandle);
    goto LABEL_10;
  }
  Number = KeGetPcr()->Prcb.Number;
  v26 = Number;
  if ( ndisMaxNumberOfProcessors != 1 )
  {
    v10 = (unsigned __int64)Number << 8;
    v11 = (char *)PoolHandle + v10 + 384;
    if ( !v11[216] )
    {
      v12 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v11 + 26);
      if ( !v11[216] )
      {
        ExInitializeLookasideListEx(
          (PLOOKASIDE_LIST_EX)v11,
          ndisAllocateFromNPagedPool,
          *(PFREE_FUNCTION_EX *)&v11[-v10 - 200],
          NonPagedPoolNx,
          0,
          *(unsigned int *)&v11[-v10 - 212],
          *(_DWORD *)&v11[-v10 - 216],
          0x400u);
        v11[216] = 1;
      }
      KeReleaseSpinLock((PKSPIN_LOCK)v11 + 26, v12);
    }
    _InterlockedIncrement((volatile signed __int32 *)v11 + 5);
    v8 = ExpInterlockedPopEntrySList(*((PSLIST_HEADER *)v11 + 24));
    if ( v8 )
      goto LABEL_10;
    if ( ExQueryDepthSList(*((PSLIST_HEADER *)v11 + 25)) >= 0xAu )
    {
      v17 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v11 + 26);
      v18 = *((_QWORD *)v11 + 24);
      *((_QWORD *)v11 + 24) = *((_QWORD *)v11 + 25);
      *((_QWORD *)v11 + 25) = v18;
      KeReleaseSpinLock((PKSPIN_LOCK)v11 + 26, v17);
      v8 = ExpInterlockedPopEntrySList(*((PSLIST_HEADER *)v11 + 24));
      if ( v8 )
        goto LABEL_10;
    }
    _InterlockedIncrement((volatile signed __int32 *)v11 + 6);
    Number = v26;
  }
  _InterlockedIncrement((volatile signed __int32 *)PoolHandle + 37);
  v8 = ExpInterlockedPopEntrySList((PSLIST_HEADER)PoolHandle + 8);
  if ( v8 )
  {
LABEL_28:
    *((_DWORD *)&v8[-1].Next + 2) = Number;
    goto LABEL_10;
  }
  _InterlockedIncrement((volatile signed __int32 *)PoolHandle + 38);
  v19 = *((unsigned int *)PoolHandle + 43);
  if ( v19 + 32 >= v19 )
  {
    Pool2 = (struct _SLIST_ENTRY *)ExAllocatePool2(66, v19 + 32, *((unsigned int *)PoolHandle + 42));
    if ( Pool2 )
    {
      v8 = Pool2 + 2;
      Pool2->Next = 0;
      if ( Pool2 == (struct _SLIST_ENTRY *)-32LL )
        goto LABEL_10;
      Pool2->Next = (_SLIST_ENTRY *)PoolHandle;
      v21 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)PoolHandle + 1);
      v22 = *((_QWORD *)PoolHandle + 2);
      v23 = (char *)PoolHandle + 16;
      v24 = v21;
      if ( *(NDIS_HANDLE *)(v22 + 8) != (char *)PoolHandle + 16 )
        __fastfail(3u);
      v25 = &v8[-2].Next + 1;
      *v25 = v22;
      v25[1] = v23;
      *(_QWORD *)(v22 + 8) = (char *)v8 - 24;
      *v23 = (char *)v8 - 24;
      KeReleaseSpinLock((PKSPIN_LOCK)PoolHandle + 1, v24);
      goto LABEL_28;
    }
  }
  v8 = 0;
LABEL_10:
  if ( !v8 )
    return 0;
  *((_QWORD *)&v8->Next + 1) = 0;
  v13 = DataOffset;
  LODWORD(v8[1].Next) = 0;
  v14 = MdlChain;
  v8[2].Next = 0;
  *((_DWORD *)&v8[2].Next + 2) = 0;
  *((_DWORD *)&v8[1].Next + 2) = 0;
  *((_QWORD *)&v8[4].Next + 1) = 0;
  v8[4].Next = 0;
  *((_QWORD *)&v8[8].Next + 1) = 0;
  v8[8].Next = 0;
  v8->Next = 0;
  *((_QWORD *)&v8[3].Next + 1) = PoolHandle;
  LODWORD(v8[3].Next) = 0;
  for ( *((_QWORD *)&v8[10].Next + 1) = 0; v14; v13 -= ByteCount )
  {
    ByteCount = v14->ByteCount;
    if ( v13 < ByteCount )
      break;
    v14 = v14->Next;
  }
  v8[2].Next = (_SLIST_ENTRY *)MdlChain;
  *((_DWORD *)&v8[2].Next + 2) = DataOffset;
  *((_DWORD *)&v8[1].Next + 2) = v4;
  *((_QWORD *)&v8->Next + 1) = v14;
  LODWORD(v8[1].Next) = v13;
  return (PNET_BUFFER)v8;
}

```

## disassembly

```asm
0x140032ee0  push    rbx
0x140032ee2  push    rbp
0x140032ee3  push    rsi
0x140032ee4  push    rdi
0x140032ee5  push    r12
0x140032ee7  push    r13
0x140032ee9  push    r14
0x140032eeb  push    r15
0x140032eed  sub     rsp, 48h
0x140032ef1  xor     r13d, r13d
0x140032ef4  mov     r12, r9
0x140032ef7  mov     r15d, r8d
0x140032efa  mov     rbp, rdx
0x140032efd  mov     rsi, rcx
0x140032f00  mov     ebx, r13d
0x140032f03  test    rcx, rcx
0x140032f06  jz      loc_140033077
0x140032f0c  mov     eax, [rcx+50h]
0x140032f0f  test    al, 1
0x140032f11  jnz     loc_1400331E7
0x140032f17  mov     eax, [rcx+4]
0x140032f1a  test    al, 1
0x140032f1c  jnz     loc_14003309D
0x140032f22  mov     edi, gs:1A4h
0x140032f2a  cmp     cs:?ndisMaxNumberOfProcessors@@3KA, 1; ulong ndisMaxNumberOfProcessors
0x140032f31  mov     [rsp+88h+arg_0], edi
0x140032f38  jz      loc_140033121
0x140032f3e  mov     ebx, edi
0x140032f40  lea     rdi, [rcx+180h]
0x140032f47  shl     rbx, 8
0x140032f4b  add     rdi, rbx
0x140032f4e  cmp     [rdi+0D8h], r13b
0x140032f55  jnz     loc_140032FE8
0x140032f5b  lea     rcx, [rdi+0D0h]; SpinLock
0x140032f62  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140032f69  nop     dword ptr [rax+rax+00h]
0x140032f6e  cmp     byte ptr [rdi+0D8h], 0
0x140032f75  movzx   r13d, al
0x140032f79  jnz     short loc_140032FD1
0x140032f7b  mov     [rsp+88h+Depth], 400h; Depth
0x140032f82  lea     rdx, ndisAllocateFromNPagedPool; Allocate
0x140032f89  mov     r8, rdi
0x140032f8c  mov     r9d, 200h; PoolType
0x140032f92  sub     r8, rbx
0x140032f95  mov     ecx, [r8-0D4h]
0x140032f9c  mov     eax, [r8-0D8h]
0x140032fa3  mov     r8, [r8-0C8h]; Free
0x140032faa  mov     [rsp+88h+Tag], eax; Tag
0x140032fae  mov     [rsp+88h+Size], rcx; Size
0x140032fb3  mov     rcx, rdi; Lookaside
0x140032fb6  mov     [rsp+88h+Flags], 0; Flags
0x140032fbe  call    cs:__imp_ExInitializeLookasideListEx
0x140032fc5  nop     dword ptr [rax+rax+00h]
0x140032fca  mov     byte ptr [rdi+0D8h], 1
0x140032fd1  movzx   edx, r13b; NewIrql
0x140032fd5  lea     rcx, [rdi+0D0h]; SpinLock
0x140032fdc  call    cs:__imp_KeReleaseSpinLock
0x140032fe3  nop     dword ptr [rax+rax+00h]
0x140032fe8  lock inc dword ptr [rdi+14h]
0x140032fec  mov     rcx, [rdi+0C0h]; ListHead
0x140032ff3  call    cs:__imp_ExpInterlockedPopEntrySList
0x140032ffa  nop     dword ptr [rax+rax+00h]
0x140032fff  mov     rbx, rax
0x140033002  test    rax, rax
0x140033005  jz      loc_140033202
0x14003300b  xor     r13d, r13d
0x14003300e  test    rbx, rbx
0x140033011  jz      short loc_14003308C
0x140033013  mov     [rbx+8], r13
0x140033017  mov     edx, r15d
0x14003301a  mov     [rbx+10h], r13d
0x14003301e  mov     rcx, rbp
0x140033021  mov     [rbx+20h], r13
0x140033025  mov     [rbx+28h], r13d
0x140033029  mov     [rbx+18h], r13d
0x14003302d  mov     [rbx+48h], r13
0x140033031  mov     [rbx+40h], r13
0x140033035  mov     [rbx+88h], r13
0x14003303c  mov     [rbx+80h], r13
0x140033043  mov     [rbx], r13
0x140033046  mov     [rbx+38h], rsi
0x14003304a  mov     dword ptr [rbx+30h], 0
0x140033051  mov     [rbx+0A8h], r13
0x140033058  test    rbp, rbp
0x14003305b  jz      short loc_140033064
0x14003305d  mov     eax, [rcx+28h]
0x140033060  cmp     edx, eax
0x140033062  jnb     short loc_140033091
0x140033064  mov     [rbx+20h], rbp
0x140033068  mov     [rbx+28h], r15d
0x14003306c  mov     [rbx+18h], r12d
0x140033070  mov     [rbx+8], rcx
0x140033074  mov     [rbx+10h], edx
0x140033077  mov     rax, rbx
0x14003307a  add     rsp, 48h
0x14003307e  pop     r15
0x140033080  pop     r14
0x140033082  pop     r13
0x140033084  pop     r12
0x140033086  pop     rdi
0x140033087  pop     rsi
0x140033088  pop     rbp
0x140033089  pop     rbx
0x14003308a  retn
0x14003308c  mov     rbx, r13
0x14003308f  jmp     short loc_140033077
0x140033091  mov     rcx, [rcx]; struct _NDIS_POOL_HEADER *
0x140033094  sub     edx, eax
0x140033096  test    rcx, rcx
0x140033099  jnz     short loc_14003305D
0x14003309b  jmp     short loc_140033064
0x14003309d  call    ?ndisPplAllocateFromSpecialPool@@YAPEAXPEBU_NDIS_POOL_HEADER@@@Z; ndisPplAllocateFromSpecialPool(_NDIS_POOL_HEADER const *)
0x1400330a2  mov     rbx, rax
0x1400330a5  jmp     loc_14003300E
0x1400330aa  lea     rcx, [rdi+0D0h]; SpinLock
0x1400330b1  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400330b8  nop     dword ptr [rax+rax+00h]
0x1400330bd  mov     rdx, [rdi+0C0h]
0x1400330c4  lea     rcx, [rdi+0D0h]; SpinLock
0x1400330cb  movzx   r8d, al
0x1400330cf  mov     rax, [rdi+0C8h]
0x1400330d6  mov     [rdi+0C0h], rax
0x1400330dd  mov     [rdi+0C8h], rdx
0x1400330e4  movzx   edx, r8b; NewIrql
0x1400330e8  call    cs:__imp_KeReleaseSpinLock
0x1400330ef  nop     dword ptr [rax+rax+00h]
0x1400330f4  mov     rcx, [rdi+0C0h]; ListHead
0x1400330fb  call    cs:__imp_ExpInterlockedPopEntrySList
0x140033102  nop     dword ptr [rax+rax+00h]
0x140033107  mov     rbx, rax
0x14003310a  test    rax, rax
0x14003310d  jnz     loc_14003300B
0x140033113  lock inc dword ptr [rdi+18h]
0x140033117  mov     edi, [rsp+88h+arg_0]
0x14003311e  xor     r13d, r13d
0x140033121  lea     r14, [rsi+80h]
0x140033128  lock inc dword ptr [r14+14h]
0x14003312d  mov     rcx, r14; ListHead
0x140033130  call    cs:__imp_ExpInterlockedPopEntrySList
0x140033137  nop     dword ptr [rax+rax+00h]
0x14003313c  mov     rbx, rax
0x14003313f  test    rax, rax
0x140033142  jnz     loc_1400331DF
0x140033148  lock inc dword ptr [r14+18h]
0x14003314d  mov     eax, [r14+2Ch]
0x140033151  lea     rdx, [rax+20h]
0x140033155  cmp     rdx, rax
0x140033158  jb      loc_140033224
0x14003315e  mov     r8d, [r14+28h]
0x140033162  mov     ecx, 42h ; 'B'
0x140033167  call    cs:__imp_ExAllocatePool2
0x14003316e  nop     dword ptr [rax+rax+00h]
0x140033173  test    rax, rax
0x140033176  jz      loc_140033224
0x14003317c  lea     rbx, [rax+20h]
0x140033180  mov     [rax], r13
0x140033183  test    rbx, rbx
0x140033186  jz      loc_14003300B
0x14003318c  lea     rcx, [rsi+8]; SpinLock
0x140033190  mov     [rbx-20h], rsi
0x140033194  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14003319b  nop     dword ptr [rax+rax+00h]
0x1400331a0  mov     rdx, [rsi+10h]
0x1400331a4  lea     rcx, [rsi+10h]
0x1400331a8  movzx   r8d, al
0x1400331ac  cmp     [rdx+8], rcx
0x1400331b0  jz      short loc_1400331B9
0x1400331b2  mov     ecx, 3
0x1400331b7  int     29h; Win8: RtlFailFast(ecx)
0x1400331b9  lea     rax, [rbx-18h]
0x1400331bd  mov     [rax], rdx
0x1400331c0  mov     [rax+8], rcx
0x1400331c4  mov     [rdx+8], rax
0x1400331c8  movzx   edx, r8b; NewIrql
0x1400331cc  mov     [rcx], rax
0x1400331cf  lea     rcx, [rsi+8]; SpinLock
0x1400331d3  call    cs:__imp_KeReleaseSpinLock
0x1400331da  nop     dword ptr [rax+rax+00h]
0x1400331df  mov     [rbx-8], edi
0x1400331e2  jmp     loc_14003300B
0x1400331e7  mov     rdx, rsi
0x1400331ea  lea     rcx, aNdisallocatene_1; "NdisAllocateNetBuffer: Pool %p wrong po"...
0x1400331f1  call    cs:__imp_DbgPrint
0x1400331f8  nop     dword ptr [rax+rax+00h]
0x1400331fd  jmp     loc_140033077
0x140033202  mov     rcx, [rdi+0C8h]; SListHead
0x140033209  call    cs:__imp_ExQueryDepthSList
0x140033210  nop     dword ptr [rax+rax+00h]
0x140033215  cmp     ax, 0Ah
0x140033219  jb      loc_140033113
0x14003321f  jmp     loc_1400330AA
0x140033224  mov     rbx, r13
0x140033227  jmp     loc_14003300B
```
