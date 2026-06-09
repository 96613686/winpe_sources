# UlAccessCheck

- ea: `0x1400422d8`
- end: `0x1400424aa`
- name: `UlAccessCheck`
- size: `466`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR SecurityDescriptor, PACCESS_STATE AccessState, ACCESS_MASK DesiredAccess, KPROCESSOR_MODE AccessMode, __int64, char)`
- caller_count: `6`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400176a0`
- `0x140043274`
- `0x1400432dc`
- `0x140095d9c`
- `0x1400cf398`
- `0x14012fb98`

## callees

- `0x1400422d8`
- `0x1400424b0`
- `0x1401c3f58`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14004232a`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14004232a`
- `ntoskrnl!SeAppendPrivileges` at `0x14004243b`
- `ntoskrnl!SeAppendPrivileges` at `0x14004243b`
- `ntoskrnl!SeFreePrivileges` at `0x14004244b`
- `ntoskrnl!SeFreePrivileges` at `0x14004244b`
- `ntoskrnl!SeAccessCheck` at `0x14004236b`
- `ntoskrnl!SeAccessCheck` at `0x14004236b`
- `ntoskrnl!SeOpenObjectAuditAlarm` at `0x1400423e8`
- `ntoskrnl!SeOpenObjectAuditAlarm` at `0x1400423e8`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1400423f7`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1400423f7`
- `ntoskrnl!SeLockSubjectContext` at `0x14004231e`
- `ntoskrnl!SeLockSubjectContext` at `0x14004231e`

## pseudocode

```c
__int64 __fastcall UlAccessCheck(
        PSECURITY_DESCRIPTOR SecurityDescriptor,
        PACCESS_STATE AccessState,
        ACCESS_MASK DesiredAccess,
        KPROCESSOR_MODE AccessMode,
        __int64 a5,
        char a6)
{
  SECURITY_SUBJECT_CONTEXT *p_SubjectSecurityContext; // r15
  struct _GENERIC_MAPPING *GenericMapping; // rax
  BOOLEAN v12; // si
  DWORD v14; // ebx
  int AccessStatus; // [rsp+50h] [rbp-29h] BYREF
  PPRIVILEGE_SET Privileges; // [rsp+58h] [rbp-21h] BYREF
  struct _UNICODE_STRING ObjectTypeName; // [rsp+60h] [rbp-19h] BYREF
  struct _UNICODE_STRING AbsoluteObjectName; // [rsp+70h] [rbp-9h] BYREF
  DWORD GrantedAccess; // [rsp+D8h] [rbp+5Fh] BYREF

  p_SubjectSecurityContext = &AccessState->SubjectSecurityContext;
  AccessStatus = 0;
  Privileges = 0;
  GrantedAccess = 0;
  AbsoluteObjectName = 0;
  ObjectTypeName = 0;
  SeLockSubjectContext(&AccessState->SubjectSecurityContext);
  GenericMapping = IoGetFileObjectGenericMapping();
  v12 = SeAccessCheck(
          SecurityDescriptor,
          p_SubjectSecurityContext,
          1u,
          DesiredAccess,
          0,
          &Privileges,
          GenericMapping,
          AccessMode,
          &GrantedAccess,
          &AccessStatus);
  if ( Privileges )
  {
    SeAppendPrivileges(AccessState, Privileges);
    SeFreePrivileges(Privileges);
  }
  if ( !a6 )
  {
    if ( !v12 )
      goto LABEL_5;
    goto LABEL_10;
  }
  if ( v12 )
  {
LABEL_10:
    v14 = GrantedAccess;
LABEL_11:
    AccessState->PreviouslyGrantedAccess |= v14;
    AccessState->RemainingDesiredAccess &= ~(v14 | 0x2000000);
    goto LABEL_5;
  }
  if ( (AccessState->Flags & 0x106) == 0x106 )
  {
    v14 = 917504;
    if ( DesiredAccess == 917504 )
    {
      if ( (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
        WPP_SF_(1049, 10, WPP_fe1f27503c643dfeaad4ba070b430e9e_Traceguids);
      GrantedAccess = 917504;
      v12 = 1;
      goto LABEL_11;
    }
  }
  if ( (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_d(1049, 11, WPP_fe1f27503c643dfeaad4ba070b430e9e_Traceguids, AccessState->Flags);
LABEL_5:
  *(_DWORD *)&ObjectTypeName.Length = 393220;
  ObjectTypeName.Buffer = L"Ul";
  if ( (int)UlInitUnicodeStringEx(&AbsoluteObjectName, a5) >= 0 )
    SeOpenObjectAuditAlarm(
      &ObjectTypeName,
      0,
      &AbsoluteObjectName,
      SecurityDescriptor,
      AccessState,
      0,
      v12,
      AccessMode,
      &AccessState->GenerateOnClose);
  SeUnlockSubjectContext(p_SubjectSecurityContext);
  if ( v12 )
    return 0;
  else
    return (unsigned int)AccessStatus;
}

```

