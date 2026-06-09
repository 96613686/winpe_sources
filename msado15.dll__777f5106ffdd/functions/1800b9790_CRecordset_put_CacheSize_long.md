# CRecordset::put_CacheSize(long)

- ea: `0x1800b9790`
- end: `0x1800b9b58`
- name: `?put_CacheSize@CRecordset@@UEAAJJ@Z`
- size: `968`
- prototype: `__int64 __fastcall(CRecordset *__hidden this, int)`
- caller_count: `1`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x180076ac0`

## callees

- `0x180020e20`
- `0x180031760`
- `0x180032710`
- `0x18004f1b0`
- `0x1800530f0`
- `0x18006a22c`
- `0x1800ab900`
- `0x1800abe40`
- `0x1800b9790`
- `0x1800c8ebc`
- `0x1800c8f34`
- `0x1800cdb20`
- `0x1800d0010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800b9a76`
- `ole32!CoTaskMemFree` at `0x1800b9a86`
- `ole32!CoTaskMemFree` at `0x1800b9a76`
- `ole32!CoTaskMemFree` at `0x1800b9a86`

## string_xrefs

- `0x1800b9898`: `<CRecordset::put_CacheSize|ADO|ERR> %u#, line %d\n`
- `0x1800b9930`: `<CRecordset::put_CacheSize|ADO|ERR> %u#, line %d\n`
- `0x1800b98be`: `<CRecordset::put_CacheSize|ADO|ERR>  line %d\n`
- `0x1800b9958`: `<CRecordset::put_CacheSize|ADO|ERR>  line %d\n`

## pseudocode

