# _CopyAndAllocateMatchValue_::_1_::dtor$0

- ea: `0x1800141a0`
- end: `0x1800141ac`
- name: `_CopyAndAllocateMatchValue_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18000563c`

## pseudocode

```c
void __fastcall CopyAndAllocateMatchValue_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  TSimpleDeallocator<unsigned char *,void,void *,&void CoTaskMemFree(void *)>::~TSimpleDeallocator<unsigned char *,void,void *,&void CoTaskMemFree(void *)>((void **)(a2 + 80));
}

```

## disassembly

```asm
0x1800141a0  lea     rcx, [rdx+50h]
0x1800141a7  jmp     ??1?$TSimpleDeallocator@PEAEXPEAX$1?CoTaskMemFree@@YAXPEAX@Z@@QEAA@XZ; TSimpleDeallocator<uchar *,void,void *,&CoTaskMemFree(void *)>::~TSimpleDeallocator<uchar *,void,void *,&CoTaskMemFree(void *)>(void)
```
