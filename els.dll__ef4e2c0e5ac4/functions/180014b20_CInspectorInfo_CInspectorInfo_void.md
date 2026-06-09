# CInspectorInfo::~CInspectorInfo(void)

- ea: `0x180014b20`
- end: `0x180014b43`
- name: `??1CInspectorInfo@@QEAA@XZ`
- size: `35`
- prototype: `void __fastcall(CInspectorInfo *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x18001b910`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180014b2d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180014b2d`
- `KERNEL32!DeleteCriticalSection` at `0x180014b3c`

## pseudocode

```c
void __fastcall CInspectorInfo::~CInspectorInfo(CInspectorInfo *this)
{
  operator delete[](*((void **)this + 2));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
}

```

## disassembly

```asm
0x180014b20  push    rbx
0x180014b22  sub     rsp, 20h
0x180014b26  mov     rbx, rcx
0x180014b29  mov     rcx, [rcx+10h]
0x180014b2d  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180014b33  lea     rcx, [rbx+18h]
0x180014b37  add     rsp, 20h
0x180014b3b  pop     rbx
0x180014b3c  jmp     cs:__imp_DeleteCriticalSection
```
