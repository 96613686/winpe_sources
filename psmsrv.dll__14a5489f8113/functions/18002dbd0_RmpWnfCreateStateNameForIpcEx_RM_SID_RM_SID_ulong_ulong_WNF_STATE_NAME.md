# RmpWnfCreateStateNameForIpcEx(_RM_SID *,_RM_SID *,ulong,ulong,_WNF_STATE_NAME *)

- ea: `0x18002dbd0`
- end: `0x18002dd2b`
- name: `?RmpWnfCreateStateNameForIpcEx@@YAJPEAT_RM_SID@@0KKPEAU_WNF_STATE_NAME@@@Z`
- size: `347`
- prototype: `__int64 __fastcall(PSID pSid, PSID, __int64, __int64, struct _WNF_STATE_NAME *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800241e4`

## callees

- `0x18001b7e0`
- `0x18001c10c`
- `0x18002dbd0`

## import_xrefs

- `ntdll!NtCreateWnfStateName` at `0x18002dcf8`
- `ntdll!NtCreateWnfStateName` at `0x18002dcf8`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18002dcc4`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18002dcc4`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x18002dc8c`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x18002dcaf`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x18002dc8c`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x18002dcaf`
- `ntdll!RtlCreateAcl` at `0x18002dc65`
- `ntdll!RtlCreateAcl` at `0x18002dc65`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18002dc45`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18002dc45`

## pseudocode

```c
__int64 __fastcall RmpWnfCreateStateNameForIpcEx(
        PSID pSid,
        PSID a2,
        __int64 a3,
        __int64 a4,
        struct _WNF_STATE_NAME *a5)
{
  NTSTATUS WnfStateName; // ecx
  _OWORD SecurityDescriptor[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v10; // [rsp+60h] [rbp-A0h]
  struct _ACL Acl; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v12[80]; // [rsp+1B0h] [rbp+B0h] BYREF

  memset_0(v12, 0, 0x44u);
  memset_0(&Acl, 0, 0x138u);
  v10 = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  WnfStateName = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
  if ( WnfStateName >= 0 )
  {
    WnfStateName = RtlCreateAcl(&Acl, 0x138u, 2u);
    if ( WnfStateName >= 0 )
    {
      WnfStateName = RtlAddAccessAllowedAceEx(&Acl, 2u, 0, 0x10000000u, pSid);
      if ( WnfStateName >= 0 )
      {
        RtlAddAccessAllowedAceEx(&Acl, 2u, 0, 0x80000000, a2);
        WnfStateName = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, &Acl, 0);
        if ( WnfStateName >= 0 )
        {
          WnfStateName = NtCreateWnfStateName(a5, 3, 0);
          if ( WnfStateName >= 0 )
            return 0;
        }
      }
    }
  }
  return (unsigned int)WnfStateName;
}

```

## disassembly

