# COdbcConnection::InitializeContext(void *)

- ea: `0x180098b60`
- end: `0x1800993d4`
- name: `?InitializeContext@COdbcConnection@@UEAAJPEAX@Z`
- size: `2164`
- prototype: `__int64 __fastcall(COdbcConnection *__hidden this, void *)`
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18001ad74`
- `0x18002d834`
- `0x18002d884`
- `0x180077e9c`
- `0x1800790c0`
- `0x180088e68`
- `0x180097b4c`
- `0x180098314`
- `0x1800983d0`
- `0x18009872c`
- `0x180098b60`
- `0x1800994cc`
- `0x180099768`
- `0x180099ef8`
- `0x18009a15c`
- `0x18009a200`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180098f00`
- `OLEAUT32!__imp_SysAllocString` at `0x180098ff7`
- `OLEAUT32!__imp_SysAllocString` at `0x180098f00`
- `OLEAUT32!__imp_SysAllocString` at `0x180098ff7`
- `OLEAUT32!__imp_SysFreeString` at `0x180098c3b`
- `OLEAUT32!__imp_SysFreeString` at `0x180098c50`
- `OLEAUT32!__imp_SysFreeString` at `0x180098c68`
- `OLEAUT32!__imp_SysFreeString` at `0x180098c80`
- `OLEAUT32!__imp_SysFreeString` at `0x18009915e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800992a7`
- `OLEAUT32!__imp_SysFreeString` at `0x180098c3b`
- `OLEAUT32!__imp_SysFreeString` at `0x180098c50`
- `OLEAUT32!__imp_SysFreeString` at `0x180098c68`
- `OLEAUT32!__imp_SysFreeString` at `0x180098c80`
- `OLEAUT32!__imp_SysFreeString` at `0x18009915e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800992a7`
- `OLEAUT32!__imp_SysStringLen` at `0x180099091`
- `OLEAUT32!__imp_SysStringLen` at `0x1800991c0`
- `OLEAUT32!__imp_SysStringLen` at `0x180099091`
- `OLEAUT32!__imp_SysStringLen` at `0x1800991c0`
- `ODBC32!__imp_SQLAllocHandle` at `0x180098ba4`
- `ODBC32!__imp_SQLAllocHandle` at `0x180098ba4`
- `ODBC32!__imp_SQLSetConnectAttrW` at `0x180098da9`
- `ODBC32!__imp_SQLSetConnectAttrW` at `0x180098da9`
- `ODBC32!__imp_SQLDriverConnectW` at `0x1800990c5`
- `ODBC32!__imp_SQLDriverConnectW` at `0x180099235`
- `ODBC32!__imp_SQLDriverConnectW` at `0x1800990c5`
- `ODBC32!__imp_SQLDriverConnectW` at `0x180099235`

## string_xrefs

