# TFixupHeaps::`vector deleting destructor'(uint)

- ea: `0x180015750`
- end: `0x180015780`
- name: `??_ETFixupHeaps@@UEAAPEAXI@Z`
- size: `48`
- prototype: `void *__fastcall(TFixupHeaps *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180015578`
- `0x180015750`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18001576c`
- `ole32!CoTaskMemFree` at `0x18001576c`

## pseudocode

```c
TFixupHeaps *__fastcall TFixupHeaps::`vector deleting destructor'(TFixupHeaps *this, char a2)
{
  TFixupHeaps::~TFixupHeaps(this);
  if ( (a2 & 1) != 0 )
    CoTaskMemFree(this);
  return this;
}

```

## disassembly

```asm
0x180015750  mov     [rsp+arg_0], rbx
0x180015755  push    rdi
0x180015756  sub     rsp, 20h
0x18001575a  mov     ebx, edx
0x18001575c  mov     rdi, rcx
0x18001575f  call    ??1TFixupHeaps@@UEAA@XZ; TFixupHeaps::~TFixupHeaps(void)
0x180015764  test    bl, 1
0x180015767  jz      short loc_180015772
0x180015769  mov     rcx, rdi; pv
0x18001576c  call    cs:__imp_CoTaskMemFree
0x180015772  mov     rax, rdi
0x180015775  mov     rbx, [rsp+28h+arg_0]
0x18001577a  add     rsp, 20h
0x18001577e  pop     rdi
0x18001577f  retn
```
