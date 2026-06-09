# CXMLReader::BuildRowDefinition(CParseNode *,ulong,CSymbol *)

- ea: `0x1800248d8`
- end: `0x180024dfe`
- name: `?BuildRowDefinition@CXMLReader@@AEAAJPEAVCParseNode@@KPEAVCSymbol@@@Z`
- size: `1318`
- prototype: `__int64 __fastcall(CXMLReader *__hidden this, struct CParseNode *, unsigned int, struct CSymbol *)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800287cc`

## callees

- `0x180001dd4`
- `0x1800023c0`
- `0x180016584`
- `0x18001b008`
- `0x1800241b0`
- `0x1800241d8`
- `0x180024334`
- `0x180024434`
- `0x1800248d8`
- `0x180024e04`
- `0x180026d04`
- `0x18002851c`
- `0x180028f38`
- `0x180029748`
- `0x180029770`
- `0x180029e94`
- `0x18002c9fc`
- `0x18002d9a4`
- `0x18002f0aa`
- `0x18002f0e0`
- `0x180031010`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x180024b4b`
- `OLEAUT32!__imp_SysStringLen` at `0x180024b4b`
- `OLEAUT32!__imp_VariantInit` at `0x180024a98`
- `OLEAUT32!__imp_VariantInit` at `0x180024d43`
- `OLEAUT32!__imp_VariantInit` at `0x180024a98`
- `OLEAUT32!__imp_VariantInit` at `0x180024d43`

## pseudocode

```c
__int64 __fastcall CXMLReader::BuildRowDefinition(
        CXMLReader *this,
        struct CParseNode *a2,
        unsigned int a3,
        struct CSymbol *a4)
{
  int v5; // r13d
  __int64 result; // rax
  CXMLRowset *v9; // rsi
  int BidObjectID; // ebx
  unsigned int v11; // eax
  unsigned int v12; // edx
  unsigned __int8 *v13; // rax
  unsigned __int8 *v14; // rbx
  unsigned int v15; // edx
  int v16; // edi
  __int64 v17; // r12
  unsigned int v18; // edx
  unsigned int v19; // r8d
  __int64 v20; // rax
  __int64 v21; // r13
  BSTR *Value; // rax
  unsigned int v23; // edx
  struct CParseNode *v24; // rcx
  unsigned __int16 **v25; // r12
  unsigned __int64 v26; // r15
  CScope *v27; // rbx
  UINT v28; // eax
  struct CSymbol *v29; // r12
  bool v30; // zf
  struct CSymbol *v31; // rdi
  unsigned __int8 *v32; // rbx
  __int64 v33; // rdi
  unsigned int v34; // eax
  int v35; // edx
  struct CSymbol *v36; // [rsp+30h] [rbp-A9h] BYREF
  CXMLRowset *v37; // [rsp+38h] [rbp-A1h] BYREF
  unsigned int v38; // [rsp+40h] [rbp-99h]
  struct CParseNode *v39; // [rsp+48h] [rbp-91h]
  VARIANTARG pvarg; // [rsp+50h] [rbp-89h] BYREF
  struct tagDBPROPSET v41; // [rsp+68h] [rbp-71h] BYREF
  _QWORD v42[6]; // [rsp+90h] [rbp-49h] BYREF
  VARIANTARG v43; // [rsp+C0h] [rbp-19h] BYREF

