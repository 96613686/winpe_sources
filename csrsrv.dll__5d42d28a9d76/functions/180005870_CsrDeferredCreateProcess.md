# CsrDeferredCreateProcess

- ea: `0x180005870`
- end: `0x180005875`
- name: `CsrDeferredCreateProcess`
- size: `5`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800058b0`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall CsrDeferredCreateProcess(
        HANDLE Handle,
        void *a2,
        _DWORD *a3,
        __int64 a4,
        __int16 a5,
        int *a6,
        _QWORD *a7)
{
  return CsrpCreateProcess(Handle, a2, a3, a4, a5, a6, a7);
}

```

## disassembly

```asm
0x180005870  jmp     CsrpCreateProcess
```
