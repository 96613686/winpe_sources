# InitComSecurity(void)

- ea: `0x180002afc`
- end: `0x180002e2d`
- name: `?InitComSecurity@@YAJXZ`
- size: `817`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001e60`

## callees

- `0x180002a60`
- `0x180002afc`
- `0x180005010`

## import_xrefs

- `ADVAPI32!SetSecurityDescriptorGroup` at `0x180002c4d`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x180002c4d`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x180002c35`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x180002c35`
- `ADVAPI32!SetEntriesInAclA` at `0x180002c07`
- `ADVAPI32!SetEntriesInAclA` at `0x180002c07`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180002c69`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180002c69`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x180002b84`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x180002b84`
- `KERNEL32!GetLastError` at `0x180002b8e`
- `KERNEL32!GetLastError` at `0x180002b8e`
- `KERNEL32!LocalFree` at `0x180002d7d`
- `KERNEL32!LocalFree` at `0x180002d8b`
- `KERNEL32!LocalFree` at `0x180002d9a`
- `KERNEL32!LocalFree` at `0x180002d7d`
- `KERNEL32!LocalFree` at `0x180002d8b`
- `KERNEL32!LocalFree` at `0x180002d9a`
- `ole32!CoCreateInstance` at `0x180002d0f`
- `ole32!CoCreateInstance` at `0x180002d0f`
- `ole32!CoInitializeSecurity` at `0x180002ca6`
- `ole32!CoInitializeSecurity` at `0x180002ca6`
- `IisRTL!PuDbgPrint` at `0x180002ceb`
- `IisRTL!PuDbgPrint` at `0x180002ceb`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ` at `0x180002b77`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ` at `0x180002de5`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ` at `0x180002e16`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ` at `0x180002b77`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ` at `0x180002de5`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ` at `0x180002e16`

## string_xrefs

- `0x180002cca`: `CoInitializeSecurity failed hr=0x%08x\n`
- `0x180002cd8`: `InitComSecurity`
- `0x180002d4c`: `COMGLB_EXCEPTION_DONOT_HANDLE failed hr=0x%08x\n`

## pseudocode

