# CPublicNotification::UnRegister(void)

- ea: `0x1800208e0`
- end: `0x180020b5b`
- name: `?UnRegister@CPublicNotification@@UEAAJXZ`
- size: `635`
- prototype: `__int64 __fastcall(CPublicNotification *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800207dc`

## callees

- `0x1800208e0`
- `0x18004b460`
- `0x18004b830`
- `0x180097010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180020a94`
- `ntdll!RtlReleaseResource` at `0x180020b36`
- `ntdll!RtlReleaseResource` at `0x180020a94`
- `ntdll!RtlReleaseResource` at `0x180020b36`
- `ntdll!RtlAcquireResourceExclusive` at `0x180020a3c`
- `ntdll!RtlAcquireResourceExclusive` at `0x180020ac1`
- `ntdll!RtlAcquireResourceExclusive` at `0x180020a3c`
- `ntdll!RtlAcquireResourceExclusive` at `0x180020ac1`
- `ntdll!EtwEventWriteTransfer` at `0x180020a21`
- `ntdll!EtwEventWriteTransfer` at `0x180020a21`

## pseudocode

```c

```
