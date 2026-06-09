# CRecordset::ProtectAnchor(unsigned __int64,unsigned __int64 *)

- ea: `0x1800b0a64`
- end: `0x1800b1223`
- name: `?ProtectAnchor@CRecordset@@AEAAJ_KPEA_K@Z`
- size: `1983`
- prototype: `__int64 __fastcall(CRecordset *__hidden this, unsigned __int64, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `17`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800a8e84`

## callees

- `0x180001514`
- `0x180006610`
- `0x180009240`
- `0x180020e20`
- `0x180027790`
- `0x180027c4c`
- `0x180041290`
- `0x18004d0d0`
- `0x180050bc0`
- `0x180054098`
- `0x18006a22c`
- `0x1800b0a64`
- `0x1800c8f34`
- `0x1800cdac6`
- `0x1800cdad2`
- `0x1800cdaea`
- `0x1800d0010`

## import_xrefs

- `MSDART!MpHeapAlloc` at `0x1800b0b57`
- `MSDART!MpHeapAlloc` at `0x1800b0b57`
- `MSDART!MpHeapFree` at `0x1800b11d9`
- `MSDART!MpHeapFree` at `0x1800b11d9`
- `ole32!CoTaskMemAlloc` at `0x1800b0db7`
- `ole32!CoTaskMemAlloc` at `0x1800b0db7`
- `ole32!CoTaskMemFree` at `0x1800b0e28`
- `ole32!CoTaskMemFree` at `0x1800b118d`
- `ole32!CoTaskMemFree` at `0x1800b11bb`
- `ole32!CoTaskMemFree` at `0x1800b0e28`
- `ole32!CoTaskMemFree` at `0x1800b118d`
- `ole32!CoTaskMemFree` at `0x1800b11bb`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800b10b5`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800b10b5`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CRecordset::ProtectAnchor(CRecordset *this, unsigned __int64 a2, unsigned __int64 *a3)
{
  __int64 v6; // rbx
  SIZE_T v7; // r12
  unsigned __int8 *v8; // rsi
  unsigned int BidObjectID; // eax
  __int64 v10; // rdx
  __int64 v11; // r9
  __int64 v12; // rdx
  char *v13; // r14
  unsigned int v14; // eax
  unsigned __int64 i; // r14
  int v16; // r15d
  __int64 v17; // r14
  char v18; // r15
  size_t v19; // r8
  __int64 *p_Buf1; // rcx
  int v21; // r14d
  void *v22; // r15
  char v23; // r15
  char v24; // r14
  int v25; // r14d
  int v26; // r15d
  int v27; // eax
  char v28; // al
  unsigned __int64 v29; // rax
  int v30; // r14d
  int v31; // r15d
  int v32; // eax
  char v33; // al
  unsigned __int64 v34; // rax
  unsigned __int64 j; // rbx
  void *v36; // rcx
  unsigned int v37; // ebx
  __int64 v39; // [rsp+20h] [rbp-A9h]
  int v40; // [rsp+50h] [rbp-79h]
  char *v41; // [rsp+58h] [rbp-71h]
  unsigned __int8 *v42; // [rsp+60h] [rbp-69h] BYREF
  unsigned __int64 v43; // [rsp+68h] [rbp-61h] BYREF
  struct IRowset *v44; // [rsp+70h] [rbp-59h] BYREF
  LPVOID pv; // [rsp+78h] [rbp-51h] BYREF
  SIZE_T v46; // [rsp+80h] [rbp-49h]
  __int64 v47; // [rsp+88h] [rbp-41h]
  __int64 Buf1; // [rsp+90h] [rbp-39h] BYREF
  __int64 v49; // [rsp+98h] [rbp-31h] BYREF
  int Interface; // [rsp+A0h] [rbp-29h] BYREF
  __int64 v51; // [rsp+A8h] [rbp-21h] BYREF
  unsigned __int64 *v52; // [rsp+B0h] [rbp-19h] BYREF
  __int64 v53; // [rsp+B8h] [rbp-11h]
  _BYTE v54[32]; // [rsp+C0h] [rbp-9h] BYREF
  unsigned __int64 v55; // [rsp+E0h] [rbp+17h]
  unsigned int v56; // [rsp+E8h] [rbp+1Fh]
  int IRowset; // [rsp+130h] [rbp+67h] BYREF
  char v58; // [rsp+148h] [rbp+7Fh]

  v55 = ((unsigned __int64)this + 32) & -(__int64)(this != 0);
  CContext::Init((CContext *)v54);
  v42 = 0;
  Buf1 = 0;
  v43 = 4294967167LL;
  v52 = &v43;
  v49 = 0;
  v46 = 0;
  v47 = 0;
  v44 = 0;
  v6 = 0;
  v51 = 0;
  pv = 0;
  if ( *((_DWORD *)this + 176)
    || !(unsigned int)CRsetOptionalInterface<IRowsetLocate,&_GUID const IID_IRowsetLocate>::BoolCheck((char *)this + 312)
    || (*((_DWORD *)this + 174) & 0x100) == 0 )
  {
    goto LABEL_105;
  }
  v7 = *((_QWORD *)this + 100);
  v8 = (unsigned __int8 *)*((_QWORD *)this + 101);
  v53 = *((_QWORD *)this + 96);
  if ( !*((_DWORD *)this + 199) )
  {
    v42 = v8;
    v8 = (unsigned __int8 *)&v42;
  }
  v41 = (char *)MpHeapAlloc(g_hHeapHandle, 10485760, 24 * a2);
  if ( (unsigned int)CContext::MemFailed((CContext *)v54, v41) )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
      {
        BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
        LODWORD(v39) = 11164;
        v10 = 11431945;
        goto LABEL_10;
      }
      v11 = 11164;
      v12 = 11431945;
      goto LABEL_12;
    }
    goto LABEL_94;
  }
  v13 = v41;
  memset_0(v41, 0, 24 * a2);
  if ( a2 )
  {
    IRowset = CRecordset::GetIRowset(this, &v44);
    if ( (unsigned int)CContext::Failed((CContext *)v54, &IRowset) )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) == -1 )
        {
          bidTraceW(off_18012A208[0], 11437065, L"<CRecordset::ProtectAnchor|ADO|ERR>  line %d\n", 11169);
        }
        else
        {
          v14 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
          bidTraceW(off_18012A208[0], 11437065, L"<CRecordset::ProtectAnchor|ADO|ERR> %u#, line %d\n", v14, 11169);
        }
      }
      goto LABEL_95;
    }
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= a2 )
    {
      v16 = 0;
      v40 = 0;
      LOBYTE(IRowset) = 0;
      v58 = 0;
      while ( (v7 != 1 || *v8 != byBmkFirst) && a2 )
      {
        v17 = 0;
        v18 = *((_BYTE *)this + 1256);
        while ( 1 )
        {
          v19 = *(_QWORD *)&v41[24 * v17 + 8];
          p_Buf1 = *(__int64 **)&v41[24 * v17];
          if ( v18 == 2 || v18 == 3 )
          {
            Buf1 = *(_QWORD *)&v41[24 * v17];
            p_Buf1 = &Buf1;
          }
          if ( v19 == v7 && !memcmp_0(p_Buf1, v8, v19) )
            break;
          if ( ++v17 >= a2 )
          {
            v16 = v40;
            goto LABEL_40;
          }
        }
        if ( v18 == 1 && pv )
        {
          CoTaskMemFree(pv);
          pv = 0;
        }
        v23 = v58;
        v24 = IRowset;
        if ( !v58 || !(_BYTE)IRowset )
        {
          if ( !v6 )
          {
            Interface = CRsetOptionalInterface<IRowsetLocate,&_GUID const IID_IRowsetLocate>::GetInterface(
                          (char *)this + 312,
                          &v51);
            if ( (unsigned int)CContext::Failed((CContext *)v54, &Interface) )
            {
              if ( (bidGblFlags & 2) == 0 )
                goto LABEL_94;
              if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) == -1 )
              {
                v11 = 11229;
                v12 = 11498505;
                goto LABEL_12;
              }
              BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
              LODWORD(v39) = 11229;
              v10 = 11498505;
              goto LABEL_10;
            }
            v6 = v51;
          }
          if ( !v23 )
          {
            v25 = 1;
            v26 = 0;
            while ( 1 )
            {
              if ( v26 )
                goto LABEL_85;
              v27 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, SIZE_T, unsigned __int8 *, _QWORD, __int64, __int64 *, unsigned __int64 **))(*(_QWORD *)v6 + 72LL))(
                      v6,
                      0,
                      *(_QWORD *)(*((_QWORD *)this + 186) + 8LL),
                      v7,
                      v8,
                      v25,
                      1,
                      &v49,
                      &v52);
              if ( !v49 || v27 < 0 )
              {
                v58 = 1;
                v16 = 0;
                v40 = 0;
                v7 = *((_QWORD *)this + 100);
                v8 = (unsigned __int8 *)*((_QWORD *)this + 101);
                v53 = *((_QWORD *)this + 96);
                if ( !*((_DWORD *)this + 199) )
                {
                  v42 = v8;
                  v8 = (unsigned __int8 *)&v42;
                }
                goto LABEL_86;
              }
              if ( (int)CRecordset::GetBookmarkData(this, v44, v43, (struct CBookmarkData *)&pv) < 0 )
              {
                ++v25;
              }
              else
              {
                v26 = 1;
                v7 = v46;
                v28 = *((_BYTE *)this + 1256);
                if ( v28 == 2 )
                {
                  v29 = (unsigned int)pv;
LABEL_64:
                  v42 = (unsigned __int8 *)v29;
                  v8 = (unsigned __int8 *)&v42;
                  goto LABEL_67;
                }
                if ( v28 == 3 )
                {
                  v29 = (unsigned __int64)pv;
                  goto LABEL_64;
                }
                v8 = (unsigned __int8 *)pv;
              }
