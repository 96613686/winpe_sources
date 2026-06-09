# ATL::CComCachedTearOffObject<CImpIColumnsRowset>::`scalar deleting destructor'(uint)

- ea: `0x18000a990`
- end: `0x18000a9b0`
- name: `??_G?$CComCachedTearOffObject@VCImpIColumnsRowset@@@ATL@@QEAAPEAXI@Z`
- size: `32`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000b180`
- `0x18000c760`

## callees

- `0x180001db8`
- `0x18000a570`

## pseudocode

```c
unsigned __int8 *__fastcall ATL::CComCachedTearOffObject<CImpIColumnsRowset>::`scalar deleting destructor'(
        unsigned __int8 *a1)
{
  ATL::CComCachedTearOffObject<CImpIColumnsRowset>::~CComCachedTearOffObject<CImpIColumnsRowset>((__int64)a1);
  operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x18000a990  push    rbx
0x18000a992  sub     rsp, 20h
0x18000a996  mov     rbx, rcx
0x18000a999  call    ??1?$CComCachedTearOffObject@VCImpIColumnsRowset@@@ATL@@QEAA@XZ; ATL::CComCachedTearOffObject<CImpIColumnsRowset>::~CComCachedTearOffObject<CImpIColumnsRowset>(void)
0x18000a99e  mov     rcx, rbx; void *
0x18000a9a1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a9a6  mov     rax, rbx
0x18000a9a9  add     rsp, 20h
0x18000a9ad  pop     rbx
0x18000a9ae  retn
```
