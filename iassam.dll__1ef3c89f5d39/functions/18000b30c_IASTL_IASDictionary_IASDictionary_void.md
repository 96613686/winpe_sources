# IASTL::IASDictionary::~IASDictionary(void)

- ea: `0x18000b30c`
- end: `0x18000b331`
- name: `??1IASDictionary@IASTL@@QEAA@XZ`
- size: `37`
- prototype: `void __fastcall(IASTL::IASDictionary *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001bcf8`
- `0x18002ccad`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18000b324`
- `OLEAUT32!__imp_VariantClear` at `0x18000b324`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b319`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b319`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall IASTL::IASDictionary::~IASDictionary(VARIANTARG *this)
{
  CoTaskMemFree(this->pRecInfo);
  VariantClear(this + 3);
}

```

## disassembly

```asm
0x18000b30c  push    rbx
0x18000b30e  sub     rsp, 20h
0x18000b312  mov     rbx, rcx
0x18000b315  mov     rcx, [rcx+10h]; pv
0x18000b319  call    cs:__imp_CoTaskMemFree
0x18000b31f  nop
0x18000b320  lea     rcx, [rbx+48h]; pvarg
0x18000b324  call    cs:__imp_VariantClear
0x18000b32a  nop
0x18000b32b  add     rsp, 20h
0x18000b32f  pop     rbx
0x18000b330  retn
```
