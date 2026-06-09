# CoCreateLocalServerIE

- ea: `0x181066ac4`
- end: `0x181066d52`
- name: `CoCreateLocalServerIE`
- size: `654`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180b42018`
- `0x181066d58`

## callees

- `0x180839f14`
- `0x180840178`
- `0x18106679c`
- `0x181066ac4`
- `0x1810d1010`

## import_xrefs

- `USER32!AllowSetForegroundWindow` at `0x181066bc4`
- `USER32!AllowSetForegroundWindow` at `0x181066bc4`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x181066b89`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x181066b89`
- `iertutil!__imp_?LCIEUnifiedFrame@@YA_NXZ` at `0x181066b15`
- `iertutil!__imp_?LCIEUnifiedFrame@@YA_NXZ` at `0x181066b15`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x181066aec`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x181066b2f`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x181066aec`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x181066b2f`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x181066b1f`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x181066b1f`
- `msIso!__imp_?IsoGetAuthorityManager@@YAKXZ` at `0x181066b60`
- `msIso!__imp_?IsoGetAuthorityManager@@YAKXZ` at `0x181066b60`
- `msIso!__imp_?IsoGetCurrentProcessManager@@YAKXZ` at `0x181066b50`
- `msIso!__imp_?IsoGetCurrentProcessManager@@YAKXZ` at `0x181066b50`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x181066c4c`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x181066c4c`

## pseudocode

```c
__int64 __fastcall CoCreateLocalServerIE(__int64 a1, __int64 a2, unsigned __int8 a3, __int64 a4)
{
  const char *v4; // r9
  const char *v5; // r9
  unsigned int CurrentProcessManager; // ebx
  int ProcessForNav; // edi
  HRESULT v8; // ebx
  DWORD v9; // ecx
  void (__fastcall *v10)(__int64, _OWORD *); // rbx
  LPVOID v11; // rcx
  DWORD dwProcessId; // [rsp+68h] [rbp+Fh] BYREF
  LPVOID ppv; // [rsp+70h] [rbp+17h] BYREF
  __int64 v15; // [rsp+78h] [rbp+1Fh] BYREF
  struct IEUserBroker *v16; // [rsp+80h] [rbp+27h] BYREF
  _OWORD v17[2]; // [rsp+88h] [rbp+2Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B0h] [rbp+57h]

  if ( (unsigned int)IEConfiguration_GetDWORD(268435501) == 2 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xD9,
      (unsigned int)"onecoreuap\\inetcore\\lib\\nav\\iehelper.cpp",
      v4);
  ppv = 0;
  if ( !LCIEUnifiedFrame() && !IsDualEngineProcess() )
    goto LABEL_16;
  if ( (unsigned int)IEConfiguration_GetDWORD(268435501) == 2 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xCA,
      (unsigned int)"onecoreuap\\inetcore\\lib\\nav\\iehelper.cpp",
      v5);
  CurrentProcessManager = IsoGetCurrentProcessManager();
  if ( !CurrentProcessManager || CurrentProcessManager == IsoGetAuthorityManager() )
  {
LABEL_16:
    v8 = CoCreateInstance_0(&CLSID_InternetExplorer, 0, 4u, &GUID_d30c1661_cdaf_11d0_8a3e_00c04fc9e26e, &ppv);
LABEL_17:
    if ( v8 >= 0 )
      v8 = (**(__int64 (__fastcall ***)(LPVOID, __int64, __int64))ppv)(ppv, a1, a2);
    goto LABEL_19;
  }
  v15 = 0;
  ProcessForNav = GetProcessForNav();
  v16 = 0;
  v8 = CoCreateUserBroker(&v16);
  if ( v8 >= 0 )
  {
    dwProcessId = 0;
    (*(void (__fastcall **)(struct IEUserBroker *, _QWORD, _QWORD, DWORD *))(*(_QWORD *)v16 + 24LL))(
      v16,
      0,
      0,
      &dwProcessId);
    v9 = -1;
    if ( dwProcessId )
      v9 = dwProcessId;
    AllowSetForegroundWindow(v9);
    *(_QWORD *)&v17[0] = 0;
    v8 = (*(__int64 (__fastcall **)(struct IEUserBroker *, GUID *, GUID *, _OWORD *))(*(_QWORD *)v16 + 48LL))(
           v16,
           &CLSID_CShdocvwBroker,
           &IID_IUnknown,
           v17);
    if ( v8 >= 0 )
    {
      v8 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))&v17[0])(
             *(_QWORD *)&v17[0],
             &GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42,
             &v15);
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v17[0] + 16LL))(*(_QWORD *)&v17[0]);
    }
    (*(void (__fastcall **)(struct IEUserBroker *))(*(_QWORD *)v16 + 16LL))(v16);
    if ( v8 >= 0 )
    {
      v10 = *(void (__fastcall **)(__int64, _OWORD *))(*(_QWORD *)v15 + 1256LL);
      v17[0] = *(_OWORD *)GlobalThreadState();
      v10(v15, v17);
      v8 = (*(__int64 (__fastcall **)(__int64, __int64, GUID *, LPVOID *, _DWORD, int, __int64, _DWORD, int, int))(*(_QWORD *)v15 + 768LL))(
             v15,
             1,
             &GUID_d30c1661_cdaf_11d0_8a3e_00c04fc9e26e,
             &ppv,
             a3,
             ProcessForNav,
             a4,
             0,
             -1,
             -1);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      goto LABEL_17;
    }
  }
