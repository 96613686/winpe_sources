# operator delete(void *)

- ea: `0x180009c68`
- end: `0x180009c7b`
- name: `??3@YAXPEAX@Z`
- size: `19`
- prototype: `void __fastcall(void *)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180009db0`
- `0x180009de8`
- `0x18000a1c8`

## callees

- `0x180009c68`
- `0x180009c84`

## pseudocode

```c
void __fastcall operator delete(void *a1)
{
  if ( a1 )
    PkiFree(a1);
}

```

## disassembly

```asm
0x180009c68  sub     rsp, 28h
0x180009c6c  test    rcx, rcx
0x180009c6f  jz      short loc_180009C76
0x180009c71  call    PkiFree
0x180009c76  add     rsp, 28h
0x180009c7a  retn
```
