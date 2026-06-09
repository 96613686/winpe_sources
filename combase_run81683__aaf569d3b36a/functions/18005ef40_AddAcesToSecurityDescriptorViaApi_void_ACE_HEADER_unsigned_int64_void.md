# AddAcesToSecurityDescriptorViaApi(void *,_ACE_HEADER * *,unsigned __int64,void * *)

- ea: `0x18005ef40`
- end: `0x18005f681`
- name: `?AddAcesToSecurityDescriptorViaApi@@YAJPEAXPEAPEAU_ACE_HEADER@@_KPEAPEAX@Z`
- size: `1857`
- prototype: `HRESULT __fastcall(void *pSdIn, _ACE_HEADER **ppAcesIn, unsigned __int64 cAcesIn, void **ppSdOut)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005e858`
- `0x18014fb20`
- `0x18014fb8c`

## callees

- `0x18005ef40`
- `0x180087660`
- `0x18008db2c`
- `0x1802135e9`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005efc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f05a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f0d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f14b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f1c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f240`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f2bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f338`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f447`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f4d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f528`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f5d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005efc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f05a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f0d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f14b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f1c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f240`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f2bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f338`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f447`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f4d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f528`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f5d3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005f3e8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005f5a9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005f3e8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005f5a9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005f64e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005f665`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005f64e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005f665`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18005efb6`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18005efb6`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18005f4c3`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18005f51e`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18005f4c3`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18005f51e`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18005f593`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18005f593`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18005f32e`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18005f32e`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18005f5c9`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18005f5c9`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x18005f050`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x18005f050`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x18005f2b2`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x18005f2b2`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x18005f43d`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x18005f43d`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x18005f1ba`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x18005f1ba`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorRMControl` at `0x18005f03f`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorRMControl` at `0x18005f03f`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorRMControl` at `0x18005f02d`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorRMControl` at `0x18005f02d`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x18005f0c9`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x18005f0c9`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x18005f141`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x18005f141`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x18005f236`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x18005f236`

## string_xrefs

- `0x18005f00e`: `onecore\com\combase\common\core\securityutilities.cpp`
- `0x18005f0a9`: `onecore\com\combase\common\core\securityutilities.cpp`
- `0x18005f122`: `onecore\com\combase\common\core\securityutilities.cpp`
- `0x18005f19a`: `onecore\com\combase\common\core\securityutilities.cpp`
- `0x18005f213`: `onecore\com\combase\common\core\securityutilities.cpp`
- `0x18005f28f`: `onecore\com\combase\common\core\securityutilities.cpp`
- `0x18005f30b`: `onecore\com\combase\common\core\securityutilities.cpp`
- `0x18005f387`: `onecore\com\combase\common\core\securityutilities.cpp`
- `0x18005f499`: `onecore\com\combase\common\core\securityutilities.cpp`
- `0x18005f57b`: `onecore\com\combase\common\core\securityutilities.cpp`
- `0x18005f626`: `onecore\com\combase\common\core\securityutilities.cpp`
- `0x18005f002`: `AddAcesToSecurityDescriptorViaApi`
- `0x18005f0a2`: `AddAcesToSecurityDescriptorViaApi`
- `0x18005f11b`: `AddAcesToSecurityDescriptorViaApi`
- `0x18005f193`: `AddAcesToSecurityDescriptorViaApi`
- `0x18005f20c`: `AddAcesToSecurityDescriptorViaApi`
- `0x18005f288`: `AddAcesToSecurityDescriptorViaApi`
- `0x18005f304`: `AddAcesToSecurityDescriptorViaApi`
- `0x18005f380`: `AddAcesToSecurityDescriptorViaApi`
- `0x18005f492`: `AddAcesToSecurityDescriptorViaApi`
- `0x18005f574`: `AddAcesToSecurityDescriptorViaApi`
- `0x18005f61f`: `AddAcesToSecurityDescriptorViaApi`

## pseudocode

