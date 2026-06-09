# FveCheckAdminAccess

- ea: `0x14000b920`
- end: `0x14000ba80`
- name: `FveCheckAdminAccess`
- size: `352`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140052d1c`
- `0x1400531e4`
- `0x14005380c`
- `0x140053c80`
- `0x1400541cc`
- `0x14005452c`

## callees

- `0x14000b920`

## import_xrefs

- `ntoskrnl!SeReleaseSubjectContext` at `0x14000ba3d`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14000ba3d`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14000ba2d`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14000ba2d`
- `ntoskrnl!SeAccessCheck` at `0x14000ba1b`
- `ntoskrnl!SeAccessCheck` at `0x14000ba1b`
- `ntoskrnl!SeLockSubjectContext` at `0x14000b9c2`
- `ntoskrnl!SeLockSubjectContext` at `0x14000b9c2`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14000b9b2`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14000b9b2`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14000b98f`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14000b9d5`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14000b98f`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14000b9d5`
- `ntoskrnl!RtlMapGenericMask` at `0x14000b9a2`
- `ntoskrnl!RtlMapGenericMask` at `0x14000b9a2`

## pseudocode

```c
__int64 __fastcall FveCheckAdminAccess(__int64 a1, __int64 a2, DWORD a3)
{
  __int64 v5; // rax
  __int64 v6; // rcx
  __int64 v7; // rdi
  struct _GENERIC_MAPPING *FileObjectGenericMapping; // rax
  KPROCESSOR_MODE AccessMode; // bl
  void *v10; // rdi
  struct _GENERIC_MAPPING *GenericMapping; // rax
  BOOLEAN v12; // bl
  DWORD GrantedAccess; // [rsp+50h] [rbp-30h] BYREF
  _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+58h] [rbp-28h] BYREF
  DWORD AccessMask; // [rsp+A0h] [rbp+20h] BYREF
  int AccessStatus; // [rsp+B8h] [rbp+38h] BYREF

  AccessMask = 0;
  GrantedAccess = 0;
  AccessStatus = 0;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  if ( !a1 )
    return 3221225860LL;
  v5 = *(_QWORD *)(a1 + 24);
  if ( !v5 )
    return 3221225860LL;
  v6 = *(_QWORD *)(v5 + 8);
  if ( !v6 )
    return 3221225860LL;
  v7 = *(_QWORD *)(v6 + 200);
  if ( !v7 )
    return 3221225860LL;
  AccessMask = a3;
  FileObjectGenericMapping = IoGetFileObjectGenericMapping();
  RtlMapGenericMask(&AccessMask, FileObjectGenericMapping);
  SeCaptureSubjectContext(&SubjectContext);
  SeLockSubjectContext(&SubjectContext);
  AccessMode = *(_BYTE *)(a2 + 64);
  v10 = *(void **)(v7 + 16);
  GenericMapping = IoGetFileObjectGenericMapping();
  v12 = SeAccessCheck(
          v10,
          &SubjectContext,
          1u,
          AccessMask,
          0,
          0,
          GenericMapping,
          AccessMode,
          &GrantedAccess,
          &AccessStatus);
  SeUnlockSubjectContext(&SubjectContext);
  SeReleaseSubjectContext(&SubjectContext);
  if ( AccessStatus >= 0 && v12 && (a3 & GrantedAccess) == a3 )
    return 0;
  else
    return 3221225506LL;
}

```

## disassembly

