# RasGetAutodialEnableW

- ea: `0x18006ee00`
- end: `0x18006f11d`
- name: `RasGetAutodialEnableW`
- size: `797`
- prototype: `DWORD __stdcall(DWORD, LPBOOL)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18006ed90`

## callees

- `0x18000f31c`
- `0x180010d10`
- `0x18004e580`
- `0x18006ee00`
- `0x18007e3a8`
- `0x1800ded50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006ef87`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006efd6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006ef87`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006efd6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006f012`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006f0d3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006f0ed`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006f012`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006f0d3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006f0ed`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006f091`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006f091`

## pseudocode

```c
DWORD __stdcall RasGetAutodialEnableW(DWORD a1, LPBOOL a2)
{
  _QWORD *v4; // rcx
  unsigned int v6; // eax
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r9
  unsigned int v10; // eax
  unsigned int v11; // ebx
  HRESULT v12; // eax
  bool v13; // zf
  BYTE Data[4]; // [rsp+30h] [rbp-50h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-4Ch] BYREF
  DWORD Type; // [rsp+38h] [rbp-48h] BYREF
  int v17; // [rsp+3Ch] [rbp-44h]
  HKEY phkResult; // [rsp+40h] [rbp-40h] BYREF
  HKEY v19; // [rsp+48h] [rbp-38h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-30h] BYREF
  wchar_t pszDest[8]; // [rsp+58h] [rbp-28h] BYREF
  __int128 v22; // [rsp+68h] [rbp-18h]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 820, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, a1);
  }
  phkResult = 0;
  *(_OWORD *)pszDest = 0;
  v19 = 0;
  v22 = 0;
  hKey = 0;
  Type = 4;
  cbData = 0;
  *(_DWORD *)Data = 0;
  v17 = 0;
  DebugInit();
  if ( !a2 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 821, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, 87);
        v4 = WPP_GLOBAL_Control;
      }
      if ( v4 != &WPP_GLOBAL_Control && (*((_DWORD *)v4 + 7) & 0x800) != 0 && *((_BYTE *)v4 + 25) >= 6u )
        WPP_SF_d(v4[2], 822, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, 87);
    }
    return 87;
  }
  v6 = DwOpenUsersRegistry(&hKey);
  if ( v6 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_46;
    }
    v8 = 823;
    goto LABEL_20;
  }
  v6 = RegOpenKeyExW(hKey, L"Software\\Microsoft\\RAS AutoDial", 0, 0x20019u, &phkResult);
  if ( v6 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_46;
    }
    v8 = 824;
    goto LABEL_20;
  }
  v10 = RegOpenKeyExW(phkResult, L"Control\\Locations", 0, 0x20019u, &v19);
  v11 = v10;
  if ( v10
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 825, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v10);
  }
  RegCloseKey(phkResult);
  if ( v11 )
    goto LABEL_46;
  v12 = StringCchPrintfW(pszDest, 0x10u, L"%d", a1);
  if ( v12 < 0 )
  {
    v9 = (unsigned __int16)v12;
    if ( !(_WORD)v12 )
      goto LABEL_46;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_46;
    }
    v8 = 826;
    goto LABEL_21;
  }
  cbData = 4;
  v6 = RegQueryValueExW(v19, pszDest, 0, &Type, Data, &cbData);
  if ( !v6 )
  {
    if ( Type != 4 )
      *(_DWORD *)Data = 0;
    goto LABEL_46;
  }
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v8 = 827;
LABEL_20:
    v9 = v6;
LABEL_21:
    WPP_SF_d(v7[2], v8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v9);
  }
LABEL_46:
  if ( v19 )
    RegCloseKey(v19);
  v13 = v17 == 0;
  *a2 = Data[0] == 0;
  if ( !v13 )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x18006ee00  mov     [rsp-28h+arg_10], rbx
