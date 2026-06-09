# WebRuntimeDiagnostics::LCIEDiagnosticsSession::OpenDiagnosticsTargetScope(ulong)

- ea: `0x18006915c`
- end: `0x180069324`
- name: `?OpenDiagnosticsTargetScope@LCIEDiagnosticsSession@WebRuntimeDiagnostics@@AEAAJK@Z`
- size: `456`
- prototype: `__int64 __fastcall(WebRuntimeDiagnostics::LCIEDiagnosticsSession *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800689a4`

## callees

- `0x180018b30`
- `0x18002652c`
- `0x18002b530`
- `0x18002c5b0`
- `0x180068f10`
- `0x18006915c`
- `0x18006932c`
- `0x180085010`

## import_xrefs

- `iertutil!__imp_GetUserPrivateNamespaceName` at `0x1800691cd`
- `iertutil!__imp_GetUserPrivateNamespaceName` at `0x1800691cd`
- `iertutil!__imp_?IEConfiguration_SetDWORD@@YAJW4IEConfigurationID@@K@Z` at `0x1800691a6`
- `iertutil!__imp_?IEConfiguration_SetDWORD@@YAJW4IEConfigurationID@@K@Z` at `0x1800691a6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800692a9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800692a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800692f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800692f5`
- `edgeIso!__imp_?IsoGetArtifactAddress@@YAJKW4IsoArtifactType@@PEAPEAU_IsoArtifact@@PEAK@Z` at `0x180069265`
- `edgeIso!__imp_?IsoGetArtifactAddress@@YAJKW4IsoArtifactType@@PEAPEAU_IsoArtifact@@PEAK@Z` at `0x180069265`
- `edgeIso!__imp_?IsoGetCurrentProcessManager@@YAKXZ` at `0x180069253`
- `edgeIso!__imp_?IsoGetCurrentProcessManager@@YAKXZ` at `0x180069253`
- `edgeIso!__imp_?IsoGetDefaultScope@@YAPEAUIsoScope@@XZ` at `0x18006921e`
- `edgeIso!__imp_?IsoGetDefaultScope@@YAPEAUIsoScope@@XZ` at `0x1800692d0`
- `edgeIso!__imp_?IsoGetDefaultScope@@YAPEAUIsoScope@@XZ` at `0x18006921e`
- `edgeIso!__imp_?IsoGetDefaultScope@@YAPEAUIsoScope@@XZ` at `0x1800692d0`
- `edgeIso!__imp_?IsoReferenceDefaultScope@@YAJKPEAPEAUIsoScope@@@Z` at `0x180069240`
- `edgeIso!__imp_?IsoReferenceDefaultScope@@YAJKPEAPEAUIsoScope@@@Z` at `0x180069240`
- `edgeIso!__imp_?IsoInitDefaultScope@@YAJKPEAKKPEBUSIsoScopeCreationData@@@Z` at `0x18006920e`
- `edgeIso!__imp_?IsoInitDefaultScope@@YAJKPEAKKPEBUSIsoScopeCreationData@@@Z` at `0x18006920e`

## pseudocode

