# CreateScalableFontResourceA

- ea: `0x180082980`
- end: `0x180082ab3`
- name: `CreateScalableFontResourceA`
- size: `307`
- prototype: `BOOL __stdcall(DWORD fdwHidden, LPCSTR lpszFont, LPCSTR lpszFile, LPCSTR lpszPath)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18007f800`
- `0x180082980`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x1800829be`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x1800829f4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x180082a2a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x1800829be`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x1800829f4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x180082a2a`
- `GDI32!CreateScalableFontResourceW` at `0x180082a75`
- `GDI32!CreateScalableFontResourceW` at `0x180082a75`
- `GDI32!GdiSetLastError` at `0x180082a88`
- `GDI32!GdiSetLastError` at `0x180082a88`
- `ntdll!RtlMultiByteToUnicodeN` at `0x1800829e5`
- `ntdll!RtlMultiByteToUnicodeN` at `0x180082a16`
- `ntdll!RtlMultiByteToUnicodeN` at `0x180082a49`
- `ntdll!RtlMultiByteToUnicodeN` at `0x1800829e5`
- `ntdll!RtlMultiByteToUnicodeN` at `0x180082a16`
- `ntdll!RtlMultiByteToUnicodeN` at `0x180082a49`

## pseudocode

```c
BOOL __stdcall CreateScalableFontResourceA(DWORD fdwHidden, LPCSTR lpszFont, LPCSTR lpszFile, LPCSTR lpszPath)
{
  int v8; // eax
  int v9; // eax
  int v10; // eax
  WCHAR szPath[264]; // [rsp+30h] [rbp-668h] BYREF
  WCHAR szFile[264]; // [rsp+240h] [rbp-458h] BYREF
  WCHAR UnicodeString[264]; // [rsp+450h] [rbp-248h] BYREF

  if ( lpszFile && lpszFont )
  {
    v8 = lstrlenA(lpszFont);
    RtlMultiByteToUnicodeN(UnicodeString, 0x208u, 0, lpszFont, v8 + 1);
    v9 = lstrlenA(lpszFile);
    RtlMultiByteToUnicodeN(szFile, 0x208u, 0, lpszFile, v9 + 1);
    if ( lpszPath )
    {
      v10 = lstrlenA(lpszPath);
      RtlMultiByteToUnicodeN(szPath, 0x208u, 0, lpszPath, v10 + 1);
    }
    else
    {
      szPath[0] = 0;
    }
    return CreateScalableFontResourceW(fdwHidden, UnicodeString, szFile, szPath);
  }
  else
  {
    GdiSetLastError(87);
    return 0;
  }
}

```

## disassembly

```asm
0x180082980  push    rbx
0x180082982  push    rbp
0x180082983  push    rsi
0x180082984  push    rdi
0x180082985  sub     rsp, 678h
0x18008298c  mov     rax, cs:__security_cookie
0x180082993  xor     rax, rsp
0x180082996  mov     [rsp+698h+var_38], rax
0x18008299e  mov     rbx, r9
0x1800829a1  mov     rsi, r8
0x1800829a4  mov     rdi, rdx
0x1800829a7  mov     ebp, ecx
0x1800829a9  test    r8, r8
0x1800829ac  jz      loc_180082A83
0x1800829b2  test    rdx, rdx
0x1800829b5  jz      loc_180082A83
0x1800829bb  mov     rcx, rdx; lpString
0x1800829be  call    cs:__imp_lstrlenA
0x1800829c5  nop     dword ptr [rax+rax+00h]
0x1800829ca  mov     r9, rdi; MultiByteString
0x1800829cd  lea     rcx, [rsp+698h+UnicodeString]; UnicodeString
0x1800829d5  inc     eax
0x1800829d7  mov     edi, 208h
0x1800829dc  mov     edx, edi; MaxBytesInUnicodeString
0x1800829de  mov     [rsp+698h+BytesInMultiByteString], eax; BytesInMultiByteString
0x1800829e2  xor     r8d, r8d; BytesInUnicodeString
0x1800829e5  call    cs:__imp_RtlMultiByteToUnicodeN
0x1800829ec  nop     dword ptr [rax+rax+00h]
0x1800829f1  mov     rcx, rsi; lpString
0x1800829f4  call    cs:__imp_lstrlenA
0x1800829fb  nop     dword ptr [rax+rax+00h]
0x180082a00  mov     r9, rsi; MultiByteString
0x180082a03  lea     rcx, [rsp+698h+szFile]; UnicodeString
0x180082a0b  inc     eax
0x180082a0d  xor     r8d, r8d; BytesInUnicodeString
0x180082a10  mov     edx, edi; MaxBytesInUnicodeString
0x180082a12  mov     [rsp+698h+BytesInMultiByteString], eax; BytesInMultiByteString
0x180082a16  call    cs:__imp_RtlMultiByteToUnicodeN
0x180082a1d  nop     dword ptr [rax+rax+00h]
0x180082a22  test    rbx, rbx
0x180082a25  jz      short loc_180082A57
0x180082a27  mov     rcx, rbx; lpString
0x180082a2a  call    cs:__imp_lstrlenA
0x180082a31  nop     dword ptr [rax+rax+00h]
0x180082a36  mov     r9, rbx; MultiByteString
0x180082a39  lea     rcx, [rsp+698h+szPath]; UnicodeString
0x180082a3e  inc     eax
0x180082a40  xor     r8d, r8d; BytesInUnicodeString
0x180082a43  mov     edx, edi; MaxBytesInUnicodeString
0x180082a45  mov     [rsp+698h+BytesInMultiByteString], eax; BytesInMultiByteString
0x180082a49  call    cs:__imp_RtlMultiByteToUnicodeN
0x180082a50  nop     dword ptr [rax+rax+00h]
0x180082a55  jmp     short loc_180082A5E
0x180082a57  xor     eax, eax
0x180082a59  mov     [rsp+698h+szPath], ax
0x180082a5e  lea     r9, [rsp+698h+szPath]; lpszPath
0x180082a63  mov     ecx, ebp; fdwHidden
0x180082a65  lea     r8, [rsp+698h+szFile]; lpszFile
0x180082a6d  lea     rdx, [rsp+698h+UnicodeString]; lpszFont
0x180082a75  call    cs:__imp_CreateScalableFontResourceW
0x180082a7c  nop     dword ptr [rax+rax+00h]
0x180082a81  jmp     short loc_180082A96
0x180082a83  mov     ecx, 57h ; 'W'
0x180082a88  call    cs:__imp_GdiSetLastError
0x180082a8f  nop     dword ptr [rax+rax+00h]
0x180082a94  xor     eax, eax
0x180082a96  mov     rcx, [rsp+698h+var_38]
0x180082a9e  xor     rcx, rsp; StackCookie
0x180082aa1  call    __security_check_cookie
0x180082aa6  add     rsp, 678h
0x180082aad  pop     rdi
0x180082aae  pop     rsi
0x180082aaf  pop     rbp
0x180082ab0  pop     rbx
0x180082ab1  retn
```
