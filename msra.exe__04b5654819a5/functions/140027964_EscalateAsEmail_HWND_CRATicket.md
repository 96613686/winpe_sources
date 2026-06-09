# EscalateAsEmail(HWND__ *,CRATicket *)

- ea: `0x140027964`
- end: `0x140027cd7`
- name: `?EscalateAsEmail@@YAJPEAUHWND__@@PEAVCRATicket@@@Z`
- size: `883`
- prototype: `int(HWND, struct CRATicket *)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x140013f4c`
- `0x1400321c0`

## callees

- `0x140025bd8`
- `0x140025e54`
- `0x140027964`
- `0x14002a72c`
- `0x14002b4a0`
- `0x140034ce4`
- `0x140034eac`
- `0x14003500c`
- `0x140037c8c`
- `0x14004d010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x140027992`
- `KERNEL32!GetModuleHandleW` at `0x140027992`
- `ole32!CoCreateInstance` at `0x140027b32`
- `ole32!CoCreateInstance` at `0x140027b32`
- `OLEAUT32!__imp_SysFreeString` at `0x140027c43`
- `OLEAUT32!__imp_SysFreeString` at `0x140027c68`
- `OLEAUT32!__imp_SysFreeString` at `0x140027c79`
- `OLEAUT32!__imp_SysFreeString` at `0x140027c8a`
- `OLEAUT32!__imp_SysFreeString` at `0x140027c9b`
- `OLEAUT32!__imp_SysFreeString` at `0x140027cac`
- `OLEAUT32!__imp_SysFreeString` at `0x140027cbd`
- `OLEAUT32!__imp_SysFreeString` at `0x140027c43`
- `OLEAUT32!__imp_SysFreeString` at `0x140027c68`
- `OLEAUT32!__imp_SysFreeString` at `0x140027c79`
- `OLEAUT32!__imp_SysFreeString` at `0x140027c8a`
- `OLEAUT32!__imp_SysFreeString` at `0x140027c9b`
- `OLEAUT32!__imp_SysFreeString` at `0x140027cac`
- `OLEAUT32!__imp_SysFreeString` at `0x140027cbd`

## string_xrefs

