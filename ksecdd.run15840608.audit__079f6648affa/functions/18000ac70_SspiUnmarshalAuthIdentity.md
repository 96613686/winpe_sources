# SspiUnmarshalAuthIdentity

- ea: `0x18000ac70`
- end: `0x18000ac7f`
- name: `SspiUnmarshalAuthIdentity`
- size: `15`
- prototype: `SECURITY_STATUS __stdcall(unsigned int AuthIdentityLength, char *AuthIdentityByteArray, PSEC_WINNT_AUTH_IDENTITY_OPAQUE *ppAuthIdentity)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180006048`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
SECURITY_STATUS __stdcall SspiUnmarshalAuthIdentity(
        unsigned int AuthIdentityLength,
        char *AuthIdentityByteArray,
        PSEC_WINNT_AUTH_IDENTITY_OPAQUE *ppAuthIdentity)
{
  unsigned int *v3; // r9

  return SspiUnmarshalAuthIdentityInternal(*(size_t *)&AuthIdentityLength, AuthIdentityByteArray, ppAuthIdentity, v3);
}

```

## disassembly

```asm
0x18000ac70  sub     rsp, 28h
0x18000ac74  call    ?SspiUnmarshalAuthIdentityInternal@@YAJKPEADPEAPEAXPEAK@Z; SspiUnmarshalAuthIdentityInternal(ulong,char *,void * *,ulong *)
0x18000ac79  add     rsp, 28h
0x18000ac7d  retn
```
