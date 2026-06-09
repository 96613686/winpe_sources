# ClfsSecurityAccessCheck

- ea: `0x14000c3a4`
- end: `0x14000c65d`
- name: `ClfsSecurityAccessCheck`
- size: `697`
- prototype: `__int64 __usercall@<rax>(PSECURITY_DESCRIPTOR SecurityDescriptor@<rcx>, PSECURITY_SUBJECT_CONTEXT SubjectContext@<rdx>, PACCESS_STATE AccessState, KPROCESSOR_MODE, char)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400337e4`
- `0x1400456a0`

## callees

- `0x14000c3a4`

## import_xrefs

- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14000c41a`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14000c560`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14000c41a`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14000c560`
- `ntoskrnl!SeLockSubjectContext` at `0x14000c401`
- `ntoskrnl!SeLockSubjectContext` at `0x14000c401`
- `ntoskrnl!SeAccessCheck` at `0x14000c468`
- `ntoskrnl!SeAccessCheck` at `0x14000c5ae`
- `ntoskrnl!SeAccessCheck` at `0x14000c468`
- `ntoskrnl!SeAccessCheck` at `0x14000c5ae`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14000c61c`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14001917a`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14000c61c`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14001917a`
- `ntoskrnl!SeFreePrivileges` at `0x14000c5f0`
- `ntoskrnl!SeFreePrivileges` at `0x14000c64f`
- `ntoskrnl!SeFreePrivileges` at `0x140019193`
- `ntoskrnl!SeFreePrivileges` at `0x14000c5f0`
- `ntoskrnl!SeFreePrivileges` at `0x14000c64f`
- `ntoskrnl!SeFreePrivileges` at `0x140019193`
- `ntoskrnl!SeAppendPrivileges` at `0x14000c53c`
- `ntoskrnl!SeAppendPrivileges` at `0x14000c5db`
- `ntoskrnl!SeAppendPrivileges` at `0x14000c53c`
- `ntoskrnl!SeAppendPrivileges` at `0x14000c5db`

## pseudocode

```c
__int64 __fastcall ClfsSecurityAccessCheck(
        PSECURITY_DESCRIPTOR SecurityDescriptor,
        PSECURITY_SUBJECT_CONTEXT SubjectContext,
        int a3,
        ACCESS_MASK a4,
        PACCESS_STATE AccessState,
        KPROCESSOR_MODE AccessMode,
        char a7)
{
  unsigned int appended; // ebx
  ACCESS_MASK v11; // edi
  struct _GENERIC_MAPPING *GenericMapping; // rax
  BOOLEAN v13; // r14
  ACCESS_MASK v14; // eax
  ACCESS_MASK v15; // r12d
  ACCESS_MASK v16; // eax
  struct _GENERIC_MAPPING *FileObjectGenericMapping; // rax
  ACCESS_MASK PreviouslyGrantedAccess; // [rsp+58h] [rbp-40h] BYREF
  int AccessStatus; // [rsp+5Ch] [rbp-3Ch] BYREF
  PPRIVILEGE_SET Privileges[2]; // [rsp+60h] [rbp-38h] BYREF

  Privileges[0] = 0;
  appended = 0;
  AccessStatus = 0;
  PreviouslyGrantedAccess = 0;
  if ( (AccessState->Flags & 4) != 0 )
  {
    v16 = AccessState->PreviouslyGrantedAccess;
    a4 = v16 | AccessState->RemainingDesiredAccess & 0xFEFFFFFF;
    if ( !a7 )
    {
      AccessState->RemainingDesiredAccess &= ~v16;
      AccessState->PreviouslyGrantedAccess = a4;
    }
  }
  v11 = a3 & ~a4;
  SeLockSubjectContext(SubjectContext);
  if ( v11 )
  {
    GenericMapping = IoGetFileObjectGenericMapping();
    v13 = SeAccessCheck(
            SecurityDescriptor,
            SubjectContext,
            1u,
            v11,
            PreviouslyGrantedAccess,
            Privileges,
            GenericMapping,
            AccessMode,
            &PreviouslyGrantedAccess,
            &AccessStatus);
    if ( Privileges[0] && !a7 )
      appended = SeAppendPrivileges(AccessState, Privileges[0]);
    v14 = PreviouslyGrantedAccess;
    v15 = v11 & ~(PreviouslyGrantedAccess | 0x2000000);
    if ( v13 )
    {
      if ( !a7 )
        AccessState->RemainingDesiredAccess &= ~(PreviouslyGrantedAccess | 0x2000000);
    }
    else
    {
      appended = AccessStatus;
    }
    if ( v15 )
    {
      FileObjectGenericMapping = IoGetFileObjectGenericMapping();
      v13 = SeAccessCheck(
              SecurityDescriptor,
              SubjectContext,
              1u,
              v15,
              0,
              Privileges,
              FileObjectGenericMapping,
              AccessMode,
              &PreviouslyGrantedAccess,
              &AccessStatus);
      if ( Privileges[0] && !a7 )
      {
        SeAppendPrivileges(AccessState, Privileges[0]);
        SeFreePrivileges(Privileges[0]);
        Privileges[0] = 0;
      }
      appended = AccessStatus;
      v14 = PreviouslyGrantedAccess;
    }
    if ( v13 && !a7 )
    {
      AccessState->PreviouslyGrantedAccess |= v14;
      AccessState->RemainingDesiredAccess &= ~(v14 | 0x2000000);
    }
  }
  else
  {
    v13 = 1;
    appended = 0;
  }
  if ( v13 )
    appended = 0;
  SeUnlockSubjectContext(SubjectContext);
  if ( Privileges[0] )
    SeFreePrivileges(Privileges[0]);
  return appended;
}

```

