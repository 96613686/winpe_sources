# CSecurityDispenser::AdjustTokenForAdministrators(void *)

- ea: `0x1800178d0`
- end: `0x180017c3c`
- name: `?AdjustTokenForAdministrators@CSecurityDispenser@@QEAAKPEAX@Z`
- size: `876`
- prototype: `unsigned int __fastcall(CSecurityDispenser *__hidden this, HANDLE TokenHandle)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180002470`
- `0x180002b60`
- `0x180016d20`
- `0x1800178d0`
- `0x1800180c0`
- `0x18002c48e`
- `0x18002c4c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001796d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800179be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017a4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017b74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001796d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800179be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017a4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017b74`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017bf4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017bf4`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x180017b6a`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x180017b6a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001795f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180017a43`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001795f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180017a43`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180017b1c`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180017b1c`

## string_xrefs

- `0x1800179ff`: `servercommon\inetsrv\iis\iisrearc\core\common\util\secfcns.cxx`
- `0x180017bdf`: `servercommon\inetsrv\iis\iisrearc\core\common\util\secfcns.cxx`
- `0x1800179e6`: `CSecurityDispenser::AdjustTokenForAdministrators`
- `0x180017bd8`: `CSecurityDispenser::AdjustTokenForAdministrators`
- `0x180017b91`: `Failed to reset token's default actl\n`
- `0x180017993`: `Failed to get size of default token\n`
- `0x180017ac8`: `Getting Admin Sid Failed\n`
- `0x180017a6e`: `Failed to get the default token\n`
- `0x1800179ed`: `Failed to resize the buffer for default dacl to %d\n`
- `0x180017b41`: `Failed to set entries in token\n`

## pseudocode

