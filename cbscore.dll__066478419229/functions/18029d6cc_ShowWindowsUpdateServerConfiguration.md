# ShowWindowsUpdateServerConfiguration

- ea: `0x18029d6cc`
- end: `0x18029de60`
- name: `ShowWindowsUpdateServerConfiguration`
- size: `1940`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18029ef9c`

## callees

- `0x180010cc0`
- `0x180093c4c`
- `0x180098538`
- `0x180099548`
- `0x18009cf78`
- `0x1800a8678`
- `0x1800eb920`
- `0x1800ef360`
- `0x1800fa3ec`
- `0x18029d6cc`
- `0x1802d5010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18029d7c9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18029d7c9`
- `OLEAUT32!__imp_SysFreeString` at `0x18029daca`
- `OLEAUT32!__imp_SysFreeString` at `0x18029dae3`
- `OLEAUT32!__imp_SysFreeString` at `0x18029dc70`
- `OLEAUT32!__imp_SysFreeString` at `0x18029dc89`
- `OLEAUT32!__imp_SysFreeString` at `0x18029dde6`
- `OLEAUT32!__imp_SysFreeString` at `0x18029ddff`
- `OLEAUT32!__imp_SysFreeString` at `0x18029daca`
- `OLEAUT32!__imp_SysFreeString` at `0x18029dae3`
- `OLEAUT32!__imp_SysFreeString` at `0x18029dc70`
- `OLEAUT32!__imp_SysFreeString` at `0x18029dc89`
- `OLEAUT32!__imp_SysFreeString` at `0x18029dde6`
- `OLEAUT32!__imp_SysFreeString` at `0x18029ddff`

## string_xrefs

- `0x18029d75c`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x18029d836`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x18029ddce`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x18029dc46`: `WU: Microsoft Update service is the default, URL: {}, Name: {}`
- `0x18029dc1c`: `WU: WSUS service is the default, URL: {}, Name: {}`
- `0x18029da9f`: `WU: Update service is not default AU service, skip. URL: {}, Name: {}`
- `0x18029d7f3`: `Failed to get IUpdateServiceManager interface`
- `0x18029da38`: `Unable to get service name.`
- `0x18029da06`: `Unable to get service URL.`
- `0x18029dba8`: `Failed to get whether update service is managed or not`
- `0x18029dcdf`: `Failed to check whether it is default service.`
- `0x18029d8af`: `Failed to get services collection`
- `0x18029dd32`: `Failed to query service 2`
- `0x18029dd89`: `Failed to get update service, index: {}`

## pseudocode

