# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CCtTuner>>,ATL::CComCreator<ATL::CComAggObject<CCtTuner>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x140002d80`
- end: `0x140002ebd`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCCtTuner@@@ATL@@@ATL@@V?$CComCreator@V?$CComAggObject@VCCtTuner@@@ATL@@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `317`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140001204`
- `0x140002d80`
- `0x140007010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CCtTuner>>,ATL::CComCreator<ATL::CComAggObject<CCtTuner>>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v6; // ebx
  _DWORD *v7; // rax
  _DWORD *v8; // rdi
  struct ATL::CAtlModule *v9; // rcx
  int v10; // ecx
  _DWORD *v11; // rax
  _DWORD *v12; // rdi
  struct ATL::CAtlModule *v13; // rcx

  if ( !a1 )
  {
    if ( a3 )
    {
      *a3 = 0;
      v6 = -2147024882;
      v7 = operator new(0x10u);
      v8 = v7;
      if ( v7 )
      {
        v9 = ATL::_pAtlModule;
        v7[2] = 0;
        *(_QWORD *)v7 = &ATL::CComObject<CCtTuner>::`vftable';
        (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v9 + 8LL))(v9);
        v10 = v8[2];
        if ( v10 != 0x7FFFFFFF )
        {
          v8[2] = v10 + 1;
          if ( v10 != 2147483646 )
            v8[2] = v10;
        }
        v6 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, _QWORD *))v8)(v8, a2, a3);
        if ( v6 )
          (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v8 + 80LL))(v8, 1);
      }
      return v6;
    }
    return (unsigned int)-2147467261;
  }
  if ( !a3 )
    return (unsigned int)-2147467261;
  *a3 = 0;
  v6 = -2147024882;
  v11 = operator new(0x20u);
  v12 = v11;
  if ( v11 )
  {
    v13 = ATL::_pAtlModule;
    v11[2] = 0;
    *(_QWORD *)v11 = &ATL::CComAggObject<CCtTuner>::`vftable';
    *((_QWORD *)v11 + 2) = &ATL::CComContainedObject<CCtTuner>::`vftable';
    *((_QWORD *)v11 + 3) = a1;
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v13 + 8LL))(v13);
    v6 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, _QWORD *))v12)(v12, a2, a3);
    if ( v6 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v12 + 24LL))(v12, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x140002d80  push    rbx
0x140002d82  push    rbp
0x140002d83  push    rsi
0x140002d84  push    rdi
0x140002d85  push    r14
0x140002d87  sub     rsp, 20h
0x140002d8b  mov     rsi, r8
0x140002d8e  mov     r14, rdx
0x140002d91  mov     rbp, rcx
0x140002d94  test    rcx, rcx
0x140002d97  jnz     loc_140002E25
0x140002d9d  test    r8, r8
0x140002da0  jz      loc_140002E2A
0x140002da6  mov     [r8], rcx
0x140002da9  mov     ebx, 8007000Eh
0x140002dae  lea     ecx, [rbp+10h]; Size
0x140002db1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140002db6  mov     rdi, rax
0x140002db9  test    rax, rax
0x140002dbc  jz      loc_140002EB0
0x140002dc2  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x140002dc9  mov     [rax+8], ebp
0x140002dcc  lea     rax, ??_7?$CComObject@VCCtTuner@@@ATL@@6B@; const ATL::CComObject<CCtTuner>::`vftable'
0x140002dd3  mov     [rdi], rax
0x140002dd6  mov     rdx, [rcx]
0x140002dd9  mov     rax, [rdx+8]
0x140002ddd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002de2  mov     ecx, [rdi+8]
0x140002de5  cmp     ecx, 7FFFFFFFh
0x140002deb  jz      short loc_140002DFE
0x140002ded  lea     eax, [rcx+1]
0x140002df0  mov     [rdi+8], eax
0x140002df3  cmp     ecx, 7FFFFFFEh
0x140002df9  jz      short loc_140002DFE
0x140002dfb  mov     [rdi+8], ecx
0x140002dfe  mov     rax, [rdi]
0x140002e01  mov     r8, rsi
0x140002e04  mov     rdx, r14
0x140002e07  mov     rcx, rdi
0x140002e0a  mov     rax, [rax]
0x140002e0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002e12  mov     ebx, eax
0x140002e14  test    eax, eax
0x140002e16  jz      loc_140002EB0
0x140002e1c  mov     rcx, [rdi]
0x140002e1f  mov     rax, [rcx+50h]
0x140002e23  jmp     short loc_140002EA3
0x140002e25  test    rsi, rsi
0x140002e28  jnz     short loc_140002E31
0x140002e2a  mov     ebx, 80004003h
0x140002e2f  jmp     short loc_140002EB0
0x140002e31  mov     ecx, 20h ; ' '; Size
0x140002e36  mov     qword ptr [r8], 0
0x140002e3d  mov     ebx, 8007000Eh
0x140002e42  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140002e47  mov     rdi, rax
0x140002e4a  test    rax, rax
0x140002e4d  jz      short loc_140002EB0
0x140002e4f  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x140002e56  mov     dword ptr [rax+8], 0
0x140002e5d  lea     rax, ??_7?$CComAggObject@VCCtTuner@@@ATL@@6B@; const ATL::CComAggObject<CCtTuner>::`vftable'
0x140002e64  mov     [rdi], rax
0x140002e67  lea     rax, ??_7?$CComContainedObject@VCCtTuner@@@ATL@@6B@; const ATL::CComContainedObject<CCtTuner>::`vftable'
0x140002e6e  mov     [rdi+10h], rax
0x140002e72  mov     [rdi+18h], rbp
0x140002e76  mov     rdx, [rcx]
0x140002e79  mov     rax, [rdx+8]
0x140002e7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002e82  mov     rax, [rdi]
0x140002e85  mov     r8, rsi
0x140002e88  mov     rdx, r14
0x140002e8b  mov     rcx, rdi
0x140002e8e  mov     rax, [rax]
0x140002e91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002e96  mov     ebx, eax
0x140002e98  test    eax, eax
0x140002e9a  jz      short loc_140002EB0
0x140002e9c  mov     rax, [rdi]
0x140002e9f  mov     rax, [rax+18h]
0x140002ea3  mov     edx, 1
0x140002ea8  mov     rcx, rdi
0x140002eab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002eb0  mov     eax, ebx
0x140002eb2  add     rsp, 20h
0x140002eb6  pop     r14
0x140002eb8  pop     rdi
0x140002eb9  pop     rsi
0x140002eba  pop     rbp
0x140002ebb  pop     rbx
0x140002ebc  retn
```