  v5 = *((_DWORD *)a2 + 11);
  v38 = *((_DWORD *)this + 108);
  v39 = a2;
  v37 = 0;
  LODWORD(v36) = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  if ( (int)ATL::CComObject<CXMLRowset>::CreateInstance(&v37) < 0 )
    return 0;
  v9 = v37;
  if ( (bidGblFlags & 2) != 0 && off_180049D28[0] )
  {
    BidObjectID = CBidGenericBase::GetBidObjectID((CXMLReader *)((char *)this + 496));
    v11 = CBidGenericBase::GetBidObjectID((CXMLRowset *)((char *)v9 + 112));
    bidTraceW(off_180049208[0], 1348608, off_180049D28[0], v11, BidObjectID);
  }
  (*(void (__fastcall **)(CXMLRowset *))(*(_QWORD *)v9 + 8LL))(v9);
  *(_DWORD *)a4 = 1;
  *((_QWORD *)a4 + 1) = v9;
  *((_BYTE *)a4 + 16) = 1;
  result = (*(__int64 (__fastcall **)(CXMLRowset *, _QWORD))(*(_QWORD *)v9 + 88LL))(v9, a3);
  if ( (int)result >= 0 )
  {
    v13 = MMMAlloc(0x38u, v12);
    v37 = (CXMLRowset *)v13;
    v14 = v13;
    if ( !v13 )
      return 2147942414LL;
    *(_DWORD *)v13 = 0;
    *((_QWORD *)v13 + 1) = 0;
    *((_DWORD *)v13 + 4) = 0;
    *((_DWORD *)v13 + 6) = 0;
    *((_QWORD *)v13 + 4) = 0;
    *((_QWORD *)v13 + 5) = 0;
    *((_QWORD *)v13 + 6) = 0;
    v16 = CCollectionList::Reserve((CCollectionList *)v13, 0xAu);
    if ( v16 < 0 )
    {
      CScope::`scalar deleting destructor'((CScope *)v14, v15);
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( off_180049D20[0] )
          bidTraceW(off_180049208[0], 1370112, off_180049D20[0], (unsigned int)v16, 1338);
      }
      return (unsigned int)v16;
    }
    v17 = (unsigned int)(v5 + 1);
    *((_QWORD *)v14 + 6) = *((_QWORD *)this + 17);
    *((_QWORD *)this + 17) = v14;
    *((_QWORD *)v9 + 79) = v14;
    LODWORD(v37) = v5 + 1;
    VariantInit(&pvarg);
    pvarg.vt = 11;
    pvarg.iVal = -1;
    CUtlProps::InternalSetProperty(
      (CXMLRowset *)((char *)v9 + 400),
      v18,
      v19,
      &pvarg,
      (int *)&v36,
      (CXMLReader *)((char *)this + 496));
    while ( 1 )
    {
      if ( (unsigned int)v17 >= v38 )
      {
        if ( *((_WORD *)v9 + 152) != *((_WORD *)v9 + 153) )
        {
          *((_DWORD *)&v41.guidPropertySet + 4) = 0;
          memset_0(v42, 0, 0x48u);
          v41.cProperties = 1;
          v41.rgProperties = (DBPROP *)v42;
          v41.guidPropertySet = DBPROPSET_ROWSET;
          v42[0] = 258;
          VariantInit(&v43);
          v35 = *((unsigned __int16 *)v9 + 152);
          v43.vt = 3;
          v43.lVal = v35 - *((unsigned __int16 *)v9 + 153);
          v16 = CUtlProps::utlSetProperties(
                  (CXMLRowset *)((char *)v9 + 400),
                  v43.cyVal.Lo,
                  1u,
                  &v41,
                  (CXMLReader *)((char *)this + 496),
                  1);
        }
        if ( *((_BYTE *)this + 472)
          || (unsigned int)CXMLRowset::AllColumnsInitialized(v9)
          || (v16 = Exit(-2147467259, 0x91u), v16 >= 0) )
        {
          *((_QWORD *)this + 17) = *(_QWORD *)(*((_QWORD *)this + 17) + 48LL);
        }
        return (unsigned int)v16;
      }
      v20 = *((_QWORD *)this + 53);
      v36 = 0;
      v21 = *(_QWORD *)(v20 + 8 * v17);
      Value = (BSTR *)CParseNode::GetValue((CParseNode *)v21);
      v24 = *(struct CParseNode **)(v21 + 16);
      v25 = Value;
      if ( v24 == v39 && *(_DWORD *)(v21 + 8) == 1 )
      {
        v26 = 0;
        if ( *(_BYTE *)(v21 + 40) != 8 )
          goto LABEL_21;
      }
      else if ( *(_BYTE *)(v21 + 40) != 8 )
      {
        if ( v24 == v39 && *(_DWORD *)(v21 + 8) == 2 )
        {
          v16 = CXMLReader::ProcessRowsetAttribute(this, (struct CParseNode *)v21, v9);
          if ( v16 < 0 )
            return (unsigned int)v16;
        }
        goto LABEL_43;
      }
      v26 = *(_QWORD *)(v21 + 16);
      if ( !v24 || *(_DWORD *)v24 == 1 )
      {
LABEL_21:
        v27 = (CScope *)*((_QWORD *)this + 17);
        v28 = SysStringLen(*Value);
        v16 = CScope::AddSymbol(v27, *v25, v28, &v36);
        if ( v16 < 0 )
          return (unsigned int)v16;
        v29 = v36;
        if ( v36 )
          goto LABEL_24;
      }
      v29 = (struct CSymbol *)v26;
LABEL_24:
      *((_QWORD *)v29 + 1) = v9;
      if ( v26 && *(_DWORD *)v26 == 1 )
      {
        v30 = *((_BYTE *)this + 472) == 0;
        v31 = *(struct CSymbol **)(v26 + 8);
        v36 = v31;
        if ( !v30 )
        {
          v16 = Exit(-2147467259, 0x91u);
          if ( v16 < 0 )
            return (unsigned int)v16;
          v31 = v36;
        }
        v32 = MMMAlloc(0x18u, v23);
        if ( !v32 )
          return (unsigned int)-2147024882;
        v33 = *(_QWORD *)(*((_QWORD *)v31 + 79) + 48LL);
        v34 = CCollectionArray::DeleteByData((CCollectionArray *)v33, v26);
        if ( v34 )
        {
          if ( (bidGblFlags & 2) != 0 && off_180049E10[0] )
            bidTraceW(off_180049218, 1027072, off_180049E10[0], v34, 1003);
        }
        else
        {
          CCollectionMap::DeleteByData((CCollectionMap *)(v33 + 24), v26);
        }
        *(_QWORD *)(*((_QWORD *)v36 + 79) + 48LL) = *((_QWORD *)this + 17);
        *(_DWORD *)v29 = 1;
        *((_QWORD *)v32 + 2) = 0;
        *((_DWORD *)v32 + 2) = 0;
        *(_QWORD *)v32 = *(_QWORD *)(v26 + 8);
        *(_BYTE *)(v26 + 16) = 0;
        CSymbol::`scalar deleting destructor'((CSymbol *)v26, 0);
      }
      else
      {
        v32 = 0;
        *(_DWORD *)v29 = 3;
      }
      v16 = CXMLReader::BuildColumnDefinition(this, (struct CParseNode *)v21, v29, (struct XMLCHAPTER *)v32);
      if ( v16 < 0 )
        return (unsigned int)v16;
      if ( v32 )
        *((_QWORD *)v29 + 1) = *(_QWORD *)v32;
LABEL_43:
      v17 = (unsigned int)((_DWORD)v37 + 1);
      LODWORD(v37) = (_DWORD)v37 + 1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800248d8  push    rbp
0x1800248da  push    rbx
0x1800248db  push    rsi
0x1800248dc  push    rdi
0x1800248dd  push    r12
0x1800248df  push    r13
0x1800248e1  push    r14
0x1800248e3  push    r15
0x1800248e5  lea     rbp, [rsp-1Fh]
0x1800248ea  sub     rsp, 0F8h
0x1800248f1  mov     rax, cs:__security_cookie
0x1800248f8  xor     rax, rsp
0x1800248fb  mov     [rbp+57h+var_50], rax
0x1800248ff  mov     eax, [rcx+1B0h]
0x180024905  mov     r14, rcx
0x180024908  mov     r13d, [rdx+2Ch]
0x18002490c  lea     rcx, [rsp+130h+var_F8]
0x180024911  mov     [rsp+130h+var_F0], eax
0x180024915  xor     r12d, r12d
0x180024918  xor     eax, eax
0x18002491a  mov     [rsp+130h+var_E8], rdx
0x18002491f  xorps   xmm0, xmm0
0x180024922  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x180024926  mov     rdi, r9
0x180024929  mov     [rsp+130h+var_F8], r12
0x18002492e  mov     r15d, r8d
0x180024931  mov     dword ptr [rsp+130h+var_100], r12d
0x180024936  movups  xmmword ptr [rsp+130h+pvarg], xmm0
0x18002493b  call    ?CreateInstance@?$CComObject@VCXMLRowset@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CXMLRowset>::CreateInstance(ATL::CComObject<CXMLRowset> * *)
0x180024940  test    eax, eax
0x180024942  jns     short loc_18002494B
0x180024944  xor     eax, eax
0x180024946  jmp     loc_180024DDD
0x18002494b  test    byte ptr cs:_bidGblFlags, 2
0x180024952  mov     rsi, [rsp+130h+var_F8]
0x180024957  jz      short loc_18002499B
0x180024959  mov     rax, cs:off_180049D28; "<CXMLReader::BuildRowDefinition|ADO|PER"...
0x180024960  test    rax, rax
0x180024963  jz      short loc_18002499B
0x180024965  lea     rcx, [r14+1F0h]; this
0x18002496c  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180024971  lea     rcx, [rsi+70h]; this
0x180024975  mov     ebx, eax
0x180024977  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18002497c  mov     r8, cs:off_180049D28; "<CXMLReader::BuildRowDefinition|ADO|PER"...
0x180024983  mov     r9d, eax
0x180024986  mov     rcx, cs:off_180049208; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18002498d  mov     edx, 149400h
0x180024992  mov     dword ptr [rsp+130h+var_110], ebx
0x180024996  call    _bidTraceW
0x18002499b  mov     rax, [rsi]
0x18002499e  mov     rcx, rsi
0x1800249a1  mov     rax, [rax+8]
0x1800249a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800249aa  mov     dword ptr [rdi], 1
0x1800249b0  mov     edx, r15d
0x1800249b3  mov     [rdi+8], rsi
0x1800249b7  mov     rcx, rsi
0x1800249ba  mov     byte ptr [rdi+10h], 1
0x1800249be  mov     rax, [rsi]
0x1800249c1  mov     rax, [rax+58h]
0x1800249c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800249ca  test    eax, eax
0x1800249cc  js      loc_180024DDD
0x1800249d2  mov     ecx, 38h ; '8'; unsigned int
0x1800249d7  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x1800249dc  mov     [rsp+130h+var_F8], rax
0x1800249e1  mov     rbx, rax
0x1800249e4  test    rax, rax
0x1800249e7  jz      loc_180024DD8
0x1800249ed  mov     [rax], r12d
0x1800249f0  mov     [rax+8], r12
0x1800249f4  mov     [rax+10h], r12d
0x1800249f8  mov     [rax+18h], r12d
0x1800249fc  mov     [rax+20h], r12
0x180024a00  mov     [rax+28h], r12
0x180024a04  mov     [rax+30h], r12
0x180024a08  test    rax, rax
0x180024a0b  jz      loc_180024DD8
0x180024a11  mov     edx, 0Ah; unsigned int
0x180024a16  mov     rcx, rax; this
0x180024a19  call    ?Reserve@CCollectionList@@QEAAJK@Z; CCollectionList::Reserve(ulong)
0x180024a1e  mov     edi, eax
0x180024a20  test    eax, eax
0x180024a22  jns     short loc_180024A71
0x180024a24  mov     rcx, rbx; this
0x180024a27  call    ??_GCScope@@QEAAPEAXI@Z; CScope::`scalar deleting destructor'(uint)
0x180024a2c  test    byte ptr cs:_bidGblFlags, 2
0x180024a33  jz      loc_180024DD4
0x180024a39  mov     rcx, cs:off_180049D20; "<CXMLReader::BuildRowDefinition|ADO|ERR"...
0x180024a40  test    rcx, rcx
0x180024a43  jz      loc_180024DD4
0x180024a49  mov     r8, cs:off_180049D20; "<CXMLReader::BuildRowDefinition|ADO|ERR"...
0x180024a50  mov     r9d, edi
0x180024a53  mov     rcx, cs:off_180049208; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180024a5a  mov     edx, 14E800h
0x180024a5f  mov     dword ptr [rsp+130h+var_110], 53Ah
0x180024a67  call    _bidTraceW
0x180024a6c  jmp     loc_180024DD4
0x180024a71  mov     rax, [r14+88h]
0x180024a78  lea     r12d, [r13+1]
0x180024a7c  mov     [rbx+30h], rax
0x180024a80  lea     rcx, [rsp+130h+pvarg]; pvarg
0x180024a85  mov     [r14+88h], rbx
0x180024a8c  mov     [rsi+278h], rbx
0x180024a93  mov     dword ptr [rsp+130h+var_F8], r12d
0x180024a98  call    cs:__imp_VariantInit
0x180024a9f  nop     dword ptr [rax+rax+00h]
0x180024aa4  mov     eax, 0Bh
0x180024aa9  lea     rbx, [r14+1F0h]
0x180024ab0  mov     word ptr [rsp+130h+pvarg], ax
0x180024ab5  lea     rcx, [rsi+190h]; this
0x180024abc  or      eax, 0FFFFFFFFh
0x180024abf  mov     [rsp+130h+var_108], rbx; struct CBidGenericBase *
0x180024ac4  mov     word ptr [rsp+130h+pvarg+8], ax
0x180024ac9  lea     r9, [rsp+130h+pvarg]; struct tagVARIANT *
0x180024ace  lea     rax, [rsp+130h+var_100]
0x180024ad3  mov     [rsp+130h+var_110], rax; int *
0x180024ad8  call    ?InternalSetProperty@CUtlProps@@QEAAXKKPEAUtagVARIANT@@PEAHAEBVCBidGenericBase@@@Z; CUtlProps::InternalSetProperty(ulong,ulong,tagVARIANT *,int *,CBidGenericBase const &)
0x180024add  cmp     r12d, [rsp+130h+var_F0]
0x180024ae2  jnb     loc_180024CF2
0x180024ae8  mov     rax, [r14+1A8h]
0x180024aef  mov     [rsp+130h+var_100], 0
0x180024af8  mov     r13, [rax+r12*8]
0x180024afc  mov     rcx, r13; this
0x180024aff  call    ?GetValue@CParseNode@@QEAAAEAVCComBSTR@ATL@@XZ; CParseNode::GetValue(void)
0x180024b04  mov     rcx, [r13+10h]
0x180024b08  mov     r12, rax
0x180024b0b  mov     rax, [rsp+130h+var_E8]
0x180024b10  cmp     rcx, rax
0x180024b13  jnz     short loc_180024B28
0x180024b15  cmp     dword ptr [r13+8], 1
0x180024b1a  jnz     short loc_180024B28
0x180024b1c  xor     r15d, r15d
0x180024b1f  cmp     byte ptr [r13+28h], 8
0x180024b24  jnz     short loc_180024B40
0x180024b26  jmp     short loc_180024B33
0x180024b28  cmp     byte ptr [r13+28h], 8
0x180024b2d  jnz     loc_180024CB2
0x180024b33  mov     r15, rcx
0x180024b36  test    rcx, rcx
0x180024b39  jz      short loc_180024B40
0x180024b3b  cmp     dword ptr [rcx], 1
0x180024b3e  jnz     short loc_180024B7F
0x180024b40  mov     rcx, [r12]; pbstr
0x180024b44  mov     rbx, [r14+88h]
0x180024b4b  call    cs:__imp_SysStringLen
0x180024b52  nop     dword ptr [rax+rax+00h]
0x180024b57  mov     rdx, [r12]; unsigned __int16 *
0x180024b5b  lea     r9, [rsp+130h+var_100]; struct CSymbol **
0x180024b60  mov     r8d, eax; unsigned int
0x180024b63  mov     rcx, rbx; this
0x180024b66  call    ?AddSymbol@CScope@@QEAAJPEAGKPEAPEAVCSymbol@@@Z; CScope::AddSymbol(ushort *,ulong,CSymbol * *)
0x180024b6b  mov     edi, eax
0x180024b6d  test    eax, eax
0x180024b6f  js      loc_180024DD4
0x180024b75  mov     r12, [rsp+130h+var_100]
0x180024b7a  test    r12, r12
0x180024b7d  jnz     short loc_180024B82
0x180024b7f  mov     r12, r15
0x180024b82  mov     [r12+8], rsi
0x180024b87  test    r15, r15
0x180024b8a  jz      loc_180024C7E
0x180024b90  cmp     dword ptr [r15], 1
0x180024b94  jnz     loc_180024C7E
0x180024b9a  cmp     byte ptr [r14+1D8h], 0
0x180024ba2  mov     rdi, [r15+8]
0x180024ba6  mov     [rsp+130h+var_100], rdi
0x180024bab  jz      short loc_180024BCB
0x180024bad  mov     edx, 91h; unsigned int
0x180024bb2  mov     ecx, 80004005h; int
0x180024bb7  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x180024bbc  mov     edi, eax
0x180024bbe  test    eax, eax
0x180024bc0  js      loc_180024DD4
0x180024bc6  mov     rdi, [rsp+130h+var_100]
0x180024bcb  mov     ecx, 18h; unsigned int
0x180024bd0  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x180024bd5  mov     rbx, rax
0x180024bd8  test    rax, rax
0x180024bdb  jz      loc_180024CE8
0x180024be1  mov     rcx, [rdi+278h]
0x180024be8  mov     rdx, r15; unsigned __int64
0x180024beb  mov     rdi, [rcx+30h]
0x180024bef  mov     rcx, rdi; this
0x180024bf2  call    ?DeleteByData@CCollectionArray@@QEAAJ_K@Z; CCollectionArray::DeleteByData(unsigned __int64)
0x180024bf7  test    eax, eax
0x180024bf9  jz      short loc_180024C35
0x180024bfb  test    byte ptr cs:_bidGblFlags, 2
0x180024c02  jz      short loc_180024C41
0x180024c04  mov     rcx, cs:off_180049E10; "<CCollectionList::DeleteByData|ADO|ERR>"...
0x180024c0b  test    rcx, rcx
0x180024c0e  jz      short loc_180024C41
0x180024c10  mov     r8, cs:off_180049E10; "<CCollectionList::DeleteByData|ADO|ERR>"...
0x180024c17  mov     r9d, eax
0x180024c1a  mov     rcx, cs:off_180049218; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180024c21  mov     edx, 0FAC00h
0x180024c26  mov     dword ptr [rsp+130h+var_110], 3EBh
0x180024c2e  call    _bidTraceW
0x180024c33  jmp     short loc_180024C41
0x180024c35  lea     rcx, [rdi+18h]; this
0x180024c39  mov     rdx, r15; unsigned __int64
0x180024c3c  call    ?DeleteByData@CCollectionMap@@QEAAJ_K@Z; CCollectionMap::DeleteByData(unsigned __int64)
0x180024c41  mov     rax, [r14+88h]
0x180024c48  mov     rcx, r15; this
0x180024c4b  mov     rdx, [rsp+130h+var_100]
0x180024c50  mov     rdx, [rdx+278h]
0x180024c57  mov     [rdx+30h], rax
0x180024c5b  xor     edx, edx; unsigned int
0x180024c5d  mov     dword ptr [r12], 1
0x180024c65  mov     [rbx+10h], rdx
0x180024c69  mov     [rbx+8], edx
0x180024c6c  mov     rax, [r15+8]
0x180024c70  mov     [rbx], rax
0x180024c73  mov     [r15+10h], dl
0x180024c77  call    ??_GCSymbol@@QEAAPEAXI@Z; CSymbol::`scalar deleting destructor'(uint)
0x180024c7c  jmp     short loc_180024C88
0x180024c7e  xor     ebx, ebx
0x180024c80  mov     dword ptr [r12], 3
0x180024c88  mov     r9, rbx; struct XMLCHAPTER *
0x180024c8b  mov     r8, r12; struct CSymbol *
0x180024c8e  mov     rdx, r13; struct CParseNode *
0x180024c91  mov     rcx, r14; this
0x180024c94  call    ?BuildColumnDefinition@CXMLReader@@AEAAJPEAVCParseNode@@PEAVCSymbol@@PEAVXMLCHAPTER@@@Z; CXMLReader::BuildColumnDefinition(CParseNode *,CSymbol *,XMLCHAPTER *)
0x180024c99  mov     edi, eax
0x180024c9b  test    eax, eax
0x180024c9d  js      loc_180024DD4
0x180024ca3  test    rbx, rbx
0x180024ca6  jz      short loc_180024CD6
0x180024ca8  mov     rax, [rbx]
0x180024cab  mov     [r12+8], rax
0x180024cb0  jmp     short loc_180024CD6
0x180024cb2  cmp     rcx, rax
0x180024cb5  jnz     short loc_180024CD6
0x180024cb7  cmp     dword ptr [r13+8], 2
0x180024cbc  jnz     short loc_180024CD6
0x180024cbe  mov     r8, rsi; struct CXMLRowset *
0x180024cc1  mov     rdx, r13; struct CParseNode *
0x180024cc4  mov     rcx, r14; this
0x180024cc7  call    ?ProcessRowsetAttribute@CXMLReader@@AEAAJPEAVCParseNode@@PEAVCXMLRowset@@@Z; CXMLReader::ProcessRowsetAttribute(CParseNode *,CXMLRowset *)
0x180024ccc  mov     edi, eax
0x180024cce  test    eax, eax
0x180024cd0  js      loc_180024DD4
0x180024cd6  mov     r12d, dword ptr [rsp+130h+var_F8]
0x180024cdb  inc     r12d
0x180024cde  mov     dword ptr [rsp+130h+var_F8], r12d
0x180024ce3  jmp     loc_180024ADD
0x180024ce8  mov     edi, 8007000Eh
0x180024ced  jmp     loc_180024DD4
0x180024cf2  movzx   ecx, word ptr [rsi+132h]
0x180024cf9  cmp     [rsi+130h], cx
0x180024d00  jz      loc_180024D97
0x180024d06  xor     edx, edx; Val
0x180024d08  mov     dword ptr [rbp+57h+var_C8+1Ch], 0
0x180024d0f  lea     rcx, [rbp+57h+var_A0]; void *
0x180024d13  lea     r8d, [rdx+48h]; Size
0x180024d17  call    memset_0
0x180024d1c  movups  xmm0, xmmword ptr cs:DBPROPSET_ROWSET.Data1
0x180024d23  lea     rax, [rbp+57h+var_A0]
0x180024d27  mov     [rbp+57h+var_C8.cProperties], 1
0x180024d2e  lea     rcx, [rbp+57h+var_70]; pvarg
0x180024d32  mov     [rbp+57h+var_C8.rgProperties], rax
0x180024d36  movdqu  xmmword ptr [rbp+57h+var_C8.guidPropertySet.Data1], xmm0
0x180024d3b  mov     [rbp+57h+var_A0], 102h
0x180024d43  call    cs:__imp_VariantInit
0x180024d4a  nop     dword ptr [rax+rax+00h]
0x180024d4f  movzx   edx, word ptr [rsi+130h]
0x180024d56  lea     r9, [rbp+57h+var_C8]; struct tagDBPROPSET *
0x180024d5a  mov     eax, 3
0x180024d5f  mov     dword ptr [rsp+130h+var_108], 1; int
0x180024d67  mov     word ptr [rbp+57h+var_70], ax
0x180024d6b  lea     rcx, [rsi+190h]; this
0x180024d72  movzx   eax, word ptr [rsi+132h]
0x180024d79  mov     r8d, 1; unsigned int
0x180024d7f  sub     edx, eax; unsigned int
0x180024d81  lea     rax, [r14+1F0h]
0x180024d88  mov     [rsp+130h+var_110], rax; struct CBidGenericBase *
0x180024d8d  mov     dword ptr [rbp+57h+var_70+8], edx
0x180024d90  call    ?utlSetProperties@CUtlProps@@QEAAJKKQEBUtagDBPROPSET@@AEBVCBidGenericBase@@H@Z; CUtlProps::utlSetProperties(ulong,ulong,tagDBPROPSET const * const,CBidGenericBase const &,int)
0x180024d95  mov     edi, eax
0x180024d97  cmp     byte ptr [r14+1D8h], 0
0x180024d9f  jnz     short loc_180024DC2
0x180024da1  mov     rcx, rsi; this
0x180024da4  call    ?AllColumnsInitialized@CXMLRowset@@QEAAHXZ; CXMLRowset::AllColumnsInitialized(void)
0x180024da9  test    eax, eax
0x180024dab  jnz     short loc_180024DC2
0x180024dad  mov     edx, 91h; unsigned int
0x180024db2  mov     ecx, 80004005h; int
0x180024db7  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x180024dbc  mov     edi, eax
0x180024dbe  test    eax, eax
0x180024dc0  js      short loc_180024DD4
0x180024dc2  mov     rax, [r14+88h]
0x180024dc9  mov     rcx, [rax+30h]
0x180024dcd  mov     [r14+88h], rcx
0x180024dd4  mov     eax, edi
0x180024dd6  jmp     short loc_180024DDD
0x180024dd8  mov     eax, 8007000Eh
0x180024ddd  mov     rcx, [rbp+57h+var_50]
0x180024de1  xor     rcx, rsp; StackCookie
  ... truncated ...
```
