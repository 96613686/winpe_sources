# CDefragService::_InitComSecurity(void)

- ea: `0x18001bb0c`
- end: `0x18001be1f`
- name: `?_InitComSecurity@CDefragService@@AEAAJXZ`
- size: `787`
- prototype: `__int64 __fastcall(CDefragService *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001b6a8`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x18001a630`
- `0x18001bb0c`
- `0x180067b0a`
- `0x180067b30`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x18001bce7`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x18001bce7`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x18001bd1f`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x18001bd1f`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18001bbea`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18001bc26`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18001bbea`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18001bc26`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18001bd5c`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18001bd5c`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18001bba6`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18001bba6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001bde0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001bde0`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x18001bdb8`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x18001bdb8`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18001bc89`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18001bc89`

## string_xrefs

- `0x18001bb43`: `CDefragService::_InitComSecurity`

## pseudocode

```c
__int64 __fastcall CDefragService::_InitComSecurity(CDefragService *this)
{
  __int64 v1; // rdx
  __int64 v2; // rcx
  __int64 v3; // r8
  __int64 v4; // r9
  int LastFailureAsHRESULT; // ebx
  __int16 v6; // ax
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r9
  signed int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // r8
  __int64 v23; // r9
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // r8
  __int64 v27; // r9
  DWORD cbSid; // [rsp+50h] [rbp-B0h] BYREF
  PACL NewAcl; // [rsp+58h] [rbp-A8h] BYREF
  int v31; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v32; // [rsp+64h] [rbp-9Ch]
  __int16 v33; // [rsp+66h] [rbp-9Ah]
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+98h] [rbp-68h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v36; // [rsp+E8h] [rbp-18h]
  _BYTE pOwner[80]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE pSid[80]; // [rsp+140h] [rbp+40h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v31, "CDefragService::_InitComSecurity", 0x3C9u, 1u);
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  v36 = 0;
  memset(&pListOfExplicitEntries, 0, sizeof(pListOfExplicitEntries));
  NewAcl = 0;
  memset_0(pOwner, 0, 0x48u);
  memset_0(pSid, 0, 0x48u);
  cbSid = 0;
  if ( !InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v2, v1, v3, v4);
    v31 = LastFailureAsHRESULT;
    v6 = 979;
LABEL_3:
    v33 = v6;
    goto LABEL_21;
  }
  v31 = 0;
  v32 = 979;
  cbSid = 72;
  if ( !CreateWellKnownSid(WinAuthenticatedUserSid, 0, pSid, &cbSid) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v8, v7, v9, v10);
    v31 = LastFailureAsHRESULT;
    v6 = 983;
    goto LABEL_3;
  }
  v31 = 0;
  v32 = 983;
  cbSid = 72;
  if ( !CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, pOwner, &cbSid) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v12, v11, v13, v14);
    v31 = LastFailureAsHRESULT;
    v6 = 987;
    goto LABEL_3;
  }
  v31 = 0;
  v32 = 987;
  pListOfExplicitEntries.grfAccessPermissions = 11;
  *(_QWORD *)&pListOfExplicitEntries.grfAccessMode = 2;
  pListOfExplicitEntries.Trustee.pMultipleTrustee = 0;
  *(_QWORD *)&pListOfExplicitEntries.Trustee.MultipleTrusteeOperation = 0;
  pListOfExplicitEntries.Trustee.TrusteeType = TRUSTEE_IS_GROUP;
  pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)pSid;
  v15 = SetEntriesInAclW(1u, &pListOfExplicitEntries, 0, &NewAcl);
  LastFailureAsHRESULT = v15;
  if ( v15 > 0 )
    LastFailureAsHRESULT = (unsigned __int16)v15 | 0x80070000;
  v31 = LastFailureAsHRESULT;
  v6 = 1000;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_3;
  v32 = 1000;
  if ( !NewAcl )
  {
    LastFailureAsHRESULT = -2147024882;
    v31 = -2147024882;
    v33 = 1001;
    goto LABEL_23;
  }
  v31 = 0;
  v32 = 1001;
  if ( !SetSecurityDescriptorOwner(pSecurityDescriptor, pOwner, 0) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v17, v16, v18, v19);
    v31 = LastFailureAsHRESULT;
    v6 = 1004;
    goto LABEL_3;
  }
  v31 = 0;
  v32 = 1004;
  if ( !SetSecurityDescriptorGroup(pSecurityDescriptor, pOwner, 0) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v21, v20, v22, v23);
    v31 = LastFailureAsHRESULT;
    v6 = 1007;
    goto LABEL_3;
  }
  v31 = 0;
  v32 = 1007;
  if ( !SetSecurityDescriptorDacl(pSecurityDescriptor, 1, NewAcl, 0) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v25, v24, v26, v27);
    v31 = LastFailureAsHRESULT;
    v6 = 1010;
    goto LABEL_3;
  }
  v31 = 0;
  v32 = 1010;
  LastFailureAsHRESULT = CoInitializeSecurity(pSecurityDescriptor, -1, 0, 0, 6u, 2u, 0, 0x3040u, 0);
  v31 = LastFailureAsHRESULT;
  v6 = 1014;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_3;
  v32 = 1014;
