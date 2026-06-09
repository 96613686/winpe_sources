# _CreateDirectory(ushort const *,_SECURITY_ATTRIBUTES *)

- ea: `0x18005d548`
- end: `0x18005d633`
- name: `?_CreateDirectory@@YAHPEBGPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `235`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180025298`

## callees

- `0x18002cfd0`
- `0x18005d548`
- `0x18006ed20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d57d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d60e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d57d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d60e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAddBackslashW` at `0x18005d5c1`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAddBackslashW` at `0x18005d5c1`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18005d56f`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18005d600`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18005d56f`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18005d600`

## pseudocode

```c
DWORD __fastcall _CreateDirectory(const unsigned __int16 *a1, struct _SECURITY_ATTRIBUTES *a2)
{
  DWORD LastError; // edi
  DWORD result; // eax
  __int16 *v5; // rbx
  __int16 v6; // ax
  WCHAR pszPath[3]; // [rsp+20h] [rbp-248h] BYREF
  __int16 v8; // [rsp+26h] [rbp-242h] BYREF

  LastError = 0;
  if ( CreateDirectoryW(a1, 0) )
    return LastError;
  result = GetLastError();
  LastError = result;
  if ( result != 3 )
    return result;
  if ( (int)StringCchCopyW(pszPath, 0x104u, a1) >= 0 && PathAddBackslashW(pszPath) )
  {
    v5 = &v8;
    if ( v8 )
    {
      do
      {
        v6 = *v5;
        do
        {
          if ( v6 == 92 )
            break;
          v6 = *++v5;
        }
        while ( *v5 );
        if ( *v5 )
        {
          *v5 = 0;
          if ( CreateDirectoryW(pszPath, 0) )
            LastError = 0;
          else
            LastError = GetLastError();
        }
        *v5++ = 92;
      }
      while ( *v5 );
    }
    return LastError;
  }
  return 206;
}

```

## disassembly

```asm
0x18005d548  push    rbx
0x18005d54a  push    rbp
0x18005d54b  push    rsi
0x18005d54c  push    rdi
0x18005d54d  sub     rsp, 248h
0x18005d554  mov     rax, cs:__security_cookie
0x18005d55b  xor     rax, rsp
0x18005d55e  mov     [rsp+268h+var_38], rax
0x18005d566  xor     esi, esi
0x18005d568  xor     edx, edx; lpSecurityAttributes
0x18005d56a  mov     edi, esi
0x18005d56c  mov     rbx, rcx
0x18005d56f  call    cs:__imp_CreateDirectoryW
0x18005d575  test    eax, eax
0x18005d577  jnz     loc_18005D622
0x18005d57d  call    cs:__imp_GetLastError
0x18005d583  mov     edi, eax
0x18005d585  cmp     eax, 3
0x18005d588  jz      short loc_18005D5A6
0x18005d58a  mov     rcx, [rsp+268h+var_38]
0x18005d592  xor     rcx, rsp; StackCookie
0x18005d595  call    __security_check_cookie
0x18005d59a  add     rsp, 248h
0x18005d5a1  pop     rdi
0x18005d5a2  pop     rsi
0x18005d5a3  pop     rbp
0x18005d5a4  pop     rbx
0x18005d5a5  retn
0x18005d5a6  mov     r8, rbx; unsigned __int16 *
0x18005d5a9  lea     rcx, [rsp+268h+pszPath]; unsigned __int16 *
0x18005d5ae  mov     edx, 104h; unsigned __int64
0x18005d5b3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18005d5b8  test    eax, eax
0x18005d5ba  js      short loc_18005D629
0x18005d5bc  lea     rcx, [rsp+268h+pszPath]; pszPath
0x18005d5c1  call    cs:__imp_PathAddBackslashW
0x18005d5c7  test    rax, rax
0x18005d5ca  jz      short loc_18005D629
0x18005d5cc  lea     rbx, [rsp+268h+var_242]
0x18005d5d1  cmp     [rsp+268h+var_242], si
0x18005d5d6  jz      short loc_18005D622
0x18005d5d8  mov     ebp, 5Ch ; '\'
0x18005d5dd  movzx   eax, word ptr [rbx]
0x18005d5e0  cmp     ax, bp
0x18005d5e3  jz      short loc_18005D5F1
0x18005d5e5  add     rbx, 2
0x18005d5e9  movzx   eax, word ptr [rbx]
0x18005d5ec  test    ax, ax
0x18005d5ef  jnz     short loc_18005D5E0
0x18005d5f1  cmp     [rbx], si
0x18005d5f4  jz      short loc_18005D616
0x18005d5f6  xor     edx, edx; lpSecurityAttributes
0x18005d5f8  mov     [rbx], si
0x18005d5fb  lea     rcx, [rsp+268h+pszPath]; lpPathName
0x18005d600  call    cs:__imp_CreateDirectoryW
0x18005d606  test    eax, eax
0x18005d608  jz      short loc_18005D60E
0x18005d60a  mov     edi, esi
0x18005d60c  jmp     short loc_18005D616
0x18005d60e  call    cs:__imp_GetLastError
0x18005d614  mov     edi, eax
0x18005d616  mov     [rbx], bp
0x18005d619  add     rbx, 2
0x18005d61d  cmp     [rbx], si
0x18005d620  jnz     short loc_18005D5DD
0x18005d622  mov     eax, edi
0x18005d624  jmp     loc_18005D58A
0x18005d629  mov     eax, 0CEh
0x18005d62e  jmp     loc_18005D58A
```
