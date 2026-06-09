# std::list<Command,std::allocator<Command>>::_Tidy(void)

- ea: `0x140007dd8`
- end: `0x140007e34`
- name: `?_Tidy@?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAAXXZ`
- size: `92`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000ac42`

## callees

- `0x140007dd8`
- `0x14000a190`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x140007e16`
- `msvcrt!??3@YAXPEAX@Z` at `0x140007e16`

## pseudocode

```c
void __fastcall std::list<Command>::_Tidy(__int64 a1)
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
0x140007dd8  mov     [rsp+arg_0], rbx
0x140007ddd  mov     [rsp+arg_8], rsi
0x140007de2  push    rdi
0x140007de3  sub     rsp, 20h
0x140007de7  mov     rax, [rcx]
0x140007dea  mov     rdi, rcx
0x140007ded  mov     rsi, [rax]
0x140007df0  mov     [rax], rax
0x140007df3  mov     rax, [rcx]
0x140007df6  mov     [rax+8], rax
0x140007dfa  mov     qword ptr [rcx+8], 0
0x140007e02  cmp     rsi, [rcx]
0x140007e05  jz      short loc_140007E24
0x140007e07  mov     rbx, [rsi]
0x140007e0a  lea     rcx, [rsi+10h]; this
0x140007e0e  call    ??1Command@@QEAA@XZ; Command::~Command(void)
0x140007e13  mov     rcx, rsi
0x140007e16  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140007e1c  mov     rsi, rbx
0x140007e1f  cmp     rbx, [rdi]
0x140007e22  jnz     short loc_140007E07
0x140007e24  mov     rbx, [rsp+28h+arg_0]
0x140007e29  mov     rsi, [rsp+28h+arg_8]
0x140007e2e  add     rsp, 20h
0x140007e32  pop     rdi
0x140007e33  retn
```
