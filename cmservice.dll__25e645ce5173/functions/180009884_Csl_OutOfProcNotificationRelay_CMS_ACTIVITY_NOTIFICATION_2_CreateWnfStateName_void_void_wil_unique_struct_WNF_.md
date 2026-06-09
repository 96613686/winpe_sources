# Csl::OutOfProcNotificationRelay<_CMS_ACTIVITY_NOTIFICATION,2>::CreateWnfStateName(void *,void *,wil::unique_struct<_WNF_STATE_NAME,long (*)(_WNF_STATE_NAME const *),&NtDeleteWnfStateName(_WNF_STATE_NAME const *),std::nullptr_t,0> &)

- ea: `0x180009884`
- end: `0x180009a81`
- name: `?CreateWnfStateName@?$OutOfProcNotificationRelay@U_CMS_ACTIVITY_NOTIFICATION@@$01@Csl@@CAJPEAX0AEAV?$unique_struct@U_WNF_STATE_NAME@@P6AJPEBU1@@Z$1?NtDeleteWnfStateName@@YAJ0@Z$$T$0A@@wil@@@Z`
- size: `509`
- prototype: `__int64 __fastcall(PSID pSid, PSID)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000b134`
- `0x18001f5c4`
- `0x18001f96c`

## callees

- `0x180004bd0`
- `0x180009884`
- `0x18000dab0`

## import_xrefs

- `ntdll!RtlCreateSecurityDescriptor` at `0x180009964`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180009964`
- `ntdll!RtlCreateAcl` at `0x1800098bf`
- `ntdll!RtlCreateAcl` at `0x1800098bf`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x180009903`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x180009931`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x180009903`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x180009931`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18000998d`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18000998d`
- `ntdll!NtCreateWnfStateName` at `0x1800099da`
- `ntdll!NtCreateWnfStateName` at `0x1800099da`
- `ntdll!NtDeleteWnfStateName` at `0x180009a2f`
- `ntdll!NtDeleteWnfStateName` at `0x180009a53`
- `ntdll!NtDeleteWnfStateName` at `0x180009a2f`
- `ntdll!NtDeleteWnfStateName` at `0x180009a53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009a1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009a1e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009a3d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009a3d`

## pseudocode

```c
int __fastcall Csl::OutOfProcNotificationRelay<_CMS_ACTIVITY_NOTIFICATION,2>::CreateWnfStateName(
        PSID pSid,
        PSID a2,
        __int64 *a3)
{
  NTSTATUS v6; // eax
  __int64 v7; // rdx
  int v9; // eax
  int v10; // ebx
  __int64 v11; // rdi
  DWORD LastError; // ebx
  int pSida; // [rsp+20h] [rbp-E0h]
  _OWORD SecurityDescriptor[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v15; // [rsp+60h] [rbp-A0h]
  __int64 v16; // [rsp+68h] [rbp-98h] BYREF
  _ACL Acl; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+38h]

  v6 = RtlCreateAcl(&Acl, 0xA0u, 2u);
  if ( v6 < 0 )
  {
    v7 = 823;
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)v7,
             (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\CslNotification.h",
             (const char *)(unsigned int)v6,
             pSida);
  }
  v6 = RtlAddAccessAllowedAceEx(&Acl, 2u, 0, 0x10000000u, pSid);
  if ( v6 < 0 )
  {
    v7 = 830;
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)v7,
             (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\CslNotification.h",
             (const char *)(unsigned int)v6,
             pSida);
  }
  v6 = RtlAddAccessAllowedAceEx(&Acl, 2u, 0, 0x80000000, a2);
  if ( v6 < 0 )
  {
    v7 = 837;
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)v7,
             (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\CslNotification.h",
             (const char *)(unsigned int)v6,
             pSida);
  }
  v15 = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  v6 = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
  if ( v6 < 0 )
  {
    v7 = 842;
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)v7,
             (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\CslNotification.h",
             (const char *)(unsigned int)v6,
             pSida);
  }
  v6 = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, &Acl, 0);
  if ( v6 < 0 )
  {
    v7 = 847;
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)v7,
             (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\CslNotification.h",
             (const char *)(unsigned int)v6,
             pSida);
  }
  v16 = 0;
  v9 = NtCreateWnfStateName(&v16, 3, 0);
  if ( v9 >= 0 )
  {
    if ( a3 != &v16 )
    {
      v11 = v16;
      v16 = 0;
      LastError = GetLastError();
      NtDeleteWnfStateName(a3);
      SetLastError(LastError);
      *a3 = v11;
    }
    v10 = 0;
  }
  else
  {
    v10 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0x35A,
            (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\CslNotification.h",
            (const char *)(unsigned int)v9,
            0);
  }
  NtDeleteWnfStateName(&v16);
  return v10;
}

