# CRecordset::CreateRowset(void)

- ea: `0x1800a8670`
- end: `0x1800a8bff`
- name: `?CreateRowset@CRecordset@@UEAAJXZ`
- size: `1423`
- prototype: `__int64 __fastcall(CRecordset *__hidden this)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x180002840`
- `0x180011530`
- `0x18002a580`
- `0x180053fec`
- `0x180057e14`
- `0x18005b724`
- `0x18006a22c`
- `0x1800a8670`
- `0x1800c8f34`
- `0x1800cdb20`
- `0x1800d0010`

## import_xrefs

- `MSDART!MpHeapAlloc` at `0x1800a871d`
- `MSDART!MpHeapAlloc` at `0x1800a899d`
- `MSDART!MpHeapAlloc` at `0x1800a871d`
- `MSDART!MpHeapAlloc` at `0x1800a899d`
- `MSDART!MpHeapFree` at `0x1800a883a`
- `MSDART!MpHeapFree` at `0x1800a883a`
- `ole32!CoCreateInstance` at `0x1800a88ed`
- `ole32!CoCreateInstance` at `0x1800a88ed`

## string_xrefs

- `0x1800a8819`: `<CRecordset::CreateRowset|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n`
- `0x1800a8afc`: `<CRecordset::CreateRowset|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n`
- `0x1800a8b8f`: `<CRecordset::CreateRowset|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n`
- `0x1800a88b5`: `<CRecordset::CreateRowset|ADO|ERR> 0x%08x{HRESULT} line %d\n`
- `0x1800a8b28`: `<CRecordset::CreateRowset|ADO|ERR> 0x%08x{HRESULT} line %d\n`
- `0x1800a8bbb`: `<CRecordset::CreateRowset|ADO|ERR> 0x%08x{HRESULT} line %d\n`
- `0x1800a89eb`: `<CRecordset::CreateRowset|ADO|ERR> %u#, line %d\n`
- `0x1800a8a03`: `<CRecordset::CreateRowset|ADO|ERR>  line %d\n`

## pseudocode

