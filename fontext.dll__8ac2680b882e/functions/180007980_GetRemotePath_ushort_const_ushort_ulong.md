# GetRemotePath(ushort const *,ushort *,ulong *)

- ea: `0x180007980`
- end: `0x180007aa8`
- name: `?GetRemotePath@@YAJPEBGPEAGPEAK@Z`
- size: `296`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *, LPDWORD lpnLength)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180007f30`
- `0x1800234d0`
- `0x180023580`

## callees

- `0x180006624`
- `0x180007980`
- `0x180031070`

## import_xrefs

- `SHLWAPI!PathIsUNCW` at `0x1800079de`
- `SHLWAPI!PathIsUNCW` at `0x1800079de`
- `SHLWAPI!PathStripToRootW` at `0x1800079f1`
- `SHLWAPI!PathStripToRootW` at `0x1800079f1`
- `SHLWAPI!PathAddBackslashW` at `0x1800079fc`
- `SHLWAPI!PathAddBackslashW` at `0x1800079fc`
- `SHLWAPI!PathAppendW` at `0x180007a64`
- `SHLWAPI!PathAppendW` at `0x180007a64`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x180007a07`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x180007a07`
- `MPR!WNetGetConnectionW` at `0x180007a45`
- `MPR!WNetGetConnectionW` at `0x180007a45`
- `KERNEL32!lstrlenW` at `0x180007a54`
- `KERNEL32!lstrlenW` at `0x180007a54`

## pseudocode

```c
__int64 __fastcall GetRemotePath(const unsigned __int16 *a1, unsigned __int16 *a2, LPDWORD lpnLength)
{
  int v6; // ebx
  int v7; // eax
  WCHAR pszPath[2]; // [rsp+20h] [rbp-238h] BYREF
  __int16 v10; // [rsp+24h] [rbp-234h]

  v6 = -2147024774;
  if ( *lpnLength >= 0x104 )
  {
    *a2 = 0;
    v6 = StringCchCopyW(pszPath, 0x104u, a1);
    if ( v6 >= 0 )
    {
      if ( PathIsUNCW(pszPath) )
      {
        StringCchCopyW(a2, *lpnLength, a1);
        return 0;
      }
      else
      {
        PathStripToRootW(pszPath);
        PathAddBackslashW(pszPath);
        if ( GetDriveTypeW(pszPath) == 4 )
        {
          if ( pszPath[0] && pszPath[1] == 58 && v10 == 92 )
            v10 = 0;
          if ( !WNetGetConnectionW(pszPath, a2, lpnLength) )
          {
            v7 = lstrlenW(pszPath);
            PathAppendW(a2, &a1[v7]);
          }
        }
        else
        {
          return (unsigned int)-2147467259;
        }
      }
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180007980  mov     [rsp+arg_18], rbx
0x180007985  push    rbp
0x180007986  push    rsi
0x180007987  push    rdi
0x180007988  sub     rsp, 240h
0x18000798f  mov     rax, cs:__security_cookie
0x180007996  xor     rax, rsp
0x180007999  mov     [rsp+258h+var_28], rax
0x1800079a1  mov     rdi, rdx
0x1800079a4  mov     rbp, r8
0x1800079a7  mov     edx, 104h; unsigned __int64
0x1800079ac  mov     rsi, rcx
0x1800079af  mov     ebx, 8007007Ah
0x1800079b4  cmp     [r8], edx
0x1800079b7  jb      loc_180007A83
0x1800079bd  xor     eax, eax
0x1800079bf  mov     r8, rcx; unsigned __int16 *
0x1800079c2  lea     rcx, [rsp+258h+pszPath]; unsigned __int16 *
0x1800079c7  mov     [rdi], ax
0x1800079ca  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800079cf  mov     ebx, eax
0x1800079d1  test    eax, eax
0x1800079d3  js      loc_180007A83
0x1800079d9  lea     rcx, [rsp+258h+pszPath]; pszPath
0x1800079de  call    cs:__imp_PathIsUNCW
0x1800079e4  test    eax, eax
0x1800079e6  jnz     loc_180007A73
0x1800079ec  lea     rcx, [rsp+258h+pszPath]; pszPath
0x1800079f1  call    cs:__imp_PathStripToRootW
0x1800079f7  lea     rcx, [rsp+258h+pszPath]; pszPath
0x1800079fc  call    cs:__imp_PathAddBackslashW
0x180007a02  lea     rcx, [rsp+258h+pszPath]; lpRootPathName
0x180007a07  call    cs:__imp_GetDriveTypeW
0x180007a0d  cmp     eax, 4
0x180007a10  jnz     short loc_180007A6C
0x180007a12  xor     eax, eax
0x180007a14  cmp     ax, [rsp+258h+pszPath]
0x180007a19  jz      short loc_180007A3A
0x180007a1b  mov     eax, 3Ah ; ':'
0x180007a20  cmp     ax, [rsp+258h+var_236]
0x180007a25  jnz     short loc_180007A3A
0x180007a27  mov     eax, 5Ch ; '\'
0x180007a2c  cmp     ax, [rsp+258h+var_234]
0x180007a31  jnz     short loc_180007A3A
0x180007a33  xor     eax, eax
0x180007a35  mov     [rsp+258h+var_234], ax
0x180007a3a  mov     r8, rbp; lpnLength
0x180007a3d  lea     rcx, [rsp+258h+pszPath]; lpLocalName
0x180007a42  mov     rdx, rdi; lpRemoteName
0x180007a45  call    cs:__imp_WNetGetConnectionW
0x180007a4b  test    eax, eax
0x180007a4d  jnz     short loc_180007A83
0x180007a4f  lea     rcx, [rsp+258h+pszPath]; lpString
0x180007a54  call    cs:__imp_lstrlenW
0x180007a5a  movsxd  rdx, eax
0x180007a5d  mov     rcx, rdi; pszPath
0x180007a60  lea     rdx, [rsi+rdx*2]; pszMore
0x180007a64  call    cs:__imp_PathAppendW
0x180007a6a  jmp     short loc_180007A83
0x180007a6c  mov     ebx, 80004005h
0x180007a71  jmp     short loc_180007A83
0x180007a73  mov     edx, [rbp+0]; unsigned __int64
0x180007a76  mov     r8, rsi; unsigned __int16 *
0x180007a79  mov     rcx, rdi; unsigned __int16 *
0x180007a7c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180007a81  xor     ebx, ebx
0x180007a83  mov     eax, ebx
0x180007a85  mov     rcx, [rsp+258h+var_28]
0x180007a8d  xor     rcx, rsp; StackCookie
0x180007a90  call    __security_check_cookie
0x180007a95  mov     rbx, [rsp+258h+arg_18]
0x180007a9d  add     rsp, 240h
0x180007aa4  pop     rdi
0x180007aa5  pop     rsi
0x180007aa6  pop     rbp
0x180007aa7  retn
```
