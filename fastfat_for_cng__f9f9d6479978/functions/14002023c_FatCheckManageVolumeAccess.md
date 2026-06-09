# FatCheckManageVolumeAccess

- ea: `0x14002023c`
- end: `0x14002029a`
- name: `FatCheckManageVolumeAccess`
- size: `94`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400202a0`
- `0x140029774`
- `0x14002adec`
- `0x14002b790`

## callees

- `0x14000c230`

## import_xrefs

- `ntoskrnl!SePrivilegeCheck` at `0x140020276`
- `ntoskrnl!SePrivilegeCheck` at `0x140020276`

## pseudocode

```c
bool __fastcall FatCheckManageVolumeAccess(__int64 a1, struct _SECURITY_SUBJECT_CONTEXT *a2, KPROCESSOR_MODE a3)
{
  struct _PRIVILEGE_SET RequiredPrivileges; // [rsp+20h] [rbp-28h] BYREF

  RequiredPrivileges.Privilege[0].Luid = (LUID)28LL;
  RequiredPrivileges.PrivilegeCount = 1;
  RequiredPrivileges.Control = 1;
  RequiredPrivileges.Privilege[0].Attributes = 0;
  return SePrivilegeCheck(&RequiredPrivileges, a2 + 1, a3) != 0;
}

```

## disassembly

```asm
0x14002023c  sub     rsp, 48h
0x140020240  mov     rax, cs:__security_cookie
0x140020247  xor     rax, rsp
0x14002024a  mov     [rsp+48h+var_10], rax
0x14002024f  mov     eax, 1
0x140020254  mov     qword ptr [rsp+48h+RequiredPrivileges.Privilege.Luid.LowPart], 1Ch
0x14002025d  add     rdx, 20h ; ' '; SubjectSecurityContext
0x140020261  mov     [rsp+48h+RequiredPrivileges.PrivilegeCount], eax
0x140020265  lea     rcx, [rsp+48h+RequiredPrivileges]; RequiredPrivileges
0x14002026a  mov     [rsp+48h+RequiredPrivileges.Control], eax
0x14002026e  mov     [rsp+48h+RequiredPrivileges.Privilege.Attributes], 0
0x140020276  call    cs:__imp_SePrivilegeCheck
0x14002027d  nop     dword ptr [rax+rax+00h]
0x140020282  test    al, al
0x140020284  setnz   al
0x140020287  mov     rcx, [rsp+48h+var_10]
0x14002028c  xor     rcx, rsp; StackCookie
0x14002028f  call    __security_check_cookie
0x140020294  add     rsp, 48h
0x140020298  retn
```
