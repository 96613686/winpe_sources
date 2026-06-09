# NsipFreeAndCleanupNode

- ea: `0x14005f99c`
- end: `0x14005f9d5`
- name: `NsipFreeAndCleanupNode`
- size: `57`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140024220`
- `0x14005f7e8`

## callees

- `0x14005f99c`

## import_xrefs

- `ntoskrnl!ObReleaseObjectSecurity` at `0x14005f9b1`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x14005f9b1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005f9c2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005f9c2`

## pseudocode

```c
void __fastcall NsipFreeAndCleanupNode(PVOID P)
{
  void *v2; // rcx

  v2 = (void *)*((_QWORD *)P + 4);
  if ( v2 )
    ObReleaseObjectSecurity(v2, *((_BYTE *)P + 40));
  ExFreePoolWithTag(P, 0);
}

```

## disassembly

```asm
0x14005f99c  push    rbx
0x14005f99e  sub     rsp, 20h
0x14005f9a2  mov     rbx, rcx
0x14005f9a5  mov     rcx, [rcx+20h]; SecurityDescriptor
0x14005f9a9  test    rcx, rcx
0x14005f9ac  jz      short loc_14005F9BD
0x14005f9ae  mov     dl, [rbx+28h]; MemoryAllocated
0x14005f9b1  call    cs:__imp_ObReleaseObjectSecurity
0x14005f9b8  nop     dword ptr [rax+rax+00h]
0x14005f9bd  xor     edx, edx; Tag
0x14005f9bf  mov     rcx, rbx; P
0x14005f9c2  call    cs:__imp_ExFreePoolWithTag
0x14005f9c9  nop     dword ptr [rax+rax+00h]
0x14005f9ce  add     rsp, 20h
0x14005f9d2  pop     rbx
0x14005f9d3  retn
```
