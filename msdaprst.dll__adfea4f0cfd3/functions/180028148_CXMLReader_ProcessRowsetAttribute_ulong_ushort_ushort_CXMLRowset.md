# CXMLReader::ProcessRowsetAttribute(ulong,ushort *,ushort *,CXMLRowset *)

- ea: `0x180028148`
- end: `0x180028513`
- name: `?ProcessRowsetAttribute@CXMLReader@@AEAAJKPEAG0PEAVCXMLRowset@@@Z`
- size: `971`
- prototype: `__int64 __fastcall(CXMLReader *__hidden this, unsigned int, unsigned __int16 *, unsigned __int16 *, struct CXMLRowset *)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800267cc`
- `0x18002851c`

## callees

- `0x180001db8`
- `0x180001dd4`
- `0x180018d38`
- `0x180027324`
- `0x180028148`
- `0x180028aec`
- `0x1800295d0`
- `0x180029dc0`
- `0x18002bbfc`
- `0x18002d9a4`
- `0x18002f0aa`
- `0x18002f0e0`
- `0x180031010`

## import_xrefs

- `msvcrt!wcschr` at `0x180028442`
- `msvcrt!wcschr` at `0x180028442`
- `OLEAUT32!__imp_SysStringLen` at `0x18002828f`
- `OLEAUT32!__imp_SysStringLen` at `0x1800283a3`
- `OLEAUT32!__imp_SysStringLen` at `0x18002828f`
- `OLEAUT32!__imp_SysStringLen` at `0x1800283a3`
- `OLEAUT32!__imp_VariantInit` at `0x180028275`
- `OLEAUT32!__imp_VariantInit` at `0x180028275`
- `OLEAUT32!__imp_VariantClear` at `0x18002836b`
- `OLEAUT32!__imp_VariantClear` at `0x18002836b`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800282bb`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800282bb`

## pseudocode

