# ConfigRegister(x,x,x,x,x)

- ea: `0x10024d8e`
- end: `0x100252a9`
- name: `_ConfigRegister@20`
- size: `1307`
- prototype: `int __stdcall(int, int, BYTE *lpData)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x100068a0`

## callees

- `0x10006390`
- `0x10006400`
- `0x10018b80`
- `0x1002496b`
- `0x100249b2`
- `0x10024ca0`
- `0x10024cc9`
- `0x10024d06`
- `0x10024d8e`
- `0x1003325b`
- `0x100335a6`
- `0x100336a8`
- `0x10035510`
- `0x10035530`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x10024e57`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x100250a8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x10025276`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x10024e57`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x100250a8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x10025276`

## string_xrefs

- `0x100251bd`: `CanLink`
- `0x1002524b`: `CreateDBOnExport`

## pseudocode

```c
int __stdcall ConfigRegister(int a1, int a2, BYTE *lpData)
{
  wchar_t **v4; // edi
  int v6; // ebx
  int v7; // edx
  int v8; // edx
  int v9; // edx
  LSTATUS v10; // eax
  const WCHAR *v11; // edx
  LSTATUS v12; // esi
  int v13; // eax
  int v14; // eax
  HKEY hKey; // [esp+10h] [ebp-A38h] BYREF
  DWORD cbData; // [esp+14h] [ebp-A34h] BYREF
  DWORD Type; // [esp+18h] [ebp-A30h] BYREF
  BYTE v18; // [esp+1Fh] [ebp-A29h] BYREF
  BYTE v19[4]; // [esp+20h] [ebp-A28h] BYREF
  BYTE v20[4]; // [esp+24h] [ebp-A24h] BYREF
  WCHAR SubKey[264]; // [esp+28h] [ebp-A20h] BYREF
  BYTE Data[2]; // [esp+238h] [ebp-810h] BYREF

  v4 = off_10038830;
  hKey = 0;
  cbData = 128;
  WCSCPY2(SubKey, L"Software\\Microsoft\\Jet\\4.0", 0x105u);
  WCSCAT2(SubKey, L"\\", 0x105u);
  WCSCAT2(SubKey, L"Engines", 0x105u);
  WCSCAT2(SubKey, L"\\", 0x105u);
  WCSCAT2(SubKey, lpSubKey, 0x105u);
  if ( JetRegCreateKeyW(HKEY_LOCAL_MACHINE, SubKey, &hKey) )
    return -1;
  if ( !SetString(hKey, L"win32", lpData) )
  {
    v6 = 0;
    while ( 1 )
    {
      while ( 1 )
      {
        while ( 1 )
        {
          a2 = *(_DWORD *)a2;
          if ( !a2 )
          {
            RegCloseKey(hKey);
            if ( !LoadInternationalDLL() )
              return -1;
            while ( 2 )
            {
              WCSCPY2(SubKey, L"Software\\Microsoft\\Jet\\4.0", 0x105u);
              WCSCAT2(SubKey, L"\\", 0x105u);
              WCSCAT2(SubKey, L"ISAM Formats", 0x105u);
              WCSCAT2(SubKey, L"\\", 0x105u);
              WCSCAT2(SubKey, *v4, 0x105u);
              if ( JetRegCreateKeyW(HKEY_LOCAL_MACHINE, SubKey, &hKey) )
                return -1;
              v12 = SetString(hKey, L"Engine", (BYTE *)v4[1]);
              if ( v12 )
                goto LABEL_66;
              if ( v4[4] )
              {
                v13 = SetIDAString(hKey, L"ExportFilter", (int)v4[4]);
LABEL_50:
                v12 = v13;
                if ( v13 )
                  goto LABEL_66;
              }
              else if ( *v4[2] )
              {
                v13 = SetString(hKey, L"ExportFilter", (BYTE *)v4[2]);
                goto LABEL_50;
              }
              if ( v4[5] )
              {
                v14 = SetIDAString(hKey, L"ImportFilter", (int)v4[5]);
LABEL_55:
                v12 = v14;
                if ( v14 )
                  goto LABEL_66;
              }
              else if ( *v4[3] )
              {
                v14 = SetString(hKey, L"ImportFilter", (BYTE *)v4[3]);
                goto LABEL_55;
              }
              v12 = SetBoolean(hKey, L"CanLink", (int)v4[6]);
              if ( v12
                || (v12 = SetBoolean(hKey, L"OneTablePerFile", (int)v4[7])) != 0
                || (*(_DWORD *)v19 = v4[8], (v12 = JetRegSetValueExW(hKey, L"IsamType", 0, 4u, v19, 4u)) != 0)
                || (v12 = SetBoolean(hKey, L"IndexDialog", (int)v4[9])) != 0
                || v4[9] && (v12 = SetIDAString(hKey, L"IndexFilter", (int)v4[10])) != 0
                || (v12 = SetBoolean(hKey, L"CreateDBOnExport", (int)v4[11])) != 0
                || (v12 = SetBoolean(hKey, L"SupportsLongNames", (int)v4[12])) != 0 )
              {
LABEL_66:
                UnLoadInternationalDLL();
                if ( v12 )
                  goto LABEL_3;
                return 0;
              }
              RegCloseKey(hKey);
              v4 += 13;
              if ( ++v6 >= 4 )
              {
                UnLoadInternationalDLL();
                return 0;
              }
              continue;
            }
          }
          if ( *(_BYTE *)(a2 + 4) )
            break;
          if ( **(_WORD **)(a2 + 20) )
          {
            cbData = 2050;
            *(_WORD *)Data = 0;
            if ( JetRegQueryValueExW(hKey, *(LPCWSTR *)(a2 + 8), 0, &Type, Data, &cbData) )
            {
              cbData = 0;
LABEL_40:
              v10 = SetString(hKey, *(LPCWSTR *)(a2 + 8), *(BYTE **)(a2 + 20));
              goto LABEL_41;
            }
            if ( (cbData & 0xFFFFFFFE) >= 0x802 )
LABEL_68:
              __report_rangecheckfailure();
            *(_WORD *)&Data[cbData & 0xFFFFFFFE] = 0;
            if ( !cbData || Type != 1 )
              goto LABEL_40;
          }
        }
        if ( *(_BYTE *)(a2 + 4) == 1 )
          break;
        if ( *(_BYTE *)(a2 + 4) == 2 )
        {
          cbData = 1;
          if ( JetRegQueryValueExW(hKey, *(LPCWSTR *)(a2 + 8), 0, &Type, &v18, &cbData) || !cbData || Type != 3 )
          {
            v10 = SetBoolean(hKey, *(LPCWSTR *)(a2 + 8), *(_DWORD *)(a2 + 16));
LABEL_41:
            if ( v10 )
              goto LABEL_3;
          }
        }
        else if ( *(_BYTE *)(a2 + 4) == 3 )
        {
          cbData = 2050;
          if ( JetRegQueryValueExW(hKey, *(LPCWSTR *)(a2 + 8), 0, &Type, Data, &cbData) || (int)cbData <= 0 || Type != 1 )
            goto LABEL_20;
          if ( 2 * cbData >= 0x802 )
            goto LABEL_68;
          *(_WORD *)&Data[2 * cbData] = 0;
          v7 = *(_DWORD *)(a2 + 20);
          if ( !v7 || WCSICMP(Data, v7) )
          {
            v8 = *(_DWORD *)(a2 + 24);
            if ( !v8 || WCSICMP(Data, v8) )
            {
              v9 = *(_DWORD *)(a2 + 28);
              if ( !v9 || WCSICMP(Data, v9) )
              {
LABEL_20:
                if ( *(_DWORD *)(a2 + 16) == 1 )
                {
                  v10 = SetString(hKey, *(LPCWSTR *)(a2 + 8), *(BYTE **)(a2 + 24));
                }
                else
                {
                  v11 = *(const WCHAR **)(a2 + 8);
                  if ( *(_DWORD *)(a2 + 16) == 2 )
                    v10 = SetString(hKey, v11, *(BYTE **)(a2 + 28));
                  else
                    v10 = SetString(hKey, v11, *(BYTE **)(a2 + 20));
                }
                goto LABEL_41;
              }
            }
          }
        }
      }
      cbData = 4;
      if ( JetRegQueryValueExW(hKey, *(LPCWSTR *)(a2 + 8), 0, &Type, v20, &cbData) || !cbData || Type != 4 )
      {
        *(_DWORD *)v19 = *(_DWORD *)(a2 + 16);
        v10 = JetRegSetValueExW(hKey, *(LPCWSTR *)(a2 + 8), 0, 4u, v19, 4u);
        goto LABEL_41;
      }
    }
  }
LABEL_3:
  RegCloseKey(hKey);
  return -1;
}

```

