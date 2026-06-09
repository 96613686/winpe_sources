# std::list<CDockInterface::Listener,std::allocator<CDockInterface::Listener>>::remove(CDockInterface::Listener const &)

- ea: `0x18001c544`
- end: `0x18001c5db`
- name: `?remove@?$list@VListener@CDockInterface@@V?$allocator@VListener@CDockInterface@@@std@@@std@@QEAAXAEBVListener@CDockInterface@@@Z`
- size: `151`
- prototype: `void __fastcall(__int64, __int64 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18001b428`
- `0x18001c330`

## callees

- `0x1800014d0`
- `0x18001a96c`
- `0x18001c544`
- `0x18001f010`

## pseudocode

```c
void __fastcall std::list<CDockInterface::Listener>::remove(__int64 a1, __int64 *a2)
{
  __int64 v3; // rbx
  __int64 v4; // rcx
  _QWORD **v5; // r14
  _QWORD *v6; // rsi
  CDockInterface::Listener *v7; // rcx
  _QWORD *v8; // rdx
  void *v9; // rdi
  __int64 v10; // [rsp+40h] [rbp+8h] BYREF

  v3 = 0;
  v10 = 0;
  v4 = *a2;
  if ( *a2 )
  {
    v3 = *a2;
    v10 = *a2;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 8LL))(v4);
  }
  v5 = *(_QWORD ***)a1;
  v6 = **(_QWORD ***)a1;
  while ( v6 != v5 )
  {
    v7 = (CDockInterface::Listener *)(v6 + 2);
    if ( v6[2] == v3 )
    {
      v8 = (_QWORD *)v6[1];
      v9 = v6;
      v6 = (_QWORD *)*v6;
      *v8 = v6;
      v6[1] = v8;
      CDockInterface::Listener::~Listener(v7);
      operator delete(v9);
      --*(_QWORD *)(a1 + 8);
    }
    else
    {
      v6 = (_QWORD *)*v6;
    }
  }
  CDockInterface::Listener::~Listener((CDockInterface::Listener *)&v10);
}

```

## disassembly

```asm
0x18001c544  mov     rax, rsp
0x18001c547  mov     [rax+10h], rbx
0x18001c54b  mov     [rax+18h], rsi
0x18001c54f  push    rdi
0x18001c550  push    r14
0x18001c552  push    r15
0x18001c554  sub     rsp, 20h
0x18001c558  mov     r15, rcx
0x18001c55b  xor     ebx, ebx
0x18001c55d  mov     [rax+8], rbx
0x18001c561  mov     rcx, [rdx]
0x18001c564  test    rcx, rcx
0x18001c567  jz      short loc_18001C57D
0x18001c569  mov     rbx, rcx
0x18001c56c  mov     [rax+8], rcx
0x18001c570  mov     rax, [rcx]
0x18001c573  mov     rax, [rax+8]
0x18001c577  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c57c  nop
0x18001c57d  mov     r14, [r15]
0x18001c580  mov     rsi, [r14]
0x18001c583  jmp     short loc_18001C5B8
0x18001c585  lea     rcx, [rsi+10h]; this
0x18001c589  cmp     [rcx], rbx
0x18001c58c  jnz     short loc_18001C5B5
0x18001c58e  mov     rdx, [rsi+8]
0x18001c592  mov     rdi, rsi
0x18001c595  mov     rax, [rsi]
0x18001c598  mov     rsi, rax
0x18001c59b  mov     [rdx], rax
0x18001c59e  mov     [rax+8], rdx
0x18001c5a2  call    ??1Listener@CDockInterface@@QEAA@XZ; CDockInterface::Listener::~Listener(void)
0x18001c5a7  mov     rcx, rdi; Block
0x18001c5aa  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001c5af  dec     qword ptr [r15+8]
0x18001c5b3  jmp     short loc_18001C5B8
0x18001c5b5  mov     rsi, [rsi]
0x18001c5b8  cmp     rsi, r14
0x18001c5bb  jnz     short loc_18001C585
0x18001c5bd  lea     rcx, [rsp+38h+arg_0]; this
0x18001c5c2  call    ??1Listener@CDockInterface@@QEAA@XZ; CDockInterface::Listener::~Listener(void)
0x18001c5c7  mov     rbx, [rsp+38h+arg_8]
0x18001c5cc  mov     rsi, [rsp+38h+arg_10]
0x18001c5d1  add     rsp, 20h
0x18001c5d5  pop     r15
0x18001c5d7  pop     r14
0x18001c5d9  pop     rdi
0x18001c5da  retn
```
