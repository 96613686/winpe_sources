# IsIcsDnsFallbackDisabled(void)

- ea: `0x180029a48`
- end: `0x180029be8`
- name: `?IsIcsDnsFallbackDisabled@@YAHXZ`
- size: `416`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x180028924`

## callees

- `0x18000c110`
- `0x180029a48`
- `0x18004e0c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180029b5e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180029b5e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180029b31`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180029b31`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029bbd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029bbd`

## string_xrefs

- `0x180029a8b`: `System\CurrentControlSet\Services\SharedAccess\Parameters`

## pseudocode

```c
_BOOL8 IsIcsDnsFallbackDisabled(void)
{
  BOOL v0; // ebx
  BYTE Data[4]; // [rsp+30h] [rbp-89h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-85h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-81h] BYREF
  WCHAR ValueName[16]; // [rsp+40h] [rbp-79h] BYREF
  WCHAR SubKey[64]; // [rsp+60h] [rbp-59h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_9be8243bb99535625437fc4fc0071459_Traceguids);
  }
  v0 = 0;
  wcscpy(SubKey, L"System\\CurrentControlSet\\Services\\SharedAccess\\Parameters");
  hKey = 0;
  wcscpy(ValueName, L"DisableFallback");
  cbData = 4;
  *(_DWORD *)Data = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 1u, &hKey)
    && !RegQueryValueExW(hKey, ValueName, 0, 0, Data, &cbData) )
  {
    v0 = *(_DWORD *)Data != 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_9be8243bb99535625437fc4fc0071459_Traceguids);
  }
  return v0;
}

```

## disassembly

```asm
0x180029a48  push    rbp
0x180029a4a  push    rbx
0x180029a4b  push    rsi
0x180029a4c  push    r14
0x180029a4e  lea     rbp, [rsp-3Fh]
0x180029a53  sub     rsp, 0F8h
0x180029a5a  mov     rax, cs:__security_cookie
0x180029a61  xor     rax, rsp
0x180029a64  mov     [rbp+57h+var_30], rax
0x180029a68  mov     rcx, cs:WPP_GLOBAL_Control
0x180029a6f  lea     rsi, WPP_GLOBAL_Control
0x180029a76  cmp     rcx, rsi
0x180029a79  jz      short loc_180029A8B
0x180029a7b  test    byte ptr [rcx+1Ch], 10h
0x180029a7f  jz      short loc_180029A8B
0x180029a81  cmp     byte ptr [rcx+19h], 6
0x180029a85  jnb     loc_180029B99
0x180029a8b  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\Sh"...
0x180029a92  lea     rdx, [rbp+57h+SubKey]; lpSubKey
0x180029a96  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_2+10h; "urrentControlSet\\Services\\SharedAcces"...
0x180029a9d  xor     ebx, ebx
0x180029a9f  mov     eax, dword ptr cs:aSystemCurrentc_2+70h; "s"
0x180029aa5  xor     r8d, r8d; ulOptions
0x180029aa8  movaps  xmmword ptr [rbp+57h+SubKey], xmm0
0x180029aac  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180029ab3  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2+20h; "ntrolSet\\Services\\SharedAccess\\Param"...
0x180029aba  movaps  [rbp+57h+var_90], xmm0
0x180029abe  lea     r14d, [rbx+1]
0x180029ac2  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2+40h; "s\\SharedAccess\\Parameters"
0x180029ac9  mov     r9d, r14d; samDesired
0x180029acc  movaps  [rbp+57h+var_A0], xmm1
0x180029ad0  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_2+30h; "\\Services\\SharedAccess\\Parameters"
0x180029ad7  movaps  [rbp+57h+var_70], xmm0
0x180029adb  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2+60h; "arameters"
0x180029ae2  movaps  [rbp+57h+var_80], xmm1
0x180029ae6  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_2+50h; "Access\\Parameters"
0x180029aed  movaps  [rbp+57h+var_50], xmm0
0x180029af1  movups  xmm0, xmmword ptr cs:aDisablefallbac; "DisableFallback"
0x180029af8  mov     [rbp+57h+var_40], eax
0x180029afb  lea     rax, [rsp+110h+hKey]
0x180029b00  movaps  [rbp+57h+var_60], xmm1
0x180029b04  movups  xmm1, xmmword ptr cs:aDisablefallbac+10h; "allback"
0x180029b0b  mov     [rsp+110h+hKey], 0
0x180029b14  movups  xmmword ptr [rbp+57h+ValueName], xmm0
0x180029b18  mov     [rsp+110h+cbData], 4
0x180029b20  mov     dword ptr [rsp+110h+Data], 0
0x180029b28  movups  [rbp+57h+var_C0], xmm1
0x180029b2c  mov     [rsp+110h+phkResult], rax; phkResult
0x180029b31  call    cs:__imp_RegOpenKeyExW
0x180029b37  test    eax, eax
0x180029b39  jnz     short loc_180029B68
0x180029b3b  mov     rcx, [rsp+110h+hKey]; hKey
0x180029b40  lea     rax, [rsp+110h+cbData]
0x180029b45  mov     [rsp+110h+lpcbData], rax; lpcbData
0x180029b4a  lea     rdx, [rbp+57h+ValueName]; lpValueName
0x180029b4e  lea     rax, [rsp+110h+Data]
0x180029b53  xor     r9d, r9d; lpType
0x180029b56  xor     r8d, r8d; lpReserved
0x180029b59  mov     [rsp+110h+phkResult], rax; lpData
0x180029b5e  call    cs:__imp_RegQueryValueExW
0x180029b64  test    eax, eax
0x180029b66  jz      short loc_180029BB3
0x180029b68  mov     rcx, [rsp+110h+hKey]; hKey
0x180029b6d  test    rcx, rcx
0x180029b70  jnz     short loc_180029BBD
0x180029b72  mov     rcx, cs:WPP_GLOBAL_Control
0x180029b79  cmp     rcx, rsi
0x180029b7c  jnz     short loc_180029BC5
0x180029b7e  mov     eax, ebx
0x180029b80  mov     rcx, [rbp+57h+var_30]
0x180029b84  xor     rcx, rsp; StackCookie
0x180029b87  call    __security_check_cookie
0x180029b8c  add     rsp, 0F8h
0x180029b93  pop     r14
0x180029b95  pop     rsi
0x180029b96  pop     rbx
0x180029b97  pop     rbp
0x180029b98  retn
0x180029b99  mov     rcx, [rcx+10h]
0x180029b9d  lea     r8, WPP_9be8243bb99535625437fc4fc0071459_Traceguids
0x180029ba4  mov     edx, 0Ah
0x180029ba9  call    WPP_SF_
0x180029bae  jmp     loc_180029A8B
0x180029bb3  cmp     dword ptr [rsp+110h+Data], ebx
0x180029bb7  cmovnz  ebx, r14d
0x180029bbb  jmp     short loc_180029B68
0x180029bbd  call    cs:__imp_RegCloseKey
0x180029bc3  jmp     short loc_180029B72
0x180029bc5  test    byte ptr [rcx+1Ch], 10h
0x180029bc9  jz      short loc_180029B7E
0x180029bcb  cmp     byte ptr [rcx+19h], 6
0x180029bcf  jb      short loc_180029B7E
0x180029bd1  mov     rcx, [rcx+10h]
0x180029bd5  lea     r8, WPP_9be8243bb99535625437fc4fc0071459_Traceguids
0x180029bdc  mov     edx, 0Bh
0x180029be1  call    WPP_SF_
0x180029be6  jmp     short loc_180029B7E
```
