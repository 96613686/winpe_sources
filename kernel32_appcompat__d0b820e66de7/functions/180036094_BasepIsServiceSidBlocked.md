# BasepIsServiceSidBlocked

- ea: `0x180036094`
- end: `0x180036392`
- name: `BasepIsServiceSidBlocked`
- size: `766`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180035f10`

## callees

- `0x180036094`
- `0x1800827c0`

## import_xrefs

- `ntdll!RtlCreateSecurityDescriptor` at `0x180036298`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180036298`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x1800362c8`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x1800362c8`
- `ntdll!RtlCreateAcl` at `0x1800361bc`
- `ntdll!RtlCreateAcl` at `0x1800361bc`
- `ntdll!RtlFreeHeap` at `0x180036375`
- `ntdll!RtlFreeHeap` at `0x180036375`
- `ntdll!RtlAddAccessAllowedAce` at `0x18003627d`
- `ntdll!RtlAddAccessAllowedAce` at `0x18003627d`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x1800362e1`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x1800362e1`
- `ntdll!RtlAllocateHeap` at `0x18003613d`
- `ntdll!RtlAllocateHeap` at `0x18003613d`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x1800362b0`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x1800362b0`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800360fa`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800360fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180036171`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180036186`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180036171`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180036186`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180036116`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180036116`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18003615b`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800361e8`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18003615b`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800361e8`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180036259`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180036259`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180036345`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180036345`

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
0x180036094  push    rbp
0x180036096  push    rbx
0x180036097  push    rsi
0x180036098  push    rdi
0x180036099  push    r12
0x18003609b  push    r14
0x18003609d  lea     rbp, [rsp-8]
0x1800360a2  sub     rsp, 108h
0x1800360a9  mov     rax, cs:__security_cookie
0x1800360b0  xor     rax, rsp
0x1800360b3  mov     [rbp+30h+var_38], rax
0x1800360b7  xor     eax, eax
0x1800360b9  mov     [rsp+130h+PrivilegeSetLength], 0
0x1800360c1  xorps   xmm0, xmm0
0x1800360c4  mov     [rbp+30h+var_88], rax
0x1800360c8  mov     r14, rcx
0x1800360cb  mov     [rsp+130h+GrantedAccess], eax
0x1800360cf  lea     r8, [rbp+30h+TokenHandle]; TokenHandle
0x1800360d3  mov     [rsp+130h+AccessStatus], eax
0x1800360d7  lea     edx, [rax+0Ah]; DesiredAccess
0x1800360da  mov     [rsp+130h+DuplicateTokenHandle], rax
0x1800360df  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1800360e3  mov     [rbp+30h+TokenHandle], rax
0x1800360e7  movups  xmmword ptr [rbp+30h+GenericMapping.GenericRead], xmm0
0x1800360eb  xor     esi, esi
0x1800360ed  mov     [rsp+130h+pSid], rax
0x1800360f2  movups  [rbp+30h+SecurityDescriptor], xmm0
0x1800360f6  movups  [rbp+30h+var_98], xmm0
0x1800360fa  call    cs:__imp_OpenProcessToken
0x180036101  nop     dword ptr [rax+rax+00h]
0x180036106  test    eax, eax
0x180036108  jz      short loc_180036151
0x18003610a  mov     rcx, [rbp+30h+TokenHandle]; ExistingTokenHandle
0x18003610e  lea     r8, [rsp+130h+DuplicateTokenHandle]; DuplicateTokenHandle
0x180036113  lea     edx, [rsi+2]; ImpersonationLevel
0x180036116  call    cs:__imp_DuplicateToken
0x18003611d  nop     dword ptr [rax+rax+00h]
0x180036122  test    eax, eax
0x180036124  jz      short loc_180036151
0x180036126  mov     rcx, gs:60h
0x18003612f  mov     edi, 198h
0x180036134  mov     r8d, edi; Size
0x180036137  xor     edx, edx; Flags
0x180036139  mov     rcx, [rcx+30h]; HeapHandle
0x18003613d  call    cs:__imp_RtlAllocateHeap
0x180036144  nop     dword ptr [rax+rax+00h]
0x180036149  mov     rbx, rax
0x18003614c  test    rax, rax
0x18003614f  jnz     short loc_1800361B1
0x180036151  mov     rcx, [rsp+130h+pSid]; pSid
0x180036156  test    rcx, rcx
0x180036159  jz      short loc_180036167
0x18003615b  call    cs:__imp_FreeSid
0x180036162  nop     dword ptr [rax+rax+00h]
0x180036167  mov     rcx, [rsp+130h+DuplicateTokenHandle]; hObject
0x18003616c  test    rcx, rcx
0x18003616f  jz      short loc_18003617D
0x180036171  call    cs:__imp_CloseHandle
0x180036178  nop     dword ptr [rax+rax+00h]
0x18003617d  mov     rcx, [rbp+30h+TokenHandle]; hObject
0x180036181  test    rcx, rcx
0x180036184  jz      short loc_180036192
0x180036186  call    cs:__imp_CloseHandle
0x18003618d  nop     dword ptr [rax+rax+00h]
0x180036192  mov     eax, esi
0x180036194  mov     rcx, [rbp+30h+var_38]
0x180036198  xor     rcx, rsp; StackCookie
0x18003619b  call    __security_check_cookie
0x1800361a0  add     rsp, 108h
0x1800361a7  pop     r14
0x1800361a9  pop     r12
0x1800361ab  pop     rdi
0x1800361ac  pop     rsi
0x1800361ad  pop     rbx
0x1800361ae  pop     rbp
0x1800361af  retn
0x1800361b1  mov     r8d, 2; AclRevision
0x1800361b7  mov     edx, edi; AclSize
0x1800361b9  mov     rcx, rbx; Acl
0x1800361bc  call    cs:__imp_RtlCreateAcl
0x1800361c3  nop     dword ptr [rax+rax+00h]
0x1800361c8  xor     edi, edi
0x1800361ca  lea     r12d, [rdi+1]
0x1800361ce  lea     r10, BasepBlockedServiceSids
0x1800361d5  cmp     edi, 5
0x1800361d8  jnb     loc_180036291
0x1800361de  mov     rcx, [rsp+130h+pSid]; pSid
0x1800361e3  test    rcx, rcx
0x1800361e6  jz      short loc_180036200
0x1800361e8  call    cs:__imp_FreeSid
0x1800361ef  nop     dword ptr [rax+rax+00h]
0x1800361f4  lea     r10, BasepBlockedServiceSids
0x1800361fb  mov     [rsp+130h+pSid], rsi
0x180036200  lea     rdx, [rdi+rdi*8]
0x180036204  mov     r9d, [r10+rdx*4+8]; nSubAuthority1
0x180036209  lea     rax, [rsp+130h+pSid]
0x18003620e  mov     r8d, [r10+rdx*4+4]; nSubAuthority0
0x180036213  lea     rcx, BasepNtIdentifierAuthority; pIdentifierAuthority
0x18003621a  mov     [rsp+130h+var_E0], rax; pSid
0x18003621f  mov     eax, [r10+rdx*4+20h]
0x180036224  mov     [rsp+130h+nSubAuthority7], eax; nSubAuthority7
0x180036228  mov     eax, [r10+rdx*4+1Ch]
0x18003622d  mov     [rsp+130h+nSubAuthority6], eax; nSubAuthority6
0x180036231  mov     eax, [r10+rdx*4+18h]
0x180036236  mov     [rsp+130h+nSubAuthority5], eax; nSubAuthority5
0x18003623a  mov     eax, [r10+rdx*4+14h]
0x18003623f  mov     [rsp+130h+nSubAuthority4], eax; nSubAuthority4
0x180036243  mov     eax, [r10+rdx*4+10h]
0x180036248  mov     [rsp+130h+nSubAuthority3], eax; nSubAuthority3
0x18003624c  mov     eax, [r10+rdx*4+0Ch]
0x180036251  mov     dl, [r10+rdx*4]; nSubAuthorityCount
0x180036255  mov     [rsp+130h+nSubAuthority2], eax; nSubAuthority2
0x180036259  call    cs:__imp_AllocateAndInitializeSid
0x180036260  nop     dword ptr [rax+rax+00h]
0x180036265  test    eax, eax
0x180036267  jz      loc_180036363
0x18003626d  mov     r9, [rsp+130h+pSid]; Sid
0x180036272  mov     r8d, r12d; AccessMask
0x180036275  mov     edx, 2; Revision
0x18003627a  mov     rcx, rbx; Acl
0x18003627d  call    cs:__imp_RtlAddAccessAllowedAce
0x180036284  nop     dword ptr [rax+rax+00h]
0x180036289  add     edi, r12d
0x18003628c  jmp     loc_1800361CE
0x180036291  mov     edx, r12d; Revision
0x180036294  lea     rcx, [rbp+30h+SecurityDescriptor]; SecurityDescriptor
0x180036298  call    cs:__imp_RtlCreateSecurityDescriptor
0x18003629f  nop     dword ptr [rax+rax+00h]
0x1800362a4  mov     rdx, [rsp+130h+pSid]; Owner
0x1800362a9  lea     rcx, [rbp+30h+SecurityDescriptor]; SecurityDescriptor
0x1800362ad  xor     r8d, r8d; OwnerDefaulted
0x1800362b0  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x1800362b7  nop     dword ptr [rax+rax+00h]
0x1800362bc  mov     rdx, [rsp+130h+pSid]; Group
0x1800362c1  lea     rcx, [rbp+30h+SecurityDescriptor]; SecurityDescriptor
0x1800362c5  xor     r8d, r8d; GroupDefaulted
0x1800362c8  call    cs:__imp_RtlSetGroupSecurityDescriptor
0x1800362cf  nop     dword ptr [rax+rax+00h]
0x1800362d4  xor     r9d, r9d; DaclDefaulted
0x1800362d7  lea     rcx, [rbp+30h+SecurityDescriptor]; SecurityDescriptor
0x1800362db  mov     r8, rbx; Dacl
0x1800362de  mov     dl, r12b; DaclPresent
0x1800362e1  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1800362e8  nop     dword ptr [rax+rax+00h]
0x1800362ed  mov     rdx, [rsp+130h+DuplicateTokenHandle]; ClientToken
0x1800362f2  lea     r9, [rbp+30h+GenericMapping]; GenericMapping
0x1800362f6  mov     eax, 20000h
0x1800362fb  mov     [rbp+30h+GenericMapping.GenericRead], 20001h
0x180036302  mov     [rbp+30h+GenericMapping.GenericWrite], eax
0x180036305  lea     rcx, [rbp+30h+SecurityDescriptor]; pSecurityDescriptor
0x180036309  mov     [rbp+30h+GenericMapping.GenericExecute], eax
0x18003630c  mov     r8d, r12d; DesiredAccess
0x18003630f  lea     rax, [rsp+130h+AccessStatus]
0x180036314  mov     [rbp+30h+GenericMapping.GenericAll], 1F0001h
0x18003631b  mov     qword ptr [rsp+130h+nSubAuthority5], rax; AccessStatus
0x180036320  lea     rax, [rsp+130h+GrantedAccess]
0x180036325  mov     qword ptr [rsp+130h+nSubAuthority4], rax; GrantedAccess
0x18003632a  lea     rax, [rsp+130h+PrivilegeSetLength]
0x18003632f  mov     qword ptr [rsp+130h+nSubAuthority3], rax; PrivilegeSetLength
0x180036334  lea     rax, [rbp+30h+PrivilegeSet]
0x180036338  mov     qword ptr [rsp+130h+nSubAuthority2], rax; PrivilegeSet
0x18003633d  mov     [rsp+130h+PrivilegeSetLength], 38h ; '8'
0x180036345  call    cs:__imp_AccessCheck
0x18003634c  nop     dword ptr [rax+rax+00h]
0x180036351  test    eax, eax
0x180036353  jz      short loc_180036363
0x180036355  cmp     [rsp+130h+AccessStatus], esi
0x180036359  jnz     short loc_180036386
0x18003635b  xor     eax, eax
0x18003635d  mov     [r14], eax
0x180036360  mov     esi, r12d
0x180036363  mov     rcx, gs:60h
0x18003636c  mov     r8, rbx; P
0x18003636f  xor     edx, edx; Flags
0x180036371  mov     rcx, [rcx+30h]; HeapHandle
0x180036375  call    cs:__imp_RtlFreeHeap
0x18003637c  nop     dword ptr [rax+rax+00h]
0x180036381  jmp     loc_180036151
0x180036386  cmp     [rsp+130h+GrantedAccess], r12d
0x18003638b  jnz     short loc_18003635B
0x18003638d  mov     eax, r12d
0x180036390  jmp     short loc_18003635D
```
