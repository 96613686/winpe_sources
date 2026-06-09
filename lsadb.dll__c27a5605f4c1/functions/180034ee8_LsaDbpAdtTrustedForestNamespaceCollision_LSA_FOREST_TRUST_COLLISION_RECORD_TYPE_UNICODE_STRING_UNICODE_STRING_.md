# LsaDbpAdtTrustedForestNamespaceCollision(LSA_FOREST_TRUST_COLLISION_RECORD_TYPE,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,void *,ulong)

- ea: `0x180034ee8`
- end: `0x1800350e2`
- name: `?LsaDbpAdtTrustedForestNamespaceCollision@@YAJW4LSA_FOREST_TRUST_COLLISION_RECORD_TYPE@@PEAU_UNICODE_STRING@@1111PEAXK@Z`
- size: `506`
- prototype: `__int64 __fastcall(enum LSA_FOREST_TRUST_COLLISION_RECORD_TYPE, struct _UNICODE_STRING *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, void *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800215a4`

## callees

- `0x180001670`
- `0x180001fb8`
- `0x180002234`
- `0x180002338`
- `0x180034ee8`

## import_xrefs

- `LSASRV!LsapGetWellKnownSid` at `0x180034fd1`
- `LSASRV!LsapGetWellKnownSid` at `0x180034fd1`
- `LSASRV!LsapAdtWriteLog` at `0x1800350a1`
- `LSASRV!LsapAdtWriteLog` at `0x1800350a1`
- `LSASRV!LsapAuditFailed` at `0x1800350b6`
- `LSASRV!LsapAuditFailed` at `0x1800350b6`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapAdtAuditingEnabledBySubCategory` at `0x180034fb3`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapAdtAuditingEnabledBySubCategory` at `0x180034fb3`
- `ext-ms-win-security-lsaadtpriv-l1-1-0!LsapAdtInitParametersArray` at `0x18003508d`
- `ext-ms-win-security-lsaadtpriv-l1-1-0!LsapAdtInitParametersArray` at `0x18003508d`

## pseudocode

