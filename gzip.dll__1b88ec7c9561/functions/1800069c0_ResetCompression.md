# ResetCompression

- ea: `0x1800069c0`
- end: `0x180006a36`
- name: `ResetCompression`
- size: `118`
- prototype: `HRESULT __stdcall(PVOID context)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800059b8`
- `0x1800069c0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800069e0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006a00`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006a20`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800069e0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006a00`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006a20`

## pseudocode

```c
HRESULT __stdcall ResetCompression(PVOID context)
{
  __int64 v2; // rcx
  void *v3; // r8
  void *v4; // r8
  void *v5; // r8

  InternalResetCompression((__int64)context);
  v3 = *(void **)(v2 + 80);
  if ( v3 )
  {
    HeapFree(g_hHeap, 0, v3);
    *((_QWORD *)context + 10) = 0;
  }
  v4 = (void *)*((_QWORD *)context + 11);
  if ( v4 )
  {
    HeapFree(g_hHeap, 0, v4);
    *((_QWORD *)context + 11) = 0;
  }
  v5 = (void *)*((_QWORD *)context + 12);
  if ( v5 )
  {
    HeapFree(g_hHeap, 0, v5);
    *((_QWORD *)context + 12) = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x1800069c0  push    rbx
0x1800069c2  sub     rsp, 20h
0x1800069c6  mov     rbx, rcx
0x1800069c9  call    InternalResetCompression
0x1800069ce  mov     r8, [rcx+50h]; lpMem
0x1800069d2  test    r8, r8
0x1800069d5  jz      short loc_1800069EE
0x1800069d7  mov     rcx, cs:g_hHeap; hHeap
0x1800069de  xor     edx, edx; dwFlags
0x1800069e0  call    cs:__imp_HeapFree
0x1800069e6  mov     qword ptr [rbx+50h], 0
0x1800069ee  mov     r8, [rbx+58h]; lpMem
0x1800069f2  test    r8, r8
0x1800069f5  jz      short loc_180006A0E
0x1800069f7  mov     rcx, cs:g_hHeap; hHeap
0x1800069fe  xor     edx, edx; dwFlags
0x180006a00  call    cs:__imp_HeapFree
0x180006a06  mov     qword ptr [rbx+58h], 0
0x180006a0e  mov     r8, [rbx+60h]; lpMem
0x180006a12  test    r8, r8
0x180006a15  jz      short loc_180006A2E
0x180006a17  mov     rcx, cs:g_hHeap; hHeap
0x180006a1e  xor     edx, edx; dwFlags
0x180006a20  call    cs:__imp_HeapFree
0x180006a26  mov     qword ptr [rbx+60h], 0
0x180006a2e  xor     eax, eax
0x180006a30  add     rsp, 20h
0x180006a34  pop     rbx
0x180006a35  retn
```
