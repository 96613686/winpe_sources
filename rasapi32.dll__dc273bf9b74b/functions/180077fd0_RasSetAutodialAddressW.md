# RasSetAutodialAddressW

- ea: `0x180077fd0`
- end: `0x1800789ea`
- name: `RasSetAutodialAddressW`
- size: `2586`
- prototype: `DWORD __stdcall(LPCWSTR, DWORD, struct tagRASAUTODIALENTRYW *, DWORD, DWORD)`
- caller_count: `2`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180077c10`
- `0x180097c80`

## callees

- `0x18000f2bc`
- `0x18000f31c`
- `0x180010d10`
- `0x180016120`
- `0x18004e580`
- `0x18004e984`
- `0x180065dbc`
- `0x1800661c4`
- `0x1800664d8`
- `0x18006a074`
- `0x18006bd14`
- `0x18006bf8c`
- `0x180077fd0`
- `0x18007e5f0`
- `0x1800d09c0`
- `0x1800ded06`
- `0x1800ded50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180078584`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180078584`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180078325`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18007840f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180078325`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18007840f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180078386`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180078386`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180078635`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180078645`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007866e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180078635`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180078645`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007866e`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18007864e`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18007865e`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18007864e`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18007865e`

## pseudocode

```c
DWORD __stdcall RasSetAutodialAddressW(LPCWSTR a1, DWORD a2, struct tagRASAUTODIALENTRYW *a3, DWORD a4, DWORD a5)
{
  BYTE *v9; // r12
  _DWORD *v10; // rcx
  __int64 v11; // rdx
  _DWORD *v12; // rcx
  DWORD v13; // edi
  __int64 v14; // rdx
  unsigned int v15; // edi
  DWORD v16; // eax
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  WCHAR *v19; // rsi
  unsigned int v20; // eax
  __int64 v21; // r9
  DWORD v22; // eax
  DWORD v23; // eax
  __int64 v24; // rax
  DWORD i; // r14d
  DWORD EntryTypeAndPbkType; // eax
  unsigned int v28; // r14d
  DWORD v29; // eax
  unsigned int v30; // eax
  LPCWSTR lpSubKey; // [rsp+50h] [rbp-B0h] BYREF
  int v32; // [rsp+58h] [rbp-A8h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-A0h] BYREF
  BYTE *lpData; // [rsp+68h] [rbp-98h] BYREF
  DWORD dwDisposition; // [rsp+70h] [rbp-90h] BYREF
  HKEY v36; // [rsp+78h] [rbp-88h] BYREF
  HKEY hKey; // [rsp+80h] [rbp-80h] BYREF
  int v38; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v39[524]; // [rsp+94h] [rbp-6Ch] BYREF

  if ( a1 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 742, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, a1);
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 743, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids);
  }
  phkResult = 0;
  v9 = 0;
  v36 = 0;
  hKey = 0;
  v32 = 0;
  dwDisposition = 0;
  lpData = 0;
  DebugInit();
  if ( a2 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return 87;
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 744, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, 87);
      v10 = WPP_GLOBAL_Control;
    }
    if ( v10 == (_DWORD *)&WPP_GLOBAL_Control || (v10[7] & 0x800) == 0 || *((_BYTE *)v10 + 25) < 6u )
      return 87;
    v11 = 745;
