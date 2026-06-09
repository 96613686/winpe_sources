# DeletePolicyIcon(wchar_t const *)

- ea: `0x1800ca8d0`
- end: `0x1800ca9bc`
- name: `?DeletePolicyIcon@@YAXPEB_W@Z`
- size: `236`
- prototype: `void __fastcall(const wchar_t *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x18003f96c`

## callees

- `0x180014d80`
- `0x1800a88a0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800ca91a`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800ca943`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800ca96c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800ca995`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800ca91a`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800ca943`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800ca96c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800ca995`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall DeletePolicyIcon(const wchar_t *a1)
{
  int v2; // [rsp+20h] [rbp-438h]
  __int64 v3; // [rsp+20h] [rbp-438h]
  __int64 v4; // [rsp+20h] [rbp-438h]
  __int64 v5; // [rsp+20h] [rbp-438h]
  WCHAR FileName[520]; // [rsp+30h] [rbp-428h] BYREF

  v2 = 16;
  StringCchPrintfW(FileName, 0x208u, L"%s_%d.bin", a1, v2);
  DeleteFileW(FileName);
  LODWORD(v3) = 24;
  StringCchPrintfW(FileName, 0x208u, L"%s_%d.bin", a1, v3);
  DeleteFileW(FileName);
  LODWORD(v4) = 32;
  StringCchPrintfW(FileName, 0x208u, L"%s_%d.bin", a1, v4);
  DeleteFileW(FileName);
  LODWORD(v5) = 48;
  StringCchPrintfW(FileName, 0x208u, L"%s_%d.bin", a1, v5);
  DeleteFileW(FileName);
}

```

## disassembly

```asm
0x1800ca8d0  mov     [rsp+arg_8], rbx
0x1800ca8d5  push    rdi
0x1800ca8d6  sub     rsp, 450h
0x1800ca8dd  mov     rax, cs:__security_cookie
0x1800ca8e4  xor     rax, rsp
0x1800ca8e7  mov     [rsp+458h+var_18], rax
0x1800ca8ef  mov     rbx, rcx
0x1800ca8f2  mov     [rsp+458h+var_438], 10h
0x1800ca8fa  mov     r9, rcx
0x1800ca8fd  lea     r8, aSDBin; "%s_%d.bin"
0x1800ca904  mov     edi, 208h
0x1800ca909  lea     rcx, [rsp+458h+FileName]; wchar_t *
0x1800ca90e  mov     edx, edi; unsigned __int64
0x1800ca910  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800ca915  lea     rcx, [rsp+458h+FileName]; lpFileName
0x1800ca91a  call    cs:__imp_DeleteFileW
0x1800ca920  mov     r9, rbx
0x1800ca923  mov     [rsp+458h+var_438], 18h
0x1800ca92b  lea     r8, aSDBin; "%s_%d.bin"
0x1800ca932  mov     edx, edi; unsigned __int64
0x1800ca934  lea     rcx, [rsp+458h+FileName]; wchar_t *
0x1800ca939  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800ca93e  lea     rcx, [rsp+458h+FileName]; lpFileName
0x1800ca943  call    cs:__imp_DeleteFileW
0x1800ca949  mov     r9, rbx
0x1800ca94c  mov     [rsp+458h+var_438], 20h ; ' '
0x1800ca954  lea     r8, aSDBin; "%s_%d.bin"
0x1800ca95b  mov     edx, edi; unsigned __int64
0x1800ca95d  lea     rcx, [rsp+458h+FileName]; wchar_t *
0x1800ca962  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800ca967  lea     rcx, [rsp+458h+FileName]; lpFileName
0x1800ca96c  call    cs:__imp_DeleteFileW
0x1800ca972  mov     r9, rbx
0x1800ca975  mov     [rsp+458h+var_438], 30h ; '0'
0x1800ca97d  lea     r8, aSDBin; "%s_%d.bin"
0x1800ca984  mov     edx, edi; unsigned __int64
0x1800ca986  lea     rcx, [rsp+458h+FileName]; wchar_t *
0x1800ca98b  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800ca990  lea     rcx, [rsp+458h+FileName]; lpFileName
0x1800ca995  call    cs:__imp_DeleteFileW
0x1800ca99b  mov     rcx, [rsp+458h+var_18]
0x1800ca9a3  xor     rcx, rsp; StackCookie
0x1800ca9a6  call    __security_check_cookie
0x1800ca9ab  mov     rbx, [rsp+458h+arg_8]
0x1800ca9b3  add     rsp, 450h
0x1800ca9ba  pop     rdi
0x1800ca9bb  retn
```
