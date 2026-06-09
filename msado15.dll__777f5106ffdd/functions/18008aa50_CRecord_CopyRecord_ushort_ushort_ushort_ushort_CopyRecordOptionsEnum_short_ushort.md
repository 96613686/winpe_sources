# CRecord::CopyRecord(ushort *,ushort *,ushort *,ushort *,CopyRecordOptionsEnum,short,ushort * *)

- ea: `0x18008aa50`
- end: `0x18008b1ee`
- name: `?CopyRecord@CRecord@@UEAAJPEAG000W4CopyRecordOptionsEnum@@FPEAPEAG@Z`
- size: `1950`
- prototype: `int(CRecord *__hidden this, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, enum CopyRecordOptionsEnum, __int16, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x18008b200`

## callees

- `0x180020e20`
- `0x180031760`
- `0x180032710`
- `0x18004f2b0`
- `0x18006a22c`
- `0x18008aa50`
- `0x1800c8ebc`
- `0x1800c8f34`
- `0x1800ca7f4`
- `0x1800cd638`
- `0x1800cd800`
- `0x1800cd890`
- `0x1800cd920`
- `0x1800d0010`

## import_xrefs

- `MSDART!MpHeapAlloc` at `0x18008ad70`
- `MSDART!MpHeapAlloc` at `0x18008ad70`
- `ole32!CoTaskMemFree` at `0x18008b125`
- `ole32!CoTaskMemFree` at `0x18008b125`
- `OLEAUT32!__imp_SysAllocString` at `0x18008b09b`
- `OLEAUT32!__imp_SysAllocString` at `0x18008b09b`
- `OLEAUT32!__imp_SysStringLen` at `0x18008ab1c`
- `OLEAUT32!__imp_SysStringLen` at `0x18008ab1c`

## string_xrefs

- `0x18008ab8a`: `<CRecord::CopyRecord|ADO|ERR> %u#, line %d\n`
- `0x18008adfb`: `<CRecord::CopyRecord|ADO|ERR> %u#, line %d\n`
- `0x18008ae5d`: `<CRecord::CopyRecord|ADO|ERR> %u#, line %d\n`
- `0x18008b066`: `<CRecord::CopyRecord|ADO|ERR> %u#, line %d\n`
- `0x18008ac07`: `<CRecord::CopyRecord|ADO|ERR>  line %d\n`
- `0x18008ae85`: `<CRecord::CopyRecord|ADO|ERR>  line %d\n`
- `0x18008aeb3`: `<CRecord::CopyRecord|ADO|ERR>  line %d\n`
- `0x18008b115`: `<CRecord::CopyRecord|ADO|ERR>  line %d\n`

## pseudocode

