# CDSLPropertySupplementSetArray::Initialize(CDSLPropertyInformationSetArray const &,CDSLPropertySetArray const &,int)

- ea: `0x180051f5c`
- end: `0x180052253`
- name: `?Initialize@CDSLPropertySupplementSetArray@@QEAAJAEBVCDSLPropertyInformationSetArray@@AEBVCDSLPropertySetArray@@H@Z`
- size: `759`
- prototype: `__int64 __fastcall(CDSLPropertySupplementSetArray *__hidden this, const struct CDSLPropertyInformationSetArray *, const struct CDSLPropertySetArray *, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x1800555b8`
- `0x18005c7a0`

## callees

- `0x180013870`
- `0x180029560`
- `0x18002ec0c`
- `0x180051f5c`
- `0x180052348`
- `0x18007e6ca`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180051f8b`
- `ole32!CoTaskMemAlloc` at `0x180052054`
- `ole32!CoTaskMemAlloc` at `0x180051f8b`
- `ole32!CoTaskMemAlloc` at `0x180052054`

## pseudocode

```c
__int64 __fastcall CDSLPropertySupplementSetArray::Initialize(
        CDSLPropertySupplementSetArray *this,
        const struct CDSLPropertyInformationSetArray *a2,
        const struct CDSLPropertySetArray *a3,
        int a4)
{
  __int64 v7; // rbx
  void *v8; // rax
  int v9; // edi
  __int64 v10; // r12
  __int64 v11; // rsi
  const struct CDSLProperty **v12; // r13
  unsigned int v13; // edi
  unsigned int v14; // r15d
  CDSLPropertySupplement *v15; // rax
  CDSLPropertySupplement *v16; // r14
  int v17; // edi
  unsigned __int16 v18; // dx
  const struct CDSLProperty *v19; // rcx
  __int64 v20; // rax
  int v21; // r13d
  unsigned int v23; // ebx
  int pExceptionObject; // [rsp+20h] [rbp-58h] BYREF
  int v25; // [rsp+24h] [rbp-54h] BYREF
  unsigned int v26; // [rsp+28h] [rbp-50h] BYREF
  unsigned int v27; // [rsp+2Ch] [rbp-4Ch] BYREF
  const struct CDSLProperty *v28; // [rsp+30h] [rbp-48h]
  const struct CDSLProperty **v30; // [rsp+88h] [rbp+10h]

  v7 = *(unsigned int *)a2;
  v8 = CoTaskMemAlloc(40 * v7);
  try
  {
    *((_QWORD *)this + 1) = v8;
    if ( !v8 )
    {
      v9 = -2147024882;
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(-2147024882, L"<CDSLPropertySupplementSetArray::Initialize|OLEDB|ERR> ", 0x175u);
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(-2147024882, L"<CDSLPropertySupplementSetArray::Initialize|OLEDB|ERR> ", 0x175u);
          if ( (bidGblFlags & 2) != 0 )
            v9 = bidTraceHR(
                   off_1800C83E0[0],
                   381961,
                   L"<CDSLPropertySupplementSetArray::Initialize|Trace|HR> ",
                   2147942414LL);
        }
      }
      pExceptionObject = v9;
      throw (long *)&pExceptionObject;
    }
    memset_0(v8, 0, 40 * v7);
    *(_DWORD *)this = v7;
    v10 = *((_QWORD *)this + 1);
    v11 = *((_QWORD *)a2 + 1);
    v12 = (const struct CDSLProperty **)*((_QWORD *)a3 + 1);
    v30 = v12;
    v13 = 0;
    while ( (_DWORD)v7 )
    {
      v14 = *(_DWORD *)(v11 + 8);
      v15 = (CDSLPropertySupplement *)CoTaskMemAlloc(152LL * v14);
      v16 = v15;
      if ( !v15 )
      {
        v17 = -2147024882;
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(-2147024882, L"<CDSLPropertySupplementSetArray::Initialize|OLEDB|ERR> ", 0x17Eu);
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(-2147024882, L"<CDSLPropertySupplementSetArray::Initialize|OLEDB|ERR> ", 0x17Eu);
            if ( (bidGblFlags & 2) != 0 )
              v17 = bidTraceHR(
                      off_1800C83E0[0],
                      391177,
                      L"<CDSLPropertySupplementSetArray::Initialize|Trace|HR> ",
                      2147942414LL);
          }
        }
        v25 = v17;
        throw (long *)&v25;
      }
      memset_0(v15, 0, 152LL * v14);
      *(_DWORD *)v10 = v14;
      *(_QWORD *)(v10 + 8) = v16;
      v19 = *v12;
      v28 = *v12;
      if ( !a4 )
        goto LABEL_21;
      v20 = *(_QWORD *)(v11 + 12) - *(_QWORD *)&DBPROPSET_DBINIT.Data1;
      if ( !v20 )
        v20 = *(_QWORD *)(v11 + 20) - *(_QWORD *)DBPROPSET_DBINIT.Data4;
      if ( v20 )
