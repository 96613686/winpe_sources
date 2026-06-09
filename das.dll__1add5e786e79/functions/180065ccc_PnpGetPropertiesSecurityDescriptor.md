# _PnpGetPropertiesSecurityDescriptor

- ea: `0x180065ccc`
- end: `0x180065ec2`
- name: `_PnpGetPropertiesSecurityDescriptor`
- size: `502`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800037f0`

## callees

- `0x18003bc80`
- `0x180065ccc`

## import_xrefs

- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x180065e68`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x180065e68`
- `ntdll!RtlValidSecurityDescriptor` at `0x180065e20`
- `ntdll!RtlValidSecurityDescriptor` at `0x180065e20`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x180065e09`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x180065e09`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x180065df0`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x180065df0`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180065dd7`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180065dd7`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180065dbd`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180065dbd`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x180065da8`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x180065da8`
- `ntdll!RtlLengthSid` at `0x180065d4b`
- `ntdll!RtlLengthSid` at `0x180065d4b`
- `ntdll!RtlValidSid` at `0x180065d39`
- `ntdll!RtlValidSid` at `0x180065d39`
- `ntdll!RtlSubAuthoritySid` at `0x180065d29`
- `ntdll!RtlSubAuthoritySid` at `0x180065d29`
- `ntdll!RtlCreateAcl` at `0x180065d82`
- `ntdll!RtlCreateAcl` at `0x180065d82`
- `ntdll!RtlInitializeSid` at `0x180065d15`
- `ntdll!RtlInitializeSid` at `0x180065d15`
- `ntdll!RtlFreeHeap` at `0x180065e89`
- `ntdll!RtlFreeHeap` at `0x180065ea1`
- `ntdll!RtlFreeHeap` at `0x180065e89`
- `ntdll!RtlFreeHeap` at `0x180065ea1`
- `ntdll!RtlAllocateHeap` at `0x180065d67`
- `ntdll!RtlAllocateHeap` at `0x180065e4f`
- `ntdll!RtlAllocateHeap` at `0x180065d67`
- `ntdll!RtlAllocateHeap` at `0x180065e4f`
- `ntdll!RtlLengthSecurityDescriptor` at `0x180065e2e`
- `ntdll!RtlLengthSecurityDescriptor` at `0x180065e2e`

## pseudocode

```c
void *PnpGetPropertiesSecurityDescriptor()
{
  void *v0; // rdi
  ULONG v1; // ebx
  struct _ACL *Heap; // rax
  struct _ACL *v3; // rsi
  ULONG v4; // eax
  PVOID v5; // rax
  void *v6; // rbx
  ULONG BufferLength; // [rsp+30h] [rbp-19h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+38h] [rbp-11h] BYREF
  __int64 v10; // [rsp+58h] [rbp+Fh]
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+60h] [rbp+17h] BYREF
  _BYTE Sid[16]; // [rsp+68h] [rbp+1Fh] BYREF

  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  v0 = 0;
  v10 = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  BufferLength = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  if ( RtlInitializeSid(Sid, &IdentifierAuthority, 1u) >= 0 )
  {
    *RtlSubAuthoritySid(Sid, 0) = 18;
    if ( RtlValidSid(Sid) )
    {
      v1 = RtlLengthSid(Sid) + 16;
      Heap = (struct _ACL *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v1);
      v3 = Heap;
      if ( Heap )
      {
        if ( RtlCreateAcl(Heap, v1, 2u) >= 0
          && RtlAddAccessAllowedAceEx(v3, 2u, 2u, 0xF003Fu, Sid) >= 0
          && RtlCreateSecurityDescriptor(SecurityDescriptor, 1u) >= 0
          && RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v3, 0) >= 0
          && RtlSetOwnerSecurityDescriptor(SecurityDescriptor, Sid, 1u) >= 0
          && RtlSetGroupSecurityDescriptor(SecurityDescriptor, Sid, 1u) >= 0 )
        {
          WORD1(SecurityDescriptor[0]) |= 0x1400u;
          if ( RtlValidSecurityDescriptor(SecurityDescriptor) )
          {
            v4 = RtlLengthSecurityDescriptor(SecurityDescriptor);
            BufferLength = v4;
            if ( v4 >= 0x28 )
            {
              v5 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v4);
              v6 = v5;
              if ( v5 )
              {
                if ( RtlAbsoluteToSelfRelativeSD(SecurityDescriptor, v5, &BufferLength) < 0 )
                  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
                else
                  v0 = v6;
              }
            }
          }
        }
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v3);
      }
    }
  }
  return v0;
}

