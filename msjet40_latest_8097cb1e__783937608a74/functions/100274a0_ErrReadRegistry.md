# ErrReadRegistry

- ea: `0x100274a0`
- end: `0x10027a89`
- name: `ErrReadRegistry`
- size: `1513`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x10027a90`

## callees

- `0x10012a80`
- `0x10026b60`
- `0x10026fb0`
- `0x100274a0`
- `0x10047304`
- `0x10123110`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x100276b6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x10027706`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x10027756`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x100277a6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x10027960`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x100279b0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x10027a00`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x10027a4e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x100276b6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x10027706`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x10027756`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x100277a6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x10027960`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x100279b0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x10027a00`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x10027a4e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1002759f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x100278b3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1002759f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x100278b3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x100277c8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x10027a70`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x100277c8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x10027a70`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1002782f`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1002782f`

## string_xrefs

- `0x100276b0`: `CompactByPKey`
- `0x1002795a`: `CompactByPKey`
- `0x10027700`: `PrevFormatCompactWithUNICODECompression`
- `0x100279aa`: `PrevFormatCompactWithUNICODECompression`

## pseudocode

```c
int __fastcall ErrReadRegistry(DWORD a1)
{
  DWORD v1; // ebx
  DWORD v2; // edi
  int v3; // eax
  const BYTE *v4; // esi
  int v5; // edx
  BYTE *v6; // ecx
  BYTE *v7; // eax
  HKEY v8; // esi
  int v9; // eax
  int v11; // ebx
  BYTE *v12; // edi
  int v13; // eax
  BYTE *v14; // edi
  LSTATUS v15; // eax
  BYTE *v16; // edi
  LSTATUS v17; // eax
  BYTE *v18; // edi
  LSTATUS v19; // eax
  BYTE *v20; // edi
  LSTATUS v21; // eax
  int v22; // edi
  _WORD *v23; // edx
  _WORD *v24; // ecx
  int v26; // ecx
  int v27; // ecx
  CHAR *v28; // eax
  int v29; // ecx
  HKEY v30; // esi
  char *v31; // ebx
  int v32; // eax
  BYTE *v33; // ebx
  LSTATUS v34; // eax
  BYTE *v35; // ebx
  LSTATUS v36; // eax
  BYTE *v37; // ebx
  LSTATUS v38; // eax
  BYTE *v39; // edi
  LSTATUS v40; // eax
  const char *v41; // [esp+0h] [ebp-268h]
  size_t v42; // [esp+4h] [ebp-264h]
  HKEY phkResult; // [esp+Ch] [ebp-25Ch] BYREF
  DWORD Type; // [esp+10h] [ebp-258h] BYREF
  DWORD v45; // [esp+14h] [ebp-254h] BYREF
  DWORD v46; // [esp+18h] [ebp-250h] BYREF
  DWORD v47; // [esp+1Ch] [ebp-24Ch] BYREF
  DWORD cbData; // [esp+20h] [ebp-248h] BYREF
  DWORD v49; // [esp+24h] [ebp-244h] BYREF
  CHAR MultiByteStr[552]; // [esp+28h] [ebp-240h] BYREF
  BYTE Data[20]; // [esp+250h] [ebp-18h] BYREF

  v1 = fOneTimeJetInitDone;
  v47 = fOneTimeJetInitDone;
  v2 = a1;
  v45 = a1;
  if ( !fOneTimeJetInitDone )
  {
    wRmtTrace = 17;
    v3 = 2147483646;
    wSQLTrace = 0;
    v4 = "'TABLE','VIEW','SYSTEM TABLE','ALIAS','SYNONYM'";
    *(_DWORD *)&wQueryTimeout = 60;
    v5 = 131;
    *(_DWORD *)&wLoginTimeout = 20;
    v6 = &szAttObj;
    *(_DWORD *)&wConnectionTimeout = 600;
    *(_DWORD *)&wTryJetAuth = 1;
    *(_DWORD *)&wFatBlastRows = -1;
    *(_DWORD *)&wFatBlastTimeout = 3;
    *(_DWORD *)&wRetryInterval = 500;
    *(_DWORD *)&wAttCaseSense = 0;
    *(_DWORD *)&wFastRequery = 0;
    *(_DWORD *)&wODBCISAMAttach = 0;
    *(_DWORD *)&wPreparedInsert = 0;
    *(_DWORD *)&wPreparedUpdate = 0;
    *(_DWORD *)&wSnapshotOnly = 0;
    do
    {
      if ( !v3 )
        break;
      if ( !*v4 )
        break;
      *v6++ = *v4++;
      --v3;
      --v5;
    }
    while ( v5 );
    v1 = v47;
    v7 = v6 - 1;
    if ( v5 )
      v7 = v6;
    *v7 = 0;
  }
  v8 = 0;
  if ( !RegOpenKeyExA(HKEY_LOCAL_MACHINE, "SOFTWARE\\Microsoft\\Jet\\4.0\\Engines", 0, 0x20019u, &phkResult) )
    v8 = phkResult;
  if ( v8 )
  {
    cbData = 20;
    v9 = JetRegQueryValueExW(v8, L"JetDisabled", 0, &Type, Data, &cbData);
    if ( (int)cbData < 20 && Type == 1 )
    {
      if ( !v9 )
      {
        Data[cbData] = 0;
        goto LABEL_17;
      }
    }
    else if ( !v9 )
    {
LABEL_17:
      if ( !WCSICMP(L"YES", Data) )
        return -5500;
    }
    if ( !v1 )
      ReadRegTree(v8);
    v11 = 2316 * v2;
    v49 = 518;
    v12 = (BYTE *)rgtib + 2316 * v2;
    v13 = JetRegQueryValueExW(v8, L"SystemDB", 0, &v46, v12, &v49);
    if ( (int)v49 < 518 && v46 == 1 && !v13 )
      v12[v49] = 0;
    cbData = 4;
    v14 = (BYTE *)rgtib + v11 + 2284;
    v15 = RegQueryValueExA(v8, "CompactByPKey", 0, &Type, v14, &cbData);
    if ( (int)cbData < 4 && Type == 1 && !v15 )
      v14[cbData] = 0;
    v49 = 4;
    v16 = (BYTE *)rgtib + v11 + 2304;
    v17 = RegQueryValueExA(v8, "PrevFormatCompactWithUNICODECompression", 0, &v46, v16, &v49);
    if ( (int)v49 < 4 && v46 == 1 && !v17 )
      v16[v49] = 0;
    cbData = 4;
    v18 = (BYTE *)rgtib + v11 + 2308;
    v19 = RegQueryValueExA(v8, "AllowQueryRemoteTables", 0, &Type, v18, &cbData);
    if ( (int)cbData < 4 && Type == 1 && !v19 )
      v18[cbData] = 0;
    v49 = 4;
    v20 = (BYTE *)rgtib + v11 + 2312;
    v21 = RegQueryValueExA(v8, "AllowQueryRemoteTables_audit", 0, &v46, v20, &v49);
    if ( (int)v49 < 4 && v46 == 1 && !v21 )
      v20[v49] = 0;
    RegCloseKey(v8);
    v2 = v45;
  }
  v22 = 2316 * v2;
  cbData = 0;
  v23 = (char *)rgtib + v22 + 520;
  if ( *v23 )
  {
    v24 = (char *)rgtib + v22 + 520;
    while ( *v24++ )
      ;
    v26 = v24 - (v23 + 1) + 1;
    if ( !v23 || !v26 )
    {
      MultiByteStr[0] = 0;
      goto LABEL_50;
    }
    if ( WideCharToMultiByte(0, 0, (LPCWCH)((char *)rgtib + v22 + 520), v26, MultiByteStr, 550, 0, 0) )
    {
LABEL_50:
      v27 = 550;
      v28 = MultiByteStr;
      do
      {
        if ( !*v28 )
          break;
        ++v28;
        --v27;
      }
      while ( v27 );
      if ( v27 )
        StringCopyWorkerA((STRSAFE_LPSTR)v27, (size_t)"\\Engines", (size_t *)v27, v41, v42);
      v29 = -2147483646;
      if ( *(_DWORD *)((char *)rgtib + v22 + 1040) )
        v29 = *(_DWORD *)((char *)rgtib + v22 + 1040);
      if ( RegOpenKeyExA((HKEY)v29, MultiByteStr, 0, 0x20019u, (PHKEY)&cbData) )
        cbData = 0;
    }
  }
  v30 = (HKEY)cbData;
  if ( cbData )
  {
    if ( !v47 )
      ReadRegTree((HKEY)cbData);
    v31 = (char *)rgtib + v22;
    v47 = 518;
    v32 = JetRegQueryValueExW(v30, L"SystemDB", 0, &v45, (LPBYTE)rgtib + v22, &v47);
    if ( (int)v47 < 518 && v45 == 1 && !v32 )
      v31[v47] = 0;
    v49 = 4;
    v33 = (BYTE *)rgtib + v22 + 2284;
    v34 = RegQueryValueExA(v30, "CompactByPKey", 0, &v46, v33, &v49);
    if ( (int)v49 < 4 && v46 == 1 && !v34 )
      v33[v49] = 0;
    v47 = 4;
    v35 = (BYTE *)rgtib + v22 + 2304;
    v36 = RegQueryValueExA(v30, "PrevFormatCompactWithUNICODECompression", 0, &v45, v35, &v47);
    if ( (int)v47 < 4 && v45 == 1 && !v36 )
      v35[v47] = 0;
    v49 = 4;
    v37 = (BYTE *)rgtib + v22 + 2308;
    v38 = RegQueryValueExA(v30, "AllowQueryRemoteTables", 0, &v46, v37, &v49);
    if ( (int)v49 < 4 && v46 == 1 && !v38 )
      v37[v49] = 0;
    v47 = 4;
    v39 = (BYTE *)rgtib + v22 + 2312;
    v40 = RegQueryValueExA(v30, "AllowQueryRemoteTables_audit", 0, &v45, v39, &v47);
    if ( (int)v47 < 4 && v45 == 1 && !v40 )
      v39[v47] = 0;
    RegCloseKey(v30);
  }
  return 0;
}

