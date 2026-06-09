# RefsCanAdministerVolume

- ea: `0x1c017a648`
- end: `0x1c017a75c`
- name: `RefsCanAdministerVolume`
- size: `276`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1c0179bd4`

## callees

- `0x1c015d78c`
- `0x1c017a648`

## import_xrefs

- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1c017a6cd`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1c017a6cd`
- `ntoskrnl!SeLockSubjectContext` at `0x1c017a6b0`
- `ntoskrnl!SeLockSubjectContext` at `0x1c017a6b0`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1c017a729`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1c0180bf4`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1c017a729`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1c0180bf4`
- `ntoskrnl!SeFreePrivileges` at `0x1c018b0c7`
- `ntoskrnl!SeFreePrivileges` at `0x1c018b0c7`
- `ntoskrnl!SeAccessCheck` at `0x1c017a718`
- `ntoskrnl!SeAccessCheck` at `0x1c017a718`

## pseudocode

```c
BOOLEAN __fastcall RefsCanAdministerVolume(__int64 a1, __int64 a2, __int64 a3, void *a4, ACCESS_MASK *a5)
{
  __int64 v8; // rdx
  struct _PRIVILEGE_SET *v9; // rdi
  ACCESS_MASK Control; // esi
  KPROCESSOR_MODE AccessMode; // r15
  struct _SECURITY_SUBJECT_CONTEXT *p_HighPart; // rdi
  struct _GENERIC_MAPPING *GenericMapping; // rax
  BOOLEAN v14; // bl
  PPRIVILEGE_SET Privileges[2]; // [rsp+50h] [rbp-28h] BYREF
  __int64 AccessStatus; // [rsp+80h] [rbp+8h] BYREF
  DWORD GrantedAccess; // [rsp+88h] [rbp+10h] BYREF

  AccessStatus = a1;
  v8 = *(_QWORD *)(a2 + 184);
  GrantedAccess = 0;
  LODWORD(AccessStatus) = 0;
  Privileges[0] = 0;
  v9 = *(struct _PRIVILEGE_SET **)(*(_QWORD *)(v8 + 8) + 8LL);
  Privileges[1] = v9;
  Control = v9[1].Control;
  if ( a5 )
    Control = *a5;
  AccessMode = RefsEffectiveMode(a2, v8, a3);
  p_HighPart = (struct _SECURITY_SUBJECT_CONTEXT *)&v9[1].Privilege[0].Luid.HighPart;
  SeLockSubjectContext(p_HighPart);
  if ( !a4 )
    a4 = (void *)(*(_QWORD *)(a3 + 184) + 20LL);
  GenericMapping = IoGetFileObjectGenericMapping();
  v14 = SeAccessCheck(
          a4,
          p_HighPart,
          1u,
          Control,
          0,
          Privileges,
          GenericMapping,
          AccessMode,
          &GrantedAccess,
          (PNTSTATUS)&AccessStatus);
  SeUnlockSubjectContext(p_HighPart);
  if ( Privileges[0] )
    SeFreePrivileges(Privileges[0]);
  return v14;
}

