# CACHED_FILE_INFO::GetCacheKey(void)

- ea: `0x180003a50`
- end: `0x180003a55`
- name: `?GetCacheKey@CACHED_FILE_INFO@@UEBAPEAVIHttpCacheKey@@XZ`
- size: `5`
- prototype: `struct IHttpCacheKey *__fastcall(CACHED_FILE_INFO *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
struct IHttpCacheKey *__fastcall CACHED_FILE_INFO::GetCacheKey(CACHED_FILE_INFO *this)
{
  return (CACHED_FILE_INFO *)((char *)this + 8);
}

```

## disassembly

```asm
0x180003a50  lea     rax, [rcx+8]
0x180003a54  retn
```
