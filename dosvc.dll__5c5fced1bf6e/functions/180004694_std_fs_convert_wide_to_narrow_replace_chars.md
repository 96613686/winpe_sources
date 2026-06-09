# __std_fs_convert_wide_to_narrow_replace_chars

- ea: `0x180004694`
- end: `0x18000475b`
- name: `__std_fs_convert_wide_to_narrow_replace_chars`
- size: `199`
- prototype: `__int64 __fastcall(UINT CodePage, LPCWCH lpWideCharStr, int cchWideChar, LPSTR lpMultiByteStr, int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180004488`

## callees

- `0x180004694`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800046ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004737`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800046ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004737`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800046e0`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180004729`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800046e0`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180004729`

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
0x180004694  mov     rax, rsp
0x180004697  push    rbx
0x180004698  push    rbp
0x180004699  push    rsi
0x18000469a  push    rdi
0x18000469b  push    r14
0x18000469d  sub     rsp, 50h
0x1800046a1  mov     r14d, [rsp+78h+arg_20]
0x1800046a9  mov     rbx, r9
0x1800046ac  mov     qword ptr [rax-40h], 0
0x1800046b4  mov     r9d, r8d; cchWideChar
0x1800046b7  mov     qword ptr [rax-48h], 0
0x1800046bf  mov     edi, r8d
0x1800046c2  mov     r8, rdx; lpWideCharStr
0x1800046c5  mov     [rax-50h], r14d
0x1800046c9  mov     rsi, rdx
0x1800046cc  mov     [rsp+78h+var_38], 0
0x1800046d5  mov     edx, 400h; dwFlags
0x1800046da  mov     [rax-58h], rbx
0x1800046de  mov     ebp, ecx
0x1800046e0  call    cs:__imp_WideCharToMultiByte
0x1800046e6  mov     dword ptr [rsp+78h+var_38], eax
0x1800046ea  test    eax, eax
0x1800046ec  jnz     short loc_1800046F6
0x1800046ee  call    cs:__imp_GetLastError
0x1800046f4  jmp     short loc_1800046F8
0x1800046f6  xor     eax, eax
0x1800046f8  mov     dword ptr [rsp+78h+var_38+4], eax
0x1800046fc  cmp     eax, 3ECh
0x180004701  jnz     short loc_18000474B
0x180004703  mov     [rsp+78h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18000470c  mov     r9d, edi; cchWideChar
0x18000470f  mov     [rsp+78h+lpDefaultChar], 0; lpDefaultChar
0x180004718  mov     r8, rsi; lpWideCharStr
0x18000471b  mov     [rsp+78h+cbMultiByte], r14d; cbMultiByte
0x180004720  xor     edx, edx; dwFlags
0x180004722  mov     ecx, ebp; CodePage
0x180004724  mov     [rsp+78h+lpMultiByteStr], rbx; lpMultiByteStr
0x180004729  call    cs:__imp_WideCharToMultiByte
0x18000472f  mov     dword ptr [rsp+78h+var_38], eax
0x180004733  test    eax, eax
0x180004735  jnz     short loc_180004743
0x180004737  call    cs:__imp_GetLastError
0x18000473d  mov     dword ptr [rsp+78h+var_38+4], eax
0x180004741  jmp     short loc_18000474B
0x180004743  mov     dword ptr [rsp+78h+var_38+4], 0
0x18000474b  mov     rax, [rsp+78h+var_38]
0x180004750  add     rsp, 50h
0x180004754  pop     r14
0x180004756  pop     rdi
0x180004757  pop     rsi
0x180004758  pop     rbp
0x180004759  pop     rbx
0x18000475a  retn
```
