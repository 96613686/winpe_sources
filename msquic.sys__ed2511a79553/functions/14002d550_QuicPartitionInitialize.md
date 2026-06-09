# QuicPartitionInitialize

- ea: `0x14002d550`
- end: `0x14002d7f4`
- name: `QuicPartitionInitialize`
- size: `676`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140028728`

## callees

- `0x14000175c`
- `0x14002d550`
- `0x140034788`

## import_xrefs

- `ntoskrnl!ExInitializePushLock` at `0x14002d7c0`
- `ntoskrnl!ExInitializePushLock` at `0x14002d7c0`
- `ntoskrnl!KeInitializeSpinLock` at `0x14002d7d0`
- `ntoskrnl!KeInitializeSpinLock` at `0x14002d7d0`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14002d5c4`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14002d5fb`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14002d62d`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14002d663`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14002d699`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14002d6cf`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14002d712`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14002d748`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14002d77a`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14002d7b0`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14002d5c4`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14002d5fb`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14002d62d`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14002d663`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14002d699`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14002d6cf`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14002d712`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14002d748`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14002d77a`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14002d7b0`

## pseudocode

```c
__int64 __fastcall QuicPartitionInitialize(__int64 a1, __int16 a2, __int16 a3, __int64 a4, __int64 a5)
{
  __int64 result; // rax

  result = CxPlatHashCreate(0, a5, 20, a1 + 32);
  if ( (int)result >= 0 )
  {
    *(_WORD *)a1 = a2;
    *(_WORD *)(a1 + 2) = a3;
    ExInitializeLookasideListEx((PLOOKASIDE_LIST_EX)(a1 + 96), 0, 0, (POOL_TYPE)512, 0, 0xF98u, 0x31306351u, 0x400u);
    ExInitializeLookasideListEx((PLOOKASIDE_LIST_EX)(a1 + 192), 0, 0, (POOL_TYPE)512, 0, 0x110u, 0x32306351u, 0x400u);
    ExInitializeLookasideListEx((PLOOKASIDE_LIST_EX)(a1 + 288), 0, 0, (POOL_TYPE)512, 0, 0x1C0u, 0x32306351u, 0x400u);
    ExInitializeLookasideListEx((PLOOKASIDE_LIST_EX)(a1 + 384), 0, 0, (POOL_TYPE)512, 0, 0x3B0u, 0x33306351u, 0x400u);
    ExInitializeLookasideListEx((PLOOKASIDE_LIST_EX)(a1 + 480), 0, 0, (POOL_TYPE)512, 0, 0x1030u, 0x34306351u, 0x400u);
    ExInitializeLookasideListEx((PLOOKASIDE_LIST_EX)(a1 + 576), 0, 0, (POOL_TYPE)512, 0, 0x50u, 0x41336351u, 0x400u);
    QuicSentPacketPoolInitialize((PLOOKASIDE_LIST_EX)(a1 + 672));
    ExInitializeLookasideListEx((PLOOKASIDE_LIST_EX)(a1 + 1824), 0, 0, (POOL_TYPE)512, 0, 0x48u, 0x42336351u, 0x400u);
    ExInitializeLookasideListEx((PLOOKASIDE_LIST_EX)(a1 + 1920), 0, 0, (POOL_TYPE)512, 0, 0x78u, 0x43336351u, 0x400u);
    ExInitializeLookasideListEx((PLOOKASIDE_LIST_EX)(a1 + 2016), 0, 0, (POOL_TYPE)512, 0, 0x48u, 0x44336351u, 0x400u);
    ExInitializeLookasideListEx((PLOOKASIDE_LIST_EX)(a1 + 2112), 0, 0, (POOL_TYPE)512, 0, 0x30u, 0x44346351u, 0x400u);
    ExInitializePushLock((PULONG_PTR)(a1 + 40));
    KeInitializeSpinLock((PKSPIN_LOCK)(a1 + 48));
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x14002d550  mov     [rsp+arg_0], rbx
0x14002d555  mov     [rsp+arg_8], rbp
0x14002d55a  mov     [rsp+arg_10], rsi
0x14002d55f  push    rdi
0x14002d560  sub     rsp, 40h
0x14002d564  movzx   edi, r8w
0x14002d568  lea     r9, [rcx+20h]
0x14002d56c  movzx   esi, dx
0x14002d56f  mov     rbx, rcx
0x14002d572  mov     rdx, [rsp+48h+arg_20]
0x14002d577  mov     r8d, 14h
0x14002d57d  xor     ecx, ecx
0x14002d57f  call    CxPlatHashCreate
0x14002d584  test    eax, eax
0x14002d586  js      loc_14002D7DE
0x14002d58c  mov     [rbx], si
0x14002d58f  lea     rcx, [rbx+60h]; Lookaside
0x14002d593  mov     ebp, 400h
0x14002d598  mov     [rbx+2], di
0x14002d59c  mov     [rsp+48h+Depth], bp; Depth
0x14002d5a1  mov     esi, 200h
0x14002d5a6  mov     [rsp+48h+Tag], 31306351h; Tag
0x14002d5ae  mov     r9d, esi; PoolType
0x14002d5b1  mov     [rsp+48h+Size], 0F98h; Size
0x14002d5ba  xor     r8d, r8d; Free
0x14002d5bd  and     [rsp+48h+var_28], 0
0x14002d5c2  xor     edx, edx; Allocate
0x14002d5c4  call    cs:__imp_ExInitializeLookasideListEx
0x14002d5cb  nop     dword ptr [rax+rax+00h]
0x14002d5d0  mov     [rsp+48h+Depth], bp; Depth
0x14002d5d5  lea     rcx, [rbx+0C0h]; Lookaside
0x14002d5dc  mov     edi, 32306351h
0x14002d5e1  mov     r9d, esi; PoolType
0x14002d5e4  mov     [rsp+48h+Tag], edi; Tag
0x14002d5e8  xor     r8d, r8d; Free
0x14002d5eb  mov     [rsp+48h+Size], 110h; Size
0x14002d5f4  xor     edx, edx; Allocate
0x14002d5f6  and     [rsp+48h+var_28], 0
0x14002d5fb  call    cs:__imp_ExInitializeLookasideListEx
0x14002d602  nop     dword ptr [rax+rax+00h]
0x14002d607  mov     [rsp+48h+Depth], bp; Depth
0x14002d60c  lea     rcx, [rbx+120h]; Lookaside
0x14002d613  mov     [rsp+48h+Tag], edi; Tag
0x14002d617  mov     r9d, esi; PoolType
0x14002d61a  mov     [rsp+48h+Size], 1C0h; Size
0x14002d623  xor     r8d, r8d; Free
0x14002d626  and     [rsp+48h+var_28], 0
0x14002d62b  xor     edx, edx; Allocate
0x14002d62d  call    cs:__imp_ExInitializeLookasideListEx
0x14002d634  nop     dword ptr [rax+rax+00h]
0x14002d639  mov     [rsp+48h+Depth], bp; Depth
0x14002d63e  lea     rcx, [rbx+180h]; Lookaside
0x14002d645  mov     [rsp+48h+Tag], 33306351h; Tag
0x14002d64d  mov     r9d, esi; PoolType
0x14002d650  mov     [rsp+48h+Size], 3B0h; Size
0x14002d659  xor     r8d, r8d; Free
0x14002d65c  and     [rsp+48h+var_28], 0
0x14002d661  xor     edx, edx; Allocate
0x14002d663  call    cs:__imp_ExInitializeLookasideListEx
0x14002d66a  nop     dword ptr [rax+rax+00h]
0x14002d66f  mov     [rsp+48h+Depth], bp; Depth
0x14002d674  lea     rcx, [rbx+1E0h]; Lookaside
0x14002d67b  mov     [rsp+48h+Tag], 34306351h; Tag
0x14002d683  mov     r9d, esi; PoolType
0x14002d686  mov     [rsp+48h+Size], 1030h; Size
0x14002d68f  xor     r8d, r8d; Free
0x14002d692  and     [rsp+48h+var_28], 0
0x14002d697  xor     edx, edx; Allocate
0x14002d699  call    cs:__imp_ExInitializeLookasideListEx
0x14002d6a0  nop     dword ptr [rax+rax+00h]
0x14002d6a5  mov     [rsp+48h+Depth], bp; Depth
0x14002d6aa  lea     rcx, [rbx+240h]; Lookaside
0x14002d6b1  mov     [rsp+48h+Tag], 41336351h; Tag
0x14002d6b9  mov     r9d, esi; PoolType
0x14002d6bc  mov     [rsp+48h+Size], 50h ; 'P'; Size
0x14002d6c5  xor     r8d, r8d; Free
0x14002d6c8  and     [rsp+48h+var_28], 0
0x14002d6cd  xor     edx, edx; Allocate
0x14002d6cf  call    cs:__imp_ExInitializeLookasideListEx
0x14002d6d6  nop     dword ptr [rax+rax+00h]
0x14002d6db  lea     rcx, [rbx+2A0h]; Lookaside
0x14002d6e2  call    QuicSentPacketPoolInitialize
0x14002d6e7  mov     [rsp+48h+Depth], bp; Depth
0x14002d6ec  lea     rcx, [rbx+720h]; Lookaside
0x14002d6f3  mov     [rsp+48h+Tag], 42336351h; Tag
0x14002d6fb  mov     edi, 48h ; 'H'
0x14002d700  mov     [rsp+48h+Size], rdi; Size
0x14002d705  mov     r9d, esi; PoolType
0x14002d708  and     [rsp+48h+var_28], 0
0x14002d70d  xor     r8d, r8d; Free
0x14002d710  xor     edx, edx; Allocate
0x14002d712  call    cs:__imp_ExInitializeLookasideListEx
0x14002d719  nop     dword ptr [rax+rax+00h]
0x14002d71e  mov     [rsp+48h+Depth], bp; Depth
0x14002d723  lea     rcx, [rbx+780h]; Lookaside
0x14002d72a  mov     [rsp+48h+Tag], 43336351h; Tag
0x14002d732  mov     r9d, esi; PoolType
0x14002d735  mov     [rsp+48h+Size], 78h ; 'x'; Size
0x14002d73e  xor     r8d, r8d; Free
0x14002d741  and     [rsp+48h+var_28], 0
0x14002d746  xor     edx, edx; Allocate
0x14002d748  call    cs:__imp_ExInitializeLookasideListEx
0x14002d74f  nop     dword ptr [rax+rax+00h]
0x14002d754  lea     rcx, [rbx+7E0h]; Lookaside
0x14002d75b  mov     [rsp+48h+Depth], bp; Depth
0x14002d760  mov     r9d, esi; PoolType
0x14002d763  mov     [rsp+48h+Tag], 44336351h; Tag
0x14002d76b  xor     r8d, r8d; Free
0x14002d76e  mov     [rsp+48h+Size], rdi; Size
0x14002d773  xor     edx, edx; Allocate
0x14002d775  and     [rsp+48h+var_28], 0
0x14002d77a  call    cs:__imp_ExInitializeLookasideListEx
0x14002d781  nop     dword ptr [rax+rax+00h]
0x14002d786  mov     [rsp+48h+Depth], bp; Depth
0x14002d78b  lea     rcx, [rbx+840h]; Lookaside
0x14002d792  mov     [rsp+48h+Tag], 44346351h; Tag
0x14002d79a  mov     r9d, esi; PoolType
0x14002d79d  mov     [rsp+48h+Size], 30h ; '0'; Size
0x14002d7a6  xor     r8d, r8d; Free
0x14002d7a9  and     [rsp+48h+var_28], 0
0x14002d7ae  xor     edx, edx; Allocate
0x14002d7b0  call    cs:__imp_ExInitializeLookasideListEx
0x14002d7b7  nop     dword ptr [rax+rax+00h]
0x14002d7bc  lea     rcx, [rbx+28h]; PushLock
0x14002d7c0  call    cs:__imp_ExInitializePushLock
0x14002d7c7  nop     dword ptr [rax+rax+00h]
0x14002d7cc  lea     rcx, [rbx+30h]; SpinLock
0x14002d7d0  call    cs:__imp_KeInitializeSpinLock
0x14002d7d7  nop     dword ptr [rax+rax+00h]
0x14002d7dc  xor     eax, eax
0x14002d7de  mov     rbx, [rsp+48h+arg_0]
0x14002d7e3  mov     rbp, [rsp+48h+arg_8]
0x14002d7e8  mov     rsi, [rsp+48h+arg_10]
0x14002d7ed  add     rsp, 40h
0x14002d7f1  pop     rdi
0x14002d7f2  retn
```
