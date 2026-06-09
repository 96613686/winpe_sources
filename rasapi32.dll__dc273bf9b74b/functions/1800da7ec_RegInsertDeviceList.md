# RegInsertDeviceList

- ea: `0x1800da7ec`
- end: `0x1800dbecf`
- name: `RegInsertDeviceList`
- size: `5859`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180040a68`

## callees

- `0x18000b0f4`
- `0x180015f3c`
- `0x180031b0c`
- `0x180032270`
- `0x18004e580`
- `0x1800da7ec`
- `0x1800dbed8`
- `0x1800dbefc`
- `0x1800dc1cc`
- `0x1800dc7dc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800da8c8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800dae75`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800db14e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800db1f4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800db335`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800db84a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800dbb8a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800da8c8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800dae75`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800db14e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800db1f4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800db335`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800db84a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800dbb8a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800dadfe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800db08b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800db0a5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800db817`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800dbeaf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800dadfe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800db08b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800db0a5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800db817`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800dbeaf`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800da943`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800db26a`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800db278`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800dbc1d`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800da943`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800db26a`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800db278`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800dbc1d`
- `rtutils!TracePrintfExA` at `0x1800db7ee`
- `rtutils!TracePrintfExA` at `0x1800db7ee`

## string_xrefs

- `0x1800db5c7`: `Protocol`
- `0x1800db64a`: `Compression`
- `0x1800dac6f`: `EnableCompression`
- `0x1800db750`: `MdmProtocol`

## pseudocode

```c
__int64 __fastcall RegInsertDeviceList(__int64 a1, HKEY a2, __int64 a3, __int64 a4)
{
  unsigned int v4; // r15d
  HKEY v6; // rcx
  HKEY v9; // rdi
  CHAR *v10; // rsi
  unsigned int v11; // edi
  char *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  unsigned int v15; // eax
  unsigned int v16; // eax
  char *v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // r9
  unsigned int v20; // eax
  unsigned int v21; // eax
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // eax
  unsigned int v25; // eax
  unsigned int v26; // eax
  unsigned int v27; // eax
  unsigned int v28; // eax
  unsigned int Key; // eax
  unsigned int inserted; // eax
  __int64 v31; // r8
  unsigned int v32; // eax
  __int64 v33; // r8
  unsigned int v34; // eax
  const CHAR *v35; // rax
  CHAR *v36; // rsi
  unsigned int v37; // eax
  unsigned int v38; // eax
  char *v39; // rcx
  unsigned int v40; // eax
  unsigned int v41; // eax
  unsigned int v42; // eax
  unsigned int v43; // eax
  unsigned int v44; // eax
  unsigned int v45; // eax
  unsigned int v46; // eax
  unsigned int v47; // eax
  unsigned int v48; // eax
  unsigned int v49; // eax
  unsigned int v50; // eax
  unsigned int v51; // eax
  __int64 v52; // r8
  unsigned int v53; // eax
  __int64 v54; // r8
  unsigned int v55; // eax
  __int64 v56; // r8
  unsigned int v57; // eax
  const WCHAR *v58; // rsi
  unsigned int v59; // eax
  const WCHAR *v60; // rax
  BOOL v61; // r15d
  const CHAR *v62; // rax
  CHAR *v63; // r12
  unsigned int v64; // eax
  unsigned int v65; // eax
  unsigned int v66; // eax
  unsigned int v67; // eax
  unsigned int v68; // eax
  HKEY hKey[2]; // [rsp+50h] [rbp-10h] BYREF
  char v72; // [rsp+B8h] [rbp+58h]

  v4 = *(_DWORD *)(a4 + 40);
  v6 = 0;
  hKey[0] = 0;
  v9 = a2;
  if ( v4 != 6 )
  {
    v28 = *(_DWORD *)(a4 + 48);
    v72 = v28;
    if ( v4 != 2 )
    {
      if ( v4 - 10 > 8 )
      {
        if ( !*(_DWORD *)(a4 + 92) )
        {
          v11 = 0;
          if ( !*(_DWORD *)(a4 + 88) )
            goto LABEL_148;
          v9 = a2;
        }
        Key = RegCreateKeyExA(v9, "switch", 0, 0, 0, 0x20206u, 0, hKey, 0);
        v11 = Key;
        if ( Key )
        {
          v12 = (char *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
            return v11;
          if ( *((char *)WPP_GLOBAL_Control + 28) < 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, Key);
            v12 = (char *)WPP_GLOBAL_Control;
          }
          if ( v12 == (char *)&WPP_GLOBAL_Control || v12[28] >= 0 || (unsigned __int8)v12[25] < 6u )
            return v11;
          v13 = 88;
          goto LABEL_19;
        }
        if ( *(_DWORD *)(a4 + 92) )
        {
          inserted = RegInsertString(hKey[0], "Name", *(_QWORD *)(a4 + 96));
          v11 = inserted;
          if ( inserted )
          {
            v17 = (char *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
              goto LABEL_396;
            if ( *((char *)WPP_GLOBAL_Control + 28) < 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                89,
                WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids,
                inserted);
              v17 = (char *)WPP_GLOBAL_Control;
            }
            if ( v17 == (char *)&WPP_GLOBAL_Control || v17[28] >= 0 || (unsigned __int8)v17[25] < 6u )
              goto LABEL_396;
            v18 = 90;
            goto LABEL_29;
          }
        }
        v31 = *(unsigned int *)(a4 + 88);
        if ( (_DWORD)v31 )
        {
          v32 = RegInsertFlag(hKey[0], "Terminal", v31);
          v11 = v32;
          if ( v32 )
          {
            v17 = (char *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
              goto LABEL_396;
            if ( *((char *)WPP_GLOBAL_Control + 28) < 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 91, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, v32);
              v17 = (char *)WPP_GLOBAL_Control;
            }
            if ( v17 == (char *)&WPP_GLOBAL_Control || v17[28] >= 0 || (unsigned __int8)v17[25] < 6u )
              goto LABEL_396;
            v18 = 92;
            goto LABEL_29;
          }
        }
        v33 = *(unsigned int *)(a4 + 92);
        if ( (_DWORD)v33 )
        {
          v34 = RegInsertFlag(hKey[0], "Script", v33);
          v11 = v34;
          if ( v34 )
          {
            v17 = (char *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
              goto LABEL_396;
            if ( *((char *)WPP_GLOBAL_Control + 28) < 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 93, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, v34);
              v17 = (char *)WPP_GLOBAL_Control;
            }
            if ( v17 == (char *)&WPP_GLOBAL_Control || v17[28] >= 0 || (unsigned __int8)v17[25] < 6u )
              goto LABEL_396;
            v18 = 94;
            goto LABEL_29;
          }
        }
        v6 = hKey[0];
LABEL_148:
        RegCloseKey(v6);
        if ( v4 == 1 )
        {
          if ( (v72 & 4) != 0 )
            goto LABEL_150;
        }
        else if ( v4 != 8 )
        {
LABEL_150:
          RegCloseKey(hKey[0]);
          if ( v4 != 3 && (v72 & 4) == 0 )
          {
LABEL_270:
            if ( v4 == 4 && g_dwTraceId != -1 )
              TracePrintfExA(
                g_dwTraceId,
                0xCu,
                "RegInsertDeviceList - (type == PBDT_Pad) || type == PBDT_Modem && ppbentry->pszX25Network). Ignoring");
            if ( !*(_DWORD *)(a3 + 216) && !*(_DWORD *)(a3 + 212) && !*(_DWORD *)(a3 + 232) )
              goto LABEL_391;
            RegCloseKey(hKey[0]);
            v50 = RegCreateKeyExA(a2, "switch", 0, 0, 0, 0x20206u, 0, hKey, 0);
            v11 = v50;
            if ( v50 )
            {
              v12 = (char *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
                return v11;
              if ( *((char *)WPP_GLOBAL_Control + 28) < 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 120, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, v50);
                v12 = (char *)WPP_GLOBAL_Control;
              }
              if ( v12 == (char *)&WPP_GLOBAL_Control || v12[28] >= 0 || (unsigned __int8)v12[25] < 6u )
                return v11;
              v13 = 121;
              goto LABEL_19;
            }
            if ( *(_DWORD *)(a3 + 216)
              && (v51 = RegInsertString(hKey[0], "Name", *(_QWORD *)(a3 + 224)), (v11 = v51) != 0) )
            {
              v17 = (char *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
                goto LABEL_396;
              if ( *((char *)WPP_GLOBAL_Control + 28) < 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 122, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, v51);
                v17 = (char *)WPP_GLOBAL_Control;
              }
              if ( v17 == (char *)&WPP_GLOBAL_Control || v17[28] >= 0 || (unsigned __int8)v17[25] < 6u )
                goto LABEL_396;
              v18 = 123;
            }
            else
            {
              v52 = *(unsigned int *)(a3 + 212);
              if ( (_DWORD)v52 && (v53 = RegInsertFlag(hKey[0], "Terminal", v52), (v11 = v53) != 0) )
              {
                v17 = (char *)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
                  goto LABEL_396;
                if ( *((char *)WPP_GLOBAL_Control + 28) < 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    124,
                    WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids,
                    v53);
                  v17 = (char *)WPP_GLOBAL_Control;
                }
                if ( v17 == (char *)&WPP_GLOBAL_Control || v17[28] >= 0 || (unsigned __int8)v17[25] < 6u )
                  goto LABEL_396;
                v18 = 125;
              }
              else
              {
                v54 = *(unsigned int *)(a3 + 216);
                if ( (_DWORD)v54 )
                {
                  v55 = RegInsertFlag(hKey[0], "Script", v54);
                  v11 = v55;
                  if ( v55 )
                  {
                    v17 = (char *)WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                      || *((char *)WPP_GLOBAL_Control + 28) >= 0
                      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 6u )
                    {
                      goto LABEL_396;
                    }
                    v18 = 126;
                    v19 = v55;
                    goto LABEL_395;
                  }
                }
                v56 = *(unsigned int *)(a3 + 232);
                if ( !(_DWORD)v56 )
                  goto LABEL_391;
                v57 = RegInsertLong(hKey[0], "CustomScript", v56);
                v11 = v57;
                if ( !v57 )
                  goto LABEL_391;
                v17 = (char *)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
                  goto LABEL_396;
                if ( *((char *)WPP_GLOBAL_Control + 28) < 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    127,
                    WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids,
                    v57);
                  v17 = (char *)WPP_GLOBAL_Control;
                }
                if ( v17 == (char *)&WPP_GLOBAL_Control || v17[28] >= 0 || (unsigned __int8)v17[25] < 6u )
                  goto LABEL_396;
                v18 = 128;
              }
            }
LABEL_29:
            v19 = v11;
            goto LABEL_395;
          }
          if ( (*(_DWORD *)(a1 + 32) & 0x400) != 0 )
          {
            v35 = (const CHAR *)StrdupWtoA(*(LPCWCH *)(a4 + 32));
            v36 = (CHAR *)v35;
            if ( !v35 )
            {
              v11 = 8;
              v17 = (char *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                || *((char *)WPP_GLOBAL_Control + 28) >= 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_396;
              }
              v18 = 97;
              goto LABEL_158;
            }
            v38 = RegCreateKeyExA(a2, v35, 0, 0, 0, 0x20206u, 0, hKey, 0);
            v11 = v38;
            if ( v38 )
            {
              v39 = (char *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
              {
                if ( *((char *)WPP_GLOBAL_Control + 28) < 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    98,
                    WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids,
                    v38);
                  v39 = (char *)WPP_GLOBAL_Control;
                }
                if ( v39 != (char *)&WPP_GLOBAL_Control && v39[28] < 0 && (unsigned __int8)v39[25] >= 6u )
                  WPP_SF_d(*((_QWORD *)v39 + 2), 99, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, v11);
              }
              GlobalFree(v36);
              return v11;
            }
            GlobalFree(v36);
LABEL_180:
            v40 = RegInsertPhoneList(hKey[0]);
            v11 = v40;
            if ( v40 )
            {
              v17 = (char *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
                goto LABEL_396;
              if ( *((char *)WPP_GLOBAL_Control + 28) < 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 102, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, v40);
                v17 = (char *)WPP_GLOBAL_Control;
              }
              if ( v17 == (char *)&WPP_GLOBAL_Control || v17[28] >= 0 || (unsigned __int8)v17[25] < 6u )
                goto LABEL_396;
              v18 = 103;
              goto LABEL_29;
            }
            v42 = RegInsertLong(hKey[0], "LastSelectedPhone", *(unsigned int *)(a4 + 176));
            v11 = v42;
            if ( v42 )
            {
              v17 = (char *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
                goto LABEL_396;
              if ( *((char *)WPP_GLOBAL_Control + 28) < 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 104, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, v42);
                v17 = (char *)WPP_GLOBAL_Control;
              }
              if ( v17 == (char *)&WPP_GLOBAL_Control || v17[28] >= 0 || (unsigned __int8)v17[25] < 6u )
                goto LABEL_396;
              v18 = 105;
              goto LABEL_29;
            }
            v43 = RegInsertFlag(hKey[0], "PromoteAlternates", *(unsigned int *)(a4 + 180));
            v11 = v43;
            if ( v43 )
            {
              v17 = (char *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
                goto LABEL_396;
              if ( *((char *)WPP_GLOBAL_Control + 28) < 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 106, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, v43);
                v17 = (char *)WPP_GLOBAL_Control;
              }
              if ( v17 == (char *)&WPP_GLOBAL_Control || v17[28] >= 0 || (unsigned __int8)v17[25] < 6u )
                goto LABEL_396;
              v18 = 107;
              goto LABEL_29;
            }
            v44 = RegInsertFlag(hKey[0], "TryNextAlternateOnFail", *(unsigned int *)(a4 + 184));
            v11 = v44;
            if ( v44 )
            {
              v17 = (char *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
                goto LABEL_396;
              if ( *((char *)WPP_GLOBAL_Control + 28) < 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 108, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, v44);
                v17 = (char *)WPP_GLOBAL_Control;
              }
              if ( v17 == (char *)&WPP_GLOBAL_Control || v17[28] >= 0 || (unsigned __int8)v17[25] < 6u )
                goto LABEL_396;
              v18 = 109;
              goto LABEL_29;
            }
            v45 = RegInsertFlag(hKey[0], "HwFlowControl", *(unsigned int *)(a4 + 108));
            v11 = v45;
            if ( v45 )
            {
              v17 = (char *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
                goto LABEL_396;
              if ( *((char *)WPP_GLOBAL_Control + 28) < 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 110, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, v45);
                v17 = (char *)WPP_GLOBAL_Control;
              }
              if ( v17 == (char *)&WPP_GLOBAL_Control || v17[28] >= 0 || (unsigned __int8)v17[25] < 6u )
                goto LABEL_396;
              v18 = 111;
              goto LABEL_29;
            }
            v46 = RegInsertFlag(hKey[0], "Protocol", *(unsigned int *)(a4 + 112));
            v11 = v46;
            if ( v46 )
            {
              v17 = (char *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
                goto LABEL_396;
              if ( *((char *)WPP_GLOBAL_Control + 28) < 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 112, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, v46);
                v17 = (char *)WPP_GLOBAL_Control;
              }
              if ( v17 == (char *)&WPP_GLOBAL_Control || v17[28] >= 0 || (unsigned __int8)v17[25] < 6u )
                goto LABEL_396;
              v18 = 113;
              goto LABEL_29;
            }
            v47 = RegInsertFlag(hKey[0], "Compression", *(unsigned int *)(a4 + 116));
            v11 = v47;
            if ( v47 )
            {
              v17 = (char *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
                goto LABEL_396;
              if ( *((char *)WPP_GLOBAL_Control + 28) < 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 114, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, v47);
                v17 = (char *)WPP_GLOBAL_Control;
              }
              if ( v17 == (char *)&WPP_GLOBAL_Control || v17[28] >= 0 || (unsigned __int8)v17[25] < 6u )
                goto LABEL_396;
              v18 = 115;
              goto LABEL_29;
            }
            v48 = RegInsertFlag(hKey[0], "Speaker", *(unsigned int *)(a4 + 120));
            v11 = v48;
            if ( v48 )
            {
              v17 = (char *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
                goto LABEL_396;
              if ( *((char *)WPP_GLOBAL_Control + 28) < 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 116, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, v48);
                v17 = (char *)WPP_GLOBAL_Control;
              }
              if ( v17 == (char *)&WPP_GLOBAL_Control || v17[28] >= 0 || (unsigned __int8)v17[25] < 6u )
                goto LABEL_396;
              v18 = 117;
              goto LABEL_29;
            }
            v49 = RegInsertLong(hKey[0], "MdmProtocol", *(unsigned int *)(a4 + 124));
            v11 = v49;
            if ( v49 )
            {
              v17 = (char *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
                goto LABEL_396;
              if ( *((char *)WPP_GLOBAL_Control + 28) < 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 118, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, v49);
                v17 = (char *)WPP_GLOBAL_Control;
              }
              if ( v17 == (char *)&WPP_GLOBAL_Control || v17[28] >= 0 || (unsigned __int8)v17[25] < 6u )
                goto LABEL_396;
              v18 = 119;
              goto LABEL_29;
            }
            goto LABEL_270;
          }
          v41 = RegCreateKeyExA(a2, "modem", 0, 0, 0, 0x20206u, 0, hKey, 0);
          v11 = v41;
          if ( !v41 )
            goto LABEL_180;
          v12 = (char *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
            return v11;
          if ( *((char *)WPP_GLOBAL_Control + 28) < 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 100, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, v41);
            v12 = (char *)WPP_GLOBAL_Control;
          }
          if ( v12 == (char *)&WPP_GLOBAL_Control || v12[28] >= 0 || (unsigned __int8)v12[25] < 6u )
            return v11;
          v13 = 101;
LABEL_19:
          v14 = v11;
          goto LABEL_8;
        }
        v37 = RegCreateKeyExA(a2, "switch", 0, 0, 0, 0x20206u, 0, hKey, 0);
        v11 = v37;
        if ( v37 )
        {
          v12 = (char *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
            return v11;
          if ( *((char *)WPP_GLOBAL_Control + 28) < 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 95, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, v37);
            v12 = (char *)WPP_GLOBAL_Control;
          }
          if ( v12 == (char *)&WPP_GLOBAL_Control || v12[28] >= 0 || (unsigned __int8)v12[25] < 6u )
            return v11;
          v13 = 96;
          goto LABEL_19;
        }
        goto LABEL_150;
      }
      v28 = *(_DWORD *)(a4 + 48);
    }
    if ( (*(_DWORD *)(a1 + 32) & 0x400) != 0 )
    {
      v58 = *(const WCHAR **)(a4 + 32);
      v61 = 0;
    }
    else
    {
      v58 = 0;
      if ( *(_QWORD *)(a1 + 24) < 6u )
      {
        v59 = RdtFromPbdt(v4, v28);
        v58 = (const WCHAR *)pszDeviceTypeFromRdt(v59);
      }
      v60 = v58;
      if ( !v58 )
        v58 = *(const WCHAR **)(a4 + 24);
      v61 = v60 != 0;
    }
    v62 = (const CHAR *)StrdupWtoA(v58);
    v63 = (CHAR *)v62;
    if ( !v62 )
    {
      v11 = 8;
      v17 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || *((char *)WPP_GLOBAL_Control + 28) >= 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_396;
      }
      v18 = 76;
