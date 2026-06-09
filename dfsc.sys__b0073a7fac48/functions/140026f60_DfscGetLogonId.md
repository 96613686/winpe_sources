# DfscGetLogonId

- ea: `0x140026f60`
- end: `0x140026fc1`
- name: `DfscGetLogonId`
- size: `97`
- prototype: `__int64 __fastcall(PLUID AuthenticationId)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000141c`
- `0x14001338c`
- `0x140013a00`
- `0x140017a64`

## callees

- `0x140026f60`

## import_xrefs

- `ntoskrnl!SeCaptureSubjectContext` at `0x140026f7b`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140026f7b`
- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x140026f99`
- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x140026f99`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140026fac`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140026fac`

## pseudocode

```c
__int64 __fastcall DfscGetLogonId(PLUID AuthenticationId)
{
  PACCESS_TOKEN ClientToken; // rcx
  unsigned int AuthenticationIdToken; // ebx
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+20h] [rbp-28h] BYREF

  memset(&SubjectContext, 0, sizeof(SubjectContext));
  SeCaptureSubjectContext(&SubjectContext);
  ClientToken = SubjectContext.ClientToken;
  if ( !SubjectContext.ClientToken )
    ClientToken = SubjectContext.PrimaryToken;
  AuthenticationIdToken = SeQueryAuthenticationIdToken(ClientToken, AuthenticationId);
  SeReleaseSubjectContext(&SubjectContext);
  return AuthenticationIdToken;
}

```

## disassembly

```asm
0x140026f60  push    rbx
0x140026f62  sub     rsp, 40h
0x140026f66  xorps   xmm0, xmm0
0x140026f69  mov     rbx, rcx
0x140026f6c  lea     rcx, [rsp+48h+SubjectContext]; SubjectContext
0x140026f71  movups  xmmword ptr [rsp+48h+SubjectContext.ClientToken], xmm0
0x140026f76  movups  xmmword ptr [rsp+48h+SubjectContext.PrimaryToken], xmm0
0x140026f7b  call    cs:__imp_SeCaptureSubjectContext
0x140026f82  nop     dword ptr [rax+rax+00h]
0x140026f87  mov     rcx, [rsp+48h+SubjectContext.ClientToken]
0x140026f8c  mov     rdx, rbx; AuthenticationId
0x140026f8f  test    rcx, rcx
0x140026f92  jnz     short loc_140026F99
0x140026f94  mov     rcx, [rsp+48h+SubjectContext.PrimaryToken]; Token
0x140026f99  call    cs:__imp_SeQueryAuthenticationIdToken
0x140026fa0  nop     dword ptr [rax+rax+00h]
0x140026fa5  lea     rcx, [rsp+48h+SubjectContext]; SubjectContext
0x140026faa  mov     ebx, eax
0x140026fac  call    cs:__imp_SeReleaseSubjectContext
0x140026fb3  nop     dword ptr [rax+rax+00h]
0x140026fb8  mov     eax, ebx
0x140026fba  add     rsp, 40h
0x140026fbe  pop     rbx
0x140026fbf  retn
```
