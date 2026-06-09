# ATL::CComCreator<ATL::CComAggObject<CRehydrationTaskHandler>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180003214`
- end: `0x180003351`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCRehydrationTaskHandler@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `317`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800031e0`

## callees

- `0x1800011d8`
- `0x180003214`
- `0x1800039cc`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CRehydrationTaskHandler>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // r14
  __int64 v4; // r15
  unsigned int v7; // esi
  char *v8; // rax
  _BYTE *v9; // rdi
  int v10; // ecx
  int v11; // eax
  int v12; // ecx
  _BYTE *v13; // [rsp+20h] [rbp-38h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v7 = -2147024882;
    v8 = (char *)operator new(0x78u);
    v9 = v8;
    if ( v8 )
    {
      *((_DWORD *)v8 + 2) = 0;
      *(_QWORD *)v8 = &ATL::CComAggObject<CRehydrationTaskHandler>::`vftable';
      *(_OWORD *)(v8 + 40) = 0;
      *(_OWORD *)(v8 + 56) = 0;
      *((_QWORD *)v8 + 9) = 0;
      v8[80] = 0;
      *((_QWORD *)v8 + 11) = 0;
      *((_QWORD *)v8 + 12) = 0;
      *((_QWORD *)v8 + 13) = 0;
      v8[112] = 0;
      *((_QWORD *)v8 + 3) = &ATL::CComContainedObject<CRehydrationTaskHandler>::`vftable';
      *((_QWORD *)v8 + 4) = a1;
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    v13 = v9;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v7 = -2147024882;
    v9 = v13;
  }
  if ( v9 )
  {
    v10 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v9 + 40));
    if ( v10 >= 0 )
      v9[80] = 1;
    v11 = 0;
    if ( v10 < 0 )
      v11 = v10;
    v12 = 0;
    if ( v11 < 0 )
      v12 = v11;
    v7 = 0;
    if ( v12 < 0 )
      v7 = v12;
    if ( v7 || (v7 = (**(__int64 (__fastcall ***)(_BYTE *, __int64, _QWORD *))v9)(v9, v4, v3)) != 0 )
      (*(void (__fastcall **)(_BYTE *, __int64))(*(_QWORD *)v9 + 24LL))(v9, 1);
  }
  return v7;
}

```

## disassembly

```asm
0x180003214  mov     [rsp+arg_10], r8
0x180003219  mov     [rsp+arg_8], rdx
0x18000321e  push    rsi
0x18000321f  push    rdi
0x180003220  push    r12
0x180003222  push    r14
0x180003224  push    r15
0x180003226  sub     rsp, 30h
0x18000322a  mov     r14, r8
0x18000322d  mov     r15, rdx
0x180003230  mov     r12, rcx
0x180003233  test    r8, r8
0x180003236  jnz     short loc_180003242
0x180003238  mov     eax, 80004003h
0x18000323d  jmp     loc_180003344
0x180003242  mov     qword ptr [r8], 0
0x180003249  mov     esi, 8007000Eh
0x18000324e  mov     [rsp+58h+arg_18], esi
0x180003252  mov     [rsp+58h+var_38], 0
0x18000325b  mov     ecx, 78h ; 'x'; Size
0x180003260  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003265  mov     rdi, rax
0x180003268  mov     [rsp+58h+var_38], rax
0x18000326d  test    rdi, rdi
0x180003270  jz      short loc_1800032C9
0x180003272  mov     dword ptr [rax+8], 0
0x180003279  lea     rax, ??_7?$CComAggObject@VCRehydrationTaskHandler@@@ATL@@6B@; const ATL::CComAggObject<CRehydrationTaskHandler>::`vftable'
0x180003280  mov     [rdi], rax
0x180003283  xorps   xmm0, xmm0
0x180003286  xor     eax, eax
0x180003288  movups  xmmword ptr [rdi+28h], xmm0
0x18000328c  movups  xmmword ptr [rdi+38h], xmm0
0x180003290  mov     [rdi+48h], rax
0x180003294  mov     [rdi+50h], al
0x180003297  mov     [rdi+58h], rax
0x18000329b  mov     [rdi+60h], rax
0x18000329f  mov     [rdi+68h], rax
0x1800032a3  mov     [rdi+70h], al
0x1800032a6  lea     rax, ??_7?$CComContainedObject@VCRehydrationTaskHandler@@@ATL@@6B@; const ATL::CComContainedObject<CRehydrationTaskHandler>::`vftable'
0x1800032ad  mov     [rdi+18h], rax
0x1800032b1  mov     [rdi+20h], r12
0x1800032b5  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800032bc  mov     rax, [rcx]
0x1800032bf  mov     rax, [rax+8]
0x1800032c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032c8  nop
0x1800032c9  mov     [rsp+58h+var_38], rdi
0x1800032ce  jmp     short loc_1800032E3
0x1800032d0  mov     r14, [rsp+58h+arg_10]
0x1800032d5  mov     r15, [rsp+58h+arg_8]
0x1800032da  mov     esi, [rsp+58h+arg_18]
0x1800032de  mov     rdi, [rsp+58h+var_38]
0x1800032e3  test    rdi, rdi
0x1800032e6  jz      short loc_180003342
0x1800032e8  lea     rcx, [rdi+28h]; this
0x1800032ec  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1800032f1  mov     ecx, eax
0x1800032f3  test    eax, eax
0x1800032f5  js      short loc_1800032FB
0x1800032f7  mov     byte ptr [rdi+50h], 1
0x1800032fb  xor     eax, eax
0x1800032fd  test    ecx, ecx
0x1800032ff  cmovs   eax, ecx
0x180003302  xor     ecx, ecx
0x180003304  test    eax, eax
0x180003306  cmovs   ecx, eax
0x180003309  xor     esi, esi
0x18000330b  test    ecx, ecx
0x18000330d  cmovs   esi, ecx
0x180003310  test    esi, esi
0x180003312  jnz     short loc_18000332E
0x180003314  mov     rax, [rdi]
0x180003317  mov     r8, r14
0x18000331a  mov     rdx, r15
0x18000331d  mov     rcx, rdi
0x180003320  mov     rax, [rax]
0x180003323  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003328  mov     esi, eax
0x18000332a  test    eax, eax
0x18000332c  jz      short loc_180003342
0x18000332e  mov     r8, [rdi]
0x180003331  mov     edx, 1
0x180003336  mov     rcx, rdi
0x180003339  mov     rax, [r8+18h]
0x18000333d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003342  mov     eax, esi
0x180003344  add     rsp, 30h
0x180003348  pop     r15
0x18000334a  pop     r14
0x18000334c  pop     r12
0x18000334e  pop     rdi
0x18000334f  pop     rsi
0x180003350  retn
```
