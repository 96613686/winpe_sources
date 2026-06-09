# NpDeleteSymlinkAccessCheck

- ea: `0x14000c648`
- end: `0x14000c72b`
- name: `NpDeleteSymlinkAccessCheck`
- size: `227`
- prototype: `__int64 __fastcall(__int64, KPROCESSOR_MODE, struct _ACCESS_STATE *)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14000b354`

## callees

- `0x14000c648`

## import_xrefs

- `ntoskrnl!SeAppendPrivileges` at `0x14000c6e3`
- `ntoskrnl!SeAppendPrivileges` at `0x14000c6e3`
- `ntoskrnl!SeFreePrivileges` at `0x14000c6f7`
- `ntoskrnl!SeFreePrivileges` at `0x14000c6f7`
- `ntoskrnl!SeAccessCheck` at `0x14000c6c5`
- `ntoskrnl!SeAccessCheck` at `0x14000c6c5`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14000c674`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14000c674`

## pseudocode

```c
__int64 __fastcall NpDeleteSymlinkAccessCheck(__int64 a1, KPROCESSOR_MODE a2, struct _ACCESS_STATE *a3)
{
  void *v3; // rdi
  struct _GENERIC_MAPPING *GenericMapping; // rax
  BOOLEAN v7; // bl
  DWORD v8; // eax
  DWORD GrantedAccess; // [rsp+70h] [rbp+8h] BYREF
  int AccessStatus; // [rsp+80h] [rbp+18h] BYREF
  PPRIVILEGE_SET Privileges; // [rsp+88h] [rbp+20h] BYREF

  v3 = *(void **)(a1 + 152);
  GrantedAccess = 0;
  AccessStatus = 0;
  Privileges = 0;
  GenericMapping = IoGetFileObjectGenericMapping();
  v7 = SeAccessCheck(
         v3,
         &a3->SubjectSecurityContext,
         0,
         0x10000u,
         0,
         &Privileges,
         GenericMapping,
         a2,
         &GrantedAccess,
         &AccessStatus);
  if ( Privileges )
  {
    SeAppendPrivileges(a3, Privileges);
    SeFreePrivileges(Privileges);
  }
  if ( !v7 )
    return (unsigned int)AccessStatus;
  v8 = GrantedAccess;
  a3->PreviouslyGrantedAccess |= GrantedAccess;
  a3->RemainingDesiredAccess &= ~(v8 | 0x2000000);
  return 0;
}

```

## disassembly

```asm
0x14000c648  mov     rax, rsp
0x14000c64b  push    rbx
0x14000c64c  push    rsi
0x14000c64d  push    rdi
0x14000c64e  sub     rsp, 50h
0x14000c652  mov     rdi, [rcx+98h]
0x14000c659  mov     rsi, r8
0x14000c65c  mov     bl, dl
0x14000c65e  mov     dword ptr [rax+8], 0
0x14000c665  mov     dword ptr [rax+18h], 0
0x14000c66c  mov     qword ptr [rax+20h], 0
0x14000c674  call    cs:__imp_IoGetFileObjectGenericMapping
0x14000c67b  nop     dword ptr [rax+rax+00h]
0x14000c680  lea     rcx, [rsp+68h+arg_10]
0x14000c688  mov     r9d, 10000h; DesiredAccess
0x14000c68e  mov     [rsp+68h+AccessStatus], rcx; AccessStatus
0x14000c693  lea     rdx, [rsi+20h]; SubjectSecurityContext
0x14000c697  lea     rcx, [rsp+68h+arg_0]
0x14000c69c  xor     r8d, r8d; SubjectContextLocked
0x14000c69f  mov     [rsp+68h+GrantedAccess], rcx; GrantedAccess
0x14000c6a4  mov     rcx, rdi; SecurityDescriptor
0x14000c6a7  mov     [rsp+68h+AccessMode], bl; AccessMode
0x14000c6ab  mov     [rsp+68h+GenericMapping], rax; GenericMapping
0x14000c6b0  lea     rax, [rsp+68h+arg_18]
0x14000c6b8  mov     [rsp+68h+Privileges], rax; Privileges
0x14000c6bd  mov     [rsp+68h+PreviouslyGrantedAccess], 0; PreviouslyGrantedAccess
0x14000c6c5  call    cs:__imp_SeAccessCheck
0x14000c6cc  nop     dword ptr [rax+rax+00h]
0x14000c6d1  mov     rdx, [rsp+68h+arg_18]; Privileges
0x14000c6d9  mov     bl, al
0x14000c6db  test    rdx, rdx
0x14000c6de  jz      short loc_14000C703
0x14000c6e0  mov     rcx, rsi; AccessState
0x14000c6e3  call    cs:__imp_SeAppendPrivileges
0x14000c6ea  nop     dword ptr [rax+rax+00h]
0x14000c6ef  mov     rcx, [rsp+68h+arg_18]; Privileges
0x14000c6f7  call    cs:__imp_SeFreePrivileges
0x14000c6fe  nop     dword ptr [rax+rax+00h]
0x14000c703  test    bl, bl
0x14000c705  jz      short loc_14000C71B
0x14000c707  mov     eax, [rsp+68h+arg_0]
0x14000c70b  or      [rsi+14h], eax
0x14000c70e  bts     eax, 19h
0x14000c712  not     eax
0x14000c714  and     [rsi+10h], eax
0x14000c717  xor     eax, eax
0x14000c719  jmp     short loc_14000C722
0x14000c71b  mov     eax, [rsp+68h+arg_10]
0x14000c722  add     rsp, 50h
0x14000c726  pop     rdi
0x14000c727  pop     rsi
0x14000c728  pop     rbx
0x14000c729  retn
```
