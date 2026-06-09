# ReadGPOList(HKEY__ *,ushort *,_GROUP_POLICY_OBJECTW * *,_GPOINFO *)

- ea: `0x180003800`
- end: `0x1800048da`
- name: `?ReadGPOList@@YAHPEAUHKEY__@@PEAGPEAPEAU_GROUP_POLICY_OBJECTW@@PEAU_GPOINFO@@@Z`
- size: `4314`
- prototype: `int(HKEY, unsigned __int16 *, struct _GROUP_POLICY_OBJECTW **, struct _GPOINFO *)`
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x180001830`
- `0x180002530`
- `0x18004eabc`
- `0x18009dd2c`

## callees

- `0x180003800`
- `0x180005e4c`
- `0x18002a5a0`
- `0x180075ec0`
- `0x18007d320`
- `0x18007d9b0`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800038c0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003e1c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003f3b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800038c0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003e1c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003f3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000385a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003ef8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800045b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800045d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004614`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004633`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004657`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004695`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800046b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800046d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004716`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000385a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003ef8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800045b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800045d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004614`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004633`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004657`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004695`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800046b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800046d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004716`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003a0b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003a29`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003a47`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003a65`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003a84`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003a0b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003a29`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003a47`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003a65`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003a84`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003d54`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003d60`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003d69`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003e6b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800041b8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004225`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004296`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000437b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800047e4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800047f2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004800`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000480e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000481c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004841`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003d54`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003d60`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003d69`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003e6b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800041b8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004225`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004296`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000437b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800047e4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800047f2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004800`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000480e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000481c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004841`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003d89`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003dfa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004827`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003d89`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003dfa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004827`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800039e1`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800039e1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800038a9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003973`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800038a9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003973`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003ac8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003b08`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003b3c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003b7b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003bba`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003bfc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003c3e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003c83`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003cd5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003d16`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003ac8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003b08`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003b3c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003b7b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003bba`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003bfc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003c3e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003c83`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003cd5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003d16`

## string_xrefs

