# NewCM<CACMAggregationWrapper>::CoCreateCM(IUnknown *,ulong,_GUID const &,void * *)

- ea: `0x18003c608`
- end: `0x18003c8a5`
- name: `?CoCreateCM@?$NewCM@VCACMAggregationWrapper@@@@SAJPEAUIUnknown@@KAEBU_GUID@@PEAPEAX@Z`
- size: `669`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003ca20`

## callees

- `0x180013870`
- `0x180026620`
- `0x180029560`
- `0x18002b0c0`
- `0x18002ec0c`
- `0x18003c44c`
- `0x18003c608`
- `0x18003c8ac`
- `0x180087010`

## import_xrefs

- `MSDART!MpHeapAlloc` at `0x18003c656`
- `MSDART!MpHeapAlloc` at `0x18003c656`

## string_xrefs

- `0x18003c6f8`: `<NewCM<class CACMAggregationWrapper>::CoCreateCM|OLEDB|ERR> `
- `0x18003c716`: `<NewCM<class CACMAggregationWrapper>::CoCreateCM|OLEDB|ERR> `
- `0x18003c7ae`: `<NewCM<class CACMAggregationWrapper>::CoCreateCM|OLEDB|ERR> `
- `0x18003c820`: `<NewCM<class CACMAggregationWrapper>::CoCreateCM|OLEDB|ERR> `
- `0x18003c731`: `<NewCM<class CACMAggregationWrapper>::CoCreateCM|Trace|HR> `
- `0x18003c7c9`: `<NewCM<class CACMAggregationWrapper>::CoCreateCM|Trace|HR> `
- `0x18003c83b`: `<NewCM<class CACMAggregationWrapper>::CoCreateCM|Trace|HR> `
- `0x18003c87b`: `<NewCM<class CACMAggregationWrapper>::CoCreateCM|Trace|HR> `

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall NewCM<CACMAggregationWrapper>::CoCreateCM(__int64 a1, __int64 a2, __int64 a3, _QWORD *a4)
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
      OLEDBTraceErr(-2147024882, L"<NewCM<class CACMAggregationWrapper>::CoCreateCM|OLEDB|ERR> ", 0x24Cu);
      if ( (bidGblFlags & 2) != 0 )
        v10 = bidTraceHR(
                `NewCM<CACMAggregationWrapper>::CoCreateCM'::`2'::_bidSrcFile2A[0],
                602121,
                L"<NewCM<class CACMAggregationWrapper>::CoCreateCM|Trace|HR> ",
                2147942414LL);
    }
    v13 = v10;
    throw (long *)&v13;
  }
  *(_DWORD *)(v6 + 8) = 0;
  *(_QWORD *)v6 = &ATL::CComPolyObject<CACMAggregationWrapper>::`vftable';
  CAcm::CAcm((CAcm *)(v6 + 24));
  *(_QWORD *)(v7 + 24) = &ATL::CComContainedObject<CDSLWrapper>::`vftable'{for `IService'};
  *(_QWORD *)(v7 + 32) = &ATL::CComContainedObject<CMRCM>::`vftable'{for `IOuterUnknown'};
  *(_QWORD *)(v7 + 40) = v7;
  _InterlockedIncrement(&dword_1800BE368);
  *(_QWORD *)v7 = &CACMComPolyObject<CACMAggregationWrapper>::`vftable';
  *(_QWORD *)(v7 + 192) = v7;
  ATL::SafeIncrementReferenceMultiThread((volatile int *)(v7 + 8));
  v8 = CAcm::FinalConstruct((CAcm *)(v7 + 24));
  ATL::SafeDecrementReferenceMultiThread((volatile int *)(v7 + 8));
  if ( v8 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      OLEDBTraceErr(v8, L"<NewCM<class CACMAggregationWrapper>::CoCreateCM|OLEDB|ERR> ", 0x250u);
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(v8, L"<NewCM<class CACMAggregationWrapper>::CoCreateCM|OLEDB|ERR> ", 0x250u);
        if ( (bidGblFlags & 2) != 0 )
          v8 = bidTraceHR(
                 `NewCM<CACMAggregationWrapper>::CoCreateCM'::`2'::_bidSrcFile2A[0],
                 606217,
                 L"<NewCM<class CACMAggregationWrapper>::CoCreateCM|Trace|HR> ",
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
      OLEDBTraceErr(v9, L"<NewCM<class CACMAggregationWrapper>::CoCreateCM|OLEDB|ERR> ", 0x259u);
      if ( (bidGblFlags & 2) != 0 )
        v9 = bidTraceHR(
               `NewCM<CACMAggregationWrapper>::CoCreateCM'::`2'::_bidSrcFile2A[0],
               615433,
               L"<NewCM<class CACMAggregationWrapper>::CoCreateCM|Trace|HR> ",
               v9);
    }
    v12 = v9;
    throw (long *)&v12;
  }
  *a4 = v14;
  if ( (bidGblFlags & 2) != 0 )
    return (unsigned int)bidTraceHR(
                           `NewCM<CACMAggregationWrapper>::CoCreateCM'::`2'::_bidSrcFile2A[0],
                           637961,
                           L"<NewCM<class CACMAggregationWrapper>::CoCreateCM|Trace|HR> ",
                           v9);
  return v9;
}

