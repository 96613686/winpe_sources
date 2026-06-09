# HNS::Service::Core::NsiNotificationManager<_NET_LUID_LH,NET_LUID_Comparator,HNS::Service::Core::NeighborNotificationManager>::SubscribeEvents(void)

- ea: `0x1800e7778`
- end: `0x1800e790e`
- name: `?SubscribeEvents@?$NsiNotificationManager@T_NET_LUID_LH@@UNET_LUID_Comparator@@VNeighborNotificationManager@Core@Service@HNS@@@Core@Service@HNS@@IEAAXXZ`
- size: `406`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800e5580`
- `0x1800e7140`
- `0x1800e7560`

## callees

- `0x1800663fc`
- `0x18006ea40`
- `0x1800e7040`
- `0x1800e7778`
- `0x1802b7010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800e77ae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800e77ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e779b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e779b`
- `WINNSI!NsiConnectToServer` at `0x1800e7786`
- `WINNSI!NsiConnectToServer` at `0x1800e7786`
- `WINNSI!NsiDisconnectFromServer` at `0x1800e77a6`
- `WINNSI!NsiDisconnectFromServer` at `0x1800e77a6`

## string_xrefs

- `0x1800e78fc`: `onecore\vm\dv\net\hns\service\core\NsiNotificationManager.h`

## pseudocode

```c

```
