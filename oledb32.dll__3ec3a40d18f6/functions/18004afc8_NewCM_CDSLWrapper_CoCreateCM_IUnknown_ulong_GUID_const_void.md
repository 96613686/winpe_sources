# NewCM<CDSLWrapper>::CoCreateCM(IUnknown *,ulong,_GUID const &,void * *)

- ea: `0x18004afc8`
- end: `0x18004b265`
- name: `?CoCreateCM@?$NewCM@VCDSLWrapper@@@@SAJPEAUIUnknown@@KAEBU_GUID@@PEAPEAX@Z`
- size: `669`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004d3f8`

## callees

- `0x180013870`
- `0x180026620`
- `0x180029560`
- `0x18002b0c0`
- `0x18002ec0c`
- `0x18003c44c`
- `0x18003c8ac`
- `0x18004afc8`
- `0x180087010`

## import_xrefs

- `MSDART!MpHeapAlloc` at `0x18004b016`
- `MSDART!MpHeapAlloc` at `0x18004b016`

## string_xrefs

- `0x18004b0b8`: `<NewCM<class CDSLWrapper>::CoCreateCM|OLEDB|ERR> `
- `0x18004b0d6`: `<NewCM<class CDSLWrapper>::CoCreateCM|OLEDB|ERR> `
- `0x18004b16e`: `<NewCM<class CDSLWrapper>::CoCreateCM|OLEDB|ERR> `
- `0x18004b1e0`: `<NewCM<class CDSLWrapper>::CoCreateCM|OLEDB|ERR> `
- `0x18004b0f1`: `<NewCM<class CDSLWrapper>::CoCreateCM|Trace|HR> `
- `0x18004b189`: `<NewCM<class CDSLWrapper>::CoCreateCM|Trace|HR> `
- `0x18004b1fb`: `<NewCM<class CDSLWrapper>::CoCreateCM|Trace|HR> `
- `0x18004b23b`: `<NewCM<class CDSLWrapper>::CoCreateCM|Trace|HR> `

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall NewCM<CDSLWrapper>::CoCreateCM(__int64 a1, __int64 a2, __int64 a3, _QWORD *a4)
{
  __int64 v6; // rax
  __int64 v7; // rdi
  int v8; // esi
  unsigned int v9; // ebx
  int v10; // ebx
  int pExceptionObject; // [rsp+20h] [rbp-28h] BYREF
  unsigned int v12; // [rsp+24h] [rbp-24h] BYREF
  int v13; // [rsp+28h] [rbp-20h] BYREF
  __int64 v14; // [rsp+60h] [rbp+18h] BYREF

  v14 = a3;
  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  v14 = 0;
  v6 = MpHeapAlloc(g_hHeapHandle, 19922944, 208);
  v7 = v6;
  if ( !v6 )
  {
    v10 = -2147024882;
    if ( (bidGblFlags & 2) != 0 )
    {
      OLEDBTraceErr(-2147024882, L"<NewCM<class CDSLWrapper>::CoCreateCM|OLEDB|ERR> ", 0x24Cu);
      if ( (bidGblFlags & 2) != 0 )
        v10 = bidTraceHR(
                `NewCM<CDSLWrapper>::CoCreateCM'::`2'::_bidSrcFile2A[0],
                602121,
                L"<NewCM<class CDSLWrapper>::CoCreateCM|Trace|HR> ",
                2147942414LL);
    }
    v13 = v10;
    throw (long *)&v13;
  }
  *(_DWORD *)(v6 + 8) = 0;
  *(_QWORD *)v6 = &ATL::CComPolyObject<CDSLWrapper>::`vftable';
  CAcm::CAcm((CAcm *)(v6 + 24));
  *(_QWORD *)(v7 + 24) = &ATL::CComContainedObject<CDSLWrapper>::`vftable'{for `IService'};
  *(_QWORD *)(v7 + 32) = &ATL::CComContainedObject<CMRCM>::`vftable'{for `IOuterUnknown'};
  *(_QWORD *)(v7 + 40) = v7;
  _InterlockedIncrement(&dword_1800BE368);
  *(_QWORD *)v7 = &CACMComPolyObject<CDSLWrapper>::`vftable';
  *(_QWORD *)(v7 + 192) = v7;
  ATL::SafeIncrementReferenceMultiThread((volatile int *)(v7 + 8));
  v8 = CAcm::FinalConstruct((CAcm *)(v7 + 24));
  ATL::SafeDecrementReferenceMultiThread((volatile int *)(v7 + 8));
  if ( v8 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      OLEDBTraceErr(v8, L"<NewCM<class CDSLWrapper>::CoCreateCM|OLEDB|ERR> ", 0x250u);
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(v8, L"<NewCM<class CDSLWrapper>::CoCreateCM|OLEDB|ERR> ", 0x250u);
        if ( (bidGblFlags & 2) != 0 )
          v8 = bidTraceHR(
                 `NewCM<CDSLWrapper>::CoCreateCM'::`2'::_bidSrcFile2A[0],
                 606217,
                 L"<NewCM<class CDSLWrapper>::CoCreateCM|Trace|HR> ",
                 (unsigned int)v8);
      }
    }
    pExceptionObject = v8;
    throw (long *)&pExceptionObject;
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
  v9 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v7)(v7, &IID_IOuterUnknown, &v14);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  if ( (v9 & 0x80000000) != 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      OLEDBTraceErr(v9, L"<NewCM<class CDSLWrapper>::CoCreateCM|OLEDB|ERR> ", 0x259u);
      if ( (bidGblFlags & 2) != 0 )
        v9 = bidTraceHR(
               `NewCM<CDSLWrapper>::CoCreateCM'::`2'::_bidSrcFile2A[0],
               615433,
               L"<NewCM<class CDSLWrapper>::CoCreateCM|Trace|HR> ",
               v9);
    }
    v12 = v9;
    throw (long *)&v12;
  }
  *a4 = v14;
  if ( (bidGblFlags & 2) != 0 )
    return (unsigned int)bidTraceHR(
                           `NewCM<CDSLWrapper>::CoCreateCM'::`2'::_bidSrcFile2A[0],
                           637961,
                           L"<NewCM<class CDSLWrapper>::CoCreateCM|Trace|HR> ",
                           v9);
  return v9;
}

