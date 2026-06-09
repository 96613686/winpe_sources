# DeleteInternalAddress

- ea: `0x1400118ec`
- end: `0x140011909`
- name: `DeleteInternalAddress`
- size: `29`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400104d8`
- `0x140011740`

## callees

- `0x1400118ec`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400118f7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400118f7`

## pseudocode

```c
void __fastcall DeleteInternalAddress(void *a1)
{
  if ( a1 )
    ExFreePoolWithTag(a1, 0);
}

```

## disassembly

```asm
0x1400118ec  sub     rsp, 28h
0x1400118f0  test    rcx, rcx
0x1400118f3  jz      short loc_140011903
0x1400118f5  xor     edx, edx; Tag
0x1400118f7  call    cs:__imp_ExFreePoolWithTag
0x1400118fe  nop     dword ptr [rax+rax+00h]
0x140011903  add     rsp, 28h
0x140011907  retn
```
