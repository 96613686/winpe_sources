# CCommand::put_CommandText(ushort *)

- ea: `0x180045ff0`
- end: `0x18004659c`
- name: `?put_CommandText@CCommand@@UEAAJPEAG@Z`
- size: `1452`
- prototype: `int(CCommand *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x1800889a0`

## callees

- `0x180011d7c`
- `0x180020e20`
- `0x180020fc0`
- `0x1800265d0`
- `0x180042a04`
- `0x180045ff0`
- `0x1800465a4`
- `0x18004f370`
- `0x18006a22c`
- `0x1800c8ebc`
- `0x1800c8f34`
- `0x1800d0010`

## import_xrefs

- `MSDART!UMSEnterCSWraper` at `0x180046173`
- `MSDART!UMSEnterCSWraper` at `0x180046173`
- `KERNEL32!CompareStringW` at `0x1800461e2`
- `KERNEL32!CompareStringW` at `0x1800461e2`
- `KERNEL32!LeaveCriticalSection` at `0x180046416`
- `KERNEL32!LeaveCriticalSection` at `0x180046416`
- `KERNEL32!TlsSetValue` at `0x18004607d`
- `KERNEL32!TlsSetValue` at `0x180046158`
- `KERNEL32!TlsSetValue` at `0x180046472`
- `KERNEL32!TlsSetValue` at `0x180046563`
- `KERNEL32!TlsSetValue` at `0x18004607d`
- `KERNEL32!TlsSetValue` at `0x180046158`
- `KERNEL32!TlsSetValue` at `0x180046472`
- `KERNEL32!TlsSetValue` at `0x180046563`
- `KERNEL32!TlsGetValue` at `0x180046039`
- `KERNEL32!TlsGetValue` at `0x180046114`
- `KERNEL32!TlsGetValue` at `0x180046039`
- `KERNEL32!TlsGetValue` at `0x180046114`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800462ee`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800462ee`
- `OLEAUT32!__imp_SysFreeString` at `0x1800462be`
- `OLEAUT32!__imp_SysFreeString` at `0x1800462be`
- `OLEAUT32!__imp_SysStringLen` at `0x18004619a`
- `OLEAUT32!__imp_SysStringLen` at `0x1800462dd`
- `OLEAUT32!__imp_SysStringLen` at `0x18004619a`
- `OLEAUT32!__imp_SysStringLen` at `0x1800462dd`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18004643c`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18004652d`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18004643c`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18004652d`

## string_xrefs

