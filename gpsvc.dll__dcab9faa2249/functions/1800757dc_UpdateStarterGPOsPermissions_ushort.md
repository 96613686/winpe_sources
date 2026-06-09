# UpdateStarterGPOsPermissions(ushort *)

- ea: `0x1800757dc`
- end: `0x180075eb9`
- name: `?UpdateStarterGPOsPermissions@@YAHPEAG@Z`
- size: `1757`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18005ce5c`

## callees

- `0x180003770`
- `0x1800757dc`
- `0x180075ec0`
- `0x18007d320`
- `0x18007de08`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075922`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075954`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075a7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075d36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075d6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075da4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075ddc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075922`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075954`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075a7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075d36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075d6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075da4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075ddc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180075e77`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180075e86`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180075e77`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180075e86`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180075a42`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180075a42`
- `api-ms-win-security-base-l1-1-0!DeleteAce` at `0x180075a73`
- `api-ms-win-security-base-l1-1-0!DeleteAce` at `0x180075a73`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800759fe`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800759fe`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180075900`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180075900`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180075a26`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180075a26`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180075e68`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180075e68`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x18007598f`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x18007598f`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x180075c0a`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x180075c0a`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180075b7b`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180075b7b`

## string_xrefs

- `0x180075ba9`: `UpdateStarterGPOsPermissions : SetEntriesInAcl failed.  Error = 0x%x.`
- `0x180075bdb`: `UpdateStarterGPOsPermissions : SetEntriesInAcl failed.  Error = 0x%x.`
- `0x180075db6`: `UpdateStarterGPOsPermissions: GetSecurityDescriptorDacl failed with 0x%x.`
- `0x180075dee`: `UpdateStarterGPOsPermissions: GetSecurityDescriptorDacl failed with 0x%x.`
- `0x180075c38`: `UpdateStarterGPOsPermissions: SetNamedSecurityInfo failed, 0x%X`
- `0x180075c6a`: `UpdateStarterGPOsPermissions: SetNamedSecurityInfo failed, 0x%X`
- `0x180075d48`: `UpdateStarterGPOsPermissions: GetAce failed with 0x%x.`
- `0x180075d80`: `UpdateStarterGPOsPermissions: GetAce failed with 0x%x.`
- `0x180075e17`: `UpdateStarterGPOsPermissions: GetNamedSecurityInfo Failed with error - 0x%x .`
- `0x180075e4c`: `UpdateStarterGPOsPermissions: GetNamedSecurityInfo Failed with error - 0x%x .`
- `0x180075899`: `UpdateStarterGPOsPermissions: StarterGPOs Path %s.`
- `0x1800758c0`: `UpdateStarterGPOsPermissions: StarterGPOs Path %s.`
- `0x180075928`: `UpdateStarterGPOsPermissions: Failed to initialize sid.  Error = %d`
- `0x18007595a`: `UpdateStarterGPOsPermissions: Failed to initialize sid.  Error = %d`
- `0x1800759b8`: `UpdateStarterGPOsPermissions: Path- %s .`
- `0x1800759df`: `UpdateStarterGPOsPermissions: Path- %s .`
- `0x180075aaa`: `UpdateStarterGPOsPermissions: DeleteAce for %d failed with 0x%x.`
- `0x180075ae1`: `UpdateStarterGPOsPermissions: DeleteAce for %d failed with 0x%x.`
- `0x180075b0c`: `UpdateStarterGPOsPermissions: Proceeding to update permissions.`
- `0x180075b2f`: `UpdateStarterGPOsPermissions: Proceeding to update permissions.`
- `0x180075cdc`: `UpdateStarterGPOsPermissions: Right permissions are already set. Skipping.`
- `0x180075d0a`: `UpdateStarterGPOsPermissions: Right permissions are already set. Skipping.`
- `0x180075c8a`: `UpdateStarterGPOsPermissions: SetNamedSecurityInfo Success`
- `0x180075cad`: `UpdateStarterGPOsPermissions: SetNamedSecurityInfo Success`

## pseudocode

```c
__int64 __fastcall UpdateStarterGPOsPermissions(unsigned __int16 *a1)
{
  unsigned int v2; // edi
  void (*v3)(unsigned int, const unsigned __int16 *, ...); // rbx
  signed int LastError; // eax
  const wchar_t *v5; // rdx
  DWORD v6; // eax
  signed int NamedSecurityInfoW; // eax
  DWORD i; // ebx
  DWORD v9; // eax
  void (*v10)(unsigned int, const unsigned __int16 *, ...); // r9
  const wchar_t *v11; // rdx
  signed int v12; // eax
  signed int v13; // eax
  PACL pDacl; // [rsp+60h] [rbp-A0h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+68h] [rbp-98h] BYREF
  WINBOOL bDaclPresent; // [rsp+6Ch] [rbp-94h] BYREF
  LPVOID pAce; // [rsp+70h] [rbp-90h] BYREF
  PSID pSid2; // [rsp+78h] [rbp-88h] BYREF
  PACL NewAcl; // [rsp+80h] [rbp-80h] BYREF
  PSECURITY_DESCRIPTOR ppSecurityDescriptor; // [rsp+88h] [rbp-78h] BYREF
  struct _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+90h] [rbp-70h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR pObjectName[264]; // [rsp+D0h] [rbp-30h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  ppSecurityDescriptor = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  pSid2 = 0;
  pDacl = 0;
  pAce = 0;
  bDaclPresent = 0;
  v2 = 0;
  bDaclDefaulted = 0;
  memset(&pListOfExplicitEntries, 0, sizeof(pListOfExplicitEntries));
  NewAcl = 0;
  memset_0(pObjectName, 0, 0x208u);
  StringCchPrintfW(pObjectName, 0x104u, L"\\\\%s\\SYSVOL\\%s\\StarterGPOs", a1, a1);
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(2u, L"UpdateStarterGPOsPermissions: StarterGPOs Path %s.", pObjectName);
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(2u, L"UpdateStarterGPOsPermissions: StarterGPOs Path %s.", pObjectName);
    }
  }
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0xBu, 0, 0, 0, 0, 0, 0, 0, &pSid2) )
  {
    NamedSecurityInfoW = GetNamedSecurityInfoW(pObjectName, SE_FILE_OBJECT, 4u, 0, 0, 0, 0, &ppSecurityDescriptor);
    if ( NamedSecurityInfoW )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        v10 = g_lpDebugMsg;
        if ( g_lpDebugMsg )
        {
          if ( NamedSecurityInfoW > 0 )
            NamedSecurityInfoW = (unsigned __int16)NamedSecurityInfoW | 0x80070000;
          v11 = L"UpdateStarterGPOsPermissions: GetNamedSecurityInfo Failed with error - 0x%x .";
LABEL_105:
          v10(2u, v11, (unsigned int)NamedSecurityInfoW);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          if ( NamedSecurityInfoW > 0 )
            NamedSecurityInfoW = (unsigned __int16)NamedSecurityInfoW | 0x80070000;
          RedirectDebugMsg(
            2u,
            L"UpdateStarterGPOsPermissions: GetNamedSecurityInfo Failed with error - 0x%x .",
            (unsigned int)NamedSecurityInfoW);
        }
      }
    }
    else
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(4u, L"UpdateStarterGPOsPermissions: Path- %s .", pObjectName);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(4u, L"UpdateStarterGPOsPermissions: Path- %s .", pObjectName);
        }
      }
      if ( GetSecurityDescriptorDacl(ppSecurityDescriptor, &bDaclPresent, &pDacl, &bDaclDefaulted) )
      {
        for ( i = 0; i < pDacl->AceCount; ++i )
        {
          if ( !GetAce(pDacl, i, &pAce) )
          {
            if ( !*(_DWORD *)&g_dwDebugLevel )
              break;
            v3 = g_lpDebugMsg;
            if ( g_lpDebugMsg )
            {
              LastError = GetLastError();
              if ( LastError > 0 )
                LastError = (unsigned __int16)LastError | 0x80070000;
              v5 = L"UpdateStarterGPOsPermissions: GetAce failed with 0x%x.";
              goto LABEL_11;
            }
            if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              v12 = GetLastError();
              if ( v12 > 0 )
                v12 = (unsigned __int16)v12 | 0x80070000;
              RedirectDebugMsg(2u, L"UpdateStarterGPOsPermissions: GetAce failed with 0x%x.", (unsigned int)v12);
            }
            break;
          }
          if ( EqualSid((char *)pAce + 8, pSid2) && (*((_BYTE *)pAce + 1) & 0xB) == 0xB )
          {
            if ( *((_DWORD *)pAce + 1) == -1610612736 )
            {
              if ( *(_DWORD *)&g_dwDebugLevel )
              {
                if ( g_lpDebugMsg )
                {
                  g_lpDebugMsg(4u, L"UpdateStarterGPOsPermissions: Right permissions are already set. Skipping.");
                }
                else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                {
                  RedirectDebugMsg(4u, L"UpdateStarterGPOsPermissions: Right permissions are already set. Skipping.");
                }
              }
            }
            else
            {
              if ( !DeleteAce(pDacl, i) )
              {
                v9 = GetLastError();
                if ( (int)v9 > 0 )
                  v9 = (unsigned __int16)v9 | 0x80070000;
                if ( *(_DWORD *)&g_dwDebugLevel )
                {
                  if ( g_lpDebugMsg )
                  {
                    g_lpDebugMsg(4u, L"UpdateStarterGPOsPermissions: DeleteAce for %d failed with 0x%x.", i, v9);
                  }
                  else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                  {
                    RedirectDebugMsg(4u, L"UpdateStarterGPOsPermissions: DeleteAce for %d failed with 0x%x.", i, v9);
                  }
                }
                break;
              }
              if ( *(_DWORD *)&g_dwDebugLevel )
              {
                if ( g_lpDebugMsg )
                {
                  g_lpDebugMsg(4u, L"UpdateStarterGPOsPermissions: Proceeding to update permissions.");
                }
                else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                {
                  RedirectDebugMsg(4u, L"UpdateStarterGPOsPermissions: Proceeding to update permissions.");
                }
              }
              pListOfExplicitEntries.Trustee.ptstrName = L"Authenticated Users";
              *(_QWORD *)&pListOfExplicitEntries.grfInheritance = 3;
              *(_QWORD *)&pListOfExplicitEntries.Trustee.TrusteeType = 2;
              pListOfExplicitEntries.grfAccessPermissions = -1610612736;
              pListOfExplicitEntries.grfAccessMode = GRANT_ACCESS;
              pListOfExplicitEntries.Trustee.pMultipleTrustee = 0;
              pListOfExplicitEntries.Trustee.MultipleTrusteeOperation = NO_MULTIPLE_TRUSTEE;
              pListOfExplicitEntries.Trustee.TrusteeForm = TRUSTEE_IS_NAME;
              NamedSecurityInfoW = SetEntriesInAclW(1u, &pListOfExplicitEntries, pDacl, &NewAcl);
              if ( NamedSecurityInfoW )
              {
                if ( !*(_DWORD *)&g_dwDebugLevel )
                  break;
                v10 = g_lpDebugMsg;
                if ( g_lpDebugMsg )
                {
                  if ( NamedSecurityInfoW > 0 )
                    NamedSecurityInfoW = (unsigned __int16)NamedSecurityInfoW | 0x80070000;
                  v11 = L"UpdateStarterGPOsPermissions : SetEntriesInAcl failed.  Error = 0x%x.";
                  goto LABEL_105;
                }
                if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                {
                  if ( NamedSecurityInfoW > 0 )
                    NamedSecurityInfoW = (unsigned __int16)NamedSecurityInfoW | 0x80070000;
                  RedirectDebugMsg(
                    2u,
                    L"UpdateStarterGPOsPermissions : SetEntriesInAcl failed.  Error = 0x%x.",
                    (unsigned int)NamedSecurityInfoW);
                }
              }
              else
              {
                NamedSecurityInfoW = SetNamedSecurityInfoW(pObjectName, SE_FILE_OBJECT, 0x80000004, 0, 0, NewAcl, 0);
                if ( NamedSecurityInfoW )
                {
                  if ( !*(_DWORD *)&g_dwDebugLevel )
                    break;
                  v10 = g_lpDebugMsg;
                  if ( g_lpDebugMsg )
                  {
                    if ( NamedSecurityInfoW > 0 )
                      NamedSecurityInfoW = (unsigned __int16)NamedSecurityInfoW | 0x80070000;
                    v11 = L"UpdateStarterGPOsPermissions: SetNamedSecurityInfo failed, 0x%X";
                    goto LABEL_105;
                  }
                  if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                  {
                    if ( NamedSecurityInfoW > 0 )
                      NamedSecurityInfoW = (unsigned __int16)NamedSecurityInfoW | 0x80070000;
                    RedirectDebugMsg(
                      2u,
                      L"UpdateStarterGPOsPermissions: SetNamedSecurityInfo failed, 0x%X",
                      (unsigned int)NamedSecurityInfoW);
                  }
                }
                else
                {
                  if ( *(_DWORD *)&g_dwDebugLevel )
                  {
                    if ( g_lpDebugMsg )
                    {
                      g_lpDebugMsg(4u, L"UpdateStarterGPOsPermissions: SetNamedSecurityInfo Success");
                    }
                    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                    {
                      RedirectDebugMsg(4u, L"UpdateStarterGPOsPermissions: SetNamedSecurityInfo Success");
                    }
                  }
                  v2 = 1;
                }
              }
            }
            break;
          }
        }
      }
      else if ( *(_DWORD *)&g_dwDebugLevel )
      {
        v3 = g_lpDebugMsg;
        if ( g_lpDebugMsg )
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          v5 = L"UpdateStarterGPOsPermissions: GetSecurityDescriptorDacl failed with 0x%x.";
          goto LABEL_11;
        }
        if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          v13 = GetLastError();
          if ( v13 > 0 )
            v13 = (unsigned __int16)v13 | 0x80070000;
          RedirectDebugMsg(
            2u,
            L"UpdateStarterGPOsPermissions: GetSecurityDescriptorDacl failed with 0x%x.",
            (unsigned int)v13);
        }
      }
    }
  }
  else
  {
    if ( !*(_DWORD *)&g_dwDebugLevel )
      goto LABEL_112;
    v3 = g_lpDebugMsg;
    if ( g_lpDebugMsg )
    {
      LastError = GetLastError();
      v5 = L"UpdateStarterGPOsPermissions: Failed to initialize sid.  Error = %d";
LABEL_11:
      v3(2u, v5, (unsigned int)LastError);
      goto LABEL_112;
    }
    if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      v6 = GetLastError();
      RedirectDebugMsg(2u, L"UpdateStarterGPOsPermissions: Failed to initialize sid.  Error = %d", v6);
    }
  }
