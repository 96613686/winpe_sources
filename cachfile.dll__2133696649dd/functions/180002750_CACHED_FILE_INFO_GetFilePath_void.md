# CACHED_FILE_INFO::GetFilePath(void)

- ea: `0x180002750`
- end: `0x180002761`
- name: `?GetFilePath@CACHED_FILE_INFO@@UEBAPEBGXZ`
- size: `17`
- prototype: `const unsigned __int16 *__fastcall(CACHED_FILE_INFO *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180004010`

## pseudocode

```c
const unsigned __int16 *__fastcall CACHED_FILE_INFO::GetFilePath(CACHED_FILE_INFO *this)
{
  return (const unsigned __int16 *)(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 1) + 40LL))((char *)this + 8);
}

```

## disassembly

```asm
0x180002750  mov     rax, [rcx+8]
0x180002754  add     rcx, 8
0x180002758  mov     rax, [rax+28h]
0x18000275c  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
