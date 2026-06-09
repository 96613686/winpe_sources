# pSetupMakeSurePathExists

- ea: `0x180007cd0`
- end: `0x180007ece`
- name: `pSetupMakeSurePathExists`
- size: `510`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, installer_update`

## callers

- `0x180006100`
- `0x1800077d0`

## callees

- `0x180007cd0`
- `0x18000a1a0`

## import_xrefs

- `msvcrt!wcsrchr` at `0x180007e21`
- `msvcrt!wcsrchr` at `0x180007e21`
- `msvcrt!wcschr` at `0x180007da7`
- `msvcrt!wcschr` at `0x180007dbd`
- `msvcrt!wcschr` at `0x180007da7`
- `msvcrt!wcschr` at `0x180007dbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007d2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007d2d`
- `KERNEL32!CreateDirectoryW` at `0x180007ebf`
- `KERNEL32!CreateDirectoryW` at `0x180007ebf`
- `KERNEL32!GetFileAttributesW` at `0x180007dd4`
- `KERNEL32!GetFileAttributesW` at `0x180007e3d`
- `KERNEL32!GetFileAttributesW` at `0x180007dd4`
- `KERNEL32!GetFileAttributesW` at `0x180007e3d`
- `KERNEL32!GetFullPathNameW` at `0x180007d1b`
- `KERNEL32!GetFullPathNameW` at `0x180007d1b`

## pseudocode

```c
DWORD __fastcall pSetupMakeSurePathExists(const WCHAR *a1)
{
  DWORD FullPathNameW; // eax
  wchar_t *v3; // rsi
  wchar_t *v4; // rax
  DWORD FileAttributesW; // eax
  WCHAR *p_Buffer; // rdi
  wchar_t *v7; // rax
  wchar_t *v8; // r14
  wchar_t v9; // bx
  DWORD v10; // eax
  __int64 v11; // rax
  LPWSTR FilePart; // [rsp+20h] [rbp-E0h] BYREF
  WCHAR Buffer; // [rsp+30h] [rbp-D0h] BYREF
  __int16 v14; // [rsp+32h] [rbp-CEh]
  wchar_t Str[262]; // [rsp+34h] [rbp-CCh] BYREF

  FilePart = 0;
  FullPathNameW = GetFullPathNameW(a1, 0x104u, &Buffer, &FilePart);
  if ( FullPathNameW >= 0x104 )
    return 123;
  if ( !FullPathNameW )
    return GetLastError();
  if ( !FilePart || FilePart == &Buffer )
    return 123;
  *FilePart = 0;
  v3 = 0;
  if ( ((unsigned __int16)(Buffer - 65) <= 0x19u || (unsigned __int16)(Buffer - 97) <= 0x19u) && v14 == 58 )
  {
    if ( Str[0] != 92 )
      return 123;
    v3 = Str;
  }
  if ( Buffer == 92 && v14 == 92 )
  {
    v4 = wcschr(Str, 0x5Cu);
    if ( !v4 )
      return 123;
    v3 = wcschr(v4 + 1, 0x5Cu);
    if ( !v3 )
      return 123;
  }
  FileAttributesW = GetFileAttributesW(&Buffer);
  if ( FileAttributesW == -1 )
  {
    if ( FilePart == &Buffer )
      p_Buffer = &Buffer;
    else
      p_Buffer = FilePart - 1;
    if ( p_Buffer != v3 && *p_Buffer == 92 && p_Buffer > v3 )
    {
      while ( 1 )
      {
        *p_Buffer = 0;
        v7 = wcsrchr(&Buffer, 0x5Cu);
        v8 = v7;
        if ( !v7 )
          break;
        v9 = v7[1];
        v7[1] = 0;
        v10 = GetFileAttributesW(&Buffer);
        v8[1] = v9;
        if ( v10 != -1 )
        {
          if ( (v10 & 0x10) == 0 )
            return 267;
          if ( p_Buffer > v3 )
          {
            while ( CreateDirectoryW(&Buffer, 0) )
            {
              if ( !p_Buffer[1] )
                return 0;
              *p_Buffer = 92;
              v11 = -1;
              do
                ++v11;
              while ( p_Buffer[v11] );
              p_Buffer += v11;
            }
            return GetLastError();
          }
          return 123;
        }
        p_Buffer = v8;
        if ( v8 <= v3 )
          return 123;
      }
    }
    return 123;
  }
  if ( (FileAttributesW & 0x10) != 0 )
    return 0;
  else
    return 267;
}

