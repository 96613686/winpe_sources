# CreateDPO(CCMProviderInfo *,IUnknown *,ulong,ushort *,_GUID const &,IUnknown * *)

- ea: `0x18005b5c8`
- end: `0x18005b9d2`
- name: `?CreateDPO@@YAJPEAVCCMProviderInfo@@PEAUIUnknown@@KPEAGAEBU_GUID@@PEAPEAU2@@Z`
- size: `1034`
- prototype: `__int64 __usercall@<rax>(struct CCMProviderInfo *@<rcx>, struct IUnknown *@<rdx>, unsigned int@<r8d>, unsigned __int16 *@<r9>, const struct _GUID *, struct IUnknown **)`
- caller_count: `3`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180013ff4`
- `0x18006946c`
- `0x18006a414`

## callees

- `0x180013870`
- `0x1800194f4`
- `0x180029560`
- `0x18002ec0c`
- `0x18005b068`
- `0x18005b5c8`
- `0x18005bb08`
- `0x18005ca1c`
- `0x180087010`

## import_xrefs

- `MSDART!MpHeapAlloc` at `0x18005b6f5`
- `MSDART!MpHeapAlloc` at `0x18005b6f5`

## string_xrefs

- `0x18005b60d`: `<CreateDPO|OLEDB|ERR> `
- `0x18005b65b`: `<CreateDPO|OLEDB|ERR> `
- `0x18005b6b8`: `<CreateDPO|OLEDB|ERR> `
- `0x18005b748`: `<CreateDPO|OLEDB|ERR> `
- `0x18005b766`: `<CreateDPO|OLEDB|ERR> `
- `0x18005b7da`: `<CreateDPO|OLEDB|ERR> `
- `0x18005b7f8`: `<CreateDPO|OLEDB|ERR> `
- `0x18005b881`: `<CreateDPO|OLEDB|ERR> `
- `0x18005b8b7`: `<CreateDPO|OLEDB|ERR> `
- `0x18005b93d`: `<CreateDPO|OLEDB|ERR> `
- `0x18005b781`: `<CreateDPO|Trace|HR> `
- `0x18005b813`: `<CreateDPO|Trace|HR> `
- `0x18005b8d2`: `<CreateDPO|Trace|HR> `
- `0x18005b958`: `<CreateDPO|Trace|HR> `
- `0x18005b9a1`: `<CreateDPO|Trace|HR> `

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall CreateDPO(
        struct CCMProviderInfo *a1,
        struct IUnknown *a2,
        unsigned int a3,
        unsigned __int16 *a4,
        const struct _GUID *a5,
        struct IUnknown **a6)
{
  unsigned int v10; // edi
  __int64 v11; // rdx
  __int64 v12; // rax
  __int64 v13; // rax
  _QWORD *v14; // rsi
  int v15; // edi
  int Datasource; // edi
  int v17; // eax
  int v18; // edi
  int pExceptionObject; // [rsp+20h] [rbp-58h] BYREF
  int v21; // [rsp+24h] [rbp-54h] BYREF
  unsigned int v22; // [rsp+28h] [rbp-50h] BYREF
  int v23; // [rsp+2Ch] [rbp-4Ch] BYREF
  struct IUnknown *v24; // [rsp+38h] [rbp-40h] BYREF
  __int64 v25; // [rsp+40h] [rbp-38h]

  if ( a1 )
  {
    if ( a6 )
    {
      *a6 = 0;
      if ( !a2 || (unsigned int)ATL::InlineIsEqualUnknown(a5) )
      {
        v24 = 0;
        v12 = MpHeapAlloc(g_hHeapHandle, 19922944, 304);
        if ( v12 )
        {
          v13 = ATL::CComPolyObject<CDPO>::CComPolyObject<CDPO>(v12, a2);
          v14 = (_QWORD *)v13;
          v25 = v13;
          if ( v13 )
          {
            v15 = ATL::CComPolyObject<CDPO>::FinalConstruct(v13);
            if ( v15 < 0 )
            {
              if ( (bidGblFlags & 2) != 0 )
              {
                OLEDBTraceErr(v15, L"<CreateDPO|OLEDB|ERR> ", 0xD0u);
                if ( (bidGblFlags & 2) != 0 )
                {
                  OLEDBTraceErr(v15, L"<CreateDPO|OLEDB|ERR> ", 0xD0u);
                  if ( (bidGblFlags & 2) != 0 )
                    v15 = bidTraceHR(off_1800C8410[0], 213001, L"<CreateDPO|Trace|HR> ", (unsigned int)v15);
                }
              }
              pExceptionObject = v15;
              throw (long *)&pExceptionObject;
            }
            Datasource = CDPO::InternalCreateDatasource((CDPO *)(v14 + 3), a1, a3, a4);
            if ( Datasource < 0 )
            {
              if ( (bidGblFlags & 2) != 0 )
              {
                OLEDBTraceErr(Datasource, L"<CreateDPO|OLEDB|ERR> ", 0xD6u);
                if ( (bidGblFlags & 2) != 0 )
                {
                  OLEDBTraceErr(Datasource, L"<CreateDPO|OLEDB|ERR> ", 0xD6u);
                  if ( (bidGblFlags & 2) != 0 )
                    Datasource = bidTraceHR(
                                   off_1800C8410[0],
                                   219145,
                                   L"<CreateDPO|Trace|HR> ",
                                   (unsigned int)Datasource);
                }
              }
              v21 = Datasource;
              throw (long *)&v21;
            }
            (*(void (__fastcall **)(_QWORD *))(*v14 + 8LL))(v14);
            v17 = (*(__int64 (__fastcall **)(_QWORD *, const struct _GUID *, struct IUnknown **))*v14)(v14, a5, &v24);
            v10 = v17;
            if ( v17 < 0 )
            {
              if ( (bidGblFlags & 2) != 0 )
                OLEDBTraceErr(v17, L"<CreateDPO|OLEDB|ERR> ", 0xDBu);
              (*(void (__fastcall **)(_QWORD *))(*v14 + 16LL))(v14);
              v25 = 0;
              if ( (bidGblFlags & 2) != 0 )
              {
                OLEDBTraceErr(v10, L"<CreateDPO|OLEDB|ERR> ", 0xDEu);
                if ( (bidGblFlags & 2) != 0 )
                  v10 = bidTraceHR(off_1800C8410[0], 227337, L"<CreateDPO|Trace|HR> ", v10);
              }
              v22 = v10;
              throw (long *)&v22;
            }
            (*(void (__fastcall **)(_QWORD *))(*v14 + 16LL))(v14);
            *a6 = v24;
            v14[31] = v14;
            if ( (bidGblFlags & 2) != 0 )
            {
              v11 = 247817;
              return (unsigned int)bidTraceHR(off_1800C8410[0], v11, L"<CreateDPO|Trace|HR> ", v10);
            }
            return v10;
          }
        }
        else
        {
          v25 = 0;
        }
        v18 = -2147024882;
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(-2147024882, L"<CreateDPO|OLEDB|ERR> ", 0xCCu);
          if ( (bidGblFlags & 2) != 0 )
            v18 = bidTraceHR(off_1800C8410[0], 208905, L"<CreateDPO|Trace|HR> ", 2147942414LL);
        }
        v23 = v18;
        throw (long *)&v23;
      }
      v10 = -2147217886;
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(-2147217886, L"<CreateDPO|OLEDB|ERR> ", 0xC0u);
        if ( (bidGblFlags & 2) != 0 )
        {
          v11 = 196617;
          return (unsigned int)bidTraceHR(off_1800C8410[0], v11, L"<CreateDPO|Trace|HR> ", v10);
        }
      }
    }
    else
    {
      v10 = -2147467261;
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(-2147467261, L"<CreateDPO|OLEDB|ERR> ", 0xBCu);
        if ( (bidGblFlags & 2) != 0 )
        {
          v11 = 192521;
          return (unsigned int)bidTraceHR(off_1800C8410[0], v11, L"<CreateDPO|Trace|HR> ", v10);
        }
      }
    }
  }
  else
  {
    v10 = -2147467261;
    if ( (bidGblFlags & 2) != 0 )
    {
      OLEDBTraceErr(-2147467261, L"<CreateDPO|OLEDB|ERR> ", 0xBBu);
      if ( (bidGblFlags & 2) != 0 )
      {
        v11 = 191497;
        return (unsigned int)bidTraceHR(off_1800C8410[0], v11, L"<CreateDPO|Trace|HR> ", v10);
      }
    }
  }
  return v10;
}

```

