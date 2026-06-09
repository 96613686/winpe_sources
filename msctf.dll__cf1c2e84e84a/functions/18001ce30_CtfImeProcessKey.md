# CtfImeProcessKey

- ea: `0x18001ce30`
- end: `0x18001d627`
- name: `CtfImeProcessKey`
- size: `2039`
- prototype: `__int64 __fastcall(HIMC, unsigned int, LPARAM lParam)`
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting`

## callees

- `0x180018640`
- `0x18001cc80`
- `0x18001ce30`
- `0x180020ce0`
- `0x18003d290`
- `0x180045040`
- `0x180045074`
- `0x18007db30`
- `0x18009eaea`
- `0x1800df708`
- `0x180106a60`
- `0x18010a010`

## import_xrefs

- `ntdll!RtlDllShutdownInProgress` at `0x18001d317`
- `ntdll!RtlDllShutdownInProgress` at `0x18001d317`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d1c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d1c0`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001d357`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001d357`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001ce71`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001ce71`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d33c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d33c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d579`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d579`
- `USER32!PostMessageW` at `0x18001d530`
- `USER32!PostMessageW` at `0x18001d530`
- `USER32!GetFocus` at `0x18001d4f4`
- `USER32!GetFocus` at `0x18001d4f4`
- `USER32!GetKeyboardLayout` at `0x18001d480`
- `USER32!GetKeyboardLayout` at `0x18001d480`
- `IMM32!ImmLockIMC` at `0x18001d0f9`
- `IMM32!ImmLockIMC` at `0x18001d0f9`
- `IMM32!ImmUnlockIMC` at `0x18001d134`
- `IMM32!ImmUnlockIMC` at `0x18001d134`
- `IMM32!ImmLockIMCC` at `0x18001d153`
- `IMM32!ImmLockIMCC` at `0x18001d153`
- `IMM32!ImmUnlockIMCC` at `0x18001d1b6`
- `IMM32!ImmUnlockIMCC` at `0x18001d1b6`

## pseudocode

```c

```
