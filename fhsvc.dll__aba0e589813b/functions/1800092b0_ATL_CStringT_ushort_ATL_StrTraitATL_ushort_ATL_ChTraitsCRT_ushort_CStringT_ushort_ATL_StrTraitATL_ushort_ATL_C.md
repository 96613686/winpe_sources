# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)

- ea: `0x1800092b0`
- end: `0x1800092e0`
- name: `??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ`
- size: `48`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x1800096c0`
- `0x18000a360`
- `0x18000bcc4`
- `0x18000dd60`
- `0x18000df70`
- `0x18000e2f0`
- `0x18000e5d0`
- `0x18000e740`
- `0x18000e8b0`
- `0x18000ed14`

## callees

- `0x180013010`

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
0x1800092b0  push    rbx
0x1800092b2  sub     rsp, 20h
0x1800092b6  mov     rbx, rcx
0x1800092b9  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800092c0  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800092c7  mov     rax, [rax+18h]
0x1800092cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800092d0  add     rax, 18h
0x1800092d4  mov     [rbx], rax
0x1800092d7  mov     rax, rbx
0x1800092da  add     rsp, 20h
0x1800092de  pop     rbx
0x1800092df  retn
```
