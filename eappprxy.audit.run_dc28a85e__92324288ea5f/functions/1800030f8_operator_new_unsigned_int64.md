# operator new(unsigned __int64)

- ea: `0x1800030f8`
- end: `0x180003139`
- name: `??2@YAPEAX_K@Z`
- size: `65`
- prototype: `void *__fastcall(SIZE_T dwBytes)`
- caller_count: `11`
- callee_count: `2`
- tags: ``

## callers

- `0x180001120`
- `0x1800075c0`
- `0x180008850`
- `0x180008cf0`
- `0x180009230`
- `0x1800096e0`
- `0x18000b408`
- `0x18000b824`
- `0x18000b8bc`
- `0x18000bac0`
- `0x18000dc34`

## callees

- `0x1800030f8`
- `0x18000d6a0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000310d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000310d`

## pseudocode

```c
LPVOID __fastcall operator new(SIZE_T dwBytes)
{
  unsigned int v1; // ebx
  LPVOID result; // rax

  v1 = dwBytes;
  result = HeapAlloc(HeapAllocator::heap, 0, dwBytes);
  if ( !result )
    LowMemoryError::Throw(L"HeapAlloc");
  _InterlockedAdd(&dword_180015488, v1);
  return result;
}

```

## disassembly

```asm
0x1800030f8  push    rbx
0x1800030fa  sub     rsp, 20h
0x1800030fe  mov     rbx, rcx
0x180003101  mov     r8, rcx; dwBytes
0x180003104  mov     rcx, cs:?heap@HeapAllocator@@0V?$StaticObject@VHeap@@@@A; hHeap
0x18000310b  xor     edx, edx; dwFlags
0x18000310d  call    cs:__imp_HeapAlloc
0x180003114  nop     dword ptr [rax+rax+00h]
0x180003119  test    rax, rax
0x18000311c  jz      short loc_18000312C
0x18000311e  lock add cs:dword_180015488, ebx
0x180003125  add     rsp, 20h
0x180003129  pop     rbx
0x18000312a  retn
0x18000312c  lea     rcx, aHeapalloc; "HeapAlloc"
0x180003133  call    ?Throw@LowMemoryError@@SAXPEB_W@Z; LowMemoryError::Throw(wchar_t const *)
```
