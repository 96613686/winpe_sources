# CCompiledInitString::SetExtendedProperties(CCMProviderInfo *,CDSLPropertySetArray &,ushort * *,int)

- ea: `0x180062670`
- end: `0x18006291c`
- name: `?SetExtendedProperties@CCompiledInitString@@QEAAJPEAVCCMProviderInfo@@AEAVCDSLPropertySetArray@@PEAPEAGH@Z`
- size: `684`
- prototype: `__int64 __fastcall(CCompiledInitString *__hidden this, struct CCMProviderInfo *, struct CDSLPropertySetArray *, unsigned __int16 **, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180014970`
- `0x18005d070`

## callees

- `0x18000faf0`
- `0x180011034`
- `0x1800112b0`
- `0x180013870`
- `0x180029560`
- `0x180029694`
- `0x18004a084`
- `0x180062670`
- `0x18007e700`
- `0x18007e7c0`

## import_xrefs

- `MSDART!mpRealloc` at `0x180062787`
- `MSDART!mpRealloc` at `0x180062787`

## string_xrefs

- `0x1800626be`: `<CCompiledInitString::SetExtendedProperties|OLEDB|ERR> `
- `0x180062722`: `<CCompiledInitString::SetExtendedProperties|OLEDB|ERR> `
- `0x1800627ab`: `<CCompiledInitString::SetExtendedProperties|OLEDB|ERR> `
- `0x1800626e2`: `<CCompiledInitString::SetExtendedProperties|Trace|HR> `
- `0x1800628eb`: `<CCompiledInitString::SetExtendedProperties|Trace|HR> `

## pseudocode

