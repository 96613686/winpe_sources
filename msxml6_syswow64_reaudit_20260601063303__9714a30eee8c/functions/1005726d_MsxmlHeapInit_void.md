# MsxmlHeapInit(void)

- ea: `0x1005726d`
- end: `0x100572b4`
- name: `?MsxmlHeapInit@@YGHXZ`
- size: `71`
- prototype: `int __stdcall()`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x1005aadb`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x1005729e`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x1005729e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x10057279`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x10057279`

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
0x1005726d  mov     edi, edi
0x1005726f  push    ebp
0x10057270  mov     ebp, esp
0x10057272  sub     esp, 24h
0x10057275  lea     eax, [ebp+SystemInfo]
0x10057278  push    eax; lpSystemInfo
0x10057279  call    ds:__imp__GetSystemInfo@4; GetSystemInfo(x)
0x1005727f  mov     eax, [ebp+SystemInfo.dwNumberOfProcessors]
0x10057282  cmp     eax, 1
0x10057285  mov     ?g_dwNumberProcessors@@3KA, eax; ulong g_dwNumberProcessors
0x1005728a  mov     eax, [ebp+SystemInfo.dwPageSize]
0x1005728d  setnbe  ?g_fMultiProcessor@@3_NA; bool g_fMultiProcessor
0x10057294  mov     ?g_dwPageSize@@3KA, eax; ulong g_dwPageSize
0x10057299  xor     eax, eax
0x1005729b  push    eax; dwMaximumSize
0x1005729c  push    eax; dwInitialSize
0x1005729d  push    eax; flOptions
0x1005729e  call    ds:__imp__HeapCreate@12; HeapCreate(x,x,x)
0x100572a4  xor     ecx, ecx
0x100572a6  mov     ?g_hMsxmlHeap@@3PAXA, eax; void * g_hMsxmlHeap
0x100572ab  test    eax, eax
0x100572ad  setnz   cl
0x100572b0  mov     eax, ecx
0x100572b2  leave
0x100572b3  retn
```
