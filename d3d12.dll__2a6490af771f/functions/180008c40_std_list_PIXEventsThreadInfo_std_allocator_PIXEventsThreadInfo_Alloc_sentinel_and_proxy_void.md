# std::list<PIXEventsThreadInfo,std::allocator<PIXEventsThreadInfo>>::_Alloc_sentinel_and_proxy(void)

- ea: `0x180008c40`
- end: `0x180008c61`
- name: `?_Alloc_sentinel_and_proxy@?$list@UPIXEventsThreadInfo@@V?$allocator@UPIXEventsThreadInfo@@@std@@@std@@AEAAXXZ`
- size: `33`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180008c20`

## callees

- `0x18000b828`

## pseudocode

```c
_QWORD *std::list<PIXEventsThreadInfo>::_Alloc_sentinel_and_proxy()
{
  _QWORD *result; // rax

  result = operator new(0x28u);
  *result = result;
  result[1] = result;
  qword_18001E8A0 = (__int64)result;
  return result;
}

```

## disassembly

```asm
0x180008c40  sub     rsp, 28h
0x180008c44  mov     ecx, 28h ; '('; Size
0x180008c49  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008c4e  mov     [rax], rax
0x180008c51  mov     [rax+8], rax
0x180008c55  mov     cs:qword_18001E8A0, rax
0x180008c5c  add     rsp, 28h
0x180008c60  retn
```
