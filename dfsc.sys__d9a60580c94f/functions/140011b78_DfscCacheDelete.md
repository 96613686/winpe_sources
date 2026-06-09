# DfscCacheDelete

- ea: `0x140011b78`
- end: `0x140011bc1`
- name: `DfscCacheDelete`
- size: `73`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140012930`
- `0x140019ec0`

## callees

- `0x140001744`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140011bae`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011bae`
- `ntoskrnl!ExDeleteResourceLite` at `0x140011b8a`
- `ntoskrnl!ExDeleteResourceLite` at `0x140011b9d`
- `ntoskrnl!ExDeleteResourceLite` at `0x140011b8a`
- `ntoskrnl!ExDeleteResourceLite` at `0x140011b9d`

## pseudocode

```c
void __fastcall DfscCacheDelete(char *P)
{
  DfscCachePurge((PUNICODE_PREFIX_TABLE)P);
  ExDeleteResourceLite((PERESOURCE)(P + 56));
  ExDeleteResourceLite((PERESOURCE)(P + 160));
  ExFreePoolWithTag(P, 0);
}

```

## disassembly

```asm
0x140011b78  push    rbx
0x140011b7a  sub     rsp, 20h
0x140011b7e  mov     rbx, rcx
0x140011b81  call    DfscCachePurge
0x140011b86  lea     rcx, [rbx+38h]; Resource
0x140011b8a  call    cs:__imp_ExDeleteResourceLite
0x140011b91  nop     dword ptr [rax+rax+00h]
0x140011b96  lea     rcx, [rbx+0A0h]; Resource
0x140011b9d  call    cs:__imp_ExDeleteResourceLite
0x140011ba4  nop     dword ptr [rax+rax+00h]
0x140011ba9  xor     edx, edx; Tag
0x140011bab  mov     rcx, rbx; P
0x140011bae  call    cs:__imp_ExFreePoolWithTag
0x140011bb5  nop     dword ptr [rax+rax+00h]
0x140011bba  add     rsp, 20h
0x140011bbe  pop     rbx
0x140011bbf  retn
```