- `0x180003b31`: `DSPath`
- `0x180003b70`: `FileSysPath`
- `0x180003bf1`: `Extensions`
- `0x180003cca`: `GPOLink`
- `0x180003fc9`: `ReadGPOList:++`
- `0x180003ffb`: `ReadGPOList:++`
- `0x18000402c`: `ReadGPOList: Failed to open reg key with %d.`
- `0x180004056`: `ReadGPOList: Failed to open reg key with %d.`
- `0x18000478f`: `ReadGPOList: Failed to open reg key <%s> with %d.`
- `0x1800047cb`: `ReadGPOList: Failed to open reg key <%s> with %d.`
- `0x18000408d`: `ReadGPOList: Read Key:%d`
- `0x1800040c2`: `ReadGPOList: Read Key:%d`
- `0x180003e4f`: `ReadGPOList: Failed to query max size with %d.`
- `0x180004754`: `ReadGPOList: Failed to query max size with %d.`
- `0x1800045df`: `ReadGPOList: Failed to allocate memory with %d.`
- `0x18000461d`: `ReadGPOList: Failed to allocate memory with %d.`
- `0x180004660`: `ReadGPOList: Failed to allocate memory with %d.`
- `0x18000469e`: `ReadGPOList: Failed to allocate memory with %d.`
- `0x1800046e1`: `ReadGPOList: Failed to allocate memory with %d.`
- `0x18000471f`: `ReadGPOList: Failed to allocate memory with %d.`
- `0x1800040f4`: `ReadGPOList: Failed to query options reg value with %d.`
- `0x18000412c`: `ReadGPOList: Failed to query options reg value with %d.`
- `0x18000415e`: `ReadGPOList: Failed to query Version reg value with %d.`
- `0x180004196`: `ReadGPOList: Failed to query Version reg value with %d.`
- `0x1800043aa`: `ReadGPOList: Failed to query DS reg value with %d.`
- `0x1800043e2`: `ReadGPOList: Failed to query DS reg value with %d.`
- `0x180004564`: `ReadGPOList: Failed to query file sys path reg value with %d.`
- `0x18000459c`: `ReadGPOList: Failed to query file sys path reg value with %d.`
- `0x1800044f5`: `ReadGPOList: Failed to query display name reg value with %d.`
- `0x18000452d`: `ReadGPOList: Failed to query display name reg value with %d.`
- `0x1800041e3`: `ReadGPOList: Failed to query extension names reg value with %d.`
- `0x180004210`: `ReadGPOList: Failed to query extension names reg value with %d.`
- `0x180004255`: `ReadGPOList: Failed to query DS Object reg value with %d.`
- `0x180004282`: `ReadGPOList: Failed to query DS Object reg value with %d.`
- `0x180003f82`: `ReadGPOList: Failed to query GPO name reg value with %d.`
- `0x1800044be`: `ReadGPOList: Failed to query GPO name reg value with %d.`
- `0x1800042c0`: `ReadGPOList: Failed to query reserved reg value with %d.`
- `0x1800042f8`: `ReadGPOList: Failed to query reserved reg value with %d.`
- `0x18000432a`: `ReadGPOList: Failed to query lParam reg value with %d.`
- `0x180004362`: `ReadGPOList: Failed to query lParam reg value with %d.`
- `0x18000444b`: `ReadGPOList: Failed to check WMI filter with error %d.`
- `0x180004483`: `ReadGPOList: Failed to check WMI filter with error %d.`
- `0x180003f20`: `ReadGPOList: Failed to add GPO to list.`
- `0x180004414`: `ReadGPOList: Failed to add GPO to list.`
- `0x18000487c`: `ReadGPOList:-- (Result:%s)`
- `0x1800048c3`: `ReadGPOList:-- (Result:%s)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ReadGPOList(HKEY a1, unsigned __int16 *a2, struct _GROUP_POLICY_OBJECTW **a3, struct _GPOINFO *a4)
{
  BYTE *v7; // r13
  DWORD LastError; // ebx
  HKEY v9; // rcx
  unsigned int v10; // eax
  DWORD v11; // edi
  unsigned int v13; // edi
  HLOCAL v14; // r12
  WCHAR *v15; // r9
  int v16; // r10d
  unsigned int v17; // r8d
  unsigned int v18; // eax
  unsigned int v19; // eax
  DWORD v20; // ecx
  HLOCAL v21; // r15
  HLOCAL v22; // rdi
  unsigned int v23; // eax
  unsigned int v24; // eax
  unsigned int v25; // eax
  unsigned int v26; // eax
  unsigned int v27; // eax
  unsigned int v28; // eax
  unsigned int v29; // eax
  unsigned int v30; // eax
  unsigned __int64 v31; // rcx
  unsigned int v32; // eax
  unsigned int v33; // eax
  unsigned int v34; // eax
  int v35; // r8d
  int v36; // r9d
  unsigned int v37; // r15d
  DWORD v38; // ecx
  void (*v39)(unsigned int, const unsigned __int16 *, ...); // r14
  DWORD v40; // eax
  DWORD v41; // eax
  void (*v42)(unsigned int, const unsigned __int16 *, ...); // rdi
  DWORD v43; // eax
  DWORD v44; // eax
  void (*v45)(unsigned int, const unsigned __int16 *, ...); // rdi
  DWORD v46; // eax
  DWORD v47; // eax
  _QWORD *v48; // rcx
  _QWORD *v49; // rdi
  const wchar_t *v50; // r8
  const wchar_t *v51; // r8
  int phkResult; // [rsp+20h] [rbp-110h]
  __int64 v53; // [rsp+60h] [rbp-D0h]
  int v54; // [rsp+68h] [rbp-C8h]
  int v55; // [rsp+98h] [rbp-98h]
  DWORD cbData; // [rsp+B0h] [rbp-80h] BYREF
  int v57; // [rsp+B4h] [rbp-7Ch]
  DWORD cbMaxValueLen; // [rsp+B8h] [rbp-78h] BYREF
  DWORD Type; // [rsp+BCh] [rbp-74h] BYREF
  HKEY v60; // [rsp+C0h] [rbp-70h] BYREF
  LPBYTE lpData; // [rsp+C8h] [rbp-68h]
  BYTE v62[4]; // [rsp+D0h] [rbp-60h] BYREF
  BYTE v63[4]; // [rsp+D4h] [rbp-5Ch] BYREF
  BYTE Data[4]; // [rsp+D8h] [rbp-58h] BYREF
  int v65; // [rsp+DCh] [rbp-54h] BYREF
  int v66; // [rsp+E0h] [rbp-50h]
  int v67; // [rsp+E4h] [rbp-4Ch]
  HKEY hKey; // [rsp+E8h] [rbp-48h] BYREF
  BYTE v69[8]; // [rsp+F0h] [rbp-40h] BYREF
  WCHAR SubKey[28]; // [rsp+F8h] [rbp-38h] BYREF
  BYTE v71[112]; // [rsp+130h] [rbp+0h] BYREF

  hKey = a1;
  v7 = 0;
  v60 = 0;
  *(_DWORD *)Data = 0;
  *(_DWORD *)v63 = 0;
  *(_DWORD *)v62 = 0;
  *(_QWORD *)v69 = 0;
  cbData = 0;
  Type = 0;
  cbMaxValueLen = 0;
  LastError = GetLastError();
  v57 = LastError;
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"ReadGPOList:++");
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(4u, L"ReadGPOList:++");
    }
  }
  v9 = hKey;
  if ( !hKey || !a2 || !a3 )
  {
    v38 = 87;
LABEL_70:
    SetLastError(v38);
    return 0;
  }
  *a3 = 0;
  v10 = RegOpenKeyExW(v9, a2, 0, 0x20019u, &hKey);
  v11 = v10;
  if ( v10 )
  {
    if ( v10 == 2 )
    {
      SetLastError(LastError);
      return 1;
    }
    v57 = v10;
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"ReadGPOList: Failed to open reg key with %d.", v10);
      }
      else if ( g_lpDebugMsgContextInstance )
      {
        if ( g_lpDebugMsgContext )
          RedirectDebugMsg(2u, L"ReadGPOList: Failed to open reg key with %d.", v10);
      }
    }
    v38 = v11;
    goto LABEL_70;
  }
  v13 = 0;
  v66 = 0;
  v67 = 0;
  v14 = 0;
  lpData = 0;
  while ( 1 )
  {
    v15 = SubKey;
    v16 = v13;
    v17 = 0;
    do
    {
      SubKey[v17++ + 12] = v16 % 10 + 48;
      v16 /= 10;
    }
    while ( v16 && v17 < 0xC );
    if ( v17 < 0xC )
    {
      do
        *v15++ = SubKey[--v17 + 12];
      while ( v17 );
    }
    *v15 = 0;
    v18 = RegOpenKeyExW(hKey, SubKey, 0, 0x20019u, &v60);
    if ( v18 )
    {
      if ( v18 == 2 )
      {
        v67 = 1;
      }
      else
      {
        LastError = v18;
        v57 = v18;
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(2u, L"ReadGPOList: Failed to open reg key <%s> with %d.", SubKey, v18);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(2u, L"ReadGPOList: Failed to open reg key <%s> with %d.", SubKey, v18);
          }
        }
      }
      goto LABEL_45;
    }
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"ReadGPOList: Read Key:%d", v13);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(4u, L"ReadGPOList: Read Key:%d", v13);
      }
    }
    v19 = RegQueryInfoKeyW(v60, 0, 0, 0, 0, 0, 0, 0, 0, &cbMaxValueLen, 0, 0);
    if ( v19 )
    {
      LastError = v19;
      v57 = v19;
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"ReadGPOList: Failed to query max size with %d.", v19);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(2u, L"ReadGPOList: Failed to query max size with %d.", v19);
        }
      }
LABEL_45:
      v21 = 0;
LABEL_46:
      v22 = 0;
LABEL_47:
      if ( v14 )
        LocalFree(v14);
      if ( v21 )
        LocalFree(v21);
      if ( v22 )
        LocalFree(v22);
      goto LABEL_53;
    }
    v20 = cbMaxValueLen + 2;
    if ( cbMaxValueLen + 2 < cbMaxValueLen )
    {
      cbMaxValueLen = -1;
      LastError = 534;
      v57 = 534;
      goto LABEL_45;
    }
    cbMaxValueLen += 2;
    v14 = LocalAlloc(0x40u, v20 + 2LL);
    if ( !v14 )
      break;
    v21 = LocalAlloc(0x40u, cbMaxValueLen + 2LL);
    if ( !v21 )
    {
      LastError = GetLastError();
      v57 = LastError;
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        v42 = g_lpDebugMsg;
        if ( g_lpDebugMsg )
        {
          v43 = GetLastError();
          v42(2u, L"ReadGPOList: Failed to allocate memory with %d.", v43);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          v44 = GetLastError();
          RedirectDebugMsg(2u, L"ReadGPOList: Failed to allocate memory with %d.", v44);
        }
      }
      goto LABEL_46;
    }
    v22 = LocalAlloc(0x40u, cbMaxValueLen + 2LL);
    if ( !v22
      || (lpData = (LPBYTE)LocalAlloc(0x40u, cbMaxValueLen + 2LL)) == 0
      || (v7 = (BYTE *)LocalAlloc(0x40u, cbMaxValueLen + 2LL)) == 0 )
    {
      LastError = GetLastError();
      v57 = LastError;
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        v39 = g_lpDebugMsg;
        if ( g_lpDebugMsg )
        {
          v40 = GetLastError();
          v39(2u, L"ReadGPOList: Failed to allocate memory with %d.", v40);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          v41 = GetLastError();
          RedirectDebugMsg(2u, L"ReadGPOList: Failed to allocate memory with %d.", v41);
        }
      }
      goto LABEL_47;
    }
    *(_DWORD *)Data = 0;
    cbData = 4;
    v23 = RegQueryValueExW(v60, L"Options", 0, &Type, Data, &cbData);
    if ( v23 && *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"ReadGPOList: Failed to query options reg value with %d.", v23);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"ReadGPOList: Failed to query options reg value with %d.", v23);
      }
    }
    *(_DWORD *)v63 = 0;
    cbData = 4;
    v24 = RegQueryValueExW(v60, L"Version", 0, &Type, v63, &cbData);
    if ( v24 && *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"ReadGPOList: Failed to query Version reg value with %d.", v24);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"ReadGPOList: Failed to query Version reg value with %d.", v24);
      }
    }
    cbData = cbMaxValueLen;
    v25 = RegQueryValueExW(v60, L"DSPath", 0, &Type, (LPBYTE)v14, &cbData);
    if ( v25 )
    {
      if ( v25 != 2 )
      {
        LastError = v25;
        v57 = v25;
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(2u, L"ReadGPOList: Failed to query DS reg value with %d.", v25);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(2u, L"ReadGPOList: Failed to query DS reg value with %d.", v25);
          }
        }
        goto LABEL_47;
      }
      LocalFree(v14);
      v14 = 0;
    }
    else
    {
      *((_WORD *)v14 + ((unsigned __int64)cbData >> 1)) = 0;
    }
    cbData = cbMaxValueLen;
    v26 = RegQueryValueExW(v60, L"FileSysPath", 0, &Type, (LPBYTE)v21, &cbData);
    if ( v26 )
    {
      LastError = v26;
      v57 = v26;
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"ReadGPOList: Failed to query file sys path reg value with %d.", v26);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(2u, L"ReadGPOList: Failed to query file sys path reg value with %d.", v26);
        }
      }
      goto LABEL_47;
    }
    *((_WORD *)v21 + ((unsigned __int64)cbData >> 1)) = 0;
    cbData = cbMaxValueLen;
    v27 = RegQueryValueExW(v60, L"DisplayName", 0, &Type, (LPBYTE)v22, &cbData);
    if ( v27 )
    {
      LastError = v27;
      v57 = v27;
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"ReadGPOList: Failed to query display name reg value with %d.", v27);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(2u, L"ReadGPOList: Failed to query display name reg value with %d.", v27);
        }
      }
      goto LABEL_47;
    }
    *((_WORD *)v22 + ((unsigned __int64)cbData >> 1)) = 0;
    cbData = cbMaxValueLen;
    v28 = RegQueryValueExW(v60, L"Extensions", 0, &Type, lpData, &cbData);
    if ( v28 )
    {
      LastError = v28;
      v57 = v28;
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"ReadGPOList: Failed to query extension names reg value with %d.", v28);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(2u, L"ReadGPOList: Failed to query extension names reg value with %d.", v28);
        }
      }
      LocalFree(lpData);
      lpData = 0;
    }
    else
    {
      *(_WORD *)&lpData[2 * ((unsigned __int64)cbData >> 1)] = 0;
    }
    cbData = cbMaxValueLen;
    v29 = RegQueryValueExW(v60, L"Link", 0, &Type, v7, &cbData);
    if ( v29 )
    {
      if ( v29 != 2 && *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"ReadGPOList: Failed to query DS Object reg value with %d.", v29);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(2u, L"ReadGPOList: Failed to query DS Object reg value with %d.", v29);
        }
      }
      LocalFree(v7);
      v7 = 0;
    }
    else
    {
      *(_WORD *)&v7[2 * ((unsigned __int64)cbData >> 1)] = 0;
    }
    cbData = 100;
    v30 = RegQueryValueExW(v60, L"GPOName", 0, &Type, v71, &cbData);
    if ( v30 )
    {
      LastError = v30;
      v57 = v30;
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"ReadGPOList: Failed to query GPO name reg value with %d.", v30);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(2u, L"ReadGPOList: Failed to query GPO name reg value with %d.", v30);
        }
      }
      goto LABEL_47;
    }
    v31 = cbData & 0xFFFFFFFE;
    if ( v31 >= 0x66 )
      _report_rangecheckfailure();
    *(_WORD *)&v71[v31] = 0;
    *(_DWORD *)v62 = 0;
    cbData = 4;
    v32 = RegQueryValueExW(v60, L"GPOLink", 0, &Type, v62, &cbData);
    if ( v32 && *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"ReadGPOList: Failed to query reserved reg value with %d.", v32);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"ReadGPOList: Failed to query reserved reg value with %d.", v32);
      }
    }
    *(_QWORD *)v69 = 0;
    cbData = 8;
    v33 = RegQueryValueExW(v60, L"lParam", 0, &Type, v69, &cbData);
    if ( v33 && *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"ReadGPOList: Failed to query lParam reg value with %d.", v33);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"ReadGPOList: Failed to query lParam reg value with %d.", v33);
      }
    }
    v65 = 1;
    v34 = CGPWMI::NoWMIFilterOrFilterAllowed(v60, &v65, a4);
    if ( v34 )
    {
      LastError = v34;
      v57 = v34;
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"ReadGPOList: Failed to check WMI filter with error %d.", v34);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(2u, L"ReadGPOList: Failed to check WMI filter with error %d.", v34);
        }
      }
      goto LABEL_47;
    }
    if ( v65
      && !(unsigned int)AddGPO(
                          (int)a3,
                          0,
                          v35,
                          v36,
                          phkResult,
                          *(int *)Data,
                          *(int *)v63,
                          (unsigned __int16 *)v14,
                          (__int64)v21,
                          (__int64)v22,
                          (__int64)v71,
                          (unsigned __int16 *)lpData,
                          v53,
                          v54,
                          *(int *)v62,
                          (__int64)v7,
                          *(__int64 *)v69,
                          0,
                          0,
                          v55,
                          1) )
    {
      LastError = GetLastError();
      v57 = LastError;
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"ReadGPOList: Failed to add GPO to list.");
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(2u, L"ReadGPOList: Failed to add GPO to list.");
        }
      }
      goto LABEL_47;
    }
    if ( v14 )
    {
      LocalFree(v14);
      v14 = 0;
    }
    LocalFree(v21);
    LocalFree(v22);
    if ( lpData )
    {
      LocalFree(lpData);
      lpData = 0;
    }
    if ( v7 )
    {
      LocalFree(v7);
      v7 = 0;
    }
    RegCloseKey(v60);
    v60 = 0;
    v13 = ++v66;
  }
  LastError = GetLastError();
  v57 = LastError;
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    v45 = g_lpDebugMsg;
    if ( g_lpDebugMsg )
    {
      v46 = GetLastError();
      v45(2u, L"ReadGPOList: Failed to allocate memory with %d.", v46);
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      v47 = GetLastError();
      RedirectDebugMsg(2u, L"ReadGPOList: Failed to allocate memory with %d.", v47);
    }
  }
LABEL_53:
  if ( lpData )
    LocalFree(lpData);
  if ( v7 )
    LocalFree(v7);
  if ( v60 )
    RegCloseKey(v60);
  RegCloseKey(hKey);
  v37 = v67;
  if ( !v67 )
  {
    v48 = *a3;
    if ( *a3 )
    {
      do
      {
        v49 = (_QWORD *)v48[18];
        LocalFree(v48);
        v48 = v49;
      }
      while ( v49 );
    }
    *a3 = 0;
  }
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      v50 = L"TRUE";
      if ( !v37 )
        v50 = L"FALSE";
      g_lpDebugMsg(4u, L"ReadGPOList:-- (Result:%s)", v50);
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      v51 = L"TRUE";
      if ( !v37 )
        v51 = L"FALSE";
      RedirectDebugMsg(4u, L"ReadGPOList:-- (Result:%s)", v51);
    }
  }
  SetLastError(LastError);
  return v37;
}

```

