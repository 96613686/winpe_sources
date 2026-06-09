# std::list<Command,std::allocator<Command>>::~list<Command,std::allocator<Command>>(void)

- ea: `0x180009fa0`
- end: `0x18000a008`
- name: `??1?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAA@XZ`
- size: `104`
- prototype: `void __fastcall(void ***)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000a010`
- `0x18000be80`
- `0x18000d35c`
- `0x18000d5c4`

## callees

- `0x180009fa0`
- `0x18000a050`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180009fe1`
- `msvcrt!??3@YAXPEAX@Z` at `0x180009fe1`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a001`

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
      Command::~Command((Command *)(v2 + 2));
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
0x180009fa0  mov     [rsp+arg_0], rbx
0x180009fa5  mov     [rsp+arg_8], rsi
0x180009faa  push    rdi
0x180009fab  sub     rsp, 20h
0x180009faf  mov     rax, [rcx]
0x180009fb2  mov     rdi, rcx
0x180009fb5  mov     rsi, [rax]
0x180009fb8  mov     [rax], rax
0x180009fbb  mov     rax, [rcx]
0x180009fbe  mov     [rax+8], rax
0x180009fc2  mov     qword ptr [rcx+8], 0
0x180009fca  mov     rcx, [rcx]
0x180009fcd  cmp     rsi, rcx
0x180009fd0  jz      short loc_180009FF2
0x180009fd2  mov     rbx, [rsi]
0x180009fd5  lea     rcx, [rsi+10h]; this
0x180009fd9  call    ??1Command@@QEAA@XZ; Command::~Command(void)
0x180009fde  mov     rcx, rsi
0x180009fe1  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180009fe7  mov     rcx, [rdi]
0x180009fea  mov     rsi, rbx
0x180009fed  cmp     rbx, rcx
0x180009ff0  jnz     short loc_180009FD2
0x180009ff2  mov     rbx, [rsp+28h+arg_0]
0x180009ff7  mov     rsi, [rsp+28h+arg_8]
0x180009ffc  add     rsp, 20h
0x18000a000  pop     rdi
0x18000a001  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
