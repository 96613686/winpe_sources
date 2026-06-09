# CStream::CopyToEx(_ADOStream *,__int64)

- ea: `0x1800bcdb0`
- end: `0x1800bd8b0`
- name: `?CopyToEx@CStream@@UEAAJPEAU_ADOStream@@_J@Z`
- size: `2816`
- prototype: `__int64 __fastcall(CStream *__hidden this, struct _ADOStream *, __int64)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x180020e20`
- `0x180031760`
- `0x180032710`
- `0x180057bdc`
- `0x18006a22c`
- `0x1800bcdb0`
- `0x1800c8ebc`
- `0x1800c8f34`
- `0x1800cdaea`
- `0x1800cdb20`
- `0x1800d0010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800bd38a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800bd4ab`
- `OLEAUT32!__imp_SysFreeString` at `0x1800bd562`
- `OLEAUT32!__imp_SysFreeString` at `0x1800bd38a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800bd4ab`
- `OLEAUT32!__imp_SysFreeString` at `0x1800bd562`
- `OLEAUT32!__imp_SysStringLen` at `0x1800bd343`
- `OLEAUT32!__imp_SysStringLen` at `0x1800bd50b`
- `OLEAUT32!__imp_SysStringLen` at `0x1800bd520`
- `OLEAUT32!__imp_SysStringLen` at `0x1800bd343`
- `OLEAUT32!__imp_SysStringLen` at `0x1800bd50b`
- `OLEAUT32!__imp_SysStringLen` at `0x1800bd520`

## string_xrefs

- `0x1800bcecc`: `<CStream::CopyToEx|ADO|ERR> %u#, line %d\n`
- `0x1800bcf71`: `<CStream::CopyToEx|ADO|ERR> %u#, line %d\n`
- `0x1800bcfec`: `<CStream::CopyToEx|ADO|ERR> %u#, line %d\n`
- `0x1800bd071`: `<CStream::CopyToEx|ADO|ERR> %u#, line %d\n`
- `0x1800bd0f2`: `<CStream::CopyToEx|ADO|ERR> %u#, line %d\n`
- `0x1800bd16d`: `<CStream::CopyToEx|ADO|ERR> %u#, line %d\n`
- `0x1800bd1e8`: `<CStream::CopyToEx|ADO|ERR> %u#, line %d\n`
- `0x1800bd264`: `<CStream::CopyToEx|ADO|ERR> %u#, line %d\n`
- `0x1800bd31d`: `<CStream::CopyToEx|ADO|ERR> %u#, line %d\n`
- `0x1800bd40b`: `<CStream::CopyToEx|ADO|ERR> %u#, line %d\n`
- `0x1800bd5fe`: `<CStream::CopyToEx|ADO|ERR> %u#, line %d\n`
- `0x1800bd68e`: `<CStream::CopyToEx|ADO|ERR> %u#, line %d\n`
- `0x1800bd716`: `<CStream::CopyToEx|ADO|ERR> %u#, line %d\n`
- `0x1800bd7bb`: `<CStream::CopyToEx|ADO|ERR> %u#, line %d\n`
- `0x1800bcef4`: `<CStream::CopyToEx|ADO|ERR>  line %d\n`
- `0x1800bd7de`: `<CStream::CopyToEx|ADO|ERR>  line %d\n`
- `0x1800bd466`: `<CStream::CopyToEx|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n`
- `0x1800bd48b`: `<CStream::CopyToEx|ADO|ERR> 0x%08x{HRESULT} line %d\n`

## pseudocode

