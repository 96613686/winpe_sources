# CCompiledInitString::SetNonExtendedProperties(CCMProviderInfo *,CDSLPropertySetArray &,int)

- ea: `0x180015170`
- end: `0x1800154fd`
- name: `?SetNonExtendedProperties@CCompiledInitString@@QEAAJPEAVCCMProviderInfo@@AEAVCDSLPropertySetArray@@H@Z`
- size: `909`
- prototype: `__int64 __fastcall(CCompiledInitString *__hidden this, struct CCMProviderInfo *, struct CDSLPropertySetArray *, int)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180014970`
- `0x18005d070`

## callees

- `0x180011034`
- `0x180013870`
- `0x180015170`
- `0x180029560`
- `0x180037d64`
- `0x180049f18`
- `0x18004a084`
- `0x180078108`
- `0x18007e700`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800152a6`
- `OLEAUT32!__imp_VariantInit` at `0x1800152c2`
- `OLEAUT32!__imp_VariantInit` at `0x1800152a6`
- `OLEAUT32!__imp_VariantInit` at `0x1800152c2`
- `OLEAUT32!__imp_VariantClear` at `0x18001530f`
- `OLEAUT32!__imp_VariantClear` at `0x18001530f`
- `OLEAUT32!__imp_VariantCopy` at `0x1800152b8`
- `OLEAUT32!__imp_VariantCopy` at `0x1800152b8`

## string_xrefs

- `0x1800151c9`: `<CCompiledInitString::SetNonExtendedProperties|OLEDB|ERR> `
- `0x1800153ee`: `<CCompiledInitString::SetNonExtendedProperties|OLEDB|ERR> `
- `0x1800154b3`: `<CCompiledInitString::SetNonExtendedProperties|OLEDB|ERR> `
- `0x1800151e8`: `<CCompiledInitString::SetNonExtendedProperties|Trace|HR> `

## pseudocode

```c
__int64 __fastcall CCompiledInitString::SetNonExtendedProperties(
        CCompiledInitString *this,
        struct CCMProviderInfo *a2,
        struct CDSLPropertySetArray *a3,
        int a4)
{
  int v4; // r11d
  struct CDSLPropertySetArray *v5; // r9
  struct CCMProviderInfo *v6; // r10
  unsigned int v7; // ebx
  unsigned int v9; // eax
  int v10; // r14d
  __int64 v11; // r13
  int v12; // esi
  unsigned int v13; // edx
  _DWORD *v14; // rdx
  __int64 v15; // r8
  __int64 v16; // r8
  __int64 v17; // r9
  __int64 v18; // r12
  __int64 v19; // rdi
  __int64 v20; // rbx
  const struct CDSLPropertyInformation *v21; // rdi
  VARIANTARG *v22; // rbx
  __int64 v23; // rax
  int v24; // eax
  unsigned int v25; // r8d
  __int64 v26; // rax
  __int64 v27; // r10
  __int64 v28; // r9
  __int64 v29; // rdx
  __int64 v30; // rax
  unsigned int v31; // [rsp+20h] [rbp-A9h]
  unsigned int v35; // [rsp+38h] [rbp-91h]
  struct CDSLPropertyInformation *v36; // [rsp+40h] [rbp-89h]
  __int64 v37; // [rsp+48h] [rbp-81h] BYREF
  VARIANTARG v39; // [rsp+58h] [rbp-71h] BYREF
  VARIANTARG pvarg; // [rsp+70h] [rbp-59h] BYREF
  int v41; // [rsp+90h] [rbp-39h] BYREF
  __int64 v42; // [rsp+94h] [rbp-35h]
  __int128 v43; // [rsp+A0h] [rbp-29h]
  __int128 v44; // [rsp+B0h] [rbp-19h]
  struct tagVARIANT v45; // [rsp+C0h] [rbp-9h] BYREF

  v4 = a4;
  v5 = a3;
  v6 = a2;
  if ( a2 )
  {
    v9 = *((_DWORD *)this + 5);
    v10 = 0;
    v11 = *((_QWORD *)this + 1);
    v12 = 0;
    v31 = v9;
    v13 = 0;
    while ( 1 )
    {
      v35 = v13;
      if ( v13 >= v9 )
      {
        if ( v10 )
          return v12 != 0 ? 0x40EDA : 0;
        else
          return v12 != 0 ? 0x80040E21 : 0;
      }
      v14 = (_DWORD *)(v11 + 52);
      if ( *(_DWORD *)(v11 + 48) != -1 || *v14 != -1 )
        break;
LABEL_39:
      v13 = v35 + 1;
      v11 += 56;
    }
    v15 = *(unsigned int *)(v11 + 48);
    v37 = *(_QWORD *)(v11 + 32);
    v16 = 32 * v15;
    if ( *(_DWORD *)(v11 + 40) )
    {
      v17 = (unsigned int)*v14;
      v18 = *((_QWORD *)v6 + 137) + v16;
      v36 = (struct CDSLPropertyInformation *)(48 * v17 + *(_QWORD *)v18);
      if ( (*((_DWORD *)v36 + 3) & 0x400) != 0 )
      {
        v21 = (const struct CDSLPropertyInformation *)(48 * v17 + *(_QWORD *)v18);
      }
      else
      {
        v19 = 9 * v17;
        v20 = *(_QWORD *)(*((_QWORD *)v6 + 152) + v16);
        memset(&pvarg, 0, sizeof(pvarg));
        VariantInit(&pvarg);
        VariantCopy(&pvarg, (const VARIANTARG *)(v20 + 8 * (v19 + 6)));
        VariantInit(&v39);
        ATL::CComVariant::InternalCopy((ATL::CComVariant *)&v39, &pvarg);
        v21 = v36;
        v43 = 0;
        v44 = 0;
        v41 = *((_DWORD *)v36 + 2);
        *(_OWORD *)&v45.decVal.scale = *(_OWORD *)&v39.decVal.scale;
        v45.vt = v39.vt;
        v45.pRecInfo = v39.pRecInfo;
        v42 = 0;
        VariantClear(&v39);
        if ( CopyValueFromInitString(
               (const struct SStringSegment *)&v37,
               v36,
               (const struct _GUID *)(v18 + 12),
               (struct CDSLProperty *)&v41) < 0
          || v45.vt && !VariantCompare(&pvarg, &v45) )
        {
          goto LABEL_15;
        }
      }
      v22 = (VARIANTARG *)(*(_QWORD *)(32LL * *(unsigned int *)(v11 + 48) + *((_QWORD *)a3 + 1))
                         + 72LL * *(unsigned int *)(v11 + 52));
      if ( CopyValueFromInitString(
             (const struct SStringSegment *)&v37,
             v21,
             (const struct _GUID *)(v18 + 12),
             (struct CDSLProperty *)v22) < 0 )
      {
        v7 = -2147217805;
        if ( (bidGblFlags & 2) != 0 )
          OLEDBTraceErr(-2147217805, L"<CCompiledInitString::SetNonExtendedProperties|OLEDB|ERR> ", 0x41Eu);
        return v7;
      }
      v4 = a4;
      v22->decVal.Hi32 = 0;
      if ( !a4 )
        goto LABEL_27;
      v23 = *(_QWORD *)(v18 + 12) - *(_QWORD *)&DBPROPSET_DBINIT.Data1;
      if ( !v23 )
        v23 = *(_QWORD *)(v18 + 20) - *(_QWORD *)DBPROPSET_DBINIT.Data4;
      if ( v23 || *(_DWORD *)&v22->vt != 9 )
      {
LABEL_27:
        ++v10;
        goto LABEL_38;
      }
      v24 = CDSLComVariant::EncryptBSTRValue(v22 + 2);
      if ( v24 < 0 )
      {
        if ( (bidGblFlags & 2) == 0 )
        {
LABEL_15:
          v4 = a4;
          ++v12;
LABEL_38:
          v9 = v31;
          v5 = a3;
          v6 = a2;
          goto LABEL_39;
        }
        v25 = 1069;
LABEL_26:
        OLEDBTraceErr(v24, L"<CCompiledInitString::SetNonExtendedProperties|OLEDB|ERR> ", v25);
        goto LABEL_15;
      }
    }
    else
    {
      v26 = (unsigned int)*v14;
      v27 = *((_QWORD *)v6 + 137);
      v28 = *(_QWORD *)(*((_QWORD *)v5 + 1) + v16);
      v29 = 9 * v26;
      *(_DWORD *)(v28 + 72 * v26 + 4) = 0;
      if ( v4 )
        goto LABEL_37;
      v30 = *(_QWORD *)(v27 + v16 + 12) - *(_QWORD *)&DBPROPSET_DBINIT.Data1;
      if ( !v30 )
        v30 = *(_QWORD *)(v27 + v16 + 20) - *(_QWORD *)DBPROPSET_DBINIT.Data4;
      if ( v30 || *(_DWORD *)(v28 + 8 * v29) != 9 )
        goto LABEL_37;
      v24 = CDSLComVariant::DecryptBSTRValue((VARIANTARG *)(v28 + 8 * (v29 + 6)));
      if ( v24 < 0 )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_15;
        v25 = 1096;
        goto LABEL_26;
      }
    }
    v4 = a4;
LABEL_37:
    ++v10;
    goto LABEL_38;
  }
  v7 = -2147467261;
  if ( (bidGblFlags & 2) != 0 )
  {
    OLEDBTraceErr(-2147467261, L"<CCompiledInitString::SetNonExtendedProperties|OLEDB|ERR> ", 0x3E1u);
    if ( (bidGblFlags & 2) != 0 )
      return (unsigned int)bidTraceHR(
                             off_1800C8430[0],
                             1016841,
                             L"<CCompiledInitString::SetNonExtendedProperties|Trace|HR> ",
                             2147500035LL);
  }
  return v7;
}

