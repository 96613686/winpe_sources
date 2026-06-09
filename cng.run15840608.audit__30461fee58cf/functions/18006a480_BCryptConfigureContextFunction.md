# BCryptConfigureContextFunction

- ea: `0x18006a480`
- end: `0x18006a795`
- name: `BCryptConfigureContextFunction`
- size: `789`
- prototype: `NTSTATUS __stdcall(ULONG dwTable, LPCWSTR pszContext, ULONG dwInterface, LPCWSTR pszFunction, PCRYPT_CONTEXT_FUNCTION_CONFIG pConfig)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config`

## callers

- `0x1800256c8`

## callees

- `0x18001ba40`
- `0x18001bd90`
- `0x180024cd0`
- `0x180024ecc`
- `0x1800289e0`
- `0x180029710`
- `0x180040594`
- `0x180048d50`
- `0x18004c328`
- `0x18006a480`
- `0x18006c9d4`
- `0x18006da1c`
- `0x18006f388`
- `0x180071f64`
- `0x180072a40`
- `0x1800731fc`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18006a6fc`
- `ntoskrnl!RtlInitUnicodeString` at `0x18006a70f`
- `ntoskrnl!RtlInitUnicodeString` at `0x18006a6fc`
- `ntoskrnl!RtlInitUnicodeString` at `0x18006a70f`
- `ntoskrnl!ExReleaseResourceLite` at `0x18006a6ab`
- `ntoskrnl!ExReleaseResourceLite` at `0x18006a6ab`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18006a6b7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18006a6b7`

## pseudocode

```c

```
