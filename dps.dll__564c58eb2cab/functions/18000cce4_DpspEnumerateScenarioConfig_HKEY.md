# DpspEnumerateScenarioConfig(HKEY__ *)

- ea: `0x18000cce4`
- end: `0x18000ce8b`
- name: `?DpspEnumerateScenarioConfig@@YAJPEAUHKEY__@@@Z`
- size: `423`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000e9d4`

## callees

- `0x180009090`
- `0x180009fb0`
- `0x18000a856`
- `0x18000cce4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ce62`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ce62`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000cd52`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000cd52`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000cd96`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000cddb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000cd96`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000cddb`
- `api-ms-win-core-sysinfo-l1-2-0!VerSetConditionMask` at `0x18000ce11`
- `api-ms-win-core-sysinfo-l1-2-0!VerSetConditionMask` at `0x18000ce11`
- `api-ms-win-core-kernel32-legacy-l1-1-1!VerifyVersionInfoW` at `0x18000ce21`
- `api-ms-win-core-kernel32-legacy-l1-1-1!VerifyVersionInfoW` at `0x18000ce21`

## string_xrefs

- `0x18000cd48`: `Config`
- `0x18000ce40`: `DpspEnumerateScenarioConfig`

## pseudocode

```c
__int64 __fastcall DpspEnumerateScenarioConfig(HKEY hKey)
{
  unsigned int v1; // edi
  int v3; // r8d
  ULONGLONG v4; // rax
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-CCh] BYREF
  BYTE v8[8]; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKeya; // [rsp+40h] [rbp-C0h] BYREF
  _OSVERSIONINFOEXW VersionInformation; // [rsp+50h] [rbp-B0h] BYREF

  v1 = 0;
  hKeya = 0;
  *(_DWORD *)Data = 0;
  *(_DWORD *)v8 = 0;
  cbData = 0;
  memset_0(&VersionInformation, 0, sizeof(VersionInformation));
  if ( !RegOpenKeyExW(hKey, L"Config", 0, 0x20019u, &hKeya) )
  {
    if ( !hKeya )
      return v1;
    cbData = 4;
    if ( !RegQueryValueExW(hKeya, L"ScenarioExecutionEnabled", 0, 0, Data, &cbData) && !*(_DWORD *)Data )
    {
      v3 = 985;
LABEL_10:
      v1 = -2147467260;
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsstate.cpp",
        (int)L"DpspEnumerateScenarioConfig",
        v3,
        (int)L"Error = %d",
        4);
      goto LABEL_11;
    }
    cbData = 4;
    if ( !RegQueryValueExW(hKeya, L"ScenarioExecutionRestrictions", 0, 0, v8, &cbData) && (v8[0] & 1) != 0 )
    {
      memset_0(&VersionInformation, 0, sizeof(VersionInformation));
      VersionInformation.wSuiteMask = 16;
      v4 = VerSetConditionMask(0, 0x40u, 6u);
      if ( VerifyVersionInfoW(&VersionInformation, 0x40u, v4) )
      {
        v3 = 1011;
        goto LABEL_10;
      }
    }
  }
LABEL_11:
  if ( hKeya )
    RegCloseKey(hKeya);
  return v1;
}

