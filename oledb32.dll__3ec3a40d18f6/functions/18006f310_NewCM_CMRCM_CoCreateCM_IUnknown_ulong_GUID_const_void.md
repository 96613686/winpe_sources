# NewCM<CMRCM>::CoCreateCM(IUnknown *,ulong,_GUID const &,void * *)

- ea: `0x18006f310`
- end: `0x18006f54d`
- name: `?CoCreateCM@?$NewCM@VCMRCM@@@@SAJPEAUIUnknown@@KAEBU_GUID@@PEAPEAX@Z`
- size: `573`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18002aba4`

## callees

- `0x180013870`
- `0x180029560`
- `0x18002ec0c`
- `0x18002fad0`
- `0x1800375ac`
- `0x18006f310`
- `0x180087010`

## import_xrefs

- `MSDART!MpHeapAlloc` at `0x18006f359`
- `MSDART!MpHeapAlloc` at `0x18006f359`

## string_xrefs

- `0x18006f3a6`: `<NewCM<class CMRCM>::CoCreateCM|OLEDB|ERR> `
- `0x18006f3c4`: `<NewCM<class CMRCM>::CoCreateCM|OLEDB|ERR> `
- `0x18006f45c`: `<NewCM<class CMRCM>::CoCreateCM|OLEDB|ERR> `
- `0x18006f4ce`: `<NewCM<class CMRCM>::CoCreateCM|OLEDB|ERR> `
- `0x18006f3df`: `<NewCM<class CMRCM>::CoCreateCM|Trace|HR> `
- `0x18006f477`: `<NewCM<class CMRCM>::CoCreateCM|Trace|HR> `
- `0x18006f4e9`: `<NewCM<class CMRCM>::CoCreateCM|Trace|HR> `
- `0x18006f529`: `<NewCM<class CMRCM>::CoCreateCM|Trace|HR> `

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall NewCM<CMRCM>::CoCreateCM(__int64 a1, __int64 a2, __int64 a3, _QWORD *a4)
{
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rdi
  int v9; // ebx
  unsigned int v10; // ebx
  int v11; // ebx
  int pExceptionObject; // [rsp+20h] [rbp-28h] BYREF
  unsigned int v13; // [rsp+24h] [rbp-24h] BYREF
  int v14; // [rsp+28h] [rbp-20h] BYREF
  __int64 v15; // [rsp+60h] [rbp+18h] BYREF

  v15 = a3;
  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  v15 = 0;
  v6 = MpHeapAlloc(g_hHeapHandle, 19922944, 384);
  if ( !v6 || (v7 = CACMComPolyObject<CMRCM>::CACMComPolyObject<CMRCM>(v6, 0), (v8 = v7) == 0) )
  {
    v11 = -2147024882;
    if ( (bidGblFlags & 2) != 0 )
    {
      OLEDBTraceErr(-2147024882, L"<NewCM<class CMRCM>::CoCreateCM|OLEDB|ERR> ", 0x24Cu);
      if ( (bidGblFlags & 2) != 0 )
        v11 = bidTraceHR(
                `NewCM<CMRCM>::CoCreateCM'::`2'::_bidSrcFile2A[0],
                602121,
                L"<NewCM<class CMRCM>::CoCreateCM|Trace|HR> ",
                2147942414LL);
    }
    v14 = v11;
    throw (long *)&v14;
  }
  v9 = ATL::CComPolyObject<CMRCM>::FinalConstruct(v7);
  if ( v9 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      OLEDBTraceErr(v9, L"<NewCM<class CMRCM>::CoCreateCM|OLEDB|ERR> ", 0x250u);
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(v9, L"<NewCM<class CMRCM>::CoCreateCM|OLEDB|ERR> ", 0x250u);
        if ( (bidGblFlags & 2) != 0 )
          v9 = bidTraceHR(
                 `NewCM<CMRCM>::CoCreateCM'::`2'::_bidSrcFile2A[0],
                 606217,
                 L"<NewCM<class CMRCM>::CoCreateCM|Trace|HR> ",
                 (unsigned int)v9);
      }
    }
    pExceptionObject = v9;
    throw (long *)&pExceptionObject;
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
  v10 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v8)(v8, &IID_IUnknown, &v15);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  if ( (v10 & 0x80000000) != 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      OLEDBTraceErr(v10, L"<NewCM<class CMRCM>::CoCreateCM|OLEDB|ERR> ", 0x259u);
      if ( (bidGblFlags & 2) != 0 )
        v10 = bidTraceHR(
                `NewCM<CMRCM>::CoCreateCM'::`2'::_bidSrcFile2A[0],
                615433,
                L"<NewCM<class CMRCM>::CoCreateCM|Trace|HR> ",
                v10);
    }
    v13 = v10;
    throw (long *)&v13;
  }
  *a4 = v15;
  if ( (bidGblFlags & 2) != 0 )
    return (unsigned int)bidTraceHR(
                           `NewCM<CMRCM>::CoCreateCM'::`2'::_bidSrcFile2A[0],
                           637961,
                           L"<NewCM<class CMRCM>::CoCreateCM|Trace|HR> ",
                           v10);
  return v10;
}

