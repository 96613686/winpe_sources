# BrokerRedirectUrlThreadProc(void *)

- ea: `0x180a3a6d0`
- end: `0x180a3a9b1`
- name: `?BrokerRedirectUrlThreadProc@@YAKPEAX@Z`
- size: `737`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x180323c94`
- `0x180773a20`
- `0x1808cf80c`
- `0x180a3a6d0`
- `0x1810f65c0`
- `0x181104010`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x180a3a7b4`
- `KERNEL32!GetCurrentProcessId` at `0x180a3a7b4`
- `USER32!AllowSetForegroundWindow` at `0x180a3a786`
- `USER32!AllowSetForegroundWindow` at `0x180a3a87b`
- `USER32!AllowSetForegroundWindow` at `0x180a3a786`
- `USER32!AllowSetForegroundWindow` at `0x180a3a87b`
- `iertutil!__imp_?CoCreateUserBrokerForThread@@YAJKPEAPEAUIEUserBroker@@@Z` at `0x180a3a841`
- `iertutil!__imp_?CoCreateUserBrokerForThread@@YAJKPEAPEAUIEUserBroker@@@Z` at `0x180a3a841`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x180a3a7e0`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x180a3a7e0`
- `api-ms-win-downlevel-ole32-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x180a3a722`
- `api-ms-win-downlevel-ole32-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x180a3a81b`
- `api-ms-win-downlevel-ole32-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x180a3a722`
- `api-ms-win-downlevel-ole32-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x180a3a81b`
- `api-ms-win-downlevel-ole32-l1-1-0!CoUninitialize` at `0x180a3a974`
- `api-ms-win-downlevel-ole32-l1-1-0!CoUninitialize` at `0x180a3a974`
- `api-ms-win-downlevel-ole32-l1-1-0!CoInitializeEx` at `0x180a3a6f9`
- `api-ms-win-downlevel-ole32-l1-1-0!CoInitializeEx` at `0x180a3a6f9`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180a3a7ef`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180a3a7ef`
- `msIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x180a3a7c6`
- `msIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x180a3a7c6`

## pseudocode

```c
__int64 __fastcall BrokerRedirectUrlThreadProc(char *Parameter)
{
  IStream *v2; // rcx
  HRESULT InterfaceAndReleaseStream; // eax
  DWORD v4; // edi
  int v5; // eax
  struct IE_GLOBAL_THREAD_STATE *v6; // rax
  IStream *v7; // rcx
  __int128 v8; // xmm0
  unsigned int v9; // ecx
  int v10; // edi
  __int64 v11; // rdx
  void *v12; // r8
  DWORD dwProcessId; // [rsp+30h] [rbp-79h] BYREF
  struct IEUserBroker *v15; // [rsp+38h] [rbp-71h] BYREF
  LPVOID ppv; // [rsp+40h] [rbp-69h] BYREF
  __int64 v17; // [rsp+48h] [rbp-61h] BYREF
  __int64 v18; // [rsp+50h] [rbp-59h] BYREF
  LPVOID v19; // [rsp+58h] [rbp-51h] BYREF
  __int128 v20; // [rsp+60h] [rbp-49h] BYREF
  __int64 v21; // [rsp+70h] [rbp-39h]
  _DWORD v22[2]; // [rsp+80h] [rbp-29h] BYREF
  __int64 v23; // [rsp+88h] [rbp-21h]
  __int64 v24; // [rsp+90h] [rbp-19h]
  __int128 v25; // [rsp+98h] [rbp-11h]
  _DWORD v26[10]; // [rsp+A8h] [rbp-1h] BYREF

  if ( CoInitializeEx(0, 2u) >= 0 )
  {
    v2 = (IStream *)*((_QWORD *)Parameter + 2);
    ppv = 0;
    InterfaceAndReleaseStream = CoGetInterfaceAndReleaseStream(v2, &GUID_00000000_0000_0000_c000_000000000046, &ppv);
    *((_QWORD *)Parameter + 2) = 0;
    if ( InterfaceAndReleaseStream >= 0 )
    {
      v21 = 0;
      v20 = 0;
      LOWORD(v20) = 11;
      WORD4(v20) = -1;
      g_pfn_IUnknown_Exec((_DWORD)ppv, (unsigned int)&CGID_DocHostCmdPriv, 15, 0, (__int64)&v20, 0);
      v4 = -1;
      AllowSetForegroundWindow(0xFFFFFFFF);
      v22[0] = *(_DWORD *)Parameter;
      v5 = *((_DWORD *)Parameter + 1);
      memset(v26, 0, 28);
      v22[1] = v5;
      v23 = 0;
      v24 = 0;
      v25 = 0;
      LODWORD(v25) = GetCurrentProcessId();
      *(_QWORD *)((char *)&v25 + 4) = IsoGetIntegrity(1) & 0x7F;
      v26[0] = IEConfiguration_GetDWORD(536870929);
      v6 = GlobalThreadState();
      v7 = (IStream *)*((_QWORD *)Parameter + 3);
      v8 = *(_OWORD *)v6;
      v19 = 0;
      *(_OWORD *)&v26[3] = v8;
      if ( v7 )
      {
        CoGetInterfaceAndReleaseStream(v7, &GUID_5a625ea4_a89f_4eb2_a45a_9ad4e37d4b00, &v19);
        *((_QWORD *)Parameter + 3) = 0;
      }
      v9 = *((_DWORD *)Parameter + 2);
      LODWORD(v24) = 1;
      v18 = 0;
      v15 = 0;
      if ( (int)CoCreateUserBrokerForThread(v9, &v15) >= 0 )
      {
        dwProcessId = 0;
        (*(void (__fastcall **)(struct IEUserBroker *, _QWORD, _QWORD, DWORD *))(*(_QWORD *)v15 + 24LL))(
          v15,
          0,
          0,
          &dwProcessId);
        if ( dwProcessId )
          v4 = dwProcessId;
        AllowSetForegroundWindow(v4);
        v17 = 0;
        v10 = (*(__int64 (__fastcall **)(struct IEUserBroker *, GUID *, GUID *, __int64 *))(*(_QWORD *)v15 + 48LL))(
                v15,
                &CLSID_CShdocvwBroker,
                &IID_IUnknown,
                &v17);
        if ( v10 >= 0 )
        {
          v10 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v17)(v17, &IID_IShdocvwBroker, &v18);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
        }
        (*(void (__fastcall **)(struct IEUserBroker *))(*(_QWORD *)v15 + 16LL))(v15);
        if ( v10 >= 0 )
        {
          (*(void (__fastcall **)(__int64, char *, _DWORD *, LPVOID))(*(_QWORD *)v18 + 40LL))(
            v18,
            Parameter + 32,
            v22,
            v19);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
        }
      }
      WORD4(v20) = 0;
      g_pfn_IUnknown_Exec((_DWORD)ppv, (unsigned int)&CGID_DocHostCmdPriv, 15, 0, (__int64)&v20, 0);
      if ( v19 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v19 + 16LL))(v19);
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    CoUninitialize();
  }
  ClearBrokerBindInfo((struct _BROKER_BIND_INFO *)(Parameter + 32));
  if ( Parameter )
    CSize::`scalar deleting destructor'((CSize *)Parameter, v11, v12);
  return 0;
}