LABEL_130:
    WPP_SF_d(*((_QWORD *)v10 + 2), v11, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, 87);
    return 87;
  }
  if ( a3 && (a4 < 4 || a3->dwSize != 528) )
  {
    v12 = WPP_GLOBAL_Control;
    v13 = 632;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v13;
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 746, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, 632);
      v12 = WPP_GLOBAL_Control;
    }
    if ( v12 == (_DWORD *)&WPP_GLOBAL_Control || (v12[7] & 0x800) == 0 || *((_BYTE *)v12 + 25) < 6u )
      return v13;
    v14 = 747;
    goto LABEL_183;
  }
  v15 = 0;
  if ( (a4 == 0) != (a5 == 0) )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return 87;
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 748, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, 87);
      v10 = WPP_GLOBAL_Control;
    }
    if ( v10 == (_DWORD *)&WPP_GLOBAL_Control || (v10[7] & 0x800) == 0 || *((_BYTE *)v10 + 25) < 6u )
      return 87;
    v11 = 749;
    goto LABEL_130;
  }
  if ( a1 && *a1 )
  {
    lpSubKey = (LPCWSTR)FormatKey(L"Addresses", a1);
    if ( !lpSubKey )
    {
      v12 = WPP_GLOBAL_Control;
      v13 = 8;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v13;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 761, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, 8);
        v12 = WPP_GLOBAL_Control;
      }
      if ( v12 == (_DWORD *)&WPP_GLOBAL_Control || (v12[7] & 0x800) == 0 || *((_BYTE *)v12 + 25) < 6u )
        return v13;
      v14 = 762;
      goto LABEL_183;
    }
    v16 = DwOpenUsersRegistry(&hKey);
    v13 = v16;
    if ( v16 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_110;
      }
      v18 = 763;
      goto LABEL_108;
    }
    v16 = RegCreateKeyExW(hKey, L"Software\\Microsoft\\RAS AutoDial", 0, 0, 0, 0x2001Fu, 0, &phkResult, &dwDisposition);
    v13 = v16;
    if ( v16 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_110;
      }
      v18 = 764;
      goto LABEL_108;
    }
    if ( !a3 && !a4 && !a5 )
    {
      v19 = (WCHAR *)lpSubKey;
      v20 = RegDeleteKeyExW(phkResult, lpSubKey, 0, 0);
      v13 = v20;
      if ( v20
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 765, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v20);
      }
      goto LABEL_111;
    }
    v16 = RegCreateKeyExW(phkResult, lpSubKey, 0, 0, 0, 2u, 0, &v36, &dwDisposition);
    v13 = v16;
    if ( v16 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_110;
      }
      v18 = 766;
      goto LABEL_108;
    }
    if ( a3 && (!a4 || !a5 || a4 < a3->dwSize * a5) )
    {
      v13 = 87;
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_110;
      }
      v18 = 767;
      v21 = 87;
      goto LABEL_109;
    }
    v22 = AutodialAddressToNetwork(phkResult, (__int64)a1, &lpData);
    v13 = v22;
    if ( v22 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 768, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v22);
      }
      v23 = AutodialEntryToNetwork(phkResult, a3->szEntry, 1, &lpData);
      v13 = v23;
      if ( v23 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 769, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v23);
        }
        v9 = lpData;
        goto LABEL_110;
      }
      v9 = lpData;
      v24 = -1;
      do
        ++v24;
      while ( *(_WORD *)&lpData[2 * v24] );
      v16 = RegSetValueExW(v36, L"Network", 0, 1u, lpData, 2 * v24 + 2);
      v13 = v16;
      if ( v16 )
      {
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_110;
        }
        v18 = 770;
LABEL_108:
        v21 = v16;
LABEL_109:
        WPP_SF_d(v17[2], v18, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v21);
LABEL_110:
        v19 = (WCHAR *)lpSubKey;
LABEL_111:
        if ( phkResult )
          RegCloseKey(phkResult);
        if ( v36 )
          RegCloseKey(v36);
        GlobalFree(v19);
        if ( v9 )
          GlobalFree(v9);
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 6u )
        {
          return v13;
        }
        v14 = 772;
        goto LABEL_183;
      }
    }
    else
    {
      v9 = lpData;
    }
    for ( i = 0; i < a5; ++i )
    {
      v16 = AddAutodialEntryToNetwork(phkResult, v9, a3[i].dwDialingLocation, (const BYTE *)a3[i].szEntry);
      v13 = v16;
      if ( v16 )
      {
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v18 = 771;
          goto LABEL_108;
        }
        goto LABEL_110;
      }
    }
    goto LABEL_110;
  }
  if ( a5 != 1 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return 87;
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 750, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, 87);
      v10 = WPP_GLOBAL_Control;
    }
    if ( v10 == (_DWORD *)&WPP_GLOBAL_Control || (v10[7] & 0x800) == 0 || *((_BYTE *)v10 + 25) < 6u )
      return 87;
    v11 = 751;
    goto LABEL_130;
  }
  memset_0(v39, 0, sizeof(v39));
  v38 = 528;
  if ( (!a1 || *a1) && a3 && a3->szEntry[0] )
  {
    v32 = 0;
    LODWORD(lpSubKey) = 0;
    EntryTypeAndPbkType = GetEntryTypeAndPbkType(a3->szEntry, &v32, &lpSubKey);
    v13 = EntryTypeAndPbkType;
    if ( EntryTypeAndPbkType )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v13;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          752,
          WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids,
          EntryTypeAndPbkType);
        v12 = WPP_GLOBAL_Control;
      }
      if ( v12 == (_DWORD *)&WPP_GLOBAL_Control || (v12[7] & 0x800) == 0 || *((_BYTE *)v12 + 25) < 6u )
        return v13;
      v14 = 753;
      goto LABEL_183;
    }
    if ( v32 == 2 )
    {
      v12 = WPP_GLOBAL_Control;
      v13 = 50;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v13;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 754, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, 50);
        v12 = WPP_GLOBAL_Control;
      }
      if ( v12 == (_DWORD *)&WPP_GLOBAL_Control || (v12[7] & 0x800) == 0 || *((_BYTE *)v12 + 25) < 6u )
        return v13;
      v14 = 755;
      goto LABEL_183;
    }
    v28 = 0;
    if ( (_DWORD)lpSubKey )
    {
      v15 = 0;
    }
    else
    {
      v15 = 1;
      if ( !(unsigned int)FIsUserAdmin() && (unsigned int)IsConsumerPlatform() )
      {
        v12 = WPP_GLOBAL_Control;
        v13 = 5;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          return v13;
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 756, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, 5);
          v12 = WPP_GLOBAL_Control;
        }
        if ( v12 == (_DWORD *)&WPP_GLOBAL_Control || (v12[7] & 0x800) == 0 || *((_BYTE *)v12 + 25) < 6u )
          return v13;
        v14 = 757;
