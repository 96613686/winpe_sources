# DsRolepSaveUpgradeState

- ea: `0x180014524`
- end: `0x180014e28`
- name: `DsRolepSaveUpgradeState`
- size: `2308`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180006bf0`

## callees

- `0x180008f24`
- `0x180014344`
- `0x180014524`
- `0x1800150a8`
- `0x180015ff0`
- `0x180016374`
- `0x18001fe50`
- `0x1800201c4`
- `0x180020dbc`
- `0x18002c050`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800147b5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180014814`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800148d4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180014929`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180014a25`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180014a7a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180014b40`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180014b95`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180014c63`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180014cff`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800147b5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180014814`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800148d4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180014929`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180014a25`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180014a7a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180014b40`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180014b95`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180014c63`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180014cff`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800146e4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001477d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800146e4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001477d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180014711`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180014841`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180014899`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180014956`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180014aa7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180014bc2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180014711`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180014841`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180014899`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180014956`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180014aa7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180014bc2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001471e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014d93`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001471e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014d93`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800149e5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800149e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014752`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014752`
- `SAMSRV!SamIGetDefaultAdministratorName` at `0x1800145a2`
- `SAMSRV!SamIGetDefaultAdministratorName` at `0x1800145a2`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180014748`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180014748`
- `ntdll!RtlAllocateHeap` at `0x1800147d9`
- `ntdll!RtlAllocateHeap` at `0x1800148f8`
- `ntdll!RtlAllocateHeap` at `0x180014a49`
- `ntdll!RtlAllocateHeap` at `0x180014b64`
- `ntdll!RtlAllocateHeap` at `0x180014cca`
- `ntdll!RtlAllocateHeap` at `0x1800147d9`
- `ntdll!RtlAllocateHeap` at `0x1800148f8`
- `ntdll!RtlAllocateHeap` at `0x180014a49`
- `ntdll!RtlAllocateHeap` at `0x180014b64`
- `ntdll!RtlAllocateHeap` at `0x180014cca`
- `ntdll!RtlNtStatusToDosError` at `0x180014658`
- `ntdll!RtlNtStatusToDosError` at `0x1800146b1`
- `ntdll!RtlNtStatusToDosError` at `0x180014658`
- `ntdll!RtlNtStatusToDosError` at `0x1800146b1`
- `ntdll!RtlFreeHeap` at `0x180014674`
- `ntdll!RtlFreeHeap` at `0x18001468e`
- `ntdll!RtlFreeHeap` at `0x18001485b`
- `ntdll!RtlFreeHeap` at `0x180014988`
- `ntdll!RtlFreeHeap` at `0x180014ac1`
- `ntdll!RtlFreeHeap` at `0x180014bdc`
- `ntdll!RtlFreeHeap` at `0x180014d88`
- `ntdll!RtlFreeHeap` at `0x180014dfd`
- `ntdll!RtlFreeHeap` at `0x180014674`
- `ntdll!RtlFreeHeap` at `0x18001468e`
- `ntdll!RtlFreeHeap` at `0x18001485b`
- `ntdll!RtlFreeHeap` at `0x180014988`
- `ntdll!RtlFreeHeap` at `0x180014ac1`
- `ntdll!RtlFreeHeap` at `0x180014bdc`
- `ntdll!RtlFreeHeap` at `0x180014d88`
- `ntdll!RtlFreeHeap` at `0x180014dfd`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180014da3`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180014da3`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x1800146a9`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x1800146a9`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180014729`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180014729`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180014637`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180014637`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaSetInformationPolicy` at `0x180014650`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaSetInformationPolicy` at `0x180014650`
- `NTDSETUP!NtdsPrepareForDsUpgrade` at `0x1800145ee`
- `NTDSETUP!NtdsPrepareForDsUpgrade` at `0x1800145ee`

## string_xrefs

- `0x1800146d6`: `Security\`

## pseudocode

```c
__int64 __fastcall DsRolepSaveUpgradeState(STRSAFE_LPCWSTR pszSrc)
{
  int v2; // eax
  __int64 v3; // rdx
  __int64 v4; // rcx
  const char *v5; // rsi
  ULONG v6; // eax
  __int64 v7; // r14
  ULONG LastError; // ebx
  int v9; // eax
  NTSTATUS v10; // eax
  LSTATUS v11; // eax
  BYTE *v12; // rdi
  LSTATUS v13; // eax
  BYTE *Heap; // rdi
  __int64 v15; // rcx
  BYTE *v16; // rax
  __int64 v17; // rcx
  _BYTE *v18; // rax
  __int64 i; // rcx
  LSTATUS v20; // eax
  int v21; // r8d
  BYTE *v22; // rdi
  __int64 v23; // rax
  LSTATUS v24; // eax
  int v25; // r8d
  BYTE *v26; // rdi
  __int64 v27; // rax
  DWORD v28; // eax
  __int64 v29; // rcx
  __int64 v30; // rax
  unsigned __int64 v31; // rsi
  BYTE *v32; // rdi
  size_t v33; // rsi
  int v34; // r8d
  __int64 v35; // rax
  _BYTE *v36; // rax
  __int64 v37; // rcx
  DWORD nSize; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-C8h] BYREF
  PVOID v42; // [rsp+40h] [rbp-C0h] BYREF
  PVOID PolicyHandle; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  PVOID v45; // [rsp+58h] [rbp-A8h] BYREF
  __int128 Buffer; // [rsp+60h] [rbp-A0h] BYREF
  PVOID P; // [rsp+70h] [rbp-90h]
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-88h] BYREF
  WCHAR v49[20]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v50[528]; // [rsp+D0h] [rbp-30h] BYREF

  nSize = 260;
  PolicyHandle = 0;
  v45 = 0;
  phkResult = 0;
  P = 0;
  hKey = 0;
  Type = 0;
  Buffer = 0;
  v42 = 0;
  memset(&ObjectAttributes, 0, 44);
  v2 = SamIGetDefaultAdministratorName(v50, &nSize);
  if ( v2 >= 0 )
  {
    v5 = v50;
  }
  else
  {
    DsRolepLogPrintRoutine(4, "SamIGetDefaultAdministratorName failed with 0x%x\n", v2);
    v5 = L"Administrator";
  }
  DsRolepInitializeOperationHandle(v4, v3);
  DsRolepSetCurrentOperationStatus(28724, 0, 0);
  v6 = NtdsPrepareForDsUpgrade(&Buffer, &v42);
  v7 = -1;
  LastError = v6;
  if ( v6 )
  {
    DsRolepLogPrintRoutine(4, "NtdsPrepareForDsUpgrade failed with %lu\n", v6);
    goto LABEL_80;
  }
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v9 = LsaOpenPolicy(0, &ObjectAttributes, 0x207FFu, &PolicyHandle);
  if ( v9 >= 0 )
    v9 = LsaSetInformationPolicy(PolicyHandle, PolicyAccountDomainInformation, &Buffer);
  LastError = RtlNtStatusToDosError(v9);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *((PVOID *)&Buffer + 1));
  if ( LastError )
    goto LABEL_80;
  v10 = LsaQueryInformationPolicy(PolicyHandle, PolicyLsaServerRoleInformation, &v45);
  LastError = RtlNtStatusToDosError(v10);
  if ( LastError )
    goto LABEL_80;
  LastError = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Security\\", 0, 0x2001Fu, &hKey);
  if ( !LastError )
  {
    LastError = RegSetValueExW(hKey, L"Upgrade", 0, 4u, (const BYTE *)v45, 4u);
    RegCloseKey(hKey);
  }
  LsaFreeMemory(v45);
  if ( LastError )
    goto LABEL_80;
  nSize = 16;
  if ( !GetComputerNameW(v49, &nSize) )
  {
    LastError = GetLastError();
    goto LABEL_80;
  }
  LastError = RegOpenKeyExW(
                HKEY_LOCAL_MACHINE,
                L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon\\",
                0,
                0x2001Fu,
                &phkResult);
  if ( LastError )
    goto LABEL_80;
  nSize = 0;
  v11 = RegQueryValueExW(phkResult, L"AutoAdminLogon", 0, &Type, 0, &nSize);
  LastError = v11;
  if ( v11 )
  {
    if ( v11 != 2 )
      goto LABEL_80;
LABEL_24:
    LastError = RegSetValueExW(phkResult, L"AutoAdminLogon", 0, 1u, L"1", 4u);
    if ( LastError )
      goto LABEL_80;
    nSize = 0;
    v13 = RegQueryValueExW(phkResult, L"DefaultPassword", 0, &Type, 0, &nSize);
    LastError = v13;
    if ( v13 )
    {
      if ( v13 != 2 )
        goto LABEL_80;
    }
    else
    {
      Heap = (BYTE *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, nSize);
      if ( !Heap )
        goto LABEL_18;
      LastError = RegQueryValueExW(phkResult, L"DefaultPassword", 0, &Type, Heap, &nSize);
      if ( !LastError )
        LastError = RegSetValueExW(phkResult, L"DcpromoOld_DefaultPassword", 0, Type, Heap, nSize);
      v15 = nSize;
      v16 = Heap;
      if ( nSize )
      {
        do
        {
          *v16++ = 0;
          --v15;
        }
        while ( v15 );
      }
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
      if ( LastError )
        goto LABEL_80;
    }
    LastError = DsRolepSaveUpgradePasswordForAutoLogonAsLsaSecret(v42);
    if ( v42 )
    {
      v17 = -1;
      do
        ++v17;
      while ( *((_WORD *)v42 + v17) );
      v18 = v42;
      for ( i = 2 * v17; i; --i )
        *v18++ = 0;
    }
    if ( !LastError )
      LastError = RegDeleteValueW(phkResult, L"DefaultPassword");
    if ( LastError != 2 && LastError )
      goto LABEL_80;
    nSize = 0;
    v20 = RegQueryValueExW(phkResult, L"DefaultUserName", 0, &Type, 0, &nSize);
    LastError = v20;
    if ( v20 )
    {
      if ( v20 != 2 )
        goto LABEL_80;
    }
    else
    {
      v22 = (BYTE *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, nSize);
      if ( !v22 )
        goto LABEL_18;
      LastError = RegQueryValueExW(phkResult, L"DefaultUserName", 0, &Type, v22, &nSize);
      if ( !LastError )
        LastError = RegSetValueExW(phkResult, L"DcpromoOld_DefaultUserName", 0, Type, v22, nSize);
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v22);
      if ( LastError )
        goto LABEL_80;
    }
    v23 = -1;
    do
      ++v23;
    while ( *(_WORD *)&v5[2 * v23] );
    LastError = DsRolepRegSetValueEx((int)phkResult, (int)L"DefaultUserName", v21, 1, (int)v5, 2 * v23 + 2);
    if ( LastError )
      goto LABEL_80;
    nSize = 0;
    v24 = RegQueryValueExW(phkResult, L"DefaultDomainName", 0, &Type, 0, &nSize);
    LastError = v24;
    if ( v24 )
    {
      if ( v24 != 2 )
        goto LABEL_80;
    }
    else
    {
      v26 = (BYTE *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, nSize);
      if ( !v26 )
        goto LABEL_18;
      LastError = RegQueryValueExW(phkResult, L"DefaultDomainName", 0, &Type, v26, &nSize);
      if ( !LastError )
        LastError = RegSetValueExW(phkResult, L"DcpromoOld_DefaultDomainName", 0, Type, v26, nSize);
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v26);
      if ( LastError )
        goto LABEL_80;
    }
    v27 = -1;
    do
      ++v27;
    while ( v49[v27] );
    LastError = DsRolepRegSetValueEx((int)phkResult, (int)L"DefaultDomainName", v25, 1, (int)v49, 2 * v27 + 2);
    if ( LastError )
      goto LABEL_80;
    nSize = 0;
    LastError = RegQueryValueExW(phkResult, L"Userinit", 0, &Type, 0, &nSize);
    if ( !LastError )
    {
      v28 = nSize + 36;
      nSize += 36;
      if ( pszSrc )
      {
        v29 = v28;
        v30 = -1;
        do
          ++v30;
        while ( pszSrc[v30] );
        if ( ULongLongToULong(v29 + 2 * v30 + 18, &nSize) )
        {
          LastError = 534;
          goto LABEL_79;
        }
        v28 = nSize;
      }
      v31 = v28;
      v32 = (BYTE *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v28);
      if ( v32 )
      {
        LastError = RegQueryValueExW(phkResult, L"Userinit", 0, &Type, v32, &nSize);
        if ( !LastError )
        {
          v33 = v31 >> 1;
          StringCchCatW((STRSAFE_LPWSTR)v32, v33, L",dcpromo /upgrade");
          if ( pszSrc )
          {
            StringCchCatW((STRSAFE_LPWSTR)v32, v33, L"/answer:");
            StringCchCatW((STRSAFE_LPWSTR)v32, v33, pszSrc);
          }
          v35 = -1;
          do
            ++v35;
          while ( *(_WORD *)&v32[2 * v35] );
          DsRolepRegSetValueEx((int)phkResult, (int)L"Userinit", v34, Type, (int)v32, 2 * v35 + 2);
        }
      }
      else
      {
        LastError = 8;
      }
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v32);
    }
