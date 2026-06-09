# WINRT_IMPL_CoTaskMemAlloc

- ea: `0x18000241d`
- end: `0x180002423`
- name: `WINRT_IMPL_CoTaskMemAlloc`
- size: `6`
- prototype: `LPVOID __stdcall(SIZE_T cb)`
- caller_count: `14`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x180004420`
- `0x1800044b0`
- `0x180004540`
- `0x1800045d0`
- `0x1800046e0`
- `0x180004c34`
- `0x1800109c0`
- `0x180010a60`
- `0x180014ab0`
- `0x180019270`
- `0x1800195ec`
- `0x18001ba60`
- `0x18001d430`
- `0x180020cc0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000241d`

## pseudocode

```c
// attributes: thunk
LPVOID __stdcall WINRT_IMPL_CoTaskMemAlloc(SIZE_T cb)
{
  return CoTaskMemAlloc(cb);
}

```

## disassembly

```asm
0x18000241d  jmp     cs:__imp_CoTaskMemAlloc
```
