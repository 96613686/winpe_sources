# ReadRegTree

- ea: `0x10026fb0`
- end: `0x10027495`
- name: `ReadRegTree`
- size: `1253`
- prototype: `int __thiscall(HKEY hKey)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callers

- `0x100274a0`

## callees

- `0x10026fb0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x10027018`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x10027065`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x100270c1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x100270fb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1002714e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1002718b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x100271c8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x10027205`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x10027242`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1002727f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x100272bc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x100272f9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x10027336`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x10027373`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x100273b0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x100273ed`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1002742a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x10027467`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x10027018`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x10027065`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x100270c1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x100270fb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1002714e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1002718b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x100271c8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x10027205`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x10027242`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1002727f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x100272bc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x100272f9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x10027336`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x10027373`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x100273b0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x100273ed`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1002742a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x10027467`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x10026fec`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x10026fec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1002748b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1002748b`

## string_xrefs

- `0x100273e7`: `PreparedUpdate`

## pseudocode

```c
int __thiscall ReadRegTree(HKEY hKey)
{
  int result; // eax
  LSTATUS v2; // eax
  LSTATUS v3; // eax
  LSTATUS v4; // eax
  LSTATUS v5; // eax
  LSTATUS v6; // eax
  LSTATUS v7; // eax
  LSTATUS v8; // eax
  LSTATUS v9; // eax
  LSTATUS v10; // eax
  LSTATUS v11; // eax
  LSTATUS v12; // eax
  LSTATUS v13; // eax
  LSTATUS v14; // eax
  LSTATUS v15; // eax
  LSTATUS v16; // eax
  LSTATUS v17; // eax
  LSTATUS v18; // eax
  LSTATUS v19; // eax
  DWORD Type; // [esp+4h] [ebp-1Ch] BYREF
  DWORD cbData; // [esp+8h] [ebp-18h] BYREF
  BYTE v22[4]; // [esp+Ch] [ebp-14h] BYREF
  BYTE v23[4]; // [esp+10h] [ebp-10h] BYREF
  BYTE v24[4]; // [esp+14h] [ebp-Ch] BYREF
  BYTE Data[4]; // [esp+18h] [ebp-8h] BYREF
  HKEY phkResult; // [esp+1Ch] [ebp-4h] BYREF

  *(_DWORD *)v23 = 0;
  *(_DWORD *)v22 = 0;
  phkResult = 0;
  *(_DWORD *)Data = 0;
  *(_DWORD *)v24 = 1;
  result = RegOpenKeyExA(hKey, "ODBC", 0, 0x20019u, &phkResult);
  if ( result )
    return result;
  cbData = 4;
  v2 = RegQueryValueExA(phkResult, "TraceODBCAPI", 0, &Type, Data, &cbData);
  if ( (int)cbData < 4 && Type == 1 )
  {
    if ( v2 )
      goto LABEL_9;
    Data[cbData] = 0;
  }
  else if ( v2 )
  {
    goto LABEL_9;
  }
  if ( *(_DWORD *)Data == 1 )
    wRmtTrace |= 8u;
LABEL_9:
  cbData = 4;
  v3 = RegQueryValueExA(phkResult, "DisableAsync", 0, &Type, v24, &cbData);
  if ( (int)cbData < 4 && Type == 1 )
  {
    if ( !v3 )
    {
      v24[cbData] = 0;
      goto LABEL_14;
    }
  }
  else if ( !v3 )
  {
LABEL_14:
    if ( *(_DWORD *)v24 == 1 )
    {
      wRmtTrace |= 0x10u;
    }
    else if ( !*(_DWORD *)v24 )
    {
      wRmtTrace &= ~0x10u;
    }
  }
  cbData = 4;
  v4 = RegQueryValueExA(phkResult, "TraceSQLMode", 0, &Type, v23, &cbData);
  if ( (int)cbData < 4 && Type == 1 && !v4 )
    v23[cbData] = 0;
  cbData = 4;
  v5 = RegQueryValueExA(phkResult, "SQLTraceMode", 0, &Type, v22, &cbData);
  if ( (int)cbData < 4 && Type == 1 && !v5 )
    v22[cbData] = 0;
  if ( *(_DWORD *)v23 )
    wSQLTrace = *(_DWORD *)v23;
  if ( *(_DWORD *)v22 )
    wSQLTrace = *(_DWORD *)v22;
  cbData = 4;
  v6 = RegQueryValueExA(phkResult, "QueryTimeout", 0, &Type, &wQueryTimeout, &cbData);
  if ( (int)cbData < 4 && Type == 1 && !v6 )
    *(&wQueryTimeout + cbData) = 0;
  cbData = 4;
  v7 = RegQueryValueExA(phkResult, "LoginTimeout", 0, &Type, &wLoginTimeout, &cbData);
  if ( (int)cbData < 4 && Type == 1 && !v7 )
    *(&wLoginTimeout + cbData) = 0;
  cbData = 4;
  v8 = RegQueryValueExA(phkResult, "ConnectionTimeout", 0, &Type, &wConnectionTimeout, &cbData);
  if ( (int)cbData < 4 && Type == 1 && !v8 )
    *(&wConnectionTimeout + cbData) = 0;
  cbData = 4;
  v9 = RegQueryValueExA(phkResult, "TryJetAuth", 0, &Type, &wTryJetAuth, &cbData);
  if ( (int)cbData < 4 && Type == 1 && !v9 )
    *(&wTryJetAuth + cbData) = 0;
  cbData = 4;
  v10 = RegQueryValueExA(phkResult, "FatBlastRows", 0, &Type, &wFatBlastRows, &cbData);
  if ( (int)cbData < 4 && Type == 1 && !v10 )
    *(&wFatBlastRows + cbData) = 0;
  cbData = 4;
  v11 = RegQueryValueExA(phkResult, "FatBlastTimeout", 0, &Type, &wFatBlastTimeout, &cbData);
  if ( (int)cbData < 4 && Type == 1 && !v11 )
    *(&wFatBlastTimeout + cbData) = 0;
  cbData = 4;
  v12 = RegQueryValueExA(phkResult, "AsyncRetryInterval", 0, &Type, &wRetryInterval, &cbData);
  if ( (int)cbData < 4 && Type == 1 && !v12 )
    *(&wRetryInterval + cbData) = 0;
  cbData = 4;
  v13 = RegQueryValueExA(phkResult, "AttachCaseSensitive", 0, &Type, &wAttCaseSense, &cbData);
  if ( (int)cbData < 4 && Type == 1 && !v13 )
    *(&wAttCaseSense + cbData) = 0;
  cbData = 4;
  v14 = RegQueryValueExA(phkResult, "FastRequery", 0, &Type, &wFastRequery, &cbData);
  if ( (int)cbData < 4 && Type == 1 && !v14 )
    *(&wFastRequery + cbData) = 0;
  cbData = 4;
  v15 = RegQueryValueExA(phkResult, "ODBCISAMAttach", 0, &Type, &wODBCISAMAttach, &cbData);
  if ( (int)cbData < 4 && Type == 1 && !v15 )
    *(&wODBCISAMAttach + cbData) = 0;
  cbData = 4;
  v16 = RegQueryValueExA(phkResult, "PreparedInsert", 0, &Type, &wPreparedInsert, &cbData);
  if ( (int)cbData < 4 && Type == 1 && !v16 )
    *(&wPreparedInsert + cbData) = 0;
  cbData = 4;
  v17 = RegQueryValueExA(phkResult, "PreparedUpdate", 0, &Type, &wPreparedUpdate, &cbData);
  if ( (int)cbData < 4 && Type == 1 && !v17 )
    *(&wPreparedUpdate + cbData) = 0;
  cbData = 4;
  v18 = RegQueryValueExA(phkResult, "SnapshotOnly", 0, &Type, &wSnapshotOnly, &cbData);
  if ( (int)cbData < 4 && Type == 1 && !v18 )
    *(&wSnapshotOnly + cbData) = 0;
  cbData = 131;
  v19 = RegQueryValueExA(phkResult, "AttachableObjects", 0, &Type, &szAttObj, &cbData);
  if ( (int)cbData < 131 && Type == 1 && !v19 )
    *(&szAttObj + cbData) = 0;
  return RegCloseKey(phkResult);
}

```

