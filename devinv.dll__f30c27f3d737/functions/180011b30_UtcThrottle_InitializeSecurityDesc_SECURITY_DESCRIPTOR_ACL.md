# UtcThrottle::InitializeSecurityDesc(_SECURITY_DESCRIPTOR &,_ACL * &)

- ea: `0x180011b30`
- end: `0x180011d32`
- name: `?InitializeSecurityDesc@UtcThrottle@@AEAAKAEAU_SECURITY_DESCRIPTOR@@AEAPEAU_ACL@@@Z`
- size: `514`
- prototype: `unsigned int(UtcThrottle *__hidden this, struct _SECURITY_DESCRIPTOR *, struct _ACL **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001178c`

## callees

- `0x180005e40`
- `0x180006ec4`
- `0x180011b30`
- `0x180066c10`

## import_xrefs

- `ntdll!RtlFreeSid` at `0x180011d07`
- `ntdll!RtlFreeSid` at `0x180011d07`
- `ntdll!RtlNtStatusToDosError` at `0x180011c02`
- `ntdll!RtlNtStatusToDosError` at `0x180011c02`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180011bf6`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180011bf6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011caa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011cd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011caa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011cd5`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180011ca0`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180011ca0`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180011ccb`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180011ccb`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180011c7f`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180011c7f`

## string_xrefs

- `0x180011c08`: `RtlAllocateAndInitializeSid failed [%d]`
- `0x180011c8b`: `SetEntriesInAcl [%d]`
- `0x180011cb0`: `InitializeSecurityDescriptor failed [%d]`
- `0x180011cdb`: `SetSecurityDescriptorDacl failed [%d]`
- `0x180011cea`: `UtcThrottle::InitializeSecurityDesc`

## pseudocode

```c
__int64 __fastcall UtcThrottle::InitializeSecurityDesc(
        UtcThrottle *this,
        struct _SECURITY_DESCRIPTOR *a2,
        struct _ACL **a3)
{
  int v5; // eax
  ULONG LastError; // eax
  const char *v7; // r9
  __int64 v8; // r8
  ULONG v9; // ebx
  __int64 SubAuthority2; // [rsp+20h] [rbp-E0h]
  PSID Sid; // [rsp+60h] [rbp-A0h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+68h] [rbp-98h] BYREF
  _DWORD v14[4]; // [rsp+70h] [rbp-90h] BYREF
  _DWORD v15[4]; // [rsp+80h] [rbp-80h] BYREF
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+90h] [rbp-70h] BYREF
  int v17; // [rsp+C0h] [rbp-40h]
  int v18; // [rsp+C4h] [rbp-3Ch]
  int v19; // [rsp+C8h] [rbp-38h]
  int v20; // [rsp+DCh] [rbp-24h]
  int v21; // [rsp+E0h] [rbp-20h]
  _DWORD *v22; // [rsp+E8h] [rbp-18h]
  int v23; // [rsp+F0h] [rbp-10h]
  int v24; // [rsp+F4h] [rbp-Ch]
  int v25; // [rsp+F8h] [rbp-8h]
  int v26; // [rsp+10Ch] [rbp+Ch]
  int v27; // [rsp+110h] [rbp+10h]
  PSID v28; // [rsp+118h] [rbp+18h]

  pListOfExplicitEntries.grfAccessPermissions = 0;
  memset_0(&pListOfExplicitEntries.grfAccessMode, 0, 0x8Cu);
  v14[0] = 257;
  v14[1] = 83886080;
  v14[2] = 18;
  v15[0] = 257;
  v15[1] = 83886080;
  v15[2] = 19;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  *a3 = 0;
  Sid = 0;
  v5 = RtlAllocateAndInitializeSid(&IdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &Sid);
  if ( v5 < 0 )
  {
    LastError = RtlNtStatusToDosError(v5);
    v7 = "RtlAllocateAndInitializeSid failed [%d]";
    v8 = 567;
LABEL_9:
    v9 = LastError;
    goto LABEL_10;
  }
  pListOfExplicitEntries.grfAccessMode = SET_ACCESS;
  pListOfExplicitEntries.grfAccessPermissions = 269418496;
  v17 = 269418496;
  pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)v14;
  v23 = 269418496;
  v22 = v15;
  v28 = Sid;
  pListOfExplicitEntries.grfInheritance = 3;
  pListOfExplicitEntries.Trustee.TrusteeForm = TRUSTEE_IS_SID;
  pListOfExplicitEntries.Trustee.TrusteeType = TRUSTEE_IS_GROUP;
  v18 = 2;
  v19 = 3;
  v20 = 0;
  v21 = 2;
  v24 = 2;
  v25 = 3;
  v26 = 0;
  v27 = 2;
  LastError = SetEntriesInAclW(3u, &pListOfExplicitEntries, 0, a3);
  v9 = LastError;
  if ( !LastError )
  {
    if ( InitializeSecurityDescriptor(a2, 1u) )
    {
      if ( SetSecurityDescriptorDacl(a2, 1, *a3, 0) )
        goto LABEL_11;
      LastError = GetLastError();
      v7 = "SetSecurityDescriptorDacl failed [%d]";
      v8 = 618;
    }
    else
    {
      LastError = GetLastError();
      v7 = "InitializeSecurityDescriptor failed [%d]";
      v8 = 609;
    }
    goto LABEL_9;
  }
  v7 = "SetEntriesInAcl [%d]";
  v8 = 602;
LABEL_10:
  LODWORD(SubAuthority2) = LastError;
  AslLogCallPrintf(1, "UtcThrottle::InitializeSecurityDesc", v8, v7, SubAuthority2);
LABEL_11:
  if ( Sid )
    RtlFreeSid(Sid);
  return v9;
}

```

