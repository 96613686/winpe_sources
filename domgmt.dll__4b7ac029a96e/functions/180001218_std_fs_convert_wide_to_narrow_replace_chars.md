# __std_fs_convert_wide_to_narrow_replace_chars

- ea: `0x180001218`
- end: `0x1800012df`
- name: `__std_fs_convert_wide_to_narrow_replace_chars`
- size: `199`
- prototype: `__int64 __fastcall(UINT CodePage, LPCWCH lpWideCharStr, int cchWideChar, LPSTR lpMultiByteStr, int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800075dc`

## callees

- `0x180001218`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001272`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800012bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001272`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800012bb`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180001264`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800012ad`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180001264`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800012ad`

## pseudocode

```c
__int64 __fastcall _std_fs_convert_wide_to_narrow_replace_chars(
        UINT CodePage,
        LPCWCH lpWideCharStr,
        int cchWideChar,
        LPSTR lpMultiByteStr,
        int cbMultiByte)
{
  DWORD LastError; // eax
  __int64 v11; // [rsp+40h] [rbp-38h]

  LODWORD(v11) = WideCharToMultiByte(CodePage, 0x400u, lpWideCharStr, cchWideChar, lpMultiByteStr, cbMultiByte, 0, 0);
  if ( (_DWORD)v11 )
    LastError = 0;
  else
    LastError = GetLastError();
  HIDWORD(v11) = LastError;
  if ( LastError == 1004 )
  {
    LODWORD(v11) = WideCharToMultiByte(CodePage, 0, lpWideCharStr, cchWideChar, lpMultiByteStr, cbMultiByte, 0, 0);
    if ( (_DWORD)v11 )
      HIDWORD(v11) = 0;
    else
      HIDWORD(v11) = GetLastError();
  }
  return v11;
}

```

## disassembly

```asm
0x180001218  mov     rax, rsp
0x18000121b  push    rbx
0x18000121c  push    rbp
0x18000121d  push    rsi
0x18000121e  push    rdi
0x18000121f  push    r14
0x180001221  sub     rsp, 50h
0x180001225  mov     r14d, [rsp+78h+arg_20]
0x18000122d  mov     rbx, r9
0x180001230  mov     qword ptr [rax-40h], 0
0x180001238  mov     r9d, r8d; cchWideChar
0x18000123b  mov     qword ptr [rax-48h], 0
0x180001243  mov     edi, r8d
0x180001246  mov     r8, rdx; lpWideCharStr
0x180001249  mov     [rax-50h], r14d
0x18000124d  mov     rsi, rdx
0x180001250  mov     [rsp+78h+var_38], 0
0x180001259  mov     edx, 400h; dwFlags
0x18000125e  mov     [rax-58h], rbx
0x180001262  mov     ebp, ecx
0x180001264  call    cs:__imp_WideCharToMultiByte
0x18000126a  mov     dword ptr [rsp+78h+var_38], eax
0x18000126e  test    eax, eax
0x180001270  jnz     short loc_18000127A
0x180001272  call    cs:__imp_GetLastError
0x180001278  jmp     short loc_18000127C
0x18000127a  xor     eax, eax
0x18000127c  mov     dword ptr [rsp+78h+var_38+4], eax
0x180001280  cmp     eax, 3ECh
0x180001285  jnz     short loc_1800012CF
0x180001287  mov     [rsp+78h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x180001290  mov     r9d, edi; cchWideChar
0x180001293  mov     [rsp+78h+lpDefaultChar], 0; lpDefaultChar
0x18000129c  mov     r8, rsi; lpWideCharStr
0x18000129f  mov     [rsp+78h+cbMultiByte], r14d; cbMultiByte
0x1800012a4  xor     edx, edx; dwFlags
0x1800012a6  mov     ecx, ebp; CodePage
0x1800012a8  mov     [rsp+78h+lpMultiByteStr], rbx; lpMultiByteStr
0x1800012ad  call    cs:__imp_WideCharToMultiByte
0x1800012b3  mov     dword ptr [rsp+78h+var_38], eax
0x1800012b7  test    eax, eax
0x1800012b9  jnz     short loc_1800012C7
0x1800012bb  call    cs:__imp_GetLastError
0x1800012c1  mov     dword ptr [rsp+78h+var_38+4], eax
0x1800012c5  jmp     short loc_1800012CF
0x1800012c7  mov     dword ptr [rsp+78h+var_38+4], 0
0x1800012cf  mov     rax, [rsp+78h+var_38]
0x1800012d4  add     rsp, 50h
0x1800012d8  pop     r14
0x1800012da  pop     rdi
0x1800012db  pop     rsi
0x1800012dc  pop     rbp
0x1800012dd  pop     rbx
0x1800012de  retn
```
