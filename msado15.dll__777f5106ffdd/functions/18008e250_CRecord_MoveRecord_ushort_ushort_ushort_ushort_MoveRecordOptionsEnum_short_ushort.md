# CRecord::MoveRecord(ushort *,ushort *,ushort *,ushort *,MoveRecordOptionsEnum,short,ushort * *)

- ea: `0x18008e250`
- end: `0x18008ea3a`
- name: `?MoveRecord@CRecord@@UEAAJPEAG000W4MoveRecordOptionsEnum@@FPEAPEAG@Z`
- size: `2026`
- prototype: `__int64 __usercall@<rax>(CRecord *__hidden this@<rcx>, unsigned __int16 *@<rdx>, unsigned __int16 *@<r8>, unsigned __int16 *@<r9>, unsigned __int16 *, enum MoveRecordOptionsEnum, __int16, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x18008ea40`

## callees

- `0x180020e20`
- `0x180031760`
- `0x180032710`
- `0x18004f2b0`
- `0x18006a22c`
- `0x18008e250`
- `0x180091430`
- `0x1800c8ebc`
- `0x1800c8f34`
- `0x1800ca7f4`
- `0x1800cd638`
- `0x1800cd800`
- `0x1800cd890`
- `0x1800cd920`
- `0x1800d0010`

## import_xrefs

- `MSDART!MpHeapAlloc` at `0x18008e589`
- `MSDART!MpHeapAlloc` at `0x18008e589`
- `ole32!CoTaskMemFree` at `0x18008e97a`
- `ole32!CoTaskMemFree` at `0x18008e97a`
- `OLEAUT32!__imp_SysAllocString` at `0x18008e8c3`
- `OLEAUT32!__imp_SysAllocString` at `0x18008e8c3`
- `OLEAUT32!__imp_SysStringLen` at `0x18008e320`
- `OLEAUT32!__imp_SysStringLen` at `0x18008e320`

## string_xrefs

- `0x18008e38e`: `<CRecord::MoveRecord|ADO|ERR> %u#, line %d\n`
- `0x18008e614`: `<CRecord::MoveRecord|ADO|ERR> %u#, line %d\n`
- `0x18008e676`: `<CRecord::MoveRecord|ADO|ERR> %u#, line %d\n`
- `0x18008e87f`: `<CRecord::MoveRecord|ADO|ERR> %u#, line %d\n`
- `0x18008e420`: `<CRecord::MoveRecord|ADO|ERR>  line %d\n`
- `0x18008e69e`: `<CRecord::MoveRecord|ADO|ERR>  line %d\n`
- `0x18008e6cc`: `<CRecord::MoveRecord|ADO|ERR>  line %d\n`
- `0x18008e8a5`: `<CRecord::MoveRecord|ADO|ERR>  line %d\n`

## pseudocode

