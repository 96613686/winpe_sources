# ATL::CComObject<CGameStatistics>::~CComObject<CGameStatistics>(void)

- ea: `0x1800025fc`
- end: `0x180002639`
- name: `??1?$CComObject@VCGameStatistics@@@ATL@@UEAA@XZ`
- size: `61`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800026d0`

## callees

- `0x180004010`

## pseudocode

```c
void **__fastcall ATL::CComObject<CGameStatistics>::~CComObject<CGameStatistics>(__int64 a1)
{
  void **result; // rax

  *(_DWORD *)(a1 + 8) = -1073741823;
  *(_QWORD *)a1 = &ATL::CComObject<CGameStatistics>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  result = &CGameStatistics::`vftable';
  *(_QWORD *)a1 = &CGameStatistics::`vftable';
  return result;
}

```

## disassembly

```asm
0x1800025fc  push    rbx
0x1800025fe  sub     rsp, 20h
0x180002602  mov     dword ptr [rcx+8], 0C0000001h
0x180002609  lea     rax, ??_7?$CComObject@VCGameStatistics@@@ATL@@6B@; const ATL::CComObject<CGameStatistics>::`vftable'
0x180002610  mov     [rcx], rax
0x180002613  mov     rbx, rcx
0x180002616  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000261d  mov     rax, [rcx]
0x180002620  mov     rax, [rax+10h]
0x180002624  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002629  lea     rax, ??_7CGameStatistics@@6B@; const CGameStatistics::`vftable'
0x180002630  mov     [rbx], rax
0x180002633  add     rsp, 20h
0x180002637  pop     rbx
0x180002638  retn
```