```c
__int64 InitComSecurity(void)
{
  PSID v0; // rbx
  void *v1; // rdi
  signed int LastError; // eax
  int v3; // eax
  signed int v4; // eax
  HRESULT v5; // eax
  int v6; // eax
  CEtwTracer *v7; // rcx
  DWORD dwImpLevel[2]; // [rsp+28h] [rbp-51h]
  PACL NewAcl; // [rsp+50h] [rbp-29h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+58h] [rbp-21h] BYREF
  __int64 v12; // [rsp+78h] [rbp-1h]
  _EXPLICIT_ACCESS_A pListOfExplicitEntries; // [rsp+80h] [rbp+7h] BYREF
  HRESULT v14; // [rsp+E0h] [rbp+67h] BYREF
  PSID pOwner; // [rsp+E8h] [rbp+6Fh] BYREF
  void *v16; // [rsp+F0h] [rbp+77h] BYREF
  LPVOID ppv; // [rsp+F8h] [rbp+7Fh] BYREF

  v14 = 0;
  NewAcl = 0;
  v12 = 0;
  v0 = 0;
  v1 = 0;
  pOwner = 0;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  v16 = 0;
  ppv = 0;
  memset(&pListOfExplicitEntries, 0, sizeof(pListOfExplicitEntries));
  if ( *((_DWORD *)g_pEtwGlobalTracer + 2)
    && (*((_BYTE *)g_pEtwGlobalTracer + 40) & 1) != 0
    && *((_DWORD *)g_pEtwGlobalTracer + 11) >= 4u )
  {
    CEtwTracer::EtwTraceEvent((CEtwTracer *)g_pEtwGlobalTracer, (const struct _GUID *)IISAdminStatupGuid, 0x1Bu, 0, 0);
  }
  if ( !InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
    goto LABEL_6;
  v14 = AllocateAndCreateWellKnownSid(WinAuthenticatedUserSid, &v16);
  if ( v14 < 0 )
  {
    v1 = v16;
    goto LABEL_28;
  }
  v3 = AllocateAndCreateWellKnownSid(WinBuiltinAdministratorsSid, &pOwner);
  v1 = v16;
  v14 = v3;
  if ( v3 < 0 )
  {
LABEL_15:
    v0 = pOwner;
    goto LABEL_28;
  }
  pListOfExplicitEntries.grfAccessPermissions = 1;
  *(_QWORD *)&pListOfExplicitEntries.grfAccessMode = 2;
  pListOfExplicitEntries.Trustee.pMultipleTrustee = 0;
  *(_QWORD *)&pListOfExplicitEntries.Trustee.MultipleTrusteeOperation = 0;
  pListOfExplicitEntries.Trustee.TrusteeType = TRUSTEE_IS_GROUP;
  pListOfExplicitEntries.Trustee.ptstrName = (LPCH)v16;
  v4 = SetEntriesInAclA(1u, &pListOfExplicitEntries, 0, &NewAcl);
  if ( v4 )
  {
    if ( v4 > 0 )
      v4 = (unsigned __int16)v4 | 0x80070000;
    v14 = v4;
    goto LABEL_15;
  }
  v0 = pOwner;
  if ( !SetSecurityDescriptorOwner(pSecurityDescriptor, pOwner, 0)
    || !SetSecurityDescriptorGroup(pSecurityDescriptor, v0, 0)
    || !SetSecurityDescriptorDacl(pSecurityDescriptor, 1, NewAcl, 0) )
  {
LABEL_6:
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v14 = LastError;
    goto LABEL_28;
  }
  v5 = CoInitializeSecurity(pSecurityDescriptor, -1, 0, 0, 6u, 2u, 0, 0x3040u, 0);
  v14 = v5;
  if ( v5 >= 0 )
  {
    v14 = CoCreateInstance(&CLSID_GlobalOptions, 0, 1u, &IID_IGlobalOptions, &ppv);
    if ( v14 >= 0 )
    {
      v6 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)ppv + 24LL))(ppv, 1, 1);
      v14 = v6;
      if ( v6 < 0 && (g_dwDebugFlags & 0xF) != 0 )
      {
        dwImpLevel[0] = v6;
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\mb\\iisadmin\\ntsec.cxx",
          594,
          "InitComSecurity",
          "COMGLB_EXCEPTION_DONOT_HANDLE failed hr=0x%08x\n",
          *(_QWORD *)dwImpLevel);
      }
    }
  }
  else if ( (g_dwDebugFlags & 0xF) != 0 )
  {
    dwImpLevel[0] = v5;
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\mb\\iisadmin\\ntsec.cxx",
      576,
      "InitComSecurity",
      "CoInitializeSecurity failed hr=0x%08x\n",
      *(_QWORD *)dwImpLevel);
  }
LABEL_28:
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  if ( v0 )
    LocalFree(v0);
  if ( v1 )
    LocalFree(v1);
  if ( NewAcl )
  {
    LocalFree(NewAcl);
    NewAcl = 0;
  }
  v7 = (CEtwTracer *)g_pEtwGlobalTracer;
  if ( v14 < 0 )
  {
    if ( !*((_DWORD *)g_pEtwGlobalTracer + 2) )
      return (unsigned int)v14;
    if ( (*((_BYTE *)g_pEtwGlobalTracer + 40) & 1) != 0 && *((_DWORD *)g_pEtwGlobalTracer + 11) )
    {
      CEtwTracer::EtwTraceEvent(
        (CEtwTracer *)g_pEtwGlobalTracer,
        (const struct _GUID *)IISAdminStatupGuid,
        0x1Cu,
        &v14,
        4,
        0,
        0);
      v7 = (CEtwTracer *)g_pEtwGlobalTracer;
    }
  }
  if ( *((_DWORD *)v7 + 2) && (*((_BYTE *)v7 + 40) & 1) != 0 && *((_DWORD *)v7 + 11) >= 4u )
    CEtwTracer::EtwTraceEvent(v7, (const struct _GUID *)IISAdminStatupGuid, 0x1Du);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180002afc  push    rbp
0x180002afe  push    rbx
0x180002aff  push    rsi
0x180002b00  push    rdi
0x180002b01  push    r14
0x180002b03  lea     rbp, [rsp-37h]
0x180002b08  sub     rsp, 0B0h
0x180002b0f  mov     rcx, cs:?g_pEtwGlobalTracer@@3PEAVCEtwTracer@@EA; CEtwTracer * g_pEtwGlobalTracer
0x180002b16  xor     esi, esi
0x180002b18  xorps   xmm1, xmm1
0x180002b1b  mov     [rbp+57h+arg_0], esi
0x180002b1e  xor     eax, eax
0x180002b20  mov     [rbp+57h+NewAcl], rsi
0x180002b24  xorps   xmm0, xmm0
0x180002b27  mov     [rbp+57h+var_58], rax
0x180002b2b  lea     r14d, [rsi+1]
0x180002b2f  mov     ebx, esi
0x180002b31  mov     edi, esi
0x180002b33  mov     [rbp+57h+pOwner], rbx
0x180002b37  movups  [rbp+57h+pSecurityDescriptor], xmm0
0x180002b3b  mov     [rbp+57h+arg_10], rsi
0x180002b3f  movups  [rbp+57h+var_68], xmm0
0x180002b43  mov     [rbp+57h+ppv], rsi
0x180002b47  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], xmm1
0x180002b4b  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.Trustee.pMultipleTrustee], xmm1
0x180002b4f  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeType], xmm1
0x180002b53  cmp     [rcx+8], esi
0x180002b56  jz      short loc_180002B7D
0x180002b58  test    [rcx+28h], r14b
0x180002b5c  jz      short loc_180002B7D
0x180002b5e  cmp     dword ptr [rcx+2Ch], 4
0x180002b62  jb      short loc_180002B7D
0x180002b64  xor     r9d, r9d
0x180002b67  mov     qword ptr [rsp+0D0h+dwAuthnLevel], rsi
0x180002b6c  lea     r8d, [rsi+1Bh]
0x180002b70  lea     rdx, IISAdminStatupGuid
0x180002b77  call    cs:__imp_?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ; CEtwTracer::EtwTraceEvent(_GUID const *,ulong,...)
0x180002b7d  mov     edx, r14d; dwRevision
0x180002b80  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x180002b84  call    cs:__imp_InitializeSecurityDescriptor
0x180002b8a  test    eax, eax
0x180002b8c  jnz     short loc_180002BA8
0x180002b8e  call    cs:__imp_GetLastError
0x180002b94  test    eax, eax
0x180002b96  jle     short loc_180002BA0
0x180002b98  movzx   eax, ax
0x180002b9b  or      eax, 80070000h
0x180002ba0  mov     [rbp+57h+arg_0], eax
0x180002ba3  jmp     loc_180002D5C
0x180002ba8  lea     rdx, [rbp+57h+arg_10]; void **
0x180002bac  mov     ecx, 11h; WellKnownSidType
0x180002bb1  call    ?AllocateAndCreateWellKnownSid@@YAJW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z; AllocateAndCreateWellKnownSid(WELL_KNOWN_SID_TYPE,void * *)
0x180002bb6  mov     [rbp+57h+arg_0], eax
0x180002bb9  test    eax, eax
0x180002bbb  js      loc_180002D58
0x180002bc1  lea     rdx, [rbp+57h+pOwner]; void **
0x180002bc5  mov     ecx, 1Ah; WellKnownSidType
0x180002bca  call    ?AllocateAndCreateWellKnownSid@@YAJW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z; AllocateAndCreateWellKnownSid(WELL_KNOWN_SID_TYPE,void * *)
0x180002bcf  mov     rdi, [rbp+57h+arg_10]
0x180002bd3  mov     [rbp+57h+arg_0], eax
0x180002bd6  test    eax, eax
0x180002bd8  js      short loc_180002C1E
0x180002bda  lea     r9, [rbp+57h+NewAcl]; NewAcl
0x180002bde  mov     [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], r14d
0x180002be2  xor     r8d, r8d; OldAcl
0x180002be5  mov     qword ptr [rbp+57h+pListOfExplicitEntries.grfAccessMode], 2
0x180002bed  lea     rdx, [rbp+57h+pListOfExplicitEntries]; pListOfExplicitEntries
0x180002bf1  mov     [rbp+57h+pListOfExplicitEntries.Trustee.pMultipleTrustee], rsi
0x180002bf5  mov     ecx, r14d; cCountOfExplicitEntries
0x180002bf8  mov     qword ptr [rbp+57h+pListOfExplicitEntries.Trustee.MultipleTrusteeOperation], rsi
0x180002bfc  mov     [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeType], 2
0x180002c03  mov     [rbp+57h+pListOfExplicitEntries.Trustee.ptstrName], rdi
0x180002c07  call    cs:__imp_SetEntriesInAclA
0x180002c0d  test    eax, eax
0x180002c0f  jz      short loc_180002C27
0x180002c11  jle     short loc_180002C1B
0x180002c13  movzx   eax, ax
0x180002c16  or      eax, 80070000h
0x180002c1b  mov     [rbp+57h+arg_0], eax
0x180002c1e  mov     rbx, [rbp+57h+pOwner]
0x180002c22  jmp     loc_180002D5C
0x180002c27  mov     rbx, [rbp+57h+pOwner]
0x180002c2b  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x180002c2f  mov     rdx, rbx; pOwner
0x180002c32  xor     r8d, r8d; bOwnerDefaulted
0x180002c35  call    cs:__imp_SetSecurityDescriptorOwner
0x180002c3b  test    eax, eax
0x180002c3d  jz      loc_180002B8E
0x180002c43  xor     r8d, r8d; bGroupDefaulted
0x180002c46  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x180002c4a  mov     rdx, rbx; pGroup
0x180002c4d  call    cs:__imp_SetSecurityDescriptorGroup
0x180002c53  test    eax, eax
0x180002c55  jz      loc_180002B8E
0x180002c5b  mov     r8, [rbp+57h+NewAcl]; pDacl
0x180002c5f  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x180002c63  xor     r9d, r9d; bDaclDefaulted
0x180002c66  mov     edx, r14d; bDaclPresent
0x180002c69  call    cs:__imp_SetSecurityDescriptorDacl
0x180002c6f  test    eax, eax
0x180002c71  jz      loc_180002B8E
0x180002c77  mov     [rsp+0D0h+pReserved3], rsi; pReserved3
0x180002c7c  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecDesc
0x180002c80  mov     [rsp+0D0h+dwCapabilities], 3040h; dwCapabilities
0x180002c88  xor     r9d, r9d; pReserved1
0x180002c8b  mov     [rsp+0D0h+pAuthList], rsi; pAuthList
0x180002c90  xor     r8d, r8d; asAuthSvc
0x180002c93  mov     [rsp+0D0h+dwImpLevel], 2; dwImpLevel
0x180002c9b  or      edx, 0FFFFFFFFh; cAuthSvc
0x180002c9e  mov     [rsp+0D0h+dwAuthnLevel], 6; dwAuthnLevel
0x180002ca6  call    cs:__imp_CoInitializeSecurity
0x180002cac  mov     [rbp+57h+arg_0], eax
0x180002caf  test    eax, eax
0x180002cb1  jns     short loc_180002CF3
0x180002cb3  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180002cba  jz      loc_180002D5C
0x180002cc0  mov     [rsp+0D0h+dwImpLevel], eax
0x180002cc4  mov     r8d, 240h
0x180002cca  lea     rax, aCoinitializese; "CoInitializeSecurity failed hr=0x%08x\n"
0x180002cd1  mov     rcx, cs:g_pDebug
0x180002cd8  lea     r9, aInitcomsecurit; "InitComSecurity"
0x180002cdf  lea     rdx, aInetsrvIisMbIi_1; "inetsrv\\iis\\mb\\iisadmin\\ntsec.cxx"
0x180002ce6  mov     qword ptr [rsp+0D0h+dwAuthnLevel], rax
0x180002ceb  call    cs:__imp_PuDbgPrint
0x180002cf1  jmp     short loc_180002D5C
0x180002cf3  lea     rax, [rbp+57h+ppv]
0x180002cf7  mov     r8d, r14d; dwClsContext
0x180002cfa  lea     r9, IID_IGlobalOptions; riid
0x180002d01  mov     qword ptr [rsp+0D0h+dwAuthnLevel], rax; ppv
0x180002d06  xor     edx, edx; pUnkOuter
0x180002d08  lea     rcx, CLSID_GlobalOptions; rclsid
0x180002d0f  call    cs:__imp_CoCreateInstance
0x180002d15  mov     [rbp+57h+arg_0], eax
0x180002d18  test    eax, eax
0x180002d1a  js      short loc_180002D5C
0x180002d1c  mov     rcx, [rbp+57h+ppv]
0x180002d20  mov     r8, r14
0x180002d23  mov     edx, r14d
0x180002d26  mov     rax, [rcx]
0x180002d29  mov     rax, [rax+18h]
0x180002d2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d32  mov     [rbp+57h+arg_0], eax
0x180002d35  test    eax, eax
0x180002d37  jns     short loc_180002D5C
0x180002d39  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180002d40  jz      short loc_180002D5C
0x180002d42  mov     [rsp+0D0h+dwImpLevel], eax
0x180002d46  mov     r8d, 252h
0x180002d4c  lea     rax, aComglbExceptio; "COMGLB_EXCEPTION_DONOT_HANDLE failed hr"...
0x180002d53  jmp     loc_180002CD1
0x180002d58  mov     rdi, [rbp+57h+arg_10]
0x180002d5c  mov     rcx, [rbp+57h+ppv]
0x180002d60  test    rcx, rcx
0x180002d63  jz      short loc_180002D75
0x180002d65  mov     rax, [rcx]
0x180002d68  mov     rax, [rax+10h]
0x180002d6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d71  mov     [rbp+57h+ppv], rsi
0x180002d75  test    rbx, rbx
0x180002d78  jz      short loc_180002D83
0x180002d7a  mov     rcx, rbx; hMem
0x180002d7d  call    cs:__imp_LocalFree
0x180002d83  test    rdi, rdi
0x180002d86  jz      short loc_180002D91
0x180002d88  mov     rcx, rdi; hMem
0x180002d8b  call    cs:__imp_LocalFree
0x180002d91  mov     rcx, [rbp+57h+NewAcl]; hMem
0x180002d95  test    rcx, rcx
0x180002d98  jz      short loc_180002DA4
0x180002d9a  call    cs:__imp_LocalFree
0x180002da0  mov     [rbp+57h+NewAcl], rsi
0x180002da4  mov     rcx, cs:?g_pEtwGlobalTracer@@3PEAVCEtwTracer@@EA; CEtwTracer * g_pEtwGlobalTracer
0x180002dab  cmp     [rbp+57h+arg_0], esi
0x180002dae  jge     short loc_180002DF2
0x180002db0  cmp     [rcx+8], esi
0x180002db3  jz      short loc_180002E1C
0x180002db5  test    [rcx+28h], r14b
0x180002db9  jz      short loc_180002DF2
0x180002dbb  cmp     [rcx+2Ch], r14d
0x180002dbf  jb      short loc_180002DF2
0x180002dc1  mov     [rsp+0D0h+pAuthList], rsi
0x180002dc6  lea     r9, [rbp+57h+arg_0]
0x180002dca  mov     qword ptr [rsp+0D0h+dwImpLevel], rsi
0x180002dcf  lea     rdx, IISAdminStatupGuid
0x180002dd6  mov     r8d, 1Ch
0x180002ddc  mov     qword ptr [rsp+0D0h+dwAuthnLevel], 4
0x180002de5  call    cs:__imp_?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ; CEtwTracer::EtwTraceEvent(_GUID const *,ulong,...)
0x180002deb  mov     rcx, cs:?g_pEtwGlobalTracer@@3PEAVCEtwTracer@@EA; CEtwTracer * g_pEtwGlobalTracer
0x180002df2  cmp     [rcx+8], esi
0x180002df5  jz      short loc_180002E1C
0x180002df7  test    [rcx+28h], r14b
0x180002dfb  jz      short loc_180002E1C
0x180002dfd  cmp     dword ptr [rcx+2Ch], 4
0x180002e01  jb      short loc_180002E1C
0x180002e03  xor     r9d, r9d
0x180002e06  mov     qword ptr [rsp+0D0h+dwAuthnLevel], rsi
0x180002e0b  lea     rdx, IISAdminStatupGuid
0x180002e12  lea     r8d, [r9+1Dh]
0x180002e16  call    cs:__imp_?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ; CEtwTracer::EtwTraceEvent(_GUID const *,ulong,...)
0x180002e1c  mov     eax, [rbp+57h+arg_0]
0x180002e1f  add     rsp, 0B0h
0x180002e26  pop     r14
0x180002e28  pop     rdi
0x180002e29  pop     rsi
0x180002e2a  pop     rbx
0x180002e2b  pop     rbp
0x180002e2c  retn
```
