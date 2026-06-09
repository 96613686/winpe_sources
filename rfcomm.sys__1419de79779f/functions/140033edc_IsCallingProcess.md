# IsCallingProcess

- ea: `0x140033edc`
- end: `0x140034040`
- name: `IsCallingProcess`
- size: `356`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR SecurityDescriptor)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140001eec`
- `0x140009cc8`
- `0x140032148`

## callees

- `0x140033edc`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140033fe7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033ffe`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033fe7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033ffe`
- `ntoskrnl!SeAccessCheckFromState` at `0x140033fce`
- `ntoskrnl!SeAccessCheckFromState` at `0x140033fce`
- `ntoskrnl!SeQueryInformationToken` at `0x140033f4c`
- `ntoskrnl!SeQueryInformationToken` at `0x140033f76`
- `ntoskrnl!SeQueryInformationToken` at `0x140033f4c`
- `ntoskrnl!SeQueryInformationToken` at `0x140033f76`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14003401e`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14003401e`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14003400e`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14003400e`
- `ntoskrnl!SeLockSubjectContext` at `0x140033f33`
- `ntoskrnl!SeLockSubjectContext` at `0x140033f33`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140033f23`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140033f23`

## pseudocode

```c
BOOLEAN __fastcall IsCallingProcess(PSECURITY_DESCRIPTOR SecurityDescriptor, char a2)
{
  BOOLEAN v4; // bl
  PVOID TokenInformation; // [rsp+50h] [rbp-30h] BYREF
  PVOID P; // [rsp+58h] [rbp-28h] BYREF
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+60h] [rbp-20h] BYREF
  int AccessStatus; // [rsp+B0h] [rbp+30h] BYREF
  DWORD GrantedAccess; // [rsp+B8h] [rbp+38h] BYREF

  GrantedAccess = 0;
  AccessStatus = 0;
  TokenInformation = 0;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  v4 = 0;
  P = 0;
  SeCaptureSubjectContext(&SubjectContext);
  SeLockSubjectContext(&SubjectContext);
  AccessStatus = SeQueryInformationToken(SubjectContext.PrimaryToken, TokenAccessInformation, &TokenInformation);
  if ( AccessStatus >= 0 )
  {
    if ( !a2
      || !SubjectContext.ClientToken
      || (AccessStatus = SeQueryInformationToken(SubjectContext.ClientToken, TokenAccessInformation, &P),
          AccessStatus >= 0) )
    {
      v4 = SeAccessCheckFromState(
             SecurityDescriptor,
             (PTOKEN_ACCESS_INFORMATION)TokenInformation,
             (PTOKEN_ACCESS_INFORMATION)P,
             1u,
             0,
             0,
             &GenericMapping,
             1,
             &GrantedAccess,
             &AccessStatus);
    }
  }
  if ( TokenInformation )
    ExFreePoolWithTag(TokenInformation, 0);
  if ( P )
    ExFreePoolWithTag(P, 0);
  SeUnlockSubjectContext(&SubjectContext);
  SeReleaseSubjectContext(&SubjectContext);
  return v4;
}

