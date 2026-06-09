# ATL::CComObject<CGameStatisticsMgr>::~CComObject<CGameStatisticsMgr>(void)

- ea: `0x180002640`
- end: `0x18000267d`
- name: `??1?$CComObject@VCGameStatisticsMgr@@@ATL@@UEAA@XZ`
- size: `61`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002710`

## callees

- `0x180004010`

## pseudocode

```c
void **__fastcall ATL::CComObject<CGameStatisticsMgr>::~CComObject<CGameStatisticsMgr>(__int64 a1)
{
  void **result; // rax

  *(_DWORD *)(a1 + 8) = -1073741823;
  *(_QWORD *)a1 = &ATL::CComObject<CGameStatisticsMgr>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  result = &CGameStatisticsMgr::`vftable';
  *(_QWORD *)a1 = &CGameStatisticsMgr::`vftable';
  return result;
}

```

## disassembly

```asm
0x180002640  push    rbx
0x180002642  sub     rsp, 20h
0x180002646  mov     dword ptr [rcx+8], 0C0000001h
0x18000264d  lea     rax, ??_7?$CComObject@VCGameStatisticsMgr@@@ATL@@6B@; const ATL::CComObject<CGameStatisticsMgr>::`vftable'
0x180002654  mov     [rcx], rax
0x180002657  mov     rbx, rcx
0x18000265a  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180002661  mov     rax, [rcx]
0x180002664  mov     rax, [rax+10h]
0x180002668  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000266d  lea     rax, ??_7CGameStatisticsMgr@@6B@; const CGameStatisticsMgr::`vftable'
0x180002674  mov     [rbx], rax
0x180002677  add     rsp, 20h
0x18000267b  pop     rbx
0x18000267c  retn
```