```c
__int64 __fastcall CSecurityDispenser::AdjustTokenForAdministrators(CSecurityDispenser *this, char *TokenHandle)
{
  int LastError; // eax
  unsigned int v5; // ebx
  int v6; // eax
  int v7; // eax
  signed int SID; // eax
  int v9; // eax
  int v10; // eax
  char v12; // [rsp+30h] [rbp-49h]
  DWORD TokenInformationLength; // [rsp+40h] [rbp-39h] BYREF
  PACL NewAcl; // [rsp+48h] [rbp-31h] BYREF
  void *v15; // [rsp+50h] [rbp-29h] BYREF
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+58h] [rbp-21h] BYREF
  _QWORD v17[4]; // [rsp+88h] [rbp+Fh] BYREF
  void *TokenInformation; // [rsp+A8h] [rbp+2Fh]
  int v19; // [rsp+B0h] [rbp+37h]
  __int16 v20; // [rsp+B4h] [rbp+3Bh]

  TokenInformationLength = 0;
  v15 = 0;
  TokenInformation = v17;
  v17[0] = 0;
  v19 = 32;
  v20 = 256;
  NewAcl = 0;
  memset(&pListOfExplicitEntries, 0, sizeof(pListOfExplicitEntries));
  if ( (unsigned __int64)(TokenHandle - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    BUFFER::~BUFFER((BUFFER *)v17);
    return 87;
  }
  else
  {
    if ( GetTokenInformation(TokenHandle, TokenDefaultDacl, 0, 0, &TokenInformationLength) )
    {
      v5 = 110;
      if ( (g_dwDebugFlagsIISUtil & 0xF) != 0 )
        PuDbgPrintError(
          (struct _DEBUG_PRINTS *)g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\secfcns.cxx",
          0x360u,
          "CSecurityDispenser::AdjustTokenForAdministrators",
          0x8007006E,
          "Did not get an error when we expected to ( changed the error to this hr ) \n",
          v12);
    }
    else
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError == 122 )
      {
        if ( BUFFER::Resize((BUFFER *)v17, TokenInformationLength) )
        {
          memset_0(TokenInformation, 0, TokenInformationLength);
          if ( GetTokenInformation(
                 TokenHandle,
                 TokenDefaultDacl,
                 TokenInformation,
                 TokenInformationLength,
                 &TokenInformationLength) )
          {
            memset(&pListOfExplicitEntries, 0, sizeof(pListOfExplicitEntries));
            SID = CSecurityDispenser::GetSID(this, WinBuiltinAdministratorsSid, &v15);
            v5 = SID;
            if ( SID )
            {
              if ( (g_dwDebugFlagsIISUtil & 0xF) != 0 )
              {
                if ( SID > 0 )
                  SID = (unsigned __int16)SID | 0x80070000;
                PuDbgPrintError(
                  (struct _DEBUG_PRINTS *)g_pDebug,
                  "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\secfcns.cxx",
                  0x399u,
                  "CSecurityDispenser::AdjustTokenForAdministrators",
                  SID,
                  "Getting Admin Sid Failed\n",
                  v12);
              }
            }
            else
            {
              *(_QWORD *)&pListOfExplicitEntries.grfAccessMode = 1;
              pListOfExplicitEntries.Trustee.TrusteeForm = TRUSTEE_IS_SID;
              pListOfExplicitEntries.Trustee.TrusteeType = TRUSTEE_IS_WELL_KNOWN_GROUP;
              pListOfExplicitEntries.grfAccessPermissions = 0x10000000;
              pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)v15;
              v9 = SetEntriesInAclW(1u, &pListOfExplicitEntries, *(PACL *)TokenInformation, &NewAcl);
              v5 = v9;
              if ( v9 )
              {
                if ( (g_dwDebugFlagsIISUtil & 0xF) != 0 )
                {
                  if ( v9 > 0 )
                    v9 = (unsigned __int16)v9 | 0x80070000;
                  PuDbgPrintError(
                    (struct _DEBUG_PRINTS *)g_pDebug,
                    "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\secfcns.cxx",
                    0x3B4u,
                    "CSecurityDispenser::AdjustTokenForAdministrators",
                    v9,
                    "Failed to set entries in token\n",
                    v12);
                }
              }
              else if ( !SetTokenInformation(TokenHandle, TokenDefaultDacl, &NewAcl, 8u) )
              {
                v10 = GetLastError();
                v5 = v10;
                if ( (g_dwDebugFlagsIISUtil & 0xF) != 0 )
                {
                  if ( v10 > 0 )
                    v10 = (unsigned __int16)v10 | 0x80070000;
                  PuDbgPrintError(
                    (struct _DEBUG_PRINTS *)g_pDebug,
                    "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\secfcns.cxx",
                    0x3C7u,
                    "CSecurityDispenser::AdjustTokenForAdministrators",
                    v10,
                    "Failed to reset token's default actl\n",
                    v12);
                }
              }
            }
          }
          else
          {
            v7 = GetLastError();
            v5 = v7;
            if ( (g_dwDebugFlagsIISUtil & 0xF) != 0 )
            {
              if ( v7 > 0 )
                v7 = (unsigned __int16)v7 | 0x80070000;
              PuDbgPrintError(
                (struct _DEBUG_PRINTS *)g_pDebug,
                "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\secfcns.cxx",
                0x38Au,
                "CSecurityDispenser::AdjustTokenForAdministrators",
                v7,
                "Failed to get the default token\n",
                v12);
            }
          }
        }
        else
        {
          v6 = GetLastError();
          v5 = v6;
          if ( (g_dwDebugFlagsIISUtil & 0xF) != 0 )
          {
            if ( v6 > 0 )
              v6 = (unsigned __int16)v6 | 0x80070000;
            PuDbgPrintError(
              (struct _DEBUG_PRINTS *)g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\secfcns.cxx",
              0x36Fu,
              "CSecurityDispenser::AdjustTokenForAdministrators",
              v6,
              "Failed to resize the buffer for default dacl to %d\n",
              TokenInformationLength);
          }
        }
      }
      else if ( (g_dwDebugFlagsIISUtil & 0xF) != 0 )
      {
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        PuDbgPrintError(
          (struct _DEBUG_PRINTS *)g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\secfcns.cxx",
          0x351u,
          "CSecurityDispenser::AdjustTokenForAdministrators",
          LastError,
          "Failed to get size of default token\n",
          v12);
      }
    }
    if ( NewAcl )
    {
      LocalFree(NewAcl);
      NewAcl = 0;
    }
    BUFFER::~BUFFER((BUFFER *)v17);
    return v5;
  }
}

```

