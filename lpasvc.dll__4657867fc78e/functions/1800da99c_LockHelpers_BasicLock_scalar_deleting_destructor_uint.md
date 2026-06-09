# LockHelpers::BasicLock::`scalar deleting destructor'(uint)

- ea: `0x1800da99c`
- end: `0x1800da9c1`
- name: `??_GBasicLock@LockHelpers@@QEAAPEAXI@Z`
- size: `37`
- prototype: `void *__fastcall(LockHelpers::BasicLock *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800da8d4`
- `0x1800eaeb4`

## callees

- `0x18000e430`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800da9a5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800da9a5`

## pseudocode

```c
struct _RTL_CRITICAL_SECTION *__fastcall LockHelpers::BasicLock::`scalar deleting destructor'(
        struct _RTL_CRITICAL_SECTION *this)
{
  DeleteCriticalSection(this);
  operator delete(this, (const struct std::nothrow_t *)0x28);
  return this;
}

```

## disassembly

```asm
0x1800da99c  push    rbx
0x1800da99e  sub     rsp, 20h
0x1800da9a2  mov     rbx, rcx
0x1800da9a5  call    cs:__imp_DeleteCriticalSection
0x1800da9ab  mov     edx, 28h ; '('; struct std::nothrow_t *
0x1800da9b0  mov     rcx, rbx; void *
0x1800da9b3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800da9b8  mov     rax, rbx
0x1800da9bb  add     rsp, 20h
0x1800da9bf  pop     rbx
0x1800da9c0  retn
```
