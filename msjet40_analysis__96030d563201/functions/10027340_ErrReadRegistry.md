# ErrReadRegistry

- ea: `0x10027340`
- end: `0x10027929`
- name: `ErrReadRegistry`
- size: `1513`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x10027930`

## callees

- `0x10012940`
- `0x10026a00`
- `0x10026e50`
- `0x10027340`
- `0x10047184`
- `0x10122f60`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x10027556`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x100275a6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x100275f6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x10027646`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x10027800`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x10027850`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x100278a0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x100278ee`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x10027556`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x100275a6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x100275f6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x10027646`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x10027800`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x10027850`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x100278a0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x100278ee`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1002743f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x10027753`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1002743f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x10027753`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x10027668`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x10027910`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x10027668`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x10027910`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x100276cf`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x100276cf`

## string_xrefs

- `0x10027550`: `CompactByPKey`
- `0x100277fa`: `CompactByPKey`
- `0x100275a0`: `PrevFormatCompactWithUNICODECompression`
- `0x1002784a`: `PrevFormatCompactWithUNICODECompression`

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
0x10027340  mov     edi, edi
0x10027342  push    ebp
0x10027343  mov     ebp, esp
0x10027345  sub     esp, 25Ch
0x1002734b  mov     eax, ___security_cookie
0x10027350  xor     eax, ebp
0x10027352  mov     [ebp+var_4], eax
0x10027355  push    ebx
0x10027356  mov     ebx, _fOneTimeJetInitDone
0x1002735c  mov     [ebp+var_24C], ebx
0x10027362  push    esi; cchToCopy
0x10027363  push    edi; pszSrc
0x10027364  mov     edi, ecx
0x10027366  mov     [ebp+var_254], edi
0x1002736c  test    ebx, ebx
0x1002736e  jnz     loc_10027427
0x10027374  mov     _wRmtTrace, 11h
0x1002737e  mov     eax, 7FFFFFFEh
0x10027383  mov     _wSQLTrace, ebx
0x10027389  mov     esi, offset _szDefaultAttObj; "'TABLE','VIEW','SYSTEM TABLE','ALIAS','"...
0x1002738e  mov     _wQueryTimeout, 3Ch ; '<'
0x10027398  mov     edx, 83h
0x1002739d  mov     _wLoginTimeout, 14h
0x100273a7  mov     ecx, offset _szAttObj
0x100273ac  mov     _wConnectionTimeout, 258h
0x100273b6  mov     _wTryJetAuth, 1
0x100273c0  mov     _wFatBlastRows, 0FFFFFFFFh
0x100273ca  mov     _wFatBlastTimeout, 3
0x100273d4  mov     _wRetryInterval, 1F4h
0x100273de  mov     _wAttCaseSense, ebx
0x100273e4  mov     _wFastRequery, ebx
0x100273ea  mov     _wODBCISAMAttach, ebx
0x100273f0  mov     _wPreparedInsert, ebx
0x100273f6  mov     _wPreparedUpdate, ebx
0x100273fc  mov     _wSnapshotOnly, ebx
0x10027402  test    eax, eax
0x10027404  jz      short loc_10027416
0x10027406  mov     bl, [esi]
0x10027408  test    bl, bl
0x1002740a  jz      short loc_10027416
0x1002740c  mov     [ecx], bl
0x1002740e  inc     esi
0x1002740f  inc     ecx
0x10027410  dec     eax
0x10027411  sub     edx, 1
0x10027414  jnz     short loc_10027402
0x10027416  mov     ebx, [ebp+var_24C]
0x1002741c  lea     eax, [ecx-1]
0x1002741f  test    edx, edx
0x10027421  cmovnz  eax, ecx
0x10027424  mov     byte ptr [eax], 0
0x10027427  lea     eax, [ebp+phkResult]
0x1002742d  push    eax; phkResult
0x1002742e  push    20019h; samDesired
0x10027433  push    0; ulOptions
0x10027435  push    offset _szDefaultJetTree; "SOFTWARE\\Microsoft\\Jet\\4.0\\Engines"
0x1002743a  push    80000002h; hKey
0x1002743f  call    ds:__imp__RegOpenKeyExA@20; RegOpenKeyExA(x,x,x,x,x)
0x10027445  xor     esi, esi
0x10027447  test    eax, eax
0x10027449  cmovz   esi, [ebp+phkResult]
0x10027450  test    esi, esi
0x10027452  jz      loc_10027674
0x10027458  lea     eax, [ebp+cbData]
0x1002745e  mov     [ebp+cbData], 14h
0x10027468  push    eax; lpcbData
0x10027469  lea     eax, [ebp+Data]
0x1002746c  push    eax; lpData
0x1002746d  lea     eax, [ebp+Type]
0x10027473  push    eax; lpType
0x10027474  push    0; lpReserved
0x10027476  push    offset _wszJetDisabledKey; "JetDisabled"
0x1002747b  push    esi; hKey
0x1002747c  call    _JetRegQueryValueExW@24; JetRegQueryValueExW(x,x,x,x,x,x)
0x10027481  mov     ecx, [ebp+cbData]
0x10027487  cmp     ecx, 14h
0x1002748a  jge     short loc_1002749F
0x1002748c  cmp     [ebp+Type], 1
0x10027493  jnz     short loc_1002749F
0x10027495  test    eax, eax
0x10027497  jnz     short loc_100274CA
0x10027499  mov     [ebp+ecx+Data], al
0x1002749d  jmp     short loc_100274A3
0x1002749f  test    eax, eax
0x100274a1  jnz     short loc_100274CA
0x100274a3  lea     edx, [ebp+Data]
0x100274a6  mov     ecx, offset aYes; "YES"
0x100274ab  call    _WCSICMP@8; WCSICMP(x,x)
0x100274b0  test    eax, eax
0x100274b2  jnz     short loc_100274CA
0x100274b4  mov     eax, 0FFFFEA84h
0x100274b9  pop     edi
0x100274ba  pop     esi
0x100274bb  pop     ebx
0x100274bc  mov     ecx, [ebp+var_4]
0x100274bf  xor     ecx, ebp; StackCookie
0x100274c1  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100274c6  mov     esp, ebp
0x100274c8  pop     ebp
0x100274c9  retn
0x100274ca  test    ebx, ebx
0x100274cc  jnz     short loc_100274D5
0x100274ce  mov     ecx, esi; hKey
0x100274d0  call    ReadRegTree
0x100274d5  imul    ebx, edi, 90Ch
0x100274db  lea     eax, [ebp+var_244]
0x100274e1  mov     edi, _rgtib
0x100274e7  push    eax; lpcbData
0x100274e8  lea     eax, [ebp+var_250]
0x100274ee  mov     [ebp+var_244], 206h
0x100274f8  add     edi, ebx
0x100274fa  push    edi; lpData
0x100274fb  push    eax; lpType
0x100274fc  push    0; lpReserved
0x100274fe  push    offset _wszSystemDB; "SystemDB"
0x10027503  push    esi; hKey
0x10027504  call    _JetRegQueryValueExW@24; JetRegQueryValueExW(x,x,x,x,x,x)
0x10027509  mov     ecx, [ebp+var_244]
0x1002750f  cmp     ecx, 206h
0x10027515  jge     short loc_10027527
0x10027517  cmp     [ebp+var_250], 1
0x1002751e  jnz     short loc_10027527
0x10027520  test    eax, eax
0x10027522  jnz     short loc_10027527
0x10027524  mov     [ecx+edi], al
0x10027527  mov     edi, _rgtib
0x1002752d  lea     eax, [ebp+cbData]
0x10027533  push    eax; lpcbData
0x10027534  add     edi, 8ECh
0x1002753a  mov     [ebp+cbData], 4
0x10027544  add     edi, ebx
0x10027546  lea     eax, [ebp+Type]
0x1002754c  push    edi; lpData
0x1002754d  push    eax; lpType
0x1002754e  push    0; lpReserved
0x10027550  push    offset _szCompactByPKey; "CompactByPKey"
0x10027555  push    esi; hKey
0x10027556  call    ds:__imp__RegQueryValueExA@24; RegQueryValueExA(x,x,x,x,x,x)
0x1002755c  mov     ecx, [ebp+cbData]
0x10027562  cmp     ecx, 4
0x10027565  jge     short loc_10027577
0x10027567  cmp     [ebp+Type], 1
0x1002756e  jnz     short loc_10027577
0x10027570  test    eax, eax
0x10027572  jnz     short loc_10027577
0x10027574  mov     [ecx+edi], al
0x10027577  mov     edi, _rgtib
0x1002757d  lea     eax, [ebp+var_244]
0x10027583  push    eax; lpcbData
0x10027584  add     edi, 900h
0x1002758a  mov     [ebp+var_244], 4
0x10027594  add     edi, ebx
0x10027596  lea     eax, [ebp+var_250]
0x1002759c  push    edi; lpData
0x1002759d  push    eax; lpType
0x1002759e  push    0; lpReserved
0x100275a0  push    offset _szCompressOldText; "PrevFormatCompactWithUNICODECompression"
0x100275a5  push    esi; hKey
0x100275a6  call    ds:__imp__RegQueryValueExA@24; RegQueryValueExA(x,x,x,x,x,x)
0x100275ac  mov     ecx, [ebp+var_244]
0x100275b2  cmp     ecx, 4
0x100275b5  jge     short loc_100275C7
0x100275b7  cmp     [ebp+var_250], 1
0x100275be  jnz     short loc_100275C7
0x100275c0  test    eax, eax
0x100275c2  jnz     short loc_100275C7
0x100275c4  mov     [ecx+edi], al
0x100275c7  mov     edi, _rgtib
0x100275cd  lea     eax, [ebp+cbData]
0x100275d3  push    eax; lpcbData
0x100275d4  add     edi, 904h
0x100275da  mov     [ebp+cbData], 4
0x100275e4  add     edi, ebx
0x100275e6  lea     eax, [ebp+Type]
0x100275ec  push    edi; lpData
0x100275ed  push    eax; lpType
0x100275ee  push    0; lpReserved
0x100275f0  push    offset _szAllowQueryRemoteTables; "AllowQueryRemoteTables"
0x100275f5  push    esi; hKey
0x100275f6  call    ds:__imp__RegQueryValueExA@24; RegQueryValueExA(x,x,x,x,x,x)
0x100275fc  mov     ecx, [ebp+cbData]
0x10027602  cmp     ecx, 4
0x10027605  jge     short loc_10027617
0x10027607  cmp     [ebp+Type], 1
0x1002760e  jnz     short loc_10027617
0x10027610  test    eax, eax
0x10027612  jnz     short loc_10027617
0x10027614  mov     [ecx+edi], al
0x10027617  mov     edi, _rgtib
0x1002761d  lea     eax, [ebp+var_244]
0x10027623  push    eax; lpcbData
0x10027624  add     edi, 908h
0x1002762a  mov     [ebp+var_244], 4
0x10027634  add     edi, ebx
0x10027636  lea     eax, [ebp+var_250]
0x1002763c  push    edi; lpData
0x1002763d  push    eax; lpType
0x1002763e  push    0; lpReserved
0x10027640  push    offset _szAllowQueryRemoteTablesAudit; "AllowQueryRemoteTables_audit"
0x10027645  push    esi; hKey
0x10027646  call    ds:__imp__RegQueryValueExA@24; RegQueryValueExA(x,x,x,x,x,x)
0x1002764c  mov     ecx, [ebp+var_244]
0x10027652  cmp     ecx, 4
0x10027655  jge     short loc_10027667
0x10027657  cmp     [ebp+var_250], 1
0x1002765e  jnz     short loc_10027667
0x10027660  test    eax, eax
0x10027662  jnz     short loc_10027667
0x10027664  mov     [ecx+edi], al
0x10027667  push    esi; hKey
0x10027668  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x1002766e  mov     edi, [ebp+var_254]
0x10027674  mov     edx, _rgtib
0x1002767a  imul    edi, 90Ch
0x10027680  add     edx, 208h
0x10027686  mov     [ebp+cbData], 0
0x10027690  add     edx, edi
0x10027692  cmp     word ptr [edx], 0
0x10027696  jz      loc_10027767
0x1002769c  mov     ecx, edx
0x1002769e  lea     esi, [ecx+2]
0x100276a1  mov     ax, [ecx]
0x100276a4  add     ecx, 2
0x100276a7  test    ax, ax
0x100276aa  jnz     short loc_100276A1
0x100276ac  sub     ecx, esi
0x100276ae  sar     ecx, 1
0x100276b0  inc     ecx
0x100276b1  test    edx, edx
0x100276b3  jz      short loc_100276DF
0x100276b5  test    ecx, ecx
0x100276b7  jz      short loc_100276DF
0x100276b9  push    0; lpUsedDefaultChar
0x100276bb  push    0; lpDefaultChar
0x100276bd  push    226h; cbMultiByte
0x100276c2  lea     eax, [ebp+MultiByteStr]
0x100276c8  push    eax; lpMultiByteStr
0x100276c9  push    ecx; cchWideChar
0x100276ca  push    edx; lpWideCharStr
0x100276cb  push    0; dwFlags
0x100276cd  push    0; CodePage
0x100276cf  call    ds:__imp__WideCharToMultiByte@32; WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x100276d5  test    eax, eax
0x100276d7  jz      loc_10027767
0x100276dd  jmp     short loc_100276E6
0x100276df  mov     [ebp+MultiByteStr], 0
0x100276e6  mov     ecx, 226h
0x100276eb  lea     eax, [ebp+MultiByteStr]
0x100276f1  cmp     byte ptr [eax], 0
0x100276f4  jz      short loc_100276FC
0x100276f6  inc     eax
0x100276f7  sub     ecx, 1
0x100276fa  jnz     short loc_100276F1
0x100276fc  mov     edx, 226h
0x10027701  mov     esi, ecx
0x10027703  mov     eax, edx
0x10027705  sub     eax, ecx
0x10027707  neg     esi
0x10027709  sbb     esi, esi
0x1002770b  and     esi, eax
0x1002770d  test    ecx, ecx
0x1002770f  jz      short loc_10027727
0x10027711  push    ecx; pcchNewDestLength
0x10027712  push    offset aEngines; "\\Engines"
0x10027717  push    ecx; pszDest
0x10027718  lea     ecx, [ebp+MultiByteStr]
0x1002771e  sub     edx, esi
0x10027720  add     ecx, esi
0x10027722  call    StringCopyWorkerA
0x10027727  mov     eax, _rgtib
0x1002772c  mov     ecx, 80000002h
0x10027731  mov     eax, [edi+eax+410h]
0x10027738  test    eax, eax
0x1002773a  cmovnz  ecx, eax
0x1002773d  lea     eax, [ebp+cbData]
0x10027743  push    eax; phkResult
0x10027744  push    20019h; samDesired
0x10027749  push    0; ulOptions
0x1002774b  lea     eax, [ebp+MultiByteStr]
0x10027751  push    eax; lpSubKey
0x10027752  push    ecx; hKey
0x10027753  call    ds:__imp__RegOpenKeyExA@20; RegOpenKeyExA(x,x,x,x,x)
0x10027759  test    eax, eax
0x1002775b  jz      short loc_10027767
0x1002775d  mov     [ebp+cbData], 0
0x10027767  mov     esi, [ebp+cbData]
0x1002776d  test    esi, esi
0x1002776f  jz      loc_10027916
0x10027775  cmp     [ebp+var_24C], 0
0x1002777c  jnz     short loc_10027785
0x1002777e  mov     ecx, esi; hKey
0x10027780  call    ReadRegTree
0x10027785  mov     ebx, _rgtib
0x1002778b  lea     eax, [ebp+var_24C]
0x10027791  push    eax; lpcbData
0x10027792  add     ebx, edi
0x10027794  mov     [ebp+var_24C], 206h
0x1002779e  push    ebx; lpData
0x1002779f  lea     eax, [ebp+var_254]
0x100277a5  push    eax; lpType
  ... truncated ...
```