LABEL_67:
              ++v40;
              HIDWORD(v39) = 0;
              (*(void (__fastcall **)(__int64, __int64, unsigned __int64 *))(*(_QWORD *)v6 + 48LL))(v6, 1, &v43);
            }
          }
          if ( !v24 )
          {
            v30 = -1;
            v31 = 0;
            while ( 1 )
            {
              if ( v31 )
              {
LABEL_85:
                v16 = v40;
                goto LABEL_86;
              }
              v32 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, SIZE_T, unsigned __int8 *, _QWORD, __int64, __int64 *, unsigned __int64 **))(*(_QWORD *)v6 + 72LL))(
                      v6,
                      0,
                      *(_QWORD *)(*((_QWORD *)this + 186) + 8LL),
                      v7,
                      v8,
                      v30,
                      -1,
                      &v49,
                      &v52);
              if ( !v49 || v32 < 0 )
              {
                LOBYTE(IRowset) = 1;
                goto LABEL_85;
              }
              if ( (int)CRecordset::GetBookmarkData(this, v44, v43, (struct CBookmarkData *)&pv) < 0 )
              {
                --v30;
              }
              else
              {
                v31 = 1;
                v7 = v46;
                v33 = *((_BYTE *)this + 1256);
                if ( v33 == 2 )
                {
                  v34 = (unsigned int)pv;
LABEL_80:
                  v42 = (unsigned __int8 *)v34;
                  v8 = (unsigned __int8 *)&v42;
                  goto LABEL_83;
                }
                if ( v33 == 3 )
                {
                  v34 = (unsigned __int64)pv;
                  goto LABEL_80;
                }
                v8 = (unsigned __int8 *)pv;
              }
