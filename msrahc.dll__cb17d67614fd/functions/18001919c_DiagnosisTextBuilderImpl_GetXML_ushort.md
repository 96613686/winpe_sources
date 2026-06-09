# DiagnosisTextBuilderImpl::GetXML(ushort * *)

- ea: `0x18001919c`
- end: `0x1800194b9`
- name: `?GetXML@DiagnosisTextBuilderImpl@@QEAAJPEAPEAG@Z`
- size: `797`
- prototype: `__int64 __fastcall(DiagnosisTextBuilderImpl *__hidden this, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000da10`
- `0x180010718`

## callees

- `0x180006b04`
- `0x180018b84`
- `0x180018e58`
- `0x180019034`
- `0x18001919c`
- `0x180019754`
- `0x18001a0c0`
- `0x18001a5a2`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180019233`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180019233`

## string_xrefs

- `0x180019327`: `</Parameters><Extensions>`
- `0x180019363`: `</Extensions></DiagnosticsText>`
- `0x1800193ae`: `<Extension><Name><![CDATA[%s]]></Name><Value><![CDATA[%s]]></Value></Extension>`

## pseudocode

```c
__int64 __fastcall DiagnosisTextBuilderImpl::GetXML(DiagnosisTextBuilderImpl *this, unsigned __int16 **a2)
{
  unsigned int v3; // r13d
  __int64 v4; // rbx
  __int64 v5; // rbx
  unsigned __int16 *v6; // rbx
  unsigned __int16 *v7; // rdi
  unsigned __int64 v8; // r15
  unsigned __int16 *v9; // rax
  unsigned __int16 *v10; // rsi
  __int64 v11; // rax
  __int64 v12; // r11
  __int64 v13; // rax
  __int64 v14; // r11
  __int64 v15; // rax
  __int64 v16; // r11
  __int64 v17; // rax
  __int64 v18; // r11
  __int64 v19; // rax
  __int64 v20; // r11
  __int64 v21; // rax
  __int64 v22; // r11
  __int64 v23; // rax
  __int64 v24; // r11
  ATL::CStringData *v25; // rdi
  __int64 j; // rax
  ATL::CStringData *v27; // rdi
  __int64 i; // rax
  ATL::CAtlException *v30; // [rsp+20h] [rbp-48h] BYREF
  __int64 v31; // [rsp+70h] [rbp+8h] BYREF
  unsigned __int16 **v32; // [rsp+78h] [rbp+10h]
  unsigned __int16 *v33; // [rsp+80h] [rbp+18h] BYREF
  unsigned __int16 *v34; // [rsp+88h] [rbp+20h] BYREF

  v32 = a2;
  v3 = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v34);
  v4 = **((_QWORD **)this + 3);
  try
  {
    while ( v4 != *((_QWORD *)this + 3) )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v31);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        &v31,
        L"<Parameter><Name><![CDATA[%s]]></Name><Value><![CDATA[%s]]></Value></Parameter>",
        *(_QWORD *)(v4 + 32),
        *(_QWORD *)(v4 + 40));
      v27 = (ATL::CStringData *)(v31 - 24);
      ATL::CSimpleStringT<unsigned short,0>::Append(&v34, v31, *(unsigned int *)(v31 - 24 + 8));
      ATL::CStringData::Release(v27);
      if ( !*(_BYTE *)(v4 + 25) )
      {
        if ( *(_BYTE *)(*(_QWORD *)(v4 + 16) + 25LL) )
        {
          for ( i = *(_QWORD *)(v4 + 8); !*(_BYTE *)(i + 25) && v4 == *(_QWORD *)(i + 16); i = *(_QWORD *)(i + 8) )
            v4 = i;
        }
        else
        {
          i = std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>>::_Min();
        }
        v4 = i;
      }
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v33);
    v5 = **((_QWORD **)this + 5);
    while ( v5 != *((_QWORD *)this + 5) )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v31);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        &v31,
        L"<Extension><Name><![CDATA[%s]]></Name><Value><![CDATA[%s]]></Value></Extension>",
        *(_QWORD *)(v5 + 32),
        *(_QWORD *)(v5 + 40));
      v25 = (ATL::CStringData *)(v31 - 24);
      ATL::CSimpleStringT<unsigned short,0>::Append(&v33, v31, *(unsigned int *)(v31 - 24 + 8));
      ATL::CStringData::Release(v25);
      if ( !*(_BYTE *)(v5 + 25) )
      {
        if ( *(_BYTE *)(*(_QWORD *)(v5 + 16) + 25LL) )
        {
          for ( j = *(_QWORD *)(v5 + 8); !*(_BYTE *)(j + 25) && v5 == *(_QWORD *)(j + 16); j = *(_QWORD *)(j + 8) )
            v5 = j;
        }
        else
        {
          j = std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>>::_Min();
        }
        v5 = j;
      }
    }
    v6 = v34;
    v7 = v33;
    v8 = *(int *)(*((_QWORD *)this + 2) - 16LL)
       + *((int *)v34 - 4)
       + (__int64)*((int *)v33 - 4)
       + *(int *)(*((_QWORD *)this + 1) - 16LL)
       + 152LL;
    v9 = (unsigned __int16 *)CoTaskMemAlloc(2 * v8);
    v10 = v9;
    if ( v9 )
    {
      memset_0(v9, 0, 2 * v8);
      StringCchCopyW(v10, v8, L"<DiagnosticsText><Title><![CDATA[");
      v11 = -1;
      do
        ++v11;
      while ( v10[v11] );
      StringCchCopyW(&v10[v11], v8 - v11, *((const unsigned __int16 **)this + 1));
      v13 = v12;
      do
        ++v13;
      while ( v10[v13] );
      StringCchCopyW(&v10[v13], v8 - v13, L"]]></Title><Description><![CDATA[");
      v15 = v14;
      do
        ++v15;
      while ( v10[v15] );
      StringCchCopyW(&v10[v15], v8 - v15, *((const unsigned __int16 **)this + 2));
      v17 = v16;
      do
        ++v17;
      while ( v10[v17] );
      StringCchCopyW(&v10[v17], v8 - v17, L"]]></Description><Parameters>");
      v19 = v18;
      do
        ++v19;
      while ( v10[v19] );
      StringCchCopyW(&v10[v19], v8 - v19, v6);
      v21 = v20;
      do
        ++v21;
      while ( v10[v21] );
      StringCchCopyW(&v10[v21], v8 - v21, L"</Parameters><Extensions>");
      v23 = v22;
      do
        ++v23;
      while ( v10[v23] );
      StringCchCopyW(&v10[v23], v8 - v23, v7);
      do
        ++v24;
      while ( v10[v24] );
      StringCchCopyW(&v10[v24], v8 - v24, L"</Extensions></DiagnosticsText>");
      *v32 = v10;
    }
    else
    {
      v3 = -2147024882;
    }
    ATL::CStringData::Release((ATL::CStringData *)(v7 - 12));
    ATL::CStringData::Release((ATL::CStringData *)(v6 - 12));
  }
  catch ( ATL::CAtlException *v30 )
  {
    LODWORD(v31) = *(_DWORD *)v30;
    return (unsigned int)v31;
  }
  while ( v4 != *((_QWORD *)this + 3) )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v31);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
      &v31,
      L"<Parameter><Name><![CDATA[%s]]></Name><Value><![CDATA[%s]]></Value></Parameter>",
      *(_QWORD *)(v4 + 32),
      *(_QWORD *)(v4 + 40));
    v27 = (ATL::CStringData *)(v31 - 24);
    ATL::CSimpleStringT<unsigned short,0>::Append(&v34, v31, *(unsigned int *)(v31 - 24 + 8));
    ATL::CStringData::Release(v27);
    if ( !*(_BYTE *)(v4 + 25) )
    {
      if ( *(_BYTE *)(*(_QWORD *)(v4 + 16) + 25LL) )
      {
        for ( i = *(_QWORD *)(v4 + 8); !*(_BYTE *)(i + 25) && v4 == *(_QWORD *)(i + 16); i = *(_QWORD *)(i + 8) )
          v4 = i;
      }
      else
      {
        i = std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>>::_Min();
      }
      v4 = i;
    }
  }
}

```