- `0x180098d30`: `ReadLoginTimeout`
- `0x180098ce4`: `ReadConnString`
- `0x180098e4a`: `"bstrCopyConnString"`
- `0x180098f98`: `"bstrCopySecondaryConnString"`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall COdbcConnection::InitializeContext(SQLHANDLE *this, void *a2)
{
  SQLRETURN v4; // ax
  unsigned int v5; // r15d
  const unsigned __int16 *v6; // rdx
  int ConnString; // edi
  HKEY v8; // r8
  int v9; // r9d
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v11; // edx
  const char *v12; // rcx
  COdbcConnection *v14; // rcx
  int v15; // ebx
  unsigned int v16; // eax
  SQLRETURN v17; // ax
  int v18; // ebx
  unsigned int v19; // eax
  OLECHAR *v20; // rdi
  unsigned int v21; // eax
  int v22; // edx
  const char *v23; // rcx
  __int64 v24; // rax
  int v25; // ebx
  unsigned int v26; // eax
  OLECHAR *v27; // rax
  unsigned int v28; // eax
  BSTR v29; // rbx
  unsigned int v30; // eax
  SQLRETURN v31; // ax
  __int64 v32; // rax
  int v33; // ebx
  PVOID *v34; // rax
  BSTR v35; // rbx
  unsigned int v36; // eax
  int v37; // r8d
  int v38; // edx
  BSTR v39; // rbx
  unsigned int v40; // eax
  int v41; // r8d
  BSTR v42; // rbx
  unsigned int v43; // eax
  SQLRETURN v44; // ax
  BSTR v45; // rbx
  unsigned int v46; // eax
  int v47; // r8d
  int v48; // r13d
  int v49; // edx
  unsigned int v50; // eax
  BSTR v51; // rbx
  unsigned int v52; // eax
  __int64 cchConnStrOutMax; // [rsp+28h] [rbp-41h]
  BSTR bstrString; // [rsp+40h] [rbp-29h] BYREF
  BSTR v55; // [rsp+48h] [rbp-21h] BYREF
  BSTR v56; // [rsp+50h] [rbp-19h]
  BSTR v57; // [rsp+58h] [rbp-11h]
  _BYTE v58[96]; // [rsp+60h] [rbp-9h] BYREF
  SQLSMALLINT pcchConnStrOut; // [rsp+D0h] [rbp+67h] BYREF
  int v60; // [rsp+E0h] [rbp+77h]
  int v61; // [rsp+E8h] [rbp+7Fh]

  pcchConnStrOut = 0;
  bstrString = 0;
  v55 = 0;
  v57 = 0;
  v56 = 0;
  v60 = 0;
  v61 = 0;
  v4 = SQLAllocHandle(2, a2, this + 2);
  v5 = 1;
  ConnString = OdbcErrorToHresult(v4, a2, 1);
  if ( ConnString < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v11 = 33;
    v12 = "SQLAllocHandle, SQL_HANDLE_DBC";
    goto LABEL_6;
  }
  ConnString = COdbcConnection::ReadConnString((COdbcConnection *)this, v6, v8, v9);
  if ( ConnString < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v11 = 34;
    v12 = "ReadConnString";
    goto LABEL_6;
  }
  ConnString = COdbcConnection::ReadLoginTimeout(v14);
  if ( ConnString < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v11 = 35;
    v12 = "ReadLoginTimeout";
LABEL_6:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v11,
      (unsigned int)&WPP_b3cfdbbee2fe34db05ba190773897d01_Traceguids,
      CurrentThreadActivityIdPrefix,
      (__int64)v12,
      ConnString);
LABEL_7:
    v5 = 0;
    goto LABEL_8;
  }
  v15 = COdbcConnection::m_sLoginTimeout;
  if ( COdbcConnection::m_sLoginTimeout >= 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v16 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_b3cfdbbee2fe34db05ba190773897d01_Traceguids, v16, v15);
    }
    v17 = SQLSetConnectAttrW(this[2], 103, &COdbcConnection::m_sLoginTimeout, -5);
    v18 = OdbcErrorToHresult(v17, this[2], 2);
    if ( v18 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v19 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        37,
        (unsigned int)&WPP_b3cfdbbee2fe34db05ba190773897d01_Traceguids,
        v19,
        (__int64)"SqlSetConnectAttr, SQL_ATTR_LOGIN_TIMEOUT, ignoring",
        v18);
    }
  }
  v20 = ATL::CComBSTR::Copy((ATL::CComBSTR *)(this + 10));
  v57 = v20;
  if ( !v20 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_44;
    }
    v21 = RdpWppGetCurrentThreadActivityIdPrefix();
    v22 = 38;
    v23 = "\"bstrCopyConnString\"";
LABEL_43:
    WPP_SF_Ds(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v22,
      (unsigned int)&WPP_b3cfdbbee2fe34db05ba190773897d01_Traceguids,
      v21,
      (__int64)v23);
