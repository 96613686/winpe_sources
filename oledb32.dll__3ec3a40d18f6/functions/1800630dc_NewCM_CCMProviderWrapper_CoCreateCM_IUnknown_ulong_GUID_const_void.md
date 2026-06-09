# NewCM<CCMProviderWrapper>::CoCreateCM(IUnknown *,ulong,_GUID const &,void * *)

- ea: `0x1800630dc`
- end: `0x180063379`
- name: `?CoCreateCM@?$NewCM@VCCMProviderWrapper@@@@SAJPEAUIUnknown@@KAEBU_GUID@@PEAPEAX@Z`
- size: `669`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001d6d8`

## callees

- `0x180013870`
- `0x180026620`
- `0x180029560`
- `0x18002b0c0`
- `0x18002ec0c`
- `0x18003c44c`
- `0x18003c8ac`
- `0x1800630dc`
- `0x180087010`

## import_xrefs

- `MSDART!MpHeapAlloc` at `0x18006312a`
- `MSDART!MpHeapAlloc` at `0x18006312a`

## string_xrefs

- `0x1800631cc`: `<NewCM<class CCMProviderWrapper>::CoCreateCM|OLEDB|ERR> `
- `0x1800631ea`: `<NewCM<class CCMProviderWrapper>::CoCreateCM|OLEDB|ERR> `
- `0x180063282`: `<NewCM<class CCMProviderWrapper>::CoCreateCM|OLEDB|ERR> `
- `0x1800632f4`: `<NewCM<class CCMProviderWrapper>::CoCreateCM|OLEDB|ERR> `
- `0x180063205`: `<NewCM<class CCMProviderWrapper>::CoCreateCM|Trace|HR> `
- `0x18006329d`: `<NewCM<class CCMProviderWrapper>::CoCreateCM|Trace|HR> `
- `0x18006330f`: `<NewCM<class CCMProviderWrapper>::CoCreateCM|Trace|HR> `
- `0x18006334f`: `<NewCM<class CCMProviderWrapper>::CoCreateCM|Trace|HR> `

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall NewCM<CCMProviderWrapper>::CoCreateCM(__int64 a1, __int64 a2, __int64 a3, _QWORD *a4)
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
      OLEDBTraceErr(-2147024882, L"<NewCM<class CCMProviderWrapper>::CoCreateCM|OLEDB|ERR> ", 0x24Cu);
      if ( (bidGblFlags & 2) != 0 )
        v10 = bidTraceHR(
                `NewCM<CCMProviderWrapper>::CoCreateCM'::`2'::_bidSrcFile2A[0],
                602121,
                L"<NewCM<class CCMProviderWrapper>::CoCreateCM|Trace|HR> ",
                2147942414LL);
    }
    v13 = v10;
    throw (long *)&v13;
  }
  *(_DWORD *)(v6 + 8) = 0;
  *(_QWORD *)v6 = &ATL::CComPolyObject<CCMProviderWrapper>::`vftable';
  CAcm::CAcm((CAcm *)(v6 + 24));
  *(_QWORD *)(v7 + 24) = &ATL::CComContainedObject<CDSLWrapper>::`vftable'{for `IService'};
  *(_QWORD *)(v7 + 32) = &ATL::CComContainedObject<CMRCM>::`vftable'{for `IOuterUnknown'};
  *(_QWORD *)(v7 + 40) = v7;
  _InterlockedIncrement(&dword_1800BE368);
  *(_QWORD *)v7 = &CACMComPolyObject<CCMProviderWrapper>::`vftable';
  *(_QWORD *)(v7 + 192) = v7;
  ATL::SafeIncrementReferenceMultiThread((volatile int *)(v7 + 8));
  v8 = CAcm::FinalConstruct((CAcm *)(v7 + 24));
  ATL::SafeDecrementReferenceMultiThread((volatile int *)(v7 + 8));
  if ( v8 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      OLEDBTraceErr(v8, L"<NewCM<class CCMProviderWrapper>::CoCreateCM|OLEDB|ERR> ", 0x250u);
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(v8, L"<NewCM<class CCMProviderWrapper>::CoCreateCM|OLEDB|ERR> ", 0x250u);
        if ( (bidGblFlags & 2) != 0 )
          v8 = bidTraceHR(
                 `NewCM<CCMProviderWrapper>::CoCreateCM'::`2'::_bidSrcFile2A[0],
                 606217,
                 L"<NewCM<class CCMProviderWrapper>::CoCreateCM|Trace|HR> ",
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
      OLEDBTraceErr(v9, L"<NewCM<class CCMProviderWrapper>::CoCreateCM|OLEDB|ERR> ", 0x259u);
      if ( (bidGblFlags & 2) != 0 )
        v9 = bidTraceHR(
               `NewCM<CCMProviderWrapper>::CoCreateCM'::`2'::_bidSrcFile2A[0],
               615433,
               L"<NewCM<class CCMProviderWrapper>::CoCreateCM|Trace|HR> ",
               v9);
    }
    v12 = v9;
    throw (long *)&v12;
  }
  *a4 = v14;
  if ( (bidGblFlags & 2) != 0 )
    return (unsigned int)bidTraceHR(
                           `NewCM<CCMProviderWrapper>::CoCreateCM'::`2'::_bidSrcFile2A[0],
                           637961,
                           L"<NewCM<class CCMProviderWrapper>::CoCreateCM|Trace|HR> ",
                           v9);
  return v9;
}

