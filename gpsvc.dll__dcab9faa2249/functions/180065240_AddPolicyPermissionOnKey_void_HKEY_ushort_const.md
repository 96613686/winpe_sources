# AddPolicyPermissionOnKey(void *,HKEY__ *,ushort const *)

- ea: `0x180065240`
- end: `0x180065920`
- name: `?AddPolicyPermissionOnKey@@YAKPEAXPEAUHKEY__@@PEBG@Z`
- size: `1760`
- prototype: `__int64 __fastcall(void *, HKEY hKey, LPCWSTR lpSubKey)`
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180053870`
- `0x18009fc00`
- `0x1800b5110`

## callees

- `0x180022bd4`
- `0x1800336a0`
- `0x180053510`
- `0x180065240`
- `0x180066284`
- `0x180075ec0`
- `0x18007d320`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800653ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800654e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006558e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065675`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800657a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006580d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800653ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800654e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006558e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065675`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800657a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006580d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180065573`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180065573`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800658df`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800658f1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800658df`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800658f1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180065459`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180065459`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x180065558`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x1800655ff`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x180065558`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x1800655ff`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x180065863`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x180065863`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180065798`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180065798`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18006566b`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18006566b`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180065803`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180065803`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800653a4`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800653a4`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800658c5`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800658c5`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18006573a`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18006573a`

## string_xrefs

- `0x1800657c3`: `MakeRegKeySecure: Failed to initialize security descriptor.  Error = %d`
- `0x1800657e9`: `MakeRegKeySecure: Failed to initialize security descriptor.  Error = %d`
- `0x18006582e`: `MakeRegKeySecure: Failed to set security descriptor dacl.  Error = %d`
- `0x18006584c`: `MakeRegKeySecure: Failed to set security descriptor dacl.  Error = %d`
- `0x1800655af`: `ResetRegKeySecurity: Failed to allocate memory`
- `0x1800655dd`: `ResetRegKeySecurity: Failed to allocate memory`
- `0x180065624`: `ResetRegKeySecurity: Failed to query key security with %d`
- `0x18006564d`: `ResetRegKeySecurity: Failed to query key security with %d`
- `0x1800653cf`: `AddPolicyPermissionOnKey: Failed to initialize system sid.  Error = %d`
- `0x180065400`: `AddPolicyPermissionOnKey: Failed to initialize system sid.  Error = %d`
- `0x18006548b`: `AddPolicyPermissionOnKey: Failed to open reg key <%s>.  Error = %d. Setting default permissions`
- `0x1800654b7`: `AddPolicyPermissionOnKey: Failed to open reg key <%s>.  Error = %d. Setting default permissions`
- `0x180065696`: `ResetRegKeySecurity: Failed to get dacl with %d`
- `0x1800656b9`: `ResetRegKeySecurity: Failed to get dacl with %d`
- `0x1800656eb`: `ResetRegKeySecurity: RegGetKeySecurity on key <%s>. error %d. size %d`
- `0x180065716`: `ResetRegKeySecurity: RegGetKeySecurity on key <%s>. error %d. size %d`
- `0x18006575f`: `AddPolicyPermissionOnKey: Failed to set acl entry.  Error = %d`
- `0x180065785`: `AddPolicyPermissionOnKey: Failed to set acl entry.  Error = %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall AddPolicyPermissionOnKey(void *a1, HKEY hKey, LPCWSTR lpSubKey)
{
  PSECURITY_DESCRIPTOR v6; // rbx
  unsigned int v7; // eax
  DWORD LastError; // edi
  void (*v9)(unsigned int, const unsigned __int16 *, ...); // rax
  const wchar_t *v10; // rdx
  __int64 v11; // rcx
  const unsigned __int16 *v12; // rdx
  unsigned int v13; // ecx
  unsigned int v14; // eax
  void (*v15)(unsigned int, const unsigned __int16 *, ...); // rax
  const wchar_t *v16; // rdx
  __int64 KeySecurity; // r9
  HLOCAL v18; // rax
  DWORD nSubAuthority2[2]; // [rsp+20h] [rbp-B9h]
  DWORD cbSecurityDescriptor; // [rsp+60h] [rbp-79h] BYREF
  WINBOOL bDaclPresent; // [rsp+64h] [rbp-75h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp-71h] BYREF
  PACL NewAcl; // [rsp+70h] [rbp-69h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+78h] [rbp-61h] BYREF
  PACL pDacl; // [rsp+80h] [rbp-59h] BYREF
  PSID pSid; // [rsp+88h] [rbp-51h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+90h] [rbp-49h] BYREF
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+98h] [rbp-41h] BYREF
  _OWORD v30[2]; // [rsp+C8h] [rbp-11h] BYREF
  __int64 v31; // [rsp+E8h] [rbp+Fh]
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+F0h] [rbp+17h] BYREF

  v6 = 0;
  pSecurityDescriptor = 0;
  pDacl = 0;
  NewAcl = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  pSid = 0;
  phkResult = 0;
  memset(&pListOfExplicitEntries, 0, sizeof(pListOfExplicitEntries));
  bDaclPresent = 0;
  bDaclDefaulted = 0;
  cbSecurityDescriptor = 0;
  memset(v30, 0, sizeof(v30));
  v31 = 0;
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"AddPolicyPermissionOnKey: Setting permission on reg key on <%s>.");
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(4u, L"AddPolicyPermissionOnKey: Setting permission on reg key on <%s>.");
    }
  }
  v7 = SetPolicyOwnerOnKey(hKey, lpSubKey);
  if ( v7 && *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(2u, L"AddPolicyPermissionOnKey: Failed to set owner reg key on <%s> with error 0x%x.", lpSubKey, v7);
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(
        2u,
        L"AddPolicyPermissionOnKey: Failed to set owner reg key on <%s> with error 0x%x.",
        lpSubKey,
        v7);
    }
  }
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &pSid) )
  {
    *(_QWORD *)&pListOfExplicitEntries.grfInheritance = 3;
    pListOfExplicitEntries.grfAccessMode = GRANT_ACCESS;
    pListOfExplicitEntries.grfAccessPermissions = 983103;
    memset(&pListOfExplicitEntries.Trustee, 0, 24);
    pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)pSid;
    v14 = RegOpenKeyExW(hKey, lpSubKey, 0, 0x60019u, &phkResult);
    if ( v14 )
    {
      if ( v14 != 2 )
      {
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(
              2u,
              L"AddPolicyPermissionOnKey: Failed to open reg key <%s>.  Error = %d. Setting default permissions",
              lpSubKey,
              v14);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(
              2u,
              L"AddPolicyPermissionOnKey: Failed to open reg key <%s>.  Error = %d. Setting default permissions",
              lpSubKey,
              v14);
          }
        }
        if ( !MakeRegKeySecure(a1, hKey, lpSubKey, 0, 0, 0) )
        {
          LastError = GetLastError();
          if ( !*(_DWORD *)&g_dwDebugLevel )
            goto LABEL_101;
          v15 = g_lpDebugMsg;
          if ( !g_lpDebugMsg )
          {
            if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
              RedirectDebugMsg(
                2u,
                L"AddPolicyPermissionOnKey: Failed to apply default permission to reg key <%s>.  Error = %d",
                lpSubKey,
                LastError);
            goto LABEL_101;
          }
          v16 = L"AddPolicyPermissionOnKey: Failed to apply default permission to reg key <%s>.  Error = %d";
          goto LABEL_35;
        }
      }
      goto LABEL_100;
    }
    KeySecurity = (unsigned int)RegGetKeySecurity(phkResult, 4u, 0, &cbSecurityDescriptor);
    if ( cbSecurityDescriptor )
    {
      v18 = LocalAlloc(0x40u, cbSecurityDescriptor);
      XPtrLF<_SECURITY_DESCRIPTOR>::operator=(&pSecurityDescriptor, v18);
      v6 = pSecurityDescriptor;
      if ( !pSecurityDescriptor )
      {
        LastError = GetLastError();
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(2u, L"ResetRegKeySecurity: Failed to allocate memory");
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(2u, L"ResetRegKeySecurity: Failed to allocate memory");
          }
        }
        goto LABEL_101;
      }
      LastError = RegGetKeySecurity(phkResult, 4u, pSecurityDescriptor, &cbSecurityDescriptor);
      if ( LastError )
      {
        if ( !*(_DWORD *)&g_dwDebugLevel )
          goto LABEL_101;
        v9 = g_lpDebugMsg;
        if ( g_lpDebugMsg )
        {
          v10 = L"ResetRegKeySecurity: Failed to query key security with %d";
LABEL_51:
          v11 = 2;
          goto LABEL_18;
        }
        if ( !g_lpDebugMsgContextInstance || !g_lpDebugMsgContext )
          goto LABEL_101;
        v12 = L"ResetRegKeySecurity: Failed to query key security with %d";
        goto LABEL_55;
      }
      if ( !GetSecurityDescriptorDacl(v6, &bDaclPresent, &pDacl, &bDaclDefaulted) )
      {
        LastError = GetLastError();
        if ( !*(_DWORD *)&g_dwDebugLevel )
          goto LABEL_101;
        v9 = g_lpDebugMsg;
        if ( g_lpDebugMsg )
        {
          v10 = L"ResetRegKeySecurity: Failed to get dacl with %d";
          goto LABEL_51;
        }
        if ( !g_lpDebugMsgContextInstance || !g_lpDebugMsgContext )
          goto LABEL_101;
        v12 = L"ResetRegKeySecurity: Failed to get dacl with %d";
LABEL_55:
        v13 = 2;
        goto LABEL_22;
      }
      if ( !bDaclPresent )
        pDacl = 0;
    }
    else if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        nSubAuthority2[0] = 0;
        g_lpDebugMsg(
          2u,
          L"ResetRegKeySecurity: RegGetKeySecurity on key <%s>. error %d. size %d",
          lpSubKey,
          KeySecurity,
          *(_QWORD *)nSubAuthority2);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        nSubAuthority2[0] = 0;
        RedirectDebugMsg(
          2u,
          L"ResetRegKeySecurity: RegGetKeySecurity on key <%s>. error %d. size %d",
          lpSubKey,
          KeySecurity,
          *(_QWORD *)nSubAuthority2);
      }
    }
    LastError = SetEntriesInAclW(1u, &pListOfExplicitEntries, pDacl, &NewAcl);
    if ( LastError )
    {
      if ( !*(_DWORD *)&g_dwDebugLevel )
        goto LABEL_101;
      v9 = g_lpDebugMsg;
      if ( g_lpDebugMsg )
      {
        v10 = L"AddPolicyPermissionOnKey: Failed to set acl entry.  Error = %d";
        goto LABEL_51;
      }
      if ( !g_lpDebugMsgContextInstance || !g_lpDebugMsgContext )
        goto LABEL_101;
      v12 = L"AddPolicyPermissionOnKey: Failed to set acl entry.  Error = %d";
    }
    else if ( InitializeSecurityDescriptor(v30, 1u) )
    {
      if ( SetSecurityDescriptorDacl(v30, 1, NewAcl, 0) )
      {
        LastError = RegSetKeySecurity(phkResult, 4u, v30);
        if ( LastError )
        {
          if ( !*(_DWORD *)&g_dwDebugLevel )
            goto LABEL_101;
          v15 = g_lpDebugMsg;
          if ( !g_lpDebugMsg )
          {
            if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
              RedirectDebugMsg(
                2u,
                L"AddPolicyPermissionOnKey: Failed to set sd on reg key <%s>.  Error = %d",
                lpSubKey,
                LastError);
            goto LABEL_101;
          }
          v16 = L"AddPolicyPermissionOnKey: Failed to set sd on reg key <%s>.  Error = %d";
LABEL_35:
          v15(2u, v16, lpSubKey, LastError);
          goto LABEL_101;
        }
LABEL_100:
        LastError = 0;
        goto LABEL_101;
      }
      LastError = GetLastError();
      if ( !*(_DWORD *)&g_dwDebugLevel )
        goto LABEL_101;
      v9 = g_lpDebugMsg;
      if ( g_lpDebugMsg )
      {
        v10 = L"MakeRegKeySecure: Failed to set security descriptor dacl.  Error = %d";
        goto LABEL_51;
      }
      if ( !g_lpDebugMsgContextInstance || !g_lpDebugMsgContext )
        goto LABEL_101;
      v12 = L"MakeRegKeySecure: Failed to set security descriptor dacl.  Error = %d";
    }
    else
    {
      LastError = GetLastError();
      if ( !*(_DWORD *)&g_dwDebugLevel )
        goto LABEL_101;
      v9 = g_lpDebugMsg;
      if ( g_lpDebugMsg )
      {
        v10 = L"MakeRegKeySecure: Failed to initialize security descriptor.  Error = %d";
        goto LABEL_51;
      }
      if ( !g_lpDebugMsgContextInstance || !g_lpDebugMsgContext )
        goto LABEL_101;
      v12 = L"MakeRegKeySecure: Failed to initialize security descriptor.  Error = %d";
    }
    goto LABEL_55;
  }
  LastError = GetLastError();
  if ( !*(_DWORD *)&g_dwDebugLevel )
    goto LABEL_101;
  v9 = g_lpDebugMsg;
  if ( g_lpDebugMsg )
  {
    v10 = L"AddPolicyPermissionOnKey: Failed to initialize system sid.  Error = %d";
    v11 = 4;
LABEL_18:
    v9(v11, v10, LastError);
    goto LABEL_101;
  }
  if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
  {
    v12 = L"AddPolicyPermissionOnKey: Failed to initialize system sid.  Error = %d";
    v13 = 4;
LABEL_22:
    RedirectDebugMsg(v13, v12, LastError);
  }
