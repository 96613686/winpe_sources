# TextFileLogger::`scalar deleting destructor'(uint)

- ea: `0x1800129e0`
- end: `0x180012a10`
- name: `??_GTextFileLogger@@UEAAPEAXI@Z`
- size: `48`
- prototype: `void *__fastcall(TextFileLogger *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180012988`
- `0x1800129e0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800129fc`
- `ole32!CoTaskMemFree` at `0x1800129fc`

## pseudocode

```c
TextFileLogger *__fastcall TextFileLogger::`scalar deleting destructor'(TextFileLogger *this, char a2)
{
  TextFileLogger::~TextFileLogger(this);
  if ( (a2 & 1) != 0 )
    CoTaskMemFree(this);
  return this;
}

```

## disassembly

```asm
0x1800129e0  mov     [rsp+arg_0], rbx
0x1800129e5  push    rdi
0x1800129e6  sub     rsp, 20h
0x1800129ea  mov     ebx, edx
0x1800129ec  mov     rdi, rcx
0x1800129ef  call    ??1TextFileLogger@@UEAA@XZ; TextFileLogger::~TextFileLogger(void)
0x1800129f4  test    bl, 1
0x1800129f7  jz      short loc_180012A02
0x1800129f9  mov     rcx, rdi; pv
0x1800129fc  call    cs:__imp_CoTaskMemFree
0x180012a02  mov     rbx, [rsp+28h+arg_0]
0x180012a07  mov     rax, rdi
0x180012a0a  add     rsp, 20h
0x180012a0e  pop     rdi
0x180012a0f  retn
```
