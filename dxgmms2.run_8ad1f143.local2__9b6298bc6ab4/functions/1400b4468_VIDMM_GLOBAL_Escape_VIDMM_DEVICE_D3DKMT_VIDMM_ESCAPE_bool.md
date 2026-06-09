# VIDMM_GLOBAL::Escape(VIDMM_DEVICE *,_D3DKMT_VIDMM_ESCAPE *,bool)

- ea: `0x1400b4468`
- end: `0x1400b4ada`
- name: `?Escape@VIDMM_GLOBAL@@QEAAJPEAVVIDMM_DEVICE@@PEAU_D3DKMT_VIDMM_ESCAPE@@_N@Z`
- size: `1650`
- prototype: `__int64 __fastcall(VIDMM_GLOBAL *this, struct VIDMM_DEVICE *, struct _D3DKMT_VIDMM_ESCAPE *, char)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140046e00`

## callees

- `0x1400045ec`
- `0x140012bf0`
- `0x14002ed1c`
- `0x14002f510`
- `0x14003e948`
- `0x140058ac0`
- `0x1400b4468`
- `0x1400b7998`
- `0x1400ba7f8`
- `0x1400c064c`
- `0x1400c241c`
- `0x1400dfe1c`
- `0x1400e284c`
- `0x1400e9900`
- `0x1400fb150`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x1400b4516`
- `ntoskrnl!KeSetEvent` at `0x1400b4516`
- `watchdog!WdLogSingleEntry0` at `0x1400b4555`
- `watchdog!WdLogSingleEntry0` at `0x1400b4707`
- `watchdog!WdLogSingleEntry0` at `0x1400b484e`
- `watchdog!WdLogSingleEntry0` at `0x1400b4953`
- `watchdog!WdLogSingleEntry0` at `0x1400b4a6f`
- `watchdog!WdLogSingleEntry0` at `0x1400b4555`
- `watchdog!WdLogSingleEntry0` at `0x1400b4707`
- `watchdog!WdLogSingleEntry0` at `0x1400b484e`
- `watchdog!WdLogSingleEntry0` at `0x1400b4953`
- `watchdog!WdLogSingleEntry0` at `0x1400b4a6f`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400b45fb`

## string_xrefs

- `0x1400b456a`: `Application should no longer use the SETFAULT command. Instead, use the new process/adapter verifier config`

## pseudocode

```c

```
