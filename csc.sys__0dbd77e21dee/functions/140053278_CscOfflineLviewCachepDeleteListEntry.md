# CscOfflineLviewCachepDeleteListEntry

- ea: `0x140053278`
- end: `0x1400532f7`
- name: `CscOfflineLviewCachepDeleteListEntry`
- size: `127`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140049150`
- `0x14004a4f4`
- `0x140053018`
- `0x14006f360`
- `0x1400709b0`
- `0x14007dee4`
- `0x140087bec`
- `0x14008d3e0`

## callees

- `0x14000a634`
- `0x140053278`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140053291`
- `ntoskrnl!ExFreePoolWithTag` at `0x140053291`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400532bb`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400532bb`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400532d8`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400532d8`

## pseudocode

```c
void __fastcall CscOfflineLviewCachepDeleteListEntry(__int64 *a1)
{
  __int64 v1; // rbx

  v1 = *a1;
  ExFreePoolWithTag(*(PVOID *)(*a1 + 184), 0);
  *(_QWORD *)(v1 + 184) = 0;
  if ( *(_QWORD *)(v1 + 32) )
    CscStoreDereferenceEntry(v1 + 32);
  ExDeleteResourceLite((PERESOURCE)(v1 + 40));
  ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(CscDevExtn + 256), (PVOID)v1);
  *a1 = 0;
}

```

## disassembly

```asm
0x140053278  mov     [rsp+arg_0], rbx
0x14005327d  push    rdi
0x14005327e  sub     rsp, 20h
0x140053282  mov     rbx, [rcx]
0x140053285  mov     rdi, rcx
0x140053288  xor     edx, edx; Tag
0x14005328a  mov     rcx, [rbx+0B8h]; P
0x140053291  call    cs:__imp_ExFreePoolWithTag
0x140053298  nop     dword ptr [rax+rax+00h]
0x14005329d  lea     rcx, [rbx+20h]
0x1400532a1  mov     qword ptr [rbx+0B8h], 0
0x1400532ac  cmp     qword ptr [rcx], 0
0x1400532b0  jz      short loc_1400532B7
0x1400532b2  call    CscStoreDereferenceEntry
0x1400532b7  lea     rcx, [rbx+28h]; Resource
0x1400532bb  call    cs:__imp_ExDeleteResourceLite
0x1400532c2  nop     dword ptr [rax+rax+00h]
0x1400532c7  mov     rcx, cs:CscDevExtn
0x1400532ce  mov     rdx, rbx; Entry
0x1400532d1  add     rcx, 100h; Lookaside
0x1400532d8  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400532df  nop     dword ptr [rax+rax+00h]
0x1400532e4  mov     rbx, [rsp+28h+arg_0]
0x1400532e9  mov     qword ptr [rdi], 0
0x1400532f0  add     rsp, 20h
0x1400532f4  pop     rdi
0x1400532f5  retn
```