## disassembly

```asm
0x1800178d0  mov     [rsp-8+arg_10], rbx
0x1800178d5  push    rbp
0x1800178d6  push    rsi
0x1800178d7  push    rdi
0x1800178d8  lea     rbp, [rsp-47h]
0x1800178dd  sub     rsp, 0C0h
0x1800178e4  mov     rax, cs:__security_cookie
0x1800178eb  xor     rax, rsp
0x1800178ee  mov     [rbp+57h+var_18], rax
0x1800178f2  xorps   xmm0, xmm0
0x1800178f5  mov     [rbp+57h+TokenInformationLength], 0
0x1800178fc  lea     rax, [rbp+57h+var_48]
0x180017900  mov     [rbp+57h+var_80], 0
0x180017908  mov     [rbp+57h+TokenInformation], rax
0x18001790c  mov     rdi, rdx
0x18001790f  lea     rax, [rdx-1]
0x180017913  mov     [rbp+57h+var_48], 0
0x18001791b  mov     [rbp+57h+var_20], 20h ; ' '
0x180017922  mov     rsi, rcx
0x180017925  mov     [rbp+57h+var_1C], 100h
0x18001792b  mov     [rbp+57h+NewAcl], 0
0x180017933  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], xmm0
0x180017937  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.Trustee.pMultipleTrustee], xmm0
0x18001793b  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeType], xmm0
0x18001793f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180017943  ja      loc_180017C0F
0x180017949  xor     r9d, r9d; TokenInformationLength
0x18001794c  lea     rax, [rbp+57h+TokenInformationLength]
0x180017950  xor     r8d, r8d; TokenInformation
0x180017953  mov     [rsp+0D0h+ReturnLength], rax; ReturnLength
0x180017958  mov     rcx, rdi; TokenHandle
0x18001795b  lea     edx, [r9+6]; TokenInformationClass
0x18001795f  call    cs:__imp_GetTokenInformation
0x180017965  test    eax, eax
0x180017967  jnz     loc_180017BA9
0x18001796d  call    cs:__imp_GetLastError
0x180017973  mov     ebx, eax
0x180017975  cmp     eax, 7Ah ; 'z'
0x180017978  jz      short loc_1800179AE
0x18001797a  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x180017981  jz      loc_180017BEB
0x180017987  test    eax, eax
0x180017989  jle     short loc_180017993
0x18001798b  movzx   eax, ax
0x18001798e  or      eax, 80070000h
0x180017993  lea     rcx, aFailedToGetSiz; "Failed to get size of default token\n"
0x18001799a  mov     r8d, 351h
0x1800179a0  mov     [rsp+0D0h+var_A8], rcx
0x1800179a5  mov     dword ptr [rsp+0D0h+ReturnLength], eax
0x1800179a9  jmp     loc_180017BD1
0x1800179ae  mov     edx, [rbp+57h+TokenInformationLength]; unsigned int
0x1800179b1  lea     rcx, [rbp+57h+var_48]; this
0x1800179b5  call    ?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x1800179ba  test    al, al
0x1800179bc  jnz     short loc_180017A1B
0x1800179be  call    cs:__imp_GetLastError
0x1800179c4  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x1800179cb  mov     ebx, eax
0x1800179cd  jz      loc_180017BEB
0x1800179d3  mov     ecx, [rbp+57h+TokenInformationLength]
0x1800179d6  test    eax, eax
0x1800179d8  jle     short loc_1800179E2
0x1800179da  movzx   eax, ax
0x1800179dd  or      eax, 80070000h
0x1800179e2  mov     dword ptr [rsp+0D0h+var_A0], ecx; char
0x1800179e6  lea     r9, aCsecuritydispe_0; "CSecurityDispenser::AdjustTokenForAdmin"...
0x1800179ed  lea     rcx, aFailedToResize_0; "Failed to resize the buffer for default"...
0x1800179f4  mov     r8d, 36Fh; unsigned int
0x1800179fa  mov     [rsp+0D0h+var_A8], rcx; char *
0x1800179ff  lea     rdx, aServercommonIn_10; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180017a06  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180017a0d  mov     dword ptr [rsp+0D0h+ReturnLength], eax; dwMessageId
0x180017a11  call    PuDbgPrintError
0x180017a16  jmp     loc_180017BEB
0x180017a1b  mov     r8d, [rbp+57h+TokenInformationLength]; Size
0x180017a1f  xor     edx, edx; Val
0x180017a21  mov     rcx, [rbp+57h+TokenInformation]; void *
0x180017a25  call    memset_0
0x180017a2a  mov     r9d, [rbp+57h+TokenInformationLength]; TokenInformationLength
0x180017a2e  lea     rax, [rbp+57h+TokenInformationLength]
0x180017a32  mov     r8, [rbp+57h+TokenInformation]; TokenInformation
0x180017a36  mov     edx, 6; TokenInformationClass
0x180017a3b  mov     rcx, rdi; TokenHandle
0x180017a3e  mov     [rsp+0D0h+ReturnLength], rax; ReturnLength
0x180017a43  call    cs:__imp_GetTokenInformation
0x180017a49  test    eax, eax
0x180017a4b  jnz     short loc_180017A89
0x180017a4d  call    cs:__imp_GetLastError
0x180017a53  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x180017a5a  mov     ebx, eax
0x180017a5c  jz      loc_180017BEB
0x180017a62  test    eax, eax
0x180017a64  jle     short loc_180017A6E
0x180017a66  movzx   eax, ax
0x180017a69  or      eax, 80070000h
0x180017a6e  lea     rcx, aFailedToGetThe; "Failed to get the default token\n"
0x180017a75  mov     r8d, 38Ah
0x180017a7b  mov     [rsp+0D0h+var_A8], rcx
0x180017a80  mov     dword ptr [rsp+0D0h+ReturnLength], eax
0x180017a84  jmp     loc_180017BD1
0x180017a89  xorps   xmm0, xmm0
0x180017a8c  lea     r8, [rbp+57h+var_80]; void **
0x180017a90  mov     edx, 1Ah; enum WELL_KNOWN_SID_TYPE
0x180017a95  mov     rcx, rsi; this
0x180017a98  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], xmm0
0x180017a9c  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.Trustee.pMultipleTrustee], xmm0
0x180017aa0  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeType], xmm0
0x180017aa4  call    ?GetSID@CSecurityDispenser@@QEAAKW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z; CSecurityDispenser::GetSID(WELL_KNOWN_SID_TYPE,void * *)
0x180017aa9  mov     ebx, eax
0x180017aab  test    eax, eax
0x180017aad  jz      short loc_180017AE3
0x180017aaf  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x180017ab6  jz      loc_180017BEB
0x180017abc  test    eax, eax
0x180017abe  jle     short loc_180017AC8
0x180017ac0  movzx   eax, ax
0x180017ac3  or      eax, 80070000h
0x180017ac8  lea     rcx, aGettingAdminSi; "Getting Admin Sid Failed\n"
0x180017acf  mov     r8d, 399h
0x180017ad5  mov     [rsp+0D0h+var_A8], rcx
0x180017ada  mov     dword ptr [rsp+0D0h+ReturnLength], eax
0x180017ade  jmp     loc_180017BD1
0x180017ae3  mov     r8, [rbp+57h+TokenInformation]
0x180017ae7  lea     r9, [rbp+57h+NewAcl]; NewAcl
0x180017aeb  mov     rax, [rbp+57h+var_80]
0x180017aef  lea     rdx, [rbp+57h+pListOfExplicitEntries]; pListOfExplicitEntries
0x180017af3  mov     qword ptr [rbp+57h+pListOfExplicitEntries.grfAccessMode], 1
0x180017afb  mov     ecx, 1; cCountOfExplicitEntries
0x180017b00  mov     [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeForm], 0
0x180017b07  mov     [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeType], 5
0x180017b0e  mov     [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], 10000000h
0x180017b15  mov     [rbp+57h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x180017b19  mov     r8, [r8]; OldAcl
0x180017b1c  call    cs:__imp_SetEntriesInAclW
0x180017b22  mov     ebx, eax
0x180017b24  test    eax, eax
0x180017b26  jz      short loc_180017B59
0x180017b28  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x180017b2f  jz      loc_180017BEB
0x180017b35  test    eax, eax
0x180017b37  jle     short loc_180017B41
0x180017b39  movzx   eax, ax
0x180017b3c  or      eax, 80070000h
0x180017b41  lea     rcx, aFailedToSetEnt; "Failed to set entries in token\n"
0x180017b48  mov     r8d, 3B4h
0x180017b4e  mov     [rsp+0D0h+var_A8], rcx
0x180017b53  mov     dword ptr [rsp+0D0h+ReturnLength], eax
0x180017b57  jmp     short loc_180017BD1
0x180017b59  mov     r9d, 8; TokenInformationLength
0x180017b5f  lea     r8, [rbp+57h+NewAcl]; TokenInformation
0x180017b63  mov     rcx, rdi; TokenHandle
0x180017b66  lea     edx, [r9-2]; TokenInformationClass
0x180017b6a  call    cs:__imp_SetTokenInformation
0x180017b70  test    eax, eax
0x180017b72  jnz     short loc_180017BEB
0x180017b74  call    cs:__imp_GetLastError
0x180017b7a  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x180017b81  mov     ebx, eax
0x180017b83  jz      short loc_180017BEB
0x180017b85  test    eax, eax
0x180017b87  jle     short loc_180017B91
0x180017b89  movzx   eax, ax
0x180017b8c  or      eax, 80070000h
0x180017b91  lea     rcx, aFailedToResetT; "Failed to reset token's default actl\n"
0x180017b98  mov     r8d, 3C7h
0x180017b9e  mov     [rsp+0D0h+var_A8], rcx
0x180017ba3  mov     dword ptr [rsp+0D0h+ReturnLength], eax
0x180017ba7  jmp     short loc_180017BD1
0x180017ba9  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x180017bb0  mov     ebx, 6Eh ; 'n'
0x180017bb5  jz      short loc_180017BEB
0x180017bb7  lea     rax, aDidNotGetAnErr; "Did not get an error when we expected t"...
0x180017bbe  mov     r8d, 360h; unsigned int
0x180017bc4  mov     [rsp+0D0h+var_A8], rax; char *
0x180017bc9  mov     dword ptr [rsp+0D0h+ReturnLength], 8007006Eh; dwMessageId
0x180017bd1  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180017bd8  lea     r9, aCsecuritydispe_0; "CSecurityDispenser::AdjustTokenForAdmin"...
0x180017bdf  lea     rdx, aServercommonIn_10; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180017be6  call    PuDbgPrintError
0x180017beb  mov     rcx, [rbp+57h+NewAcl]; hMem
0x180017bef  test    rcx, rcx
0x180017bf2  jz      short loc_180017C02
0x180017bf4  call    cs:__imp_LocalFree
0x180017bfa  mov     [rbp+57h+NewAcl], 0
0x180017c02  lea     rcx, [rbp+57h+var_48]; this
0x180017c06  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180017c0b  mov     eax, ebx
0x180017c0d  jmp     short loc_180017C1D
0x180017c0f  lea     rcx, [rbp+57h+var_48]; this
0x180017c13  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180017c18  mov     eax, 57h ; 'W'
0x180017c1d  mov     rcx, [rbp+57h+var_18]
0x180017c21  xor     rcx, rsp; StackCookie
0x180017c24  call    __security_check_cookie
0x180017c29  mov     rbx, [rsp+0D0h+arg_10]
0x180017c31  add     rsp, 0C0h
0x180017c38  pop     rdi
0x180017c39  pop     rsi
0x180017c3a  pop     rbp
0x180017c3b  retn
```
