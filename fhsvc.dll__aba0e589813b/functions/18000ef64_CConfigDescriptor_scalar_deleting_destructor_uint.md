# CConfigDescriptor::`scalar deleting destructor'(uint)

- ea: `0x18000ef64`
- end: `0x18000ef84`
- name: `??_GCConfigDescriptor@@QEAAPEAXI@Z`
- size: `32`
- prototype: `CConfigDescriptor *__fastcall(CConfigDescriptor *this)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, registry_config`

## callers

- `0x18000eec4`
- `0x180012500`

## callees

- `0x18000ee2c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000ef75`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000ef75`

## pseudocode

```c
CConfigDescriptor *__fastcall CConfigDescriptor::`scalar deleting destructor'(CConfigDescriptor *this)
{
  CConfigDescriptor::~CConfigDescriptor(this);
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000ef64  push    rbx
0x18000ef66  sub     rsp, 20h
0x18000ef6a  mov     rbx, rcx
0x18000ef6d  call    ??1CConfigDescriptor@@QEAA@XZ; CConfigDescriptor::~CConfigDescriptor(void)
0x18000ef72  mov     rcx, rbx
0x18000ef75  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000ef7b  mov     rax, rbx
0x18000ef7e  add     rsp, 20h
0x18000ef82  pop     rbx
0x18000ef83  retn
```
