# WriteTelemetryForGPSecuritySettings(bool,IWbemServices *)

- ea: `0x180057be4`
- end: `0x180058590`
- name: `?WriteTelemetryForGPSecuritySettings@@YAX_NPEAUIWbemServices@@@Z`
- size: `2476`
- prototype: `void __fastcall(bool, struct IWbemServices *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18006a2e0`

## callees

- `0x1800535a0`
- `0x180057be4`
- `0x1800585e8`
- `0x180063aec`
- `0x18006b5f0`
- `0x1800705e8`
- `0x1800bf010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180057c21`
- `OLEAUT32!__imp_SysAllocString` at `0x180057c3f`
- `OLEAUT32!__imp_SysAllocString` at `0x180057d28`
- `OLEAUT32!__imp_SysAllocString` at `0x180057d46`
- `OLEAUT32!__imp_SysAllocString` at `0x1800580c0`
- `OLEAUT32!__imp_SysAllocString` at `0x1800580de`
- `OLEAUT32!__imp_SysAllocString` at `0x180057c21`
- `OLEAUT32!__imp_SysAllocString` at `0x180057c3f`
- `OLEAUT32!__imp_SysAllocString` at `0x180057d28`
- `OLEAUT32!__imp_SysAllocString` at `0x180057d46`
- `OLEAUT32!__imp_SysAllocString` at `0x1800580c0`
- `OLEAUT32!__imp_SysAllocString` at `0x1800580de`
- `OLEAUT32!__imp_SysFreeString` at `0x180057c75`
- `OLEAUT32!__imp_SysFreeString` at `0x180057d7c`
- `OLEAUT32!__imp_SysFreeString` at `0x180057e2d`
- `OLEAUT32!__imp_SysFreeString` at `0x180057ece`
- `OLEAUT32!__imp_SysFreeString` at `0x180057f6a`
- `OLEAUT32!__imp_SysFreeString` at `0x180057ff3`
- `OLEAUT32!__imp_SysFreeString` at `0x18005808f`
- `OLEAUT32!__imp_SysFreeString` at `0x180058116`
- `OLEAUT32!__imp_SysFreeString` at `0x1800581c6`
- `OLEAUT32!__imp_SysFreeString` at `0x180058265`
- `OLEAUT32!__imp_SysFreeString` at `0x1800582ff`
- `OLEAUT32!__imp_SysFreeString` at `0x18005837d`
- `OLEAUT32!__imp_SysFreeString` at `0x180058414`
- `OLEAUT32!__imp_SysFreeString` at `0x180058492`
- `OLEAUT32!__imp_SysFreeString` at `0x180058524`
- `OLEAUT32!__imp_SysFreeString` at `0x180058542`
- `OLEAUT32!__imp_SysFreeString` at `0x180057c75`
- `OLEAUT32!__imp_SysFreeString` at `0x180057d7c`
- `OLEAUT32!__imp_SysFreeString` at `0x180057e2d`
- `OLEAUT32!__imp_SysFreeString` at `0x180057ece`
- `OLEAUT32!__imp_SysFreeString` at `0x180057f6a`
- `OLEAUT32!__imp_SysFreeString` at `0x180057ff3`
- `OLEAUT32!__imp_SysFreeString` at `0x18005808f`
- `OLEAUT32!__imp_SysFreeString` at `0x180058116`
- `OLEAUT32!__imp_SysFreeString` at `0x1800581c6`
- `OLEAUT32!__imp_SysFreeString` at `0x180058265`
- `OLEAUT32!__imp_SysFreeString` at `0x1800582ff`
- `OLEAUT32!__imp_SysFreeString` at `0x18005837d`
- `OLEAUT32!__imp_SysFreeString` at `0x180058414`
- `OLEAUT32!__imp_SysFreeString` at `0x180058492`
- `OLEAUT32!__imp_SysFreeString` at `0x180058524`
- `OLEAUT32!__imp_SysFreeString` at `0x180058542`

## string_xrefs

- `0x180057c1a`: `SELECT * FROM RSOP_SecuritySettingNumeric`
- `0x180057d21`: `SELECT * FROM RSOP_SecuritySettingBoolean`
- `0x180057cd4`: `SecuritySettingNumeric`
- `0x180057dd8`: `SecuritySettingBoolean`
- `0x180057e74`: `SELECT * FROM RSOP_SecuritySettingString`
- `0x180057f24`: `SecuritySettingString`
- `0x180058049`: `SecurityAuditPolicy`
- `0x180058171`: `SecurityRestrictGroup`
- `0x1800582be`: `SecurityRestrictGroupEx`
- `0x180058329`: `SELECT * FROM RSOP_SystemService`
- `0x1800583b5`: `Service`
- `0x1800583d3`: `SecurityService`
- `0x18005843e`: `SELECT * FROM RSOP_UserPrivilegeRight`
- `0x1800584e5`: `SecurityUserPrivilegeRight`

