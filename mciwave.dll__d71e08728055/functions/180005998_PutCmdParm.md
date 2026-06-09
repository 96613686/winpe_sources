# PutCmdParm

- ea: `0x180005998`
- end: `0x180005a87`
- name: `PutCmdParm`
- size: `239`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180005680`

## callees

- `0x180005998`
- `0x180005a90`
- `0x180005c60`

## import_xrefs

- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x1800059e8`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x1800059e8`
- `KERNEL32!WriteProfileStringW` at `0x180005a60`
- `KERNEL32!WriteProfileStringW` at `0x180005a60`

## pseudocode

```c
DWORD __fastcall PutCmdParm(__int64 a1, unsigned int a2)
{
  __int64 v2; // rbx
  DWORD result; // eax
  WCHAR v5; // cx
  WCHAR *v6; // rax
  WCHAR *v7; // rcx
  wchar_t pszDest[16]; // [rsp+30h] [rbp-148h] BYREF
  WCHAR ReturnedString[136]; // [rsp+50h] [rbp-128h] BYREF

  v2 = qword_1800085B8;
  result = GetPrivateProfileStringW(
             *(LPCWSTR *)(qword_1800085B8 + 4),
             *(LPCWSTR *)(qword_1800085B8 + 12),
             &aszNULL,
             ReturnedString,
             0x7Eu,
             aszSystemIni);
  if ( result )
  {
    v5 = ReturnedString[0];
    v6 = ReturnedString;
    while ( v5 && v5 != 32 )
      v5 = *++v6;
    while ( *v6 == 32 )
      ++v6;
    if ( *v6 )
    {
      do
        v7 = v6--;
      while ( *v6 == 32 );
      *v7 = 0;
    }
    StringCchPrintfW(pszDest, 0xAu, aszWordFormat, a2);
    return WriteProfileStringW(ReturnedString, *(LPCWSTR *)(v2 + 12), pszDest);
  }
  return result;
}

```

## disassembly

```asm
0x180005998  mov     [rsp+arg_0], rbx
0x18000599d  push    rdi
0x18000599e  sub     rsp, 170h
0x1800059a5  mov     rax, cs:__security_cookie
0x1800059ac  xor     rax, rsp
0x1800059af  mov     [rsp+178h+var_18], rax
0x1800059b7  mov     rbx, cs:qword_1800085B8
0x1800059be  lea     rax, aszSystemIni; "system.ini"
0x1800059c5  mov     edi, edx
0x1800059c7  mov     [rsp+178h+lpFileName], rax; lpFileName
0x1800059cc  lea     r9, [rsp+178h+ReturnedString]; lpReturnedString
0x1800059d1  mov     [rsp+178h+nSize], 7Eh ; '~'; nSize
0x1800059d9  lea     r8, aszNULL; lpDefault
0x1800059e0  mov     rdx, [rbx+0Ch]; lpKeyName
0x1800059e4  mov     rcx, [rbx+4]; lpAppName
0x1800059e8  call    cs:__imp_GetPrivateProfileStringW
0x1800059ee  xor     r8d, r8d
0x1800059f1  test    eax, eax
0x1800059f3  jz      short loc_180005A66
0x1800059f5  movzx   ecx, [rsp+178h+ReturnedString]
0x1800059fa  lea     rax, [rsp+178h+ReturnedString]
0x1800059ff  mov     dx, 20h ; ' '
0x180005a03  jmp     short loc_180005A11
0x180005a05  cmp     cx, dx
0x180005a08  jz      short loc_180005A1C
0x180005a0a  add     rax, 2
0x180005a0e  movzx   ecx, word ptr [rax]
0x180005a11  test    cx, cx
0x180005a14  jnz     short loc_180005A05
0x180005a16  jmp     short loc_180005A1C
0x180005a18  add     rax, 2
0x180005a1c  movzx   ecx, word ptr [rax]
0x180005a1f  cmp     cx, dx
0x180005a22  jz      short loc_180005A18
0x180005a24  test    cx, cx
0x180005a27  jz      short loc_180005A39
0x180005a29  mov     rcx, rax
0x180005a2c  sub     rax, 2
0x180005a30  cmp     [rax], dx
0x180005a33  jz      short loc_180005A29
0x180005a35  mov     [rcx], r8w
0x180005a39  mov     r9d, edi
0x180005a3c  lea     r8, aszWordFormat; "%u"
0x180005a43  mov     edx, 0Ah; cchDest
0x180005a48  lea     rcx, [rsp+178h+pszDest]; pszDest
0x180005a4d  call    StringCchPrintfW
0x180005a52  mov     rdx, [rbx+0Ch]; lpKeyName
0x180005a56  lea     r8, [rsp+178h+pszDest]; lpString
0x180005a5b  lea     rcx, [rsp+178h+ReturnedString]; lpAppName
0x180005a60  call    cs:__imp_WriteProfileStringW
0x180005a66  mov     rcx, [rsp+178h+var_18]
0x180005a6e  xor     rcx, rsp; StackCookie
0x180005a71  call    __security_check_cookie
0x180005a76  mov     rbx, [rsp+178h+arg_0]
0x180005a7e  add     rsp, 170h
0x180005a85  pop     rdi
0x180005a86  retn
```
