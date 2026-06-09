# CFreeBlockEntry::Delete(void *)

- ea: `0x14000fca0`
- end: `0x14000fcaf`
- name: `?Delete@CFreeBlockEntry@@SAXPEAX@Z`
- size: `15`
- prototype: `void __fastcall(void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x1400010a4`

## pseudocode

```c
void __fastcall CFreeBlockEntry::Delete(void *a1)
{
  operator delete(a1);
}

```

## disassembly

```asm
0x14000fca0  sub     rsp, 28h
0x14000fca4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000fca9  add     rsp, 28h
0x14000fcad  retn
```
