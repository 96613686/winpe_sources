# EnsureServiceLogonPrivilege(void *)

- ea: `0x180060d6c`
- end: `0x180060eb4`
- name: `?EnsureServiceLogonPrivilege@@YAJPEAX@Z`
- size: `328`
- prototype: `__int64 __fastcall(PSID AccountSid)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180060cc0`

## callees

- `0x180060d6c`

## import_xrefs

- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180060dc0`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180060dc0`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180060e97`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180060e97`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaAddAccountRights` at `0x180060df8`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaAddAccountRights` at `0x180060e29`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaAddAccountRights` at `0x180060e56`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaAddAccountRights` at `0x180060e83`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaAddAccountRights` at `0x180060df8`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaAddAccountRights` at `0x180060e29`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaAddAccountRights` at `0x180060e56`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaAddAccountRights` at `0x180060e83`

## string_xrefs

- `0x180060dd9`: `SeServiceLogonRight`
- `0x180060e0c`: `SeAssignPrimaryTokenPrivilege`
- `0x180060e39`: `SeIncreaseQuotaPrivilege`
- `0x180060e66`: `SeAuditPrivilege`

## pseudocode

```c
__int64 __fastcall EnsureServiceLogonPrivilege(PSID AccountSid)
{
  NTSTATUS v2; // ebx
  unsigned int v3; // ebx
  NTSTATUS v4; // eax
  struct _LSA_UNICODE_STRING UserRights; // [rsp+20h] [rbp-19h] BYREF
  struct _LSA_UNICODE_STRING v7; // [rsp+30h] [rbp-9h] BYREF
  struct _LSA_UNICODE_STRING v8; // [rsp+40h] [rbp+7h] BYREF
  struct _LSA_UNICODE_STRING v9; // [rsp+50h] [rbp+17h] BYREF
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp+27h] BYREF
  PVOID PolicyHandle; // [rsp+A8h] [rbp+6Fh] BYREF

  PolicyHandle = 0;
  UserRights = 0;
  v7 = 0;
  v8 = 0;
  v9 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v2 = LsaOpenPolicy(0, &ObjectAttributes, 0x810u, &PolicyHandle);
  if ( !v2 )
  {
    UserRights.Buffer = L"SeServiceLogonRight";
    *(_DWORD *)&UserRights.Length = 2621478;
    v3 = LsaAddAccountRights(PolicyHandle, AccountSid, &UserRights, 1u);
    if ( !v3 )
    {
      v7.Buffer = L"SeAssignPrimaryTokenPrivilege";
      *(_DWORD *)&v7.Length = 3932218;
      v3 = LsaAddAccountRights(PolicyHandle, AccountSid, &v7, 1u);
      if ( !v3 )
      {
        v8.Buffer = L"SeIncreaseQuotaPrivilege";
        *(_DWORD *)&v8.Length = 3276848;
        v3 = LsaAddAccountRights(PolicyHandle, AccountSid, &v8, 1u);
        if ( !v3 )
        {
          v9.Buffer = L"SeAuditPrivilege";
          *(_DWORD *)&v9.Length = 2228256;
          v4 = LsaAddAccountRights(PolicyHandle, AccountSid, &v9, 1u);
          if ( !v4 )
          {
LABEL_9:
            LsaClose(PolicyHandle);
            return v3;
          }
          v3 = v4;
        }
      }
    }
    v3 |= 0x10000000u;
    goto LABEL_9;
  }
  return v2 | 0x10000000u;
}

```

## disassembly

