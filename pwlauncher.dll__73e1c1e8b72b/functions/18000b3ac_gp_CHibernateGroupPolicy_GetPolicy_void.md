# gp::CHibernateGroupPolicy::GetPolicy(void)

- ea: `0x18000b3ac`
- end: `0x18000b5cf`
- name: `?GetPolicy@CHibernateGroupPolicy@gp@@CA?AW4HibernateGroupPolicy@2@XZ`
- size: `547`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18000b5d8`

## callees

- `0x180002148`
- `0x18000253c`
- `0x180008b30`
- `0x18000b3ac`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x18000b43f`
- `ADVAPI32!RegQueryValueExW` at `0x18000b43f`
- `ADVAPI32!RegCloseKey` at `0x18000b46b`
- `ADVAPI32!RegCloseKey` at `0x18000b480`
- `ADVAPI32!RegCloseKey` at `0x18000b49e`
- `ADVAPI32!RegCloseKey` at `0x18000b46b`
- `ADVAPI32!RegCloseKey` at `0x18000b480`
- `ADVAPI32!RegCloseKey` at `0x18000b49e`
- `ADVAPI32!RegOpenKeyExW` at `0x18000b3f9`
- `ADVAPI32!RegOpenKeyExW` at `0x18000b3f9`

## string_xrefs

- `0x18000b4e1`: `drivers\wdm\usbpw\launcher\dll\chibernategrouppolicy.cpp`
- `0x18000b53d`: `drivers\wdm\usbpw\launcher\dll\chibernategrouppolicy.cpp`
- `0x18000b599`: `drivers\wdm\usbpw\launcher\dll\chibernategrouppolicy.cpp`

## pseudocode