LABEL_79:
    RegCloseKey(phkResult);
    goto LABEL_80;
  }
  v12 = (BYTE *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, nSize);
  if ( !v12 )
  {
LABEL_18:
    LastError = 8;
    goto LABEL_80;
  }
  LastError = RegQueryValueExW(phkResult, L"AutoAdminLogon", 0, &Type, v12, &nSize);
  if ( !LastError )
    LastError = RegSetValueExW(phkResult, L"DcpromoOld_AutoAdminLogon", 0, Type, v12, nSize);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v12);
  if ( !LastError )
    goto LABEL_24;
LABEL_80:
  if ( PolicyHandle )
    LsaClose(PolicyHandle);
  if ( !LastError )
    LastError = DsRolepSetProductType(1);
  if ( v42 )
  {
    do
      ++v7;
    while ( *((_WORD *)v42 + v7) );
    v36 = v42;
    v37 = 2 * v7 + 2;
    if ( 2 * v7 != -2 )
    {
      do
      {
        *v36++ = 0;
        --v37;
      }
      while ( v37 );
    }
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v42);
  }
  return LastError;
}

```

## disassembly

```asm
0x180014524  push    rbp
0x180014526  push    rbx
0x180014527  push    rsi
0x180014528  push    rdi
0x180014529  push    r12
0x18001452b  push    r13
0x18001452d  push    r14
0x18001452f  push    r15
0x180014531  lea     rbp, [rsp-1F8h]
0x180014539  sub     rsp, 2F8h
0x180014540  mov     rax, cs:__security_cookie
0x180014547  xor     rax, rsp
0x18001454a  mov     [rbp+230h+var_50], rax
0x180014551  xor     r12d, r12d
0x180014554  mov     [rsp+330h+nSize], 104h
0x18001455c  xorps   xmm0, xmm0
0x18001455f  mov     [rsp+330h+PolicyHandle], r12
0x180014564  mov     r15, rcx
0x180014567  mov     [rsp+330h+var_2D8], r12
0x18001456c  xor     eax, eax
0x18001456e  mov     [rsp+330h+var_2F8], r12
0x180014573  movups  xmmword ptr [rbp+230h+ObjectAttributes.ObjectName], xmm0
0x180014577  lea     rdx, [rsp+330h+nSize]
0x18001457c  mov     [rsp+330h+P], rax
0x180014581  lea     rcx, [rbp+230h+var_260]
0x180014585  mov     [rsp+330h+hKey], r12
0x18001458a  movups  xmmword ptr [rbp+230h+ObjectAttributes+1Ch], xmm0
0x18001458e  mov     [rsp+330h+Type], r12d
0x180014593  movups  [rsp+330h+Buffer], xmm0
0x180014598  mov     [rsp+330h+var_2F0], r12
0x18001459d  movups  xmmword ptr [rsp+330h+ObjectAttributes.Length], xmm0
0x1800145a2  call    cs:__imp_SamIGetDefaultAdministratorName
0x1800145a8  lea     r13d, [r12+4]
0x1800145ad  test    eax, eax
0x1800145af  jns     short loc_1800145CC
0x1800145b1  mov     r8d, eax
0x1800145b4  lea     rdx, aSamigetdefault; "SamIGetDefaultAdministratorName failed "...
0x1800145bb  mov     ecx, r13d
0x1800145be  call    DsRolepLogPrintRoutine
0x1800145c3  lea     rsi, aAdministrator; "Administrator"
0x1800145ca  jmp     short loc_1800145D0
0x1800145cc  lea     rsi, [rbp+230h+var_260]
0x1800145d0  call    DsRolepInitializeOperationHandle
0x1800145d5  xor     r8d, r8d
0x1800145d8  xor     edx, edx
0x1800145da  mov     ecx, 7034h
0x1800145df  call    DsRolepSetCurrentOperationStatus
0x1800145e4  lea     rdx, [rsp+330h+var_2F0]
0x1800145e9  lea     rcx, [rsp+330h+Buffer]
0x1800145ee  call    cs:__imp_NtdsPrepareForDsUpgrade
0x1800145f4  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800145f8  mov     ebx, eax
0x1800145fa  test    eax, eax
0x1800145fc  jz      short loc_180014615
0x1800145fe  mov     r8d, eax
0x180014601  lea     rdx, aNtdspreparefor_2; "NtdsPrepareForDsUpgrade failed with %lu"...
0x180014608  mov     ecx, r13d
0x18001460b  call    DsRolepLogPrintRoutine
0x180014610  jmp     loc_180014D99
0x180014615  xorps   xmm0, xmm0
0x180014618  lea     r9, [rsp+330h+PolicyHandle]; PolicyHandle
0x18001461d  mov     r8d, 207FFh; DesiredAccess
0x180014623  lea     rdx, [rsp+330h+ObjectAttributes]; ObjectAttributes
0x180014628  xor     ecx, ecx; SystemName
0x18001462a  movups  xmmword ptr [rsp+330h+ObjectAttributes.Length], xmm0
0x18001462f  movups  xmmword ptr [rbp+230h+ObjectAttributes.ObjectName], xmm0
0x180014633  movups  xmmword ptr [rbp+230h+ObjectAttributes.SecurityDescriptor], xmm0
0x180014637  call    cs:__imp_LsaOpenPolicy
0x18001463d  test    eax, eax
0x18001463f  js      short loc_180014656
0x180014641  mov     rcx, [rsp+330h+PolicyHandle]; PolicyHandle
0x180014646  lea     r8, [rsp+330h+Buffer]; Buffer
0x18001464b  mov     edx, 5; InformationClass
0x180014650  call    cs:__imp_LsaSetInformationPolicy
0x180014656  mov     ecx, eax; Status
0x180014658  call    cs:__imp_RtlNtStatusToDosError
0x18001465e  mov     rcx, gs:60h
0x180014667  xor     edx, edx; Flags
0x180014669  mov     r8, [rsp+330h+P]; P
0x18001466e  mov     ebx, eax
0x180014670  mov     rcx, [rcx+30h]; HeapHandle
0x180014674  call    cs:__imp_RtlFreeHeap
0x18001467a  mov     rcx, gs:60h
0x180014683  xor     edx, edx; Flags
0x180014685  mov     r8, qword ptr [rsp+330h+Buffer+8]; P
0x18001468a  mov     rcx, [rcx+30h]; HeapHandle
0x18001468e  call    cs:__imp_RtlFreeHeap
0x180014694  test    ebx, ebx
0x180014696  jnz     loc_180014D99
0x18001469c  mov     rcx, [rsp+330h+PolicyHandle]; PolicyHandle
0x1800146a1  lea     r8, [rsp+330h+var_2D8]; Buffer
0x1800146a6  lea     edx, [rbx+6]; InformationClass
0x1800146a9  call    cs:__imp_LsaQueryInformationPolicy
0x1800146af  mov     ecx, eax; Status
0x1800146b1  call    cs:__imp_RtlNtStatusToDosError
0x1800146b7  mov     ebx, eax
0x1800146b9  test    eax, eax
0x1800146bb  jnz     loc_180014D99
0x1800146c1  lea     rax, [rsp+330h+hKey]
0x1800146c6  mov     edi, 2001Fh
0x1800146cb  mov     r9d, edi; samDesired
0x1800146ce  mov     [rsp+330h+phkResult], rax; phkResult
0x1800146d3  xor     r8d, r8d; ulOptions
0x1800146d6  lea     rdx, aSecurity; "Security\\"
0x1800146dd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800146e4  call    cs:__imp_RegOpenKeyExW
0x1800146ea  mov     ebx, eax
0x1800146ec  test    eax, eax
0x1800146ee  jnz     short loc_180014724
0x1800146f0  mov     rax, [rsp+330h+var_2D8]
0x1800146f5  lea     rdx, aUpgrade; "Upgrade"
0x1800146fc  mov     rcx, [rsp+330h+hKey]; hKey
0x180014701  mov     r9d, r13d; dwType
0x180014704  mov     [rsp+330h+cbData], r13d; cbData
0x180014709  xor     r8d, r8d; Reserved
0x18001470c  mov     [rsp+330h+phkResult], rax; lpData
0x180014711  call    cs:__imp_RegSetValueExW
0x180014717  mov     rcx, [rsp+330h+hKey]; hKey
0x18001471c  mov     ebx, eax
0x18001471e  call    cs:__imp_RegCloseKey
0x180014724  mov     rcx, [rsp+330h+var_2D8]; Buffer
0x180014729  call    cs:__imp_LsaFreeMemory
0x18001472f  test    ebx, ebx
0x180014731  jnz     loc_180014D99
0x180014737  lea     rdx, [rsp+330h+nSize]; nSize
0x18001473c  mov     [rsp+330h+nSize], 10h
0x180014744  lea     rcx, [rbp+230h+var_288]; lpBuffer
0x180014748  call    cs:__imp_GetComputerNameW
0x18001474e  test    eax, eax
0x180014750  jnz     short loc_18001475F
0x180014752  call    cs:__imp_GetLastError
0x180014758  mov     ebx, eax
0x18001475a  jmp     loc_180014D99
0x18001475f  lea     rax, [rsp+330h+var_2F8]
0x180014764  mov     r9d, edi; samDesired
0x180014767  xor     r8d, r8d; ulOptions
0x18001476a  mov     [rsp+330h+phkResult], rax; phkResult
0x18001476f  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180014776  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001477d  call    cs:__imp_RegOpenKeyExW
0x180014783  mov     ebx, eax
0x180014785  test    eax, eax
0x180014787  jnz     loc_180014D99
0x18001478d  mov     rcx, [rsp+330h+var_2F8]; hKey
0x180014792  lea     rax, [rsp+330h+nSize]
0x180014797  mov     qword ptr [rsp+330h+cbData], rax; lpcbData
0x18001479c  lea     r9, [rsp+330h+Type]; lpType
0x1800147a1  xor     r8d, r8d; lpReserved
0x1800147a4  mov     [rsp+330h+phkResult], r12; lpData
0x1800147a9  lea     rdx, aAutoadminlogon; "AutoAdminLogon"
0x1800147b0  mov     [rsp+330h+nSize], r12d
0x1800147b5  call    cs:__imp_RegQueryValueExW
0x1800147bb  mov     ebx, eax
0x1800147bd  test    eax, eax
0x1800147bf  jnz     loc_18001486A
0x1800147c5  mov     rcx, gs:60h
0x1800147ce  xor     edx, edx; Flags
0x1800147d0  mov     r8d, [rsp+330h+nSize]; Size
0x1800147d5  mov     rcx, [rcx+30h]; HeapHandle
0x1800147d9  call    cs:__imp_RtlAllocateHeap
0x1800147df  mov     rdi, rax
0x1800147e2  test    rax, rax
0x1800147e5  jnz     short loc_1800147F1
0x1800147e7  mov     ebx, 8
0x1800147ec  jmp     loc_180014D99
0x1800147f1  mov     rcx, [rsp+330h+var_2F8]; hKey
0x1800147f6  lea     rax, [rsp+330h+nSize]
0x1800147fb  mov     qword ptr [rsp+330h+cbData], rax; lpcbData
0x180014800  lea     r9, [rsp+330h+Type]; lpType
0x180014805  xor     r8d, r8d; lpReserved
0x180014808  mov     [rsp+330h+phkResult], rdi; lpData
0x18001480d  lea     rdx, aAutoadminlogon; "AutoAdminLogon"
0x180014814  call    cs:__imp_RegQueryValueExW
0x18001481a  mov     ebx, eax
0x18001481c  test    eax, eax
0x18001481e  jnz     short loc_180014849
0x180014820  mov     eax, [rsp+330h+nSize]
0x180014824  lea     rdx, aDcpromooldAuto; "DcpromoOld_AutoAdminLogon"
0x18001482b  mov     r9d, [rsp+330h+Type]; dwType
0x180014830  xor     r8d, r8d; Reserved
0x180014833  mov     rcx, [rsp+330h+var_2F8]; hKey
0x180014838  mov     [rsp+330h+cbData], eax; cbData
0x18001483c  mov     [rsp+330h+phkResult], rdi; lpData
0x180014841  call    cs:__imp_RegSetValueExW
0x180014847  mov     ebx, eax
0x180014849  mov     rcx, gs:60h
0x180014852  mov     r8, rdi; P
0x180014855  xor     edx, edx; Flags
0x180014857  mov     rcx, [rcx+30h]; HeapHandle
0x18001485b  call    cs:__imp_RtlFreeHeap
0x180014861  test    ebx, ebx
0x180014863  jz      short loc_180014873
0x180014865  jmp     loc_180014D99
0x18001486a  cmp     eax, 2
0x18001486d  jnz     loc_180014D99
0x180014873  mov     rcx, [rsp+330h+var_2F8]; hKey
0x180014878  lea     rax, Data; "1"
0x18001487f  mov     [rsp+330h+cbData], r13d; cbData
0x180014884  lea     rdx, aAutoadminlogon; "AutoAdminLogon"
0x18001488b  mov     r9d, 1; dwType
0x180014891  mov     [rsp+330h+phkResult], rax; lpData
0x180014896  xor     r8d, r8d; Reserved
0x180014899  call    cs:__imp_RegSetValueExW
0x18001489f  mov     ebx, eax
0x1800148a1  test    eax, eax
0x1800148a3  jnz     loc_180014D99
0x1800148a9  mov     rcx, [rsp+330h+var_2F8]; hKey
0x1800148ae  lea     rax, [rsp+330h+nSize]
0x1800148b3  mov     qword ptr [rsp+330h+cbData], rax; lpcbData
0x1800148b8  lea     r13, aDefaultpasswor; "DefaultPassword"
0x1800148bf  mov     rdx, r13; lpValueName
0x1800148c2  mov     [rsp+330h+phkResult], r12; lpData
0x1800148c7  lea     r9, [rsp+330h+Type]; lpType
0x1800148cc  mov     [rsp+330h+nSize], r12d
0x1800148d1  xor     r8d, r8d; lpReserved
0x1800148d4  call    cs:__imp_RegQueryValueExW
0x1800148da  mov     ebx, eax
0x1800148dc  test    eax, eax
0x1800148de  jnz     loc_180014997
0x1800148e4  mov     rcx, gs:60h
0x1800148ed  xor     edx, edx; Flags
0x1800148ef  mov     r8d, [rsp+330h+nSize]; Size
0x1800148f4  mov     rcx, [rcx+30h]; HeapHandle
0x1800148f8  call    cs:__imp_RtlAllocateHeap
0x1800148fe  mov     rdi, rax
0x180014901  test    rax, rax
0x180014904  jz      loc_1800147E7
0x18001490a  mov     rcx, [rsp+330h+var_2F8]; hKey
0x18001490f  lea     rax, [rsp+330h+nSize]
0x180014914  mov     qword ptr [rsp+330h+cbData], rax; lpcbData
0x180014919  lea     r9, [rsp+330h+Type]; lpType
0x18001491e  xor     r8d, r8d; lpReserved
0x180014921  mov     [rsp+330h+phkResult], rdi; lpData
0x180014926  mov     rdx, r13; lpValueName
0x180014929  call    cs:__imp_RegQueryValueExW
0x18001492f  mov     ebx, eax
0x180014931  test    eax, eax
0x180014933  jnz     short loc_18001495E
0x180014935  mov     eax, [rsp+330h+nSize]
0x180014939  lea     rdx, aDcpromooldDefa_0; "DcpromoOld_DefaultPassword"
0x180014940  mov     r9d, [rsp+330h+Type]; dwType
0x180014945  xor     r8d, r8d; Reserved
0x180014948  mov     rcx, [rsp+330h+var_2F8]; hKey
0x18001494d  mov     [rsp+330h+cbData], eax; cbData
0x180014951  mov     [rsp+330h+phkResult], rdi; lpData
0x180014956  call    cs:__imp_RegSetValueExW
0x18001495c  mov     ebx, eax
0x18001495e  mov     ecx, [rsp+330h+nSize]
0x180014962  mov     rax, rdi
0x180014965  test    rcx, rcx
0x180014968  jz      short loc_180014976
0x18001496a  mov     [rax], r12b
0x18001496d  inc     rax
0x180014970  sub     rcx, 1
0x180014974  jnz     short loc_18001496A
0x180014976  mov     rcx, gs:60h
0x18001497f  mov     r8, rdi; P
0x180014982  xor     edx, edx; Flags
0x180014984  mov     rcx, [rcx+30h]; HeapHandle
0x180014988  call    cs:__imp_RtlFreeHeap
0x18001498e  test    ebx, ebx
0x180014990  jz      short loc_1800149A0
0x180014992  jmp     loc_180014D99
0x180014997  cmp     eax, 2
0x18001499a  jnz     loc_180014D99
0x1800149a0  mov     rcx, [rsp+330h+var_2F0]
0x1800149a5  call    DsRolepSaveUpgradePasswordForAutoLogonAsLsaSecret
0x1800149aa  mov     ebx, eax
0x1800149ac  mov     rax, [rsp+330h+var_2F0]
0x1800149b1  test    rax, rax
0x1800149b4  jz      short loc_1800149D9
0x1800149b6  mov     rcx, r14
0x1800149b9  inc     rcx
0x1800149bc  cmp     [rax+rcx*2], r12w
0x1800149c1  jnz     short loc_1800149B9
0x1800149c3  mov     rax, [rsp+330h+var_2F0]
0x1800149c8  add     rcx, rcx
0x1800149cb  jz      short loc_1800149D9
0x1800149cd  mov     [rax], r12b
0x1800149d0  inc     rax
0x1800149d3  sub     rcx, 1
0x1800149d7  jnz     short loc_1800149CD
0x1800149d9  test    ebx, ebx
0x1800149db  jnz     short loc_1800149ED
0x1800149dd  mov     rcx, [rsp+330h+var_2F8]; hKey
0x1800149e2  mov     rdx, r13; lpValueName
0x1800149e5  call    cs:__imp_RegDeleteValueW
0x1800149eb  mov     ebx, eax
0x1800149ed  cmp     ebx, 2
0x1800149f0  jz      short loc_1800149FA
0x1800149f2  test    ebx, ebx
0x1800149f4  jnz     loc_180014D99
0x1800149fa  mov     rcx, [rsp+330h+var_2F8]; hKey
0x1800149ff  lea     rax, [rsp+330h+nSize]
0x180014a04  mov     qword ptr [rsp+330h+cbData], rax; lpcbData
0x180014a09  lea     r13, aDefaultusernam; "DefaultUserName"
0x180014a10  mov     rdx, r13; lpValueName
0x180014a13  mov     [rsp+330h+phkResult], r12; lpData
0x180014a18  lea     r9, [rsp+330h+Type]; lpType
0x180014a1d  mov     [rsp+330h+nSize], r12d
  ... truncated ...
```