## disassembly

```asm
0x10024d8e  mov     edi, edi
0x10024d90  push    ebp
0x10024d91  mov     ebp, esp
0x10024d93  and     esp, 0FFFFFFF8h
0x10024d96  sub     esp, 0A3Ch
0x10024d9c  mov     eax, ___security_cookie
0x10024da1  xor     eax, esp
0x10024da3  mov     [esp+0A3Ch+var_4], eax
0x10024daa  push    ebx
0x10024dab  mov     ebx, [ebp+lpData]
0x10024dae  lea     ecx, [esp+0A40h+SubKey]
0x10024db2  push    esi
0x10024db3  mov     esi, [ebp+arg_4]
0x10024db6  mov     edx, offset aSoftwareMicros; "Software\\Microsoft\\Jet\\4.0"
0x10024dbb  push    edi
0x10024dbc  push    105h
0x10024dc1  mov     edi, offset off_10038830; "Excel 5.0"
0x10024dc6  mov     [esp+0A4Ch+hKey], 0
0x10024dce  mov     [esp+0A4Ch+cbData], 80h
0x10024dd6  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x10024ddb  push    105h
0x10024de0  mov     edx, offset asc_1000539C; "\\"
0x10024de5  lea     ecx, [esp+0A4Ch+SubKey]
0x10024de9  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x10024dee  push    105h
0x10024df3  mov     edx, offset aEngines_0; "Engines"
0x10024df8  lea     ecx, [esp+0A4Ch+SubKey]
0x10024dfc  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x10024e01  push    105h
0x10024e06  mov     edx, offset asc_1000539C; "\\"
0x10024e0b  lea     ecx, [esp+0A4Ch+SubKey]
0x10024e0f  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x10024e14  mov     edx, lpSubKey
0x10024e1a  lea     ecx, [esp+0A48h+SubKey]
0x10024e1e  push    105h
0x10024e23  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x10024e28  lea     eax, [esp+0A48h+hKey]
0x10024e2c  push    eax; phkResult
0x10024e2d  lea     eax, [esp+0A4Ch+SubKey]
0x10024e31  push    eax; lpSubKey
0x10024e32  push    80000002h; hKey
0x10024e37  call    _JetRegCreateKeyW@12; JetRegCreateKeyW(x,x,x)
0x10024e3c  test    eax, eax
0x10024e3e  jnz     short loc_10024E5D
0x10024e40  mov     ecx, [esp+0A48h+hKey]; hKey
0x10024e44  mov     edx, offset aWin32; "win32"
0x10024e49  push    ebx; lpData
0x10024e4a  call    SetString
0x10024e4f  test    eax, eax
0x10024e51  jz      short loc_10024E77
0x10024e53  push    [esp+0A48h+hKey]; hKey
0x10024e57  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x10024e5d  or      eax, 0FFFFFFFFh
0x10024e60  mov     ecx, [esp+0A48h+var_4]
0x10024e67  pop     edi
0x10024e68  pop     esi
0x10024e69  pop     ebx
0x10024e6a  xor     ecx, esp; StackCookie
0x10024e6c  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10024e71  mov     esp, ebp
0x10024e73  pop     ebp
0x10024e74  retn    0Ch
0x10024e77  xor     ebx, ebx
0x10024e79  jmp     loc_1002509A
0x10024e7e  movzx   eax, byte ptr [esi+4]
0x10024e82  sub     eax, ebx
0x10024e84  jz      loc_10025017
0x10024e8a  sub     eax, 1
0x10024e8d  jz      loc_10024FBF
0x10024e93  sub     eax, 1
0x10024e96  jz      loc_10024F72
0x10024e9c  sub     eax, 1
0x10024e9f  jnz     loc_1002509A
0x10024ea5  lea     eax, [esp+0A48h+cbData]
0x10024ea9  mov     [esp+0A48h+cbData], 802h
0x10024eb1  push    eax; lpcbData
0x10024eb2  lea     eax, [esp+0A4Ch+Data]
0x10024eb9  push    eax; lpData
0x10024eba  lea     eax, [esp+0A50h+Type]
0x10024ebe  push    eax; lpType
0x10024ebf  push    ebx; lpReserved
0x10024ec0  push    dword ptr [esi+8]; lpValueName
0x10024ec3  push    [esp+0A5Ch+hKey]; hKey
0x10024ec7  call    _JetRegQueryValueExW@24; JetRegQueryValueExW(x,x,x,x,x,x)
0x10024ecc  test    eax, eax
0x10024ece  jnz     short loc_10024F47
0x10024ed0  mov     eax, [esp+0A48h+cbData]
0x10024ed4  test    eax, eax
0x10024ed6  jle     short loc_10024F47
0x10024ed8  cmp     [esp+0A48h+Type], 1
0x10024edd  jnz     short loc_10024F47
0x10024edf  add     eax, eax
0x10024ee1  cmp     eax, 802h
0x10024ee6  jnb     loc_100252A4
0x10024eec  xor     ecx, ecx
0x10024eee  mov     word ptr [esp+eax+0A48h+Data], cx
0x10024ef6  mov     edx, [esi+14h]
0x10024ef9  test    edx, edx
0x10024efb  jz      short loc_10024F11
0x10024efd  lea     ecx, [esp+0A48h+Data]
0x10024f04  call    _WCSICMP@8; WCSICMP(x,x)
0x10024f09  test    eax, eax
0x10024f0b  jz      loc_1002509A
0x10024f11  mov     edx, [esi+18h]
0x10024f14  test    edx, edx
0x10024f16  jz      short loc_10024F2C
0x10024f18  lea     ecx, [esp+0A48h+Data]
0x10024f1f  call    _WCSICMP@8; WCSICMP(x,x)
0x10024f24  test    eax, eax
0x10024f26  jz      loc_1002509A
0x10024f2c  mov     edx, [esi+1Ch]
0x10024f2f  test    edx, edx
0x10024f31  jz      short loc_10024F47
0x10024f33  lea     ecx, [esp+0A48h+Data]
0x10024f3a  call    _WCSICMP@8; WCSICMP(x,x)
0x10024f3f  test    eax, eax
0x10024f41  jz      loc_1002509A
0x10024f47  cmp     dword ptr [esi+10h], 1
0x10024f4b  jnz     short loc_10024F55
0x10024f4d  push    dword ptr [esi+18h]
0x10024f50  jmp     loc_10025086
0x10024f55  cmp     dword ptr [esi+10h], 2
0x10024f59  mov     edx, [esi+8]
0x10024f5c  mov     ecx, [esp+0A48h+hKey]
0x10024f60  jnz     short loc_10024F6A
0x10024f62  push    dword ptr [esi+1Ch]
0x10024f65  jmp     loc_1002508D
0x10024f6a  push    dword ptr [esi+14h]
0x10024f6d  jmp     loc_1002508D
0x10024f72  lea     eax, [esp+0A48h+cbData]
0x10024f76  mov     [esp+0A48h+cbData], 1
0x10024f7e  push    eax; lpcbData
0x10024f7f  lea     eax, [esp+0A4Ch+var_A29]
0x10024f83  push    eax; lpData
0x10024f84  lea     eax, [esp+0A50h+Type]
0x10024f88  push    eax; lpType
0x10024f89  push    ebx; lpReserved
0x10024f8a  push    dword ptr [esi+8]; lpValueName
0x10024f8d  push    [esp+0A5Ch+hKey]; hKey
0x10024f91  call    _JetRegQueryValueExW@24; JetRegQueryValueExW(x,x,x,x,x,x)
0x10024f96  test    eax, eax
0x10024f98  jnz     short loc_10024FAB
0x10024f9a  cmp     [esp+0A48h+cbData], ebx
0x10024f9e  jz      short loc_10024FAB
0x10024fa0  cmp     [esp+0A48h+Type], 3
0x10024fa5  jz      loc_1002509A
0x10024fab  push    dword ptr [esi+10h]; int
0x10024fae  mov     edx, [esi+8]; lpValueName
0x10024fb1  mov     ecx, [esp+0A4Ch+hKey]; hKey
0x10024fb5  call    SetBoolean
0x10024fba  jmp     loc_10025092
0x10024fbf  lea     eax, [esp+0A48h+cbData]
0x10024fc3  mov     [esp+0A48h+cbData], 4
0x10024fcb  push    eax; lpcbData
0x10024fcc  lea     eax, [esp+0A4Ch+var_A24]
0x10024fd0  push    eax; lpData
0x10024fd1  lea     eax, [esp+0A50h+Type]
0x10024fd5  push    eax; lpType
0x10024fd6  push    ebx; lpReserved
0x10024fd7  push    dword ptr [esi+8]; lpValueName
0x10024fda  push    [esp+0A5Ch+hKey]; hKey
0x10024fde  call    _JetRegQueryValueExW@24; JetRegQueryValueExW(x,x,x,x,x,x)
0x10024fe3  test    eax, eax
0x10024fe5  jnz     short loc_10024FF8
0x10024fe7  cmp     [esp+0A48h+cbData], ebx
0x10024feb  jz      short loc_10024FF8
0x10024fed  cmp     [esp+0A48h+Type], 4
0x10024ff2  jz      loc_1002509A
0x10024ff8  mov     eax, [esi+10h]
0x10024ffb  push    4; cbData
0x10024ffd  mov     dword ptr [esp+0A4Ch+var_A28], eax
0x10025001  lea     eax, [esp+0A4Ch+var_A28]
0x10025005  push    eax; lpData
0x10025006  push    4; dwType
0x10025008  push    ebx; Reserved
0x10025009  push    dword ptr [esi+8]; lpValueName
0x1002500c  push    [esp+0A5Ch+hKey]; hKey
0x10025010  call    _JetRegSetValueExW@24; JetRegSetValueExW(x,x,x,x,x,x)
0x10025015  jmp     short loc_10025092
0x10025017  mov     eax, [esi+14h]
0x1002501a  cmp     [eax], bx
0x1002501d  jz      short loc_1002509A
0x1002501f  xor     eax, eax
0x10025021  mov     [esp+0A48h+cbData], 802h
0x10025029  mov     word ptr [esp+0A48h+Data], ax
0x10025031  lea     eax, [esp+0A48h+cbData]
0x10025035  push    eax; lpcbData
0x10025036  lea     eax, [esp+0A4Ch+Data]
0x1002503d  push    eax; lpData
0x1002503e  lea     eax, [esp+0A50h+Type]
0x10025042  push    eax; lpType
0x10025043  push    ebx; lpReserved
0x10025044  push    dword ptr [esi+8]; lpValueName
0x10025047  push    [esp+0A5Ch+hKey]; hKey
0x1002504b  call    _JetRegQueryValueExW@24; JetRegQueryValueExW(x,x,x,x,x,x)
0x10025050  test    eax, eax
0x10025052  jnz     short loc_1002507F
0x10025054  mov     eax, [esp+0A48h+cbData]
0x10025058  and     eax, 0FFFFFFFEh
0x1002505b  cmp     eax, 802h
0x10025060  jnb     loc_100252A4
0x10025066  xor     ecx, ecx
0x10025068  mov     word ptr [esp+eax+0A48h+Data], cx
0x10025070  cmp     [esp+0A48h+cbData], ecx
0x10025074  jz      short loc_10025083
0x10025076  cmp     [esp+0A48h+Type], 1
0x1002507b  jz      short loc_1002509A
0x1002507d  jmp     short loc_10025083
0x1002507f  mov     [esp+0A48h+cbData], ebx
0x10025083  push    dword ptr [esi+14h]; lpData
0x10025086  mov     edx, [esi+8]; lpValueName
0x10025089  mov     ecx, [esp+0A4Ch+hKey]; hKey
0x1002508d  call    SetString
0x10025092  test    eax, eax
0x10025094  jnz     loc_10024E53
0x1002509a  mov     esi, [esi]
0x1002509c  test    esi, esi
0x1002509e  jnz     loc_10024E7E
0x100250a4  push    [esp+0A48h+hKey]; hKey
0x100250a8  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x100250ae  call    LoadInternationalDLL
0x100250b3  test    eax, eax
0x100250b5  jz      loc_10024E5D
0x100250bb  mov     esi, 105h
0x100250c0  lea     ecx, [esp+0A48h+SubKey]
0x100250c4  push    esi
0x100250c5  mov     edx, offset aSoftwareMicros; "Software\\Microsoft\\Jet\\4.0"
0x100250ca  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x100250cf  push    esi
0x100250d0  mov     edx, offset asc_1000539C; "\\"
0x100250d5  lea     ecx, [esp+0A4Ch+SubKey]
0x100250d9  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x100250de  push    esi
0x100250df  mov     edx, offset aIsamFormats; "ISAM Formats"
0x100250e4  lea     ecx, [esp+0A4Ch+SubKey]
0x100250e8  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x100250ed  push    esi
0x100250ee  mov     edx, offset asc_1000539C; "\\"
0x100250f3  lea     ecx, [esp+0A4Ch+SubKey]
0x100250f7  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x100250fc  mov     edx, [edi]
0x100250fe  lea     ecx, [esp+0A48h+SubKey]
0x10025102  push    esi
0x10025103  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x10025108  lea     eax, [esp+0A48h+hKey]
0x1002510c  push    eax; phkResult
0x1002510d  lea     eax, [esp+0A4Ch+SubKey]
0x10025111  push    eax; lpSubKey
0x10025112  push    80000002h; hKey
0x10025117  call    _JetRegCreateKeyW@12; JetRegCreateKeyW(x,x,x)
0x1002511c  test    eax, eax
0x1002511e  jnz     loc_10024E5D
0x10025124  push    dword ptr [edi+4]; lpData
0x10025127  mov     ecx, [esp+0A4Ch+hKey]; hKey
0x1002512b  mov     edx, offset aEngine; "Engine"
0x10025130  call    SetString
0x10025135  mov     esi, eax
0x10025137  test    esi, esi
0x10025139  jnz     loc_10025290
0x1002513f  cmp     [edi+10h], eax
0x10025142  jz      short loc_10025157
0x10025144  push    dword ptr [edi+10h]; int
0x10025147  mov     ecx, [esp+0A4Ch+hKey]; hKey
0x1002514b  mov     edx, offset aExportfilter; "ExportFilter"
0x10025150  call    SetIDAString
0x10025155  jmp     short loc_10025170
0x10025157  mov     eax, [edi+8]
0x1002515a  xor     ecx, ecx
0x1002515c  cmp     [eax], cx
0x1002515f  jz      short loc_1002517C
0x10025161  mov     ecx, [esp+0A48h+hKey]; hKey
0x10025165  mov     edx, offset aExportfilter; "ExportFilter"
0x1002516a  push    eax; lpData
0x1002516b  call    SetString
0x10025170  mov     esi, eax
0x10025172  test    esi, esi
0x10025174  jnz     loc_10025290
0x1002517a  xor     ecx, ecx
0x1002517c  cmp     dword ptr [edi+14h], 0
0x10025180  jz      short loc_10025195
0x10025182  push    dword ptr [edi+14h]; int
0x10025185  mov     ecx, [esp+0A4Ch+hKey]; hKey
0x10025189  mov     edx, offset aImportfilter; "ImportFilter"
0x1002518e  call    SetIDAString
0x10025193  jmp     short loc_100251AC
0x10025195  mov     eax, [edi+0Ch]
0x10025198  cmp     [eax], cx
0x1002519b  jz      short loc_100251B6
0x1002519d  mov     ecx, [esp+0A48h+hKey]; hKey
0x100251a1  mov     edx, offset aImportfilter; "ImportFilter"
0x100251a6  push    eax; lpData
0x100251a7  call    SetString
0x100251ac  mov     esi, eax
0x100251ae  test    esi, esi
0x100251b0  jnz     loc_10025290
0x100251b6  push    dword ptr [edi+18h]; int
0x100251b9  mov     ecx, [esp+0A4Ch+hKey]; hKey
0x100251bd  mov     edx, offset aCanlink; "CanLink"
0x100251c2  call    SetBoolean
0x100251c7  mov     esi, eax
  ... truncated ...
```