## pseudocode

```c
// Hidden C++ exception states: #wind=25
void __fastcall WriteTelemetryForGPSecuritySettings(char a1, struct IWbemServices *a2)
{
  OLECHAR *v3; // rsi
  HRESULT (__stdcall *ExecQuery)(IWbemServices *, const BSTR, const BSTR, int, IWbemContext *, IEnumWbemClassObject **); // rdi
  OLECHAR *v5; // rbx
  int v6; // eax
  OLECHAR *v7; // rdi
  HRESULT (__stdcall *v8)(IWbemServices *, const BSTR, const BSTR, int, IWbemContext *, IEnumWbemClassObject **); // r14
  OLECHAR *v9; // rbx
  CGPRegistryTelemetry *v10; // rcx
  int v11; // ebx
  HRESULT (__stdcall *v12)(IWbemServices *, const BSTR, const BSTR, int, IWbemContext *, IEnumWbemClassObject **); // rbx
  XBStr *v13; // rax
  int v14; // ebx
  HRESULT (__stdcall *v15)(IWbemServices *, const BSTR, const BSTR, int, IWbemContext *, IEnumWbemClassObject **); // rbx
  XBStr *v16; // rax
  int v17; // ebx
  OLECHAR *v18; // rdi
  HRESULT (__stdcall *v19)(IWbemServices *, const BSTR, const BSTR, int, IWbemContext *, IEnumWbemClassObject **); // r14
  OLECHAR *v20; // rbx
  int v21; // r14d
  HRESULT (__stdcall *v22)(IWbemServices *, const BSTR, const BSTR, int, IWbemContext *, IEnumWbemClassObject **); // rbx
  XBStr *v23; // rax
  int v24; // ebx
  HRESULT (__stdcall *v25)(IWbemServices *, const BSTR, const BSTR, int, IWbemContext *, IEnumWbemClassObject **); // rbx
  XBStr *v26; // rax
  int v27; // ebx
  HRESULT (__stdcall *v28)(IWbemServices *, const BSTR, const BSTR, int, IWbemContext *, IEnumWbemClassObject **); // rbx
  XBStr *v29; // rax
  __int64 v30; // [rsp+40h] [rbp-39h] BYREF
  BSTR v31; // [rsp+48h] [rbp-31h] BYREF
  unsigned __int16 *v32[2]; // [rsp+50h] [rbp-29h] BYREF
  __int64 v33; // [rsp+60h] [rbp-19h]
  BSTR v34; // [rsp+68h] [rbp-11h] BYREF
  __int64 v35; // [rsp+70h] [rbp-9h] BYREF
  __int64 v36; // [rsp+78h] [rbp-1h] BYREF
  BSTR bstrString[10]; // [rsp+80h] [rbp+7h] BYREF
  int v38; // [rsp+E0h] [rbp+67h] BYREF
  OLECHAR *v39; // [rsp+F0h] [rbp+77h] BYREF
  __int64 v40; // [rsp+F8h] [rbp+7Fh] BYREF

  bstrString[1] = 0;
  if ( a1 )
  {
    v36 = 0;
    v35 = 0;
    v3 = SysAllocString(L"SELECT * FROM RSOP_SecuritySettingNumeric");
    bstrString[2] = v3;
    ExecQuery = a2->lpVtbl->ExecQuery;
    v5 = SysAllocString(L"WQL");
    v39 = v5;
    LODWORD(ExecQuery) = ((__int64 (__fastcall *)(struct IWbemServices *, OLECHAR *, OLECHAR *, __int64, _QWORD, __int64 *))ExecQuery)(
                           a2,
                           v5,
                           v3,
                           32,
                           0,
                           &v36);
    SysFreeString(v5);
    v38 = 0;
    if ( (int)ExecQuery >= 0 )
    {
      while ( 1 )
      {
        v6 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *, int *))(*(_QWORD *)v36 + 32LL))(
               v36,
               0xFFFFFFFFLL,
               1,
               &v35,
               &v38);
        if ( v6 )
          break;
        *(_OWORD *)v32 = 0;
        v33 = 0;
        if ( (*(int (__fastcall **)(__int64, const wchar_t *, _QWORD, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v35 + 32LL))(
               v35,
               L"KeyName",
               0,
               v32,
               0,
               0) >= 0
          && ((__int64)v32[0] & 8) != 0 )
        {
          WritePolicyToTelemetryIfNeeded(L"SecuritySettingNumeric", v32[1]);
        }
        XInterface<IWbemServices>::operator=(&v35);
      }
      if ( v6 >= 0 )
      {
        v34 = 0;
        v30 = 0;
        v40 = 0;
        v7 = SysAllocString(L"SELECT * FROM RSOP_SecuritySettingBoolean");
        bstrString[0] = v7;
        v8 = a2->lpVtbl->ExecQuery;
        v9 = SysAllocString(L"WQL");
        v31 = v9;
        ((void (__fastcall *)(struct IWbemServices *, OLECHAR *, OLECHAR *, __int64, _QWORD, __int64 *))v8)(
          a2,
          v9,
          v7,
          32,
          0,
          &v30);
        SysFreeString(v9);
        LODWORD(v39) = 0;
        while ( 1 )
        {
          v11 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *, OLECHAR **))(*(_QWORD *)v30 + 32LL))(
                  v30,
                  0xFFFFFFFFLL,
                  1,
                  &v40,
                  &v39);
          if ( v11 )
            break;
          *(_OWORD *)v32 = 0;
          v33 = 0;
          if ( (*(int (__fastcall **)(__int64, const wchar_t *, _QWORD, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v40 + 32LL))(
                 v40,
                 L"KeyName",
                 0,
                 v32,
                 0,
                 0) >= 0
            && ((__int64)v32[0] & 8) != 0
            && qword_18012A218 )
          {
            CGPRegistryTelemetry::WritePolicyToTelemetryIfNeeded(v10, L"SecuritySettingBoolean", v32[1]);
          }
          if ( v40 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
          v40 = 0;
        }
        SysFreeString(v7);
        if ( v40 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
        if ( v30 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
        if ( v11 >= 0 )
        {
          v34 = 0;
          v30 = 0;
          v40 = 0;
          XBStr::XBStr((XBStr *)&v31, L"SELECT * FROM RSOP_SecuritySettingString");
          v12 = a2->lpVtbl->ExecQuery;
          v13 = XBStr::XBStr((XBStr *)bstrString, L"WQL");
          v14 = ((__int64 (__fastcall *)(struct IWbemServices *, _QWORD, BSTR, __int64, _QWORD, __int64 *))v12)(
                  a2,
                  *(_QWORD *)v13,
                  v31,
                  32,
                  0,
                  &v30);
          SysFreeString(bstrString[0]);
          LODWORD(v39) = 0;
          if ( v14 >= 0 )
          {
            while ( 1 )
            {
              v14 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *, OLECHAR **))(*(_QWORD *)v30 + 32LL))(
                      v30,
                      0xFFFFFFFFLL,
                      1,
                      &v40,
                      &v39);
              if ( v14 )
                break;
              *(_OWORD *)v32 = 0;
              v33 = 0;
              if ( (*(int (__fastcall **)(__int64, const wchar_t *, _QWORD, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v40 + 32LL))(
                     v40,
                     L"KeyName",
                     0,
                     v32,
                     0,
                     0) >= 0
                && ((__int64)v32[0] & 8) != 0 )
              {
                WritePolicyToTelemetryIfNeeded(L"SecuritySettingString", v32[1]);
              }
              XInterface<IWbemServices>::operator=(&v40);
            }
          }
          SysFreeString(v31);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v40);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v30);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v34);
          if ( v14 >= 0 )
          {
            v30 = 0;
            v40 = 0;
            XBStr::XBStr((XBStr *)&v31, L"SELECT * FROM RSOP_AuditPolicy");
            v15 = a2->lpVtbl->ExecQuery;
            v16 = XBStr::XBStr((XBStr *)&v34, L"WQL");
            v17 = ((__int64 (__fastcall *)(struct IWbemServices *, _QWORD, BSTR, __int64, _QWORD, __int64 *))v15)(
                    a2,
                    *(_QWORD *)v16,
                    v31,
                    32,
                    0,
                    &v30);
            SysFreeString(v34);
            LODWORD(v39) = 0;
            if ( v17 >= 0 )
            {
              while ( 1 )
              {
                v17 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *, OLECHAR **))(*(_QWORD *)v30 + 32LL))(
                        v30,
                        0xFFFFFFFFLL,
                        1,
                        &v40,
                        &v39);
                if ( v17 )
                  break;
                *(_OWORD *)v32 = 0;
                v33 = 0;
                if ( (*(int (__fastcall **)(__int64, const wchar_t *, _QWORD, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v40 + 32LL))(
                       v40,
                       L"Category",
                       0,
                       v32,
                       0,
                       0) >= 0
                  && ((__int64)v32[0] & 8) != 0 )
                {
                  WritePolicyToTelemetryIfNeeded(L"SecurityAuditPolicy", v32[1]);
                }
                XInterface<IWbemServices>::operator=(&v40);
              }
            }
            SysFreeString(v31);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v40);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v30);
            if ( v17 >= 0 )
            {
              v30 = 0;
              v40 = 0;
              v18 = SysAllocString(L"SELECT * FROM RSOP_RestrictedGroup");
              v34 = v18;
              v19 = a2->lpVtbl->ExecQuery;
              v20 = SysAllocString(L"WQL");
              bstrString[0] = v20;
              v21 = ((__int64 (__fastcall *)(struct IWbemServices *, OLECHAR *, OLECHAR *, __int64, _QWORD, __int64 *))v19)(
                      a2,
                      v20,
                      v18,
                      32,
                      0,
                      &v30);
              SysFreeString(v20);
              LODWORD(v39) = 0;
              if ( v21 >= 0 )
              {
                while ( 1 )
                {
                  v21 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *, OLECHAR **))(*(_QWORD *)v30 + 32LL))(
                          v30,
                          0xFFFFFFFFLL,
                          1,
                          &v40,
                          &v39);
                  if ( v21 )
                    break;
                  *(_OWORD *)v32 = 0;
                  v33 = 0;
                  if ( (*(int (__fastcall **)(__int64, const wchar_t *, _QWORD, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v40 + 32LL))(
                         v40,
                         L"GroupName",
                         0,
                         v32,
                         0,
                         0) >= 0
                    && ((__int64)v32[0] & 8) != 0 )
                  {
                    WritePolicyToTelemetryIfNeeded(L"SecurityRestrictGroup", v32[1]);
                  }
                  if ( v40 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
                  v40 = 0;
                }
              }
              SysFreeString(v18);
              if ( v40 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
              if ( v30 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
              if ( v21 >= 0 )
              {
                v30 = 0;
                v40 = 0;
                XBStr::XBStr((XBStr *)&v31, L"SELECT * FROM RSOP_RestrictedGroupEx");
                v22 = a2->lpVtbl->ExecQuery;
                v23 = XBStr::XBStr((XBStr *)&v34, L"WQL");
                v24 = ((__int64 (__fastcall *)(struct IWbemServices *, _QWORD, BSTR, __int64, _QWORD, __int64 *))v22)(
                        a2,
                        *(_QWORD *)v23,
                        v31,
                        32,
                        0,
                        &v30);
                SysFreeString(v34);
                LODWORD(v39) = 0;
                if ( v24 >= 0 )
                {
                  while ( 1 )
                  {
                    v24 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *, OLECHAR **))(*(_QWORD *)v30 + 32LL))(
                            v30,
                            0xFFFFFFFFLL,
                            1,
                            &v40,
                            &v39);
                    if ( v24 )
                      break;
                    *(_OWORD *)v32 = 0;
                    v33 = 0;
                    if ( (*(int (__fastcall **)(__int64, const wchar_t *, _QWORD, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v40 + 32LL))(
                           v40,
                           L"GroupName",
                           0,
                           v32,
                           0,
                           0) >= 0
                      && ((__int64)v32[0] & 8) != 0 )
                    {
                      WritePolicyToTelemetryIfNeeded(L"SecurityRestrictGroupEx", v32[1]);
                    }
                    XInterface<IWbemServices>::operator=(&v40);
                  }
                }
                SysFreeString(v31);
                ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v40);
                ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v30);
                if ( v24 >= 0 )
                {
                  v30 = 0;
                  v40 = 0;
                  XBStr::XBStr((XBStr *)&v31, L"SELECT * FROM RSOP_SystemService");
                  v25 = a2->lpVtbl->ExecQuery;
                  v26 = XBStr::XBStr((XBStr *)&v34, L"WQL");
                  v27 = ((__int64 (__fastcall *)(struct IWbemServices *, _QWORD, BSTR, __int64, _QWORD, __int64 *))v25)(
                          a2,
                          *(_QWORD *)v26,
                          v31,
                          32,
                          0,
                          &v30);
                  SysFreeString(v34);
                  LODWORD(v39) = 0;
                  if ( v27 >= 0 )
                  {
                    while ( 1 )
                    {
                      v27 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *, OLECHAR **))(*(_QWORD *)v30 + 32LL))(
                              v30,
                              0xFFFFFFFFLL,
                              1,
                              &v40,
                              &v39);
                      if ( v27 )
                        break;
                      *(_OWORD *)v32 = 0;
                      v33 = 0;
                      if ( (*(int (__fastcall **)(__int64, const wchar_t *, _QWORD, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v40 + 32LL))(
                             v40,
                             L"Service",
                             0,
                             v32,
                             0,
                             0) >= 0
                        && ((__int64)v32[0] & 8) != 0 )
                      {
                        WritePolicyToTelemetryIfNeeded(L"SecurityService", v32[1]);
                      }
                      XInterface<IWbemServices>::operator=(&v40);
                    }
                  }
                  SysFreeString(v31);
                  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v40);
                  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v30);
                  if ( v27 >= 0 )
                  {
                    v30 = 0;
                    v40 = 0;
                    XBStr::XBStr((XBStr *)&v31, L"SELECT * FROM RSOP_UserPrivilegeRight");
                    v28 = a2->lpVtbl->ExecQuery;
                    v29 = XBStr::XBStr((XBStr *)&v34, L"WQL");
                    LODWORD(v28) = ((__int64 (__fastcall *)(struct IWbemServices *, _QWORD, BSTR, __int64, _QWORD, __int64 *))v28)(
                                     a2,
                                     *(_QWORD *)v29,
                                     v31,
                                     32,
                                     0,
                                     &v30);
                    SysFreeString(v34);
                    LODWORD(v39) = 0;
                    if ( (int)v28 >= 0 )
                    {
                      while ( !(*(unsigned int (__fastcall **)(__int64, __int64, __int64, __int64 *, OLECHAR **))(*(_QWORD *)v30 + 32LL))(
                                 v30,
                                 0xFFFFFFFFLL,
                                 1,
                                 &v40,
                                 &v39) )
                      {
                        *(_OWORD *)v32 = 0;
                        v33 = 0;
                        if ( (*(int (__fastcall **)(__int64, const wchar_t *, _QWORD, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v40 + 32LL))(
                               v40,
                               L"UserRight",
                               0,
                               v32,
                               0,
                               0) >= 0
                          && ((__int64)v32[0] & 8) != 0 )
                        {
                          WritePolicyToTelemetryIfNeeded(L"SecurityUserPrivilegeRight", v32[1]);
                        }
                        XInterface<IWbemServices>::operator=(&v40);
                      }
                    }
                    SysFreeString(v31);
                    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v40);
                    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v30);
                  }
                }
              }
            }
          }
        }
      }
    }
    SysFreeString(v3);
    if ( v35 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    if ( v36 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
  }
}

```

