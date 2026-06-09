# BrokerRedirectUrlThreadProc(void *)

- ea: `0x180a278e0`
- end: `0x180a27b72`
- name: `?BrokerRedirectUrlThreadProc@@YAKPEAX@Z`
- size: `658`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x1802910dc`
- `0x18076a3f0`
- `0x1808c5f50`
- `0x180a278e0`
- `0x1810c2d60`
- `0x1810d1010`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x180a279ac`
- `KERNEL32!GetCurrentProcessId` at `0x180a279ac`
- `USER32!AllowSetForegroundWindow` at `0x180a27984`
- `USER32!AllowSetForegroundWindow` at `0x180a27a4f`
- `USER32!AllowSetForegroundWindow` at `0x180a27984`
- `USER32!AllowSetForegroundWindow` at `0x180a27a4f`
- `iertutil!__imp_?CoCreateUserBrokerForThread@@YAJKPEAPEAUIEUserBroker@@@Z` at `0x180a27a1b`
- `iertutil!__imp_?CoCreateUserBrokerForThread@@YAJKPEAPEAUIEUserBroker@@@Z` at `0x180a27a1b`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x180a279cc`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x180a279cc`
- `api-ms-win-downlevel-ole32-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x180a2792c`
- `api-ms-win-downlevel-ole32-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x180a279fb`
- `api-ms-win-downlevel-ole32-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x180a2792c`
- `api-ms-win-downlevel-ole32-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x180a279fb`
- `api-ms-win-downlevel-ole32-l1-1-0!CoUninitialize` at `0x180a27b3c`
- `api-ms-win-downlevel-ole32-l1-1-0!CoUninitialize` at `0x180a27b3c`
- `api-ms-win-downlevel-ole32-l1-1-0!CoInitializeEx` at `0x180a27909`
- `api-ms-win-downlevel-ole32-l1-1-0!CoInitializeEx` at `0x180a27909`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180a279d5`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180a279d5`
- `msIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x180a279b8`
- `msIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x180a279b8`

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
  unsigned int v11; // edx
  DWORD dwProcessId; // [rsp+30h] [rbp-79h] BYREF
  struct IEUserBroker *v14; // [rsp+38h] [rbp-71h] BYREF
  LPVOID ppv; // [rsp+40h] [rbp-69h] BYREF
  __int64 v16; // [rsp+48h] [rbp-61h] BYREF
  __int64 v17; // [rsp+50h] [rbp-59h] BYREF
  LPVOID v18; // [rsp+58h] [rbp-51h] BYREF
  __int128 v19; // [rsp+60h] [rbp-49h] BYREF
  __int64 v20; // [rsp+70h] [rbp-39h]
  _DWORD v21[2]; // [rsp+80h] [rbp-29h] BYREF
  __int64 v22; // [rsp+88h] [rbp-21h]
  __int64 v23; // [rsp+90h] [rbp-19h]
  __int128 v24; // [rsp+98h] [rbp-11h]
  _DWORD v25[10]; // [rsp+A8h] [rbp-1h] BYREF

  if ( CoInitializeEx(0, 2u) >= 0 )
  {
    v2 = (IStream *)*((_QWORD *)Parameter + 2);
    ppv = 0;
    InterfaceAndReleaseStream = CoGetInterfaceAndReleaseStream(v2, &GUID_00000000_0000_0000_c000_000000000046, &ppv);
    *((_QWORD *)Parameter + 2) = 0;
    if ( InterfaceAndReleaseStream >= 0 )
    {
      v20 = 0;
      v19 = 0;
      LOWORD(v19) = 11;
      WORD4(v19) = -1;
      g_pfn_IUnknown_Exec((_DWORD)ppv, (unsigned int)&CGID_DocHostCmdPriv, 15, 0, (__int64)&v19, 0);
      v4 = -1;
      AllowSetForegroundWindow(0xFFFFFFFF);
      v21[0] = *(_DWORD *)Parameter;
      v5 = *((_DWORD *)Parameter + 1);
      memset(v25, 0, 28);
      v21[1] = v5;
      v22 = 0;
      v23 = 0;
      v24 = 0;
      LODWORD(v24) = GetCurrentProcessId();
      *(_QWORD *)((char *)&v24 + 4) = IsoGetIntegrity(1) & 0x7F;
      v25[0] = IEConfiguration_GetDWORD(536870929);
      v6 = GlobalThreadState();
      v7 = (IStream *)*((_QWORD *)Parameter + 3);
      v8 = *(_OWORD *)v6;
      v18 = 0;
      *(_OWORD *)&v25[3] = v8;
      if ( v7 )
      {
        CoGetInterfaceAndReleaseStream(v7, &GUID_5a625ea4_a89f_4eb2_a45a_9ad4e37d4b00, &v18);
        *((_QWORD *)Parameter + 3) = 0;
      }
      v9 = *((_DWORD *)Parameter + 2);
      LODWORD(v23) = 1;
      v17 = 0;
      v14 = 0;
      if ( (int)CoCreateUserBrokerForThread(v9, &v14) >= 0 )
      {
        dwProcessId = 0;
        (*(void (__fastcall **)(struct IEUserBroker *, _QWORD, _QWORD, DWORD *))(*(_QWORD *)v14 + 24LL))(
          v14,
          0,
          0,
          &dwProcessId);
        if ( dwProcessId )
          v4 = dwProcessId;
        AllowSetForegroundWindow(v4);
        v16 = 0;
        v10 = (*(__int64 (__fastcall **)(struct IEUserBroker *, GUID *, GUID *, __int64 *))(*(_QWORD *)v14 + 48LL))(
                v14,
                &CLSID_CShdocvwBroker,
                &IID_IUnknown,
                &v16);
        if ( v10 >= 0 )
        {
          v10 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v16)(v16, &IID_IShdocvwBroker, &v17);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
        }
        (*(void (__fastcall **)(struct IEUserBroker *))(*(_QWORD *)v14 + 16LL))(v14);
        if ( v10 >= 0 )
        {
          (*(void (__fastcall **)(__int64, char *, _DWORD *, LPVOID))(*(_QWORD *)v17 + 40LL))(
            v17,
            Parameter + 32,
            v21,
            v18);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
        }
      }
      WORD4(v19) = 0;
      g_pfn_IUnknown_Exec((_DWORD)ppv, (unsigned int)&CGID_DocHostCmdPriv, 15, 0, (__int64)&v19, 0);
      if ( v18 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v18 + 16LL))(v18);
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    CoUninitialize();
  }
  ClearBrokerBindInfo((struct _BROKER_BIND_INFO *)(Parameter + 32));
  if ( Parameter )
    CSize::`scalar deleting destructor'((CSize *)Parameter, v11);
  return 0;
}

```

