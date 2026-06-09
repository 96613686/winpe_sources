# GetTempFile

- ea: `0x180009650`
- end: `0x1800096da`
- name: `GetTempFile`
- size: `138`
- prototype: `__int64 __fastcall(LPCWSTR lpPrefixString, LPWSTR lpTempFileName)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180009520`

## callees

- `0x180009650`
- `0x1800191f0`

## import_xrefs

- `KERNEL32!GetTempPath2W` at `0x180009689`
- `KERNEL32!GetTempPath2W` at `0x180009689`
- `KERNEL32!GetTempFileNameW` at `0x1800096a6`
- `KERNEL32!GetTempFileNameW` at `0x1800096a6`

## pseudocode

```c
_BOOL8 __fastcall GetTempFile(LPCWSTR lpPrefixString, LPWSTR lpTempFileName)
{
  _BOOL8 result; // rax
  WCHAR PathName[264]; // [rsp+20h] [rbp-228h] BYREF

  result = 0;
  if ( lpTempFileName )
  {
    *lpTempFileName = 0;
    if ( (unsigned int)GetTempPath2W(260, PathName) - 1 <= 0x103 )
    {
      if ( GetTempFileNameW(PathName, lpPrefixString, 0, lpTempFileName) )
        return 1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180009650  mov     [rsp+arg_10], rbx
0x180009655  push    rdi
0x180009656  sub     rsp, 240h
0x18000965d  mov     rax, cs:__security_cookie
0x180009664  xor     rax, rsp
0x180009667  mov     [rsp+248h+var_18], rax
0x18000966f  mov     rbx, rdx
0x180009672  mov     rdi, rcx
0x180009675  test    rdx, rdx
0x180009678  jz      short loc_1800096B7
0x18000967a  xor     eax, eax
0x18000967c  mov     ecx, 104h
0x180009681  mov     [rdx], ax
0x180009684  lea     rdx, [rsp+248h+PathName]
0x180009689  call    cs:__imp_GetTempPath2W
0x18000968f  dec     eax
0x180009691  cmp     eax, 103h
0x180009696  ja      short loc_1800096B7
0x180009698  mov     r9, rbx; lpTempFileName
0x18000969b  lea     rcx, [rsp+248h+PathName]; lpPathName
0x1800096a0  xor     r8d, r8d; uUnique
0x1800096a3  mov     rdx, rdi; lpPrefixString
0x1800096a6  call    cs:__imp_GetTempFileNameW
0x1800096ac  test    eax, eax
0x1800096ae  jz      short loc_1800096B7
0x1800096b0  mov     eax, 1
0x1800096b5  jmp     short loc_1800096B9
0x1800096b7  xor     eax, eax
0x1800096b9  mov     rcx, [rsp+248h+var_18]
0x1800096c1  xor     rcx, rsp; StackCookie
0x1800096c4  call    __security_check_cookie
0x1800096c9  mov     rbx, [rsp+248h+arg_10]
0x1800096d1  add     rsp, 240h
0x1800096d8  pop     rdi
0x1800096d9  retn
```