```

## disassembly

```asm
0x180065ccc  push    rbp
0x180065cce  push    rbx
0x180065ccf  push    rsi
0x180065cd0  push    rdi
0x180065cd1  lea     rbp, [rsp-3Fh]
0x180065cd6  sub     rsp, 88h
0x180065cdd  mov     rax, cs:__security_cookie
0x180065ce4  xor     rax, rsp
0x180065ce7  mov     [rbp+57h+var_28], rax
0x180065ceb  xorps   xmm0, xmm0
0x180065cee  mov     word ptr [rbp+57h+IdentifierAuthority.Value+4], 500h
0x180065cf4  xor     eax, eax
0x180065cf6  lea     rdx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x180065cfa  xor     edi, edi
0x180065cfc  mov     [rbp+57h+var_48], rax
0x180065d00  mov     r8b, 1; SubAuthorityCount
0x180065d03  mov     dword ptr [rbp+57h+IdentifierAuthority.Value], edi
0x180065d06  lea     rcx, [rbp+57h+Sid]; Sid
0x180065d0a  mov     [rbp+57h+BufferLength], eax
0x180065d0d  movups  [rbp+57h+SecurityDescriptor], xmm0
0x180065d11  movups  [rbp+57h+var_58], xmm0
0x180065d15  call    cs:__imp_RtlInitializeSid
0x180065d1b  test    eax, eax
0x180065d1d  js      loc_180065EA7
0x180065d23  xor     edx, edx; SubAuthority
0x180065d25  lea     rcx, [rbp+57h+Sid]; Sid
0x180065d29  call    cs:__imp_RtlSubAuthoritySid
0x180065d2f  lea     rcx, [rbp+57h+Sid]; Sid
0x180065d33  mov     dword ptr [rax], 12h
0x180065d39  call    cs:__imp_RtlValidSid
0x180065d3f  test    al, al
0x180065d41  jz      loc_180065EA7
0x180065d47  lea     rcx, [rbp+57h+Sid]; Sid
0x180065d4b  call    cs:__imp_RtlLengthSid
0x180065d51  mov     rcx, gs:60h
0x180065d5a  lea     edx, [rdi+8]; Flags
0x180065d5d  lea     ebx, [rax+10h]
0x180065d60  mov     rcx, [rcx+30h]; HeapHandle
0x180065d64  mov     r8d, ebx; Size
0x180065d67  call    cs:__imp_RtlAllocateHeap
0x180065d6d  mov     rsi, rax
0x180065d70  test    rax, rax
0x180065d73  jz      loc_180065EA7
0x180065d79  lea     r8d, [rdi+2]; AclRevision
0x180065d7d  mov     edx, ebx; AclSize
0x180065d7f  mov     rcx, rax; Acl
0x180065d82  call    cs:__imp_RtlCreateAcl
0x180065d88  test    eax, eax
0x180065d8a  js      loc_180065E8F
0x180065d90  lea     edx, [rdi+2]; dwAceRevision
0x180065d93  mov     r9d, 0F003Fh; AccessMask
0x180065d99  lea     rax, [rbp+57h+Sid]
0x180065d9d  mov     r8d, edx; AceFlags
0x180065da0  mov     rcx, rsi; pAcl
0x180065da3  mov     [rsp+0A0h+pSid], rax; pSid
0x180065da8  call    cs:__imp_RtlAddAccessAllowedAceEx
0x180065dae  test    eax, eax
0x180065db0  js      loc_180065E8F
0x180065db6  lea     edx, [rdi+1]; Revision
0x180065db9  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x180065dbd  call    cs:__imp_RtlCreateSecurityDescriptor
0x180065dc3  test    eax, eax
0x180065dc5  js      loc_180065E8F
0x180065dcb  xor     r9d, r9d; DaclDefaulted
0x180065dce  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x180065dd2  mov     r8, rsi; Dacl
0x180065dd5  mov     dl, 1; DaclPresent
0x180065dd7  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x180065ddd  test    eax, eax
0x180065ddf  js      loc_180065E8F
0x180065de5  mov     r8b, 1; OwnerDefaulted
0x180065de8  lea     rdx, [rbp+57h+Sid]; Owner
0x180065dec  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x180065df0  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x180065df6  test    eax, eax
0x180065df8  js      loc_180065E8F
0x180065dfe  mov     r8b, 1; GroupDefaulted
0x180065e01  lea     rdx, [rbp+57h+Sid]; Group
0x180065e05  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x180065e09  call    cs:__imp_RtlSetGroupSecurityDescriptor
0x180065e0f  test    eax, eax
0x180065e11  js      short loc_180065E8F
0x180065e13  mov     eax, 1400h
0x180065e18  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x180065e1c  or      word ptr [rbp+57h+SecurityDescriptor+2], ax
0x180065e20  call    cs:__imp_RtlValidSecurityDescriptor
0x180065e26  test    al, al
0x180065e28  jz      short loc_180065E8F
0x180065e2a  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x180065e2e  call    cs:__imp_RtlLengthSecurityDescriptor
0x180065e34  mov     [rbp+57h+BufferLength], eax
0x180065e37  cmp     eax, 28h ; '('
0x180065e3a  jb      short loc_180065E8F
0x180065e3c  mov     rcx, gs:60h
0x180065e45  lea     edx, [rdi+8]; Flags
0x180065e48  mov     r8d, eax; Size
0x180065e4b  mov     rcx, [rcx+30h]; HeapHandle
0x180065e4f  call    cs:__imp_RtlAllocateHeap
0x180065e55  mov     rbx, rax
0x180065e58  test    rax, rax
0x180065e5b  jz      short loc_180065E8F
0x180065e5d  lea     r8, [rbp+57h+BufferLength]; BufferLength
0x180065e61  mov     rdx, rax; SelfRelativeSecurityDescriptor
0x180065e64  lea     rcx, [rbp+57h+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x180065e68  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x180065e6e  test    eax, eax
0x180065e70  js      short loc_180065E77
0x180065e72  mov     rdi, rbx
0x180065e75  jmp     short loc_180065E8F
0x180065e77  mov     rcx, gs:60h
0x180065e80  mov     r8, rbx; P
0x180065e83  xor     edx, edx; Flags
0x180065e85  mov     rcx, [rcx+30h]; HeapHandle
0x180065e89  call    cs:__imp_RtlFreeHeap
0x180065e8f  mov     rcx, gs:60h
0x180065e98  mov     r8, rsi; P
0x180065e9b  xor     edx, edx; Flags
0x180065e9d  mov     rcx, [rcx+30h]; HeapHandle
0x180065ea1  call    cs:__imp_RtlFreeHeap
0x180065ea7  mov     rax, rdi
0x180065eaa  mov     rcx, [rbp+57h+var_28]
0x180065eae  xor     rcx, rsp; StackCookie
0x180065eb1  call    __security_check_cookie
0x180065eb6  add     rsp, 88h
0x180065ebd  pop     rdi
0x180065ebe  pop     rsi
0x180065ebf  pop     rbx
0x180065ec0  pop     rbp
0x180065ec1  retn
```
