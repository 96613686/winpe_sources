# EtwpSetOrAddAce(_GUID *,ulong,void *,ulong,uchar)

- ea: `0x180013e28`
- end: `0x1800140c6`
- name: `?EtwpSetOrAddAce@@YAKPEAU_GUID@@KPEAXKE@Z`
- size: `670`
- prototype: `unsigned int __usercall@<eax>(struct _GUID *@<rcx>, unsigned int@<edx>, void *@<r8>, unsigned int@<r9d>, unsigned __int8)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000b970`

## callees

- `0x180001560`
- `0x180001eb2`
- `0x180001ff0`
- `0x180002014`
- `0x18000bbe0`
- `0x180013c30`
- `0x180013d90`
- `0x180013e28`
- `0x1800140cc`
- `0x180015834`

## import_xrefs

- `ntdll!RtlCreateAcl` at `0x18001400f`
- `ntdll!RtlCreateAcl` at `0x18001400f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013e94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013f5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001403e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013e94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013f5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001403e`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180013e8a`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180013e8a`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x180013f48`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x180013f48`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180013f50`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180013f50`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180013f85`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180013f85`
- `api-ms-win-security-base-l1-1-0!AddAccessDeniedAce` at `0x18001402c`
- `api-ms-win-security-base-l1-1-0!AddAccessDeniedAce` at `0x18001402c`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180014034`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180014034`

## pseudocode

```c
DWORD __fastcall EtwpSetOrAddAce(struct _GUID *a1, int a2, void *a3, DWORD a4, unsigned __int8 a5)
{
  DWORD v6; // r12d
  PSID v7; // r14
  unsigned int v9; // edx
  DWORD result; // eax
  void *v11; // r15
  ULONG v12; // ebx
  void *v13; // rax
  WINBOOL v14; // eax
  DWORD LastError; // esi
  struct _ACL *p_Acl; // rdi
  WORD AclSize; // bx
  WORD v19; // r14
  __int16 v20; // bx
  struct _ACL *v21; // rax
  BOOL v22; // eax
  DWORD v23; // eax
  unsigned int v24; // r8d
  ULONG Size; // [rsp+20h] [rbp-E0h] BYREF
  WINBOOL Size_4; // [rsp+24h] [rbp-DCh] BYREF
  WINBOOL bSaclPresent; // [rsp+28h] [rbp-D8h] BYREF
  unsigned int v28; // [rsp+2Ch] [rbp-D4h] BYREF
  PACL pSacl; // [rsp+30h] [rbp-D0h] BYREF
  DWORD v30; // [rsp+38h] [rbp-C8h]
  PSID pSid; // [rsp+40h] [rbp-C0h]
  unsigned __int16 v32[40]; // [rsp+50h] [rbp-B0h] BYREF
  struct _ACL Acl; // [rsp+A0h] [rbp-60h] BYREF

  v30 = a4;
  pSid = a3;
  v6 = a4;
  pSacl = 0;
  v7 = a3;
  v28 = 0;
  Size = 0;
  if ( !IsValidSid(a3) )
    return GetLastError();
  EtwpGuidToString(v32, v9, a1);
  result = EtwpChangePrivs(1u, &v28);
  if ( !result )
  {
    v11 = 0;
    Size = 1024;
    while ( 1 )
    {
      operator delete(v11);
      v12 = Size;
      v13 = operator new(Size, (const struct std::nothrow_t *)&std::nothrow);
      v11 = v13;
      if ( !v13 )
        break;
      memset_0(v13, 0, v12);
      v14 = EventAccessQuery(a1, v11, &Size);
      LastError = v14;
      if ( v14 != 234 )
      {
        if ( v14 )
        {
LABEL_34:
          operator delete(v11);
          goto LABEL_36;
        }
        if ( (unsigned int)(a2 - 2) <= 1 )
        {
          bSaclPresent = v14;
          Size_4 = v14;
          if ( !(a2 == 3
               ? GetSecurityDescriptorSacl(v11, &bSaclPresent, &pSacl, &Size_4)
               : GetSecurityDescriptorDacl(v11, &bSaclPresent, &pSacl, &Size_4)) )
          {
            LastError = GetLastError();
            goto LABEL_34;
          }
        }
        p_Acl = &Acl;
        LastError = 8;
        if ( pSacl )
        {
          AclSize = pSacl->AclSize;
          v19 = AclSize + GetLengthSid(v7) + 8;
          if ( v19 <= AclSize )
          {
            LastError = 122;
            goto LABEL_34;
          }
          v20 = 512;
          if ( v19 > 0x200u )
          {
            v21 = (struct _ACL *)operator new(v19, (const struct std::nothrow_t *)&std::nothrow);
            p_Acl = v21;
            if ( v21 )
            {
              v20 = v19;
              memset_0(v21, 0, v19);
              v6 = v30;
              goto LABEL_20;
            }
LABEL_31:
            if ( p_Acl != &Acl )
            {
              if ( p_Acl )
                operator delete(p_Acl);
            }
            goto LABEL_34;
          }
LABEL_20:
          memcpy_0(p_Acl, pSacl, pSacl->AclSize);
          v7 = pSid;
          p_Acl->AclSize = v20;
        }
        else
        {
          RtlCreateAcl(&Acl, 0x200u, 2u);
        }
        if ( a5 )
          v22 = AddAccessAllowedAce(p_Acl, 2u, v6, v7);
        else
          v22 = AddAccessDeniedAce(p_Acl, 2u, v6, v7);
        if ( v22 )
        {
          v24 = 4;
          if ( ((a2 - 1) & 0xFFFFFFFD) == 0 )
            v24 = 8;
          v23 = EtwpSetWmiGuidSecurity(v32, p_Acl, v24);
        }
        else
        {
          v23 = GetLastError();
        }
        LastError = v23;
        goto LABEL_31;
      }
    }
    LastError = 14;
LABEL_36:
    EtwpChangePrivs(0, &v28);
    return LastError;
  }
  return result;
}

```

