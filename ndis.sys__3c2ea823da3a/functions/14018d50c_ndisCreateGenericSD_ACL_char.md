# ndisCreateGenericSD(_ACL *,char *)

- ea: `0x14018d50c`
- end: `0x14018d5ff`
- name: `?ndisCreateGenericSD@@YAJPEAU_ACL@@PEAD@Z`
- size: `243`
- prototype: `__int64 __fastcall(PACL Dacl, PSECURITY_DESCRIPTOR SecurityDescriptor)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14018b240`

## callees

- `0x14018d50c`

## import_xrefs

- `ntoskrnl!DbgPrint` at `0x14018d5e0`
- `ntoskrnl!DbgPrint` at `0x14018d5e0`
- `ntoskrnl!SeExports` at `0x14018d57c`
- `ntoskrnl!SeExports` at `0x14018d5ae`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14018d561`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14018d561`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14018d538`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14018d538`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x14018d593`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x14018d593`
- `ntoskrnl!RtlSetGroupSecurityDescriptor` at `0x14018d5c5`
- `ntoskrnl!RtlSetGroupSecurityDescriptor` at `0x14018d5c5`

## string_xrefs

- `0x14018d54a`: `RtlCreateSecurityDescriptor failed, Status %lx.\n`
- `0x14018d573`: `RtlSetDaclSecurityDescriptor failed, Status %lx.\n`
- `0x14018d5a5`: `RtlSetOwnerSecurityDescriptor failed, Status %lx.\n`
- `0x14018d5d7`: `RtlSetGroupSecurityDescriptor failed, Status %lx.\n`

## pseudocode

```c
__int64 __fastcall ndisCreateGenericSD(PACL Dacl, PSECURITY_DESCRIPTOR SecurityDescriptor)
{
  NTSTATUS v5; // eax
  unsigned int v6; // ebx
  NTSTATUS v7; // eax
  NTSTATUS v8; // eax
  NTSTATUS v9; // eax

  if ( !Dacl )
    return 3221225473LL;
  v5 = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v7 = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, Dacl, 0);
    v6 = v7;
    if ( v7 >= 0 )
    {
      v8 = RtlSetOwnerSecurityDescriptor(SecurityDescriptor, SeExports->SeAliasAdminsSid, 0);
      v6 = v8;
      if ( v8 >= 0 )
      {
        v9 = RtlSetGroupSecurityDescriptor(SecurityDescriptor, SeExports->SeAliasAdminsSid, 0);
        v6 = v9;
        if ( v9 < 0 )
          DbgPrint("RtlSetGroupSecurityDescriptor failed, Status %lx.\n", (unsigned int)v9);
      }
      else
      {
        DbgPrint("RtlSetOwnerSecurityDescriptor failed, Status %lx.\n", (unsigned int)v8);
      }
    }
    else
    {
      DbgPrint("RtlSetDaclSecurityDescriptor failed, Status %lx.\n", (unsigned int)v7);
    }
  }
  else
  {
    DbgPrint("RtlCreateSecurityDescriptor failed, Status %lx.\n", (unsigned int)v5);
  }
  return v6;
}

```

## disassembly

```asm
0x14018d50c  mov     [rsp+arg_0], rbx
0x14018d511  mov     [rsp+arg_8], rsi
0x14018d516  push    rdi
0x14018d517  sub     rsp, 20h
0x14018d51b  mov     rdi, rdx
0x14018d51e  mov     rsi, rcx
0x14018d521  test    rcx, rcx
0x14018d524  jnz     short loc_14018D530
0x14018d526  mov     eax, 0C0000001h
0x14018d52b  jmp     loc_14018D5EE
0x14018d530  mov     edx, 1; Revision
0x14018d535  mov     rcx, rdi; SecurityDescriptor
0x14018d538  call    cs:__imp_RtlCreateSecurityDescriptor
0x14018d53f  nop     dword ptr [rax+rax+00h]
0x14018d544  mov     ebx, eax
0x14018d546  test    eax, eax
0x14018d548  jns     short loc_14018D556
0x14018d54a  lea     rcx, aRtlcreatesecur; "RtlCreateSecurityDescriptor failed, Sta"...
0x14018d551  jmp     loc_14018D5DE
0x14018d556  xor     r9d, r9d; DaclDefaulted
0x14018d559  mov     r8, rsi; Dacl
0x14018d55c  mov     dl, 1; DaclPresent
0x14018d55e  mov     rcx, rdi; SecurityDescriptor
0x14018d561  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x14018d568  nop     dword ptr [rax+rax+00h]
0x14018d56d  mov     ebx, eax
0x14018d56f  test    eax, eax
0x14018d571  jns     short loc_14018D57C
0x14018d573  lea     rcx, aRtlsetdaclsecu; "RtlSetDaclSecurityDescriptor failed, St"...
0x14018d57a  jmp     short loc_14018D5DE
0x14018d57c  mov     rax, cs:__imp_SeExports
0x14018d583  xor     r8d, r8d; OwnerDefaulted
0x14018d586  mov     rcx, rdi; SecurityDescriptor
0x14018d589  mov     rdx, [rax]
0x14018d58c  mov     rdx, [rdx+110h]; Owner
0x14018d593  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x14018d59a  nop     dword ptr [rax+rax+00h]
0x14018d59f  mov     ebx, eax
0x14018d5a1  test    eax, eax
0x14018d5a3  jns     short loc_14018D5AE
0x14018d5a5  lea     rcx, aRtlsetownersec; "RtlSetOwnerSecurityDescriptor failed, S"...
0x14018d5ac  jmp     short loc_14018D5DE
0x14018d5ae  mov     rax, cs:__imp_SeExports
0x14018d5b5  xor     r8d, r8d; GroupDefaulted
0x14018d5b8  mov     rcx, rdi; SecurityDescriptor
0x14018d5bb  mov     rdx, [rax]
0x14018d5be  mov     rdx, [rdx+110h]; Group
0x14018d5c5  call    cs:__imp_RtlSetGroupSecurityDescriptor
0x14018d5cc  nop     dword ptr [rax+rax+00h]
0x14018d5d1  mov     ebx, eax
0x14018d5d3  test    eax, eax
0x14018d5d5  jns     short loc_14018D5EC
0x14018d5d7  lea     rcx, aRtlsetgroupsec; "RtlSetGroupSecurityDescriptor failed, S"...
0x14018d5de  mov     edx, eax
0x14018d5e0  call    cs:__imp_DbgPrint
0x14018d5e7  nop     dword ptr [rax+rax+00h]
0x14018d5ec  mov     eax, ebx
0x14018d5ee  mov     rbx, [rsp+28h+arg_0]
0x14018d5f3  mov     rsi, [rsp+28h+arg_8]
0x14018d5f8  add     rsp, 20h
0x14018d5fc  pop     rdi
0x14018d5fd  retn
```
