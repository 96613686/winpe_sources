# FatExplicitDeviceAccessGranted

- ea: `0x1400202a0`
- end: `0x140020450`
- name: `FatExplicitDeviceAccessGranted`
- size: `432`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14002c234`

## callees

- `0x14000c230`
- `0x14002023c`
- `0x1400202a0`

## import_xrefs

- `ntoskrnl!SeLockSubjectContext` at `0x140020307`
- `ntoskrnl!SeLockSubjectContext` at `0x140020307`
- `ntoskrnl!SeFilterToken` at `0x14002036f`
- `ntoskrnl!SeFilterToken` at `0x14002036f`
- `ntoskrnl!SeExports` at `0x140020329`
- `ntoskrnl!ObfDereferenceObject` at `0x140020415`
- `ntoskrnl!ObfDereferenceObject` at `0x140020415`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140020405`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140020405`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400203ac`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400203ac`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140020385`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140020385`
- `ntoskrnl!SeAccessCheck` at `0x1400203f1`
- `ntoskrnl!SeAccessCheck` at `0x1400203f1`

## pseudocode

```c
__int64 __fastcall FatExplicitDeviceAccessGranted(__int64 a1, __int64 a2, __int64 a3, KPROCESSOR_MODE a4)
{
  bool v5; // zf
  __int64 v6; // rsi
  void *v8; // rax
  void *v9; // r15
  unsigned __int64 v10; // r12
  ACCESS_MASK v12; // ebx
  void *v13; // rdi
  struct _GENERIC_MAPPING *GenericMapping; // rax
  int AccessStatus; // [rsp+50h] [rbp-19h] BYREF
  PACCESS_TOKEN Object; // [rsp+58h] [rbp-11h] BYREF
  DWORD GrantedAccess; // [rsp+60h] [rbp-9h] BYREF
  struct _TOKEN_GROUPS SidsToDisable; // [rsp+68h] [rbp-1h] BYREF

  v5 = (*(_DWORD *)(a3 + 20) & 0xFFDF) == 0;
  v6 = a3;
  AccessStatus = 0;
  Object = 0;
  GrantedAccess = 0;
  if ( !v5 )
    return 0;
  LOBYTE(a3) = a4;
  if ( (unsigned __int8)FatCheckManageVolumeAccess(a1, v6, a3) )
    return 0;
  SeLockSubjectContext((PSECURITY_SUBJECT_CONTEXT)(v6 + 32));
  v8 = *(void **)(v6 + 32);
  v9 = v8;
  if ( !v8 )
    v9 = *(void **)(v6 + 48);
  Object = 0;
  SidsToDisable.GroupCount = 1;
  *(_OWORD *)(&SidsToDisable.GroupCount + 1) = 0u;
  v10 = -(__int64)(v8 != 0) & 0xFFFFFFFFFFFFFFF0uLL;
  SidsToDisable.Groups[0].Sid = SeExports->SeWorldSid;
  AccessStatus = SeFilterToken(v9, 0, &SidsToDisable, 0, 0, &Object);
  if ( AccessStatus >= 0 )
  {
    *(_QWORD *)(v10 + v6 + 48) = Object;
    v12 = *(_DWORD *)(v6 + 24);
    v13 = *(void **)(a2 + 272);
    GenericMapping = IoGetFileObjectGenericMapping();
    SeAccessCheck(
      v13,
      (PSECURITY_SUBJECT_CONTEXT)(v6 + 32),
      0,
      v12,
      0,
      0,
      GenericMapping,
      a4,
      &GrantedAccess,
      &AccessStatus);
    *(_QWORD *)(v10 + v6 + 48) = v9;
    SeUnlockSubjectContext((PSECURITY_SUBJECT_CONTEXT)(v6 + 32));
    ObfDereferenceObject(Object);
  }
  else
  {
    SeReleaseSubjectContext((PSECURITY_SUBJECT_CONTEXT)(v6 + 32));
  }
  return (unsigned int)AccessStatus;
}

