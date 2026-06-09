# SetDirPermsForFaxService

- ea: `0x18000ef60`
- end: `0x18000f1d3`
- name: `SetDirPermsForFaxService`
- size: `627`
- prototype: `__int64 __fastcall(LPWSTR pObjectName)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000eaec`

## callees

- `0x180005eac`
- `0x180005ed4`
- `0x18000ef60`
- `0x180015cf0`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18000f185`
- `KERNEL32!LocalFree` at `0x18000f194`
- `KERNEL32!LocalFree` at `0x18000f185`
- `KERNEL32!LocalFree` at `0x18000f194`
- `KERNEL32!GetLastError` at `0x18000f02d`
- `KERNEL32!GetLastError` at `0x18000f02d`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18000f023`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18000f023`
- `ADVAPI32!SetEntriesInAclW` at `0x18000f0f9`
- `ADVAPI32!SetEntriesInAclW` at `0x18000f0f9`
- `ADVAPI32!FreeSid` at `0x18000f1a3`
- `ADVAPI32!FreeSid` at `0x18000f1a3`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x18000f144`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x18000f144`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x18000f08a`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x18000f08a`

## pseudocode

```c
__int64 __fastcall SetDirPermsForFaxService(LPWSTR pObjectName)
{
  DWORD NamedSecurityInfoW; // eax
  DWORD v3; // ebx
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  PACL NewAcl; // [rsp+60h] [rbp-29h] BYREF
  PSID pSid; // [rsp+68h] [rbp-21h] BYREF
  PACL ppDacl; // [rsp+70h] [rbp-19h] BYREF
  PSECURITY_DESCRIPTOR ppSecurityDescriptor; // [rsp+78h] [rbp-11h] BYREF
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+80h] [rbp-9h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+B0h] [rbp+27h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_506210d4ee34309f98ba1c03a656d666_Traceguids);
  }
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  ppSecurityDescriptor = 0;
  ppDacl = 0;
  NewAcl = 0;
  pSid = 0;
  memset(&pListOfExplicitEntries, 0, sizeof(pListOfExplicitEntries));
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x14u, 0, 0, 0, 0, 0, 0, 0, &pSid) )
  {
    NamedSecurityInfoW = GetNamedSecurityInfoW(pObjectName, SE_FILE_OBJECT, 4u, 0, 0, &ppDacl, 0, &ppSecurityDescriptor);
    v3 = NamedSecurityInfoW;
    if ( NamedSecurityInfoW )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v5 = 33;
        goto LABEL_25;
      }
    }
    else
    {
      pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)pSid;
      pListOfExplicitEntries.grfAccessPermissions = 2032127;
      pListOfExplicitEntries.grfAccessMode = GRANT_ACCESS;
      pListOfExplicitEntries.grfInheritance = 3;
      pListOfExplicitEntries.Trustee.pMultipleTrustee = 0;
      *(_QWORD *)&pListOfExplicitEntries.Trustee.MultipleTrusteeOperation = 0;
      pListOfExplicitEntries.Trustee.TrusteeType = TRUSTEE_IS_USER;
      NamedSecurityInfoW = SetEntriesInAclW(1u, &pListOfExplicitEntries, ppDacl, &NewAcl);
      v3 = NamedSecurityInfoW;
      if ( NamedSecurityInfoW )
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v5 = 34;
          goto LABEL_25;
        }
      }
      else
      {
        NamedSecurityInfoW = SetNamedSecurityInfoW(pObjectName, SE_FILE_OBJECT, 4u, 0, 0, NewAcl, 0);
        v3 = NamedSecurityInfoW;
        if ( NamedSecurityInfoW )
        {
          v4 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v5 = 35;
            goto LABEL_25;
          }
        }
      }
    }
  }
  else
  {
    NamedSecurityInfoW = GetLastError();
    v3 = NamedSecurityInfoW;
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v5 = 32;
LABEL_25:
      WPP_SF_d(v4[2], v5, WPP_506210d4ee34309f98ba1c03a656d666_Traceguids, NamedSecurityInfoW);
    }
  }
  if ( NewAcl )
    LocalFree(NewAcl);
  if ( ppSecurityDescriptor )
    LocalFree(ppSecurityDescriptor);
  if ( pSid )
    FreeSid(pSid);
  return v3;
}

