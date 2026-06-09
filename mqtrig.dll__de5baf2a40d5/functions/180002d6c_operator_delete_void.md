# operator delete(void *)

- ea: `0x180002d6c`
- end: `0x180002d7c`
- name: `??3@YAXPEAX@Z`
- size: `16`
- prototype: `void __fastcall(void *)`
- caller_count: `17`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x180001860`
- `0x180002008`
- `0x180002058`
- `0x180002108`
- `0x1800022c0`
- `0x180002700`
- `0x18001ebd1`
- `0x18001ec4d`
- `0x18001f7a7`
- `0x18001fc0b`
- `0x18002037e`
- `0x1800203f2`
- `0x180020416`
- `0x18002096f`
- `0x18002136c`
- `0x180021453`
- `0x180021906`

## import_xrefs

- `msvcrt!free` at `0x180002d70`
- `msvcrt!free` at `0x180002d70`

## pseudocode

```c
void __fastcall operator delete(void *a1)
{
  free(a1);
}

```

## disassembly

```asm
0x180002d6c  sub     rsp, 28h
0x180002d70  call    cs:__imp_free
0x180002d76  nop
0x180002d77  add     rsp, 28h
0x180002d7b  retn
```
