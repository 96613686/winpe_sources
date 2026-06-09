# ATL::CComObject<CEnhancedStorageAct>::CComObject<CEnhancedStorageAct>(void *)

- ea: `0x180003d3c`
- end: `0x180003dae`
- name: `??0?$CComObject@VCEnhancedStorageAct@@@ATL@@QEAA@PEAX@Z`
- size: `114`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180004220`
- `0x180009b78`

## callees

- `0x180002064`
- `0x18000d010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CEnhancedStorageAct>::CComObject<CEnhancedStorageAct>(__int64 a1)
{
  struct ATL::CAtlModule *v2; // rcx

  *(_DWORD *)(a1 + 8) = 0;
  *(_OWORD *)(a1 + 16) = 0;
  *(_OWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 48) = 0;
  *(_BYTE *)(a1 + 56) = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(a1 + 64);
  v2 = ATL::_pAtlModule;
  *(_QWORD *)(a1 + 72) = 0;
  *(_QWORD *)(a1 + 80) = 0;
  *(_QWORD *)(a1 + 88) = 0;
  *(_DWORD *)(a1 + 96) = 0;
  *(_QWORD *)a1 = &ATL::CComObject<CEnhancedStorageAct>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v2 + 8LL))(v2);
  return a1;
}

```

## disassembly

```asm
0x180003d3c  push    rbx
0x180003d3e  sub     rsp, 20h
0x180003d42  mov     dword ptr [rcx+8], 0
0x180003d49  xorps   xmm0, xmm0
0x180003d4c  movups  xmmword ptr [rcx+10h], xmm0
0x180003d50  xor     eax, eax
0x180003d52  mov     rbx, rcx
0x180003d55  movups  xmmword ptr [rcx+20h], xmm0
0x180003d59  mov     [rcx+30h], rax
0x180003d5d  mov     [rcx+38h], al
0x180003d60  add     rcx, 40h ; '@'
0x180003d64  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180003d69  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180003d70  lea     rax, ??_7?$CComObject@VCEnhancedStorageAct@@@ATL@@6B@; const ATL::CComObject<CEnhancedStorageAct>::`vftable'
0x180003d77  mov     qword ptr [rbx+48h], 0
0x180003d7f  mov     qword ptr [rbx+50h], 0
0x180003d87  mov     qword ptr [rbx+58h], 0
0x180003d8f  mov     dword ptr [rbx+60h], 0
0x180003d96  mov     [rbx], rax
0x180003d99  mov     rax, [rcx]
0x180003d9c  mov     rax, [rax+8]
0x180003da0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003da5  mov     rax, rbx
0x180003da8  add     rsp, 20h
0x180003dac  pop     rbx
0x180003dad  retn
```
