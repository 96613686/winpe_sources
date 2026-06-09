# MRxSmbCheckDevFcbXXXControlFileAccess

- ea: `0x140091690`
- end: `0x1400917bd`
- name: `MRxSmbCheckDevFcbXXXControlFileAccess`
- size: `301`
- prototype: `__int64 __fastcall(ACCESS_MASK DesiredAccess)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001f0e0`
- `0x140039644`
- `0x140039b38`

## callees

- `0x140059dc0`
- `0x140091690`

## import_xrefs

- `ntoskrnl!SeReleaseSubjectContext` at `0x140091764`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140091764`
- `ntoskrnl!SeExports` at `0x14009179a`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x1400917aa`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x1400917aa`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1400916c3`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1400916c3`
- `ntoskrnl!SeAccessCheck` at `0x140091741`
- `ntoskrnl!SeAccessCheck` at `0x140091741`

## pseudocode

```c
__int64 __fastcall MRxSmbCheckDevFcbXXXControlFileAccess(ACCESS_MASK DesiredAccess)
{
  unsigned int v2; // ebx
  int AccessStatus; // [rsp+50h] [rbp-48h] BYREF
  DWORD GrantedAccess; // [rsp+54h] [rbp-44h] BYREF
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+58h] [rbp-40h] BYREF
  struct _GENERIC_MAPPING GenericMapping; // [rsp+78h] [rbp-20h] BYREF

  memset(&SubjectContext, 0, sizeof(SubjectContext));
  SeCaptureSubjectContext(&SubjectContext);
  AccessStatus = -1073741790;
  GrantedAccess = 0;
  GenericMapping.GenericRead = 1179785;
  GenericMapping.GenericWrite = 1179926;
  GenericMapping.GenericExecute = 1179808;
  GenericMapping.GenericAll = 2032127;
  if ( SeAccessCheck(
         qword_140099008,
         &SubjectContext,
         0,
         DesiredAccess,
         0,
         0,
         &GenericMapping,
         1,
         &GrantedAccess,
         &AccessStatus) )
  {
    v2 = 0;
    AccessStatus = 0;
  }
  else
  {
    v2 = AccessStatus;
  }
  if ( v2 == -1073741790 && SeSinglePrivilegeCheck(SeExports->SeTcbPrivilege, 1) )
    v2 = 0;
  SeReleaseSubjectContext(&SubjectContext);
  return v2;
}

```

## disassembly

```asm
0x140091690  mov     [rsp+arg_8], rbx
0x140091695  push    rdi
0x140091696  sub     rsp, 90h
0x14009169d  mov     rax, cs:__security_cookie
0x1400916a4  xor     rax, rsp
0x1400916a7  mov     [rsp+98h+var_10], rax
0x1400916af  xorps   xmm0, xmm0
0x1400916b2  mov     ebx, ecx
0x1400916b4  lea     rcx, [rsp+98h+SubjectContext]; SubjectContext
0x1400916b9  movups  xmmword ptr [rsp+98h+SubjectContext.ClientToken], xmm0
0x1400916be  movups  xmmword ptr [rsp+98h+SubjectContext.PrimaryToken], xmm0
0x1400916c3  call    cs:__imp_SeCaptureSubjectContext
0x1400916ca  nop     dword ptr [rax+rax+00h]
0x1400916cf  xor     edi, edi
0x1400916d1  mov     [rsp+98h+var_48], 0C0000022h
0x1400916d9  lea     rax, [rsp+98h+var_48]
0x1400916de  mov     [rsp+98h+var_44], edi
0x1400916e2  mov     [rsp+98h+AccessStatus], rax; AccessStatus
0x1400916e7  lea     rdx, [rsp+98h+SubjectContext]; SubjectSecurityContext
0x1400916ec  lea     rax, [rsp+98h+var_44]
0x1400916f1  mov     [rsp+98h+var_20.GenericRead], 120089h
0x1400916f9  mov     [rsp+98h+GrantedAccess], rax; GrantedAccess
0x1400916fe  lea     rcx, qword_140099008; SecurityDescriptor
0x140091705  mov     [rsp+98h+AccessMode], 1; AccessMode
0x14009170a  lea     rax, [rsp+98h+var_20]
0x14009170f  mov     [rsp+98h+GenericMapping], rax; GenericMapping
0x140091714  mov     r9d, ebx; DesiredAccess
0x140091717  mov     [rsp+98h+Privileges], rdi; Privileges
0x14009171c  xor     r8d, r8d; SubjectContextLocked
0x14009171f  mov     [rsp+98h+PreviouslyGrantedAccess], edi; PreviouslyGrantedAccess
0x140091723  mov     [rsp+98h+var_20.GenericWrite], 120116h
0x14009172b  mov     [rsp+98h+var_20.GenericExecute], 1200A0h
0x140091736  mov     [rsp+98h+var_20.GenericAll], 1F01FFh
0x140091741  call    cs:__imp_SeAccessCheck
0x140091748  nop     dword ptr [rax+rax+00h]
0x14009174d  test    al, al
0x14009174f  jz      short loc_140091794
0x140091751  mov     ebx, edi
0x140091753  mov     [rsp+98h+var_48], ebx
0x140091757  cmp     ebx, 0C0000022h
0x14009175d  jz      short loc_14009179A
0x14009175f  lea     rcx, [rsp+98h+SubjectContext]; SubjectContext
0x140091764  call    cs:__imp_SeReleaseSubjectContext
0x14009176b  nop     dword ptr [rax+rax+00h]
0x140091770  mov     eax, ebx
0x140091772  mov     rcx, [rsp+98h+var_10]
0x14009177a  xor     rcx, rsp; StackCookie
0x14009177d  call    __security_check_cookie
0x140091782  mov     rbx, [rsp+98h+arg_8]
0x14009178a  add     rsp, 90h
0x140091791  pop     rdi
0x140091792  retn
0x140091794  mov     ebx, [rsp+98h+var_48]
0x140091798  jmp     short loc_140091757
0x14009179a  mov     rax, cs:__imp_SeExports
0x1400917a1  mov     dl, 1; PreviousMode
0x1400917a3  mov     rcx, [rax]
0x1400917a6  mov     rcx, [rcx+28h]; PrivilegeValue
0x1400917aa  call    cs:__imp_SeSinglePrivilegeCheck
0x1400917b1  nop     dword ptr [rax+rax+00h]
0x1400917b6  test    al, al
0x1400917b8  cmovnz  ebx, edi
0x1400917bb  jmp     short loc_14009175F
```
