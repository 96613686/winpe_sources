# NrtAccessCheck

- ea: `0x14003fa78`
- end: `0x14003fb55`
- name: `NrtAccessCheck`
- size: `221`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14003f780`

## import_xrefs

- `ntoskrnl!SeAccessCheck` at `0x14003fb1f`
- `ntoskrnl!SeAccessCheck` at `0x14003fb1f`
- `ntoskrnl!SeCaptureSubjectContextEx` at `0x14003fab6`
- `ntoskrnl!SeCaptureSubjectContextEx` at `0x14003fab6`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14003fb3f`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14003fb3f`
- `ntoskrnl!PsGetCurrentProcess` at `0x14003fa9a`
- `ntoskrnl!PsGetCurrentProcess` at `0x14003fa9a`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14003fb2f`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14003fb2f`
- `ntoskrnl!SeLockSubjectContext` at `0x14003fac6`
- `ntoskrnl!SeLockSubjectContext` at `0x14003fac6`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14003fad2`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14003fad2`

## pseudocode

```c
__int64 NrtAccessCheck()
{
  struct _KPROCESS *CurrentProcess; // rax
  struct _GENERIC_MAPPING *GenericMapping; // rax
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+50h] [rbp-20h] BYREF
  int AccessStatus; // [rsp+80h] [rbp+10h] BYREF
  DWORD GrantedAccess; // [rsp+88h] [rbp+18h] BYREF

  AccessStatus = 0;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  GrantedAccess = 0;
  CurrentProcess = (struct _KPROCESS *)PsGetCurrentProcess();
  SeCaptureSubjectContextEx(KeGetCurrentThread(), CurrentProcess, &SubjectContext);
  SeLockSubjectContext(&SubjectContext);
  GenericMapping = IoGetFileObjectGenericMapping();
  SeAccessCheck(
    NrtSecurityDescriptor,
    &SubjectContext,
    1u,
    0x1F01FFu,
    0,
    0,
    GenericMapping,
    1,
    &GrantedAccess,
    &AccessStatus);
  SeUnlockSubjectContext(&SubjectContext);
  SeReleaseSubjectContext(&SubjectContext);
  return (unsigned int)AccessStatus;
}

```

## disassembly

```asm
0x14003fa78  push    rbp
0x14003fa7a  mov     rbp, rsp
0x14003fa7d  sub     rsp, 70h
0x14003fa81  xorps   xmm0, xmm0
0x14003fa84  mov     [rbp+arg_0], 0
0x14003fa8b  movups  xmmword ptr [rbp+SubjectContext.ClientToken], xmm0
0x14003fa8f  mov     [rbp+arg_8], 0
0x14003fa96  movups  xmmword ptr [rbp+SubjectContext.PrimaryToken], xmm0
0x14003fa9a  call    cs:__imp_PsGetCurrentProcess
0x14003faa1  nop     dword ptr [rax+rax+00h]
0x14003faa6  mov     rcx, gs:188h; Thread
0x14003faaf  lea     r8, [rbp+SubjectContext]; SubjectContext
0x14003fab3  mov     rdx, rax; Process
0x14003fab6  call    cs:__imp_SeCaptureSubjectContextEx
0x14003fabd  nop     dword ptr [rax+rax+00h]
0x14003fac2  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x14003fac6  call    cs:__imp_SeLockSubjectContext
0x14003facd  nop     dword ptr [rax+rax+00h]
0x14003fad2  call    cs:__imp_IoGetFileObjectGenericMapping
0x14003fad9  nop     dword ptr [rax+rax+00h]
0x14003fade  lea     rcx, [rbp+arg_0]
0x14003fae2  mov     r9d, 1F01FFh; DesiredAccess
0x14003fae8  mov     [rsp+70h+AccessStatus], rcx; AccessStatus
0x14003faed  lea     rdx, [rbp+SubjectContext]; SubjectSecurityContext
0x14003faf1  lea     rcx, [rbp+arg_8]
0x14003faf5  mov     r8b, 1; SubjectContextLocked
0x14003faf8  mov     [rsp+70h+GrantedAccess], rcx; GrantedAccess
0x14003fafd  mov     rcx, cs:NrtSecurityDescriptor; SecurityDescriptor
0x14003fb04  mov     [rsp+70h+AccessMode], 1; AccessMode
0x14003fb09  mov     [rsp+70h+GenericMapping], rax; GenericMapping
0x14003fb0e  mov     [rsp+70h+Privileges], 0; Privileges
0x14003fb17  mov     [rsp+70h+PreviouslyGrantedAccess], 0; PreviouslyGrantedAccess
0x14003fb1f  call    cs:__imp_SeAccessCheck
0x14003fb26  nop     dword ptr [rax+rax+00h]
0x14003fb2b  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x14003fb2f  call    cs:__imp_SeUnlockSubjectContext
0x14003fb36  nop     dword ptr [rax+rax+00h]
0x14003fb3b  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x14003fb3f  call    cs:__imp_SeReleaseSubjectContext
0x14003fb46  nop     dword ptr [rax+rax+00h]
0x14003fb4b  mov     eax, [rbp+arg_0]
0x14003fb4e  add     rsp, 70h
0x14003fb52  pop     rbp
0x14003fb53  retn
```