LABEL_83:
              --v40;
              HIDWORD(v39) = 0;
              (*(void (__fastcall **)(__int64, __int64, unsigned __int64 *))(*(_QWORD *)v6 + 48LL))(v6, 1, &v43);
            }
          }
        }
        v7 = 1;
        v8 = &byBmkFirst;
        v16 = 0;
        v40 = 0;
LABEL_86:
        SetErrorInfo(0, 0);
      }
LABEL_40:
      v21 = -v16;
      if ( !*((_BYTE *)this + 752) )
        v21 = v16;
      v22 = CoTaskMemAlloc(v7);
      if ( !(unsigned int)CContext::MemFailed((CContext *)v54, v22) )
      {
        memcpy_0(v22, v8, v7);
        CRecordGroup::FreeBookmark((CRecordset *)((char *)this + 736));
        *((_QWORD *)this + 100) = v7;
        *((_QWORD *)this + 101) = v22;
        *((_DWORD *)this + 199) = 1;
        *((_QWORD *)this + 96) = v53 + v21;
        *((_BYTE *)this + 833) = v21 != 0;
        goto LABEL_94;
      }
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_94;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) == -1 )
      {
        v11 = 11374;
        v12 = 11646985;
        goto LABEL_12;
      }
      BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
      LODWORD(v39) = 11374;
      v10 = 11646985;
