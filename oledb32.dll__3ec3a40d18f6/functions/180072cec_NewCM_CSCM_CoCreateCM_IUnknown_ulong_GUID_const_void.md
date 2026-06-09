# NewCM<CSCM>::CoCreateCM(IUnknown *,ulong,_GUID const &,void * *)

- ea: `0x180072cec`
- end: `0x180072f1b`
- name: `?CoCreateCM@?$NewCM@VCSCM@@@@SAJPEAUIUnknown@@KAEBU_GUID@@PEAPEAX@Z`
- size: `559`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18001c2b0`
- `0x180072f30`
- `0x18007a4e0`

## callees

- `0x180013870`
- `0x1800191a0`
- `0x18001b8c0`
- `0x180026620`
- `0x180029560`
- `0x18002ec0c`
- `0x18002ff70`
- `0x18003761c`
- `0x180072cec`

## import_xrefs

- `MSDART!MpHeapAlloc` at `0x180072d35`
- `MSDART!MpHeapAlloc` at `0x180072d35`

## string_xrefs

- `0x180072d82`: `<NewCM<class CSCM>::CoCreateCM|OLEDB|ERR> `
- `0x180072da0`: `<NewCM<class CSCM>::CoCreateCM|OLEDB|ERR> `
- `0x180072e25`: `<NewCM<class CSCM>::CoCreateCM|OLEDB|ERR> `
- `0x180072e9c`: `<NewCM<class CSCM>::CoCreateCM|OLEDB|ERR> `
- `0x180072dbb`: `<NewCM<class CSCM>::CoCreateCM|Trace|HR> `
- `0x180072e40`: `<NewCM<class CSCM>::CoCreateCM|Trace|HR> `
- `0x180072eb7`: `<NewCM<class CSCM>::CoCreateCM|Trace|HR> `
- `0x180072ef7`: `<NewCM<class CSCM>::CoCreateCM|Trace|HR> `

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall NewCM<CSCM>::CoCreateCM(__int64 a1, __int64 a2, __int64 a3, _QWORD *a4)
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
  v6 = MpHeapAlloc(g_hHeapHandle, 19922944, 512);
  if ( !v6 || (v7 = CSCMComPolyObject<CSCM>::CSCMComPolyObject<CSCM>(v6, 0), (v8 = v7) == 0) )
  {
    v11 = -2147024882;
    if ( (bidGblFlags & 2) != 0 )
    {
      OLEDBTraceErr(-2147024882, L"<NewCM<class CSCM>::CoCreateCM|OLEDB|ERR> ", 0x24Cu);
      if ( (bidGblFlags & 2) != 0 )
        v11 = bidTraceHR(
                `NewCM<CSCM>::CoCreateCM'::`2'::_bidSrcFile2A[0],
                602121,
                L"<NewCM<class CSCM>::CoCreateCM|Trace|HR> ",
                2147942414LL);
    }
    v14 = v11;
    throw (long *)&v14;
  }
  v9 = ATL::CComPolyObject<CSCM>::FinalConstruct(v7);
  if ( v9 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      OLEDBTraceErr(v9, L"<NewCM<class CSCM>::CoCreateCM|OLEDB|ERR> ", 0x250u);
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(v9, L"<NewCM<class CSCM>::CoCreateCM|OLEDB|ERR> ", 0x250u);
        if ( (bidGblFlags & 2) != 0 )
          v9 = bidTraceHR(
                 `NewCM<CSCM>::CoCreateCM'::`2'::_bidSrcFile2A[0],
                 606217,
                 L"<NewCM<class CSCM>::CoCreateCM|Trace|HR> ",
                 (unsigned int)v9);
      }
    }
    pExceptionObject = v9;
    throw (long *)&pExceptionObject;
  }
  ATL::SafeIncrementReferenceMultiThread((volatile int *)(v8 + 8));
  v10 = CACMComPolyObject<CSCM>::QueryInterface(v8, &IID_IUnknown, &v15);
  if ( (v10 & 0x80000000) != 0 )
  {
    CSCMComPolyObject<CSCM>::Release(v8);
    if ( (bidGblFlags & 2) != 0 )
    {
      OLEDBTraceErr(v10, L"<NewCM<class CSCM>::CoCreateCM|OLEDB|ERR> ", 0x259u);
      if ( (bidGblFlags & 2) != 0 )
        v10 = bidTraceHR(
                `NewCM<CSCM>::CoCreateCM'::`2'::_bidSrcFile2A[0],
                615433,
                L"<NewCM<class CSCM>::CoCreateCM|Trace|HR> ",
                v10);
    }
    v13 = v10;
    throw (long *)&v13;
  }
  CSCMComPolyObject<CSCM>::Release(v8);
  *a4 = v15;
  if ( (bidGblFlags & 2) != 0 )
    return (unsigned int)bidTraceHR(
                           `NewCM<CSCM>::CoCreateCM'::`2'::_bidSrcFile2A[0],
                           637961,
                           L"<NewCM<class CSCM>::CoCreateCM|Trace|HR> ",
                           v10);
  return v10;
}

