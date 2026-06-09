# FreeCredentialsHandle

- ea: `0x180027a10`
- end: `0x180027a1f`
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
0x180027a10  sub     rsp, 28h
0x180027a14  call    SspipFreeCredentialsHandle
0x180027a19  add     rsp, 28h
0x180027a1d  retn
```
