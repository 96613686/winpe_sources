# CStream::ReadLine(ushort * *)

- ea: `0x1800bfd00`
- end: `0x1800c072a`
- name: `?ReadLine@CStream@@EEAAJPEAPEAG@Z`
- size: `2602`
- prototype: `__int64 __fastcall(CStream *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `20`
- tags: `broker_com_uri`

## callees

- `0x180020e20`
- `0x180031760`
- `0x180032710`
- `0x18004f2b0`
- `0x180054098`
- `0x18006a22c`
- `0x1800bc204`
- `0x1800bc238`
- `0x1800bc554`
- `0x1800bc878`
- `0x1800bd930`
- `0x1800bdbec`
- `0x1800bfd00`
- `0x1800c1860`
- `0x1800c4538`
- `0x1800c8f34`
- `0x1800cdad2`
- `0x1800cdb20`
- `0x1800cdbe0`
- `0x1800d0010`

## import_xrefs

- `msvcrt!wcsstr` at `0x1800c0153`
- `msvcrt!wcsstr` at `0x1800c0153`
- `MSDART!MpHeapFree` at `0x1800c06e5`
- `MSDART!MpHeapFree` at `0x1800c06e5`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800c05ed`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800c0661`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800c05ed`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800c0661`

## string_xrefs

- `0x1800bfdeb`: `<CStream::ReadLine|ADO|ERR> %u#, line %d\n`
- `0x1800c00a6`: `<CStream::ReadLine|ADO|ERR> %u#, line %d\n`
- `0x1800bfe11`: `<CStream::ReadLine|ADO|ERR>  line %d\n`
- `0x1800c06ca`: `<CStream::ReadLine|ADO|ERR>  line %d\n`

## pseudocode

