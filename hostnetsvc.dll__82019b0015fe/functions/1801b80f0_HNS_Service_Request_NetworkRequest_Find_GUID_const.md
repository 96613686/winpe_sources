# HNS::Service::Request::NetworkRequest::Find(_GUID const &)

- ea: `0x1801b80f0`
- end: `0x1801b841a`
- name: `?Find@NetworkRequest@Request@Service@HNS@@UEAA?AV?$shared_ptr@VBaseNetwork@Network@Service@HNS@@@std@@AEBU_GUID@@@Z`
- size: `810`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task`

## callers

- `0x1801b8420`

## callees

- `0x180001d38`
- `0x18005ecb0`
- `0x18005ffa0`
- `0x180061dc4`
- `0x1800666b4`
- `0x18006ea40`
- `0x180071af4`
- `0x180075aac`
- `0x18007c420`
- `0x1800805c4`
- `0x1800c0300`
- `0x1801b80f0`
- `0x1802b7010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1801b83c7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1801b83c7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1801b81d0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1801b81d0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801b8299`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801b83b8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801b8299`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801b83b8`

## string_xrefs

- `0x1801b83f0`: `onecore\internal\sdk\inc\wil\opensource/wil/stl.h`
- `0x1801b8122`: `HNS::Service::Core::EntityManager<class std::shared_ptr<class HNS::Service::Network::BaseNetwork> >::FindNoThrow`
- `0x1801b81e3`: `HNS::Service::Core::EntityManager<class std::shared_ptr<class HNS::Service::Network::BaseNetwork> >::FindNoThrow`
- `0x1801b830b`: `HNS::Service::Request::NetworkRequest::Find`
- `0x1801b8408`: `onecore\vm\dv\net\hns\service\request\networkrequest.cpp`

## pseudocode

```c

```
