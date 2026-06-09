# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)

- ea: `0x180002064`
- end: `0x180002094`
- name: `??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ`
- size: `48`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180002008`
- `0x180003d3c`
- `0x180003e28`
- `0x18000408c`
- `0x180005960`
- `0x180006308`
- `0x18000664c`
- `0x1800079d0`

## callees

- `0x18000d010`

## pseudocode

```c
_QWORD *__fastcall ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        _QWORD *a1)
{
  *a1 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  return a1;
}

```

## disassembly

```asm
0x180002064  push    rbx
0x180002066  sub     rsp, 20h
0x18000206a  mov     rbx, rcx
0x18000206d  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180002074  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000207b  mov     rax, [rax+18h]
0x18000207f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002084  add     rax, 18h
0x180002088  mov     [rbx], rax
0x18000208b  mov     rax, rbx
0x18000208e  add     rsp, 20h
0x180002092  pop     rbx
0x180002093  retn
```
