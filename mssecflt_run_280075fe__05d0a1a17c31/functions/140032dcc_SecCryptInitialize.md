# SecCryptInitialize

- ea: `0x140032dcc`
- end: `0x140032e13`
- name: `SecCryptInitialize`
- size: `71`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14002a1d4`

## callees

- `0x14000767c`

## import_xrefs

- `ntoskrnl!ExInitializePagedLookasideList` at `0x140032dfe`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140032dfe`

## pseudocode

```c
__int64 SecCryptInitialize()
{
  ExInitializePagedLookasideList((PPAGED_LOOKASIDE_LIST)SecData + 6, 0, 0, 0, 0x100980u, 0x73486353u, 0);
  return SymCryptInit();
}

```

## disassembly

```asm
0x140032dcc  sub     rsp, 48h
0x140032dd0  mov     rcx, cs:SecData
0x140032dd7  xor     eax, eax
0x140032dd9  mov     [rsp+48h+Depth], ax; Depth
0x140032dde  add     rcx, 300h; Lookaside
0x140032de5  mov     [rsp+48h+Tag], 73486353h; Tag
0x140032ded  xor     r9d, r9d; Flags
0x140032df0  xor     r8d, r8d; Free
0x140032df3  mov     [rsp+48h+Size], 100980h; Size
0x140032dfc  xor     edx, edx; Allocate
0x140032dfe  call    cs:__imp_ExInitializePagedLookasideList
0x140032e05  nop     dword ptr [rax+rax+00h]
0x140032e0a  add     rsp, 48h
0x140032e0e  jmp     SymCryptInit
```
