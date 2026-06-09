# SetAuthOptions

- ea: `0x18000d9b0`
- end: `0x18000dc13`
- name: `SetAuthOptions`
- size: `611`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpSubKey)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000be24`

## callees

- `0x18000d9b0`
- `0x18000e5f4`
- `0x18000eccc`
- `0x180011b62`

## import_xrefs

- `msvcrt!_snwprintf_s` at `0x18000db04`
- `msvcrt!_snwprintf_s` at `0x18000db04`
- `KERNEL32!GlobalFree` at `0x18000db69`
- `KERNEL32!GlobalFree` at `0x18000db69`
- `KERNEL32!GlobalAlloc` at `0x18000dac3`
- `KERNEL32!GlobalAlloc` at `0x18000dac3`
- `ADVAPI32!RegCloseKey` at `0x18000da6a`
- `ADVAPI32!RegCloseKey` at `0x18000db60`
- `ADVAPI32!RegCloseKey` at `0x18000dbf5`
- `ADVAPI32!RegCloseKey` at `0x18000da6a`
- `ADVAPI32!RegCloseKey` at `0x18000db60`
- `ADVAPI32!RegCloseKey` at `0x18000dbf5`
- `ADVAPI32!RegQueryValueExW` at `0x18000da5e`
- `ADVAPI32!RegQueryValueExW` at `0x18000db56`
- `ADVAPI32!RegQueryValueExW` at `0x18000dbbb`
- `ADVAPI32!RegQueryValueExW` at `0x18000dbeb`
- `ADVAPI32!RegQueryValueExW` at `0x18000da5e`
- `ADVAPI32!RegQueryValueExW` at `0x18000db56`
- `ADVAPI32!RegQueryValueExW` at `0x18000dbbb`
- `ADVAPI32!RegQueryValueExW` at `0x18000dbeb`
- `ADVAPI32!RegOpenKeyExW` at `0x18000da2a`
- `ADVAPI32!RegOpenKeyExW` at `0x18000db22`
- `ADVAPI32!RegOpenKeyExW` at `0x18000db87`
- `ADVAPI32!RegOpenKeyExW` at `0x18000da2a`
- `ADVAPI32!RegOpenKeyExW` at `0x18000db22`
- `ADVAPI32!RegOpenKeyExW` at `0x18000db87`

## pseudocode

```c
LSTATUS __fastcall SetAuthOptions(HKEY hKey, LPCWSTR lpSubKey, __int64 a3)
{
  __int64 v3; // rsi
  LSTATUS Value; // ebx
  DWORD v8; // eax
  __int64 v9; // rax
  __int64 v10; // rsi
  unsigned int v11; // r14d
  wchar_t *v12; // rax
  wchar_t *v13; // rbx
  LSTATUS result; // eax
  __int64 cbData; // [rsp+30h] [rbp-20h] BYREF
  __int64 v16; // [rsp+38h] [rbp-18h] BYREF
  HKEY phkResult; // [rsp+40h] [rbp-10h] BYREF
  HKEY hKeya; // [rsp+48h] [rbp-8h] BYREF
  DWORD lpcbData; // [rsp+A0h] [rbp+50h] BYREF
  DWORD Data; // [rsp+A8h] [rbp+58h] BYREF

  v3 = *(_QWORD *)(a3 + 8);
  lpcbData = 0;
  phkResult = 0;
  LODWORD(v16) = 1;
  SetUserName(hKey, (__int64)lpSubKey, a3);
  SetPasswd(hKey, (__int64)lpSubKey, a3);
  hKeya = 0;
  cbData = 0x100000000LL;
  Data = 0;
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Users\\Default\\Auth",
         0,
         0x20019u,
         &hKeya)
    || (LODWORD(cbData) = 4,
        Value = RegQueryValueExW(hKeya, L"AuthType", 0, 0, (LPBYTE)&Data, (LPDWORD)&cbData),
        RegCloseKey(hKeya),
        Value) )
  {
    v8 = Data;
  }
  else
  {
    v8 = Data;
    if ( Data == 5 )
    {
LABEL_8:
      *(_DWORD *)(v3 + 1056) = 5;
      goto LABEL_9;
    }
    if ( Data )
      v8 = 0;
  }
  if ( v8 == 5 )
    goto LABEL_8;
