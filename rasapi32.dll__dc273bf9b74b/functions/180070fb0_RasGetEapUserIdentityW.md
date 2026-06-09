# RasGetEapUserIdentityW

- ea: `0x180070fb0`
- end: `0x1800716c1`
- name: `RasGetEapUserIdentityW`
- size: `1809`
- prototype: `DWORD __stdcall(LPCWSTR pszPhonebook, LPCWSTR pszEntry, DWORD dwFlags, HWND hwnd, struct tagRASEAPUSERIDENTITYW **ppRasEapUserIdentity)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180070c70`

## callees

- `0x180006afc`
- `0x18000ada0`
- `0x180010d10`
- `0x1800161d0`
- `0x1800289e0`
- `0x18004e580`
- `0x18006ae64`
- `0x180070a40`
- `0x180070fb0`
- `0x18007e598`
- `0x18007e774`
- `0x1800b9e04`
- `0x1800ba4bc`
- `0x1800ba550`
- `0x1800ba898`
- `0x1800cfd40`
- `0x1800d01a0`
- `0x1800decee`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180071605`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180071605`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180071212`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180071491`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180071212`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180071491`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180071422`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180071422`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180071323`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180071323`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071220`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800712de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071330`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071220`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800712de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071330`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007136f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007136f`
- `eappcfg!EapHostPeerInvokeIdentityUI` at `0x1800713de`
- `eappcfg!EapHostPeerInvokeIdentityUI` at `0x1800713de`

## pseudocode

```c
DWORD __stdcall RasGetEapUserIdentityW(
        LPCWSTR pszPhonebook,
        LPCWSTR pszEntry,
        DWORD dwFlags,
        HWND hwnd,
        struct tagRASEAPUSERIDENTITYW **ppRasEapUserIdentity)
{
  struct tagRASEAPUSERIDENTITYW **v7; // r13
  DWORD EntryFromSystem; // eax
  DWORD v9; // ebx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  __int64 v13; // r13
  DWORD v14; // ebx
  HWND v15; // rax
  int v16; // eax
  DWORD v17; // ecx
  DWORD EapMethodTypeFromEapType; // eax
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // r9
  DWORD EapUserDataW; // eax
  void * near **v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // r8
  BYTE *pUserData; // r13
  int v27; // ecx
  BOOL v28; // r15d
  DWORD LastError; // eax
  DWORD v30; // eax
  void * near **v31; // rdx
  void *v32; // rcx
  __int64 v33; // r8
  DWORD v34; // ecx
  struct tagRASEAPUSERIDENTITYW *v35; // rax
  _QWORD *v36; // rcx
  __int64 v37; // rdx
  DWORD dwSizeofConnectionData; // [rsp+70h] [rbp-41h] BYREF
  BYTE *pData; // [rsp+78h] [rbp-39h] BYREF
  DWORD dwFlagsa; // [rsp+80h] [rbp-31h]
  HANDLE hToken; // [rsp+88h] [rbp-29h] BYREF
  __int64 v43; // [rsp+90h] [rbp-21h] BYREF
  LPWSTR ppwszIdentity; // [rsp+98h] [rbp-19h] BYREF
  BYTE *pConnectionData; // [rsp+A0h] [rbp-11h] BYREF
  EAP_ERROR *pEapError; // [rsp+A8h] [rbp-9h] BYREF
  EAP_METHOD_TYPE eapMethodType; // [rsp+B0h] [rbp-1h] BYREF
  HWND hwndParent; // [rsp+C0h] [rbp+Fh]
  DWORD pdwSizeOfUserDataOut; // [rsp+110h] [rbp+5Fh] BYREF
  DWORD pdwSizeofEapData; // [rsp+118h] [rbp+67h] BYREF
  DWORD v51; // [rsp+120h] [rbp+6Fh]
  HWND v52; // [rsp+128h] [rbp+77h]