## disassembly

```asm
0x14000c3a4  mov     rax, rsp
0x14000c3a7  mov     [rax+8], rbx
0x14000c3ab  mov     [rax+18h], rsi
0x14000c3af  mov     [rax+10h], rdx
0x14000c3b3  push    rdi
0x14000c3b4  push    r12
0x14000c3b6  push    r13
0x14000c3b8  push    r14
0x14000c3ba  push    r15
0x14000c3bc  sub     rsp, 70h
0x14000c3c0  mov     edi, r9d
0x14000c3c3  mov     r15, rdx
0x14000c3c6  mov     r13, rcx
0x14000c3c9  xor     r12d, r12d
0x14000c3cc  mov     [rax-38h], r12
0x14000c3d0  mov     ebx, r12d
0x14000c3d3  mov     [rax-44h], ebx
0x14000c3d6  mov     [rax-3Ch], r12d
0x14000c3da  mov     [rax-40h], r12d
0x14000c3de  mov     [rax-47h], r12b
0x14000c3e2  mov     [rax-48h], r12b
0x14000c3e6  mov     rsi, [rsp+98h+AccessState]
0x14000c3ee  mov     eax, [rsi+0Ch]
0x14000c3f1  test    al, 4
0x14000c3f3  jnz     loc_14000C4F9
0x14000c3f9  not     edi
0x14000c3fb  and     edi, r8d
0x14000c3fe  mov     rcx, r15; SubjectContext
0x14000c401  call    cs:__imp_SeLockSubjectContext
0x14000c408  nop     dword ptr [rax+rax+00h]
0x14000c40d  mov     [rsp+98h+var_47], 1
0x14000c412  test    edi, edi
0x14000c414  jz      loc_14000C4E5
0x14000c41a  call    cs:__imp_IoGetFileObjectGenericMapping
0x14000c421  nop     dword ptr [rax+rax+00h]
0x14000c426  mov     ecx, [rsp+98h+var_40]
0x14000c42a  lea     rdx, [rsp+98h+var_3C]
0x14000c42f  mov     [rsp+98h+AccessStatus], rdx; AccessStatus
0x14000c434  lea     rdx, [rsp+98h+var_40]
0x14000c439  mov     [rsp+98h+GrantedAccess], rdx; GrantedAccess
0x14000c43e  mov     dl, [rsp+98h+arg_28]
0x14000c445  mov     [rsp+98h+AccessMode], dl; AccessMode
0x14000c449  mov     [rsp+98h+GenericMapping], rax; GenericMapping
0x14000c44e  lea     rax, [rsp+98h+var_38]
0x14000c453  mov     [rsp+98h+Privileges], rax; Privileges
0x14000c458  mov     [rsp+98h+PreviouslyGrantedAccess], ecx; PreviouslyGrantedAccess
0x14000c45c  mov     r9d, edi; DesiredAccess
0x14000c45f  mov     r8b, 1; SubjectContextLocked
0x14000c462  mov     rdx, r15; SubjectSecurityContext
0x14000c465  mov     rcx, r13; SecurityDescriptor
0x14000c468  call    cs:__imp_SeAccessCheck
0x14000c46f  nop     dword ptr [rax+rax+00h]
0x14000c474  mov     r14b, al
0x14000c477  mov     [rsp+98h+var_48], al
0x14000c47b  mov     rdx, [rsp+98h+var_38]; Privileges
0x14000c480  test    rdx, rdx
0x14000c483  jnz     loc_14000C52B
0x14000c489  mov     eax, [rsp+98h+var_40]
0x14000c48d  mov     ecx, eax
0x14000c48f  bts     ecx, 19h
0x14000c493  not     ecx
0x14000c495  mov     r12d, ecx
0x14000c498  and     r12d, edi
0x14000c49b  test    r14b, r14b
0x14000c49e  jz      loc_14000C553
0x14000c4a4  cmp     [rsp+98h+arg_30], 0
0x14000c4ac  jnz     short loc_14000C4B1
0x14000c4ae  and     [rsi+10h], ecx
0x14000c4b1  test    r12d, r12d
0x14000c4b4  jnz     loc_14000C560
0x14000c4ba  xor     r12d, r12d
0x14000c4bd  test    r14b, r14b
0x14000c4c0  jz      loc_14000C612
0x14000c4c6  cmp     [rsp+98h+arg_30], r12b
0x14000c4ce  jnz     loc_14000C612
0x14000c4d4  or      [rsi+14h], eax
0x14000c4d7  bts     eax, 19h
0x14000c4db  not     eax
0x14000c4dd  and     [rsi+10h], eax
0x14000c4e0  jmp     loc_14000C612
0x14000c4e5  mov     r14b, 1
0x14000c4e8  mov     [rsp+98h+var_48], r14b
0x14000c4ed  mov     ebx, r12d
0x14000c4f0  mov     [rsp+98h+var_44], ebx
0x14000c4f4  jmp     loc_14000C612
0x14000c4f9  mov     eax, [rsi+14h]
0x14000c4fc  mov     ecx, [rsi+10h]
0x14000c4ff  mov     edi, ecx
0x14000c501  btr     edi, 18h
0x14000c505  or      edi, eax
0x14000c507  mov     [rsp+98h+arg_18], edi
0x14000c50e  cmp     [rsp+98h+arg_30], r12b
0x14000c516  jnz     loc_14000C3F9
0x14000c51c  not     eax
0x14000c51e  and     eax, ecx
0x14000c520  mov     [rsi+10h], eax
0x14000c523  mov     [rsi+14h], edi
0x14000c526  jmp     loc_14000C3F9
0x14000c52b  cmp     [rsp+98h+arg_30], r12b
0x14000c533  jnz     loc_14000C489
0x14000c539  mov     rcx, rsi; AccessState
0x14000c53c  call    cs:__imp_SeAppendPrivileges
0x14000c543  nop     dword ptr [rax+rax+00h]
0x14000c548  mov     ebx, eax
0x14000c54a  mov     [rsp+98h+var_44], eax
0x14000c54e  jmp     loc_14000C489
0x14000c553  mov     ebx, [rsp+98h+var_3C]
0x14000c557  mov     [rsp+98h+var_44], ebx
0x14000c55b  jmp     loc_14000C4B1
0x14000c560  call    cs:__imp_IoGetFileObjectGenericMapping
0x14000c567  nop     dword ptr [rax+rax+00h]
0x14000c56c  lea     rcx, [rsp+98h+var_3C]
0x14000c571  mov     [rsp+98h+AccessStatus], rcx; AccessStatus
0x14000c576  lea     rcx, [rsp+98h+var_40]
0x14000c57b  mov     [rsp+98h+GrantedAccess], rcx; GrantedAccess
0x14000c580  mov     cl, [rsp+98h+arg_28]
0x14000c587  mov     [rsp+98h+AccessMode], cl; AccessMode
0x14000c58b  mov     [rsp+98h+GenericMapping], rax; GenericMapping
0x14000c590  lea     rax, [rsp+98h+var_38]
0x14000c595  mov     [rsp+98h+Privileges], rax; Privileges
0x14000c59a  mov     [rsp+98h+PreviouslyGrantedAccess], 0; PreviouslyGrantedAccess
0x14000c5a2  mov     r9d, r12d; DesiredAccess
0x14000c5a5  mov     r8b, 1; SubjectContextLocked
0x14000c5a8  mov     rdx, r15; SubjectSecurityContext
0x14000c5ab  mov     rcx, r13; SecurityDescriptor
0x14000c5ae  call    cs:__imp_SeAccessCheck
0x14000c5b5  nop     dword ptr [rax+rax+00h]
0x14000c5ba  mov     r14b, al
0x14000c5bd  mov     [rsp+98h+var_48], al
0x14000c5c1  mov     rdx, [rsp+98h+var_38]; Privileges
0x14000c5c6  xor     r12d, r12d
0x14000c5c9  test    rdx, rdx
0x14000c5cc  jz      short loc_14000C601
0x14000c5ce  cmp     [rsp+98h+arg_30], r12b
0x14000c5d6  jnz     short loc_14000C601
0x14000c5d8  mov     rcx, rsi; AccessState
0x14000c5db  call    cs:__imp_SeAppendPrivileges
0x14000c5e2  nop     dword ptr [rax+rax+00h]
0x14000c5e7  mov     [rsp+98h+var_44], eax
0x14000c5eb  mov     rcx, [rsp+98h+var_38]; Privileges
0x14000c5f0  call    cs:__imp_SeFreePrivileges
0x14000c5f7  nop     dword ptr [rax+rax+00h]
0x14000c5fc  mov     [rsp+98h+var_38], r12
0x14000c601  mov     ebx, [rsp+98h+var_3C]
0x14000c605  mov     [rsp+98h+var_44], ebx
0x14000c609  mov     eax, [rsp+98h+var_40]
0x14000c60d  jmp     loc_14000C4BD
0x14000c612  test    r14b, r14b
0x14000c615  cmovnz  ebx, r12d
0x14000c619  mov     rcx, r15; SubjectContext
0x14000c61c  call    cs:__imp_SeUnlockSubjectContext
0x14000c623  nop     dword ptr [rax+rax+00h]
0x14000c628  mov     rcx, [rsp+98h+var_38]; Privileges
0x14000c62d  test    rcx, rcx
0x14000c630  jnz     short loc_14000C64F
0x14000c632  mov     eax, ebx
0x14000c634  lea     r11, [rsp+98h+var_28]
0x14000c639  mov     rbx, [r11+30h]
0x14000c63d  mov     rsi, [r11+40h]
0x14000c641  mov     rsp, r11
0x14000c644  pop     r15
0x14000c646  pop     r14
0x14000c648  pop     r13
0x14000c64a  pop     r12
0x14000c64c  pop     rdi
0x14000c64d  retn
0x14000c64f  call    cs:__imp_SeFreePrivileges
0x14000c656  nop     dword ptr [rax+rax+00h]
0x14000c65b  jmp     short loc_14000C632
0x140019157  push    rbp
0x140019159  sub     rsp, 50h
0x14001915d  mov     rbp, rdx
0x140019160  mov     eax, [rbp+54h]
0x140019163  xor     ecx, ecx
0x140019165  cmp     [rbp+50h], cl
0x140019168  cmovnz  eax, ecx
0x14001916b  mov     [rbp+54h], eax
0x14001916e  cmp     [rbp+51h], cl
0x140019171  jz      short loc_14001918A
0x140019173  mov     rcx, [rbp+0A8h]; SubjectContext
0x14001917a  call    cs:__imp_SeUnlockSubjectContext
0x140019181  nop     dword ptr [rax+rax+00h]
0x140019186  mov     byte ptr [rbp+51h], 1
0x14001918a  mov     rcx, [rbp+60h]; Privileges
0x14001918e  test    rcx, rcx
0x140019191  jz      short loc_1400191A0
0x140019193  call    cs:__imp_SeFreePrivileges
0x14001919a  nop     dword ptr [rax+rax+00h]
0x14001919f  nop
0x1400191a0  add     rsp, 50h
0x1400191a4  pop     rbp
0x1400191a5  retn
```
