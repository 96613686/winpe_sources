# CRecord::GetChildren(_ADORecordset * *)

- ea: `0x18008bae0`
- end: `0x18008c60d`
- name: `?GetChildren@CRecord@@UEAAJPEAPEAU_ADORecordset@@@Z`
- size: `2861`
- prototype: `__int64 __fastcall(CRecord *__hidden this, struct _ADORecordset **)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180020e20`
- `0x180031760`
- `0x180032710`
- `0x18004f2b0`
- `0x180056ccc`
- `0x180059ccc`
- `0x18006a22c`
- `0x18008bae0`
- `0x18008c870`
- `0x1800c8ebc`
- `0x1800c8f34`
- `0x1800d0010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18008bf10`
- `ole32!CoCreateInstance` at `0x18008bf10`
- `OLEAUT32!__imp_SysFreeString` at `0x18008c4ee`
- `OLEAUT32!__imp_SysFreeString` at `0x18008c4ee`

## pseudocode

```c
__int64 __fastcall CRecord::GetChildren(CRecord *this, LPVOID *a2)
{
  unsigned int BidObjectID; // eax
  __int64 v5; // r9
  unsigned int v6; // eax
  __int64 v7; // rdx
  __int64 v8; // r9
  __int64 v9; // rdx
  __int64 v10; // r10
  int v11; // ecx
  __int64 v12; // r9
  int v13; // ecx
  int v14; // ecx
  __int64 v15; // r8
  __int64 v16; // r9
  char *v17; // rcx
  unsigned int (__fastcall ***v18)(_QWORD, GUID *, __int64 *); // rax
  unsigned int (__fastcall ***v19)(_QWORD, GUID *, __int64 *); // rax
  RecordTypeEnum v20; // ebx
  __int64 v21; // r9
  int v22; // r10d
  CBidGenericBase *v23; // rsi
  unsigned int v24; // eax
  LPVOID v25; // rcx
  unsigned int v26; // ebx
  unsigned int v27; // eax
  unsigned int v28; // ebx
  LPVOID *ppv; // [rsp+20h] [rbp-99h]
  __int64 v31; // [rsp+28h] [rbp-91h]
  __int64 v32; // [rsp+60h] [rbp-59h] BYREF
  __int64 v33; // [rsp+68h] [rbp-51h] BYREF
  __int64 v34; // [rsp+70h] [rbp-49h] BYREF
  __int64 v35; // [rsp+78h] [rbp-41h] BYREF
  BSTR bstrString; // [rsp+80h] [rbp-39h] BYREF
  __int64 v37; // [rsp+88h] [rbp-31h] BYREF
  _BYTE v38[40]; // [rsp+90h] [rbp-29h] BYREF
  unsigned int v39; // [rsp+B8h] [rbp-1h]
  __int128 v40; // [rsp+C8h] [rbp+Fh] BYREF
  __int64 v41; // [rsp+D8h] [rbp+1Fh]
  RecordTypeEnum v42; // [rsp+120h] [rbp+67h] BYREF
  int RecordType; // [rsp+128h] [rbp+6Fh] BYREF
  LPVOID v44; // [rsp+130h] [rbp+77h] BYREF
  __int64 v45; // [rsp+138h] [rbp+7Fh] BYREF

  CXLockContext::CXLockContext(
    (CXLockContext *)v38,
    (struct CStdComObjectRoot *)(((unsigned __int64)this + 32)
                               & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64)),
    (struct CCriticalSection **)(*((_QWORD *)this + 18) + 8LL),
    (const char *)this + 32);
  v37 = -1;
  v35 = 0;
  v44 = 0;
  v34 = 0;
  v33 = 0;
  v32 = 0;
  v45 = 0;
  v40 = 0;
  v41 = 0;
  bstrString = 0;
  v42 = adSimpleRecord;
  if ( (bidGblFlags & 4) != 0 && off_18012AB08[0] )
  {
    BidObjectID = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
    bidScopeEnterW(&v37, off_18012AB08[0], BidObjectID, v5, (_DWORD)ppv);
  }
  if ( !a2 )
  {
    RecordType = -2146825287;
    if ( (unsigned int)CContext::Failed((CContext *)v38, &RecordType) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_114;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
      {
        v6 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
        v7 = 1992713;
        LODWORD(ppv) = 1946;
LABEL_9:
        bidTraceW(off_18012A1E8[0], v7, L"<CRecord::GetChildren|ADO|ERR> %u#, line %d\n", v6, ppv);
        goto LABEL_114;
      }
      v8 = 1946;
      v9 = 1992713;
      goto LABEL_11;
    }
  }
  if ( *((_QWORD *)this + 34)
    || (RecordType = -2146824584, !(unsigned int)CContext::Failed((CContext *)v38, &RecordType)) )
  {
    RecordType = CRecord::GetRecordType(this, &v42);
    if ( (unsigned int)CContext::Failed((CContext *)v38, &RecordType) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_114;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
      {
        v6 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
        v7 = 1999881;
        LODWORD(ppv) = 1953;
        goto LABEL_9;
      }
      v8 = 1953;
      v9 = 1999881;
      goto LABEL_11;
    }
    if ( v42 != adCollectionRecord )
    {
      v42 = -2146825069;
      if ( (unsigned int)CContext::Failed((CContext *)v38, (const int *)&v42) )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_114;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
        {
          v6 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
          v7 = 2001929;
          LODWORD(ppv) = 1955;
          goto LABEL_9;
        }
        v8 = 1955;
        v9 = 2001929;
        goto LABEL_11;
      }
    }
    v10 = *((_QWORD *)this + 37);
    if ( !v10 )
    {
      v42 = ((***((int (__fastcall ****)(_QWORD, GUID *, char *))this + 34))(
               *((_QWORD *)this + 34),
               &IID_IScopedOperations,
               (char *)this + 296) >> 31)
          & 0x800A0CB3;
      if ( (unsigned int)CContext::FailedDescription((CContext *)v38, (const int *)&v42, 0x2729u) )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_114;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
        {
          v6 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
          v7 = 2007049;
          LODWORD(ppv) = 1960;
          goto LABEL_9;
        }
        v8 = 1960;
        v9 = 2007049;
        goto LABEL_11;
      }
      v10 = *((_QWORD *)this + 37);
    }
    v11 = *((_DWORD *)this + 142);
    if ( v11 == -1 )
    {
      v12 = *((unsigned int *)this + 76);
      if ( !(_DWORD)v12 )
        v12 = 1;
    }
    else
    {
      v13 = v11 - 1;
      if ( v13 )
      {
        v14 = v13 - 1;
        if ( !v14 )
        {
          v12 = 11;
          goto LABEL_46;
        }
        if ( (unsigned int)(v14 - 1) <= 1 )
        {
          v12 = 19;
          goto LABEL_46;
        }
      }
      v12 = 1;
    }
LABEL_46:
    v42 = (*(unsigned int (__fastcall **)(__int64, _QWORD, const OLECHAR *, __int64, const GUID *, GUID *, _QWORD, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v10 + 24LL))(
            v10,
            0,
            &WindowName,
            v12,
            &DBGUID_ROWSET,
            &IID_IUnknown,
            0,
            0,
            0,
            &v35);
    if ( (unsigned int)CContext::Failed((CContext *)v38, (const int *)&v42) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_114;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
      {
        v6 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
        v7 = 2027529;
        LODWORD(ppv) = 1980;
        goto LABEL_9;
      }
      v8 = 1980;
      v9 = 2027529;
      goto LABEL_11;
    }
    v42 = CoCreateInstance(&CLSID_CADORecordset, 0, 3u, &IID_IADORecordset, &v44);
    if ( (unsigned int)CContext::Failed((CContext *)v38, (const int *)&v42) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_114;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
      {
        v6 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
        v7 = 2032649;
        LODWORD(ppv) = 1985;
        goto LABEL_9;
      }
      v8 = 1985;
      v9 = 2032649;
      goto LABEL_11;
    }
    v42 = (**(unsigned int (__fastcall ***)(LPVOID, GUID *, __int64 *))v44)(v44, &IID_IADORecordsetConstruction, &v34);
    if ( (unsigned int)CContext::Failed((CContext *)v38, (const int *)&v42) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_114;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
      {
        v6 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
        v7 = 2034697;
        LODWORD(ppv) = 1987;
        goto LABEL_9;
      }
      v8 = 1987;
      v9 = 2034697;
      goto LABEL_11;
    }
    v42 = (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v34 + 64LL))(v34, v35);
    if ( (unsigned int)CContext::Failed((CContext *)v38, (const int *)&v42) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_114;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
      {
        v6 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
        v7 = 2035721;
        LODWORD(ppv) = 1988;
        goto LABEL_9;
      }
      v8 = 1988;
      v9 = 2035721;
      goto LABEL_11;
    }
    v17 = (char *)this + 168;
    if ( (*((_WORD *)this + 92) & 0xBFFF) == 0xD )
    {
      v18 = (unsigned int (__fastcall ***)(_QWORD, GUID *, __int64 *))CVar::operator IUnknown *(v17, 49151, v15, v16);
      v42 = (**v18)(v18, &IID_IADOConnection, &v45);
      if ( (unsigned int)CContext::Failed((CContext *)v38, (const int *)&v42) )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_114;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
        {
          v6 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
          v7 = 2040841;
          LODWORD(ppv) = 1993;
          goto LABEL_9;
        }
        v8 = 1993;
        v9 = 2040841;
        goto LABEL_11;
      }
    }
    else
    {
      v19 = (unsigned int (__fastcall ***)(_QWORD, GUID *, __int64 *))CVar::operator IUnknown *(v17, 49151, v15, v16);
      v42 = (**v19)(v19, &IID_IADOConnection, &v45);
      if ( (unsigned int)CContext::Failed((CContext *)v38, (const int *)&v42) )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_114;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
        {
          v6 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
          v7 = 2045961;
          LODWORD(ppv) = 1998;
          goto LABEL_9;
        }
        v8 = 1998;
        v9 = 2045961;
        goto LABEL_11;
      }
    }
    v42 = (**(unsigned int (__fastcall ***)(LPVOID, GUID *, __int64 *))v44)(v44, &IID_IADOClass, &v33);
    if ( (unsigned int)CContext::Failed((CContext *)v38, (const int *)&v42) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_114;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
      {
        v6 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
        v7 = 2048009;
        LODWORD(ppv) = 2000;
        goto LABEL_9;
      }
      v8 = 2000;
      v9 = 2048009;
    }
    else
    {
      v42 = (*(unsigned int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v33 + 24LL))(v33, &v32);
      if ( (unsigned int)CContext::Failed((CContext *)v38, (const int *)&v42) )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_114;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
        {
          v6 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
          v7 = 2050057;
          LODWORD(ppv) = 2002;
          goto LABEL_9;
        }
        v8 = 2002;
        v9 = 2050057;
      }
      else
      {
        v42 = (*(unsigned int (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v32 + 696LL))(v32, v45, 1);
        if ( (unsigned int)CContext::Failed((CContext *)v38, (const int *)&v42) )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_114;
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
          {
            v6 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
            v7 = 2051081;
            LODWORD(ppv) = 2003;
            goto LABEL_9;
          }
          v8 = 2003;
          v9 = 2051081;
        }
        else
        {
          v42 = (*(unsigned int (__fastcall **)(CRecord *, BSTR *))(*(_QWORD *)this + 232LL))(this, &bstrString);
          if ( (unsigned int)CContext::Failed((CContext *)v38, (const int *)&v42) )
          {
            if ( (bidGblFlags & 2) == 0 )
              goto LABEL_114;
            if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
            {
              v6 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
              v7 = 2054153;
              LODWORD(ppv) = 2006;
              goto LABEL_9;
            }
            v8 = 2006;
            v9 = 2054153;
          }
          else
          {
            *((_QWORD *)&v40 + 1) = bstrString;
            LOWORD(v40) = 8;
            v42 = (*(unsigned int (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v32 + 712LL))(v32, &v40);
            if ( (unsigned int)CContext::Failed((CContext *)v38, (const int *)&v42) )
            {
              if ( (bidGblFlags & 2) == 0 )
                goto LABEL_114;
              if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
              {
                v6 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
                v7 = 2058249;
                LODWORD(ppv) = 2010;
                goto LABEL_9;
              }
              v8 = 2010;
              v9 = 2058249;
            }
            else
            {
              v20 = (unsigned int)ValidateCmdType(512, 3);
              if ( v20 >= adSimpleRecord )
              {
                *(_DWORD *)(v21 + 1452) = v22;
              }
              else if ( (bidGblFlags & 2) != 0 )
              {
                v23 = (CBidGenericBase *)(v21 + 1560);
                if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)(v21 + 1560)) == -1 )
                {
                  LODWORD(ppv) = 8431;
                  bidTraceW(
                    off_18012A208[0],
                    8633353,
                    L"<CRecordset::SetCmdType|ADO|ERR> 0x%08x{HRESULT} line %d\n",
                    (unsigned int)v20,
                    ppv);
                }
                else
                {
                  v24 = CBidGenericBase::GetBidObjectID(v23);
                  LODWORD(v31) = 8431;
                  LODWORD(ppv) = v20;
                  bidTraceW(
                    off_18012A208[0],
                    8633353,
                    L"<CRecordset::SetCmdType|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
                    v24,
                    ppv,
                    v31);
                }
              }
              v42 = v20;
              if ( !(unsigned int)CContext::Failed((CContext *)v38, (const int *)&v42) )
              {
                v25 = v44;
                *a2 = v44;
                (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v25 + 8LL))(v25);
                goto LABEL_114;
              }
              if ( (bidGblFlags & 2) == 0 )
                goto LABEL_114;
              if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
              {
                v6 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
                v7 = 2060297;
                LODWORD(ppv) = 2012;
                goto LABEL_9;
              }
              v8 = 2012;
              v9 = 2060297;
            }
          }
        }
      }
    }
LABEL_11:
    bidTraceW(off_18012A1E8[0], v9, L"<CRecord::GetChildren|ADO|ERR>  line %d\n", v8);
    goto LABEL_114;
  }
  if ( (bidGblFlags & 2) != 0 )
  {
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
    {
      v6 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
      v7 = 1996809;
      LODWORD(ppv) = 1950;
      goto LABEL_9;
    }
    v8 = 1950;
    v9 = 1996809;
    goto LABEL_11;
  }
LABEL_114:
  SysFreeString(bstrString);
  if ( v45 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
    v45 = 0;
  }
  if ( v33 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    v33 = 0;
  }
  if ( v34 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    v34 = 0;
  }
  if ( v44 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v44 + 16LL))(v44);
    v44 = 0;
  }
  if ( v35 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    v35 = 0;
  }
  if ( (bidGblFlags & 2) != 0 && off_18012A578[0] )
  {
    v26 = v39;
    v27 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
    LODWORD(ppv) = v26;
    bidTraceW(off_18012A1E8[0], 2072576, off_18012A578[0], v27, ppv);
  }
  if ( (bidGblFlags & 4) != 0 && v37 != -1 && bidID != -1 )
    ((void (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *))off_180121248[0])(bidID, 0, 0, &v37);
  v28 = v39;
  CXLockContext::~CXLockContext((CXLockContext *)v38);
  return v28;
}

```

