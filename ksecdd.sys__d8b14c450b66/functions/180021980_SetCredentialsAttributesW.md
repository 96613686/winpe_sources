# SetCredentialsAttributesW

- ea: `0x180021980`
- end: `0x18002199e`
- name: `SetCredentialsAttributesW`
- size: `30`
- prototype: `SECURITY_STATUS __stdcall(PCredHandle phCredential, unsigned int ulAttribute, void *pBuffer, unsigned int cbBuffer)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180003574`
- `0x18000b184`
- `0x180021980`

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
0x180021980  sub     rsp, 28h
0x180021984  cmp     edx, 60h ; '`'
0x180021987  jz      short loc_180021990
0x180021989  call    SspipSslSetCredentialsAttributesEx
0x18002198e  jmp     short loc_180021998
0x180021990  mov     rdx, r8
0x180021993  call    SspipSslSetCredentialsAttributes
0x180021998  add     rsp, 28h
0x18002199c  retn
```
