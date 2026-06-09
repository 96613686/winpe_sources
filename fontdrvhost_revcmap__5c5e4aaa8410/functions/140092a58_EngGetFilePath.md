# EngGetFilePath

- ea: `0x140092a58`
- end: `0x140092afe`
- name: `EngGetFilePath`
- size: `166`
- prototype: `BOOL __stdcall(HANDLE h, WCHAR (*pDest)[261])`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14007ee98`

## callees

- `0x140075de0`

## import_xrefs

- `win32u!NtGdiExtEscape` at `0x140092ae0`
- `win32u!NtGdiExtEscape` at `0x140092ae0`

## pseudocode

```c
BOOL __stdcall EngGetFilePath(HANDLE h, WCHAR (*pDest)[261])
{
  __int64 v3; // [rsp+40h] [rbp+7h] BYREF
  HANDLE v4; // [rsp+48h] [rbp+Fh]
  WCHAR *v5; // [rsp+50h] [rbp+17h]
  __int128 v6; // [rsp+58h] [rbp+1Fh]
  __int64 v7; // [rsp+68h] [rbp+2Fh]
  __int128 v8; // [rsp+70h] [rbp+37h] BYREF
  wchar_t v9; // [rsp+80h] [rbp+47h]

  v4 = h;
  v9 = aUmfdhost[8];
  v6 = 0;
  v5 = (WCHAR *)pDest;
  v3 = 13;
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
0x140092a58  push    rbp
0x140092a5a  lea     rbp, [rsp-57h]
0x140092a5f  sub     rsp, 90h
0x140092a66  mov     rax, cs:__security_cookie
0x140092a6d  xor     rax, rsp
0x140092a70  mov     [rbp+57h+var_8], rax
0x140092a74  mov     rax, rcx
0x140092a77  mov     [rbp+57h+var_48], ecx
0x140092a7a  sar     rax, 20h
0x140092a7e  mov     ecx, 30h ; '0'
0x140092a83  mov     [rbp+57h+var_44], eax
0x140092a86  xorps   xmm0, xmm0
0x140092a89  movzx   eax, word ptr cs:aUmfdhost+10h; ""
0x140092a90  mov     [rbp+57h+var_10], ax
0x140092a94  lea     rax, [rbp+57h+var_50]
0x140092a98  mov     [rsp+90h+var_58], rax
0x140092a9d  lea     r9d, [rcx-1Dh]
0x140092aa1  mov     [rsp+90h+var_60], ecx
0x140092aa5  lea     rax, [rbp+57h+var_50]
0x140092aa9  movdqu  [rbp+57h+var_38], xmm0
0x140092aae  mov     [rsp+90h+var_68], rax
0x140092ab3  lea     r8d, [rcx-27h]
0x140092ab7  movups  xmm0, xmmword ptr cs:aUmfdhost; "UmfdHost"
0x140092abe  mov     [rsp+90h+var_70], ecx
0x140092ac2  xor     ecx, ecx
0x140092ac4  mov     [rbp+57h+var_40], rdx
0x140092ac8  lea     rdx, [rbp+57h+var_20]
0x140092acc  mov     [rbp+57h+var_50], 0Dh
0x140092ad4  mov     [rbp+57h+var_28], 0
0x140092adc  movups  [rbp+57h+var_20], xmm0
0x140092ae0  call    cs:__imp_NtGdiExtEscape
0x140092ae6  mov     eax, [rbp+57h+var_48]
0x140092ae9  mov     rcx, [rbp+57h+var_8]
0x140092aed  xor     rcx, rsp; StackCookie
0x140092af0  call    __security_check_cookie
0x140092af5  add     rsp, 90h
0x140092afc  pop     rbp
0x140092afd  retn
```