```c
__int64 __fastcall WebRuntimeDiagnostics::LCIEDiagnosticsSession::OpenDiagnosticsTargetScope(
        WebRuntimeDiagnostics::LCIEDiagnosticsSession *this)
{
  WebRuntimeDiagnostics::LCIEDiagnosticsSession *v1; // rsi
  const unsigned __int16 *UserPrivateNamespaceName; // rax
  WebRuntimeDiagnostics::LCIEDiagnosticsSession *v3; // rcx
  int inited; // ebx
  struct IsoScope *DefaultScope; // rax
  unsigned int CurrentProcessManager; // eax
  HANDLE EventW; // rdi
  const char *v8; // r9
  struct IsoScope *v9; // rax
  __int64 v11; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v12; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v13[96]; // [rsp+40h] [rbp-C0h] BYREF
  struct _GUID v14; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v15[3568]; // [rsp+B0h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+ED8h] [rbp+DD8h]

  v1 = WebRuntimeDiagnostics::LCIEDiagnosticsSession::s_instance;
  v12 = WebRuntimeDiagnostics::LCIEDiagnosticsSession::s_isoProcessId;
  v14.Data1 = WebRuntimeDiagnostics::LCIEDiagnosticsSession::s_isoProcessId;
  *(_QWORD *)&v14.Data2 = 0;
  *(_DWORD *)&v14.Data4[4] = 0;
  IEConfiguration_SetDWORD(536870930, 122);
  memset_0(v13, 0, sizeof(v13));
  memset_0(v15, 0, 0xDE8u);
  UserPrivateNamespaceName = (const unsigned __int16 *)GetUserPrivateNamespaceName();
  inited = WebRuntimeDiagnostics::LCIEDiagnosticsSession::IAS_PopulateIsoCreationData(
             v3,
             &v14,
             UserPrivateNamespaceName,
             (struct SIsoScopeCreationData *)v13,
             (struct SImmutableApplicationState *)v15);
  if ( inited >= 0 )
  {
    inited = IsoInitDefaultScope(0x301u, &v12, 1u, (const struct SIsoScopeCreationData *)v13);
    if ( inited >= 0 )
    {
      DefaultScope = IsoGetDefaultScope();
      (*(void (__fastcall **)(struct IsoScope *, __int64))(*(_QWORD *)DefaultScope + 160LL))(DefaultScope, 16);
      IsoReferenceDefaultScope(1u, 0);
      *(_BYTE *)v1 = 1;
      v11 = 0;
      CurrentProcessManager = IsoGetCurrentProcessManager();
      inited = IsoGetArtifactAddress(CurrentProcessManager, 1, &v11);
      if ( inited < 0 )
        goto LABEL_7;
      *(_DWORD *)(v11 + 48) = 4;
      _IsoComponent::SetFromSHAREDMEM_64BITVALUE(
        v11,
        *(unsigned int *)(v11 + 48),
        WebRuntimeDiagnostics::LCIEDiagnosticsSession::LCIEProcessMessage);
      *(_DWORD *)(v11 + 20) &= ~0x2000000u;
      EventW = CreateEventW(0, 0, 0, 0);
      if ( !EventW )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x1AE,
          (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webruntimediagnostics\\lciediagnosticssession.cpp",
          v8);
      v9 = IsoGetDefaultScope();
      inited = (*(__int64 (__fastcall **)(struct IsoScope *, __int64, HANDLE))(*(_QWORD *)v9 + 256LL))(v9, 17, EventW);
      CloseHandle(EventW);
      if ( inited < 0 )
LABEL_7:
        WebRuntimeDiagnostics::LCIEDiagnosticsSession::UninitializeIsoSession(v1);
    }
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18006915c  push    rbp
0x18006915e  push    rbx
0x18006915f  push    rsi
0x180069160  push    rdi
0x180069161  lea     rbp, [rsp-0DB8h]
0x180069169  sub     rsp, 0EB8h
0x180069170  mov     rax, cs:__security_cookie
0x180069177  xor     rax, rsp
0x18006917a  mov     [rbp+0DD0h+var_30], rax
0x180069181  mov     eax, cs:?s_isoProcessId@LCIEDiagnosticsSession@WebRuntimeDiagnostics@@0KA; ulong WebRuntimeDiagnostics::LCIEDiagnosticsSession::s_isoProcessId
0x180069187  mov     ecx, 20000012h
0x18006918c  mov     rsi, cs:?s_instance@LCIEDiagnosticsSession@WebRuntimeDiagnostics@@0PEAV12@EA; WebRuntimeDiagnostics::LCIEDiagnosticsSession * WebRuntimeDiagnostics::LCIEDiagnosticsSession::s_instance
0x180069193  mov     [rsp+0ED0h+var_E98], eax
0x180069197  mov     [rbp+0DD0h+var_E30.Data1], eax
0x18006919a  xor     eax, eax
0x18006919c  mov     qword ptr [rbp+0DD0h+var_E30.Data2], rax
0x1800691a0  mov     dword ptr [rbp+0DD0h+var_E30.Data4+4], eax
0x1800691a3  lea     edx, [rax+7Ah]
0x1800691a6  call    cs:__imp_?IEConfiguration_SetDWORD@@YAJW4IEConfigurationID@@K@Z; IEConfiguration_SetDWORD(IEConfigurationID,ulong)
0x1800691ac  xor     edx, edx; Val
0x1800691ae  lea     rcx, [rsp+0ED0h+var_E90]; void *
0x1800691b3  lea     r8d, [rdx+60h]; Size
0x1800691b7  call    memset_0
0x1800691bc  xor     edx, edx; Val
0x1800691be  lea     rcx, [rbp+0DD0h+var_E20]; void *
0x1800691c2  mov     r8d, 0DE8h; Size
0x1800691c8  call    memset_0
0x1800691cd  call    cs:__imp_GetUserPrivateNamespaceName
0x1800691d3  mov     r8, rax; unsigned __int16 *
0x1800691d6  lea     r9, [rsp+0ED0h+var_E90]; struct SIsoScopeCreationData *
0x1800691db  lea     rax, [rbp+0DD0h+var_E20]
0x1800691df  lea     rdx, [rbp+0DD0h+var_E30]; struct _GUID *
0x1800691e3  mov     [rsp+0ED0h+var_EB0], rax; struct SImmutableApplicationState *
0x1800691e8  call    ?IAS_PopulateIsoCreationData@LCIEDiagnosticsSession@WebRuntimeDiagnostics@@AEAAJAEBU_GUID@@PEBGPEAUSIsoScopeCreationData@@PEAUSImmutableApplicationState@@@Z; WebRuntimeDiagnostics::LCIEDiagnosticsSession::IAS_PopulateIsoCreationData(_GUID const &,ushort const *,SIsoScopeCreationData *,SImmutableApplicationState *)
0x1800691ed  mov     ebx, eax
0x1800691ef  test    eax, eax
0x1800691f1  js      loc_180069307
0x1800691f7  mov     edi, 1
0x1800691fc  lea     r9, [rsp+0ED0h+var_E90]
0x180069201  mov     r8d, edi
0x180069204  lea     rdx, [rsp+0ED0h+var_E98]
0x180069209  mov     ecx, 301h
0x18006920e  call    cs:__imp_?IsoInitDefaultScope@@YAJKPEAKKPEBUSIsoScopeCreationData@@@Z; IsoInitDefaultScope(ulong,ulong *,ulong,SIsoScopeCreationData const *)
0x180069214  mov     ebx, eax
0x180069216  test    eax, eax
0x180069218  js      loc_180069307
0x18006921e  call    cs:__imp_?IsoGetDefaultScope@@YAPEAUIsoScope@@XZ; IsoGetDefaultScope(void)
0x180069224  mov     r8, rax
0x180069227  lea     edx, [rdi+0Fh]
0x18006922a  mov     rcx, [rax]
0x18006922d  mov     rax, [rcx+0A0h]
0x180069234  mov     rcx, r8
0x180069237  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006923c  xor     edx, edx
0x18006923e  mov     ecx, edi
0x180069240  call    cs:__imp_?IsoReferenceDefaultScope@@YAJKPEAPEAUIsoScope@@@Z; IsoReferenceDefaultScope(ulong,IsoScope * *)
0x180069246  mov     eax, edi
0x180069248  xchg    al, [rsi]
0x18006924a  mov     [rsp+0ED0h+var_EA0], 0
0x180069253  call    cs:__imp_?IsoGetCurrentProcessManager@@YAKXZ; IsoGetCurrentProcessManager(void)
0x180069259  xor     r9d, r9d
0x18006925c  lea     r8, [rsp+0ED0h+var_EA0]
0x180069261  mov     ecx, eax
0x180069263  mov     edx, edi
0x180069265  call    cs:__imp_?IsoGetArtifactAddress@@YAJKW4IsoArtifactType@@PEAPEAU_IsoArtifact@@PEAK@Z; IsoGetArtifactAddress(ulong,IsoArtifactType,_IsoArtifact * *,ulong *)
0x18006926b  mov     ebx, eax
0x18006926d  test    eax, eax
0x18006926f  js      loc_1800692FF
0x180069275  mov     rax, [rsp+0ED0h+var_EA0]
0x18006927a  lea     r8, ?LCIEProcessMessage@LCIEDiagnosticsSession@WebRuntimeDiagnostics@@SA_JPEAUHWND__@@I_K_J@Z; WebRuntimeDiagnostics::LCIEDiagnosticsSession::LCIEProcessMessage(HWND__ *,uint,unsigned __int64,__int64)
0x180069281  mov     dword ptr [rax+30h], 4
0x180069288  mov     rcx, [rsp+0ED0h+var_EA0]
0x18006928d  mov     edx, [rcx+30h]
0x180069290  call    ?SetFromSHAREDMEM_64BITVALUE@_IsoComponent@@QEAAXW4_IsoComponentDispatchType@@USHAREDMEM_64BITVALUE@@@Z; _IsoComponent::SetFromSHAREDMEM_64BITVALUE(_IsoComponentDispatchType,SHAREDMEM_64BITVALUE)
0x180069295  mov     rax, [rsp+0ED0h+var_EA0]
0x18006929a  xor     r9d, r9d; lpName
0x18006929d  xor     r8d, r8d; bInitialState
0x1800692a0  xor     edx, edx; bManualReset
0x1800692a2  xor     ecx, ecx; lpEventAttributes
0x1800692a4  btr     dword ptr [rax+14h], 19h
0x1800692a9  call    cs:__imp_CreateEventW
0x1800692af  mov     rdi, rax
0x1800692b2  test    rax, rax
0x1800692b5  jnz     short loc_1800692D0
0x1800692b7  mov     rcx, [rbp+0DD8h]; this
0x1800692be  lea     r8, aOnecoreuapInet_3; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x1800692c5  mov     edx, 1AEh; void *
0x1800692ca  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800692d0  call    cs:__imp_?IsoGetDefaultScope@@YAPEAUIsoScope@@XZ; IsoGetDefaultScope(void)
0x1800692d6  mov     rcx, rax
0x1800692d9  mov     r8, rdi
0x1800692dc  mov     rdx, [rax]
0x1800692df  mov     rax, [rdx+100h]
0x1800692e6  mov     edx, 11h
0x1800692eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800692f0  mov     rcx, rdi; hObject
0x1800692f3  mov     ebx, eax
0x1800692f5  call    cs:__imp_CloseHandle
0x1800692fb  test    ebx, ebx
0x1800692fd  jns     short loc_180069307
0x1800692ff  mov     rcx, rsi; this
0x180069302  call    ?UninitializeIsoSession@LCIEDiagnosticsSession@WebRuntimeDiagnostics@@AEAAXXZ; WebRuntimeDiagnostics::LCIEDiagnosticsSession::UninitializeIsoSession(void)
0x180069307  mov     eax, ebx
0x180069309  mov     rcx, [rbp+0DD0h+var_30]
0x180069310  xor     rcx, rsp; StackCookie
0x180069313  call    __security_check_cookie
0x180069318  add     rsp, 0EB8h
0x18006931f  pop     rdi
0x180069320  pop     rsi
0x180069321  pop     rbx
0x180069322  pop     rbp
0x180069323  retn
```