```

## disassembly

```asm
0x1800630dc  mov     rax, rsp
0x1800630df  mov     [rax+20h], rbx
0x1800630e3  mov     [rax+18h], r8
0x1800630e7  mov     [rax+10h], edx
0x1800630ea  mov     [rax+8], rcx
0x1800630ee  push    rsi
0x1800630ef  push    rdi
0x1800630f0  push    r14
0x1800630f2  sub     rsp, 30h
0x1800630f6  mov     r14, r9
0x1800630f9  test    r9, r9
0x1800630fc  jnz     short loc_180063108
0x1800630fe  mov     eax, 80004003h
0x180063103  jmp     loc_18006336B
0x180063108  mov     qword ptr [r9], 0
0x18006310f  mov     [rsp+48h+arg_10], 0
0x180063118  mov     edx, 1300000h
0x18006311d  mov     r8d, 0D0h
0x180063123  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x18006312a  call    cs:__imp_MpHeapAlloc
0x180063130  mov     rdi, rax
0x180063133  mov     [rsp+48h+arg_0], rax
0x180063138  test    rax, rax
0x18006313b  jz      loc_1800632D6
0x180063141  mov     dword ptr [rax+8], 0
0x180063148  lea     rax, ??_7?$CComPolyObject@VCCMProviderWrapper@@@ATL@@6B@; const ATL::CComPolyObject<CCMProviderWrapper>::`vftable'
0x18006314f  mov     [rdi], rax
0x180063152  lea     rcx, [rdi+18h]; this
0x180063156  call    ??0CAcm@@QEAA@XZ; CAcm::CAcm(void)
0x18006315b  lea     rax, ??_7?$CComContainedObject@VCDSLWrapper@@@ATL@@6BIService@@@; const ATL::CComContainedObject<CDSLWrapper>::`vftable'{for `IService'}
0x180063162  mov     [rdi+18h], rax
0x180063166  lea     rax, ??_7?$CComContainedObject@VCMRCM@@@ATL@@6BIOuterUnknown@@@; const ATL::CComContainedObject<CMRCM>::`vftable'{for `IOuterUnknown'}
0x18006316d  mov     [rdi+20h], rax
0x180063171  mov     [rdi+28h], rdi
0x180063175  lock inc cs:dword_1800BE368
0x18006317c  lea     rax, ??_7?$CACMComPolyObject@VCCMProviderWrapper@@@@6B@; const CACMComPolyObject<CCMProviderWrapper>::`vftable'
0x180063183  mov     [rdi], rax
0x180063186  mov     [rdi+0C0h], rdi
0x18006318d  mov     [rsp+48h+arg_0], rdi
0x180063192  test    rdi, rdi
0x180063195  jz      loc_1800632DF
0x18006319b  lea     rcx, [rdi+8]; volatile int *
0x18006319f  call    ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
0x1800631a4  lea     rcx, [rdi+18h]; this
0x1800631a8  call    ?FinalConstruct@CAcm@@QEAAJXZ; CAcm::FinalConstruct(void)
0x1800631ad  mov     esi, eax
0x1800631af  lea     rcx, [rdi+8]; volatile int *
0x1800631b3  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x1800631b8  test    esi, esi
0x1800631ba  jns     short loc_180063234
0x1800631bc  mov     eax, cs:_bidGblFlags
0x1800631c2  test    al, 2
0x1800631c4  jz      short loc_18006321F
0x1800631c6  mov     r8d, 250h; unsigned int
0x1800631cc  lea     rdx, aNewcmClassCcmp_1; "<NewCM<class CCMProviderWrapper>::CoCre"...
0x1800631d3  mov     ecx, esi; int
0x1800631d5  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x1800631da  mov     eax, cs:_bidGblFlags
0x1800631e0  test    al, 2
0x1800631e2  jz      short loc_18006321F
0x1800631e4  mov     r8d, 250h; unsigned int
0x1800631ea  lea     rdx, aNewcmClassCcmp_1; "<NewCM<class CCMProviderWrapper>::CoCre"...
0x1800631f1  mov     ecx, esi; int
0x1800631f3  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x1800631f8  mov     eax, cs:_bidGblFlags
0x1800631fe  test    al, 2
0x180063200  jz      short loc_18006321F
0x180063202  mov     r9d, esi
0x180063205  lea     r8, aNewcmClassCcmp_0; "<NewCM<class CCMProviderWrapper>::CoCre"...
0x18006320c  mov     edx, 94009h
0x180063211  mov     rcx, cs:?_bidSrcFile2A@?1??CoCreateCM@?$NewCM@VCCMProviderWrapper@@@@SAJPEAUIUnknown@@KAEBU_GUID@@PEAPEAX@Z@4REBDEB; char const * const `NewCM<CCMProviderWrapper>::CoCreateCM(IUnknown *,ulong,_GUID const &,void * *)'::`2'::_bidSrcFile2A
0x180063218  call    _bidTraceHR
0x18006321d  mov     esi, eax
0x18006321f  mov     [rsp+48h+pExceptionObject], esi
0x180063223  lea     rdx, _TI1J; pThrowInfo
0x18006322a  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18006322f  call    _CxxThrowException_0
0x180063234  mov     rax, [rdi]
0x180063237  mov     rcx, rdi
0x18006323a  mov     rax, [rax+8]
0x18006323e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063243  mov     rax, [rdi]
0x180063246  lea     r8, [rsp+48h+arg_10]
0x18006324b  lea     rdx, IID_IOuterUnknown
0x180063252  mov     rcx, rdi
0x180063255  mov     rax, [rax]
0x180063258  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006325d  mov     ebx, eax
0x18006325f  mov     rax, [rdi]
0x180063262  mov     rax, [rax+10h]
0x180063266  mov     rcx, rdi
0x180063269  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006326e  test    ebx, ebx
0x180063270  jns     short loc_1800632CC
0x180063272  mov     eax, cs:_bidGblFlags
0x180063278  test    al, 2
0x18006327a  jz      short loc_1800632B7
0x18006327c  mov     r8d, 259h; unsigned int
0x180063282  lea     rdx, aNewcmClassCcmp_1; "<NewCM<class CCMProviderWrapper>::CoCre"...
0x180063289  mov     ecx, ebx; int
0x18006328b  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180063290  mov     eax, cs:_bidGblFlags
0x180063296  test    al, 2
0x180063298  jz      short loc_1800632B7
0x18006329a  mov     r9d, ebx
0x18006329d  lea     r8, aNewcmClassCcmp_0; "<NewCM<class CCMProviderWrapper>::CoCre"...
0x1800632a4  mov     edx, 96409h
0x1800632a9  mov     rcx, cs:?_bidSrcFile2A@?1??CoCreateCM@?$NewCM@VCCMProviderWrapper@@@@SAJPEAUIUnknown@@KAEBU_GUID@@PEAPEAX@Z@4REBDEB; char const * const `NewCM<CCMProviderWrapper>::CoCreateCM(IUnknown *,ulong,_GUID const &,void * *)'::`2'::_bidSrcFile2A
0x1800632b0  call    _bidTraceHR
0x1800632b5  mov     ebx, eax
0x1800632b7  mov     [rsp+48h+var_24], ebx
0x1800632bb  lea     rdx, _TI1J; pThrowInfo
0x1800632c2  lea     rcx, [rsp+48h+var_24]; pExceptionObject
0x1800632c7  call    _CxxThrowException_0
0x1800632cc  mov     rax, [rsp+48h+arg_10]
0x1800632d1  mov     [r14], rax
0x1800632d4  jmp     short loc_180063343
0x1800632d6  mov     [rsp+48h+arg_0], 0
0x1800632df  mov     eax, cs:_bidGblFlags
0x1800632e5  mov     ebx, 8007000Eh
0x1800632ea  test    al, 2
0x1800632ec  jz      short loc_180063329
0x1800632ee  mov     r8d, 24Ch; unsigned int
0x1800632f4  lea     rdx, aNewcmClassCcmp_1; "<NewCM<class CCMProviderWrapper>::CoCre"...
0x1800632fb  mov     ecx, ebx; int
0x1800632fd  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180063302  mov     eax, cs:_bidGblFlags
0x180063308  test    al, 2
0x18006330a  jz      short loc_180063329
0x18006330c  mov     r9d, ebx
0x18006330f  lea     r8, aNewcmClassCcmp_0; "<NewCM<class CCMProviderWrapper>::CoCre"...
0x180063316  mov     edx, 93009h
0x18006331b  mov     rcx, cs:?_bidSrcFile2A@?1??CoCreateCM@?$NewCM@VCCMProviderWrapper@@@@SAJPEAUIUnknown@@KAEBU_GUID@@PEAPEAX@Z@4REBDEB; char const * const `NewCM<CCMProviderWrapper>::CoCreateCM(IUnknown *,ulong,_GUID const &,void * *)'::`2'::_bidSrcFile2A
0x180063322  call    _bidTraceHR
0x180063327  mov     ebx, eax
0x180063329  mov     [rsp+48h+var_20], ebx
0x18006332d  lea     rdx, _TI1J; pThrowInfo
0x180063334  lea     rcx, [rsp+48h+var_20]; pExceptionObject
0x180063339  call    _CxxThrowException_0
0x18006333f  mov     ebx, [rsp+48h+arg_8]
0x180063343  test    byte ptr cs:_bidGblFlags, 2
0x18006334a  jz      short loc_180063369
0x18006334c  mov     r9d, ebx
0x18006334f  lea     r8, aNewcmClassCcmp_0; "<NewCM<class CCMProviderWrapper>::CoCre"...
0x180063356  mov     edx, 9BC09h
0x18006335b  mov     rcx, cs:?_bidSrcFile2A@?1??CoCreateCM@?$NewCM@VCCMProviderWrapper@@@@SAJPEAUIUnknown@@KAEBU_GUID@@PEAPEAX@Z@4REBDEB; char const * const `NewCM<CCMProviderWrapper>::CoCreateCM(IUnknown *,ulong,_GUID const &,void * *)'::`2'::_bidSrcFile2A
0x180063362  call    _bidTraceHR
0x180063367  mov     ebx, eax
0x180063369  mov     eax, ebx
0x18006336b  mov     rbx, [rsp+48h+arg_18]
0x180063370  add     rsp, 30h
0x180063374  pop     r14
0x180063376  pop     rdi
0x180063377  pop     rsi
0x180063378  retn
```
