# LuafvIsSystemManagedAdminCaller

- ea: `0x140002348`
- end: `0x1400023fc`
- name: `LuafvIsSystemManagedAdminCaller`
- size: `180`
- prototype: `__int64 __fastcall(__int64, bool *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140025820`

## callees

- `0x140002348`

## import_xrefs

- `ntoskrnl!SeQueryInformationToken` at `0x1400023b7`
- `ntoskrnl!SeQueryInformationToken` at `0x1400023b7`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1400023cf`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1400023cf`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140002392`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140002392`

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
0x140002348  mov     rax, rsp
0x14000234b  mov     [rax+10h], rbx
0x14000234f  mov     [rax+18h], rsi
0x140002353  push    rdi
0x140002354  sub     rsp, 40h
0x140002358  xorps   xmm0, xmm0
0x14000235b  mov     dword ptr [rax+8], 0
0x140002362  movups  xmmword ptr [rax-28h], xmm0
0x140002366  mov     rsi, rdx
0x140002369  movups  xmmword ptr [rax-18h], xmm0
0x14000236d  mov     rax, [rcx+10h]
0x140002371  cmp     byte ptr [rax+4], 0
0x140002375  jnz     short loc_140002388
0x140002377  mov     rax, [rax+18h]
0x14000237b  mov     rbx, [rax+8]
0x14000237f  add     rbx, 20h ; ' '
0x140002383  xor     dil, dil
0x140002386  jmp     short loc_1400023A1
0x140002388  lea     rcx, [rsp+48h+SubjectContext]; SubjectContext
0x14000238d  lea     rbx, [rsp+48h+SubjectContext]
0x140002392  call    cs:__imp_SeCaptureSubjectContext
0x140002399  nop     dword ptr [rax+rax+00h]
0x14000239e  mov     dil, 1
0x1400023a1  mov     rcx, [rbx]
0x1400023a4  test    rcx, rcx
0x1400023a7  jnz     short loc_1400023AD
0x1400023a9  mov     rcx, [rbx+10h]; Token
0x1400023ad  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x1400023b2  mov     edx, 33h ; '3'; TokenInformationClass
0x1400023b7  call    cs:__imp_SeQueryInformationToken
0x1400023be  nop     dword ptr [rax+rax+00h]
0x1400023c3  mov     ebx, eax
0x1400023c5  test    dil, dil
0x1400023c8  jz      short loc_1400023DB
0x1400023ca  lea     rcx, [rsp+48h+SubjectContext]; SubjectContext
0x1400023cf  call    cs:__imp_SeReleaseSubjectContext
0x1400023d6  nop     dword ptr [rax+rax+00h]
0x1400023db  test    ebx, ebx
0x1400023dd  js      short loc_1400023E9
0x1400023df  cmp     dword ptr [rsp+48h+TokenInformation], 0
0x1400023e4  setnz   cl
0x1400023e7  mov     [rsi], cl
0x1400023e9  mov     rsi, [rsp+48h+arg_10]
0x1400023ee  mov     eax, ebx
0x1400023f0  mov     rbx, [rsp+48h+arg_8]
0x1400023f5  add     rsp, 40h
0x1400023f9  pop     rdi
0x1400023fa  retn
```
