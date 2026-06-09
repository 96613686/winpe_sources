# CMsiEnvironmentBlock::InitializeFromSystemEnvironment(CMsiEnvironmentBlock *)

- ea: `0x1801cc988`
- end: `0x1801ccf2c`
- name: `?InitializeFromSystemEnvironment@CMsiEnvironmentBlock@@QEAA_NPEAV1@@Z`
- size: `1444`
- prototype: `bool __fastcall(CMsiEnvironmentBlock *__hidden this, struct CMsiEnvironmentBlock *)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1801cc5bc`

## callees

- `0x18000c4bc`
- `0x180010ac0`
- `0x180027634`
- `0x180045ba4`
- `0x18008c93c`
- `0x18009bf74`
- `0x1800eee44`
- `0x1801351cc`
- `0x18013dd1c`
- `0x1801cc70c`
- `0x1801cc988`
- `0x1802651ea`
- `0x180265240`
- `0x180266010`

## import_xrefs

- `ADVAPI32!LookupAccountSidW` at `0x1801cca9a`
- `ADVAPI32!LookupAccountSidW` at `0x1801cca9a`
- `ADVAPI32!GetTokenInformation` at `0x1801cca2d`
- `ADVAPI32!GetTokenInformation` at `0x1801cca2d`
- `KERNEL32!GetLastError` at `0x1801cca3d`
- `KERNEL32!GetLastError` at `0x1801ccaaa`
- `KERNEL32!GetLastError` at `0x1801ccaeb`
- `KERNEL32!GetLastError` at `0x1801cca3d`
- `KERNEL32!GetLastError` at `0x1801ccaaa`
- `KERNEL32!GetLastError` at `0x1801ccaeb`
- `KERNEL32!GlobalFree` at `0x1801cce65`
- `KERNEL32!GlobalFree` at `0x1801cced0`
- `KERNEL32!GlobalFree` at `0x1801cce65`
- `KERNEL32!GlobalFree` at `0x1801cced0`
- `KERNEL32!GetSystemDirectoryW` at `0x1801ccad7`
- `KERNEL32!GetSystemDirectoryW` at `0x1801ccad7`

## string_xrefs

- `0x1801cca55`: `ERROR: GetTokenInformation failed with error %d`
- `0x1801ccac2`: `ERROR: LookupAccountSid failed with error %d`
- `0x1801ccaff`: `ERROR: GetSystemDirectory failed with error %d`
- `0x1801ccc5e`: `ERROR: Failed to set environment variable: USERPROFILE when it is remote path`
- `0x1801ccd4a`: `ERROR: Failed to set environment variable: TMP when it is remote path`
- `0x1801ccd7d`: `ERROR: Failed to set environment variable: TEMP when it is remote path`
- `0x1801ccda9`: `%c:\Windows\SystemTemp`
- `0x1801ccdcd`: `ERROR: StringCchPrintf failure in CMsiEnvironmentBlock::InitializeFromSystemEnvironment`
- `0x1801cce98`: `ERROR: Failed to set environment variable: TEMP`

## pseudocode

