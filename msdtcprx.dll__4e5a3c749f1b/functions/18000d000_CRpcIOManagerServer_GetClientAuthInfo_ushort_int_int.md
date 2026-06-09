# CRpcIOManagerServer::GetClientAuthInfo(ushort * *,int *,int *)

- ea: `0x18000d000`
- end: `0x18000d5ee`
- name: `?GetClientAuthInfo@CRpcIOManagerServer@@AEAAJPEAPEAGPEAH1@Z`
- size: `1518`
- prototype: `int(CRpcIOManagerServer *__hidden this, unsigned __int16 **, int *, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800592a8`

## callees

- `0x180003cf0`
- `0x18000c6bc`
- `0x18000d000`
- `0x18000d5f4`
- `0x180016f64`
- `0x180019cb0`
- `0x18001d178`
- `0x18001d184`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x18000d113`
- `RPCRT4!RpcRevertToSelf` at `0x18000d44a`
- `RPCRT4!RpcRevertToSelf` at `0x18000d113`
- `RPCRT4!RpcRevertToSelf` at `0x18000d44a`
- `RPCRT4!RpcImpersonateClient` at `0x18000d04a`
- `RPCRT4!RpcImpersonateClient` at `0x18000d04a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d0c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d189`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d254`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d25f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d2d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d327`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d332`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d3e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d56e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d0c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d189`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d254`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d25f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d2d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d327`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d332`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d3e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d56e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000d0a4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000d0a4`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000d0bc`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000d0bc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d433`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d433`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18000d176`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18000d176`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000d24e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000d2ca`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000d24e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000d2ca`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18000d31d`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18000d3d5`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18000d31d`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18000d3d5`

## string_xrefs

- `0x18000d076`: `com\complus\dtc\dtc\cm\src\iomgrsrv.cpp`
- `0x18000d0f1`: `com\complus\dtc\dtc\cm\src\iomgrsrv.cpp`
- `0x18000d139`: `com\complus\dtc\dtc\cm\src\iomgrsrv.cpp`
- `0x18000d1f4`: `com\complus\dtc\dtc\cm\src\iomgrsrv.cpp`
- `0x18000d413`: `com\complus\dtc\dtc\cm\src\iomgrsrv.cpp`
- `0x18000d471`: `com\complus\dtc\dtc\cm\src\iomgrsrv.cpp`
- `0x18000d343`: `LookupAccountSid failed`
- `0x18000d3f4`: `LookupAccountSid failed`
- `0x18000d270`: `Call to GetTokenInformation failed`
- `0x18000d2e5`: `Call to GetTokenInformation failed`
- `0x18000d05d`: `call to RpcImpersonateClient failed`
- `0x18000d0df`: `Call to OpenThreadTokenFailed`
- `0x18000d57f`: `Call to LookupAccountSid failed`
- `0x18000d1b3`: `CheckTokenForAdmin`
- `0x18000d19a`: `Failed to check token for admin.`
- `0x18000d1ac`: `com\complus\dtc\shared\util\security.cpp`
- `0x18000d1d3`: `Error checking token for Admin`
- `0x18000d22a`: `Error checking token for WMI Service SID`
- `0x18000d50e`: `Unable to copy SPN in GetClientSPN.`
- `0x18000d53a`: `Failed to check token for computer`

## pseudocode

