# CCommand::CreateParameterEx(ushort *,DataTypeEnum,ParameterDirectionEnum,__int64,tagVARIANT,_ADOParameter * *)

- ea: `0x180025fd0`
- end: `0x1800265ca`
- name: `?CreateParameterEx@CCommand@@UEAAJPEAGW4DataTypeEnum@@W4ParameterDirectionEnum@@_JUtagVARIANT@@PEAPEAU_ADOParameter@@@Z`
- size: `1530`
- prototype: `int(CCommand *__hidden this, unsigned __int16 *, enum DataTypeEnum, enum ParameterDirectionEnum, __int64, struct tagVARIANT *__struct_ptr, struct _ADOParameter **)`
- caller_count: `0`
- callee_count: `20`
- tags: `broker_com_uri`

## callees

- `0x180009240`
- `0x18001a750`
- `0x18001a820`
- `0x18001c890`
- `0x180020e20`
- `0x180020fc0`
- `0x180025fd0`
- `0x1800265d0`
- `0x180027790`
- `0x180027810`
- `0x180050b90`
- `0x180056e84`
- `0x180059e64`
- `0x18005a094`
- `0x18005cee0`
- `0x18006a22c`
- `0x18007e3d8`
- `0x1800c8ebc`
- `0x1800c8f34`
- `0x1800d0010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x180026194`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180026194`
- `OLEAUT32!__imp_SysStringLen` at `0x180026174`
- `OLEAUT32!__imp_SysStringLen` at `0x180026174`
- `OLEAUT32!__imp_VariantInit` at `0x180026098`
- `OLEAUT32!__imp_VariantInit` at `0x180026098`

## string_xrefs

- `0x18002610d`: `<CCommand::CreateParameterEx|ADO|ERR> %u#, line %d\n`
- `0x18002623b`: `<CCommand::CreateParameterEx|ADO|ERR> %u#, line %d\n`
- `0x180026135`: `<CCommand::CreateParameterEx|ADO|ERR>  line %d\n`
- `0x180026453`: `<CCommand::CreateParameterEx|ADO|ERR>  line %d\n`

## pseudocode

