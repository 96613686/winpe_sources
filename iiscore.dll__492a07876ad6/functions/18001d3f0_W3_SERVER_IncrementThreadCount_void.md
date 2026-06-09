# W3_SERVER::IncrementThreadCount(void)

- ea: `0x18001d3f0`
- end: `0x18001d3fb`
- name: `?IncrementThreadCount@W3_SERVER@@UEAAXXZ`
- size: `11`
- prototype: `void __fastcall(W3_SERVER *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `W3TP!ThreadPoolSetInfo` at `0x18001d3f4`

## pseudocode

```c
void __fastcall W3_SERVER::IncrementThreadCount(W3_SERVER *this)
{
  ThreadPoolSetInfo(0, 0);
}

```

## disassembly

```asm
0x18001d3f0  xor     edx, edx
0x18001d3f2  xor     ecx, ecx
0x18001d3f4  jmp     cs:__imp_?ThreadPoolSetInfo@@YA_KW4THREAD_POOL_INFO@@_K@Z; ThreadPoolSetInfo(THREAD_POOL_INFO,unsigned __int64)
```
