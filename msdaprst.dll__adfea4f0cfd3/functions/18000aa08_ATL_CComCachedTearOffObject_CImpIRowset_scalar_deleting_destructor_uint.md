# ATL::CComCachedTearOffObject<CImpIRowset>::`scalar deleting destructor'(uint)

- ea: `0x18000aa08`
- end: `0x18000aa28`
- name: `??_G?$CComCachedTearOffObject@VCImpIRowset@@@ATL@@QEAAPEAXI@Z`
- size: `32`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000b430`
- `0x18000c820`

## callees

- `0x180001db8`
- `0x18000a5e8`

## pseudocode

```c
unsigned __int8 *__fastcall ATL::CComCachedTearOffObject<CImpIRowset>::`scalar deleting destructor'(
        unsigned __int8 *a1)
{
  ATL::CComCachedTearOffObject<CImpIRowset>::~CComCachedTearOffObject<CImpIRowset>();
  operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x18000aa08  push    rbx
0x18000aa0a  sub     rsp, 20h
0x18000aa0e  mov     rbx, rcx
0x18000aa11  call    ??1?$CComCachedTearOffObject@VCImpIRowset@@@ATL@@QEAA@XZ; ATL::CComCachedTearOffObject<CImpIRowset>::~CComCachedTearOffObject<CImpIRowset>(void)
0x18000aa16  mov     rcx, rbx; void *
0x18000aa19  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000aa1e  mov     rax, rbx
0x18000aa21  add     rsp, 20h
0x18000aa25  pop     rbx
0x18000aa26  retn
```
