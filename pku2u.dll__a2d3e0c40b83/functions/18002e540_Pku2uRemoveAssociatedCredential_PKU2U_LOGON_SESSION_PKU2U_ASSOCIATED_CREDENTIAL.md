# Pku2uRemoveAssociatedCredential(_PKU2U_LOGON_SESSION *,_PKU2U_ASSOCIATED_CREDENTIAL *)

- ea: `0x18002e540`
- end: `0x18002e596`
- name: `?Pku2uRemoveAssociatedCredential@@YAXPEAU_PKU2U_LOGON_SESSION@@PEAU_PKU2U_ASSOCIATED_CREDENTIAL@@@Z`
- size: `86`
- prototype: `void(struct _PKU2U_LOGON_SESSION *, struct _PKU2U_ASSOCIATED_CREDENTIAL *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18002cc00`
- `0x18002cce4`

## callees

- `0x180017820`
- `0x18002e540`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18002e588`
- `ntdll!RtlEnterCriticalSection` at `0x18002e554`
- `ntdll!RtlEnterCriticalSection` at `0x18002e554`

## pseudocode

```c

```
