# DTC_XaClose(char *,int,long)

- ea: `0x18002dd50`
- end: `0x18002deb3`
- name: `?DTC_XaClose@@YAHPEADHJ@Z`
- size: `355`
- prototype: `__int64 __fastcall(char *, int, int)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180003cf0`
- `0x18002dd50`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ddfc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ddfc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ddd1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ddd1`

## string_xrefs

- `0x18002dd86`: `com\complus\dtc\dtc\msdtcprx\src\dtcxamap.cpp`
- `0x18002de78`: `com\complus\dtc\dtc\msdtcprx\src\dtcxamap.cpp`
- `0x18002dd70`: `Entering DTC_XaClose, rmid=0x%x, flags=0x%x`
- `0x18002dd7b`: `DTC_XaClose`
- `0x18002de6c`: `Exiting DTC_XaClose, error=%d`

## pseudocode

```c

```