## disassembly

```asm
0x180011b30  mov     [rsp-8+arg_0], rbx
0x180011b35  push    rbp
0x180011b36  push    rsi
0x180011b37  push    rdi
0x180011b38  push    r14
0x180011b3a  push    r15
0x180011b3c  lea     rbp, [rsp-30h]
0x180011b41  sub     rsp, 130h
0x180011b48  mov     rax, cs:__security_cookie
0x180011b4f  xor     rax, rsp
0x180011b52  mov     [rbp+50h+var_30], rax
0x180011b56  mov     rsi, r8
0x180011b59  lea     rcx, [rbp+50h+pListOfExplicitEntries.grfAccessMode]; void *
0x180011b5d  mov     rdi, rdx
0x180011b60  xor     r14d, r14d
0x180011b63  xor     edx, edx; Val
0x180011b65  mov     [rbp+50h+pListOfExplicitEntries.grfAccessPermissions], r14d
0x180011b69  mov     r8d, 8Ch; Size
0x180011b6f  call    memset_0
0x180011b74  lea     rax, [rsp+150h+var_F0]
0x180011b79  mov     [rsp+150h+var_E0], 101h
0x180011b81  mov     [rsp+150h+Sid], rax; Sid
0x180011b86  lea     ebx, [r14+2]
0x180011b8a  mov     [rsp+150h+SubAuthority7], r14d; SubAuthority7
0x180011b8f  lea     r8d, [r14+20h]; SubAuthority0
0x180011b93  mov     [rsp+150h+SubAuthority6], r14d; SubAuthority6
0x180011b98  lea     rcx, [rsp+150h+IdentifierAuthority]; IdentifierAuthority
0x180011b9d  mov     [rsp+150h+SubAuthority5], r14d; SubAuthority5
0x180011ba2  lea     r15d, [r14+1]
0x180011ba6  mov     [rsp+150h+SubAuthority4], r14d; SubAuthority4
0x180011bab  mov     r9d, 220h; SubAuthority1
0x180011bb1  mov     [rsp+150h+SubAuthority3], r14d; SubAuthority3
0x180011bb6  mov     dl, bl; SubAuthorityCount
0x180011bb8  mov     dword ptr [rsp+150h+SubAuthority2], r14d; SubAuthority2
0x180011bbd  mov     [rsp+150h+var_DC], 5000000h
0x180011bc5  mov     [rsp+150h+var_D8], 12h
0x180011bcd  mov     [rbp+50h+var_D0], 101h
0x180011bd4  mov     [rbp+50h+var_CC], 5000000h
0x180011bdb  mov     [rbp+50h+var_C8], 13h
0x180011be2  mov     dword ptr [rsp+150h+IdentifierAuthority.Value], r14d
0x180011be7  mov     word ptr [rsp+150h+IdentifierAuthority.Value+4], 500h
0x180011bee  mov     [rsi], r14
0x180011bf1  mov     [rsp+150h+var_F0], r14
0x180011bf6  call    cs:__imp_RtlAllocateAndInitializeSid
0x180011bfc  test    eax, eax
0x180011bfe  jns     short loc_180011C1A
0x180011c00  mov     ecx, eax; Status
0x180011c02  call    cs:__imp_RtlNtStatusToDosError
0x180011c08  lea     r9, aRtlallocateand; "RtlAllocateAndInitializeSid failed [%d]"
0x180011c0f  mov     r8d, 237h
0x180011c15  jmp     loc_180011CE8
0x180011c1a  mov     ecx, 100F0000h
0x180011c1f  mov     [rbp+50h+pListOfExplicitEntries.grfAccessMode], ebx
0x180011c22  mov     r10d, 3
0x180011c28  mov     [rbp+50h+pListOfExplicitEntries.grfAccessPermissions], ecx
0x180011c2b  lea     rax, [rsp+150h+var_E0]
0x180011c30  mov     [rbp+50h+var_90], ecx
0x180011c33  mov     [rbp+50h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x180011c37  lea     rdx, [rbp+50h+pListOfExplicitEntries]; pListOfExplicitEntries
0x180011c3b  lea     rax, [rbp+50h+var_D0]
0x180011c3f  mov     [rbp+50h+var_60], ecx
0x180011c42  mov     [rbp+50h+var_68], rax
0x180011c46  mov     r9, rsi; NewAcl
0x180011c49  mov     rax, [rsp+150h+var_F0]
0x180011c4e  xor     r8d, r8d; OldAcl
0x180011c51  mov     ecx, r10d; cCountOfExplicitEntries
0x180011c54  mov     [rbp+50h+var_38], rax
0x180011c58  mov     [rbp+50h+pListOfExplicitEntries.grfInheritance], r10d
0x180011c5c  mov     [rbp+50h+pListOfExplicitEntries.Trustee.TrusteeForm], r14d
0x180011c60  mov     [rbp+50h+pListOfExplicitEntries.Trustee.TrusteeType], ebx
0x180011c63  mov     [rbp+50h+var_8C], ebx
0x180011c66  mov     [rbp+50h+var_88], r10d
0x180011c6a  mov     [rbp+50h+var_74], r14d
0x180011c6e  mov     [rbp+50h+var_70], ebx
0x180011c71  mov     [rbp+50h+var_5C], ebx
0x180011c74  mov     [rbp+50h+var_58], r10d
0x180011c78  mov     [rbp+50h+var_44], r14d
0x180011c7c  mov     [rbp+50h+var_40], ebx
0x180011c7f  call    cs:__imp_SetEntriesInAclW
0x180011c85  mov     ebx, eax
0x180011c87  test    eax, eax
0x180011c89  jz      short loc_180011C9A
0x180011c8b  lea     r9, aSetentriesinac; "SetEntriesInAcl [%d]"
0x180011c92  mov     r8d, 25Ah
0x180011c98  jmp     short loc_180011CEA
0x180011c9a  mov     edx, r15d; dwRevision
0x180011c9d  mov     rcx, rdi; pSecurityDescriptor
0x180011ca0  call    cs:__imp_InitializeSecurityDescriptor
0x180011ca6  test    eax, eax
0x180011ca8  jnz     short loc_180011CBF
0x180011caa  call    cs:__imp_GetLastError
0x180011cb0  lea     r9, aInitializesecu; "InitializeSecurityDescriptor failed [%d"...
0x180011cb7  mov     r8d, 261h
0x180011cbd  jmp     short loc_180011CE8
0x180011cbf  mov     r8, [rsi]; pDacl
0x180011cc2  xor     r9d, r9d; bDaclDefaulted
0x180011cc5  mov     edx, r15d; bDaclPresent
0x180011cc8  mov     rcx, rdi; pSecurityDescriptor
0x180011ccb  call    cs:__imp_SetSecurityDescriptorDacl
0x180011cd1  test    eax, eax
0x180011cd3  jnz     short loc_180011CFD
0x180011cd5  call    cs:__imp_GetLastError
0x180011cdb  lea     r9, aSetsecuritydes; "SetSecurityDescriptorDacl failed [%d]"
0x180011ce2  mov     r8d, 26Ah
0x180011ce8  mov     ebx, eax
0x180011cea  lea     rdx, aUtcthrottleIni_0; "UtcThrottle::InitializeSecurityDesc"
0x180011cf1  mov     dword ptr [rsp+150h+SubAuthority2], eax
0x180011cf5  mov     ecx, r15d
0x180011cf8  call    AslLogCallPrintf
0x180011cfd  mov     rcx, [rsp+150h+var_F0]; Sid
0x180011d02  test    rcx, rcx
0x180011d05  jz      short loc_180011D0D
0x180011d07  call    cs:__imp_RtlFreeSid
0x180011d0d  mov     eax, ebx
0x180011d0f  mov     rcx, [rbp+50h+var_30]
0x180011d13  xor     rcx, rsp; StackCookie
0x180011d16  call    __security_check_cookie
0x180011d1b  mov     rbx, [rsp+150h+arg_0]
0x180011d23  add     rsp, 130h
0x180011d2a  pop     r15
0x180011d2c  pop     r14
0x180011d2e  pop     rdi
0x180011d2f  pop     rsi
0x180011d30  pop     rbp
0x180011d31  retn
```
