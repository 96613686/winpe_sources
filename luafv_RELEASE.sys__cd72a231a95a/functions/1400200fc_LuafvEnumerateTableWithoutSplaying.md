# LuafvEnumerateTableWithoutSplaying

- ea: `0x1400200fc`
- end: `0x14002014a`
- name: `LuafvEnumerateTableWithoutSplaying`
- size: `78`
- prototype: `PRTL_SPLAY_LINKS __fastcall(__int64, PRTL_SPLAY_LINKS *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14001fda8`
- `0x14001fdd0`

## callees

- `0x1400200fc`

## import_xrefs

- `ntoskrnl!RtlRealSuccessor` at `0x14002012f`
- `ntoskrnl!RtlRealSuccessor` at `0x14002012f`

## pseudocode

```c
PRTL_SPLAY_LINKS __fastcall LuafvEnumerateTableWithoutSplaying(__int64 a1, PRTL_SPLAY_LINKS *a2)
{
  PRTL_SPLAY_LINKS result; // rax

  if ( !*(_DWORD *)(a1 + 16) )
    return 0;
  if ( *a2 )
  {
    result = RtlRealSuccessor(*a2);
    if ( result )
      *a2 = result;
  }
  else
  {
    for ( result = *(PRTL_SPLAY_LINKS *)a1; result->LeftChild; result = result->LeftChild )
      ;
    *a2 = result;
  }
  return result;
}

```

## disassembly

```asm
0x1400200fc  push    rbx
0x1400200fe  sub     rsp, 20h
0x140020102  cmp     dword ptr [rcx+10h], 0
0x140020106  mov     rbx, rdx
0x140020109  mov     rax, rcx
0x14002010c  jnz     short loc_140020112
0x14002010e  xor     eax, eax
0x140020110  jmp     short loc_140020143
0x140020112  mov     rcx, [rdx]; Links
0x140020115  test    rcx, rcx
0x140020118  jnz     short loc_14002012F
0x14002011a  mov     rax, [rax]
0x14002011d  jmp     short loc_140020123
0x14002011f  mov     rax, [rax+8]
0x140020123  cmp     qword ptr [rax+8], 0
0x140020128  jnz     short loc_14002011F
0x14002012a  mov     [rdx], rax
0x14002012d  jmp     short loc_140020143
0x14002012f  call    cs:__imp_RtlRealSuccessor
0x140020136  nop     dword ptr [rax+rax+00h]
0x14002013b  test    rax, rax
0x14002013e  jz      short loc_140020143
0x140020140  mov     [rbx], rax
0x140020143  add     rsp, 20h
0x140020147  pop     rbx
0x140020148  retn
```
