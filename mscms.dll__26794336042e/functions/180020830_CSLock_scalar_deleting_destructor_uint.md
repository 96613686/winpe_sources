# CSLock::`scalar deleting destructor'(uint)

- ea: `0x180020830`
- end: `0x180020856`
- name: `??_GCSLock@@QEAAPEAXI@Z`
- size: `38`
- prototype: `struct _RTL_CRITICAL_SECTION *__fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18001c894`
- `0x18004c424`

## callees

- `0x18002e614`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180020839`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180020839`

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
0x180020830  push    rbx
0x180020832  sub     rsp, 20h
0x180020836  mov     rbx, rcx
0x180020839  call    cs:__imp_DeleteCriticalSection
0x18002083f  nop
0x180020840  mov     edx, 28h ; '('; unsigned __int64
0x180020845  mov     rcx, rbx; void *
0x180020848  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002084d  mov     rax, rbx
0x180020850  add     rsp, 20h
0x180020854  pop     rbx
0x180020855  retn
```
