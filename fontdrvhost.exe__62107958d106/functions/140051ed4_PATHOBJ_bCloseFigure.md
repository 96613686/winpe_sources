# PATHOBJ_bCloseFigure

- ea: `0x140051ed4`
- end: `0x140051f74`
- name: `PATHOBJ_bCloseFigure`
- size: `160`
- prototype: `BOOL __stdcall(PATHOBJ *ppo)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400517c8`
- `0x14007f490`

## callees

- `0x140075de0`

## import_xrefs

- `win32u!NtGdiExtEscape` at `0x140051f56`
- `win32u!NtGdiExtEscape` at `0x140051f56`

## pseudocode

```c
BOOL __stdcall PATHOBJ_bCloseFigure(PATHOBJ *ppo)
{
  __int64 v2; // [rsp+40h] [rbp+7h] BYREF
  PATHOBJ *v3; // [rsp+48h] [rbp+Fh]
  __int128 v4; // [rsp+50h] [rbp+17h]
  __int128 v5; // [rsp+60h] [rbp+27h]
  __int128 v6; // [rsp+70h] [rbp+37h] BYREF
  wchar_t v7; // [rsp+80h] [rbp+47h]

  v3 = ppo;
  v7 = aUmfdhost[8];
  v4 = 0;
  v5 = 0;
  v2 = 4;
  v6 = *(_OWORD *)L"UmfdHost";
  ((void (__fastcall *)(_QWORD, __int128 *, __int64, __int64, int, __int64 *, int, __int64 *))NtGdiExtEscape)(
    0,
    &v6,
    9,
    19,
    48,
    &v2,
    48,
    &v2);
  return (int)v3;
}

```

## disassembly

```asm
0x140051ed4  push    rbp
0x140051ed6  lea     rbp, [rsp-57h]
0x140051edb  sub     rsp, 90h
0x140051ee2  mov     rax, cs:__security_cookie
0x140051ee9  xor     rax, rsp
0x140051eec  mov     [rbp+57h+var_8], rax
0x140051ef0  xorps   xmm0, xmm0
0x140051ef3  lea     rdx, [rbp+57h+var_20]
0x140051ef7  movups  [rbp+57h+var_50], xmm0
0x140051efb  mov     rax, rcx
0x140051efe  mov     dword ptr [rbp+57h+var_50+8], ecx
0x140051f01  sar     rax, 20h
0x140051f05  mov     ecx, 30h ; '0'
0x140051f0a  mov     dword ptr [rbp+57h+var_50+0Ch], eax
0x140051f0d  movzx   eax, word ptr cs:aUmfdhost+10h; ""
0x140051f14  mov     [rbp+57h+var_10], ax
0x140051f18  lea     rax, [rbp+57h+var_50]
0x140051f1c  mov     [rsp+90h+var_58], rax
0x140051f21  lea     r9d, [rcx-1Dh]
0x140051f25  mov     [rsp+90h+var_60], ecx
0x140051f29  lea     rax, [rbp+57h+var_50]
0x140051f2d  movups  [rbp+57h+var_40], xmm0
0x140051f31  mov     [rsp+90h+var_68], rax
0x140051f36  lea     r8d, [rcx-27h]
0x140051f3a  movups  [rbp+57h+var_30], xmm0
0x140051f3e  mov     [rsp+90h+var_70], ecx
0x140051f42  xor     ecx, ecx
0x140051f44  movups  xmm0, xmmword ptr cs:aUmfdhost; "UmfdHost"
0x140051f4b  mov     dword ptr [rbp+57h+var_50], 4
0x140051f52  movups  [rbp+57h+var_20], xmm0
0x140051f56  call    cs:__imp_NtGdiExtEscape
0x140051f5c  mov     eax, dword ptr [rbp+57h+var_50+8]
0x140051f5f  mov     rcx, [rbp+57h+var_8]
0x140051f63  xor     rcx, rsp; StackCookie
0x140051f66  call    __security_check_cookie
0x140051f6b  add     rsp, 90h
0x140051f72  pop     rbp
0x140051f73  retn
```
