# SavedCredsFeatureEnabledForUsernamePassword(void)

- ea: `0x18000ef70`
- end: `0x18000f06b`
- name: `?SavedCredsFeatureEnabledForUsernamePassword@@YAHXZ`
- size: `251`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x180006c60`

## callees

- `0x180003bd0`
- `0x18000ef70`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000effa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000effa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000efad`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000efad`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f05c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f05c`

## string_xrefs

- `0x18000ef9a`: `SYSTEM\CurrentControlSet\Services\Eaphost\Configuration`

## pseudocode

```c
__int64 SavedCredsFeatureEnabledForUsernamePassword(void)
{
  unsigned int v0; // ebx
  unsigned int v1; // eax
  __int64 v2; // r9
  _QWORD *v3; // rcx
  __int64 v4; // rdx
  unsigned int v5; // eax
  DWORD Type; // [rsp+50h] [rbp+18h] BYREF
  DWORD cbData; // [rsp+58h] [rbp+20h] BYREF
  int Data; // [rsp+60h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+30h] BYREF

  v0 = 0;
  cbData = 4;
  hKey = 0;
  Type = 0;
  Data = 0;
  v1 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Services\\Eaphost\\Configuration",
         0,
         0x20019u,
         &hKey);
  v2 = v1;
  if ( v1 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_14;
    v4 = 10;
    goto LABEL_13;
  }
  v5 = RegQueryValueExW(hKey, L"DisableUsrPwdStoring", 0, &Type, (LPBYTE)&Data, &cbData);
  v2 = v5;
  if ( v5 )
  {
    if ( v5 == 2 )
    {
      v0 = 1;
      goto LABEL_14;
    }
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      v4 = 11;
LABEL_13:
      WPP_SF_d(v3[2], v4, &WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids, v2);
    }
  }
  else if ( Type != 4 || cbData != 4 || (v0 = 1, Data == 1) )
  {
    v0 = 0;
  }
LABEL_14:
  if ( hKey )
    RegCloseKey(hKey);
  return v0;
}

```

## disassembly

```asm
0x18000ef70  push    rbp
0x18000ef72  push    rbx
0x18000ef73  mov     rbp, rsp
0x18000ef76  sub     rsp, 38h
0x18000ef7a  xor     ebx, ebx
0x18000ef7c  mov     [rbp+cbData], 4
0x18000ef83  lea     rax, [rbp+hKey]
0x18000ef87  mov     [rbp+hKey], rbx
0x18000ef8b  mov     r9d, 20019h; samDesired
0x18000ef91  mov     [rbp+Type], ebx
0x18000ef94  xor     r8d, r8d; ulOptions
0x18000ef97  mov     [rbp+Data], ebx
0x18000ef9a  lea     rdx, aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Services\\Ea"...
0x18000efa1  mov     [rsp+38h+phkResult], rax; phkResult
0x18000efa6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000efad  call    cs:__imp_RegOpenKeyExW
0x18000efb3  mov     r9d, eax
0x18000efb6  test    eax, eax
0x18000efb8  jz      short loc_18000EFD6
0x18000efba  mov     rcx, cs:WPP_GLOBAL_Control
0x18000efc1  lea     rax, WPP_GLOBAL_Control
0x18000efc8  cmp     rcx, rax
0x18000efcb  jz      loc_18000F053
0x18000efd1  lea     edx, [rbx+0Ah]
0x18000efd4  jmp     short loc_18000F043
0x18000efd6  mov     rcx, [rbp+hKey]; hKey
0x18000efda  lea     rax, [rbp+cbData]
0x18000efde  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18000efe3  lea     r9, [rbp+Type]; lpType
0x18000efe7  lea     rax, [rbp+Data]
0x18000efeb  xor     r8d, r8d; lpReserved
0x18000efee  lea     rdx, aDisableusrpwds; "DisableUsrPwdStoring"
0x18000eff5  mov     [rsp+38h+phkResult], rax; lpData
0x18000effa  call    cs:__imp_RegQueryValueExW
0x18000f000  mov     r9d, eax
0x18000f003  test    eax, eax
0x18000f005  jnz     short loc_18000F01F
0x18000f007  cmp     [rbp+Type], 4
0x18000f00b  jnz     short loc_18000F01B
0x18000f00d  cmp     [rbp+cbData], 4
0x18000f011  jnz     short loc_18000F01B
0x18000f013  lea     ebx, [rax+1]
0x18000f016  cmp     [rbp+Data], ebx
0x18000f019  jnz     short loc_18000F053
0x18000f01b  xor     ebx, ebx
0x18000f01d  jmp     short loc_18000F053
0x18000f01f  cmp     r9d, 2
0x18000f023  jnz     short loc_18000F02B
0x18000f025  lea     ebx, [r9-1]
0x18000f029  jmp     short loc_18000F053
0x18000f02b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f032  lea     rax, WPP_GLOBAL_Control
0x18000f039  cmp     rcx, rax
0x18000f03c  jz      short loc_18000F053
0x18000f03e  mov     edx, 0Bh
0x18000f043  mov     rcx, [rcx+10h]
0x18000f047  lea     r8, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids
0x18000f04e  call    WPP_SF_d
0x18000f053  mov     rcx, [rbp+hKey]; hKey
0x18000f057  test    rcx, rcx
0x18000f05a  jz      short loc_18000F062
0x18000f05c  call    cs:__imp_RegCloseKey
0x18000f062  mov     eax, ebx
0x18000f064  add     rsp, 38h
0x18000f068  pop     rbx
0x18000f069  pop     rbp
0x18000f06a  retn
```
