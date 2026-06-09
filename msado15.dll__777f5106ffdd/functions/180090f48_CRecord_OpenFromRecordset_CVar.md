# CRecord::OpenFromRecordset(CVar &)

- ea: `0x180090f48`
- end: `0x1800913c6`
- name: `?OpenFromRecordset@CRecord@@QEAAJAEAVCVar@@@Z`
- size: `1150`
- prototype: `__int64 __fastcall(CRecord *__hidden this, struct CVar *)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x18008ea50`

## callees

- `0x180020da0`
- `0x180020e20`
- `0x180031760`
- `0x180032710`
- `0x180059ccc`
- `0x18006a22c`
- `0x18008a800`
- `0x18008b550`
- `0x180090f48`
- `0x1800ac0e0`
- `0x1800c8f34`
- `0x1800ccd14`
- `0x1800d0010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180090fac`
- `OLEAUT32!__imp_VariantInit` at `0x180090fac`
- `OLEAUT32!__imp_VariantClear` at `0x180091391`
- `OLEAUT32!__imp_VariantClear` at `0x180091391`

## string_xrefs

- `0x180091035`: `<CRecord::OpenFromRecordset|ADO|ERR> %u#, line %d\n`
- `0x1800911d8`: `<CRecord::OpenFromRecordset|ADO|ERR> %u#, line %d\n`
- `0x18009126e`: `<CRecord::OpenFromRecordset|ADO|ERR> %u#, line %d\n`
- `0x180091051`: `<CRecord::OpenFromRecordset|ADO|ERR>  line %d\n`
- `0x1800911f4`: `<CRecord::OpenFromRecordset|ADO|ERR>  line %d\n`
- `0x18009128a`: `<CRecord::OpenFromRecordset|ADO|ERR>  line %d\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRecord::OpenFromRecordset(CRecord *this, struct CVar *a2)
{
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 v5; // r9
  __int64 (__fastcall ***v6)(_QWORD, GUID *, __int64 *); // rax
  unsigned int BidObjectID; // eax
  __int64 v8; // rdx
  __int64 v9; // r9
  __int64 v10; // rdx
  unsigned int v11; // eax
  unsigned int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // r9
  __int64 v15; // rdx
  const struct CVar *v16; // rax
  struct IRow *v17; // rcx
  unsigned int v18; // ebx
  int v20; // [rsp+20h] [rbp-19h]
  int v21; // [rsp+20h] [rbp-19h]
  VARIANTARG pvarg; // [rsp+30h] [rbp-9h] BYREF
  _BYTE v23[40]; // [rsp+48h] [rbp+Fh] BYREF
  unsigned int v24; // [rsp+70h] [rbp+37h]
  CRecordset *v25; // [rsp+A0h] [rbp+67h] BYREF
  struct CVar *v26; // [rsp+A8h] [rbp+6Fh] BYREF
  __int64 v27; // [rsp+B0h] [rbp+77h] BYREF
  struct IRow *v28; // [rsp+B8h] [rbp+7Fh] BYREF

  v26 = a2;
  CXLockContext::CXLockContext(
    (CXLockContext *)v23,
    (struct CStdComObjectRoot *)(((unsigned __int64)this + 32)
                               & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64)),
    (struct CCriticalSection **)(*((_QWORD *)this + 18) + 8LL),
    (const char *)this + 32);
  v27 = 0;
  v25 = 0;
  v28 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  v6 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))CVar::operator IUnknown *((char *)this + 216, v3, v4, v5);
  LODWORD(v26) = (**v6)(v6, &IID_IADOClass, &v27);
  if ( !(unsigned int)CContext::Failed((CContext *)v23, (const int *)&v26) )
  {
    (*(void (__fastcall **)(__int64, CRecordset **))(*(_QWORD *)v27 + 24LL))(v27, &v25);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    LODWORD(v26) = (*(__int64 (__fastcall **)(CRecordset *, char *))(*(_QWORD *)v25 + 176LL))(v25, (char *)this + 568);
    if ( (unsigned int)CContext::Failed((CContext *)v23, (const int *)&v26) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_43;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
      {
        BidObjectID = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
        v20 = 1704;
        v8 = 1744905;
        goto LABEL_5;
      }
      v9 = 1704;
      v10 = 1744905;
LABEL_7:
      bidTraceW(off_18012A1E8[0], v10, L"<CRecord::OpenFromRecordset|ADO|ERR>  line %d\n", v9);
      goto LABEL_43;
    }
    LODWORD(v26) = CRecordset::GetRow(v25, &v28);
    if ( (unsigned int)CContext::Failed((CContext *)v23, (const int *)&v26) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_43;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
      {
        BidObjectID = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
        v20 = 1707;
        v8 = 1747977;
        goto LABEL_5;
      }
      v9 = 1707;
      v10 = 1747977;
      goto LABEL_7;
    }
    LODWORD(v26) = (*(__int64 (__fastcall **)(CRecordset *, VARIANTARG *))(*(_QWORD *)v25 + 96LL))(v25, &pvarg);
    if ( (unsigned int)CContext::Failed((CContext *)v23, (const int *)&v26) )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) == -1 )
        {
          bidTraceW(off_18012A1E8[0], 1749001, L"<CRecord::OpenFromRecordset|ADO|ERR>  line %d\n", 1708);
        }
        else
        {
          v11 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
          bidTraceW(off_18012A1E8[0], 1749001, L"<CRecord::OpenFromRecordset|ADO|ERR> %u#, line %d\n", v11, 1708);
        }
      }
      goto LABEL_42;
    }
    LODWORD(v26) = CRecord::Disconnect(this);
    if ( (unsigned int)CContext::Failed((CContext *)v23, (const int *)&v26) )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
        {
          v12 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
          v21 = 1713;
          v13 = 1754121;
LABEL_27:
          bidTraceW(off_18012A1E8[0], v13, L"<CRecord::OpenFromRecordset|ADO|ERR> %u#, line %d\n", v12, v21);
          goto LABEL_41;
        }
        v14 = 1713;
        v15 = 1754121;
        goto LABEL_29;
      }
    }
    else
    {
      LODWORD(v26) = CRecord::Connect(this, pvarg.punkVal);
      if ( (unsigned int)CContext::Failed((CContext *)v23, (const int *)&v26) )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_41;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
        {
          v12 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
          v21 = 1714;
          v13 = 1755145;
          goto LABEL_27;
        }
        v14 = 1714;
        v15 = 1755145;
LABEL_29:
        bidTraceW(off_18012A1E8[0], v15, L"<CRecord::OpenFromRecordset|ADO|ERR>  line %d\n", v14);
        goto LABEL_41;
      }
      v16 = (const struct CVar *)CVar::operator=((char *)this + 168, pvarg.llVal);
      if ( !(unsigned int)CContext::VariantFailed((CContext *)v23, v16) )
      {
        v17 = v28;
        *((_QWORD *)this + 34) = v28;
        ((void (__fastcall *)(struct IRow *))v17->lpVtbl->AddRef)(v17);
        goto LABEL_41;
      }
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
        {
          v12 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
          v21 = 1715;
          v13 = 1756169;
          goto LABEL_27;
        }
        v14 = 1715;
        v15 = 1756169;
        goto LABEL_29;
      }
    }
LABEL_41:
    VariantClear(&pvarg);
LABEL_42:
    ((void (__fastcall *)(struct IRow *))v28->lpVtbl->Release)(v28);
    goto LABEL_43;
  }
  if ( (bidGblFlags & 2) != 0 )
  {
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
    {
      BidObjectID = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
      v20 = 1699;
      v8 = 1739785;
LABEL_5:
      bidTraceW(off_18012A1E8[0], v8, L"<CRecord::OpenFromRecordset|ADO|ERR> %u#, line %d\n", BidObjectID, v20);
      goto LABEL_43;
    }
    v9 = 1699;
    v10 = 1739785;
    goto LABEL_7;
  }
LABEL_43:
  v18 = v24;
  CXLockContext::~CXLockContext((CXLockContext *)v23);
  return v18;
}

```

