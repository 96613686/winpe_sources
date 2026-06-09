# BasepIsServiceSidBlocked

- ea: `0x180033c24`
- end: `0x180033ec1`
- name: `BasepIsServiceSidBlocked`
- size: `669`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180033ac0`

## callees

- `0x180033c24`
- `0x18007a840`

## import_xrefs

- `ntdll!RtlCreateSecurityDescriptor` at `0x180033deb`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180033deb`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x180033e0f`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x180033e0f`
- `ntdll!RtlCreateAcl` at `0x180033d27`
- `ntdll!RtlCreateAcl` at `0x180033d27`
- `ntdll!RtlFreeHeap` at `0x180033eaa`
- `ntdll!RtlFreeHeap` at `0x180033eaa`
- `ntdll!RtlAddAccessAllowedAce` at `0x180033dd6`
- `ntdll!RtlAddAccessAllowedAce` at `0x180033dd6`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180033e22`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180033e22`
- `ntdll!RtlAllocateHeap` at `0x180033cc1`
- `ntdll!RtlAllocateHeap` at `0x180033cc1`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x180033dfd`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x180033dfd`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180033c8a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180033c8a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033ce9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033cf8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033ce9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033cf8`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180033ca0`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180033ca0`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180033cd9`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180033d4d`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180033cd9`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180033d4d`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180033db8`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180033db8`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180033e80`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180033e80`

## pseudocode

```c
__int64 __fastcall BasepIsServiceSidBlocked(BOOL *a1)
{
  unsigned int v2; // esi
  struct _ACL *Heap; // rax
  struct _ACL *v4; // rbx
  __int64 i; // rdi
  BOOL v7; // eax
  PSID pSid; // [rsp+60h] [rbp-A0h] BYREF
  DWORD PrivilegeSetLength; // [rsp+68h] [rbp-98h] BYREF
  BOOL AccessStatus; // [rsp+6Ch] [rbp-94h] BYREF
  DWORD GrantedAccess; // [rsp+70h] [rbp-90h] BYREF
  void *DuplicateTokenHandle; // [rsp+78h] [rbp-88h] BYREF
  void *TokenHandle; // [rsp+80h] [rbp-80h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v15; // [rsp+A8h] [rbp-58h]
  _GENERIC_MAPPING GenericMapping; // [rsp+B0h] [rbp-50h] BYREF
  _PRIVILEGE_SET PrivilegeSet; // [rsp+C0h] [rbp-40h] BYREF

  PrivilegeSetLength = 0;
  v15 = 0;
  GrantedAccess = 0;
  AccessStatus = 0;
  DuplicateTokenHandle = 0;
  TokenHandle = 0;
  GenericMapping = 0;
  v2 = 0;
  pSid = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  if ( OpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0xAu, &TokenHandle) )
  {
    if ( DuplicateToken(TokenHandle, SecurityImpersonation, &DuplicateTokenHandle) )
    {
      Heap = (struct _ACL *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x198u);
      v4 = Heap;
      if ( Heap )
      {
        RtlCreateAcl(Heap, 0x198u, 2u);
        for ( i = 0; (unsigned int)i < 5; i = (unsigned int)(i + 1) )
        {
          if ( pSid )
          {
            FreeSid(pSid);
            pSid = 0;
          }
          if ( !AllocateAndInitializeSid(
                  &BasepNtIdentifierAuthority,
                  *((_BYTE *)BasepBlockedServiceSids + 36 * i),
                  *((_DWORD *)BasepBlockedServiceSids + 9 * i + 1),
                  *((_DWORD *)&BasepBlockedServiceSids[1] + 9 * i),
                  *((_DWORD *)&BasepBlockedServiceSids[1] + 9 * i + 1),
                  *((_DWORD *)&BasepBlockedServiceSids[2] + 9 * i),
                  *((_DWORD *)&BasepBlockedServiceSids[2] + 9 * i + 1),
                  *((_DWORD *)&BasepBlockedServiceSids[3] + 9 * i),
                  *((_DWORD *)&BasepBlockedServiceSids[3] + 9 * i + 1),
                  *((_DWORD *)&BasepBlockedServiceSids[4] + 9 * i),
                  &pSid) )
            goto LABEL_21;
          RtlAddAccessAllowedAce(v4, 2u, 1u, pSid);
        }
        RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
        RtlSetOwnerSecurityDescriptor(SecurityDescriptor, pSid, 0);
        RtlSetGroupSecurityDescriptor(SecurityDescriptor, pSid, 0);
        RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v4, 0);
        GenericMapping.GenericRead = 131073;
        GenericMapping.GenericWrite = 0x20000;
        GenericMapping.GenericExecute = 0x20000;
        GenericMapping.GenericAll = 2031617;
        PrivilegeSetLength = 56;
        if ( AccessCheck(
               SecurityDescriptor,
               DuplicateTokenHandle,
               1u,
               &GenericMapping,
               &PrivilegeSet,
               &PrivilegeSetLength,
               &GrantedAccess,
               &AccessStatus) )
        {
          v7 = AccessStatus && GrantedAccess == 1;
          *a1 = v7;
          v2 = 1;
        }
LABEL_21:
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
      }
    }
  }
  if ( pSid )
    FreeSid(pSid);
  if ( DuplicateTokenHandle )
    CloseHandle(DuplicateTokenHandle);
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v2;
}

