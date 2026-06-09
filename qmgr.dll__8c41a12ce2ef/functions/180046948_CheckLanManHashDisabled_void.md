# CheckLanManHashDisabled(void)

- ea: `0x180046948`
- end: `0x180046b87`
- name: `?CheckLanManHashDisabled@@YAJXZ`
- size: `575`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180045ea0`

## callees

- `0x180014374`
- `0x180045d90`
- `0x180046948`
- `0x18009d024`
- `0x18009e9c8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180046b07`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180046b32`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180046b07`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180046b32`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180046aa0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180046aa0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800469d2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180046af1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800469d2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180046af1`

## string_xrefs

- `0x180046995`: `UseLmCompat`
- `0x1800469c3`: `UseLmCompat`
- `0x180046aea`: `lmcompatibilitylevel`

## pseudocode

```c
LSTATUS CheckLanManHashDisabled(void)
{
  __int64 v0; // rcx
  HKEY RegistryKey; // rbx
  LSTATUS v2; // ebx
  EVENT_LOG *v3; // rcx
  __int64 v4; // rdx
  LSTATUS result; // eax
  bool v6; // cc
  DWORD cbData; // [rsp+50h] [rbp+18h] BYREF
  DWORD Type; // [rsp+58h] [rbp+20h] BYREF
  unsigned int Data; // [rsp+60h] [rbp+28h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp+30h] BYREF

  phkResult = 0;
  cbData = 0;
  Type = 0;
  v0 = *((_QWORD *)g_GlobalInfo + 2);
  Data = 0;
  g_bLanManHashDisabled = 0;
  RegistryKey = (HKEY)RegistryKeyManager::GetRegistryKey(v0, 1);
  RegistryKeyManager::PropagateVolatileSettingsRegistryValue(*((RegistryKeyManager **)g_GlobalInfo + 2), L"UseLmCompat");
  cbData = 4;
  v2 = RegQueryValueExW(RegistryKey, L"UseLmCompat", 0, &Type, (LPBYTE)&Data, &cbData);
  if ( v2 )
  {
    if ( v2 != 2 )
    {
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          128,
          &WPP_f564cdc5d2433e52f9a3270eb457e218_Traceguids,
          (unsigned int)v2);
      v6 = v2 <= 0;
      goto LABEL_33;
    }
  }
  else if ( Type == 4 && cbData == 4 )
  {
    if ( !Data )
    {
      g_bLanManHashDisabled = 1;
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (EVENT_LOG *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return 0;
      v4 = 126;
      goto LABEL_12;
    }
    if ( Data == 2 )
    {
      g_bLanManHashDisabled = 0;
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (EVENT_LOG *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return 0;
      v4 = 127;
LABEL_12:
      WPP_SF_(*((_QWORD *)v3 + 2), v4, &WPP_f564cdc5d2433e52f9a3270eb457e218_Traceguids);
      return 0;
    }
  }
  result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\Currentcontrolset\\Control\\Lsa", 0, 0x20019u, &phkResult);
  if ( result == 2 )
    return 0;
  if ( result )
  {
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  cbData = 4;
  v2 = RegQueryValueExW(phkResult, L"lmcompatibilitylevel", 0, &Type, (LPBYTE)&Data, &cbData);
  if ( v2 == 2 )
  {
    if ( phkResult )
      RegCloseKey(phkResult);
    return 0;
  }
  if ( !v2 && Type == 4 && Data >= 2 )
    g_bLanManHashDisabled = 1;
  if ( phkResult )
    RegCloseKey(phkResult);
  v6 = v2 <= 0;
  if ( !v2 )
    return 0;
LABEL_33:
  if ( !v6 )
    return (unsigned __int16)v2 | 0x80070000;
  return v2;
}

```

## disassembly

```asm
0x180046948  push    rbp
0x18004694a  push    rbx
0x18004694b  mov     rbp, rsp
0x18004694e  sub     rsp, 38h
0x180046952  mov     rcx, cs:?g_GlobalInfo@@3PEAVGlobalInfo@@EA; GlobalInfo * g_GlobalInfo
0x180046959  mov     edx, 1
0x18004695e  mov     [rbp+phkResult], 0
0x180046966  mov     [rbp+cbData], 0
0x18004696d  mov     [rbp+Type], 0
0x180046974  mov     rcx, [rcx+10h]
0x180046978  mov     [rbp+Data], 0
0x18004697f  mov     cs:?g_bLanManHashDisabled@@3HA, 0; int g_bLanManHashDisabled
0x180046989  call    ?GetRegistryKey@RegistryKeyManager@@QEAAPEAUHKEY__@@W4RegistryKeyType@@@Z; RegistryKeyManager::GetRegistryKey(RegistryKeyType)
0x18004698e  mov     rcx, cs:?g_GlobalInfo@@3PEAVGlobalInfo@@EA; GlobalInfo * g_GlobalInfo
0x180046995  lea     rdx, aUselmcompat; "UseLmCompat"
0x18004699c  mov     rbx, rax
0x18004699f  mov     rcx, [rcx+10h]; this
0x1800469a3  call    ?PropagateVolatileSettingsRegistryValue@RegistryKeyManager@@QEAAJPEBG@Z; RegistryKeyManager::PropagateVolatileSettingsRegistryValue(ushort const *)
0x1800469a8  lea     rax, [rbp+cbData]
0x1800469ac  mov     [rbp+cbData], 4
0x1800469b3  mov     [rsp+38h+lpcbData], rax; lpcbData
0x1800469b8  lea     r9, [rbp+Type]; lpType
0x1800469bc  lea     rax, [rbp+Data]
0x1800469c0  xor     r8d, r8d; lpReserved
0x1800469c3  lea     rdx, aUselmcompat; "UseLmCompat"
0x1800469ca  mov     [rsp+38h+lpData], rax; lpData
0x1800469cf  mov     rcx, rbx; hKey
0x1800469d2  call    cs:__imp_RegQueryValueExW
0x1800469d8  mov     ebx, eax
0x1800469da  test    eax, eax
0x1800469dc  jnz     loc_180046A77
0x1800469e2  cmp     [rbp+Type], 4
0x1800469e6  jnz     loc_180046A80
0x1800469ec  cmp     [rbp+cbData], 4
0x1800469f0  jnz     loc_180046A80
0x1800469f6  mov     eax, [rbp+Data]
0x1800469f9  test    eax, eax
0x1800469fb  jnz     short loc_180046A2D
0x1800469fd  mov     cs:?g_bLanManHashDisabled@@3HA, 1; int g_bLanManHashDisabled
0x180046a07  mov     rcx, cs:WPP_GLOBAL_Control
0x180046a0e  lea     rax, WPP_GLOBAL_Control
0x180046a15  cmp     rcx, rax
0x180046a18  jz      loc_180046B3C
0x180046a1e  test    byte ptr [rcx+1Ch], 1
0x180046a22  jz      loc_180046B3C
0x180046a28  lea     edx, [rbx+7Eh]
0x180046a2b  jmp     short loc_180046A62
0x180046a2d  cmp     eax, 2
0x180046a30  jnz     short loc_180046A80
0x180046a32  mov     cs:?g_bLanManHashDisabled@@3HA, 0; int g_bLanManHashDisabled
0x180046a3c  mov     rcx, cs:WPP_GLOBAL_Control
0x180046a43  lea     rax, WPP_GLOBAL_Control
0x180046a4a  cmp     rcx, rax
0x180046a4d  jz      loc_180046B3C
0x180046a53  test    byte ptr [rcx+1Ch], 1
0x180046a57  jz      loc_180046B3C
0x180046a5d  mov     edx, 7Fh
0x180046a62  mov     rcx, [rcx+10h]
0x180046a66  lea     r8, WPP_f564cdc5d2433e52f9a3270eb457e218_Traceguids
0x180046a6d  call    WPP_SF_
0x180046a72  jmp     loc_180046B3C
0x180046a77  cmp     ebx, 2
0x180046a7a  jnz     loc_180046B40
0x180046a80  lea     rax, [rbp+phkResult]
0x180046a84  mov     r9d, 20019h; samDesired
0x180046a8a  xor     r8d, r8d; ulOptions
0x180046a8d  mov     [rsp+38h+lpData], rax; phkResult
0x180046a92  lea     rdx, SubKey; "System\\Currentcontrolset\\Control\\Lsa"
0x180046a99  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180046aa0  call    cs:__imp_RegOpenKeyExW
0x180046aa6  cmp     eax, 2
0x180046aa9  jz      loc_180046B3C
0x180046aaf  test    eax, eax
0x180046ab1  jz      short loc_180046AC6
0x180046ab3  jle     loc_180046B80
0x180046ab9  movzx   eax, ax
0x180046abc  or      eax, 80070000h
0x180046ac1  jmp     loc_180046B80
0x180046ac6  mov     rcx, [rbp+phkResult]; hKey
0x180046aca  lea     rax, [rbp+cbData]
0x180046ace  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180046ad3  lea     r9, [rbp+Type]; lpType
0x180046ad7  lea     rax, [rbp+Data]
0x180046adb  mov     [rbp+cbData], 4
0x180046ae2  xor     r8d, r8d; lpReserved
0x180046ae5  mov     [rsp+38h+lpData], rax; lpData
0x180046aea  lea     rdx, aLmcompatibilit; "lmcompatibilitylevel"
0x180046af1  call    cs:__imp_RegQueryValueExW
0x180046af7  mov     ebx, eax
0x180046af9  cmp     eax, 2
0x180046afc  jnz     short loc_180046B0F
0x180046afe  mov     rcx, [rbp+phkResult]; hKey
0x180046b02  test    rcx, rcx
0x180046b05  jz      short loc_180046B3C
0x180046b07  call    cs:__imp_RegCloseKey
0x180046b0d  jmp     short loc_180046B3C
0x180046b0f  test    ebx, ebx
0x180046b11  jnz     short loc_180046B29
0x180046b13  cmp     [rbp+Type], 4
0x180046b17  jnz     short loc_180046B29
0x180046b19  cmp     [rbp+Data], 2
0x180046b1d  jb      short loc_180046B29
0x180046b1f  mov     cs:?g_bLanManHashDisabled@@3HA, 1; int g_bLanManHashDisabled
0x180046b29  mov     rcx, [rbp+phkResult]; hKey
0x180046b2d  test    rcx, rcx
0x180046b30  jz      short loc_180046B38
0x180046b32  call    cs:__imp_RegCloseKey
0x180046b38  test    ebx, ebx
0x180046b3a  jnz     short loc_180046B73
0x180046b3c  xor     eax, eax
0x180046b3e  jmp     short loc_180046B80
0x180046b40  mov     rcx, cs:WPP_GLOBAL_Control
0x180046b47  lea     rax, WPP_GLOBAL_Control
0x180046b4e  cmp     rcx, rax
0x180046b51  jz      short loc_180046B71
0x180046b53  test    byte ptr [rcx+1Ch], 1
0x180046b57  jz      short loc_180046B71
0x180046b59  mov     rcx, [rcx+10h]
0x180046b5d  lea     r8, WPP_f564cdc5d2433e52f9a3270eb457e218_Traceguids
0x180046b64  mov     edx, 80h
0x180046b69  mov     r9d, ebx
0x180046b6c  call    WPP_SF_d
0x180046b71  test    ebx, ebx
0x180046b73  jle     short loc_180046B7E
0x180046b75  movzx   ebx, bx
0x180046b78  or      ebx, 80070000h
0x180046b7e  mov     eax, ebx
0x180046b80  add     rsp, 38h
0x180046b84  pop     rbx
0x180046b85  pop     rbp
0x180046b86  retn
```
