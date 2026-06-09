# PATHOBJ_bMoveTo

- ea: `0x140051e28`
- end: `0x140051ece`
- name: `PATHOBJ_bMoveTo`
- size: `166`
- prototype: `BOOL __stdcall(PATHOBJ *ppo, POINTFIX ptfx)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1400517c8`
- `0x14007c358`
- `0x14007f630`

## callees

- `0x140075de0`

## import_xrefs

- `win32u!NtGdiExtEscape` at `0x140051eb0`
- `win32u!NtGdiExtEscape` at `0x140051eb0`

## pseudocode

```c
BOOL __stdcall PATHOBJ_bMoveTo(PATHOBJ *ppo, POINTFIX ptfx)
{
  __int64 v3; // [rsp+40h] [rbp+7h] BYREF
  PATHOBJ *v4; // [rsp+48h] [rbp+Fh]
  POINTFIX v5; // [rsp+50h] [rbp+17h]
  __int128 v6; // [rsp+58h] [rbp+1Fh]
  __int64 v7; // [rsp+68h] [rbp+2Fh]
  __int128 v8; // [rsp+70h] [rbp+37h] BYREF
  wchar_t v9; // [rsp+80h] [rbp+47h]

  v4 = ppo;
  v9 = aUmfdhost[8];
  v6 = 0;
  v5 = ptfx;
  v3 = 5;
  v7 = 0;
  v8 = *(_OWORD *)L"UmfdHost";
  ((void (__fastcall *)(_QWORD, __int128 *, __int64, __int64, int, __int64 *, int, __int64 *))NtGdiExtEscape)(
    0,
    &v8,
    9,
    19,
    48,
    &v3,
    48,
    &v3);
  return (int)v4;
}

```

## disassembly

```asm
0x140051e28  push    rbp
0x140051e2a  lea     rbp, [rsp-57h]
0x140051e2f  sub     rsp, 90h
0x140051e36  mov     rax, cs:__security_cookie
0x140051e3d  xor     rax, rsp
0x140051e40  mov     [rbp+57h+var_8], rax
0x140051e44  mov     rax, rcx
0x140051e47  mov     [rbp+57h+var_48], ecx
0x140051e4a  sar     rax, 20h
0x140051e4e  mov     ecx, 30h ; '0'
0x140051e53  mov     [rbp+57h+var_44], eax
0x140051e56  xorps   xmm0, xmm0
0x140051e59  movzx   eax, word ptr cs:aUmfdhost+10h; ""
0x140051e60  mov     [rbp+57h+var_10], ax
0x140051e64  lea     rax, [rbp+57h+var_50]
0x140051e68  mov     [rsp+90h+var_58], rax
0x140051e6d  lea     r9d, [rcx-1Dh]
0x140051e71  mov     [rsp+90h+var_60], ecx
0x140051e75  lea     rax, [rbp+57h+var_50]
0x140051e79  movdqu  [rbp+57h+var_38], xmm0
0x140051e7e  mov     [rsp+90h+var_68], rax
0x140051e83  lea     r8d, [rcx-27h]
0x140051e87  movups  xmm0, xmmword ptr cs:aUmfdhost; "UmfdHost"
0x140051e8e  mov     [rsp+90h+var_70], ecx
0x140051e92  xor     ecx, ecx
0x140051e94  mov     [rbp+57h+var_40], rdx
0x140051e98  lea     rdx, [rbp+57h+var_20]
0x140051e9c  mov     [rbp+57h+var_50], 5
0x140051ea4  mov     [rbp+57h+var_28], 0
0x140051eac  movups  [rbp+57h+var_20], xmm0
0x140051eb0  call    cs:__imp_NtGdiExtEscape
0x140051eb6  mov     eax, [rbp+57h+var_48]
0x140051eb9  mov     rcx, [rbp+57h+var_8]
0x140051ebd  xor     rcx, rsp; StackCookie
0x140051ec0  call    __security_check_cookie
0x140051ec5  add     rsp, 90h
0x140051ecc  pop     rbp
0x140051ecd  retn
```
