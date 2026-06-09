# pSetupMakeSurePathExists

- ea: `0x18007e33c`
- end: `0x18007e53c`
- name: `pSetupMakeSurePathExists`
- size: `512`
- prototype: `DWORD __fastcall(const WCHAR *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, installer_update`

## callers

- `0x18007db84`
- `0x18007e544`

## callees

- `0x18003bc80`
- `0x18007e33c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18007e498`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18007e498`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18007e413`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18007e429`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18007e413`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18007e429`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e399`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e399`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18007e387`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18007e387`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18007e440`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18007e4b4`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18007e440`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18007e4b4`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18007e4db`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18007e4db`

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
0x18007e33c  mov     [rsp-8+arg_8], rbx
0x18007e341  mov     [rsp-8+arg_10], rsi
0x18007e346  push    rbp
0x18007e347  push    rdi
0x18007e348  push    r12
0x18007e34a  push    r14
0x18007e34c  push    r15
0x18007e34e  lea     rbp, [rsp-150h]
0x18007e356  sub     rsp, 250h
0x18007e35d  mov     rax, cs:__security_cookie
0x18007e364  xor     rax, rsp
0x18007e367  mov     [rbp+170h+var_30], rax
0x18007e36e  mov     ebx, 104h
0x18007e373  lea     r9, [rsp+270h+FilePart]; lpFilePart
0x18007e378  xor     r15d, r15d
0x18007e37b  lea     r8, [rsp+270h+Buffer]; lpBuffer
0x18007e380  mov     edx, ebx; nBufferLength
0x18007e382  mov     [rsp+270h+FilePart], r15
0x18007e387  call    cs:__imp_GetFullPathNameW
0x18007e38d  cmp     eax, ebx
0x18007e38f  jnb     loc_18007E50C
0x18007e395  test    eax, eax
0x18007e397  jnz     short loc_18007E3A4
0x18007e399  call    cs:__imp_GetLastError
0x18007e39f  jmp     loc_18007E511
0x18007e3a4  mov     rcx, [rsp+270h+FilePart]
0x18007e3a9  test    rcx, rcx
0x18007e3ac  jz      loc_18007E50C
0x18007e3b2  lea     rax, [rsp+270h+Buffer]
0x18007e3b7  cmp     rcx, rax
0x18007e3ba  jz      loc_18007E50C
0x18007e3c0  mov     [rcx], r15w
0x18007e3c4  mov     rsi, r15
0x18007e3c7  movzx   ecx, [rsp+270h+Buffer]
0x18007e3cc  mov     r12d, 5Ch ; '\'
0x18007e3d2  lea     eax, [rcx-41h]
0x18007e3d5  cmp     ax, 19h
0x18007e3d9  jbe     short loc_18007E3E4
0x18007e3db  lea     eax, [rcx-61h]
0x18007e3de  cmp     ax, 19h
0x18007e3e2  ja      short loc_18007E3FD
0x18007e3e4  cmp     [rsp+270h+var_23E], 3Ah ; ':'
0x18007e3ea  jnz     short loc_18007E3FD
0x18007e3ec  cmp     [rsp+270h+Str], r12w
0x18007e3f2  jnz     loc_18007E50C
0x18007e3f8  lea     rsi, [rsp+270h+Str]
0x18007e3fd  cmp     cx, r12w
0x18007e401  jnz     short loc_18007E43B
0x18007e403  cmp     [rsp+270h+var_23E], r12w
0x18007e409  jnz     short loc_18007E43B
0x18007e40b  mov     edx, r12d; Ch
0x18007e40e  lea     rcx, [rsp+270h+Str]; Str
0x18007e413  call    cs:__imp_wcschr
0x18007e419  test    rax, rax
0x18007e41c  jz      loc_18007E50C
0x18007e422  mov     edx, r12d; Ch
0x18007e425  lea     rcx, [rax+2]; Str
0x18007e429  call    cs:__imp_wcschr
0x18007e42f  mov     rsi, rax
0x18007e432  test    rax, rax
0x18007e435  jz      loc_18007E50C
0x18007e43b  lea     rcx, [rsp+270h+Buffer]; lpFileName
0x18007e440  call    cs:__imp_GetFileAttributesW
0x18007e446  cmp     eax, 0FFFFFFFFh
0x18007e449  jz      short loc_18007E456
0x18007e44b  test    al, 10h
0x18007e44d  jz      short loc_18007E4CD
0x18007e44f  xor     eax, eax
0x18007e451  jmp     loc_18007E511
0x18007e456  mov     rdi, [rsp+270h+FilePart]
0x18007e45b  lea     rax, [rsp+270h+Buffer]
0x18007e460  cmp     rdi, rax
0x18007e463  jnz     short loc_18007E46C
0x18007e465  lea     rdi, [rsp+270h+Buffer]
0x18007e46a  jmp     short loc_18007E470
0x18007e46c  add     rdi, 0FFFFFFFFFFFFFFFEh
0x18007e470  cmp     rdi, rsi
0x18007e473  jz      loc_18007E50C
0x18007e479  cmp     [rdi], r12w
0x18007e47d  jnz     loc_18007E50C
0x18007e483  cmp     rdi, rsi
0x18007e486  jbe     loc_18007E50C
0x18007e48c  mov     edx, r12d; Ch
0x18007e48f  mov     [rdi], r15w
0x18007e493  lea     rcx, [rsp+270h+Buffer]; Str
0x18007e498  call    cs:__imp_wcsrchr
0x18007e49e  mov     r14, rax
0x18007e4a1  test    rax, rax
0x18007e4a4  jz      short loc_18007E50C
0x18007e4a6  movzx   ebx, word ptr [rax+2]
0x18007e4aa  lea     rcx, [rsp+270h+Buffer]; lpFileName
0x18007e4af  mov     [rax+2], r15w
0x18007e4b4  call    cs:__imp_GetFileAttributesW
0x18007e4ba  mov     [r14+2], bx
0x18007e4bf  cmp     eax, 0FFFFFFFFh
0x18007e4c2  jnz     short loc_18007E4C9
0x18007e4c4  mov     rdi, r14
0x18007e4c7  jmp     short loc_18007E483
0x18007e4c9  test    al, 10h
0x18007e4cb  jnz     short loc_18007E4D4
0x18007e4cd  mov     eax, 10Bh
0x18007e4d2  jmp     short loc_18007E511
0x18007e4d4  xor     edx, edx; lpSecurityAttributes
0x18007e4d6  lea     rcx, [rsp+270h+Buffer]; lpPathName
0x18007e4db  call    cs:__imp_CreateDirectoryW
0x18007e4e1  test    eax, eax
0x18007e4e3  jz      loc_18007E399
0x18007e4e9  cmp     [rdi+2], r15w
0x18007e4ee  jz      loc_18007E44F
0x18007e4f4  mov     [rdi], r12w
0x18007e4f8  or      rax, 0FFFFFFFFFFFFFFFFh
0x18007e4fc  inc     rax
0x18007e4ff  cmp     [rdi+rax*2], r15w
0x18007e504  jnz     short loc_18007E4FC
0x18007e506  lea     rdi, [rdi+rax*2]
0x18007e50a  jmp     short loc_18007E4D4
0x18007e50c  mov     eax, 7Bh ; '{'
0x18007e511  mov     rcx, [rbp+170h+var_30]
0x18007e518  xor     rcx, rsp; StackCookie
0x18007e51b  call    __security_check_cookie
0x18007e520  lea     r11, [rsp+270h+var_20]
0x18007e528  mov     rbx, [r11+38h]
0x18007e52c  mov     rsi, [r11+40h]
0x18007e530  mov     rsp, r11
0x18007e533  pop     r15
0x18007e535  pop     r14
0x18007e537  pop     r12
0x18007e539  pop     rdi
0x18007e53a  pop     rbp
0x18007e53b  retn
```
