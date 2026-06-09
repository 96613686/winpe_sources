# MsxmlHeapInit(void)

- ea: `0x100572fd`
- end: `0x10057344`
- name: `?MsxmlHeapInit@@YGHXZ`
- size: `71`
- prototype: `int __stdcall()`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x1005ab6b`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x1005732e`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x1005732e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x10057309`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x10057309`

## pseudocode

```c
BOOL __stdcall MsxmlHeapInit()
{
  _SYSTEM_INFO SystemInfo; // [esp+0h] [ebp-24h] BYREF

  GetSystemInfo(&SystemInfo);
  g_dwNumberProcessors = SystemInfo.dwNumberOfProcessors;
  g_fMultiProcessor = SystemInfo.dwNumberOfProcessors > 1;
  g_dwPageSize = SystemInfo.dwPageSize;
  g_hMsxmlHeap = HeapCreate(0, 0, 0);
  return g_hMsxmlHeap != 0;
}

```

## disassembly

```asm
0x100572fd  mov     edi, edi
0x100572ff  push    ebp
0x10057300  mov     ebp, esp
0x10057302  sub     esp, 24h
0x10057305  lea     eax, [ebp+SystemInfo]
0x10057308  push    eax; lpSystemInfo
0x10057309  call    ds:__imp__GetSystemInfo@4; GetSystemInfo(x)
0x1005730f  mov     eax, [ebp+SystemInfo.dwNumberOfProcessors]
0x10057312  cmp     eax, 1
0x10057315  mov     ?g_dwNumberProcessors@@3KA, eax; ulong g_dwNumberProcessors
0x1005731a  mov     eax, [ebp+SystemInfo.dwPageSize]
0x1005731d  setnbe  ?g_fMultiProcessor@@3_NA; bool g_fMultiProcessor
0x10057324  mov     ?g_dwPageSize@@3KA, eax; ulong g_dwPageSize
0x10057329  xor     eax, eax
0x1005732b  push    eax; dwMaximumSize
0x1005732c  push    eax; dwInitialSize
0x1005732d  push    eax; flOptions
0x1005732e  call    ds:__imp__HeapCreate@12; HeapCreate(x,x,x)
0x10057334  xor     ecx, ecx
0x10057336  mov     ?g_hMsxmlHeap@@3PAXA, eax; void * g_hMsxmlHeap
0x1005733b  test    eax, eax
0x1005733d  setnz   cl
0x10057340  mov     eax, ecx
0x10057342  leave
0x10057343  retn
```
