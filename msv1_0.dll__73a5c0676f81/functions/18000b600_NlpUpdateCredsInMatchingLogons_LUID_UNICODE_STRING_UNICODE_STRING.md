# NlpUpdateCredsInMatchingLogons(_LUID *,_UNICODE_STRING *,_UNICODE_STRING *)

- ea: `0x18000b600`
- end: `0x18000b87e`
- name: `?NlpUpdateCredsInMatchingLogons@@YAJPEAU_LUID@@PEAU_UNICODE_STRING@@1@Z`
- size: `638`
- prototype: `int(struct _LUID *, struct _UNICODE_STRING *, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x18000b3b0`

## callees

- `0x18000b600`
- `0x18000c000`
- `0x18000c660`
- `0x18002ee7c`
- `0x1800555f8`
- `0x18006d010`

## import_xrefs

- `ntdll!RtlInitString` at `0x18000b6b7`
- `ntdll!RtlInitString` at `0x18000b6b7`
- `LSASRV!LsaIFreeHeap` at `0x18000b7df`
- `LSASRV!LsaIFreeHeap` at `0x18000b7e9`
- `LSASRV!LsaIFreeHeap` at `0x18000b7df`
- `LSASRV!LsaIFreeHeap` at `0x18000b7e9`
- `LSASRV!LsaIGetNbAndDnsDomainNames` at `0x18000b64b`
- `LSASRV!LsaIGetNbAndDnsDomainNames` at `0x18000b64b`

## pseudocode

```c

```
