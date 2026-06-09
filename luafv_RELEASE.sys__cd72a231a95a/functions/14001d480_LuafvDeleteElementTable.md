# LuafvDeleteElementTable

- ea: `0x14001d480`
- end: `0x14001d4cc`
- name: `LuafvDeleteElementTable`
- size: `76`
- prototype: `void __fastcall(PRTL_SPLAY_LINKS *Root, PRTL_SPLAY_LINKS Links)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14001af3c`
- `0x14001d37c`
- `0x14001ddc4`

## callees

- `0x14001d480`

## import_xrefs

- `ntoskrnl!RtlRealPredecessor` at `0x14001d4ba`
- `ntoskrnl!RtlRealPredecessor` at `0x14001d4ba`
- `ntoskrnl!RtlDeleteNoSplay` at `0x14001d49c`
- `ntoskrnl!RtlDeleteNoSplay` at `0x14001d49c`

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
0x14001d480  mov     [rsp+arg_0], rbx
0x14001d485  push    rdi
0x14001d486  sub     rsp, 20h
0x14001d48a  mov     rdi, rdx
0x14001d48d  mov     rbx, rcx
0x14001d490  cmp     rdx, [rcx+8]
0x14001d494  jz      short loc_14001D4B7
0x14001d496  mov     rdx, rbx; Root
0x14001d499  mov     rcx, rdi; Links
0x14001d49c  call    cs:__imp_RtlDeleteNoSplay
0x14001d4a3  nop     dword ptr [rax+rax+00h]
0x14001d4a8  dec     dword ptr [rbx+10h]
0x14001d4ab  mov     rbx, [rsp+28h+arg_0]
0x14001d4b0  add     rsp, 20h
0x14001d4b4  pop     rdi
0x14001d4b5  retn
0x14001d4b7  mov     rcx, rdi; Links
0x14001d4ba  call    cs:__imp_RtlRealPredecessor
0x14001d4c1  nop     dword ptr [rax+rax+00h]
0x14001d4c6  mov     [rbx+8], rax
0x14001d4ca  jmp     short loc_14001D496
```
