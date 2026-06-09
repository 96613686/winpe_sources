# Microsoft::WRL::ComPtr<IShellItemArray>::~ComPtr<IShellItemArray>(void)

- ea: `0x1800132a8`
- end: `0x1800132ad`
- name: `??1?$ComPtr@UIShellItemArray@@@WRL@Microsoft@@QEAA@XZ`
- size: `5`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180019527`
- `0x18001954b`
- `0x18001955d`

## callees

- `0x180004dcc`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall Microsoft::WRL::ComPtr<IShellItemArray>::~ComPtr<IShellItemArray>(__int64 *a1)
{
  return Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a1);
}

```

## disassembly

```asm
0x1800132a8  jmp     ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
```
