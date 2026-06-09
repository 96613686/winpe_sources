# LuafvIsInstallerCaller

- ea: `0x140004b94`
- end: `0x140004c48`
- name: `LuafvIsInstallerCaller`
- size: `180`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140003fb8`

## callees

- `0x140004b94`

## import_xrefs

- `ntoskrnl!SeQueryInformationToken` at `0x140004c03`
- `ntoskrnl!SeQueryInformationToken` at `0x140004c03`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140004c1b`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140004c1b`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140004bde`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140004bde`

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
0x140004b94  mov     rax, rsp
0x140004b97  mov     [rax+10h], rbx
0x140004b9b  mov     [rax+18h], rsi
0x140004b9f  push    rdi
0x140004ba0  sub     rsp, 40h
0x140004ba4  xorps   xmm0, xmm0
0x140004ba7  mov     dword ptr [rax+8], 0
0x140004bae  movups  xmmword ptr [rax-28h], xmm0
0x140004bb2  mov     rsi, rdx
0x140004bb5  movups  xmmword ptr [rax-18h], xmm0
0x140004bb9  mov     rax, [rcx+10h]
0x140004bbd  cmp     byte ptr [rax+4], 0
0x140004bc1  jnz     short loc_140004BD4
0x140004bc3  mov     rax, [rax+18h]
0x140004bc7  mov     rbx, [rax+8]
0x140004bcb  add     rbx, 20h ; ' '
0x140004bcf  xor     dil, dil
0x140004bd2  jmp     short loc_140004BED
0x140004bd4  lea     rcx, [rsp+48h+SubjectContext]; SubjectContext
0x140004bd9  lea     rbx, [rsp+48h+SubjectContext]
0x140004bde  call    cs:__imp_SeCaptureSubjectContext
0x140004be5  nop     dword ptr [rax+rax+00h]
0x140004bea  mov     dil, 1
0x140004bed  mov     rcx, [rbx]
0x140004bf0  test    rcx, rcx
0x140004bf3  jnz     short loc_140004BF9
0x140004bf5  mov     rcx, [rbx+10h]; Token
0x140004bf9  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x140004bfe  mov     edx, 35h ; '5'; TokenInformationClass
0x140004c03  call    cs:__imp_SeQueryInformationToken
0x140004c0a  nop     dword ptr [rax+rax+00h]
0x140004c0f  mov     ebx, eax
0x140004c11  test    dil, dil
0x140004c14  jz      short loc_140004C27
0x140004c16  lea     rcx, [rsp+48h+SubjectContext]; SubjectContext
0x140004c1b  call    cs:__imp_SeReleaseSubjectContext
0x140004c22  nop     dword ptr [rax+rax+00h]
0x140004c27  test    ebx, ebx
0x140004c29  js      short loc_140004C35
0x140004c2b  cmp     dword ptr [rsp+48h+TokenInformation], 0
0x140004c30  setnz   cl
0x140004c33  mov     [rsi], cl
0x140004c35  mov     rsi, [rsp+48h+arg_10]
0x140004c3a  mov     eax, ebx
0x140004c3c  mov     rbx, [rsp+48h+arg_8]
0x140004c41  add     rsp, 40h
0x140004c45  pop     rdi
0x140004c46  retn
```