- `0x180046269`: `<CCommand::SetSQL|ADO|ERR> %u#, line %d\n`
- `0x18004628f`: `<CCommand::SetSQL|ADO|ERR>  line %d\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CCommand::put_CommandText(CCommand *this, unsigned __int16 *a2)
{
  unsigned __int64 v4; // rbx
  _DWORD *Value; // rax
  unsigned int BidObjectID; // eax
  __int64 v7; // r14
  _DWORD *v8; // rax
  PCNZWCH *v9; // rbx
  UINT v10; // eax
  unsigned __int64 v11; // r15
  unsigned __int64 v12; // r14
  int cchCount2; // r9d
  unsigned int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // r9
  __int64 v17; // rdx
  UINT v18; // eax
  BSTR v19; // rax
  char v20; // cl
  char v21; // cl
  __int64 v22; // rax
  __int64 v23; // rcx
  const struct CSysString *v24; // rax
  __int64 v25; // rax
  int v26; // ebx
  __int64 v27; // rcx
  bool v28; // zf
  _DWORD *v29; // rax
  IErrorInfo *v30; // rdx
  int v31; // ebx
  unsigned int v32; // eax
  unsigned int v33; // ebx
  _DWORD *v34; // rax
  IErrorInfo *v35; // rdx
  PCNZWCH lpString2; // [rsp+20h] [rbp-59h]
  unsigned __int16 *v38; // [rsp+30h] [rbp-49h] BYREF
  char v39; // [rsp+38h] [rbp-41h]
  _DWORD *TlsValue; // [rsp+40h] [rbp-39h] BYREF
  int v41; // [rsp+48h] [rbp-31h]
  __int64 v42; // [rsp+50h] [rbp-29h]
  int v43; // [rsp+58h] [rbp-21h]
  __int16 v44; // [rsp+5Ch] [rbp-1Dh]
  char v45; // [rsp+5Eh] [rbp-1Bh]
  unsigned __int64 v46; // [rsp+60h] [rbp-19h]
  int v47; // [rsp+68h] [rbp-11h]
  int v48; // [rsp+6Ch] [rbp-Dh]
  _DWORD *v49; // [rsp+70h] [rbp-9h] BYREF
  int v50; // [rsp+78h] [rbp-1h]
  __int64 v51; // [rsp+80h] [rbp+7h]
  int v52; // [rsp+88h] [rbp+Fh]
  __int16 v53; // [rsp+8Ch] [rbp+13h]
  char v54; // [rsp+8Eh] [rbp+15h]
  unsigned __int64 v55; // [rsp+90h] [rbp+17h]
  int v56; // [rsp+98h] [rbp+1Fh]
  int v57; // [rsp+9Ch] [rbp+23h]
  __int64 *v58; // [rsp+A0h] [rbp+27h]
  int v59; // [rsp+E0h] [rbp+67h] BYREF
  __int64 v60; // [rsp+F0h] [rbp+77h] BYREF

  v4 = ((unsigned __int64)this + 32) & -(__int64)(this != 0);
  v46 = v4;
  v48 = 0;
  Value = TlsGetValue(*((_DWORD *)g_pStaticGlobals + 5));
  TlsValue = Value;
  v47 = 0;
  if ( Value )
  {
    ++Value[2];
  }
  else
  {
    v41 = 1;
    v42 = 0;
    v43 = 0;
    v44 = 0;
    v45 = 0;
    TlsSetValue(*((_DWORD *)g_pStaticGlobals + 5), &TlsValue);
    TlsValue = &TlsValue;
  }
  v60 = -1;
  if ( (bidGblFlags & 4) != 0 && off_18012AAC8[0] )
  {
    BidObjectID = CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144));
    bidScopeEnterW(&v60, off_18012AAC8[0], BidObjectID, a2, (_DWORD)lpString2);
  }
  if ( *((_BYTE *)this + 544) == 1 )
  {
    v59 = -2146824577;
    CContext::FailedPushWarning((CContext *)&TlsValue, &v59);
    goto LABEL_65;
  }
  v38 = a2;
  v39 = 4;
  v7 = *((_QWORD *)this + 14) + 8LL;
  v55 = v4;
  v57 = 0;
  v8 = TlsGetValue(*((_DWORD *)g_pStaticGlobals + 5));
  v49 = v8;
  v56 = 0;
  if ( v8 )
  {
    ++v8[2];
  }
  else
  {
    v50 = 1;
    v51 = 0;
    v52 = 0;
    v53 = 0;
    v54 = 0;
    TlsSetValue(*((_DWORD *)g_pStaticGlobals + 5), &v49);
    v49 = &v49;
  }
  v58 = 0;
  UMSEnterCSWraper(v7);
  v58 = (__int64 *)v7;
  if ( *((_BYTE *)this + 216) )
  {
    v9 = (PCNZWCH *)((char *)this + 176);
    v10 = SysStringLen(*((BSTR *)this + 22));
    v11 = v10;
    if ( a2 )
    {
      v12 = -1;
      do
        ++v12;
      while ( a2[v12] );
    }
    else
    {
      v12 = 0;
    }
    cchCount2 = v10;
    if ( v10 >= v12 )
      cchCount2 = v12;
    if ( CompareStringW(0x400u, 0x30000u, *v9, cchCount2, a2, cchCount2) == 2 && v11 >= v12 && v11 <= v12 )
      goto LABEL_57;
    if ( (unsigned int)CSysString::IsEmpty((CCommand *)((char *)this + 176))
      || (v59 = CParameters::EmptyParameters((CCommand *)((char *)this + 368)),
          !(unsigned int)CContext::Failed((CContext *)&v49, &v59)) )
    {
      if ( &v38 != (unsigned __int16 **)v9 && a2 != *v9 )
      {
        if ( (*((_BYTE *)this + 184) & 2) != 0 )
          SysFreeString((BSTR)*v9);
        if ( a2 )
        {
          if ( (*((_BYTE *)this + 184) & 1) != 0 )
          {
            v18 = SysStringLen(a2);
            v19 = SysAllocStringLen(a2, v18);
            *v9 = v19;
            v20 = *((_BYTE *)this + 184);
            if ( v19 )
              v21 = v20 | 4;
            else
              v21 = v20 & 0xFB;
            *((_BYTE *)this + 184) = v21;
          }
          else
          {
            *v9 = a2;
          }
        }
        else
        {
          *v9 = 0;
        }
      }
      if ( (*((_BYTE *)this + 184) & 4) == 0 )
      {
        v59 = -2147024882;
        CContext::FailedPushWarning((CContext *)&v49, &v59);
      }
      v22 = *((_QWORD *)this + 15);
      if ( v22 )
        *(_BYTE *)(v22 + 172) = 1;
      goto LABEL_57;
    }
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144)) != -1 )
      {
        v14 = CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144));
        LODWORD(lpString2) = 561;
        v15 = 574473;
LABEL_28:
        bidTraceW(off_18012A1E0[0], v15, L"<CCommand::SetSQL|ADO|ERR> %u#, line %d\n", v14, lpString2);
        goto LABEL_57;
      }
      v16 = 561;
      v17 = 574473;
      goto LABEL_30;
    }
  }
  else
  {
    v59 = CParameters::EmptyParameters((CCommand *)((char *)this + 368));
    if ( !(unsigned int)CContext::Failed((CContext *)&v49, &v59) )
    {
      v23 = *((_QWORD *)this + 26);
      if ( v23 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
        *((_QWORD *)this + 26) = 0;
      }
      v24 = (const struct CSysString *)CSysString::operator=((char *)this + 176, &v38);
      CContext::StringFailed((CContext *)&v49, v24);
      v25 = *((_QWORD *)this + 15);
      if ( v25 )
        *(_BYTE *)(v25 + 172) = 1;
      *((_BYTE *)this + 216) = 1;
      goto LABEL_57;
    }
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144)) != -1 )
      {
        v14 = CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144));
        LODWORD(lpString2) = 577;
        v15 = 590857;
        goto LABEL_28;
      }
      v16 = 577;
      v17 = 590857;
LABEL_30:
      bidTraceW(off_18012A1E0[0], v17, L"<CCommand::SetSQL|ADO|ERR>  line %d\n", v16);
    }
  }
LABEL_57:
  v26 = v56;
  v27 = *v58;
  --*(_DWORD *)(v27 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v27 + 8));
  v28 = v49[2]-- == 1;
  if ( v28 )
  {
    v29 = v49;
    v30 = (IErrorInfo *)*((_QWORD *)v49 + 2);
    if ( v30 )
    {
      SetErrorInfo(0, v30);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v49 + 2) + 16LL))(*((_QWORD *)v49 + 2));
      v29 = v49;
    }
    if ( *((_BYTE *)v29 + 30) )
    {
      *((_QWORD *)v29 + 2) = 0;
      v49[6] = 0;
    }
    else
    {
      TlsSetValue(*((_DWORD *)g_pStaticGlobals + 5), 0);
    }
  }
  v47 = v26;
  if ( v26 < 0 )
    CContext::PushError((CContext *)&TlsValue);
LABEL_65:
  if ( (bidGblFlags & 2) != 0 && off_18012A4E0[0] )
  {
    v31 = v47;
    v32 = CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144));
    LODWORD(lpString2) = v31;
    bidTraceW(off_18012A1E0[0], 1616896, off_18012A4E0[0], v32, lpString2);
  }
  if ( (bidGblFlags & 4) != 0 && v60 != -1 && bidID != -1 )
    ((void (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *))off_180121248[0])(bidID, 0, 0, &v60);
  v33 = v47;
  v28 = TlsValue[2]-- == 1;
  if ( v28 )
  {
    v34 = TlsValue;
    v35 = (IErrorInfo *)*((_QWORD *)TlsValue + 2);
    if ( v35 )
    {
      SetErrorInfo(0, v35);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)TlsValue + 2) + 16LL))(*((_QWORD *)TlsValue + 2));
      v34 = TlsValue;
    }
    if ( *((_BYTE *)v34 + 30) )
    {
      *((_QWORD *)v34 + 2) = 0;
      TlsValue[6] = 0;
    }
    else
    {
      TlsSetValue(*((_DWORD *)g_pStaticGlobals + 5), 0);
    }
  }
  return v33;
}

```

