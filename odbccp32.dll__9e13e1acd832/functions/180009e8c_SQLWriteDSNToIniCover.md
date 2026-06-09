# SQLWriteDSNToIniCover

- ea: `0x180009e8c`
- end: `0x18000a0f0`
- name: `SQLWriteDSNToIniCover`
- size: `612`
- prototype: `_BOOL8 __fastcall(wchar_t *lpAppName, LPCWSTR lpszString)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000a100`

## callees

- `0x1800017c0`
- `0x180002e4c`
- `0x180004bac`
- `0x1800097d0`
- `0x180009dc0`
- `0x180009e8c`
- `0x18000a320`
- `0x18000a378`
- `0x180014ae0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180009ed7`
- `msvcrt!_wcsicmp` at `0x180009eef`
- `msvcrt!_wcsicmp` at `0x180009f37`
- `msvcrt!_wcsicmp` at `0x180009f8f`
- `msvcrt!_wcsicmp` at `0x180009feb`
- `msvcrt!_wcsicmp` at `0x18000a085`
- `msvcrt!_wcsicmp` at `0x180009ed7`
- `msvcrt!_wcsicmp` at `0x180009eef`
- `msvcrt!_wcsicmp` at `0x180009f37`
- `msvcrt!_wcsicmp` at `0x180009f8f`
- `msvcrt!_wcsicmp` at `0x180009feb`
- `msvcrt!_wcsicmp` at `0x18000a085`
- `KERNEL32!WritePrivateProfileStringW` at `0x18000a023`
- `KERNEL32!WritePrivateProfileStringW` at `0x18000a079`
- `KERNEL32!WritePrivateProfileStringW` at `0x18000a023`
- `KERNEL32!WritePrivateProfileStringW` at `0x18000a079`

## pseudocode

```c
_BOOL8 __fastcall SQLWriteDSNToIniCover(wchar_t *lpAppName, LPCWSTR lpszString)
{
  unsigned __int64 v4; // rax
  int v5; // eax
  const WCHAR *v6; // rdx
  wchar_t *v7; // r8
  const WCHAR *v8; // rcx
  int v10; // ecx
  wchar_t String2[264]; // [rsp+30h] [rbp-678h] BYREF
  WCHAR Buffer[264]; // [rsp+240h] [rbp-468h] BYREF
  wchar_t pszDest[264]; // [rsp+450h] [rbp-258h] BYREF

  if ( !SQLValidDSNCover(lpAppName) || !_wcsicmp(lpAppName, L"ODBC Data Sources") || !_wcsicmp(lpAppName, L"ODBC") )
  {
    v10 = 9;
    goto LABEL_25;
  }
  if ( !lpszString )
    goto LABEL_23;
  if ( !*lpszString )
    goto LABEL_23;
  v4 = -1;
  do
    ++v4;
  while ( lpszString[v4] );
  if ( v4 >= 0x104 )
  {
LABEL_23:
    v10 = 7;
LABEL_25:
    PostInstError(v10);
    return 0;
  }
  v5 = _wcsicmp(lpAppName, L"Default");
  v6 = lpAppName;
  v7 = (wchar_t *)L"ODBC.INI";
  if ( !v5 )
    v7 = (wchar_t *)L"ODBCINST.INI";
  v8 = L"ODBC Data Sources";
  if ( !v5 )
  {
    v8 = L"Default";
    v6 = L"Driver";
  }
  if ( (int)SQLGetPrivateProfileStringCover(v8, v6, (void *)&SubKey, String2, 260, v7) > 0
    && _wcsicmp(lpszString, String2)
    && !(unsigned int)SQLRemoveDSNFromIniCover(lpAppName) )
  {
    return 0;
  }
  SetString(Buffer, 260, 0x54Cu);
  StringCchPrintfW(pszDest, 0x104u, L"%s%s", lpszString, Buffer);
  if ( _wcsicmp(lpAppName, L"Default") )
  {
    if ( !SQLWritePrivateProfileStringW(L"ODBC Data Sources", lpAppName, lpszString, L"ODBC.INI") )
      return 0;
    WritePrivateProfileStringW(L"ODBC 32 bit Data Sources", lpAppName, pszDest, L"ODBC.INI");
  }
  SQLGetPrivateProfileStringCover(lpszString, L"Driver", (void *)&SubKey, String2, 260, (wchar_t *)L"ODBCINST.INI");
  if ( !SQLWritePrivateProfileStringW(lpAppName, L"Driver", String2, L"ODBC.INI") )
    return 0;
  WritePrivateProfileStringW(lpAppName, L"Driver32", String2, L"ODBC.INI");
  return _wcsicmp(lpAppName, L"Default")
      || SQLWritePrivateProfileStringW(lpAppName, L"Driver", lpszString, L"ODBCINST.INI");
}

```

