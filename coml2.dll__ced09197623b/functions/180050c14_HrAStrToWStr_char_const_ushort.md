# HrAStrToWStr(char const *,ushort * *)

- ea: `0x180050c14`
- end: `0x180050cb7`
- name: `?HrAStrToWStr@@YAJPEBDPEAPEAG@Z`
- size: `163`
- prototype: `__int64 __fastcall(LPCCH lpMultiByteStr, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180050bb8`
- `0x1800514a0`
- `0x180052500`

## callees

- `0x180050c14`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050c90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050c90`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180050c45`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180050c7f`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180050c45`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180050c7f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180050c56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180050c56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050ca6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050ca6`

## pseudocode

```c
__int64 __fastcall HrAStrToWStr(LPCCH lpMultiByteStr, unsigned __int16 **a2)
{
  unsigned __int16 *v5; // rdi
  unsigned int v6; // eax
  int cchWideChar; // ebp
  WCHAR *lpWideCharStr; // rax
  DWORD v9; // ebx

  if ( !lpMultiByteStr )
  {
    *a2 = 0;
    return 0;
  }
  v5 = 0;
  v6 = MultiByteToWideChar(0, 0, lpMultiByteStr, -1, 0, 0);
  cchWideChar = v6;
  if ( !v6 )
    goto LABEL_8;
  lpWideCharStr = (WCHAR *)CoTaskMemAlloc(2LL * v6);
  v5 = lpWideCharStr;
  if ( lpWideCharStr )
  {
    if ( MultiByteToWideChar(0, 0, lpMultiByteStr, -1, lpWideCharStr, cchWideChar) )
    {
      v9 = 0;
      *a2 = v5;
      return v9;
    }
LABEL_8:
    v9 = GetLastError() | 0x80070000;
    if ( v5 )
      CoTaskMemFree(v5);
    return v9;
  }
  return (DWORD)-2147024882;
}

```

## disassembly

```asm
0x180050c14  push    rbx
0x180050c16  push    rbp
0x180050c17  push    rsi
0x180050c18  push    rdi
0x180050c19  sub     rsp, 38h
0x180050c1d  mov     rsi, rdx
0x180050c20  mov     rbx, rcx
0x180050c23  test    rcx, rcx
0x180050c26  jnz     short loc_180050C2F
0x180050c28  mov     [rdx], rcx
0x180050c2b  xor     eax, eax
0x180050c2d  jmp     short loc_180050CAE
0x180050c2f  xor     edi, edi
0x180050c31  or      r9d, 0FFFFFFFFh; cbMultiByte
0x180050c35  mov     [rsp+58h+cchWideChar], edi; cchWideChar
0x180050c39  mov     r8, rbx; lpMultiByteStr
0x180050c3c  xor     edx, edx; dwFlags
0x180050c3e  mov     [rsp+58h+lpWideCharStr], rdi; lpWideCharStr
0x180050c43  xor     ecx, ecx; CodePage
0x180050c45  call    cs:__imp_MultiByteToWideChar
0x180050c4b  mov     ebp, eax
0x180050c4d  test    eax, eax
0x180050c4f  jz      short loc_180050C90
0x180050c51  mov     ecx, ebp
0x180050c53  add     rcx, rcx; cb
0x180050c56  call    cs:__imp_CoTaskMemAlloc
0x180050c5c  mov     rdi, rax
0x180050c5f  test    rax, rax
0x180050c62  jnz     short loc_180050C6B
0x180050c64  mov     ebx, 8007000Eh
0x180050c69  jmp     short loc_180050CAC
0x180050c6b  mov     [rsp+58h+cchWideChar], ebp; cchWideChar
0x180050c6f  or      r9d, 0FFFFFFFFh; cbMultiByte
0x180050c73  mov     r8, rbx; lpMultiByteStr
0x180050c76  mov     [rsp+58h+lpWideCharStr], rdi; lpWideCharStr
0x180050c7b  xor     edx, edx; dwFlags
0x180050c7d  xor     ecx, ecx; CodePage
0x180050c7f  call    cs:__imp_MultiByteToWideChar
0x180050c85  test    eax, eax
0x180050c87  jz      short loc_180050C90
0x180050c89  xor     ebx, ebx
0x180050c8b  mov     [rsi], rdi
0x180050c8e  jmp     short loc_180050CAC
0x180050c90  call    cs:__imp_GetLastError
0x180050c96  mov     ebx, eax
0x180050c98  or      ebx, 80070000h
0x180050c9e  test    rdi, rdi
0x180050ca1  jz      short loc_180050CAC
0x180050ca3  mov     rcx, rdi; pv
0x180050ca6  call    cs:__imp_CoTaskMemFree
0x180050cac  mov     eax, ebx
0x180050cae  add     rsp, 38h
0x180050cb2  pop     rdi
0x180050cb3  pop     rsi
0x180050cb4  pop     rbp
0x180050cb5  pop     rbx
0x180050cb6  retn
```