```c
char __fastcall CMsiEnvironmentBlock::InitializeFromSystemEnvironment(
        CMsiEnvironmentBlock *this,
        struct CMsiEnvironmentBlock *a2)
{
  void *UserToken; // rax
  void *v5; // rax
  DWORD LastError; // eax
  const unsigned __int16 *v7; // r9
  const char *v9; // r9
  const char *v10; // r9
  unsigned int v11; // [rsp+50h] [rbp-B0h]
  void *v12; // [rsp+58h] [rbp-A8h]
  __int64 v13; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v14; // [rsp+68h] [rbp-98h] BYREF
  DWORD ReturnLength; // [rsp+70h] [rbp-90h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+74h] [rbp-8Ch] BYREF
  DWORD cchReferencedDomainName; // [rsp+78h] [rbp-88h] BYREF
  DWORD cchName; // [rsp+7Ch] [rbp-84h] BYREF
  HGLOBAL hMem; // [rsp+80h] [rbp-80h] BYREF
  int v20; // [rsp+88h] [rbp-78h]
  int v21; // [rsp+8Ch] [rbp-74h]
  char v22; // [rsp+90h] [rbp-70h] BYREF
  PSID TokenInformation[12]; // [rsp+2A0h] [rbp+1A0h] BYREF
  unsigned __int16 v24; // [rsp+300h] [rbp+200h] BYREF
  _BYTE v25[798]; // [rsp+302h] [rbp+202h] BYREF
  WCHAR Buffer[264]; // [rsp+620h] [rbp+520h] BYREF
  WCHAR ReferencedDomainName[400]; // [rsp+830h] [rbp+730h] BYREF
  WCHAR Name[504]; // [rsp+B50h] [rbp+A50h] BYREF

  if ( !CMsiEnvironmentBlock::InitializeFromEnvironment(this, 1) )
    return 0;
  UserToken = MsiUIMessageContext::GetUserToken((MsiUIMessageContext *)&g_MessageContext);
  if ( !IsLocalSystemToken(UserToken) )
  {
    v5 = MsiUIMessageContext::GetUserToken((MsiUIMessageContext *)&g_MessageContext);
    if ( v5 )
    {
      cchName = 500;
      cchReferencedDomainName = 400;
      ReturnLength = 0;
      if ( !GetTokenInformation(v5, TokenUser, TokenInformation, 0x58u, &ReturnLength) )
      {
        LastError = GetLastError();
        if ( g_dmDiagnosticMode )
        {
          v7 = L"ERROR: GetTokenInformation failed with error %d";
LABEL_13:
          DebugString(
            9,
            0,
            0,
            v7,
            (const unsigned __int16 *)LastError,
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
          return 0;
        }
        return 0;
      }
      peUse = 0;
      if ( !LookupAccountSidW(
              0,
              TokenInformation[0],
              Name,
              &cchName,
              ReferencedDomainName,
              &cchReferencedDomainName,
              &peUse) )
      {
        LastError = GetLastError();
        if ( g_dmDiagnosticMode )
        {
          v7 = L"ERROR: LookupAccountSid failed with error %d";
          goto LABEL_13;
        }
        return 0;
      }
      if ( !GetSystemDirectoryW(Buffer, 0x104u) )
      {
        LastError = GetLastError();
        if ( g_dmDiagnosticMode )
        {
          v7 = L"ERROR: GetSystemDirectory failed with error %d";
          goto LABEL_13;
        }
        return 0;
      }
      v20 = 261;
      hMem = &v22;
      v21 = 261;
      if ( !(unsigned __int8)CMsiEnvironmentBlock::Get(a2, L"USERPROFILE", &hMem) )
      {
        if ( g_dmDiagnosticMode )
          DebugString(
            9,
            0,
            0,
            "ERROR: Failed to get environment variable: USERPROFILE",
            "(NULL)",
            "(NULL)",
            "(NULL)",
            "(NULL)",
            "(NULL)",
            "(NULL)",
            v11,
            v12);
        goto LABEL_44;
      }
      MsiString::MsiString((MsiString *)&v13, (const unsigned __int16 *)hMem);
      if ( (*(unsigned int (__fastcall **)(__int64, __int64, const wchar_t *))(*(_QWORD *)v13 + 200LL))(v13, 3, L"\\\\") == 1
        && !(*(unsigned int (__fastcall **)(__int64, __int64, const wchar_t *))(*(_QWORD *)v13 + 200LL))(
              v13,
              3,
              L"\\\\?\\")
        && !CMsiEnvironmentBlock::Set(this, L"USERPROFILE", (const unsigned __int16 *)hMem) )
      {
        if ( g_dmDiagnosticMode )
        {
          v9 = "ERROR: Failed to set environment variable: USERPROFILE when it is remote path";
LABEL_26:
          DebugString(9, 0, 0, v9, "(NULL)", "(NULL)", "(NULL)", "(NULL)", "(NULL)", "(NULL)", v11, v12);
          goto LABEL_43;
        }
        goto LABEL_43;
      }
      v21 = 261;
      if ( !(unsigned __int8)CMsiEnvironmentBlock::Get(a2, L"TMP", &hMem) )
      {
        if ( g_dmDiagnosticMode )
        {
          v9 = "ERROR: Failed to get environment variable: TMP";
          goto LABEL_26;
        }
LABEL_43:
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
LABEL_44:
        if ( v20 > 261 )
          GlobalFree(hMem);
        return 0;
      }
      MsiString::MsiString((MsiString *)&v14, (const unsigned __int16 *)hMem);
      if ( (*(unsigned int (__fastcall **)(__int64, __int64, const wchar_t *))(*(_QWORD *)v14 + 200LL))(v14, 3, L"\\\\") != 1
        || (*(unsigned int (__fastcall **)(__int64, __int64, const wchar_t *))(*(_QWORD *)v14 + 200LL))(
             v14,
             3,
             L"\\\\?\\") )
      {
        v24 = 0;
        memset_0(v25, 0, sizeof(v25));
        if ( (int)StringCchPrintfW(&v24, 0x190u, L"%c:\\Windows\\SystemTemp", Buffer[0]) < 0 )
        {
          if ( g_dmDiagnosticMode )
          {
            v10 = "ERROR: StringCchPrintf failure in CMsiEnvironmentBlock::InitializeFromSystemEnvironment";
            goto LABEL_41;
          }
          goto LABEL_42;
        }
        if ( !CMsiEnvironmentBlock::Set(this, L"TMP", &v24) )
        {
          if ( g_dmDiagnosticMode )
          {
            v10 = "ERROR: Failed to set environment variable: TMP";
            goto LABEL_41;
          }
          goto LABEL_42;
        }
        if ( !CMsiEnvironmentBlock::Set(this, L"TEMP", &v24) )
        {
          if ( !g_dmDiagnosticMode )
            goto LABEL_42;
          v10 = "ERROR: Failed to set environment variable: TEMP";
          goto LABEL_41;
        }
      }
      else
      {
        if ( !CMsiEnvironmentBlock::Set(this, L"TMP", (const unsigned __int16 *)hMem) )
        {
          if ( g_dmDiagnosticMode )
          {
            v10 = "ERROR: Failed to set environment variable: TMP when it is remote path";
LABEL_41:
            DebugString(9, 0, 0, v10, "(NULL)", "(NULL)", "(NULL)", "(NULL)", "(NULL)", "(NULL)", v11, v12);
            goto LABEL_42;
          }
          goto LABEL_42;
        }
        if ( !CMsiEnvironmentBlock::Set(this, L"TEMP", (const unsigned __int16 *)hMem) )
        {
          if ( g_dmDiagnosticMode )
          {
            v10 = "ERROR: Failed to set environment variable: TEMP when it is remote path";
            goto LABEL_41;
          }
LABEL_42:
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
          goto LABEL_43;
        }
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      if ( v20 > 261 )
        GlobalFree(hMem);
    }
  }
  if ( g_dmDiagnosticMode )
    DebugString(
      9,
      0,
      0,
      "Current environment block after setting user environment variables",
      "(NULL)",
      "(NULL)",
      "(NULL)",
      "(NULL)",
      "(NULL)",
      "(NULL)",
      v11,
      v12);
  DumpEnvironment(*(const unsigned __int16 **)this);
  return 1;
}

```