## disassembly

```asm
0x180013e28  mov     [rsp-8+arg_8], rbx
0x180013e2d  push    rbp
0x180013e2e  push    rsi
0x180013e2f  push    rdi
0x180013e30  push    r12
0x180013e32  push    r13
0x180013e34  push    r14
0x180013e36  push    r15
0x180013e38  lea     rbp, [rsp-1B0h]
0x180013e40  sub     rsp, 2B0h
0x180013e47  mov     rax, cs:__security_cookie
0x180013e4e  xor     rax, rsp
0x180013e51  mov     [rbp+1E0h+var_40], rax
0x180013e58  mov     rdi, rcx
0x180013e5b  mov     [rsp+2E0h+var_2A8], r9d
0x180013e60  mov     rcx, r8; pSid
0x180013e63  mov     [rsp+2E0h+pSid], r8
0x180013e68  mov     r12d, r9d
0x180013e6b  mov     [rsp+2E0h+pSacl], 0
0x180013e74  mov     r14, r8
0x180013e77  mov     [rsp+2E0h+var_2B4], 0
0x180013e7f  mov     r13d, edx
0x180013e82  mov     dword ptr [rsp+2E0h+Size], 0
0x180013e8a  call    cs:__imp_IsValidSid
0x180013e90  test    eax, eax
0x180013e92  jnz     short loc_180013E9F
0x180013e94  call    cs:__imp_GetLastError
0x180013e9a  jmp     loc_18001409C
0x180013e9f  mov     r8, rdi; struct _GUID *
0x180013ea2  lea     rcx, [rsp+2E0h+var_290]; unsigned __int16 *
0x180013ea7  call    ?EtwpGuidToString@@YAPEAGPEAGKPEBU_GUID@@@Z; EtwpGuidToString(ushort *,ulong,_GUID const *)
0x180013eac  lea     rdx, [rsp+2E0h+var_2B4]; unsigned int *
0x180013eb1  mov     cl, 1; unsigned __int8
0x180013eb3  call    ?EtwpChangePrivs@@YAKEPEAK@Z; EtwpChangePrivs(uchar,ulong *)
0x180013eb8  test    eax, eax
0x180013eba  jnz     loc_18001409C
0x180013ec0  xor     r15d, r15d
0x180013ec3  mov     dword ptr [rsp+2E0h+Size], 400h
0x180013ecb  mov     rcx, r15; Block
0x180013ece  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180013ed3  mov     ebx, dword ptr [rsp+2E0h+Size]
0x180013ed7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180013ede  mov     ecx, ebx; unsigned __int64
0x180013ee0  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180013ee5  mov     r15, rax
0x180013ee8  test    rax, rax
0x180013eeb  jz      loc_180014089
0x180013ef1  mov     r8d, ebx; Size
0x180013ef4  xor     edx, edx; Val
0x180013ef6  mov     rcx, rax; void *
0x180013ef9  call    memset_0
0x180013efe  lea     r8, [rsp+2E0h+Size]; BufferSize
0x180013f03  mov     rdx, r15; Buffer
0x180013f06  mov     rcx, rdi; Guid
0x180013f09  call    EventAccessQuery
0x180013f0e  mov     esi, eax
0x180013f10  cmp     eax, 0EAh
0x180013f15  jz      short loc_180013ECB
0x180013f17  test    eax, eax
0x180013f19  jnz     loc_18001407F
0x180013f1f  lea     eax, [r13-2]
0x180013f23  cmp     eax, 1
0x180013f26  ja      short loc_180013F67
0x180013f28  mov     [rsp+2E0h+bSaclPresent], esi
0x180013f2c  lea     r9, [rsp+2E0h+Size+4]; lpbDaclDefaulted
0x180013f31  mov     dword ptr [rsp+2E0h+Size+4], esi
0x180013f35  lea     r8, [rsp+2E0h+pSacl]; pDacl
0x180013f3a  lea     rdx, [rsp+2E0h+bSaclPresent]; lpbDaclPresent
0x180013f3f  mov     rcx, r15; pSecurityDescriptor
0x180013f42  cmp     r13d, 3
0x180013f46  jnz     short loc_180013F50
0x180013f48  call    cs:__imp_GetSecurityDescriptorSacl
0x180013f4e  jmp     short loc_180013F56
0x180013f50  call    cs:__imp_GetSecurityDescriptorDacl
0x180013f56  test    eax, eax
0x180013f58  jnz     short loc_180013F67
0x180013f5a  call    cs:__imp_GetLastError
0x180013f60  mov     esi, eax
0x180013f62  jmp     loc_18001407F
0x180013f67  mov     rbx, [rsp+2E0h+pSacl]
0x180013f6c  lea     rdi, [rbp+1E0h+Acl]
0x180013f70  mov     esi, 8
0x180013f75  test    rbx, rbx
0x180013f78  jz      loc_180014000
0x180013f7e  movzx   ebx, word ptr [rbx+2]
0x180013f82  mov     rcx, r14; pSid
0x180013f85  call    cs:__imp_GetLengthSid
0x180013f8b  lea     r14d, [rbx+rax]
0x180013f8f  add     r14w, si
0x180013f93  cmp     r14w, bx
0x180013f97  ja      short loc_180013FA3
0x180013f99  mov     esi, 7Ah ; 'z'
0x180013f9e  jmp     loc_18001407F
0x180013fa3  mov     ebx, 200h
0x180013fa8  cmp     r14w, bx
0x180013fac  jbe     short loc_180013FE3
0x180013fae  movzx   r12d, r14w
0x180013fb2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180013fb9  mov     ecx, r12d; unsigned __int64
0x180013fbc  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180013fc1  mov     rdi, rax
0x180013fc4  test    rax, rax
0x180013fc7  jz      loc_180014069
0x180013fcd  mov     r8d, r12d; Size
0x180013fd0  xor     edx, edx; Val
0x180013fd2  mov     rcx, rax; void *
0x180013fd5  movzx   ebx, r14w
0x180013fd9  call    memset_0
0x180013fde  mov     r12d, [rsp+2E0h+var_2A8]
0x180013fe3  mov     rdx, [rsp+2E0h+pSacl]; Src
0x180013fe8  mov     rcx, rdi; void *
0x180013feb  movzx   r8d, word ptr [rdx+2]; Size
0x180013ff0  call    memcpy_0
0x180013ff5  mov     r14, [rsp+2E0h+pSid]
0x180013ffa  mov     [rdi+2], bx
0x180013ffe  jmp     short loc_180014015
0x180014000  mov     edx, 200h; AclSize
0x180014005  lea     rcx, [rbp+1E0h+Acl]; Acl
0x180014009  mov     r8d, 2; AclRevision
0x18001400f  call    cs:__imp_RtlCreateAcl
0x180014015  cmp     [rbp+1E0h+arg_20], 0
0x18001401c  mov     r9, r14; pSid
0x18001401f  mov     r8d, r12d; AccessMask
0x180014022  mov     edx, 2; dwAceRevision
0x180014027  mov     rcx, rdi; pAcl
0x18001402a  jnz     short loc_180014034
0x18001402c  call    cs:__imp_AddAccessDeniedAce
0x180014032  jmp     short loc_18001403A
0x180014034  call    cs:__imp_AddAccessAllowedAce
0x18001403a  test    eax, eax
0x18001403c  jnz     short loc_180014046
0x18001403e  call    cs:__imp_GetLastError
0x180014044  jmp     short loc_180014067
0x180014046  lea     eax, [r13-1]
0x18001404a  mov     rdx, rdi; struct _ACL *
0x18001404d  lea     rcx, [rsp+2E0h+var_290]; unsigned __int16 *
0x180014052  mov     r8d, 4
0x180014058  test    eax, 0FFFFFFFDh
0x18001405d  jnz     short loc_180014062
0x18001405f  mov     r8d, esi; unsigned int
0x180014062  call    ?EtwpSetWmiGuidSecurity@@YAKPEAGPEAU_ACL@@K@Z; EtwpSetWmiGuidSecurity(ushort *,_ACL *,ulong)
0x180014067  mov     esi, eax
0x180014069  lea     rax, [rbp+1E0h+Acl]
0x18001406d  cmp     rdi, rax
0x180014070  jz      short loc_18001407F
0x180014072  test    rdi, rdi
0x180014075  jz      short loc_18001407F
0x180014077  mov     rcx, rdi; Block
0x18001407a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001407f  mov     rcx, r15; Block
0x180014082  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180014087  jmp     short loc_18001408E
0x180014089  mov     esi, 0Eh
0x18001408e  lea     rdx, [rsp+2E0h+var_2B4]; unsigned int *
0x180014093  xor     ecx, ecx; unsigned __int8
0x180014095  call    ?EtwpChangePrivs@@YAKEPEAK@Z; EtwpChangePrivs(uchar,ulong *)
0x18001409a  mov     eax, esi
0x18001409c  mov     rcx, [rbp+1E0h+var_40]
0x1800140a3  xor     rcx, rsp; StackCookie
0x1800140a6  call    __security_check_cookie
0x1800140ab  mov     rbx, [rsp+2E0h+arg_8]
0x1800140b3  add     rsp, 2B0h
0x1800140ba  pop     r15
0x1800140bc  pop     r14
0x1800140be  pop     r13
0x1800140c0  pop     r12
0x1800140c2  pop     rdi
0x1800140c3  pop     rsi
0x1800140c4  pop     rbp
0x1800140c5  retn
```