```c
__int64 __fastcall CRecordset::put_CacheSize(CRecordset *this, unsigned int a2)
{
  unsigned int BidObjectID; // eax
  int v5; // ebx
  unsigned int v6; // eax
  __int64 v7; // rdx
  __int64 v8; // r9
  __int64 v9; // rdx
  int PropInt; // eax
  unsigned int v11; // eax
  int v12; // eax
  int v13; // ebx
  unsigned int v14; // eax
  unsigned int v15; // ebx
  __int64 v17; // [rsp+20h] [rbp-69h]
  unsigned int v18; // [rsp+40h] [rbp-49h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-41h] BYREF
  struct IUnknown *v20; // [rsp+50h] [rbp-39h] BYREF
  int v21; // [rsp+58h] [rbp-31h] BYREF
  __int64 v22; // [rsp+60h] [rbp-29h] BYREF
  _BYTE v23[40]; // [rsp+68h] [rbp-21h] BYREF
  int v24; // [rsp+90h] [rbp+7h]
  tagDBPROPIDSET v25; // [rsp+A0h] [rbp+17h] BYREF

  CXLockContext::CXLockContext(
    (CXLockContext *)v23,
    (struct CStdComObjectRoot *)(((unsigned __int64)this + 32)
                               & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64)),
    (struct CCriticalSection **)(*((_QWORD *)this + 38) + 8LL),
    (const char *)this + 32);
  v20 = 0;
  pv = 0;
  v22 = -1;
  if ( (bidGblFlags & 4) != 0 && off_18012ACF0[0] )
  {
    BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
    bidScopeEnterW(&v22, off_18012ACF0[0], BidObjectID, a2, v17);
  }
  v5 = 1;
  if ( *((_BYTE *)this + 1505) == 1 )
  {
    v18 = -2146824577;
    if ( (unsigned int)CContext::Failed((CContext *)v23, (const int *)&v18) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_34;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
      {
        v6 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
        v7 = 2917385;
        LODWORD(v17) = 2849;
LABEL_9:
        bidTraceW(off_18012A208[0], v7, L"<CRecordset::put_CacheSize|ADO|ERR> %u#, line %d\n", v6, v17);
        goto LABEL_34;
      }
      v8 = 2849;
      v9 = 2917385;
LABEL_11:
      bidTraceW(off_18012A208[0], v9, L"<CRecordset::put_CacheSize|ADO|ERR>  line %d\n", v8);
      goto LABEL_34;
    }
  }
  if ( *((_DWORD *)this + 175) == -1 )
  {
    *((_DWORD *)this + 175) = 0;
    PropInt = CRsetProperties::GetPropInt((CRecordset *)((char *)this + 1704), &v20, 0);
    if ( PropInt >= 0 )
    {
      v24 = PropInt;
      if ( !(unsigned int)CContext::IsStatusFalse((CContext *)v23) )
      {
        *((_DWORD *)&v25.guidPropertySet + 4) = 0;
        v18 = 0;
        v21 = 71;
        v25.rgPropertyIDs = (DBPROPID *)&v21;
        v25.guidPropertySet = DBPROPSET_ROWSET;
        v25.cPropertyIDs = 1;
        if ( (int)CRsetProperties::GetPropertiesFromPropInt(
                    (CRecordset *)((char *)this + 1704),
                    v20,
                    &v18,
                    (struct tagDBPROPSET **)&pv,
                    0,
                    1u,
                    &v25) >= 0
          && v18
          && *((_DWORD *)pv + 2)
          && !*(_DWORD *)(*(_QWORD *)pv + 8LL) )
        {
          *((_DWORD *)this + 175) = *(_DWORD *)(*(_QWORD *)pv + 56LL);
        }
      }
    }
    else if ( (bidGblFlags & 2) != 0 )
    {
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) == -1 )
      {
        bidTraceW(off_18012A208[0], 2931721, L"<CRecordset::put_CacheSize|ADO|ERR>  line %d\n", 2863);
      }
      else
      {
        v11 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
        LODWORD(v17) = 2863;
        bidTraceW(off_18012A208[0], 2931721, L"<CRecordset::put_CacheSize|ADO|ERR> %u#, line %d\n", v11, v17);
      }
    }
  }
  if ( !a2 || (v12 = *((_DWORD *)this + 175)) != 0 && (int)a2 > v12 )
    v5 = 0;
  if ( (unsigned int)CContext::ArgFailed((CContext *)v23, v5) )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
      {
        v6 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
        v7 = 2959369;
        LODWORD(v17) = 2890;
        goto LABEL_9;
      }
      v8 = 2890;
      v9 = 2959369;
      goto LABEL_11;
    }
  }
  else
  {
    *((_DWORD *)this + 180) = a2;
  }
LABEL_34:
  if ( pv )
  {
    CoTaskMemFree(*(LPVOID *)pv);
    CoTaskMemFree(pv);
  }
  if ( v20 )
  {
    ((void (__fastcall *)(struct IUnknown *))v20->lpVtbl->Release)(v20);
    v20 = 0;
  }
  if ( (bidGblFlags & 2) != 0 && off_18012A858[0] )
  {
    v13 = v24;
    v14 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
    LODWORD(v17) = v13;
    bidTraceW(off_18012A208[0], 2973696, off_18012A858[0], v14, v17);
  }
  if ( (bidGblFlags & 4) != 0 && v22 != -1 && bidID != -1 )
    ((void (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *))off_180121248[0])(bidID, 0, 0, &v22);
  v15 = v24;
  CXLockContext::~CXLockContext((CXLockContext *)v23);
  return v15;
}

```

## disassembly