LABEL_44:
    ConnString = -2147024882;
    goto LABEL_7;
  }
  v24 = CBaseStringT<unsigned short>::CBaseStringT<unsigned short>(v58, this[10]);
  v25 = CBaseStringT<unsigned short>::Contains(v24, L"Trusted_Connection=Yes", 1);
  CBaseStringT<unsigned short>::~CBaseStringT<unsigned short>(v58);
  if ( v25 )
  {
    bstrString = v20;
  }
  else
  {
    v61 = 1;
    if ( (int)InternalGetSbDbConnStringWithoutPassword(v20, &bstrString) < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v26 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_b3cfdbbee2fe34db05ba190773897d01_Traceguids, v26);
      }
      bstrString = SysAllocString(&pszSrc);
      if ( !bstrString )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_44;
        }
        v21 = RdpWppGetCurrentThreadActivityIdPrefix();
        v22 = 40;
        v23 = "\"bstrDbConnStringWithoutPswd\"";
        goto LABEL_43;
      }
    }
    if ( this[11] )
    {
      v27 = ATL::CComBSTR::Copy((ATL::CComBSTR *)(this + 11));
      v56 = v27;
      if ( !v27 )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_44;
        }
        v21 = RdpWppGetCurrentThreadActivityIdPrefix();
        v22 = 41;
        v23 = "\"bstrCopySecondaryConnString\"";
        goto LABEL_43;
      }
      if ( (int)InternalGetSbDbConnStringWithoutPassword(v27, &v55) < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v28 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_b3cfdbbee2fe34db05ba190773897d01_Traceguids, v28);
        }
        v55 = SysAllocString(&pszSrc);
        if ( !v55 )
        {
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_44;
          }
          v21 = RdpWppGetCurrentThreadActivityIdPrefix();
          v22 = 43;
          v23 = "\"bstrDbSecondaryConnStringWithoutPswd\"";
          goto LABEL_43;
        }
      }
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v29 = bstrString;
    v30 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      44,
      (unsigned int)&WPP_b3cfdbbee2fe34db05ba190773897d01_Traceguids,
      v30,
      (__int64)v29);
  }
  SysStringLen((BSTR)this[10]);
  v31 = SQLDriverConnectW(this[2], 0, (SQLWCHAR *)this[10], -3, 0, 0, &pcchConnStrOut, 0);
  ConnString = OdbcErrorToHresult(v31, this[2], 2);
  if ( ConnString < 0 )
  {
    v32 = CBaseStringT<unsigned short>::CBaseStringT<unsigned short>(v58, bstrString);
    v33 = CBaseStringT<unsigned short>::Contains(v32, L"Trusted_Connection=Yes", 1);
    CBaseStringT<unsigned short>::~CBaseStringT<unsigned short>(v58);
    if ( v33 )
    {
      v5 = 4;
      v34 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v35 = bstrString;
        v36 = RdpWppGetCurrentThreadActivityIdPrefix();
        v38 = 45;
LABEL_102:
        WPP_SF_DSd(*((_QWORD *)WPP_GLOBAL_Control + 2), v38, v37, v36, (__int64)v35, ConnString);
LABEL_103:
        v34 = (PVOID *)WPP_GLOBAL_Control;
      }
    }
    else
    {
      SysFreeString((BSTR)this[10]);
      this[10] = 0;
      if ( this[11] )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v39 = bstrString;
          v40 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DSd(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, v41, v40, (__int64)v39, ConnString);
        }
        SysStringLen((BSTR)this[11]);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v42 = v55;
          v43 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            47,
            (unsigned int)&WPP_b3cfdbbee2fe34db05ba190773897d01_Traceguids,
            v43,
            (__int64)v42);
        }
        v44 = SQLDriverConnectW(this[2], 0, (SQLWCHAR *)this[11], -3, 0, 0, &pcchConnStrOut, 0);
        ConnString = OdbcErrorToHresult(v44, this[2], 2);
        if ( ConnString >= 0 )
        {
          v49 = v60;
          goto LABEL_115;
        }
        v60 = 2;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v45 = v55;
          v46 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DSd(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, v47, v46, (__int64)v45, ConnString);
        }
        SysFreeString((BSTR)this[11]);
        this[11] = 0;
        goto LABEL_103;
      }
      v5 = 5;
      v34 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v35 = bstrString;
        v36 = RdpWppGetCurrentThreadActivityIdPrefix();
        v38 = 49;
        goto LABEL_102;
      }
    }
    v48 = v60;
    v49 = v60;
    if ( v34 != &WPP_GLOBAL_Control && (*((_BYTE *)v34 + 28) & 8) != 0 && *((_BYTE *)v34 + 25) >= 2u )
    {
      v50 = RdpWppGetCurrentThreadActivityIdPrefix();
      LODWORD(cchConnStrOutMax) = ConnString;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        51,
        (unsigned int)&WPP_b3cfdbbee2fe34db05ba190773897d01_Traceguids,
        v50,
        (__int64)"SQLDriverConnect",
        cchConnStrOutMax);
      v49 = v48;
    }
    goto LABEL_115;
  }
  v5 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v51 = bstrString;
    v52 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      50,
      (unsigned int)&WPP_b3cfdbbee2fe34db05ba190773897d01_Traceguids,
      v52,
      (__int64)v51);
    goto LABEL_7;
  }
  v49 = 0;
