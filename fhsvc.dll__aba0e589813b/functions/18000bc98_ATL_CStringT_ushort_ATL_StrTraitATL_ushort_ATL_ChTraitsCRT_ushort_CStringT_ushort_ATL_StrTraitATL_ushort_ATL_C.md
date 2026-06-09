# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)

- ea: `0x18000bc98`
- end: `0x18000bcbd`
- name: `??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z`
- size: `37`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *)`
- caller_count: `17`
- callee_count: `1`
- tags: ``

## callers

- `0x180003f00`
- `0x1800062b0`
- `0x1800065c0`
- `0x180007330`
- `0x1800079e0`
- `0x180009fd0`
- `0x18000a148`
- `0x18000a254`
- `0x18000ac48`
- `0x18000dd60`
- `0x18000df70`
- `0x18000e2f0`
- `0x18000e5d0`
- `0x18000e740`
- `0x18000e8b0`
- `0x18000efb4`
- `0x18000feb4`

## callees

- `0x180006d38`

## pseudocode

```c
_QWORD *__fastcall ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        _QWORD *a1,
        _QWORD *a2)
{
  *a1 = ATL::CSimpleStringT<unsigned short,0>::CloneData(*a2 - 24LL) + 24;
  return a1;
}

```

## disassembly

```asm
0x18000bc98  push    rbx
0x18000bc9a  sub     rsp, 20h
0x18000bc9e  mov     rbx, rcx
0x18000bca1  mov     rcx, [rdx]
0x18000bca4  sub     rcx, 18h
0x18000bca8  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18000bcad  add     rax, 18h
0x18000bcb1  mov     [rbx], rax
0x18000bcb4  mov     rax, rbx
0x18000bcb7  add     rsp, 20h
0x18000bcbb  pop     rbx
0x18000bcbc  retn
```
