# FilterUnload(_DRIVER_OBJECT *)

- ea: `0x140036420`
- end: `0x1400364d8`
- name: `?FilterUnload@@YAXPEAU_DRIVER_OBJECT@@@Z`
- size: `184`
- prototype: `void __fastcall(struct _DRIVER_OBJECT *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1400bb078`

## callees

- `0x140036420`
- `0x1400380f0`
- `0x1400b93d0`

## import_xrefs

- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x14003648e`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x14003648e`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x1400364b1`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x1400364b1`
- `ntoskrnl!EtwUnregister` at `0x14003642b`
- `ntoskrnl!EtwUnregister` at `0x14003642b`
- `NDIS!NdisFDeregisterFilterDriver` at `0x14003644e`
- `NDIS!NdisFDeregisterFilterDriver` at `0x14003644e`

## pseudocode

```c

```
