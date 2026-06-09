# ATL::CComCreator<ATL::CComObject<IASTL::IASComponentObject<InfoBase>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000f538`
- end: `0x18000f6b8`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@V?$IASComponentObject@VInfoBase@@@IASTL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `384`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000f4b0`

## callees

- `0x18000d98c`
- `0x18000f538`
- `0x18001033c`
- `0x180014cc0`
- `0x180016634`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<IASTL::IASComponentObject<InfoBase>>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // r15
  __int64 v4; // r12
  unsigned int v6; // r14d
  _DWORD *v7; // rax
  _DWORD *v8; // rsi
  int v9; // ecx
  int v10; // eax
  _DWORD *v13; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v6 = -2147024882;
    v7 = operator new(0x88u);
    v8 = v7;
    if ( v7 )
    {
      v7[2] = 0;
      *((_OWORD *)v7 + 1) = 0;
      *((_OWORD *)v7 + 2) = 0;
      *((_QWORD *)v7 + 6) = 0;
      *((_BYTE *)v7 + 56) = 0;
      IASTraceInitializeEx(0);
      v8[16] = 0;
      *((_QWORD *)v8 + 10) = 0;
      *((_QWORD *)v8 + 11) = 0;
      *((_QWORD *)v8 + 10) = std::_Tree_alloc<0,std::_Tree_base_types<std::pair<std::wstring const,_RadiusClientEntry *>>>::_Buyheadnode();
      *((_QWORD *)v8 + 12) = 0;
      *((_QWORD *)v8 + 13) = 0;
      v8[28] = 0;
      *((_QWORD *)v8 + 15) = 0;
      *((_QWORD *)v8 + 16) = 0;
      *(_QWORD *)v8 = &ATL::CComObject<IASTL::IASComponentObject<InfoBase>>::`vftable'{for `IASTL::IASComponent'};
      *((_QWORD *)v8 + 9) = &ATL::CComObject<IASTL::IASComponentObject<InfoBase>>::`vftable'{for `IAuditSink'};
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    v13 = v8;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v6 = -2147024882;
    v8 = v13;
  }
  if ( v8 )
  {
    v9 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v8 + 4));
    if ( v9 >= 0 )
      *((_BYTE *)v8 + 56) = 1;
    v10 = 0;
    if ( v9 < 0 )
      v10 = v9;
    v6 = 0;
    if ( v10 < 0 )
      v6 = v10;
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, _QWORD *))v8)(v8, v4, v3)) != 0 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v8 + 128LL))(v8, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x18000f538  mov     [rsp+arg_10], r8
0x18000f53d  mov     [rsp+arg_8], rdx
0x18000f542  mov     [rsp+arg_0], rcx
0x18000f547  push    rbx
0x18000f548  push    rsi
0x18000f549  push    r12
0x18000f54b  push    r14
0x18000f54d  push    r15
0x18000f54f  sub     rsp, 20h
0x18000f553  mov     r15, r8
0x18000f556  mov     r12, rdx
0x18000f559  test    r8, r8
0x18000f55c  jnz     short loc_18000F568
0x18000f55e  mov     eax, 80004003h
0x18000f563  jmp     loc_18000F6AB
0x18000f568  mov     qword ptr [r8], 0
0x18000f56f  mov     r14d, 8007000Eh
0x18000f575  mov     dword ptr [rsp+48h+arg_0], r14d
0x18000f57a  mov     [rsp+48h+arg_18], 0
0x18000f583  mov     ecx, 88h; Size
0x18000f588  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f58d  mov     rsi, rax
0x18000f590  test    rsi, rsi
0x18000f593  jz      loc_18000F62E
0x18000f599  mov     dword ptr [rax+8], 0
0x18000f5a0  xorps   xmm0, xmm0
0x18000f5a3  xor     eax, eax
0x18000f5a5  movups  xmmword ptr [rsi+10h], xmm0
0x18000f5a9  movups  xmmword ptr [rsi+20h], xmm0
0x18000f5ad  mov     [rsi+30h], rax
0x18000f5b1  mov     [rsi+38h], al
0x18000f5b4  xor     ecx, ecx; Source
0x18000f5b6  call    IASTraceInitializeEx
0x18000f5bb  nop
0x18000f5bc  mov     dword ptr [rsi+40h], 0
0x18000f5c3  mov     qword ptr [rsi+50h], 0
0x18000f5cb  mov     qword ptr [rsi+58h], 0
0x18000f5d3  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAU_RadiusClientEntry@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAU_RadiusClientEntry@@@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAU_RadiusClientEntry@@@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::pair<std::wstring const,_RadiusClientEntry *>>>::_Buyheadnode(void)
0x18000f5d8  mov     [rsi+50h], rax
0x18000f5dc  mov     qword ptr [rsi+60h], 0
0x18000f5e4  mov     qword ptr [rsi+68h], 0
0x18000f5ec  mov     dword ptr [rsi+70h], 0
0x18000f5f3  mov     qword ptr [rsi+78h], 0
0x18000f5fb  mov     qword ptr [rsi+80h], 0
0x18000f606  lea     rax, ??_7?$CComObject@V?$IASComponentObject@VInfoBase@@@IASTL@@@ATL@@6BIASComponent@IASTL@@@; const ATL::CComObject<IASTL::IASComponentObject<InfoBase>>::`vftable'{for `IASTL::IASComponent'}
0x18000f60d  mov     [rsi], rax
0x18000f610  lea     rax, ??_7?$CComObject@V?$IASComponentObject@VInfoBase@@@IASTL@@@ATL@@6BIAuditSink@@@; const ATL::CComObject<IASTL::IASComponentObject<InfoBase>>::`vftable'{for `IAuditSink'}
0x18000f617  mov     [rsi+48h], rax
0x18000f61b  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000f622  mov     rax, [rcx]
0x18000f625  mov     rax, [rax+8]
0x18000f629  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f62e  mov     [rsp+48h+arg_18], rsi
0x18000f633  jmp     short loc_18000F649
0x18000f635  mov     r15, [rsp+48h+arg_10]
0x18000f63a  mov     r12, [rsp+48h+arg_8]
0x18000f63f  mov     r14d, dword ptr [rsp+48h+arg_0]
0x18000f644  mov     rsi, [rsp+48h+arg_18]
0x18000f649  test    rsi, rsi
0x18000f64c  jz      short loc_18000F6A8
0x18000f64e  lea     rcx, [rsi+10h]; this
0x18000f652  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18000f657  mov     ecx, eax
0x18000f659  test    eax, eax
0x18000f65b  js      short loc_18000F661
0x18000f65d  mov     byte ptr [rsi+38h], 1
0x18000f661  xor     eax, eax
0x18000f663  test    ecx, ecx
0x18000f665  cmovs   eax, ecx
0x18000f668  xor     r14d, r14d
0x18000f66b  test    eax, eax
0x18000f66d  cmovs   r14d, eax
0x18000f671  test    r14d, r14d
0x18000f674  jnz     short loc_18000F691
0x18000f676  mov     rax, [rsi]
0x18000f679  mov     r8, r15
0x18000f67c  mov     rdx, r12
0x18000f67f  mov     rcx, rsi
0x18000f682  mov     rax, [rax]
0x18000f685  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f68a  mov     r14d, eax
0x18000f68d  test    eax, eax
0x18000f68f  jz      short loc_18000F6A8
0x18000f691  mov     r8, [rsi]
0x18000f694  mov     edx, 1
0x18000f699  mov     rcx, rsi
0x18000f69c  mov     rax, [r8+80h]
0x18000f6a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f6a8  mov     eax, r14d
0x18000f6ab  add     rsp, 20h
0x18000f6af  pop     r15
0x18000f6b1  pop     r14
0x18000f6b3  pop     r12
0x18000f6b5  pop     rsi
0x18000f6b6  pop     rbx
0x18000f6b7  retn
```
