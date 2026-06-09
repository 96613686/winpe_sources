# operator delete(void *)

- ea: `0x180001ee0`
- end: `0x180001ee7`
- name: `??3@YAXPEAX@Z`
- size: `7`
- prototype: `void __stdcall(LPVOID pv)`
- caller_count: `4`
- callee_count: `0`
- tags: `file_ops, service_task`

## callers

- `0x180001e50`
- `0x18002e717`
- `0x18002e729`
- `0x18002e82b`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180001ee0`

## pseudocode

```c
// attributes: thunk
void __stdcall operator delete(LPVOID pv)
{
  CoTaskMemFree(pv);
}

```

## disassembly

```asm
0x180001ee0  jmp     cs:__imp_CoTaskMemFree
```
