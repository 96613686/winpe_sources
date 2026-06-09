# MRxSmbCheckDevFcbXXXControlFileAccess

- ea: `0x140091640`
- end: `0x14009176d`
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
- `0x140091640`

## import_xrefs

- `ntoskrnl!SeReleaseSubjectContext` at `0x140091714`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140091714`
- `ntoskrnl!SeExports` at `0x14009174a`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x14009175a`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x14009175a`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140091673`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140091673`
- `ntoskrnl!SeAccessCheck` at `0x1400916f1`
- `ntoskrnl!SeAccessCheck` at `0x1400916f1`

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
0x140091640  mov     [rsp+arg_8], rbx
0x140091645  push    rdi
0x140091646  sub     rsp, 90h
0x14009164d  mov     rax, cs:__security_cookie
0x140091654  xor     rax, rsp
0x140091657  mov     [rsp+98h+var_10], rax
0x14009165f  xorps   xmm0, xmm0
0x140091662  mov     ebx, ecx
0x140091664  lea     rcx, [rsp+98h+SubjectContext]; SubjectContext
0x140091669  movups  xmmword ptr [rsp+98h+SubjectContext.ClientToken], xmm0
0x14009166e  movups  xmmword ptr [rsp+98h+SubjectContext.PrimaryToken], xmm0
0x140091673  call    cs:__imp_SeCaptureSubjectContext
0x14009167a  nop     dword ptr [rax+rax+00h]
0x14009167f  xor     edi, edi
0x140091681  mov     [rsp+98h+var_48], 0C0000022h
0x140091689  lea     rax, [rsp+98h+var_48]
0x14009168e  mov     [rsp+98h+var_44], edi
0x140091692  mov     [rsp+98h+AccessStatus], rax; AccessStatus
0x140091697  lea     rdx, [rsp+98h+SubjectContext]; SubjectSecurityContext
0x14009169c  lea     rax, [rsp+98h+var_44]
0x1400916a1  mov     [rsp+98h+var_20.GenericRead], 120089h
0x1400916a9  mov     [rsp+98h+GrantedAccess], rax; GrantedAccess
0x1400916ae  lea     rcx, qword_140099008; SecurityDescriptor
0x1400916b5  mov     [rsp+98h+AccessMode], 1; AccessMode
0x1400916ba  lea     rax, [rsp+98h+var_20]
0x1400916bf  mov     [rsp+98h+GenericMapping], rax; GenericMapping
0x1400916c4  mov     r9d, ebx; DesiredAccess
0x1400916c7  mov     [rsp+98h+Privileges], rdi; Privileges
0x1400916cc  xor     r8d, r8d; SubjectContextLocked
0x1400916cf  mov     [rsp+98h+PreviouslyGrantedAccess], edi; PreviouslyGrantedAccess
0x1400916d3  mov     [rsp+98h+var_20.GenericWrite], 120116h
0x1400916db  mov     [rsp+98h+var_20.GenericExecute], 1200A0h
0x1400916e6  mov     [rsp+98h+var_20.GenericAll], 1F01FFh
0x1400916f1  call    cs:__imp_SeAccessCheck
0x1400916f8  nop     dword ptr [rax+rax+00h]
0x1400916fd  test    al, al
0x1400916ff  jz      short loc_140091744
0x140091701  mov     ebx, edi
0x140091703  mov     [rsp+98h+var_48], ebx
0x140091707  cmp     ebx, 0C0000022h
0x14009170d  jz      short loc_14009174A
0x14009170f  lea     rcx, [rsp+98h+SubjectContext]; SubjectContext
0x140091714  call    cs:__imp_SeReleaseSubjectContext
0x14009171b  nop     dword ptr [rax+rax+00h]
0x140091720  mov     eax, ebx
0x140091722  mov     rcx, [rsp+98h+var_10]
0x14009172a  xor     rcx, rsp; StackCookie
0x14009172d  call    __security_check_cookie
0x140091732  mov     rbx, [rsp+98h+arg_8]
0x14009173a  add     rsp, 90h
0x140091741  pop     rdi
0x140091742  retn
0x140091744  mov     ebx, [rsp+98h+var_48]
0x140091748  jmp     short loc_140091707
0x14009174a  mov     rax, cs:__imp_SeExports
0x140091751  mov     dl, 1; PreviousMode
0x140091753  mov     rcx, [rax]
0x140091756  mov     rcx, [rcx+28h]; PrivilegeValue
0x14009175a  call    cs:__imp_SeSinglePrivilegeCheck
0x140091761  nop     dword ptr [rax+rax+00h]
0x140091766  test    al, al
0x140091768  cmovnz  ebx, edi
0x14009176b  jmp     short loc_14009170F
```