```

## disassembly

```asm
0x18000cce4  mov     [rsp-8+arg_8], rbx
0x18000cce9  mov     [rsp-8+arg_10], rdi
0x18000ccee  push    rbp
0x18000ccef  lea     rbp, [rsp-80h]
0x18000ccf4  sub     rsp, 180h
0x18000ccfb  mov     rax, cs:__security_cookie
0x18000cd02  xor     rax, rsp
0x18000cd05  mov     [rbp+80h+var_10], rax
0x18000cd09  xor     edi, edi
0x18000cd0b  mov     [rsp+180h+hKey], 0
0x18000cd14  mov     rbx, rcx
0x18000cd17  mov     dword ptr [rsp+180h+Data], edi
0x18000cd1b  lea     rcx, [rsp+180h+VersionInformation]; void *
0x18000cd20  mov     dword ptr [rsp+180h+var_148], edi
0x18000cd24  xor     edx, edx; Val
0x18000cd26  mov     [rsp+180h+cbData], edi
0x18000cd2a  mov     r8d, 11Ch; Size
0x18000cd30  call    memset_0
0x18000cd35  lea     rax, [rsp+180h+hKey]
0x18000cd3a  mov     r9d, 20019h; samDesired
0x18000cd40  xor     r8d, r8d; ulOptions
0x18000cd43  mov     [rsp+180h+phkResult], rax; phkResult
0x18000cd48  lea     rdx, aConfig; "Config"
0x18000cd4f  mov     rcx, rbx; hKey
0x18000cd52  call    cs:__imp_RegOpenKeyExW
0x18000cd58  test    eax, eax
0x18000cd5a  jnz     loc_18000CE58
0x18000cd60  mov     rcx, [rsp+180h+hKey]; hKey
0x18000cd65  test    rcx, rcx
0x18000cd68  jz      loc_18000CE68
0x18000cd6e  lea     rax, [rsp+180h+cbData]
0x18000cd73  xor     r9d, r9d; lpType
0x18000cd76  mov     [rsp+180h+lpcbData], rax; lpcbData
0x18000cd7b  lea     ebx, [rdi+4]
0x18000cd7e  lea     rax, [rsp+180h+Data]
0x18000cd83  mov     [rsp+180h+cbData], ebx
0x18000cd87  xor     r8d, r8d; lpReserved
0x18000cd8a  mov     [rsp+180h+phkResult], rax; lpData
0x18000cd8f  lea     rdx, aScenarioexecut; "ScenarioExecutionEnabled"
0x18000cd96  call    cs:__imp_RegQueryValueExW
0x18000cd9c  test    eax, eax
0x18000cd9e  jnz     short loc_18000CDB1
0x18000cda0  cmp     dword ptr [rsp+180h+Data], edi
0x18000cda4  jnz     short loc_18000CDB1
0x18000cda6  mov     r8d, 3D9h
0x18000cdac  jmp     loc_18000CE31
0x18000cdb1  mov     rcx, [rsp+180h+hKey]; hKey
0x18000cdb6  lea     rax, [rsp+180h+cbData]
0x18000cdbb  mov     [rsp+180h+lpcbData], rax; lpcbData
0x18000cdc0  lea     rdx, aScenarioexecut_0; "ScenarioExecutionRestrictions"
0x18000cdc7  lea     rax, [rsp+180h+var_148]
0x18000cdcc  mov     [rsp+180h+cbData], ebx
0x18000cdd0  xor     r9d, r9d; lpType
0x18000cdd3  mov     [rsp+180h+phkResult], rax; lpData
0x18000cdd8  xor     r8d, r8d; lpReserved
0x18000cddb  call    cs:__imp_RegQueryValueExW
0x18000cde1  test    eax, eax
0x18000cde3  jnz     short loc_18000CE58
0x18000cde5  test    [rsp+180h+var_148], 1
0x18000cdea  jz      short loc_18000CE58
0x18000cdec  xor     edx, edx; Val
0x18000cdee  lea     rcx, [rsp+180h+VersionInformation]; void *
0x18000cdf3  mov     r8d, 11Ch; Size
0x18000cdf9  call    memset_0
0x18000cdfe  mov     eax, 10h
0x18000ce03  mov     r8b, 6; Condition
0x18000ce06  xor     ecx, ecx; ConditionMask
0x18000ce08  mov     [rbp+80h+VersionInformation.wSuiteMask], ax
0x18000ce0c  lea     ebx, [rax+30h]
0x18000ce0f  mov     edx, ebx; TypeMask
0x18000ce11  call    cs:__imp_VerSetConditionMask
0x18000ce17  mov     edx, ebx; dwTypeMask
0x18000ce19  lea     rcx, [rsp+180h+VersionInformation]; lpVersionInformation
0x18000ce1e  mov     r8, rax; dwlConditionMask
0x18000ce21  call    cs:__imp_VerifyVersionInfoW
0x18000ce27  test    eax, eax
0x18000ce29  jz      short loc_18000CE58
0x18000ce2b  mov     r8d, 3F3h; int
0x18000ce31  lea     r9, aErrorD; "Error = %d"
0x18000ce38  mov     dword ptr [rsp+180h+phkResult], 4004h; Args
0x18000ce40  lea     rdx, aDpspenumerates; "DpspEnumerateScenarioConfig"
0x18000ce47  mov     edi, 80004004h
0x18000ce4c  lea     rcx, aClientcoreBase_8; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18000ce53  call    WdipTraceError
0x18000ce58  mov     rcx, [rsp+180h+hKey]; hKey
0x18000ce5d  test    rcx, rcx
0x18000ce60  jz      short loc_18000CE68
0x18000ce62  call    cs:__imp_RegCloseKey
0x18000ce68  mov     eax, edi
0x18000ce6a  mov     rcx, [rbp+80h+var_10]
0x18000ce6e  xor     rcx, rsp; StackCookie
0x18000ce71  call    __security_check_cookie
0x18000ce76  lea     r11, [rsp+180h+var_s0]
0x18000ce7e  mov     rbx, [r11+18h]
0x18000ce82  mov     rdi, [r11+20h]
0x18000ce86  mov     rsp, r11
0x18000ce89  pop     rbp
0x18000ce8a  retn
```
