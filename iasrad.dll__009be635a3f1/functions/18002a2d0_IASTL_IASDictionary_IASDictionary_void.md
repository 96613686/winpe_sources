# IASTL::IASDictionary::~IASDictionary(void)

- ea: `0x18002a2d0`
- end: `0x18002a2f3`
- name: `??1IASDictionary@IASTL@@QEAA@XZ`
- size: `35`
- prototype: `void __fastcall(IASTL::IASDictionary *__hidden this)`
- caller_count: `5`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000dcc8`
- `0x18001be88`
- `0x180020578`
- `0x18002e931`
- `0x18002f19a`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18002a2ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a2dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a2dd`

## pseudocode

```c
void __fastcall IASTL::IASDictionary::~IASDictionary(VARIANTARG *this)
{
  CoTaskMemFree(this->pRecInfo);
  VariantClear(this + 3);
}

```

## disassembly

```asm
0x18002a2d0  push    rbx
0x18002a2d2  sub     rsp, 20h
0x18002a2d6  mov     rbx, rcx
0x18002a2d9  mov     rcx, [rcx+10h]; pv
0x18002a2dd  call    cs:__imp_CoTaskMemFree
0x18002a2e3  lea     rcx, [rbx+48h]
0x18002a2e7  add     rsp, 20h
0x18002a2eb  pop     rbx
0x18002a2ec  jmp     cs:__imp_VariantClear
```