LABEL_10:
      bidTraceW(off_18012A208[0], v10, L"<CRecordset::ProtectAnchor|ADO|ERR> %u#, line %d\n", BidObjectID, v39);
      goto LABEL_94;
    }
    IRowset = CRecordset::GetBookmarkData(this, v44, a3[i], (struct CBookmarkData *)&v41[24 * i]);
    if ( IRowset != -2147217885 )
    {
      if ( (unsigned int)CContext::Failed((CContext *)v54, &IRowset) )
        break;
    }
  }
  if ( (bidGblFlags & 2) != 0 )
  {
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
    {
      BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
      LODWORD(v39) = 11180;
      v10 = 11448329;
      goto LABEL_10;
    }
    v11 = 11180;
    v12 = 11448329;
LABEL_12:
    bidTraceW(off_18012A208[0], v12, L"<CRecordset::ProtectAnchor|ADO|ERR>  line %d\n", v11);
  }
LABEL_94:
  v13 = v41;
LABEL_95:
  if ( *((_BYTE *)this + 1256) == 1 && pv )
    CoTaskMemFree(pv);
  if ( v13 )
  {
    for ( j = 0; j < a2; ++j )
    {
      if ( *((_BYTE *)this + 1256) == 1 )
      {
        v36 = *(void **)&v13[24 * j];
        if ( v36 )
          CoTaskMemFree(v36);
      }
    }
    MpHeapFree(g_hHeapHandle, v13);
  }
LABEL_105:
  v37 = v56;
  ATL::CComPtr<IDBCreateSession>::~CComPtr<IDBCreateSession>(&v51);
  ATL::CComPtr<IDBCreateSession>::~CComPtr<IDBCreateSession>(&v44);
  CContext::~CContext((CContext *)v54);
  return v37;
}