```c
__int64 __fastcall CXMLReader::ProcessRowsetAttribute(
        CCollectionList **this,
        unsigned int a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        struct CXMLRowset *a5)
{
  unsigned int v6; // edi
  int v7; // eax
  int v8; // ebx
  __int64 v9; // rdx
  __int64 v10; // rax
  VARTYPE v11; // di
  unsigned __int64 v12; // rax
  GUID v13; // xmm0
  struct tagDBPROPIDSET near *v14; // rax
  unsigned int v15; // edx
  CUtlProps *v16; // r14
  const struct CBidGenericBase *v17; // r13
  __int64 v18; // rax
  unsigned int v19; // edx
  UINT v20; // edi
  unsigned int v21; // edx
  unsigned __int8 *v22; // rax
  unsigned __int8 *v23; // rbx
  wchar_t *v24; // rbx
  wchar_t *v25; // rax
  wchar_t *v26; // r12
  __int64 v27; // rsi
  CCollectionList *v28; // rcx
  int v30; // [rsp+30h] [rbp-A1h] BYREF
  unsigned int v31[2]; // [rsp+38h] [rbp-99h] BYREF
  unsigned __int64 v32; // [rsp+40h] [rbp-91h] BYREF
  _QWORD pvarSrc[4]; // [rsp+48h] [rbp-89h] BYREF
  struct tagDBPROPSET v34; // [rsp+68h] [rbp-69h] BYREF
  int v35; // [rsp+90h] [rbp-41h] BYREF
  __int64 v36; // [rsp+94h] [rbp-3Dh]
  DBID v37; // [rsp+A0h] [rbp-31h]
  VARIANTARG pvarg; // [rsp+C0h] [rbp-11h] BYREF

  memset(pvarSrc, 0, sizeof(pvarSrc));
  v6 = 0;
  if ( CXMLReader::LookupAttributeInfo((CXMLReader *)this, a2, a3, a4, (struct tagDBATTRIBINFO *)pvarSrc) )
    return v6;
  v7 = *((_DWORD *)this + 120);
  if ( v7 != 3 )
  {
    if ( v7 != 5 )
      return v6;
    if ( HIDWORD(pvarSrc[0]) != 1 )
      return v6;
    v24 = (wchar_t *)pvarSrc[2];
    v32 = 0;
    if ( !*(_WORD *)pvarSrc[2] )
      return v6;
    do
    {
      v25 = wcschr(v24, 0x20u);
      v26 = v25;
      if ( v25 )
      {
        v27 = v25 - v24;
      }
      else
      {
        v27 = -1;
        do
          ++v27;
        while ( v24[v27] );
      }
      v28 = this[17];
      *(_QWORD *)v31 = 0;
      CCollectionList::LookUpByKey(v28, v24, v27, (unsigned __int64 *)v31);
      if ( *(_QWORD *)v31
        && **(_DWORD **)v31 == 3
        && !(unsigned int)CCollectionList::LookUpByKey((struct CXMLRowset *)((char *)a5 + 552), v24, v27, &v32) )
      {
        *(_DWORD *)(*(_QWORD *)(*((_QWORD *)a5 + 35) + 8LL * (unsigned int)v32) + 4LL) = 3;
      }
      if ( v26 )
        ++v24;
      v24 += (unsigned int)v27;
    }
    while ( *v24 );
    return 0;
  }
  if ( !XMLProps::m_fInitialized )
    XMLProps::_InitProps();
  v8 = HIDWORD(pvarSrc[0]) - (_DWORD)XMLProps::m_rgRSAttr;
  if ( (unsigned int)(HIDWORD(pvarSrc[0]) - (_DWORD)XMLProps::m_rgRSAttr) > 0xB )
  {
    if ( HIDWORD(pvarSrc[0]) == 16 )
    {
      ATL::CComBSTR::operator=((char *)a5 + 640, pvarSrc[2]);
      return v6;
    }
    if ( HIDWORD(pvarSrc[0]) != 3 )
      return v6;
    v30 = 0;
    v20 = SysStringLen((BSTR)pvarSrc[2]);
    v22 = MMMAlloc(v20 >> 1, v21);
    v23 = v22;
    if ( !v22 )
      return (unsigned int)-2147024882;
    v6 = DecodeBin((unsigned __int16 *)pvarSrc[2], v22, v20, &v30);
    if ( (v6 & 0x80000000) != 0 )
    {
      operator delete(v23);
      return v6;
    }
    *((_DWORD *)a5 + 154) = v30;
    *((_QWORD *)a5 + 78) = v23;
    return 0;
  }
  memset(&v34, 0, sizeof(v34));
  memset_0(&v35, 0, 0x48u);
  v9 = (unsigned int)(v8 - 3);
  v10 = 0;
  if ( v8 >= 3 )
    v10 = 1;
  else
    v9 = (unsigned int)v8;
  v11 = (VARTYPE)(&XMLProps::m_rgDefaultSets)[v10][3 * v9];
  v34.cProperties = 1;
  v12 = 0;
  if ( v8 >= 3 )
    v12 = 4;
  v34.rgProperties = (DBPROP *)&v35;
  v13 = (GUID)xmmword_18004655C[v12 / 2];
  v14 = (&XMLProps::m_rgPropSets)[v12];
  v34.guidPropertySet = v13;
  v35 = *((_DWORD *)&v14->rgPropertyIDs + v9);
  v36 = 0;
  v37 = DB_NULLID;
  VariantInit(&pvarg);
  if ( v11 != 11 || SysStringLen((BSTR)pvarSrc[2]) )
  {
    v6 = VariantChangeType(&pvarg, (const VARIANTARG *)&pvarSrc[1], 0, v11);
    if ( (v6 & 0x80000000) != 0 )
      return v6;
  }
  else
  {
    pvarg.vt = 11;
    pvarg.iVal = -1;
  }
  v16 = (struct CXMLRowset *)((char *)a5 + 400);
  v17 = (const struct CBidGenericBase *)(this + 62);
  v6 = CUtlProps::utlSetProperties((struct CXMLRowset *)((char *)a5 + 400), v15, 1u, &v34, v17, 1);
  if ( (v6 & 0x80000000) == 0 && HIDWORD(pvarSrc[0]) == 5 && pvarg.iVal == -1 )
  {
    v18 = *(_QWORD *)v16;
    v31[0] = 0;
    v30 = 0;
    (*(void (__fastcall **)(CUtlProps *, GUID *, unsigned int *))(v18 + 8))(v16, &v34.guidPropertySet, v31);
    CUtlProps::GetPropState(v16, v31[0], 0x86u, (enum PROPSTATES *)&v30);
    if ( v30 != 1 )
    {
      v35 = 134;
      v6 = CUtlProps::utlSetProperties(v16, v19, 1u, &v34, v17, 1);
    }
  }
  VariantClear(&pvarg);
  return v6;
}

```

