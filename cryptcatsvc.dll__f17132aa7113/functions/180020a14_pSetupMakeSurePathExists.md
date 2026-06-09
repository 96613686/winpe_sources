# pSetupMakeSurePathExists

- ea: `0x180020a14`
- end: `0x180020c14`
- name: `pSetupMakeSurePathExists`
- size: `512`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, installer_update`

## callers

- `0x180020384`
- `0x180021124`

## callees

- `0x18000be40`
- `0x180020a14`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180020b70`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180020b70`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180020aeb`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180020b01`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180020aeb`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180020b01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020a71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020a71`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180020a5f`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180020a5f`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180020bb3`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180020bb3`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180020b18`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180020b8c`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180020b18`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180020b8c`

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
    if ( p_Buffer != v3 && *p_Buffer == 92 )
    {
      while ( p_Buffer > v3 )
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
        p_Buffer = v8;
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
0x180020a14  mov     [rsp-8+arg_8], rbx
0x180020a19  mov     [rsp-8+arg_10], rsi
0x180020a1e  push    rbp
0x180020a1f  push    rdi
0x180020a20  push    r12
0x180020a22  push    r14
0x180020a24  push    r15
0x180020a26  lea     rbp, [rsp-150h]
0x180020a2e  sub     rsp, 250h
0x180020a35  mov     rax, cs:__security_cookie
0x180020a3c  xor     rax, rsp
0x180020a3f  mov     [rbp+170h+var_30], rax
0x180020a46  mov     ebx, 104h
0x180020a4b  lea     r9, [rsp+270h+FilePart]; lpFilePart
0x180020a50  xor     r15d, r15d
0x180020a53  lea     r8, [rsp+270h+Buffer]; lpBuffer
0x180020a58  mov     edx, ebx; nBufferLength
0x180020a5a  mov     [rsp+270h+FilePart], r15
0x180020a5f  call    cs:__imp_GetFullPathNameW
0x180020a65  cmp     eax, ebx
0x180020a67  jnb     loc_180020BE4
0x180020a6d  test    eax, eax
0x180020a6f  jnz     short loc_180020A7C
0x180020a71  call    cs:__imp_GetLastError
0x180020a77  jmp     loc_180020BE9
0x180020a7c  mov     rcx, [rsp+270h+FilePart]
0x180020a81  test    rcx, rcx
0x180020a84  jz      loc_180020BE4
0x180020a8a  lea     rax, [rsp+270h+Buffer]
0x180020a8f  cmp     rcx, rax
0x180020a92  jz      loc_180020BE4
0x180020a98  mov     [rcx], r15w
0x180020a9c  mov     rsi, r15
0x180020a9f  movzx   ecx, [rsp+270h+Buffer]
0x180020aa4  mov     r12d, 5Ch ; '\'
0x180020aaa  lea     eax, [rcx-41h]
0x180020aad  cmp     ax, 19h
0x180020ab1  jbe     short loc_180020ABC
0x180020ab3  lea     eax, [rcx-61h]
0x180020ab6  cmp     ax, 19h
0x180020aba  ja      short loc_180020AD5
0x180020abc  cmp     [rsp+270h+var_23E], 3Ah ; ':'
0x180020ac2  jnz     short loc_180020AD5
0x180020ac4  cmp     [rsp+270h+Str], r12w
0x180020aca  jnz     loc_180020BE4
0x180020ad0  lea     rsi, [rsp+270h+Str]
0x180020ad5  cmp     cx, r12w
0x180020ad9  jnz     short loc_180020B13
0x180020adb  cmp     [rsp+270h+var_23E], r12w
0x180020ae1  jnz     short loc_180020B13
0x180020ae3  mov     edx, r12d; Ch
0x180020ae6  lea     rcx, [rsp+270h+Str]; Str
0x180020aeb  call    cs:__imp_wcschr
0x180020af1  test    rax, rax
0x180020af4  jz      loc_180020BE4
0x180020afa  mov     edx, r12d; Ch
0x180020afd  lea     rcx, [rax+2]; Str
0x180020b01  call    cs:__imp_wcschr
0x180020b07  mov     rsi, rax
0x180020b0a  test    rax, rax
0x180020b0d  jz      loc_180020BE4
0x180020b13  lea     rcx, [rsp+270h+Buffer]; lpFileName
0x180020b18  call    cs:__imp_GetFileAttributesW
0x180020b1e  cmp     eax, 0FFFFFFFFh
0x180020b21  jz      short loc_180020B2E
0x180020b23  test    al, 10h
0x180020b25  jz      short loc_180020BA5
0x180020b27  xor     eax, eax
0x180020b29  jmp     loc_180020BE9
0x180020b2e  mov     rdi, [rsp+270h+FilePart]
0x180020b33  lea     rax, [rsp+270h+Buffer]
0x180020b38  cmp     rdi, rax
0x180020b3b  jnz     short loc_180020B44
0x180020b3d  lea     rdi, [rsp+270h+Buffer]
0x180020b42  jmp     short loc_180020B48
0x180020b44  add     rdi, 0FFFFFFFFFFFFFFFEh
0x180020b48  cmp     rdi, rsi
0x180020b4b  jz      loc_180020BE4
0x180020b51  cmp     [rdi], r12w
0x180020b55  jnz     loc_180020BE4
0x180020b5b  cmp     rdi, rsi
0x180020b5e  jbe     loc_180020BE4
0x180020b64  mov     edx, r12d; Ch
0x180020b67  mov     [rdi], r15w
0x180020b6b  lea     rcx, [rsp+270h+Buffer]; Str
0x180020b70  call    cs:__imp_wcsrchr
0x180020b76  mov     r14, rax
0x180020b79  test    rax, rax
0x180020b7c  jz      short loc_180020BE4
0x180020b7e  movzx   ebx, word ptr [rax+2]
0x180020b82  lea     rcx, [rsp+270h+Buffer]; lpFileName
0x180020b87  mov     [rax+2], r15w
0x180020b8c  call    cs:__imp_GetFileAttributesW
0x180020b92  mov     [r14+2], bx
0x180020b97  cmp     eax, 0FFFFFFFFh
0x180020b9a  jnz     short loc_180020BA1
0x180020b9c  mov     rdi, r14
0x180020b9f  jmp     short loc_180020B5B
0x180020ba1  test    al, 10h
0x180020ba3  jnz     short loc_180020BAC
0x180020ba5  mov     eax, 10Bh
0x180020baa  jmp     short loc_180020BE9
0x180020bac  xor     edx, edx; lpSecurityAttributes
0x180020bae  lea     rcx, [rsp+270h+Buffer]; lpPathName
0x180020bb3  call    cs:__imp_CreateDirectoryW
0x180020bb9  test    eax, eax
0x180020bbb  jz      loc_180020A71
0x180020bc1  cmp     [rdi+2], r15w
0x180020bc6  jz      loc_180020B27
0x180020bcc  mov     [rdi], r12w
0x180020bd0  or      rax, 0FFFFFFFFFFFFFFFFh
0x180020bd4  inc     rax
0x180020bd7  cmp     [rdi+rax*2], r15w
0x180020bdc  jnz     short loc_180020BD4
0x180020bde  lea     rdi, [rdi+rax*2]
0x180020be2  jmp     short loc_180020BAC
0x180020be4  mov     eax, 7Bh ; '{'
0x180020be9  mov     rcx, [rbp+170h+var_30]
0x180020bf0  xor     rcx, rsp; StackCookie
0x180020bf3  call    __security_check_cookie
0x180020bf8  lea     r11, [rsp+270h+var_20]
0x180020c00  mov     rbx, [r11+38h]
0x180020c04  mov     rsi, [r11+40h]
0x180020c08  mov     rsp, r11
0x180020c0b  pop     r15
0x180020c0d  pop     r14
0x180020c0f  pop     r12
0x180020c11  pop     rdi
0x180020c12  pop     rbp
0x180020c13  retn
```
