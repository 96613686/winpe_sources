# RemoveDrvrDSNs

- ea: `0x180006db8`
- end: `0x1800071f7`
- name: `RemoveDrvrDSNs`
- size: `1087`
- prototype: `__int64 __fastcall(HWND hWnd, HKEY hKey, wchar_t *String1)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x180006afc`

## callees

- `0x180001010`
- `0x180002940`
- `0x180002e4c`
- `0x180004bac`
- `0x180004bdc`
- `0x180006db8`
- `0x1800074c4`
- `0x180007c0c`
- `0x1800099a0`
- `0x180013fa8`
- `0x180014aae`
- `0x180014ae0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180006f22`
- `msvcrt!_wcsicmp` at `0x180007178`
- `msvcrt!_wcsicmp` at `0x180007188`
- `msvcrt!_wcsicmp` at `0x180006f22`
- `msvcrt!_wcsicmp` at `0x180007178`
- `msvcrt!_wcsicmp` at `0x180007188`
- `msvcrt!_wsplitpath_s` at `0x180007139`
- `msvcrt!_wsplitpath_s` at `0x18000716c`
- `msvcrt!_wsplitpath_s` at `0x180007139`
- `msvcrt!_wsplitpath_s` at `0x18000716c`
- `msvcrt!calloc` at `0x180006dfb`
- `msvcrt!calloc` at `0x180006dfb`
- `ADVAPI32!RegCloseKey` at `0x1800071bb`
- `ADVAPI32!RegCloseKey` at `0x1800071bb`
- `ADVAPI32!RegOpenKeyExW` at `0x180006e3f`
- `ADVAPI32!RegOpenKeyExW` at `0x180006e3f`

## pseudocode

