# DDMGetEapUserIdentityW

- ea: `0x1800679b0`
- end: `0x180067fae`
- name: `DDMGetEapUserIdentityW`
- size: `1534`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, BYTE *, HANDLE hToken)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180006afc`
- `0x180010d10`
- `0x1800161d0`
- `0x18004e580`
- `0x18004e984`
- `0x180067888`
- `0x1800679b0`
- `0x18006ae64`
- `0x18007f01c`
- `0x1800b9e04`
- `0x1800ba4bc`
- `0x1800ba550`
- `0x1800ba898`
- `0x1800cfd40`
- `0x1800decee`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180067f54`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180067f54`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180067df6`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180067df6`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180067d87`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180067d87`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180067c7c`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180067c7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067c37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067c89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067c37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067c89`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180067cc8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180067cc8`
- `eappcfg!EapHostPeerInvokeIdentityUI` at `0x180067d43`
- `eappcfg!EapHostPeerInvokeIdentityUI` at `0x180067d43`

## pseudocode

```c
__int64 __fastcall DDMGetEapUserIdentityW(__int64 a1, __int64 a2, __int64 a3, BYTE *a4, HANDLE hToken)
{
  HWND v5; // r13
  DWORD v6; // ebx
  int v7; // r12d
  HLOCAL *v9; // r15
  _QWORD *v10; // rcx
  __int64 v12; // rcx
  HWND v13; // rax
  DWORD v14; // r13d
  DWORD EapMethodTypeFromEapType; // eax
  unsigned int v16; // ebx
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // r9
  int v20; // ecx
  int v21; // r9d
  int v22; // ecx
  BOOL v23; // r14d
  DWORD LastError; // eax
  DWORD v25; // eax
  DWORD v26; // ecx
  wchar_t *v27; // rax
  BYTE *pConnectionData; // [rsp+28h] [rbp-79h]
  DWORD pdwSizeOfUserDataOut; // [rsp+70h] [rbp-31h] BYREF
  DWORD dwSizeofUserData; // [rsp+74h] [rbp-2Dh] BYREF
  DWORD dwSizeofConnectionData; // [rsp+78h] [rbp-29h] BYREF
  BYTE *pData; // [rsp+80h] [rbp-21h] BYREF
  LPWSTR ppwszIdentity; // [rsp+88h] [rbp-19h] BYREF
  BYTE *v34; // [rsp+90h] [rbp-11h] BYREF
  EAP_ERROR *pEapError; // [rsp+98h] [rbp-9h] BYREF
  EAP_METHOD_TYPE eapMethodType; // [rsp+A0h] [rbp-1h] BYREF
  HWND hwndParent; // [rsp+B0h] [rbp+Fh]

  v5 = (HWND)a4;
  v6 = a3;
  v7 = a2;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    pConnectionData = a4;
    LOBYTE(a4) = (_DWORD)a2 != 0;
    WPP_SF_cDq(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, a4, a3, pConnectionData);
  }
  pEapError = 0;
  eapMethodType = 0;
  dwSizeofUserData = 0;
  pData = 0;
  pdwSizeOfUserDataOut = 0;
  v34 = 0;
  dwSizeofConnectionData = 0;
  ppwszIdentity = 0;
  DebugInit();
  v9 = (HLOCAL *)hToken;
  if ( !hToken )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 1042, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, 87);
        v10 = WPP_GLOBAL_Control;
      }
      if ( v10 != &WPP_GLOBAL_Control && (*((_DWORD *)v10 + 7) & 0x800) != 0 && *((_BYTE *)v10 + 25) >= 6u )
        WPP_SF_d(v10[2], 1043, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, 87);
    }
    return 87;
  }
  *(_QWORD *)hToken = 0;
  if ( *(char *)(a1 + 164) >= 0 || (v12 = *(unsigned int *)(a1 + 192), !(_DWORD)v12) )
  {
    v16 = 780;
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_94;
    }
    v18 = 1044;
    goto LABEL_92;
  }
  v13 = 0;
  if ( (v6 & 2) == 0 )
    v13 = v5;
  v14 = v6 | 1;
  hwndParent = v13;
  if ( !v7 )
    v14 = v6;
  EapMethodTypeFromEapType = RasGetEapMethodTypeFromEapType(v12, &eapMethodType);
  v16 = EapMethodTypeFromEapType;
  if ( EapMethodTypeFromEapType )
  {
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v18 = 1045;
LABEL_26:
      v19 = EapMethodTypeFromEapType;
LABEL_93:
      WPP_SF_d(v17[2], v18, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v19);
      goto LABEL_94;
    }
    goto LABEL_94;
  }
  EapMethodTypeFromEapType = DwGetCustomAuthData(a1, &dwSizeofConnectionData, &v34);
  v16 = EapMethodTypeFromEapType;
  if ( EapMethodTypeFromEapType )
  {
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v18 = 1046;
      goto LABEL_26;
    }
LABEL_94:
    if ( pData )
      RasFreeEapMemory(pData);
    goto LABEL_96;
  }
  EapMethodTypeFromEapType = DDMGetEapUserDataW(v20, a1, v7, v21, (__int64)&dwSizeofUserData);
  v16 = EapMethodTypeFromEapType;
  if ( EapMethodTypeFromEapType )
  {
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v18 = 1047;
      goto LABEL_26;
    }
    goto LABEL_94;
  }
  if ( (unsigned int)RasMobileCore() )
  {
    v22 = (int)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 1048, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids);
    }
    hToken = 0;
    if ( !(unsigned int)QueryLoggedOnUserForSingleSessionDevice(v22, &hToken) )
    {
      EapMethodTypeFromEapType = GetLastError();
      v16 = EapMethodTypeFromEapType;
      if ( EapMethodTypeFromEapType )
      {
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v18 = 1049;
          goto LABEL_26;
        }
      }
      goto LABEL_94;
    }
    v23 = ImpersonateLoggedOnUser(hToken);
    if ( !v23 )
    {
      LastError = GetLastError();
      v16 = LastError;
      if ( LastError )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            1050,
            WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids,
            LastError);
        }
      }
    }
    CloseHandle(hToken);
    if ( !v23 )
      goto LABEL_94;
  }
  v25 = EapHostPeerInvokeIdentityUI(
          0,
          &eapMethodType,
          v14,
          hwndParent,
          dwSizeofConnectionData,
          v34,
          dwSizeofUserData,
          0,
          &pdwSizeOfUserDataOut,
          &pData,
          &ppwszIdentity,
          &pEapError,
          0);
  v16 = v25;
  if ( v25
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 1051, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v25);
  }
  if ( (unsigned int)RasMobileCore() )
    RevertToSelf();
  if ( !v16 && pdwSizeOfUserDataOut )
  {
    v26 = -1;
    if ( pdwSizeOfUserDataOut + 523 >= 0x20B )
      v26 = pdwSizeOfUserDataOut + 523;
    v16 = pdwSizeOfUserDataOut >= 0xFFFFFDF5 ? 0x80070216 : 0;
    if ( pdwSizeOfUserDataOut + 523 >= 0x20B )
    {
      v27 = (wchar_t *)GlobalAlloc(0x40u, v26);
      *v9 = v27;
      if ( v27 )
      {
        EapMethodTypeFromEapType = StringCchCopyWrapW(v27);
        v16 = EapMethodTypeFromEapType;
        if ( !EapMethodTypeFromEapType )
        {
          *((_DWORD *)*v9 + 129) = pdwSizeOfUserDataOut;
          memcpy_0((char *)*v9 + 520, pData, pdwSizeOfUserDataOut);
          goto LABEL_94;
        }
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v18 = 1055;
          goto LABEL_26;
        }
        goto LABEL_94;
      }
      v16 = 8;
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_94;
      }
      v18 = 1054;
    }
    else
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_94;
      }
      v18 = 1053;
    }
LABEL_92:
    v19 = v16;
    goto LABEL_93;
  }
  pData = 0;
  pdwSizeOfUserDataOut = 0;
  if ( v16 != 1223 )
  {
    EapMethodTypeFromEapType = MapEapHostErrorToRasError(v16);
    v16 = EapMethodTypeFromEapType;
    if ( EapMethodTypeFromEapType )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v18 = 1052;
        goto LABEL_26;
      }
    }
    goto LABEL_94;
  }
LABEL_96:
  if ( ppwszIdentity )
    RasFreeEapMemory((BYTE *)ppwszIdentity);
  if ( v16 && *v9 )
  {
    LocalFree(*v9);
    *v9 = 0;
  }
  RasFreeEapConfigErrorMemory(pEapError);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 1056, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v16);
  }
  return v16;
}

```

