# ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)

- ea: `0x180008cd0`
- end: `0x180008ce7`
- name: `??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ`
- size: `23`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000919c`
- `0x18000ac80`
- `0x18000cd0b`
- `0x18000cd77`

## callees

- `0x180008cd0`
- `0x18000a1f8`

## pseudocode

```c
__int64 __fastcall ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(
        _QWORD *a1)
{
  __int64 result; // rax

  result = (__int64)(a1 + 1);
  if ( (_QWORD *)*a1 != a1 + 1 )
    return ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap();
  return result;
}

```

## disassembly

```asm
0x180008cd0  sub     rsp, 28h
0x180008cd4  lea     rax, [rcx+8]
0x180008cd8  cmp     [rcx], rax
0x180008cdb  jz      short loc_180008CE2
0x180008cdd  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180008ce2  add     rsp, 28h
0x180008ce6  retn
```
