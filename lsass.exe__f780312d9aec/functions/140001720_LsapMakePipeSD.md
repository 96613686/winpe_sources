# LsapMakePipeSD

- ea: `0x140001720`
- end: `0x140001a6e`
- name: `LsapMakePipeSD`
- size: `846`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140002c24`

## callees

- `0x1400016c0`
- `0x140001720`
- `0x140001a80`
- `0x1400020c0`
- `0x140002a02`

## import_xrefs

- `ntdll!RtlCreateSecurityDescriptor` at `0x1400017b0`
- `ntdll!RtlCreateSecurityDescriptor` at `0x1400017b0`
- `ntdll!RtlCreateAcl` at `0x140001882`
- `ntdll!RtlCreateAcl` at `0x140001971`
- `ntdll!RtlCreateAcl` at `0x140001882`
- `ntdll!RtlCreateAcl` at `0x140001971`
- `ntdll!RtlAddMandatoryAce` at `0x14000199f`
- `ntdll!RtlAddMandatoryAce` at `0x14000199f`
- `ntdll!RtlAddAccessAllowedAce` at `0x1400018a7`
- `ntdll!RtlAddAccessAllowedAce` at `0x1400018cc`
- `ntdll!RtlAddAccessAllowedAce` at `0x1400018ee`
- `ntdll!RtlAddAccessAllowedAce` at `0x1400018a7`
- `ntdll!RtlAddAccessAllowedAce` at `0x1400018cc`
- `ntdll!RtlAddAccessAllowedAce` at `0x1400018ee`
- `ntdll!RtlLengthSid` at `0x140001827`
- `ntdll!RtlLengthSid` at `0x140001837`
- `ntdll!RtlLengthSid` at `0x140001827`
- `ntdll!RtlLengthSid` at `0x140001837`
- `ntdll!RtlAllocateAndInitializeSid` at `0x140001952`
- `ntdll!RtlAllocateAndInitializeSid` at `0x140001952`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x140001909`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x140001909`
- `ntdll!RtlMakeSelfRelativeSD` at `0x1400019d2`
- `ntdll!RtlMakeSelfRelativeSD` at `0x140001a04`
- `ntdll!RtlMakeSelfRelativeSD` at `0x1400019d2`
- `ntdll!RtlMakeSelfRelativeSD` at `0x140001a04`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x140001865`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x140001865`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x1400019b7`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x1400019b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140001a31`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140001a31`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140001804`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140001804`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400017c0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400017c0`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1400017d3`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1400017d3`

## pseudocode

```c
__int64 __fastcall LsapMakePipeSD(_QWORD *a1)
{
  __int64 v2; // rdx
  __int64 v3; // r8
  void *LsaHeap; // rax
  void *v5; // rdi
  struct _ACL *v7; // r15
  NTSTATUS SecurityDescriptor; // ebx
  HANDLE CurrentProcess; // rax
  ULONG v10; // r14d
  ULONG v11; // r14d
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rdx
  __int64 v15; // r8
  void *v16; // rax
  void *v17; // r14
  void *SubAuthority3; // [rsp+28h] [rbp-D8h]
  ULONG BufferLength; // [rsp+60h] [rbp-A0h] BYREF
  DWORD TokenInformationLength; // [rsp+64h] [rbp-9Ch] BYREF
  void *TokenHandle; // [rsp+68h] [rbp-98h] BYREF
  PSID Sid; // [rsp+70h] [rbp-90h] BYREF
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+78h] [rbp-88h] BYREF
  PSID TokenInformation[12]; // [rsp+80h] [rbp-80h] BYREF
  _ACL Acl; // [rsp+E0h] [rbp-20h] BYREF

  TokenInformationLength = 76;
  TokenHandle = 0;
  BufferLength = 0;
  Sid = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 4096;
  memset_0(&Acl, 0, 0x200u);
  LsaHeap = (void *)LsapAllocateLsaHeap(40, v2, v3);
  v5 = LsaHeap;
  if ( !LsaHeap )
    return 3221225495LL;
  v7 = 0;
  SecurityDescriptor = RtlCreateSecurityDescriptor(LsaHeap, 1u);
  if ( SecurityDescriptor >= 0 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 0x20008u, &TokenHandle) )
    {
      if ( GetTokenInformation(
             TokenHandle,
             TokenOwner,
             TokenInformation,
             TokenInformationLength,
             &TokenInformationLength) )
      {
        v10 = RtlLengthSid(gLsapAnonymousSid);
        v11 = RtlLengthSid(gLsapWorldSid) + v10;
        v7 = (struct _ACL *)LsapAllocateLsaHeap(v11 + 112, v12, v13);
        if ( v7 )
        {
          SecurityDescriptor = RtlSetOwnerSecurityDescriptor(v5, TokenInformation[0], 0);
          if ( SecurityDescriptor >= 0 )
          {
            SecurityDescriptor = RtlCreateAcl(v7, v11 + 112, 2u);
            if ( SecurityDescriptor >= 0 )
            {
              SecurityDescriptor = RtlAddAccessAllowedAce(v7, 2u, 0x12019Bu, gLsapWorldSid);
              if ( SecurityDescriptor >= 0 )
              {
                SecurityDescriptor = RtlAddAccessAllowedAce(v7, 2u, 0x12019Bu, gLsapAnonymousSid);
                if ( SecurityDescriptor >= 0 )
                {
                  SecurityDescriptor = RtlAddAccessAllowedAce(v7, 2u, 0x1F01FFu, TokenInformation[0]);
                  if ( SecurityDescriptor >= 0 )
                  {
                    if ( RtlSetDaclSecurityDescriptor(v5, 1u, v7, 0) >= 0 )
                    {
                      SecurityDescriptor = RtlAllocateAndInitializeSid(
                                             &IdentifierAuthority,
                                             1u,
                                             0,
                                             0,
                                             0,
                                             0,
                                             0,
                                             0,
                                             0,
                                             0,
                                             &Sid);
                      if ( SecurityDescriptor >= 0 )
                      {
                        SecurityDescriptor = RtlCreateAcl(&Acl, 0x200u, 2u);
                        if ( SecurityDescriptor >= 0 )
                        {
                          LODWORD(SubAuthority3) = 1;
                          SecurityDescriptor = RtlAddMandatoryAce(&Acl, 2u, 0, (ULONG)Sid, 0x11u, SubAuthority3);
                          if ( SecurityDescriptor >= 0 )
                          {
                            SecurityDescriptor = RtlSetSaclSecurityDescriptor(v5, 1u, &Acl, 0);
                            if ( SecurityDescriptor >= 0 )
                            {
                              BufferLength = 0;
                              SecurityDescriptor = RtlMakeSelfRelativeSD(v5, 0, &BufferLength);
                              if ( SecurityDescriptor == -1073741789 )
                              {
                                v16 = (void *)LsapAllocateLsaHeap(BufferLength, v14, v15);
                                v17 = v16;
                                if ( v16 )
                                {
                                  SecurityDescriptor = RtlMakeSelfRelativeSD(v5, v16, &BufferLength);
                                  if ( SecurityDescriptor >= 0 )
                                    *a1 = v17;
                                }
                                else
                                {
                                  SecurityDescriptor = -1073741801;
                                }
                              }
                              else if ( SecurityDescriptor >= 0 )
                              {
                                SecurityDescriptor = -1073741595;
                              }
                            }
                          }
                        }
                      }
                    }
                    else
                    {
                      SecurityDescriptor = -1073741801;
                    }
                  }
                }
              }
            }
          }
        }
        else
        {
          SecurityDescriptor = -1073741801;
        }
      }
      else
      {
        SecurityDescriptor = -1073741801;
      }
    }
    else
    {
      SecurityDescriptor = -1073741801;
    }
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  LsapFreeLsaHeap(v7);
  LsapFreeLsaHeap(v5);
  return (unsigned int)SecurityDescriptor;
}

