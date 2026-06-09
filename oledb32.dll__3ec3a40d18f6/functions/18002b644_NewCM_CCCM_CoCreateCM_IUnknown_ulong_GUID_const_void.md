# NewCM<CCCM>::CoCreateCM(IUnknown *,ulong,_GUID const &,void * *)

- ea: `0x18002b644`
- end: `0x18002b87b`
- name: `?CoCreateCM@?$NewCM@VCCCM@@@@SAJPEAUIUnknown@@KAEBU_GUID@@PEAPEAX@Z`
- size: `567`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18001baf0`

## callees

- `0x180013870`
- `0x180029560`
- `0x18002b644`
- `0x18002ec0c`
- `0x18002f9ac`
- `0x18003753c`
- `0x180087010`

## import_xrefs

- `MSDART!MpHeapAlloc` at `0x18002b694`
- `MSDART!MpHeapAlloc` at `0x18002b694`

## string_xrefs

- `0x18002b6d5`: `<NewCM<class CCCM>::CoCreateCM|OLEDB|ERR> `
- `0x18002b73d`: `<NewCM<class CCCM>::CoCreateCM|OLEDB|ERR> `
- `0x18002b75b`: `<NewCM<class CCCM>::CoCreateCM|OLEDB|ERR> `
- `0x18002b7f3`: `<NewCM<class CCCM>::CoCreateCM|OLEDB|ERR> `
- `0x18002b6f0`: `<NewCM<class CCCM>::CoCreateCM|Trace|HR> `
- `0x18002b776`: `<NewCM<class CCCM>::CoCreateCM|Trace|HR> `
- `0x18002b80e`: `<NewCM<class CCCM>::CoCreateCM|Trace|HR> `
- `0x18002b857`: `<NewCM<class CCCM>::CoCreateCM|Trace|HR> `

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall NewCM<CCCM>::CoCreateCM(__int64 a1, __int64 a2, __int64 a3, _QWORD *a4)
{
  __int64 v7; // rax
  __int64 v8; // rbx
  int v9; // ebx
  int v10; // edi
  unsigned int v11; // edi
  unsigned int v12; // ebx
  int pExceptionObject; // [rsp+20h] [rbp-38h] BYREF
  int v14; // [rsp+24h] [rbp-34h] BYREF
  unsigned int v15; // [rsp+28h] [rbp-30h] BYREF
  unsigned int v16; // [rsp+2Ch] [rbp-2Ch] BYREF
  __int64 v17; // [rsp+30h] [rbp-28h]
  __int64 v18; // [rsp+70h] [rbp+18h] BYREF
  __int64 v19; // [rsp+78h] [rbp+20h]

  v18 = a3;
  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  v19 = 0;
  v18 = 0;
  v7 = MpHeapAlloc(g_hHeapHandle, 19922944, 808);
  try
  {
    v17 = v7;
    if ( v7 )
      v8 = CACMComPolyObject<CCCM>::CACMComPolyObject<CCCM>(v7, a1);
    else
      v8 = 0;
    v19 = v8;
    if ( !v8 )
    {
      v9 = -2147024882;
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(-2147024882, L"<NewCM<class CCCM>::CoCreateCM|OLEDB|ERR> ", 0x24Cu);
        if ( (bidGblFlags & 2) != 0 )
          v9 = bidTraceHR(
                 `NewCM<CCCM>::CoCreateCM'::`2'::_bidSrcFile2A[0],
                 602121,
                 L"<NewCM<class CCCM>::CoCreateCM|Trace|HR> ",
                 2147942414LL);
      }
      pExceptionObject = v9;
      throw (long *)&pExceptionObject;
    }
    v10 = ATL::CComPolyObject<CCCM>::FinalConstruct(v8);
    if ( v10 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(v10, L"<NewCM<class CCCM>::CoCreateCM|OLEDB|ERR> ", 0x250u);
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(v10, L"<NewCM<class CCCM>::CoCreateCM|OLEDB|ERR> ", 0x250u);
          if ( (bidGblFlags & 2) != 0 )
            v10 = bidTraceHR(
                    `NewCM<CCCM>::CoCreateCM'::`2'::_bidSrcFile2A[0],
                    606217,
                    L"<NewCM<class CCCM>::CoCreateCM|Trace|HR> ",
                    (unsigned int)v10);
        }
      }
      v14 = v10;
      throw (long *)&v14;
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
    v11 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v8)(v8, &IID_IUnknown, &v18);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    if ( (v11 & 0x80000000) != 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(v11, L"<NewCM<class CCCM>::CoCreateCM|OLEDB|ERR> ", 0x259u);
        if ( (bidGblFlags & 2) != 0 )
          v11 = bidTraceHR(
                  `NewCM<CCCM>::CoCreateCM'::`2'::_bidSrcFile2A[0],
                  615433,
                  L"<NewCM<class CCCM>::CoCreateCM|Trace|HR> ",
                  v11);
      }
      v15 = v11;
      throw (long *)&v15;
    }
    *a4 = v18;
  }
  catch ( long v16 )
  {
    if ( (bidGblFlags & 2) != 0 && `NewCM<CCCM>::CoCreateCM'::`31'::_bidPtrSA_030_609[0] )
    {
      v12 = v16;
      bidTraceA(
        `NewCM<CCCM>::CoCreateCM'::`31'::_bidSrcFileA[0],
        623616,
        `NewCM<CCCM>::CoCreateCM'::`31'::_bidPtrSA_030_609[0],
        v16);
    }
    else
    {
      v12 = v16;
    }
    if ( v18 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    if ( v19 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v19 + 24LL))(v19, 1);
    v11 = v12;
  }
  if ( (bidGblFlags & 2) != 0 )
    return (unsigned int)bidTraceHR(
                           `NewCM<CCCM>::CoCreateCM'::`2'::_bidSrcFile2A[0],
                           637961,
                           L"<NewCM<class CCCM>::CoCreateCM|Trace|HR> ",
                           v11);
  return v11;
}

