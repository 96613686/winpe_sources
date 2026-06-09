# SetFileDsnDir

- ea: `0x1800134d4`
- end: `0x1800135ac`
- name: `SetFileDsnDir`
- size: `216`
- prototype: `__int64 __fastcall(wchar_t *lpData)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18000c440`

## callees

- `0x180004afc`
- `0x180004bac`
- `0x1800134d4`
- `0x180013998`
- `0x180013fa8`
- `0x180014ae0`

## pseudocode

```c
__int64 __fastcall SetFileDsnDir(wchar_t *lpData)
{
  __int64 v1; // rax
  wchar_t pszDest[264]; // [rsp+30h] [rbp-228h] BYREF

  if ( !lpData )
  {
    GetShellFilesDir(pszDest, 0x105u);
    v1 = -1;
    do
      ++v1;
    while ( pszDest[v1] );
    if ( (unsigned __int64)(v1 + 18) >= 0x104 )
    {
      PostInstError(12);
      return 0;
    }
    StringCchCatW(pszDest, 0x105u, L"\\ODBC");
    StringCchCatW(pszDest, 0x105u, L"\\Data Sources");
    lpData = pszDest;
  }
  return cpWritePrivateProfileString(
           HKEY_CURRENT_USER,
           (__int64)L"ODBC File DSN",
           L"DefaultDSNDir",
           1u,
           (BYTE *)lpData,
           (__int64)L"ODBC.INI");
}

```

## disassembly

```asm
0x1800134d4  push    rbx
0x1800134d6  sub     rsp, 250h
0x1800134dd  mov     rax, cs:__security_cookie
0x1800134e4  xor     rax, rsp
0x1800134e7  mov     [rsp+258h+var_18], rax
0x1800134ef  xor     ebx, ebx
0x1800134f1  test    rcx, rcx
0x1800134f4  jnz     short loc_180013562
0x1800134f6  mov     edx, 105h; uSize
0x1800134fb  lea     rcx, [rsp+258h+pszDest]; lpBuffer
0x180013500  call    GetShellFilesDir
0x180013505  lea     rcx, [rsp+258h+pszDest]
0x18001350a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001350e  inc     rax
0x180013511  cmp     [rcx+rax*2], bx
0x180013515  jnz     short loc_18001350E
0x180013517  add     rax, 12h
0x18001351b  cmp     rax, 104h
0x180013521  jb      short loc_180013531
0x180013523  mov     ecx, 0Ch
0x180013528  call    PostInstError
0x18001352d  xor     eax, eax
0x18001352f  jmp     short loc_180013593
0x180013531  lea     r8, aOdbc_0; "\\ODBC"
0x180013538  mov     edx, 105h; cchDest
0x18001353d  lea     rcx, [rsp+258h+pszDest]; pszDest
0x180013542  call    StringCchCatW
0x180013547  lea     r8, aDataSources; "\\Data Sources"
0x18001354e  mov     edx, 105h; cchDest
0x180013553  lea     rcx, [rsp+258h+pszDest]; pszDest
0x180013558  call    StringCchCatW
0x18001355d  lea     rcx, [rsp+258h+pszDest]
0x180013562  lea     rax, aOdbcIni; "ODBC.INI"
0x180013569  mov     r9d, 1
0x18001356f  mov     [rsp+258h+var_230], rax; __int64
0x180013574  lea     r8, aDefaultdsndir; "DefaultDSNDir"
0x18001357b  mov     [rsp+258h+lpData], rcx; lpData
0x180013580  lea     rdx, aOdbcFileDsn; "ODBC File DSN"
0x180013587  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18001358e  call    cpWritePrivateProfileString
0x180013593  mov     rcx, [rsp+258h+var_18]
0x18001359b  xor     rcx, rsp; StackCookie
0x18001359e  call    __security_check_cookie
0x1800135a3  add     rsp, 250h
0x1800135aa  pop     rbx
0x1800135ab  retn
```