```asm
0x1800b9790  mov     [rsp-8+arg_10], rbx
0x1800b9795  mov     [rsp-8+arg_18], rdi
0x1800b979a  push    rbp
0x1800b979b  push    r14
0x1800b979d  push    r15
0x1800b979f  lea     rbp, [rsp-47h]
0x1800b97a4  sub     rsp, 0D0h
0x1800b97ab  mov     rax, cs:__security_cookie
0x1800b97b2  xor     rax, rsp
0x1800b97b5  mov     [rbp+57h+var_20], rax
0x1800b97b9  mov     r8, [rcx+130h]
0x1800b97c0  lea     r9, [rcx+20h]; char *
0x1800b97c4  mov     rax, rcx
0x1800b97c7  mov     r14d, edx
0x1800b97ca  add     r8, 8; struct CCriticalSection **
0x1800b97ce  mov     rdi, rcx
0x1800b97d1  neg     rax
0x1800b97d4  lea     rcx, [rbp+57h+var_78]; this
0x1800b97d8  sbb     rdx, rdx
0x1800b97db  and     rdx, r9; struct CStdComObjectRoot *
0x1800b97de  call    ??0CXLockContext@@QEAA@PEAVCStdComObjectRoot@@PEAPEAVCCriticalSection@@PEBD@Z; CXLockContext::CXLockContext(CStdComObjectRoot *,CCriticalSection * *,char const *)
0x1800b97e3  test    byte ptr cs:_bidGblFlags, 4
0x1800b97ea  mov     [rbp+57h+var_90], 0
0x1800b97f2  mov     [rbp+57h+pv], 0
0x1800b97fa  mov     [rbp+57h+var_80], 0FFFFFFFFFFFFFFFFh
0x1800b9802  jz      short loc_1800B9832
0x1800b9804  mov     rax, cs:off_18012ACF0; "<CRecordset::put_CacheSize|API|ADO> %u#"...
0x1800b980b  test    rax, rax
0x1800b980e  jz      short loc_1800B9832
0x1800b9810  lea     rcx, [rdi+618h]; this
0x1800b9817  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b981c  mov     rdx, cs:off_18012ACF0; "<CRecordset::put_CacheSize|API|ADO> %u#"...
0x1800b9823  lea     rcx, [rbp+57h+var_80]
0x1800b9827  mov     r9d, r14d
0x1800b982a  mov     r8d, eax
0x1800b982d  call    _bidScopeEnterW
0x1800b9832  mov     ebx, 1
0x1800b9837  cmp     [rdi+5E1h], bl
0x1800b983d  jnz     loc_1800B98CF
0x1800b9843  lea     rdx, [rbp+57h+var_A0]; int *
0x1800b9847  mov     [rbp+57h+var_A0], 800A0E7Fh
0x1800b984e  lea     rcx, [rbp+57h+var_78]; this
0x1800b9852  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800b9857  test    eax, eax
0x1800b9859  jz      short loc_1800B98CF
0x1800b985b  test    byte ptr cs:_bidGblFlags, 2
0x1800b9862  jz      loc_1800B9A6A
0x1800b9868  lea     rbx, [rdi+618h]
0x1800b986f  mov     rcx, rbx; this
0x1800b9872  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b9877  cmp     eax, 0FFFFFFFFh
0x1800b987a  jz      short loc_1800B98AC
0x1800b987c  mov     rcx, rbx; this
0x1800b987f  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b9884  mov     edx, 2C8409h
0x1800b9889  mov     dword ptr [rsp+0E0h+var_C0], 0B21h
0x1800b9891  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800b9898  lea     r8, aCrecordsetPutC_2; "<CRecordset::put_CacheSize|ADO|ERR> %u#"...
0x1800b989f  mov     r9d, eax
0x1800b98a2  call    _bidTraceW
0x1800b98a7  jmp     loc_1800B9A6A
0x1800b98ac  mov     r9d, 0B21h
0x1800b98b2  mov     edx, 2C8409h
0x1800b98b7  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800b98be  lea     r8, aCrecordsetPutC_6; "<CRecordset::put_CacheSize|ADO|ERR>  li"...
0x1800b98c5  call    _bidTraceW
0x1800b98ca  jmp     loc_1800B9A6A
0x1800b98cf  cmp     dword ptr [rdi+2BCh], 0FFFFFFFFh
0x1800b98d6  jnz     loc_1800B99F7
0x1800b98dc  lea     r15, [rdi+6A8h]
0x1800b98e3  mov     dword ptr [rdi+2BCh], 0
0x1800b98ed  mov     rcx, r15; this
0x1800b98f0  lea     rdx, [rbp+57h+var_90]; struct IUnknown **
0x1800b98f4  xor     r8d, r8d; unsigned int
0x1800b98f7  call    ?GetPropInt@CRsetProperties@@UEAAJPEAPEAUIUnknown@@K@Z; CRsetProperties::GetPropInt(IUnknown * *,ulong)
0x1800b98fc  test    eax, eax
0x1800b98fe  jns     short loc_1800B9974
0x1800b9900  test    byte ptr cs:_bidGblFlags, 2
0x1800b9907  jz      loc_1800B99F7
0x1800b990d  lea     r15, [rdi+618h]
0x1800b9914  mov     rcx, r15; this
0x1800b9917  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b991c  cmp     eax, 0FFFFFFFFh
0x1800b991f  jz      short loc_1800B9951
0x1800b9921  mov     rcx, r15; this
0x1800b9924  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b9929  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800b9930  lea     r8, aCrecordsetPutC_2; "<CRecordset::put_CacheSize|ADO|ERR> %u#"...
0x1800b9937  mov     r9d, eax
0x1800b993a  mov     dword ptr [rsp+0E0h+var_C0], 0B2Fh
0x1800b9942  mov     edx, 2CBC09h
0x1800b9947  call    _bidTraceW
0x1800b994c  jmp     loc_1800B99F7
0x1800b9951  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800b9958  lea     r8, aCrecordsetPutC_6; "<CRecordset::put_CacheSize|ADO|ERR>  li"...
0x1800b995f  mov     r9d, 0B2Fh
0x1800b9965  mov     edx, 2CBC09h
0x1800b996a  call    _bidTraceW
0x1800b996f  jmp     loc_1800B99F7
0x1800b9974  lea     rcx, [rbp+57h+var_78]; this
0x1800b9978  mov     [rbp+57h+var_50], eax
0x1800b997b  call    ?IsStatusFalse@CContext@@QEAAHXZ; CContext::IsStatusFalse(void)
0x1800b9980  test    eax, eax
0x1800b9982  jnz     short loc_1800B99F7
0x1800b9984  movups  xmm0, xmmword ptr cs:DBPROPSET_ROWSET.Data1
0x1800b998b  mov     rdx, [rbp+57h+var_90]; struct IUnknown *
0x1800b998f  lea     r9, [rbp+57h+pv]; struct tagDBPROPSET **
0x1800b9993  mov     dword ptr [rbp+57h+var_40+1Ch], eax
0x1800b9996  lea     r8, [rbp+57h+var_A0]; unsigned int *
0x1800b999a  mov     [rbp+57h+var_A0], eax
0x1800b999d  mov     rcx, r15; this
0x1800b99a0  lea     rax, [rbp+57h+var_88]
0x1800b99a4  mov     [rbp+57h+var_88], 47h ; 'G'
0x1800b99ab  mov     [rbp+57h+var_40.rgPropertyIDs], rax
0x1800b99af  lea     rax, [rbp+57h+var_40]
0x1800b99b3  mov     [rsp+0E0h+var_B0], rax; struct tagDBPROPIDSET *
0x1800b99b8  mov     [rsp+0E0h+var_B8], ebx; unsigned int
0x1800b99bc  mov     dword ptr [rsp+0E0h+var_C0], 0; unsigned int
0x1800b99c4  movdqu  xmmword ptr [rbp+57h+var_40.guidPropertySet.Data1], xmm0
0x1800b99c9  mov     [rbp+57h+var_40.cPropertyIDs], ebx
0x1800b99cc  call    ?GetPropertiesFromPropInt@CRsetProperties@@UEAAJPEAUIUnknown@@PEAKPEAPEAUtagDBPROPSET@@KKPEAUtagDBPROPIDSET@@@Z; CRsetProperties::GetPropertiesFromPropInt(IUnknown *,ulong *,tagDBPROPSET * *,ulong,ulong,tagDBPROPIDSET *)
0x1800b99d1  test    eax, eax
0x1800b99d3  js      short loc_1800B99F7
0x1800b99d5  cmp     [rbp+57h+var_A0], 0
0x1800b99d9  jz      short loc_1800B99F7
0x1800b99db  mov     rax, [rbp+57h+pv]
0x1800b99df  cmp     dword ptr [rax+8], 0
0x1800b99e3  jz      short loc_1800B99F7
0x1800b99e5  mov     rax, [rax]
0x1800b99e8  cmp     dword ptr [rax+8], 0
0x1800b99ec  jnz     short loc_1800B99F7
0x1800b99ee  mov     eax, [rax+38h]
0x1800b99f1  mov     [rdi+2BCh], eax
0x1800b99f7  test    r14d, r14d
0x1800b99fa  jz      short loc_1800B9A0B
0x1800b99fc  mov     eax, [rdi+2BCh]
0x1800b9a02  test    eax, eax
0x1800b9a04  jz      short loc_1800B9A0D
0x1800b9a06  cmp     r14d, eax
0x1800b9a09  jle     short loc_1800B9A0D
0x1800b9a0b  xor     ebx, ebx
0x1800b9a0d  mov     edx, ebx; int
0x1800b9a0f  lea     rcx, [rbp+57h+var_78]; this
0x1800b9a13  call    ?ArgFailed@CContext@@QEAAHH@Z; CContext::ArgFailed(int)
0x1800b9a18  test    eax, eax
0x1800b9a1a  jz      short loc_1800B9A63
0x1800b9a1c  test    byte ptr cs:_bidGblFlags, 2
0x1800b9a23  jz      short loc_1800B9A6A
0x1800b9a25  lea     rbx, [rdi+618h]
0x1800b9a2c  mov     rcx, rbx; this
0x1800b9a2f  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b9a34  cmp     eax, 0FFFFFFFFh
0x1800b9a37  jz      short loc_1800B9A53
0x1800b9a39  mov     rcx, rbx; this
0x1800b9a3c  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b9a41  mov     edx, 2D2809h
0x1800b9a46  mov     dword ptr [rsp+0E0h+var_C0], 0B4Ah
0x1800b9a4e  jmp     loc_1800B9891
0x1800b9a53  mov     r9d, 0B4Ah
0x1800b9a59  mov     edx, 2D2809h
0x1800b9a5e  jmp     loc_1800B98B7
0x1800b9a63  mov     [rdi+2D0h], r14d
0x1800b9a6a  mov     rcx, [rbp+57h+pv]
0x1800b9a6e  test    rcx, rcx
0x1800b9a71  jz      short loc_1800B9A92
0x1800b9a73  mov     rcx, [rcx]; pv
0x1800b9a76  call    cs:__imp_CoTaskMemFree
0x1800b9a7d  nop     dword ptr [rax+rax+00h]
0x1800b9a82  mov     rcx, [rbp+57h+pv]; pv
0x1800b9a86  call    cs:__imp_CoTaskMemFree
0x1800b9a8d  nop     dword ptr [rax+rax+00h]
0x1800b9a92  mov     rcx, [rbp+57h+var_90]
0x1800b9a96  test    rcx, rcx
0x1800b9a99  jz      short loc_1800B9AAF
0x1800b9a9b  mov     rax, [rcx]
0x1800b9a9e  mov     rax, [rax+10h]
0x1800b9aa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9aa7  mov     [rbp+57h+var_90], 0
0x1800b9aaf  test    byte ptr cs:_bidGblFlags, 2
0x1800b9ab6  jz      short loc_1800B9AF2
0x1800b9ab8  mov     rax, cs:off_18012A858; "<CRecordset::put_CacheSize|API|ADO|RET>"...
0x1800b9abf  test    rax, rax
0x1800b9ac2  jz      short loc_1800B9AF2
0x1800b9ac4  mov     ebx, [rbp+57h+var_50]
0x1800b9ac7  lea     rcx, [rdi+618h]; this
0x1800b9ace  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b9ad3  mov     r8, cs:off_18012A858; "<CRecordset::put_CacheSize|API|ADO|RET>"...
0x1800b9ada  mov     r9d, eax
0x1800b9add  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800b9ae4  mov     edx, 2D6000h
0x1800b9ae9  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x1800b9aed  call    _bidTraceW
0x1800b9af2  test    byte ptr cs:_bidGblFlags, 4
0x1800b9af9  jz      short loc_1800B9B24
0x1800b9afb  cmp     [rbp+57h+var_80], 0FFFFFFFFFFFFFFFFh
0x1800b9b00  jz      short loc_1800B9B24
0x1800b9b02  mov     rcx, cs:_bidID
0x1800b9b09  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800b9b0d  jz      short loc_1800B9B24
0x1800b9b0f  mov     rax, cs:off_180121248
0x1800b9b16  lea     r9, [rbp+57h+var_80]
0x1800b9b1a  xor     r8d, r8d
0x1800b9b1d  xor     edx, edx
0x1800b9b1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9b24  mov     ebx, [rbp+57h+var_50]
0x1800b9b27  lea     rcx, [rbp+57h+var_78]; this
0x1800b9b2b  call    ??1CXLockContext@@QEAA@XZ; CXLockContext::~CXLockContext(void)
0x1800b9b30  mov     eax, ebx
0x1800b9b32  mov     rcx, [rbp+57h+var_20]
0x1800b9b36  xor     rcx, rsp; StackCookie
0x1800b9b39  call    __security_check_cookie
0x1800b9b3e  lea     r11, [rsp+0E0h+var_10]
0x1800b9b46  mov     rbx, [r11+30h]
0x1800b9b4a  mov     rdi, [r11+38h]
0x1800b9b4e  mov     rsp, r11
0x1800b9b51  pop     r15
0x1800b9b53  pop     r14
0x1800b9b55  pop     rbp
0x1800b9b56  retn
```
