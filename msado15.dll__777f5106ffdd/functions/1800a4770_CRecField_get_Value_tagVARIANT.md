# CRecField::get_Value(tagVARIANT *)

- ea: `0x1800a4770`
- end: `0x1800a4b52`
- name: `?get_Value@CRecField@@UEAAJPEAUtagVARIANT@@@Z`
- size: `994`
- prototype: `__int64 __fastcall(CRecField *__hidden this, VARIANTARG *pvargDest)`
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800a4b60`

## callees

- `0x180018788`
- `0x180020e20`
- `0x180031760`
- `0x180032710`
- `0x18006a22c`
- `0x18009f940`
- `0x1800a4770`
- `0x1800c8ebc`
- `0x1800c8f34`
- `0x1800ca824`
- `0x1800d0010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800a4861`
- `OLEAUT32!__imp_VariantInit` at `0x1800a4861`
- `OLEAUT32!__imp_VariantCopy` at `0x1800a48a1`
- `OLEAUT32!__imp_VariantCopy` at `0x1800a4929`
- `OLEAUT32!__imp_VariantCopy` at `0x1800a49b1`
- `OLEAUT32!__imp_VariantCopy` at `0x1800a48a1`
- `OLEAUT32!__imp_VariantCopy` at `0x1800a4929`
- `OLEAUT32!__imp_VariantCopy` at `0x1800a49b1`

## pseudocode

```c
__int64 __fastcall CRecField::get_Value(CRecField *this, VARIANTARG *pvargDest, __int64 a3, const char *a4)
{
  unsigned int BidObjectID; // eax
  unsigned int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // r9
  __int64 v10; // rdx
  int v11; // eax
  __int64 v12; // r8
  __int64 v13; // r8
  __int64 v14; // r8
  unsigned int v15; // ebx
  unsigned int v16; // eax
  unsigned int v17; // ebx
  __int64 v19; // [rsp+20h] [rbp-50h]
  _BYTE v20[40]; // [rsp+30h] [rbp-40h] BYREF
  unsigned int v21; // [rsp+58h] [rbp-18h]
  int v22; // [rsp+80h] [rbp+10h] BYREF
  __int64 v23; // [rsp+88h] [rbp+18h] BYREF

  v23 = -1;
  if ( (bidGblFlags & 4) != 0 && off_18012ABB8[0] )
  {
    BidObjectID = CBidGenericBase::GetBidObjectID((CRecField *)((char *)this + 88));
    bidScopeEnterW(&v23, off_18012ABB8[0], BidObjectID, pvargDest, v19);
  }
  CXLockContext::CXLockContext(
    (CXLockContext *)v20,
    (struct CStdComObjectRoot *)(((unsigned __int64)this + 8)
                               & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64)),
    (struct CCriticalSection **)(*((_QWORD *)this + 8) + 8LL),
    a4);
  if ( !pvargDest )
  {
    v22 = -2146825287;
    if ( (unsigned int)CContext::Failed((CContext *)v20, &v22) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_46;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecField *)((char *)this + 88)) != -1 )
      {
        v7 = CBidGenericBase::GetBidObjectID((CRecField *)((char *)this + 88));
        v8 = 422921;
        LODWORD(v19) = 413;
LABEL_9:
        bidTraceW(off_18012A200[0], v8, L"<CRecField::get_Value|ADO|ERR> %u#, line %d\n", v7, v19);
        goto LABEL_43;
      }
      v9 = 413;
      v10 = 422921;
      goto LABEL_42;
    }
  }
  VariantInit(pvargDest);
  if ( !(unsigned int)CRecField::IsPropReadable(this) )
    goto LABEL_43;
  v11 = *((_DWORD *)this + 84);
  if ( (v11 & 1) != 0 )
  {
    CVar::UpdateVariant((CRecField *)((char *)this + 192));
    v22 = VariantCopy(pvargDest, (const VARIANTARG *)(v12 + 16));
    if ( !(unsigned int)CContext::Failed((CContext *)v20, &v22) )
      goto LABEL_43;
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_46;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecField *)((char *)this + 88)) != -1 )
    {
      v7 = CBidGenericBase::GetBidObjectID((CRecField *)((char *)this + 88));
      v8 = 432137;
      LODWORD(v19) = 422;
      goto LABEL_9;
    }
    v9 = 422;
    v10 = 432137;