## disassembly

```asm
0x180a278e0  push    rbp
0x180a278e2  push    rbx
0x180a278e3  push    rsi
0x180a278e4  push    rdi
0x180a278e5  lea     rbp, [rsp-3Fh]
0x180a278ea  sub     rsp, 0E8h
0x180a278f1  mov     rax, cs:__security_cookie
0x180a278f8  xor     rax, rsp
0x180a278fb  mov     [rbp+57h+var_30], rax
0x180a278ff  mov     rbx, rcx
0x180a27902  mov     edx, 2; dwCoInit
0x180a27907  xor     ecx, ecx; pvReserved
0x180a27909  call    cs:__imp_CoInitializeEx
0x180a2790f  xor     esi, esi
0x180a27911  test    eax, eax
0x180a27913  js      loc_180A27B42
0x180a27919  mov     rcx, [rbx+10h]; pStm
0x180a2791d  lea     r8, [rbp+57h+ppv]; ppv
0x180a27921  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; iid
0x180a27928  mov     [rbp+57h+ppv], rsi
0x180a2792c  call    cs:__imp_CoGetInterfaceAndReleaseStream
0x180a27932  mov     [rbx+10h], rsi
0x180a27936  test    eax, eax
0x180a27938  js      loc_180A27B3C
0x180a2793e  mov     rcx, [rbp+57h+ppv]
0x180a27942  lea     r8d, [rsi+0Fh]
0x180a27946  xor     eax, eax
0x180a27948  mov     [rsp+100h+var_D8], rsi
0x180a2794d  mov     [rbp+57h+var_90], rax
0x180a27951  lea     rdx, CGID_DocHostCmdPriv
0x180a27958  lea     eax, [rsi+0Bh]
0x180a2795b  xorps   xmm0, xmm0
0x180a2795e  movups  [rbp+57h+var_A0], xmm0
0x180a27962  mov     word ptr [rbp+57h+var_A0], ax
0x180a27966  xor     r9d, r9d
0x180a27969  or      eax, 0FFFFFFFFh
0x180a2796c  mov     word ptr [rbp+57h+var_A0+8], ax
0x180a27970  lea     rax, [rbp+57h+var_A0]
0x180a27974  mov     [rsp+100h+var_E0], rax
0x180a27979  call    cs:g_pfn_IUnknown_Exec
0x180a2797f  or      edi, 0FFFFFFFFh
0x180a27982  mov     ecx, edi; dwProcessId
0x180a27984  call    cs:__imp_AllowSetForegroundWindow
0x180a2798a  mov     eax, [rbx]
0x180a2798c  xorps   xmm0, xmm0
0x180a2798f  mov     [rbp+57h+var_80], eax
0x180a27992  mov     eax, [rbx+4]
0x180a27995  movups  xmmword ptr [rbp+57h+var_58], xmm0
0x180a27999  mov     [rbp+57h+var_7C], eax
0x180a2799c  movups  xmmword ptr [rbp+57h+var_58+0Ch], xmm0
0x180a279a0  mov     [rbp+57h+var_78], rsi
0x180a279a4  mov     [rbp+57h+var_70], rsi
0x180a279a8  movups  [rbp+57h+var_68], xmm0
0x180a279ac  call    cs:__imp_GetCurrentProcessId
0x180a279b2  lea     ecx, [rsi+1]
0x180a279b5  mov     dword ptr [rbp+57h+var_68], eax
0x180a279b8  call    cs:__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z; IsoGetIntegrity(ulong)
0x180a279be  mov     ecx, 20000011h
0x180a279c3  mov     dword ptr [rbp+57h+var_68+8], esi
0x180a279c6  and     eax, 7Fh
0x180a279c9  mov     dword ptr [rbp+57h+var_68+4], eax
0x180a279cc  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x180a279d2  mov     [rbp+57h+var_58], eax
0x180a279d5  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180a279db  mov     rcx, [rbx+18h]; pStm
0x180a279df  movups  xmm0, xmmword ptr [rax]
0x180a279e2  mov     [rbp+57h+var_A8], rsi
0x180a279e6  movdqu  xmmword ptr [rbp+57h+var_58+0Ch], xmm0
0x180a279eb  test    rcx, rcx
0x180a279ee  jz      short loc_180A27A05
0x180a279f0  lea     r8, [rbp+57h+var_A8]; ppv
0x180a279f4  lea     rdx, _GUID_5a625ea4_a89f_4eb2_a45a_9ad4e37d4b00; iid
0x180a279fb  call    cs:__imp_CoGetInterfaceAndReleaseStream
0x180a27a01  mov     [rbx+18h], rsi
0x180a27a05  mov     ecx, [rbx+8]
0x180a27a08  lea     rdx, [rbp+57h+var_C8]
0x180a27a0c  mov     dword ptr [rbp+57h+var_70], 1
0x180a27a13  mov     [rbp+57h+var_B0], rsi
0x180a27a17  mov     [rbp+57h+var_C8], rsi
0x180a27a1b  call    cs:__imp_?CoCreateUserBrokerForThread@@YAJKPEAPEAUIEUserBroker@@@Z; CoCreateUserBrokerForThread(ulong,IEUserBroker * *)
0x180a27a21  test    eax, eax
0x180a27a23  js      loc_180A27AED
0x180a27a29  mov     rcx, [rbp+57h+var_C8]
0x180a27a2d  lea     r9, [rbp+57h+dwProcessId]
0x180a27a31  mov     [rbp+57h+dwProcessId], esi
0x180a27a34  xor     r8d, r8d
0x180a27a37  xor     edx, edx
0x180a27a39  mov     rax, [rcx]
0x180a27a3c  mov     rax, [rax+18h]
0x180a27a40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180a27a45  mov     eax, [rbp+57h+dwProcessId]
0x180a27a48  test    eax, eax
0x180a27a4a  cmovnz  edi, eax
0x180a27a4d  mov     ecx, edi; dwProcessId
0x180a27a4f  call    cs:__imp_AllowSetForegroundWindow
0x180a27a55  mov     rcx, [rbp+57h+var_C8]
0x180a27a59  lea     r9, [rbp+57h+var_B8]
0x180a27a5d  mov     [rbp+57h+var_B8], rsi
0x180a27a61  lea     r8, IID_IUnknown
0x180a27a68  lea     rdx, CLSID_CShdocvwBroker
0x180a27a6f  mov     rax, [rcx]
0x180a27a72  mov     rax, [rax+30h]
0x180a27a76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180a27a7b  mov     edi, eax
0x180a27a7d  test    eax, eax
0x180a27a7f  js      short loc_180A27AAD
0x180a27a81  mov     rcx, [rbp+57h+var_B8]
0x180a27a85  lea     r8, [rbp+57h+var_B0]
0x180a27a89  lea     rdx, IID_IShdocvwBroker
0x180a27a90  mov     rax, [rcx]
0x180a27a93  mov     rax, [rax]
0x180a27a96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180a27a9b  mov     rcx, [rbp+57h+var_B8]
0x180a27a9f  mov     edi, eax
0x180a27aa1  mov     rax, [rcx]
0x180a27aa4  mov     rax, [rax+10h]
0x180a27aa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180a27aad  mov     rcx, [rbp+57h+var_C8]
0x180a27ab1  mov     rax, [rcx]
0x180a27ab4  mov     rax, [rax+10h]
0x180a27ab8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180a27abd  test    edi, edi
0x180a27abf  js      short loc_180A27AED
0x180a27ac1  mov     rcx, [rbp+57h+var_B0]
0x180a27ac5  lea     rdx, [rbx+20h]
0x180a27ac9  mov     r9, [rbp+57h+var_A8]
0x180a27acd  lea     r8, [rbp+57h+var_80]
0x180a27ad1  mov     rax, [rcx]
0x180a27ad4  mov     rax, [rax+28h]
0x180a27ad8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180a27add  mov     rcx, [rbp+57h+var_B0]
0x180a27ae1  mov     rax, [rcx]
0x180a27ae4  mov     rax, [rax+10h]
0x180a27ae8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180a27aed  mov     rcx, [rbp+57h+ppv]
0x180a27af1  lea     rax, [rbp+57h+var_A0]
0x180a27af5  xor     r9d, r9d
0x180a27af8  mov     [rsp+100h+var_D8], rsi
0x180a27afd  lea     rdx, CGID_DocHostCmdPriv
0x180a27b04  mov     word ptr [rbp+57h+var_A0+8], si
0x180a27b08  mov     [rsp+100h+var_E0], rax
0x180a27b0d  lea     r8d, [r9+0Fh]
0x180a27b11  call    cs:g_pfn_IUnknown_Exec
0x180a27b17  mov     rcx, [rbp+57h+var_A8]
0x180a27b1b  test    rcx, rcx
0x180a27b1e  jz      short loc_180A27B2C
0x180a27b20  mov     rax, [rcx]
0x180a27b23  mov     rax, [rax+10h]
0x180a27b27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180a27b2c  mov     rcx, [rbp+57h+ppv]
0x180a27b30  mov     rax, [rcx]
0x180a27b33  mov     rax, [rax+10h]
0x180a27b37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180a27b3c  call    cs:__imp_CoUninitialize
0x180a27b42  lea     rcx, [rbx+20h]; struct _BROKER_BIND_INFO *
0x180a27b46  call    ?ClearBrokerBindInfo@@YAXPEAU_BROKER_BIND_INFO@@@Z; ClearBrokerBindInfo(_BROKER_BIND_INFO *)
0x180a27b4b  test    rbx, rbx
0x180a27b4e  jz      short loc_180A27B58
0x180a27b50  mov     rcx, rbx; this
0x180a27b53  call    ??_GCSize@@QEAAPEAXI@Z; CSize::`scalar deleting destructor'(uint)
0x180a27b58  xor     eax, eax
0x180a27b5a  mov     rcx, [rbp+57h+var_30]
0x180a27b5e  xor     rcx, rsp; StackCookie
0x180a27b61  call    __security_check_cookie
0x180a27b66  add     rsp, 0E8h
0x180a27b6d  pop     rdi
0x180a27b6e  pop     rsi
0x180a27b6f  pop     rbx
0x180a27b70  pop     rbp
0x180a27b71  retn
```