```

## disassembly

```asm
0x140001720  push    rbp
0x140001722  push    rbx
0x140001723  push    rsi
0x140001724  push    rdi
0x140001725  push    r12
0x140001727  lea     rbp, [rsp-1F0h]
0x14000172f  sub     rsp, 2F0h
0x140001736  mov     rax, cs:__security_cookie
0x14000173d  xor     rax, rsp
0x140001740  mov     [rbp+210h+var_30], rax
0x140001747  xor     r12d, r12d
0x14000174a  mov     [rsp+310h+TokenInformationLength], 4Ch ; 'L'
0x140001752  mov     rsi, rcx
0x140001755  mov     [rsp+310h+TokenHandle], r12
0x14000175a  lea     rcx, [rbp+210h+Acl]; void *
0x14000175e  mov     [rsp+310h+BufferLength], r12d
0x140001763  xor     edx, edx; Val
0x140001765  mov     [rsp+310h+var_2A0], r12
0x14000176a  mov     r8d, 200h; Size
0x140001770  mov     dword ptr [rsp+310h+IdentifierAuthority.Value], r12d
0x140001775  mov     word ptr [rsp+310h+IdentifierAuthority.Value+4], 1000h
0x14000177c  call    memset_0
0x140001781  mov     ecx, 28h ; '('
0x140001786  call    LsapAllocateLsaHeap
0x14000178b  mov     rdi, rax
0x14000178e  test    rax, rax
0x140001791  jnz     short loc_14000179D
0x140001793  mov     eax, 0C0000017h
0x140001798  jmp     loc_140001A51
0x14000179d  mov     [rsp+310h+arg_10], r15
0x1400017a5  mov     edx, 1; Revision
0x1400017aa  mov     rcx, rdi; SecurityDescriptor
0x1400017ad  mov     r15, r12
0x1400017b0  call    cs:__imp_RtlCreateSecurityDescriptor
0x1400017b6  mov     ebx, eax
0x1400017b8  test    eax, eax
0x1400017ba  js      loc_140001A27
0x1400017c0  call    cs:__imp_GetCurrentProcess
0x1400017c6  lea     r8, [rsp+310h+TokenHandle]; TokenHandle
0x1400017cb  mov     edx, 20008h; DesiredAccess
0x1400017d0  mov     rcx, rax; ProcessHandle
0x1400017d3  call    cs:__imp_OpenProcessToken
0x1400017d9  test    eax, eax
0x1400017db  jnz     short loc_1400017E7
0x1400017dd  mov     ebx, 0C0000017h
0x1400017e2  jmp     loc_140001A27
0x1400017e7  mov     r9d, [rsp+310h+TokenInformationLength]; TokenInformationLength
0x1400017ec  lea     rax, [rsp+310h+TokenInformationLength]
0x1400017f1  mov     rcx, [rsp+310h+TokenHandle]; TokenHandle
0x1400017f6  lea     r8, [rbp+210h+TokenInformation]; TokenInformation
0x1400017fa  mov     edx, 4; TokenInformationClass
0x1400017ff  mov     [rsp+310h+ReturnLength], rax; ReturnLength
0x140001804  call    cs:__imp_GetTokenInformation
0x14000180a  test    eax, eax
0x14000180c  jnz     short loc_140001818
0x14000180e  mov     ebx, 0C0000017h
0x140001813  jmp     loc_140001A27
0x140001818  mov     rcx, cs:gLsapAnonymousSid; Sid
0x14000181f  mov     [rsp+310h+arg_8], r14
0x140001827  call    cs:__imp_RtlLengthSid
0x14000182d  mov     rcx, cs:gLsapWorldSid; Sid
0x140001834  mov     r14d, eax
0x140001837  call    cs:__imp_RtlLengthSid
0x14000183d  add     r14d, eax
0x140001840  lea     ecx, [r14+70h]
0x140001844  call    LsapAllocateLsaHeap
0x140001849  mov     r15, rax
0x14000184c  test    rax, rax
0x14000184f  jnz     short loc_14000185B
0x140001851  mov     ebx, 0C0000017h
0x140001856  jmp     loc_140001A1F
0x14000185b  mov     rdx, [rbp+210h+TokenInformation]; Owner
0x14000185f  xor     r8d, r8d; OwnerDefaulted
0x140001862  mov     rcx, rdi; SecurityDescriptor
0x140001865  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x14000186b  mov     ebx, eax
0x14000186d  test    eax, eax
0x14000186f  js      loc_140001A1F
0x140001875  mov     r8d, 2; AclRevision
0x14000187b  lea     edx, [r14+70h]; AclSize
0x14000187f  mov     rcx, r15; Acl
0x140001882  call    cs:__imp_RtlCreateAcl
0x140001888  mov     ebx, eax
0x14000188a  test    eax, eax
0x14000188c  js      loc_140001A1F
0x140001892  mov     r9, cs:gLsapWorldSid; Sid
0x140001899  mov     edx, 2; Revision
0x14000189e  mov     r8d, 12019Bh; AccessMask
0x1400018a4  mov     rcx, r15; Acl
0x1400018a7  call    cs:__imp_RtlAddAccessAllowedAce
0x1400018ad  mov     ebx, eax
0x1400018af  test    eax, eax
0x1400018b1  js      loc_140001A1F
0x1400018b7  mov     r9, cs:gLsapAnonymousSid; Sid
0x1400018be  mov     edx, 2; Revision
0x1400018c3  mov     r8d, 12019Bh; AccessMask
0x1400018c9  mov     rcx, r15; Acl
0x1400018cc  call    cs:__imp_RtlAddAccessAllowedAce
0x1400018d2  mov     ebx, eax
0x1400018d4  test    eax, eax
0x1400018d6  js      loc_140001A1F
0x1400018dc  mov     r9, [rbp+210h+TokenInformation]; Sid
0x1400018e0  mov     edx, 2; Revision
0x1400018e5  mov     r8d, 1F01FFh; AccessMask
0x1400018eb  mov     rcx, r15; Acl
0x1400018ee  call    cs:__imp_RtlAddAccessAllowedAce
0x1400018f4  mov     ebx, eax
0x1400018f6  test    eax, eax
0x1400018f8  js      loc_140001A1F
0x1400018fe  xor     r9d, r9d; DaclDefaulted
0x140001901  mov     r8, r15; Dacl
0x140001904  mov     dl, 1; DaclPresent
0x140001906  mov     rcx, rdi; SecurityDescriptor
0x140001909  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x14000190f  test    eax, eax
0x140001911  jns     short loc_14000191D
0x140001913  mov     ebx, 0C0000017h
0x140001918  jmp     loc_140001A1F
0x14000191d  lea     rax, [rsp+310h+var_2A0]
0x140001922  xor     r9d, r9d; SubAuthority1
0x140001925  mov     [rsp+310h+Sid], rax; Sid
0x14000192a  lea     rcx, [rsp+310h+IdentifierAuthority]; IdentifierAuthority
0x14000192f  mov     [rsp+310h+SubAuthority7], r12d; SubAuthority7
0x140001934  xor     r8d, r8d; SubAuthority0
0x140001937  mov     [rsp+310h+SubAuthority6], r12d; SubAuthority6
0x14000193c  mov     dl, 1; SubAuthorityCount
0x14000193e  mov     [rsp+310h+SubAuthority5], r12d; SubAuthority5
0x140001943  mov     [rsp+310h+SubAuthority4], r12d; SubAuthority4
0x140001948  mov     dword ptr [rsp+310h+SubAuthority3], r12d; SubAuthority3
0x14000194d  mov     dword ptr [rsp+310h+ReturnLength], r12d; SubAuthority2
0x140001952  call    cs:__imp_RtlAllocateAndInitializeSid
0x140001958  mov     ebx, eax
0x14000195a  test    eax, eax
0x14000195c  js      loc_140001A1F
0x140001962  mov     edx, 200h; AclSize
0x140001967  lea     rcx, [rbp+210h+Acl]; Acl
0x14000196b  mov     r8d, 2; AclRevision
0x140001971  call    cs:__imp_RtlCreateAcl
0x140001977  mov     ebx, eax
0x140001979  test    eax, eax
0x14000197b  js      loc_140001A1F
0x140001981  mov     r9, [rsp+310h+var_2A0]; MandatoryFlags
0x140001986  lea     rcx, [rbp+210h+Acl]; Acl
0x14000198a  mov     dword ptr [rsp+310h+SubAuthority3], 1; LabelSid
0x140001992  xor     r8d, r8d; Flags
0x140001995  mov     edx, 2; Revision
0x14000199a  mov     byte ptr [rsp+310h+ReturnLength], 11h; AceType
0x14000199f  call    cs:__imp_RtlAddMandatoryAce
0x1400019a5  mov     ebx, eax
0x1400019a7  test    eax, eax
0x1400019a9  js      short loc_140001A1F
0x1400019ab  xor     r9d, r9d; SaclDefaulted
0x1400019ae  lea     r8, [rbp+210h+Acl]; Sacl
0x1400019b2  mov     dl, 1; SaclPresent
0x1400019b4  mov     rcx, rdi; SecurityDescriptor
0x1400019b7  call    cs:__imp_RtlSetSaclSecurityDescriptor
0x1400019bd  mov     ebx, eax
0x1400019bf  test    eax, eax
0x1400019c1  js      short loc_140001A1F
0x1400019c3  lea     r8, [rsp+310h+BufferLength]; BufferLength
0x1400019c8  mov     [rsp+310h+BufferLength], r12d
0x1400019cd  xor     edx, edx; SelfRelativeSD
0x1400019cf  mov     rcx, rdi; AbsoluteSD
0x1400019d2  call    cs:__imp_RtlMakeSelfRelativeSD
0x1400019d8  mov     ebx, eax
0x1400019da  cmp     eax, 0C0000023h
0x1400019df  jnz     short loc_140001A15
0x1400019e1  mov     ecx, [rsp+310h+BufferLength]
0x1400019e5  call    LsapAllocateLsaHeap
0x1400019ea  mov     r14, rax
0x1400019ed  test    rax, rax
0x1400019f0  jnz     short loc_1400019F9
0x1400019f2  mov     ebx, 0C0000017h
0x1400019f7  jmp     short loc_140001A1F
0x1400019f9  lea     r8, [rsp+310h+BufferLength]; BufferLength
0x1400019fe  mov     rdx, r14; SelfRelativeSD
0x140001a01  mov     rcx, rdi; AbsoluteSD
0x140001a04  call    cs:__imp_RtlMakeSelfRelativeSD
0x140001a0a  mov     ebx, eax
0x140001a0c  test    eax, eax
0x140001a0e  js      short loc_140001A1F
0x140001a10  mov     [rsi], r14
0x140001a13  jmp     short loc_140001A1F
0x140001a15  test    ebx, ebx
0x140001a17  mov     eax, 0C00000E5h
0x140001a1c  cmovns  ebx, eax
0x140001a1f  mov     r14, [rsp+310h+arg_8]
0x140001a27  mov     rcx, [rsp+310h+TokenHandle]; hObject
0x140001a2c  test    rcx, rcx
0x140001a2f  jz      short loc_140001A37
0x140001a31  call    cs:__imp_CloseHandle
0x140001a37  mov     rcx, r15
0x140001a3a  call    LsapFreeLsaHeap
0x140001a3f  mov     rcx, rdi
0x140001a42  call    LsapFreeLsaHeap
0x140001a47  mov     r15, [rsp+310h+arg_10]
0x140001a4f  mov     eax, ebx
0x140001a51  mov     rcx, [rbp+210h+var_30]
0x140001a58  xor     rcx, rsp; StackCookie
0x140001a5b  call    __security_check_cookie
0x140001a60  add     rsp, 2F0h
0x140001a67  pop     r12
0x140001a69  pop     rdi
0x140001a6a  pop     rsi
0x140001a6b  pop     rbx
0x140001a6c  pop     rbp
0x140001a6d  retn
```
