# UlAccessCheck

- ea: `0x1400422b8`
- end: `0x14004248a`
- name: `UlAccessCheck`
- size: `466`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR SecurityDescriptor, PACCESS_STATE AccessState, ACCESS_MASK DesiredAccess, KPROCESSOR_MODE AccessMode, __int64, char)`
- caller_count: `6`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400176a0`
- `0x140043254`
- `0x1400432bc`
- `0x140095d7c`
- `0x1400cf2b8`
- `0x14012fc88`

## callees

- `0x1400422b8`
- `0x140042490`
- `0x1401c3f58`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14004230a`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14004230a`
- `ntoskrnl!SeAppendPrivileges` at `0x14004241b`
- `ntoskrnl!SeAppendPrivileges` at `0x14004241b`
- `ntoskrnl!SeFreePrivileges` at `0x14004242b`
- `ntoskrnl!SeFreePrivileges` at `0x14004242b`
- `ntoskrnl!SeAccessCheck` at `0x14004234b`
- `ntoskrnl!SeAccessCheck` at `0x14004234b`
- `ntoskrnl!SeOpenObjectAuditAlarm` at `0x1400423c8`
- `ntoskrnl!SeOpenObjectAuditAlarm` at `0x1400423c8`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1400423d7`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1400423d7`
- `ntoskrnl!SeLockSubjectContext` at `0x1400422fe`
- `ntoskrnl!SeLockSubjectContext` at `0x1400422fe`

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
0x1400422b8  push    rbp
0x1400422ba  push    rbx
0x1400422bb  push    rsi
0x1400422bc  push    rdi
0x1400422bd  push    r12
0x1400422bf  push    r13
0x1400422c1  push    r14
0x1400422c3  push    r15
0x1400422c5  lea     rbp, [rsp-0Fh]
0x1400422ca  sub     rsp, 88h
0x1400422d1  xor     ebx, ebx
0x1400422d3  lea     r15, [rdx+20h]
0x1400422d7  mov     r13, rcx
0x1400422da  mov     [rbp+47h+var_70], ebx
0x1400422dd  xorps   xmm0, xmm0
0x1400422e0  mov     [rbp+47h+var_68], rbx
0x1400422e4  xorps   xmm1, xmm1
0x1400422e7  mov     [rbp+47h+arg_8], ebx
0x1400422ea  mov     rcx, r15; SubjectContext
0x1400422ed  mov     r12b, r9b
0x1400422f0  mov     r14d, r8d
0x1400422f3  mov     rdi, rdx
0x1400422f6  movups  xmmword ptr [rbp+47h+AbsoluteObjectName.Length], xmm0
0x1400422fa  movups  xmmword ptr [rbp+47h+ObjectTypeName.Length], xmm1
0x1400422fe  call    cs:__imp_SeLockSubjectContext
0x140042305  nop     dword ptr [rax+rax+00h]
0x14004230a  call    cs:__imp_IoGetFileObjectGenericMapping
0x140042311  nop     dword ptr [rax+rax+00h]
0x140042316  lea     rcx, [rbp+47h+var_70]
0x14004231a  mov     r9d, r14d; DesiredAccess
0x14004231d  mov     [rsp+0C0h+AccessStatus], rcx; AccessStatus
0x140042322  mov     r8b, 1; SubjectContextLocked
0x140042325  lea     rcx, [rbp+47h+arg_8]
0x140042329  mov     rdx, r15; SubjectSecurityContext
0x14004232c  mov     [rsp+0C0h+GrantedAccess], rcx; GrantedAccess
0x140042331  mov     rcx, r13; SecurityDescriptor
0x140042334  mov     [rsp+0C0h+AccessMode], r12b; AccessMode
0x140042339  mov     [rsp+0C0h+GenericMapping], rax; GenericMapping
0x14004233e  lea     rax, [rbp+47h+var_68]
0x140042342  mov     [rsp+0C0h+Privileges], rax; Privileges
0x140042347  mov     [rsp+0C0h+PreviouslyGrantedAccess], ebx; PreviouslyGrantedAccess
0x14004234b  call    cs:__imp_SeAccessCheck
0x140042352  nop     dword ptr [rax+rax+00h]
0x140042357  mov     rdx, [rbp+47h+var_68]; Privileges
0x14004235b  mov     sil, al
0x14004235e  mov     bl, al
0x140042360  test    rdx, rdx
0x140042363  jnz     loc_140042418
0x140042369  cmp     [rbp+47h+arg_28], 0
0x14004236d  jnz     loc_14004243C
0x140042373  test    bl, bl
0x140042375  jnz     loc_140042404
0x14004237b  lea     rax, aUl; "Ul"
0x140042382  mov     dword ptr [rbp+47h+ObjectTypeName.Length], 60004h
0x140042389  mov     [rbp+47h+ObjectTypeName.Buffer], rax
0x14004238d  mov     rdx, [rbp+47h+arg_20]
0x140042391  lea     rcx, [rbp+47h+AbsoluteObjectName]
0x140042395  call    UlInitUnicodeStringEx
0x14004239a  test    eax, eax
0x14004239c  js      short loc_1400423D4
0x14004239e  lea     rax, [rdi+0Ah]
0x1400423a2  mov     r9, r13; SecurityDescriptor
0x1400423a5  mov     [rsp+0C0h+GrantedAccess], rax; GenerateOnClose
0x1400423aa  lea     r8, [rbp+47h+AbsoluteObjectName]; AbsoluteObjectName
0x1400423ae  mov     [rsp+0C0h+AccessMode], r12b; AccessMode
0x1400423b3  lea     rcx, [rbp+47h+ObjectTypeName]; ObjectTypeName
0x1400423b7  mov     byte ptr [rsp+0C0h+GenericMapping], sil; AccessGranted
0x1400423bc  xor     edx, edx; Object
0x1400423be  mov     byte ptr [rsp+0C0h+Privileges], 0; ObjectCreated
0x1400423c3  mov     qword ptr [rsp+0C0h+PreviouslyGrantedAccess], rdi; AccessState
0x1400423c8  call    cs:__imp_SeOpenObjectAuditAlarm
0x1400423cf  nop     dword ptr [rax+rax+00h]
0x1400423d4  mov     rcx, r15; SubjectContext
0x1400423d7  call    cs:__imp_SeUnlockSubjectContext
0x1400423de  nop     dword ptr [rax+rax+00h]
0x1400423e3  test    sil, sil
0x1400423e6  jz      short loc_1400423FF
0x1400423e8  xor     eax, eax
0x1400423ea  add     rsp, 88h
0x1400423f1  pop     r15
0x1400423f3  pop     r14
0x1400423f5  pop     r13
0x1400423f7  pop     r12
0x1400423f9  pop     rdi
0x1400423fa  pop     rsi
0x1400423fb  pop     rbx
0x1400423fc  pop     rbp
0x1400423fd  retn
0x1400423ff  mov     eax, [rbp+47h+var_70]
0x140042402  jmp     short loc_1400423EA
0x140042404  mov     ebx, [rbp+47h+arg_8]
0x140042407  or      [rdi+14h], ebx
0x14004240a  bts     ebx, 19h
0x14004240e  not     ebx
0x140042410  and     [rdi+10h], ebx
0x140042413  jmp     loc_14004237B
0x140042418  mov     rcx, rdi; AccessState
0x14004241b  call    cs:__imp_SeAppendPrivileges
0x140042422  nop     dword ptr [rax+rax+00h]
0x140042427  mov     rcx, [rbp+47h+var_68]; Privileges
0x14004242b  call    cs:__imp_SeFreePrivileges
0x140042432  nop     dword ptr [rax+rax+00h]
0x140042437  jmp     loc_140042369
0x14004243c  test    sil, sil
0x14004243f  jnz     short loc_140042404
0x140042441  mov     eax, [rdi+0Ch]
0x140042444  mov     ecx, 106h
0x140042449  and     eax, ecx
0x14004244b  cmp     eax, ecx
0x14004244d  jnz     loc_140175C3B
0x140042453  mov     ebx, 0E0000h
0x140042458  cmp     r14d, ebx
0x14004245b  jnz     loc_140175C3B
0x140042461  test    byte ptr cs:xmmword_1401A2CA0+3, 2
0x140042468  jz      loc_140175C30
0x14004246e  mov     edx, 0Ah
0x140042473  lea     r8, WPP_fe1f27503c643dfeaad4ba070b430e9e_Traceguids
0x14004247a  mov     ecx, 419h
0x14004247f  call    WPP_SF_
0x140042484  nop
0x140042485  jmp     loc_140175C30
0x140175c30  mov     [rbp+47h+arg_8], ebx
0x140175c33  mov     sil, 1
0x140175c36  jmp     loc_140042407
0x140175c3b  test    byte ptr cs:xmmword_1401A2CA0+3, 2
0x140175c42  jz      loc_14004237B
0x140175c48  mov     r9d, [rdi+0Ch]
0x140175c4c  lea     r8, WPP_fe1f27503c643dfeaad4ba070b430e9e_Traceguids
0x140175c53  mov     edx, 0Bh
0x140175c58  mov     ecx, 419h
0x140175c5d  call    WPP_SF_d
0x140175c62  nop
0x140175c63  jmp     loc_14004237B
```