```c
__int64 __fastcall CRecord::CopyRecord(
        CRecord *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        char *a4,
        unsigned __int16 *a5,
        enum CopyRecordOptionsEnum a6,
        __int16 a7,
        unsigned __int16 **a8)
{
  int v11; // r12d
  enum CopyRecordOptionsEnum v12; // r14d
  int v13; // ebx
  unsigned int BidObjectID; // eax
  unsigned int v15; // eax
  __int64 v16; // rdx
  int v17; // ebx
  unsigned int v18; // eax
  __int64 v19; // r9
  __int64 v20; // rdx
  int v21; // edx
  int v22; // r14d
  CAuthenticateInfo *v23; // rax
  CAuthenticateInfo *v24; // rsi
  unsigned int v25; // eax
  __int64 v26; // rdx
  unsigned int v27; // eax
  __int64 v28; // r9
  __int64 v29; // rdx
  int v30; // eax
  unsigned int v31; // eax
  __int64 v32; // rdx
  __int64 v33; // r9
  __int64 v34; // rdx
  unsigned __int16 **v35; // r14
  BSTR v36; // rax
  int v37; // ebx
  unsigned int v38; // eax
  unsigned int v39; // ebx
  __int64 v41; // [rsp+20h] [rbp-89h]
  __int64 v42; // [rsp+28h] [rbp-81h]
  __int64 v43; // [rsp+30h] [rbp-79h]
  int v44; // [rsp+50h] [rbp-59h] BYREF
  __int64 v45; // [rsp+58h] [rbp-51h] BYREF
  OLECHAR *psz; // [rsp+60h] [rbp-49h] BYREF
  const OLECHAR *v47; // [rsp+68h] [rbp-41h] BYREF
  LPVOID pv; // [rsp+70h] [rbp-39h] BYREF
  _BYTE v49[40]; // [rsp+78h] [rbp-31h] BYREF
  int v50; // [rsp+A0h] [rbp-9h]
  unsigned int v51; // [rsp+F0h] [rbp+47h] BYREF
  BSTR pbstr; // [rsp+100h] [rbp+57h] BYREF

  pbstr = a3;
  CXLockContext::CXLockContext(
    (CXLockContext *)v49,
    (struct CStdComObjectRoot *)(((unsigned __int64)this + 32)
                               & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64)),
    (struct CCriticalSection **)(*((_QWORD *)this + 18) + 8LL),
    a4);
  v11 = a7;
  v12 = a6;
  v47 = &WindowName;
  v51 = 0;
  psz = 0;
  pv = 0;
  v45 = -1;
  if ( (bidGblFlags & 4) != 0 && off_18012AB38[0] )
  {
    v13 = (int)pbstr;
    BidObjectID = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
    LODWORD(v43) = v11;
    LODWORD(v42) = v12;
    bidScopeEnterW(&v45, off_18012AB38[0], BidObjectID, a2, v13);
  }
  if ( !pbstr || !SysStringLen(pbstr) )
  {
    v44 = -2146825287;
    if ( (unsigned int)CContext::Failed((CContext *)v49, &v44) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_11;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
      {
        v15 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
        v16 = 731145;
        LODWORD(v41) = 714;
LABEL_10:
        bidTraceW(off_18012A1E8[0], v16, L"<CRecord::CopyRecord|ADO|ERR> %u#, line %d\n", v15, v41, v42, v43);
        goto LABEL_11;
      }
      v19 = 714;
      v20 = 731145;
      goto LABEL_16;
    }
  }
  if ( a2 )
    v47 = a2;
  if ( !*((_QWORD *)this + 34) )
  {
    v44 = -2146824584;
    if ( (unsigned int)CContext::Failed((CContext *)v49, &v44) )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
        {
          v15 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
          v16 = 740361;
          LODWORD(v41) = 723;
          goto LABEL_10;
        }
        v19 = 723;
        v20 = 740361;
        goto LABEL_16;
      }
      goto LABEL_11;
    }
  }
  if ( *((_QWORD *)this + 37)
    || (v44 = ((***((int (__fastcall ****)(_QWORD, GUID *, char *))this + 34))(
                 *((_QWORD *)this + 34),
                 &IID_IScopedOperations,
                 (char *)this + 296) >> 31)
            & 0x800A0CB3,
        !(unsigned int)CContext::FailedDescription((CContext *)v49, &v44, 0x2729u)) )
  {
    v21 = 0;
    if ( v12 != adCopyUnspecified )
    {
      v21 = ((v12 & 1) << 9) | 0x400;
      if ( (v12 & 4) == 0 )
        v21 = (v12 & 1) << 9;
      if ( (v12 & 2) != 0 )
        v21 |= 0x800u;
    }
    v22 = v21 | 0x100;
    if ( !(_WORD)v11 )
      v22 = v21;
    v23 = (CAuthenticateInfo *)MpHeapAlloc(g_hHeapHandle, 10485760, 32);
    if ( v23 )
    {
      v24 = CAuthenticateInfo::CAuthenticateInfo(v23);
      if ( v24 )
        goto LABEL_40;
    }
    else
    {
      v24 = 0;
    }
    v44 = -2147024882;
    if ( (unsigned int)CContext::Failed((CContext *)v49, &v44) )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) == -1 )
        {
          bidTraceW(off_18012A1E8[0], 772105, L"<CRecord::CopyRecord|ADO|ERR>  line %d\n", 754);
        }
        else
        {
          v27 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
          LODWORD(v41) = 754;
          bidTraceW(off_18012A1E8[0], 772105, L"<CRecord::CopyRecord|ADO|ERR> %u#, line %d\n", v27, v41);
        }
      }
      goto LABEL_11;
    }
LABEL_40:
    v44 = CAuthenticateInfo::PutUserID(v24, (unsigned __int16 *)a4);
    if ( (unsigned int)CContext::Failed((CContext *)v49, &v44) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_84;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
      {
        v25 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
        v26 = 774153;
        LODWORD(v41) = 756;
LABEL_44:
        bidTraceW(off_18012A1E8[0], v26, L"<CRecord::CopyRecord|ADO|ERR> %u#, line %d\n", v25, v41, v42, v43);
        goto LABEL_84;
      }
      v28 = 756;
      v29 = 774153;
      goto LABEL_52;
    }
    v44 = CAuthenticateInfo::PutPassword(v24, a5);
    if ( (unsigned int)CContext::Failed((CContext *)v49, &v44) )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
        {
          v25 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
          v26 = 775177;
          LODWORD(v41) = 757;
          goto LABEL_44;
        }
        v28 = 757;
        v29 = 775177;
        goto LABEL_52;
      }
      goto LABEL_84;
    }
    v44 = (*(__int64 (__fastcall **)(_QWORD, __int64, const OLECHAR **, BSTR *, int, CAuthenticateInfo *, unsigned int *, OLECHAR **, LPVOID *))(**((_QWORD **)this + 37) + 32LL))(
            *((_QWORD *)this + 37),
            1,
            &v47,
            &pbstr,
            v22,
            v24,
            &v51,
            &psz,
            &pv);
    if ( v44 == -2147217887 )
      v44 = MapOLEDBStatusToADOError(v51, (const struct OLEDBStatusMap *)&g_CopyRowStatusMap);
    if ( (unsigned int)CContext::Failed((CContext *)v49, &v44) )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
        {
          v25 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
          v26 = 785417;
          LODWORD(v41) = 767;
          goto LABEL_44;
        }
        v28 = 767;
        v29 = 785417;
LABEL_52:
        bidTraceW(off_18012A1E8[0], v29, L"<CRecord::CopyRecord|ADO|ERR>  line %d\n", v28);
      }
LABEL_84:
      if ( v24 )
        CAuthenticateInfo::Release(v24);
      goto LABEL_11;
    }
    if ( v50 == 265946
      && v51 <= 0x19
      && (v30 = 41878016, _bittest(&v30, v51))
      && (v44 = MapOLEDBStatusToADOError(v51, (const struct OLEDBStatusMap *)&g_CopyRowStatusMap),
          (unsigned int)CContext::Failed((CContext *)v49, &v44)) )
    {
      if ( (bidGblFlags & 2) == 0 )
      {
LABEL_83:
        CoTaskMemFree(pv);
        goto LABEL_84;
      }
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
      {
        v31 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
        v32 = 789513;
        LODWORD(v41) = 771;
LABEL_72:
        bidTraceW(off_18012A1E8[0], v32, L"<CRecord::CopyRecord|ADO|ERR> %u#, line %d\n", v31, v41);
        goto LABEL_83;
      }
      v33 = 771;
      v34 = 789513;
    }
    else
    {
      v35 = a8;
      if ( !a8 )
        goto LABEL_83;
      v36 = SysAllocString(psz);
      *v35 = v36;
      if ( v36 )
        goto LABEL_83;
      if ( !psz )
        goto LABEL_83;
      v44 = -2147024882;
      if ( !(unsigned int)CContext::Failed((CContext *)v49, &v44) || (bidGblFlags & 2) == 0 )
        goto LABEL_83;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
      {
        v31 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
        v32 = 796681;
        LODWORD(v41) = 778;
        goto LABEL_72;
      }
      v33 = 778;
      v34 = 796681;
    }
    bidTraceW(off_18012A1E8[0], v34, L"<CRecord::CopyRecord|ADO|ERR>  line %d\n", v33);
    goto LABEL_83;
  }
  if ( (bidGblFlags & 2) != 0 )
  {
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
    {
      v15 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
      v16 = 746505;
      LODWORD(v41) = 729;
      goto LABEL_10;
    }
    v19 = 729;
    v20 = 746505;
LABEL_16:
    bidTraceW(off_18012A1E8[0], v20, L"<CRecord::CopyRecord|ADO|ERR>  line %d\n", v19);
  }
LABEL_11:
  if ( v50 >= 0 )
  {
    if ( (bidGblFlags & 2) != 0 && off_18012A5C8[0] )
    {
      v37 = v50;
      v38 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
      LODWORD(v41) = v37;
      bidTraceW(off_18012A1E8[0], 816128, off_18012A5C8[0], v38, v41, a8);
    }
  }
  else if ( (bidGblFlags & 2) != 0 && off_18012A598[0] )
  {
    v17 = v50;
    v18 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
    LODWORD(v41) = v17;
    bidTraceW(off_18012A1E8[0], 808960, off_18012A598[0], v18, v41);
  }
  if ( (bidGblFlags & 4) != 0 && v45 != -1 && bidID != -1 )
    ((void (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *))off_180121248[0])(bidID, 0, 0, &v45);
  v39 = v50;
  CXLockContext::~CXLockContext((CXLockContext *)v49);
  return v39;
}

```

