# ATL::CComCachedTearOffObject<CImpIConvertType>::`scalar deleting destructor'(uint)

- ea: `0x18000a9e0`
- end: `0x18000aa00`
- name: `??_G?$CComCachedTearOffObject@VCImpIConvertType@@@ATL@@QEAAPEAXI@Z`
- size: `32`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000b350`
- `0x18000c7e0`

## callees

- `0x180001db8`
- `0x18000a5c0`

## pseudocode

```c
unsigned __int8 *__fastcall ATL::CComCachedTearOffObject<CImpIConvertType>::`scalar deleting destructor'(
        unsigned __int8 *a1)
{
  ATL::CComCachedTearOffObject<CImpIConvertType>::~CComCachedTearOffObject<CImpIConvertType>((__int64)a1);
  operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x18000a9e0  push    rbx
0x18000a9e2  sub     rsp, 20h
0x18000a9e6  mov     rbx, rcx
0x18000a9e9  call    ??1?$CComCachedTearOffObject@VCImpIConvertType@@@ATL@@QEAA@XZ; ATL::CComCachedTearOffObject<CImpIConvertType>::~CComCachedTearOffObject<CImpIConvertType>(void)
0x18000a9ee  mov     rcx, rbx; void *
0x18000a9f1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a9f6  mov     rax, rbx
0x18000a9f9  add     rsp, 20h
0x18000a9fd  pop     rbx
0x18000a9fe  retn
```
