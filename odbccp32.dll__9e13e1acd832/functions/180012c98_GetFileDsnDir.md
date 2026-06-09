# GetFileDsnDir

- ea: `0x180012c98`
- end: `0x180012e87`
- name: `GetFileDsnDir`
- size: `495`
- prototype: `int __fastcall(LPWSTR lpBuffer, int uSize)`
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x18000c440`
- `0x180012b14`
- `0x18001484c`

## callees

- `0x180001010`
- `0x180004afc`
- `0x180004bac`
- `0x180012c98`
- `0x180013998`
- `0x180013db4`
- `0x180014ae0`

## import_xrefs

- `msvcrt!_wstat` at `0x180012e3f`
- `msvcrt!_wstat` at `0x180012e3f`
- `msvcrt!_waccess` at `0x180012d24`
- `msvcrt!_waccess` at `0x180012d95`
- `msvcrt!_waccess` at `0x180012d24`
- `msvcrt!_waccess` at `0x180012d95`
- `SHELL32!SHGetSpecialFolderPathW` at `0x180012dbf`
- `SHELL32!SHGetSpecialFolderPathW` at `0x180012dbf`

## pseudocode

```c
int __fastcall GetFileDsnDir(LPWSTR lpBuffer, int uSize)
{
  unsigned __int64 v2; // rdi
  int result; // eax
  int PrivateProfileString; // eax
  DWORD v6; // esi
  __int64 v7; // rax
  DWORD v8; // [rsp+50h] [rbp-58h] BYREF
  _OWORD v9[3]; // [rsp+58h] [rbp-50h] BYREF

  v2 = (unsigned int)uSize;
  *lpBuffer = 0;
  v8 = 0;
  if ( !(unsigned int)cpGetPrivateProfileString(
                        HKEY_CURRENT_USER,
                        L"ODBC File DSN",
                        L"DefaultDSNDir",
                        (void *)&SubKey,
                        2u,
                        0,
                        lpBuffer,
                        uSize,
                        (__int64)L"ODBC.INI",
                        &v8)
    || !v8
    || (result = _waccess(lpBuffer, 0)) != 0 && (result = ODBCCreatePath(lpBuffer)) == 0 )
  {
    PrivateProfileString = cpGetPrivateProfileString(
                             HKEY_LOCAL_MACHINE,
                             L"ODBC File DSN",
                             L"DefaultDSNDir",
                             (void *)&SubKey,
                             2u,
                             0,
                             lpBuffer,
                             v2,
                             (__int64)L"ODBC.INI",
                             &v8);
    v6 = v8;
    if ( !PrivateProfileString
      || !v8
      || (result = _waccess(lpBuffer, 0)) != 0 && (result = ODBCCreatePath(lpBuffer)) == 0 )
    {
      result = SHGetSpecialFolderPathW(0, lpBuffer, 5, 0);
      if ( !result && !v6 )
      {
        memset(v9, 0, sizeof(v9));
        GetShellFilesDir(lpBuffer, v2);
        v7 = -1;
        do
          ++v7;
        while ( lpBuffer[v7] );
        if ( v7 + 18 < v2 )
        {
          StringCchCatW(lpBuffer, v2, L"\\ODBC");
          StringCchCatW(lpBuffer, v2, L"\\Data Sources");
          result = _wstat(lpBuffer, v9);
          if ( result )
          {
            result = ODBCCreatePath(lpBuffer);
            if ( !result )
              return GetShellFilesDir(lpBuffer, v2);
          }
        }
        else
        {
          return PostInstError(12);
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180012c98  mov     r11, rsp
0x180012c9b  mov     [r11+18h], rbx
0x180012c9f  mov     [r11+20h], rbp
0x180012ca3  push    rsi
0x180012ca4  push    rdi
0x180012ca5  push    r14
0x180012ca7  sub     rsp, 90h
0x180012cae  mov     rax, cs:__security_cookie
0x180012cb5  xor     rax, rsp
0x180012cb8  mov     [rsp+0A8h+var_20], rax
0x180012cc0  xor     ebp, ebp
0x180012cc2  mov     edi, edx
0x180012cc4  lea     rax, [r11-58h]
0x180012cc8  mov     [rcx], bp
0x180012ccb  mov     [r11-60h], rax
0x180012ccf  lea     r14, aOdbcIni; "ODBC.INI"
0x180012cd6  mov     [r11-68h], r14
0x180012cda  lea     r9, SubKey
0x180012ce1  mov     [rsp+0A8h+var_70], edi
0x180012ce5  lea     esi, [rbp+2]
0x180012ce8  mov     [r11-78h], rcx
0x180012cec  lea     r8, aDefaultdsndir; "DefaultDSNDir"
0x180012cf3  mov     rbx, rcx
0x180012cf6  mov     [r11-80h], rbp
0x180012cfa  mov     rcx, 0FFFFFFFF80000001h
0x180012d01  mov     [rsp+0A8h+var_88], esi
0x180012d05  lea     rdx, aOdbcFileDsn; "ODBC File DSN"
0x180012d0c  mov     [rsp+0A8h+var_58], ebp
0x180012d10  call    cpGetPrivateProfileString
0x180012d15  test    eax, eax
0x180012d17  jz      short loc_180012D42
0x180012d19  cmp     [rsp+0A8h+var_58], ebp
0x180012d1d  jz      short loc_180012D42
0x180012d1f  xor     edx, edx; AccessMode
0x180012d21  mov     rcx, rbx; FileName
0x180012d24  call    cs:__imp__waccess
0x180012d2a  test    eax, eax
0x180012d2c  jz      loc_180012E5F
0x180012d32  mov     rcx, rbx
0x180012d35  call    ODBCCreatePath
0x180012d3a  test    eax, eax
0x180012d3c  jnz     loc_180012E5F
0x180012d42  lea     rax, [rsp+0A8h+var_58]
0x180012d47  mov     rcx, 0FFFFFFFF80000002h
0x180012d4e  mov     [rsp+0A8h+var_60], rax
0x180012d53  lea     r9, SubKey
0x180012d5a  mov     [rsp+0A8h+var_68], r14
0x180012d5f  lea     r8, aDefaultdsndir; "DefaultDSNDir"
0x180012d66  mov     [rsp+0A8h+var_70], edi
0x180012d6a  lea     rdx, aOdbcFileDsn; "ODBC File DSN"
0x180012d71  mov     [rsp+0A8h+var_78], rbx
0x180012d76  mov     [rsp+0A8h+var_80], rbp
0x180012d7b  mov     [rsp+0A8h+var_88], esi
0x180012d7f  call    cpGetPrivateProfileString
0x180012d84  mov     esi, [rsp+0A8h+var_58]
0x180012d88  test    eax, eax
0x180012d8a  jz      short loc_180012DB3
0x180012d8c  test    esi, esi
0x180012d8e  jz      short loc_180012DB3
0x180012d90  xor     edx, edx; AccessMode
0x180012d92  mov     rcx, rbx; FileName
0x180012d95  call    cs:__imp__waccess
0x180012d9b  test    eax, eax
0x180012d9d  jz      loc_180012E5F
0x180012da3  mov     rcx, rbx
0x180012da6  call    ODBCCreatePath
0x180012dab  test    eax, eax
0x180012dad  jnz     loc_180012E5F
0x180012db3  xor     r9d, r9d; fCreate
0x180012db6  mov     rdx, rbx; pszPath
0x180012db9  xor     ecx, ecx; hwnd
0x180012dbb  lea     r8d, [r9+5]; csidl
0x180012dbf  call    cs:__imp_SHGetSpecialFolderPathW
0x180012dc5  test    eax, eax
0x180012dc7  jnz     loc_180012E5F
0x180012dcd  test    esi, esi
0x180012dcf  jnz     loc_180012E5F
0x180012dd5  xorps   xmm0, xmm0
0x180012dd8  mov     edx, edi; uSize
0x180012dda  mov     rcx, rbx; lpBuffer
0x180012ddd  movups  [rsp+0A8h+var_50], xmm0
0x180012de2  movups  [rsp+0A8h+var_40], xmm0
0x180012de7  movups  [rsp+0A8h+var_30], xmm0
0x180012dec  call    GetShellFilesDir
0x180012df1  or      rax, 0FFFFFFFFFFFFFFFFh
0x180012df5  inc     rax
0x180012df8  cmp     [rbx+rax*2], bp
0x180012dfc  jnz     short loc_180012DF5
0x180012dfe  add     rax, 12h
0x180012e02  cmp     rax, rdi
0x180012e05  jb      short loc_180012E13
0x180012e07  mov     ecx, 0Ch
0x180012e0c  call    PostInstError
0x180012e11  jmp     short loc_180012E5F
0x180012e13  lea     r8, aOdbc_0; "\\ODBC"
0x180012e1a  mov     rdx, rdi; cchDest
0x180012e1d  mov     rcx, rbx; pszDest
0x180012e20  call    StringCchCatW
0x180012e25  lea     r8, aDataSources; "\\Data Sources"
0x180012e2c  mov     rdx, rdi; cchDest
0x180012e2f  mov     rcx, rbx; pszDest
0x180012e32  call    StringCchCatW
0x180012e37  lea     rdx, [rsp+0A8h+var_50]
0x180012e3c  mov     rcx, rbx
0x180012e3f  call    cs:__imp__wstat
0x180012e45  test    eax, eax
0x180012e47  jz      short loc_180012E5F
0x180012e49  mov     rcx, rbx
0x180012e4c  call    ODBCCreatePath
0x180012e51  test    eax, eax
0x180012e53  jnz     short loc_180012E5F
0x180012e55  mov     edx, edi; uSize
0x180012e57  mov     rcx, rbx; lpBuffer
0x180012e5a  call    GetShellFilesDir
0x180012e5f  mov     rcx, [rsp+0A8h+var_20]
0x180012e67  xor     rcx, rsp; StackCookie
0x180012e6a  call    __security_check_cookie
0x180012e6f  lea     r11, [rsp+0A8h+var_18]
0x180012e77  mov     rbx, [r11+30h]
0x180012e7b  mov     rbp, [r11+38h]
0x180012e7f  mov     rsp, r11
0x180012e82  pop     r14
0x180012e84  pop     rdi
0x180012e85  pop     rsi
0x180012e86  retn
```
