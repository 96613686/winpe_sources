# CSLock::`scalar deleting destructor'(uint)

- ea: `0x180020eac`
- end: `0x180020ed1`
- name: `??_GCSLock@@QEAAPEAXI@Z`
- size: `37`
- prototype: `void *__fastcall(CSLock *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18002089c`

## callees

- `0x180001ea4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180020eb5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180020eb5`

## pseudocode

```c
struct _RTL_CRITICAL_SECTION *__fastcall CSLock::`scalar deleting destructor'(struct _RTL_CRITICAL_SECTION *this)
{
  DeleteCriticalSection(this);
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180020eac  push    rbx
0x180020eae  sub     rsp, 20h
0x180020eb2  mov     rbx, rcx
0x180020eb5  call    cs:__imp_DeleteCriticalSection
0x180020ebb  mov     edx, 28h ; '('
0x180020ec0  mov     rcx, rbx; Block
0x180020ec3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180020ec8  mov     rax, rbx
0x180020ecb  add     rsp, 20h
0x180020ecf  pop     rbx
0x180020ed0  retn
```
