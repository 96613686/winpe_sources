# DhcpOpenGlobalEvent

- ea: `0x18000dd30`
- end: `0x18000df4b`
- name: `DhcpOpenGlobalEvent`
- size: `539`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180001f90`
- `0x180002160`
- `0x1800048c0`
- `0x18000dd30`
- `0x180011f08`
- `0x1800127f0`

## import_xrefs

- `api-ms-win-downlevel-kernel32-l1-1-0!SetLastError` at `0x18000df07`
- `api-ms-win-downlevel-kernel32-l1-1-0!SetLastError` at `0x18000df07`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetLastError` at `0x18000de37`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetLastError` at `0x18000de8d`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetLastError` at `0x18000de37`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetLastError` at `0x18000de8d`
- `api-ms-win-downlevel-kernel32-l1-1-0!CreateEventW` at `0x18000decf`
- `api-ms-win-downlevel-kernel32-l1-1-0!CreateEventW` at `0x18000decf`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000dd7b`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000dd7b`
- `api-ms-win-downlevel-kernel32-l1-1-0!OpenEventW` at `0x18000dda7`
- `api-ms-win-downlevel-kernel32-l1-1-0!OpenEventW` at `0x18000dda7`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18000dea4`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18000dea4`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000ddfe`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000ddfe`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18000de83`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18000de83`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18000de56`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18000de56`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18000de2d`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18000de2d`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000defb`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000defb`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18000ddec`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18000ddec`

## pseudocode

```c
HANDLE DhcpOpenGlobalEvent()
{
  DWORD LastError; // ebx
  LPWSTR CommandLineW; // rax
  HANDLE v2; // rdi
  DWORD v3; // ebx
  __int64 v4; // rdx
  __int64 v5; // r8
  struct _ACL *v6; // rax
  struct _ACL *v7; // rsi
  __int64 v8; // rdx
  __int64 v9; // r8
  void *v10; // rax
  void *v11; // rbx
  PSID v12; // rcx
  __int64 nSubAuthority2; // [rsp+20h] [rbp-49h]
  PSID pSid; // [rsp+60h] [rbp-9h] BYREF
  void *v16; // [rsp+68h] [rbp-1h] BYREF
  struct _ACL *v17; // [rsp+70h] [rbp+7h] BYREF
  struct _SECURITY_ATTRIBUTES EventAttributes; // [rsp+78h] [rbp+Fh] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+90h] [rbp+27h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 256;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  LastError = 0;
  pSid = 0;
  memset(&EventAttributes, 0, sizeof(EventAttributes));
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
  {
    CommandLineW = GetCommandLineW();
    WPP_SF_S(1028, 10, WPP_bced608cee43397007671a721f646035_Traceguids, CommandLineW);
  }
  v2 = OpenEventW(0x100002u, 0, L"DHCPNEWIPADDRESS");
  if ( !v2 && AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0, 0, 0, 0, 0, 0, 0, 0, &pSid) )
  {
    v3 = GetLengthSid(pSid) + 36;
    v6 = (struct _ACL *)DhcpAlloc(v3, v4, v5);
    v17 = v6;
    v7 = v6;
    if ( v6 )
    {
      if ( InitializeAcl(v6, v3, 2u) && AddAccessAllowedAce(v7, 2u, 0x100002u, pSid) )
      {
        v10 = (void *)DhcpAlloc(40, v8, v9);
        v16 = v10;
        v11 = v10;
        if ( v10 )
        {
          if ( InitializeSecurityDescriptor(v10, 1u)
            && SetSecurityDescriptorDacl(v11, 1, v7, 0)
            && (EventAttributes.nLength = 24,
                EventAttributes.lpSecurityDescriptor = v11,
                EventAttributes.bInheritHandle = 0,
                (v2 = CreateEventW(&EventAttributes, 1, 0, L"DHCPNEWIPADDRESS")) != 0) )
          {
            LastError = 0;
          }
          else
          {
            LastError = GetLastError();
          }
          DhcpFree(&v16);
        }
        else
        {
          LastError = 8;
        }
      }
      else
      {
        LastError = GetLastError();
      }
      DhcpFree(&v17);
    }
    else
    {
      LastError = 8;
    }
  }
  v12 = pSid;
  if ( pSid )
    FreeSid(pSid);
  if ( LastError )
    SetLastError(LastError);
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
  {
    LODWORD(nSubAuthority2) = LastError;
    WPP_SF_qD(v12, 11, WPP_bced608cee43397007671a721f646035_Traceguids, v2, nSubAuthority2);
  }
  return v2;
}

