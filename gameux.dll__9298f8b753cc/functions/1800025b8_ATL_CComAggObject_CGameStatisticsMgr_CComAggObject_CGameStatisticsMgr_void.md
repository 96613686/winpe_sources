# ATL::CComAggObject<CGameStatisticsMgr>::~CComAggObject<CGameStatisticsMgr>(void)

- ea: `0x1800025b8`
- end: `0x1800025f6`
- name: `??1?$CComAggObject@VCGameStatisticsMgr@@@ATL@@UEAA@XZ`
- size: `62`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002690`

## callees

- `0x180004010`

## pseudocode

```c
void **__fastcall ATL::CComAggObject<CGameStatisticsMgr>::~CComAggObject<CGameStatisticsMgr>(__int64 a1)
{
  void **result; // rax

  *(_DWORD *)(a1 + 8) = -1073741823;
  *(_QWORD *)a1 = &ATL::CComAggObject<CGameStatisticsMgr>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  result = &CGameStatisticsMgr::`vftable';
  *(_QWORD *)(a1 + 16) = &CGameStatisticsMgr::`vftable';
  return result;
}

```

## disassembly

```asm
0x1800025b8  push    rbx
0x1800025ba  sub     rsp, 20h
0x1800025be  mov     dword ptr [rcx+8], 0C0000001h
0x1800025c5  lea     rax, ??_7?$CComAggObject@VCGameStatisticsMgr@@@ATL@@6B@; const ATL::CComAggObject<CGameStatisticsMgr>::`vftable'
0x1800025cc  mov     [rcx], rax
0x1800025cf  mov     rbx, rcx
0x1800025d2  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800025d9  mov     rax, [rcx]
0x1800025dc  mov     rax, [rax+10h]
0x1800025e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025e5  lea     rax, ??_7CGameStatisticsMgr@@6B@; const CGameStatisticsMgr::`vftable'
0x1800025ec  mov     [rbx+10h], rax
0x1800025f0  add     rsp, 20h
0x1800025f4  pop     rbx
0x1800025f5  retn
```
