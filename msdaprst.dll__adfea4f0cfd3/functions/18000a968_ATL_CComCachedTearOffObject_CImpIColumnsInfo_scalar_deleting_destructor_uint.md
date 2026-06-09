# ATL::CComCachedTearOffObject<CImpIColumnsInfo>::`scalar deleting destructor'(uint)

- ea: `0x18000a968`
- end: `0x18000a988`
- name: `??_G?$CComCachedTearOffObject@VCImpIColumnsInfo@@@ATL@@QEAAPEAXI@Z`
- size: `32`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000b0a0`
- `0x18000c720`

## callees

- `0x180001db8`
- `0x18000a548`

## pseudocode

```c
unsigned __int8 *__fastcall ATL::CComCachedTearOffObject<CImpIColumnsInfo>::`scalar deleting destructor'(
        unsigned __int8 *a1)
{
  ATL::CComCachedTearOffObject<CImpIColumnsInfo>::~CComCachedTearOffObject<CImpIColumnsInfo>((__int64)a1);
  operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x18000a968  push    rbx
0x18000a96a  sub     rsp, 20h
0x18000a96e  mov     rbx, rcx
0x18000a971  call    ??1?$CComCachedTearOffObject@VCImpIColumnsInfo@@@ATL@@QEAA@XZ; ATL::CComCachedTearOffObject<CImpIColumnsInfo>::~CComCachedTearOffObject<CImpIColumnsInfo>(void)
0x18000a976  mov     rcx, rbx; void *
0x18000a979  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a97e  mov     rax, rbx
0x18000a981  add     rsp, 20h
0x18000a985  pop     rbx
0x18000a986  retn
```
