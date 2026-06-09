# ATL::CComCachedTearOffObject<CImpIColumnsUpdateInfo>::`scalar deleting destructor'(uint)

- ea: `0x18000a9b8`
- end: `0x18000a9d8`
- name: `??_G?$CComCachedTearOffObject@VCImpIColumnsUpdateInfo@@@ATL@@QEAAPEAXI@Z`
- size: `32`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18000b260`
- `0x18000c7a0`

## callees

- `0x180001db8`
- `0x18000a598`

## pseudocode

```c
unsigned __int8 *__fastcall ATL::CComCachedTearOffObject<CImpIColumnsUpdateInfo>::`scalar deleting destructor'(
        unsigned __int8 *a1)
{
  ATL::CComCachedTearOffObject<CImpIColumnsUpdateInfo>::~CComCachedTearOffObject<CImpIColumnsUpdateInfo>((__int64)a1);
  operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x18000a9b8  push    rbx
0x18000a9ba  sub     rsp, 20h
0x18000a9be  mov     rbx, rcx
0x18000a9c1  call    ??1?$CComCachedTearOffObject@VCImpIColumnsUpdateInfo@@@ATL@@QEAA@XZ; ATL::CComCachedTearOffObject<CImpIColumnsUpdateInfo>::~CComCachedTearOffObject<CImpIColumnsUpdateInfo>(void)
0x18000a9c6  mov     rcx, rbx; void *
0x18000a9c9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a9ce  mov     rax, rbx
0x18000a9d1  add     rsp, 20h
0x18000a9d5  pop     rbx
0x18000a9d6  retn
```
