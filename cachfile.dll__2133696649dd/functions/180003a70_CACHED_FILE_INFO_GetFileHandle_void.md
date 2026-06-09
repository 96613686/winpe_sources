# CACHED_FILE_INFO::GetFileHandle(void)

- ea: `0x180003a70`
- end: `0x180003a75`
- name: `?GetFileHandle@CACHED_FILE_INFO@@UEBAPEAXXZ`
- size: `5`
- prototype: `void *__fastcall(CACHED_FILE_INFO *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall CACHED_FILE_INFO::GetFileHandle(CACHED_FILE_INFO *this)
{
  return -1;
}

```

## disassembly

```asm
0x180003a70  or      rax, 0FFFFFFFFFFFFFFFFh
0x180003a74  retn
```