```c
__int64 __fastcall CRecord::MoveRecord(
        CRecord *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        char *a4,
        unsigned __int16 *a5,
        enum MoveRecordOptionsEnum a6,
        __int16 a7,
        unsigned __int16 **a8)
{
  int v11; // r12d
  enum MoveRecordOptionsEnum v12; // r14d
  int v13; // ebx
  unsigned int BidObjectID; // eax
  unsigned int v15; // eax
  __int64 v16; // rdx
  unsigned __int16 *v17; // rbx
  int v18; // edi
  unsigned int v19; // eax
  __int64 v20; // r9
  __int64 v21; // rdx
  int v22; // edx
  int v23; // r14d
  CAuthenticateInfo *v24; // rax
  CAuthenticateInfo *v25; // rdi
  unsigned int v26; // eax
  __int64 v27; // rdx
  unsigned int v28; // eax
  __int64 v29; // r9
  __int64 v30; // rdx
  int v31; // eax
  unsigned int v32; // eax
  __int64 v33; // rdx
  __int64 v34; // r9
  __int64 v35; // rdx
  unsigned __int16 **v36; // r14
  BSTR v37; // rax
  int v38; // ebx
  unsigned int v39; // eax
  unsigned int v40; // ebx
  __int64 v42; // [rsp+20h] [rbp-99h]
  __int64 v43; // [rsp+28h] [rbp-91h]
  __int64 v44; // [rsp+30h] [rbp-89h]
  int v45; // [rsp+50h] [rbp-69h] BYREF
  __int64 v46; // [rsp+58h] [rbp-61h] BYREF
  OLECHAR *psz; // [rsp+60h] [rbp-59h] BYREF
  const OLECHAR *v48; // [rsp+68h] [rbp-51h] BYREF
  __int64 v49; // [rsp+70h] [rbp-49h] BYREF
  LPVOID pv; // [rsp+78h] [rbp-41h] BYREF
  _BYTE v51[40]; // [rsp+80h] [rbp-39h] BYREF
  int v52; // [rsp+A8h] [rbp-11h]
  unsigned int v53; // [rsp+100h] [rbp+47h] BYREF
  BSTR pbstr; // [rsp+110h] [rbp+57h] BYREF

  pbstr = a3;
  CXLockContext::CXLockContext(
    (CXLockContext *)v51,
    (struct CStdComObjectRoot *)(((unsigned __int64)this + 32)
                               & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64)),
    (struct CCriticalSection **)(*((_QWORD *)this + 18) + 8LL),
    a4);
  v11 = a7;
  v12 = a6;
  v48 = &WindowName;
  v53 = 0;
  psz = 0;
  pv = 0;
  v49 = 0;
  v46 = -1;
  if ( (bidGblFlags & 4) != 0 && off_18012AB00[0] )
  {
    v13 = (int)pbstr;
    BidObjectID = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
    LODWORD(v44) = v11;
    LODWORD(v43) = v12;
    bidScopeEnterW(&v46, off_18012AB00[0], BidObjectID, a2, v13);
  }
  if ( pbstr && SysStringLen(pbstr) || (v45 = -2146825287, !(unsigned int)CContext::Failed((CContext *)v51, &v45)) )
  {
    if ( a2 )
      v48 = a2;
    if ( !*((_QWORD *)this + 34) )
    {
      v45 = -2146824584;
      if ( (unsigned int)CContext::Failed((CContext *)v51, &v45) )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_11;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
        {
          v15 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
          v16 = 610313;
          LODWORD(v42) = 596;
          goto LABEL_10;
        }
        v20 = 596;
        v21 = 610313;
LABEL_17:
        bidTraceW(off_18012A1E8[0], v21, L"<CRecord::MoveRecord|ADO|ERR>  line %d\n", v20);
        goto LABEL_11;
      }
    }
    if ( !*((_QWORD *)this + 37) )
    {
      v45 = ((***((int (__fastcall ****)(_QWORD, GUID *, char *))this + 34))(
               *((_QWORD *)this + 34),
               &IID_IScopedOperations,
               (char *)this + 296) >> 31)
          & 0x800A0CB3;
      if ( (unsigned int)CContext::FailedDescription((CContext *)v51, &v45, 0x2729u) )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_11;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
        {
          v15 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
          v16 = 616457;
          LODWORD(v42) = 602;
          goto LABEL_10;
        }
        v20 = 602;
        v21 = 616457;
        goto LABEL_17;
      }
    }
    v22 = 0;
    if ( v12 != adMoveUnspecified )
    {
      v22 = v12 & 1 | 0x200;
      if ( (v12 & 2) == 0 )
        v22 = v12 & 1;
      if ( (v12 & 4) != 0 )
        v22 |= 0x400u;
    }
    v23 = v22 | 0x100;
    if ( !(_WORD)v11 )
      v23 = v22;
    v24 = (CAuthenticateInfo *)MpHeapAlloc(g_hHeapHandle, 10485760, 32);
    if ( v24 )
    {
      v25 = CAuthenticateInfo::CAuthenticateInfo(v24);
      if ( v25 )
        goto LABEL_41;
    }
    else
    {
      v25 = 0;
    }
    v45 = -2147024882;
    if ( (unsigned int)CContext::Failed((CContext *)v51, &v45) )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) == -1 )
        {
          bidTraceW(off_18012A1E8[0], 643081, L"<CRecord::MoveRecord|ADO|ERR>  line %d\n", 628);
        }
        else
        {
          v28 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
          LODWORD(v42) = 628;
          bidTraceW(off_18012A1E8[0], 643081, L"<CRecord::MoveRecord|ADO|ERR> %u#, line %d\n", v28, v42);
        }
      }
      goto LABEL_11;
    }
LABEL_41:
    v45 = CAuthenticateInfo::PutUserID(v25, (unsigned __int16 *)a4);
    if ( (unsigned int)CContext::Failed((CContext *)v51, &v45) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_88;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
      {
        v26 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
        v27 = 645129;
        LODWORD(v42) = 630;
LABEL_45:
        bidTraceW(off_18012A1E8[0], v27, L"<CRecord::MoveRecord|ADO|ERR> %u#, line %d\n", v26, v42, v43, v44);
        goto LABEL_88;
      }
      v29 = 630;
      v30 = 645129;
      goto LABEL_53;
    }
    v45 = CAuthenticateInfo::PutPassword(v25, a5);
    if ( (unsigned int)CContext::Failed((CContext *)v51, &v45) )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
        {
          v26 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
          v27 = 646153;
          LODWORD(v42) = 631;
          goto LABEL_45;
        }
        v29 = 631;
        v30 = 646153;
        goto LABEL_53;
      }
      goto LABEL_88;
    }
    v45 = (*(__int64 (__fastcall **)(_QWORD, __int64, const OLECHAR **, BSTR *, int, CAuthenticateInfo *, unsigned int *, OLECHAR **, LPVOID *))(**((_QWORD **)this + 37) + 40LL))(
            *((_QWORD *)this + 37),
            1,
            &v48,
            &pbstr,
            v23,
            v25,
            &v53,
            &psz,
            &pv);
    if ( v45 == -2147217887 )
      v45 = MapOLEDBStatusToADOError(v53, (const struct OLEDBStatusMap *)&g_MoveRowStatusMap);
    if ( (unsigned int)CContext::Failed((CContext *)v51, &v45) )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
        {
          v26 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
          v27 = 656393;
          LODWORD(v42) = 641;
          goto LABEL_45;
        }
        v29 = 641;
        v30 = 656393;
LABEL_53:
        bidTraceW(off_18012A1E8[0], v30, L"<CRecord::MoveRecord|ADO|ERR>  line %d\n", v29);
      }
LABEL_88:
      if ( v25 )
        CAuthenticateInfo::Release(v25);
      goto LABEL_11;
    }
    if ( v52 == 265946
      && v53 <= 0x19
      && (v31 = 41878016, _bittest(&v31, v53))
      && (v45 = MapOLEDBStatusToADOError(v53, (const struct OLEDBStatusMap *)&g_MoveRowStatusMap),
          (unsigned int)CContext::Failed((CContext *)v51, &v45)) )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
        {
          v32 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
          v33 = 660489;
          LODWORD(v42) = 645;
LABEL_73:
          bidTraceW(off_18012A1E8[0], v33, L"<CRecord::MoveRecord|ADO|ERR> %u#, line %d\n", v32, v42);
          goto LABEL_87;
        }
        v34 = 645;
        v35 = 660489;
        goto LABEL_75;
      }
    }
    else
    {
      v36 = a8;
      if ( !a8
        || (v37 = SysAllocString(psz), (*v36 = v37) != 0)
        || !psz
        || (v45 = -2147024882, !(unsigned int)CContext::Failed((CContext *)v51, &v45)) )
      {
        if ( (***((int (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 34))(
               *((_QWORD *)this + 34),
               &IID_IUnknown,
               &v49) >= 0 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
        else
          CRecord::Reset(this);
        goto LABEL_87;
      }
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
        {
          v32 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
          v33 = 667657;
          LODWORD(v42) = 652;
          goto LABEL_73;
        }
        v34 = 652;
        v35 = 667657;
LABEL_75:
        bidTraceW(off_18012A1E8[0], v35, L"<CRecord::MoveRecord|ADO|ERR>  line %d\n", v34);
      }
    }
LABEL_87:
    CoTaskMemFree(pv);
    goto LABEL_88;
  }
  if ( (bidGblFlags & 2) != 0 )
  {
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
    {
      v15 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
      v16 = 601097;
      LODWORD(v42) = 587;
LABEL_10:
      bidTraceW(off_18012A1E8[0], v16, L"<CRecord::MoveRecord|ADO|ERR> %u#, line %d\n", v15, v42, v43, v44);
      goto LABEL_11;
    }
    v20 = 587;
    v21 = 601097;
    goto LABEL_17;
  }
LABEL_11:
  if ( v52 >= 0 && a8 )
  {
    if ( (bidGblFlags & 2) != 0 && off_18012A560[0] )
    {
      v17 = *a8;
      v18 = v52;
      v19 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
      LODWORD(v42) = v18;
      bidTraceW(off_18012A1E8[0], 690176, off_18012A560[0], v19, v42, v17);
    }
  }
  else if ( (bidGblFlags & 2) != 0 && off_18012A5C0[0] )
  {
    v38 = v52;
    v39 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
    LODWORD(v42) = v38;
    bidTraceW(off_18012A1E8[0], 694272, off_18012A5C0[0], v39, v42);
  }
  if ( (bidGblFlags & 4) != 0 && v46 != -1 && bidID != -1 )
    ((void (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *))off_180121248[0])(bidID, 0, 0, &v46);
  v40 = v52;
  CXLockContext::~CXLockContext((CXLockContext *)v51);
  return v40;
}

```

