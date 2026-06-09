# ATL::CComObject<CEnhancedStorageSiloAction>::CComObject<CEnhancedStorageSiloAction>(void *)

- ea: `0x180006308`
- end: `0x180006376`
- name: `??0?$CComObject@VCEnhancedStorageSiloAction@@@ATL@@QEAA@PEAX@Z`
- size: `110`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180006988`
- `0x180009e88`

## callees

- `0x180002064`
- `0x18000d010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CEnhancedStorageSiloAction>::CComObject<CEnhancedStorageSiloAction>(__int64 a1)
{
  struct ATL::CAtlModule *v2; // rcx

  *(_DWORD *)(a1 + 8) = 0;
  *(_OWORD *)(a1 + 16) = 0;
  *(_OWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 48) = 0;
  *(_BYTE *)(a1 + 56) = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(a1 + 64);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(a1 + 72);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(a1 + 80);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(a1 + 88);
  v2 = ATL::_pAtlModule;
  *(_QWORD *)a1 = &ATL::CComObject<CEnhancedStorageSiloAction>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v2 + 8LL))(v2);
  return a1;
}

```

## disassembly

```asm
0x180006308  push    rbx
0x18000630a  sub     rsp, 20h
0x18000630e  mov     dword ptr [rcx+8], 0
0x180006315  xorps   xmm0, xmm0
0x180006318  movups  xmmword ptr [rcx+10h], xmm0
0x18000631c  xor     eax, eax
0x18000631e  mov     rbx, rcx
0x180006321  movups  xmmword ptr [rcx+20h], xmm0
0x180006325  mov     [rcx+30h], rax
0x180006329  mov     [rcx+38h], al
0x18000632c  add     rcx, 40h ; '@'
0x180006330  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180006335  lea     rcx, [rbx+48h]
0x180006339  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18000633e  lea     rcx, [rbx+50h]
0x180006342  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180006347  lea     rcx, [rbx+58h]
0x18000634b  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180006350  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180006357  lea     rax, ??_7?$CComObject@VCEnhancedStorageSiloAction@@@ATL@@6B@; const ATL::CComObject<CEnhancedStorageSiloAction>::`vftable'
0x18000635e  mov     [rbx], rax
0x180006361  mov     rax, [rcx]
0x180006364  mov     rax, [rax+8]
0x180006368  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000636d  mov     rax, rbx
0x180006370  add     rsp, 20h
0x180006374  pop     rbx
0x180006375  retn
```
