# ATL::CComCreator<ATL::CComAggObject<CDataIntegrityScanTaskHandler>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x1800036b4`
- end: `0x1800037df`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCDataIntegrityScanTaskHandler@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `299`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800036a0`

## callees

- `0x180001b78`
- `0x180002ec4`
- `0x1800036b4`
- `0x180004424`
- `0x180004a4c`
- `0x180039010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CDataIntegrityScanTaskHandler>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rsi
  __int64 v4; // r14
  unsigned int v7; // edi
  char *v8; // rax
  _BYTE *v9; // rbx
  _QWORD *v10; // rcx
  int v11; // ecx
  int v12; // eax
  _BYTE *v13; // [rsp+20h] [rbp-38h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v7 = -2147024882;
    v8 = (char *)operator new(0x1C8u);
    v9 = v8;
    if ( v8 )
    {
      *((_DWORD *)v8 + 2) = 0;
      *(_QWORD *)v8 = &ATL::CComAggObject<CDataIntegrityScanTaskHandler>::`vftable';
      CDataIntegrityScanTaskHandler::CDataIntegrityScanTaskHandler((CDataIntegrityScanTaskHandler *)(v8 + 24));
      *v10 = &ATL::CComContainedObject<CDataIntegrityScanTaskHandler>::`vftable'{for `ITaskHandler'};
      v10[1] = &ATL::CComObject<CDataIntegrityScanTaskHandler>::`vftable'{for `ISystemScanNotify'};
      v10[2] = a1;
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
    v11 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v9 + 48));
    if ( v11 >= 0 )
      v9[88] = 1;
    v12 = 0;
    if ( v11 < 0 )
      v12 = v11;
    if ( v12 >= 0 )
      v12 = CDataIntegrityScanTaskHandler::FinalConstruct(v9 + 24);
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
0x1800036b4  mov     [rsp+arg_10], r8
0x1800036b9  mov     [rsp+arg_8], rdx
0x1800036be  push    rbx
0x1800036bf  push    rsi
0x1800036c0  push    rdi
0x1800036c1  push    r14
0x1800036c3  push    r15
0x1800036c5  sub     rsp, 30h
0x1800036c9  mov     rsi, r8
0x1800036cc  mov     r14, rdx
0x1800036cf  mov     r15, rcx
0x1800036d2  test    r8, r8
0x1800036d5  jnz     short loc_1800036E1
0x1800036d7  mov     eax, 80004003h
0x1800036dc  jmp     loc_1800037D3
0x1800036e1  mov     qword ptr [r8], 0
0x1800036e8  mov     edi, 8007000Eh
0x1800036ed  mov     [rsp+58h+arg_18], edi
0x1800036f1  mov     [rsp+58h+var_38], 0
0x1800036fa  mov     ecx, 1C8h; Size
0x1800036ff  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003704  mov     rbx, rax
0x180003707  test    rbx, rbx
0x18000370a  jz      short loc_180003752
0x18000370c  mov     dword ptr [rax+8], 0
0x180003713  lea     rax, ??_7?$CComAggObject@VCDataIntegrityScanTaskHandler@@@ATL@@6B@; const ATL::CComAggObject<CDataIntegrityScanTaskHandler>::`vftable'
0x18000371a  mov     [rbx], rax
0x18000371d  lea     rcx, [rbx+18h]; this
0x180003721  call    ??0CDataIntegrityScanTaskHandler@@QEAA@XZ; CDataIntegrityScanTaskHandler::CDataIntegrityScanTaskHandler(void)
0x180003726  lea     r8, ??_7?$CComContainedObject@VCDataIntegrityScanTaskHandler@@@ATL@@6BITaskHandler@@@; const ATL::CComContainedObject<CDataIntegrityScanTaskHandler>::`vftable'{for `ITaskHandler'}
0x18000372d  mov     [rcx], r8
0x180003730  lea     rax, ??_7?$CComObject@VCDataIntegrityScanTaskHandler@@@ATL@@6BISystemScanNotify@@@; const ATL::CComObject<CDataIntegrityScanTaskHandler>::`vftable'{for `ISystemScanNotify'}
0x180003737  mov     [rcx+8], rax
0x18000373b  mov     [rcx+10h], r15
0x18000373f  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180003746  mov     rax, [rcx]
0x180003749  mov     rax, [rax+8]
0x18000374d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003752  mov     [rsp+58h+var_38], rbx
0x180003757  jmp     short loc_18000376C
0x180003759  mov     rsi, [rsp+58h+arg_10]
0x18000375e  mov     r14, [rsp+58h+arg_8]
0x180003763  mov     edi, [rsp+58h+arg_18]
0x180003767  mov     rbx, [rsp+58h+var_38]
0x18000376c  test    rbx, rbx
0x18000376f  jz      short loc_1800037D1
0x180003771  lea     rcx, [rbx+30h]; this
0x180003775  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18000377a  mov     ecx, eax
0x18000377c  test    eax, eax
0x18000377e  js      short loc_180003784
0x180003780  mov     byte ptr [rbx+58h], 1
0x180003784  xor     eax, eax
0x180003786  test    ecx, ecx
0x180003788  cmovs   eax, ecx
0x18000378b  test    eax, eax
0x18000378d  js      short loc_180003798
0x18000378f  lea     rcx, [rbx+18h]; pv
0x180003793  call    ?FinalConstruct@CDataIntegrityScanTaskHandler@@QEAAJXZ; CDataIntegrityScanTaskHandler::FinalConstruct(void)
0x180003798  xor     edi, edi
0x18000379a  test    eax, eax
0x18000379c  cmovs   edi, eax
0x18000379f  test    edi, edi
0x1800037a1  jnz     short loc_1800037BD
0x1800037a3  mov     rax, [rbx]
0x1800037a6  mov     r8, rsi
0x1800037a9  mov     rdx, r14
0x1800037ac  mov     rcx, rbx
0x1800037af  mov     rax, [rax]
0x1800037b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037b7  mov     edi, eax
0x1800037b9  test    eax, eax
0x1800037bb  jz      short loc_1800037D1
0x1800037bd  mov     r8, [rbx]
0x1800037c0  mov     edx, 1
0x1800037c5  mov     rcx, rbx
0x1800037c8  mov     rax, [r8+18h]
0x1800037cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037d1  mov     eax, edi
0x1800037d3  add     rsp, 30h
0x1800037d7  pop     r15
0x1800037d9  pop     r14
0x1800037db  pop     rdi
0x1800037dc  pop     rsi
0x1800037dd  pop     rbx
0x1800037de  retn
```
