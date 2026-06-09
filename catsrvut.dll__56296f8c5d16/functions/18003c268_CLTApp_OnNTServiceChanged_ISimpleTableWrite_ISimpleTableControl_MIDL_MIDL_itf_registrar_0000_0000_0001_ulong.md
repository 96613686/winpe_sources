# CLTApp::OnNTServiceChanged(ISimpleTableWrite *,ISimpleTableControl *,__MIDL___MIDL_itf_registrar_0000_0000_0001,ulong)

- ea: `0x18003c268`
- end: `0x18003caa3`
- name: `?OnNTServiceChanged@CLTApp@@AEAAJPEAUISimpleTableWrite@@PEAUISimpleTableControl@@W4__MIDL___MIDL_itf_registrar_0000_0000_0001@@K@Z`
- size: `2107`
- prototype: `__int64 __fastcall(CLTApp *, __int64, __int64, unsigned int, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18003ef60`

## callees

- `0x18003abec`
- `0x18003b36c`
- `0x18003b3f8`
- `0x18003c268`
- `0x180057010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18003c601`
- `msvcrt!_wcsicmp` at `0x18003c735`
- `msvcrt!_wcsicmp` at `0x18003c75e`
- `msvcrt!_wcsicmp` at `0x18003c601`
- `msvcrt!_wcsicmp` at `0x18003c735`
- `msvcrt!_wcsicmp` at `0x18003c75e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ca86`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ca86`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18003c7c1`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18003c7c1`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18003ca3f`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18003ca3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c7fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c837`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c85e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c8e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c935`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c993`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c9de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ca1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c7fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c837`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c85e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c8e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c935`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c993`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c9de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ca1c`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18003c7ec`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18003c7ec`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18003c9fb`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18003ca34`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18003c9fb`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18003ca34`
- `api-ms-win-service-management-l1-1-0!CreateServiceW` at `0x18003c8d3`
- `api-ms-win-service-management-l1-1-0!CreateServiceW` at `0x18003c8d3`
- `api-ms-win-service-management-l1-1-0!DeleteService` at `0x18003c850`
- `api-ms-win-service-management-l1-1-0!DeleteService` at `0x18003ca12`
- `api-ms-win-service-management-l1-1-0!DeleteService` at `0x18003c850`
- `api-ms-win-service-management-l1-1-0!DeleteService` at `0x18003ca12`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18003c829`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18003c927`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18003c829`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18003c927`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x18003c989`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x18003c989`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x18003c9d4`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x18003c9d4`

## string_xrefs

- `0x18003c887`: `NT AUTHORITY\LocalService`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall CLTApp::OnNTServiceChanged(CLTApp *a1, __int64 a2, __int64 a3, unsigned int a4, int a5)
{
  int v6; // r12d
  int v7; // esi
  _QWORD *v8; // rdi
  signed int Dispenser; // ebx
  _QWORD *v10; // rcx
  __int64 v11; // rax
  struct ISimpleTableDispenser *v12; // r13
  int v13; // r15d
  int v14; // esi
  wchar_t *v15; // rcx
  wchar_t *v16; // rax
  HRESULT v17; // eax
  int v18; // r14d
  SC_HANDLE v19; // rsi
  signed int LastError; // eax
  SC_HANDLE v21; // rax
  SC_HANDLE ServiceW; // rdi
  bool v23; // zf
  CLTApp *v24; // rcx
  signed int v25; // eax
  signed int v26; // eax
  signed int v27; // eax
  struct ISimpleTableDispenser *v28; // rcx
  signed int v29; // eax
  signed int v30; // eax
  wchar_t *String2; // [rsp+78h] [rbp-71h] BYREF
  wchar_t *String1; // [rsp+80h] [rbp-69h]
  int v34; // [rsp+88h] [rbp-61h] BYREF
  int v35; // [rsp+8Ch] [rbp-5Dh] BYREF
  int v36; // [rsp+90h] [rbp-59h] BYREF
  struct ISimpleTableDispenser *Info; // [rsp+98h] [rbp-51h] BYREF
  __int64 v38; // [rsp+A0h] [rbp-49h] BYREF
  LPCWSTR lpBinaryPathName; // [rsp+A8h] [rbp-41h] BYREF
  int v40; // [rsp+B0h] [rbp-39h] BYREF
  _QWORD *v41; // [rsp+B8h] [rbp-31h] BYREF
  LPCWSTR lpDisplayName; // [rsp+C0h] [rbp-29h] BYREF
  struct ISimpleTableDispenser *v43; // [rsp+C8h] [rbp-21h] BYREF
  wchar_t *v44; // [rsp+D0h] [rbp-19h] BYREF
  _QWORD v45[2]; // [rsp+D8h] [rbp-11h] BYREF
  int v46; // [rsp+E8h] [rbp-1h]
  int v47; // [rsp+ECh] [rbp+3h]
  int v48; // [rsp+148h] [rbp+5Fh] BYREF
  __int64 v49; // [rsp+150h] [rbp+67h]
  __int64 v50; // [rsp+158h] [rbp+6Fh]
  unsigned int v51; // [rsp+160h] [rbp+77h]

  v51 = a4;
  v50 = a3;
  v49 = a2;
  v6 = 0;
  lpDisplayName = 0;
  lpBinaryPathName = 0;
  v43 = 0;
  String2 = 0;
  v44 = 0;
  String1 = 0;
  v34 = 0;
  v35 = 0;
  v36 = 0;
  v48 = 0;
  v41 = 0;
  v40 = 0;
  v7 = 0;
  Info = 0;
  v38 = 0;
  v8 = (_QWORD *)((char *)a1 + 8);
  Dispenser = (*(__int64 (__fastcall **)(_QWORD *, __int64, int *, _QWORD, _QWORD, wchar_t **))(*((_QWORD *)a1 + 1)
                                                                                              + 152LL))(
                (_QWORD *)a1 + 1,
                6,
                &v34,
                0,
                0,
                &String2);
  if ( Dispenser >= 0 )
  {
    Dispenser = (*(__int64 (__fastcall **)(_QWORD *, __int64, int *, _QWORD, _QWORD, LPCWSTR *))(*v8 + 152LL))(
                  v8,
                  5,
                  &v35,
                  0,
                  0,
                  &lpBinaryPathName);
    if ( Dispenser >= 0 )
    {
      Dispenser = (*(__int64 (__fastcall **)(_QWORD *, __int64, int *, _QWORD, _QWORD, LPCWSTR *))(*v8 + 152LL))(
                    v8,
                    1,
                    &v36,
                    0,
                    0,
                    &lpDisplayName);
      if ( Dispenser >= 0 )
      {
        Dispenser = (*(__int64 (__fastcall **)(_QWORD *, __int64, int *, _QWORD, _QWORD, struct ISimpleTableDispenser **))(*v8 + 152LL))(
                      v8,
                      10,
                      &v48,
                      0,
                      0,
                      &v43);
        if ( Dispenser >= 0 )
        {
          Dispenser = (*(__int64 (__fastcall **)(_QWORD *, __int64, int *, _QWORD, _QWORD, wchar_t **))(*v8 + 152LL))(
                        v8,
                        16,
                        &v40,
                        0,
                        0,
                        &v44);
          if ( Dispenser >= 0 )
          {
            Dispenser = (*(__int64 (__fastcall **)(_QWORD *, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD **))(*v8 + 152LL))(
                          v8,
                          0,
                          0,
                          0,
                          0,
                          &v41);
            if ( Dispenser >= 0 )
            {
              v10 = v41;
              v11 = *v41 - *(_QWORD *)&CLSID_SystemApplication.Data1;
              if ( *v41 == *(_QWORD *)&CLSID_SystemApplication.Data1 )
                v11 = v41[1] - *(_QWORD *)CLSID_SystemApplication.Data4;
              if ( v11 )
              {
                lpBinaryPathName = 0;
                v7 = 1;
                LODWORD(v50) = 1;
                if ( String2 && !*String2 )
                {
                  String2 = 0;
                  Dispenser = (*(__int64 (__fastcall **)(_QWORD *))(*((_QWORD *)a1 + 3) + 80LL))((_QWORD *)a1 + 3);
                  if ( Dispenser < 0 )
                    goto LABEL_120;
                  Dispenser = (*(__int64 (__fastcall **)(_QWORD *, __int64, _QWORD, _QWORD))(*v8 + 160LL))(v8, 6, 0, 0);
                  if ( Dispenser < 0 )
                    goto LABEL_120;
                  Dispenser = (*(__int64 (__fastcall **)(_QWORD *))(*v8 + 144LL))(v8);
                  if ( Dispenser < 0 )
                    goto LABEL_120;
                  v10 = v41;
                }
                v34 &= 2u;
                v35 &= 2u;
                v36 &= 2u;
                v48 &= 2u;
                v45[0] = v10;
                v45[1] = 0;
                v46 = 72;
                v47 = 16;
                Dispenser = CLTApp::GetDispenser(a1, &Info);
                v12 = Info;
                if ( Dispenser < 0 )
                  goto LABEL_118;
                Dispenser = (*(__int64 (__fastcall **)(struct ISimpleTableDispenser *, __int128 *, const struct _GUID *, _QWORD *, __int64, int, int, __int64 *))(*(_QWORD *)Info + 24LL))(
                              Info,
                              &didCOMSERVICES,
                              &TID_APPLICATION,
                              v45,
                              1,
                              1,
                              131073,
                              &v38);
                if ( Dispenser < 0 )
                  goto LABEL_118;
                Dispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v38 + 24LL))(v38);
                if ( Dispenser < 0 )
                  goto LABEL_118;
                Dispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v38 + 40LL))(v38);
                if ( (int)(Dispenser + 0x80000000) >= 0 && Dispenser != -2146367487 )
                  goto LABEL_118;
                v13 = 0;
                v14 = a5;
                if ( v34 || a5 == 3 )
                {
                  if ( Dispenser == -2146367487 )
                  {
                    v16 = String2;
                    if ( a5 != 3 )
                      LOBYTE(v13) = String2 != 0;
                    Dispenser = 0;
                    v15 = String1;
                  }
                  else
                  {
                    Dispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v38 + 64LL))(v38, 6, 0);
                    if ( Dispenser < 0 )
                      goto LABEL_117;
                    v16 = String2;
                    v15 = String1;
                    if ( String1 && (!String2 || v14 == 3) )
                    {
                      v6 = 1;
                    }
                    else if ( String2 && !String1 && v14 != 3 )
                    {
                      v13 = 1;
                    }
                  }
LABEL_37:
                  if ( !v44 )
                  {
LABEL_38:
                    Dispenser = -2147418113;
                    goto LABEL_117;
                  }
                  if ( v16 )
                  {
                    if ( !_wcsicmp(L"Inproc", v44) )
                    {
                      Dispenser = -2146367468;
                      goto LABEL_117;
                    }
                    v16 = String2;
                    v15 = String1;
                  }
                  if ( v15 && v16 )
                  {
                    if ( _wcsicmp(v15, v16) )
                      goto LABEL_38;
                    v16 = String2;
                  }
                  if ( !v13 && !v6 && (!v35 && !v36 && !v48 || !v16) )
                    goto LABEL_117;
                  Info = 0;
                  if ( !v6 )
                  {
                    Dispenser = CLTApp::BuildAppCmdLine(v15, v49, v51, &lpBinaryPathName);
                    if ( Dispenser < 0 )
                      goto LABEL_117;
                  }
                  v17 = CoImpersonateClient();
                  Dispenser = v17;
                  if ( v17 >= 0 )
                  {
                    v18 = 1;
                  }
                  else
                  {
                    if ( v17 != -2147417833 )
                      goto LABEL_117;
                    v18 = 0;
                    Dispenser = 0;
                  }
                  v19 = OpenSCManagerW(0, 0, 0x40000000u);
                  if ( !v19 )
                  {
                    LastError = GetLastError();
                    Dispenser = LastError;
                    if ( LastError > 0 )
                      Dispenser = (unsigned __int16)LastError | 0x80070000;
                    if ( Dispenser < 0 )
                    {
LABEL_115:
                      if ( v18 )
                        CoRevertToSelf();
                      goto LABEL_117;
                    }
                  }
                  if ( v6 )
                  {
                    v21 = OpenServiceW(v19, String1, 0x10000u);
                    ServiceW = v21;
                    if ( v21 )
                    {
                      if ( DeleteService(v21) )
                        goto LABEL_106;
                      v23 = GetLastError() == 1072;
                    }
                    else
                    {
                      v23 = GetLastError() == 1060;
                    }
                    if ( !v23 )
                    {
LABEL_104:
                      v29 = GetLastError();
                      Dispenser = v29;
                      if ( v29 > 0 )
                        Dispenser = (unsigned __int16)v29 | 0x80070000;
                    }
                  }
                  else
                  {
                    if ( v13 )
                    {
                      ServiceW = CreateServiceW(
                                   v19,
                                   String2,
                                   lpDisplayName,
                                   0xF0002u,
                                   0x10u,
                                   3u,
                                   1u,
                                   lpBinaryPathName,
                                   0,
                                   0,
                                   L"rpcss",
                                   L"NT AUTHORITY\\LocalService",
                                   &Password);
                      if ( !ServiceW )
                      {
                        v25 = GetLastError();
                        Dispenser = v25;
                        if ( v25 > 0 )
                          Dispenser = (unsigned __int16)v25 | 0x80070000;
                        if ( Dispenser < 0 )
                          goto LABEL_106;
                      }
                      Dispenser = CLTApp::LogServiceCreate(v24, String2);
                      if ( Dispenser < 0 )
                        goto LABEL_106;
                      Info = v43;
                    }
                    else
                    {
                      ServiceW = OpenServiceW(v19, String2, 2u);
                      if ( !ServiceW )
                      {
                        v26 = GetLastError();
                        Dispenser = v26;
                        if ( v26 > 0 )
                          Dispenser = (unsigned __int16)v26 | 0x80070000;
                        if ( Dispenser < 0 )
                          goto LABEL_106;
                      }
                      if ( !ChangeServiceConfigW(
                              ServiceW,
                              0xFFFFFFFF,
                              0xFFFFFFFF,
                              0xFFFFFFFF,
                              lpBinaryPathName,
                              0,
                              0,
                              0,
                              0,
                              0,
                              lpDisplayName) )
                      {
                        v27 = GetLastError();
                        Dispenser = v27;
                        if ( v27 > 0 )
                          Dispenser = (unsigned __int16)v27 | 0x80070000;
                        if ( Dispenser < 0 )
                          goto LABEL_106;
                      }
                      if ( !v48 )
                        goto LABEL_106;
                      v28 = (struct ISimpleTableDispenser *)&Password;
                      if ( v43 )
                        v28 = v43;
                      Info = v28;
                    }
                    if ( !ChangeServiceConfig2W(ServiceW, 1u, &Info) )
                      goto LABEL_104;
                  }
LABEL_106:
                  if ( v19 )
                    CloseServiceHandle(v19);
                  if ( ServiceW )
                  {
                    if ( Dispenser < 0 )
                    {
                      if ( v13 )
                      {
                        if ( !DeleteService(ServiceW) )
                        {
                          v30 = GetLastError();
                          Dispenser = v30;
                          if ( v30 > 0 )
                            Dispenser = (unsigned __int16)v30 | 0x80070000;
                        }
                      }
                    }
                    CloseServiceHandle(ServiceW);
                  }
                  goto LABEL_115;
                }
                if ( Dispenser >= 0 )
                {
                  Dispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v38 + 64LL))(v38, 6, 0);
                  if ( Dispenser < 0 )
                  {
LABEL_117:
                    v7 = v50;
LABEL_118:
                    if ( v12 )
                      (*(void (__fastcall **)(struct ISimpleTableDispenser *))(*(_QWORD *)v12 + 16LL))(v12);
                    goto LABEL_120;
                  }
                  v15 = String1;
                  v16 = String2;
                  if ( !String1 )
                  {
                    if ( String2 )
                    {
LABEL_31:
                      Dispenser = (*(__int64 (__fastcall **)(_QWORD *))(*((_QWORD *)a1 + 3) + 80LL))((_QWORD *)a1 + 3);
                      if ( Dispenser < 0 )
                        goto LABEL_117;
                      Dispenser = (*(__int64 (__fastcall **)(_QWORD *, __int64, _QWORD, wchar_t *))(*v8 + 160LL))(
                                    v8,
                                    6,
                                    0,
                                    String1);
                      if ( Dispenser < 0 )
                        goto LABEL_117;
                      Dispenser = (*(__int64 (__fastcall **)(_QWORD *))(*v8 + 144LL))(v8);
                      if ( Dispenser < 0 )
                        goto LABEL_117;
                      v15 = String1;
                      v16 = String1;
                      String2 = String1;
                    }
LABEL_36:
                    Dispenser = 0;
                    goto LABEL_37;
                  }
                  if ( !String2 || _wcsicmp(String1, String2) )
                    goto LABEL_31;
                }
                v16 = String2;
                v15 = String1;
                goto LABEL_36;
              }
            }
          }
        }
      }
    }
  }
LABEL_120:
  if ( v38 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
  if ( v7 == 1 && lpBinaryPathName )
    CoTaskMemFree((LPVOID)lpBinaryPathName);
  return (unsigned int)Dispenser;
}

```

