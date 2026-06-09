# DrIsIoRequestFromSID(void *,_IRP *,_IO_STACK_LOCATION *)

- ea: `0x140016de0`
- end: `0x140016f1f`
- name: `?DrIsIoRequestFromSID@@YAEPEAXPEAU_IRP@@PEAU_IO_STACK_LOCATION@@@Z`
- size: `319`
- prototype: `BOOLEAN __fastcall(void *, struct _IRP *, struct _IO_STACK_LOCATION *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14001af78`

## callees

- `0x140016de0`

## import_xrefs

- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140016e22`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140016e68`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140016e22`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140016e68`
- `ntoskrnl!RtlMapGenericMask` at `0x140016e35`
- `ntoskrnl!RtlMapGenericMask` at `0x140016e35`
- `ntoskrnl!SeLockSubjectContext` at `0x140016e50`
- `ntoskrnl!SeLockSubjectContext` at `0x140016e50`
- `ntoskrnl!SeAccessCheck` at `0x140016ead`
- `ntoskrnl!SeAccessCheck` at `0x140016ead`
- `ntoskrnl!SeAppendPrivileges` at `0x140016ec7`
- `ntoskrnl!SeAppendPrivileges` at `0x140016ec7`
- `ntoskrnl!SeFreePrivileges` at `0x140016ed7`
- `ntoskrnl!SeFreePrivileges` at `0x140016ed7`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140016efc`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140016efc`

## pseudocode

```c
BOOLEAN __fastcall DrIsIoRequestFromSID(void *a1, struct _IRP *a2, struct _IO_STACK_LOCATION *a3)
{
  void *v3; // r15
  struct _GENERIC_MAPPING *FileObjectGenericMapping; // rax
  struct _ACCESS_STATE *v7; // rdi
  bool v8; // zf
  KPROCESSOR_MODE AccessMode; // bl
  struct _GENERIC_MAPPING *GenericMapping; // rax
  BOOLEAN v11; // bl
  PPRIVILEGE_SET Privileges; // [rsp+50h] [rbp-10h] BYREF
  DWORD GrantedAccess; // [rsp+90h] [rbp+30h] BYREF
  int v15; // [rsp+94h] [rbp+34h]
  DWORD AccessMask; // [rsp+A0h] [rbp+40h] BYREF
  int AccessStatus; // [rsp+A8h] [rbp+48h] BYREF

  v15 = HIDWORD(a1);
  v3 = *(void **)&WPP_MAIN_CB.DeviceQueue.Type;
  Privileges = 0;
  GrantedAccess = 0;
  AccessMask = 0x10000000;
  AccessStatus = 0;
  FileObjectGenericMapping = IoGetFileObjectGenericMapping();
  RtlMapGenericMask(&AccessMask, FileObjectGenericMapping);
  v7 = *(struct _ACCESS_STATE **)(a3->Parameters.WMI.ProviderId + 8);
  SeLockSubjectContext(&v7->SubjectSecurityContext);
  v8 = (a3->Flags & 1) == 0;
  AccessMode = 1;
  if ( v8 )
    AccessMode = a2->RequestorMode;
  GenericMapping = IoGetFileObjectGenericMapping();
  v11 = SeAccessCheck(
          v3,
          &v7->SubjectSecurityContext,
          1u,
          AccessMask,
          0,
          &Privileges,
          GenericMapping,
          AccessMode,
          &GrantedAccess,
          &AccessStatus);
  if ( Privileges )
  {
    SeAppendPrivileges(v7, Privileges);
    SeFreePrivileges(Privileges);
  }
  if ( v11 )
  {
    v7->PreviouslyGrantedAccess |= GrantedAccess;
    v7->RemainingDesiredAccess &= ~(GrantedAccess | 0x2000000);
  }
  SeUnlockSubjectContext(&v7->SubjectSecurityContext);
  return v11;
}

```

## disassembly