```c
__int64 __fastcall CStream::ReadLine(CStream *this, unsigned __int16 **a2)
{
  __int64 v2; // r8
  unsigned int v4; // eax
  int v5; // r14d
  unsigned int BidObjectID; // eax
  __int64 v7; // rdx
  __int64 v8; // r9
  __int64 v9; // rdx
  char v10; // bl
  CStream *v11; // rcx
  void *v12; // r12
  unsigned int v13; // r11d
  wchar_t *v14; // rsi
  unsigned int v15; // r15d
  int v16; // r13d
  int v17; // r8d
  int v18; // r11d
  int v19; // r11d
  unsigned int v20; // r8d
  __int64 v21; // rcx
  unsigned int v22; // eax
  __int64 v23; // rdx
  __int64 v24; // r9
  int v25; // r10d
  char *v26; // rbx
  wchar_t *v27; // rdx
  __int64 v28; // r9
  __int64 v29; // rdx
  unsigned int v30; // r9d
  __int64 v31; // rax
  unsigned int v32; // r8d
  int v33; // edx
  __int64 v34; // rcx
  unsigned __int16 **v35; // rbx
  BSTR v36; // rax
  BSTR v37; // rax
  unsigned int v38; // ebx
  unsigned __int16 *v40; // [rsp+20h] [rbp-E0h]
  int v41; // [rsp+20h] [rbp-E0h]
  unsigned int v42; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v43; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int v44; // [rsp+58h] [rbp-A8h]
  size_t Size; // [rsp+5Ch] [rbp-A4h] BYREF
  unsigned int v46; // [rsp+64h] [rbp-9Ch] BYREF
  int v47; // [rsp+68h] [rbp-98h] BYREF
  wchar_t *SubStr; // [rsp+70h] [rbp-90h] BYREF
  __int64 v49; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v50; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v51[40]; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v52; // [rsp+B0h] [rbp-50h]
  unsigned __int8 *v53; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 **v54; // [rsp+C8h] [rbp-38h]
  unsigned __int8 v55[2048]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 Src[8192]; // [rsp+8D0h] [rbp+7D0h] BYREF

  v2 = *((_QWORD *)this + 18);
  v54 = a2;
  CXLockContext::CXLockContext(
    (CXLockContext *)v51,
    (struct CStdComObjectRoot *)(((unsigned __int64)this + 32)
                               & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64)),
    (struct CCriticalSection **)(v2 + 8),
    (const char *)this + 32);
  v4 = *((_DWORD *)this + 58);
  v5 = 0;
  v46 = 0;
  v44 = 0;
  Size = 0;
  v49 = 0;
  v50 = v4;
  if ( !*((_QWORD *)this + 21) )
  {
    v42 = -2146824584;
    if ( (unsigned int)CContext::Failed((CContext *)v51, (const int *)&v42) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_109;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
      {
        BidObjectID = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
        v7 = 1722377;
        v41 = 1682;
LABEL_6:
        bidTraceW(off_18012A210[0], v7, L"<CStream::ReadLine|ADO|ERR> %u#, line %d\n", BidObjectID, v41);
        goto LABEL_109;
      }
      v8 = 1682;
      v9 = 1722377;
      goto LABEL_8;
    }
  }
  v42 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int64 *))(**((_QWORD **)this + 21) + 40LL))(
          *((_QWORD *)this + 21),
          0,
          1,
          &v49);
  if ( (unsigned int)CContext::Failed((CContext *)v51, (const int *)&v42) )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_109;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
    {
      BidObjectID = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
      v7 = 1738761;
      v41 = 1698;
      goto LABEL_6;
    }
    v8 = 1698;
    v9 = 1738761;
LABEL_8:
    bidTraceW(off_18012A210[0], v9, L"<CStream::ReadLine|ADO|ERR>  line %d\n", v8);
    goto LABEL_109;
  }
  if ( HIDWORD(v49) || (v10 = 1, (_DWORD)v49) )
    v10 = 0;
  v42 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int8 *, __int64, char *))(**((_QWORD **)this + 21) + 24LL))(
          *((_QWORD *)this + 21),
          v55,
          2048,
          (char *)&Size + 4);
  if ( (unsigned int)CContext::Failed((CContext *)v51, (const int *)&v42) )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_109;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
    {
      BidObjectID = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
      v7 = 1741833;
      v41 = 1701;
      goto LABEL_6;
    }
    v8 = 1701;
    v9 = 1741833;
    goto LABEL_8;
  }
  v12 = 0;
  v13 = HIDWORD(Size);
  v14 = 0;
  v15 = 0;
  v16 = 0;
  if ( *((_DWORD *)this + 54) == 1200
    && v10
    && HIDWORD(Size) >= 2
    && CStream::CheckUnicodeByteOrderMark(v11, v55, (CStream *)((char *)this + 220)) )
  {
    v5 = 2;
    LODWORD(v49) = 2;
  }
  else if ( *((_DWORD *)this + 54) == 65001 && v10 && v13 >= 3 && (unsigned int)CheckUTF8Mark(v55) )
  {
    v5 = v17;
    LODWORD(v49) = v17;
  }
  v47 = *((_DWORD *)this + 54);
  SubStr = (wchar_t *)CStream::strEOL(this, 1);
  v53 = (unsigned __int8 *)Src;
  while ( 1 )
  {
    v19 = v18 - v5;
    if ( !v19 )
      goto LABEL_94;
    if ( !(v19 + v15) )
      goto LABEL_44;
    v20 = *((_DWORD *)this + 54);
    v46 = v19 + v15;
    LODWORD(Size) = 0x2000;
    v43 = CStream::ConvertString(this, &v50, v20, 0x4B0u, &v55[v5], (int *)&v46, &v53, (int *)&Size);
    if ( v43 == -2146825037 )
    {
      if ( (unsigned int)CContext::FailedDescription((CContext *)v51, (const int *)&v43, 0x272Eu) )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_107;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) == -1 )
        {
          v28 = 1731;
          v29 = 1772553;
          goto LABEL_106;
        }
        v22 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
        v23 = 1772553;
        LODWORD(v40) = 1731;
        goto LABEL_40;
      }
    }
    else if ( (unsigned int)CContext::Failed((CContext *)v51, (const int *)&v43) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_107;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) == -1 )
      {
        v28 = 1733;
        v29 = 1774601;
        goto LABEL_106;
      }
      v22 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
      v23 = 1774601;
      LODWORD(v40) = 1733;
LABEL_40:
      bidTraceW(off_18012A210[0], v23, L"<CStream::ReadLine|ADO|ERR> %u#, line %d\n", v22, v40);
      goto LABEL_107;
    }
    v24 = *((unsigned int *)this + 55);
    if ( (_DWORD)v24 )
      CStream::TranslateByteOrder(v21, Src, (unsigned int)Size, v24, 0);
    else
LABEL_44:
      v25 = Size;
    v26 = (char *)MEMREALLOC(v12, v25 + v44 + 2LL);
    if ( (unsigned int)CContext::MemFailed((CContext *)v51, v26) )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
        {
          v22 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
          v23 = 1781769;
          LODWORD(v40) = 1740;
          goto LABEL_40;
        }
        v28 = 1740;
        v29 = 1781769;
        goto LABEL_106;
      }
      goto LABEL_107;
    }
    v12 = v26;
    memcpy_0(&v26[v44], Src, (unsigned int)Size);
    v27 = SubStr;
    v44 += Size;
    *(_WORD *)&v26[v44] = 0;
    v14 = wcsstr((const wchar_t *)v26, v27);
    if ( v14 )
      break;
    if ( HIDWORD(Size) < 2048 - v15 )
      goto LABEL_94;
    if ( v47 == 50220 )
      v16 += v46;
    v15 += HIDWORD(Size) - v5 - v46;
    if ( v15 > 0x800 )
    {
      v42 = -2147024882;
      if ( (unsigned int)CContext::Failed((CContext *)v51, (const int *)&v42) )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
          {
            v22 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
            v23 = 1806345;
            LODWORD(v40) = 1764;
            goto LABEL_40;
          }
          v28 = 1764;
          v29 = 1806345;
LABEL_106:
          bidTraceW(off_18012A210[0], v29, L"<CStream::ReadLine|ADO|ERR>  line %d\n", v28);
        }
        goto LABEL_107;
      }
    }
    memcpy_0(v55, (char *)Src - v15, v15);
    v42 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int8 *, _QWORD, char *))(**((_QWORD **)this + 21) + 24LL))(
            *((_QWORD *)this + 21),
            &v55[v15],
            2048 - v15,
            (char *)&Size + 4);
    if ( (unsigned int)CContext::Failed((CContext *)v51, (const int *)&v42) )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
        {
          v22 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
          v23 = 1810441;
          LODWORD(v40) = 1768;
          goto LABEL_40;
        }
        v28 = 1768;
        v29 = 1810441;
        goto LABEL_106;
      }
      goto LABEL_107;
    }
    v18 = HIDWORD(Size);
    v5 = 0;
  }
  v30 = *((_DWORD *)this + 54);
  v43 = 0;
  v42 = 0;
  v31 = -1;
  do
    ++v31;
  while ( SubStr[v31] );
  if ( v30 == 1200 )
  {
    v32 = (_DWORD)v14 + 2 * v31 - (_DWORD)v26;
    v43 = v32;
LABEL_85:
    LODWORD(SubStr) = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))(**((_QWORD **)this + 21) + 40LL))(
                        *((_QWORD *)this + 21),
                        v49 + v32,
                        0,
                        0);
    if ( (unsigned int)CContext::Failed((CContext *)v51, (const int *)&SubStr) )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
        {
          v22 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
          v23 = 1868809;
          LODWORD(v40) = 1825;
          goto LABEL_40;
        }
        v28 = 1825;
        v29 = 1868809;
        goto LABEL_106;
      }
    }
    else
    {
LABEL_94:
      v35 = v54;
      if ( v54 )
      {
        if ( v14 )
        {
          v37 = SysAllocStringLen((const OLECHAR *)v12, ((char *)v14 - (_BYTE *)v12) >> 1);
          *v35 = v37;
          if ( (unsigned int)CContext::MemFailed((CContext *)v51, v37) && (bidGblFlags & 2) != 0 )
          {
            if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
            {
              v22 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
              v23 = 1877001;
              LODWORD(v40) = 1833;
              goto LABEL_40;
            }
            v28 = 1833;
            v29 = 1877001;
            goto LABEL_106;
          }
        }
        else
        {
          v36 = SysAllocStringLen((const OLECHAR *)v12, v44 >> 1);
          *v35 = v36;
          if ( (unsigned int)CContext::MemFailed((CContext *)v51, v36) && (bidGblFlags & 2) != 0 )
          {
            if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
            {
              v22 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
              v23 = 1874953;
              LODWORD(v40) = 1831;
              goto LABEL_40;
            }
            v28 = 1831;
            v29 = 1874953;
            goto LABEL_106;
          }
        }
      }
    }
  }
  else
  {
    v33 = (_DWORD)v14 - (_DWORD)v26;
    if ( v47 == 50220 )
    {
      v47 = 0;
      LODWORD(SubStr) = CStream::ConvertEscapedString(
                          this,
                          &v42,
                          0,
                          v30,
                          Src,
                          (unsigned __int8)Size + v33 + 2 * (unsigned __int8)v31 - (unsigned __int8)v44,
                          v55,
                          v46,
                          &v43,
                          (enum ESCAPEMODE *)&v47);
      if ( !(unsigned int)CContext::Failed((CContext *)v51, (const int *)&SubStr) )
      {
        v32 = v16 + v43;
        v43 += v16;
        if ( v47 )
          *((_DWORD *)this + 58) = EscMode(*((unsigned int *)this + 54));
        goto LABEL_85;
      }
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
        {
          v22 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
          v23 = 1845257;
          LODWORD(v40) = 1802;
          goto LABEL_40;
        }
        v28 = 1802;
        v29 = 1845257;
        goto LABEL_106;
      }
    }
    else
    {
      v34 = *((_QWORD *)this + 28);
      v44 = v33 + 2 * v31;
      HIDWORD(v40) = HIDWORD(v26);
      LODWORD(SubStr) = (*(__int64 (__fastcall **)(__int64, unsigned int *, __int64))(*(_QWORD *)v34 + 72LL))(
                          v34,
                          &v42,
                          1200);
      if ( !(unsigned int)CContext::Failed((CContext *)v51, (const int *)&SubStr) )
      {
        v32 = v43;
        goto LABEL_85;
      }
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
        {
          v22 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
          v23 = 1863689;
          LODWORD(v40) = 1820;
          goto LABEL_40;
        }
        v28 = 1820;
        v29 = 1863689;
        goto LABEL_106;
      }
    }
  }
LABEL_107:
  if ( v12 )
    MpHeapFree(g_hHeapHandle, v12);
LABEL_109:
  v38 = v52;
  CXLockContext::~CXLockContext((CXLockContext *)v51);
  return v38;
}

```

