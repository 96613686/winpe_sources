# Microsoft::WRL::ComPtr<IConfigNode>::~ComPtr<IConfigNode>(void)

- ea: `0x180003994`
- end: `0x180003999`
- name: `??1?$ComPtr@UIConfigNode@@@WRL@Microsoft@@QEAA@XZ`
- size: `5`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800254ac`
- `0x1800254f4`
- `0x18002583f`
- `0x180025887`
- `0x1800258d1`
- `0x180025919`
- `0x180025972`

## callees

- `0x1800050e0`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall Microsoft::WRL::ComPtr<IConfigNode>::~ComPtr<IConfigNode>(__int64 a1)
{
  return Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(a1);
}

```

## disassembly

```asm
0x180003994  jmp     ?InternalRelease@?$ComPtr@UIConfigNode@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(void)
```
