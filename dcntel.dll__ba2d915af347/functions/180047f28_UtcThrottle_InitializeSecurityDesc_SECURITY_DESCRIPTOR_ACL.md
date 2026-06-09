# UtcThrottle::InitializeSecurityDesc(_SECURITY_DESCRIPTOR &,_ACL * &)

- ea: `0x180047f28`
- end: `0x18004812a`
- name: `?InitializeSecurityDesc@UtcThrottle@@AEAAKAEAU_SECURITY_DESCRIPTOR@@AEAPEAU_ACL@@@Z`
- size: `514`
- prototype: `unsigned int(UtcThrottle *__hidden this, struct _SECURITY_DESCRIPTOR *, struct _ACL **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180047b84`

## callees

- `0x180008dc0`
- `0x180009f14`
- `0x180047f28`
- `0x18016796c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800480a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800480cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800480a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800480cd`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180048098`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180048098`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800480c3`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800480c3`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180047fee`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180047fee`
- `ntdll!RtlFreeSid` at `0x1800480ff`
- `ntdll!RtlFreeSid` at `0x1800480ff`
- `ntdll!RtlNtStatusToDosError` at `0x180047ffa`
- `ntdll!RtlNtStatusToDosError` at `0x180047ffa`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180048077`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180048077`

## string_xrefs