```

## disassembly

```asm
0x180033c24  push    rbp
0x180033c26  push    rbx
0x180033c27  push    rsi
0x180033c28  push    rdi
0x180033c29  push    r12
0x180033c2b  push    r14
0x180033c2d  lea     rbp, [rsp-8]
0x180033c32  sub     rsp, 108h
0x180033c39  mov     rax, cs:__security_cookie
0x180033c40  xor     rax, rsp
0x180033c43  mov     [rbp+30h+var_38], rax
0x180033c47  xor     eax, eax
0x180033c49  mov     [rsp+130h+PrivilegeSetLength], 0
0x180033c51  xorps   xmm0, xmm0
0x180033c54  mov     [rbp+30h+var_88], rax
0x180033c58  mov     r14, rcx
0x180033c5b  mov     [rsp+130h+GrantedAccess], eax
0x180033c5f  lea     r8, [rbp+30h+TokenHandle]; TokenHandle
0x180033c63  mov     [rsp+130h+AccessStatus], eax
0x180033c67  lea     edx, [rax+0Ah]; DesiredAccess
0x180033c6a  mov     [rsp+130h+DuplicateTokenHandle], rax
0x180033c6f  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180033c73  mov     [rbp+30h+TokenHandle], rax
0x180033c77  movups  xmmword ptr [rbp+30h+GenericMapping.GenericRead], xmm0
0x180033c7b  xor     esi, esi
0x180033c7d  mov     [rsp+130h+pSid], rax
0x180033c82  movups  [rbp+30h+SecurityDescriptor], xmm0
0x180033c86  movups  [rbp+30h+var_98], xmm0
0x180033c8a  call    cs:__imp_OpenProcessToken
0x180033c90  test    eax, eax
0x180033c92  jz      short loc_180033CCF
0x180033c94  mov     rcx, [rbp+30h+TokenHandle]; ExistingTokenHandle
0x180033c98  lea     r8, [rsp+130h+DuplicateTokenHandle]; DuplicateTokenHandle
0x180033c9d  lea     edx, [rsi+2]; ImpersonationLevel
0x180033ca0  call    cs:__imp_DuplicateToken
0x180033ca6  test    eax, eax
0x180033ca8  jz      short loc_180033CCF
0x180033caa  mov     rcx, gs:60h
0x180033cb3  mov     edi, 198h
0x180033cb8  mov     r8d, edi; Size
0x180033cbb  xor     edx, edx; Flags
0x180033cbd  mov     rcx, [rcx+30h]; HeapHandle
0x180033cc1  call    cs:__imp_RtlAllocateHeap
0x180033cc7  mov     rbx, rax
0x180033cca  test    rax, rax
0x180033ccd  jnz     short loc_180033D1C
0x180033ccf  mov     rcx, [rsp+130h+pSid]; pSid
0x180033cd4  test    rcx, rcx
0x180033cd7  jz      short loc_180033CDF
0x180033cd9  call    cs:__imp_FreeSid
0x180033cdf  mov     rcx, [rsp+130h+DuplicateTokenHandle]; hObject
0x180033ce4  test    rcx, rcx
0x180033ce7  jz      short loc_180033CEF
0x180033ce9  call    cs:__imp_CloseHandle
0x180033cef  mov     rcx, [rbp+30h+TokenHandle]; hObject
0x180033cf3  test    rcx, rcx
0x180033cf6  jz      short loc_180033CFE
0x180033cf8  call    cs:__imp_CloseHandle
0x180033cfe  mov     eax, esi
0x180033d00  mov     rcx, [rbp+30h+var_38]
0x180033d04  xor     rcx, rsp; StackCookie
0x180033d07  call    __security_check_cookie
0x180033d0c  add     rsp, 108h
0x180033d13  pop     r14
0x180033d15  pop     r12
0x180033d17  pop     rdi
0x180033d18  pop     rsi
0x180033d19  pop     rbx
0x180033d1a  pop     rbp
0x180033d1b  retn
0x180033d1c  mov     r8d, 2; AclRevision
0x180033d22  mov     edx, edi; AclSize
0x180033d24  mov     rcx, rbx; Acl
0x180033d27  call    cs:__imp_RtlCreateAcl
0x180033d2d  xor     edi, edi
0x180033d2f  lea     r12d, [rdi+1]
0x180033d33  lea     r10, BasepBlockedServiceSids
0x180033d3a  cmp     edi, 5
0x180033d3d  jnb     loc_180033DE4
0x180033d43  mov     rcx, [rsp+130h+pSid]; pSid
0x180033d48  test    rcx, rcx
0x180033d4b  jz      short loc_180033D5F
0x180033d4d  call    cs:__imp_FreeSid
0x180033d53  lea     r10, BasepBlockedServiceSids
0x180033d5a  mov     [rsp+130h+pSid], rsi
0x180033d5f  lea     rdx, [rdi+rdi*8]
0x180033d63  mov     r9d, [r10+rdx*4+8]; nSubAuthority1
0x180033d68  lea     rax, [rsp+130h+pSid]
0x180033d6d  mov     r8d, [r10+rdx*4+4]; nSubAuthority0
0x180033d72  lea     rcx, BasepNtIdentifierAuthority; pIdentifierAuthority
0x180033d79  mov     [rsp+130h+var_E0], rax; pSid
0x180033d7e  mov     eax, [r10+rdx*4+20h]
0x180033d83  mov     [rsp+130h+nSubAuthority7], eax; nSubAuthority7
0x180033d87  mov     eax, [r10+rdx*4+1Ch]
0x180033d8c  mov     [rsp+130h+nSubAuthority6], eax; nSubAuthority6
0x180033d90  mov     eax, [r10+rdx*4+18h]
0x180033d95  mov     [rsp+130h+nSubAuthority5], eax; nSubAuthority5
0x180033d99  mov     eax, [r10+rdx*4+14h]
0x180033d9e  mov     [rsp+130h+nSubAuthority4], eax; nSubAuthority4
0x180033da2  mov     eax, [r10+rdx*4+10h]
0x180033da7  mov     [rsp+130h+nSubAuthority3], eax; nSubAuthority3
0x180033dab  mov     eax, [r10+rdx*4+0Ch]
0x180033db0  mov     dl, [r10+rdx*4]; nSubAuthorityCount
0x180033db4  mov     [rsp+130h+nSubAuthority2], eax; nSubAuthority2
0x180033db8  call    cs:__imp_AllocateAndInitializeSid
0x180033dbe  test    eax, eax
0x180033dc0  jz      loc_180033E98
0x180033dc6  mov     r9, [rsp+130h+pSid]; Sid
0x180033dcb  mov     r8d, r12d; AccessMask
0x180033dce  mov     edx, 2; Revision
0x180033dd3  mov     rcx, rbx; Acl
0x180033dd6  call    cs:__imp_RtlAddAccessAllowedAce
0x180033ddc  add     edi, r12d
0x180033ddf  jmp     loc_180033D33
0x180033de4  mov     edx, r12d; Revision
0x180033de7  lea     rcx, [rbp+30h+SecurityDescriptor]; SecurityDescriptor
0x180033deb  call    cs:__imp_RtlCreateSecurityDescriptor
0x180033df1  mov     rdx, [rsp+130h+pSid]; Owner
0x180033df6  lea     rcx, [rbp+30h+SecurityDescriptor]; SecurityDescriptor
0x180033dfa  xor     r8d, r8d; OwnerDefaulted
0x180033dfd  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x180033e03  mov     rdx, [rsp+130h+pSid]; Group
0x180033e08  lea     rcx, [rbp+30h+SecurityDescriptor]; SecurityDescriptor
0x180033e0c  xor     r8d, r8d; GroupDefaulted
0x180033e0f  call    cs:__imp_RtlSetGroupSecurityDescriptor
0x180033e15  xor     r9d, r9d; DaclDefaulted
0x180033e18  lea     rcx, [rbp+30h+SecurityDescriptor]; SecurityDescriptor
0x180033e1c  mov     r8, rbx; Dacl
0x180033e1f  mov     dl, r12b; DaclPresent
0x180033e22  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x180033e28  mov     rdx, [rsp+130h+DuplicateTokenHandle]; ClientToken
0x180033e2d  lea     r9, [rbp+30h+GenericMapping]; GenericMapping
0x180033e31  mov     eax, 20000h
0x180033e36  mov     [rbp+30h+GenericMapping.GenericRead], 20001h
0x180033e3d  mov     [rbp+30h+GenericMapping.GenericWrite], eax
0x180033e40  lea     rcx, [rbp+30h+SecurityDescriptor]; pSecurityDescriptor
0x180033e44  mov     [rbp+30h+GenericMapping.GenericExecute], eax
0x180033e47  mov     r8d, r12d; DesiredAccess
0x180033e4a  lea     rax, [rsp+130h+AccessStatus]
0x180033e4f  mov     [rbp+30h+GenericMapping.GenericAll], 1F0001h
0x180033e56  mov     qword ptr [rsp+130h+nSubAuthority5], rax; AccessStatus
0x180033e5b  lea     rax, [rsp+130h+GrantedAccess]
0x180033e60  mov     qword ptr [rsp+130h+nSubAuthority4], rax; GrantedAccess
0x180033e65  lea     rax, [rsp+130h+PrivilegeSetLength]
0x180033e6a  mov     qword ptr [rsp+130h+nSubAuthority3], rax; PrivilegeSetLength
0x180033e6f  lea     rax, [rbp+30h+PrivilegeSet]
0x180033e73  mov     qword ptr [rsp+130h+nSubAuthority2], rax; PrivilegeSet
0x180033e78  mov     [rsp+130h+PrivilegeSetLength], 38h ; '8'
0x180033e80  call    cs:__imp_AccessCheck
0x180033e86  test    eax, eax
0x180033e88  jz      short loc_180033E98
0x180033e8a  cmp     [rsp+130h+AccessStatus], esi
0x180033e8e  jnz     short loc_180033EB5
0x180033e90  xor     eax, eax
0x180033e92  mov     [r14], eax
0x180033e95  mov     esi, r12d
0x180033e98  mov     rcx, gs:60h
0x180033ea1  mov     r8, rbx; P
0x180033ea4  xor     edx, edx; Flags
0x180033ea6  mov     rcx, [rcx+30h]; HeapHandle
0x180033eaa  call    cs:__imp_RtlFreeHeap
0x180033eb0  jmp     loc_180033CCF
0x180033eb5  cmp     [rsp+130h+GrantedAccess], r12d
0x180033eba  jnz     short loc_180033E90
0x180033ebc  mov     eax, r12d
0x180033ebf  jmp     short loc_180033E92
```
