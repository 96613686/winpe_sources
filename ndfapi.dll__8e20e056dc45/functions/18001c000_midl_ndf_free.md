# midl_ndf_free

- ea: `0x18001c000`
- end: `0x18001c007`
- name: `midl_ndf_free`
- size: `7`
- prototype: `void __stdcall(LPVOID pv)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18001c000`

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
0x18001c000  jmp     cs:__imp_CoTaskMemFree
```
