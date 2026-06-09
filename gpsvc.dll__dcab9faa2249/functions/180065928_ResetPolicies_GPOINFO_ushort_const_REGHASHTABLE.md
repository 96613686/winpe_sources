# ResetPolicies(_GPOINFO *,ushort const *,_REGHASHTABLE *)

- ea: `0x180065928`
- end: `0x18006612f`
- name: `?ResetPolicies@@YAHPEAU_GPOINFO@@PEBGPEAU_REGHASHTABLE@@@Z`
- size: `2055`
- prototype: `__int64 __fastcall(struct _GPOINFO *, const unsigned __int16 *, struct _REGHASHTABLE *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800a1e20`

## callees

- `0x1800336a0`
- `0x180065928`
- `0x180066138`
- `0x180068650`
- `0x180075ec0`
- `0x18009fbb0`
- `0x18009ff54`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180066115`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180066115`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065957`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800659d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065a02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065a40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065a69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065aa0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065ad1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065b40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065957`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800659d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065a02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065a40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065a69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065aa0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065ad1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065b40`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180065d4f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180065e44`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180065f39`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800660c1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180065d4f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180065e44`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180065f39`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800660c1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800660b7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800660b7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180065d30`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180065e33`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180065f28`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180066088`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180065d30`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180065e33`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180065f28`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180066088`

## string_xrefs

- `0x180065b70`: `ResetPolicies: ParseRegistryFile failed with error %d. deleting policy keys`
- `0x180065b95`: `ResetPolicies: ParseRegistryFile failed with error %d. deleting policy keys`
- `0x180065bbe`: `ResetPolicies: Failed to delete the reg key with %d`
- `0x180065ccf`: `ResetPolicies: ParseRegistryFile failed with error %d and thus skipping the registy keys deletion`
- `0x180065cf1`: `ResetPolicies: ParseRegistryFile failed with error %d and thus skipping the registy keys deletion`
- `0x180065d40`: `ResetPolicies: Failed to create reg key with %d.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ResetPolicies(struct _GPOINFO *a1, unsigned __int16 *a2, struct _REGHASHTABLE *a3)
{
  DWORD LastError; // ebx
  void (*v7)(unsigned int, const unsigned __int16 *, ...); // rsi
  DWORD v8; // eax
  const wchar_t *v9; // rdx
  DWORD v10; // eax
  DWORD v11; // eax
  DWORD v12; // eax
  unsigned int v13; // r14d
  int IsDomainIncapableSystem; // eax
  int v15; // eax
  __int64 v16; // r8
  void *v17; // rcx
  unsigned int v18; // eax
  void *v19; // rcx
  unsigned int v20; // eax
  void *v21; // rcx
  unsigned int v22; // eax
  void (*v23)(unsigned int, const unsigned __int16 *, ...); // rax
  const unsigned __int16 *v24; // rdx
  unsigned int v25; // eax
  void *v26; // rcx
  unsigned int v27; // eax
  void *v28; // rcx
  unsigned int v29; // eax
  void *v30; // rcx
  BYTE Data[4]; // [rsp+60h] [rbp-18h] BYREF
  DWORD v33; // [rsp+64h] [rbp-14h]
  HKEY hKey[2]; // [rsp+68h] [rbp-10h] BYREF
  DWORD dwDisposition; // [rsp+D8h] [rbp+60h] BYREF

  hKey[0] = 0;
  dwDisposition = 0;
  *(_DWORD *)Data = 145;
  LastError = GetLastError();
  v33 = LastError;
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"ResetPolicies: Entering.");
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(4u, L"ResetPolicies: Entering.");
    }
  }
  if ( !SetRegPermissionsOnPoliciesKey(a1, L"Software\\Policies") )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      v7 = g_lpDebugMsg;
      if ( !g_lpDebugMsg )
      {
        if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          v10 = GetLastError();
          RedirectDebugMsg(2u, L"ResetPolicies: Failed to set permissions on the policy key(1) with %d", v10);
        }
        goto LABEL_29;
      }
      v8 = GetLastError();
      v9 = L"ResetPolicies: Failed to set permissions on the policy key(1) with %d";
      goto LABEL_25;
    }
