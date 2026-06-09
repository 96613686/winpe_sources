# CRemoteAssistanceApp::CreateTicketThroughObject(int)

- ea: `0x14000fcb4`
- end: `0x14001009b`
- name: `?CreateTicketThroughObject@CRemoteAssistanceApp@@QEAAJH@Z`
- size: `999`
- prototype: `__int64 __fastcall(CRemoteAssistanceApp *__hidden this, int)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140012794`

## callees

- `0x140001cc4`
- `0x1400044f8`
- `0x14000fcb4`
- `0x140029418`
- `0x140029978`
- `0x14002c0a4`
- `0x140034ce4`
- `0x140034eac`
- `0x14003c120`
- `0x14003fbc4`
- `0x14003fe58`
- `0x14003ff50`
- `0x140040390`
- `0x140041058`
- `0x14004d010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x14000fffb`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000fffb`
- `ole32!CoCreateInstance` at `0x14000fd0c`
- `ole32!CoCreateInstance` at `0x14000fd0c`
- `OLEAUT32!__imp_SysAllocString` at `0x14000fd71`
- `OLEAUT32!__imp_SysAllocString` at `0x14000fd71`
- `OLEAUT32!__imp_SysFreeString` at `0x14000fda0`
- `OLEAUT32!__imp_SysFreeString` at `0x140010010`
- `OLEAUT32!__imp_SysFreeString` at `0x140010032`
- `OLEAUT32!__imp_SysFreeString` at `0x140010059`
- `OLEAUT32!__imp_SysFreeString` at `0x140010069`
- `OLEAUT32!__imp_SysFreeString` at `0x14000fda0`
- `OLEAUT32!__imp_SysFreeString` at `0x140010010`
- `OLEAUT32!__imp_SysFreeString` at `0x140010032`
- `OLEAUT32!__imp_SysFreeString` at `0x140010059`
- `OLEAUT32!__imp_SysFreeString` at `0x140010069`

## string_xrefs

- `0x14000fd28`: `CRemoteAssistanceApp::CreateTicketThroughObject`
- `0x14000fe8f`: `CRemoteAssistanceApp::CreateTicketThroughObject`
- `0x14000fede`: `CRemoteAssistanceApp::CreateTicketThroughObject`
- `0x14000ff4e`: `CRemoteAssistanceApp::CreateTicketThroughObject`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CRemoteAssistanceApp::CreateTicketThroughObject(struct CRATicket **this, int a2)
{
  unsigned __int16 *v4; // rbx
  unsigned __int16 *v5; // rdi
  HRESULT inited; // eax
  CEventLogger *v7; // rcx
  struct CReadWriteLock *v8; // r8
  int RAConnectionString; // esi
  unsigned int v10; // r9d
  void (*v11)(int); // r8
  LPVOID v12; // r12
  __int64 v13; // r13
  BSTR v14; // rax
  OLECHAR *v15; // r14
  int v16; // r13d
  CRAEncryption *v17; // rax
  CEventLogger *v18; // rcx
  CRAEncryption *v19; // r14
  signed int UserPassword; // eax
  CEventLogger *v21; // rcx
  signed int v22; // eax
  CEventLogger *v23; // rcx
  unsigned __int16 *v24; // rdx
  signed int v25; // eax
  CEventLogger *v26; // rcx
  CEventLogger *v27; // rcx
  int v28; // eax
  void (*v30)(int); // [rsp+28h] [rbp-38h]
  void (*v31)(unsigned __int16 *, unsigned __int16 *); // [rsp+30h] [rbp-30h]
  BSTR Src; // [rsp+40h] [rbp-20h] BYREF
  unsigned __int16 *v33; // [rsp+48h] [rbp-18h] BYREF
  unsigned __int16 *v34; // [rsp+50h] [rbp-10h] BYREF
  BSTR v35; // [rsp+58h] [rbp-8h]
  BSTR bstrString; // [rsp+B0h] [rbp+50h] BYREF
  LPVOID ppv; // [rsp+B8h] [rbp+58h] BYREF

  v4 = 0;
  v33 = 0;
  Src = 0;
  ppv = 0;
  v5 = 0;
  v34 = 0;
  bstrString = 0;
  inited = CoCreateInstance(&CLSID_RemoteAssistance, 0, 4u, &GUID_59308e66_7cde_478a_8eba_4d73fdce3545, &ppv);
  RAConnectionString = inited;
  if ( inited < 0 )
  {
    v10 = 1131;
LABEL_3:
    CEventLogger::LogError(
      v7,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\app.cpp",
      v10,
      L"CRemoteAssistanceApp::CreateTicketThroughObject",
      inited);
    goto LABEL_29;
  }
  RAConnectionString = GetRAConnectionString(&Src, this[104], v8);
  if ( RAConnectionString >= 0 )
  {
    v16 = *(_DWORD *)(*((_QWORD *)_AtlModule + 104) + 136LL);
    if ( v16 == 3 )
    {
      inited = CRATicket::InitRDPEventsNovice(
                 this[104],
                 (void (__high *)(void *, enum _STATUS))&OfferRAOnAttendeeConnectedProc,
                 v11,
                 wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy,
                 wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy,
                 v30,
                 v31);
      RAConnectionString = inited;
      if ( inited < 0 )
      {
        v10 = 1180;
        goto LABEL_3;
      }
    }
    if ( a2 == 1 )
    {
      v17 = (CRAEncryption *)operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
      v19 = v17;
      v35 = (BSTR)v17;
      if ( !v17 )
      {
        RAConnectionString = -2147024882;
        CEventLogger::LogError(
          v18,
          &Recoverable_Error,
          L"base\\diagnosis\\ra\\ui\\app.cpp",
          0x4A3u,
          L"CRemoteAssistanceApp::CreateTicketThroughObject",
          0x8007000E);
        goto LABEL_29;
      }
      *(_QWORD *)v17 = 0;
      *((_QWORD *)v17 + 1) = 0;
      *((_QWORD *)v17 + 2) = 0;
      *((_QWORD *)v17 + 3) = 0;
      *((_QWORD *)v17 + 4) = 0;
      *((_QWORD *)v17 + 5) = 0;
      UserPassword = CRATicket::get_UserPassword(this[104], &v33, 0);
      RAConnectionString = UserPassword;
      if ( UserPassword < 0 )
      {
        CEventLogger::LogError(
          v21,
          &Recoverable_Error,
          L"base\\diagnosis\\ra\\ui\\app.cpp",
          0x4A5u,
          L"CRemoteAssistanceApp::CreateTicketThroughObject",
          UserPassword);
        v4 = v33;
        goto LABEL_28;
      }
      v4 = v33;
      v22 = CRAEncryption::EncryptTicket(v19, v33, Src, &v34);
      RAConnectionString = v22;
      if ( v22 < 0 )
      {
        CEventLogger::LogError(
          v23,
          &Recoverable_Error,
          L"base\\diagnosis\\ra\\ui\\app.cpp",
          0x4AEu,
          L"CRemoteAssistanceApp::CreateTicketThroughObject",
          v22);
        v5 = v34;
        goto LABEL_28;
      }
      v5 = v34;
      v24 = v34;
    }
    else
    {
      v19 = 0;
      v24 = Src;
    }
    v25 = (*(__int64 (__fastcall **)(LPVOID, unsigned __int16 *))(*(_QWORD *)ppv + 72LL))(ppv, v24);
    RAConnectionString = v25;
    if ( v25 >= 0 )
    {
      if ( (unsigned int)(v16 - 5) <= 1 )
      {
        RAConnectionString = (*(__int64 (__fastcall **)(LPVOID, BSTR *))(*(_QWORD *)ppv + 120LL))(ppv, &bstrString);
        CRATicket::put_ExpertName(*((CRATicket **)_AtlModule + 104), bstrString);
        v28 = 111;
      }
      else
      {
        GetUserInfoAsBSTR(1, &bstrString);
        CRATicket::put_NoviceName(*((CRATicket **)_AtlModule + 104), bstrString);
        v28 = 32;
      }
      *((_DWORD *)this + 205) = v28;
      CEventLogger::LogEvent(v27, &Invitation_Opened);
    }
    else
    {
      CEventLogger::LogError(
        v26,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\ui\\app.cpp",
        0x4BBu,
        L"CRemoteAssistanceApp::CreateTicketThroughObject",
        v25);
    }
    if ( !v19 )
      goto LABEL_29;
LABEL_28:
    CRAEncryption::~CRAEncryption(v19);
    operator delete(v19);
    goto LABEL_29;
  }
  v12 = ppv;
  v13 = *(_QWORD *)ppv;
  v14 = SysAllocString(&String);
  v15 = v14;
  v35 = v14;
  if ( !v14 )
    ATL::AtlThrowImpl(-2147024882);
  (*(void (__fastcall **)(LPVOID, BSTR))(v13 + 72))(v12, v14);
  SysFreeString(v15);
  if ( RAConnectionString == -2147483099 )
    ShowErrorMessage(0x278u, 0x279u, 0, 0, 0, 0);
LABEL_29:
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( RAConnectionString < 0 )
    *((_DWORD *)this + 205) = -1;
  SysFreeString(v5);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  SysFreeString(Src);
  SysFreeString(v4);
  return (unsigned int)RAConnectionString;
}

```

