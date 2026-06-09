# freefunc

- ea: `0x1800159e0`
- end: `0x1800159e7`
- name: `freefunc`
- size: `7`
- prototype: `void __stdcall(LPVOID pv)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800159e0`

## pseudocode

```c
// attributes: thunk
void __stdcall freefunc(LPVOID pv)
{
  CoTaskMemFree(pv);
}

```

## disassembly

```asm
0x1800159e0  jmp     cs:__imp_CoTaskMemFree
```