## disassembly

```asm
0x18008bae0  push    rbp
0x18008bae2  push    rbx
0x18008bae3  push    rsi
0x18008bae4  push    rdi
0x18008bae5  push    r12
0x18008bae7  push    r14
0x18008bae9  push    r15
0x18008baeb  lea     rbp, [rsp-27h]
0x18008baf0  sub     rsp, 0E0h
0x18008baf7  mov     r8, [rcx+90h]
0x18008bafe  lea     r9, [rcx+20h]; char *
0x18008bb02  mov     rax, rcx
0x18008bb05  mov     r14, rdx
0x18008bb08  mov     rdi, rcx
0x18008bb0b  mov     r12d, 8
0x18008bb11  add     r8, r12; struct CCriticalSection **
0x18008bb14  lea     rcx, [rbp+57h+var_80]; this
0x18008bb18  neg     rax
0x18008bb1b  sbb     rdx, rdx
0x18008bb1e  and     rdx, r9; struct CStdComObjectRoot *
0x18008bb21  call    ??0CXLockContext@@QEAA@PEAVCStdComObjectRoot@@PEAPEAVCCriticalSection@@PEBD@Z; CXLockContext::CXLockContext(CStdComObjectRoot *,CCriticalSection * *,char const *)
0x18008bb26  xor     r15d, r15d
0x18008bb29  mov     [rbp+57h+var_88], 0FFFFFFFFFFFFFFFFh
0x18008bb31  xor     eax, eax
0x18008bb33  mov     [rbp+57h+var_98], r15
0x18008bb37  test    byte ptr cs:_bidGblFlags, 4
0x18008bb3e  xorps   xmm0, xmm0
0x18008bb41  mov     [rbp+57h+arg_10], r15
0x18008bb45  mov     [rbp+57h+var_A0], r15
0x18008bb49  mov     [rbp+57h+var_A8], r15
0x18008bb4d  mov     [rbp+57h+var_B0], r15
0x18008bb51  mov     [rbp+57h+arg_18], r15
0x18008bb55  movups  [rbp+57h+var_48], xmm0
0x18008bb59  mov     [rbp+57h+var_38], rax
0x18008bb5d  mov     [rbp+57h+bstrString], r15
0x18008bb61  mov     [rbp+57h+arg_0], r15d
0x18008bb65  jz      short loc_18008BB92
0x18008bb67  mov     rax, cs:off_18012AB08; "<CRecord::GetChildren|API|ADO> %u#\n"
0x18008bb6e  test    rax, rax
0x18008bb71  jz      short loc_18008BB92
0x18008bb73  lea     rcx, [rdi+98h]; this
0x18008bb7a  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18008bb7f  mov     rdx, cs:off_18012AB08; "<CRecord::GetChildren|API|ADO> %u#\n"
0x18008bb86  lea     rcx, [rbp+57h+var_88]
0x18008bb8a  mov     r8d, eax
0x18008bb8d  call    _bidScopeEnterW
0x18008bb92  test    r14, r14
0x18008bb95  jnz     loc_18008BC27
0x18008bb9b  lea     rdx, [rbp+57h+arg_8]; int *
0x18008bb9f  mov     [rbp+57h+arg_8], 800A0BB9h
0x18008bba6  lea     rcx, [rbp+57h+var_80]; this
0x18008bbaa  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x18008bbaf  test    eax, eax
0x18008bbb1  jz      short loc_18008BC27
0x18008bbb3  test    byte ptr cs:_bidGblFlags, 2
0x18008bbba  jz      loc_18008C4EA
0x18008bbc0  lea     rbx, [rdi+98h]
0x18008bbc7  mov     rcx, rbx; this
0x18008bbca  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18008bbcf  cmp     eax, 0FFFFFFFFh
0x18008bbd2  jz      short loc_18008BC04
0x18008bbd4  mov     rcx, rbx; this
0x18008bbd7  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18008bbdc  mov     edx, 1E6809h
0x18008bbe1  mov     dword ptr [rsp+110h+ppv], 79Ah
0x18008bbe9  mov     rcx, cs:off_18012A1E8; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18008bbf0  lea     r8, aCrecordGetchil_1; "<CRecord::GetChildren|ADO|ERR> %u#, lin"...
0x18008bbf7  mov     r9d, eax
0x18008bbfa  call    _bidTraceW
0x18008bbff  jmp     loc_18008C4EA
0x18008bc04  mov     r9d, 79Ah
0x18008bc0a  mov     edx, 1E6809h
0x18008bc0f  mov     rcx, cs:off_18012A1E8; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18008bc16  lea     r8, aCrecordGetchil; "<CRecord::GetChildren|ADO|ERR>  line %d"...
0x18008bc1d  call    _bidTraceW
0x18008bc22  jmp     loc_18008C4EA
0x18008bc27  cmp     [rdi+110h], r15
0x18008bc2e  jnz     short loc_18008BC93
0x18008bc30  lea     rdx, [rbp+57h+arg_8]; int *
0x18008bc34  mov     [rbp+57h+arg_8], 800A0E78h
0x18008bc3b  lea     rcx, [rbp+57h+var_80]; this
0x18008bc3f  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x18008bc44  test    eax, eax
0x18008bc46  jz      short loc_18008BC93
0x18008bc48  test    byte ptr cs:_bidGblFlags, 2
0x18008bc4f  jz      loc_18008C4EA
0x18008bc55  lea     rbx, [rdi+98h]
0x18008bc5c  mov     rcx, rbx; this
0x18008bc5f  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18008bc64  cmp     eax, 0FFFFFFFFh
0x18008bc67  jz      short loc_18008BC83
0x18008bc69  mov     rcx, rbx; this
0x18008bc6c  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18008bc71  mov     edx, 1E7809h
0x18008bc76  mov     dword ptr [rsp+110h+ppv], 79Eh
0x18008bc7e  jmp     loc_18008BBE9
0x18008bc83  mov     r9d, 79Eh
0x18008bc89  mov     edx, 1E7809h
0x18008bc8e  jmp     loc_18008BC0F
0x18008bc93  lea     rdx, [rbp+57h+arg_0]; enum RecordTypeEnum *
0x18008bc97  mov     rcx, rdi; this
0x18008bc9a  call    ?GetRecordType@CRecord@@AEAAJPEAW4RecordTypeEnum@@@Z; CRecord::GetRecordType(RecordTypeEnum *)
0x18008bc9f  lea     rdx, [rbp+57h+arg_8]; int *
0x18008bca3  mov     [rbp+57h+arg_8], eax
0x18008bca6  lea     rcx, [rbp+57h+var_80]; this
0x18008bcaa  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x18008bcaf  test    eax, eax
0x18008bcb1  jz      short loc_18008BCFE
0x18008bcb3  test    byte ptr cs:_bidGblFlags, 2
0x18008bcba  jz      loc_18008C4EA
0x18008bcc0  lea     rbx, [rdi+98h]
0x18008bcc7  mov     rcx, rbx; this
0x18008bcca  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18008bccf  cmp     eax, 0FFFFFFFFh
0x18008bcd2  jz      short loc_18008BCEE
0x18008bcd4  mov     rcx, rbx; this
0x18008bcd7  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18008bcdc  mov     edx, 1E8409h
0x18008bce1  mov     dword ptr [rsp+110h+ppv], 7A1h
0x18008bce9  jmp     loc_18008BBE9
0x18008bcee  mov     r9d, 7A1h
0x18008bcf4  mov     edx, 1E8409h
0x18008bcf9  jmp     loc_18008BC0F
0x18008bcfe  mov     esi, 1
0x18008bd03  cmp     [rbp+57h+arg_0], esi
0x18008bd06  jz      short loc_18008BD6B
0x18008bd08  lea     rdx, [rbp+57h+arg_0]; int *
0x18008bd0c  mov     [rbp+57h+arg_0], 800A0C93h
0x18008bd13  lea     rcx, [rbp+57h+var_80]; this
0x18008bd17  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x18008bd1c  test    eax, eax
0x18008bd1e  jz      short loc_18008BD6B
0x18008bd20  test    byte ptr cs:_bidGblFlags, 2
0x18008bd27  jz      loc_18008C4EA
0x18008bd2d  lea     rbx, [rdi+98h]
0x18008bd34  mov     rcx, rbx; this
0x18008bd37  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18008bd3c  cmp     eax, 0FFFFFFFFh
0x18008bd3f  jz      short loc_18008BD5B
0x18008bd41  mov     rcx, rbx; this
0x18008bd44  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18008bd49  mov     edx, 1E8C09h
0x18008bd4e  mov     dword ptr [rsp+110h+ppv], 7A3h
0x18008bd56  jmp     loc_18008BBE9
0x18008bd5b  mov     r9d, 7A3h
0x18008bd61  mov     edx, 1E8C09h
0x18008bd66  jmp     loc_18008BC0F
0x18008bd6b  lea     rbx, [rdi+128h]
0x18008bd72  mov     r10, [rbx]
0x18008bd75  test    r10, r10
0x18008bd78  jnz     loc_18008BE0A
0x18008bd7e  mov     rcx, [rdi+110h]
0x18008bd85  lea     rdx, IID_IScopedOperations
0x18008bd8c  mov     r8, rbx
0x18008bd8f  mov     rax, [rcx]
0x18008bd92  mov     rax, [rax]
0x18008bd95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008bd9a  sar     eax, 1Fh
0x18008bd9d  lea     rdx, [rbp+57h+arg_0]; int *
0x18008bda1  and     eax, 800A0CB3h
0x18008bda6  lea     rcx, [rbp+57h+var_80]; this
0x18008bdaa  mov     r8d, 2729h; unsigned int
0x18008bdb0  mov     [rbp+57h+arg_0], eax
0x18008bdb3  call    ?FailedDescription@CContext@@QEAAHAEBJK@Z; CContext::FailedDescription(long const &,ulong)
0x18008bdb8  test    eax, eax
0x18008bdba  jz      short loc_18008BE07
0x18008bdbc  test    byte ptr cs:_bidGblFlags, 2
0x18008bdc3  jz      loc_18008C4EA
0x18008bdc9  lea     rbx, [rdi+98h]
0x18008bdd0  mov     rcx, rbx; this
0x18008bdd3  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18008bdd8  cmp     eax, 0FFFFFFFFh
0x18008bddb  jz      short loc_18008BDF7
0x18008bddd  mov     rcx, rbx; this
0x18008bde0  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18008bde5  mov     edx, 1EA009h
0x18008bdea  mov     dword ptr [rsp+110h+ppv], 7A8h
0x18008bdf2  jmp     loc_18008BBE9
0x18008bdf7  mov     r9d, 7A8h
0x18008bdfd  mov     edx, 1EA009h
0x18008be02  jmp     loc_18008BC0F
0x18008be07  mov     r10, [rbx]
0x18008be0a  mov     ecx, [rdi+238h]
0x18008be10  cmp     ecx, 0FFFFFFFFh
0x18008be13  jnz     short loc_18008BE25
0x18008be15  mov     r9d, [rdi+130h]
0x18008be1c  test    r9d, r9d
0x18008be1f  cmovz   r9d, esi
0x18008be23  jmp     short loc_18008BE48
0x18008be25  sub     ecx, esi
0x18008be27  jz      short loc_18008BE45
0x18008be29  sub     ecx, esi
0x18008be2b  jz      short loc_18008BE3D
0x18008be2d  sub     ecx, esi
0x18008be2f  jz      short loc_18008BE35
0x18008be31  cmp     ecx, esi
0x18008be33  jnz     short loc_18008BE45
0x18008be35  mov     r9d, 13h
0x18008be3b  jmp     short loc_18008BE48
0x18008be3d  mov     r9d, 0Bh
0x18008be43  jmp     short loc_18008BE48
0x18008be45  mov     r9d, esi
0x18008be48  mov     rax, [r10]
0x18008be4b  lea     rcx, [rbp+57h+var_98]
0x18008be4f  mov     [rsp+110h+var_C8], rcx
0x18008be54  lea     r8, WindowName
0x18008be5b  mov     [rsp+110h+var_D0], r15
0x18008be60  lea     rcx, IID_IUnknown
0x18008be67  mov     [rsp+110h+var_D8], r15
0x18008be6c  xor     edx, edx
0x18008be6e  mov     rax, [rax+18h]
0x18008be72  mov     [rsp+110h+var_E0], r15
0x18008be77  mov     [rsp+110h+var_E8], rcx
0x18008be7c  lea     rcx, DBGUID_ROWSET
0x18008be83  mov     [rsp+110h+ppv], rcx
0x18008be88  mov     rcx, r10
0x18008be8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008be90  lea     rdx, [rbp+57h+arg_0]; int *
0x18008be94  mov     [rbp+57h+arg_0], eax
0x18008be97  lea     rcx, [rbp+57h+var_80]; this
0x18008be9b  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x18008bea0  test    eax, eax
0x18008bea2  jz      short loc_18008BEEF
0x18008bea4  test    byte ptr cs:_bidGblFlags, 2
0x18008beab  jz      loc_18008C4EA
0x18008beb1  lea     rbx, [rdi+98h]
0x18008beb8  mov     rcx, rbx; this
0x18008bebb  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18008bec0  cmp     eax, 0FFFFFFFFh
0x18008bec3  jz      short loc_18008BEDF
0x18008bec5  mov     rcx, rbx; this
0x18008bec8  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18008becd  mov     edx, 1EF009h
0x18008bed2  mov     dword ptr [rsp+110h+ppv], 7BCh
0x18008beda  jmp     loc_18008BBE9
0x18008bedf  mov     r9d, 7BCh
0x18008bee5  mov     edx, 1EF009h
0x18008beea  jmp     loc_18008BC0F
0x18008beef  lea     rax, [rbp+57h+arg_10]
0x18008bef3  mov     ebx, 3
0x18008bef8  mov     r8d, ebx; dwClsContext
0x18008befb  mov     [rsp+110h+ppv], rax; ppv
0x18008bf00  lea     r9, IID_IADORecordset; riid
0x18008bf07  xor     edx, edx; pUnkOuter
0x18008bf09  lea     rcx, CLSID_CADORecordset; rclsid
0x18008bf10  call    cs:__imp_CoCreateInstance
0x18008bf17  nop     dword ptr [rax+rax+00h]
0x18008bf1c  lea     rdx, [rbp+57h+arg_0]; int *
0x18008bf20  mov     [rbp+57h+arg_0], eax
0x18008bf23  lea     rcx, [rbp+57h+var_80]; this
0x18008bf27  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x18008bf2c  test    eax, eax
0x18008bf2e  jz      short loc_18008BF7B
0x18008bf30  test    byte ptr cs:_bidGblFlags, 2
0x18008bf37  jz      loc_18008C4EA
0x18008bf3d  lea     rbx, [rdi+98h]
0x18008bf44  mov     rcx, rbx; this
0x18008bf47  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18008bf4c  cmp     eax, 0FFFFFFFFh
0x18008bf4f  jz      short loc_18008BF6B
0x18008bf51  mov     rcx, rbx; this
0x18008bf54  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18008bf59  mov     edx, 1F0409h
0x18008bf5e  mov     dword ptr [rsp+110h+ppv], 7C1h
0x18008bf66  jmp     loc_18008BBE9
0x18008bf6b  mov     r9d, 7C1h
0x18008bf71  mov     edx, 1F0409h
0x18008bf76  jmp     loc_18008BC0F
0x18008bf7b  mov     rcx, [rbp+57h+arg_10]
0x18008bf7f  lea     r8, [rbp+57h+var_A0]
0x18008bf83  lea     rdx, IID_IADORecordsetConstruction
0x18008bf8a  mov     rax, [rcx]
0x18008bf8d  mov     rax, [rax]
0x18008bf90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008bf95  lea     rdx, [rbp+57h+arg_0]; int *
0x18008bf99  mov     [rbp+57h+arg_0], eax
0x18008bf9c  lea     rcx, [rbp+57h+var_80]; this
0x18008bfa0  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x18008bfa5  test    eax, eax
0x18008bfa7  jz      short loc_18008BFF4
0x18008bfa9  test    byte ptr cs:_bidGblFlags, 2
0x18008bfb0  jz      loc_18008C4EA
0x18008bfb6  lea     rbx, [rdi+98h]
0x18008bfbd  mov     rcx, rbx; this
0x18008bfc0  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18008bfc5  cmp     eax, 0FFFFFFFFh
0x18008bfc8  jz      short loc_18008BFE4
0x18008bfca  mov     rcx, rbx; this
0x18008bfcd  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18008bfd2  mov     edx, 1F0C09h
0x18008bfd7  mov     dword ptr [rsp+110h+ppv], 7C3h
0x18008bfdf  jmp     loc_18008BBE9
0x18008bfe4  mov     r9d, 7C3h
0x18008bfea  mov     edx, 1F0C09h
0x18008bfef  jmp     loc_18008BC0F
0x18008bff4  mov     rcx, [rbp+57h+var_A0]
0x18008bff8  mov     rdx, [rbp+57h+var_98]
0x18008bffc  mov     rax, [rcx]
0x18008bfff  mov     rax, [rax+40h]
0x18008c003  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
