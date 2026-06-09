# CscSeSinglePrilegeCheck

- ea: `0x14005f6b4`
- end: `0x14005f705`
- name: `CscSeSinglePrilegeCheck`
- size: `81`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14006cdc0`

## callees

- `0x14002f010`

## import_xrefs

- `ntoskrnl!SePrivilegeCheck` at `0x14005f6e6`
- `ntoskrnl!SePrivilegeCheck` at `0x14005f6e6`

## pseudocode

```c
BOOLEAN __fastcall CscSeSinglePrilegeCheck(LUID a1, struct _SECURITY_SUBJECT_CONTEXT *a2, KPROCESSOR_MODE a3)
{
  struct _PRIVILEGE_SET RequiredPrivileges; // [rsp+20h] [rbp-28h] BYREF

  RequiredPrivileges.Privilege[0].Luid = a1;
  RequiredPrivileges.PrivilegeCount = 1;
  RequiredPrivileges.Control = 1;
  RequiredPrivileges.Privilege[0].Attributes = 0;
  return SePrivilegeCheck(&RequiredPrivileges, a2, a3);
}

```

## disassembly

```asm
0x14005f6b4  sub     rsp, 48h
0x14005f6b8  mov     rax, cs:__security_cookie
0x14005f6bf  xor     rax, rsp
0x14005f6c2  mov     [rsp+48h+var_10], rax
0x14005f6c7  mov     eax, 1
0x14005f6cc  mov     qword ptr [rsp+48h+RequiredPrivileges.Privilege.Luid.LowPart], rcx
0x14005f6d1  lea     rcx, [rsp+48h+RequiredPrivileges]; RequiredPrivileges
0x14005f6d6  mov     [rsp+48h+RequiredPrivileges.PrivilegeCount], eax
0x14005f6da  mov     [rsp+48h+RequiredPrivileges.Control], eax
0x14005f6de  mov     [rsp+48h+RequiredPrivileges.Privilege.Attributes], 0
0x14005f6e6  call    cs:__imp_SePrivilegeCheck
0x14005f6ed  nop     dword ptr [rax+rax+00h]
0x14005f6f2  mov     rcx, [rsp+48h+var_10]
0x14005f6f7  xor     rcx, rsp; StackCookie
0x14005f6fa  call    __security_check_cookie
0x14005f6ff  add     rsp, 48h
0x14005f703  retn
```
