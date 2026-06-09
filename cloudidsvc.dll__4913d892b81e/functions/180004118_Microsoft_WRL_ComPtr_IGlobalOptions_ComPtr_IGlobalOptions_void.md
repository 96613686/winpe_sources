# Microsoft::WRL::ComPtr<IGlobalOptions>::~ComPtr<IGlobalOptions>(void)

- ea: `0x180004118`
- end: `0x18000411d`
- name: `??1?$ComPtr@UIGlobalOptions@@@WRL@Microsoft@@QEAA@XZ`
- size: `5`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800108fa`

## callees

- `0x180006160`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall Microsoft::WRL::ComPtr<IGlobalOptions>::~ComPtr<IGlobalOptions>(__int64 a1)
{
  return Microsoft::WRL::ComPtr<IGlobalOptions>::InternalRelease(a1);
}

```

## disassembly

```asm
0x180004118  jmp     ?InternalRelease@?$ComPtr@UIGlobalOptions@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IGlobalOptions>::InternalRelease(void)
```