LABEL_29:
    v13 = 0;
    goto LABEL_137;
  }
  if ( !SetRegPermissionsOnPoliciesKey(a1, L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies") )
  {
    if ( !*(_DWORD *)&g_dwDebugLevel )
      goto LABEL_29;
    v7 = g_lpDebugMsg;
    if ( !g_lpDebugMsg )
    {
      if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        v11 = GetLastError();
        RedirectDebugMsg(2u, L"ResetPolicies: Failed to set permissions on the policy key(2) with %d", v11);
      }
      goto LABEL_29;
    }
    v8 = GetLastError();
    v9 = L"ResetPolicies: Failed to set permissions on the policy key(2) with %d";
LABEL_25:
    v7(2u, v9, v8);
    goto LABEL_29;
  }
  if ( !SetRegPermissionsOnPoliciesKey(a1, L"System\\CurrentControlSet\\Policies") )
  {
    if ( !*(_DWORD *)&g_dwDebugLevel )
      goto LABEL_29;
    v7 = g_lpDebugMsg;
    if ( !g_lpDebugMsg )
    {
      if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        v12 = GetLastError();
        RedirectDebugMsg(2u, L"ResetPolicies: Failed to set permissions on the policy key(3) with %d", v12);
      }
      goto LABEL_29;
    }
    v8 = GetLastError();
    v9 = L"ResetPolicies: Failed to set permissions on the policy key(3) with %d";
    goto LABEL_25;
  }
  IsDomainIncapableSystem = CSKU::IsDomainIncapableSystem();
  v15 = ParseRegistryFile(a1, a2, DeleteRegistryValue, 0, 0, 0, 0, a3, 0, 0, IsDomainIncapableSystem);
  v13 = 1;
  if ( !v15 )
  {
    LastError = GetLastError();
    v33 = LastError;
    v16 = 32;
    if ( LastError != 32 )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"ResetPolicies: ParseRegistryFile failed with error %d. deleting policy keys", LastError);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(
            2u,
            L"ResetPolicies: ParseRegistryFile failed with error %d. deleting policy keys",
            LastError);
        }
      }
      v17 = 0;
      if ( (*(_BYTE *)a1 & 1) == 0 )
        v17 = (void *)*((_QWORD *)a1 + 1);
      v18 = ForceGPRegDelnode(v17, *((HKEY *)a1 + 5), L"Software\\Policies");
      if ( v18 && *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"ResetPolicies: Failed to delete the reg key with %d", v18);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(2u, L"ResetPolicies: Failed to delete the reg key with %d", v18);
        }
      }
      v19 = 0;
      if ( (*(_BYTE *)a1 & 1) == 0 )
        v19 = (void *)*((_QWORD *)a1 + 1);
      v20 = ForceGPRegDelnode(v19, *((HKEY *)a1 + 5), L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies");
      if ( v20 && *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"ResetPolicies: Failed to delete the reg key with %d", v20);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(2u, L"ResetPolicies: Failed to delete the reg key with %d", v20);
        }
      }
      v21 = 0;
      if ( (*(_BYTE *)a1 & 1) == 0 )
        v21 = (void *)*((_QWORD *)a1 + 1);
      v22 = ForceGPRegDelnode(v21, *((HKEY *)a1 + 5), L"System\\CurrentControlSet\\Policies");
      v16 = v22;
      if ( !v22 || !*(_DWORD *)&g_dwDebugLevel )
        goto LABEL_72;
      v23 = g_lpDebugMsg;
      if ( !g_lpDebugMsg )
      {
        if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          RedirectDebugMsg(2u, L"ResetPolicies: Failed to delete the reg key with %d", v16);
        goto LABEL_72;
      }
      v24 = L"ResetPolicies: Failed to delete the reg key with %d";
      goto LABEL_68;
    }
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      v23 = g_lpDebugMsg;
      if ( !g_lpDebugMsg )
      {
        if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          RedirectDebugMsg(
            2u,
            L"ResetPolicies: ParseRegistryFile failed with error %d and thus skipping the registy keys deletion",
            32);
        goto LABEL_72;
      }
      v24 = L"ResetPolicies: ParseRegistryFile failed with error %d and thus skipping the registy keys deletion";
