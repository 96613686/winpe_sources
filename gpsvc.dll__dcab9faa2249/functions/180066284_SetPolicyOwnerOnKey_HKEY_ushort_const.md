# SetPolicyOwnerOnKey(HKEY__ *,ushort const *)

- ea: `0x180066284`
- end: `0x18006667c`
- name: `?SetPolicyOwnerOnKey@@YAKPEAUHKEY__@@PEBG@Z`
- size: `1016`
- prototype: `unsigned int __fastcall(HKEY hKey, LPCWSTR lpSubKey)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180065240`
- `0x180066138`
- `0x1800b5610`

## callees

- `0x180022bd4`
- `0x180066284`
- `0x180075ec0`
- `0x18007d320`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066371`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800663ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006644f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066371`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800663ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006644f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006652b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006652b`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x18006658d`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x18006658d`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800663e3`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800663e3`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x180066445`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x180066445`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180066361`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180066361`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800665e4`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800665e4`
- `ntdll!RtlAdjustPrivilege` at `0x1800664af`
- `ntdll!RtlAdjustPrivilege` at `0x1800665fc`
- `ntdll!RtlAdjustPrivilege` at `0x1800664af`
- `ntdll!RtlAdjustPrivilege` at `0x1800665fc`
- `ntdll!RtlNtStatusToDosError` at `0x1800664bb`
- `ntdll!RtlNtStatusToDosError` at `0x1800664bb`

## string_xrefs

- `0x180066392`: `SetRegPermissionsOnPoliciesKey: Failed to initialize system sid.  Error = %d`
- `0x1800663c3`: `SetRegPermissionsOnPoliciesKey: Failed to initialize system sid.  Error = %d`
- `0x18006640e`: `SetRegPermissionsOnPoliciesKey: Failed to initialize security descriptor.  Error = %d`
- `0x180066431`: `SetRegPermissionsOnPoliciesKey: Failed to initialize security descriptor.  Error = %d`
- `0x180066470`: `SetRegPermissionsOnPoliciesKey: Failed to set security descriptor owner.  Error = %d`
- `0x180066496`: `SetRegPermissionsOnPoliciesKey: Failed to set security descriptor owner.  Error = %d`
- `0x1800664dc`: `SetRegPermissionsOnPoliciesKey: Failed to enable privilege.  Error = %d`
- `0x180066502`: `SetRegPermissionsOnPoliciesKey: Failed to enable privilege.  Error = %d`
- `0x180066559`: `SetRegPermissionsOnPoliciesKey: Failed to open reg key.  Error = %d`
- `0x180066577`: `SetRegPermissionsOnPoliciesKey: Failed to open reg key.  Error = %d`
- `0x1800665ae`: `SetRegPermissionsOnPoliciesKey: Failed to set security, error = %d`
- `0x1800665cc`: `SetRegPermissionsOnPoliciesKey: Failed to set security, error = %d`
- `0x18006661b`: `SetRegPermissionsOnPoliciesKey:  Failed to restore privilege to previous enabled state`
- `0x18006663e`: `SetRegPermissionsOnPoliciesKey:  Failed to restore privilege to previous enabled state`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SetPolicyOwnerOnKey(HKEY hKey, LPCWSTR lpSubKey)
{
  int v4; // esi
  ULONG LastError; // ebx
  void (*v6)(unsigned int, const unsigned __int16 *, ...); // rax
  const wchar_t *v7; // rdx
  int v8; // eax
  LSTATUS v9; // eax
  unsigned __int8 OldValue[8]; // [rsp+60h] [rbp-19h] BYREF
  PSID pOwner; // [rsp+68h] [rbp-11h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp-9h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+78h] [rbp-1h] BYREF
  __int64 v15; // [rsp+98h] [rbp+1Fh]
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+A0h] [rbp+27h] BYREF

  OldValue[0] = 0;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  v15 = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  pOwner = 0;
  phkResult = 0;
  v4 = 0;
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"SetPolicyOwnerOnKey: Setting owner on reg key on <%s>.", lpSubKey);
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(4u, L"SetPolicyOwnerOnKey: Setting owner on reg key on <%s>.", lpSubKey);
    }
  }
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &pOwner) )
  {
    if ( InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
    {
      if ( SetSecurityDescriptorOwner(pSecurityDescriptor, pOwner, 0) )
      {
        v8 = RtlAdjustPrivilege(9u, 1u, 0, OldValue);
        if ( v8 >= 0 )
        {
          v4 = 1;
          v9 = RegOpenKeyExW(hKey, lpSubKey, 0, 0x80000u, &phkResult);
          LastError = v9;
          if ( v9 )
          {
            if ( v9 != 2 )
            {
              if ( *(_DWORD *)&g_dwDebugLevel )
              {
                v6 = g_lpDebugMsg;
                if ( g_lpDebugMsg )
                {
                  v7 = L"SetRegPermissionsOnPoliciesKey: Failed to open reg key.  Error = %d";
                  goto LABEL_11;
                }
                if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                  RedirectDebugMsg(
                    2u,
                    L"SetRegPermissionsOnPoliciesKey: Failed to open reg key.  Error = %d",
                    LastError);
              }
              goto LABEL_53;
            }
          }
          else
          {
            LastError = RegSetKeySecurity(phkResult, 1u, pSecurityDescriptor);
            if ( LastError )
            {
              if ( *(_DWORD *)&g_dwDebugLevel )
              {
                v6 = g_lpDebugMsg;
                if ( g_lpDebugMsg )
                {
                  v7 = L"SetRegPermissionsOnPoliciesKey: Failed to set security, error = %d";
                  goto LABEL_11;
                }
                if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                  RedirectDebugMsg(2u, L"SetRegPermissionsOnPoliciesKey: Failed to set security, error = %d", LastError);
              }
              goto LABEL_53;
            }
          }
          LastError = 0;
          goto LABEL_53;
        }
        LastError = RtlNtStatusToDosError(v8);
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          v6 = g_lpDebugMsg;
          if ( g_lpDebugMsg )
          {
            v7 = L"SetRegPermissionsOnPoliciesKey: Failed to enable privilege.  Error = %d";
            goto LABEL_11;
          }
          if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            RedirectDebugMsg(2u, L"SetRegPermissionsOnPoliciesKey: Failed to enable privilege.  Error = %d", LastError);
        }
      }
      else
      {
        LastError = GetLastError();
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          v6 = g_lpDebugMsg;
          if ( g_lpDebugMsg )
          {
            v7 = L"SetRegPermissionsOnPoliciesKey: Failed to set security descriptor owner.  Error = %d";
            goto LABEL_11;
          }
          if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            RedirectDebugMsg(
              2u,
              L"SetRegPermissionsOnPoliciesKey: Failed to set security descriptor owner.  Error = %d",
              LastError);
        }
      }
    }
    else
    {
      LastError = GetLastError();
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        v6 = g_lpDebugMsg;
        if ( g_lpDebugMsg )
        {
          v7 = L"SetRegPermissionsOnPoliciesKey: Failed to initialize security descriptor.  Error = %d";
          goto LABEL_11;
        }
        if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          RedirectDebugMsg(
            2u,
            L"SetRegPermissionsOnPoliciesKey: Failed to initialize security descriptor.  Error = %d",
            LastError);
      }
    }
  }
  else
  {
    LastError = GetLastError();
    if ( !*(_DWORD *)&g_dwDebugLevel )
      goto LABEL_53;
    v6 = g_lpDebugMsg;
    if ( g_lpDebugMsg )
    {
      v7 = L"SetRegPermissionsOnPoliciesKey: Failed to initialize system sid.  Error = %d";
LABEL_11:
      v6(2u, v7, LastError);
      goto LABEL_53;
    }
    if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      RedirectDebugMsg(2u, L"SetRegPermissionsOnPoliciesKey: Failed to initialize system sid.  Error = %d", LastError);
  }
LABEL_53:
  if ( pOwner )
    FreeSid(pOwner);
  if ( v4 && RtlAdjustPrivilege(9u, OldValue[0], 0, OldValue) < 0 && *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(2u, L"SetRegPermissionsOnPoliciesKey:  Failed to restore privilege to previous enabled state");
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(2u, L"SetRegPermissionsOnPoliciesKey:  Failed to restore privilege to previous enabled state");
    }
  }
  XKey::Free((XKey *)&phkResult);
  return LastError;
}

```

