# ValidateObjectAccessWithToken

- ea: `0x180005290`
- end: `0x1800059b9`
- name: `ValidateObjectAccessWithToken`
- size: `1833`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, unsigned int, DWORD, __int64, DWORD *, __int64, int, int)`
- caller_count: `4`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800051f0`
- `0x18002ee50`
- `0x18005afa4`
- `0x180097874`

## callees

- `0x180005290`
- `0x180015e28`
- `0x18003ea2c`
- `0x180046650`
- `0x1800547e0`
- `0x180099318`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005433`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005482`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005793`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800057b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005837`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005433`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005482`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005793`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800057b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005837`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005965`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005965`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000550b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000552a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000550b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000552a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800054f6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180005515`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800054f6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180005515`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005580`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000569e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000598e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005580`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000569e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000598e`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x1800053be`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x1800053be`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180005603`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180005603`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180005701`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180005802`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180005701`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180005802`
- `api-ms-win-security-base-l1-1-0!ObjectCloseAuditAlarmW` at `0x18000589a`
- `api-ms-win-security-base-l1-1-0!ObjectCloseAuditAlarmW` at `0x18000589a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180005565`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180005565`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800058c1`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800058f4`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180005919`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800058c1`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800058f4`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180005919`
- `api-ms-win-security-base-l1-1-0!ObjectOpenAuditAlarmW` at `0x180005785`
- `api-ms-win-security-base-l1-1-0!ObjectOpenAuditAlarmW` at `0x180005785`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800055b8`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800055b8`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x180005668`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x180005668`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180005425`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180005478`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18000586e`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180005425`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180005478`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18000586e`
- `SPOOLSS!DllFreeSplMem` at `0x180005446`
- `SPOOLSS!DllFreeSplMem` at `0x1800054a1`
- `SPOOLSS!DllFreeSplMem` at `0x180005877`
- `SPOOLSS!DllFreeSplMem` at `0x180005446`
- `SPOOLSS!DllFreeSplMem` at `0x1800054a1`
- `SPOOLSS!DllFreeSplMem` at `0x180005877`
- `SPOOLSS!DllAllocSplMem` at `0x1800053e3`
- `SPOOLSS!DllAllocSplMem` at `0x18000544f`
- `SPOOLSS!DllAllocSplMem` at `0x1800053e3`
- `SPOOLSS!DllAllocSplMem` at `0x18000544f`
- `SPOOLSS!RevertToPrinterSelf` at `0x18000562a`
- `SPOOLSS!RevertToPrinterSelf` at `0x18000562a`
- `SPOOLSS!ImpersonatePrinterClient` at `0x1800056b0`
- `SPOOLSS!ImpersonatePrinterClient` at `0x1800056b0`

## string_xrefs

- `0x1800055cc`: `Failed to create medium IL SID: hr: 0x%x`
- `0x18000567c`: `Failed to modify token: hr: 0x%x`
- `0x1800055d3`: `CreateMediumIntegrityTokenFromToken`
- `0x18000561e`: `CreateMediumIntegrityTokenFromToken`
- `0x180005683`: `CreateMediumIntegrityTokenFromToken`
- `0x180005617`: `Failed to duplicate token: hr: 0x%x`
- `0x18000548b`: `AdjustTokenPrivileges failed: Error %d`
- `0x180005492`: `SetRequiredPrivileges`

## pseudocode

