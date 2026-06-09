# CommandSet::~CommandSet(void)

- ea: `0x18000a50c`
- end: `0x18000a54c`
- name: `??1CommandSet@@QEAA@XZ`
- size: `64`
- prototype: `void __fastcall(CommandSet *__hidden this)`
- caller_count: `10`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180006d20`
- `0x180006e40`
- `0x18000751c`
- `0x1800096c0`
- `0x18000be6c`
- `0x18000d5ac`
- `0x18000d618`
- `0x18000d9b4`
- `0x18000dbed`
- `0x18000dc5c`

## callees

- `0x18000a490`
- `0x18000a50c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000a520`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a520`

## pseudocode

```c
void __fastcall CommandSet::~CommandSet(void **this)
{
  if ( (unsigned __int64)this[6] >= 8 )
    operator delete(this[3]);
  this[6] = (void *)7;
  this[5] = 0;
  *((_WORD *)this + 12) = 0;
  std::list<Command>::~list<Command>(this + 1);
}

```

## disassembly

```asm
0x18000a50c  push    rbx
0x18000a50e  sub     rsp, 20h
0x18000a512  cmp     qword ptr [rcx+30h], 8
0x18000a517  mov     rbx, rcx
0x18000a51a  jb      short loc_18000A52C
0x18000a51c  mov     rcx, [rcx+18h]
0x18000a520  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000a527  nop     dword ptr [rax+rax+00h]
0x18000a52c  xor     eax, eax
0x18000a52e  mov     qword ptr [rbx+30h], 7
0x18000a536  mov     [rbx+28h], rax
0x18000a53a  lea     rcx, [rbx+8]; void *
0x18000a53e  mov     [rbx+18h], ax
0x18000a542  add     rsp, 20h
0x18000a546  pop     rbx
0x18000a547  jmp     ??1?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAA@XZ; std::list<Command>::~list<Command>(void)
```