## disassembly

```asm
0x1801cc988  mov     [rsp-8+arg_10], rbx
0x1801cc98d  mov     [rsp-8+arg_18], rsi
0x1801cc992  push    rbp
0x1801cc993  push    rdi
0x1801cc994  push    r14
0x1801cc996  lea     rbp, [rsp-0E50h]
0x1801cc99e  sub     rsp, 0F50h
0x1801cc9a5  mov     rax, cs:__security_cookie
0x1801cc9ac  xor     rax, rsp
0x1801cc9af  mov     [rbp+0E60h+var_20], rax
0x1801cc9b6  mov     rdi, rdx
0x1801cc9b9  mov     rbx, rcx
0x1801cc9bc  mov     dl, 1; bool
0x1801cc9be  call    ?InitializeFromEnvironment@CMsiEnvironmentBlock@@AEAA_N_N@Z; CMsiEnvironmentBlock::InitializeFromEnvironment(bool)
0x1801cc9c3  xor     esi, esi
0x1801cc9c5  test    al, al
0x1801cc9c7  jz      loc_1801CCB43
0x1801cc9cd  lea     rcx, ?g_MessageContext@@3UMsiUIMessageContext@@A; this
0x1801cc9d4  call    ?GetUserToken@MsiUIMessageContext@@QEAAPEAXXZ; MsiUIMessageContext::GetUserToken(void)
0x1801cc9d9  mov     rcx, rax; void *
0x1801cc9dc  call    ?IsLocalSystemToken@@YA_NPEAX@Z; IsLocalSystemToken(void *)
0x1801cc9e1  test    al, al
0x1801cc9e3  jnz     loc_1801CCEDC
0x1801cc9e9  lea     rcx, ?g_MessageContext@@3UMsiUIMessageContext@@A; this
0x1801cc9f0  call    ?GetUserToken@MsiUIMessageContext@@QEAAPEAXXZ; MsiUIMessageContext::GetUserToken(void)
0x1801cc9f5  test    rax, rax
0x1801cc9f8  jz      loc_1801CCEDC
0x1801cc9fe  lea     rcx, [rsp+0F60h+var_EF0]
0x1801cca03  mov     [rsp+0F60h+cchName], 1F4h
0x1801cca0b  mov     [rsp+0F60h+ReturnLength], rcx; ReturnLength
0x1801cca10  lea     r9d, [rsi+58h]; TokenInformationLength
0x1801cca14  mov     rcx, rax; TokenHandle
0x1801cca17  mov     [rsp+0F60h+var_EE8], 190h
0x1801cca1f  lea     r8, [rbp+0E60h+TokenInformation]; TokenInformation
0x1801cca26  mov     [rsp+0F60h+var_EF0], esi
0x1801cca2a  lea     edx, [rsi+1]; TokenInformationClass
0x1801cca2d  call    cs:__imp_GetTokenInformation
0x1801cca34  nop     dword ptr [rax+rax+00h]
0x1801cca39  test    eax, eax
0x1801cca3b  jnz     short loc_1801CCA61
0x1801cca3d  call    cs:__imp_GetLastError
0x1801cca44  nop     dword ptr [rax+rax+00h]
0x1801cca49  cmp     cs:?g_dmDiagnosticMode@@3HA, esi; int g_dmDiagnosticMode
0x1801cca4f  jz      loc_1801CCB43
0x1801cca55  lea     r9, aErrorGettokeni; "ERROR: GetTokenInformation failed with "...
0x1801cca5c  jmp     loc_1801CCB06
0x1801cca61  mov     rdx, [rbp+0E60h+TokenInformation]; Sid
0x1801cca68  lea     rax, [rsp+0F60h+var_EEC]
0x1801cca6d  mov     [rsp+0F60h+peUse], rax; peUse
0x1801cca72  lea     r9, [rsp+0F60h+cchName]; cchName
0x1801cca77  lea     rax, [rsp+0F60h+var_EE8]
0x1801cca7c  mov     [rsp+0F60h+var_EEC], esi
0x1801cca80  mov     [rsp+0F60h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1801cca85  lea     r8, [rbp+0E60h+Name]; Name
0x1801cca8c  lea     rax, [rbp+0E60h+ReferencedDomainName]
0x1801cca93  xor     ecx, ecx; lpSystemName
0x1801cca95  mov     [rsp+0F60h+ReturnLength], rax; ReferencedDomainName
0x1801cca9a  call    cs:__imp_LookupAccountSidW
0x1801ccaa1  nop     dword ptr [rax+rax+00h]
0x1801ccaa6  test    eax, eax
0x1801ccaa8  jnz     short loc_1801CCACB
0x1801ccaaa  call    cs:__imp_GetLastError
0x1801ccab1  nop     dword ptr [rax+rax+00h]
0x1801ccab6  cmp     cs:?g_dmDiagnosticMode@@3HA, esi; int g_dmDiagnosticMode
0x1801ccabc  jz      loc_1801CCB43
0x1801ccac2  lea     r9, aErrorLookupacc; "ERROR: LookupAccountSid failed with err"...
0x1801ccac9  jmp     short loc_1801CCB06
0x1801ccacb  mov     edx, 104h; uSize
0x1801ccad0  lea     rcx, [rbp+0E60h+Buffer]; lpBuffer
0x1801ccad7  call    cs:__imp_GetSystemDirectoryW
0x1801ccade  nop     dword ptr [rax+rax+00h]
0x1801ccae3  test    eax, eax
0x1801ccae5  jnz     loc_1801CCB6D
0x1801ccaeb  call    cs:__imp_GetLastError
0x1801ccaf2  nop     dword ptr [rax+rax+00h]
0x1801ccaf7  cmp     cs:?g_dmDiagnosticMode@@3HA, esi; int g_dmDiagnosticMode
0x1801ccafd  jz      short loc_1801CCB43
0x1801ccaff  lea     r9, aErrorGetsystem; "ERROR: GetSystemDirectory failed with e"...
0x1801ccb06  mov     [rsp+0F60h+var_F08], rsi; void *
0x1801ccb0b  lea     rcx, aNull; "(NULL)"
0x1801ccb12  mov     [rsp+0F60h+var_F10], esi; unsigned int
0x1801ccb16  xor     edx, edx; unsigned __int16
0x1801ccb18  mov     [rsp+0F60h+var_F18], rcx; unsigned __int16 *
0x1801ccb1d  xor     r8d, r8d; int
0x1801ccb20  mov     [rsp+0F60h+var_F20], rcx; unsigned __int16 *
0x1801ccb25  mov     [rsp+0F60h+var_F28], rcx; unsigned __int16 *
0x1801ccb2a  mov     [rsp+0F60h+peUse], rcx; unsigned __int16 *
0x1801ccb2f  mov     [rsp+0F60h+cchReferencedDomainName], rcx; unsigned __int16 *
0x1801ccb34  lea     ecx, [rdx+9]; int
0x1801ccb37  mov     eax, eax
0x1801ccb39  mov     [rsp+0F60h+ReturnLength], rax; unsigned __int16 *
0x1801ccb3e  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1801ccb43  xor     al, al
0x1801ccb45  mov     rcx, [rbp+0E60h+var_20]
0x1801ccb4c  xor     rcx, rsp; StackCookie
0x1801ccb4f  call    __security_check_cookie
0x1801ccb54  lea     r11, [rsp+0F60h+var_10]
0x1801ccb5c  mov     rbx, [r11+30h]
0x1801ccb60  mov     rsi, [r11+38h]
0x1801ccb64  mov     rsp, r11
0x1801ccb67  pop     r14
0x1801ccb69  pop     rdi
0x1801ccb6a  pop     rbp
0x1801ccb6b  retn
0x1801ccb6d  mov     r14d, 105h
0x1801ccb73  lea     rax, [rbp+0E60h+var_ED0]
0x1801ccb77  lea     r8, [rbp+0E60h+hMem]
0x1801ccb7b  mov     [rbp+0E60h+var_ED8], r14d
0x1801ccb7f  lea     rdx, aUserprofile_0; "USERPROFILE"
0x1801ccb86  mov     [rbp+0E60h+hMem], rax
0x1801ccb8a  mov     rcx, rdi
0x1801ccb8d  mov     [rbp+0E60h+var_ED4], r14d
0x1801ccb91  call    ?Get@CMsiEnvironmentBlock@@QEBA_NPEBGAEAV?$CAPITempBufferRef@G@@@Z; CMsiEnvironmentBlock::Get(ushort const *,CAPITempBufferRef<ushort> &)
0x1801ccb96  test    al, al
0x1801ccb98  jnz     short loc_1801CCBE4
0x1801ccb9a  cmp     cs:?g_dmDiagnosticMode@@3HA, esi; int g_dmDiagnosticMode
0x1801ccba0  jz      loc_1801CCE57
0x1801ccba6  lea     rax, aNull_0; "(NULL)"
0x1801ccbad  xor     edx, edx; unsigned __int16
0x1801ccbaf  mov     [rsp+0F60h+var_F18], rax; char *
0x1801ccbb4  lea     r9, aErrorFailedToG; "ERROR: Failed to get environment variab"...
0x1801ccbbb  mov     [rsp+0F60h+var_F20], rax; char *
0x1801ccbc0  xor     r8d, r8d; int
0x1801ccbc3  mov     [rsp+0F60h+var_F28], rax; char *
0x1801ccbc8  mov     [rsp+0F60h+peUse], rax; char *
0x1801ccbcd  lea     ecx, [rdx+9]; int
0x1801ccbd0  mov     [rsp+0F60h+cchReferencedDomainName], rax; char *
0x1801ccbd5  mov     [rsp+0F60h+ReturnLength], rax; char *
0x1801ccbda  call    ?DebugString@@YAXHGHPEBD000000KPEAX@Z; DebugString(int,ushort,int,char const *,char const *,char const *,char const *,char const *,char const *,char const *,ulong,void *)
0x1801ccbdf  jmp     loc_1801CCE57
0x1801ccbe4  mov     rdx, [rbp+0E60h+hMem]; unsigned __int16 *
0x1801ccbe8  lea     rcx, [rsp+0F60h+var_F00]; this
0x1801ccbed  call    ??0MsiString@@QEAA@PEBG@Z; MsiString::MsiString(ushort const *)
0x1801ccbf2  mov     rcx, [rsp+0F60h+var_F00]
0x1801ccbf7  lea     r8, asc_1802B8C88; "\\\\"
0x1801ccbfe  mov     edx, 3
0x1801ccc03  mov     rax, [rcx]
0x1801ccc06  mov     rax, [rax+0C8h]
0x1801ccc0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ccc12  cmp     eax, 1
0x1801ccc15  jnz     short loc_1801CCC67
0x1801ccc17  mov     rcx, [rsp+0F60h+var_F00]
0x1801ccc1c  lea     r8, asc_1802B8C90; "\\\\?\\"
0x1801ccc23  mov     edx, 3
0x1801ccc28  mov     rax, [rcx]
0x1801ccc2b  mov     rax, [rax+0C8h]
0x1801ccc32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ccc37  test    eax, eax
0x1801ccc39  jnz     short loc_1801CCC67
0x1801ccc3b  mov     r8, [rbp+0E60h+hMem]; unsigned __int16 *
0x1801ccc3f  lea     rdx, aUserprofile_0; "USERPROFILE"
0x1801ccc46  mov     rcx, rbx; this
0x1801ccc49  call    ?Set@CMsiEnvironmentBlock@@QEAA_NPEBG0@Z; CMsiEnvironmentBlock::Set(ushort const *,ushort const *)
0x1801ccc4e  test    al, al
0x1801ccc50  jnz     short loc_1801CCC67
0x1801ccc52  cmp     cs:?g_dmDiagnosticMode@@3HA, esi; int g_dmDiagnosticMode
0x1801ccc58  jz      loc_1801CCE46
0x1801ccc5e  lea     r9, aErrorFailedToS_3; "ERROR: Failed to set environment variab"...
0x1801ccc65  jmp     short loc_1801CCC95
0x1801ccc67  lea     r8, [rbp+0E60h+hMem]
0x1801ccc6b  mov     [rbp+0E60h+var_ED4], r14d
0x1801ccc6f  lea     rdx, aTmp; "TMP"
0x1801ccc76  mov     rcx, rdi
0x1801ccc79  call    ?Get@CMsiEnvironmentBlock@@QEBA_NPEBGAEAV?$CAPITempBufferRef@G@@@Z; CMsiEnvironmentBlock::Get(ushort const *,CAPITempBufferRef<ushort> &)
0x1801ccc7e  test    al, al
0x1801ccc80  jnz     short loc_1801CCCCC
0x1801ccc82  cmp     cs:?g_dmDiagnosticMode@@3HA, esi; int g_dmDiagnosticMode
0x1801ccc88  jz      loc_1801CCE46
0x1801ccc8e  lea     r9, aErrorFailedToG_1; "ERROR: Failed to get environment variab"...
0x1801ccc95  lea     rax, aNull_0; "(NULL)"
0x1801ccc9c  xor     edx, edx; unsigned __int16
0x1801ccc9e  mov     [rsp+0F60h+var_F18], rax; char *
0x1801ccca3  xor     r8d, r8d; int
0x1801ccca6  mov     [rsp+0F60h+var_F20], rax; char *
0x1801cccab  mov     [rsp+0F60h+var_F28], rax; char *
0x1801cccb0  mov     [rsp+0F60h+peUse], rax; char *
0x1801cccb5  lea     ecx, [rdx+9]; int
0x1801cccb8  mov     [rsp+0F60h+cchReferencedDomainName], rax; char *
0x1801cccbd  mov     [rsp+0F60h+ReturnLength], rax; char *
0x1801cccc2  call    ?DebugString@@YAXHGHPEBD000000KPEAX@Z; DebugString(int,ushort,int,char const *,char const *,char const *,char const *,char const *,char const *,char const *,ulong,void *)
0x1801cccc7  jmp     loc_1801CCE46
0x1801ccccc  mov     rdx, [rbp+0E60h+hMem]; unsigned __int16 *
0x1801cccd0  lea     rcx, [rsp+0F60h+var_EF8]; this
0x1801cccd5  call    ??0MsiString@@QEAA@PEBG@Z; MsiString::MsiString(ushort const *)
0x1801cccda  mov     rcx, [rsp+0F60h+var_EF8]
0x1801cccdf  lea     r8, asc_1802B8C88; "\\\\"
0x1801ccce6  mov     edx, 3
0x1801ccceb  mov     rax, [rcx]
0x1801cccee  mov     rax, [rax+0C8h]
0x1801cccf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801cccfa  cmp     eax, 1
0x1801cccfd  jnz     loc_1801CCD86
0x1801ccd03  mov     rcx, [rsp+0F60h+var_EF8]
0x1801ccd08  lea     r8, asc_1802B8C90; "\\\\?\\"
0x1801ccd0f  mov     edx, 3
0x1801ccd14  mov     rax, [rcx]
0x1801ccd17  mov     rax, [rax+0C8h]
0x1801ccd1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ccd23  test    eax, eax
0x1801ccd25  jnz     short loc_1801CCD86
0x1801ccd27  mov     r8, [rbp+0E60h+hMem]; unsigned __int16 *
0x1801ccd2b  lea     rdx, aTmp; "TMP"
0x1801ccd32  mov     rcx, rbx; this
0x1801ccd35  call    ?Set@CMsiEnvironmentBlock@@QEAA_NPEBG0@Z; CMsiEnvironmentBlock::Set(ushort const *,ushort const *)
0x1801ccd3a  test    al, al
0x1801ccd3c  jnz     short loc_1801CCD56
0x1801ccd3e  cmp     cs:?g_dmDiagnosticMode@@3HA, esi; int g_dmDiagnosticMode
0x1801ccd44  jz      loc_1801CCE35
0x1801ccd4a  lea     r9, aErrorFailedToS; "ERROR: Failed to set environment variab"...
0x1801ccd51  jmp     loc_1801CCE03
0x1801ccd56  mov     r8, [rbp+0E60h+hMem]; unsigned __int16 *
0x1801ccd5a  lea     rdx, aTemp; "TEMP"
0x1801ccd61  mov     rcx, rbx; this
0x1801ccd64  call    ?Set@CMsiEnvironmentBlock@@QEAA_NPEBG0@Z; CMsiEnvironmentBlock::Set(ushort const *,ushort const *)
0x1801ccd69  test    al, al
0x1801ccd6b  jnz     loc_1801CCEA4
0x1801ccd71  cmp     cs:?g_dmDiagnosticMode@@3HA, esi; int g_dmDiagnosticMode
0x1801ccd77  jz      loc_1801CCE35
0x1801ccd7d  lea     r9, aErrorFailedToS_0; "ERROR: Failed to set environment variab"...
0x1801ccd84  jmp     short loc_1801CCE03
0x1801ccd86  xor     edx, edx; Val
0x1801ccd88  mov     [rbp+0E60h+var_C60], si
0x1801ccd8f  mov     r8d, 31Eh; Size
0x1801ccd95  lea     rcx, [rbp+0E60h+var_C5E]; void *
0x1801ccd9c  call    memset_0
0x1801ccda1  movzx   r9d, [rbp+0E60h+Buffer]
0x1801ccda9  lea     r8, aCWindowsSystem; "%c:\\Windows\\SystemTemp"
0x1801ccdb0  mov     edx, 190h; unsigned __int64
0x1801ccdb5  lea     rcx, [rbp+0E60h+var_C60]; unsigned __int16 *
0x1801ccdbc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801ccdc1  test    eax, eax
0x1801ccdc3  jns     short loc_1801CCDD6
0x1801ccdc5  cmp     cs:?g_dmDiagnosticMode@@3HA, esi; int g_dmDiagnosticMode
0x1801ccdcb  jz      short loc_1801CCE35
0x1801ccdcd  lea     r9, aErrorStringcch_0; "ERROR: StringCchPrintf failure in CMsiE"...
0x1801ccdd4  jmp     short loc_1801CCE03
0x1801ccdd6  lea     r8, [rbp+0E60h+var_C60]; unsigned __int16 *
0x1801ccddd  mov     rcx, rbx; this
0x1801ccde0  lea     rdx, aTmp; "TMP"
0x1801ccde7  call    ?Set@CMsiEnvironmentBlock@@QEAA_NPEBG0@Z; CMsiEnvironmentBlock::Set(ushort const *,ushort const *)
0x1801ccdec  test    al, al
0x1801ccdee  jnz     loc_1801CCE76
0x1801ccdf4  cmp     cs:?g_dmDiagnosticMode@@3HA, esi; int g_dmDiagnosticMode
0x1801ccdfa  jz      short loc_1801CCE35
0x1801ccdfc  lea     r9, aErrorFailedToS_2; "ERROR: Failed to set environment variab"...
0x1801cce03  lea     rax, aNull_0; "(NULL)"
0x1801cce0a  xor     edx, edx; unsigned __int16
0x1801cce0c  mov     [rsp+0F60h+var_F18], rax; char *
0x1801cce11  xor     r8d, r8d; int
0x1801cce14  mov     [rsp+0F60h+var_F20], rax; char *
0x1801cce19  mov     [rsp+0F60h+var_F28], rax; char *
0x1801cce1e  mov     [rsp+0F60h+peUse], rax; char *
0x1801cce23  lea     ecx, [rdx+9]; int
0x1801cce26  mov     [rsp+0F60h+cchReferencedDomainName], rax; char *
0x1801cce2b  mov     [rsp+0F60h+ReturnLength], rax; char *
0x1801cce30  call    ?DebugString@@YAXHGHPEBD000000KPEAX@Z; DebugString(int,ushort,int,char const *,char const *,char const *,char const *,char const *,char const *,char const *,ulong,void *)
0x1801cce35  mov     rcx, [rsp+0F60h+var_EF8]
0x1801cce3a  mov     rax, [rcx]
0x1801cce3d  mov     rax, [rax+10h]
0x1801cce41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801cce46  mov     rcx, [rsp+0F60h+var_F00]
0x1801cce4b  mov     rax, [rcx]
0x1801cce4e  mov     rax, [rax+10h]
0x1801cce52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801cce57  cmp     [rbp+0E60h+var_ED8], r14d
0x1801cce5b  jle     loc_1801CCB43
0x1801cce61  mov     rcx, [rbp+0E60h+hMem]; hMem
0x1801cce65  call    cs:__imp_GlobalFree
0x1801cce6c  nop     dword ptr [rax+rax+00h]
0x1801cce71  jmp     loc_1801CCB43
0x1801cce76  lea     r8, [rbp+0E60h+var_C60]; unsigned __int16 *
0x1801cce7d  mov     rcx, rbx; this
0x1801cce80  lea     rdx, aTemp; "TEMP"
0x1801cce87  call    ?Set@CMsiEnvironmentBlock@@QEAA_NPEBG0@Z; CMsiEnvironmentBlock::Set(ushort const *,ushort const *)
0x1801cce8c  test    al, al
0x1801cce8e  jnz     short loc_1801CCEA4
0x1801cce90  cmp     cs:?g_dmDiagnosticMode@@3HA, esi; int g_dmDiagnosticMode
0x1801cce96  jz      short loc_1801CCE35
0x1801cce98  lea     r9, aErrorFailedToS_1; "ERROR: Failed to set environment variab"...
0x1801cce9f  jmp     loc_1801CCE03
0x1801ccea4  mov     rcx, [rsp+0F60h+var_EF8]
0x1801ccea9  mov     rax, [rcx]
0x1801cceac  mov     rax, [rax+10h]
0x1801cceb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801cceb5  mov     rcx, [rsp+0F60h+var_F00]
0x1801cceba  mov     rax, [rcx]
0x1801ccebd  mov     rax, [rax+10h]
0x1801ccec1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ccec6  cmp     [rbp+0E60h+var_ED8], r14d
0x1801cceca  jle     short loc_1801CCEDC
0x1801ccecc  mov     rcx, [rbp+0E60h+hMem]; hMem
0x1801cced0  call    cs:__imp_GlobalFree
0x1801cced7  nop     dword ptr [rax+rax+00h]
0x1801ccedc  cmp     cs:?g_dmDiagnosticMode@@3HA, esi; int g_dmDiagnosticMode
0x1801ccee2  jz      short loc_1801CCF1D
0x1801ccee4  lea     rax, aNull_0; "(NULL)"
0x1801cceeb  xor     edx, edx; unsigned __int16
0x1801cceed  mov     [rsp+0F60h+var_F18], rax; char *
0x1801ccef2  lea     r9, aCurrentEnviron; "Current environment block after setting"...
0x1801ccef9  mov     [rsp+0F60h+var_F20], rax; char *
  ... truncated ...
```