```

## disassembly

```asm
0x180015170  push    rbp
0x180015172  push    rbx
0x180015173  push    rsi
0x180015174  push    rdi
0x180015175  push    r12
0x180015177  push    r13
0x180015179  push    r14
0x18001517b  lea     rbp, [rsp-27h]
0x180015180  sub     rsp, 0F0h
0x180015187  mov     rax, cs:__security_cookie
0x18001518e  xor     rax, rsp
0x180015191  mov     [rbp+57h+var_40], rax
0x180015195  xor     ebx, ebx
0x180015197  mov     [rsp+120h+var_FC], r9d
0x18001519c  mov     [rsp+120h+var_F8], r8
0x1800151a1  mov     r11d, r9d
0x1800151a4  mov     [rsp+120h+var_F0], rdx
0x1800151a9  mov     r9, r8
0x1800151ac  mov     r10, rdx
0x1800151af  test    rdx, rdx
0x1800151b2  jnz     short loc_180015205
0x1800151b4  mov     eax, cs:_bidGblFlags
0x1800151ba  mov     ebx, 80004003h
0x1800151bf  test    al, 2
0x1800151c1  jz      short loc_1800151FE
0x1800151c3  mov     r8d, 3E1h; unsigned int
0x1800151c9  lea     rdx, aCcompiledinits_11; "<CCompiledInitString::SetNonExtendedPro"...
0x1800151d0  mov     ecx, ebx; int
0x1800151d2  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x1800151d7  mov     eax, cs:_bidGblFlags
0x1800151dd  test    al, 2
0x1800151df  jz      short loc_1800151FE
0x1800151e1  mov     rcx, cs:off_1800C8430; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x1800151e8  lea     r8, aCcompiledinits_7; "<CCompiledInitString::SetNonExtendedPro"...
0x1800151ef  mov     r9d, ebx
0x1800151f2  mov     edx, 0F8409h
0x1800151f7  call    _bidTraceHR
0x1800151fc  mov     ebx, eax
0x1800151fe  mov     eax, ebx
0x180015200  jmp     loc_1800154DF
0x180015205  mov     eax, [rcx+14h]
0x180015208  mov     r14d, ebx
0x18001520b  mov     r13, [rcx+8]
0x18001520f  mov     esi, ebx
0x180015211  mov     [rsp+120h+var_100], eax
0x180015215  mov     edx, ebx
0x180015217  mov     [rsp+120h+var_E8], edx
0x18001521b  cmp     edx, eax
0x18001521d  jnb     loc_1800154C6
0x180015223  cmp     dword ptr [r13+30h], 0FFFFFFFFh
0x180015228  lea     rdx, [r13+34h]
0x18001522c  jnz     short loc_180015237
0x18001522e  cmp     dword ptr [rdx], 0FFFFFFFFh
0x180015231  jz      loc_18001548C
0x180015237  mov     rax, [r13+20h]
0x18001523b  mov     r8d, [r13+30h]
0x18001523f  mov     [rsp+120h+var_D8], rax
0x180015244  mov     eax, [r13+28h]
0x180015248  shl     r8, 5
0x18001524c  mov     [rbp+57h+var_D0], eax
0x18001524f  test    eax, eax
0x180015251  jz      loc_180015408
0x180015257  mov     r9d, [rdx]
0x18001525a  mov     rdx, [r10+448h]
0x180015261  lea     rcx, [r9+r9*2]
0x180015265  mov     rax, [rdx+r8]
0x180015269  lea     r12, [rdx+r8]
0x18001526d  shl     rcx, 4
0x180015271  add     rax, rcx
0x180015274  mov     [rsp+120h+var_E0], rax
0x180015279  test    dword ptr [rax+0Ch], 400h
0x180015280  jnz     loc_180015352
0x180015286  mov     rax, [r10+4C0h]
0x18001528d  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180015291  xorps   xmm0, xmm0
0x180015294  lea     rdi, [r9+r9*8]
0x180015298  mov     rbx, [rax+r8]
0x18001529c  xor     eax, eax
0x18001529e  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x1800152a2  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x1800152a6  call    cs:__imp_VariantInit
0x1800152ac  lea     rdi, [rdi+6]
0x1800152b0  lea     rdx, [rbx+rdi*8]; pvargSrc
0x1800152b4  lea     rcx, [rbp+57h+pvarg]; pvargDest
0x1800152b8  call    cs:__imp_VariantCopy
0x1800152be  lea     rcx, [rbp+57h+var_C8]; pvarg
0x1800152c2  call    cs:__imp_VariantInit
0x1800152c8  lea     rdx, [rbp+57h+pvarg]; struct tagVARIANT *
0x1800152cc  lea     rcx, [rbp+57h+var_C8]; this
0x1800152d0  call    ?InternalCopy@CComVariant@ATL@@QEAAXPEBUtagVARIANT@@@Z; ATL::CComVariant::InternalCopy(tagVARIANT const *)
0x1800152d5  movsd   xmm1, qword ptr [rbp+57h+var_C8+10h]
0x1800152da  lea     rcx, [rbp+57h+var_C8]; pvarg
0x1800152de  mov     rdi, [rsp+120h+var_E0]
0x1800152e3  xorps   xmm0, xmm0
0x1800152e6  movups  [rbp+57h+var_80], xmm0
0x1800152ea  xor     ebx, ebx
0x1800152ec  movups  [rbp+57h+var_70], xmm0
0x1800152f0  mov     eax, [rdi+8]
0x1800152f3  movups  xmm0, xmmword ptr [rbp-6Fh]
0x1800152f7  mov     [rbp+57h+var_90], eax
0x1800152fa  movzx   eax, word ptr [rbp+57h+var_C8]
0x1800152fe  movups  xmmword ptr [rbp+57h+var_60+2], xmm0
0x180015302  mov     word ptr [rbp+57h+var_60], ax
0x180015306  movsd   qword ptr [rbp+57h+var_60+10h], xmm1
0x18001530b  mov     [rbp+57h+var_8C], rbx
0x18001530f  call    cs:__imp_VariantClear
0x180015315  lea     r9, [rbp+57h+var_90]; struct CDSLProperty *
0x180015319  mov     rdx, rdi; struct CDSLPropertyInformation *
0x18001531c  lea     r8, [r12+0Ch]; struct _GUID *
0x180015321  lea     rcx, [rsp+120h+var_D8]; struct SStringSegment *
0x180015326  call    ?CopyValueFromInitString@@YAJAEBUSStringSegment@@AEBVCDSLPropertyInformation@@AEBU_GUID@@AEAVCDSLProperty@@@Z; CopyValueFromInitString(SStringSegment const &,CDSLPropertyInformation const &,_GUID const &,CDSLProperty &)
0x18001532b  test    eax, eax
0x18001532d  js      short loc_180015346
0x18001532f  cmp     word ptr [rbp+57h+var_60], bx
0x180015333  jz      short loc_180015355
0x180015335  lea     rdx, [rbp+57h+var_60]; struct tagVARIANT *
0x180015339  lea     rcx, [rbp+57h+pvarg]; struct tagVARIANT *
0x18001533d  call    ?VariantCompare@@YA_NPEBUtagVARIANT@@0@Z; VariantCompare(tagVARIANT const *,tagVARIANT const *)
0x180015342  test    al, al
0x180015344  jnz     short loc_180015355
0x180015346  mov     r11d, [rsp+120h+var_FC]
0x18001534b  inc     esi
0x18001534d  jmp     loc_18001547E
0x180015352  mov     rdi, rax
0x180015355  mov     eax, [r13+34h]
0x180015359  mov     rdx, rdi; struct CDSLPropertyInformation *
0x18001535c  mov     r9d, [r13+30h]
0x180015360  mov     r8, [rsp+120h+var_F8]
0x180015365  shl     r9, 5
0x180015369  lea     rcx, [rax+rax*8]
0x18001536d  mov     r8, [r8+8]
0x180015371  mov     rax, [r9+r8]
0x180015375  lea     r8, [r12+0Ch]; struct _GUID *
0x18001537a  lea     rbx, [rax+rcx*8]
0x18001537e  mov     r9, rbx; struct CDSLProperty *
0x180015381  lea     rcx, [rsp+120h+var_D8]; struct SStringSegment *
0x180015386  call    ?CopyValueFromInitString@@YAJAEBUSStringSegment@@AEBVCDSLPropertyInformation@@AEBU_GUID@@AEAVCDSLProperty@@@Z; CopyValueFromInitString(SStringSegment const &,CDSLPropertyInformation const &,_GUID const &,CDSLProperty &)
0x18001538b  test    eax, eax
0x18001538d  js      loc_18001549B
0x180015393  mov     r11d, [rsp+120h+var_FC]
0x180015398  mov     dword ptr [rbx+4], 0
0x18001539f  test    r11d, r11d
0x1800153a2  jz      short loc_180015401
0x1800153a4  mov     rax, [r12+0Ch]
0x1800153a9  sub     rax, qword ptr cs:DBPROPSET_DBINIT.Data1
0x1800153b0  jnz     short loc_1800153BE
0x1800153b2  mov     rax, [r12+14h]
0x1800153b7  sub     rax, qword ptr cs:DBPROPSET_DBINIT.Data4
0x1800153be  test    rax, rax
0x1800153c1  jnz     short loc_180015401
0x1800153c3  cmp     dword ptr [rbx], 9
0x1800153c6  jnz     short loc_180015401
0x1800153c8  lea     rcx, [rbx+30h]; pvarg
0x1800153cc  call    ?EncryptBSTRValue@CDSLComVariant@@QEAAJXZ; CDSLComVariant::EncryptBSTRValue(void)
0x1800153d1  xor     ebx, ebx
0x1800153d3  test    eax, eax
0x1800153d5  jns     loc_180015476
0x1800153db  test    byte ptr cs:_bidGblFlags, 2
0x1800153e2  jz      loc_180015346
0x1800153e8  mov     r8d, 42Dh; unsigned int
0x1800153ee  lea     rdx, aCcompiledinits_11; "<CCompiledInitString::SetNonExtendedPro"...
0x1800153f5  mov     ecx, eax; int
0x1800153f7  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x1800153fc  jmp     loc_180015346
0x180015401  inc     r14d
0x180015404  xor     ebx, ebx
0x180015406  jmp     short loc_18001547E
0x180015408  mov     rcx, [r9+8]
0x18001540c  mov     eax, [rdx]
0x18001540e  mov     r10, [r10+448h]
0x180015415  mov     r9, [rcx+r8]
0x180015419  lea     rdx, [rax+rax*8]
0x18001541d  mov     [r9+rdx*8+4], ebx
0x180015422  test    r11d, r11d
0x180015425  jnz     short loc_18001547B
0x180015427  mov     rax, [r10+r8+0Ch]
0x18001542c  sub     rax, qword ptr cs:DBPROPSET_DBINIT.Data1
0x180015433  jnz     short loc_180015441
0x180015435  mov     rax, [r10+r8+14h]
0x18001543a  sub     rax, qword ptr cs:DBPROPSET_DBINIT.Data4
0x180015441  test    rax, rax
0x180015444  jnz     short loc_18001547B
0x180015446  cmp     dword ptr [r9+rdx*8], 9
0x18001544b  jnz     short loc_18001547B
0x18001544d  add     rdx, 6
0x180015451  lea     rcx, [r9+rdx*8]; pvarg
0x180015455  call    ?DecryptBSTRValue@CDSLComVariant@@QEAAJXZ; CDSLComVariant::DecryptBSTRValue(void)
0x18001545a  test    eax, eax
0x18001545c  jns     short loc_180015476
0x18001545e  test    byte ptr cs:_bidGblFlags, 2
0x180015465  jz      loc_180015346
0x18001546b  mov     r8d, 448h
0x180015471  jmp     loc_1800153EE
0x180015476  mov     r11d, [rsp+120h+var_FC]
0x18001547b  inc     r14d
0x18001547e  mov     eax, [rsp+120h+var_100]
0x180015482  mov     r9, [rsp+120h+var_F8]
0x180015487  mov     r10, [rsp+120h+var_F0]
0x18001548c  mov     edx, [rsp+120h+var_E8]
0x180015490  inc     edx
0x180015492  add     r13, 38h ; '8'
0x180015496  jmp     loc_180015217
0x18001549b  test    byte ptr cs:_bidGblFlags, 2
0x1800154a2  mov     ebx, 80040E73h
0x1800154a7  jz      loc_1800151FE
0x1800154ad  mov     r8d, 41Eh; unsigned int
0x1800154b3  lea     rdx, aCcompiledinits_11; "<CCompiledInitString::SetNonExtendedPro"...
0x1800154ba  mov     ecx, ebx; int
0x1800154bc  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x1800154c1  jmp     loc_1800151FE
0x1800154c6  test    r14d, r14d
0x1800154c9  jz      short loc_1800154D6
0x1800154cb  neg     esi
0x1800154cd  sbb     eax, eax
0x1800154cf  and     eax, 40EDAh
0x1800154d4  jmp     short loc_1800154DF
0x1800154d6  neg     esi
0x1800154d8  sbb     eax, eax
0x1800154da  and     eax, 80040E21h
0x1800154df  mov     rcx, [rbp+57h+var_40]
0x1800154e3  xor     rcx, rsp; StackCookie
0x1800154e6  call    __security_check_cookie
0x1800154eb  add     rsp, 0F0h
0x1800154f2  pop     r14
0x1800154f4  pop     r13
0x1800154f6  pop     r12
0x1800154f8  pop     rdi
0x1800154f9  pop     rsi
0x1800154fa  pop     rbx
0x1800154fb  pop     rbp
0x1800154fc  retn
```