LABEL_158:
      v19 = 8;
      goto LABEL_395;
    }
    v64 = RegCreateKeyExA(v9, v62, 0, 0, 0, 0x20206u, 0, hKey, 0);
    v11 = v64;
    if ( !v64 )
    {
      GlobalFree(v63);
      v65 = RegInsertPhoneList(hKey[0]);
      v11 = v65;
      if ( v65 )
      {
        v17 = (char *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((char *)WPP_GLOBAL_Control + 28) < 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, v65);
          v17 = (char *)WPP_GLOBAL_Control;
        }
        if ( v61 )
        {
          Free0(v58);
          v17 = (char *)WPP_GLOBAL_Control;
        }
        if ( v17 == (char *)&WPP_GLOBAL_Control || v17[28] >= 0 || (unsigned __int8)v17[25] < 6u )
          goto LABEL_396;
        v18 = 80;
      }
      else
      {
        v66 = RegInsertLong(hKey[0], "LastSelectedPhone", *(unsigned int *)(a4 + 176));
        v11 = v66;
        if ( v66 )
        {
          v17 = (char *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && *((char *)WPP_GLOBAL_Control + 28) < 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 81, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, v66);
            v17 = (char *)WPP_GLOBAL_Control;
          }
          if ( v61 )
          {
            Free0(v58);
            v17 = (char *)WPP_GLOBAL_Control;
          }
          if ( v17 == (char *)&WPP_GLOBAL_Control || v17[28] >= 0 || (unsigned __int8)v17[25] < 6u )
            goto LABEL_396;
          v18 = 82;
        }
        else
        {
          v67 = RegInsertFlag(hKey[0], "PromoteAlternates", *(unsigned int *)(a4 + 180));
          v11 = v67;
          if ( v67 )
          {
            v17 = (char *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && *((char *)WPP_GLOBAL_Control + 28) < 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, v67);
              v17 = (char *)WPP_GLOBAL_Control;
            }
            if ( v61 )
            {
              Free0(v58);
              v17 = (char *)WPP_GLOBAL_Control;
            }
            if ( v17 == (char *)&WPP_GLOBAL_Control || v17[28] >= 0 || (unsigned __int8)v17[25] < 6u )
              goto LABEL_396;
            v18 = 84;
          }
          else
          {
            v68 = RegInsertFlag(hKey[0], "TryNextAlternateOnFail", *(unsigned int *)(a4 + 184));
            v11 = v68;
            if ( !v68 )
            {
              if ( v61 )
                Free0(v58);
              goto LABEL_391;
            }
            v17 = (char *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && *((char *)WPP_GLOBAL_Control + 28) < 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 85, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, v68);
              v17 = (char *)WPP_GLOBAL_Control;
            }
            if ( v61 )
            {
              Free0(v58);
              v17 = (char *)WPP_GLOBAL_Control;
            }
            if ( v17 == (char *)&WPP_GLOBAL_Control || v17[28] >= 0 || (unsigned __int8)v17[25] < 6u )
              goto LABEL_396;
            v18 = 86;
          }
        }
      }
      goto LABEL_29;
    }
    v12 = (char *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, v64);
      v12 = (char *)WPP_GLOBAL_Control;
    }
    if ( v61 )
    {
      Free0(v58);
      Free0(v63);
      v12 = (char *)WPP_GLOBAL_Control;
    }
    if ( v12 == (char *)&WPP_GLOBAL_Control || v12[28] >= 0 || (unsigned __int8)v12[25] < 6u )
      return v11;
    v13 = 78;
    goto LABEL_19;
  }
  if ( (*(_DWORD *)(a1 + 32) & 0x400) == 0 )
  {
    v10 = (CHAR *)"isdn";
    goto LABEL_10;
  }
  v10 = (CHAR *)StrdupWtoA(*(LPCWCH *)(a4 + 32));
  if ( v10 )
  {
LABEL_10:
    v15 = RegCreateKeyExA(v9, v10, 0, 0, 0, 0x20206u, 0, hKey, 0);
    v11 = v15;
    if ( v15 )
    {
      v12 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v11;
      if ( *((char *)WPP_GLOBAL_Control + 28) < 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, v15);
        v12 = (char *)WPP_GLOBAL_Control;
      }
      if ( v12 == (char *)&WPP_GLOBAL_Control || v12[28] >= 0 || (unsigned __int8)v12[25] < 6u )
        return v11;
      v13 = 57;
      goto LABEL_19;
    }
    GlobalFree(v10);
    v16 = RegInsertPhoneList(hKey[0]);
    v11 = v16;
    if ( v16 )
    {
      v17 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_396;
      if ( *((char *)WPP_GLOBAL_Control + 28) < 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, v16);
        v17 = (char *)WPP_GLOBAL_Control;
      }
      if ( v17 == (char *)&WPP_GLOBAL_Control || v17[28] >= 0 || (unsigned __int8)v17[25] < 6u )
        goto LABEL_396;
      v18 = 59;
      goto LABEL_29;
    }
    v20 = RegInsertLong(hKey[0], "LastSelectedPhone", *(unsigned int *)(a4 + 176));
    v11 = v20;
    if ( v20 )
    {
      v17 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_396;
      if ( *((char *)WPP_GLOBAL_Control + 28) < 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, v20);
        v17 = (char *)WPP_GLOBAL_Control;
      }
      if ( v17 == (char *)&WPP_GLOBAL_Control || v17[28] >= 0 || (unsigned __int8)v17[25] < 6u )
        goto LABEL_396;
      v18 = 61;
      goto LABEL_29;
    }
    v21 = RegInsertFlag(hKey[0], "PromoteAlternates", *(unsigned int *)(a4 + 180));
    v11 = v21;
    if ( v21 )
    {
      v17 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_396;
      if ( *((char *)WPP_GLOBAL_Control + 28) < 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, v21);
        v17 = (char *)WPP_GLOBAL_Control;
      }
      if ( v17 == (char *)&WPP_GLOBAL_Control || v17[28] >= 0 || (unsigned __int8)v17[25] < 6u )
        goto LABEL_396;
      v18 = 63;
      goto LABEL_29;
    }
    v22 = RegInsertFlag(hKey[0], "TryNextAlternateOnFail", *(unsigned int *)(a4 + 184));
    v11 = v22;
    if ( v22 )
    {
      v17 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_396;
      if ( *((char *)WPP_GLOBAL_Control + 28) < 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, v22);
        v17 = (char *)WPP_GLOBAL_Control;
      }
      if ( v17 == (char *)&WPP_GLOBAL_Control || v17[28] >= 0 || (unsigned __int8)v17[25] < 6u )
        goto LABEL_396;
      v18 = 65;
      goto LABEL_29;
    }
    v23 = RegInsertLong(hKey[0], "LineType", *(unsigned int *)(a4 + 132));
    v11 = v23;
    if ( v23 )
    {
      v17 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_396;
      if ( *((char *)WPP_GLOBAL_Control + 28) < 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, v23);
        v17 = (char *)WPP_GLOBAL_Control;
      }
      if ( v17 == (char *)&WPP_GLOBAL_Control || v17[28] >= 0 || (unsigned __int8)v17[25] < 6u )
        goto LABEL_396;
      v18 = 67;
      goto LABEL_29;
    }
    v24 = RegInsertFlag(hKey[0], "Fallback", *(unsigned int *)(a4 + 136));
    v11 = v24;
    if ( v24 )
    {
      v17 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_396;
      if ( *((char *)WPP_GLOBAL_Control + 28) < 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, v24);
        v17 = (char *)WPP_GLOBAL_Control;
      }
      if ( v17 == (char *)&WPP_GLOBAL_Control || v17[28] >= 0 || (unsigned __int8)v17[25] < 6u )
        goto LABEL_396;
      v18 = 69;
      goto LABEL_29;
    }
    v25 = RegInsertFlag(hKey[0], "EnableCompression", *(unsigned int *)(a4 + 140));
    v11 = v25;
    if ( v25 )
    {
      v17 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_396;
      if ( *((char *)WPP_GLOBAL_Control + 28) < 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, v25);
        v17 = (char *)WPP_GLOBAL_Control;
      }
      if ( v17 == (char *)&WPP_GLOBAL_Control || v17[28] >= 0 || (unsigned __int8)v17[25] < 6u )
        goto LABEL_396;
      v18 = 71;
      goto LABEL_29;
    }
    v26 = RegInsertLong(hKey[0], "ChannelAggregation", *(unsigned int *)(a4 + 144));
    v11 = v26;
    if ( v26 )
    {
      v17 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_396;
      if ( *((char *)WPP_GLOBAL_Control + 28) < 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, v26);
        v17 = (char *)WPP_GLOBAL_Control;
      }
      if ( v17 == (char *)&WPP_GLOBAL_Control || v17[28] >= 0 || (unsigned __int8)v17[25] < 6u )
        goto LABEL_396;
      v18 = 73;
      goto LABEL_29;
    }
    v27 = RegInsertFlag(hKey[0], "Proprietary", *(unsigned int *)(a4 + 128));
    v11 = v27;
    if ( v27 )
    {
      v17 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_396;
      if ( *((char *)WPP_GLOBAL_Control + 28) < 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, v27);
        v17 = (char *)WPP_GLOBAL_Control;
      }
      if ( v17 == (char *)&WPP_GLOBAL_Control || v17[28] >= 0 || (unsigned __int8)v17[25] < 6u )
        goto LABEL_396;
      v18 = 75;
      goto LABEL_29;
    }
    RegCloseKey(hKey[0]);
