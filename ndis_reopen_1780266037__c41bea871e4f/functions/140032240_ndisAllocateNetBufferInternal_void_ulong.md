# ndisAllocateNetBufferInternal(void *,ulong *)

- ea: `0x140032240`
- end: `0x140032504`
- name: `?ndisAllocateNetBufferInternal@@YAPEAU_NET_BUFFER@@PEAXPEAK@Z`
- size: `708`
- prototype: `struct _NET_BUFFER *__fastcall(void *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140031590`

## callees

- `0x140032240`
- `0x140032510`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14003244b`
- `ntoskrnl!ExAllocatePool2` at `0x14003244b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140032337`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400323d9`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400324b0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140032337`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400323d9`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400324b0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400322c0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400323a7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140032477`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400322c0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400323a7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140032477`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x140032319`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x140032319`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140032353`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400323ec`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140032416`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140032353`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400323ec`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140032416`
- `ntoskrnl!ExQueryDepthSList` at `0x1400324d7`
- `ntoskrnl!ExQueryDepthSList` at `0x1400324d7`

## pseudocode

```c
struct _NET_BUFFER *__fastcall ndisAllocateNetBufferInternal(char *a1, unsigned int *a2)
{
  unsigned int Number; // r12d
  bool v5; // zf
  unsigned __int64 v6; // rdi
  char *v7; // rbx
  KIRQL v8; // r15
  PSLIST_ENTRY v9; // rdi
  KIRQL v11; // al
  __int64 v12; // r8
  unsigned __int64 v13; // rax
  struct _SLIST_ENTRY *Pool2; // rax
  KSPIN_LOCK *v15; // rbx
  KIRQL v16; // al
  __int64 v17; // rcx
  _QWORD *v18; // rsi
  KIRQL v19; // dl
  _QWORD *v20; // rax

  if ( a1 )
  {
    if ( (*((_DWORD *)a1 + 1) & 1) != 0 )
    {
      *a2 = 0;
      return (struct _NET_BUFFER *)ndisPplAllocateFromSpecialPool((const struct _NDIS_POOL_HEADER *)a1);
    }
    else
    {
      Number = KeGetPcr()->Prcb.Number;
      v5 = ndisMaxNumberOfProcessors == 1;
      *a2 = 1;
      if ( !v5 )
      {
        v6 = (unsigned __int64)Number << 8;
        v7 = &a1[v6 + 384];
        if ( !v7[216] )
        {
          v8 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v7 + 26);
          if ( !v7[216] )
          {
            ExInitializeLookasideListEx(
              (PLOOKASIDE_LIST_EX)v7,
              ndisAllocateFromNPagedPool,
              *(PFREE_FUNCTION_EX *)&v7[-v6 - 200],
              NonPagedPoolNx,
              0,
              *(unsigned int *)&v7[-v6 - 212],
              *(_DWORD *)&v7[-v6 - 216],
              0x400u);
            v7[216] = 1;
          }
          KeReleaseSpinLock((PKSPIN_LOCK)v7 + 26, v8);
        }
        _InterlockedIncrement((volatile signed __int32 *)v7 + 5);
        v9 = ExpInterlockedPopEntrySList(*((PSLIST_HEADER *)v7 + 24));
        if ( v9 )
          return (struct _NET_BUFFER *)v9;
        if ( ExQueryDepthSList(*((PSLIST_HEADER *)v7 + 25)) >= 0xAu )
        {
          v11 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v7 + 26);
          v12 = *((_QWORD *)v7 + 24);
          *((_QWORD *)v7 + 24) = *((_QWORD *)v7 + 25);
          *((_QWORD *)v7 + 25) = v12;
          KeReleaseSpinLock((PKSPIN_LOCK)v7 + 26, v11);
          v9 = ExpInterlockedPopEntrySList(*((PSLIST_HEADER *)v7 + 24));
          if ( v9 )
            return (struct _NET_BUFFER *)v9;
        }
        _InterlockedIncrement((volatile signed __int32 *)v7 + 6);
      }
      _InterlockedIncrement((volatile signed __int32 *)a1 + 37);
      v9 = ExpInterlockedPopEntrySList((PSLIST_HEADER)a1 + 8);
      if ( !v9 )
      {
        _InterlockedIncrement((volatile signed __int32 *)a1 + 38);
        v13 = *((unsigned int *)a1 + 43);
        if ( v13 + 32 < v13
          || (Pool2 = (struct _SLIST_ENTRY *)ExAllocatePool2(66, v13 + 32, *((unsigned int *)a1 + 42))) == 0 )
        {
          *a2 = 0;
          return 0;
        }
        v9 = Pool2 + 2;
        Pool2->Next = 0;
        if ( Pool2 == (struct _SLIST_ENTRY *)-32LL )
        {
          *a2 = 0;
          return (struct _NET_BUFFER *)v9;
        }
        v15 = (KSPIN_LOCK *)(a1 + 8);
        Pool2->Next = (_SLIST_ENTRY *)a1;
        v16 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 1);
        v17 = *((_QWORD *)a1 + 2);
        v18 = a1 + 16;
        v19 = v16;
        if ( *(_QWORD **)(v17 + 8) != v18 )
          __fastfail(3u);
        v20 = &v9[-2].Next + 1;
        *v20 = v17;
        v20[1] = v18;
        *(_QWORD *)(v17 + 8) = (char *)v9 - 24;
        *v18 = (char *)v9 - 24;
        KeReleaseSpinLock(v15, v19);
        *a2 = 0;
      }
      *((_DWORD *)&v9[-1].Next + 2) = Number;
    }
    return (struct _NET_BUFFER *)v9;
  }
  return 0;
}

```

