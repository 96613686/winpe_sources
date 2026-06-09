# EfpsPerformAccessCheck

- ea: `0x14004ed40`
- end: `0x14004ee30`
- name: `EfpsPerformAccessCheck`
- size: `240`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR SecurityDescriptor, ACCESS_MASK DesiredAccess)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14004eff0`
- `0x1400518a8`

## callees

- `0x140008008`
- `0x14004ed40`

## import_xrefs

- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14004ed8e`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14004ed8e`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14004ee0f`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14004ee0f`
- `ntoskrnl!SeAccessCheck` at `0x14004eddd`
- `ntoskrnl!SeAccessCheck` at `0x14004eddd`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14004ed82`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14004ed82`

## pseudocode

```c
char __fastcall EfpsPerformAccessCheck(PSECURITY_DESCRIPTOR SecurityDescriptor, ACCESS_MASK DesiredAccess, char a3)
{
  BOOLEAN HasPrivilege; // bl
  struct _GENERIC_MAPPING *GenericMapping; // rax
  PACCESS_TOKEN ClientToken; // rcx
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+50h] [rbp-28h] BYREF
  int AccessStatus; // [rsp+80h] [rbp+8h] BYREF
  DWORD GrantedAccess; // [rsp+98h] [rbp+20h] BYREF

  GrantedAccess = 0;
  AccessStatus = 0;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  if ( !SecurityDescriptor )
    return 1;
  SeCaptureSubjectContext(&SubjectContext);
  GenericMapping = IoGetFileObjectGenericMapping();
  HasPrivilege = SeAccessCheck(
                   SecurityDescriptor,
                   &SubjectContext,
                   0,
                   DesiredAccess,
                   0,
                   0,
                   GenericMapping,
                   1,
                   &GrantedAccess,
                   &AccessStatus);
  if ( !HasPrivilege && a3 == 1 )
  {
    ClientToken = SubjectContext.ClientToken;
    if ( !SubjectContext.ClientToken )
      ClientToken = SubjectContext.PrimaryToken;
    HasPrivilege = EfspHasPrivilege(ClientToken);
  }
  SeReleaseSubjectContext(&SubjectContext);
  return HasPrivilege;
}

```

## disassembly

```asm
0x14004ed40  mov     rax, rsp
0x14004ed43  mov     [rax+10h], rbx
0x14004ed47  mov     [rax+18h], rsi
0x14004ed4b  push    rdi
0x14004ed4c  sub     rsp, 70h
0x14004ed50  mov     dword ptr [rax+20h], 0
0x14004ed57  xorps   xmm0, xmm0
0x14004ed5a  mov     dword ptr [rax+8], 0
0x14004ed61  mov     dil, r8b
0x14004ed64  mov     esi, edx
0x14004ed66  mov     rbx, rcx
0x14004ed69  movups  xmmword ptr [rax-28h], xmm0
0x14004ed6d  movups  xmmword ptr [rax-18h], xmm0
0x14004ed71  test    rcx, rcx
0x14004ed74  jnz     short loc_14004ED7D
0x14004ed76  mov     bl, 1
0x14004ed78  jmp     loc_14004EE1B
0x14004ed7d  lea     rcx, [rsp+78h+SubjectContext]; SubjectContext
0x14004ed82  call    cs:__imp_SeCaptureSubjectContext
0x14004ed89  nop     dword ptr [rax+rax+00h]
0x14004ed8e  call    cs:__imp_IoGetFileObjectGenericMapping
0x14004ed95  nop     dword ptr [rax+rax+00h]
0x14004ed9a  lea     rcx, [rsp+78h+arg_0]
0x14004eda2  mov     r9d, esi; DesiredAccess
0x14004eda5  mov     [rsp+78h+AccessStatus], rcx; AccessStatus
0x14004edaa  lea     rdx, [rsp+78h+SubjectContext]; SubjectSecurityContext
0x14004edaf  lea     rcx, [rsp+78h+arg_18]
0x14004edb7  xor     r8d, r8d; SubjectContextLocked
0x14004edba  mov     [rsp+78h+GrantedAccess], rcx; GrantedAccess
0x14004edbf  mov     rcx, rbx; SecurityDescriptor
0x14004edc2  mov     [rsp+78h+AccessMode], 1; AccessMode
0x14004edc7  mov     [rsp+78h+GenericMapping], rax; GenericMapping
0x14004edcc  mov     [rsp+78h+Privileges], 0; Privileges
0x14004edd5  mov     [rsp+78h+PreviouslyGrantedAccess], 0; PreviouslyGrantedAccess
0x14004eddd  call    cs:__imp_SeAccessCheck
0x14004ede4  nop     dword ptr [rax+rax+00h]
0x14004ede9  mov     bl, al
0x14004edeb  test    al, al
0x14004eded  jnz     short loc_14004EE0A
0x14004edef  cmp     dil, 1
0x14004edf3  jnz     short loc_14004EE0A
0x14004edf5  mov     rcx, [rsp+78h+SubjectContext.ClientToken]
0x14004edfa  test    rcx, rcx
0x14004edfd  cmovz   rcx, [rsp+78h+SubjectContext.PrimaryToken]
0x14004ee03  call    EfspHasPrivilege
0x14004ee08  mov     bl, al
0x14004ee0a  lea     rcx, [rsp+78h+SubjectContext]; SubjectContext
0x14004ee0f  call    cs:__imp_SeReleaseSubjectContext
0x14004ee16  nop     dword ptr [rax+rax+00h]
0x14004ee1b  lea     r11, [rsp+78h+var_8]
0x14004ee20  mov     al, bl
0x14004ee22  mov     rbx, [r11+18h]
0x14004ee26  mov     rsi, [r11+20h]
0x14004ee2a  mov     rsp, r11
0x14004ee2d  pop     rdi
0x14004ee2e  retn
```
