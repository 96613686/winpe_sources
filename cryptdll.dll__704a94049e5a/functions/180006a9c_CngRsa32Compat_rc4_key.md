# CngRsa32Compat_rc4_key

- ea: `0x180006a9c`
- end: `0x180006b11`
- name: `CngRsa32Compat_rc4_key`
- size: `117`
- prototype: `__int64 __fastcall(BCRYPT_KEY_HANDLE *phKey, ULONG cbSecret, PUCHAR pbSecret)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800070e0`
- `0x180007250`
- `0x180007384`
- `0x180007710`
- `0x180007870`
- `0x180007ab8`
- `0x180007bc0`

## callees

- `0x180006a9c`

## import_xrefs

- `bcrypt!BCryptDestroyKey` at `0x180006ac5`
- `bcrypt!BCryptDestroyKey` at `0x180006ac5`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180006af0`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180006af0`

## pseudocode

```c
NTSTATUS __fastcall CngRsa32Compat_rc4_key(BCRYPT_KEY_HANDLE *phKey, ULONG cbSecret, PUCHAR pbSecret)
{
  BCRYPT_KEY_HANDLE v6; // rcx
  NTSTATUS result; // eax

  if ( !phKey )
    __fastfail(7u);
  v6 = *phKey;
  if ( *phKey )
  {
    BCryptDestroyKey(v6);
    *phKey = 0;
  }
  result = BCryptGenerateSymmetricKey((BCRYPT_ALG_HANDLE)0x71, phKey, 0, 0, pbSecret, cbSecret, 0);
  if ( result < 0 )
    __fastfail(7u);
  return result;
}

```

## disassembly

```asm
0x180006a9c  mov     [rsp+arg_0], rbx
0x180006aa1  mov     [rsp+arg_8], rsi
0x180006aa6  push    rdi
0x180006aa7  sub     rsp, 40h
0x180006aab  mov     rdi, r8
0x180006aae  mov     esi, edx
0x180006ab0  mov     rbx, rcx
0x180006ab3  test    rcx, rcx
0x180006ab6  jnz     short loc_180006ABD
0x180006ab8  lea     ecx, [rbx+7]
0x180006abb  int     29h; Win8: RtlFailFast(ecx)
0x180006abd  mov     rcx, [rbx]; hKey
0x180006ac0  test    rcx, rcx
0x180006ac3  jz      short loc_180006AD2
0x180006ac5  call    cs:__imp_BCryptDestroyKey
0x180006acb  mov     qword ptr [rbx], 0
0x180006ad2  xor     r9d, r9d; cbKeyObject
0x180006ad5  mov     [rsp+48h+dwFlags], 0; dwFlags
0x180006add  mov     [rsp+48h+cbSecret], esi; cbSecret
0x180006ae1  xor     r8d, r8d; pbKeyObject
0x180006ae4  mov     rdx, rbx; phKey
0x180006ae7  mov     [rsp+48h+pbSecret], rdi; pbSecret
0x180006aec  lea     ecx, [r9+71h]; hAlgorithm
0x180006af0  call    cs:__imp_BCryptGenerateSymmetricKey
0x180006af6  test    eax, eax
0x180006af8  jns     short loc_180006B01
0x180006afa  mov     ecx, 7
0x180006aff  int     29h; Win8: RtlFailFast(ecx)
0x180006b01  mov     rbx, [rsp+48h+arg_0]
0x180006b06  mov     rsi, [rsp+48h+arg_8]
0x180006b0b  add     rsp, 40h
0x180006b0f  pop     rdi
0x180006b10  retn
```
