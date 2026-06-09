# gp::CLauncherGroupPolicy::GetPolicy(void)

- ea: `0x18000b180`
- end: `0x18000b3a3`
- name: `?GetPolicy@CLauncherGroupPolicy@gp@@SA?AW4LauncherGroupPolicyState@2@XZ`
- size: `547`
- prototype: `__int64()`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x1800091c0`
- `0x18000946c`
- `0x18000a4e8`

## callees

- `0x180002148`
- `0x18000253c`
- `0x180008b30`
- `0x18000b180`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x18000b213`
- `ADVAPI32!RegQueryValueExW` at `0x18000b213`
- `ADVAPI32!RegCloseKey` at `0x18000b23f`
- `ADVAPI32!RegCloseKey` at `0x18000b254`
- `ADVAPI32!RegCloseKey` at `0x18000b272`
- `ADVAPI32!RegCloseKey` at `0x18000b23f`
- `ADVAPI32!RegCloseKey` at `0x18000b254`
- `ADVAPI32!RegCloseKey` at `0x18000b272`
- `ADVAPI32!RegOpenKeyExW` at `0x18000b1cd`
- `ADVAPI32!RegOpenKeyExW` at `0x18000b1cd`

## string_xrefs

- `0x18000b2b5`: `drivers\wdm\usbpw\launcher\dll\claunchergrouppolicy.cpp`
- `0x18000b311`: `drivers\wdm\usbpw\launcher\dll\claunchergrouppolicy.cpp`
- `0x18000b36d`: `drivers\wdm\usbpw\launcher\dll\claunchergrouppolicy.cpp`

## pseudocode

```c
__int64 gp::CLauncherGroupPolicy::GetPolicy()
{
  LSTATUS v0; // eax
  HKEY v1; // rbx
  LSTATUS v2; // eax
  HKEY v4; // [rsp+30h] [rbp-20h]
  HKEY hKey; // [rsp+60h] [rbp+10h] BYREF
  int Data; // [rsp+68h] [rbp+18h] BYREF
  DWORD cbData; // [rsp+70h] [rbp+20h] BYREF

  hKey = 0;
  v0 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, gp::CLauncherGroupPolicy::KEY_PATH, 0, 0x20019u, &hKey);
  if ( v0 )
  {
    if ( v0 != 2 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          (unsigned int)&WPP_ef853054c05831a47345c60e532c49bf_Traceguids,
          (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\claunchergrouppolicy.cpp",
          55);
      ATL::CAtlException::CAtlException((ATL::CAtlException *)&hKey, -2147467259);
      throw (ATL::CAtlException *)&hKey;
    }
    return 1;
  }
  v1 = hKey;
  v4 = hKey;
  Data = 0;
  LODWORD(hKey) = 0;
  cbData = 4;
  v2 = RegQueryValueExW(v4, gp::CLauncherGroupPolicy::VALUE_NAME, 0, (LPDWORD)&hKey, (LPBYTE)&Data, &cbData);
  if ( v2 )
  {
    if ( v2 != 2 )
      goto LABEL_25;
    if ( v1 )
      RegCloseKey(v1);
    return 1;
  }
  if ( (_DWORD)hKey != 4 )
  {
LABEL_25:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        (unsigned int)&WPP_ef853054c05831a47345c60e532c49bf_Traceguids,
        (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\claunchergrouppolicy.cpp",
        64);
    ATL::CAtlException::CAtlException((ATL::CAtlException *)&hKey, -2147467259);
    throw (ATL::CAtlException *)&hKey;
  }
  if ( Data )
  {
    if ( Data != 1 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          12,
          (unsigned int)&WPP_ef853054c05831a47345c60e532c49bf_Traceguids,
          (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\claunchergrouppolicy.cpp",
          70);
      ATL::CAtlException::CAtlException((ATL::CAtlException *)&hKey, -2147467259);
      throw (ATL::CAtlException *)&hKey;
    }
    if ( v1 )
      RegCloseKey(v1);
    return 2;
  }
  else
  {
    if ( v1 )
      RegCloseKey(v1);
    return 3;
  }
}

```

## disassembly