  v52 = hwnd;
  v51 = dwFlags;
  if ( pszPhonebook && pszEntry )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      WPP_SF_SSDq(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)pszEntry,
        dwFlags,
        (_DWORD)pszPhonebook,
        (__int64)pszEntry,
        dwFlags,
        (char)hwnd);
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_Dq(*((_QWORD *)WPP_GLOBAL_Control + 2), pszEntry, dwFlags, dwFlags, hwnd);
  }
  v43 = 0;
  eapMethodType = 0;
  pEapError = 0;
  pdwSizeofEapData = 0;
  pData = 0;
  pdwSizeOfUserDataOut = 0;
  pConnectionData = 0;
  dwSizeofConnectionData = 0;
  ppwszIdentity = 0;
  DebugInit();
  if ( pszEntry )
  {
    v7 = ppRasEapUserIdentity;
    if ( ppRasEapUserIdentity )
    {
      *ppRasEapUserIdentity = 0;
      EntryFromSystem = ReadEntryFromSystem(pszPhonebook, (__int64)pszEntry, 0x408u, 0, (size_t *)&v43, 0);
      v9 = EntryFromSystem;
      if ( EntryFromSystem )
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v11 = 1061;
LABEL_18:
          v12 = EntryFromSystem;
LABEL_19:
          WPP_SF_d(v10[2], v11, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v12);
          goto LABEL_104;
        }
        goto LABEL_104;
      }
      v13 = *(_QWORD *)(v43 + 16);
      if ( *(char *)(v13 + 164) >= 0 || !*(_DWORD *)(v13 + 192) )
      {
        v9 = 780;
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_103;
        }
        v20 = 1062;
        goto LABEL_101;
      }
      v14 = v51;
      v15 = 0;
      if ( (v51 & 2) == 0 )
        v15 = v52;
      hwndParent = v15;
      v16 = IsRouterPhonebook(pszPhonebook);
      v17 = v14 | 1;
      if ( !v16 )
        v17 = v14;
      dwFlagsa = v17;
      EapMethodTypeFromEapType = RasGetEapMethodTypeFromEapType(*(unsigned int *)(v13 + 192), &eapMethodType);
      v9 = EapMethodTypeFromEapType;
      if ( EapMethodTypeFromEapType )
      {
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_103;
        }
        v20 = 1063;
        goto LABEL_31;
      }
      EapMethodTypeFromEapType = DwGetCustomAuthData(v13, &dwSizeofConnectionData, &pConnectionData);
      v9 = EapMethodTypeFromEapType;
      if ( EapMethodTypeFromEapType )
      {
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_103;
        }
        v20 = 1064;
        goto LABEL_31;
      }
      EapUserDataW = RasGetEapUserDataW(0, pszPhonebook, pszEntry, 0, &pdwSizeofEapData);
      v9 = EapUserDataW;
      if ( EapUserDataW == 603 )
      {
        pUserData = (BYTE *)GlobalAlloc(0x40u, pdwSizeofEapData);
        if ( !pUserData )
        {
          EapMethodTypeFromEapType = GetLastError();
          v9 = EapMethodTypeFromEapType;
          if ( !EapMethodTypeFromEapType )
            goto LABEL_103;
          v19 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_103;
          }
          v20 = 1065;
          goto LABEL_31;
        }
        EapMethodTypeFromEapType = RasGetEapUserDataW(0, pszPhonebook, pszEntry, pUserData, &pdwSizeofEapData);
        v9 = EapMethodTypeFromEapType;
        if ( EapMethodTypeFromEapType )
        {
          v19 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_103;
          }
          v20 = 1066;
          goto LABEL_31;
        }
      }
      else
      {
        pUserData = 0;
        if ( EapUserDataW )
          goto LABEL_103;
      }
      if ( (unsigned int)RasMobileCore(v24, v23, v25) )
      {
        hToken = 0;
        if ( !(unsigned int)QueryLoggedOnUserForSingleSessionDevice(v27, &hToken) )
        {
          EapMethodTypeFromEapType = GetLastError();
          v9 = EapMethodTypeFromEapType;
          if ( !EapMethodTypeFromEapType )
            goto LABEL_103;
          v19 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_103;
          }
          v20 = 1067;
          goto LABEL_31;
        }
        v28 = ImpersonateLoggedOnUser(hToken);
        if ( !v28 )
        {
          LastError = GetLastError();
          v9 = LastError;
          if ( LastError )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                1068,
                WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids,
                LastError);
            }
          }
        }
        CloseHandle(hToken);
        if ( !v28 )
          goto LABEL_103;
      }
      v30 = EapHostPeerInvokeIdentityUI(
              0,
              &eapMethodType,
              dwFlagsa,
              hwndParent,
              dwSizeofConnectionData,
              pConnectionData,
              pdwSizeofEapData,
              pUserData,
              &pdwSizeOfUserDataOut,
              &pData,
              &ppwszIdentity,
              &pEapError,
              0);
      v9 = v30;
      if ( v30 )
      {
        v32 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 1069, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v30);
        }
      }
      if ( (unsigned int)RasMobileCore((__int64)v32, v31, v33) )
        RevertToSelf();
      if ( v9 || !pdwSizeOfUserDataOut )
      {
        pData = 0;
        pdwSizeOfUserDataOut = 0;
        if ( v9 == 1223 )
          goto LABEL_103;
        EapMethodTypeFromEapType = MapEapHostErrorToRasError(v9);
        v9 = EapMethodTypeFromEapType;
        if ( !EapMethodTypeFromEapType )
          goto LABEL_103;
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_103;
        }
        v20 = 1070;