LABEL_115:
  if ( !v5 )
    goto LABEL_7;
  if ( v49 )
    v5 = 3;
LABEL_8:
  COdbcConnection::m_dwConnectionError = v5;
  if ( bstrString && v61 )
    SysFreeString(bstrString);
  if ( v55 )
    SysFreeString(v55);
  if ( v56 )
    SysFreeString(v56);
  if ( v57 )
    SysFreeString(v57);
  return (unsigned int)ConnString;
}

```

## disassembly

```asm
0x180098b60  push    rbp
0x180098b62  push    rbx
0x180098b63  push    rsi
0x180098b64  push    rdi
0x180098b65  push    r12
0x180098b67  push    r13
0x180098b69  push    r15
0x180098b6b  lea     rbp, [rsp-27h]
0x180098b70  sub     rsp, 90h
0x180098b77  mov     rbx, rdx
0x180098b7a  mov     r13, rcx
0x180098b7d  xor     esi, esi
0x180098b7f  mov     [rbp+57h+arg_0], si
0x180098b83  mov     [rbp+57h+bstrString], rsi
0x180098b87  mov     [rbp+57h+var_78], rsi
0x180098b8b  mov     [rbp+57h+var_68], rsi
0x180098b8f  mov     [rbp+57h+var_70], rsi
0x180098b93  mov     [rbp+57h+arg_10], esi
0x180098b96  mov     [rbp+57h+arg_18], esi
0x180098b99  lea     r8, [rcx+10h]; OutputHandle
0x180098b9d  lea     r12d, [rsi+2]
0x180098ba1  mov     ecx, r12d; HandleType
0x180098ba4  call    cs:__imp_SQLAllocHandle
0x180098bab  nop     dword ptr [rax+rax+00h]
0x180098bb0  lea     r15d, [rsi+1]
0x180098bb4  mov     r8d, r15d; __int16
0x180098bb7  mov     rdx, rbx; void *
0x180098bba  movzx   ecx, ax; __int16
0x180098bbd  call    ?OdbcErrorToHresult@@YAJFPEAXF@Z; OdbcErrorToHresult(short,void *,short)
0x180098bc2  mov     edi, eax
0x180098bc4  test    eax, eax
0x180098bc6  jns     loc_180098CA1
0x180098bcc  lea     rsi, WPP_GLOBAL_Control
0x180098bd3  mov     rax, cs:WPP_GLOBAL_Control
0x180098bda  cmp     rax, rsi
0x180098bdd  jz      short loc_180098C1F
0x180098bdf  test    byte ptr [rax+1Ch], 8
0x180098be3  jz      short loc_180098C1F
0x180098be5  cmp     [rax+19h], r12b
0x180098be9  jb      short loc_180098C1F
0x180098beb  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180098bf0  lea     edx, [r12+1Fh]
0x180098bf5  lea     rcx, aSqlallochandle_1; "SQLAllocHandle, SQL_HANDLE_DBC"
0x180098bfc  mov     dword ptr [rsp+0C0h+cchConnStrOutMax], edi
0x180098c00  mov     [rsp+0C0h+szConnStrOut], rcx
0x180098c05  mov     r9d, eax
0x180098c08  lea     r8, WPP_b3cfdbbee2fe34db05ba190773897d01_Traceguids
0x180098c0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180098c16  mov     rcx, [rcx+10h]
0x180098c1a  call    WPP_SF_DsD
0x180098c1f  xor     r15d, r15d
0x180098c22  mov     cs:?m_dwConnectionError@COdbcConnection@@0KA, r15d; ulong COdbcConnection::m_dwConnectionError
0x180098c29  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180098c2d  xor     r15d, r15d
0x180098c30  test    rcx, rcx
0x180098c33  jz      short loc_180098C47
0x180098c35  cmp     [rbp+57h+arg_18], r15d
0x180098c39  jz      short loc_180098C47
0x180098c3b  call    cs:__imp_SysFreeString
0x180098c42  nop     dword ptr [rax+rax+00h]
0x180098c47  mov     rcx, [rbp+57h+var_78]; bstrString
0x180098c4b  test    rcx, rcx
0x180098c4e  jz      short loc_180098C5C
0x180098c50  call    cs:__imp_SysFreeString
0x180098c57  nop     dword ptr [rax+rax+00h]
0x180098c5c  mov     rax, [rbp+57h+var_70]
0x180098c60  test    rax, rax
0x180098c63  jz      short loc_180098C74
0x180098c65  mov     rcx, rax; bstrString
0x180098c68  call    cs:__imp_SysFreeString
0x180098c6f  nop     dword ptr [rax+rax+00h]
0x180098c74  mov     rax, [rbp+57h+var_68]
0x180098c78  test    rax, rax
0x180098c7b  jz      short loc_180098C8C
0x180098c7d  mov     rcx, rax; bstrString
0x180098c80  call    cs:__imp_SysFreeString
0x180098c87  nop     dword ptr [rax+rax+00h]
0x180098c8c  mov     eax, edi
0x180098c8e  add     rsp, 90h
0x180098c95  pop     r15
0x180098c97  pop     r13
0x180098c99  pop     r12
0x180098c9b  pop     rdi
0x180098c9c  pop     rsi
0x180098c9d  pop     rbx
0x180098c9e  pop     rbp
0x180098c9f  retn
0x180098ca1  mov     rcx, r13; this
0x180098ca4  call    ?ReadConnString@COdbcConnection@@AEAAJXZ; COdbcConnection::ReadConnString(void)
0x180098ca9  mov     edi, eax
0x180098cab  test    eax, eax
0x180098cad  jns     short loc_180098CF0
0x180098caf  lea     rsi, WPP_GLOBAL_Control
0x180098cb6  mov     rax, cs:WPP_GLOBAL_Control
0x180098cbd  cmp     rax, rsi
0x180098cc0  jz      loc_180098C1F
0x180098cc6  test    byte ptr [rax+1Ch], 8
0x180098cca  jz      loc_180098C1F
0x180098cd0  cmp     [rax+19h], r12b
0x180098cd4  jb      loc_180098C1F
0x180098cda  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180098cdf  mov     edx, 22h ; '"'
0x180098ce4  lea     rcx, aReadconnstring; "ReadConnString"
0x180098ceb  jmp     loc_180098BFC
0x180098cf0  call    ?ReadLoginTimeout@COdbcConnection@@AEAAJXZ; COdbcConnection::ReadLoginTimeout(void)
0x180098cf5  mov     edi, eax
0x180098cf7  test    eax, eax
0x180098cf9  jns     short loc_180098D3C
0x180098cfb  lea     rsi, WPP_GLOBAL_Control
0x180098d02  mov     rax, cs:WPP_GLOBAL_Control
0x180098d09  cmp     rax, rsi
0x180098d0c  jz      loc_180098C1F
0x180098d12  test    byte ptr [rax+1Ch], 8
0x180098d16  jz      loc_180098C1F
0x180098d1c  cmp     [rax+19h], r12b
0x180098d20  jb      loc_180098C1F
0x180098d26  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180098d2b  mov     edx, 23h ; '#'
0x180098d30  lea     rcx, aReadlogintimeo; "ReadLoginTimeout"
0x180098d37  jmp     loc_180098BFC
0x180098d3c  lea     rsi, WPP_GLOBAL_Control
0x180098d43  lea     r12, WPP_b3cfdbbee2fe34db05ba190773897d01_Traceguids
0x180098d4a  mov     ebx, cs:?m_sLoginTimeout@COdbcConnection@@0JA; long COdbcConnection::m_sLoginTimeout
0x180098d50  test    ebx, ebx
0x180098d52  js      loc_180098E15
0x180098d58  mov     rax, cs:WPP_GLOBAL_Control
0x180098d5f  cmp     rax, rsi
0x180098d62  jz      short loc_180098D94
0x180098d64  test    byte ptr [rax+1Ch], 8
0x180098d68  jz      short loc_180098D94
0x180098d6a  cmp     byte ptr [rax+19h], 4
0x180098d6e  jb      short loc_180098D94
0x180098d70  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180098d75  mov     r9d, eax
0x180098d78  mov     rax, cs:WPP_GLOBAL_Control
0x180098d7f  mov     edx, 24h ; '$'
0x180098d84  mov     dword ptr [rsp+0C0h+szConnStrOut], ebx
0x180098d88  mov     r8, r12
0x180098d8b  mov     rcx, [rax+10h]
0x180098d8f  call    WPP_SF_DD
0x180098d94  mov     r9d, 0FFFFFFFBh; cbValue
0x180098d9a  lea     r8, ?m_sLoginTimeout@COdbcConnection@@0JA; rgbValue
0x180098da1  lea     edx, [r9+6Ch]; fAttribute
0x180098da5  mov     rcx, [r13+10h]; hdbc
0x180098da9  call    cs:__imp_SQLSetConnectAttrW
0x180098db0  nop     dword ptr [rax+rax+00h]
0x180098db5  mov     r8d, 2; __int16
0x180098dbb  mov     rdx, [r13+10h]; void *
0x180098dbf  movzx   ecx, ax; __int16
0x180098dc2  call    ?OdbcErrorToHresult@@YAJFPEAXF@Z; OdbcErrorToHresult(short,void *,short)
0x180098dc7  mov     ebx, eax
0x180098dc9  test    eax, eax
0x180098dcb  jns     short loc_180098E15
0x180098dcd  mov     rcx, cs:WPP_GLOBAL_Control
0x180098dd4  cmp     rcx, rsi
0x180098dd7  jz      short loc_180098E15
0x180098dd9  test    byte ptr [rcx+1Ch], 8
0x180098ddd  jz      short loc_180098E15
0x180098ddf  cmp     byte ptr [rcx+19h], 2
0x180098de3  jb      short loc_180098E15
0x180098de5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180098dea  mov     r9d, eax
0x180098ded  mov     rax, cs:WPP_GLOBAL_Control
0x180098df4  mov     edx, 25h ; '%'
0x180098df9  mov     dword ptr [rsp+0C0h+cchConnStrOutMax], ebx
0x180098dfd  lea     rcx, aSqlsetconnecta_0; "SqlSetConnectAttr, SQL_ATTR_LOGIN_TIMEO"...
0x180098e04  mov     [rsp+0C0h+szConnStrOut], rcx
0x180098e09  mov     r8, r12
0x180098e0c  mov     rcx, [rax+10h]
0x180098e10  call    WPP_SF_DsD
0x180098e15  lea     rcx, [r13+50h]; this
0x180098e19  call    ?Copy@CComBSTR@ATL@@QEBAPEAGXZ; ATL::CComBSTR::Copy(void)
0x180098e1e  mov     rdi, rax
0x180098e21  mov     [rbp+57h+var_68], rax
0x180098e25  test    rax, rax
0x180098e28  jnz     short loc_180098E76
0x180098e2a  mov     rcx, cs:WPP_GLOBAL_Control
0x180098e31  cmp     rcx, rsi
0x180098e34  jz      short loc_180098E6C
0x180098e36  test    byte ptr [rcx+1Ch], 8
0x180098e3a  jz      short loc_180098E6C
0x180098e3c  cmp     byte ptr [rcx+19h], 2
0x180098e40  jb      short loc_180098E6C
0x180098e42  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180098e47  lea     edx, [rdi+26h]
0x180098e4a  lea     rcx, aBstrcopyconnst; "\"bstrCopyConnString\""
0x180098e51  mov     [rsp+0C0h+szConnStrOut], rcx
0x180098e56  mov     r9d, eax
0x180098e59  mov     r8, r12
0x180098e5c  mov     rcx, cs:WPP_GLOBAL_Control
0x180098e63  mov     rcx, [rcx+10h]
0x180098e67  call    WPP_SF_Ds
0x180098e6c  mov     edi, 8007000Eh
0x180098e71  jmp     loc_180098C1F
0x180098e76  mov     rdx, [r13+50h]
0x180098e7a  lea     rcx, [rbp+57h+var_60]
0x180098e7e  call    ??0?$CBaseStringT@G@@QEAA@PEBG@Z; CBaseStringT<ushort>::CBaseStringT<ushort>(ushort const *)
0x180098e83  nop
0x180098e84  mov     r8d, r15d
0x180098e87  lea     rdx, aTrustedConnect_0; "Trusted_Connection=Yes"
0x180098e8e  mov     rcx, rax
0x180098e91  call    ?Contains@?$CBaseStringT@G@@QEBAHPEBGH@Z; CBaseStringT<ushort>::Contains(ushort const *,int)
0x180098e96  mov     ebx, eax
0x180098e98  lea     rcx, [rbp+57h+var_60]
0x180098e9c  call    ??1?$CBaseStringT@G@@QEAA@XZ; CBaseStringT<ushort>::~CBaseStringT<ushort>(void)
0x180098ea1  test    ebx, ebx
0x180098ea3  jnz     loc_180099046
0x180098ea9  mov     [rbp+57h+arg_18], r15d
0x180098ead  lea     rdx, [rbp+57h+bstrString]; unsigned __int16 **
0x180098eb1  mov     rcx, rdi; unsigned __int16 *
0x180098eb4  call    ?InternalGetSbDbConnStringWithoutPassword@@YAJPEAGPEAPEAG@Z; InternalGetSbDbConnStringWithoutPassword(ushort *,ushort * *)
0x180098eb9  xor     edi, edi
0x180098ebb  test    eax, eax
0x180098ebd  jns     loc_180098F4F
0x180098ec3  mov     rax, cs:WPP_GLOBAL_Control
0x180098eca  cmp     rax, rsi
0x180098ecd  jz      short loc_180098EF9
0x180098ecf  test    [rax+1Ch], r15b
0x180098ed3  jz      short loc_180098EF9
0x180098ed5  cmp     byte ptr [rax+19h], 4
0x180098ed9  jb      short loc_180098EF9
0x180098edb  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180098ee0  mov     rcx, cs:WPP_GLOBAL_Control
0x180098ee7  lea     edx, [rbx+27h]
0x180098eea  mov     r9d, eax
0x180098eed  mov     r8, r12
0x180098ef0  mov     rcx, [rcx+10h]
0x180098ef4  call    WPP_SF_D
0x180098ef9  lea     rcx, pszSrc; psz
0x180098f00  call    cs:__imp_SysAllocString
0x180098f07  nop     dword ptr [rax+rax+00h]
0x180098f0c  mov     [rbp+57h+bstrString], rax
0x180098f10  test    rax, rax
0x180098f13  jnz     short loc_180098F4F
0x180098f15  mov     rax, cs:WPP_GLOBAL_Control
0x180098f1c  cmp     rax, rsi
0x180098f1f  jz      loc_180098E6C
0x180098f25  test    byte ptr [rax+1Ch], 8
0x180098f29  jz      loc_180098E6C
0x180098f2f  cmp     byte ptr [rax+19h], 2
0x180098f33  jb      loc_180098E6C
0x180098f39  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180098f3e  mov     edx, 28h ; '('
0x180098f43  lea     rcx, aBstrdbconnstri; "\"bstrDbConnStringWithoutPswd\""
0x180098f4a  jmp     loc_180098E51
0x180098f4f  lea     rcx, [r13+58h]; this
0x180098f53  cmp     [rcx], rdi
0x180098f56  jz      loc_18009904C
0x180098f5c  call    ?Copy@CComBSTR@ATL@@QEBAPEAGXZ; ATL::CComBSTR::Copy(void)
0x180098f61  mov     [rbp+57h+var_70], rax
0x180098f65  test    rax, rax
0x180098f68  jnz     short loc_180098FA4
0x180098f6a  mov     rcx, cs:WPP_GLOBAL_Control
0x180098f71  cmp     rcx, rsi
0x180098f74  jz      loc_180098E6C
0x180098f7a  test    byte ptr [rcx+1Ch], 8
0x180098f7e  jz      loc_180098E6C
0x180098f84  cmp     byte ptr [rcx+19h], 2
0x180098f88  jb      loc_180098E6C
0x180098f8e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180098f93  mov     edx, 29h ; ')'
0x180098f98  lea     rcx, aBstrcopysecond; "\"bstrCopySecondaryConnString\""
0x180098f9f  jmp     loc_180098E51
0x180098fa4  lea     rdx, [rbp+57h+var_78]; unsigned __int16 **
0x180098fa8  mov     rcx, rax; unsigned __int16 *
0x180098fab  call    ?InternalGetSbDbConnStringWithoutPassword@@YAJPEAGPEAPEAG@Z; InternalGetSbDbConnStringWithoutPassword(ushort *,ushort * *)
0x180098fb0  test    eax, eax
0x180098fb2  jns     loc_18009904C
0x180098fb8  mov     rax, cs:WPP_GLOBAL_Control
0x180098fbf  cmp     rax, rsi
0x180098fc2  jz      short loc_180098FF0
0x180098fc4  test    [rax+1Ch], r15b
0x180098fc8  jz      short loc_180098FF0
0x180098fca  cmp     byte ptr [rax+19h], 4
0x180098fce  jb      short loc_180098FF0
0x180098fd0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180098fd5  mov     rdx, cs:WPP_GLOBAL_Control
0x180098fdc  mov     rcx, [rdx+10h]
0x180098fe0  mov     edx, 2Ah ; '*'
0x180098fe5  mov     r9d, eax
0x180098fe8  mov     r8, r12
0x180098feb  call    WPP_SF_D
0x180098ff0  lea     rcx, pszSrc; psz
0x180098ff7  call    cs:__imp_SysAllocString
0x180098ffe  nop     dword ptr [rax+rax+00h]
0x180099003  mov     [rbp+57h+var_78], rax
0x180099007  test    rax, rax
0x18009900a  jnz     short loc_18009904C
0x18009900c  mov     rax, cs:WPP_GLOBAL_Control
0x180099013  cmp     rax, rsi
0x180099016  jz      loc_180098E6C
0x18009901c  test    byte ptr [rax+1Ch], 8
0x180099020  jz      loc_180098E6C
0x180099026  cmp     byte ptr [rax+19h], 2
0x18009902a  jb      loc_180098E6C
0x180099030  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180099035  mov     edx, 2Bh ; '+'
0x18009903a  lea     rcx, aBstrdbsecondar; "\"bstrDbSecondaryConnStringWithoutPswd"...
0x180099041  jmp     loc_180098E51
0x180099046  mov     [rbp+57h+bstrString], rdi
  ... truncated ...
```
