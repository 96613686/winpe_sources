# TFixedTableHeapBuilder::`vector deleting destructor'(uint)

- ea: `0x180024a80`
- end: `0x180024ab0`
- name: `??_ETFixedTableHeapBuilder@@UEAAPEAXI@Z`
- size: `48`
- prototype: `void *__fastcall(TFixedTableHeapBuilder *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180024a48`
- `0x180024a80`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180024a9c`
- `ole32!CoTaskMemFree` at `0x180024a9c`

## pseudocode

```c
TFixedTableHeapBuilder *__fastcall TFixedTableHeapBuilder::`vector deleting destructor'(
        TFixedTableHeapBuilder *this,
        char a2)
{
  TFixedTableHeapBuilder::~TFixedTableHeapBuilder(this);
  if ( (a2 & 1) != 0 )
    CoTaskMemFree(this);
  return this;
}

```

## disassembly

```asm
0x180024a80  mov     [rsp+arg_0], rbx
0x180024a85  push    rdi
0x180024a86  sub     rsp, 20h
0x180024a8a  mov     ebx, edx
0x180024a8c  mov     rdi, rcx
0x180024a8f  call    ??1TFixedTableHeapBuilder@@UEAA@XZ; TFixedTableHeapBuilder::~TFixedTableHeapBuilder(void)
0x180024a94  test    bl, 1
0x180024a97  jz      short loc_180024AA2
0x180024a99  mov     rcx, rdi; pv
0x180024a9c  call    cs:__imp_CoTaskMemFree
0x180024aa2  mov     rax, rdi
0x180024aa5  mov     rbx, [rsp+28h+arg_0]
0x180024aaa  add     rsp, 20h
0x180024aae  pop     rdi
0x180024aaf  retn
```
