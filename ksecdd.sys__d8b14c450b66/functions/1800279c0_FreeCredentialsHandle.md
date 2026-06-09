# FreeCredentialsHandle

- ea: `0x1800279c0`
- end: `0x1800279cf`
- name: `FreeCredentialsHandle`
- size: `15`
- prototype: `SECURITY_STATUS __stdcall(PCredHandle phCredential)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003a54`

## pseudocode

```c
SECURITY_STATUS __stdcall FreeCredentialsHandle(PCredHandle phCredential)
{
  return SspipFreeCredentialsHandle(phCredential);
}

```

## disassembly

```asm
0x1800279c0  sub     rsp, 28h
0x1800279c4  call    SspipFreeCredentialsHandle
0x1800279c9  add     rsp, 28h
0x1800279cd  retn
```
