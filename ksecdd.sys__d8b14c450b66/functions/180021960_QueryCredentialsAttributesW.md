# QueryCredentialsAttributesW

- ea: `0x180021960`
- end: `0x18002196f`
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
0x180021960  sub     rsp, 28h
0x180021964  call    SspipSslQueryCredentialsAttributes
0x180021969  add     rsp, 28h
0x18002196d  retn
```
