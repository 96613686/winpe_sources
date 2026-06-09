# std::list<Command,std::allocator<Command>>::~list<Command,std::allocator<Command>>(void)

- ea: `0x18000a490`
- end: `0x18000a503`
- name: `??1?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAA@XZ`
- size: `115`
- prototype: `void(void *)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000a50c`
- `0x18000c47c`
- `0x18000da28`
- `0x18000dc94`

## callees

- `0x18000a490`
- `0x18000a554`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000a4d1`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a4d1`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a4f7`

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
0x18000a490  mov     [rsp+arg_0], rbx
0x18000a495  mov     [rsp+arg_8], rsi
0x18000a49a  push    rdi
0x18000a49b  sub     rsp, 20h
0x18000a49f  mov     rax, [rcx]
0x18000a4a2  mov     rdi, rcx
0x18000a4a5  mov     rsi, [rax]
0x18000a4a8  mov     [rax], rax
0x18000a4ab  mov     rax, [rcx]
0x18000a4ae  mov     [rax+8], rax
0x18000a4b2  mov     qword ptr [rcx+8], 0
0x18000a4ba  mov     rcx, [rcx]
0x18000a4bd  cmp     rsi, rcx
0x18000a4c0  jz      short loc_18000A4E8
0x18000a4c2  mov     rbx, [rsi]
0x18000a4c5  lea     rcx, [rsi+10h]; this
0x18000a4c9  call    ??1Command@@QEAA@XZ; Command::~Command(void)
0x18000a4ce  mov     rcx, rsi
0x18000a4d1  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000a4d8  nop     dword ptr [rax+rax+00h]
0x18000a4dd  mov     rcx, [rdi]
0x18000a4e0  mov     rsi, rbx
0x18000a4e3  cmp     rbx, rcx
0x18000a4e6  jnz     short loc_18000A4C2
0x18000a4e8  mov     rbx, [rsp+28h+arg_0]
0x18000a4ed  mov     rsi, [rsp+28h+arg_8]
0x18000a4f2  add     rsp, 20h
0x18000a4f6  pop     rdi
0x18000a4f7  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
