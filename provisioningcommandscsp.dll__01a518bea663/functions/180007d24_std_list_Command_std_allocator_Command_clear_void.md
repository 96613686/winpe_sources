# std::list<Command,std::allocator<Command>>::clear(void)

- ea: `0x180007d24`
- end: `0x180007d80`
- name: `?clear@?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAAXXZ`
- size: `92`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000ce86`
- `0x18000d3ea`

## callees

- `0x180007d24`
- `0x18000a050`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180007d62`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007d62`

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
0x180007d24  mov     [rsp+arg_0], rbx
0x180007d29  mov     [rsp+arg_8], rsi
0x180007d2e  push    rdi
0x180007d2f  sub     rsp, 20h
0x180007d33  mov     rax, [rcx]
0x180007d36  mov     rdi, rcx
0x180007d39  mov     rsi, [rax]
0x180007d3c  mov     [rax], rax
0x180007d3f  mov     rax, [rcx]
0x180007d42  mov     [rax+8], rax
0x180007d46  mov     qword ptr [rcx+8], 0
0x180007d4e  cmp     rsi, [rcx]
0x180007d51  jz      short loc_180007D70
0x180007d53  mov     rbx, [rsi]
0x180007d56  lea     rcx, [rsi+10h]; this
0x180007d5a  call    ??1Command@@QEAA@XZ; Command::~Command(void)
0x180007d5f  mov     rcx, rsi
0x180007d62  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180007d68  mov     rsi, rbx
0x180007d6b  cmp     rbx, [rdi]
0x180007d6e  jnz     short loc_180007D53
0x180007d70  mov     rbx, [rsp+28h+arg_0]
0x180007d75  mov     rsi, [rsp+28h+arg_8]
0x180007d7a  add     rsp, 20h
0x180007d7e  pop     rdi
0x180007d7f  retn
```
