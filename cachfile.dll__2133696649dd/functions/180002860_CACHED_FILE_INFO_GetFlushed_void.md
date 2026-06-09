# CACHED_FILE_INFO::GetFlushed(void)

- ea: `0x180002860`
- end: `0x180002868`
- name: `?GetFlushed@CACHED_FILE_INFO@@UEBAHXZ`
- size: `8`
- prototype: `__int64 __fastcall(CACHED_FILE_INFO *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall CACHED_FILE_INFO::GetFlushed(CACHED_FILE_INFO *this)
{
  return *((unsigned __int8 *)this + 320);
}

```

## disassembly

```asm
0x180002860  movzx   eax, byte ptr [rcx+140h]
0x180002867  retn
```