LABEL_183:
        WPP_SF_d(*((_QWORD *)v12 + 2), v14, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v13);
        return v13;
      }
    }
  }
  else
  {
    v28 = 1;
  }
  v29 = RasDefIntConnSet(a3, &v38, v28, v15);
  v13 = v29;
  if ( !v29 )
  {
    v30 = RasDefIntConnNotify(a3, &v38, v28);
    if ( v30 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_178;
      }
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 759, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v30);
    }
    v12 = WPP_GLOBAL_Control;
LABEL_178:
    v13 = 0;
LABEL_179:
    if ( v12 == (_DWORD *)&WPP_GLOBAL_Control || (v12[7] & 0x800) == 0 || *((_BYTE *)v12 + 25) < 6u )
      return v13;
    v14 = 760;
    goto LABEL_183;
  }
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 758, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v29);
      v12 = WPP_GLOBAL_Control;
    }
    goto LABEL_179;
  }
  return v13;
}

```

## disassembly

```asm
0x180077fd0  mov     [rsp-8+arg_8], rbx
0x180077fd5  push    rbp
0x180077fd6  push    rsi
0x180077fd7  push    rdi
0x180077fd8  push    r12
0x180077fda  push    r13
0x180077fdc  push    r14
0x180077fde  push    r15
0x180077fe0  lea     rbp, [rsp-1B0h]
0x180077fe8  sub     rsp, 2B0h
0x180077fef  mov     rax, cs:__security_cookie
0x180077ff6  xor     rax, rsp
0x180077ff9  mov     [rbp+1E0h+var_40], rax
0x180078000  xor     r13d, r13d
0x180078003  mov     r15d, r9d
0x180078006  mov     rsi, r8
0x180078009  mov     edi, edx
0x18007800b  mov     r14, rcx
0x18007800e  mov     eax, 800h
0x180078013  test    rcx, rcx
0x180078016  jz      short loc_180078050
0x180078018  mov     rcx, cs:WPP_GLOBAL_Control
0x18007801f  lea     rbx, WPP_GLOBAL_Control
0x180078026  cmp     rcx, rbx
0x180078029  jz      short loc_180078083
0x18007802b  test    [rcx+1Ch], eax
0x18007802e  jz      short loc_180078083
0x180078030  cmp     byte ptr [rcx+19h], 6
0x180078034  jb      short loc_180078083
0x180078036  mov     rcx, [rcx+10h]
0x18007803a  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x180078041  mov     edx, 2E6h
0x180078046  mov     r9, r14
0x180078049  call    WPP_SF_S
0x18007804e  jmp     short loc_180078083
0x180078050  mov     rcx, cs:WPP_GLOBAL_Control
0x180078057  lea     rbx, WPP_GLOBAL_Control
0x18007805e  cmp     rcx, rbx
0x180078061  jz      short loc_180078083
0x180078063  test    [rcx+1Ch], eax
0x180078066  jz      short loc_180078083
0x180078068  cmp     byte ptr [rcx+19h], 6
0x18007806c  jb      short loc_180078083
0x18007806e  mov     rcx, [rcx+10h]
0x180078072  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x180078079  mov     edx, 2E7h
0x18007807e  call    WPP_SF_
0x180078083  mov     [rsp+2E0h+var_280], r13
0x180078088  mov     r12, r13
0x18007808b  mov     [rsp+2E0h+var_268], r13
0x180078090  mov     [rbp+1E0h+hKey], r13
0x180078094  mov     [rsp+2E0h+var_288], r13d
0x180078099  mov     [rsp+2E0h+dwDisposition], r13d
0x18007809e  mov     [rsp+2E0h+lpData], r13
0x1800780a3  call    DebugInit
0x1800780a8  test    edi, edi
0x1800780aa  jz      short loc_180078114
0x1800780ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800780b3  cmp     rcx, rbx
0x1800780b6  jz      loc_180078717
0x1800780bc  mov     esi, 800h
0x1800780c1  test    [rcx+1Ch], esi
0x1800780c4  jz      short loc_1800780EE
0x1800780c6  cmp     byte ptr [rcx+19h], 2
0x1800780ca  jb      short loc_1800780EE
0x1800780cc  mov     rcx, [rcx+10h]
0x1800780d0  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x1800780d7  mov     edx, 2E8h
0x1800780dc  mov     r9d, 57h ; 'W'
0x1800780e2  call    WPP_SF_d
0x1800780e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800780ee  cmp     rcx, rbx
0x1800780f1  jz      loc_180078717
0x1800780f7  test    [rcx+1Ch], esi
0x1800780fa  jz      loc_180078717
0x180078100  cmp     byte ptr [rcx+19h], 6
0x180078104  jb      loc_180078717
0x18007810a  mov     edx, 2E9h
0x18007810f  jmp     loc_180078701
0x180078114  test    rsi, rsi
0x180078117  jz      short loc_18007818F
0x180078119  cmp     r15d, 4
0x18007811d  jb      short loc_180078127
0x18007811f  cmp     dword ptr [rsi], 210h
0x180078125  jz      short loc_18007818F
0x180078127  mov     rcx, cs:WPP_GLOBAL_Control
0x18007812e  mov     edi, 278h
0x180078133  cmp     rcx, rbx
0x180078136  jz      loc_1800789BE
0x18007813c  mov     esi, 800h
0x180078141  test    [rcx+1Ch], esi
0x180078144  jz      short loc_180078169
0x180078146  cmp     byte ptr [rcx+19h], 2
0x18007814a  jb      short loc_180078169
0x18007814c  mov     rcx, [rcx+10h]
0x180078150  lea     edx, [rdi+72h]
0x180078153  mov     r9d, edi
0x180078156  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x18007815d  call    WPP_SF_d
0x180078162  mov     rcx, cs:WPP_GLOBAL_Control
0x180078169  cmp     rcx, rbx
0x18007816c  jz      loc_1800789BE
0x180078172  test    [rcx+1Ch], esi
0x180078175  jz      loc_1800789BE
0x18007817b  cmp     byte ptr [rcx+19h], 6
0x18007817f  jb      loc_1800789BE
0x180078185  mov     edx, 2EBh
0x18007818a  jmp     loc_1800789AB
0x18007818f  test    r15d, r15d
0x180078192  mov     ecx, r13d
0x180078195  mov     eax, r13d
0x180078198  mov     r13d, [rbp+1E0h+arg_20]
0x18007819f  setz    cl
0x1800781a2  xor     edi, edi
0x1800781a4  test    r13d, r13d
0x1800781a7  setz    al
0x1800781aa  cmp     ecx, eax
0x1800781ac  jz      short loc_180078214
0x1800781ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800781b5  cmp     rcx, rbx
0x1800781b8  jz      loc_180078717
0x1800781be  mov     esi, 800h
0x1800781c3  test    [rcx+1Ch], esi
0x1800781c6  jz      short loc_1800781EE
0x1800781c8  cmp     byte ptr [rcx+19h], 2
0x1800781cc  jb      short loc_1800781EE
0x1800781ce  mov     rcx, [rcx+10h]
0x1800781d2  lea     r9d, [rdi+57h]
0x1800781d6  mov     edx, 2ECh
0x1800781db  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x1800781e2  call    WPP_SF_d
0x1800781e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800781ee  cmp     rcx, rbx
0x1800781f1  jz      loc_180078717
0x1800781f7  test    [rcx+1Ch], esi
0x1800781fa  jz      loc_180078717
0x180078200  cmp     byte ptr [rcx+19h], 6
0x180078204  jb      loc_180078717
0x18007820a  mov     edx, 2EDh
0x18007820f  jmp     loc_180078701
0x180078214  test    r14, r14
0x180078217  jz      loc_1800786A5
0x18007821d  cmp     [r14], di
0x180078221  jz      loc_1800786A5
0x180078227  mov     rdx, r14
0x18007822a  lea     rcx, aAddresses; "Addresses"
0x180078231  call    FormatKey
0x180078236  mov     [rsp+2E0h+lpSubKey], rax
0x18007823b  test    rax, rax
0x18007823e  jnz     short loc_1800782A8
0x180078240  mov     rcx, cs:WPP_GLOBAL_Control
0x180078247  lea     edi, [rax+8]
0x18007824a  cmp     rcx, rbx
0x18007824d  jz      loc_1800789BE
0x180078253  mov     esi, 800h
0x180078258  test    [rcx+1Ch], esi
0x18007825b  jz      short loc_180078282
0x18007825d  cmp     byte ptr [rcx+19h], 2
0x180078261  jb      short loc_180078282
0x180078263  mov     rcx, [rcx+10h]
0x180078267  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x18007826e  mov     edx, 2F9h
0x180078273  mov     r9d, edi
0x180078276  call    WPP_SF_d
0x18007827b  mov     rcx, cs:WPP_GLOBAL_Control
0x180078282  cmp     rcx, rbx
0x180078285  jz      loc_1800789BE
0x18007828b  test    [rcx+1Ch], esi
0x18007828e  jz      loc_1800789BE
0x180078294  cmp     byte ptr [rcx+19h], 6
0x180078298  jb      loc_1800789BE
0x18007829e  mov     edx, 2FAh
0x1800782a3  jmp     loc_1800789AB
0x1800782a8  lea     rdx, [rsp+2E0h+var_288]
0x1800782ad  lea     rcx, [rbp+1E0h+hKey]; phkResult
0x1800782b1  call    DwOpenUsersRegistry
0x1800782b6  xor     ecx, ecx
0x1800782b8  mov     edi, eax
0x1800782ba  test    eax, eax
0x1800782bc  jz      short loc_1800782EF
0x1800782be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800782c5  cmp     rcx, rbx
0x1800782c8  jz      loc_180078626
0x1800782ce  test    dword ptr [rcx+1Ch], 800h
0x1800782d5  jz      loc_180078626
0x1800782db  cmp     byte ptr [rcx+19h], 2
0x1800782df  jb      loc_180078626
0x1800782e5  mov     edx, 2FBh
0x1800782ea  jmp     loc_180078613
0x1800782ef  lea     rax, [rsp+2E0h+dwDisposition]
0x1800782f4  xor     r9d, r9d; lpClass
0x1800782f7  mov     [rsp+2E0h+lpdwDisposition], rax; lpdwDisposition
0x1800782fc  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\RAS AutoDial"
0x180078303  lea     rax, [rsp+2E0h+var_280]
0x180078308  xor     r8d, r8d; Reserved
0x18007830b  mov     [rsp+2E0h+phkResult], rax; phkResult
0x180078310  mov     [rsp+2E0h+lpSecurityAttributes], rcx; lpSecurityAttributes
0x180078315  mov     [rsp+2E0h+samDesired], 2001Fh; samDesired
0x18007831d  mov     [rsp+2E0h+dwOptions], ecx; dwOptions
0x180078321  mov     rcx, [rbp+1E0h+hKey]; hKey
0x180078325  call    cs:__imp_RegCreateKeyExW
0x18007832b  xor     ecx, ecx
0x18007832d  mov     edi, eax
0x18007832f  test    eax, eax
0x180078331  jz      short loc_180078364
0x180078333  mov     rcx, cs:WPP_GLOBAL_Control
0x18007833a  cmp     rcx, rbx
0x18007833d  jz      loc_180078626
0x180078343  test    dword ptr [rcx+1Ch], 800h
0x18007834a  jz      loc_180078626
0x180078350  cmp     byte ptr [rcx+19h], 2
0x180078354  jb      loc_180078626
0x18007835a  mov     edx, 2FCh
0x18007835f  jmp     loc_180078613
0x180078364  test    rsi, rsi
0x180078367  jnz     short loc_1800783DA
0x180078369  test    r15d, r15d
0x18007836c  jnz     short loc_1800783DA
0x18007836e  test    r13d, r13d
0x180078371  jnz     short loc_1800783DA
0x180078373  mov     rsi, [rsp+2E0h+lpSubKey]
0x180078378  xor     r9d, r9d; Reserved
0x18007837b  mov     rcx, [rsp+2E0h+var_280]; hKey
0x180078380  mov     rdx, rsi; lpSubKey
0x180078383  xor     r8d, r8d; samDesired
0x180078386  call    cs:__imp_RegDeleteKeyExW
0x18007838c  mov     edi, eax
0x18007838e  test    eax, eax
0x180078390  jz      loc_18007862B
0x180078396  mov     rcx, cs:WPP_GLOBAL_Control
0x18007839d  cmp     rcx, rbx
0x1800783a0  jz      loc_18007862B
0x1800783a6  test    dword ptr [rcx+1Ch], 800h
0x1800783ad  jz      loc_18007862B
0x1800783b3  cmp     byte ptr [rcx+19h], 2
0x1800783b7  jb      loc_18007862B
0x1800783bd  mov     rcx, [rcx+10h]
0x1800783c1  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x1800783c8  mov     edx, 2FDh
0x1800783cd  mov     r9d, eax
0x1800783d0  call    WPP_SF_d
0x1800783d5  jmp     loc_18007862B
0x1800783da  mov     rdx, [rsp+2E0h+lpSubKey]; lpSubKey
0x1800783df  lea     rax, [rsp+2E0h+dwDisposition]
0x1800783e4  mov     [rsp+2E0h+lpdwDisposition], rax; lpdwDisposition
0x1800783e9  xor     r9d, r9d; lpClass
0x1800783ec  lea     rax, [rsp+2E0h+var_268]
0x1800783f1  xor     r8d, r8d; Reserved
0x1800783f4  mov     [rsp+2E0h+phkResult], rax; phkResult
0x1800783f9  mov     [rsp+2E0h+lpSecurityAttributes], rcx; lpSecurityAttributes
0x1800783fe  mov     [rsp+2E0h+samDesired], 2; samDesired
0x180078406  mov     [rsp+2E0h+dwOptions], ecx; dwOptions
0x18007840a  mov     rcx, [rsp+2E0h+var_280]; hKey
0x18007840f  call    cs:__imp_RegCreateKeyExW
0x180078415  mov     edi, eax
0x180078417  test    eax, eax
0x180078419  jz      short loc_18007844C
0x18007841b  mov     rcx, cs:WPP_GLOBAL_Control
0x180078422  cmp     rcx, rbx
0x180078425  jz      loc_180078626
0x18007842b  test    dword ptr [rcx+1Ch], 800h
0x180078432  jz      loc_180078626
0x180078438  cmp     byte ptr [rcx+19h], 2
0x18007843c  jb      loc_180078626
0x180078442  mov     edx, 2FEh
0x180078447  jmp     loc_180078613
0x18007844c  test    rsi, rsi
0x18007844f  jz      short loc_18007849F
0x180078451  test    r15d, r15d
0x180078454  jz      short loc_180078466
0x180078456  test    r13d, r13d
0x180078459  jz      short loc_180078466
0x18007845b  mov     eax, r13d
0x18007845e  imul    eax, [rsi]
0x180078461  cmp     r15d, eax
0x180078464  jnb     short loc_18007849F
0x180078466  mov     edi, 57h ; 'W'
0x18007846b  mov     rcx, cs:WPP_GLOBAL_Control
0x180078472  cmp     rcx, rbx
0x180078475  jz      loc_180078626
0x18007847b  test    dword ptr [rcx+1Ch], 800h
0x180078482  jz      loc_180078626
0x180078488  cmp     byte ptr [rcx+19h], 2
0x18007848c  jb      loc_180078626
0x180078492  mov     edx, 2FFh
0x180078497  mov     r9d, edi
0x18007849a  jmp     loc_180078616
0x18007849f  mov     rcx, [rsp+2E0h+var_280]; hKey
0x1800784a4  lea     r8, [rsp+2E0h+lpData]
0x1800784a9  mov     rdx, r14
0x1800784ac  call    AutodialAddressToNetwork
0x1800784b1  xor     ecx, ecx
0x1800784b3  mov     edi, eax
0x1800784b5  lea     r15d, [rcx+1]
0x1800784b9  test    eax, eax
0x1800784bb  jz      loc_1800785B8
0x1800784c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800784c8  cmp     rcx, rbx
0x1800784cb  jz      short loc_1800784F4
0x1800784cd  test    dword ptr [rcx+1Ch], 800h
  ... truncated ...
```