```c
__int64 __fastcall AddAcesToSecurityDescriptorViaApi(
        void *pSdIn,
        _ACE_HEADER **ppAcesIn,
        unsigned __int64 cAcesIn,
        void **ppSdOut)
{
  HRESULT v8; // ebx
  signed int LastError; // eax
  signed int v10; // eax
  signed int v11; // eax
  signed int v12; // eax
  signed int v13; // eax
  signed int v14; // eax
  signed int v15; // eax
  signed int v16; // eax
  void *v17; // rsi
  int v18; // r9d
  unsigned __int64 i; // rdx
  _ACE_HEADER *v20; // rax
  unsigned int v21; // r14d
  _ACL *v22; // rax
  _ACL *v23; // rdi
  unsigned __int64 v24; // r14
  signed int v25; // eax
  signed int v26; // eax
  int v27; // r8d
  signed int v28; // eax
  void *v29; // rax
  signed int v30; // eax
  int bOwnerDefaulted; // [rsp+30h] [rbp-59h] BYREF
  int bGroupDefaulted; // [rsp+34h] [rbp-55h] BYREF
  int bSaclDefaulted; // [rsp+38h] [rbp-51h] BYREF
  int bSaclPresent; // [rsp+3Ch] [rbp-4Dh] BYREF
  int bDaclPresent; // [rsp+40h] [rbp-49h] BYREF
  int bDaclDefaulted; // [rsp+44h] [rbp-45h] BYREF
  unsigned int dwSdOutSize; // [rsp+48h] [rbp-41h] BYREF
  _ACL *pDacl; // [rsp+50h] [rbp-39h] BYREF
  void *pOwner; // [rsp+58h] [rbp-31h] BYREF
  void *pGroup; // [rsp+60h] [rbp-29h] BYREF
  _ACL *pSacl; // [rsp+68h] [rbp-21h] BYREF
  _SECURITY_DESCRIPTOR SdCopy; // [rsp+70h] [rbp-19h] BYREF
  unsigned __int8 RMControl; // [rsp+108h] [rbp+7Fh] BYREF

  *ppSdOut = 0;
  RMControl = 0;
  pOwner = 0;
  bOwnerDefaulted = 0;
  pGroup = 0;
  bGroupDefaulted = 0;
  v8 = 0;
  bSaclPresent = 0;
  memset(&SdCopy, 0, sizeof(SdCopy));
  pSacl = 0;
  bSaclDefaulted = 0;
  bDaclPresent = 0;
  pDacl = 0;
  bDaclDefaulted = 0;
  dwSdOutSize = 0;
  if ( !InitializeSecurityDescriptor(&SdCopy, 1u) )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
      ComTraceMessageT<long>(
        "onecore\\com\\combase\\common\\core\\securityutilities.cpp",
        "AddAcesToSecurityDescriptorViaApi",
        113,
        ERRORS,
        L"%!HRESULT!",
        v8);
    if ( v8 < 0 )
      return (unsigned int)v8;
  }
  if ( GetSecurityDescriptorRMControl(pSdIn, &RMControl) )
    SetSecurityDescriptorRMControl(&SdCopy, &RMControl);
  if ( !GetSecurityDescriptorOwner(pSdIn, &pOwner, &bOwnerDefaulted) )
  {
    v10 = GetLastError();
    v8 = v10;
    if ( v10 > 0 )
      v8 = (unsigned __int16)v10 | 0x80070000;
    if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
      ComTraceMessageT<long>(
        "onecore\\com\\combase\\common\\core\\securityutilities.cpp",
        "AddAcesToSecurityDescriptorViaApi",
        131,
        ERRORS,
        L"%!HRESULT!",
        v8);
  }
  if ( v8 < 0 )
    return (unsigned int)v8;
  if ( !SetSecurityDescriptorOwner(&SdCopy, pOwner, bOwnerDefaulted) )
  {
    v11 = GetLastError();
    v8 = v11;
    if ( v11 > 0 )
      v8 = (unsigned __int16)v11 | 0x80070000;
    if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
      ComTraceMessageT<long>(
        "onecore\\com\\combase\\common\\core\\securityutilities.cpp",
        "AddAcesToSecurityDescriptorViaApi",
        139,
        ERRORS,
        L"%!HRESULT!",
        v8);
    if ( v8 < 0 )
      return (unsigned int)v8;
  }
  if ( !GetSecurityDescriptorGroup(pSdIn, &pGroup, &bGroupDefaulted) )
  {
    v12 = GetLastError();
    v8 = v12;
    if ( v12 > 0 )
      v8 = (unsigned __int16)v12 | 0x80070000;
    if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
      ComTraceMessageT<long>(
        "onecore\\com\\combase\\common\\core\\securityutilities.cpp",
        "AddAcesToSecurityDescriptorViaApi",
        149,
        ERRORS,
        L"%!HRESULT!",
        v8);
    if ( v8 < 0 )
      return (unsigned int)v8;
  }
  if ( !SetSecurityDescriptorGroup(&SdCopy, pGroup, bGroupDefaulted) )
  {
    v13 = GetLastError();
    v8 = v13;
    if ( v13 > 0 )
      v8 = (unsigned __int16)v13 | 0x80070000;
    if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
      ComTraceMessageT<long>(
        "onecore\\com\\combase\\common\\core\\securityutilities.cpp",
        "AddAcesToSecurityDescriptorViaApi",
        157,
        ERRORS,
        L"%!HRESULT!",
        v8);
    if ( v8 < 0 )
      return (unsigned int)v8;
  }
  if ( !GetSecurityDescriptorSacl(pSdIn, &bSaclPresent, &pSacl, &bSaclDefaulted) )
  {
    v14 = GetLastError();
    v8 = v14;
    if ( v14 > 0 )
      v8 = (unsigned __int16)v14 | 0x80070000;
    if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
      ComTraceMessageT<long>(
        "onecore\\com\\combase\\common\\core\\securityutilities.cpp",
        "AddAcesToSecurityDescriptorViaApi",
        167,
        ERRORS,
        L"%!HRESULT!",
        v8);
    if ( v8 < 0 )
      return (unsigned int)v8;
  }
  if ( !SetSecurityDescriptorSacl(&SdCopy, bSaclPresent, pSacl, bSaclDefaulted) )
  {
    v15 = GetLastError();
    v8 = v15;
    if ( v15 > 0 )
      v8 = (unsigned __int16)v15 | 0x80070000;
    if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
      ComTraceMessageT<long>(
        "onecore\\com\\combase\\common\\core\\securityutilities.cpp",
        "AddAcesToSecurityDescriptorViaApi",
        175,
        ERRORS,
        L"%!HRESULT!",
        v8);
    if ( v8 < 0 )
      return (unsigned int)v8;
  }
  if ( !GetSecurityDescriptorDacl(pSdIn, &bDaclPresent, &pDacl, &bDaclDefaulted) )
  {
    v16 = GetLastError();
    v8 = v16;
    if ( v16 > 0 )
      v8 = (unsigned __int16)v16 | 0x80070000;
    if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
      ComTraceMessageT<long>(
        "onecore\\com\\combase\\common\\core\\securityutilities.cpp",
        "AddAcesToSecurityDescriptorViaApi",
        185,
        ERRORS,
        L"%!HRESULT!",
        v8);
    if ( v8 < 0 )
      return (unsigned int)v8;
  }
  v17 = 0;
  if ( !bDaclPresent || !pDacl )
  {
    v23 = 0;
    if ( SetSecurityDescriptorDacl(&SdCopy, bDaclPresent, pDacl, bDaclDefaulted) )
      goto LABEL_100;
    v28 = GetLastError();
    v8 = v28;
    if ( v28 > 0 )
      v8 = (unsigned __int16)v28 | 0x80070000;
    if ( !Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 && (!gfEnableTracing || !IsWppLevelEnabled(ERRORS)) )
      goto LABEL_99;
    v27 = 197;
    goto LABEL_98;
  }
  v18 = 0;
  for ( i = 0; i < cAcesIn; v18 += v20->AceSize )
    v20 = ppAcesIn[i++];
  v21 = v18 + pDacl->AclSize;
  v22 = (_ACL *)HeapAlloc(g_hHeap, 0, v21);
  v23 = v22;
  if ( !v22 )
    return (unsigned int)-2147024882;
  memcpy_0(v22, pDacl, pDacl->AclSize);
  v23->AclSize = v21;
  v24 = 0;
  while ( v24 < cAcesIn )
  {
    if ( !AddAce(v23, pDacl->AclRevision, 0xFFFFFFFF, ppAcesIn[v24], ppAcesIn[v24]->AceSize) )
    {
      v25 = GetLastError();
      v8 = v25;
      if ( v25 > 0 )
        v8 = (unsigned __int16)v25 | 0x80070000;
      if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
        ComTraceMessageT<long>(
          "onecore\\com\\combase\\common\\core\\securityutilities.cpp",
          "AddAcesToSecurityDescriptorViaApi",
          228,
          ERRORS,
          L"%!HRESULT!",
          v8);
    }
    ++v24;
    if ( v8 < 0 )
      goto LABEL_112;
  }
  if ( SetSecurityDescriptorDacl(&SdCopy, 1, v23, 0) )
    goto LABEL_100;
  v26 = GetLastError();
  v8 = v26;
  if ( v26 > 0 )
    v8 = (unsigned __int16)v26 | 0x80070000;
  if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
  {
    v27 = 239;
LABEL_98:
    ComTraceMessageT<long>(
      "onecore\\com\\combase\\common\\core\\securityutilities.cpp",
      "AddAcesToSecurityDescriptorViaApi",
      v27,
      ERRORS,
      L"%!HRESULT!",
      v8);
  }
LABEL_99:
  if ( v8 >= 0 )
  {
LABEL_100:
    dwSdOutSize = GetSecurityDescriptorLength(&SdCopy);
    v29 = HeapAlloc(g_hHeap, 0, dwSdOutSize);
    v17 = v29;
    if ( v29 )
    {
      if ( MakeSelfRelativeSD(&SdCopy, v29, &dwSdOutSize) )
        goto LABEL_110;
      v30 = GetLastError();
      v8 = v30;
      if ( v30 > 0 )
        v8 = (unsigned __int16)v30 | 0x80070000;
      if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
        ComTraceMessageT<long>(
          "onecore\\com\\combase\\common\\core\\securityutilities.cpp",
          "AddAcesToSecurityDescriptorViaApi",
          260,
          ERRORS,
          L"%!HRESULT!",
          v8);
      if ( v8 >= 0 )
      {
LABEL_110:
        *ppSdOut = v17;
        v17 = 0;
      }
    }
    else
    {
      v8 = -2147024882;
    }
  }
  if ( v23 )
LABEL_112:
    HeapFree(g_hHeap, 0, v23);
  if ( v17 )
    HeapFree(g_hHeap, 0, v17);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18005ef40  push    rbp
0x18005ef42  push    rbx
0x18005ef43  push    rsi
0x18005ef44  push    rdi
0x18005ef45  push    r12
0x18005ef47  push    r13
0x18005ef49  push    r14
0x18005ef4b  push    r15
0x18005ef4d  lea     rbp, [rsp-1Fh]
0x18005ef52  sub     rsp, 0A8h
0x18005ef59  xor     r14d, r14d
0x18005ef5c  xor     eax, eax
0x18005ef5e  xorps   xmm0, xmm0
0x18005ef61  mov     [ppSdOut], r14
0x18005ef64  mov     r12, ppAcesIn
0x18005ef67  mov     [rbp+57h+SdCopy.Dacl], rax
0x18005ef6b  mov     rdi, pSdIn
0x18005ef6e  mov     [rbp+57h+RMControl], r14b
0x18005ef72  lea     edx, [rax+1]; dwRevision
0x18005ef75  mov     [rbp+57h+pOwner], r14
0x18005ef79  lea     pSdIn, [rbp+57h+SdCopy]; pSecurityDescriptor
0x18005ef7d  mov     [rbp+57h+bOwnerDefaulted], r14d
0x18005ef81  mov     r13, ppSdOut
0x18005ef84  mov     [rbp+57h+pGroup], r14
0x18005ef88  mov     r15, cAcesIn
0x18005ef8b  mov     [rbp+57h+bGroupDefaulted], r14d
0x18005ef8f  mov     ebx, r14d
0x18005ef92  mov     [rbp+57h+bSaclPresent], r14d
0x18005ef96  movups  xmmword ptr [rbp+57h+SdCopy.Revision], xmm0
0x18005ef9a  mov     [rbp+57h+pSacl], r14
0x18005ef9e  movups  xmmword ptr [rbp+57h+SdCopy.Group], xmm0
0x18005efa2  mov     [rbp+57h+bSaclDefaulted], r14d
0x18005efa6  mov     [rbp+57h+bDaclPresent], r14d
0x18005efaa  mov     [rbp+57h+pDacl], r14
0x18005efae  mov     [rbp+57h+bDaclDefaulted], r14d
0x18005efb2  mov     [rbp+57h+dwSdOutSize], r14d
0x18005efb6  call    cs:__imp_InitializeSecurityDescriptor
0x18005efbc  mov     esi, 80070000h
0x18005efc1  test    eax, eax
0x18005efc3  jnz     short loc_18005F026
0x18005efc5  call    cs:__imp_GetLastError
0x18005efcb  mov     ebx, eax
0x18005efcd  test    eax, eax
0x18005efcf  jle     short loc_18005EFD6
0x18005efd1  movzx   ebx, ax
0x18005efd4  or      ebx, esi
0x18005efd6  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x18005efdc  test    eax, eax
0x18005efde  jnz     short loc_18005EFF4
0x18005efe0  cmp     cs:?gfEnableTracing@@3HA, r14d; int gfEnableTracing
0x18005efe7  jz      short loc_18005F01E
0x18005efe9  xor     ecx, ecx; level
0x18005efeb  call    IsWppLevelEnabled
0x18005eff0  test    al, al
0x18005eff2  jz      short loc_18005F01E
0x18005eff4  xor     r9d, r9d; level
0x18005eff7  mov     [rsp+0E0h+var_B8], ebx; <args_0>
0x18005effb  lea     rax, aHresult; "%!HRESULT!"
0x18005f002  lea     ppAcesIn, aAddacestosecur; "AddAcesToSecurityDescriptorViaApi"
0x18005f009  mov     [rsp+0E0h+format], rax; format
0x18005f00e  lea     pSdIn, aOnecoreComComb_149; "onecore\\com\\combase\\common\\core\\se"...
0x18005f015  lea     r8d, [ppSdOut+71h]; line
0x18005f019  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x18005f01e  test    ebx, ebx
0x18005f020  js      loc_18005F66B
0x18005f026  lea     ppAcesIn, [rbp+57h+RMControl]; RMControl
0x18005f02a  mov     pSdIn, rdi; SecurityDescriptor
0x18005f02d  call    cs:__imp_GetSecurityDescriptorRMControl
0x18005f033  test    eax, eax
0x18005f035  jz      short loc_18005F045
0x18005f037  lea     ppAcesIn, [rbp+57h+RMControl]; RMControl
0x18005f03b  lea     pSdIn, [rbp+57h+SdCopy]; SecurityDescriptor
0x18005f03f  call    cs:__imp_SetSecurityDescriptorRMControl
0x18005f045  lea     cAcesIn, [rbp+57h+bOwnerDefaulted]; lpbOwnerDefaulted
0x18005f049  mov     pSdIn, rdi; pSecurityDescriptor
0x18005f04c  lea     ppAcesIn, [rbp+57h+pOwner]; pOwner
0x18005f050  call    cs:__imp_GetSecurityDescriptorOwner
0x18005f056  test    eax, eax
0x18005f058  jnz     short loc_18005F0B5
0x18005f05a  call    cs:__imp_GetLastError
0x18005f060  mov     ebx, eax
0x18005f062  test    eax, eax
0x18005f064  jle     short loc_18005F06B
0x18005f066  movzx   ebx, ax
0x18005f069  or      ebx, esi
0x18005f06b  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x18005f071  test    eax, eax
0x18005f073  jnz     short loc_18005F089
0x18005f075  cmp     cs:?gfEnableTracing@@3HA, r14d; int gfEnableTracing
0x18005f07c  jz      short loc_18005F0B5
0x18005f07e  xor     ecx, ecx; level
0x18005f080  call    IsWppLevelEnabled
0x18005f085  test    al, al
0x18005f087  jz      short loc_18005F0B5
0x18005f089  lea     rax, aHresult; "%!HRESULT!"
0x18005f090  mov     [rsp+0E0h+var_B8], ebx; <args_0>
0x18005f094  xor     r9d, r9d; level
0x18005f097  mov     [rsp+0E0h+format], rax; format
0x18005f09c  mov     r8d, 83h; line
0x18005f0a2  lea     ppAcesIn, aAddacestosecur; "AddAcesToSecurityDescriptorViaApi"
0x18005f0a9  lea     pSdIn, aOnecoreComComb_149; "onecore\\com\\combase\\common\\core\\se"...
0x18005f0b0  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x18005f0b5  test    ebx, ebx
0x18005f0b7  js      loc_18005F66B
0x18005f0bd  mov     r8d, [rbp+57h+bOwnerDefaulted]; bOwnerDefaulted
0x18005f0c1  lea     pSdIn, [rbp+57h+SdCopy]; pSecurityDescriptor
0x18005f0c5  mov     ppAcesIn, [rbp+57h+pOwner]; pOwner
0x18005f0c9  call    cs:__imp_SetSecurityDescriptorOwner
0x18005f0cf  test    eax, eax
0x18005f0d1  jnz     short loc_18005F136
0x18005f0d3  call    cs:__imp_GetLastError
0x18005f0d9  mov     ebx, eax
0x18005f0db  test    eax, eax
0x18005f0dd  jle     short loc_18005F0E4
0x18005f0df  movzx   ebx, ax
0x18005f0e2  or      ebx, esi
0x18005f0e4  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x18005f0ea  test    eax, eax
0x18005f0ec  jnz     short loc_18005F102
0x18005f0ee  cmp     cs:?gfEnableTracing@@3HA, r14d; int gfEnableTracing
0x18005f0f5  jz      short loc_18005F12E
0x18005f0f7  xor     ecx, ecx; level
0x18005f0f9  call    IsWppLevelEnabled
0x18005f0fe  test    al, al
0x18005f100  jz      short loc_18005F12E
0x18005f102  lea     rax, aHresult; "%!HRESULT!"
0x18005f109  mov     [rsp+0E0h+var_B8], ebx; <args_0>
0x18005f10d  xor     r9d, r9d; level
0x18005f110  mov     [rsp+0E0h+format], rax; format
0x18005f115  mov     r8d, 8Bh; line
0x18005f11b  lea     ppAcesIn, aAddacestosecur; "AddAcesToSecurityDescriptorViaApi"
0x18005f122  lea     pSdIn, aOnecoreComComb_149; "onecore\\com\\combase\\common\\core\\se"...
0x18005f129  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x18005f12e  test    ebx, ebx
0x18005f130  js      loc_18005F66B
0x18005f136  lea     cAcesIn, [rbp+57h+bGroupDefaulted]; lpbGroupDefaulted
0x18005f13a  mov     pSdIn, rdi; pSecurityDescriptor
0x18005f13d  lea     ppAcesIn, [rbp+57h+pGroup]; pGroup
0x18005f141  call    cs:__imp_GetSecurityDescriptorGroup
0x18005f147  test    eax, eax
0x18005f149  jnz     short loc_18005F1AE
0x18005f14b  call    cs:__imp_GetLastError
0x18005f151  mov     ebx, eax
0x18005f153  test    eax, eax
0x18005f155  jle     short loc_18005F15C
0x18005f157  movzx   ebx, ax
0x18005f15a  or      ebx, esi
0x18005f15c  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x18005f162  test    eax, eax
0x18005f164  jnz     short loc_18005F17A
0x18005f166  cmp     cs:?gfEnableTracing@@3HA, r14d; int gfEnableTracing
0x18005f16d  jz      short loc_18005F1A6
0x18005f16f  xor     ecx, ecx; level
0x18005f171  call    IsWppLevelEnabled
0x18005f176  test    al, al
0x18005f178  jz      short loc_18005F1A6
0x18005f17a  lea     rax, aHresult; "%!HRESULT!"
0x18005f181  mov     [rsp+0E0h+var_B8], ebx; <args_0>
0x18005f185  xor     r9d, r9d; level
0x18005f188  mov     [rsp+0E0h+format], rax; format
0x18005f18d  mov     r8d, 95h; line
0x18005f193  lea     ppAcesIn, aAddacestosecur; "AddAcesToSecurityDescriptorViaApi"
0x18005f19a  lea     pSdIn, aOnecoreComComb_149; "onecore\\com\\combase\\common\\core\\se"...
0x18005f1a1  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x18005f1a6  test    ebx, ebx
0x18005f1a8  js      loc_18005F66B
0x18005f1ae  mov     r8d, [rbp+57h+bGroupDefaulted]; bGroupDefaulted
0x18005f1b2  lea     pSdIn, [rbp+57h+SdCopy]; pSecurityDescriptor
0x18005f1b6  mov     ppAcesIn, [rbp+57h+pGroup]; pGroup
0x18005f1ba  call    cs:__imp_SetSecurityDescriptorGroup
0x18005f1c0  test    eax, eax
0x18005f1c2  jnz     short loc_18005F227
0x18005f1c4  call    cs:__imp_GetLastError
0x18005f1ca  mov     ebx, eax
0x18005f1cc  test    eax, eax
0x18005f1ce  jle     short loc_18005F1D5
0x18005f1d0  movzx   ebx, ax
0x18005f1d3  or      ebx, esi
0x18005f1d5  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x18005f1db  test    eax, eax
0x18005f1dd  jnz     short loc_18005F1F3
0x18005f1df  cmp     cs:?gfEnableTracing@@3HA, r14d; int gfEnableTracing
0x18005f1e6  jz      short loc_18005F21F
0x18005f1e8  xor     ecx, ecx; level
0x18005f1ea  call    IsWppLevelEnabled
0x18005f1ef  test    al, al
0x18005f1f1  jz      short loc_18005F21F
0x18005f1f3  lea     rax, aHresult; "%!HRESULT!"
0x18005f1fa  mov     [rsp+0E0h+var_B8], ebx; <args_0>
0x18005f1fe  xor     r9d, r9d; level
0x18005f201  mov     [rsp+0E0h+format], rax; format
0x18005f206  mov     r8d, 9Dh; line
0x18005f20c  lea     ppAcesIn, aAddacestosecur; "AddAcesToSecurityDescriptorViaApi"
0x18005f213  lea     pSdIn, aOnecoreComComb_149; "onecore\\com\\combase\\common\\core\\se"...
0x18005f21a  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x18005f21f  test    ebx, ebx
0x18005f221  js      loc_18005F66B
0x18005f227  lea     ppSdOut, [rbp+57h+bSaclDefaulted]; lpbSaclDefaulted
0x18005f22b  mov     pSdIn, rdi; pSecurityDescriptor
0x18005f22e  lea     cAcesIn, [rbp+57h+pSacl]; pSacl
0x18005f232  lea     ppAcesIn, [rbp+57h+bSaclPresent]; lpbSaclPresent
0x18005f236  call    cs:__imp_GetSecurityDescriptorSacl
0x18005f23c  test    eax, eax
0x18005f23e  jnz     short loc_18005F2A3
0x18005f240  call    cs:__imp_GetLastError
0x18005f246  mov     ebx, eax
0x18005f248  test    eax, eax
0x18005f24a  jle     short loc_18005F251
0x18005f24c  movzx   ebx, ax
0x18005f24f  or      ebx, esi
0x18005f251  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x18005f257  test    eax, eax
0x18005f259  jnz     short loc_18005F26F
0x18005f25b  cmp     cs:?gfEnableTracing@@3HA, r14d; int gfEnableTracing
0x18005f262  jz      short loc_18005F29B
0x18005f264  xor     ecx, ecx; level
0x18005f266  call    IsWppLevelEnabled
0x18005f26b  test    al, al
0x18005f26d  jz      short loc_18005F29B
0x18005f26f  lea     rax, aHresult; "%!HRESULT!"
0x18005f276  mov     [rsp+0E0h+var_B8], ebx; <args_0>
0x18005f27a  xor     r9d, r9d; level
0x18005f27d  mov     [rsp+0E0h+format], rax; format
0x18005f282  mov     r8d, 0A7h; line
0x18005f288  lea     ppAcesIn, aAddacestosecur; "AddAcesToSecurityDescriptorViaApi"
0x18005f28f  lea     pSdIn, aOnecoreComComb_149; "onecore\\com\\combase\\common\\core\\se"...
0x18005f296  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x18005f29b  test    ebx, ebx
0x18005f29d  js      loc_18005F66B
0x18005f2a3  mov     r9d, [rbp+57h+bSaclDefaulted]; bSaclDefaulted
0x18005f2a7  lea     pSdIn, [rbp+57h+SdCopy]; pSecurityDescriptor
0x18005f2ab  mov     cAcesIn, [rbp+57h+pSacl]; pSacl
0x18005f2af  mov     edx, [rbp+57h+bSaclPresent]; bSaclPresent
0x18005f2b2  call    cs:__imp_SetSecurityDescriptorSacl
0x18005f2b8  test    eax, eax
0x18005f2ba  jnz     short loc_18005F31F
0x18005f2bc  call    cs:__imp_GetLastError
0x18005f2c2  mov     ebx, eax
0x18005f2c4  test    eax, eax
0x18005f2c6  jle     short loc_18005F2CD
0x18005f2c8  movzx   ebx, ax
0x18005f2cb  or      ebx, esi
0x18005f2cd  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x18005f2d3  test    eax, eax
0x18005f2d5  jnz     short loc_18005F2EB
0x18005f2d7  cmp     cs:?gfEnableTracing@@3HA, r14d; int gfEnableTracing
0x18005f2de  jz      short loc_18005F317
0x18005f2e0  xor     ecx, ecx; level
0x18005f2e2  call    IsWppLevelEnabled
0x18005f2e7  test    al, al
0x18005f2e9  jz      short loc_18005F317
0x18005f2eb  lea     rax, aHresult; "%!HRESULT!"
0x18005f2f2  mov     [rsp+0E0h+var_B8], ebx; <args_0>
0x18005f2f6  xor     r9d, r9d; level
0x18005f2f9  mov     [rsp+0E0h+format], rax; format
0x18005f2fe  mov     r8d, 0AFh; line
0x18005f304  lea     ppAcesIn, aAddacestosecur; "AddAcesToSecurityDescriptorViaApi"
0x18005f30b  lea     pSdIn, aOnecoreComComb_149; "onecore\\com\\combase\\common\\core\\se"...
0x18005f312  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x18005f317  test    ebx, ebx
0x18005f319  js      loc_18005F66B
0x18005f31f  lea     ppSdOut, [rbp+57h+bDaclDefaulted]; lpbDaclDefaulted
0x18005f323  mov     pSdIn, rdi; pSecurityDescriptor
0x18005f326  lea     cAcesIn, [rbp+57h+pDacl]; pDacl
0x18005f32a  lea     ppAcesIn, [rbp+57h+bDaclPresent]; lpbDaclPresent
0x18005f32e  call    cs:__imp_GetSecurityDescriptorDacl
0x18005f334  test    eax, eax
0x18005f336  jnz     short loc_18005F39B
0x18005f338  call    cs:__imp_GetLastError
0x18005f33e  mov     ebx, eax
0x18005f340  test    eax, eax
0x18005f342  jle     short loc_18005F349
0x18005f344  movzx   ebx, ax
0x18005f347  or      ebx, esi
0x18005f349  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x18005f34f  test    eax, eax
0x18005f351  jnz     short loc_18005F367
0x18005f353  cmp     cs:?gfEnableTracing@@3HA, r14d; int gfEnableTracing
0x18005f35a  jz      short loc_18005F393
0x18005f35c  xor     ecx, ecx; level
0x18005f35e  call    IsWppLevelEnabled
0x18005f363  test    al, al
0x18005f365  jz      short loc_18005F393
0x18005f367  lea     rax, aHresult; "%!HRESULT!"
0x18005f36e  mov     [rsp+0E0h+var_B8], ebx; <args_0>
0x18005f372  xor     r9d, r9d; level
0x18005f375  mov     [rsp+0E0h+format], rax; format
0x18005f37a  mov     r8d, 0B9h; line
0x18005f380  lea     ppAcesIn, aAddacestosecur; "AddAcesToSecurityDescriptorViaApi"
0x18005f387  lea     pSdIn, aOnecoreComComb_149; "onecore\\com\\combase\\common\\core\\se"...
0x18005f38e  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x18005f393  test    ebx, ebx
0x18005f395  js      loc_18005F66B
0x18005f39b  mov     edx, [rbp+57h+bDaclPresent]; bDaclPresent
0x18005f39e  mov     rsi, r14
0x18005f3a1  mov     cAcesIn, [rbp+57h+pDacl]; pDacl
0x18005f3a5  test    edx, edx
0x18005f3a7  jz      loc_18005F513
0x18005f3ad  test    cAcesIn, cAcesIn
0x18005f3b0  jz      loc_18005F513
  ... truncated ...
```
