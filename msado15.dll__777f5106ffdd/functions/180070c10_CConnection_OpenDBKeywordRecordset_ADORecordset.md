# CConnection::OpenDBKeywordRecordset(_ADORecordset * *)

- ea: `0x180070c10`
- end: `0x1800712a5`
- name: `?OpenDBKeywordRecordset@CConnection@@UEAAJPEAPEAU_ADORecordset@@@Z`
- size: `1685`
- prototype: `__int64 __fastcall(CConnection *__hidden this, struct _ADORecordset **)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x180018788`
- `0x18001a750`
- `0x18001a820`
- `0x180045580`
- `0x18004a0c0`
- `0x18004c390`
- `0x180052bf8`
- `0x18006a22c`
- `0x180070c10`
- `0x180075050`
- `0x1800c8f34`
- `0x1800cdaea`
- `0x1800cdb20`
- `0x1800d0010`

## import_xrefs

- `MSDART!MpHeapFree` at `0x18007121d`
- `MSDART!MpHeapFree` at `0x18007123f`
- `MSDART!MpHeapFree` at `0x18007121d`
- `MSDART!MpHeapFree` at `0x18007123f`
- `ole32!CoCreateInstance` at `0x180070cd2`
- `ole32!CoCreateInstance` at `0x180070cd2`

## string_xrefs

- `0x180070d2a`: `<CConnection::OpenDBKeywordRecordset|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n`
- `0x180070ee8`: `<CConnection::OpenDBKeywordRecordset|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n`
- `0x180070d4f`: `<CConnection::OpenDBKeywordRecordset|ADO|ERR> 0x%08x{HRESULT} line %d\n`
- `0x180070f11`: `<CConnection::OpenDBKeywordRecordset|ADO|ERR> 0x%08x{HRESULT} line %d\n`
- `0x1800710c1`: `<CConnection::OpenDBKeywordRecordset|ADO|ERR> %u#, line %d\n`
- `0x180071119`: `<CConnection::OpenDBKeywordRecordset|ADO|ERR> %u#, line %d\n`
- `0x18007113c`: `<CConnection::OpenDBKeywordRecordset|ADO|ERR>  line %d\n`

## pseudocode

