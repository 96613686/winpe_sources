# EngFntCacheFault

- ea: `0x1400928c0`
- end: `0x14009295c`
- name: `EngFntCacheFault`
- size: `156`
- prototype: `void __stdcall(ULONG ulFastCheckSum, ULONG iFaultMode)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x140007104`
- `0x14000978c`
- `0x140031ed8`
- `0x1400787e4`
- `0x14007eac4`
- `0x140092168`

## callees

- `0x140075de0`

## import_xrefs

- `win32u!NtGdiExtEscape` at `0x14009293e`
- `win32u!NtGdiExtEscape` at `0x14009293e`

## pseudocode

```c
void __stdcall EngFntCacheFault(ULONG ulFastCheckSum, ULONG iFaultMode)
{
  __int64 v2; // [rsp+40h] [rbp-58h] BYREF
  ULONG v3; // [rsp+48h] [rbp-50h]
  ULONG v4; // [rsp+4Ch] [rbp-4Ch]
  __int128 v5; // [rsp+50h] [rbp-48h]
  __int128 v6; // [rsp+60h] [rbp-38h]
  __int128 v7; // [rsp+70h] [rbp-28h] BYREF
  wchar_t v8; // [rsp+80h] [rbp-18h]

  v2 = 9;
  v5 = 0;
  v6 = 0;
  v3 = ulFastCheckSum;
  v4 = iFaultMode;
  v7 = *(_OWORD *)L"UmfdHost";
  v8 = aUmfdhost[8];
  ((void (__fastcall *)(_QWORD, __int128 *, __int64, __int64, int, __int64 *, int, __int64 *))NtGdiExtEscape)(
    0,
    &v7,
    9,
    19,
    48,
    &v2,
    48,
    &v2);
}

```

## disassembly

```asm
0x1400928c0  mov     r11, rsp
0x1400928c3  sub     rsp, 98h
0x1400928ca  mov     rax, cs:__security_cookie
0x1400928d1  xor     rax, rsp
0x1400928d4  mov     [rsp+98h+var_10], rax
0x1400928dc  movzx   eax, word ptr cs:aUmfdhost+10h; ""
0x1400928e3  xorps   xmm0, xmm0
0x1400928e6  movups  [rsp+98h+var_58], xmm0
0x1400928eb  mov     r8d, 9
0x1400928f1  movups  [rsp+98h+var_48], xmm0
0x1400928f6  movups  [rsp+98h+var_38], xmm0
0x1400928fb  mov     [r11-58h], r8d
0x1400928ff  lea     r9d, [r8+0Ah]
0x140092903  movups  xmm0, xmmword ptr cs:aUmfdhost; "UmfdHost"
0x14009290a  mov     dword ptr [rsp+98h+var_58+8], ecx
0x14009290e  lea     ecx, [r8+27h]
0x140092912  mov     dword ptr [rsp+98h+var_58+0Ch], edx
0x140092916  lea     rdx, [r11-28h]
0x14009291a  movups  [rsp+98h+var_28], xmm0
0x14009291f  mov     [r11-18h], ax
0x140092924  lea     rax, [r11-58h]
0x140092928  mov     [r11-60h], rax
0x14009292c  lea     rax, [r11-58h]
0x140092930  mov     [rsp+98h+var_68], ecx
0x140092934  mov     [r11-70h], rax
0x140092938  mov     [rsp+98h+var_78], ecx
0x14009293c  xor     ecx, ecx
0x14009293e  call    cs:__imp_NtGdiExtEscape
0x140092944  mov     rcx, [rsp+98h+var_10]
0x14009294c  xor     rcx, rsp; StackCookie
0x14009294f  call    __security_check_cookie
0x140092954  add     rsp, 98h
0x14009295b  retn
```
