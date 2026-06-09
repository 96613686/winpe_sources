# NtlmLogging::UpdateFailureReason(_LUID *,_SSP_CONTEXT *)

- ea: `0x18005a080`
- end: `0x18005a20d`
- name: `?UpdateFailureReason@NtlmLogging@@YA?AW4_SECPKG_FAILURE_SPECIAL_REASON@@PEAU_LUID@@PEAU_SSP_CONTEXT@@@Z`
- size: `397`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x1800268dc`

## callees

- `0x18000c5d0`
- `0x18002fb50`
- `0x180052e90`
- `0x18005a080`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x18005a12d`
- `ntdll!RtlReleaseResource` at `0x18005a147`
- `ntdll!RtlReleaseResource` at `0x18005a16f`
- `ntdll!RtlReleaseResource` at `0x18005a17b`
- `ntdll!RtlReleaseResource` at `0x18005a12d`
- `ntdll!RtlReleaseResource` at `0x18005a147`
- `ntdll!RtlReleaseResource` at `0x18005a16f`
- `ntdll!RtlReleaseResource` at `0x18005a17b`
- `ntdll!RtlAcquireResourceShared` at `0x18005a10c`
- `ntdll!RtlAcquireResourceShared` at `0x18005a10c`
- `ntdll!RtlEqualUnicodeString` at `0x18005a1d9`
- `ntdll!RtlEqualUnicodeString` at `0x18005a1d9`

## pseudocode

```c

```
