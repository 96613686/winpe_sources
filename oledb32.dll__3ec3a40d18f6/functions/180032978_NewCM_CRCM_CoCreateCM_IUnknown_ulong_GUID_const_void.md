# NewCM<CRCM>::CoCreateCM(IUnknown *,ulong,_GUID const &,void * *)

- ea: `0x180032978`
- end: `0x180032bb5`
- name: `?CoCreateCM@?$NewCM@VCRCM@@@@SAJPEAUIUnknown@@KAEBU_GUID@@PEAPEAX@Z`
- size: `573`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18002a994`
- `0x18002ced8`
- `0x18002d3bc`
- `0x18007a108`

## callees

- `0x180013870`
- `0x180029560`
- `0x18002ec0c`
- `0x18002fb64`
- `0x180032978`
- `0x1800375e4`
- `0x180087010`

## import_xrefs

- `MSDART!MpHeapAlloc` at `0x1800329c1`
- `MSDART!MpHeapAlloc` at `0x1800329c1`

## string_xrefs

- `0x180032a0e`: `<NewCM<class CRCM>::CoCreateCM|OLEDB|ERR> `
- `0x180032a2c`: `<NewCM<class CRCM>::CoCreateCM|OLEDB|ERR> `
- `0x180032ac4`: `<NewCM<class CRCM>::CoCreateCM|OLEDB|ERR> `
- `0x180032b36`: `<NewCM<class CRCM>::CoCreateCM|OLEDB|ERR> `
- `0x180032a47`: `<NewCM<class CRCM>::CoCreateCM|Trace|HR> `
- `0x180032adf`: `<NewCM<class CRCM>::CoCreateCM|Trace|HR> `
- `0x180032b51`: `<NewCM<class CRCM>::CoCreateCM|Trace|HR> `
- `0x180032b91`: `<NewCM<class CRCM>::CoCreateCM|Trace|HR> `

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall NewCM<CRCM>::CoCreateCM(__int64 a1, __int64 a2, __int64 a3, _QWORD *a4)
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
  if ( !v6 || (v7 = CACMComPolyObject<CRCM>::CACMComPolyObject<CRCM>(v6, 0), (v8 = v7) == 0) )
  {
    v11 = -2147024882;
    if ( (bidGblFlags & 2) != 0 )
    {
      OLEDBTraceErr(-2147024882, L"<NewCM<class CRCM>::CoCreateCM|OLEDB|ERR> ", 0x24Cu);
      if ( (bidGblFlags & 2) != 0 )
        v11 = bidTraceHR(
                `NewCM<CRCM>::CoCreateCM'::`2'::_bidSrcFile2A[0],
                602121,
                L"<NewCM<class CRCM>::CoCreateCM|Trace|HR> ",
                2147942414LL);
    }
    v14 = v11;
    throw (long *)&v14;
  }
  v9 = ATL::CComPolyObject<CRCM>::FinalConstruct(v7);
  if ( v9 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      OLEDBTraceErr(v9, L"<NewCM<class CRCM>::CoCreateCM|OLEDB|ERR> ", 0x250u);
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(v9, L"<NewCM<class CRCM>::CoCreateCM|OLEDB|ERR> ", 0x250u);
        if ( (bidGblFlags & 2) != 0 )
          v9 = bidTraceHR(
                 `NewCM<CRCM>::CoCreateCM'::`2'::_bidSrcFile2A[0],
                 606217,
                 L"<NewCM<class CRCM>::CoCreateCM|Trace|HR> ",
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
      OLEDBTraceErr(v10, L"<NewCM<class CRCM>::CoCreateCM|OLEDB|ERR> ", 0x259u);
      if ( (bidGblFlags & 2) != 0 )
        v10 = bidTraceHR(
                `NewCM<CRCM>::CoCreateCM'::`2'::_bidSrcFile2A[0],
                615433,
                L"<NewCM<class CRCM>::CoCreateCM|Trace|HR> ",
                v10);
    }
    v13 = v10;
    throw (long *)&v13;
  }
  *a4 = v15;
  if ( (bidGblFlags & 2) != 0 )
    return (unsigned int)bidTraceHR(
                           `NewCM<CRCM>::CoCreateCM'::`2'::_bidSrcFile2A[0],
                           637961,
                           L"<NewCM<class CRCM>::CoCreateCM|Trace|HR> ",
                           v10);
  return v10;
}

