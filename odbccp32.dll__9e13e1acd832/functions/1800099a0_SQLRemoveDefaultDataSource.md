# SQLRemoveDefaultDataSource

- ea: `0x1800099a0`
- end: `0x180009a81`
- name: `SQLRemoveDefaultDataSource`
- size: `225`
- prototype: `BOOL __stdcall()`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x180006db8`
- `0x1800084c0`

## callees

- `0x180001740`
- `0x1800017c0`
- `0x180007c0c`
- `0x1800099a0`
- `0x18000a320`
- `0x180014ae0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180009a58`
- `KERNEL32!LeaveCriticalSection` at `0x180009a58`
- `KERNEL32!EnterCriticalSection` at `0x1800099cb`
- `KERNEL32!EnterCriticalSection` at `0x1800099cb`

## pseudocode

```c
BOOL __stdcall SQLRemoveDefaultDataSource()
{
  int v0; // ebx
  wchar_t v2[264]; // [rsp+30h] [rbp-228h] BYREF

  v0 = 1;
  EnterCriticalSection(&g_csInstaller);
  FreeErrorQueue();
  if ( (unsigned int)SQLGetPrivateProfileStringCover(
                       L"Default",
                       L"Driver",
                       (void *)&SubKey,
                       v2,
                       260,
                       (wchar_t *)L"ODBCINST.INI") )
    v0 = ConfigDataSourceW(0, 3u, v2, (__int64)L"DSN=Default");
  SQLWritePrivateProfileStringW(L"Default", 0, 0, L"ODBC.INI");
  SQLWritePrivateProfileStringW(L"Default", 0, 0, L"ODBCINST.INI");
  LeaveCriticalSection(&g_csInstaller);
  return v0;
}

```

## disassembly

```asm
0x1800099a0  mov     [rsp+arg_0], rbx
0x1800099a5  push    rsi
0x1800099a6  sub     rsp, 250h
0x1800099ad  mov     rax, cs:__security_cookie
0x1800099b4  xor     rax, rsp
0x1800099b7  mov     [rsp+258h+var_18], rax
0x1800099bf  lea     rcx, g_csInstaller; lpCriticalSection
0x1800099c6  mov     ebx, 1
0x1800099cb  call    cs:__imp_EnterCriticalSection
0x1800099d1  call    FreeErrorQueue
0x1800099d6  lea     rsi, aOdbcinstIni; "ODBCINST.INI"
0x1800099dd  mov     [rsp+258h+var_230], rsi
0x1800099e2  lea     r9, [rsp+258h+var_228]
0x1800099e7  lea     r8, SubKey
0x1800099ee  mov     [rsp+258h+var_238], 104h
0x1800099f6  lea     rdx, aDriver_0; "Driver"
0x1800099fd  lea     rcx, aDefault; "Default"
0x180009a04  call    SQLGetPrivateProfileStringCover
0x180009a09  test    eax, eax
0x180009a0b  jz      short loc_180009A25
0x180009a0d  lea     edx, [rbx+2]
0x180009a10  xor     ecx, ecx; hWnd
0x180009a12  lea     r9, aDsnDefault; "DSN=Default"
0x180009a19  lea     r8, [rsp+258h+var_228]
0x180009a1e  call    ConfigDataSourceW
0x180009a23  mov     ebx, eax
0x180009a25  lea     r9, aOdbcIni; "ODBC.INI"
0x180009a2c  xor     r8d, r8d; lpszString
0x180009a2f  xor     edx, edx; lpszEntry
0x180009a31  lea     rcx, aDefault; "Default"
0x180009a38  call    SQLWritePrivateProfileStringW
0x180009a3d  mov     r9, rsi; lpszFilename
0x180009a40  lea     rcx, aDefault; "Default"
0x180009a47  xor     r8d, r8d; lpszString
0x180009a4a  xor     edx, edx; lpszEntry
0x180009a4c  call    SQLWritePrivateProfileStringW
0x180009a51  lea     rcx, g_csInstaller; lpCriticalSection
0x180009a58  call    cs:__imp_LeaveCriticalSection
0x180009a5e  mov     eax, ebx
0x180009a60  mov     rcx, [rsp+258h+var_18]
0x180009a68  xor     rcx, rsp; StackCookie
0x180009a6b  call    __security_check_cookie
0x180009a70  mov     rbx, [rsp+258h+arg_0]
0x180009a78  add     rsp, 250h
0x180009a7f  pop     rsi
0x180009a80  retn
```
