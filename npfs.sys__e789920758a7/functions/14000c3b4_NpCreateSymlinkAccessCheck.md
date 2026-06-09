# NpCreateSymlinkAccessCheck

- ea: `0x14000c3b4`
- end: `0x14000c542`
- name: `NpCreateSymlinkAccessCheck`
- size: `398`
- prototype: `__int64 __fastcall(__int64, char, __int64, __int64, KPROCESSOR_MODE PreviousMode, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14000b15c`

## callees

- `0x14000c3b4`
- `0x140012730`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14000c440`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000c440`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000c458`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000c458`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000c47f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000c47f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000c48b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000c48b`
- `ntoskrnl!SeAccessCheck` at `0x14000c50e`
- `ntoskrnl!SeAccessCheck` at `0x14000c50e`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14000c4bb`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14000c4bb`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x14000c404`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x14000c404`
- `ntoskrnl!SeExports` at `0x14000c3f3`
- `ntoskrnl!PsIsHostSilo` at `0x14000c426`
- `ntoskrnl!PsIsHostSilo` at `0x14000c426`

## pseudocode

```c
__int64 __fastcall NpCreateSymlinkAccessCheck(
        __int64 a1,
        char a2,
        __int64 a3,
        __int64 a4,
        KPROCESSOR_MODE PreviousMode,
        __int64 a6)
{
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // r8
  __int64 Prefix; // rdi
  void *v15; // rdi
  struct _GENERIC_MAPPING *GenericMapping; // rax
  DWORD v17; // eax
  DWORD GrantedAccess; // [rsp+50h] [rbp-48h] BYREF
  int AccessStatus; // [rsp+54h] [rbp-44h] BYREF
  _OWORD v20[4]; // [rsp+58h] [rbp-40h] BYREF

  GrantedAccess = 0;
  AccessStatus = 0;
  v20[0] = 0;
  if ( !PreviousMode )
    return 0;
  if ( !SeSinglePrivilegeCheck(SeExports->SeTcbPrivilege, PreviousMode) )
    return 3221225569LL;
  if ( (a2 & 1) != 0 && !(unsigned __int8)PsIsHostSilo(a3) )
    return 3221225506LL;
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(a4 + 192, 0, v11, v12);
  LOBYTE(v13) = 1;
  Prefix = NpFindPrefix(a4, a1, v13, v20);
  ExReleasePushLockExclusiveEx(a4 + 192, 0);
  KeLeaveCriticalRegion();
  if ( Prefix && *(_WORD *)Prefix == 515 )
    v15 = *(void **)(Prefix + 152);
  else
    v15 = *(void **)(a4 + 136);
  if ( !v15 )
    return 0;
  GenericMapping = IoGetFileObjectGenericMapping();
  if ( SeAccessCheck(
         v15,
         (PSECURITY_SUBJECT_CONTEXT)(a6 + 32),
         0,
         2u,
         0,
         0,
         GenericMapping,
         PreviousMode,
         &GrantedAccess,
         &AccessStatus) )
  {
    v17 = GrantedAccess;
    *(_DWORD *)(a6 + 20) |= GrantedAccess;
    *(_DWORD *)(a6 + 16) &= ~(v17 | 0x2000000);
    return 0;
  }
  return (unsigned int)AccessStatus;
}

