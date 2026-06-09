# CACHED_FILE_INFO::GetFileBuffer(void)

- ea: `0x180002740`
- end: `0x180002748`
- name: `?GetFileBuffer@CACHED_FILE_INFO@@UEBAPEBEXZ`
- size: `8`
- prototype: `const unsigned __int8 *__fastcall(CACHED_FILE_INFO *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
const unsigned __int8 *__fastcall CACHED_FILE_INFO::GetFileBuffer(CACHED_FILE_INFO *this)
{
  return (const unsigned __int8 *)*((_QWORD *)this + 45);
}

```

## disassembly

```asm
0x180002740  mov     rax, [rcx+168h]
0x180002747  retn
```