## disassembly

```asm
0x180045ff0  mov     [rsp-8+arg_8], rbx
0x180045ff5  mov     [rsp-8+arg_18], rsi
0x180045ffa  push    rbp
0x180045ffb  push    rdi
0x180045ffc  push    r12
0x180045ffe  push    r14
0x180046000  push    r15
0x180046002  lea     rbp, [rsp-37h]
0x180046007  sub     rsp, 0B0h
0x18004600e  mov     rsi, rdx
0x180046011  mov     rdi, rcx
0x180046014  mov     rax, rcx
0x180046017  lea     r8, [rcx+20h]
0x18004601b  neg     rax
0x18004601e  sbb     rbx, rbx
0x180046021  and     rbx, r8
0x180046024  mov     [rbp+57h+var_70], rbx
0x180046028  xor     r12d, r12d
0x18004602b  mov     [rbp+57h+var_64], r12d
0x18004602f  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x180046036  mov     ecx, [rcx+14h]; dwTlsIndex
0x180046039  call    cs:__imp_TlsGetValue
0x180046040  nop     dword ptr [rax+rax+00h]
0x180046045  mov     [rbp+57h+TlsValue], rax
0x180046049  mov     [rbp+57h+var_68], r12d
0x18004604d  test    rax, rax
0x180046050  jz      short loc_180046057
0x180046052  inc     dword ptr [rax+8]
0x180046055  jmp     short loc_180046091
0x180046057  mov     [rbp+57h+var_88], 1
0x18004605e  mov     [rbp+57h+var_80], r12
0x180046062  mov     [rbp+57h+var_78], r12d
0x180046066  mov     [rbp+57h+var_74], r12w
0x18004606b  mov     [rbp+57h+var_72], r12b
0x18004606f  lea     rdx, [rbp+57h+TlsValue]; lpTlsValue
0x180046073  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x18004607a  mov     ecx, [rcx+14h]; dwTlsIndex
0x18004607d  call    cs:__imp_TlsSetValue
0x180046084  nop     dword ptr [rax+rax+00h]
0x180046089  lea     rax, [rbp+57h+TlsValue]
0x18004608d  mov     [rbp+57h+TlsValue], rax
0x180046091  mov     [rbp+57h+arg_10], 0FFFFFFFFFFFFFFFFh
0x180046099  test    byte ptr cs:_bidGblFlags, 4
0x1800460a0  jz      short loc_1800460D0
0x1800460a2  mov     rax, cs:off_18012AAC8; "<CCommand::put_CommandText|API|ADO> %u#"...
0x1800460a9  test    rax, rax
0x1800460ac  jz      short loc_1800460D0
0x1800460ae  lea     rcx, [rdi+90h]; this
0x1800460b5  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800460ba  mov     rdx, cs:off_18012AAC8; "<CCommand::put_CommandText|API|ADO> %u#"...
0x1800460c1  mov     r9, rsi
0x1800460c4  mov     r8d, eax
0x1800460c7  lea     rcx, [rbp+57h+arg_10]
0x1800460cb  call    _bidScopeEnterW
0x1800460d0  cmp     byte ptr [rdi+220h], 1
0x1800460d7  jnz     short loc_1800460F2
0x1800460d9  mov     [rbp+57h+arg_0], 800A0E7Fh
0x1800460e0  lea     rdx, [rbp+57h+arg_0]; int *
0x1800460e4  lea     rcx, [rbp+57h+TlsValue]; this
0x1800460e8  call    ?FailedPushWarning@CContext@@QEAAHAEBJ@Z; CContext::FailedPushWarning(long const &)
0x1800460ed  jmp     loc_18004649C
0x1800460f2  mov     [rbp+57h+var_A0], rsi
0x1800460f6  mov     [rbp+57h+var_98], 4
0x1800460fa  mov     r14, [rdi+70h]
0x1800460fe  add     r14, 8
0x180046102  mov     [rbp+57h+var_40], rbx
0x180046106  mov     [rbp+57h+var_34], r12d
0x18004610a  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x180046111  mov     ecx, [rcx+14h]; dwTlsIndex
0x180046114  call    cs:__imp_TlsGetValue
0x18004611b  nop     dword ptr [rax+rax+00h]
0x180046120  mov     [rbp+57h+var_60], rax
0x180046124  mov     [rbp+57h+var_38], r12d
0x180046128  test    rax, rax
0x18004612b  jz      short loc_180046132
0x18004612d  inc     dword ptr [rax+8]
0x180046130  jmp     short loc_18004616C
0x180046132  mov     [rbp+57h+var_58], 1
0x180046139  mov     [rbp+57h+var_50], r12
0x18004613d  mov     [rbp+57h+var_48], r12d
0x180046141  mov     [rbp+57h+var_44], r12w
0x180046146  mov     [rbp+57h+var_42], r12b
0x18004614a  lea     rdx, [rbp+57h+var_60]; lpTlsValue
0x18004614e  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x180046155  mov     ecx, [rcx+14h]; dwTlsIndex
0x180046158  call    cs:__imp_TlsSetValue
0x18004615f  nop     dword ptr [rax+rax+00h]
0x180046164  lea     rax, [rbp+57h+var_60]
0x180046168  mov     [rbp+57h+var_60], rax
0x18004616c  mov     [rbp+57h+var_30], r12
0x180046170  mov     rcx, r14
0x180046173  call    cs:__imp_UMSEnterCSWraper
0x18004617a  nop     dword ptr [rax+rax+00h]
0x18004617f  mov     [rbp+57h+var_30], r14
0x180046183  cmp     [rdi+0D8h], r12b
0x18004618a  jz      loc_180046348
0x180046190  lea     rbx, [rdi+0B0h]
0x180046197  mov     rcx, [rbx]; pbstr
0x18004619a  call    cs:__imp_SysStringLen
0x1800461a1  nop     dword ptr [rax+rax+00h]
0x1800461a6  mov     r15d, eax
0x1800461a9  test    rsi, rsi
0x1800461ac  jz      short loc_1800461BE
0x1800461ae  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800461b2  inc     r14
0x1800461b5  cmp     [rsi+r14*2], r12w
0x1800461ba  jnz     short loc_1800461B2
0x1800461bc  jmp     short loc_1800461C1
0x1800461be  mov     r14, r12
0x1800461c1  mov     r9d, r15d
0x1800461c4  cmp     r15, r14
0x1800461c7  cmovnb  r9d, r14d; cchCount1
0x1800461cb  mov     [rsp+0D0h+cchCount2], r9d; cchCount2
0x1800461d0  mov     [rsp+0D0h+lpString2], rsi; lpString2
0x1800461d5  mov     r8, [rbx]; lpString1
0x1800461d8  mov     edx, 30000h; dwCmpFlags
0x1800461dd  mov     ecx, 400h; Locale
0x1800461e2  call    cs:__imp_CompareStringW
0x1800461e9  nop     dword ptr [rax+rax+00h]
0x1800461ee  sub     eax, 1
0x1800461f1  jz      short loc_180046203
0x1800461f3  cmp     eax, 1
0x1800461f6  jnz     short loc_180046203
0x1800461f8  cmp     r15, r14
0x1800461fb  jb      short loc_180046203
0x1800461fd  jbe     loc_180046405
0x180046203  mov     rcx, rbx; this
0x180046206  call    ?IsEmpty@CSysString@@QEBAHXZ; CSysString::IsEmpty(void)
0x18004620b  test    eax, eax
0x18004620d  jnz     loc_1800462A7
0x180046213  lea     rcx, [rdi+170h]; this
0x18004621a  call    ?EmptyParameters@CParameters@@QEAAJXZ; CParameters::EmptyParameters(void)
0x18004621f  mov     [rbp+57h+arg_0], eax
0x180046222  lea     rdx, [rbp+57h+arg_0]; int *
0x180046226  lea     rcx, [rbp+57h+var_60]; this
0x18004622a  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x18004622f  test    eax, eax
0x180046231  jz      short loc_1800462A7
0x180046233  test    byte ptr cs:_bidGblFlags, 2
0x18004623a  jz      loc_180046405
0x180046240  lea     rbx, [rdi+90h]
0x180046247  mov     rcx, rbx; this
0x18004624a  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18004624f  cmp     eax, 0FFFFFFFFh
0x180046252  jz      short loc_180046284
0x180046254  mov     rcx, rbx; this
0x180046257  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18004625c  mov     dword ptr [rsp+0D0h+lpString2], 231h
0x180046264  mov     edx, 8C409h
0x180046269  lea     r8, aCcommandSetsql_0; "<CCommand::SetSQL|ADO|ERR> %u#, line %d"...
0x180046270  mov     r9d, eax
0x180046273  mov     rcx, cs:off_18012A1E0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18004627a  call    _bidTraceW
0x18004627f  jmp     loc_180046405
0x180046284  mov     r9d, 231h
0x18004628a  mov     edx, 8C409h
0x18004628f  lea     r8, aCcommandSetsql; "<CCommand::SetSQL|ADO|ERR>  line %d\n"
0x180046296  mov     rcx, cs:off_18012A1E0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18004629d  call    _bidTraceW
0x1800462a2  jmp     loc_180046405
0x1800462a7  lea     rax, [rbp+57h+var_A0]
0x1800462ab  cmp     rax, rbx
0x1800462ae  jz      short loc_180046315
0x1800462b0  cmp     rsi, [rbx]
0x1800462b3  jz      short loc_180046315
0x1800462b5  test    byte ptr [rbx+8], 2
0x1800462b9  jz      short loc_1800462CA
0x1800462bb  mov     rcx, [rbx]; bstrString
0x1800462be  call    cs:__imp_SysFreeString
0x1800462c5  nop     dword ptr [rax+rax+00h]
0x1800462ca  test    rsi, rsi
0x1800462cd  jnz     short loc_1800462D4
0x1800462cf  mov     [rbx], r12
0x1800462d2  jmp     short loc_180046315
0x1800462d4  test    byte ptr [rbx+8], 1
0x1800462d8  jz      short loc_180046312
0x1800462da  mov     rcx, rsi; pbstr
0x1800462dd  call    cs:__imp_SysStringLen
0x1800462e4  nop     dword ptr [rax+rax+00h]
0x1800462e9  mov     edx, eax; ui
0x1800462eb  mov     rcx, rsi; strIn
0x1800462ee  call    cs:__imp_SysAllocStringLen
0x1800462f5  nop     dword ptr [rax+rax+00h]
0x1800462fa  mov     [rbx], rax
0x1800462fd  mov     cl, [rbx+8]
0x180046300  test    rax, rax
0x180046303  jnz     short loc_18004630A
0x180046305  and     cl, 0FBh
0x180046308  jmp     short loc_18004630D
0x18004630a  or      cl, 4
0x18004630d  mov     [rbx+8], cl
0x180046310  jmp     short loc_180046315
0x180046312  mov     [rbx], rsi
0x180046315  test    byte ptr [rbx+8], 4
0x180046319  jnz     short loc_18004632F
0x18004631b  mov     [rbp+57h+arg_0], 8007000Eh
0x180046322  lea     rdx, [rbp+57h+arg_0]; int *
0x180046326  lea     rcx, [rbp+57h+var_60]; this
0x18004632a  call    ?FailedPushWarning@CContext@@QEAAHAEBJ@Z; CContext::FailedPushWarning(long const &)
0x18004632f  mov     rax, [rdi+78h]
0x180046333  test    rax, rax
0x180046336  jz      loc_180046405
0x18004633c  mov     byte ptr [rax+0ACh], 1
0x180046343  jmp     loc_180046405
0x180046348  lea     rcx, [rdi+170h]; this
0x18004634f  call    ?EmptyParameters@CParameters@@QEAAJXZ; CParameters::EmptyParameters(void)
0x180046354  mov     [rbp+57h+arg_0], eax
0x180046357  lea     rdx, [rbp+57h+arg_0]; int *
0x18004635b  lea     rcx, [rbp+57h+var_60]; this
0x18004635f  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x180046364  test    eax, eax
0x180046366  jz      short loc_1800463B3
0x180046368  test    byte ptr cs:_bidGblFlags, 2
0x18004636f  jz      loc_180046405
0x180046375  lea     rbx, [rdi+90h]
0x18004637c  mov     rcx, rbx; this
0x18004637f  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180046384  cmp     eax, 0FFFFFFFFh
0x180046387  jz      short loc_1800463A3
0x180046389  mov     rcx, rbx; this
0x18004638c  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180046391  mov     dword ptr [rsp+0D0h+lpString2], 241h
0x180046399  mov     edx, 90409h
0x18004639e  jmp     loc_180046269
0x1800463a3  mov     r9d, 241h
0x1800463a9  mov     edx, 90409h
0x1800463ae  jmp     loc_18004628F
0x1800463b3  mov     rcx, [rdi+0D0h]
0x1800463ba  test    rcx, rcx
0x1800463bd  jz      short loc_1800463D2
0x1800463bf  mov     rax, [rcx]
0x1800463c2  mov     rax, [rax+10h]
0x1800463c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800463cb  mov     [rdi+0D0h], r12
0x1800463d2  lea     rcx, [rdi+0B0h]
0x1800463d9  lea     rdx, [rbp+57h+var_A0]
0x1800463dd  call    ??4CSysString@@QEAAAEBV0@AEBV0@@Z; CSysString::operator=(CSysString const &)
0x1800463e2  mov     rdx, rax; struct CSysString *
0x1800463e5  lea     rcx, [rbp+57h+var_60]; this
0x1800463e9  call    ?StringFailed@CContext@@QEAAHAEBVCSysString@@@Z; CContext::StringFailed(CSysString const &)
0x1800463ee  mov     rax, [rdi+78h]
0x1800463f2  test    rax, rax
0x1800463f5  jz      short loc_1800463FE
0x1800463f7  mov     byte ptr [rax+0ACh], 1
0x1800463fe  mov     byte ptr [rdi+0D8h], 1
0x180046405  mov     ebx, [rbp+57h+var_38]
0x180046408  mov     rax, [rbp+57h+var_30]
0x18004640c  mov     rcx, [rax]
0x18004640f  dec     dword ptr [rcx+30h]
0x180046412  add     rcx, 8; lpCriticalSection
0x180046416  call    cs:__imp_LeaveCriticalSection
0x18004641d  nop     dword ptr [rax+rax+00h]
0x180046422  nop
0x180046423  mov     rax, [rbp+57h+var_60]
0x180046427  add     dword ptr [rax+8], 0FFFFFFFFh
0x18004642b  jnz     short loc_18004648C
0x18004642d  mov     rax, [rbp+57h+var_60]
0x180046431  mov     rdx, [rax+10h]; perrinfo
0x180046435  test    rdx, rdx
0x180046438  jz      short loc_180046460
0x18004643a  xor     ecx, ecx; dwReserved
0x18004643c  call    cs:__imp_SetErrorInfo
0x180046443  nop     dword ptr [rax+rax+00h]
0x180046448  mov     rax, [rbp+57h+var_60]
0x18004644c  mov     rcx, [rax+10h]
0x180046450  mov     rax, [rcx]
0x180046453  mov     rax, [rax+10h]
0x180046457  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004645c  mov     rax, [rbp+57h+var_60]
0x180046460  cmp     [rax+1Eh], r12b
0x180046464  jnz     short loc_180046480
0x180046466  xor     edx, edx; lpTlsValue
0x180046468  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x18004646f  mov     ecx, [rcx+14h]; dwTlsIndex
0x180046472  call    cs:__imp_TlsSetValue
0x180046479  nop     dword ptr [rax+rax+00h]
0x18004647e  jmp     short loc_18004648C
0x180046480  mov     [rax+10h], r12
0x180046484  mov     rax, [rbp+57h+var_60]
0x180046488  mov     [rax+18h], r12d
0x18004648c  mov     [rbp+57h+var_68], ebx
0x18004648f  test    ebx, ebx
0x180046491  jns     short loc_18004649C
0x180046493  lea     rcx, [rbp+57h+TlsValue]; this
0x180046497  call    ?PushError@CContext@@QEAAHXZ; CContext::PushError(void)
0x18004649c  test    byte ptr cs:_bidGblFlags, 2
0x1800464a3  jz      short loc_1800464DF
0x1800464a5  mov     rax, cs:off_18012A4E0; "<CCommand::put_CommandText|API|ADO|RET>"...
0x1800464ac  test    rax, rax
0x1800464af  jz      short loc_1800464DF
0x1800464b1  mov     ebx, [rbp+57h+var_68]
0x1800464b4  lea     rcx, [rdi+90h]; this
0x1800464bb  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800464c0  mov     r8, cs:off_18012A4E0; "<CCommand::put_CommandText|API|ADO|RET>"...
0x1800464c7  mov     rcx, cs:off_18012A1E0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800464ce  mov     dword ptr [rsp+0D0h+lpString2], ebx
0x1800464d2  mov     r9d, eax
0x1800464d5  mov     edx, 18AC00h
0x1800464da  call    _bidTraceW
0x1800464df  test    byte ptr cs:_bidGblFlags, 4
  ... truncated ...
```