```

## disassembly

```asm
0x18002b644  mov     [rsp+arg_10], r8
0x18002b649  mov     [rsp+arg_8], edx
0x18002b64d  push    rbx
0x18002b64e  push    rsi
0x18002b64f  push    rdi
0x18002b650  sub     rsp, 40h
0x18002b654  mov     rsi, r9
0x18002b657  mov     rbx, rcx
0x18002b65a  test    r9, r9
0x18002b65d  jnz     short loc_18002B669
0x18002b65f  mov     eax, 80004003h
0x18002b664  jmp     loc_18002B873
0x18002b669  mov     qword ptr [r9], 0
0x18002b670  mov     [rsp+58h+arg_18], 0
0x18002b679  mov     [rsp+58h+arg_10], 0
0x18002b682  mov     edx, 1300000h
0x18002b687  mov     r8d, 328h
0x18002b68d  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x18002b694  call    cs:__imp_MpHeapAlloc
0x18002b69a  mov     [rsp+58h+var_28], rax
0x18002b69f  test    rax, rax
0x18002b6a2  jz      short loc_18002B6B4
0x18002b6a4  mov     rdx, rbx
0x18002b6a7  mov     rcx, rax
0x18002b6aa  call    ??0?$CACMComPolyObject@VCCCM@@@@QEAA@PEAX@Z; CACMComPolyObject<CCCM>::CACMComPolyObject<CCCM>(void *)
0x18002b6af  mov     rbx, rax
0x18002b6b2  jmp     short loc_18002B6B6
0x18002b6b4  xor     ebx, ebx
0x18002b6b6  mov     [rsp+58h+arg_18], rbx
0x18002b6bb  test    rbx, rbx
0x18002b6be  jnz     short loc_18002B71F
0x18002b6c0  mov     eax, cs:_bidGblFlags
0x18002b6c6  mov     ebx, 8007000Eh
0x18002b6cb  test    al, 2
0x18002b6cd  jz      short loc_18002B70A
0x18002b6cf  mov     r8d, 24Ch; unsigned int
0x18002b6d5  lea     rdx, aNewcmClassCccm; "<NewCM<class CCCM>::CoCreateCM|OLEDB|ER"...
0x18002b6dc  mov     ecx, ebx; int
0x18002b6de  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18002b6e3  mov     eax, cs:_bidGblFlags
0x18002b6e9  test    al, 2
0x18002b6eb  jz      short loc_18002B70A
0x18002b6ed  mov     r9d, ebx
0x18002b6f0  lea     r8, aNewcmClassCccm_1; "<NewCM<class CCCM>::CoCreateCM|Trace|HR"...
0x18002b6f7  mov     edx, 93009h
0x18002b6fc  mov     rcx, cs:?_bidSrcFile2A@?1??CoCreateCM@?$NewCM@VCCCM@@@@SAJPEAUIUnknown@@KAEBU_GUID@@PEAPEAX@Z@4REBDEB; char const * const `NewCM<CCCM>::CoCreateCM(IUnknown *,ulong,_GUID const &,void * *)'::`2'::_bidSrcFile2A
0x18002b703  call    _bidTraceHR
0x18002b708  mov     ebx, eax
0x18002b70a  mov     [rsp+58h+pExceptionObject], ebx
0x18002b70e  lea     rdx, _TI1J; pThrowInfo
0x18002b715  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18002b71a  call    _CxxThrowException_0
0x18002b71f  mov     rcx, rbx
0x18002b722  call    ?FinalConstruct@?$CComPolyObject@VCCCM@@@ATL@@QEAAJXZ; ATL::CComPolyObject<CCCM>::FinalConstruct(void)
0x18002b727  mov     edi, eax
0x18002b729  test    eax, eax
0x18002b72b  jns     short loc_18002B7A5
0x18002b72d  mov     eax, cs:_bidGblFlags
0x18002b733  test    al, 2
0x18002b735  jz      short loc_18002B790
0x18002b737  mov     r8d, 250h; unsigned int
0x18002b73d  lea     rdx, aNewcmClassCccm; "<NewCM<class CCCM>::CoCreateCM|OLEDB|ER"...
0x18002b744  mov     ecx, edi; int
0x18002b746  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18002b74b  mov     eax, cs:_bidGblFlags
0x18002b751  test    al, 2
0x18002b753  jz      short loc_18002B790
0x18002b755  mov     r8d, 250h; unsigned int
0x18002b75b  lea     rdx, aNewcmClassCccm; "<NewCM<class CCCM>::CoCreateCM|OLEDB|ER"...
0x18002b762  mov     ecx, edi; int
0x18002b764  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18002b769  mov     eax, cs:_bidGblFlags
0x18002b76f  test    al, 2
0x18002b771  jz      short loc_18002B790
0x18002b773  mov     r9d, edi
0x18002b776  lea     r8, aNewcmClassCccm_1; "<NewCM<class CCCM>::CoCreateCM|Trace|HR"...
0x18002b77d  mov     edx, 94009h
0x18002b782  mov     rcx, cs:?_bidSrcFile2A@?1??CoCreateCM@?$NewCM@VCCCM@@@@SAJPEAUIUnknown@@KAEBU_GUID@@PEAPEAX@Z@4REBDEB; char const * const `NewCM<CCCM>::CoCreateCM(IUnknown *,ulong,_GUID const &,void * *)'::`2'::_bidSrcFile2A
0x18002b789  call    _bidTraceHR
0x18002b78e  mov     edi, eax
0x18002b790  mov     [rsp+58h+var_34], edi
0x18002b794  lea     rdx, _TI1J; pThrowInfo
0x18002b79b  lea     rcx, [rsp+58h+var_34]; pExceptionObject
0x18002b7a0  call    _CxxThrowException_0
0x18002b7a5  mov     rax, [rbx]
0x18002b7a8  mov     rcx, rbx
0x18002b7ab  mov     rax, [rax+8]
0x18002b7af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b7b4  mov     rax, [rbx]
0x18002b7b7  lea     r8, [rsp+58h+arg_10]
0x18002b7bc  lea     rdx, IID_IUnknown
0x18002b7c3  mov     rcx, rbx
0x18002b7c6  mov     rax, [rax]
0x18002b7c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b7ce  mov     edi, eax
0x18002b7d0  mov     rax, [rbx]
0x18002b7d3  mov     rax, [rax+10h]
0x18002b7d7  mov     rcx, rbx
0x18002b7da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b7df  test    edi, edi
0x18002b7e1  jns     short loc_18002B83D
0x18002b7e3  mov     eax, cs:_bidGblFlags
0x18002b7e9  test    al, 2
0x18002b7eb  jz      short loc_18002B828
0x18002b7ed  mov     r8d, 259h; unsigned int
0x18002b7f3  lea     rdx, aNewcmClassCccm; "<NewCM<class CCCM>::CoCreateCM|OLEDB|ER"...
0x18002b7fa  mov     ecx, edi; int
0x18002b7fc  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18002b801  mov     eax, cs:_bidGblFlags
0x18002b807  test    al, 2
0x18002b809  jz      short loc_18002B828
0x18002b80b  mov     r9d, edi
0x18002b80e  lea     r8, aNewcmClassCccm_1; "<NewCM<class CCCM>::CoCreateCM|Trace|HR"...
0x18002b815  mov     edx, 96409h
0x18002b81a  mov     rcx, cs:?_bidSrcFile2A@?1??CoCreateCM@?$NewCM@VCCCM@@@@SAJPEAUIUnknown@@KAEBU_GUID@@PEAPEAX@Z@4REBDEB; char const * const `NewCM<CCCM>::CoCreateCM(IUnknown *,ulong,_GUID const &,void * *)'::`2'::_bidSrcFile2A
0x18002b821  call    _bidTraceHR
0x18002b826  mov     edi, eax
0x18002b828  mov     [rsp+58h+var_30], edi
0x18002b82c  lea     rdx, _TI1J; pThrowInfo
0x18002b833  lea     rcx, [rsp+58h+var_30]; pExceptionObject
0x18002b838  call    _CxxThrowException_0
0x18002b83d  mov     rax, [rsp+58h+arg_10]
0x18002b842  mov     [rsi], rax
0x18002b845  jmp     short loc_18002B84B
0x18002b847  mov     edi, [rsp+58h+arg_8]
0x18002b84b  test    byte ptr cs:_bidGblFlags, 2
0x18002b852  jz      short loc_18002B871
0x18002b854  mov     r9d, edi
0x18002b857  lea     r8, aNewcmClassCccm_1; "<NewCM<class CCCM>::CoCreateCM|Trace|HR"...
0x18002b85e  mov     edx, 9BC09h
0x18002b863  mov     rcx, cs:?_bidSrcFile2A@?1??CoCreateCM@?$NewCM@VCCCM@@@@SAJPEAUIUnknown@@KAEBU_GUID@@PEAPEAX@Z@4REBDEB; char const * const `NewCM<CCCM>::CoCreateCM(IUnknown *,ulong,_GUID const &,void * *)'::`2'::_bidSrcFile2A
0x18002b86a  call    _bidTraceHR
0x18002b86f  mov     edi, eax
0x18002b871  mov     eax, edi
0x18002b873  add     rsp, 40h
0x18002b877  pop     rdi
0x18002b878  pop     rsi
0x18002b879  pop     rbx
0x18002b87a  retn
```
