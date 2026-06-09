# CRecFields::Delete(tagVARIANT)

- ea: `0x18009d5f0`
- end: `0x18009dabb`
- name: `?Delete@CRecFields@@UEAAJUtagVARIANT@@@Z`
- size: `1227`
- prototype: `__int64 __fastcall(CRecFields *__hidden this, struct tagVARIANT *__struct_ptr)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18008b210`

## callees

- `0x180009240`
- `0x18000bbc0`
- `0x180011700`
- `0x180020e20`
- `0x180027790`
- `0x18006a22c`
- `0x18009d5f0`
- `0x18009f2d0`
- `0x1800c8ebc`
- `0x1800c8f34`
- `0x1800d0010`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x18009d8bc`
- `OLEAUT32!__imp_SysStringLen` at `0x18009d8bc`
- `OLEAUT32!__imp_VariantInit` at `0x18009d8e5`
- `OLEAUT32!__imp_VariantInit` at `0x18009d8e5`

## string_xrefs

- `0x18009d6e8`: `<CRecFields::Delete|ADO|ERR> %u#, line %d\n`
- `0x18009d7fc`: `<CRecFields::Delete|ADO|ERR> %u#, line %d\n`
- `0x18009d97c`: `<CRecFields::Delete|ADO|ERR> %u#, line %d\n`
- `0x18009d70b`: `<CRecFields::Delete|ADO|ERR>  line %d\n`
- `0x18009d9e5`: `<CRecFields::Delete|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n`
- `0x18009da0f`: `<CRecFields::Delete|ADO|ERR> 0x%08x{HRESULT} line %d\n`

## pseudocode

