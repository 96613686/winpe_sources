# MsxmlHeapInit(void)

- ea: `0x1800ac468`
- end: `0x1800ac4d7`
- name: `?MsxmlHeapInit@@YAHXZ`
- size: `111`
- prototype: `int __fastcall()`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x18008a820`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x1800ac4b3`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x1800ac4b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x1800ac482`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x1800ac482`

## pseudocode

```c
_BOOL8 __fastcall MsxmlHeapInit()
{
  _SYSTEM_INFO v1; // [rsp+20h] [rbp-38h] BYREF

  memset(&v1, 0, sizeof(v1));
  GetSystemInfo(&v1);
  g_dwNumberProcessors = v1.dwNumberOfProcessors;
  g_fMultiProcessor = v1.dwNumberOfProcessors > 1;
  g_dwPageSize = v1.dwPageSize;
  g_hMsxmlHeap = HeapCreate(0, 0, 0);
  return g_hMsxmlHeap != 0;
}

```

## disassembly

```asm
0x1800ac468  mov     rax, rsp
0x1800ac46b  sub     rsp, 58h
0x1800ac46f  xorps   xmm0, xmm0
0x1800ac472  lea     rcx, [rax-38h]; lpSystemInfo
0x1800ac476  movups  xmmword ptr [rax-38h], xmm0
0x1800ac47a  movups  xmmword ptr [rax-28h], xmm0
0x1800ac47e  movups  xmmword ptr [rax-18h], xmm0
0x1800ac482  call    cs:__imp_GetSystemInfo
0x1800ac489  nop     dword ptr [rax+rax+00h]
0x1800ac48e  mov     eax, [rsp+58h+var_38.dwNumberOfProcessors]
0x1800ac492  cmp     eax, 1
0x1800ac495  mov     cs:?g_dwNumberProcessors@@3KA, eax; ulong g_dwNumberProcessors
0x1800ac49b  mov     eax, [rsp+58h+var_38.dwPageSize]
0x1800ac49f  setnbe  cs:?g_fMultiProcessor@@3_NA; bool g_fMultiProcessor
0x1800ac4a6  xor     r8d, r8d; dwMaximumSize
0x1800ac4a9  mov     cs:?g_dwPageSize@@3KA, eax; ulong g_dwPageSize
0x1800ac4af  xor     edx, edx; dwInitialSize
0x1800ac4b1  xor     ecx, ecx; flOptions
0x1800ac4b3  call    cs:__imp_HeapCreate
0x1800ac4ba  nop     dword ptr [rax+rax+00h]
0x1800ac4bf  mov     rcx, rax
0x1800ac4c2  mov     cs:?g_hMsxmlHeap@@3PEAXEA, rax; void * g_hMsxmlHeap
0x1800ac4c9  xor     eax, eax
0x1800ac4cb  test    rcx, rcx
0x1800ac4ce  setnz   al
0x1800ac4d1  add     rsp, 58h
0x1800ac4d5  retn
```
