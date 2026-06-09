# CngRsa32Compat_rc4_key

- ea: `0x14000ee70`
- end: `0x14000eef2`
- name: `CngRsa32Compat_rc4_key`
- size: `130`
- prototype: `__int64 __fastcall(BCRYPT_KEY_HANDLE *phKey, ULONG cbSecret, PUCHAR pbSecret)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000f244`
- `0x14000f580`
- `0x14002e630`
- `0x14002e7b0`
- `0x14002ea10`
- `0x14002eb70`
- `0x14002ed60`

## callees

- `0x14000ee70`

## import_xrefs

- `cng!BCryptDestroyKey` at `0x14000ee99`
- `cng!BCryptDestroyKey` at `0x14000ee99`
- `cng!BCryptGenerateSymmetricKey` at `0x14000eeca`
- `cng!BCryptGenerateSymmetricKey` at `0x14000eeca`

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
0x14000ee70  mov     [rsp+arg_0], rbx
0x14000ee75  mov     [rsp+arg_8], rsi
0x14000ee7a  push    rdi
0x14000ee7b  sub     rsp, 40h
0x14000ee7f  mov     rdi, r8
0x14000ee82  mov     esi, edx
0x14000ee84  mov     rbx, rcx
0x14000ee87  test    rcx, rcx
0x14000ee8a  jnz     short loc_14000EE91
0x14000ee8c  lea     ecx, [rbx+7]
0x14000ee8f  int     29h; Win8: RtlFailFast(ecx)
0x14000ee91  mov     rcx, [rbx]; hKey
0x14000ee94  test    rcx, rcx
0x14000ee97  jz      short loc_14000EEAC
0x14000ee99  call    cs:__imp_BCryptDestroyKey
0x14000eea0  nop     dword ptr [rax+rax+00h]
0x14000eea5  mov     qword ptr [rbx], 0
0x14000eeac  xor     r9d, r9d; cbKeyObject
0x14000eeaf  mov     [rsp+48h+dwFlags], 0; dwFlags
0x14000eeb7  mov     [rsp+48h+cbSecret], esi; cbSecret
0x14000eebb  xor     r8d, r8d; pbKeyObject
0x14000eebe  mov     rdx, rbx; phKey
0x14000eec1  mov     [rsp+48h+pbSecret], rdi; pbSecret
0x14000eec6  lea     ecx, [r9+71h]; hAlgorithm
0x14000eeca  call    cs:__imp_BCryptGenerateSymmetricKey
0x14000eed1  nop     dword ptr [rax+rax+00h]
0x14000eed6  test    eax, eax
0x14000eed8  jns     short loc_14000EEE1
0x14000eeda  mov     ecx, 7
0x14000eedf  int     29h; Win8: RtlFailFast(ecx)
0x14000eee1  mov     rbx, [rsp+48h+arg_0]
0x14000eee6  mov     rsi, [rsp+48h+arg_8]
0x14000eeeb  add     rsp, 40h
0x14000eeef  pop     rdi
0x14000eef0  retn
```
