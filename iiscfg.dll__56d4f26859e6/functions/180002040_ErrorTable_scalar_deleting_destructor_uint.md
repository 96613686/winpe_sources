# ErrorTable::`scalar deleting destructor'(uint)

- ea: `0x180002040`
- end: `0x180002070`
- name: `??_GErrorTable@@UEAAPEAXI@Z`
- size: `48`
- prototype: `void *__fastcall(ErrorTable *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180001f94`
- `0x180002040`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18000205c`
- `ole32!CoTaskMemFree` at `0x18000205c`

## pseudocode

```c
ErrorTable *__fastcall ErrorTable::`scalar deleting destructor'(ErrorTable *this, char a2)
{
  ErrorTable::~ErrorTable(this);
  if ( (a2 & 1) != 0 )
    CoTaskMemFree(this);
  return this;
}

```

## disassembly

```asm
0x180002040  mov     [rsp+arg_0], rbx
0x180002045  push    rdi
0x180002046  sub     rsp, 20h
0x18000204a  mov     ebx, edx
0x18000204c  mov     rdi, rcx
0x18000204f  call    ??1ErrorTable@@UEAA@XZ; ErrorTable::~ErrorTable(void)
0x180002054  test    bl, 1
0x180002057  jz      short loc_180002062
0x180002059  mov     rcx, rdi; pv
0x18000205c  call    cs:__imp_CoTaskMemFree
0x180002062  mov     rbx, [rsp+28h+arg_0]
0x180002067  mov     rax, rdi
0x18000206a  add     rsp, 20h
0x18000206e  pop     rdi
0x18000206f  retn
```
