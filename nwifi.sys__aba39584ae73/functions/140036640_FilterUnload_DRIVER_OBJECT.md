# FilterUnload(_DRIVER_OBJECT *)

- ea: `0x140036640`
- end: `0x1400366f8`
- name: `?FilterUnload@@YAXPEAU_DRIVER_OBJECT@@@Z`
- size: `184`
- prototype: `void __fastcall(struct _DRIVER_OBJECT *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1400be078`

## callees

- `0x140036640`
- `0x140038310`
- `0x1400bc3d0`

## import_xrefs

- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x1400366ae`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x1400366ae`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x1400366d1`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x1400366d1`
- `ntoskrnl!EtwUnregister` at `0x14003664b`
- `ntoskrnl!EtwUnregister` at `0x14003664b`
- `NDIS!NdisFDeregisterFilterDriver` at `0x14003666e`
- `NDIS!NdisFDeregisterFilterDriver` at `0x14003666e`

## pseudocode

```c

```