```asm
0x180060d6c  mov     [rsp-8+arg_0], rbx
0x180060d71  mov     [rsp-8+arg_10], rdi
0x180060d76  push    rbp
0x180060d77  lea     rbp, [rsp-57h]
0x180060d7c  sub     rsp, 90h
0x180060d83  xorps   xmm0, xmm0
0x180060d86  mov     [rbp+57h+PolicyHandle], 0
0x180060d8e  xorps   xmm1, xmm1
0x180060d91  lea     r9, [rbp+57h+PolicyHandle]; PolicyHandle
0x180060d95  mov     rdi, rcx
0x180060d98  lea     rdx, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180060d9c  xor     ecx, ecx; SystemName
0x180060d9e  mov     r8d, 810h; DesiredAccess
0x180060da4  movups  xmmword ptr [rbp+57h+UserRights.Length], xmm0
0x180060da8  movups  xmmword ptr [rbp+57h+var_60.Length], xmm1
0x180060dac  movups  xmmword ptr [rbp+57h+var_50.Length], xmm0
0x180060db0  movups  xmmword ptr [rbp+57h+var_40.Length], xmm1
0x180060db4  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180060db8  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180060dbc  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180060dc0  call    cs:__imp_LsaOpenPolicy
0x180060dc6  mov     ebx, eax
0x180060dc8  test    eax, eax
0x180060dca  jz      short loc_180060DD5
0x180060dcc  bts     ebx, 1Ch
0x180060dd0  jmp     loc_180060E9D
0x180060dd5  mov     rcx, [rbp+57h+PolicyHandle]; PolicyHandle
0x180060dd9  lea     rax, aSeservicelogon; "SeServiceLogonRight"
0x180060de0  mov     r9d, 1; CountOfRights
0x180060de6  mov     [rbp+57h+UserRights.Buffer], rax
0x180060dea  lea     r8, [rbp+57h+UserRights]; UserRights
0x180060dee  mov     dword ptr [rbp+57h+UserRights.Length], 280026h
0x180060df5  mov     rdx, rdi; AccountSid
0x180060df8  call    cs:__imp_LsaAddAccountRights
0x180060dfe  mov     ebx, eax
0x180060e00  test    eax, eax
0x180060e02  jnz     loc_180060E8F
0x180060e08  mov     rcx, [rbp+57h+PolicyHandle]; PolicyHandle
0x180060e0c  lea     rax, aSeassignprimar; "SeAssignPrimaryTokenPrivilege"
0x180060e13  lea     r9d, [rbx+1]; CountOfRights
0x180060e17  mov     [rbp+57h+var_60.Buffer], rax
0x180060e1b  lea     r8, [rbp+57h+var_60]; UserRights
0x180060e1f  mov     dword ptr [rbp+57h+var_60.Length], 3C003Ah
0x180060e26  mov     rdx, rdi; AccountSid
0x180060e29  call    cs:__imp_LsaAddAccountRights
0x180060e2f  mov     ebx, eax
0x180060e31  test    eax, eax
0x180060e33  jnz     short loc_180060E8F
0x180060e35  mov     rcx, [rbp+57h+PolicyHandle]; PolicyHandle
0x180060e39  lea     rax, aSeincreasequot; "SeIncreaseQuotaPrivilege"
0x180060e40  lea     r9d, [rbx+1]; CountOfRights
0x180060e44  mov     [rbp+57h+var_50.Buffer], rax
0x180060e48  lea     r8, [rbp+57h+var_50]; UserRights
0x180060e4c  mov     dword ptr [rbp+57h+var_50.Length], 320030h
0x180060e53  mov     rdx, rdi; AccountSid
0x180060e56  call    cs:__imp_LsaAddAccountRights
0x180060e5c  mov     ebx, eax
0x180060e5e  test    eax, eax
0x180060e60  jnz     short loc_180060E8F
0x180060e62  mov     rcx, [rbp+57h+PolicyHandle]; PolicyHandle
0x180060e66  lea     rax, aSeauditprivile; "SeAuditPrivilege"
0x180060e6d  lea     r9d, [rbx+1]; CountOfRights
0x180060e71  mov     [rbp+57h+var_40.Buffer], rax
0x180060e75  lea     r8, [rbp+57h+var_40]; UserRights
0x180060e79  mov     dword ptr [rbp+57h+var_40.Length], 220020h
0x180060e80  mov     rdx, rdi; AccountSid
0x180060e83  call    cs:__imp_LsaAddAccountRights
0x180060e89  test    eax, eax
0x180060e8b  jz      short loc_180060E93
0x180060e8d  mov     ebx, eax
0x180060e8f  bts     ebx, 1Ch
0x180060e93  mov     rcx, [rbp+57h+PolicyHandle]; ObjectHandle
0x180060e97  call    cs:__imp_LsaClose
0x180060e9d  lea     r11, [rsp+90h+var_s0]
0x180060ea5  mov     eax, ebx
0x180060ea7  mov     rbx, [r11+10h]
0x180060eab  mov     rdi, [r11+20h]
0x180060eaf  mov     rsp, r11
0x180060eb2  pop     rbp
0x180060eb3  retn
```
