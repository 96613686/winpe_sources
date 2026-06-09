# KerbCredIsoIum::VerifyServiceTicket(KERB_TICKET *,_KERB_ENCRYPTION_KEY *,KERB_ADJUSTED_TIME *,KERB_ENCRYPTED_TICKET * *,long *)

- ea: `0x180053db0`
- end: `0x180053f9d`
- name: `?VerifyServiceTicket@KerbCredIsoIum@@UEAAJPEAUKERB_TICKET@@PEAU_KERB_ENCRYPTION_KEY@@PEAUKERB_ADJUSTED_TIME@@PEAPEAUKERB_ENCRYPTED_TICKET@@PEAJ@Z`
- size: `493`
- prototype: `__int64 __fastcall(KerbCredIsoIum *__hidden this, struct KERB_TICKET *, struct _KERB_ENCRYPTION_KEY *, struct KERB_ADJUSTED_TIME *, struct KERB_ENCRYPTED_TICKET **, int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x18002af2c`
- `0x180053db0`
- `0x18008b70c`

## import_xrefs

- `KerbClientShared!KerbClientPackAsn1Buffer` at `0x180053e05`
- `KerbClientShared!KerbClientPackAsn1Buffer` at `0x180053e05`
- `KerbClientShared!KerbClientUnpackAsn1BufferVoid` at `0x180053f2f`
- `KerbClientShared!KerbClientUnpackAsn1BufferVoid` at `0x180053f2f`
- `RPCRT4!NdrClientCall3` at `0x180053e86`
- `RPCRT4!NdrClientCall3` at `0x180053e86`
- `RPCRT4!I_RpcMapWin32Status` at `0x180053ea5`
- `RPCRT4!I_RpcMapWin32Status` at `0x180053ea5`
- `RPCRT4!RpcExceptionFilter` at `0x1800f2df4`
- `RPCRT4!RpcExceptionFilter` at `0x1800f2df4`

## string_xrefs

- `0x180053e0d`: `KerbCredIsoIum::VerifyServiceTicket`
- `0x180053eb5`: `KerbCredIsoIum::VerifyServiceTicket`
- `0x180053ee0`: `KerbCredIsoIum::VerifyServiceTicket`

## pseudocode

```c

```
