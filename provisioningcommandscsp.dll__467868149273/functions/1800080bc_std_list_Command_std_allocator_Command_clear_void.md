# std::list<Command,std::allocator<Command>>::clear(void)

- ea: `0x1800080bc`
- end: `0x18000811f`
- name: `?clear@?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAAXXZ`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000d54c`
- `0x18000dab6`

## callees

- `0x1800080bc`
- `0x18000a554`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800080fa`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800080fa`

## pseudocode

```c
void __fastcall std::list<Command>::clear(__int64 a1)
{
  void **v2; // rsi
  void **v3; // rbx

  v2 = **(void ****)a1;
  **(_QWORD **)a1 = *(_QWORD *)a1;
  *(_QWORD *)(*(_QWORD *)a1 + 8LL) = *(_QWORD *)a1;
  *(_QWORD *)(a1 + 8) = 0;
  if ( v2 != *(void ***)a1 )
  {
    do
    {
      v3 = (void **)*v2;
      Command::~Command(v2 + 2);
      operator delete(v2);
      v2 = v3;
    }
    while ( v3 != *(void ***)a1 );
  }
}

```

## disassembly

```asm
0x1800080bc  mov     [rsp+arg_0], rbx
0x1800080c1  mov     [rsp+arg_8], rsi
0x1800080c6  push    rdi
0x1800080c7  sub     rsp, 20h
0x1800080cb  mov     rax, [rcx]
0x1800080ce  mov     rdi, rcx
0x1800080d1  mov     rsi, [rax]
0x1800080d4  mov     [rax], rax
0x1800080d7  mov     rax, [rcx]
0x1800080da  mov     [rax+8], rax
0x1800080de  mov     qword ptr [rcx+8], 0
0x1800080e6  cmp     rsi, [rcx]
0x1800080e9  jz      short loc_18000810E
0x1800080eb  mov     rbx, [rsi]
0x1800080ee  lea     rcx, [rsi+10h]; this
0x1800080f2  call    ??1Command@@QEAA@XZ; Command::~Command(void)
0x1800080f7  mov     rcx, rsi
0x1800080fa  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180008101  nop     dword ptr [rax+rax+00h]
0x180008106  mov     rsi, rbx
0x180008109  cmp     rbx, [rdi]
0x18000810c  jnz     short loc_1800080EB
0x18000810e  mov     rbx, [rsp+28h+arg_0]
0x180008113  mov     rsi, [rsp+28h+arg_8]
0x180008118  add     rsp, 20h
0x18000811c  pop     rdi
0x18000811d  retn
```