```c
__int64 __fastcall CStream::CopyToEx(CStream *this, struct _ADOStream *a2, __int64 a3)
{
  unsigned int BidObjectID; // eax
  unsigned int v7; // eax
  __int64 v8; // r9
  __int64 v9; // r9
  __int64 v10; // rdx
  __int64 v11; // r9
  __int64 v12; // r9
  __int64 v13; // r9
  __int64 v14; // r9
  __int64 v15; // r9
  __int64 v16; // r9
  __int64 v17; // r9
  unsigned int v18; // esi
  __int64 v19; // r9
  unsigned int v20; // eax
  __int64 v21; // rdx
  __int64 v22; // rdx
  OLECHAR *v23; // rcx
  __int64 v24; // rdx
  UINT v25; // eax
  __int64 v26; // r14
  __int64 v27; // r9
  __int64 v28; // rax
  __int64 v29; // r9
  __int64 v30; // r9
  __int64 v31; // r8
  __int64 v32; // r9
  int v33; // ebx
  unsigned int v34; // eax
  unsigned int v35; // ebx
  __int64 v37; // [rsp+20h] [rbp-A9h]
  int v38; // [rsp+28h] [rbp-A1h]
  int v39; // [rsp+30h] [rbp-99h] BYREF
  BSTR pbstr; // [rsp+38h] [rbp-91h] BYREF
  __int64 v41; // [rsp+40h] [rbp-89h] BYREF
  __int64 v42; // [rsp+48h] [rbp-81h] BYREF
  __int64 v43; // [rsp+50h] [rbp-79h] BYREF
  _BYTE v44[40]; // [rsp+58h] [rbp-71h] BYREF
  int v45; // [rsp+80h] [rbp-49h]
  __int64 v46; // [rsp+90h] [rbp-39h] BYREF
  __int64 v47; // [rsp+98h] [rbp-31h] BYREF
  _BYTE v48[16]; // [rsp+A0h] [rbp-29h] BYREF
  unsigned __int64 v49; // [rsp+B0h] [rbp-19h]

  CXLockContext::CXLockContext(
    (CXLockContext *)v44,
    (struct CStdComObjectRoot *)(((unsigned __int64)this + 32)
                               & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64)),
    (struct CCriticalSection **)(*((_QWORD *)this + 18) + 8LL),
    (const char *)this + 32);
  v47 = 0;
  memset_0(v48, 0, 0x50u);
  v42 = 0;
  v41 = 0;
  v43 = -1;
  if ( (bidGblFlags & 4) != 0 && off_18012ADC8[0] )
  {
    BidObjectID = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
    bidScopeEnterW(&v43, off_18012ADC8[0], BidObjectID, a2, a3);
  }
  if ( a2 || (v39 = -2146825287, !(unsigned int)CContext::Failed((CContext *)v44, &v39)) )
  {
    if ( a2 == this )
      goto LABEL_113;
    if ( *((_QWORD *)this + 21) || (v39 = -2146824584, !(unsigned int)CContext::Failed((CContext *)v44, &v39)) )
    {
      if ( !a3 )
        goto LABEL_111;
      if ( a3 <= -2 && (v39 = -2146825287, (unsigned int)CContext::Failed((CContext *)v44, &v39)) )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_111;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
        {
          v11 = (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
          LODWORD(v37) = 2198;
          bidTraceW(off_18012A210[0], 2250761, L"<CStream::CopyToEx|ADO|ERR> %u#, line %d\n", v11, v37);
          goto LABEL_111;
        }
        v9 = 2198;
        v10 = 2250761;
      }
      else
      {
        v39 = (**(__int64 (__fastcall ***)(struct _ADOStream *, GUID *, __int64 *))a2)(a2, &IID_IADOClass, &v42);
        if ( (unsigned int)CContext::Failed((CContext *)v44, &v39) )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_111;
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
          {
            v12 = (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
            LODWORD(v37) = 2202;
            bidTraceW(off_18012A210[0], 2254857, L"<CStream::CopyToEx|ADO|ERR> %u#, line %d\n", v12, v37);
            goto LABEL_111;
          }
          v9 = 2202;
          v10 = 2254857;
        }
        else
        {
          v39 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v42 + 24LL))(v42, &v41);
          if ( (unsigned int)CContext::Failed((CContext *)v44, &v39) )
          {
            if ( (bidGblFlags & 2) == 0 )
              goto LABEL_111;
            if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
            {
              v13 = (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
              LODWORD(v37) = 2203;
              bidTraceW(off_18012A210[0], 2255881, L"<CStream::CopyToEx|ADO|ERR> %u#, line %d\n", v13, v37);
              goto LABEL_111;
            }
            v9 = 2203;
            v10 = 2255881;
          }
          else if ( *(_QWORD *)(v41 + 168)
                 || (v39 = -2146825287, !(unsigned int)CContext::Failed((CContext *)v44, &v39)) )
          {
            if ( *((_DWORD *)this + 46) == 1
              && *(_DWORD *)(v41 + 184) == 2
              && (unsigned int)CContext::OpFailed((CContext *)v44, 0) )
            {
              if ( (bidGblFlags & 2) == 0 )
                goto LABEL_111;
              if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
              {
                v15 = (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
                LODWORD(v37) = 2212;
                bidTraceW(off_18012A210[0], 2265097, L"<CStream::CopyToEx|ADO|ERR> %u#, line %d\n", v15, v37);
                goto LABEL_111;
              }
              v9 = 2212;
              v10 = 2265097;
            }
            else if ( (*((_DWORD *)this + 48) & 3) == 2
                   && (v39 = -2146825069, (unsigned int)CContext::Failed((CContext *)v44, &v39)) )
            {
              if ( (bidGblFlags & 2) == 0 )
                goto LABEL_111;
              if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
              {
                v16 = (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
                LODWORD(v37) = 2217;
                bidTraceW(off_18012A210[0], 2270217, L"<CStream::CopyToEx|ADO|ERR> %u#, line %d\n", v16, v37);
                goto LABEL_111;
              }
              v9 = 2217;
              v10 = 2270217;
            }
            else if ( *((_DWORD *)this + 46) == 2 && *(_DWORD *)(v41 + 184) == 2 )
            {
              pbstr = 0;
              if ( a3 != -1 )
              {
                while ( a3 )
                {
                  v24 = 2048;
                  if ( a3 <= 2048 )
                    v24 = (unsigned int)a3;
                  v39 = (*(__int64 (__fastcall **)(CStream *, __int64, BSTR *))(*(_QWORD *)this + 240LL))(
                          this,
                          v24,
                          &pbstr);
                  if ( (unsigned int)CContext::Failed((CContext *)v44, &v39) )
                  {
                    if ( (bidGblFlags & 2) == 0 )
                      goto LABEL_111;
                    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
                    {
                      v27 = (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
                      LODWORD(v37) = 2252;
                      bidTraceW(off_18012A210[0], 2306057, L"<CStream::CopyToEx|ADO|ERR> %u#, line %d\n", v27, v37);
                      goto LABEL_111;
                    }
                    v9 = 2252;
                    v10 = 2306057;
                    goto LABEL_110;
                  }
                  v25 = SysStringLen(pbstr);
                  v23 = pbstr;
                  if ( !v25 )
                  {
LABEL_76:
                    SysFreeString(v23);
                    goto LABEL_111;
                  }
                  v26 = SysStringLen(pbstr);
                  v39 = (*(__int64 (__fastcall **)(__int64, BSTR, _QWORD))(*(_QWORD *)v41 + 248LL))(v41, pbstr, 0);
                  CContext::Failed((CContext *)v44, &v39);
                  SysFreeString(pbstr);
                  v18 = v45;
                  if ( v45 < 0 )
                  {
                    if ( (bidGblFlags & 2) == 0 )
                      goto LABEL_111;
                    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) == -1 )
                    {
                      LODWORD(v37) = 2261;
                      v22 = 2315273;
                      goto LABEL_73;
                    }
                    v20 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
                    v21 = 2315273;
                    v38 = 2261;
LABEL_71:
                    LODWORD(v37) = v18;
                    bidTraceW(
                      off_18012A210[0],
                      v21,
                      L"<CStream::CopyToEx|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
                      v20,
                      v37,
                      v38);
                    goto LABEL_111;
                  }
                  a3 -= v26;
                }
                goto LABEL_111;
              }
              v39 = (*(__int64 (__fastcall **)(CStream *, __int64, BSTR *))(*(_QWORD *)this + 240LL))(
                      this,
                      2048,
                      &pbstr);
              if ( !(unsigned int)CContext::Failed((CContext *)v44, &v39) )
              {
                while ( 1 )
                {
                  if ( !SysStringLen(pbstr) )
                  {
                    v23 = pbstr;
                    goto LABEL_76;
                  }
                  v39 = (*(__int64 (__fastcall **)(__int64, BSTR, _QWORD))(*(_QWORD *)v41 + 248LL))(v41, pbstr, 0);
                  CContext::Failed((CContext *)v44, &v39);
                  SysFreeString(pbstr);
                  v18 = v45;
                  if ( v45 < 0 )
                    break;
                  v39 = (*(__int64 (__fastcall **)(CStream *, __int64, BSTR *))(*(_QWORD *)this + 240LL))(
                          this,
                          2048,
                          &pbstr);
                  if ( (unsigned int)CContext::Failed((CContext *)v44, &v39) )
                  {
                    if ( (bidGblFlags & 2) == 0 )
                      goto LABEL_111;
                    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
                    {
                      v19 = (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
                      LODWORD(v37) = 2236;
                      bidTraceW(off_18012A210[0], 2289673, L"<CStream::CopyToEx|ADO|ERR> %u#, line %d\n", v19, v37);
                      goto LABEL_111;
                    }
                    v9 = 2236;
                    v10 = 2289673;
                    goto LABEL_110;
                  }
                }
                if ( (bidGblFlags & 2) == 0 )
                  goto LABEL_111;
                if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
                {
                  v20 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
                  v21 = 2288649;
                  v38 = 2235;
                  goto LABEL_71;
                }
                LODWORD(v37) = 2235;
                v22 = 2288649;
LABEL_73:
                bidTraceW(off_18012A210[0], v22, L"<CStream::CopyToEx|ADO|ERR> 0x%08x{HRESULT} line %d\n", v18, v37);
                goto LABEL_111;
              }
              if ( (bidGblFlags & 2) == 0 )
              {
LABEL_111:
                if ( v42 )
                {
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
                  v42 = 0;
                }
                goto LABEL_113;
              }
              if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
              {
                v17 = (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
                LODWORD(v37) = 2230;
                bidTraceW(off_18012A210[0], 2283529, L"<CStream::CopyToEx|ADO|ERR> %u#, line %d\n", v17, v37);
                goto LABEL_111;
              }
              v9 = 2230;
              v10 = 2283529;
            }
            else
            {
              v46 = 0;
              v28 = *((_QWORD *)this + 1);
              pbstr = 0;
              v39 = (*(__int64 (__fastcall **)(char *, __int64 *))(v28 + 72))((char *)this + 8, &v47);
              if ( (unsigned int)CContext::Failed((CContext *)v44, &v39) )
              {
                if ( (bidGblFlags & 2) == 0 )
                  goto LABEL_111;
                if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
                {
                  v29 = (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
                  LODWORD(v37) = 2272;
                  bidTraceW(off_18012A210[0], 2326537, L"<CStream::CopyToEx|ADO|ERR> %u#, line %d\n", v29, v37);
                  goto LABEL_111;
                }
                v9 = 2272;
                v10 = 2326537;
              }
              else
              {
                v39 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *, __int64))(**((_QWORD **)this + 21) + 96LL))(
                        *((_QWORD *)this + 21),
                        v48,
                        1);
                if ( (unsigned int)CContext::Failed((CContext *)v44, &v39) )
                {
                  if ( (bidGblFlags & 2) == 0 )
                    goto LABEL_111;
                  if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
                  {
                    v30 = (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
                    LODWORD(v37) = 2274;
                    bidTraceW(off_18012A210[0], 2328585, L"<CStream::CopyToEx|ADO|ERR> %u#, line %d\n", v30, v37);
                    goto LABEL_111;
                  }
                  v9 = 2274;
                  v10 = 2328585;
                }
                else
                {
                  v31 = v49;
                  if ( a3 != -1 && a3 < v49 )
                    v31 = a3;
                  v39 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int64 *, BSTR *))(**((_QWORD **)this + 21)
                                                                                              + 56LL))(
                          *((_QWORD *)this + 21),
                          *(_QWORD *)(v41 + 168),
                          v31,
                          &v46,
                          &pbstr);
                  if ( !(unsigned int)CContext::Failed((CContext *)v44, &v39) || (bidGblFlags & 2) == 0 )
                    goto LABEL_111;
                  if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
                  {
                    v32 = (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
                    LODWORD(v37) = 2290;
                    bidTraceW(off_18012A210[0], 2344969, L"<CStream::CopyToEx|ADO|ERR> %u#, line %d\n", v32, v37);
                    goto LABEL_111;
                  }
                  v9 = 2290;
                  v10 = 2344969;
                }
              }
            }
          }
          else
          {
            if ( (bidGblFlags & 2) == 0 )
              goto LABEL_111;
            if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
            {
              v14 = (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
              LODWORD(v37) = 2206;
              bidTraceW(off_18012A210[0], 2258953, L"<CStream::CopyToEx|ADO|ERR> %u#, line %d\n", v14, v37);
              goto LABEL_111;
            }
            v9 = 2206;
            v10 = 2258953;
          }
        }
      }
    }
    else
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_111;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
      {
        v8 = (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
        LODWORD(v37) = 2178;
        bidTraceW(off_18012A210[0], 2230281, L"<CStream::CopyToEx|ADO|ERR> %u#, line %d\n", v8, v37);
        goto LABEL_111;
      }
      v9 = 2178;
      v10 = 2230281;
    }
LABEL_110:
    bidTraceW(off_18012A210[0], v10, L"<CStream::CopyToEx|ADO|ERR>  line %d\n", v9);
    goto LABEL_111;
  }
  if ( (bidGblFlags & 2) == 0 )
    goto LABEL_116;
  if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) == -1 )
  {
    bidTraceW(off_18012A210[0], 2216969, L"<CStream::CopyToEx|ADO|ERR>  line %d\n", 2165);
  }
  else
  {
    v7 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
    LODWORD(v37) = 2165;
    bidTraceW(off_18012A210[0], 2216969, L"<CStream::CopyToEx|ADO|ERR> %u#, line %d\n", v7, v37);
  }
LABEL_113:
  if ( (bidGblFlags & 2) != 0 && off_18012A8F8[0] )
  {
    v33 = v45;
    v34 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
    LODWORD(v37) = v33;
    bidTraceW(off_18012A210[0], 2351104, off_18012A8F8[0], v34, v37);
  }
LABEL_116:
  if ( (bidGblFlags & 4) != 0 && v43 != -1 && bidID != -1 )
    ((void (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *))off_180121248[0])(bidID, 0, 0, &v43);
  v35 = v45;
  CXLockContext::~CXLockContext((CXLockContext *)v44);
  return v35;
}

```