LABEL_112:
  if ( pSid2 )
    FreeSid(pSid2);
  if ( NewAcl )
    LocalFree(NewAcl);
  if ( ppSecurityDescriptor )
    LocalFree(ppSecurityDescriptor);
  return v2;
}

```

## disassembly

```asm
0x1800757dc  mov     [rsp-8+arg_8], rbx
0x1800757e1  mov     [rsp-8+arg_10], rsi
0x1800757e6  push    rbp
0x1800757e7  push    rdi
0x1800757e8  push    r12
0x1800757ea  push    r14
0x1800757ec  push    r15
0x1800757ee  lea     rbp, [rsp-1F0h]
0x1800757f6  sub     rsp, 2F0h
0x1800757fd  mov     rax, cs:__security_cookie
0x180075804  xor     rax, rsp
0x180075807  mov     [rbp+210h+var_30], rax
0x18007580e  xor     esi, esi
0x180075810  mov     word ptr [rbp+210h+pIdentifierAuthority.Value+4], 500h
0x180075816  xorps   xmm0, xmm0
0x180075819  mov     [rbp+210h+ppSecurityDescriptor], rsi
0x18007581d  mov     rbx, rcx
0x180075820  mov     dword ptr [rbp+210h+pIdentifierAuthority.Value], esi
0x180075823  lea     rcx, [rbp+210h+pObjectName]; void *
0x180075827  mov     [rsp+310h+pSid2], rsi
0x18007582c  xor     edx, edx; Val
0x18007582e  mov     [rsp+310h+pDacl], rsi
0x180075833  mov     r8d, 208h; Size
0x180075839  mov     [rsp+310h+pAce], rsi
0x18007583e  mov     [rsp+310h+bDaclPresent], esi
0x180075842  mov     edi, esi
0x180075844  mov     [rsp+310h+bDaclDefaulted], esi
0x180075848  movups  xmmword ptr [rbp+210h+pListOfExplicitEntries.grfAccessPermissions], xmm0
0x18007584c  mov     [rbp+210h+NewAcl], rsi
0x180075850  movups  xmmword ptr [rbp+210h+pListOfExplicitEntries.Trustee.pMultipleTrustee], xmm0
0x180075854  movups  xmmword ptr [rbp+210h+pListOfExplicitEntries.Trustee.TrusteeType], xmm0
0x180075858  call    memset_0
0x18007585d  mov     r9, rbx
0x180075860  mov     qword ptr [rsp+310h+nSubAuthority2], rbx
0x180075865  lea     r8, aSSysvolSStarte; "\\\\%s\\SYSVOL\\%s\\StarterGPOs"
0x18007586c  mov     edx, 104h; unsigned __int64
0x180075871  lea     rcx, [rbp+210h+pObjectName]; unsigned __int16 *
0x180075875  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18007587a  cmp     cs:?g_dwDebugLevel@@3KA, esi; ulong g_dwDebugLevel
0x180075880  lea     r15d, [rsi+2]
0x180075884  jz      short loc_1800758CC
0x180075886  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18007588d  test    rax, rax
0x180075890  jz      short loc_1800758A7
0x180075892  lea     r8, [rbp+210h+pObjectName]
0x180075896  mov     ecx, r15d
0x180075899  lea     rdx, aUpdatestarterg_1; "UpdateStarterGPOsPermissions: StarterGP"...
0x1800758a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800758a5  jmp     short loc_1800758CC
0x1800758a7  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rsi; void * g_lpDebugMsgContextInstance
0x1800758ae  jz      short loc_1800758CC
0x1800758b0  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rsi; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800758b7  jz      short loc_1800758CC
0x1800758b9  lea     r8, [rbp+210h+pObjectName]
0x1800758bd  mov     ecx, r15d; unsigned int
0x1800758c0  lea     rdx, aUpdatestarterg_1; "UpdateStarterGPOsPermissions: StarterGP"...
0x1800758c7  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800758cc  xor     r9d, r9d; nSubAuthority1
0x1800758cf  lea     rax, [rsp+310h+pSid2]
0x1800758d4  mov     [rsp+310h+pSid], rax; pSid
0x1800758d9  lea     rcx, [rbp+210h+pIdentifierAuthority]; pIdentifierAuthority
0x1800758dd  mov     [rsp+310h+nSubAuthority7], esi; nSubAuthority7
0x1800758e1  mov     [rsp+310h+nSubAuthority6], esi; nSubAuthority6
0x1800758e5  mov     [rsp+310h+nSubAuthority5], esi; nSubAuthority5
0x1800758e9  lea     r12d, [r9+1]
0x1800758ed  mov     [rsp+310h+nSubAuthority4], esi; nSubAuthority4
0x1800758f1  lea     r8d, [r9+0Bh]; nSubAuthority0
0x1800758f5  mov     [rsp+310h+nSubAuthority3], esi; nSubAuthority3
0x1800758f9  mov     dl, r12b; nSubAuthorityCount
0x1800758fc  mov     [rsp+310h+nSubAuthority2], esi; nSubAuthority2
0x180075900  call    cs:__imp_AllocateAndInitializeSid
0x180075906  test    eax, eax
0x180075908  jnz     short loc_180075966
0x18007590a  cmp     cs:?g_dwDebugLevel@@3KA, esi; ulong g_dwDebugLevel
0x180075910  jz      loc_180075E5E
0x180075916  mov     rbx, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18007591d  test    rbx, rbx
0x180075920  jz      short loc_18007593A
0x180075922  call    cs:__imp_GetLastError
0x180075928  lea     rdx, aUpdatestarterg_9; "UpdateStarterGPOsPermissions: Failed to"...
0x18007592f  mov     r8d, eax
0x180075932  mov     rax, rbx
0x180075935  jmp     loc_180075E24
0x18007593a  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rsi; void * g_lpDebugMsgContextInstance
0x180075941  jz      loc_180075E5E
0x180075947  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rsi; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18007594e  jz      loc_180075E5E
0x180075954  call    cs:__imp_GetLastError
0x18007595a  lea     rdx, aUpdatestarterg_9; "UpdateStarterGPOsPermissions: Failed to"...
0x180075961  jmp     loc_180075E53
0x180075966  xor     r9d, r9d; ppsidOwner
0x180075969  lea     rax, [rbp+210h+ppSecurityDescriptor]
0x18007596d  mov     qword ptr [rsp+310h+nSubAuthority5], rax; ppSecurityDescriptor
0x180075972  lea     rcx, [rbp+210h+pObjectName]; pObjectName
0x180075976  mov     qword ptr [rsp+310h+nSubAuthority4], rsi; ppSacl
0x18007597b  mov     edx, r12d; ObjectType
0x18007597e  mov     qword ptr [rsp+310h+nSubAuthority3], rsi; ppDacl
0x180075983  lea     r14d, [r9+4]
0x180075987  mov     qword ptr [rsp+310h+nSubAuthority2], rsi; ppsidGroup
0x18007598c  mov     r8d, r14d; SecurityInfo
0x18007598f  call    cs:__imp_GetNamedSecurityInfoW
0x180075995  test    eax, eax
0x180075997  jnz     loc_180075DF7
0x18007599d  cmp     cs:?g_dwDebugLevel@@3KA, esi; ulong g_dwDebugLevel
0x1800759a3  jz      short loc_1800759EB
0x1800759a5  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800759ac  test    rax, rax
0x1800759af  jz      short loc_1800759C6
0x1800759b1  lea     r8, [rbp+210h+pObjectName]
0x1800759b5  mov     ecx, r14d
0x1800759b8  lea     rdx, aUpdatestarterg_5; "UpdateStarterGPOsPermissions: Path- %s "...
0x1800759bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800759c4  jmp     short loc_1800759EB
0x1800759c6  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rsi; void * g_lpDebugMsgContextInstance
0x1800759cd  jz      short loc_1800759EB
0x1800759cf  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rsi; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800759d6  jz      short loc_1800759EB
0x1800759d8  lea     r8, [rbp+210h+pObjectName]
0x1800759dc  mov     ecx, r14d; unsigned int
0x1800759df  lea     rdx, aUpdatestarterg_5; "UpdateStarterGPOsPermissions: Path- %s "...
0x1800759e6  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800759eb  mov     rcx, [rbp+210h+ppSecurityDescriptor]; pSecurityDescriptor
0x1800759ef  lea     r9, [rsp+310h+bDaclDefaulted]; lpbDaclDefaulted
0x1800759f4  lea     r8, [rsp+310h+pDacl]; pDacl
0x1800759f9  lea     rdx, [rsp+310h+bDaclPresent]; lpbDaclPresent
0x1800759fe  call    cs:__imp_GetSecurityDescriptorDacl
0x180075a04  test    eax, eax
0x180075a06  jz      loc_180075D8C
0x180075a0c  mov     ebx, esi
0x180075a0e  mov     rcx, [rsp+310h+pDacl]; pAcl
0x180075a13  movzx   eax, word ptr [rcx+4]
0x180075a17  cmp     ebx, eax
0x180075a19  jnb     loc_180075E5E
0x180075a1f  lea     r8, [rsp+310h+pAce]; pAce
0x180075a24  mov     edx, ebx; dwAceIndex
0x180075a26  call    cs:__imp_GetAce
0x180075a2c  test    eax, eax
0x180075a2e  jz      loc_180075D1E
0x180075a34  mov     rcx, [rsp+310h+pAce]
0x180075a39  mov     rdx, [rsp+310h+pSid2]; pSid2
0x180075a3e  add     rcx, 8; pSid1
0x180075a42  call    cs:__imp_EqualSid
0x180075a48  test    eax, eax
0x180075a4a  jz      short loc_180075A5A
0x180075a4c  mov     rcx, [rsp+310h+pAce]
0x180075a51  mov     al, [rcx+1]
0x180075a54  and     al, 0Bh
0x180075a56  cmp     al, 0Bh
0x180075a58  jz      short loc_180075A5F
0x180075a5a  add     ebx, r12d
0x180075a5d  jmp     short loc_180075A0E
0x180075a5f  cmp     dword ptr [rcx+4], 0A0000000h
0x180075a66  jz      loc_180075CC4
0x180075a6c  mov     rcx, [rsp+310h+pDacl]; pAcl
0x180075a71  mov     edx, ebx; dwAceIndex
0x180075a73  call    cs:__imp_DeleteAce
0x180075a79  test    eax, eax
0x180075a7b  jnz     short loc_180075AF8
0x180075a7d  call    cs:__imp_GetLastError
0x180075a83  test    eax, eax
0x180075a85  jle     short loc_180075A8F
0x180075a87  movzx   eax, ax
0x180075a8a  or      eax, 80070000h
0x180075a8f  cmp     cs:?g_dwDebugLevel@@3KA, esi; ulong g_dwDebugLevel
0x180075a95  jz      loc_180075E5E
0x180075a9b  mov     r10, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180075aa2  test    r10, r10
0x180075aa5  jz      short loc_180075AC4
0x180075aa7  mov     r9d, eax
0x180075aaa  lea     rdx, aUpdatestarterg_10; "UpdateStarterGPOsPermissions: DeleteAce"...
0x180075ab1  mov     rax, r10
0x180075ab4  mov     r8d, ebx
0x180075ab7  mov     ecx, r14d
0x180075aba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075abf  jmp     loc_180075E5E
0x180075ac4  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rsi; void * g_lpDebugMsgContextInstance
0x180075acb  jz      loc_180075E5E
0x180075ad1  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rsi; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180075ad8  jz      loc_180075E5E
0x180075ade  mov     r9d, eax
0x180075ae1  lea     rdx, aUpdatestarterg_10; "UpdateStarterGPOsPermissions: DeleteAce"...
0x180075ae8  mov     r8d, ebx
0x180075aeb  mov     ecx, r14d; unsigned int
0x180075aee  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180075af3  jmp     loc_180075E5E
0x180075af8  cmp     cs:?g_dwDebugLevel@@3KA, esi; ulong g_dwDebugLevel
0x180075afe  jz      short loc_180075B3E
0x180075b00  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180075b07  test    rax, rax
0x180075b0a  jz      short loc_180075B1D
0x180075b0c  lea     rdx, aUpdatestarterg_3; "UpdateStarterGPOsPermissions: Proceedin"...
0x180075b13  mov     ecx, r14d
0x180075b16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075b1b  jmp     short loc_180075B3E
0x180075b1d  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rsi; void * g_lpDebugMsgContextInstance
0x180075b24  jz      short loc_180075B3E
0x180075b26  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rsi; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180075b2d  jz      short loc_180075B3E
0x180075b2f  lea     rdx, aUpdatestarterg_3; "UpdateStarterGPOsPermissions: Proceedin"...
0x180075b36  mov     ecx, r14d; unsigned int
0x180075b39  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180075b3e  mov     r8, [rsp+310h+pDacl]; OldAcl
0x180075b43  lea     rax, aAuthenticatedU; "Authenticated Users"
0x180075b4a  lea     r9, [rbp+210h+NewAcl]; NewAcl
0x180075b4e  mov     [rbp+210h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x180075b52  lea     rdx, [rbp+210h+pListOfExplicitEntries]; pListOfExplicitEntries
0x180075b56  mov     qword ptr [rbp+210h+pListOfExplicitEntries.grfInheritance], 3
0x180075b5e  mov     ecx, r12d; cCountOfExplicitEntries
0x180075b61  mov     qword ptr [rbp+210h+pListOfExplicitEntries.Trustee.TrusteeType], r15
0x180075b65  mov     [rbp+210h+pListOfExplicitEntries.grfAccessPermissions], 0A0000000h
0x180075b6c  mov     [rbp+210h+pListOfExplicitEntries.grfAccessMode], r12d
0x180075b70  mov     [rbp+210h+pListOfExplicitEntries.Trustee.pMultipleTrustee], rsi
0x180075b74  mov     [rbp+210h+pListOfExplicitEntries.Trustee.MultipleTrusteeOperation], esi
0x180075b77  mov     [rbp+210h+pListOfExplicitEntries.Trustee.TrusteeForm], r12d
0x180075b7b  call    cs:__imp_SetEntriesInAclW
0x180075b81  test    eax, eax
0x180075b83  jz      short loc_180075BE7
0x180075b85  cmp     cs:?g_dwDebugLevel@@3KA, esi; ulong g_dwDebugLevel
0x180075b8b  jz      loc_180075E5E
0x180075b91  mov     r9, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180075b98  test    r9, r9
0x180075b9b  jz      short loc_180075BB5
0x180075b9d  test    eax, eax
0x180075b9f  jle     short loc_180075BA9
0x180075ba1  movzx   eax, ax
0x180075ba4  or      eax, 80070000h
0x180075ba9  lea     rdx, aUpdatestarterg; "UpdateStarterGPOsPermissions : SetEntri"...
0x180075bb0  jmp     loc_180075E1E
0x180075bb5  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rsi; void * g_lpDebugMsgContextInstance
0x180075bbc  jz      loc_180075E5E
0x180075bc2  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rsi; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180075bc9  jz      loc_180075E5E
0x180075bcf  test    eax, eax
0x180075bd1  jle     short loc_180075BDB
0x180075bd3  movzx   eax, ax
0x180075bd6  or      eax, 80070000h
0x180075bdb  lea     rdx, aUpdatestarterg; "UpdateStarterGPOsPermissions : SetEntri"...
0x180075be2  jmp     loc_180075E53
0x180075be7  mov     rax, [rbp+210h+NewAcl]
0x180075beb  lea     rcx, [rbp+210h+pObjectName]; pObjectName
0x180075bef  mov     qword ptr [rsp+310h+nSubAuthority4], rsi; pSacl
0x180075bf4  xor     r9d, r9d; psidOwner
0x180075bf7  mov     qword ptr [rsp+310h+nSubAuthority3], rax; pDacl
0x180075bfc  mov     r8d, 80000004h; SecurityInfo
0x180075c02  mov     edx, r12d; ObjectType
0x180075c05  mov     qword ptr [rsp+310h+nSubAuthority2], rsi; psidGroup
0x180075c0a  call    cs:__imp_SetNamedSecurityInfoW
0x180075c10  test    eax, eax
0x180075c12  jz      short loc_180075C76
0x180075c14  cmp     cs:?g_dwDebugLevel@@3KA, esi; ulong g_dwDebugLevel
0x180075c1a  jz      loc_180075E5E
0x180075c20  mov     r9, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180075c27  test    r9, r9
0x180075c2a  jz      short loc_180075C44
0x180075c2c  test    eax, eax
0x180075c2e  jle     short loc_180075C38
0x180075c30  movzx   eax, ax
0x180075c33  or      eax, 80070000h
0x180075c38  lea     rdx, aUpdatestarterg_7; "UpdateStarterGPOsPermissions: SetNamedS"...
0x180075c3f  jmp     loc_180075E1E
0x180075c44  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rsi; void * g_lpDebugMsgContextInstance
0x180075c4b  jz      loc_180075E5E
0x180075c51  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rsi; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180075c58  jz      loc_180075E5E
0x180075c5e  test    eax, eax
0x180075c60  jle     short loc_180075C6A
0x180075c62  movzx   eax, ax
0x180075c65  or      eax, 80070000h
0x180075c6a  lea     rdx, aUpdatestarterg_7; "UpdateStarterGPOsPermissions: SetNamedS"...
0x180075c71  jmp     loc_180075E53
0x180075c76  cmp     cs:?g_dwDebugLevel@@3KA, esi; ulong g_dwDebugLevel
0x180075c7c  jz      short loc_180075CBC
0x180075c7e  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180075c85  test    rax, rax
0x180075c88  jz      short loc_180075C9B
0x180075c8a  lea     rdx, aUpdatestarterg_2; "UpdateStarterGPOsPermissions: SetNamedS"...
0x180075c91  mov     ecx, r14d
0x180075c94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075c99  jmp     short loc_180075CBC
0x180075c9b  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rsi; void * g_lpDebugMsgContextInstance
0x180075ca2  jz      short loc_180075CBC
0x180075ca4  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rsi; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180075cab  jz      short loc_180075CBC
0x180075cad  lea     rdx, aUpdatestarterg_2; "UpdateStarterGPOsPermissions: SetNamedS"...
0x180075cb4  mov     ecx, r14d; unsigned int
0x180075cb7  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180075cbc  mov     edi, r12d
0x180075cbf  jmp     loc_180075E5E
0x180075cc4  cmp     cs:?g_dwDebugLevel@@3KA, esi; ulong g_dwDebugLevel
0x180075cca  jz      loc_180075E5E
0x180075cd0  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180075cd7  test    rax, rax
0x180075cda  jz      short loc_180075CF0
0x180075cdc  lea     rdx, aUpdatestarterg_6; "UpdateStarterGPOsPermissions: Right per"...
0x180075ce3  mov     ecx, r14d
0x180075ce6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075ceb  jmp     loc_180075E5E
0x180075cf0  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rsi; void * g_lpDebugMsgContextInstance
0x180075cf7  jz      loc_180075E5E
0x180075cfd  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rsi; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
  ... truncated ...
```
