# FveCheckAdminAccess

- ea: `0x14000ba48`
- end: `0x14000bba8`
- name: `FveCheckAdminAccess`
- size: `352`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140054d24`
- `0x1400551f4`
- `0x14005581c`
- `0x140055c90`
- `0x1400561dc`
- `0x14005653c`

## callees

- `0x14000ba48`

## import_xrefs

- `ntoskrnl!SeReleaseSubjectContext` at `0x14000bb65`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14000bb65`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14000bb55`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14000bb55`
- `ntoskrnl!SeAccessCheck` at `0x14000bb43`
- `ntoskrnl!SeAccessCheck` at `0x14000bb43`
- `ntoskrnl!SeLockSubjectContext` at `0x14000baea`
- `ntoskrnl!SeLockSubjectContext` at `0x14000baea`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14000bada`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14000bada`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14000bab7`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14000bafd`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14000bab7`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14000bafd`
- `ntoskrnl!RtlMapGenericMask` at `0x14000baca`
- `ntoskrnl!RtlMapGenericMask` at `0x14000baca`

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
0x14000ba48  mov     [rsp-18h+arg_8], rbx
0x14000ba4d  push    rbp
0x14000ba4e  push    rsi
0x14000ba4f  push    rdi
0x14000ba50  mov     rbp, rsp
0x14000ba53  sub     rsp, 80h
0x14000ba5a  mov     [rbp+AccessMask], 0
0x14000ba61  xorps   xmm0, xmm0
0x14000ba64  mov     [rbp+var_30], 0
0x14000ba6b  mov     esi, r8d
0x14000ba6e  mov     [rbp+arg_18], 0
0x14000ba75  mov     rbx, rdx
0x14000ba78  movups  xmmword ptr [rbp+SubjectContext.ClientToken], xmm0
0x14000ba7c  movups  xmmword ptr [rbp+SubjectContext.PrimaryToken], xmm0
0x14000ba80  test    rcx, rcx
0x14000ba83  jz      loc_14000BB8F
0x14000ba89  mov     rax, [rcx+18h]
0x14000ba8d  test    rax, rax
0x14000ba90  jz      loc_14000BB8F
0x14000ba96  mov     rcx, [rax+8]
0x14000ba9a  test    rcx, rcx
0x14000ba9d  jz      loc_14000BB8F
0x14000baa3  mov     rdi, [rcx+0C8h]
0x14000baaa  test    rdi, rdi
0x14000baad  jz      loc_14000BB8F
0x14000bab3  mov     [rbp+AccessMask], r8d
0x14000bab7  call    cs:__imp_IoGetFileObjectGenericMapping
0x14000babe  nop     dword ptr [rax+rax+00h]
0x14000bac3  mov     rdx, rax; GenericMapping
0x14000bac6  lea     rcx, [rbp+AccessMask]; AccessMask
0x14000baca  call    cs:__imp_RtlMapGenericMask
0x14000bad1  nop     dword ptr [rax+rax+00h]
0x14000bad6  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x14000bada  call    cs:__imp_SeCaptureSubjectContext
0x14000bae1  nop     dword ptr [rax+rax+00h]
0x14000bae6  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x14000baea  call    cs:__imp_SeLockSubjectContext
0x14000baf1  nop     dword ptr [rax+rax+00h]
0x14000baf6  mov     bl, [rbx+40h]
0x14000baf9  mov     rdi, [rdi+10h]
0x14000bafd  call    cs:__imp_IoGetFileObjectGenericMapping
0x14000bb04  nop     dword ptr [rax+rax+00h]
0x14000bb09  mov     r9d, [rbp+AccessMask]; DesiredAccess
0x14000bb0d  lea     rcx, [rbp+arg_18]
0x14000bb11  mov     [rsp+80h+AccessStatus], rcx; AccessStatus
0x14000bb16  lea     rdx, [rbp+SubjectContext]; SubjectSecurityContext
0x14000bb1a  lea     rcx, [rbp+var_30]
0x14000bb1e  mov     r8b, 1; SubjectContextLocked
0x14000bb21  mov     [rsp+80h+GrantedAccess], rcx; GrantedAccess
0x14000bb26  mov     rcx, rdi; SecurityDescriptor
0x14000bb29  mov     [rsp+80h+AccessMode], bl; AccessMode
0x14000bb2d  mov     [rsp+80h+GenericMapping], rax; GenericMapping
0x14000bb32  mov     [rsp+80h+Privileges], 0; Privileges
0x14000bb3b  mov     [rsp+80h+PreviouslyGrantedAccess], 0; PreviouslyGrantedAccess
0x14000bb43  call    cs:__imp_SeAccessCheck
0x14000bb4a  nop     dword ptr [rax+rax+00h]
0x14000bb4f  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x14000bb53  mov     bl, al
0x14000bb55  call    cs:__imp_SeUnlockSubjectContext
0x14000bb5c  nop     dword ptr [rax+rax+00h]
0x14000bb61  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x14000bb65  call    cs:__imp_SeReleaseSubjectContext
0x14000bb6c  nop     dword ptr [rax+rax+00h]
0x14000bb71  cmp     [rbp+arg_18], 0
0x14000bb75  jl      short loc_14000BB88
0x14000bb77  test    bl, bl
0x14000bb79  jz      short loc_14000BB88
0x14000bb7b  mov     eax, [rbp+var_30]
0x14000bb7e  and     eax, esi
0x14000bb80  cmp     eax, esi
0x14000bb82  jnz     short loc_14000BB88
0x14000bb84  xor     eax, eax
0x14000bb86  jmp     short loc_14000BB94
0x14000bb88  mov     eax, 0C0000022h
0x14000bb8d  jmp     short loc_14000BB94
0x14000bb8f  mov     eax, 0C0000184h
0x14000bb94  mov     rbx, [rsp+80h+arg_8]
0x14000bb9c  add     rsp, 80h
0x14000bba3  pop     rdi
0x14000bba4  pop     rsi
0x14000bba5  pop     rbp
0x14000bba6  retn
```
