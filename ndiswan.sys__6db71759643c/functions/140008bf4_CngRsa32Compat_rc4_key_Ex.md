# CngRsa32Compat_rc4_key_Ex

- ea: `0x140008bf4`
- end: `0x140008c79`
- name: `CngRsa32Compat_rc4_key_Ex`
- size: `133`
- prototype: `__int64 __fastcall(BCRYPT_KEY_HANDLE *phKey, ULONG cbSecret, PUCHAR pbSecret)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140024728`
- `0x1400247c4`
- `0x140032340`
- `0x1400330a0`

## callees

- `0x140008bf4`

## import_xrefs

- `cng!BCryptDestroyKey` at `0x140008c1d`
- `cng!BCryptDestroyKey` at `0x140008c1d`
- `cng!BCryptGenerateSymmetricKey` at `0x140008c51`
- `cng!BCryptGenerateSymmetricKey` at `0x140008c51`

## pseudocode

```c
NTSTATUS __fastcall CngRsa32Compat_rc4_key_Ex(BCRYPT_KEY_HANDLE *phKey, ULONG cbSecret, PUCHAR pbSecret)
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
  result = BCryptGenerateSymmetricKey(ghAlgRC4, phKey, 0, 0, pbSecret, cbSecret, 0);
  if ( result < 0 )
    __fastfail(7u);
  return result;
}

```

## disassembly

```asm
0x140008bf4  mov     [rsp+arg_0], rbx
0x140008bf9  mov     [rsp+arg_8], rsi
0x140008bfe  push    rdi
0x140008bff  sub     rsp, 40h
0x140008c03  mov     rdi, r8
0x140008c06  mov     esi, edx
0x140008c08  mov     rbx, rcx
0x140008c0b  test    rcx, rcx
0x140008c0e  jnz     short loc_140008C15
0x140008c10  lea     ecx, [rbx+7]
0x140008c13  int     29h; Win8: RtlFailFast(ecx)
0x140008c15  mov     rcx, [rbx]; hKey
0x140008c18  test    rcx, rcx
0x140008c1b  jz      short loc_140008C30
0x140008c1d  call    cs:__imp_BCryptDestroyKey
0x140008c24  nop     dword ptr [rax+rax+00h]
0x140008c29  mov     qword ptr [rbx], 0
0x140008c30  mov     rcx, cs:ghAlgRC4; hAlgorithm
0x140008c37  xor     r9d, r9d; cbKeyObject
0x140008c3a  mov     [rsp+48h+dwFlags], 0; dwFlags
0x140008c42  xor     r8d, r8d; pbKeyObject
0x140008c45  mov     [rsp+48h+cbSecret], esi; cbSecret
0x140008c49  mov     rdx, rbx; phKey
0x140008c4c  mov     [rsp+48h+pbSecret], rdi; pbSecret
0x140008c51  call    cs:__imp_BCryptGenerateSymmetricKey
0x140008c58  nop     dword ptr [rax+rax+00h]
0x140008c5d  test    eax, eax
0x140008c5f  jns     short loc_140008C68
0x140008c61  mov     ecx, 7
0x140008c66  int     29h; Win8: RtlFailFast(ecx)
0x140008c68  mov     rbx, [rsp+48h+arg_0]
0x140008c6d  mov     rsi, [rsp+48h+arg_8]
0x140008c72  add     rsp, 40h
0x140008c76  pop     rdi
0x140008c77  retn
```