```asm
0x18002dbd0  mov     [rsp-8+arg_10], rbx
0x18002dbd5  push    rbp
0x18002dbd6  push    rsi
0x18002dbd7  push    rdi
0x18002dbd8  lea     rbp, [rsp-110h]
0x18002dbe0  sub     rsp, 210h
0x18002dbe7  mov     rax, cs:__security_cookie
0x18002dbee  xor     rax, rsp
0x18002dbf1  mov     [rbp+120h+var_20], rax
0x18002dbf8  mov     rdi, [rbp+120h+arg_20]
0x18002dbff  mov     rsi, rdx
0x18002dc02  xor     edx, edx; Val
0x18002dc04  mov     rbx, rcx
0x18002dc07  lea     rcx, [rbp+120h+var_70]; void *
0x18002dc0e  lea     r8d, [rdx+44h]; Size
0x18002dc12  call    memset_0
0x18002dc17  xor     edx, edx; Val
0x18002dc19  lea     rcx, [rsp+220h+Acl]; void *
0x18002dc1e  mov     r8d, 138h; Size
0x18002dc24  call    memset_0
0x18002dc29  xor     eax, eax
0x18002dc2b  lea     rcx, [rsp+220h+SecurityDescriptor]; SecurityDescriptor
0x18002dc30  xorps   xmm0, xmm0
0x18002dc33  mov     [rsp+220h+var_1C0], rax
0x18002dc38  movups  [rsp+220h+SecurityDescriptor], xmm0
0x18002dc3d  lea     edx, [rax+1]; Revision
0x18002dc40  movups  [rsp+220h+var_1D0], xmm0
0x18002dc45  call    cs:__imp_RtlCreateSecurityDescriptor
0x18002dc4b  mov     ecx, eax
0x18002dc4d  test    eax, eax
0x18002dc4f  js      loc_18002DD07
0x18002dc55  mov     edx, 138h; AclSize
0x18002dc5a  lea     rcx, [rsp+220h+Acl]; Acl
0x18002dc5f  mov     r8d, 2; AclRevision
0x18002dc65  call    cs:__imp_RtlCreateAcl
0x18002dc6b  mov     ecx, eax
0x18002dc6d  test    eax, eax
0x18002dc6f  js      loc_18002DD07
0x18002dc75  xor     r8d, r8d; AceFlags
0x18002dc78  mov     [rsp+220h+pSid], rbx; pSid
0x18002dc7d  mov     r9d, 10000000h; AccessMask
0x18002dc83  lea     rcx, [rsp+220h+Acl]; pAcl
0x18002dc88  lea     edx, [r8+2]; dwAceRevision
0x18002dc8c  call    cs:__imp_RtlAddAccessAllowedAceEx
0x18002dc92  mov     ecx, eax
0x18002dc94  test    eax, eax
0x18002dc96  js      short loc_18002DD07
0x18002dc98  xor     r8d, r8d; AceFlags
0x18002dc9b  mov     [rsp+220h+pSid], rsi; pSid
0x18002dca0  mov     r9d, 80000000h; AccessMask
0x18002dca6  lea     rcx, [rsp+220h+Acl]; pAcl
0x18002dcab  lea     edx, [r8+2]; dwAceRevision
0x18002dcaf  call    cs:__imp_RtlAddAccessAllowedAceEx
0x18002dcb5  xor     r9d, r9d; DaclDefaulted
0x18002dcb8  lea     r8, [rsp+220h+Acl]; Dacl
0x18002dcbd  mov     dl, 1; DaclPresent
0x18002dcbf  lea     rcx, [rsp+220h+SecurityDescriptor]; SecurityDescriptor
0x18002dcc4  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x18002dcca  mov     ecx, eax
0x18002dccc  test    eax, eax
0x18002dcce  js      short loc_18002DD07
0x18002dcd0  xor     r9d, r9d
0x18002dcd3  lea     rax, [rsp+220h+SecurityDescriptor]
0x18002dcd8  mov     [rsp+220h+var_1F0], rax
0x18002dcdd  xor     r8d, r8d
0x18002dce0  mov     [rsp+220h+var_1F8], 260h
0x18002dce8  mov     rcx, rdi
0x18002dceb  mov     [rsp+220h+pSid], 0
0x18002dcf4  lea     edx, [r9+3]
0x18002dcf8  call    cs:__imp_NtCreateWnfStateName
0x18002dcfe  mov     ecx, eax
0x18002dd00  xor     eax, eax
0x18002dd02  test    ecx, ecx
0x18002dd04  cmovns  ecx, eax
0x18002dd07  mov     eax, ecx
0x18002dd09  mov     rcx, [rbp+120h+var_20]
0x18002dd10  xor     rcx, rsp; StackCookie
0x18002dd13  call    __security_check_cookie
0x18002dd18  mov     rbx, [rsp+220h+arg_10]
0x18002dd20  add     rsp, 210h
0x18002dd27  pop     rdi
0x18002dd28  pop     rsi
0x18002dd29  pop     rbp
0x18002dd2a  retn
```