```c
__int64 __fastcall CRecFields::Delete(CBidGenericBase **this, struct tagVARIANT *a2)
{
  unsigned int BidObjectID; // eax
  LONGLONG llVal; // rax
  __int64 v6; // r9
  __int64 v7; // r9
  __int64 v8; // rdx
  struct CStdComObjectRoot *v9; // rcx
  char *v10; // rax
  char *v11; // rax
  __int64 v12; // r9
  struct CStdComObjectRoot *v13; // rax
  struct CStdComObjectRoot *v14; // rax
  char *v15; // rcx
  struct CStdComObjectRoot *v16; // rax
  OLECHAR *bstrVal; // rcx
  OLECHAR *v18; // rdx
  __int64 v19; // r9
  unsigned int v20; // ebx
  unsigned int v21; // eax
  int v22; // ebx
  unsigned int v23; // eax
  unsigned int v24; // ebx
  __int64 v26; // [rsp+20h] [rbp-59h]
  VARIANTARG pvarg; // [rsp+40h] [rbp-39h] BYREF
  struct tagVARIANT v28; // [rsp+60h] [rbp-19h] BYREF
  _BYTE v29[32]; // [rsp+80h] [rbp+7h] BYREF
  unsigned __int64 v30; // [rsp+A0h] [rbp+27h]
  int v31; // [rsp+A8h] [rbp+2Fh]
  int v32; // [rsp+E0h] [rbp+67h] BYREF
  struct CStdComObjectRoot *v33; // [rsp+E8h] [rbp+6Fh] BYREF
  __int64 v34; // [rsp+F0h] [rbp+77h] BYREF
  struct ADOField *v35; // [rsp+F8h] [rbp+7Fh] BYREF

  v34 = -1;
  if ( (bidGblFlags & 4) != 0 && off_18012ABA8[0] )
  {
    BidObjectID = CBidGenericBase::GetBidObjectID(this[18]);
    bidScopeEnterW(&v34, off_18012ABA8[0], BidObjectID, a2, v26);
  }
  v33 = 0;
  v30 = (unsigned __int64)(this + 1) & -(__int64)(this != 0);
  CContext::Init((CContext *)v29);
  while ( a2->vt == 16396 )
  {
    llVal = a2->llVal;
    if ( !llVal )
      break;
    *(_OWORD *)&a2->vt = *(_OWORD *)llVal;
    a2->pRecInfo = *(IRecordInfo **)(llVal + 16);
  }
  v32 = CStdCollection::Refresh(this + 1, 0, 1u);
  if ( !(unsigned int)CContext::Failed((CContext *)v29, &v32) )
  {
    v32 = (*((__int64 (__fastcall **)(char *, struct tagVARIANT *, struct CStdComObjectRoot **))this[1] + 30))(
            (char *)this + 8,
            a2,
            &v33);
    if ( (unsigned int)CContext::Failed((CContext *)v29, &v32) )
    {
      if ( v31 != -2146825023 || a2->vt != 8 || (bstrVal = a2->bstrVal) == 0 || !SysStringLen(bstrVal) )
      {
        v20 = v31;
        if ( v31 < 0 )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_59;
          if ( (unsigned int)CBidGenericBase::GetBidObjectID(this[18]) == -1 )
          {
            LODWORD(v26) = 1531;
            bidTraceW(off_18012A200[0], 1567753, L"<CRecFields::Delete|ADO|ERR> 0x%08x{HRESULT} line %d\n", v20, v26);
          }
          else
          {
            v21 = CBidGenericBase::GetBidObjectID(this[18]);
            LODWORD(v26) = v20;
            bidTraceW(
              off_18012A200[0],
              1567753,
              L"<CRecFields::Delete|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
              v21,
              v26,
              1531);
          }
        }
        goto LABEL_56;
      }
      memset(&pvarg, 0, sizeof(pvarg));
      v35 = 0;
      VariantInit(&pvarg);
      v18 = a2->bstrVal;
      v28 = pvarg;
      v32 = CRecFields::InternalAppend((CRecFields *)this, v18, adVariant, 24, adFldUnspecified, &v28, &v35);
      if ( !(unsigned int)CContext::Failed((CContext *)v29, &v32) )
      {
        *((_DWORD *)v35 + 45) = 0x100000;
        goto LABEL_56;
      }
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_59;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID(this[18]) != -1 )
      {
        v19 = (unsigned int)CBidGenericBase::GetBidObjectID(this[18]);
        LODWORD(v26) = 1525;
        bidTraceW(off_18012A200[0], 1561609, L"<CRecFields::Delete|ADO|ERR> %u#, line %d\n", v19, v26);
        goto LABEL_56;
      }
      v7 = 1525;
      v8 = 1561609;
    }
    else
    {
      v9 = v33;
      if ( v33 )
        v10 = (char *)v33 - 8;
      else
        v10 = 0;
      if ( *((_DWORD *)v10 + 45) != 0x10000 )
      {
        v11 = v33 ? (char *)v33 - 8 : 0LL;
        if ( *((_DWORD *)v11 + 45) != 0x100000 )
        {
          if ( v33 )
            v9 = (struct CStdComObjectRoot *)((char *)v33 - 8);
          *((_DWORD *)v9 + 45) = 0x20000;
          goto LABEL_56;
        }
      }
      (*(void (**)(void))(*(_QWORD *)v33 + 80LL))();
      v32 = CStdCollection::Delete((CStdCollection *)(this + 1), v33);
      if ( !(unsigned int)CContext::Failed((CContext *)v29, &v32) )
      {
        v13 = v33;
        if ( v33 )
          v13 = (struct CStdComObjectRoot *)((char *)v33 - 8);
        *((_DWORD *)v13 + 45) = 0x80000;
        v14 = v33;
        if ( v33 )
          v14 = (struct CStdComObjectRoot *)((char *)v33 - 8);
        *((_QWORD *)v14 + 43) = this;
        if ( v33 )
          v15 = (char *)v33 - 8;
        else
          v15 = 0;
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v15 + 43) + 8LL))(*((_QWORD *)v15 + 43));
        v16 = v33;
        if ( v33 )
          v16 = (struct CStdComObjectRoot *)((char *)v33 - 8);
        *((_DWORD *)v16 + 46) = 0;
        (*(void (__fastcall **)(struct CStdComObjectRoot *))(*(_QWORD *)v33 + 88LL))(v33);
        goto LABEL_56;
      }
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_59;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID(this[18]) != -1 )
      {
        v12 = (unsigned int)CBidGenericBase::GetBidObjectID(this[18]);
        LODWORD(v26) = 1506;
        bidTraceW(off_18012A200[0], 1542153, L"<CRecFields::Delete|ADO|ERR> %u#, line %d\n", v12, v26);
        goto LABEL_56;
      }
      v7 = 1506;
      v8 = 1542153;
    }
    goto LABEL_13;
  }
  if ( (bidGblFlags & 2) == 0 )
    goto LABEL_59;
  if ( (unsigned int)CBidGenericBase::GetBidObjectID(this[18]) == -1 )
  {
    v7 = 1499;
    v8 = 1534985;
LABEL_13:
    bidTraceW(off_18012A200[0], v8, L"<CRecFields::Delete|ADO|ERR>  line %d\n", v7);
    goto LABEL_56;
  }
  v6 = (unsigned int)CBidGenericBase::GetBidObjectID(this[18]);
  LODWORD(v26) = 1499;
  bidTraceW(off_18012A200[0], 1534985, L"<CRecFields::Delete|ADO|ERR> %u#, line %d\n", v6, v26);
LABEL_56:
  if ( (bidGblFlags & 2) != 0 && off_18012A660[0] )
  {
    v22 = v31;
    v23 = CBidGenericBase::GetBidObjectID(this[18]);
    LODWORD(v26) = v22;
    bidTraceW(off_18012A200[0], 1571840, off_18012A660[0], v23, v26);
  }
LABEL_59:
  if ( (bidGblFlags & 4) != 0 && v34 != -1 && bidID != -1 )
    ((void (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *))off_180121248[0])(bidID, 0, 0, &v34);
  v24 = v31;
  CContext::~CContext((CContext *)v29);
  return v24;
}

```

