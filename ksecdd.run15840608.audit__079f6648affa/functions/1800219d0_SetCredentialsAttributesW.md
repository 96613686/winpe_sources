# SetCredentialsAttributesW

- ea: `0x1800219d0`
- end: `0x1800219ee`
- name: `SetCredentialsAttributesW`
- size: `30`
- prototype: `SECURITY_STATUS __stdcall(PCredHandle phCredential, unsigned int ulAttribute, void *pBuffer, unsigned int cbBuffer)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180003574`
- `0x18000b184`
- `0x1800219d0`

## pseudocode

```c
SECURITY_STATUS __stdcall SetCredentialsAttributesW(
        PCredHandle phCredential,
        unsigned int ulAttribute,
        void *pBuffer,
        unsigned int cbBuffer)
{
  if ( ulAttribute == 96 )
    return (unsigned int)SspipSslSetCredentialsAttributes(phCredential, (__int64)pBuffer).Pointer;
  else
    return (unsigned int)SspipSslSetCredentialsAttributesEx(phCredential, ulAttribute, (__int64)pBuffer).Pointer;
}

```

## disassembly

```asm
0x1800219d0  sub     rsp, 28h
0x1800219d4  cmp     edx, 60h ; '`'
0x1800219d7  jz      short loc_1800219E0
0x1800219d9  call    SspipSslSetCredentialsAttributesEx
0x1800219de  jmp     short loc_1800219E8
0x1800219e0  mov     rdx, r8
0x1800219e3  call    SspipSslSetCredentialsAttributes
0x1800219e8  add     rsp, 28h
0x1800219ec  retn
```
