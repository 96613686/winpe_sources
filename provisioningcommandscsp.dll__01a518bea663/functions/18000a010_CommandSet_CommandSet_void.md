# CommandSet::~CommandSet(void)

- ea: `0x18000a010`
- end: `0x18000a04a`
- name: `??1CommandSet@@QEAA@XZ`
- size: `58`
- prototype: `void __fastcall(CommandSet *__hidden this)`
- caller_count: `10`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180006a00`
- `0x180006b10`
- `0x1800071d8`
- `0x180009290`
- `0x18000b7dc`
- `0x18000cee6`
- `0x18000cf52`
- `0x18000d2e8`
- `0x18000d51f`
- `0x18000d58c`

## callees

- `0x180009fa0`
- `0x18000a010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000a024`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a024`

## pseudocode

```c
void __fastcall CommandSet::~CommandSet(CommandSet *this)
{
  if ( *((_QWORD *)this + 6) >= 8u )
    operator delete(*((void **)this + 3));
  *((_QWORD *)this + 6) = 7;
  *((_QWORD *)this + 5) = 0;
  *((_WORD *)this + 12) = 0;
  std::list<Command>::~list<Command>((void ***)this + 1);
}

```

## disassembly

```asm
0x18000a010  push    rbx
0x18000a012  sub     rsp, 20h
0x18000a016  cmp     qword ptr [rcx+30h], 8
0x18000a01b  mov     rbx, rcx
0x18000a01e  jb      short loc_18000A02A
0x18000a020  mov     rcx, [rcx+18h]
0x18000a024  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000a02a  xor     eax, eax
0x18000a02c  mov     qword ptr [rbx+30h], 7
0x18000a034  mov     [rbx+28h], rax
0x18000a038  lea     rcx, [rbx+8]; void *
0x18000a03c  mov     [rbx+18h], ax
0x18000a040  add     rsp, 20h
0x18000a044  pop     rbx
0x18000a045  jmp     ??1?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAA@XZ; std::list<Command>::~list<Command>(void)
```
