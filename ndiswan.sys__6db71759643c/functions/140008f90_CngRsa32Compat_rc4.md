# CngRsa32Compat_rc4

- ea: `0x140008f90`
- end: `0x140008ff3`
- name: `CngRsa32Compat_rc4`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400330a0`

## callees

- `0x140008f90`

## import_xrefs

- `cng!BCryptEncrypt` at `0x140008fd6`
- `cng!BCryptEncrypt` at `0x140008fd6`

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
0x140008f90  mov     r11, rsp
0x140008f93  sub     rsp, 58h
0x140008f97  mov     rcx, [rcx]; hKey
0x140008f9a  mov     rax, r8
0x140008f9d  mov     [rsp+58h+dwFlags], 0; dwFlags
0x140008fa5  lea     r8, [r11+20h]
0x140008fa9  mov     [r11-18h], r8
0x140008fad  xor     r9d, r9d; pPaddingInfo
0x140008fb0  mov     [rsp+58h+cbOutput], edx; cbOutput
0x140008fb4  mov     r8d, edx; cbInput
0x140008fb7  mov     [r11-28h], rax
0x140008fbb  mov     rdx, rax; pbInput
0x140008fbe  mov     [rsp+58h+cbIV], 0; cbIV
0x140008fc6  mov     qword ptr [r11-38h], 0
0x140008fce  mov     [rsp+58h+arg_18], 0
0x140008fd6  call    cs:__imp_BCryptEncrypt
0x140008fdd  nop     dword ptr [rax+rax+00h]
0x140008fe2  test    eax, eax
0x140008fe4  jns     short loc_140008FED
0x140008fe6  mov     ecx, 7
0x140008feb  int     29h; Win8: RtlFailFast(ecx)
0x140008fed  add     rsp, 58h
0x140008ff1  retn
```