```

## disassembly

```asm
0x18004afc8  mov     rax, rsp
0x18004afcb  mov     [rax+20h], rbx
0x18004afcf  mov     [rax+18h], r8
0x18004afd3  mov     [rax+10h], edx
0x18004afd6  mov     [rax+8], rcx
0x18004afda  push    rsi
0x18004afdb  push    rdi
0x18004afdc  push    r14
0x18004afde  sub     rsp, 30h
0x18004afe2  mov     r14, r9
0x18004afe5  test    r9, r9
0x18004afe8  jnz     short loc_18004AFF4
0x18004afea  mov     eax, 80004003h
0x18004afef  jmp     loc_18004B257
0x18004aff4  mov     qword ptr [r9], 0
0x18004affb  mov     [rsp+48h+arg_10], 0
0x18004b004  mov     edx, 1300000h
0x18004b009  mov     r8d, 0D0h
0x18004b00f  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x18004b016  call    cs:__imp_MpHeapAlloc
0x18004b01c  mov     rdi, rax
0x18004b01f  mov     [rsp+48h+arg_0], rax
0x18004b024  test    rax, rax
0x18004b027  jz      loc_18004B1C2
0x18004b02d  mov     dword ptr [rax+8], 0
0x18004b034  lea     rax, ??_7?$CComPolyObject@VCDSLWrapper@@@ATL@@6B@; const ATL::CComPolyObject<CDSLWrapper>::`vftable'
0x18004b03b  mov     [rdi], rax
0x18004b03e  lea     rcx, [rdi+18h]; this
0x18004b042  call    ??0CAcm@@QEAA@XZ; CAcm::CAcm(void)
0x18004b047  lea     rax, ??_7?$CComContainedObject@VCDSLWrapper@@@ATL@@6BIService@@@; const ATL::CComContainedObject<CDSLWrapper>::`vftable'{for `IService'}
0x18004b04e  mov     [rdi+18h], rax
0x18004b052  lea     rax, ??_7?$CComContainedObject@VCMRCM@@@ATL@@6BIOuterUnknown@@@; const ATL::CComContainedObject<CMRCM>::`vftable'{for `IOuterUnknown'}
0x18004b059  mov     [rdi+20h], rax
0x18004b05d  mov     [rdi+28h], rdi
0x18004b061  lock inc cs:dword_1800BE368
0x18004b068  lea     rax, ??_7?$CACMComPolyObject@VCDSLWrapper@@@@6B@; const CACMComPolyObject<CDSLWrapper>::`vftable'
0x18004b06f  mov     [rdi], rax
0x18004b072  mov     [rdi+0C0h], rdi
0x18004b079  mov     [rsp+48h+arg_0], rdi
0x18004b07e  test    rdi, rdi
0x18004b081  jz      loc_18004B1CB
0x18004b087  lea     rcx, [rdi+8]; volatile int *
0x18004b08b  call    ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
0x18004b090  lea     rcx, [rdi+18h]; this
0x18004b094  call    ?FinalConstruct@CAcm@@QEAAJXZ; CAcm::FinalConstruct(void)
0x18004b099  mov     esi, eax
0x18004b09b  lea     rcx, [rdi+8]; volatile int *
0x18004b09f  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x18004b0a4  test    esi, esi
0x18004b0a6  jns     short loc_18004B120
0x18004b0a8  mov     eax, cs:_bidGblFlags
0x18004b0ae  test    al, 2
0x18004b0b0  jz      short loc_18004B10B
0x18004b0b2  mov     r8d, 250h; unsigned int
0x18004b0b8  lea     rdx, aNewcmClassCdsl_0; "<NewCM<class CDSLWrapper>::CoCreateCM|O"...
0x18004b0bf  mov     ecx, esi; int
0x18004b0c1  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18004b0c6  mov     eax, cs:_bidGblFlags
0x18004b0cc  test    al, 2
0x18004b0ce  jz      short loc_18004B10B
0x18004b0d0  mov     r8d, 250h; unsigned int
0x18004b0d6  lea     rdx, aNewcmClassCdsl_0; "<NewCM<class CDSLWrapper>::CoCreateCM|O"...
0x18004b0dd  mov     ecx, esi; int
0x18004b0df  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18004b0e4  mov     eax, cs:_bidGblFlags
0x18004b0ea  test    al, 2
0x18004b0ec  jz      short loc_18004B10B
0x18004b0ee  mov     r9d, esi
0x18004b0f1  lea     r8, aNewcmClassCdsl_1; "<NewCM<class CDSLWrapper>::CoCreateCM|T"...
0x18004b0f8  mov     edx, 94009h
0x18004b0fd  mov     rcx, cs:?_bidSrcFile2A@?1??CoCreateCM@?$NewCM@VCDSLWrapper@@@@SAJPEAUIUnknown@@KAEBU_GUID@@PEAPEAX@Z@4REBDEB; char const * const `NewCM<CDSLWrapper>::CoCreateCM(IUnknown *,ulong,_GUID const &,void * *)'::`2'::_bidSrcFile2A
0x18004b104  call    _bidTraceHR
0x18004b109  mov     esi, eax
0x18004b10b  mov     [rsp+48h+pExceptionObject], esi
0x18004b10f  lea     rdx, _TI1J; pThrowInfo
0x18004b116  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18004b11b  call    _CxxThrowException_0
0x18004b120  mov     rax, [rdi]
0x18004b123  mov     rcx, rdi
0x18004b126  mov     rax, [rax+8]
0x18004b12a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b12f  mov     rax, [rdi]
0x18004b132  lea     r8, [rsp+48h+arg_10]
0x18004b137  lea     rdx, IID_IOuterUnknown
0x18004b13e  mov     rcx, rdi
0x18004b141  mov     rax, [rax]
0x18004b144  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b149  mov     ebx, eax
0x18004b14b  mov     rax, [rdi]
0x18004b14e  mov     rax, [rax+10h]
0x18004b152  mov     rcx, rdi
0x18004b155  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b15a  test    ebx, ebx
0x18004b15c  jns     short loc_18004B1B8
0x18004b15e  mov     eax, cs:_bidGblFlags
0x18004b164  test    al, 2
0x18004b166  jz      short loc_18004B1A3
0x18004b168  mov     r8d, 259h; unsigned int
0x18004b16e  lea     rdx, aNewcmClassCdsl_0; "<NewCM<class CDSLWrapper>::CoCreateCM|O"...
0x18004b175  mov     ecx, ebx; int
0x18004b177  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18004b17c  mov     eax, cs:_bidGblFlags
0x18004b182  test    al, 2
0x18004b184  jz      short loc_18004B1A3
0x18004b186  mov     r9d, ebx
0x18004b189  lea     r8, aNewcmClassCdsl_1; "<NewCM<class CDSLWrapper>::CoCreateCM|T"...
0x18004b190  mov     edx, 96409h
0x18004b195  mov     rcx, cs:?_bidSrcFile2A@?1??CoCreateCM@?$NewCM@VCDSLWrapper@@@@SAJPEAUIUnknown@@KAEBU_GUID@@PEAPEAX@Z@4REBDEB; char const * const `NewCM<CDSLWrapper>::CoCreateCM(IUnknown *,ulong,_GUID const &,void * *)'::`2'::_bidSrcFile2A
0x18004b19c  call    _bidTraceHR
0x18004b1a1  mov     ebx, eax
0x18004b1a3  mov     [rsp+48h+var_24], ebx
0x18004b1a7  lea     rdx, _TI1J; pThrowInfo
0x18004b1ae  lea     rcx, [rsp+48h+var_24]; pExceptionObject
0x18004b1b3  call    _CxxThrowException_0
0x18004b1b8  mov     rax, [rsp+48h+arg_10]
0x18004b1bd  mov     [r14], rax
0x18004b1c0  jmp     short loc_18004B22F
0x18004b1c2  mov     [rsp+48h+arg_0], 0
0x18004b1cb  mov     eax, cs:_bidGblFlags
0x18004b1d1  mov     ebx, 8007000Eh
0x18004b1d6  test    al, 2
0x18004b1d8  jz      short loc_18004B215
0x18004b1da  mov     r8d, 24Ch; unsigned int
0x18004b1e0  lea     rdx, aNewcmClassCdsl_0; "<NewCM<class CDSLWrapper>::CoCreateCM|O"...
0x18004b1e7  mov     ecx, ebx; int
0x18004b1e9  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18004b1ee  mov     eax, cs:_bidGblFlags
0x18004b1f4  test    al, 2
0x18004b1f6  jz      short loc_18004B215
0x18004b1f8  mov     r9d, ebx
0x18004b1fb  lea     r8, aNewcmClassCdsl_1; "<NewCM<class CDSLWrapper>::CoCreateCM|T"...
0x18004b202  mov     edx, 93009h
0x18004b207  mov     rcx, cs:?_bidSrcFile2A@?1??CoCreateCM@?$NewCM@VCDSLWrapper@@@@SAJPEAUIUnknown@@KAEBU_GUID@@PEAPEAX@Z@4REBDEB; char const * const `NewCM<CDSLWrapper>::CoCreateCM(IUnknown *,ulong,_GUID const &,void * *)'::`2'::_bidSrcFile2A
0x18004b20e  call    _bidTraceHR
0x18004b213  mov     ebx, eax
0x18004b215  mov     [rsp+48h+var_20], ebx
0x18004b219  lea     rdx, _TI1J; pThrowInfo
0x18004b220  lea     rcx, [rsp+48h+var_20]; pExceptionObject
0x18004b225  call    _CxxThrowException_0
0x18004b22b  mov     ebx, [rsp+48h+arg_8]
0x18004b22f  test    byte ptr cs:_bidGblFlags, 2
0x18004b236  jz      short loc_18004B255
0x18004b238  mov     r9d, ebx
0x18004b23b  lea     r8, aNewcmClassCdsl_1; "<NewCM<class CDSLWrapper>::CoCreateCM|T"...
0x18004b242  mov     edx, 9BC09h
0x18004b247  mov     rcx, cs:?_bidSrcFile2A@?1??CoCreateCM@?$NewCM@VCDSLWrapper@@@@SAJPEAUIUnknown@@KAEBU_GUID@@PEAPEAX@Z@4REBDEB; char const * const `NewCM<CDSLWrapper>::CoCreateCM(IUnknown *,ulong,_GUID const &,void * *)'::`2'::_bidSrcFile2A
0x18004b24e  call    _bidTraceHR
0x18004b253  mov     ebx, eax
0x18004b255  mov     eax, ebx
0x18004b257  mov     rbx, [rsp+48h+arg_18]
0x18004b25c  add     rsp, 30h
0x18004b260  pop     r14
0x18004b262  pop     rdi
0x18004b263  pop     rsi
0x18004b264  retn
```
