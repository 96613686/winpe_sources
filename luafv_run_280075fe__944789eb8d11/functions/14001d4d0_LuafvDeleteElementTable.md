# LuafvDeleteElementTable

- ea: `0x14001d4d0`
- end: `0x14001d51c`
- name: `LuafvDeleteElementTable`
- size: `76`
- prototype: `__int64 __fastcall(PRTL_SPLAY_LINKS *Root, PRTL_SPLAY_LINKS Links)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14001af8c`
- `0x14001d3cc`
- `0x14001de14`

## callees

- `0x14001d4d0`

## import_xrefs

- `ntoskrnl!RtlRealPredecessor` at `0x14001d50a`
- `ntoskrnl!RtlRealPredecessor` at `0x14001d50a`
- `ntoskrnl!RtlDeleteNoSplay` at `0x14001d4ec`
- `ntoskrnl!RtlDeleteNoSplay` at `0x14001d4ec`

## pseudocode

```c
void __fastcall LuafvDeleteElementTable(PRTL_SPLAY_LINKS *Root, PRTL_SPLAY_LINKS Links)
{
  if ( Links == Root[1] )
    Root[1] = RtlRealPredecessor(Links);
  RtlDeleteNoSplay(Links, Root);
  --*((_DWORD *)Root + 4);
}

```

## disassembly

```asm
0x14001d4d0  mov     [rsp+arg_0], rbx
0x14001d4d5  push    rdi
0x14001d4d6  sub     rsp, 20h
0x14001d4da  mov     rdi, rdx
0x14001d4dd  mov     rbx, rcx
0x14001d4e0  cmp     rdx, [rcx+8]
0x14001d4e4  jz      short loc_14001D507
0x14001d4e6  mov     rdx, rbx; Root
0x14001d4e9  mov     rcx, rdi; Links
0x14001d4ec  call    cs:__imp_RtlDeleteNoSplay
0x14001d4f3  nop     dword ptr [rax+rax+00h]
0x14001d4f8  dec     dword ptr [rbx+10h]
0x14001d4fb  mov     rbx, [rsp+28h+arg_0]
0x14001d500  add     rsp, 20h
0x14001d504  pop     rdi
0x14001d505  retn
0x14001d507  mov     rcx, rdi; Links
0x14001d50a  call    cs:__imp_RtlRealPredecessor
0x14001d511  nop     dword ptr [rax+rax+00h]
0x14001d516  mov     [rbx+8], rax
0x14001d51a  jmp     short loc_14001D4E6
```