## disassembly

```asm
0x1400422d8  push    rbp
0x1400422da  push    rbx
0x1400422db  push    rsi
0x1400422dc  push    rdi
0x1400422dd  push    r12
0x1400422df  push    r13
0x1400422e1  push    r14
0x1400422e3  push    r15
0x1400422e5  lea     rbp, [rsp-0Fh]
0x1400422ea  sub     rsp, 88h
0x1400422f1  xor     ebx, ebx
0x1400422f3  lea     r15, [rdx+20h]
0x1400422f7  mov     r13, rcx
0x1400422fa  mov     [rbp+47h+var_70], ebx
0x1400422fd  xorps   xmm0, xmm0
0x140042300  mov     [rbp+47h+var_68], rbx
0x140042304  xorps   xmm1, xmm1
0x140042307  mov     [rbp+47h+arg_8], ebx
0x14004230a  mov     rcx, r15; SubjectContext
0x14004230d  mov     r12b, r9b
0x140042310  mov     r14d, r8d
0x140042313  mov     rdi, rdx
0x140042316  movups  xmmword ptr [rbp+47h+AbsoluteObjectName.Length], xmm0
0x14004231a  movups  xmmword ptr [rbp+47h+ObjectTypeName.Length], xmm1
0x14004231e  call    cs:__imp_SeLockSubjectContext
0x140042325  nop     dword ptr [rax+rax+00h]
0x14004232a  call    cs:__imp_IoGetFileObjectGenericMapping
0x140042331  nop     dword ptr [rax+rax+00h]
0x140042336  lea     rcx, [rbp+47h+var_70]
0x14004233a  mov     r9d, r14d; DesiredAccess
0x14004233d  mov     [rsp+0C0h+AccessStatus], rcx; AccessStatus
0x140042342  mov     r8b, 1; SubjectContextLocked
0x140042345  lea     rcx, [rbp+47h+arg_8]
0x140042349  mov     rdx, r15; SubjectSecurityContext
0x14004234c  mov     [rsp+0C0h+GrantedAccess], rcx; GrantedAccess
0x140042351  mov     rcx, r13; SecurityDescriptor
0x140042354  mov     [rsp+0C0h+AccessMode], r12b; AccessMode
0x140042359  mov     [rsp+0C0h+GenericMapping], rax; GenericMapping
0x14004235e  lea     rax, [rbp+47h+var_68]
0x140042362  mov     [rsp+0C0h+Privileges], rax; Privileges
0x140042367  mov     [rsp+0C0h+PreviouslyGrantedAccess], ebx; PreviouslyGrantedAccess
0x14004236b  call    cs:__imp_SeAccessCheck
0x140042372  nop     dword ptr [rax+rax+00h]
0x140042377  mov     rdx, [rbp+47h+var_68]; Privileges
0x14004237b  mov     sil, al
0x14004237e  mov     bl, al
0x140042380  test    rdx, rdx
0x140042383  jnz     loc_140042438
0x140042389  cmp     [rbp+47h+arg_28], 0
0x14004238d  jnz     loc_14004245C
0x140042393  test    bl, bl
0x140042395  jnz     loc_140042424
0x14004239b  lea     rax, aUl; "Ul"
0x1400423a2  mov     dword ptr [rbp+47h+ObjectTypeName.Length], 60004h
0x1400423a9  mov     [rbp+47h+ObjectTypeName.Buffer], rax
0x1400423ad  mov     rdx, [rbp+47h+arg_20]
0x1400423b1  lea     rcx, [rbp+47h+AbsoluteObjectName]
0x1400423b5  call    UlInitUnicodeStringEx
0x1400423ba  test    eax, eax
0x1400423bc  js      short loc_1400423F4
0x1400423be  lea     rax, [rdi+0Ah]
0x1400423c2  mov     r9, r13; SecurityDescriptor
0x1400423c5  mov     [rsp+0C0h+GrantedAccess], rax; GenerateOnClose
0x1400423ca  lea     r8, [rbp+47h+AbsoluteObjectName]; AbsoluteObjectName
0x1400423ce  mov     [rsp+0C0h+AccessMode], r12b; AccessMode
0x1400423d3  lea     rcx, [rbp+47h+ObjectTypeName]; ObjectTypeName
0x1400423d7  mov     byte ptr [rsp+0C0h+GenericMapping], sil; AccessGranted
0x1400423dc  xor     edx, edx; Object
0x1400423de  mov     byte ptr [rsp+0C0h+Privileges], 0; ObjectCreated
0x1400423e3  mov     qword ptr [rsp+0C0h+PreviouslyGrantedAccess], rdi; AccessState
0x1400423e8  call    cs:__imp_SeOpenObjectAuditAlarm
0x1400423ef  nop     dword ptr [rax+rax+00h]
0x1400423f4  mov     rcx, r15; SubjectContext
0x1400423f7  call    cs:__imp_SeUnlockSubjectContext
0x1400423fe  nop     dword ptr [rax+rax+00h]
0x140042403  test    sil, sil
0x140042406  jz      short loc_14004241F
0x140042408  xor     eax, eax
0x14004240a  add     rsp, 88h
0x140042411  pop     r15
0x140042413  pop     r14
0x140042415  pop     r13
0x140042417  pop     r12
0x140042419  pop     rdi
0x14004241a  pop     rsi
0x14004241b  pop     rbx
0x14004241c  pop     rbp
0x14004241d  retn
0x14004241f  mov     eax, [rbp+47h+var_70]
0x140042422  jmp     short loc_14004240A
0x140042424  mov     ebx, [rbp+47h+arg_8]
0x140042427  or      [rdi+14h], ebx
0x14004242a  bts     ebx, 19h
0x14004242e  not     ebx
0x140042430  and     [rdi+10h], ebx
0x140042433  jmp     loc_14004239B
0x140042438  mov     rcx, rdi; AccessState
0x14004243b  call    cs:__imp_SeAppendPrivileges
0x140042442  nop     dword ptr [rax+rax+00h]
0x140042447  mov     rcx, [rbp+47h+var_68]; Privileges
0x14004244b  call    cs:__imp_SeFreePrivileges
0x140042452  nop     dword ptr [rax+rax+00h]
0x140042457  jmp     loc_140042389
0x14004245c  test    sil, sil
0x14004245f  jnz     short loc_140042424
0x140042461  mov     eax, [rdi+0Ch]
0x140042464  mov     ecx, 106h
0x140042469  and     eax, ecx
0x14004246b  cmp     eax, ecx
0x14004246d  jnz     loc_140175B3B
0x140042473  mov     ebx, 0E0000h
0x140042478  cmp     r14d, ebx
0x14004247b  jnz     loc_140175B3B
0x140042481  test    byte ptr cs:xmmword_1401A2CA0+3, 2
0x140042488  jz      loc_140175B30
0x14004248e  mov     edx, 0Ah
0x140042493  lea     r8, WPP_fe1f27503c643dfeaad4ba070b430e9e_Traceguids
0x14004249a  mov     ecx, 419h
0x14004249f  call    WPP_SF_
0x1400424a4  nop
0x1400424a5  jmp     loc_140175B30
0x140175b30  mov     [rbp+47h+arg_8], ebx
0x140175b33  mov     sil, 1
0x140175b36  jmp     loc_140042427
0x140175b3b  test    byte ptr cs:xmmword_1401A2CA0+3, 2
0x140175b42  jz      loc_14004239B
0x140175b48  mov     r9d, [rdi+0Ch]
0x140175b4c  lea     r8, WPP_fe1f27503c643dfeaad4ba070b430e9e_Traceguids
0x140175b53  mov     edx, 0Bh
0x140175b58  mov     ecx, 419h
0x140175b5d  call    WPP_SF_d
0x140175b62  nop
0x140175b63  jmp     loc_14004239B
```
