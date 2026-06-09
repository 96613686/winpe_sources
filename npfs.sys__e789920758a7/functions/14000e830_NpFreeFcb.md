# NpFreeFcb

- ea: `0x14000e830`
- end: `0x14000e8b5`
- name: `NpFreeFcb`
- size: `133`
- prototype: `void __fastcall(PVOID P)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000e640`
- `0x14001399c`

## callees

- `0x14000e830`
- `0x140010068`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000e870`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e891`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e8a2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e870`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e891`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e8a2`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x14000e84a`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x14000e84a`
- `ntoskrnl!FsRtlTeardownPerStreamContexts` at `0x14000e87f`
- `ntoskrnl!FsRtlTeardownPerStreamContexts` at `0x14000e87f`

## pseudocode

```c
void __fastcall NpFreeFcb(PVOID P)
{
  __int64 v2; // rcx
  void *v3; // rcx

  v2 = *((_QWORD *)P + 19);
  if ( v2 )
    ObDereferenceSecurityDescriptor(v2, 1);
  NpRemoveAllAttributesFromList((_QWORD **)P + 37);
  v3 = (void *)*((_QWORD *)P + 21);
  if ( v3 )
    ExFreePoolWithTag(v3, 0);
  FsRtlTeardownPerStreamContexts((PFSRTL_ADVANCED_FCB_HEADER)P);
  ExFreePoolWithTag(*((PVOID *)P + 6), 0);
  ExFreePoolWithTag(P, 0);
}

```

## disassembly

```asm
0x14000e830  push    rbx
0x14000e832  sub     rsp, 20h
0x14000e836  mov     rbx, rcx
0x14000e839  mov     rcx, [rcx+98h]
0x14000e840  test    rcx, rcx
0x14000e843  jz      short loc_14000E856
0x14000e845  mov     edx, 1
0x14000e84a  call    cs:__imp_ObDereferenceSecurityDescriptor
0x14000e851  nop     dword ptr [rax+rax+00h]
0x14000e856  lea     rcx, [rbx+128h]
0x14000e85d  call    NpRemoveAllAttributesFromList
0x14000e862  mov     rcx, [rbx+0A8h]; P
0x14000e869  test    rcx, rcx
0x14000e86c  jz      short loc_14000E87C
0x14000e86e  xor     edx, edx; Tag
0x14000e870  call    cs:__imp_ExFreePoolWithTag
0x14000e877  nop     dword ptr [rax+rax+00h]
0x14000e87c  mov     rcx, rbx; AdvancedHeader
0x14000e87f  call    cs:__imp_FsRtlTeardownPerStreamContexts
0x14000e886  nop     dword ptr [rax+rax+00h]
0x14000e88b  mov     rcx, [rbx+30h]; P
0x14000e88f  xor     edx, edx; Tag
0x14000e891  call    cs:__imp_ExFreePoolWithTag
0x14000e898  nop     dword ptr [rax+rax+00h]
0x14000e89d  xor     edx, edx; Tag
0x14000e89f  mov     rcx, rbx; P
0x14000e8a2  call    cs:__imp_ExFreePoolWithTag
0x14000e8a9  nop     dword ptr [rax+rax+00h]
0x14000e8ae  add     rsp, 20h
0x14000e8b2  pop     rbx
0x14000e8b3  retn
```
