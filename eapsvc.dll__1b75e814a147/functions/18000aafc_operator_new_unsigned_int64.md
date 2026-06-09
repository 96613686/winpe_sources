# operator new(unsigned __int64)

- ea: `0x18000aafc`
- end: `0x18000ab36`
- name: `??2@YAPEAX_K@Z`
- size: `58`
- prototype: `LPVOID __fastcall(SIZE_T dwBytes)`
- caller_count: `12`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ac00`
- `0x18000b5c0`
- `0x18000c7b8`
- `0x18000c880`
- `0x18000d0f8`
- `0x18000d3b8`
- `0x18000de8c`
- `0x18000e978`
- `0x18000f77c`
- `0x18001100c`
- `0x18001129c`
- `0x18001140c`

## callees

- `0x18000aafc`
- `0x18000dc0c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ab11`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ab11`

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
  _InterlockedAdd(&dword_180020B58, v1);
  return result;
}

```

## disassembly

```asm
0x18000aafc  push    rbx
0x18000aafe  sub     rsp, 20h
0x18000ab02  mov     rbx, rcx
0x18000ab05  mov     r8, rcx; dwBytes
0x18000ab08  mov     rcx, cs:?heap@HeapAllocator@@0V?$StaticObject@VHeap@@@@A; hHeap
0x18000ab0f  xor     edx, edx; dwFlags
0x18000ab11  call    cs:__imp_HeapAlloc
0x18000ab17  test    rax, rax
0x18000ab1a  jz      short loc_18000AB29
0x18000ab1c  lock add cs:dword_180020B58, ebx
0x18000ab23  add     rsp, 20h
0x18000ab27  pop     rbx
0x18000ab28  retn
0x18000ab29  lea     rcx, aHeapalloc; "HeapAlloc"
0x18000ab30  call    ?Throw@LowMemoryError@@SAXPEB_W@Z; LowMemoryError::Throw(wchar_t const *)
```
