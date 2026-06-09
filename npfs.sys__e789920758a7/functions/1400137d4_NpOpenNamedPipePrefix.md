# NpOpenNamedPipePrefix

- ea: `0x1400137d4`
- end: `0x140013993`
- name: `NpOpenNamedPipePrefix`
- size: `447`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, struct _ACCESS_STATE *, ACCESS_MASK DesiredAccess, KPROCESSOR_MODE AccessMode)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140011490`

## callees

- `0x140012730`
- `0x1400137d4`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140013810`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140013810`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140013828`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140013828`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14001392f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14001392f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001393b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001393b`
- `ntoskrnl!SeAppendPrivileges` at `0x1400138e8`
- `ntoskrnl!SeAppendPrivileges` at `0x1400138e8`
- `ntoskrnl!SeFreePrivileges` at `0x1400138f8`
- `ntoskrnl!SeFreePrivileges` at `0x1400138f8`
- `ntoskrnl!SeAccessCheck` at `0x1400138ce`
- `ntoskrnl!SeAccessCheck` at `0x1400138ce`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140013886`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140013886`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14001391a`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14001391a`
- `ntoskrnl!SeLockSubjectContext` at `0x140013873`
- `ntoskrnl!SeLockSubjectContext` at `0x140013873`

## pseudocode

```c
__int64 __fastcall NpOpenNamedPipePrefix(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        struct _ACCESS_STATE *a4,
        ACCESS_MASK DesiredAccess,
        KPROCESSOR_MODE AccessMode)
{
  __int64 v10; // r13
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 Prefix; // rdi
  void *v14; // rbx
  struct _GENERIC_MAPPING *GenericMapping; // rax
  BOOLEAN v16; // bl
  DWORD v17; // eax
  __int128 v19; // [rsp+50h] [rbp-10h] BYREF
  int AccessStatus; // [rsp+A0h] [rbp+40h] BYREF
  DWORD GrantedAccess; // [rsp+A8h] [rbp+48h] BYREF
  PPRIVILEGE_SET Privileges; // [rsp+B0h] [rbp+50h] BYREF

  *(_OWORD *)a1 = 0;
  AccessStatus = 0;
  v19 = 0;
  GrantedAccess = 0;
  Privileges = 0;
  KeEnterCriticalRegion();
  v10 = a2 + 192;
  ExAcquirePushLockExclusiveEx(a2 + 192, 0, v11, v12);
  Prefix = NpFindPrefix(a2, a3 + 88, 0, &v19);
  if ( Prefix && *(_WORD *)Prefix == 515 && !(_WORD)v19 )
  {
    SeLockSubjectContext(&a4->SubjectSecurityContext);
    v14 = *(void **)(Prefix + 152);
    GenericMapping = IoGetFileObjectGenericMapping();
    v16 = SeAccessCheck(
            v14,
            &a4->SubjectSecurityContext,
            1u,
            DesiredAccess,
            0,
            &Privileges,
            GenericMapping,
            AccessMode,
            &GrantedAccess,
            &AccessStatus);
    if ( Privileges )
    {
      SeAppendPrivileges(a4, Privileges);
      SeFreePrivileges(Privileges);
    }
    if ( v16 )
    {
      v17 = GrantedAccess;
      a4->PreviouslyGrantedAccess |= GrantedAccess;
      a4->RemainingDesiredAccess &= ~(v17 | 0x2000000);
    }
    SeUnlockSubjectContext(&a4->SubjectSecurityContext);
    if ( v16 )
    {
      ++*(_DWORD *)(Prefix + 120);
      _InterlockedAdd((volatile signed __int32 *)(Prefix + 124), 1u);
      *(_QWORD *)(a3 + 24) = Prefix;
      *(_QWORD *)(a3 + 32) = 1;
      AccessStatus = 0;
      *(_QWORD *)(a1 + 8) = 1;
    }
  }
  else
  {
    AccessStatus = -1073741772;
  }
  ExReleasePushLockExclusiveEx(v10, 0);
  KeLeaveCriticalRegion();
  *(_DWORD *)a1 = AccessStatus;
  return a1;
}

```

## disassembly

