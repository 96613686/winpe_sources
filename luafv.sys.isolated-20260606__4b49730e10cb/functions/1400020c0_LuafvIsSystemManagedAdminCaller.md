# LuafvIsSystemManagedAdminCaller

- ea: `0x1400020c0`
- end: `0x140002174`
- name: `LuafvIsSystemManagedAdminCaller`
- size: `180`
- prototype: `__int64 __fastcall(__int64, bool *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400258a0`

## callees

- `0x1400020c0`

## import_xrefs

- `ntoskrnl!SeQueryInformationToken` at `0x14000212f`
- `ntoskrnl!SeQueryInformationToken` at `0x14000212f`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140002147`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140002147`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14000210a`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14000210a`

## pseudocode

```c
__int64 __fastcall LuafvIsSystemManagedAdminCaller(__int64 a1, bool *a2)
{
  __int64 v3; // rax
  struct _SECURITY_SUBJECT_CONTEXT *p_SubjectContext; // rbx
  char v5; // di
  PACCESS_TOKEN ClientToken; // rcx
  NTSTATUS v7; // ebx
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+20h] [rbp-28h] BYREF
  PVOID TokenInformation; // [rsp+50h] [rbp+8h] BYREF

  LODWORD(TokenInformation) = 0;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  v3 = *(_QWORD *)(a1 + 16);
  if ( *(_BYTE *)(v3 + 4) )
  {
    p_SubjectContext = &SubjectContext;
    SeCaptureSubjectContext(&SubjectContext);
    v5 = 1;
  }
  else
  {
    p_SubjectContext = (struct _SECURITY_SUBJECT_CONTEXT *)(*(_QWORD *)(*(_QWORD *)(v3 + 24) + 8LL) + 32LL);
    v5 = 0;
  }
  ClientToken = p_SubjectContext->ClientToken;
  if ( !p_SubjectContext->ClientToken )
    ClientToken = p_SubjectContext->PrimaryToken;
  v7 = SeQueryInformationToken(ClientToken, TokenRestrictedUserClaimAttributes|TokenAuditPolicy, &TokenInformation);
  if ( v5 )
    SeReleaseSubjectContext(&SubjectContext);
  if ( v7 >= 0 )
    *a2 = (_DWORD)TokenInformation != 0;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1400020c0  mov     rax, rsp
0x1400020c3  mov     [rax+10h], rbx
0x1400020c7  mov     [rax+18h], rsi
0x1400020cb  push    rdi
0x1400020cc  sub     rsp, 40h
0x1400020d0  xorps   xmm0, xmm0
0x1400020d3  mov     dword ptr [rax+8], 0
0x1400020da  movups  xmmword ptr [rax-28h], xmm0
0x1400020de  mov     rsi, rdx
0x1400020e1  movups  xmmword ptr [rax-18h], xmm0
0x1400020e5  mov     rax, [rcx+10h]
0x1400020e9  cmp     byte ptr [rax+4], 0
0x1400020ed  jnz     short loc_140002100
0x1400020ef  mov     rax, [rax+18h]
0x1400020f3  mov     rbx, [rax+8]
0x1400020f7  add     rbx, 20h ; ' '
0x1400020fb  xor     dil, dil
0x1400020fe  jmp     short loc_140002119
0x140002100  lea     rcx, [rsp+48h+SubjectContext]; SubjectContext
0x140002105  lea     rbx, [rsp+48h+SubjectContext]
0x14000210a  call    cs:__imp_SeCaptureSubjectContext
0x140002111  nop     dword ptr [rax+rax+00h]
0x140002116  mov     dil, 1
0x140002119  mov     rcx, [rbx]
0x14000211c  test    rcx, rcx
0x14000211f  jnz     short loc_140002125
0x140002121  mov     rcx, [rbx+10h]; Token
0x140002125  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x14000212a  mov     edx, 33h ; '3'; TokenInformationClass
0x14000212f  call    cs:__imp_SeQueryInformationToken
0x140002136  nop     dword ptr [rax+rax+00h]
0x14000213b  mov     ebx, eax
0x14000213d  test    dil, dil
0x140002140  jz      short loc_140002153
0x140002142  lea     rcx, [rsp+48h+SubjectContext]; SubjectContext
0x140002147  call    cs:__imp_SeReleaseSubjectContext
0x14000214e  nop     dword ptr [rax+rax+00h]
0x140002153  test    ebx, ebx
0x140002155  js      short loc_140002161
0x140002157  cmp     dword ptr [rsp+48h+TokenInformation], 0
0x14000215c  setnz   cl
0x14000215f  mov     [rsi], cl
0x140002161  mov     rsi, [rsp+48h+arg_10]
0x140002166  mov     eax, ebx
0x140002168  mov     rbx, [rsp+48h+arg_8]
0x14000216d  add     rsp, 40h
0x140002171  pop     rdi
0x140002172  retn
```