```c
__int64 __fastcall ShowWindowsUpdateServerConfiguration(_BYTE *a1)
{
  int v2; // ebx
  int v3; // edx
  void (*v4)(void); // rax
  HRESULT v6; // eax
  int v7; // edx
  __int64 v8; // rdx
  int v9; // eax
  int v10; // edx
  int v11; // eax
  int v12; // edx
  __int64 v13; // rdx
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, __int64); // rbx
  __int64 InitPointer; // rax
  unsigned int v17; // eax
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, __int64); // rbx
  __int64 v20; // rax
  unsigned int v21; // eax
  int v22; // edx
  OLECHAR *v23; // rax
  OLECHAR *v24; // rcx
  int v25; // eax
  int v26; // edx
  int v27; // edx
  __int64 v28; // rdx
  OLECHAR *v29; // rcx
  struct LogAdapter::Logger *v30; // rax
  const char *v31; // r9
  int *v32; // rcx
  int v33; // edx
  int v34; // edx
  int v35; // edx
  int ppv; // [rsp+20h] [rbp-59h]
  int ppva; // [rsp+20h] [rbp-59h]
  int *v38; // [rsp+28h] [rbp-51h]
  int v39[2]; // [rsp+30h] [rbp-49h] BYREF
  BSTR v40; // [rsp+38h] [rbp-41h] BYREF
  BSTR v41; // [rsp+40h] [rbp-39h] BYREF
  int v42; // [rsp+48h] [rbp-31h] BYREF
  __int64 v43; // [rsp+50h] [rbp-29h] BYREF
  int v44[2]; // [rsp+58h] [rbp-21h] BYREF
  __int64 v45; // [rsp+60h] [rbp-19h] BYREF
  BSTR bstrString; // [rsp+68h] [rbp-11h] BYREF
  BSTR v47; // [rsp+70h] [rbp-9h] BYREF
  int v48; // [rsp+78h] [rbp-1h] BYREF
  __int16 v49; // [rsp+7Ch] [rbp+3h] BYREF
  __int16 v50; // [rsp+80h] [rbp+7h] BYREF
  LPVOID v51; // [rsp+88h] [rbp+Fh] BYREF
  int v52; // [rsp+90h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v51 = 0;
  v43 = 0;
  if ( !a1 )
  {
    v2 = -2147467261;
    v42 = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No WSUS result specified");
      *(_QWORD *)v44 = &v42;
      LOBYTE(v3) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v3,
        3,
        (unsigned int)": {}",
        (__int64)v44);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C6,
      (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
      (const char *)0x80004003LL,
      ppv);
    if ( v43 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
      v43 = 0;
    }
    if ( !v51 )
      return (unsigned int)v2;
    v4 = *(void (**)(void))(*(_QWORD *)v51 + 16LL);
LABEL_8:
    v4();
    return (unsigned int)v2;
  }
  *a1 = 0;
  v52 = 0;
  v6 = CoCreateInstance(
         &GUID_f8d253d9_89a4_4daa_87b6_1168369f0b21,
         0,
         1u,
         &GUID_23857e3c_02ba_44a3_9423_b1c900805f37,
         &v51);
  v2 = v6;
  if ( v6 < 0 )
  {
    v42 = v6;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get IUpdateServiceManager interface");
      *(_QWORD *)v44 = &v42;
      LOBYTE(v7) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v7,
        3,
        (unsigned int)": {}",
        (__int64)v44);
    }
    v8 = 461;
    goto LABEL_14;
  }
  if ( v43 )
  {
    INTERNAL_ERROR_ACTION(-1073741595);
    JUMPOUT(0x18029DE5FLL);
  }
  v9 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)v51 + 56LL))(v51, &v43);
  v2 = v9;
  if ( v9 < 0 )
  {
    v42 = v9;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get services collection");
      *(_QWORD *)v44 = &v42;
      LOBYTE(v10) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v10,
        3,
        (unsigned int)": {}",
        (__int64)v44);
    }
    v8 = 463;
    goto LABEL_14;
  }
  v11 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v43 + 72LL))(v43, &v52);
  v2 = v11;
  if ( v11 < 0 )
  {
    v42 = v11;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get collection count.");
      *(_QWORD *)v44 = &v42;
      LOBYTE(v12) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v12,
        3,
        (unsigned int)": {}",
        (__int64)v44);
    }
    v8 = 465;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
      (const char *)(unsigned int)v2,
      ppva);
LABEL_15:
    if ( v43 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
      v43 = 0;
    }
    if ( !v51 )
      return (unsigned int)v2;
    v4 = *(void (**)(void))(*(_QWORD *)v51 + 16LL);
    goto LABEL_8;
  }
  v42 = 0;
  if ( v52 > 0 )
  {
    v13 = 0;
    while ( 1 )
    {
      *(_QWORD *)v44 = 0;
      v45 = 0;
      v47 = 0;
      bstrString = 0;
      v50 = 0;
      v49 = 0;
      v2 = (*(__int64 (__fastcall **)(__int64, __int64, int *))(*(_QWORD *)v43 + 56LL))(v43, v13, v44);
      if ( v2 < 0 )
      {
        v48 = v2;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<long>(
            (_DWORD)LogAdapter::g_Logger,
            0,
            3,
            (unsigned int)"Failed to get update service, index: {}",
            (__int64)&v42);
          *(_QWORD *)v39 = &v48;
          LOBYTE(v35) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v35,
            3,
            (unsigned int)": {}",
            (__int64)v39);
        }
        v28 = 477;
        goto LABEL_78;
      }
      if ( v45 )
      {
        INTERNAL_ERROR_ACTION(-1073741595);
        __debugbreak();
      }
      v2 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))v44)(
             *(_QWORD *)v44,
             &GUID_1518b460_6518_4172_940f_c75883b24ceb,
             &v45);
      if ( v2 < 0 )
      {
        v48 = v2;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to query service 2");
          *(_QWORD *)v39 = &v48;
          LOBYTE(v34) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v34,
            3,
            (unsigned int)": {}",
            (__int64)v39);
        }
        v28 = 479;
        goto LABEL_78;
      }
      v14 = v45;
      v15 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v45 + 144LL);
      InitPointer = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v47);
      v17 = v15(v14, InitPointer);
      LogAdapter::TraceAtLevelIfFailed<long,>(3, v17, "Unable to get service URL.");
      v18 = v45;
      v19 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v45 + 56LL);
      v20 = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&bstrString);
      v21 = v19(v18, v20);
      LogAdapter::TraceAtLevelIfFailed<long,>(3, v21, "Unable to get service name.");
      v2 = (*(__int64 (__fastcall **)(__int64, __int16 *))(*(_QWORD *)v45 + 160LL))(v45, &v49);
      if ( v2 < 0 )
      {
        v48 = v2;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            LogAdapter::g_Logger,
            0,
            3,
            "Failed to check whether it is default service.");
          *(_QWORD *)v39 = &v48;
          LOBYTE(v33) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v33,
            3,
            (unsigned int)": {}",
            (__int64)v39);
        }
        v28 = 485;
        goto LABEL_78;
      }
      if ( v49 == -1 )
        break;
      v23 = bstrString;
      v24 = v47;
      v40 = bstrString;
      v41 = v47;
      if ( LogAdapter::g_Logger )
      {
        LOBYTE(v22) = 1;
        LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
          (_DWORD)LogAdapter::g_Logger,
          v22,
          1,
          (unsigned int)"WU: Update service is not default AU service, skip. URL: {}, Name: {}",
          (__int64)&v41,
          (__int64)&v40);
        v24 = v47;
        v23 = bstrString;
      }
      if ( v23 )
      {
        SysFreeString(v23);
        v24 = v47;
        bstrString = 0;
      }
      if ( v24 )
      {
        SysFreeString(v24);
        v47 = 0;
      }
      if ( v45 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
        v45 = 0;
      }
      if ( *(_QWORD *)v44 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v44 + 16LL))(*(_QWORD *)v44);
      v13 = (unsigned int)(v42 + 1);
      v42 = v13;
      if ( (int)v13 >= v52 )
        goto LABEL_46;
    }
    v25 = (*(__int64 (__fastcall **)(__int64, __int16 *))(*(_QWORD *)v45 + 80LL))(v45, &v50);
    v2 = v25;
    if ( v25 < 0 )
    {
      v48 = v25;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          LogAdapter::g_Logger,
          0,
          3,
          "Failed to get whether update service is managed or not");
        v41 = (BSTR)&v48;
        LOBYTE(v27) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v27,
          3,
          (unsigned int)": {}",
          (__int64)&v41);
      }
      v28 = 489;
LABEL_78:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v28,
        (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
        (const char *)(unsigned int)v2,
        ppva);
      if ( bstrString )
      {
        SysFreeString(bstrString);
        bstrString = 0;
      }
      if ( v47 )
      {
        SysFreeString(v47);
        v47 = 0;
      }
      if ( v45 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
        v45 = 0;
      }
      if ( *(_QWORD *)v44 )
      {
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v44 + 16LL))(*(_QWORD *)v44);
        *(_QWORD *)v44 = 0;
      }
      goto LABEL_15;
    }
    v29 = bstrString;
    if ( v50 == -1 )
    {
      *(_QWORD *)v39 = v47;
      v30 = LogAdapter::g_Logger;
      *a1 = 1;
      v40 = v29;
      if ( v30 )
      {
        v38 = (int *)&v40;
        v31 = "WU: WSUS service is the default, URL: {}, Name: {}";
        v32 = v39;
LABEL_60:
        LOBYTE(v26) = 1;
        LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
          (_DWORD)v30,
          v26,
          1,
          (_DWORD)v31,
          (__int64)v32,
          (__int64)v38);
        v29 = bstrString;
      }
    }
    else
    {
      v40 = v47;
      LODWORD(v30) = (_DWORD)LogAdapter::g_Logger;
      *(_QWORD *)v39 = bstrString;
      if ( LogAdapter::g_Logger )
      {
        v38 = v39;
        v31 = "WU: Microsoft Update service is the default, URL: {}, Name: {}";
        v32 = (int *)&v40;
        goto LABEL_60;
      }
    }
    if ( v29 )
    {
      SysFreeString(v29);
      bstrString = 0;
    }
    if ( v47 )
    {
      SysFreeString(v47);
      v47 = 0;
    }
    if ( v45 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
      v45 = 0;
    }
    if ( *(_QWORD *)v44 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v44 + 16LL))(*(_QWORD *)v44);
  }
LABEL_46:
  if ( v43 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    v43 = 0;
  }
  if ( v51 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v51 + 16LL))(v51);
  return 0;
}

```

