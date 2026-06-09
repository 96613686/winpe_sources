# NpDeleteSymlink

- ea: `0x14000c548`
- end: `0x14000c640`
- name: `NpDeleteSymlink`
- size: `248`
- prototype: `void __fastcall(char *P, struct _UNICODE_PREFIX_TABLE *)`
- caller_count: `2`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14000b354`
- `0x14000d6dc`

## callees

- `0x14000c548`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000c5c7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c5dc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c615`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c626`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c5c7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c5dc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c615`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c626`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x14000c5f4`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x14000c5f4`
- `ntoskrnl!RtlRemoveUnicodePrefix` at `0x14000c58a`
- `ntoskrnl!RtlRemoveUnicodePrefix` at `0x14000c58a`
- `ntoskrnl!FsRtlTeardownPerStreamContexts` at `0x14000c603`
- `ntoskrnl!FsRtlTeardownPerStreamContexts` at `0x14000c603`

## pseudocode

```c
void __fastcall NpDeleteSymlink(char *P, struct _UNICODE_PREFIX_TABLE *a2)
{
  char *v2; // rax
  __int64 v3; // r8
  char **v5; // rcx
  char **v6; // rdx
  PVOID *v7; // rcx

  v2 = P + 232;
  v3 = *((_QWORD *)P + 29);
  if ( *(char **)(v3 + 8) != P + 232
    || (v5 = (char **)*((_QWORD *)P + 30), *v5 != v2)
    || (*v5 = (char *)v3,
        *(_QWORD *)(v3 + 8) = v5,
        RtlRemoveUnicodePrefix(a2 + 9, (PUNICODE_PREFIX_TABLE_ENTRY)(P + 176)),
        v6 = (char **)*((_QWORD *)P + 17),
        v6[1] != P + 136)
    || (v7 = (PVOID *)*((_QWORD *)P + 18), *v7 != P + 136) )
  {
    __fastfail(3u);
  }
  *v7 = v6;
  v6[1] = (char *)v7;
  ExFreePoolWithTag(*((PVOID *)P + 33), 0);
  ExFreePoolWithTag(*((PVOID *)P + 21), 0);
  ObDereferenceSecurityDescriptor(*((_QWORD *)P + 19), 1);
  FsRtlTeardownPerStreamContexts((PFSRTL_ADVANCED_FCB_HEADER)P);
  ExFreePoolWithTag(*((PVOID *)P + 6), 0);
  ExFreePoolWithTag(P, 0);
}

```

## disassembly

```asm
0x14000c548  push    rbx
0x14000c54a  sub     rsp, 20h
0x14000c54e  lea     rax, [rcx+0E8h]
0x14000c555  mov     r9, rdx
0x14000c558  mov     r8, [rax]
0x14000c55b  mov     rbx, rcx
0x14000c55e  cmp     [r8+8], rax
0x14000c562  jnz     loc_14000C639
0x14000c568  mov     rcx, [rax+8]
0x14000c56c  cmp     [rcx], rax
0x14000c56f  jnz     loc_14000C639
0x14000c575  mov     [rcx], r8
0x14000c578  lea     rdx, [rbx+0B0h]; PrefixTableEntry
0x14000c57f  mov     [r8+8], rcx
0x14000c583  lea     rcx, [r9+0D8h]; PrefixTable
0x14000c58a  call    cs:__imp_RtlRemoveUnicodePrefix
0x14000c591  nop     dword ptr [rax+rax+00h]
0x14000c596  lea     rax, [rbx+88h]
0x14000c59d  mov     rdx, [rax]
0x14000c5a0  cmp     [rdx+8], rax
0x14000c5a4  jnz     loc_14000C639
0x14000c5aa  mov     rcx, [rax+8]
0x14000c5ae  cmp     [rcx], rax
0x14000c5b1  jnz     loc_14000C639
0x14000c5b7  mov     [rcx], rdx
0x14000c5ba  mov     [rdx+8], rcx
0x14000c5be  xor     edx, edx; Tag
0x14000c5c0  mov     rcx, [rbx+108h]; P
0x14000c5c7  call    cs:__imp_ExFreePoolWithTag
0x14000c5ce  nop     dword ptr [rax+rax+00h]
0x14000c5d3  mov     rcx, [rbx+0A8h]; P
0x14000c5da  xor     edx, edx; Tag
0x14000c5dc  call    cs:__imp_ExFreePoolWithTag
0x14000c5e3  nop     dword ptr [rax+rax+00h]
0x14000c5e8  mov     rcx, [rbx+98h]
0x14000c5ef  mov     edx, 1
0x14000c5f4  call    cs:__imp_ObDereferenceSecurityDescriptor
0x14000c5fb  nop     dword ptr [rax+rax+00h]
0x14000c600  mov     rcx, rbx; AdvancedHeader
0x14000c603  call    cs:__imp_FsRtlTeardownPerStreamContexts
0x14000c60a  nop     dword ptr [rax+rax+00h]
0x14000c60f  mov     rcx, [rbx+30h]; P
0x14000c613  xor     edx, edx; Tag
0x14000c615  call    cs:__imp_ExFreePoolWithTag
0x14000c61c  nop     dword ptr [rax+rax+00h]
0x14000c621  xor     edx, edx; Tag
0x14000c623  mov     rcx, rbx; P
0x14000c626  call    cs:__imp_ExFreePoolWithTag
0x14000c62d  nop     dword ptr [rax+rax+00h]
0x14000c632  add     rsp, 20h
0x14000c636  pop     rbx
0x14000c637  retn
0x14000c639  mov     ecx, 3
0x14000c63e  int     29h; Win8: RtlFailFast(ecx)
```
