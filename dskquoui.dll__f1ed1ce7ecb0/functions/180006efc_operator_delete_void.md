# operator delete(void *)

- ea: `0x180006efc`
- end: `0x180006f10`
- name: `??3@YAXPEAX@Z`
- size: `20`
- prototype: `void __fastcall(void *)`
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001534`
- `0x1800019c0`
- `0x18001d510`
- `0x18001e18e`

## callees

- `0x180006efc`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006f05`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006f05`

## pseudocode

```c
void __fastcall operator delete(void *a1)
{
  if ( a1 )
    LocalFree(a1);
}

```

## disassembly

```asm
0x180006efc  sub     rsp, 28h
0x180006f00  test    rcx, rcx
0x180006f03  jz      short loc_180006F0B
0x180006f05  call    cs:__imp_LocalFree
0x180006f0b  add     rsp, 28h
0x180006f0f  retn
```