## disassembly

```asm
0x18003c268  mov     rax, rsp
0x18003c26b  mov     [rax+20h], r9d
0x18003c26f  mov     [rax+18h], r8
0x18003c273  mov     [rax+10h], rdx
0x18003c277  push    rbp
0x18003c278  push    rbx
0x18003c279  push    rsi
0x18003c27a  push    rdi
0x18003c27b  push    r12
0x18003c27d  push    r13
0x18003c27f  push    r14
0x18003c281  push    r15
0x18003c283  lea     rbp, [rax-57h]
0x18003c287  sub     rsp, 0F8h
0x18003c28e  mov     r14, rcx
0x18003c291  xor     r12d, r12d
0x18003c294  mov     [rbp+4Fh+lpDisplayName], r12
0x18003c298  mov     [rbp+4Fh+var_90], r12
0x18003c29c  mov     [rbp+4Fh+var_70], r12
0x18003c2a0  mov     [rbp+4Fh+String2], r12
0x18003c2a4  mov     [rbp+4Fh+var_68], r12
0x18003c2a8  mov     [rbp+4Fh+String1], r12
0x18003c2ac  mov     [rbp+4Fh+var_B0], r12d
0x18003c2b0  mov     [rbp+4Fh+var_AC], r12d
0x18003c2b4  mov     [rbp+4Fh+var_A8], r12d
0x18003c2b8  mov     [rbp+4Fh+arg_0], r12d
0x18003c2bc  mov     [rbp+4Fh+var_80], r12
0x18003c2c0  mov     [rbp+4Fh+var_88], r12d
0x18003c2c4  mov     esi, r12d
0x18003c2c7  mov     [rbp+4Fh+Info], r12
0x18003c2cb  mov     [rbp+4Fh+var_98], r12
0x18003c2cf  lea     rdi, [rcx+8]
0x18003c2d3  mov     rax, [rdi]
0x18003c2d6  lea     rcx, [rbp+4Fh+String2]
0x18003c2da  mov     qword ptr [rsp+130h+dwStartType], rcx
0x18003c2df  mov     qword ptr [rsp+130h+dwServiceType], r12
0x18003c2e4  xor     r9d, r9d
0x18003c2e7  lea     r8, [rbp+4Fh+var_B0]
0x18003c2eb  lea     r15d, [r12+6]
0x18003c2f0  mov     edx, r15d
0x18003c2f3  mov     rcx, rdi
0x18003c2f6  mov     rax, [rax+98h]
0x18003c2fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c302  mov     ebx, eax
0x18003c304  lea     r13d, [r12+1]
0x18003c309  test    eax, eax
0x18003c30b  js      loc_18003CA63
0x18003c311  mov     rax, [rdi]
0x18003c314  lea     rcx, [rbp+4Fh+var_90]
0x18003c318  mov     qword ptr [rsp+130h+dwStartType], rcx
0x18003c31d  mov     qword ptr [rsp+130h+dwServiceType], r12
0x18003c322  xor     r9d, r9d
0x18003c325  lea     r8, [rbp+4Fh+var_AC]
0x18003c329  lea     edx, [r12+5]
0x18003c32e  mov     rcx, rdi
0x18003c331  mov     rax, [rax+98h]
0x18003c338  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c33d  mov     ebx, eax
0x18003c33f  test    eax, eax
0x18003c341  js      loc_18003CA63
0x18003c347  mov     rax, [rdi]
0x18003c34a  lea     rcx, [rbp+4Fh+lpDisplayName]
0x18003c34e  mov     qword ptr [rsp+130h+dwStartType], rcx
0x18003c353  mov     qword ptr [rsp+130h+dwServiceType], r12
0x18003c358  xor     r9d, r9d
0x18003c35b  lea     r8, [rbp+4Fh+var_A8]
0x18003c35f  mov     edx, r13d
0x18003c362  mov     rcx, rdi
0x18003c365  mov     rax, [rax+98h]
0x18003c36c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c371  mov     ebx, eax
0x18003c373  test    eax, eax
0x18003c375  js      loc_18003CA63
0x18003c37b  mov     rax, [rdi]
0x18003c37e  lea     rcx, [rbp+4Fh+var_70]
0x18003c382  mov     qword ptr [rsp+130h+dwStartType], rcx
0x18003c387  mov     qword ptr [rsp+130h+dwServiceType], r12
0x18003c38c  xor     r9d, r9d
0x18003c38f  lea     r8, [rbp+4Fh+arg_0]
0x18003c393  lea     edx, [r12+0Ah]
0x18003c398  mov     rcx, rdi
0x18003c39b  mov     rax, [rax+98h]
0x18003c3a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c3a7  mov     ebx, eax
0x18003c3a9  test    eax, eax
0x18003c3ab  js      loc_18003CA63
0x18003c3b1  mov     rax, [rdi]
0x18003c3b4  lea     rcx, [rbp+4Fh+var_68]
0x18003c3b8  mov     qword ptr [rsp+130h+dwStartType], rcx
0x18003c3bd  mov     qword ptr [rsp+130h+dwServiceType], r12
0x18003c3c2  xor     r9d, r9d
0x18003c3c5  lea     r8, [rbp+4Fh+var_88]
0x18003c3c9  lea     edx, [r12+10h]
0x18003c3ce  mov     rcx, rdi
0x18003c3d1  mov     rax, [rax+98h]
0x18003c3d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c3dd  mov     ebx, eax
0x18003c3df  test    eax, eax
0x18003c3e1  js      loc_18003CA63
0x18003c3e7  mov     rax, [rdi]
0x18003c3ea  lea     rcx, [rbp+4Fh+var_80]
0x18003c3ee  mov     qword ptr [rsp+130h+dwStartType], rcx
0x18003c3f3  mov     qword ptr [rsp+130h+dwServiceType], r12
0x18003c3f8  xor     r9d, r9d
0x18003c3fb  xor     r8d, r8d
0x18003c3fe  xor     edx, edx
0x18003c400  mov     rcx, rdi
0x18003c403  mov     rax, [rax+98h]
0x18003c40a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c40f  mov     ebx, eax
0x18003c411  test    eax, eax
0x18003c413  js      loc_18003CA63
0x18003c419  mov     rcx, [rbp+4Fh+var_80]
0x18003c41d  mov     rax, [rcx]
0x18003c420  sub     rax, qword ptr cs:CLSID_SystemApplication.Data1
0x18003c427  jnz     short loc_18003C434
0x18003c429  mov     rax, [rcx+8]
0x18003c42d  sub     rax, qword ptr cs:CLSID_SystemApplication.Data4
0x18003c434  test    rax, rax
0x18003c437  jz      loc_18003CA63
0x18003c43d  mov     [rbp+4Fh+var_90], r12
0x18003c441  mov     esi, r13d
0x18003c444  mov     dword ptr [rbp+4Fh+arg_10], r13d
0x18003c448  mov     rax, [rbp+4Fh+String2]
0x18003c44c  test    rax, rax
0x18003c44f  jz      short loc_18003C4BA
0x18003c451  cmp     [rax], r12w
0x18003c455  jnz     short loc_18003C4BA
0x18003c457  mov     [rbp+4Fh+String2], r12
0x18003c45b  lea     rcx, [r14+18h]
0x18003c45f  mov     rax, [rcx]
0x18003c462  mov     rax, [rax+50h]
0x18003c466  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c46b  mov     ebx, eax
0x18003c46d  test    eax, eax
0x18003c46f  js      loc_18003CA63
0x18003c475  mov     rax, [rdi]
0x18003c478  xor     r9d, r9d
0x18003c47b  xor     r8d, r8d
0x18003c47e  mov     edx, r15d
0x18003c481  mov     rcx, rdi
0x18003c484  mov     rax, [rax+0A0h]
0x18003c48b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c490  mov     ebx, eax
0x18003c492  test    eax, eax
0x18003c494  js      loc_18003CA63
0x18003c49a  mov     rax, [rdi]
0x18003c49d  mov     rcx, rdi
0x18003c4a0  mov     rax, [rax+90h]
0x18003c4a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c4ac  mov     ebx, eax
0x18003c4ae  test    eax, eax
0x18003c4b0  js      loc_18003CA63
0x18003c4b6  mov     rcx, [rbp+4Fh+var_80]
0x18003c4ba  and     [rbp+4Fh+var_B0], 2
0x18003c4be  and     [rbp+4Fh+var_AC], 2
0x18003c4c2  and     [rbp+4Fh+var_A8], 2
0x18003c4c6  and     [rbp+4Fh+arg_0], 2
0x18003c4ca  mov     [rbp+4Fh+var_60], rcx
0x18003c4ce  mov     [rbp+4Fh+var_58], r12
0x18003c4d2  mov     [rbp+4Fh+var_50], 48h ; 'H'
0x18003c4d9  mov     [rbp+4Fh+var_4C], 10h
0x18003c4e0  lea     rdx, [rbp+4Fh+Info]; struct ISimpleTableDispenser **
0x18003c4e4  mov     rcx, r14; this
0x18003c4e7  call    ?GetDispenser@CLTApp@@AEAAJPEAPEAUISimpleTableDispenser@@@Z; CLTApp::GetDispenser(ISimpleTableDispenser * *)
0x18003c4ec  mov     ebx, eax
0x18003c4ee  mov     r13, [rbp+4Fh+Info]
0x18003c4f2  test    eax, eax
0x18003c4f4  js      loc_18003CA48
0x18003c4fa  mov     rax, [r13+0]
0x18003c4fe  lea     rcx, [rbp+4Fh+var_98]
0x18003c502  mov     [rsp+130h+lpBinaryPathName], rcx
0x18003c507  mov     [rsp+130h+dwErrorControl], 20001h
0x18003c50f  mov     rdx, rsi
0x18003c512  mov     [rsp+130h+dwStartType], edx
0x18003c516  mov     qword ptr [rsp+130h+dwServiceType], rdx
0x18003c51b  lea     r9, [rbp+4Fh+var_60]
0x18003c51f  lea     r8, TID_APPLICATION
0x18003c526  lea     rdx, didCOMSERVICES
0x18003c52d  mov     rcx, r13
0x18003c530  mov     rax, [rax+18h]
0x18003c534  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c539  mov     ebx, eax
0x18003c53b  test    eax, eax
0x18003c53d  js      loc_18003CA48
0x18003c543  mov     rcx, [rbp+4Fh+var_98]
0x18003c547  mov     rax, [rcx]
0x18003c54a  mov     rax, [rax+18h]
0x18003c54e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c553  mov     ebx, eax
0x18003c555  test    eax, eax
0x18003c557  js      loc_18003CA48
0x18003c55d  mov     rcx, [rbp+4Fh+var_98]
0x18003c561  mov     rax, [rcx]
0x18003c564  mov     rax, [rax+28h]
0x18003c568  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c56d  mov     ebx, eax
0x18003c56f  mov     ecx, 80000000h
0x18003c574  add     eax, ecx
0x18003c576  mov     edx, 80110801h
0x18003c57b  test    ecx, eax
0x18003c57d  jnz     short loc_18003C587
0x18003c57f  cmp     ebx, edx
0x18003c581  jnz     loc_18003CA48
0x18003c587  mov     r15d, r12d
0x18003c58a  mov     esi, [rbp+4Fh+arg_20]
0x18003c58d  cmp     [rbp+4Fh+var_B0], r12d
0x18003c591  jnz     loc_18003C699
0x18003c597  cmp     esi, 3
0x18003c59a  jz      loc_18003C699
0x18003c5a0  test    ebx, ebx
0x18003c5a2  js      loc_18003C673
0x18003c5a8  mov     rcx, [rbp+4Fh+var_98]
0x18003c5ac  mov     rax, [rcx]
0x18003c5af  lea     rdx, [rbp+4Fh+String1]
0x18003c5b3  mov     qword ptr [rsp+130h+dwServiceType], rdx
0x18003c5b8  xor     r9d, r9d
0x18003c5bb  xor     r8d, r8d
0x18003c5be  lea     esi, [r9+6]
0x18003c5c2  mov     edx, esi
0x18003c5c4  mov     rax, [rax+40h]
0x18003c5c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c5cd  mov     ebx, eax
0x18003c5cf  test    eax, eax
0x18003c5d1  js      loc_18003CA45
0x18003c5d7  mov     rcx, [rbp+4Fh+String1]; String1
0x18003c5db  mov     rax, [rbp+4Fh+String2]
0x18003c5df  test    rcx, rcx
0x18003c5e2  jz      short loc_18003C5EB
0x18003c5e4  test    rax, rax
0x18003c5e7  jz      short loc_18003C60B
0x18003c5e9  jmp     short loc_18003C5F9
0x18003c5eb  test    rax, rax
0x18003c5ee  jnz     short loc_18003C60B
0x18003c5f0  test    rcx, rcx
0x18003c5f3  jz      loc_18003C67B
0x18003c5f9  test    rax, rax
0x18003c5fc  jz      short loc_18003C67B
0x18003c5fe  mov     rdx, rax; String2
0x18003c601  call    cs:__imp__wcsicmp
0x18003c607  test    eax, eax
0x18003c609  jz      short loc_18003C673
0x18003c60b  lea     rcx, [r14+18h]
0x18003c60f  mov     rax, [rcx]
0x18003c612  mov     rax, [rax+50h]
0x18003c616  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c61b  mov     ebx, eax
0x18003c61d  test    eax, eax
0x18003c61f  js      loc_18003CA45
0x18003c625  mov     rax, [rdi]
0x18003c628  mov     r9, [rbp+4Fh+String1]
0x18003c62c  xor     r8d, r8d
0x18003c62f  mov     edx, esi
0x18003c631  mov     rcx, rdi
0x18003c634  mov     rax, [rax+0A0h]
0x18003c63b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c640  mov     ebx, eax
0x18003c642  test    eax, eax
0x18003c644  js      loc_18003CA45
0x18003c64a  mov     rax, [rdi]
0x18003c64d  mov     rcx, rdi
0x18003c650  mov     rax, [rax+90h]
0x18003c657  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c65c  mov     ebx, eax
0x18003c65e  test    eax, eax
0x18003c660  js      loc_18003CA45
0x18003c666  mov     rcx, [rbp+4Fh+String1]
0x18003c66a  mov     rax, rcx
0x18003c66d  mov     [rbp+4Fh+String2], rcx
0x18003c671  jmp     short loc_18003C67B
0x18003c673  mov     rax, [rbp+4Fh+String2]
0x18003c677  mov     rcx, [rbp+4Fh+String1]
0x18003c67b  xor     ebx, ebx
0x18003c67d  mov     edi, 1
0x18003c682  mov     rdx, [rbp+4Fh+var_68]; String2
0x18003c686  test    rdx, rdx
0x18003c689  jnz     loc_18003C729
0x18003c68f  mov     ebx, 8000FFFFh
0x18003c694  jmp     loc_18003CA45
0x18003c699  cmp     ebx, edx
0x18003c69b  jnz     short loc_18003C6B5
0x18003c69d  mov     rax, [rbp+4Fh+String2]
0x18003c6a1  cmp     esi, 3
0x18003c6a4  jz      short loc_18003C6AD
0x18003c6a6  test    rax, rax
0x18003c6a9  setnz   r15b
0x18003c6ad  xor     ebx, ebx
0x18003c6af  mov     rcx, [rbp+4Fh+String1]
0x18003c6b3  jmp     short loc_18003C67D
0x18003c6b5  mov     rcx, [rbp+4Fh+var_98]
0x18003c6b9  mov     rax, [rcx]
0x18003c6bc  lea     rdx, [rbp+4Fh+String1]
0x18003c6c0  mov     qword ptr [rsp+130h+dwServiceType], rdx
0x18003c6c5  xor     r9d, r9d
0x18003c6c8  xor     r8d, r8d
0x18003c6cb  lea     edx, [r9+6]
0x18003c6cf  mov     rax, [rax+40h]
0x18003c6d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c6d8  mov     ebx, eax
0x18003c6da  test    eax, eax
  ... truncated ...
```