```

## disassembly

```asm
0x18000dd30  push    rbp
0x18000dd32  push    rbx
0x18000dd33  push    rsi
0x18000dd34  push    rdi
0x18000dd35  push    r14
0x18000dd37  lea     rbp, [rsp-37h]
0x18000dd3c  sub     rsp, 0A0h
0x18000dd43  mov     rax, cs:__security_cookie
0x18000dd4a  xor     rax, rsp
0x18000dd4d  mov     [rbp+57h+var_28], rax
0x18000dd51  xor     r14d, r14d
0x18000dd54  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 100h
0x18000dd5a  xor     eax, eax
0x18000dd5c  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r14d
0x18000dd60  xorps   xmm0, xmm0
0x18000dd63  mov     qword ptr [rbp+57h+EventAttributes.bInheritHandle], rax
0x18000dd67  mov     ebx, r14d
0x18000dd6a  mov     [rbp+57h+var_60], r14
0x18000dd6e  movups  xmmword ptr [rbp+57h+EventAttributes.nLength], xmm0
0x18000dd72  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000dd79  jz      short loc_18000DD99
0x18000dd7b  call    cs:__imp_GetCommandLineW
0x18000dd81  lea     edx, [r14+0Ah]
0x18000dd85  mov     ecx, 404h
0x18000dd8a  mov     r9, rax
0x18000dd8d  lea     r8, WPP_bced608cee43397007671a721f646035_Traceguids
0x18000dd94  call    WPP_SF_S
0x18000dd99  lea     r8, Name; "DHCPNEWIPADDRESS"
0x18000dda0  xor     edx, edx; bInheritHandle
0x18000dda2  mov     ecx, 100002h; dwDesiredAccess
0x18000dda7  call    cs:__imp_OpenEventW
0x18000ddad  mov     rdi, rax
0x18000ddb0  test    rax, rax
0x18000ddb3  jnz     loc_18000DEF2
0x18000ddb9  lea     rax, [rbp+57h+var_60]
0x18000ddbd  xor     r9d, r9d; nSubAuthority1
0x18000ddc0  mov     [rsp+0C0h+pSid], rax; pSid
0x18000ddc5  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18000ddc9  mov     [rsp+0C0h+nSubAuthority7], r14d; nSubAuthority7
0x18000ddce  xor     r8d, r8d; nSubAuthority0
0x18000ddd1  mov     [rsp+0C0h+nSubAuthority6], r14d; nSubAuthority6
0x18000ddd6  mov     dl, 1; nSubAuthorityCount
0x18000ddd8  mov     [rsp+0C0h+nSubAuthority5], r14d; nSubAuthority5
0x18000dddd  mov     [rsp+0C0h+nSubAuthority4], r14d; nSubAuthority4
0x18000dde2  mov     [rsp+0C0h+nSubAuthority3], r14d; nSubAuthority3
0x18000dde7  mov     dword ptr [rsp+0C0h+nSubAuthority2], r14d; nSubAuthority2
0x18000ddec  call    cs:__imp_AllocateAndInitializeSid
0x18000ddf2  test    eax, eax
0x18000ddf4  jz      loc_18000DEF2
0x18000ddfa  mov     rcx, [rbp+57h+var_60]; pSid
0x18000ddfe  call    cs:__imp_GetLengthSid
0x18000de04  lea     ebx, [rax+24h]
0x18000de07  mov     ecx, ebx
0x18000de09  call    DhcpAlloc
0x18000de0e  mov     [rbp+57h+var_50], rax
0x18000de12  mov     rsi, rax
0x18000de15  test    rax, rax
0x18000de18  jnz     short loc_18000DE22
0x18000de1a  lea     ebx, [rdi+8]
0x18000de1d  jmp     loc_18000DEF2
0x18000de22  mov     r8d, 2; dwAclRevision
0x18000de28  mov     edx, ebx; nAclLength
0x18000de2a  mov     rcx, rsi; pAcl
0x18000de2d  call    cs:__imp_InitializeAcl
0x18000de33  test    eax, eax
0x18000de35  jnz     short loc_18000DE44
0x18000de37  call    cs:__imp_GetLastError
0x18000de3d  mov     ebx, eax
0x18000de3f  jmp     loc_18000DEE9
0x18000de44  mov     r9, [rbp+57h+var_60]; pSid
0x18000de48  mov     edx, 2; dwAceRevision
0x18000de4d  mov     r8d, 100002h; AccessMask
0x18000de53  mov     rcx, rsi; pAcl
0x18000de56  call    cs:__imp_AddAccessAllowedAce
0x18000de5c  test    eax, eax
0x18000de5e  jz      short loc_18000DE37
0x18000de60  mov     ecx, 28h ; '('
0x18000de65  call    DhcpAlloc
0x18000de6a  mov     [rbp+57h+var_58], rax
0x18000de6e  mov     rbx, rax
0x18000de71  test    rax, rax
0x18000de74  jnz     short loc_18000DE7B
0x18000de76  lea     ebx, [rax+8]
0x18000de79  jmp     short loc_18000DEE9
0x18000de7b  mov     edx, 1; dwRevision
0x18000de80  mov     rcx, rbx; pSecurityDescriptor
0x18000de83  call    cs:__imp_InitializeSecurityDescriptor
0x18000de89  test    eax, eax
0x18000de8b  jnz     short loc_18000DE97
0x18000de8d  call    cs:__imp_GetLastError
0x18000de93  mov     ebx, eax
0x18000de95  jmp     short loc_18000DEE0
0x18000de97  xor     r9d, r9d; bDaclDefaulted
0x18000de9a  mov     r8, rsi; pDacl
0x18000de9d  mov     rcx, rbx; pSecurityDescriptor
0x18000dea0  lea     edx, [r9+1]; bDaclPresent
0x18000dea4  call    cs:__imp_SetSecurityDescriptorDacl
0x18000deaa  test    eax, eax
0x18000deac  jz      short loc_18000DE8D
0x18000deae  xor     r8d, r8d; bInitialState
0x18000deb1  mov     [rbp+57h+EventAttributes.nLength], 18h
0x18000deb8  lea     r9, Name; "DHCPNEWIPADDRESS"
0x18000debf  mov     [rbp+57h+EventAttributes.lpSecurityDescriptor], rbx
0x18000dec3  lea     rcx, [rbp+57h+EventAttributes]; lpEventAttributes
0x18000dec7  mov     [rbp+57h+EventAttributes.bInheritHandle], r14d
0x18000decb  lea     edx, [r8+1]; bManualReset
0x18000decf  call    cs:__imp_CreateEventW
0x18000ded5  mov     rdi, rax
0x18000ded8  test    rax, rax
0x18000dedb  jz      short loc_18000DE8D
0x18000dedd  mov     ebx, r14d
0x18000dee0  lea     rcx, [rbp+57h+var_58]
0x18000dee4  call    DhcpFree
0x18000dee9  lea     rcx, [rbp+57h+var_50]
0x18000deed  call    DhcpFree
0x18000def2  mov     rcx, [rbp+57h+var_60]; pSid
0x18000def6  test    rcx, rcx
0x18000def9  jz      short loc_18000DF01
0x18000defb  call    cs:__imp_FreeSid
0x18000df01  test    ebx, ebx
0x18000df03  jz      short loc_18000DF0D
0x18000df05  mov     ecx, ebx; dwErrCode
0x18000df07  call    cs:__imp_SetLastError
0x18000df0d  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000df14  jz      short loc_18000DF2E
0x18000df16  mov     edx, 0Bh
0x18000df1b  mov     dword ptr [rsp+0C0h+nSubAuthority2], ebx
0x18000df1f  mov     r9, rdi
0x18000df22  lea     r8, WPP_bced608cee43397007671a721f646035_Traceguids
0x18000df29  call    WPP_SF_qD
0x18000df2e  mov     rax, rdi
0x18000df31  mov     rcx, [rbp+57h+var_28]
0x18000df35  xor     rcx, rsp; StackCookie
0x18000df38  call    __security_check_cookie
0x18000df3d  add     rsp, 0A0h
0x18000df44  pop     r14
0x18000df46  pop     rdi
0x18000df47  pop     rsi
0x18000df48  pop     rbx
0x18000df49  pop     rbp
0x18000df4a  retn
```