```

## disassembly

```asm
0x180072cec  mov     [rsp+arg_10], r8
0x180072cf1  mov     [rsp+arg_8], edx
0x180072cf5  mov     [rsp+arg_0], rcx
0x180072cfa  push    rbx
0x180072cfb  push    rsi
0x180072cfc  push    rdi
0x180072cfd  sub     rsp, 30h
0x180072d01  mov     rsi, r9
0x180072d04  test    r9, r9
0x180072d07  jnz     short loc_180072D13
0x180072d09  mov     eax, 80004003h
0x180072d0e  jmp     loc_180072F13
0x180072d13  mov     qword ptr [r9], 0
0x180072d1a  mov     [rsp+48h+arg_10], 0
0x180072d23  mov     edx, 1300000h
0x180072d28  mov     r8d, 200h
0x180072d2e  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x180072d35  call    cs:__imp_MpHeapAlloc
0x180072d3b  mov     [rsp+48h+arg_0], rax
0x180072d40  test    rax, rax
0x180072d43  jz      loc_180072E7E
0x180072d49  xor     edx, edx
0x180072d4b  mov     rcx, rax
0x180072d4e  call    ??0?$CSCMComPolyObject@VCSCM@@@@QEAA@PEAX@Z; CSCMComPolyObject<CSCM>::CSCMComPolyObject<CSCM>(void *)
0x180072d53  mov     rdi, rax
0x180072d56  mov     [rsp+48h+arg_0], rax
0x180072d5b  test    rax, rax
0x180072d5e  jz      loc_180072E87
0x180072d64  mov     rcx, rax
0x180072d67  call    ?FinalConstruct@?$CComPolyObject@VCSCM@@@ATL@@QEAAJXZ; ATL::CComPolyObject<CSCM>::FinalConstruct(void)
0x180072d6c  mov     ebx, eax
0x180072d6e  test    eax, eax
0x180072d70  jns     short loc_180072DEA
0x180072d72  mov     eax, cs:_bidGblFlags
0x180072d78  test    al, 2
0x180072d7a  jz      short loc_180072DD5
0x180072d7c  mov     r8d, 250h; unsigned int
0x180072d82  lea     rdx, aNewcmClassCscm; "<NewCM<class CSCM>::CoCreateCM|OLEDB|ER"...
0x180072d89  mov     ecx, ebx; int
0x180072d8b  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180072d90  mov     eax, cs:_bidGblFlags
0x180072d96  test    al, 2
0x180072d98  jz      short loc_180072DD5
0x180072d9a  mov     r8d, 250h; unsigned int
0x180072da0  lea     rdx, aNewcmClassCscm; "<NewCM<class CSCM>::CoCreateCM|OLEDB|ER"...
0x180072da7  mov     ecx, ebx; int
0x180072da9  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180072dae  mov     eax, cs:_bidGblFlags
0x180072db4  test    al, 2
0x180072db6  jz      short loc_180072DD5
0x180072db8  mov     r9d, ebx
0x180072dbb  lea     r8, aNewcmClassCscm_0; "<NewCM<class CSCM>::CoCreateCM|Trace|HR"...
0x180072dc2  mov     edx, 94009h
0x180072dc7  mov     rcx, cs:?_bidSrcFile2A@?1??CoCreateCM@?$NewCM@VCSCM@@@@SAJPEAUIUnknown@@KAEBU_GUID@@PEAPEAX@Z@4REBDEB; char const * const `NewCM<CSCM>::CoCreateCM(IUnknown *,ulong,_GUID const &,void * *)'::`2'::_bidSrcFile2A
0x180072dce  call    _bidTraceHR
0x180072dd3  mov     ebx, eax
0x180072dd5  mov     [rsp+48h+pExceptionObject], ebx
0x180072dd9  lea     rdx, _TI1J; pThrowInfo
0x180072de0  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180072de5  call    _CxxThrowException_0
0x180072dea  lea     rcx, [rdi+8]; volatile int *
0x180072dee  call    ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
0x180072df3  lea     r8, [rsp+48h+arg_10]
0x180072df8  lea     rdx, IID_IUnknown
0x180072dff  mov     rcx, rdi
0x180072e02  call    ?QueryInterface@?$CACMComPolyObject@VCSCM@@@@UEAAJAEBU_GUID@@PEAPEAX@Z; CACMComPolyObject<CSCM>::QueryInterface(_GUID const &,void * *)
0x180072e07  mov     ebx, eax
0x180072e09  mov     rcx, rdi
0x180072e0c  test    eax, eax
0x180072e0e  jns     short loc_180072E6F
0x180072e10  call    ?Release@?$CSCMComPolyObject@VCSCM@@@@UEAAKXZ; CSCMComPolyObject<CSCM>::Release(void)
0x180072e15  mov     eax, cs:_bidGblFlags
0x180072e1b  test    al, 2
0x180072e1d  jz      short loc_180072E5A
0x180072e1f  mov     r8d, 259h; unsigned int
0x180072e25  lea     rdx, aNewcmClassCscm; "<NewCM<class CSCM>::CoCreateCM|OLEDB|ER"...
0x180072e2c  mov     ecx, ebx; int
0x180072e2e  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180072e33  mov     eax, cs:_bidGblFlags
0x180072e39  test    al, 2
0x180072e3b  jz      short loc_180072E5A
0x180072e3d  mov     r9d, ebx
0x180072e40  lea     r8, aNewcmClassCscm_0; "<NewCM<class CSCM>::CoCreateCM|Trace|HR"...
0x180072e47  mov     edx, 96409h
0x180072e4c  mov     rcx, cs:?_bidSrcFile2A@?1??CoCreateCM@?$NewCM@VCSCM@@@@SAJPEAUIUnknown@@KAEBU_GUID@@PEAPEAX@Z@4REBDEB; char const * const `NewCM<CSCM>::CoCreateCM(IUnknown *,ulong,_GUID const &,void * *)'::`2'::_bidSrcFile2A
0x180072e53  call    _bidTraceHR
0x180072e58  mov     ebx, eax
0x180072e5a  mov     [rsp+48h+var_24], ebx
0x180072e5e  lea     rdx, _TI1J; pThrowInfo
0x180072e65  lea     rcx, [rsp+48h+var_24]; pExceptionObject
0x180072e6a  call    _CxxThrowException_0
0x180072e6f  call    ?Release@?$CSCMComPolyObject@VCSCM@@@@UEAAKXZ; CSCMComPolyObject<CSCM>::Release(void)
0x180072e74  mov     rax, [rsp+48h+arg_10]
0x180072e79  mov     [rsi], rax
0x180072e7c  jmp     short loc_180072EEB
0x180072e7e  mov     [rsp+48h+arg_0], 0
0x180072e87  mov     eax, cs:_bidGblFlags
0x180072e8d  mov     ebx, 8007000Eh
0x180072e92  test    al, 2
0x180072e94  jz      short loc_180072ED1
0x180072e96  mov     r8d, 24Ch; unsigned int
0x180072e9c  lea     rdx, aNewcmClassCscm; "<NewCM<class CSCM>::CoCreateCM|OLEDB|ER"...
0x180072ea3  mov     ecx, ebx; int
0x180072ea5  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180072eaa  mov     eax, cs:_bidGblFlags
0x180072eb0  test    al, 2
0x180072eb2  jz      short loc_180072ED1
0x180072eb4  mov     r9d, ebx
0x180072eb7  lea     r8, aNewcmClassCscm_0; "<NewCM<class CSCM>::CoCreateCM|Trace|HR"...
0x180072ebe  mov     edx, 93009h
0x180072ec3  mov     rcx, cs:?_bidSrcFile2A@?1??CoCreateCM@?$NewCM@VCSCM@@@@SAJPEAUIUnknown@@KAEBU_GUID@@PEAPEAX@Z@4REBDEB; char const * const `NewCM<CSCM>::CoCreateCM(IUnknown *,ulong,_GUID const &,void * *)'::`2'::_bidSrcFile2A
0x180072eca  call    _bidTraceHR
0x180072ecf  mov     ebx, eax
0x180072ed1  mov     [rsp+48h+var_20], ebx
0x180072ed5  lea     rdx, _TI1J; pThrowInfo
0x180072edc  lea     rcx, [rsp+48h+var_20]; pExceptionObject
0x180072ee1  call    _CxxThrowException_0
0x180072ee7  mov     ebx, [rsp+48h+arg_8]
0x180072eeb  test    byte ptr cs:_bidGblFlags, 2
0x180072ef2  jz      short loc_180072F11
0x180072ef4  mov     r9d, ebx
0x180072ef7  lea     r8, aNewcmClassCscm_0; "<NewCM<class CSCM>::CoCreateCM|Trace|HR"...
0x180072efe  mov     edx, 9BC09h
0x180072f03  mov     rcx, cs:?_bidSrcFile2A@?1??CoCreateCM@?$NewCM@VCSCM@@@@SAJPEAUIUnknown@@KAEBU_GUID@@PEAPEAX@Z@4REBDEB; char const * const `NewCM<CSCM>::CoCreateCM(IUnknown *,ulong,_GUID const &,void * *)'::`2'::_bidSrcFile2A
0x180072f0a  call    _bidTraceHR
0x180072f0f  mov     ebx, eax
0x180072f11  mov     eax, ebx
0x180072f13  add     rsp, 30h
0x180072f17  pop     rdi
0x180072f18  pop     rsi
0x180072f19  pop     rbx
0x180072f1a  retn
```
