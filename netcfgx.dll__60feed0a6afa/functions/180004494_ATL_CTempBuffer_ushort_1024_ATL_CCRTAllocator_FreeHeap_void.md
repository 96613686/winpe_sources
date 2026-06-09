# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)

- ea: `0x180004494`
- end: `0x1800044b7`
- name: `?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ`
- size: `35`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800030ac`
- `0x18000366c`
- `0x180005038`

## callees

- `0x180004494`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800044ac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800044ac`

## pseudocode

```c
BOOL __fastcall ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(LPVOID *a1)
{
  BOOL result; // eax

  if ( g_hLocalHeap )
    return HeapFree(g_hLocalHeap, 0, *a1);
  return result;
}

```

## disassembly

```asm
0x180004494  sub     rsp, 28h
0x180004498  mov     r8, rcx
0x18000449b  mov     rcx, cs:?g_hLocalHeap@@3PEAXEA; hHeap
0x1800044a2  test    rcx, rcx
0x1800044a5  jz      short loc_1800044B2
0x1800044a7  mov     r8, [r8]; lpMem
0x1800044aa  xor     edx, edx; dwFlags
0x1800044ac  call    cs:__imp_HeapFree
0x1800044b2  add     rsp, 28h
0x1800044b6  retn
```
