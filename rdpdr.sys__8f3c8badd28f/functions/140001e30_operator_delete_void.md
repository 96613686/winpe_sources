# operator delete(void *)

- ea: `0x140001e30`
- end: `0x140001e4d`
- name: `??3@YAXPEAX@Z`
- size: `29`
- prototype: `void __fastcall(void *)`
- caller_count: `51`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140001d60`
- `0x1400027b0`
- `0x140002d44`
- `0x140002efc`
- `0x140002fb0`
- `0x1400031c0`
- `0x140003780`
- `0x1400037c0`
- `0x140003800`
- `0x140003840`
- `0x140003970`
- `0x140004024`
- `0x1400042fc`
- `0x14000487c`
- `0x1400049fc`
- `0x140004ca0`
- `0x140005000`
- `0x1400050cc`
- `0x140005200`
- `0x140005410`
- `0x1400054b0`
- `0x140005a60`
- `0x140005b50`
- `0x140006080`
- `0x1400114c4`
- `0x140011a2c`
- `0x140011df0`
- `0x140012330`
- `0x140014d50`
- `0x140015c50`
- `0x140016130`
- `0x14001652c`
- `0x1400167f4`
- `0x140017544`
- `0x1400176bc`
- `0x140017cac`
- `0x140018ea4`
- `0x14001aba0`
- `0x14001b210`
- `0x14001bcb0`
- `0x14001d2e0`
- `0x14001dd70`
- `0x14001e10c`
- `0x14001e3f0`
- `0x14001eeb0`
- `0x14001f900`
- `0x140029228`
- `0x14002b088`
- `0x14002b120`
- `0x14002c54c`

## callees

- `0x140001e30`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140001e3b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001e3b`

## pseudocode

```c
void __fastcall operator delete(void *a1)
{
  if ( a1 )
    ExFreePoolWithTag(a1, 0);
}

```

## disassembly

```asm
0x140001e30  sub     rsp, 28h
0x140001e34  test    rcx, rcx
0x140001e37  jz      short loc_140001E47
0x140001e39  xor     edx, edx; Tag
0x140001e3b  call    cs:__imp_ExFreePoolWithTag
0x140001e42  nop     dword ptr [rax+rax+00h]
0x140001e47  add     rsp, 28h
0x140001e4b  retn
```