## disassembly

```asm
0x180066284  mov     [rsp-8+arg_10], rbx
0x180066289  push    rbp
0x18006628a  push    rsi
0x18006628b  push    rdi
0x18006628c  push    r14
0x18006628e  push    r15
0x180066290  lea     rbp, [rsp-37h]
0x180066295  sub     rsp, 0B0h
0x18006629c  mov     rax, cs:__security_cookie
0x1800662a3  xor     rax, rsp
0x1800662a6  mov     [rbp+57h+var_28], rax
0x1800662aa  mov     rbx, rdx
0x1800662ad  mov     rdi, rcx
0x1800662b0  xor     r14d, r14d
0x1800662b3  mov     [rbp+57h+OldValue], r14b
0x1800662b7  xorps   xmm0, xmm0
0x1800662ba  xor     eax, eax
0x1800662bc  movups  [rbp+57h+pSecurityDescriptor], xmm0
0x1800662c0  movups  [rbp+57h+var_48], xmm0
0x1800662c4  mov     [rbp+57h+var_38], rax
0x1800662c8  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r14d
0x1800662cc  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x1800662d2  mov     [rbp+57h+pOwner], r14
0x1800662d6  mov     [rbp+57h+phkResult], r14
0x1800662da  mov     esi, r14d
0x1800662dd  cmp     cs:?g_dwDebugLevel@@3KA, r14d; ulong g_dwDebugLevel
0x1800662e4  jz      short loc_18006632D
0x1800662e6  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800662ed  test    rax, rax
0x1800662f0  jz      short loc_180066307
0x1800662f2  mov     r8, rdx
0x1800662f5  lea     rdx, aSetpolicyowner; "SetPolicyOwnerOnKey: Setting owner on r"...
0x1800662fc  lea     ecx, [r14+4]
0x180066300  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066305  jmp     short loc_18006632D
0x180066307  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r14; void * g_lpDebugMsgContextInstance
0x18006630e  jz      short loc_18006632D
0x180066310  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r14; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180066317  jz      short loc_18006632D
0x180066319  mov     r8, rbx
0x18006631c  lea     rdx, aSetpolicyowner; "SetPolicyOwnerOnKey: Setting owner on r"...
0x180066323  mov     ecx, 4; unsigned int
0x180066328  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18006632d  lea     rax, [rbp+57h+pOwner]
0x180066331  mov     [rsp+0D0h+pSid], rax; pSid
0x180066336  mov     [rsp+0D0h+nSubAuthority7], r14d; nSubAuthority7
0x18006633b  mov     [rsp+0D0h+nSubAuthority6], r14d; nSubAuthority6
0x180066340  mov     [rsp+0D0h+nSubAuthority5], r14d; nSubAuthority5
0x180066345  mov     [rsp+0D0h+nSubAuthority4], r14d; nSubAuthority4
0x18006634a  mov     [rsp+0D0h+nSubAuthority3], r14d; nSubAuthority3
0x18006634f  mov     [rsp+0D0h+nSubAuthority2], r14d; nSubAuthority2
0x180066354  xor     r9d, r9d; nSubAuthority1
0x180066357  lea     r8d, [r9+12h]; nSubAuthority0
0x18006635b  mov     dl, 1; nSubAuthorityCount
0x18006635d  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x180066361  call    cs:__imp_AllocateAndInitializeSid
0x180066367  mov     r15d, 2
0x18006636d  test    eax, eax
0x18006636f  jnz     short loc_1800663DA
0x180066371  call    cs:__imp_GetLastError
0x180066377  mov     ebx, eax
0x180066379  cmp     cs:?g_dwDebugLevel@@3KA, r14d; ulong g_dwDebugLevel
0x180066380  jz      loc_1800665DB
0x180066386  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18006638d  test    rax, rax
0x180066390  jz      short loc_1800663A9
0x180066392  lea     rdx, aSetregpermissi; "SetRegPermissionsOnPoliciesKey: Failed "...
0x180066399  mov     r8d, ebx
0x18006639c  mov     ecx, r15d
0x18006639f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800663a4  jmp     loc_1800665DB
0x1800663a9  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r14; void * g_lpDebugMsgContextInstance
0x1800663b0  jz      loc_1800665DB
0x1800663b6  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r14; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800663bd  jz      loc_1800665DB
0x1800663c3  lea     rdx, aSetregpermissi; "SetRegPermissionsOnPoliciesKey: Failed "...
0x1800663ca  mov     r8d, ebx
0x1800663cd  mov     ecx, r15d; unsigned int
0x1800663d0  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800663d5  jmp     loc_1800665DB
0x1800663da  mov     edx, 1; dwRevision
0x1800663df  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x1800663e3  call    cs:__imp_InitializeSecurityDescriptor
0x1800663e9  test    eax, eax
0x1800663eb  jnz     short loc_18006643A
0x1800663ed  call    cs:__imp_GetLastError
0x1800663f3  mov     ebx, eax
0x1800663f5  cmp     cs:?g_dwDebugLevel@@3KA, r14d; ulong g_dwDebugLevel
0x1800663fc  jz      loc_1800665DB
0x180066402  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180066409  test    rax, rax
0x18006640c  jz      short loc_180066417
0x18006640e  lea     rdx, aSetregpermissi_5; "SetRegPermissionsOnPoliciesKey: Failed "...
0x180066415  jmp     short loc_180066399
0x180066417  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r14; void * g_lpDebugMsgContextInstance
0x18006641e  jz      loc_1800665DB
0x180066424  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r14; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18006642b  jz      loc_1800665DB
0x180066431  lea     rdx, aSetregpermissi_5; "SetRegPermissionsOnPoliciesKey: Failed "...
0x180066438  jmp     short loc_1800663CA
0x18006643a  xor     r8d, r8d; bOwnerDefaulted
0x18006643d  mov     rdx, [rbp+57h+pOwner]; pOwner
0x180066441  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x180066445  call    cs:__imp_SetSecurityDescriptorOwner
0x18006644b  test    eax, eax
0x18006644d  jnz     short loc_1800664A2
0x18006644f  call    cs:__imp_GetLastError
0x180066455  mov     ebx, eax
0x180066457  cmp     cs:?g_dwDebugLevel@@3KA, r14d; ulong g_dwDebugLevel
0x18006645e  jz      loc_1800665DB
0x180066464  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18006646b  test    rax, rax
0x18006646e  jz      short loc_18006647C
0x180066470  lea     rdx, aSetregpermissi_3; "SetRegPermissionsOnPoliciesKey: Failed "...
0x180066477  jmp     loc_180066399
0x18006647c  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r14; void * g_lpDebugMsgContextInstance
0x180066483  jz      loc_1800665DB
0x180066489  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r14; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180066490  jz      loc_1800665DB
0x180066496  lea     rdx, aSetregpermissi_3; "SetRegPermissionsOnPoliciesKey: Failed "...
0x18006649d  jmp     loc_1800663CA
0x1800664a2  lea     r9, [rbp+57h+OldValue]; OldValue
0x1800664a6  xor     r8d, r8d; ForThread
0x1800664a9  mov     dl, 1; NewValue
0x1800664ab  lea     ecx, [r8+9]; Privilege
0x1800664af  call    cs:__imp_RtlAdjustPrivilege
0x1800664b5  test    eax, eax
0x1800664b7  jns     short loc_18006650E
0x1800664b9  mov     ecx, eax; Status
0x1800664bb  call    cs:__imp_RtlNtStatusToDosError
0x1800664c1  mov     ebx, eax
0x1800664c3  cmp     cs:?g_dwDebugLevel@@3KA, r14d; ulong g_dwDebugLevel
0x1800664ca  jz      loc_1800665DB
0x1800664d0  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800664d7  test    rax, rax
0x1800664da  jz      short loc_1800664E8
0x1800664dc  lea     rdx, aSetregpermissi_0; "SetRegPermissionsOnPoliciesKey: Failed "...
0x1800664e3  jmp     loc_180066399
0x1800664e8  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r14; void * g_lpDebugMsgContextInstance
0x1800664ef  jz      loc_1800665DB
0x1800664f5  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r14; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800664fc  jz      loc_1800665DB
0x180066502  lea     rdx, aSetregpermissi_0; "SetRegPermissionsOnPoliciesKey: Failed "...
0x180066509  jmp     loc_1800663CA
0x18006650e  mov     esi, 1
0x180066513  lea     rax, [rbp+57h+phkResult]
0x180066517  mov     qword ptr [rsp+0D0h+nSubAuthority2], rax; phkResult
0x18006651c  mov     r9d, 80000h; samDesired
0x180066522  xor     r8d, r8d; ulOptions
0x180066525  mov     rdx, rbx; lpSubKey
0x180066528  mov     rcx, rdi; hKey
0x18006652b  call    cs:__imp_RegOpenKeyExW
0x180066531  mov     ebx, eax
0x180066533  test    eax, eax
0x180066535  jz      short loc_180066583
0x180066537  cmp     eax, r15d
0x18006653a  jz      loc_1800665D8
0x180066540  cmp     cs:?g_dwDebugLevel@@3KA, r14d; ulong g_dwDebugLevel
0x180066547  jz      loc_1800665DB
0x18006654d  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180066554  test    rax, rax
0x180066557  jz      short loc_180066565
0x180066559  lea     rdx, aSetregpermissi_2; "SetRegPermissionsOnPoliciesKey: Failed "...
0x180066560  jmp     loc_180066399
0x180066565  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r14; void * g_lpDebugMsgContextInstance
0x18006656c  jz      short loc_1800665DB
0x18006656e  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r14; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180066575  jz      short loc_1800665DB
0x180066577  lea     rdx, aSetregpermissi_2; "SetRegPermissionsOnPoliciesKey: Failed "...
0x18006657e  jmp     loc_1800663CA
0x180066583  lea     r8, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x180066587  mov     edx, esi; SecurityInformation
0x180066589  mov     rcx, [rbp+57h+phkResult]; hKey
0x18006658d  call    cs:__imp_RegSetKeySecurity
0x180066593  mov     ebx, eax
0x180066595  test    eax, eax
0x180066597  jz      short loc_1800665D8
0x180066599  cmp     cs:?g_dwDebugLevel@@3KA, r14d; ulong g_dwDebugLevel
0x1800665a0  jz      short loc_1800665DB
0x1800665a2  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800665a9  test    rax, rax
0x1800665ac  jz      short loc_1800665BA
0x1800665ae  lea     rdx, aSetregpermissi_1; "SetRegPermissionsOnPoliciesKey: Failed "...
0x1800665b5  jmp     loc_180066399
0x1800665ba  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r14; void * g_lpDebugMsgContextInstance
0x1800665c1  jz      short loc_1800665DB
0x1800665c3  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r14; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800665ca  jz      short loc_1800665DB
0x1800665cc  lea     rdx, aSetregpermissi_1; "SetRegPermissionsOnPoliciesKey: Failed "...
0x1800665d3  jmp     loc_1800663CA
0x1800665d8  mov     ebx, r14d
0x1800665db  mov     rcx, [rbp+57h+pOwner]; pSid
0x1800665df  test    rcx, rcx
0x1800665e2  jz      short loc_1800665EA
0x1800665e4  call    cs:__imp_FreeSid
0x1800665ea  test    esi, esi
0x1800665ec  jz      short loc_18006664E
0x1800665ee  lea     r9, [rbp+57h+OldValue]; OldValue
0x1800665f2  xor     r8d, r8d; ForThread
0x1800665f5  mov     dl, [rbp+57h+OldValue]; NewValue
0x1800665f8  lea     ecx, [r8+9]; Privilege
0x1800665fc  call    cs:__imp_RtlAdjustPrivilege
0x180066602  test    eax, eax
0x180066604  jns     short loc_18006664E
0x180066606  cmp     cs:?g_dwDebugLevel@@3KA, r14d; ulong g_dwDebugLevel
0x18006660d  jz      short loc_18006664E
0x18006660f  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180066616  test    rax, rax
0x180066619  jz      short loc_18006662C
0x18006661b  lea     rdx, aSetregpermissi_6; "SetRegPermissionsOnPoliciesKey:  Failed"...
0x180066622  mov     ecx, r15d
0x180066625  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006662a  jmp     short loc_18006664E
0x18006662c  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r14; void * g_lpDebugMsgContextInstance
0x180066633  jz      short loc_18006664E
0x180066635  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r14; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18006663c  jz      short loc_18006664E
0x18006663e  lea     rdx, aSetregpermissi_6; "SetRegPermissionsOnPoliciesKey:  Failed"...
0x180066645  mov     ecx, r15d; unsigned int
0x180066648  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18006664d  nop
0x18006664e  lea     rcx, [rbp+57h+phkResult]; this
0x180066652  call    ?Free@XKey@@QEAAXXZ; XKey::Free(void)
0x180066657  mov     eax, ebx
0x180066659  mov     rcx, [rbp+57h+var_28]
0x18006665d  xor     rcx, rsp; StackCookie
0x180066660  call    __security_check_cookie
0x180066665  mov     rbx, [rsp+0D0h+arg_10]
0x18006666d  add     rsp, 0B0h
0x180066674  pop     r15
0x180066676  pop     r14
0x180066678  pop     rdi
0x180066679  pop     rsi
0x18006667a  pop     rbp
0x18006667b  retn
```