```asm
0x1400137d4  mov     [rsp-38h+arg_18], rbx
0x1400137d9  push    rbp
0x1400137da  push    rsi
0x1400137db  push    rdi
0x1400137dc  push    r12
0x1400137de  push    r13
0x1400137e0  push    r14
0x1400137e2  push    r15
0x1400137e4  mov     rbp, rsp
0x1400137e7  sub     rsp, 60h
0x1400137eb  xorps   xmm0, xmm0
0x1400137ee  xor     r12d, r12d
0x1400137f1  movups  xmmword ptr [rcx], xmm0
0x1400137f4  mov     [rbp+arg_0], r12d
0x1400137f8  mov     rsi, r9
0x1400137fb  movups  [rbp+var_10], xmm0
0x1400137ff  mov     [rbp+arg_8], r12d
0x140013803  mov     r15, r8
0x140013806  mov     [rbp+arg_10], r12
0x14001380a  mov     rbx, rdx
0x14001380d  mov     r14, rcx
0x140013810  call    cs:__imp_KeEnterCriticalRegion
0x140013817  nop     dword ptr [rax+rax+00h]
0x14001381c  lea     r13, [rbx+0C0h]
0x140013823  xor     edx, edx
0x140013825  mov     rcx, r13
0x140013828  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14001382f  nop     dword ptr [rax+rax+00h]
0x140013834  lea     rdx, [r15+58h]
0x140013838  xor     r8d, r8d
0x14001383b  lea     r9, [rbp+var_10]
0x14001383f  mov     rcx, rbx
0x140013842  call    NpFindPrefix
0x140013847  mov     rdi, rax
0x14001384a  test    rax, rax
0x14001384d  jz      loc_14001398A
0x140013853  mov     eax, 203h
0x140013858  cmp     [rdi], ax
0x14001385b  jnz     loc_14001398A
0x140013861  cmp     r12w, word ptr [rbp+var_10]
0x140013866  jnz     loc_14001398A
0x14001386c  lea     r12, [rsi+20h]
0x140013870  mov     rcx, r12; SubjectContext
0x140013873  call    cs:__imp_SeLockSubjectContext
0x14001387a  nop     dword ptr [rax+rax+00h]
0x14001387f  mov     rbx, [rdi+98h]
0x140013886  call    cs:__imp_IoGetFileObjectGenericMapping
0x14001388d  nop     dword ptr [rax+rax+00h]
0x140013892  mov     dl, [rbp+arg_28]
0x140013895  lea     rcx, [rbp+arg_0]
0x140013899  mov     r9d, [rbp+DesiredAccess]; DesiredAccess
0x14001389d  mov     r8b, 1; SubjectContextLocked
0x1400138a0  mov     [rsp+60h+AccessStatus], rcx; AccessStatus
0x1400138a5  lea     rcx, [rbp+arg_8]
0x1400138a9  mov     [rsp+60h+GrantedAccess], rcx; GrantedAccess
0x1400138ae  mov     rcx, rbx; SecurityDescriptor
0x1400138b1  mov     [rsp+60h+AccessMode], dl; AccessMode
0x1400138b5  mov     rdx, r12; SubjectSecurityContext
0x1400138b8  mov     [rsp+60h+GenericMapping], rax; GenericMapping
0x1400138bd  lea     rax, [rbp+arg_10]
0x1400138c1  mov     [rsp+60h+Privileges], rax; Privileges
0x1400138c6  mov     [rsp+60h+PreviouslyGrantedAccess], 0; PreviouslyGrantedAccess
0x1400138ce  call    cs:__imp_SeAccessCheck
0x1400138d5  nop     dword ptr [rax+rax+00h]
0x1400138da  mov     rdx, [rbp+arg_10]; Privileges
0x1400138de  mov     bl, al
0x1400138e0  test    rdx, rdx
0x1400138e3  jz      short loc_140013904
0x1400138e5  mov     rcx, rsi; AccessState
0x1400138e8  call    cs:__imp_SeAppendPrivileges
0x1400138ef  nop     dword ptr [rax+rax+00h]
0x1400138f4  mov     rcx, [rbp+arg_10]; Privileges
0x1400138f8  call    cs:__imp_SeFreePrivileges
0x1400138ff  nop     dword ptr [rax+rax+00h]
0x140013904  test    bl, bl
0x140013906  jz      short loc_140013917
0x140013908  mov     eax, [rbp+arg_8]
0x14001390b  or      [rsi+14h], eax
0x14001390e  bts     eax, 19h
0x140013912  not     eax
0x140013914  and     [rsi+10h], eax
0x140013917  mov     rcx, r12; SubjectContext
0x14001391a  call    cs:__imp_SeUnlockSubjectContext
0x140013921  nop     dword ptr [rax+rax+00h]
0x140013926  test    bl, bl
0x140013928  jnz     short loc_140013969
0x14001392a  xor     edx, edx
0x14001392c  mov     rcx, r13
0x14001392f  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140013936  nop     dword ptr [rax+rax+00h]
0x14001393b  call    cs:__imp_KeLeaveCriticalRegion
0x140013942  nop     dword ptr [rax+rax+00h]
0x140013947  mov     eax, [rbp+arg_0]
0x14001394a  mov     rbx, [rsp+60h+arg_18]
0x140013952  mov     [r14], eax
0x140013955  mov     rax, r14
0x140013958  add     rsp, 60h
0x14001395c  pop     r15
0x14001395e  pop     r14
0x140013960  pop     r13
0x140013962  pop     r12
0x140013964  pop     rdi
0x140013965  pop     rsi
0x140013966  pop     rbp
0x140013967  retn
0x140013969  mov     eax, 1
0x14001396e  add     [rdi+78h], eax
0x140013971  lock add [rdi+7Ch], eax
0x140013975  mov     [r15+18h], rdi
0x140013979  mov     [r15+20h], rax
0x14001397d  mov     [rbp+arg_0], 0
0x140013984  mov     [r14+8], rax
0x140013988  jmp     short loc_14001392A
0x14001398a  mov     [rbp+arg_0], 0C0000034h
0x140013991  jmp     short loc_14001392A
```
