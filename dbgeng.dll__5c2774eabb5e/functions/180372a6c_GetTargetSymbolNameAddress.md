# GetTargetSymbolNameAddress

- ea: `0x180372a6c`
- end: `0x180372c41`
- name: `GetTargetSymbolNameAddress`
- size: `469`
- prototype: `__int64 __usercall@<rax>(ULONG64 UserContext@<rcx>, DWORD64 BaseOfDll@<rdx>, PCWSTR ImageName, PCWSTR Name)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1803703e8`
- `0x1803737b4`

## callees

- `0x180071a60`
- `0x1800f0f40`
- `0x180372a6c`
- `0x1804da4c0`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x180372adf`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x180372adf`
- `dbghelp!SymFromNameW` at `0x180372bbb`
- `dbghelp!SymFromNameW` at `0x180372bbb`
- `dbghelp!SymLoadModuleExW` at `0x180372b8f`
- `dbghelp!SymLoadModuleExW` at `0x180372b8f`
- `dbghelp!SymInitializeW` at `0x180372b3f`
- `dbghelp!SymInitializeW` at `0x180372b3f`
- `dbghelp!SymRegisterCallbackW64` at `0x180372b62`
- `dbghelp!SymRegisterCallbackW64` at `0x180372b62`
- `dbghelp!SymCleanup` at `0x180372c00`
- `dbghelp!SymCleanup` at `0x180372c00`

## string_xrefs

- `0x180372ad8`: `_NT_SYMBOL_PATH`
- `0x180372b0b`: `Overriding symbol path for %s location to %s\n`
- `0x180372b22`: `The following symbol path will be used to find %s kernel symbols: %s\n`
- `0x180372bda`: `SymFromName() could not find the location of %s. Check your symbol path.\n`

## pseudocode

```c

```
