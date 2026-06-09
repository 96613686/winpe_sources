# OWEDestroyCrypto(OWE_CRYPTO *)

- ea: `0x140021034`
- end: `0x1400210c0`
- name: `?OWEDestroyCrypto@@YAXPEAUOWE_CRYPTO@@@Z`
- size: `140`
- prototype: `void __fastcall(struct OWE_CRYPTO *)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140020fbc`
- `0x14003a6b8`

## callees

- `0x140021034`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140021058`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140021058`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021069`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021069`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x140021088`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x140021088`
- `ksecdd!BCryptDestroyKey` at `0x1400210a5`
- `ksecdd!BCryptDestroyKey` at `0x1400210a5`

## pseudocode

```c

```