0x18006ee05  mov     [rsp-28h+arg_18], rsi
0x18006ee0a  push    rbp
0x18006ee0b  push    rdi
0x18006ee0c  push    r12
0x18006ee0e  push    r13
0x18006ee10  push    r15
0x18006ee12  mov     rbp, rsp
0x18006ee15  sub     rsp, 80h
0x18006ee1c  mov     rax, cs:__security_cookie
0x18006ee23  xor     rax, rsp
0x18006ee26  mov     [rbp+var_8], rax
0x18006ee2a  mov     rsi, rdx
0x18006ee2d  mov     edi, ecx
0x18006ee2f  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ee36  lea     r12, WPP_GLOBAL_Control
0x18006ee3d  lea     r13, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x18006ee44  mov     r15d, 800h
0x18006ee4a  cmp     rcx, r12
0x18006ee4d  jz      short loc_18006EE6F
0x18006ee4f  test    [rcx+1Ch], r15d
0x18006ee53  jz      short loc_18006EE6F
0x18006ee55  cmp     byte ptr [rcx+19h], 6
0x18006ee59  jb      short loc_18006EE6F
0x18006ee5b  mov     rcx, [rcx+10h]
0x18006ee5f  mov     edx, 334h
0x18006ee64  mov     r9d, edi
0x18006ee67  mov     r8, r13
0x18006ee6a  call    WPP_SF_d
0x18006ee6f  xorps   xmm0, xmm0
0x18006ee72  mov     [rbp+var_40], 0
0x18006ee7a  movups  xmmword ptr [rbp+pszDest], xmm0
0x18006ee7e  mov     [rbp+var_38], 0
0x18006ee86  movups  [rbp+var_18], xmm0
0x18006ee8a  mov     [rbp+hKey], 0
0x18006ee92  mov     [rbp+Type], 4
0x18006ee99  mov     [rbp+cbData], 0
0x18006eea0  mov     dword ptr [rbp+Data], 0
0x18006eea7  mov     [rbp+var_44], 0
0x18006eeae  call    DebugInit
0x18006eeb3  test    rsi, rsi
0x18006eeb6  jnz     short loc_18006EF1A
0x18006eeb8  mov     rcx, cs:WPP_GLOBAL_Control
0x18006eebf  lea     ebx, [rsi+57h]
0x18006eec2  cmp     rcx, r12
0x18006eec5  jz      short loc_18006EF13
0x18006eec7  test    [rcx+1Ch], r15d
0x18006eecb  jz      short loc_18006EEEE
0x18006eecd  cmp     byte ptr [rcx+19h], 2
0x18006eed1  jb      short loc_18006EEEE
0x18006eed3  mov     rcx, [rcx+10h]
0x18006eed7  mov     edx, 335h
0x18006eedc  mov     r9d, ebx
0x18006eedf  mov     r8, r13
0x18006eee2  call    WPP_SF_d
0x18006eee7  mov     rcx, cs:WPP_GLOBAL_Control
0x18006eeee  cmp     rcx, r12
0x18006eef1  jz      short loc_18006EF13
0x18006eef3  test    [rcx+1Ch], r15d
0x18006eef7  jz      short loc_18006EF13
0x18006eef9  cmp     byte ptr [rcx+19h], 6
0x18006eefd  jb      short loc_18006EF13
0x18006eeff  mov     rcx, [rcx+10h]
0x18006ef03  mov     edx, 336h
0x18006ef08  mov     r9d, ebx
0x18006ef0b  mov     r8, r13
0x18006ef0e  call    WPP_SF_d
0x18006ef13  mov     eax, ebx
0x18006ef15  jmp     loc_18006F0F5
0x18006ef1a  lea     rdx, [rbp+var_44]
0x18006ef1e  lea     rcx, [rbp+hKey]; phkResult
0x18006ef22  call    DwOpenUsersRegistry
0x18006ef27  test    eax, eax
0x18006ef29  jz      short loc_18006EF68
0x18006ef2b  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ef32  cmp     rcx, r12
0x18006ef35  jz      loc_18006F0CA
0x18006ef3b  test    [rcx+1Ch], r15d
0x18006ef3f  jz      loc_18006F0CA
0x18006ef45  cmp     byte ptr [rcx+19h], 2
0x18006ef49  jb      loc_18006F0CA
0x18006ef4f  mov     edx, 337h
0x18006ef54  mov     r9d, eax
0x18006ef57  mov     rcx, [rcx+10h]
0x18006ef5b  mov     r8, r13
0x18006ef5e  call    WPP_SF_d
0x18006ef63  jmp     loc_18006F0CA
0x18006ef68  mov     rcx, [rbp+hKey]; hKey
0x18006ef6c  lea     rax, [rbp+var_40]
0x18006ef70  mov     ebx, 20019h
0x18006ef75  mov     [rsp+80h+phkResult], rax; phkResult
0x18006ef7a  mov     r9d, ebx; samDesired
0x18006ef7d  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\RAS AutoDial"
0x18006ef84  xor     r8d, r8d; ulOptions
0x18006ef87  call    cs:__imp_RegOpenKeyExW
0x18006ef8d  test    eax, eax
0x18006ef8f  jz      short loc_18006EFBC
0x18006ef91  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ef98  cmp     rcx, r12
0x18006ef9b  jz      loc_18006F0CA
0x18006efa1  test    [rcx+1Ch], r15d
0x18006efa5  jz      loc_18006F0CA
0x18006efab  cmp     byte ptr [rcx+19h], 2
0x18006efaf  jb      loc_18006F0CA
0x18006efb5  mov     edx, 338h
0x18006efba  jmp     short loc_18006EF54
0x18006efbc  mov     rcx, [rbp+var_40]; hKey
0x18006efc0  lea     rax, [rbp+var_38]
0x18006efc4  mov     r9d, ebx; samDesired
0x18006efc7  mov     [rsp+80h+phkResult], rax; phkResult
0x18006efcc  xor     r8d, r8d; ulOptions
0x18006efcf  lea     rdx, aControlLocatio; "Control\\Locations"
0x18006efd6  call    cs:__imp_RegOpenKeyExW
0x18006efdc  mov     ebx, eax
0x18006efde  test    eax, eax
0x18006efe0  jz      short loc_18006F00E
0x18006efe2  mov     rcx, cs:WPP_GLOBAL_Control
0x18006efe9  cmp     rcx, r12
0x18006efec  jz      short loc_18006F00E
0x18006efee  test    [rcx+1Ch], r15d
0x18006eff2  jz      short loc_18006F00E
0x18006eff4  cmp     byte ptr [rcx+19h], 2
0x18006eff8  jb      short loc_18006F00E
0x18006effa  mov     rcx, [rcx+10h]
0x18006effe  mov     edx, 339h
0x18006f003  mov     r9d, eax
0x18006f006  mov     r8, r13
0x18006f009  call    WPP_SF_d
0x18006f00e  mov     rcx, [rbp+var_40]; hKey
0x18006f012  call    cs:__imp_RegCloseKey
0x18006f018  test    ebx, ebx
0x18006f01a  jnz     loc_18006F0CA
0x18006f020  mov     r9d, edi
0x18006f023  lea     r8, aD; "%d"
0x18006f02a  lea     edx, [rbx+10h]; cchDest
0x18006f02d  lea     rcx, [rbp+pszDest]; pszDest
0x18006f031  call    StringCchPrintfW
0x18006f036  test    eax, eax
0x18006f038  jns     short loc_18006F069
0x18006f03a  movzx   r9d, ax
0x18006f03e  test    r9d, r9d
0x18006f041  jz      loc_18006F0CA
0x18006f047  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f04e  cmp     rcx, r12
0x18006f051  jz      short loc_18006F0CA
0x18006f053  test    [rcx+1Ch], r15d
0x18006f057  jz      short loc_18006F0CA
0x18006f059  cmp     byte ptr [rcx+19h], 2
0x18006f05d  jb      short loc_18006F0CA
0x18006f05f  mov     edx, 33Ah
0x18006f064  jmp     loc_18006EF57
0x18006f069  mov     rcx, [rbp+var_38]; hKey
0x18006f06d  lea     rax, [rbp+cbData]
0x18006f071  mov     [rsp+80h+lpcbData], rax; lpcbData
0x18006f076  lea     r9, [rbp+Type]; lpType
0x18006f07a  lea     rax, [rbp+Data]
0x18006f07e  mov     [rbp+cbData], 4
0x18006f085  xor     r8d, r8d; lpReserved
0x18006f088  mov     [rsp+80h+phkResult], rax; lpData
0x18006f08d  lea     rdx, [rbp+pszDest]; lpValueName
0x18006f091  call    cs:__imp_RegQueryValueExW
0x18006f097  test    eax, eax
0x18006f099  jz      short loc_18006F0BD
0x18006f09b  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f0a2  cmp     rcx, r12
0x18006f0a5  jz      short loc_18006F0CA
0x18006f0a7  test    [rcx+1Ch], r15d
0x18006f0ab  jz      short loc_18006F0CA
0x18006f0ad  cmp     byte ptr [rcx+19h], 2
0x18006f0b1  jb      short loc_18006F0CA
0x18006f0b3  mov     edx, 33Bh
0x18006f0b8  jmp     loc_18006EF54
0x18006f0bd  cmp     [rbp+Type], 4
0x18006f0c1  jz      short loc_18006F0CA
0x18006f0c3  mov     dword ptr [rbp+Data], 0
0x18006f0ca  mov     rcx, [rbp+var_38]; hKey
0x18006f0ce  test    rcx, rcx
0x18006f0d1  jz      short loc_18006F0D9
0x18006f0d3  call    cs:__imp_RegCloseKey
0x18006f0d9  xor     eax, eax
0x18006f0db  cmp     [rbp+Data], al
0x18006f0de  setz    al
0x18006f0e1  cmp     [rbp+var_44], 0
0x18006f0e5  mov     [rsi], eax
0x18006f0e7  jz      short loc_18006F0F3
0x18006f0e9  mov     rcx, [rbp+hKey]; hKey
0x18006f0ed  call    cs:__imp_RegCloseKey
0x18006f0f3  xor     eax, eax
0x18006f0f5  mov     rcx, [rbp+var_8]
0x18006f0f9  xor     rcx, rsp; StackCookie
0x18006f0fc  call    __security_check_cookie
0x18006f101  lea     r11, [rsp+80h+var_s0]
0x18006f109  mov     rbx, [r11+40h]
0x18006f10d  mov     rsi, [r11+48h]
0x18006f111  mov     rsp, r11
0x18006f114  pop     r15
0x18006f116  pop     r13
0x18006f118  pop     r12
0x18006f11a  pop     rdi
0x18006f11b  pop     rbp
0x18006f11c  retn
```
