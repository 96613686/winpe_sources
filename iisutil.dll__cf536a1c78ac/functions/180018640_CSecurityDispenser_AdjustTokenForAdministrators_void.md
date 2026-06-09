# CSecurityDispenser::AdjustTokenForAdministrators(void *)

- ea: `0x180018640`
- end: `0x1800189e6`
- name: `?AdjustTokenForAdministrators@CSecurityDispenser@@QEAAKPEAX@Z`
- size: `934`
- prototype: `__int64 __fastcall(CSecurityDispenser *this, char *TokenHandle)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180002da0`
- `0x1800034f0`
- `0x1800179a0`
- `0x180018640`
- `0x180018ec0`
- `0x18002e52e`
- `0x18002e560`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800186e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001873a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800187d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018911`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800186e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001873a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800187d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018911`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018997`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018997`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x180018901`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x180018901`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800186cf`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800187c5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800186cf`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800187c5`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x1800188aa`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x1800188aa`

## string_xrefs

- `0x180018781`: `servercommon\inetsrv\iis\iisrearc\core\common\util\secfcns.cxx`
- `0x180018982`: `servercommon\inetsrv\iis\iisrearc\core\common\util\secfcns.cxx`
- `0x180018768`: `CSecurityDispenser::AdjustTokenForAdministrators`
- `0x18001897b`: `CSecurityDispenser::AdjustTokenForAdministrators`
- `0x180018934`: `Failed to reset token's default actl\n`
- `0x18001870f`: `Failed to get size of default token\n`
- `0x180018856`: `Getting Admin Sid Failed\n`
- `0x1800187fc`: `Failed to get the default token\n`
- `0x18001876f`: `Failed to resize the buffer for default dacl to %d\n`
- `0x1800188d5`: `Failed to set entries in token\n`

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
0x180018640  mov     [rsp-8+arg_10], rbx
0x180018645  push    rbp
0x180018646  push    rsi
0x180018647  push    rdi
0x180018648  lea     rbp, [rsp-47h]
0x18001864d  sub     rsp, 0C0h
0x180018654  mov     rax, cs:__security_cookie
0x18001865b  xor     rax, rsp
0x18001865e  mov     [rbp+57h+var_18], rax
0x180018662  xorps   xmm0, xmm0
0x180018665  mov     [rbp+57h+TokenInformationLength], 0
0x18001866c  lea     rax, [rbp+57h+var_48]
0x180018670  mov     [rbp+57h+var_80], 0
0x180018678  mov     [rbp+57h+TokenInformation], rax
0x18001867c  mov     rdi, rdx
0x18001867f  lea     rax, [rdx-1]
0x180018683  mov     [rbp+57h+var_48], 0
0x18001868b  mov     [rbp+57h+var_20], 20h ; ' '
0x180018692  mov     rsi, rcx
0x180018695  mov     [rbp+57h+var_1C], 100h
0x18001869b  mov     [rbp+57h+NewAcl], 0
0x1800186a3  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], xmm0
0x1800186a7  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.Trustee.pMultipleTrustee], xmm0
0x1800186ab  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeType], xmm0
0x1800186af  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800186b3  ja      loc_1800189B8
0x1800186b9  xor     r9d, r9d; TokenInformationLength
0x1800186bc  lea     rax, [rbp+57h+TokenInformationLength]
0x1800186c0  xor     r8d, r8d; TokenInformation
0x1800186c3  mov     [rsp+0D0h+ReturnLength], rax; ReturnLength
0x1800186c8  mov     rcx, rdi; TokenHandle
0x1800186cb  lea     edx, [r9+6]; TokenInformationClass
0x1800186cf  call    cs:__imp_GetTokenInformation
0x1800186d6  nop     dword ptr [rax+rax+00h]
0x1800186db  test    eax, eax
0x1800186dd  jnz     loc_18001894C
0x1800186e3  call    cs:__imp_GetLastError
0x1800186ea  nop     dword ptr [rax+rax+00h]
0x1800186ef  mov     ebx, eax
0x1800186f1  cmp     eax, 7Ah ; 'z'
0x1800186f4  jz      short loc_18001872A
0x1800186f6  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x1800186fd  jz      loc_18001898E
0x180018703  test    eax, eax
0x180018705  jle     short loc_18001870F
0x180018707  movzx   eax, ax
0x18001870a  or      eax, 80070000h
0x18001870f  lea     rcx, aFailedToGetSiz; "Failed to get size of default token\n"
0x180018716  mov     r8d, 351h
0x18001871c  mov     [rsp+0D0h+var_A8], rcx
0x180018721  mov     dword ptr [rsp+0D0h+ReturnLength], eax
0x180018725  jmp     loc_180018974
0x18001872a  mov     edx, [rbp+57h+TokenInformationLength]; unsigned int
0x18001872d  lea     rcx, [rbp+57h+var_48]; this
0x180018731  call    ?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180018736  test    al, al
0x180018738  jnz     short loc_18001879D
0x18001873a  call    cs:__imp_GetLastError
0x180018741  nop     dword ptr [rax+rax+00h]
0x180018746  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x18001874d  mov     ebx, eax
0x18001874f  jz      loc_18001898E
0x180018755  mov     ecx, [rbp+57h+TokenInformationLength]
0x180018758  test    eax, eax
0x18001875a  jle     short loc_180018764
0x18001875c  movzx   eax, ax
0x18001875f  or      eax, 80070000h
0x180018764  mov     dword ptr [rsp+0D0h+var_A0], ecx; char
0x180018768  lea     r9, aCsecuritydispe_0; "CSecurityDispenser::AdjustTokenForAdmin"...
0x18001876f  lea     rcx, aFailedToResize_0; "Failed to resize the buffer for default"...
0x180018776  mov     r8d, 36Fh; unsigned int
0x18001877c  mov     [rsp+0D0h+var_A8], rcx; char *
0x180018781  lea     rdx, aServercommonIn_10; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180018788  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18001878f  mov     dword ptr [rsp+0D0h+ReturnLength], eax; dwMessageId
0x180018793  call    PuDbgPrintError
0x180018798  jmp     loc_18001898E
0x18001879d  mov     r8d, [rbp+57h+TokenInformationLength]; Size
0x1800187a1  xor     edx, edx; Val
0x1800187a3  mov     rcx, [rbp+57h+TokenInformation]; void *
0x1800187a7  call    memset_0
0x1800187ac  mov     r9d, [rbp+57h+TokenInformationLength]; TokenInformationLength
0x1800187b0  lea     rax, [rbp+57h+TokenInformationLength]
0x1800187b4  mov     r8, [rbp+57h+TokenInformation]; TokenInformation
0x1800187b8  mov     edx, 6; TokenInformationClass
0x1800187bd  mov     rcx, rdi; TokenHandle
0x1800187c0  mov     [rsp+0D0h+ReturnLength], rax; ReturnLength
0x1800187c5  call    cs:__imp_GetTokenInformation
0x1800187cc  nop     dword ptr [rax+rax+00h]
0x1800187d1  test    eax, eax
0x1800187d3  jnz     short loc_180018817
0x1800187d5  call    cs:__imp_GetLastError
0x1800187dc  nop     dword ptr [rax+rax+00h]
0x1800187e1  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x1800187e8  mov     ebx, eax
0x1800187ea  jz      loc_18001898E
0x1800187f0  test    eax, eax
0x1800187f2  jle     short loc_1800187FC
0x1800187f4  movzx   eax, ax
0x1800187f7  or      eax, 80070000h
0x1800187fc  lea     rcx, aFailedToGetThe; "Failed to get the default token\n"
0x180018803  mov     r8d, 38Ah
0x180018809  mov     [rsp+0D0h+var_A8], rcx
0x18001880e  mov     dword ptr [rsp+0D0h+ReturnLength], eax
0x180018812  jmp     loc_180018974
0x180018817  xorps   xmm0, xmm0
0x18001881a  lea     r8, [rbp+57h+var_80]; void **
0x18001881e  mov     edx, 1Ah; enum WELL_KNOWN_SID_TYPE
0x180018823  mov     rcx, rsi; this
0x180018826  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], xmm0
0x18001882a  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.Trustee.pMultipleTrustee], xmm0
0x18001882e  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeType], xmm0
0x180018832  call    ?GetSID@CSecurityDispenser@@QEAAKW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z; CSecurityDispenser::GetSID(WELL_KNOWN_SID_TYPE,void * *)
0x180018837  mov     ebx, eax
0x180018839  test    eax, eax
0x18001883b  jz      short loc_180018871
0x18001883d  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x180018844  jz      loc_18001898E
0x18001884a  test    eax, eax
0x18001884c  jle     short loc_180018856
0x18001884e  movzx   eax, ax
0x180018851  or      eax, 80070000h
0x180018856  lea     rcx, aGettingAdminSi; "Getting Admin Sid Failed\n"
0x18001885d  mov     r8d, 399h
0x180018863  mov     [rsp+0D0h+var_A8], rcx
0x180018868  mov     dword ptr [rsp+0D0h+ReturnLength], eax
0x18001886c  jmp     loc_180018974
0x180018871  mov     r8, [rbp+57h+TokenInformation]
0x180018875  lea     r9, [rbp+57h+NewAcl]; NewAcl
0x180018879  mov     rax, [rbp+57h+var_80]
0x18001887d  lea     rdx, [rbp+57h+pListOfExplicitEntries]; pListOfExplicitEntries
0x180018881  mov     qword ptr [rbp+57h+pListOfExplicitEntries.grfAccessMode], 1
0x180018889  mov     ecx, 1; cCountOfExplicitEntries
0x18001888e  mov     [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeForm], 0
0x180018895  mov     [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeType], 5
0x18001889c  mov     [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], 10000000h
0x1800188a3  mov     [rbp+57h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x1800188a7  mov     r8, [r8]; OldAcl
0x1800188aa  call    cs:__imp_SetEntriesInAclW
0x1800188b1  nop     dword ptr [rax+rax+00h]
0x1800188b6  mov     ebx, eax
0x1800188b8  test    eax, eax
0x1800188ba  jz      short loc_1800188F0
0x1800188bc  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x1800188c3  jz      loc_18001898E
0x1800188c9  test    eax, eax
0x1800188cb  jle     short loc_1800188D5
0x1800188cd  movzx   eax, ax
0x1800188d0  or      eax, 80070000h
0x1800188d5  lea     rcx, aFailedToSetEnt; "Failed to set entries in token\n"
0x1800188dc  mov     r8d, 3B4h
0x1800188e2  mov     [rsp+0D0h+var_A8], rcx
0x1800188e7  mov     dword ptr [rsp+0D0h+ReturnLength], eax
0x1800188eb  jmp     loc_180018974
0x1800188f0  mov     r9d, 8; TokenInformationLength
0x1800188f6  lea     r8, [rbp+57h+NewAcl]; TokenInformation
0x1800188fa  mov     rcx, rdi; TokenHandle
0x1800188fd  lea     edx, [r9-2]; TokenInformationClass
0x180018901  call    cs:__imp_SetTokenInformation
0x180018908  nop     dword ptr [rax+rax+00h]
0x18001890d  test    eax, eax
0x18001890f  jnz     short loc_18001898E
0x180018911  call    cs:__imp_GetLastError
0x180018918  nop     dword ptr [rax+rax+00h]
0x18001891d  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x180018924  mov     ebx, eax
0x180018926  jz      short loc_18001898E
0x180018928  test    eax, eax
0x18001892a  jle     short loc_180018934
0x18001892c  movzx   eax, ax
0x18001892f  or      eax, 80070000h
0x180018934  lea     rcx, aFailedToResetT; "Failed to reset token's default actl\n"
0x18001893b  mov     r8d, 3C7h
0x180018941  mov     [rsp+0D0h+var_A8], rcx
0x180018946  mov     dword ptr [rsp+0D0h+ReturnLength], eax
0x18001894a  jmp     short loc_180018974
0x18001894c  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x180018953  mov     ebx, 6Eh ; 'n'
0x180018958  jz      short loc_18001898E
0x18001895a  lea     rax, aDidNotGetAnErr; "Did not get an error when we expected t"...
0x180018961  mov     r8d, 360h; unsigned int
0x180018967  mov     [rsp+0D0h+var_A8], rax; char *
0x18001896c  mov     dword ptr [rsp+0D0h+ReturnLength], 8007006Eh; dwMessageId
0x180018974  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18001897b  lea     r9, aCsecuritydispe_0; "CSecurityDispenser::AdjustTokenForAdmin"...
0x180018982  lea     rdx, aServercommonIn_10; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180018989  call    PuDbgPrintError
0x18001898e  mov     rcx, [rbp+57h+NewAcl]; hMem
0x180018992  test    rcx, rcx
0x180018995  jz      short loc_1800189AB
0x180018997  call    cs:__imp_LocalFree
0x18001899e  nop     dword ptr [rax+rax+00h]
0x1800189a3  mov     [rbp+57h+NewAcl], 0
0x1800189ab  lea     rcx, [rbp+57h+var_48]; this
0x1800189af  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800189b4  mov     eax, ebx
0x1800189b6  jmp     short loc_1800189C6
0x1800189b8  lea     rcx, [rbp+57h+var_48]; this
0x1800189bc  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800189c1  mov     eax, 57h ; 'W'
0x1800189c6  mov     rcx, [rbp+57h+var_18]
0x1800189ca  xor     rcx, rsp; StackCookie
0x1800189cd  call    __security_check_cookie
0x1800189d2  mov     rbx, [rsp+0D0h+arg_10]
0x1800189da  add     rsp, 0C0h
0x1800189e1  pop     rdi
0x1800189e2  pop     rsi
0x1800189e3  pop     rbp
0x1800189e4  retn
```
