# ndisCheckAccess(_IRP *,_IO_STACK_LOCATION *,void *)

- ea: `0x140040f10`
- end: `0x140041058`
- name: `?ndisCheckAccess@@YAEPEAU_IRP@@PEAU_IO_STACK_LOCATION@@PEAX@Z`
- size: `328`
- prototype: `__int64 __fastcall(struct _IRP *, struct _IO_STACK_LOCATION *, void *)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400401c0`
- `0x140040bc0`
- `0x1400421a0`

## callees

- `0x140040f10`

## import_xrefs

- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140040f41`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140040f89`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140040f41`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140040f89`
- `ntoskrnl!RtlMapGenericMask` at `0x140040f58`
- `ntoskrnl!RtlMapGenericMask` at `0x140040f58`
- `ntoskrnl!SeLockSubjectContext` at `0x140040f70`
- `ntoskrnl!SeLockSubjectContext` at `0x140040f70`
- `ntoskrnl!SeAccessCheck` at `0x140040fd7`
- `ntoskrnl!SeAccessCheck` at `0x140040fd7`
- `ntoskrnl!SeAppendPrivileges` at `0x140040ff3`
- `ntoskrnl!SeAppendPrivileges` at `0x140040ff3`
- `ntoskrnl!SeFreePrivileges` at `0x140041004`
- `ntoskrnl!SeFreePrivileges` at `0x140041004`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140041033`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140041033`

## pseudocode

```c
__int64 __fastcall ndisCheckAccess(struct _IRP *a1, struct _IO_STACK_LOCATION *a2, void *a3)
{
  struct _GENERIC_MAPPING *FileObjectGenericMapping; // rax
  struct _ACCESS_STATE *v7; // rbx
  bool v8; // zf
  KPROCESSOR_MODE AccessMode; // di
  struct _GENERIC_MAPPING *GenericMapping; // rax
  BOOLEAN v11; // di
  int AccessStatus; // [rsp+50h] [rbp-38h] BYREF
  PPRIVILEGE_SET Privileges; // [rsp+58h] [rbp-30h] BYREF
  DWORD GrantedAccess; // [rsp+98h] [rbp+10h] BYREF
  DWORD AccessMask; // [rsp+A8h] [rbp+20h] BYREF

  AccessMask = 0x10000000;
  AccessStatus = 0;
  Privileges = 0;
  GrantedAccess = 0;
  FileObjectGenericMapping = IoGetFileObjectGenericMapping();
  RtlMapGenericMask(&AccessMask, FileObjectGenericMapping);
  v7 = *(struct _ACCESS_STATE **)(a2->Parameters.WMI.ProviderId + 8);
  SeLockSubjectContext(&v7->SubjectSecurityContext);
  v8 = (a2->Flags & 1) == 0;
  AccessMode = 1;
  if ( v8 )
    AccessMode = a1->RequestorMode;
  GenericMapping = IoGetFileObjectGenericMapping();
  v11 = SeAccessCheck(
          a3,
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
0x140040f10  mov     rax, rsp
0x140040f13  mov     [rax+8], rbx
0x140040f17  push    rbp
0x140040f18  push    rsi
0x140040f19  push    rdi
0x140040f1a  push    r14
0x140040f1c  push    r15
0x140040f1e  sub     rsp, 60h
0x140040f22  xor     r15d, r15d
0x140040f25  mov     dword ptr [rax+20h], 10000000h
0x140040f2c  mov     [rax-38h], r15d
0x140040f30  mov     r14, r8
0x140040f33  mov     [rax-30h], r15
0x140040f37  mov     rdi, rdx
0x140040f3a  mov     [rax+10h], r15d
0x140040f3e  mov     rbp, rcx
0x140040f41  call    cs:__imp_IoGetFileObjectGenericMapping
0x140040f48  nop     dword ptr [rax+rax+00h]
0x140040f4d  mov     rdx, rax; GenericMapping
0x140040f50  lea     rcx, [rsp+88h+AccessMask]; AccessMask
0x140040f58  call    cs:__imp_RtlMapGenericMask
0x140040f5f  nop     dword ptr [rax+rax+00h]
0x140040f64  mov     rbx, [rdi+8]
0x140040f68  mov     rbx, [rbx+8]
0x140040f6c  lea     rcx, [rbx+20h]; SubjectContext
0x140040f70  call    cs:__imp_SeLockSubjectContext
0x140040f77  nop     dword ptr [rax+rax+00h]
0x140040f7c  test    byte ptr [rdi+2], 1
0x140040f80  mov     dil, 1
0x140040f83  jnz     short loc_140040F89
0x140040f85  movzx   edi, byte ptr [rbp+40h]
0x140040f89  call    cs:__imp_IoGetFileObjectGenericMapping
0x140040f90  nop     dword ptr [rax+rax+00h]
0x140040f95  mov     r9d, [rsp+88h+AccessMask]; DesiredAccess
0x140040f9d  lea     rcx, [rsp+88h+var_38]
0x140040fa2  mov     [rsp+88h+AccessStatus], rcx; AccessStatus
0x140040fa7  lea     rdx, [rbx+20h]; SubjectSecurityContext
0x140040fab  lea     rcx, [rsp+88h+arg_8]
0x140040fb3  mov     r8b, 1; SubjectContextLocked
0x140040fb6  mov     [rsp+88h+GrantedAccess], rcx; GrantedAccess
0x140040fbb  mov     rcx, r14; SecurityDescriptor
0x140040fbe  mov     [rsp+88h+AccessMode], dil; AccessMode
0x140040fc3  mov     [rsp+88h+GenericMapping], rax; GenericMapping
0x140040fc8  lea     rax, [rsp+88h+var_30]
0x140040fcd  mov     [rsp+88h+Privileges], rax; Privileges
0x140040fd2  mov     [rsp+88h+PreviouslyGrantedAccess], r15d; PreviouslyGrantedAccess
0x140040fd7  call    cs:__imp_SeAccessCheck
0x140040fde  nop     dword ptr [rax+rax+00h]
0x140040fe3  mov     rdx, [rsp+88h+var_30]; Privileges
0x140040fe8  movzx   edi, al
0x140040feb  test    rdx, rdx
0x140040fee  jz      short loc_140041010
0x140040ff0  mov     rcx, rbx; AccessState
0x140040ff3  call    cs:__imp_SeAppendPrivileges
0x140040ffa  nop     dword ptr [rax+rax+00h]
0x140040fff  mov     rcx, [rsp+88h+var_30]; Privileges
0x140041004  call    cs:__imp_SeFreePrivileges
0x14004100b  nop     dword ptr [rax+rax+00h]
0x140041010  test    dil, dil
0x140041013  jz      short loc_14004102F
0x140041015  mov     eax, [rsp+88h+arg_8]
0x14004101c  or      [rbx+14h], eax
0x14004101f  mov     eax, [rsp+88h+arg_8]
0x140041026  bts     eax, 19h
0x14004102a  not     eax
0x14004102c  and     [rbx+10h], eax
0x14004102f  lea     rcx, [rbx+20h]; SubjectContext
0x140041033  call    cs:__imp_SeUnlockSubjectContext
0x14004103a  nop     dword ptr [rax+rax+00h]
0x14004103f  mov     rbx, [rsp+88h+arg_0]
0x140041047  movzx   eax, dil
0x14004104b  add     rsp, 60h
0x14004104f  pop     r15
0x140041051  pop     r14
0x140041053  pop     rdi
0x140041054  pop     rsi
0x140041055  pop     rbp
0x140041056  retn
```