```

## disassembly

```asm
0x100274a0  mov     edi, edi
0x100274a2  push    ebp
0x100274a3  mov     ebp, esp
0x100274a5  sub     esp, 25Ch
0x100274ab  mov     eax, ___security_cookie
0x100274b0  xor     eax, ebp
0x100274b2  mov     [ebp+var_4], eax
0x100274b5  push    ebx
0x100274b6  mov     ebx, _fOneTimeJetInitDone
0x100274bc  mov     [ebp+var_24C], ebx
0x100274c2  push    esi; cchToCopy
0x100274c3  push    edi; pszSrc
0x100274c4  mov     edi, ecx
0x100274c6  mov     [ebp+var_254], edi
0x100274cc  test    ebx, ebx
0x100274ce  jnz     loc_10027587
0x100274d4  mov     _wRmtTrace, 11h
0x100274de  mov     eax, 7FFFFFFEh
0x100274e3  mov     _wSQLTrace, ebx
0x100274e9  mov     esi, offset _szDefaultAttObj; "'TABLE','VIEW','SYSTEM TABLE','ALIAS','"...
0x100274ee  mov     _wQueryTimeout, 3Ch ; '<'
0x100274f8  mov     edx, 83h
0x100274fd  mov     _wLoginTimeout, 14h
0x10027507  mov     ecx, offset _szAttObj
0x1002750c  mov     _wConnectionTimeout, 258h
0x10027516  mov     _wTryJetAuth, 1
0x10027520  mov     _wFatBlastRows, 0FFFFFFFFh
0x1002752a  mov     _wFatBlastTimeout, 3
0x10027534  mov     _wRetryInterval, 1F4h
0x1002753e  mov     _wAttCaseSense, ebx
0x10027544  mov     _wFastRequery, ebx
0x1002754a  mov     _wODBCISAMAttach, ebx
0x10027550  mov     _wPreparedInsert, ebx
0x10027556  mov     _wPreparedUpdate, ebx
0x1002755c  mov     _wSnapshotOnly, ebx
0x10027562  test    eax, eax
0x10027564  jz      short loc_10027576
0x10027566  mov     bl, [esi]
0x10027568  test    bl, bl
0x1002756a  jz      short loc_10027576
0x1002756c  mov     [ecx], bl
0x1002756e  inc     esi
0x1002756f  inc     ecx
0x10027570  dec     eax
0x10027571  sub     edx, 1
0x10027574  jnz     short loc_10027562
0x10027576  mov     ebx, [ebp+var_24C]
0x1002757c  lea     eax, [ecx-1]
0x1002757f  test    edx, edx
0x10027581  cmovnz  eax, ecx
0x10027584  mov     byte ptr [eax], 0
0x10027587  lea     eax, [ebp+phkResult]
0x1002758d  push    eax; phkResult
0x1002758e  push    20019h; samDesired
0x10027593  push    0; ulOptions
0x10027595  push    offset _szDefaultJetTree; "SOFTWARE\\Microsoft\\Jet\\4.0\\Engines"
0x1002759a  push    80000002h; hKey
0x1002759f  call    ds:__imp__RegOpenKeyExA@20; RegOpenKeyExA(x,x,x,x,x)
0x100275a5  xor     esi, esi
0x100275a7  test    eax, eax
0x100275a9  cmovz   esi, [ebp+phkResult]
0x100275b0  test    esi, esi
0x100275b2  jz      loc_100277D4
0x100275b8  lea     eax, [ebp+cbData]
0x100275be  mov     [ebp+cbData], 14h
0x100275c8  push    eax; lpcbData
0x100275c9  lea     eax, [ebp+Data]
0x100275cc  push    eax; lpData
0x100275cd  lea     eax, [ebp+Type]
0x100275d3  push    eax; lpType
0x100275d4  push    0; lpReserved
0x100275d6  push    offset _wszJetDisabledKey; "JetDisabled"
0x100275db  push    esi; hKey
0x100275dc  call    _JetRegQueryValueExW@24; JetRegQueryValueExW(x,x,x,x,x,x)
0x100275e1  mov     ecx, [ebp+cbData]
0x100275e7  cmp     ecx, 14h
0x100275ea  jge     short loc_100275FF
0x100275ec  cmp     [ebp+Type], 1
0x100275f3  jnz     short loc_100275FF
0x100275f5  test    eax, eax
0x100275f7  jnz     short loc_1002762A
0x100275f9  mov     [ebp+ecx+Data], al
0x100275fd  jmp     short loc_10027603
0x100275ff  test    eax, eax
0x10027601  jnz     short loc_1002762A
0x10027603  lea     edx, [ebp+Data]
0x10027606  mov     ecx, offset aYes; "YES"
0x1002760b  call    _WCSICMP@8; WCSICMP(x,x)
0x10027610  test    eax, eax
0x10027612  jnz     short loc_1002762A
0x10027614  mov     eax, 0FFFFEA84h
0x10027619  pop     edi
0x1002761a  pop     esi
0x1002761b  pop     ebx
0x1002761c  mov     ecx, [ebp+var_4]
0x1002761f  xor     ecx, ebp; StackCookie
0x10027621  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10027626  mov     esp, ebp
0x10027628  pop     ebp
0x10027629  retn
0x1002762a  test    ebx, ebx
0x1002762c  jnz     short loc_10027635
0x1002762e  mov     ecx, esi; hKey
0x10027630  call    ReadRegTree
0x10027635  imul    ebx, edi, 90Ch
0x1002763b  lea     eax, [ebp+var_244]
0x10027641  mov     edi, _rgtib
0x10027647  push    eax; lpcbData
0x10027648  lea     eax, [ebp+var_250]
0x1002764e  mov     [ebp+var_244], 206h
0x10027658  add     edi, ebx
0x1002765a  push    edi; lpData
0x1002765b  push    eax; lpType
0x1002765c  push    0; lpReserved
0x1002765e  push    offset _wszSystemDB; "SystemDB"
0x10027663  push    esi; hKey
0x10027664  call    _JetRegQueryValueExW@24; JetRegQueryValueExW(x,x,x,x,x,x)
0x10027669  mov     ecx, [ebp+var_244]
0x1002766f  cmp     ecx, 206h
0x10027675  jge     short loc_10027687
0x10027677  cmp     [ebp+var_250], 1
0x1002767e  jnz     short loc_10027687
0x10027680  test    eax, eax
0x10027682  jnz     short loc_10027687
0x10027684  mov     [ecx+edi], al
0x10027687  mov     edi, _rgtib
0x1002768d  lea     eax, [ebp+cbData]
0x10027693  push    eax; lpcbData
0x10027694  add     edi, 8ECh
0x1002769a  mov     [ebp+cbData], 4
0x100276a4  add     edi, ebx
0x100276a6  lea     eax, [ebp+Type]
0x100276ac  push    edi; lpData
0x100276ad  push    eax; lpType
0x100276ae  push    0; lpReserved
0x100276b0  push    offset _szCompactByPKey; "CompactByPKey"
0x100276b5  push    esi; hKey
0x100276b6  call    ds:__imp__RegQueryValueExA@24; RegQueryValueExA(x,x,x,x,x,x)
0x100276bc  mov     ecx, [ebp+cbData]
0x100276c2  cmp     ecx, 4
0x100276c5  jge     short loc_100276D7
0x100276c7  cmp     [ebp+Type], 1
0x100276ce  jnz     short loc_100276D7
0x100276d0  test    eax, eax
0x100276d2  jnz     short loc_100276D7
0x100276d4  mov     [ecx+edi], al
0x100276d7  mov     edi, _rgtib
0x100276dd  lea     eax, [ebp+var_244]
0x100276e3  push    eax; lpcbData
0x100276e4  add     edi, 900h
0x100276ea  mov     [ebp+var_244], 4
0x100276f4  add     edi, ebx
0x100276f6  lea     eax, [ebp+var_250]
0x100276fc  push    edi; lpData
0x100276fd  push    eax; lpType
0x100276fe  push    0; lpReserved
0x10027700  push    offset _szCompressOldText; "PrevFormatCompactWithUNICODECompression"
0x10027705  push    esi; hKey
0x10027706  call    ds:__imp__RegQueryValueExA@24; RegQueryValueExA(x,x,x,x,x,x)
0x1002770c  mov     ecx, [ebp+var_244]
0x10027712  cmp     ecx, 4
0x10027715  jge     short loc_10027727
0x10027717  cmp     [ebp+var_250], 1
0x1002771e  jnz     short loc_10027727
0x10027720  test    eax, eax
0x10027722  jnz     short loc_10027727
0x10027724  mov     [ecx+edi], al
0x10027727  mov     edi, _rgtib
0x1002772d  lea     eax, [ebp+cbData]
0x10027733  push    eax; lpcbData
0x10027734  add     edi, 904h
0x1002773a  mov     [ebp+cbData], 4
0x10027744  add     edi, ebx
0x10027746  lea     eax, [ebp+Type]
0x1002774c  push    edi; lpData
0x1002774d  push    eax; lpType
0x1002774e  push    0; lpReserved
0x10027750  push    offset _szAllowQueryRemoteTables; "AllowQueryRemoteTables"
0x10027755  push    esi; hKey
0x10027756  call    ds:__imp__RegQueryValueExA@24; RegQueryValueExA(x,x,x,x,x,x)
0x1002775c  mov     ecx, [ebp+cbData]
0x10027762  cmp     ecx, 4
0x10027765  jge     short loc_10027777
0x10027767  cmp     [ebp+Type], 1
0x1002776e  jnz     short loc_10027777
0x10027770  test    eax, eax
0x10027772  jnz     short loc_10027777
0x10027774  mov     [ecx+edi], al
0x10027777  mov     edi, _rgtib
0x1002777d  lea     eax, [ebp+var_244]
0x10027783  push    eax; lpcbData
0x10027784  add     edi, 908h
0x1002778a  mov     [ebp+var_244], 4
0x10027794  add     edi, ebx
0x10027796  lea     eax, [ebp+var_250]
0x1002779c  push    edi; lpData
0x1002779d  push    eax; lpType
0x1002779e  push    0; lpReserved
0x100277a0  push    offset _szAllowQueryRemoteTablesAudit; "AllowQueryRemoteTables_audit"
0x100277a5  push    esi; hKey
0x100277a6  call    ds:__imp__RegQueryValueExA@24; RegQueryValueExA(x,x,x,x,x,x)
0x100277ac  mov     ecx, [ebp+var_244]
0x100277b2  cmp     ecx, 4
0x100277b5  jge     short loc_100277C7
0x100277b7  cmp     [ebp+var_250], 1
0x100277be  jnz     short loc_100277C7
0x100277c0  test    eax, eax
0x100277c2  jnz     short loc_100277C7
0x100277c4  mov     [ecx+edi], al
0x100277c7  push    esi; hKey
0x100277c8  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x100277ce  mov     edi, [ebp+var_254]
0x100277d4  mov     edx, _rgtib
0x100277da  imul    edi, 90Ch
0x100277e0  add     edx, 208h
0x100277e6  mov     [ebp+cbData], 0
0x100277f0  add     edx, edi
0x100277f2  cmp     word ptr [edx], 0
0x100277f6  jz      loc_100278C7
0x100277fc  mov     ecx, edx
0x100277fe  lea     esi, [ecx+2]
0x10027801  mov     ax, [ecx]
0x10027804  add     ecx, 2
0x10027807  test    ax, ax
0x1002780a  jnz     short loc_10027801
0x1002780c  sub     ecx, esi
0x1002780e  sar     ecx, 1
0x10027810  inc     ecx
0x10027811  test    edx, edx
0x10027813  jz      short loc_1002783F
0x10027815  test    ecx, ecx
0x10027817  jz      short loc_1002783F
0x10027819  push    0; lpUsedDefaultChar
0x1002781b  push    0; lpDefaultChar
0x1002781d  push    226h; cbMultiByte
0x10027822  lea     eax, [ebp+MultiByteStr]
0x10027828  push    eax; lpMultiByteStr
0x10027829  push    ecx; cchWideChar
0x1002782a  push    edx; lpWideCharStr
0x1002782b  push    0; dwFlags
0x1002782d  push    0; CodePage
0x1002782f  call    ds:__imp__WideCharToMultiByte@32; WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x10027835  test    eax, eax
0x10027837  jz      loc_100278C7
0x1002783d  jmp     short loc_10027846
0x1002783f  mov     [ebp+MultiByteStr], 0
0x10027846  mov     ecx, 226h
0x1002784b  lea     eax, [ebp+MultiByteStr]
0x10027851  cmp     byte ptr [eax], 0
0x10027854  jz      short loc_1002785C
0x10027856  inc     eax
0x10027857  sub     ecx, 1
0x1002785a  jnz     short loc_10027851
0x1002785c  mov     edx, 226h
0x10027861  mov     esi, ecx
0x10027863  mov     eax, edx
0x10027865  sub     eax, ecx
0x10027867  neg     esi
0x10027869  sbb     esi, esi
0x1002786b  and     esi, eax
0x1002786d  test    ecx, ecx
0x1002786f  jz      short loc_10027887
0x10027871  push    ecx; pcchNewDestLength
0x10027872  push    offset aEngines; "\\Engines"
0x10027877  push    ecx; pszDest
0x10027878  lea     ecx, [ebp+MultiByteStr]
0x1002787e  sub     edx, esi
0x10027880  add     ecx, esi
0x10027882  call    StringCopyWorkerA
0x10027887  mov     eax, _rgtib
0x1002788c  mov     ecx, 80000002h
0x10027891  mov     eax, [edi+eax+410h]
0x10027898  test    eax, eax
0x1002789a  cmovnz  ecx, eax
0x1002789d  lea     eax, [ebp+cbData]
0x100278a3  push    eax; phkResult
0x100278a4  push    20019h; samDesired
0x100278a9  push    0; ulOptions
0x100278ab  lea     eax, [ebp+MultiByteStr]
0x100278b1  push    eax; lpSubKey
0x100278b2  push    ecx; hKey
0x100278b3  call    ds:__imp__RegOpenKeyExA@20; RegOpenKeyExA(x,x,x,x,x)
0x100278b9  test    eax, eax
0x100278bb  jz      short loc_100278C7
0x100278bd  mov     [ebp+cbData], 0
0x100278c7  mov     esi, [ebp+cbData]
0x100278cd  test    esi, esi
0x100278cf  jz      loc_10027A76
0x100278d5  cmp     [ebp+var_24C], 0
0x100278dc  jnz     short loc_100278E5
0x100278de  mov     ecx, esi; hKey
0x100278e0  call    ReadRegTree
0x100278e5  mov     ebx, _rgtib
0x100278eb  lea     eax, [ebp+var_24C]
0x100278f1  push    eax; lpcbData
0x100278f2  add     ebx, edi
0x100278f4  mov     [ebp+var_24C], 206h
0x100278fe  push    ebx; lpData
0x100278ff  lea     eax, [ebp+var_254]
0x10027905  push    eax; lpType
  ... truncated ...
```
