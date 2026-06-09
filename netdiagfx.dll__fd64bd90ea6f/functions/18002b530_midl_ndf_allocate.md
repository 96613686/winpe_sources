# midl_ndf_allocate

- ea: `0x18002b530`
- end: `0x18002b537`
- name: `midl_ndf_allocate`
- size: `7`
- prototype: `LPVOID __stdcall(SIZE_T cb)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002b530`

## pseudocode

```c
// attributes: thunk
LPVOID __stdcall midl_ndf_allocate(SIZE_T cb)
{
  return CoTaskMemAlloc(cb);
}

```

## disassembly

```asm
0x18002b530  jmp     cs:__imp_CoTaskMemAlloc
```