```asm
0x18000b180  mov     [rsp-8+arg_18], rbx
0x18000b185  push    rbp
0x18000b186  mov     rbp, rsp
0x18000b189  sub     rsp, 50h
0x18000b18d  mov     [rbp+var_20], 0
0x18000b195  mov     [rbp+var_18], 0
0x18000b19d  mov     [rbp+var_10], 0
0x18000b1a5  mov     [rbp+hKey], 0
0x18000b1ad  lea     rax, [rbp+hKey]
0x18000b1b1  mov     [rsp+50h+phkResult], rax; phkResult
0x18000b1b6  mov     r9d, 20019h; samDesired
0x18000b1bc  xor     r8d, r8d; ulOptions
0x18000b1bf  mov     rdx, cs:?KEY_PATH@CLauncherGroupPolicy@gp@@0V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@B; lpSubKey
0x18000b1c6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000b1cd  call    cs:__imp_RegOpenKeyExW
0x18000b1d3  test    eax, eax
0x18000b1d5  jnz     loc_18000B27A
0x18000b1db  mov     rbx, [rbp+hKey]
0x18000b1df  mov     [rbp+var_20], rbx
0x18000b1e3  mov     [rbp+Data], eax
0x18000b1e6  mov     dword ptr [rbp+hKey], eax
0x18000b1e9  mov     [rbp+cbData], 4
0x18000b1f0  lea     rax, [rbp+cbData]
0x18000b1f4  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18000b1f9  lea     rax, [rbp+Data]
0x18000b1fd  mov     [rsp+50h+phkResult], rax; lpData
0x18000b202  lea     r9, [rbp+hKey]; lpType
0x18000b206  xor     r8d, r8d; lpReserved
0x18000b209  mov     rdx, cs:?VALUE_NAME@CLauncherGroupPolicy@gp@@0V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@B; lpValueName
0x18000b210  mov     rcx, rbx; hKey
0x18000b213  call    cs:__imp_RegQueryValueExW
0x18000b219  test    eax, eax
0x18000b21b  jnz     short loc_18000B261
0x18000b21d  cmp     dword ptr [rbp+hKey], 4
0x18000b221  jnz     loc_18000B347
0x18000b227  mov     eax, [rbp+Data]
0x18000b22a  test    eax, eax
0x18000b22c  jz      short loc_18000B24C
0x18000b22e  cmp     eax, 1
0x18000b231  jnz     loc_18000B2EB
0x18000b237  test    rbx, rbx
0x18000b23a  jz      short loc_18000B245
0x18000b23c  mov     rcx, rbx; hKey
0x18000b23f  call    cs:__imp_RegCloseKey
0x18000b245  mov     eax, 2
0x18000b24a  jmp     short loc_18000B284
0x18000b24c  test    rbx, rbx
0x18000b24f  jz      short loc_18000B25A
0x18000b251  mov     rcx, rbx; hKey
0x18000b254  call    cs:__imp_RegCloseKey
0x18000b25a  mov     eax, 3
0x18000b25f  jmp     short loc_18000B284
0x18000b261  cmp     eax, 2
0x18000b264  jnz     loc_18000B347
0x18000b26a  test    rbx, rbx
0x18000b26d  jz      short loc_18000B27F
0x18000b26f  mov     rcx, rbx; hKey
0x18000b272  call    cs:__imp_RegCloseKey
0x18000b278  jmp     short loc_18000B27F
0x18000b27a  cmp     eax, 2
0x18000b27d  jnz     short loc_18000B28F
0x18000b27f  mov     eax, 1
0x18000b284  mov     rbx, [rsp+50h+arg_18]
0x18000b289  add     rsp, 50h
0x18000b28d  pop     rbp
0x18000b28e  retn
0x18000b28f  lea     rax, WPP_GLOBAL_Control
0x18000b296  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b29d  cmp     rcx, rax
0x18000b2a0  jz      short loc_18000B2CC
0x18000b2a2  test    byte ptr [rcx+1Ch], 1
0x18000b2a6  jz      short loc_18000B2CC
0x18000b2a8  mov     edx, 0Ah
0x18000b2ad  mov     dword ptr [rsp+50h+phkResult], 37h ; '7'
0x18000b2b5  lea     r9, aDriversWdmUsbp_1; "drivers\\wdm\\usbpw\\launcher\\dll\\cla"...
0x18000b2bc  lea     r8, WPP_ef853054c05831a47345c60e532c49bf_Traceguids
0x18000b2c3  mov     rcx, [rcx+10h]
0x18000b2c7  call    WPP_SF_sd
0x18000b2cc  mov     edx, 80004005h; int
0x18000b2d1  lea     rcx, [rbp+hKey]; this
0x18000b2d5  call    ??0CAtlException@ATL@@QEAA@J@Z; ATL::CAtlException::CAtlException(long)
0x18000b2da  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x18000b2e1  lea     rcx, [rbp+hKey]; pExceptionObject
0x18000b2e5  call    _CxxThrowException_0
0x18000b2eb  lea     rax, WPP_GLOBAL_Control
0x18000b2f2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b2f9  cmp     rcx, rax
0x18000b2fc  jz      short loc_18000B328
0x18000b2fe  test    byte ptr [rcx+1Ch], 1
0x18000b302  jz      short loc_18000B328
0x18000b304  mov     edx, 0Ch
0x18000b309  mov     dword ptr [rsp+50h+phkResult], 46h ; 'F'
0x18000b311  lea     r9, aDriversWdmUsbp_1; "drivers\\wdm\\usbpw\\launcher\\dll\\cla"...
0x18000b318  lea     r8, WPP_ef853054c05831a47345c60e532c49bf_Traceguids
0x18000b31f  mov     rcx, [rcx+10h]
0x18000b323  call    WPP_SF_sd
0x18000b328  mov     edx, 80004005h; int
0x18000b32d  lea     rcx, [rbp+hKey]; this
0x18000b331  call    ??0CAtlException@ATL@@QEAA@J@Z; ATL::CAtlException::CAtlException(long)
0x18000b336  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x18000b33d  lea     rcx, [rbp+hKey]; pExceptionObject
0x18000b341  call    _CxxThrowException_0
0x18000b347  lea     rax, WPP_GLOBAL_Control
0x18000b34e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b355  cmp     rcx, rax
0x18000b358  jz      short loc_18000B384
0x18000b35a  test    byte ptr [rcx+1Ch], 1
0x18000b35e  jz      short loc_18000B384
0x18000b360  mov     edx, 0Bh
0x18000b365  mov     dword ptr [rsp+50h+phkResult], 40h ; '@'
0x18000b36d  lea     r9, aDriversWdmUsbp_1; "drivers\\wdm\\usbpw\\launcher\\dll\\cla"...
0x18000b374  lea     r8, WPP_ef853054c05831a47345c60e532c49bf_Traceguids
0x18000b37b  mov     rcx, [rcx+10h]
0x18000b37f  call    WPP_SF_sd
0x18000b384  mov     edx, 80004005h; int
0x18000b389  lea     rcx, [rbp+hKey]; this
0x18000b38d  call    ??0CAtlException@ATL@@QEAA@J@Z; ATL::CAtlException::CAtlException(long)
0x18000b392  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x18000b399  lea     rcx, [rbp+hKey]; pExceptionObject
0x18000b39d  call    _CxxThrowException_0
```
