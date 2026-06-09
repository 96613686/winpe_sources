# CReadWriteLock::~CReadWriteLock(void)

- ea: `0x14001c7e4`
- end: `0x14001c812`
- name: `??1CReadWriteLock@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(CReadWriteLock *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140003c5c`
- `0x140005db8`
- `0x140005e40`
- `0x14001d401`
- `0x14001e055`

## callees

- `0x14001c7e4`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14001c7f6`
- `KERNEL32!CloseHandle` at `0x14001c805`
- `KERNEL32!CloseHandle` at `0x14001c7f6`
- `KERNEL32!CloseHandle` at `0x14001c805`

## pseudocode

```c
void __fastcall CReadWriteLock::~CReadWriteLock(CReadWriteLock *this)
{
  void *v2; // rcx
  void *v3; // rcx

  v2 = (void *)*((_QWORD *)this + 1);
  if ( v2 )
    CloseHandle(v2);
  v3 = (void *)*((_QWORD *)this + 2);
  if ( v3 )
    CloseHandle(v3);
}

```

## disassembly

```asm
0x14001c7e4  push    rbx
0x14001c7e6  sub     rsp, 20h
0x14001c7ea  mov     rbx, rcx
0x14001c7ed  mov     rcx, [rcx+8]; hObject
0x14001c7f1  test    rcx, rcx
0x14001c7f4  jz      short loc_14001C7FC
0x14001c7f6  call    cs:__imp_CloseHandle
0x14001c7fc  mov     rcx, [rbx+10h]; hObject
0x14001c800  test    rcx, rcx
0x14001c803  jz      short loc_14001C80C
0x14001c805  call    cs:__imp_CloseHandle
0x14001c80b  nop
0x14001c80c  add     rsp, 20h
0x14001c810  pop     rbx
0x14001c811  retn
```
