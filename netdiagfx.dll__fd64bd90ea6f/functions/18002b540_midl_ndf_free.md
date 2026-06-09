# midl_ndf_free

- ea: `0x18002b540`
- end: `0x18002b547`
- name: `midl_ndf_free`
- size: `7`
- prototype: `void __stdcall(LPVOID pv)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b540`

## pseudocode

```c
// attributes: thunk
void __stdcall midl_ndf_free(LPVOID pv)
{
  CoTaskMemFree(pv);
}

```

## disassembly

```asm
0x18002b540  jmp     cs:__imp_CoTaskMemFree
```
