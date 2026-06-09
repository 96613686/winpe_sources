# CStream::Read(long,tagVARIANT *)

- ea: `0x1800bf180`
- end: `0x1800bf5ec`
- name: `?Read@CStream@@UEAAJJPEAUtagVARIANT@@@Z`
- size: `1132`
- prototype: `__int64 __fastcall(CStream *__hidden this, unsigned int, VARIANTARG *pvarg)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18009fae0`

## callees

- `0x180020e20`
- `0x180031760`
- `0x180032710`
- `0x18006a22c`
- `0x1800bf180`
- `0x1800bf95c`
- `0x1800c8ebc`
- `0x1800c8f34`
- `0x1800d0010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x1800bf2a4`
- `OLEAUT32!__imp_VariantClear` at `0x1800bf2a4`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800bf4f9`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800bf4f9`

## string_xrefs

- `0x1800bf26a`: `<CStream::Read|ADO|ERR> %u#, line %d\n`
- `0x1800bf290`: `<CStream::Read|ADO|ERR>  line %d\n`

## pseudocode

```c
__int64 __fastcall CStream::Read(CStream *this, signed int a2, VARIANTARG *pvarg)
{
  unsigned int BidObjectID; // eax
  unsigned int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // r9
  __int64 v10; // rdx
  union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *p_llVal; // rsi
  unsigned int v12; // eax
  unsigned int v13; // ebx
  unsigned int v14; // eax
  unsigned int v15; // ebx
  __int64 v17; // [rsp+20h] [rbp-50h]
  _BYTE v18[40]; // [rsp+30h] [rbp-40h] BYREF
  unsigned int v19; // [rsp+58h] [rbp-18h]
  int Binary; // [rsp+A0h] [rbp+30h] BYREF
  __int64 v21; // [rsp+B0h] [rbp+40h] BYREF

  CXLockContext::CXLockContext(
    (CXLockContext *)v18,
    (struct CStdComObjectRoot *)(((unsigned __int64)this + 32)
                               & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64)),
    (struct CCriticalSection **)(*((_QWORD *)this + 18) + 8LL),
    (const char *)this + 32);
  v21 = -1;
  if ( (bidGblFlags & 4) != 0 && off_18012ADD0 )
  {
    BidObjectID = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
    bidScopeEnterW(&v21, off_18012ADD0, BidObjectID, (unsigned int)a2, v17);
  }
  if ( !pvarg || a2 <= -2 )
  {
    Binary = -2146825287;
    if ( (unsigned int)CContext::Failed((CContext *)v18, &Binary) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_51;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
      {
        v7 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
        v8 = 1627145;
        LODWORD(v17) = 1589;
LABEL_10:
        bidTraceW(off_18012A210[0], v8, L"<CStream::Read|ADO|ERR> %u#, line %d\n", v7, v17);
        goto LABEL_45;
      }
      v9 = 1589;
      v10 = 1627145;
      goto LABEL_12;
    }
  }
  VariantClear(pvarg);
  if ( !*((_QWORD *)this + 21) )
  {
    Binary = -2146824584;
    if ( (unsigned int)CContext::Failed((CContext *)v18, &Binary) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_51;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
      {
        v7 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
        v8 = 1634313;
        LODWORD(v17) = 1596;
        goto LABEL_10;
      }
      v9 = 1596;
      v10 = 1634313;
      goto LABEL_12;
    }
  }
  if ( *((_DWORD *)this + 46) != 1 )
  {
    Binary = -2146825069;
    if ( (unsigned int)CContext::Failed((CContext *)v18, &Binary) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_51;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
      {
        v7 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
        v8 = 1650697;
        LODWORD(v17) = 1612;
        goto LABEL_10;
      }
      v9 = 1612;
      v10 = 1650697;
      goto LABEL_12;
    }
  }
  if ( (*((_DWORD *)this + 48) & 3) == 2 )
  {
    Binary = -2146825069;
    if ( (unsigned int)CContext::Failed((CContext *)v18, &Binary) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_51;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
      {
        v7 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
        v8 = 1655817;
        LODWORD(v17) = 1617;
        goto LABEL_10;
      }
      v9 = 1617;
      v10 = 1655817;
      goto LABEL_12;
    }
  }
  p_llVal = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)&pvarg->llVal;
  if ( a2 == -1 )
  {
    Binary = (*(__int64 (__fastcall **)(CStream *, CY *))(*(_QWORD *)this + 280LL))(this, &pvarg->cyVal);
    if ( (unsigned int)CContext::Failed((CContext *)v18, &Binary) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_51;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
      {
        v7 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
        v8 = 1660937;
        LODWORD(v17) = 1622;
        goto LABEL_10;
      }
      v9 = 1622;
      v10 = 1660937;
      goto LABEL_12;
    }
  }
  else
  {
    Binary = CStream::ReadBinary(this, a2, &pvarg->parray);
    if ( (unsigned int)CContext::Failed((CContext *)v18, &Binary) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_51;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
      {
        v7 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
        v8 = 1665033;
        LODWORD(v17) = 1626;
        goto LABEL_10;
      }
      v9 = 1626;
      v10 = 1665033;
LABEL_12:
      bidTraceW(off_18012A210[0], v10, L"<CStream::Read|ADO|ERR>  line %d\n", v9);
      goto LABEL_45;
    }
  }
  if ( *(_DWORD *)(p_llVal->llVal + 24) )
  {
    pvarg->vt = 8209;
  }
  else
  {
    SafeArrayDestroy(p_llVal->parray);
    p_llVal->llVal = 0;
    pvarg->vt = 1;
  }
LABEL_45:
  if ( (bidGblFlags & 2) != 0 )
  {
    if ( off_18012A960[0] )
    {
      v12 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
      bidTraceW(off_18012A210[0], 1682432, off_18012A960[0], v12, pvarg);
    }
    if ( (bidGblFlags & 2) != 0 && off_18012A920[0] )
    {
      v13 = v19;
      v14 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
      LODWORD(v17) = v13;
      bidTraceW(off_18012A210[0], 1684480, off_18012A920[0], v14, v17);
    }
  }
LABEL_51:
  if ( (bidGblFlags & 4) != 0 && v21 != -1 && bidID != -1 )
    ((void (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *))off_180121248[0])(bidID, 0, 0, &v21);
  v15 = v19;
  CXLockContext::~CXLockContext((CXLockContext *)v18);
  return v15;
}

```