LABEL_9:
  hKeya = 0;
  v9 = -1;
  Data = 0;
  LODWORD(cbData) = 1;
  do
    ++v9;
  while ( lpSubKey[v9] );
  v10 = (unsigned int)(v9 + 8);
  v11 = v9 + 8;
  v12 = (wchar_t *)GlobalAlloc(0x40u, 2 * v10);
  v13 = v12;
  if ( v12 )
  {
    memset_0(v12, 0, 2 * v10);
    _snwprintf_s(v13, v11, (unsigned int)(v10 - 1), L"%s%s", lpSubKey, L"\\Auth", cbData, v16, phkResult);
    if ( !RegOpenKeyExW(hKey, v13, 0, 0x20019u, &hKeya) )
    {
      Data = 4;
      RegQueryValueExW(hKeya, L"AuthenticateAtLogon", 0, 0, (LPBYTE)&cbData, &Data);
      RegCloseKey(hKeya);
    }
    GlobalFree(v13);
  }
  result = RegOpenKeyExW(hKey, lpSubKey, 0, 0x20019u, &phkResult);
  if ( !result )
  {
    lpcbData = 4;
    RegQueryValueExW(phkResult, L"ConnectDisplay", 0, 0, (LPBYTE)&cbData + 4, &lpcbData);
    lpcbData = 4;
    RegQueryValueExW(phkResult, L"DisplayConfirmation", 0, 0, (LPBYTE)&v16, &lpcbData);
    return RegCloseKey(phkResult);
  }
  return result;
}

