# ndisCreateGenericSD(_ACL *,char *)

- ea: `0x14019351c`
- end: `0x14019360f`
- name: `?ndisCreateGenericSD@@YAJPEAU_ACL@@PEAD@Z`
- size: `243`
- prototype: `__int64 __fastcall(PACL Dacl, PSECURITY_DESCRIPTOR SecurityDescriptor)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140191240`

## callees

- `0x14019351c`

## import_xrefs

- `ntoskrnl!DbgPrint` at `0x1401935f0`
- `ntoskrnl!DbgPrint` at `0x1401935f0`
- `ntoskrnl!SeExports` at `0x14019358c`
- `ntoskrnl!SeExports` at `0x1401935be`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140193571`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140193571`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140193548`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140193548`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x1401935a3`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x1401935a3`
- `ntoskrnl!RtlSetGroupSecurityDescriptor` at `0x1401935d5`
- `ntoskrnl!RtlSetGroupSecurityDescriptor` at `0x1401935d5`

## string_xrefs

- `0x14019355a`: `RtlCreateSecurityDescriptor failed, Status %lx.\n`
- `0x140193583`: `RtlSetDaclSecurityDescriptor failed, Status %lx.\n`
- `0x1401935b5`: `RtlSetOwnerSecurityDescriptor failed, Status %lx.\n`
- `0x1401935e7`: `RtlSetGroupSecurityDescriptor failed, Status %lx.\n`

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
0x14019351c  mov     [rsp+arg_0], rbx
0x140193521  mov     [rsp+arg_8], rsi
0x140193526  push    rdi
0x140193527  sub     rsp, 20h
0x14019352b  mov     rdi, rdx
0x14019352e  mov     rsi, rcx
0x140193531  test    rcx, rcx
0x140193534  jnz     short loc_140193540
0x140193536  mov     eax, 0C0000001h
0x14019353b  jmp     loc_1401935FE
0x140193540  mov     edx, 1; Revision
0x140193545  mov     rcx, rdi; SecurityDescriptor
0x140193548  call    cs:__imp_RtlCreateSecurityDescriptor
0x14019354f  nop     dword ptr [rax+rax+00h]
0x140193554  mov     ebx, eax
0x140193556  test    eax, eax
0x140193558  jns     short loc_140193566
0x14019355a  lea     rcx, aRtlcreatesecur; "RtlCreateSecurityDescriptor failed, Sta"...
0x140193561  jmp     loc_1401935EE
0x140193566  xor     r9d, r9d; DaclDefaulted
0x140193569  mov     r8, rsi; Dacl
0x14019356c  mov     dl, 1; DaclPresent
0x14019356e  mov     rcx, rdi; SecurityDescriptor
0x140193571  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x140193578  nop     dword ptr [rax+rax+00h]
0x14019357d  mov     ebx, eax
0x14019357f  test    eax, eax
0x140193581  jns     short loc_14019358C
0x140193583  lea     rcx, aRtlsetdaclsecu; "RtlSetDaclSecurityDescriptor failed, St"...
0x14019358a  jmp     short loc_1401935EE
0x14019358c  mov     rax, cs:__imp_SeExports
0x140193593  xor     r8d, r8d; OwnerDefaulted
0x140193596  mov     rcx, rdi; SecurityDescriptor
0x140193599  mov     rdx, [rax]
0x14019359c  mov     rdx, [rdx+110h]; Owner
0x1401935a3  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x1401935aa  nop     dword ptr [rax+rax+00h]
0x1401935af  mov     ebx, eax
0x1401935b1  test    eax, eax
0x1401935b3  jns     short loc_1401935BE
0x1401935b5  lea     rcx, aRtlsetownersec; "RtlSetOwnerSecurityDescriptor failed, S"...
0x1401935bc  jmp     short loc_1401935EE
0x1401935be  mov     rax, cs:__imp_SeExports
0x1401935c5  xor     r8d, r8d; GroupDefaulted
0x1401935c8  mov     rcx, rdi; SecurityDescriptor
0x1401935cb  mov     rdx, [rax]
0x1401935ce  mov     rdx, [rdx+110h]; Group
0x1401935d5  call    cs:__imp_RtlSetGroupSecurityDescriptor
0x1401935dc  nop     dword ptr [rax+rax+00h]
0x1401935e1  mov     ebx, eax
0x1401935e3  test    eax, eax
0x1401935e5  jns     short loc_1401935FC
0x1401935e7  lea     rcx, aRtlsetgroupsec; "RtlSetGroupSecurityDescriptor failed, S"...
0x1401935ee  mov     edx, eax
0x1401935f0  call    cs:__imp_DbgPrint
0x1401935f7  nop     dword ptr [rax+rax+00h]
0x1401935fc  mov     eax, ebx
0x1401935fe  mov     rbx, [rsp+28h+arg_0]
0x140193603  mov     rsi, [rsp+28h+arg_8]
0x140193608  add     rsp, 20h
0x14019360c  pop     rdi
0x14019360d  retn
```