## disassembly

```asm
0x18009d5f0  push    rbp
0x18009d5f2  push    rbx
0x18009d5f3  push    rdi
0x18009d5f4  push    r14
0x18009d5f6  lea     rbp, [rsp-3Fh]
0x18009d5fb  sub     rsp, 0B8h
0x18009d602  test    byte ptr cs:_bidGblFlags, 4
0x18009d609  mov     rbx, rdx
0x18009d60c  mov     rdi, rcx
0x18009d60f  mov     [rbp+57h+arg_10], 0FFFFFFFFFFFFFFFFh
0x18009d617  jz      short loc_18009D647
0x18009d619  mov     rax, cs:off_18012ABA8; "<CRecFields::Delete|API|ADO> %u#, Index"...
0x18009d620  test    rax, rax
0x18009d623  jz      short loc_18009D647
0x18009d625  mov     rcx, [rcx+90h]; this
0x18009d62c  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18009d631  mov     rdx, cs:off_18012ABA8; "<CRecFields::Delete|API|ADO> %u#, Index"...
0x18009d638  lea     rcx, [rbp+57h+arg_10]
0x18009d63c  mov     r9, rbx
0x18009d63f  mov     r8d, eax
0x18009d642  call    _bidScopeEnterW
0x18009d647  mov     rax, rdi
0x18009d64a  mov     [rbp+57h+arg_8], 0
0x18009d652  neg     rax
0x18009d655  lea     r14, [rdi+8]
0x18009d659  sbb     rcx, rcx
0x18009d65c  and     rcx, r14
0x18009d65f  mov     [rbp+57h+var_30], rcx
0x18009d663  lea     rcx, [rbp+57h+var_50]; this
0x18009d667  call    ?Init@CContext@@QEAAXXZ; CContext::Init(void)
0x18009d66c  mov     ecx, 400Ch
0x18009d671  jmp     short loc_18009D68C
0x18009d673  mov     rax, [rbx+8]
0x18009d677  test    rax, rax
0x18009d67a  jz      short loc_18009D691
0x18009d67c  movups  xmm0, xmmword ptr [rax]
0x18009d67f  movups  xmmword ptr [rbx], xmm0
0x18009d682  movsd   xmm1, qword ptr [rax+10h]
0x18009d687  movsd   qword ptr [rbx+10h], xmm1
0x18009d68c  cmp     [rbx], cx
0x18009d68f  jz      short loc_18009D673
0x18009d691  xor     edx, edx; void *
0x18009d693  mov     rcx, r14; this
0x18009d696  lea     r8d, [rdx+1]; __int16
0x18009d69a  call    ?Refresh@CStdCollection@@UEAAJPEAXF@Z; CStdCollection::Refresh(void *,short)
0x18009d69f  lea     rdx, [rbp+57h+arg_0]; int *
0x18009d6a3  mov     [rbp+57h+arg_0], eax
0x18009d6a6  lea     rcx, [rbp+57h+var_50]; this
0x18009d6aa  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x18009d6af  test    eax, eax
0x18009d6b1  jz      short loc_18009D71C
0x18009d6b3  test    byte ptr cs:_bidGblFlags, 2
0x18009d6ba  jz      loc_18009DA6D
0x18009d6c0  mov     rcx, [rdi+90h]; this
0x18009d6c7  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18009d6cc  cmp     eax, 0FFFFFFFFh
0x18009d6cf  jz      short loc_18009D6F9
0x18009d6d1  mov     rcx, [rdi+90h]; this
0x18009d6d8  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18009d6dd  mov     r9d, eax
0x18009d6e0  mov     dword ptr [rsp+0D0h+var_B0], 5DBh
0x18009d6e8  lea     r8, aCrecfieldsDele_0; "<CRecFields::Delete|ADO|ERR> %u#, line "...
0x18009d6ef  mov     edx, 176C09h
0x18009d6f4  jmp     loc_18009DA1E
0x18009d6f9  mov     r9d, 5DBh
0x18009d6ff  mov     edx, 176C09h
0x18009d704  mov     rcx, cs:off_18012A200; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18009d70b  lea     r8, aCrecfieldsDele_4; "<CRecFields::Delete|ADO|ERR>  line %d\n"
0x18009d712  call    _bidTraceW
0x18009d717  jmp     loc_18009DA2A
0x18009d71c  mov     rax, [r14]
0x18009d71f  lea     r8, [rbp+57h+arg_8]
0x18009d723  mov     rdx, rbx
0x18009d726  mov     rcx, r14
0x18009d729  mov     rax, [rax+0F0h]
0x18009d730  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d735  lea     rdx, [rbp+57h+arg_0]; int *
0x18009d739  mov     [rbp+57h+arg_0], eax
0x18009d73c  lea     rcx, [rbp+57h+var_50]; this
0x18009d740  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x18009d745  test    eax, eax
0x18009d747  jnz     loc_18009D898
0x18009d74d  mov     rcx, [rbp+57h+arg_8]
0x18009d751  test    rcx, rcx
0x18009d754  jz      short loc_18009D75C
0x18009d756  lea     rax, [rcx-8]
0x18009d75a  jmp     short loc_18009D75E
0x18009d75c  xor     eax, eax
0x18009d75e  cmp     dword ptr [rax+0B4h], 10000h
0x18009d768  jz      short loc_18009D79B
0x18009d76a  test    rcx, rcx
0x18009d76d  jz      short loc_18009D775
0x18009d76f  lea     rax, [rcx-8]
0x18009d773  jmp     short loc_18009D777
0x18009d775  xor     eax, eax
0x18009d777  cmp     dword ptr [rax+0B4h], 100000h
0x18009d781  jz      short loc_18009D79B
0x18009d783  test    rcx, rcx
0x18009d786  jz      short loc_18009D78C
0x18009d788  add     rcx, 0FFFFFFFFFFFFFFF8h
0x18009d78c  mov     dword ptr [rcx+0B4h], 20000h
0x18009d796  jmp     loc_18009DA2A
0x18009d79b  mov     rax, [rcx]
0x18009d79e  mov     rax, [rax+50h]
0x18009d7a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d7a7  mov     rdx, [rbp+57h+arg_8]; struct CStdComObjectRoot *
0x18009d7ab  mov     rcx, r14; this
0x18009d7ae  call    ?Delete@CStdCollection@@QEAAJPEAVCStdComObjectRoot@@@Z; CStdCollection::Delete(CStdComObjectRoot *)
0x18009d7b3  lea     rdx, [rbp+57h+arg_0]; int *
0x18009d7b7  mov     [rbp+57h+arg_0], eax
0x18009d7ba  lea     rcx, [rbp+57h+var_50]; this
0x18009d7be  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x18009d7c3  test    eax, eax
0x18009d7c5  jz      short loc_18009D81D
0x18009d7c7  test    byte ptr cs:_bidGblFlags, 2
0x18009d7ce  jz      loc_18009DA6D
0x18009d7d4  mov     rcx, [rdi+90h]; this
0x18009d7db  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18009d7e0  cmp     eax, 0FFFFFFFFh
0x18009d7e3  jz      short loc_18009D80D
0x18009d7e5  mov     rcx, [rdi+90h]; this
0x18009d7ec  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18009d7f1  mov     r9d, eax
0x18009d7f4  mov     dword ptr [rsp+0D0h+var_B0], 5E2h
0x18009d7fc  lea     r8, aCrecfieldsDele_0; "<CRecFields::Delete|ADO|ERR> %u#, line "...
0x18009d803  mov     edx, 178809h
0x18009d808  jmp     loc_18009DA1E
0x18009d80d  mov     r9d, 5E2h
0x18009d813  mov     edx, 178809h
0x18009d818  jmp     loc_18009D704
0x18009d81d  mov     rax, [rbp+57h+arg_8]
0x18009d821  test    rax, rax
0x18009d824  jz      short loc_18009D82A
0x18009d826  add     rax, 0FFFFFFFFFFFFFFF8h
0x18009d82a  mov     dword ptr [rax+0B4h], 80000h
0x18009d834  mov     rax, [rbp+57h+arg_8]
0x18009d838  test    rax, rax
0x18009d83b  jz      short loc_18009D841
0x18009d83d  add     rax, 0FFFFFFFFFFFFFFF8h
0x18009d841  mov     [rax+158h], rdi
0x18009d848  mov     rax, [rbp+57h+arg_8]
0x18009d84c  test    rax, rax
0x18009d84f  jz      short loc_18009D857
0x18009d851  lea     rcx, [rax-8]
0x18009d855  jmp     short loc_18009D859
0x18009d857  xor     ecx, ecx
0x18009d859  mov     rcx, [rcx+158h]
0x18009d860  mov     rax, [rcx]
0x18009d863  mov     rax, [rax+8]
0x18009d867  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d86c  mov     rax, [rbp+57h+arg_8]
0x18009d870  test    rax, rax
0x18009d873  jz      short loc_18009D879
0x18009d875  add     rax, 0FFFFFFFFFFFFFFF8h
0x18009d879  mov     dword ptr [rax+0B8h], 0
0x18009d883  mov     rcx, [rbp+57h+arg_8]
0x18009d887  mov     rax, [rcx]
0x18009d88a  mov     rax, [rax+58h]
0x18009d88e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d893  jmp     loc_18009DA2A
0x18009d898  cmp     [rbp+57h+var_28], 800A0CC1h
0x18009d89f  jnz     loc_18009D9AD
0x18009d8a5  cmp     word ptr [rbx], 8
0x18009d8a9  jnz     loc_18009D9AD
0x18009d8af  mov     rcx, [rbx+8]; pbstr
0x18009d8b3  test    rcx, rcx
0x18009d8b6  jz      loc_18009D9AD
0x18009d8bc  call    cs:__imp_SysStringLen
0x18009d8c3  nop     dword ptr [rax+rax+00h]
0x18009d8c8  test    eax, eax
0x18009d8ca  jz      loc_18009D9AD
0x18009d8d0  xor     eax, eax
0x18009d8d2  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18009d8d6  xorps   xmm0, xmm0
0x18009d8d9  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x18009d8dd  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18009d8e1  mov     [rbp+57h+arg_18], rax
0x18009d8e5  call    cs:__imp_VariantInit
0x18009d8ec  nop     dword ptr [rax+rax+00h]
0x18009d8f1  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x18009d8f5  lea     rax, [rbp+57h+arg_18]
0x18009d8f9  mov     rdx, [rbx+8]; pbstr
0x18009d8fd  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x18009d902  mov     r9d, 18h; __int64
0x18009d908  mov     [rsp+0D0h+var_A0], rax; struct ADOField **
0x18009d90d  mov     rcx, rdi; this
0x18009d910  lea     rax, [rbp+57h+var_70]
0x18009d914  movaps  xmmword ptr [rbp+57h+var_70], xmm0
0x18009d918  mov     [rsp+0D0h+var_A8], rax; struct tagVARIANT
0x18009d91d  lea     r8d, [r9-0Ch]; enum DataTypeEnum
0x18009d921  mov     dword ptr [rsp+0D0h+var_B0], 0FFFFFFFFh; enum FieldAttributeEnum
0x18009d929  movsd   qword ptr [rbp+57h+var_70+10h], xmm1
0x18009d92e  call    ?InternalAppend@CRecFields@@AEAAJPEAGW4DataTypeEnum@@_JW4FieldAttributeEnum@@UtagVARIANT@@PEAPEAUADOField@@@Z; CRecFields::InternalAppend(ushort *,DataTypeEnum,__int64,FieldAttributeEnum,tagVARIANT,ADOField * *)
0x18009d933  lea     rdx, [rbp+57h+arg_0]; int *
0x18009d937  mov     [rbp+57h+arg_0], eax
0x18009d93a  lea     rcx, [rbp+57h+var_50]; this
0x18009d93e  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x18009d943  test    eax, eax
0x18009d945  jz      short loc_18009D99D
0x18009d947  test    byte ptr cs:_bidGblFlags, 2
0x18009d94e  jz      loc_18009DA6D
0x18009d954  mov     rcx, [rdi+90h]; this
0x18009d95b  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18009d960  cmp     eax, 0FFFFFFFFh
0x18009d963  jz      short loc_18009D98D
0x18009d965  mov     rcx, [rdi+90h]; this
0x18009d96c  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18009d971  mov     r9d, eax
0x18009d974  mov     dword ptr [rsp+0D0h+var_B0], 5F5h
0x18009d97c  lea     r8, aCrecfieldsDele_0; "<CRecFields::Delete|ADO|ERR> %u#, line "...
0x18009d983  mov     edx, 17D409h
0x18009d988  jmp     loc_18009DA1E
0x18009d98d  mov     r9d, 5F5h
0x18009d993  mov     edx, 17D409h
0x18009d998  jmp     loc_18009D704
0x18009d99d  mov     rax, [rbp+57h+arg_18]
0x18009d9a1  mov     dword ptr [rax+0B4h], 100000h
0x18009d9ab  jmp     short loc_18009DA2A
0x18009d9ad  mov     ebx, [rbp+57h+var_28]
0x18009d9b0  test    ebx, ebx
0x18009d9b2  jns     short loc_18009DA2A
0x18009d9b4  test    byte ptr cs:_bidGblFlags, 2
0x18009d9bb  jz      loc_18009DA6D
0x18009d9c1  mov     rcx, [rdi+90h]; this
0x18009d9c8  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18009d9cd  cmp     eax, 0FFFFFFFFh
0x18009d9d0  jz      short loc_18009DA07
0x18009d9d2  mov     rcx, [rdi+90h]; this
0x18009d9d9  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18009d9de  mov     rcx, cs:off_18012A200; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18009d9e5  lea     r8, aCrecfieldsDele_2; "<CRecFields::Delete|ADO|ERR> %u#,0x%08x"...
0x18009d9ec  mov     r9d, eax
0x18009d9ef  mov     dword ptr [rsp+0D0h+var_A8], 5FBh
0x18009d9f7  mov     edx, 17EC09h
0x18009d9fc  mov     dword ptr [rsp+0D0h+var_B0], ebx
0x18009da00  call    _bidTraceW
0x18009da05  jmp     short loc_18009DA2A
0x18009da07  mov     dword ptr [rsp+0D0h+var_B0], 5FBh
0x18009da0f  lea     r8, aCrecfieldsDele_3; "<CRecFields::Delete|ADO|ERR> 0x%08x{HRE"...
0x18009da16  mov     r9d, ebx
0x18009da19  mov     edx, 17EC09h
0x18009da1e  mov     rcx, cs:off_18012A200; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18009da25  call    _bidTraceW
0x18009da2a  test    byte ptr cs:_bidGblFlags, 2
0x18009da31  jz      short loc_18009DA6D
0x18009da33  mov     rax, cs:off_18012A660; "<CRecFields::Delete|API|ADO|RET> %u#, H"...
0x18009da3a  test    rax, rax
0x18009da3d  jz      short loc_18009DA6D
0x18009da3f  mov     rcx, [rdi+90h]; this
0x18009da46  mov     ebx, [rbp+57h+var_28]
0x18009da49  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18009da4e  mov     r8, cs:off_18012A660; "<CRecFields::Delete|API|ADO|RET> %u#, H"...
0x18009da55  mov     r9d, eax
0x18009da58  mov     rcx, cs:off_18012A200; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18009da5f  mov     edx, 17FC00h
0x18009da64  mov     dword ptr [rsp+0D0h+var_B0], ebx
0x18009da68  call    _bidTraceW
0x18009da6d  test    byte ptr cs:_bidGblFlags, 4
0x18009da74  jz      short loc_18009DA9F
0x18009da76  cmp     [rbp+57h+arg_10], 0FFFFFFFFFFFFFFFFh
0x18009da7b  jz      short loc_18009DA9F
0x18009da7d  mov     rcx, cs:_bidID
0x18009da84  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18009da88  jz      short loc_18009DA9F
0x18009da8a  mov     rax, cs:off_180121248
0x18009da91  lea     r9, [rbp+57h+arg_10]
0x18009da95  xor     r8d, r8d
0x18009da98  xor     edx, edx
0x18009da9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009da9f  mov     ebx, [rbp+57h+var_28]
0x18009daa2  lea     rcx, [rbp+57h+var_50]; this
0x18009daa6  call    ??1CContext@@QEAA@XZ; CContext::~CContext(void)
0x18009daab  mov     eax, ebx
0x18009daad  add     rsp, 0B8h
0x18009dab4  pop     r14
0x18009dab6  pop     rdi
0x18009dab7  pop     rbx
0x18009dab8  pop     rbp
0x18009dab9  retn
```
