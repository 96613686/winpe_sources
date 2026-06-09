# CACHED_FILE_INFO::ResetTTL(void)

- ea: `0x180002720`
- end: `0x180002736`
- name: `?ResetTTL@CACHED_FILE_INFO@@UEAAXXZ`
- size: `22`
- prototype: `void __fastcall(CACHED_FILE_INFO *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
void __fastcall CACHED_FILE_INFO::ResetTTL(CACHED_FILE_INFO *this)
{
  _InterlockedIncrement((volatile signed __int32 *)this + 66);
  _InterlockedIncrement((volatile signed __int32 *)g_pFileCache + 48);
}

```

## disassembly

```asm
0x180002720  lock inc dword ptr [rcx+108h]
0x180002727  mov     rax, cs:?g_pFileCache@@3PEAVFILE_CACHE@@EA; FILE_CACHE * g_pFileCache
0x18000272e  lock inc dword ptr [rax+0C0h]
0x180002735  retn
```
