# NsippIsCallerNsiService

- ea: `0x1400032d0`
- end: `0x1400033b3`
- name: `NsippIsCallerNsiService`
- size: `227`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140001dd0`
- `0x140002090`

## callees

- `0x1400032d0`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x1400032eb`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400032eb`
- `ntoskrnl!SeCaptureSubjectContextEx` at `0x140003301`
- `ntoskrnl!SeCaptureSubjectContextEx` at `0x140003301`
- `ntoskrnl!SeLockSubjectContext` at `0x140003312`
- `ntoskrnl!SeLockSubjectContext` at `0x140003312`
- `ntoskrnl!SeAccessCheck` at `0x14000336c`
- `ntoskrnl!SeAccessCheck` at `0x14000336c`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14000331e`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14000331e`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140003380`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140003380`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140003391`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140003391`

## pseudocode

```c
__int64 NsippIsCallerNsiService()
{
  struct _KPROCESS *CurrentProcess; // rax
  struct _GENERIC_MAPPING *GenericMapping; // rax
  BOOLEAN v2; // bl
  _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+50h] [rbp-28h] BYREF
  int AccessStatus; // [rsp+80h] [rbp+8h] BYREF
  DWORD GrantedAccess; // [rsp+88h] [rbp+10h] BYREF

  AccessStatus = 0;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  GrantedAccess = 0;
  CurrentProcess = (struct _KPROCESS *)PsGetCurrentProcess();
  SeCaptureSubjectContextEx(0, CurrentProcess, &SubjectContext);
  SeLockSubjectContext(&SubjectContext);
  GenericMapping = IoGetFileObjectGenericMapping();
  v2 = SeAccessCheck(
         NsiServiceSecurityDescriptor,
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
  if ( v2 )
    return 0;
  else
    return (unsigned int)AccessStatus;
}

```

## disassembly

```asm
0x1400032d0  mov     rax, rsp
0x1400032d3  push    rbx
0x1400032d4  sub     rsp, 70h
0x1400032d8  xorps   xmm0, xmm0
0x1400032db  xor     ebx, ebx
0x1400032dd  mov     [rax+8], ebx
0x1400032e0  movups  xmmword ptr [rax-28h], xmm0
0x1400032e4  mov     [rax+10h], ebx
0x1400032e7  movups  xmmword ptr [rax-18h], xmm0
0x1400032eb  call    cs:__imp_PsGetCurrentProcess
0x1400032f2  nop     dword ptr [rax+rax+00h]
0x1400032f7  lea     r8, [rsp+78h+SubjectContext]; SubjectContext
0x1400032fc  xor     ecx, ecx; Thread
0x1400032fe  mov     rdx, rax; Process
0x140003301  call    cs:__imp_SeCaptureSubjectContextEx
0x140003308  nop     dword ptr [rax+rax+00h]
0x14000330d  lea     rcx, [rsp+78h+SubjectContext]; SubjectContext
0x140003312  call    cs:__imp_SeLockSubjectContext
0x140003319  nop     dword ptr [rax+rax+00h]
0x14000331e  call    cs:__imp_IoGetFileObjectGenericMapping
0x140003325  nop     dword ptr [rax+rax+00h]
0x14000332a  lea     rcx, [rsp+78h+arg_0]
0x140003332  mov     r9d, 1F01FFh; DesiredAccess
0x140003338  mov     [rsp+78h+AccessStatus], rcx; AccessStatus
0x14000333d  lea     rdx, [rsp+78h+SubjectContext]; SubjectSecurityContext
0x140003342  lea     rcx, [rsp+78h+arg_8]
0x14000334a  mov     r8b, 1; SubjectContextLocked
0x14000334d  mov     [rsp+78h+GrantedAccess], rcx; GrantedAccess
0x140003352  mov     rcx, cs:NsiServiceSecurityDescriptor; SecurityDescriptor
0x140003359  mov     [rsp+78h+AccessMode], 1; AccessMode
0x14000335e  mov     [rsp+78h+GenericMapping], rax; GenericMapping
0x140003363  mov     [rsp+78h+Privileges], rbx; Privileges
0x140003368  mov     [rsp+78h+PreviouslyGrantedAccess], ebx; PreviouslyGrantedAccess
0x14000336c  call    cs:__imp_SeAccessCheck
0x140003373  nop     dword ptr [rax+rax+00h]
0x140003378  lea     rcx, [rsp+78h+SubjectContext]; SubjectContext
0x14000337d  movzx   ebx, al
0x140003380  call    cs:__imp_SeUnlockSubjectContext
0x140003387  nop     dword ptr [rax+rax+00h]
0x14000338c  lea     rcx, [rsp+78h+SubjectContext]; SubjectContext
0x140003391  call    cs:__imp_SeReleaseSubjectContext
0x140003398  nop     dword ptr [rax+rax+00h]
0x14000339d  test    bl, bl
0x14000339f  jz      short loc_1400033AA
0x1400033a1  xor     eax, eax
0x1400033a3  add     rsp, 70h
0x1400033a7  pop     rbx
0x1400033a8  retn
0x1400033aa  mov     eax, [rsp+78h+arg_0]
0x1400033b1  jmp     short loc_1400033A3
```
