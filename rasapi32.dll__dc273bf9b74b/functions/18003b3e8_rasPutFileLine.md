# rasPutFileLine

- ea: `0x18003b3e8`
- end: `0x18003b48f`
- name: `rasPutFileLine`
- size: `167`
- prototype: `__int64 __fastcall(HANDLE hFile)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18003b31c`

## callees

- `0x18003b3e8`
- `0x18003b498`
- `0x1800ded50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b487`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b487`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x18003b43c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x18003b43c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003b45b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003b45b`

## pseudocode

```c
__int64 __fastcall rasPutFileLine(HANDLE hFile, const char *a2)
{
  DWORD v3; // eax
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-C38h] BYREF
  char pszDest[3088]; // [rsp+40h] [rbp-C28h] BYREF

  NumberOfBytesWritten = 0;
  if ( !StringCchPrintfA(pszDest, 0xC04u, "%s%s", a2, "\r\n") )
  {
    v3 = lstrlenA(pszDest);
    if ( WriteFile(hFile, pszDest, v3, &NumberOfBytesWritten, 0) )
      return 1;
    GetLastError();
  }
  return 0;
}

```

## disassembly

```asm
0x18003b3e8  push    rbx
0x18003b3ea  sub     rsp, 0C60h
0x18003b3f1  mov     rax, cs:__security_cookie
0x18003b3f8  xor     rax, rsp
0x18003b3fb  mov     [rsp+0C68h+var_18], rax
0x18003b403  mov     rbx, rcx
0x18003b406  mov     [rsp+0C68h+NumberOfBytesWritten], 0
0x18003b40e  lea     rax, asc_1800E521C; "\r\n"
0x18003b415  mov     r9, rdx
0x18003b418  mov     edx, 0C04h; cchDest
0x18003b41d  mov     [rsp+0C68h+lpOverlapped], rax
0x18003b422  lea     rcx, [rsp+0C68h+pszDest]; pszDest
0x18003b427  lea     r8, aSS_4; "%s%s"
0x18003b42e  call    StringCchPrintfA
0x18003b433  test    eax, eax
0x18003b435  jnz     short loc_18003B483
0x18003b437  lea     rcx, [rsp+0C68h+pszDest]; lpString
0x18003b43c  call    cs:__imp_lstrlenA
0x18003b442  lea     r9, [rsp+0C68h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18003b447  mov     [rsp+0C68h+lpOverlapped], 0; lpOverlapped
0x18003b450  mov     r8d, eax; nNumberOfBytesToWrite
0x18003b453  lea     rdx, [rsp+0C68h+pszDest]; lpBuffer
0x18003b458  mov     rcx, rbx; hFile
0x18003b45b  call    cs:__imp_WriteFile
0x18003b461  test    eax, eax
0x18003b463  jz      short loc_18003B487
0x18003b465  mov     eax, 1
0x18003b46a  mov     rcx, [rsp+0C68h+var_18]
0x18003b472  xor     rcx, rsp; StackCookie
0x18003b475  call    __security_check_cookie
0x18003b47a  add     rsp, 0C60h
0x18003b481  pop     rbx
0x18003b482  retn
0x18003b483  xor     eax, eax
0x18003b485  jmp     short loc_18003B46A
0x18003b487  call    cs:__imp_GetLastError
0x18003b48d  jmp     short loc_18003B483
```