LABEL_21:
        v21 = 0;
      else
        v21 = 1;
      v13 = 0;
      while ( v14 )
      {
        v13 = CDSLPropertySupplement::SetInitialProperty(v16, v18, v19, v21);
        if ( (v13 & 0x80000000) != 0 )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(v13, L"<CDSLPropertySupplementSetArray::Initialize|OLEDB|ERR> ", 0x18Fu);
            if ( (bidGblFlags & 2) != 0 )
            {
              OLEDBTraceErr(v13, L"<CDSLPropertySupplementSetArray::Initialize|OLEDB|ERR> ", 0x18Fu);
              if ( (bidGblFlags & 2) != 0 )
                v13 = bidTraceHR(
                        off_1800C83E0[0],
                        408585,
                        L"<CDSLPropertySupplementSetArray::Initialize|Trace|HR> ",
                        v13);
            }
          }
          v26 = v13;
          throw (long *)&v26;
        }
        --v14;
        v16 = (CDSLPropertySupplement *)((char *)v16 + 152);
        v19 = (const struct CDSLProperty *)((char *)v28 + 72);
        v28 = (const struct CDSLProperty *)((char *)v28 + 72);
      }
      LODWORD(v7) = v7 - 1;
      *(_OWORD *)(v10 + 16) = *(_OWORD *)(v11 + 12);
      v10 += 40;
      v11 += 32;
      v30 += 4;
      v12 = v30;
    }
  }
  catch ( long v27 )
  {
    if ( (bidGblFlags & 2) != 0 && off_1800C8868[0] )
    {
      v23 = v27;
      bidTraceA(off_1800C83E0[0], 424960, off_1800C8868[0], v27);
    }
    else
    {
      v23 = v27;
    }
    TDSLSetArray<CDSLPropertySupplementSet,CDSLPropertySupplement>::Free(this);
    v13 = v23;
  }
  if ( (bidGblFlags & 2) != 0 )
    return (unsigned int)bidTraceHR(
                           off_1800C83E0[0],
                           430089,
                           L"<CDSLPropertySupplementSetArray::Initialize|Trace|HR> ",
                           v13);
  return v13;
}

