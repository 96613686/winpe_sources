# _CmGetRegKeySecurityDescriptor

- ea: `0x18006d04c`
- end: `0x18006d43b`
- name: `_CmGetRegKeySecurityDescriptor`
- size: `1007`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18006b934`
- `0x18006be2c`

## callees

- `0x18003bc80`
- `0x18006d04c`

## import_xrefs

- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x18006d3d8`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x18006d3d8`
- `ntdll!RtlValidSecurityDescriptor` at `0x18006d379`
- `ntdll!RtlValidSecurityDescriptor` at `0x18006d379`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x18006d35c`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x18006d35c`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x18006d341`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x18006d341`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18006d326`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18006d326`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18006d30a`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18006d30a`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x18006d278`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x18006d2a0`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x18006d2c8`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x18006d2f1`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x18006d278`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x18006d2a0`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x18006d2c8`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x18006d2f1`
- `ntdll!RtlLengthSid` at `0x18006d1e5`
- `ntdll!RtlLengthSid` at `0x18006d1f1`
- `ntdll!RtlLengthSid` at `0x18006d1fd`
- `ntdll!RtlLengthSid` at `0x18006d210`
- `ntdll!RtlLengthSid` at `0x18006d1e5`
- `ntdll!RtlLengthSid` at `0x18006d1f1`
- `ntdll!RtlLengthSid` at `0x18006d1fd`
- `ntdll!RtlLengthSid` at `0x18006d210`
- `ntdll!RtlValidSid` at `0x18006d0e8`
- `ntdll!RtlValidSid` at `0x18006d12a`
- `ntdll!RtlValidSid` at `0x18006d17d`
- `ntdll!RtlValidSid` at `0x18006d1cf`
- `ntdll!RtlValidSid` at `0x18006d0e8`
- `ntdll!RtlValidSid` at `0x18006d12a`
- `ntdll!RtlValidSid` at `0x18006d17d`
- `ntdll!RtlValidSid` at `0x18006d1cf`
- `ntdll!RtlSubAuthoritySid` at `0x18006d0d8`
- `ntdll!RtlSubAuthoritySid` at `0x18006d11d`
- `ntdll!RtlSubAuthoritySid` at `0x18006d15b`
- `ntdll!RtlSubAuthoritySid` at `0x18006d16d`
- `ntdll!RtlSubAuthoritySid` at `0x18006d1b4`
- `ntdll!RtlSubAuthoritySid` at `0x18006d1c3`
- `ntdll!RtlSubAuthoritySid` at `0x18006d0d8`
- `ntdll!RtlSubAuthoritySid` at `0x18006d11d`
- `ntdll!RtlSubAuthoritySid` at `0x18006d15b`
- `ntdll!RtlSubAuthoritySid` at `0x18006d16d`
- `ntdll!RtlSubAuthoritySid` at `0x18006d1b4`
- `ntdll!RtlSubAuthoritySid` at `0x18006d1c3`
- `ntdll!RtlCreateAcl` at `0x18006d250`
- `ntdll!RtlCreateAcl` at `0x18006d250`
- `ntdll!RtlInitializeSid` at `0x18006d0c2`
- `ntdll!RtlInitializeSid` at `0x18006d107`
- `ntdll!RtlInitializeSid` at `0x18006d145`
- `ntdll!RtlInitializeSid` at `0x18006d19e`
- `ntdll!RtlInitializeSid` at `0x18006d0c2`
- `ntdll!RtlInitializeSid` at `0x18006d107`
- `ntdll!RtlInitializeSid` at `0x18006d145`
- `ntdll!RtlInitializeSid` at `0x18006d19e`
- `ntdll!RtlFreeHeap` at `0x18006d3fb`
- `ntdll!RtlFreeHeap` at `0x18006d413`
- `ntdll!RtlFreeHeap` at `0x18006d3fb`
- `ntdll!RtlFreeHeap` at `0x18006d413`
- `ntdll!RtlAllocateHeap` at `0x18006d230`
- `ntdll!RtlAllocateHeap` at `0x18006d3b8`
- `ntdll!RtlAllocateHeap` at `0x18006d230`
- `ntdll!RtlAllocateHeap` at `0x18006d3b8`
- `ntdll!RtlLengthSecurityDescriptor` at `0x18006d38e`
- `ntdll!RtlLengthSecurityDescriptor` at `0x18006d38e`

## pseudocode

```c
__int64 __fastcall CmGetRegKeySecurityDescriptor(char a1, _QWORD *a2)
{
  NTSTATUS Acl; // ebx
  _BYTE *v5; // rdi
  ULONG v6; // ebx
  ULONG v7; // ebx
  ULONG v8; // ebx
  struct _ACL *Heap; // rax
  struct _ACL *v10; // rsi
  ULONG v11; // eax
  PVOID v12; // rax
  void *v13; // rdi
  ULONG BufferLength; // [rsp+30h] [rbp-79h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+38h] [rbp-71h] BYREF
  __int64 v17; // [rsp+58h] [rbp-51h]
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+60h] [rbp-49h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v19; // [rsp+68h] [rbp-41h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v20; // [rsp+70h] [rbp-39h] BYREF
  _BYTE Owner[16]; // [rsp+78h] [rbp-31h] BYREF
  _BYTE Sid[12]; // [rsp+88h] [rbp-21h] BYREF
  _BYTE pSid[12]; // [rsp+94h] [rbp-15h] BYREF
  _BYTE v24[16]; // [rsp+A0h] [rbp-9h] BYREF

  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  *a2 = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_DWORD *)v19.Value = 0;
  *(_WORD *)&v19.Value[4] = 256;
  *(_DWORD *)v20.Value = 0;
  *(_WORD *)&v20.Value[4] = 3840;
  v17 = 0;
  BufferLength = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  Acl = RtlInitializeSid(Sid, &IdentifierAuthority, 1u);
  if ( Acl < 0 )
    return (unsigned int)Acl;
  *RtlSubAuthoritySid(Sid, 0) = 18;
  if ( !RtlValidSid(Sid) )
    return (unsigned int)-1073741762;
  Acl = RtlInitializeSid(pSid, &v19, 1u);
  if ( Acl < 0 )
    return (unsigned int)Acl;
  *RtlSubAuthoritySid(pSid, 0) = 0;
  if ( !RtlValidSid(pSid) )
    return (unsigned int)-1073741762;
  Acl = RtlInitializeSid(Owner, &IdentifierAuthority, 2u);
  if ( Acl < 0 )
    return (unsigned int)Acl;
  *RtlSubAuthoritySid(Owner, 0) = 32;
  *RtlSubAuthoritySid(Owner, 1u) = 544;
  if ( !RtlValidSid(Owner) )
    return (unsigned int)-1073741762;
  v5 = 0;
  if ( a1 )
  {
    Acl = RtlInitializeSid(v24, &v20, 2u);
    if ( Acl < 0 )
      return (unsigned int)Acl;
    *RtlSubAuthoritySid(v24, 0) = 2;
    *RtlSubAuthoritySid(v24, 1u) = 1;
    if ( RtlValidSid(v24) )
    {
      v5 = v24;
      goto LABEL_12;
    }
    return (unsigned int)-1073741762;
  }
