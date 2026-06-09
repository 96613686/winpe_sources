# W3_SERVER::DecrementThreadCount(void)

- ea: `0x18001ad90`
- end: `0x18001ad9c`
- name: `?DecrementThreadCount@W3_SERVER@@UEAAXXZ`
- size: `12`
- prototype: `void __fastcall(W3_SERVER *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `W3TP!ThreadPoolSetInfo` at `0x18001ad95`

## pseudocode

```c
void __fastcall W3_SERVER::DecrementThreadCount(W3_SERVER *this)
{
  ThreadPoolSetInfo(1, 0);
}

```

## disassembly

```asm
0x18001ad90  xor     edx, edx
0x18001ad92  lea     ecx, [rdx+1]
0x18001ad95  jmp     cs:__imp_?ThreadPoolSetInfo@@YA_KW4THREAD_POOL_INFO@@_K@Z; ThreadPoolSetInfo(THREAD_POOL_INFO,unsigned __int64)
```
