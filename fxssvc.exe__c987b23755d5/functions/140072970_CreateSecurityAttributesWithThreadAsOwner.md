# CreateSecurityAttributesWithThreadAsOwner

- ea: `0x140072970`
- end: `0x140072e3b`
- name: `CreateSecurityAttributesWithThreadAsOwner`
- size: `1227`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400723b4`

## callees

- `0x140002c43`
- `0x140004b30`
- `0x140004b58`
- `0x140065d14`
- `0x140065dbc`
- `0x140072970`
- `0x140073418`
- `0x1400818b0`

## import_xrefs

- `ADVAPI32!SetSecurityDescriptorDacl` at `0x140072d7c`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x140072d7c`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x140072b31`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x140072b31`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140072bec`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140072c60`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140072bec`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140072c60`
- `ADVAPI32!SetEntriesInAclW` at `0x140072cfa`
- `ADVAPI32!SetEntriesInAclW` at `0x140072cfa`
- `ADVAPI32!FreeSid` at `0x140072d4d`
- `ADVAPI32!FreeSid` at `0x140072d62`
- `ADVAPI32!FreeSid` at `0x140072de9`
- `ADVAPI32!FreeSid` at `0x140072df9`
- `ADVAPI32!FreeSid` at `0x140072d4d`
- `ADVAPI32!FreeSid` at `0x140072d62`
- `ADVAPI32!FreeSid` at `0x140072de9`
- `ADVAPI32!FreeSid` at `0x140072df9`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x140072aaa`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x140072aaa`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x140072b78`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x140072b78`
- `KERNEL32!GetLastError` at `0x140072ad8`
- `KERNEL32!GetLastError` at `0x140072b1c`
- `KERNEL32!GetLastError` at `0x140072b5f`
- `KERNEL32!GetLastError` at `0x140072ba6`
- `KERNEL32!GetLastError` at `0x140072c1a`
- `KERNEL32!GetLastError` at `0x140072c8e`
- `KERNEL32!GetLastError` at `0x140072da2`
- `KERNEL32!GetLastError` at `0x140072ad8`
- `KERNEL32!GetLastError` at `0x140072b1c`
- `KERNEL32!GetLastError` at `0x140072b5f`
- `KERNEL32!GetLastError` at `0x140072ba6`
- `KERNEL32!GetLastError` at `0x140072c1a`
- `KERNEL32!GetLastError` at `0x140072c8e`
- `KERNEL32!GetLastError` at `0x140072da2`
- `KERNEL32!SetLastError` at `0x140072d38`
- `KERNEL32!SetLastError` at `0x140072d38`
- `KERNEL32!LocalFree` at `0x140072e0d`
- `KERNEL32!LocalFree` at `0x140072e0d`

## pseudocode