LABEL_31:
        v21 = EapMethodTypeFromEapType;
LABEL_102:
        WPP_SF_d(v19[2], v20, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v21);
        goto LABEL_103;
      }
      v34 = -1;
      if ( pdwSizeOfUserDataOut + 523 >= 0x20B )
        v34 = pdwSizeOfUserDataOut + 523;
      v9 = pdwSizeOfUserDataOut >= 0xFFFFFDF5 ? 0x80070216 : 0;
      if ( pdwSizeOfUserDataOut + 523 >= 0x20B )
      {
        v35 = (struct tagRASEAPUSERIDENTITYW *)GlobalAlloc(0x40u, v34);
        v7 = ppRasEapUserIdentity;
        *ppRasEapUserIdentity = v35;
        if ( v35 )
        {
          EntryFromSystem = StringCchCopyWrapW(v35->szUserName);
          v9 = EntryFromSystem;
          if ( EntryFromSystem )
          {
            v10 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v11 = 1073;
              goto LABEL_18;
            }
          }
          else
          {
            (*v7)->dwSizeofEapInfo = pdwSizeOfUserDataOut;
            memcpy_0((*v7)->pbEapInfo, pData, pdwSizeOfUserDataOut);
          }
        }
        else
        {
          v9 = 8;
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v11 = 1072;
            v12 = 8;
            goto LABEL_19;
          }
        }
LABEL_104:
        if ( v43 )
          DestroyEntryNode(v43);
        if ( pData )
          RasFreeEapMemory(pData);
        if ( ppwszIdentity )
          RasFreeEapMemory((BYTE *)ppwszIdentity);
        if ( v9 && *v7 )
        {
          LocalFree(*v7);
          *v7 = 0;
        }
        RasFreeEapConfigErrorMemory(pEapError);
        v36 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
        {
          v37 = 1074;
LABEL_125:
          WPP_SF_d(v36[2], v37, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v9);
          return v9;
        }
        return v9;
      }
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v20 = 1071;
LABEL_101:
        v21 = v9;
        goto LABEL_102;
      }
LABEL_103:
      v7 = ppRasEapUserIdentity;
      goto LABEL_104;
    }
  }
  v36 = WPP_GLOBAL_Control;
  v9 = 87;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 1059, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, 87);
      v36 = WPP_GLOBAL_Control;
    }
    if ( v36 != &WPP_GLOBAL_Control && (*((_DWORD *)v36 + 7) & 0x800) != 0 && *((_BYTE *)v36 + 25) >= 6u )
    {
      v37 = 1060;
      goto LABEL_125;
    }
  }
  return v9;
}