```c
__int64 __fastcall CConnection::OpenDBKeywordRecordset(CConnection *this, struct _ADORecordset **a2)
{
  struct _ADORecordset *v4; // rdi
  HRESULT Recordset; // ebx
  unsigned int BidObjectID; // eax
  __int64 v7; // rdx
  __int64 v8; // rdx
  struct IMultipleResults *v9; // r8
  unsigned int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // rdx
  int i; // r15d
  __int64 (__fastcall *v14)(struct _ADORecordset *, __int64, __int16 *, _BYTE *); // r10
  __int64 v15; // r9
  __int64 v16; // r9
  __int64 v17; // rdx
  __int64 v18; // r9
  int v19; // r14d
  int v20; // edi
  unsigned __int16 **j; // rsi
  unsigned __int16 *v22; // rdx
  LPVOID *ppv; // [rsp+20h] [rbp-E0h]
  __int64 v25; // [rsp+28h] [rbp-D8h]
  int v26; // [rsp+40h] [rbp-C0h] BYREF
  struct _ADORecordset *v27; // [rsp+48h] [rbp-B8h] BYREF
  struct IRowset *v28; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID v29; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 **v30; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v31; // [rsp+68h] [rbp-98h] BYREF
  char v32; // [rsp+70h] [rbp-90h]
  _QWORD v33[2]; // [rsp+78h] [rbp-88h] BYREF
  __int16 v34; // [rsp+88h] [rbp-78h] BYREF
  int v35; // [rsp+90h] [rbp-70h]
  void **v36; // [rsp+A8h] [rbp-58h] BYREF
  char v37; // [rsp+B0h] [rbp-50h]
  _BYTE v38[32]; // [rsp+B8h] [rbp-48h] BYREF
  _OWORD v39[2]; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD v40[3]; // [rsp+100h] [rbp+0h] BYREF
  int v41; // [rsp+118h] [rbp+18h]
  __int64 v42; // [rsp+120h] [rbp+20h]
  int v43; // [rsp+128h] [rbp+28h]
  int v44; // [rsp+140h] [rbp+40h]
  const wchar_t *v45; // [rsp+148h] [rbp+48h]
  __int64 v46; // [rsp+150h] [rbp+50h] BYREF
  DBID v47; // [rsp+160h] [rbp+60h]
  __int16 v48; // [rsp+180h] [rbp+80h]
  __int16 v49; // [rsp+188h] [rbp+88h]
  __int64 v50; // [rsp+198h] [rbp+98h]
  DBID v51; // [rsp+1A8h] [rbp+A8h]
  __int16 v52; // [rsp+1C8h] [rbp+C8h]
  __int16 v53; // [rsp+1D0h] [rbp+D0h]

  memset_0(v40, 0, 0x50u);
  v28 = 0;
  v29 = 0;
  v4 = 0;
  v27 = 0;
  v33[0] = &CVar::`vftable';
  CVar::Init((CVar *)v33, 3u);
  v36 = &CVar::`vftable';
  CVar::Init((CVar *)&v36, 4u);
  v31 = 0;
  v32 = 7;
  v30 = 0;
  v26 = 0;
  memset(v39, 0, sizeof(v39));
  Recordset = CoCreateInstance(&CLSID_FoxRowset, 0, 3u, &IID_ICreateRowset, &v29);
  if ( Recordset < 0 )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_53;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) == -1 )
    {
      LODWORD(ppv) = 2961;
      v8 = 3032073;
      goto LABEL_7;
    }
    BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
    v7 = 3032073;
    LODWORD(v25) = 2961;
    goto LABEL_5;
  }
  v48 = 11;
  v52 = 11;
  *(_QWORD *)&v39[0] = &v46;
  v40[0] = L"Keyword";
  v45 = L"Keyword";
  *(GUID *)((char *)v39 + 12) = DBPROPSET_ROWSET;
  v49 = -1;
  v53 = -1;
  DWORD2(v39[0]) = 2;
  v46 = 127;
  v47 = DB_NULLID;
  v50 = 134;
  v51 = DB_NULLID;
  v40[1] = 0;
  v40[2] = 1;
  v41 = 4;
  v42 = 128;
  v43 = 129;
  v44 = 2;
  Recordset = (*(__int64 (__fastcall **)(LPVOID, __int64, _OWORD *, __int64, _QWORD *, struct IRowset **))(*(_QWORD *)v29 + 24LL))(
                v29,
                1,
                v39,
                1,
                v40,
                &v28);
  if ( Recordset < 0 )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_53;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) == -1 )
    {
      LODWORD(ppv) = 2996;
      v8 = 3067913;
      goto LABEL_7;
    }
    BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
    v7 = 3067913;
    LODWORD(v25) = 2996;
    goto LABEL_5;
  }
  Recordset = CConnection::GetRecordset(this, v28, v9, 0, &v27);
  if ( Recordset < 0 )
  {
    if ( (bidGblFlags & 2) == 0 )
    {
LABEL_21:
      v4 = v27;
      goto LABEL_53;
    }
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
    {
      v10 = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
      v11 = 3068937;
      LODWORD(v25) = 2997;
LABEL_18:
      LODWORD(ppv) = Recordset;
      bidTraceW(
        off_18012A1C0[0],
        v11,
        L"<CConnection::OpenDBKeywordRecordset|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
        v10,
        ppv,
        v25);
      goto LABEL_21;
    }
    LODWORD(ppv) = 2997;
    v12 = 3068937;
    goto LABEL_20;
  }
  CVar::Clear((CVar *)v33);
  v35 = 0;
  v34 = 3;
  Recordset = CConnection::getKeywords(this, &v26, &v30);
  if ( Recordset < 0 )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_21;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
    {
      v10 = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
      v11 = 3075081;
      LODWORD(v25) = 3003;
      goto LABEL_18;
    }
    LODWORD(ppv) = 3003;
    v12 = 3075081;
LABEL_20:
    bidTraceW(
      off_18012A1C0[0],
      v12,
      L"<CConnection::OpenDBKeywordRecordset|ADO|ERR> 0x%08x{HRESULT} line %d\n",
      (unsigned int)Recordset,
      ppv);
    goto LABEL_21;
  }
  v4 = v27;
  if ( v26 <= 0 )
  {
LABEL_52:
    *a2 = v4;
    goto LABEL_53;
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= v26 )
    {
      Recordset = (*(__int64 (__fastcall **)(struct _ADORecordset *))(*(_QWORD *)v4 + 304LL))(v4);
      if ( Recordset < 0 )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_53;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) == -1 )
        {
          LODWORD(ppv) = 3025;
          v8 = 3097609;
          goto LABEL_7;
        }
        BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
        v7 = 3097609;
        LODWORD(v25) = 3025;
LABEL_5:
        LODWORD(ppv) = Recordset;
        bidTraceW(
          off_18012A1C0[0],
          v7,
          L"<CConnection::OpenDBKeywordRecordset|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
          BidObjectID,
          ppv,
          v25);
        goto LABEL_53;
      }
      goto LABEL_52;
    }
    CSysString::operator=(&v31, v30[i]);
    if ( (v32 & 4) == 0 )
    {
      Recordset = -2147024882;
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_53;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
      {
        v18 = (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
        LODWORD(ppv) = 3012;
        bidTraceW(off_18012A1C0[0], 3084297, L"<CConnection::OpenDBKeywordRecordset|ADO|ERR> %u#, line %d\n", v18, ppv);
        goto LABEL_53;
      }
      v16 = 3012;
      v17 = 3084297;
      goto LABEL_46;
    }
    CVar::operator=((CVar *)&v36);
    if ( (v37 & 4) == 0 )
    {
      Recordset = -2147024882;
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_53;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
      {
        v15 = (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
        LODWORD(ppv) = 3019;
        bidTraceW(off_18012A1C0[0], 3091465, L"<CConnection::OpenDBKeywordRecordset|ADO|ERR> %u#, line %d\n", v15, ppv);
        goto LABEL_53;
      }
      v16 = 3019;
      v17 = 3091465;
LABEL_46:
      bidTraceW(off_18012A1C0[0], v17, L"<CConnection::OpenDBKeywordRecordset|ADO|ERR>  line %d\n", v16);
      goto LABEL_53;
    }
    CVar::UpdateVariant((CVar *)&v36);
    CVar::UpdateVariant((CVar *)v33);
    Recordset = v14(v4, 1, &v34, v38);
    if ( Recordset < 0 )
      break;
  }
  if ( (bidGblFlags & 2) == 0 )
    goto LABEL_53;
  if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
  {
    BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
    v7 = 3094537;
    LODWORD(v25) = 3022;
    goto LABEL_5;
  }
  LODWORD(ppv) = 3022;
  v8 = 3094537;
LABEL_7:
  bidTraceW(
    off_18012A1C0[0],
    v8,
    L"<CConnection::OpenDBKeywordRecordset|ADO|ERR> 0x%08x{HRESULT} line %d\n",
    (unsigned int)Recordset,
    ppv);
LABEL_53:
  if ( v28 )
  {
    ((void (__fastcall *)(struct IRowset *))v28->lpVtbl->Release)(v28);
    v28 = 0;
  }
  if ( v29 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v29 + 16LL))(v29);
  if ( Recordset < 0 && v4 )
    (*(void (__fastcall **)(struct _ADORecordset *))(*(_QWORD *)v4 + 16LL))(v4);
  v19 = v26;
  v20 = 0;
  for ( j = v30; v20 < v19; ++v20 )
  {
    v22 = j[v20];
    if ( v22 )
      MpHeapFree(g_hHeapHandle, v22);
  }
  if ( j )
    MpHeapFree(g_hHeapHandle, j);
  CSysString::~CSysString((CSysString *)&v31);
  v36 = &CVar::`vftable';
  CVar::Clear((CVar *)&v36);
  v33[0] = &CVar::`vftable';
  CVar::Clear((CVar *)v33);
  return (unsigned int)Recordset;
}

```