## disassembly

```asm
0x180057be4  mov     [rsp-8+arg_8], rbx
0x180057be9  push    rbp
0x180057bea  push    rsi
0x180057beb  push    rdi
0x180057bec  push    r12
0x180057bee  push    r13
0x180057bf0  push    r14
0x180057bf2  push    r15
0x180057bf4  lea     rbp, [rsp-27h]
0x180057bf9  sub     rsp, 0A0h
0x180057c00  mov     r15, rdx
0x180057c03  xor     r12d, r12d
0x180057c06  mov     [rbp+57h+var_48], r12
0x180057c0a  test    cl, cl
0x180057c0c  jz      loc_180058575
0x180057c12  mov     [rbp+57h+var_58], r12
0x180057c16  mov     [rbp+57h+var_60], r12
0x180057c1a  lea     rcx, aSelectFromRsop_3; "SELECT * FROM RSOP_SecuritySettingNumer"...
0x180057c21  call    cs:__imp_SysAllocString
0x180057c27  mov     rsi, rax
0x180057c2a  mov     [rbp+57h+var_40], rax
0x180057c2e  mov     rax, [r15]
0x180057c31  mov     rdi, [rax+0A0h]
0x180057c38  lea     rcx, aWql; "WQL"
0x180057c3f  call    cs:__imp_SysAllocString
0x180057c45  mov     rbx, rax
0x180057c48  mov     [rbp+57h+arg_10], rax
0x180057c4c  lea     rax, [rbp+57h+var_58]
0x180057c50  mov     [rsp+0D0h+var_A8], rax
0x180057c55  mov     [rsp+0D0h+var_B0], r12
0x180057c5a  lea     r9d, [r12+20h]
0x180057c5f  mov     r8, rsi
0x180057c62  mov     rdx, rbx
0x180057c65  mov     rcx, r15
0x180057c68  mov     rax, rdi
0x180057c6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057c70  mov     edi, eax
0x180057c72  mov     rcx, rbx; bstrString
0x180057c75  call    cs:__imp_SysFreeString
0x180057c7b  mov     [rbp+57h+arg_0], r12d
0x180057c7f  test    edi, edi
0x180057c81  js      loc_18005853F
0x180057c87  lea     r13d, [r12+1]
0x180057c8c  or      ebx, 0FFFFFFFFh
0x180057c8f  jmp     short loc_180057CE9
0x180057c91  xorps   xmm0, xmm0
0x180057c94  xor     eax, eax
0x180057c96  movups  xmmword ptr [rbp+57h+var_80], xmm0
0x180057c9a  mov     [rbp+57h+var_70], rax
0x180057c9e  mov     rcx, [rbp+57h+var_60]
0x180057ca2  mov     rax, [rcx]
0x180057ca5  mov     [rsp+0D0h+var_A8], r12
0x180057caa  mov     [rsp+0D0h+var_B0], r12
0x180057caf  lea     r9, [rbp+57h+var_80]
0x180057cb3  xor     r8d, r8d
0x180057cb6  lea     rdx, aKeyname; "KeyName"
0x180057cbd  mov     rax, [rax+20h]
0x180057cc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057cc6  test    eax, eax
0x180057cc8  js      short loc_180057CE0
0x180057cca  test    byte ptr [rbp+57h+var_80], 8
0x180057cce  jz      short loc_180057CE0
0x180057cd0  mov     rdx, [rbp+57h+var_80+8]; unsigned __int16 *
0x180057cd4  lea     rcx, aSecuritysettin_0; "SecuritySettingNumeric"
0x180057cdb  call    ?WritePolicyToTelemetryIfNeeded@@YAXPEBG0@Z; WritePolicyToTelemetryIfNeeded(ushort const *,ushort const *)
0x180057ce0  lea     rcx, [rbp+57h+var_60]
0x180057ce4  call    ??4?$XInterface@UIWbemServices@@@@QEAAXPEAUIWbemServices@@@Z; XInterface<IWbemServices>::operator=(IWbemServices *)
0x180057ce9  lea     rdx, [rbp+57h+arg_0]
0x180057ced  mov     rcx, [rbp+57h+var_58]
0x180057cf1  mov     [rsp+0D0h+var_B0], rdx
0x180057cf6  mov     rax, [rcx]
0x180057cf9  lea     r9, [rbp+57h+var_60]
0x180057cfd  mov     r8d, r13d
0x180057d00  mov     edx, ebx
0x180057d02  mov     rax, [rax+20h]
0x180057d06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057d0b  test    eax, eax
0x180057d0d  jz      short loc_180057C91
0x180057d0f  js      loc_18005853F
0x180057d15  mov     [rbp+57h+var_68], r12
0x180057d19  mov     [rbp+57h+var_90], r12
0x180057d1d  mov     [rbp+57h+arg_18], r12
0x180057d21  lea     rcx, aSelectFromRsop_1; "SELECT * FROM RSOP_SecuritySettingBoole"...
0x180057d28  call    cs:__imp_SysAllocString
0x180057d2e  mov     rdi, rax
0x180057d31  mov     [rbp+57h+bstrString], rax
0x180057d35  mov     rax, [r15]
0x180057d38  mov     r14, [rax+0A0h]
0x180057d3f  lea     rcx, aWql; "WQL"
0x180057d46  call    cs:__imp_SysAllocString
0x180057d4c  mov     rbx, rax
0x180057d4f  mov     [rbp+57h+var_88], rax
0x180057d53  lea     rax, [rbp+57h+var_90]
0x180057d57  mov     [rsp+0D0h+var_A8], rax
0x180057d5c  mov     [rsp+0D0h+var_B0], r12
0x180057d61  mov     r9d, 20h ; ' '
0x180057d67  mov     r8, rdi
0x180057d6a  mov     rdx, rbx
0x180057d6d  mov     rcx, r15
0x180057d70  mov     rax, r14
0x180057d73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057d78  nop
0x180057d79  mov     rcx, rbx; bstrString
0x180057d7c  call    cs:__imp_SysFreeString
0x180057d82  mov     dword ptr [rbp+57h+arg_10], r12d
0x180057d86  or      r14d, 0FFFFFFFFh
0x180057d8a  jmp     short loc_180057DFD
0x180057d8c  xorps   xmm0, xmm0
0x180057d8f  xor     eax, eax
0x180057d91  movups  xmmword ptr [rbp+57h+var_80], xmm0
0x180057d95  mov     [rbp+57h+var_70], rax
0x180057d99  mov     rcx, [rbp+57h+arg_18]
0x180057d9d  mov     rax, [rcx]
0x180057da0  mov     [rsp+0D0h+var_A8], r12
0x180057da5  mov     [rsp+0D0h+var_B0], r12
0x180057daa  lea     r9, [rbp+57h+var_80]
0x180057dae  xor     r8d, r8d
0x180057db1  lea     rdx, aKeyname; "KeyName"
0x180057db8  mov     rax, [rax+20h]
0x180057dbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057dc1  test    eax, eax
0x180057dc3  js      short loc_180057DE4
0x180057dc5  test    byte ptr [rbp+57h+var_80], 8
0x180057dc9  jz      short loc_180057DE4
0x180057dcb  cmp     cs:qword_18012A218, r12
0x180057dd2  jz      short loc_180057DE4
0x180057dd4  mov     r8, [rbp+57h+var_80+8]; unsigned __int16 *
0x180057dd8  lea     rdx, aSecuritysettin; "SecuritySettingBoolean"
0x180057ddf  call    ?WritePolicyToTelemetryIfNeeded@CGPRegistryTelemetry@@QEAAXPEBG0@Z; CGPRegistryTelemetry::WritePolicyToTelemetryIfNeeded(ushort const *,ushort const *)
0x180057de4  mov     rcx, [rbp+57h+arg_18]
0x180057de8  test    rcx, rcx
0x180057deb  jz      short loc_180057DF9
0x180057ded  mov     rax, [rcx]
0x180057df0  mov     rax, [rax+10h]
0x180057df4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057df9  mov     [rbp+57h+arg_18], r12
0x180057dfd  lea     rdx, [rbp+57h+arg_10]
0x180057e01  mov     rcx, [rbp+57h+var_90]
0x180057e05  mov     [rsp+0D0h+var_B0], rdx
0x180057e0a  mov     rax, [rcx]
0x180057e0d  lea     r9, [rbp+57h+arg_18]
0x180057e11  mov     r8d, r13d
0x180057e14  mov     edx, r14d
0x180057e17  mov     rax, [rax+20h]
0x180057e1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057e20  test    eax, eax
0x180057e22  mov     ebx, eax
0x180057e24  jz      loc_180057D8C
0x180057e2a  mov     rcx, rdi; bstrString
0x180057e2d  call    cs:__imp_SysFreeString
0x180057e33  nop
0x180057e34  mov     rcx, [rbp+57h+arg_18]
0x180057e38  test    rcx, rcx
0x180057e3b  jz      short loc_180057E4A
0x180057e3d  mov     rax, [rcx]
0x180057e40  mov     rax, [rax+10h]
0x180057e44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057e49  nop
0x180057e4a  mov     rcx, [rbp+57h+var_90]
0x180057e4e  test    rcx, rcx
0x180057e51  jz      short loc_180057E60
0x180057e53  mov     rax, [rcx]
0x180057e56  mov     rax, [rax+10h]
0x180057e5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057e5f  nop
0x180057e60  test    ebx, ebx
0x180057e62  js      loc_18005853F
0x180057e68  mov     [rbp+57h+var_68], r12
0x180057e6c  mov     [rbp+57h+var_90], r12
0x180057e70  mov     [rbp+57h+arg_18], r12
0x180057e74  lea     rdx, aSelectFromRsop_0; "SELECT * FROM RSOP_SecuritySettingStrin"...
0x180057e7b  lea     rcx, [rbp+57h+var_88]; this
0x180057e7f  call    ??0XBStr@@QEAA@PEBG@Z; XBStr::XBStr(ushort const *)
0x180057e84  nop
0x180057e85  mov     rax, [r15]
0x180057e88  mov     rbx, [rax+0A0h]
0x180057e8f  lea     rdx, aWql; "WQL"
0x180057e96  lea     rcx, [rbp+57h+bstrString]; this
0x180057e9a  call    ??0XBStr@@QEAA@PEBG@Z; XBStr::XBStr(ushort const *)
0x180057e9f  nop
0x180057ea0  lea     rcx, [rbp+57h+var_90]
0x180057ea4  mov     [rsp+0D0h+var_A8], rcx
0x180057ea9  mov     [rsp+0D0h+var_B0], r12
0x180057eae  mov     edi, 20h ; ' '
0x180057eb3  mov     r9d, edi
0x180057eb6  mov     r8, [rbp+57h+var_88]
0x180057eba  mov     rdx, [rax]
0x180057ebd  mov     rcx, r15
0x180057ec0  mov     rax, rbx
0x180057ec3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057ec8  mov     ebx, eax
0x180057eca  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180057ece  call    cs:__imp_SysFreeString
0x180057ed4  mov     dword ptr [rbp+57h+arg_10], r12d
0x180057ed8  test    ebx, ebx
0x180057eda  jns     short loc_180057F39
0x180057edc  jmp     loc_180057F66
0x180057ee1  xorps   xmm0, xmm0
0x180057ee4  xor     eax, eax
0x180057ee6  movups  xmmword ptr [rbp+57h+var_80], xmm0
0x180057eea  mov     [rbp+57h+var_70], rax
0x180057eee  mov     rcx, [rbp+57h+arg_18]
0x180057ef2  mov     rax, [rcx]
0x180057ef5  mov     [rsp+0D0h+var_A8], r12
0x180057efa  mov     [rsp+0D0h+var_B0], r12
0x180057eff  lea     r9, [rbp+57h+var_80]
0x180057f03  xor     r8d, r8d
0x180057f06  lea     rdx, aKeyname; "KeyName"
0x180057f0d  mov     rax, [rax+20h]
0x180057f11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057f16  test    eax, eax
0x180057f18  js      short loc_180057F30
0x180057f1a  test    byte ptr [rbp+57h+var_80], 8
0x180057f1e  jz      short loc_180057F30
0x180057f20  mov     rdx, [rbp+57h+var_80+8]; unsigned __int16 *
0x180057f24  lea     rcx, aSecuritysettin_1; "SecuritySettingString"
0x180057f2b  call    ?WritePolicyToTelemetryIfNeeded@@YAXPEBG0@Z; WritePolicyToTelemetryIfNeeded(ushort const *,ushort const *)
0x180057f30  lea     rcx, [rbp+57h+arg_18]
0x180057f34  call    ??4?$XInterface@UIWbemServices@@@@QEAAXPEAUIWbemServices@@@Z; XInterface<IWbemServices>::operator=(IWbemServices *)
0x180057f39  lea     rdx, [rbp+57h+arg_10]
0x180057f3d  mov     rcx, [rbp+57h+var_90]
0x180057f41  mov     [rsp+0D0h+var_B0], rdx
0x180057f46  mov     rax, [rcx]
0x180057f49  lea     r9, [rbp+57h+arg_18]
0x180057f4d  mov     r8d, r13d
0x180057f50  mov     edx, r14d
0x180057f53  mov     rax, [rax+20h]
0x180057f57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057f5c  test    eax, eax
0x180057f5e  mov     ebx, eax
0x180057f60  jz      loc_180057EE1
0x180057f66  mov     rcx, [rbp+57h+var_88]; bstrString
0x180057f6a  call    cs:__imp_SysFreeString
0x180057f70  nop
0x180057f71  lea     rcx, [rbp+57h+arg_18]
0x180057f75  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180057f7a  nop
0x180057f7b  lea     rcx, [rbp+57h+var_90]
0x180057f7f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180057f84  nop
0x180057f85  lea     rcx, [rbp+57h+var_68]
0x180057f89  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180057f8e  test    ebx, ebx
0x180057f90  js      loc_18005853F
0x180057f96  mov     [rbp+57h+var_90], r12
0x180057f9a  mov     [rbp+57h+arg_18], r12
0x180057f9e  lea     rdx, aSelectFromRsop_4; "SELECT * FROM RSOP_AuditPolicy"
0x180057fa5  lea     rcx, [rbp+57h+var_88]; this
0x180057fa9  call    ??0XBStr@@QEAA@PEBG@Z; XBStr::XBStr(ushort const *)
0x180057fae  nop
0x180057faf  mov     rax, [r15]
0x180057fb2  mov     rbx, [rax+0A0h]
0x180057fb9  lea     rdx, aWql; "WQL"
0x180057fc0  lea     rcx, [rbp+57h+var_68]; this
0x180057fc4  call    ??0XBStr@@QEAA@PEBG@Z; XBStr::XBStr(ushort const *)
0x180057fc9  nop
0x180057fca  lea     rcx, [rbp+57h+var_90]
0x180057fce  mov     [rsp+0D0h+var_A8], rcx
0x180057fd3  mov     [rsp+0D0h+var_B0], r12
0x180057fd8  mov     r9d, edi
0x180057fdb  mov     r8, [rbp+57h+var_88]
0x180057fdf  mov     rdx, [rax]
0x180057fe2  mov     rcx, r15
0x180057fe5  mov     rax, rbx
0x180057fe8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057fed  mov     ebx, eax
0x180057fef  mov     rcx, [rbp+57h+var_68]; bstrString
0x180057ff3  call    cs:__imp_SysFreeString
0x180057ff9  mov     dword ptr [rbp+57h+arg_10], r12d
0x180057ffd  test    ebx, ebx
0x180057fff  jns     short loc_18005805E
0x180058001  jmp     loc_18005808B
0x180058006  xorps   xmm0, xmm0
0x180058009  xor     eax, eax
0x18005800b  movups  xmmword ptr [rbp+57h+var_80], xmm0
0x18005800f  mov     [rbp+57h+var_70], rax
0x180058013  mov     rcx, [rbp+57h+arg_18]
0x180058017  mov     rax, [rcx]
0x18005801a  mov     [rsp+0D0h+var_A8], r12
0x18005801f  mov     [rsp+0D0h+var_B0], r12
0x180058024  lea     r9, [rbp+57h+var_80]
0x180058028  xor     r8d, r8d
0x18005802b  lea     rdx, aCategory; "Category"
0x180058032  mov     rax, [rax+20h]
0x180058036  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005803b  test    eax, eax
0x18005803d  js      short loc_180058055
0x18005803f  test    byte ptr [rbp+57h+var_80], 8
0x180058043  jz      short loc_180058055
0x180058045  mov     rdx, [rbp+57h+var_80+8]; unsigned __int16 *
0x180058049  lea     rcx, aSecurityauditp; "SecurityAuditPolicy"
0x180058050  call    ?WritePolicyToTelemetryIfNeeded@@YAXPEBG0@Z; WritePolicyToTelemetryIfNeeded(ushort const *,ushort const *)
0x180058055  lea     rcx, [rbp+57h+arg_18]
0x180058059  call    ??4?$XInterface@UIWbemServices@@@@QEAAXPEAUIWbemServices@@@Z; XInterface<IWbemServices>::operator=(IWbemServices *)
0x18005805e  lea     rdx, [rbp+57h+arg_10]
0x180058062  mov     rcx, [rbp+57h+var_90]
0x180058066  mov     [rsp+0D0h+var_B0], rdx
0x18005806b  mov     rax, [rcx]
0x18005806e  lea     r9, [rbp+57h+arg_18]
0x180058072  mov     r8d, r13d
  ... truncated ...
```