```c
_DWORD *CreateSecurityAttributesWithThreadAsOwner()
{
  _DWORD *v0; // rsi
  void *v2; // r14
  void *v3; // rax
  void *v4; // rdi
  CMapDeviceId *v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // r9
  DWORD LastError; // eax
  void *CurrentThreadSID; // rax
  DWORD v10; // eax
  DWORD v11; // ebx
  PSID v12; // [rsp+60h] [rbp-A0h] BYREF
  PSID pSid; // [rsp+68h] [rbp-98h] BYREF
  PACL NewAcl; // [rsp+70h] [rbp-90h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+78h] [rbp-88h] BYREF
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+80h] [rbp-80h] BYREF
  int v17; // [rsp+B0h] [rbp-50h]
  __int64 v18; // [rsp+B4h] [rbp-4Ch]
  int v19; // [rsp+CCh] [rbp-34h]
  int v20; // [rsp+D0h] [rbp-30h]
  PSID v21; // [rsp+D8h] [rbp-28h]
  int v22; // [rsp+E0h] [rbp-20h]
  __int64 v23; // [rsp+E4h] [rbp-1Ch]
  int v24; // [rsp+FCh] [rbp-4h]
  int v25; // [rsp+100h] [rbp+0h]
  PSID v26; // [rsp+108h] [rbp+8h]

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, WPP_db036311db36307996a98c23702218b2_Traceguids);
  }
  v12 = 0;
  pSid = 0;
  NewAcl = 0;
  pListOfExplicitEntries.grfAccessPermissions = 0;
  memset_0(&pListOfExplicitEntries.grfAccessMode, 0, 0x8Cu);
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  v0 = (_DWORD *)pMemAlloc(0x18u);
  if ( !v0 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, WPP_db036311db36307996a98c23702218b2_Traceguids, 24);
    }
    return 0;
  }
  v2 = 0;
  v3 = (void *)pMemAlloc(0x28u);
  v4 = v3;
  if ( !v3 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_63;
    }
    v6 = 58;
    v7 = 40;
LABEL_62:
    WPP_SF_d(*((_QWORD *)v5 + 2), v6, WPP_db036311db36307996a98c23702218b2_Traceguids, v7);
LABEL_63:
    pMemFree(v0);
    pMemFree(v4);
    pMemFree(v2);
    if ( v12 )
      FreeSid(v12);
    if ( pSid )
      FreeSid(pSid);
    if ( NewAcl )
      LocalFree(NewAcl);
    return 0;
  }
  *v0 = 24;
  v0[4] = 1;
  *((_QWORD *)v0 + 1) = v3;
  if ( !InitializeSecurityDescriptor(v3, 1u) )
  {
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_63;
    }
    LastError = GetLastError();
    v6 = 59;
    goto LABEL_61;
  }
  CurrentThreadSID = (void *)GetCurrentThreadSID();
  v2 = CurrentThreadSID;
  if ( !CurrentThreadSID )
  {
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_63;
    }
    LastError = GetLastError();
    v6 = 60;
    goto LABEL_61;
  }
  if ( !SetSecurityDescriptorOwner(v4, CurrentThreadSID, 0) )
  {
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_63;
    }
    LastError = GetLastError();
    v6 = 61;
    goto LABEL_61;
  }
  if ( !SetSecurityDescriptorGroup(v4, v2, 0) )
  {
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_63;
    }
    LastError = GetLastError();
    v6 = 62;
    goto LABEL_61;
  }
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x14u, 0, 0, 0, 0, 0, 0, 0, &pSid) )
  {
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_63;
    }
    LastError = GetLastError();
    v6 = 63;
    goto LABEL_61;
  }
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0xBu, 0, 0, 0, 0, 0, 0, 0, &v12) )
  {
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_63;
    }
    LastError = GetLastError();
    v6 = 64;
    goto LABEL_61;
  }
  v21 = pSid;
  pListOfExplicitEntries.grfAccessPermissions = 0x100000;
  v22 = 0x100000;
  *(_QWORD *)&pListOfExplicitEntries.grfAccessMode = 2;
  pListOfExplicitEntries.Trustee.TrusteeForm = TRUSTEE_IS_SID;
  pListOfExplicitEntries.Trustee.TrusteeType = TRUSTEE_IS_GROUP;
  pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)v2;
  v17 = 2031619;
  v18 = 2;
  v19 = 0;
  v20 = 2;
  v23 = 2;
  v24 = 0;
  v25 = 2;
  v26 = v12;
  v10 = SetEntriesInAclW(3u, &pListOfExplicitEntries, 0, &NewAcl);
  v11 = v10;
  if ( v10 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, WPP_db036311db36307996a98c23702218b2_Traceguids, v10);
    }
    SetLastError(v11);
    goto LABEL_63;
  }
  if ( v12 )
  {
    FreeSid(v12);
    v12 = 0;
  }
  if ( pSid )
  {
    FreeSid(pSid);
    pSid = 0;
  }
  if ( !SetSecurityDescriptorDacl(v4, 1, NewAcl, 0) )
  {
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_63;
    }
    LastError = GetLastError();
    v6 = 66;
LABEL_61:
    v5 = WPP_GLOBAL_Control;
    v7 = LastError;
    goto LABEL_62;
  }
  return v0;
}

```

## disassembly

