# CngRsa32Compat_rc4

- ea: `0x180006a38`
- end: `0x180006a94`
- name: `CngRsa32Compat_rc4`
- size: `92`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180006cd0`
- `0x180006d60`
- `0x180006e20`
- `0x1800070e0`
- `0x180007250`
- `0x180007710`
- `0x180007870`
- `0x180007c40`
- `0x180007c70`

## callees

- `0x180006a38`

## import_xrefs

- `bcrypt!BCryptEncrypt` at `0x180006a7e`
- `bcrypt!BCryptEncrypt` at `0x180006a7e`

## pseudocode

```c
NTSTATUS __fastcall CngRsa32Compat_rc4(void **a1, ULONG cbOutput, UCHAR *a3)
{
  void *v3; // rcx
  NTSTATUS result; // eax
  ULONG v5; // [rsp+78h] [rbp+20h] BYREF

  v3 = *a1;
  v5 = 0;
  result = BCryptEncrypt(v3, a3, cbOutput, 0, 0, 0, a3, cbOutput, &v5, 0);
  if ( result < 0 )
    __fastfail(7u);
  return result;
}

```

## disassembly

```asm
0x180006a38  mov     r11, rsp
0x180006a3b  sub     rsp, 58h
0x180006a3f  mov     rcx, [rcx]; hKey
0x180006a42  mov     rax, r8
0x180006a45  mov     [rsp+58h+dwFlags], 0; dwFlags
0x180006a4d  lea     r8, [r11+20h]
0x180006a51  mov     [r11-18h], r8
0x180006a55  xor     r9d, r9d; pPaddingInfo
0x180006a58  mov     [rsp+58h+cbOutput], edx; cbOutput
0x180006a5c  mov     r8d, edx; cbInput
0x180006a5f  mov     [r11-28h], rax
0x180006a63  mov     rdx, rax; pbInput
0x180006a66  mov     [rsp+58h+cbIV], 0; cbIV
0x180006a6e  mov     qword ptr [r11-38h], 0
0x180006a76  mov     [rsp+58h+arg_18], 0
0x180006a7e  call    cs:__imp_BCryptEncrypt
0x180006a84  test    eax, eax
0x180006a86  jns     short loc_180006A8F
0x180006a88  mov     ecx, 7
0x180006a8d  int     29h; Win8: RtlFailFast(ecx)
0x180006a8f  add     rsp, 58h
0x180006a93  retn
```
