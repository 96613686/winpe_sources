# CACHED_FILE_INFO::GetLastModifiedString(void)

- ea: `0x180002850`
- end: `0x180002858`
- name: `?GetLastModifiedString@CACHED_FILE_INFO@@UEBAPEBDXZ`
- size: `8`
- prototype: `const char *__fastcall(CACHED_FILE_INFO *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
const char *__fastcall CACHED_FILE_INFO::GetLastModifiedString(CACHED_FILE_INFO *this)
{
  return (char *)this + 400;
}

```

## disassembly

```asm
0x180002850  lea     rax, [rcx+190h]
0x180002857  retn
```