- `0x180048000`: `RtlAllocateAndInitializeSid failed [%d]`
- `0x1800480a8`: `InitializeSecurityDescriptor failed [%d]`
- `0x180048083`: `SetEntriesInAcl [%d]`
- `0x1800480e2`: `UtcThrottle::InitializeSecurityDesc`
- `0x1800480d3`: `SetSecurityDescriptorDacl failed [%d]`

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
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+68h] [rbp-98h] BYREF
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
0x180047f28  mov     [rsp-8+arg_0], rbx
0x180047f2d  push    rbp
0x180047f2e  push    rsi
0x180047f2f  push    rdi
0x180047f30  push    r14
0x180047f32  push    r15
0x180047f34  lea     rbp, [rsp-30h]
0x180047f39  sub     rsp, 130h
0x180047f40  mov     rax, cs:__security_cookie
0x180047f47  xor     rax, rsp
0x180047f4a  mov     [rbp+50h+var_30], rax
0x180047f4e  mov     rsi, r8
0x180047f51  lea     rcx, [rbp+50h+pListOfExplicitEntries.grfAccessMode]; void *
0x180047f55  mov     rdi, rdx
0x180047f58  xor     r14d, r14d
0x180047f5b  xor     edx, edx; Val
0x180047f5d  mov     [rbp+50h+pListOfExplicitEntries.grfAccessPermissions], r14d
0x180047f61  mov     r8d, 8Ch; Size
0x180047f67  call    memset_0
0x180047f6c  lea     rax, [rsp+150h+var_F0]
0x180047f71  mov     [rsp+150h+var_E0], 101h
0x180047f79  mov     [rsp+150h+Sid], rax; Sid
0x180047f7e  lea     ebx, [r14+2]
0x180047f82  mov     [rsp+150h+SubAuthority7], r14d; SubAuthority7
0x180047f87  lea     r8d, [r14+20h]; SubAuthority0
0x180047f8b  mov     [rsp+150h+SubAuthority6], r14d; SubAuthority6
0x180047f90  lea     rcx, [rsp+150h+IdentifierAuthority]; IdentifierAuthority
0x180047f95  mov     [rsp+150h+SubAuthority5], r14d; SubAuthority5
0x180047f9a  lea     r15d, [r14+1]
0x180047f9e  mov     [rsp+150h+SubAuthority4], r14d; SubAuthority4
0x180047fa3  mov     r9d, 220h; SubAuthority1
0x180047fa9  mov     [rsp+150h+SubAuthority3], r14d; SubAuthority3
0x180047fae  mov     dl, bl; SubAuthorityCount
0x180047fb0  mov     dword ptr [rsp+150h+SubAuthority2], r14d; SubAuthority2
0x180047fb5  mov     [rsp+150h+var_DC], 5000000h
0x180047fbd  mov     [rsp+150h+var_D8], 12h
0x180047fc5  mov     [rbp+50h+var_D0], 101h
0x180047fcc  mov     [rbp+50h+var_CC], 5000000h
0x180047fd3  mov     [rbp+50h+var_C8], 13h
0x180047fda  mov     dword ptr [rsp+150h+IdentifierAuthority.Value], r14d
0x180047fdf  mov     word ptr [rsp+150h+IdentifierAuthority.Value+4], 500h
0x180047fe6  mov     [rsi], r14
0x180047fe9  mov     [rsp+150h+var_F0], r14
0x180047fee  call    cs:__imp_RtlAllocateAndInitializeSid
0x180047ff4  test    eax, eax
0x180047ff6  jns     short loc_180048012
0x180047ff8  mov     ecx, eax; Status
0x180047ffa  call    cs:__imp_RtlNtStatusToDosError
0x180048000  lea     r9, aRtlallocateand; "RtlAllocateAndInitializeSid failed [%d]"
0x180048007  mov     r8d, 237h
0x18004800d  jmp     loc_1800480E0
0x180048012  mov     ecx, 100F0000h
0x180048017  mov     [rbp+50h+pListOfExplicitEntries.grfAccessMode], ebx
0x18004801a  mov     r10d, 3
0x180048020  mov     [rbp+50h+pListOfExplicitEntries.grfAccessPermissions], ecx
0x180048023  lea     rax, [rsp+150h+var_E0]
0x180048028  mov     [rbp+50h+var_90], ecx
0x18004802b  mov     [rbp+50h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x18004802f  lea     rdx, [rbp+50h+pListOfExplicitEntries]; pListOfExplicitEntries
0x180048033  lea     rax, [rbp+50h+var_D0]
0x180048037  mov     [rbp+50h+var_60], ecx
0x18004803a  mov     [rbp+50h+var_68], rax
0x18004803e  mov     r9, rsi; NewAcl
0x180048041  mov     rax, [rsp+150h+var_F0]
0x180048046  xor     r8d, r8d; OldAcl
0x180048049  mov     ecx, r10d; cCountOfExplicitEntries
0x18004804c  mov     [rbp+50h+var_38], rax
0x180048050  mov     [rbp+50h+pListOfExplicitEntries.grfInheritance], r10d
0x180048054  mov     [rbp+50h+pListOfExplicitEntries.Trustee.TrusteeForm], r14d
0x180048058  mov     [rbp+50h+pListOfExplicitEntries.Trustee.TrusteeType], ebx
0x18004805b  mov     [rbp+50h+var_8C], ebx
0x18004805e  mov     [rbp+50h+var_88], r10d
0x180048062  mov     [rbp+50h+var_74], r14d
0x180048066  mov     [rbp+50h+var_70], ebx
0x180048069  mov     [rbp+50h+var_5C], ebx
0x18004806c  mov     [rbp+50h+var_58], r10d
0x180048070  mov     [rbp+50h+var_44], r14d
0x180048074  mov     [rbp+50h+var_40], ebx
0x180048077  call    cs:__imp_SetEntriesInAclW
0x18004807d  mov     ebx, eax
0x18004807f  test    eax, eax
0x180048081  jz      short loc_180048092
0x180048083  lea     r9, aSetentriesinac_0; "SetEntriesInAcl [%d]"
0x18004808a  mov     r8d, 25Ah
0x180048090  jmp     short loc_1800480E2
0x180048092  mov     edx, r15d; dwRevision
0x180048095  mov     rcx, rdi; pSecurityDescriptor
0x180048098  call    cs:__imp_InitializeSecurityDescriptor
0x18004809e  test    eax, eax
0x1800480a0  jnz     short loc_1800480B7
0x1800480a2  call    cs:__imp_GetLastError
0x1800480a8  lea     r9, aInitializesecu; "InitializeSecurityDescriptor failed [%d"...
0x1800480af  mov     r8d, 261h
0x1800480b5  jmp     short loc_1800480E0
0x1800480b7  mov     r8, [rsi]; pDacl
0x1800480ba  xor     r9d, r9d; bDaclDefaulted
0x1800480bd  mov     edx, r15d; bDaclPresent
0x1800480c0  mov     rcx, rdi; pSecurityDescriptor
0x1800480c3  call    cs:__imp_SetSecurityDescriptorDacl
0x1800480c9  test    eax, eax
0x1800480cb  jnz     short loc_1800480F5
0x1800480cd  call    cs:__imp_GetLastError
0x1800480d3  lea     r9, aSetsecuritydes; "SetSecurityDescriptorDacl failed [%d]"
0x1800480da  mov     r8d, 26Ah
0x1800480e0  mov     ebx, eax
0x1800480e2  lea     rdx, aUtcthrottleIni_0; "UtcThrottle::InitializeSecurityDesc"
0x1800480e9  mov     dword ptr [rsp+150h+SubAuthority2], eax
0x1800480ed  mov     ecx, r15d
0x1800480f0  call    AslLogCallPrintf
0x1800480f5  mov     rcx, [rsp+150h+var_F0]; Sid
0x1800480fa  test    rcx, rcx
0x1800480fd  jz      short loc_180048105
0x1800480ff  call    cs:__imp_RtlFreeSid
0x180048105  mov     eax, ebx
0x180048107  mov     rcx, [rbp+50h+var_30]
0x18004810b  xor     rcx, rsp; StackCookie
0x18004810e  call    __security_check_cookie
0x180048113  mov     rbx, [rsp+150h+arg_0]
0x18004811b  add     rsp, 130h
0x180048122  pop     r15
0x180048124  pop     r14
0x180048126  pop     rdi
0x180048127  pop     rsi
0x180048128  pop     rbp
0x180048129  retn
```