```c
__int64 gp::CHibernateGroupPolicy::GetPolicy()
{
  LSTATUS v0; // eax
  HKEY v1; // rbx
  LSTATUS v2; // eax
  HKEY v4; // [rsp+30h] [rbp-20h]
  HKEY hKey; // [rsp+60h] [rbp+10h] BYREF
  int Data; // [rsp+68h] [rbp+18h] BYREF
  DWORD cbData; // [rsp+70h] [rbp+20h] BYREF

  hKey = 0;
  v0 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, gp::CHibernateGroupPolicy::POLICY_KEY_PATH, 0, 0x20019u, &hKey);
  if ( v0 )
  {
    if ( v0 != 2 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          (unsigned int)&WPP_41015684a9fe312220e27f269d4aeb4f_Traceguids,
          (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\chibernategrouppolicy.cpp",
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
  v2 = RegQueryValueExW(v4, gp::CHibernateGroupPolicy::POLICY_VALUE_NAME, 0, (LPDWORD)&hKey, (LPBYTE)&Data, &cbData);
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
        (unsigned int)&WPP_41015684a9fe312220e27f269d4aeb4f_Traceguids,
        (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\chibernategrouppolicy.cpp",
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
          (unsigned int)&WPP_41015684a9fe312220e27f269d4aeb4f_Traceguids,
          (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\chibernategrouppolicy.cpp",
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
0x18000b3ac  mov     [rsp-8+arg_18], rbx
0x18000b3b1  push    rbp
0x18000b3b2  mov     rbp, rsp
0x18000b3b5  sub     rsp, 50h
0x18000b3b9  mov     [rbp+var_20], 0
0x18000b3c1  mov     [rbp+var_18], 0
0x18000b3c9  mov     [rbp+var_10], 0
0x18000b3d1  mov     [rbp+hKey], 0
0x18000b3d9  lea     rax, [rbp+hKey]
0x18000b3dd  mov     [rsp+50h+phkResult], rax; phkResult
0x18000b3e2  mov     r9d, 20019h; samDesired
0x18000b3e8  xor     r8d, r8d; ulOptions
0x18000b3eb  mov     rdx, cs:?POLICY_KEY_PATH@CHibernateGroupPolicy@gp@@0V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@B; lpSubKey
0x18000b3f2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000b3f9  call    cs:__imp_RegOpenKeyExW
0x18000b3ff  test    eax, eax
0x18000b401  jnz     loc_18000B4A6
0x18000b407  mov     rbx, [rbp+hKey]
0x18000b40b  mov     [rbp+var_20], rbx
0x18000b40f  mov     [rbp+Data], eax
0x18000b412  mov     dword ptr [rbp+hKey], eax
0x18000b415  mov     [rbp+cbData], 4
0x18000b41c  lea     rax, [rbp+cbData]
0x18000b420  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18000b425  lea     rax, [rbp+Data]
0x18000b429  mov     [rsp+50h+phkResult], rax; lpData
0x18000b42e  lea     r9, [rbp+hKey]; lpType
0x18000b432  xor     r8d, r8d; lpReserved
0x18000b435  mov     rdx, cs:?POLICY_VALUE_NAME@CHibernateGroupPolicy@gp@@0V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@B; lpValueName
0x18000b43c  mov     rcx, rbx; hKey
0x18000b43f  call    cs:__imp_RegQueryValueExW
0x18000b445  test    eax, eax
0x18000b447  jnz     short loc_18000B48D
0x18000b449  cmp     dword ptr [rbp+hKey], 4
0x18000b44d  jnz     loc_18000B573
0x18000b453  mov     eax, [rbp+Data]
0x18000b456  test    eax, eax
0x18000b458  jz      short loc_18000B478
0x18000b45a  cmp     eax, 1
0x18000b45d  jnz     loc_18000B517
0x18000b463  test    rbx, rbx
0x18000b466  jz      short loc_18000B471
0x18000b468  mov     rcx, rbx; hKey
0x18000b46b  call    cs:__imp_RegCloseKey
0x18000b471  mov     eax, 2
0x18000b476  jmp     short loc_18000B4B0
0x18000b478  test    rbx, rbx
0x18000b47b  jz      short loc_18000B486
0x18000b47d  mov     rcx, rbx; hKey
0x18000b480  call    cs:__imp_RegCloseKey
0x18000b486  mov     eax, 3
0x18000b48b  jmp     short loc_18000B4B0
0x18000b48d  cmp     eax, 2
0x18000b490  jnz     loc_18000B573
0x18000b496  test    rbx, rbx
0x18000b499  jz      short loc_18000B4AB
0x18000b49b  mov     rcx, rbx; hKey
0x18000b49e  call    cs:__imp_RegCloseKey
0x18000b4a4  jmp     short loc_18000B4AB
0x18000b4a6  cmp     eax, 2
0x18000b4a9  jnz     short loc_18000B4BB
0x18000b4ab  mov     eax, 1
0x18000b4b0  mov     rbx, [rsp+50h+arg_18]
0x18000b4b5  add     rsp, 50h
0x18000b4b9  pop     rbp
0x18000b4ba  retn
0x18000b4bb  lea     rax, WPP_GLOBAL_Control
0x18000b4c2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b4c9  cmp     rcx, rax
0x18000b4cc  jz      short loc_18000B4F8
0x18000b4ce  test    byte ptr [rcx+1Ch], 1
0x18000b4d2  jz      short loc_18000B4F8
0x18000b4d4  mov     edx, 0Ah
0x18000b4d9  mov     dword ptr [rsp+50h+phkResult], 37h ; '7'
0x18000b4e1  lea     r9, aDriversWdmUsbp_9; "drivers\\wdm\\usbpw\\launcher\\dll\\chi"...
0x18000b4e8  lea     r8, WPP_41015684a9fe312220e27f269d4aeb4f_Traceguids
0x18000b4ef  mov     rcx, [rcx+10h]
0x18000b4f3  call    WPP_SF_sd
0x18000b4f8  mov     edx, 80004005h; int
0x18000b4fd  lea     rcx, [rbp+hKey]; this
0x18000b501  call    ??0CAtlException@ATL@@QEAA@J@Z; ATL::CAtlException::CAtlException(long)
0x18000b506  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x18000b50d  lea     rcx, [rbp+hKey]; pExceptionObject
0x18000b511  call    _CxxThrowException_0
0x18000b517  lea     rax, WPP_GLOBAL_Control
0x18000b51e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b525  cmp     rcx, rax
0x18000b528  jz      short loc_18000B554
0x18000b52a  test    byte ptr [rcx+1Ch], 1
0x18000b52e  jz      short loc_18000B554
0x18000b530  mov     edx, 0Ch
0x18000b535  mov     dword ptr [rsp+50h+phkResult], 46h ; 'F'
0x18000b53d  lea     r9, aDriversWdmUsbp_9; "drivers\\wdm\\usbpw\\launcher\\dll\\chi"...
0x18000b544  lea     r8, WPP_41015684a9fe312220e27f269d4aeb4f_Traceguids
0x18000b54b  mov     rcx, [rcx+10h]
0x18000b54f  call    WPP_SF_sd
0x18000b554  mov     edx, 80004005h; int
0x18000b559  lea     rcx, [rbp+hKey]; this
0x18000b55d  call    ??0CAtlException@ATL@@QEAA@J@Z; ATL::CAtlException::CAtlException(long)
0x18000b562  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x18000b569  lea     rcx, [rbp+hKey]; pExceptionObject
0x18000b56d  call    _CxxThrowException_0
0x18000b573  lea     rax, WPP_GLOBAL_Control
0x18000b57a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b581  cmp     rcx, rax
0x18000b584  jz      short loc_18000B5B0
0x18000b586  test    byte ptr [rcx+1Ch], 1
0x18000b58a  jz      short loc_18000B5B0
0x18000b58c  mov     edx, 0Bh
0x18000b591  mov     dword ptr [rsp+50h+phkResult], 40h ; '@'
0x18000b599  lea     r9, aDriversWdmUsbp_9; "drivers\\wdm\\usbpw\\launcher\\dll\\chi"...
0x18000b5a0  lea     r8, WPP_41015684a9fe312220e27f269d4aeb4f_Traceguids
0x18000b5a7  mov     rcx, [rcx+10h]
0x18000b5ab  call    WPP_SF_sd
0x18000b5b0  mov     edx, 80004005h; int
0x18000b5b5  lea     rcx, [rbp+hKey]; this
0x18000b5b9  call    ??0CAtlException@ATL@@QEAA@J@Z; ATL::CAtlException::CAtlException(long)
0x18000b5be  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x18000b5c5  lea     rcx, [rbp+hKey]; pExceptionObject
0x18000b5c9  call    _CxxThrowException_0
```
