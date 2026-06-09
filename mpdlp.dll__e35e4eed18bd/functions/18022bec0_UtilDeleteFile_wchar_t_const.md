# UtilDeleteFile(wchar_t const *)

- ea: `0x18022bec0`
- end: `0x18022bf27`
- name: `?UtilDeleteFile@@YAJPEB_W@Z`
- size: `103`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800b05b0`
- `0x1800b06e4`
- `0x18020546c`

## callees

- `0x18022bec0`

## import_xrefs

- `KERNEL32!SetFileAttributesW` at `0x18022bef4`
- `KERNEL32!SetFileAttributesW` at `0x18022bef4`
- `KERNEL32!DeleteFileW` at `0x18022bec9`
- `KERNEL32!DeleteFileW` at `0x18022bf15`
- `KERNEL32!DeleteFileW` at `0x18022bec9`
- `KERNEL32!DeleteFileW` at `0x18022bf15`
- `KERNEL32!GetLastError` at `0x18022bed3`
- `KERNEL32!GetLastError` at `0x18022befe`
- `KERNEL32!GetLastError` at `0x18022bed3`
- `KERNEL32!GetLastError` at `0x18022befe`

## pseudocode

```c
signed int __fastcall UtilDeleteFile(LPCWSTR lpFileName)
{
  signed int result; // eax

  if ( DeleteFileW(lpFileName) )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    result = (unsigned __int16)result | 0x80070000;
  if ( result == -2147024891 )
  {
    if ( SetFileAttributesW(lpFileName, 0x80u) && DeleteFileW(lpFileName) )
      return 0;
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x18022bec0  push    rbx
0x18022bec2  sub     rsp, 20h
0x18022bec6  mov     rbx, rcx
0x18022bec9  call    cs:__imp_DeleteFileW
0x18022becf  test    eax, eax
0x18022bed1  jnz     short loc_18022BF1F
0x18022bed3  call    cs:__imp_GetLastError
0x18022bed9  test    eax, eax
0x18022bedb  jle     short loc_18022BEE5
0x18022bedd  movzx   eax, ax
0x18022bee0  or      eax, 80070000h
0x18022bee5  cmp     eax, 80070005h
0x18022beea  jnz     short loc_18022BF21
0x18022beec  mov     edx, 80h; dwFileAttributes
0x18022bef1  mov     rcx, rbx; lpFileName
0x18022bef4  call    cs:__imp_SetFileAttributesW
0x18022befa  test    eax, eax
0x18022befc  jnz     short loc_18022BF12
0x18022befe  call    cs:__imp_GetLastError
0x18022bf04  test    eax, eax
0x18022bf06  jle     short loc_18022BF21
0x18022bf08  movzx   eax, ax
0x18022bf0b  or      eax, 80070000h
0x18022bf10  jmp     short loc_18022BF21
0x18022bf12  mov     rcx, rbx; lpFileName
0x18022bf15  call    cs:__imp_DeleteFileW
0x18022bf1b  test    eax, eax
0x18022bf1d  jz      short loc_18022BEFE
0x18022bf1f  xor     eax, eax
0x18022bf21  add     rsp, 20h
0x18022bf25  pop     rbx
0x18022bf26  retn
```
