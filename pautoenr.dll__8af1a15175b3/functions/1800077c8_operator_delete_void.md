# operator delete(void *)

- ea: `0x1800077c8`
- end: `0x1800077db`
- name: `??3@YAXPEAX@Z`
- size: `19`
- prototype: `void __fastcall(void *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180006604`
- `0x180007330`

## callees

- `0x180005200`
- `0x1800077c8`

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
0x1800077c8  sub     rsp, 28h
0x1800077cc  test    rcx, rcx
0x1800077cf  jz      short loc_1800077D6
0x1800077d1  call    PkiFree
0x1800077d6  add     rsp, 28h
0x1800077da  retn
```
