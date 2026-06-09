# FTP_SERVERP::InitializeCOMSecurity(void)

- ea: `0x180003f78`
- end: `0x1800041e7`
- name: `?InitializeCOMSecurity@FTP_SERVERP@@AEAAJXZ`
- size: `623`
- prototype: `__int64 __fastcall(FTP_SERVERP *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800029fc`

## callees

- `0x180003f78`
- `0x18004700f`
- `0x180047050`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180004017`
- `KERNEL32!GetLastError` at `0x180004192`
- `KERNEL32!GetLastError` at `0x180004017`
- `KERNEL32!GetLastError` at `0x180004192`
- `KERNEL32!LocalFree` at `0x1800041bb`
- `KERNEL32!LocalFree` at `0x1800041bb`
- `ADVAPI32!CreateWellKnownSid` at `0x180004047`
- `ADVAPI32!CreateWellKnownSid` at `0x180004063`
- `ADVAPI32!CreateWellKnownSid` at `0x180004082`
- `ADVAPI32!CreateWellKnownSid` at `0x180004047`
- `ADVAPI32!CreateWellKnownSid` at `0x180004063`
- `ADVAPI32!CreateWellKnownSid` at `0x180004082`
- `ADVAPI32!SetEntriesInAclW` at `0x1800040f1`
- `ADVAPI32!SetEntriesInAclW` at `0x1800040f1`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x180004116`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x180004116`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x180004130`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x180004130`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x18000414e`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x18000414e`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x18000400d`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x18000400d`
- `ole32!CoInitializeSecurity` at `0x180004188`
- `ole32!CoInitializeSecurity` at `0x180004188`

## pseudocode

```c
__int64 __fastcall FTP_SERVERP::InitializeCOMSecurity(FTP_SERVERP *this)
{
  signed int LastError; // eax
  int v2; // ebx
  signed int v3; // eax
  DWORD cbSid; // [rsp+50h] [rbp-B0h] BYREF
  PACL NewAcl; // [rsp+58h] [rbp-A8h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v8; // [rsp+80h] [rbp-80h]
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+90h] [rbp-70h] BYREF
  int v10; // [rsp+C0h] [rbp-40h]
  __int64 v11; // [rsp+C4h] [rbp-3Ch]
  __int64 v12; // [rsp+D0h] [rbp-30h]
  __int64 v13; // [rsp+D8h] [rbp-28h]
  int v14; // [rsp+E0h] [rbp-20h]
  _BYTE *v15; // [rsp+E8h] [rbp-18h]
  int v16; // [rsp+F0h] [rbp-10h]
  __int64 v17; // [rsp+F4h] [rbp-Ch]
  __int64 v18; // [rsp+100h] [rbp+0h]
  __int64 v19; // [rsp+108h] [rbp+8h]
  int v20; // [rsp+110h] [rbp+10h]
  _BYTE *v21; // [rsp+118h] [rbp+18h]
  _BYTE pSid[80]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v23[80]; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v24[80]; // [rsp+1C0h] [rbp+C0h] BYREF

  v8 = 0;
  pListOfExplicitEntries.grfAccessPermissions = 0;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  memset_0(&pListOfExplicitEntries.grfAccessMode, 0, 0x8Cu);
  NewAcl = 0;
  memset_0(pSid, 0, 0x48u);
  memset_0(v23, 0, 0x48u);
  memset_0(v24, 0, 0x48u);
  cbSid = 0;
  if ( !InitializeSecurityDescriptor(pSecurityDescriptor, 1u)
    || (cbSid = 72, !CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, pSid, &cbSid))
    || (cbSid = 72, !CreateWellKnownSid(WinSelfSid, 0, v23, &cbSid))
    || (cbSid = 72, !CreateWellKnownSid(WinLocalSystemSid, 0, v24, &cbSid)) )
  {
LABEL_2:
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_17;
  }
  pListOfExplicitEntries.Trustee.pMultipleTrustee = 0;
  pListOfExplicitEntries.grfAccessPermissions = 3;
  pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)pSid;
  *(_QWORD *)&pListOfExplicitEntries.Trustee.MultipleTrusteeOperation = 0;
  v15 = v23;
  *(_QWORD *)&pListOfExplicitEntries.grfAccessMode = 2;
  v21 = v24;
  pListOfExplicitEntries.Trustee.TrusteeType = TRUSTEE_IS_GROUP;
  v10 = 3;
  v11 = 2;
  v12 = 0;
  v13 = 0;
  v14 = 2;
  v16 = 3;
  v17 = 2;
  v18 = 0;
  v19 = 0;
  v20 = 2;
  if ( !SetEntriesInAclW(3u, &pListOfExplicitEntries, 0, &NewAcl) && NewAcl )
  {
    if ( SetSecurityDescriptorOwner(pSecurityDescriptor, pSid, 0)
      && SetSecurityDescriptorGroup(pSecurityDescriptor, pSid, 0)
      && SetSecurityDescriptorDacl(pSecurityDescriptor, 1, NewAcl, 0) )
    {
      v2 = CoInitializeSecurity(pSecurityDescriptor, -1, 0, 0, 6u, 2u, 0, 0x3040u, 0);
      goto LABEL_17;
    }
    goto LABEL_2;
  }
  v3 = GetLastError();
  v2 = v3;
  if ( v3 > 0 )
    v2 = (unsigned __int16)v3 | 0x80070000;
  if ( v2 >= 0 )
    v2 = -2147467259;
