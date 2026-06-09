# CCommand::`scalar deleting destructor'(uint)

- ea: `0x180004220`
- end: `0x180004251`
- name: `??_GCCommand@@EEAAPEAXI@Z`
- size: `49`
- prototype: `void *__fastcall(CCommand *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180004220`
- `0x180004a80`
- `0x180004fbc`

## pseudocode

```c
CCommand *__fastcall CCommand::`scalar deleting destructor'(CCommand *this, char a2)
{
  CCommand::~CCommand(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180004220  mov     [rsp+arg_0], rbx
0x180004225  push    rdi
0x180004226  sub     rsp, 20h
0x18000422a  mov     edi, edx
0x18000422c  mov     rbx, rcx
0x18000422f  call    ??1CCommand@@EEAA@XZ; CCommand::~CCommand(void)
0x180004234  test    dil, 1
0x180004238  jz      short loc_180004242
0x18000423a  mov     rcx, rbx; Block
0x18000423d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004242  mov     rax, rbx
0x180004245  mov     rbx, [rsp+28h+arg_0]
0x18000424a  add     rsp, 20h
0x18000424e  pop     rdi
0x18000424f  retn
```