## disassembly

```asm
0x18029d6cc  push    rbp
0x18029d6ce  push    rbx
0x18029d6cf  push    rsi
0x18029d6d0  push    rdi
0x18029d6d1  push    r12
0x18029d6d3  push    r15
0x18029d6d5  lea     rbp, [rsp-2Fh]
0x18029d6da  sub     rsp, 0A8h
0x18029d6e1  mov     rax, cs:__security_cookie
0x18029d6e8  xor     rax, rsp
0x18029d6eb  mov     [rbp+57h+var_38], rax
0x18029d6ef  xor     r12d, r12d
0x18029d6f2  mov     r15, rcx
0x18029d6f5  mov     [rbp+57h+var_48], r12
0x18029d6f9  mov     [rbp+57h+var_80], r12
0x18029d6fd  test    rcx, rcx
0x18029d700  jnz     loc_18029D7A5
0x18029d706  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18029d70d  mov     ebx, 80004003h
0x18029d712  mov     [rbp+57h+var_88], ebx
0x18029d715  test    rcx, rcx
0x18029d718  jz      short loc_18029D758
0x18029d71a  lea     esi, [r15+3]
0x18029d71e  xor     edx, edx
0x18029d720  mov     r8d, esi
0x18029d723  lea     r9, aNoWsusResultSp; "No WSUS result specified"
0x18029d72a  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18029d72f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18029d736  lea     rax, [rbp+57h+var_88]
0x18029d73a  mov     qword ptr [rbp+57h+var_78], rax
0x18029d73e  lea     r9, asc_1802EE7AC; ": {}"
0x18029d745  lea     rax, [rbp+57h+var_78]
0x18029d749  mov     r8d, esi
0x18029d74c  mov     dl, 1
0x18029d74e  mov     [rsp+0D0h+ppv], rax; int
0x18029d753  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18029d758  mov     rcx, [rbp+5Fh]; this
0x18029d75c  lea     r8, aOnecoreBaseCbs_91; "onecore\\base\\cbs\\wulib\\windowsupdat"...
0x18029d763  mov     r9d, ebx; char *
0x18029d766  mov     edx, 1C6h; void *
0x18029d76b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18029d770  mov     rcx, [rbp+57h+var_80]
0x18029d774  test    rcx, rcx
0x18029d777  jz      short loc_18029D789
0x18029d779  mov     rax, [rcx]
0x18029d77c  mov     rax, [rax+10h]
0x18029d780  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029d785  mov     [rbp+57h+var_80], r12
0x18029d789  mov     rcx, [rbp+57h+var_48]
0x18029d78d  test    rcx, rcx
0x18029d790  jz      short loc_18029D79E
0x18029d792  mov     rdx, [rcx]
0x18029d795  mov     rax, [rdx+10h]
0x18029d799  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029d79e  mov     eax, ebx
0x18029d7a0  jmp     loc_18029DB62
0x18029d7a5  xor     edx, edx; pUnkOuter
0x18029d7a7  mov     [rcx], r12b
0x18029d7aa  lea     rax, [rbp+57h+var_48]
0x18029d7ae  mov     [rbp+57h+var_40], r12d
0x18029d7b2  lea     r9, _GUID_23857e3c_02ba_44a3_9423_b1c900805f37; riid
0x18029d7b9  mov     [rsp+0D0h+ppv], rax; ppv
0x18029d7be  lea     rcx, _GUID_f8d253d9_89a4_4daa_87b6_1168369f0b21; rclsid
0x18029d7c5  lea     r8d, [rdx+1]; dwClsContext
0x18029d7c9  call    cs:__imp_CoCreateInstance
0x18029d7d0  nop     dword ptr [rax+rax+00h]
0x18029d7d5  mov     ebx, eax
0x18029d7d7  test    eax, eax
0x18029d7d9  jns     loc_18029D877
0x18029d7df  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18029d7e6  mov     [rbp+57h+var_88], eax
0x18029d7e9  test    rcx, rcx
0x18029d7ec  jz      short loc_18029D82D
0x18029d7ee  mov     esi, 3
0x18029d7f3  lea     r9, aFailedToGetIup; "Failed to get IUpdateServiceManager int"...
0x18029d7fa  mov     r8d, esi
0x18029d7fd  xor     edx, edx
0x18029d7ff  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18029d804  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18029d80b  lea     rax, [rbp+57h+var_88]
0x18029d80f  mov     qword ptr [rbp+57h+var_78], rax
0x18029d813  lea     r9, asc_1802EE7AC; ": {}"
0x18029d81a  lea     rax, [rbp+57h+var_78]
0x18029d81e  mov     r8d, esi
0x18029d821  mov     dl, 1
0x18029d823  mov     [rsp+0D0h+ppv], rax; int
0x18029d828  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18029d82d  mov     edx, 1CDh; void *
0x18029d832  mov     rcx, [rbp+5Fh]; this
0x18029d836  lea     r8, aOnecoreBaseCbs_91; "onecore\\base\\cbs\\wulib\\windowsupdat"...
0x18029d83d  mov     r9d, ebx; char *
0x18029d840  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18029d845  mov     rcx, [rbp+57h+var_80]
0x18029d849  test    rcx, rcx
0x18029d84c  jz      short loc_18029D85E
0x18029d84e  mov     rax, [rcx]
0x18029d851  mov     rax, [rax+10h]
0x18029d855  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029d85a  mov     [rbp+57h+var_80], r12
0x18029d85e  mov     rcx, [rbp+57h+var_48]
0x18029d862  test    rcx, rcx
0x18029d865  jz      loc_18029D79E
0x18029d86b  mov     rax, [rcx]
0x18029d86e  mov     rax, [rax+10h]
0x18029d872  jmp     loc_18029D799
0x18029d877  cmp     [rbp+57h+var_80], r12
0x18029d87b  jnz     loc_18029DE55
0x18029d881  mov     rcx, [rbp+57h+var_48]
0x18029d885  lea     rdx, [rbp+57h+var_80]
0x18029d889  mov     rax, [rcx]
0x18029d88c  mov     rax, [rax+38h]
0x18029d890  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029d895  mov     ebx, eax
0x18029d897  test    eax, eax
0x18029d899  jns     short loc_18029D8F3
0x18029d89b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18029d8a2  mov     [rbp+57h+var_88], eax
0x18029d8a5  test    rcx, rcx
0x18029d8a8  jz      short loc_18029D8E9
0x18029d8aa  mov     esi, 3
0x18029d8af  lea     r9, aFailedToGetSer; "Failed to get services collection"
0x18029d8b6  mov     r8d, esi
0x18029d8b9  xor     edx, edx
0x18029d8bb  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18029d8c0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18029d8c7  lea     rax, [rbp+57h+var_88]
0x18029d8cb  mov     qword ptr [rbp+57h+var_78], rax
0x18029d8cf  lea     r9, asc_1802EE7AC; ": {}"
0x18029d8d6  lea     rax, [rbp+57h+var_78]
0x18029d8da  mov     r8d, esi
0x18029d8dd  mov     dl, 1
0x18029d8df  mov     [rsp+0D0h+ppv], rax
0x18029d8e4  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18029d8e9  mov     edx, 1CFh
0x18029d8ee  jmp     loc_18029D832
0x18029d8f3  mov     rcx, [rbp+57h+var_80]
0x18029d8f7  lea     rdx, [rbp+57h+var_40]
0x18029d8fb  mov     rax, [rcx]
0x18029d8fe  mov     rax, [rax+48h]
0x18029d902  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029d907  mov     ebx, eax
0x18029d909  test    eax, eax
0x18029d90b  jns     short loc_18029D965
0x18029d90d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18029d914  mov     [rbp+57h+var_88], eax
0x18029d917  test    rcx, rcx
0x18029d91a  jz      short loc_18029D95B
0x18029d91c  mov     esi, 3
0x18029d921  lea     r9, aFailedToGetCol; "Failed to get collection count."
0x18029d928  mov     r8d, esi
0x18029d92b  xor     edx, edx
0x18029d92d  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18029d932  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18029d939  lea     rax, [rbp+57h+var_88]
0x18029d93d  mov     qword ptr [rbp+57h+var_78], rax
0x18029d941  lea     r9, asc_1802EE7AC; ": {}"
0x18029d948  lea     rax, [rbp+57h+var_78]
0x18029d94c  mov     r8d, esi
0x18029d94f  mov     dl, 1
0x18029d951  mov     [rsp+0D0h+ppv], rax
0x18029d956  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18029d95b  mov     edx, 1D1h
0x18029d960  jmp     loc_18029D832
0x18029d965  mov     [rbp+57h+var_88], r12d
0x18029d969  cmp     [rbp+57h+var_40], r12d
0x18029d96d  jle     loc_18029DB32
0x18029d973  mov     edx, r12d
0x18029d976  mov     esi, 3
0x18029d97b  mov     rcx, [rbp+57h+var_80]
0x18029d97f  lea     r8, [rbp+57h+var_78]
0x18029d983  mov     qword ptr [rbp+57h+var_78], r12
0x18029d987  mov     [rbp+57h+var_70], r12
0x18029d98b  mov     [rbp+57h+var_60], r12
0x18029d98f  mov     [rbp+57h+bstrString], r12
0x18029d993  mov     [rbp+57h+var_50], r12w
0x18029d998  mov     [rbp+57h+var_54], r12w
0x18029d99d  mov     rax, [rcx]
0x18029d9a0  mov     rax, [rax+38h]
0x18029d9a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029d9a9  mov     ebx, eax
0x18029d9ab  test    eax, eax
0x18029d9ad  js      loc_18029DD73
0x18029d9b3  cmp     [rbp+57h+var_70], r12
0x18029d9b7  jnz     loc_18029DE4A
0x18029d9bd  mov     rcx, qword ptr [rbp+57h+var_78]
0x18029d9c1  lea     r8, [rbp+57h+var_70]
0x18029d9c5  lea     rdx, _GUID_1518b460_6518_4172_940f_c75883b24ceb
0x18029d9cc  mov     rax, [rcx]
0x18029d9cf  mov     rax, [rax]
0x18029d9d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029d9d7  mov     ebx, eax
0x18029d9d9  test    eax, eax
0x18029d9db  js      loc_18029DD23
0x18029d9e1  mov     rdi, [rbp+57h+var_70]
0x18029d9e5  lea     rcx, [rbp+57h+var_60]
0x18029d9e9  mov     rax, [rdi]
0x18029d9ec  mov     rbx, [rax+90h]
0x18029d9f3  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x18029d9f8  mov     rdx, rax
0x18029d9fb  mov     rcx, rdi
0x18029d9fe  mov     rax, rbx
0x18029da01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029da06  lea     r8, aUnableToGetSer_0; "Unable to get service URL."
0x18029da0d  mov     edx, eax
0x18029da0f  mov     ecx, esi
0x18029da11  call    ??$TraceAtLevelIfFailed@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelIfFailed<long,>(LogAdapter::LogLevel,long,char const * const)
0x18029da16  mov     rdi, [rbp+57h+var_70]
0x18029da1a  lea     rcx, [rbp+57h+bstrString]
0x18029da1e  mov     rax, [rdi]
0x18029da21  mov     rbx, [rax+38h]
0x18029da25  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x18029da2a  mov     rdx, rax
0x18029da2d  mov     rcx, rdi
0x18029da30  mov     rax, rbx
0x18029da33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029da38  lea     r8, aUnableToGetSer; "Unable to get service name."
0x18029da3f  mov     edx, eax
0x18029da41  mov     ecx, esi
0x18029da43  call    ??$TraceAtLevelIfFailed@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelIfFailed<long,>(LogAdapter::LogLevel,long,char const * const)
0x18029da48  mov     rcx, [rbp+57h+var_70]
0x18029da4c  lea     rdx, [rbp+57h+var_54]
0x18029da50  mov     rax, [rcx]
0x18029da53  mov     rax, [rax+0A0h]
0x18029da5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029da5f  mov     ebx, eax
0x18029da61  test    eax, eax
0x18029da63  js      loc_18029DCD0
0x18029da69  cmp     [rbp+57h+var_54], 0FFFFh
0x18029da6e  jz      loc_18029DB7F
0x18029da74  mov     r10, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18029da7b  mov     rax, [rbp+57h+bstrString]
0x18029da7f  mov     rcx, [rbp+57h+var_60]
0x18029da83  mov     [rbp+57h+var_98], rax
0x18029da87  mov     [rbp+57h+var_90], rcx
0x18029da8b  test    r10, r10
0x18029da8e  jz      short loc_18029DAC2
0x18029da90  lea     rax, [rbp+57h+var_98]
0x18029da94  mov     r8d, 1
0x18029da9a  mov     [rsp+0D0h+var_A8], rax
0x18029da9f  lea     r9, aWuUpdateServic; "WU: Update service is not default AU se"...
0x18029daa6  lea     rax, [rbp+57h+var_90]
0x18029daaa  mov     dl, r8b
0x18029daad  mov     rcx, r10
0x18029dab0  mov     [rsp+0D0h+ppv], rax
0x18029dab5  call    ??$LogNumObjects@PEB_WPEA_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_WAEBQEA_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &,wchar_t * const &)
0x18029daba  mov     rcx, [rbp+57h+var_60]
0x18029dabe  mov     rax, [rbp+57h+bstrString]
0x18029dac2  test    rax, rax
0x18029dac5  jz      short loc_18029DADE
0x18029dac7  mov     rcx, rax; bstrString
0x18029daca  call    cs:__imp_SysFreeString
0x18029dad1  nop     dword ptr [rax+rax+00h]
0x18029dad6  mov     rcx, [rbp+57h+var_60]; bstrString
0x18029dada  mov     [rbp+57h+bstrString], r12
0x18029dade  test    rcx, rcx
0x18029dae1  jz      short loc_18029DAF3
0x18029dae3  call    cs:__imp_SysFreeString
0x18029daea  nop     dword ptr [rax+rax+00h]
0x18029daef  mov     [rbp+57h+var_60], r12
0x18029daf3  mov     rcx, [rbp+57h+var_70]
0x18029daf7  test    rcx, rcx
0x18029dafa  jz      short loc_18029DB0C
0x18029dafc  mov     rax, [rcx]
0x18029daff  mov     rax, [rax+10h]
0x18029db03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029db08  mov     [rbp+57h+var_70], r12
0x18029db0c  mov     rcx, qword ptr [rbp+57h+var_78]
0x18029db10  test    rcx, rcx
0x18029db13  jz      short loc_18029DB21
0x18029db15  mov     rax, [rcx]
0x18029db18  mov     rax, [rax+10h]
0x18029db1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029db21  mov     edx, [rbp+57h+var_88]
0x18029db24  inc     edx
0x18029db26  mov     [rbp+57h+var_88], edx
0x18029db29  cmp     edx, [rbp+57h+var_40]
0x18029db2c  jl      loc_18029D97B
0x18029db32  mov     rcx, [rbp+57h+var_80]
0x18029db36  test    rcx, rcx
0x18029db39  jz      short loc_18029DB4B
0x18029db3b  mov     rax, [rcx]
0x18029db3e  mov     rax, [rax+10h]
0x18029db42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029db47  mov     [rbp+57h+var_80], r12
0x18029db4b  mov     rcx, [rbp+57h+var_48]
0x18029db4f  test    rcx, rcx
0x18029db52  jz      short loc_18029DB60
0x18029db54  mov     rax, [rcx]
0x18029db57  mov     rax, [rax+10h]
0x18029db5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029db60  xor     eax, eax
0x18029db62  mov     rcx, [rbp+57h+var_38]
0x18029db66  xor     rcx, rsp; StackCookie
0x18029db69  call    __security_check_cookie
0x18029db6e  add     rsp, 0A8h
0x18029db75  pop     r15
0x18029db77  pop     r12
0x18029db79  pop     rdi
0x18029db7a  pop     rsi
0x18029db7b  pop     rbx
  ... truncated ...
```