```

## disassembly

```asm
0x14000c3b4  push    rbx
0x14000c3b6  push    rbp
0x14000c3b7  push    rsi
0x14000c3b8  push    rdi
0x14000c3b9  push    r14
0x14000c3bb  sub     rsp, 70h
0x14000c3bf  mov     bpl, [rsp+98h+PreviousMode]
0x14000c3c7  xorps   xmm0, xmm0
0x14000c3ca  mov     [rsp+98h+var_48], 0
0x14000c3d2  mov     rsi, r9
0x14000c3d5  mov     [rsp+98h+var_44], 0
0x14000c3dd  mov     rdi, r8
0x14000c3e0  mov     ebx, edx
0x14000c3e2  mov     r14, rcx
0x14000c3e5  movups  [rsp+98h+var_40], xmm0
0x14000c3ea  test    bpl, bpl
0x14000c3ed  jz      loc_14000C52E
0x14000c3f3  mov     rax, cs:__imp_SeExports
0x14000c3fa  mov     dl, bpl; PreviousMode
0x14000c3fd  mov     rcx, [rax]
0x14000c400  mov     rcx, [rcx+28h]; PrivilegeValue
0x14000c404  call    cs:__imp_SeSinglePrivilegeCheck
0x14000c40b  nop     dword ptr [rax+rax+00h]
0x14000c410  test    al, al
0x14000c412  jnz     short loc_14000C41E
0x14000c414  mov     eax, 0C0000061h
0x14000c419  jmp     loc_14000C530
0x14000c41e  test    bl, 1
0x14000c421  jz      short loc_14000C440
0x14000c423  mov     rcx, rdi
0x14000c426  call    cs:__imp_PsIsHostSilo
0x14000c42d  nop     dword ptr [rax+rax+00h]
0x14000c432  test    al, al
0x14000c434  jnz     short loc_14000C440
0x14000c436  mov     eax, 0C0000022h
0x14000c43b  jmp     loc_14000C530
0x14000c440  call    cs:__imp_KeEnterCriticalRegion
0x14000c447  nop     dword ptr [rax+rax+00h]
0x14000c44c  lea     rbx, [rsi+0C0h]
0x14000c453  xor     edx, edx
0x14000c455  mov     rcx, rbx
0x14000c458  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000c45f  nop     dword ptr [rax+rax+00h]
0x14000c464  lea     r9, [rsp+98h+var_40]
0x14000c469  mov     r8b, 1
0x14000c46c  mov     rdx, r14
0x14000c46f  mov     rcx, rsi
0x14000c472  call    NpFindPrefix
0x14000c477  xor     edx, edx
0x14000c479  mov     rcx, rbx
0x14000c47c  mov     rdi, rax
0x14000c47f  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000c486  nop     dword ptr [rax+rax+00h]
0x14000c48b  call    cs:__imp_KeLeaveCriticalRegion
0x14000c492  nop     dword ptr [rax+rax+00h]
0x14000c497  test    rdi, rdi
0x14000c49a  jz      short loc_14000C4AF
0x14000c49c  mov     eax, 203h
0x14000c4a1  cmp     [rdi], ax
0x14000c4a4  jnz     short loc_14000C4AF
0x14000c4a6  mov     rdi, [rdi+98h]
0x14000c4ad  jmp     short loc_14000C4B6
0x14000c4af  mov     rdi, [rsi+88h]
0x14000c4b6  test    rdi, rdi
0x14000c4b9  jz      short loc_14000C52E
0x14000c4bb  call    cs:__imp_IoGetFileObjectGenericMapping
0x14000c4c2  nop     dword ptr [rax+rax+00h]
0x14000c4c7  mov     rbx, [rsp+98h+arg_28]
0x14000c4cf  lea     rcx, [rsp+98h+var_44]
0x14000c4d4  mov     [rsp+98h+AccessStatus], rcx; AccessStatus
0x14000c4d9  mov     r9d, 2; DesiredAccess
0x14000c4df  lea     rcx, [rsp+98h+var_48]
0x14000c4e4  xor     r8d, r8d; SubjectContextLocked
0x14000c4e7  mov     [rsp+98h+GrantedAccess], rcx; GrantedAccess
0x14000c4ec  mov     rcx, rdi; SecurityDescriptor
0x14000c4ef  mov     [rsp+98h+AccessMode], bpl; AccessMode
0x14000c4f4  lea     rdx, [rbx+20h]; SubjectSecurityContext
0x14000c4f8  mov     [rsp+98h+GenericMapping], rax; GenericMapping
0x14000c4fd  mov     [rsp+98h+Privileges], 0; Privileges
0x14000c506  mov     [rsp+98h+PreviouslyGrantedAccess], 0; PreviouslyGrantedAccess
0x14000c50e  call    cs:__imp_SeAccessCheck
0x14000c515  nop     dword ptr [rax+rax+00h]
0x14000c51a  test    al, al
0x14000c51c  jz      short loc_14000C53C
0x14000c51e  mov     eax, [rsp+98h+var_48]
0x14000c522  or      [rbx+14h], eax
0x14000c525  bts     eax, 19h
0x14000c529  not     eax
0x14000c52b  and     [rbx+10h], eax
0x14000c52e  xor     eax, eax
0x14000c530  add     rsp, 70h
0x14000c534  pop     r14
0x14000c536  pop     rdi
0x14000c537  pop     rsi
0x14000c538  pop     rbp
0x14000c539  pop     rbx
0x14000c53a  retn
0x14000c53c  mov     eax, [rsp+98h+var_44]
0x14000c540  jmp     short loc_14000C530
```
