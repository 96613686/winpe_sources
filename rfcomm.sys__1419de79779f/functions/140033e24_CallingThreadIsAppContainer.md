# CallingThreadIsAppContainer

- ea: `0x140033e24`
- end: `0x140033ed4`
- name: `CallingThreadIsAppContainer`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000b5b0`

## callees

- `0x140033e24`

## import_xrefs

- `ntoskrnl!SeQueryInformationToken` at `0x140033e88`
- `ntoskrnl!SeQueryInformationToken` at `0x140033e88`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140033eba`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140033eba`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140033ea9`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140033ea9`
- `ntoskrnl!SeLockSubjectContext` at `0x140033e59`
- `ntoskrnl!SeLockSubjectContext` at `0x140033e59`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140033e48`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140033e48`

## pseudocode

```c
__int64 __fastcall CallingThreadIsAppContainer(char a1, bool *a2)
{
  void *PrimaryToken; // rcx
  NTSTATUS v4; // ebx
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+20h] [rbp-28h] BYREF
  PVOID TokenInformation; // [rsp+50h] [rbp+8h] BYREF

  LOBYTE(TokenInformation) = a1;
  *a2 = 0;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  SeCaptureSubjectContext(&SubjectContext);
  SeLockSubjectContext(&SubjectContext);
  PrimaryToken = SubjectContext.PrimaryToken;
  LODWORD(TokenInformation) = 0;
  if ( SubjectContext.ClientToken )
    PrimaryToken = SubjectContext.ClientToken;
  v4 = SeQueryInformationToken(PrimaryToken, TokenIsAppContainer, &TokenInformation);
  if ( v4 >= 0 )
    *a2 = (_DWORD)TokenInformation != 0;
  SeUnlockSubjectContext(&SubjectContext);
  SeReleaseSubjectContext(&SubjectContext);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140033e24  mov     rax, rsp
0x140033e27  mov     [rax+10h], rbx
0x140033e2b  mov     [rax+8], cl
0x140033e2e  push    rdi
0x140033e2f  sub     rsp, 40h
0x140033e33  xorps   xmm0, xmm0
0x140033e36  mov     byte ptr [rdx], 0
0x140033e39  lea     rcx, [rax-28h]; SubjectContext
0x140033e3d  mov     rdi, rdx
0x140033e40  movups  xmmword ptr [rax-28h], xmm0
0x140033e44  movups  xmmword ptr [rax-18h], xmm0
0x140033e48  call    cs:__imp_SeCaptureSubjectContext
0x140033e4f  nop     dword ptr [rax+rax+00h]
0x140033e54  lea     rcx, [rsp+48h+SubjectContext]; SubjectContext
0x140033e59  call    cs:__imp_SeLockSubjectContext
0x140033e60  nop     dword ptr [rax+rax+00h]
0x140033e65  mov     rax, [rsp+48h+SubjectContext.ClientToken]
0x140033e6a  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x140033e6f  mov     rcx, [rsp+48h+SubjectContext.PrimaryToken]
0x140033e74  test    rax, rax
0x140033e77  mov     edx, 1Dh; TokenInformationClass
0x140033e7c  mov     dword ptr [rsp+48h+TokenInformation], 0
0x140033e84  cmovnz  rcx, rax; Token
0x140033e88  call    cs:__imp_SeQueryInformationToken
0x140033e8f  nop     dword ptr [rax+rax+00h]
0x140033e94  mov     ebx, eax
0x140033e96  test    eax, eax
0x140033e98  js      short loc_140033EA4
0x140033e9a  cmp     dword ptr [rsp+48h+TokenInformation], 0
0x140033e9f  setnz   cl
0x140033ea2  mov     [rdi], cl
0x140033ea4  lea     rcx, [rsp+48h+SubjectContext]; SubjectContext
0x140033ea9  call    cs:__imp_SeUnlockSubjectContext
0x140033eb0  nop     dword ptr [rax+rax+00h]
0x140033eb5  lea     rcx, [rsp+48h+SubjectContext]; SubjectContext
0x140033eba  call    cs:__imp_SeReleaseSubjectContext
0x140033ec1  nop     dword ptr [rax+rax+00h]
0x140033ec6  mov     eax, ebx
0x140033ec8  mov     rbx, [rsp+48h+arg_8]
0x140033ecd  add     rsp, 40h
0x140033ed1  pop     rdi
0x140033ed2  retn
```
