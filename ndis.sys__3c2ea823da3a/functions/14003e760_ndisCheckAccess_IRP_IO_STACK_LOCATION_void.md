# ndisCheckAccess(_IRP *,_IO_STACK_LOCATION *,void *)

- ea: `0x14003e760`
- end: `0x14003e8a8`
- name: `?ndisCheckAccess@@YAEPEAU_IRP@@PEAU_IO_STACK_LOCATION@@PEAX@Z`
- size: `328`
- prototype: `unsigned __int8(struct _IRP *, struct _IO_STACK_LOCATION *, void *)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14003da10`
- `0x14003e410`
- `0x14003f880`

## callees

- `0x14003e760`

## import_xrefs

- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14003e791`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14003e7d9`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14003e791`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14003e7d9`
- `ntoskrnl!RtlMapGenericMask` at `0x14003e7a8`
- `ntoskrnl!RtlMapGenericMask` at `0x14003e7a8`
- `ntoskrnl!SeLockSubjectContext` at `0x14003e7c0`
- `ntoskrnl!SeLockSubjectContext` at `0x14003e7c0`
- `ntoskrnl!SeAccessCheck` at `0x14003e827`
- `ntoskrnl!SeAccessCheck` at `0x14003e827`
- `ntoskrnl!SeAppendPrivileges` at `0x14003e843`
- `ntoskrnl!SeAppendPrivileges` at `0x14003e843`
- `ntoskrnl!SeFreePrivileges` at `0x14003e854`
- `ntoskrnl!SeFreePrivileges` at `0x14003e854`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14003e883`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14003e883`

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
0x14003e760  mov     rax, rsp
0x14003e763  mov     [rax+8], rbx
0x14003e767  push    rbp
0x14003e768  push    rsi
0x14003e769  push    rdi
0x14003e76a  push    r14
0x14003e76c  push    r15
0x14003e76e  sub     rsp, 60h
0x14003e772  xor     r15d, r15d
0x14003e775  mov     dword ptr [rax+20h], 10000000h
0x14003e77c  mov     [rax-38h], r15d
0x14003e780  mov     r14, r8
0x14003e783  mov     [rax-30h], r15
0x14003e787  mov     rdi, rdx
0x14003e78a  mov     [rax+10h], r15d
0x14003e78e  mov     rbp, rcx
0x14003e791  call    cs:__imp_IoGetFileObjectGenericMapping
0x14003e798  nop     dword ptr [rax+rax+00h]
0x14003e79d  mov     rdx, rax; GenericMapping
0x14003e7a0  lea     rcx, [rsp+88h+AccessMask]; AccessMask
0x14003e7a8  call    cs:__imp_RtlMapGenericMask
0x14003e7af  nop     dword ptr [rax+rax+00h]
0x14003e7b4  mov     rbx, [rdi+8]
0x14003e7b8  mov     rbx, [rbx+8]
0x14003e7bc  lea     rcx, [rbx+20h]; SubjectContext
0x14003e7c0  call    cs:__imp_SeLockSubjectContext
0x14003e7c7  nop     dword ptr [rax+rax+00h]
0x14003e7cc  test    byte ptr [rdi+2], 1
0x14003e7d0  mov     dil, 1
0x14003e7d3  jnz     short loc_14003E7D9
0x14003e7d5  movzx   edi, byte ptr [rbp+40h]
0x14003e7d9  call    cs:__imp_IoGetFileObjectGenericMapping
0x14003e7e0  nop     dword ptr [rax+rax+00h]
0x14003e7e5  mov     r9d, [rsp+88h+AccessMask]; DesiredAccess
0x14003e7ed  lea     rcx, [rsp+88h+var_38]
0x14003e7f2  mov     [rsp+88h+AccessStatus], rcx; AccessStatus
0x14003e7f7  lea     rdx, [rbx+20h]; SubjectSecurityContext
0x14003e7fb  lea     rcx, [rsp+88h+arg_8]
0x14003e803  mov     r8b, 1; SubjectContextLocked
0x14003e806  mov     [rsp+88h+GrantedAccess], rcx; GrantedAccess
0x14003e80b  mov     rcx, r14; SecurityDescriptor
0x14003e80e  mov     [rsp+88h+AccessMode], dil; AccessMode
0x14003e813  mov     [rsp+88h+GenericMapping], rax; GenericMapping
0x14003e818  lea     rax, [rsp+88h+var_30]
0x14003e81d  mov     [rsp+88h+Privileges], rax; Privileges
0x14003e822  mov     [rsp+88h+PreviouslyGrantedAccess], r15d; PreviouslyGrantedAccess
0x14003e827  call    cs:__imp_SeAccessCheck
0x14003e82e  nop     dword ptr [rax+rax+00h]
0x14003e833  mov     rdx, [rsp+88h+var_30]; Privileges
0x14003e838  movzx   edi, al
0x14003e83b  test    rdx, rdx
0x14003e83e  jz      short loc_14003E860
0x14003e840  mov     rcx, rbx; AccessState
0x14003e843  call    cs:__imp_SeAppendPrivileges
0x14003e84a  nop     dword ptr [rax+rax+00h]
0x14003e84f  mov     rcx, [rsp+88h+var_30]; Privileges
0x14003e854  call    cs:__imp_SeFreePrivileges
0x14003e85b  nop     dword ptr [rax+rax+00h]
0x14003e860  test    dil, dil
0x14003e863  jz      short loc_14003E87F
0x14003e865  mov     eax, [rsp+88h+arg_8]
0x14003e86c  or      [rbx+14h], eax
0x14003e86f  mov     eax, [rsp+88h+arg_8]
0x14003e876  bts     eax, 19h
0x14003e87a  not     eax
0x14003e87c  and     [rbx+10h], eax
0x14003e87f  lea     rcx, [rbx+20h]; SubjectContext
0x14003e883  call    cs:__imp_SeUnlockSubjectContext
0x14003e88a  nop     dword ptr [rax+rax+00h]
0x14003e88f  mov     rbx, [rsp+88h+arg_0]
0x14003e897  movzx   eax, dil
0x14003e89b  add     rsp, 60h
0x14003e89f  pop     r15
0x14003e8a1  pop     r14
0x14003e8a3  pop     rdi
0x14003e8a4  pop     rsi
0x14003e8a5  pop     rbp
0x14003e8a6  retn
```
