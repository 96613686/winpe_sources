# ATL::CComCreator<ATL::CComAggObject<CTaskHandler>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180003358`
- end: `0x180003496`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCTaskHandler@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `318`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180003200`

## callees

- `0x1800011d8`
- `0x180003358`
- `0x1800039cc`
- `0x18000612c`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CTaskHandler>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // r14
  __int64 v4; // r15
  unsigned int v7; // esi
  char *v8; // rax
  char *v9; // rdi
  int v10; // ecx
  int v11; // eax
  char *v12; // [rsp+20h] [rbp-38h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v7 = -2147024882;
    v8 = (char *)operator new(0xA8u);
    v9 = v8;
    if ( v8 )
    {
      *((_DWORD *)v8 + 2) = 0;
      *(_QWORD *)v8 = &ATL::CComAggObject<CTaskHandler>::`vftable';
      *(_OWORD *)(v8 + 40) = 0;
      *(_OWORD *)(v8 + 56) = 0;
      *((_QWORD *)v8 + 9) = 0;
      v8[80] = 0;
      *((_QWORD *)v8 + 11) = 0;
      *((_QWORD *)v8 + 3) = &ATL::CComContainedObject<CTaskHandler>::`vftable';
      *((_QWORD *)v8 + 4) = a1;
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    v12 = v9;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v7 = -2147024882;
    v9 = v12;
  }
  if ( v9 )
  {
    v10 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v9 + 40));
    if ( v10 >= 0 )
      v9[80] = 1;
    v11 = 0;
    if ( v10 < 0 )
      v11 = v10;
    if ( v11 >= 0 )
      v11 = CTaskHandler::FinalConstruct((struct _RTL_CRITICAL_SECTION *)(v9 + 24));
    v7 = 0;
    if ( v11 < 0 )
      v7 = v11;
    if ( v7 || (v7 = (**(__int64 (__fastcall ***)(char *, __int64, _QWORD *))v9)(v9, v4, v3)) != 0 )
      (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v9 + 24LL))(v9, 1);
  }
  return v7;
}

```

## disassembly

```asm
0x180003358  mov     [rsp+arg_0], rsi
0x18000335d  mov     [rsp+arg_10], r8
0x180003362  mov     [rsp+arg_8], rdx
0x180003367  push    rdi
0x180003368  push    r12
0x18000336a  push    r13
0x18000336c  push    r14
0x18000336e  push    r15
0x180003370  sub     rsp, 30h
0x180003374  mov     r14, r8
0x180003377  mov     r15, rdx
0x18000337a  mov     r12, rcx
0x18000337d  test    r8, r8
0x180003380  jnz     short loc_18000338C
0x180003382  mov     eax, 80004003h
0x180003387  jmp     loc_180003483
0x18000338c  mov     qword ptr [r8], 0
0x180003393  mov     esi, 8007000Eh
0x180003398  mov     [rsp+58h+arg_18], esi
0x18000339c  mov     [rsp+58h+var_38], 0
0x1800033a5  mov     ecx, 0A8h; Size
0x1800033aa  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800033af  mov     rdi, rax
0x1800033b2  test    rdi, rdi
0x1800033b5  jz      short loc_180003402
0x1800033b7  mov     dword ptr [rax+8], 0
0x1800033be  lea     rax, ??_7?$CComAggObject@VCTaskHandler@@@ATL@@6B@; const ATL::CComAggObject<CTaskHandler>::`vftable'
0x1800033c5  mov     [rdi], rax
0x1800033c8  xorps   xmm0, xmm0
0x1800033cb  xor     eax, eax
0x1800033cd  movups  xmmword ptr [rdi+28h], xmm0
0x1800033d1  movups  xmmword ptr [rdi+38h], xmm0
0x1800033d5  mov     [rdi+48h], rax
0x1800033d9  mov     [rdi+50h], al
0x1800033dc  mov     [rdi+58h], rax
0x1800033e0  lea     rax, ??_7?$CComContainedObject@VCTaskHandler@@@ATL@@6B@; const ATL::CComContainedObject<CTaskHandler>::`vftable'
0x1800033e7  mov     [rdi+18h], rax
0x1800033eb  mov     [rdi+20h], r12
0x1800033ef  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800033f6  mov     rax, [rcx]
0x1800033f9  mov     rax, [rax+8]
0x1800033fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003402  mov     [rsp+58h+var_38], rdi
0x180003407  jmp     short loc_18000341C
0x180003409  mov     r14, [rsp+58h+arg_10]
0x18000340e  mov     r15, [rsp+58h+arg_8]
0x180003413  mov     esi, [rsp+58h+arg_18]
0x180003417  mov     rdi, [rsp+58h+var_38]
0x18000341c  test    rdi, rdi
0x18000341f  jz      short loc_180003481
0x180003421  lea     rcx, [rdi+28h]; this
0x180003425  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18000342a  mov     ecx, eax
0x18000342c  test    eax, eax
0x18000342e  js      short loc_180003434
0x180003430  mov     byte ptr [rdi+50h], 1
0x180003434  xor     eax, eax
0x180003436  test    ecx, ecx
0x180003438  cmovs   eax, ecx
0x18000343b  test    eax, eax
0x18000343d  js      short loc_180003448
0x18000343f  lea     rcx, [rdi+18h]; this
0x180003443  call    ?FinalConstruct@CTaskHandler@@QEAAJXZ; CTaskHandler::FinalConstruct(void)
0x180003448  xor     esi, esi
0x18000344a  test    eax, eax
0x18000344c  cmovs   esi, eax
0x18000344f  test    esi, esi
0x180003451  jnz     short loc_18000346D
0x180003453  mov     rax, [rdi]
0x180003456  mov     r8, r14
0x180003459  mov     rdx, r15
0x18000345c  mov     rcx, rdi
0x18000345f  mov     rax, [rax]
0x180003462  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003467  mov     esi, eax
0x180003469  test    eax, eax
0x18000346b  jz      short loc_180003481
0x18000346d  mov     r8, [rdi]
0x180003470  mov     edx, 1
0x180003475  mov     rcx, rdi
0x180003478  mov     rax, [r8+18h]
0x18000347c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003481  mov     eax, esi
0x180003483  mov     rsi, [rsp+58h+arg_0]
0x180003488  add     rsp, 30h
0x18000348c  pop     r15
0x18000348e  pop     r14
0x180003490  pop     r13
0x180003492  pop     r12
0x180003494  pop     rdi
0x180003495  retn
```