## disassembly

```asm
0x180009e8c  mov     [rsp+arg_10], rbx
0x180009e91  push    rbp
0x180009e92  push    rsi
0x180009e93  push    rdi
0x180009e94  push    r12
0x180009e96  push    r13
0x180009e98  push    r14
0x180009e9a  push    r15
0x180009e9c  sub     rsp, 670h
0x180009ea3  mov     rax, cs:__security_cookie
0x180009eaa  xor     rax, rsp
0x180009ead  mov     [rsp+6A8h+var_48], rax
0x180009eb5  mov     rdi, rdx
0x180009eb8  mov     rbx, rcx
0x180009ebb  call    SQLValidDSNCover
0x180009ec0  xor     esi, esi
0x180009ec2  test    eax, eax
0x180009ec4  jz      loc_18000A0B9
0x180009eca  lea     r15, aOdbcDataSource; "ODBC Data Sources"
0x180009ed1  mov     rcx, rbx; String1
0x180009ed4  mov     rdx, r15; String2
0x180009ed7  call    cs:__imp__wcsicmp
0x180009edd  test    eax, eax
0x180009edf  jz      loc_18000A0B9
0x180009ee5  lea     rdx, aOdbc; "ODBC"
0x180009eec  mov     rcx, rbx; String1
0x180009eef  call    cs:__imp__wcsicmp
0x180009ef5  test    eax, eax
0x180009ef7  jz      loc_18000A0B9
0x180009efd  test    rdi, rdi
0x180009f00  jz      loc_18000A0B2
0x180009f06  cmp     [rdi], si
0x180009f09  jz      loc_18000A0B2
0x180009f0f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009f13  inc     rax
0x180009f16  cmp     [rdi+rax*2], si
0x180009f1a  jnz     short loc_180009F13
0x180009f1c  mov     ebp, 104h
0x180009f21  cmp     rax, rbp
0x180009f24  jnb     loc_18000A0B2
0x180009f2a  lea     r13, aDefault; "Default"
0x180009f31  mov     rcx, rbx; String1
0x180009f34  mov     rdx, r13; String2
0x180009f37  call    cs:__imp__wcsicmp
0x180009f3d  lea     rcx, aOdbcinstIni; "ODBCINST.INI"
0x180009f44  mov     rdx, rbx
0x180009f47  test    eax, eax
0x180009f49  lea     r14, aOdbcIni; "ODBC.INI"
0x180009f50  mov     r8, r14
0x180009f53  lea     r12, aDriver_0; "Driver"
0x180009f5a  cmovz   r8, rcx
0x180009f5e  lea     r9, [rsp+6A8h+String2]
0x180009f63  mov     [rsp+6A8h+var_680], r8
0x180009f68  mov     rcx, r15
0x180009f6b  cmovz   rcx, r13
0x180009f6f  mov     dword ptr [rsp+6A8h+var_688], ebp
0x180009f73  lea     r8, SubKey
0x180009f7a  cmovz   rdx, r12
0x180009f7e  call    SQLGetPrivateProfileStringCover
0x180009f83  test    eax, eax
0x180009f85  jle     short loc_180009FA9
0x180009f87  lea     rdx, [rsp+6A8h+String2]; String2
0x180009f8c  mov     rcx, rdi; String1
0x180009f8f  call    cs:__imp__wcsicmp
0x180009f95  test    eax, eax
0x180009f97  jz      short loc_180009FA9
0x180009f99  mov     rcx, rbx; lpAppName
0x180009f9c  call    SQLRemoveDSNFromIniCover
0x180009fa1  test    eax, eax
0x180009fa3  jz      loc_18000A0C3
0x180009fa9  mov     r8d, 54Ch
0x180009faf  lea     rcx, [rsp+6A8h+Buffer]; lpBuffer
0x180009fb7  mov     edx, ebp; cchBufferMax
0x180009fb9  call    SetString
0x180009fbe  lea     rax, [rsp+6A8h+Buffer]
0x180009fc6  mov     r9, rdi
0x180009fc9  lea     r8, aSS_1; "%s%s"
0x180009fd0  mov     [rsp+6A8h+var_688], rax
0x180009fd5  mov     rdx, rbp; cchDest
0x180009fd8  lea     rcx, [rsp+6A8h+pszDest]; pszDest
0x180009fe0  call    StringCchPrintfW
0x180009fe5  mov     rdx, r13; String2
0x180009fe8  mov     rcx, rbx; String1
0x180009feb  call    cs:__imp__wcsicmp
0x180009ff1  test    eax, eax
0x180009ff3  jz      short loc_18000A029
0x180009ff5  mov     r9, r14; lpszFilename
0x180009ff8  mov     r8, rdi; lpszString
0x180009ffb  mov     rdx, rbx; lpszEntry
0x180009ffe  mov     rcx, r15; lpszSection
0x18000a001  call    SQLWritePrivateProfileStringW
0x18000a006  test    eax, eax
0x18000a008  jz      loc_18000A0C3
0x18000a00e  mov     r9, r14; lpFileName
0x18000a011  lea     r8, [rsp+6A8h+pszDest]; lpString
0x18000a019  mov     rdx, rbx; lpKeyName
0x18000a01c  lea     rcx, aOdbc32BitDataS; "ODBC 32 bit Data Sources"
0x18000a023  call    cs:__imp_WritePrivateProfileStringW
0x18000a029  lea     r15, aOdbcinstIni; "ODBCINST.INI"
0x18000a030  mov     rdx, r12
0x18000a033  mov     [rsp+6A8h+var_680], r15
0x18000a038  lea     r9, [rsp+6A8h+String2]
0x18000a03d  lea     r8, SubKey
0x18000a044  mov     dword ptr [rsp+6A8h+var_688], ebp
0x18000a048  mov     rcx, rdi
0x18000a04b  call    SQLGetPrivateProfileStringCover
0x18000a050  mov     r9, r14; lpszFilename
0x18000a053  lea     r8, [rsp+6A8h+String2]; lpszString
0x18000a058  mov     rdx, r12; lpszEntry
0x18000a05b  mov     rcx, rbx; lpszSection
0x18000a05e  call    SQLWritePrivateProfileStringW
0x18000a063  test    eax, eax
0x18000a065  jz      short loc_18000A0C3
0x18000a067  mov     r9, r14; lpFileName
0x18000a06a  lea     r8, [rsp+6A8h+String2]; lpString
0x18000a06f  lea     rdx, aDriver32; "Driver32"
0x18000a076  mov     rcx, rbx; lpAppName
0x18000a079  call    cs:__imp_WritePrivateProfileStringW
0x18000a07f  mov     rdx, r13; String2
0x18000a082  mov     rcx, rbx; String1
0x18000a085  call    cs:__imp__wcsicmp
0x18000a08b  test    eax, eax
0x18000a08d  jnz     short loc_18000A0AB
0x18000a08f  mov     r9, r15; lpszFilename
0x18000a092  mov     r8, rdi; lpszString
0x18000a095  mov     rdx, r12; lpszEntry
0x18000a098  mov     rcx, rbx; lpszSection
0x18000a09b  call    SQLWritePrivateProfileStringW
0x18000a0a0  test    eax, eax
0x18000a0a2  mov     ecx, esi
0x18000a0a4  setnz   cl
0x18000a0a7  mov     eax, ecx
0x18000a0a9  jmp     short loc_18000A0C5
0x18000a0ab  mov     eax, 1
0x18000a0b0  jmp     short loc_18000A0C5
0x18000a0b2  mov     ecx, 7
0x18000a0b7  jmp     short loc_18000A0BE
0x18000a0b9  mov     ecx, 9
0x18000a0be  call    PostInstError
0x18000a0c3  xor     eax, eax
0x18000a0c5  mov     rcx, [rsp+6A8h+var_48]
0x18000a0cd  xor     rcx, rsp; StackCookie
0x18000a0d0  call    __security_check_cookie
0x18000a0d5  mov     rbx, [rsp+6A8h+arg_10]
0x18000a0dd  add     rsp, 670h
0x18000a0e4  pop     r15
0x18000a0e6  pop     r14
0x18000a0e8  pop     r13
0x18000a0ea  pop     r12
0x18000a0ec  pop     rdi
0x18000a0ed  pop     rsi
0x18000a0ee  pop     rbp
0x18000a0ef  retn
```
