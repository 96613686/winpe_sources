# CDwnBindData::HandleBrokerRedirect(ushort const *,long)

- ea: `0x180a28264`
- end: `0x180a2870a`
- name: `?HandleBrokerRedirect@CDwnBindData@@AEAAJPEBGJ@Z`
- size: `1190`
- prototype: `__int64 __fastcall(CDwnBindData *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1804e7d30`

## callees

- `0x1801bf528`
- `0x1802910dc`
- `0x1805fe298`
- `0x1807c0050`
- `0x1808c5f50`
- `0x1808c936c`
- `0x180a28264`
- `0x1810c2cb6`
- `0x1810d1010`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x180a285b5`
- `KERNEL32!GetCurrentProcessId` at `0x180a285b5`
- `KERNEL32!GetCurrentThreadId` at `0x180a28296`
- `KERNEL32!GetCurrentThreadId` at `0x180a283a3`
- `KERNEL32!GetCurrentThreadId` at `0x180a28296`
- `KERNEL32!GetCurrentThreadId` at `0x180a283a3`
- `KERNEL32!CreateThread` at `0x180a284fc`
- `KERNEL32!CreateThread` at `0x180a284fc`
- `KERNEL32!CloseHandle` at `0x180a2850a`
- `KERNEL32!CloseHandle` at `0x180a2850a`
- `USER32!AllowSetForegroundWindow` at `0x180a2861b`
- `USER32!AllowSetForegroundWindow` at `0x180a2861b`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x180a285e3`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x180a285e3`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x180a285cb`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x180a285cb`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180a285a5`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180a285a5`
- `api-ms-win-downlevel-ole32-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x180a28527`
- `api-ms-win-downlevel-ole32-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x180a2855c`
- `api-ms-win-downlevel-ole32-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x180a28527`
- `api-ms-win-downlevel-ole32-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x180a2855c`
- `api-ms-win-downlevel-ole32-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x180a28485`
- `api-ms-win-downlevel-ole32-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x180a284b9`
- `api-ms-win-downlevel-ole32-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x180a28485`
- `api-ms-win-downlevel-ole32-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x180a284b9`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IUnknown_QueryService` at `0x180a28331`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IUnknown_QueryService` at `0x180a28331`
- `msIso!__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z` at `0x180a282ab`
- `msIso!__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z` at `0x180a282ab`
- `msIso!__imp_?IsoInProcessData@@YAPEAXPEAU_IsoArtifact@@KKPEAX@Z` at `0x180a282ce`
- `msIso!__imp_?IsoInProcessData@@YAPEAXPEAU_IsoArtifact@@KKPEAX@Z` at `0x180a282f5`
- `msIso!__imp_?IsoInProcessData@@YAPEAXPEAU_IsoArtifact@@KKPEAX@Z` at `0x180a282ce`
- `msIso!__imp_?IsoInProcessData@@YAPEAXPEAU_IsoArtifact@@KKPEAX@Z` at `0x180a282f5`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180a285d1`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180a2869b`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180a285d1`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180a2869b`
- `msIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x180a285c0`
- `msIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x180a285c0`
- `OLEAUT32!__imp_VariantInit` at `0x180a283ec`
- `OLEAUT32!__imp_VariantInit` at `0x180a283ec`

## pseudocode

```c
__int64 __fastcall CDwnBindData::HandleBrokerRedirect(CDwnBindData *this, const unsigned __int16 *a2)
{
  DWORD CurrentThreadId; // eax
  int (__fastcall ***v5)(void *, GUID *, IUnknown **); // rax
  int UserBroker; // ebx
  __int64 v7; // rax
  __int64 v8; // rdi
  __int64 v9; // rcx
  struct COmWindowProxy *v10; // rsi
  unsigned __int64 v11; // rbx
  HRESULT v12; // esi
  __int64 v13; // rcx
  __int64 (__fastcall ***v14)(_QWORD, GUID *, LPUNKNOWN *); // rcx
  IStream **v15; // r15
  __int64 v16; // r8
  __int64 v17; // r9
  __int64 v18; // rax
  __int64 v19; // rcx
  HANDLE Thread; // rax
  IStream *v21; // rcx
  IStream *v22; // rcx
  unsigned int v23; // edx
  void *v24; // rcx
  DWORD v25; // ecx
  void (__fastcall *v26)(void *, LPVOID *); // rbx
  int v27; // eax
  void *ppvOut; // [rsp+50h] [rbp-30h] BYREF
  LPUNKNOWN pUnk; // [rsp+58h] [rbp-28h] BYREF
  struct _IsoComponent *v31; // [rsp+60h] [rbp-20h] BYREF
  LPVOID ppv[2]; // [rsp+70h] [rbp-10h] BYREF
  unsigned int v33; // [rsp+C0h] [rbp+40h] BYREF
  IUnknown *punk; // [rsp+C8h] [rbp+48h] BYREF

  v33 = 0;
  v31 = 0;
  CurrentThreadId = GetCurrentThreadId();
  if ( (int)LCIEGetTypedComponentFromThread(0x203u, CurrentThreadId, &v33, &v31) >= 0
    && IsoInProcessData(v31, 0x30014u, *((_DWORD *)v31 + 67), 0) )
  {
    ppvOut = 0;
    punk = 0;
    v5 = (int (__fastcall ***)(void *, GUID *, IUnknown **))IsoInProcessData(v31, 0x30014u, *((_DWORD *)v31 + 67), 0);
    if ( (**v5)(v5, &GUID_d8d2dda0_fd33_4b6a_9a67_e8c9fb471034, &punk) >= 0 )
    {
      IUnknown_QueryService(punk, &IID_IWebBrowserApp, &GUID_5a625ea4_a89f_4eb2_a45a_9ad4e37d4b00, &ppvOut);
      ((void (__fastcall *)(IUnknown *, _QWORD, _QWORD))punk->lpVtbl[1].QueryInterface)(punk, 0, 0);
      ((void (__fastcall *)(IUnknown *))punk->lpVtbl->Release)(punk);
    }
    UserBroker = -2147024882;
    v7 = MemoryProtection::HeapAlloc<0>(g_hProcessHeap, 176);
    v8 = v7;
    if ( v7 )
    {
      *(_QWORD *)v7 = 0;
      *(_DWORD *)(v7 + 8) = 0;
      *(_QWORD *)(v7 + 16) = 0;
      *(_QWORD *)(v7 + 24) = 0;
      memset_0((void *)(v7 + 32), 0, 0x90u);
      *(_DWORD *)v8 = v33;
      *(_DWORD *)(v8 + 8) = GetCurrentThreadId();
      *(_DWORD *)(v8 + 4) = 134234112;
      v9 = *(_QWORD *)(*((_QWORD *)this + 10) + 112LL);
      if ( v9 )
      {
        v10 = *(struct COmWindowProxy **)(v9 + 352);
        if ( v10 )
        {
          v11 = *(_QWORD *)(v9 + 136) & 0x200000000000000LL;
          VariantInit((VARIANTARG *)(v8 + 120));
          UserBroker = SetBrokerBindInfoForRedirectToBroker(
                         a2,
                         a2,
                         this,
                         v10,
                         v11,
                         0,
                         0,
                         0,
                         (struct _BROKER_BIND_INFO *)(v8 + 32));
          if ( UserBroker >= 0 )
          {
            UserBroker = -2147467259;
            v12 = -2147467259;
            v13 = *(_QWORD *)(*((_QWORD *)this + 10) + 104LL);
            if ( v13
              && (v14 = *(__int64 (__fastcall ****)(_QWORD, GUID *, LPUNKNOWN *))(v13 + 64)) != 0
              && (pUnk = 0, v12 = (**v14)(v14, &GUID_00000000_0000_0000_c000_000000000046, &pUnk), v12 >= 0)
              && (v15 = (IStream **)(v8 + 16),
                  v12 = CoMarshalInterThreadInterfaceInStream(&IID_IUnknown, pUnk, (LPSTREAM *)(v8 + 16)),
                  ((void (__fastcall *)(LPUNKNOWN))pUnk->lpVtbl->Release)(pUnk),
                  v12 >= 0) )
            {
              if ( ppvOut )
                CoMarshalInterThreadInterfaceInStream(&IID_IXMicTestMode, (LPUNKNOWN)ppvOut, (LPSTREAM *)(v8 + 24));
              v18 = *((_QWORD *)this + 10);
              if ( v18 )
              {
                v19 = *(_QWORD *)(v18 + 104);
                if ( v19 )
                {
                  if ( !(unsigned int)CDoc::CheckBFCacheCandidacy(v19, 809035761, v16, v17) )
                    *(_DWORD *)(v8 + 4) |= 0x40000u;
                }
              }
              Thread = CreateThread(0, 0, BrokerRedirectUrlThreadProc, (LPVOID)v8, 0, 0);
              if ( Thread )
              {
                CloseHandle(Thread);
                UserBroker = 0;
                goto LABEL_29;
              }
              v21 = *v15;
              ppv[0] = 0;
              if ( CoGetInterfaceAndReleaseStream(v21, &GUID_00000000_0000_0000_c000_000000000046, ppv) >= 0 )
                (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv[0] + 16LL))(ppv[0]);
              v22 = *(IStream **)(v8 + 24);
              *v15 = 0;
              pUnk = 0;
              if ( v22
                && CoGetInterfaceAndReleaseStream(v22, &GUID_5a625ea4_a89f_4eb2_a45a_9ad4e37d4b00, (LPVOID *)&pUnk) >= 0 )
              {
                ((void (__fastcall *)(LPUNKNOWN))pUnk->lpVtbl->Release)(pUnk);
              }
              *(_QWORD *)(v8 + 24) = 0;
            }
            else
            {
              UserBroker = v12;
            }
          }
        }
      }
      ClearBrokerBindInfo((struct _BROKER_BIND_INFO *)(v8 + 32));
      CSize::`scalar deleting destructor'((CSize *)v8, v23);
    }
LABEL_29:
    v24 = ppvOut;
    if ( ppvOut )
      goto LABEL_40;
    return (unsigned int)UserBroker;
  }
  if ( IsDualEngineProcess() )
    Abandonment::AssertionFailed();
  GetCurrentProcessId();
  IsoGetIntegrity(1);
  IEConfiguration_GetDWORD(536870929);
  GlobalThreadState();
  ppvOut = 0;
  pUnk = 0;
  UserBroker = CoCreateUserBroker((struct IEUserBroker **)&pUnk);
  if ( UserBroker >= 0 )
  {
    LODWORD(punk) = 0;
    ((void (__fastcall *)(LPUNKNOWN, _QWORD, _QWORD, IUnknown **))pUnk->lpVtbl[1].QueryInterface)(pUnk, 0, 0, &punk);
    v25 = -1;
    if ( (_DWORD)punk )
      v25 = (unsigned int)punk;
    AllowSetForegroundWindow(v25);
    ppv[0] = 0;
    UserBroker = ((__int64 (__fastcall *)(LPUNKNOWN, GUID *, GUID *, LPVOID *))pUnk->lpVtbl[2].QueryInterface)(
                   pUnk,
                   &CLSID_CShdocvwBroker,
                   &IID_IUnknown,
                   ppv);
    if ( UserBroker >= 0 )
    {
      UserBroker = (**(__int64 (__fastcall ***)(LPVOID, GUID *, void **))ppv[0])(
                     ppv[0],
                     &GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42,
                     &ppvOut);
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv[0] + 16LL))(ppv[0]);
    }
    ((void (__fastcall *)(LPUNKNOWN))pUnk->lpVtbl->Release)(pUnk);
    if ( UserBroker >= 0 )
    {
      v26 = *(void (__fastcall **)(void *, LPVOID *))(*(_QWORD *)ppvOut + 1256LL);
      *(_OWORD *)ppv = *(_OWORD *)GlobalThreadState();
      v26(ppvOut, ppv);
      v27 = (*(__int64 (__fastcall **)(void *, const unsigned __int16 *, __int64, _QWORD, _QWORD))(*(_QWORD *)ppvOut
                                                                                                 + 24LL))(
              ppvOut,
              a2,
              2048,
              0,
              0);
      v24 = ppvOut;
      UserBroker = v27;
LABEL_40:
      (*(void (__fastcall **)(void *))(*(_QWORD *)v24 + 16LL))(v24);
    }
  }
  return (unsigned int)UserBroker;
}

```

## disassembly

```asm
0x180a28264  mov     [rsp-28h+arg_0], rbx
0x180a28269  mov     [rsp-28h+arg_8], rsi
0x180a2826e  mov     [rsp-28h+arg_10], r8d
0x180a28273  push    rbp
0x180a28274  push    rdi
0x180a28275  push    r12
0x180a28277  push    r14
0x180a28279  push    r15
0x180a2827b  mov     rbp, rsp
0x180a2827e  sub     rsp, 80h
0x180a28285  xor     r12d, r12d
0x180a28288  mov     r15, rdx
0x180a2828b  mov     [rbp+arg_10], r12d
0x180a2828f  mov     r14, rcx
0x180a28292  mov     [rbp+var_20], r12
0x180a28296  call    cs:__imp_GetCurrentThreadId
0x180a2829c  lea     r9, [rbp+var_20]
0x180a282a0  mov     ecx, 203h
0x180a282a5  mov     edx, eax
0x180a282a7  lea     r8, [rbp+arg_10]
0x180a282ab  call    cs:__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z; LCIEGetTypedComponentFromThread(ulong,ulong,ulong *,_IsoComponent * *)
0x180a282b1  test    eax, eax
0x180a282b3  js      loc_180A285A5
0x180a282b9  mov     rcx, [rbp+var_20]
0x180a282bd  mov     ebx, 30014h
0x180a282c2  xor     r9d, r9d
0x180a282c5  mov     edx, ebx
0x180a282c7  mov     r8d, [rcx+10Ch]
0x180a282ce  call    cs:__imp_?IsoInProcessData@@YAPEAXPEAU_IsoArtifact@@KKPEAX@Z; IsoInProcessData(_IsoArtifact *,ulong,ulong,void *)
0x180a282d4  test    rax, rax
0x180a282d7  jz      loc_180A285A5
0x180a282dd  mov     rcx, [rbp+var_20]
0x180a282e1  xor     r9d, r9d
0x180a282e4  mov     [rbp+ppvOut], r12
0x180a282e8  mov     edx, ebx
0x180a282ea  mov     [rbp+punk], r12
0x180a282ee  mov     r8d, [rcx+10Ch]
0x180a282f5  call    cs:__imp_?IsoInProcessData@@YAPEAXPEAU_IsoArtifact@@KKPEAX@Z; IsoInProcessData(_IsoArtifact *,ulong,ulong,void *)
0x180a282fb  mov     r9, rax
0x180a282fe  lea     r8, [rbp+punk]
0x180a28302  lea     rdx, _GUID_d8d2dda0_fd33_4b6a_9a67_e8c9fb471034
0x180a28309  mov     rcx, [rax]
0x180a2830c  mov     rax, [rcx]
0x180a2830f  mov     rcx, r9
0x180a28312  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180a28317  test    eax, eax
0x180a28319  js      short loc_180A2835C
0x180a2831b  mov     rcx, [rbp+punk]; punk
0x180a2831f  lea     r9, [rbp+ppvOut]; ppvOut
0x180a28323  lea     r8, _GUID_5a625ea4_a89f_4eb2_a45a_9ad4e37d4b00; riid
0x180a2832a  lea     rdx, IID_IWebBrowserApp; guidService
0x180a28331  call    cs:__imp_IUnknown_QueryService
0x180a28337  mov     rcx, [rbp+punk]
0x180a2833b  xor     r8d, r8d
0x180a2833e  xor     edx, edx
0x180a28340  mov     rax, [rcx]
0x180a28343  mov     rax, [rax+18h]
0x180a28347  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180a2834c  mov     rcx, [rbp+punk]
0x180a28350  mov     rax, [rcx]
0x180a28353  mov     rax, [rax+10h]
0x180a28357  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180a2835c  mov     rcx, cs:g_hProcessHeap
0x180a28363  mov     edx, 0B0h
0x180a28368  mov     ebx, 8007000Eh
0x180a2836d  call    ??$HeapAlloc@$0A@@MemoryProtection@@YAPEAXPEAX_K@Z; MemoryProtection::HeapAlloc<0>(void *,unsigned __int64)
0x180a28372  mov     rdi, rax
0x180a28375  test    rax, rax
0x180a28378  jz      loc_180A28593
0x180a2837e  lea     rcx, [rax+20h]; void *
0x180a28382  mov     [rax], r12
0x180a28385  xor     edx, edx; Val
0x180a28387  mov     [rax+8], r12d
0x180a2838b  mov     r8d, 90h; Size
0x180a28391  mov     [rax+10h], r12
0x180a28395  mov     [rax+18h], r12
0x180a28399  call    memset_0
0x180a2839e  mov     ecx, [rbp+arg_10]
0x180a283a1  mov     [rdi], ecx
0x180a283a3  call    cs:__imp_GetCurrentThreadId
0x180a283a9  mov     [rdi+8], eax
0x180a283ac  mov     dword ptr [rdi+4], 8004000h
0x180a283b3  mov     rax, [r14+50h]
0x180a283b7  mov     rcx, [rax+70h]
0x180a283bb  test    rcx, rcx
0x180a283be  jz      loc_180A28582
0x180a283c4  mov     rsi, [rcx+160h]
0x180a283cb  test    rsi, rsi
0x180a283ce  jz      loc_180A28582
0x180a283d4  mov     rbx, [rcx+88h]
0x180a283db  mov     rax, 200000000000000h
0x180a283e5  lea     rcx, [rdi+78h]; pvarg
0x180a283e9  and     rbx, rax
0x180a283ec  call    cs:__imp_VariantInit
0x180a283f2  lea     rax, [rdi+20h]
0x180a283f6  mov     r9, rsi; struct COmWindowProxy *
0x180a283f9  mov     [rsp+80h+var_40], rax; struct _BROKER_BIND_INFO *
0x180a283fe  mov     r8, r14; struct CDwnBindInfo *
0x180a28401  mov     [rsp+80h+var_48], r12; unsigned __int16 *
0x180a28406  mov     rdx, r15; unsigned __int16 *
0x180a28409  mov     [rsp+80h+var_50], r12; unsigned __int16 *
0x180a2840e  mov     rcx, r15; unsigned __int16 *
0x180a28411  mov     [rsp+80h+lpThreadId], r12; unsigned __int16 *
0x180a28416  mov     qword ptr [rsp+80h+dwCreationFlags], rbx; unsigned __int64
0x180a2841b  call    ?SetBrokerBindInfoForRedirectToBroker@@YAJPEBG0PEAVCDwnBindInfo@@PEAVCOmWindowProxy@@_K000PEAU_BROKER_BIND_INFO@@@Z; SetBrokerBindInfoForRedirectToBroker(ushort const *,ushort const *,CDwnBindInfo *,COmWindowProxy *,unsigned __int64,ushort const *,ushort const *,ushort const *,_BROKER_BIND_INFO *)
0x180a28420  mov     ebx, eax
0x180a28422  test    eax, eax
0x180a28424  js      loc_180A2857E
0x180a2842a  mov     rax, [r14+50h]
0x180a2842e  mov     ebx, 80004005h
0x180a28433  mov     esi, ebx
0x180a28435  mov     rcx, [rax+68h]
0x180a28439  test    rcx, rcx
0x180a2843c  jz      loc_180A2857C
0x180a28442  mov     rcx, [rcx+40h]
0x180a28446  test    rcx, rcx
0x180a28449  jz      loc_180A2857C
0x180a2844f  mov     [rbp+pUnk], r12
0x180a28453  lea     r8, [rbp+pUnk]
0x180a28457  mov     rax, [rcx]
0x180a2845a  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180a28461  mov     rax, [rax]
0x180a28464  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180a28469  mov     esi, eax
0x180a2846b  test    eax, eax
0x180a2846d  js      loc_180A2857C
0x180a28473  mov     rdx, [rbp+pUnk]; pUnk
0x180a28477  lea     r15, [rdi+10h]
0x180a2847b  mov     r8, r15; ppStm
0x180a2847e  lea     rcx, IID_IUnknown; riid
0x180a28485  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x180a2848b  mov     rcx, [rbp+pUnk]
0x180a2848f  mov     esi, eax
0x180a28491  mov     rax, [rcx]
0x180a28494  mov     rax, [rax+10h]
0x180a28498  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180a2849d  test    esi, esi
0x180a2849f  js      loc_180A2857C
0x180a284a5  mov     rdx, [rbp+ppvOut]; pUnk
0x180a284a9  test    rdx, rdx
0x180a284ac  jz      short loc_180A284BF
0x180a284ae  lea     r8, [rdi+18h]; ppStm
0x180a284b2  lea     rcx, IID_IXMicTestMode; riid
0x180a284b9  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x180a284bf  mov     rax, [r14+50h]
0x180a284c3  test    rax, rax
0x180a284c6  jz      short loc_180A284E4
0x180a284c8  mov     rcx, [rax+68h]
0x180a284cc  test    rcx, rcx
0x180a284cf  jz      short loc_180A284E4
0x180a284d1  mov     edx, 3038E7F1h
0x180a284d6  call    ?CheckBFCacheCandidacy@CDoc@@QEAA?AW4tagBFCACHE_CANDIDACY_FAILURE_FLAGS@@W42@@Z; CDoc::CheckBFCacheCandidacy(tagBFCACHE_CANDIDACY_FAILURE_FLAGS)
0x180a284db  test    eax, eax
0x180a284dd  jnz     short loc_180A284E4
0x180a284df  bts     dword ptr [rdi+4], 12h
0x180a284e4  mov     [rsp+80h+lpThreadId], r12; lpThreadId
0x180a284e9  lea     r8, ?BrokerRedirectUrlThreadProc@@YAKPEAX@Z; lpStartAddress
0x180a284f0  mov     r9, rdi; lpParameter
0x180a284f3  mov     [rsp+80h+dwCreationFlags], r12d; dwCreationFlags
0x180a284f8  xor     edx, edx; dwStackSize
0x180a284fa  xor     ecx, ecx; lpThreadAttributes
0x180a284fc  call    cs:__imp_CreateThread
0x180a28502  test    rax, rax
0x180a28505  jz      short loc_180A28515
0x180a28507  mov     rcx, rax; hObject
0x180a2850a  call    cs:__imp_CloseHandle
0x180a28510  mov     ebx, r12d
0x180a28513  jmp     short loc_180A28593
0x180a28515  mov     rcx, [r15]; pStm
0x180a28518  lea     r8, [rbp+ppv]; ppv
0x180a2851c  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; iid
0x180a28523  mov     [rbp+ppv], r12
0x180a28527  call    cs:__imp_CoGetInterfaceAndReleaseStream
0x180a2852d  test    eax, eax
0x180a2852f  js      short loc_180A28541
0x180a28531  mov     rcx, [rbp+ppv]
0x180a28535  mov     rax, [rcx]
0x180a28538  mov     rax, [rax+10h]
0x180a2853c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180a28541  mov     rcx, [rdi+18h]; pStm
0x180a28545  mov     [r15], r12
0x180a28548  mov     [rbp+pUnk], r12
0x180a2854c  test    rcx, rcx
0x180a2854f  jz      short loc_180A28576
0x180a28551  lea     r8, [rbp+pUnk]; ppv
0x180a28555  lea     rdx, _GUID_5a625ea4_a89f_4eb2_a45a_9ad4e37d4b00; iid
0x180a2855c  call    cs:__imp_CoGetInterfaceAndReleaseStream
0x180a28562  test    eax, eax
0x180a28564  js      short loc_180A28576
0x180a28566  mov     rcx, [rbp+pUnk]
0x180a2856a  mov     rax, [rcx]
0x180a2856d  mov     rax, [rax+10h]
0x180a28571  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180a28576  mov     [rdi+18h], r12
0x180a2857a  jmp     short loc_180A28582
0x180a2857c  mov     ebx, esi
0x180a2857e  test    ebx, ebx
0x180a28580  jz      short loc_180A28593
0x180a28582  lea     rcx, [rdi+20h]; struct _BROKER_BIND_INFO *
0x180a28586  call    ?ClearBrokerBindInfo@@YAXPEAU_BROKER_BIND_INFO@@@Z; ClearBrokerBindInfo(_BROKER_BIND_INFO *)
0x180a2858b  mov     rcx, rdi; this
0x180a2858e  call    ??_GCSize@@QEAAPEAXI@Z; CSize::`scalar deleting destructor'(uint)
0x180a28593  mov     rcx, [rbp+ppvOut]
0x180a28597  test    rcx, rcx
0x180a2859a  jz      loc_180A286EC
0x180a285a0  jmp     loc_180A286E0
0x180a285a5  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x180a285ab  test    al, al
0x180a285ad  jz      short loc_180A285B5
0x180a285af  call    ?AssertionFailed@Abandonment@@SAXXZ; Abandonment::AssertionFailed(void)
0x180a285b5  call    cs:__imp_GetCurrentProcessId
0x180a285bb  mov     ecx, 1
0x180a285c0  call    cs:__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z; IsoGetIntegrity(ulong)
0x180a285c6  mov     ecx, 20000011h
0x180a285cb  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x180a285d1  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180a285d7  lea     rcx, [rbp+pUnk]
0x180a285db  mov     [rbp+ppvOut], r12
0x180a285df  mov     [rbp+pUnk], r12
0x180a285e3  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x180a285e9  mov     ebx, eax
0x180a285eb  test    eax, eax
0x180a285ed  js      loc_180A286EC
0x180a285f3  mov     rcx, [rbp+pUnk]
0x180a285f7  lea     r9, [rbp+punk]
0x180a285fb  mov     dword ptr [rbp+punk], r12d
0x180a285ff  xor     r8d, r8d
0x180a28602  xor     edx, edx
0x180a28604  mov     rax, [rcx]
0x180a28607  mov     rax, [rax+18h]
0x180a2860b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180a28610  mov     eax, dword ptr [rbp+punk]
0x180a28613  or      ecx, 0FFFFFFFFh
0x180a28616  test    eax, eax
0x180a28618  cmovnz  ecx, eax; dwProcessId
0x180a2861b  call    cs:__imp_AllowSetForegroundWindow
0x180a28621  mov     rcx, [rbp+pUnk]
0x180a28625  lea     r9, [rbp+ppv]
0x180a28629  mov     [rbp+ppv], r12
0x180a2862d  lea     r8, IID_IUnknown
0x180a28634  lea     rdx, CLSID_CShdocvwBroker
0x180a2863b  mov     rax, [rcx]
0x180a2863e  mov     rax, [rax+30h]
0x180a28642  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180a28647  mov     ebx, eax
0x180a28649  test    eax, eax
0x180a2864b  js      short loc_180A28679
0x180a2864d  mov     rcx, [rbp+ppv]
0x180a28651  lea     r8, [rbp+ppvOut]
0x180a28655  lea     rdx, _GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42
0x180a2865c  mov     rax, [rcx]
0x180a2865f  mov     rax, [rax]
0x180a28662  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180a28667  mov     rcx, [rbp+ppv]
0x180a2866b  mov     ebx, eax
0x180a2866d  mov     rax, [rcx]
0x180a28670  mov     rax, [rax+10h]
0x180a28674  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180a28679  mov     rcx, [rbp+pUnk]
0x180a2867d  mov     rax, [rcx]
0x180a28680  mov     rax, [rax+10h]
0x180a28684  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180a28689  test    ebx, ebx
0x180a2868b  js      short loc_180A286EC
0x180a2868d  mov     rax, [rbp+ppvOut]
0x180a28691  mov     rcx, [rax]
0x180a28694  mov     rbx, [rcx+4E8h]
0x180a2869b  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180a286a1  mov     rcx, [rbp+ppvOut]
0x180a286a5  lea     rdx, [rbp+ppv]
0x180a286a9  movups  xmm0, xmmword ptr [rax]
0x180a286ac  mov     rax, rbx
0x180a286af  movdqu  xmmword ptr [rbp+ppv], xmm0
0x180a286b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180a286b9  mov     rcx, [rbp+ppvOut]
0x180a286bd  xor     r9d, r9d
0x180a286c0  mov     r8d, 800h
0x180a286c6  mov     qword ptr [rsp+80h+dwCreationFlags], r12
0x180a286cb  mov     rdx, r15
0x180a286ce  mov     rax, [rcx]
0x180a286d1  mov     rax, [rax+18h]
0x180a286d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180a286da  mov     rcx, [rbp+ppvOut]
0x180a286de  mov     ebx, eax
0x180a286e0  mov     rax, [rcx]
0x180a286e3  mov     rax, [rax+10h]
0x180a286e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180a286ec  lea     r11, [rsp+80h+var_s0]
0x180a286f4  mov     eax, ebx
0x180a286f6  mov     rbx, [r11+30h]
0x180a286fa  mov     rsi, [r11+38h]
0x180a286fe  mov     rsp, r11
0x180a28701  pop     r15
0x180a28703  pop     r14
0x180a28705  pop     r12
0x180a28707  pop     rdi
0x180a28708  pop     rbp
0x180a28709  retn
```
