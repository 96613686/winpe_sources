# std::list<Command,std::allocator<Command>>::~list<Command,std::allocator<Command>>(void)

- ea: `0x140007c70`
- end: `0x140007cd8`
- name: `??1?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAA@XZ`
- size: `104`
- prototype: `void(void *)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140007ce0`
- `0x140009c08`
- `0x14000abb4`
- `0x14000ae6d`

## callees

- `0x140007c70`
- `0x14000a190`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x140007cb1`
- `msvcrt!??3@YAXPEAX@Z` at `0x140007cb1`
- `msvcrt!??3@YAXPEAX@Z` at `0x140007cd1`

## pseudocode

```c
void __fastcall std::list<Command>::~list<Command>(void ***a1)
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
      Command::~Command(v2 + 2);
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
0x140007c70  mov     [rsp+arg_0], rbx
0x140007c75  mov     [rsp+arg_8], rsi
0x140007c7a  push    rdi
0x140007c7b  sub     rsp, 20h
0x140007c7f  mov     rax, [rcx]
0x140007c82  mov     rdi, rcx
0x140007c85  mov     rsi, [rax]
0x140007c88  mov     [rax], rax
0x140007c8b  mov     rax, [rcx]
0x140007c8e  mov     [rax+8], rax
0x140007c92  mov     qword ptr [rcx+8], 0
0x140007c9a  mov     rcx, [rcx]
0x140007c9d  cmp     rsi, rcx
0x140007ca0  jz      short loc_140007CC2
0x140007ca2  mov     rbx, [rsi]
0x140007ca5  lea     rcx, [rsi+10h]; this
0x140007ca9  call    ??1Command@@QEAA@XZ; Command::~Command(void)
0x140007cae  mov     rcx, rsi
0x140007cb1  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140007cb7  mov     rcx, [rdi]
0x140007cba  mov     rsi, rbx
0x140007cbd  cmp     rbx, rcx
0x140007cc0  jnz     short loc_140007CA2
0x140007cc2  mov     rbx, [rsp+28h+arg_0]
0x140007cc7  mov     rsi, [rsp+28h+arg_8]
0x140007ccc  add     rsp, 20h
0x140007cd0  pop     rdi
0x140007cd1  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
