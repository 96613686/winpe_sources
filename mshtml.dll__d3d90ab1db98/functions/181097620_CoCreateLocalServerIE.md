# CoCreateLocalServerIE

- ea: `0x181097620`
- end: `0x1810978e5`
- name: `CoCreateLocalServerIE`
- size: `709`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180b5a774`
- `0x1810978ec`

## callees

- `0x18083ca44`
- `0x180842d84`
- `0x1810971f0`
- `0x181097620`
- `0x181104010`

## import_xrefs

- `USER32!AllowSetForegroundWindow` at `0x18109774a`
- `USER32!AllowSetForegroundWindow` at `0x18109774a`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x181097709`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x181097709`
- `iertutil!__imp_?LCIEUnifiedFrame@@YA_NXZ` at `0x181097677`
- `iertutil!__imp_?LCIEUnifiedFrame@@YA_NXZ` at `0x181097677`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x181097648`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x18109769d`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x181097648`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x18109769d`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x181097687`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x181097687`
- `msIso!__imp_?IsoGetAuthorityManager@@YAKXZ` at `0x1810976da`
- `msIso!__imp_?IsoGetAuthorityManager@@YAKXZ` at `0x1810976da`
- `msIso!__imp_?IsoGetCurrentProcessManager@@YAKXZ` at `0x1810976c4`
- `msIso!__imp_?IsoGetCurrentProcessManager@@YAKXZ` at `0x1810976c4`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1810977d8`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1810977d8`

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
0x181097620  mov     rax, rsp
0x181097623  mov     [rax+20h], r9
0x181097627  mov     [rax+18h], r8b
0x18109762b  mov     [rax+10h], rdx
0x18109762f  mov     [rax+8], rcx
0x181097633  push    rbp
0x181097634  push    rbx
0x181097635  push    rdi
0x181097636  lea     rbp, [rax-57h]
0x18109763a  sub     rsp, 90h
0x181097641  mov     ebx, 1000002Dh
0x181097646  mov     ecx, ebx
0x181097648  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x18109764f  nop     dword ptr [rax+rax+00h]
0x181097654  cmp     eax, 2
0x181097657  jnz     short loc_18109766F
0x181097659  mov     rcx, [rbp+57h]; this
0x18109765d  lea     r8, aOnecoreuapInet_46; "onecoreuap\\inetcore\\lib\\nav\\iehelpe"...
0x181097664  mov     edx, 0D9h; void *
0x181097669  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18109766f  mov     [rbp+4Fh+var_38], 0
0x181097677  call    cs:__imp_?LCIEUnifiedFrame@@YA_NXZ; LCIEUnifiedFrame(void)
0x18109767e  nop     dword ptr [rax+rax+00h]
0x181097683  test    al, al
0x181097685  jnz     short loc_18109769B
0x181097687  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x18109768e  nop     dword ptr [rax+rax+00h]
0x181097693  test    al, al
0x181097695  jz      loc_18109785D
0x18109769b  mov     ecx, ebx
0x18109769d  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x1810976a4  nop     dword ptr [rax+rax+00h]
0x1810976a9  cmp     eax, 2
0x1810976ac  jnz     short loc_1810976C4
0x1810976ae  mov     rcx, [rbp+57h]; this
0x1810976b2  lea     r8, aOnecoreuapInet_46; "onecoreuap\\inetcore\\lib\\nav\\iehelpe"...
0x1810976b9  mov     edx, 0CAh; void *
0x1810976be  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1810976c4  call    cs:__imp_?IsoGetCurrentProcessManager@@YAKXZ; IsoGetCurrentProcessManager(void)
0x1810976cb  nop     dword ptr [rax+rax+00h]
0x1810976d0  mov     ebx, eax
0x1810976d2  test    eax, eax
0x1810976d4  jz      loc_18109785D
0x1810976da  call    cs:__imp_?IsoGetAuthorityManager@@YAKXZ; IsoGetAuthorityManager(void)
0x1810976e1  nop     dword ptr [rax+rax+00h]
0x1810976e6  cmp     ebx, eax
0x1810976e8  jz      loc_18109785D
0x1810976ee  call    ?GetProcessForNav@@YAKXZ; GetProcessForNav(void)
0x1810976f3  lea     rcx, [rbp+4Fh+var_28]
0x1810976f7  mov     [rbp+4Fh+var_30], 0
0x1810976ff  mov     edi, eax
0x181097701  mov     [rbp+4Fh+var_28], 0
0x181097709  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x181097710  nop     dword ptr [rax+rax+00h]
0x181097715  mov     ebx, eax
0x181097717  test    eax, eax
0x181097719  js      loc_18109789E
0x18109771f  mov     rcx, [rbp+4Fh+var_28]
0x181097723  lea     r9, [rbp+4Fh+dwProcessId]
0x181097727  mov     [rbp+4Fh+dwProcessId], 0
0x18109772e  xor     r8d, r8d
0x181097731  mov     rdx, [rcx]
0x181097734  mov     rax, [rdx+18h]
0x181097738  xor     edx, edx
0x18109773a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18109773f  mov     eax, [rbp+4Fh+dwProcessId]
0x181097742  or      ecx, 0FFFFFFFFh
0x181097745  test    eax, eax
0x181097747  cmovnz  ecx, eax; dwProcessId
0x18109774a  call    cs:__imp_AllowSetForegroundWindow
0x181097751  nop     dword ptr [rax+rax+00h]
0x181097756  mov     rcx, [rbp+4Fh+var_28]
0x18109775a  lea     r9, [rbp+4Fh+var_20]
0x18109775e  mov     qword ptr [rbp+4Fh+var_20], 0
0x181097766  lea     r8, IID_IUnknown
0x18109776d  lea     rdx, CLSID_CShdocvwBroker
0x181097774  mov     rax, [rcx]
0x181097777  mov     rax, [rax+30h]
0x18109777b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181097780  mov     ebx, eax
0x181097782  test    eax, eax
0x181097784  js      short loc_1810977B2
0x181097786  mov     rcx, qword ptr [rbp+4Fh+var_20]
0x18109778a  lea     r8, [rbp+4Fh+var_30]
0x18109778e  lea     rdx, _GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42
0x181097795  mov     rax, [rcx]
0x181097798  mov     rax, [rax]
0x18109779b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1810977a0  mov     rcx, qword ptr [rbp+4Fh+var_20]
0x1810977a4  mov     ebx, eax
0x1810977a6  mov     rax, [rcx]
0x1810977a9  mov     rax, [rax+10h]
0x1810977ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1810977b2  mov     rcx, [rbp+4Fh+var_28]
0x1810977b6  mov     rax, [rcx]
0x1810977b9  mov     rax, [rax+10h]
0x1810977bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1810977c2  test    ebx, ebx
0x1810977c4  js      loc_18109789E
0x1810977ca  mov     rax, [rbp+4Fh+var_30]
0x1810977ce  mov     rcx, [rax]
0x1810977d1  mov     rbx, [rcx+4E8h]
0x1810977d8  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1810977df  nop     dword ptr [rax+rax+00h]
0x1810977e4  mov     rcx, [rbp+4Fh+var_30]
0x1810977e8  lea     rdx, [rbp+4Fh+var_20]
0x1810977ec  movups  xmm0, xmmword ptr [rax]
0x1810977ef  mov     rax, rbx
0x1810977f2  movdqu  [rbp+4Fh+var_20], xmm0
0x1810977f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1810977fc  mov     rcx, [rbp+4Fh+var_30]
0x181097800  lea     r9, [rbp+4Fh+var_38]
0x181097804  movzx   r8d, [rbp+4Fh+arg_10]
0x181097809  or      edx, 0FFFFFFFFh
0x18109780c  mov     [rsp+48h], edx
0x181097810  mov     [rsp+0A0h+var_60], edx
0x181097814  mov     rdx, [rbp+4Fh+arg_18]
0x181097818  mov     rax, [rcx]
0x18109781b  mov     [rsp+0A0h+var_68], 0
0x181097823  mov     qword ptr [rsp+0A0h+var_70], rdx
0x181097828  mov     edx, 1
0x18109782d  mov     dword ptr [rsp+0A0h+var_78], edi
0x181097831  mov     rax, [rax+300h]
0x181097838  mov     dword ptr [rsp+0A0h+ppv], r8d
0x18109783d  lea     r8, _GUID_d30c1661_cdaf_11d0_8a3e_00c04fc9e26e
0x181097844  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181097849  mov     rcx, [rbp+4Fh+var_30]
0x18109784d  mov     ebx, eax
0x18109784f  mov     rax, [rcx]
0x181097852  mov     rax, [rax+10h]
0x181097856  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18109785b  jmp     short loc_181097881
0x18109785d  xor     edx, edx; pUnkOuter
0x18109785f  lea     rax, [rbp+4Fh+var_38]
0x181097863  lea     r9, _GUID_d30c1661_cdaf_11d0_8a3e_00c04fc9e26e; riid
0x18109786a  mov     [rsp+0A0h+ppv], rax; ppv
0x18109786f  lea     rcx, CLSID_InternetExplorer; rclsid
0x181097876  lea     r8d, [rdx+4]; dwClsContext
0x18109787a  call    CoCreateInstance_0
0x18109787f  mov     ebx, eax
0x181097881  test    ebx, ebx
0x181097883  js      short loc_18109789E
0x181097885  mov     rcx, [rbp+4Fh+var_38]
0x181097889  mov     r8, [rbp+4Fh+arg_8]
0x18109788d  mov     rdx, [rbp+4Fh+arg_0]
0x181097891  mov     rax, [rcx]
0x181097894  mov     rax, [rax]
0x181097897  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18109789c  mov     ebx, eax
0x18109789e  mov     rcx, [rbp+4Fh+var_38]
0x1810978a2  test    rcx, rcx
0x1810978a5  jz      short loc_1810978D7
0x1810978a7  test    ebx, ebx
0x1810978a9  jns     short loc_1810978BE
0x1810978ab  mov     rax, [rcx]
0x1810978ae  mov     rax, [rax+100h]
0x1810978b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1810978ba  mov     rcx, [rbp+4Fh+var_38]
0x1810978be  test    rcx, rcx
0x1810978c1  jz      short loc_1810978D7
0x1810978c3  mov     [rbp+4Fh+var_38], 0
0x1810978cb  mov     rax, [rcx]
0x1810978ce  mov     rax, [rax+10h]
0x1810978d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1810978d7  mov     eax, ebx
0x1810978d9  add     rsp, 90h
0x1810978e0  pop     rdi
0x1810978e1  pop     rbx
0x1810978e2  pop     rbp
0x1810978e3  retn
```
