# ATL::CTempBuffer<wchar_t,256,ATL::CCRTAllocator>::~CTempBuffer<wchar_t,256,ATL::CCRTAllocator>(void)

- ea: `0x18000b45c`
- end: `0x18000b473`
- name: `??1?$CTempBuffer@_W$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ`
- size: `23`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18001620e`
- `0x180016220`
- `0x1800162d6`

## callees

- `0x18000b45c`
- `0x18000c974`

## pseudocode

```c
__int64 __fastcall ATL::CTempBuffer<wchar_t,256,ATL::CCRTAllocator>::~CTempBuffer<wchar_t,256,ATL::CCRTAllocator>(
        _QWORD *a1)
{
  __int64 result; // rax

  result = (__int64)(a1 + 1);
  if ( (_QWORD *)*a1 != a1 + 1 )
    return ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::FreeHeap();
  return result;
}

```

## disassembly

```asm
0x18000b45c  sub     rsp, 28h
0x18000b460  lea     rax, [rcx+8]
0x18000b464  cmp     [rcx], rax
0x18000b467  jz      short loc_18000B46E
0x18000b469  call    ?FreeHeap@?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::FreeHeap(void)
0x18000b46e  add     rsp, 28h
0x18000b472  retn
```