```

## disassembly

```asm
0x180070fb0  mov     [rsp-8+arg_18], r9
0x180070fb5  mov     [rsp-8+arg_10], r8d
0x180070fba  push    rbp
0x180070fbb  push    rbx
0x180070fbc  push    rsi
0x180070fbd  push    r12
0x180070fbf  push    r13
0x180070fc1  push    r14
0x180070fc3  push    r15
0x180070fc5  lea     rbp, [rsp-1Fh]
0x180070fca  sub     rsp, 0D0h
0x180070fd1  xor     ebx, ebx
0x180070fd3  mov     eax, r8d
0x180070fd6  mov     r15, rdx
0x180070fd9  mov     r12, rcx
0x180070fdc  test    rcx, rcx
0x180070fdf  jz      short loc_180071024
0x180070fe1  test    rdx, rdx
0x180070fe4  jz      short loc_180071024
0x180070fe6  mov     rcx, cs:WPP_GLOBAL_Control
0x180070fed  lea     rsi, WPP_GLOBAL_Control
0x180070ff4  cmp     rcx, rsi
0x180070ff7  jz      short loc_180071057
0x180070ff9  test    dword ptr [rcx+1Ch], 800h
0x180071000  jz      short loc_180071057
0x180071002  cmp     byte ptr [rcx+19h], 6
0x180071006  jb      short loc_180071057
0x180071008  mov     rcx, [rcx+10h]
0x18007100c  mov     qword ptr [rsp+100h+dwSizeofUserData], r9
0x180071011  mov     r9, r12
0x180071014  mov     dword ptr [rsp+100h+pConnectionData], eax
0x180071018  mov     [rsp+100h+pdwSizeofEapData], rdx
0x18007101d  call    WPP_SF_SSDq
0x180071022  jmp     short loc_180071057
0x180071024  mov     rcx, cs:WPP_GLOBAL_Control
0x18007102b  lea     rsi, WPP_GLOBAL_Control
0x180071032  cmp     rcx, rsi
0x180071035  jz      short loc_180071057
0x180071037  test    dword ptr [rcx+1Ch], 800h
0x18007103e  jz      short loc_180071057
0x180071040  cmp     byte ptr [rcx+19h], 6
0x180071044  jb      short loc_180071057
0x180071046  mov     rcx, [rcx+10h]
0x18007104a  mov     [rsp+100h+pdwSizeofEapData], r9
0x18007104f  mov     r9d, eax
0x180071052  call    WPP_SF_Dq
0x180071057  xorps   xmm0, xmm0
0x18007105a  mov     [rbp+4Fh+var_70], rbx
0x18007105e  movups  xmmword ptr [rbp+4Fh+eapMethodType.eapType.type], xmm0
0x180071062  mov     [rbp+4Fh+pEapError], rbx
0x180071066  mov     [rbp+4Fh+arg_8], ebx
0x180071069  mov     [rbp+4Fh+pData], rbx
0x18007106d  mov     [rbp+4Fh+arg_0], ebx
0x180071070  mov     [rbp+4Fh+var_60], rbx
0x180071074  mov     [rbp+4Fh+dwSizeofConnectionData], ebx
0x180071077  mov     [rbp+4Fh+var_68], rbx
0x18007107b  call    DebugInit
0x180071080  test    r15, r15
0x180071083  jz      loc_180071642
0x180071089  mov     r13, [rbp+4Fh+ppRasEapUserIdentity]
0x18007108d  test    r13, r13
0x180071090  jz      loc_180071642
0x180071096  lea     rax, [rbp+4Fh+var_70]
0x18007109a  mov     [rsp+100h+pConnectionData], rbx; __int64
0x18007109f  xor     r9d, r9d
0x1800710a2  mov     [rsp+100h+pdwSizeofEapData], rax; __int64
0x1800710a7  mov     r8d, 408h
0x1800710ad  mov     [r13+0], rbx
0x1800710b1  mov     rdx, r15
0x1800710b4  mov     rcx, r12; lpString2
0x1800710b7  call    ReadEntryFromSystem
0x1800710bc  lea     r14, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x1800710c3  mov     ebx, eax
0x1800710c5  test    eax, eax
0x1800710c7  jz      short loc_180071109
0x1800710c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800710d0  cmp     rcx, rsi
0x1800710d3  jz      loc_1800715CE
0x1800710d9  test    dword ptr [rcx+1Ch], 800h
0x1800710e0  jz      loc_1800715CE
0x1800710e6  cmp     byte ptr [rcx+19h], 2
0x1800710ea  jb      loc_1800715CE
0x1800710f0  mov     edx, 425h
0x1800710f5  mov     r9d, eax
0x1800710f8  mov     rcx, [rcx+10h]
0x1800710fc  mov     r8, r14
0x1800710ff  call    WPP_SF_d
0x180071104  jmp     loc_1800715CE
0x180071109  mov     r13, [rbp+4Fh+var_70]
0x18007110d  mov     r13, [r13+10h]
0x180071111  test    byte ptr [r13+0A4h], 80h
0x180071119  jz      loc_180071596
0x18007111f  cmp     dword ptr [r13+0C0h], 0
0x180071127  jz      loc_180071596
0x18007112d  mov     ebx, [rbp+4Fh+arg_10]
0x180071130  mov     eax, 0
0x180071135  test    bl, 2
0x180071138  mov     rcx, r12; lpString
0x18007113b  cmovz   rax, [rbp+4Fh+arg_18]
0x180071140  mov     [rbp+4Fh+hwndParent], rax
0x180071144  call    IsRouterPhonebook
0x180071149  mov     ecx, ebx
0x18007114b  lea     rdx, [rbp+4Fh+eapMethodType]
0x18007114f  or      ecx, 1
0x180071152  test    eax, eax
0x180071154  cmovz   ecx, ebx
0x180071157  mov     [rbp+4Fh+dwFlags], ecx
0x18007115a  mov     ecx, [r13+0C0h]
0x180071161  call    RasGetEapMethodTypeFromEapType
0x180071166  mov     ebx, eax
0x180071168  test    eax, eax
0x18007116a  jz      short loc_1800711A0
0x18007116c  mov     rcx, cs:WPP_GLOBAL_Control
0x180071173  cmp     rcx, rsi
0x180071176  jz      loc_1800715CA
0x18007117c  test    dword ptr [rcx+1Ch], 800h
0x180071183  jz      loc_1800715CA
0x180071189  cmp     byte ptr [rcx+19h], 2
0x18007118d  jb      loc_1800715CA
0x180071193  mov     edx, 427h
0x180071198  mov     r9d, eax
0x18007119b  jmp     loc_1800715BE
0x1800711a0  lea     r8, [rbp+4Fh+var_60]
0x1800711a4  mov     rcx, r13
0x1800711a7  lea     rdx, [rbp+4Fh+dwSizeofConnectionData]
0x1800711ab  call    DwGetCustomAuthData
0x1800711b0  mov     ebx, eax
0x1800711b2  test    eax, eax
0x1800711b4  jz      short loc_1800711E4
0x1800711b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800711bd  cmp     rcx, rsi
0x1800711c0  jz      loc_1800715CA
0x1800711c6  test    dword ptr [rcx+1Ch], 800h
0x1800711cd  jz      loc_1800715CA
0x1800711d3  cmp     byte ptr [rcx+19h], 2
0x1800711d7  jb      loc_1800715CA
0x1800711dd  mov     edx, 428h
0x1800711e2  jmp     short loc_180071198
0x1800711e4  lea     rax, [rbp+4Fh+arg_8]
0x1800711e8  xor     r9d, r9d; pbEapData
0x1800711eb  mov     r8, r15; pszEntry
0x1800711ee  mov     [rsp+100h+pdwSizeofEapData], rax; pdwSizeofEapData
0x1800711f3  mov     rdx, r12; pszPhonebook
0x1800711f6  xor     ecx, ecx; hToken
0x1800711f8  call    RasGetEapUserDataW
0x1800711fd  mov     ebx, eax
0x1800711ff  cmp     eax, 25Bh
0x180071204  jnz     loc_1800712B1
0x18007120a  mov     edx, [rbp+4Fh+arg_8]; dwBytes
0x18007120d  mov     ecx, 40h ; '@'; uFlags
0x180071212  call    cs:__imp_GlobalAlloc
0x180071218  mov     r13, rax
0x18007121b  test    rax, rax
0x18007121e  jnz     short loc_180071261
0x180071220  call    cs:__imp_GetLastError
0x180071226  mov     ebx, eax
0x180071228  test    eax, eax
0x18007122a  jz      loc_1800715CA
0x180071230  mov     rcx, cs:WPP_GLOBAL_Control
0x180071237  cmp     rcx, rsi
0x18007123a  jz      loc_1800715CA
0x180071240  test    dword ptr [rcx+1Ch], 800h
0x180071247  jz      loc_1800715CA
0x18007124d  cmp     byte ptr [rcx+19h], 2
0x180071251  jb      loc_1800715CA
0x180071257  mov     edx, 429h
0x18007125c  jmp     loc_180071198
0x180071261  lea     rax, [rbp+4Fh+arg_8]
0x180071265  mov     r9, r13; pbEapData
0x180071268  mov     r8, r15; pszEntry
0x18007126b  mov     [rsp+100h+pdwSizeofEapData], rax; pdwSizeofEapData
0x180071270  mov     rdx, r12; pszPhonebook
0x180071273  xor     ecx, ecx; hToken
0x180071275  call    RasGetEapUserDataW
0x18007127a  mov     ebx, eax
0x18007127c  test    eax, eax
0x18007127e  jz      short loc_1800712BC
0x180071280  mov     rcx, cs:WPP_GLOBAL_Control
0x180071287  cmp     rcx, rsi
0x18007128a  jz      loc_1800715CA
0x180071290  test    dword ptr [rcx+1Ch], 800h
0x180071297  jz      loc_1800715CA
0x18007129d  cmp     byte ptr [rcx+19h], 2
0x1800712a1  jb      loc_1800715CA
0x1800712a7  mov     edx, 42Ah
0x1800712ac  jmp     loc_180071198
0x1800712b1  xor     r13d, r13d
0x1800712b4  test    eax, eax
0x1800712b6  jnz     loc_1800715CA
0x1800712bc  call    RasMobileCore
0x1800712c1  test    eax, eax
0x1800712c3  jz      loc_18007137E
0x1800712c9  lea     rdx, [rbp+4Fh+hToken]; void **
0x1800712cd  mov     [rbp+4Fh+hToken], 0
0x1800712d5  call    ?QueryLoggedOnUserForSingleSessionDevice@@YAHKPEAPEAX@Z; QueryLoggedOnUserForSingleSessionDevice(ulong,void * *)
0x1800712da  test    eax, eax
0x1800712dc  jnz     short loc_18007131F
0x1800712de  call    cs:__imp_GetLastError
0x1800712e4  mov     ebx, eax
0x1800712e6  test    eax, eax
0x1800712e8  jz      loc_1800715CA
0x1800712ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800712f5  cmp     rcx, rsi
0x1800712f8  jz      loc_1800715CA
0x1800712fe  test    dword ptr [rcx+1Ch], 800h
0x180071305  jz      loc_1800715CA
0x18007130b  cmp     byte ptr [rcx+19h], 2
0x18007130f  jb      loc_1800715CA
0x180071315  mov     edx, 42Bh
0x18007131a  jmp     loc_180071198
0x18007131f  mov     rcx, [rbp+4Fh+hToken]; hToken
0x180071323  call    cs:__imp_ImpersonateLoggedOnUser
0x180071329  mov     r15d, eax
0x18007132c  test    eax, eax
0x18007132e  jnz     short loc_18007136B
0x180071330  call    cs:__imp_GetLastError
0x180071336  mov     ebx, eax
0x180071338  test    eax, eax
0x18007133a  jz      short loc_18007136B
0x18007133c  mov     rcx, cs:WPP_GLOBAL_Control
0x180071343  cmp     rcx, rsi
0x180071346  jz      short loc_18007136B
0x180071348  test    dword ptr [rcx+1Ch], 800h
0x18007134f  jz      short loc_18007136B
0x180071351  cmp     byte ptr [rcx+19h], 2
0x180071355  jb      short loc_18007136B
0x180071357  mov     rcx, [rcx+10h]
0x18007135b  mov     edx, 42Ch
0x180071360  mov     r9d, eax
0x180071363  mov     r8, r14
0x180071366  call    WPP_SF_d
0x18007136b  mov     rcx, [rbp+4Fh+hToken]; hObject
0x18007136f  call    cs:__imp_CloseHandle
0x180071375  test    r15d, r15d
0x180071378  jz      loc_1800715CA
0x18007137e  movaps  xmm0, xmmword ptr [rbp+4Fh+eapMethodType.eapType.type]
0x180071382  lea     rax, [rbp+4Fh+pEapError]
0x180071386  mov     r9, [rbp+4Fh+hwndParent]; hwndParent
0x18007138a  lea     rdx, [rbp+4Fh+eapMethodType]; eapMethodType
0x18007138e  mov     r8d, [rbp+4Fh+dwFlags]; dwFlags
0x180071392  xor     ecx, ecx; dwVersion
0x180071394  mov     [rsp+100h+ppvReserved], 0; ppvReserved
0x18007139d  mov     [rsp+100h+ppEapError], rax; ppEapError
0x1800713a2  lea     rax, [rbp+4Fh+var_68]
0x1800713a6  mov     [rsp+100h+ppwszIdentity], rax; ppwszIdentity
0x1800713ab  lea     rax, [rbp+4Fh+pData]
0x1800713af  mov     [rsp+100h+ppUserDataOut], rax; ppUserDataOut
0x1800713b4  lea     rax, [rbp+4Fh+arg_0]
0x1800713b8  mov     [rsp+100h+pdwSizeOfUserDataOut], rax; pdwSizeOfUserDataOut
0x1800713bd  mov     eax, [rbp+4Fh+arg_8]
0x1800713c0  mov     [rsp+100h+pUserData], r13; pUserData
0x1800713c5  mov     [rsp+100h+dwSizeofUserData], eax; dwSizeofUserData
0x1800713c9  mov     rax, [rbp+4Fh+var_60]
0x1800713cd  mov     [rsp+100h+pConnectionData], rax; pConnectionData
0x1800713d2  mov     eax, [rbp+4Fh+dwSizeofConnectionData]
0x1800713d5  mov     dword ptr [rsp+100h+pdwSizeofEapData], eax; dwSizeofConnectionData
0x1800713d9  movdqa  xmmword ptr [rbp+4Fh+eapMethodType.eapType.type], xmm0
0x1800713de  call    cs:__imp_EapHostPeerInvokeIdentityUI
0x1800713e4  mov     ebx, eax
0x1800713e6  test    eax, eax
0x1800713e8  jz      short loc_180071419
0x1800713ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800713f1  cmp     rcx, rsi
0x1800713f4  jz      short loc_180071419
0x1800713f6  test    dword ptr [rcx+1Ch], 800h
0x1800713fd  jz      short loc_180071419
0x1800713ff  cmp     byte ptr [rcx+19h], 2
0x180071403  jb      short loc_180071419
0x180071405  mov     rcx, [rcx+10h]
0x180071409  mov     edx, 42Dh
0x18007140e  mov     r9d, eax
0x180071411  mov     r8, r14
0x180071414  call    WPP_SF_d
0x180071419  call    RasMobileCore
0x18007141e  test    eax, eax
0x180071420  jz      short loc_180071428
0x180071422  call    cs:__imp_RevertToSelf
0x180071428  test    ebx, ebx
0x18007142a  jnz     loc_18007154D
0x180071430  mov     eax, [rbp+4Fh+arg_0]
0x180071433  test    eax, eax
0x180071435  jz      loc_18007154D
0x18007143b  add     eax, 20Bh
0x180071440  or      ecx, 0FFFFFFFFh
0x180071443  mov     edx, 20Bh
0x180071448  cmp     eax, edx
0x18007144a  cmovnb  ecx, eax
0x18007144d  sbb     ebx, ebx
0x18007144f  and     ebx, 80070216h
0x180071455  cmp     eax, edx
0x180071457  jnb     short loc_18007148A
0x180071459  mov     rcx, cs:WPP_GLOBAL_Control
0x180071460  cmp     rcx, rsi
0x180071463  jz      loc_1800715CA
0x180071469  test    dword ptr [rcx+1Ch], 800h
0x180071470  jz      loc_1800715CA
0x180071476  cmp     byte ptr [rcx+19h], 2
0x18007147a  jb      loc_1800715CA
0x180071480  mov     edx, 42Fh
0x180071485  jmp     loc_1800715BB
  ... truncated ...
```