```asm
0x140072970  push    rbp
0x140072972  push    rbx
0x140072973  push    rsi
0x140072974  push    rdi
0x140072975  push    r12
0x140072977  push    r13
0x140072979  push    r14
0x14007297b  push    r15
0x14007297d  lea     rbp, [rsp-28h]
0x140072982  sub     rsp, 128h
0x140072989  mov     rax, cs:__security_cookie
0x140072990  xor     rax, rsp
0x140072993  mov     [rbp+60h+var_50], rax
0x140072997  mov     rcx, cs:WPP_GLOBAL_Control
0x14007299e  lea     r13, WPP_GLOBAL_Control
0x1400729a5  lea     rbx, WPP_db036311db36307996a98c23702218b2_Traceguids
0x1400729ac  mov     r12d, 2
0x1400729b2  cmp     rcx, r13
0x1400729b5  jz      short loc_1400729D4
0x1400729b7  test    [rcx+1Ch], r12b
0x1400729bb  jz      short loc_1400729D4
0x1400729bd  cmp     byte ptr [rcx+19h], 5
0x1400729c1  jb      short loc_1400729D4
0x1400729c3  mov     rcx, [rcx+10h]
0x1400729c7  lea     edx, [r12+36h]
0x1400729cc  mov     r8, rbx
0x1400729cf  call    WPP_SF_
0x1400729d4  xor     r15d, r15d
0x1400729d7  lea     rcx, [rbp+60h+pListOfExplicitEntries.grfAccessMode]; void *
0x1400729db  xor     edx, edx; Val
0x1400729dd  mov     [rsp+160h+var_100], r15
0x1400729e2  mov     r8d, 8Ch; Size
0x1400729e8  mov     [rsp+160h+var_F8], r15
0x1400729ed  mov     [rsp+160h+NewAcl], r15
0x1400729f2  mov     [rbp+60h+pListOfExplicitEntries.grfAccessPermissions], r15d
0x1400729f6  call    memset_0
0x1400729fb  lea     edi, [r15+18h]
0x1400729ff  mov     dword ptr [rsp+160h+pIdentifierAuthority.Value], r15d
0x140072a04  mov     ecx, edi; dwBytes
0x140072a06  mov     word ptr [rsp+160h+pIdentifierAuthority.Value+4], 500h
0x140072a0d  call    pMemAlloc
0x140072a12  mov     rsi, rax
0x140072a15  test    rax, rax
0x140072a18  jnz     short loc_140072A4B
0x140072a1a  mov     rcx, cs:WPP_GLOBAL_Control
0x140072a21  cmp     rcx, r13
0x140072a24  jz      short loc_140072A44
0x140072a26  test    [rcx+1Ch], r12b
0x140072a2a  jz      short loc_140072A44
0x140072a2c  cmp     [rcx+19h], r12b
0x140072a30  jb      short loc_140072A44
0x140072a32  mov     rcx, [rcx+10h]
0x140072a36  lea     edx, [rdi+21h]
0x140072a39  mov     r9d, edi
0x140072a3c  mov     r8, rbx
0x140072a3f  call    WPP_SF_d
0x140072a44  xor     eax, eax
0x140072a46  jmp     loc_140072E1B
0x140072a4b  mov     ecx, 28h ; '('; dwBytes
0x140072a50  mov     r14, r15
0x140072a53  call    pMemAlloc
0x140072a58  mov     rdi, rax
0x140072a5b  test    rax, rax
0x140072a5e  jnz     short loc_140072A93
0x140072a60  mov     rcx, cs:WPP_GLOBAL_Control
0x140072a67  cmp     rcx, r13
0x140072a6a  jz      loc_140072DC7
0x140072a70  test    [rcx+1Ch], r12b
0x140072a74  jz      loc_140072DC7
0x140072a7a  cmp     [rcx+19h], r12b
0x140072a7e  jb      loc_140072DC7
0x140072a84  lea     edx, [rax+3Ah]
0x140072a87  mov     r8, rbx
0x140072a8a  lea     r9d, [rax+28h]
0x140072a8e  jmp     loc_140072DBE
0x140072a93  mov     eax, 1
0x140072a98  mov     dword ptr [rsi], 18h
0x140072a9e  mov     edx, eax; dwRevision
0x140072aa0  mov     [rsi+10h], eax
0x140072aa3  mov     rcx, rdi; pSecurityDescriptor
0x140072aa6  mov     [rsi+8], rdi
0x140072aaa  call    cs:__imp_InitializeSecurityDescriptor
0x140072ab0  test    eax, eax
0x140072ab2  jnz     short loc_140072AEB
0x140072ab4  mov     rax, cs:WPP_GLOBAL_Control
0x140072abb  cmp     rax, r13
0x140072abe  jz      loc_140072DC7
0x140072ac4  test    [rax+1Ch], r12b
0x140072ac8  jz      loc_140072DC7
0x140072ace  cmp     [rax+19h], r12b
0x140072ad2  jb      loc_140072DC7
0x140072ad8  call    cs:__imp_GetLastError
0x140072ade  mov     edx, 3Bh ; ';'
0x140072ae3  mov     r8, rbx
0x140072ae6  jmp     loc_140072DB4
0x140072aeb  call    GetCurrentThreadSID
0x140072af0  mov     r14, rax
0x140072af3  test    rax, rax
0x140072af6  jnz     short loc_140072B28
0x140072af8  mov     rcx, cs:WPP_GLOBAL_Control
0x140072aff  cmp     rcx, r13
0x140072b02  jz      loc_140072DC7
0x140072b08  test    [rcx+1Ch], r12b
0x140072b0c  jz      loc_140072DC7
0x140072b12  cmp     [rcx+19h], r12b
0x140072b16  jb      loc_140072DC7
0x140072b1c  call    cs:__imp_GetLastError
0x140072b22  lea     edx, [r14+3Ch]
0x140072b26  jmp     short loc_140072AE3
0x140072b28  xor     r8d, r8d; bOwnerDefaulted
0x140072b2b  mov     rdx, r14; pOwner
0x140072b2e  mov     rcx, rdi; pSecurityDescriptor
0x140072b31  call    cs:__imp_SetSecurityDescriptorOwner
0x140072b37  test    eax, eax
0x140072b39  jnz     short loc_140072B6F
0x140072b3b  mov     rax, cs:WPP_GLOBAL_Control
0x140072b42  cmp     rax, r13
0x140072b45  jz      loc_140072DC7
0x140072b4b  test    [rax+1Ch], r12b
0x140072b4f  jz      loc_140072DC7
0x140072b55  cmp     [rax+19h], r12b
0x140072b59  jb      loc_140072DC7
0x140072b5f  call    cs:__imp_GetLastError
0x140072b65  mov     edx, 3Dh ; '='
0x140072b6a  jmp     loc_140072AE3
0x140072b6f  xor     r8d, r8d; bGroupDefaulted
0x140072b72  mov     rdx, r14; pGroup
0x140072b75  mov     rcx, rdi; pSecurityDescriptor
0x140072b78  call    cs:__imp_SetSecurityDescriptorGroup
0x140072b7e  test    eax, eax
0x140072b80  jnz     short loc_140072BB6
0x140072b82  mov     rax, cs:WPP_GLOBAL_Control
0x140072b89  cmp     rax, r13
0x140072b8c  jz      loc_140072DC7
0x140072b92  test    [rax+1Ch], r12b
0x140072b96  jz      loc_140072DC7
0x140072b9c  cmp     [rax+19h], r12b
0x140072ba0  jb      loc_140072DC7
0x140072ba6  call    cs:__imp_GetLastError
0x140072bac  mov     edx, 3Eh ; '>'
0x140072bb1  jmp     loc_140072AE3
0x140072bb6  lea     rax, [rsp+160h+var_F8]
0x140072bbb  xor     r9d, r9d; nSubAuthority1
0x140072bbe  mov     [rsp+160h+pSid], rax; pSid
0x140072bc3  lea     rcx, [rsp+160h+pIdentifierAuthority]; pIdentifierAuthority
0x140072bc8  mov     [rsp+160h+nSubAuthority7], r15d; nSubAuthority7
0x140072bcd  mov     dl, 1; nSubAuthorityCount
0x140072bcf  mov     [rsp+160h+nSubAuthority6], r15d; nSubAuthority6
0x140072bd4  mov     [rsp+160h+nSubAuthority5], r15d; nSubAuthority5
0x140072bd9  lea     r8d, [r9+14h]; nSubAuthority0
0x140072bdd  mov     [rsp+160h+nSubAuthority4], r15d; nSubAuthority4
0x140072be2  mov     [rsp+160h+nSubAuthority3], r15d; nSubAuthority3
0x140072be7  mov     [rsp+160h+nSubAuthority2], r15d; nSubAuthority2
0x140072bec  call    cs:__imp_AllocateAndInitializeSid
0x140072bf2  test    eax, eax
0x140072bf4  jnz     short loc_140072C2A
0x140072bf6  mov     rax, cs:WPP_GLOBAL_Control
0x140072bfd  cmp     rax, r13
0x140072c00  jz      loc_140072DC7
0x140072c06  test    [rax+1Ch], r12b
0x140072c0a  jz      loc_140072DC7
0x140072c10  cmp     [rax+19h], r12b
0x140072c14  jb      loc_140072DC7
0x140072c1a  call    cs:__imp_GetLastError
0x140072c20  mov     edx, 3Fh ; '?'
0x140072c25  jmp     loc_140072AE3
0x140072c2a  lea     rax, [rsp+160h+var_100]
0x140072c2f  xor     r9d, r9d; nSubAuthority1
0x140072c32  mov     [rsp+160h+pSid], rax; pSid
0x140072c37  lea     rcx, [rsp+160h+pIdentifierAuthority]; pIdentifierAuthority
0x140072c3c  mov     [rsp+160h+nSubAuthority7], r15d; nSubAuthority7
0x140072c41  mov     dl, 1; nSubAuthorityCount
0x140072c43  mov     [rsp+160h+nSubAuthority6], r15d; nSubAuthority6
0x140072c48  mov     [rsp+160h+nSubAuthority5], r15d; nSubAuthority5
0x140072c4d  lea     r8d, [r9+0Bh]; nSubAuthority0
0x140072c51  mov     [rsp+160h+nSubAuthority4], r15d; nSubAuthority4
0x140072c56  mov     [rsp+160h+nSubAuthority3], r15d; nSubAuthority3
0x140072c5b  mov     [rsp+160h+nSubAuthority2], r15d; nSubAuthority2
0x140072c60  call    cs:__imp_AllocateAndInitializeSid
0x140072c66  test    eax, eax
0x140072c68  jnz     short loc_140072C9E
0x140072c6a  mov     rax, cs:WPP_GLOBAL_Control
0x140072c71  cmp     rax, r13
0x140072c74  jz      loc_140072DC7
0x140072c7a  test    [rax+1Ch], r12b
0x140072c7e  jz      loc_140072DC7
0x140072c84  cmp     [rax+19h], r12b
0x140072c88  jb      loc_140072DC7
0x140072c8e  call    cs:__imp_GetLastError
0x140072c94  mov     edx, 40h ; '@'
0x140072c99  jmp     loc_140072AE3
0x140072c9e  mov     rax, [rsp+160h+var_F8]
0x140072ca3  lea     r9, [rsp+160h+NewAcl]; NewAcl
0x140072ca8  mov     ecx, 100000h
0x140072cad  mov     [rbp+60h+var_88], rax
0x140072cb1  mov     rax, [rsp+160h+var_100]
0x140072cb6  lea     rdx, [rbp+60h+pListOfExplicitEntries]; pListOfExplicitEntries
0x140072cba  xor     r8d, r8d; OldAcl
0x140072cbd  mov     [rbp+60h+pListOfExplicitEntries.grfAccessPermissions], ecx
0x140072cc0  mov     [rbp+60h+var_80], ecx
0x140072cc3  mov     qword ptr [rbp+60h+pListOfExplicitEntries.grfAccessMode], r12
0x140072cc7  mov     [rbp+60h+pListOfExplicitEntries.Trustee.TrusteeForm], r15d
0x140072ccb  lea     ecx, [r8+3]; cCountOfExplicitEntries
0x140072ccf  mov     [rbp+60h+pListOfExplicitEntries.Trustee.TrusteeType], r12d
0x140072cd3  mov     [rbp+60h+pListOfExplicitEntries.Trustee.ptstrName], r14
0x140072cd7  mov     [rbp+60h+var_B0], 1F0003h
0x140072cde  mov     [rbp+60h+var_AC], r12
0x140072ce2  mov     [rbp+60h+var_94], r15d
0x140072ce6  mov     [rbp+60h+var_90], r12d
0x140072cea  mov     [rbp+60h+var_7C], r12
0x140072cee  mov     [rbp+60h+var_64], r15d
0x140072cf2  mov     [rbp+60h+var_60], r12d
0x140072cf6  mov     [rbp+60h+var_58], rax
0x140072cfa  call    cs:__imp_SetEntriesInAclW
0x140072d00  mov     ebx, eax
0x140072d02  test    eax, eax
0x140072d04  jz      short loc_140072D43
0x140072d06  mov     rcx, cs:WPP_GLOBAL_Control
0x140072d0d  cmp     rcx, r13
0x140072d10  jz      short loc_140072D36
0x140072d12  test    [rcx+1Ch], r12b
0x140072d16  jz      short loc_140072D36
0x140072d18  cmp     [rcx+19h], r12b
0x140072d1c  jb      short loc_140072D36
0x140072d1e  mov     rcx, [rcx+10h]
0x140072d22  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x140072d29  mov     edx, 41h ; 'A'
0x140072d2e  mov     r9d, eax
0x140072d31  call    WPP_SF_d
0x140072d36  mov     ecx, ebx; dwErrCode
0x140072d38  call    cs:__imp_SetLastError
0x140072d3e  jmp     loc_140072DC7
0x140072d43  mov     rcx, [rsp+160h+var_100]; pSid
0x140072d48  test    rcx, rcx
0x140072d4b  jz      short loc_140072D58
0x140072d4d  call    cs:__imp_FreeSid
0x140072d53  mov     [rsp+160h+var_100], r15
0x140072d58  mov     rcx, [rsp+160h+var_F8]; pSid
0x140072d5d  test    rcx, rcx
0x140072d60  jz      short loc_140072D6D
0x140072d62  call    cs:__imp_FreeSid
0x140072d68  mov     [rsp+160h+var_F8], r15
0x140072d6d  mov     r8, [rsp+160h+NewAcl]; pDacl
0x140072d72  xor     r9d, r9d; bDaclDefaulted
0x140072d75  mov     rcx, rdi; pSecurityDescriptor
0x140072d78  lea     edx, [r9+1]; bDaclPresent
0x140072d7c  call    cs:__imp_SetSecurityDescriptorDacl
0x140072d82  test    eax, eax
0x140072d84  jnz     loc_140072E18
0x140072d8a  mov     rax, cs:WPP_GLOBAL_Control
0x140072d91  cmp     rax, r13
0x140072d94  jz      short loc_140072DC7
0x140072d96  test    [rax+1Ch], r12b
0x140072d9a  jz      short loc_140072DC7
0x140072d9c  cmp     [rax+19h], r12b
0x140072da0  jb      short loc_140072DC7
0x140072da2  call    cs:__imp_GetLastError
0x140072da8  mov     edx, 42h ; 'B'
0x140072dad  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x140072db4  mov     rcx, cs:WPP_GLOBAL_Control
0x140072dbb  mov     r9d, eax
0x140072dbe  mov     rcx, [rcx+10h]
0x140072dc2  call    WPP_SF_d
0x140072dc7  mov     rcx, rsi; lpMem
0x140072dca  call    pMemFree
0x140072dcf  mov     rcx, rdi; lpMem
0x140072dd2  call    pMemFree
0x140072dd7  mov     rcx, r14; lpMem
0x140072dda  call    pMemFree
0x140072ddf  mov     rcx, [rsp+160h+var_100]; pSid
0x140072de4  test    rcx, rcx
0x140072de7  jz      short loc_140072DEF
0x140072de9  call    cs:__imp_FreeSid
0x140072def  mov     rcx, [rsp+160h+var_F8]; pSid
0x140072df4  test    rcx, rcx
0x140072df7  jz      short loc_140072DFF
0x140072df9  call    cs:__imp_FreeSid
0x140072dff  mov     rcx, [rsp+160h+NewAcl]; hMem
0x140072e04  test    rcx, rcx
0x140072e07  jz      loc_140072A44
0x140072e0d  call    cs:__imp_LocalFree
0x140072e13  jmp     loc_140072A44
0x140072e18  mov     rax, rsi
0x140072e1b  mov     rcx, [rbp+60h+var_50]
0x140072e1f  xor     rcx, rsp; StackCookie
0x140072e22  call    __security_check_cookie
0x140072e27  add     rsp, 128h
0x140072e2e  pop     r15
0x140072e30  pop     r14
0x140072e32  pop     r13
0x140072e34  pop     r12
0x140072e36  pop     rdi
0x140072e37  pop     rsi
0x140072e38  pop     rbx
0x140072e39  pop     rbp
0x140072e3a  retn
```