## disassembly

```asm
0x180090f48  mov     [rsp-8+arg_8], rdx
0x180090f4d  push    rbp
0x180090f4e  push    rbx
0x180090f4f  lea     rbp, [rsp-4Fh]
0x180090f54  sub     rsp, 88h
0x180090f5b  mov     rbx, rcx
0x180090f5e  mov     r8, [rcx+90h]
0x180090f65  add     r8, 8; struct CCriticalSection **
0x180090f69  mov     rax, rcx
0x180090f6c  lea     r9, [rcx+20h]; char *
0x180090f70  neg     rax
0x180090f73  sbb     rdx, rdx
0x180090f76  and     rdx, r9; struct CStdComObjectRoot *
0x180090f79  lea     rcx, [rbp+57h+var_48]; this
0x180090f7d  call    ??0CXLockContext@@QEAA@PEAVCStdComObjectRoot@@PEAPEAVCCriticalSection@@PEBD@Z; CXLockContext::CXLockContext(CStdComObjectRoot *,CCriticalSection * *,char const *)
0x180090f82  nop
0x180090f83  mov     [rbp+57h+arg_10], 0
0x180090f8b  mov     [rbp+57h+arg_0], 0
0x180090f93  mov     [rbp+57h+arg_18], 0
0x180090f9b  xorps   xmm0, xmm0
0x180090f9e  xor     eax, eax
0x180090fa0  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x180090fa4  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x180090fa8  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180090fac  call    cs:__imp_VariantInit
0x180090fb3  nop     dword ptr [rax+rax+00h]
0x180090fb8  lea     rcx, [rbx+0D8h]
0x180090fbf  call    ??BCVar@@QEAAPEAUIUnknown@@XZ; CVar::operator IUnknown *(void)
0x180090fc4  mov     r9, rax
0x180090fc7  mov     rcx, [rax]
0x180090fca  mov     rax, [rcx]
0x180090fcd  lea     r8, [rbp+57h+arg_10]
0x180090fd1  lea     rdx, IID_IADOClass
0x180090fd8  mov     rcx, r9
0x180090fdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090fe0  mov     dword ptr [rbp+57h+arg_8], eax
0x180090fe3  lea     rdx, [rbp+57h+arg_8]; int *
0x180090fe7  lea     rcx, [rbp+57h+var_48]; this
0x180090feb  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x180090ff0  test    eax, eax
0x180090ff2  jz      short loc_180091069
0x180090ff4  test    byte ptr cs:_bidGblFlags, 2
0x180090ffb  jz      loc_1800913AD
0x180091001  lea     rcx, [rbx+98h]; this
0x180091008  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18009100d  cmp     eax, 0FFFFFFFFh
0x180091010  jz      short loc_180091046
0x180091012  lea     rcx, [rbx+98h]; this
0x180091019  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18009101e  mov     [rsp+90h+var_70], 6A3h
0x180091026  mov     edx, 1A8C09h
0x18009102b  mov     rcx, cs:off_18012A1E8; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180091032  mov     r9d, eax
0x180091035  lea     r8, aCrecordOpenfro_3; "<CRecord::OpenFromRecordset|ADO|ERR> %u"...
0x18009103c  call    _bidTraceW
0x180091041  jmp     loc_1800913AD
0x180091046  mov     r9d, 6A3h
0x18009104c  mov     edx, 1A8C09h
0x180091051  lea     r8, aCrecordOpenfro; "<CRecord::OpenFromRecordset|ADO|ERR>  l"...
0x180091058  mov     rcx, cs:off_18012A1E8; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18009105f  call    _bidTraceW
0x180091064  jmp     loc_1800913AD
0x180091069  mov     rcx, [rbp+57h+arg_10]
0x18009106d  mov     rax, [rcx]
0x180091070  lea     rdx, [rbp+57h+arg_0]
0x180091074  mov     rax, [rax+18h]
0x180091078  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009107d  mov     rcx, [rbp+57h+arg_10]
0x180091081  mov     rax, [rcx]
0x180091084  mov     rax, [rax+10h]
0x180091088  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009108d  mov     rcx, [rbp+57h+arg_0]
0x180091091  mov     rax, [rcx]
0x180091094  lea     rdx, [rbx+238h]
0x18009109b  mov     rax, [rax+0B0h]
0x1800910a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800910a7  mov     dword ptr [rbp+57h+arg_8], eax
0x1800910aa  lea     rdx, [rbp+57h+arg_8]; int *
0x1800910ae  lea     rcx, [rbp+57h+var_48]; this
0x1800910b2  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800910b7  test    eax, eax
0x1800910b9  jz      short loc_180091107
0x1800910bb  test    byte ptr cs:_bidGblFlags, 2
0x1800910c2  jz      loc_1800913AD
0x1800910c8  lea     rcx, [rbx+98h]; this
0x1800910cf  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800910d4  cmp     eax, 0FFFFFFFFh
0x1800910d7  jz      short loc_1800910F7
0x1800910d9  lea     rcx, [rbx+98h]; this
0x1800910e0  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800910e5  mov     [rsp+90h+var_70], 6A8h
0x1800910ed  mov     edx, 1AA009h
0x1800910f2  jmp     loc_18009102B
0x1800910f7  mov     r9d, 6A8h
0x1800910fd  mov     edx, 1AA009h
0x180091102  jmp     loc_180091051
0x180091107  lea     rdx, [rbp+57h+arg_18]; struct IRow **
0x18009110b  mov     rcx, [rbp+57h+arg_0]; this
0x18009110f  call    ?GetRow@CRecordset@@QEAAJPEAPEAUIRow@@@Z; CRecordset::GetRow(IRow * *)
0x180091114  mov     dword ptr [rbp+57h+arg_8], eax
0x180091117  lea     rdx, [rbp+57h+arg_8]; int *
0x18009111b  lea     rcx, [rbp+57h+var_48]; this
0x18009111f  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x180091124  test    eax, eax
0x180091126  jz      short loc_180091174
0x180091128  test    byte ptr cs:_bidGblFlags, 2
0x18009112f  jz      loc_1800913AD
0x180091135  lea     rcx, [rbx+98h]; this
0x18009113c  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180091141  cmp     eax, 0FFFFFFFFh
0x180091144  jz      short loc_180091164
0x180091146  lea     rcx, [rbx+98h]; this
0x18009114d  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180091152  mov     [rsp+90h+var_70], 6ABh
0x18009115a  mov     edx, 1AAC09h
0x18009115f  jmp     loc_18009102B
0x180091164  mov     r9d, 6ABh
0x18009116a  mov     edx, 1AAC09h
0x18009116f  jmp     loc_180091051
0x180091174  mov     rcx, [rbp+57h+arg_0]
0x180091178  mov     rax, [rcx]
0x18009117b  lea     rdx, [rbp+57h+pvarg]
0x18009117f  mov     rax, [rax+60h]
0x180091183  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091188  mov     dword ptr [rbp+57h+arg_8], eax
0x18009118b  lea     rdx, [rbp+57h+arg_8]; int *
0x18009118f  lea     rcx, [rbp+57h+var_48]; this
0x180091193  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x180091198  test    eax, eax
0x18009119a  jz      short loc_180091211
0x18009119c  test    byte ptr cs:_bidGblFlags, 2
0x1800911a3  jz      loc_18009139D
0x1800911a9  lea     rcx, [rbx+98h]; this
0x1800911b0  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800911b5  cmp     eax, 0FFFFFFFFh
0x1800911b8  jz      short loc_1800911EE
0x1800911ba  lea     rcx, [rbx+98h]; this
0x1800911c1  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800911c6  mov     rcx, cs:off_18012A1E8; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800911cd  mov     [rsp+90h+var_70], 6ACh
0x1800911d5  mov     r9d, eax
0x1800911d8  lea     r8, aCrecordOpenfro_3; "<CRecord::OpenFromRecordset|ADO|ERR> %u"...
0x1800911df  mov     edx, 1AB009h
0x1800911e4  call    _bidTraceW
0x1800911e9  jmp     loc_18009139D
0x1800911ee  mov     r9d, 6ACh
0x1800911f4  lea     r8, aCrecordOpenfro; "<CRecord::OpenFromRecordset|ADO|ERR>  l"...
0x1800911fb  mov     edx, 1AB009h
0x180091200  mov     rcx, cs:off_18012A1E8; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180091207  call    _bidTraceW
0x18009120c  jmp     loc_18009139D
0x180091211  mov     rcx, rbx; this
0x180091214  call    ?Disconnect@CRecord@@AEAAJXZ; CRecord::Disconnect(void)
0x180091219  mov     dword ptr [rbp+57h+arg_8], eax
0x18009121c  lea     rdx, [rbp+57h+arg_8]; int *
0x180091220  lea     rcx, [rbp+57h+var_48]; this
0x180091224  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x180091229  test    eax, eax
0x18009122b  jz      short loc_1800912A2
0x18009122d  test    byte ptr cs:_bidGblFlags, 2
0x180091234  jz      loc_18009138D
0x18009123a  lea     rcx, [rbx+98h]; this
0x180091241  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180091246  cmp     eax, 0FFFFFFFFh
0x180091249  jz      short loc_18009127F
0x18009124b  lea     rcx, [rbx+98h]; this
0x180091252  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180091257  mov     [rsp+90h+var_70], 6B1h
0x18009125f  mov     edx, 1AC409h
0x180091264  mov     rcx, cs:off_18012A1E8; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18009126b  mov     r9d, eax
0x18009126e  lea     r8, aCrecordOpenfro_3; "<CRecord::OpenFromRecordset|ADO|ERR> %u"...
0x180091275  call    _bidTraceW
0x18009127a  jmp     loc_18009138D
0x18009127f  mov     r9d, 6B1h
0x180091285  mov     edx, 1AC409h
0x18009128a  lea     r8, aCrecordOpenfro; "<CRecord::OpenFromRecordset|ADO|ERR>  l"...
0x180091291  mov     rcx, cs:off_18012A1E8; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180091298  call    _bidTraceW
0x18009129d  jmp     loc_18009138D
0x1800912a2  mov     rdx, qword ptr [rbp+57h+pvarg+8]; struct IUnknown *
0x1800912a6  mov     rcx, rbx; this
0x1800912a9  call    ?Connect@CRecord@@AEAAJPEAUIUnknown@@@Z; CRecord::Connect(IUnknown *)
0x1800912ae  mov     dword ptr [rbp+57h+arg_8], eax
0x1800912b1  lea     rdx, [rbp+57h+arg_8]; int *
0x1800912b5  lea     rcx, [rbp+57h+var_48]; this
0x1800912b9  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800912be  test    eax, eax
0x1800912c0  jz      short loc_18009130E
0x1800912c2  test    byte ptr cs:_bidGblFlags, 2
0x1800912c9  jz      loc_18009138D
0x1800912cf  lea     rcx, [rbx+98h]; this
0x1800912d6  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800912db  cmp     eax, 0FFFFFFFFh
0x1800912de  jz      short loc_1800912FE
0x1800912e0  lea     rcx, [rbx+98h]; this
0x1800912e7  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800912ec  mov     [rsp+90h+var_70], 6B2h
0x1800912f4  mov     edx, 1AC809h
0x1800912f9  jmp     loc_180091264
0x1800912fe  mov     r9d, 6B2h
0x180091304  mov     edx, 1AC809h
0x180091309  jmp     loc_18009128A
0x18009130e  lea     rcx, [rbx+0A8h]
0x180091315  mov     rdx, qword ptr [rbp+57h+pvarg+8]
0x180091319  call    ??4CVar@@QEAAAEBV0@QEAUIDispatch@@@Z; CVar::operator=(IDispatch * const)
0x18009131e  mov     rdx, rax; struct CVar *
0x180091321  lea     rcx, [rbp+57h+var_48]; this
0x180091325  call    ?VariantFailed@CContext@@QEAAHAEBVCVar@@@Z; CContext::VariantFailed(CVar const &)
0x18009132a  test    eax, eax
0x18009132c  jz      short loc_180091376
0x18009132e  test    byte ptr cs:_bidGblFlags, 2
0x180091335  jz      short loc_18009138D
0x180091337  lea     rcx, [rbx+98h]; this
0x18009133e  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180091343  cmp     eax, 0FFFFFFFFh
0x180091346  jz      short loc_180091366
0x180091348  lea     rcx, [rbx+98h]; this
0x18009134f  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180091354  mov     [rsp+90h+var_70], 6B3h
0x18009135c  mov     edx, 1ACC09h
0x180091361  jmp     loc_180091264
0x180091366  mov     r9d, 6B3h
0x18009136c  mov     edx, 1ACC09h
0x180091371  jmp     loc_18009128A
0x180091376  mov     rcx, [rbp+57h+arg_18]
0x18009137a  mov     [rbx+110h], rcx
0x180091381  mov     rax, [rcx]
0x180091384  mov     rax, [rax+8]
0x180091388  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009138d  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180091391  call    cs:__imp_VariantClear
0x180091398  nop     dword ptr [rax+rax+00h]
0x18009139d  mov     rcx, [rbp+57h+arg_18]
0x1800913a1  mov     rax, [rcx]
0x1800913a4  mov     rax, [rax+10h]
0x1800913a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800913ad  mov     ebx, [rbp+57h+var_20]
0x1800913b0  lea     rcx, [rbp+57h+var_48]; this
0x1800913b4  call    ??1CXLockContext@@QEAA@XZ; CXLockContext::~CXLockContext(void)
0x1800913b9  mov     eax, ebx
0x1800913bb  add     rsp, 88h
0x1800913c2  pop     rbx
0x1800913c3  pop     rbp
0x1800913c4  retn
```