```c
__int64 __fastcall ValidateObjectAccessWithToken(
        HANDLE TokenHandle,
        unsigned int a2,
        DWORD a3,
        __int64 a4,
        DWORD *a5,
        __int64 a6,
        int a7,
        int a8)
{
  void *v8; // rsi
  unsigned int v11; // edi
  __int64 v12; // r14
  __int64 v13; // r12
  struct _TOKEN_PRIVILEGES *PreviousState; // r15
  struct _GENERIC_MAPPING *v15; // r12
  DWORD v16; // r12d
  DWORD LastError; // eax
  HANDLE CurrentThread; // rax
  HANDLE v20; // rax
  void *v21; // rcx
  bool v22; // bl
  BOOL v23; // eax
  __int64 LastErrorAsFailHRNoBreak; // rbx
  NCoreLibrary *v25; // rcx
  NCoreLibrary *v26; // rcx
  HANDLE v27; // r14
  void *v28; // r10
  NCoreLibrary *v29; // rcx
  __int64 v30; // rbx
  HANDLE v31; // rbx
  struct _GENERIC_MAPPING *v32; // r9
  PSECURITY_DESCRIPTOR v33; // r12
  int v34; // ebx
  struct _PRIVILEGE_SET *Privileges; // rax
  BOOL v36; // r12d
  DWORD v37; // eax
  DWORD v38; // edx
  DWORD GrantedAccess; // [rsp+60h] [rbp-A0h] BYREF
  DWORD BufferLength; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD AccessMask; // [rsp+68h] [rbp-98h] BYREF
  WINBOOL AccessStatus; // [rsp+6Ch] [rbp-94h] BYREF
  DWORD v43; // [rsp+70h] [rbp-90h]
  DWORD cbSid; // [rsp+74h] [rbp-8Ch] BYREF
  void *phNewToken; // [rsp+78h] [rbp-88h] BYREF
  int TokenInformation; // [rsp+80h] [rbp-80h] BYREF
  DWORD PrivilegeSetLength; // [rsp+84h] [rbp-7Ch] BYREF
  int v48; // [rsp+88h] [rbp-78h]
  void *TokenHandlea[2]; // [rsp+90h] [rbp-70h] BYREF
  LPBOOL GenerateOnClose; // [rsp+A0h] [rbp-60h]
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+A8h] [rbp-58h]
  LPWSTR ObjectName; // [rsp+B0h] [rbp-50h]
  __int64 v53; // [rsp+B8h] [rbp-48h]
  PGENERIC_MAPPING GenericMapping; // [rsp+C0h] [rbp-40h]
  DWORD *v55; // [rsp+C8h] [rbp-38h]
  __int64 v56; // [rsp+D0h] [rbp-30h]
  _TOKEN_PRIVILEGES NewState; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE pSid[80]; // [rsp+F0h] [rbp-10h] BYREF
  _PRIVILEGE_SET PrivilegeSet; // [rsp+140h] [rbp+40h] BYREF

  v8 = (void *)a4;
  v55 = a5;
  v11 = 1;
  AccessStatus = 1;
  AccessMask = 0;
  GrantedAccess = 0;
  PrivilegeSetLength = 256;
  if ( (*(_BYTE *)(a6 + 168) & 0x20) != 0 )
  {
    v12 = 0;
    if ( a2 )
    {
      if ( a2 == 1 )
      {
        v53 = a4;
        v12 = *(_QWORD *)(a4 + 64);
        ObjectName = *(LPWSTR *)(v12 + 24);
        pSecurityDescriptor = *(PSECURITY_DESCRIPTOR *)(v12 + 192);
        GenerateOnClose = (LPBOOL)(a4 + 184);
      }
      else
      {
        if ( a2 != 2 )
          return 0;
        v53 = 0;
        ObjectName = *(LPWSTR *)(a4 + 72);
        pSecurityDescriptor = *(PSECURITY_DESCRIPTOR *)(a4 + 264);
        GenerateOnClose = (LPBOOL)(a4 + 292);
      }
    }
    else
    {
      v13 = a4;
      if ( !a4 )
        v13 = 0;
      v53 = v13;
      v8 = (void *)a6;
      ObjectName = *(LPWSTR *)(a6 + 24);
      pSecurityDescriptor = *(PSECURITY_DESCRIPTOR *)(a6 + 352);
      GenerateOnClose = &ServerGenerateOnClose;
    }
    PreviousState = 0;
    AccessMask = a3;
    v56 = a2;
    v15 = &::GenericMapping + a2;
    GenericMapping = v15;
    MapGenericMask(&AccessMask, v15);
    if ( (AccessMask & 0x1000000) != 0 )
    {
      NewState = 0;
      BufferLength = 0;
      PreviousState = (struct _TOKEN_PRIVILEGES *)DllAllocSplMem(1000);
      if ( !PreviousState )
        goto LABEL_17;
      NewState.PrivilegeCount = 1;
      NewState.Privileges[0].Luid = (LUID)8LL;
      NewState.Privileges[0].Attributes = 2;
      if ( !AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0x3E8u, PreviousState, &BufferLength) )
      {
        if ( GetLastError() != 122 )
          goto LABEL_16;
        v16 = BufferLength;
        DllFreeSplMem(PreviousState);
        PreviousState = (struct _TOKEN_PRIVILEGES *)DllAllocSplMem(v16);
        if ( !PreviousState )
          goto LABEL_17;
        if ( !AdjustTokenPrivileges(TokenHandle, 0, &NewState, v16, PreviousState, &BufferLength) )
        {
LABEL_16:
          LastError = GetLastError();
          LocalSpoolerTelemetry::WriteDbgTraceError(
            "SetRequiredPrivileges",
            L"AdjustTokenPrivileges failed: Error %d",
            LastError);
          DllFreeSplMem(PreviousState);
LABEL_17:
          if ( v55 )
            *v55 = 0;
          return 0;
        }
        v15 = GenericMapping;
      }
    }
    v48 = 0;
    v43 = 0;
    phNewToken = (void *)-1LL;
    if ( a2 != 1 || (AccessMask & 0x44) != 0x40 )
      goto LABEL_47;
    TokenHandlea[0] = (void *)-1LL;
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 8u, 1, TokenHandlea) )
    {
      v20 = GetCurrentThread();
      OpenThreadToken(v20, 8u, 0, TokenHandlea);
    }
    v21 = TokenHandlea[0];
    if ( TokenHandlea[0] == (void *)-1LL )
      goto LABEL_98;
    v22 = 1;
    if ( TokenHandlea[0] )
    {
      TokenInformation = 1;
      cbSid = 0;
      v23 = GetTokenInformation(TokenHandlea[0], TokenIsAppContainer, &TokenInformation, 4u, &cbSid);
      v21 = TokenHandlea[0];
      if ( v23 )
        v22 = TokenInformation != 0;
    }
    if ( v21 != (void *)-1LL )
      CloseHandle(v21);
    if ( v22 )
    {
LABEL_98:
      if ( IsClientAssociatedWSDA((struct _INIPRINTER *)v12) )
      {
        LODWORD(LastErrorAsFailHRNoBreak) = 0;
        cbSid = 68;
        if ( CreateWellKnownSid(WinMediumLabelSid, 0, pSid, &cbSid)
          || (LastErrorAsFailHRNoBreak = (unsigned int)NCoreLibrary::GetLastErrorAsFailHRNoBreak(v25),
              LocalSpoolerTelemetry::WriteDbgTraceError(
                "CreateMediumIntegrityTokenFromToken",
                L"Failed to create medium IL SID: hr: 0x%x",
                LastErrorAsFailHRNoBreak),
              (int)LastErrorAsFailHRNoBreak >= 0) )
        {
          if ( !DuplicateTokenEx(TokenHandle, 0, 0, SecurityImpersonation, TokenImpersonation, &phNewToken) )
          {
            LastErrorAsFailHRNoBreak = (unsigned int)NCoreLibrary::GetLastErrorAsFailHRNoBreak(v26);
            LocalSpoolerTelemetry::WriteDbgTraceError(
              "CreateMediumIntegrityTokenFromToken",
              L"Failed to duplicate token: hr: 0x%x",
              LastErrorAsFailHRNoBreak);
          }
        }
        v27 = RevertToPrinterSelf();
        if ( (int)LastErrorAsFailHRNoBreak < 0 )
          goto LABEL_42;
        TokenHandlea[1] = (void *)96;
        TokenHandlea[0] = pSid;
        v28 = phNewToken;
        if ( phNewToken == (void *)-1LL )
          v28 = 0;
        if ( !SetTokenInformation(v28, TokenIntegrityLevel, TokenHandlea, 0x10u) )
        {
          v30 = (unsigned int)NCoreLibrary::GetLastErrorAsFailHRNoBreak(v29);
          LocalSpoolerTelemetry::WriteDbgTraceError(
            "CreateMediumIntegrityTokenFromToken",
            L"Failed to modify token: hr: 0x%x",
            v30);
          if ( (int)v30 < 0 )
          {
LABEL_42:
            if ( phNewToken != (void *)-1LL )
            {
              CloseHandle(phNewToken);
              phNewToken = (void *)-1LL;
            }
          }
        }
        ImpersonatePrinterClient(v27);
      }
    }
    v31 = phNewToken;
    if ( phNewToken == (void *)-1LL || !phNewToken )
LABEL_47:
      v31 = TokenHandle;
    v32 = v15;
    v33 = pSecurityDescriptor;
    if ( AccessCheck(
           pSecurityDescriptor,
           v31,
           AccessMask,
           v32,
           &PrivilegeSet,
           &PrivilegeSetLength,
           &GrantedAccess,
           &AccessStatus)
      && AccessStatus )
    {
      v34 = 1;
    }
    else
    {
      if ( GetLastError() == 1309 )
      {
        v48 = 1;
        v34 = 1;
        GrantedAccess = AccessMask;
        Privileges = 0;
        goto LABEL_52;
      }
      if ( GetLastError() != 5
        || (AccessMask & 0x40) == 0
        || !AccessCheck(
              v33,
              v31,
              AccessMask & 0xFFFFFFBB | 4,
              GenericMapping,
              &PrivilegeSet,
              &PrivilegeSetLength,
              &GrantedAccess,
              &AccessStatus)
        || !AccessStatus )
      {
        v43 = GetLastError();
        Privileges = 0;
        v34 = 0;
        goto LABEL_52;
      }
      v34 = 1;
      v37 = GrantedAccess | 0x40;
      GrantedAccess |= 0x40u;
      if ( (AccessMask & 4) == 0 )
        GrantedAccess = v37 & 0xFFFFFFFB;
    }
    Privileges = &PrivilegeSet;
LABEL_52:
    if ( a8 )
      v36 = ObjectOpenAuditAlarmW(
              L"Spooler",
              v8,
              (LPWSTR)(&ObjectTypeName)[v56],
              ObjectName,
              v33,
              TokenHandle,
              AccessMask,
              GrantedAccess,
              Privileges,
              0,
              AccessStatus,
              GenerateOnClose);
    else
      v36 = 1;
    if ( (AccessMask & 0x1000000) != 0 )
    {
      AdjustTokenPrivileges(TokenHandle, 0, PreviousState, 0, 0, 0);
      DllFreeSplMem(PreviousState);
    }
    if ( a8 && !v53 )
      ObjectCloseAuditAlarmW(L"Spooler", v8, *GenerateOnClose);
    if ( a7 )
      goto LABEL_80;
    BufferLength = 0;
    if ( !CheckTokenMembership(TokenHandle, pLocalSystemSid, (PBOOL)&BufferLength) )
      BufferLength = 0;
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl'::`2'::impl) )
      goto LABEL_76;
    if ( BufferLength )
      goto LABEL_80;
    if ( CheckTokenMembership(TokenHandle, gRestrictedSpoolerServiceSid, (PBOOL)&BufferLength) )
    {
LABEL_76:
      if ( BufferLength )
        goto LABEL_80;
    }
    else
    {
      BufferLength = 0;
    }
    if ( !CheckTokenMembership(TokenHandle, pLocalAdminSid, (PBOOL)&BufferLength) || !BufferLength )
    {
      GrantedAccess = 0;
      AccessStatus = 0;
      v38 = 5;
LABEL_81:
      if ( (GrantedAccess & 4) != 0 )
        GrantedAccess |= 0x40u;
      if ( v55 )
        *v55 = GrantedAccess;
      if ( !v34 || !AccessStatus )
        SetLastError(v38);
      if ( (!v36 || !v34 || !AccessStatus) && !v48 )
        v11 = 0;
      if ( phNewToken != (void *)-1LL )
        CloseHandle(phNewToken);
      return v11;
    }
