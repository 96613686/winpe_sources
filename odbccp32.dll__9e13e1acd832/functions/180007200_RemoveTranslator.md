# RemoveTranslator

- ea: `0x180007200`
- end: `0x18000738e`
- name: `RemoveTranslator`
- size: `398`
- prototype: `__int64 __fastcall(const WCHAR *, _DWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180009c30`

## callees

- `0x180001010`
- `0x1800017c0`
- `0x18000663c`
- `0x180007200`
- `0x18000a320`
- `0x180013fa8`
- `0x180014ae0`

## pseudocode

```c
__int64 __fastcall RemoveTranslator(const WCHAR *a1, _DWORD *a2)
{
  unsigned int v4; // r8d
  WCHAR Data[8]; // [rsp+50h] [rbp-248h] BYREF
  _BYTE v7[528]; // [rsp+60h] [rbp-238h] BYREF

  *(_DWORD *)Data = 0;
  if ( (int)cpGetPrivateProfileString(
              HKEY_LOCAL_MACHINE,
              a1,
              L"UsageCount",
              (void *)&SubKey,
              0x10u,
              0,
              Data,
              4,
              (__int64)L"ODBCINST.INI",
              0) <= 0 )
  {
    if ( a2 )
      *a2 = 1;
  }
  else
  {
    v4 = *(_DWORD *)Data;
    if ( a2 )
      *a2 = *(_DWORD *)Data - 1;
    if ( v4 <= 1 )
    {
      cpWritePrivateProfileString(HKEY_LOCAL_MACHINE, (__int64)a1, 0, 1u, 0, (__int64)L"ODBCINST.INI");
      cpWritePrivateProfileString(HKEY_LOCAL_MACHINE, (__int64)L"ODBC Translators", a1, 1u, 0, (__int64)L"ODBCINST.INI");
      if ( !(unsigned int)SQLGetPrivateProfileStringCover(L"ODBC Translators", 0, &SubKey, v7, 260, L"ODBCINST.INI") )
        SQLWritePrivateProfileStringW(L"ODBC Translators", 0, 0, L"ODBCINST.INI");
      CleanupRegistry();
    }
    else
    {
      *(_DWORD *)Data = v4 - 1;
      cpWritePrivateProfileString(
        HKEY_LOCAL_MACHINE,
        (__int64)a1,
        L"UsageCount",
        4u,
        (BYTE *)Data,
        (__int64)L"ODBCINST.INI");
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180007200  mov     [rsp+arg_10], rbx
0x180007205  push    rdi
0x180007206  push    r14
0x180007208  push    r15
0x18000720a  sub     rsp, 280h
0x180007211  mov     rax, cs:__security_cookie
0x180007218  xor     rax, rsp
0x18000721b  mov     [rsp+298h+var_28], rax
0x180007223  mov     [rsp+298h+var_250], 0
0x18000722c  lea     rax, [rsp+298h+Data]
0x180007231  mov     rbx, rdx
0x180007234  mov     dword ptr [rsp+298h+Data], 0
0x18000723c  mov     rdi, rcx
0x18000723f  lea     r14, aOdbcinstIni; "ODBCINST.INI"
0x180007246  mov     [rsp+298h+var_258], r14
0x18000724b  lea     r9, SubKey
0x180007252  mov     [rsp+298h+var_260], 4
0x18000725a  lea     r8, aUsagecount; "UsageCount"
0x180007261  mov     [rsp+298h+var_268], rax
0x180007266  mov     rdx, rcx
0x180007269  mov     r15, 0FFFFFFFF80000002h
0x180007270  mov     [rsp+298h+var_270], 0
0x180007279  mov     rcx, r15
0x18000727c  mov     dword ptr [rsp+298h+lpData], 10h
0x180007284  call    cpGetPrivateProfileString
0x180007289  test    eax, eax
0x18000728b  jle     loc_180007359
0x180007291  mov     r8d, dword ptr [rsp+298h+Data]
0x180007296  test    rbx, rbx
0x180007299  jz      short loc_1800072A1
0x18000729b  lea     eax, [r8-1]
0x18000729f  mov     [rbx], eax
0x1800072a1  mov     [rsp+298h+var_270], r14; __int64
0x1800072a6  mov     rdx, rdi
0x1800072a9  mov     rcx, r15; hKey
0x1800072ac  cmp     r8d, 1
0x1800072b0  jbe     short loc_1800072DB
0x1800072b2  dec     r8d
0x1800072b5  lea     rax, [rsp+298h+Data]
0x1800072ba  mov     dword ptr [rsp+298h+Data], r8d
0x1800072bf  mov     r9d, 4
0x1800072c5  lea     r8, aUsagecount; "UsageCount"
0x1800072cc  mov     [rsp+298h+lpData], rax; lpData
0x1800072d1  call    cpWritePrivateProfileString
0x1800072d6  jmp     loc_180007364
0x1800072db  mov     r9d, 1
0x1800072e1  mov     [rsp+298h+lpData], 0; lpData
0x1800072ea  xor     r8d, r8d
0x1800072ed  call    cpWritePrivateProfileString
0x1800072f2  lea     rbx, szSection; "ODBC Translators"
0x1800072f9  mov     [rsp+298h+var_270], r14; __int64
0x1800072fe  mov     rdx, rbx
0x180007301  mov     [rsp+298h+lpData], 0; lpData
0x18000730a  mov     r9d, 1
0x180007310  mov     r8, rdi
0x180007313  mov     rcx, r15; hKey
0x180007316  call    cpWritePrivateProfileString
0x18000731b  lea     r9, [rsp+298h+var_238]
0x180007320  mov     [rsp+298h+var_270], r14
0x180007325  lea     r8, SubKey
0x18000732c  mov     dword ptr [rsp+298h+lpData], 104h
0x180007334  xor     edx, edx
0x180007336  mov     rcx, rbx
0x180007339  call    SQLGetPrivateProfileStringCover
0x18000733e  test    eax, eax
0x180007340  jnz     short loc_180007352
0x180007342  mov     r9, r14; lpszFilename
0x180007345  xor     r8d, r8d; lpszString
0x180007348  xor     edx, edx; lpszEntry
0x18000734a  mov     rcx, rbx; lpszSection
0x18000734d  call    SQLWritePrivateProfileStringW
0x180007352  call    CleanupRegistry
0x180007357  jmp     short loc_180007364
0x180007359  test    rbx, rbx
0x18000735c  jz      short loc_180007364
0x18000735e  mov     dword ptr [rbx], 1
0x180007364  mov     eax, 1
0x180007369  mov     rcx, [rsp+298h+var_28]
0x180007371  xor     rcx, rsp; StackCookie
0x180007374  call    __security_check_cookie
0x180007379  mov     rbx, [rsp+298h+arg_10]
0x180007381  add     rsp, 280h
0x180007388  pop     r15
0x18000738a  pop     r14
0x18000738c  pop     rdi
0x18000738d  retn
```
