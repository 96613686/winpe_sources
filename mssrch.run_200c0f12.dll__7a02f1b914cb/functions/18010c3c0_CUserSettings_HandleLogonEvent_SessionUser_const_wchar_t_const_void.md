# CUserSettings::HandleLogonEvent(SessionUser const &,wchar_t const *,void *)

- ea: `0x18010c3c0`
- end: `0x18010c8c4`
- name: `?HandleLogonEvent@CUserSettings@@QEAAJAEBUSessionUser@@PEB_WPEAX@Z`
- size: `1284`
- prototype: `int(CUserSettings *__hidden this, const struct SessionUser *, const wchar_t *, void *)`
- caller_count: `1`
- callee_count: `32`
- tags: `registry_config`

## callers

- `0x1800f7dc8`

## callees

- `0x18000edc4`
- `0x18000f880`
- `0x180012120`
- `0x180012318`
- `0x18001b470`
- `0x18005cbf4`
- `0x1800723ac`
- `0x180079d34`
- `0x1800c071c`
- `0x1800cae14`
- `0x1800e2374`
- `0x180102440`
- `0x1801092f0`
- `0x18010acd0`
- `0x18010c3c0`
- `0x18010c8cc`
- `0x18010ca34`
- `0x18010cadc`
- `0x18010caf8`
- `0x180112b54`
- `0x180117adc`
- `0x18011beec`
- `0x180121b0c`
- `0x1801244c0`
- `0x180124d80`
- `0x180182e48`
- `0x18019b768`
- `0x18019b968`
- `0x18019cb2c`
- `0x18019cf84`
- `0x18019d164`
- `0x180241010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18010c78a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18010c85a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18010c8ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18010c78a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18010c85a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18010c8ab`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18010c53b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18010c53b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18010c83a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18010c83a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010c80b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010c80b`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18010c7fc`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18010c7fc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18010c422`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18010c422`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18010c406`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18010c732`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18010c406`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18010c732`

## pseudocode

```c

```
