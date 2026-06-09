# Vml::CreateDirectoryW(ushort const *)

- ea: `0x18000a678`
- end: `0x18000a806`
- name: `?CreateDirectoryW@Vml@@YAKPEBG@Z`
- size: `398`
- prototype: `__int64 __fastcall(LPCWSTR lpPathName, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, reparse_path`

## callers

- `0x180015050`
- `0x18001c3d0`

## callees

- `0x180002690`
- `0x18000a678`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000a7c0`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000a7c0`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000a6ba`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000a79b`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000a6ba`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000a79b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a6ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a7ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a6ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a7ab`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x18000a699`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x18000a699`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathSkipRootW` at `0x18000a753`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathSkipRootW` at `0x18000a753`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x18000a73e`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x18000a73e`

## pseudocode

```c
__int64 __fastcall Vml::CreateDirectoryW(LPCWSTR lpPathName, const unsigned __int16 *a2)
{
  const WCHAR *v2; // rdi
  DWORD LastError; // ebx
  WCHAR *v4; // rax
  __int64 v5; // rdx
  __int64 v6; // rcx
  WCHAR *v7; // rcx
  LPWSTR v8; // rax
  LPWSTR v9; // rdi
  WCHAR v10; // ax
  DWORD v11; // eax
  DWORD FileAttributesW; // eax
  WCHAR pszPath[264]; // [rsp+20h] [rbp-248h] BYREF

  v2 = lpPathName;
  if ( PathIsRelativeW(lpPathName) )
    return 161;
  if ( CreateDirectoryW(v2, 0) )
    return 0;
  LastError = GetLastError();
  if ( LastError != 3 )
    return LastError;
  v4 = pszPath;
  v5 = 260;
  v6 = 2147483646;
  do
  {
    if ( !v6 )
      break;
    if ( !*v2 )
      break;
    *v4++ = *v2++;
    --v6;
    --v5;
  }
  while ( v5 );
  v7 = v4 - 1;
  if ( v5 )
    v7 = v4;
  *v7 = 0;
  if ( !v5 || PathCchAddBackslash(pszPath, 0x104u) < 0 )
    return 206;
  v8 = PathSkipRootW(pszPath);
  v9 = v8;
  if ( v8 )
  {
    if ( *v8 )
    {
      LastError = 183;
      while ( 1 )
      {
        v10 = *v9;
        do
        {
          if ( v10 == 92 )
            break;
          v10 = *++v9;
        }
        while ( *v9 );
        if ( *v9 )
        {
          *v9 = 0;
          if ( !CreateDirectoryW(pszPath, 0) )
          {
            v11 = GetLastError();
            if ( v11 != 183 )
              return v11;
            FileAttributesW = GetFileAttributesW(pszPath);
            if ( FileAttributesW == -1 || (FileAttributesW & 0x10) == 0 )
              return LastError;
          }
        }
        *v9++ = 92;
        if ( !*v9 )
          return 0;
      }
    }
    return 0;
  }
  return 161;
}

```

## disassembly

