# KclCheckCurrentTokenMembership

- ea: `0x1400400e8`
- end: `0x1400402de`
- name: `KclCheckCurrentTokenMembership`
- size: `502`
- prototype: `__int64 __fastcall(PSID Sid)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14003fae4`

## callees

- `0x140011650`
- `0x1400119c0`
- `0x1400400e8`

## import_xrefs

- `ntoskrnl!SeCaptureSubjectContext` at `0x140040151`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140040151`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1400402b0`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1400402b0`
- `ntoskrnl!SeAccessCheck` at `0x140040281`
- `ntoskrnl!SeAccessCheck` at `0x140040281`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140040167`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140040167`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14004021c`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14004021c`
- `ntoskrnl!RtlCreateAcl` at `0x1400401cf`
- `ntoskrnl!RtlCreateAcl` at `0x1400401cf`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400401f8`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400401f8`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x140040188`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x140040188`
- `ntoskrnl!RtlSetGroupSecurityDescriptor` at `0x1400401ac`
- `ntoskrnl!RtlSetGroupSecurityDescriptor` at `0x1400401ac`
- `ntoskrnl!ExGetPreviousMode` at `0x14004022e`
- `ntoskrnl!ExGetPreviousMode` at `0x14004022e`

## pseudocode

```c
__int64 __fastcall KclCheckCurrentTokenMembership(PSID Sid, _BYTE *a2)
{
  NTSTATUS v4; // ebx
  KPROCESSOR_MODE AccessMode; // al
  int AccessStatus; // [rsp+50h] [rbp-B0h] BYREF
  DWORD GrantedAccess; // [rsp+54h] [rbp-ACh] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v10; // [rsp+78h] [rbp-88h]
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+80h] [rbp-80h] BYREF
  _ACL Acl[12]; // [rsp+A0h] [rbp-60h] BYREF

  GrantedAccess = 0;
  AccessStatus = -1073741790;
  memset(Acl, 0, 0x54u);
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  v10 = 0;
  *a2 = 0;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  SeCaptureSubjectContext(&SubjectContext);
  v4 = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
  if ( v4 >= 0 )
  {
    v4 = RtlSetOwnerSecurityDescriptor(SecurityDescriptor, Sid, 0);
    if ( v4 >= 0 )
    {
      _mm_lfence();
      v4 = RtlSetGroupSecurityDescriptor(SecurityDescriptor, Sid, 0);
      if ( v4 >= 0 )
      {
        v4 = RtlCreateAcl(Acl, 0x54u, 2u);
        if ( v4 >= 0 )
        {
          _mm_lfence();
          v4 = RtlAddAccessAllowedAce(Acl, 2u, 1u, Sid);
          if ( v4 >= 0 )
          {
            v4 = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, Acl, 0);
            if ( v4 >= 0 )
            {
              AccessMode = ExGetPreviousMode();
              SeAccessCheck(
                SecurityDescriptor,
                &SubjectContext,
                0,
                1u,
                0,
                0,
                (PGENERIC_MAPPING)&RtlCheckTokenMembershipGenericMapping,
                AccessMode,
                &GrantedAccess,
                &AccessStatus);
              v4 = 0;
              if ( AccessStatus )
              {
                if ( AccessStatus == -1073741790 )
                  goto LABEL_12;
              }
              else if ( GrantedAccess == 1 )
              {
                *a2 = 1;
                goto LABEL_12;
              }
              v4 = AccessStatus;
            }
          }
        }
      }
    }
  }
LABEL_12:
  SeReleaseSubjectContext(&SubjectContext);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1400400e8  mov     [rsp-8+arg_10], rbx
