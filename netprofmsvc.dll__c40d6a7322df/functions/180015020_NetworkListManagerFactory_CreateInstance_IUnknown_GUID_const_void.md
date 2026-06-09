# NetworkListManagerFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180015020`
- end: `0x1800151cf`
- name: `?CreateInstance@NetworkListManagerFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `431`
- prototype: `int(NetworkListManagerFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callees

- `0x180009990`
- `0x180015020`
- `0x180015628`
- `0x180015d50`
- `0x180035f00`
- `0x1800958d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015068`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015068`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800150b5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001519a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800150b5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001519a`

## string_xrefs

- `0x1800150f7`: `onecore\net\netprofiles\service\src\host\dll\factory.cpp`
- `0x180015138`: `onecore\net\netprofiles\service\src\host\dll\factory.cpp`
- `0x18001517b`: `onecore\net\netprofiles\service\src\host\lib\profmani.cpp`

## pseudocode

```c

```
