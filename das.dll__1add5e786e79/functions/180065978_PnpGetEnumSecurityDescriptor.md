# _PnpGetEnumSecurityDescriptor

- ea: `0x180065978`
- end: `0x180065cc4`
- name: `_PnpGetEnumSecurityDescriptor`
- size: `844`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180038b5c`

## callees

- `0x18003bc80`
- `0x180065978`

## import_xrefs

- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x180065c66`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x180065c66`
- `ntdll!RtlValidSecurityDescriptor` at `0x180065c1d`
- `ntdll!RtlValidSecurityDescriptor` at `0x180065c1d`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x180065c06`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x180065c06`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x180065bed`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x180065bed`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180065bd4`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180065bd4`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180065bba`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180065bba`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x180065b58`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x180065b7e`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x180065ba4`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x180065b58`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x180065b7e`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x180065ba4`
- `ntdll!RtlLengthSid` at `0x180065ae1`
- `ntdll!RtlLengthSid` at `0x180065aed`
- `ntdll!RtlLengthSid` at `0x180065af9`
- `ntdll!RtlLengthSid` at `0x180065ae1`
- `ntdll!RtlLengthSid` at `0x180065aed`
- `ntdll!RtlLengthSid` at `0x180065af9`
- `ntdll!RtlValidSid` at `0x180065a03`
- `ntdll!RtlValidSid` at `0x180065a40`
- `ntdll!RtlValidSid` at `0x180065a7a`
- `ntdll!RtlValidSid` at `0x180065acf`
- `ntdll!RtlValidSid` at `0x180065a03`
- `ntdll!RtlValidSid` at `0x180065a40`
- `ntdll!RtlValidSid` at `0x180065a7a`
- `ntdll!RtlValidSid` at `0x180065acf`
- `ntdll!RtlSubAuthoritySid` at `0x1800659f3`
- `ntdll!RtlSubAuthoritySid` at `0x180065a30`
- `ntdll!RtlSubAuthoritySid` at `0x180065a6d`
- `ntdll!RtlSubAuthoritySid` at `0x180065aab`
- `ntdll!RtlSubAuthoritySid` at `0x180065abf`
- `ntdll!RtlSubAuthoritySid` at `0x1800659f3`
- `ntdll!RtlSubAuthoritySid` at `0x180065a30`
- `ntdll!RtlSubAuthoritySid` at `0x180065a6d`
- `ntdll!RtlSubAuthoritySid` at `0x180065aab`
- `ntdll!RtlSubAuthoritySid` at `0x180065abf`
- `ntdll!RtlCreateAcl` at `0x180065b32`
- `ntdll!RtlCreateAcl` at `0x180065b32`
- `ntdll!RtlInitializeSid` at `0x1800659df`
- `ntdll!RtlInitializeSid` at `0x180065a1c`
- `ntdll!RtlInitializeSid` at `0x180065a59`
- `ntdll!RtlInitializeSid` at `0x180065a97`
- `ntdll!RtlInitializeSid` at `0x1800659df`
- `ntdll!RtlInitializeSid` at `0x180065a1c`
- `ntdll!RtlInitializeSid` at `0x180065a59`
- `ntdll!RtlInitializeSid` at `0x180065a97`
- `ntdll!RtlFreeHeap` at `0x180065c87`
- `ntdll!RtlFreeHeap` at `0x180065c9f`
- `ntdll!RtlFreeHeap` at `0x180065c87`
- `ntdll!RtlFreeHeap` at `0x180065c9f`
- `ntdll!RtlAllocateHeap` at `0x180065b18`
- `ntdll!RtlAllocateHeap` at `0x180065c4d`
- `ntdll!RtlAllocateHeap` at `0x180065b18`
- `ntdll!RtlAllocateHeap` at `0x180065c4d`
- `ntdll!RtlLengthSecurityDescriptor` at `0x180065c2b`
- `ntdll!RtlLengthSecurityDescriptor` at `0x180065c2b`

## pseudocode

```c
void *PnpGetEnumSecurityDescriptor()
{
  void *v0; // rsi
  ULONG v1; // ebx
  ULONG v2; // ebx
  ULONG v3; // ebx
  struct _ACL *Heap; // rax
  struct _ACL *v5; // rdi
  ULONG v6; // eax
  PVOID v7; // rax
  void *v8; // rbx
  ULONG BufferLength; // [rsp+30h] [rbp-69h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+38h] [rbp-61h] BYREF
  __int64 v12; // [rsp+58h] [rbp-41h]
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+60h] [rbp-39h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v14; // [rsp+68h] [rbp-31h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v15; // [rsp+70h] [rbp-29h] BYREF
  _BYTE Sid[12]; // [rsp+78h] [rbp-21h] BYREF
  _BYTE pSid[12]; // [rsp+84h] [rbp-15h] BYREF
  _BYTE v18[12]; // [rsp+90h] [rbp-9h] BYREF
  _BYTE Owner[20]; // [rsp+9Ch] [rbp+3h] BYREF

  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_DWORD *)v14.Value = 0;
  *(_DWORD *)v15.Value = 0;
  v12 = 0;
  BufferLength = 0;
  v0 = 0;
  *(_WORD *)&v14.Value[4] = 768;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  *(_WORD *)&v15.Value[4] = 256;
  if ( RtlInitializeSid(Sid, &IdentifierAuthority, 1u) >= 0 )
  {
    *RtlSubAuthoritySid(Sid, 0) = 18;
    if ( RtlValidSid(Sid) )
    {
      if ( RtlInitializeSid(pSid, &v14, 1u) >= 0 )
      {
        *RtlSubAuthoritySid(pSid, 0) = 4;
        if ( RtlValidSid(pSid) )
        {
          if ( RtlInitializeSid(v18, &v15, 1u) >= 0 )
          {
            *RtlSubAuthoritySid(v18, 0) = 0;
            if ( RtlValidSid(v18) )
            {
              if ( RtlInitializeSid(Owner, &IdentifierAuthority, 2u) >= 0 )
              {
                *RtlSubAuthoritySid(Owner, 0) = 32;
                *RtlSubAuthoritySid(Owner, 1u) = 544;
                if ( RtlValidSid(Owner) )
                {
                  v1 = RtlLengthSid(Sid);
                  v2 = RtlLengthSid(pSid) + v1;
                  v3 = RtlLengthSid(v18) + 32 + v2;
                  Heap = (struct _ACL *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v3);
                  v5 = Heap;
                  if ( Heap )
                  {
                    if ( RtlCreateAcl(Heap, v3, 2u) >= 0
                      && RtlAddAccessAllowedAceEx(v5, 2u, 2u, 0xF003Fu, Sid) >= 0
                      && RtlAddAccessAllowedAceEx(v5, 2u, 2u, 0x20000u, pSid) >= 0
                      && RtlAddAccessAllowedAceEx(v5, 2u, 2u, 0x20019u, v18) >= 0
                      && RtlCreateSecurityDescriptor(SecurityDescriptor, 1u) >= 0
                      && RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v5, 0) >= 0
                      && RtlSetOwnerSecurityDescriptor(SecurityDescriptor, Owner, 1u) >= 0
                      && RtlSetGroupSecurityDescriptor(SecurityDescriptor, Owner, 1u) >= 0 )
                    {
                      WORD1(SecurityDescriptor[0]) |= 0x1400u;
                      if ( RtlValidSecurityDescriptor(SecurityDescriptor) )
                      {
                        v6 = RtlLengthSecurityDescriptor(SecurityDescriptor);
                        BufferLength = v6;
                        if ( v6 >= 0x28 )
                        {
                          v7 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v6);
                          v8 = v7;
                          if ( v7 )
                          {
                            if ( RtlAbsoluteToSelfRelativeSD(SecurityDescriptor, v7, &BufferLength) < 0 )
                              RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
                            else
                              v0 = v8;
                          }
                        }
                      }
                    }
                    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  return v0;
}

```

## disassembly

```asm
0x180065978  push    rbp
0x18006597a  push    rbx
0x18006597b  push    rsi
0x18006597c  push    rdi
0x18006597d  push    r12
0x18006597f  push    r14
0x180065981  lea     rbp, [rsp-2Fh]
0x180065986  sub     rsp, 0C8h
0x18006598d  mov     rax, cs:__security_cookie
0x180065994  xor     rax, rsp
0x180065997  mov     [rbp+57h+var_40], rax
0x18006599b  xor     r14d, r14d
0x18006599e  mov     word ptr [rbp+57h+IdentifierAuthority.Value+4], 500h
0x1800659a4  xorps   xmm0, xmm0
0x1800659a7  mov     dword ptr [rbp+57h+IdentifierAuthority.Value], r14d
0x1800659ab  xor     eax, eax
0x1800659ad  mov     dword ptr [rbp+57h+var_88.Value], r14d
0x1800659b1  mov     r8b, 1; SubAuthorityCount
0x1800659b4  mov     dword ptr [rbp+57h+var_80.Value], r14d
0x1800659b8  lea     rdx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x1800659bc  mov     [rbp+57h+var_98], rax
0x1800659c0  lea     rcx, [rbp+57h+Sid]; Sid
0x1800659c4  mov     [rbp+57h+BufferLength], r14d
0x1800659c8  mov     esi, r14d
0x1800659cb  mov     word ptr [rbp+57h+var_88.Value+4], 300h
0x1800659d1  movups  [rbp+57h+SecurityDescriptor], xmm0
0x1800659d5  mov     word ptr [rbp+57h+var_80.Value+4], 100h
0x1800659db  movups  [rbp+57h+var_A8], xmm0
0x1800659df  call    cs:__imp_RtlInitializeSid
0x1800659e5  test    eax, eax
0x1800659e7  js      loc_180065CA5
0x1800659ed  xor     edx, edx; SubAuthority
0x1800659ef  lea     rcx, [rbp+57h+Sid]; Sid
0x1800659f3  call    cs:__imp_RtlSubAuthoritySid
0x1800659f9  lea     rcx, [rbp+57h+Sid]; Sid
0x1800659fd  mov     dword ptr [rax], 12h
0x180065a03  call    cs:__imp_RtlValidSid
0x180065a09  test    al, al
0x180065a0b  jz      loc_180065CA5
0x180065a11  mov     r8b, 1; SubAuthorityCount
0x180065a14  lea     rdx, [rbp+57h+var_88]; IdentifierAuthority
0x180065a18  lea     rcx, [rbp+57h+var_6C]; Sid
0x180065a1c  call    cs:__imp_RtlInitializeSid
0x180065a22  test    eax, eax
0x180065a24  js      loc_180065CA5
0x180065a2a  xor     edx, edx; SubAuthority
0x180065a2c  lea     rcx, [rbp+57h+var_6C]; Sid
0x180065a30  call    cs:__imp_RtlSubAuthoritySid
0x180065a36  lea     rcx, [rbp+57h+var_6C]; Sid
0x180065a3a  mov     dword ptr [rax], 4
0x180065a40  call    cs:__imp_RtlValidSid
0x180065a46  test    al, al
0x180065a48  jz      loc_180065CA5
0x180065a4e  mov     r8b, 1; SubAuthorityCount
0x180065a51  lea     rdx, [rbp+57h+var_80]; IdentifierAuthority
0x180065a55  lea     rcx, [rbp+57h+var_60]; Sid
0x180065a59  call    cs:__imp_RtlInitializeSid
0x180065a5f  test    eax, eax
0x180065a61  js      loc_180065CA5
0x180065a67  xor     edx, edx; SubAuthority
0x180065a69  lea     rcx, [rbp+57h+var_60]; Sid
0x180065a6d  call    cs:__imp_RtlSubAuthoritySid
0x180065a73  lea     rcx, [rbp+57h+var_60]; Sid
0x180065a77  mov     [rax], r14d
0x180065a7a  call    cs:__imp_RtlValidSid
0x180065a80  test    al, al
0x180065a82  jz      loc_180065CA5
0x180065a88  lea     r12d, [r14+2]
0x180065a8c  mov     r8b, r12b; SubAuthorityCount
0x180065a8f  lea     rdx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x180065a93  lea     rcx, [rbp+57h+Owner]; Sid
0x180065a97  call    cs:__imp_RtlInitializeSid
0x180065a9d  test    eax, eax
0x180065a9f  js      loc_180065CA5
0x180065aa5  xor     edx, edx; SubAuthority
0x180065aa7  lea     rcx, [rbp+57h+Owner]; Sid
0x180065aab  call    cs:__imp_RtlSubAuthoritySid
0x180065ab1  lea     edx, [r14+1]; SubAuthority
0x180065ab5  lea     rcx, [rbp+57h+Owner]; Sid
0x180065ab9  mov     dword ptr [rax], 20h ; ' '
0x180065abf  call    cs:__imp_RtlSubAuthoritySid
0x180065ac5  lea     rcx, [rbp+57h+Owner]; Sid
0x180065ac9  mov     dword ptr [rax], 220h
0x180065acf  call    cs:__imp_RtlValidSid
0x180065ad5  test    al, al
0x180065ad7  jz      loc_180065CA5
0x180065add  lea     rcx, [rbp+57h+Sid]; Sid
0x180065ae1  call    cs:__imp_RtlLengthSid
0x180065ae7  lea     rcx, [rbp+57h+var_6C]; Sid
0x180065aeb  mov     ebx, eax
0x180065aed  call    cs:__imp_RtlLengthSid
0x180065af3  lea     rcx, [rbp+57h+var_60]; Sid
0x180065af7  add     ebx, eax
0x180065af9  call    cs:__imp_RtlLengthSid
0x180065aff  mov     rcx, gs:60h
0x180065b08  lea     edx, [r14+8]; Flags
0x180065b0c  add     eax, 20h ; ' '
0x180065b0f  add     ebx, eax
0x180065b11  mov     r8d, ebx; Size
0x180065b14  mov     rcx, [rcx+30h]; HeapHandle
0x180065b18  call    cs:__imp_RtlAllocateHeap
0x180065b1e  mov     rdi, rax
0x180065b21  test    rax, rax
0x180065b24  jz      loc_180065CA5
0x180065b2a  mov     r8d, r12d; AclRevision
0x180065b2d  mov     edx, ebx; AclSize
0x180065b2f  mov     rcx, rax; Acl
0x180065b32  call    cs:__imp_RtlCreateAcl
0x180065b38  test    eax, eax
0x180065b3a  js      loc_180065C8D
0x180065b40  lea     rax, [rbp+57h+Sid]
0x180065b44  mov     r9d, 0F003Fh; AccessMask
0x180065b4a  mov     r8d, r12d; AceFlags
0x180065b4d  mov     [rsp+0F0h+pSid], rax; pSid
0x180065b52  mov     edx, r12d; dwAceRevision
0x180065b55  mov     rcx, rdi; pAcl
0x180065b58  call    cs:__imp_RtlAddAccessAllowedAceEx
0x180065b5e  test    eax, eax
0x180065b60  js      loc_180065C8D
0x180065b66  lea     rax, [rbp+57h+var_6C]
0x180065b6a  mov     r9d, 20000h; AccessMask
0x180065b70  mov     r8d, r12d; AceFlags
0x180065b73  mov     [rsp+0F0h+pSid], rax; pSid
0x180065b78  mov     edx, r12d; dwAceRevision
0x180065b7b  mov     rcx, rdi; pAcl
0x180065b7e  call    cs:__imp_RtlAddAccessAllowedAceEx
0x180065b84  test    eax, eax
0x180065b86  js      loc_180065C8D
0x180065b8c  lea     rax, [rbp+57h+var_60]
0x180065b90  mov     r9d, 20019h; AccessMask
0x180065b96  mov     r8d, r12d; AceFlags
0x180065b99  mov     [rsp+0F0h+pSid], rax; pSid
0x180065b9e  mov     edx, r12d; dwAceRevision
0x180065ba1  mov     rcx, rdi; pAcl
0x180065ba4  call    cs:__imp_RtlAddAccessAllowedAceEx
0x180065baa  test    eax, eax
0x180065bac  js      loc_180065C8D
0x180065bb2  lea     edx, [r14+1]; Revision
0x180065bb6  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x180065bba  call    cs:__imp_RtlCreateSecurityDescriptor
0x180065bc0  test    eax, eax
0x180065bc2  js      loc_180065C8D
0x180065bc8  xor     r9d, r9d; DaclDefaulted
0x180065bcb  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x180065bcf  mov     r8, rdi; Dacl
0x180065bd2  mov     dl, 1; DaclPresent
0x180065bd4  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x180065bda  test    eax, eax
0x180065bdc  js      loc_180065C8D
0x180065be2  mov     r8b, 1; OwnerDefaulted
0x180065be5  lea     rdx, [rbp+57h+Owner]; Owner
0x180065be9  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x180065bed  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x180065bf3  test    eax, eax
0x180065bf5  js      loc_180065C8D
0x180065bfb  mov     r8b, 1; GroupDefaulted
0x180065bfe  lea     rdx, [rbp+57h+Owner]; Group
0x180065c02  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x180065c06  call    cs:__imp_RtlSetGroupSecurityDescriptor
0x180065c0c  test    eax, eax
0x180065c0e  js      short loc_180065C8D
0x180065c10  mov     eax, 1400h
0x180065c15  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x180065c19  or      word ptr [rbp+57h+SecurityDescriptor+2], ax
0x180065c1d  call    cs:__imp_RtlValidSecurityDescriptor
0x180065c23  test    al, al
0x180065c25  jz      short loc_180065C8D
0x180065c27  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x180065c2b  call    cs:__imp_RtlLengthSecurityDescriptor
0x180065c31  mov     [rbp+57h+BufferLength], eax
0x180065c34  cmp     eax, 28h ; '('
0x180065c37  jb      short loc_180065C8D
0x180065c39  mov     rcx, gs:60h
0x180065c42  lea     edx, [r14+8]; Flags
0x180065c46  mov     r8d, eax; Size
0x180065c49  mov     rcx, [rcx+30h]; HeapHandle
0x180065c4d  call    cs:__imp_RtlAllocateHeap
0x180065c53  mov     rbx, rax
0x180065c56  test    rax, rax
0x180065c59  jz      short loc_180065C8D
0x180065c5b  lea     r8, [rbp+57h+BufferLength]; BufferLength
0x180065c5f  mov     rdx, rax; SelfRelativeSecurityDescriptor
0x180065c62  lea     rcx, [rbp+57h+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x180065c66  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x180065c6c  test    eax, eax
0x180065c6e  js      short loc_180065C75
0x180065c70  mov     rsi, rbx
0x180065c73  jmp     short loc_180065C8D
0x180065c75  mov     rcx, gs:60h
0x180065c7e  mov     r8, rbx; P
0x180065c81  xor     edx, edx; Flags
0x180065c83  mov     rcx, [rcx+30h]; HeapHandle
0x180065c87  call    cs:__imp_RtlFreeHeap
0x180065c8d  mov     rcx, gs:60h
0x180065c96  mov     r8, rdi; P
0x180065c99  xor     edx, edx; Flags
0x180065c9b  mov     rcx, [rcx+30h]; HeapHandle
0x180065c9f  call    cs:__imp_RtlFreeHeap
0x180065ca5  mov     rax, rsi
0x180065ca8  mov     rcx, [rbp+57h+var_40]
0x180065cac  xor     rcx, rsp; StackCookie
0x180065caf  call    __security_check_cookie
0x180065cb4  add     rsp, 0C8h
0x180065cbb  pop     r14
0x180065cbd  pop     r12
0x180065cbf  pop     rdi
0x180065cc0  pop     rsi
0x180065cc1  pop     rbx
0x180065cc2  pop     rbp
0x180065cc3  retn
```