```

## disassembly

```asm
0x18000d9b0  mov     [rsp-38h+arg_0], rbx
0x18000d9b5  push    rbp
0x18000d9b6  push    rsi
0x18000d9b7  push    rdi
0x18000d9b8  push    r12
0x18000d9ba  push    r13
0x18000d9bc  push    r14
0x18000d9be  push    r15
0x18000d9c0  mov     rbp, rsp
0x18000d9c3  sub     rsp, 50h
0x18000d9c7  mov     rsi, [r8+8]
0x18000d9cb  xor     r13d, r13d
0x18000d9ce  mov     rbx, r8
0x18000d9d1  mov     [rbp+arg_10], r13d
0x18000d9d5  mov     rdi, rdx
0x18000d9d8  mov     [rbp+var_10], r13
0x18000d9dc  mov     r12, rcx
0x18000d9df  lea     r14d, [r13+1]
0x18000d9e3  mov     dword ptr [rbp+var_1C], r14d
0x18000d9e7  mov     dword ptr [rbp+var_18], r14d
0x18000d9eb  call    SetUserName
0x18000d9f0  mov     r8, rbx
0x18000d9f3  mov     rdx, rdi
0x18000d9f6  mov     rcx, r12
0x18000d9f9  call    SetPasswd
0x18000d9fe  lea     rax, [rbp+hKey]
0x18000da02  mov     [rbp+hKey], r13
0x18000da06  mov     r9d, 20019h; samDesired
0x18000da0c  mov     [rsp+50h+phkResult], rax; phkResult
0x18000da11  xor     r8d, r8d; ulOptions
0x18000da14  mov     [rbp+cbData], r13d
0x18000da18  lea     rdx, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\ClientForNFS\\Curr"...
0x18000da1f  mov     [rbp+Data], r13d
0x18000da23  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000da2a  call    cs:__imp_RegOpenKeyExW
0x18000da30  test    eax, eax
0x18000da32  jnz     short loc_18000DA85
0x18000da34  mov     rcx, [rbp+hKey]; hKey
0x18000da38  lea     rax, [rbp+cbData]
0x18000da3c  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18000da41  lea     rdx, aAuthtype; "AuthType"
0x18000da48  lea     rax, [rbp+Data]
0x18000da4c  mov     [rbp+cbData], 4
0x18000da53  xor     r9d, r9d; lpType
0x18000da56  mov     [rsp+50h+phkResult], rax; lpData
0x18000da5b  xor     r8d, r8d; lpReserved
0x18000da5e  call    cs:__imp_RegQueryValueExW
0x18000da64  mov     rcx, [rbp+hKey]; hKey
0x18000da68  mov     ebx, eax
0x18000da6a  call    cs:__imp_RegCloseKey
0x18000da70  test    ebx, ebx
0x18000da72  jnz     short loc_18000DA85
0x18000da74  mov     eax, [rbp+Data]
0x18000da77  cmp     eax, 5
0x18000da7a  jz      short loc_18000DA8D
0x18000da7c  test    eax, eax
0x18000da7e  jz      short loc_18000DA88
0x18000da80  mov     eax, r13d
0x18000da83  jmp     short loc_18000DA88
0x18000da85  mov     eax, [rbp+Data]
0x18000da88  cmp     eax, 5
0x18000da8b  jnz     short loc_18000DA97
0x18000da8d  mov     dword ptr [rsi+420h], 5
0x18000da97  mov     [rbp+hKey], r13
0x18000da9b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000da9f  mov     [rbp+Data], r13d
0x18000daa3  mov     [rbp+cbData], r14d
0x18000daa7  inc     rax
0x18000daaa  cmp     [rdi+rax*2], r13w
0x18000daaf  jnz     short loc_18000DAA7
0x18000dab1  lea     esi, [rax+8]
0x18000dab4  mov     ecx, 40h ; '@'; uFlags
0x18000dab9  lea     r15, [rsi+rsi]
0x18000dabd  mov     r14d, esi
0x18000dac0  mov     rdx, r15; dwBytes
0x18000dac3  call    cs:__imp_GlobalAlloc
0x18000dac9  mov     rbx, rax
0x18000dacc  test    rax, rax
0x18000dacf  jz      loc_18000DB6F
0x18000dad5  mov     r8, r15; Size
0x18000dad8  xor     edx, edx; Val
0x18000dada  mov     rcx, rax; void *
0x18000dadd  call    memset_0
0x18000dae2  lea     rax, aAuth; "\\Auth"
0x18000dae9  mov     edx, r14d; BufferCount
0x18000daec  mov     [rsp+50h+lpcbData], rax
0x18000daf1  lea     r8d, [rsi-1]; MaxCount
0x18000daf5  lea     r9, aSS_0; "%s%s"
0x18000dafc  mov     [rsp+50h+phkResult], rdi
0x18000db01  mov     rcx, rbx; Buffer
0x18000db04  call    cs:__imp__snwprintf_s
0x18000db0a  lea     rax, [rbp+hKey]
0x18000db0e  mov     r9d, 20019h; samDesired
0x18000db14  xor     r8d, r8d; ulOptions
0x18000db17  mov     [rsp+50h+phkResult], rax; phkResult
0x18000db1c  mov     rdx, rbx; lpSubKey
0x18000db1f  mov     rcx, r12; hKey
0x18000db22  call    cs:__imp_RegOpenKeyExW
0x18000db28  test    eax, eax
0x18000db2a  jnz     short loc_18000DB66
0x18000db2c  mov     rcx, [rbp+hKey]; hKey
0x18000db30  lea     rax, [rbp+Data]
0x18000db34  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18000db39  lea     rdx, aAuthenticateat; "AuthenticateAtLogon"
0x18000db40  lea     rax, [rbp+cbData]
0x18000db44  mov     [rbp+Data], 4
0x18000db4b  xor     r9d, r9d; lpType
0x18000db4e  mov     [rsp+50h+phkResult], rax; lpData
0x18000db53  xor     r8d, r8d; lpReserved
0x18000db56  call    cs:__imp_RegQueryValueExW
0x18000db5c  mov     rcx, [rbp+hKey]; hKey
0x18000db60  call    cs:__imp_RegCloseKey
0x18000db66  mov     rcx, rbx; hMem
0x18000db69  call    cs:__imp_GlobalFree
0x18000db6f  lea     rax, [rbp+var_10]
0x18000db73  mov     r9d, 20019h; samDesired
0x18000db79  xor     r8d, r8d; ulOptions
0x18000db7c  mov     [rsp+50h+phkResult], rax; phkResult
0x18000db81  mov     rdx, rdi; lpSubKey
0x18000db84  mov     rcx, r12; hKey
0x18000db87  call    cs:__imp_RegOpenKeyExW
0x18000db8d  test    eax, eax
0x18000db8f  jnz     short loc_18000DBFB
0x18000db91  mov     rcx, [rbp+var_10]; hKey
0x18000db95  lea     rax, [rbp+arg_10]
0x18000db99  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18000db9e  lea     rdx, aConnectdisplay; "ConnectDisplay"
0x18000dba5  lea     rax, [rbp+var_1C]
0x18000dba9  mov     [rbp+arg_10], 4
0x18000dbb0  xor     r9d, r9d; lpType
0x18000dbb3  mov     [rsp+50h+phkResult], rax; lpData
0x18000dbb8  xor     r8d, r8d; lpReserved
0x18000dbbb  call    cs:__imp_RegQueryValueExW
0x18000dbc1  mov     rcx, [rbp+var_10]; hKey
0x18000dbc5  lea     rax, [rbp+arg_10]
0x18000dbc9  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18000dbce  lea     rdx, aDisplayconfirm; "DisplayConfirmation"
0x18000dbd5  lea     rax, [rbp+var_18]
0x18000dbd9  mov     [rbp+arg_10], 4
0x18000dbe0  xor     r9d, r9d; lpType
0x18000dbe3  mov     [rsp+50h+phkResult], rax; lpData
0x18000dbe8  xor     r8d, r8d; lpReserved
0x18000dbeb  call    cs:__imp_RegQueryValueExW
0x18000dbf1  mov     rcx, [rbp+var_10]; hKey
0x18000dbf5  call    cs:__imp_RegCloseKey
0x18000dbfb  mov     rbx, [rsp+50h+arg_0]
0x18000dc03  add     rsp, 50h
0x18000dc07  pop     r15
0x18000dc09  pop     r14
0x18000dc0b  pop     r13
0x18000dc0d  pop     r12
0x18000dc0f  pop     rdi
0x18000dc10  pop     rsi
0x18000dc11  pop     rbp
0x18000dc12  retn
```
