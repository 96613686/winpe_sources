# HttpsRequest::Initialize(ushort const *,char *,unsigned __int64,ulong)

- ea: `0x18039cbdc`
- end: `0x18039d065`
- name: `?Initialize@HttpsRequest@@AEAAJPEBGPEAD_KK@Z`
- size: `1161`
- prototype: `int(HttpsRequest *__hidden this, const unsigned __int16 *, char *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18039c5a0`

## callees

- `0x18002a374`
- `0x1800829d4`
- `0x1800dafe4`
- `0x1800e9b1c`
- `0x18012962c`
- `0x18039cbdc`
- `0x180688f26`
- `0x18068c010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18039cc1b`
- `KERNEL32!GetLastError` at `0x18039ccb0`
- `KERNEL32!GetLastError` at `0x18039cdb1`
- `KERNEL32!GetLastError` at `0x18039ce2d`
- `KERNEL32!GetLastError` at `0x18039cea1`
- `KERNEL32!GetLastError` at `0x18039cf12`
- `KERNEL32!GetLastError` at `0x18039cf94`
- `KERNEL32!GetLastError` at `0x18039cc1b`
- `KERNEL32!GetLastError` at `0x18039ccb0`
- `KERNEL32!GetLastError` at `0x18039cdb1`
- `KERNEL32!GetLastError` at `0x18039ce2d`
- `KERNEL32!GetLastError` at `0x18039cea1`
- `KERNEL32!GetLastError` at `0x18039cf12`
- `KERNEL32!GetLastError` at `0x18039cf94`
- `KERNEL32!CreateEventW` at `0x18039cc06`
- `KERNEL32!CreateEventW` at `0x18039cca1`
- `KERNEL32!CreateEventW` at `0x18039cc06`
- `KERNEL32!CreateEventW` at `0x18039cca1`
- `WINHTTP!WinHttpSetStatusCallback` at `0x18039cda5`
- `WINHTTP!WinHttpSetStatusCallback` at `0x18039cda5`
- `WINHTTP!WinHttpSendRequest` at `0x18039cf8a`
- `WINHTTP!WinHttpSendRequest` at `0x18039cf8a`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x18039cf08`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x18039cf08`
- `WINHTTP!WinHttpSetTimeouts` at `0x18039ce23`
- `WINHTTP!WinHttpSetTimeouts` at `0x18039ce23`
- `WINHTTP!WinHttpSetOption` at `0x18039ce97`
- `WINHTTP!WinHttpSetOption` at `0x18039ce97`

## string_xrefs

- `0x18039ccfb`: `CreateEvent(m_hRequestClosedEvent) failed!`
- `0x18039cc66`: `CreateEvent(m_hRequestCompletedEvent) failed!`

## pseudocode

```c

```
