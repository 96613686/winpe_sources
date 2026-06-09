# CGPPolicyEventReporting::Report(CGPEventInfo *,int *)

- ea: `0x180030bcc`
- end: `0x180030eb1`
- name: `?Report@CGPPolicyEventReporting@@QEAAKPEAVCGPEventInfo@@PEAH@Z`
- size: `741`
- prototype: `unsigned int __fastcall(CGPPolicyEventReporting *__hidden this, struct CGPEventInfo *, int *)`
- caller_count: `21`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x1800144e4`
- `0x1800147b0`
- `0x18001b490`
- `0x18002d188`
- `0x18002e5a0`
- `0x18002f880`
- `0x1800310b0`
- `0x180039364`
- `0x18003a810`
- `0x18003e060`
- `0x180053870`
- `0x180058620`
- `0x180058f20`
- `0x18005ce5c`
- `0x1800631a8`
- `0x1800689e0`
- `0x18006a2e0`
- `0x180094cb4`
- `0x180098a2c`
- `0x18009ff54`
- `0x1800a1e20`

## callees

- `0x18001ae60`
- `0x180030bcc`
- `0x18005334c`
- `0x18005cc8c`
- `0x180075ec0`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030d9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030dce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030e9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030d9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030dce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030e9b`
- `ntdll!EtwEventWrite` at `0x180030dff`
- `ntdll!EtwEventWrite` at `0x180030dff`
- `ntdll!EtwEventActivityIdControl` at `0x180030d15`
- `ntdll!EtwEventActivityIdControl` at `0x180030d15`
- `ntdll!EtwEventEnabled` at `0x180030c7a`
- `ntdll!EtwEventEnabled` at `0x180030c7a`

## string_xrefs

- `0x180030da3`: `ImpersonateUser() failed with error 0x%x. Will attempt to publish event anyway.`
- `0x180030dd4`: `ImpersonateUser() failed with error 0x%x. Will attempt to publish event anyway.`

## pseudocode

```c

```
