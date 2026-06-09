# ExtractFileName

- ea: `0x180005210`
- end: `0x1800052b0`
- name: `ExtractFileName`
- size: `160`
- prototype: `HRESULT __fastcall(STRSAFE_LPWSTR pszDest, __int64, const wchar_t *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a66c`

## callees

- `0x180002e4c`
- `0x180014ae0`

## import_xrefs

- `msvcrt!_wsplitpath_s` at `0x18000526b`
- `msvcrt!_wsplitpath_s` at `0x18000526b`

## pseudocode

```c
HRESULT __fastcall ExtractFileName(STRSAFE_LPWSTR pszDest, __int64 a2, const wchar_t *a3)
{
  wchar_t Ext[256]; // [rsp+50h] [rbp-418h] BYREF
  wchar_t Filename[256]; // [rsp+250h] [rbp-218h] BYREF

  _wsplitpath_s(a3, 0, 0, 0, 0, Filename, 0x100u, Ext, 0x100u);
  return StringCchPrintfW(pszDest, 0x104u, L"%s%s", Filename, Ext);
}

```

## disassembly

```asm
0x180005210  push    rbx
0x180005212  sub     rsp, 460h
0x180005219  mov     rax, cs:__security_cookie
0x180005220  xor     rax, rsp
0x180005223  mov     [rsp+468h+var_18], rax
0x18000522b  mov     rbx, rcx
0x18000522e  mov     edx, 100h
0x180005233  mov     [rsp+468h+ExtCount], rdx; ExtCount
0x180005238  lea     rcx, [rsp+468h+var_418]
0x18000523d  mov     [rsp+468h+Ext], rcx; Ext
0x180005242  mov     rax, r8
0x180005245  mov     [rsp+468h+FilenameCount], rdx; FilenameCount
0x18000524a  lea     rcx, [rsp+468h+var_218]
0x180005252  mov     [rsp+468h+Filename], rcx; Filename
0x180005257  xor     r9d, r9d; Dir
0x18000525a  mov     rcx, rax; FullPath
0x18000525d  mov     [rsp+468h+DirCount], 0; DirCount
0x180005266  xor     r8d, r8d; DriveCount
0x180005269  xor     edx, edx; Drive
0x18000526b  call    cs:__imp__wsplitpath_s
0x180005271  lea     rax, [rsp+468h+var_418]
0x180005276  mov     edx, 104h; cchDest
0x18000527b  lea     r9, [rsp+468h+var_218]
0x180005283  mov     [rsp+468h+DirCount], rax
0x180005288  lea     r8, aSS_1; "%s%s"
0x18000528f  mov     rcx, rbx; pszDest
0x180005292  call    StringCchPrintfW
0x180005297  mov     rcx, [rsp+468h+var_18]
0x18000529f  xor     rcx, rsp; StackCookie
0x1800052a2  call    __security_check_cookie
0x1800052a7  add     rsp, 460h
0x1800052ae  pop     rbx
0x1800052af  retn
```