```

## disassembly

```asm
0x180009884  mov     [rsp-8+arg_18], rbx
0x180009889  push    rbp
0x18000988a  push    rsi
0x18000988b  push    rdi
0x18000988c  lea     rbp, [rsp-20h]
0x180009891  sub     rsp, 120h
0x180009898  mov     rax, cs:__security_cookie
0x18000989f  xor     rax, rsp
0x1800098a2  mov     [rbp+30h+var_20], rax
0x1800098a6  mov     rsi, r8
0x1800098a9  mov     rdi, rdx
0x1800098ac  mov     rbx, rcx
0x1800098af  mov     edx, 0A0h; AclSize
0x1800098b4  mov     r8d, 2; AclRevision
0x1800098ba  lea     rcx, [rsp+130h+Acl]; Acl
0x1800098bf  call    cs:__imp_RtlCreateAcl
0x1800098c6  nop     dword ptr [rax+rax+00h]
0x1800098cb  test    eax, eax
0x1800098cd  jns     short loc_1800098EC
0x1800098cf  mov     edx, 337h; void *
0x1800098d4  mov     rcx, [rbp+38h]; this
0x1800098d8  lea     r8, aOnecoreBaseGen_5; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x1800098df  mov     r9d, eax; char *
0x1800098e2  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800098e7  jmp     loc_180009A61
0x1800098ec  xor     r8d, r8d; AceFlags
0x1800098ef  mov     [rsp+130h+pSid], rbx; pSid
0x1800098f4  mov     r9d, 10000000h; AccessMask
0x1800098fa  lea     rcx, [rsp+130h+Acl]; pAcl
0x1800098ff  lea     edx, [r8+2]; dwAceRevision
0x180009903  call    cs:__imp_RtlAddAccessAllowedAceEx
0x18000990a  nop     dword ptr [rax+rax+00h]
0x18000990f  test    eax, eax
0x180009911  jns     short loc_18000991A
0x180009913  mov     edx, 33Eh
0x180009918  jmp     short loc_1800098D4
0x18000991a  xor     r8d, r8d; AceFlags
0x18000991d  mov     [rsp+130h+pSid], rdi; pSid
0x180009922  mov     r9d, 80000000h; AccessMask
0x180009928  lea     rcx, [rsp+130h+Acl]; pAcl
0x18000992d  lea     edx, [r8+2]; dwAceRevision
0x180009931  call    cs:__imp_RtlAddAccessAllowedAceEx
0x180009938  nop     dword ptr [rax+rax+00h]
0x18000993d  test    eax, eax
0x18000993f  jns     short loc_180009948
0x180009941  mov     edx, 345h
0x180009946  jmp     short loc_1800098D4
0x180009948  xor     eax, eax
0x18000994a  lea     rcx, [rsp+130h+SecurityDescriptor]; SecurityDescriptor
0x18000994f  xorps   xmm0, xmm0
0x180009952  mov     [rsp+130h+var_D0], rax
0x180009957  movups  [rsp+130h+SecurityDescriptor], xmm0
0x18000995c  lea     edx, [rax+1]; Revision
0x18000995f  movups  [rsp+130h+var_E0], xmm0
0x180009964  call    cs:__imp_RtlCreateSecurityDescriptor
0x18000996b  nop     dword ptr [rax+rax+00h]
0x180009970  test    eax, eax
0x180009972  jns     short loc_18000997E
0x180009974  mov     edx, 34Ah
0x180009979  jmp     loc_1800098D4
0x18000997e  xor     r9d, r9d; DaclDefaulted
0x180009981  lea     r8, [rsp+130h+Acl]; Dacl
0x180009986  mov     dl, 1; DaclPresent
0x180009988  lea     rcx, [rsp+130h+SecurityDescriptor]; SecurityDescriptor
0x18000998d  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x180009994  nop     dword ptr [rax+rax+00h]
0x180009999  test    eax, eax
0x18000999b  jns     short loc_1800099A7
0x18000999d  mov     edx, 34Fh
0x1800099a2  jmp     loc_1800098D4
0x1800099a7  xor     r9d, r9d
0x1800099aa  mov     [rsp+130h+var_C8], 0
0x1800099b3  lea     rax, [rsp+130h+SecurityDescriptor]
0x1800099b8  xor     r8d, r8d
0x1800099bb  mov     [rsp+130h+var_100], rax
0x1800099c0  lea     rcx, [rsp+130h+var_C8]
0x1800099c5  mov     [rsp+130h+var_108], 8
0x1800099cd  lea     edx, [r9+3]
0x1800099d1  mov     [rsp+130h+pSid], 0; int
0x1800099da  call    cs:__imp_NtCreateWnfStateName
0x1800099e1  nop     dword ptr [rax+rax+00h]
0x1800099e6  test    eax, eax
0x1800099e8  jns     short loc_180009A06
0x1800099ea  mov     rcx, [rbp+38h]; this
0x1800099ee  lea     r8, aOnecoreBaseGen_5; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x1800099f5  mov     r9d, eax; char *
0x1800099f8  mov     edx, 35Ah; void *
0x1800099fd  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180009a02  mov     ebx, eax
0x180009a04  jmp     short loc_180009A4E
0x180009a06  lea     rax, [rsp+130h+var_C8]
0x180009a0b  cmp     rsi, rax
0x180009a0e  jz      short loc_180009A4C
0x180009a10  mov     rdi, [rsp+130h+var_C8]
0x180009a15  mov     [rsp+130h+var_C8], 0
0x180009a1e  call    cs:__imp_GetLastError
0x180009a25  nop     dword ptr [rax+rax+00h]
0x180009a2a  mov     rcx, rsi
0x180009a2d  mov     ebx, eax
0x180009a2f  call    cs:__imp_NtDeleteWnfStateName
0x180009a36  nop     dword ptr [rax+rax+00h]
0x180009a3b  mov     ecx, ebx; dwErrCode
0x180009a3d  call    cs:__imp_SetLastError
0x180009a44  nop     dword ptr [rax+rax+00h]
0x180009a49  mov     [rsi], rdi
0x180009a4c  xor     ebx, ebx
0x180009a4e  lea     rcx, [rsp+130h+var_C8]
0x180009a53  call    cs:__imp_NtDeleteWnfStateName
0x180009a5a  nop     dword ptr [rax+rax+00h]
0x180009a5f  mov     eax, ebx
0x180009a61  mov     rcx, [rbp+30h+var_20]
0x180009a65  xor     rcx, rsp; StackCookie
0x180009a68  call    __security_check_cookie
0x180009a6d  mov     rbx, [rsp+130h+arg_18]
0x180009a75  add     rsp, 120h
0x180009a7c  pop     rdi
0x180009a7d  pop     rsi
0x180009a7e  pop     rbp
0x180009a7f  retn
```