## disassembly

```asm
0x1800bfd00  mov     [rsp-8+arg_10], rbx
0x1800bfd05  push    rbp
0x1800bfd06  push    rsi
0x1800bfd07  push    rdi
0x1800bfd08  push    r12
0x1800bfd0a  push    r13
0x1800bfd0c  push    r14
0x1800bfd0e  push    r15
0x1800bfd10  lea     rbp, [rsp-47E0h]
0x1800bfd18  mov     eax, 48E0h
0x1800bfd1d  call    _alloca_probe
0x1800bfd22  sub     rsp, rax
0x1800bfd25  mov     rax, cs:__security_cookie
0x1800bfd2c  xor     rax, rsp
0x1800bfd2f  mov     [rbp+4810h+var_40], rax
0x1800bfd36  mov     r8, [rcx+90h]
0x1800bfd3d  lea     r9, [rcx+20h]; char *
0x1800bfd41  mov     rax, rcx
0x1800bfd44  mov     [rbp+4810h+var_4848], rdx
0x1800bfd48  add     r8, 8; struct CCriticalSection **
0x1800bfd4c  mov     rdi, rcx
0x1800bfd4f  neg     rax
0x1800bfd52  lea     rcx, [rbp+4810h+var_4888]; this
0x1800bfd56  sbb     rdx, rdx
0x1800bfd59  and     rdx, r9; struct CStdComObjectRoot *
0x1800bfd5c  call    ??0CXLockContext@@QEAA@PEAVCStdComObjectRoot@@PEAPEAVCCriticalSection@@PEBD@Z; CXLockContext::CXLockContext(CStdComObjectRoot *,CCriticalSection * *,char const *)
0x1800bfd61  mov     eax, [rdi+0E8h]
0x1800bfd67  xor     r14d, r14d
0x1800bfd6a  mov     [rsp+4910h+var_48AC], r14d
0x1800bfd6f  mov     dword ptr [rsp+4910h+Size+4], r14d
0x1800bfd74  mov     [rsp+4910h+var_48B8], r14d
0x1800bfd79  mov     dword ptr [rsp+4910h+Size], r14d
0x1800bfd7e  mov     [rsp+4910h+var_4898], r14
0x1800bfd83  mov     [rbp+4810h+var_4890], eax
0x1800bfd86  cmp     [rdi+0A8h], r14
0x1800bfd8d  jnz     loc_1800BFE22
0x1800bfd93  lea     rdx, [rsp+4910h+var_48C0]; int *
0x1800bfd98  mov     [rsp+4910h+var_48C0], 800A0E78h
0x1800bfda0  lea     rcx, [rbp+4810h+var_4888]; this
0x1800bfda4  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800bfda9  test    eax, eax
0x1800bfdab  jz      short loc_1800BFE22
0x1800bfdad  test    byte ptr cs:_bidGblFlags, 2
0x1800bfdb4  jz      loc_1800C06F1
0x1800bfdba  lea     rcx, [rdi+98h]; this
0x1800bfdc1  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800bfdc6  cmp     eax, 0FFFFFFFFh
0x1800bfdc9  jz      short loc_1800BFDFF
0x1800bfdcb  lea     rcx, [rdi+98h]; this
0x1800bfdd2  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800bfdd7  mov     edx, 1A4809h
0x1800bfddc  mov     dword ptr [rsp+4910h+var_48F0], 692h
0x1800bfde4  mov     rcx, cs:off_18012A210; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800bfdeb  lea     r8, aCstreamReadlin_0; "<CStream::ReadLine|ADO|ERR> %u#, line %"...
0x1800bfdf2  mov     r9d, eax
0x1800bfdf5  call    _bidTraceW
0x1800bfdfa  jmp     loc_1800C06F1
0x1800bfdff  mov     r9d, 692h
0x1800bfe05  mov     edx, 1A4809h
0x1800bfe0a  mov     rcx, cs:off_18012A210; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800bfe11  lea     r8, aCstreamReadlin; "<CStream::ReadLine|ADO|ERR>  line %d\n"
0x1800bfe18  call    _bidTraceW
0x1800bfe1d  jmp     loc_1800C06F1
0x1800bfe22  mov     rcx, [rdi+0A8h]
0x1800bfe29  lea     r9, [rsp+4910h+var_4898]
0x1800bfe2e  mov     rdx, r14
0x1800bfe31  mov     r8d, 1
0x1800bfe37  mov     rax, [rcx]
0x1800bfe3a  mov     rax, [rax+28h]
0x1800bfe3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bfe43  lea     rdx, [rsp+4910h+var_48C0]; int *
0x1800bfe48  mov     [rsp+4910h+var_48C0], eax
0x1800bfe4c  lea     rcx, [rbp+4810h+var_4888]; this
0x1800bfe50  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800bfe55  test    eax, eax
0x1800bfe57  jz      short loc_1800BFEA5
0x1800bfe59  test    byte ptr cs:_bidGblFlags, 2
0x1800bfe60  jz      loc_1800C06F1
0x1800bfe66  lea     rcx, [rdi+98h]; this
0x1800bfe6d  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800bfe72  cmp     eax, 0FFFFFFFFh
0x1800bfe75  jz      short loc_1800BFE95
0x1800bfe77  lea     rcx, [rdi+98h]; this
0x1800bfe7e  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800bfe83  mov     edx, 1A8809h
0x1800bfe88  mov     dword ptr [rsp+4910h+var_48F0], 6A2h
0x1800bfe90  jmp     loc_1800BFDE4
0x1800bfe95  mov     r9d, 6A2h
0x1800bfe9b  mov     edx, 1A8809h
0x1800bfea0  jmp     loc_1800BFE0A
0x1800bfea5  cmp     dword ptr [rsp+4910h+var_4898+4], r14d
0x1800bfeaa  jnz     short loc_1800BFEB5
0x1800bfeac  mov     bl, 1
0x1800bfeae  cmp     dword ptr [rsp+4910h+var_4898], r14d
0x1800bfeb3  jz      short loc_1800BFEB8
0x1800bfeb5  mov     bl, r14b
0x1800bfeb8  mov     rcx, [rdi+0A8h]
0x1800bfebf  lea     r9, [rsp+4910h+Size+4]
0x1800bfec4  mov     r8d, 800h
0x1800bfeca  lea     rdx, [rbp+4810h+var_4840]
0x1800bfece  mov     rax, [rcx]
0x1800bfed1  mov     rax, [rax+18h]
0x1800bfed5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bfeda  lea     rdx, [rsp+4910h+var_48C0]; int *
0x1800bfedf  mov     [rsp+4910h+var_48C0], eax
0x1800bfee3  lea     rcx, [rbp+4810h+var_4888]; this
0x1800bfee7  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800bfeec  test    eax, eax
0x1800bfeee  jz      short loc_1800BFF3C
0x1800bfef0  test    byte ptr cs:_bidGblFlags, 2
0x1800bfef7  jz      loc_1800C06F1
0x1800bfefd  lea     rcx, [rdi+98h]; this
0x1800bff04  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800bff09  cmp     eax, 0FFFFFFFFh
0x1800bff0c  jz      short loc_1800BFF2C
0x1800bff0e  lea     rcx, [rdi+98h]; this
0x1800bff15  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800bff1a  mov     edx, 1A9409h
0x1800bff1f  mov     dword ptr [rsp+4910h+var_48F0], 6A5h
0x1800bff27  jmp     loc_1800BFDE4
0x1800bff2c  mov     r9d, 6A5h
0x1800bff32  mov     edx, 1A9409h
0x1800bff37  jmp     loc_1800BFE0A
0x1800bff3c  cmp     dword ptr [rdi+0D8h], 4B0h
0x1800bff46  mov     r12, r14
0x1800bff49  mov     r11d, dword ptr [rsp+4910h+Size+4]
0x1800bff4e  mov     rsi, r14
0x1800bff51  mov     r15d, r14d
0x1800bff54  mov     r13d, r14d
0x1800bff57  jnz     short loc_1800BFF84
0x1800bff59  test    bl, bl
0x1800bff5b  jz      short loc_1800BFF84
0x1800bff5d  cmp     r11d, 2
0x1800bff61  jb      short loc_1800BFF84
0x1800bff63  lea     r8, [rdi+0DCh]; enum BYTEORDER *
0x1800bff6a  lea     rdx, [rbp+4810h+var_4840]; unsigned __int8 *
0x1800bff6e  call    ?CheckUnicodeByteOrderMark@CStream@@QEAA_NPEAEPEAW4BYTEORDER@@@Z; CStream::CheckUnicodeByteOrderMark(uchar *,BYTEORDER *)
0x1800bff73  test    al, al
0x1800bff75  jz      short loc_1800BFF84
0x1800bff77  mov     r14d, 2
0x1800bff7d  mov     dword ptr [rsp+4910h+var_4898], r14d
0x1800bff82  jmp     short loc_1800BFFB4
0x1800bff84  cmp     dword ptr [rdi+0D8h], 0FDE9h
0x1800bff8e  jnz     short loc_1800BFFB4
0x1800bff90  test    bl, bl
0x1800bff92  jz      short loc_1800BFFB4
0x1800bff94  mov     r8d, 3
0x1800bff9a  cmp     r11d, r8d
0x1800bff9d  jb      short loc_1800BFFB4
0x1800bff9f  lea     rcx, [rbp+4810h+var_4840]; unsigned __int8 *
0x1800bffa3  call    ?CheckUTF8Mark@@YAHPEAE@Z; CheckUTF8Mark(uchar *)
0x1800bffa8  test    eax, eax
0x1800bffaa  jz      short loc_1800BFFB4
0x1800bffac  mov     r14d, r8d
0x1800bffaf  mov     dword ptr [rsp+4910h+var_4898], r8d
0x1800bffb4  mov     eax, [rdi+0D8h]
0x1800bffba  mov     edx, 1; int
0x1800bffbf  mov     rcx, rdi; this
0x1800bffc2  mov     [rsp+4910h+var_48A8], eax
0x1800bffc6  call    ?strEOL@CStream@@AEAAPEAEH@Z; CStream::strEOL(int)
0x1800bffcb  mov     [rsp+4910h+SubStr], rax
0x1800bffd0  lea     rax, [rbp+4810h+Src]
0x1800bffd7  mov     [rbp+4810h+var_4850], rax
0x1800bffdb  sub     r11d, r14d
0x1800bffde  jz      loc_1800C05D2
0x1800bffe4  lea     ecx, [r11+r15]
0x1800bffe8  test    ecx, ecx
0x1800bffea  jz      loc_1800C00EF
0x1800bfff0  mov     r8d, [rdi+0D8h]; unsigned int
0x1800bfff7  lea     rdx, [rbp+4810h+var_4890]; unsigned int *
0x1800bfffb  mov     [rsp+4910h+var_48AC], ecx
0x1800bffff  mov     r9d, 4B0h; unsigned int
0x1800c0005  mov     eax, r14d
0x1800c0008  lea     rcx, [rbp+4810h+var_4840]
0x1800c000c  add     rcx, rax
0x1800c000f  mov     dword ptr [rsp+4910h+Size], 2000h
0x1800c0017  lea     rax, [rsp+4910h+Size]
0x1800c001c  mov     [rsp+4910h+var_48D8], rax; int *
0x1800c0021  lea     rax, [rbp+4810h+var_4850]
0x1800c0025  mov     [rsp+4910h+var_48E0], rax; unsigned __int8 **
0x1800c002a  lea     rax, [rsp+4910h+var_48AC]
0x1800c002f  mov     [rsp+4910h+var_48E8], rax; int *
0x1800c0034  mov     [rsp+4910h+var_48F0], rcx; Src
0x1800c0039  mov     rcx, rdi; this
0x1800c003c  call    ?ConvertString@CStream@@AEAAJPEAKKKPEAEPEAHPEAPEAE2@Z; CStream::ConvertString(ulong *,ulong,ulong,uchar *,int *,uchar * *,int *)
0x1800c0041  mov     [rsp+4910h+var_48BC], eax
0x1800c0045  lea     rdx, [rsp+4910h+var_48BC]; int *
0x1800c004a  lea     rcx, [rbp+4810h+var_4888]; this
0x1800c004e  cmp     eax, 800A0CB3h
0x1800c0053  jnz     short loc_1800C00BA
0x1800c0055  mov     r8d, 272Eh; unsigned int
0x1800c005b  call    ?FailedDescription@CContext@@QEAAHAEBJK@Z; CContext::FailedDescription(long const &,ulong)
0x1800c0060  test    eax, eax
0x1800c0062  jz      short loc_1800C00C7
0x1800c0064  test    byte ptr cs:_bidGblFlags, 2
0x1800c006b  jz      loc_1800C06D6
0x1800c0071  lea     rcx, [rdi+98h]; this
0x1800c0078  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800c007d  cmp     eax, 0FFFFFFFFh
0x1800c0080  jz      loc_1800C0229
0x1800c0086  lea     rcx, [rdi+98h]; this
0x1800c008d  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800c0092  mov     edx, 1B0C09h
0x1800c0097  mov     dword ptr [rsp+4910h+var_48F0], 6C3h
0x1800c009f  mov     rcx, cs:off_18012A210; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800c00a6  lea     r8, aCstreamReadlin_0; "<CStream::ReadLine|ADO|ERR> %u#, line %"...
0x1800c00ad  mov     r9d, eax
0x1800c00b0  call    _bidTraceW
0x1800c00b5  jmp     loc_1800C06D6
0x1800c00ba  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800c00bf  test    eax, eax
0x1800c00c1  jnz     loc_1800C0239
0x1800c00c7  mov     r9d, [rdi+0DCh]
0x1800c00ce  xor     eax, eax
0x1800c00d0  test    r9d, r9d
0x1800c00d3  jz      short loc_1800C00EF
0x1800c00d5  mov     r10d, dword ptr [rsp+4910h+Size]
0x1800c00da  lea     rdx, [rbp+4810h+Src]
0x1800c00e1  mov     r8d, r10d
0x1800c00e4  mov     dword ptr [rsp+4910h+var_48F0], eax
0x1800c00e8  call    ?TranslateByteOrder@CStream@@QEAAXPEAEKW4BYTEORDER@@1@Z; CStream::TranslateByteOrder(uchar *,ulong,BYTEORDER,BYTEORDER)
0x1800c00ed  jmp     short loc_1800C00F4
0x1800c00ef  mov     r10d, dword ptr [rsp+4910h+Size]
0x1800c00f4  mov     edx, [rsp+4910h+var_48B8]
0x1800c00f8  mov     rcx, r12; void *
0x1800c00fb  add     edx, r10d
0x1800c00fe  add     rdx, 2; unsigned __int64
0x1800c0102  call    ?MEMREALLOC@@YAPEAXPEAX_K@Z; MEMREALLOC(void *,unsigned __int64)
0x1800c0107  mov     rdx, rax; void *
0x1800c010a  lea     rcx, [rbp+4810h+var_4888]; this
0x1800c010e  mov     rbx, rax
0x1800c0111  call    ?MemFailed@CContext@@QEAAHPEAX@Z; CContext::MemFailed(void *)
0x1800c0116  xor     esi, esi
0x1800c0118  test    eax, eax
0x1800c011a  jnz     loc_1800C0586
0x1800c0120  mov     ecx, [rsp+4910h+var_48B8]
0x1800c0124  lea     rdx, [rbp+4810h+Src]; Src
0x1800c012b  mov     r8d, dword ptr [rsp+4910h+Size]; Size
0x1800c0130  add     rcx, rbx; void *
0x1800c0133  mov     r12, rbx
0x1800c0136  call    memcpy_0
0x1800c013b  mov     eax, [rsp+4910h+var_48B8]
0x1800c013f  mov     rcx, rbx; Str
0x1800c0142  add     eax, dword ptr [rsp+4910h+Size]
0x1800c0146  mov     rdx, [rsp+4910h+SubStr]; SubStr
0x1800c014b  mov     [rsp+4910h+var_48B8], eax
0x1800c014f  mov     [rax+rbx], si
0x1800c0153  call    cs:__imp_wcsstr
0x1800c015a  nop     dword ptr [rax+rax+00h]
0x1800c015f  mov     rsi, rax
0x1800c0162  xor     eax, eax
0x1800c0164  test    rsi, rsi
0x1800c0167  jnz     loc_1800C031D
0x1800c016d  mov     eax, dword ptr [rsp+4910h+Size+4]
0x1800c0171  mov     edx, 800h
0x1800c0176  mov     ecx, edx
0x1800c0178  sub     ecx, r15d
0x1800c017b  cmp     eax, ecx
0x1800c017d  jb      loc_1800C05D2
0x1800c0183  cmp     [rsp+4910h+var_48A8], 0C42Ch
0x1800c018b  jnz     short loc_1800C0192
0x1800c018d  add     r13d, [rsp+4910h+var_48AC]
0x1800c0192  sub     eax, r14d
0x1800c0195  sub     eax, [rsp+4910h+var_48AC]
0x1800c0199  add     r15d, eax
0x1800c019c  cmp     r15d, edx
0x1800c019f  jbe     short loc_1800C01BF
0x1800c01a1  lea     rdx, [rsp+4910h+var_48C0]; int *
0x1800c01a6  mov     [rsp+4910h+var_48C0], 8007000Eh
0x1800c01ae  lea     rcx, [rbp+4810h+var_4888]; this
0x1800c01b2  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800c01b7  test    eax, eax
0x1800c01b9  jnz     loc_1800C0285
0x1800c01bf  mov     ebx, r15d
0x1800c01c2  lea     rdx, [rbp+4810h+Src]
0x1800c01c9  sub     rdx, rbx; Src
0x1800c01cc  mov     r8d, r15d; Size
0x1800c01cf  lea     rcx, [rbp+4810h+var_4840]; void *
0x1800c01d3  call    memcpy_0
0x1800c01d8  mov     rcx, [rdi+0A8h]
0x1800c01df  lea     rdx, [rbp+4810h+var_4840]
0x1800c01e3  mov     r8d, 800h
0x1800c01e9  lea     r9, [rsp+4910h+Size+4]
0x1800c01ee  sub     r8d, r15d
0x1800c01f1  add     rdx, rbx
0x1800c01f4  mov     rax, [rcx]
0x1800c01f7  mov     rax, [rax+18h]
0x1800c01fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c0200  lea     rdx, [rsp+4910h+var_48C0]; int *
0x1800c0205  mov     [rsp+4910h+var_48C0], eax
0x1800c0209  lea     rcx, [rbp+4810h+var_4888]; this
0x1800c020d  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800c0212  test    eax, eax
0x1800c0214  jnz     loc_1800C02D1
0x1800c021a  mov     r11d, dword ptr [rsp+4910h+Size+4]
0x1800c021f  xor     eax, eax
0x1800c0221  mov     r14d, eax
0x1800c0224  jmp     loc_1800BFFDB
0x1800c0229  mov     r9d, 6C3h
0x1800c022f  mov     edx, 1B0C09h
  ... truncated ...
```
