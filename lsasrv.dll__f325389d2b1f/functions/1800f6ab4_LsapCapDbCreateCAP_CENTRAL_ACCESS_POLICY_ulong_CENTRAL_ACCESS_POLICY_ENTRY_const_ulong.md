# LsapCapDbCreateCAP(_CENTRAL_ACCESS_POLICY *,ulong,_CENTRAL_ACCESS_POLICY_ENTRY const *,ulong)

- ea: `0x1800f6ab4`
- end: `0x1800f6dda`
- name: `?LsapCapDbCreateCAP@@YAJPEAU_CENTRAL_ACCESS_POLICY@@KPEBU_CENTRAL_ACCESS_POLICY_ENTRY@@K@Z`
- size: `806`
- prototype: `__int64 __fastcall(struct _CENTRAL_ACCESS_POLICY *, unsigned int, const struct _CENTRAL_ACCESS_POLICY_ENTRY *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x1800f268c`

## callees

- `0x1800b86d0`
- `0x1800b9304`
- `0x1800f6ab4`
- `0x1800f9990`

## import_xrefs

- `ntdll!NtCreateKeyTransacted` at `0x1800f6bdf`
- `ntdll!NtCreateKeyTransacted` at `0x1800f6bdf`
- `ntdll!NtSetValueKey` at `0x1800f6c25`
- `ntdll!NtSetValueKey` at `0x1800f6c64`
- `ntdll!NtSetValueKey` at `0x1800f6c9d`
- `ntdll!NtSetValueKey` at `0x1800f6cd6`
- `ntdll!NtSetValueKey` at `0x1800f6d0d`
- `ntdll!NtSetValueKey` at `0x1800f6d88`
- `ntdll!NtSetValueKey` at `0x1800f6c25`
- `ntdll!NtSetValueKey` at `0x1800f6c64`
- `ntdll!NtSetValueKey` at `0x1800f6c9d`
- `ntdll!NtSetValueKey` at `0x1800f6cd6`
- `ntdll!NtSetValueKey` at `0x1800f6d0d`
- `ntdll!NtSetValueKey` at `0x1800f6d88`
- `ntdll!NtClose` at `0x1800f6da0`
- `ntdll!NtClose` at `0x1800f6da0`
- `ntdll!RtlLengthSid` at `0x1800f6bf8`
- `ntdll!RtlLengthSid` at `0x1800f6bf8`

## pseudocode

```c

```
