# PathIsSubFolder(ushort const *,ushort const *)

- ea: `0x18001ae04`
- end: `0x18001ae96`
- name: `?PathIsSubFolder@@YAHPEBG0@Z`
- size: `146`
- prototype: `__int64 __fastcall(PCWSTR pszPathIn, PCWSTR)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x18005b080`
- `0x18005d334`

## callees

- `0x18001ae04`
- `0x1800254e0`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchCanonicalize` at `0x18001ae38`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalize` at `0x18001ae72`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalize` at `0x18001ae38`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalize` at `0x18001ae72`
- `SHELL32!__imp_PathComparePaths` at `0x18001ae89`
- `SHELL32!__imp_PathComparePaths` at `0x18001ae89`

## pseudocode

```c
__int64 __fastcall PathIsSubFolder(PCWSTR pszPathIn, PCWSTR a2)
{
  unsigned int v3; // ebx
  WCHAR v5[264]; // [rsp+20h] [rbp-438h] BYREF
  WCHAR pszPathOut[264]; // [rsp+230h] [rbp-228h] BYREF

  v3 = 0;
  if ( PathCchCanonicalize(pszPathOut, 0x104u, pszPathIn) >= 0 && PathCchCanonicalize(v5, 0x104u, a2) >= 0 )
    return PathComparePaths(pszPathOut, v5) & 8;
  return v3;
}

```

## disassembly

```asm
0x18001ae04  mov     [rsp+arg_10], rbx
0x18001ae09  push    rdi
0x18001ae0a  sub     rsp, 450h
0x18001ae11  mov     rax, cs:__security_cookie
0x18001ae18  xor     rax, rsp
0x18001ae1b  mov     [rsp+458h+var_18], rax
0x18001ae23  mov     rdi, rdx
0x18001ae26  mov     r8, rcx; pszPathIn
0x18001ae29  mov     edx, 104h; cchPathOut
0x18001ae2e  lea     rcx, [rsp+458h+pszPathOut]; pszPathOut
0x18001ae36  xor     ebx, ebx
0x18001ae38  call    cs:__imp_PathCchCanonicalize
0x18001ae3e  test    eax, eax
0x18001ae40  jns     short loc_18001AE65
0x18001ae42  mov     eax, ebx
0x18001ae44  mov     rcx, [rsp+458h+var_18]
0x18001ae4c  xor     rcx, rsp; StackCookie
0x18001ae4f  call    __security_check_cookie
0x18001ae54  mov     rbx, [rsp+458h+arg_10]
0x18001ae5c  add     rsp, 450h
0x18001ae63  pop     rdi
0x18001ae64  retn
0x18001ae65  mov     r8, rdi; pszPathIn
0x18001ae68  lea     rcx, [rsp+458h+var_438]; pszPathOut
0x18001ae6d  mov     edx, 104h; cchPathOut
0x18001ae72  call    cs:__imp_PathCchCanonicalize
0x18001ae78  test    eax, eax
0x18001ae7a  js      short loc_18001AE42
0x18001ae7c  lea     rdx, [rsp+458h+var_438]
0x18001ae81  lea     rcx, [rsp+458h+pszPathOut]
0x18001ae89  call    cs:__imp_PathComparePaths
0x18001ae8f  mov     ebx, eax
0x18001ae91  and     ebx, 8
0x18001ae94  jmp     short loc_18001AE42
```
