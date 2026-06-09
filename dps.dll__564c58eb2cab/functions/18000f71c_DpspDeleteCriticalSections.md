# DpspDeleteCriticalSections

- ea: `0x18000f71c`
- end: `0x18000f76c`
- name: `DpspDeleteCriticalSections`
- size: `80`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180006188`
- `0x18000e024`

## callees

- `0x180017818`

## pseudocode

```c
__int64 DpspDeleteCriticalSections()
{
  WdipDeleteCriticalSection(g_csDPS);
  WdipDeleteCriticalSection(&g_csFast);
  WdipDeleteCriticalSection(&g_csDMList);
  WdipDeleteCriticalSection(&g_csHostList);
  WdipDeleteCriticalSection(&g_csUserList);
  return WdipDeleteCriticalSection(&g_csPreAllocated);
}

```

## disassembly

```asm
0x18000f71c  sub     rsp, 28h
0x18000f720  lea     rcx, g_csDPS
0x18000f727  call    WdipDeleteCriticalSection
0x18000f72c  lea     rcx, g_csFast
0x18000f733  call    WdipDeleteCriticalSection
0x18000f738  lea     rcx, g_csDMList
0x18000f73f  call    WdipDeleteCriticalSection
0x18000f744  lea     rcx, g_csHostList
0x18000f74b  call    WdipDeleteCriticalSection
0x18000f750  lea     rcx, g_csUserList
0x18000f757  call    WdipDeleteCriticalSection
0x18000f75c  lea     rcx, g_csPreAllocated
0x18000f763  add     rsp, 28h
0x18000f767  jmp     WdipDeleteCriticalSection
```
