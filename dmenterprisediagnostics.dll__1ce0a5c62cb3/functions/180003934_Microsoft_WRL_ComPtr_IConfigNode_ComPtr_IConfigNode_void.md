# Microsoft::WRL::ComPtr<IConfigNode>::~ComPtr<IConfigNode>(void)

- ea: `0x180003934`
- end: `0x180003939`
- name: `??1?$ComPtr@UIConfigNode@@@WRL@Microsoft@@QEAA@XZ`
- size: `5`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `7`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800245ec`
- `0x180024634`
- `0x18002497f`
- `0x1800249c7`
- `0x180024a11`
- `0x180024a59`
- `0x180024ab2`

## callees

- `0x180004f58`

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
0x180003934  jmp     ?InternalRelease@?$ComPtr@UIConfigNode@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(void)
```