LABEL_68:
      v23(2u, v24, v16);
    }
  }
LABEL_72:
  v25 = RegCreateKeyExW(*((HKEY *)a1 + 5), L"Software\\Policies", 0, 0, 0, 0x20006u, 0, hKey, &dwDisposition);
  if ( v25 )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"ResetPolicies: Failed to create reg key with %d.", v25);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"ResetPolicies: Failed to create reg key with %d.", v25);
      }
    }
  }
  else
  {
    RegCloseKey(hKey[0]);
    v26 = 0;
    if ( (*(_BYTE *)a1 & 1) == 0 )
      v26 = (void *)*((_QWORD *)a1 + 1);
    if ( !(unsigned int)MakeRegKeySecure(v26, *((HKEY *)a1 + 5), L"Software\\Policies", 0, 0, 1)
      && *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"ResetPolicies: Failed to secure reg key.");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"ResetPolicies: Failed to secure reg key.");
      }
    }
  }
  v27 = RegCreateKeyExW(
          *((HKEY *)a1 + 5),
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies",
          0,
          0,
          0,
          0x20006u,
          0,
          hKey,
          &dwDisposition);
  if ( v27 )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"ResetPolicies: Failed to create reg key with %d.", v27);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"ResetPolicies: Failed to create reg key with %d.", v27);
      }
    }
  }
  else
  {
    RegCloseKey(hKey[0]);
    v28 = 0;
    if ( (*(_BYTE *)a1 & 1) == 0 )
      v28 = (void *)*((_QWORD *)a1 + 1);
    if ( !(unsigned int)MakeRegKeySecure(
                          v28,
                          *((HKEY *)a1 + 5),
                          L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies",
                          0,
                          0,
                          1)
      && *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"ResetPolicies: Failed to secure reg key.");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"ResetPolicies: Failed to secure reg key.");
      }
    }
  }
  v29 = RegCreateKeyExW(
          *((HKEY *)a1 + 5),
          L"System\\CurrentControlSet\\Policies",
          0,
          0,
          0,
          0x20006u,
          0,
          hKey,
          &dwDisposition);
  if ( v29 )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"ResetPolicies: Failed to create reg key with %d.", v29);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"ResetPolicies: Failed to create reg key with %d.", v29);
      }
    }
  }
  else
  {
    RegCloseKey(hKey[0]);
    v30 = 0;
    if ( (*(_BYTE *)a1 & 1) == 0 )
      v30 = (void *)*((_QWORD *)a1 + 1);
    if ( !(unsigned int)MakeRegKeySecure(v30, *((HKEY *)a1 + 5), L"System\\CurrentControlSet\\Policies", 0, 0, 1)
      && *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"ResetPolicies: Failed to secure reg key.");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"ResetPolicies: Failed to secure reg key.");
      }
    }
  }
  if ( (*(_BYTE *)a1 & 1) == 0 )
  {
    if ( ((g_ProductType - 2) & 0xFFFFFFFD) == 0 )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(4u, L"ResetPolicies: resetting shell autorun value for server.");
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(4u, L"ResetPolicies: resetting shell autorun value for server.");
        }
      }
      *(_DWORD *)Data = 149;
    }
    if ( !RegCreateKeyExW(
            *((HKEY *)a1 + 5),
            L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\Explorer",
            0,
            0,
            0,
            0x20006u,
            0,
            hKey,
            &dwDisposition) )
    {
      RegSetValueExW(hKey[0], L"NoDriveTypeAutoRun", 0, 4u, Data, 4u);
      RegCloseKey(hKey[0]);
    }
  }
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"ResetPolicies: Leaving.");
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(4u, L"ResetPolicies: Leaving.");
    }
  }
LABEL_137:
  SetLastError(LastError);
  return v13;
}