## disassembly

```asm
0x18001919c  mov     rax, rsp
0x18001919f  mov     [rax+10h], rdx
0x1800191a3  push    rbx
0x1800191a4  push    rsi
0x1800191a5  push    rdi
0x1800191a6  push    r12
0x1800191a8  push    r13
0x1800191aa  push    r14
0x1800191ac  push    r15
0x1800191ae  sub     rsp, 30h
0x1800191b2  mov     r14, rcx
0x1800191b5  xor     esi, esi
0x1800191b7  mov     r13d, esi
0x1800191ba  lea     rcx, [rax+20h]
0x1800191be  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800191c3  nop
0x1800191c4  mov     rbx, [r14+18h]
0x1800191c8  mov     rbx, [rbx]
0x1800191cb  cmp     rbx, [r14+18h]
0x1800191cf  jnz     loc_18001941E
0x1800191d5  lea     rcx, [rsp+68h+arg_10]
0x1800191dd  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800191e2  nop
0x1800191e3  mov     rbx, [r14+28h]
0x1800191e7  mov     rbx, [rbx]
0x1800191ea  cmp     rbx, [r14+28h]
0x1800191ee  jnz     loc_18001939B
0x1800191f4  mov     rbx, [rsp+68h+arg_18]
0x1800191fc  mov     rdi, [rsp+68h+arg_10]
0x180019204  movsxd  rdx, dword ptr [rdi-10h]
0x180019208  movsxd  rax, dword ptr [rbx-10h]
0x18001920c  add     rdx, rax
0x18001920f  mov     rax, [r14+10h]
0x180019213  movsxd  rcx, dword ptr [rax-10h]
0x180019217  add     rdx, rcx
0x18001921a  mov     rax, [r14+8]
0x18001921e  movsxd  r15, dword ptr [rax-10h]
0x180019222  add     r15, 98h
0x180019229  add     r15, rdx
0x18001922c  lea     r12, [r15+r15]
0x180019230  mov     rcx, r12; cb
0x180019233  call    cs:__imp_CoTaskMemAlloc
0x180019239  mov     rsi, rax
0x18001923c  test    rax, rax
0x18001923f  jz      loc_18001937C
0x180019245  mov     r8, r12; Size
0x180019248  xor     edx, edx; Val
0x18001924a  mov     rcx, rax; void *
0x18001924d  call    memset_0
0x180019252  lea     r8, aDiagnosticstex; "<DiagnosticsText><Title><![CDATA["
0x180019259  mov     rdx, r15; unsigned __int64
0x18001925c  mov     rcx, rsi; unsigned __int16 *
0x18001925f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180019264  or      r11, 0FFFFFFFFFFFFFFFFh
0x180019268  mov     rax, r11
0x18001926b  xor     r12d, r12d
0x18001926e  inc     rax
0x180019271  cmp     [rsi+rax*2], r12w
0x180019276  jnz     short loc_18001926E
0x180019278  mov     rdx, r15
0x18001927b  sub     rdx, rax; unsigned __int64
0x18001927e  lea     rcx, [rsi+rax*2]; unsigned __int16 *
0x180019282  mov     r8, [r14+8]; unsigned __int16 *
0x180019286  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001928b  mov     rax, r11
0x18001928e  inc     rax
0x180019291  cmp     [rsi+rax*2], r12w
0x180019296  jnz     short loc_18001928E
0x180019298  mov     rdx, r15
0x18001929b  sub     rdx, rax; unsigned __int64
0x18001929e  lea     rcx, [rsi+rax*2]; unsigned __int16 *
0x1800192a2  lea     r8, aTitleDescripti; "]]></Title><Description><![CDATA["
0x1800192a9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800192ae  mov     rax, r11
0x1800192b1  inc     rax
0x1800192b4  cmp     [rsi+rax*2], r12w
0x1800192b9  jnz     short loc_1800192B1
0x1800192bb  mov     rdx, r15
0x1800192be  sub     rdx, rax; unsigned __int64
0x1800192c1  lea     rcx, [rsi+rax*2]; unsigned __int16 *
0x1800192c5  mov     r8, [r14+10h]; unsigned __int16 *
0x1800192c9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800192ce  mov     rax, r11
0x1800192d1  inc     rax
0x1800192d4  cmp     [rsi+rax*2], r12w
0x1800192d9  jnz     short loc_1800192D1
0x1800192db  mov     rdx, r15
0x1800192de  sub     rdx, rax; unsigned __int64
0x1800192e1  lea     rcx, [rsi+rax*2]; unsigned __int16 *
0x1800192e5  lea     r8, aDescriptionPar; "]]></Description><Parameters>"
0x1800192ec  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800192f1  mov     rax, r11
0x1800192f4  inc     rax
0x1800192f7  cmp     [rsi+rax*2], r12w
0x1800192fc  jnz     short loc_1800192F4
0x1800192fe  mov     rdx, r15
0x180019301  sub     rdx, rax; unsigned __int64
0x180019304  lea     rcx, [rsi+rax*2]; unsigned __int16 *
0x180019308  mov     r8, rbx; unsigned __int16 *
0x18001930b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180019310  mov     rax, r11
0x180019313  inc     rax
0x180019316  cmp     [rsi+rax*2], r12w
0x18001931b  jnz     short loc_180019313
0x18001931d  mov     rdx, r15
0x180019320  sub     rdx, rax; unsigned __int64
0x180019323  lea     rcx, [rsi+rax*2]; unsigned __int16 *
0x180019327  lea     r8, aParametersExte; "</Parameters><Extensions>"
0x18001932e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180019333  mov     rax, r11
0x180019336  inc     rax
0x180019339  cmp     [rsi+rax*2], r12w
0x18001933e  jnz     short loc_180019336
0x180019340  mov     rdx, r15
0x180019343  sub     rdx, rax; unsigned __int64
0x180019346  lea     rcx, [rsi+rax*2]; unsigned __int16 *
0x18001934a  mov     r8, rdi; unsigned __int16 *
0x18001934d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180019352  inc     r11
0x180019355  cmp     [rsi+r11*2], r12w
0x18001935a  jnz     short loc_180019352
0x18001935c  sub     r15, r11
0x18001935f  lea     rcx, [rsi+r11*2]; unsigned __int16 *
0x180019363  lea     r8, aExtensionsDiag; "</Extensions></DiagnosticsText>"
0x18001936a  mov     rdx, r15; unsigned __int64
0x18001936d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180019372  mov     r11, [rsp+68h+arg_8]
0x180019377  mov     [r11], rsi
0x18001937a  jmp     short loc_180019382
0x18001937c  mov     r13d, 8007000Eh
0x180019382  lea     rcx, [rdi-18h]; this
0x180019386  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001938b  nop
0x18001938c  lea     rcx, [rbx-18h]; this
0x180019390  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180019395  nop
0x180019396  jmp     loc_1800194A6
0x18001939b  lea     rcx, [rsp+68h+arg_0]
0x1800193a0  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800193a5  nop
0x1800193a6  mov     r9, [rbx+28h]
0x1800193aa  mov     r8, [rbx+20h]
0x1800193ae  lea     rdx, aExtensionNameC; "<Extension><Name><![CDATA[%s]]></Name><"...
0x1800193b5  lea     rcx, [rsp+68h+arg_0]
0x1800193ba  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x1800193bf  mov     rdx, [rsp+68h+arg_0]
0x1800193c4  lea     rdi, [rdx-18h]
0x1800193c8  mov     r8d, [rdi+8]
0x1800193cc  lea     rcx, [rsp+68h+arg_10]
0x1800193d4  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x1800193d9  nop
0x1800193da  mov     rcx, rdi; this
0x1800193dd  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800193e2  cmp     [rbx+19h], sil
0x1800193e6  jnz     loc_1800191EA
0x1800193ec  mov     rcx, [rbx+10h]
0x1800193f0  cmp     [rcx+19h], sil
0x1800193f4  jnz     short loc_1800193FD
0x1800193f6  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>>::_Min(std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *> *)
0x1800193fb  jmp     short loc_180019416
0x1800193fd  mov     rax, [rbx+8]
0x180019401  jmp     short loc_180019410
0x180019403  cmp     rbx, [rax+10h]
0x180019407  jnz     short loc_180019416
0x180019409  mov     rbx, rax
0x18001940c  mov     rax, [rax+8]
0x180019410  cmp     [rax+19h], sil
0x180019414  jz      short loc_180019403
0x180019416  mov     rbx, rax
0x180019419  jmp     loc_1800191EA
0x18001941e  lea     rcx, [rsp+68h+arg_0]
0x180019423  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180019428  nop
0x180019429  mov     r9, [rbx+28h]
0x18001942d  mov     r8, [rbx+20h]
0x180019431  lea     rdx, aParameterNameC; "<Parameter><Name><![CDATA[%s]]></Name><"...
0x180019438  lea     rcx, [rsp+68h+arg_0]
0x18001943d  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180019442  mov     rdx, [rsp+68h+arg_0]
0x180019447  lea     rdi, [rdx-18h]
0x18001944b  mov     r8d, [rdi+8]
0x18001944f  lea     rcx, [rsp+68h+arg_18]
0x180019457  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x18001945c  nop
0x18001945d  mov     rcx, rdi; this
0x180019460  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180019465  cmp     [rbx+19h], sil
0x180019469  jnz     loc_1800191CB
0x18001946f  mov     rcx, [rbx+10h]
0x180019473  cmp     [rcx+19h], sil
0x180019477  jnz     short loc_180019480
0x180019479  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>>::_Min(std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *> *)
0x18001947e  jmp     short loc_180019499
0x180019480  mov     rax, [rbx+8]
0x180019484  jmp     short loc_180019493
0x180019486  cmp     rbx, [rax+10h]
0x18001948a  jnz     short loc_180019499
0x18001948c  mov     rbx, rax
0x18001948f  mov     rax, [rax+8]
0x180019493  cmp     [rax+19h], sil
0x180019497  jz      short loc_180019486
0x180019499  mov     rbx, rax
0x18001949c  jmp     loc_1800191CB
0x1800194a1  mov     r13d, dword ptr [rsp+68h+arg_0]
0x1800194a6  mov     eax, r13d
0x1800194a9  add     rsp, 30h
0x1800194ad  pop     r15
0x1800194af  pop     r14
0x1800194b1  pop     r13
0x1800194b3  pop     r12
0x1800194b5  pop     rdi
0x1800194b6  pop     rsi
0x1800194b7  pop     rbx
0x1800194b8  retn
```
