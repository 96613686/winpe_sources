# CHostDLLInfo::`scalar deleting destructor'(uint)

- ea: `0x18001ed98`
- end: `0x18001edb8`
- name: `??_GCHostDLLInfo@@QEAAPEAXI@Z`
- size: `32`
- prototype: `CHostDLLInfo *__fastcall(CHostDLLInfo *this)`
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x18001ef0c`
- `0x18001efbc`
- `0x18002dd8a`
- `0x18002de88`

## callees

- `0x18001eaf4`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001eda9`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001eda9`

## pseudocode

```c
CHostDLLInfo *__fastcall CHostDLLInfo::`scalar deleting destructor'(CHostDLLInfo *this)
{
  CHostDLLInfo::~CHostDLLInfo(this);
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18001ed98  push    rbx
0x18001ed9a  sub     rsp, 20h
0x18001ed9e  mov     rbx, rcx
0x18001eda1  call    ??1CHostDLLInfo@@QEAA@XZ; CHostDLLInfo::~CHostDLLInfo(void)
0x18001eda6  mov     rcx, rbx
0x18001eda9  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001edaf  mov     rax, rbx
0x18001edb2  add     rsp, 20h
0x18001edb6  pop     rbx
0x18001edb7  retn
```