```

## disassembly

```asm
0x18003c608  mov     rax, rsp
0x18003c60b  mov     [rax+20h], rbx
0x18003c60f  mov     [rax+18h], r8
0x18003c613  mov     [rax+10h], edx
0x18003c616  mov     [rax+8], rcx
0x18003c61a  push    rsi
0x18003c61b  push    rdi
0x18003c61c  push    r14
0x18003c61e  sub     rsp, 30h
0x18003c622  mov     r14, r9
0x18003c625  test    r9, r9
0x18003c628  jnz     short loc_18003C634
0x18003c62a  mov     eax, 80004003h
0x18003c62f  jmp     loc_18003C897
0x18003c634  mov     qword ptr [r9], 0
0x18003c63b  mov     [rsp+48h+arg_10], 0
0x18003c644  mov     edx, 1300000h
0x18003c649  mov     r8d, 0D0h
0x18003c64f  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x18003c656  call    cs:__imp_MpHeapAlloc
0x18003c65c  mov     rdi, rax
0x18003c65f  mov     [rsp+48h+arg_0], rax
0x18003c664  test    rax, rax
0x18003c667  jz      loc_18003C802
0x18003c66d  mov     dword ptr [rax+8], 0
0x18003c674  lea     rax, ??_7?$CComPolyObject@VCACMAggregationWrapper@@@ATL@@6B@; const ATL::CComPolyObject<CACMAggregationWrapper>::`vftable'
0x18003c67b  mov     [rdi], rax
0x18003c67e  lea     rcx, [rdi+18h]; this
0x18003c682  call    ??0CAcm@@QEAA@XZ; CAcm::CAcm(void)
0x18003c687  lea     rax, ??_7?$CComContainedObject@VCDSLWrapper@@@ATL@@6BIService@@@; const ATL::CComContainedObject<CDSLWrapper>::`vftable'{for `IService'}
0x18003c68e  mov     [rdi+18h], rax
0x18003c692  lea     rax, ??_7?$CComContainedObject@VCMRCM@@@ATL@@6BIOuterUnknown@@@; const ATL::CComContainedObject<CMRCM>::`vftable'{for `IOuterUnknown'}
0x18003c699  mov     [rdi+20h], rax
0x18003c69d  mov     [rdi+28h], rdi
0x18003c6a1  lock inc cs:dword_1800BE368
0x18003c6a8  lea     rax, ??_7?$CACMComPolyObject@VCACMAggregationWrapper@@@@6B@; const CACMComPolyObject<CACMAggregationWrapper>::`vftable'
0x18003c6af  mov     [rdi], rax
0x18003c6b2  mov     [rdi+0C0h], rdi
0x18003c6b9  mov     [rsp+48h+arg_0], rdi
0x18003c6be  test    rdi, rdi
0x18003c6c1  jz      loc_18003C80B
0x18003c6c7  lea     rcx, [rdi+8]; volatile int *
0x18003c6cb  call    ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
0x18003c6d0  lea     rcx, [rdi+18h]; this
0x18003c6d4  call    ?FinalConstruct@CAcm@@QEAAJXZ; CAcm::FinalConstruct(void)
0x18003c6d9  mov     esi, eax
0x18003c6db  lea     rcx, [rdi+8]; volatile int *
0x18003c6df  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x18003c6e4  test    esi, esi
0x18003c6e6  jns     short loc_18003C760
0x18003c6e8  mov     eax, cs:_bidGblFlags
0x18003c6ee  test    al, 2
0x18003c6f0  jz      short loc_18003C74B
0x18003c6f2  mov     r8d, 250h; unsigned int
0x18003c6f8  lea     rdx, aNewcmClassCacm; "<NewCM<class CACMAggregationWrapper>::C"...
0x18003c6ff  mov     ecx, esi; int
0x18003c701  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18003c706  mov     eax, cs:_bidGblFlags
0x18003c70c  test    al, 2
0x18003c70e  jz      short loc_18003C74B
0x18003c710  mov     r8d, 250h; unsigned int
0x18003c716  lea     rdx, aNewcmClassCacm; "<NewCM<class CACMAggregationWrapper>::C"...
0x18003c71d  mov     ecx, esi; int
0x18003c71f  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18003c724  mov     eax, cs:_bidGblFlags
0x18003c72a  test    al, 2
0x18003c72c  jz      short loc_18003C74B
0x18003c72e  mov     r9d, esi
0x18003c731  lea     r8, aNewcmClassCacm_0; "<NewCM<class CACMAggregationWrapper>::C"...
0x18003c738  mov     edx, 94009h
0x18003c73d  mov     rcx, cs:?_bidSrcFile2A@?1??CoCreateCM@?$NewCM@VCACMAggregationWrapper@@@@SAJPEAUIUnknown@@KAEBU_GUID@@PEAPEAX@Z@4REBDEB; char const * const `NewCM<CACMAggregationWrapper>::CoCreateCM(IUnknown *,ulong,_GUID const &,void * *)'::`2'::_bidSrcFile2A
0x18003c744  call    _bidTraceHR
0x18003c749  mov     esi, eax
0x18003c74b  mov     [rsp+48h+pExceptionObject], esi
0x18003c74f  lea     rdx, _TI1J; pThrowInfo
0x18003c756  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18003c75b  call    _CxxThrowException_0
0x18003c760  mov     rax, [rdi]
0x18003c763  mov     rcx, rdi
0x18003c766  mov     rax, [rax+8]
0x18003c76a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c76f  mov     rax, [rdi]
0x18003c772  lea     r8, [rsp+48h+arg_10]
0x18003c777  lea     rdx, IID_IOuterUnknown
0x18003c77e  mov     rcx, rdi
0x18003c781  mov     rax, [rax]
0x18003c784  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c789  mov     ebx, eax
0x18003c78b  mov     rax, [rdi]
0x18003c78e  mov     rax, [rax+10h]
0x18003c792  mov     rcx, rdi
0x18003c795  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c79a  test    ebx, ebx
0x18003c79c  jns     short loc_18003C7F8
0x18003c79e  mov     eax, cs:_bidGblFlags
0x18003c7a4  test    al, 2
0x18003c7a6  jz      short loc_18003C7E3
0x18003c7a8  mov     r8d, 259h; unsigned int
0x18003c7ae  lea     rdx, aNewcmClassCacm; "<NewCM<class CACMAggregationWrapper>::C"...
0x18003c7b5  mov     ecx, ebx; int
0x18003c7b7  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18003c7bc  mov     eax, cs:_bidGblFlags
0x18003c7c2  test    al, 2
0x18003c7c4  jz      short loc_18003C7E3
0x18003c7c6  mov     r9d, ebx
0x18003c7c9  lea     r8, aNewcmClassCacm_0; "<NewCM<class CACMAggregationWrapper>::C"...
0x18003c7d0  mov     edx, 96409h
0x18003c7d5  mov     rcx, cs:?_bidSrcFile2A@?1??CoCreateCM@?$NewCM@VCACMAggregationWrapper@@@@SAJPEAUIUnknown@@KAEBU_GUID@@PEAPEAX@Z@4REBDEB; char const * const `NewCM<CACMAggregationWrapper>::CoCreateCM(IUnknown *,ulong,_GUID const &,void * *)'::`2'::_bidSrcFile2A
0x18003c7dc  call    _bidTraceHR
0x18003c7e1  mov     ebx, eax
0x18003c7e3  mov     [rsp+48h+var_24], ebx
0x18003c7e7  lea     rdx, _TI1J; pThrowInfo
0x18003c7ee  lea     rcx, [rsp+48h+var_24]; pExceptionObject
0x18003c7f3  call    _CxxThrowException_0
0x18003c7f8  mov     rax, [rsp+48h+arg_10]
0x18003c7fd  mov     [r14], rax
0x18003c800  jmp     short loc_18003C86F
0x18003c802  mov     [rsp+48h+arg_0], 0
0x18003c80b  mov     eax, cs:_bidGblFlags
0x18003c811  mov     ebx, 8007000Eh
0x18003c816  test    al, 2
0x18003c818  jz      short loc_18003C855
0x18003c81a  mov     r8d, 24Ch; unsigned int
0x18003c820  lea     rdx, aNewcmClassCacm; "<NewCM<class CACMAggregationWrapper>::C"...
0x18003c827  mov     ecx, ebx; int
0x18003c829  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18003c82e  mov     eax, cs:_bidGblFlags
0x18003c834  test    al, 2
0x18003c836  jz      short loc_18003C855
0x18003c838  mov     r9d, ebx
0x18003c83b  lea     r8, aNewcmClassCacm_0; "<NewCM<class CACMAggregationWrapper>::C"...
0x18003c842  mov     edx, 93009h
0x18003c847  mov     rcx, cs:?_bidSrcFile2A@?1??CoCreateCM@?$NewCM@VCACMAggregationWrapper@@@@SAJPEAUIUnknown@@KAEBU_GUID@@PEAPEAX@Z@4REBDEB; char const * const `NewCM<CACMAggregationWrapper>::CoCreateCM(IUnknown *,ulong,_GUID const &,void * *)'::`2'::_bidSrcFile2A
0x18003c84e  call    _bidTraceHR
0x18003c853  mov     ebx, eax
0x18003c855  mov     [rsp+48h+var_20], ebx
0x18003c859  lea     rdx, _TI1J; pThrowInfo
0x18003c860  lea     rcx, [rsp+48h+var_20]; pExceptionObject
0x18003c865  call    _CxxThrowException_0
0x18003c86b  mov     ebx, [rsp+48h+arg_8]
0x18003c86f  test    byte ptr cs:_bidGblFlags, 2
0x18003c876  jz      short loc_18003C895
0x18003c878  mov     r9d, ebx
0x18003c87b  lea     r8, aNewcmClassCacm_0; "<NewCM<class CACMAggregationWrapper>::C"...
0x18003c882  mov     edx, 9BC09h
0x18003c887  mov     rcx, cs:?_bidSrcFile2A@?1??CoCreateCM@?$NewCM@VCACMAggregationWrapper@@@@SAJPEAUIUnknown@@KAEBU_GUID@@PEAPEAX@Z@4REBDEB; char const * const `NewCM<CACMAggregationWrapper>::CoCreateCM(IUnknown *,ulong,_GUID const &,void * *)'::`2'::_bidSrcFile2A
0x18003c88e  call    _bidTraceHR
0x18003c893  mov     ebx, eax
0x18003c895  mov     eax, ebx
0x18003c897  mov     rbx, [rsp+48h+arg_18]
0x18003c89c  add     rsp, 30h
0x18003c8a0  pop     r14
0x18003c8a2  pop     rdi
0x18003c8a3  pop     rsi
0x18003c8a4  retn
```