LABEL_21:
  if ( NewAcl )
  {
    LocalFree(NewAcl);
    NewAcl = 0;
    LastFailureAsHRESULT = v31;
  }
LABEL_23:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v31);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x18001bb0c  mov     [rsp-8+arg_0], rbx
0x18001bb11  mov     [rsp-8+arg_8], rdi
0x18001bb16  push    rbp
0x18001bb17  lea     rbp, [rsp-0A0h]
0x18001bb1f  sub     rsp, 1A0h
0x18001bb26  mov     rax, cs:__security_cookie
0x18001bb2d  xor     rax, rsp
0x18001bb30  mov     [rbp+0A0h+var_10], rax
0x18001bb37  mov     r9d, 1; unsigned __int16
0x18001bb3d  mov     r8d, 3C9h; unsigned __int16
0x18001bb43  lea     rdx, aCdefragservice_8; "CDefragService::_InitComSecurity"
0x18001bb4a  lea     rcx, [rsp+1A0h+var_140]; this
0x18001bb4f  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001bb54  nop
0x18001bb55  xorps   xmm0, xmm0
0x18001bb58  xor     eax, eax
0x18001bb5a  movups  [rbp+0A0h+pSecurityDescriptor], xmm0
0x18001bb5e  movups  [rbp+0A0h+var_C8], xmm0
0x18001bb62  mov     [rbp+0A0h+var_B8], rax
0x18001bb66  xorps   xmm1, xmm1
0x18001bb69  movups  xmmword ptr [rbp+0A0h+pListOfExplicitEntries.grfAccessPermissions], xmm1
0x18001bb6d  movups  xmmword ptr [rbp+0A0h+pListOfExplicitEntries.Trustee.pMultipleTrustee], xmm1
0x18001bb71  movups  xmmword ptr [rbp+0A0h+pListOfExplicitEntries.Trustee.TrusteeType], xmm1
0x18001bb75  xor     edi, edi
0x18001bb77  mov     [rsp+1A0h+NewAcl], rdi
0x18001bb7c  lea     ebx, [rax+48h]
0x18001bb7f  mov     r8d, ebx; Size
0x18001bb82  xor     edx, edx; Val
0x18001bb84  lea     rcx, [rbp+0A0h+pOwner]; void *
0x18001bb88  call    memset_0
0x18001bb8d  mov     r8d, ebx; Size
0x18001bb90  xor     edx, edx; Val
0x18001bb92  lea     rcx, [rbp+0A0h+pSid]; void *
0x18001bb96  call    memset_0
0x18001bb9b  mov     [rsp+1A0h+cbSid], edi
0x18001bb9f  lea     edx, [rdi+1]; dwRevision
0x18001bba2  lea     rcx, [rbp+0A0h+pSecurityDescriptor]; pSecurityDescriptor
0x18001bba6  call    cs:__imp_InitializeSecurityDescriptor
0x18001bbac  test    eax, eax
0x18001bbae  jnz     short loc_18001BBCA
0x18001bbb0  call    GetLastFailureAsHRESULT
0x18001bbb5  mov     ebx, eax
0x18001bbb7  mov     [rsp+1A0h+var_140], eax
0x18001bbbb  mov     eax, 3D3h
0x18001bbc0  mov     [rsp+1A0h+var_13A], ax
0x18001bbc5  jmp     loc_18001BDD6
0x18001bbca  mov     [rsp+1A0h+var_140], edi
0x18001bbce  mov     eax, 3D3h
0x18001bbd3  mov     [rsp+1A0h+var_13C], ax
0x18001bbd8  mov     [rsp+1A0h+cbSid], ebx
0x18001bbdc  lea     r9, [rsp+1A0h+cbSid]; cbSid
0x18001bbe1  lea     r8, [rbp+0A0h+pSid]; pSid
0x18001bbe5  xor     edx, edx; DomainSid
0x18001bbe7  lea     ecx, [rdx+11h]; WellKnownSidType
0x18001bbea  call    cs:__imp_CreateWellKnownSid
0x18001bbf0  test    eax, eax
0x18001bbf2  jnz     short loc_18001BC06
0x18001bbf4  call    GetLastFailureAsHRESULT
0x18001bbf9  mov     ebx, eax
0x18001bbfb  mov     [rsp+1A0h+var_140], eax
0x18001bbff  mov     eax, 3D7h
0x18001bc04  jmp     short loc_18001BBC0
0x18001bc06  mov     [rsp+1A0h+var_140], edi
0x18001bc0a  mov     eax, 3D7h
0x18001bc0f  mov     [rsp+1A0h+var_13C], ax
0x18001bc14  mov     [rsp+1A0h+cbSid], ebx
0x18001bc18  lea     r9, [rsp+1A0h+cbSid]; cbSid
0x18001bc1d  lea     r8, [rbp+0A0h+pOwner]; pSid
0x18001bc21  xor     edx, edx; DomainSid
0x18001bc23  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x18001bc26  call    cs:__imp_CreateWellKnownSid
0x18001bc2c  test    eax, eax
0x18001bc2e  jnz     short loc_18001BC45
0x18001bc30  call    GetLastFailureAsHRESULT
0x18001bc35  mov     ebx, eax
0x18001bc37  mov     [rsp+1A0h+var_140], eax
0x18001bc3b  mov     eax, 3DBh
0x18001bc40  jmp     loc_18001BBC0
0x18001bc45  mov     [rsp+1A0h+var_140], edi
0x18001bc49  mov     eax, 3DBh
0x18001bc4e  mov     [rsp+1A0h+var_13C], ax
0x18001bc53  mov     [rbp+0A0h+pListOfExplicitEntries.grfAccessPermissions], 0Bh
0x18001bc5a  mov     qword ptr [rbp+0A0h+pListOfExplicitEntries.grfAccessMode], 2
0x18001bc62  mov     [rbp+0A0h+pListOfExplicitEntries.Trustee.pMultipleTrustee], rdi
0x18001bc66  mov     qword ptr [rbp+0A0h+pListOfExplicitEntries.Trustee.MultipleTrusteeOperation], rdi
0x18001bc6a  mov     [rbp+0A0h+pListOfExplicitEntries.Trustee.TrusteeType], 2
0x18001bc71  lea     rax, [rbp+0A0h+pSid]
0x18001bc75  mov     [rbp+0A0h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x18001bc79  lea     r9, [rsp+1A0h+NewAcl]; NewAcl
0x18001bc7e  xor     r8d, r8d; OldAcl
0x18001bc81  lea     rdx, [rbp+0A0h+pListOfExplicitEntries]; pListOfExplicitEntries
0x18001bc85  lea     ecx, [r8+1]; cCountOfExplicitEntries
0x18001bc89  call    cs:__imp_SetEntriesInAclW
0x18001bc8f  mov     ebx, eax
0x18001bc91  test    eax, eax
0x18001bc93  jle     short loc_18001BC9E
0x18001bc95  movzx   ebx, ax
0x18001bc98  or      ebx, 80070000h
0x18001bc9e  mov     [rsp+1A0h+var_140], ebx
0x18001bca2  mov     eax, 3E8h
0x18001bca7  test    ebx, ebx
0x18001bca9  js      loc_18001BBC0
0x18001bcaf  mov     [rsp+1A0h+var_13C], ax
0x18001bcb4  mov     eax, 3E9h
0x18001bcb9  cmp     [rsp+1A0h+NewAcl], rdi
0x18001bcbe  jnz     short loc_18001BCD3
0x18001bcc0  mov     ebx, 8007000Eh
0x18001bcc5  mov     [rsp+1A0h+var_140], ebx
0x18001bcc9  mov     [rsp+1A0h+var_13A], ax
0x18001bcce  jmp     loc_18001BDEF
0x18001bcd3  mov     [rsp+1A0h+var_140], edi
0x18001bcd7  mov     [rsp+1A0h+var_13C], ax
0x18001bcdc  xor     r8d, r8d; bOwnerDefaulted
0x18001bcdf  lea     rdx, [rbp+0A0h+pOwner]; pOwner
0x18001bce3  lea     rcx, [rbp+0A0h+pSecurityDescriptor]; pSecurityDescriptor
0x18001bce7  call    cs:__imp_SetSecurityDescriptorOwner
0x18001bced  test    eax, eax
0x18001bcef  jnz     short loc_18001BD06
0x18001bcf1  call    GetLastFailureAsHRESULT
0x18001bcf6  mov     ebx, eax
0x18001bcf8  mov     [rsp+1A0h+var_140], eax
0x18001bcfc  mov     eax, 3ECh
0x18001bd01  jmp     loc_18001BBC0
0x18001bd06  mov     [rsp+1A0h+var_140], edi
0x18001bd0a  mov     eax, 3ECh
0x18001bd0f  mov     [rsp+1A0h+var_13C], ax
0x18001bd14  xor     r8d, r8d; bGroupDefaulted
0x18001bd17  lea     rdx, [rbp+0A0h+pOwner]; pGroup
0x18001bd1b  lea     rcx, [rbp+0A0h+pSecurityDescriptor]; pSecurityDescriptor
0x18001bd1f  call    cs:__imp_SetSecurityDescriptorGroup
0x18001bd25  test    eax, eax
0x18001bd27  jnz     short loc_18001BD3E
0x18001bd29  call    GetLastFailureAsHRESULT
0x18001bd2e  mov     ebx, eax
0x18001bd30  mov     [rsp+1A0h+var_140], eax
0x18001bd34  mov     eax, 3EFh
0x18001bd39  jmp     loc_18001BBC0
0x18001bd3e  mov     [rsp+1A0h+var_140], edi
0x18001bd42  mov     eax, 3EFh
0x18001bd47  mov     [rsp+1A0h+var_13C], ax
0x18001bd4c  xor     r9d, r9d; bDaclDefaulted
0x18001bd4f  mov     r8, [rsp+1A0h+NewAcl]; pDacl
0x18001bd54  lea     edx, [r9+1]; bDaclPresent
0x18001bd58  lea     rcx, [rbp+0A0h+pSecurityDescriptor]; pSecurityDescriptor
0x18001bd5c  call    cs:__imp_SetSecurityDescriptorDacl
0x18001bd62  test    eax, eax
0x18001bd64  jnz     short loc_18001BD7B
0x18001bd66  call    GetLastFailureAsHRESULT
0x18001bd6b  mov     ebx, eax
0x18001bd6d  mov     [rsp+1A0h+var_140], eax
0x18001bd71  mov     eax, 3F2h
0x18001bd76  jmp     loc_18001BBC0
0x18001bd7b  mov     [rsp+1A0h+var_140], edi
0x18001bd7f  mov     eax, 3F2h
0x18001bd84  mov     [rsp+1A0h+var_13C], ax
0x18001bd89  mov     [rsp+1A0h+pReserved3], rdi; pReserved3
0x18001bd8e  mov     [rsp+1A0h+dwCapabilities], 3040h; dwCapabilities
0x18001bd96  mov     [rsp+1A0h+pAuthList], rdi; pAuthList
0x18001bd9b  mov     [rsp+1A0h+dwImpLevel], 2; dwImpLevel
0x18001bda3  mov     [rsp+1A0h+dwAuthnLevel], 6; dwAuthnLevel
0x18001bdab  xor     r9d, r9d; pReserved1
0x18001bdae  xor     r8d, r8d; asAuthSvc
0x18001bdb1  or      edx, 0FFFFFFFFh; cAuthSvc
0x18001bdb4  lea     rcx, [rbp+0A0h+pSecurityDescriptor]; pSecDesc
0x18001bdb8  call    cs:__imp_CoInitializeSecurity
0x18001bdbe  mov     ebx, eax
0x18001bdc0  mov     [rsp+1A0h+var_140], eax
0x18001bdc4  test    eax, eax
0x18001bdc6  mov     eax, 3F6h
0x18001bdcb  js      loc_18001BBC0
0x18001bdd1  mov     [rsp+1A0h+var_13C], ax
0x18001bdd6  mov     rcx, [rsp+1A0h+NewAcl]; hMem
0x18001bddb  test    rcx, rcx
0x18001bdde  jz      short loc_18001BDEF
0x18001bde0  call    cs:__imp_LocalFree
0x18001bde6  mov     [rsp+1A0h+NewAcl], rdi
0x18001bdeb  mov     ebx, [rsp+1A0h+var_140]
0x18001bdef  lea     rcx, [rsp+1A0h+var_140]; this
0x18001bdf4  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001bdf9  mov     eax, ebx
0x18001bdfb  mov     rcx, [rbp+0A0h+var_10]
0x18001be02  xor     rcx, rsp; StackCookie
0x18001be05  call    __security_check_cookie
0x18001be0a  lea     r11, [rsp+1A0h+var_s0]
0x18001be12  mov     rbx, [r11+10h]
0x18001be16  mov     rdi, [r11+18h]
0x18001be1a  mov     rsp, r11
0x18001be1d  pop     rbp
0x18001be1e  retn
```
