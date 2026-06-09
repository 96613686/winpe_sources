# CRecordset::SaveToFile(ushort *,tagDBPROP *,ulong)

- ea: `0x18005dc90`
- end: `0x18005e594`
- name: `?SaveToFile@CRecordset@@AEAAJPEAGPEAUtagDBPROP@@K@Z`
- size: `2308`
- prototype: `__int64 __fastcall(CRecordset *__hidden this, unsigned __int16 *, struct tagDBPROP *, unsigned int)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800b2200`

## callees

- `0x180001514`
- `0x1800465a4`
- `0x18005dc90`
- `0x18005e59c`
- `0x18005e848`
- `0x180063ed8`
- `0x18006a22c`
- `0x1800a8268`
- `0x1800b28b0`
- `0x1800c8f34`
- `0x1800ca894`
- `0x1800caa28`
- `0x1800cc16c`
- `0x1800cc1bc`
- `0x1800cc30c`
- `0x1800cdb20`
- `0x1800cdbe0`
- `0x1800d0010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18005dd3d`
- `msvcrt!_wcsnicmp` at `0x18005dd5d`
- `msvcrt!_wcsnicmp` at `0x18005dd3d`
- `msvcrt!_wcsnicmp` at `0x18005dd5d`
- `msvcrt!_wcsicmp` at `0x18005df1d`
- `msvcrt!_wcsicmp` at `0x18005df1d`
- `msvcrt!_get_osfhandle` at `0x18005e3e5`
- `msvcrt!_get_osfhandle` at `0x18005e3e5`
- `msvcrt!_fileno` at `0x18005e3d7`
- `msvcrt!_fileno` at `0x18005e3d7`
- `KERNEL32!GetFileType` at `0x18005e3fe`
- `KERNEL32!GetFileType` at `0x18005e3fe`
- `KERNEL32!GetTempFileNameW` at `0x18005e242`
- `KERNEL32!GetTempFileNameW` at `0x18005e242`
- `KERNEL32!GetFullPathNameW` at `0x18005e12a`
- `KERNEL32!GetFullPathNameW` at `0x18005e12a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRecordset::SaveToFile(CRecordset *this, unsigned __int16 *a2, struct tagDBPROP *a3)
{
  unsigned __int16 *v4; // r15
  FILE **v6; // r14
  const wchar_t *v7; // rbx
  char *v8; // rbx
  BOOL v9; // esi
  unsigned __int16 *v10; // rdx
  int v11; // ebx
  __int64 BidObjectID; // r9
  unsigned int v13; // eax
  const wchar_t **v14; // rsi
  int IsEmpty; // eax
  CFileStream *v16; // rcx
  const wchar_t *v17; // rdx
  unsigned __int16 *v18; // rdx
  unsigned __int16 *v19; // r8
  unsigned int v20; // eax
  __int64 v21; // rdx
  __int64 v22; // rdx
  unsigned __int16 *v23; // rdx
  char v24; // r12
  const WCHAR *v25; // rcx
  DWORD FullPathNameW; // eax
  __int64 v27; // r9
  unsigned __int64 v28; // rcx
  unsigned __int16 *v29; // r8
  int v30; // eax
  void *osfhandle; // rax
  unsigned __int16 *v32; // r8
  WCHAR *v33; // rdx
  int v35; // [rsp+20h] [rbp-E0h]
  int v36; // [rsp+20h] [rbp-E0h]
  int v37; // [rsp+28h] [rbp-D8h]
  int v38; // [rsp+30h] [rbp-D0h] BYREF
  struct IUnknown *v39; // [rsp+38h] [rbp-C8h] BYREF
  struct IUnknown *v40; // [rsp+40h] [rbp-C0h] BYREF
  LPWSTR FilePart; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v42; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Buffer[1024]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR TempFileName[1024]; // [rsp+860h] [rbp+760h] BYREF

  v4 = a2;
  v42 = 0;
  FilePart = 0;
  v6 = 0;
  v39 = 0;
  v38 = 0;
  v40 = 0;
  if ( a2 )
  {
    v7 = a2;
  }
  else
  {
    v8 = (char *)this + 1264;
    if ( (unsigned int)CSysString::IsEmpty((CRecordset *)((char *)this + 1264)) )
      goto LABEL_21;
    v7 = (v8[8] & 4) != 0 ? *(const wchar_t **)v8 : 0LL;
    if ( !v7 )
      goto LABEL_21;
  }
  v9 = _wcsnicmp(v7, L"http://", 7u) && _wcsnicmp(v7, L"https://", 8u);
  (*(void (__fastcall **)(char *, GUID *, struct IUnknown **))(*((_QWORD *)this + 31) + 32LL))(
    (char *)this + 248,
    &IID_IUnknown,
    &v40);
  if ( (*((_BYTE *)this + 280) & 3) != 0 && !*((_QWORD *)this + 34)
    || (v10 = (unsigned __int16 *)*((_QWORD *)this + 34)) != 0
    && (int)SecurityCheck(v7, v10) < 0
    && (unsigned int)SecurityDialog(v40, *((unsigned __int16 **)this + 34), v9) )
  {
    v11 = -2146824572;
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) == -1 )
      {
        bidTraceW(off_18012A208[0], 1500169, L"<CRecordset::SaveToFile|ADO|ERR>  line %d\n", 1465);
      }
      else
      {
        BidObjectID = (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
        bidTraceW(off_18012A208[0], 1500169, L"<CRecordset::SaveToFile|ADO|ERR> %u#, line %d\n", BidObjectID, 1465);
      }
    }
    goto LABEL_124;
  }
LABEL_21:
  v11 = ATL::CComObject<CFileStream>::CreateInstance(&v39);
  if ( v11 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) == -1 )
      {
        bidTraceW(
          off_18012A208[0],
          1505289,
          L"<CRecordset::SaveToFile|ADO|ERR> 0x%08x{HRESULT} line %d\n",
          (unsigned int)v11,
          1470);
      }
      else
      {
        v13 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
        bidTraceW(
          off_18012A208[0],
          1505289,
          L"<CRecordset::SaveToFile|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
          v13,
          v11,
          1470);
      }
    }
    v6 = (FILE **)v39;
    goto LABEL_124;
  }
  v6 = (FILE **)v39;
  ((void (__fastcall *)(struct IUnknown *))v39->lpVtbl->AddRef)(v39);
  v14 = (const wchar_t **)((char *)this + 1264);
  IsEmpty = CSysString::IsEmpty((CRecordset *)((char *)this + 1264));
  if ( v4 )
  {
    if ( IsEmpty || ((*((_BYTE *)this + 1272) & 4) == 0 ? (v17 = 0) : (v17 = *v14), _wcsicmp(v4, v17)) )
    {
      v11 = CFileStream::Exists(v16, v4, &v38);
      if ( v11 < 0 )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_124;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
        {
          v20 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
          v37 = 1483;
          v21 = 1518601;
          goto LABEL_40;
        }
        v36 = 1483;
        v22 = 1518601;
        goto LABEL_122;
      }
      if ( !v38 )
      {
        v11 = -2147286960;
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_124;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
        {
          v20 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
          v37 = 1487;
          v21 = 1522697;
          goto LABEL_40;
        }
        v36 = 1487;
        v22 = 1522697;
        goto LABEL_122;
      }
      goto LABEL_96;
    }
    if ( (*((_BYTE *)this + 1272) & 4) != 0 )
      v18 = (unsigned __int16 *)*v14;
    else
      v18 = 0;
    v11 = CFileStream::Exists(v16, v18, &v38);
    if ( v11 < 0 )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_124;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
      {
        v20 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
        v37 = 1492;
        v21 = 1527817;
LABEL_40:
        v35 = v11;
LABEL_41:
        bidTraceW(
          off_18012A208[0],
          v21,
          L"<CRecordset::SaveToFile|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
          v20,
          v35,
          v37);
        goto LABEL_124;
      }
      v36 = 1492;
      v22 = 1527817;
      goto LABEL_122;
    }
  }
  else
  {
    if ( IsEmpty )
    {
      v11 = -2147286788;
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_124;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
      {
        v20 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
        v37 = 1514;
        v21 = 1550345;
        goto LABEL_40;
      }
      v36 = 1514;
      v22 = 1550345;
LABEL_122:
      v27 = (unsigned int)v11;
      goto LABEL_123;
    }
    if ( (*((_BYTE *)this + 1272) & 4) != 0 )
      v23 = (unsigned __int16 *)*v14;
    else
      v23 = 0;
    v11 = CFileStream::Exists(v16, v23, &v38);
    if ( v11 < 0 )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_124;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
      {
        v20 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
        v37 = 1509;
        v21 = 1545225;
        goto LABEL_40;
      }
      v36 = 1509;
      v22 = 1545225;
      goto LABEL_122;
    }
  }
  if ( !v38 )
  {
    v24 = 1;
    if ( (*((_BYTE *)this + 1272) & 4) != 0 )
      v25 = *v14;
    else
      v25 = 0;
    FullPathNameW = GetFullPathNameW(v25, 0x3F4u, Buffer, &FilePart);
    if ( FullPathNameW < 0x3F4 )
    {
      if ( FullPathNameW )
      {
        if ( FilePart > Buffer )
        {
          v28 = FilePart - Buffer;
          if ( v28 >= 1024 )
            _report_rangecheckfailure();
          Buffer[v28] = 0;
          if ( !GetTempFileNameW(Buffer, L"dag", 0, TempFileName) )
          {
            v11 = -2147286781;
            if ( (bidGblFlags & 2) == 0 )
              goto LABEL_124;
            if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
            {
              v20 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
              v37 = 1543;
              v21 = 1580041;
              goto LABEL_40;
            }
            v36 = 1543;
            v22 = 1580041;
            goto LABEL_122;
          }
          v11 = CFileStream::Open((CFileStream *)v6, TempFileName, v29);
          if ( v11 < 0 )
          {
            if ( (bidGblFlags & 2) == 0 )
              goto LABEL_124;
            if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
            {
              v20 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
              v37 = 1545;
              v21 = 1582089;
              goto LABEL_40;
            }
            v36 = 1545;
            v22 = 1582089;
            goto LABEL_122;
          }
          goto LABEL_102;
        }
        v11 = -2146825286;
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_124;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
        {
          v20 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
          v37 = 1538;
          v35 = -2146825286;
          v21 = 1574921;
          goto LABEL_41;
        }
        v36 = 1538;
        v27 = 2148142010LL;
        v22 = 1574921;
      }
      else
      {
        v11 = -2146825286;
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_124;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
        {
          v20 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
          v37 = 1534;
          v35 = -2146825286;
          v21 = 1570825;
          goto LABEL_41;
        }
        v36 = 1534;
        v27 = 2148142010LL;
        v22 = 1570825;
      }
    }
    else
    {
      v11 = -2146825286;
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_124;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
      {
        v20 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
        v37 = 1532;
        v35 = -2146825286;
        v21 = 1568777;
        goto LABEL_41;
      }
      v36 = 1532;
      v27 = 2148142010LL;
      v22 = 1568777;
    }
LABEL_123:
    bidTraceW(off_18012A208[0], v22, L"<CRecordset::SaveToFile|ADO|ERR> 0x%08x{HRESULT} line %d\n", v27, v36);
    goto LABEL_124;
  }
  if ( (*((_BYTE *)this + 1272) & 4) != 0 )
    v4 = (unsigned __int16 *)*v14;
  else
    v4 = 0;
LABEL_96:
  v11 = CFileStream::Open((CFileStream *)v6, v4, v19);
  if ( v11 < 0 )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_124;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
    {
      v20 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
      v37 = 1548;
      v21 = 1585161;
      goto LABEL_40;
    }
    v36 = 1548;
    v22 = 1585161;
    goto LABEL_122;
  }
  v24 = 0;
LABEL_102:
  v30 = _fileno(v6[5]);
  osfhandle = (void *)_get_osfhandle(v30);
  if ( osfhandle == (void *)-1LL || GetFileType(osfhandle) != 1 )
  {
    v11 = -2146825069;
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_124;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
    {
      v20 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
      v37 = 1553;
      v21 = 1590281;
      goto LABEL_40;
    }
    v36 = 1553;
    v22 = 1590281;
    goto LABEL_122;
  }
  v11 = CRecordset::SaveToStream(this, (struct IUnknown *)v6, a3, 3u);
  if ( v11 < 0 )
  {
    CFileStream::Close((CFileStream *)v6);
    if ( v24 )
      v33 = TempFileName;
    else
      v33 = v4;
    CFileStream::Delete((CFileStream *)v6, v33);
  }
  else if ( v24 )
  {
    CFileStream::Close((CFileStream *)v6);
    if ( (*((_BYTE *)this + 1272) & 4) != 0 )
      v32 = (unsigned __int16 *)*v14;
    else
      v32 = 0;
    v11 = CFileStream::Move((CFileStream *)v6, TempFileName, v32);
  }
LABEL_124:
  if ( v40 )
    ((void (__fastcall *)(struct IUnknown *))v40->lpVtbl->Release)(v40);
  if ( v6 )
    ((void (__fastcall *)(FILE **))(*v6)->_base)(v6);
  ATL::CComPtr<IDBCreateSession>::~CComPtr<IDBCreateSession>(&v42);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18005dc90  mov     [rsp-8+arg_18], rbx
0x18005dc95  push    rbp
0x18005dc96  push    rsi
0x18005dc97  push    rdi
0x18005dc98  push    r12
0x18005dc9a  push    r13
0x18005dc9c  push    r14
0x18005dc9e  push    r15
0x18005dca0  lea     rbp, [rsp-0F70h]
0x18005dca8  mov     eax, 1070h
0x18005dcad  call    _alloca_probe
0x18005dcb2  sub     rsp, rax
0x18005dcb5  mov     rax, cs:__security_cookie
0x18005dcbc  xor     rax, rsp
0x18005dcbf  mov     [rbp+0FA0h+var_40], rax
0x18005dcc6  mov     r13, r8
0x18005dcc9  mov     r15, rdx
0x18005dccc  mov     rdi, rcx
0x18005dccf  mov     [rsp+10A0h+var_1050], 0
0x18005dcd8  mov     [rsp+10A0h+FilePart], 0
0x18005dce1  xor     r14d, r14d
0x18005dce4  mov     [rsp+10A0h+var_1068], r14
0x18005dce9  mov     [rsp+10A0h+var_1070], r14d
0x18005dcee  mov     [rsp+10A0h+var_1060], r14
0x18005dcf3  mov     r12b, 4
0x18005dcf6  test    rdx, rdx
0x18005dcf9  jz      short loc_18005DD00
0x18005dcfb  mov     rbx, rdx
0x18005dcfe  jmp     short loc_18005DD2D
0x18005dd00  lea     rbx, [rcx+4F0h]
0x18005dd07  mov     rcx, rbx; this
0x18005dd0a  call    ?IsEmpty@CSysString@@QEBAHXZ; CSysString::IsEmpty(void)
0x18005dd0f  test    eax, eax
0x18005dd11  jnz     loc_18005DE4D
0x18005dd17  test    [rbx+8], r12b
0x18005dd1b  jz      short loc_18005DD22
0x18005dd1d  mov     rbx, [rbx]
0x18005dd20  jmp     short loc_18005DD24
0x18005dd22  xor     ebx, ebx
0x18005dd24  test    rbx, rbx
0x18005dd27  jz      loc_18005DE4D
0x18005dd2d  mov     r8d, 7; MaxCount
0x18005dd33  lea     rdx, aHttp; "http://"
0x18005dd3a  mov     rcx, rbx; String1
0x18005dd3d  call    cs:__imp__wcsnicmp
0x18005dd44  nop     dword ptr [rax+rax+00h]
0x18005dd49  test    eax, eax
0x18005dd4b  jz      short loc_18005DD74
0x18005dd4d  mov     r8d, 8; MaxCount
0x18005dd53  lea     rdx, aHttps; "https://"
0x18005dd5a  mov     rcx, rbx; String1
0x18005dd5d  call    cs:__imp__wcsnicmp
0x18005dd64  nop     dword ptr [rax+rax+00h]
0x18005dd69  test    eax, eax
0x18005dd6b  jz      short loc_18005DD74
0x18005dd6d  mov     esi, 1
0x18005dd72  jmp     short loc_18005DD76
0x18005dd74  xor     esi, esi
0x18005dd76  lea     rcx, [rdi+0F8h]
0x18005dd7d  mov     rax, [rcx]
0x18005dd80  lea     r8, [rsp+10A0h+var_1060]
0x18005dd85  lea     rdx, IID_IUnknown
0x18005dd8c  mov     rax, [rax+20h]
0x18005dd90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005dd95  test    byte ptr [rdi+118h], 3
0x18005dd9c  jz      short loc_18005DDA7
0x18005dd9e  cmp     [rdi+110h], r14
0x18005dda5  jz      short loc_18005DDDF
0x18005dda7  mov     rdx, [rdi+110h]; unsigned __int16 *
0x18005ddae  test    rdx, rdx
0x18005ddb1  jz      loc_18005DE4D
0x18005ddb7  mov     rcx, rbx; unsigned __int16 *
0x18005ddba  call    ?SecurityCheck@@YAJPEBGPEAG@Z; SecurityCheck(ushort const *,ushort *)
0x18005ddbf  test    eax, eax
0x18005ddc1  jns     loc_18005DE4D
0x18005ddc7  mov     r8d, esi; int
0x18005ddca  mov     rdx, [rdi+110h]; unsigned __int16 *
0x18005ddd1  mov     rcx, [rsp+10A0h+var_1060]; struct IUnknown *
0x18005ddd6  call    ?SecurityDialog@@YAJPEAUIUnknown@@PEAGH@Z; SecurityDialog(IUnknown *,ushort *,int)
0x18005dddb  test    eax, eax
0x18005dddd  jz      short loc_18005DE4D
0x18005dddf  mov     ebx, 800A0E84h
0x18005dde4  test    byte ptr cs:_bidGblFlags, 2
0x18005ddeb  jz      loc_18005E532
0x18005ddf1  lea     rcx, [rdi+618h]; this
0x18005ddf8  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18005ddfd  cmp     eax, 0FFFFFFFFh
0x18005de00  jz      short loc_18005DE2A
0x18005de02  lea     rcx, [rdi+618h]; this
0x18005de09  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18005de0e  mov     [rsp+10A0h+var_1080], 5B9h
0x18005de16  mov     r9d, eax
0x18005de19  lea     r8, aCrecordsetSave_0; "<CRecordset::SaveToFile|ADO|ERR> %u#, l"...
0x18005de20  mov     edx, 16E409h
0x18005de25  jmp     loc_18005E526
0x18005de2a  mov     r9d, 5B9h
0x18005de30  lea     r8, aCrecordsetSave_5; "<CRecordset::SaveToFile|ADO|ERR>  line "...
0x18005de37  mov     edx, 16E409h
0x18005de3c  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18005de43  call    _bidTraceW
0x18005de48  jmp     loc_18005E532
0x18005de4d  lea     rcx, [rsp+10A0h+var_1068]
0x18005de52  call    ?CreateInstance@?$CComObject@VCFileStream@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CFileStream>::CreateInstance(ATL::CComObject<CFileStream> * *)
0x18005de57  mov     ebx, eax
0x18005de59  test    eax, eax
0x18005de5b  jns     short loc_18005DED9
0x18005de5d  test    byte ptr cs:_bidGblFlags, 2
0x18005de64  jz      short loc_18005DECF
0x18005de66  lea     rcx, [rdi+618h]; this
0x18005de6d  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18005de72  cmp     eax, 0FFFFFFFFh
0x18005de75  jz      short loc_18005DEAC
0x18005de77  lea     rcx, [rdi+618h]; this
0x18005de7e  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18005de83  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18005de8a  mov     [rsp+10A0h+var_1078], 5BEh
0x18005de92  mov     [rsp+10A0h+var_1080], ebx
0x18005de96  mov     r9d, eax
0x18005de99  lea     r8, aCrecordsetSave; "<CRecordset::SaveToFile|ADO|ERR> %u#,0x"...
0x18005dea0  mov     edx, 16F809h
0x18005dea5  call    _bidTraceW
0x18005deaa  jmp     short loc_18005DECF
0x18005deac  mov     [rsp+10A0h+var_1080], 5BEh
0x18005deb4  mov     r9d, ebx
0x18005deb7  lea     r8, aCrecordsetSave_7; "<CRecordset::SaveToFile|ADO|ERR> 0x%08x"...
0x18005debe  mov     edx, 16F809h
0x18005dec3  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18005deca  call    _bidTraceW
0x18005decf  mov     r14, [rsp+10A0h+var_1068]
0x18005ded4  jmp     loc_18005E532
0x18005ded9  mov     r14, [rsp+10A0h+var_1068]
0x18005dede  mov     rax, [r14]
0x18005dee1  mov     rcx, r14
0x18005dee4  mov     rax, [rax+8]
0x18005dee8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005deed  lea     rsi, [rdi+4F0h]
0x18005def4  mov     rcx, rsi; this
0x18005def7  call    ?IsEmpty@CSysString@@QEBAHXZ; CSysString::IsEmpty(void)
0x18005defc  test    r15, r15
0x18005deff  jz      loc_18005E092
0x18005df05  test    eax, eax
0x18005df07  jnz     loc_18005DFD3
0x18005df0d  test    [rsi+8], r12b
0x18005df11  jz      short loc_18005DF18
0x18005df13  mov     rdx, [rsi]
0x18005df16  jmp     short loc_18005DF1A
0x18005df18  xor     edx, edx; String2
0x18005df1a  mov     rcx, r15; String1
0x18005df1d  call    cs:__imp__wcsicmp
0x18005df24  nop     dword ptr [rax+rax+00h]
0x18005df29  test    eax, eax
0x18005df2b  jnz     loc_18005DFD3
0x18005df31  test    [rsi+8], r12b
0x18005df35  jz      short loc_18005DF3C
0x18005df37  mov     rdx, [rsi]
0x18005df3a  jmp     short loc_18005DF3E
0x18005df3c  xor     edx, edx; unsigned __int16 *
0x18005df3e  lea     r8, [rsp+10A0h+var_1070]; int *
0x18005df43  call    ?Exists@CFileStream@@QEAAJPEAGPEAH@Z; CFileStream::Exists(ushort *,int *)
0x18005df48  mov     ebx, eax
0x18005df4a  test    eax, eax
0x18005df4c  jns     short loc_18005DFB6
0x18005df4e  test    byte ptr cs:_bidGblFlags, 2
0x18005df55  jz      loc_18005E532
0x18005df5b  lea     rcx, [rdi+618h]; this
0x18005df62  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18005df67  cmp     eax, 0FFFFFFFFh
0x18005df6a  jz      short loc_18005DFA4
0x18005df6c  lea     rcx, [rdi+618h]; this
0x18005df73  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18005df78  mov     [rsp+10A0h+var_1078], 5D4h
0x18005df80  mov     edx, 175009h
0x18005df85  mov     [rsp+10A0h+var_1080], ebx
0x18005df89  lea     r8, aCrecordsetSave; "<CRecordset::SaveToFile|ADO|ERR> %u#,0x"...
0x18005df90  mov     r9d, eax
0x18005df93  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18005df9a  call    _bidTraceW
0x18005df9f  jmp     loc_18005E532
0x18005dfa4  mov     [rsp+10A0h+var_1080], 5D4h
0x18005dfac  mov     edx, 175009h
0x18005dfb1  jmp     loc_18005E51C
0x18005dfb6  cmp     [rsp+10A0h+var_1070], 0
0x18005dfbb  jz      loc_18005E109
0x18005dfc1  test    [rsi+8], r12b
0x18005dfc5  jz      loc_18005E36E
0x18005dfcb  mov     r15, [rsi]
0x18005dfce  jmp     loc_18005E371
0x18005dfd3  lea     r8, [rsp+10A0h+var_1070]; int *
0x18005dfd8  mov     rdx, r15; unsigned __int16 *
0x18005dfdb  call    ?Exists@CFileStream@@QEAAJPEAGPEAH@Z; CFileStream::Exists(ushort *,int *)
0x18005dfe0  mov     ebx, eax
0x18005dfe2  test    eax, eax
0x18005dfe4  jns     short loc_18005E034
0x18005dfe6  test    byte ptr cs:_bidGblFlags, 2
0x18005dfed  jz      loc_18005E532
0x18005dff3  lea     rcx, [rdi+618h]; this
0x18005dffa  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18005dfff  cmp     eax, 0FFFFFFFFh
0x18005e002  jz      short loc_18005E022
0x18005e004  lea     rcx, [rdi+618h]; this
0x18005e00b  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18005e010  mov     [rsp+10A0h+var_1078], 5CBh
0x18005e018  mov     edx, 172C09h
0x18005e01d  jmp     loc_18005DF85
0x18005e022  mov     [rsp+10A0h+var_1080], 5CBh
0x18005e02a  mov     edx, 172C09h
0x18005e02f  jmp     loc_18005E51C
0x18005e034  cmp     [rsp+10A0h+var_1070], 0
0x18005e039  jnz     loc_18005E371
0x18005e03f  mov     ebx, 80030050h
0x18005e044  test    byte ptr cs:_bidGblFlags, 2
0x18005e04b  jz      loc_18005E532
0x18005e051  lea     rcx, [rdi+618h]; this
0x18005e058  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18005e05d  cmp     eax, 0FFFFFFFFh
0x18005e060  jz      short loc_18005E080
0x18005e062  lea     rcx, [rdi+618h]; this
0x18005e069  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18005e06e  mov     [rsp+10A0h+var_1078], 5CFh
0x18005e076  mov     edx, 173C09h
0x18005e07b  jmp     loc_18005DF85
0x18005e080  mov     [rsp+10A0h+var_1080], 5CFh
0x18005e088  mov     edx, 173C09h
0x18005e08d  jmp     loc_18005E51C
0x18005e092  test    eax, eax
0x18005e094  jnz     loc_18005E4D2
0x18005e09a  test    [rsi+8], r12b
0x18005e09e  jz      short loc_18005E0A5
0x18005e0a0  mov     rdx, [rsi]
0x18005e0a3  jmp     short loc_18005E0A7
0x18005e0a5  xor     edx, edx; unsigned __int16 *
0x18005e0a7  lea     r8, [rsp+10A0h+var_1070]; int *
0x18005e0ac  call    ?Exists@CFileStream@@QEAAJPEAGPEAH@Z; CFileStream::Exists(ushort *,int *)
0x18005e0b1  mov     ebx, eax
0x18005e0b3  test    eax, eax
0x18005e0b5  jns     loc_18005DFB6
0x18005e0bb  test    byte ptr cs:_bidGblFlags, 2
0x18005e0c2  jz      loc_18005E532
0x18005e0c8  lea     rcx, [rdi+618h]; this
0x18005e0cf  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18005e0d4  cmp     eax, 0FFFFFFFFh
0x18005e0d7  jz      short loc_18005E0F7
0x18005e0d9  lea     rcx, [rdi+618h]; this
0x18005e0e0  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18005e0e5  mov     [rsp+10A0h+var_1078], 5E5h
0x18005e0ed  mov     edx, 179409h
0x18005e0f2  jmp     loc_18005DF85
0x18005e0f7  mov     [rsp+10A0h+var_1080], 5E5h
0x18005e0ff  mov     edx, 179409h
0x18005e104  jmp     loc_18005E51C
0x18005e109  mov     r12b, 1
0x18005e10c  test    byte ptr [rsi+8], 4
0x18005e110  jz      short loc_18005E117
0x18005e112  mov     rcx, [rsi]
0x18005e115  jmp     short loc_18005E119
0x18005e117  xor     ecx, ecx; lpFileName
0x18005e119  lea     r9, [rsp+10A0h+FilePart]; lpFilePart
0x18005e11e  lea     r8, [rsp+10A0h+Buffer]; lpBuffer
0x18005e123  mov     ebx, 3F4h
0x18005e128  mov     edx, ebx; nBufferLength
0x18005e12a  call    cs:__imp_GetFullPathNameW
0x18005e131  nop     dword ptr [rax+rax+00h]
0x18005e136  cmp     eax, ebx
0x18005e138  jb      short loc_18005E196
0x18005e13a  mov     esi, 800A0BBAh
0x18005e13f  mov     ebx, esi
0x18005e141  test    byte ptr cs:_bidGblFlags, 2
0x18005e148  jz      loc_18005E532
0x18005e14e  lea     rcx, [rdi+618h]; this
0x18005e155  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18005e15a  cmp     eax, 0FFFFFFFFh
0x18005e15d  jz      short loc_18005E181
0x18005e15f  lea     rcx, [rdi+618h]; this
0x18005e166  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18005e16b  mov     [rsp+10A0h+var_1078], 5FCh
0x18005e173  mov     [rsp+10A0h+var_1080], esi
0x18005e177  mov     edx, 17F009h
0x18005e17c  jmp     loc_18005DF89
0x18005e181  mov     [rsp+10A0h+var_1080], 5FCh
0x18005e189  mov     r9d, esi
0x18005e18c  mov     edx, 17F009h
0x18005e191  jmp     loc_18005E51F
0x18005e196  test    eax, eax
0x18005e198  jnz     short loc_18005E1F6
0x18005e19a  mov     esi, 800A0BBAh
0x18005e19f  mov     ebx, esi
0x18005e1a1  test    byte ptr cs:_bidGblFlags, 2
0x18005e1a8  jz      loc_18005E532
0x18005e1ae  lea     rcx, [rdi+618h]; this
0x18005e1b5  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18005e1ba  cmp     eax, 0FFFFFFFFh
0x18005e1bd  jz      short loc_18005E1E1
0x18005e1bf  lea     rcx, [rdi+618h]; this
0x18005e1c6  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18005e1cb  mov     [rsp+10A0h+var_1078], 5FEh
0x18005e1d3  mov     [rsp+10A0h+var_1080], esi
0x18005e1d7  mov     edx, 17F809h
0x18005e1dc  jmp     loc_18005DF89
0x18005e1e1  mov     [rsp+10A0h+var_1080], 5FEh
0x18005e1e9  mov     r9d, esi
  ... truncated ...
```