```c
__int64 __fastcall CRpcIOManagerServer::GetClientAuthInfo(
        CRpcIOManagerServer *this,
        unsigned __int16 **a2,
        int *a3,
        int *a4)
{
  PSID *v6; // r15
  WCHAR *v7; // r12
  int v8; // ebx
  int v9; // r14d
  WCHAR *v10; // r13
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  int v13; // eax
  void *v14; // rcx
  signed int v15; // eax
  const wchar_t *v16; // rax
  __int64 v17; // r9
  signed int v18; // eax
  signed int v19; // eax
  PSID v20; // r14
  signed int v21; // eax
  WCHAR *v22; // rax
  signed int v23; // eax
  const wchar_t *v24; // rax
  __int64 v25; // r9
  int v26; // eax
  unsigned __int64 v27; // rbx
  unsigned __int16 *v28; // rax
  CRpcIOManagerServer *v29; // rcx
  signed int v30; // eax
  LPDWORD cchReferencedDomainName; // [rsp+28h] [rbp-38h]
  LPDWORD cchReferencedDomainNamea; // [rsp+28h] [rbp-38h]
  DWORD v34; // [rsp+40h] [rbp-20h] BYREF
  DWORD TokenInformationLength; // [rsp+44h] [rbp-1Ch] BYREF
  DWORD cchName; // [rsp+48h] [rbp-18h] BYREF
  enum _SID_NAME_USE peUse[3]; // [rsp+4Ch] [rbp-14h] BYREF
  void *TokenHandle; // [rsp+58h] [rbp-8h] BYREF

  *a3 = 0;
  *a4 = 0;
  TokenHandle = 0;
  v6 = 0;
  TokenInformationLength = 0;
  v7 = 0;
  cchName = 0;
  v34 = 0;
  peUse[0] = 0;
  *a2 = 0;
  v8 = RpcImpersonateClient(0);
  if ( v8 )
  {
    LODWORD(cchReferencedDomainName) = v8;
    v9 = 0;
    TraceStringInline(
      1,
      1,
      L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrsrv.cpp",
      858,
      L"CRpcIOManagerServer::GetClientAuthInfo",
      cchReferencedDomainName,
      L"call to RpcImpersonateClient failed");
    if ( v8 > 0 )
      v8 = (unsigned __int16)v8 | 0x80070000;
LABEL_4:
    v10 = 0;
    goto LABEL_48;
  }
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    v9 = 1;
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    LODWORD(cchReferencedDomainName) = v8;
    TraceStringInline(
      1,
      1,
      L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrsrv.cpp",
      873,
      L"CRpcIOManagerServer::GetClientAuthInfo",
      cchReferencedDomainName,
      L"Call to OpenThreadTokenFailed");
    goto LABEL_4;
  }
  v13 = RpcRevertToSelf();
  if ( v13 )
  {
    if ( v13 > 0 )
      v13 = (unsigned __int16)v13 | 0x80070000;
    LODWORD(cchReferencedDomainName) = v13;
    TraceStringInline(
      1,
      1,
      L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrsrv.cpp",
      881,
      L"CRpcIOManagerServer::GetClientAuthInfo",
      cchReferencedDomainName,
      L"Call to RpcRevertToSelf failed");
    DtcInternalErrorW(L"Call to RpcRevertToSelf failed");
  }
  v14 = TokenHandle;
  *a4 = 0;
  if ( !CheckTokenMembership(v14, &AdministratorsSid, a4) )
  {
    v15 = GetLastError();
    v8 = v15;
    if ( v15 > 0 )
      v8 = (unsigned __int16)v15 | 0x80070000;
    LODWORD(cchReferencedDomainName) = v8;
    TraceStringInline(
      7,
      1,
      L"com\\complus\\dtc\\shared\\util\\security.cpp",
      1240,
      L"CheckTokenForAdmin",
      cchReferencedDomainName,
      L"Failed to check token for admin.");
    if ( v8 < 0 )
    {
      v16 = L"Error checking token for Admin";
      v17 = 896;
LABEL_18:
      LODWORD(cchReferencedDomainName) = v8;
      TraceStringInline(
        1,
        1,
        L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrsrv.cpp",
        v17,
        L"CRpcIOManagerServer::GetClientAuthInfo",
        cchReferencedDomainName,
        v16);
LABEL_19:
      v10 = 0;
      v9 = 0;
      goto LABEL_48;
    }
  }
  if ( !*a4 )
  {
    v8 = CRpcIOManagerServer::CheckTokenForWMIServiceSID(this, TokenHandle, a4);
    if ( v8 < 0 )
    {
      v16 = L"Error checking token for WMI Service SID";
      v17 = 910;
      goto LABEL_18;
    }
  }
  GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
  if ( GetLastError() != 122 )
  {
    v18 = GetLastError();
    v8 = v18;
    if ( v18 > 0 )
      v8 = (unsigned __int16)v18 | 0x80070000;
    v16 = L"Call to GetTokenInformation failed";
    v17 = 926;
    goto LABEL_18;
  }
  v6 = (PSID *)operator new[](TokenInformationLength);
  if ( !v6 )
  {
    v8 = -2147024882;
    LODWORD(cchReferencedDomainName) = -2147024882;
    TraceStringInline(
      1,
      1,
      L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrsrv.cpp",
      935,
      L"CRpcIOManagerServer::GetClientAuthInfo",
      cchReferencedDomainName,
      L"Unable to allocate memory");
    goto LABEL_19;
  }
  if ( !GetTokenInformation(TokenHandle, TokenUser, v6, TokenInformationLength, &TokenInformationLength) )
  {
    v19 = GetLastError();
    v8 = v19;
    if ( v19 > 0 )
      v8 = (unsigned __int16)v19 | 0x80070000;
    v16 = L"Call to GetTokenInformation failed";
    v17 = 948;
    goto LABEL_18;
  }
  v20 = *v6;
  if ( !LookupAccountSidW(0, *v6, 0, &cchName, 0, &v34, peUse) && GetLastError() != 122 )
  {
    v21 = GetLastError();
    v8 = v21;
    if ( v21 > 0 )
      v8 = (unsigned __int16)v21 | 0x80070000;
    v16 = L"LookupAccountSid failed";
    v17 = 966;
    goto LABEL_18;
  }
  if ( !cchName || !v34 )
  {
    v30 = GetLastError();
    v8 = v30;
    if ( v30 > 0 )
      v8 = (unsigned __int16)v30 | 0x80070000;
    v16 = L"Call to LookupAccountSid failed";
    v17 = 973;
    goto LABEL_18;
  }
  v10 = (WCHAR *)operator new[](saturated_mul(cchName, 2u));
  v22 = (WCHAR *)operator new[](saturated_mul(v34, 2u));
  v7 = v22;
  if ( !v10 || !v22 )
  {
    v8 = -2147024882;
    LODWORD(cchReferencedDomainName) = -2147024882;
    TraceStringInline(
      1,
      1,
      L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrsrv.cpp",
      984,
      L"CRpcIOManagerServer::GetClientAuthInfo",
      cchReferencedDomainName,
      L"Out of memory");
    goto LABEL_47;
  }
  if ( LookupAccountSidW(0, v20, v10, &cchName, v22, &v34, peUse) )
  {
    v27 = v34 + 2 + cchName;
    v28 = (unsigned __int16 *)operator new[](saturated_mul(v27, 2u));
    *a2 = v28;
    if ( !v28 )
    {
      v8 = -2147024882;
      LODWORD(cchReferencedDomainNamea) = -2147024882;
      TraceStringInline(
        1,
        1,
        L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrsrv.cpp",
        1010,
        L"CRpcIOManagerServer::GetClientAuthInfo",
        cchReferencedDomainNamea,
        L"Out of memory");
      goto LABEL_47;
    }
    v8 = StringCchPrintfW(v28, v27, L"%s\\%s", v7, v10);
    if ( v8 >= 0 )
    {
      v8 = CRpcIOManagerServer::CheckTokenForComputer(v29, TokenHandle, v20, a3);
      if ( v8 >= 0 )
        goto LABEL_47;
      v24 = L"Failed to check token for computer";
      v25 = 1030;
    }
    else
    {
      v24 = L"Unable to copy SPN in GetClientSPN.";
      v25 = 1021;
    }
  }
  else
  {
    v23 = GetLastError();
    v8 = v23;
    if ( v23 > 0 )
      v8 = (unsigned __int16)v23 | 0x80070000;
    v24 = L"LookupAccountSid failed";
    v25 = 998;
  }
  LODWORD(cchReferencedDomainNamea) = v8;
  TraceStringInline(
    1,
    1,
    L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrsrv.cpp",
    v25,
    L"CRpcIOManagerServer::GetClientAuthInfo",
    cchReferencedDomainNamea,
    v24);
LABEL_47:
  v9 = 0;
LABEL_48:
  if ( TokenHandle )
  {
    CloseHandle(TokenHandle);
    TokenHandle = 0;
  }
  if ( v9 )
  {
    v26 = RpcRevertToSelf();
    if ( v26 )
    {
      if ( v26 > 0 )
        v26 = (unsigned __int16)v26 | 0x80070000;
      LODWORD(cchReferencedDomainNamea) = v26;
      TraceStringInline(
        1,
        1,
        L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrsrv.cpp",
        1050,
        L"CRpcIOManagerServer::GetClientAuthInfo",
        cchReferencedDomainNamea,
        L"Call to RpcRevertToSelf failed");
      DtcInternalErrorW(L"Call to RpcRevertToSelf failed");
    }
  }
  if ( v8 < 0 && *a2 )
  {
    operator delete(*a2);
    *a2 = 0;
  }
  if ( v6 )
    operator delete(v6);
  if ( v10 )
    operator delete(v10);
  if ( v7 )
    operator delete(v7);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000d000  mov     [rsp-38h+arg_0], rbx
0x18000d005  mov     [rsp-38h+arg_10], r8
0x18000d00a  mov     [rsp-38h+arg_8], rdx
0x18000d00f  push    rbp
0x18000d010  push    rsi
0x18000d011  push    rdi
0x18000d012  push    r12
0x18000d014  push    r13
0x18000d016  push    r14
0x18000d018  push    r15
0x18000d01a  mov     rbp, rsp
0x18000d01d  sub     rsp, 60h
0x18000d021  xor     esi, esi
0x18000d023  mov     r13, rcx
0x18000d026  mov     [r8], esi
0x18000d029  xor     ecx, ecx; BindingHandle
0x18000d02b  mov     [r9], esi
0x18000d02e  mov     r14, r9
0x18000d031  mov     [rbp+TokenHandle], rsi
0x18000d035  mov     r15d, esi
0x18000d038  mov     [rbp+TokenInformationLength], esi
0x18000d03b  mov     r12d, esi
0x18000d03e  mov     [rbp+cchName], esi
0x18000d041  mov     [rbp+var_20], esi
0x18000d044  mov     [rbp+var_14], esi
0x18000d047  mov     [rdx], rsi
0x18000d04a  call    cs:__imp_RpcImpersonateClient
0x18000d050  lea     rcx, aCrpciomanagers_8; "CRpcIOManagerServer::GetClientAuthInfo"
0x18000d057  mov     ebx, eax
0x18000d059  test    eax, eax
0x18000d05b  jz      short loc_18000D0A4
0x18000d05d  lea     rax, aCallToRpcimper; "call to RpcImpersonateClient failed"
0x18000d064  mov     r9d, 35Ah
0x18000d06a  mov     [rsp+60h+peUse], rax
0x18000d06f  lea     edi, [rsi+1]
0x18000d072  mov     dword ptr [rsp+60h+cchReferencedDomainName], ebx
0x18000d076  lea     r8, aComComplusDtcD_34; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrs"...
0x18000d07d  mov     [rsp+60h+ReturnLength], rcx
0x18000d082  mov     edx, edi
0x18000d084  mov     ecx, edi
0x18000d086  mov     r14d, esi
0x18000d089  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18000d08e  mov     esi, 80070000h
0x18000d093  test    ebx, ebx
0x18000d095  jle     short loc_18000D09C
0x18000d097  movzx   ebx, bx
0x18000d09a  or      ebx, esi
0x18000d09c  mov     r13, r12
0x18000d09f  jmp     loc_18000D42A
0x18000d0a4  call    cs:__imp_GetCurrentThread
0x18000d0aa  mov     edi, 1
0x18000d0af  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18000d0b3  mov     rcx, rax; ThreadHandle
0x18000d0b6  mov     r8d, edi; OpenAsSelf
0x18000d0b9  lea     edx, [rdi+7]; DesiredAccess
0x18000d0bc  call    cs:__imp_OpenThreadToken
0x18000d0c2  test    eax, eax
0x18000d0c4  jnz     short loc_18000D113
0x18000d0c6  mov     r14d, edi
0x18000d0c9  call    cs:__imp_GetLastError
0x18000d0cf  mov     ebx, eax
0x18000d0d1  mov     esi, 80070000h
0x18000d0d6  test    eax, eax
0x18000d0d8  jle     short loc_18000D0DF
0x18000d0da  movzx   ebx, ax
0x18000d0dd  or      ebx, esi
0x18000d0df  lea     rax, aCallToOpenthre_0; "Call to OpenThreadTokenFailed"
0x18000d0e6  mov     r9d, 369h
0x18000d0ec  mov     [rsp+60h+peUse], rax
0x18000d0f1  lea     r8, aComComplusDtcD_34; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrs"...
0x18000d0f8  lea     rax, aCrpciomanagers_8; "CRpcIOManagerServer::GetClientAuthInfo"
0x18000d0ff  mov     dword ptr [rsp+60h+cchReferencedDomainName], ebx
0x18000d103  mov     edx, edi
0x18000d105  mov     [rsp+60h+ReturnLength], rax
0x18000d10a  mov     ecx, edi
0x18000d10c  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18000d111  jmp     short loc_18000D09C
0x18000d113  call    cs:__imp_RpcRevertToSelf
0x18000d119  test    eax, eax
0x18000d11b  jz      short loc_18000D162
0x18000d11d  jle     short loc_18000D127
0x18000d11f  movzx   eax, ax
0x18000d122  or      eax, 80070000h
0x18000d127  lea     rbx, aCallToRpcrever; "Call to RpcRevertToSelf failed"
0x18000d12e  mov     r9d, 371h
0x18000d134  mov     [rsp+60h+peUse], rbx
0x18000d139  lea     r8, aComComplusDtcD_34; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrs"...
0x18000d140  mov     dword ptr [rsp+60h+cchReferencedDomainName], eax
0x18000d144  mov     edx, edi
0x18000d146  lea     rax, aCrpciomanagers_8; "CRpcIOManagerServer::GetClientAuthInfo"
0x18000d14d  mov     ecx, edi
0x18000d14f  mov     [rsp+60h+ReturnLength], rax
0x18000d154  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18000d159  mov     rcx, rbx; unsigned __int16 *
0x18000d15c  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x18000d162  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18000d166  lea     rdx, ?AdministratorsSid@@3U_SID2@@A; SidToCheck
0x18000d16d  mov     r8, r14; IsMember
0x18000d170  mov     [rbp+arg_18], esi
0x18000d173  mov     [r14], esi
0x18000d176  call    cs:__imp_CheckTokenMembership
0x18000d17c  mov     esi, 80070000h
0x18000d181  test    eax, eax
0x18000d183  jnz     loc_18000D210
0x18000d189  call    cs:__imp_GetLastError
0x18000d18f  mov     ebx, eax
0x18000d191  test    eax, eax
0x18000d193  jle     short loc_18000D19A
0x18000d195  movzx   ebx, ax
0x18000d198  or      ebx, esi
0x18000d19a  lea     rax, aFailedToCheckT_1; "Failed to check token for admin."
0x18000d1a1  mov     r9d, 4D8h
0x18000d1a7  mov     [rsp+60h+peUse], rax
0x18000d1ac  lea     r8, aComComplusDtcS_7; "com\\complus\\dtc\\shared\\util\\securi"...
0x18000d1b3  lea     rax, aChecktokenfora; "CheckTokenForAdmin"
0x18000d1ba  mov     dword ptr [rsp+60h+cchReferencedDomainName], ebx
0x18000d1be  mov     edx, edi
0x18000d1c0  mov     [rsp+60h+ReturnLength], rax
0x18000d1c5  mov     ecx, 7
0x18000d1ca  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18000d1cf  test    ebx, ebx
0x18000d1d1  jns     short loc_18000D210
0x18000d1d3  lea     rax, aErrorCheckingT; "Error checking token for Admin"
0x18000d1da  mov     r9d, 380h
0x18000d1e0  mov     [rsp+60h+peUse], rax
0x18000d1e5  mov     edx, edi
0x18000d1e7  mov     dword ptr [rsp+60h+cchReferencedDomainName], ebx
0x18000d1eb  lea     rax, aCrpciomanagers_8; "CRpcIOManagerServer::GetClientAuthInfo"
0x18000d1f2  mov     ecx, edi
0x18000d1f4  lea     r8, aComComplusDtcD_34; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrs"...
0x18000d1fb  mov     [rsp+60h+ReturnLength], rax
0x18000d200  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18000d205  mov     r13, r12
0x18000d208  mov     r14d, r12d
0x18000d20b  jmp     loc_18000D42A
0x18000d210  cmp     [r14], r12d
0x18000d213  jnz     short loc_18000D239
0x18000d215  mov     rdx, [rbp+TokenHandle]; void *
0x18000d219  mov     r8, r14; int *
0x18000d21c  mov     rcx, r13; this
0x18000d21f  call    ?CheckTokenForWMIServiceSID@CRpcIOManagerServer@@AEAAJPEAXPEAH@Z; CRpcIOManagerServer::CheckTokenForWMIServiceSID(void *,int *)
0x18000d224  mov     ebx, eax
0x18000d226  test    eax, eax
0x18000d228  jns     short loc_18000D239
0x18000d22a  lea     rax, aErrorCheckingT_0; "Error checking token for WMI Service SI"...
0x18000d231  mov     r9d, 38Eh
0x18000d237  jmp     short loc_18000D1E0
0x18000d239  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18000d23d  lea     rax, [rbp+TokenInformationLength]
0x18000d241  xor     r9d, r9d; TokenInformationLength
0x18000d244  mov     [rsp+60h+ReturnLength], rax; ReturnLength
0x18000d249  xor     r8d, r8d; TokenInformation
0x18000d24c  mov     edx, edi; TokenInformationClass
0x18000d24e  call    cs:__imp_GetTokenInformation
0x18000d254  call    cs:__imp_GetLastError
0x18000d25a  cmp     eax, 7Ah ; 'z'
0x18000d25d  jz      short loc_18000D282
0x18000d25f  call    cs:__imp_GetLastError
0x18000d265  mov     ebx, eax
0x18000d267  test    eax, eax
0x18000d269  jle     short loc_18000D270
0x18000d26b  movzx   ebx, ax
0x18000d26e  or      ebx, esi
0x18000d270  lea     rax, aCallToGettoken; "Call to GetTokenInformation failed"
0x18000d277  mov     r9d, 39Eh
0x18000d27d  jmp     loc_18000D1E0
0x18000d282  mov     ecx, [rbp+TokenInformationLength]; unsigned __int64
0x18000d285  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000d28a  mov     r15, rax
0x18000d28d  mov     edx, edi; TokenInformationClass
0x18000d28f  test    rax, rax
0x18000d292  jnz     short loc_18000D2B6
0x18000d294  mov     eax, 8007000Eh
0x18000d299  lea     rcx, aUnableToAlloca; "Unable to allocate memory"
0x18000d2a0  mov     [rsp+60h+peUse], rcx
0x18000d2a5  mov     ebx, eax
0x18000d2a7  mov     dword ptr [rsp+60h+cchReferencedDomainName], eax
0x18000d2ab  mov     r9d, 3A7h
0x18000d2b1  jmp     loc_18000D1EB
0x18000d2b6  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18000d2ba  lea     rax, [rbp+TokenInformationLength]
0x18000d2be  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18000d2c2  mov     r8, r15; TokenInformation
0x18000d2c5  mov     [rsp+60h+ReturnLength], rax; ReturnLength
0x18000d2ca  call    cs:__imp_GetTokenInformation
0x18000d2d0  test    eax, eax
0x18000d2d2  jnz     short loc_18000D2F7
0x18000d2d4  call    cs:__imp_GetLastError
0x18000d2da  mov     ebx, eax
0x18000d2dc  test    eax, eax
0x18000d2de  jle     short loc_18000D2E5
0x18000d2e0  movzx   ebx, ax
0x18000d2e3  or      ebx, esi
0x18000d2e5  lea     rax, aCallToGettoken; "Call to GetTokenInformation failed"
0x18000d2ec  mov     r9d, 3B4h
0x18000d2f2  jmp     loc_18000D1E0
0x18000d2f7  mov     r14, [r15]
0x18000d2fa  lea     rax, [rbp+var_14]
0x18000d2fe  mov     [rsp+60h+peUse], rax; peUse
0x18000d303  lea     r9, [rbp+cchName]; cchName
0x18000d307  lea     rax, [rbp+var_20]
0x18000d30b  xor     r8d, r8d; Name
0x18000d30e  mov     [rsp+60h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18000d313  mov     rdx, r14; Sid
0x18000d316  xor     ecx, ecx; lpSystemName
0x18000d318  mov     [rsp+60h+ReturnLength], r12; ReferencedDomainName
0x18000d31d  call    cs:__imp_LookupAccountSidW
0x18000d323  test    eax, eax
0x18000d325  jnz     short loc_18000D355
0x18000d327  call    cs:__imp_GetLastError
0x18000d32d  cmp     eax, 7Ah ; 'z'
0x18000d330  jz      short loc_18000D355
0x18000d332  call    cs:__imp_GetLastError
0x18000d338  mov     ebx, eax
0x18000d33a  test    eax, eax
0x18000d33c  jle     short loc_18000D343
0x18000d33e  movzx   ebx, ax
0x18000d341  or      ebx, esi
0x18000d343  lea     rax, aLookupaccounts; "LookupAccountSid failed"
0x18000d34a  mov     r9d, 3C6h
0x18000d350  jmp     loc_18000D1E0
0x18000d355  mov     eax, [rbp+cchName]
0x18000d358  test    eax, eax
0x18000d35a  jz      loc_18000D56E
0x18000d360  cmp     [rbp+var_20], r12d
0x18000d364  jz      loc_18000D56E
0x18000d36a  mov     ecx, eax
0x18000d36c  mov     ebx, 2
0x18000d371  mov     eax, ebx
0x18000d373  mul     rcx
0x18000d376  lea     r12, [rbx-3]
0x18000d37a  cmovb   rax, r12
0x18000d37e  mov     rcx, rax; unsigned __int64
0x18000d381  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000d386  mov     ecx, [rbp+var_20]
0x18000d389  mov     r13, rax
0x18000d38c  mov     eax, ebx
0x18000d38e  mul     rcx
0x18000d391  cmovb   rax, r12
0x18000d395  mov     rcx, rax; unsigned __int64
0x18000d398  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000d39d  mov     r12, rax
0x18000d3a0  test    r13, r13
0x18000d3a3  jz      loc_18000D54C
0x18000d3a9  test    rax, rax
0x18000d3ac  jz      loc_18000D54C
0x18000d3b2  lea     rax, [rbp+var_14]
0x18000d3b6  mov     r8, r13; Name
0x18000d3b9  mov     [rsp+60h+peUse], rax; peUse
0x18000d3be  lea     r9, [rbp+cchName]; cchName
0x18000d3c2  lea     rax, [rbp+var_20]
0x18000d3c6  mov     rdx, r14; Sid
0x18000d3c9  mov     [rsp+60h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18000d3ce  xor     ecx, ecx; lpSystemName
0x18000d3d0  mov     [rsp+60h+ReturnLength], r12; ReferencedDomainName
0x18000d3d5  call    cs:__imp_LookupAccountSidW
0x18000d3db  test    eax, eax
0x18000d3dd  jnz     loc_18000D49A
0x18000d3e3  call    cs:__imp_GetLastError
0x18000d3e9  mov     ebx, eax
0x18000d3eb  test    eax, eax
0x18000d3ed  jle     short loc_18000D3F4
0x18000d3ef  movzx   ebx, ax
0x18000d3f2  or      ebx, esi
0x18000d3f4  lea     rax, aLookupaccounts; "LookupAccountSid failed"
0x18000d3fb  mov     r9d, 3E6h
0x18000d401  mov     [rsp+60h+peUse], rax
0x18000d406  mov     dword ptr [rsp+60h+cchReferencedDomainName], ebx
0x18000d40a  lea     rax, aCrpciomanagers_8; "CRpcIOManagerServer::GetClientAuthInfo"
0x18000d411  mov     edx, edi
0x18000d413  lea     r8, aComComplusDtcD_34; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrs"...
0x18000d41a  mov     [rsp+60h+ReturnLength], rax
0x18000d41f  mov     ecx, edi
0x18000d421  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18000d426  mov     r14d, [rbp+arg_18]
0x18000d42a  mov     rcx, [rbp+TokenHandle]; hObject
0x18000d42e  test    rcx, rcx
0x18000d431  jz      short loc_18000D441
0x18000d433  call    cs:__imp_CloseHandle
0x18000d439  mov     [rbp+TokenHandle], 0
0x18000d441  test    r14d, r14d
0x18000d444  jz      loc_18000D591
0x18000d44a  call    cs:__imp_RpcRevertToSelf
0x18000d450  test    eax, eax
0x18000d452  jz      loc_18000D591
0x18000d458  jle     short loc_18000D45F
0x18000d45a  movzx   eax, ax
0x18000d45d  or      eax, esi
0x18000d45f  lea     rbx, aCallToRpcrever; "Call to RpcRevertToSelf failed"
0x18000d466  mov     r9d, 41Ah
0x18000d46c  mov     [rsp+60h+peUse], rbx
0x18000d471  lea     r8, aComComplusDtcD_34; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrs"...
0x18000d478  mov     dword ptr [rsp+60h+cchReferencedDomainName], eax
0x18000d47c  mov     edx, edi
0x18000d47e  lea     rax, aCrpciomanagers_8; "CRpcIOManagerServer::GetClientAuthInfo"
0x18000d485  mov     ecx, edi
0x18000d487  mov     [rsp+60h+ReturnLength], rax
0x18000d48c  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18000d491  mov     rcx, rbx; unsigned __int16 *
0x18000d494  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
  ... truncated ...
```