```

## disassembly

```asm
0x1800b0a64  mov     [rsp-8+arg_8], rbx
0x1800b0a69  push    rbp
0x1800b0a6a  push    rsi
0x1800b0a6b  push    rdi
0x1800b0a6c  push    r12
0x1800b0a6e  push    r13
0x1800b0a70  push    r14
0x1800b0a72  push    r15
0x1800b0a74  lea     rbp, [rsp-27h]
0x1800b0a79  sub     rsp, 0F0h
0x1800b0a80  mov     r15, r8
0x1800b0a83  mov     r13, rdx
0x1800b0a86  mov     rdi, rcx
0x1800b0a89  mov     rax, rcx
0x1800b0a8c  lea     r10, [rcx+20h]
0x1800b0a90  neg     rax
0x1800b0a93  sbb     r9, r9
0x1800b0a96  and     r9, r10
0x1800b0a99  mov     [rbp+57h+var_40], r9
0x1800b0a9d  lea     rcx, [rbp+57h+var_60]; this
0x1800b0aa1  call    ?Init@CContext@@QEAAXXZ; CContext::Init(void)
0x1800b0aa6  nop
0x1800b0aa7  xor     r14d, r14d
0x1800b0aaa  mov     [rbp+57h+var_C0], r14
0x1800b0aae  mov     [rbp+57h+Buf1], r14
0x1800b0ab2  mov     eax, 0FFFFFF7Fh
0x1800b0ab7  mov     [rbp+57h+var_B8], rax
0x1800b0abb  lea     rax, [rbp+57h+var_B8]
0x1800b0abf  mov     [rbp+57h+var_70], rax
0x1800b0ac3  mov     [rbp+57h+var_88], r14
0x1800b0ac7  mov     [rbp+57h+var_A0], r14
0x1800b0acb  mov     [rbp+57h+var_98], r14
0x1800b0acf  mov     [rbp+57h+var_B0], r14
0x1800b0ad3  mov     ebx, r14d
0x1800b0ad6  mov     [rbp+57h+var_78], rbx
0x1800b0ada  mov     [rbp+57h+pv], r14
0x1800b0ade  cmp     [rdi+2C0h], r14d
0x1800b0ae5  jnz     loc_1800B11E5
0x1800b0aeb  lea     rcx, [rdi+138h]
0x1800b0af2  call    ?BoolCheck@?$CRsetOptionalInterface@UIRowsetLocate@@$1?IID_IRowsetLocate@@3U_GUID@@B@@QEAAHXZ; CRsetOptionalInterface<IRowsetLocate,&_GUID const IID_IRowsetLocate>::BoolCheck(void)
0x1800b0af7  test    eax, eax
0x1800b0af9  jz      loc_1800B11E5
0x1800b0aff  test    dword ptr [rdi+2B8h], 100h
0x1800b0b09  jz      loc_1800B11E5
0x1800b0b0f  mov     r12, [rdi+320h]
0x1800b0b16  mov     rsi, [rdi+328h]
0x1800b0b1d  mov     rcx, [rdi+300h]
0x1800b0b24  mov     [rbp+57h+var_68], rcx
0x1800b0b28  cmp     [rdi+31Ch], r14d
0x1800b0b2f  jnz     short loc_1800B0B39
0x1800b0b31  mov     [rbp+57h+var_C0], rsi
0x1800b0b35  lea     rsi, [rbp+57h+var_C0]
0x1800b0b39  lea     r14, ds:0[r13*2]
0x1800b0b41  add     r14, r13
0x1800b0b44  shl     r14, 3
0x1800b0b48  mov     r8, r14
0x1800b0b4b  mov     edx, 0A00000h
0x1800b0b50  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x1800b0b57  call    cs:__imp_MpHeapAlloc
0x1800b0b5e  nop     dword ptr [rax+rax+00h]
0x1800b0b63  mov     [rbp+57h+var_C8], rax
0x1800b0b67  mov     rdx, rax; void *
0x1800b0b6a  lea     rcx, [rbp+57h+var_60]; this
0x1800b0b6e  call    ?MemFailed@CContext@@QEAAHPEAX@Z; CContext::MemFailed(void *)
0x1800b0b73  test    eax, eax
0x1800b0b75  jz      short loc_1800B0BEB
0x1800b0b77  test    byte ptr cs:_bidGblFlags, 2
0x1800b0b7e  jz      loc_1800B1177
0x1800b0b84  lea     rbx, [rdi+618h]
0x1800b0b8b  mov     rcx, rbx; this
0x1800b0b8e  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b0b93  cmp     eax, 0FFFFFFFFh
0x1800b0b96  jz      short loc_1800B0BC8
0x1800b0b98  mov     rcx, rbx; this
0x1800b0b9b  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b0ba0  mov     dword ptr [rsp+120h+var_100], 2B9Ch
0x1800b0ba8  mov     edx, 0AE7009h
0x1800b0bad  lea     r8, aCrecordsetProt; "<CRecordset::ProtectAnchor|ADO|ERR> %u#"...
0x1800b0bb4  mov     r9d, eax
0x1800b0bb7  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800b0bbe  call    _bidTraceW
0x1800b0bc3  jmp     loc_1800B1177
0x1800b0bc8  mov     r9d, 2B9Ch
0x1800b0bce  mov     edx, 0AE7009h
0x1800b0bd3  lea     r8, aCrecordsetProt_0; "<CRecordset::ProtectAnchor|ADO|ERR>  li"...
0x1800b0bda  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800b0be1  call    _bidTraceW
0x1800b0be6  jmp     loc_1800B1177
0x1800b0beb  mov     r8, r14; Size
0x1800b0bee  xor     edx, edx; Val
0x1800b0bf0  mov     r14, [rbp+57h+var_C8]
0x1800b0bf4  mov     rcx, r14; void *
0x1800b0bf7  call    memset_0
0x1800b0bfc  test    r13, r13
0x1800b0bff  jz      loc_1800B0C99
0x1800b0c05  lea     rdx, [rbp+57h+var_B0]; struct IRowset **
0x1800b0c09  mov     rcx, rdi; this
0x1800b0c0c  call    ?GetIRowset@CRecordset@@QEAAJPEAPEAUIRowset@@@Z; CRecordset::GetIRowset(IRowset * *)
0x1800b0c11  mov     [rbp+57h+arg_0], eax
0x1800b0c14  lea     rdx, [rbp+57h+arg_0]; int *
0x1800b0c18  lea     rcx, [rbp+57h+var_60]; this
0x1800b0c1c  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800b0c21  test    eax, eax
0x1800b0c23  jz      short loc_1800B0C99
0x1800b0c25  test    byte ptr cs:_bidGblFlags, 2
0x1800b0c2c  jz      loc_1800B117B
0x1800b0c32  lea     rbx, [rdi+618h]
0x1800b0c39  mov     rcx, rbx; this
0x1800b0c3c  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b0c41  cmp     eax, 0FFFFFFFFh
0x1800b0c44  jz      short loc_1800B0C76
0x1800b0c46  mov     rcx, rbx; this
0x1800b0c49  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b0c4e  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800b0c55  mov     dword ptr [rsp+120h+var_100], 2BA1h
0x1800b0c5d  mov     r9d, eax
0x1800b0c60  lea     r8, aCrecordsetProt; "<CRecordset::ProtectAnchor|ADO|ERR> %u#"...
0x1800b0c67  mov     edx, 0AE8409h
0x1800b0c6c  call    _bidTraceW
0x1800b0c71  jmp     loc_1800B117B
0x1800b0c76  mov     r9d, 2BA1h
0x1800b0c7c  lea     r8, aCrecordsetProt_0; "<CRecordset::ProtectAnchor|ADO|ERR>  li"...
0x1800b0c83  mov     edx, 0AE8409h
0x1800b0c88  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800b0c8f  call    _bidTraceW
0x1800b0c94  jmp     loc_1800B117B
0x1800b0c99  xor     r14d, r14d
0x1800b0c9c  cmp     r14, r13
0x1800b0c9f  jnb     loc_1800B0D2C
0x1800b0ca5  lea     rax, [r14+r14*2]
0x1800b0ca9  mov     rcx, [rbp+57h+var_C8]
0x1800b0cad  lea     r9, [rcx+rax*8]; struct CBookmarkData *
0x1800b0cb1  mov     r8, [r15+r14*8]; unsigned __int64
0x1800b0cb5  mov     rdx, [rbp+57h+var_B0]; struct IRowset *
0x1800b0cb9  mov     rcx, rdi; this
0x1800b0cbc  call    ?GetBookmarkData@CRecordset@@AEAAJPEAUIRowset@@_KAEAVCBookmarkData@@@Z; CRecordset::GetBookmarkData(IRowset *,unsigned __int64,CBookmarkData &)
0x1800b0cc1  mov     [rbp+57h+arg_0], eax
0x1800b0cc4  cmp     eax, 80040E23h
0x1800b0cc9  jz      short loc_1800B0CDC
0x1800b0ccb  lea     rdx, [rbp+57h+arg_0]; int *
0x1800b0ccf  lea     rcx, [rbp+57h+var_60]; this
0x1800b0cd3  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800b0cd8  test    eax, eax
0x1800b0cda  jnz     short loc_1800B0CE1
0x1800b0cdc  inc     r14
0x1800b0cdf  jmp     short loc_1800B0C9C
0x1800b0ce1  test    byte ptr cs:_bidGblFlags, 2
0x1800b0ce8  jz      loc_1800B1177
0x1800b0cee  lea     rbx, [rdi+618h]
0x1800b0cf5  mov     rcx, rbx; this
0x1800b0cf8  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b0cfd  cmp     eax, 0FFFFFFFFh
0x1800b0d00  jz      short loc_1800B0D1C
0x1800b0d02  mov     rcx, rbx; this
0x1800b0d05  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b0d0a  mov     dword ptr [rsp+120h+var_100], 2BACh
0x1800b0d12  mov     edx, 0AEB009h
0x1800b0d17  jmp     loc_1800B0BAD
0x1800b0d1c  mov     r9d, 2BACh
0x1800b0d22  mov     edx, 0AEB009h
0x1800b0d27  jmp     loc_1800B0BD3
0x1800b0d2c  xor     r15d, r15d
0x1800b0d2f  mov     [rbp+57h+var_D0], r15d
0x1800b0d33  xor     r14b, r14b
0x1800b0d36  mov     byte ptr [rbp+57h+arg_0], r14b
0x1800b0d3a  mov     [rbp+57h+arg_18], r14b
0x1800b0d3e  cmp     r12, 1
0x1800b0d42  jnz     short loc_1800B0D4E
0x1800b0d44  mov     al, cs:?byBmkFirst@@3EA; uchar byBmkFirst
0x1800b0d4a  cmp     [rsi], al
0x1800b0d4c  jz      short loc_1800B0DA3
0x1800b0d4e  test    r13, r13
0x1800b0d51  jz      short loc_1800B0DA3
0x1800b0d53  xor     r14d, r14d
0x1800b0d56  mov     r15b, [rdi+4E8h]
0x1800b0d5d  lea     rax, [r14+r14*2]
0x1800b0d61  mov     rcx, [rbp+57h+var_C8]
0x1800b0d65  mov     r8, [rcx+rax*8+8]; Size
0x1800b0d6a  mov     rcx, [rcx+rax*8]
0x1800b0d6e  cmp     r15b, 2
0x1800b0d72  jz      short loc_1800B0D7A
0x1800b0d74  cmp     r15b, 3
0x1800b0d78  jnz     short loc_1800B0D82
0x1800b0d7a  mov     [rbp+57h+Buf1], rcx
0x1800b0d7e  lea     rcx, [rbp+57h+Buf1]; Buf1
0x1800b0d82  cmp     r8, r12
0x1800b0d85  jnz     short loc_1800B0D97
0x1800b0d87  mov     rdx, rsi; Buf2
0x1800b0d8a  call    memcmp_0
0x1800b0d8f  test    eax, eax
0x1800b0d91  jz      loc_1800B0E19
0x1800b0d97  inc     r14
0x1800b0d9a  cmp     r14, r13
0x1800b0d9d  jb      short loc_1800B0D5D
0x1800b0d9f  mov     r15d, [rbp+57h+var_D0]
0x1800b0da3  mov     r14d, r15d
0x1800b0da6  neg     r14d
0x1800b0da9  cmp     byte ptr [rdi+2F0h], 0
0x1800b0db0  cmovz   r14d, r15d
0x1800b0db4  mov     rcx, r12; cb
0x1800b0db7  call    cs:__imp_CoTaskMemAlloc
0x1800b0dbe  nop     dword ptr [rax+rax+00h]
0x1800b0dc3  mov     r15, rax
0x1800b0dc6  mov     rdx, rax; void *
0x1800b0dc9  lea     rcx, [rbp+57h+var_60]; this
0x1800b0dcd  call    ?MemFailed@CContext@@QEAAHPEAX@Z; CContext::MemFailed(void *)
0x1800b0dd2  test    eax, eax
0x1800b0dd4  jz      loc_1800B1137
0x1800b0dda  test    byte ptr cs:_bidGblFlags, 2
0x1800b0de1  jz      loc_1800B1177
0x1800b0de7  lea     rbx, [rdi+618h]
0x1800b0dee  mov     rcx, rbx; this
0x1800b0df1  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b0df6  cmp     eax, 0FFFFFFFFh
0x1800b0df9  jz      loc_1800B1127
0x1800b0dff  mov     rcx, rbx; this
0x1800b0e02  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b0e07  mov     dword ptr [rsp+120h+var_100], 2C6Eh
0x1800b0e0f  mov     edx, 0B1B809h
0x1800b0e14  jmp     loc_1800B0BAD
0x1800b0e19  cmp     r15b, 1
0x1800b0e1d  jnz     short loc_1800B0E3C
0x1800b0e1f  mov     rcx, [rbp+57h+pv]; pv
0x1800b0e23  test    rcx, rcx
0x1800b0e26  jz      short loc_1800B0E3C
0x1800b0e28  call    cs:__imp_CoTaskMemFree
0x1800b0e2f  nop     dword ptr [rax+rax+00h]
0x1800b0e34  mov     [rbp+57h+pv], 0
0x1800b0e3c  mov     r15b, [rbp+57h+arg_18]
0x1800b0e40  mov     r14b, byte ptr [rbp+57h+arg_0]
0x1800b0e44  test    r15b, r15b
0x1800b0e47  jz      short loc_1800B0E52
0x1800b0e49  test    r14b, r14b
0x1800b0e4c  jnz     loc_1800B10C6
0x1800b0e52  test    rbx, rbx
0x1800b0e55  jnz     short loc_1800B0E83
0x1800b0e57  lea     rdx, [rbp+57h+var_78]
0x1800b0e5b  lea     rcx, [rdi+138h]
0x1800b0e62  call    ?GetInterface@?$CRsetOptionalInterface@UIRowsetLocate@@$1?IID_IRowsetLocate@@3U_GUID@@B@@QEAAJPEAPEAUIRowsetLocate@@@Z; CRsetOptionalInterface<IRowsetLocate,&_GUID const IID_IRowsetLocate>::GetInterface(IRowsetLocate * *)
0x1800b0e67  mov     [rbp+57h+var_80], eax
0x1800b0e6a  lea     rdx, [rbp+57h+var_80]; int *
0x1800b0e6e  lea     rcx, [rbp+57h+var_60]; this
0x1800b0e72  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800b0e77  test    eax, eax
0x1800b0e79  jnz     loc_1800B10DC
0x1800b0e7f  mov     rbx, [rbp+57h+var_78]
0x1800b0e83  test    r15b, r15b
0x1800b0e86  jnz     loc_1800B0FB6
0x1800b0e8c  mov     r14d, 1
0x1800b0e92  xor     r15d, r15d
0x1800b0e95  test    r15d, r15d
0x1800b0e98  jnz     loc_1800B10AD
0x1800b0e9e  mov     rax, [rbx]
0x1800b0ea1  movsxd  rcx, r14d
0x1800b0ea4  mov     r8, [rdi+5D0h]
0x1800b0eab  lea     rdx, [rbp+57h+var_70]
0x1800b0eaf  mov     [rsp+120h+var_E0], rdx
0x1800b0eb4  lea     rdx, [rbp+57h+var_88]
0x1800b0eb8  mov     [rsp+120h+var_E8], rdx
0x1800b0ebd  mov     [rsp+120h+var_F0], 1
0x1800b0ec6  mov     [rsp+120h+var_F8], rcx
0x1800b0ecb  mov     [rsp+120h+var_100], rsi
0x1800b0ed0  mov     r9, r12
0x1800b0ed3  mov     r8, [r8+8]
0x1800b0ed7  xor     edx, edx
0x1800b0ed9  mov     rcx, rbx
0x1800b0edc  mov     rax, [rax+48h]
0x1800b0ee0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0ee5  cmp     [rbp+57h+var_88], 0
0x1800b0eea  jz      loc_1800B0F78
0x1800b0ef0  test    eax, eax
0x1800b0ef2  js      loc_1800B0F78
0x1800b0ef8  lea     r9, [rbp+57h+pv]; struct CBookmarkData *
0x1800b0efc  mov     r8, [rbp+57h+var_B8]; unsigned __int64
0x1800b0f00  mov     rdx, [rbp+57h+var_B0]; struct IRowset *
0x1800b0f04  mov     rcx, rdi; this
0x1800b0f07  call    ?GetBookmarkData@CRecordset@@AEAAJPEAUIRowset@@_KAEAVCBookmarkData@@@Z; CRecordset::GetBookmarkData(IRowset *,unsigned __int64,CBookmarkData &)
0x1800b0f0c  test    eax, eax
0x1800b0f0e  js      short loc_1800B0F41
0x1800b0f10  mov     r15d, 1
0x1800b0f16  mov     r12, [rbp+57h+var_A0]
0x1800b0f1a  mov     al, [rdi+4E8h]
0x1800b0f20  cmp     al, 2
0x1800b0f22  jnz     short loc_1800B0F29
0x1800b0f24  mov     eax, dword ptr [rbp+57h+pv]
0x1800b0f27  jmp     short loc_1800B0F31
0x1800b0f29  cmp     al, 3
0x1800b0f2b  jnz     short loc_1800B0F3B
0x1800b0f2d  mov     rax, [rbp+57h+pv]
0x1800b0f31  mov     [rbp+57h+var_C0], rax
0x1800b0f35  lea     rsi, [rbp+57h+var_C0]
0x1800b0f39  jmp     short loc_1800B0F44
0x1800b0f3b  mov     rsi, [rbp+57h+pv]
0x1800b0f3f  jmp     short loc_1800B0F44
0x1800b0f41  inc     r14d
0x1800b0f44  inc     [rbp+57h+var_D0]
0x1800b0f47  mov     rax, [rbx]
0x1800b0f4a  mov     [rsp+120h+var_F8], 0
0x1800b0f53  mov     [rsp+120h+var_100], 0
0x1800b0f5c  xor     r9d, r9d
  ... truncated ...
```
