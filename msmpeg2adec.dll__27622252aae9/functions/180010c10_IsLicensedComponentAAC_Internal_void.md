# IsLicensedComponentAAC_Internal(void)

- ea: `0x180010c10`
- end: `0x180010c4a`
- name: `?IsLicensedComponentAAC_Internal@@YAHXZ`
- size: `58`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000d2f0`
- `0x1800168e0`
- `0x180018b70`

## callees

- `0x180010b80`
- `0x180010c10`
- `0x180021a20`
- `0x180024b70`

## pseudocode

```c
__int64 IsLicensedComponentAAC_Internal(void)
{
  unsigned int v0; // ebx

  if ( (unsigned int)WarbirdRuntime::CEncryption<6,WarbirdCrypto::CCipherFeistel64<8,152,173,121,15,82,70,191,11,106,45,152,3,61,67,9,12,123,61,110,5,165,244,41,28,218,32,125,0,14,70,72,18,148,249,32,9,134,85,67>,WarbirdCrypto::CHashFunctionSCP<1,2,3,6586405832520086161>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_7,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_7>::Decrypt() )
    return 0;
  v0 = IsLicensedComponentAAC();
  if ( (unsigned int)WarbirdRuntime::CEncryption<6,WarbirdCrypto::CCipherFeistel64<8,152,173,121,15,82,70,191,11,106,45,152,3,61,67,9,12,123,61,110,5,165,244,41,28,218,32,125,0,14,70,72,18,148,249,32,9,134,85,67>,WarbirdCrypto::CHashFunctionSCP<1,2,3,6586405832520086161>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_7,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_7>::Encrypt() )
    return 0;
  return v0;
}

```

## disassembly

```asm
0x180010c10  sub     rsp, 28h
0x180010c14  call    ?Decrypt@?$CEncryption@$05V?$CCipherFeistel64@$07$0JI@$0KN@$0HJ@$0P@$0FC@$0EG@$0LP@$0L@$0GK@$0CN@$0JI@$02$0DN@$0ED@$08$0M@$0HL@$0DN@$0GO@$04$0KF@$0PE@$0CJ@$0BM@$0NK@$0CA@$0HN@$0A@$0O@$0EG@$0EI@$0BC@$0JE@$0PJ@$0CA@$08$0IG@$0FF@$0ED@@WarbirdCrypto@@V?$CHashFunctionSCP@$00$01$02$0FLGHJNDFFJOLLCJB@@2@UENCRYPTED_SEGMENT_DATA_CONST_7@WarbirdRuntime@@UENCRYPTED_SEGMENT_DATA_READ_WRITE_7@5@@WarbirdRuntime@@SAJPEAUENCRYPTED_SEGMENT_DATA_CONST_7@2@PEAUENCRYPTED_SEGMENT_DATA_READ_WRITE_7@2@@Z; WarbirdRuntime::CEncryption<6,WarbirdCrypto::CCipherFeistel64<8,152,173,121,15,82,70,191,11,106,45,152,3,61,67,9,12,123,61,110,5,165,244,41,28,218,32,125,0,14,70,72,18,148,249,32,9,134,85,67>,WarbirdCrypto::CHashFunctionSCP<1,2,3,6586405832520086161>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_7,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_7>::Decrypt(WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_7 *,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_7 *)
0x180010c19  test    eax, eax
0x180010c1b  jnz     short loc_180010C42
0x180010c1d  mov     [rsp+28h+var_8], rbx
0x180010c22  call    ?IsLicensedComponentAAC@@YAHXZ; IsLicensedComponentAAC(void)
0x180010c27  mov     ebx, eax
0x180010c29  call    ?Encrypt@?$CEncryption@$05V?$CCipherFeistel64@$07$0JI@$0KN@$0HJ@$0P@$0FC@$0EG@$0LP@$0L@$0GK@$0CN@$0JI@$02$0DN@$0ED@$08$0M@$0HL@$0DN@$0GO@$04$0KF@$0PE@$0CJ@$0BM@$0NK@$0CA@$0HN@$0A@$0O@$0EG@$0EI@$0BC@$0JE@$0PJ@$0CA@$08$0IG@$0FF@$0ED@@WarbirdCrypto@@V?$CHashFunctionSCP@$00$01$02$0FLGHJNDFFJOLLCJB@@2@UENCRYPTED_SEGMENT_DATA_CONST_7@WarbirdRuntime@@UENCRYPTED_SEGMENT_DATA_READ_WRITE_7@5@@WarbirdRuntime@@SAJPEAUENCRYPTED_SEGMENT_DATA_CONST_7@2@PEAUENCRYPTED_SEGMENT_DATA_READ_WRITE_7@2@@Z; WarbirdRuntime::CEncryption<6,WarbirdCrypto::CCipherFeistel64<8,152,173,121,15,82,70,191,11,106,45,152,3,61,67,9,12,123,61,110,5,165,244,41,28,218,32,125,0,14,70,72,18,148,249,32,9,134,85,67>,WarbirdCrypto::CHashFunctionSCP<1,2,3,6586405832520086161>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_7,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_7>::Encrypt(WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_7 *,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_7 *)
0x180010c2e  xor     ecx, ecx
0x180010c30  test    eax, eax
0x180010c32  cmovnz  ebx, ecx
0x180010c35  mov     eax, ebx
0x180010c37  mov     rbx, [rsp+28h+var_8]
0x180010c3c  add     rsp, 28h
0x180010c40  retn
0x180010c42  xor     eax, eax
0x180010c44  add     rsp, 28h
0x180010c48  retn
```
