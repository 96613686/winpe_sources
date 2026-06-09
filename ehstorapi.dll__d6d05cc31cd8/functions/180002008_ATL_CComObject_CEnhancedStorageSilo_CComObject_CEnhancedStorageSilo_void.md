# ATL::CComObject<CEnhancedStorageSilo>::CComObject<CEnhancedStorageSilo>(void *)

- ea: `0x180002008`
- end: `0x18000205b`
- name: `??0?$CComObject@VCEnhancedStorageSilo@@@ATL@@QEAA@PEAX@Z`
- size: `83`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002504`
- `0x180009d90`

## callees

- `0x180002064`
- `0x18000d010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CEnhancedStorageSilo>::CComObject<CEnhancedStorageSilo>(__int64 a1)
{
  struct ATL::CAtlModule *v2; // rcx

  *(_DWORD *)(a1 + 8) = 0;
  *(_OWORD *)(a1 + 16) = 0;
  *(_OWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 48) = 0;
  *(_BYTE *)(a1 + 56) = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(a1 + 64);
  v2 = ATL::_pAtlModule;
  *(_QWORD *)a1 = &ATL::CComObject<CEnhancedStorageSilo>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v2 + 8LL))(v2);
  return a1;
}

```

## disassembly

```asm
0x180002008  push    rbx
0x18000200a  sub     rsp, 20h
0x18000200e  mov     dword ptr [rcx+8], 0
0x180002015  xorps   xmm0, xmm0
0x180002018  movups  xmmword ptr [rcx+10h], xmm0
0x18000201c  xor     eax, eax
0x18000201e  mov     rbx, rcx
0x180002021  movups  xmmword ptr [rcx+20h], xmm0
0x180002025  mov     [rcx+30h], rax
0x180002029  mov     [rcx+38h], al
0x18000202c  add     rcx, 40h ; '@'
0x180002030  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180002035  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000203c  lea     rax, ??_7?$CComObject@VCEnhancedStorageSilo@@@ATL@@6B@; const ATL::CComObject<CEnhancedStorageSilo>::`vftable'
0x180002043  mov     [rbx], rax
0x180002046  mov     rax, [rcx]
0x180002049  mov     rax, [rax+8]
0x18000204d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002052  mov     rax, rbx
0x180002055  add     rsp, 20h
0x180002059  pop     rbx
0x18000205a  retn
```