## disassembly

```asm
0x14000fcb4  mov     [rsp-38h+arg_0], rbx
0x14000fcb9  push    rbp
0x14000fcba  push    rsi
0x14000fcbb  push    rdi
0x14000fcbc  push    r12
0x14000fcbe  push    r13
0x14000fcc0  push    r14
0x14000fcc2  push    r15
0x14000fcc4  mov     rbp, rsp
0x14000fcc7  sub     rsp, 60h
0x14000fccb  mov     r14d, edx
0x14000fcce  mov     r15, rcx
0x14000fcd1  xor     r12d, r12d
0x14000fcd4  mov     ebx, r12d
0x14000fcd7  mov     [rbp+var_18], rbx
0x14000fcdb  mov     [rbp+Src], r12
0x14000fcdf  mov     [rbp+arg_18], r12
0x14000fce3  mov     edi, r12d
0x14000fce6  mov     [rbp+var_10], r12
0x14000fcea  mov     [rbp+bstrString], r12
0x14000fcee  lea     rax, [rbp+arg_18]
0x14000fcf2  mov     [rsp+60h+ppv], rax; ppv
0x14000fcf7  lea     r9, _GUID_59308e66_7cde_478a_8eba_4d73fdce3545; riid
0x14000fcfe  xor     edx, edx; pUnkOuter
0x14000fd00  lea     r8d, [r12+4]; dwClsContext
0x14000fd05  lea     rcx, CLSID_RemoteAssistance; rclsid
0x14000fd0c  call    cs:__imp_CoCreateInstance
0x14000fd13  nop     dword ptr [rax+rax+00h]
0x14000fd18  mov     esi, eax
0x14000fd1a  test    eax, eax
0x14000fd1c  jns     short loc_14000FD4C
0x14000fd1e  mov     r9d, 46Bh; unsigned int
0x14000fd24  mov     dword ptr [rsp+60h+var_38], eax; unsigned int
0x14000fd28  lea     rax, aCremoteassista_8; "CRemoteAssistanceApp::CreateTicketThrou"...
0x14000fd2f  mov     [rsp+60h+ppv], rax; unsigned __int16 *
0x14000fd34  lea     r8, aBaseDiagnosisR_14; "base\\diagnosis\\ra\\ui\\app.cpp"
0x14000fd3b  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x14000fd42  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14000fd47  jmp     loc_140010007
0x14000fd4c  mov     rdx, [r15+340h]; this
0x14000fd53  lea     rcx, [rbp+Src]; unsigned __int16 **
0x14000fd57  call    ?GetRAConnectionString@@YAJPEAPEAGPEAVCRATicket@@PEAVCReadWriteLock@@@Z; GetRAConnectionString(ushort * *,CRATicket *,CReadWriteLock *)
0x14000fd5c  mov     esi, eax
0x14000fd5e  test    eax, eax
0x14000fd60  jns     short loc_14000FDDD
0x14000fd62  mov     r12, [rbp+arg_18]
0x14000fd66  mov     r13, [r12]
0x14000fd6a  lea     rcx, String; psz
0x14000fd71  call    cs:__imp_SysAllocString
0x14000fd78  nop     dword ptr [rax+rax+00h]
0x14000fd7d  mov     r14, rax
0x14000fd80  mov     [rbp+var_8], rax
0x14000fd84  test    rax, rax
0x14000fd87  jz      loc_140010090
0x14000fd8d  mov     rdx, rax
0x14000fd90  mov     rcx, r12
0x14000fd93  mov     rax, [r13+48h]
0x14000fd97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fd9c  nop
0x14000fd9d  mov     rcx, r14; bstrString
0x14000fda0  call    cs:__imp_SysFreeString
0x14000fda7  nop     dword ptr [rax+rax+00h]
0x14000fdac  xor     r12d, r12d
0x14000fdaf  cmp     esi, 80000225h
0x14000fdb5  jnz     loc_140010007
0x14000fdbb  mov     dword ptr [rsp+60h+var_38], r12d; int
0x14000fdc0  mov     [rsp+60h+ppv], r12; unsigned __int16 *
0x14000fdc5  xor     r9d, r9d; int
0x14000fdc8  xor     r8d, r8d; HWND
0x14000fdcb  mov     edx, 279h; int
0x14000fdd0  lea     ecx, [rdx-1]; int
0x14000fdd3  call    ?ShowErrorMessage@@YAJHHPEAUHWND__@@JPEBGH@Z; ShowErrorMessage(int,int,HWND__ *,long,ushort const *,int)
0x14000fdd8  jmp     loc_140010007
0x14000fddd  mov     rax, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14000fde4  mov     rcx, [rax+340h]
0x14000fdeb  mov     r13d, [rcx+88h]
0x14000fdf2  cmp     r13d, 3
0x14000fdf6  jnz     short loc_14000FE28
0x14000fdf8  lea     r9, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; void (*)(void *, enum __MIDL___MIDL_itf_rdpencomapi_0000_0000_0001)
0x14000fdff  mov     [rsp+60h+ppv], r9; void (*)(void *, enum __MIDL___MIDL_itf_rdpencomapi_0000_0000_0001)
0x14000fe04  lea     rdx, ?OfferRAOnAttendeeConnectedProc@@YAXPEAXW4_STATUS@@@Z; void (__high *)(void *, enum _STATUS)
0x14000fe0b  mov     rcx, [r15+340h]; this
0x14000fe12  call    ?InitRDPEventsNovice@CRATicket@@QEAAJP6AXPEAXW4_STATUS@@@ZP6AXJ@ZP6AX0W4__MIDL___MIDL_itf_rdpencomapi_0000_0000_0001@@@Z5P6AXH@ZP6AXPEAG7@Z@Z; CRATicket::InitRDPEventsNovice(void (*)(void *,_STATUS),void (*)(long),void (*)(void *,__MIDL___MIDL_itf_rdpencomapi_0000_0000_0001),void (*)(void *,__MIDL___MIDL_itf_rdpencomapi_0000_0000_0001),void (*)(int),void (*)(ushort *,ushort *))
0x14000fe17  mov     esi, eax
0x14000fe19  test    eax, eax
0x14000fe1b  jns     short loc_14000FE28
0x14000fe1d  mov     r9d, 49Ch
0x14000fe23  jmp     loc_14000FD24
0x14000fe28  cmp     r14d, 1
0x14000fe2c  jnz     loc_14000FF2D
0x14000fe32  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000fe39  lea     ecx, [r14+2Fh]; unsigned __int64
0x14000fe3d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14000fe42  mov     r14, rax
0x14000fe45  mov     [rbp+var_8], rax
0x14000fe49  test    rax, rax
0x14000fe4c  jz      loc_14000FF15
0x14000fe52  mov     [rax], r12
0x14000fe55  mov     [rax+8], r12
0x14000fe59  mov     [rax+10h], r12
0x14000fe5d  mov     [rax+18h], r12
0x14000fe61  mov     [rax+20h], r12
0x14000fe65  mov     [rax+28h], r12
0x14000fe69  test    rax, rax
0x14000fe6c  jz      loc_14000FF15
0x14000fe72  xor     r8d, r8d; int
0x14000fe75  lea     rdx, [rbp+var_18]; unsigned __int16 **
0x14000fe79  mov     rcx, [r15+340h]; this
0x14000fe80  call    ?get_UserPassword@CRATicket@@QEAAJPEAPEAGH@Z; CRATicket::get_UserPassword(ushort * *,int)
0x14000fe85  mov     esi, eax
0x14000fe87  test    eax, eax
0x14000fe89  jns     short loc_14000FEBD
0x14000fe8b  mov     dword ptr [rsp+60h+var_38], eax; unsigned int
0x14000fe8f  lea     rax, aCremoteassista_8; "CRemoteAssistanceApp::CreateTicketThrou"...
0x14000fe96  mov     [rsp+60h+ppv], rax; unsigned __int16 *
0x14000fe9b  mov     r9d, 4A5h; unsigned int
0x14000fea1  lea     r8, aBaseDiagnosisR_14; "base\\diagnosis\\ra\\ui\\app.cpp"
0x14000fea8  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x14000feaf  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14000feb4  mov     rbx, [rbp+var_18]
0x14000feb8  jmp     loc_14000FFF0
0x14000febd  lea     r9, [rbp+var_10]; unsigned __int16 **
0x14000fec1  mov     r8, [rbp+Src]; Src
0x14000fec5  mov     rbx, [rbp+var_18]
0x14000fec9  mov     rdx, rbx; unsigned __int16 *
0x14000fecc  mov     rcx, r14; this
0x14000fecf  call    ?EncryptTicket@CRAEncryption@@QEAAJPEAG0PEAPEAG@Z; CRAEncryption::EncryptTicket(ushort *,ushort *,ushort * *)
0x14000fed4  mov     esi, eax
0x14000fed6  test    eax, eax
0x14000fed8  jns     short loc_14000FF0C
0x14000feda  mov     dword ptr [rsp+60h+var_38], eax; unsigned int
0x14000fede  lea     rax, aCremoteassista_8; "CRemoteAssistanceApp::CreateTicketThrou"...
0x14000fee5  mov     [rsp+60h+ppv], rax; unsigned __int16 *
0x14000feea  mov     r9d, 4AEh; unsigned int
0x14000fef0  lea     r8, aBaseDiagnosisR_14; "base\\diagnosis\\ra\\ui\\app.cpp"
0x14000fef7  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x14000fefe  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14000ff03  mov     rdi, [rbp+var_10]
0x14000ff07  jmp     loc_14000FFF0
0x14000ff0c  mov     rdi, [rbp+var_10]
0x14000ff10  mov     rdx, rdi
0x14000ff13  jmp     short loc_14000FF34
0x14000ff15  mov     esi, 8007000Eh
0x14000ff1a  mov     dword ptr [rsp+60h+var_38], 8007000Eh
0x14000ff22  mov     r9d, 4A3h
0x14000ff28  jmp     loc_14000FD28
0x14000ff2d  mov     r14, r12
0x14000ff30  mov     rdx, [rbp+Src]
0x14000ff34  mov     rcx, [rbp+arg_18]
0x14000ff38  mov     rax, [rcx]
0x14000ff3b  mov     rax, [rax+48h]
0x14000ff3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ff44  mov     esi, eax
0x14000ff46  test    eax, eax
0x14000ff48  jns     short loc_14000FF75
0x14000ff4a  mov     dword ptr [rsp+60h+var_38], eax; unsigned int
0x14000ff4e  lea     rax, aCremoteassista_8; "CRemoteAssistanceApp::CreateTicketThrou"...
0x14000ff55  mov     [rsp+60h+ppv], rax; unsigned __int16 *
0x14000ff5a  mov     r9d, 4BBh; unsigned int
0x14000ff60  lea     r8, aBaseDiagnosisR_14; "base\\diagnosis\\ra\\ui\\app.cpp"
0x14000ff67  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x14000ff6e  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14000ff73  jmp     short loc_14000FFEB
0x14000ff75  lea     eax, [r13-5]
0x14000ff79  lea     rdx, [rbp+bstrString]
0x14000ff7d  cmp     eax, 1
0x14000ff80  jbe     short loc_14000FFAA
0x14000ff82  mov     ecx, 1
0x14000ff87  call    ?GetUserInfoAsBSTR@@YAJW4_USERINFOTYPE@@PEAPEAG@Z; GetUserInfoAsBSTR(_USERINFOTYPE,ushort * *)
0x14000ff8c  mov     rdx, [rbp+bstrString]; unsigned __int16 *
0x14000ff90  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14000ff97  mov     rcx, [rcx+340h]; this
0x14000ff9e  call    ?put_NoviceName@CRATicket@@QEAAJPEAG@Z; CRATicket::put_NoviceName(ushort *)
0x14000ffa3  mov     eax, 20h ; ' '
0x14000ffa8  jmp     short loc_14000FFD8
0x14000ffaa  mov     rcx, [rbp+arg_18]
0x14000ffae  mov     rax, [rcx]
0x14000ffb1  mov     rax, [rax+78h]
0x14000ffb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ffba  mov     esi, eax
0x14000ffbc  mov     rdx, [rbp+bstrString]; unsigned __int16 *
0x14000ffc0  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14000ffc7  mov     rcx, [rcx+340h]; this
0x14000ffce  call    ?put_ExpertName@CRATicket@@QEAAJPEAG@Z; CRATicket::put_ExpertName(ushort *)
0x14000ffd3  mov     eax, 6Fh ; 'o'
0x14000ffd8  mov     [r15+334h], eax
0x14000ffdf  lea     rdx, Invitation_Opened; struct _EVENT_DESCRIPTOR *
0x14000ffe6  call    ?LogEvent@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@@Z; CEventLogger::LogEvent(_EVENT_DESCRIPTOR const *)
0x14000ffeb  test    r14, r14
0x14000ffee  jz      short loc_140010007
0x14000fff0  mov     rcx, r14; this
0x14000fff3  call    ??1CRAEncryption@@QEAA@XZ; CRAEncryption::~CRAEncryption(void)
0x14000fff8  mov     rcx, r14
0x14000fffb  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140010002  nop     dword ptr [rax+rax+00h]
0x140010007  mov     rcx, [rbp+bstrString]; bstrString
0x14001000b  test    rcx, rcx
0x14001000e  jz      short loc_140010020
0x140010010  call    cs:__imp_SysFreeString
0x140010017  nop     dword ptr [rax+rax+00h]
0x14001001c  mov     [rbp+bstrString], r12
0x140010020  test    esi, esi
0x140010022  jns     short loc_14001002F
0x140010024  mov     dword ptr [r15+334h], 0FFFFFFFFh
0x14001002f  mov     rcx, rdi; bstrString
0x140010032  call    cs:__imp_SysFreeString
0x140010039  nop     dword ptr [rax+rax+00h]
0x14001003e  nop
0x14001003f  mov     rcx, [rbp+arg_18]
0x140010043  test    rcx, rcx
0x140010046  jz      short loc_140010055
0x140010048  mov     rax, [rcx]
0x14001004b  mov     rax, [rax+10h]
0x14001004f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010054  nop
0x140010055  mov     rcx, [rbp+Src]; bstrString
0x140010059  call    cs:__imp_SysFreeString
0x140010060  nop     dword ptr [rax+rax+00h]
0x140010065  nop
0x140010066  mov     rcx, rbx; bstrString
0x140010069  call    cs:__imp_SysFreeString
0x140010070  nop     dword ptr [rax+rax+00h]
0x140010075  mov     eax, esi
0x140010077  mov     rbx, [rsp+60h+arg_0]
0x14001007f  add     rsp, 60h
0x140010083  pop     r15
0x140010085  pop     r14
0x140010087  pop     r13
0x140010089  pop     r12
0x14001008b  pop     rdi
0x14001008c  pop     rsi
0x14001008d  pop     rbp
0x14001008e  retn
0x140010090  mov     ecx, 8007000Eh; int
0x140010095  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