```

## disassembly

```asm
0x180051f5c  mov     [rsp+arg_18], r9d
0x180051f61  mov     [rsp+arg_0], rcx
0x180051f66  push    rbx
0x180051f67  push    rsi
0x180051f68  push    rdi
0x180051f69  push    r12
0x180051f6b  push    r13
0x180051f6d  push    r14
0x180051f6f  push    r15
0x180051f71  sub     rsp, 40h
0x180051f75  mov     r15, r8
0x180051f78  mov     r14, rdx
0x180051f7b  mov     rdi, rcx
0x180051f7e  mov     ebx, [rdx]
0x180051f80  lea     rsi, [rbx+rbx*4]
0x180051f84  shl     rsi, 3
0x180051f88  mov     rcx, rsi; cb
0x180051f8b  call    cs:__imp_CoTaskMemAlloc
0x180051f91  mov     [rdi+8], rax
0x180051f95  test    rax, rax
0x180051f98  jnz     short loc_180052019
0x180051f9a  mov     eax, cs:_bidGblFlags
0x180051fa0  mov     bl, 2
0x180051fa2  mov     edi, 8007000Eh
0x180051fa7  test    bl, al
0x180051fa9  jz      short loc_180052004
0x180051fab  mov     r8d, 175h; unsigned int
0x180051fb1  lea     rdx, aCdslpropertysu_3; "<CDSLPropertySupplementSetArray::Initia"...
0x180051fb8  mov     ecx, edi; int
0x180051fba  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180051fbf  mov     eax, cs:_bidGblFlags
0x180051fc5  test    bl, al
0x180051fc7  jz      short loc_180052004
0x180051fc9  mov     r8d, 175h; unsigned int
0x180051fcf  lea     rdx, aCdslpropertysu_3; "<CDSLPropertySupplementSetArray::Initia"...
0x180051fd6  mov     ecx, edi; int
0x180051fd8  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180051fdd  mov     eax, cs:_bidGblFlags
0x180051fe3  test    bl, al
0x180051fe5  jz      short loc_180052004
0x180051fe7  mov     r9d, edi
0x180051fea  lea     r8, aCdslpropertysu; "<CDSLPropertySupplementSetArray::Initia"...
0x180051ff1  mov     edx, 5D409h
0x180051ff6  mov     rcx, cs:off_1800C83E0; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x180051ffd  call    _bidTraceHR
0x180052002  mov     edi, eax
0x180052004  mov     [rsp+78h+pExceptionObject], edi
0x180052008  lea     rdx, _TI1J; pThrowInfo
0x18005200f  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x180052014  call    _CxxThrowException_0
0x180052019  mov     r8, rsi; Size
0x18005201c  xor     edx, edx; Val
0x18005201e  mov     rcx, rax; void *
0x180052021  call    memset_0
0x180052026  mov     [rdi], ebx
0x180052028  mov     r12, [rdi+8]
0x18005202c  mov     rsi, [r14+8]
0x180052030  mov     r13, [r15+8]
0x180052034  mov     [rsp+78h+arg_8], r13
0x18005203c  xor     edi, edi
0x18005203e  test    ebx, ebx
0x180052040  jz      loc_180052211
0x180052046  mov     r15d, [rsi+8]
0x18005204a  imul    rdi, r15, 98h
0x180052051  mov     rcx, rdi; cb
0x180052054  call    cs:__imp_CoTaskMemAlloc
0x18005205a  mov     r14, rax
0x18005205d  test    rax, rax
0x180052060  jnz     short loc_1800520E1
0x180052062  mov     eax, cs:_bidGblFlags
0x180052068  mov     bl, 2
0x18005206a  mov     edi, 8007000Eh
0x18005206f  test    bl, al
0x180052071  jz      short loc_1800520CC
0x180052073  mov     r8d, 17Eh; unsigned int
0x180052079  lea     rdx, aCdslpropertysu_3; "<CDSLPropertySupplementSetArray::Initia"...
0x180052080  mov     ecx, edi; int
0x180052082  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180052087  mov     eax, cs:_bidGblFlags
0x18005208d  test    bl, al
0x18005208f  jz      short loc_1800520CC
0x180052091  mov     r8d, 17Eh; unsigned int
0x180052097  lea     rdx, aCdslpropertysu_3; "<CDSLPropertySupplementSetArray::Initia"...
0x18005209e  mov     ecx, edi; int
0x1800520a0  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x1800520a5  mov     eax, cs:_bidGblFlags
0x1800520ab  test    bl, al
0x1800520ad  jz      short loc_1800520CC
0x1800520af  mov     r9d, edi
0x1800520b2  lea     r8, aCdslpropertysu; "<CDSLPropertySupplementSetArray::Initia"...
0x1800520b9  mov     edx, 5F809h
0x1800520be  mov     rcx, cs:off_1800C83E0; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x1800520c5  call    _bidTraceHR
0x1800520ca  mov     edi, eax
0x1800520cc  mov     [rsp+78h+var_54], edi
0x1800520d0  lea     rdx, _TI1J; pThrowInfo
0x1800520d7  lea     rcx, [rsp+78h+var_54]; pExceptionObject
0x1800520dc  call    _CxxThrowException_0
0x1800520e1  mov     r8, rdi; Size
0x1800520e4  xor     edx, edx; Val
0x1800520e6  mov     rcx, r14; void *
0x1800520e9  call    memset_0
0x1800520ee  mov     [r12], r15d
0x1800520f2  mov     [r12+8], r14
0x1800520f7  mov     rcx, [r13+0]
0x1800520fb  mov     [rsp+78h+var_48], rcx
0x180052100  cmp     [rsp+78h+arg_18], 0
0x180052108  jz      short loc_18005212D
0x18005210a  mov     rax, [rsi+0Ch]
0x18005210e  sub     rax, qword ptr cs:DBPROPSET_DBINIT.Data1
0x180052115  jnz     short loc_180052122
0x180052117  mov     rax, [rsi+14h]
0x18005211b  sub     rax, qword ptr cs:DBPROPSET_DBINIT.Data4
0x180052122  test    rax, rax
0x180052125  jnz     short loc_18005212D
0x180052127  lea     r13d, [rax+1]
0x18005212b  jmp     short loc_180052130
0x18005212d  xor     r13d, r13d
0x180052130  xor     edi, edi
0x180052132  test    r15d, r15d
0x180052135  jz      loc_1800521E6
0x18005213b  mov     r9d, r13d; int
0x18005213e  mov     r8, rcx; struct CDSLProperty *
0x180052141  mov     rcx, r14; this
0x180052144  call    ?SetInitialProperty@CDSLPropertySupplement@@QEAAJGAEBVCDSLProperty@@H@Z; CDSLPropertySupplement::SetInitialProperty(ushort,CDSLProperty const &,int)
0x180052149  mov     edi, eax
0x18005214b  test    eax, eax
0x18005214d  jns     short loc_1800521C9
0x18005214f  mov     eax, cs:_bidGblFlags
0x180052155  mov     bl, 2
0x180052157  test    bl, al
0x180052159  jz      short loc_1800521B4
0x18005215b  mov     r8d, 18Fh; unsigned int
0x180052161  lea     rdx, aCdslpropertysu_3; "<CDSLPropertySupplementSetArray::Initia"...
0x180052168  mov     ecx, edi; int
0x18005216a  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18005216f  mov     eax, cs:_bidGblFlags
0x180052175  test    bl, al
0x180052177  jz      short loc_1800521B4
0x180052179  mov     r8d, 18Fh; unsigned int
0x18005217f  lea     rdx, aCdslpropertysu_3; "<CDSLPropertySupplementSetArray::Initia"...
0x180052186  mov     ecx, edi; int
0x180052188  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18005218d  mov     eax, cs:_bidGblFlags
0x180052193  test    bl, al
0x180052195  jz      short loc_1800521B4
0x180052197  mov     r9d, edi
0x18005219a  lea     r8, aCdslpropertysu; "<CDSLPropertySupplementSetArray::Initia"...
0x1800521a1  mov     edx, 63C09h
0x1800521a6  mov     rcx, cs:off_1800C83E0; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x1800521ad  call    _bidTraceHR
0x1800521b2  mov     edi, eax
0x1800521b4  mov     [rsp+78h+var_50], edi
0x1800521b8  lea     rdx, _TI1J; pThrowInfo
0x1800521bf  lea     rcx, [rsp+78h+var_50]; pExceptionObject
0x1800521c4  call    _CxxThrowException_0
0x1800521c9  dec     r15d
0x1800521cc  add     r14, 98h
0x1800521d3  mov     rcx, [rsp+78h+var_48]
0x1800521d8  add     rcx, 48h ; 'H'
0x1800521dc  mov     [rsp+78h+var_48], rcx
0x1800521e1  jmp     loc_180052132
0x1800521e6  dec     ebx
0x1800521e8  movups  xmm0, xmmword ptr [rsi+0Ch]
0x1800521ec  movdqu  xmmword ptr [r12+10h], xmm0
0x1800521f3  add     r12, 28h ; '('
0x1800521f7  add     rsi, 20h ; ' '
0x1800521fb  add     [rsp+78h+arg_8], 20h ; ' '
0x180052204  mov     r13, [rsp+78h+arg_8]
0x18005220c  jmp     loc_18005203E
0x180052211  jmp     short loc_18005221A
0x180052213  mov     edi, dword ptr [rsp+78h+arg_8]
0x18005221a  mov     bl, 2
0x18005221c  test    byte ptr cs:_bidGblFlags, bl
0x180052222  jz      short loc_180052241
0x180052224  mov     r9d, edi
0x180052227  lea     r8, aCdslpropertysu; "<CDSLPropertySupplementSetArray::Initia"...
0x18005222e  mov     edx, 69009h
0x180052233  mov     rcx, cs:off_1800C83E0; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18005223a  call    _bidTraceHR
0x18005223f  mov     edi, eax
0x180052241  mov     eax, edi
0x180052243  add     rsp, 40h
0x180052247  pop     r15
0x180052249  pop     r14
0x18005224b  pop     r13
0x18005224d  pop     r12
0x18005224f  pop     rdi
0x180052250  pop     rsi
0x180052251  pop     rbx
0x180052252  retn
```
