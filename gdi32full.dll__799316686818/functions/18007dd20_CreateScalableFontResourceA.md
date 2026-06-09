# CreateScalableFontResourceA

- ea: `0x18007dd20`
- end: `0x18007de22`
- name: `CreateScalableFontResourceA`
- size: `258`
- prototype: `BOOL __stdcall(DWORD fdwHidden, LPCSTR lpszFont, LPCSTR lpszFile, LPCSTR lpszPath)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18007ac50`
- `0x18007dd20`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x18007dd5e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x18007dd88`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x18007ddb2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x18007dd5e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x18007dd88`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x18007ddb2`
- `GDI32!CreateScalableFontResourceW` at `0x18007ddf1`
- `GDI32!CreateScalableFontResourceW` at `0x18007ddf1`
- `GDI32!GdiSetLastError` at `0x18007ddfe`
- `GDI32!GdiSetLastError` at `0x18007ddfe`
- `ntdll!RtlMultiByteToUnicodeN` at `0x18007dd7f`
- `ntdll!RtlMultiByteToUnicodeN` at `0x18007dda4`
- `ntdll!RtlMultiByteToUnicodeN` at `0x18007ddcb`
- `ntdll!RtlMultiByteToUnicodeN` at `0x18007dd7f`
- `ntdll!RtlMultiByteToUnicodeN` at `0x18007dda4`
- `ntdll!RtlMultiByteToUnicodeN` at `0x18007ddcb`

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
0x18007dd20  push    rbx
0x18007dd22  push    rbp
0x18007dd23  push    rsi
0x18007dd24  push    rdi
0x18007dd25  sub     rsp, 678h
0x18007dd2c  mov     rax, cs:__security_cookie
0x18007dd33  xor     rax, rsp
0x18007dd36  mov     [rsp+698h+var_38], rax
0x18007dd3e  mov     rbx, r9
0x18007dd41  mov     rsi, r8
0x18007dd44  mov     rdi, rdx
0x18007dd47  mov     ebp, ecx
0x18007dd49  test    r8, r8
0x18007dd4c  jz      loc_18007DDF9
0x18007dd52  test    rdx, rdx
0x18007dd55  jz      loc_18007DDF9
0x18007dd5b  mov     rcx, rdx; lpString
0x18007dd5e  call    cs:__imp_lstrlenA
0x18007dd64  mov     r9, rdi; MultiByteString
0x18007dd67  lea     rcx, [rsp+698h+UnicodeString]; UnicodeString
0x18007dd6f  inc     eax
0x18007dd71  mov     edi, 208h
0x18007dd76  mov     edx, edi; MaxBytesInUnicodeString
0x18007dd78  mov     [rsp+698h+BytesInMultiByteString], eax; BytesInMultiByteString
0x18007dd7c  xor     r8d, r8d; BytesInUnicodeString
0x18007dd7f  call    cs:__imp_RtlMultiByteToUnicodeN
0x18007dd85  mov     rcx, rsi; lpString
0x18007dd88  call    cs:__imp_lstrlenA
0x18007dd8e  mov     r9, rsi; MultiByteString
0x18007dd91  lea     rcx, [rsp+698h+szFile]; UnicodeString
0x18007dd99  inc     eax
0x18007dd9b  xor     r8d, r8d; BytesInUnicodeString
0x18007dd9e  mov     edx, edi; MaxBytesInUnicodeString
0x18007dda0  mov     [rsp+698h+BytesInMultiByteString], eax; BytesInMultiByteString
0x18007dda4  call    cs:__imp_RtlMultiByteToUnicodeN
0x18007ddaa  test    rbx, rbx
0x18007ddad  jz      short loc_18007DDD3
0x18007ddaf  mov     rcx, rbx; lpString
0x18007ddb2  call    cs:__imp_lstrlenA
0x18007ddb8  mov     r9, rbx; MultiByteString
0x18007ddbb  lea     rcx, [rsp+698h+szPath]; UnicodeString
0x18007ddc0  inc     eax
0x18007ddc2  xor     r8d, r8d; BytesInUnicodeString
0x18007ddc5  mov     edx, edi; MaxBytesInUnicodeString
0x18007ddc7  mov     [rsp+698h+BytesInMultiByteString], eax; BytesInMultiByteString
0x18007ddcb  call    cs:__imp_RtlMultiByteToUnicodeN
0x18007ddd1  jmp     short loc_18007DDDA
0x18007ddd3  xor     eax, eax
0x18007ddd5  mov     [rsp+698h+szPath], ax
0x18007ddda  lea     r9, [rsp+698h+szPath]; lpszPath
0x18007dddf  mov     ecx, ebp; fdwHidden
0x18007dde1  lea     r8, [rsp+698h+szFile]; lpszFile
0x18007dde9  lea     rdx, [rsp+698h+UnicodeString]; lpszFont
0x18007ddf1  call    cs:__imp_CreateScalableFontResourceW
0x18007ddf7  jmp     short loc_18007DE06
0x18007ddf9  mov     ecx, 57h ; 'W'
0x18007ddfe  call    cs:__imp_GdiSetLastError
0x18007de04  xor     eax, eax
0x18007de06  mov     rcx, [rsp+698h+var_38]
0x18007de0e  xor     rcx, rsp; StackCookie
0x18007de11  call    __security_check_cookie
0x18007de16  add     rsp, 678h
0x18007de1d  pop     rdi
0x18007de1e  pop     rsi
0x18007de1f  pop     rbp
0x18007de20  pop     rbx
0x18007de21  retn
```