```

## disassembly

```asm
0x180065928  push    rbp
0x18006592a  push    rbx
0x18006592b  push    rsi
0x18006592c  push    rdi
0x18006592d  push    r12
0x18006592f  push    r13
0x180065931  push    r14
0x180065933  push    r15
0x180065935  mov     rbp, rsp
0x180065938  sub     rsp, 78h
0x18006593c  mov     rdi, r8
0x18006593f  mov     r14, rdx
0x180065942  mov     rsi, rcx
0x180065945  xor     r15d, r15d
0x180065948  mov     [rbp+hKey], r15
0x18006594c  mov     [rbp+dwDisposition], r15d
0x180065950  mov     dword ptr [rbp+Data], 91h
0x180065957  call    cs:__imp_GetLastError
0x18006595d  mov     ebx, eax
0x18006595f  mov     [rbp+var_14], eax
0x180065962  lea     ecx, [r15+4]; unsigned int
0x180065966  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x18006596d  jz      short loc_1800659A7
0x18006596f  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180065976  test    rax, rax
0x180065979  jz      short loc_180065989
0x18006597b  lea     rdx, aResetpoliciesE; "ResetPolicies: Entering."
0x180065982  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065987  jmp     short loc_1800659A7
0x180065989  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x180065990  jz      short loc_1800659A7
0x180065992  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180065999  jz      short loc_1800659A7
0x18006599b  lea     rdx, aResetpoliciesE; "ResetPolicies: Entering."
0x1800659a2  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800659a7  lea     r13, String1; "Software\\Policies"
0x1800659ae  mov     rdx, r13; unsigned __int16 *
0x1800659b1  mov     rcx, rsi; struct _GPOINFO *
0x1800659b4  call    ?SetRegPermissionsOnPoliciesKey@@YAHPEAU_GPOINFO@@PEBG@Z; SetRegPermissionsOnPoliciesKey(_GPOINFO *,ushort const *)
0x1800659b9  test    eax, eax
0x1800659bb  jnz     short loc_180065A14
0x1800659bd  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x1800659c4  jz      loc_180065AEB
0x1800659ca  mov     rsi, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800659d1  test    rsi, rsi
0x1800659d4  jz      short loc_1800659E8
0x1800659d6  call    cs:__imp_GetLastError
0x1800659dc  lea     rdx, aResetpoliciesF_1; "ResetPolicies: Failed to set permission"...
0x1800659e3  jmp     loc_180065AAD
0x1800659e8  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x1800659ef  jz      loc_180065AEB
0x1800659f5  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800659fc  jz      loc_180065AEB
0x180065a02  call    cs:__imp_GetLastError
0x180065a08  lea     rdx, aResetpoliciesF_1; "ResetPolicies: Failed to set permission"...
0x180065a0f  jmp     loc_180065ADE
0x180065a14  lea     rdx, aSoftwareMicros_26; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180065a1b  mov     rcx, rsi; struct _GPOINFO *
0x180065a1e  call    ?SetRegPermissionsOnPoliciesKey@@YAHPEAU_GPOINFO@@PEBG@Z; SetRegPermissionsOnPoliciesKey(_GPOINFO *,ushort const *)
0x180065a23  test    eax, eax
0x180065a25  jnz     short loc_180065A78
0x180065a27  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x180065a2e  jz      loc_180065AEB
0x180065a34  mov     rsi, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180065a3b  test    rsi, rsi
0x180065a3e  jz      short loc_180065A4F
0x180065a40  call    cs:__imp_GetLastError
0x180065a46  lea     rdx, aResetpoliciesF_3; "ResetPolicies: Failed to set permission"...
0x180065a4d  jmp     short loc_180065AAD
0x180065a4f  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x180065a56  jz      loc_180065AEB
0x180065a5c  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180065a63  jz      loc_180065AEB
0x180065a69  call    cs:__imp_GetLastError
0x180065a6f  lea     rdx, aResetpoliciesF_3; "ResetPolicies: Failed to set permission"...
0x180065a76  jmp     short loc_180065ADE
0x180065a78  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Policies"
0x180065a7f  mov     rcx, rsi; struct _GPOINFO *
0x180065a82  call    ?SetRegPermissionsOnPoliciesKey@@YAHPEAU_GPOINFO@@PEBG@Z; SetRegPermissionsOnPoliciesKey(_GPOINFO *,ushort const *)
0x180065a87  test    eax, eax
0x180065a89  jnz     short loc_180065AF3
0x180065a8b  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x180065a92  jz      short loc_180065AEB
0x180065a94  mov     rsi, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180065a9b  test    rsi, rsi
0x180065a9e  jz      short loc_180065ABF
0x180065aa0  call    cs:__imp_GetLastError
0x180065aa6  lea     rdx, aResetpoliciesF_4; "ResetPolicies: Failed to set permission"...
0x180065aad  mov     r8d, eax
0x180065ab0  mov     ecx, 2
0x180065ab5  mov     rax, rsi
0x180065ab8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065abd  jmp     short loc_180065AEB
0x180065abf  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x180065ac6  jz      short loc_180065AEB
0x180065ac8  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180065acf  jz      short loc_180065AEB
0x180065ad1  call    cs:__imp_GetLastError
0x180065ad7  lea     rdx, aResetpoliciesF_4; "ResetPolicies: Failed to set permission"...
0x180065ade  mov     r8d, eax
0x180065ae1  mov     ecx, 2; unsigned int
0x180065ae6  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180065aeb  mov     r14d, r15d
0x180065aee  jmp     loc_180066113
0x180065af3  call    ?IsDomainIncapableSystem@CSKU@@SAHXZ; CSKU::IsDomainIncapableSystem(void)
0x180065af8  mov     [rsp+78h+var_28], eax; int
0x180065afc  mov     [rsp+78h+var_30], r15d; int
0x180065b01  mov     dword ptr [rsp+78h+lpdwDisposition], r15d; int
0x180065b06  mov     [rsp+78h+phkResult], rdi; struct _REGHASHTABLE *
0x180065b0b  mov     [rsp+78h+lpSecurityAttributes], r15; struct _REGHASHTABLE *
0x180065b10  mov     qword ptr [rsp+78h+samDesired], r15; unsigned __int16 *
0x180065b15  mov     qword ptr [rsp+78h+dwOptions], r15; unsigned __int16 *
0x180065b1a  xor     r9d, r9d; void *
0x180065b1d  lea     r8, ?DeleteRegistryValue@@YAHPEAU_GPOINFO@@PEBG1KKPEAE11PEAU_REGHASHTABLE@@3@Z; int (*)(struct _GPOINFO *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int, unsigned __int8 *, const unsigned __int16 *, const unsigned __int16 *, struct _REGHASHTABLE *, struct _REGHASHTABLE *)
0x180065b24  mov     rdx, r14; unsigned __int16 *
0x180065b27  mov     rcx, rsi; struct _GPOINFO *
0x180065b2a  call    ?ParseRegistryFile@@YAHPEAU_GPOINFO@@PEBGP6AH011KKPEAE11PEAU_REGHASHTABLE@@3@ZPEAX1133HHH@Z; ParseRegistryFile(_GPOINFO *,ushort const *,int (*)(_GPOINFO *,ushort const *,ushort const *,ulong,ulong,uchar *,ushort const *,ushort const *,_REGHASHTABLE *,_REGHASHTABLE *),void *,ushort const *,ushort const *,_REGHASHTABLE *,_REGHASHTABLE *,int,int,int)
0x180065b2f  mov     edi, 2
0x180065b34  lea     r14d, [rdi-1]
0x180065b38  test    eax, eax
0x180065b3a  jnz     loc_180065CFF
0x180065b40  call    cs:__imp_GetLastError
0x180065b46  mov     ebx, eax
0x180065b48  mov     [rbp+var_14], eax
0x180065b4b  lea     r8d, [rdi+1Eh]
0x180065b4f  cmp     eax, r8d
0x180065b52  jz      loc_180065CBA
0x180065b58  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x180065b5f  jz      short loc_180065BA3
0x180065b61  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180065b68  test    rax, rax
0x180065b6b  jz      short loc_180065B80
0x180065b6d  mov     r8d, ebx
0x180065b70  lea     rdx, aResetpoliciesP; "ResetPolicies: ParseRegistryFile failed"...
0x180065b77  mov     ecx, edi
0x180065b79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065b7e  jmp     short loc_180065BA3
0x180065b80  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x180065b87  jz      short loc_180065BA3
0x180065b89  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180065b90  jz      short loc_180065BA3
0x180065b92  mov     r8d, ebx
0x180065b95  lea     rdx, aResetpoliciesP; "ResetPolicies: ParseRegistryFile failed"...
0x180065b9c  mov     ecx, edi; unsigned int
0x180065b9e  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180065ba3  test    [rsi], r14b
0x180065ba6  mov     rcx, r15
0x180065ba9  jnz     short loc_180065BAF
0x180065bab  mov     rcx, [rsi+8]; void *
0x180065baf  mov     r8, r13; unsigned __int16 *
0x180065bb2  mov     rdx, [rsi+28h]; HKEY
0x180065bb6  call    ?ForceGPRegDelnode@@YAKPEAXPEAUHKEY__@@PEBG@Z; ForceGPRegDelnode(void *,HKEY__ *,ushort const *)
0x180065bbb  mov     r8d, eax
0x180065bbe  lea     r12, aResetpoliciesF_0; "ResetPolicies: Failed to delete the reg"...
0x180065bc5  test    eax, eax
0x180065bc7  jz      short loc_180065C06
0x180065bc9  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x180065bd0  jz      short loc_180065C06
0x180065bd2  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180065bd9  test    rax, rax
0x180065bdc  jz      short loc_180065BEA
0x180065bde  mov     rdx, r12
0x180065be1  mov     ecx, edi
0x180065be3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065be8  jmp     short loc_180065C06
0x180065bea  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x180065bf1  jz      short loc_180065C06
0x180065bf3  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180065bfa  jz      short loc_180065C06
0x180065bfc  mov     rdx, r12; unsigned __int16 *
0x180065bff  mov     ecx, edi; unsigned int
0x180065c01  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180065c06  test    [rsi], r14b
0x180065c09  mov     rcx, r15
0x180065c0c  jnz     short loc_180065C12
0x180065c0e  mov     rcx, [rsi+8]; void *
0x180065c12  lea     r8, aSoftwareMicros_26; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180065c19  mov     rdx, [rsi+28h]; HKEY
0x180065c1d  call    ?ForceGPRegDelnode@@YAKPEAXPEAUHKEY__@@PEBG@Z; ForceGPRegDelnode(void *,HKEY__ *,ushort const *)
0x180065c22  mov     r8d, eax
0x180065c25  test    eax, eax
0x180065c27  jz      short loc_180065C66
0x180065c29  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x180065c30  jz      short loc_180065C66
0x180065c32  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180065c39  test    rax, rax
0x180065c3c  jz      short loc_180065C4A
0x180065c3e  mov     rdx, r12
0x180065c41  mov     ecx, edi
0x180065c43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065c48  jmp     short loc_180065C66
0x180065c4a  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x180065c51  jz      short loc_180065C66
0x180065c53  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180065c5a  jz      short loc_180065C66
0x180065c5c  mov     rdx, r12; unsigned __int16 *
0x180065c5f  mov     ecx, edi; unsigned int
0x180065c61  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180065c66  test    [rsi], r14b
0x180065c69  mov     rcx, r15
0x180065c6c  jnz     short loc_180065C72
0x180065c6e  mov     rcx, [rsi+8]; void *
0x180065c72  lea     r8, aSystemCurrentc; "System\\CurrentControlSet\\Policies"
0x180065c79  mov     rdx, [rsi+28h]; HKEY
0x180065c7d  call    ?ForceGPRegDelnode@@YAKPEAXPEAUHKEY__@@PEBG@Z; ForceGPRegDelnode(void *,HKEY__ *,ushort const *)
0x180065c82  mov     r8d, eax
0x180065c85  test    eax, eax
0x180065c87  jz      short loc_180065CFF
0x180065c89  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x180065c90  jz      short loc_180065CFF
0x180065c92  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180065c99  test    rax, rax
0x180065c9c  jz      short loc_180065CA3
0x180065c9e  mov     rdx, r12
0x180065ca1  jmp     short loc_180065CD6
0x180065ca3  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x180065caa  jz      short loc_180065CFF
0x180065cac  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180065cb3  jz      short loc_180065CFF
0x180065cb5  mov     rdx, r12
0x180065cb8  jmp     short loc_180065CF8
0x180065cba  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x180065cc1  jz      short loc_180065CFF
0x180065cc3  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180065cca  test    rax, rax
0x180065ccd  jz      short loc_180065CDF
0x180065ccf  lea     rdx, aResetpoliciesP_0; "ResetPolicies: ParseRegistryFile failed"...
0x180065cd6  mov     ecx, edi
0x180065cd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065cdd  jmp     short loc_180065CFF
0x180065cdf  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x180065ce6  jz      short loc_180065CFF
0x180065ce8  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180065cef  jz      short loc_180065CFF
0x180065cf1  lea     rdx, aResetpoliciesP_0; "ResetPolicies: ParseRegistryFile failed"...
0x180065cf8  mov     ecx, edi; unsigned int
0x180065cfa  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180065cff  lea     rax, [rbp+dwDisposition]
0x180065d03  mov     [rsp+78h+lpdwDisposition], rax; lpdwDisposition
0x180065d08  lea     rax, [rbp+hKey]
0x180065d0c  mov     [rsp+78h+phkResult], rax; phkResult
0x180065d11  mov     [rsp+78h+lpSecurityAttributes], r15; lpSecurityAttributes
0x180065d16  mov     [rsp+78h+samDesired], 20006h; samDesired
0x180065d1e  mov     [rsp+78h+dwOptions], r15d; dwOptions
0x180065d23  xor     r9d, r9d; lpClass
0x180065d26  xor     r8d, r8d; Reserved
0x180065d29  mov     rdx, r13; lpSubKey
0x180065d2c  mov     rcx, [rsi+28h]; hKey
0x180065d30  call    cs:__imp_RegCreateKeyExW
0x180065d36  mov     r8d, eax
0x180065d39  lea     r12, aResetpoliciesF; "ResetPolicies: Failed to secure reg key"...
0x180065d40  lea     r13, aResetpoliciesF_2; "ResetPolicies: Failed to create reg key"...
0x180065d47  test    eax, eax
0x180065d49  jnz     short loc_180065DC1
0x180065d4b  mov     rcx, [rbp+hKey]; hKey
0x180065d4f  call    cs:__imp_RegCloseKey
0x180065d55  test    [rsi], r14b
0x180065d58  mov     rcx, r15
0x180065d5b  jnz     short loc_180065D61
0x180065d5d  mov     rcx, [rsi+8]; void *
0x180065d61  mov     [rsp+78h+samDesired], r14d; int
0x180065d66  mov     [rsp+78h+dwOptions], r15d; int
0x180065d6b  xor     r9d, r9d; int
0x180065d6e  lea     r8, String1; "Software\\Policies"
0x180065d75  mov     rdx, [rsi+28h]; HKEY
0x180065d79  call    ?MakeRegKeySecure@@YAHPEAXPEAUHKEY__@@PEBGHHH@Z; MakeRegKeySecure(void *,HKEY__ *,ushort const *,int,int,int)
0x180065d7e  test    eax, eax
0x180065d80  jnz     short loc_180065DFE
0x180065d82  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x180065d89  jz      short loc_180065DFE
0x180065d8b  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180065d92  test    rax, rax
0x180065d95  jz      short loc_180065DA3
0x180065d97  mov     rdx, r12
0x180065d9a  mov     ecx, edi
0x180065d9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065da1  jmp     short loc_180065DFE
0x180065da3  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x180065daa  jz      short loc_180065DFE
0x180065dac  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180065db3  jz      short loc_180065DFE
0x180065db5  mov     rdx, r12; unsigned __int16 *
0x180065db8  mov     ecx, edi; unsigned int
0x180065dba  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180065dbf  jmp     short loc_180065DFE
0x180065dc1  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x180065dc8  jz      short loc_180065DFE
0x180065dca  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180065dd1  test    rax, rax
0x180065dd4  jz      short loc_180065DE2
0x180065dd6  mov     rdx, r13
0x180065dd9  mov     ecx, edi
0x180065ddb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065de0  jmp     short loc_180065DFE
0x180065de2  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x180065de9  jz      short loc_180065DFE
0x180065deb  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180065df2  jz      short loc_180065DFE
0x180065df4  mov     rdx, r13; unsigned __int16 *
0x180065df7  mov     ecx, edi; unsigned int
  ... truncated ...
```
