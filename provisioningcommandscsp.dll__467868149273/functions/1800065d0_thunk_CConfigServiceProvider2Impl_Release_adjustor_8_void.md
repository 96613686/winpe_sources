# [thunk]:CConfigServiceProvider2Impl::Release`adjustor{8}' (void)

- ea: `0x1800065d0`
- end: `0x1800065d9`
- name: `?Release@CConfigServiceProvider2Impl@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task`

## callees

- `0x180008690`

## pseudocode

```c
__int64 __fastcall CConfigServiceProvider2Impl::Release(__int64 a1)
{
  return CConfigServiceProvider2Impl::Release((CConfigServiceProvider2Impl *)(a1 - 8));
}

```

## disassembly

```asm
0x1800065d0  sub     rcx, 8; this
0x1800065d4  jmp     ?Release@CConfigServiceProvider2Impl@@UEAAKXZ; CConfigServiceProvider2Impl::Release(void)
```
