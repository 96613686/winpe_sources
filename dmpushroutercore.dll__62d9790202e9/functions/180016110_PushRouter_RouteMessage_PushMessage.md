# PushRouter::RouteMessage(PushMessage * *)

- ea: `0x180016110`
- end: `0x180016bfb`
- name: `?RouteMessage@PushRouter@@AEAAJPEAPEAVPushMessage@@@Z`
- size: `2795`
- prototype: `__int64 __fastcall(PushRouter *this, struct PushMessage **, __int64)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180016c04`

## callees

- `0x180001464`
- `0x1800039f0`
- `0x180003a14`
- `0x1800060b4`
- `0x18000c504`
- `0x18000c63c`
- `0x18000dc6c`
- `0x18000e860`
- `0x180012860`
- `0x180012e24`
- `0x1800132fc`
- `0x180013cdc`
- `0x180014468`
- `0x180014bf8`
- `0x180016110`
- `0x180017928`
- `0x180018060`
- `0x180018974`
- `0x180018a98`
- `0x180019ce4`
- `0x18001adf8`
- `0x180036338`
- `0x18003b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180016424`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180016424`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001640c`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001640c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800164df`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800164df`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180016375`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180016375`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016315`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016315`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016236`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800164c7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800164d0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016b71`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016b7b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016b85`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016b90`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016b9a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016236`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800164c7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800164d0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016b71`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016b7b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016b85`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016b90`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016b9a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800163ab`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800163ab`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800167a7`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800167a7`
- `DMCmnUtils!InvStrCmpIW` at `0x180016455`
- `DMCmnUtils!InvStrCmpIW` at `0x18001648e`
- `DMCmnUtils!InvStrCmpIW` at `0x180016455`
- `DMCmnUtils!InvStrCmpIW` at `0x18001648e`
- `DMCmnUtils!CopyString` at `0x1800165e5`
- `DMCmnUtils!CopyString` at `0x180016673`
- `DMCmnUtils!CopyString` at `0x1800165e5`
- `DMCmnUtils!CopyString` at `0x180016673`
- `DMCmnUtils!InvStrCmpW` at `0x180016228`
- `DMCmnUtils!InvStrCmpW` at `0x180016228`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall PushRouter::RouteMessage(PushRouter *this, struct PushMessage **a2, __int64 a3)
{
  PushMessage **v3; // rsi
  PushRouter *v4; // r13
  struct PushClient *ExistingClient; // r12
  __int64 v6; // rbx
  unsigned int v7; // r15d
  int v8; // ecx
  signed int HeaderValue; // edi
  unsigned __int16 *SenderAddress; // r14
  const unsigned __int16 *v11; // r12
  const unsigned __int16 *v12; // r14
  signed int UniqueQueueId; // ebx
  HLOCAL v14; // r12
  LSTATUS v15; // eax
  signed int v16; // ecx
  DWORD v17; // r13d
  const wchar_t *v18; // rsi
  LSTATUS v19; // eax
  wchar_t *v20; // rax
  const unsigned __int16 *v21; // rsi
  BOOL v22; // r15d
  HKEY v23; // rax
  HKEY v24; // rbx
  int StringValue; // eax
  __int64 v26; // r8
  _WORD *v27; // rax
  __int64 v28; // rcx
  unsigned __int16 *v29; // rax
  __int64 v30; // rax
  __int16 *v31; // rcx
  __int64 v32; // rdx
  _WORD *v33; // r8
  __int16 v34; // r9
  _WORD *v35; // rcx
  int v36; // eax
  __int64 v37; // rcx
  unsigned int v38; // edi
  __int64 v39; // rcx
  int v40; // eax
  const struct std::nothrow_t *v41; // rdx
  __int64 v42; // rcx
  const struct std::nothrow_t *v43; // rdx
  const struct std::nothrow_t *v44; // rdx
  const OLECHAR *v45; // rdx
  const OLECHAR *v46; // r9
  const OLECHAR *v47; // r10
  const OLECHAR *v48; // r11
  __int64 v49; // rax
  __int64 v50; // r8
  int v51; // r8d
  __int64 v52; // rdx
  int v53; // edx
  const OLECHAR *v54; // r8
  __int64 v55; // rdx
  int v56; // edx
  __int64 v57; // rdx
  int v58; // edx
  const OLECHAR *v59; // rdx
  const OLECHAR *v60; // r9
  const OLECHAR *v61; // r10
  const OLECHAR *v62; // r11
  __int64 v63; // rax
  __int64 v64; // r8
  int v65; // r8d
  __int64 v66; // rdx
  int v67; // edx
  const OLECHAR *v68; // r8
  __int64 v69; // rdx
  int v70; // edx
  __int64 v71; // rdx
  int v72; // edx
  unsigned __int16 *v74; // [rsp+60h] [rbp-A0h]
  HLOCAL v75; // [rsp+68h] [rbp-98h] BYREF
  HLOCAL v76; // [rsp+70h] [rbp-90h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+78h] [rbp-88h] BYREF
  PushRouter *v78; // [rsp+80h] [rbp-80h]
  HLOCAL hMem; // [rsp+88h] [rbp-78h] BYREF
  HLOCAL v80; // [rsp+90h] [rbp-70h] BYREF
  struct PushMessage **v81; // [rsp+98h] [rbp-68h]
  unsigned int v82; // [rsp+A0h] [rbp-60h] BYREF
  struct PushClient *v83; // [rsp+A8h] [rbp-58h] BYREF
  HLOCAL v84; // [rsp+B0h] [rbp-50h] BYREF
  DWORD cSubKeys; // [rsp+B8h] [rbp-48h] BYREF
  DWORD cchName; // [rsp+BCh] [rbp-44h] BYREF
  BOOL v87; // [rsp+C0h] [rbp-40h]
  int v88; // [rsp+C4h] [rbp-3Ch]
  LPWSTR lpName; // [rsp+C8h] [rbp-38h]
  struct IPersistStore *v90; // [rsp+D0h] [rbp-30h] BYREF
  struct IPersistStore *v91; // [rsp+D8h] [rbp-28h]
  HKEY hKey[2]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v93[32]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned int *v94; // [rsp+110h] [rbp+10h]
  __int64 v95; // [rsp+118h] [rbp+18h]
  const OLECHAR *v96; // [rsp+120h] [rbp+20h]
  unsigned int v97; // [rsp+128h] [rbp+28h]
  int v98; // [rsp+12Ch] [rbp+2Ch]
  const OLECHAR *v99; // [rsp+130h] [rbp+30h]
  int v100; // [rsp+138h] [rbp+38h]
  int v101; // [rsp+13Ch] [rbp+3Ch]
  const OLECHAR *v102; // [rsp+140h] [rbp+40h]
  int v103; // [rsp+148h] [rbp+48h]
  int v104; // [rsp+14Ch] [rbp+4Ch]
  const OLECHAR *v105; // [rsp+150h] [rbp+50h]
  int v106; // [rsp+158h] [rbp+58h]
  int v107; // [rsp+15Ch] [rbp+5Ch]
  const OLECHAR *v108; // [rsp+160h] [rbp+60h]
  int v109; // [rsp+168h] [rbp+68h]
  int v110; // [rsp+16Ch] [rbp+6Ch]
  unsigned __int16 v111[264]; // [rsp+170h] [rbp+70h] BYREF

  v3 = a2;
  v81 = a2;
  v4 = this;
  v78 = this;
  v88 = 0;
  v84 = 0;
  hMem = 0;
  v75 = 0;
  v80 = 0;
  ExistingClient = 0;
  v83 = 0;
  v91 = 0;
  v90 = 0;
  v6 = 0;
  v74 = 0;
  v7 = 2;
  if ( (Microsoft_Windows_DeviceManagement_PushrouterEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(MDM_PUSHROUTER_Context, PushRouterPushRouterMessageRoutingInitiated, a3, 1, hKey);
  HeaderValue = PushMessage::TrimContentType(*v3);
  if ( HeaderValue < 0 )
    goto LABEL_145;
  HeaderValue = PushMessage::GetHeaderValue(*v3, L"X-Wap-Application-Id", (unsigned __int16 **)&hMem);
  if ( HeaderValue < 0 )
    goto LABEL_145;
  HeaderValue = PushMessage::GetHeaderValue(*v3, L"Content-Type", (unsigned __int16 **)&v84);
  if ( HeaderValue < 0 )
    goto LABEL_145;
  SenderAddress = PushMessage::GetSenderAddress(*v3);
  v74 = SenderAddress;
  if ( !v84 && !hMem )
    goto LABEL_116;
  if ( hMem && !InvStrCmpW((const unsigned __int16 *)hMem, L"x-wap-application:wml.ua") )
  {
    LocalFree(hMem);
    hMem = 0;
  }
  v11 = (const unsigned __int16 *)hMem;
  v12 = (const unsigned __int16 *)v84;
  if ( (int)FindExactRegisteredPC(
              (const unsigned __int16 *)v84,
              (const unsigned __int16 *)hMem,
              (unsigned __int16 **)&v75,
              (unsigned __int16 **)&v80) < 0 )
    goto LABEL_114;
  if ( v75 )
    goto LABEL_58;
  if ( v11 )
  {
    if ( v12 )
    {
      if ( (int)FindExactRegisteredPC(&c_szUNKNOWN, v11, (unsigned __int16 **)&v75, (unsigned __int16 **)&v80) >= 0
        && (v75
         || (int)FindExactRegisteredPC(&c_szUNKNOWN, v11, (unsigned __int16 **)&v75, (unsigned __int16 **)&v80) >= 0) )
      {
        goto LABEL_58;
      }
      goto LABEL_114;
    }
  }
  else if ( !v12 )
  {
    goto LABEL_58;
  }
  hKey[0] = 0;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  cchName = 0;
  lpName = 0;
  v76 = 0;
  v82 = 0;
  v75 = 0;
  v80 = 0;
  UniqueQueueId = RegOpenKeyExW(
                    HKEY_LOCAL_MACHINE,
                    L"Software\\Microsoft\\PushRouter\\Registrations\\ByCTAndAppId",
                    0,
                    0xF003Fu,
                    hKey);
  if ( UniqueQueueId )
  {
    if ( UniqueQueueId <= 0 )
    {
LABEL_24:
      v14 = v76;
      goto LABEL_55;
    }
    UniqueQueueId = (unsigned __int16)UniqueQueueId;
LABEL_23:
    UniqueQueueId |= 0x80070000;
    goto LABEL_24;
  }
  v15 = RegQueryInfoKeyW(hKey[0], 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
  UniqueQueueId = v15;
  if ( v15 )
  {
    if ( v15 <= 0 )
      goto LABEL_24;
    UniqueQueueId = (unsigned __int16)v15;
    goto LABEL_23;
  }
  v16 = cbMaxSubKeyLen + 1;
  if ( cbMaxSubKeyLen + 1 < cbMaxSubKeyLen )
  {
    cbMaxSubKeyLen = -1;
    goto LABEL_30;
  }
  ++cbMaxSubKeyLen;
  if ( v16 < 0 )
  {
LABEL_30:
    UniqueQueueId = -2147024362;
    goto LABEL_24;
  }
  lpName = (LPWSTR)LocalAlloc(0, (unsigned int)(2 * v16));
  if ( !lpName )
  {
    UniqueQueueId = -2147024882;
    goto LABEL_24;
  }
  v17 = 0;
  UniqueQueueId = 0;
  if ( !cSubKeys )
  {
    v14 = v76;
    goto LABEL_54;
  }
  v87 = v12 == 0;
  while ( 1 )
  {
    cchName = cbMaxSubKeyLen;
    v18 = lpName;
    v19 = RegEnumKeyExW(hKey[0], v17, lpName, &cchName, 0, 0, 0, 0);
    if ( v19 )
    {
      if ( v19 > 0 )
        UniqueQueueId = (unsigned __int16)v19 | 0x80070000;
      else
        UniqueQueueId = v19;
      goto LABEL_52;
    }
    v20 = wcsstr(v18, L";");
    v21 = v20;
    if ( v20 )
    {
      *v20 = 0;
      v21 = v20 + 1;
    }
    v22 = v12 && (!*lpName && !*v12 || !InvStrCmpIW(lpName, v12)) || v87;
    if ( !v11 )
      break;
    if ( v21 && *v21 )
      goto LABEL_182;
    if ( !*v11 )
      break;
    if ( v21 )
    {
LABEL_182:
      if ( !InvStrCmpIW(v21, v11) )
        break;
    }
LABEL_51:
    ++v17;
    v7 = 2;
    if ( v17 >= cSubKeys )
      goto LABEL_52;
  }
  if ( !v22 )
    goto LABEL_51;
  if ( v21 )
    *((_WORD *)v21 - 1) = 59;
  StringValue = QueryStringValue(hKey[0], lpName, 0, (BYTE **)&v76);
  UniqueQueueId = StringValue;
  if ( StringValue < 0 )
  {
    v7 = 2;
LABEL_52:
    v14 = v76;
    goto LABEL_53;
  }
  v14 = v76;
  if ( StringValue == 1 )
  {
    UniqueQueueId = -2147467259;
    goto LABEL_67;
  }
  if ( !v76 )
  {
    UniqueQueueId = -2147024809;
LABEL_67:
    v7 = 2;
    goto LABEL_53;
  }
  v26 = 0x7FFFFFFF;
  v27 = v76;
  v7 = 2;
  do
  {
    if ( !*v27 )
      break;
    ++v27;
    --v26;
  }
  while ( v26 );
  UniqueQueueId = v26 == 0 ? 0x80070057 : 0;
  if ( !v26 )
    goto LABEL_67;
  UniqueQueueId = CopyString(
                    (const unsigned __int16 *)v76,
                    (0x7FFFFFFF - v26) & ((unsigned __int128)-(__int128)(unsigned __int64)v26 >> 64),
                    (unsigned __int16 **)&v75);
  if ( UniqueQueueId >= 0 )
  {
    UniqueQueueId = GetUniqueQueueId((const unsigned __int16 *)v75, &v82);
    if ( UniqueQueueId >= 0 )
    {
      UniqueQueueId = StringCchPrintfW(v111, 0x104u, L"%d", v82);
      if ( UniqueQueueId >= 0 )
      {
        v28 = 0x7FFFFFFF;
        v29 = v111;
        do
        {
          if ( !*v29 )
            break;
          ++v29;
          --v28;
        }
        while ( v28 );
        UniqueQueueId = v28 == 0 ? 0x80070057 : 0;
        if ( v28 )
          UniqueQueueId = CopyString(
                            v111,
                            (0x7FFFFFFF - v28) & ((unsigned __int128)-(__int128)(unsigned __int64)v28 >> 64),
                            (unsigned __int16 **)&v80);
      }
    }
  }
LABEL_53:
  v3 = v81;
LABEL_54:
  v4 = v78;
LABEL_55:
  LocalFree(lpName);
  LocalFree(v14);
  v8 = (int)hKey[0];
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  if ( UniqueQueueId < 0 )
    goto LABEL_114;
LABEL_58:
  if ( !v75 )
  {
LABEL_114:
    ExistingClient = v83;
LABEL_115:
    SenderAddress = v74;
LABEL_116:
    if ( (Microsoft_Windows_DeviceManagement_PushrouterEnableBits & 2) != 0 )
      McTemplateU0zzzzzd_EventWriteTransfer(
        v8,
        (unsigned int)PushRouterRouteMessageSucceeded,
        (_DWORD)v84,
        (_DWORD)hMem,
        (__int64)SenderAddress,
        (__int64)v75,
        (__int64)v80,
        HeaderValue);
    if ( (unsigned int)dword_180050060 > 4 )
    {
      v45 = (const OLECHAR *)v80;
      v46 = (const OLECHAR *)v75;
      v47 = (const OLECHAR *)hMem;
      v48 = (const OLECHAR *)v84;
      v49 = -1;
      if ( v80 )
      {
        v50 = -1;
        do
          ++v50;
        while ( *((_WORD *)v80 + v50) );
        v51 = 2 * v50 + 2;
      }
      else
      {
        v45 = &word_1800401D0;
        v51 = 2;
      }
      v105 = v45;
      v106 = v51;
      v107 = 0;
      if ( v75 )
      {
        v52 = -1;
        do
          ++v52;
        while ( *((_WORD *)v75 + v52) );
        v53 = 2 * v52 + 2;
      }
      else
      {
        v46 = &word_1800401D0;
        v53 = 2;
      }
      v102 = v46;
      v103 = v53;
      v104 = 0;
      if ( SenderAddress )
      {
        v54 = SenderAddress;
        v55 = -1;
        do
          ++v55;
        while ( SenderAddress[v55] );
        v56 = 2 * v55 + 2;
      }
      else
      {
        v54 = &word_1800401D0;
        v56 = 2;
      }
      v99 = v54;
      v100 = v56;
      v101 = 0;
      if ( hMem )
      {
        v57 = -1;
        do
          ++v57;
        while ( *((_WORD *)hMem + v57) );
        v58 = 2 * v57 + 2;
      }
      else
      {
        v47 = &word_1800401D0;
        v58 = 2;
      }
      v96 = v47;
      v97 = v58;
      v98 = 0;
      if ( v84 )
      {
        do
          ++v49;
        while ( *((_WORD *)v84 + v49) );
        v7 = 2 * v49 + 2;
      }
      else
      {
        v48 = &word_1800401D0;
      }
      v94 = (unsigned int *)v48;
      v95 = v7;
      tlgWriteTransfer_EventWriteTransfer(&dword_180050060, byte_1800465A5, 0, 0, 7, v93);
    }
    goto LABEL_173;
  }
  ExistingClient = PushRouter::FindExistingClient(v4, (const unsigned __int16 *)v75);
  v83 = ExistingClient;
  if ( ExistingClient )
  {
LABEL_112:
    HeaderValue = PushClient::QueueMessage(ExistingClient, *v3);
    if ( HeaderValue < 0 )
      goto LABEL_144;
    *v3 = 0;
    goto LABEL_115;
  }
  v23 = (HKEY)operator new[](0x208u, (const struct std::nothrow_t *)&std::nothrow);
  v24 = v23;
  hKey[0] = v23;
  if ( !v23 )
  {
    HeaderValue = -2147024882;
    goto LABEL_144;
  }
  *(_WORD *)v23 = 0;
  v30 = 2147483646;
  v31 = *(__int16 **)v4;
  v32 = 260;
  v33 = v24;
  do
  {
    if ( !v30 )
      break;
    v34 = *v31;
    if ( !*v31 )
      break;
    ++v31;
    *v33++ = v34;
    --v30;
    --v32;
  }
  while ( v32 );
  HeaderValue = v32 == 0 ? 0x8007007A : 0;
  v35 = v33 - 1;
  if ( v32 )
    v35 = v33;
  *v35 = 0;
  if ( !v32
    || (HeaderValue = StringCchCatW((unsigned __int16 *)v24, 0x104u, L"\\"), HeaderValue < 0)
    || (HeaderValue = StringCchCatW((unsigned __int16 *)v24, 0x104u, (const unsigned __int16 *)v80), HeaderValue < 0)
    || (HeaderValue = StringCchCatW((unsigned __int16 *)v24, 0x104u, aQueue), HeaderValue < 0) )
  {
    operator delete(v24, (const struct std::nothrow_t *)v32);
    goto LABEL_144;
  }
  v36 = PersistXmlStore::CreatePersistXmlStore((const unsigned __int16 *)v24, &v90);
  v38 = v36;
  if ( v36 >= 0 )
    goto LABEL_109;
  if ( (Microsoft_Windows_DeviceManagement_PushrouterEnableBits & 1) != 0 )
    McTemplateU0zd_EventWriteTransfer(v37, PushRouterFailedToLoadMessageFile, v24, (unsigned int)v36);
  if ( !DeleteFileW((LPCWSTR)v24) && (Microsoft_Windows_DeviceManagement_PushrouterEnableBits & 1) != 0 )
    McTemplateU0zd_EventWriteTransfer(v39, PushRouterFailedToDeleteMessageFile, v24, v38);
  v40 = PersistXmlStore::CreatePersistXmlStore((const unsigned __int16 *)v24, &v90);
  HeaderValue = v40;
  if ( v40 >= 0 )
  {
LABEL_109:
    v91 = v90;
    HeaderValue = PushClient::CreateClient((const unsigned __int16 *)v75, v90, &v83);
    if ( HeaderValue < 0 )
    {
      operator delete(v24, v43);
      ExistingClient = v83;
      goto LABEL_144;
    }
    v91 = 0;
    v88 = 1;
    ExistingClient = v83;
    CTList<PushClient>::AddHead((char *)v4 + 24, v83);
    operator delete(v24, v44);
    goto LABEL_112;
  }
  if ( (Microsoft_Windows_DeviceManagement_PushrouterEnableBits & 1) != 0 )
    McTemplateU0zd_EventWriteTransfer(v42, PushRouterFailedToLoadMessageFile, v24, (unsigned int)v40);
  operator delete(v24, v41);
  v91 = v90;
LABEL_144:
  v6 = (__int64)v74;
LABEL_145:
  if ( (Microsoft_Windows_DeviceManagement_PushrouterEnableBits & 1) != 0 )
    McTemplateU0zzzzzd_EventWriteTransfer(
      v8,
      (unsigned int)PushRouterRouteMessageFailed,
      (_DWORD)v84,
      (_DWORD)hMem,
      v6,
      (__int64)v75,
      (__int64)v80,
      HeaderValue);
  if ( (unsigned int)dword_180050060 > 2 )
  {
    v59 = (const OLECHAR *)v80;
    v60 = (const OLECHAR *)v75;
    v61 = (const OLECHAR *)hMem;
    v62 = (const OLECHAR *)v84;
    v82 = HeaderValue;
    v63 = -1;
    if ( v80 )
    {
      v64 = -1;
      do
        ++v64;
      while ( *((_WORD *)v80 + v64) );
      v65 = 2 * v64 + 2;
    }
    else
    {
      v59 = &word_1800401D0;
      v65 = 2;
    }
    v108 = v59;
    v109 = v65;
    v110 = 0;
    if ( v75 )
    {
      v66 = -1;
      do
        ++v66;
      while ( *((_WORD *)v75 + v66) );
      v67 = 2 * v66 + 2;
    }
    else
    {
      v60 = &word_1800401D0;
      v67 = 2;
    }
    v105 = v60;
    v106 = v67;
    v107 = 0;
    if ( v6 )
    {
      v68 = (const OLECHAR *)v6;
      v69 = -1;
      do
        ++v69;
      while ( *(_WORD *)(v6 + 2 * v69) );
      v70 = 2 * v69 + 2;
    }
    else
    {
      v68 = &word_1800401D0;
      v70 = 2;
    }
    v102 = v68;
    v103 = v70;
    v104 = 0;
    if ( hMem )
    {
      v71 = -1;
      do
        ++v71;
      while ( *((_WORD *)hMem + v71) );
      v72 = 2 * v71 + 2;
    }
    else
    {
      v61 = &word_1800401D0;
      v72 = 2;
    }
    v99 = v61;
    v100 = v72;
    v101 = 0;
    if ( v84 )
    {
      do
        ++v63;
      while ( *((_WORD *)v84 + v63) );
      v7 = 2 * v63 + 2;
    }
    else
    {
      v62 = &word_1800401D0;
    }
    v96 = v62;
    v97 = v7;
    v98 = 0;
    v94 = &v82;
    v95 = 4;
    tlgWriteTransfer_EventWriteTransfer(&dword_180050060, &word_1800465FE, 0, 0, 8, v93);
  }
LABEL_173:
  LocalFree(v74);
  LocalFree(v84);
  LocalFree(hMem);
  LocalFree(v75);
  LocalFree(v80);
  if ( v91 )
    (**(void (__fastcall ***)(struct IPersistStore *, __int64))v91)(v91, 1);
  if ( v88 && HeaderValue < 0 && ExistingClient )
    PushClient::xClose(ExistingClient);
  return (unsigned int)HeaderValue;
}

```

## disassembly

```asm
0x180016110  mov     [rsp-8+arg_10], rbx
0x180016115  push    rbp
0x180016116  push    rsi
0x180016117  push    rdi
0x180016118  push    r12
0x18001611a  push    r13
0x18001611c  push    r14
0x18001611e  push    r15
0x180016120  lea     rbp, [rsp-290h]
0x180016128  sub     rsp, 390h
0x18001612f  mov     rax, cs:__security_cookie
0x180016136  xor     rax, rsp
0x180016139  mov     [rbp+2C0h+var_40], rax
0x180016140  mov     rsi, rdx
0x180016143  mov     [rbp+2C0h+var_328], rdx
0x180016147  mov     r13, rcx
0x18001614a  mov     [rbp+2C0h+var_340], rcx
0x18001614e  xor     eax, eax
0x180016150  mov     [rbp+2C0h+var_2FC], eax
0x180016153  mov     [rbp+2C0h+var_310], rax
0x180016157  mov     [rbp+2C0h+hMem], rax
0x18001615b  mov     [rsp+3C0h+var_358], rax
0x180016160  mov     [rbp+2C0h+var_330], rax
0x180016164  mov     r12d, eax
0x180016167  mov     [rbp+2C0h+var_318], rax
0x18001616b  mov     [rbp+2C0h+var_2E8], rax
0x18001616f  mov     [rbp+2C0h+var_2F0], rax
0x180016173  xor     r14d, r14d
0x180016176  mov     ebx, r14d
0x180016179  mov     [rsp+3C0h+var_360], rbx
0x18001617e  lea     r15d, [rax+2]
0x180016182  test    cs:Microsoft_Windows_DeviceManagement_PushrouterEnableBits, r15b
0x180016189  jz      short loc_1800161AC
0x18001618b  lea     rax, [rbp+2C0h+hKey]
0x18001618f  mov     [rsp+3C0h+phkResult], rax
0x180016194  lea     r9d, [r12+1]
0x180016199  lea     rdx, PushRouterPushRouterMessageRoutingInitiated
0x1800161a0  lea     rcx, MDM_PUSHROUTER_Context
0x1800161a7  call    McGenEventWrite_EventWriteTransfer
0x1800161ac  mov     rcx, [rsi]; this
0x1800161af  call    ?TrimContentType@PushMessage@@QEAAJXZ; PushMessage::TrimContentType(void)
0x1800161b4  mov     edi, eax
0x1800161b6  test    eax, eax
0x1800161b8  js      loc_1800169EE
0x1800161be  lea     r8, [rbp+2C0h+hMem]; unsigned __int16 **
0x1800161c2  lea     rdx, ?c_szAppIdHeader@@3QBGB; "X-Wap-Application-Id"
0x1800161c9  mov     rcx, [rsi]; this
0x1800161cc  call    ?GetHeaderValue@PushMessage@@QEAAJPEBGPEAPEAG@Z; PushMessage::GetHeaderValue(ushort const *,ushort * *)
0x1800161d1  mov     edi, eax
0x1800161d3  test    eax, eax
0x1800161d5  js      loc_1800169EE
0x1800161db  lea     r8, [rbp+2C0h+var_310]; unsigned __int16 **
0x1800161df  lea     rdx, aContentType; "Content-Type"
0x1800161e6  mov     rcx, [rsi]; this
0x1800161e9  call    ?GetHeaderValue@PushMessage@@QEAAJPEBGPEAPEAG@Z; PushMessage::GetHeaderValue(ushort const *,ushort * *)
0x1800161ee  mov     edi, eax
0x1800161f0  test    eax, eax
0x1800161f2  js      loc_1800169EE
0x1800161f8  mov     rcx, [rsi]; this
0x1800161fb  call    ?GetSenderAddress@PushMessage@@QEAAPEBGXZ; PushMessage::GetSenderAddress(void)
0x180016200  mov     r14, rax
0x180016203  mov     [rsp+3C0h+var_360], rax
0x180016208  cmp     [rbp+2C0h+var_310], rbx
0x18001620c  jnz     short loc_180016218
0x18001620e  cmp     [rbp+2C0h+hMem], rbx
0x180016212  jz      loc_18001688D
0x180016218  mov     rcx, [rbp+2C0h+hMem]
0x18001621c  test    rcx, rcx
0x18001621f  jz      short loc_180016240
0x180016221  lea     rdx, ?c_szDefaultUserAgent@@3QBGB; "x-wap-application:wml.ua"
0x180016228  call    cs:__imp_?InvStrCmpW@@YAHPEBG0@Z; InvStrCmpW(ushort const *,ushort const *)
0x18001622e  test    eax, eax
0x180016230  jnz     short loc_180016240
0x180016232  mov     rcx, [rbp+2C0h+hMem]; hMem
0x180016236  call    cs:__imp_LocalFree
0x18001623c  mov     [rbp+2C0h+hMem], rbx
0x180016240  mov     r12, [rbp+2C0h+hMem]
0x180016244  mov     r14, [rbp+2C0h+var_310]
0x180016248  lea     r9, [rbp+2C0h+var_330]; unsigned __int16 **
0x18001624c  lea     r8, [rsp+3C0h+var_358]; unsigned __int16 **
0x180016251  mov     rdx, r12; unsigned __int16 *
0x180016254  mov     rcx, r14; unsigned __int16 *
0x180016257  call    ?FindExactRegisteredPC@@YAJPEBG0PEAPEAG1@Z; FindExactRegisteredPC(ushort const *,ushort const *,ushort * *,ushort * *)
0x18001625c  test    eax, eax
0x18001625e  js      loc_180016884
0x180016264  cmp     [rsp+3C0h+var_358], rbx
0x180016269  jnz     loc_1800164EF
0x18001626f  test    r12, r12
0x180016272  jz      short loc_1800162C9
0x180016274  test    r14, r14
0x180016277  jz      short loc_1800162D2
0x180016279  lea     r9, [rbp+2C0h+var_330]; unsigned __int16 **
0x18001627d  lea     r8, [rsp+3C0h+var_358]; unsigned __int16 **
0x180016282  mov     rdx, r12; unsigned __int16 *
0x180016285  lea     rcx, ?c_szUNKNOWN@@3QBGB; unsigned __int16 *
0x18001628c  call    ?FindExactRegisteredPC@@YAJPEBG0PEAPEAG1@Z; FindExactRegisteredPC(ushort const *,ushort const *,ushort * *,ushort * *)
0x180016291  test    eax, eax
0x180016293  js      loc_180016884
0x180016299  cmp     [rsp+3C0h+var_358], rbx
0x18001629e  jnz     loc_1800164EF
0x1800162a4  lea     r9, [rbp+2C0h+var_330]; unsigned __int16 **
0x1800162a8  lea     r8, [rsp+3C0h+var_358]; unsigned __int16 **
0x1800162ad  mov     rdx, r12; unsigned __int16 *
0x1800162b0  lea     rcx, ?c_szUNKNOWN@@3QBGB; unsigned __int16 *
0x1800162b7  call    ?FindExactRegisteredPC@@YAJPEBG0PEAPEAG1@Z; FindExactRegisteredPC(ushort const *,ushort const *,ushort * *,ushort * *)
0x1800162bc  test    eax, eax
0x1800162be  js      loc_180016884
0x1800162c4  jmp     loc_1800164EF
0x1800162c9  test    r14, r14
0x1800162cc  jz      loc_1800164EF
0x1800162d2  mov     [rbp+2C0h+hKey], rbx
0x1800162d6  mov     [rbp+2C0h+cSubKeys], ebx
0x1800162d9  mov     [rsp+3C0h+cbMaxSubKeyLen], ebx
0x1800162dd  mov     [rbp+2C0h+cchName], ebx
0x1800162e0  mov     [rbp+2C0h+lpName], rbx
0x1800162e4  mov     [rsp+3C0h+var_350], rbx
0x1800162e9  mov     [rbp+2C0h+var_320], ebx
0x1800162ec  mov     [rsp+3C0h+var_358], rbx
0x1800162f1  mov     [rbp+2C0h+var_330], rbx
0x1800162f5  lea     rax, [rbp+2C0h+hKey]
0x1800162f9  mov     [rsp+3C0h+phkResult], rax; phkResult
0x1800162fe  mov     r9d, 0F003Fh; samDesired
0x180016304  xor     r8d, r8d; ulOptions
0x180016307  lea     rdx, ?c_szAppRegistrationByCTAndAppId@@3QBGB; "Software\\Microsoft\\PushRouter\\Regist"...
0x18001630e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180016315  call    cs:__imp_RegOpenKeyExW
0x18001631b  mov     ebx, eax
0x18001631d  xor     eax, eax
0x18001631f  test    ebx, ebx
0x180016321  jz      short loc_180016338
0x180016323  jle     short loc_18001632E
0x180016325  movzx   ebx, bx
0x180016328  or      ebx, 80070000h
0x18001632e  mov     r12, [rsp+3C0h+var_350]
0x180016333  jmp     loc_1800164C3
0x180016338  mov     [rsp+3C0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18001633d  mov     [rsp+3C0h+lpcbSecurityDescriptor], rax; lpcbSecurityDescriptor
0x180016342  mov     [rsp+3C0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x180016347  mov     [rsp+3C0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x18001634c  mov     [rsp+3C0h+lpcValues], rax; lpcValues
0x180016351  mov     [rsp+3C0h+lpcbMaxClassLen], rax; lpcbMaxClassLen
0x180016356  lea     rax, [rsp+3C0h+cbMaxSubKeyLen]
0x18001635b  mov     [rsp+3C0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180016360  lea     rax, [rbp+2C0h+cSubKeys]
0x180016364  mov     [rsp+3C0h+phkResult], rax; lpcSubKeys
0x180016369  xor     r9d, r9d; lpReserved
0x18001636c  xor     r8d, r8d; lpcchClass
0x18001636f  xor     edx, edx; lpClass
0x180016371  mov     rcx, [rbp+2C0h+hKey]; hKey
0x180016375  call    cs:__imp_RegQueryInfoKeyW
0x18001637b  mov     ebx, eax
0x18001637d  test    eax, eax
0x18001637f  jz      short loc_180016388
0x180016381  jle     short loc_18001632E
0x180016383  movzx   ebx, ax
0x180016386  jmp     short loc_180016328
0x180016388  mov     eax, [rsp+3C0h+cbMaxSubKeyLen]
0x18001638c  lea     ecx, [rax+1]
0x18001638f  cmp     ecx, eax
0x180016391  jb      loc_1800166AC
0x180016397  mov     [rsp+3C0h+cbMaxSubKeyLen], ecx
0x18001639b  test    ecx, ecx
0x18001639d  jns     short loc_1800163A6
0x18001639f  mov     ebx, 80070216h
0x1800163a4  jmp     short loc_18001632E
0x1800163a6  lea     edx, [rcx+rcx]; uBytes
0x1800163a9  xor     ecx, ecx; uFlags
0x1800163ab  call    cs:__imp_LocalAlloc
0x1800163b1  mov     [rbp+2C0h+lpName], rax
0x1800163b5  xor     edx, edx
0x1800163b7  test    rax, rax
0x1800163ba  jnz     short loc_1800163C6
0x1800163bc  mov     ebx, 8007000Eh
0x1800163c1  jmp     loc_18001632E
0x1800163c6  mov     r13d, edx
0x1800163c9  mov     ebx, edx
0x1800163cb  cmp     [rbp+2C0h+cSubKeys], edx
0x1800163ce  jbe     loc_1800166B9
0x1800163d4  mov     ecx, edx
0x1800163d6  test    r14, r14
0x1800163d9  setz    cl
0x1800163dc  mov     [rbp+2C0h+var_300], ecx
0x1800163df  mov     eax, [rsp+3C0h+cbMaxSubKeyLen]
0x1800163e3  mov     [rbp+2C0h+cchName], eax
0x1800163e6  mov     [rsp+3C0h+lpcValues], rdx; lpftLastWriteTime
0x1800163eb  mov     [rsp+3C0h+lpcbMaxClassLen], rdx; lpcchClass
0x1800163f0  mov     [rsp+3C0h+lpcbMaxSubKeyLen], rdx; lpClass
0x1800163f5  mov     [rsp+3C0h+phkResult], rdx; lpReserved
0x1800163fa  lea     r9, [rbp+2C0h+cchName]; lpcchName
0x1800163fe  mov     rsi, [rbp+2C0h+lpName]
0x180016402  mov     r8, rsi; lpName
0x180016405  mov     edx, r13d; dwIndex
0x180016408  mov     rcx, [rbp+2C0h+hKey]; hKey
0x18001640c  call    cs:__imp_RegEnumKeyExW
0x180016412  test    eax, eax
0x180016414  jnz     loc_180016695
0x18001641a  lea     rdx, ?c_szKeySeparator@@3QBGB; ";"
0x180016421  mov     rcx, rsi; Str
0x180016424  call    cs:__imp_wcsstr
0x18001642a  mov     rsi, rax
0x18001642d  xor     edx, edx
0x18001642f  test    rax, rax
0x180016432  jz      short loc_18001643A
0x180016434  mov     [rax], dx
0x180016437  add     rsi, r15
0x18001643a  test    r14, r14
0x18001643d  jz      short loc_180016469
0x18001643f  mov     r8, [rbp+2C0h+lpName]
0x180016443  cmp     dx, [r8]
0x180016447  jnz     short loc_18001644F
0x180016449  cmp     dx, [r14]
0x18001644d  jz      short loc_180016461
0x18001644f  mov     rdx, r14
0x180016452  mov     rcx, r8
0x180016455  call    cs:__imp_?InvStrCmpIW@@YAHPEBG0@Z; InvStrCmpIW(ushort const *,ushort const *)
0x18001645b  xor     edx, edx
0x18001645d  test    eax, eax
0x18001645f  jnz     short loc_180016469
0x180016461  mov     r15d, 1
0x180016467  jmp     short loc_18001646D
0x180016469  mov     r15d, [rbp+2C0h+var_300]
0x18001646d  test    r12, r12
0x180016470  jz      short loc_18001649A
0x180016472  test    rsi, rsi
0x180016475  jz      short loc_18001647C
0x180016477  cmp     dx, [rsi]
0x18001647a  jnz     short loc_180016488
0x18001647c  cmp     dx, [r12]
0x180016481  jz      short loc_18001649A
0x180016483  test    rsi, rsi
0x180016486  jz      short loc_1800164A3
0x180016488  mov     rdx, r12
0x18001648b  mov     rcx, rsi
0x18001648e  call    cs:__imp_?InvStrCmpIW@@YAHPEBG0@Z; InvStrCmpIW(ushort const *,ushort const *)
0x180016494  xor     edx, edx
0x180016496  test    eax, eax
0x180016498  jnz     short loc_1800164A3
0x18001649a  test    r15d, r15d
0x18001649d  jnz     loc_180016543
0x1800164a3  inc     r13d
0x1800164a6  cmp     r13d, [rbp+2C0h+cSubKeys]
0x1800164aa  mov     r15d, 2
0x1800164b0  jb      loc_1800163DF
0x1800164b6  mov     r12, [rsp+3C0h+var_350]
0x1800164bb  mov     rsi, [rbp+2C0h+var_328]
0x1800164bf  mov     r13, [rbp+2C0h+var_340]
0x1800164c3  mov     rcx, [rbp+2C0h+lpName]; hMem
0x1800164c7  call    cs:__imp_LocalFree
0x1800164cd  mov     rcx, r12; hMem
0x1800164d0  call    cs:__imp_LocalFree
0x1800164d6  mov     rcx, [rbp+2C0h+hKey]; hKey
0x1800164da  test    rcx, rcx
0x1800164dd  jz      short loc_1800164E5
0x1800164df  call    cs:__imp_RegCloseKey
0x1800164e5  test    ebx, ebx
0x1800164e7  js      loc_180016882
0x1800164ed  xor     ebx, ebx
0x1800164ef  mov     rdx, [rsp+3C0h+var_358]; unsigned __int16 *
0x1800164f4  test    rdx, rdx
0x1800164f7  jz      loc_180016884
0x1800164fd  mov     rcx, r13; this
0x180016500  call    ?FindExistingClient@PushRouter@@AEAAPEAVPushClient@@PEBG@Z; PushRouter::FindExistingClient(ushort const *)
0x180016505  mov     r12, rax
0x180016508  mov     [rbp+2C0h+var_318], rax
0x18001650c  test    rax, rax
0x18001650f  jnz     loc_180016868
0x180016515  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001651c  mov     ecx, 208h; unsigned __int64
0x180016521  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180016526  mov     rbx, rax
0x180016529  mov     [rbp+2C0h+hKey], rax
0x18001652d  xor     r14d, r14d
0x180016530  test    rax, rax
0x180016533  jnz     loc_1800166C3
0x180016539  mov     edi, 8007000Eh
0x18001653e  jmp     loc_1800169E9
0x180016543  test    rsi, rsi
0x180016546  jz      short loc_18001654E
0x180016548  mov     word ptr [rsi-2], 3Bh ; ';'
0x18001654e  lea     r9, [rsp+3C0h+var_350]; unsigned __int16 **
0x180016553  xor     r8d, r8d; unsigned __int16 *
0x180016556  mov     rdx, [rbp+2C0h+lpName]; unsigned __int16 *
0x18001655a  mov     rcx, [rbp+2C0h+hKey]; HKEY
0x18001655e  call    ?QueryStringValue@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z; QueryStringValue(HKEY__ *,ushort const *,ushort const *,ushort * *)
0x180016563  mov     ebx, eax
0x180016565  xor     r13d, r13d
0x180016568  test    eax, eax
0x18001656a  js      loc_18001668A
0x180016570  mov     r12, [rsp+3C0h+var_350]
0x180016575  cmp     eax, 1
0x180016578  jnz     short loc_18001658A
0x18001657a  mov     ebx, 80004005h
0x18001657f  mov     r15d, 2
0x180016585  jmp     loc_1800164BB
0x18001658a  test    r12, r12
0x18001658d  jz      loc_180016680
0x180016593  mov     esi, 7FFFFFFFh
0x180016598  mov     r8d, esi
0x18001659b  mov     rax, r12
0x18001659e  mov     r15d, 2
  ... truncated ...
```