## disassembly

```asm
0x1800679b0  push    rbp
0x1800679b2  push    rbx
0x1800679b3  push    rsi
0x1800679b4  push    r12
0x1800679b6  push    r13
0x1800679b8  push    r14
0x1800679ba  push    r15
0x1800679bc  lea     rbp, [rsp-1Fh]
0x1800679c1  sub     rsp, 0C0h
0x1800679c8  mov     r13, r9
0x1800679cb  mov     ebx, r8d
0x1800679ce  mov     r12d, edx
0x1800679d1  mov     r14, rcx
0x1800679d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800679db  lea     rax, WPP_GLOBAL_Control
0x1800679e2  xor     esi, esi
0x1800679e4  cmp     rcx, rax
0x1800679e7  jz      short loc_180067A10
0x1800679e9  test    dword ptr [rcx+1Ch], 800h
0x1800679f0  jz      short loc_180067A10
0x1800679f2  cmp     byte ptr [rcx+19h], 6
0x1800679f6  jb      short loc_180067A10
0x1800679f8  mov     rcx, [rcx+10h]
0x1800679fc  test    edx, edx
0x1800679fe  mov     [rsp+0F0h+pConnectionData], r13
0x180067a03  setnz   r9b
0x180067a07  mov     [rsp+0F0h+dwSizeofConnectionData], ebx
0x180067a0b  call    WPP_SF_cDq
0x180067a10  xorps   xmm0, xmm0
0x180067a13  mov     [rbp+4Fh+pEapError], rsi
0x180067a17  movups  xmmword ptr [rbp+4Fh+eapMethodType.eapType.type], xmm0
0x180067a1b  mov     [rbp+4Fh+var_7C], esi
0x180067a1e  mov     [rbp+4Fh+pData], rsi
0x180067a22  mov     [rbp+4Fh+var_80], esi
0x180067a25  mov     [rbp+4Fh+var_60], rsi
0x180067a29  mov     [rbp+4Fh+var_78], esi
0x180067a2c  mov     [rbp+4Fh+var_68], rsi
0x180067a30  call    DebugInit
0x180067a35  mov     r15, [rbp+4Fh+hToken]
0x180067a39  test    r15, r15
0x180067a3c  jnz     short loc_180067AB6
0x180067a3e  mov     rcx, cs:WPP_GLOBAL_Control
0x180067a45  lea     rbx, WPP_GLOBAL_Control
0x180067a4c  lea     r14d, [r15+57h]
0x180067a50  cmp     rcx, rbx
0x180067a53  jz      short loc_180067AAE
0x180067a55  test    dword ptr [rcx+1Ch], 800h
0x180067a5c  lea     rsi, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x180067a63  jz      short loc_180067A86
0x180067a65  cmp     byte ptr [rcx+19h], 2
0x180067a69  jb      short loc_180067A86
0x180067a6b  mov     rcx, [rcx+10h]
0x180067a6f  mov     edx, 412h
0x180067a74  mov     r9d, r14d
0x180067a77  mov     r8, rsi
0x180067a7a  call    WPP_SF_d
0x180067a7f  mov     rcx, cs:WPP_GLOBAL_Control
0x180067a86  cmp     rcx, rbx
0x180067a89  jz      short loc_180067AAE
0x180067a8b  test    dword ptr [rcx+1Ch], 800h
0x180067a92  jz      short loc_180067AAE
0x180067a94  cmp     byte ptr [rcx+19h], 6
0x180067a98  jb      short loc_180067AAE
0x180067a9a  mov     rcx, [rcx+10h]
0x180067a9e  mov     edx, 413h
0x180067aa3  mov     r9d, r14d
0x180067aa6  mov     r8, rsi
0x180067aa9  call    WPP_SF_d
0x180067aae  mov     eax, r14d
0x180067ab1  jmp     loc_180067F9B
0x180067ab6  mov     [r15], rsi
0x180067ab9  lea     rsi, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x180067ac0  test    byte ptr [r14+0A4h], 80h
0x180067ac8  jz      loc_180067EF1
0x180067ace  mov     ecx, [r14+0C0h]
0x180067ad5  test    ecx, ecx
0x180067ad7  jz      loc_180067EF1
0x180067add  test    bl, 2
0x180067ae0  lea     rdx, [rbp+4Fh+eapMethodType]
0x180067ae4  mov     eax, 0
0x180067ae9  cmovz   rax, r13
0x180067aed  mov     r13d, ebx
0x180067af0  or      r13d, 1
0x180067af4  mov     [rbp+4Fh+hwndParent], rax
0x180067af8  test    r12d, r12d
0x180067afb  cmovz   r13d, ebx
0x180067aff  call    RasGetEapMethodTypeFromEapType
0x180067b04  mov     ebx, eax
0x180067b06  test    eax, eax
0x180067b08  jz      short loc_180067B45
0x180067b0a  mov     rcx, cs:WPP_GLOBAL_Control
0x180067b11  lea     r12, WPP_GLOBAL_Control
0x180067b18  cmp     rcx, r12
0x180067b1b  jz      loc_180067F2C
0x180067b21  test    dword ptr [rcx+1Ch], 800h
0x180067b28  jz      loc_180067F2C
0x180067b2e  cmp     byte ptr [rcx+19h], 2
0x180067b32  jb      loc_180067F2C
0x180067b38  mov     edx, 415h
0x180067b3d  mov     r9d, eax
0x180067b40  jmp     loc_180067F20
0x180067b45  lea     r8, [rbp+4Fh+var_60]
0x180067b49  mov     rcx, r14
0x180067b4c  lea     rdx, [rbp+4Fh+var_78]
0x180067b50  call    DwGetCustomAuthData
0x180067b55  mov     ebx, eax
0x180067b57  test    eax, eax
0x180067b59  jz      short loc_180067B90
0x180067b5b  mov     rcx, cs:WPP_GLOBAL_Control
0x180067b62  lea     r12, WPP_GLOBAL_Control
0x180067b69  cmp     rcx, r12
0x180067b6c  jz      loc_180067F2C
0x180067b72  test    dword ptr [rcx+1Ch], 800h
0x180067b79  jz      loc_180067F2C
0x180067b7f  cmp     byte ptr [rcx+19h], 2
0x180067b83  jb      loc_180067F2C
0x180067b89  mov     edx, 416h
0x180067b8e  jmp     short loc_180067B3D
0x180067b90  lea     rax, [rbp+4Fh+var_7C]
0x180067b94  mov     r8d, r12d
0x180067b97  mov     rdx, r14
0x180067b9a  mov     qword ptr [rsp+0F0h+dwSizeofConnectionData], rax
0x180067b9f  call    DDMGetEapUserDataW
0x180067ba4  mov     ebx, eax
0x180067ba6  test    eax, eax
0x180067ba8  jz      short loc_180067BE2
0x180067baa  mov     rcx, cs:WPP_GLOBAL_Control
0x180067bb1  lea     r12, WPP_GLOBAL_Control
0x180067bb8  cmp     rcx, r12
0x180067bbb  jz      loc_180067F2C
0x180067bc1  test    dword ptr [rcx+1Ch], 800h
0x180067bc8  jz      loc_180067F2C
0x180067bce  cmp     byte ptr [rcx+19h], 2
0x180067bd2  jb      loc_180067F2C
0x180067bd8  mov     edx, 417h
0x180067bdd  jmp     loc_180067B3D
0x180067be2  call    RasMobileCore
0x180067be7  test    eax, eax
0x180067be9  jz      loc_180067CD9
0x180067bef  mov     rcx, cs:WPP_GLOBAL_Control
0x180067bf6  lea     r12, WPP_GLOBAL_Control
0x180067bfd  cmp     rcx, r12
0x180067c00  jz      short loc_180067C22
0x180067c02  test    dword ptr [rcx+1Ch], 800h
0x180067c09  jz      short loc_180067C22
0x180067c0b  cmp     byte ptr [rcx+19h], 5
0x180067c0f  jb      short loc_180067C22
0x180067c11  mov     rcx, [rcx+10h]
0x180067c15  mov     edx, 418h
0x180067c1a  mov     r8, rsi
0x180067c1d  call    WPP_SF_
0x180067c22  lea     rdx, [rbp+4Fh+hToken]; void **
0x180067c26  mov     [rbp+4Fh+hToken], 0
0x180067c2e  call    ?QueryLoggedOnUserForSingleSessionDevice@@YAHKPEAPEAX@Z; QueryLoggedOnUserForSingleSessionDevice(ulong,void * *)
0x180067c33  test    eax, eax
0x180067c35  jnz     short loc_180067C78
0x180067c37  call    cs:__imp_GetLastError
0x180067c3d  mov     ebx, eax
0x180067c3f  test    eax, eax
0x180067c41  jz      loc_180067F2C
0x180067c47  mov     rcx, cs:WPP_GLOBAL_Control
0x180067c4e  cmp     rcx, r12
0x180067c51  jz      loc_180067F2C
0x180067c57  test    dword ptr [rcx+1Ch], 800h
0x180067c5e  jz      loc_180067F2C
0x180067c64  cmp     byte ptr [rcx+19h], 2
0x180067c68  jb      loc_180067F2C
0x180067c6e  mov     edx, 419h
0x180067c73  jmp     loc_180067B3D
0x180067c78  mov     rcx, [rbp+4Fh+hToken]; hToken
0x180067c7c  call    cs:__imp_ImpersonateLoggedOnUser
0x180067c82  mov     r14d, eax
0x180067c85  test    eax, eax
0x180067c87  jnz     short loc_180067CC4
0x180067c89  call    cs:__imp_GetLastError
0x180067c8f  mov     ebx, eax
0x180067c91  test    eax, eax
0x180067c93  jz      short loc_180067CC4
0x180067c95  mov     rcx, cs:WPP_GLOBAL_Control
0x180067c9c  cmp     rcx, r12
0x180067c9f  jz      short loc_180067CC4
0x180067ca1  test    dword ptr [rcx+1Ch], 800h
0x180067ca8  jz      short loc_180067CC4
0x180067caa  cmp     byte ptr [rcx+19h], 2
0x180067cae  jb      short loc_180067CC4
0x180067cb0  mov     rcx, [rcx+10h]
0x180067cb4  mov     edx, 41Ah
0x180067cb9  mov     r9d, eax
0x180067cbc  mov     r8, rsi
0x180067cbf  call    WPP_SF_d
0x180067cc4  mov     rcx, [rbp+4Fh+hToken]; hObject
0x180067cc8  call    cs:__imp_CloseHandle
0x180067cce  test    r14d, r14d
0x180067cd1  jz      loc_180067F2C
0x180067cd7  jmp     short loc_180067CE0
0x180067cd9  lea     r12, WPP_GLOBAL_Control
0x180067ce0  movaps  xmm0, xmmword ptr [rbp+4Fh+eapMethodType.eapType.type]
0x180067ce4  lea     rax, [rbp+4Fh+pEapError]
0x180067ce8  mov     r9, [rbp+4Fh+hwndParent]; hwndParent
0x180067cec  lea     rdx, [rbp+4Fh+eapMethodType]; eapMethodType
0x180067cf0  mov     [rsp+0F0h+ppvReserved], 0; ppvReserved
0x180067cf9  mov     r8d, r13d; dwFlags
0x180067cfc  mov     [rsp+0F0h+ppEapError], rax; ppEapError
0x180067d01  xor     ecx, ecx; dwVersion
0x180067d03  lea     rax, [rbp+4Fh+var_68]
0x180067d07  movdqa  xmmword ptr [rbp+4Fh+eapMethodType.eapType.type], xmm0
0x180067d0c  mov     [rsp+0F0h+ppwszIdentity], rax; ppwszIdentity
0x180067d11  lea     rax, [rbp+4Fh+pData]
0x180067d15  mov     [rsp+0F0h+ppUserDataOut], rax; ppUserDataOut
0x180067d1a  lea     rax, [rbp+4Fh+var_80]
0x180067d1e  mov     [rsp+0F0h+pdwSizeOfUserDataOut], rax; pdwSizeOfUserDataOut
0x180067d23  mov     eax, [rbp+4Fh+var_7C]
0x180067d26  mov     [rsp+0F0h+pUserData], 0; pUserData
0x180067d2f  mov     [rsp+0F0h+dwSizeofUserData], eax; dwSizeofUserData
0x180067d33  mov     rax, [rbp+4Fh+var_60]
0x180067d37  mov     [rsp+0F0h+pConnectionData], rax; pConnectionData
0x180067d3c  mov     eax, [rbp+4Fh+var_78]
0x180067d3f  mov     [rsp+0F0h+dwSizeofConnectionData], eax; dwSizeofConnectionData
0x180067d43  call    cs:__imp_EapHostPeerInvokeIdentityUI
0x180067d49  mov     ebx, eax
0x180067d4b  test    eax, eax
0x180067d4d  jz      short loc_180067D7E
0x180067d4f  mov     rcx, cs:WPP_GLOBAL_Control
0x180067d56  cmp     rcx, r12
0x180067d59  jz      short loc_180067D7E
0x180067d5b  test    dword ptr [rcx+1Ch], 800h
0x180067d62  jz      short loc_180067D7E
0x180067d64  cmp     byte ptr [rcx+19h], 2
0x180067d68  jb      short loc_180067D7E
0x180067d6a  mov     rcx, [rcx+10h]
0x180067d6e  mov     edx, 41Bh
0x180067d73  mov     r9d, eax
0x180067d76  mov     r8, rsi
0x180067d79  call    WPP_SF_d
0x180067d7e  call    RasMobileCore
0x180067d83  test    eax, eax
0x180067d85  jz      short loc_180067D8D
0x180067d87  call    cs:__imp_RevertToSelf
0x180067d8d  test    ebx, ebx
0x180067d8f  jnz     loc_180067EA8
0x180067d95  mov     eax, [rbp+4Fh+var_80]
0x180067d98  test    eax, eax
0x180067d9a  jz      loc_180067EA8
0x180067da0  add     eax, 20Bh
0x180067da5  or      ecx, 0FFFFFFFFh
0x180067da8  mov     edx, 20Bh
0x180067dad  cmp     eax, edx
0x180067daf  cmovnb  ecx, eax
0x180067db2  sbb     ebx, ebx
0x180067db4  and     ebx, 80070216h
0x180067dba  cmp     eax, edx
0x180067dbc  jnb     short loc_180067DEF
0x180067dbe  mov     rcx, cs:WPP_GLOBAL_Control
0x180067dc5  cmp     rcx, r12
0x180067dc8  jz      loc_180067F2C
0x180067dce  test    dword ptr [rcx+1Ch], 800h
0x180067dd5  jz      loc_180067F2C
0x180067ddb  cmp     byte ptr [rcx+19h], 2
0x180067ddf  jb      loc_180067F2C
0x180067de5  mov     edx, 41Dh
0x180067dea  jmp     loc_180067F1D
0x180067def  mov     edx, ecx; dwBytes
0x180067df1  mov     ecx, 40h ; '@'; uFlags
0x180067df6  call    cs:__imp_GlobalAlloc
0x180067dfc  mov     [r15], rax
0x180067dff  test    rax, rax
0x180067e02  jnz     short loc_180067E38
0x180067e04  lea     ebx, [rax+8]
0x180067e07  mov     rcx, cs:WPP_GLOBAL_Control
0x180067e0e  cmp     rcx, r12
0x180067e11  jz      loc_180067F2C
0x180067e17  test    dword ptr [rcx+1Ch], 800h
0x180067e1e  jz      loc_180067F2C
0x180067e24  cmp     byte ptr [rcx+19h], 2
0x180067e28  jb      loc_180067F2C
0x180067e2e  mov     edx, 41Eh
0x180067e33  jmp     loc_180067F1D
0x180067e38  mov     r8, [rbp+4Fh+var_68]
0x180067e3c  mov     edx, 101h
0x180067e41  mov     rcx, rax; pszDest
0x180067e44  call    StringCchCopyWrapW
0x180067e49  mov     ebx, eax
0x180067e4b  test    eax, eax
0x180067e4d  jz      short loc_180067E80
0x180067e4f  mov     rcx, cs:WPP_GLOBAL_Control
0x180067e56  cmp     rcx, r12
0x180067e59  jz      loc_180067F2C
0x180067e5f  test    dword ptr [rcx+1Ch], 800h
0x180067e66  jz      loc_180067F2C
0x180067e6c  cmp     byte ptr [rcx+19h], 2
0x180067e70  jb      loc_180067F2C
0x180067e76  mov     edx, 41Fh
0x180067e7b  jmp     loc_180067B3D
0x180067e80  mov     rcx, [r15]
0x180067e83  mov     eax, [rbp+4Fh+var_80]
0x180067e86  mov     [rcx+204h], eax
0x180067e8c  mov     rcx, [r15]
0x180067e8f  mov     r8d, [rbp+4Fh+var_80]; Size
0x180067e93  add     rcx, 208h; void *
0x180067e9a  mov     rdx, [rbp+4Fh+pData]; Src
  ... truncated ...
```