- `0x1400279e4`: `base\diagnosis\ra\ui\commonfunc.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall EscalateAsEmail(HWND a1, struct CRATicket *a2)
{
  HMODULE ModuleHandleW; // rdi
  unsigned int v4; // esi
  signed int v5; // eax
  CEventLogger *v6; // rcx
  unsigned int v7; // r9d
  CEventLogger *v8; // rcx
  CEventLogger *v9; // rcx
  CEventLogger *v10; // rcx
  CEventLogger *v11; // rcx
  CEventLogger *v12; // rcx
  CEventLogger *v13; // rcx
  HRESULT v14; // ebx
  CEventLogger *v15; // rcx
  char *v16; // rcx
  CEventLogger *v17; // rcx
  CEventLogger *v18; // rcx
  LPVOID ppv; // [rsp+30h] [rbp-40h] BYREF
  BSTR v21; // [rsp+38h] [rbp-38h] BYREF
  BSTR bstrString; // [rsp+40h] [rbp-30h] BYREF
  BSTR v23; // [rsp+48h] [rbp-28h] BYREF
  BSTR v24; // [rsp+50h] [rbp-20h] BYREF
  BSTR v25; // [rsp+58h] [rbp-18h] BYREF
  BSTR v26; // [rsp+60h] [rbp-10h] BYREF
  BSTR v27; // [rsp+68h] [rbp-8h] BYREF
  HWND v28; // [rsp+A0h] [rbp+30h] BYREF
  int v29; // [rsp+B0h] [rbp+40h] BYREF
  int v30; // [rsp+B8h] [rbp+48h] BYREF

  v28 = a1;
  v27 = 0;
  v26 = 0;
  v25 = 0;
  v24 = 0;
  v23 = 0;
  ModuleHandleW = GetModuleHandleW(0);
  v29 = 0;
  LODWORD(v28) = 0;
  v30 = 0;
  v4 = -2147467259;
  bstrString = 0;
  v21 = 0;
  ppv = 0;
  v5 = SaveTicketToTempDirectory(&bstrString, a2);
  if ( v5 >= 0 )
  {
    if ( !ATL::CComBSTR::LoadStringW((ATL::CComBSTR *)&v27, ModuleHandleW, 0x207u) )
    {
      CEventLogger::LogError(
        v8,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
        0x7D5u,
        L"EscalateAsEmail",
        0);
      goto LABEL_28;
    }
    if ( !ATL::CComBSTR::LoadStringW((ATL::CComBSTR *)&v26, ModuleHandleW, 0x208u) )
    {
      CEventLogger::LogError(
        v9,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
        0x7D6u,
        L"EscalateAsEmail",
        0);
      goto LABEL_28;
    }
    if ( !ATL::CComBSTR::LoadStringW((ATL::CComBSTR *)&v25, ModuleHandleW, 0x209u) )
    {
      CEventLogger::LogError(
        v10,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
        0x7D7u,
        L"EscalateAsEmail",
        0);
      goto LABEL_28;
    }
    if ( !ATL::CComBSTR::LoadStringW((ATL::CComBSTR *)&v24, ModuleHandleW, 0x20Au) )
    {
      CEventLogger::LogError(
        v11,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
        0x7D8u,
        L"EscalateAsEmail",
        0);
      goto LABEL_28;
    }
    if ( !ATL::CComBSTR::LoadStringW((ATL::CComBSTR *)&v23, ModuleHandleW, 0x20Cu) )
    {
      CEventLogger::LogError(
        v12,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
        0x7D9u,
        L"EscalateAsEmail",
        0);
      goto LABEL_28;
    }
    ATL::CComBSTR::operator=(&v21, &v24);
    v5 = ATL::CComBSTR::Append((ATL::CComBSTR *)&v21, (const struct ATL::CComBSTR *)&v23);
    if ( v5 >= 0 )
    {
      v5 = ATL::CComBSTR::Append((ATL::CComBSTR *)&v21, (const struct ATL::CComBSTR *)&v26);
      if ( v5 >= 0 )
      {
        v5 = ATL::CComBSTR::Append((ATL::CComBSTR *)&v21, (const struct ATL::CComBSTR *)&v25);
        if ( v5 >= 0 )
        {
          v14 = CoCreateInstance(
                  &GUID_d0e55f9f_0021_42fe_a1db_c41f5b564efe,
                  0,
                  4u,
                  &GUID_37473440_9cef_4061_9da2_0730773e7806,
                  &ppv);
          if ( v14 < 0 )
          {
            CEventLogger::LogEvent(v13, &COM_Problem, L"D0E55F9F-0021-42fe-A1DB-C41F5B564EFE");
            CEventLogger::LogError(
              v15,
              &Recoverable_Error,
              L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
              0x7F0u,
              L"EscalateAsEmail",
              v14);
            goto LABEL_28;
          }
          v4 = -2147418113;
          v5 = (*(__int64 (__fastcall **)(LPVOID, int *, HWND *))(*(_QWORD *)ppv + 120LL))(ppv, &v29, &v28);
          if ( v5 >= 0 )
          {
            (*(void (__fastcall **)(LPVOID, BSTR))(*(_QWORD *)ppv + 96LL))(ppv, v27);
            (*(void (__fastcall **)(LPVOID, BSTR))(*(_QWORD *)ppv + 80LL))(ppv, v21);
            (*(void (__fastcall **)(LPVOID, BSTR))(*(_QWORD *)ppv + 64LL))(ppv, bstrString);
            v5 = (*(__int64 (__fastcall **)(LPVOID, int *, HWND *))(*(_QWORD *)ppv + 104LL))(ppv, &v30, &v28);
            if ( v5 >= 0 )
            {
              v16 = (char *)_AtlModule + 496;
              *((_DWORD *)_AtlModule + 131) = 1;
              CSqmManager::ProcessRAEvent(v16, 0);
              CEventLogger::LogEvent(v17, &Invitation_Opened);
              v4 = 0;
              goto LABEL_28;
            }
            v7 = 2043;
          }
          else
          {
            v7 = 2037;
          }
        }
        else
        {
          v7 = 2017;
        }
      }
      else
      {
        v7 = 2016;
      }
    }
    else
    {
      v7 = 2015;
    }
  }
  else
  {
    v7 = 2000;
  }
  CEventLogger::LogError(v6, &Recoverable_Error, L"base\\diagnosis\\ra\\ui\\commonfunc.cpp", v7, L"EscalateAsEmail", v5);
LABEL_28:
  v18 = (CEventLogger *)ppv;
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  if ( bstrString )
    SysFreeString(bstrString);
  if ( v4 == -2147418113 )
    CEventLogger::LogEvent(v18, &SMAPI_Problem);
  SysFreeString(v21);
  SysFreeString(v23);
  SysFreeString(v24);
  SysFreeString(v25);
  SysFreeString(v26);
  SysFreeString(v27);
  return v4;
}

```

## disassembly