## disassembly

```asm
0x18008aa50  mov     [rsp-8+arg_8], rbx
0x18008aa55  mov     [rsp-8+pbstr], r8
0x18008aa5a  push    rbp
0x18008aa5b  push    rsi
0x18008aa5c  push    rdi
0x18008aa5d  push    r12
0x18008aa5f  push    r13
0x18008aa61  push    r14
0x18008aa63  push    r15
0x18008aa65  lea     rbp, [rsp-7]
0x18008aa6a  sub     rsp, 0B0h
0x18008aa71  mov     r8, [rcx+90h]
0x18008aa78  lea     r10, [rcx+20h]
0x18008aa7c  mov     rax, rcx
0x18008aa7f  mov     rsi, rdx
0x18008aa82  add     r8, 8; struct CCriticalSection **
0x18008aa86  mov     rdi, rcx
0x18008aa89  neg     rax
0x18008aa8c  lea     rcx, [rbp+37h+var_68]; this
0x18008aa90  mov     r13, r9
0x18008aa93  sbb     rdx, rdx
0x18008aa96  and     rdx, r10; struct CStdComObjectRoot *
0x18008aa99  call    ??0CXLockContext@@QEAA@PEAVCStdComObjectRoot@@PEAPEAVCCriticalSection@@PEBD@Z; CXLockContext::CXLockContext(CStdComObjectRoot *,CCriticalSection * *,char const *)
0x18008aa9e  movsx   r12d, [rbp+37h+arg_30]
0x18008aaa3  lea     rax, WindowName
0x18008aaaa  mov     r14d, [rbp+37h+arg_28]
0x18008aaae  xor     ebx, ebx
0x18008aab0  test    byte ptr cs:_bidGblFlags, 4
0x18008aab7  mov     [rbp+37h+var_78], rax
0x18008aabb  mov     [rbp+37h+arg_0], ebx
0x18008aabe  mov     [rbp+37h+psz], rbx
0x18008aac2  mov     [rbp+37h+pv], rbx
0x18008aac6  mov     [rbp+37h+var_88], 0FFFFFFFFFFFFFFFFh
0x18008aace  jz      short loc_18008AB13
0x18008aad0  mov     rax, cs:off_18012AB38; "<CRecord::CopyRecord|API|ADO> %u#, Sour"...
0x18008aad7  test    rax, rax
0x18008aada  jz      short loc_18008AB13
0x18008aadc  mov     rbx, [rbp+37h+pbstr]
0x18008aae0  lea     rcx, [rdi+98h]; this
0x18008aae7  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18008aaec  mov     rdx, cs:off_18012AB38; "<CRecord::CopyRecord|API|ADO> %u#, Sour"...
0x18008aaf3  lea     rcx, [rbp+37h+var_88]
0x18008aaf7  mov     dword ptr [rsp+0E0h+var_B0], r12d
0x18008aafc  mov     r9, rsi
0x18008aaff  mov     dword ptr [rsp+0E0h+var_B8], r14d
0x18008ab04  mov     r8d, eax
0x18008ab07  mov     [rsp+0E0h+var_C0], rbx
0x18008ab0c  call    _bidScopeEnterW
0x18008ab11  xor     ebx, ebx
0x18008ab13  mov     rcx, [rbp+37h+pbstr]; pbstr
0x18008ab17  test    rcx, rcx
0x18008ab1a  jz      short loc_18008AB30
0x18008ab1c  call    cs:__imp_SysStringLen
0x18008ab23  nop     dword ptr [rax+rax+00h]
0x18008ab28  test    eax, eax
0x18008ab2a  jnz     loc_18008AC15
0x18008ab30  lea     rdx, [rbp+37h+var_90]; int *
0x18008ab34  mov     [rbp+37h+var_90], 800A0BB9h
0x18008ab3b  lea     rcx, [rbp+37h+var_68]; this
0x18008ab3f  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x18008ab44  test    eax, eax
0x18008ab46  jz      loc_18008AC15
0x18008ab4c  mov     bl, 2
0x18008ab4e  test    byte ptr cs:_bidGblFlags, bl
0x18008ab54  jz      short loc_18008AB99
0x18008ab56  lea     rsi, [rdi+98h]
0x18008ab5d  mov     rcx, rsi; this
0x18008ab60  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18008ab65  cmp     eax, 0FFFFFFFFh
0x18008ab68  jz      loc_18008ABF5
0x18008ab6e  mov     rcx, rsi; this
0x18008ab71  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18008ab76  mov     edx, 0B2809h
0x18008ab7b  mov     dword ptr [rsp+0E0h+var_C0], 2CAh
0x18008ab83  mov     rcx, cs:off_18012A1E8; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18008ab8a  lea     r8, aCrecordCopyrec_1; "<CRecord::CopyRecord|ADO|ERR> %u#, line"...
0x18008ab91  mov     r9d, eax
0x18008ab94  call    _bidTraceW
0x18008ab99  xor     r12d, r12d
0x18008ab9c  cmp     [rbp+37h+var_40], r12d
0x18008aba0  jge     loc_18008B147
0x18008aba6  test    byte ptr cs:_bidGblFlags, bl
0x18008abac  jz      loc_18008B192
0x18008abb2  mov     rax, cs:off_18012A598; "<CRecord::CopyRecord|API|ADO|RET> %u#, "...
0x18008abb9  test    rax, rax
0x18008abbc  jz      loc_18008B192
0x18008abc2  mov     ebx, [rbp+37h+var_40]
0x18008abc5  lea     rcx, [rdi+98h]; this
0x18008abcc  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18008abd1  mov     r8, cs:off_18012A598; "<CRecord::CopyRecord|API|ADO|RET> %u#, "...
0x18008abd8  mov     r9d, eax
0x18008abdb  mov     rcx, cs:off_18012A1E8; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18008abe2  mov     edx, 0C5800h
0x18008abe7  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x18008abeb  call    _bidTraceW
0x18008abf0  jmp     loc_18008B192
0x18008abf5  mov     r9d, 2CAh
0x18008abfb  mov     edx, 0B2809h
0x18008ac00  mov     rcx, cs:off_18012A1E8; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18008ac07  lea     r8, aCrecordCopyrec_2; "<CRecord::CopyRecord|ADO|ERR>  line %d"...
0x18008ac0e  call    _bidTraceW
0x18008ac13  jmp     short loc_18008AB99
0x18008ac15  test    rsi, rsi
0x18008ac18  jz      short loc_18008AC1E
0x18008ac1a  mov     [rbp+37h+var_78], rsi
0x18008ac1e  cmp     [rdi+110h], rbx
0x18008ac25  jnz     short loc_18008AC8B
0x18008ac27  lea     rdx, [rbp+37h+var_90]; int *
0x18008ac2b  mov     [rbp+37h+var_90], 800A0E78h
0x18008ac32  lea     rcx, [rbp+37h+var_68]; this
0x18008ac36  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x18008ac3b  test    eax, eax
0x18008ac3d  jz      short loc_18008AC8B
0x18008ac3f  mov     bl, 2
0x18008ac41  test    byte ptr cs:_bidGblFlags, bl
0x18008ac47  jz      loc_18008AB99
0x18008ac4d  lea     rsi, [rdi+98h]
0x18008ac54  mov     rcx, rsi; this
0x18008ac57  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18008ac5c  cmp     eax, 0FFFFFFFFh
0x18008ac5f  jz      short loc_18008AC7B
0x18008ac61  mov     rcx, rsi; this
0x18008ac64  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18008ac69  mov     edx, 0B4C09h
0x18008ac6e  mov     dword ptr [rsp+0E0h+var_C0], 2D3h
0x18008ac76  jmp     loc_18008AB83
0x18008ac7b  mov     r9d, 2D3h
0x18008ac81  mov     edx, 0B4C09h
0x18008ac86  jmp     loc_18008AC00
0x18008ac8b  lea     r15, [rdi+128h]
0x18008ac92  cmp     [r15], rbx
0x18008ac95  jnz     loc_18008AD25
0x18008ac9b  mov     rcx, [rdi+110h]
0x18008aca2  lea     rdx, IID_IScopedOperations
0x18008aca9  mov     r8, r15
0x18008acac  mov     rax, [rcx]
0x18008acaf  mov     rax, [rax]
0x18008acb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008acb7  sar     eax, 1Fh
0x18008acba  lea     rdx, [rbp+37h+var_90]; int *
0x18008acbe  and     eax, 800A0CB3h
0x18008acc3  lea     rcx, [rbp+37h+var_68]; this
0x18008acc7  mov     r8d, 2729h; unsigned int
0x18008accd  mov     [rbp+37h+var_90], eax
0x18008acd0  call    ?FailedDescription@CContext@@QEAAHAEBJK@Z; CContext::FailedDescription(long const &,ulong)
0x18008acd5  test    eax, eax
0x18008acd7  jz      short loc_18008AD25
0x18008acd9  mov     bl, 2
0x18008acdb  test    byte ptr cs:_bidGblFlags, bl
0x18008ace1  jz      loc_18008AB99
0x18008ace7  lea     rsi, [rdi+98h]
0x18008acee  mov     rcx, rsi; this
0x18008acf1  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18008acf6  cmp     eax, 0FFFFFFFFh
0x18008acf9  jz      short loc_18008AD15
0x18008acfb  mov     rcx, rsi; this
0x18008acfe  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18008ad03  mov     edx, 0B6409h
0x18008ad08  mov     dword ptr [rsp+0E0h+var_C0], 2D9h
0x18008ad10  jmp     loc_18008AB83
0x18008ad15  mov     r9d, 2D9h
0x18008ad1b  mov     edx, 0B6409h
0x18008ad20  jmp     loc_18008AC00
0x18008ad25  mov     edx, ebx
0x18008ad27  mov     bl, 2
0x18008ad29  cmp     r14d, 0FFFFFFFFh
0x18008ad2d  jz      short loc_18008AD4E
0x18008ad2f  mov     ecx, r14d
0x18008ad32  and     ecx, 1
0x18008ad35  shl     ecx, 9
0x18008ad38  mov     edx, ecx
0x18008ad3a  bts     edx, 0Ah
0x18008ad3e  test    r14b, 4
0x18008ad42  cmovz   edx, ecx
0x18008ad45  test    bl, r14b
0x18008ad48  jz      short loc_18008AD4E
0x18008ad4a  bts     edx, 0Bh
0x18008ad4e  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x18008ad55  mov     r14d, edx
0x18008ad58  bts     r14d, 8
0x18008ad5d  mov     r8d, 20h ; ' '
0x18008ad63  test    r12w, r12w
0x18008ad67  cmovz   r14d, edx
0x18008ad6b  mov     edx, 0A00000h
0x18008ad70  call    cs:__imp_MpHeapAlloc
0x18008ad77  nop     dword ptr [rax+rax+00h]
0x18008ad7c  xor     r12d, r12d
0x18008ad7f  test    rax, rax
0x18008ad82  jz      loc_18008AE0F
0x18008ad88  mov     rcx, rax; this
0x18008ad8b  call    ??0CAuthenticateInfo@@QEAA@XZ; CAuthenticateInfo::CAuthenticateInfo(void)
0x18008ad90  mov     rsi, rax
0x18008ad93  test    rax, rax
0x18008ad96  jz      short loc_18008AE12
0x18008ad98  mov     rdx, r13; unsigned __int16 *
0x18008ad9b  mov     rcx, rsi; this
0x18008ad9e  call    ?PutUserID@CAuthenticateInfo@@UEAAJPEAG@Z; CAuthenticateInfo::PutUserID(ushort *)
0x18008ada3  lea     rdx, [rbp+37h+var_90]; int *
0x18008ada7  mov     [rbp+37h+var_90], eax
0x18008adaa  lea     rcx, [rbp+37h+var_68]; this
0x18008adae  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x18008adb3  test    eax, eax
0x18008adb5  jz      loc_18008AEC4
0x18008adbb  test    byte ptr cs:_bidGblFlags, bl
0x18008adc1  jz      loc_18008B131
0x18008adc7  lea     r14, [rdi+98h]
0x18008adce  mov     rcx, r14; this
0x18008add1  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18008add6  cmp     eax, 0FFFFFFFFh
0x18008add9  jz      loc_18008AEA1
0x18008addf  mov     rcx, r14; this
0x18008ade2  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18008ade7  mov     edx, 0BD009h
0x18008adec  mov     dword ptr [rsp+0E0h+var_C0], 2F4h
0x18008adf4  mov     rcx, cs:off_18012A1E8; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18008adfb  lea     r8, aCrecordCopyrec_1; "<CRecord::CopyRecord|ADO|ERR> %u#, line"...
0x18008ae02  mov     r9d, eax
0x18008ae05  call    _bidTraceW
0x18008ae0a  jmp     loc_18008B131
0x18008ae0f  mov     rsi, r12
0x18008ae12  lea     rdx, [rbp+37h+var_90]; int *
0x18008ae16  mov     [rbp+37h+var_90], 8007000Eh
0x18008ae1d  lea     rcx, [rbp+37h+var_68]; this
0x18008ae21  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x18008ae26  test    eax, eax
0x18008ae28  jz      loc_18008AD98
0x18008ae2e  test    byte ptr cs:_bidGblFlags, bl
0x18008ae34  jz      loc_18008AB9C
0x18008ae3a  lea     rsi, [rdi+98h]
0x18008ae41  mov     rcx, rsi; this
0x18008ae44  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18008ae49  cmp     eax, 0FFFFFFFFh
0x18008ae4c  jz      short loc_18008AE7E
0x18008ae4e  mov     rcx, rsi; this
0x18008ae51  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18008ae56  mov     rcx, cs:off_18012A1E8; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18008ae5d  lea     r8, aCrecordCopyrec_1; "<CRecord::CopyRecord|ADO|ERR> %u#, line"...
0x18008ae64  mov     r9d, eax
0x18008ae67  mov     dword ptr [rsp+0E0h+var_C0], 2F2h
0x18008ae6f  mov     edx, 0BC809h
0x18008ae74  call    _bidTraceW
0x18008ae79  jmp     loc_18008AB9C
0x18008ae7e  mov     rcx, cs:off_18012A1E8; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18008ae85  lea     r8, aCrecordCopyrec_2; "<CRecord::CopyRecord|ADO|ERR>  line %d"...
0x18008ae8c  mov     r9d, 2F2h
0x18008ae92  mov     edx, 0BC809h
0x18008ae97  call    _bidTraceW
0x18008ae9c  jmp     loc_18008AB9C
0x18008aea1  mov     r9d, 2F4h
0x18008aea7  mov     edx, 0BD009h
0x18008aeac  mov     rcx, cs:off_18012A1E8; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18008aeb3  lea     r8, aCrecordCopyrec_2; "<CRecord::CopyRecord|ADO|ERR>  line %d"...
0x18008aeba  call    _bidTraceW
0x18008aebf  jmp     loc_18008B131
0x18008aec4  mov     rdx, [rbp+37h+arg_20]; unsigned __int16 *
0x18008aec8  mov     rcx, rsi; this
0x18008aecb  call    ?PutPassword@CAuthenticateInfo@@UEAAJPEAG@Z; CAuthenticateInfo::PutPassword(ushort *)
0x18008aed0  lea     rdx, [rbp+37h+var_90]; int *
0x18008aed4  mov     [rbp+37h+var_90], eax
0x18008aed7  lea     rcx, [rbp+37h+var_68]; this
0x18008aedb  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x18008aee0  test    eax, eax
0x18008aee2  jz      short loc_18008AF2B
0x18008aee4  test    byte ptr cs:_bidGblFlags, bl
0x18008aeea  jz      loc_18008B131
0x18008aef0  lea     r14, [rdi+98h]
0x18008aef7  mov     rcx, r14; this
0x18008aefa  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18008aeff  cmp     eax, 0FFFFFFFFh
0x18008af02  jz      short loc_18008AF1E
0x18008af04  mov     rcx, r14; this
0x18008af07  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18008af0c  mov     edx, 0BD409h
0x18008af11  mov     dword ptr [rsp+0E0h+var_C0], 2F5h
0x18008af19  jmp     loc_18008ADF4
0x18008af1e  mov     r9d, 2F5h
0x18008af24  mov     edx, 0BD409h
0x18008af29  jmp     short loc_18008AEAC
0x18008af2b  mov     rcx, [r15]
0x18008af2e  lea     r8, [rbp+37h+pv]
0x18008af32  mov     [rsp+0E0h+var_A0], r8
0x18008af37  lea     r9, [rbp+37h+pbstr]
0x18008af3b  lea     r8, [rbp+37h+psz]
0x18008af3f  mov     edx, 1
0x18008af44  mov     [rsp+0E0h+var_A8], r8
0x18008af49  lea     r8, [rbp+37h+arg_0]
0x18008af4d  mov     rax, [rcx]
0x18008af50  mov     [rsp+0E0h+var_B0], r8
0x18008af55  lea     r8, [rbp+37h+var_78]
0x18008af59  mov     [rsp+0E0h+var_B8], rsi
0x18008af5e  mov     dword ptr [rsp+0E0h+var_C0], r14d
0x18008af63  mov     rax, [rax+20h]
0x18008af67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008af6c  mov     [rbp+37h+var_90], eax
0x18008af6f  cmp     eax, 80040E21h
0x18008af74  jnz     short loc_18008AF88
0x18008af76  mov     ecx, [rbp+37h+arg_0]; unsigned int
0x18008af79  lea     rdx, ?g_CopyRowStatusMap@@3QBUOLEDBStatusMap@@B; struct OLEDBStatusMap *
0x18008af80  call    ?MapOLEDBStatusToADOError@@YAJKPEBUOLEDBStatusMap@@@Z; MapOLEDBStatusToADOError(ulong,OLEDBStatusMap const *)
0x18008af85  mov     [rbp+37h+var_90], eax
  ... truncated ...
```