```

## disassembly

```asm
0x180032978  mov     [rsp+arg_10], r8
0x18003297d  mov     [rsp+arg_8], edx
0x180032981  mov     [rsp+arg_0], rcx
0x180032986  push    rbx
0x180032987  push    rsi
0x180032988  push    rdi
0x180032989  sub     rsp, 30h
0x18003298d  mov     rsi, r9
0x180032990  test    r9, r9
0x180032993  jnz     short loc_18003299F
0x180032995  mov     eax, 80004003h
0x18003299a  jmp     loc_180032BAD
0x18003299f  mov     qword ptr [r9], 0
0x1800329a6  mov     [rsp+48h+arg_10], 0
0x1800329af  mov     edx, 1300000h
0x1800329b4  mov     r8d, 180h
0x1800329ba  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x1800329c1  call    cs:__imp_MpHeapAlloc
0x1800329c7  mov     [rsp+48h+arg_0], rax
0x1800329cc  test    rax, rax
0x1800329cf  jz      loc_180032B18
0x1800329d5  xor     edx, edx
0x1800329d7  mov     rcx, rax
0x1800329da  call    ??0?$CACMComPolyObject@VCRCM@@@@QEAA@PEAX@Z; CACMComPolyObject<CRCM>::CACMComPolyObject<CRCM>(void *)
0x1800329df  mov     rdi, rax
0x1800329e2  mov     [rsp+48h+arg_0], rax
0x1800329e7  test    rax, rax
0x1800329ea  jz      loc_180032B21
0x1800329f0  mov     rcx, rax
0x1800329f3  call    ?FinalConstruct@?$CComPolyObject@VCRCM@@@ATL@@QEAAJXZ; ATL::CComPolyObject<CRCM>::FinalConstruct(void)
0x1800329f8  mov     ebx, eax
0x1800329fa  test    eax, eax
0x1800329fc  jns     short loc_180032A76
0x1800329fe  mov     eax, cs:_bidGblFlags
0x180032a04  test    al, 2
0x180032a06  jz      short loc_180032A61
0x180032a08  mov     r8d, 250h; unsigned int
0x180032a0e  lea     rdx, aNewcmClassCrcm_0; "<NewCM<class CRCM>::CoCreateCM|OLEDB|ER"...
0x180032a15  mov     ecx, ebx; int
0x180032a17  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180032a1c  mov     eax, cs:_bidGblFlags
0x180032a22  test    al, 2
0x180032a24  jz      short loc_180032A61
0x180032a26  mov     r8d, 250h; unsigned int
0x180032a2c  lea     rdx, aNewcmClassCrcm_0; "<NewCM<class CRCM>::CoCreateCM|OLEDB|ER"...
0x180032a33  mov     ecx, ebx; int
0x180032a35  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180032a3a  mov     eax, cs:_bidGblFlags
0x180032a40  test    al, 2
0x180032a42  jz      short loc_180032A61
0x180032a44  mov     r9d, ebx
0x180032a47  lea     r8, aNewcmClassCrcm_1; "<NewCM<class CRCM>::CoCreateCM|Trace|HR"...
0x180032a4e  mov     edx, 94009h
0x180032a53  mov     rcx, cs:?_bidSrcFile2A@?1??CoCreateCM@?$NewCM@VCRCM@@@@SAJPEAUIUnknown@@KAEBU_GUID@@PEAPEAX@Z@4REBDEB; char const * const `NewCM<CRCM>::CoCreateCM(IUnknown *,ulong,_GUID const &,void * *)'::`2'::_bidSrcFile2A
0x180032a5a  call    _bidTraceHR
0x180032a5f  mov     ebx, eax
0x180032a61  mov     [rsp+48h+pExceptionObject], ebx
0x180032a65  lea     rdx, _TI1J; pThrowInfo
0x180032a6c  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180032a71  call    _CxxThrowException_0
0x180032a76  mov     rax, [rdi]
0x180032a79  mov     rcx, rdi
0x180032a7c  mov     rax, [rax+8]
0x180032a80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032a85  mov     rax, [rdi]
0x180032a88  lea     r8, [rsp+48h+arg_10]
0x180032a8d  lea     rdx, IID_IUnknown
0x180032a94  mov     rcx, rdi
0x180032a97  mov     rax, [rax]
0x180032a9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032a9f  mov     ebx, eax
0x180032aa1  mov     rax, [rdi]
0x180032aa4  mov     rax, [rax+10h]
0x180032aa8  mov     rcx, rdi
0x180032aab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032ab0  test    ebx, ebx
0x180032ab2  jns     short loc_180032B0E
0x180032ab4  mov     eax, cs:_bidGblFlags
0x180032aba  test    al, 2
0x180032abc  jz      short loc_180032AF9
0x180032abe  mov     r8d, 259h; unsigned int
0x180032ac4  lea     rdx, aNewcmClassCrcm_0; "<NewCM<class CRCM>::CoCreateCM|OLEDB|ER"...
0x180032acb  mov     ecx, ebx; int
0x180032acd  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180032ad2  mov     eax, cs:_bidGblFlags
0x180032ad8  test    al, 2
0x180032ada  jz      short loc_180032AF9
0x180032adc  mov     r9d, ebx
0x180032adf  lea     r8, aNewcmClassCrcm_1; "<NewCM<class CRCM>::CoCreateCM|Trace|HR"...
0x180032ae6  mov     edx, 96409h
0x180032aeb  mov     rcx, cs:?_bidSrcFile2A@?1??CoCreateCM@?$NewCM@VCRCM@@@@SAJPEAUIUnknown@@KAEBU_GUID@@PEAPEAX@Z@4REBDEB; char const * const `NewCM<CRCM>::CoCreateCM(IUnknown *,ulong,_GUID const &,void * *)'::`2'::_bidSrcFile2A
0x180032af2  call    _bidTraceHR
0x180032af7  mov     ebx, eax
0x180032af9  mov     [rsp+48h+var_24], ebx
0x180032afd  lea     rdx, _TI1J; pThrowInfo
0x180032b04  lea     rcx, [rsp+48h+var_24]; pExceptionObject
0x180032b09  call    _CxxThrowException_0
0x180032b0e  mov     rax, [rsp+48h+arg_10]
0x180032b13  mov     [rsi], rax
0x180032b16  jmp     short loc_180032B85
0x180032b18  mov     [rsp+48h+arg_0], 0
0x180032b21  mov     eax, cs:_bidGblFlags
0x180032b27  mov     ebx, 8007000Eh
0x180032b2c  test    al, 2
0x180032b2e  jz      short loc_180032B6B
0x180032b30  mov     r8d, 24Ch; unsigned int
0x180032b36  lea     rdx, aNewcmClassCrcm_0; "<NewCM<class CRCM>::CoCreateCM|OLEDB|ER"...
0x180032b3d  mov     ecx, ebx; int
0x180032b3f  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180032b44  mov     eax, cs:_bidGblFlags
0x180032b4a  test    al, 2
0x180032b4c  jz      short loc_180032B6B
0x180032b4e  mov     r9d, ebx
0x180032b51  lea     r8, aNewcmClassCrcm_1; "<NewCM<class CRCM>::CoCreateCM|Trace|HR"...
0x180032b58  mov     edx, 93009h
0x180032b5d  mov     rcx, cs:?_bidSrcFile2A@?1??CoCreateCM@?$NewCM@VCRCM@@@@SAJPEAUIUnknown@@KAEBU_GUID@@PEAPEAX@Z@4REBDEB; char const * const `NewCM<CRCM>::CoCreateCM(IUnknown *,ulong,_GUID const &,void * *)'::`2'::_bidSrcFile2A
0x180032b64  call    _bidTraceHR
0x180032b69  mov     ebx, eax
0x180032b6b  mov     [rsp+48h+var_20], ebx
0x180032b6f  lea     rdx, _TI1J; pThrowInfo
0x180032b76  lea     rcx, [rsp+48h+var_20]; pExceptionObject
0x180032b7b  call    _CxxThrowException_0
0x180032b81  mov     ebx, [rsp+48h+arg_8]
0x180032b85  test    byte ptr cs:_bidGblFlags, 2
0x180032b8c  jz      short loc_180032BAB
0x180032b8e  mov     r9d, ebx
0x180032b91  lea     r8, aNewcmClassCrcm_1; "<NewCM<class CRCM>::CoCreateCM|Trace|HR"...
0x180032b98  mov     edx, 9BC09h
0x180032b9d  mov     rcx, cs:?_bidSrcFile2A@?1??CoCreateCM@?$NewCM@VCRCM@@@@SAJPEAUIUnknown@@KAEBU_GUID@@PEAPEAX@Z@4REBDEB; char const * const `NewCM<CRCM>::CoCreateCM(IUnknown *,ulong,_GUID const &,void * *)'::`2'::_bidSrcFile2A
0x180032ba4  call    _bidTraceHR
0x180032ba9  mov     ebx, eax
0x180032bab  mov     eax, ebx
0x180032bad  add     rsp, 30h
0x180032bb1  pop     rdi
0x180032bb2  pop     rsi
0x180032bb3  pop     rbx
0x180032bb4  retn
```