LABEL_391:
    v17 = (char *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || *((char *)WPP_GLOBAL_Control + 28) >= 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 6u )
    {
      goto LABEL_396;
    }
    v18 = 129;
    v19 = 0;
LABEL_395:
    WPP_SF_d(*((_QWORD *)v17 + 2), v18, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, v19);
LABEL_396:
    RegCloseKey(hKey[0]);
    return v11;
  }
  v11 = 8;
  v12 = (char *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v13 = 55;
    v14 = 8;
LABEL_8:
    WPP_SF_d(*((_QWORD *)v12 + 2), v13, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, v14);
  }
  return v11;
}

```

## disassembly

```asm
0x1800da7ec  mov     [rsp-38h+arg_0], rbx
0x1800da7f1  mov     [rsp-38h+arg_8], rdx
0x1800da7f6  push    rbp
0x1800da7f7  push    rsi
0x1800da7f8  push    rdi
0x1800da7f9  push    r12
0x1800da7fb  push    r13
0x1800da7fd  push    r14
0x1800da7ff  push    r15
0x1800da801  mov     rbp, rsp
0x1800da804  sub     rsp, 60h
0x1800da808  mov     r15d, [r9+28h]
0x1800da80c  xor     r14d, r14d
0x1800da80f  mov     r12, rcx
0x1800da812  mov     ecx, r14d
0x1800da815  mov     [rbp+hKey], rcx
0x1800da819  mov     rbx, r9
0x1800da81c  mov     r13, r8
0x1800da81f  mov     rdi, rdx
0x1800da822  cmp     r15d, 6
0x1800da826  jnz     loc_1800DAE09
0x1800da82c  test    dword ptr [r12+20h], 400h
0x1800da835  jz      short loc_1800DA895
0x1800da837  mov     rcx, [r9+20h]; lpWideCharStr
0x1800da83b  call    _StrdupWtoA
0x1800da840  mov     rsi, rax
0x1800da843  test    rax, rax
0x1800da846  jnz     short loc_1800DA89C
0x1800da848  lea     r14d, [r15+2]
0x1800da84c  mov     edi, r14d
0x1800da84f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800da856  lea     rbx, WPP_GLOBAL_Control
0x1800da85d  cmp     rcx, rbx
0x1800da860  jz      loc_1800DBEB5
0x1800da866  test    byte ptr [rcx+1Ch], 80h
0x1800da86a  jz      loc_1800DBEB5
0x1800da870  cmp     byte ptr [rcx+19h], 2
0x1800da874  jb      loc_1800DBEB5
0x1800da87a  lea     edx, [rax+37h]
0x1800da87d  mov     r9d, r14d
0x1800da880  mov     rcx, [rcx+10h]
0x1800da884  lea     r8, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids
0x1800da88b  call    WPP_SF_d
0x1800da890  jmp     loc_1800DBEB5
0x1800da895  lea     rsi, String1; "isdn"
0x1800da89c  mov     [rsp+60h+lpdwDisposition], r14; lpdwDisposition
0x1800da8a1  lea     rax, [rbp+hKey]
0x1800da8a5  mov     [rsp+60h+phkResult], rax; phkResult
0x1800da8aa  xor     r9d, r9d; lpClass
0x1800da8ad  mov     [rsp+60h+lpSecurityAttributes], r14; lpSecurityAttributes
0x1800da8b2  xor     r8d, r8d; Reserved
0x1800da8b5  mov     [rsp+60h+samDesired], 20206h; samDesired
0x1800da8bd  mov     rdx, rsi; lpSubKey
0x1800da8c0  mov     rcx, rdi; hKey
0x1800da8c3  mov     [rsp+60h+dwOptions], r14d; dwOptions
0x1800da8c8  call    cs:__imp_RegCreateKeyExA
0x1800da8ce  mov     edi, eax
0x1800da8d0  test    eax, eax
0x1800da8d2  jz      short loc_1800DA940
0x1800da8d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800da8db  lea     rbx, WPP_GLOBAL_Control
0x1800da8e2  cmp     rcx, rbx
0x1800da8e5  jz      loc_1800DBEB5
0x1800da8eb  test    byte ptr [rcx+1Ch], 80h
0x1800da8ef  jz      short loc_1800DA916
0x1800da8f1  cmp     byte ptr [rcx+19h], 2
0x1800da8f5  jb      short loc_1800DA916
0x1800da8f7  mov     rcx, [rcx+10h]
0x1800da8fb  lea     r8, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids
0x1800da902  mov     edx, 38h ; '8'
0x1800da907  mov     r9d, eax
0x1800da90a  call    WPP_SF_d
0x1800da90f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800da916  cmp     rcx, rbx
0x1800da919  jz      loc_1800DBEB5
0x1800da91f  test    byte ptr [rcx+1Ch], 80h
0x1800da923  jz      loc_1800DBEB5
0x1800da929  cmp     byte ptr [rcx+19h], 6
0x1800da92d  jb      loc_1800DBEB5
0x1800da933  mov     edx, 39h ; '9'
0x1800da938  mov     r9d, edi
0x1800da93b  jmp     loc_1800DA880
0x1800da940  mov     rcx, rsi; hMem
0x1800da943  call    cs:__imp_GlobalFree
0x1800da949  mov     rcx, [rbp+hKey]; hKey
0x1800da94d  mov     r8, rbx
0x1800da950  mov     rdx, r13
0x1800da953  call    RegInsertPhoneList
0x1800da958  mov     edi, eax
0x1800da95a  test    eax, eax
0x1800da95c  jz      short loc_1800DA9CA
0x1800da95e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800da965  lea     rbx, WPP_GLOBAL_Control
0x1800da96c  cmp     rcx, rbx
0x1800da96f  jz      loc_1800DBEAB
0x1800da975  test    byte ptr [rcx+1Ch], 80h
0x1800da979  jz      short loc_1800DA9A0
0x1800da97b  cmp     byte ptr [rcx+19h], 2
0x1800da97f  jb      short loc_1800DA9A0
0x1800da981  mov     rcx, [rcx+10h]
0x1800da985  lea     r8, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids
0x1800da98c  mov     edx, 3Ah ; ':'
0x1800da991  mov     r9d, eax
0x1800da994  call    WPP_SF_d
0x1800da999  mov     rcx, cs:WPP_GLOBAL_Control
0x1800da9a0  cmp     rcx, rbx
0x1800da9a3  jz      loc_1800DBEAB
0x1800da9a9  test    byte ptr [rcx+1Ch], 80h
0x1800da9ad  jz      loc_1800DBEAB
0x1800da9b3  cmp     byte ptr [rcx+19h], 6
0x1800da9b7  jb      loc_1800DBEAB
0x1800da9bd  mov     edx, 3Bh ; ';'
0x1800da9c2  mov     r9d, edi
0x1800da9c5  jmp     loc_1800DBE9B
0x1800da9ca  mov     r8d, [rbx+0B0h]
0x1800da9d1  lea     rdx, String2; "LastSelectedPhone"
0x1800da9d8  mov     rcx, [rbp+hKey]
0x1800da9dc  call    RegInsertLong
0x1800da9e1  mov     edi, eax
0x1800da9e3  test    eax, eax
0x1800da9e5  jz      short loc_1800DAA50
0x1800da9e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800da9ee  lea     rbx, WPP_GLOBAL_Control
0x1800da9f5  cmp     rcx, rbx
0x1800da9f8  jz      loc_1800DBEAB
0x1800da9fe  test    byte ptr [rcx+1Ch], 80h
0x1800daa02  jz      short loc_1800DAA29
0x1800daa04  cmp     byte ptr [rcx+19h], 2
0x1800daa08  jb      short loc_1800DAA29
0x1800daa0a  mov     rcx, [rcx+10h]
0x1800daa0e  lea     r8, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids
0x1800daa15  mov     edx, 3Ch ; '<'
0x1800daa1a  mov     r9d, eax
0x1800daa1d  call    WPP_SF_d
0x1800daa22  mov     rcx, cs:WPP_GLOBAL_Control
0x1800daa29  cmp     rcx, rbx
0x1800daa2c  jz      loc_1800DBEAB
0x1800daa32  test    byte ptr [rcx+1Ch], 80h
0x1800daa36  jz      loc_1800DBEAB
0x1800daa3c  cmp     byte ptr [rcx+19h], 6
0x1800daa40  jb      loc_1800DBEAB
0x1800daa46  mov     edx, 3Dh ; '='
0x1800daa4b  jmp     loc_1800DA9C2
0x1800daa50  mov     r8d, [rbx+0B4h]
0x1800daa57  lea     rdx, aPromotealterna; "PromoteAlternates"
0x1800daa5e  mov     rcx, [rbp+hKey]
0x1800daa62  call    RegInsertFlag
0x1800daa67  mov     edi, eax
0x1800daa69  test    eax, eax
0x1800daa6b  jz      short loc_1800DAAD6
0x1800daa6d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800daa74  lea     rbx, WPP_GLOBAL_Control
0x1800daa7b  cmp     rcx, rbx
0x1800daa7e  jz      loc_1800DBEAB
0x1800daa84  test    byte ptr [rcx+1Ch], 80h
0x1800daa88  jz      short loc_1800DAAAF
0x1800daa8a  cmp     byte ptr [rcx+19h], 2
0x1800daa8e  jb      short loc_1800DAAAF
0x1800daa90  mov     rcx, [rcx+10h]
0x1800daa94  lea     r8, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids
0x1800daa9b  mov     edx, 3Eh ; '>'
0x1800daaa0  mov     r9d, eax
0x1800daaa3  call    WPP_SF_d
0x1800daaa8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800daaaf  cmp     rcx, rbx
0x1800daab2  jz      loc_1800DBEAB
0x1800daab8  test    byte ptr [rcx+1Ch], 80h
0x1800daabc  jz      loc_1800DBEAB
0x1800daac2  cmp     byte ptr [rcx+19h], 6
0x1800daac6  jb      loc_1800DBEAB
0x1800daacc  mov     edx, 3Fh ; '?'
0x1800daad1  jmp     loc_1800DA9C2
0x1800daad6  mov     r8d, [rbx+0B8h]
0x1800daadd  lea     rdx, aTrynextalterna; "TryNextAlternateOnFail"
0x1800daae4  mov     rcx, [rbp+hKey]
0x1800daae8  call    RegInsertFlag
0x1800daaed  mov     edi, eax
0x1800daaef  test    eax, eax
0x1800daaf1  jz      short loc_1800DAB5C
0x1800daaf3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800daafa  lea     rbx, WPP_GLOBAL_Control
0x1800dab01  cmp     rcx, rbx
0x1800dab04  jz      loc_1800DBEAB
0x1800dab0a  test    byte ptr [rcx+1Ch], 80h
0x1800dab0e  jz      short loc_1800DAB35
0x1800dab10  cmp     byte ptr [rcx+19h], 2
0x1800dab14  jb      short loc_1800DAB35
0x1800dab16  mov     rcx, [rcx+10h]
0x1800dab1a  lea     r8, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids
0x1800dab21  mov     edx, 40h ; '@'
0x1800dab26  mov     r9d, eax
0x1800dab29  call    WPP_SF_d
0x1800dab2e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dab35  cmp     rcx, rbx
0x1800dab38  jz      loc_1800DBEAB
0x1800dab3e  test    byte ptr [rcx+1Ch], 80h
0x1800dab42  jz      loc_1800DBEAB
0x1800dab48  cmp     byte ptr [rcx+19h], 6
0x1800dab4c  jb      loc_1800DBEAB
0x1800dab52  mov     edx, 41h ; 'A'
0x1800dab57  jmp     loc_1800DA9C2
0x1800dab5c  mov     r8d, [rbx+84h]
0x1800dab63  lea     rdx, aLinetype; "LineType"
0x1800dab6a  mov     rcx, [rbp+hKey]
0x1800dab6e  call    RegInsertLong
0x1800dab73  mov     edi, eax
0x1800dab75  test    eax, eax
0x1800dab77  jz      short loc_1800DABE2
0x1800dab79  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dab80  lea     rbx, WPP_GLOBAL_Control
0x1800dab87  cmp     rcx, rbx
0x1800dab8a  jz      loc_1800DBEAB
0x1800dab90  test    byte ptr [rcx+1Ch], 80h
0x1800dab94  jz      short loc_1800DABBB
0x1800dab96  cmp     byte ptr [rcx+19h], 2
0x1800dab9a  jb      short loc_1800DABBB
0x1800dab9c  mov     rcx, [rcx+10h]
0x1800daba0  lea     r8, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids
0x1800daba7  mov     edx, 42h ; 'B'
0x1800dabac  mov     r9d, eax
0x1800dabaf  call    WPP_SF_d
0x1800dabb4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dabbb  cmp     rcx, rbx
0x1800dabbe  jz      loc_1800DBEAB
0x1800dabc4  test    byte ptr [rcx+1Ch], 80h
0x1800dabc8  jz      loc_1800DBEAB
0x1800dabce  cmp     byte ptr [rcx+19h], 6
0x1800dabd2  jb      loc_1800DBEAB
0x1800dabd8  mov     edx, 43h ; 'C'
0x1800dabdd  jmp     loc_1800DA9C2
0x1800dabe2  mov     r8d, [rbx+88h]
0x1800dabe9  lea     rdx, aFallback; "Fallback"
0x1800dabf0  mov     rcx, [rbp+hKey]
0x1800dabf4  call    RegInsertFlag
0x1800dabf9  mov     edi, eax
0x1800dabfb  test    eax, eax
0x1800dabfd  jz      short loc_1800DAC68
0x1800dabff  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dac06  lea     rbx, WPP_GLOBAL_Control
0x1800dac0d  cmp     rcx, rbx
0x1800dac10  jz      loc_1800DBEAB
0x1800dac16  test    byte ptr [rcx+1Ch], 80h
0x1800dac1a  jz      short loc_1800DAC41
0x1800dac1c  cmp     byte ptr [rcx+19h], 2
0x1800dac20  jb      short loc_1800DAC41
0x1800dac22  mov     rcx, [rcx+10h]
0x1800dac26  lea     r8, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids
0x1800dac2d  mov     edx, 44h ; 'D'
0x1800dac32  mov     r9d, eax
0x1800dac35  call    WPP_SF_d
0x1800dac3a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dac41  cmp     rcx, rbx
0x1800dac44  jz      loc_1800DBEAB
0x1800dac4a  test    byte ptr [rcx+1Ch], 80h
0x1800dac4e  jz      loc_1800DBEAB
0x1800dac54  cmp     byte ptr [rcx+19h], 6
0x1800dac58  jb      loc_1800DBEAB
0x1800dac5e  mov     edx, 45h ; 'E'
0x1800dac63  jmp     loc_1800DA9C2
0x1800dac68  mov     r8d, [rbx+8Ch]
0x1800dac6f  lea     rdx, aEnablecompress; "EnableCompression"
0x1800dac76  mov     rcx, [rbp+hKey]
0x1800dac7a  call    RegInsertFlag
0x1800dac7f  mov     edi, eax
0x1800dac81  test    eax, eax
0x1800dac83  jz      short loc_1800DACEE
0x1800dac85  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dac8c  lea     rbx, WPP_GLOBAL_Control
0x1800dac93  cmp     rcx, rbx
0x1800dac96  jz      loc_1800DBEAB
0x1800dac9c  test    byte ptr [rcx+1Ch], 80h
0x1800daca0  jz      short loc_1800DACC7
0x1800daca2  cmp     byte ptr [rcx+19h], 2
0x1800daca6  jb      short loc_1800DACC7
0x1800daca8  mov     rcx, [rcx+10h]
0x1800dacac  lea     r8, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids
0x1800dacb3  mov     edx, 46h ; 'F'
0x1800dacb8  mov     r9d, eax
0x1800dacbb  call    WPP_SF_d
0x1800dacc0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dacc7  cmp     rcx, rbx
0x1800dacca  jz      loc_1800DBEAB
0x1800dacd0  test    byte ptr [rcx+1Ch], 80h
0x1800dacd4  jz      loc_1800DBEAB
0x1800dacda  cmp     byte ptr [rcx+19h], 6
0x1800dacde  jb      loc_1800DBEAB
0x1800dace4  mov     edx, 47h ; 'G'
0x1800dace9  jmp     loc_1800DA9C2
0x1800dacee  mov     r8d, [rbx+90h]
0x1800dacf5  lea     rdx, aChannelaggrega; "ChannelAggregation"
0x1800dacfc  mov     rcx, [rbp+hKey]
0x1800dad00  call    RegInsertLong
0x1800dad05  mov     edi, eax
0x1800dad07  test    eax, eax
0x1800dad09  jz      short loc_1800DAD74
0x1800dad0b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dad12  lea     rbx, WPP_GLOBAL_Control
0x1800dad19  cmp     rcx, rbx
0x1800dad1c  jz      loc_1800DBEAB
0x1800dad22  test    byte ptr [rcx+1Ch], 80h
  ... truncated ...
```
