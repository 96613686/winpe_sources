# ReadRegTree

- ea: `0x10026e50`
- end: `0x10027335`
- name: `ReadRegTree`
- size: `1253`
- prototype: `int __thiscall(HKEY hKey)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callers

- `0x10027340`

## callees

- `0x10026e50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x10026eb8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x10026f05`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x10026f61`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x10026f9b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x10026fee`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1002702b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x10027068`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x100270a5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x100270e2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1002711f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1002715c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x10027199`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x100271d6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x10027213`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x10027250`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1002728d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x100272ca`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x10027307`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x10026eb8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x10026f05`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x10026f61`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x10026f9b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x10026fee`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1002702b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x10027068`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x100270a5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x100270e2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1002711f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1002715c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x10027199`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x100271d6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x10027213`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x10027250`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1002728d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x100272ca`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x10027307`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x10026e8c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x10026e8c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1002732b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1002732b`

## string_xrefs

- `0x10027287`: `PreparedUpdate`

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
0x10026e50  mov     edi, edi
0x10026e52  push    ebp
0x10026e53  mov     ebp, esp
0x10026e55  sub     esp, 20h
0x10026e58  lea     eax, [ebp+phkResult]
0x10026e5b  mov     dword ptr [ebp+var_10], 0
0x10026e62  push    eax; phkResult
0x10026e63  push    20019h; samDesired
0x10026e68  push    0; ulOptions
0x10026e6a  push    offset _szODBCSection; "ODBC"
0x10026e6f  push    ecx; hKey
0x10026e70  mov     dword ptr [ebp+var_14], 0
0x10026e77  mov     [ebp+phkResult], 0
0x10026e7e  mov     dword ptr [ebp+Data], 0
0x10026e85  mov     dword ptr [ebp+var_C], 1
0x10026e8c  call    ds:__imp__RegOpenKeyExA@20; RegOpenKeyExA(x,x,x,x,x)
0x10026e92  test    eax, eax
0x10026e94  jnz     loc_10027331
0x10026e9a  mov     eax, [ebp+phkResult]
0x10026e9d  lea     ecx, [ebp+cbData]
0x10026ea0  push    ecx; lpcbData
0x10026ea1  lea     ecx, [ebp+Data]
0x10026ea4  mov     [ebp+cbData], 4
0x10026eab  push    ecx; lpData
0x10026eac  lea     ecx, [ebp+Type]
0x10026eaf  push    ecx; lpType
0x10026eb0  push    0; lpReserved
0x10026eb2  push    offset _szTraceODBCAPI; "TraceODBCAPI"
0x10026eb7  push    eax; hKey
0x10026eb8  call    ds:__imp__RegQueryValueExA@24; RegQueryValueExA(x,x,x,x,x,x)
0x10026ebe  mov     ecx, [ebp+cbData]
0x10026ec1  cmp     ecx, 4
0x10026ec4  jge     short loc_10026ED6
0x10026ec6  cmp     [ebp+Type], 1
0x10026eca  jnz     short loc_10026ED6
0x10026ecc  test    eax, eax
0x10026ece  jnz     short loc_10026EE7
0x10026ed0  mov     [ebp+ecx+Data], al
0x10026ed4  jmp     short loc_10026EDA
0x10026ed6  test    eax, eax
0x10026ed8  jnz     short loc_10026EE7
0x10026eda  cmp     dword ptr [ebp+Data], 1
0x10026ede  jnz     short loc_10026EE7
0x10026ee0  or      _wRmtTrace, 8
0x10026ee7  mov     eax, [ebp+phkResult]
0x10026eea  lea     ecx, [ebp+cbData]
0x10026eed  push    ecx; lpcbData
0x10026eee  lea     ecx, [ebp+var_C]
0x10026ef1  mov     [ebp+cbData], 4
0x10026ef8  push    ecx; lpData
0x10026ef9  lea     ecx, [ebp+Type]
0x10026efc  push    ecx; lpType
0x10026efd  push    0; lpReserved
0x10026eff  push    offset _szDisableAsync; "DisableAsync"
0x10026f04  push    eax; hKey
0x10026f05  call    ds:__imp__RegQueryValueExA@24; RegQueryValueExA(x,x,x,x,x,x)
0x10026f0b  mov     ecx, [ebp+cbData]
0x10026f0e  cmp     ecx, 4
0x10026f11  jge     short loc_10026F23
0x10026f13  cmp     [ebp+Type], 1
0x10026f17  jnz     short loc_10026F23
0x10026f19  test    eax, eax
0x10026f1b  jnz     short loc_10026F43
0x10026f1d  mov     [ebp+ecx+var_C], al
0x10026f21  jmp     short loc_10026F27
0x10026f23  test    eax, eax
0x10026f25  jnz     short loc_10026F43
0x10026f27  mov     eax, dword ptr [ebp+var_C]
0x10026f2a  cmp     eax, 1
0x10026f2d  jnz     short loc_10026F38
0x10026f2f  or      _wRmtTrace, 10h
0x10026f36  jmp     short loc_10026F43
0x10026f38  test    eax, eax
0x10026f3a  jnz     short loc_10026F43
0x10026f3c  and     _wRmtTrace, 0FFFFFFEFh
0x10026f43  mov     eax, [ebp+phkResult]
0x10026f46  lea     ecx, [ebp+cbData]
0x10026f49  push    ecx; lpcbData
0x10026f4a  lea     ecx, [ebp+var_10]
0x10026f4d  mov     [ebp+cbData], 4
0x10026f54  push    ecx; lpData
0x10026f55  lea     ecx, [ebp+Type]
0x10026f58  push    ecx; lpType
0x10026f59  push    0; lpReserved
0x10026f5b  push    offset _szTraceSQLMode; "TraceSQLMode"
0x10026f60  push    eax; hKey
0x10026f61  call    ds:__imp__RegQueryValueExA@24; RegQueryValueExA(x,x,x,x,x,x)
0x10026f67  mov     ecx, [ebp+cbData]
0x10026f6a  cmp     ecx, 4
0x10026f6d  jge     short loc_10026F7D
0x10026f6f  cmp     [ebp+Type], 1
0x10026f73  jnz     short loc_10026F7D
0x10026f75  test    eax, eax
0x10026f77  jnz     short loc_10026F7D
0x10026f79  mov     [ebp+ecx+var_10], al
0x10026f7d  mov     eax, [ebp+phkResult]
0x10026f80  lea     ecx, [ebp+cbData]
0x10026f83  push    ecx; lpcbData
0x10026f84  lea     ecx, [ebp+var_14]
0x10026f87  mov     [ebp+cbData], 4
0x10026f8e  push    ecx; lpData
0x10026f8f  lea     ecx, [ebp+Type]
0x10026f92  push    ecx; lpType
0x10026f93  push    0; lpReserved
0x10026f95  push    offset _szSQLTraceMode; "SQLTraceMode"
0x10026f9a  push    eax; hKey
0x10026f9b  call    ds:__imp__RegQueryValueExA@24; RegQueryValueExA(x,x,x,x,x,x)
0x10026fa1  mov     ecx, [ebp+cbData]
0x10026fa4  cmp     ecx, 4
0x10026fa7  jge     short loc_10026FB7
0x10026fa9  cmp     [ebp+Type], 1
0x10026fad  jnz     short loc_10026FB7
0x10026faf  test    eax, eax
0x10026fb1  jnz     short loc_10026FB7
0x10026fb3  mov     [ebp+ecx+var_14], al
0x10026fb7  mov     eax, dword ptr [ebp+var_10]
0x10026fba  test    eax, eax
0x10026fbc  jz      short loc_10026FC3
0x10026fbe  mov     _wSQLTrace, eax
0x10026fc3  mov     eax, dword ptr [ebp+var_14]
0x10026fc6  test    eax, eax
0x10026fc8  jz      short loc_10026FCF
0x10026fca  mov     _wSQLTrace, eax
0x10026fcf  mov     eax, [ebp+phkResult]
0x10026fd2  lea     ecx, [ebp+cbData]
0x10026fd5  push    ecx; lpcbData
0x10026fd6  push    offset _wQueryTimeout; lpData
0x10026fdb  lea     ecx, [ebp+Type]
0x10026fde  mov     [ebp+cbData], 4
0x10026fe5  push    ecx; lpType
0x10026fe6  push    0; lpReserved
0x10026fe8  push    offset _szQueryTimeout; "QueryTimeout"
0x10026fed  push    eax; hKey
0x10026fee  call    ds:__imp__RegQueryValueExA@24; RegQueryValueExA(x,x,x,x,x,x)
0x10026ff4  mov     ecx, [ebp+cbData]
0x10026ff7  cmp     ecx, 4
0x10026ffa  jge     short loc_1002700C
0x10026ffc  cmp     [ebp+Type], 1
0x10027000  jnz     short loc_1002700C
0x10027002  test    eax, eax
0x10027004  jnz     short loc_1002700C
0x10027006  mov     byte ptr _wQueryTimeout[ecx], al
0x1002700c  mov     eax, [ebp+phkResult]
0x1002700f  lea     ecx, [ebp+cbData]
0x10027012  push    ecx; lpcbData
0x10027013  push    offset _wLoginTimeout; lpData
0x10027018  lea     ecx, [ebp+Type]
0x1002701b  mov     [ebp+cbData], 4
0x10027022  push    ecx; lpType
0x10027023  push    0; lpReserved
0x10027025  push    offset _szLoginTimeout; "LoginTimeout"
0x1002702a  push    eax; hKey
0x1002702b  call    ds:__imp__RegQueryValueExA@24; RegQueryValueExA(x,x,x,x,x,x)
0x10027031  mov     ecx, [ebp+cbData]
0x10027034  cmp     ecx, 4
0x10027037  jge     short loc_10027049
0x10027039  cmp     [ebp+Type], 1
0x1002703d  jnz     short loc_10027049
0x1002703f  test    eax, eax
0x10027041  jnz     short loc_10027049
0x10027043  mov     byte ptr _wLoginTimeout[ecx], al
0x10027049  mov     eax, [ebp+phkResult]
0x1002704c  lea     ecx, [ebp+cbData]
0x1002704f  push    ecx; lpcbData
0x10027050  push    offset _wConnectionTimeout; lpData
0x10027055  lea     ecx, [ebp+Type]
0x10027058  mov     [ebp+cbData], 4
0x1002705f  push    ecx; lpType
0x10027060  push    0; lpReserved
0x10027062  push    offset _szConnectionTimeout; "ConnectionTimeout"
0x10027067  push    eax; hKey
0x10027068  call    ds:__imp__RegQueryValueExA@24; RegQueryValueExA(x,x,x,x,x,x)
0x1002706e  mov     ecx, [ebp+cbData]
0x10027071  cmp     ecx, 4
0x10027074  jge     short loc_10027086
0x10027076  cmp     [ebp+Type], 1
0x1002707a  jnz     short loc_10027086
0x1002707c  test    eax, eax
0x1002707e  jnz     short loc_10027086
0x10027080  mov     byte ptr _wConnectionTimeout[ecx], al
0x10027086  mov     eax, [ebp+phkResult]
0x10027089  lea     ecx, [ebp+cbData]
0x1002708c  push    ecx; lpcbData
0x1002708d  push    offset _wTryJetAuth; lpData
0x10027092  lea     ecx, [ebp+Type]
0x10027095  mov     [ebp+cbData], 4
0x1002709c  push    ecx; lpType
0x1002709d  push    0; lpReserved
0x1002709f  push    offset _szTryJetAuth; "TryJetAuth"
0x100270a4  push    eax; hKey
0x100270a5  call    ds:__imp__RegQueryValueExA@24; RegQueryValueExA(x,x,x,x,x,x)
0x100270ab  mov     ecx, [ebp+cbData]
0x100270ae  cmp     ecx, 4
0x100270b1  jge     short loc_100270C3
0x100270b3  cmp     [ebp+Type], 1
0x100270b7  jnz     short loc_100270C3
0x100270b9  test    eax, eax
0x100270bb  jnz     short loc_100270C3
0x100270bd  mov     byte ptr _wTryJetAuth[ecx], al
0x100270c3  mov     eax, [ebp+phkResult]
0x100270c6  lea     ecx, [ebp+cbData]
0x100270c9  push    ecx; lpcbData
0x100270ca  push    offset _wFatBlastRows; lpData
0x100270cf  lea     ecx, [ebp+Type]
0x100270d2  mov     [ebp+cbData], 4
0x100270d9  push    ecx; lpType
0x100270da  push    0; lpReserved
0x100270dc  push    offset _szFatBlastRows; "FatBlastRows"
0x100270e1  push    eax; hKey
0x100270e2  call    ds:__imp__RegQueryValueExA@24; RegQueryValueExA(x,x,x,x,x,x)
0x100270e8  mov     ecx, [ebp+cbData]
0x100270eb  cmp     ecx, 4
0x100270ee  jge     short loc_10027100
0x100270f0  cmp     [ebp+Type], 1
0x100270f4  jnz     short loc_10027100
0x100270f6  test    eax, eax
0x100270f8  jnz     short loc_10027100
0x100270fa  mov     byte ptr _wFatBlastRows[ecx], al
0x10027100  mov     eax, [ebp+phkResult]
0x10027103  lea     ecx, [ebp+cbData]
0x10027106  push    ecx; lpcbData
0x10027107  push    offset _wFatBlastTimeout; lpData
0x1002710c  lea     ecx, [ebp+Type]
0x1002710f  mov     [ebp+cbData], 4
0x10027116  push    ecx; lpType
0x10027117  push    0; lpReserved
0x10027119  push    offset _szFatBlastTimeout; "FatBlastTimeout"
0x1002711e  push    eax; hKey
0x1002711f  call    ds:__imp__RegQueryValueExA@24; RegQueryValueExA(x,x,x,x,x,x)
0x10027125  mov     ecx, [ebp+cbData]
0x10027128  cmp     ecx, 4
0x1002712b  jge     short loc_1002713D
0x1002712d  cmp     [ebp+Type], 1
0x10027131  jnz     short loc_1002713D
0x10027133  test    eax, eax
0x10027135  jnz     short loc_1002713D
0x10027137  mov     byte ptr _wFatBlastTimeout[ecx], al
0x1002713d  mov     eax, [ebp+phkResult]
0x10027140  lea     ecx, [ebp+cbData]
0x10027143  push    ecx; lpcbData
0x10027144  push    offset _wRetryInterval; lpData
0x10027149  lea     ecx, [ebp+Type]
0x1002714c  mov     [ebp+cbData], 4
0x10027153  push    ecx; lpType
0x10027154  push    0; lpReserved
0x10027156  push    offset _szRetryInterval; "AsyncRetryInterval"
0x1002715b  push    eax; hKey
0x1002715c  call    ds:__imp__RegQueryValueExA@24; RegQueryValueExA(x,x,x,x,x,x)
0x10027162  mov     ecx, [ebp+cbData]
0x10027165  cmp     ecx, 4
0x10027168  jge     short loc_1002717A
0x1002716a  cmp     [ebp+Type], 1
0x1002716e  jnz     short loc_1002717A
0x10027170  test    eax, eax
0x10027172  jnz     short loc_1002717A
0x10027174  mov     byte ptr _wRetryInterval[ecx], al
0x1002717a  mov     eax, [ebp+phkResult]
0x1002717d  lea     ecx, [ebp+cbData]
0x10027180  push    ecx; lpcbData
0x10027181  push    offset _wAttCaseSense; lpData
0x10027186  lea     ecx, [ebp+Type]
0x10027189  mov     [ebp+cbData], 4
0x10027190  push    ecx; lpType
0x10027191  push    0; lpReserved
0x10027193  push    offset _szAttCaseSense; "AttachCaseSensitive"
0x10027198  push    eax; hKey
0x10027199  call    ds:__imp__RegQueryValueExA@24; RegQueryValueExA(x,x,x,x,x,x)
0x1002719f  mov     ecx, [ebp+cbData]
0x100271a2  cmp     ecx, 4
0x100271a5  jge     short loc_100271B7
0x100271a7  cmp     [ebp+Type], 1
0x100271ab  jnz     short loc_100271B7
0x100271ad  test    eax, eax
0x100271af  jnz     short loc_100271B7
0x100271b1  mov     byte ptr _wAttCaseSense[ecx], al
0x100271b7  mov     eax, [ebp+phkResult]
0x100271ba  lea     ecx, [ebp+cbData]
0x100271bd  push    ecx; lpcbData
0x100271be  push    offset _wFastRequery; lpData
0x100271c3  lea     ecx, [ebp+Type]
0x100271c6  mov     [ebp+cbData], 4
0x100271cd  push    ecx; lpType
0x100271ce  push    0; lpReserved
0x100271d0  push    offset _szFastRequery; "FastRequery"
0x100271d5  push    eax; hKey
0x100271d6  call    ds:__imp__RegQueryValueExA@24; RegQueryValueExA(x,x,x,x,x,x)
0x100271dc  mov     ecx, [ebp+cbData]
0x100271df  cmp     ecx, 4
0x100271e2  jge     short loc_100271F4
0x100271e4  cmp     [ebp+Type], 1
0x100271e8  jnz     short loc_100271F4
0x100271ea  test    eax, eax
0x100271ec  jnz     short loc_100271F4
0x100271ee  mov     byte ptr _wFastRequery[ecx], al
0x100271f4  mov     eax, [ebp+phkResult]
0x100271f7  lea     ecx, [ebp+cbData]
0x100271fa  push    ecx; lpcbData
0x100271fb  push    offset _wODBCISAMAttach; lpData
0x10027200  lea     ecx, [ebp+Type]
0x10027203  mov     [ebp+cbData], 4
  ... truncated ...
```