LABEL_101:
  if ( pSid )
    FreeSid(pSid);
  XKey::Free((XKey *)&phkResult);
  if ( NewAcl )
    NewAcl = (PACL)LocalFree(NewAcl);
  if ( v6 )
    LocalFree(v6);
  return LastError;
}

```

## disassembly

```asm
0x180065240  mov     [rsp-8+arg_18], rbx
0x180065245  push    rbp
0x180065246  push    rsi
0x180065247  push    rdi
0x180065248  push    r12
0x18006524a  push    r13
0x18006524c  push    r14
0x18006524e  push    r15
0x180065250  lea     rbp, [rsp-27h]
0x180065255  sub     rsp, 100h
0x18006525c  mov     rax, cs:__security_cookie
0x180065263  xor     rax, rsp
0x180065266  mov     [rbp+57h+var_38], rax
0x18006526a  mov     rsi, r8
0x18006526d  mov     rdi, rdx
0x180065270  mov     r14, rcx
0x180065273  xor     r15d, r15d
0x180065276  mov     ebx, r15d
0x180065279  mov     [rbp+57h+pSecurityDescriptor], rbx
0x18006527d  mov     [rbp+57h+pDacl], r15
0x180065281  mov     [rbp+57h+NewAcl], r15
0x180065285  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r15d
0x180065289  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x18006528f  mov     [rbp+57h+var_A8], r15
0x180065293  mov     [rbp+57h+phkResult], r15
0x180065297  xorps   xmm0, xmm0
0x18006529a  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], xmm0
0x18006529e  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.Trustee.pMultipleTrustee], xmm0
0x1800652a2  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeType], xmm0
0x1800652a6  mov     [rbp+57h+bDaclPresent], r15d
0x1800652aa  mov     [rbp+57h+bDaclDefaulted], r15d
0x1800652ae  mov     [rbp+57h+cbSecurityDescriptor], r15d
0x1800652b2  xor     eax, eax
0x1800652b4  movups  [rbp+57h+var_68], xmm0
0x1800652b8  movups  [rbp+57h+var_58], xmm0
0x1800652bc  mov     [rbp+57h+var_48], rax
0x1800652c0  lea     r13d, [r15+4]
0x1800652c4  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x1800652cb  jz      short loc_18006530B
0x1800652cd  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800652d4  test    rax, rax
0x1800652d7  jz      short loc_1800652EA
0x1800652d9  lea     rdx, aAddpolicypermi_3; "AddPolicyPermissionOnKey: Setting permi"...
0x1800652e0  mov     ecx, r13d
0x1800652e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800652e8  jmp     short loc_18006530B
0x1800652ea  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x1800652f1  jz      short loc_18006530B
0x1800652f3  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800652fa  jz      short loc_18006530B
0x1800652fc  lea     rdx, aAddpolicypermi_3; "AddPolicyPermissionOnKey: Setting permi"...
0x180065303  mov     ecx, r13d; unsigned int
0x180065306  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18006530b  mov     rdx, rsi; lpSubKey
0x18006530e  mov     rcx, rdi; hKey
0x180065311  call    ?SetPolicyOwnerOnKey@@YAKPEAUHKEY__@@PEBG@Z; SetPolicyOwnerOnKey(HKEY__ *,ushort const *)
0x180065316  mov     r9d, eax
0x180065319  mov     r12d, 2
0x18006531f  test    eax, eax
0x180065321  jz      short loc_180065370
0x180065323  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x18006532a  jz      short loc_180065370
0x18006532c  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180065333  test    rax, rax
0x180065336  jz      short loc_18006534C
0x180065338  mov     r8, rsi
0x18006533b  lea     rdx, aAddpolicypermi_7; "AddPolicyPermissionOnKey: Failed to set"...
0x180065342  mov     ecx, r12d
0x180065345  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006534a  jmp     short loc_180065370
0x18006534c  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x180065353  jz      short loc_180065370
0x180065355  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18006535c  jz      short loc_180065370
0x18006535e  mov     r8, rsi
0x180065361  lea     rdx, aAddpolicypermi_7; "AddPolicyPermissionOnKey: Failed to set"...
0x180065368  mov     ecx, r12d; unsigned int
0x18006536b  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180065370  lea     rax, [rbp+57h+var_A8]
0x180065374  mov     [rsp+130h+pSid], rax; pSid
0x180065379  mov     [rsp+130h+nSubAuthority7], r15d; nSubAuthority7
0x18006537e  mov     [rsp+130h+nSubAuthority6], r15d; nSubAuthority6
0x180065383  mov     [rsp+130h+nSubAuthority5], r15d; nSubAuthority5
0x180065388  mov     [rsp+130h+nSubAuthority4], r15d; nSubAuthority4
0x18006538d  mov     [rsp+130h+nSubAuthority3], r15d; nSubAuthority3
0x180065392  mov     [rsp+130h+nSubAuthority2], r15d; nSubAuthority2
0x180065397  xor     r9d, r9d; nSubAuthority1
0x18006539a  lea     r8d, [r9+12h]; nSubAuthority0
0x18006539e  mov     dl, 1; nSubAuthorityCount
0x1800653a0  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x1800653a4  call    cs:__imp_AllocateAndInitializeSid
0x1800653aa  test    eax, eax
0x1800653ac  jnz     short loc_180065417
0x1800653ae  call    cs:__imp_GetLastError
0x1800653b4  mov     edi, eax
0x1800653b6  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x1800653bd  jz      loc_1800658BC
0x1800653c3  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800653ca  test    rax, rax
0x1800653cd  jz      short loc_1800653E6
0x1800653cf  lea     rdx, aAddpolicypermi_11; "AddPolicyPermissionOnKey: Failed to ini"...
0x1800653d6  mov     ecx, r13d
0x1800653d9  mov     r8d, edi
0x1800653dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800653e1  jmp     loc_1800658BC
0x1800653e6  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x1800653ed  jz      loc_1800658BC
0x1800653f3  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800653fa  jz      loc_1800658BC
0x180065400  lea     rdx, aAddpolicypermi_11; "AddPolicyPermissionOnKey: Failed to ini"...
0x180065407  mov     ecx, r13d; unsigned int
0x18006540a  mov     r8d, edi
0x18006540d  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180065412  jmp     loc_1800658BC
0x180065417  mov     qword ptr [rbp+57h+pListOfExplicitEntries.grfInheritance], 3
0x18006541f  mov     qword ptr [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeType], r15
0x180065423  mov     [rbp+57h+pListOfExplicitEntries.grfAccessMode], 1
0x18006542a  mov     [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], 0F003Fh
0x180065431  mov     qword ptr [rbp+57h+pListOfExplicitEntries.Trustee.MultipleTrusteeOperation], r15
0x180065435  mov     [rbp+57h+pListOfExplicitEntries.Trustee.pMultipleTrustee], r15
0x180065439  mov     rax, [rbp+57h+var_A8]
0x18006543d  mov     [rbp+57h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x180065441  lea     rax, [rbp+57h+phkResult]
0x180065445  mov     qword ptr [rsp+130h+nSubAuthority2], rax; phkResult
0x18006544a  mov     r9d, 60019h; samDesired
0x180065450  xor     r8d, r8d; ulOptions
0x180065453  mov     rdx, rsi; lpSubKey
0x180065456  mov     rcx, rdi; hKey
0x180065459  call    cs:__imp_RegOpenKeyExW
0x18006545f  test    eax, eax
0x180065461  jz      loc_18006554A
0x180065467  cmp     eax, r12d
0x18006546a  jz      loc_1800658B9
0x180065470  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x180065477  jz      short loc_1800654C6
0x180065479  mov     r10, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180065480  test    r10, r10
0x180065483  jz      short loc_18006549F
0x180065485  mov     r9d, eax
0x180065488  mov     r8, rsi
0x18006548b  lea     rdx, aAddpolicypermi_0; "AddPolicyPermissionOnKey: Failed to ope"...
0x180065492  mov     ecx, r12d
0x180065495  mov     rax, r10
0x180065498  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006549d  jmp     short loc_1800654C6
0x18006549f  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x1800654a6  jz      short loc_1800654C6
0x1800654a8  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800654af  jz      short loc_1800654C6
0x1800654b1  mov     r9d, eax
0x1800654b4  mov     r8, rsi
0x1800654b7  lea     rdx, aAddpolicypermi_0; "AddPolicyPermissionOnKey: Failed to ope"...
0x1800654be  mov     ecx, r12d; unsigned int
0x1800654c1  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800654c6  mov     [rsp+130h+nSubAuthority3], r15d; int
0x1800654cb  mov     [rsp+130h+nSubAuthority2], r15d; int
0x1800654d0  xor     r9d, r9d; int
0x1800654d3  mov     r8, rsi; unsigned __int16 *
0x1800654d6  mov     rdx, rdi; HKEY
0x1800654d9  mov     rcx, r14; void *
0x1800654dc  call    ?MakeRegKeySecure@@YAHPEAXPEAUHKEY__@@PEBGHHH@Z; MakeRegKeySecure(void *,HKEY__ *,ushort const *,int,int,int)
0x1800654e1  test    eax, eax
0x1800654e3  jnz     loc_1800658B9
0x1800654e9  call    cs:__imp_GetLastError
0x1800654ef  mov     edi, eax
0x1800654f1  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x1800654f8  jz      loc_1800658BC
0x1800654fe  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180065505  test    rax, rax
0x180065508  jz      short loc_180065524
0x18006550a  lea     rdx, aAddpolicypermi_8; "AddPolicyPermissionOnKey: Failed to app"...
0x180065511  mov     r8, rsi
0x180065514  mov     r9d, edi
0x180065517  mov     ecx, r12d
0x18006551a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006551f  jmp     loc_1800658BC
0x180065524  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x18006552b  jz      loc_1800658BC
0x180065531  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180065538  jz      loc_1800658BC
0x18006553e  lea     rdx, aAddpolicypermi_8; "AddPolicyPermissionOnKey: Failed to app"...
0x180065545  jmp     loc_1800658A9
0x18006554a  lea     r9, [rbp+57h+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x18006554e  xor     r8d, r8d; pSecurityDescriptor
0x180065551  mov     edx, r13d; SecurityInformation
0x180065554  mov     rcx, [rbp+57h+phkResult]; hKey
0x180065558  call    cs:__imp_RegGetKeySecurity
0x18006555e  mov     r9d, eax
0x180065561  mov     ecx, [rbp+57h+cbSecurityDescriptor]
0x180065564  test    ecx, ecx
0x180065566  jz      loc_1800656CE
0x18006556c  mov     edx, ecx; uBytes
0x18006556e  mov     ecx, 40h ; '@'; uFlags
0x180065573  call    cs:__imp_LocalAlloc
0x180065579  mov     rdx, rax
0x18006557c  lea     rcx, [rbp+57h+pSecurityDescriptor]
0x180065580  call    ??4?$XPtrLF@U_SECURITY_DESCRIPTOR@@@@QEAAPEAU_SECURITY_DESCRIPTOR@@PEAU1@@Z; XPtrLF<_SECURITY_DESCRIPTOR>::operator=(_SECURITY_DESCRIPTOR *)
0x180065585  mov     rbx, [rbp+57h+pSecurityDescriptor]
0x180065589  test    rbx, rbx
0x18006558c  jnz     short loc_1800655F1
0x18006558e  call    cs:__imp_GetLastError
0x180065594  mov     edi, eax
0x180065596  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x18006559d  jz      loc_1800658BC
0x1800655a3  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800655aa  test    rax, rax
0x1800655ad  jz      short loc_1800655C3
0x1800655af  lea     rdx, aResetregkeysec_5; "ResetRegKeySecurity: Failed to allocate"...
0x1800655b6  mov     ecx, r12d
0x1800655b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800655be  jmp     loc_1800658BC
0x1800655c3  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x1800655ca  jz      loc_1800658BC
0x1800655d0  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800655d7  jz      loc_1800658BC
0x1800655dd  lea     rdx, aResetregkeysec_5; "ResetRegKeySecurity: Failed to allocate"...
0x1800655e4  mov     ecx, r12d; unsigned int
0x1800655e7  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800655ec  jmp     loc_1800658BC
0x1800655f1  lea     r9, [rbp+57h+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x1800655f5  mov     r8, rbx; pSecurityDescriptor
0x1800655f8  mov     edx, r13d; SecurityInformation
0x1800655fb  mov     rcx, [rbp+57h+phkResult]; hKey
0x1800655ff  call    cs:__imp_RegGetKeySecurity
0x180065605  mov     edi, eax
0x180065607  test    eax, eax
0x180065609  jz      short loc_18006565C
0x18006560b  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x180065612  jz      loc_1800658BC
0x180065618  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18006561f  test    rax, rax
0x180065622  jz      short loc_180065633
0x180065624  lea     rdx, aResetregkeysec_3; "ResetRegKeySecurity: Failed to query ke"...
0x18006562b  mov     ecx, r12d
0x18006562e  jmp     loc_1800653D9
0x180065633  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x18006563a  jz      loc_1800658BC
0x180065640  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180065647  jz      loc_1800658BC
0x18006564d  lea     rdx, aResetregkeysec_3; "ResetRegKeySecurity: Failed to query ke"...
0x180065654  mov     ecx, r12d
0x180065657  jmp     loc_18006540A
0x18006565c  lea     r9, [rbp+57h+bDaclDefaulted]; lpbDaclDefaulted
0x180065660  lea     r8, [rbp+57h+pDacl]; pDacl
0x180065664  lea     rdx, [rbp+57h+bDaclPresent]; lpbDaclPresent
0x180065668  mov     rcx, rbx; pSecurityDescriptor
0x18006566b  call    cs:__imp_GetSecurityDescriptorDacl
0x180065671  test    eax, eax
0x180065673  jnz     short loc_1800656C2
0x180065675  call    cs:__imp_GetLastError
0x18006567b  mov     edi, eax
0x18006567d  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x180065684  jz      loc_1800658BC
0x18006568a  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180065691  test    rax, rax
0x180065694  jz      short loc_18006569F
0x180065696  lea     rdx, aResetregkeysec_0; "ResetRegKeySecurity: Failed to get dacl"...
0x18006569d  jmp     short loc_18006562B
0x18006569f  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x1800656a6  jz      loc_1800658BC
0x1800656ac  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800656b3  jz      loc_1800658BC
0x1800656b9  lea     rdx, aResetregkeysec_0; "ResetRegKeySecurity: Failed to get dacl"...
0x1800656c0  jmp     short loc_180065654
0x1800656c2  cmp     [rbp+57h+bDaclPresent], r15d
0x1800656c6  jnz     short loc_180065725
0x1800656c8  mov     [rbp+57h+pDacl], r15
0x1800656cc  jmp     short loc_180065725
0x1800656ce  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x1800656d5  jz      short loc_180065725
0x1800656d7  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800656de  test    rax, rax
0x1800656e1  jz      short loc_1800656FC
0x1800656e3  mov     [rsp+130h+nSubAuthority2], r15d
0x1800656e8  mov     r8, rsi
0x1800656eb  lea     rdx, aResetregkeysec; "ResetRegKeySecurity: RegGetKeySecurity "...
0x1800656f2  mov     ecx, r12d
0x1800656f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800656fa  jmp     short loc_180065725
0x1800656fc  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x180065703  jz      short loc_180065725
0x180065705  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18006570c  jz      short loc_180065725
0x18006570e  mov     [rsp+130h+nSubAuthority2], r15d
0x180065713  mov     r8, rsi
0x180065716  lea     rdx, aResetregkeysec; "ResetRegKeySecurity: RegGetKeySecurity "...
0x18006571d  mov     ecx, r12d; unsigned int
0x180065720  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180065725  lea     r9, [rbp+57h+NewAcl]; NewAcl
0x180065729  mov     r8, [rbp+57h+pDacl]; OldAcl
0x18006572d  lea     rdx, [rbp+57h+pListOfExplicitEntries]; pListOfExplicitEntries
0x180065731  mov     r14d, 1
0x180065737  mov     ecx, r14d; cCountOfExplicitEntries
0x18006573a  call    cs:__imp_SetEntriesInAclW
0x180065740  mov     edi, eax
0x180065742  test    eax, eax
0x180065744  jz      short loc_180065791
0x180065746  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x18006574d  jz      loc_1800658BC
0x180065753  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
  ... truncated ...
```
