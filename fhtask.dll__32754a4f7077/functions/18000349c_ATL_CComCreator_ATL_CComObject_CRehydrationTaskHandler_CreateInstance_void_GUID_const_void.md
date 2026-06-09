# ATL::CComCreator<ATL::CComObject<CRehydrationTaskHandler>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000349c`
- end: `0x1800035f7`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCRehydrationTaskHandler@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `347`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800031e0`

## callees

- `0x1800011d8`
- `0x18000349c`
- `0x1800039cc`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CRehydrationTaskHandler>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // r14
  __int64 v4; // r15
  unsigned int v6; // esi
  _DWORD *v7; // rax
  _DWORD *v8; // rbx
  signed __int32 v9; // eax
  int v10; // ecx
  int v11; // eax
  signed __int32 v12; // eax
  _DWORD *v15; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v6 = -2147024882;
    v7 = operator new(0x60u);
    v8 = v7;
    if ( v7 )
    {
      v7[2] = 0;
      *((_OWORD *)v7 + 1) = 0;
      *((_OWORD *)v7 + 2) = 0;
      *((_QWORD *)v7 + 6) = 0;
      *((_BYTE *)v7 + 56) = 0;
      *((_QWORD *)v7 + 8) = 0;
      *((_QWORD *)v7 + 9) = 0;
      *((_QWORD *)v7 + 10) = 0;
      *((_BYTE *)v7 + 88) = 0;
      *(_QWORD *)v7 = &ATL::CComObject<CRehydrationTaskHandler>::`vftable';
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    v15 = v8;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v6 = -2147024882;
    v8 = v15;
  }
  if ( v8 )
  {
    do
      v9 = v8[2];
    while ( v9 != 0x7FFFFFFF && v9 != _InterlockedCompareExchange(v8 + 2, v9 + 1, v9) );
    v10 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v8 + 4));
    if ( v10 >= 0 )
      *((_BYTE *)v8 + 56) = 1;
    v11 = 0;
    if ( v10 < 0 )
      v11 = v10;
    v6 = 0;
    if ( v11 < 0 )
      v6 = v11;
    do
      v12 = v8[2];
    while ( v12 != 0x7FFFFFFF && v12 != _InterlockedCompareExchange(v8 + 2, v12 - 1, v12) );
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, _QWORD *))v8)(v8, v4, v3)) != 0 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v8 + 56LL))(v8, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x18000349c  mov     [rsp+arg_10], r8
0x1800034a1  mov     [rsp+arg_8], rdx
0x1800034a6  mov     [rsp+arg_0], rcx
0x1800034ab  push    rbx
0x1800034ac  push    rsi
0x1800034ad  push    r12
0x1800034af  push    r14
0x1800034b1  push    r15
0x1800034b3  sub     rsp, 20h
0x1800034b7  mov     r14, r8
0x1800034ba  mov     r15, rdx
0x1800034bd  test    r8, r8
0x1800034c0  jnz     short loc_1800034CC
0x1800034c2  mov     eax, 80004003h
0x1800034c7  jmp     loc_1800035EA
0x1800034cc  mov     qword ptr [r8], 0
0x1800034d3  mov     esi, 8007000Eh
0x1800034d8  mov     dword ptr [rsp+48h+arg_0], esi
0x1800034dc  mov     [rsp+48h+arg_18], 0
0x1800034e5  mov     ecx, 60h ; '`'; Size
0x1800034ea  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800034ef  mov     rbx, rax
0x1800034f2  mov     [rsp+48h+arg_18], rax
0x1800034f7  test    rbx, rbx
0x1800034fa  jz      short loc_180003544
0x1800034fc  mov     dword ptr [rax+8], 0
0x180003503  xorps   xmm0, xmm0
0x180003506  xor     eax, eax
0x180003508  movups  xmmword ptr [rbx+10h], xmm0
0x18000350c  movups  xmmword ptr [rbx+20h], xmm0
0x180003510  mov     [rbx+30h], rax
0x180003514  mov     [rbx+38h], al
0x180003517  mov     [rbx+40h], rax
0x18000351b  mov     [rbx+48h], rax
0x18000351f  mov     [rbx+50h], rax
0x180003523  mov     [rbx+58h], al
0x180003526  lea     rax, ??_7?$CComObject@VCRehydrationTaskHandler@@@ATL@@6B@; const ATL::CComObject<CRehydrationTaskHandler>::`vftable'
0x18000352d  mov     [rbx], rax
0x180003530  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180003537  mov     rax, [rcx]
0x18000353a  mov     rax, [rax+8]
0x18000353e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003543  nop
0x180003544  mov     [rsp+48h+arg_18], rbx
0x180003549  jmp     short loc_18000355E
0x18000354b  mov     r14, [rsp+48h+arg_10]
0x180003550  mov     r15, [rsp+48h+arg_8]
0x180003555  mov     esi, dword ptr [rsp+48h+arg_0]
0x180003559  mov     rbx, [rsp+48h+arg_18]
0x18000355e  test    rbx, rbx
0x180003561  jz      loc_1800035E8
0x180003567  mov     r12d, 7FFFFFFFh
0x18000356d  jmp     short loc_180003579
0x18000356f  lea     ecx, [rax+1]
0x180003572  lock cmpxchg [rbx+8], ecx
0x180003577  jz      short loc_180003581
0x180003579  mov     eax, [rbx+8]
0x18000357c  cmp     eax, r12d
0x18000357f  jnz     short loc_18000356F
0x180003581  lea     rcx, [rbx+10h]; this
0x180003585  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18000358a  mov     ecx, eax
0x18000358c  test    eax, eax
0x18000358e  js      short loc_180003594
0x180003590  mov     byte ptr [rbx+38h], 1
0x180003594  xor     eax, eax
0x180003596  test    ecx, ecx
0x180003598  cmovs   eax, ecx
0x18000359b  xor     esi, esi
0x18000359d  test    eax, eax
0x18000359f  cmovs   esi, eax
0x1800035a2  jmp     short loc_1800035AE
0x1800035a4  lea     ecx, [rax-1]
0x1800035a7  lock cmpxchg [rbx+8], ecx
0x1800035ac  jz      short loc_1800035B6
0x1800035ae  mov     eax, [rbx+8]
0x1800035b1  cmp     eax, r12d
0x1800035b4  jnz     short loc_1800035A4
0x1800035b6  test    esi, esi
0x1800035b8  jnz     short loc_1800035D4
0x1800035ba  mov     rax, [rbx]
0x1800035bd  mov     r8, r14
0x1800035c0  mov     rdx, r15
0x1800035c3  mov     rcx, rbx
0x1800035c6  mov     rax, [rax]
0x1800035c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035ce  mov     esi, eax
0x1800035d0  test    eax, eax
0x1800035d2  jz      short loc_1800035E8
0x1800035d4  mov     r8, [rbx]
0x1800035d7  mov     edx, 1
0x1800035dc  mov     rcx, rbx
0x1800035df  mov     rax, [r8+38h]
0x1800035e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035e8  mov     eax, esi
0x1800035ea  add     rsp, 20h
0x1800035ee  pop     r15
0x1800035f0  pop     r14
0x1800035f2  pop     r12
0x1800035f4  pop     rsi
0x1800035f5  pop     rbx
0x1800035f6  retn
```