```c
__int64 __fastcall CRecordset::CreateRowset(CRecordset *this)
{
  CStdCollection *v1; // r14
  CRecordset *v2; // rdi
  unsigned int Count; // eax
  int v4; // ecx
  __int64 v5; // r13
  __int64 v6; // rax
  int v7; // r12d
  __int64 v8; // rax
  __int64 v9; // rbx
  struct tagDBPROP *v11; // r15
  unsigned int v12; // esi
  struct CStdComObjectRoot *v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rax
  HRESULT v16; // ebx
  unsigned int BidObjectID; // eax
  __int64 v18; // rdx
  __int64 v19; // rsi
  __int64 v20; // rdx
  unsigned int v21; // r12d
  unsigned __int64 v22; // rsi
  __int64 i; // rcx
  unsigned int v24; // eax
  __int64 v25; // rax
  __int64 v26; // r9
  __int64 v27; // r14
  unsigned __int64 v28; // r8
  bool v29; // zf
  unsigned int v30; // eax
  unsigned int v31; // eax
  LPVOID *ppv; // [rsp+20h] [rbp-69h]
  LPVOID *ppva; // [rsp+20h] [rbp-69h]
  int v34; // [rsp+28h] [rbp-61h]
  __int64 v35; // [rsp+28h] [rbp-61h]
  __int64 v36; // [rsp+40h] [rbp-49h]
  LPVOID v37; // [rsp+48h] [rbp-41h] BYREF
  int v38; // [rsp+50h] [rbp-39h]
  __int64 v39; // [rsp+58h] [rbp-31h] BYREF
  struct CStdComObjectRoot *v40; // [rsp+60h] [rbp-29h] BYREF
  CRecordset *v41; // [rsp+68h] [rbp-21h]
  _OWORD v42[2]; // [rsp+70h] [rbp-19h] BYREF

  v1 = (CRecordset *)((char *)this + 1584);
  v41 = this;
  v2 = this;
  v37 = 0;
  Count = CStdCollection::GetCount((CRecordset *)((char *)this + 1584));
  v4 = *((_DWORD *)v2 + 343);
  v5 = Count;
  if ( v4 == -1 )
  {
    *((_DWORD *)v2 + 343) = 4;
    v4 = 4;
  }
  v40 = 0;
  v39 = 0;
  v38 = dword_1800E8744[v4];
  v6 = *((int *)v2 + 362);
  memset(v42, 0, sizeof(v42));
  v7 = dword_1800E87A0[v6];
  v8 = MpHeapAlloc(g_hHeapHandle, 10485760, 80 * v5);
  v9 = v8;
  if ( !v8 )
    return 2147942414LL;
  v11 = 0;
  v36 = v8;
  v12 = 0;
  while ( v12 < (unsigned int)v5 )
  {
    if ( CStdCollection::GetElement(v1, v12, &v40) )
    {
      v16 = -2147467259;
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)v2 + 1560)) != -1 )
        {
          BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)v2 + 1560));
          v18 = 8219657;
          v34 = 8027;
          goto LABEL_20;
        }
        LODWORD(ppv) = 8027;
        v20 = 8219657;
LABEL_31:
        bidTraceW(
          off_18012A208[0],
          v20,
          L"<CRecordset::CreateRowset|ADO|ERR> 0x%08x{HRESULT} line %d\n",
          (unsigned int)v16,
          ppv);
      }
      goto LABEL_21;
    }
    v13 = v40;
    if ( v40 )
      v13 = (struct CStdComObjectRoot *)((char *)v40 - 8);
    if ( (*((_BYTE *)v13 + 96) & 4) != 0 )
      v14 = *((_QWORD *)v13 + 11);
    else
      v14 = 0;
    *(_QWORD *)v9 = v14;
    *(_DWORD *)(v9 + 64) = 2;
    if ( (*((_BYTE *)v13 + 96) & 4) != 0 )
      v15 = *((_QWORD *)v13 + 11);
    else
      v15 = 0;
    *(_QWORD *)(v9 + 72) = v15;
    ++v12;
    *(_QWORD *)(v9 + 8) = 0;
    *(_QWORD *)(v9 + 16) = v12;
    *(_DWORD *)(v9 + 24) = *((_DWORD *)v13 + 34);
    *(_QWORD *)(v9 + 32) = *((_QWORD *)v13 + 15);
    *(_WORD *)(v9 + 40) = *((_WORD *)v13 + 56);
    *(_BYTE *)(v9 + 42) = *((_BYTE *)v13 + 128);
    *(_BYTE *)(v9 + 43) = *((_BYTE *)v13 + 129);
    v9 += 80;
  }
  v16 = CoCreateInstance(&CLSID_FoxRowset, 0, 3u, &IID_ICreateRowset, &v37);
  if ( v16 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)v2 + 1560)) == -1 )
      {
        LODWORD(ppv) = 8048;
        v20 = 8241161;
        goto LABEL_31;
      }
      BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)v2 + 1560));
      v18 = 8241161;
      v34 = 8048;
LABEL_20:
      LODWORD(ppv) = v16;
      bidTraceW(
        off_18012A208[0],
        v18,
        L"<CRecordset::CreateRowset|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
        BidObjectID,
        ppv,
        v34);
    }
LABEL_21:
    v19 = v36;
LABEL_22:
    MpHeapFree(g_hHeapHandle, v19);
    goto LABEL_23;
  }
  v21 = v38 | v7;
  LODWORD(v22) = 0;
  for ( i = 0; i != 17; ++i )
  {
    v24 = v22 + 1;
    if ( (v21 & *((_DWORD *)&xmmword_1800E0CE0 + i)) == 0 )
      v24 = v22;
    v22 = v24;
  }
  if ( v24 )
  {
    v25 = 72LL * v24;
    if ( !is_mul_ok(v22, 0x48u) )
      v25 = -1;
    v11 = (struct tagDBPROP *)MpHeapAlloc(g_hHeapHandle, 10485760, v25);
    if ( !v11 )
    {
      v16 = -2147024882;
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)v2 + 1560)) == -1 )
        {
          bidTraceW(off_18012A208[0], 8257545, L"<CRecordset::CreateRowset|ADO|ERR>  line %d\n", 8064);
        }
        else
        {
          v26 = (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)v2 + 1560));
          LODWORD(ppv) = 8064;
          bidTraceW(off_18012A208[0], 8257545, L"<CRecordset::CreateRowset|ADO|ERR> %u#, line %d\n", v26, ppv);
        }
      }
      goto LABEL_21;
    }
    v22 = 0;
    v27 = 0;
    do
    {
      if ( (v21 & *((_DWORD *)&xmmword_1800E0CE0 + v27)) != 0 )
      {
        FillDBProp(dword_1800E14F0[v27], &v11[v22], 0, 0, 0);
        SetCommandPropVal(&v11[v22], v27, v21, 1);
        v22 = (unsigned int)(v22 + 1);
      }
      v27 = (unsigned int)(v27 + 1);
    }
    while ( (unsigned int)v27 < 0x11 );
    v2 = v41;
    *(_QWORD *)&v42[0] = v11;
    *(GUID *)((char *)v42 + 12) = DBPROPSET_ROWSET;
    DWORD2(v42[0]) = v22;
  }
  v28 = (unsigned __int64)v42 & -(__int64)((_DWORD)v22 != 0);
  v29 = (_DWORD)v22 == 0;
  v19 = v36;
  v16 = (*(__int64 (__fastcall **)(LPVOID, bool, unsigned __int64, _QWORD, __int64, __int64 *))(*(_QWORD *)v37 + 24LL))(
          v37,
          !v29,
          v28,
          (unsigned int)v5,
          v36,
          &v39);
  if ( v16 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)v2 + 1560)) == -1 )
      {
        LODWORD(ppva) = 8088;
        bidTraceW(
          off_18012A208[0],
          8282121,
          L"<CRecordset::CreateRowset|ADO|ERR> 0x%08x{HRESULT} line %d\n",
          (unsigned int)v16,
          ppva);
      }
      else
      {
        v30 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)v2 + 1560));
        LODWORD(v35) = 8088;
        LODWORD(ppva) = v16;
        bidTraceW(
          off_18012A208[0],
          8282121,
          L"<CRecordset::CreateRowset|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
          v30,
          ppva,
          v35);
      }
    }
    goto LABEL_22;
  }
  v16 = CRecordset::SetRowset(v2, v39, 0);
  if ( v16 >= 0 )
  {
    *((_DWORD *)v2 + 177) = 3;
    *((_DWORD *)v2 + 451) = 1;
    *((_DWORD *)v2 + 417) = 1;
    goto LABEL_22;
  }
  if ( (bidGblFlags & 2) != 0 )
  {
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)v2 + 1560)) == -1 )
    {
      LODWORD(ppva) = 8091;
      bidTraceW(
        off_18012A208[0],
        8285193,
        L"<CRecordset::CreateRowset|ADO|ERR> 0x%08x{HRESULT} line %d\n",
        (unsigned int)v16,
        ppva);
    }
    else
    {
      v31 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)v2 + 1560));
      LODWORD(v35) = 8091;
      LODWORD(ppva) = v16;
      bidTraceW(
        off_18012A208[0],
        8285193,
        L"<CRecordset::CreateRowset|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
        v31,
        ppva,
        v35);
    }
  }
LABEL_23:
  if ( v11 )
    operator delete(v11);
  if ( v37 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v37 + 16LL))(v37);
    v37 = 0;
  }
  if ( v39 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x1800a8670  push    rbp
0x1800a8672  push    rbx
0x1800a8673  push    rsi
0x1800a8674  push    rdi
0x1800a8675  push    r12
0x1800a8677  push    r13
0x1800a8679  push    r14
0x1800a867b  push    r15
0x1800a867d  lea     rbp, [rsp-1Fh]
0x1800a8682  sub     rsp, 0A8h
0x1800a8689  mov     rax, cs:__security_cookie
0x1800a8690  xor     rax, rsp
0x1800a8693  mov     [rbp+57h+var_50], rax
0x1800a8697  lea     r14, [rcx+630h]
0x1800a869e  mov     [rbp+57h+var_78], rcx
0x1800a86a2  mov     rdi, rcx
0x1800a86a5  xor     ebx, ebx
0x1800a86a7  mov     rcx, r14; this
0x1800a86aa  mov     [rbp+57h+var_98], rbx
0x1800a86ae  call    ?GetCount@CStdCollection@@UEAAKXZ; CStdCollection::GetCount(void)
0x1800a86b3  mov     ecx, [rdi+55Ch]
0x1800a86b9  mov     r13d, eax
0x1800a86bc  lea     eax, [rbx+4]
0x1800a86bf  cmp     ecx, 0FFFFFFFFh
0x1800a86c2  jnz     short loc_1800A86CC
0x1800a86c4  mov     [rdi+55Ch], eax
0x1800a86ca  mov     ecx, eax
0x1800a86cc  movsxd  rax, ecx
0x1800a86cf  lea     r8, ds:0[r13*4]
0x1800a86d7  lea     rcx, cs:180000000h
0x1800a86de  mov     [rbp+57h+var_80], rbx
0x1800a86e2  xorps   xmm0, xmm0
0x1800a86e5  mov     [rbp+57h+var_88], rbx
0x1800a86e9  add     r8, r13
0x1800a86ec  mov     edx, 0A00000h
0x1800a86f1  mov     eax, ds:rva dword_1800E8744[rcx+rax*4]
0x1800a86f8  mov     [rbp+57h+var_90], eax
0x1800a86fb  movsxd  rax, dword ptr [rdi+5A8h]
0x1800a8702  shl     r8, 4
0x1800a8706  movups  [rbp+57h+var_70], xmm0
0x1800a870a  mov     r12d, ds:rva dword_1800E87A0[rcx+rax*4]
0x1800a8712  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x1800a8719  movups  [rbp+57h+var_60], xmm0
0x1800a871d  call    cs:__imp_MpHeapAlloc
0x1800a8724  nop     dword ptr [rax+rax+00h]
0x1800a8729  mov     rbx, rax
0x1800a872c  test    rax, rax
0x1800a872f  jnz     short loc_1800A873B
0x1800a8731  mov     eax, 8007000Eh
0x1800a8736  jmp     loc_1800A8887
0x1800a873b  xor     r15d, r15d
0x1800a873e  mov     [rbp+57h+var_A0], rax
0x1800a8742  xor     esi, esi
0x1800a8744  cmp     esi, r13d
0x1800a8747  jnb     loc_1800A88D0
0x1800a874d  mov     edx, esi; unsigned __int64
0x1800a874f  lea     r8, [rbp+57h+var_80]; struct CStdComObjectRoot **
0x1800a8753  mov     rcx, r14; this
0x1800a8756  call    ?GetElement@CStdCollection@@QEAAJ_KPEAPEAVCStdComObjectRoot@@@Z; CStdCollection::GetElement(unsigned __int64,CStdComObjectRoot * *)
0x1800a875b  test    eax, eax
0x1800a875d  jnz     short loc_1800A87D6
0x1800a875f  mov     rcx, [rbp+57h+var_80]
0x1800a8763  test    rcx, rcx
0x1800a8766  jz      short loc_1800A876C
0x1800a8768  add     rcx, 0FFFFFFFFFFFFFFF8h
0x1800a876c  test    byte ptr [rcx+60h], 4
0x1800a8770  jz      short loc_1800A8778
0x1800a8772  mov     rax, [rcx+58h]
0x1800a8776  jmp     short loc_1800A877A
0x1800a8778  xor     eax, eax
0x1800a877a  mov     [rbx], rax
0x1800a877d  mov     dword ptr [rbx+40h], 2
0x1800a8784  test    byte ptr [rcx+60h], 4
0x1800a8788  jz      short loc_1800A8790
0x1800a878a  mov     rax, [rcx+58h]
0x1800a878e  jmp     short loc_1800A8792
0x1800a8790  xor     eax, eax
0x1800a8792  mov     [rbx+48h], rax
0x1800a8796  inc     esi
0x1800a8798  mov     [rbx+8], r15
0x1800a879c  mov     eax, esi
0x1800a879e  mov     [rbx+10h], rax
0x1800a87a2  mov     eax, [rcx+88h]
0x1800a87a8  mov     [rbx+18h], eax
0x1800a87ab  mov     rax, [rcx+78h]
0x1800a87af  mov     [rbx+20h], rax
0x1800a87b3  movzx   eax, word ptr [rcx+70h]
0x1800a87b7  mov     [rbx+28h], ax
0x1800a87bb  mov     al, [rcx+80h]
0x1800a87c1  mov     [rbx+2Ah], al
0x1800a87c4  mov     al, [rcx+81h]
0x1800a87ca  mov     [rbx+2Bh], al
0x1800a87cd  add     rbx, 50h ; 'P'
0x1800a87d1  jmp     loc_1800A8744
0x1800a87d6  test    byte ptr cs:_bidGblFlags, 2
0x1800a87dd  mov     ebx, 80004005h
0x1800a87e2  jz      short loc_1800A882C
0x1800a87e4  lea     rcx, [rdi+618h]; this
0x1800a87eb  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a87f0  cmp     eax, 0FFFFFFFFh
0x1800a87f3  jz      loc_1800A88A8
0x1800a87f9  lea     rcx, [rdi+618h]; this
0x1800a8800  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a8805  mov     edx, 7D6C09h
0x1800a880a  mov     dword ptr [rsp+0E0h+var_B8], 1F5Bh
0x1800a8812  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800a8819  lea     r8, aCrecordsetCrea_3; "<CRecordset::CreateRowset|ADO|ERR> %u#,"...
0x1800a8820  mov     r9d, eax
0x1800a8823  mov     dword ptr [rsp+0E0h+ppv], ebx
0x1800a8827  call    _bidTraceW
0x1800a882c  mov     rsi, [rbp+57h+var_A0]
0x1800a8830  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x1800a8837  mov     rdx, rsi
0x1800a883a  call    cs:__imp_MpHeapFree
0x1800a8841  nop     dword ptr [rax+rax+00h]
0x1800a8846  test    r15, r15
0x1800a8849  jz      short loc_1800A8853
0x1800a884b  mov     rcx, r15; void *
0x1800a884e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800a8853  mov     rcx, [rbp+57h+var_98]
0x1800a8857  test    rcx, rcx
0x1800a885a  jz      short loc_1800A8870
0x1800a885c  mov     rax, [rcx]
0x1800a885f  mov     rax, [rax+10h]
0x1800a8863  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8868  mov     [rbp+57h+var_98], 0
0x1800a8870  mov     rcx, [rbp+57h+var_88]
0x1800a8874  test    rcx, rcx
0x1800a8877  jz      short loc_1800A8885
0x1800a8879  mov     rax, [rcx]
0x1800a887c  mov     rax, [rax+10h]
0x1800a8880  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8885  mov     eax, ebx
0x1800a8887  mov     rcx, [rbp+57h+var_50]
0x1800a888b  xor     rcx, rsp; StackCookie
0x1800a888e  call    __security_check_cookie
0x1800a8893  add     rsp, 0A8h
0x1800a889a  pop     r15
0x1800a889c  pop     r14
0x1800a889e  pop     r13
0x1800a88a0  pop     r12
0x1800a88a2  pop     rdi
0x1800a88a3  pop     rsi
0x1800a88a4  pop     rbx
0x1800a88a5  pop     rbp
0x1800a88a6  retn
0x1800a88a8  mov     dword ptr [rsp+0E0h+ppv], 1F5Bh
0x1800a88b0  mov     edx, 7D6C09h
0x1800a88b5  lea     r8, aCrecordsetCrea_4; "<CRecordset::CreateRowset|ADO|ERR> 0x%0"...
0x1800a88bc  mov     r9d, ebx
0x1800a88bf  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800a88c6  call    _bidTraceW
0x1800a88cb  jmp     loc_1800A882C
0x1800a88d0  xor     edx, edx; pUnkOuter
0x1800a88d2  lea     rax, [rbp+57h+var_98]
0x1800a88d6  lea     r9, IID_ICreateRowset; riid
0x1800a88dd  mov     [rsp+0E0h+ppv], rax; ppv
0x1800a88e2  lea     rcx, ?CLSID_FoxRowset@@3U_GUID@@B; rclsid
0x1800a88e9  lea     r8d, [rdx+3]; dwClsContext
0x1800a88ed  call    cs:__imp_CoCreateInstance
0x1800a88f4  nop     dword ptr [rax+rax+00h]
0x1800a88f9  mov     ebx, eax
0x1800a88fb  test    eax, eax
0x1800a88fd  jns     short loc_1800A894D
0x1800a88ff  test    byte ptr cs:_bidGblFlags, 2
0x1800a8906  jz      loc_1800A882C
0x1800a890c  lea     rcx, [rdi+618h]; this
0x1800a8913  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a8918  cmp     eax, 0FFFFFFFFh
0x1800a891b  jz      short loc_1800A893B
0x1800a891d  lea     rcx, [rdi+618h]; this
0x1800a8924  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a8929  mov     edx, 7DC009h
0x1800a892e  mov     dword ptr [rsp+0E0h+var_B8], 1F70h
0x1800a8936  jmp     loc_1800A8812
0x1800a893b  mov     dword ptr [rsp+0E0h+ppv], 1F70h
0x1800a8943  mov     edx, 7DC009h
0x1800a8948  jmp     loc_1800A88B5
0x1800a894d  or      r12d, [rbp+57h+var_90]
0x1800a8951  lea     r8, cs:180000000h
0x1800a8958  xor     esi, esi
0x1800a895a  xor     ecx, ecx
0x1800a895c  test    dword ptr ds:rva xmmword_1800E0CE0[r8+rcx*4], r12d
0x1800a8964  lea     eax, [rsi+1]
0x1800a8967  cmovz   eax, esi
0x1800a896a  inc     rcx
0x1800a896d  mov     esi, eax
0x1800a896f  cmp     rcx, 11h
0x1800a8973  jnz     short loc_1800A895C
0x1800a8975  test    eax, eax
0x1800a8977  jz      loc_1800A8A8B
0x1800a897d  lea     eax, [rcx+37h]
0x1800a8980  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800a8987  mul     rsi
0x1800a898a  mov     edx, 0A00000h
0x1800a898f  cmovb   rax, rcx
0x1800a8993  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x1800a899a  mov     r8, rax
0x1800a899d  call    cs:__imp_MpHeapAlloc
0x1800a89a4  nop     dword ptr [rax+rax+00h]
0x1800a89a9  mov     r15, rax
0x1800a89ac  test    rax, rax
0x1800a89af  jnz     short loc_1800A8A1F
0x1800a89b1  test    byte ptr cs:_bidGblFlags, 2
0x1800a89b8  mov     ebx, 8007000Eh
0x1800a89bd  jz      loc_1800A882C
0x1800a89c3  lea     rcx, [rdi+618h]; this
0x1800a89ca  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a89cf  cmp     eax, 0FFFFFFFFh
0x1800a89d2  jz      short loc_1800A89FC
0x1800a89d4  lea     rcx, [rdi+618h]; this
0x1800a89db  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a89e0  mov     r9d, eax
0x1800a89e3  mov     dword ptr [rsp+0E0h+ppv], 1F80h
0x1800a89eb  lea     r8, aCrecordsetCrea; "<CRecordset::CreateRowset|ADO|ERR> %u#,"...
0x1800a89f2  mov     edx, 7E0009h
0x1800a89f7  jmp     loc_1800A88BF
0x1800a89fc  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800a8a03  lea     r8, aCrecordsetCrea_0; "<CRecordset::CreateRowset|ADO|ERR>  lin"...
0x1800a8a0a  mov     r9d, 1F80h
0x1800a8a10  mov     edx, 7E0009h
0x1800a8a15  call    _bidTraceW
0x1800a8a1a  jmp     loc_1800A882C
0x1800a8a1f  xor     esi, esi
0x1800a8a21  lea     rdi, cs:180000000h
0x1800a8a28  xor     r14d, r14d
0x1800a8a2b  test    dword ptr ds:rva xmmword_1800E0CE0[rdi+r14*4], r12d
0x1800a8a33  jz      short loc_1800A8A6B
0x1800a8a35  lea     rcx, [rsi+rsi*8]
0x1800a8a39  xor     r9d, r9d; unsigned __int16
0x1800a8a3c  lea     rbx, [r15+rcx*8]
0x1800a8a40  mov     byte ptr [rsp+0E0h+ppv], r9b; unsigned __int8
0x1800a8a45  mov     ecx, ds:rva dword_1800E14F0[rdi+r14*4]; unsigned int
0x1800a8a4d  mov     rdx, rbx; struct tagDBPROP *
0x1800a8a50  xor     r8d, r8d; struct tagVARIANT *
0x1800a8a53  call    ?FillDBProp@@YAJKPEAUtagDBPROP@@PEAUtagVARIANT@@GE@Z; FillDBProp(ulong,tagDBPROP *,tagVARIANT *,ushort,uchar)
0x1800a8a58  mov     r9b, 1; bool
0x1800a8a5b  mov     r8d, r12d; unsigned int
0x1800a8a5e  mov     edx, r14d; unsigned int
0x1800a8a61  mov     rcx, rbx; struct tagDBPROP *
0x1800a8a64  call    ?SetCommandPropVal@@YAXAEAUtagDBPROP@@KK_N@Z; SetCommandPropVal(tagDBPROP &,ulong,ulong,bool)
0x1800a8a69  inc     esi
0x1800a8a6b  inc     r14d
0x1800a8a6e  cmp     r14d, 11h
0x1800a8a72  jb      short loc_1800A8A2B
0x1800a8a74  movups  xmm0, xmmword ptr cs:DBPROPSET_ROWSET.Data1
0x1800a8a7b  mov     rdi, [rbp+57h+var_78]
0x1800a8a7f  mov     qword ptr [rbp+57h+var_70], r15
0x1800a8a83  movdqu  [rbp+57h+var_70+0Ch], xmm0
0x1800a8a88  mov     dword ptr [rbp+57h+var_70+8], esi
0x1800a8a8b  mov     rcx, [rbp+57h+var_98]
0x1800a8a8f  mov     eax, esi
0x1800a8a91  neg     eax
0x1800a8a93  lea     rax, [rbp+57h+var_70]
0x1800a8a97  sbb     r8, r8
0x1800a8a9a  xor     edx, edx
0x1800a8a9c  mov     r9, [rcx]
0x1800a8a9f  and     r8, rax
0x1800a8aa2  test    esi, esi
0x1800a8aa4  mov     rsi, [rbp+57h+var_A0]
0x1800a8aa8  setnz   dl
0x1800a8aab  mov     rax, [r9+18h]
0x1800a8aaf  lea     r9, [rbp+57h+var_88]
0x1800a8ab3  mov     [rsp+0E0h+var_B8], r9
0x1800a8ab8  mov     r9d, r13d
0x1800a8abb  mov     [rsp+0E0h+ppv], rsi
0x1800a8ac0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8ac5  mov     ebx, eax
0x1800a8ac7  test    eax, eax
0x1800a8ac9  jns     short loc_1800A8B49
0x1800a8acb  test    byte ptr cs:_bidGblFlags, 2
0x1800a8ad2  jz      loc_1800A8830
0x1800a8ad8  lea     rcx, [rdi+618h]; this
0x1800a8adf  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a8ae4  cmp     eax, 0FFFFFFFFh
0x1800a8ae7  jz      short loc_1800A8B21
0x1800a8ae9  lea     rcx, [rdi+618h]; this
0x1800a8af0  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a8af5  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800a8afc  lea     r8, aCrecordsetCrea_3; "<CRecordset::CreateRowset|ADO|ERR> %u#,"...
0x1800a8b03  mov     r9d, eax
0x1800a8b06  mov     dword ptr [rsp+0E0h+var_B8], 1F98h
0x1800a8b0e  mov     edx, 7E6009h
0x1800a8b13  mov     dword ptr [rsp+0E0h+ppv], ebx
0x1800a8b17  call    _bidTraceW
0x1800a8b1c  jmp     loc_1800A8830
0x1800a8b21  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800a8b28  lea     r8, aCrecordsetCrea_4; "<CRecordset::CreateRowset|ADO|ERR> 0x%0"...
0x1800a8b2f  mov     r9d, ebx
0x1800a8b32  mov     dword ptr [rsp+0E0h+ppv], 1F98h
0x1800a8b3a  mov     edx, 7E6009h
0x1800a8b3f  call    _bidTraceW
0x1800a8b44  jmp     loc_1800A8830
0x1800a8b49  mov     rdx, [rbp+57h+var_88]
0x1800a8b4d  xor     r8d, r8d
0x1800a8b50  mov     rcx, rdi
0x1800a8b53  call    ?SetRowset@CRecordset@@QEAAJPEAUIUnknown@@W4PointerFormat@@@Z; CRecordset::SetRowset(IUnknown *,PointerFormat)
0x1800a8b58  mov     ebx, eax
0x1800a8b5a  test    eax, eax
0x1800a8b5c  jns     short loc_1800A8BDC
  ... truncated ...
```