```asm
0x14000b920  mov     [rsp-18h+arg_8], rbx
0x14000b925  push    rbp
0x14000b926  push    rsi
0x14000b927  push    rdi
0x14000b928  mov     rbp, rsp
0x14000b92b  sub     rsp, 80h
0x14000b932  mov     [rbp+AccessMask], 0
0x14000b939  xorps   xmm0, xmm0
0x14000b93c  mov     [rbp+var_30], 0
0x14000b943  mov     esi, r8d
0x14000b946  mov     [rbp+arg_18], 0
0x14000b94d  mov     rbx, rdx
0x14000b950  movups  xmmword ptr [rbp+SubjectContext.ClientToken], xmm0
0x14000b954  movups  xmmword ptr [rbp+SubjectContext.PrimaryToken], xmm0
0x14000b958  test    rcx, rcx
0x14000b95b  jz      loc_14000BA67
0x14000b961  mov     rax, [rcx+18h]
0x14000b965  test    rax, rax
0x14000b968  jz      loc_14000BA67
0x14000b96e  mov     rcx, [rax+8]
0x14000b972  test    rcx, rcx
0x14000b975  jz      loc_14000BA67
0x14000b97b  mov     rdi, [rcx+0C8h]
0x14000b982  test    rdi, rdi
0x14000b985  jz      loc_14000BA67
0x14000b98b  mov     [rbp+AccessMask], r8d
0x14000b98f  call    cs:__imp_IoGetFileObjectGenericMapping
0x14000b996  nop     dword ptr [rax+rax+00h]
0x14000b99b  mov     rdx, rax; GenericMapping
0x14000b99e  lea     rcx, [rbp+AccessMask]; AccessMask
0x14000b9a2  call    cs:__imp_RtlMapGenericMask
0x14000b9a9  nop     dword ptr [rax+rax+00h]
0x14000b9ae  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x14000b9b2  call    cs:__imp_SeCaptureSubjectContext
0x14000b9b9  nop     dword ptr [rax+rax+00h]
0x14000b9be  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x14000b9c2  call    cs:__imp_SeLockSubjectContext
0x14000b9c9  nop     dword ptr [rax+rax+00h]
0x14000b9ce  mov     bl, [rbx+40h]
0x14000b9d1  mov     rdi, [rdi+10h]
0x14000b9d5  call    cs:__imp_IoGetFileObjectGenericMapping
0x14000b9dc  nop     dword ptr [rax+rax+00h]
0x14000b9e1  mov     r9d, [rbp+AccessMask]; DesiredAccess
0x14000b9e5  lea     rcx, [rbp+arg_18]
0x14000b9e9  mov     [rsp+80h+AccessStatus], rcx; AccessStatus
0x14000b9ee  lea     rdx, [rbp+SubjectContext]; SubjectSecurityContext
0x14000b9f2  lea     rcx, [rbp+var_30]
0x14000b9f6  mov     r8b, 1; SubjectContextLocked
0x14000b9f9  mov     [rsp+80h+GrantedAccess], rcx; GrantedAccess
0x14000b9fe  mov     rcx, rdi; SecurityDescriptor
0x14000ba01  mov     [rsp+80h+AccessMode], bl; AccessMode
0x14000ba05  mov     [rsp+80h+GenericMapping], rax; GenericMapping
0x14000ba0a  mov     [rsp+80h+Privileges], 0; Privileges
0x14000ba13  mov     [rsp+80h+PreviouslyGrantedAccess], 0; PreviouslyGrantedAccess
0x14000ba1b  call    cs:__imp_SeAccessCheck
0x14000ba22  nop     dword ptr [rax+rax+00h]
0x14000ba27  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x14000ba2b  mov     bl, al
0x14000ba2d  call    cs:__imp_SeUnlockSubjectContext
0x14000ba34  nop     dword ptr [rax+rax+00h]
0x14000ba39  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x14000ba3d  call    cs:__imp_SeReleaseSubjectContext
0x14000ba44  nop     dword ptr [rax+rax+00h]
0x14000ba49  cmp     [rbp+arg_18], 0
0x14000ba4d  jl      short loc_14000BA60
0x14000ba4f  test    bl, bl
0x14000ba51  jz      short loc_14000BA60
0x14000ba53  mov     eax, [rbp+var_30]
0x14000ba56  and     eax, esi
0x14000ba58  cmp     eax, esi
0x14000ba5a  jnz     short loc_14000BA60
0x14000ba5c  xor     eax, eax
0x14000ba5e  jmp     short loc_14000BA6C
0x14000ba60  mov     eax, 0C0000022h
0x14000ba65  jmp     short loc_14000BA6C
0x14000ba67  mov     eax, 0C0000184h
0x14000ba6c  mov     rbx, [rsp+80h+arg_8]
0x14000ba74  add     rsp, 80h
0x14000ba7b  pop     rdi
0x14000ba7c  pop     rsi
0x14000ba7d  pop     rbp
0x14000ba7e  retn
```