LABEL_42:
    bidTraceW(off_18012A200[0], v10, L"<CRecField::get_Value|ADO|ERR>  line %d\n", v9);
    goto LABEL_43;
  }
  if ( (v11 & 4) != 0 )
  {
    CVar::UpdateVariant((CRecField *)((char *)this + 240));
    v22 = VariantCopy(pvargDest, (const VARIANTARG *)(v13 + 16));
    if ( !(unsigned int)CContext::Failed((CContext *)v20, &v22) )
      goto LABEL_43;
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_46;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecField *)((char *)this + 88)) != -1 )
    {
      v7 = CBidGenericBase::GetBidObjectID((CRecField *)((char *)this + 88));
      v8 = 436233;
      LODWORD(v19) = 426;
      goto LABEL_9;
    }
    v9 = 426;
    v10 = 436233;
    goto LABEL_42;
  }
  if ( (v11 & 2) != 0 )
  {
    CVar::UpdateVariant((CRecField *)((char *)this + 288));
    v22 = VariantCopy(pvargDest, (const VARIANTARG *)(v14 + 16));
    if ( !(unsigned int)CContext::Failed((CContext *)v20, &v22) )
      goto LABEL_43;
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_46;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecField *)((char *)this + 88)) != -1 )
    {
      v7 = CBidGenericBase::GetBidObjectID((CRecField *)((char *)this + 88));
      v8 = 440329;
      LODWORD(v19) = 430;
      goto LABEL_9;
    }
    v9 = 430;
    v10 = 440329;
    goto LABEL_42;
  }
  if ( *((_DWORD *)this + 46) == 2
    || *((_DWORD *)this + 46) == 5
    || *((_DWORD *)this + 46) == 6
    || *((_DWORD *)this + 46) == 7
    || *((_DWORD *)this + 46) == 8
    || *((_DWORD *)this + 46) == 9
    || (unsigned int)(*((_DWORD *)this + 46) - 10) <= 1 )
  {
    v22 = MapOLEDBStatusToADOErrorDirect(*((_DWORD *)this + 46), (const struct OLEDBStatusMap *)qword_180111B40);
    if ( (unsigned int)CContext::Failed((CContext *)v20, &v22) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_46;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecField *)((char *)this + 88)) != -1 )
      {
        v7 = CBidGenericBase::GetBidObjectID((CRecField *)((char *)this + 88));
        v8 = 446473;
        LODWORD(v19) = 436;
        goto LABEL_9;
      }
      v9 = 436;
      v10 = 446473;
      goto LABEL_42;
    }
  }
LABEL_43:
  if ( (bidGblFlags & 2) != 0 && off_18012A670[0] )
  {
    v15 = v21;
    v16 = CBidGenericBase::GetBidObjectID((CRecField *)((char *)this + 88));
    LODWORD(v19) = v15;
    bidTraceW(off_18012A200[0], 457728, off_18012A670[0], v16, v19);
  }
LABEL_46:
  if ( (bidGblFlags & 4) != 0 && v23 != -1 && bidID != -1 )
    ((void (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *))off_180121248[0])(bidID, 0, 0, &v23);
  v17 = v21;
  CXLockContext::~CXLockContext((CXLockContext *)v20);
  return v17;
}

