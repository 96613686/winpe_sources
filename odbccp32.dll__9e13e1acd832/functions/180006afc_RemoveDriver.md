# RemoveDriver

- ea: `0x180006afc`
- end: `0x180006daf`
- name: `RemoveDriver`
- size: `691`
- prototype: `__int64 __fastcall(HWND hWnd, wchar_t *String1, int, char *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x180009a88`

## callees

- `0x180001010`
- `0x1800017c0`
- `0x180002940`
- `0x180002e4c`
- `0x18000663c`
- `0x180006afc`
- `0x180006db8`
- `0x1800085c8`
- `0x18000a320`
- `0x18000a378`
- `0x180013fa8`
- `0x180014ae0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180006cc2`
- `msvcrt!_wcsicmp` at `0x180006cc2`
- `msvcrt!calloc` at `0x180006bf8`
- `msvcrt!calloc` at `0x180006bf8`
- `KERNEL32!WritePrivateProfileStringW` at `0x180006d62`
- `KERNEL32!WritePrivateProfileStringW` at `0x180006d7a`
- `KERNEL32!WritePrivateProfileStringW` at `0x180006d62`
- `KERNEL32!WritePrivateProfileStringW` at `0x180006d7a`

## pseudocode

```c
__int64 __fastcall RemoveDriver(HWND hWnd, wchar_t *String1, int a3, char *a4)
{
  char *v5; // rsi
  unsigned int v8; // ebx
  int v9; // eax
  wchar_t *v10; // r14
  BYTE Data[4]; // [rsp+50h] [rbp-B0h] BYREF
  char v13; // [rsp+54h] [rbp-ACh] BYREF
  wchar_t pszDest[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Buffer[264]; // [rsp+270h] [rbp+170h] BYREF

  *(_DWORD *)Data = 0;
  v5 = &v13;
  if ( a4 )
    v5 = a4;
  v8 = 1;
  if ( (int)cpGetPrivateProfileString(
              HKEY_LOCAL_MACHINE,
              String1,
              L"UsageCount",
              (void *)&SubKey,
              0x10u,
              0,
              (WCHAR *)Data,
              4,
              (__int64)L"ODBCINST.INI",
              0) <= 0 )
  {
    *(_DWORD *)v5 = 1;
  }
  else
  {
    if ( *(_DWORD *)Data <= 1u )
    {
      v9 = 0;
      *(_DWORD *)Data = 0;
    }
    else
    {
      --*(_DWORD *)Data;
      cpWritePrivateProfileString(
        HKEY_LOCAL_MACHINE,
        (__int64)String1,
        L"UsageCount",
        4u,
        Data,
        (__int64)L"ODBCINST.INI");
      v9 = *(_DWORD *)Data;
    }
    *(_DWORD *)v5 = v9;
    if ( !v9 )
    {
      v10 = (wchar_t *)calloc(0x410u, 1u);
      SQLConfigDriverCover(0, 0, 0, 0);
      if ( !a3
        || (unsigned int)RemoveDrvrDSNs(hWnd, HKEY_CURRENT_USER, String1)
        && (unsigned int)RemoveDrvrDSNs(hWnd, HKEY_LOCAL_MACHINE, String1) )
      {
        SQLWritePrivateProfileStringW(String1, 0, 0, L"ODBCINST.INI");
        SQLWritePrivateProfileStringW(L"ODBC Drivers", String1, 0, L"ODBCINST.INI");
        if ( (int)SQLGetPrivateProfileStringCover(L"Default", L"Driver", &SubKey, v10 + 260, 260, L"ODBCINST.INI") > 0
          && !_wcsicmp(v10 + 260, String1) )
        {
          SQLWritePrivateProfileStringW(L"Default", 0, 0, L"ODBCINST.INI");
        }
        if ( !(unsigned int)SQLGetPrivateProfileStringCover(
                              L"ODBC Drivers",
                              0,
                              &SubKey,
                              v10 + 260,
                              260,
                              L"ODBCINST.INI") )
          SQLWritePrivateProfileStringW(L"ODBC Drivers", 0, 0, L"ODBCINST.INI");
        CleanupRegistry();
        SetString(Buffer, 260);
        StringCchPrintfW(pszDest, 0x104u, L"%s%s", String1, Buffer);
        WritePrivateProfileStringW(pszDest, 0, 0, L"ODBCINST.INI");
        WritePrivateProfileStringW(L"ODBC 32 bit Drivers", pszDest, 0, L"ODBCINST.INI");
      }
      else
      {
        v8 = 0;
      }
      OFree(v10);
    }
  }
  return v8;
}

```

## disassembly

