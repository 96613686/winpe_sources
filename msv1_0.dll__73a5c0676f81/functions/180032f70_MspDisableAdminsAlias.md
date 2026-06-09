# MspDisableAdminsAlias

- ea: `0x180032f70`
- end: `0x180033142`
- name: `MspDisableAdminsAlias`
- size: `466`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180032500`

## callees

- `0x18002ee7c`
- `0x18002fb50`
- `0x180032f70`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180032fc1`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180032fc1`
- `ntdll!RtlImpersonateSelf` at `0x180032fca`
- `ntdll!RtlImpersonateSelf` at `0x180032fca`
- `ntdll!NtOpenThreadToken` at `0x180032fe8`
- `ntdll!NtOpenThreadToken` at `0x180032fe8`
- `ntdll!NtFilterToken` at `0x1800330a9`
- `ntdll!NtFilterToken` at `0x1800330a9`
- `ntdll!RtlFreeSid` at `0x1800330fb`
- `ntdll!RtlFreeSid` at `0x1800330fb`
- `ntdll!NtClose` at `0x18003310a`
- `ntdll!NtClose` at `0x180033119`
- `ntdll!NtClose` at `0x18003310a`
- `ntdll!NtClose` at `0x180033119`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180033029`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180033029`
- `ntdll!NtSetInformationThread` at `0x1800330ea`
- `ntdll!NtSetInformationThread` at `0x1800330ea`

## pseudocode

```c
__int64 MspDisableAdminsAlias()
{
  NTSTATUS v0; // ebx
  _QWORD *v1; // rcx
  __int64 v2; // rdx
  PSID Sid; // [rsp+60h] [rbp-9h] BYREF
  void *TokenHandle; // [rsp+68h] [rbp-1h] BYREF
  void *NewTokenHandle; // [rsp+70h] [rbp+7h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+78h] [rbp+Fh] BYREF
  _DWORD v8[4]; // [rsp+80h] [rbp+17h] BYREF
  _TOKEN_GROUPS SidsToDisable; // [rsp+90h] [rbp+27h] BYREF
  _DWORD *v10; // [rsp+A8h] [rbp+3Fh]
  int v11; // [rsp+B0h] [rbp+47h]

  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  TokenHandle = 0;
  NewTokenHandle = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  Sid = 0;
  v8[0] = 257;
  v8[1] = 83886080;
  v8[2] = 18;
  RevertToSelf();
  v0 = RtlImpersonateSelf(SecurityDelegation);
  if ( v0 >= 0 )
  {
    v0 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0xEu, 1u, &TokenHandle);
    if ( v0 >= 0 )
    {
      v0 = RtlAllocateAndInitializeSid(&IdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &Sid);
      if ( v0 >= 0 )
      {
        SidsToDisable.Groups[0].Sid = Sid;
        SidsToDisable.GroupCount = 2;
        v10 = v8;
        SidsToDisable.Groups[0].Attributes = 0;
        v11 = 0;
        v0 = NtFilterToken(TokenHandle, 0, &SidsToDisable, 0, 0, &NewTokenHandle);
        if ( v0 >= 0 )
        {
          v0 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &NewTokenHandle, 8u);
        }
        else
        {
          v1 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v2 = 11;
            goto LABEL_7;
          }
        }
      }
      else
      {
        v1 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v2 = 10;
LABEL_7:
          WPP_SF_d(v1[2], v2, WPP_d81ffe40114e3ef115b20edc6117ed6d_Traceguids, (unsigned int)v0);
        }
      }
    }
  }
  if ( Sid )
    RtlFreeSid(Sid);
  if ( TokenHandle )
    NtClose(TokenHandle);
  if ( NewTokenHandle )
    NtClose(NewTokenHandle);
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x180032f70  mov     [rsp-8+arg_0], rbx
0x180032f75  mov     [rsp-8+arg_8], rdi
0x180032f7a  push    rbp
0x180032f7b  lea     rbp, [rsp-57h]
0x180032f80  sub     rsp, 0C0h
0x180032f87  mov     rax, cs:__security_cookie
0x180032f8e  xor     rax, rsp
0x180032f91  mov     [rbp+57h+var_8], rax
0x180032f95  xor     edi, edi
0x180032f97  mov     word ptr [rbp+57h+IdentifierAuthority.Value+4], 500h
0x180032f9d  mov     [rbp+57h+TokenHandle], rdi
0x180032fa1  mov     [rbp+57h+NewTokenHandle], rdi
0x180032fa5  mov     dword ptr [rbp+57h+IdentifierAuthority.Value], edi
0x180032fa8  mov     [rbp+57h+var_60], rdi
0x180032fac  mov     [rbp+57h+var_40], 101h
0x180032fb3  mov     [rbp+57h+var_3C], 5000000h
0x180032fba  mov     [rbp+57h+var_38], 12h
0x180032fc1  call    cs:__imp_RevertToSelf
0x180032fc7  lea     ecx, [rdi+3]; ImpersonationLevel
0x180032fca  call    cs:__imp_RtlImpersonateSelf
0x180032fd0  mov     ebx, eax
0x180032fd2  test    eax, eax
0x180032fd4  js      loc_1800330F2
0x180032fda  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x180032fde  mov     r8b, 1; OpenAsSelf
0x180032fe1  lea     edx, [rdi+0Eh]; DesiredAccess
0x180032fe4  lea     rcx, [rdi-2]; ThreadHandle
0x180032fe8  call    cs:__imp_NtOpenThreadToken
0x180032fee  mov     ebx, eax
0x180032ff0  test    eax, eax
0x180032ff2  js      loc_1800330F2
0x180032ff8  lea     rax, [rbp+57h+var_60]
0x180032ffc  mov     r9d, 220h; SubAuthority1
0x180033002  mov     [rsp+0C0h+Sid], rax; Sid
0x180033007  lea     r8d, [rdi+20h]; SubAuthority0
0x18003300b  mov     [rsp+0C0h+SubAuthority7], edi; SubAuthority7
0x18003300f  lea     rcx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x180033013  mov     [rsp+0C0h+SubAuthority6], edi; SubAuthority6
0x180033017  mov     dl, 2; SubAuthorityCount
0x180033019  mov     [rsp+0C0h+SubAuthority5], edi; SubAuthority5
0x18003301d  mov     [rsp+0C0h+SubAuthority4], edi; SubAuthority4
0x180033021  mov     [rsp+0C0h+SubAuthority3], edi; SubAuthority3
0x180033025  mov     [rsp+0C0h+SubAuthority2], edi; SubAuthority2
0x180033029  call    cs:__imp_RtlAllocateAndInitializeSid
0x18003302f  mov     ebx, eax
0x180033031  test    eax, eax
0x180033033  jns     short loc_180033071
0x180033035  mov     rcx, cs:WPP_GLOBAL_Control
0x18003303c  lea     rax, WPP_GLOBAL_Control
0x180033043  cmp     rcx, rax
0x180033046  jz      loc_1800330F2
0x18003304c  test    byte ptr [rcx+1Ch], 1
0x180033050  jz      loc_1800330F2
0x180033056  lea     edx, [rdi+0Ah]
0x180033059  mov     rcx, [rcx+10h]
0x18003305d  lea     r8, WPP_d81ffe40114e3ef115b20edc6117ed6d_Traceguids
0x180033064  mov     r9d, ebx
0x180033067  call    WPP_SF_d
0x18003306c  jmp     loc_1800330F2
0x180033071  mov     rax, [rbp+57h+var_60]
0x180033075  lea     r8, [rbp+57h+SidsToDisable]; SidsToDisable
0x180033079  mov     rcx, [rbp+57h+TokenHandle]; ExistingTokenHandle
0x18003307d  xor     r9d, r9d; PrivilegesToDelete
0x180033080  mov     [rbp+57h+SidsToDisable.Groups.Sid], rax
0x180033084  xor     edx, edx; Flags
0x180033086  lea     rax, [rbp+57h+var_40]
0x18003308a  mov     [rbp+57h+SidsToDisable.GroupCount], 2
0x180033091  mov     [rbp+57h+var_18], rax
0x180033095  lea     rax, [rbp+57h+NewTokenHandle]
0x180033099  mov     qword ptr [rsp+0C0h+SubAuthority3], rax; NewTokenHandle
0x18003309e  mov     qword ptr [rsp+0C0h+SubAuthority2], rdi; RestrictedSids
0x1800330a3  mov     [rbp+57h+SidsToDisable.Groups.Attributes], edi
0x1800330a6  mov     [rbp+57h+var_10], edi
0x1800330a9  call    cs:__imp_NtFilterToken
0x1800330af  mov     ebx, eax
0x1800330b1  test    eax, eax
0x1800330b3  jns     short loc_1800330D5
0x1800330b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800330bc  lea     rax, WPP_GLOBAL_Control
0x1800330c3  cmp     rcx, rax
0x1800330c6  jz      short loc_1800330F2
0x1800330c8  test    byte ptr [rcx+1Ch], 1
0x1800330cc  jz      short loc_1800330F2
0x1800330ce  mov     edx, 0Bh
0x1800330d3  jmp     short loc_180033059
0x1800330d5  mov     r9d, 8; ThreadInformationLength
0x1800330db  lea     r8, [rbp+57h+NewTokenHandle]; ThreadInformation
0x1800330df  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1800330e6  lea     edx, [r9-3]; ThreadInformationClass
0x1800330ea  call    cs:__imp_NtSetInformationThread
0x1800330f0  mov     ebx, eax
0x1800330f2  mov     rcx, [rbp+57h+var_60]; Sid
0x1800330f6  test    rcx, rcx
0x1800330f9  jz      short loc_180033101
0x1800330fb  call    cs:__imp_RtlFreeSid
0x180033101  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x180033105  test    rcx, rcx
0x180033108  jz      short loc_180033110
0x18003310a  call    cs:__imp_NtClose
0x180033110  mov     rcx, [rbp+57h+NewTokenHandle]; Handle
0x180033114  test    rcx, rcx
0x180033117  jz      short loc_18003311F
0x180033119  call    cs:__imp_NtClose
0x18003311f  mov     eax, ebx
0x180033121  mov     rcx, [rbp+57h+var_8]
0x180033125  xor     rcx, rsp; StackCookie
0x180033128  call    __security_check_cookie
0x18003312d  lea     r11, [rsp+0C0h+var_s0]
0x180033135  mov     rbx, [r11+10h]
0x180033139  mov     rdi, [r11+18h]
0x18003313d  mov     rsp, r11
0x180033140  pop     rbp
0x180033141  retn
```
