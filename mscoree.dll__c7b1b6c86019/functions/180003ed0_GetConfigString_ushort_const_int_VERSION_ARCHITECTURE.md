# GetConfigString(ushort const *,int,VERSION_ARCHITECTURE)

- ea: `0x180003ed0`
- end: `0x180004161`
- name: `?GetConfigString@@YAPEAGPEBGHW4VERSION_ARCHITECTURE@@@Z`
- size: `657`
- prototype: ``
- caller_count: `7`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180001ff0`
- `0x180009af4`
- `0x18000af8c`
- `0x180029528`
- `0x180030798`
- `0x1800313bc`
- `0x180033604`

## callees

- `0x180003840`
- `0x180003ed0`
- `0x180004d50`
- `0x18000c1a8`
- `0x18000d614`
- `0x180041ac0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180003f82`
- `KERNEL32!GetLastError` at `0x18000408c`
- `KERNEL32!GetLastError` at `0x1800040f2`
- `KERNEL32!GetLastError` at `0x18000410d`
- `KERNEL32!GetLastError` at `0x180003f82`
- `KERNEL32!GetLastError` at `0x18000408c`
- `KERNEL32!GetLastError` at `0x1800040f2`
- `KERNEL32!GetLastError` at `0x18000410d`
- `KERNEL32!GetEnvironmentVariableW` at `0x180003f66`
- `KERNEL32!GetEnvironmentVariableW` at `0x180004144`
- `KERNEL32!GetEnvironmentVariableW` at `0x180003f66`
- `KERNEL32!GetEnvironmentVariableW` at `0x180004144`
- `KERNEL32!SetLastError` at `0x180004102`
- `KERNEL32!SetLastError` at `0x180004119`
- `KERNEL32!SetLastError` at `0x180004102`
- `KERNEL32!SetLastError` at `0x180004119`
- `ADVAPI32!RegOpenKeyExW` at `0x180004033`
- `ADVAPI32!RegOpenKeyExW` at `0x180004033`
- `ADVAPI32!RegQueryValueExW` at `0x180004060`
- `ADVAPI32!RegQueryValueExW` at `0x1800040d3`
- `ADVAPI32!RegQueryValueExW` at `0x180004060`
- `ADVAPI32!RegQueryValueExW` at `0x1800040d3`
- `ADVAPI32!RegCloseKey` at `0x1800040e7`
- `ADVAPI32!RegCloseKey` at `0x1800040e7`

## string_xrefs

- `0x180003f34`: `COMPlus_`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
WCHAR *__fastcall GetConfigString(const wchar_t *a1, int a2, int a3)
{
  unsigned __int64 v6; // rax
  signed int EnvironmentVariableW; // eax
  DWORD v8; // esi
  unsigned __int64 v9; // rbx
  DWORD LastError; // ebp
  WCHAR *v11; // rbx
  REGSAM v13; // r9d
  int v14; // eax
  unsigned __int64 v15; // rbx
  DWORD v16; // esi
  DWORD cbData; // [rsp+30h] [rbp-F8h] BYREF
  DWORD Type; // [rsp+34h] [rbp-F4h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-F0h] BYREF
  DWORD v20; // [rsp+40h] [rbp-E8h]
  int v21; // [rsp+44h] [rbp-E4h]
  wchar_t Destination[64]; // [rsp+50h] [rbp-D8h] BYREF

  hKey = 0;
  Type = 0;
  cbData = 0;
  v6 = -1;
  do
    ++v6;
  while ( a1[v6] );
  if ( v6 <= 0x37 )
  {
    wcscpy_s(Destination, 0x40u, L"COMPlus_");
    wcscat_s(Destination, 0x40u, a1);
    EnvironmentVariableW = GetEnvironmentVariableW(Destination, 0, 0);
    v8 = EnvironmentVariableW;
    if ( EnvironmentVariableW )
    {
      v9 = 2LL * EnvironmentVariableW;
      if ( !is_mul_ok(EnvironmentVariableW, 2u) )
        v9 = -1;
      LastError = GetLastError();
      v20 = LastError;
      v21 = 2;
      v11 = (WCHAR *)ClrAllocInProcessHeapBootstrap(0, v9);
      if ( LastError && !GetLastError() )
        SetLastError(LastError);
      if ( v11 )
      {
        GetEnvironmentVariableW(Destination, v11, v8);
        if ( *v11 )
          return v11;
        operator delete(v11);
      }
    }
  }
  v11 = 0;
  if ( a2 )
  {
    v13 = 131097;
    if ( g_OSVersionInfo.dwMajorVersion > 5 || g_OSVersionInfo.dwMajorVersion == 5 && g_OSVersionInfo.dwMinorVersion )
    {
      v14 = 131609;
      if ( a3 != 1 )
        v14 = 131097;
      v13 = v14;
      if ( (unsigned int)(a3 - 2) <= 1 )
        v13 = v14 | 0x100;
    }
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\.NETFramework", 0, v13, &hKey)
      && !RegQueryValueExW(hKey, a1, 0, &Type, 0, &cbData)
      && Type == 1
      && cbData > 1 )
    {
      v15 = 2LL * (cbData + 1);
      if ( !is_mul_ok(cbData + 1, 2u) )
        v15 = -1;
      v16 = GetLastError();
      v20 = v16;
      v21 = 2;
      v11 = (WCHAR *)ClrAllocInProcessHeapBootstrap(0, v15);
      if ( v16 && !GetLastError() )
        SetLastError(v16);
      if ( v11 )
        RegQueryValueExW(hKey, a1, 0, 0, (LPBYTE)v11, &cbData);
    }
    if ( hKey )
      RegCloseKey(hKey);
  }
  return v11;
}

```