## disassembly

```asm
0x10026fb0  mov     edi, edi
0x10026fb2  push    ebp
0x10026fb3  mov     ebp, esp
0x10026fb5  sub     esp, 20h
0x10026fb8  lea     eax, [ebp+phkResult]
0x10026fbb  mov     dword ptr [ebp+var_10], 0
0x10026fc2  push    eax; phkResult
0x10026fc3  push    20019h; samDesired
0x10026fc8  push    0; ulOptions
0x10026fca  push    offset _szODBCSection; "ODBC"
0x10026fcf  push    ecx; hKey
0x10026fd0  mov     dword ptr [ebp+var_14], 0
0x10026fd7  mov     [ebp+phkResult], 0
0x10026fde  mov     dword ptr [ebp+Data], 0
0x10026fe5  mov     dword ptr [ebp+var_C], 1
0x10026fec  call    ds:__imp__RegOpenKeyExA@20; RegOpenKeyExA(x,x,x,x,x)
0x10026ff2  test    eax, eax
0x10026ff4  jnz     loc_10027491
0x10026ffa  mov     eax, [ebp+phkResult]
0x10026ffd  lea     ecx, [ebp+cbData]
0x10027000  push    ecx; lpcbData
0x10027001  lea     ecx, [ebp+Data]
0x10027004  mov     [ebp+cbData], 4
0x1002700b  push    ecx; lpData
0x1002700c  lea     ecx, [ebp+Type]
0x1002700f  push    ecx; lpType
0x10027010  push    0; lpReserved
0x10027012  push    offset _szTraceODBCAPI; "TraceODBCAPI"
0x10027017  push    eax; hKey
0x10027018  call    ds:__imp__RegQueryValueExA@24; RegQueryValueExA(x,x,x,x,x,x)
0x1002701e  mov     ecx, [ebp+cbData]
0x10027021  cmp     ecx, 4
0x10027024  jge     short loc_10027036
0x10027026  cmp     [ebp+Type], 1
0x1002702a  jnz     short loc_10027036
0x1002702c  test    eax, eax
0x1002702e  jnz     short loc_10027047
0x10027030  mov     [ebp+ecx+Data], al
0x10027034  jmp     short loc_1002703A
0x10027036  test    eax, eax
0x10027038  jnz     short loc_10027047
0x1002703a  cmp     dword ptr [ebp+Data], 1
0x1002703e  jnz     short loc_10027047
0x10027040  or      _wRmtTrace, 8
0x10027047  mov     eax, [ebp+phkResult]
0x1002704a  lea     ecx, [ebp+cbData]
0x1002704d  push    ecx; lpcbData
0x1002704e  lea     ecx, [ebp+var_C]
0x10027051  mov     [ebp+cbData], 4
0x10027058  push    ecx; lpData
0x10027059  lea     ecx, [ebp+Type]
0x1002705c  push    ecx; lpType
0x1002705d  push    0; lpReserved
0x1002705f  push    offset _szDisableAsync; "DisableAsync"
0x10027064  push    eax; hKey
0x10027065  call    ds:__imp__RegQueryValueExA@24; RegQueryValueExA(x,x,x,x,x,x)
0x1002706b  mov     ecx, [ebp+cbData]
0x1002706e  cmp     ecx, 4
0x10027071  jge     short loc_10027083
0x10027073  cmp     [ebp+Type], 1
0x10027077  jnz     short loc_10027083
0x10027079  test    eax, eax
0x1002707b  jnz     short loc_100270A3
0x1002707d  mov     [ebp+ecx+var_C], al
0x10027081  jmp     short loc_10027087
0x10027083  test    eax, eax
0x10027085  jnz     short loc_100270A3
0x10027087  mov     eax, dword ptr [ebp+var_C]
0x1002708a  cmp     eax, 1
0x1002708d  jnz     short loc_10027098
0x1002708f  or      _wRmtTrace, 10h
0x10027096  jmp     short loc_100270A3
0x10027098  test    eax, eax
0x1002709a  jnz     short loc_100270A3
0x1002709c  and     _wRmtTrace, 0FFFFFFEFh
0x100270a3  mov     eax, [ebp+phkResult]
0x100270a6  lea     ecx, [ebp+cbData]
0x100270a9  push    ecx; lpcbData
0x100270aa  lea     ecx, [ebp+var_10]
0x100270ad  mov     [ebp+cbData], 4
0x100270b4  push    ecx; lpData
0x100270b5  lea     ecx, [ebp+Type]
0x100270b8  push    ecx; lpType
0x100270b9  push    0; lpReserved
0x100270bb  push    offset _szTraceSQLMode; "TraceSQLMode"
0x100270c0  push    eax; hKey
0x100270c1  call    ds:__imp__RegQueryValueExA@24; RegQueryValueExA(x,x,x,x,x,x)
0x100270c7  mov     ecx, [ebp+cbData]
0x100270ca  cmp     ecx, 4
0x100270cd  jge     short loc_100270DD
0x100270cf  cmp     [ebp+Type], 1
0x100270d3  jnz     short loc_100270DD
0x100270d5  test    eax, eax
0x100270d7  jnz     short loc_100270DD
0x100270d9  mov     [ebp+ecx+var_10], al
0x100270dd  mov     eax, [ebp+phkResult]
0x100270e0  lea     ecx, [ebp+cbData]
0x100270e3  push    ecx; lpcbData
0x100270e4  lea     ecx, [ebp+var_14]
0x100270e7  mov     [ebp+cbData], 4
0x100270ee  push    ecx; lpData
0x100270ef  lea     ecx, [ebp+Type]
0x100270f2  push    ecx; lpType
0x100270f3  push    0; lpReserved
0x100270f5  push    offset _szSQLTraceMode; "SQLTraceMode"
0x100270fa  push    eax; hKey
0x100270fb  call    ds:__imp__RegQueryValueExA@24; RegQueryValueExA(x,x,x,x,x,x)
0x10027101  mov     ecx, [ebp+cbData]
0x10027104  cmp     ecx, 4
0x10027107  jge     short loc_10027117
0x10027109  cmp     [ebp+Type], 1
0x1002710d  jnz     short loc_10027117
0x1002710f  test    eax, eax
0x10027111  jnz     short loc_10027117
0x10027113  mov     [ebp+ecx+var_14], al
0x10027117  mov     eax, dword ptr [ebp+var_10]
0x1002711a  test    eax, eax
0x1002711c  jz      short loc_10027123
0x1002711e  mov     _wSQLTrace, eax
0x10027123  mov     eax, dword ptr [ebp+var_14]
0x10027126  test    eax, eax
0x10027128  jz      short loc_1002712F
0x1002712a  mov     _wSQLTrace, eax
0x1002712f  mov     eax, [ebp+phkResult]
0x10027132  lea     ecx, [ebp+cbData]
0x10027135  push    ecx; lpcbData
0x10027136  push    offset _wQueryTimeout; lpData
0x1002713b  lea     ecx, [ebp+Type]
0x1002713e  mov     [ebp+cbData], 4
0x10027145  push    ecx; lpType
0x10027146  push    0; lpReserved
0x10027148  push    offset _szQueryTimeout; "QueryTimeout"
0x1002714d  push    eax; hKey
0x1002714e  call    ds:__imp__RegQueryValueExA@24; RegQueryValueExA(x,x,x,x,x,x)
0x10027154  mov     ecx, [ebp+cbData]
0x10027157  cmp     ecx, 4
0x1002715a  jge     short loc_1002716C
0x1002715c  cmp     [ebp+Type], 1
0x10027160  jnz     short loc_1002716C
0x10027162  test    eax, eax
0x10027164  jnz     short loc_1002716C
0x10027166  mov     byte ptr _wQueryTimeout[ecx], al
0x1002716c  mov     eax, [ebp+phkResult]
0x1002716f  lea     ecx, [ebp+cbData]
0x10027172  push    ecx; lpcbData
0x10027173  push    offset _wLoginTimeout; lpData
0x10027178  lea     ecx, [ebp+Type]
0x1002717b  mov     [ebp+cbData], 4
0x10027182  push    ecx; lpType
0x10027183  push    0; lpReserved
0x10027185  push    offset _szLoginTimeout; "LoginTimeout"
0x1002718a  push    eax; hKey
0x1002718b  call    ds:__imp__RegQueryValueExA@24; RegQueryValueExA(x,x,x,x,x,x)
0x10027191  mov     ecx, [ebp+cbData]
0x10027194  cmp     ecx, 4
0x10027197  jge     short loc_100271A9
0x10027199  cmp     [ebp+Type], 1
0x1002719d  jnz     short loc_100271A9
0x1002719f  test    eax, eax
0x100271a1  jnz     short loc_100271A9
0x100271a3  mov     byte ptr _wLoginTimeout[ecx], al
0x100271a9  mov     eax, [ebp+phkResult]
0x100271ac  lea     ecx, [ebp+cbData]
0x100271af  push    ecx; lpcbData
0x100271b0  push    offset _wConnectionTimeout; lpData
0x100271b5  lea     ecx, [ebp+Type]
0x100271b8  mov     [ebp+cbData], 4
0x100271bf  push    ecx; lpType
0x100271c0  push    0; lpReserved
0x100271c2  push    offset _szConnectionTimeout; "ConnectionTimeout"
0x100271c7  push    eax; hKey
0x100271c8  call    ds:__imp__RegQueryValueExA@24; RegQueryValueExA(x,x,x,x,x,x)
0x100271ce  mov     ecx, [ebp+cbData]
0x100271d1  cmp     ecx, 4
0x100271d4  jge     short loc_100271E6
0x100271d6  cmp     [ebp+Type], 1
0x100271da  jnz     short loc_100271E6
0x100271dc  test    eax, eax
0x100271de  jnz     short loc_100271E6
0x100271e0  mov     byte ptr _wConnectionTimeout[ecx], al
0x100271e6  mov     eax, [ebp+phkResult]
0x100271e9  lea     ecx, [ebp+cbData]
0x100271ec  push    ecx; lpcbData
0x100271ed  push    offset _wTryJetAuth; lpData
0x100271f2  lea     ecx, [ebp+Type]
0x100271f5  mov     [ebp+cbData], 4
0x100271fc  push    ecx; lpType
0x100271fd  push    0; lpReserved
0x100271ff  push    offset _szTryJetAuth; "TryJetAuth"
0x10027204  push    eax; hKey
0x10027205  call    ds:__imp__RegQueryValueExA@24; RegQueryValueExA(x,x,x,x,x,x)
0x1002720b  mov     ecx, [ebp+cbData]
0x1002720e  cmp     ecx, 4
0x10027211  jge     short loc_10027223
0x10027213  cmp     [ebp+Type], 1
0x10027217  jnz     short loc_10027223
0x10027219  test    eax, eax
0x1002721b  jnz     short loc_10027223
0x1002721d  mov     byte ptr _wTryJetAuth[ecx], al
0x10027223  mov     eax, [ebp+phkResult]
0x10027226  lea     ecx, [ebp+cbData]
0x10027229  push    ecx; lpcbData
0x1002722a  push    offset _wFatBlastRows; lpData
0x1002722f  lea     ecx, [ebp+Type]
0x10027232  mov     [ebp+cbData], 4
0x10027239  push    ecx; lpType
0x1002723a  push    0; lpReserved
0x1002723c  push    offset _szFatBlastRows; "FatBlastRows"
0x10027241  push    eax; hKey
0x10027242  call    ds:__imp__RegQueryValueExA@24; RegQueryValueExA(x,x,x,x,x,x)
0x10027248  mov     ecx, [ebp+cbData]
0x1002724b  cmp     ecx, 4
0x1002724e  jge     short loc_10027260
0x10027250  cmp     [ebp+Type], 1
0x10027254  jnz     short loc_10027260
0x10027256  test    eax, eax
0x10027258  jnz     short loc_10027260
0x1002725a  mov     byte ptr _wFatBlastRows[ecx], al
0x10027260  mov     eax, [ebp+phkResult]
0x10027263  lea     ecx, [ebp+cbData]
0x10027266  push    ecx; lpcbData
0x10027267  push    offset _wFatBlastTimeout; lpData
0x1002726c  lea     ecx, [ebp+Type]
0x1002726f  mov     [ebp+cbData], 4
0x10027276  push    ecx; lpType
0x10027277  push    0; lpReserved
0x10027279  push    offset _szFatBlastTimeout; "FatBlastTimeout"
0x1002727e  push    eax; hKey
0x1002727f  call    ds:__imp__RegQueryValueExA@24; RegQueryValueExA(x,x,x,x,x,x)
0x10027285  mov     ecx, [ebp+cbData]
0x10027288  cmp     ecx, 4
0x1002728b  jge     short loc_1002729D
0x1002728d  cmp     [ebp+Type], 1
0x10027291  jnz     short loc_1002729D
0x10027293  test    eax, eax
0x10027295  jnz     short loc_1002729D
0x10027297  mov     byte ptr _wFatBlastTimeout[ecx], al
0x1002729d  mov     eax, [ebp+phkResult]
0x100272a0  lea     ecx, [ebp+cbData]
0x100272a3  push    ecx; lpcbData
0x100272a4  push    offset _wRetryInterval; lpData
0x100272a9  lea     ecx, [ebp+Type]
0x100272ac  mov     [ebp+cbData], 4
0x100272b3  push    ecx; lpType
0x100272b4  push    0; lpReserved
0x100272b6  push    offset _szRetryInterval; "AsyncRetryInterval"
0x100272bb  push    eax; hKey
0x100272bc  call    ds:__imp__RegQueryValueExA@24; RegQueryValueExA(x,x,x,x,x,x)
0x100272c2  mov     ecx, [ebp+cbData]
0x100272c5  cmp     ecx, 4
0x100272c8  jge     short loc_100272DA
0x100272ca  cmp     [ebp+Type], 1
0x100272ce  jnz     short loc_100272DA
0x100272d0  test    eax, eax
0x100272d2  jnz     short loc_100272DA
0x100272d4  mov     byte ptr _wRetryInterval[ecx], al
0x100272da  mov     eax, [ebp+phkResult]
0x100272dd  lea     ecx, [ebp+cbData]
0x100272e0  push    ecx; lpcbData
0x100272e1  push    offset _wAttCaseSense; lpData
0x100272e6  lea     ecx, [ebp+Type]
0x100272e9  mov     [ebp+cbData], 4
0x100272f0  push    ecx; lpType
0x100272f1  push    0; lpReserved
0x100272f3  push    offset _szAttCaseSense; "AttachCaseSensitive"
0x100272f8  push    eax; hKey
0x100272f9  call    ds:__imp__RegQueryValueExA@24; RegQueryValueExA(x,x,x,x,x,x)
0x100272ff  mov     ecx, [ebp+cbData]
0x10027302  cmp     ecx, 4
0x10027305  jge     short loc_10027317
0x10027307  cmp     [ebp+Type], 1
0x1002730b  jnz     short loc_10027317
0x1002730d  test    eax, eax
0x1002730f  jnz     short loc_10027317
0x10027311  mov     byte ptr _wAttCaseSense[ecx], al
0x10027317  mov     eax, [ebp+phkResult]
0x1002731a  lea     ecx, [ebp+cbData]
0x1002731d  push    ecx; lpcbData
0x1002731e  push    offset _wFastRequery; lpData
0x10027323  lea     ecx, [ebp+Type]
0x10027326  mov     [ebp+cbData], 4
0x1002732d  push    ecx; lpType
0x1002732e  push    0; lpReserved
0x10027330  push    offset _szFastRequery; "FastRequery"
0x10027335  push    eax; hKey
0x10027336  call    ds:__imp__RegQueryValueExA@24; RegQueryValueExA(x,x,x,x,x,x)
0x1002733c  mov     ecx, [ebp+cbData]
0x1002733f  cmp     ecx, 4
0x10027342  jge     short loc_10027354
0x10027344  cmp     [ebp+Type], 1
0x10027348  jnz     short loc_10027354
0x1002734a  test    eax, eax
0x1002734c  jnz     short loc_10027354
0x1002734e  mov     byte ptr _wFastRequery[ecx], al
0x10027354  mov     eax, [ebp+phkResult]
0x10027357  lea     ecx, [ebp+cbData]
0x1002735a  push    ecx; lpcbData
0x1002735b  push    offset _wODBCISAMAttach; lpData
0x10027360  lea     ecx, [ebp+Type]
0x10027363  mov     [ebp+cbData], 4
  ... truncated ...
```