LABEL_19:
  v11 = ppv;
  if ( ppv )
  {
    if ( v8 < 0 )
    {
      (*(void (**)(void))(*(_QWORD *)ppv + 256LL))();
      v11 = ppv;
    }
    if ( v11 )
    {
      ppv = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v11 + 16LL))(v11);
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x181066ac4  mov     rax, rsp
0x181066ac7  mov     [rax+20h], r9
0x181066acb  mov     [rax+18h], r8b
0x181066acf  mov     [rax+10h], rdx
0x181066ad3  mov     [rax+8], rcx
0x181066ad7  push    rbp
0x181066ad8  push    rbx
0x181066ad9  push    rdi
0x181066ada  lea     rbp, [rax-57h]
0x181066ade  sub     rsp, 90h
0x181066ae5  mov     ebx, 1000002Dh
0x181066aea  mov     ecx, ebx
0x181066aec  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x181066af2  cmp     eax, 2
0x181066af5  jnz     short loc_181066B0D
0x181066af7  mov     rcx, [rbp+57h]; this
0x181066afb  lea     r8, aOnecoreuapInet_46; "onecoreuap\\inetcore\\lib\\nav\\iehelpe"...
0x181066b02  mov     edx, 0D9h; void *
0x181066b07  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x181066b0d  mov     [rbp+4Fh+var_38], 0
0x181066b15  call    cs:__imp_?LCIEUnifiedFrame@@YA_NXZ; LCIEUnifiedFrame(void)
0x181066b1b  test    al, al
0x181066b1d  jnz     short loc_181066B2D
0x181066b1f  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x181066b25  test    al, al
0x181066b27  jz      loc_181066CCB
0x181066b2d  mov     ecx, ebx
0x181066b2f  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x181066b35  cmp     eax, 2
0x181066b38  jnz     short loc_181066B50
0x181066b3a  mov     rcx, [rbp+57h]; this
0x181066b3e  lea     r8, aOnecoreuapInet_46; "onecoreuap\\inetcore\\lib\\nav\\iehelpe"...
0x181066b45  mov     edx, 0CAh; void *
0x181066b4a  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x181066b50  call    cs:__imp_?IsoGetCurrentProcessManager@@YAKXZ; IsoGetCurrentProcessManager(void)
0x181066b56  mov     ebx, eax
0x181066b58  test    eax, eax
0x181066b5a  jz      loc_181066CCB
0x181066b60  call    cs:__imp_?IsoGetAuthorityManager@@YAKXZ; IsoGetAuthorityManager(void)
0x181066b66  cmp     ebx, eax
0x181066b68  jz      loc_181066CCB
0x181066b6e  call    ?GetProcessForNav@@YAKXZ; GetProcessForNav(void)
0x181066b73  lea     rcx, [rbp+4Fh+var_28]
0x181066b77  mov     [rbp+4Fh+var_30], 0
0x181066b7f  mov     edi, eax
0x181066b81  mov     [rbp+4Fh+var_28], 0
0x181066b89  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x181066b8f  mov     ebx, eax
0x181066b91  test    eax, eax
0x181066b93  js      loc_181066D0C
0x181066b99  mov     rcx, [rbp+4Fh+var_28]
0x181066b9d  lea     r9, [rbp+4Fh+dwProcessId]
0x181066ba1  mov     [rbp+4Fh+dwProcessId], 0
0x181066ba8  xor     r8d, r8d
0x181066bab  mov     rdx, [rcx]
0x181066bae  mov     rax, [rdx+18h]
0x181066bb2  xor     edx, edx
0x181066bb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181066bb9  mov     eax, [rbp+4Fh+dwProcessId]
0x181066bbc  or      ecx, 0FFFFFFFFh
0x181066bbf  test    eax, eax
0x181066bc1  cmovnz  ecx, eax; dwProcessId
0x181066bc4  call    cs:__imp_AllowSetForegroundWindow
0x181066bca  mov     rcx, [rbp+4Fh+var_28]
0x181066bce  lea     r9, [rbp+4Fh+var_20]
0x181066bd2  mov     qword ptr [rbp+4Fh+var_20], 0
0x181066bda  lea     r8, IID_IUnknown
0x181066be1  lea     rdx, CLSID_CShdocvwBroker
0x181066be8  mov     rax, [rcx]
0x181066beb  mov     rax, [rax+30h]
0x181066bef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181066bf4  mov     ebx, eax
0x181066bf6  test    eax, eax
0x181066bf8  js      short loc_181066C26
0x181066bfa  mov     rcx, qword ptr [rbp+4Fh+var_20]
0x181066bfe  lea     r8, [rbp+4Fh+var_30]
0x181066c02  lea     rdx, _GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42
0x181066c09  mov     rax, [rcx]
0x181066c0c  mov     rax, [rax]
0x181066c0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181066c14  mov     rcx, qword ptr [rbp+4Fh+var_20]
0x181066c18  mov     ebx, eax
0x181066c1a  mov     rax, [rcx]
0x181066c1d  mov     rax, [rax+10h]
0x181066c21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181066c26  mov     rcx, [rbp+4Fh+var_28]
0x181066c2a  mov     rax, [rcx]
0x181066c2d  mov     rax, [rax+10h]
0x181066c31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181066c36  test    ebx, ebx
0x181066c38  js      loc_181066D0C
0x181066c3e  mov     rax, [rbp+4Fh+var_30]
0x181066c42  mov     rcx, [rax]
0x181066c45  mov     rbx, [rcx+4E8h]
0x181066c4c  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x181066c52  mov     rcx, [rbp+4Fh+var_30]
0x181066c56  lea     rdx, [rbp+4Fh+var_20]
0x181066c5a  movups  xmm0, xmmword ptr [rax]
0x181066c5d  mov     rax, rbx
0x181066c60  movdqu  [rbp+4Fh+var_20], xmm0
0x181066c65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181066c6a  mov     rcx, [rbp+4Fh+var_30]
0x181066c6e  lea     r9, [rbp+4Fh+var_38]
0x181066c72  movzx   r8d, [rbp+4Fh+arg_10]
0x181066c77  or      edx, 0FFFFFFFFh
0x181066c7a  mov     [rsp+48h], edx
0x181066c7e  mov     [rsp+0A0h+var_60], edx
0x181066c82  mov     rdx, [rbp+4Fh+arg_18]
0x181066c86  mov     rax, [rcx]
0x181066c89  mov     [rsp+0A0h+var_68], 0
0x181066c91  mov     qword ptr [rsp+0A0h+var_70], rdx
0x181066c96  mov     edx, 1
0x181066c9b  mov     dword ptr [rsp+0A0h+var_78], edi
0x181066c9f  mov     rax, [rax+300h]
0x181066ca6  mov     dword ptr [rsp+0A0h+ppv], r8d
0x181066cab  lea     r8, _GUID_d30c1661_cdaf_11d0_8a3e_00c04fc9e26e
0x181066cb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181066cb7  mov     rcx, [rbp+4Fh+var_30]
0x181066cbb  mov     ebx, eax
0x181066cbd  mov     rax, [rcx]
0x181066cc0  mov     rax, [rax+10h]
0x181066cc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181066cc9  jmp     short loc_181066CEF
0x181066ccb  xor     edx, edx; pUnkOuter
0x181066ccd  lea     rax, [rbp+4Fh+var_38]
0x181066cd1  lea     r9, _GUID_d30c1661_cdaf_11d0_8a3e_00c04fc9e26e; riid
0x181066cd8  mov     [rsp+0A0h+ppv], rax; ppv
0x181066cdd  lea     rcx, CLSID_InternetExplorer; rclsid
0x181066ce4  lea     r8d, [rdx+4]; dwClsContext
0x181066ce8  call    CoCreateInstance_0
0x181066ced  mov     ebx, eax
0x181066cef  test    ebx, ebx
0x181066cf1  js      short loc_181066D0C
0x181066cf3  mov     rcx, [rbp+4Fh+var_38]
0x181066cf7  mov     r8, [rbp+4Fh+arg_8]
0x181066cfb  mov     rdx, [rbp+4Fh+arg_0]
0x181066cff  mov     rax, [rcx]
0x181066d02  mov     rax, [rax]
0x181066d05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181066d0a  mov     ebx, eax
0x181066d0c  mov     rcx, [rbp+4Fh+var_38]
0x181066d10  test    rcx, rcx
0x181066d13  jz      short loc_181066D45
0x181066d15  test    ebx, ebx
0x181066d17  jns     short loc_181066D2C
0x181066d19  mov     rax, [rcx]
0x181066d1c  mov     rax, [rax+100h]
0x181066d23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181066d28  mov     rcx, [rbp+4Fh+var_38]
0x181066d2c  test    rcx, rcx
0x181066d2f  jz      short loc_181066D45
0x181066d31  mov     [rbp+4Fh+var_38], 0
0x181066d39  mov     rax, [rcx]
0x181066d3c  mov     rax, [rax+10h]
0x181066d40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181066d45  mov     eax, ebx
0x181066d47  add     rsp, 90h
0x181066d4e  pop     rdi
0x181066d4f  pop     rbx
0x181066d50  pop     rbp
0x181066d51  retn
```