```c
__int64 __fastcall CCommand::CreateParameterEx(
        CCommand *this,
        unsigned __int16 *a2,
        enum DataTypeEnum a3,
        enum ParameterDirectionEnum a4,
        __int64 a5,
        struct tagVARIANT *a6,
        struct _ADOParameter **a7)
{
  struct _ADOParameter **v11; // r12
  struct tagVARIANT *v12; // r13
  unsigned int BidObjectID; // eax
  unsigned int v14; // eax
  CParameter *v15; // rbx
  UINT Length; // eax
  signed int v17; // edi
  unsigned int v18; // eax
  __int64 v19; // rdx
  __int64 v20; // r9
  __int64 v21; // rdx
  __int64 v22; // rdx
  int v23; // ebx
  unsigned int v24; // eax
  unsigned int v25; // ebx
  struct _ADOParameter *v26; // rbx
  int v27; // edi
  unsigned int v28; // eax
  __int64 v30; // [rsp+20h] [rbp-C1h]
  enum ParameterDirectionEnum v31; // [rsp+28h] [rbp-B9h]
  __int64 v32; // [rsp+30h] [rbp-B1h]
  struct tagVARIANT *v33; // [rsp+38h] [rbp-A9h]
  struct _ADOParameter **v34; // [rsp+40h] [rbp-A1h]
  __int64 v35; // [rsp+50h] [rbp-91h] BYREF
  BSTR v36; // [rsp+58h] [rbp-89h] BYREF
  char v37; // [rsp+60h] [rbp-81h]
  _BYTE v38[32]; // [rsp+68h] [rbp-79h] BYREF
  unsigned __int64 v39; // [rsp+88h] [rbp-59h]
  int v40; // [rsp+90h] [rbp-51h]
  void **v41; // [rsp+98h] [rbp-49h] BYREF
  char v42; // [rsp+A0h] [rbp-41h]
  VARIANTARG pvarg; // [rsp+A8h] [rbp-39h] BYREF
  __int64 v44; // [rsp+C0h] [rbp-21h]
  unsigned __int16 *v45; // [rsp+C8h] [rbp-19h] BYREF
  char v46; // [rsp+D0h] [rbp-11h]
  CParameter *v47; // [rsp+130h] [rbp+4Fh] BYREF

  v39 = ((unsigned __int64)this + 32) & -(__int64)(this != 0);
  CContext::Init((CContext *)v38);
  v11 = a7;
  v12 = a6;
  v35 = -1;
  if ( (bidGblFlags & 4) != 0 && off_18012AAA8[0] )
  {
    BidObjectID = CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144));
    v34 = v11;
    v33 = v12;
    v32 = a5;
    v31 = a4;
    bidScopeEnterW(&v35, off_18012AAA8[0], BidObjectID, a2, a3);
  }
  v42 = 4;
  v41 = &CVar::`vftable';
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  pvarg.lVal = -2147352572;
  pvarg.vt = 10;
  v44 = 0;
  v47 = 0;
  v40 = ATL::CComObject<CParameter>::CreateInstance(&v47);
  if ( v40 < 0 )
  {
    CContext::PushError((CContext *)v38);
    if ( (bidGblFlags & 2) == 0 )
    {
LABEL_51:
      if ( (bidGblFlags & 4) != 0 && v35 != -1 && bidID != -1 )
        ((void (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *))off_180121248[0])(bidID, 0, 0, &v35);
      v25 = v40;
      v41 = &CVar::`vftable';
      CVar::Clear((CVar *)&v41);
      goto LABEL_64;
    }
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144)) == -1 )
    {
      bidTraceW(off_18012A1E0[0], 1448969, L"<CCommand::CreateParameterEx|ADO|ERR>  line %d\n", 1415);
    }
    else
    {
      v14 = CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144));
      LODWORD(v30) = 1415;
      bidTraceW(off_18012A1E0[0], 1448969, L"<CCommand::CreateParameterEx|ADO|ERR> %u#, line %d\n", v14, v30);
    }
LABEL_48:
    if ( (bidGblFlags & 2) != 0 && off_18012A538[0] )
    {
      v23 = v40;
      v24 = CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144));
      LODWORD(v30) = v23;
      bidTraceW(off_18012A1E0[0], 1498112, off_18012A538[0], v24, v30);
    }
    goto LABEL_51;
  }
  v15 = v47;
  (*(void (__fastcall **)(CParameter *))(*(_QWORD *)v47 + 8LL))(v47);
  v46 = 4;
  v45 = a2;
  if ( a2 && SysStringLen(a2) )
  {
    Length = CSysString::GetLength((CSysString *)&v45, 0);
    v36 = SysAllocStringLen(a2, Length);
    if ( !v36 )
    {
      v37 = 3;
      v17 = -2147024882;
      goto LABEL_15;
    }
  }
  else
  {
    v36 = 0;
  }
  v37 = 7;
  CSysString::operator=((char *)v15 + 112, &v36);
  v17 = (*((_BYTE *)v15 + 120) & 4) == 0 ? 0x8007000E : 0;
LABEL_15:
  CSysString::~CSysString((CSysString *)&v36);
  v40 = v17;
  if ( v17 < 0 )
  {
    CContext::PushError((CContext *)v38);
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_46;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144)) != -1 )
    {
      v18 = CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144));
      v19 = 1463305;
      LODWORD(v30) = 1429;
LABEL_19:
      bidTraceW(
        off_18012A1E0[0],
        v19,
        L"<CCommand::CreateParameterEx|ADO|ERR> %u#, line %d\n",
        v18,
        v30,
        v31,
        v32,
        v33,
        v34);
      goto LABEL_46;
    }
    v20 = 1429;
    v21 = 1463305;
    goto LABEL_45;
  }
  if ( a3 )
  {
    LODWORD(v47) = CParameter::SetType(v15, a3);
    if ( (unsigned int)CContext::Failed((CContext *)v38, (const int *)&v47) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_46;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144)) != -1 )
      {
        v18 = CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144));
        v19 = 1467401;
        LODWORD(v30) = 1433;
        goto LABEL_19;
      }
      v20 = 1433;
      v21 = 1467401;
      goto LABEL_45;
    }
  }
  if ( a4 != adParamInput && a4 != adParamOutput && (unsigned int)(a4 - 3) >= 2 )
  {
    v40 = -2146825287;
    CContext::PushError((CContext *)v38);
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_46;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144)) != -1 )
    {
      v18 = CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144));
      v19 = 1470473;
      LODWORD(v30) = 1436;
      goto LABEL_19;
    }
    v20 = 1436;
    v21 = 1470473;
    goto LABEL_45;
  }
  *((_DWORD *)v15 + 47) = a4;
  CParameter::MarkAccessorDirty(v15);
  v22 = a5;
  *((_BYTE *)v15 + 224) = 1;
  v40 = 0;
  LODWORD(v47) = CParameter::SetSize(v15, v22);
  if ( (unsigned int)CContext::Failed((CContext *)v38, (const int *)&v47) )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_46;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144)) != -1 )
    {
      v18 = CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144));
      v19 = 1472521;
      LODWORD(v30) = 1438;
      goto LABEL_19;
    }
    v20 = 1438;
    v21 = 1472521;
    goto LABEL_45;
  }
  CVar::operator=((CVar *)&v41);
  if ( (unsigned int)CVar::Exists((CVar *)&v41) )
  {
    LODWORD(v47) = CParameter::SetValue(v15, (const struct CVar *)&v41);
    if ( (unsigned int)CContext::Failed((CContext *)v38, (const int *)&v47) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_46;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144)) != -1 )
      {
        v18 = CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144));
        v19 = 1482761;
        LODWORD(v30) = 1448;
        goto LABEL_19;
      }
      v20 = 1448;
      v21 = 1482761;
LABEL_45:
      bidTraceW(off_18012A1E0[0], v21, L"<CCommand::CreateParameterEx|ADO|ERR>  line %d\n", v20);
LABEL_46:
      if ( v15 )
        (*(void (__fastcall **)(CParameter *))(*(_QWORD *)v15 + 16LL))(v15);
      goto LABEL_48;
    }
  }
  *v11 = v15;
  if ( (bidGblFlags & 2) != 0 && off_18012A550[0] )
  {
    v26 = *v11;
    v27 = v40;
    v28 = CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144));
    LODWORD(v30) = v27;
    bidTraceW(off_18012A1E0[0], 1490944, off_18012A550[0], v28, v30, v26);
  }
  if ( (bidGblFlags & 4) != 0 && v35 != -1 && bidID != -1 )
    ((void (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *))off_180121248[0])(bidID, 0, 0, &v35);
  v25 = v40;
  v41 = &CVar::`vftable';
  CVar::Clear((CVar *)&v41);
  CSysString::~CSysString((CSysString *)&v45);
LABEL_64:
  CContext::~CContext((CContext *)v38);
  return v25;
}

```

## disassembly

```asm
0x180025fd0  push    rbp
0x180025fd2  push    rbx
0x180025fd3  push    rsi
0x180025fd4  push    rdi
0x180025fd5  push    r12
0x180025fd7  push    r13
0x180025fd9  push    r14
0x180025fdb  push    r15
0x180025fdd  lea     rbp, [rsp-7]
0x180025fe2  sub     rsp, 0E8h
0x180025fe9  mov     rax, rcx
0x180025fec  lea     r11, [rcx+20h]
0x180025ff0  neg     rax
0x180025ff3  mov     rsi, rcx
0x180025ff6  lea     rcx, [rbp+3Fh+var_B8]; this
0x180025ffa  mov     r14d, r9d
0x180025ffd  sbb     r10, r10
0x180026000  mov     r15d, r8d
0x180026003  and     r10, r11
0x180026006  mov     rdi, rdx
0x180026009  mov     [rbp+3Fh+var_98], r10
0x18002600d  call    ?Init@CContext@@QEAAXXZ; CContext::Init(void)
0x180026012  test    byte ptr cs:_bidGblFlags, 4
0x180026019  mov     r12, [rbp+3Fh+arg_30]
0x18002601d  mov     r13, [rbp+3Fh+arg_28]
0x180026021  mov     [rsp+120h+var_D0], 0FFFFFFFFFFFFFFFFh
0x18002602a  jz      short loc_180026078
0x18002602c  mov     rax, cs:off_18012AAA8; "<CCommand::CreateParameterEx|API|ADO> %"...
0x180026033  test    rax, rax
0x180026036  jz      short loc_180026078
0x180026038  lea     rcx, [rsi+90h]; this
0x18002603f  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180026044  mov     rcx, [rbp+3Fh+arg_20]
0x180026048  mov     r9, rdi
0x18002604b  mov     rdx, cs:off_18012AAA8; "<CCommand::CreateParameterEx|API|ADO> %"...
0x180026052  mov     r8d, eax
0x180026055  mov     [rsp+120h+var_E0], r12
0x18002605a  mov     [rsp+120h+var_E8], r13
0x18002605f  mov     [rsp+120h+var_F0], rcx
0x180026064  lea     rcx, [rsp+120h+var_D0]
0x180026069  mov     dword ptr [rsp+120h+var_F8], r14d
0x18002606e  mov     dword ptr [rsp+120h+var_100], r15d
0x180026073  call    _bidScopeEnterW
0x180026078  lea     rax, ??_7CVar@@6B@; const CVar::`vftable'
0x18002607f  mov     [rbp+3Fh+var_80], 4
0x180026083  mov     [rbp+3Fh+var_88], rax
0x180026087  lea     rcx, [rbp+3Fh+pvarg]; pvarg
0x18002608b  xor     eax, eax
0x18002608d  xorps   xmm0, xmm0
0x180026090  mov     qword ptr [rbp+3Fh+pvarg+10h], rax
0x180026094  movups  xmmword ptr [rbp+3Fh+pvarg], xmm0
0x180026098  call    cs:__imp_VariantInit
0x18002609f  nop     dword ptr [rax+rax+00h]
0x1800260a4  mov     eax, 0Ah
0x1800260a9  mov     dword ptr [rbp+3Fh+pvarg+8], 80020004h
0x1800260b0  lea     rcx, [rbp+3Fh+arg_0]
0x1800260b4  mov     word ptr [rbp+3Fh+pvarg], ax
0x1800260b8  mov     [rbp+3Fh+var_60], 0
0x1800260c0  mov     [rbp+3Fh+arg_0], 0
0x1800260c8  call    ?CreateInstance@?$CComObject@VCParameter@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CParameter>::CreateInstance(ATL::CComObject<CParameter> * *)
0x1800260cd  mov     [rbp+3Fh+var_90], eax
0x1800260d0  test    eax, eax
0x1800260d2  jns     short loc_180026151
0x1800260d4  lea     rcx, [rbp+3Fh+var_B8]; this
0x1800260d8  call    ?PushError@CContext@@QEAAHXZ; CContext::PushError(void)
0x1800260dd  test    byte ptr cs:_bidGblFlags, 2
0x1800260e4  jz      loc_1800264B6
0x1800260ea  lea     rbx, [rsi+90h]
0x1800260f1  mov     rcx, rbx; this
0x1800260f4  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800260f9  cmp     eax, 0FFFFFFFFh
0x1800260fc  jz      short loc_18002612E
0x1800260fe  mov     rcx, rbx; this
0x180026101  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180026106  mov     rcx, cs:off_18012A1E0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18002610d  lea     r8, aCcommandCreate; "<CCommand::CreateParameterEx|ADO|ERR> %"...
0x180026114  mov     r9d, eax
0x180026117  mov     dword ptr [rsp+120h+var_100], 587h
0x18002611f  mov     edx, 161C09h
0x180026124  call    _bidTraceW
0x180026129  jmp     loc_180026473
0x18002612e  mov     rcx, cs:off_18012A1E0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180026135  lea     r8, aCcommandCreate_2; "<CCommand::CreateParameterEx|ADO|ERR>  "...
0x18002613c  mov     r9d, 587h
0x180026142  mov     edx, 161C09h
0x180026147  call    _bidTraceW
0x18002614c  jmp     loc_180026473
0x180026151  mov     rbx, [rbp+3Fh+arg_0]
0x180026155  mov     rcx, rbx
0x180026158  mov     rax, [rbx]
0x18002615b  mov     rax, [rax+8]
0x18002615f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026164  mov     [rbp+3Fh+var_50], 4
0x180026168  mov     [rbp+3Fh+var_58], rdi
0x18002616c  test    rdi, rdi
0x18002616f  jz      short loc_1800261B6
0x180026171  mov     rcx, rdi; pbstr
0x180026174  call    cs:__imp_SysStringLen
0x18002617b  nop     dword ptr [rax+rax+00h]
0x180026180  test    eax, eax
0x180026182  jz      short loc_1800261B6
0x180026184  xor     edx, edx; int
0x180026186  lea     rcx, [rbp+3Fh+var_58]; this
0x18002618a  call    ?GetLength@CSysString@@QEBAKH@Z; CSysString::GetLength(int)
0x18002618f  mov     edx, eax; ui
0x180026191  mov     rcx, rdi; strIn
0x180026194  call    cs:__imp_SysAllocStringLen
0x18002619b  nop     dword ptr [rax+rax+00h]
0x1800261a0  mov     [rsp+120h+var_C8], rax
0x1800261a5  test    rax, rax
0x1800261a8  jnz     short loc_1800261BF
0x1800261aa  mov     [rsp+120h+var_C0], 3
0x1800261af  mov     edi, 8007000Eh
0x1800261b4  jmp     short loc_1800261E4
0x1800261b6  mov     [rsp+120h+var_C8], 0
0x1800261bf  lea     rcx, [rbx+70h]
0x1800261c3  mov     [rsp+120h+var_C0], 7
0x1800261c8  lea     rdx, [rsp+120h+var_C8]
0x1800261cd  call    ??4CSysString@@QEAAAEBV0@AEBV0@@Z; CSysString::operator=(CSysString const &)
0x1800261d2  mov     al, [rbx+78h]
0x1800261d5  mov     edi, 8007000Eh
0x1800261da  and     al, 4
0x1800261dc  neg     al
0x1800261de  sbb     ecx, ecx
0x1800261e0  not     ecx
0x1800261e2  and     edi, ecx
0x1800261e4  lea     rcx, [rsp+120h+var_C8]; this
0x1800261e9  call    ??1CSysString@@QEAA@XZ; CSysString::~CSysString(void)
0x1800261ee  mov     [rbp+3Fh+var_90], edi
0x1800261f1  test    edi, edi
0x1800261f3  jns     short loc_18002625F
0x1800261f5  lea     rcx, [rbp+3Fh+var_B8]; this
0x1800261f9  call    ?PushError@CContext@@QEAAHXZ; CContext::PushError(void)
0x1800261fe  test    byte ptr cs:_bidGblFlags, 2
0x180026205  jz      loc_18002645F
0x18002620b  lea     rdi, [rsi+90h]
0x180026212  mov     rcx, rdi; this
0x180026215  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18002621a  cmp     eax, 0FFFFFFFFh
0x18002621d  jz      short loc_18002624F
0x18002621f  mov     rcx, rdi; this
0x180026222  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180026227  mov     edx, 165409h
0x18002622c  mov     dword ptr [rsp+120h+var_100], 595h
0x180026234  mov     rcx, cs:off_18012A1E0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18002623b  lea     r8, aCcommandCreate; "<CCommand::CreateParameterEx|ADO|ERR> %"...
0x180026242  mov     r9d, eax
0x180026245  call    _bidTraceW
0x18002624a  jmp     loc_18002645F
0x18002624f  mov     r9d, 595h
0x180026255  mov     edx, 165409h
0x18002625a  jmp     loc_18002644C
0x18002625f  test    r15d, r15d
0x180026262  jz      short loc_1800262CF
0x180026264  movzx   edx, r15w; __int16
0x180026268  mov     rcx, rbx; this
0x18002626b  call    ?SetType@CParameter@@QEAAJF@Z; CParameter::SetType(short)
0x180026270  lea     rdx, [rbp+3Fh+arg_0]; int *
0x180026274  mov     dword ptr [rbp+3Fh+arg_0], eax
0x180026277  lea     rcx, [rbp+3Fh+var_B8]; this
0x18002627b  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x180026280  test    eax, eax
0x180026282  jz      short loc_1800262CF
0x180026284  test    byte ptr cs:_bidGblFlags, 2
0x18002628b  jz      loc_18002645F
0x180026291  lea     rdi, [rsi+90h]
0x180026298  mov     rcx, rdi; this
0x18002629b  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800262a0  cmp     eax, 0FFFFFFFFh
0x1800262a3  jz      short loc_1800262BF
0x1800262a5  mov     rcx, rdi; this
0x1800262a8  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800262ad  mov     edx, 166409h
0x1800262b2  mov     dword ptr [rsp+120h+var_100], 599h
0x1800262ba  jmp     loc_180026234
0x1800262bf  mov     r9d, 599h
0x1800262c5  mov     edx, 166409h
0x1800262ca  jmp     loc_18002644C
0x1800262cf  mov     ecx, r14d
0x1800262d2  sub     ecx, 1
0x1800262d5  jz      short loc_180026341
0x1800262d7  sub     ecx, 1
0x1800262da  jz      short loc_180026341
0x1800262dc  sub     ecx, 1
0x1800262df  jz      short loc_180026341
0x1800262e1  cmp     ecx, 1
0x1800262e4  jz      short loc_180026341
0x1800262e6  lea     rcx, [rbp+3Fh+var_B8]; this
0x1800262ea  mov     [rbp+3Fh+var_90], 800A0BB9h
0x1800262f1  call    ?PushError@CContext@@QEAAHXZ; CContext::PushError(void)
0x1800262f6  test    byte ptr cs:_bidGblFlags, 2
0x1800262fd  jz      loc_18002645F
0x180026303  lea     rdi, [rsi+90h]
0x18002630a  mov     rcx, rdi; this
0x18002630d  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180026312  cmp     eax, 0FFFFFFFFh
0x180026315  jz      short loc_180026331
0x180026317  mov     rcx, rdi; this
0x18002631a  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18002631f  mov     edx, 167009h
0x180026324  mov     dword ptr [rsp+120h+var_100], 59Ch
0x18002632c  jmp     loc_180026234
0x180026331  mov     r9d, 59Ch
0x180026337  mov     edx, 167009h
0x18002633c  jmp     loc_18002644C
0x180026341  mov     rcx, rbx; this
0x180026344  mov     [rbx+0BCh], r14d
0x18002634b  call    ?MarkAccessorDirty@CParameter@@IEAAXXZ; CParameter::MarkAccessorDirty(void)
0x180026350  mov     rdx, [rbp+3Fh+arg_20]; __int64
0x180026354  mov     rcx, rbx; this
0x180026357  mov     byte ptr [rbx+0E0h], 1
0x18002635e  mov     [rbp+3Fh+var_90], 0
0x180026365  call    ?SetSize@CParameter@@QEAAJ_J@Z; CParameter::SetSize(__int64)
0x18002636a  lea     rdx, [rbp+3Fh+arg_0]; int *
0x18002636e  mov     dword ptr [rbp+3Fh+arg_0], eax
0x180026371  lea     rcx, [rbp+3Fh+var_B8]; this
0x180026375  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x18002637a  test    eax, eax
0x18002637c  jz      short loc_1800263C9
0x18002637e  test    byte ptr cs:_bidGblFlags, 2
0x180026385  jz      loc_18002645F
0x18002638b  lea     rdi, [rsi+90h]
0x180026392  mov     rcx, rdi; this
0x180026395  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18002639a  cmp     eax, 0FFFFFFFFh
0x18002639d  jz      short loc_1800263B9
0x18002639f  mov     rcx, rdi; this
0x1800263a2  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800263a7  mov     edx, 167809h
0x1800263ac  mov     dword ptr [rsp+120h+var_100], 59Eh
0x1800263b4  jmp     loc_180026234
0x1800263b9  mov     r9d, 59Eh
0x1800263bf  mov     edx, 167809h
0x1800263c4  jmp     loc_18002644C
0x1800263c9  mov     rdx, r13
0x1800263cc  lea     rcx, [rbp+3Fh+var_88]; this
0x1800263d0  call    ??4CVar@@QEAAAEBV0@AEBUtagVARIANT@@@Z; CVar::operator=(tagVARIANT const &)
0x1800263d5  lea     rcx, [rbp+3Fh+var_88]; this
0x1800263d9  call    ?Exists@CVar@@QEBAHXZ; CVar::Exists(void)
0x1800263de  test    eax, eax
0x1800263e0  jz      loc_180026506
0x1800263e6  lea     rdx, [rbp+3Fh+var_88]; struct CVar *
0x1800263ea  mov     rcx, rbx; this
0x1800263ed  call    ?SetValue@CParameter@@QEAAJAEBVCVar@@@Z; CParameter::SetValue(CVar const &)
0x1800263f2  lea     rdx, [rbp+3Fh+arg_0]; int *
0x1800263f6  mov     dword ptr [rbp+3Fh+arg_0], eax
0x1800263f9  lea     rcx, [rbp+3Fh+var_B8]; this
0x1800263fd  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x180026402  test    eax, eax
0x180026404  jz      loc_180026506
0x18002640a  test    byte ptr cs:_bidGblFlags, 2
0x180026411  jz      short loc_18002645F
0x180026413  lea     rdi, [rsi+90h]
0x18002641a  mov     rcx, rdi; this
0x18002641d  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180026422  cmp     eax, 0FFFFFFFFh
0x180026425  jz      short loc_180026441
0x180026427  mov     rcx, rdi; this
0x18002642a  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18002642f  mov     edx, 16A009h
0x180026434  mov     dword ptr [rsp+120h+var_100], 5A8h
0x18002643c  jmp     loc_180026234
0x180026441  mov     r9d, 5A8h
0x180026447  mov     edx, 16A009h
0x18002644c  mov     rcx, cs:off_18012A1E0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180026453  lea     r8, aCcommandCreate_2; "<CCommand::CreateParameterEx|ADO|ERR>  "...
0x18002645a  call    _bidTraceW
0x18002645f  test    rbx, rbx
0x180026462  jz      short loc_180026473
0x180026464  mov     rax, [rbx]
0x180026467  mov     rcx, rbx
0x18002646a  mov     rax, [rax+10h]
0x18002646e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026473  test    byte ptr cs:_bidGblFlags, 2
0x18002647a  jz      short loc_1800264B6
0x18002647c  mov     rax, cs:off_18012A538; "<CCommand::CreateParameterEx|API|ADO|RE"...
0x180026483  test    rax, rax
0x180026486  jz      short loc_1800264B6
0x180026488  mov     ebx, [rbp+3Fh+var_90]
0x18002648b  lea     rcx, [rsi+90h]; this
0x180026492  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180026497  mov     r8, cs:off_18012A538; "<CCommand::CreateParameterEx|API|ADO|RE"...
0x18002649e  mov     r9d, eax
0x1800264a1  mov     rcx, cs:off_18012A1E0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800264a8  mov     edx, 16DC00h
0x1800264ad  mov     dword ptr [rsp+120h+var_100], ebx
0x1800264b1  call    _bidTraceW
0x1800264b6  test    byte ptr cs:_bidGblFlags, 4
0x1800264bd  jz      short loc_1800264EA
0x1800264bf  cmp     [rsp+120h+var_D0], 0FFFFFFFFFFFFFFFFh
0x1800264c5  jz      short loc_1800264EA
0x1800264c7  mov     rcx, cs:_bidID
0x1800264ce  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800264d2  jz      short loc_1800264EA
0x1800264d4  mov     rax, cs:off_180121248
0x1800264db  lea     r9, [rsp+120h+var_D0]
0x1800264e0  xor     r8d, r8d
0x1800264e3  xor     edx, edx
0x1800264e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800264ea  mov     ebx, [rbp+3Fh+var_90]
  ... truncated ...
```
