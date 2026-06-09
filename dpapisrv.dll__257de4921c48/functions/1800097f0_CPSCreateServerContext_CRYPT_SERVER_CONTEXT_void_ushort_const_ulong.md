# CPSCreateServerContext(CRYPT_SERVER_CONTEXT *,void *,ushort const * *,ulong *)

- ea: `0x1800097f0`
- end: `0x18000a325`
- name: `?CPSCreateServerContext@@YAKPEAUCRYPT_SERVER_CONTEXT@@PEAXPEAPEBGPEAK@Z`
- size: `2869`
- prototype: `__int64 __fastcall(struct CRYPT_SERVER_CONTEXT *, void *, const unsigned __int16 **, unsigned int *)`
- caller_count: `13`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000ce90`
- `0x18000d540`
- `0x18000e0c0`
- `0x180010870`
- `0x18001b72c`
- `0x18001cd50`
- `0x180024670`
- `0x18002ae48`
- `0x18002b0ec`
- `0x18002c0a0`
- `0x18002ca70`
- `0x180038d40`
- `0x180039190`

## callees

- `0x180007f10`
- `0x1800097f0`
- `0x18000a32c`
- `0x18001d810`
- `0x18001e1b4`
- `0x18001eb8c`
- `0x18003e010`

## import_xrefs

- `RPCRT4!RpcRevertToSelfEx` at `0x180009f1b`
- `RPCRT4!RpcRevertToSelfEx` at `0x18000a307`
- `RPCRT4!RpcRevertToSelfEx` at `0x180009f1b`
- `RPCRT4!RpcRevertToSelfEx` at `0x18000a307`
- `RPCRT4!RpcImpersonateClient` at `0x180009f33`
- `RPCRT4!RpcImpersonateClient` at `0x180009f33`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800098dd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800099fe`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180009cd1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180009d68`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800098dd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800099fe`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180009cd1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180009d68`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000a050`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000a050`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180009a16`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180009a16`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180009a4a`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180009a4a`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180009cfb`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180009cfb`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000a279`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000a279`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009d16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009dc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009f01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009f88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a0b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a0ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a0f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a137`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a1c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a28d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a2a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009d16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009dc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009f01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009f88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a0b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a0ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a0f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a137`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a1c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a28d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a2a1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800098a1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180009da3`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800098a1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180009da3`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000a01f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000a01f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180009eed`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180009eed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000a006`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000a006`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180009884`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180009d84`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180009884`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180009d84`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180009b8e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180009bba`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180009be6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180009c12`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180009c3e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180009b8e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180009bba`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180009be6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180009c12`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180009c3e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009a6f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009b1f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009ff5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a156`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a1e2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a254`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a268`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009a6f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009b1f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009ff5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a156`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a1e2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a254`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a268`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009a2c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009d34`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a168`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a1f4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009a2c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009d34`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a168`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a1f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a069`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a126`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a2cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a069`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a126`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a2cf`
- `ntdll!RtlEqualSid` at `0x180009970`
- `ntdll!RtlEqualSid` at `0x180009970`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180009ab5`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180009ab5`

## string_xrefs

- `0x180009921`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32.cpp`
- `0x180009ded`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32.cpp`
- `0x180009fc2`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32.cpp`
- `0x18000a09c`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32.cpp`
- `0x18000a0dc`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32.cpp`
- `0x18000a10a`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32.cpp`
- `0x18000a186`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32.cpp`
- `0x18000a1a9`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32.cpp`
- `0x18000a211`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32.cpp`
- `0x18000a237`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32.cpp`
- `0x18000a2b3`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32.cpp`

## pseudocode