```c
int __fastcall CCompiledInitString::SetExtendedProperties(
        CCompiledInitString *this,
        struct CCMProviderInfo *a2,
        struct CDSLPropertySetArray *a3,
        unsigned __int16 **a4,
        int a5)
{
  unsigned int v8; // ebx
  __int64 v9; // rdx
  int result; // eax
  __int64 v11; // r8
  __int64 v12; // rdi
  __int64 v13; // rsi
  __int64 v14; // rcx
  __int64 v15; // r8
  int v16; // r13d
  unsigned __int16 *v17; // rax
  __int64 v18; // rax
  unsigned __int64 v19; // rcx
  __int64 v20; // rax
  unsigned __int64 v21; // rax
  void *v22; // rsp
  __int64 v23; // rdx
  void *v24; // rsp
  __int64 v25; // rdx
  __int64 v26; // r8
  VARIANTARG *v27; // rbx
  __int64 v28; // [rsp+20h] [rbp+0h] BYREF
  int v29; // [rsp+28h] [rbp+8h]
  struct CDSLPropertySetArray *v30; // [rsp+30h] [rbp+10h]

  v30 = a3;
  if ( !a2 )
  {
    v8 = -2147467261;
    if ( (bidGblFlags & 2) == 0 )
      return v8;
    OLEDBTraceErr(-2147467261, L"<CCompiledInitString::SetExtendedProperties|OLEDB|ERR> ", 0x46Bu);
    if ( (bidGblFlags & 2) == 0 )
      return v8;
    v9 = 1158153;
    return bidTraceHR(off_1800C8430[0], v9, L"<CCompiledInitString::SetExtendedProperties|Trace|HR> ", v8);
  }
  if ( *((_DWORD *)a2 + 292) == -1 && *((_DWORD *)a2 + 293) == -1 )
  {
    v8 = -2147217887;
    if ( (bidGblFlags & 2) == 0 )
      return v8;
    OLEDBTraceErr(-2147217887, L"<CCompiledInitString::SetExtendedProperties|OLEDB|ERR> ", 0x46Cu);
    if ( (bidGblFlags & 2) == 0 )
      return v8;
    v9 = 1159177;
    return bidTraceHR(off_1800C8430[0], v9, L"<CCompiledInitString::SetExtendedProperties|Trace|HR> ", v8);
  }
  v11 = (__int64)*a4;
  v28 = 0;
  if ( v11 )
  {
    v12 = -1;
    v13 = -1;
    do
      ++v13;
    while ( *(_WORD *)(v11 + 2 * v13) );
    if ( CCompiledInitString::ContainsExtendedProperties(this) )
    {
      v16 = v13 + *(_DWORD *)(v14 + 136) + 2;
      v17 = (unsigned __int16 *)mpRealloc(v15, 2LL * (unsigned int)(v16 + 1));
      if ( !v17 )
      {
        v8 = -2147024882;
        if ( (bidGblFlags & 2) == 0 )
          return v8;
        OLEDBTraceErr(-2147024882, L"<CCompiledInitString::SetExtendedProperties|OLEDB|ERR> ", 0x47Fu);
        if ( (bidGblFlags & 2) == 0 )
          return v8;
        v9 = 1178633;
        return bidTraceHR(off_1800C8430[0], v9, L"<CCompiledInitString::SetExtendedProperties|Trace|HR> ", v8);
      }
      *a4 = v17;
      StringCchCopyW(&v17[(unsigned int)v13], (unsigned int)(v16 - v13), L";");
      CopyUnQuotedValueString(&(*a4)[(unsigned int)v13 + 1], *((_QWORD *)this + 16));
      v18 = (__int64)*a4;
      v28 = (__int64)*a4;
      do
        ++v12;
      while ( *(_WORD *)(v18 + 2 * v12) );
      v29 = v12;
    }
    else
    {
      v28 = v15;
      v29 = v13;
    }
  }
  else
  {
    v29 = *((_DWORD *)this + 34);
    v19 = 2LL * (unsigned int)(v29 + 1);
    v20 = v19 + 15;
    if ( v19 + 15 < v19 )
      v20 = 0xFFFFFFFFFFFFFF0LL;
    v21 = v20 & 0xFFFFFFFFFFFFFFF0uLL;
    v22 = alloca(v21);
    v23 = *((_QWORD *)this + 16);
    v24 = alloca(v21);
    v28 = (__int64)&v28;
    CopyUnQuotedValueString(&v28, v23);
  }
  v25 = *((unsigned int *)a2 + 293);
  v26 = 32LL * *((unsigned int *)a2 + 292);
  v27 = (VARIANTARG *)(*(_QWORD *)(*((_QWORD *)v30 + 1) + v26) + 72 * v25);
  result = CopyValueFromInitString(
             (const struct SStringSegment *)&v28,
             (const struct CDSLPropertyInformation *)(*(_QWORD *)(*((_QWORD *)a2 + 137) + v26) + 48 * v25),
             &DBPROPSET_DBINIT,
             (struct CDSLProperty *)v27);
  if ( result >= 0 )
  {
    v27->decVal.Hi32 = 0;
    if ( a5 )
      result = CDSLComVariant::EncryptBSTRValue(v27 + 2);
  }
  if ( (bidGblFlags & 2) != 0 )
    return bidTraceHR(
             off_1800C8430[0],
             1227785,
             L"<CCompiledInitString::SetExtendedProperties|Trace|HR> ",
             (unsigned int)result);
  return result;
}

```

## disassembly