```asm
0x180006afc  push    rbp
0x180006afe  push    rbx
0x180006aff  push    rsi
0x180006b00  push    rdi
0x180006b01  push    r12
0x180006b03  push    r14
0x180006b05  push    r15
0x180006b07  lea     rbp, [rsp-390h]
0x180006b0f  sub     rsp, 490h
0x180006b16  mov     rax, cs:__security_cookie
0x180006b1d  xor     rax, rsp
0x180006b20  mov     [rbp+3C0h+var_40], rax
0x180006b27  mov     [rsp+4C0h+var_478], 0
0x180006b30  lea     rax, [rsp+4C0h+Data]
0x180006b35  test    r9, r9
0x180006b38  mov     dword ptr [rsp+4C0h+Data], 0
0x180006b40  mov     r12d, r8d
0x180006b43  lea     r14, aOdbcinstIni; "ODBCINST.INI"
0x180006b4a  mov     [rsp+4C0h+var_480], r14
0x180006b4f  lea     rsi, [rsp+4C0h+var_46C]
0x180006b54  mov     [rsp+4C0h+var_488], 4
0x180006b5c  lea     r8, aUsagecount; "UsageCount"
0x180006b63  mov     [rsp+4C0h+var_490], rax
0x180006b68  mov     r15, rcx
0x180006b6b  cmovnz  rsi, r9
0x180006b6f  mov     qword ptr [rsp+4C0h+var_498], 0
0x180006b78  lea     r9, SubKey
0x180006b7f  mov     dword ptr [rsp+4C0h+lpData], 10h
0x180006b87  mov     rcx, 0FFFFFFFF80000002h
0x180006b8e  mov     rdi, rdx
0x180006b91  call    cpGetPrivateProfileString
0x180006b96  mov     ebx, 1
0x180006b9b  test    eax, eax
0x180006b9d  jle     loc_180006D8A
0x180006ba3  mov     eax, dword ptr [rsp+4C0h+Data]
0x180006ba7  cmp     eax, ebx
0x180006ba9  jbe     short loc_180006BE0
0x180006bab  dec     eax
0x180006bad  mov     qword ptr [rsp+4C0h+var_498], r14; __int64
0x180006bb2  mov     dword ptr [rsp+4C0h+Data], eax
0x180006bb6  lea     r9d, [rbx+3]
0x180006bba  lea     rax, [rsp+4C0h+Data]
0x180006bbf  mov     rdx, rdi
0x180006bc2  lea     r8, aUsagecount; "UsageCount"
0x180006bc9  mov     [rsp+4C0h+lpData], rax; lpData
0x180006bce  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180006bd5  call    cpWritePrivateProfileString
0x180006bda  mov     eax, dword ptr [rsp+4C0h+Data]
0x180006bde  jmp     short loc_180006BE6
0x180006be0  xor     eax, eax
0x180006be2  mov     dword ptr [rsp+4C0h+Data], eax
0x180006be6  mov     [rsi], eax
0x180006be8  test    eax, eax
0x180006bea  jnz     loc_180006D8C
0x180006bf0  mov     rdx, rbx; Size
0x180006bf3  mov     ecx, 410h; Count
0x180006bf8  call    cs:__imp_calloc
0x180006bfe  xor     ecx, ecx; hWnd
0x180006c00  xor     r9d, r9d
0x180006c03  mov     [rsp+4C0h+var_490], rcx; __int64
0x180006c08  mov     r8, rdi
0x180006c0b  mov     [rsp+4C0h+var_498], cx; __int16
0x180006c10  mov     r14, rax
0x180006c13  mov     [rsp+4C0h+lpData], rcx; lpWideCharStr
0x180006c18  lea     edx, [rcx+2]
0x180006c1b  call    SQLConfigDriverCover
0x180006c20  test    r12d, r12d
0x180006c23  jz      short loc_180006C58
0x180006c25  mov     r8, rdi; String1
0x180006c28  mov     rdx, 0FFFFFFFF80000001h; hKey
0x180006c2f  mov     rcx, r15; hWnd
0x180006c32  call    RemoveDrvrDSNs
0x180006c37  test    eax, eax
0x180006c39  jz      short loc_180006C51
0x180006c3b  mov     r8, rdi; String1
0x180006c3e  mov     rdx, 0FFFFFFFF80000002h; hKey
0x180006c45  mov     rcx, r15; hWnd
0x180006c48  call    RemoveDrvrDSNs
0x180006c4d  test    eax, eax
0x180006c4f  jnz     short loc_180006C58
0x180006c51  xor     ebx, ebx
0x180006c53  jmp     loc_180006D80
0x180006c58  lea     r15, aOdbcinstIni; "ODBCINST.INI"
0x180006c5f  xor     r8d, r8d; lpszString
0x180006c62  mov     r9, r15; lpszFilename
0x180006c65  lea     rsi, [r14+208h]
0x180006c6c  xor     edx, edx; lpszEntry
0x180006c6e  mov     rcx, rdi; lpszSection
0x180006c71  call    SQLWritePrivateProfileStringW
0x180006c76  lea     r12, aOdbcDrivers; "ODBC Drivers"
0x180006c7d  mov     r9, r15; lpszFilename
0x180006c80  mov     rcx, r12; lpszSection
0x180006c83  xor     r8d, r8d; lpszString
0x180006c86  mov     rdx, rdi; lpszEntry
0x180006c89  call    SQLWritePrivateProfileStringW
0x180006c8e  mov     r9, rsi
0x180006c91  mov     qword ptr [rsp+4C0h+var_498], r15
0x180006c96  lea     r8, SubKey
0x180006c9d  mov     dword ptr [rsp+4C0h+lpData], 104h
0x180006ca5  lea     rdx, aDriver_0; "Driver"
0x180006cac  lea     rcx, aDefault; "Default"
0x180006cb3  call    SQLGetPrivateProfileStringCover
0x180006cb8  test    eax, eax
0x180006cba  jle     short loc_180006CE0
0x180006cbc  mov     rdx, rdi; String2
0x180006cbf  mov     rcx, rsi; String1
0x180006cc2  call    cs:__imp__wcsicmp
0x180006cc8  test    eax, eax
0x180006cca  jnz     short loc_180006CE0
0x180006ccc  mov     r9, r15; lpszFilename
0x180006ccf  lea     rcx, aDefault; "Default"
0x180006cd6  xor     r8d, r8d; lpszString
0x180006cd9  xor     edx, edx; lpszEntry
0x180006cdb  call    SQLWritePrivateProfileStringW
0x180006ce0  mov     qword ptr [rsp+4C0h+var_498], r15
0x180006ce5  lea     r8, SubKey
0x180006cec  mov     r9, rsi
0x180006cef  mov     dword ptr [rsp+4C0h+lpData], 104h
0x180006cf7  xor     edx, edx
0x180006cf9  mov     rcx, r12
0x180006cfc  call    SQLGetPrivateProfileStringCover
0x180006d01  test    eax, eax
0x180006d03  jnz     short loc_180006D15
0x180006d05  mov     r9, r15; lpszFilename
0x180006d08  xor     r8d, r8d; lpszString
0x180006d0b  xor     edx, edx; lpszEntry
0x180006d0d  mov     rcx, r12; lpszSection
0x180006d10  call    SQLWritePrivateProfileStringW
0x180006d15  call    CleanupRegistry
0x180006d1a  mov     esi, 104h
0x180006d1f  lea     rcx, [rbp+3C0h+Buffer]; lpBuffer
0x180006d26  mov     edx, esi; cchBufferMax
0x180006d28  mov     r8d, 54Ch
0x180006d2e  call    SetString
0x180006d33  lea     rax, [rbp+3C0h+Buffer]
0x180006d3a  mov     r9, rdi
0x180006d3d  lea     r8, aSS_1; "%s%s"
0x180006d44  mov     [rsp+4C0h+lpData], rax
0x180006d49  mov     edx, esi; cchDest
0x180006d4b  lea     rcx, [rsp+4C0h+pszDest]; pszDest
0x180006d50  call    StringCchPrintfW
0x180006d55  mov     r9, r15; lpFileName
0x180006d58  lea     rcx, [rsp+4C0h+pszDest]; lpAppName
0x180006d5d  xor     r8d, r8d; lpString
0x180006d60  xor     edx, edx; lpKeyName
0x180006d62  call    cs:__imp_WritePrivateProfileStringW
0x180006d68  mov     r9, r15; lpFileName
0x180006d6b  lea     rdx, [rsp+4C0h+pszDest]; lpKeyName
0x180006d70  xor     r8d, r8d; lpString
0x180006d73  lea     rcx, aOdbc32BitDrive; "ODBC 32 bit Drivers"
0x180006d7a  call    cs:__imp_WritePrivateProfileStringW
0x180006d80  mov     rcx, r14
0x180006d83  call    OFree
0x180006d88  jmp     short loc_180006D8C
0x180006d8a  mov     [rsi], ebx
0x180006d8c  mov     eax, ebx
0x180006d8e  mov     rcx, [rbp+3C0h+var_40]
0x180006d95  xor     rcx, rsp; StackCookie
0x180006d98  call    __security_check_cookie
0x180006d9d  add     rsp, 490h
0x180006da4  pop     r15
0x180006da6  pop     r14
0x180006da8  pop     r12
0x180006daa  pop     rdi
0x180006dab  pop     rsi
0x180006dac  pop     rbx
0x180006dad  pop     rbp
0x180006dae  retn
```
