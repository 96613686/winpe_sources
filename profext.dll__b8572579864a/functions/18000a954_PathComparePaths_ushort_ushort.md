# PathComparePaths(ushort *,ushort *)

- ea: `0x18000a954`
- end: `0x18000aac6`
- name: `?PathComparePaths@@YAKPEAG0@Z`
- size: `370`
- prototype: `unsigned int __fastcall(LPCWCH lpString2, LPCWCH lpString1)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x18000a8b0`

## callees

- `0x18000a954`
- `0x180022830`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000aa1d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000aa1d`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveBackslash` at `0x18000a9ac`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveBackslash` at `0x18000a9dd`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveBackslash` at `0x18000a9ac`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveBackslash` at `0x18000a9dd`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetFolderPathW` at `0x18000aa77`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetFolderPathW` at `0x18000aa77`

## pseudocode

```c
__int64 __fastcall PathComparePaths(unsigned __int64 lpString2, WCHAR *lpString1)
{
  WCHAR *v3; // rbp
  unsigned int v4; // esi
  unsigned __int64 v5; // rbx
  __int64 v6; // rdx
  unsigned __int64 v7; // rdi
  __int64 v8; // rdx
  int v9; // edx
  const WCHAR *v11; // rax
  const WCHAR *v12; // rcx
  WCHAR pszPath[264]; // [rsp+30h] [rbp-248h] BYREF

  v3 = (WCHAR *)lpString2;
  v4 = 1;
  if ( lpString2 < 0x10000 )
  {
    if ( SHGetFolderPathW(0, lpString2 | 0x4000, 0, 0, pszPath) < 0 )
      return v4;
    v3 = pszPath;
  }
  v5 = -1;
  v6 = -1;
  do
    ++v6;
  while ( v3[v6] );
  if ( PathCchRemoveBackslash(v3, v6 + 1) >= 0 )
  {
    v7 = -1;
    do
      ++v7;
    while ( v3[v7] );
    v8 = -1;
    do
      ++v8;
    while ( lpString1[v8] );
    if ( PathCchRemoveBackslash(lpString1, v8 + 1) >= 0 )
    {
      do
        ++v5;
      while ( lpString1[v5] );
      if ( v7 <= v5 )
      {
        if ( lpString1[v7] == 92 )
        {
          v9 = v7;
        }
        else
        {
          if ( v5 != v7 )
            return v4;
          v9 = v5;
        }
        if ( CompareStringOrdinal(lpString1, v9, v3, v7, 1) == 2 )
        {
          if ( v7 < v5 )
          {
            v11 = &lpString1[v7 + 1];
            v12 = &lpString1[v5];
            while ( v11 < v12 && *v11 != 92 )
              ++v11;
            return v11 < v12 ? 8 : 12;
          }
          else
          {
            return 2;
          }
        }
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18000a954  mov     [rsp+arg_10], rbx
0x18000a959  push    rbp
0x18000a95a  push    rsi
0x18000a95b  push    rdi
0x18000a95c  push    r14
0x18000a95e  push    r15
0x18000a960  sub     rsp, 250h
0x18000a967  mov     rax, cs:__security_cookie
0x18000a96e  xor     rax, rsp
0x18000a971  mov     [rsp+278h+var_38], rax
0x18000a979  xor     r15d, r15d
0x18000a97c  mov     r14, rdx
0x18000a97f  mov     rbp, rcx
0x18000a982  mov     esi, 1
0x18000a987  cmp     rcx, 10000h
0x18000a98e  jb      loc_18000AA5F
0x18000a994  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000a998  mov     rdx, rbx
0x18000a99b  inc     rdx
0x18000a99e  cmp     [rbp+rdx*2+0], r15w
0x18000a9a4  jnz     short loc_18000A99B
0x18000a9a6  inc     rdx; cchPath
0x18000a9a9  mov     rcx, rbp; pszPath
0x18000a9ac  call    cs:__imp_PathCchRemoveBackslash
0x18000a9b3  nop     dword ptr [rax+rax+00h]
0x18000a9b8  test    eax, eax
0x18000a9ba  js      short loc_18000AA35
0x18000a9bc  mov     rdi, rbx
0x18000a9bf  inc     rdi
0x18000a9c2  cmp     [rbp+rdi*2+0], r15w
0x18000a9c8  jnz     short loc_18000A9BF
0x18000a9ca  mov     rdx, rbx
0x18000a9cd  inc     rdx
0x18000a9d0  cmp     [r14+rdx*2], r15w
0x18000a9d5  jnz     short loc_18000A9CD
0x18000a9d7  inc     rdx; cchPath
0x18000a9da  mov     rcx, r14; pszPath
0x18000a9dd  call    cs:__imp_PathCchRemoveBackslash
0x18000a9e4  nop     dword ptr [rax+rax+00h]
0x18000a9e9  test    eax, eax
0x18000a9eb  js      short loc_18000AA35
0x18000a9ed  inc     rbx
0x18000a9f0  cmp     [r14+rbx*2], r15w
0x18000a9f5  jnz     short loc_18000A9ED
0x18000a9f7  cmp     rdi, rbx
0x18000a9fa  ja      short loc_18000AA35
0x18000a9fc  cmp     word ptr [r14+rdi*2], 5Ch ; '\'
0x18000aa02  jz      loc_18000AA91
0x18000aa08  cmp     rbx, rdi
0x18000aa0b  jnz     short loc_18000AA35
0x18000aa0d  mov     rdx, rbx; cchCount1
0x18000aa10  mov     r9d, edi; cchCount2
0x18000aa13  mov     [rsp+278h+bIgnoreCase], esi; bIgnoreCase
0x18000aa17  mov     r8, rbp; lpString2
0x18000aa1a  mov     rcx, r14; lpString1
0x18000aa1d  call    cs:__imp_CompareStringOrdinal
0x18000aa24  nop     dword ptr [rax+rax+00h]
0x18000aa29  cmp     eax, 2
0x18000aa2c  jnz     short loc_18000AA35
0x18000aa2e  cmp     rdi, rbx
0x18000aa31  jb      short loc_18000AA99
0x18000aa33  mov     esi, eax
0x18000aa35  mov     eax, esi
0x18000aa37  mov     rcx, [rsp+278h+var_38]
0x18000aa3f  xor     rcx, rsp; StackCookie
0x18000aa42  call    __security_check_cookie
0x18000aa47  mov     rbx, [rsp+278h+arg_10]
0x18000aa4f  add     rsp, 250h
0x18000aa56  pop     r15
0x18000aa58  pop     r14
0x18000aa5a  pop     rdi
0x18000aa5b  pop     rsi
0x18000aa5c  pop     rbp
0x18000aa5d  retn
0x18000aa5f  lea     rax, [rsp+278h+pszPath]
0x18000aa64  bts     ebp, 0Eh
0x18000aa68  mov     edx, ebp; csidl
0x18000aa6a  mov     qword ptr [rsp+278h+bIgnoreCase], rax; pszPath
0x18000aa6f  xor     r9d, r9d; dwFlags
0x18000aa72  xor     r8d, r8d; hToken
0x18000aa75  xor     ecx, ecx; hwnd
0x18000aa77  call    cs:__imp_SHGetFolderPathW
0x18000aa7e  nop     dword ptr [rax+rax+00h]
0x18000aa83  test    eax, eax
0x18000aa85  js      short loc_18000AA35
0x18000aa87  lea     rbp, [rsp+278h+pszPath]
0x18000aa8c  jmp     loc_18000A994
0x18000aa91  mov     rdx, rdi
0x18000aa94  jmp     loc_18000AA10
0x18000aa99  lea     rax, [r14+2]
0x18000aa9d  lea     rax, [rax+rdi*2]
0x18000aaa1  lea     rcx, [r14+rbx*2]
0x18000aaa5  jmp     short loc_18000AAB1
0x18000aaa7  cmp     word ptr [rax], 5Ch ; '\'
0x18000aaab  jz      short loc_18000AAB6
0x18000aaad  add     rax, 2
0x18000aab1  cmp     rax, rcx
0x18000aab4  jb      short loc_18000AAA7
0x18000aab6  cmp     rax, rcx
0x18000aab9  sbb     esi, esi
0x18000aabb  and     esi, 0FFFFFFFCh
0x18000aabe  add     esi, 0Ch
0x18000aac1  jmp     loc_18000AA35
```