## disassembly

```asm
0x180003800  push    rbp
0x180003802  push    rbx
0x180003803  push    rsi
0x180003804  push    rdi
0x180003805  push    r12
0x180003807  push    r13
0x180003809  push    r14
0x18000380b  push    r15
0x18000380d  lea     rbp, [rsp-88h]
0x180003815  sub     rsp, 1B8h
0x18000381c  mov     rax, cs:__security_cookie
0x180003823  xor     rax, rsp
0x180003826  mov     [rbp+0C0h+var_50], rax
0x18000382a  mov     r14, r9
0x18000382d  mov     rsi, r8
0x180003830  mov     rdi, rdx
0x180003833  mov     [rbp+0C0h+hKey], rcx
0x180003837  xor     r13d, r13d
0x18000383a  mov     [rbp+0C0h+var_130], r13
0x18000383e  mov     dword ptr [rbp+0C0h+Data], r13d
0x180003842  mov     dword ptr [rbp+0C0h+var_11C], r13d
0x180003846  mov     dword ptr [rbp+0C0h+var_120], r13d
0x18000384a  mov     qword ptr [rbp+0C0h+var_100], r13
0x18000384e  mov     [rbp+0C0h+cbData], r13d
0x180003852  mov     [rbp+0C0h+Type], r13d
0x180003856  mov     [rbp+0C0h+cbMaxValueLen], r13d
0x18000385a  call    cs:__imp_GetLastError
0x180003860  mov     ebx, eax
0x180003862  mov     [rbp+0C0h+var_13C], eax
0x180003865  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x18000386c  jnz     loc_180003FBD
0x180003872  mov     rcx, [rbp+0C0h+hKey]; hKey
0x180003876  test    rcx, rcx
0x180003879  jz      loc_180003F36
0x18000387f  test    rdi, rdi
0x180003882  jz      loc_180003F36
0x180003888  test    rsi, rsi
0x18000388b  jz      loc_180003F36
0x180003891  mov     [rsi], r13
0x180003894  lea     rax, [rbp+0C0h+hKey]
0x180003898  mov     [rsp+1F0h+phkResult], rax; phkResult
0x18000389d  mov     r9d, 20019h; samDesired
0x1800038a3  xor     r8d, r8d; ulOptions
0x1800038a6  mov     rdx, rdi; lpSubKey
0x1800038a9  call    cs:__imp_RegOpenKeyExW
0x1800038af  mov     edi, eax
0x1800038b1  test    eax, eax
0x1800038b3  jz      short loc_1800038EB
0x1800038b5  cmp     eax, 2
0x1800038b8  jnz     loc_180004011
0x1800038be  mov     ecx, ebx; dwErrCode
0x1800038c0  call    cs:__imp_SetLastError
0x1800038c6  mov     eax, 1
0x1800038cb  mov     rcx, [rbp+0C0h+var_50]
0x1800038cf  xor     rcx, rsp; StackCookie
0x1800038d2  call    __security_check_cookie
0x1800038d7  add     rsp, 1B8h
0x1800038de  pop     r15
0x1800038e0  pop     r14
0x1800038e2  pop     r13
0x1800038e4  pop     r12
0x1800038e6  pop     rdi
0x1800038e7  pop     rsi
0x1800038e8  pop     rbx
0x1800038e9  pop     rbp
0x1800038ea  retn
0x1800038eb  mov     edi, r13d
0x1800038ee  mov     [rbp+0C0h+var_110], r13d
0x1800038f2  mov     [rbp+0C0h+var_10C], r13d
0x1800038f6  mov     r12, r13
0x1800038f9  mov     [rbp+0C0h+lpData], r13
0x1800038fd  nop     dword ptr [rax]
0x180003900  lea     r9, [rbp+0C0h+SubKey]
0x180003904  mov     r10d, edi
0x180003907  xor     r8d, r8d
0x18000390a  mov     eax, 66666667h
0x18000390f  imul    r10d
0x180003912  sar     edx, 2
0x180003915  mov     eax, edx
0x180003917  shr     eax, 1Fh
0x18000391a  add     edx, eax
0x18000391c  movzx   eax, dx
0x18000391f  shl     ax, 2
0x180003923  lea     ecx, [rax+rdx]
0x180003926  add     cx, cx
0x180003929  sub     r10w, cx
0x18000392d  add     r10w, 30h ; '0'
0x180003932  movsxd  rax, r8d
0x180003935  mov     [rbp+rax*2+0C0h+var_E0], r10w
0x18000393b  inc     r8d
0x18000393e  mov     r10d, edx
0x180003941  test    edx, edx
0x180003943  jnz     loc_18000406F
0x180003949  cmp     r8d, 0Ch
0x18000394d  jb      loc_180003FA0
0x180003953  xor     eax, eax
0x180003955  mov     [r9], ax
0x180003959  lea     rax, [rbp+0C0h+var_130]
0x18000395d  mov     [rsp+1F0h+phkResult], rax; phkResult
0x180003962  mov     r9d, 20019h; samDesired
0x180003968  xor     r8d, r8d; ulOptions
0x18000396b  lea     rdx, [rbp+0C0h+SubKey]; lpSubKey
0x18000396f  mov     rcx, [rbp+0C0h+hKey]; hKey
0x180003973  call    cs:__imp_RegOpenKeyExW
0x180003979  test    eax, eax
0x18000397b  jnz     loc_180003F48
0x180003981  cmp     cs:?g_dwDebugLevel@@3KA, eax; ulong g_dwDebugLevel
0x180003987  jnz     loc_18000407E
0x18000398d  mov     [rsp+1F0h+lpftLastWriteTime], 0; lpftLastWriteTime
0x180003996  mov     [rsp+1F0h+lpcbSecurityDescriptor], 0; lpcbSecurityDescriptor
0x18000399f  lea     rax, [rbp+0C0h+cbMaxValueLen]
0x1800039a3  mov     [rsp+1F0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x1800039a8  mov     [rsp+1F0h+lpcbMaxValueNameLen], 0; lpcbMaxValueNameLen
0x1800039b1  mov     [rsp+1F0h+lpcValues], 0; lpcValues
0x1800039ba  mov     [rsp+1F0h+lpcbMaxClassLen], 0; lpcbMaxClassLen
0x1800039c3  mov     [rsp+1F0h+lpcbMaxSubKeyLen], 0; lpcbMaxSubKeyLen
0x1800039cc  mov     [rsp+1F0h+phkResult], 0; lpcSubKeys
0x1800039d5  xor     r9d, r9d; lpReserved
0x1800039d8  xor     r8d, r8d; lpcchClass
0x1800039db  xor     edx, edx; lpClass
0x1800039dd  mov     rcx, [rbp+0C0h+var_130]; hKey
0x1800039e1  call    cs:__imp_RegQueryInfoKeyW
0x1800039e7  test    eax, eax
0x1800039e9  jnz     loc_180003E2A
0x1800039ef  mov     eax, [rbp+0C0h+cbMaxValueLen]
0x1800039f2  lea     ecx, [rax+2]
0x1800039f5  cmp     ecx, eax
0x1800039f7  jb      loc_180003DA4
0x1800039fd  mov     [rbp+0C0h+cbMaxValueLen], ecx
0x180003a00  mov     edx, ecx
0x180003a02  add     rdx, 2; uBytes
0x180003a06  mov     ecx, 40h ; '@'; uFlags
0x180003a0b  call    cs:__imp_LocalAlloc
0x180003a11  mov     r12, rax
0x180003a14  test    rax, rax
0x180003a17  jz      loc_1800046B4
0x180003a1d  mov     edx, [rbp+0C0h+cbMaxValueLen]
0x180003a20  add     rdx, 2; uBytes
0x180003a24  mov     ecx, 40h ; '@'; uFlags
0x180003a29  call    cs:__imp_LocalAlloc
0x180003a2f  mov     r15, rax
0x180003a32  test    rax, rax
0x180003a35  jz      loc_180004633
0x180003a3b  mov     edx, [rbp+0C0h+cbMaxValueLen]
0x180003a3e  add     rdx, 2; uBytes
0x180003a42  mov     ecx, 40h ; '@'; uFlags
0x180003a47  call    cs:__imp_LocalAlloc
0x180003a4d  mov     rdi, rax
0x180003a50  test    rax, rax
0x180003a53  jz      loc_1800045B2
0x180003a59  mov     edx, [rbp+0C0h+cbMaxValueLen]
0x180003a5c  add     rdx, 2; uBytes
0x180003a60  mov     ecx, 40h ; '@'; uFlags
0x180003a65  call    cs:__imp_LocalAlloc
0x180003a6b  mov     [rbp+0C0h+lpData], rax
0x180003a6f  test    rax, rax
0x180003a72  jz      loc_1800045B2
0x180003a78  mov     edx, [rbp+0C0h+cbMaxValueLen]
0x180003a7b  add     rdx, 2; uBytes
0x180003a7f  mov     ecx, 40h ; '@'; uFlags
0x180003a84  call    cs:__imp_LocalAlloc
0x180003a8a  mov     r13, rax
0x180003a8d  test    rax, rax
0x180003a90  jz      loc_1800045B2
0x180003a96  mov     dword ptr [rbp+0C0h+Data], 0
0x180003a9d  mov     [rbp+0C0h+cbData], 4
0x180003aa4  lea     rax, [rbp+0C0h+cbData]
0x180003aa8  mov     [rsp+1F0h+lpcbMaxSubKeyLen], rax; lpcbData
0x180003aad  lea     rax, [rbp+0C0h+Data]
0x180003ab1  mov     [rsp+1F0h+phkResult], rax; lpData
0x180003ab6  lea     r9, [rbp+0C0h+Type]; lpType
0x180003aba  xor     r8d, r8d; lpReserved
0x180003abd  lea     rdx, aOptions; "Options"
0x180003ac4  mov     rcx, [rbp+0C0h+var_130]; hKey
0x180003ac8  call    cs:__imp_RegQueryValueExW
0x180003ace  test    eax, eax
0x180003ad0  jnz     loc_1800040D8
0x180003ad6  mov     dword ptr [rbp+0C0h+var_11C], 0
0x180003add  mov     [rbp+0C0h+cbData], 4
0x180003ae4  lea     rax, [rbp+0C0h+cbData]
0x180003ae8  mov     [rsp+1F0h+lpcbMaxSubKeyLen], rax; lpcbData
0x180003aed  lea     rax, [rbp+0C0h+var_11C]
0x180003af1  mov     [rsp+1F0h+phkResult], rax; lpData
0x180003af6  lea     r9, [rbp+0C0h+Type]; lpType
0x180003afa  xor     r8d, r8d; lpReserved
0x180003afd  lea     rdx, aVersion_1; "Version"
0x180003b04  mov     rcx, [rbp+0C0h+var_130]; hKey
0x180003b08  call    cs:__imp_RegQueryValueExW
0x180003b0e  test    eax, eax
0x180003b10  jnz     loc_180004142
0x180003b16  mov     eax, [rbp+0C0h+cbMaxValueLen]
0x180003b19  mov     [rbp+0C0h+cbData], eax
0x180003b1c  lea     rax, [rbp+0C0h+cbData]
0x180003b20  mov     [rsp+1F0h+lpcbMaxSubKeyLen], rax; lpcbData
0x180003b25  mov     [rsp+1F0h+phkResult], r12; lpData
0x180003b2a  lea     r9, [rbp+0C0h+Type]; lpType
0x180003b2e  xor     r8d, r8d; lpReserved
0x180003b31  lea     rdx, aDspath; "DSPath"
0x180003b38  mov     rcx, [rbp+0C0h+var_130]; hKey
0x180003b3c  call    cs:__imp_RegQueryValueExW
0x180003b42  test    eax, eax
0x180003b44  jnz     loc_1800041AC
0x180003b4a  mov     ecx, [rbp+0C0h+cbData]
0x180003b4d  shr     rcx, 1
0x180003b50  mov     [r12+rcx*2], ax
0x180003b55  mov     eax, [rbp+0C0h+cbMaxValueLen]
0x180003b58  mov     [rbp+0C0h+cbData], eax
0x180003b5b  lea     rax, [rbp+0C0h+cbData]
0x180003b5f  mov     [rsp+1F0h+lpcbMaxSubKeyLen], rax; lpcbData
0x180003b64  mov     [rsp+1F0h+phkResult], r15; lpData
0x180003b69  lea     r9, [rbp+0C0h+Type]; lpType
0x180003b6d  xor     r8d, r8d; lpReserved
0x180003b70  lea     rdx, aFilesyspath; "FileSysPath"
0x180003b77  mov     rcx, [rbp+0C0h+var_130]; hKey
0x180003b7b  call    cs:__imp_RegQueryValueExW
0x180003b81  test    eax, eax
0x180003b83  jnz     loc_180004543
0x180003b89  mov     ecx, [rbp+0C0h+cbData]
0x180003b8c  shr     rcx, 1
0x180003b8f  mov     [r15+rcx*2], ax
0x180003b94  mov     eax, [rbp+0C0h+cbMaxValueLen]
0x180003b97  mov     [rbp+0C0h+cbData], eax
0x180003b9a  lea     rax, [rbp+0C0h+cbData]
0x180003b9e  mov     [rsp+1F0h+lpcbMaxSubKeyLen], rax; lpcbData
0x180003ba3  mov     [rsp+1F0h+phkResult], rdi; lpData
0x180003ba8  lea     r9, [rbp+0C0h+Type]; lpType
0x180003bac  xor     r8d, r8d; lpReserved
0x180003baf  lea     rdx, aDisplayname; "DisplayName"
0x180003bb6  mov     rcx, [rbp+0C0h+var_130]; hKey
0x180003bba  call    cs:__imp_RegQueryValueExW
0x180003bc0  test    eax, eax
0x180003bc2  jnz     loc_1800044D4
0x180003bc8  mov     ecx, [rbp+0C0h+cbData]
0x180003bcb  shr     rcx, 1
0x180003bce  mov     [rdi+rcx*2], ax
0x180003bd2  mov     eax, [rbp+0C0h+cbMaxValueLen]
0x180003bd5  mov     [rbp+0C0h+cbData], eax
0x180003bd8  lea     rax, [rbp+0C0h+cbData]
0x180003bdc  mov     [rsp+1F0h+lpcbMaxSubKeyLen], rax; lpcbData
0x180003be1  mov     rax, [rbp+0C0h+lpData]
0x180003be5  mov     [rsp+1F0h+phkResult], rax; lpData
0x180003bea  lea     r9, [rbp+0C0h+Type]; lpType
0x180003bee  xor     r8d, r8d; lpReserved
0x180003bf1  lea     rdx, aExtensions; "Extensions"
0x180003bf8  mov     rcx, [rbp+0C0h+var_130]; hKey
0x180003bfc  call    cs:__imp_RegQueryValueExW
0x180003c02  test    eax, eax
0x180003c04  jnz     loc_1800041C6
0x180003c0a  mov     ecx, [rbp+0C0h+cbData]
0x180003c0d  shr     rcx, 1
0x180003c10  mov     rdx, [rbp+0C0h+lpData]
0x180003c14  mov     [rdx+rcx*2], ax
0x180003c18  mov     eax, [rbp+0C0h+cbMaxValueLen]
0x180003c1b  mov     [rbp+0C0h+cbData], eax
0x180003c1e  lea     rax, [rbp+0C0h+cbData]
0x180003c22  mov     [rsp+1F0h+lpcbMaxSubKeyLen], rax; lpcbData
0x180003c27  mov     [rsp+1F0h+phkResult], r13; lpData
0x180003c2c  lea     r9, [rbp+0C0h+Type]; lpType
0x180003c30  xor     r8d, r8d; lpReserved
0x180003c33  lea     rdx, aLink; "Link"
0x180003c3a  mov     rcx, [rbp+0C0h+var_130]; hKey
0x180003c3e  call    cs:__imp_RegQueryValueExW
0x180003c44  test    eax, eax
0x180003c46  jnz     loc_180004238
0x180003c4c  mov     ecx, [rbp+0C0h+cbData]
0x180003c4f  shr     rcx, 1
0x180003c52  mov     [r13+rcx*2+0], ax
0x180003c58  mov     [rbp+0C0h+cbData], 64h ; 'd'
0x180003c5f  lea     rax, [rbp+0C0h+cbData]
0x180003c63  mov     [rsp+1F0h+lpcbMaxSubKeyLen], rax; lpcbData
0x180003c68  lea     rax, [rbp+0C0h+var_C0]
0x180003c6c  mov     [rsp+1F0h+phkResult], rax; lpData
0x180003c71  lea     r9, [rbp+0C0h+Type]; lpType
0x180003c75  xor     r8d, r8d; lpReserved
0x180003c78  lea     rdx, aGponame; "GPOName"
0x180003c7f  mov     rcx, [rbp+0C0h+var_130]; hKey
0x180003c83  call    cs:__imp_RegQueryValueExW
0x180003c89  test    eax, eax
0x180003c8b  jnz     loc_180003F5D
0x180003c91  mov     ecx, [rbp+0C0h+cbData]
0x180003c94  and     rcx, 0FFFFFFFFFFFFFFFEh
0x180003c98  cmp     rcx, 66h ; 'f'
0x180003c9c  jnb     loc_180004499
0x180003ca2  mov     word ptr [rbp+rcx+0C0h+var_C0], ax
0x180003ca7  mov     dword ptr [rbp+0C0h+var_120], eax
0x180003caa  mov     [rbp+0C0h+cbData], 4
0x180003cb1  lea     rax, [rbp+0C0h+cbData]
0x180003cb5  mov     [rsp+1F0h+lpcbMaxSubKeyLen], rax; lpcbData
0x180003cba  lea     rax, [rbp+0C0h+var_120]
0x180003cbe  mov     [rsp+1F0h+phkResult], rax; lpData
0x180003cc3  lea     r9, [rbp+0C0h+Type]; lpType
0x180003cc7  xor     r8d, r8d; lpReserved
0x180003cca  lea     rdx, aGpolink; "GPOLink"
0x180003cd1  mov     rcx, [rbp+0C0h+var_130]; hKey
0x180003cd5  call    cs:__imp_RegQueryValueExW
0x180003cdb  test    eax, eax
0x180003cdd  jnz     loc_1800042A4
0x180003ce3  mov     qword ptr [rbp+0C0h+var_100], 0
0x180003ceb  mov     [rbp+0C0h+cbData], 8
0x180003cf2  lea     rax, [rbp+0C0h+cbData]
  ... truncated ...
```
