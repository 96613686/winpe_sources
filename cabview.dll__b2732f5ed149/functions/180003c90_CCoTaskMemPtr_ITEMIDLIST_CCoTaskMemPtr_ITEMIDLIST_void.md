# CCoTaskMemPtr<_ITEMIDLIST>::~CCoTaskMemPtr<_ITEMIDLIST>(void)

- ea: `0x180003c90`
- end: `0x180003ca4`
- name: `??1?$CCoTaskMemPtr@U_ITEMIDLIST@@@@QEAA@XZ`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000570c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003c9d`

## pseudocode

```c
void __fastcall CCoTaskMemPtr<_ITEMIDLIST>::~CCoTaskMemPtr<_ITEMIDLIST>(void **a1)
{
  void *v2; // rcx

  v2 = *a1;
  *a1 = 0;
  CoTaskMemFree(v2);
}

```

## disassembly

```asm
0x180003c90  mov     rax, rcx
0x180003c93  mov     rcx, [rcx]
0x180003c96  mov     qword ptr [rax], 0
0x180003c9d  jmp     cs:__imp_CoTaskMemFree
```