## disassembly

```asm
0x1800bf180  mov     [rsp-28h+arg_8], rbx
0x1800bf185  mov     [rsp-28h+arg_18], rsi
0x1800bf18a  push    rbp
0x1800bf18b  push    rdi
0x1800bf18c  push    r13
0x1800bf18e  push    r14
0x1800bf190  push    r15
0x1800bf192  mov     rbp, rsp
0x1800bf195  sub     rsp, 70h
0x1800bf199  mov     r15, r8
0x1800bf19c  lea     r9, [rcx+20h]; char *
0x1800bf1a0  mov     r8, [rcx+90h]
0x1800bf1a7  mov     rax, rcx
0x1800bf1aa  mov     r14d, edx
0x1800bf1ad  add     r8, 8; struct CCriticalSection **
0x1800bf1b1  neg     rax
0x1800bf1b4  mov     rdi, rcx
0x1800bf1b7  lea     rcx, [rbp+var_40]; this
0x1800bf1bb  sbb     rdx, rdx
0x1800bf1be  and     rdx, r9; struct CStdComObjectRoot *
0x1800bf1c1  call    ??0CXLockContext@@QEAA@PEAVCStdComObjectRoot@@PEAPEAVCCriticalSection@@PEBD@Z; CXLockContext::CXLockContext(CStdComObjectRoot *,CCriticalSection * *,char const *)
0x1800bf1c6  test    byte ptr cs:_bidGblFlags, 4
0x1800bf1cd  mov     [rbp+arg_10], 0FFFFFFFFFFFFFFFFh
0x1800bf1d5  jz      short loc_1800BF205
0x1800bf1d7  mov     rax, cs:off_18012ADD0; "<CStream::Read|API|ADO> %u#, NumBytes: "...
0x1800bf1de  test    rax, rax
0x1800bf1e1  jz      short loc_1800BF205
0x1800bf1e3  lea     rcx, [rdi+98h]; this
0x1800bf1ea  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800bf1ef  mov     rdx, cs:off_18012ADD0; "<CStream::Read|API|ADO> %u#, NumBytes: "...
0x1800bf1f6  lea     rcx, [rbp+arg_10]
0x1800bf1fa  mov     r9d, r14d
0x1800bf1fd  mov     r8d, eax
0x1800bf200  call    _bidScopeEnterW
0x1800bf205  test    r15, r15
0x1800bf208  jz      short loc_1800BF214
0x1800bf20a  cmp     r14d, 0FFFFFFFEh
0x1800bf20e  jg      loc_1800BF2A1
0x1800bf214  lea     rdx, [rbp+arg_0]; int *
0x1800bf218  mov     [rbp+arg_0], 800A0BB9h
0x1800bf21f  lea     rcx, [rbp+var_40]; this
0x1800bf223  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800bf228  test    eax, eax
0x1800bf22a  jz      short loc_1800BF2A1
0x1800bf22c  mov     bl, 2
0x1800bf22e  test    byte ptr cs:_bidGblFlags, bl
0x1800bf234  jz      loc_1800BF592
0x1800bf23a  lea     rsi, [rdi+98h]
0x1800bf241  mov     rcx, rsi; this
0x1800bf244  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800bf249  cmp     eax, 0FFFFFFFFh
0x1800bf24c  jz      short loc_1800BF27E
0x1800bf24e  mov     rcx, rsi; this
0x1800bf251  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800bf256  mov     edx, 18D409h
0x1800bf25b  mov     dword ptr [rsp+70h+var_50], 635h
0x1800bf263  mov     rcx, cs:off_18012A210; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800bf26a  lea     r8, aCstreamReadAdo; "<CStream::Read|ADO|ERR> %u#, line %d\n"
0x1800bf271  mov     r9d, eax
0x1800bf274  call    _bidTraceW
0x1800bf279  jmp     loc_1800BF510
0x1800bf27e  mov     r9d, 635h
0x1800bf284  mov     edx, 18D409h
0x1800bf289  mov     rcx, cs:off_18012A210; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800bf290  lea     r8, aCstreamReadAdo_0; "<CStream::Read|ADO|ERR>  line %d\n"
0x1800bf297  call    _bidTraceW
0x1800bf29c  jmp     loc_1800BF510
0x1800bf2a1  mov     rcx, r15; pvarg
0x1800bf2a4  call    cs:__imp_VariantClear
0x1800bf2ab  nop     dword ptr [rax+rax+00h]
0x1800bf2b0  cmp     qword ptr [rdi+0A8h], 0
0x1800bf2b8  jnz     short loc_1800BF31E
0x1800bf2ba  lea     rdx, [rbp+arg_0]; int *
0x1800bf2be  mov     [rbp+arg_0], 800A0E78h
0x1800bf2c5  lea     rcx, [rbp+var_40]; this
0x1800bf2c9  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800bf2ce  test    eax, eax
0x1800bf2d0  jz      short loc_1800BF31E
0x1800bf2d2  mov     bl, 2
0x1800bf2d4  test    byte ptr cs:_bidGblFlags, bl
0x1800bf2da  jz      loc_1800BF592
0x1800bf2e0  lea     rsi, [rdi+98h]
0x1800bf2e7  mov     rcx, rsi; this
0x1800bf2ea  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800bf2ef  cmp     eax, 0FFFFFFFFh
0x1800bf2f2  jz      short loc_1800BF30E
0x1800bf2f4  mov     rcx, rsi; this
0x1800bf2f7  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800bf2fc  mov     edx, 18F009h
0x1800bf301  mov     dword ptr [rsp+70h+var_50], 63Ch
0x1800bf309  jmp     loc_1800BF263
0x1800bf30e  mov     r9d, 63Ch
0x1800bf314  mov     edx, 18F009h
0x1800bf319  jmp     loc_1800BF289
0x1800bf31e  mov     r13d, 1
0x1800bf324  mov     esi, 800A0C93h
0x1800bf329  cmp     [rdi+0B8h], r13d
0x1800bf330  jz      short loc_1800BF392
0x1800bf332  lea     rdx, [rbp+arg_0]; int *
0x1800bf336  mov     [rbp+arg_0], esi
0x1800bf339  lea     rcx, [rbp+var_40]; this
0x1800bf33d  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800bf342  test    eax, eax
0x1800bf344  jz      short loc_1800BF392
0x1800bf346  mov     bl, 2
0x1800bf348  test    byte ptr cs:_bidGblFlags, bl
0x1800bf34e  jz      loc_1800BF592
0x1800bf354  lea     rsi, [rdi+98h]
0x1800bf35b  mov     rcx, rsi; this
0x1800bf35e  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800bf363  cmp     eax, 0FFFFFFFFh
0x1800bf366  jz      short loc_1800BF382
0x1800bf368  mov     rcx, rsi; this
0x1800bf36b  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800bf370  mov     edx, 193009h
0x1800bf375  mov     dword ptr [rsp+70h+var_50], 64Ch
0x1800bf37d  jmp     loc_1800BF263
0x1800bf382  mov     r9d, 64Ch
0x1800bf388  mov     edx, 193009h
0x1800bf38d  jmp     loc_1800BF289
0x1800bf392  mov     eax, [rdi+0C0h]
0x1800bf398  mov     bl, 2
0x1800bf39a  and     al, 3
0x1800bf39c  cmp     al, bl
0x1800bf39e  jnz     short loc_1800BF3FE
0x1800bf3a0  lea     rdx, [rbp+arg_0]; int *
0x1800bf3a4  mov     [rbp+arg_0], esi
0x1800bf3a7  lea     rcx, [rbp+var_40]; this
0x1800bf3ab  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800bf3b0  test    eax, eax
0x1800bf3b2  jz      short loc_1800BF3FE
0x1800bf3b4  test    byte ptr cs:_bidGblFlags, bl
0x1800bf3ba  jz      loc_1800BF592
0x1800bf3c0  lea     rsi, [rdi+98h]
0x1800bf3c7  mov     rcx, rsi; this
0x1800bf3ca  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800bf3cf  cmp     eax, 0FFFFFFFFh
0x1800bf3d2  jz      short loc_1800BF3EE
0x1800bf3d4  mov     rcx, rsi; this
0x1800bf3d7  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800bf3dc  mov     edx, 194409h
0x1800bf3e1  mov     dword ptr [rsp+70h+var_50], 651h
0x1800bf3e9  jmp     loc_1800BF263
0x1800bf3ee  mov     r9d, 651h
0x1800bf3f4  mov     edx, 194409h
0x1800bf3f9  jmp     loc_1800BF289
0x1800bf3fe  lea     rsi, [r15+8]
0x1800bf402  mov     rcx, rdi; this
0x1800bf405  cmp     r14d, 0FFFFFFFFh
0x1800bf409  jnz     short loc_1800BF47F
0x1800bf40b  mov     rax, [rdi]
0x1800bf40e  mov     rdx, rsi
0x1800bf411  mov     rax, [rax+118h]
0x1800bf418  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf41d  lea     rdx, [rbp+arg_0]; int *
0x1800bf421  mov     [rbp+arg_0], eax
0x1800bf424  lea     rcx, [rbp+var_40]; this
0x1800bf428  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800bf42d  test    eax, eax
0x1800bf42f  jz      loc_1800BF4E8
0x1800bf435  test    byte ptr cs:_bidGblFlags, bl
0x1800bf43b  jz      loc_1800BF592
0x1800bf441  lea     rsi, [rdi+98h]
0x1800bf448  mov     rcx, rsi; this
0x1800bf44b  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800bf450  cmp     eax, 0FFFFFFFFh
0x1800bf453  jz      short loc_1800BF46F
0x1800bf455  mov     rcx, rsi; this
0x1800bf458  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800bf45d  mov     edx, 195809h
0x1800bf462  mov     dword ptr [rsp+70h+var_50], 656h
0x1800bf46a  jmp     loc_1800BF263
0x1800bf46f  mov     r9d, 656h
0x1800bf475  mov     edx, 195809h
0x1800bf47a  jmp     loc_1800BF289
0x1800bf47f  mov     r8, rsi; struct tagSAFEARRAY **
0x1800bf482  mov     edx, r14d; unsigned int
0x1800bf485  call    ?ReadBinary@CStream@@AEAAJKPEAPEAUtagSAFEARRAY@@@Z; CStream::ReadBinary(ulong,tagSAFEARRAY * *)
0x1800bf48a  lea     rdx, [rbp+arg_0]; int *
0x1800bf48e  mov     [rbp+arg_0], eax
0x1800bf491  lea     rcx, [rbp+var_40]; this
0x1800bf495  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800bf49a  test    eax, eax
0x1800bf49c  jz      short loc_1800BF4E8
0x1800bf49e  test    byte ptr cs:_bidGblFlags, bl
0x1800bf4a4  jz      loc_1800BF592
0x1800bf4aa  lea     rsi, [rdi+98h]
0x1800bf4b1  mov     rcx, rsi; this
0x1800bf4b4  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800bf4b9  cmp     eax, 0FFFFFFFFh
0x1800bf4bc  jz      short loc_1800BF4D8
0x1800bf4be  mov     rcx, rsi; this
0x1800bf4c1  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800bf4c6  mov     edx, 196809h
0x1800bf4cb  mov     dword ptr [rsp+70h+var_50], 65Ah
0x1800bf4d3  jmp     loc_1800BF263
0x1800bf4d8  mov     r9d, 65Ah
0x1800bf4de  mov     edx, 196809h
0x1800bf4e3  jmp     loc_1800BF289
0x1800bf4e8  mov     rcx, [rsi]; psa
0x1800bf4eb  cmp     dword ptr [rcx+18h], 0
0x1800bf4ef  jz      short loc_1800BF4F9
0x1800bf4f1  mov     word ptr [r15], 2011h
0x1800bf4f7  jmp     short loc_1800BF510
0x1800bf4f9  call    cs:__imp_SafeArrayDestroy
0x1800bf500  nop     dword ptr [rax+rax+00h]
0x1800bf505  mov     qword ptr [rsi], 0
0x1800bf50c  mov     [r15], r13w
0x1800bf510  test    byte ptr cs:_bidGblFlags, bl
0x1800bf516  jz      short loc_1800BF592
0x1800bf518  mov     rax, cs:off_18012A960; "<CStream::Read|REG|ADO> %u#, return val"...
0x1800bf51f  test    rax, rax
0x1800bf522  jz      short loc_1800BF550
0x1800bf524  lea     rcx, [rdi+98h]; this
0x1800bf52b  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800bf530  mov     r8, cs:off_18012A960; "<CStream::Read|REG|ADO> %u#, return val"...
0x1800bf537  mov     r9d, eax
0x1800bf53a  mov     rcx, cs:off_18012A210; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800bf541  mov     edx, 19AC00h
0x1800bf546  mov     [rsp+70h+var_50], r15
0x1800bf54b  call    _bidTraceW
0x1800bf550  test    byte ptr cs:_bidGblFlags, bl
0x1800bf556  jz      short loc_1800BF592
0x1800bf558  mov     rax, cs:off_18012A920; "<CStream::Read|API|ADO|RET> %u#, HRESUL"...
0x1800bf55f  test    rax, rax
0x1800bf562  jz      short loc_1800BF592
0x1800bf564  mov     ebx, [rbp+var_18]
0x1800bf567  lea     rcx, [rdi+98h]; this
0x1800bf56e  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800bf573  mov     r8, cs:off_18012A920; "<CStream::Read|API|ADO|RET> %u#, HRESUL"...
0x1800bf57a  mov     r9d, eax
0x1800bf57d  mov     rcx, cs:off_18012A210; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800bf584  mov     edx, 19B400h
0x1800bf589  mov     dword ptr [rsp+70h+var_50], ebx
0x1800bf58d  call    _bidTraceW
0x1800bf592  test    byte ptr cs:_bidGblFlags, 4
0x1800bf599  jz      short loc_1800BF5C4
0x1800bf59b  cmp     [rbp+arg_10], 0FFFFFFFFFFFFFFFFh
0x1800bf5a0  jz      short loc_1800BF5C4
0x1800bf5a2  mov     rcx, cs:_bidID
0x1800bf5a9  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800bf5ad  jz      short loc_1800BF5C4
0x1800bf5af  mov     rax, cs:off_180121248
0x1800bf5b6  lea     r9, [rbp+arg_10]
0x1800bf5ba  xor     r8d, r8d
0x1800bf5bd  xor     edx, edx
0x1800bf5bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf5c4  mov     ebx, [rbp+var_18]
0x1800bf5c7  lea     rcx, [rbp+var_40]; this
0x1800bf5cb  call    ??1CXLockContext@@QEAA@XZ; CXLockContext::~CXLockContext(void)
0x1800bf5d0  lea     r11, [rsp+70h+var_s0]
0x1800bf5d5  mov     eax, ebx
0x1800bf5d7  mov     rbx, [r11+38h]
0x1800bf5db  mov     rsi, [r11+48h]
0x1800bf5df  mov     rsp, r11
0x1800bf5e2  pop     r15
0x1800bf5e4  pop     r14
0x1800bf5e6  pop     r13
0x1800bf5e8  pop     rdi
0x1800bf5e9  pop     rbp
0x1800bf5ea  retn
```