## disassembly

```asm
0x140032240  mov     r11, rsp
0x140032243  push    rsi
0x140032244  push    r14
0x140032246  sub     rsp, 58h
0x14003224a  mov     r14, rdx
0x14003224d  mov     rsi, rcx
0x140032250  test    rcx, rcx
0x140032253  jz      loc_1400324FD
0x140032259  mov     eax, [rcx+4]
0x14003225c  mov     [r11+8], rbx
0x140032260  mov     [r11+10h], rbp
0x140032264  mov     [r11+18h], rdi
0x140032268  mov     [r11-18h], r12
0x14003226c  mov     [r11-20h], r13
0x140032270  xor     r13d, r13d
0x140032273  test    al, 1
0x140032275  jnz     loc_140032393
0x14003227b  mov     r12d, gs:1A4h
0x140032284  cmp     cs:?ndisMaxNumberOfProcessors@@3KA, 1; ulong ndisMaxNumberOfProcessors
0x14003228b  mov     dword ptr [rdx], 1
0x140032291  jz      loc_140032408
0x140032297  mov     edi, r12d
0x14003229a  lea     rbx, [rcx+180h]
0x1400322a1  shl     rdi, 8
0x1400322a5  add     rbx, rdi
0x1400322a8  cmp     [rbx+0D8h], r13b
0x1400322af  jnz     loc_140032348
0x1400322b5  lea     rcx, [rbx+0D0h]; SpinLock
0x1400322bc  mov     [r11-28h], r15
0x1400322c0  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400322c7  nop     dword ptr [rax+rax+00h]
0x1400322cc  movzx   r15d, al
0x1400322d0  cmp     [rbx+0D8h], r13b
0x1400322d7  jnz     short loc_14003232C
0x1400322d9  mov     [rsp+68h+Depth], 400h; Depth
0x1400322e0  mov     r8, rbx
0x1400322e3  sub     r8, rdi
0x1400322e6  mov     r9d, 200h; PoolType
0x1400322ec  mov     edx, [r8-0D4h]
0x1400322f3  mov     ecx, [r8-0D8h]
0x1400322fa  mov     r8, [r8-0C8h]; Free
0x140032301  mov     [rsp+68h+Tag], ecx; Tag
0x140032305  mov     rcx, rbx; Lookaside
0x140032308  mov     [rsp+68h+Size], rdx; Size
0x14003230d  lea     rdx, ndisAllocateFromNPagedPool; Allocate
0x140032314  mov     [rsp+68h+Flags], r13d; Flags
0x140032319  call    cs:__imp_ExInitializeLookasideListEx
0x140032320  nop     dword ptr [rax+rax+00h]
0x140032325  mov     byte ptr [rbx+0D8h], 1
0x14003232c  movzx   edx, r15b; NewIrql
0x140032330  lea     rcx, [rbx+0D0h]; SpinLock
0x140032337  call    cs:__imp_KeReleaseSpinLock
0x14003233e  nop     dword ptr [rax+rax+00h]
0x140032343  mov     r15, [rsp+68h+var_28]
0x140032348  lock inc dword ptr [rbx+14h]
0x14003234c  mov     rcx, [rbx+0C0h]; ListHead
0x140032353  call    cs:__imp_ExpInterlockedPopEntrySList
0x14003235a  nop     dword ptr [rax+rax+00h]
0x14003235f  mov     rdi, rax
0x140032362  test    rax, rax
0x140032365  jz      loc_1400324D0
0x14003236b  mov     r12, [rsp+68h+var_18]
0x140032370  mov     rax, rdi
0x140032373  mov     rdi, [rsp+68h+arg_10]
0x14003237b  mov     rbp, [rsp+68h+arg_8]
0x140032380  mov     rbx, [rsp+68h+arg_0]
0x140032385  mov     r13, [rsp+68h+var_20]
0x14003238a  add     rsp, 58h
0x14003238e  pop     r14
0x140032390  pop     rsi
0x140032391  retn
0x140032393  mov     [rdx], r13d
0x140032396  call    ?ndisPplAllocateFromSpecialPool@@YAPEAXPEBU_NDIS_POOL_HEADER@@@Z; ndisPplAllocateFromSpecialPool(_NDIS_POOL_HEADER const *)
0x14003239b  mov     rdi, rax
0x14003239e  jmp     short loc_14003236B
0x1400323a0  lea     rcx, [rbx+0D0h]; SpinLock
0x1400323a7  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400323ae  nop     dword ptr [rax+rax+00h]
0x1400323b3  mov     rdx, [rbx+0C8h]
0x1400323ba  lea     rcx, [rbx+0D0h]; SpinLock
0x1400323c1  mov     r8, [rbx+0C0h]
0x1400323c8  mov     [rbx+0C0h], rdx
0x1400323cf  movzx   edx, al; NewIrql
0x1400323d2  mov     [rbx+0C8h], r8
0x1400323d9  call    cs:__imp_KeReleaseSpinLock
0x1400323e0  nop     dword ptr [rax+rax+00h]
0x1400323e5  mov     rcx, [rbx+0C0h]; ListHead
0x1400323ec  call    cs:__imp_ExpInterlockedPopEntrySList
0x1400323f3  nop     dword ptr [rax+rax+00h]
0x1400323f8  mov     rdi, rax
0x1400323fb  test    rax, rax
0x1400323fe  jnz     loc_14003236B
0x140032404  lock inc dword ptr [rbx+18h]
0x140032408  lea     rbx, [rsi+80h]
0x14003240f  lock inc dword ptr [rbx+14h]
0x140032413  mov     rcx, rbx; ListHead
0x140032416  call    cs:__imp_ExpInterlockedPopEntrySList
0x14003241d  nop     dword ptr [rax+rax+00h]
0x140032422  mov     rdi, rax
0x140032425  test    rax, rax
0x140032428  jnz     loc_1400324BF
0x14003242e  lock inc dword ptr [rbx+18h]
0x140032432  mov     eax, [rbx+2Ch]
0x140032435  lea     rdx, [rax+20h]
0x140032439  cmp     rdx, rax
0x14003243c  jb      loc_1400324F2
0x140032442  mov     r8d, [rbx+28h]
0x140032446  mov     ecx, 42h ; 'B'
0x14003244b  call    cs:__imp_ExAllocatePool2
0x140032452  nop     dword ptr [rax+rax+00h]
0x140032457  test    rax, rax
0x14003245a  jz      loc_1400324F2
0x140032460  lea     rdi, [rax+20h]
0x140032464  mov     [rax], r13
0x140032467  test    rdi, rdi
0x14003246a  jz      short loc_1400324C8
0x14003246c  lea     rbx, [rsi+8]
0x140032470  mov     [rdi-20h], rsi
0x140032474  mov     rcx, rbx; SpinLock
0x140032477  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14003247e  nop     dword ptr [rax+rax+00h]
0x140032483  mov     rcx, [rsi+10h]
0x140032487  add     rsi, 10h
0x14003248b  movzx   edx, al; NewIrql
0x14003248e  cmp     [rcx+8], rsi
0x140032492  jz      short loc_14003249B
0x140032494  mov     ecx, 3
0x140032499  int     29h; Win8: RtlFailFast(ecx)
0x14003249b  lea     rax, [rdi-18h]
0x14003249f  mov     [rax], rcx
0x1400324a2  mov     [rax+8], rsi
0x1400324a6  mov     [rcx+8], rax
0x1400324aa  mov     rcx, rbx; SpinLock
0x1400324ad  mov     [rsi], rax
0x1400324b0  call    cs:__imp_KeReleaseSpinLock
0x1400324b7  nop     dword ptr [rax+rax+00h]
0x1400324bc  mov     [r14], r13d
0x1400324bf  mov     [rdi-8], r12d
0x1400324c3  jmp     loc_14003236B
0x1400324c8  mov     [r14], r13d
0x1400324cb  jmp     loc_14003236B
0x1400324d0  mov     rcx, [rbx+0C8h]; SListHead
0x1400324d7  call    cs:__imp_ExQueryDepthSList
0x1400324de  nop     dword ptr [rax+rax+00h]
0x1400324e3  cmp     ax, 0Ah
0x1400324e7  jb      loc_140032404
0x1400324ed  jmp     loc_1400323A0
0x1400324f2  mov     [r14], r13d
0x1400324f5  mov     rdi, r13
0x1400324f8  jmp     loc_14003236B
0x1400324fd  xor     eax, eax
0x1400324ff  jmp     loc_14003238A
```