LABEL_17:
  if ( NewAcl )
    LocalFree(NewAcl);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180003f78  mov     [rsp-8+arg_0], rbx
0x180003f7d  mov     [rsp-8+arg_8], rdi
0x180003f82  push    rbp
0x180003f83  lea     rbp, [rsp-120h]
0x180003f8b  sub     rsp, 220h
0x180003f92  mov     rax, cs:__security_cookie
0x180003f99  xor     rax, rsp
0x180003f9c  mov     [rbp+120h+var_10], rax
0x180003fa3  xorps   xmm0, xmm0
0x180003fa6  lea     rcx, [rbp+120h+pListOfExplicitEntries.grfAccessMode]; void *
0x180003faa  xor     eax, eax
0x180003fac  xor     edi, edi
0x180003fae  xor     edx, edx; Val
0x180003fb0  mov     [rbp+120h+var_1A0], rax
0x180003fb4  mov     r8d, 8Ch; Size
0x180003fba  mov     [rbp+120h+pListOfExplicitEntries.grfAccessPermissions], edi
0x180003fbd  movups  [rsp+220h+pSecurityDescriptor], xmm0
0x180003fc2  movups  [rsp+220h+var_1B0], xmm0
0x180003fc7  call    memset_0
0x180003fcc  lea     ebx, [rdi+48h]
0x180003fcf  mov     [rsp+220h+NewAcl], rdi
0x180003fd4  mov     r8d, ebx; Size
0x180003fd7  lea     rcx, [rbp+120h+pSid]; void *
0x180003fdb  xor     edx, edx; Val
0x180003fdd  call    memset_0
0x180003fe2  mov     r8d, ebx; Size
0x180003fe5  lea     rcx, [rbp+120h+var_B0]; void *
0x180003fe9  xor     edx, edx; Val
0x180003feb  call    memset_0
0x180003ff0  mov     r8d, ebx; Size
0x180003ff3  lea     rcx, [rbp+120h+var_60]; void *
0x180003ffa  xor     edx, edx; Val
0x180003ffc  call    memset_0
0x180004001  lea     edx, [rdi+1]; dwRevision
0x180004004  mov     [rsp+220h+cbSid], edi
0x180004008  lea     rcx, [rsp+220h+pSecurityDescriptor]; pSecurityDescriptor
0x18000400d  call    cs:__imp_InitializeSecurityDescriptor
0x180004013  test    eax, eax
0x180004015  jnz     short loc_180004035
0x180004017  call    cs:__imp_GetLastError
0x18000401d  mov     ebx, eax
0x18000401f  test    eax, eax
0x180004021  jle     loc_1800041B1
0x180004027  movzx   ebx, ax
0x18000402a  or      ebx, 80070000h
0x180004030  jmp     loc_1800041B1
0x180004035  xor     edx, edx; DomainSid
0x180004037  mov     [rsp+220h+cbSid], ebx
0x18000403b  lea     r9, [rsp+220h+cbSid]; cbSid
0x180004040  lea     r8, [rbp+120h+pSid]; pSid
0x180004044  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x180004047  call    cs:__imp_CreateWellKnownSid
0x18000404d  test    eax, eax
0x18000404f  jz      short loc_180004017
0x180004051  xor     edx, edx; DomainSid
0x180004053  mov     [rsp+220h+cbSid], ebx
0x180004057  lea     r9, [rsp+220h+cbSid]; cbSid
0x18000405c  lea     r8, [rbp+120h+var_B0]; pSid
0x180004060  lea     ecx, [rdx+10h]; WellKnownSidType
0x180004063  call    cs:__imp_CreateWellKnownSid
0x180004069  test    eax, eax
0x18000406b  jz      short loc_180004017
0x18000406d  xor     edx, edx; DomainSid
0x18000406f  mov     [rsp+220h+cbSid], ebx
0x180004073  lea     r9, [rsp+220h+cbSid]; cbSid
0x180004078  lea     r8, [rbp+120h+var_60]; pSid
0x18000407f  lea     ecx, [rdx+16h]; WellKnownSidType
0x180004082  call    cs:__imp_CreateWellKnownSid
0x180004088  test    eax, eax
0x18000408a  jz      short loc_180004017
0x18000408c  mov     ecx, 3; cCountOfExplicitEntries
0x180004091  mov     [rbp+120h+pListOfExplicitEntries.Trustee.pMultipleTrustee], rdi
0x180004095  lea     rax, [rbp+120h+pSid]
0x180004099  mov     [rbp+120h+pListOfExplicitEntries.grfAccessPermissions], ecx
0x18000409c  mov     [rbp+120h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x1800040a0  lea     r9, [rsp+220h+NewAcl]; NewAcl
0x1800040a5  lea     rax, [rbp+120h+var_B0]
0x1800040a9  mov     qword ptr [rbp+120h+pListOfExplicitEntries.Trustee.MultipleTrusteeOperation], rdi
0x1800040ad  lea     ebx, [rcx-1]
0x1800040b0  mov     [rbp+120h+var_138], rax
0x1800040b4  lea     rax, [rbp+120h+var_60]
0x1800040bb  mov     qword ptr [rbp+120h+pListOfExplicitEntries.grfAccessMode], rbx
0x1800040bf  xor     r8d, r8d; OldAcl
0x1800040c2  mov     [rbp+120h+var_108], rax
0x1800040c6  lea     rdx, [rbp+120h+pListOfExplicitEntries]; pListOfExplicitEntries
0x1800040ca  mov     [rbp+120h+pListOfExplicitEntries.Trustee.TrusteeType], ebx
0x1800040cd  mov     [rbp+120h+var_160], ecx
0x1800040d0  mov     [rbp+120h+var_15C], rbx
0x1800040d4  mov     [rbp+120h+var_150], rdi
0x1800040d8  mov     [rbp+120h+var_148], rdi
0x1800040dc  mov     [rbp+120h+var_140], ebx
0x1800040df  mov     [rbp+120h+var_130], ecx
0x1800040e2  mov     [rbp+120h+var_12C], rbx
0x1800040e6  mov     [rbp+120h+var_120], rdi
0x1800040ea  mov     [rbp+120h+var_118], rdi
0x1800040ee  mov     [rbp+120h+var_110], ebx
0x1800040f1  call    cs:__imp_SetEntriesInAclW
0x1800040f7  test    eax, eax
0x1800040f9  jnz     loc_180004192
0x1800040ff  cmp     [rsp+220h+NewAcl], rdi
0x180004104  jz      loc_180004192
0x18000410a  xor     r8d, r8d; bOwnerDefaulted
0x18000410d  lea     rdx, [rbp+120h+pSid]; pOwner
0x180004111  lea     rcx, [rsp+220h+pSecurityDescriptor]; pSecurityDescriptor
0x180004116  call    cs:__imp_SetSecurityDescriptorOwner
0x18000411c  test    eax, eax
0x18000411e  jz      loc_180004017
0x180004124  xor     r8d, r8d; bGroupDefaulted
0x180004127  lea     rdx, [rbp+120h+pSid]; pGroup
0x18000412b  lea     rcx, [rsp+220h+pSecurityDescriptor]; pSecurityDescriptor
0x180004130  call    cs:__imp_SetSecurityDescriptorGroup
0x180004136  test    eax, eax
0x180004138  jz      loc_180004017
0x18000413e  mov     r8, [rsp+220h+NewAcl]; pDacl
0x180004143  lea     edx, [rbx-1]; bDaclPresent
0x180004146  xor     r9d, r9d; bDaclDefaulted
0x180004149  lea     rcx, [rsp+220h+pSecurityDescriptor]; pSecurityDescriptor
0x18000414e  call    cs:__imp_SetSecurityDescriptorDacl
0x180004154  test    eax, eax
0x180004156  jz      loc_180004017
0x18000415c  mov     [rsp+220h+pReserved3], rdi; pReserved3
0x180004161  lea     rcx, [rsp+220h+pSecurityDescriptor]; pSecDesc
0x180004166  mov     [rsp+220h+dwCapabilities], 3040h; dwCapabilities
0x18000416e  xor     r9d, r9d; pReserved1
0x180004171  mov     [rsp+220h+pAuthList], rdi; pAuthList
0x180004176  xor     r8d, r8d; asAuthSvc
0x180004179  mov     [rsp+220h+dwImpLevel], ebx; dwImpLevel
0x18000417d  or      edx, 0FFFFFFFFh; cAuthSvc
0x180004180  mov     [rsp+220h+dwAuthnLevel], 6; dwAuthnLevel
0x180004188  call    cs:__imp_CoInitializeSecurity
0x18000418e  mov     ebx, eax
0x180004190  jmp     short loc_1800041B1
0x180004192  call    cs:__imp_GetLastError
0x180004198  mov     ebx, eax
0x18000419a  test    eax, eax
0x18000419c  jle     short loc_1800041A7
0x18000419e  movzx   ebx, ax
0x1800041a1  or      ebx, 80070000h
0x1800041a7  test    ebx, ebx
0x1800041a9  mov     eax, 80004005h
0x1800041ae  cmovns  ebx, eax
0x1800041b1  mov     rcx, [rsp+220h+NewAcl]; hMem
0x1800041b6  test    rcx, rcx
0x1800041b9  jz      short loc_1800041C1
0x1800041bb  call    cs:__imp_LocalFree
0x1800041c1  mov     eax, ebx
0x1800041c3  mov     rcx, [rbp+120h+var_10]
0x1800041ca  xor     rcx, rsp; StackCookie
0x1800041cd  call    __security_check_cookie
0x1800041d2  lea     r11, [rsp+220h+var_s0]
0x1800041da  mov     rbx, [r11+10h]
0x1800041de  mov     rdi, [r11+18h]
0x1800041e2  mov     rsp, r11
0x1800041e5  pop     rbp
0x1800041e6  retn
```
