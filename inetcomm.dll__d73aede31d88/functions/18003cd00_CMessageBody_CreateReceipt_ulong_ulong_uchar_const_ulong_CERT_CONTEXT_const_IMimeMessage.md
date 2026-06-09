# CMessageBody::CreateReceipt(ulong,ulong,uchar const *,ulong,_CERT_CONTEXT const * *,IMimeMessage * *)

- ea: `0x18003cd00`
- end: `0x18003d41c`
- name: `?CreateReceipt@CMessageBody@@UEAAJKKPEBEKPEAPEBU_CERT_CONTEXT@@PEAPEAUIMimeMessage@@@Z`
- size: `1820`
- prototype: `int(CMessageBody *__hidden this, unsigned int, unsigned int, const unsigned __int8 *, unsigned int, const struct _CERT_CONTEXT **, struct IMimeMessage **)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180002098`
- `0x180002cf0`
- `0x180021140`
- `0x18003cd00`
- `0x180040c08`
- `0x1800cca00`
- `0x1800cd010`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x18003ceea`
- `KERNEL32!lstrcmpiW` at `0x18003ceea`
- `KERNEL32!WideCharToMultiByte` at `0x18003d159`
- `KERNEL32!WideCharToMultiByte` at `0x18003d159`
- `CRYPT32!CryptDecodeObjectEx` at `0x18003ce30`
- `CRYPT32!CryptDecodeObjectEx` at `0x18003ce9d`
- `CRYPT32!CryptDecodeObjectEx` at `0x18003d0fc`
- `CRYPT32!CryptDecodeObjectEx` at `0x18003ce30`
- `CRYPT32!CryptDecodeObjectEx` at `0x18003ce9d`
- `CRYPT32!CryptDecodeObjectEx` at `0x18003d0fc`
- `CRYPT32!CryptEncodeObjectEx` at `0x18003d272`
- `CRYPT32!CryptEncodeObjectEx` at `0x18003d272`

## pseudocode

```c

```