```

## disassembly

```asm
0x140033edc  mov     [rsp-18h+arg_0], rbx
0x140033ee1  push    rbp
0x140033ee2  push    rsi
0x140033ee3  push    rdi
0x140033ee4  mov     rbp, rsp
0x140033ee7  sub     rsp, 80h
0x140033eee  xorps   xmm0, xmm0
0x140033ef1  mov     [rbp+arg_18], 0
0x140033ef8  mov     rsi, rcx
0x140033efb  mov     [rbp+arg_10], 0
0x140033f02  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x140033f06  mov     [rbp+TokenInformation], 0
0x140033f0e  movups  xmmword ptr [rbp+SubjectContext.ClientToken], xmm0
0x140033f12  mov     dil, dl
0x140033f15  xor     bl, bl
0x140033f17  movups  xmmword ptr [rbp+SubjectContext.PrimaryToken], xmm0
0x140033f1b  mov     [rbp+P], 0
0x140033f23  call    cs:__imp_SeCaptureSubjectContext
0x140033f2a  nop     dword ptr [rax+rax+00h]
0x140033f2f  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x140033f33  call    cs:__imp_SeLockSubjectContext
0x140033f3a  nop     dword ptr [rax+rax+00h]
0x140033f3f  mov     rcx, [rbp+SubjectContext.PrimaryToken]; Token
0x140033f43  lea     r8, [rbp+TokenInformation]; TokenInformation
0x140033f47  mov     edx, 16h; TokenInformationClass
0x140033f4c  call    cs:__imp_SeQueryInformationToken
0x140033f53  nop     dword ptr [rax+rax+00h]
0x140033f58  mov     [rbp+arg_10], eax
0x140033f5b  test    eax, eax
0x140033f5d  js      short loc_140033FDC
0x140033f5f  test    dil, dil
0x140033f62  jz      short loc_140033F89
0x140033f64  mov     rcx, [rbp+SubjectContext.ClientToken]; Token
0x140033f68  test    rcx, rcx
0x140033f6b  jz      short loc_140033F89
0x140033f6d  lea     r8, [rbp+P]; TokenInformation
0x140033f71  mov     edx, 16h; TokenInformationClass
0x140033f76  call    cs:__imp_SeQueryInformationToken
0x140033f7d  nop     dword ptr [rax+rax+00h]
0x140033f82  mov     [rbp+arg_10], eax
0x140033f85  test    eax, eax
0x140033f87  js      short loc_140033FDC
0x140033f89  mov     r8, [rbp+P]; ClientTokenInformation
0x140033f8d  lea     rax, [rbp+arg_10]
0x140033f91  mov     rdx, [rbp+TokenInformation]; PrimaryTokenInformation
0x140033f95  mov     r9d, 1; DesiredAccess
0x140033f9b  mov     [rsp+80h+AccessStatus], rax; AccessStatus
0x140033fa0  mov     rcx, rsi; SecurityDescriptor
0x140033fa3  lea     rax, [rbp+arg_18]
0x140033fa7  mov     [rsp+80h+GrantedAccess], rax; GrantedAccess
0x140033fac  lea     rax, GenericMapping
0x140033fb3  mov     [rsp+80h+AccessMode], 1; AccessMode
0x140033fb8  mov     [rsp+80h+GenericMapping], rax; GenericMapping
0x140033fbd  mov     [rsp+80h+Privileges], 0; Privileges
0x140033fc6  mov     [rsp+80h+PreviouslyGrantedAccess], 0; PreviouslyGrantedAccess
0x140033fce  call    cs:__imp_SeAccessCheckFromState
0x140033fd5  nop     dword ptr [rax+rax+00h]
0x140033fda  mov     bl, al
0x140033fdc  mov     rcx, [rbp+TokenInformation]; P
0x140033fe0  test    rcx, rcx
0x140033fe3  jz      short loc_140033FF3
0x140033fe5  xor     edx, edx; Tag
0x140033fe7  call    cs:__imp_ExFreePoolWithTag
0x140033fee  nop     dword ptr [rax+rax+00h]
0x140033ff3  mov     rcx, [rbp+P]; P
0x140033ff7  test    rcx, rcx
0x140033ffa  jz      short loc_14003400A
0x140033ffc  xor     edx, edx; Tag
0x140033ffe  call    cs:__imp_ExFreePoolWithTag
0x140034005  nop     dword ptr [rax+rax+00h]
0x14003400a  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x14003400e  call    cs:__imp_SeUnlockSubjectContext
0x140034015  nop     dword ptr [rax+rax+00h]
0x14003401a  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x14003401e  call    cs:__imp_SeReleaseSubjectContext
0x140034025  nop     dword ptr [rax+rax+00h]
0x14003402a  mov     al, bl
0x14003402c  mov     rbx, [rsp+80h+arg_0]
0x140034034  add     rsp, 80h
0x14003403b  pop     rdi
0x14003403c  pop     rsi
0x14003403d  pop     rbp
0x14003403e  retn
```
