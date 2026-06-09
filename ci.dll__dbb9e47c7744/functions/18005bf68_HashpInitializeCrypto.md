# HashpInitializeCrypto

- ea: `0x18005bf68`
- end: `0x18005bfe4`
- name: `HashpInitializeCrypto`
- size: `124`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180077c44`

## callees

- `0x180011cb8`

## import_xrefs

- `ntoskrnl!ExInitializePagedLookasideList` at `0x18005bf98`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x18005bfcb`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x18005bf98`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x18005bfcb`

## pseudocode

```c
void HashpInitializeCrypto()
{
  SymCryptInit();
  ExInitializePagedLookasideList(&Lookaside, 0, 0, 0, 0xA20u, 0x72634943u, 0);
  ExInitializePagedLookasideList(&stru_180049900, 0, 0, 0, 0xF0u, 0x72634943u, 0);
  byte_180049EF4 = 1;
}

```

## disassembly

```asm
0x18005bf68  sub     rsp, 48h
0x18005bf6c  call    SymCryptInit
0x18005bf71  xor     eax, eax
0x18005bf73  lea     rcx, Lookaside; Lookaside
0x18005bf7a  mov     [rsp+48h+Depth], ax; Depth
0x18005bf7f  xor     r9d, r9d; Flags
0x18005bf82  mov     [rsp+48h+Tag], 72634943h; Tag
0x18005bf8a  xor     r8d, r8d; Free
0x18005bf8d  xor     edx, edx; Allocate
0x18005bf8f  mov     [rsp+48h+Size], 0A20h; Size
0x18005bf98  call    cs:__imp_ExInitializePagedLookasideList
0x18005bf9f  nop     dword ptr [rax+rax+00h]
0x18005bfa4  xor     eax, eax
0x18005bfa6  lea     rcx, stru_180049900; Lookaside
0x18005bfad  mov     [rsp+48h+Depth], ax; Depth
0x18005bfb2  xor     r9d, r9d; Flags
0x18005bfb5  mov     [rsp+48h+Tag], 72634943h; Tag
0x18005bfbd  xor     r8d, r8d; Free
0x18005bfc0  xor     edx, edx; Allocate
0x18005bfc2  mov     [rsp+48h+Size], 0F0h; Size
0x18005bfcb  call    cs:__imp_ExInitializePagedLookasideList
0x18005bfd2  nop     dword ptr [rax+rax+00h]
0x18005bfd7  mov     cs:byte_180049EF4, 1
0x18005bfde  add     rsp, 48h
0x18005bfe2  retn
```
