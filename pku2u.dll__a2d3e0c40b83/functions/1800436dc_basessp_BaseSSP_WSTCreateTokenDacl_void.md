# basessp::BaseSSP::WSTCreateTokenDacl(void *)

- ea: `0x1800436dc`
- end: `0x180043a6e`
- name: `?WSTCreateTokenDacl@BaseSSP@basessp@@QEAAJPEAX@Z`
- size: `914`
- prototype: `__int64 __fastcall(basessp::BaseSSP *__hidden this, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002ee60`

## callees

- `0x180012820`
- `0x180018870`
- `0x1800436dc`
- `0x180043b20`
- `0x180043be4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800439ec`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800439ec`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180043754`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180043754`
- `ntdll!RtlEqualSid` at `0x18004383e`
- `ntdll!RtlEqualSid` at `0x18004384f`
- `ntdll!RtlEqualSid` at `0x18004383e`
- `ntdll!RtlEqualSid` at `0x18004384f`
- `ntdll!NtOpenProcessToken` at `0x180043791`
- `ntdll!NtOpenProcessToken` at `0x180043791`
- `ntdll!RtlCreateAcl` at `0x1800438ad`
- `ntdll!RtlCreateAcl` at `0x1800438ad`
- `ntdll!RtlAddAccessAllowedAce` at `0x1800438ce`
- `ntdll!RtlAddAccessAllowedAce` at `0x1800438f0`
- `ntdll!RtlAddAccessAllowedAce` at `0x180043917`
- `ntdll!RtlAddAccessAllowedAce` at `0x18004393f`
- `ntdll!RtlAddAccessAllowedAce` at `0x180043964`
- `ntdll!RtlAddAccessAllowedAce` at `0x180043985`
- `ntdll!RtlAddAccessAllowedAce` at `0x1800438ce`
- `ntdll!RtlAddAccessAllowedAce` at `0x1800438f0`
- `ntdll!RtlAddAccessAllowedAce` at `0x180043917`
- `ntdll!RtlAddAccessAllowedAce` at `0x18004393f`
- `ntdll!RtlAddAccessAllowedAce` at `0x180043964`
- `ntdll!RtlAddAccessAllowedAce` at `0x180043985`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18004399a`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18004399a`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x1800439b2`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x1800439b2`
- `ntdll!NtSetSecurityObject` at `0x1800439cb`
- `ntdll!NtSetSecurityObject` at `0x1800439cb`
- `ntdll!NtClose` at `0x1800439f6`
- `ntdll!NtClose` at `0x180043a55`
- `ntdll!NtClose` at `0x1800439f6`
- `ntdll!NtClose` at `0x180043a55`
- `ntdll!RtlLengthSid` at `0x1800437fa`
- `ntdll!RtlLengthSid` at `0x180043809`
- `ntdll!RtlLengthSid` at `0x180043819`
- `ntdll!RtlLengthSid` at `0x180043828`
- `ntdll!RtlLengthSid` at `0x18004385c`
- `ntdll!RtlLengthSid` at `0x18004387b`
- `ntdll!RtlLengthSid` at `0x1800437fa`
- `ntdll!RtlLengthSid` at `0x180043809`
- `ntdll!RtlLengthSid` at `0x180043819`
- `ntdll!RtlLengthSid` at `0x180043828`
- `ntdll!RtlLengthSid` at `0x18004385c`
- `ntdll!RtlLengthSid` at `0x18004387b`
- `ntdll!NtOpenThreadToken` at `0x180043748`
- `ntdll!NtOpenThreadToken` at `0x180043748`

## pseudocode

```c
__int64 __fastcall basessp::BaseSSP::WSTCreateTokenDacl(basessp::BaseSSP *this, void *a2)
{
  PSID *v2; // rdi
  struct _TOKEN_USER *v3; // r15
  struct _TOKEN_USER *v4; // r13
  struct _TOKEN_USER *v5; // r14
  PSID *v6; // r12
  struct _ACL *v7; // rsi
  NTSTATUS v8; // eax
  NTSTATUS Acl; // ebx
  int v10; // eax
  struct _TOKEN_APPCONTAINER_INFORMATION **v11; // r9
  PSID v12; // rcx
  ULONG v13; // ebx
  ULONG v14; // eax
  ULONG v15; // ebx
  ULONG v16; // eax
  ULONG v17; // ebx
  ULONG v18; // eax
  struct _ACL *v19; // rax
  int v21[2]; // [rsp+20h] [rbp-58h] BYREF
  void *TokenHandle; // [rsp+28h] [rbp-50h] BYREF
  HANDLE v23; // [rsp+30h] [rbp-48h] BYREF
  struct _TOKEN_USER *v24; // [rsp+38h] [rbp-40h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+40h] [rbp-38h] BYREF
  __int64 v26; // [rsp+60h] [rbp-18h]
  int v27; // [rsp+C0h] [rbp+48h] BYREF
  int v28; // [rsp+C4h] [rbp+4Ch]
  HANDLE Handle; // [rsp+C8h] [rbp+50h]
  struct _TOKEN_USER *v30; // [rsp+D0h] [rbp+58h] BYREF
  struct _TOKEN_USER *v31; // [rsp+D8h] [rbp+60h] BYREF

  Handle = a2;
  v28 = HIDWORD(this);
  v2 = (PSID *)Pku2uGlobalBaseSSP;
  v31 = 0;
  v3 = 0;
  v24 = 0;
  v4 = 0;
  v30 = 0;
  *(_QWORD *)v21 = 0;
  v23 = 0;
  v5 = 0;
  TokenHandle = 0;
  v6 = 0;
  v27 = 0;
  v7 = 0;
  v26 = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  v8 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0xCu, 1u, &TokenHandle);
  Acl = v8;
  if ( v8 < 0 )
  {
    if ( v8 != -1073741700 )
      goto LABEL_32;
  }
  else
  {
    RevertToSelf();
    v10 = basessp::BaseSSP::WSTGetTokenUser((basessp::BaseSSP *)v2, TokenHandle, &v30);
    v5 = v30;
    Acl = v10;
    if ( v10 < 0 )
      goto LABEL_32;
  }
  Acl = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 8u, &v23);
  if ( Acl < 0 )
    goto LABEL_32;
  Acl = basessp::BaseSSP::WSTGetTokenUser((basessp::BaseSSP *)v2, v23, &v31);
  if ( Acl < 0 )
  {
LABEL_31:
    v3 = v31;
    goto LABEL_32;
  }
  Acl = basessp::WSTGetTokenPackage(v23, &v27, v21, v11);
  if ( Acl < 0 )
  {
LABEL_30:
    v6 = *(PSID **)v21;
    goto LABEL_31;
  }
  Acl = basessp::BaseSSP::WSTGetTokenUser((basessp::BaseSSP *)v2, Handle, &v24);
  if ( Acl < 0 )
  {
    v4 = v24;
    goto LABEL_30;
  }
  v12 = v2[29];
  LODWORD(v30) = 0;
  v13 = RtlLengthSid(v12);
  v14 = RtlLengthSid(v2[28]);
  v4 = v24;
  v15 = v14 + v13;
  v16 = RtlLengthSid(v24->User.Sid);
  v3 = v31;
  v17 = RtlLengthSid(v31->User.Sid) + v16 + v15 + 40;
  if ( v5 && !RtlEqualSid(v5->User.Sid, v3->User.Sid) && !RtlEqualSid(v5->User.Sid, v4->User.Sid) )
  {
    v18 = RtlLengthSid(v5->User.Sid);
    LODWORD(v30) = 1;
    v17 += v18 + 8;
  }
  v6 = *(PSID **)v21;
  if ( v27 )
    v17 += RtlLengthSid(**(PSID **)v21) + 8;
  v19 = (struct _ACL *)basessp::BaseSSP::WSTAllocate((basessp::BaseSSP *)v2, v17);
  v7 = v19;
  if ( v19 )
  {
    Acl = RtlCreateAcl(v19, v17, 2u);
    if ( Acl >= 0 )
    {
      Acl = RtlAddAccessAllowedAce(v7, 2u, 0xF01FFu, v3->User.Sid);
      if ( Acl >= 0 )
      {
        Acl = RtlAddAccessAllowedAce(v7, 2u, 0xF01FFu, v4->User.Sid);
        if ( Acl >= 0 )
        {
          if ( !(_DWORD)v30 || (Acl = RtlAddAccessAllowedAce(v7, 2u, 0xF01FFu, v5->User.Sid), Acl >= 0) )
          {
            if ( !v27 || (Acl = RtlAddAccessAllowedAce(v7, 2u, 0xF01FFu, *v6), Acl >= 0) )
            {
              Acl = RtlAddAccessAllowedAce(v7, 2u, 0xF01FFu, v2[29]);
              if ( Acl >= 0 )
              {
                Acl = RtlAddAccessAllowedAce(v7, 2u, 0xF01FFu, v2[28]);
                if ( Acl >= 0 )
                {
                  Acl = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
                  if ( Acl >= 0 )
                  {
                    Acl = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v7, 0);
                    if ( Acl >= 0 )
                      Acl = NtSetSecurityObject(Handle, 4u, SecurityDescriptor);
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  else
  {
    Acl = -1073741670;
  }
LABEL_32:
  if ( TokenHandle )
  {
    SetThreadToken(0, TokenHandle);
    NtClose(TokenHandle);
  }
  if ( v4 )
    basessp::BaseSSP::WSTFree((basessp::BaseSSP *)v2, v4);
  if ( v3 )
    basessp::BaseSSP::WSTFree((basessp::BaseSSP *)v2, v3);
  if ( v5 )
    basessp::BaseSSP::WSTFree((basessp::BaseSSP *)v2, v5);
  if ( v6 )
    basessp::BaseSSP::WSTFree((basessp::BaseSSP *)v2, v6);
  if ( v7 )
    basessp::BaseSSP::WSTFree((basessp::BaseSSP *)v2, v7);
  if ( v23 )
    NtClose(v23);
  return (unsigned int)Acl;
}

```

## disassembly

```asm
0x1800436dc  mov     [rsp-40h+Handle], rdx
0x1800436e1  mov     [rsp-40h+arg_0], rcx
0x1800436e6  push    rbp
0x1800436e7  push    rbx
0x1800436e8  push    rsi
0x1800436e9  push    rdi
0x1800436ea  push    r12
0x1800436ec  push    r13
0x1800436ee  push    r14
0x1800436f0  push    r15
0x1800436f2  mov     rbp, rsp
0x1800436f5  sub     rsp, 78h
0x1800436f9  mov     rdi, cs:?Pku2uGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA; basessp::BaseSSP * Pku2uGlobalBaseSSP
0x180043700  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180043704  xor     eax, eax
0x180043706  xorps   xmm0, xmm0
0x180043709  mov     r8b, 1; OpenAsSelf
0x18004370c  mov     [rbp+arg_18], rax
0x180043710  mov     r15d, eax
0x180043713  mov     [rbp+var_40], rax
0x180043717  mov     r13d, eax
0x18004371a  mov     [rbp+arg_10], rax
0x18004371e  lea     edx, [rax+0Ch]; DesiredAccess
0x180043721  mov     qword ptr [rbp+var_58], rax
0x180043725  lea     rcx, [rax-2]; ThreadHandle
0x180043729  mov     [rbp+var_48], rax
0x18004372d  mov     r14d, eax
0x180043730  mov     [rbp+TokenHandle], rax
0x180043734  mov     r12d, eax
0x180043737  mov     dword ptr [rbp+arg_0], eax
0x18004373a  mov     esi, eax
0x18004373c  mov     [rbp+var_18], rax
0x180043740  movups  [rbp+SecurityDescriptor], xmm0
0x180043744  movups  [rbp+var_28], xmm0
0x180043748  call    cs:__imp_NtOpenThreadToken
0x18004374e  mov     ebx, eax
0x180043750  test    eax, eax
0x180043752  js      short loc_180043779
0x180043754  call    cs:__imp_RevertToSelf
0x18004375a  mov     rdx, [rbp+TokenHandle]; TokenHandle
0x18004375e  lea     r8, [rbp+arg_10]; struct _TOKEN_USER **
0x180043762  mov     rcx, rdi; this
0x180043765  call    ?WSTGetTokenUser@BaseSSP@basessp@@QEAAJPEAXPEAPEAU_TOKEN_USER@@@Z; basessp::BaseSSP::WSTGetTokenUser(void *,_TOKEN_USER * *)
0x18004376a  mov     r14, [rbp+arg_10]
0x18004376e  mov     ebx, eax
0x180043770  test    eax, eax
0x180043772  jns     short loc_180043784
0x180043774  jmp     loc_1800439E1
0x180043779  cmp     eax, 0C000007Ch
0x18004377e  jnz     loc_1800439E1
0x180043784  lea     r8, [rbp+var_48]; TokenHandle
0x180043788  mov     edx, 8; DesiredAccess
0x18004378d  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180043791  call    cs:__imp_NtOpenProcessToken
0x180043797  mov     ebx, eax
0x180043799  test    eax, eax
0x18004379b  js      loc_1800439E1
0x1800437a1  mov     rdx, [rbp+var_48]; TokenHandle
0x1800437a5  lea     r8, [rbp+arg_18]; struct _TOKEN_USER **
0x1800437a9  mov     rcx, rdi; this
0x1800437ac  call    ?WSTGetTokenUser@BaseSSP@basessp@@QEAAJPEAXPEAPEAU_TOKEN_USER@@@Z; basessp::BaseSSP::WSTGetTokenUser(void *,_TOKEN_USER * *)
0x1800437b1  mov     ebx, eax
0x1800437b3  test    eax, eax
0x1800437b5  js      loc_1800439DD
0x1800437bb  mov     rcx, [rbp+var_48]; TokenHandle
0x1800437bf  lea     r8, [rbp+var_58]; int *
0x1800437c3  lea     rdx, [rbp+arg_0]; void *
0x1800437c7  call    ?WSTGetTokenPackage@basessp@@YAJPEAXPEAHPEAPEAU_TOKEN_APPCONTAINER_INFORMATION@@@Z; basessp::WSTGetTokenPackage(void *,int *,_TOKEN_APPCONTAINER_INFORMATION * *)
0x1800437cc  mov     ebx, eax
0x1800437ce  test    eax, eax
0x1800437d0  js      loc_1800439D9
0x1800437d6  mov     rdx, [rbp+Handle]; TokenHandle
0x1800437da  lea     r8, [rbp+var_40]; struct _TOKEN_USER **
0x1800437de  mov     rcx, rdi; this
0x1800437e1  call    ?WSTGetTokenUser@BaseSSP@basessp@@QEAAJPEAXPEAPEAU_TOKEN_USER@@@Z; basessp::BaseSSP::WSTGetTokenUser(void *,_TOKEN_USER * *)
0x1800437e6  mov     ebx, eax
0x1800437e8  test    eax, eax
0x1800437ea  js      loc_1800439D5
0x1800437f0  mov     rcx, [rdi+0E8h]; Sid
0x1800437f7  mov     dword ptr [rbp+arg_10], esi
0x1800437fa  call    cs:__imp_RtlLengthSid
0x180043800  mov     rcx, [rdi+0E0h]; Sid
0x180043807  mov     ebx, eax
0x180043809  call    cs:__imp_RtlLengthSid
0x18004380f  mov     r13, [rbp+var_40]
0x180043813  add     ebx, eax
0x180043815  mov     rcx, [r13+0]; Sid
0x180043819  call    cs:__imp_RtlLengthSid
0x18004381f  mov     r15, [rbp+arg_18]
0x180043823  add     ebx, eax
0x180043825  mov     rcx, [r15]; Sid
0x180043828  call    cs:__imp_RtlLengthSid
0x18004382e  add     ebx, 28h ; '('
0x180043831  add     ebx, eax
0x180043833  test    r14, r14
0x180043836  jz      short loc_18004386E
0x180043838  mov     rdx, [r15]; Sid2
0x18004383b  mov     rcx, [r14]; Sid1
0x18004383e  call    cs:__imp_RtlEqualSid
0x180043844  test    al, al
0x180043846  jnz     short loc_18004386E
0x180043848  mov     rdx, [r13+0]; Sid2
0x18004384c  mov     rcx, [r14]; Sid1
0x18004384f  call    cs:__imp_RtlEqualSid
0x180043855  test    al, al
0x180043857  jnz     short loc_18004386E
0x180043859  mov     rcx, [r14]; Sid
0x18004385c  call    cs:__imp_RtlLengthSid
0x180043862  add     ebx, 8
0x180043865  mov     dword ptr [rbp+arg_10], 1
0x18004386c  add     ebx, eax
0x18004386e  mov     r12, qword ptr [rbp+var_58]
0x180043872  cmp     dword ptr [rbp+arg_0], esi
0x180043875  jz      short loc_180043886
0x180043877  mov     rcx, [r12]; Sid
0x18004387b  call    cs:__imp_RtlLengthSid
0x180043881  add     eax, 8
0x180043884  add     ebx, eax
0x180043886  mov     edx, ebx; unsigned __int64
0x180043888  mov     rcx, rdi; this
0x18004388b  call    ?WSTAllocate@BaseSSP@basessp@@QEAAPEAX_K@Z; basessp::BaseSSP::WSTAllocate(unsigned __int64)
0x180043890  mov     rsi, rax
0x180043893  test    rax, rax
0x180043896  jnz     short loc_1800438A2
0x180043898  mov     ebx, 0C000009Ah
0x18004389d  jmp     loc_1800439E1
0x1800438a2  mov     r8d, 2; AclRevision
0x1800438a8  mov     edx, ebx; AclSize
0x1800438aa  mov     rcx, rsi; Acl
0x1800438ad  call    cs:__imp_RtlCreateAcl
0x1800438b3  mov     ebx, eax
0x1800438b5  test    eax, eax
0x1800438b7  js      loc_1800439E1
0x1800438bd  mov     r9, [r15]; Sid
0x1800438c0  mov     edx, 2; Revision
0x1800438c5  mov     r8d, 0F01FFh; AccessMask
0x1800438cb  mov     rcx, rsi; Acl
0x1800438ce  call    cs:__imp_RtlAddAccessAllowedAce
0x1800438d4  mov     ebx, eax
0x1800438d6  test    eax, eax
0x1800438d8  js      loc_1800439E1
0x1800438de  mov     r9, [r13+0]; Sid
0x1800438e2  mov     edx, 2; Revision
0x1800438e7  mov     r8d, 0F01FFh; AccessMask
0x1800438ed  mov     rcx, rsi; Acl
0x1800438f0  call    cs:__imp_RtlAddAccessAllowedAce
0x1800438f6  mov     ebx, eax
0x1800438f8  test    eax, eax
0x1800438fa  js      loc_1800439E1
0x180043900  cmp     dword ptr [rbp+arg_10], 0
0x180043904  jz      short loc_180043927
0x180043906  mov     r9, [r14]; Sid
0x180043909  mov     edx, 2; Revision
0x18004390e  mov     r8d, 0F01FFh; AccessMask
0x180043914  mov     rcx, rsi; Acl
0x180043917  call    cs:__imp_RtlAddAccessAllowedAce
0x18004391d  mov     ebx, eax
0x18004391f  test    eax, eax
0x180043921  js      loc_1800439E1
0x180043927  cmp     dword ptr [rbp+arg_0], 0
0x18004392b  jz      short loc_18004394F
0x18004392d  mov     r9, [r12]; Sid
0x180043931  mov     edx, 2; Revision
0x180043936  mov     r8d, 0F01FFh; AccessMask
0x18004393c  mov     rcx, rsi; Acl
0x18004393f  call    cs:__imp_RtlAddAccessAllowedAce
0x180043945  mov     ebx, eax
0x180043947  test    eax, eax
0x180043949  js      loc_1800439E1
0x18004394f  mov     r9, [rdi+0E8h]; Sid
0x180043956  mov     edx, 2; Revision
0x18004395b  mov     r8d, 0F01FFh; AccessMask
0x180043961  mov     rcx, rsi; Acl
0x180043964  call    cs:__imp_RtlAddAccessAllowedAce
0x18004396a  mov     ebx, eax
0x18004396c  test    eax, eax
0x18004396e  js      short loc_1800439E1
0x180043970  mov     r9, [rdi+0E0h]; Sid
0x180043977  mov     edx, 2; Revision
0x18004397c  mov     r8d, 0F01FFh; AccessMask
0x180043982  mov     rcx, rsi; Acl
0x180043985  call    cs:__imp_RtlAddAccessAllowedAce
0x18004398b  mov     ebx, eax
0x18004398d  test    eax, eax
0x18004398f  js      short loc_1800439E1
0x180043991  mov     edx, 1; Revision
0x180043996  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18004399a  call    cs:__imp_RtlCreateSecurityDescriptor
0x1800439a0  mov     ebx, eax
0x1800439a2  test    eax, eax
0x1800439a4  js      short loc_1800439E1
0x1800439a6  xor     r9d, r9d; DaclDefaulted
0x1800439a9  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1800439ad  mov     r8, rsi; Dacl
0x1800439b0  mov     dl, 1; DaclPresent
0x1800439b2  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1800439b8  mov     ebx, eax
0x1800439ba  test    eax, eax
0x1800439bc  js      short loc_1800439E1
0x1800439be  mov     rcx, [rbp+Handle]; Handle
0x1800439c2  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1800439c6  mov     edx, 4; SecurityInformation
0x1800439cb  call    cs:__imp_NtSetSecurityObject
0x1800439d1  mov     ebx, eax
0x1800439d3  jmp     short loc_1800439E1
0x1800439d5  mov     r13, [rbp+var_40]
0x1800439d9  mov     r12, qword ptr [rbp+var_58]
0x1800439dd  mov     r15, [rbp+arg_18]
0x1800439e1  mov     rdx, [rbp+TokenHandle]; Token
0x1800439e5  test    rdx, rdx
0x1800439e8  jz      short loc_1800439FC
0x1800439ea  xor     ecx, ecx; Thread
0x1800439ec  call    cs:__imp_SetThreadToken
0x1800439f2  mov     rcx, [rbp+TokenHandle]; Handle
0x1800439f6  call    cs:__imp_NtClose
0x1800439fc  test    r13, r13
0x1800439ff  jz      short loc_180043A0C
0x180043a01  mov     rdx, r13; void *
0x180043a04  mov     rcx, rdi; this
0x180043a07  call    ?WSTFree@BaseSSP@basessp@@QEAAXPEAX@Z; basessp::BaseSSP::WSTFree(void *)
0x180043a0c  test    r15, r15
0x180043a0f  jz      short loc_180043A1C
0x180043a11  mov     rdx, r15; void *
0x180043a14  mov     rcx, rdi; this
0x180043a17  call    ?WSTFree@BaseSSP@basessp@@QEAAXPEAX@Z; basessp::BaseSSP::WSTFree(void *)
0x180043a1c  test    r14, r14
0x180043a1f  jz      short loc_180043A2C
0x180043a21  mov     rdx, r14; void *
0x180043a24  mov     rcx, rdi; this
0x180043a27  call    ?WSTFree@BaseSSP@basessp@@QEAAXPEAX@Z; basessp::BaseSSP::WSTFree(void *)
0x180043a2c  test    r12, r12
0x180043a2f  jz      short loc_180043A3C
0x180043a31  mov     rdx, r12; void *
0x180043a34  mov     rcx, rdi; this
0x180043a37  call    ?WSTFree@BaseSSP@basessp@@QEAAXPEAX@Z; basessp::BaseSSP::WSTFree(void *)
0x180043a3c  test    rsi, rsi
0x180043a3f  jz      short loc_180043A4C
0x180043a41  mov     rdx, rsi; void *
0x180043a44  mov     rcx, rdi; this
0x180043a47  call    ?WSTFree@BaseSSP@basessp@@QEAAXPEAX@Z; basessp::BaseSSP::WSTFree(void *)
0x180043a4c  mov     rcx, [rbp+var_48]; Handle
0x180043a50  test    rcx, rcx
0x180043a53  jz      short loc_180043A5B
0x180043a55  call    cs:__imp_NtClose
0x180043a5b  mov     eax, ebx
0x180043a5d  add     rsp, 78h
0x180043a61  pop     r15
0x180043a63  pop     r14
0x180043a65  pop     r13
0x180043a67  pop     r12
0x180043a69  pop     rdi
0x180043a6a  pop     rsi
0x180043a6b  pop     rbx
0x180043a6c  pop     rbp
0x180043a6d  retn
```
