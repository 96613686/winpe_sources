# PcwpAccessCheck(PCW_SILO_NEUTRAL_COUNTERSET const *,ulong)

- ea: `0x14000dd2c`
- end: `0x14000dded`
- name: `?PcwpAccessCheck@@YAJPEBVPCW_SILO_NEUTRAL_COUNTERSET@@K@Z`
- size: `193`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR *, ACCESS_MASK)`
- caller_count: `4`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000d660`
- `0x14000ddf4`
- `0x14000e3e8`
- `0x14000e8c0`

## import_xrefs

- `ntoskrnl!SeCaptureSubjectContext` at `0x14000dd5a`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14000dd5a`
- `ntoskrnl!SeAccessCheck` at `0x14000ddb1`
- `ntoskrnl!SeAccessCheck` at `0x14000ddb1`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14000ddc4`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14000ddc4`

## pseudocode

```c
__int64 __fastcall PcwpAccessCheck(PSECURITY_DESCRIPTOR *a1, ACCESS_MASK a2)
{
  __int64 result; // rax
  _SECURITY_SUBJECT_CONTEXT SubjectSecurityContext; // [rsp+50h] [rbp-28h] BYREF
  int AccessStatus; // [rsp+80h] [rbp+8h] BYREF
  DWORD GrantedAccess; // [rsp+90h] [rbp+18h] BYREF

  GrantedAccess = 0;
  AccessStatus = 0;
  memset(&SubjectSecurityContext, 0, sizeof(SubjectSecurityContext));
  SeCaptureSubjectContext(&SubjectSecurityContext);
  LOBYTE(a2) = SeAccessCheck(
                 a1[12],
                 &SubjectSecurityContext,
                 0,
                 a2,
                 0,
                 0,
                 &PcwCounterSetGenericMap,
                 1,
                 &GrantedAccess,
                 &AccessStatus);
  SeReleaseSubjectContext(&SubjectSecurityContext);
  result = (unsigned int)AccessStatus;
  if ( (_BYTE)a2 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x14000dd2c  mov     rax, rsp
0x14000dd2f  mov     [rax+10h], rbx
0x14000dd33  push    rdi
0x14000dd34  sub     rsp, 70h
0x14000dd38  xorps   xmm0, xmm0
0x14000dd3b  mov     dword ptr [rax+18h], 0
0x14000dd42  mov     rdi, rcx
0x14000dd45  mov     dword ptr [rax+8], 0
0x14000dd4c  lea     rcx, [rax-28h]; SubjectContext
0x14000dd50  mov     ebx, edx
0x14000dd52  movups  xmmword ptr [rax-28h], xmm0
0x14000dd56  movups  xmmword ptr [rax-18h], xmm0
0x14000dd5a  call    cs:__imp_SeCaptureSubjectContext
0x14000dd61  nop     dword ptr [rax+rax+00h]
0x14000dd66  mov     rcx, [rdi+60h]; SecurityDescriptor
0x14000dd6a  lea     rax, [rsp+78h+arg_0]
0x14000dd72  mov     [rsp+78h+AccessStatus], rax; AccessStatus
0x14000dd77  lea     rdx, [rsp+78h+SubjectSecurityContext]; SubjectSecurityContext
0x14000dd7c  lea     rax, [rsp+78h+arg_10]
0x14000dd84  mov     r9d, ebx; DesiredAccess
0x14000dd87  mov     [rsp+78h+GrantedAccess], rax; GrantedAccess
0x14000dd8c  xor     r8d, r8d; SubjectContextLocked
0x14000dd8f  mov     [rsp+78h+AccessMode], 1; AccessMode
0x14000dd94  lea     rax, ?PcwCounterSetGenericMap@@3U_GENERIC_MAPPING@@A; _GENERIC_MAPPING PcwCounterSetGenericMap
0x14000dd9b  mov     [rsp+78h+GenericMapping], rax; GenericMapping
0x14000dda0  mov     [rsp+78h+Privileges], 0; Privileges
0x14000dda9  mov     [rsp+78h+PreviouslyGrantedAccess], 0; PreviouslyGrantedAccess
0x14000ddb1  call    cs:__imp_SeAccessCheck
0x14000ddb8  nop     dword ptr [rax+rax+00h]
0x14000ddbd  lea     rcx, [rsp+78h+SubjectSecurityContext]; SubjectContext
0x14000ddc2  mov     bl, al
0x14000ddc4  call    cs:__imp_SeReleaseSubjectContext
0x14000ddcb  nop     dword ptr [rax+rax+00h]
0x14000ddd0  mov     eax, [rsp+78h+arg_0]
0x14000ddd7  xor     ecx, ecx
0x14000ddd9  test    bl, bl
0x14000dddb  mov     rbx, [rsp+78h+arg_8]
0x14000dde3  cmovnz  eax, ecx
0x14000dde6  add     rsp, 70h
0x14000ddea  pop     rdi
0x14000ddeb  retn
```
