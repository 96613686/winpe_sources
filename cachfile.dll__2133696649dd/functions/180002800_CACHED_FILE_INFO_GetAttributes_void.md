# CACHED_FILE_INFO::GetAttributes(void)

- ea: `0x180002800`
- end: `0x180002807`
- name: `?GetAttributes@CACHED_FILE_INFO@@UEBAKXZ`
- size: `7`
- prototype: `unsigned int __fastcall(CACHED_FILE_INFO *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall CACHED_FILE_INFO::GetAttributes(CACHED_FILE_INFO *this)
{
  return *((unsigned int *)this + 84);
}

```

## disassembly

```asm
0x180002800  mov     eax, [rcx+150h]
0x180002806  retn
```
