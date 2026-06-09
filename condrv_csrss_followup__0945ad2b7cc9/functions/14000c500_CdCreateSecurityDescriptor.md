# CdCreateSecurityDescriptor

- ea: `0x14000c500`
- end: `0x14000c5c0`
- name: `CdCreateSecurityDescriptor`
- size: `192`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000b820`
- `0x14000d5c0`

## callees

- `0x14000c500`

## import_xrefs

- `ntoskrnl!SeAssignSecurityEx` at `0x14000c54d`
- `ntoskrnl!SeAssignSecurityEx` at `0x14000c54d`
- `ntoskrnl!ObLogSecurityDescriptor` at `0x14000c572`
- `ntoskrnl!ObLogSecurityDescriptor` at `0x14000c572`
- `ntoskrnl!SeDeassignSecurity` at `0x14000c585`
- `ntoskrnl!SeDeassignSecurity` at `0x14000c585`

## pseudocode

```c
NTSTATUS __fastcall CdCreateSecurityDescriptor(_QWORD *a1, struct _SECURITY_SUBJECT_CONTEXT *a2)
{
  NTSTATUS result; // eax
  int v4; // ebx
  PSECURITY_DESCRIPTOR NewDescriptor; // [rsp+68h] [rbp+10h] BYREF
  __int64 v6; // [rsp+70h] [rbp+18h] BYREF

  NewDescriptor = 0;
  v6 = 0;
  result = SeAssignSecurityEx(0, a2[2].ClientToken, &NewDescriptor, 0, 0, 0x700u, a2 + 1, &CdpGenericMapping, PagedPool);
  if ( result >= 0 )
  {
    v4 = ObLogSecurityDescriptor(NewDescriptor, &v6, 1);
    SeDeassignSecurity(&NewDescriptor);
    if ( v4 < 0 )
    {
      return v4;
    }
    else
    {
      *a1 = v6;
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000c500  push    rdi
0x14000c502  sub     rsp, 50h
0x14000c506  xor     eax, eax
0x14000c508  mov     [rsp+58h+PoolType], 1; PoolType
0x14000c510  mov     rdi, rcx
0x14000c513  mov     [rsp+58h+NewDescriptor], rax
0x14000c518  mov     [rsp+58h+arg_10], rax
0x14000c51d  lea     rcx, CdpGenericMapping
0x14000c524  mov     [rsp+58h+GenericMapping], rcx; GenericMapping
0x14000c529  lea     rax, [rdx+20h]
0x14000c52d  mov     rdx, [rdx+40h]; ExplicitDescriptor
0x14000c531  lea     r8, [rsp+58h+NewDescriptor]; NewDescriptor
0x14000c536  mov     [rsp+58h+SubjectContext], rax; SubjectContext
0x14000c53b  xor     r9d, r9d; ObjectType
0x14000c53e  mov     [rsp+58h+AutoInheritFlags], 700h; AutoInheritFlags
0x14000c546  xor     ecx, ecx; ParentDescriptor
0x14000c548  mov     [rsp+58h+IsDirectoryObject], 0; IsDirectoryObject
0x14000c54d  call    cs:__imp_SeAssignSecurityEx
0x14000c554  nop     dword ptr [rax+rax+00h]
0x14000c559  test    eax, eax
0x14000c55b  js      short loc_14000C5A4
0x14000c55d  mov     rcx, [rsp+58h+NewDescriptor]
0x14000c562  lea     rdx, [rsp+58h+arg_10]
0x14000c567  mov     r8d, 1
0x14000c56d  mov     [rsp+58h+arg_0], rbx
0x14000c572  call    cs:__imp_ObLogSecurityDescriptor
0x14000c579  nop     dword ptr [rax+rax+00h]
0x14000c57e  lea     rcx, [rsp+58h+NewDescriptor]; SecurityDescriptor
0x14000c583  mov     ebx, eax
0x14000c585  call    cs:__imp_SeDeassignSecurity
0x14000c58c  nop     dword ptr [rax+rax+00h]
0x14000c591  test    ebx, ebx
0x14000c593  js      short loc_14000C5AB
0x14000c595  mov     rax, [rsp+58h+arg_10]
0x14000c59a  mov     rbx, [rsp+58h+arg_0]
0x14000c59f  mov     [rdi], rax
0x14000c5a2  xor     eax, eax
0x14000c5a4  add     rsp, 50h
0x14000c5a8  pop     rdi
0x14000c5a9  retn
0x14000c5ab  mov     eax, ebx
0x14000c5ad  mov     rbx, [rsp+58h+arg_0]
0x14000c5b2  add     rsp, 50h
0x14000c5b6  pop     rdi
0x14000c5b7  retn
```
