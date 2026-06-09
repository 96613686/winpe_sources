# CngRsa32Compat_rc4

- ea: `0x14000ee04`
- end: `0x14000ee67`
- name: `CngRsa32Compat_rc4`
- size: `99`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14002e3a0`
- `0x14002e430`
- `0x14002e4f0`
- `0x14002e630`
- `0x14002e7b0`
- `0x14002ea10`
- `0x14002eb70`
- `0x14002ede0`
- `0x14002ee10`

## callees

- `0x14000ee04`

## import_xrefs

- `cng!BCryptEncrypt` at `0x14000ee4a`
- `cng!BCryptEncrypt` at `0x14000ee4a`

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
0x14000ee04  mov     r11, rsp
0x14000ee07  sub     rsp, 58h
0x14000ee0b  mov     rcx, [rcx]; hKey
0x14000ee0e  mov     rax, r8
0x14000ee11  mov     [rsp+58h+dwFlags], 0; dwFlags
0x14000ee19  lea     r8, [r11+20h]
0x14000ee1d  mov     [r11-18h], r8
0x14000ee21  xor     r9d, r9d; pPaddingInfo
0x14000ee24  mov     [rsp+58h+cbOutput], edx; cbOutput
0x14000ee28  mov     r8d, edx; cbInput
0x14000ee2b  mov     [r11-28h], rax
0x14000ee2f  mov     rdx, rax; pbInput
0x14000ee32  mov     [rsp+58h+cbIV], 0; cbIV
0x14000ee3a  mov     qword ptr [r11-38h], 0
0x14000ee42  mov     [rsp+58h+arg_18], 0
0x14000ee4a  call    cs:__imp_BCryptEncrypt
0x14000ee51  nop     dword ptr [rax+rax+00h]
0x14000ee56  test    eax, eax
0x14000ee58  jns     short loc_14000EE61
0x14000ee5a  mov     ecx, 7
0x14000ee5f  int     29h; Win8: RtlFailFast(ecx)
0x14000ee61  add     rsp, 58h
0x14000ee65  retn
```
