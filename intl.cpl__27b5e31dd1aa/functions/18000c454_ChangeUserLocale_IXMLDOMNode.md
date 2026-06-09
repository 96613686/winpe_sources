# ChangeUserLocale(IXMLDOMNode *)

- ea: `0x18000c454`
- end: `0x18000c86a`
- name: `?ChangeUserLocale@@YAJPEAUIXMLDOMNode@@@Z`
- size: `1046`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000c870`

## callees

- `0x18000626c`
- `0x18000a860`
- `0x18000aa9c`
- `0x18000ac4c`
- `0x18000c454`
- `0x18000ce98`
- `0x18000d020`
- `0x18000d5d0`
- `0x18000d610`
- `0x18000e690`
- `0x18000e844`
- `0x18000f464`
- `0x18000f4d4`
- `0x180012dc8`
- `0x18002a112`
- `0x18002a150`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c5d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c5d5`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x18000c5cb`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x18000c5cb`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18000c5ad`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18000c6e3`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18000c79a`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18000c5ad`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18000c6e3`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18000c79a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c7e1`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c7ef`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c7fd`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c7e1`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c7ef`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c7fd`
- `KERNEL32!NlsUpdateLocale` at `0x18000c7b5`
- `KERNEL32!NlsUpdateLocale` at `0x18000c7b5`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ChangeUserLocale(struct IXMLDOMNode *a1)
{
  OLECHAR *v2; // rdi
  WCHAR *v3; // r15
  unsigned int v4; // r8d
  unsigned int Attribute; // ebx
  unsigned __int16 ***v6; // rax
  unsigned __int16 *v7; // rdx
  int v8; // r14d
  unsigned int v9; // r8d
  __int64 v10; // rdx
  DWORD LastError; // eax
  unsigned int v12; // r8d
  unsigned int v13; // esi
  unsigned __int16 ***v14; // rax
  unsigned __int16 *v15; // rdx
  unsigned int v16; // r8d
  unsigned __int16 *v17; // rdx
  __int64 v18; // rdx
  int lpString2; // [rsp+20h] [rbp-E0h]
  LPCWCH lpString1; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v22[8]; // [rsp+58h] [rbp-A8h] BYREF
  LPCWCH v23; // [rsp+60h] [rbp-A0h] BYREF
  LPCWCH v24; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v25[42]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR LCData[88]; // [rsp+1C0h] [rbp+C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  lpString1 = 0;
  v2 = 0;
  v23 = 0;
  v3 = 0;
  v24 = 0;
  memset_0(LCData, 0, 0xAAu);
  wil::ActivityBase<IntlCplTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<IntlCplTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v25,
    "ChangeUserLocale");
  v25[0] = &IntlCplTraceLoggingTelemetry::ChangeUserLocale::`vftable';
  IntlCplTraceLoggingTelemetry::ChangeUserLocale::StartActivity((IntlCplTraceLoggingTelemetry::ChangeUserLocale *)v25);
  if ( !a1 )
  {
    Attribute = -2147024809;
    wil::details::in1diag3::Log_Hr(retaddr, (void *)0x23E, v4, (const char *)0x80070057LL, lpString2);
    goto LABEL_46;
  }
  v6 = (unsigned __int16 ***)_bstr_t::_bstr_t((_bstr_t *)v22, NAME_ATTR);
  if ( *v6 )
    v7 = **v6;
  else
    v7 = 0;
  Attribute = GetAttribute(a1, v7, (unsigned __int16 **)&lpString1);
  _bstr_t::_Free((_bstr_t *)v22);
  v8 = 1;
  if ( Attribute != 1 )
  {
    if ( !(unsigned int)CheckHR(Attribute) )
    {
      v10 = 593;
LABEL_9:
      wil::details::in1diag3::Log_Hr(retaddr, (void *)v10, v9, (const char *)Attribute, lpString2);
      goto LABEL_40;
    }
    if ( CompareStringEx(&LocaleName, 0x10u, lpString1, -1, CURRENT, -1, 0, 0, 0) == 2 )
    {
      if ( !GetLocaleInfoW(0x400u, 0x5Cu, LCData, 85) )
      {
        LastError = GetLastError();
        wil::details::in1diag3::Log_Win32(retaddr, (void *)0x269, v12, (const char *)LastError, lpString2);
        goto LABEL_40;
      }
      v13 = 0;
    }
    else
    {
      Attribute = StringCchCopyW(LCData, 0x55u, lpString1);
      if ( !(unsigned int)CheckHR(Attribute) )
      {
        v10 = 628;
        goto LABEL_9;
      }
      v13 = 1;
      v8 = 0;
    }
    v14 = (unsigned __int16 ***)_bstr_t::_bstr_t((_bstr_t *)v22, SETASCURRENT_ATTR);
    if ( *v14 )
      v15 = **v14;
    else
      v15 = 0;
    Attribute = GetAttribute(a1, v15, (unsigned __int16 **)&v23);
    _bstr_t::_Free((_bstr_t *)v22);
    if ( !(unsigned int)CheckHR(Attribute) )
    {
      wil::details::in1diag3::Log_Hr(retaddr, (void *)0x283, v16, (const char *)Attribute, lpString2);
LABEL_22:
      v2 = (OLECHAR *)v23;
      goto LABEL_40;
    }
    if ( Attribute == 1 && !v8 )
      goto LABEL_22;
    v2 = (OLECHAR *)v23;
    if ( !v8 )
    {
      if ( CompareStringEx(&LocaleName, 0x10u, v23, -1, FALSE_ATTR, -1, 0, 0, 0) == 2 )
        goto LABEL_27;
      v13 = 1;
    }
    v17 = *(unsigned __int16 **)_bstr_t::_bstr_t((_bstr_t *)v22, RESET_ATTR);
    if ( v17 )
      v17 = *(unsigned __int16 **)v17;
    Attribute = GetAttribute(a1, v17, (unsigned __int16 **)&v24);
    _bstr_t::_Free((_bstr_t *)v22);
    v3 = (WCHAR *)v24;
    if ( Attribute == 1 )
    {
      Attribute = 0;
    }
    else
    {
      if ( !(unsigned int)CheckHR(Attribute) )
      {
        v10 = 685;
        goto LABEL_9;
      }
      if ( CompareStringEx(&LocaleName, 0x10u, v3, -1, TRUE_ATTR, -1, 0, 0, 0) == 2 )
        v13 |= 6u;
    }
    if ( !v13 )
      goto LABEL_40;
    if ( !(unsigned int)NlsUpdateLocale(LCData, v13) )
    {
      Input_InstallLayout(0, LCData, 0);
      goto LABEL_40;
    }
LABEL_27:
    Attribute = 1;
  }
