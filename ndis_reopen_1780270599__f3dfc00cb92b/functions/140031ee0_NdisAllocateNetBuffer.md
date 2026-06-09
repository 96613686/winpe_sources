# NdisAllocateNetBuffer

- ea: `0x140031ee0`
- end: `0x14003222c`
- name: `NdisAllocateNetBuffer`
- size: `844`
- prototype: `PNET_BUFFER __stdcall(NDIS_HANDLE PoolHandle, PMDL MdlChain, ULONG DataOffset, SIZE_T DataLength)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140030860`
- `0x140031590`

## callees

- `0x140031ee0`
- `0x140032510`

## import_xrefs

- `ntoskrnl!DbgPrint` at `0x1400321f1`
- `ntoskrnl!DbgPrint` at `0x1400321f1`
- `ntoskrnl!ExAllocatePool2` at `0x140032167`
- `ntoskrnl!ExAllocatePool2` at `0x140032167`
- `ntoskrnl!KeReleaseSpinLock` at `0x140031fdc`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400320e8`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400321d3`
- `ntoskrnl!KeReleaseSpinLock` at `0x140031fdc`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400320e8`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400321d3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140031f62`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400320b1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140032194`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140031f62`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400320b1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140032194`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x140031fbe`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x140031fbe`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140031ff3`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400320fb`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140032130`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140031ff3`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400320fb`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140032130`
- `ntoskrnl!ExQueryDepthSList` at `0x140032209`
- `ntoskrnl!ExQueryDepthSList` at `0x140032209`

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
0x140031ee0  push    rbx
0x140031ee2  push    rbp
0x140031ee3  push    rsi
0x140031ee4  push    rdi
0x140031ee5  push    r12
0x140031ee7  push    r13
0x140031ee9  push    r14
0x140031eeb  push    r15
0x140031eed  sub     rsp, 48h
0x140031ef1  xor     r13d, r13d
0x140031ef4  mov     r12, r9
0x140031ef7  mov     r15d, r8d
0x140031efa  mov     rbp, rdx
0x140031efd  mov     rsi, rcx
0x140031f00  mov     ebx, r13d
0x140031f03  test    rcx, rcx
0x140031f06  jz      loc_140032077
0x140031f0c  mov     eax, [rcx+50h]
0x140031f0f  test    al, 1
0x140031f11  jnz     loc_1400321E7
0x140031f17  mov     eax, [rcx+4]
0x140031f1a  test    al, 1
0x140031f1c  jnz     loc_14003209D
0x140031f22  mov     edi, gs:1A4h
0x140031f2a  cmp     cs:?ndisMaxNumberOfProcessors@@3KA, 1; ulong ndisMaxNumberOfProcessors
0x140031f31  mov     [rsp+88h+arg_0], edi
0x140031f38  jz      loc_140032121
0x140031f3e  mov     ebx, edi
0x140031f40  lea     rdi, [rcx+180h]
0x140031f47  shl     rbx, 8
0x140031f4b  add     rdi, rbx
0x140031f4e  cmp     [rdi+0D8h], r13b
0x140031f55  jnz     loc_140031FE8
0x140031f5b  lea     rcx, [rdi+0D0h]; SpinLock
0x140031f62  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140031f69  nop     dword ptr [rax+rax+00h]
0x140031f6e  cmp     byte ptr [rdi+0D8h], 0
0x140031f75  movzx   r13d, al
0x140031f79  jnz     short loc_140031FD1
0x140031f7b  mov     [rsp+88h+Depth], 400h; Depth
0x140031f82  lea     rdx, ndisAllocateFromNPagedPool; Allocate
0x140031f89  mov     r8, rdi
0x140031f8c  mov     r9d, 200h; PoolType
0x140031f92  sub     r8, rbx
0x140031f95  mov     ecx, [r8-0D4h]
0x140031f9c  mov     eax, [r8-0D8h]
0x140031fa3  mov     r8, [r8-0C8h]; Free
0x140031faa  mov     [rsp+88h+Tag], eax; Tag
0x140031fae  mov     [rsp+88h+Size], rcx; Size
0x140031fb3  mov     rcx, rdi; Lookaside
0x140031fb6  mov     [rsp+88h+Flags], 0; Flags
0x140031fbe  call    cs:__imp_ExInitializeLookasideListEx
0x140031fc5  nop     dword ptr [rax+rax+00h]
0x140031fca  mov     byte ptr [rdi+0D8h], 1
0x140031fd1  movzx   edx, r13b; NewIrql
0x140031fd5  lea     rcx, [rdi+0D0h]; SpinLock
0x140031fdc  call    cs:__imp_KeReleaseSpinLock
0x140031fe3  nop     dword ptr [rax+rax+00h]
0x140031fe8  lock inc dword ptr [rdi+14h]
0x140031fec  mov     rcx, [rdi+0C0h]; ListHead
0x140031ff3  call    cs:__imp_ExpInterlockedPopEntrySList
0x140031ffa  nop     dword ptr [rax+rax+00h]
0x140031fff  mov     rbx, rax
0x140032002  test    rax, rax
0x140032005  jz      loc_140032202
0x14003200b  xor     r13d, r13d
0x14003200e  test    rbx, rbx
0x140032011  jz      short loc_14003208C
0x140032013  mov     [rbx+8], r13
0x140032017  mov     edx, r15d
0x14003201a  mov     [rbx+10h], r13d
0x14003201e  mov     rcx, rbp
0x140032021  mov     [rbx+20h], r13
0x140032025  mov     [rbx+28h], r13d
0x140032029  mov     [rbx+18h], r13d
0x14003202d  mov     [rbx+48h], r13
0x140032031  mov     [rbx+40h], r13
0x140032035  mov     [rbx+88h], r13
0x14003203c  mov     [rbx+80h], r13
0x140032043  mov     [rbx], r13
0x140032046  mov     [rbx+38h], rsi
0x14003204a  mov     dword ptr [rbx+30h], 0
0x140032051  mov     [rbx+0A8h], r13
0x140032058  test    rbp, rbp
0x14003205b  jz      short loc_140032064
0x14003205d  mov     eax, [rcx+28h]
0x140032060  cmp     edx, eax
0x140032062  jnb     short loc_140032091
0x140032064  mov     [rbx+20h], rbp
0x140032068  mov     [rbx+28h], r15d
0x14003206c  mov     [rbx+18h], r12d
0x140032070  mov     [rbx+8], rcx
0x140032074  mov     [rbx+10h], edx
0x140032077  mov     rax, rbx
0x14003207a  add     rsp, 48h
0x14003207e  pop     r15
0x140032080  pop     r14
0x140032082  pop     r13
0x140032084  pop     r12
0x140032086  pop     rdi
0x140032087  pop     rsi
0x140032088  pop     rbp
0x140032089  pop     rbx
0x14003208a  retn
0x14003208c  mov     rbx, r13
0x14003208f  jmp     short loc_140032077
0x140032091  mov     rcx, [rcx]; struct _NDIS_POOL_HEADER *
0x140032094  sub     edx, eax
0x140032096  test    rcx, rcx
0x140032099  jnz     short loc_14003205D
0x14003209b  jmp     short loc_140032064
0x14003209d  call    ?ndisPplAllocateFromSpecialPool@@YAPEAXPEBU_NDIS_POOL_HEADER@@@Z; ndisPplAllocateFromSpecialPool(_NDIS_POOL_HEADER const *)
0x1400320a2  mov     rbx, rax
0x1400320a5  jmp     loc_14003200E
0x1400320aa  lea     rcx, [rdi+0D0h]; SpinLock
0x1400320b1  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400320b8  nop     dword ptr [rax+rax+00h]
0x1400320bd  mov     rdx, [rdi+0C0h]
0x1400320c4  lea     rcx, [rdi+0D0h]; SpinLock
0x1400320cb  movzx   r8d, al
0x1400320cf  mov     rax, [rdi+0C8h]
0x1400320d6  mov     [rdi+0C0h], rax
0x1400320dd  mov     [rdi+0C8h], rdx
0x1400320e4  movzx   edx, r8b; NewIrql
0x1400320e8  call    cs:__imp_KeReleaseSpinLock
0x1400320ef  nop     dword ptr [rax+rax+00h]
0x1400320f4  mov     rcx, [rdi+0C0h]; ListHead
0x1400320fb  call    cs:__imp_ExpInterlockedPopEntrySList
0x140032102  nop     dword ptr [rax+rax+00h]
0x140032107  mov     rbx, rax
0x14003210a  test    rax, rax
0x14003210d  jnz     loc_14003200B
0x140032113  lock inc dword ptr [rdi+18h]
0x140032117  mov     edi, [rsp+88h+arg_0]
0x14003211e  xor     r13d, r13d
0x140032121  lea     r14, [rsi+80h]
0x140032128  lock inc dword ptr [r14+14h]
0x14003212d  mov     rcx, r14; ListHead
0x140032130  call    cs:__imp_ExpInterlockedPopEntrySList
0x140032137  nop     dword ptr [rax+rax+00h]
0x14003213c  mov     rbx, rax
0x14003213f  test    rax, rax
0x140032142  jnz     loc_1400321DF
0x140032148  lock inc dword ptr [r14+18h]
0x14003214d  mov     eax, [r14+2Ch]
0x140032151  lea     rdx, [rax+20h]
0x140032155  cmp     rdx, rax
0x140032158  jb      loc_140032224
0x14003215e  mov     r8d, [r14+28h]
0x140032162  mov     ecx, 42h ; 'B'
0x140032167  call    cs:__imp_ExAllocatePool2
0x14003216e  nop     dword ptr [rax+rax+00h]
0x140032173  test    rax, rax
0x140032176  jz      loc_140032224
0x14003217c  lea     rbx, [rax+20h]
0x140032180  mov     [rax], r13
0x140032183  test    rbx, rbx
0x140032186  jz      loc_14003200B
0x14003218c  lea     rcx, [rsi+8]; SpinLock
0x140032190  mov     [rbx-20h], rsi
0x140032194  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14003219b  nop     dword ptr [rax+rax+00h]
0x1400321a0  mov     rdx, [rsi+10h]
0x1400321a4  lea     rcx, [rsi+10h]
0x1400321a8  movzx   r8d, al
0x1400321ac  cmp     [rdx+8], rcx
0x1400321b0  jz      short loc_1400321B9
0x1400321b2  mov     ecx, 3
0x1400321b7  int     29h; Win8: RtlFailFast(ecx)
0x1400321b9  lea     rax, [rbx-18h]
0x1400321bd  mov     [rax], rdx
0x1400321c0  mov     [rax+8], rcx
0x1400321c4  mov     [rdx+8], rax
0x1400321c8  movzx   edx, r8b; NewIrql
0x1400321cc  mov     [rcx], rax
0x1400321cf  lea     rcx, [rsi+8]; SpinLock
0x1400321d3  call    cs:__imp_KeReleaseSpinLock
0x1400321da  nop     dword ptr [rax+rax+00h]
0x1400321df  mov     [rbx-8], edi
0x1400321e2  jmp     loc_14003200B
0x1400321e7  mov     rdx, rsi
0x1400321ea  lea     rcx, aNdisallocatene_1; "NdisAllocateNetBuffer: Pool %p wrong po"...
0x1400321f1  call    cs:__imp_DbgPrint
0x1400321f8  nop     dword ptr [rax+rax+00h]
0x1400321fd  jmp     loc_140032077
0x140032202  mov     rcx, [rdi+0C8h]; SListHead
0x140032209  call    cs:__imp_ExQueryDepthSList
0x140032210  nop     dword ptr [rax+rax+00h]
0x140032215  cmp     ax, 0Ah
0x140032219  jb      loc_140032113
0x14003221f  jmp     loc_1400320AA
0x140032224  mov     rbx, r13
0x140032227  jmp     loc_14003200B
```