```c
__int64 __fastcall LsaDbpAdtTrustedForestNamespaceCollision(
        enum LSA_FOREST_TRUST_COLLISION_RECORD_TYPE a1,
        struct _UNICODE_STRING *a2,
        struct _UNICODE_STRING *a3,
        struct _UNICODE_STRING *a4,
        struct _UNICODE_STRING *a5,
        struct _UNICODE_STRING *a6,
        void *a7,
        unsigned int a8)
{
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r8
  int inited; // ebx
  __int64 WellKnownSid; // rax
  __int16 v18; // [rsp+20h] [rbp-528h]
  __int16 v19; // [rsp+28h] [rbp-520h]
  _BYTE v20[1056]; // [rsp+D0h] [rbp-478h] BYREF

  memset_0(v20, 0, 0x418u);
  if ( a2 && a2->MaximumLength < a2->Length
    || a3 && a3->MaximumLength < a3->Length
    || a4 && a4->MaximumLength < a4->Length
    || a5 && a5->MaximumLength < a5->Length
    || a6 && a6->MaximumLength < a6->Length )
  {
    inited = -1073741811;
LABEL_19:
    LsapAuditFailed((unsigned int)inited);
    return (unsigned int)inited;
  }
  inited = 0;
  if ( (unsigned __int8)IsLsapAdtAuditingEnabledByLogonIdPresent(v13, v12, v14)
    && (unsigned __int8)LsapAdtAuditingEnabledBySubCategory(141, 8) )
  {
    if ( !(unsigned __int8)IsLsapAdtInitParametersArrayPresent() )
    {
      inited = -1073741822;
      goto LABEL_19;
    }
    WellKnownSid = LsapGetWellKnownSid(15);
    v19 = 10;
    v18 = 8;
    inited = LsapAdtInitParametersArray(
               v20,
               6,
               4864,
               141,
               v18,
               v19,
               4,
               WellKnownSid,
               1,
               &LsaDbpSubsystemName,
               27,
               a1,
               1,
               a2,
               1,
               a3,
               1,
               a4,
               1,
               a5,
               1,
               a6,
               4,
               a7,
               27,
               a8);
    if ( inited < 0 )
      goto LABEL_19;
    inited = LsapAdtWriteLog(v20);
    if ( inited < 0 )
      goto LABEL_19;
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180034ee8  push    rbx
0x180034eea  push    rbp
0x180034eeb  push    rsi
0x180034eec  push    rdi
0x180034eed  push    r12
0x180034eef  push    r13
0x180034ef1  push    r14
0x180034ef3  push    r15
0x180034ef5  sub     rsp, 508h
0x180034efc  mov     rax, cs:__security_cookie
0x180034f03  xor     rax, rsp
0x180034f06  mov     [rsp+548h+var_58], rax
0x180034f0e  mov     rdi, [rsp+548h+arg_28]
0x180034f16  mov     r15, r8
0x180034f19  mov     rsi, [rsp+548h+arg_20]
0x180034f21  mov     rbp, rdx
0x180034f24  mov     r13, [rsp+548h+arg_30]
0x180034f2c  mov     r12d, ecx
0x180034f2f  xor     edx, edx; Val
0x180034f31  lea     rcx, [rsp+548h+var_478]; void *
0x180034f39  mov     r8d, 418h; Size
0x180034f3f  mov     r14, r9
0x180034f42  call    memset_0
0x180034f47  test    rbp, rbp
0x180034f4a  jz      short loc_180034F56
0x180034f4c  movzx   eax, word ptr [rbp+0]
0x180034f50  cmp     [rbp+2], ax
0x180034f54  jb      short loc_180034F92
0x180034f56  test    r15, r15
0x180034f59  jz      short loc_180034F66
0x180034f5b  movzx   eax, word ptr [r15]
0x180034f5f  cmp     [r15+2], ax
0x180034f64  jb      short loc_180034F92
0x180034f66  test    r14, r14
0x180034f69  jz      short loc_180034F76
0x180034f6b  movzx   eax, word ptr [r14]
0x180034f6f  cmp     [r14+2], ax
0x180034f74  jb      short loc_180034F92
0x180034f76  test    rsi, rsi
0x180034f79  jz      short loc_180034F84
0x180034f7b  movzx   eax, word ptr [rsi]
0x180034f7e  cmp     [rsi+2], ax
0x180034f82  jb      short loc_180034F92
0x180034f84  test    rdi, rdi
0x180034f87  jz      short loc_180034F9C
0x180034f89  movzx   eax, word ptr [rdi]
0x180034f8c  cmp     [rdi+2], ax
0x180034f90  jnb     short loc_180034F9C
0x180034f92  mov     ebx, 0C000000Dh
0x180034f97  jmp     loc_1800350B4
0x180034f9c  xor     ebx, ebx
0x180034f9e  call    IsLsapAdtAuditingEnabledByLogonIdPresent
0x180034fa3  test    al, al
0x180034fa5  jz      loc_1800350BC
0x180034fab  lea     edx, [rbx+8]
0x180034fae  mov     ecx, 8Dh
0x180034fb3  call    cs:__imp_LsapAdtAuditingEnabledBySubCategory
0x180034fb9  test    al, al
0x180034fbb  jz      loc_1800350BC
0x180034fc1  call    IsLsapAdtInitParametersArrayPresent
0x180034fc6  test    al, al
0x180034fc8  jz      loc_1800350AF
0x180034fce  lea     ecx, [rbx+0Fh]
0x180034fd1  call    cs:__imp_LsapGetWellKnownSid
0x180034fd7  mov     ecx, [rsp+548h+arg_38]
0x180034fde  lea     edx, [rbx+1]
0x180034fe1  mov     [rsp+548h+var_480], ecx
0x180034fe8  lea     r8d, [rbx+4]
0x180034fec  lea     ecx, [rbx+1Bh]
0x180034fef  mov     r9d, 8Dh
0x180034ff5  mov     [rsp+548h+var_488], ecx
0x180034ffc  mov     [rsp+548h+var_490], r13
0x180035004  mov     [rsp+548h+var_498], r8d
0x18003500c  mov     [rsp+548h+var_4A0], rdi
0x180035014  mov     [rsp+548h+var_4A8], edx
0x18003501b  mov     [rsp+548h+var_4B0], rsi
0x180035023  mov     [rsp+548h+var_4B8], edx
0x18003502a  mov     [rsp+548h+var_4C0], r14
0x180035032  mov     [rsp+548h+var_4C8], edx
0x180035039  mov     [rsp+548h+var_4D0], r15
0x18003503e  mov     [rsp+548h+var_4D8], edx
0x180035042  mov     [rsp+548h+var_4E0], rbp
0x180035047  mov     [rsp+548h+var_4E8], edx
0x18003504b  mov     [rsp+548h+var_4F0], r12d
0x180035050  mov     [rsp+548h+var_4F8], ecx
0x180035054  lea     rcx, ?LsaDbpSubsystemName@@3U_UNICODE_STRING@@A; _UNICODE_STRING LsaDbpSubsystemName
0x18003505b  mov     [rsp+548h+var_500], rcx
0x180035060  lea     rcx, [rsp+548h+var_478]
0x180035068  mov     [rsp+548h+var_508], edx
0x18003506c  lea     edx, [rbx+6]
0x18003506f  mov     [rsp+548h+var_510], rax
0x180035074  mov     [rsp+548h+var_518], r8d
0x180035079  mov     r8d, 1300h
0x18003507f  mov     [rsp+548h+var_520], 0Ah
0x180035086  mov     [rsp+548h+var_528], 8
0x18003508d  call    cs:__imp_LsapAdtInitParametersArray
0x180035093  mov     ebx, eax
0x180035095  test    eax, eax
0x180035097  js      short loc_1800350B4
0x180035099  lea     rcx, [rsp+548h+var_478]
0x1800350a1  call    cs:__imp_LsapAdtWriteLog
0x1800350a7  mov     ebx, eax
0x1800350a9  test    eax, eax
0x1800350ab  jns     short loc_1800350BC
0x1800350ad  jmp     short loc_1800350B4
0x1800350af  mov     ebx, 0C0000002h
0x1800350b4  mov     ecx, ebx
0x1800350b6  call    cs:__imp_LsapAuditFailed
0x1800350bc  mov     eax, ebx
0x1800350be  mov     rcx, [rsp+548h+var_58]
0x1800350c6  xor     rcx, rsp; StackCookie
0x1800350c9  call    __security_check_cookie
0x1800350ce  add     rsp, 508h
0x1800350d5  pop     r15
0x1800350d7  pop     r14
0x1800350d9  pop     r13
0x1800350db  pop     r12
0x1800350dd  pop     rdi
0x1800350de  pop     rsi
0x1800350df  pop     rbp
0x1800350e0  pop     rbx
0x1800350e1  retn
```