```

## disassembly

```asm
0x18006f310  mov     [rsp+arg_10], r8
0x18006f315  mov     [rsp+arg_8], edx
0x18006f319  mov     [rsp+arg_0], rcx
0x18006f31e  push    rbx
0x18006f31f  push    rsi
0x18006f320  push    rdi
0x18006f321  sub     rsp, 30h
0x18006f325  mov     rsi, r9
0x18006f328  test    r9, r9
0x18006f32b  jnz     short loc_18006F337
0x18006f32d  mov     eax, 80004003h
0x18006f332  jmp     loc_18006F545
0x18006f337  mov     qword ptr [r9], 0
0x18006f33e  mov     [rsp+48h+arg_10], 0
0x18006f347  mov     edx, 1300000h
0x18006f34c  mov     r8d, 180h
0x18006f352  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x18006f359  call    cs:__imp_MpHeapAlloc
0x18006f35f  mov     [rsp+48h+arg_0], rax
0x18006f364  test    rax, rax
0x18006f367  jz      loc_18006F4B0
0x18006f36d  xor     edx, edx
0x18006f36f  mov     rcx, rax
0x18006f372  call    ??0?$CACMComPolyObject@VCMRCM@@@@QEAA@PEAX@Z; CACMComPolyObject<CMRCM>::CACMComPolyObject<CMRCM>(void *)
0x18006f377  mov     rdi, rax
0x18006f37a  mov     [rsp+48h+arg_0], rax
0x18006f37f  test    rax, rax
0x18006f382  jz      loc_18006F4B9
0x18006f388  mov     rcx, rax
0x18006f38b  call    ?FinalConstruct@?$CComPolyObject@VCMRCM@@@ATL@@QEAAJXZ; ATL::CComPolyObject<CMRCM>::FinalConstruct(void)
0x18006f390  mov     ebx, eax
0x18006f392  test    eax, eax
0x18006f394  jns     short loc_18006F40E
0x18006f396  mov     eax, cs:_bidGblFlags
0x18006f39c  test    al, 2
0x18006f39e  jz      short loc_18006F3F9
0x18006f3a0  mov     r8d, 250h; unsigned int
0x18006f3a6  lea     rdx, aNewcmClassCmrc_1; "<NewCM<class CMRCM>::CoCreateCM|OLEDB|E"...
0x18006f3ad  mov     ecx, ebx; int
0x18006f3af  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18006f3b4  mov     eax, cs:_bidGblFlags
0x18006f3ba  test    al, 2
0x18006f3bc  jz      short loc_18006F3F9
0x18006f3be  mov     r8d, 250h; unsigned int
0x18006f3c4  lea     rdx, aNewcmClassCmrc_1; "<NewCM<class CMRCM>::CoCreateCM|OLEDB|E"...
0x18006f3cb  mov     ecx, ebx; int
0x18006f3cd  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18006f3d2  mov     eax, cs:_bidGblFlags
0x18006f3d8  test    al, 2
0x18006f3da  jz      short loc_18006F3F9
0x18006f3dc  mov     r9d, ebx
0x18006f3df  lea     r8, aNewcmClassCmrc_0; "<NewCM<class CMRCM>::CoCreateCM|Trace|H"...
0x18006f3e6  mov     edx, 94009h
0x18006f3eb  mov     rcx, cs:?_bidSrcFile2A@?1??CoCreateCM@?$NewCM@VCMRCM@@@@SAJPEAUIUnknown@@KAEBU_GUID@@PEAPEAX@Z@4REBDEB; char const * const `NewCM<CMRCM>::CoCreateCM(IUnknown *,ulong,_GUID const &,void * *)'::`2'::_bidSrcFile2A
0x18006f3f2  call    _bidTraceHR
0x18006f3f7  mov     ebx, eax
0x18006f3f9  mov     [rsp+48h+pExceptionObject], ebx
0x18006f3fd  lea     rdx, _TI1J; pThrowInfo
0x18006f404  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18006f409  call    _CxxThrowException_0
0x18006f40e  mov     rax, [rdi]
0x18006f411  mov     rcx, rdi
0x18006f414  mov     rax, [rax+8]
0x18006f418  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f41d  mov     rax, [rdi]
0x18006f420  lea     r8, [rsp+48h+arg_10]
0x18006f425  lea     rdx, IID_IUnknown
0x18006f42c  mov     rcx, rdi
0x18006f42f  mov     rax, [rax]
0x18006f432  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f437  mov     ebx, eax
0x18006f439  mov     rax, [rdi]
0x18006f43c  mov     rax, [rax+10h]
0x18006f440  mov     rcx, rdi
0x18006f443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f448  test    ebx, ebx
0x18006f44a  jns     short loc_18006F4A6
0x18006f44c  mov     eax, cs:_bidGblFlags
0x18006f452  test    al, 2
0x18006f454  jz      short loc_18006F491
0x18006f456  mov     r8d, 259h; unsigned int
0x18006f45c  lea     rdx, aNewcmClassCmrc_1; "<NewCM<class CMRCM>::CoCreateCM|OLEDB|E"...
0x18006f463  mov     ecx, ebx; int
0x18006f465  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18006f46a  mov     eax, cs:_bidGblFlags
0x18006f470  test    al, 2
0x18006f472  jz      short loc_18006F491
0x18006f474  mov     r9d, ebx
0x18006f477  lea     r8, aNewcmClassCmrc_0; "<NewCM<class CMRCM>::CoCreateCM|Trace|H"...
0x18006f47e  mov     edx, 96409h
0x18006f483  mov     rcx, cs:?_bidSrcFile2A@?1??CoCreateCM@?$NewCM@VCMRCM@@@@SAJPEAUIUnknown@@KAEBU_GUID@@PEAPEAX@Z@4REBDEB; char const * const `NewCM<CMRCM>::CoCreateCM(IUnknown *,ulong,_GUID const &,void * *)'::`2'::_bidSrcFile2A
0x18006f48a  call    _bidTraceHR
0x18006f48f  mov     ebx, eax
0x18006f491  mov     [rsp+48h+var_24], ebx
0x18006f495  lea     rdx, _TI1J; pThrowInfo
0x18006f49c  lea     rcx, [rsp+48h+var_24]; pExceptionObject
0x18006f4a1  call    _CxxThrowException_0
0x18006f4a6  mov     rax, [rsp+48h+arg_10]
0x18006f4ab  mov     [rsi], rax
0x18006f4ae  jmp     short loc_18006F51D
0x18006f4b0  mov     [rsp+48h+arg_0], 0
0x18006f4b9  mov     eax, cs:_bidGblFlags
0x18006f4bf  mov     ebx, 8007000Eh
0x18006f4c4  test    al, 2
0x18006f4c6  jz      short loc_18006F503
0x18006f4c8  mov     r8d, 24Ch; unsigned int
0x18006f4ce  lea     rdx, aNewcmClassCmrc_1; "<NewCM<class CMRCM>::CoCreateCM|OLEDB|E"...
0x18006f4d5  mov     ecx, ebx; int
0x18006f4d7  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18006f4dc  mov     eax, cs:_bidGblFlags
0x18006f4e2  test    al, 2
0x18006f4e4  jz      short loc_18006F503
0x18006f4e6  mov     r9d, ebx
0x18006f4e9  lea     r8, aNewcmClassCmrc_0; "<NewCM<class CMRCM>::CoCreateCM|Trace|H"...
0x18006f4f0  mov     edx, 93009h
0x18006f4f5  mov     rcx, cs:?_bidSrcFile2A@?1??CoCreateCM@?$NewCM@VCMRCM@@@@SAJPEAUIUnknown@@KAEBU_GUID@@PEAPEAX@Z@4REBDEB; char const * const `NewCM<CMRCM>::CoCreateCM(IUnknown *,ulong,_GUID const &,void * *)'::`2'::_bidSrcFile2A
0x18006f4fc  call    _bidTraceHR
0x18006f501  mov     ebx, eax
0x18006f503  mov     [rsp+48h+var_20], ebx
0x18006f507  lea     rdx, _TI1J; pThrowInfo
0x18006f50e  lea     rcx, [rsp+48h+var_20]; pExceptionObject
0x18006f513  call    _CxxThrowException_0
0x18006f519  mov     ebx, [rsp+48h+arg_8]
0x18006f51d  test    byte ptr cs:_bidGblFlags, 2
0x18006f524  jz      short loc_18006F543
0x18006f526  mov     r9d, ebx
0x18006f529  lea     r8, aNewcmClassCmrc_0; "<NewCM<class CMRCM>::CoCreateCM|Trace|H"...
0x18006f530  mov     edx, 9BC09h
0x18006f535  mov     rcx, cs:?_bidSrcFile2A@?1??CoCreateCM@?$NewCM@VCMRCM@@@@SAJPEAUIUnknown@@KAEBU_GUID@@PEAPEAX@Z@4REBDEB; char const * const `NewCM<CMRCM>::CoCreateCM(IUnknown *,ulong,_GUID const &,void * *)'::`2'::_bidSrcFile2A
0x18006f53c  call    _bidTraceHR
0x18006f541  mov     ebx, eax
0x18006f543  mov     eax, ebx
0x18006f545  add     rsp, 30h
0x18006f549  pop     rdi
0x18006f54a  pop     rsi
0x18006f54b  pop     rbx
0x18006f54c  retn
```
