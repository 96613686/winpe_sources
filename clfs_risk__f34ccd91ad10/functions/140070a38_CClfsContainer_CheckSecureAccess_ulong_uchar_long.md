# CClfsContainer::CheckSecureAccess(ulong,uchar &,long &)

- ea: `0x140070a38`
- end: `0x140070b56`
- name: `?CheckSecureAccess@CClfsContainer@@QEAAJKAEAEAEAJ@Z`
- size: `286`
- prototype: `int(CClfsContainer *__hidden this, unsigned int, unsigned __int8 *, int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14003a7cc`
- `0x140078d5c`

## callees

- `0x140070a38`
- `0x140070b5c`

## import_xrefs

- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140070ac1`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140070ac1`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140070a96`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140070a96`
- `ntoskrnl!SeLockSubjectContext` at `0x140070aa6`
- `ntoskrnl!SeLockSubjectContext` at `0x140070aa6`
- `ntoskrnl!SeAccessCheck` at `0x140070b03`
- `ntoskrnl!SeAccessCheck` at `0x140070b03`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140070b15`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140070b15`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140070b25`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140070b25`
- `ntoskrnl!ExFreePoolWithTag` at `0x140070b37`
- `ntoskrnl!ExFreePoolWithTag` at `0x140070b37`

## pseudocode

```c
__int64 __fastcall CClfsContainer::CheckSecureAccess(
        CClfsContainer *this,
        ACCESS_MASK a2,
        unsigned __int8 *a3,
        int *a4)
{
  __int64 result; // rax
  unsigned int v8; // edi
  KPROCESSOR_MODE AccessMode; // bl
  struct _GENERIC_MAPPING *GenericMapping; // rax
  DWORD GrantedAccess; // [rsp+50h] [rbp-9h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+58h] [rbp-1h] BYREF
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+60h] [rbp+7h] BYREF
  unsigned int v14; // [rsp+D0h] [rbp+77h] BYREF

  *a3 = 0;
  SecurityDescriptor = 0;
  v14 = 0;
  GrantedAccess = 0;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  result = CClfsContainer::QuerySecurityDescriptor(this, &SecurityDescriptor, &v14);
  v8 = result;
  if ( (int)result >= 0 )
  {
    SeCaptureSubjectContext(&SubjectContext);
    SeLockSubjectContext(&SubjectContext);
    AccessMode = *((_BYTE *)KeGetCurrentThread() + 562);
    GenericMapping = IoGetFileObjectGenericMapping();
    *a3 = SeAccessCheck(
            SecurityDescriptor,
            &SubjectContext,
            1u,
            a2,
            0,
            0,
            GenericMapping,
            AccessMode,
            &GrantedAccess,
            a4);
    SeUnlockSubjectContext(&SubjectContext);
    SeReleaseSubjectContext(&SubjectContext);
    ExFreePoolWithTag(SecurityDescriptor, 0);
    return v8;
  }
  return result;
}

```

## disassembly

```asm
0x140070a38  push    rbp
0x140070a3a  push    rbx
0x140070a3b  push    rsi
0x140070a3c  push    rdi
0x140070a3d  push    r14
0x140070a3f  push    r15
0x140070a41  lea     rbp, [rsp-2Fh]
0x140070a46  sub     rsp, 88h
0x140070a4d  xorps   xmm0, xmm0
0x140070a50  mov     byte ptr [r8], 0
0x140070a54  mov     rsi, r8
0x140070a57  mov     [rbp+57h+SecurityDescriptor], 0
0x140070a5f  mov     r15d, edx
0x140070a62  mov     [rbp+57h+arg_10], 0
0x140070a69  lea     r8, [rbp+57h+arg_10]; unsigned int *
0x140070a6d  mov     [rbp+57h+var_60], 0
0x140070a74  lea     rdx, [rbp+57h+SecurityDescriptor]; void **
0x140070a78  mov     r14, r9
0x140070a7b  movups  xmmword ptr [rbp+57h+SubjectContext.ClientToken], xmm0
0x140070a7f  movups  xmmword ptr [rbp+57h+SubjectContext.PrimaryToken], xmm0
0x140070a83  call    ?QuerySecurityDescriptor@CClfsContainer@@QEAAJAEAPEAXAEAK@Z; CClfsContainer::QuerySecurityDescriptor(void * &,ulong &)
0x140070a88  mov     edi, eax
0x140070a8a  test    eax, eax
0x140070a8c  js      loc_140070B45
0x140070a92  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x140070a96  call    cs:__imp_SeCaptureSubjectContext
0x140070a9d  nop     dword ptr [rax+rax+00h]
0x140070aa2  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x140070aa6  call    cs:__imp_SeLockSubjectContext
0x140070aad  nop     dword ptr [rax+rax+00h]
0x140070ab2  mov     rax, gs:188h
0x140070abb  mov     bl, [rax+232h]
0x140070ac1  call    cs:__imp_IoGetFileObjectGenericMapping
0x140070ac8  nop     dword ptr [rax+rax+00h]
0x140070acd  mov     [rsp+0B0h+AccessStatus], r14; AccessStatus
0x140070ad2  lea     rcx, [rbp+57h+var_60]
0x140070ad6  mov     [rsp+0B0h+GrantedAccess], rcx; GrantedAccess
0x140070adb  lea     rdx, [rbp+57h+SubjectContext]; SubjectSecurityContext
0x140070adf  mov     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x140070ae3  mov     r9d, r15d; DesiredAccess
0x140070ae6  mov     [rsp+0B0h+AccessMode], bl; AccessMode
0x140070aea  mov     r8b, 1; SubjectContextLocked
0x140070aed  mov     [rsp+0B0h+GenericMapping], rax; GenericMapping
0x140070af2  mov     [rsp+0B0h+Privileges], 0; Privileges
0x140070afb  mov     [rsp+0B0h+PreviouslyGrantedAccess], 0; PreviouslyGrantedAccess
0x140070b03  call    cs:__imp_SeAccessCheck
0x140070b0a  nop     dword ptr [rax+rax+00h]
0x140070b0f  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x140070b13  mov     [rsi], al
0x140070b15  call    cs:__imp_SeUnlockSubjectContext
0x140070b1c  nop     dword ptr [rax+rax+00h]
0x140070b21  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x140070b25  call    cs:__imp_SeReleaseSubjectContext
0x140070b2c  nop     dword ptr [rax+rax+00h]
0x140070b31  mov     rcx, [rbp+57h+SecurityDescriptor]; P
0x140070b35  xor     edx, edx; Tag
0x140070b37  call    cs:__imp_ExFreePoolWithTag
0x140070b3e  nop     dword ptr [rax+rax+00h]
0x140070b43  mov     eax, edi
0x140070b45  add     rsp, 88h
0x140070b4c  pop     r15
0x140070b4e  pop     r14
0x140070b50  pop     rdi
0x140070b51  pop     rsi
0x140070b52  pop     rbx
0x140070b53  pop     rbp
0x140070b54  retn
```
