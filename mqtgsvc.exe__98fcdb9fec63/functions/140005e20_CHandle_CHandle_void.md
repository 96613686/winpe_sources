# CHandle::~CHandle(void)

- ea: `0x140005e20`
- end: `0x140005e38`
- name: `??1CHandle@@QEAA@XZ`
- size: `24`
- prototype: `void __fastcall(void **this)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x140005e40`
- `0x14000ac9c`
- `0x14000d9d0`
- `0x14001d439`
- `0x14001d44f`
- `0x14001dc69`
- `0x14001e4da`
- `0x14001f210`
- `0x14001f230`

## callees

- `0x140005e20`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140005e2c`
- `KERNEL32!CloseHandle` at `0x140005e2c`

## pseudocode

```c
void __fastcall CHandle::~CHandle(void **this)
{
  void *v1; // rcx

  v1 = *this;
  if ( v1 )
    CloseHandle(v1);
}

```

## disassembly

```asm
0x140005e20  sub     rsp, 28h
0x140005e24  mov     rcx, [rcx]; hObject
0x140005e27  test    rcx, rcx
0x140005e2a  jz      short loc_140005E33
0x140005e2c  call    cs:__imp_CloseHandle
0x140005e32  nop
0x140005e33  add     rsp, 28h
0x140005e37  retn
```
