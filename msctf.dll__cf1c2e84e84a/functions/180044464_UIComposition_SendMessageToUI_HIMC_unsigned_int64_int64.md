# UIComposition::SendMessageToUI(HIMC__ *,unsigned __int64,__int64)

- ea: `0x180044464`
- end: `0x180044589`
- name: `?SendMessageToUI@UIComposition@@CAJPEAUHIMC__@@_K_J@Z`
- size: `293`
- prototype: `__int64 __fastcall(HIMC, WPARAM wParam, LPARAM lParam)`
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180015d30`
- `0x18001bbd0`
- `0x18001d630`

## callees

- `0x1800139a4`
- `0x18001a460`
- `0x180044464`
- `0x180045040`
- `0x1800454c0`

## import_xrefs

- `ntdll!RtlDllShutdownInProgress` at `0x1800444dc`
- `ntdll!RtlDllShutdownInProgress` at `0x1800444dc`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18004450e`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18004450e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004449f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004449f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800444f7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800444f7`
- `USER32!SendMessageW` at `0x1800444c1`
- `USER32!SendMessageW` at `0x180044579`
- `USER32!SendMessageW` at `0x1800444c1`
- `USER32!SendMessageW` at `0x180044579`
- `USER32!IsWindow` at `0x180044486`
- `USER32!IsWindow` at `0x180044486`
- `IMM32!ImmGetDefaultIMEWnd` at `0x18004447a`
- `IMM32!ImmGetDefaultIMEWnd` at `0x18004447a`

## pseudocode

```c

```
