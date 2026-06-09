# ConnectAccessCheck(_SECURITY_SUBJECT_CONTEXT *)

- ea: `0x14000c2a8`
- end: `0x14000c381`
- name: `?ConnectAccessCheck@@YAJPEAU_SECURITY_SUBJECT_CONTEXT@@@Z`
- size: `217`
- prototype: `__int64 __fastcall(PSECURITY_SUBJECT_CONTEXT SubjectContext)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x14000bb00`

## callees

- `0x1400010a4`
- `0x14000c100`
- `0x14000c2a8`

## import_xrefs

- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14000c2f3`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14000c2f3`
- `ntoskrnl!SeLockSubjectContext` at `0x14000c2e7`
- `ntoskrnl!SeLockSubjectContext` at `0x14000c2e7`
- `ntoskrnl!SeAccessCheck` at `0x14000c33f`
- `ntoskrnl!SeAccessCheck` at `0x14000c33f`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14000c350`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14000c350`

## pseudocode

```c
__int64 __fastcall ConnectAccessCheck(PSECURITY_SUBJECT_CONTEXT SubjectContext)
{
  unsigned int v2; // ebx
  struct _GENERIC_MAPPING *GenericMapping; // rax
  BOOLEAN v4; // bl
  int AccessStatus; // [rsp+68h] [rbp+10h] BYREF
  DWORD GrantedAccess; // [rsp+70h] [rbp+18h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+78h] [rbp+20h] BYREF

  AccessStatus = 0;
  GrantedAccess = 0;
  SecurityDescriptor = 0;
  AccessStatus = BuildConnectSecurityDescriptor((struct _SECURITY_DESCRIPTOR **)&SecurityDescriptor);
  v2 = AccessStatus;
  if ( AccessStatus >= 0 )
  {
    SeLockSubjectContext(SubjectContext);
    GenericMapping = IoGetFileObjectGenericMapping();
    v4 = SeAccessCheck(
           SecurityDescriptor,
           SubjectContext,
           0,
           3u,
           0,
           0,
           GenericMapping,
           1,
           &GrantedAccess,
           &AccessStatus);
    SeUnlockSubjectContext(SubjectContext);
    if ( v4 )
      v2 = 0;
    else
      v2 = -1073741790;
  }
  operator delete(SecurityDescriptor);
  return v2;
}

```

## disassembly

```asm
0x14000c2a8  mov     rax, rsp
0x14000c2ab  mov     [rax+8], rbx
0x14000c2af  push    rdi
0x14000c2b0  sub     rsp, 50h
0x14000c2b4  mov     rdi, rcx
0x14000c2b7  mov     dword ptr [rax+10h], 0
0x14000c2be  lea     rcx, [rax+20h]; struct _SECURITY_DESCRIPTOR **
0x14000c2c2  mov     dword ptr [rax+18h], 0
0x14000c2c9  mov     qword ptr [rax+20h], 0
0x14000c2d1  call    ?BuildConnectSecurityDescriptor@@YAJPEAPEAU_SECURITY_DESCRIPTOR@@@Z; BuildConnectSecurityDescriptor(_SECURITY_DESCRIPTOR * *)
0x14000c2d6  mov     [rsp+58h+arg_8], eax
0x14000c2da  mov     ebx, eax
0x14000c2dc  test    eax, eax
0x14000c2de  js      loc_14000C369
0x14000c2e4  mov     rcx, rdi; SubjectContext
0x14000c2e7  call    cs:__imp_SeLockSubjectContext
0x14000c2ee  nop     dword ptr [rax+rax+00h]
0x14000c2f3  call    cs:__imp_IoGetFileObjectGenericMapping
0x14000c2fa  nop     dword ptr [rax+rax+00h]
0x14000c2ff  lea     rcx, [rsp+58h+arg_8]
0x14000c304  mov     r9d, 3; DesiredAccess
0x14000c30a  mov     [rsp+58h+AccessStatus], rcx; AccessStatus
0x14000c30f  xor     r8d, r8d; SubjectContextLocked
0x14000c312  lea     rcx, [rsp+58h+arg_10]
0x14000c317  mov     rdx, rdi; SubjectSecurityContext
0x14000c31a  mov     [rsp+58h+GrantedAccess], rcx; GrantedAccess
0x14000c31f  mov     rcx, [rsp+58h+SecurityDescriptor]; SecurityDescriptor
0x14000c324  mov     [rsp+58h+AccessMode], 1; AccessMode
0x14000c329  mov     [rsp+58h+GenericMapping], rax; GenericMapping
0x14000c32e  mov     [rsp+58h+Privileges], 0; Privileges
0x14000c337  mov     [rsp+58h+PreviouslyGrantedAccess], 0; PreviouslyGrantedAccess
0x14000c33f  call    cs:__imp_SeAccessCheck
0x14000c346  nop     dword ptr [rax+rax+00h]
0x14000c34b  mov     rcx, rdi; SubjectContext
0x14000c34e  mov     bl, al
0x14000c350  call    cs:__imp_SeUnlockSubjectContext
0x14000c357  nop     dword ptr [rax+rax+00h]
0x14000c35c  test    bl, bl
0x14000c35e  jz      short loc_14000C364
0x14000c360  xor     ebx, ebx
0x14000c362  jmp     short loc_14000C369
0x14000c364  mov     ebx, 0C0000022h
0x14000c369  mov     rcx, [rsp+58h+SecurityDescriptor]; void *
0x14000c36e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000c373  mov     eax, ebx
0x14000c375  mov     rbx, [rsp+58h+arg_0]
0x14000c37a  add     rsp, 50h
0x14000c37e  pop     rdi
0x14000c37f  retn
```