```c
__int64 __fastcall RemoveDrvrDSNs(HWND hWnd, HKEY hKey, wchar_t *String1)
{
  __int16 v6; // di
  WCHAR *v7; // rbp
  unsigned int v9; // r13d
  wchar_t *v10; // rsi
  DWORD *v11; // r10
  const WCHAR *v12; // rbx
  int PrivateProfileString; // eax
  int v14; // eax
  __int64 v15; // rax
  __int64 v16; // rcx
  bool v17; // zf
  __int16 v18; // ax
  __int64 v19; // rax
  wchar_t *Filename; // rsi
  HKEY hKeya; // [rsp+50h] [rbp-F8h] BYREF
  WCHAR *v22; // [rsp+58h] [rbp-F0h]
  wchar_t String2[80]; // [rsp+60h] [rbp-E8h] BYREF

  hKeya = 0;
  v6 = 1;
  v22 = (WCHAR *)calloc(0x2A28u, 1u);
  v7 = v22;
  if ( v22 )
  {
    v9 = 1;
    if ( !RegOpenKeyExW(hKey, L"Software\\ODBC\\ODBC.INI", 0, 0x20019u, &hKeya) )
    {
      v10 = v7 + 4096;
      if ( (int)cpGetPrivateProfileString(
                  hKey,
                  L"ODBC Data Sources",
                  0,
                  (void *)&SubKey,
                  0xFFFFu,
                  0,
                  v7,
                  0x2000,
                  (__int64)L"ODBC.INI",
                  0) > 0 )
      {
        memset_0(String2, 0, 0x98u);
        v11 = 0;
        v12 = v7;
        if ( *v7 )
        {
          do
          {
            PrivateProfileString = cpGetPrivateProfileString(
                                     hKey,
                                     L"ODBC Data Sources",
                                     v12,
                                     (void *)&SubKey,
                                     2u,
                                     v11,
                                     String2,
                                     152,
                                     (__int64)L"ODBC.INI",
                                     v11);
            v11 = 0;
            if ( PrivateProfileString > 0 )
            {
              v14 = _wcsicmp(String1, String2);
              v11 = 0;
              if ( !v14 )
              {
                v15 = -1;
                do
                  ++v15;
                while ( v12[v15] );
                if ( (unsigned __int64)(v15 + 5) >= 0x104 )
                {
                  PostInstErrorMsgId(1, 1416);
                  v9 = (unsigned int)v11;
                }
                else
                {
                  StringCchPrintfW(v10, 0x104u, L"%s%s", L"DSN=", v12);
                  v16 = -1;
                  do
                    ++v16;
                  while ( v10[v16] );
                  v17 = hKey == (HKEY)g_hkeyMachine;
                  v10[v16 + 1] = 0;
                  if ( v17 )
                    v18 = 1;
                  else
                    v18 = 2;
                  g_wSystemDSN = v18;
                  ConfigDataSourceW(hWnd, 3u, String1, (__int64)v10);
                  v11 = 0;
                  g_wSystemDSN = 4;
                }
              }
            }
            v19 = -1;
            do
              ++v19;
            while ( v12[v19] != (_WORD)v11 );
            v12 += v19 + 1;
          }
          while ( *v12 != (_WORD)v11 );
          v7 = v22;
        }
      }
      if ( !(unsigned int)cpGetPrivateProfileString(
                            hKey,
                            L"ODBC Data Sources",
                            0,
                            (void *)&SubKey,
                            0xFFFFu,
                            0,
                            v7,
                            0x2000,
                            (__int64)L"ODBC.INI",
                            0) )
        cpWritePrivateProfileString(hKey, (__int64)L"ODBC Data Sources", 0, 1u, 0, (__int64)L"ODBC.INI");
      if ( (int)cpGetPrivateProfileString(
                  hKey,
                  L"Default",
                  L"Driver",
                  (void *)&SubKey,
                  2u,
                  0,
                  v7,
                  520,
                  (__int64)L"ODBC.INI",
                  0) > 0 )
      {
        Filename = v10 + 260;
        if ( (int)cpGetPrivateProfileString(
                    HKEY_LOCAL_MACHINE,
                    String1,
                    L"Driver",
                    (void *)&SubKey,
                    2u,
                    0,
                    Filename,
                    520,
                    (__int64)L"ODBCINST.INI",
                    0) > 0 )
        {
          _wsplitpath_s(Filename, 0, 0, 0, 0, Filename + 260, 0x104u, Filename + 780, 0x104u);
          _wsplitpath_s(v7, 0, 0, 0, 0, Filename, 0x104u, Filename + 520, 0x104u);
          if ( !_wcsicmp(Filename, Filename + 260) && !_wcsicmp(Filename + 520, Filename + 780) )
          {
            if ( hKey != (HKEY)g_hkeyMachine )
              v6 = 2;
            g_wSystemDSN = v6;
            SQLRemoveDefaultDataSource();
            g_wSystemDSN = 4;
          }
        }
      }
      RegCloseKey(hKeya);
    }
    OFree(v7);
    return v9;
  }
  else
  {
    MemError();
    PostInstError(21);
    return 0;
  }
}

```

## disassembly

