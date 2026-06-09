# CtfImeDispatchDefImeMessage

- ea: `0x18002b690`
- end: `0x18002ba45`
- name: `CtfImeDispatchDefImeMessage`
- size: `949`
- prototype: `__int64 __fastcall(HWND)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callees

- `0x18002b690`
- `0x18004527c`
- `0x18010a010`

## import_xrefs

- `ntdll!RtlDllShutdownInProgress` at `0x18002b92c`
- `ntdll!RtlDllShutdownInProgress` at `0x18002b92c`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18002b97d`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18002b97d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002b732`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002b823`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002b86b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002b949`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002b732`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002b823`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002b86b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002b949`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002b962`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002b962`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ba0f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ba0f`
- `USER32!SendMessageW` at `0x18002b8e9`
- `USER32!SendMessageW` at `0x18002b8e9`
- `USER32!SendMessageW` at `0x18002b91d`
- `USER32!IsWindow` at `0x18002b8f5`
- `USER32!IsWindow` at `0x18002b8f5`
- `USER32!GetKeyboardLayout` at `0x18002b802`
- `USER32!GetKeyboardLayout` at `0x18002b802`
- `IMM32!ImmLockIMC` at `0x18002b891`
- `IMM32!ImmLockIMC` at `0x18002b891`
- `IMM32!ImmGetContext` at `0x18002b87c`
- `IMM32!ImmGetContext` at `0x18002ba2c`
- `IMM32!ImmGetContext` at `0x18002b87c`
- `IMM32!ImmGetContext` at `0x18002ba2c`
- `IMM32!ImmUnlockIMC` at `0x18002b8c8`
- `IMM32!ImmUnlockIMC` at `0x18002b8c8`

## pseudocode

```c

```
