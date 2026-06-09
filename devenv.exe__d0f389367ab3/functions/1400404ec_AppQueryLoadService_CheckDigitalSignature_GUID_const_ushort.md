# AppQueryLoadService::CheckDigitalSignature(_GUID const &,ushort * *)

- ea: `0x1400404ec`
- end: `0x1400407c6`
- name: `?CheckDigitalSignature@AppQueryLoadService@@AEAAHAEBU_GUID@@PEAPEAG@Z`
- size: `730`
- prototype: `__int64 __fastcall(AppQueryLoadService *__hidden this, const struct _GUID *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task`

## callers

- `0x140004ce8`

## callees

- `0x140001020`
- `0x140004a98`
- `0x140033ab0`
- `0x140038c5c`
- `0x140038d60`
- `0x14003f694`
- `0x14003fae8`
- `0x14003fe5c`
- `0x1400404ec`
- `0x1400407c8`

## import_xrefs

- `ADVAPI32!CryptDestroyHash` at `0x1400406e2`
- `ADVAPI32!CryptDestroyHash` at `0x140040794`
- `ADVAPI32!CryptDestroyHash` at `0x1400406e2`
- `ADVAPI32!CryptDestroyHash` at `0x140040794`
- `OLEAUT32!__imp_SysFreeString` at `0x1400406d3`
- `OLEAUT32!__imp_SysFreeString` at `0x140040711`
- `OLEAUT32!__imp_SysFreeString` at `0x14004071a`
- `OLEAUT32!__imp_SysFreeString` at `0x140040781`
- `OLEAUT32!__imp_SysFreeString` at `0x1400406d3`
- `OLEAUT32!__imp_SysFreeString` at `0x140040711`
- `OLEAUT32!__imp_SysFreeString` at `0x14004071a`
- `OLEAUT32!__imp_SysFreeString` at `0x140040781`
- `OLEAUT32!__imp_SysStringByteLen` at `0x1400405b8`
- `OLEAUT32!__imp_SysStringByteLen` at `0x1400405b8`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x1400405c3`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x1400405c3`

## pseudocode

```c

```