LABEL_40:
  if ( lpString1 )
    SysFreeString((BSTR)lpString1);
  if ( v3 )
    SysFreeString(v3);
  if ( v2 )
    SysFreeString(v2);
LABEL_46:
  if ( (Attribute & 0x80000000) == 0 )
  {
    v18 = 0;
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2D6,
      (unsigned int)"shell\\osshell\\cpls\\intl\\cme.cpp",
      (const char *)Attribute,
      lpString2);
    v18 = Attribute;
  }
  wil::ActivityBase<IntlCplTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v25, v18);
  IntlCplTraceLoggingTelemetry::ChangeUserLocale::~ChangeUserLocale((IntlCplTraceLoggingTelemetry::ChangeUserLocale *)v25);
  return Attribute;
}

```

## disassembly

```asm
0x18000c454  mov     [rsp-8+arg_8], rbx
0x18000c459  mov     [rsp-8+arg_10], rsi
0x18000c45e  push    rbp
0x18000c45f  push    rdi
0x18000c460  push    r13
0x18000c462  push    r14
0x18000c464  push    r15
0x18000c466  lea     rbp, [rsp-180h]
0x18000c46e  sub     rsp, 280h
0x18000c475  mov     rax, cs:__security_cookie
0x18000c47c  xor     rax, rsp
0x18000c47f  mov     [rbp+1A0h+var_30], rax
0x18000c486  mov     r13, rcx
0x18000c489  mov     [rsp+2A0h+lpString1], 0
0x18000c492  xor     edi, edi
0x18000c494  mov     [rsp+2A0h+var_240], rdi
0x18000c499  xor     r15d, r15d
0x18000c49c  mov     [rsp+2A0h+var_238], r15
0x18000c4a1  xor     edx, edx; Val
0x18000c4a3  mov     r8d, 0AAh; Size
0x18000c4a9  lea     rcx, [rbp+1A0h+LCData]; void *
0x18000c4b0  call    memset_0
0x18000c4b5  lea     rdx, aChangeuserloca; "ChangeUserLocale"
0x18000c4bc  lea     rcx, [rsp+2A0h+var_230]
0x18000c4c1  call    ??0?$ActivityBase@VIntlCplTraceLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<IntlCplTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<IntlCplTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18000c4c6  lea     rax, ??_7ChangeUserLocale@IntlCplTraceLoggingTelemetry@@6B@; const IntlCplTraceLoggingTelemetry::ChangeUserLocale::`vftable'
0x18000c4cd  mov     [rsp+2A0h+var_230], rax
0x18000c4d2  lea     rcx, [rsp+2A0h+var_230]; this
0x18000c4d7  call    ?StartActivity@ChangeUserLocale@IntlCplTraceLoggingTelemetry@@QEAAXXZ; IntlCplTraceLoggingTelemetry::ChangeUserLocale::StartActivity(void)
0x18000c4dc  nop
0x18000c4dd  test    r13, r13
0x18000c4e0  jnz     short loc_18000C500
0x18000c4e2  mov     ebx, 80070057h
0x18000c4e7  mov     rcx, [rbp+1A8h]; this
0x18000c4ee  mov     r9d, ebx; char *
0x18000c4f1  mov     edx, 23Eh; void *
0x18000c4f6  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18000c4fb  jmp     loc_18000C803
0x18000c500  lea     rdx, ?NAME_ATTR@@3PAGA; "Name"
0x18000c507  lea     rcx, [rsp+2A0h+var_248]; this
0x18000c50c  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18000c511  nop
0x18000c512  mov     rcx, [rax]
0x18000c515  test    rcx, rcx
0x18000c518  jz      short loc_18000C51F
0x18000c51a  mov     rdx, [rcx]
0x18000c51d  jmp     short loc_18000C521
0x18000c51f  xor     edx, edx; unsigned __int16 *
0x18000c521  lea     r8, [rsp+2A0h+lpString1]; unsigned __int16 **
0x18000c526  mov     rcx, r13; struct IXMLDOMNode *
0x18000c529  call    ?GetAttribute@@YAJPEAUIXMLDOMNode@@PEAGPEAPEAG@Z; GetAttribute(IXMLDOMNode *,ushort *,ushort * *)
0x18000c52e  mov     ebx, eax
0x18000c530  lea     rcx, [rsp+2A0h+var_248]; this
0x18000c535  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000c53a  mov     r14d, 1
0x18000c540  cmp     ebx, r14d
0x18000c543  jz      loc_18000C7D4
0x18000c549  mov     ecx, ebx; int
0x18000c54b  call    ?CheckHR@@YAHJ@Z; CheckHR(long)
0x18000c550  test    eax, eax
0x18000c552  jnz     short loc_18000C56D
0x18000c554  mov     edx, 251h; void *
0x18000c559  mov     rcx, [rbp+1A8h]; this
0x18000c560  mov     r9d, ebx; char *
0x18000c563  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18000c568  jmp     loc_18000C7D4
0x18000c56d  mov     [rsp+2A0h+lParam], 0; lParam
0x18000c576  mov     [rsp+2A0h+lpReserved], 0; lpReserved
0x18000c57f  mov     [rsp+2A0h+lpVersionInformation], 0; lpVersionInformation
0x18000c588  or      ecx, 0FFFFFFFFh
0x18000c58b  mov     [rsp+2A0h+cchCount2], ecx; cchCount2
0x18000c58f  lea     rax, ?CURRENT@@3PAGA; "Current"
0x18000c596  mov     [rsp+2A0h+lpString2], rax; int
0x18000c59b  mov     r9d, ecx; cchCount1
0x18000c59e  mov     r8, [rsp+2A0h+lpString1]; lpString1
0x18000c5a3  lea     edx, [rcx+11h]; dwCmpFlags
0x18000c5a6  lea     rcx, LocaleName; lpLocaleName
0x18000c5ad  call    cs:__imp_CompareStringEx
0x18000c5b3  cmp     eax, 2
0x18000c5b6  jnz     short loc_18000C5F8
0x18000c5b8  lea     r9d, [rax+53h]; cchData
0x18000c5bc  lea     r8, [rbp+1A0h+LCData]; lpLCData
0x18000c5c3  lea     edx, [rax+5Ah]; LCType
0x18000c5c6  mov     ecx, 400h; Locale
0x18000c5cb  call    cs:__imp_GetLocaleInfoW
0x18000c5d1  test    eax, eax
0x18000c5d3  jnz     short loc_18000C5F4
0x18000c5d5  call    cs:__imp_GetLastError
0x18000c5db  mov     rcx, [rbp+1A8h]; this
0x18000c5e2  mov     r9d, eax; char *
0x18000c5e5  mov     edx, 269h; void *
0x18000c5ea  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x18000c5ef  jmp     loc_18000C7D4
0x18000c5f4  xor     esi, esi
0x18000c5f6  jmp     short loc_18000C62B
0x18000c5f8  mov     r8, [rsp+2A0h+lpString1]; unsigned __int16 *
0x18000c5fd  mov     edx, 55h ; 'U'; unsigned __int64
0x18000c602  lea     rcx, [rbp+1A0h+LCData]; unsigned __int16 *
0x18000c609  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000c60e  mov     ebx, eax
0x18000c610  mov     ecx, eax; int
0x18000c612  call    ?CheckHR@@YAHJ@Z; CheckHR(long)
0x18000c617  test    eax, eax
0x18000c619  jnz     short loc_18000C625
0x18000c61b  mov     edx, 274h
0x18000c620  jmp     loc_18000C559
0x18000c625  mov     esi, r14d
0x18000c628  xor     r14d, r14d
0x18000c62b  lea     rdx, ?SETASCURRENT_ATTR@@3PAGA; "SetAsCurrent"
0x18000c632  lea     rcx, [rsp+2A0h+var_248]; this
0x18000c637  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18000c63c  nop
0x18000c63d  mov     rcx, [rax]
0x18000c640  test    rcx, rcx
0x18000c643  jz      short loc_18000C64A
0x18000c645  mov     rdx, [rcx]
0x18000c648  jmp     short loc_18000C64C
0x18000c64a  xor     edx, edx; unsigned __int16 *
0x18000c64c  lea     r8, [rsp+2A0h+var_240]; unsigned __int16 **
0x18000c651  mov     rcx, r13; struct IXMLDOMNode *
0x18000c654  call    ?GetAttribute@@YAJPEAUIXMLDOMNode@@PEAGPEAPEAG@Z; GetAttribute(IXMLDOMNode *,ushort *,ushort * *)
0x18000c659  mov     ebx, eax
0x18000c65b  lea     rcx, [rsp+2A0h+var_248]; this
0x18000c660  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000c665  mov     ecx, ebx; int
0x18000c667  call    ?CheckHR@@YAHJ@Z; CheckHR(long)
0x18000c66c  test    eax, eax
0x18000c66e  jnz     short loc_18000C68E
0x18000c670  mov     rcx, [rbp+1A8h]; this
0x18000c677  mov     r9d, ebx; char *
0x18000c67a  mov     edx, 283h; void *
0x18000c67f  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18000c684  mov     rdi, [rsp+2A0h+var_240]
0x18000c689  jmp     loc_18000C7D4
0x18000c68e  cmp     ebx, 1
0x18000c691  jnz     short loc_18000C698
0x18000c693  test    r14d, r14d
0x18000c696  jz      short loc_18000C684
0x18000c698  mov     rdi, [rsp+2A0h+var_240]
0x18000c69d  test    r14d, r14d
0x18000c6a0  jnz     short loc_18000C6FF
0x18000c6a2  mov     [rsp+2A0h+lParam], 0; lParam
0x18000c6ab  mov     [rsp+2A0h+lpReserved], 0; lpReserved
0x18000c6b4  mov     [rsp+2A0h+lpVersionInformation], 0; lpVersionInformation
0x18000c6bd  or      r14d, 0FFFFFFFFh
0x18000c6c1  mov     [rsp+2A0h+cchCount2], r14d; cchCount2
0x18000c6c6  lea     rax, ?FALSE_ATTR@@3PAGA; "false"
0x18000c6cd  mov     [rsp+2A0h+lpString2], rax; lpString2
0x18000c6d2  mov     r9d, r14d; cchCount1
0x18000c6d5  mov     r8, rdi; lpString1
0x18000c6d8  lea     edx, [r14+11h]; dwCmpFlags
0x18000c6dc  lea     rcx, LocaleName; lpLocaleName
0x18000c6e3  call    cs:__imp_CompareStringEx
0x18000c6e9  cmp     eax, 2
0x18000c6ec  jnz     short loc_18000C6F8
0x18000c6ee  mov     ebx, 1
0x18000c6f3  jmp     loc_18000C7D4
0x18000c6f8  mov     esi, 1
0x18000c6fd  jmp     short loc_18000C703
0x18000c6ff  or      r14d, 0FFFFFFFFh
0x18000c703  lea     rdx, ?RESET_ATTR@@3PAGA; "ResetAllSettings"
0x18000c70a  lea     rcx, [rsp+2A0h+var_248]; this
0x18000c70f  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18000c714  nop
0x18000c715  mov     rdx, [rax]
0x18000c718  test    rdx, rdx
0x18000c71b  jz      short loc_18000C720
0x18000c71d  mov     rdx, [rdx]; unsigned __int16 *
0x18000c720  lea     r8, [rsp+2A0h+var_238]; unsigned __int16 **
0x18000c725  mov     rcx, r13; struct IXMLDOMNode *
0x18000c728  call    ?GetAttribute@@YAJPEAUIXMLDOMNode@@PEAGPEAPEAG@Z; GetAttribute(IXMLDOMNode *,ushort *,ushort * *)
0x18000c72d  mov     ebx, eax
0x18000c72f  lea     rcx, [rsp+2A0h+var_248]; this
0x18000c734  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000c739  mov     r15, [rsp+2A0h+var_238]
0x18000c73e  cmp     ebx, 1
0x18000c741  jnz     short loc_18000C747
0x18000c743  xor     ebx, ebx
0x18000c745  jmp     short loc_18000C7A8
0x18000c747  mov     ecx, ebx; int
0x18000c749  call    ?CheckHR@@YAHJ@Z; CheckHR(long)
0x18000c74e  test    eax, eax
0x18000c750  jnz     short loc_18000C75C
0x18000c752  mov     edx, 2ADh
0x18000c757  jmp     loc_18000C559
0x18000c75c  mov     [rsp+2A0h+lParam], 0; lParam
0x18000c765  mov     [rsp+2A0h+lpReserved], 0; lpReserved
0x18000c76e  mov     [rsp+2A0h+lpVersionInformation], 0; lpVersionInformation
0x18000c777  mov     [rsp+2A0h+cchCount2], r14d; cchCount2
0x18000c77c  lea     rax, ?TRUE_ATTR@@3PAGA; "true"
0x18000c783  mov     [rsp+2A0h+lpString2], rax; int
0x18000c788  mov     r9d, r14d; cchCount1
0x18000c78b  mov     r8, r15; lpString1
0x18000c78e  mov     edx, 10h; dwCmpFlags
0x18000c793  lea     rcx, LocaleName; lpLocaleName
0x18000c79a  call    cs:__imp_CompareStringEx
0x18000c7a0  cmp     eax, 2
0x18000c7a3  jnz     short loc_18000C7A8
0x18000c7a5  or      esi, 6
0x18000c7a8  test    esi, esi
0x18000c7aa  jz      short loc_18000C7D4
0x18000c7ac  mov     edx, esi
0x18000c7ae  lea     rcx, [rbp+1A0h+LCData]
0x18000c7b5  call    cs:__imp_NlsUpdateLocale
0x18000c7bb  test    eax, eax
0x18000c7bd  jnz     loc_18000C6EE
0x18000c7c3  xor     r8d, r8d; unsigned int
0x18000c7c6  lea     rdx, [rbp+1A0h+LCData]; lpLocaleName
0x18000c7cd  xor     ecx, ecx; hWnd
0x18000c7cf  call    ?Input_InstallLayout@@YAHPEAUHWND__@@PEBGK@Z; Input_InstallLayout(HWND__ *,ushort const *,ulong)
0x18000c7d4  cmp     [rsp+2A0h+lpString1], 0
0x18000c7da  jz      short loc_18000C7E7
0x18000c7dc  mov     rcx, [rsp+2A0h+lpString1]; bstrString
0x18000c7e1  call    cs:__imp_SysFreeString
0x18000c7e7  test    r15, r15
0x18000c7ea  jz      short loc_18000C7F5
0x18000c7ec  mov     rcx, r15; bstrString
0x18000c7ef  call    cs:__imp_SysFreeString
0x18000c7f5  test    rdi, rdi
0x18000c7f8  jz      short loc_18000C803
0x18000c7fa  mov     rcx, rdi; bstrString
0x18000c7fd  call    cs:__imp_SysFreeString
0x18000c803  mov     rcx, [rbp+1A8h]; this
0x18000c80a  test    ebx, ebx
0x18000c80c  jns     short loc_18000C826
0x18000c80e  mov     r9d, ebx; char *
0x18000c811  lea     r8, aShellOsshellCp_0; "shell\\osshell\\cpls\\intl\\cme.cpp"
0x18000c818  mov     edx, 2D6h; void *
0x18000c81d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000c822  mov     edx, ebx
0x18000c824  jmp     short loc_18000C828
0x18000c826  xor     edx, edx
0x18000c828  lea     rcx, [rsp+2A0h+var_230]
0x18000c82d  call    ?Stop@?$ActivityBase@VIntlCplTraceLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<IntlCplTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18000c832  nop
0x18000c833  lea     rcx, [rsp+2A0h+var_230]; this
0x18000c838  call    ??1ChangeUserLocale@IntlCplTraceLoggingTelemetry@@QEAA@XZ; IntlCplTraceLoggingTelemetry::ChangeUserLocale::~ChangeUserLocale(void)
0x18000c83d  mov     eax, ebx
0x18000c83f  mov     rcx, [rbp+1A0h+var_30]
0x18000c846  xor     rcx, rsp; StackCookie
0x18000c849  call    __security_check_cookie
0x18000c84e  lea     r11, [rsp+2A0h+var_20]
0x18000c856  mov     rbx, [r11+38h]
0x18000c85a  mov     rsi, [r11+40h]
0x18000c85e  mov     rsp, r11
0x18000c861  pop     r15
0x18000c863  pop     r14
0x18000c865  pop     r13
0x18000c867  pop     rdi
0x18000c868  pop     rbp
0x18000c869  retn
```
