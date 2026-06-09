# CopyRupDirectory(ushort const *,ushort const *,int)

- ea: `0x18001d96c`
- end: `0x18001da36`
- name: `?CopyRupDirectory@@YAJPEBG0H@Z`
- size: `202`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180007bd0`

## callees

- `0x18000547c`
- `0x180012f28`
- `0x18001d84c`
- `0x18001d96c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18001d986`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18001d986`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18001da23`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18001da23`
- `api-ms-win-core-kernel32-private-l1-1-1!PrivCopyFileExW` at `0x18001d9fe`
- `api-ms-win-core-kernel32-private-l1-1-1!PrivCopyFileExW` at `0x18001d9fe`

## string_xrefs

- `0x18001d9ad`: `onecore\ds\security\gina\profile\proflib\dir.cpp`
- `0x18001da0d`: `onecore\ds\security\gina\profile\proflib\dir.cpp`
- `0x18001d9a1`: `Failed to create the destination directory <%ls>.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CopyRupDirectory(const unsigned __int16 *a1, const unsigned __int16 *a2, int a3)
{
  unsigned int NestedDirectory; // ebx
  const char *v8; // r9
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  int v10; // [rsp+78h] [rbp+20h] BYREF

  SetFileAttributesW(a2, 0x80u);
  NestedDirectory = CreateNestedDirectory(a2, 0);
  if ( (NestedDirectory & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x182,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\dir.cpp",
      (const char *)NestedDirectory,
      (int)"Failed to create the destination directory <%ls>.",
      (const char *)a2);
    return NestedDirectory;
  }
  v10 = 0;
  if ( !(unsigned int)PrivCopyFileExW(a1, a2, CopyProgressRoutine, 0, &v10, a3 != 0 ? 640 : 1680) )
  {
    NestedDirectory = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0x195,
                        (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\dir.cpp",
                        v8);
    RemoveDirectoryW(a2);
    return NestedDirectory;
  }
  return 0;
}

```

## disassembly

```asm
0x18001d96c  push    rbx
0x18001d96e  push    rbp
0x18001d96f  push    rsi
0x18001d970  push    rdi
0x18001d971  sub     rsp, 38h
0x18001d975  mov     rdi, rdx
0x18001d978  mov     rbp, rcx
0x18001d97b  mov     rcx, rdi; lpFileName
0x18001d97e  mov     edx, 80h; dwFileAttributes
0x18001d983  mov     esi, r8d
0x18001d986  call    cs:__imp_SetFileAttributesW
0x18001d98c  xor     edx, edx; lpSecurityAttributes
0x18001d98e  mov     rcx, rdi; unsigned __int16 *
0x18001d991  call    ?CreateNestedDirectory@@YAJPEBGPEAU_SECURITY_ATTRIBUTES@@@Z; CreateNestedDirectory(ushort const *,_SECURITY_ATTRIBUTES *)
0x18001d996  mov     ebx, eax
0x18001d998  test    eax, eax
0x18001d99a  jns     short loc_18001D9CA
0x18001d99c  mov     rcx, [rsp+58h]; this
0x18001d9a1  lea     rax, aFailedToCreate; "Failed to create the destination direct"...
0x18001d9a8  mov     [rsp+58h+var_30], rdi; char *
0x18001d9ad  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001d9b4  mov     r9d, ebx; char *
0x18001d9b7  mov     qword ptr [rsp+58h+var_38], rax; int
0x18001d9bc  mov     edx, 182h; void *
0x18001d9c1  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001d9c6  mov     eax, ebx
0x18001d9c8  jmp     short loc_18001DA2D
0x18001d9ca  neg     esi
0x18001d9cc  mov     [rsp+58h+arg_18], 0
0x18001d9d4  lea     r8, _CopyProgressRoutine
0x18001d9db  mov     rdx, rdi
0x18001d9de  sbb     eax, eax
0x18001d9e0  mov     rcx, rbp
0x18001d9e3  and     eax, 0FFFFFBF0h
0x18001d9e8  xor     r9d, r9d
0x18001d9eb  add     eax, 690h
0x18001d9f0  mov     dword ptr [rsp+58h+var_30], eax
0x18001d9f4  lea     rax, [rsp+58h+arg_18]
0x18001d9f9  mov     qword ptr [rsp+58h+var_38], rax
0x18001d9fe  call    cs:__imp_PrivCopyFileExW
0x18001da04  test    eax, eax
0x18001da06  jnz     short loc_18001DA2B
0x18001da08  mov     rcx, [rsp+58h]; this
0x18001da0d  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001da14  mov     edx, 195h; void *
0x18001da19  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001da1e  mov     rcx, rdi; lpPathName
0x18001da21  mov     ebx, eax
0x18001da23  call    cs:__imp_RemoveDirectoryW
0x18001da29  jmp     short loc_18001D9C6
0x18001da2b  xor     eax, eax
0x18001da2d  add     rsp, 38h
0x18001da31  pop     rdi
0x18001da32  pop     rsi
0x18001da33  pop     rbp
0x18001da34  pop     rbx
0x18001da35  retn
```