## disassembly

```asm
0x180070c10  mov     [rsp-8+arg_10], rbx
0x180070c15  push    rbp
0x180070c16  push    rsi
0x180070c17  push    rdi
0x180070c18  push    r12
0x180070c1a  push    r13
0x180070c1c  push    r14
0x180070c1e  push    r15
0x180070c20  lea     rbp, [rsp-0F0h]
0x180070c28  sub     rsp, 1F0h
0x180070c2f  mov     rax, cs:__security_cookie
0x180070c36  xor     rax, rsp
0x180070c39  mov     [rbp+120h+var_40], rax
0x180070c40  mov     r12, rdx
0x180070c43  mov     r14, rcx
0x180070c46  xor     edx, edx; Val
0x180070c48  lea     rcx, [rbp+120h+var_120]; void *
0x180070c4c  lea     r8d, [rdx+50h]; Size
0x180070c50  call    memset_0
0x180070c55  xor     r13d, r13d
0x180070c58  lea     rbx, ??_7CVar@@6B@; const CVar::`vftable'
0x180070c5f  lea     rcx, [rsp+220h+var_1A8]; this
0x180070c64  mov     [rsp+220h+var_1D0], r13
0x180070c69  mov     [rsp+220h+var_1C8], r13
0x180070c6e  mov     edi, r13d
0x180070c71  mov     [rsp+220h+var_1D8], r13
0x180070c76  lea     r15d, [r13+3]
0x180070c7a  mov     [rsp+220h+var_1A8], rbx
0x180070c7f  mov     dl, r15b; unsigned __int8
0x180070c82  call    ?Init@CVar@@AEAAXE@Z; CVar::Init(uchar)
0x180070c87  mov     dl, 4; unsigned __int8
0x180070c89  mov     [rbp+120h+var_178], rbx
0x180070c8d  lea     rcx, [rbp+120h+var_178]; this
0x180070c91  call    ?Init@CVar@@AEAAXE@Z; CVar::Init(uchar)
0x180070c96  xorps   xmm0, xmm0
0x180070c99  mov     [rsp+220h+var_1B8], r13
0x180070c9e  lea     rax, [rsp+220h+var_1C8]
0x180070ca3  mov     [rsp+220h+var_1B0], 7
0x180070ca8  lea     r9, IID_ICreateRowset; riid
0x180070caf  mov     [rsp+220h+ppv], rax; ppv
0x180070cb4  mov     r8d, r15d; dwClsContext
0x180070cb7  mov     [rsp+220h+var_1C0], r13
0x180070cbc  xor     edx, edx; pUnkOuter
0x180070cbe  mov     [rsp+220h+var_1E0], r13d
0x180070cc3  lea     rcx, ?CLSID_FoxRowset@@3U_GUID@@B; rclsid
0x180070cca  movups  [rbp+120h+var_148], xmm0
0x180070cce  movups  [rbp+120h+var_138], xmm0
0x180070cd2  call    cs:__imp_CoCreateInstance
0x180070cd9  nop     dword ptr [rax+rax+00h]
0x180070cde  lea     r10d, [r13+1]
0x180070ce2  mov     ebx, eax
0x180070ce4  lea     esi, [r13+2]
0x180070ce8  test    eax, eax
0x180070cea  jns     short loc_180070D6A
0x180070cec  test    byte ptr cs:_bidGblFlags, sil
0x180070cf3  jz      loc_1800711B0
0x180070cf9  lea     rcx, [r14+100h]; this
0x180070d00  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180070d05  cmp     eax, 0FFFFFFFFh
0x180070d08  jz      short loc_180070D42
0x180070d0a  lea     rcx, [r14+100h]; this
0x180070d11  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180070d16  mov     edx, 2E4409h
0x180070d1b  mov     dword ptr [rsp+220h+var_1F8], 0B91h
0x180070d23  mov     rcx, cs:off_18012A1C0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180070d2a  lea     r8, aCconnectionOpe_11; "<CConnection::OpenDBKeywordRecordset|AD"...
0x180070d31  mov     r9d, eax
0x180070d34  mov     dword ptr [rsp+220h+ppv], ebx
0x180070d38  call    _bidTraceW
0x180070d3d  jmp     loc_1800711B0
0x180070d42  mov     dword ptr [rsp+220h+ppv], 0B91h
0x180070d4a  mov     edx, 2E4409h
0x180070d4f  lea     r8, aCconnectionOpe_13; "<CConnection::OpenDBKeywordRecordset|AD"...
0x180070d56  mov     r9d, ebx
0x180070d59  mov     rcx, cs:off_18012A1C0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180070d60  call    _bidTraceW
0x180070d65  jmp     loc_1800711B0
0x180070d6a  movups  xmm0, xmmword ptr cs:DBPROPSET_ROWSET.Data1
0x180070d71  mov     ecx, 0Bh
0x180070d76  lea     rax, [rbp+120h+var_D0]
0x180070d7a  movups  xmm1, xmmword ptr cs:DB_NULLID.uGuid
0x180070d81  mov     [rbp+120h+var_A0], cx
0x180070d88  lea     rdx, [rsp+220h+var_1D0]
0x180070d8d  mov     [rbp+120h+var_58], cx
0x180070d94  lea     r8, [rbp+120h+var_148]
0x180070d98  mov     qword ptr [rbp+120h+var_148], rax
0x180070d9c  lea     rcx, aKeyword; "Keyword"
0x180070da3  or      eax, 0FFFFFFFFh
0x180070da6  mov     [rsp+220h+var_1F8], rdx
0x180070dab  mov     [rbp+120h+var_120], rcx
0x180070daf  lea     rdx, [rbp+120h+var_120]
0x180070db3  mov     [rbp+120h+var_D8], rcx
0x180070db7  mov     r9d, r10d
0x180070dba  mov     rcx, [rsp+220h+var_1C8]
0x180070dbf  movdqu  [rbp+120h+var_148+0Ch], xmm0
0x180070dc4  mov     [rbp+120h+var_98], ax
0x180070dcb  movups  xmm0, xmmword ptr cs:DB_NULLID.eKind
0x180070dd2  mov     [rbp+120h+var_50], ax
0x180070dd9  mov     dword ptr [rbp+120h+var_148+8], esi
0x180070ddc  mov     [rbp+120h+var_D0], 7Fh
0x180070de4  movaps  [rbp+120h+var_C0], xmm1
0x180070de8  movaps  [rbp+120h+var_B0], xmm0
0x180070dec  mov     [rbp+120h+var_88], 86h
0x180070df7  movups  [rbp+120h+var_78], xmm1
0x180070dfe  mov     [rbp+120h+var_118], r13
0x180070e02  movups  [rbp+120h+var_68], xmm0
0x180070e09  mov     [rbp+120h+var_110], r10
0x180070e0d  mov     [rbp+120h+var_108], 4
0x180070e14  mov     [rbp+120h+var_100], 80h
0x180070e1c  mov     [rbp+120h+var_F8], 81h
0x180070e23  mov     [rbp+120h+var_E0], esi
0x180070e26  mov     rax, [rcx]
0x180070e29  mov     [rsp+220h+ppv], rdx
0x180070e2e  mov     edx, r10d
0x180070e31  mov     rax, [rax+18h]
0x180070e35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070e3a  mov     ebx, eax
0x180070e3c  test    eax, eax
0x180070e3e  jns     short loc_180070E8E
0x180070e40  test    byte ptr cs:_bidGblFlags, sil
0x180070e47  jz      loc_1800711B0
0x180070e4d  lea     rcx, [r14+100h]; this
0x180070e54  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180070e59  cmp     eax, 0FFFFFFFFh
0x180070e5c  jz      short loc_180070E7C
0x180070e5e  lea     rcx, [r14+100h]; this
0x180070e65  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180070e6a  mov     edx, 2ED009h
0x180070e6f  mov     dword ptr [rsp+220h+var_1F8], 0BB4h
0x180070e77  jmp     loc_180070D23
0x180070e7c  mov     dword ptr [rsp+220h+ppv], 0BB4h
0x180070e84  mov     edx, 2ED009h
0x180070e89  jmp     loc_180070D4F
0x180070e8e  mov     rdx, [rsp+220h+var_1D0]; struct IRowset *
0x180070e93  lea     rax, [rsp+220h+var_1D8]
0x180070e98  xor     r9d, r9d; struct CRecordset *
0x180070e9b  mov     [rsp+220h+ppv], rax; struct _ADORecordset **
0x180070ea0  mov     rcx, r14; this
0x180070ea3  call    ?GetRecordset@CConnection@@QEAAJPEAUIRowset@@PEAUIMultipleResults@@PEAVCRecordset@@PEAPEAU_ADORecordset@@@Z; CConnection::GetRecordset(IRowset *,IMultipleResults *,CRecordset *,_ADORecordset * *)
0x180070ea8  mov     ebx, eax
0x180070eaa  test    eax, eax
0x180070eac  jns     short loc_180070F2A
0x180070eae  test    byte ptr cs:_bidGblFlags, sil
0x180070eb5  jz      short loc_180070F20
0x180070eb7  lea     rcx, [r14+100h]; this
0x180070ebe  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180070ec3  cmp     eax, 0FFFFFFFFh
0x180070ec6  jz      short loc_180070EFD
0x180070ec8  lea     rcx, [r14+100h]; this
0x180070ecf  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180070ed4  mov     edx, 2ED409h
0x180070ed9  mov     dword ptr [rsp+220h+var_1F8], 0BB5h
0x180070ee1  mov     rcx, cs:off_18012A1C0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180070ee8  lea     r8, aCconnectionOpe_11; "<CConnection::OpenDBKeywordRecordset|AD"...
0x180070eef  mov     r9d, eax
0x180070ef2  mov     dword ptr [rsp+220h+ppv], ebx
0x180070ef6  call    _bidTraceW
0x180070efb  jmp     short loc_180070F20
0x180070efd  mov     dword ptr [rsp+220h+ppv], 0BB5h
0x180070f05  mov     edx, 2ED409h
0x180070f0a  mov     rcx, cs:off_18012A1C0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180070f11  lea     r8, aCconnectionOpe_13; "<CConnection::OpenDBKeywordRecordset|AD"...
0x180070f18  mov     r9d, ebx
0x180070f1b  call    _bidTraceW
0x180070f20  mov     rdi, [rsp+220h+var_1D8]
0x180070f25  jmp     loc_1800711B0
0x180070f2a  lea     rcx, [rsp+220h+var_1A8]; this
0x180070f2f  call    ?Clear@CVar@@QEAAXXZ; CVar::Clear(void)
0x180070f34  lea     r8, [rsp+220h+var_1C0]; unsigned __int16 ***
0x180070f39  mov     [rbp+120h+var_190], r13d
0x180070f3d  lea     rdx, [rsp+220h+var_1E0]; int *
0x180070f42  mov     [rbp+120h+var_198], r15w
0x180070f47  mov     rcx, r14; this
0x180070f4a  call    ?getKeywords@CConnection@@QEAAJPEAJPEAPEAPEAG@Z; CConnection::getKeywords(long *,ushort * * *)
0x180070f4f  mov     ebx, eax
0x180070f51  test    eax, eax
0x180070f53  jns     short loc_180070F9F
0x180070f55  test    byte ptr cs:_bidGblFlags, sil
0x180070f5c  jz      short loc_180070F20
0x180070f5e  lea     rcx, [r14+100h]; this
0x180070f65  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180070f6a  cmp     eax, 0FFFFFFFFh
0x180070f6d  jz      short loc_180070F8D
0x180070f6f  lea     rcx, [r14+100h]; this
0x180070f76  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180070f7b  mov     edx, 2EEC09h
0x180070f80  mov     dword ptr [rsp+220h+var_1F8], 0BBBh
0x180070f88  jmp     loc_180070EE1
0x180070f8d  mov     dword ptr [rsp+220h+ppv], 0BBBh
0x180070f95  mov     edx, 2EEC09h
0x180070f9a  jmp     loc_180070F0A
0x180070f9f  mov     rdi, [rsp+220h+var_1D8]
0x180070fa4  cmp     [rsp+220h+var_1E0], r13d
0x180070fa9  jle     loc_1800711AC
0x180070faf  mov     r15d, r13d
0x180070fb2  cmp     r15d, [rsp+220h+var_1E0]
0x180070fb7  jge     loc_18007114A
0x180070fbd  mov     rdx, [rsp+220h+var_1C0]
0x180070fc2  lea     rcx, [rsp+220h+var_1B8]
0x180070fc7  movsxd  rax, r15d
0x180070fca  mov     rdx, [rdx+rax*8]
0x180070fce  call    ??4CSysString@@QEAAAEBV0@PEBG@Z; CSysString::operator=(ushort const *)
0x180070fd3  test    [rsp+220h+var_1B0], 4
0x180070fd8  jz      loc_1800710DF
0x180070fde  lea     rdx, [rsp+220h+var_1B8]
0x180070fe3  lea     rcx, [rbp+120h+var_178]; this
0x180070fe7  call    ??4CVar@@QEAAAEBV0@AEBVCSysString@@@Z; CVar::operator=(CSysString const &)
0x180070fec  test    [rbp+120h+var_170], 4
0x180070ff0  jz      loc_180071087
0x180070ff6  mov     rax, [rdi]
0x180070ff9  lea     rcx, [rbp+120h+var_178]; this
0x180070ffd  mov     r10, [rax+2F8h]
0x180071004  call    ?UpdateVariant@CVar@@QEAAXXZ; CVar::UpdateVariant(void)
0x180071009  lea     rcx, [rsp+220h+var_1A8]; this
0x18007100e  call    ?UpdateVariant@CVar@@QEAAXXZ; CVar::UpdateVariant(void)
0x180071013  lea     r9, [rbp+120h+var_168]
0x180071017  mov     edx, 1
0x18007101c  mov     rcx, rdi
0x18007101f  lea     r8, [rbp+120h+var_198]
0x180071023  mov     rax, r10
0x180071026  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007102b  mov     ebx, eax
0x18007102d  test    eax, eax
0x18007102f  js      short loc_180071039
0x180071031  inc     r15d
0x180071034  jmp     loc_180070FB2
0x180071039  test    byte ptr cs:_bidGblFlags, sil
0x180071040  jz      loc_1800711B0
0x180071046  lea     rcx, [r14+100h]; this
0x18007104d  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180071052  cmp     eax, 0FFFFFFFFh
0x180071055  jz      short loc_180071075
0x180071057  lea     rcx, [r14+100h]; this
0x18007105e  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180071063  mov     edx, 2F3809h
0x180071068  mov     dword ptr [rsp+220h+var_1F8], 0BCEh
0x180071070  jmp     loc_180070D23
0x180071075  mov     dword ptr [rsp+220h+ppv], 0BCEh
0x18007107d  mov     edx, 2F3809h
0x180071082  jmp     loc_180070D4F
0x180071087  test    byte ptr cs:_bidGblFlags, sil
0x18007108e  mov     ebx, 8007000Eh
0x180071093  jz      loc_1800711B0
0x180071099  lea     rcx, [r14+100h]; this
0x1800710a0  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800710a5  cmp     eax, 0FFFFFFFFh
0x1800710a8  jz      short loc_1800710D2
0x1800710aa  lea     rcx, [r14+100h]; this
0x1800710b1  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800710b6  mov     r9d, eax
0x1800710b9  mov     dword ptr [rsp+220h+ppv], 0BCBh
0x1800710c1  lea     r8, aCconnectionOpe_22; "<CConnection::OpenDBKeywordRecordset|AD"...
0x1800710c8  mov     edx, 2F2C09h
0x1800710cd  jmp     loc_180070D59
0x1800710d2  mov     r9d, 0BCBh
0x1800710d8  mov     edx, 2F2C09h
0x1800710dd  jmp     short loc_180071135
0x1800710df  test    byte ptr cs:_bidGblFlags, sil
0x1800710e6  mov     ebx, 8007000Eh
0x1800710eb  jz      loc_1800711B0
0x1800710f1  lea     rcx, [r14+100h]; this
0x1800710f8  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800710fd  cmp     eax, 0FFFFFFFFh
0x180071100  jz      short loc_18007112A
0x180071102  lea     rcx, [r14+100h]; this
0x180071109  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18007110e  mov     r9d, eax
0x180071111  mov     dword ptr [rsp+220h+ppv], 0BC4h
0x180071119  lea     r8, aCconnectionOpe_22; "<CConnection::OpenDBKeywordRecordset|AD"...
0x180071120  mov     edx, 2F1009h
0x180071125  jmp     loc_180070D59
0x18007112a  mov     r9d, 0BC4h
0x180071130  mov     edx, 2F1009h
0x180071135  mov     rcx, cs:off_18012A1C0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18007113c  lea     r8, aCconnectionOpe_1; "<CConnection::OpenDBKeywordRecordset|AD"...
0x180071143  call    _bidTraceW
0x180071148  jmp     short loc_1800711B0
0x18007114a  mov     rax, [rdi]
0x18007114d  mov     rcx, rdi
0x180071150  mov     rax, [rax+130h]
0x180071157  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007115c  mov     ebx, eax
0x18007115e  test    eax, eax
0x180071160  jns     short loc_1800711AC
0x180071162  test    byte ptr cs:_bidGblFlags, sil
0x180071169  jz      short loc_1800711B0
0x18007116b  lea     rcx, [r14+100h]; this
0x180071172  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180071177  cmp     eax, 0FFFFFFFFh
0x18007117a  jz      short loc_18007119A
0x18007117c  lea     rcx, [r14+100h]; this
0x180071183  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180071188  mov     edx, 2F4409h
0x18007118d  mov     dword ptr [rsp+220h+var_1F8], 0BD1h
0x180071195  jmp     loc_180070D23
0x18007119a  mov     dword ptr [rsp+220h+ppv], 0BD1h
0x1800711a2  mov     edx, 2F4409h
0x1800711a7  jmp     loc_180070D4F
0x1800711ac  mov     [r12], rdi
0x1800711b0  mov     rcx, [rsp+220h+var_1D0]
  ... truncated ...
```
