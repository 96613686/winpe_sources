# ATL::CComCreator<ATL::CComAggObject<CGameStatisticsMgr>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180002864`
- end: `0x18000290d`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCGameStatisticsMgr@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `169`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180002850`

## callees

- `0x180001268`
- `0x180002558`
- `0x180002864`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CGameStatisticsMgr>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v7; // esi
  _DWORD *v8; // rax
  _DWORD *v9; // rbx

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v7 = -2147024882;
  v8 = operator new(0x20u);
  v9 = v8;
  if ( v8 )
  {
    v8[2] = 0;
    *(_QWORD *)v8 = &ATL::CComAggObject<CGameStatisticsMgr>::`vftable';
    ATL::CComContainedObject<CGameStatisticsMgr>::CComContainedObject<CGameStatisticsMgr>(v8 + 4, a1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    v7 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, _QWORD *))v9)(v9, a2, a3);
    if ( v7 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v9 + 24LL))(v9, 1);
  }
  return v7;
}

```

## disassembly

```asm
0x180002864  push    rbx
0x180002866  push    rbp
0x180002867  push    rsi
0x180002868  push    rdi
0x180002869  push    r14
0x18000286b  sub     rsp, 20h
0x18000286f  mov     rdi, r8
0x180002872  mov     rbp, rdx
0x180002875  mov     r14, rcx
0x180002878  test    r8, r8
0x18000287b  jnz     short loc_180002884
0x18000287d  mov     eax, 80004003h
0x180002882  jmp     short loc_180002902
0x180002884  mov     ecx, 20h ; ' '; Size
0x180002889  mov     qword ptr [r8], 0
0x180002890  mov     esi, 8007000Eh
0x180002895  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000289a  mov     rbx, rax
0x18000289d  test    rax, rax
0x1800028a0  jz      short loc_180002900
0x1800028a2  mov     dword ptr [rax+8], 0
0x1800028a9  lea     rcx, [rbx+10h]
0x1800028ad  lea     rax, ??_7?$CComAggObject@VCGameStatisticsMgr@@@ATL@@6B@; const ATL::CComAggObject<CGameStatisticsMgr>::`vftable'
0x1800028b4  mov     rdx, r14
0x1800028b7  mov     [rbx], rax
0x1800028ba  call    ??0?$CComContainedObject@VCGameStatisticsMgr@@@ATL@@QEAA@PEAX@Z; ATL::CComContainedObject<CGameStatisticsMgr>::CComContainedObject<CGameStatisticsMgr>(void *)
0x1800028bf  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800028c6  mov     rax, [rcx]
0x1800028c9  mov     rax, [rax+8]
0x1800028cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028d2  mov     rax, [rbx]
0x1800028d5  mov     r8, rdi
0x1800028d8  mov     rdx, rbp
0x1800028db  mov     rcx, rbx
0x1800028de  mov     rax, [rax]
0x1800028e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028e6  mov     esi, eax
0x1800028e8  test    eax, eax
0x1800028ea  jz      short loc_180002900
0x1800028ec  mov     rcx, [rbx]
0x1800028ef  mov     edx, 1
0x1800028f4  mov     rax, [rcx+18h]
0x1800028f8  mov     rcx, rbx
0x1800028fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002900  mov     eax, esi
0x180002902  add     rsp, 20h
0x180002906  pop     r14
0x180002908  pop     rdi
0x180002909  pop     rsi
0x18000290a  pop     rbp
0x18000290b  pop     rbx
0x18000290c  retn
```
