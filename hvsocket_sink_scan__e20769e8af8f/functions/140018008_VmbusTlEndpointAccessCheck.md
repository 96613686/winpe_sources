# VmbusTlEndpointAccessCheck

- ea: `0x140018008`
- end: `0x14001812a`
- name: `VmbusTlEndpointAccessCheck`
- size: `290`
- prototype: `__int64 __fastcall(PEPROCESS Process, PSECURITY_DESCRIPTOR SecurityDescriptor)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140004f2c`
- `0x14000695c`
- `0x140006be0`
- `0x14001e5ac`

## callees

- `0x14000a2c8`
- `0x140018008`

## import_xrefs

- `ntoskrnl!SeLockSubjectContext` at `0x14001804b`
- `ntoskrnl!SeLockSubjectContext` at `0x14001804b`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1400180b9`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1400180b9`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1400180c9`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1400180c9`
- `ntoskrnl!PsGetProcessId` at `0x1400180f0`
- `ntoskrnl!PsGetProcessId` at `0x1400180f0`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14001805e`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14001805e`
- `ntoskrnl!SeCaptureSubjectContextEx` at `0x14001803b`
- `ntoskrnl!SeCaptureSubjectContextEx` at `0x14001803b`
- `ntoskrnl!SeAccessCheck` at `0x1400180a7`
- `ntoskrnl!SeAccessCheck` at `0x1400180a7`

## string_xrefs

- `0x140018100`: `VmbusTlEndpointAccessCheck`

## pseudocode

```c
__int64 __fastcall VmbusTlEndpointAccessCheck(PEPROCESS Process, PSECURITY_DESCRIPTOR SecurityDescriptor)
{
  struct _GENERIC_MAPPING *GenericMapping; // rax
  unsigned int ProcessId; // eax
  _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+50h] [rbp-20h] BYREF
  int AccessStatus; // [rsp+90h] [rbp+20h] BYREF
  DWORD GrantedAccess; // [rsp+98h] [rbp+28h] BYREF

  GrantedAccess = 0;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  SeCaptureSubjectContextEx(0, Process, &SubjectContext);
  SeLockSubjectContext(&SubjectContext);
  AccessStatus = 0;
  GenericMapping = IoGetFileObjectGenericMapping();
  LOBYTE(SecurityDescriptor) = SeAccessCheck(
                                 SecurityDescriptor,
                                 &SubjectContext,
                                 1u,
                                 0x12019Fu,
                                 0,
                                 0,
                                 GenericMapping,
                                 1,
                                 &GrantedAccess,
                                 &AccessStatus);
  SeUnlockSubjectContext(&SubjectContext);
  SeReleaseSubjectContext(&SubjectContext);
  if ( !(_BYTE)SecurityDescriptor && (unsigned int)dword_140013058 > 2 )
  {
    if ( Process )
      ProcessId = (unsigned int)PsGetProcessId(Process);
    else
      ProcessId = 0;
    HvsocketTraceULongError("VmbusTlEndpointAccessCheck", 49, (unsigned int)AccessStatus, ProcessId);
  }
  return (unsigned int)AccessStatus;
}

```

## disassembly

```asm
0x140018008  mov     [rsp-8+arg_0], rbx
0x14001800d  mov     [rsp-8+arg_8], rdi
0x140018012  push    rbp
0x140018013  mov     rbp, rsp
0x140018016  sub     rsp, 70h
0x14001801a  xorps   xmm0, xmm0
0x14001801d  mov     [rbp+arg_18], 0
0x140018024  mov     rbx, rdx
0x140018027  lea     r8, [rbp+SubjectContext]; SubjectContext
0x14001802b  mov     rdx, rcx; Process
0x14001802e  mov     rdi, rcx
0x140018031  xor     ecx, ecx; Thread
0x140018033  movups  xmmword ptr [rbp+SubjectContext.ClientToken], xmm0
0x140018037  movups  xmmword ptr [rbp+SubjectContext.PrimaryToken], xmm0
0x14001803b  call    cs:__imp_SeCaptureSubjectContextEx
0x140018042  nop     dword ptr [rax+rax+00h]
0x140018047  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x14001804b  call    cs:__imp_SeLockSubjectContext
0x140018052  nop     dword ptr [rax+rax+00h]
0x140018057  mov     [rbp+arg_10], 0
0x14001805e  call    cs:__imp_IoGetFileObjectGenericMapping
0x140018065  nop     dword ptr [rax+rax+00h]
0x14001806a  lea     rcx, [rbp+arg_10]
0x14001806e  mov     r9d, 12019Fh; DesiredAccess
0x140018074  mov     [rsp+70h+AccessStatus], rcx; AccessStatus
0x140018079  lea     rdx, [rbp+SubjectContext]; SubjectSecurityContext
0x14001807d  lea     rcx, [rbp+arg_18]
0x140018081  mov     r8b, 1; SubjectContextLocked
0x140018084  mov     [rsp+70h+GrantedAccess], rcx; GrantedAccess
0x140018089  mov     rcx, rbx; SecurityDescriptor
0x14001808c  mov     [rsp+70h+AccessMode], 1; AccessMode
0x140018091  mov     [rsp+70h+GenericMapping], rax; GenericMapping
0x140018096  mov     [rsp+70h+Privileges], 0; Privileges
0x14001809f  mov     [rsp+70h+PreviouslyGrantedAccess], 0; PreviouslyGrantedAccess
0x1400180a7  call    cs:__imp_SeAccessCheck
0x1400180ae  nop     dword ptr [rax+rax+00h]
0x1400180b3  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x1400180b7  mov     bl, al
0x1400180b9  call    cs:__imp_SeUnlockSubjectContext
0x1400180c0  nop     dword ptr [rax+rax+00h]
0x1400180c5  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x1400180c9  call    cs:__imp_SeReleaseSubjectContext
0x1400180d0  nop     dword ptr [rax+rax+00h]
0x1400180d5  test    bl, bl
0x1400180d7  jnz     short loc_140018114
0x1400180d9  mov     eax, cs:dword_140013058
0x1400180df  cmp     eax, 2
0x1400180e2  jbe     short loc_140018114
0x1400180e4  test    rdi, rdi
0x1400180e7  jnz     short loc_1400180ED
0x1400180e9  xor     eax, eax
0x1400180eb  jmp     short loc_1400180FC
0x1400180ed  mov     rcx, rdi; Process
0x1400180f0  call    cs:__imp_PsGetProcessId
0x1400180f7  nop     dword ptr [rax+rax+00h]
0x1400180fc  mov     r8d, [rbp+arg_10]
0x140018100  lea     rcx, aVmbustlendpoin_1; "VmbusTlEndpointAccessCheck"
0x140018107  mov     r9d, eax
0x14001810a  mov     edx, 31h ; '1'
0x14001810f  call    HvsocketTraceULongError
0x140018114  mov     eax, [rbp+arg_10]
0x140018117  lea     r11, [rsp+70h+var_s0]
0x14001811c  mov     rbx, [r11+10h]
0x140018120  mov     rdi, [r11+18h]
0x140018124  mov     rsp, r11
0x140018127  pop     rbp
0x140018128  retn
```
