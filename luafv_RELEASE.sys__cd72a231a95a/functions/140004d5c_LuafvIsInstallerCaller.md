# LuafvIsInstallerCaller

- ea: `0x140004d5c`
- end: `0x140004e10`
- name: `LuafvIsInstallerCaller`
- size: `180`
- prototype: `__int64 __fastcall(__int64, bool *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1400041e8`

## callees

- `0x140004d5c`

## import_xrefs

- `ntoskrnl!SeQueryInformationToken` at `0x140004dcb`
- `ntoskrnl!SeQueryInformationToken` at `0x140004dcb`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140004de3`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140004de3`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140004da6`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140004da6`

## pseudocode

```c
__int64 __fastcall LuafvIsInstallerCaller(__int64 a1, bool *a2)
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
  v7 = SeQueryInformationToken(ClientToken, TokenDeviceGroups|TokenAuditPolicy, &TokenInformation);
  if ( v5 )
    SeReleaseSubjectContext(&SubjectContext);
  if ( v7 >= 0 )
    *a2 = (_DWORD)TokenInformation != 0;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140004d5c  mov     rax, rsp
0x140004d5f  mov     [rax+10h], rbx
0x140004d63  mov     [rax+18h], rsi
0x140004d67  push    rdi
0x140004d68  sub     rsp, 40h
0x140004d6c  xorps   xmm0, xmm0
0x140004d6f  mov     dword ptr [rax+8], 0
0x140004d76  movups  xmmword ptr [rax-28h], xmm0
0x140004d7a  mov     rsi, rdx
0x140004d7d  movups  xmmword ptr [rax-18h], xmm0
0x140004d81  mov     rax, [rcx+10h]
0x140004d85  cmp     byte ptr [rax+4], 0
0x140004d89  jnz     short loc_140004D9C
0x140004d8b  mov     rax, [rax+18h]
0x140004d8f  mov     rbx, [rax+8]
0x140004d93  add     rbx, 20h ; ' '
0x140004d97  xor     dil, dil
0x140004d9a  jmp     short loc_140004DB5
0x140004d9c  lea     rcx, [rsp+48h+SubjectContext]; SubjectContext
0x140004da1  lea     rbx, [rsp+48h+SubjectContext]
0x140004da6  call    cs:__imp_SeCaptureSubjectContext
0x140004dad  nop     dword ptr [rax+rax+00h]
0x140004db2  mov     dil, 1
0x140004db5  mov     rcx, [rbx]
0x140004db8  test    rcx, rcx
0x140004dbb  jnz     short loc_140004DC1
0x140004dbd  mov     rcx, [rbx+10h]; Token
0x140004dc1  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x140004dc6  mov     edx, 35h ; '5'; TokenInformationClass
0x140004dcb  call    cs:__imp_SeQueryInformationToken
0x140004dd2  nop     dword ptr [rax+rax+00h]
0x140004dd7  mov     ebx, eax
0x140004dd9  test    dil, dil
0x140004ddc  jz      short loc_140004DEF
0x140004dde  lea     rcx, [rsp+48h+SubjectContext]; SubjectContext
0x140004de3  call    cs:__imp_SeReleaseSubjectContext
0x140004dea  nop     dword ptr [rax+rax+00h]
0x140004def  test    ebx, ebx
0x140004df1  js      short loc_140004DFD
0x140004df3  cmp     dword ptr [rsp+48h+TokenInformation], 0
0x140004df8  setnz   cl
0x140004dfb  mov     [rsi], cl
0x140004dfd  mov     rsi, [rsp+48h+arg_10]
0x140004e02  mov     eax, ebx
0x140004e04  mov     rbx, [rsp+48h+arg_8]
0x140004e09  add     rsp, 40h
0x140004e0d  pop     rdi
0x140004e0e  retn
```
