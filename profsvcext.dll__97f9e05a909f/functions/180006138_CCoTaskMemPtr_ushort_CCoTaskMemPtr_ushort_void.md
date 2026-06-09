# CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)

- ea: `0x180006138`
- end: `0x18000614c`
- name: `??1?$CCoTaskMemPtr@G@@QEAA@XZ`
- size: `20`
- prototype: `void __fastcall(void **)`
- caller_count: `3`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005b54`
- `0x180006154`
- `0x18000fa10`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006145`

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
0x180006138  mov     rax, rcx
0x18000613b  mov     rcx, [rcx]
0x18000613e  mov     qword ptr [rax], 0
0x180006145  jmp     cs:__imp_CoTaskMemFree
```