```

## disassembly

```asm
0x18000ef60  mov     [rsp-8+arg_8], rbx
0x18000ef65  mov     [rsp-8+arg_10], rsi
0x18000ef6a  push    rbp
0x18000ef6b  push    rdi
0x18000ef6c  push    r12
0x18000ef6e  push    r13
0x18000ef70  push    r15
0x18000ef72  lea     rbp, [rsp-37h]
0x18000ef77  sub     rsp, 0C0h
0x18000ef7e  mov     rax, cs:__security_cookie
0x18000ef85  xor     rax, rsp
0x18000ef88  mov     [rbp+57h+var_28], rax
0x18000ef8c  mov     rdi, rcx
0x18000ef8f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ef96  lea     r15, WPP_GLOBAL_Control
0x18000ef9d  lea     r12, WPP_506210d4ee34309f98ba1c03a656d666_Traceguids
0x18000efa4  cmp     rcx, r15
0x18000efa7  jz      short loc_18000EFC6
0x18000efa9  test    byte ptr [rcx+1Ch], 2
0x18000efad  jz      short loc_18000EFC6
0x18000efaf  cmp     byte ptr [rcx+19h], 5
0x18000efb3  jb      short loc_18000EFC6
0x18000efb5  mov     rcx, [rcx+10h]
0x18000efb9  mov     edx, 1Fh
0x18000efbe  mov     r8, r12
0x18000efc1  call    WPP_SF_
0x18000efc6  xor     esi, esi
0x18000efc8  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x18000efce  xorps   xmm0, xmm0
0x18000efd1  mov     [rbp+57h+ppSecurityDescriptor], rsi
0x18000efd5  lea     rax, [rbp+57h+var_78]
0x18000efd9  mov     [rbp+57h+ppDacl], rsi
0x18000efdd  mov     [rsp+0E0h+pSid], rax; pSid
0x18000efe2  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18000efe6  mov     [rsp+0E0h+nSubAuthority7], esi; nSubAuthority7
0x18000efea  lea     r13d, [rsi+1]
0x18000efee  mov     [rsp+0E0h+nSubAuthority6], esi; nSubAuthority6
0x18000eff2  lea     r8d, [rsi+14h]; nSubAuthority0
0x18000eff6  mov     [rsp+0E0h+nSubAuthority5], esi; nSubAuthority5
0x18000effa  mov     dl, r13b; nSubAuthorityCount
0x18000effd  mov     [rsp+0E0h+nSubAuthority4], esi; nSubAuthority4
0x18000f001  xor     r9d, r9d; nSubAuthority1
0x18000f004  mov     [rsp+0E0h+nSubAuthority3], esi; nSubAuthority3
0x18000f008  mov     [rsp+0E0h+nSubAuthority2], esi; nSubAuthority2
0x18000f00c  mov     [rbp+57h+NewAcl], rsi
0x18000f010  mov     [rbp+57h+var_78], rsi
0x18000f014  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], xmm0
0x18000f018  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], esi
0x18000f01b  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.Trustee.pMultipleTrustee], xmm0
0x18000f01f  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeType], xmm0
0x18000f023  call    cs:__imp_AllocateAndInitializeSid
0x18000f029  test    eax, eax
0x18000f02b  jnz     short loc_18000F061
0x18000f02d  call    cs:__imp_GetLastError
0x18000f033  mov     ebx, eax
0x18000f035  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f03c  cmp     rcx, r15
0x18000f03f  jz      loc_18000F17C
0x18000f045  test    byte ptr [rcx+1Ch], 2
0x18000f049  jz      loc_18000F17C
0x18000f04f  cmp     byte ptr [rcx+19h], 2
0x18000f053  jb      loc_18000F17C
0x18000f059  lea     edx, [rsi+20h]
0x18000f05c  jmp     loc_18000F16D
0x18000f061  lea     rax, [rbp+57h+ppSecurityDescriptor]
0x18000f065  xor     r9d, r9d; ppsidOwner
0x18000f068  mov     qword ptr [rsp+0E0h+nSubAuthority5], rax; ppSecurityDescriptor
0x18000f06d  mov     edx, r13d; ObjectType
0x18000f070  lea     rax, [rbp+57h+ppDacl]
0x18000f074  mov     qword ptr [rsp+0E0h+nSubAuthority4], rsi; ppSacl
0x18000f079  mov     qword ptr [rsp+0E0h+nSubAuthority3], rax; ppDacl
0x18000f07e  mov     rcx, rdi; pObjectName
0x18000f081  lea     r8d, [r9+4]; SecurityInfo
0x18000f085  mov     qword ptr [rsp+0E0h+nSubAuthority2], rsi; ppsidGroup
0x18000f08a  call    cs:__imp_GetNamedSecurityInfoW
0x18000f090  mov     ebx, eax
0x18000f092  test    eax, eax
0x18000f094  jz      short loc_18000F0C4
0x18000f096  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f09d  cmp     rcx, r15
0x18000f0a0  jz      loc_18000F17C
0x18000f0a6  test    byte ptr [rcx+1Ch], 2
0x18000f0aa  jz      loc_18000F17C
0x18000f0b0  cmp     byte ptr [rcx+19h], 2
0x18000f0b4  jb      loc_18000F17C
0x18000f0ba  mov     edx, 21h ; '!'
0x18000f0bf  jmp     loc_18000F16D
0x18000f0c4  mov     rax, [rbp+57h+var_78]
0x18000f0c8  lea     r9, [rbp+57h+NewAcl]; NewAcl
0x18000f0cc  mov     r8, [rbp+57h+ppDacl]; OldAcl
0x18000f0d0  lea     rdx, [rbp+57h+pListOfExplicitEntries]; pListOfExplicitEntries
0x18000f0d4  mov     ecx, r13d; cCountOfExplicitEntries
0x18000f0d7  mov     [rbp+57h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x18000f0db  mov     [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], 1F01FFh
0x18000f0e2  mov     [rbp+57h+pListOfExplicitEntries.grfAccessMode], r13d
0x18000f0e6  mov     [rbp+57h+pListOfExplicitEntries.grfInheritance], 3
0x18000f0ed  mov     [rbp+57h+pListOfExplicitEntries.Trustee.pMultipleTrustee], rsi
0x18000f0f1  mov     qword ptr [rbp+57h+pListOfExplicitEntries.Trustee.MultipleTrusteeOperation], rsi
0x18000f0f5  mov     [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeType], r13d
0x18000f0f9  call    cs:__imp_SetEntriesInAclW
0x18000f0ff  mov     ebx, eax
0x18000f101  test    eax, eax
0x18000f103  jz      short loc_18000F124
0x18000f105  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f10c  cmp     rcx, r15
0x18000f10f  jz      short loc_18000F17C
0x18000f111  test    byte ptr [rcx+1Ch], 2
0x18000f115  jz      short loc_18000F17C
0x18000f117  cmp     byte ptr [rcx+19h], 2
0x18000f11b  jb      short loc_18000F17C
0x18000f11d  mov     edx, 22h ; '"'
0x18000f122  jmp     short loc_18000F16D
0x18000f124  mov     rax, [rbp+57h+NewAcl]
0x18000f128  xor     r9d, r9d; psidOwner
0x18000f12b  mov     qword ptr [rsp+0E0h+nSubAuthority4], rsi; pSacl
0x18000f130  mov     edx, r13d; ObjectType
0x18000f133  mov     qword ptr [rsp+0E0h+nSubAuthority3], rax; pDacl
0x18000f138  mov     rcx, rdi; pObjectName
0x18000f13b  mov     qword ptr [rsp+0E0h+nSubAuthority2], rsi; psidGroup
0x18000f140  lea     r8d, [r9+4]; SecurityInfo
0x18000f144  call    cs:__imp_SetNamedSecurityInfoW
0x18000f14a  mov     ebx, eax
0x18000f14c  test    eax, eax
0x18000f14e  jz      short loc_18000F17C
0x18000f150  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f157  cmp     rcx, r15
0x18000f15a  jz      short loc_18000F17C
0x18000f15c  test    byte ptr [rcx+1Ch], 2
0x18000f160  jz      short loc_18000F17C
0x18000f162  cmp     byte ptr [rcx+19h], 2
0x18000f166  jb      short loc_18000F17C
0x18000f168  mov     edx, 23h ; '#'
0x18000f16d  mov     rcx, [rcx+10h]
0x18000f171  mov     r9d, eax
0x18000f174  mov     r8, r12
0x18000f177  call    WPP_SF_d
0x18000f17c  mov     rcx, [rbp+57h+NewAcl]; hMem
0x18000f180  test    rcx, rcx
0x18000f183  jz      short loc_18000F18B
0x18000f185  call    cs:__imp_LocalFree
0x18000f18b  mov     rcx, [rbp+57h+ppSecurityDescriptor]; hMem
0x18000f18f  test    rcx, rcx
0x18000f192  jz      short loc_18000F19A
0x18000f194  call    cs:__imp_LocalFree
0x18000f19a  mov     rcx, [rbp+57h+var_78]; pSid
0x18000f19e  test    rcx, rcx
0x18000f1a1  jz      short loc_18000F1A9
0x18000f1a3  call    cs:__imp_FreeSid
0x18000f1a9  mov     eax, ebx
0x18000f1ab  mov     rcx, [rbp+57h+var_28]
0x18000f1af  xor     rcx, rsp; StackCookie
0x18000f1b2  call    __security_check_cookie
0x18000f1b7  lea     r11, [rsp+0E0h+var_20]
0x18000f1bf  mov     rbx, [r11+38h]
0x18000f1c3  mov     rsi, [r11+40h]
0x18000f1c7  mov     rsp, r11
0x18000f1ca  pop     r15
0x18000f1cc  pop     r13
0x18000f1ce  pop     r12
0x18000f1d0  pop     rdi
0x18000f1d1  pop     rbp
0x18000f1d2  retn
```