```asm
0x180062670  push    rbp
0x180062672  push    rbx
0x180062673  push    rsi
0x180062674  push    rdi
0x180062675  push    r12
0x180062677  push    r13
0x180062679  push    r14
0x18006267b  push    r15
0x18006267d  sub     rsp, 48h
0x180062681  lea     rbp, [rsp+20h]
0x180062686  mov     rax, cs:__security_cookie
0x18006268d  xor     rax, rbp
0x180062690  mov     [rbp+60h+var_48], rax
0x180062694  xor     r13d, r13d
0x180062697  mov     [rbp+60h+var_50], r8
0x18006269b  mov     r12, r9
0x18006269e  mov     r14, rdx
0x1800626a1  mov     r15, rcx
0x1800626a4  test    rdx, rdx
0x1800626a7  jnz     short loc_1800626FA
0x1800626a9  mov     eax, cs:_bidGblFlags
0x1800626af  mov     ebx, 80004003h
0x1800626b4  test    al, 2
0x1800626b6  jz      short loc_1800626F3
0x1800626b8  mov     r8d, 46Bh; unsigned int
0x1800626be  lea     rdx, aCcompiledinits_9; "<CCompiledInitString::SetExtendedProper"...
0x1800626c5  mov     ecx, ebx; int
0x1800626c7  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x1800626cc  mov     eax, cs:_bidGblFlags
0x1800626d2  test    al, 2
0x1800626d4  jz      short loc_1800626F3
0x1800626d6  mov     edx, 11AC09h
0x1800626db  mov     rcx, cs:off_1800C8430; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x1800626e2  lea     r8, aCcompiledinits_0; "<CCompiledInitString::SetExtendedProper"...
0x1800626e9  mov     r9d, ebx
0x1800626ec  call    _bidTraceHR
0x1800626f1  mov     ebx, eax
0x1800626f3  mov     eax, ebx
0x1800626f5  jmp     loc_1800628FF
0x1800626fa  or      eax, 0FFFFFFFFh
0x1800626fd  cmp     [rdx+490h], eax
0x180062703  jnz     short loc_180062741
0x180062705  cmp     [rdx+494h], eax
0x18006270b  jnz     short loc_180062741
0x18006270d  mov     eax, cs:_bidGblFlags
0x180062713  mov     ebx, 80040E21h
0x180062718  test    al, 2
0x18006271a  jz      short loc_1800626F3
0x18006271c  mov     r8d, 46Ch; unsigned int
0x180062722  lea     rdx, aCcompiledinits_9; "<CCompiledInitString::SetExtendedProper"...
0x180062729  mov     ecx, ebx; int
0x18006272b  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180062730  mov     eax, cs:_bidGblFlags
0x180062736  test    al, 2
0x180062738  jz      short loc_1800626F3
0x18006273a  mov     edx, 11B009h
0x18006273f  jmp     short loc_1800626DB
0x180062741  mov     r8, [r9]
0x180062744  mov     [rbp+60h+var_60], r13
0x180062748  test    r8, r8
0x18006274b  jz      loc_18006282F
0x180062751  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180062755  mov     rsi, rdi
0x180062758  inc     rsi
0x18006275b  cmp     [r8+rsi*2], r13w
0x180062760  jnz     short loc_180062758
0x180062762  call    ?ContainsExtendedProperties@CCompiledInitString@@QEBA_NXZ; CCompiledInitString::ContainsExtendedProperties(void)
0x180062767  test    al, al
0x180062769  jz      loc_180062826
0x18006276f  mov     r13d, [rcx+88h]
0x180062776  mov     rcx, r8
0x180062779  add     r13d, 2
0x18006277d  add     r13d, esi
0x180062780  lea     edx, [r13+1]
0x180062784  add     rdx, rdx
0x180062787  call    cs:__imp_mpRealloc
0x18006278d  test    rax, rax
0x180062790  jnz     short loc_1800627D1
0x180062792  mov     eax, cs:_bidGblFlags
0x180062798  mov     ebx, 8007000Eh
0x18006279d  test    al, 2
0x18006279f  jz      loc_1800626F3
0x1800627a5  mov     r8d, 47Fh; unsigned int
0x1800627ab  lea     rdx, aCcompiledinits_9; "<CCompiledInitString::SetExtendedProper"...
0x1800627b2  mov     ecx, ebx; int
0x1800627b4  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x1800627b9  mov     eax, cs:_bidGblFlags
0x1800627bf  test    al, 2
0x1800627c1  jz      loc_1800626F3
0x1800627c7  mov     edx, 11FC09h
0x1800627cc  jmp     loc_1800626DB
0x1800627d1  mov     ebx, esi
0x1800627d3  lea     r8, asc_18009F530; ";"
0x1800627da  sub     r13d, esi
0x1800627dd  mov     [r12], rax
0x1800627e1  mov     edx, r13d; unsigned __int64
0x1800627e4  lea     rcx, [rax+rbx*2]; unsigned __int16 *
0x1800627e8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800627ed  mov     rcx, [r12]
0x1800627f1  mov     r8d, [r15+88h]
0x1800627f8  add     rcx, 2
0x1800627fc  mov     rdx, [r15+80h]
0x180062803  lea     rcx, [rcx+rbx*2]
0x180062807  call    CopyUnQuotedValueString
0x18006280c  mov     rax, [r12]
0x180062810  xor     r13d, r13d
0x180062813  mov     [rbp+60h+var_60], rax
0x180062817  inc     rdi
0x18006281a  cmp     [rax+rdi*2], r13w
0x18006281f  jnz     short loc_180062817
0x180062821  mov     [rbp+60h+var_58], edi
0x180062824  jmp     short loc_180062875
0x180062826  mov     [rbp+60h+var_60], r8
0x18006282a  mov     [rbp+60h+var_58], esi
0x18006282d  jmp     short loc_180062875
0x18006282f  mov     r8d, [rcx+88h]
0x180062836  mov     [rbp+60h+var_58], r8d
0x18006283a  lea     ecx, [r8+1]
0x18006283e  add     rcx, rcx
0x180062841  lea     rax, [rcx+0Fh]
0x180062845  cmp     rax, rcx
0x180062848  ja      short loc_180062854
0x18006284a  mov     rax, 0FFFFFFFFFFFFFF0h
0x180062854  and     rax, 0FFFFFFFFFFFFFFF0h
0x180062858  call    _alloca_probe
0x18006285d  mov     rdx, [r15+80h]
0x180062864  sub     rsp, rax
0x180062867  lea     rcx, [rsp+80h+var_60]
0x18006286c  mov     [rbp+60h+var_60], rcx
0x180062870  call    CopyUnQuotedValueString
0x180062875  mov     edx, [r14+494h]
0x18006287c  mov     r8d, [r14+490h]
0x180062883  mov     rax, [rbp+60h+var_50]
0x180062887  shl     r8, 5
0x18006288b  lea     rcx, [rdx+rdx*8]
0x18006288f  lea     rdx, [rdx+rdx*2]
0x180062893  mov     rax, [rax+8]
0x180062897  shl     rdx, 4
0x18006289b  mov     rax, [rax+r8]
0x18006289f  lea     rbx, [rax+rcx*8]
0x1800628a3  mov     rax, [r14+448h]
0x1800628aa  mov     r9, rbx; struct CDSLProperty *
0x1800628ad  lea     rcx, [rbp+60h+var_60]; struct SStringSegment *
0x1800628b1  add     rdx, [rax+r8]; struct CDSLPropertyInformation *
0x1800628b5  lea     r8, DBPROPSET_DBINIT; struct _GUID *
0x1800628bc  call    ?CopyValueFromInitString@@YAJAEBUSStringSegment@@AEBVCDSLPropertyInformation@@AEBU_GUID@@AEAVCDSLProperty@@@Z; CopyValueFromInitString(SStringSegment const &,CDSLPropertyInformation const &,_GUID const &,CDSLProperty &)
0x1800628c1  test    eax, eax
0x1800628c3  js      short loc_1800628DB
0x1800628c5  mov     [rbx+4], r13d
0x1800628c9  cmp     [rbp+60h+arg_20], r13d
0x1800628d0  jz      short loc_1800628DB
0x1800628d2  lea     rcx, [rbx+30h]; pvarg
0x1800628d6  call    ?EncryptBSTRValue@CDSLComVariant@@QEAAJXZ; CDSLComVariant::EncryptBSTRValue(void)
0x1800628db  test    byte ptr cs:_bidGblFlags, 2
0x1800628e2  jz      short loc_1800628FF
0x1800628e4  mov     rcx, cs:off_1800C8430; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x1800628eb  lea     r8, aCcompiledinits_0; "<CCompiledInitString::SetExtendedProper"...
0x1800628f2  mov     r9d, eax
0x1800628f5  mov     edx, 12BC09h
0x1800628fa  call    _bidTraceHR
0x1800628ff  mov     rcx, [rbp+60h+var_48]
0x180062903  xor     rcx, rbp; StackCookie
0x180062906  call    __security_check_cookie
0x18006290b  lea     rsp, [rbp+28h]
0x18006290f  pop     r15
0x180062911  pop     r14
0x180062913  pop     r13
0x180062915  pop     r12
0x180062917  pop     rdi
0x180062918  pop     rsi
0x180062919  pop     rbx
0x18006291a  pop     rbp
0x18006291b  retn
```
