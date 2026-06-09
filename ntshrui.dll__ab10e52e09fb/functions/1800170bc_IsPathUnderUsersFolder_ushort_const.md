# IsPathUnderUsersFolder(ushort const *)

- ea: `0x1800170bc`
- end: `0x180017182`
- name: `?IsPathUnderUsersFolder@@YAHPEBG@Z`
- size: `198`
- prototype: `__int64 __fastcall(PCWSTR pszPathIn)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x180016f8c`

## callees

- `0x1800170bc`
- `0x1800254e0`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchCanonicalize` at `0x180017112`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalize` at `0x180017156`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalize` at `0x180017112`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalize` at `0x180017156`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001717a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001717a`
- `SHELL32!SHGetKnownFolderPath` at `0x1800170f6`
- `SHELL32!SHGetKnownFolderPath` at `0x1800170f6`
- `SHELL32!__imp_PathComparePaths` at `0x18001716d`
- `SHELL32!__imp_PathComparePaths` at `0x18001716d`

## pseudocode

```c
__int64 __fastcall IsPathUnderUsersFolder(PCWSTR pszPathIn)
{
  unsigned int v2; // ebx
  PWSTR ppszPath; // [rsp+20h] [rbp-448h] BYREF
  WCHAR v5[264]; // [rsp+30h] [rbp-438h] BYREF
  WCHAR pszPathOut[264]; // [rsp+240h] [rbp-228h] BYREF

  v2 = 0;
  ppszPath = 0;
  if ( SHGetKnownFolderPath(&FOLDERID_UserProfiles, 0, 0, &ppszPath) >= 0
    && PathCchCanonicalize(pszPathOut, 0x104u, ppszPath) >= 0
    && PathCchCanonicalize(v5, 0x104u, pszPathIn) >= 0 )
  {
    v2 = PathComparePaths(pszPathOut, v5) & 8;
  }
  if ( ppszPath )
    CoTaskMemFree(ppszPath);
  return v2;
}

```

## disassembly

```asm
0x1800170bc  mov     [rsp+arg_8], rbx
0x1800170c1  push    rdi
0x1800170c2  sub     rsp, 460h
0x1800170c9  mov     rax, cs:__security_cookie
0x1800170d0  xor     rax, rsp
0x1800170d3  mov     [rsp+468h+var_18], rax
0x1800170db  mov     rdi, rcx
0x1800170de  lea     r9, [rsp+468h+ppszPath]; ppszPath
0x1800170e3  xor     ebx, ebx
0x1800170e5  lea     rcx, FOLDERID_UserProfiles; rfid
0x1800170ec  xor     r8d, r8d; hToken
0x1800170ef  mov     [rsp+468h+ppszPath], rbx
0x1800170f4  xor     edx, edx; dwFlags
0x1800170f6  call    cs:__imp_SHGetKnownFolderPath
0x1800170fc  test    eax, eax
0x1800170fe  js      short loc_18001711C
0x180017100  mov     r8, [rsp+468h+ppszPath]; pszPathIn
0x180017105  lea     rcx, [rsp+468h+pszPathOut]; pszPathOut
0x18001710d  mov     edx, 104h; cchPathOut
0x180017112  call    cs:__imp_PathCchCanonicalize
0x180017118  test    eax, eax
0x18001711a  jns     short loc_180017149
0x18001711c  mov     rcx, [rsp+468h+ppszPath]; pv
0x180017121  test    rcx, rcx
0x180017124  jnz     short loc_18001717A
0x180017126  mov     eax, ebx
0x180017128  mov     rcx, [rsp+468h+var_18]
0x180017130  xor     rcx, rsp; StackCookie
0x180017133  call    __security_check_cookie
0x180017138  mov     rbx, [rsp+468h+arg_8]
0x180017140  add     rsp, 460h
0x180017147  pop     rdi
0x180017148  retn
0x180017149  mov     r8, rdi; pszPathIn
0x18001714c  lea     rcx, [rsp+468h+var_438]; pszPathOut
0x180017151  mov     edx, 104h; cchPathOut
0x180017156  call    cs:__imp_PathCchCanonicalize
0x18001715c  test    eax, eax
0x18001715e  js      short loc_18001711C
0x180017160  lea     rdx, [rsp+468h+var_438]
0x180017165  lea     rcx, [rsp+468h+pszPathOut]
0x18001716d  call    cs:__imp_PathComparePaths
0x180017173  mov     ebx, eax
0x180017175  and     ebx, 8
0x180017178  jmp     short loc_18001711C
0x18001717a  call    cs:__imp_CoTaskMemFree
0x180017180  jmp     short loc_180017126
```
