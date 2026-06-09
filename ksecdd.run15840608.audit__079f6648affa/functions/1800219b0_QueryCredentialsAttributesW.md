# QueryCredentialsAttributesW

- ea: `0x1800219b0`
- end: `0x1800219bf`
- name: `QueryCredentialsAttributesW`
- size: `15`
- prototype: `SECURITY_STATUS __stdcall(PCredHandle phCredential, unsigned int ulAttribute, void *pBuffer)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000b048`

## pseudocode

```c
SECURITY_STATUS __stdcall QueryCredentialsAttributesW(
        PCredHandle phCredential,
        unsigned int ulAttribute,
        void *pBuffer)
{
  return (unsigned int)SspipSslQueryCredentialsAttributes(phCredential, ulAttribute, pBuffer).Pointer;
}

```

## disassembly

```asm
0x1800219b0  sub     rsp, 28h
0x1800219b4  call    SspipSslQueryCredentialsAttributes
0x1800219b9  add     rsp, 28h
0x1800219bd  retn
```