0x1400400ed  push    rbp
0x1400400ee  push    rsi
0x1400400ef  push    rdi
0x1400400f0  lea     rbp, [rsp-10h]
0x1400400f5  sub     rsp, 110h
0x1400400fc  mov     rax, cs:__security_cookie
0x140040103  xor     rax, rsp
0x140040106  mov     [rbp+20h+var_20], rax
0x14004010a  mov     rsi, rdx
0x14004010d  mov     [rsp+120h+var_CC], 0
0x140040115  xor     edx, edx; Val
0x140040117  mov     [rsp+120h+var_D0], 0C0000022h
0x14004011f  mov     rdi, rcx
0x140040122  lea     rcx, [rbp+20h+Acl]; void *
0x140040126  lea     r8d, [rdx+54h]; Size
0x14004012a  call    memset
0x14004012f  xorps   xmm0, xmm0
0x140040132  lea     rcx, [rbp+20h+SubjectContext]; SubjectContext
0x140040136  xor     eax, eax
0x140040138  movups  [rsp+120h+SecurityDescriptor], xmm0
0x14004013d  mov     [rsp+120h+var_A8], rax
0x140040142  movups  [rsp+120h+var_B8], xmm0
0x140040147  mov     [rsi], al
0x140040149  movups  xmmword ptr [rbp+20h+SubjectContext.ClientToken], xmm0
0x14004014d  movups  xmmword ptr [rbp+20h+SubjectContext.PrimaryToken], xmm0
0x140040151  call    cs:__imp_SeCaptureSubjectContext
0x140040158  nop     dword ptr [rax+rax+00h]
0x14004015d  mov     edx, 1; Revision
0x140040162  lea     rcx, [rsp+120h+SecurityDescriptor]; SecurityDescriptor
0x140040167  call    cs:__imp_RtlCreateSecurityDescriptor
0x14004016e  nop     dword ptr [rax+rax+00h]
0x140040173  mov     ebx, eax
0x140040175  test    eax, eax
0x140040177  js      loc_1400402AC
0x14004017d  xor     r8d, r8d; OwnerDefaulted
0x140040180  lea     rcx, [rsp+120h+SecurityDescriptor]; SecurityDescriptor
0x140040185  mov     rdx, rdi; Owner
0x140040188  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x14004018f  nop     dword ptr [rax+rax+00h]
0x140040194  mov     ebx, eax
0x140040196  test    eax, eax
0x140040198  js      loc_1400402AC
0x14004019e  lfence
0x1400401a1  xor     r8d, r8d; GroupDefaulted
0x1400401a4  lea     rcx, [rsp+120h+SecurityDescriptor]; SecurityDescriptor
0x1400401a9  mov     rdx, rdi; Group
0x1400401ac  call    cs:__imp_RtlSetGroupSecurityDescriptor
0x1400401b3  nop     dword ptr [rax+rax+00h]
0x1400401b8  mov     ebx, eax
0x1400401ba  test    eax, eax
0x1400401bc  js      loc_1400402AC
0x1400401c2  mov     edx, 54h ; 'T'; AclLength
0x1400401c7  lea     rcx, [rbp+20h+Acl]; Acl
0x1400401cb  lea     r8d, [rdx-52h]; AclRevision
0x1400401cf  call    cs:__imp_RtlCreateAcl
0x1400401d6  nop     dword ptr [rax+rax+00h]
0x1400401db  mov     ebx, eax
0x1400401dd  test    eax, eax
0x1400401df  js      loc_1400402AC
0x1400401e5  lfence
0x1400401e8  mov     edx, 2; AceRevision
0x1400401ed  lea     rcx, [rbp+20h+Acl]; Acl
0x1400401f1  mov     r9, rdi; Sid
0x1400401f4  lea     r8d, [rdx-1]; AccessMask
0x1400401f8  call    cs:__imp_RtlAddAccessAllowedAce
0x1400401ff  nop     dword ptr [rax+rax+00h]
0x140040204  mov     ebx, eax
0x140040206  test    eax, eax
0x140040208  js      loc_1400402AC
0x14004020e  xor     r9d, r9d; DaclDefaulted
0x140040211  lea     r8, [rbp+20h+Acl]; Dacl
0x140040215  mov     dl, 1; DaclPresent
0x140040217  lea     rcx, [rsp+120h+SecurityDescriptor]; SecurityDescriptor
0x14004021c  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x140040223  nop     dword ptr [rax+rax+00h]
0x140040228  mov     ebx, eax
0x14004022a  test    eax, eax
0x14004022c  js      short loc_1400402AC
0x14004022e  call    cs:__imp_ExGetPreviousMode
0x140040235  nop     dword ptr [rax+rax+00h]
0x14004023a  lea     rcx, [rsp+120h+var_D0]
0x14004023f  mov     r9d, 1; DesiredAccess
0x140040245  mov     [rsp+120h+AccessStatus], rcx; AccessStatus
0x14004024a  lea     rdx, [rbp+20h+SubjectContext]; SubjectSecurityContext
0x14004024e  lea     rcx, [rsp+120h+var_CC]
0x140040253  xor     r8d, r8d; SubjectContextLocked
0x140040256  mov     [rsp+120h+GrantedAccess], rcx; GrantedAccess
0x14004025b  lea     rcx, [rsp+120h+SecurityDescriptor]; SecurityDescriptor
0x140040260  mov     [rsp+120h+AccessMode], al; AccessMode
0x140040264  lea     rax, RtlCheckTokenMembershipGenericMapping
0x14004026b  mov     [rsp+120h+GenericMapping], rax; GenericMapping
0x140040270  mov     [rsp+120h+Privileges], 0; Privileges
0x140040279  mov     [rsp+120h+PreviouslyGrantedAccess], 0; PreviouslyGrantedAccess
0x140040281  call    cs:__imp_SeAccessCheck
0x140040288  nop     dword ptr [rax+rax+00h]
0x14004028d  mov     eax, [rsp+120h+var_D0]
0x140040291  xor     ebx, ebx
0x140040293  test    eax, eax
0x140040295  jnz     short loc_1400402A3
0x140040297  cmp     [rsp+120h+var_CC], 1
0x14004029c  jnz     short loc_1400402AA
0x14004029e  mov     byte ptr [rsi], 1
0x1400402a1  jmp     short loc_1400402AC
0x1400402a3  cmp     eax, 0C0000022h
0x1400402a8  jz      short loc_1400402AC
0x1400402aa  mov     ebx, eax
0x1400402ac  lea     rcx, [rbp+20h+SubjectContext]; SubjectContext
0x1400402b0  call    cs:__imp_SeReleaseSubjectContext
0x1400402b7  nop     dword ptr [rax+rax+00h]
0x1400402bc  mov     eax, ebx
0x1400402be  mov     rcx, [rbp+20h+var_20]
0x1400402c2  xor     rcx, rsp; StackCookie
0x1400402c5  call    __security_check_cookie
0x1400402ca  mov     rbx, [rsp+120h+arg_10]
0x1400402d2  add     rsp, 110h
0x1400402d9  pop     rdi
0x1400402da  pop     rsi
0x1400402db  pop     rbp
0x1400402dc  retn
```