```

## disassembly

```asm
0x1c017a648  mov     rax, rsp
0x1c017a64b  mov     [rax+18h], rbx
0x1c017a64f  mov     [rax+20h], rsi
0x1c017a653  mov     [rax+8], rcx
0x1c017a657  push    rdi
0x1c017a658  push    r14
0x1c017a65a  push    r15
0x1c017a65c  sub     rsp, 60h
0x1c017a660  mov     rbx, r9
0x1c017a663  mov     r14, r8
0x1c017a666  mov     r9, rdx
0x1c017a669  mov     rdx, [rdx+0B8h]
0x1c017a670  and     dword ptr [rax+10h], 0
0x1c017a674  and     dword ptr [rax+8], 0
0x1c017a678  and     qword ptr [rax-28h], 0
0x1c017a67d  mov     rax, [rdx+8]
0x1c017a681  mov     rdi, [rax+8]
0x1c017a685  mov     [rsp+78h+var_20], rdi
0x1c017a68a  mov     esi, [rdi+18h]
0x1c017a68d  mov     rax, [rsp+78h+arg_20]
0x1c017a695  test    rax, rax
0x1c017a698  jnz     loc_1C018B0C0
0x1c017a69e  mov     rcx, r9
0x1c017a6a1  call    RefsEffectiveMode
0x1c017a6a6  mov     r15b, al
0x1c017a6a9  add     rdi, 20h ; ' '
0x1c017a6ad  mov     rcx, rdi; SubjectContext
0x1c017a6b0  call    cs:__imp_SeLockSubjectContext
0x1c017a6b7  nop     dword ptr [rax+rax+00h]
0x1c017a6bc  nop
0x1c017a6bd  test    rbx, rbx
0x1c017a6c0  jnz     short loc_1C017A6CD
0x1c017a6c2  mov     rbx, [r14+0B8h]
0x1c017a6c9  add     rbx, 14h
0x1c017a6cd  call    cs:__imp_IoGetFileObjectGenericMapping
0x1c017a6d4  nop     dword ptr [rax+rax+00h]
0x1c017a6d9  lea     rcx, [rsp+78h+arg_0]
0x1c017a6e1  mov     [rsp+78h+AccessStatus], rcx; AccessStatus
0x1c017a6e6  lea     rcx, [rsp+78h+arg_8]
0x1c017a6ee  mov     [rsp+78h+GrantedAccess], rcx; GrantedAccess
0x1c017a6f3  mov     [rsp+78h+AccessMode], r15b; AccessMode
0x1c017a6f8  mov     [rsp+78h+GenericMapping], rax; GenericMapping
0x1c017a6fd  lea     rax, [rsp+78h+var_28]
0x1c017a702  mov     [rsp+78h+Privileges], rax; Privileges
0x1c017a707  and     [rsp+78h+var_58], 0
0x1c017a70c  mov     r9d, esi; DesiredAccess
0x1c017a70f  mov     r8b, 1; SubjectContextLocked
0x1c017a712  mov     rdx, rdi; SubjectSecurityContext
0x1c017a715  mov     rcx, rbx; SecurityDescriptor
0x1c017a718  call    cs:__imp_SeAccessCheck
0x1c017a71f  nop     dword ptr [rax+rax+00h]
0x1c017a724  mov     bl, al
0x1c017a726  mov     rcx, rdi; SubjectContext
0x1c017a729  call    cs:__imp_SeUnlockSubjectContext
0x1c017a730  nop     dword ptr [rax+rax+00h]
0x1c017a735  mov     rcx, [rsp+78h+var_28]; Privileges
0x1c017a73a  test    rcx, rcx
0x1c017a73d  jnz     loc_1C018B0C7
0x1c017a743  mov     al, bl
0x1c017a745  lea     r11, [rsp+78h+var_18]
0x1c017a74a  mov     rbx, [r11+30h]
0x1c017a74e  mov     rsi, [r11+38h]
0x1c017a752  mov     rsp, r11
0x1c017a755  pop     r15
0x1c017a757  pop     r14
0x1c017a759  pop     rdi
0x1c017a75a  retn
0x1c0180be3  push    rbp
0x1c0180be5  sub     rsp, 50h
0x1c0180be9  mov     rbp, rdx
0x1c0180bec  mov     rcx, [rbp+58h]
0x1c0180bf0  add     rcx, 20h ; ' '; SubjectContext
0x1c0180bf4  call    cs:__imp_SeUnlockSubjectContext
0x1c0180bfb  nop     dword ptr [rax+rax+00h]
0x1c0180c00  nop
0x1c0180c01  add     rsp, 50h
0x1c0180c05  pop     rbp
0x1c0180c06  retn
0x1c018b0c0  mov     esi, [rax]
0x1c018b0c2  jmp     loc_1C017A69E
0x1c018b0c7  call    cs:__imp_SeFreePrivileges
0x1c018b0ce  nop     dword ptr [rax+rax+00h]
0x1c018b0d3  nop
0x1c018b0d4  jmp     loc_1C017A743
```
