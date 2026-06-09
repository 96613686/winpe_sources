# MsxmlHeapInit(void)

- ea: `0x1800aafa8`
- end: `0x1800ab00a`
- name: `?MsxmlHeapInit@@YAHXZ`
- size: `98`
- prototype: `int __fastcall()`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x18008a58c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x1800aafed`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x1800aafed`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x1800aafc2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x1800aafc2`

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
0x1800aafa8  mov     rax, rsp
0x1800aafab  sub     rsp, 58h
0x1800aafaf  xorps   xmm0, xmm0
0x1800aafb2  lea     rcx, [rax-38h]; lpSystemInfo
0x1800aafb6  movups  xmmword ptr [rax-38h], xmm0
0x1800aafba  movups  xmmword ptr [rax-28h], xmm0
0x1800aafbe  movups  xmmword ptr [rax-18h], xmm0
0x1800aafc2  call    cs:__imp_GetSystemInfo
0x1800aafc8  mov     eax, [rsp+58h+var_38.dwNumberOfProcessors]
0x1800aafcc  cmp     eax, 1
0x1800aafcf  mov     cs:?g_dwNumberProcessors@@3KA, eax; ulong g_dwNumberProcessors
0x1800aafd5  mov     eax, [rsp+58h+var_38.dwPageSize]
0x1800aafd9  setnbe  cs:?g_fMultiProcessor@@3_NA; bool g_fMultiProcessor
0x1800aafe0  xor     r8d, r8d; dwMaximumSize
0x1800aafe3  mov     cs:?g_dwPageSize@@3KA, eax; ulong g_dwPageSize
0x1800aafe9  xor     edx, edx; dwInitialSize
0x1800aafeb  xor     ecx, ecx; flOptions
0x1800aafed  call    cs:__imp_HeapCreate
0x1800aaff3  mov     rcx, rax
0x1800aaff6  mov     cs:?g_hMsxmlHeap@@3PEAXEA, rax; void * g_hMsxmlHeap
0x1800aaffd  xor     eax, eax
0x1800aafff  test    rcx, rcx
0x1800ab002  setnz   al
0x1800ab005  add     rsp, 58h
0x1800ab009  retn
```
