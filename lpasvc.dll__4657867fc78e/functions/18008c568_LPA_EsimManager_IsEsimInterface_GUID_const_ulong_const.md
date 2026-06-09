# LPA::EsimManager::IsEsimInterface(_GUID const &,ulong const &)

- ea: `0x18008c568`
- end: `0x18008c704`
- name: `?IsEsimInterface@EsimManager@LPA@@AEAA_NAEBU_GUID@@AEBK@Z`
- size: `412`
- prototype: `bool __fastcall(LPA::EsimManager *__hidden this, const struct _GUID *, const unsigned int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18008fb10`
- `0x180090d80`

## callees

- `0x1800014d8`
- `0x180003c3c`
- `0x180089f00`
- `0x18008c568`

## import_xrefs

- `wwapi!WwanQueryInterfaceEx` at `0x18008c5c4`
- `wwapi!WwanQueryInterfaceEx` at `0x18008c5c4`
- `wwapi!WwanFreeMemory` at `0x18008c67b`
- `wwapi!WwanFreeMemory` at `0x18008c67b`

## string_xrefs

- `0x18008c609`: `LpaServiceEsimManager`
- `0x18008c69b`: `LpaServiceEsimManager`

## pseudocode

```c

```