## disassembly

```asm
0x18008e250  mov     [rsp-8+arg_8], rbx
0x18008e255  mov     [rsp-8+pbstr], r8
0x18008e25a  push    rbp
0x18008e25b  push    rsi
0x18008e25c  push    rdi
0x18008e25d  push    r12
0x18008e25f  push    r13
0x18008e261  push    r14
0x18008e263  push    r15
0x18008e265  lea     rbp, [rsp-7]
0x18008e26a  sub     rsp, 0C0h
0x18008e271  mov     r8, [rcx+90h]
0x18008e278  lea     r10, [rcx+20h]
0x18008e27c  mov     rax, rcx
0x18008e27f  mov     rdi, rdx
0x18008e282  add     r8, 8; struct CCriticalSection **
0x18008e286  mov     rsi, rcx
0x18008e289  neg     rax
0x18008e28c  lea     rcx, [rbp+37h+var_70]; this
0x18008e290  mov     r13, r9
0x18008e293  sbb     rdx, rdx
0x18008e296  and     rdx, r10; struct CStdComObjectRoot *
0x18008e299  call    ??0CXLockContext@@QEAA@PEAVCStdComObjectRoot@@PEAPEAVCCriticalSection@@PEBD@Z; CXLockContext::CXLockContext(CStdComObjectRoot *,CCriticalSection * *,char const *)
0x18008e29e  movsx   r12d, [rbp+37h+arg_30]
0x18008e2a3  lea     rax, WindowName
0x18008e2aa  mov     r14d, [rbp+37h+arg_28]
0x18008e2ae  xor     ebx, ebx
0x18008e2b0  test    byte ptr cs:_bidGblFlags, 4
0x18008e2b7  mov     [rbp+37h+var_88], rax
0x18008e2bb  mov     [rbp+37h+arg_0], ebx
0x18008e2be  mov     [rbp+37h+psz], rbx
0x18008e2c2  mov     [rbp+37h+pv], rbx
0x18008e2c6  mov     [rbp+37h+var_80], rbx
0x18008e2ca  mov     [rbp+37h+var_98], 0FFFFFFFFFFFFFFFFh
0x18008e2d2  jz      short loc_18008E317
0x18008e2d4  mov     rax, cs:off_18012AB00; "<CRecord::MoveRecord|API|ADO> %u#, Sour"...
0x18008e2db  test    rax, rax
0x18008e2de  jz      short loc_18008E317
0x18008e2e0  mov     rbx, [rbp+37h+pbstr]
0x18008e2e4  lea     rcx, [rsi+98h]; this
0x18008e2eb  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18008e2f0  mov     rdx, cs:off_18012AB00; "<CRecord::MoveRecord|API|ADO> %u#, Sour"...
0x18008e2f7  lea     rcx, [rbp+37h+var_98]
0x18008e2fb  mov     dword ptr [rsp+0F0h+var_C0], r12d
0x18008e300  mov     r9, rdi
0x18008e303  mov     dword ptr [rsp+0F0h+var_C8], r14d
0x18008e308  mov     r8d, eax
0x18008e30b  mov     [rsp+0F0h+var_D0], rbx
0x18008e310  call    _bidScopeEnterW
0x18008e315  xor     ebx, ebx
0x18008e317  mov     rcx, [rbp+37h+pbstr]; pbstr
0x18008e31b  test    rcx, rcx
0x18008e31e  jz      short loc_18008E334
0x18008e320  call    cs:__imp_SysStringLen
0x18008e327  nop     dword ptr [rax+rax+00h]
0x18008e32c  test    eax, eax
0x18008e32e  jnz     loc_18008E431
0x18008e334  lea     rdx, [rbp+37h+var_A0]; int *
0x18008e338  mov     [rbp+37h+var_A0], 800A0BB9h
0x18008e33f  lea     rcx, [rbp+37h+var_70]; this
0x18008e343  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x18008e348  test    eax, eax
0x18008e34a  jz      loc_18008E431
0x18008e350  mov     bl, 2
0x18008e352  test    byte ptr cs:_bidGblFlags, bl
0x18008e358  jz      short loc_18008E39D
0x18008e35a  lea     rdi, [rsi+98h]
0x18008e361  mov     rcx, rdi; this
0x18008e364  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18008e369  cmp     eax, 0FFFFFFFFh
0x18008e36c  jz      loc_18008E40E
0x18008e372  mov     rcx, rdi; this
0x18008e375  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18008e37a  mov     edx, 92C09h
0x18008e37f  mov     dword ptr [rsp+0F0h+var_D0], 24Bh
0x18008e387  mov     rcx, cs:off_18012A1E8; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18008e38e  lea     r8, aCrecordMoverec; "<CRecord::MoveRecord|ADO|ERR> %u#, line"...
0x18008e395  mov     r9d, eax
0x18008e398  call    _bidTraceW
0x18008e39d  xor     r12d, r12d
0x18008e3a0  cmp     [rbp+37h+var_48], r12d
0x18008e3a4  jl      loc_18008E99C
0x18008e3aa  mov     rcx, [rbp+37h+arg_38]
0x18008e3ae  test    rcx, rcx
0x18008e3b1  jz      loc_18008E99C
0x18008e3b7  test    byte ptr cs:_bidGblFlags, bl
0x18008e3bd  jz      loc_18008E9DE
0x18008e3c3  mov     rax, cs:off_18012A560; "<CRecord::MoveRecord|API|ADO|RET> %u#, "...
0x18008e3ca  test    rax, rax
0x18008e3cd  jz      loc_18008E9DE
0x18008e3d3  mov     rbx, [rcx]
0x18008e3d6  lea     rcx, [rsi+98h]; this
0x18008e3dd  mov     edi, [rbp+37h+var_48]
0x18008e3e0  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18008e3e5  mov     r8, cs:off_18012A560; "<CRecord::MoveRecord|API|ADO|RET> %u#, "...
0x18008e3ec  mov     r9d, eax
0x18008e3ef  mov     rcx, cs:off_18012A1E8; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18008e3f6  mov     edx, 0A8800h
0x18008e3fb  mov     [rsp+0F0h+var_C8], rbx
0x18008e400  mov     dword ptr [rsp+0F0h+var_D0], edi
0x18008e404  call    _bidTraceW
0x18008e409  jmp     loc_18008E9DE
0x18008e40e  mov     r9d, 24Bh
0x18008e414  mov     edx, 92C09h
0x18008e419  mov     rcx, cs:off_18012A1E8; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18008e420  lea     r8, aCrecordMoverec_2; "<CRecord::MoveRecord|ADO|ERR>  line %d"...
0x18008e427  call    _bidTraceW
0x18008e42c  jmp     loc_18008E39D
0x18008e431  test    rdi, rdi
0x18008e434  jz      short loc_18008E43A
0x18008e436  mov     [rbp+37h+var_88], rdi
0x18008e43a  cmp     [rsi+110h], rbx
0x18008e441  jnz     short loc_18008E4A7
0x18008e443  lea     rdx, [rbp+37h+var_A0]; int *
0x18008e447  mov     [rbp+37h+var_A0], 800A0E78h
0x18008e44e  lea     rcx, [rbp+37h+var_70]; this
0x18008e452  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x18008e457  test    eax, eax
0x18008e459  jz      short loc_18008E4A7
0x18008e45b  mov     bl, 2
0x18008e45d  test    byte ptr cs:_bidGblFlags, bl
0x18008e463  jz      loc_18008E39D
0x18008e469  lea     rdi, [rsi+98h]
0x18008e470  mov     rcx, rdi; this
0x18008e473  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18008e478  cmp     eax, 0FFFFFFFFh
0x18008e47b  jz      short loc_18008E497
0x18008e47d  mov     rcx, rdi; this
0x18008e480  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18008e485  mov     edx, 95009h
0x18008e48a  mov     dword ptr [rsp+0F0h+var_D0], 254h
0x18008e492  jmp     loc_18008E387
0x18008e497  mov     r9d, 254h
0x18008e49d  mov     edx, 95009h
0x18008e4a2  jmp     loc_18008E419
0x18008e4a7  lea     r15, [rsi+128h]
0x18008e4ae  cmp     [r15], rbx
0x18008e4b1  jnz     loc_18008E541
0x18008e4b7  mov     rcx, [rsi+110h]
0x18008e4be  lea     rdx, IID_IScopedOperations
0x18008e4c5  mov     r8, r15
0x18008e4c8  mov     rax, [rcx]
0x18008e4cb  mov     rax, [rax]
0x18008e4ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e4d3  sar     eax, 1Fh
0x18008e4d6  lea     rdx, [rbp+37h+var_A0]; int *
0x18008e4da  and     eax, 800A0CB3h
0x18008e4df  lea     rcx, [rbp+37h+var_70]; this
0x18008e4e3  mov     r8d, 2729h; unsigned int
0x18008e4e9  mov     [rbp+37h+var_A0], eax
0x18008e4ec  call    ?FailedDescription@CContext@@QEAAHAEBJK@Z; CContext::FailedDescription(long const &,ulong)
0x18008e4f1  test    eax, eax
0x18008e4f3  jz      short loc_18008E541
0x18008e4f5  mov     bl, 2
0x18008e4f7  test    byte ptr cs:_bidGblFlags, bl
0x18008e4fd  jz      loc_18008E39D
0x18008e503  lea     rdi, [rsi+98h]
0x18008e50a  mov     rcx, rdi; this
0x18008e50d  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18008e512  cmp     eax, 0FFFFFFFFh
0x18008e515  jz      short loc_18008E531
0x18008e517  mov     rcx, rdi; this
0x18008e51a  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18008e51f  mov     edx, 96809h
0x18008e524  mov     dword ptr [rsp+0F0h+var_D0], 25Ah
0x18008e52c  jmp     loc_18008E387
0x18008e531  mov     r9d, 25Ah
0x18008e537  mov     edx, 96809h
0x18008e53c  jmp     loc_18008E419
0x18008e541  mov     edx, ebx
0x18008e543  mov     bl, 2
0x18008e545  cmp     r14d, 0FFFFFFFFh
0x18008e549  jz      short loc_18008E567
0x18008e54b  mov     ecx, r14d
0x18008e54e  and     ecx, 1
0x18008e551  mov     edx, ecx
0x18008e553  bts     edx, 9
0x18008e557  test    bl, r14b
0x18008e55a  cmovz   edx, ecx
0x18008e55d  test    r14b, 4
0x18008e561  jz      short loc_18008E567
0x18008e563  bts     edx, 0Ah
0x18008e567  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x18008e56e  mov     r14d, edx
0x18008e571  bts     r14d, 8
0x18008e576  mov     r8d, 20h ; ' '
0x18008e57c  test    r12w, r12w
0x18008e580  cmovz   r14d, edx
0x18008e584  mov     edx, 0A00000h
0x18008e589  call    cs:__imp_MpHeapAlloc
0x18008e590  nop     dword ptr [rax+rax+00h]
0x18008e595  xor     r12d, r12d
0x18008e598  test    rax, rax
0x18008e59b  jz      loc_18008E628
0x18008e5a1  mov     rcx, rax; this
0x18008e5a4  call    ??0CAuthenticateInfo@@QEAA@XZ; CAuthenticateInfo::CAuthenticateInfo(void)
0x18008e5a9  mov     rdi, rax
0x18008e5ac  test    rax, rax
0x18008e5af  jz      short loc_18008E62B
0x18008e5b1  mov     rdx, r13; unsigned __int16 *
0x18008e5b4  mov     rcx, rdi; this
0x18008e5b7  call    ?PutUserID@CAuthenticateInfo@@UEAAJPEAG@Z; CAuthenticateInfo::PutUserID(ushort *)
0x18008e5bc  lea     rdx, [rbp+37h+var_A0]; int *
0x18008e5c0  mov     [rbp+37h+var_A0], eax
0x18008e5c3  lea     rcx, [rbp+37h+var_70]; this
0x18008e5c7  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x18008e5cc  test    eax, eax
0x18008e5ce  jz      loc_18008E6DD
0x18008e5d4  test    byte ptr cs:_bidGblFlags, bl
0x18008e5da  jz      loc_18008E986
0x18008e5e0  lea     r14, [rsi+98h]
0x18008e5e7  mov     rcx, r14; this
0x18008e5ea  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18008e5ef  cmp     eax, 0FFFFFFFFh
0x18008e5f2  jz      loc_18008E6BA
0x18008e5f8  mov     rcx, r14; this
0x18008e5fb  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18008e600  mov     edx, 9D809h
0x18008e605  mov     dword ptr [rsp+0F0h+var_D0], 276h
0x18008e60d  mov     rcx, cs:off_18012A1E8; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18008e614  lea     r8, aCrecordMoverec; "<CRecord::MoveRecord|ADO|ERR> %u#, line"...
0x18008e61b  mov     r9d, eax
0x18008e61e  call    _bidTraceW
0x18008e623  jmp     loc_18008E986
0x18008e628  mov     rdi, r12
0x18008e62b  lea     rdx, [rbp+37h+var_A0]; int *
0x18008e62f  mov     [rbp+37h+var_A0], 8007000Eh
0x18008e636  lea     rcx, [rbp+37h+var_70]; this
0x18008e63a  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x18008e63f  test    eax, eax
0x18008e641  jz      loc_18008E5B1
0x18008e647  test    byte ptr cs:_bidGblFlags, bl
0x18008e64d  jz      loc_18008E3A0
0x18008e653  lea     rdi, [rsi+98h]
0x18008e65a  mov     rcx, rdi; this
0x18008e65d  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18008e662  cmp     eax, 0FFFFFFFFh
0x18008e665  jz      short loc_18008E697
0x18008e667  mov     rcx, rdi; this
0x18008e66a  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18008e66f  mov     rcx, cs:off_18012A1E8; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18008e676  lea     r8, aCrecordMoverec; "<CRecord::MoveRecord|ADO|ERR> %u#, line"...
0x18008e67d  mov     r9d, eax
0x18008e680  mov     dword ptr [rsp+0F0h+var_D0], 274h
0x18008e688  mov     edx, 9D009h
0x18008e68d  call    _bidTraceW
0x18008e692  jmp     loc_18008E3A0
0x18008e697  mov     rcx, cs:off_18012A1E8; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18008e69e  lea     r8, aCrecordMoverec_2; "<CRecord::MoveRecord|ADO|ERR>  line %d"...
0x18008e6a5  mov     r9d, 274h
0x18008e6ab  mov     edx, 9D009h
0x18008e6b0  call    _bidTraceW
0x18008e6b5  jmp     loc_18008E3A0
0x18008e6ba  mov     r9d, 276h
0x18008e6c0  mov     edx, 9D809h
0x18008e6c5  mov     rcx, cs:off_18012A1E8; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18008e6cc  lea     r8, aCrecordMoverec_2; "<CRecord::MoveRecord|ADO|ERR>  line %d"...
0x18008e6d3  call    _bidTraceW
0x18008e6d8  jmp     loc_18008E986
0x18008e6dd  mov     rdx, [rbp+37h+arg_20]; unsigned __int16 *
0x18008e6e1  mov     rcx, rdi; this
0x18008e6e4  call    ?PutPassword@CAuthenticateInfo@@UEAAJPEAG@Z; CAuthenticateInfo::PutPassword(ushort *)
0x18008e6e9  lea     rdx, [rbp+37h+var_A0]; int *
0x18008e6ed  mov     [rbp+37h+var_A0], eax
0x18008e6f0  lea     rcx, [rbp+37h+var_70]; this
0x18008e6f4  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x18008e6f9  test    eax, eax
0x18008e6fb  jz      short loc_18008E744
0x18008e6fd  test    byte ptr cs:_bidGblFlags, bl
0x18008e703  jz      loc_18008E986
0x18008e709  lea     r14, [rsi+98h]
0x18008e710  mov     rcx, r14; this
0x18008e713  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18008e718  cmp     eax, 0FFFFFFFFh
0x18008e71b  jz      short loc_18008E737
0x18008e71d  mov     rcx, r14; this
0x18008e720  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18008e725  mov     edx, 9DC09h
0x18008e72a  mov     dword ptr [rsp+0F0h+var_D0], 277h
0x18008e732  jmp     loc_18008E60D
0x18008e737  mov     r9d, 277h
0x18008e73d  mov     edx, 9DC09h
0x18008e742  jmp     short loc_18008E6C5
0x18008e744  mov     rcx, [r15]
0x18008e747  lea     r8, [rbp+37h+pv]
0x18008e74b  mov     [rsp+0F0h+var_B0], r8
0x18008e750  lea     r9, [rbp+37h+pbstr]
0x18008e754  lea     r8, [rbp+37h+psz]
0x18008e758  mov     edx, 1
0x18008e75d  mov     [rsp+0F0h+var_B8], r8
0x18008e762  lea     r8, [rbp+37h+arg_0]
0x18008e766  mov     rax, [rcx]
0x18008e769  mov     [rsp+0F0h+var_C0], r8
0x18008e76e  lea     r8, [rbp+37h+var_88]
0x18008e772  mov     [rsp+0F0h+var_C8], rdi
0x18008e777  mov     dword ptr [rsp+0F0h+var_D0], r14d
0x18008e77c  mov     rax, [rax+28h]
0x18008e780  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e785  mov     [rbp+37h+var_A0], eax
0x18008e788  cmp     eax, 80040E21h
  ... truncated ...
```
