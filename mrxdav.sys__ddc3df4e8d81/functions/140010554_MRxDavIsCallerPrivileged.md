# MRxDavIsCallerPrivileged

- ea: `0x140010554`
- end: `0x14001060f`
- name: `MRxDavIsCallerPrivileged`
- size: `187`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000f120`
- `0x14000f780`

## import_xrefs

- `ntoskrnl!SeCaptureSubjectContext` at `0x140010579`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140010579`
- `ntoskrnl!SeAccessCheck` at `0x1400105db`
- `ntoskrnl!SeAccessCheck` at `0x1400105db`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140010585`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140010585`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1400105ee`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1400105ee`

## pseudocode

```c
__int64 MRxDavIsCallerPrivileged()
{
  struct _GENERIC_MAPPING *GenericMapping; // rax
  BOOLEAN v1; // bl
  __int64 result; // rax
  struct _SECURITY_SUBJECT_CONTEXT SubjectSecurityContext; // [rsp+50h] [rbp-28h] BYREF
  int AccessStatus; // [rsp+80h] [rbp+8h] BYREF
  DWORD GrantedAccess; // [rsp+88h] [rbp+10h] BYREF

  GrantedAccess = 0;
  AccessStatus = -1073741790;
  memset(&SubjectSecurityContext, 0, sizeof(SubjectSecurityContext));
  SeCaptureSubjectContext(&SubjectSecurityContext);
  GenericMapping = IoGetFileObjectGenericMapping();
  v1 = SeAccessCheck(
         qword_14002A008,
         &SubjectSecurityContext,
         0,
         2u,
         0,
         0,
         GenericMapping,
         1,
         &GrantedAccess,
         &AccessStatus);
  SeReleaseSubjectContext(&SubjectSecurityContext);
  result = (unsigned int)AccessStatus;
  if ( v1 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x140010554  mov     rax, rsp
0x140010557  push    rbx
0x140010558  sub     rsp, 70h
0x14001055c  xorps   xmm0, xmm0
0x14001055f  mov     dword ptr [rax+10h], 0
0x140010566  lea     rcx, [rax-28h]; SubjectContext
0x14001056a  mov     dword ptr [rax+8], 0C0000022h
0x140010571  movups  xmmword ptr [rax-28h], xmm0
0x140010575  movups  xmmword ptr [rax-18h], xmm0
0x140010579  call    cs:__imp_SeCaptureSubjectContext
0x140010580  nop     dword ptr [rax+rax+00h]
0x140010585  call    cs:__imp_IoGetFileObjectGenericMapping
0x14001058c  nop     dword ptr [rax+rax+00h]
0x140010591  lea     rcx, [rsp+78h+arg_0]
0x140010599  mov     r9d, 2; DesiredAccess
0x14001059f  mov     [rsp+78h+AccessStatus], rcx; AccessStatus
0x1400105a4  lea     rdx, [rsp+78h+SubjectSecurityContext]; SubjectSecurityContext
0x1400105a9  lea     rcx, [rsp+78h+arg_8]
0x1400105b1  xor     r8d, r8d; SubjectContextLocked
0x1400105b4  mov     [rsp+78h+GrantedAccess], rcx; GrantedAccess
0x1400105b9  lea     rcx, qword_14002A008; SecurityDescriptor
0x1400105c0  mov     [rsp+78h+AccessMode], 1; AccessMode
0x1400105c5  mov     [rsp+78h+GenericMapping], rax; GenericMapping
0x1400105ca  mov     [rsp+78h+Privileges], 0; Privileges
0x1400105d3  mov     [rsp+78h+PreviouslyGrantedAccess], 0; PreviouslyGrantedAccess
0x1400105db  call    cs:__imp_SeAccessCheck
0x1400105e2  nop     dword ptr [rax+rax+00h]
0x1400105e7  lea     rcx, [rsp+78h+SubjectSecurityContext]; SubjectContext
0x1400105ec  mov     bl, al
0x1400105ee  call    cs:__imp_SeReleaseSubjectContext
0x1400105f5  nop     dword ptr [rax+rax+00h]
0x1400105fa  mov     eax, [rsp+78h+arg_0]
0x140010601  xor     ecx, ecx
0x140010603  test    bl, bl
0x140010605  cmovnz  eax, ecx
0x140010608  add     rsp, 70h
0x14001060c  pop     rbx
0x14001060d  retn
```
