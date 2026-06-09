# VIDMM_GLOBAL::Escape(VIDMM_DEVICE *,_D3DKMT_VIDMM_ESCAPE *,bool)

- ea: `0x1400b7da4`
- end: `0x1400b840f`
- name: `?Escape@VIDMM_GLOBAL@@QEAAJPEAVVIDMM_DEVICE@@PEAU_D3DKMT_VIDMM_ESCAPE@@_N@Z`
- size: `1643`
- prototype: `__int64 __fastcall(VIDMM_GLOBAL *this, struct VIDMM_DEVICE *, struct _D3DKMT_VIDMM_ESCAPE *, char)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140047110`

## callees

- `0x140004268`
- `0x140012690`
- `0x14002bddc`
- `0x14002c5d0`
- `0x14003d308`
- `0x140059380`
- `0x1400b7da4`
- `0x1400bb380`
- `0x1400be298`
- `0x1400c473c`
- `0x1400c65c8`
- `0x1400e827c`
- `0x1400eac74`
- `0x1400ff470`
- `0x140104d50`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x1400b7e52`
- `ntoskrnl!KeSetEvent` at `0x1400b7e52`
- `watchdog!WdLogSingleEntry0` at `0x1400b7e91`
- `watchdog!WdLogSingleEntry0` at `0x1400b8043`
- `watchdog!WdLogSingleEntry0` at `0x1400b818a`
- `watchdog!WdLogSingleEntry0` at `0x1400b828f`
- `watchdog!WdLogSingleEntry0` at `0x1400b83a4`
- `watchdog!WdLogSingleEntry0` at `0x1400b7e91`
- `watchdog!WdLogSingleEntry0` at `0x1400b8043`
- `watchdog!WdLogSingleEntry0` at `0x1400b818a`
- `watchdog!WdLogSingleEntry0` at `0x1400b828f`
- `watchdog!WdLogSingleEntry0` at `0x1400b83a4`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400b7f37`

## string_xrefs

- `0x1400b7ea6`: `Application should no longer use the SETFAULT command. Instead, use the new process/adapter verifier config`

## pseudocode

```c

```