```asm
0x180006db8  mov     [rsp+arg_18], rbx
0x180006dbd  push    rbp
0x180006dbe  push    rsi
0x180006dbf  push    rdi
0x180006dc0  push    r12
0x180006dc2  push    r13
0x180006dc4  push    r14
0x180006dc6  push    r15
0x180006dc8  sub     rsp, 110h
0x180006dcf  mov     rax, cs:__security_cookie
0x180006dd6  xor     rax, rsp
0x180006dd9  mov     [rsp+148h+var_48], rax
0x180006de1  xor     ebx, ebx
0x180006de3  mov     r14, rdx
0x180006de6  mov     r12, rcx
0x180006de9  mov     [rsp+148h+hKey], rbx
0x180006dee  mov     ecx, 2A28h; Count
0x180006df3  mov     r15, r8
0x180006df6  lea     edi, [rbx+1]
0x180006df9  mov     edx, edi; Size
0x180006dfb  call    cs:__imp_calloc
0x180006e01  mov     [rsp+148h+var_F0], rax
0x180006e06  mov     rbp, rax
0x180006e09  test    rax, rax
0x180006e0c  jnz     short loc_180006E22
0x180006e0e  call    MemError
0x180006e13  lea     ecx, [rbx+15h]
0x180006e16  call    PostInstError
0x180006e1b  xor     eax, eax
0x180006e1d  jmp     loc_1800071CC
0x180006e22  lea     rax, [rsp+148h+hKey]
0x180006e27  mov     r9d, 20019h; samDesired
0x180006e2d  xor     r8d, r8d; ulOptions
0x180006e30  mov     [rsp+148h+phkResult], rax; phkResult
0x180006e35  lea     rdx, aSoftwareOdbcOd_1; "Software\\ODBC\\ODBC.INI"
0x180006e3c  mov     rcx, r14; hKey
0x180006e3f  call    cs:__imp_RegOpenKeyExW
0x180006e45  mov     r13d, edi
0x180006e48  test    eax, eax
0x180006e4a  jnz     loc_1800071C1
0x180006e50  mov     [rsp+148h+var_100], rbx
0x180006e55  lea     rax, aOdbcIni; "ODBC.INI"
0x180006e5c  mov     [rsp+148h+ExtCount], rax
0x180006e61  lea     r9, SubKey
0x180006e68  mov     dword ptr [rsp+148h+Ext], 2000h
0x180006e70  lea     rdx, aOdbcDataSource; "ODBC Data Sources"
0x180006e77  mov     [rsp+148h+FilenameCount], rbp
0x180006e7c  lea     rsi, [rbp+2000h]
0x180006e83  mov     [rsp+148h+Filename], rbx
0x180006e88  xor     r8d, r8d
0x180006e8b  mov     rcx, r14
0x180006e8e  mov     dword ptr [rsp+148h+phkResult], 0FFFFh
0x180006e96  call    cpGetPrivateProfileString
0x180006e9b  test    eax, eax
0x180006e9d  jle     loc_180006FF4
0x180006ea3  xor     edx, edx; Val
0x180006ea5  lea     rcx, [rsp+148h+String2]; void *
0x180006eaa  mov     r8d, 98h; Size
0x180006eb0  call    memset_0
0x180006eb5  xor     r10d, r10d
0x180006eb8  mov     rbx, rbp
0x180006ebb  cmp     [rbp+0], r10w
0x180006ec0  jz      loc_180006FF2
0x180006ec6  lea     rbp, aOdbcIni; "ODBC.INI"
0x180006ecd  mov     [rsp+148h+var_100], r10
0x180006ed2  lea     rax, [rsp+148h+String2]
0x180006ed7  mov     [rsp+148h+ExtCount], rbp
0x180006edc  lea     r9, SubKey
0x180006ee3  mov     dword ptr [rsp+148h+Ext], 98h
0x180006eeb  lea     rdx, aOdbcDataSource; "ODBC Data Sources"
0x180006ef2  mov     [rsp+148h+FilenameCount], rax
0x180006ef7  mov     r8, rbx
0x180006efa  mov     [rsp+148h+Filename], r10
0x180006eff  mov     rcx, r14
0x180006f02  mov     dword ptr [rsp+148h+phkResult], 2
0x180006f0a  call    cpGetPrivateProfileString
0x180006f0f  xor     r10d, r10d
0x180006f12  test    eax, eax
0x180006f14  jle     loc_180006FCD
0x180006f1a  lea     rdx, [rsp+148h+String2]; String2
0x180006f1f  mov     rcx, r15; String1
0x180006f22  call    cs:__imp__wcsicmp
0x180006f28  xor     r10d, r10d
0x180006f2b  test    eax, eax
0x180006f2d  jnz     loc_180006FCD
0x180006f33  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006f37  inc     rax
0x180006f3a  cmp     [rbx+rax*2], r10w
0x180006f3f  jnz     short loc_180006F37
0x180006f41  add     rax, 5
0x180006f45  mov     ecx, 104h
0x180006f4a  cmp     rax, rcx
0x180006f4d  jnb     short loc_180006FBE
0x180006f4f  mov     edx, ecx; cchDest
0x180006f51  mov     [rsp+148h+phkResult], rbx
0x180006f56  mov     rcx, rsi; pszDest
0x180006f59  lea     r9, aDsn_0; "DSN="
0x180006f60  lea     r8, aSS_1; "%s%s"
0x180006f67  call    StringCchPrintfW
0x180006f6c  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180006f70  xor     eax, eax
0x180006f72  inc     rcx
0x180006f75  cmp     [rsi+rcx*2], ax
0x180006f79  jnz     short loc_180006F72
0x180006f7b  cmp     r14, cs:g_hkeyMachine
0x180006f82  mov     [rsi+rcx*2+2], ax
0x180006f87  jnz     short loc_180006F8E
0x180006f89  movzx   eax, di
0x180006f8c  jmp     short loc_180006F93
0x180006f8e  mov     eax, 2
0x180006f93  mov     edx, 3
0x180006f98  mov     cs:g_wSystemDSN, ax
0x180006f9f  mov     r9, rsi
0x180006fa2  mov     r8, r15
0x180006fa5  mov     rcx, r12; hWnd
0x180006fa8  call    ConfigDataSourceW
0x180006fad  mov     eax, 4
0x180006fb2  xor     r10d, r10d
0x180006fb5  mov     cs:g_wSystemDSN, ax
0x180006fbc  jmp     short loc_180006FCD
0x180006fbe  mov     edx, 588h
0x180006fc3  mov     ecx, edi
0x180006fc5  call    PostInstErrorMsgId
0x180006fca  mov     r13d, r10d
0x180006fcd  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006fd1  inc     rax
0x180006fd4  cmp     [rbx+rax*2], r10w
0x180006fd9  jnz     short loc_180006FD1
0x180006fdb  lea     rbx, [rbx+rax*2]
0x180006fdf  add     rbx, 2
0x180006fe3  cmp     [rbx], r10w
0x180006fe7  jnz     loc_180006ECD
0x180006fed  mov     rbp, [rsp+148h+var_F0]
0x180006ff2  xor     ebx, ebx
0x180006ff4  mov     [rsp+148h+var_100], rbx
0x180006ff9  lea     r12, aOdbcIni; "ODBC.INI"
0x180007000  mov     [rsp+148h+ExtCount], r12
0x180007005  lea     r9, SubKey
0x18000700c  mov     dword ptr [rsp+148h+Ext], 2000h
0x180007014  lea     rdx, aOdbcDataSource; "ODBC Data Sources"
0x18000701b  mov     [rsp+148h+FilenameCount], rbp
0x180007020  xor     r8d, r8d
0x180007023  mov     [rsp+148h+Filename], rbx
0x180007028  mov     rcx, r14
0x18000702b  mov     dword ptr [rsp+148h+phkResult], 0FFFFh
0x180007033  call    cpGetPrivateProfileString
0x180007038  test    eax, eax
0x18000703a  jnz     short loc_18000705B
0x18000703c  mov     [rsp+148h+Filename], r12; __int64
0x180007041  lea     rdx, aOdbcDataSource; "ODBC Data Sources"
0x180007048  mov     r9d, edi
0x18000704b  mov     [rsp+148h+phkResult], rbx; lpData
0x180007050  xor     r8d, r8d
0x180007053  mov     rcx, r14; hKey
0x180007056  call    cpWritePrivateProfileString
0x18000705b  mov     [rsp+148h+var_100], rbx
0x180007060  lea     r9, SubKey
0x180007067  mov     [rsp+148h+ExtCount], r12
0x18000706c  lea     r8, aDriver_0; "Driver"
0x180007073  mov     r12d, 208h
0x180007079  lea     rdx, aDefault; "Default"
0x180007080  mov     dword ptr [rsp+148h+Ext], r12d
0x180007085  mov     rcx, r14
0x180007088  mov     [rsp+148h+FilenameCount], rbp
0x18000708d  mov     [rsp+148h+Filename], rbx
0x180007092  mov     dword ptr [rsp+148h+phkResult], 2
0x18000709a  call    cpGetPrivateProfileString
0x18000709f  test    eax, eax
0x1800070a1  jle     loc_1800071B6
0x1800070a7  mov     [rsp+148h+var_100], rbx
0x1800070ac  lea     rax, aOdbcinstIni; "ODBCINST.INI"
0x1800070b3  mov     [rsp+148h+ExtCount], rax
0x1800070b8  lea     r9, SubKey
0x1800070bf  mov     dword ptr [rsp+148h+Ext], r12d
0x1800070c4  lea     r8, aDriver_0; "Driver"
0x1800070cb  add     rsi, r12
0x1800070ce  mov     rdx, r15
0x1800070d1  mov     [rsp+148h+FilenameCount], rsi
0x1800070d6  mov     rcx, 0FFFFFFFF80000002h
0x1800070dd  mov     [rsp+148h+Filename], rbx
0x1800070e2  mov     dword ptr [rsp+148h+phkResult], 2
0x1800070ea  call    cpGetPrivateProfileString
0x1800070ef  test    eax, eax
0x1800070f1  jle     loc_1800071B6
0x1800070f7  mov     eax, 104h
0x1800070fc  lea     rbx, [rsi+208h]
0x180007103  mov     [rsp+148h+ExtCount], rax; ExtCount
0x180007108  lea     r15, [rbx+208h]
0x18000710f  lea     r12, [r15+208h]
0x180007116  xor     r9d, r9d; Dir
0x180007119  mov     [rsp+148h+Ext], r12; Ext
0x18000711e  xor     r8d, r8d; DriveCount
0x180007121  mov     [rsp+148h+FilenameCount], rax; FilenameCount
0x180007126  xor     edx, edx; Drive
0x180007128  mov     [rsp+148h+Filename], rbx; Filename
0x18000712d  mov     rcx, rsi; FullPath
0x180007130  mov     [rsp+148h+phkResult], 0; DirCount
0x180007139  call    cs:__imp__wsplitpath_s
0x18000713f  mov     eax, 104h
0x180007144  xor     r9d, r9d; Dir
0x180007147  mov     [rsp+148h+ExtCount], rax; ExtCount
0x18000714c  xor     r8d, r8d; DriveCount
0x18000714f  mov     [rsp+148h+Ext], r15; Ext
0x180007154  xor     edx, edx; Drive
0x180007156  mov     [rsp+148h+FilenameCount], rax; FilenameCount
0x18000715b  mov     rcx, rbp; FullPath
0x18000715e  mov     [rsp+148h+Filename], rsi; Filename
0x180007163  mov     [rsp+148h+phkResult], 0; DirCount
0x18000716c  call    cs:__imp__wsplitpath_s
0x180007172  mov     rdx, rbx; String2
0x180007175  mov     rcx, rsi; String1
0x180007178  call    cs:__imp__wcsicmp
0x18000717e  test    eax, eax
0x180007180  jnz     short loc_1800071B6
0x180007182  mov     rdx, r12; String2
0x180007185  mov     rcx, r15; String1
0x180007188  call    cs:__imp__wcsicmp
0x18000718e  test    eax, eax
0x180007190  jnz     short loc_1800071B6
0x180007192  cmp     r14, cs:g_hkeyMachine
0x180007199  jz      short loc_18000719E
0x18000719b  lea     edi, [rax+2]
0x18000719e  mov     cs:g_wSystemDSN, di
0x1800071a5  call    SQLRemoveDefaultDataSource
0x1800071aa  mov     eax, 4
0x1800071af  mov     cs:g_wSystemDSN, ax
0x1800071b6  mov     rcx, [rsp+148h+hKey]; hKey
0x1800071bb  call    cs:__imp_RegCloseKey
0x1800071c1  mov     rcx, rbp
0x1800071c4  call    OFree
0x1800071c9  mov     eax, r13d
0x1800071cc  mov     rcx, [rsp+148h+var_48]
0x1800071d4  xor     rcx, rsp; StackCookie
0x1800071d7  call    __security_check_cookie
0x1800071dc  mov     rbx, [rsp+148h+arg_18]
0x1800071e4  add     rsp, 110h
0x1800071eb  pop     r15
0x1800071ed  pop     r14
0x1800071ef  pop     r13
0x1800071f1  pop     r12
0x1800071f3  pop     rdi
0x1800071f4  pop     rsi
0x1800071f5  pop     rbp
0x1800071f6  retn
```
