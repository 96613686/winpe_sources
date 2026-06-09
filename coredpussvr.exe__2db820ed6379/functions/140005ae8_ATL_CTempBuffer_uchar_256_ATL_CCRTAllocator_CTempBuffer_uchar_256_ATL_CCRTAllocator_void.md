# ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)

- ea: `0x140005ae8`
- end: `0x140005b00`
- name: `??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ`
- size: `24`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1400091c9`
- `0x1400091db`
- `0x14000927f`

## callees

- `0x140005ae8`
- `0x140006e04`

## pseudocode

```c
__int64 __fastcall ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(
        _QWORD *a1)
{
  __int64 result; // rax

  result = (__int64)(a1 + 1);
  if ( (_QWORD *)*a1 != a1 + 1 )
    return ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(a1);
  return result;
}

```

## disassembly

```asm
0x140005ae8  sub     rsp, 28h
0x140005aec  lea     rax, [rcx+8]
0x140005af0  cmp     [rcx], rax
0x140005af3  jz      short loc_140005AFA
0x140005af5  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x140005afa  add     rsp, 28h
0x140005afe  retn
```
