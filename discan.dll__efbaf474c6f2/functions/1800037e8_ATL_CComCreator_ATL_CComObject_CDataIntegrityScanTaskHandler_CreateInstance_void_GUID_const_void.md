# ATL::CComCreator<ATL::CComObject<CDataIntegrityScanTaskHandler>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x1800037e8`
- end: `0x180003903`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCDataIntegrityScanTaskHandler@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `283`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800036a0`

## callees

- `0x180001b78`
- `0x180002ec4`
- `0x1800037e8`
- `0x180004424`
- `0x180004a4c`
- `0x180004fd4`
- `0x180004ffc`
- `0x180039010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CDataIntegrityScanTaskHandler>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rsi
  __int64 v4; // r15
  unsigned int v6; // edi
  CDataIntegrityScanTaskHandler *v7; // rax
  volatile int *v8; // rbx
  int v9; // eax
  volatile int *v12; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v6 = -2147024882;
    v7 = (CDataIntegrityScanTaskHandler *)operator new(0x1B0u);
    v8 = (volatile int *)v7;
    if ( v7 )
    {
      CDataIntegrityScanTaskHandler::CDataIntegrityScanTaskHandler(v7);
      *(_QWORD *)v8 = &ATL::CComObject<CDataIntegrityScanTaskHandler>::`vftable'{for `ITaskHandler'};
      *((_QWORD *)v8 + 1) = &ATL::CComObject<CDataIntegrityScanTaskHandler>::`vftable'{for `ISystemScanNotify'};
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    v12 = v8;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v6 = -2147024882;
    v8 = v12;
  }
  if ( v8 )
  {
    ATL::SafeIncrementReferenceMultiThread(v8 + 4);
    v9 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v8 + 6));
    if ( v9 >= 0 )
    {
      *((_BYTE *)v8 + 64) = 1;
      v9 = CDataIntegrityScanTaskHandler::FinalConstruct((PVOID)v8);
    }
    v6 = 0;
    if ( v9 < 0 )
      v6 = v9;
    ATL::SafeDecrementReferenceMultiThread(v8 + 4);
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(volatile int *, __int64, _QWORD *))v8)(v8, v4, v3)) != 0 )
      (*(void (__fastcall **)(volatile int *, __int64))(*(_QWORD *)v8 + 56LL))(v8, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x1800037e8  mov     [rsp+arg_10], r8
0x1800037ed  mov     [rsp+arg_8], rdx
0x1800037f2  mov     [rsp+arg_0], rcx
0x1800037f7  push    rbx
0x1800037f8  push    rsi
0x1800037f9  push    rdi
0x1800037fa  push    r14
0x1800037fc  push    r15
0x1800037fe  sub     rsp, 20h
0x180003802  mov     rsi, r8
0x180003805  mov     r15, rdx
0x180003808  test    r8, r8
0x18000380b  jnz     short loc_180003817
0x18000380d  mov     eax, 80004003h
0x180003812  jmp     loc_1800038F7
0x180003817  mov     qword ptr [r8], 0
0x18000381e  mov     edi, 8007000Eh
0x180003823  mov     dword ptr [rsp+48h+arg_0], edi
0x180003827  mov     [rsp+48h+arg_18], 0
0x180003830  mov     ecx, 1B0h; Size
0x180003835  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000383a  mov     rbx, rax
0x18000383d  test    rbx, rbx
0x180003840  jz      short loc_180003872
0x180003842  mov     rcx, rax; this
0x180003845  call    ??0CDataIntegrityScanTaskHandler@@QEAA@XZ; CDataIntegrityScanTaskHandler::CDataIntegrityScanTaskHandler(void)
0x18000384a  lea     rcx, ??_7?$CComObject@VCDataIntegrityScanTaskHandler@@@ATL@@6BITaskHandler@@@; const ATL::CComObject<CDataIntegrityScanTaskHandler>::`vftable'{for `ITaskHandler'}
0x180003851  mov     [rbx], rcx
0x180003854  lea     rax, ??_7?$CComObject@VCDataIntegrityScanTaskHandler@@@ATL@@6BISystemScanNotify@@@; const ATL::CComObject<CDataIntegrityScanTaskHandler>::`vftable'{for `ISystemScanNotify'}
0x18000385b  mov     [rbx+8], rax
0x18000385f  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180003866  mov     rax, [rcx]
0x180003869  mov     rax, [rax+8]
0x18000386d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003872  mov     [rsp+48h+arg_18], rbx
0x180003877  jmp     short loc_18000388C
0x180003879  mov     rsi, [rsp+48h+arg_10]
0x18000387e  mov     r15, [rsp+48h+arg_8]
0x180003883  mov     edi, dword ptr [rsp+48h+arg_0]
0x180003887  mov     rbx, [rsp+48h+arg_18]
0x18000388c  test    rbx, rbx
0x18000388f  jz      short loc_1800038F5
0x180003891  lea     rcx, [rbx+10h]; volatile int *
0x180003895  call    ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
0x18000389a  lea     rcx, [rbx+18h]; this
0x18000389e  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1800038a3  test    eax, eax
0x1800038a5  js      short loc_1800038B3
0x1800038a7  mov     byte ptr [rbx+40h], 1
0x1800038ab  mov     rcx, rbx; pv
0x1800038ae  call    ?FinalConstruct@CDataIntegrityScanTaskHandler@@QEAAJXZ; CDataIntegrityScanTaskHandler::FinalConstruct(void)
0x1800038b3  xor     edi, edi
0x1800038b5  test    eax, eax
0x1800038b7  cmovs   edi, eax
0x1800038ba  lea     rcx, [rbx+10h]; volatile int *
0x1800038be  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x1800038c3  test    edi, edi
0x1800038c5  jnz     short loc_1800038E1
0x1800038c7  mov     rax, [rbx]
0x1800038ca  mov     r8, rsi
0x1800038cd  mov     rdx, r15
0x1800038d0  mov     rcx, rbx
0x1800038d3  mov     rax, [rax]
0x1800038d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038db  mov     edi, eax
0x1800038dd  test    eax, eax
0x1800038df  jz      short loc_1800038F5
0x1800038e1  mov     r8, [rbx]
0x1800038e4  mov     edx, 1
0x1800038e9  mov     rcx, rbx
0x1800038ec  mov     rax, [r8+38h]
0x1800038f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038f5  mov     eax, edi
0x1800038f7  add     rsp, 20h
0x1800038fb  pop     r15
0x1800038fd  pop     r14
0x1800038ff  pop     rdi
0x180003900  pop     rsi
0x180003901  pop     rbx
0x180003902  retn
```