```c
__int64 __fastcall CPSCreateServerContext(
        struct CRYPT_SERVER_CONTEXT *a1,
        void *a2,
        const unsigned __int16 **a3,
        unsigned int *a4)
{
  RPC_BINDING_HANDLE v4; // rdi
  int v5; // esi
  HANDLE *v7; // r14
  HANDLE CurrentThread; // rax
  int v9; // edx
  HANDLE v10; // rdi
  BOOL v11; // r15d
  PSID *v12; // rsi
  int v13; // ebx
  _BYTE *v14; // rdi
  HANDLE v15; // rbx
  HLOCAL v16; // r14
  int v17; // esi
  HANDLE v18; // rcx
  PSID *v19; // r12
  SIZE_T LengthSid; // r15
  HLOCAL v21; // rax
  void *v22; // rdi
  void *v23; // rcx
  int v24; // edi
  BOOL v25; // eax
  LPWSTR v26; // r10
  __int64 v27; // rcx
  LPWSTR v28; // rdx
  __int64 v29; // r8
  _WORD *v30; // r9
  _WORD *v31; // rdx
  __int64 v32; // rcx
  _WORD *v33; // rax
  unsigned __int64 v34; // rbx
  int v35; // eax
  __int64 v36; // rbx
  HANDLE v38; // rax
  int v39; // edx
  DWORD v40; // eax
  __int64 v41; // r9
  unsigned int v42; // eax
  const unsigned __int16 **v43; // rcx
  int v44; // edx
  HANDLE CurrentProcess; // rax
  DWORD LastError; // eax
  __int64 v47; // r9
  DWORD v48; // eax
  DWORD v49; // eax
  RPC_STATUS v50; // eax
  DWORD TokenInformationLength; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbSid[2]; // [rsp+48h] [rbp-B8h] BYREF
  int v53; // [rsp+50h] [rbp-B0h]
  RPC_BINDING_HANDLE BindingHandle; // [rsp+58h] [rbp-A8h]
  LPWSTR StringSid; // [rsp+60h] [rbp-A0h] BYREF
  void *TokenHandle; // [rsp+68h] [rbp-98h] BYREF
  DWORD ReturnLength; // [rsp+70h] [rbp-90h] BYREF
  unsigned int *v58; // [rsp+78h] [rbp-88h]
  const unsigned __int16 **v59; // [rsp+80h] [rbp-80h]
  _OWORD TokenInformation[3]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v61; // [rsp+B8h] [rbp-48h]
  _BYTE hMem[32]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE Sid1[80]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v64[256]; // [rsp+130h] [rbp+30h] BYREF

  v59 = a3;
  BindingHandle = a2;
  v4 = a2;
  TokenHandle = 0;
  ReturnLength = 0;
  v61 = 0;
  v53 = 0;
  memset(TokenInformation, 0, sizeof(TokenInformation));
  v5 = 0;
  StringSid = 0;
  v58 = a4;
  memset_0(a1, 0, 0x270u);
  *(_DWORD *)a1 = 624;
  *((_QWORD *)a1 + 1) = v4;
  if ( v4 )
  {
    v42 = RpcImpersonateClient(v4);
    LODWORD(v36) = v42;
    if ( v42 )
    {
      DebugTraceError(v42, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32.cpp", 313);
      return (unsigned int)v36;
    }
    v5 = 1;
    v53 = 1;
  }
  v7 = (HANDLE *)((char *)a1 + 24);
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xEu, 1, (PHANDLE)a1 + 3) )
  {
    *((_DWORD *)a1 + 5) = v4 == 0;
  }
  else
  {
    LODWORD(v36) = GetLastError();
    if ( (_DWORD)v36 != 1008 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_sDsd(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          v44,
          (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
          (unsigned int)"dwLastError",
          v36,
          (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32.cpp",
          81);
      goto LABEL_62;
    }
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 0xEu, &TokenHandle) )
    {
      LastError = GetLastError();
      v47 = 352;
LABEL_108:
      LODWORD(v36) = LastError;
      DebugTraceError(LastError, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32.cpp", v47);
      goto LABEL_62;
    }
    if ( !DuplicateTokenEx(TokenHandle, 0, 0, SecurityImpersonation, TokenImpersonation, (PHANDLE)a1 + 3) )
    {
      v36 = GetLastError();
      DebugTraceError(v36, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32.cpp", 366);
      CloseHandle(TokenHandle);
      goto LABEL_62;
    }
    CloseHandle(TokenHandle);
  }
  if ( !GetTokenInformation(*v7, TokenStatistics, TokenInformation, 0x38u, &ReturnLength) )
  {
    LastError = GetLastError();
    v47 = 384;
    goto LABEL_108;
  }
  *(_QWORD *)((char *)a1 + 60) = *((_QWORD *)&TokenInformation[0] + 1);
  if ( v5 )
  {
    RpcRevertToSelfEx(v4);
    v53 = 0;
  }
  v10 = *v7;
  TokenInformationLength = 32;
  cbSid[0] = 68;
  if ( v10 )
  {
    v11 = 0;
    v12 = (PSID *)hMem;
    v13 = 122;
    while ( v13 == 122 )
    {
      if ( GetTokenInformation(v10, TokenIntegrityLevel, v12, TokenInformationLength, &TokenInformationLength) )
      {
        v13 = 0;
      }
      else
      {
        v48 = GetLastError();
        v13 = v48;
        if ( v48 != 122 )
        {
          DebugTraceError(v48, "dwError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32.cpp", 98);
          goto LABEL_16;
        }
        if ( v12 != (PSID *)hMem )
          LocalFree(v12);
        v12 = (PSID *)LocalAlloc(0, TokenInformationLength);
        if ( !v12 )
        {
          DebugTraceError(14, "dwError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32.cpp", 92);
          goto LABEL_20;
        }
      }
    }
    v14 = Sid1;
    v13 = 122;
    while ( 1 )
    {
      while ( 1 )
      {
        if ( v13 != 122 )
        {
          v13 = 0;
          v11 = RtlEqualSid(v14, *v12) != 0;
          goto LABEL_13;
        }
        if ( !CreateWellKnownSid(WinLowLabelSid, 0, v14, cbSid) )
          break;
        v13 = 0;
      }
      v49 = GetLastError();
      v13 = v49;
      if ( v49 != 122 )
        break;
      if ( v14 != Sid1 )
        LocalFree(v14);
      v14 = LocalAlloc(0, cbSid[0]);
      if ( !v14 )
      {
        v13 = 14;
        DebugTraceError(14, "dwError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32.cpp", 130);
        goto LABEL_16;
      }
    }
    DebugTraceError(v49, "dwError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32.cpp", 136);
LABEL_13:
    if ( v14 && v14 != Sid1 )
      LocalFree(v14);
LABEL_16:
    if ( v12 && v12 != (PSID *)hMem )
      LocalFree(v12);
    if ( !v13 && v11 )
    {
      if ( *((_DWORD *)a1 + 5) && !RevertToSelf() )
      {
        v40 = GetLastError();
        v41 = 419;
        goto LABEL_125;
      }
      if ( !CPSGetMediumIntegrityToken(*v7, (void **)&StringSid) )
      {
        *((_QWORD *)a1 + 4) = *v7;
        *v7 = StringSid;
      }
      if ( *((_DWORD *)a1 + 5) && !SetThreadToken(0, *v7) )
      {
        v40 = GetLastError();
        v41 = 441;
        goto LABEL_125;
      }
    }
  }
  else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    WPP_SF_sDsd(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      v9,
      (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
      (unsigned int)"dwError",
      87,
      (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32.cpp",
      62);
  }
LABEL_20:
  v15 = *v7;
  v16 = 0;
  TokenInformationLength = 0;
  v17 = 0;
  *(_QWORD *)cbSid = 0;
  *((_QWORD *)a1 + 9) = 0;
  if ( v15 )
  {
    v18 = v15;
    *(_QWORD *)cbSid = v15;
  }
  else
  {
    v38 = GetCurrentThread();
    if ( !OpenThreadToken(v38, 8u, 1, (PHANDLE)cbSid) )
      goto LABEL_28;
    v18 = *(HANDLE *)cbSid;
  }
  TokenInformationLength = 256;
  v19 = (PSID *)v64;
  if ( GetTokenInformation(v18, TokenUser, v64, 0x100u, &TokenInformationLength) || GetLastError() != 122 )
    goto LABEL_23;
  v16 = LocalAlloc(0x40u, TokenInformationLength);
  if ( v16 )
  {
    if ( !GetTokenInformation(*(HANDLE *)cbSid, TokenUser, v16, TokenInformationLength, &TokenInformationLength) )
    {
LABEL_27:
      LocalFree(v16);
      goto LABEL_28;
    }
    v19 = (PSID *)v16;
LABEL_23:
    LengthSid = GetLengthSid(*v19);
    v21 = LocalAlloc(0x40u, LengthSid);
    v22 = v21;
    if ( v21 )
    {
      if ( CopySid(LengthSid, v21, *v19) )
      {
        *((_QWORD *)a1 + 9) = v22;
        v17 = 1;
      }
      else
      {
        LocalFree(v22);
      }
    }
    if ( !v16 )
      goto LABEL_28;
    goto LABEL_27;
  }
LABEL_28:
  if ( *(_QWORD *)cbSid && *(HANDLE *)cbSid != v15 )
    CloseHandle(*(HANDLE *)cbSid);
  if ( v17 )
  {
    v23 = (void *)*((_QWORD *)a1 + 9);
    StringSid = 0;
    v24 = 0;
    v25 = ConvertSidToStringSidW(v23, &StringSid);
    v26 = StringSid;
    if ( v25 )
    {
      v27 = 2147483646;
      v28 = StringSid;
      v29 = 260;
      v30 = (_WORD *)((char *)a1 + 80);
      do
      {
        if ( !v27 )
          break;
        if ( !*v28 )
          break;
        *v30++ = *v28++;
        --v27;
        --v29;
      }
      while ( v29 );
      v31 = v30 - 1;
      if ( v29 )
        v31 = v30;
      *v31 = 0;
      if ( v29 )
        v24 = 1;
    }
    if ( v26 )
      LocalFree(v26);
    if ( v24 )
    {
      if ( a1 != (struct CRYPT_SERVER_CONTEXT *)-80LL )
      {
        v32 = 260;
        v33 = (_WORD *)((char *)a1 + 80);
        while ( *v33 )
        {
          ++v33;
          if ( !--v32 )
          {
            v34 = 0;
            v35 = -2147024809;
            goto LABEL_50;
          }
        }
        v34 = 260 - v32;
        v35 = 0;
LABEL_50:
        if ( v35 >= 0 && v34 <= 0x7FFFFFFF )
        {
          if ( CompareStringOrdinal((LPCWCH)a1 + 40, v34, L"S-1-5-18", 8, 0) == 2 )
          {
            *((_DWORD *)a1 + 12) = 18;
          }
          else if ( CompareStringOrdinal((LPCWCH)a1 + 40, v34, L"S-1-5-19", 8, 0) == 2 )
          {
            *((_DWORD *)a1 + 12) = 19;
          }
          else if ( CompareStringOrdinal((LPCWCH)a1 + 40, v34, L"S-1-5-20", 8, 0) == 2 )
          {
            *((_DWORD *)a1 + 12) = 20;
          }
          else if ( CompareStringOrdinal((LPCWCH)a1 + 40, v34, L"S-1-5-93-2-1", 12, 0) == 2 )
          {
            *((_DWORD *)a1 + 12) = 90;
          }
          else if ( CompareStringOrdinal((LPCWCH)a1 + 40, v34, L"S-1-5-93-2-2", 12, 0) == 2 )
          {
            *((_DWORD *)a1 + 12) = 91;
          }
        }
      }
      if ( !*((_DWORD *)a1 + 12) )
      {
        cbSid[0] = 0;
        if ( (*((int (__fastcall **)(char *, DWORD *))g_pDPAPILsasrvIfTable + 7))((char *)a1 + 60, cbSid) >= 0
          && (cbSid[0] & 0x10000000) != 0 )
        {
          *((_DWORD *)a1 + 12) = 99;
        }
      }
      if ( v58 )
      {
        v43 = v59;
        if ( v59 )
        {
          *((_DWORD *)a1 + 154) = *v58;
          *((_QWORD *)a1 + 76) = v43;
        }
      }
      LODWORD(v36) = 0;
    }
    else
    {
      LODWORD(v36) = GetLastError();
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_sDsd(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          v39,
          (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
          (unsigned int)"dwLastError",
          v36,
          (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32.cpp",
          207);
    }
    goto LABEL_61;
  }
  v40 = GetLastError();
  v41 = 452;
LABEL_125:
  LODWORD(v36) = v40;
  DebugTraceError(v40, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32.cpp", v41);
LABEL_61:
  v4 = BindingHandle;
LABEL_62:
  if ( v53 )
  {
    v50 = RpcRevertToSelfEx(v4);
    if ( v50 )
    {
      if ( !(_DWORD)v36 )
        LODWORD(v36) = v50;
    }
  }
  return (unsigned int)v36;
}

```

