# CDwnBindData::HandleBrokerRedirect(ushort const *,long)

- ea: `0x180a3b100`
- end: `0x180a3b5bd`
- name: `?HandleBrokerRedirect@CDwnBindData@@AEAAJPEBGJ@Z`
- size: `1213`
- prototype: `__int64 __fastcall(CDwnBindData *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180161610`

## callees

- `0x18005d080`
- `0x180323c94`
- `0x1805f2dec`
- `0x1807cc3bc`
- `0x1808cf80c`
- `0x1808d3fb0`
- `0x180a3af48`
- `0x180a3b100`
- `0x1810f6516`
- `0x181104010`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x180a3b43d`
- `KERNEL32!GetCurrentProcessId` at `0x180a3b43d`
- `KERNEL32!GetCurrentThreadId` at `0x180a3b132`
- `KERNEL32!GetCurrentThreadId` at `0x180a3b25d`
- `KERNEL32!GetCurrentThreadId` at `0x180a3b132`
- `KERNEL32!GetCurrentThreadId` at `0x180a3b25d`
- `KERNEL32!CreateThread` at `0x180a3b366`
- `KERNEL32!CreateThread` at `0x180a3b366`
- `KERNEL32!CloseHandle` at `0x180a3b37a`
- `KERNEL32!CloseHandle` at `0x180a3b37a`
- `USER32!AllowSetForegroundWindow` at `0x180a3b4c1`
- `USER32!AllowSetForegroundWindow` at `0x180a3b4c1`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x180a3b483`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x180a3b483`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x180a3b45f`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x180a3b45f`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180a3b427`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180a3b427`
- `api-ms-win-downlevel-ole32-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x180a3b3a0`
- `api-ms-win-downlevel-ole32-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x180a3b3db`
- `api-ms-win-downlevel-ole32-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x180a3b3a0`
- `api-ms-win-downlevel-ole32-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x180a3b3db`
- `api-ms-win-downlevel-ole32-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x180a3b31d`
- `api-ms-win-downlevel-ole32-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x180a3b31d`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IUnknown_QueryService` at `0x180a3b1e5`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IUnknown_QueryService` at `0x180a3b1e5`
- `msIso!__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z` at `0x180a3b14d`
- `msIso!__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z` at `0x180a3b14d`
- `msIso!__imp_?IsoInProcessData@@YAPEAXPEAU_IsoArtifact@@KKPEAX@Z` at `0x180a3b176`
- `msIso!__imp_?IsoInProcessData@@YAPEAXPEAU_IsoArtifact@@KKPEAX@Z` at `0x180a3b1a3`
- `msIso!__imp_?IsoInProcessData@@YAPEAXPEAU_IsoArtifact@@KKPEAX@Z` at `0x180a3b176`
- `msIso!__imp_?IsoInProcessData@@YAPEAXPEAU_IsoArtifact@@KKPEAX@Z` at `0x180a3b1a3`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180a3b46b`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180a3b547`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180a3b46b`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180a3b547`
- `msIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x180a3b44e`
- `msIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x180a3b44e`
- `OLEAUT32!__imp_VariantInit` at `0x180a3b2ac`
- `OLEAUT32!__imp_VariantInit` at `0x180a3b2ac`

## pseudocode

```c
__int64 __fastcall CDwnBindData::HandleBrokerRedirect(CDwnBindData *this, const unsigned __int16 *a2)
{
  DWORD CurrentThreadId; // eax
  int (__fastcall ***v5)(void *, GUID *, IUnknown **); // rax
  __int64 v6; // r8
  int MarshalledClientSiteStream; // ebx
  __int64 v8; // rax
  __int64 v9; // rdi
  __int64 v10; // rcx
  struct COmWindowProxy *v11; // r14
  unsigned __int64 v12; // rbx
  IStream **v13; // r14
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v16; // rax
  __int64 v17; // rcx
  HANDLE Thread; // rax
  IStream *v19; // rcx
  IStream *v20; // rcx
  unsigned int v21; // edx
  void *v22; // rcx
  DWORD v23; // ecx
  void (__fastcall *v24)(LPVOID, LPVOID *); // rbx
  int v25; // eax
  LPVOID v27; // [rsp+50h] [rbp-30h] BYREF
  void *ppvOut; // [rsp+58h] [rbp-28h] BYREF
  struct _IsoComponent *v29; // [rsp+60h] [rbp-20h] BYREF
  LPVOID ppv[2]; // [rsp+70h] [rbp-10h] BYREF
  unsigned int v31; // [rsp+C0h] [rbp+40h] BYREF
  IUnknown *punk; // [rsp+C8h] [rbp+48h] BYREF

  v31 = 0;
  v29 = 0;
  CurrentThreadId = GetCurrentThreadId();
  if ( (int)LCIEGetTypedComponentFromThread(0x203u, CurrentThreadId, &v31, &v29) >= 0
    && IsoInProcessData(v29, 0x30014u, *((_DWORD *)v29 + 67), 0) )
  {
    ppvOut = 0;
    punk = 0;
    v5 = (int (__fastcall ***)(void *, GUID *, IUnknown **))IsoInProcessData(v29, 0x30014u, *((_DWORD *)v29 + 67), 0);
    if ( (**v5)(v5, &GUID_d8d2dda0_fd33_4b6a_9a67_e8c9fb471034, &punk) >= 0 )
    {
      IUnknown_QueryService(punk, &IID_IWebBrowserApp, &GUID_5a625ea4_a89f_4eb2_a45a_9ad4e37d4b00, &ppvOut);
      ((void (__fastcall *)(IUnknown *, _QWORD, _QWORD))punk->lpVtbl[1].QueryInterface)(punk, 0, 0);
      ((void (__fastcall *)(IUnknown *))punk->lpVtbl->Release)(punk);
    }
    MarshalledClientSiteStream = -2147024882;
    v8 = MemoryProtection::HeapAlloc<0>(g_hProcessHeap, 176, v6);
    v9 = v8;
    if ( v8 )
    {
      *(_QWORD *)v8 = 0;
      *(_DWORD *)(v8 + 8) = 0;
      *(_QWORD *)(v8 + 16) = 0;
      *(_QWORD *)(v8 + 24) = 0;
      memset_0((void *)(v8 + 32), 0, 0x90u);
      *(_DWORD *)v9 = v31;
      *(_DWORD *)(v9 + 8) = GetCurrentThreadId();
      *(_DWORD *)(v9 + 4) = 134234112;
      v10 = *(_QWORD *)(*((_QWORD *)this + 10) + 112LL);
      if ( v10 )
      {
        v11 = *(struct COmWindowProxy **)(v10 + 352);
        if ( v11 )
        {
          v12 = *(_QWORD *)(v10 + 136) & 0x200000000000000LL;
          VariantInit((VARIANTARG *)(v9 + 120));
          MarshalledClientSiteStream = SetBrokerBindInfoForRedirectToBroker(
                                         a2,
                                         a2,
                                         this,
                                         v11,
                                         v12,
                                         0,
                                         0,
                                         0,
                                         (struct _BROKER_BIND_INFO *)(v9 + 32));
          if ( MarshalledClientSiteStream >= 0 )
          {
            v13 = (IStream **)(v9 + 16);
            MarshalledClientSiteStream = CDwnBindData::GetMarshalledClientSiteStream(this, (struct IStream **)(v9 + 16));
            if ( MarshalledClientSiteStream >= 0 )
            {
              if ( ppvOut )
                CoMarshalInterThreadInterfaceInStream(&IID_IXMicTestMode, (LPUNKNOWN)ppvOut, (LPSTREAM *)(v9 + 24));
              v16 = *((_QWORD *)this + 10);
              if ( v16 )
              {
                v17 = *(_QWORD *)(v16 + 104);
                if ( v17 )
                {
                  if ( !(unsigned int)CDoc::CheckBFCacheCandidacy(v17, 809035761, v14, v15) )
                    *(_DWORD *)(v9 + 4) |= 0x40000u;
                }
              }
              Thread = CreateThread(0, 0, BrokerRedirectUrlThreadProc, (LPVOID)v9, 0, 0);
              if ( Thread )
              {
                CloseHandle(Thread);
                MarshalledClientSiteStream = 0;
                goto LABEL_25;
              }
              v19 = *v13;
              ppv[0] = 0;
              if ( CoGetInterfaceAndReleaseStream(v19, &GUID_00000000_0000_0000_c000_000000000046, ppv) >= 0 )
                (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv[0] + 16LL))(ppv[0]);
              v20 = *(IStream **)(v9 + 24);
              *v13 = 0;
              v27 = 0;
              if ( v20 && CoGetInterfaceAndReleaseStream(v20, &GUID_5a625ea4_a89f_4eb2_a45a_9ad4e37d4b00, &v27) >= 0 )
                (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v27 + 16LL))(v27);
              *(_QWORD *)(v9 + 24) = 0;
              MarshalledClientSiteStream = -2147467259;
            }
          }
        }
      }
      ClearBrokerBindInfo((struct _BROKER_BIND_INFO *)(v9 + 32));
      CSize::`scalar deleting destructor'((CSize *)v9, v21);
    }
LABEL_25:
    v22 = ppvOut;
    if ( ppvOut )
      goto LABEL_36;
    return (unsigned int)MarshalledClientSiteStream;
  }
  if ( IsDualEngineProcess() )
    Abandonment::AssertionFailed();
  GetCurrentProcessId();
  IsoGetIntegrity(1);
  IEConfiguration_GetDWORD(536870929);
  GlobalThreadState();
  v27 = 0;
  ppvOut = 0;
  MarshalledClientSiteStream = CoCreateUserBroker((struct IEUserBroker **)&ppvOut);
  if ( MarshalledClientSiteStream >= 0 )
  {
    LODWORD(punk) = 0;
    (*(void (__fastcall **)(void *, _QWORD, _QWORD, IUnknown **))(*(_QWORD *)ppvOut + 24LL))(ppvOut, 0, 0, &punk);
    v23 = -1;
    if ( (_DWORD)punk )
      v23 = (unsigned int)punk;
    AllowSetForegroundWindow(v23);
    ppv[0] = 0;
    MarshalledClientSiteStream = (*(__int64 (__fastcall **)(void *, GUID *, GUID *, LPVOID *))(*(_QWORD *)ppvOut + 48LL))(
                                   ppvOut,
                                   &CLSID_CShdocvwBroker,
                                   &IID_IUnknown,
                                   ppv);
    if ( MarshalledClientSiteStream >= 0 )
    {
      MarshalledClientSiteStream = (**(__int64 (__fastcall ***)(LPVOID, GUID *, LPVOID *))ppv[0])(
                                     ppv[0],
                                     &GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42,
                                     &v27);
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv[0] + 16LL))(ppv[0]);
    }
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
    if ( MarshalledClientSiteStream >= 0 )
    {
      v24 = *(void (__fastcall **)(LPVOID, LPVOID *))(*(_QWORD *)v27 + 1256LL);
      *(_OWORD *)ppv = *(_OWORD *)GlobalThreadState();
      v24(v27, ppv);
      v25 = (*(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *, __int64, _QWORD, _QWORD))(*(_QWORD *)v27 + 24LL))(
              v27,
              a2,
              2048,
              0,
              0);
      v22 = v27;
      MarshalledClientSiteStream = v25;
LABEL_36:
      (*(void (__fastcall **)(void *))(*(_QWORD *)v22 + 16LL))(v22);
    }
  }
  return (unsigned int)MarshalledClientSiteStream;
}

```

## disassembly

```asm
0x180a3b100  mov     [rsp-28h+arg_0], rbx
0x180a3b105  mov     [rsp-28h+arg_8], rsi
0x180a3b10a  mov     [rsp-28h+arg_10], r8d
0x180a3b10f  push    rbp
0x180a3b110  push    rdi
0x180a3b111  push    r12
0x180a3b113  push    r14
0x180a3b115  push    r15
0x180a3b117  mov     rbp, rsp
0x180a3b11a  sub     rsp, 80h
0x180a3b121  xor     r12d, r12d
0x180a3b124  mov     r15, rdx
0x180a3b127  mov     [rbp+arg_10], r12d
0x180a3b12b  mov     rsi, rcx
0x180a3b12e  mov     [rbp+var_20], r12
0x180a3b132  call    cs:__imp_GetCurrentThreadId
0x180a3b139  nop     dword ptr [rax+rax+00h]
0x180a3b13e  lea     r9, [rbp+var_20]
0x180a3b142  mov     ecx, 203h
0x180a3b147  mov     edx, eax
0x180a3b149  lea     r8, [rbp+arg_10]
0x180a3b14d  call    cs:__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z; LCIEGetTypedComponentFromThread(ulong,ulong,ulong *,_IsoComponent * *)
0x180a3b154  nop     dword ptr [rax+rax+00h]
0x180a3b159  test    eax, eax
0x180a3b15b  js      loc_180A3B427
0x180a3b161  mov     rcx, [rbp+var_20]
0x180a3b165  mov     ebx, 30014h
0x180a3b16a  xor     r9d, r9d
0x180a3b16d  mov     edx, ebx
0x180a3b16f  mov     r8d, [rcx+10Ch]
0x180a3b176  call    cs:__imp_?IsoInProcessData@@YAPEAXPEAU_IsoArtifact@@KKPEAX@Z; IsoInProcessData(_IsoArtifact *,ulong,ulong,void *)
0x180a3b17d  nop     dword ptr [rax+rax+00h]
0x180a3b182  test    rax, rax
0x180a3b185  jz      loc_180A3B427
0x180a3b18b  mov     rcx, [rbp+var_20]
0x180a3b18f  xor     r9d, r9d
0x180a3b192  mov     [rbp+ppvOut], r12
0x180a3b196  mov     edx, ebx
0x180a3b198  mov     [rbp+punk], r12
0x180a3b19c  mov     r8d, [rcx+10Ch]
0x180a3b1a3  call    cs:__imp_?IsoInProcessData@@YAPEAXPEAU_IsoArtifact@@KKPEAX@Z; IsoInProcessData(_IsoArtifact *,ulong,ulong,void *)
0x180a3b1aa  nop     dword ptr [rax+rax+00h]
0x180a3b1af  mov     r9, rax
0x180a3b1b2  lea     r8, [rbp+punk]
0x180a3b1b6  lea     rdx, _GUID_d8d2dda0_fd33_4b6a_9a67_e8c9fb471034
0x180a3b1bd  mov     rcx, [rax]
0x180a3b1c0  mov     rax, [rcx]
0x180a3b1c3  mov     rcx, r9
0x180a3b1c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180a3b1cb  test    eax, eax
0x180a3b1cd  js      short loc_180A3B216
0x180a3b1cf  mov     rcx, [rbp+punk]; punk
0x180a3b1d3  lea     r9, [rbp+ppvOut]; ppvOut
0x180a3b1d7  lea     r8, _GUID_5a625ea4_a89f_4eb2_a45a_9ad4e37d4b00; riid
0x180a3b1de  lea     rdx, IID_IWebBrowserApp; guidService
0x180a3b1e5  call    cs:__imp_IUnknown_QueryService
0x180a3b1ec  nop     dword ptr [rax+rax+00h]
0x180a3b1f1  mov     rcx, [rbp+punk]
0x180a3b1f5  xor     r8d, r8d
0x180a3b1f8  xor     edx, edx
0x180a3b1fa  mov     rax, [rcx]
0x180a3b1fd  mov     rax, [rax+18h]
0x180a3b201  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180a3b206  mov     rcx, [rbp+punk]
0x180a3b20a  mov     rax, [rcx]
0x180a3b20d  mov     rax, [rax+10h]
0x180a3b211  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180a3b216  mov     rcx, cs:g_hProcessHeap
0x180a3b21d  mov     edx, 0B0h
0x180a3b222  mov     ebx, 8007000Eh
0x180a3b227  call    ??$HeapAlloc@$0A@@MemoryProtection@@YAPEAXPEAX_K@Z; MemoryProtection::HeapAlloc<0>(void *,unsigned __int64)
0x180a3b22c  mov     rdi, rax
0x180a3b22f  test    rax, rax
0x180a3b232  jz      loc_180A3B415
0x180a3b238  lea     rcx, [rax+20h]; void *
0x180a3b23c  mov     [rax], r12
0x180a3b23f  xor     edx, edx; Val
0x180a3b241  mov     [rax+8], r12d
0x180a3b245  mov     r8d, 90h; Size
0x180a3b24b  mov     [rax+10h], r12
0x180a3b24f  mov     [rax+18h], r12
0x180a3b253  call    memset_0
0x180a3b258  mov     ecx, [rbp+arg_10]
0x180a3b25b  mov     [rdi], ecx
0x180a3b25d  call    cs:__imp_GetCurrentThreadId
0x180a3b264  nop     dword ptr [rax+rax+00h]
0x180a3b269  mov     [rdi+8], eax
0x180a3b26c  mov     dword ptr [rdi+4], 8004000h
0x180a3b273  mov     rax, [rsi+50h]
0x180a3b277  mov     rcx, [rax+70h]
0x180a3b27b  test    rcx, rcx
0x180a3b27e  jz      loc_180A3B404
0x180a3b284  mov     r14, [rcx+160h]
0x180a3b28b  test    r14, r14
0x180a3b28e  jz      loc_180A3B404
0x180a3b294  mov     rbx, [rcx+88h]
0x180a3b29b  mov     rax, 200000000000000h
0x180a3b2a5  lea     rcx, [rdi+78h]; pvarg
0x180a3b2a9  and     rbx, rax
0x180a3b2ac  call    cs:__imp_VariantInit
0x180a3b2b3  nop     dword ptr [rax+rax+00h]
0x180a3b2b8  lea     rax, [rdi+20h]
0x180a3b2bc  mov     r9, r14; struct COmWindowProxy *
0x180a3b2bf  mov     [rsp+80h+var_40], rax; struct _BROKER_BIND_INFO *
0x180a3b2c4  mov     r8, rsi; struct CDwnBindInfo *
0x180a3b2c7  mov     [rsp+80h+var_48], r12; unsigned __int16 *
0x180a3b2cc  mov     rdx, r15; unsigned __int16 *
0x180a3b2cf  mov     [rsp+80h+var_50], r12; unsigned __int16 *
0x180a3b2d4  mov     rcx, r15; unsigned __int16 *
0x180a3b2d7  mov     [rsp+80h+lpThreadId], r12; unsigned __int16 *
0x180a3b2dc  mov     qword ptr [rsp+80h+dwCreationFlags], rbx; unsigned __int64
0x180a3b2e1  call    ?SetBrokerBindInfoForRedirectToBroker@@YAJPEBG0PEAVCDwnBindInfo@@PEAVCOmWindowProxy@@_K000PEAU_BROKER_BIND_INFO@@@Z; SetBrokerBindInfoForRedirectToBroker(ushort const *,ushort const *,CDwnBindInfo *,COmWindowProxy *,unsigned __int64,ushort const *,ushort const *,ushort const *,_BROKER_BIND_INFO *)
0x180a3b2e6  mov     ebx, eax
0x180a3b2e8  test    eax, eax
0x180a3b2ea  js      loc_180A3B404
0x180a3b2f0  lea     r14, [rdi+10h]
0x180a3b2f4  mov     rcx, rsi; this
0x180a3b2f7  mov     rdx, r14; struct IStream **
0x180a3b2fa  call    ?GetMarshalledClientSiteStream@CDwnBindData@@AEAAJPEAPEAUIStream@@@Z; CDwnBindData::GetMarshalledClientSiteStream(IStream * *)
0x180a3b2ff  mov     ebx, eax
0x180a3b301  test    eax, eax
0x180a3b303  js      loc_180A3B404
0x180a3b309  mov     rdx, [rbp+ppvOut]; pUnk
0x180a3b30d  test    rdx, rdx
0x180a3b310  jz      short loc_180A3B329
0x180a3b312  lea     r8, [rdi+18h]; ppStm
0x180a3b316  lea     rcx, IID_IXMicTestMode; riid
0x180a3b31d  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x180a3b324  nop     dword ptr [rax+rax+00h]
0x180a3b329  mov     rax, [rsi+50h]
0x180a3b32d  test    rax, rax
0x180a3b330  jz      short loc_180A3B34E
0x180a3b332  mov     rcx, [rax+68h]
0x180a3b336  test    rcx, rcx
0x180a3b339  jz      short loc_180A3B34E
0x180a3b33b  mov     edx, 3038E7F1h
0x180a3b340  call    ?CheckBFCacheCandidacy@CDoc@@QEAA?AW4tagBFCACHE_CANDIDACY_FAILURE_FLAGS@@W42@@Z; CDoc::CheckBFCacheCandidacy(tagBFCACHE_CANDIDACY_FAILURE_FLAGS)
0x180a3b345  test    eax, eax
0x180a3b347  jnz     short loc_180A3B34E
0x180a3b349  bts     dword ptr [rdi+4], 12h
0x180a3b34e  mov     [rsp+80h+lpThreadId], r12; lpThreadId
0x180a3b353  lea     r8, ?BrokerRedirectUrlThreadProc@@YAKPEAX@Z; lpStartAddress
0x180a3b35a  mov     r9, rdi; lpParameter
0x180a3b35d  mov     [rsp+80h+dwCreationFlags], r12d; dwCreationFlags
0x180a3b362  xor     edx, edx; dwStackSize
0x180a3b364  xor     ecx, ecx; lpThreadAttributes
0x180a3b366  call    cs:__imp_CreateThread
0x180a3b36d  nop     dword ptr [rax+rax+00h]
0x180a3b372  test    rax, rax
0x180a3b375  jz      short loc_180A3B38E
0x180a3b377  mov     rcx, rax; hObject
0x180a3b37a  call    cs:__imp_CloseHandle
0x180a3b381  nop     dword ptr [rax+rax+00h]
0x180a3b386  mov     ebx, r12d
0x180a3b389  jmp     loc_180A3B415
0x180a3b38e  mov     rcx, [r14]; pStm
0x180a3b391  lea     r8, [rbp+ppv]; ppv
0x180a3b395  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; iid
0x180a3b39c  mov     [rbp+ppv], r12
0x180a3b3a0  call    cs:__imp_CoGetInterfaceAndReleaseStream
0x180a3b3a7  nop     dword ptr [rax+rax+00h]
0x180a3b3ac  test    eax, eax
0x180a3b3ae  js      short loc_180A3B3C0
0x180a3b3b0  mov     rcx, [rbp+ppv]
0x180a3b3b4  mov     rax, [rcx]
0x180a3b3b7  mov     rax, [rax+10h]
0x180a3b3bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180a3b3c0  mov     rcx, [rdi+18h]; pStm
0x180a3b3c4  mov     [r14], r12
0x180a3b3c7  mov     [rbp+var_30], r12
0x180a3b3cb  test    rcx, rcx
0x180a3b3ce  jz      short loc_180A3B3FB
0x180a3b3d0  lea     r8, [rbp+var_30]; ppv
0x180a3b3d4  lea     rdx, _GUID_5a625ea4_a89f_4eb2_a45a_9ad4e37d4b00; iid
0x180a3b3db  call    cs:__imp_CoGetInterfaceAndReleaseStream
0x180a3b3e2  nop     dword ptr [rax+rax+00h]
0x180a3b3e7  test    eax, eax
0x180a3b3e9  js      short loc_180A3B3FB
0x180a3b3eb  mov     rcx, [rbp+var_30]
0x180a3b3ef  mov     rax, [rcx]
0x180a3b3f2  mov     rax, [rax+10h]
0x180a3b3f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180a3b3fb  mov     [rdi+18h], r12
0x180a3b3ff  mov     ebx, 80004005h
0x180a3b404  lea     rcx, [rdi+20h]; struct _BROKER_BIND_INFO *
0x180a3b408  call    ?ClearBrokerBindInfo@@YAXPEAU_BROKER_BIND_INFO@@@Z; ClearBrokerBindInfo(_BROKER_BIND_INFO *)
0x180a3b40d  mov     rcx, rdi; this
0x180a3b410  call    ??_GCSize@@QEAAPEAXI@Z; CSize::`scalar deleting destructor'(uint)
0x180a3b415  mov     rcx, [rbp+ppvOut]
0x180a3b419  test    rcx, rcx
0x180a3b41c  jz      loc_180A3B59E
0x180a3b422  jmp     loc_180A3B592
0x180a3b427  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x180a3b42e  nop     dword ptr [rax+rax+00h]
0x180a3b433  test    al, al
0x180a3b435  jz      short loc_180A3B43D
0x180a3b437  call    ?AssertionFailed@Abandonment@@SAXXZ; Abandonment::AssertionFailed(void)
0x180a3b43d  call    cs:__imp_GetCurrentProcessId
0x180a3b444  nop     dword ptr [rax+rax+00h]
0x180a3b449  mov     ecx, 1
0x180a3b44e  call    cs:__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z; IsoGetIntegrity(ulong)
0x180a3b455  nop     dword ptr [rax+rax+00h]
0x180a3b45a  mov     ecx, 20000011h
0x180a3b45f  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x180a3b466  nop     dword ptr [rax+rax+00h]
0x180a3b46b  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180a3b472  nop     dword ptr [rax+rax+00h]
0x180a3b477  lea     rcx, [rbp+ppvOut]
0x180a3b47b  mov     [rbp+var_30], r12
0x180a3b47f  mov     [rbp+ppvOut], r12
0x180a3b483  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x180a3b48a  nop     dword ptr [rax+rax+00h]
0x180a3b48f  mov     ebx, eax
0x180a3b491  test    eax, eax
0x180a3b493  js      loc_180A3B59E
0x180a3b499  mov     rcx, [rbp+ppvOut]
0x180a3b49d  lea     r9, [rbp+punk]
0x180a3b4a1  mov     dword ptr [rbp+punk], r12d
0x180a3b4a5  xor     r8d, r8d
0x180a3b4a8  xor     edx, edx
0x180a3b4aa  mov     rax, [rcx]
0x180a3b4ad  mov     rax, [rax+18h]
0x180a3b4b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180a3b4b6  mov     eax, dword ptr [rbp+punk]
0x180a3b4b9  or      ecx, 0FFFFFFFFh
0x180a3b4bc  test    eax, eax
0x180a3b4be  cmovnz  ecx, eax; dwProcessId
0x180a3b4c1  call    cs:__imp_AllowSetForegroundWindow
0x180a3b4c8  nop     dword ptr [rax+rax+00h]
0x180a3b4cd  mov     rcx, [rbp+ppvOut]
0x180a3b4d1  lea     r9, [rbp+ppv]
0x180a3b4d5  mov     [rbp+ppv], r12
0x180a3b4d9  lea     r8, IID_IUnknown
0x180a3b4e0  lea     rdx, CLSID_CShdocvwBroker
0x180a3b4e7  mov     rax, [rcx]
0x180a3b4ea  mov     rax, [rax+30h]
0x180a3b4ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180a3b4f3  mov     ebx, eax
0x180a3b4f5  test    eax, eax
0x180a3b4f7  js      short loc_180A3B525
0x180a3b4f9  mov     rcx, [rbp+ppv]
0x180a3b4fd  lea     r8, [rbp+var_30]
0x180a3b501  lea     rdx, _GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42
0x180a3b508  mov     rax, [rcx]
0x180a3b50b  mov     rax, [rax]
0x180a3b50e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180a3b513  mov     rcx, [rbp+ppv]
0x180a3b517  mov     ebx, eax
0x180a3b519  mov     rax, [rcx]
0x180a3b51c  mov     rax, [rax+10h]
0x180a3b520  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180a3b525  mov     rcx, [rbp+ppvOut]
0x180a3b529  mov     rax, [rcx]
0x180a3b52c  mov     rax, [rax+10h]
0x180a3b530  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180a3b535  test    ebx, ebx
0x180a3b537  js      short loc_180A3B59E
0x180a3b539  mov     rax, [rbp+var_30]
0x180a3b53d  mov     rcx, [rax]
0x180a3b540  mov     rbx, [rcx+4E8h]
0x180a3b547  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180a3b54e  nop     dword ptr [rax+rax+00h]
0x180a3b553  mov     rcx, [rbp+var_30]
0x180a3b557  lea     rdx, [rbp+ppv]
0x180a3b55b  movups  xmm0, xmmword ptr [rax]
0x180a3b55e  mov     rax, rbx
0x180a3b561  movdqu  xmmword ptr [rbp+ppv], xmm0
0x180a3b566  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180a3b56b  mov     rcx, [rbp+var_30]
0x180a3b56f  xor     r9d, r9d
0x180a3b572  mov     r8d, 800h
0x180a3b578  mov     qword ptr [rsp+80h+dwCreationFlags], r12
0x180a3b57d  mov     rdx, r15
0x180a3b580  mov     rax, [rcx]
0x180a3b583  mov     rax, [rax+18h]
0x180a3b587  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180a3b58c  mov     rcx, [rbp+var_30]
0x180a3b590  mov     ebx, eax
0x180a3b592  mov     rax, [rcx]
0x180a3b595  mov     rax, [rax+10h]
0x180a3b599  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180a3b59e  lea     r11, [rsp+80h+var_s0]
0x180a3b5a6  mov     eax, ebx
0x180a3b5a8  mov     rbx, [r11+30h]
0x180a3b5ac  mov     rsi, [r11+38h]
0x180a3b5b0  mov     rsp, r11
0x180a3b5b3  pop     r15
0x180a3b5b5  pop     r14
0x180a3b5b7  pop     r12
0x180a3b5b9  pop     rdi
0x180a3b5ba  pop     rbp
0x180a3b5bb  retn
```
