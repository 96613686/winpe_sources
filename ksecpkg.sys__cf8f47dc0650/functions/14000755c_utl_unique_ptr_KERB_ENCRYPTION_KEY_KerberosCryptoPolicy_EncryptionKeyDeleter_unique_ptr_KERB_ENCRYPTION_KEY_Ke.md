# utl::unique_ptr<_KERB_ENCRYPTION_KEY,KerberosCryptoPolicy::EncryptionKeyDeleter>::~unique_ptr<_KERB_ENCRYPTION_KEY,KerberosCryptoPolicy::EncryptionKeyDeleter>(void)

- ea: `0x14000755c`
- end: `0x14000757c`
- name: `??1?$unique_ptr@U_KERB_ENCRYPTION_KEY@@UEncryptionKeyDeleter@KerberosCryptoPolicy@@@utl@@QEAA@XZ`
- size: `32`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1400075b4`
- `0x140008104`

## callees

- `0x14000755c`
- `0x1400086e0`

## pseudocode

```c
_BYTE *__fastcall utl::unique_ptr<_KERB_ENCRYPTION_KEY,KerberosCryptoPolicy::EncryptionKeyDeleter>::~unique_ptr<_KERB_ENCRYPTION_KEY,KerberosCryptoPolicy::EncryptionKeyDeleter>(
        __int64 a1,
        __int64 a2)
{
  _BYTE *result; // rax
  __int64 v3; // rcx

  result = (_BYTE *)a1;
  v3 = *(_QWORD *)(a1 + 8);
  if ( v3 )
  {
    if ( *result )
      return (_BYTE *)KerbFreeKey(v3, a2);
  }
  return result;
}

```

## disassembly

```asm
0x14000755c  sub     rsp, 28h
0x140007560  mov     rax, rcx
0x140007563  mov     rcx, [rcx+8]
0x140007567  test    rcx, rcx
0x14000756a  jz      short loc_140007576
0x14000756c  cmp     byte ptr [rax], 0
0x14000756f  jz      short loc_140007576
0x140007571  call    KerbFreeKey
0x140007576  add     rsp, 28h
0x14000757a  retn
```
