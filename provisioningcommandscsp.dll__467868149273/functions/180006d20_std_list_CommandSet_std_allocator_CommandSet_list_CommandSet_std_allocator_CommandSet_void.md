# std::list<CommandSet,std::allocator<CommandSet>>::~list<CommandSet,std::allocator<CommandSet>>(void)

- ea: `0x180006d20`
- end: `0x180006d93`
- name: `??1?$list@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@QEAA@XZ`
- size: `115`
- prototype: `void(void *)`
- caller_count: `8`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800076ac`
- `0x1800096c0`
- `0x18000b81c`
- `0x18000c744`
- `0x18000d67b`
- `0x18000d9a2`
- `0x18000dbc9`
- `0x18000dc1a`

## callees

- `0x180006d20`
- `0x18000a50c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180006d61`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006d61`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006d87`

## pseudocode

```c
void __fastcall std::list<CommandSet>::~list<CommandSet>(void ***a1)
{
  void **v2; // rsi
  void **v3; // rcx
  void **v4; // rbx

  v2 = (void **)**a1;
  **a1 = *a1;
  (*a1)[1] = *a1;
  a1[1] = 0;
  v3 = *a1;
  if ( v2 != v3 )
  {
    do
    {
      v4 = (void **)*v2;
      CommandSet::~CommandSet(v2 + 2);
      operator delete(v2);
      v3 = *a1;
      v2 = v4;
    }
    while ( v4 != *a1 );
  }
  operator delete(v3);
}

```

## disassembly

```asm
0x180006d20  mov     [rsp+arg_0], rbx
0x180006d25  mov     [rsp+arg_8], rsi
0x180006d2a  push    rdi
0x180006d2b  sub     rsp, 20h
0x180006d2f  mov     rax, [rcx]
0x180006d32  mov     rdi, rcx
0x180006d35  mov     rsi, [rax]
0x180006d38  mov     [rax], rax
0x180006d3b  mov     rax, [rcx]
0x180006d3e  mov     [rax+8], rax
0x180006d42  mov     qword ptr [rcx+8], 0
0x180006d4a  mov     rcx, [rcx]
0x180006d4d  cmp     rsi, rcx
0x180006d50  jz      short loc_180006D78
0x180006d52  mov     rbx, [rsi]
0x180006d55  lea     rcx, [rsi+10h]; this
0x180006d59  call    ??1CommandSet@@QEAA@XZ; CommandSet::~CommandSet(void)
0x180006d5e  mov     rcx, rsi
0x180006d61  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006d68  nop     dword ptr [rax+rax+00h]
0x180006d6d  mov     rcx, [rdi]
0x180006d70  mov     rsi, rbx
0x180006d73  cmp     rbx, rcx
0x180006d76  jnz     short loc_180006D52
0x180006d78  mov     rbx, [rsp+28h+arg_0]
0x180006d7d  mov     rsi, [rsp+28h+arg_8]
0x180006d82  add     rsp, 20h
0x180006d86  pop     rdi
0x180006d87  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