## disassembly

```asm
0x180003ed0  push    rbx
0x180003ed2  push    rbp
0x180003ed3  push    rsi
0x180003ed4  push    rdi
0x180003ed5  push    r12
0x180003ed7  push    r13
0x180003ed9  push    r14
0x180003edb  push    r15
0x180003edd  sub     rsp, 0E8h
0x180003ee4  mov     rax, cs:__security_cookie
0x180003eeb  xor     rax, rsp
0x180003eee  mov     [rsp+128h+var_58], rax
0x180003ef6  mov     r15d, r8d
0x180003ef9  mov     r14d, edx
0x180003efc  mov     rdi, rcx
0x180003eff  xor     r12d, r12d
0x180003f02  mov     [rsp+128h+hKey], r12
0x180003f07  mov     [rsp+128h+Type], r12d
0x180003f0c  mov     [rsp+128h+cbData], r12d
0x180003f11  mov     r13, 0FFFFFFFFFFFFFFFFh
0x180003f18  mov     rax, r13
0x180003f1b  nop     dword ptr [rax+rax+00h]
0x180003f20  inc     rax
0x180003f23  cmp     [rcx+rax*2], r12w
0x180003f28  jnz     short loc_180003F20
0x180003f2a  cmp     rax, 37h ; '7'
0x180003f2e  ja      loc_180003FB4
0x180003f34  lea     r8, aComplus; "COMPlus_"
0x180003f3b  mov     edx, 40h ; '@'; SizeInWords
0x180003f40  lea     rcx, [rsp+128h+Destination]; Destination
0x180003f45  call    wcscpy_s
0x180003f4a  mov     r8, rdi; Source
0x180003f4d  mov     edx, 40h ; '@'; SizeInWords
0x180003f52  lea     rcx, [rsp+128h+Destination]; Destination
0x180003f57  call    wcscat_s
0x180003f5c  xor     r8d, r8d; nSize
0x180003f5f  xor     edx, edx; lpBuffer
0x180003f61  lea     rcx, [rsp+128h+Destination]; lpName
0x180003f66  call    cs:__imp_GetEnvironmentVariableW
0x180003f6c  movsxd  rsi, eax
0x180003f6f  test    eax, eax
0x180003f71  jz      short loc_180003FB4
0x180003f73  mov     eax, 2
0x180003f78  mul     rsi
0x180003f7b  mov     rbx, rax
0x180003f7e  cmovb   rbx, r13
0x180003f82  call    cs:__imp_GetLastError
0x180003f88  mov     ebp, eax
0x180003f8a  mov     [rsp+128h+var_E8], eax
0x180003f8e  mov     [rsp+128h+var_E4], 2
0x180003f96  mov     rdx, rbx; unsigned __int64
0x180003f99  xor     ecx, ecx; unsigned int
0x180003f9b  call    ?ClrAllocInProcessHeapBootstrap@@YAPEAXK_K@Z; ClrAllocInProcessHeapBootstrap(ulong,unsigned __int64)
0x180003fa0  mov     rbx, rax
0x180003fa3  test    ebp, ebp
0x180003fa5  jnz     loc_1800040F2
0x180003fab  test    rbx, rbx
0x180003fae  jnz     loc_180004139
0x180003fb4  mov     rbx, r12
0x180003fb7  test    r14d, r14d
0x180003fba  jnz     short loc_180003FE3
0x180003fbc  mov     rax, rbx
0x180003fbf  mov     rcx, [rsp+128h+var_58]
0x180003fc7  xor     rcx, rsp; StackCookie
0x180003fca  call    __security_check_cookie
0x180003fcf  add     rsp, 0E8h
0x180003fd6  pop     r15
0x180003fd8  pop     r14
0x180003fda  pop     r13
0x180003fdc  pop     r12
0x180003fde  pop     rdi
0x180003fdf  pop     rsi
0x180003fe0  pop     rbp
0x180003fe1  pop     rbx
0x180003fe2  retn
0x180003fe3  mov     r9d, 20019h
0x180003fe9  cmp     cs:?g_OSVersionInfo@@3U_OSVERSIONINFOW@@A.dwMajorVersion, 5; _OSVERSIONINFOW g_OSVersionInfo ...
0x180003ff0  jbe     loc_180004121
0x180003ff6  mov     eax, 20219h
0x180003ffb  cmp     r15d, 1
0x180003fff  cmovnz  eax, r9d
0x180004003  mov     r9d, eax
0x180004006  lea     eax, [r15-2]
0x18000400a  mov     ecx, r9d
0x18000400d  bts     ecx, 8
0x180004011  cmp     eax, 1
0x180004014  cmovbe  r9d, ecx; samDesired
0x180004018  lea     rax, [rsp+128h+hKey]
0x18000401d  mov     [rsp+128h+phkResult], rax; phkResult
0x180004022  xor     r8d, r8d; ulOptions
0x180004025  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\.NETFramework"
0x18000402c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180004033  call    cs:__imp_RegOpenKeyExW
0x180004039  test    eax, eax
0x18000403b  jnz     loc_1800040D9
0x180004041  lea     rax, [rsp+128h+cbData]
0x180004046  mov     [rsp+128h+lpcbData], rax; lpcbData
0x18000404b  mov     [rsp+128h+phkResult], r12; lpData
0x180004050  lea     r9, [rsp+128h+Type]; lpType
0x180004055  xor     r8d, r8d; lpReserved
0x180004058  mov     rdx, rdi; lpValueName
0x18000405b  mov     rcx, [rsp+128h+hKey]; hKey
0x180004060  call    cs:__imp_RegQueryValueExW
0x180004066  test    eax, eax
0x180004068  jnz     short loc_1800040D9
0x18000406a  cmp     [rsp+128h+Type], 1
0x18000406f  jnz     short loc_1800040D9
0x180004071  mov     eax, [rsp+128h+cbData]
0x180004075  cmp     eax, 1
0x180004078  jbe     short loc_1800040D9
0x18000407a  lea     ecx, [rax+1]
0x18000407d  mov     eax, 2
0x180004082  mul     rcx
0x180004085  mov     rbx, rax
0x180004088  cmovb   rbx, r13
0x18000408c  call    cs:__imp_GetLastError
0x180004092  mov     esi, eax
0x180004094  mov     [rsp+128h+var_E8], eax
0x180004098  mov     [rsp+128h+var_E4], 2
0x1800040a0  mov     rdx, rbx; unsigned __int64
0x1800040a3  xor     ecx, ecx; unsigned int
0x1800040a5  call    ?ClrAllocInProcessHeapBootstrap@@YAPEAXK_K@Z; ClrAllocInProcessHeapBootstrap(ulong,unsigned __int64)
0x1800040aa  mov     rbx, rax
0x1800040ad  test    esi, esi
0x1800040af  jnz     short loc_18000410D
0x1800040b1  test    rbx, rbx
0x1800040b4  jz      short loc_1800040D9
0x1800040b6  lea     rax, [rsp+128h+cbData]
0x1800040bb  mov     [rsp+128h+lpcbData], rax; lpcbData
0x1800040c0  mov     [rsp+128h+phkResult], rbx; lpData
0x1800040c5  xor     r9d, r9d; lpType
0x1800040c8  xor     r8d, r8d; lpReserved
0x1800040cb  mov     rdx, rdi; lpValueName
0x1800040ce  mov     rcx, [rsp+128h+hKey]; hKey
0x1800040d3  call    cs:__imp_RegQueryValueExW
0x1800040d9  mov     rcx, [rsp+128h+hKey]; hKey
0x1800040de  test    rcx, rcx
0x1800040e1  jz      loc_180003FBC
0x1800040e7  call    cs:__imp_RegCloseKey
0x1800040ed  jmp     loc_180003FBC
0x1800040f2  call    cs:__imp_GetLastError
0x1800040f8  test    eax, eax
0x1800040fa  jnz     loc_180003FAB
0x180004100  mov     ecx, ebp; dwErrCode
0x180004102  call    cs:__imp_SetLastError
0x180004108  jmp     loc_180003FAB
0x18000410d  call    cs:__imp_GetLastError
0x180004113  test    eax, eax
0x180004115  jnz     short loc_1800040B1
0x180004117  mov     ecx, esi; dwErrCode
0x180004119  call    cs:__imp_SetLastError
0x18000411f  jmp     short loc_1800040B1
0x180004121  jnz     loc_180004018
0x180004127  cmp     cs:?g_OSVersionInfo@@3U_OSVERSIONINFOW@@A.dwMinorVersion, 0; _OSVERSIONINFOW g_OSVersionInfo ...
0x18000412e  jbe     loc_180004018
0x180004134  jmp     loc_180003FF6
0x180004139  mov     r8d, esi; nSize
0x18000413c  mov     rdx, rbx; lpBuffer
0x18000413f  lea     rcx, [rsp+128h+Destination]; lpName
0x180004144  call    cs:__imp_GetEnvironmentVariableW
0x18000414a  cmp     word ptr [rbx], 0
0x18000414e  jnz     loc_180003FBC
0x180004154  mov     rcx, rbx; void *
0x180004157  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000415c  jmp     loc_180003FB4
```
