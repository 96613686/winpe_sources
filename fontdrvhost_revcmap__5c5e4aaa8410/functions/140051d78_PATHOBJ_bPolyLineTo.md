# PATHOBJ_bPolyLineTo

- ea: `0x140051d78`
- end: `0x140051e21`
- name: `PATHOBJ_bPolyLineTo`
- size: `169`
- prototype: `BOOL __stdcall(PATHOBJ *ppo, POINTFIX *pptfx, ULONG cptfx)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1400517c8`
- `0x14007c358`
- `0x14007f5b0`

## callees

- `0x140075de0`

## import_xrefs

- `win32u!NtGdiExtEscape` at `0x140051e03`
- `win32u!NtGdiExtEscape` at `0x140051e03`

## pseudocode

```c
BOOL __stdcall PATHOBJ_bPolyLineTo(PATHOBJ *ppo, POINTFIX *pptfx, ULONG cptfx)
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
  v4 = 7;
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
0x140051d78  push    rbp
0x140051d7a  lea     rbp, [rsp-57h]
0x140051d7f  sub     rsp, 90h
0x140051d86  mov     rax, cs:__security_cookie
0x140051d8d  xor     rax, rsp
0x140051d90  mov     [rbp+57h+var_8], rax
0x140051d94  mov     rax, rcx
0x140051d97  mov     [rbp+57h+var_48], ecx
0x140051d9a  sar     rax, 20h
0x140051d9e  mov     ecx, 30h ; '0'
0x140051da3  mov     [rbp+57h+var_44], eax
0x140051da6  xorps   xmm0, xmm0
0x140051da9  movzx   eax, word ptr cs:aUmfdhost+10h; ""
0x140051db0  mov     [rbp+57h+var_10], ax
0x140051db4  lea     rax, [rbp+57h+var_50]
0x140051db8  mov     [rsp+90h+var_58], rax
0x140051dbd  lea     r9d, [rcx-1Dh]
0x140051dc1  mov     [rsp+90h+var_60], ecx
0x140051dc5  lea     rax, [rbp+57h+var_50]
0x140051dc9  movdqu  [rbp+57h+var_34], xmm0
0x140051dce  mov     [rsp+90h+var_68], rax
0x140051dd3  movups  xmm0, xmmword ptr cs:aUmfdhost; "UmfdHost"
0x140051dda  mov     [rbp+57h+var_38], r8d
0x140051dde  lea     r8d, [rcx-27h]
0x140051de2  mov     [rsp+90h+var_70], ecx
0x140051de6  xor     ecx, ecx
0x140051de8  mov     [rbp+57h+var_40], rdx
0x140051dec  lea     rdx, [rbp+57h+var_20]
0x140051df0  mov     [rbp+57h+var_50], 7
0x140051df8  mov     [rbp+57h+var_24], 0
0x140051dff  movups  [rbp+57h+var_20], xmm0
0x140051e03  call    cs:__imp_NtGdiExtEscape
0x140051e09  mov     eax, [rbp+57h+var_48]
0x140051e0c  mov     rcx, [rbp+57h+var_8]
0x140051e10  xor     rcx, rsp; StackCookie
0x140051e13  call    __security_check_cookie
0x140051e18  add     rsp, 90h
0x140051e1f  pop     rbp
0x140051e20  retn
```