```

## disassembly

```asm
0x180007cd0  mov     [rsp-8+arg_8], rbx
0x180007cd5  mov     [rsp-8+arg_10], rsi
0x180007cda  push    rbp
0x180007cdb  push    rdi
0x180007cdc  push    r12
0x180007cde  push    r14
0x180007ce0  push    r15
0x180007ce2  lea     rbp, [rsp-150h]
0x180007cea  sub     rsp, 250h
0x180007cf1  mov     rax, cs:__security_cookie
0x180007cf8  xor     rax, rsp
0x180007cfb  mov     [rbp+170h+var_30], rax
0x180007d02  mov     ebx, 104h
0x180007d07  lea     r9, [rsp+270h+FilePart]; lpFilePart
0x180007d0c  xor     r15d, r15d
0x180007d0f  lea     r8, [rsp+270h+Buffer]; lpBuffer
0x180007d14  mov     edx, ebx; nBufferLength
0x180007d16  mov     [rsp+270h+FilePart], r15
0x180007d1b  call    cs:__imp_GetFullPathNameW
0x180007d21  cmp     eax, ebx
0x180007d23  jnb     loc_180007E55
0x180007d29  test    eax, eax
0x180007d2b  jnz     short loc_180007D38
0x180007d2d  call    cs:__imp_GetLastError
0x180007d33  jmp     loc_180007E5A
0x180007d38  mov     rcx, [rsp+270h+FilePart]
0x180007d3d  test    rcx, rcx
0x180007d40  jz      loc_180007E55
0x180007d46  lea     rax, [rsp+270h+Buffer]
0x180007d4b  cmp     rcx, rax
0x180007d4e  jz      loc_180007E55
0x180007d54  mov     [rcx], r15w
0x180007d58  mov     rsi, r15
0x180007d5b  movzx   ecx, [rsp+270h+Buffer]
0x180007d60  mov     r12d, 5Ch ; '\'
0x180007d66  lea     eax, [rcx-41h]
0x180007d69  cmp     ax, 19h
0x180007d6d  jbe     short loc_180007D78
0x180007d6f  lea     eax, [rcx-61h]
0x180007d72  cmp     ax, 19h
0x180007d76  ja      short loc_180007D91
0x180007d78  cmp     [rsp+270h+var_23E], 3Ah ; ':'
0x180007d7e  jnz     short loc_180007D91
0x180007d80  cmp     [rsp+270h+Str], r12w
0x180007d86  jnz     loc_180007E55
0x180007d8c  lea     rsi, [rsp+270h+Str]
0x180007d91  cmp     cx, r12w
0x180007d95  jnz     short loc_180007DCF
0x180007d97  cmp     [rsp+270h+var_23E], r12w
0x180007d9d  jnz     short loc_180007DCF
0x180007d9f  mov     edx, r12d; Ch
0x180007da2  lea     rcx, [rsp+270h+Str]; Str
0x180007da7  call    cs:__imp_wcschr
0x180007dad  test    rax, rax
0x180007db0  jz      loc_180007E55
0x180007db6  mov     edx, r12d; Ch
0x180007db9  lea     rcx, [rax+2]; Str
0x180007dbd  call    cs:__imp_wcschr
0x180007dc3  mov     rsi, rax
0x180007dc6  test    rax, rax
0x180007dc9  jz      loc_180007E55
0x180007dcf  lea     rcx, [rsp+270h+Buffer]; lpFileName
0x180007dd4  call    cs:__imp_GetFileAttributesW
0x180007dda  cmp     eax, 0FFFFFFFFh
0x180007ddd  jz      short loc_180007DEB
0x180007ddf  test    al, 10h
0x180007de1  jz      loc_180007E89
0x180007de7  xor     eax, eax
0x180007de9  jmp     short loc_180007E5A
0x180007deb  mov     rdi, [rsp+270h+FilePart]
0x180007df0  lea     rax, [rsp+270h+Buffer]
0x180007df5  cmp     rdi, rax
0x180007df8  jnz     short loc_180007E01
0x180007dfa  lea     rdi, [rsp+270h+Buffer]
0x180007dff  jmp     short loc_180007E05
0x180007e01  add     rdi, 0FFFFFFFFFFFFFFFEh
0x180007e05  cmp     rdi, rsi
0x180007e08  jz      short loc_180007E55
0x180007e0a  cmp     [rdi], r12w
0x180007e0e  jnz     short loc_180007E55
0x180007e10  cmp     rdi, rsi
0x180007e13  jbe     short loc_180007E55
0x180007e15  mov     edx, r12d; Ch
0x180007e18  mov     [rdi], r15w
0x180007e1c  lea     rcx, [rsp+270h+Buffer]; Str
0x180007e21  call    cs:__imp_wcsrchr
0x180007e27  mov     r14, rax
0x180007e2a  test    rax, rax
0x180007e2d  jz      short loc_180007E55
0x180007e2f  movzx   ebx, word ptr [rax+2]
0x180007e33  lea     rcx, [rsp+270h+Buffer]; lpFileName
0x180007e38  mov     [rax+2], r15w
0x180007e3d  call    cs:__imp_GetFileAttributesW
0x180007e43  mov     [r14+2], bx
0x180007e48  cmp     eax, 0FFFFFFFFh
0x180007e4b  jnz     short loc_180007E85
0x180007e4d  mov     rdi, r14
0x180007e50  cmp     r14, rsi
0x180007e53  ja      short loc_180007E15
0x180007e55  mov     eax, 7Bh ; '{'
0x180007e5a  mov     rcx, [rbp+170h+var_30]
0x180007e61  xor     rcx, rsp; StackCookie
0x180007e64  call    __security_check_cookie
0x180007e69  lea     r11, [rsp+270h+var_20]
0x180007e71  mov     rbx, [r11+38h]
0x180007e75  mov     rsi, [r11+40h]
0x180007e79  mov     rsp, r11
0x180007e7c  pop     r15
0x180007e7e  pop     r14
0x180007e80  pop     r12
0x180007e82  pop     rdi
0x180007e83  pop     rbp
0x180007e84  retn
0x180007e85  test    al, 10h
0x180007e87  jnz     short loc_180007E90
0x180007e89  mov     eax, 10Bh
0x180007e8e  jmp     short loc_180007E5A
0x180007e90  cmp     rdi, rsi
0x180007e93  jbe     short loc_180007E55
0x180007e95  jmp     short loc_180007EB8
0x180007e97  cmp     [rdi+2], r15w
0x180007e9c  jz      loc_180007DE7
0x180007ea2  mov     [rdi], r12w
0x180007ea6  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007eaa  inc     rax
0x180007ead  cmp     [rdi+rax*2], r15w
0x180007eb2  jnz     short loc_180007EAA
0x180007eb4  lea     rdi, [rdi+rax*2]
0x180007eb8  xor     edx, edx; lpSecurityAttributes
0x180007eba  lea     rcx, [rsp+270h+Buffer]; lpPathName
0x180007ebf  call    cs:__imp_CreateDirectoryW
0x180007ec5  test    eax, eax
0x180007ec7  jnz     short loc_180007E97
0x180007ec9  jmp     loc_180007D2D
```