```

## disassembly

```asm
0x1400202a0  mov     [rsp-8+arg_0], rbx
0x1400202a5  push    rbp
0x1400202a6  push    rsi
0x1400202a7  push    rdi
0x1400202a8  push    r12
0x1400202aa  push    r13
0x1400202ac  push    r14
0x1400202ae  push    r15
0x1400202b0  lea     rbp, [rsp-27h]
0x1400202b5  sub     rsp, 90h
0x1400202bc  mov     rax, cs:__security_cookie
0x1400202c3  xor     rax, rsp
0x1400202c6  mov     [rbp+57h+var_40], rax
0x1400202ca  xor     ebx, ebx
0x1400202cc  mov     r13b, r9b
0x1400202cf  test    dword ptr [r8+14h], 0FFDFh
0x1400202d7  mov     rsi, r8
0x1400202da  mov     rdi, rdx
0x1400202dd  mov     [rbp+57h+var_70], ebx
0x1400202e0  mov     [rbp+57h+Object], rbx
0x1400202e4  mov     [rbp+57h+var_60], ebx
0x1400202e7  jnz     loc_140020426
0x1400202ed  mov     r8b, r9b
0x1400202f0  mov     rdx, rsi
0x1400202f3  call    FatCheckManageVolumeAccess
0x1400202f8  test    al, al
0x1400202fa  jnz     loc_140020426
0x140020300  lea     r14, [rsi+20h]
0x140020304  mov     rcx, r14; SubjectContext
0x140020307  call    cs:__imp_SeLockSubjectContext
0x14002030e  nop     dword ptr [rax+rax+00h]
0x140020313  mov     rax, [r14]
0x140020316  mov     r15, rax
0x140020319  test    rax, rax
0x14002031c  jnz     short loc_140020322
0x14002031e  mov     r15, [rsi+30h]
0x140020322  neg     rax
0x140020325  mov     [rbp+57h+Object], rbx
0x140020329  mov     rax, cs:__imp_SeExports
0x140020330  lea     r8, [rbp+57h+SidsToDisable]; SidsToDisable
0x140020334  sbb     r12, r12
0x140020337  mov     qword ptr [rbp+57h+SidsToDisable.GroupCount], 1
0x14002033f  mov     qword ptr [rbp+57h+SidsToDisable+4], rbx
0x140020343  xor     r9d, r9d; PrivilegesToDelete
0x140020346  mov     [rbp+57h+SidsToDisable.Groups.Sid+4], rbx
0x14002034a  xor     edx, edx; Flags
0x14002034c  mov     rcx, [rax]
0x14002034f  and     r12, 0FFFFFFFFFFFFFFF0h
0x140020353  mov     rax, [rcx+0C0h]
0x14002035a  mov     rcx, r15; ExistingToken
0x14002035d  mov     [rbp+7], rax
0x140020361  lea     rax, [rbp+57h+Object]
0x140020365  mov     [rsp+0C0h+FilteredToken], rax; FilteredToken
0x14002036a  mov     [rsp+0C0h+RestrictedSids], rbx; RestrictedSids
0x14002036f  call    cs:__imp_SeFilterToken
0x140020376  nop     dword ptr [rax+rax+00h]
0x14002037b  mov     [rbp+57h+var_70], eax
0x14002037e  test    eax, eax
0x140020380  jns     short loc_140020399
0x140020382  mov     rcx, r14; SubjectContext
0x140020385  call    cs:__imp_SeReleaseSubjectContext
0x14002038c  nop     dword ptr [rax+rax+00h]
0x140020391  mov     eax, [rbp+57h+var_70]
0x140020394  jmp     loc_140020428
0x140020399  mov     rax, [rbp+57h+Object]
0x14002039d  mov     [r12+rsi+30h], rax
0x1400203a2  mov     ebx, [rsi+18h]
0x1400203a5  mov     rdi, [rdi+110h]
0x1400203ac  call    cs:__imp_IoGetFileObjectGenericMapping
0x1400203b3  nop     dword ptr [rax+rax+00h]
0x1400203b8  lea     rcx, [rbp+57h+var_70]
0x1400203bc  mov     r9d, ebx; DesiredAccess
0x1400203bf  mov     [rsp+0C0h+AccessStatus], rcx; AccessStatus
0x1400203c4  xor     r8d, r8d; SubjectContextLocked
0x1400203c7  lea     rcx, [rbp+57h+var_60]
0x1400203cb  mov     rdx, r14; SubjectSecurityContext
0x1400203ce  mov     [rsp+0C0h+GrantedAccess], rcx; GrantedAccess
0x1400203d3  mov     rcx, rdi; SecurityDescriptor
0x1400203d6  mov     [rsp+0C0h+AccessMode], r13b; AccessMode
0x1400203db  mov     [rsp+0C0h+GenericMapping], rax; GenericMapping
0x1400203e0  mov     [rsp+0C0h+FilteredToken], 0; Privileges
0x1400203e9  mov     dword ptr [rsp+0C0h+RestrictedSids], 0; PreviouslyGrantedAccess
0x1400203f1  call    cs:__imp_SeAccessCheck
0x1400203f8  nop     dword ptr [rax+rax+00h]
0x1400203fd  mov     rcx, r14; SubjectContext
0x140020400  mov     [r12+rsi+30h], r15
0x140020405  call    cs:__imp_SeUnlockSubjectContext
0x14002040c  nop     dword ptr [rax+rax+00h]
0x140020411  mov     rcx, [rbp+57h+Object]; Object
0x140020415  call    cs:__imp_ObfDereferenceObject
0x14002041c  nop     dword ptr [rax+rax+00h]
0x140020421  jmp     loc_140020391
0x140020426  xor     eax, eax
0x140020428  mov     rcx, [rbp+57h+var_40]
0x14002042c  xor     rcx, rsp; StackCookie
0x14002042f  call    __security_check_cookie
0x140020434  mov     rbx, [rsp+0C0h+arg_0]
0x14002043c  add     rsp, 90h
0x140020443  pop     r15
0x140020445  pop     r14
0x140020447  pop     r13
0x140020449  pop     r12
0x14002044b  pop     rdi
0x14002044c  pop     rsi
0x14002044d  pop     rbp
0x14002044e  retn
```
