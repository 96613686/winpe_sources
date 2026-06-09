# HashpInitializeCrypto

- ea: `0x18005be98`
- end: `0x18005bf14`
- name: `HashpInitializeCrypto`
- size: `124`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180077f24`

## callees

- `0x180011cc8`

## import_xrefs

- `ntoskrnl!ExInitializePagedLookasideList` at `0x18005bec8`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x18005befb`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x18005bec8`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x18005befb`

## pseudocode

```c
void HashpInitializeCrypto()
{
  SymCryptInit();
  ExInitializePagedLookasideList(&Lookaside, 0, 0, 0, 0xA20u, 0x72634943u, 0);
  ExInitializePagedLookasideList(&stru_180049900, 0, 0, 0, 0xF0u, 0x72634943u, 0);
  byte_180049F0C = 1;
}

```

## disassembly

```asm
0x18005be98  sub     rsp, 48h
0x18005be9c  call    SymCryptInit
0x18005bea1  xor     eax, eax
0x18005bea3  lea     rcx, Lookaside; Lookaside
0x18005beaa  mov     [rsp+48h+Depth], ax; Depth
0x18005beaf  xor     r9d, r9d; Flags
0x18005beb2  mov     [rsp+48h+Tag], 72634943h; Tag
0x18005beba  xor     r8d, r8d; Free
0x18005bebd  xor     edx, edx; Allocate
0x18005bebf  mov     [rsp+48h+Size], 0A20h; Size
0x18005bec8  call    cs:__imp_ExInitializePagedLookasideList
0x18005becf  nop     dword ptr [rax+rax+00h]
0x18005bed4  xor     eax, eax
0x18005bed6  lea     rcx, stru_180049900; Lookaside
0x18005bedd  mov     [rsp+48h+Depth], ax; Depth
0x18005bee2  xor     r9d, r9d; Flags
0x18005bee5  mov     [rsp+48h+Tag], 72634943h; Tag
0x18005beed  xor     r8d, r8d; Free
0x18005bef0  xor     edx, edx; Allocate
0x18005bef2  mov     [rsp+48h+Size], 0F0h; Size
0x18005befb  call    cs:__imp_ExInitializePagedLookasideList
0x18005bf02  nop     dword ptr [rax+rax+00h]
0x18005bf07  mov     cs:byte_180049F0C, 1
0x18005bf0e  add     rsp, 48h
0x18005bf12  retn
```
