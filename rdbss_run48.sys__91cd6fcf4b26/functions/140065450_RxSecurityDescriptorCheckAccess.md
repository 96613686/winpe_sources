# RxSecurityDescriptorCheckAccess

- ea: `0x140065450`
- end: `0x14006556c`
- name: `RxSecurityDescriptorCheckAccess`
- size: `284`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR SecurityDescriptor)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140063990`

## callees

- `0x140025c20`
- `0x140065450`

## import_xrefs

- `ntoskrnl!SeCaptureSubjectContext` at `0x1400654af`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1400654af`
- `ntoskrnl!SeAccessCheck` at `0x1400654f8`
- `ntoskrnl!SeAccessCheck` at `0x1400654f8`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x140065555`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x140065555`
- `ntoskrnl!SeExports` at `0x140065545`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140065513`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140065513`

## pseudocode

```c
__int64 __fastcall RxSecurityDescriptorCheckAccess(PSECURITY_DESCRIPTOR SecurityDescriptor)
{
  int v2; // eax
  int AccessStatus; // [rsp+50h] [rbp-48h] BYREF
  DWORD GrantedAccess; // [rsp+54h] [rbp-44h] BYREF
  struct _SECURITY_SUBJECT_CONTEXT SubjectSecurityContext; // [rsp+58h] [rbp-40h] BYREF
  struct _GENERIC_MAPPING GenericMapping; // [rsp+78h] [rbp-20h] BYREF

  GenericMapping.GenericRead = 1179785;
  GenericMapping.GenericWrite = 1179926;
  GenericMapping.GenericExecute = 1179808;
  AccessStatus = 0;
  memset(&SubjectSecurityContext, 0, sizeof(SubjectSecurityContext));
  GrantedAccess = 0;
  GenericMapping.GenericAll = 2032127;
  SeCaptureSubjectContext(&SubjectSecurityContext);
  if ( SeAccessCheck(
         SecurityDescriptor,
         &SubjectSecurityContext,
         0,
         1u,
         0,
         0,
         &GenericMapping,
         1,
         &GrantedAccess,
         &AccessStatus)
    || SeSinglePrivilegeCheck(SeExports->SeLoadDriverPrivilege, 1) )
  {
    v2 = 0;
  }
  else
  {
    v2 = -1073741790;
  }
  AccessStatus = v2;
  SeReleaseSubjectContext(&SubjectSecurityContext);
  return (unsigned int)AccessStatus;
}

```

## disassembly

```asm
0x140065450  mov     r11, rsp
0x140065453  mov     [r11+10h], rbx
0x140065457  push    rdi
0x140065458  sub     rsp, 90h
0x14006545f  mov     rax, cs:__security_cookie
0x140065466  xor     rax, rsp
0x140065469  mov     [rsp+98h+var_10], rax
0x140065471  xorps   xmm0, xmm0
0x140065474  mov     [rsp+98h+var_20.GenericRead], 120089h
0x14006547c  mov     [rsp+98h+var_20.GenericWrite], 120116h
0x140065484  mov     rbx, rcx
0x140065487  xor     edi, edi
0x140065489  mov     dword ptr [r11-18h], 1200A0h
0x140065491  lea     rcx, [r11-40h]; SubjectContext
0x140065495  mov     [rsp+98h+var_48], edi
0x140065499  movups  xmmword ptr [rsp+98h+SubjectSecurityContext.ClientToken], xmm0
0x14006549e  mov     [rsp+98h+var_44], edi
0x1400654a2  movups  xmmword ptr [rsp+98h+SubjectSecurityContext.PrimaryToken], xmm0
0x1400654a7  mov     dword ptr [r11-14h], 1F01FFh
0x1400654af  call    cs:__imp_SeCaptureSubjectContext
0x1400654b6  nop     dword ptr [rax+rax+00h]
0x1400654bb  lea     rax, [rsp+98h+var_48]
0x1400654c0  mov     r9d, 1; DesiredAccess
0x1400654c6  mov     [rsp+98h+AccessStatus], rax; AccessStatus
0x1400654cb  lea     rdx, [rsp+98h+SubjectSecurityContext]; SubjectSecurityContext
0x1400654d0  lea     rax, [rsp+98h+var_44]
0x1400654d5  xor     r8d, r8d; SubjectContextLocked
0x1400654d8  mov     [rsp+98h+GrantedAccess], rax; GrantedAccess
0x1400654dd  mov     rcx, rbx; SecurityDescriptor
0x1400654e0  mov     [rsp+98h+AccessMode], 1; AccessMode
0x1400654e5  lea     rax, [rsp+98h+var_20]
0x1400654ea  mov     [rsp+98h+GenericMapping], rax; GenericMapping
0x1400654ef  mov     [rsp+98h+Privileges], rdi; Privileges
0x1400654f4  mov     [rsp+98h+PreviouslyGrantedAccess], edi; PreviouslyGrantedAccess
0x1400654f8  call    cs:__imp_SeAccessCheck
0x1400654ff  nop     dword ptr [rax+rax+00h]
0x140065504  test    al, al
0x140065506  jz      short loc_140065545
0x140065508  mov     eax, edi
0x14006550a  lea     rcx, [rsp+98h+SubjectSecurityContext]; SubjectContext
0x14006550f  mov     [rsp+98h+var_48], eax
0x140065513  call    cs:__imp_SeReleaseSubjectContext
0x14006551a  nop     dword ptr [rax+rax+00h]
0x14006551f  mov     eax, [rsp+98h+var_48]
0x140065523  mov     rcx, [rsp+98h+var_10]
0x14006552b  xor     rcx, rsp; StackCookie
0x14006552e  call    __security_check_cookie
0x140065533  mov     rbx, [rsp+98h+arg_8]
0x14006553b  add     rsp, 90h
0x140065542  pop     rdi
0x140065543  retn
0x140065545  mov     rax, cs:__imp_SeExports
0x14006554c  mov     dl, 1; PreviousMode
0x14006554e  mov     rcx, [rax]
0x140065551  mov     rcx, [rcx+40h]; PrivilegeValue
0x140065555  call    cs:__imp_SeSinglePrivilegeCheck
0x14006555c  nop     dword ptr [rax+rax+00h]
0x140065561  test    al, al
0x140065563  jnz     short loc_140065508
0x140065565  mov     eax, 0C0000022h
0x14006556a  jmp     short loc_14006550A
```
