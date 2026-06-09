# CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)

- ea: `0x18000b2e4`
- end: `0x18000b2f8`
- name: `??1?$CCoTaskMemPtr@G@@QEAA@XZ`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000b300`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b2f1`

## pseudocode

```c
void __fastcall CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(void **a1)
{
  void *v2; // rcx

  v2 = *a1;
  *a1 = 0;
  CoTaskMemFree(v2);
}

```

## disassembly

```asm
0x18000b2e4  mov     rax, rcx
0x18000b2e7  mov     rcx, [rcx]
0x18000b2ea  mov     qword ptr [rax], 0
0x18000b2f1  jmp     cs:__imp_CoTaskMemFree
```