## disassembly

```asm
0x1800bcdb0  mov     [rsp-8+arg_18], rbx
0x1800bcdb5  push    rbp
0x1800bcdb6  push    rsi
0x1800bcdb7  push    rdi
0x1800bcdb8  push    r14
0x1800bcdba  push    r15
0x1800bcdbc  lea     rbp, [rsp-37h]
0x1800bcdc1  sub     rsp, 100h
0x1800bcdc8  mov     rax, cs:__security_cookie
0x1800bcdcf  xor     rax, rsp
0x1800bcdd2  mov     [rbp+57h+var_30], rax
0x1800bcdd6  mov     rbx, r8
0x1800bcdd9  lea     r9, [rcx+20h]; char *
0x1800bcddd  mov     r8, [rcx+90h]
0x1800bcde4  mov     rax, rcx
0x1800bcde7  mov     rsi, rdx
0x1800bcdea  add     r8, 8; struct CCriticalSection **
0x1800bcdee  neg     rax
0x1800bcdf1  mov     rdi, rcx
0x1800bcdf4  lea     rcx, [rbp+57h+var_C8]; this
0x1800bcdf8  sbb     rdx, rdx
0x1800bcdfb  and     rdx, r9; struct CStdComObjectRoot *
0x1800bcdfe  call    ??0CXLockContext@@QEAA@PEAVCStdComObjectRoot@@PEAPEAVCCriticalSection@@PEBD@Z; CXLockContext::CXLockContext(CStdComObjectRoot *,CCriticalSection * *,char const *)
0x1800bce03  xor     edx, edx; Val
0x1800bce05  mov     [rbp+57h+var_88], 0
0x1800bce0d  lea     rcx, [rbp+57h+var_80]; void *
0x1800bce11  lea     r8d, [rdx+50h]; Size
0x1800bce15  call    memset_0
0x1800bce1a  test    byte ptr cs:_bidGblFlags, 4
0x1800bce21  mov     [rsp+120h+var_D8], 0
0x1800bce2a  mov     [rsp+120h+var_E0], 0
0x1800bce33  mov     [rbp+57h+var_D0], 0FFFFFFFFFFFFFFFFh
0x1800bce3b  jz      short loc_1800BCE70
0x1800bce3d  mov     rax, cs:off_18012ADC8; "<CStream::CopyToEx|API|ADO> %u#, Stream"...
0x1800bce44  test    rax, rax
0x1800bce47  jz      short loc_1800BCE70
0x1800bce49  lea     rcx, [rdi+98h]; this
0x1800bce50  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800bce55  mov     rdx, cs:off_18012ADC8; "<CStream::CopyToEx|API|ADO> %u#, Stream"...
0x1800bce5c  lea     rcx, [rbp+57h+var_D0]
0x1800bce60  mov     r9, rsi
0x1800bce63  mov     [rsp+120h+var_100], rbx
0x1800bce68  mov     r8d, eax
0x1800bce6b  call    _bidScopeEnterW
0x1800bce70  mov     r15d, 2
0x1800bce76  mov     r14d, 800A0BB9h
0x1800bce7c  test    rsi, rsi
0x1800bce7f  jnz     loc_1800BCF10
0x1800bce85  lea     rdx, [rsp+120h+var_F0]; int *
0x1800bce8a  mov     [rsp+120h+var_F0], r14d
0x1800bce8f  lea     rcx, [rbp+57h+var_C8]; this
0x1800bce93  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800bce98  test    eax, eax
0x1800bce9a  jz      short loc_1800BCF10
0x1800bce9c  test    byte ptr cs:_bidGblFlags, r15b
0x1800bcea3  jz      loc_1800BD84C
0x1800bcea9  lea     rbx, [rdi+98h]
0x1800bceb0  mov     rcx, rbx; this
0x1800bceb3  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800bceb8  cmp     eax, 0FFFFFFFFh
0x1800bcebb  jz      short loc_1800BCEED
0x1800bcebd  mov     rcx, rbx; this
0x1800bcec0  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800bcec5  mov     rcx, cs:off_18012A210; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800bcecc  lea     r8, aCstreamCopytoe; "<CStream::CopyToEx|ADO|ERR> %u#, line %"...
0x1800bced3  mov     r9d, eax
0x1800bced6  mov     dword ptr [rsp+120h+var_100], 875h
0x1800bcede  mov     edx, 21D409h
0x1800bcee3  call    _bidTraceW
0x1800bcee8  jmp     loc_1800BD809
0x1800bceed  mov     rcx, cs:off_18012A210; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800bcef4  lea     r8, aCstreamCopytoe_3; "<CStream::CopyToEx|ADO|ERR>  line %d\n"
0x1800bcefb  mov     r9d, 875h
0x1800bcf01  mov     edx, 21D409h
0x1800bcf06  call    _bidTraceW
0x1800bcf0b  jmp     loc_1800BD809
0x1800bcf10  cmp     rsi, rdi
0x1800bcf13  jz      loc_1800BD809
0x1800bcf19  cmp     qword ptr [rdi+0A8h], 0
0x1800bcf21  jnz     short loc_1800BCF92
0x1800bcf23  lea     rdx, [rsp+120h+var_F0]; int *
0x1800bcf28  mov     [rsp+120h+var_F0], 800A0E78h
0x1800bcf30  lea     rcx, [rbp+57h+var_C8]; this
0x1800bcf34  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800bcf39  test    eax, eax
0x1800bcf3b  jz      short loc_1800BCF92
0x1800bcf3d  test    byte ptr cs:_bidGblFlags, r15b
0x1800bcf44  jz      loc_1800BD7EA
0x1800bcf4a  lea     rbx, [rdi+98h]
0x1800bcf51  mov     rcx, rbx; this
0x1800bcf54  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800bcf59  cmp     eax, 0FFFFFFFFh
0x1800bcf5c  jz      short loc_1800BCF82
0x1800bcf5e  mov     rcx, rbx; this
0x1800bcf61  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800bcf66  mov     r9d, eax
0x1800bcf69  mov     dword ptr [rsp+120h+var_100], 882h
0x1800bcf71  lea     r8, aCstreamCopytoe; "<CStream::CopyToEx|ADO|ERR> %u#, line %"...
0x1800bcf78  mov     edx, 220809h
0x1800bcf7d  jmp     loc_1800BD495
0x1800bcf82  mov     r9d, 882h
0x1800bcf88  mov     edx, 220809h
0x1800bcf8d  jmp     loc_1800BD7D7
0x1800bcf92  test    rbx, rbx
0x1800bcf95  jz      loc_1800BD7EA
0x1800bcf9b  cmp     rbx, 0FFFFFFFFFFFFFFFEh
0x1800bcf9f  jg      short loc_1800BD00D
0x1800bcfa1  lea     rdx, [rsp+120h+var_F0]; int *
0x1800bcfa6  mov     [rsp+120h+var_F0], r14d
0x1800bcfab  lea     rcx, [rbp+57h+var_C8]; this
0x1800bcfaf  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800bcfb4  test    eax, eax
0x1800bcfb6  jz      short loc_1800BD00D
0x1800bcfb8  test    byte ptr cs:_bidGblFlags, r15b
0x1800bcfbf  jz      loc_1800BD7EA
0x1800bcfc5  lea     rbx, [rdi+98h]
0x1800bcfcc  mov     rcx, rbx; this
0x1800bcfcf  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800bcfd4  cmp     eax, 0FFFFFFFFh
0x1800bcfd7  jz      short loc_1800BCFFD
0x1800bcfd9  mov     rcx, rbx; this
0x1800bcfdc  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800bcfe1  mov     r9d, eax
0x1800bcfe4  mov     dword ptr [rsp+120h+var_100], 896h
0x1800bcfec  lea     r8, aCstreamCopytoe; "<CStream::CopyToEx|ADO|ERR> %u#, line %"...
0x1800bcff3  mov     edx, 225809h
0x1800bcff8  jmp     loc_1800BD495
0x1800bcffd  mov     r9d, 896h
0x1800bd003  mov     edx, 225809h
0x1800bd008  jmp     loc_1800BD7D7
0x1800bd00d  mov     rax, [rsi]
0x1800bd010  lea     r8, [rsp+120h+var_D8]
0x1800bd015  lea     rdx, IID_IADOClass
0x1800bd01c  mov     rcx, rsi
0x1800bd01f  mov     rax, [rax]
0x1800bd022  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd027  lea     rdx, [rsp+120h+var_F0]; int *
0x1800bd02c  mov     [rsp+120h+var_F0], eax
0x1800bd030  lea     rcx, [rbp+57h+var_C8]; this
0x1800bd034  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800bd039  test    eax, eax
0x1800bd03b  jz      short loc_1800BD092
0x1800bd03d  test    byte ptr cs:_bidGblFlags, r15b
0x1800bd044  jz      loc_1800BD7EA
0x1800bd04a  lea     rbx, [rdi+98h]
0x1800bd051  mov     rcx, rbx; this
0x1800bd054  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800bd059  cmp     eax, 0FFFFFFFFh
0x1800bd05c  jz      short loc_1800BD082
0x1800bd05e  mov     rcx, rbx; this
0x1800bd061  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800bd066  mov     r9d, eax
0x1800bd069  mov     dword ptr [rsp+120h+var_100], 89Ah
0x1800bd071  lea     r8, aCstreamCopytoe; "<CStream::CopyToEx|ADO|ERR> %u#, line %"...
0x1800bd078  mov     edx, 226809h
0x1800bd07d  jmp     loc_1800BD495
0x1800bd082  mov     r9d, 89Ah
0x1800bd088  mov     edx, 226809h
0x1800bd08d  jmp     loc_1800BD7D7
0x1800bd092  mov     rcx, [rsp+120h+var_D8]
0x1800bd097  lea     rdx, [rsp+120h+var_E0]
0x1800bd09c  mov     rax, [rcx]
0x1800bd09f  mov     rax, [rax+18h]
0x1800bd0a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd0a8  lea     rdx, [rsp+120h+var_F0]; int *
0x1800bd0ad  mov     [rsp+120h+var_F0], eax
0x1800bd0b1  lea     rcx, [rbp+57h+var_C8]; this
0x1800bd0b5  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800bd0ba  test    eax, eax
0x1800bd0bc  jz      short loc_1800BD113
0x1800bd0be  test    byte ptr cs:_bidGblFlags, r15b
0x1800bd0c5  jz      loc_1800BD7EA
0x1800bd0cb  lea     rbx, [rdi+98h]
0x1800bd0d2  mov     rcx, rbx; this
0x1800bd0d5  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800bd0da  cmp     eax, 0FFFFFFFFh
0x1800bd0dd  jz      short loc_1800BD103
0x1800bd0df  mov     rcx, rbx; this
0x1800bd0e2  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800bd0e7  mov     r9d, eax
0x1800bd0ea  mov     dword ptr [rsp+120h+var_100], 89Bh
0x1800bd0f2  lea     r8, aCstreamCopytoe; "<CStream::CopyToEx|ADO|ERR> %u#, line %"...
0x1800bd0f9  mov     edx, 226C09h
0x1800bd0fe  jmp     loc_1800BD495
0x1800bd103  mov     r9d, 89Bh
0x1800bd109  mov     edx, 226C09h
0x1800bd10e  jmp     loc_1800BD7D7
0x1800bd113  mov     rax, [rsp+120h+var_E0]
0x1800bd118  cmp     qword ptr [rax+0A8h], 0
0x1800bd120  jnz     short loc_1800BD18E
0x1800bd122  lea     rdx, [rsp+120h+var_F0]; int *
0x1800bd127  mov     [rsp+120h+var_F0], r14d
0x1800bd12c  lea     rcx, [rbp+57h+var_C8]; this
0x1800bd130  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800bd135  test    eax, eax
0x1800bd137  jz      short loc_1800BD18E
0x1800bd139  test    byte ptr cs:_bidGblFlags, r15b
0x1800bd140  jz      loc_1800BD7EA
0x1800bd146  lea     rbx, [rdi+98h]
0x1800bd14d  mov     rcx, rbx; this
0x1800bd150  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800bd155  cmp     eax, 0FFFFFFFFh
0x1800bd158  jz      short loc_1800BD17E
0x1800bd15a  mov     rcx, rbx; this
0x1800bd15d  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800bd162  mov     r9d, eax
0x1800bd165  mov     dword ptr [rsp+120h+var_100], 89Eh
0x1800bd16d  lea     r8, aCstreamCopytoe; "<CStream::CopyToEx|ADO|ERR> %u#, line %"...
0x1800bd174  mov     edx, 227809h
0x1800bd179  jmp     loc_1800BD495
0x1800bd17e  mov     r9d, 89Eh
0x1800bd184  mov     edx, 227809h
0x1800bd189  jmp     loc_1800BD7D7
0x1800bd18e  cmp     dword ptr [rdi+0B8h], 1
0x1800bd195  jnz     short loc_1800BD209
0x1800bd197  mov     rax, [rsp+120h+var_E0]
0x1800bd19c  cmp     [rax+0B8h], r15d
0x1800bd1a3  jnz     short loc_1800BD209
0x1800bd1a5  xor     edx, edx; int
0x1800bd1a7  lea     rcx, [rbp+57h+var_C8]; this
0x1800bd1ab  call    ?OpFailed@CContext@@QEAAHH@Z; CContext::OpFailed(int)
0x1800bd1b0  test    eax, eax
0x1800bd1b2  jz      short loc_1800BD209
0x1800bd1b4  test    byte ptr cs:_bidGblFlags, r15b
0x1800bd1bb  jz      loc_1800BD7EA
0x1800bd1c1  lea     rbx, [rdi+98h]
0x1800bd1c8  mov     rcx, rbx; this
0x1800bd1cb  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800bd1d0  cmp     eax, 0FFFFFFFFh
0x1800bd1d3  jz      short loc_1800BD1F9
0x1800bd1d5  mov     rcx, rbx; this
0x1800bd1d8  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800bd1dd  mov     r9d, eax
0x1800bd1e0  mov     dword ptr [rsp+120h+var_100], 8A4h
0x1800bd1e8  lea     r8, aCstreamCopytoe; "<CStream::CopyToEx|ADO|ERR> %u#, line %"...
0x1800bd1ef  mov     edx, 229009h
0x1800bd1f4  jmp     loc_1800BD495
0x1800bd1f9  mov     r9d, 8A4h
0x1800bd1ff  mov     edx, 229009h
0x1800bd204  jmp     loc_1800BD7D7
0x1800bd209  mov     eax, [rdi+0C0h]
0x1800bd20f  and     al, 3
0x1800bd211  cmp     al, r15b
0x1800bd214  jnz     short loc_1800BD285
0x1800bd216  lea     rdx, [rsp+120h+var_F0]; int *
0x1800bd21b  mov     [rsp+120h+var_F0], 800A0C93h
0x1800bd223  lea     rcx, [rbp+57h+var_C8]; this
0x1800bd227  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800bd22c  test    eax, eax
0x1800bd22e  jz      short loc_1800BD285
0x1800bd230  test    byte ptr cs:_bidGblFlags, r15b
0x1800bd237  jz      loc_1800BD7EA
0x1800bd23d  lea     rbx, [rdi+98h]
0x1800bd244  mov     rcx, rbx; this
0x1800bd247  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800bd24c  cmp     eax, 0FFFFFFFFh
0x1800bd24f  jz      short loc_1800BD275
0x1800bd251  mov     rcx, rbx; this
0x1800bd254  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800bd259  mov     r9d, eax
0x1800bd25c  mov     dword ptr [rsp+120h+var_100], 8A9h
0x1800bd264  lea     r8, aCstreamCopytoe; "<CStream::CopyToEx|ADO|ERR> %u#, line %"...
0x1800bd26b  mov     edx, 22A409h
0x1800bd270  jmp     loc_1800BD495
0x1800bd275  mov     r9d, 8A9h
0x1800bd27b  mov     edx, 22A409h
0x1800bd280  jmp     loc_1800BD7D7
0x1800bd285  cmp     [rdi+0B8h], r15d
0x1800bd28c  jnz     loc_1800BD61F
0x1800bd292  mov     rax, [rsp+120h+var_E0]
0x1800bd297  cmp     [rax+0B8h], r15d
0x1800bd29e  jnz     loc_1800BD61F
0x1800bd2a4  mov     [rsp+120h+pbstr], 0
0x1800bd2ad  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800bd2b1  jnz     loc_1800BD4BC
0x1800bd2b7  mov     rax, [rdi]
0x1800bd2ba  lea     r8, [rsp+120h+pbstr]
0x1800bd2bf  mov     edx, 800h
0x1800bd2c4  mov     rcx, rdi
0x1800bd2c7  mov     rax, [rax+0F0h]
0x1800bd2ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd2d3  lea     rdx, [rsp+120h+var_F0]; int *
0x1800bd2d8  mov     [rsp+120h+var_F0], eax
0x1800bd2dc  lea     rcx, [rbp+57h+var_C8]; this
0x1800bd2e0  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800bd2e5  test    eax, eax
0x1800bd2e7  jz      short loc_1800BD33E
0x1800bd2e9  test    byte ptr cs:_bidGblFlags, r15b
0x1800bd2f0  jz      loc_1800BD7EA
0x1800bd2f6  lea     rbx, [rdi+98h]
0x1800bd2fd  mov     rcx, rbx; this
0x1800bd300  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800bd305  cmp     eax, 0FFFFFFFFh
0x1800bd308  jz      short loc_1800BD32E
0x1800bd30a  mov     rcx, rbx; this
0x1800bd30d  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800bd312  mov     r9d, eax
0x1800bd315  mov     dword ptr [rsp+120h+var_100], 8B6h
0x1800bd31d  lea     r8, aCstreamCopytoe; "<CStream::CopyToEx|ADO|ERR> %u#, line %"...
0x1800bd324  mov     edx, 22D809h
  ... truncated ...
```
