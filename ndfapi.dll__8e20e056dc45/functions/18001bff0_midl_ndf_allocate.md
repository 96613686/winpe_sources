# midl_ndf_allocate

- ea: `0x18001bff0`
- end: `0x18001bff7`
- name: `midl_ndf_allocate`
- size: `7`
- prototype: `LPVOID __stdcall(SIZE_T cb)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x18001bff0`

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
0x18001bff0  jmp     cs:__imp_CoTaskMemAlloc
```