```

## disassembly

```asm
0x1800a4770  mov     [rsp-8+arg_10], rbx
0x1800a4775  mov     [rsp-8+arg_18], rdi
0x1800a477a  push    rbp
0x1800a477b  mov     rbp, rsp
0x1800a477e  sub     rsp, 70h
0x1800a4782  test    byte ptr cs:_bidGblFlags, 4
0x1800a4789  mov     rbx, rdx
0x1800a478c  mov     rdi, rcx
0x1800a478f  mov     [rbp+arg_8], 0FFFFFFFFFFFFFFFFh
0x1800a4797  jz      short loc_1800A47C4
0x1800a4799  mov     rax, cs:off_18012ABB8; "<CRecField::get_Value|API|ADO> %u#, pva"...
0x1800a47a0  test    rax, rax
0x1800a47a3  jz      short loc_1800A47C4
0x1800a47a5  add     rcx, 58h ; 'X'; this
0x1800a47a9  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a47ae  mov     rdx, cs:off_18012ABB8; "<CRecField::get_Value|API|ADO> %u#, pva"...
0x1800a47b5  lea     rcx, [rbp+arg_8]
0x1800a47b9  mov     r9, rbx
0x1800a47bc  mov     r8d, eax
0x1800a47bf  call    _bidScopeEnterW
0x1800a47c4  mov     r8, [rdi+40h]
0x1800a47c8  lea     rcx, [rdi+8]
0x1800a47cc  add     r8, 8; struct CCriticalSection **
0x1800a47d0  mov     rax, rdi
0x1800a47d3  neg     rax
0x1800a47d6  sbb     rdx, rdx
0x1800a47d9  and     rdx, rcx; struct CStdComObjectRoot *
0x1800a47dc  lea     rcx, [rbp+var_40]; this
0x1800a47e0  call    ??0CXLockContext@@QEAA@PEAVCStdComObjectRoot@@PEAPEAVCCriticalSection@@PEBD@Z; CXLockContext::CXLockContext(CStdComObjectRoot *,CCriticalSection * *,char const *)
0x1800a47e5  test    rbx, rbx
0x1800a47e8  jnz     short loc_1800A485E
0x1800a47ea  lea     rdx, [rbp+arg_0]; int *
0x1800a47ee  mov     [rbp+arg_0], 800A0BB9h
0x1800a47f5  lea     rcx, [rbp+var_40]; this
0x1800a47f9  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800a47fe  test    eax, eax
0x1800a4800  jz      short loc_1800A485E
0x1800a4802  test    byte ptr cs:_bidGblFlags, 2
0x1800a4809  jz      loc_1800A4AFF
0x1800a480f  lea     rcx, [rdi+58h]; this
0x1800a4813  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a4818  cmp     eax, 0FFFFFFFFh
0x1800a481b  jz      short loc_1800A484E
0x1800a481d  lea     rcx, [rdi+58h]; this
0x1800a4821  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a4826  mov     edx, 67409h
0x1800a482b  mov     [rsp+70h+var_50], 19Dh
0x1800a4833  mov     rcx, cs:off_18012A200; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800a483a  lea     r8, aCrecfieldGetVa; "<CRecField::get_Value|ADO|ERR> %u#, lin"...
0x1800a4841  mov     r9d, eax
0x1800a4844  call    _bidTraceW
0x1800a4849  jmp     loc_1800A4ABF
0x1800a484e  mov     r9d, 19Dh
0x1800a4854  mov     edx, 67409h
0x1800a4859  jmp     loc_1800A4AAC
0x1800a485e  mov     rcx, rbx; pvarg
0x1800a4861  call    cs:__imp_VariantInit
0x1800a4868  nop     dword ptr [rax+rax+00h]
0x1800a486d  mov     rcx, rdi; this
0x1800a4870  call    ?IsPropReadable@CRecField@@AEAAHXZ; CRecField::IsPropReadable(void)
0x1800a4875  test    eax, eax
0x1800a4877  jz      loc_1800A4ABF
0x1800a487d  mov     eax, [rdi+150h]
0x1800a4883  test    al, 1
0x1800a4885  jz      loc_1800A490B
0x1800a488b  lea     r8, [rdi+0C0h]
0x1800a4892  mov     rcx, r8; this
0x1800a4895  call    ?UpdateVariant@CVar@@QEAAXXZ; CVar::UpdateVariant(void)
0x1800a489a  lea     rdx, [r8+10h]; pvargSrc
0x1800a489e  mov     rcx, rbx; pvargDest
0x1800a48a1  call    cs:__imp_VariantCopy
0x1800a48a8  nop     dword ptr [rax+rax+00h]
0x1800a48ad  lea     rdx, [rbp+arg_0]; int *
0x1800a48b1  mov     [rbp+arg_0], eax
0x1800a48b4  lea     rcx, [rbp+var_40]; this
0x1800a48b8  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800a48bd  test    eax, eax
0x1800a48bf  jz      loc_1800A4ABF
0x1800a48c5  test    byte ptr cs:_bidGblFlags, 2
0x1800a48cc  jz      loc_1800A4AFF
0x1800a48d2  lea     rcx, [rdi+58h]; this
0x1800a48d6  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a48db  cmp     eax, 0FFFFFFFFh
0x1800a48de  jz      short loc_1800A48FB
0x1800a48e0  lea     rcx, [rdi+58h]; this
0x1800a48e4  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a48e9  mov     edx, 69809h
0x1800a48ee  mov     [rsp+70h+var_50], 1A6h
0x1800a48f6  jmp     loc_1800A4833
0x1800a48fb  mov     r9d, 1A6h
0x1800a4901  mov     edx, 69809h
0x1800a4906  jmp     loc_1800A4AAC
0x1800a490b  test    al, 4
0x1800a490d  jz      loc_1800A4993
0x1800a4913  lea     r8, [rdi+0F0h]
0x1800a491a  mov     rcx, r8; this
0x1800a491d  call    ?UpdateVariant@CVar@@QEAAXXZ; CVar::UpdateVariant(void)
0x1800a4922  lea     rdx, [r8+10h]; pvargSrc
0x1800a4926  mov     rcx, rbx; pvargDest
0x1800a4929  call    cs:__imp_VariantCopy
0x1800a4930  nop     dword ptr [rax+rax+00h]
0x1800a4935  lea     rdx, [rbp+arg_0]; int *
0x1800a4939  mov     [rbp+arg_0], eax
0x1800a493c  lea     rcx, [rbp+var_40]; this
0x1800a4940  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800a4945  test    eax, eax
0x1800a4947  jz      loc_1800A4ABF
0x1800a494d  test    byte ptr cs:_bidGblFlags, 2
0x1800a4954  jz      loc_1800A4AFF
0x1800a495a  lea     rcx, [rdi+58h]; this
0x1800a495e  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a4963  cmp     eax, 0FFFFFFFFh
0x1800a4966  jz      short loc_1800A4983
0x1800a4968  lea     rcx, [rdi+58h]; this
0x1800a496c  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a4971  mov     edx, 6A809h
0x1800a4976  mov     [rsp+70h+var_50], 1AAh
0x1800a497e  jmp     loc_1800A4833
0x1800a4983  mov     r9d, 1AAh
0x1800a4989  mov     edx, 6A809h
0x1800a498e  jmp     loc_1800A4AAC
0x1800a4993  test    al, 2
0x1800a4995  jz      loc_1800A4A1B
0x1800a499b  lea     r8, [rdi+120h]
0x1800a49a2  mov     rcx, r8; this
0x1800a49a5  call    ?UpdateVariant@CVar@@QEAAXXZ; CVar::UpdateVariant(void)
0x1800a49aa  lea     rdx, [r8+10h]; pvargSrc
0x1800a49ae  mov     rcx, rbx; pvargDest
0x1800a49b1  call    cs:__imp_VariantCopy
0x1800a49b8  nop     dword ptr [rax+rax+00h]
0x1800a49bd  lea     rdx, [rbp+arg_0]; int *
0x1800a49c1  mov     [rbp+arg_0], eax
0x1800a49c4  lea     rcx, [rbp+var_40]; this
0x1800a49c8  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800a49cd  test    eax, eax
0x1800a49cf  jz      loc_1800A4ABF
0x1800a49d5  test    byte ptr cs:_bidGblFlags, 2
0x1800a49dc  jz      loc_1800A4AFF
0x1800a49e2  lea     rcx, [rdi+58h]; this
0x1800a49e6  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a49eb  cmp     eax, 0FFFFFFFFh
0x1800a49ee  jz      short loc_1800A4A0B
0x1800a49f0  lea     rcx, [rdi+58h]; this
0x1800a49f4  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a49f9  mov     edx, 6B809h
0x1800a49fe  mov     [rsp+70h+var_50], 1AEh
0x1800a4a06  jmp     loc_1800A4833
0x1800a4a0b  mov     r9d, 1AEh
0x1800a4a11  mov     edx, 6B809h
0x1800a4a16  jmp     loc_1800A4AAC
0x1800a4a1b  mov     ecx, [rdi+0B8h]; unsigned int
0x1800a4a21  mov     eax, ecx
0x1800a4a23  sub     eax, 2
0x1800a4a26  jz      short loc_1800A4A4B
0x1800a4a28  sub     eax, 3
0x1800a4a2b  jz      short loc_1800A4A4B
0x1800a4a2d  sub     eax, 1
0x1800a4a30  jz      short loc_1800A4A4B
0x1800a4a32  sub     eax, 1
0x1800a4a35  jz      short loc_1800A4A4B
0x1800a4a37  sub     eax, 1
0x1800a4a3a  jz      short loc_1800A4A4B
0x1800a4a3c  sub     eax, 1
0x1800a4a3f  jz      short loc_1800A4A4B
0x1800a4a41  sub     eax, 1
0x1800a4a44  jz      short loc_1800A4A4B
0x1800a4a46  cmp     eax, 1
0x1800a4a49  jnz     short loc_1800A4ABF
0x1800a4a4b  lea     rdx, qword_180111B40; struct OLEDBStatusMap *
0x1800a4a52  call    ?MapOLEDBStatusToADOErrorDirect@@YAJKPEBUOLEDBStatusMap@@@Z; MapOLEDBStatusToADOErrorDirect(ulong,OLEDBStatusMap const *)
0x1800a4a57  lea     rdx, [rbp+arg_0]; int *
0x1800a4a5b  mov     [rbp+arg_0], eax
0x1800a4a5e  lea     rcx, [rbp+var_40]; this
0x1800a4a62  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800a4a67  test    eax, eax
0x1800a4a69  jz      short loc_1800A4ABF
0x1800a4a6b  test    byte ptr cs:_bidGblFlags, 2
0x1800a4a72  jz      loc_1800A4AFF
0x1800a4a78  lea     rcx, [rdi+58h]; this
0x1800a4a7c  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a4a81  cmp     eax, 0FFFFFFFFh
0x1800a4a84  jz      short loc_1800A4AA1
0x1800a4a86  lea     rcx, [rdi+58h]; this
0x1800a4a8a  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a4a8f  mov     edx, 6D009h
0x1800a4a94  mov     [rsp+70h+var_50], 1B4h
0x1800a4a9c  jmp     loc_1800A4833
0x1800a4aa1  mov     r9d, 1B4h
0x1800a4aa7  mov     edx, 6D009h
0x1800a4aac  mov     rcx, cs:off_18012A200; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800a4ab3  lea     r8, aCrecfieldGetVa_1; "<CRecField::get_Value|ADO|ERR>  line %d"...
0x1800a4aba  call    _bidTraceW
0x1800a4abf  test    byte ptr cs:_bidGblFlags, 2
0x1800a4ac6  jz      short loc_1800A4AFF
0x1800a4ac8  mov     rax, cs:off_18012A670; "<CRecField::get_Value|API|ADO|RET> %u#,"...
0x1800a4acf  test    rax, rax
0x1800a4ad2  jz      short loc_1800A4AFF
0x1800a4ad4  mov     ebx, [rbp+var_18]
0x1800a4ad7  lea     rcx, [rdi+58h]; this
0x1800a4adb  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a4ae0  mov     r8, cs:off_18012A670; "<CRecField::get_Value|API|ADO|RET> %u#,"...
0x1800a4ae7  mov     r9d, eax
0x1800a4aea  mov     rcx, cs:off_18012A200; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800a4af1  mov     edx, 6FC00h
0x1800a4af6  mov     [rsp+70h+var_50], ebx
0x1800a4afa  call    _bidTraceW
0x1800a4aff  test    byte ptr cs:_bidGblFlags, 4
0x1800a4b06  jz      short loc_1800A4B31
0x1800a4b08  cmp     [rbp+arg_8], 0FFFFFFFFFFFFFFFFh
0x1800a4b0d  jz      short loc_1800A4B31
0x1800a4b0f  mov     rcx, cs:_bidID
0x1800a4b16  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800a4b1a  jz      short loc_1800A4B31
0x1800a4b1c  mov     rax, cs:off_180121248
0x1800a4b23  lea     r9, [rbp+arg_8]
0x1800a4b27  xor     r8d, r8d
0x1800a4b2a  xor     edx, edx
0x1800a4b2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a4b31  mov     ebx, [rbp+var_18]
0x1800a4b34  lea     rcx, [rbp+var_40]; this
0x1800a4b38  call    ??1CXLockContext@@QEAA@XZ; CXLockContext::~CXLockContext(void)
0x1800a4b3d  lea     r11, [rsp+70h+var_s0]
0x1800a4b42  mov     eax, ebx
0x1800a4b44  mov     rbx, [r11+20h]
0x1800a4b48  mov     rdi, [r11+28h]
0x1800a4b4c  mov     rsp, r11
0x1800a4b4f  pop     rbp
0x1800a4b50  retn
```