```asm
0x140016de0  mov     [rsp-28h+arg_8], rbx
0x140016de5  mov     qword ptr [rsp-28h+arg_0], rcx
0x140016dea  push    rbp
0x140016deb  push    rsi
0x140016dec  push    rdi
0x140016ded  push    r14
0x140016def  push    r15
0x140016df1  mov     rbp, rsp
0x140016df4  sub     rsp, 60h
0x140016df8  mov     r15, qword ptr cs:WPP_MAIN_CB.DeviceQueue.Type
0x140016dff  mov     rbx, r8
0x140016e02  mov     r14, rdx
0x140016e05  mov     [rbp+var_10], 0
0x140016e0d  mov     [rbp+arg_0], 0
0x140016e14  mov     [rbp+AccessMask], 10000000h
0x140016e1b  mov     [rbp+arg_18], 0
0x140016e22  call    cs:__imp_IoGetFileObjectGenericMapping
0x140016e29  nop     dword ptr [rax+rax+00h]
0x140016e2e  mov     rdx, rax; GenericMapping
0x140016e31  lea     rcx, [rbp+AccessMask]; AccessMask
0x140016e35  call    cs:__imp_RtlMapGenericMask
0x140016e3c  nop     dword ptr [rax+rax+00h]
0x140016e41  mov     rax, [rbx+8]
0x140016e45  mov     rdi, [rax+8]
0x140016e49  lea     rsi, [rdi+20h]
0x140016e4d  mov     rcx, rsi; SubjectContext
0x140016e50  call    cs:__imp_SeLockSubjectContext
0x140016e57  nop     dword ptr [rax+rax+00h]
0x140016e5c  test    byte ptr [rbx+2], 1
0x140016e60  mov     bl, 1
0x140016e62  jnz     short loc_140016E68
0x140016e64  mov     bl, [r14+40h]
0x140016e68  call    cs:__imp_IoGetFileObjectGenericMapping
0x140016e6f  nop     dword ptr [rax+rax+00h]
0x140016e74  mov     r9d, [rbp+AccessMask]; DesiredAccess
0x140016e78  lea     rcx, [rbp+arg_18]
0x140016e7c  mov     [rsp+60h+AccessStatus], rcx; AccessStatus
0x140016e81  mov     r8b, 1; SubjectContextLocked
0x140016e84  lea     rcx, [rbp+arg_0]
0x140016e88  mov     rdx, rsi; SubjectSecurityContext
0x140016e8b  mov     [rsp+60h+GrantedAccess], rcx; GrantedAccess
0x140016e90  mov     rcx, r15; SecurityDescriptor
0x140016e93  mov     [rsp+60h+AccessMode], bl; AccessMode
0x140016e97  mov     [rsp+60h+GenericMapping], rax; GenericMapping
0x140016e9c  lea     rax, [rbp+var_10]
0x140016ea0  mov     [rsp+60h+Privileges], rax; Privileges
0x140016ea5  mov     [rsp+60h+PreviouslyGrantedAccess], 0; PreviouslyGrantedAccess
0x140016ead  call    cs:__imp_SeAccessCheck
0x140016eb4  nop     dword ptr [rax+rax+00h]
0x140016eb9  mov     rdx, [rbp+var_10]; Privileges
0x140016ebd  mov     bl, al
0x140016ebf  test    rdx, rdx
0x140016ec2  jz      short loc_140016EE3
0x140016ec4  mov     rcx, rdi; AccessState
0x140016ec7  call    cs:__imp_SeAppendPrivileges
0x140016ece  nop     dword ptr [rax+rax+00h]
0x140016ed3  mov     rcx, [rbp+var_10]; Privileges
0x140016ed7  call    cs:__imp_SeFreePrivileges
0x140016ede  nop     dword ptr [rax+rax+00h]
0x140016ee3  test    bl, bl
0x140016ee5  jz      short loc_140016EF9
0x140016ee7  mov     eax, [rbp+arg_0]
0x140016eea  or      [rdi+14h], eax
0x140016eed  mov     eax, [rbp+arg_0]
0x140016ef0  bts     eax, 19h
0x140016ef4  not     eax
0x140016ef6  and     [rdi+10h], eax
0x140016ef9  mov     rcx, rsi; SubjectContext
0x140016efc  call    cs:__imp_SeUnlockSubjectContext
0x140016f03  nop     dword ptr [rax+rax+00h]
0x140016f08  mov     al, bl
0x140016f0a  mov     rbx, [rsp+60h+arg_8]
0x140016f12  add     rsp, 60h
0x140016f16  pop     r15
0x140016f18  pop     r14
0x140016f1a  pop     rdi
0x140016f1b  pop     rsi
0x140016f1c  pop     rbp
0x140016f1d  retn
```