LABEL_12:
  v6 = RtlLengthSid(Sid);
  v7 = RtlLengthSid(pSid) + v6;
  v8 = RtlLengthSid(Owner) + v7 + 32;
  if ( a1 )
    v8 += RtlLengthSid(v5) + 8;
  Heap = (struct _ACL *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v8);
  v10 = Heap;
  if ( Heap )
  {
    Acl = RtlCreateAcl(Heap, v8, 2u);
    if ( Acl >= 0 )
    {
      Acl = RtlAddAccessAllowedAceEx(v10, 2u, 2u, 0xF003Fu, Sid);
      if ( Acl >= 0 )
      {
        Acl = RtlAddAccessAllowedAceEx(v10, 2u, 2u, 0x20019u, pSid);
        if ( Acl >= 0 )
        {
          Acl = RtlAddAccessAllowedAceEx(v10, 2u, 2u, 0xF003Fu, Owner);
          if ( Acl >= 0 )
          {
            if ( !a1 || (Acl = RtlAddAccessAllowedAceEx(v10, 2u, 2u, 0x20019u, v5), Acl >= 0) )
            {
              Acl = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
              if ( Acl >= 0 )
              {
                Acl = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v10, 0);
                if ( Acl >= 0 )
                {
                  Acl = RtlSetOwnerSecurityDescriptor(SecurityDescriptor, Owner, 1u);
                  if ( Acl >= 0 )
                  {
                    Acl = RtlSetGroupSecurityDescriptor(SecurityDescriptor, Owner, 1u);
                    if ( Acl >= 0 )
                    {
                      WORD1(SecurityDescriptor[0]) |= 0x1500u;
                      if ( RtlValidSecurityDescriptor(SecurityDescriptor) )
                      {
                        v11 = RtlLengthSecurityDescriptor(SecurityDescriptor);
                        BufferLength = v11;
                        if ( v11 >= 0x28 )
                        {
                          v12 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v11);
                          v13 = v12;
                          if ( v12 )
                          {
                            Acl = RtlAbsoluteToSelfRelativeSD(SecurityDescriptor, v12, &BufferLength);
                            if ( Acl < 0 )
                              RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v13);
                            else
                              *a2 = v13;
                          }
                          else
                          {
                            Acl = -1073741801;
                          }
                        }
                        else
                        {
                          Acl = -1073741762;
                        }
                      }
                      else
                      {
                        Acl = -1073741595;
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
  }
  else
  {
    return (unsigned int)-1073741801;
  }
  return (unsigned int)Acl;
}

```

## disassembly

```asm
0x18006d04c  push    rbp
0x18006d04e  push    rbx
0x18006d04f  push    rsi
0x18006d050  push    rdi
0x18006d051  push    r12
0x18006d053  push    r13
0x18006d055  push    r14
0x18006d057  push    r15
0x18006d059  lea     rbp, [rsp-1Fh]
0x18006d05e  sub     rsp, 0C8h
0x18006d065  mov     rax, cs:__security_cookie
0x18006d06c  xor     rax, rsp
0x18006d06f  mov     [rbp+57h+var_50], rax
0x18006d073  xor     r12d, r12d
0x18006d076  mov     word ptr [rbp+57h+IdentifierAuthority.Value+4], 500h
0x18006d07c  xorps   xmm0, xmm0
0x18006d07f  mov     [rdx], r12
0x18006d082  mov     r15, rdx
0x18006d085  mov     dword ptr [rbp+57h+IdentifierAuthority.Value], r12d
0x18006d089  mov     r14b, cl
0x18006d08c  mov     dword ptr [rbp+57h+var_98.Value], r12d
0x18006d090  xor     eax, eax
0x18006d092  mov     word ptr [rbp+57h+var_98.Value+4], 100h
0x18006d098  lea     esi, [r12+1]
0x18006d09d  mov     dword ptr [rbp+57h+var_90.Value], r12d
0x18006d0a1  mov     r8b, sil; SubAuthorityCount
0x18006d0a4  mov     word ptr [rbp+57h+var_90.Value+4], 0F00h
0x18006d0aa  lea     rdx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x18006d0ae  mov     [rbp+57h+var_A8], rax
0x18006d0b2  lea     rcx, [rbp+57h+Sid]; Sid
0x18006d0b6  mov     [rbp+57h+BufferLength], r12d
0x18006d0ba  movups  [rbp+57h+SecurityDescriptor], xmm0
0x18006d0be  movups  [rbp+57h+var_B8], xmm0
0x18006d0c2  call    cs:__imp_RtlInitializeSid
0x18006d0c8  mov     ebx, eax
0x18006d0ca  test    eax, eax
0x18006d0cc  js      loc_18006D419
0x18006d0d2  xor     edx, edx; SubAuthority
0x18006d0d4  lea     rcx, [rbp+57h+Sid]; Sid
0x18006d0d8  call    cs:__imp_RtlSubAuthoritySid
0x18006d0de  lea     rcx, [rbp+57h+Sid]; Sid
0x18006d0e2  mov     dword ptr [rax], 12h
0x18006d0e8  call    cs:__imp_RtlValidSid
0x18006d0ee  test    al, al
0x18006d0f0  jnz     short loc_18006D0FC
0x18006d0f2  mov     ebx, 0C000003Eh
0x18006d0f7  jmp     loc_18006D419
0x18006d0fc  mov     r8b, sil; SubAuthorityCount
0x18006d0ff  lea     rdx, [rbp+57h+var_98]; IdentifierAuthority
0x18006d103  lea     rcx, [rbp+57h+var_6C]; Sid
0x18006d107  call    cs:__imp_RtlInitializeSid
0x18006d10d  mov     ebx, eax
0x18006d10f  test    eax, eax
0x18006d111  js      loc_18006D419
0x18006d117  xor     edx, edx; SubAuthority
0x18006d119  lea     rcx, [rbp+57h+var_6C]; Sid
0x18006d11d  call    cs:__imp_RtlSubAuthoritySid
0x18006d123  lea     rcx, [rbp+57h+var_6C]; Sid
0x18006d127  mov     [rax], r12d
0x18006d12a  call    cs:__imp_RtlValidSid
0x18006d130  test    al, al
0x18006d132  jz      short loc_18006D0F2
0x18006d134  mov     r13d, 2
0x18006d13a  lea     rdx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x18006d13e  mov     r8b, r13b; SubAuthorityCount
0x18006d141  lea     rcx, [rbp+57h+Owner]; Sid
0x18006d145  call    cs:__imp_RtlInitializeSid
0x18006d14b  mov     ebx, eax
0x18006d14d  test    eax, eax
0x18006d14f  js      loc_18006D419
0x18006d155  xor     edx, edx; SubAuthority
0x18006d157  lea     rcx, [rbp+57h+Owner]; Sid
0x18006d15b  call    cs:__imp_RtlSubAuthoritySid
0x18006d161  mov     edx, esi; SubAuthority
0x18006d163  lea     rcx, [rbp+57h+Owner]; Sid
0x18006d167  mov     dword ptr [rax], 20h ; ' '
0x18006d16d  call    cs:__imp_RtlSubAuthoritySid
0x18006d173  lea     rcx, [rbp+57h+Owner]; Sid
0x18006d177  mov     dword ptr [rax], 220h
0x18006d17d  call    cs:__imp_RtlValidSid
0x18006d183  test    al, al
0x18006d185  jz      loc_18006D0F2
0x18006d18b  mov     rdi, r12
0x18006d18e  test    r14b, r14b
0x18006d191  jz      short loc_18006D1E1
0x18006d193  mov     r8b, r13b; SubAuthorityCount
0x18006d196  lea     rdx, [rbp+57h+var_90]; IdentifierAuthority
0x18006d19a  lea     rcx, [rbp+57h+var_60]; Sid
0x18006d19e  call    cs:__imp_RtlInitializeSid
0x18006d1a4  mov     ebx, eax
0x18006d1a6  test    eax, eax
0x18006d1a8  js      loc_18006D419
0x18006d1ae  xor     edx, edx; SubAuthority
0x18006d1b0  lea     rcx, [rbp+57h+var_60]; Sid
0x18006d1b4  call    cs:__imp_RtlSubAuthoritySid
0x18006d1ba  mov     edx, esi; SubAuthority
0x18006d1bc  lea     rcx, [rbp+57h+var_60]; Sid
0x18006d1c0  mov     [rax], r13d
0x18006d1c3  call    cs:__imp_RtlSubAuthoritySid
0x18006d1c9  lea     rcx, [rbp+57h+var_60]; Sid
0x18006d1cd  mov     [rax], esi
0x18006d1cf  call    cs:__imp_RtlValidSid
0x18006d1d5  test    al, al
0x18006d1d7  jz      loc_18006D0F2
0x18006d1dd  lea     rdi, [rbp+57h+var_60]
0x18006d1e1  lea     rcx, [rbp+57h+Sid]; Sid
0x18006d1e5  call    cs:__imp_RtlLengthSid
0x18006d1eb  lea     rcx, [rbp+57h+var_6C]; Sid
0x18006d1ef  mov     ebx, eax
0x18006d1f1  call    cs:__imp_RtlLengthSid
0x18006d1f7  lea     rcx, [rbp+57h+Owner]; Sid
0x18006d1fb  add     ebx, eax
0x18006d1fd  call    cs:__imp_RtlLengthSid
0x18006d203  add     ebx, 20h ; ' '
0x18006d206  add     ebx, eax
0x18006d208  test    r14b, r14b
0x18006d20b  jz      short loc_18006D21B
0x18006d20d  mov     rcx, rdi; Sid
0x18006d210  call    cs:__imp_RtlLengthSid
0x18006d216  add     ebx, 8
0x18006d219  add     ebx, eax
0x18006d21b  mov     rcx, gs:60h
0x18006d224  mov     edx, 8; Flags
0x18006d229  mov     r8d, ebx; Size
0x18006d22c  mov     rcx, [rcx+30h]; HeapHandle
0x18006d230  call    cs:__imp_RtlAllocateHeap
0x18006d236  mov     rsi, rax
0x18006d239  test    rax, rax
0x18006d23c  jnz     short loc_18006D248
0x18006d23e  mov     ebx, 0C0000017h
0x18006d243  jmp     loc_18006D419
0x18006d248  mov     r8d, r13d; AclRevision
0x18006d24b  mov     edx, ebx; AclSize
0x18006d24d  mov     rcx, rsi; Acl
0x18006d250  call    cs:__imp_RtlCreateAcl
0x18006d256  mov     ebx, eax
0x18006d258  test    eax, eax
0x18006d25a  js      loc_18006D401
0x18006d260  lea     rax, [rbp+57h+Sid]
0x18006d264  mov     r9d, 0F003Fh; AccessMask
0x18006d26a  mov     r8d, r13d; AceFlags
0x18006d26d  mov     [rsp+100h+pSid], rax; pSid
0x18006d272  mov     edx, r13d; dwAceRevision
0x18006d275  mov     rcx, rsi; pAcl
0x18006d278  call    cs:__imp_RtlAddAccessAllowedAceEx
0x18006d27e  mov     ebx, eax
0x18006d280  test    eax, eax
0x18006d282  js      loc_18006D401
0x18006d288  lea     rax, [rbp+57h+var_6C]
0x18006d28c  mov     r9d, 20019h; AccessMask
0x18006d292  mov     r8d, r13d; AceFlags
0x18006d295  mov     [rsp+100h+pSid], rax; pSid
0x18006d29a  mov     edx, r13d; dwAceRevision
0x18006d29d  mov     rcx, rsi; pAcl
0x18006d2a0  call    cs:__imp_RtlAddAccessAllowedAceEx
0x18006d2a6  mov     ebx, eax
0x18006d2a8  test    eax, eax
0x18006d2aa  js      loc_18006D401
0x18006d2b0  lea     rax, [rbp+57h+Owner]
0x18006d2b4  mov     r9d, 0F003Fh; AccessMask
0x18006d2ba  mov     r8d, r13d; AceFlags
0x18006d2bd  mov     [rsp+100h+pSid], rax; pSid
0x18006d2c2  mov     edx, r13d; dwAceRevision
0x18006d2c5  mov     rcx, rsi; pAcl
0x18006d2c8  call    cs:__imp_RtlAddAccessAllowedAceEx
0x18006d2ce  mov     ebx, eax
0x18006d2d0  test    eax, eax
0x18006d2d2  js      loc_18006D401
0x18006d2d8  test    r14b, r14b
0x18006d2db  jz      short loc_18006D301
0x18006d2dd  mov     r9d, 20019h; AccessMask
0x18006d2e3  mov     [rsp+100h+pSid], rdi; pSid
0x18006d2e8  mov     r8d, r13d; AceFlags
0x18006d2eb  mov     edx, r13d; dwAceRevision
0x18006d2ee  mov     rcx, rsi; pAcl
0x18006d2f1  call    cs:__imp_RtlAddAccessAllowedAceEx
0x18006d2f7  mov     ebx, eax
0x18006d2f9  test    eax, eax
0x18006d2fb  js      loc_18006D401
0x18006d301  mov     edx, 1; Revision
0x18006d306  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x18006d30a  call    cs:__imp_RtlCreateSecurityDescriptor
0x18006d310  mov     ebx, eax
0x18006d312  test    eax, eax
0x18006d314  js      loc_18006D401
0x18006d31a  xor     r9d, r9d; DaclDefaulted
0x18006d31d  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x18006d321  mov     r8, rsi; Dacl
0x18006d324  mov     dl, 1; DaclPresent
0x18006d326  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x18006d32c  mov     ebx, eax
0x18006d32e  test    eax, eax
0x18006d330  js      loc_18006D401
0x18006d336  mov     r8b, 1; OwnerDefaulted
0x18006d339  lea     rdx, [rbp+57h+Owner]; Owner
0x18006d33d  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x18006d341  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x18006d347  mov     ebx, eax
0x18006d349  test    eax, eax
0x18006d34b  js      loc_18006D401
0x18006d351  mov     r8b, 1; GroupDefaulted
0x18006d354  lea     rdx, [rbp+57h+Owner]; Group
0x18006d358  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x18006d35c  call    cs:__imp_RtlSetGroupSecurityDescriptor
0x18006d362  mov     ebx, eax
0x18006d364  test    eax, eax
0x18006d366  js      loc_18006D401
0x18006d36c  mov     eax, 1500h
0x18006d371  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x18006d375  or      word ptr [rbp+57h+SecurityDescriptor+2], ax
0x18006d379  call    cs:__imp_RtlValidSecurityDescriptor
0x18006d37f  test    al, al
0x18006d381  jnz     short loc_18006D38A
0x18006d383  mov     ebx, 0C00000E5h
0x18006d388  jmp     short loc_18006D401
0x18006d38a  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x18006d38e  call    cs:__imp_RtlLengthSecurityDescriptor
0x18006d394  mov     [rbp+57h+BufferLength], eax
0x18006d397  cmp     eax, 28h ; '('
0x18006d39a  jnb     short loc_18006D3A3
0x18006d39c  mov     ebx, 0C000003Eh
0x18006d3a1  jmp     short loc_18006D401
0x18006d3a3  mov     rcx, gs:60h
0x18006d3ac  mov     edx, 8; Flags
0x18006d3b1  mov     r8d, eax; Size
0x18006d3b4  mov     rcx, [rcx+30h]; HeapHandle
0x18006d3b8  call    cs:__imp_RtlAllocateHeap
0x18006d3be  mov     rdi, rax
0x18006d3c1  test    rax, rax
0x18006d3c4  jnz     short loc_18006D3CD
0x18006d3c6  mov     ebx, 0C0000017h
0x18006d3cb  jmp     short loc_18006D401
0x18006d3cd  lea     r8, [rbp+57h+BufferLength]; BufferLength
0x18006d3d1  mov     rdx, rdi; SelfRelativeSecurityDescriptor
0x18006d3d4  lea     rcx, [rbp+57h+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x18006d3d8  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x18006d3de  mov     ebx, eax
0x18006d3e0  test    eax, eax
0x18006d3e2  js      short loc_18006D3E9
0x18006d3e4  mov     [r15], rdi
0x18006d3e7  jmp     short loc_18006D401
0x18006d3e9  mov     rcx, gs:60h
0x18006d3f2  mov     r8, rdi; P
0x18006d3f5  xor     edx, edx; Flags
0x18006d3f7  mov     rcx, [rcx+30h]; HeapHandle
0x18006d3fb  call    cs:__imp_RtlFreeHeap
0x18006d401  mov     rcx, gs:60h
0x18006d40a  mov     r8, rsi; P
0x18006d40d  xor     edx, edx; Flags
0x18006d40f  mov     rcx, [rcx+30h]; HeapHandle
0x18006d413  call    cs:__imp_RtlFreeHeap
0x18006d419  mov     eax, ebx
0x18006d41b  mov     rcx, [rbp+57h+var_50]
0x18006d41f  xor     rcx, rsp; StackCookie
0x18006d422  call    __security_check_cookie
0x18006d427  add     rsp, 0C8h
0x18006d42e  pop     r15
0x18006d430  pop     r14
0x18006d432  pop     r13
0x18006d434  pop     r12
0x18006d436  pop     rdi
0x18006d437  pop     rsi
0x18006d438  pop     rbx
0x18006d439  pop     rbp
0x18006d43a  retn
```