```asm
0x18000a678  push    rbx
0x18000a67a  push    rbp
0x18000a67b  push    rsi
0x18000a67c  push    rdi
0x18000a67d  sub     rsp, 248h
0x18000a684  mov     rax, cs:__security_cookie
0x18000a68b  xor     rax, rsp
0x18000a68e  mov     [rsp+268h+var_38], rax
0x18000a696  mov     rdi, rcx
0x18000a699  call    cs:__imp_PathIsRelativeW
0x18000a6a0  nop     dword ptr [rax+rax+00h]
0x18000a6a5  xor     esi, esi
0x18000a6a7  test    eax, eax
0x18000a6a9  jz      short loc_18000A6B5
0x18000a6ab  mov     ebx, 0A1h
0x18000a6b0  jmp     loc_18000A7E3
0x18000a6b5  xor     edx, edx; lpSecurityAttributes
0x18000a6b7  mov     rcx, rdi; lpPathName
0x18000a6ba  call    cs:__imp_CreateDirectoryW
0x18000a6c1  nop     dword ptr [rax+rax+00h]
0x18000a6c6  test    eax, eax
0x18000a6c8  jnz     loc_18000A7E1
0x18000a6ce  call    cs:__imp_GetLastError
0x18000a6d5  nop     dword ptr [rax+rax+00h]
0x18000a6da  mov     ebx, eax
0x18000a6dc  cmp     eax, 3
0x18000a6df  jnz     loc_18000A7E3
0x18000a6e5  mov     r9d, 104h
0x18000a6eb  lea     rax, [rsp+268h+pszPath]
0x18000a6f0  mov     edx, r9d
0x18000a6f3  mov     ecx, 7FFFFFFEh
0x18000a6f8  test    rcx, rcx
0x18000a6fb  jz      short loc_18000A71C
0x18000a6fd  movzx   r8d, word ptr [rdi]
0x18000a701  test    r8w, r8w
0x18000a705  jz      short loc_18000A71C
0x18000a707  mov     [rax], r8w
0x18000a70b  add     rdi, 2
0x18000a70f  add     rax, 2
0x18000a713  dec     rcx
0x18000a716  sub     rdx, 1
0x18000a71a  jnz     short loc_18000A6F8
0x18000a71c  test    rdx, rdx
0x18000a71f  lea     rcx, [rax-2]
0x18000a723  cmovnz  rcx, rax
0x18000a727  mov     [rcx], si
0x18000a72a  jnz     short loc_18000A736
0x18000a72c  mov     ebx, 0CEh
0x18000a731  jmp     loc_18000A7E3
0x18000a736  mov     rdx, r9; cchPath
0x18000a739  lea     rcx, [rsp+268h+pszPath]; pszPath
0x18000a73e  call    cs:__imp_PathCchAddBackslash
0x18000a745  nop     dword ptr [rax+rax+00h]
0x18000a74a  test    eax, eax
0x18000a74c  js      short loc_18000A72C
0x18000a74e  lea     rcx, [rsp+268h+pszPath]; pszPath
0x18000a753  call    cs:__imp_PathSkipRootW
0x18000a75a  nop     dword ptr [rax+rax+00h]
0x18000a75f  mov     rdi, rax
0x18000a762  test    rax, rax
0x18000a765  jz      loc_18000A6AB
0x18000a76b  cmp     [rax], si
0x18000a76e  jz      short loc_18000A7E1
0x18000a770  mov     ebp, 5Ch ; '\'
0x18000a775  lea     ebx, [rbp+5Bh]
0x18000a778  movzx   eax, word ptr [rdi]
0x18000a77b  cmp     ax, bp
0x18000a77e  jz      short loc_18000A78C
0x18000a780  add     rdi, 2
0x18000a784  movzx   eax, word ptr [rdi]
0x18000a787  test    ax, ax
0x18000a78a  jnz     short loc_18000A77B
0x18000a78c  cmp     [rdi], si
0x18000a78f  jz      short loc_18000A7D5
0x18000a791  xor     edx, edx; lpSecurityAttributes
0x18000a793  mov     [rdi], si
0x18000a796  lea     rcx, [rsp+268h+pszPath]; lpPathName
0x18000a79b  call    cs:__imp_CreateDirectoryW
0x18000a7a2  nop     dword ptr [rax+rax+00h]
0x18000a7a7  test    eax, eax
0x18000a7a9  jnz     short loc_18000A7D5
0x18000a7ab  call    cs:__imp_GetLastError
0x18000a7b2  nop     dword ptr [rax+rax+00h]
0x18000a7b7  cmp     eax, ebx
0x18000a7b9  jnz     short loc_18000A802
0x18000a7bb  lea     rcx, [rsp+268h+pszPath]; lpFileName
0x18000a7c0  call    cs:__imp_GetFileAttributesW
0x18000a7c7  nop     dword ptr [rax+rax+00h]
0x18000a7cc  cmp     eax, 0FFFFFFFFh
0x18000a7cf  jz      short loc_18000A7E3
0x18000a7d1  test    al, 10h
0x18000a7d3  jz      short loc_18000A7E3
0x18000a7d5  mov     [rdi], bp
0x18000a7d8  add     rdi, 2
0x18000a7dc  cmp     [rdi], si
0x18000a7df  jnz     short loc_18000A778
0x18000a7e1  mov     ebx, esi
0x18000a7e3  mov     eax, ebx
0x18000a7e5  mov     rcx, [rsp+268h+var_38]
0x18000a7ed  xor     rcx, rsp; StackCookie
0x18000a7f0  call    __security_check_cookie
0x18000a7f5  add     rsp, 248h
0x18000a7fc  pop     rdi
0x18000a7fd  pop     rsi
0x18000a7fe  pop     rbp
0x18000a7ff  pop     rbx
0x18000a800  retn
0x18000a802  mov     ebx, eax
0x18000a804  jmp     short loc_18000A7E3
```
