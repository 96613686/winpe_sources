# CACHED_FILE_INFO::SetFlushed(void)

- ea: `0x180002870`
- end: `0x180002878`
- name: `?SetFlushed@CACHED_FILE_INFO@@UEAAXXZ`
- size: `8`
- prototype: `void __fastcall(CACHED_FILE_INFO *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
void __fastcall CACHED_FILE_INFO::SetFlushed(CACHED_FILE_INFO *this)
{
  *((_BYTE *)this + 320) = 1;
}

```

## disassembly

```asm
0x180002870  mov     byte ptr [rcx+140h], 1
0x180002877  retn
```
