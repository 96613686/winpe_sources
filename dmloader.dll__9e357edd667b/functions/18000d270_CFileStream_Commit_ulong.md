# CFileStream::Commit(ulong)

- ea: `0x18000d270`
- end: `0x18000d276`
- name: `?Commit@CFileStream@@UEAAJK@Z`
- size: `6`
- prototype: `__int64 __fastcall(CFileStream *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall CFileStream::Commit(CFileStream *this)
{
  return 2147500033LL;
}

```

## disassembly

```asm
0x18000d270  mov     eax, 80004001h
0x18000d275  retn
```