## disassembly

```asm
0x180028148  mov     [rsp-8+arg_18], rbx
0x18002814d  push    rbp
0x18002814e  push    rsi
0x18002814f  push    rdi
0x180028150  push    r12
0x180028152  push    r13
0x180028154  push    r14
0x180028156  push    r15
0x180028158  lea     rbp, [rsp-1Fh]
0x18002815d  sub     rsp, 0F0h
0x180028164  mov     rax, cs:__security_cookie
0x18002816b  xor     rax, rsp
0x18002816e  mov     [rbp+4Fh+var_40], rax
0x180028172  mov     r14, [rbp+4Fh+arg_20]
0x180028176  lea     rax, [rsp+120h+pvarSrc]
0x18002817b  xorps   xmm0, xmm0
0x18002817e  mov     [rsp+120h+var_100], rax; struct tagDBATTRIBINFO *
0x180028183  xor     esi, esi
0x180028185  mov     r13, rcx
0x180028188  movups  xmmword ptr [rsp+120h+pvarSrc], xmm0
0x18002818d  mov     edi, esi
0x18002818f  movups  xmmword ptr [rbp+4Fh+pvarSrc+10h], xmm0
0x180028193  call    ?LookupAttributeInfo@CXMLReader@@AEAAJKPEAG0PEAUtagDBATTRIBINFO@@@Z; CXMLReader::LookupAttributeInfo(ulong,ushort *,ushort *,tagDBATTRIBINFO *)
0x180028198  test    eax, eax
0x18002819a  jnz     loc_1800284E9
0x1800281a0  mov     eax, [r13+1E0h]
0x1800281a7  cmp     eax, 3
0x1800281aa  jnz     loc_18002840E
0x1800281b0  cmp     cs:?m_fInitialized@XMLProps@@0KA, esi; ulong XMLProps::m_fInitialized
0x1800281b6  jnz     short loc_1800281BD
0x1800281b8  call    ?_InitProps@XMLProps@@CAXXZ; XMLProps::_InitProps(void)
0x1800281bd  mov     eax, dword ptr [rsp+120h+pvarSrc+4]
0x1800281c1  mov     r12d, 0Bh
0x1800281c7  mov     ebx, eax
0x1800281c9  sub     ebx, cs:?m_rgRSAttr@XMLProps@@0PAW4ROWSETATTRIBUTES@@A; ROWSETATTRIBUTES near * XMLProps::m_rgRSAttr
0x1800281cf  cmp     ebx, r12d
0x1800281d2  ja      loc_18002837C
0x1800281d8  xorps   xmm0, xmm0
0x1800281db  lea     r8d, [r12+3Dh]; Size
0x1800281e0  xor     edx, edx; Val
0x1800281e2  lea     rcx, [rbp+4Fh+var_90]; void *
0x1800281e6  movups  xmmword ptr [rbp+4Fh+var_B8.rgProperties], xmm0
0x1800281ea  movups  xmmword ptr [rbp+4Fh+var_B8.guidPropertySet.Data2], xmm0
0x1800281ee  call    memset_0
0x1800281f3  movups  xmm1, xmmword ptr cs:DB_NULLID.eKind
0x1800281fa  lea     edx, [rbx-3]
0x1800281fd  cmp     ebx, 3
0x180028200  lea     r8, cs:180000000h
0x180028207  mov     rax, rsi
0x18002820a  cmovl   edx, ebx
0x18002820d  lea     ecx, [r12-3]
0x180028212  cmovge  rax, rcx
0x180028216  lea     ebx, [r12-0Ah]
0x18002821b  lea     rcx, [rdx+rdx*2]
0x18002821f  mov     rax, [rax+r8+46540h]
0x180028227  movzx   edi, word ptr [rax+rcx*8]
0x18002822b  lea     ecx, [r12+15h]
0x180028230  mov     [rbp+4Fh+var_B8.cProperties], ebx
0x180028233  mov     rax, rsi
0x180028236  cmovge  rax, rcx
0x18002823a  lea     rcx, [rbp+4Fh+var_90]
0x18002823e  mov     [rbp+4Fh+var_B8.rgProperties], rcx
0x180028242  movups  xmm0, xmmword ptr [rax+r8+4655Ch]
0x18002824b  mov     rax, [rax+r8+46550h]
0x180028253  movdqu  xmmword ptr [rbp+4Fh+var_B8.guidPropertySet.Data1], xmm0
0x180028258  mov     ecx, [rax+rdx*4]
0x18002825b  movups  xmm0, xmmword ptr cs:DB_NULLID.uGuid
0x180028262  mov     [rbp+4Fh+var_90], ecx
0x180028265  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x180028269  mov     [rbp+4Fh+var_8C], rsi
0x18002826d  movaps  [rbp+4Fh+var_80], xmm0
0x180028271  movaps  [rbp+4Fh+var_70], xmm1
0x180028275  call    cs:__imp_VariantInit
0x18002827c  nop     dword ptr [rax+rax+00h]
0x180028281  or      r15, 0FFFFFFFFFFFFFFFFh
0x180028285  cmp     di, r12w
0x180028289  jnz     short loc_1800282AB
0x18002828b  mov     rcx, qword ptr [rbp+4Fh+pvarSrc+10h]; pbstr
0x18002828f  call    cs:__imp_SysStringLen
0x180028296  nop     dword ptr [rax+rax+00h]
0x18002829b  test    eax, eax
0x18002829d  jnz     short loc_1800282AB
0x18002829f  mov     word ptr [rbp+4Fh+pvarg], r12w
0x1800282a4  mov     word ptr [rbp+4Fh+pvarg+8], r15w
0x1800282a9  jmp     short loc_1800282D1
0x1800282ab  xor     r8d, r8d; wFlags
0x1800282ae  lea     rdx, [rsp+120h+pvarSrc+8]; pvarSrc
0x1800282b3  movzx   r9d, di; vt
0x1800282b7  lea     rcx, [rbp+4Fh+pvarg]; pvargDest
0x1800282bb  call    cs:__imp_VariantChangeType
0x1800282c2  nop     dword ptr [rax+rax+00h]
0x1800282c7  mov     edi, eax
0x1800282c9  test    eax, eax
0x1800282cb  js      loc_1800284E9
0x1800282d1  add     r14, 190h
0x1800282d8  mov     [rsp+120h+var_F8], ebx; int
0x1800282dc  add     r13, 1F0h
0x1800282e3  lea     r9, [rbp+4Fh+var_B8]; struct tagDBPROPSET *
0x1800282e7  mov     rcx, r14; this
0x1800282ea  mov     [rsp+120h+var_100], r13; struct CBidGenericBase *
0x1800282ef  mov     r8d, ebx; unsigned int
0x1800282f2  call    ?utlSetProperties@CUtlProps@@QEAAJKKQEBUtagDBPROPSET@@AEBVCBidGenericBase@@H@Z; CUtlProps::utlSetProperties(ulong,ulong,tagDBPROPSET const * const,CBidGenericBase const &,int)
0x1800282f7  mov     edi, eax
0x1800282f9  test    eax, eax
0x1800282fb  js      short loc_180028367
0x1800282fd  cmp     dword ptr [rsp+120h+pvarSrc+4], 5
0x180028302  jnz     short loc_180028367
0x180028304  cmp     r15w, word ptr [rbp+4Fh+pvarg+8]
0x180028309  jnz     short loc_180028367
0x18002830b  mov     rax, [r14]
0x18002830e  lea     r8, [rsp+120h+var_E8]
0x180028313  lea     rdx, [rbp+4Fh+var_B8.guidPropertySet]
0x180028317  mov     [rsp+120h+var_E8], esi
0x18002831b  mov     rcx, r14
0x18002831e  mov     [rsp+120h+var_F0], esi
0x180028322  mov     rax, [rax+8]
0x180028326  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002832b  mov     edx, [rsp+120h+var_E8]; unsigned int
0x18002832f  lea     r9, [rsp+120h+var_F0]; enum PROPSTATES *
0x180028334  mov     esi, 86h
0x180028339  mov     rcx, r14; this
0x18002833c  mov     r8d, esi; unsigned int
0x18002833f  call    ?GetPropState@CUtlProps@@QEAAHKKPEAW4PROPSTATES@@@Z; CUtlProps::GetPropState(ulong,ulong,PROPSTATES *)
0x180028344  cmp     [rsp+120h+var_F0], ebx
0x180028348  jz      short loc_180028367
0x18002834a  mov     [rsp+120h+var_F8], ebx; int
0x18002834e  lea     r9, [rbp+4Fh+var_B8]; struct tagDBPROPSET *
0x180028352  mov     r8d, ebx; unsigned int
0x180028355  mov     [rsp+120h+var_100], r13; struct CBidGenericBase *
0x18002835a  mov     rcx, r14; this
0x18002835d  mov     [rbp+4Fh+var_90], esi
0x180028360  call    ?utlSetProperties@CUtlProps@@QEAAJKKQEBUtagDBPROPSET@@AEBVCBidGenericBase@@H@Z; CUtlProps::utlSetProperties(ulong,ulong,tagDBPROPSET const * const,CBidGenericBase const &,int)
0x180028365  mov     edi, eax
0x180028367  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x18002836b  call    cs:__imp_VariantClear
0x180028372  nop     dword ptr [rax+rax+00h]
0x180028377  jmp     loc_1800284E9
0x18002837c  cmp     eax, 10h
0x18002837f  jnz     short loc_180028396
0x180028381  mov     rdx, qword ptr [rbp+4Fh+pvarSrc+10h]
0x180028385  lea     rcx, [r14+280h]
0x18002838c  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x180028391  jmp     loc_1800284E9
0x180028396  cmp     eax, 3
0x180028399  jnz     loc_1800284E9
0x18002839f  mov     rcx, qword ptr [rbp+4Fh+pvarSrc+10h]; pbstr
0x1800283a3  call    cs:__imp_SysStringLen
0x1800283aa  nop     dword ptr [rax+rax+00h]
0x1800283af  mov     ecx, eax
0x1800283b1  mov     [rsp+120h+var_F0], esi
0x1800283b5  shr     ecx, 1; unsigned int
0x1800283b7  mov     edi, eax
0x1800283b9  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x1800283be  mov     rbx, rax
0x1800283c1  test    rax, rax
0x1800283c4  jnz     short loc_1800283D0
0x1800283c6  mov     edi, 8007000Eh
0x1800283cb  jmp     loc_1800284E9
0x1800283d0  mov     rcx, qword ptr [rbp+4Fh+pvarSrc+10h]; unsigned __int16 *
0x1800283d4  lea     r9, [rsp+120h+var_F0]; int *
0x1800283d9  mov     r8d, edi; unsigned int
0x1800283dc  mov     rdx, rbx; unsigned __int8 *
0x1800283df  call    ?DecodeBin@@YAJPEAGPEAEKPEAJ@Z; DecodeBin(ushort *,uchar *,ulong,long *)
0x1800283e4  mov     edi, eax
0x1800283e6  test    eax, eax
0x1800283e8  jns     short loc_1800283F7
0x1800283ea  mov     rcx, rbx; void *
0x1800283ed  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800283f2  jmp     loc_1800284E9
0x1800283f7  mov     eax, [rsp+120h+var_F0]
0x1800283fb  mov     [r14+268h], eax
0x180028402  mov     [r14+270h], rbx
0x180028409  jmp     loc_1800284E7
0x18002840e  cmp     eax, 5
0x180028411  jnz     loc_1800284E9
0x180028417  lea     ebx, [rax-4]
0x18002841a  cmp     dword ptr [rsp+120h+pvarSrc+4], ebx
0x18002841e  jnz     loc_1800284E9
0x180028424  mov     rbx, qword ptr [rbp+4Fh+pvarSrc+10h]
0x180028428  mov     [rsp+120h+var_E0], rsi
0x18002842d  cmp     [rbx], si
0x180028430  jz      loc_1800284E9
0x180028436  lea     edi, [rax+1Bh]
0x180028439  or      r15, 0FFFFFFFFFFFFFFFFh
0x18002843d  mov     edx, edi; Ch
0x18002843f  mov     rcx, rbx; Str
0x180028442  call    cs:__imp_wcschr
0x180028449  nop     dword ptr [rax+rax+00h]
0x18002844e  mov     r12, rax
0x180028451  test    rax, rax
0x180028454  jz      short loc_180028463
0x180028456  mov     rsi, rax
0x180028459  sub     rsi, rbx
0x18002845c  sar     rsi, 1
0x18002845f  xor     eax, eax
0x180028461  jmp     short loc_180028471
0x180028463  mov     rsi, r15
0x180028466  xor     eax, eax
0x180028468  inc     rsi
0x18002846b  cmp     [rbx+rsi*2], ax
0x18002846f  jnz     short loc_180028468
0x180028471  mov     rcx, [r13+88h]; this
0x180028478  lea     r9, [rsp+120h+var_E8]; unsigned __int64 *
0x18002847d  mov     r8d, esi; unsigned int
0x180028480  mov     qword ptr [rsp+120h+var_E8], rax
0x180028485  mov     rdx, rbx; unsigned __int16 *
0x180028488  call    ?LookUpByKey@CCollectionList@@QEAAJPEAGKPEA_K@Z; CCollectionList::LookUpByKey(ushort *,ulong,unsigned __int64 *)
0x18002848d  mov     rax, qword ptr [rsp+120h+var_E8]
0x180028492  test    rax, rax
0x180028495  jz      short loc_1800284CD
0x180028497  cmp     dword ptr [rax], 3
0x18002849a  jnz     short loc_1800284CD
0x18002849c  lea     rcx, [r14+228h]; this
0x1800284a3  mov     r8d, esi; unsigned int
0x1800284a6  lea     r9, [rsp+120h+var_E0]; unsigned __int64 *
0x1800284ab  mov     rdx, rbx; unsigned __int16 *
0x1800284ae  call    ?LookUpByKey@CCollectionList@@QEAAJPEAGKPEA_K@Z; CCollectionList::LookUpByKey(ushort *,ulong,unsigned __int64 *)
0x1800284b3  test    eax, eax
0x1800284b5  jnz     short loc_1800284CD
0x1800284b7  mov     rax, [r14+118h]
0x1800284be  mov     ecx, dword ptr [rsp+120h+var_E0]
0x1800284c2  mov     rcx, [rax+rcx*8]
0x1800284c6  mov     dword ptr [rcx+4], 3
0x1800284cd  test    r12, r12
0x1800284d0  jz      short loc_1800284D6
0x1800284d2  add     rbx, 2
0x1800284d6  mov     eax, esi
0x1800284d8  xor     esi, esi
0x1800284da  lea     rbx, [rbx+rax*2]
0x1800284de  cmp     [rbx], si
0x1800284e1  jnz     loc_18002843D
0x1800284e7  mov     edi, esi
0x1800284e9  mov     eax, edi
0x1800284eb  mov     rcx, [rbp+4Fh+var_40]
0x1800284ef  xor     rcx, rsp; StackCookie
0x1800284f2  call    __security_check_cookie
0x1800284f7  mov     rbx, [rsp+120h+arg_18]
0x1800284ff  add     rsp, 0F0h
0x180028506  pop     r15
0x180028508  pop     r14
0x18002850a  pop     r13
0x18002850c  pop     r12
0x18002850e  pop     rdi
0x18002850f  pop     rsi
0x180028510  pop     rbp
0x180028511  retn
```
