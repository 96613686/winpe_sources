# DestroyCompression

- ea: `0x180006950`
- end: `0x1800069b9`
- name: `DestroyCompression`
- size: `105`
- prototype: `void __stdcall(PVOID context)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180006950`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000696b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006983`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000699b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000696b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006983`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000699b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800069b2`

## pseudocode

```c
void __stdcall DestroyCompression(PVOID context)
{
  void *v1; // r8
  void *v3; // r8
  void *v4; // r8

  v1 = (void *)*((_QWORD *)context + 10);
  if ( v1 )
    HeapFree(g_hHeap, 0, v1);
  v3 = (void *)*((_QWORD *)context + 11);
  if ( v3 )
    HeapFree(g_hHeap, 0, v3);
  v4 = (void *)*((_QWORD *)context + 12);
  if ( v4 )
    HeapFree(g_hHeap, 0, v4);
  HeapFree(g_hHeap, 0, context);
}

```

## disassembly

```asm
0x180006950  push    rbx
0x180006952  sub     rsp, 20h
0x180006956  mov     r8, [rcx+50h]; lpMem
0x18000695a  mov     rbx, rcx
0x18000695d  test    r8, r8
0x180006960  jz      short loc_180006971
0x180006962  mov     rcx, cs:g_hHeap; hHeap
0x180006969  xor     edx, edx; dwFlags
0x18000696b  call    cs:__imp_HeapFree
0x180006971  mov     r8, [rbx+58h]; lpMem
0x180006975  test    r8, r8
0x180006978  jz      short loc_180006989
0x18000697a  mov     rcx, cs:g_hHeap; hHeap
0x180006981  xor     edx, edx; dwFlags
0x180006983  call    cs:__imp_HeapFree
0x180006989  mov     r8, [rbx+60h]; lpMem
0x18000698d  test    r8, r8
0x180006990  jz      short loc_1800069A1
0x180006992  mov     rcx, cs:g_hHeap; hHeap
0x180006999  xor     edx, edx; dwFlags
0x18000699b  call    cs:__imp_HeapFree
0x1800069a1  mov     rcx, cs:g_hHeap
0x1800069a8  mov     r8, rbx
0x1800069ab  xor     edx, edx
0x1800069ad  add     rsp, 20h
0x1800069b1  pop     rbx
0x1800069b2  jmp     cs:__imp_HeapFree
```
