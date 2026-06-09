# DRR_CreateDirectory

- ea: `0x18000cebc`
- end: `0x18000cfe0`
- name: `DRR_CreateDirectory`
- size: `292`
- prototype: `__int64 __fastcall(void *Src, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180003ad0`

## callees

- `0x18000cebc`
- `0x18000d892`
- `0x18000d8d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cf50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cf89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cf50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cf89`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000cf46`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000cf7f`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000cf46`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000cf7f`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000cfa2`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000cfa2`

## pseudocode

```c
__int64 __fastcall DRR_CreateDirectory(void *Src, __int64 a2)
{
  WCHAR *v3; // rbx
  WCHAR *v4; // rsi
  DWORD v5; // edi
  DWORD LastError; // eax
  WCHAR v8[2]; // [rsp+1Ch] [rbp-23Ch] BYREF
  WCHAR PathName[264]; // [rsp+20h] [rbp-238h] BYREF

  if ( (unsigned __int64)(a2 - 3) > 0x100 )
  {
    return 87;
  }
  else
  {
    memcpy_0(PathName, Src, 2 * a2 + 2);
    v3 = &v8[a2];
    v4 = 0;
    v5 = 3;
    while ( 1 )
    {
      while ( *v3 != 92 )
      {
        if ( --v3 <= PathName )
          return v5;
      }
      *v3 = 0;
      if ( !v4 )
        v4 = v3;
      if ( CreateDirectoryW(PathName, 0) )
        break;
      LastError = GetLastError();
      if ( LastError == 183 )
        break;
      if ( LastError != 3 )
        return LastError;
      --v3;
    }
    while ( 1 )
    {
      SetFileAttributesW(PathName, 4u);
      if ( v3 >= v4 )
        break;
      *v3 = 92;
      do
        ++v3;
      while ( *v3 );
      if ( !CreateDirectoryW(PathName, 0) )
      {
        v5 = GetLastError();
        if ( v5 != 183 )
          return v5;
      }
    }
    return 0;
  }
}

```

## disassembly

```asm
0x18000cebc  mov     [rsp+arg_10], rbx
0x18000cec1  mov     [rsp+arg_18], rbp
0x18000cec6  push    rsi
0x18000cec7  push    rdi
0x18000cec8  push    r14
0x18000ceca  sub     rsp, 240h
0x18000ced1  mov     rax, cs:__security_cookie
0x18000ced8  xor     rax, rsp
0x18000cedb  mov     [rsp+258h+var_28], rax
0x18000cee3  lea     rax, [rdx-3]
0x18000cee7  mov     rbx, rdx
0x18000ceea  cmp     rax, 100h
0x18000cef0  ja      loc_18000CFB1
0x18000cef6  lea     r8, ds:2[rdx*2]; Size
0x18000cefe  mov     rdx, rcx; Src
0x18000cf01  lea     rcx, [rsp+258h+PathName]; void *
0x18000cf06  call    memcpy_0
0x18000cf0b  xor     ebp, ebp
0x18000cf0d  lea     rbx, [rsp+rbx*2+258h+var_23C]
0x18000cf12  mov     esi, ebp
0x18000cf14  lea     edi, [rbp+3]
0x18000cf17  lea     r14d, [rbp+5Ch]
0x18000cf1b  jmp     short loc_18000CF2F
0x18000cf1d  sub     rbx, 2
0x18000cf21  lea     rax, [rsp+258h+PathName]
0x18000cf26  cmp     rbx, rax
0x18000cf29  jbe     loc_18000CFB6
0x18000cf2f  cmp     [rbx], r14w
0x18000cf33  jnz     short loc_18000CF1D
0x18000cf35  test    rsi, rsi
0x18000cf38  mov     [rbx], bp
0x18000cf3b  lea     rcx, [rsp+258h+PathName]; lpPathName
0x18000cf40  cmovz   rsi, rbx
0x18000cf44  xor     edx, edx; lpSecurityAttributes
0x18000cf46  call    cs:__imp_CreateDirectoryW
0x18000cf4c  test    eax, eax
0x18000cf4e  jnz     short loc_18000CF98
0x18000cf50  call    cs:__imp_GetLastError
0x18000cf56  cmp     eax, 0B7h
0x18000cf5b  jz      short loc_18000CF98
0x18000cf5d  cmp     eax, edi
0x18000cf5f  jnz     short loc_18000CF67
0x18000cf61  sub     rbx, 2
0x18000cf65  jmp     short loc_18000CF2F
0x18000cf67  mov     edi, eax
0x18000cf69  jmp     short loc_18000CFB6
0x18000cf6b  mov     [rbx], r14w
0x18000cf6f  add     rbx, 2
0x18000cf73  cmp     [rbx], bp
0x18000cf76  jnz     short loc_18000CF6F
0x18000cf78  xor     edx, edx; lpSecurityAttributes
0x18000cf7a  lea     rcx, [rsp+258h+PathName]; lpPathName
0x18000cf7f  call    cs:__imp_CreateDirectoryW
0x18000cf85  test    eax, eax
0x18000cf87  jnz     short loc_18000CF98
0x18000cf89  call    cs:__imp_GetLastError
0x18000cf8f  mov     edi, eax
0x18000cf91  cmp     eax, 0B7h
0x18000cf96  jnz     short loc_18000CFB6
0x18000cf98  mov     edx, 4; dwFileAttributes
0x18000cf9d  lea     rcx, [rsp+258h+PathName]; lpFileName
0x18000cfa2  call    cs:__imp_SetFileAttributesW
0x18000cfa8  cmp     rbx, rsi
0x18000cfab  jb      short loc_18000CF6B
0x18000cfad  mov     edi, ebp
0x18000cfaf  jmp     short loc_18000CFB6
0x18000cfb1  mov     edi, 57h ; 'W'
0x18000cfb6  mov     eax, edi
0x18000cfb8  mov     rcx, [rsp+258h+var_28]
0x18000cfc0  xor     rcx, rsp; StackCookie
0x18000cfc3  call    __security_check_cookie
0x18000cfc8  lea     r11, [rsp+258h+var_18]
0x18000cfd0  mov     rbx, [r11+30h]
0x18000cfd4  mov     rbp, [r11+38h]
0x18000cfd8  mov     rsp, r11
0x18000cfdb  pop     r14
0x18000cfdd  pop     rdi
0x18000cfde  pop     rsi
0x18000cfdf  retn
```
