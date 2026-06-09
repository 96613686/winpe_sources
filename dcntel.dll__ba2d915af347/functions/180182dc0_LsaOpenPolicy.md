# LsaOpenPolicy

- ea: `0x180182dc0`
- end: `0x180182fa6`
- name: `LsaOpenPolicy`
- size: `486`
- prototype: `NTSTATUS __stdcall(PLSA_UNICODE_STRING SystemName, PLSA_OBJECT_ATTRIBUTES ObjectAttributes, ACCESS_MASK DesiredAccess, PLSA_HANDLE PolicyHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180182cf0`

## callees

- `0x180182dc0`
- `0x180182fac`
- `0x18018301c`

## import_xrefs

- `RPCRT4!I_RpcExceptionFilter` at `0x18018ca13`
- `RPCRT4!I_RpcExceptionFilter` at `0x18018ca2f`
- `RPCRT4!I_RpcExceptionFilter` at `0x18018ca13`
- `RPCRT4!I_RpcExceptionFilter` at `0x18018ca2f`
- `RPCRT4!I_RpcMapWin32Status` at `0x180182ed7`
- `RPCRT4!I_RpcMapWin32Status` at `0x180182f53`
- `RPCRT4!I_RpcMapWin32Status` at `0x180182ed7`
- `RPCRT4!I_RpcMapWin32Status` at `0x180182f53`
- `RPCRT4!NdrClientCall3` at `0x180182eaf`
- `RPCRT4!NdrClientCall3` at `0x180182f3b`
- `RPCRT4!NdrClientCall3` at `0x180182eaf`
- `RPCRT4!NdrClientCall3` at `0x180182f3b`

## pseudocode

```c

```
