# ATL::CComCachedTearOffObject<CImpIAccessor>::`scalar deleting destructor'(uint)

- ea: `0x18000a918`
- end: `0x18000a938`
- name: `??_G?$CComCachedTearOffObject@VCImpIAccessor@@@ATL@@QEAAPEAXI@Z`
- size: `32`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000aee0`
- `0x18000c6a0`

## callees

- `0x180001db8`
- `0x18000a4f8`

## pseudocode

```c
unsigned __int8 *__fastcall ATL::CComCachedTearOffObject<CImpIAccessor>::`scalar deleting destructor'(
        unsigned __int8 *a1)
{
  ATL::CComCachedTearOffObject<CImpIAccessor>::~CComCachedTearOffObject<CImpIAccessor>((__int64)a1);
  operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x18000a918  push    rbx
0x18000a91a  sub     rsp, 20h
0x18000a91e  mov     rbx, rcx
0x18000a921  call    ??1?$CComCachedTearOffObject@VCImpIAccessor@@@ATL@@QEAA@XZ; ATL::CComCachedTearOffObject<CImpIAccessor>::~CComCachedTearOffObject<CImpIAccessor>(void)
0x18000a926  mov     rcx, rbx; void *
0x18000a929  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a92e  mov     rax, rbx
0x18000a931  add     rsp, 20h
0x18000a935  pop     rbx
0x18000a936  retn
```
