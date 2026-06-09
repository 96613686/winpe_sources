# PATHOBJ_bPolyBezierTo

- ea: `0x140051cc8`
- end: `0x140051d71`
- name: `PATHOBJ_bPolyBezierTo`
- size: `169`
- prototype: `BOOL __stdcall(PATHOBJ *ppo, POINTFIX *pptfx, ULONG cptfx)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400517c8`
- `0x14007f4c0`

## callees

- `0x140075de0`

## import_xrefs

- `win32u!NtGdiExtEscape` at `0x140051d53`
- `win32u!NtGdiExtEscape` at `0x140051d53`

## pseudocode

```c
BOOL __stdcall PATHOBJ_bPolyBezierTo(PATHOBJ *ppo, POINTFIX *pptfx, ULONG cptfx)
{
  __int64 v4; // [rsp+40h] [rbp+7h] BYREF
  PATHOBJ *v5; // [rsp+48h] [rbp+Fh]
  POINTFIX *v6; // [rsp+50h] [rbp+17h]
  ULONG v7; // [rsp+58h] [rbp+1Fh]
  __int128 v8; // [rsp+5Ch] [rbp+23h]
  int v9; // [rsp+6Ch] [rbp+33h]
  __int128 v10; // [rsp+70h] [rbp+37h] BYREF
  wchar_t v11; // [rsp+80h] [rbp+47h]

  v5 = ppo;
  v11 = aUmfdhost[8];
  v8 = 0;
  v7 = cptfx;
  v6 = pptfx;
  v4 = 6;
  v9 = 0;
  v10 = *(_OWORD *)L"UmfdHost";
  ((void (__fastcall *)(_QWORD, __int128 *, __int64, __int64, int, __int64 *, int, __int64 *))NtGdiExtEscape)(
    0,
    &v10,
    9,
    19,
    48,
    &v4,
    48,
    &v4);
  return (int)v5;
}

```

## disassembly

```asm
0x140051cc8  push    rbp
0x140051cca  lea     rbp, [rsp-57h]
0x140051ccf  sub     rsp, 90h
0x140051cd6  mov     rax, cs:__security_cookie
0x140051cdd  xor     rax, rsp
0x140051ce0  mov     [rbp+57h+var_8], rax
0x140051ce4  mov     rax, rcx
0x140051ce7  mov     [rbp+57h+var_48], ecx
0x140051cea  sar     rax, 20h
0x140051cee  mov     ecx, 30h ; '0'
0x140051cf3  mov     [rbp+57h+var_44], eax
0x140051cf6  xorps   xmm0, xmm0
0x140051cf9  movzx   eax, word ptr cs:aUmfdhost+10h; ""
0x140051d00  mov     [rbp+57h+var_10], ax
0x140051d04  lea     rax, [rbp+57h+var_50]
0x140051d08  mov     [rsp+90h+var_58], rax
0x140051d0d  lea     r9d, [rcx-1Dh]
0x140051d11  mov     [rsp+90h+var_60], ecx
0x140051d15  lea     rax, [rbp+57h+var_50]
0x140051d19  movdqu  [rbp+57h+var_34], xmm0
0x140051d1e  mov     [rsp+90h+var_68], rax
0x140051d23  movups  xmm0, xmmword ptr cs:aUmfdhost; "UmfdHost"
0x140051d2a  mov     [rbp+57h+var_38], r8d
0x140051d2e  lea     r8d, [rcx-27h]
0x140051d32  mov     [rsp+90h+var_70], ecx
0x140051d36  xor     ecx, ecx
0x140051d38  mov     [rbp+57h+var_40], rdx
0x140051d3c  lea     rdx, [rbp+57h+var_20]
0x140051d40  mov     [rbp+57h+var_50], 6
0x140051d48  mov     [rbp+57h+var_24], 0
0x140051d4f  movups  [rbp+57h+var_20], xmm0
0x140051d53  call    cs:__imp_NtGdiExtEscape
0x140051d59  mov     eax, [rbp+57h+var_48]
0x140051d5c  mov     rcx, [rbp+57h+var_8]
0x140051d60  xor     rcx, rsp; StackCookie
0x140051d63  call    __security_check_cookie
0x140051d68  add     rsp, 90h
0x140051d6f  pop     rbp
0x140051d70  retn
```
