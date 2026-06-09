# ATL::CComCreator<ATL::CComObject<CGameStatisticsMgr>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180002914`
- end: `0x1800029ab`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCGameStatisticsMgr@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `151`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180002850`

## callees

- `0x180001268`
- `0x18000259c`
- `0x180002914`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CGameStatisticsMgr>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v6; // esi
  CGameStatisticsMgr *v7; // rax
  CGameStatisticsMgr *v8; // rbx

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -2147024882;
  v7 = (CGameStatisticsMgr *)operator new(0x10u);
  v8 = v7;
  if ( v7 )
  {
    CGameStatisticsMgr::CGameStatisticsMgr(v7);
    *(_QWORD *)v8 = &ATL::CComObject<CGameStatisticsMgr>::`vftable';
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    v6 = (**(__int64 (__fastcall ***)(CGameStatisticsMgr *, __int64, _QWORD *))v8)(v8, a2, a3);
    if ( v6 )
      (*(void (__fastcall **)(CGameStatisticsMgr *, __int64))(*(_QWORD *)v8 + 40LL))(v8, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x180002914  push    rbx
0x180002916  push    rbp
0x180002917  push    rsi
0x180002918  push    rdi
0x180002919  sub     rsp, 28h
0x18000291d  mov     rdi, r8
0x180002920  mov     rbp, rdx
0x180002923  test    r8, r8
0x180002926  jnz     short loc_18000292F
0x180002928  mov     eax, 80004003h
0x18000292d  jmp     short loc_1800029A2
0x18000292f  mov     ecx, 10h; Size
0x180002934  mov     qword ptr [r8], 0
0x18000293b  mov     esi, 8007000Eh
0x180002940  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002945  mov     rbx, rax
0x180002948  test    rax, rax
0x18000294b  jz      short loc_1800029A0
0x18000294d  mov     rcx, rax; this
0x180002950  call    ??0CGameStatisticsMgr@@QEAA@XZ; CGameStatisticsMgr::CGameStatisticsMgr(void)
0x180002955  lea     rcx, ??_7?$CComObject@VCGameStatisticsMgr@@@ATL@@6B@; const ATL::CComObject<CGameStatisticsMgr>::`vftable'
0x18000295c  mov     [rbx], rcx
0x18000295f  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180002966  mov     rax, [rcx]
0x180002969  mov     rax, [rax+8]
0x18000296d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002972  mov     rax, [rbx]
0x180002975  mov     r8, rdi
0x180002978  mov     rdx, rbp
0x18000297b  mov     rcx, rbx
0x18000297e  mov     rax, [rax]
0x180002981  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002986  mov     esi, eax
0x180002988  test    eax, eax
0x18000298a  jz      short loc_1800029A0
0x18000298c  mov     rcx, [rbx]
0x18000298f  mov     edx, 1
0x180002994  mov     rax, [rcx+28h]
0x180002998  mov     rcx, rbx
0x18000299b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029a0  mov     eax, esi
0x1800029a2  add     rsp, 28h
0x1800029a6  pop     rdi
0x1800029a7  pop     rsi
0x1800029a8  pop     rbp
0x1800029a9  pop     rbx
0x1800029aa  retn
```