## disassembly

```asm
0x1800097f0  push    rbp
0x1800097f2  push    rbx
0x1800097f3  push    rsi
0x1800097f4  push    rdi
0x1800097f5  push    r13
0x1800097f7  lea     rbp, [rsp-150h]
0x1800097ff  sub     rsp, 250h
0x180009806  mov     rax, cs:__security_cookie
0x18000980d  xor     rax, rsp
0x180009810  mov     [rbp+170h+var_40], rax
0x180009817  xor     ebx, ebx
0x180009819  mov     [rbp+170h+var_1F0], r8
0x18000981d  xorps   xmm0, xmm0
0x180009820  mov     [rsp+270h+BindingHandle], rdx
0x180009825  mov     rdi, rdx
0x180009828  mov     [rsp+270h+TokenHandle], rbx
0x18000982d  xor     eax, eax
0x18000982f  mov     [rsp+270h+var_200], ebx
0x180009833  xor     edx, edx; Val
0x180009835  mov     [rbp+170h+var_1B8], rax
0x180009839  mov     r8d, 270h; Size
0x18000983f  mov     [rsp+270h+var_220], ebx
0x180009843  movups  [rbp+170h+TokenInformation], xmm0
0x180009847  mov     esi, ebx
0x180009849  mov     [rsp+270h+StringSid], rbx
0x18000984e  movups  [rbp+170h+var_1D8], xmm0
0x180009852  mov     [rsp+270h+var_1F8], r9
0x180009857  mov     r13, rcx
0x18000985a  movups  [rbp+170h+var_1C8], xmm0
0x18000985e  call    memset_0
0x180009863  mov     dword ptr [r13+0], 270h
0x18000986b  mov     [r13+8], rdi
0x18000986f  test    rdi, rdi
0x180009872  jnz     loc_180009F30
0x180009878  mov     [rsp+270h+var_28], r14
0x180009880  lea     r14, [r13+18h]
0x180009884  call    cs:__imp_GetCurrentThread
0x18000988b  nop     dword ptr [rax+rax+00h]
0x180009890  mov     r9, r14; TokenHandle
0x180009893  mov     edx, 0Eh; DesiredAccess
0x180009898  mov     rcx, rax; ThreadHandle
0x18000989b  mov     r8d, 1; OpenAsSelf
0x1800098a1  call    cs:__imp_OpenThreadToken
0x1800098a8  nop     dword ptr [rax+rax+00h]
0x1800098ad  test    eax, eax
0x1800098af  jz      loc_180009F88
0x1800098b5  mov     eax, ebx
0x1800098b7  test    rdi, rdi
0x1800098ba  setz    al
0x1800098bd  mov     [r13+14h], eax
0x1800098c1  mov     rcx, [r14]; TokenHandle
0x1800098c4  lea     rax, [rsp+270h+var_200]
0x1800098c9  mov     r9d, 38h ; '8'; TokenInformationLength
0x1800098cf  mov     [rsp+270h+ReturnLength], rax; ReturnLength
0x1800098d4  lea     r8, [rbp+170h+TokenInformation]; TokenInformation
0x1800098d8  mov     edx, 0Ah; TokenInformationClass
0x1800098dd  call    cs:__imp_GetTokenInformation
0x1800098e4  nop     dword ptr [rax+rax+00h]
0x1800098e9  test    eax, eax
0x1800098eb  jz      loc_18000A0CA
0x1800098f1  mov     eax, dword ptr [rbp+170h+TokenInformation+0Ch]
0x1800098f4  mov     [r13+40h], eax
0x1800098f8  mov     eax, dword ptr [rbp+170h+TokenInformation+8]
0x1800098fb  mov     [r13+3Ch], eax
0x1800098ff  mov     [rsp+270h+arg_10], r12
0x180009907  test    esi, esi
0x180009909  jnz     loc_180009F18
0x18000990f  mov     rdi, [r14]
0x180009912  lea     r12, WPP_GLOBAL_Control
0x180009919  mov     [rsp+270h+var_30], r15
0x180009921  lea     rax, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180009928  mov     [rsp+270h+TokenInformationLength], 20h ; ' '
0x180009930  mov     [rsp+270h+cbSid], 44h ; 'D'
0x180009938  test    rdi, rdi
0x18000993b  jz      loc_180009E1D
0x180009941  mov     r15d, ebx
0x180009944  lea     rsi, [rbp+170h+hMem]
0x180009948  mov     ebx, 7Ah ; 'z'
0x18000994d  cmp     ebx, 7Ah ; 'z'
0x180009950  jz      loc_180009CB7
0x180009956  lea     rdi, [rbp+170h+Sid1]
0x18000995a  mov     ebx, 7Ah ; 'z'
0x18000995f  cmp     ebx, 7Ah ; 'z'
0x180009962  jz      loc_180009CEC
0x180009968  mov     rdx, [rsi]; Sid2
0x18000996b  mov     rcx, rdi; Sid1
0x18000996e  xor     ebx, ebx
0x180009970  call    cs:__imp_RtlEqualSid
0x180009977  nop     dword ptr [rax+rax+00h]
0x18000997c  xor     r15d, r15d
0x18000997f  test    al, al
0x180009981  setnz   r15b
0x180009985  test    rdi, rdi
0x180009988  jz      short loc_180009997
0x18000998a  lea     rax, [rbp+170h+Sid1]
0x18000998e  cmp     rdi, rax
0x180009991  jnz     loc_18000A251
0x180009997  test    rsi, rsi
0x18000999a  jz      short loc_1800099A9
0x18000999c  lea     rax, [rbp+170h+hMem]
0x1800099a0  cmp     rsi, rax
0x1800099a3  jnz     loc_18000A265
0x1800099a9  test    ebx, ebx
0x1800099ab  jz      loc_180009EA9
0x1800099b1  mov     rbx, [r14]
0x1800099b4  xor     r14d, r14d
0x1800099b7  mov     [rsp+270h+TokenInformationLength], r14d
0x1800099bc  mov     esi, r14d
0x1800099bf  mov     qword ptr [rsp+270h+cbSid], r14
0x1800099c4  mov     [r13+48h], r14
0x1800099c8  test    rbx, rbx
0x1800099cb  jz      loc_180009D84
0x1800099d1  mov     rcx, rbx; TokenHandle
0x1800099d4  mov     qword ptr [rsp+270h+cbSid], rbx
0x1800099d9  lea     rax, [rsp+270h+TokenInformationLength]
0x1800099de  mov     [rsp+270h+TokenInformationLength], 100h
0x1800099e6  mov     r9d, 100h; TokenInformationLength
0x1800099ec  mov     [rsp+270h+ReturnLength], rax; ReturnLength
0x1800099f1  lea     r8, [rbp+170h+var_140]; TokenInformation
0x1800099f5  mov     edx, 1; TokenInformationClass
0x1800099fa  lea     r12, [rbp+170h+var_140]
0x1800099fe  call    cs:__imp_GetTokenInformation
0x180009a05  nop     dword ptr [rax+rax+00h]
0x180009a0a  test    eax, eax
0x180009a0c  jz      loc_180009D16
0x180009a12  mov     rcx, [r12]; pSid
0x180009a16  call    cs:__imp_GetLengthSid
0x180009a1d  nop     dword ptr [rax+rax+00h]
0x180009a22  mov     edx, eax; uBytes
0x180009a24  mov     ecx, 40h ; '@'; uFlags
0x180009a29  mov     r15d, eax
0x180009a2c  call    cs:__imp_LocalAlloc
0x180009a33  nop     dword ptr [rax+rax+00h]
0x180009a38  mov     rdi, rax
0x180009a3b  test    rax, rax
0x180009a3e  jz      short loc_180009A67
0x180009a40  mov     r8, [r12]; pSourceSid
0x180009a44  mov     rdx, rax; pDestinationSid
0x180009a47  mov     ecx, r15d; nDestinationSidLength
0x180009a4a  call    cs:__imp_CopySid
0x180009a51  nop     dword ptr [rax+rax+00h]
0x180009a56  test    eax, eax
0x180009a58  jz      loc_180009FF2
0x180009a5e  mov     [r13+48h], rdi
0x180009a62  mov     esi, 1
0x180009a67  test    r14, r14
0x180009a6a  jz      short loc_180009A7B
0x180009a6c  mov     rcx, r14; hMem
0x180009a6f  call    cs:__imp_LocalFree
0x180009a76  nop     dword ptr [rax+rax+00h]
0x180009a7b  lea     r12, WPP_GLOBAL_Control
0x180009a82  xor     r14d, r14d
0x180009a85  mov     rcx, qword ptr [rsp+270h+cbSid]; hObject
0x180009a8a  test    rcx, rcx
0x180009a8d  jz      short loc_180009A98
0x180009a8f  cmp     rcx, rbx
0x180009a92  jnz     loc_18000A2CF
0x180009a98  test    esi, esi
0x180009a9a  jz      loc_18000A2A1
0x180009aa0  mov     rcx, [r13+48h]; Sid
0x180009aa4  lea     rdx, [rsp+270h+StringSid]; StringSid
0x180009aa9  lea     rsi, [r13+50h]
0x180009aad  mov     [rsp+270h+StringSid], r14
0x180009ab2  mov     edi, r14d
0x180009ab5  call    cs:__imp_ConvertSidToStringSidW
0x180009abc  nop     dword ptr [rax+rax+00h]
0x180009ac1  mov     r10, [rsp+270h+StringSid]
0x180009ac6  mov     ebx, 104h
0x180009acb  test    eax, eax
0x180009acd  jz      short loc_180009B17
0x180009acf  mov     ecx, 7FFFFFFEh
0x180009ad4  mov     rdx, r10
0x180009ad7  mov     r8d, ebx
0x180009ada  mov     r9, rsi
0x180009add  nop     dword ptr [rax]
0x180009ae0  test    rcx, rcx
0x180009ae3  jz      short loc_180009B02
0x180009ae5  movzx   eax, word ptr [rdx]
0x180009ae8  test    ax, ax
0x180009aeb  jz      short loc_180009B02
0x180009aed  mov     [r9], ax
0x180009af1  add     rdx, 2
0x180009af5  add     r9, 2
0x180009af9  dec     rcx
0x180009afc  sub     r8, 1
0x180009b00  jnz     short loc_180009AE0
0x180009b02  test    r8, r8
0x180009b05  lea     rdx, [r9-2]
0x180009b09  cmovnz  rdx, r9
0x180009b0d  mov     [rdx], r14w
0x180009b11  jnz     loc_18000A2E0
0x180009b17  test    r10, r10
0x180009b1a  jz      short loc_180009B2B
0x180009b1c  mov     rcx, r10; hMem
0x180009b1f  call    cs:__imp_LocalFree
0x180009b26  nop     dword ptr [rax+rax+00h]
0x180009b2b  test    edi, edi
0x180009b2d  jz      loc_180009DC1
0x180009b33  test    rsi, rsi
0x180009b36  jz      loc_180009C53
0x180009b3c  mov     rcx, rbx
0x180009b3f  mov     rax, rsi
0x180009b42  cmp     word ptr [rax], 0
0x180009b46  jz      short loc_180009B5C
0x180009b48  add     rax, 2
0x180009b4c  sub     rcx, 1
0x180009b50  jnz     short loc_180009B42
0x180009b52  mov     rbx, r14
0x180009b55  mov     eax, 80070057h
0x180009b5a  jmp     short loc_180009B62
0x180009b5c  sub     rbx, rcx
0x180009b5f  mov     eax, r14d
0x180009b62  test    eax, eax
0x180009b64  js      loc_180009C53
0x180009b6a  cmp     rbx, 7FFFFFFFh
0x180009b71  ja      loc_180009C53
0x180009b77  mov     r9d, 8; cchCount2
0x180009b7d  mov     dword ptr [rsp+270h+ReturnLength], r14d; bIgnoreCase
0x180009b82  lea     r8, String2; "S-1-5-18"
0x180009b89  mov     edx, ebx; cchCount1
0x180009b8b  mov     rcx, rsi; lpString1
0x180009b8e  call    cs:__imp_CompareStringOrdinal
0x180009b95  nop     dword ptr [rax+rax+00h]
0x180009b9a  cmp     eax, 2
0x180009b9d  jz      loc_180009F59
0x180009ba3  mov     r9d, 8; cchCount2
0x180009ba9  mov     dword ptr [rsp+270h+ReturnLength], r14d; bIgnoreCase
0x180009bae  lea     r8, aS1519; "S-1-5-19"
0x180009bb5  mov     edx, ebx; cchCount1
0x180009bb7  mov     rcx, rsi; lpString1
0x180009bba  call    cs:__imp_CompareStringOrdinal
0x180009bc1  nop     dword ptr [rax+rax+00h]
0x180009bc6  cmp     eax, 2
0x180009bc9  jz      loc_18000A07C
0x180009bcf  mov     r9d, 8; cchCount2
0x180009bd5  mov     dword ptr [rsp+270h+ReturnLength], r14d; bIgnoreCase
0x180009bda  lea     r8, aS1520; "S-1-5-20"
0x180009be1  mov     edx, ebx; cchCount1
0x180009be3  mov     rcx, rsi; lpString1
0x180009be6  call    cs:__imp_CompareStringOrdinal
0x180009bed  nop     dword ptr [rax+rax+00h]
0x180009bf2  cmp     eax, 2
0x180009bf5  jz      loc_18000A089
0x180009bfb  mov     r9d, 0Ch; cchCount2
0x180009c01  mov     dword ptr [rsp+270h+ReturnLength], r14d; bIgnoreCase
0x180009c06  lea     r8, aS159321; "S-1-5-93-2-1"
0x180009c0d  mov     edx, ebx; cchCount1
0x180009c0f  mov     rcx, rsi; lpString1
0x180009c12  call    cs:__imp_CompareStringOrdinal
0x180009c19  nop     dword ptr [rax+rax+00h]
0x180009c1e  cmp     eax, 2
0x180009c21  jz      loc_18000A2EA
0x180009c27  mov     r9d, 0Ch; cchCount2
0x180009c2d  mov     dword ptr [rsp+270h+ReturnLength], r14d; bIgnoreCase
0x180009c32  lea     r8, aS159322; "S-1-5-93-2-2"
0x180009c39  mov     edx, ebx; cchCount1
0x180009c3b  mov     rcx, rsi; lpString1
0x180009c3e  call    cs:__imp_CompareStringOrdinal
0x180009c45  nop     dword ptr [rax+rax+00h]
0x180009c4a  cmp     eax, 2
0x180009c4d  jz      loc_18000A2F7
0x180009c53  cmp     dword ptr [r13+30h], 0
0x180009c58  jz      loc_180009E68
0x180009c5e  mov     rax, [rsp+270h+var_1F8]
0x180009c63  test    rax, rax
0x180009c66  jnz     loc_180009F66
0x180009c6c  mov     ebx, r14d
0x180009c6f  mov     rdi, [rsp+270h+BindingHandle]
0x180009c74  mov     r15, [rsp+270h+var_30]
0x180009c7c  mov     r12, [rsp+270h+arg_10]
0x180009c84  cmp     [rsp+270h+var_220], 0
0x180009c89  mov     r14, [rsp+270h+var_28]
0x180009c91  jnz     loc_18000A304
0x180009c97  mov     eax, ebx
0x180009c99  mov     rcx, [rbp+170h+var_40]
0x180009ca0  xor     rcx, rsp; StackCookie
0x180009ca3  call    __security_check_cookie
0x180009ca8  add     rsp, 250h
0x180009caf  pop     r13
0x180009cb1  pop     rdi
0x180009cb2  pop     rsi
0x180009cb3  pop     rbx
0x180009cb4  pop     rbp
0x180009cb5  retn
0x180009cb7  mov     r9d, [rsp+270h+TokenInformationLength]; TokenInformationLength
0x180009cbc  lea     rax, [rsp+270h+TokenInformationLength]
0x180009cc1  mov     r8, rsi; TokenInformation
0x180009cc4  mov     [rsp+270h+ReturnLength], rax; ReturnLength
0x180009cc9  mov     edx, 19h; TokenInformationClass
0x180009cce  mov     rcx, rdi; TokenHandle
0x180009cd1  call    cs:__imp_GetTokenInformation
0x180009cd8  nop     dword ptr [rax+rax+00h]
0x180009cdd  test    eax, eax
0x180009cdf  jz      loc_18000A137
0x180009ce5  xor     ebx, ebx
0x180009ce7  jmp     loc_18000994D
0x180009cec  lea     r9, [rsp+270h+cbSid]; cbSid
0x180009cf1  mov     r8, rdi; pSid
0x180009cf4  xor     edx, edx; DomainSid
0x180009cf6  mov     ecx, 42h ; 'B'; WellKnownSidType
  ... truncated ...
```
