# ATL::CComCachedTearOffObject<CImpIChapteredRowset>::`scalar deleting destructor'(uint)

- ea: `0x18000a940`
- end: `0x18000a960`
- name: `??_G?$CComCachedTearOffObject@VCImpIChapteredRowset@@@ATL@@QEAAPEAXI@Z`
- size: `32`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000afc0`
- `0x18000c6e0`

## callees

- `0x180001db8`
- `0x18000a520`

## pseudocode

```c
unsigned __int8 *__fastcall ATL::CComCachedTearOffObject<CImpIChapteredRowset>::`scalar deleting destructor'(
        unsigned __int8 *a1)
{
  ATL::CComCachedTearOffObject<CImpIChapteredRowset>::~CComCachedTearOffObject<CImpIChapteredRowset>((__int64)a1);
  operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x18000a940  push    rbx
0x18000a942  sub     rsp, 20h
0x18000a946  mov     rbx, rcx
0x18000a949  call    ??1?$CComCachedTearOffObject@VCImpIChapteredRowset@@@ATL@@QEAA@XZ; ATL::CComCachedTearOffObject<CImpIChapteredRowset>::~CComCachedTearOffObject<CImpIChapteredRowset>(void)
0x18000a94e  mov     rcx, rbx; void *
0x18000a951  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a956  mov     rax, rbx
0x18000a959  add     rsp, 20h
0x18000a95d  pop     rbx
0x18000a95e  retn
```
