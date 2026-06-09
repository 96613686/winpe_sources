# [thunk]:CConfigServiceProvider2Impl::QueryInterface`adjustor{8}' (_GUID const &,void * *)

- ea: `0x1800062c0`
- end: `0x1800062c9`
- name: `?QueryInterface@CConfigServiceProvider2Impl@@W7EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: `__int64 __fastcall(__int64, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task`

## callees

- `0x180008260`

## pseudocode

```c
__int64 __fastcall CConfigServiceProvider2Impl::QueryInterface(__int64 a1, const struct _GUID *a2, void **a3)
{
  return CConfigServiceProvider2Impl::QueryInterface((CConfigServiceProvider2Impl *)(a1 - 8), a2, a3);
}

```

## disassembly

```asm
0x1800062c0  sub     rcx, 8; this
0x1800062c4  jmp     ?QueryInterface@CConfigServiceProvider2Impl@@UEAAJAEBU_GUID@@PEAPEAX@Z; CConfigServiceProvider2Impl::QueryInterface(_GUID const &,void * *)
```
