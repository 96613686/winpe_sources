# ndisAllocateNetBufferInternal(void *,ulong *)

- ea: `0x140033240`
- end: `0x140033504`
- name: `?ndisAllocateNetBufferInternal@@YAPEAU_NET_BUFFER@@PEAXPEAK@Z`
- size: `708`
- prototype: `struct _NET_BUFFER *__fastcall(void *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140031090`

## callees

- `0x140033240`
- `0x140033510`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14003344b`
- `ntoskrnl!ExAllocatePool2` at `0x14003344b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140033337`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400333d9`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400334b0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140033337`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400333d9`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400334b0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400332c0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400333a7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140033477`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400332c0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400333a7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140033477`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x140033319`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x140033319`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140033353`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400333ec`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140033416`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140033353`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400333ec`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140033416`
- `ntoskrnl!ExQueryDepthSList` at `0x1400334d7`
- `ntoskrnl!ExQueryDepthSList` at `0x1400334d7`

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
0x140033240  mov     r11, rsp
0x140033243  push    rsi
0x140033244  push    r14
0x140033246  sub     rsp, 58h
0x14003324a  mov     r14, rdx
0x14003324d  mov     rsi, rcx
0x140033250  test    rcx, rcx
0x140033253  jz      loc_1400334FD
0x140033259  mov     eax, [rcx+4]
0x14003325c  mov     [r11+8], rbx
0x140033260  mov     [r11+10h], rbp
0x140033264  mov     [r11+18h], rdi
0x140033268  mov     [r11-18h], r12
0x14003326c  mov     [r11-20h], r13
0x140033270  xor     r13d, r13d
0x140033273  test    al, 1
0x140033275  jnz     loc_140033393
0x14003327b  mov     r12d, gs:1A4h
0x140033284  cmp     cs:?ndisMaxNumberOfProcessors@@3KA, 1; ulong ndisMaxNumberOfProcessors
0x14003328b  mov     dword ptr [rdx], 1
0x140033291  jz      loc_140033408
0x140033297  mov     edi, r12d
0x14003329a  lea     rbx, [rcx+180h]
0x1400332a1  shl     rdi, 8
0x1400332a5  add     rbx, rdi
0x1400332a8  cmp     [rbx+0D8h], r13b
0x1400332af  jnz     loc_140033348
0x1400332b5  lea     rcx, [rbx+0D0h]; SpinLock
0x1400332bc  mov     [r11-28h], r15
0x1400332c0  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400332c7  nop     dword ptr [rax+rax+00h]
0x1400332cc  movzx   r15d, al
0x1400332d0  cmp     [rbx+0D8h], r13b
0x1400332d7  jnz     short loc_14003332C
0x1400332d9  mov     [rsp+68h+Depth], 400h; Depth
0x1400332e0  mov     r8, rbx
0x1400332e3  sub     r8, rdi
0x1400332e6  mov     r9d, 200h; PoolType
0x1400332ec  mov     edx, [r8-0D4h]
0x1400332f3  mov     ecx, [r8-0D8h]
0x1400332fa  mov     r8, [r8-0C8h]; Free
0x140033301  mov     [rsp+68h+Tag], ecx; Tag
0x140033305  mov     rcx, rbx; Lookaside
0x140033308  mov     [rsp+68h+Size], rdx; Size
0x14003330d  lea     rdx, ndisAllocateFromNPagedPool; Allocate
0x140033314  mov     [rsp+68h+Flags], r13d; Flags
0x140033319  call    cs:__imp_ExInitializeLookasideListEx
0x140033320  nop     dword ptr [rax+rax+00h]
0x140033325  mov     byte ptr [rbx+0D8h], 1
0x14003332c  movzx   edx, r15b; NewIrql
0x140033330  lea     rcx, [rbx+0D0h]; SpinLock
0x140033337  call    cs:__imp_KeReleaseSpinLock
0x14003333e  nop     dword ptr [rax+rax+00h]
0x140033343  mov     r15, [rsp+68h+var_28]
0x140033348  lock inc dword ptr [rbx+14h]
0x14003334c  mov     rcx, [rbx+0C0h]; ListHead
0x140033353  call    cs:__imp_ExpInterlockedPopEntrySList
0x14003335a  nop     dword ptr [rax+rax+00h]
0x14003335f  mov     rdi, rax
0x140033362  test    rax, rax
0x140033365  jz      loc_1400334D0
0x14003336b  mov     r12, [rsp+68h+var_18]
0x140033370  mov     rax, rdi
0x140033373  mov     rdi, [rsp+68h+arg_10]
0x14003337b  mov     rbp, [rsp+68h+arg_8]
0x140033380  mov     rbx, [rsp+68h+arg_0]
0x140033385  mov     r13, [rsp+68h+var_20]
0x14003338a  add     rsp, 58h
0x14003338e  pop     r14
0x140033390  pop     rsi
0x140033391  retn
0x140033393  mov     [rdx], r13d
0x140033396  call    ?ndisPplAllocateFromSpecialPool@@YAPEAXPEBU_NDIS_POOL_HEADER@@@Z; ndisPplAllocateFromSpecialPool(_NDIS_POOL_HEADER const *)
0x14003339b  mov     rdi, rax
0x14003339e  jmp     short loc_14003336B
0x1400333a0  lea     rcx, [rbx+0D0h]; SpinLock
0x1400333a7  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400333ae  nop     dword ptr [rax+rax+00h]
0x1400333b3  mov     rdx, [rbx+0C8h]
0x1400333ba  lea     rcx, [rbx+0D0h]; SpinLock
0x1400333c1  mov     r8, [rbx+0C0h]
0x1400333c8  mov     [rbx+0C0h], rdx
0x1400333cf  movzx   edx, al; NewIrql
0x1400333d2  mov     [rbx+0C8h], r8
0x1400333d9  call    cs:__imp_KeReleaseSpinLock
0x1400333e0  nop     dword ptr [rax+rax+00h]
0x1400333e5  mov     rcx, [rbx+0C0h]; ListHead
0x1400333ec  call    cs:__imp_ExpInterlockedPopEntrySList
0x1400333f3  nop     dword ptr [rax+rax+00h]
0x1400333f8  mov     rdi, rax
0x1400333fb  test    rax, rax
0x1400333fe  jnz     loc_14003336B
0x140033404  lock inc dword ptr [rbx+18h]
0x140033408  lea     rbx, [rsi+80h]
0x14003340f  lock inc dword ptr [rbx+14h]
0x140033413  mov     rcx, rbx; ListHead
0x140033416  call    cs:__imp_ExpInterlockedPopEntrySList
0x14003341d  nop     dword ptr [rax+rax+00h]
0x140033422  mov     rdi, rax
0x140033425  test    rax, rax
0x140033428  jnz     loc_1400334BF
0x14003342e  lock inc dword ptr [rbx+18h]
0x140033432  mov     eax, [rbx+2Ch]
0x140033435  lea     rdx, [rax+20h]
0x140033439  cmp     rdx, rax
0x14003343c  jb      loc_1400334F2
0x140033442  mov     r8d, [rbx+28h]
0x140033446  mov     ecx, 42h ; 'B'
0x14003344b  call    cs:__imp_ExAllocatePool2
0x140033452  nop     dword ptr [rax+rax+00h]
0x140033457  test    rax, rax
0x14003345a  jz      loc_1400334F2
0x140033460  lea     rdi, [rax+20h]
0x140033464  mov     [rax], r13
0x140033467  test    rdi, rdi
0x14003346a  jz      short loc_1400334C8
0x14003346c  lea     rbx, [rsi+8]
0x140033470  mov     [rdi-20h], rsi
0x140033474  mov     rcx, rbx; SpinLock
0x140033477  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14003347e  nop     dword ptr [rax+rax+00h]
0x140033483  mov     rcx, [rsi+10h]
0x140033487  add     rsi, 10h
0x14003348b  movzx   edx, al; NewIrql
0x14003348e  cmp     [rcx+8], rsi
0x140033492  jz      short loc_14003349B
0x140033494  mov     ecx, 3
0x140033499  int     29h; Win8: RtlFailFast(ecx)
0x14003349b  lea     rax, [rdi-18h]
0x14003349f  mov     [rax], rcx
0x1400334a2  mov     [rax+8], rsi
0x1400334a6  mov     [rcx+8], rax
0x1400334aa  mov     rcx, rbx; SpinLock
0x1400334ad  mov     [rsi], rax
0x1400334b0  call    cs:__imp_KeReleaseSpinLock
0x1400334b7  nop     dword ptr [rax+rax+00h]
0x1400334bc  mov     [r14], r13d
0x1400334bf  mov     [rdi-8], r12d
0x1400334c3  jmp     loc_14003336B
0x1400334c8  mov     [r14], r13d
0x1400334cb  jmp     loc_14003336B
0x1400334d0  mov     rcx, [rbx+0C8h]; SListHead
0x1400334d7  call    cs:__imp_ExQueryDepthSList
0x1400334de  nop     dword ptr [rax+rax+00h]
0x1400334e3  cmp     ax, 0Ah
0x1400334e7  jb      loc_140033404
0x1400334ed  jmp     loc_1400333A0
0x1400334f2  mov     [r14], r13d
0x1400334f5  mov     rdi, r13
0x1400334f8  jmp     loc_14003336B
0x1400334fd  xor     eax, eax
0x1400334ff  jmp     loc_14003338A
```
