# QuicSentPacketPoolInitialize

- ea: `0x14000175c`
- end: `0x1400017c2`
- name: `QuicSentPacketPoolInitialize`
- size: `102`
- prototype: `__int64 __fastcall(PLOOKASIDE_LIST_EX Lookaside)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14002d550`

## callees

- `0x14000175c`

## import_xrefs

- `ntoskrnl!ExInitializeLookasideListEx` at `0x14000179f`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14000179f`

## pseudocode

```c
NTSTATUS __fastcall QuicSentPacketPoolInitialize(PLOOKASIDE_LIST_EX Lookaside)
{
  unsigned int i; // ebx
  NTSTATUS result; // eax

  for ( i = 0; i < 0xC; ++i )
    result = ExInitializeLookasideListEx(Lookaside++, 0, 0, (POOL_TYPE)512, 0, 24 * (i + 5) + 16LL, 0x35306351u, 0x400u);
  return result;
}

```

## disassembly

```asm
0x14000175c  mov     [rsp+arg_0], rbx
0x140001761  push    rdi
0x140001762  sub     rsp, 40h
0x140001766  mov     rdi, rcx
0x140001769  xor     ebx, ebx
0x14000176b  mov     [rsp+48h+Depth], 400h; Depth
0x140001772  lea     eax, [rbx+5]
0x140001775  lea     eax, [rax+rax*2]
0x140001778  mov     [rsp+48h+Tag], 35306351h; Tag
0x140001780  shl     eax, 3
0x140001783  mov     r9d, 200h; PoolType
0x140001789  add     rax, 10h
0x14000178d  xor     r8d, r8d; Free
0x140001790  mov     [rsp+48h+Size], rax; Size
0x140001795  xor     edx, edx; Allocate
0x140001797  and     [rsp+48h+var_28], 0
0x14000179c  mov     rcx, rdi; Lookaside
0x14000179f  call    cs:__imp_ExInitializeLookasideListEx
0x1400017a6  nop     dword ptr [rax+rax+00h]
0x1400017ab  inc     ebx
0x1400017ad  add     rdi, 60h ; '`'
0x1400017b1  cmp     ebx, 0Ch
0x1400017b4  jb      short loc_14000176B
0x1400017b6  mov     rbx, [rsp+48h+arg_0]
0x1400017bb  add     rsp, 40h
0x1400017bf  pop     rdi
0x1400017c0  retn
```
