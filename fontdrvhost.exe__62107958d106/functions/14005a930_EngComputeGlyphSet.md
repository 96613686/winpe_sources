# EngComputeGlyphSet

- ea: `0x14005a930`
- end: `0x14005aaa4`
- name: `EngComputeGlyphSet`
- size: `372`
- prototype: `FD_GLYPHSET *__stdcall(INT nCodePage, INT nFirstChar, INT cChars)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14005a7b8`
- `0x140091fdc`

## callees

- `0x14005a930`
- `0x140075de0`

## import_xrefs

- `KERNEL32!GlobalFree` at `0x14005aa9c`
- `KERNEL32!GlobalFree` at `0x14005aa9c`
- `KERNEL32!GlobalAlloc` at `0x14005a9e8`
- `KERNEL32!GlobalAlloc` at `0x14005a9e8`
- `win32u!NtGdiExtEscape` at `0x14005a9d3`
- `win32u!NtGdiExtEscape` at `0x14005aa63`
- `win32u!NtGdiExtEscape` at `0x14005a9d3`
- `win32u!NtGdiExtEscape` at `0x14005aa63`

## pseudocode

```c
FD_GLYPHSET *__stdcall EngComputeGlyphSet(INT nCodePage, INT nFirstChar, INT cChars)
{
  __int64 v4; // rsi
  FD_GLYPHSET *v5; // rax
  FD_GLYPHSET *v6; // rbx
  __int64 v8; // [rsp+48h] [rbp-9h] BYREF
  SIZE_T dwBytes; // [rsp+50h] [rbp-1h]
  __int64 v10; // [rsp+58h] [rbp+7h]
  FD_GLYPHSET *v11; // [rsp+60h] [rbp+Fh]
  __int64 v12; // [rsp+68h] [rbp+17h]
  __int64 v13; // [rsp+70h] [rbp+1Fh]
  __int128 v14; // [rsp+78h] [rbp+27h] BYREF
  wchar_t v15; // [rsp+88h] [rbp+37h]

  v15 = aUmfdhost[8];
  dwBytes = (unsigned int)nCodePage;
  v8 = 14;
  v10 = 256;
  v13 = 0;
  v11 = 0;
  v12 = 0;
  v14 = *(_OWORD *)L"UmfdHost";
  ((void (__fastcall *)(_QWORD, __int128 *, __int64, __int64, int, __int64 *, int, __int64 *))NtGdiExtEscape)(
    0,
    &v14,
    9,
    19,
    48,
    &v8,
    48,
    &v8);
  v4 = (unsigned int)dwBytes;
  if ( (_DWORD)dwBytes )
  {
    v5 = (FD_GLYPHSET *)GlobalAlloc(0, (unsigned int)dwBytes);
    v6 = v5;
    if ( v5 )
    {
      v11 = v5;
      v15 = aUmfdhost[8];
      LODWORD(v8) = 14;
      dwBytes = (unsigned int)nCodePage;
      LODWORD(v10) = 256;
      v12 = v4;
      v14 = *(_OWORD *)L"UmfdHost";
      ((void (__fastcall *)(_QWORD, __int128 *, __int64, __int64, int, __int64 *, int, __int64 *))NtGdiExtEscape)(
        0,
        &v14,
        9,
        19,
        48,
        &v8,
        48,
        &v8);
      if ( (_DWORD)dwBytes == (_DWORD)v4 )
        return v6;
      GlobalFree(v6);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14005a930  mov     r11, rsp
0x14005a933  mov     [r11+10h], rbx
0x14005a937  mov     [r11+18h], rsi
0x14005a93b  push    rbp
0x14005a93c  push    rdi
0x14005a93d  push    r14
0x14005a93f  lea     rbp, [r11-5Fh]
0x14005a943  sub     rsp, 90h
0x14005a94a  mov     rax, cs:__security_cookie
0x14005a951  xor     rax, rsp
0x14005a954  mov     [rbp+57h+var_18], rax
0x14005a958  movzx   eax, word ptr cs:aUmfdhost+10h; ""
0x14005a95f  lea     rdx, [rbp+57h+var_30]
0x14005a963  movups  xmm0, xmmword ptr cs:aUmfdhost; "UmfdHost"
0x14005a96a  mov     [rbp+57h+var_20], ax
0x14005a96e  mov     r9d, 13h
0x14005a974  lea     rax, [rbp+57h+var_60]
0x14005a978  mov     dword ptr [rbp+57h+dwBytes], ecx
0x14005a97b  mov     [r11-70h], rax
0x14005a97f  mov     r14d, ecx
0x14005a982  lea     rax, [rbp+57h+var_60]
0x14005a986  mov     dword ptr [rsp+0A0h+var_70], 30h ; '0'
0x14005a98e  mov     [r11-80h], rax
0x14005a992  lea     r8d, [r9-0Ah]
0x14005a996  xor     ecx, ecx
0x14005a998  mov     dword ptr [rsp+0A0h+var_80], 30h ; '0'
0x14005a9a0  mov     [rbp+57h+var_60], 0Eh
0x14005a9a8  mov     [rbp+57h+var_50], 100h
0x14005a9b0  mov     [rbp+57h+var_38], 0
0x14005a9b8  mov     dword ptr [rbp+57h+dwBytes+4], 0
0x14005a9bf  mov     [rbp+57h+var_48], 0
0x14005a9c7  mov     [rbp+57h+var_40], 0
0x14005a9cf  movups  [rbp+57h+var_30], xmm0
0x14005a9d3  call    cs:__imp_NtGdiExtEscape
0x14005a9d9  mov     esi, dword ptr [rbp+57h+dwBytes]
0x14005a9dc  test    esi, esi
0x14005a9de  jz      loc_14005AA95
0x14005a9e4  mov     edx, esi; dwBytes
0x14005a9e6  xor     ecx, ecx; uFlags
0x14005a9e8  call    cs:__imp_GlobalAlloc
0x14005a9ee  mov     rbx, rax
0x14005a9f1  test    rax, rax
0x14005a9f4  jz      loc_14005AA95
0x14005a9fa  movzx   ecx, word ptr cs:aUmfdhost+10h; ""
0x14005aa01  lea     rdx, [rbp+57h+var_30]
0x14005aa05  movups  xmm0, xmmword ptr cs:aUmfdhost; "UmfdHost"
0x14005aa0c  mov     [rbp+57h+var_48], rax
0x14005aa10  mov     r9d, 13h
0x14005aa16  lea     rax, [rbp+57h+var_60]
0x14005aa1a  mov     [rbp+57h+var_20], cx
0x14005aa1e  mov     [rsp+0A0h+var_68], rax
0x14005aa23  xor     ecx, ecx
0x14005aa25  lea     rax, [rbp+57h+var_60]
0x14005aa29  mov     dword ptr [rsp+0A0h+var_70], 30h ; '0'
0x14005aa31  mov     qword ptr [rsp+0A0h+var_78], rax
0x14005aa36  lea     r8d, [r9-0Ah]
0x14005aa3a  mov     dword ptr [rsp+0A0h+var_80], 30h ; '0'
0x14005aa42  mov     dword ptr [rbp+57h+var_60], 0Eh
0x14005aa49  mov     dword ptr [rbp+57h+dwBytes], r14d
0x14005aa4d  mov     dword ptr [rbp+57h+dwBytes+4], 0
0x14005aa54  mov     dword ptr [rbp+57h+var_50], 100h
0x14005aa5b  mov     [rbp+57h+var_40], rsi
0x14005aa5f  movups  [rbp+57h+var_30], xmm0
0x14005aa63  call    cs:__imp_NtGdiExtEscape
0x14005aa69  cmp     dword ptr [rbp+57h+dwBytes], esi
0x14005aa6c  jnz     short loc_14005AA99
0x14005aa6e  mov     rax, rbx
0x14005aa71  mov     rcx, [rbp+57h+var_18]
0x14005aa75  xor     rcx, rsp; StackCookie
0x14005aa78  call    __security_check_cookie
0x14005aa7d  lea     r11, [rsp+0A0h+var_10]
0x14005aa85  mov     rbx, [r11+28h]
0x14005aa89  mov     rsi, [r11+30h]
0x14005aa8d  mov     rsp, r11
0x14005aa90  pop     r14
0x14005aa92  pop     rdi
0x14005aa93  pop     rbp
0x14005aa94  retn
0x14005aa95  xor     eax, eax
0x14005aa97  jmp     short loc_14005AA71
0x14005aa99  mov     rcx, rbx; hMem
0x14005aa9c  call    cs:__imp_GlobalFree
0x14005aaa2  jmp     short loc_14005AA95
```
