# std::unique_ptr<ushort,CoTaskMemDeleter>::~unique_ptr<ushort,CoTaskMemDeleter>(void)

- ea: `0x180007c00`
- end: `0x180007c17`
- name: `??1?$unique_ptr@GUCoTaskMemDeleter@@@std@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(void **)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000b477`
- `0x18000b489`

## callees

- `0x180007c00`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007c0c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007c0c`

## pseudocode

```c
void __fastcall std::unique_ptr<unsigned short,CoTaskMemDeleter>::~unique_ptr<unsigned short,CoTaskMemDeleter>(
        void **a1)
{
  void *v1; // rcx

  v1 = *a1;
  if ( v1 )
    CoTaskMemFree(v1);
}

```

## disassembly

```asm
0x180007c00  sub     rsp, 28h
0x180007c04  mov     rcx, [rcx]; pv
0x180007c07  test    rcx, rcx
0x180007c0a  jz      short loc_180007C12
0x180007c0c  call    cs:__imp_CoTaskMemFree
0x180007c12  add     rsp, 28h
0x180007c16  retn
```