## disassembly

```asm
0x18005b5c8  mov     [rsp+arg_8], rbx
0x18005b5cd  mov     [rsp+arg_10], rsi
0x18005b5d2  push    rdi
0x18005b5d3  push    r12
0x18005b5d5  push    r13
0x18005b5d7  push    r14
0x18005b5d9  push    r15
0x18005b5db  sub     rsp, 50h
0x18005b5df  mov     r12, r9
0x18005b5e2  mov     r13d, r8d
0x18005b5e5  mov     rdi, rdx
0x18005b5e8  mov     r15, rcx
0x18005b5eb  xor     esi, esi
0x18005b5ed  test    rcx, rcx
0x18005b5f0  jnz     short loc_18005B633
0x18005b5f2  mov     eax, cs:_bidGblFlags
0x18005b5f8  mov     bl, 2
0x18005b5fa  mov     edi, 80004003h
0x18005b5ff  test    bl, al
0x18005b601  jz      loc_18005B9B6
0x18005b607  mov     r8d, 0BBh; unsigned int
0x18005b60d  lea     rdx, aCreatedpoOledb; "<CreateDPO|OLEDB|ERR> "
0x18005b614  mov     ecx, edi; int
0x18005b616  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18005b61b  mov     eax, cs:_bidGblFlags
0x18005b621  test    bl, al
0x18005b623  jz      loc_18005B9B6
0x18005b629  mov     edx, 2EC09h
0x18005b62e  jmp     loc_18005B99E
0x18005b633  mov     rbx, [rsp+78h+arg_28]
0x18005b63b  test    rbx, rbx
0x18005b63e  jnz     short loc_18005B681
0x18005b640  mov     eax, cs:_bidGblFlags
0x18005b646  mov     bl, 2
0x18005b648  mov     edi, 80004003h
0x18005b64d  test    bl, al
0x18005b64f  jz      loc_18005B9B6
0x18005b655  mov     r8d, 0BCh; unsigned int
0x18005b65b  lea     rdx, aCreatedpoOledb; "<CreateDPO|OLEDB|ERR> "
0x18005b662  mov     ecx, edi; int
0x18005b664  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18005b669  mov     eax, cs:_bidGblFlags
0x18005b66f  test    bl, al
0x18005b671  jz      loc_18005B9B6
0x18005b677  mov     edx, 2F009h
0x18005b67c  jmp     loc_18005B99E
0x18005b681  mov     [rbx], rsi
0x18005b684  mov     r14, [rsp+78h+arg_20]
0x18005b68c  test    rdi, rdi
0x18005b68f  jz      short loc_18005B6DE
0x18005b691  mov     rcx, r14; struct _GUID *
0x18005b694  call    ?InlineIsEqualUnknown@ATL@@YAHAEBU_GUID@@@Z; ATL::InlineIsEqualUnknown(_GUID const &)
0x18005b699  test    eax, eax
0x18005b69b  jnz     short loc_18005B6DE
0x18005b69d  mov     eax, cs:_bidGblFlags
0x18005b6a3  mov     bl, 2
0x18005b6a5  mov     edi, 80040E22h
0x18005b6aa  test    bl, al
0x18005b6ac  jz      loc_18005B9B6
0x18005b6b2  mov     r8d, 0C0h; unsigned int
0x18005b6b8  lea     rdx, aCreatedpoOledb; "<CreateDPO|OLEDB|ERR> "
0x18005b6bf  mov     ecx, edi; int
0x18005b6c1  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18005b6c6  mov     eax, cs:_bidGblFlags
0x18005b6cc  test    bl, al
0x18005b6ce  jz      loc_18005B9B6
0x18005b6d4  mov     edx, 30009h
0x18005b6d9  jmp     loc_18005B99E
0x18005b6de  mov     [rsp+78h+var_40], rsi
0x18005b6e3  mov     edx, 1300000h
0x18005b6e8  mov     r8d, 130h
0x18005b6ee  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x18005b6f5  call    cs:__imp_MpHeapAlloc
0x18005b6fb  mov     [rsp+78h+arg_0], rax
0x18005b703  test    rax, rax
0x18005b706  jz      loc_18005B921
0x18005b70c  mov     rdx, rdi
0x18005b70f  mov     rcx, rax
0x18005b712  call    ??0?$CComPolyObject@VCDPO@@@ATL@@QEAA@PEAX@Z; ATL::CComPolyObject<CDPO>::CComPolyObject<CDPO>(void *)
0x18005b717  mov     rsi, rax
0x18005b71a  mov     [rsp+78h+var_38], rax
0x18005b71f  test    rax, rax
0x18005b722  jz      loc_18005B926
0x18005b728  mov     rcx, rax
0x18005b72b  call    ?FinalConstruct@?$CComPolyObject@VCDPO@@@ATL@@QEAAJXZ; ATL::CComPolyObject<CDPO>::FinalConstruct(void)
0x18005b730  mov     edi, eax
0x18005b732  test    eax, eax
0x18005b734  jns     short loc_18005B7B0
0x18005b736  mov     eax, cs:_bidGblFlags
0x18005b73c  mov     bl, 2
0x18005b73e  test    bl, al
0x18005b740  jz      short loc_18005B79B
0x18005b742  mov     r8d, 0D0h; unsigned int
0x18005b748  lea     rdx, aCreatedpoOledb; "<CreateDPO|OLEDB|ERR> "
0x18005b74f  mov     ecx, edi; int
0x18005b751  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18005b756  mov     eax, cs:_bidGblFlags
0x18005b75c  test    bl, al
0x18005b75e  jz      short loc_18005B79B
0x18005b760  mov     r8d, 0D0h; unsigned int
0x18005b766  lea     rdx, aCreatedpoOledb; "<CreateDPO|OLEDB|ERR> "
0x18005b76d  mov     ecx, edi; int
0x18005b76f  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18005b774  mov     eax, cs:_bidGblFlags
0x18005b77a  test    bl, al
0x18005b77c  jz      short loc_18005B79B
0x18005b77e  mov     r9d, edi
0x18005b781  lea     r8, aCreatedpoTrace; "<CreateDPO|Trace|HR> "
0x18005b788  mov     edx, 34009h
0x18005b78d  mov     rcx, cs:off_1800C8410; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18005b794  call    _bidTraceHR
0x18005b799  mov     edi, eax
0x18005b79b  mov     [rsp+78h+pExceptionObject], edi
0x18005b79f  lea     rdx, _TI1J; pThrowInfo
0x18005b7a6  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x18005b7ab  call    _CxxThrowException_0
0x18005b7b0  lea     rcx, [rsi+18h]; this
0x18005b7b4  mov     r9, r12; unsigned __int16 *
0x18005b7b7  mov     r8d, r13d; unsigned int
0x18005b7ba  mov     rdx, r15; struct CCMProviderInfo *
0x18005b7bd  call    ?InternalCreateDatasource@CDPO@@QEAAJPEAVCCMProviderInfo@@KPEAG@Z; CDPO::InternalCreateDatasource(CCMProviderInfo *,ulong,ushort *)
0x18005b7c2  mov     edi, eax
0x18005b7c4  test    eax, eax
0x18005b7c6  jns     short loc_18005B842
0x18005b7c8  mov     eax, cs:_bidGblFlags
0x18005b7ce  mov     bl, 2
0x18005b7d0  test    bl, al
0x18005b7d2  jz      short loc_18005B82D
0x18005b7d4  mov     r8d, 0D6h; unsigned int
0x18005b7da  lea     rdx, aCreatedpoOledb; "<CreateDPO|OLEDB|ERR> "
0x18005b7e1  mov     ecx, edi; int
0x18005b7e3  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18005b7e8  mov     eax, cs:_bidGblFlags
0x18005b7ee  test    bl, al
0x18005b7f0  jz      short loc_18005B82D
0x18005b7f2  mov     r8d, 0D6h; unsigned int
0x18005b7f8  lea     rdx, aCreatedpoOledb; "<CreateDPO|OLEDB|ERR> "
0x18005b7ff  mov     ecx, edi; int
0x18005b801  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18005b806  mov     eax, cs:_bidGblFlags
0x18005b80c  test    bl, al
0x18005b80e  jz      short loc_18005B82D
0x18005b810  mov     r9d, edi
0x18005b813  lea     r8, aCreatedpoTrace; "<CreateDPO|Trace|HR> "
0x18005b81a  mov     edx, 35809h
0x18005b81f  mov     rcx, cs:off_1800C8410; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18005b826  call    _bidTraceHR
0x18005b82b  mov     edi, eax
0x18005b82d  mov     [rsp+78h+var_54], edi
0x18005b831  lea     rdx, _TI1J; pThrowInfo
0x18005b838  lea     rcx, [rsp+78h+var_54]; pExceptionObject
0x18005b83d  call    _CxxThrowException_0
0x18005b842  mov     rax, [rsi]
0x18005b845  mov     rcx, rsi
0x18005b848  mov     rax, [rax+8]
0x18005b84c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b851  mov     rax, [rsi]
0x18005b854  lea     r8, [rsp+78h+var_40]
0x18005b859  mov     rdx, r14
0x18005b85c  mov     rcx, rsi
0x18005b85f  mov     rax, [rax]
0x18005b862  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b867  mov     edi, eax
0x18005b869  test    eax, eax
0x18005b86b  jns     loc_18005B901
0x18005b871  mov     bl, 2
0x18005b873  test    byte ptr cs:_bidGblFlags, bl
0x18005b879  jz      short loc_18005B88F
0x18005b87b  mov     r8d, 0DBh; unsigned int
0x18005b881  lea     rdx, aCreatedpoOledb; "<CreateDPO|OLEDB|ERR> "
0x18005b888  mov     ecx, eax; int
0x18005b88a  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18005b88f  mov     rax, [rsi]
0x18005b892  mov     rcx, rsi
0x18005b895  mov     rax, [rax+10h]
0x18005b899  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b89e  mov     [rsp+78h+var_38], 0
0x18005b8a7  mov     eax, cs:_bidGblFlags
0x18005b8ad  test    bl, al
0x18005b8af  jz      short loc_18005B8EC
0x18005b8b1  mov     r8d, 0DEh; unsigned int
0x18005b8b7  lea     rdx, aCreatedpoOledb; "<CreateDPO|OLEDB|ERR> "
0x18005b8be  mov     ecx, edi; int
0x18005b8c0  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18005b8c5  mov     eax, cs:_bidGblFlags
0x18005b8cb  test    bl, al
0x18005b8cd  jz      short loc_18005B8EC
0x18005b8cf  mov     r9d, edi
0x18005b8d2  lea     r8, aCreatedpoTrace; "<CreateDPO|Trace|HR> "
0x18005b8d9  mov     edx, 37809h
0x18005b8de  mov     rcx, cs:off_1800C8410; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18005b8e5  call    _bidTraceHR
0x18005b8ea  mov     edi, eax
0x18005b8ec  mov     [rsp+78h+var_50], edi
0x18005b8f0  lea     rdx, _TI1J; pThrowInfo
0x18005b8f7  lea     rcx, [rsp+78h+var_50]; pExceptionObject
0x18005b8fc  call    _CxxThrowException_0
0x18005b901  mov     rax, [rsi]
0x18005b904  mov     rcx, rsi
0x18005b907  mov     rax, [rax+10h]
0x18005b90b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b910  mov     rax, [rsp+78h+var_40]
0x18005b915  mov     [rbx], rax
0x18005b918  mov     [rsi+0F8h], rsi
0x18005b91f  jmp     short loc_18005B98F
0x18005b921  mov     [rsp+78h+var_38], rsi
0x18005b926  mov     eax, cs:_bidGblFlags
0x18005b92c  mov     bl, 2
0x18005b92e  mov     edi, 8007000Eh
0x18005b933  test    bl, al
0x18005b935  jz      short loc_18005B972
0x18005b937  mov     r8d, 0CCh; unsigned int
0x18005b93d  lea     rdx, aCreatedpoOledb; "<CreateDPO|OLEDB|ERR> "
0x18005b944  mov     ecx, edi; int
0x18005b946  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18005b94b  mov     eax, cs:_bidGblFlags
0x18005b951  test    bl, al
0x18005b953  jz      short loc_18005B972
0x18005b955  mov     r9d, edi
0x18005b958  lea     r8, aCreatedpoTrace; "<CreateDPO|Trace|HR> "
0x18005b95f  mov     edx, 33009h
0x18005b964  mov     rcx, cs:off_1800C8410; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18005b96b  call    _bidTraceHR
0x18005b970  mov     edi, eax
0x18005b972  mov     [rsp+78h+var_4C], edi
0x18005b976  lea     rdx, _TI1J; pThrowInfo
0x18005b97d  lea     rcx, [rsp+78h+var_4C]; pExceptionObject
0x18005b982  call    _CxxThrowException_0
0x18005b988  mov     edi, dword ptr [rsp+78h+arg_0]
0x18005b98f  mov     bl, 2
0x18005b991  test    byte ptr cs:_bidGblFlags, bl
0x18005b997  jz      short loc_18005B9B6
0x18005b999  mov     edx, 3C809h
0x18005b99e  mov     r9d, edi
0x18005b9a1  lea     r8, aCreatedpoTrace; "<CreateDPO|Trace|HR> "
0x18005b9a8  mov     rcx, cs:off_1800C8410; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18005b9af  call    _bidTraceHR
0x18005b9b4  mov     edi, eax
0x18005b9b6  mov     eax, edi
0x18005b9b8  lea     r11, [rsp+78h+var_28]
0x18005b9bd  mov     rbx, [r11+38h]
0x18005b9c1  mov     rsi, [r11+40h]
0x18005b9c5  mov     rsp, r11
0x18005b9c8  pop     r15
0x18005b9ca  pop     r14
0x18005b9cc  pop     r13
0x18005b9ce  pop     r12
0x18005b9d0  pop     rdi
0x18005b9d1  retn
```