```

## disassembly

```asm
0x180a3a6d0  push    rbp
0x180a3a6d2  push    rbx
0x180a3a6d3  push    rsi
0x180a3a6d4  push    rdi
0x180a3a6d5  lea     rbp, [rsp-3Fh]
0x180a3a6da  sub     rsp, 0E8h
0x180a3a6e1  mov     rax, cs:__security_cookie
0x180a3a6e8  xor     rax, rsp
0x180a3a6eb  mov     [rbp+57h+var_30], rax
0x180a3a6ef  mov     rbx, rcx
0x180a3a6f2  mov     edx, 2; dwCoInit
0x180a3a6f7  xor     ecx, ecx; pvReserved
0x180a3a6f9  call    cs:__imp_CoInitializeEx
0x180a3a700  nop     dword ptr [rax+rax+00h]
0x180a3a705  xor     esi, esi
0x180a3a707  test    eax, eax
0x180a3a709  js      loc_180A3A980
0x180a3a70f  mov     rcx, [rbx+10h]; pStm
0x180a3a713  lea     r8, [rbp+57h+ppv]; ppv
0x180a3a717  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; iid
0x180a3a71e  mov     [rbp+57h+ppv], rsi
0x180a3a722  call    cs:__imp_CoGetInterfaceAndReleaseStream
0x180a3a729  nop     dword ptr [rax+rax+00h]
0x180a3a72e  mov     [rbx+10h], rsi
0x180a3a732  test    eax, eax
0x180a3a734  js      loc_180A3A974
0x180a3a73a  mov     rcx, [rbp+57h+ppv]
0x180a3a73e  lea     r8d, [rsi+0Fh]
0x180a3a742  xor     eax, eax
0x180a3a744  mov     [rsp+100h+var_D8], rsi
0x180a3a749  mov     [rbp+57h+var_90], rax
0x180a3a74d  lea     rdx, CGID_DocHostCmdPriv
0x180a3a754  lea     eax, [rsi+0Bh]
0x180a3a757  xorps   xmm0, xmm0
0x180a3a75a  movups  [rbp+57h+var_A0], xmm0
0x180a3a75e  mov     word ptr [rbp+57h+var_A0], ax
0x180a3a762  xor     r9d, r9d
0x180a3a765  or      eax, 0FFFFFFFFh
0x180a3a768  mov     word ptr [rbp+57h+var_A0+8], ax
0x180a3a76c  lea     rax, [rbp+57h+var_A0]
0x180a3a770  mov     [rsp+100h+var_E0], rax
0x180a3a775  call    cs:g_pfn_IUnknown_Exec
0x180a3a77c  nop     dword ptr [rax+rax+00h]
0x180a3a781  or      edi, 0FFFFFFFFh
0x180a3a784  mov     ecx, edi; dwProcessId
0x180a3a786  call    cs:__imp_AllowSetForegroundWindow
0x180a3a78d  nop     dword ptr [rax+rax+00h]
0x180a3a792  mov     eax, [rbx]
0x180a3a794  xorps   xmm0, xmm0
0x180a3a797  mov     [rbp+57h+var_80], eax
0x180a3a79a  mov     eax, [rbx+4]
0x180a3a79d  movups  xmmword ptr [rbp+57h+var_58], xmm0
0x180a3a7a1  mov     [rbp+57h+var_7C], eax
0x180a3a7a4  movups  xmmword ptr [rbp+57h+var_58+0Ch], xmm0
0x180a3a7a8  mov     [rbp+57h+var_78], rsi
0x180a3a7ac  mov     [rbp+57h+var_70], rsi
0x180a3a7b0  movups  [rbp+57h+var_68], xmm0
0x180a3a7b4  call    cs:__imp_GetCurrentProcessId
0x180a3a7bb  nop     dword ptr [rax+rax+00h]
0x180a3a7c0  lea     ecx, [rsi+1]
0x180a3a7c3  mov     dword ptr [rbp+57h+var_68], eax
0x180a3a7c6  call    cs:__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z; IsoGetIntegrity(ulong)
0x180a3a7cd  nop     dword ptr [rax+rax+00h]
0x180a3a7d2  mov     ecx, 20000011h
0x180a3a7d7  mov     dword ptr [rbp+57h+var_68+8], esi
0x180a3a7da  and     eax, 7Fh
0x180a3a7dd  mov     dword ptr [rbp+57h+var_68+4], eax
0x180a3a7e0  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x180a3a7e7  nop     dword ptr [rax+rax+00h]
0x180a3a7ec  mov     [rbp+57h+var_58], eax
0x180a3a7ef  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180a3a7f6  nop     dword ptr [rax+rax+00h]
0x180a3a7fb  mov     rcx, [rbx+18h]; pStm
0x180a3a7ff  movups  xmm0, xmmword ptr [rax]
0x180a3a802  mov     [rbp+57h+var_A8], rsi
0x180a3a806  movdqu  xmmword ptr [rbp+57h+var_58+0Ch], xmm0
0x180a3a80b  test    rcx, rcx
0x180a3a80e  jz      short loc_180A3A82B
0x180a3a810  lea     r8, [rbp+57h+var_A8]; ppv
0x180a3a814  lea     rdx, _GUID_5a625ea4_a89f_4eb2_a45a_9ad4e37d4b00; iid
0x180a3a81b  call    cs:__imp_CoGetInterfaceAndReleaseStream
0x180a3a822  nop     dword ptr [rax+rax+00h]
0x180a3a827  mov     [rbx+18h], rsi
0x180a3a82b  mov     ecx, [rbx+8]
0x180a3a82e  lea     rdx, [rbp+57h+var_C8]
0x180a3a832  mov     dword ptr [rbp+57h+var_70], 1
0x180a3a839  mov     [rbp+57h+var_B0], rsi
0x180a3a83d  mov     [rbp+57h+var_C8], rsi
0x180a3a841  call    cs:__imp_?CoCreateUserBrokerForThread@@YAJKPEAPEAUIEUserBroker@@@Z; CoCreateUserBrokerForThread(ulong,IEUserBroker * *)
0x180a3a848  nop     dword ptr [rax+rax+00h]
0x180a3a84d  test    eax, eax
0x180a3a84f  js      loc_180A3A91F
0x180a3a855  mov     rcx, [rbp+57h+var_C8]
0x180a3a859  lea     r9, [rbp+57h+dwProcessId]
0x180a3a85d  mov     [rbp+57h+dwProcessId], esi
0x180a3a860  xor     r8d, r8d
0x180a3a863  xor     edx, edx
0x180a3a865  mov     rax, [rcx]
0x180a3a868  mov     rax, [rax+18h]
0x180a3a86c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180a3a871  mov     eax, [rbp+57h+dwProcessId]
0x180a3a874  test    eax, eax
0x180a3a876  cmovnz  edi, eax
0x180a3a879  mov     ecx, edi; dwProcessId
0x180a3a87b  call    cs:__imp_AllowSetForegroundWindow
0x180a3a882  nop     dword ptr [rax+rax+00h]
0x180a3a887  mov     rcx, [rbp+57h+var_C8]
0x180a3a88b  lea     r9, [rbp+57h+var_B8]
0x180a3a88f  mov     [rbp+57h+var_B8], rsi
0x180a3a893  lea     r8, IID_IUnknown
0x180a3a89a  lea     rdx, CLSID_CShdocvwBroker
0x180a3a8a1  mov     rax, [rcx]
0x180a3a8a4  mov     rax, [rax+30h]
0x180a3a8a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180a3a8ad  mov     edi, eax
0x180a3a8af  test    eax, eax
0x180a3a8b1  js      short loc_180A3A8DF
0x180a3a8b3  mov     rcx, [rbp+57h+var_B8]
0x180a3a8b7  lea     r8, [rbp+57h+var_B0]
0x180a3a8bb  lea     rdx, IID_IShdocvwBroker
0x180a3a8c2  mov     rax, [rcx]
0x180a3a8c5  mov     rax, [rax]
0x180a3a8c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180a3a8cd  mov     rcx, [rbp+57h+var_B8]
0x180a3a8d1  mov     edi, eax
0x180a3a8d3  mov     rax, [rcx]
0x180a3a8d6  mov     rax, [rax+10h]
0x180a3a8da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180a3a8df  mov     rcx, [rbp+57h+var_C8]
0x180a3a8e3  mov     rax, [rcx]
0x180a3a8e6  mov     rax, [rax+10h]
0x180a3a8ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180a3a8ef  test    edi, edi
0x180a3a8f1  js      short loc_180A3A91F
0x180a3a8f3  mov     rcx, [rbp+57h+var_B0]
0x180a3a8f7  lea     rdx, [rbx+20h]
0x180a3a8fb  mov     r9, [rbp+57h+var_A8]
0x180a3a8ff  lea     r8, [rbp+57h+var_80]
0x180a3a903  mov     rax, [rcx]
0x180a3a906  mov     rax, [rax+28h]
0x180a3a90a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180a3a90f  mov     rcx, [rbp+57h+var_B0]
0x180a3a913  mov     rax, [rcx]
0x180a3a916  mov     rax, [rax+10h]
0x180a3a91a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180a3a91f  mov     rcx, [rbp+57h+ppv]
0x180a3a923  lea     rax, [rbp+57h+var_A0]
0x180a3a927  xor     r9d, r9d
0x180a3a92a  mov     [rsp+100h+var_D8], rsi
0x180a3a92f  lea     rdx, CGID_DocHostCmdPriv
0x180a3a936  mov     word ptr [rbp+57h+var_A0+8], si
0x180a3a93a  mov     [rsp+100h+var_E0], rax
0x180a3a93f  lea     r8d, [r9+0Fh]
0x180a3a943  call    cs:g_pfn_IUnknown_Exec
0x180a3a94a  nop     dword ptr [rax+rax+00h]
0x180a3a94f  mov     rcx, [rbp+57h+var_A8]
0x180a3a953  test    rcx, rcx
0x180a3a956  jz      short loc_180A3A964
0x180a3a958  mov     rax, [rcx]
0x180a3a95b  mov     rax, [rax+10h]
0x180a3a95f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180a3a964  mov     rcx, [rbp+57h+ppv]
0x180a3a968  mov     rax, [rcx]
0x180a3a96b  mov     rax, [rax+10h]
0x180a3a96f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180a3a974  call    cs:__imp_CoUninitialize
0x180a3a97b  nop     dword ptr [rax+rax+00h]
0x180a3a980  lea     rcx, [rbx+20h]; struct _BROKER_BIND_INFO *
0x180a3a984  call    ?ClearBrokerBindInfo@@YAXPEAU_BROKER_BIND_INFO@@@Z; ClearBrokerBindInfo(_BROKER_BIND_INFO *)
0x180a3a989  test    rbx, rbx
0x180a3a98c  jz      short loc_180A3A996
0x180a3a98e  mov     rcx, rbx; this
0x180a3a991  call    ??_GCSize@@QEAAPEAXI@Z; CSize::`scalar deleting destructor'(uint)
0x180a3a996  xor     eax, eax
0x180a3a998  mov     rcx, [rbp+57h+var_30]
0x180a3a99c  xor     rcx, rsp; StackCookie
0x180a3a99f  call    __security_check_cookie
0x180a3a9a4  add     rsp, 0E8h
0x180a3a9ab  pop     rdi
0x180a3a9ac  pop     rsi
0x180a3a9ad  pop     rbx
0x180a3a9ae  pop     rbp
0x180a3a9af  retn
```
