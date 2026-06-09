# IFileKey::GetCacheName(void)

- ea: `0x180003a60`
- end: `0x180003a68`
- name: `?GetCacheName@IFileKey@@UEBAPEBGXZ`
- size: `8`
- prototype: `const unsigned __int16 *__fastcall(IFileKey *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
const unsigned __int16 *__fastcall IFileKey::GetCacheName(IFileKey *this)
{
  return L"FILE";
}

```

## disassembly

```asm
0x180003a60  lea     rax, aFile; "FILE"
0x180003a67  retn
```
