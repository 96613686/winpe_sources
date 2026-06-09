# Windows::Compat::Inventory::Service::PnpListener::Uninitialize(void)

- ea: `0x1800c2d48`
- end: `0x1800c2da2`
- name: `?Uninitialize@PnpListener@Service@Inventory@Compat@Windows@@AEAAXXZ`
- size: `90`
- prototype: `void __fastcall(Windows::Compat::Inventory::Service::PnpListener *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800c1260`
- `0x1800c22f8`
- `0x1800c2d30`

## callees

- `0x1800108d4`
- `0x180011334`
- `0x1800c2d48`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800c2d55`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800c2d55`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x1800c2d68`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x1800c2d68`

## string_xrefs

- `0x1800c2d90`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c

```
