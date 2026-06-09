# CLdapStore::`scalar deleting destructor'(uint)

- ea: `0x18001d024`
- end: `0x18001d044`
- name: `??_GCLdapStore@@QEAAPEAXI@Z`
- size: `32`
- prototype: `struct _RTL_CRITICAL_SECTION *__fastcall(struct _RTL_CRITICAL_SECTION *hMem)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18001d460`
- `0x18001d4f0`

## callees

- `0x18000a990`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001d02d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001d02d`

## pseudocode

```c
struct _RTL_CRITICAL_SECTION *__fastcall CLdapStore::`scalar deleting destructor'(struct _RTL_CRITICAL_SECTION *hMem)
{
  DeleteCriticalSection(hMem);
  operator delete(hMem);
  return hMem;
}

```

## disassembly

```asm
0x18001d024  push    rbx
0x18001d026  sub     rsp, 20h
0x18001d02a  mov     rbx, rcx
0x18001d02d  call    cs:__imp_DeleteCriticalSection
0x18001d033  mov     rcx, rbx; hMem
0x18001d036  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001d03b  mov     rax, rbx
0x18001d03e  add     rsp, 20h
0x18001d042  pop     rbx
0x18001d043  retn
```