```asm
0x140027964  mov     [rsp-28h+arg_0], rcx
0x140027969  push    rbp
0x14002796a  push    rbx
0x14002796b  push    rsi
0x14002796c  push    rdi
0x14002796d  push    r15
0x14002796f  mov     rbp, rsp
0x140027972  sub     rsp, 70h
0x140027976  mov     rbx, rdx
0x140027979  xor     r15d, r15d
0x14002797c  mov     [rbp+var_8], r15
0x140027980  mov     [rbp+var_10], r15
0x140027984  mov     [rbp+var_18], r15
0x140027988  mov     [rbp+var_20], r15
0x14002798c  mov     [rbp+var_28], r15
0x140027990  xor     ecx, ecx; lpModuleName
0x140027992  call    cs:__imp_GetModuleHandleW
0x140027999  nop     dword ptr [rax+rax+00h]
0x14002799e  mov     rdi, rax
0x1400279a1  mov     [rbp+arg_10], r15d
0x1400279a5  mov     dword ptr [rbp+arg_0], r15d
0x1400279a9  mov     [rbp+arg_18], r15d
0x1400279ad  mov     esi, 80004005h
0x1400279b2  mov     [rbp+bstrString], r15
0x1400279b6  mov     [rbp+var_38], r15
0x1400279ba  mov     [rbp+var_40], r15
0x1400279be  mov     rdx, rbx; struct CRATicket *
0x1400279c1  lea     rcx, [rbp+bstrString]; unsigned __int16 **
0x1400279c5  call    ?SaveTicketToTempDirectory@@YAJPEAPEAGPEAVCRATicket@@@Z; SaveTicketToTempDirectory(ushort * *,CRATicket *)
0x1400279ca  test    eax, eax
0x1400279cc  jns     short loc_1400279FC
0x1400279ce  mov     r9d, 7D0h; unsigned int
0x1400279d4  mov     [rsp+70h+var_48], eax; unsigned int
0x1400279d8  lea     rax, aEscalateasemai; "EscalateAsEmail"
0x1400279df  mov     [rsp+70h+ppv], rax; unsigned __int16 *
0x1400279e4  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\ui\\commonfunc.cpp"
0x1400279eb  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x1400279f2  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1400279f7  jmp     loc_140027C20
0x1400279fc  mov     r8d, 207h; unsigned int
0x140027a02  mov     rdx, rdi; HINSTANCE
0x140027a05  lea     rcx, [rbp+var_8]; this
0x140027a09  call    ?LoadStringW@CComBSTR@ATL@@QEAA_NPEAUHINSTANCE__@@I@Z; ATL::CComBSTR::LoadStringW(HINSTANCE__ *,uint)
0x140027a0e  test    al, al
0x140027a10  jnz     short loc_140027A1F
0x140027a12  mov     [rsp+70h+var_48], r15d
0x140027a17  mov     r9d, 7D5h
0x140027a1d  jmp     short loc_1400279D8
0x140027a1f  mov     r8d, 208h; unsigned int
0x140027a25  mov     rdx, rdi; HINSTANCE
0x140027a28  lea     rcx, [rbp+var_10]; this
0x140027a2c  call    ?LoadStringW@CComBSTR@ATL@@QEAA_NPEAUHINSTANCE__@@I@Z; ATL::CComBSTR::LoadStringW(HINSTANCE__ *,uint)
0x140027a31  test    al, al
0x140027a33  jnz     short loc_140027A42
0x140027a35  mov     [rsp+70h+var_48], r15d
0x140027a3a  mov     r9d, 7D6h
0x140027a40  jmp     short loc_1400279D8
0x140027a42  mov     r8d, 209h; unsigned int
0x140027a48  mov     rdx, rdi; HINSTANCE
0x140027a4b  lea     rcx, [rbp+var_18]; this
0x140027a4f  call    ?LoadStringW@CComBSTR@ATL@@QEAA_NPEAUHINSTANCE__@@I@Z; ATL::CComBSTR::LoadStringW(HINSTANCE__ *,uint)
0x140027a54  test    al, al
0x140027a56  jnz     short loc_140027A68
0x140027a58  mov     [rsp+70h+var_48], r15d
0x140027a5d  mov     r9d, 7D7h
0x140027a63  jmp     loc_1400279D8
0x140027a68  mov     r8d, 20Ah; unsigned int
0x140027a6e  mov     rdx, rdi; HINSTANCE
0x140027a71  lea     rcx, [rbp+var_20]; this
0x140027a75  call    ?LoadStringW@CComBSTR@ATL@@QEAA_NPEAUHINSTANCE__@@I@Z; ATL::CComBSTR::LoadStringW(HINSTANCE__ *,uint)
0x140027a7a  test    al, al
0x140027a7c  jnz     short loc_140027A8E
0x140027a7e  mov     [rsp+70h+var_48], r15d
0x140027a83  mov     r9d, 7D8h
0x140027a89  jmp     loc_1400279D8
0x140027a8e  mov     r8d, 20Ch; unsigned int
0x140027a94  mov     rdx, rdi; HINSTANCE
0x140027a97  lea     rcx, [rbp+var_28]; this
0x140027a9b  call    ?LoadStringW@CComBSTR@ATL@@QEAA_NPEAUHINSTANCE__@@I@Z; ATL::CComBSTR::LoadStringW(HINSTANCE__ *,uint)
0x140027aa0  test    al, al
0x140027aa2  jnz     short loc_140027AB4
0x140027aa4  mov     [rsp+70h+var_48], r15d
0x140027aa9  mov     r9d, 7D9h
0x140027aaf  jmp     loc_1400279D8
0x140027ab4  lea     rdx, [rbp+var_20]
0x140027ab8  lea     rcx, [rbp+var_38]
0x140027abc  call    ??4CComBSTR@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CComBSTR::operator=(ATL::CComBSTR const &)
0x140027ac1  lea     rdx, [rbp+var_28]; struct ATL::CComBSTR *
0x140027ac5  lea     rcx, [rbp+var_38]; this
0x140027ac9  call    ?Append@CComBSTR@ATL@@QEAAJAEBV12@@Z; ATL::CComBSTR::Append(ATL::CComBSTR const &)
0x140027ace  test    eax, eax
0x140027ad0  jns     short loc_140027ADD
0x140027ad2  mov     r9d, 7DFh
0x140027ad8  jmp     loc_1400279D4
0x140027add  lea     rdx, [rbp+var_10]; struct ATL::CComBSTR *
0x140027ae1  lea     rcx, [rbp+var_38]; this
0x140027ae5  call    ?Append@CComBSTR@ATL@@QEAAJAEBV12@@Z; ATL::CComBSTR::Append(ATL::CComBSTR const &)
0x140027aea  test    eax, eax
0x140027aec  jns     short loc_140027AF9
0x140027aee  mov     r9d, 7E0h
0x140027af4  jmp     loc_1400279D4
0x140027af9  lea     rdx, [rbp+var_18]; struct ATL::CComBSTR *
0x140027afd  lea     rcx, [rbp+var_38]; this
0x140027b01  call    ?Append@CComBSTR@ATL@@QEAAJAEBV12@@Z; ATL::CComBSTR::Append(ATL::CComBSTR const &)
0x140027b06  test    eax, eax
0x140027b08  jns     short loc_140027B15
0x140027b0a  mov     r9d, 7E1h
0x140027b10  jmp     loc_1400279D4
0x140027b15  lea     rax, [rbp+var_40]
0x140027b19  mov     [rsp+70h+ppv], rax; ppv
0x140027b1e  lea     r9, _GUID_37473440_9cef_4061_9da2_0730773e7806; riid
0x140027b25  xor     edx, edx; pUnkOuter
0x140027b27  lea     r8d, [rdx+4]; dwClsContext
0x140027b2b  lea     rcx, _GUID_d0e55f9f_0021_42fe_a1db_c41f5b564efe; rclsid
0x140027b32  call    cs:__imp_CoCreateInstance
0x140027b39  nop     dword ptr [rax+rax+00h]
0x140027b3e  mov     ebx, eax
0x140027b40  test    eax, eax
0x140027b42  jns     short loc_140027B66
0x140027b44  lea     r8, aD0e55f9f002142; "D0E55F9F-0021-42fe-A1DB-C41F5B564EFE"
0x140027b4b  lea     rdx, COM_Problem; struct _EVENT_DESCRIPTOR *
0x140027b52  call    ?LogEvent@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAG@Z; CEventLogger::LogEvent(_EVENT_DESCRIPTOR const *,ushort *)
0x140027b57  mov     [rsp+70h+var_48], ebx
0x140027b5b  mov     r9d, 7F0h
0x140027b61  jmp     loc_1400279D8
0x140027b66  mov     esi, 8000FFFFh
0x140027b6b  mov     rcx, [rbp+var_40]
0x140027b6f  mov     rax, [rcx]
0x140027b72  lea     r8, [rbp+arg_0]
0x140027b76  lea     rdx, [rbp+arg_10]
0x140027b7a  mov     rax, [rax+78h]
0x140027b7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140027b83  test    eax, eax
0x140027b85  jns     short loc_140027B92
0x140027b87  mov     r9d, 7F5h
0x140027b8d  jmp     loc_1400279D4
0x140027b92  mov     rcx, [rbp+var_40]
0x140027b96  mov     rax, [rcx]
0x140027b99  mov     rdx, [rbp+var_8]
0x140027b9d  mov     rax, [rax+60h]
0x140027ba1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140027ba6  mov     rcx, [rbp+var_40]
0x140027baa  mov     rax, [rcx]
0x140027bad  mov     rdx, [rbp+var_38]
0x140027bb1  mov     rax, [rax+50h]
0x140027bb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140027bba  mov     rcx, [rbp+var_40]
0x140027bbe  mov     rax, [rcx]
0x140027bc1  mov     rdx, [rbp+bstrString]
0x140027bc5  mov     rax, [rax+40h]
0x140027bc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140027bce  mov     rcx, [rbp+var_40]
0x140027bd2  mov     rax, [rcx]
0x140027bd5  lea     r8, [rbp+arg_0]
0x140027bd9  lea     rdx, [rbp+arg_18]
0x140027bdd  mov     rax, [rax+68h]
0x140027be1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140027be6  test    eax, eax
0x140027be8  jns     short loc_140027BF5
0x140027bea  mov     r9d, 7FBh
0x140027bf0  jmp     loc_1400279D4
0x140027bf5  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x140027bfc  add     rcx, 1F0h
0x140027c03  mov     dword ptr [rcx+1Ch], 1
0x140027c0a  xor     edx, edx
0x140027c0c  call    ?ProcessRAEvent@CSqmManager@@QEAAXW4_RASQM_EVENT@@@Z; CSqmManager::ProcessRAEvent(_RASQM_EVENT)
0x140027c11  lea     rdx, Invitation_Opened; struct _EVENT_DESCRIPTOR *
0x140027c18  call    ?LogEvent@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@@Z; CEventLogger::LogEvent(_EVENT_DESCRIPTOR const *)
0x140027c1d  mov     esi, r15d
0x140027c20  mov     rcx, [rbp+var_40]
0x140027c24  test    rcx, rcx
0x140027c27  jz      short loc_140027C39
0x140027c29  mov     rax, [rcx]
0x140027c2c  mov     rax, [rax+10h]
0x140027c30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140027c35  mov     [rbp+var_40], r15
0x140027c39  cmp     [rbp+bstrString], r15
0x140027c3d  jz      short loc_140027C4F
0x140027c3f  mov     rcx, [rbp+bstrString]; bstrString
0x140027c43  call    cs:__imp_SysFreeString
0x140027c4a  nop     dword ptr [rax+rax+00h]
0x140027c4f  cmp     esi, 8000FFFFh
0x140027c55  jnz     short loc_140027C64
0x140027c57  lea     rdx, SMAPI_Problem; struct _EVENT_DESCRIPTOR *
0x140027c5e  call    ?LogEvent@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@@Z; CEventLogger::LogEvent(_EVENT_DESCRIPTOR const *)
0x140027c63  nop
0x140027c64  mov     rcx, [rbp+var_38]; bstrString
0x140027c68  call    cs:__imp_SysFreeString
0x140027c6f  nop     dword ptr [rax+rax+00h]
0x140027c74  nop
0x140027c75  mov     rcx, [rbp+var_28]; bstrString
0x140027c79  call    cs:__imp_SysFreeString
0x140027c80  nop     dword ptr [rax+rax+00h]
0x140027c85  nop
0x140027c86  mov     rcx, [rbp+var_20]; bstrString
0x140027c8a  call    cs:__imp_SysFreeString
0x140027c91  nop     dword ptr [rax+rax+00h]
0x140027c96  nop
0x140027c97  mov     rcx, [rbp+var_18]; bstrString
0x140027c9b  call    cs:__imp_SysFreeString
0x140027ca2  nop     dword ptr [rax+rax+00h]
0x140027ca7  nop
0x140027ca8  mov     rcx, [rbp+var_10]; bstrString
0x140027cac  call    cs:__imp_SysFreeString
0x140027cb3  nop     dword ptr [rax+rax+00h]
0x140027cb8  nop
0x140027cb9  mov     rcx, [rbp+var_8]; bstrString
0x140027cbd  call    cs:__imp_SysFreeString
0x140027cc4  nop     dword ptr [rax+rax+00h]
0x140027cc9  mov     eax, esi
0x140027ccb  add     rsp, 70h
0x140027ccf  pop     r15
0x140027cd1  pop     rdi
0x140027cd2  pop     rsi
0x140027cd3  pop     rbx
0x140027cd4  pop     rbp
0x140027cd5  retn
```
