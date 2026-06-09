# KerbCredIsoIum::ComputeTgsChecksum(KERB_KDC_REQUEST_BODY *,_KERB_ENCRYPTION_KEY *,ulong,KERB_CHECKSUM *)

- ea: `0x180052c40`
- end: `0x180052e44`
- name: `?ComputeTgsChecksum@KerbCredIsoIum@@UEAAJPEAUKERB_KDC_REQUEST_BODY@@PEAU_KERB_ENCRYPTION_KEY@@KPEAUKERB_CHECKSUM@@@Z`
- size: `516`
- prototype: `__int64 __fastcall(KerbCredIsoIum *__hidden this, struct KERB_KDC_REQUEST_BODY *, struct _KERB_ENCRYPTION_KEY *, unsigned int, struct KERB_CHECKSUM *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18002af2c`
- `0x18002b9fc`
- `0x180052c40`
- `0x1800744cf`
- `0x18008b70c`

## import_xrefs

- `KerbClientShared!KerbClientAlloc` at `0x180052dac`
- `KerbClientShared!KerbClientAlloc` at `0x180052dac`
- `KerbClientShared!KerbClientPackAsn1Buffer` at `0x180052c81`
- `KerbClientShared!KerbClientPackAsn1Buffer` at `0x180052c81`
- `KerbClientShared!KerbClientUnpackAsn1BufferVoid` at `0x180052d80`
- `KerbClientShared!KerbClientUnpackAsn1BufferVoid` at `0x180052d80`
- `KerbClientShared!KerbClientFree` at `0x180052e21`
- `KerbClientShared!KerbClientFree` at `0x180052e21`
- `RPCRT4!NdrClientCall3` at `0x180052cf3`
- `RPCRT4!NdrClientCall3` at `0x180052cf3`
- `RPCRT4!I_RpcMapWin32Status` at `0x180052d0b`
- `RPCRT4!I_RpcMapWin32Status` at `0x180052d0b`
- `RPCRT4!RpcExceptionFilter` at `0x1800f2caa`
- `RPCRT4!RpcExceptionFilter` at `0x1800f2caa`

## string_xrefs

- `0x180052c89`: `KerbCredIsoIum::ComputeTgsChecksum`
- `0x180052d1b`: `KerbCredIsoIum::ComputeTgsChecksum`
- `0x180052d44`: `KerbCredIsoIum::ComputeTgsChecksum`
- `0x180052dfb`: `%hs: ComputeTgsChecksumFailed. %#x\n`

## pseudocode

```c

```
