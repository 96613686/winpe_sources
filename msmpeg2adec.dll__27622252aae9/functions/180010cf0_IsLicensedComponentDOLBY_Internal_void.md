# IsLicensedComponentDOLBY_Internal(void)

- ea: `0x180010cf0`
- end: `0x180010d2a`
- name: `?IsLicensedComponentDOLBY_Internal@@YAHXZ`
- size: `58`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000d2f0`
- `0x180018b70`

## callees

- `0x180010c50`
- `0x180010cf0`
- `0x180021310`
- `0x180024700`

## pseudocode

```c
__int64 IsLicensedComponentDOLBY_Internal(void)
{
  unsigned int v0; // ebx

  if ( (unsigned int)WarbirdRuntime::CEncryption<5,WarbirdCrypto::CCipherFeistel64<28,217,204,126,13,48,223,208,17,214,202,223,18,190,165,137,8,173,218,252,11,62,167,189,14,93,32,35,30,91,149,35,2,231,74,182,24,237,126,169>,WarbirdCrypto::CHashFunctionSCP<1,1,2,2329519407998533220>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_6,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_6>::Decrypt() )
    return 0;
  v0 = IsLicensedComponentDOLBY();
  if ( (unsigned int)WarbirdRuntime::CEncryption<5,WarbirdCrypto::CCipherFeistel64<28,217,204,126,13,48,223,208,17,214,202,223,18,190,165,137,8,173,218,252,11,62,167,189,14,93,32,35,30,91,149,35,2,231,74,182,24,237,126,169>,WarbirdCrypto::CHashFunctionSCP<1,1,2,2329519407998533220>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_6,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_6>::Encrypt() )
    return 0;
  return v0;
}

```

## disassembly

```asm
0x180010cf0  sub     rsp, 28h
0x180010cf4  call    ?Decrypt@?$CEncryption@$04V?$CCipherFeistel64@$0BM@$0NJ@$0MM@$0HO@$0N@$0DA@$0NP@$0NA@$0BB@$0NG@$0MK@$0NP@$0BC@$0LO@$0KF@$0IJ@$07$0KN@$0NK@$0PM@$0L@$0DO@$0KH@$0LN@$0O@$0FN@$0CA@$0CD@$0BO@$0FL@$0JF@$0CD@$01$0OH@$0EK@$0LG@$0BI@$0ON@$0HO@$0KJ@@WarbirdCrypto@@V?$CHashFunctionSCP@$00$00$01$0CAFEBNIPCLCBHOGE@@2@UENCRYPTED_SEGMENT_DATA_CONST_6@WarbirdRuntime@@UENCRYPTED_SEGMENT_DATA_READ_WRITE_6@5@@WarbirdRuntime@@SAJPEAUENCRYPTED_SEGMENT_DATA_CONST_6@2@PEAUENCRYPTED_SEGMENT_DATA_READ_WRITE_6@2@@Z; WarbirdRuntime::CEncryption<5,WarbirdCrypto::CCipherFeistel64<28,217,204,126,13,48,223,208,17,214,202,223,18,190,165,137,8,173,218,252,11,62,167,189,14,93,32,35,30,91,149,35,2,231,74,182,24,237,126,169>,WarbirdCrypto::CHashFunctionSCP<1,1,2,2329519407998533220>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_6,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_6>::Decrypt(WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_6 *,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_6 *)
0x180010cf9  test    eax, eax
0x180010cfb  jnz     short loc_180010D22
0x180010cfd  mov     [rsp+28h+var_8], rbx
0x180010d02  call    ?IsLicensedComponentDOLBY@@YAHXZ; IsLicensedComponentDOLBY(void)
0x180010d07  mov     ebx, eax
0x180010d09  call    ?Encrypt@?$CEncryption@$04V?$CCipherFeistel64@$0BM@$0NJ@$0MM@$0HO@$0N@$0DA@$0NP@$0NA@$0BB@$0NG@$0MK@$0NP@$0BC@$0LO@$0KF@$0IJ@$07$0KN@$0NK@$0PM@$0L@$0DO@$0KH@$0LN@$0O@$0FN@$0CA@$0CD@$0BO@$0FL@$0JF@$0CD@$01$0OH@$0EK@$0LG@$0BI@$0ON@$0HO@$0KJ@@WarbirdCrypto@@V?$CHashFunctionSCP@$00$00$01$0CAFEBNIPCLCBHOGE@@2@UENCRYPTED_SEGMENT_DATA_CONST_6@WarbirdRuntime@@UENCRYPTED_SEGMENT_DATA_READ_WRITE_6@5@@WarbirdRuntime@@SAJPEAUENCRYPTED_SEGMENT_DATA_CONST_6@2@PEAUENCRYPTED_SEGMENT_DATA_READ_WRITE_6@2@@Z; WarbirdRuntime::CEncryption<5,WarbirdCrypto::CCipherFeistel64<28,217,204,126,13,48,223,208,17,214,202,223,18,190,165,137,8,173,218,252,11,62,167,189,14,93,32,35,30,91,149,35,2,231,74,182,24,237,126,169>,WarbirdCrypto::CHashFunctionSCP<1,1,2,2329519407998533220>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_6,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_6>::Encrypt(WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_6 *,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_6 *)
0x180010d0e  xor     ecx, ecx
0x180010d10  test    eax, eax
0x180010d12  cmovnz  ebx, ecx
0x180010d15  mov     eax, ebx
0x180010d17  mov     rbx, [rsp+28h+var_8]
0x180010d1c  add     rsp, 28h
0x180010d20  retn
0x180010d22  xor     eax, eax
0x180010d24  add     rsp, 28h
0x180010d28  retn
```
