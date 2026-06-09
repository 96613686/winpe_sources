# SavedCredsFeatureEnabledForUsernamePassword(void)

- ea: `0x180064bb0`
- end: `0x180064cab`
- name: `?SavedCredsFeatureEnabledForUsernamePassword@@YAHXZ`
- size: `251`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x180065294`

## callees

- `0x180004bd0`
- `0x180064bb0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180064c9c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180064c9c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180064bed`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180064bed`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180064c3a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180064c3a`

## string_xrefs

- `0x180064bda`: `SYSTEM\CurrentControlSet\Services\Eaphost\Configuration`

## pseudocode

```c
__int64 SavedCredsFeatureEnabledForUsernamePassword(void)
{
  unsigned int v0; // ebx
  unsigned int v1; // eax
  __int64 v2; // r9
  struct _EAPTLS_CONTROL_BLOCK *v3; // rcx
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
    if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
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
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      v4 = 11;
LABEL_13:
      WPP_SF_d(*((_QWORD *)v3 + 2), v4, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids, v2);
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
0x180064bb0  push    rbp
0x180064bb2  push    rbx
0x180064bb3  mov     rbp, rsp
0x180064bb6  sub     rsp, 38h
0x180064bba  xor     ebx, ebx
0x180064bbc  mov     [rbp+cbData], 4
0x180064bc3  lea     rax, [rbp+hKey]
0x180064bc7  mov     [rbp+hKey], rbx
0x180064bcb  mov     r9d, 20019h; samDesired
0x180064bd1  mov     [rbp+Type], ebx
0x180064bd4  xor     r8d, r8d; ulOptions
0x180064bd7  mov     [rbp+Data], ebx
0x180064bda  lea     rdx, aSystemCurrentc_7; "SYSTEM\\CurrentControlSet\\Services\\Ea"...
0x180064be1  mov     [rsp+38h+phkResult], rax; phkResult
0x180064be6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180064bed  call    cs:__imp_RegOpenKeyExW
0x180064bf3  mov     r9d, eax
0x180064bf6  test    eax, eax
0x180064bf8  jz      short loc_180064C16
0x180064bfa  mov     rcx, cs:WPP_GLOBAL_Control
0x180064c01  lea     rax, WPP_GLOBAL_Control
0x180064c08  cmp     rcx, rax
0x180064c0b  jz      loc_180064C93
0x180064c11  lea     edx, [rbx+0Ah]
0x180064c14  jmp     short loc_180064C83
0x180064c16  mov     rcx, [rbp+hKey]; hKey
0x180064c1a  lea     rax, [rbp+cbData]
0x180064c1e  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180064c23  lea     r9, [rbp+Type]; lpType
0x180064c27  lea     rax, [rbp+Data]
0x180064c2b  xor     r8d, r8d; lpReserved
0x180064c2e  lea     rdx, aDisableusrpwds; "DisableUsrPwdStoring"
0x180064c35  mov     [rsp+38h+phkResult], rax; lpData
0x180064c3a  call    cs:__imp_RegQueryValueExW
0x180064c40  mov     r9d, eax
0x180064c43  test    eax, eax
0x180064c45  jnz     short loc_180064C5F
0x180064c47  cmp     [rbp+Type], 4
0x180064c4b  jnz     short loc_180064C5B
0x180064c4d  cmp     [rbp+cbData], 4
0x180064c51  jnz     short loc_180064C5B
0x180064c53  lea     ebx, [rax+1]
0x180064c56  cmp     [rbp+Data], ebx
0x180064c59  jnz     short loc_180064C93
0x180064c5b  xor     ebx, ebx
0x180064c5d  jmp     short loc_180064C93
0x180064c5f  cmp     r9d, 2
0x180064c63  jnz     short loc_180064C6B
0x180064c65  lea     ebx, [r9-1]
0x180064c69  jmp     short loc_180064C93
0x180064c6b  mov     rcx, cs:WPP_GLOBAL_Control
0x180064c72  lea     rax, WPP_GLOBAL_Control
0x180064c79  cmp     rcx, rax
0x180064c7c  jz      short loc_180064C93
0x180064c7e  mov     edx, 0Bh
0x180064c83  mov     rcx, [rcx+10h]
0x180064c87  lea     r8, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids
0x180064c8e  call    WPP_SF_d
0x180064c93  mov     rcx, [rbp+hKey]; hKey
0x180064c97  test    rcx, rcx
0x180064c9a  jz      short loc_180064CA2
0x180064c9c  call    cs:__imp_RegCloseKey
0x180064ca2  mov     eax, ebx
0x180064ca4  add     rsp, 38h
0x180064ca8  pop     rbx
0x180064ca9  pop     rbp
0x180064caa  retn
```