LABEL_80:
    v38 = v43;
    goto LABEL_81;
  }
  return v11;
}

```

## disassembly

```asm
0x180005290  push    rbp
0x180005292  push    rbx
0x180005293  push    rsi
0x180005294  push    rdi
0x180005295  push    r12
0x180005297  push    r13
0x180005299  push    r14
0x18000529b  push    r15
0x18000529d  lea     rbp, [rsp-158h]
0x1800052a5  sub     rsp, 258h
0x1800052ac  mov     rax, cs:__security_cookie
0x1800052b3  xor     rax, rsp
0x1800052b6  mov     [rbp+190h+var_50], rax
0x1800052bd  mov     rsi, r9
0x1800052c0  mov     ebx, edx
0x1800052c2  mov     r13, rcx
0x1800052c5  mov     rax, [rbp+190h+arg_20]
0x1800052cc  mov     [rbp+190h+var_1C8], rax
0x1800052d0  mov     rcx, [rbp+190h+arg_28]
0x1800052d7  mov     edi, 1
0x1800052dc  mov     [rsp+290h+var_224], edi
0x1800052e0  xor     edx, edx
0x1800052e2  mov     [rsp+290h+AccessMask], edx
0x1800052e6  mov     [rsp+290h+var_230], edx
0x1800052ea  mov     [rbp+190h+PrivilegeSetLength], 100h
0x1800052f1  test    byte ptr [rcx+0A8h], 20h
0x1800052f8  jz      loc_180005994
0x1800052fe  mov     r14d, edx
0x180005301  mov     eax, ebx
0x180005303  test    ebx, ebx
0x180005305  jz      short loc_18000535F
0x180005307  sub     eax, edi
0x180005309  jz      short loc_180005337
0x18000530b  cmp     eax, edi
0x18000530d  jnz     loc_1800054B6
0x180005313  mov     [rbp+190h+var_1D8], rdx
0x180005317  mov     rax, [r9+48h]
0x18000531b  mov     [rbp+190h+ObjectName], rax
0x18000531f  mov     r12, [r9+108h]
0x180005326  mov     [rbp+190h+pSecurityDescriptor], r12
0x18000532a  lea     r12, [r9+124h]
0x180005331  mov     [rbp+190h+var_1F0], r12
0x180005335  jmp     short loc_18000538E
0x180005337  mov     [rbp+190h+var_1D8], r9
0x18000533b  mov     r14, [r9+40h]
0x18000533f  mov     rax, [r14+18h]
0x180005343  mov     [rbp+190h+ObjectName], rax
0x180005347  mov     rax, [r14+0C0h]
0x18000534e  mov     [rbp+190h+pSecurityDescriptor], rax
0x180005352  lea     r12, [r9+0B8h]
0x180005359  mov     [rbp+190h+var_1F0], r12
0x18000535d  jmp     short loc_18000538E
0x18000535f  mov     r12, r9
0x180005362  test    r9, r9
0x180005365  cmovz   r12, rdx
0x180005369  mov     [rbp+190h+var_1D8], r12
0x18000536d  mov     rsi, rcx
0x180005370  mov     rax, [rcx+18h]
0x180005374  mov     [rbp+190h+ObjectName], rax
0x180005378  mov     rax, [rcx+160h]
0x18000537f  mov     [rbp+190h+pSecurityDescriptor], rax
0x180005383  lea     rax, ?ServerGenerateOnClose@@3HA; int ServerGenerateOnClose
0x18000538a  mov     [rbp+190h+var_1F0], rax
0x18000538e  mov     r15, rdx
0x180005391  mov     [rsp+290h+AccessMask], r8d
0x180005396  mov     rax, rbx
0x180005399  mov     [rbp+190h+var_1C0], rbx
0x18000539d  shl     rax, 4
0x1800053a1  lea     rcx, __ImageBase
0x1800053a8  lea     r12, rva ?GenericMapping@@3PAU_GENERIC_MAPPING@@A.GenericRead[rcx]; _GENERIC_MAPPING near * GenericMapping ...
0x1800053af  add     r12, rax
0x1800053b2  mov     [rbp+190h+GenericMapping], r12
0x1800053b6  mov     rdx, r12; GenericMapping
0x1800053b9  lea     rcx, [rsp+290h+AccessMask]; AccessMask
0x1800053be  call    cs:__imp_MapGenericMask
0x1800053c4  test    [rsp+290h+AccessMask], 1000000h
0x1800053cc  jz      loc_1800054C1
0x1800053d2  xorps   xmm0, xmm0
0x1800053d5  movups  xmmword ptr [rbp+190h+NewState.PrivilegeCount], xmm0
0x1800053d9  mov     [rsp+290h+BufferLength], r15d
0x1800053de  mov     ecx, 3E8h
0x1800053e3  call    cs:__imp_DllAllocSplMem
0x1800053e9  mov     r15, rax
0x1800053ec  test    rax, rax
0x1800053ef  jz      loc_1800054A7
0x1800053f5  mov     [rbp+190h+NewState.PrivilegeCount], edi
0x1800053f8  mov     qword ptr [rbp+190h+NewState.Privileges.Luid.LowPart], 8
0x180005400  mov     [rbp+190h+NewState.Privileges.Attributes], 2
0x180005407  lea     rax, [rsp+290h+BufferLength]
0x18000540c  mov     [rsp+290h+ReturnLength], rax; ReturnLength
0x180005411  mov     [rsp+290h+PreviousState], r15; PreviousState
0x180005416  mov     r9d, 3E8h; BufferLength
0x18000541c  lea     r8, [rbp+190h+NewState]; NewState
0x180005420  xor     edx, edx; DisableAllPrivileges
0x180005422  mov     rcx, r13; TokenHandle
0x180005425  call    cs:__imp_AdjustTokenPrivileges
0x18000542b  test    eax, eax
0x18000542d  jnz     loc_1800054C1
0x180005433  call    cs:__imp_GetLastError
0x180005439  cmp     eax, 7Ah ; 'z'
0x18000543c  jnz     short loc_180005482
0x18000543e  mov     r12d, [rsp+290h+BufferLength]
0x180005443  mov     rcx, r15
0x180005446  call    cs:__imp_DllFreeSplMem
0x18000544c  mov     ecx, r12d
0x18000544f  call    cs:__imp_DllAllocSplMem
0x180005455  mov     r15, rax
0x180005458  test    rax, rax
0x18000545b  jz      short loc_1800054A7
0x18000545d  lea     rax, [rsp+290h+BufferLength]
0x180005462  mov     [rsp+290h+ReturnLength], rax; ReturnLength
0x180005467  mov     [rsp+290h+PreviousState], r15; PreviousState
0x18000546c  mov     r9d, r12d; BufferLength
0x18000546f  lea     r8, [rbp+190h+NewState]; NewState
0x180005473  xor     edx, edx; DisableAllPrivileges
0x180005475  mov     rcx, r13; TokenHandle
0x180005478  call    cs:__imp_AdjustTokenPrivileges
0x18000547e  test    eax, eax
0x180005480  jnz     short loc_1800054BD
0x180005482  call    cs:__imp_GetLastError
0x180005488  mov     r8d, eax
0x18000548b  lea     rdx, aAdjusttokenpri; "AdjustTokenPrivileges failed: Error %d"
0x180005492  lea     rcx, aSetrequiredpri; "SetRequiredPrivileges"
0x180005499  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18000549e  mov     rcx, r15
0x1800054a1  call    cs:__imp_DllFreeSplMem
0x1800054a7  mov     rax, [rbp+190h+var_1C8]
0x1800054ab  test    rax, rax
0x1800054ae  jz      short loc_1800054B6
0x1800054b0  mov     dword ptr [rax], 0
0x1800054b6  xor     eax, eax
0x1800054b8  jmp     loc_180005996
0x1800054bd  mov     r12, [rbp+190h+GenericMapping]
0x1800054c1  mov     [rbp+190h+var_208], 0
0x1800054c8  xor     eax, eax
0x1800054ca  mov     [rsp+290h+var_220], eax
0x1800054ce  mov     [rsp+290h+phNewToken], 0FFFFFFFFFFFFFFFFh
0x1800054d7  cmp     ebx, 1
0x1800054da  jnz     loc_1800056C6
0x1800054e0  mov     eax, [rsp+290h+AccessMask]
0x1800054e4  and     al, 44h
0x1800054e6  cmp     al, 40h ; '@'
0x1800054e8  jnz     loc_1800056C6
0x1800054ee  mov     [rbp+190h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x1800054f6  call    cs:__imp_GetCurrentThread
0x1800054fc  lea     r9, [rbp+190h+TokenHandle]; TokenHandle
0x180005500  mov     r8d, edi; OpenAsSelf
0x180005503  mov     edx, 8; DesiredAccess
0x180005508  mov     rcx, rax; ThreadHandle
0x18000550b  call    cs:__imp_OpenThreadToken
0x180005511  test    eax, eax
0x180005513  jnz     short loc_180005530
0x180005515  call    cs:__imp_GetCurrentThread
0x18000551b  lea     r9, [rbp+190h+TokenHandle]; TokenHandle
0x18000551f  xor     r8d, r8d; OpenAsSelf
0x180005522  mov     edx, 8; DesiredAccess
0x180005527  mov     rcx, rax; ThreadHandle
0x18000552a  call    cs:__imp_OpenThreadToken
0x180005530  mov     rcx, [rbp+190h+TokenHandle]; TokenHandle
0x180005534  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180005538  jz      short loc_18000558E
0x18000553a  mov     bl, 1
0x18000553c  test    rcx, rcx
0x18000553f  jz      short loc_18000557A
0x180005541  mov     [rbp+190h+TokenInformation], edi
0x180005544  mov     [rsp+290h+cbSid], 0
0x18000554c  lea     rax, [rsp+290h+cbSid]
0x180005551  mov     [rsp+290h+PreviousState], rax; ReturnLength
0x180005556  mov     r9d, 4; TokenInformationLength
0x18000555c  lea     r8, [rbp+190h+TokenInformation]; TokenInformation
0x180005560  mov     edx, 1Dh; TokenInformationClass
0x180005565  call    cs:__imp_GetTokenInformation
0x18000556b  mov     rcx, [rbp+190h+TokenHandle]; hObject
0x18000556f  test    eax, eax
0x180005571  jz      short loc_18000557A
0x180005573  cmp     [rbp+190h+TokenInformation], 0
0x180005577  setnz   bl
0x18000557a  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000557e  jz      short loc_180005586
0x180005580  call    cs:__imp_CloseHandle
0x180005586  test    bl, bl
0x180005588  jz      loc_1800056B6
0x18000558e  mov     rcx, r14; struct _INIPRINTER *
0x180005591  call    ?IsClientAssociatedWSDA@@YA_NPEAU_INIPRINTER@@@Z; IsClientAssociatedWSDA(_INIPRINTER *)
0x180005596  test    al, al
0x180005598  jz      loc_1800056B6
0x18000559e  xor     ebx, ebx
0x1800055a0  mov     [rsp+290h+cbSid], 44h ; 'D'
0x1800055a8  lea     r9, [rsp+290h+cbSid]; cbSid
0x1800055ad  lea     r8, [rbp+190h+pSid]; pSid
0x1800055b1  xor     edx, edx; DomainSid
0x1800055b3  mov     ecx, 43h ; 'C'; WellKnownSidType
0x1800055b8  call    cs:__imp_CreateWellKnownSid
0x1800055be  test    eax, eax
0x1800055c0  jnz     short loc_1800055E3
0x1800055c2  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x1800055c7  mov     ebx, eax
0x1800055c9  mov     r8d, eax
0x1800055cc  lea     rdx, aFailedToCreate_17; "Failed to create medium IL SID: hr: 0x%"...
0x1800055d3  lea     rcx, aCreatemediumin; "CreateMediumIntegrityTokenFromToken"
0x1800055da  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800055df  test    ebx, ebx
0x1800055e1  js      short loc_18000562A
0x1800055e3  lea     rax, [rsp+290h+phNewToken]
0x1800055e8  mov     [rsp+290h+ReturnLength], rax; phNewToken
0x1800055ed  mov     dword ptr [rsp+290h+PreviousState], 2; TokenType
0x1800055f5  mov     r9d, 2; ImpersonationLevel
0x1800055fb  xor     r8d, r8d; lpTokenAttributes
0x1800055fe  xor     edx, edx; dwDesiredAccess
0x180005600  mov     rcx, r13; hExistingToken
0x180005603  call    cs:__imp_DuplicateTokenEx
0x180005609  test    eax, eax
0x18000560b  jnz     short loc_18000562A
0x18000560d  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x180005612  mov     ebx, eax
0x180005614  mov     r8d, eax
0x180005617  lea     rdx, aFailedToDuplic_0; "Failed to duplicate token: hr: 0x%x"
0x18000561e  lea     rcx, aCreatemediumin; "CreateMediumIntegrityTokenFromToken"
0x180005625  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18000562a  call    cs:__imp_RevertToPrinterSelf
0x180005630  mov     r14, rax
0x180005633  test    ebx, ebx
0x180005635  js      short loc_180005693
0x180005637  mov     [rbp+190h+var_1F8], 60h ; '`'
0x18000563f  lea     rax, [rbp+190h+pSid]
0x180005643  mov     [rbp+190h+TokenHandle], rax
0x180005647  mov     r10, [rsp+290h+phNewToken]
0x18000564c  xor     ecx, ecx
0x18000564e  cmp     r10, 0FFFFFFFFFFFFFFFFh
0x180005652  cmovz   r10, rcx
0x180005656  mov     r9d, 10h; TokenInformationLength
0x18000565c  lea     r8, [rbp+190h+TokenHandle]; TokenInformation
0x180005660  mov     edx, 19h; TokenInformationClass
0x180005665  mov     rcx, r10; TokenHandle
0x180005668  call    cs:__imp_SetTokenInformation
0x18000566e  test    eax, eax
0x180005670  jnz     short loc_1800056AD
0x180005672  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x180005677  mov     ebx, eax
0x180005679  mov     r8d, eax
0x18000567c  lea     rdx, aFailedToModify; "Failed to modify token: hr: 0x%x"
0x180005683  lea     rcx, aCreatemediumin; "CreateMediumIntegrityTokenFromToken"
0x18000568a  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18000568f  test    ebx, ebx
0x180005691  jns     short loc_1800056AD
0x180005693  mov     rcx, [rsp+290h+phNewToken]; hObject
0x180005698  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000569c  jz      short loc_1800056AD
0x18000569e  call    cs:__imp_CloseHandle
0x1800056a4  mov     [rsp+290h+phNewToken], 0FFFFFFFFFFFFFFFFh
0x1800056ad  mov     rcx, r14; hToken
0x1800056b0  call    cs:__imp_ImpersonatePrinterClient
0x1800056b6  mov     rbx, [rsp+290h+phNewToken]
0x1800056bb  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800056bf  jz      short loc_1800056C6
0x1800056c1  test    rbx, rbx
0x1800056c4  jnz     short loc_1800056C9
0x1800056c6  mov     rbx, r13
0x1800056c9  lea     rax, [rsp+290h+var_224]
0x1800056ce  mov     [rsp+290h+AccessStatus], rax; AccessStatus
0x1800056d3  lea     rax, [rsp+290h+var_230]
0x1800056d8  mov     [rsp+290h+GrantedAccess], rax; GrantedAccess
0x1800056dd  lea     rax, [rbp+190h+PrivilegeSetLength]
0x1800056e1  mov     [rsp+290h+ReturnLength], rax; PrivilegeSetLength
0x1800056e6  lea     rax, [rbp+190h+PrivilegeSet]
0x1800056ea  mov     [rsp+290h+PreviousState], rax; PrivilegeSet
0x1800056ef  mov     r9, r12; GenericMapping
0x1800056f2  mov     r8d, [rsp+290h+AccessMask]; DesiredAccess
0x1800056f7  mov     rdx, rbx; ClientToken
0x1800056fa  mov     r12, [rbp+190h+pSecurityDescriptor]
0x1800056fe  mov     rcx, r12; pSecurityDescriptor
0x180005701  call    cs:__imp_AccessCheck
0x180005707  test    eax, eax
0x180005709  jz      loc_180005793
0x18000570f  cmp     [rsp+290h+var_224], 0
0x180005714  jz      short loc_180005793
0x180005716  mov     ebx, edi
0x180005718  lea     rax, [rbp+190h+PrivilegeSet]
0x18000571c  mov     r14d, [rbp+190h+arg_38]
0x180005723  test    r14d, r14d
0x180005726  jz      loc_18000584A
0x18000572c  mov     rcx, [rbp+190h+var_1F0]
0x180005730  mov     [rsp+290h+GenerateOnClose], rcx; GenerateOnClose
0x180005735  mov     ecx, [rsp+290h+var_224]
0x180005739  mov     [rsp+290h+AccessGranted], ecx; AccessGranted
0x18000573d  mov     [rsp+290h+ObjectCreation], 0; ObjectCreation
0x180005745  mov     [rsp+290h+Privileges], rax; Privileges
0x18000574a  mov     eax, [rsp+290h+var_230]
0x18000574e  mov     dword ptr [rsp+290h+AccessStatus], eax; GrantedAccess
0x180005752  mov     eax, [rsp+290h+AccessMask]
0x180005756  mov     dword ptr [rsp+290h+GrantedAccess], eax; DesiredAccess
0x18000575a  mov     [rsp+290h+ReturnLength], r13; ClientToken
0x18000575f  mov     [rsp+290h+PreviousState], r12; pSecurityDescriptor
0x180005764  mov     r9, [rbp+190h+ObjectName]; ObjectName
0x180005768  mov     r8, [rbp+190h+var_1C0]
0x18000576c  lea     rax, __ImageBase
0x180005773  mov     r8, ds:rva ?ObjectTypeName@@3PAPEAGA[rax+r8*8]; ObjectTypeName
0x18000577b  mov     rdx, rsi; HandleId
0x18000577e  lea     rcx, szSpooler; "Spooler"
0x180005785  call    cs:__imp_ObjectOpenAuditAlarmW
  ... truncated ...
```
