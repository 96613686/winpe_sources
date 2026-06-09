# HashpInitializeCrypto

- ea: `0x18005b258`
- end: `0x18005b2d4`
- name: `HashpInitializeCrypto`
- size: `124`
- prototype: `void()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180076694`

## callees

- `0x180011dd0`

## import_xrefs

- `ntoskrnl!ExInitializePagedLookasideList` at `0x18005b288`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x18005b2bb`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x18005b288`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x18005b2bb`

## pseudocode

```c
void HashpInitializeCrypto()
{
  SymCryptInit();
  ExInitializePagedLookasideList(&Lookaside, 0, 0, 0, 0xA20u, 0x72634943u, 0);
  ExInitializePagedLookasideList(&stru_180048900, 0, 0, 0, 0xF0u, 0x72634943u, 0);
  byte_180048F04 = 1;
}

```

## disassembly

```asm
0x18005b258  sub     rsp, 48h
0x18005b25c  call    SymCryptInit
0x18005b261  xor     eax, eax
0x18005b263  lea     rcx, Lookaside; Lookaside
0x18005b26a  mov     [rsp+48h+Depth], ax; Depth
0x18005b26f  xor     r9d, r9d; Flags
0x18005b272  mov     [rsp+48h+Tag], 72634943h; Tag
0x18005b27a  xor     r8d, r8d; Free
0x18005b27d  xor     edx, edx; Allocate
0x18005b27f  mov     [rsp+48h+Size], 0A20h; Size
0x18005b288  call    cs:__imp_ExInitializePagedLookasideList
0x18005b28f  nop     dword ptr [rax+rax+00h]
0x18005b294  xor     eax, eax
0x18005b296  lea     rcx, stru_180048900; Lookaside
0x18005b29d  mov     [rsp+48h+Depth], ax; Depth
0x18005b2a2  xor     r9d, r9d; Flags
0x18005b2a5  mov     [rsp+48h+Tag], 72634943h; Tag
0x18005b2ad  xor     r8d, r8d; Free
0x18005b2b0  xor     edx, edx; Allocate
0x18005b2b2  mov     [rsp+48h+Size], 0F0h; Size
0x18005b2bb  call    cs:__imp_ExInitializePagedLookasideList
0x18005b2c2  nop     dword ptr [rax+rax+00h]
0x18005b2c7  mov     cs:byte_180048F04, 1
0x18005b2ce  add     rsp, 48h
0x18005b2d2  retn
```
