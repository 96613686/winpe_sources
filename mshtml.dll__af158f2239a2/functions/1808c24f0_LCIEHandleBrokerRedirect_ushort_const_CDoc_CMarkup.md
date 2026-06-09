# LCIEHandleBrokerRedirect(ushort const *,CDoc *,CMarkup *)

- ea: `0x1808c24f0`
- end: `0x1808c294b`
- name: `?LCIEHandleBrokerRedirect@@YAJPEBGPEAVCDoc@@PEAVCMarkup@@@Z`
- size: `1115`
- prototype: `__int64 __fastcall(OLECHAR *psz, struct CDoc *this, struct CMarkup *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180826508`

## callees

- `0x1801bf528`
- `0x18020f6f8`
- `0x1807c0050`
- `0x1808c1410`
- `0x1808c24f0`
- `0x1810c2d60`
- `0x1810d1010`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x1808c27dc`
- `KERNEL32!GetCurrentProcessId` at `0x1808c27dc`
- `KERNEL32!GetCurrentThreadId` at `0x1808c2527`
- `KERNEL32!GetCurrentThreadId` at `0x1808c2627`
- `KERNEL32!GetCurrentThreadId` at `0x1808c2527`
- `KERNEL32!GetCurrentThreadId` at `0x1808c2627`
- `KERNEL32!CreateThread` at `0x1808c2703`
- `KERNEL32!CreateThread` at `0x1808c2703`
- `KERNEL32!CloseHandle` at `0x1808c2711`
- `KERNEL32!CloseHandle` at `0x1808c2711`
- `USER32!AllowSetForegroundWindow` at `0x1808c2857`
- `USER32!AllowSetForegroundWindow` at `0x1808c2857`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1808c281f`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1808c281f`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x1808c27fc`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x1808c27fc`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1808c27a3`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1808c27a3`
- `api-ms-win-downlevel-ole32-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x1808c272e`
- `api-ms-win-downlevel-ole32-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x1808c2763`
- `api-ms-win-downlevel-ole32-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x1808c272e`
- `api-ms-win-downlevel-ole32-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x1808c2763`
- `api-ms-win-downlevel-ole32-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x1808c26b1`
- `api-ms-win-downlevel-ole32-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x1808c26e5`
- `api-ms-win-downlevel-ole32-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x1808c26b1`
- `api-ms-win-downlevel-ole32-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x1808c26e5`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IUnknown_QueryService` at `0x1808c25c2`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IUnknown_QueryService` at `0x1808c25c2`
- `msIso!__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z` at `0x1808c253c`
- `msIso!__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z` at `0x1808c253c`
- `msIso!__imp_?IsoInProcessData@@YAPEAXPEAU_IsoArtifact@@KKPEAX@Z` at `0x1808c255f`
- `msIso!__imp_?IsoInProcessData@@YAPEAXPEAU_IsoArtifact@@KKPEAX@Z` at `0x1808c2586`
- `msIso!__imp_?IsoInProcessData@@YAPEAXPEAU_IsoArtifact@@KKPEAX@Z` at `0x1808c255f`
- `msIso!__imp_?IsoInProcessData@@YAPEAXPEAU_IsoArtifact@@KKPEAX@Z` at `0x1808c2586`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1808c2805`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1808c28d7`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1808c2805`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1808c28d7`
- `msIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x1808c27e7`
- `msIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x1808c27e7`
- `OLEAUT32!__imp_SysAllocString` at `0x1808c2633`
- `OLEAUT32!__imp_SysAllocString` at `0x1808c2633`

## pseudocode

```c
__int64 __fastcall LCIEHandleBrokerRedirect(OLECHAR *psz, struct CDoc *this, struct CMarkup *a3)
{
  DWORD CurrentThreadId; // eax
  int (__fastcall ***v6)(void *, GUID *, IUnknown **); // rax
  int UserBroker; // edi
  __int64 v8; // rax
  __int64 v9; // rbx
  BSTR v10; // rax
  unsigned int v11; // edx
  struct CDoc *CDoc; // rax
  HRESULT v13; // esi
  __int64 (__fastcall ***v14)(_QWORD, GUID *, LPUNKNOWN *); // rcx
  IStream **v15; // r14
  HANDLE Thread; // rax
  IStream *v17; // rcx
  IStream *v18; // rcx
  void *v19; // rcx
  DWORD v20; // ecx
  ULONG (__stdcall *AddRef)(IUnknown *); // rbx
  int v22; // eax
  LPUNKNOWN pUnk; // [rsp+30h] [rbp-69h] BYREF
  IUnknown *punk; // [rsp+38h] [rbp-61h] BYREF
  void *ppvOut; // [rsp+40h] [rbp-59h] BYREF
  unsigned int v27; // [rsp+48h] [rbp-51h] BYREF
  LPVOID ppv[2]; // [rsp+50h] [rbp-49h] BYREF
  struct _IsoComponent *v29; // [rsp+60h] [rbp-39h] BYREF
  int v30; // [rsp+70h] [rbp-29h] BYREF
  __int64 v31; // [rsp+74h] [rbp-25h]
  int v32; // [rsp+7Ch] [rbp-1Dh]
  __int64 v33; // [rsp+80h] [rbp-19h]
  __int128 v34; // [rsp+88h] [rbp-11h]
  _DWORD v35[10]; // [rsp+98h] [rbp-1h] BYREF

  v27 = 0;
  v29 = 0;
  CurrentThreadId = GetCurrentThreadId();
  if ( (int)LCIEGetTypedComponentFromThread(0x203u, CurrentThreadId, &v27, &v29) >= 0
    && IsoInProcessData(v29, 0x30014u, *((_DWORD *)v29 + 67), 0) )
  {
    ppvOut = 0;
    punk = 0;
    v6 = (int (__fastcall ***)(void *, GUID *, IUnknown **))IsoInProcessData(v29, 0x30014u, *((_DWORD *)v29 + 67), 0);
    if ( (**v6)(v6, &GUID_d8d2dda0_fd33_4b6a_9a67_e8c9fb471034, &punk) >= 0 )
    {
      IUnknown_QueryService(punk, &IID_IWebBrowserApp, &GUID_5a625ea4_a89f_4eb2_a45a_9ad4e37d4b00, &ppvOut);
      ((void (__fastcall *)(IUnknown *, _QWORD, _QWORD))punk->lpVtbl[1].QueryInterface)(punk, 0, 0);
      ((void (__fastcall *)(IUnknown *))punk->lpVtbl->Release)(punk);
    }
    UserBroker = -2147024882;
    v8 = MemoryProtection::HeapAlloc<0>(g_hProcessHeap, 40);
    v9 = v8;
    if ( v8 )
    {
      *(_DWORD *)v8 = 0;
      *(_QWORD *)(v8 + 8) = 0;
      *(_DWORD *)(v8 + 16) = 0;
      *(_QWORD *)(v8 + 24) = 0;
      *(_QWORD *)(v8 + 32) = 0;
      *(_DWORD *)v8 = v27;
      *(_DWORD *)(v8 + 16) = GetCurrentThreadId();
      v10 = SysAllocString(psz);
      *(_DWORD *)(v9 + 4) = 0x4000;
      *(_QWORD *)(v9 + 8) = v10;
      if ( this && v10 )
      {
        CDoc = CBase::GetCDoc(this);
        UserBroker = -2147467259;
        v13 = -2147467259;
        if ( CDoc
          && (v14 = (__int64 (__fastcall ***)(_QWORD, GUID *, LPUNKNOWN *))*((_QWORD *)CDoc + 8)) != 0
          && (pUnk = 0, v13 = (**v14)(v14, &GUID_00000000_0000_0000_c000_000000000046, &pUnk), v13 >= 0)
          && (v15 = (IStream **)(v9 + 24),
              v13 = CoMarshalInterThreadInterfaceInStream(&IID_IUnknown, pUnk, (LPSTREAM *)(v9 + 24)),
              ((void (__fastcall *)(LPUNKNOWN))pUnk->lpVtbl->Release)(pUnk),
              v13 >= 0) )
        {
          if ( ppvOut )
            CoMarshalInterThreadInterfaceInStream(&IID_IXMicTestMode, (LPUNKNOWN)ppvOut, (LPSTREAM *)(v9 + 32));
          Thread = CreateThread(0, 0, LCIEBrokerRedirectUrlThreadProc, (LPVOID)v9, 0, 0);
          if ( Thread )
          {
            CloseHandle(Thread);
            UserBroker = 0;
            goto LABEL_24;
          }
          v17 = *v15;
          ppv[0] = 0;
          if ( CoGetInterfaceAndReleaseStream(v17, &GUID_00000000_0000_0000_c000_000000000046, ppv) >= 0 )
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv[0] + 16LL))(ppv[0]);
          v18 = *(IStream **)(v9 + 32);
          *v15 = 0;
          pUnk = 0;
          if ( v18
            && CoGetInterfaceAndReleaseStream(v18, &GUID_5a625ea4_a89f_4eb2_a45a_9ad4e37d4b00, (LPVOID *)&pUnk) >= 0 )
          {
            ((void (__fastcall *)(LPUNKNOWN))pUnk->lpVtbl->Release)(pUnk);
          }
          *(_QWORD *)(v9 + 32) = 0;
        }
        else
        {
          UserBroker = v13;
        }
      }
      LCIESRedirectUrlInfo::`scalar deleting destructor'((LCIESRedirectUrlInfo *)v9, v11);
    }
LABEL_24:
    v19 = ppvOut;
    if ( ppvOut )
      goto LABEL_35;
    return (unsigned int)UserBroker;
  }
  if ( IsDualEngineProcess() )
    Abandonment::AssertionFailed();
  v30 = 0;
  memset(v35, 0, 28);
  v32 = 0;
  v31 = 2048;
  v33 = 1;
  v34 = 0;
  LODWORD(v34) = GetCurrentProcessId();
  *(_QWORD *)((char *)&v34 + 4) = IsoGetIntegrity(1) & 0x7F;
  v35[0] = IEConfiguration_GetDWORD(536870929);
  punk = 0;
  pUnk = 0;
  *(_OWORD *)&v35[3] = *(_OWORD *)GlobalThreadState();
  UserBroker = CoCreateUserBroker((struct IEUserBroker **)&pUnk);
  if ( UserBroker >= 0 )
  {
    LODWORD(ppvOut) = 0;
    ((void (__fastcall *)(LPUNKNOWN, _QWORD, _QWORD, void **))pUnk->lpVtbl[1].QueryInterface)(pUnk, 0, 0, &ppvOut);
    v20 = -1;
    if ( (_DWORD)ppvOut )
      v20 = (unsigned int)ppvOut;
    AllowSetForegroundWindow(v20);
    ppv[0] = 0;
    UserBroker = ((__int64 (__fastcall *)(LPUNKNOWN, GUID *, GUID *, LPVOID *))pUnk->lpVtbl[2].QueryInterface)(
                   pUnk,
                   &CLSID_CShdocvwBroker,
                   &IID_IUnknown,
                   ppv);
    if ( UserBroker >= 0 )
    {
      UserBroker = (**(__int64 (__fastcall ***)(LPVOID, GUID *, IUnknown **))ppv[0])(
                     ppv[0],
                     &GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42,
                     &punk);
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv[0] + 16LL))(ppv[0]);
    }
    ((void (__fastcall *)(LPUNKNOWN))pUnk->lpVtbl->Release)(pUnk);
    if ( UserBroker >= 0 )
    {
      AddRef = punk->lpVtbl[52].AddRef;
      *(_OWORD *)ppv = *(_OWORD *)GlobalThreadState();
      ((void (__fastcall *)(IUnknown *, LPVOID *))AddRef)(punk, ppv);
      v22 = ((__int64 (__fastcall *)(IUnknown *, OLECHAR *, __int64, int *, _QWORD))punk->lpVtbl[1].QueryInterface)(
              punk,
              psz,
              2048,
              &v30,
              0);
      v19 = punk;
      UserBroker = v22;
LABEL_35:
      (*(void (__fastcall **)(void *))(*(_QWORD *)v19 + 16LL))(v19);
    }
  }
  return (unsigned int)UserBroker;
}

```

## disassembly

```asm
0x1808c24f0  mov     [rsp-8+arg_10], rbx
0x1808c24f5  push    rbp
0x1808c24f6  push    rsi
0x1808c24f7  push    rdi
0x1808c24f8  push    r14
0x1808c24fa  push    r15
0x1808c24fc  lea     rbp, [rsp-37h]
0x1808c2501  sub     rsp, 0D0h
0x1808c2508  mov     rax, cs:__security_cookie
0x1808c250f  xor     rax, rsp
0x1808c2512  mov     [rbp+57h+var_30], rax
0x1808c2516  xor     r15d, r15d
0x1808c2519  mov     rsi, rdx
0x1808c251c  mov     [rbp+57h+var_A8], r15d
0x1808c2520  mov     r14, rcx
0x1808c2523  mov     [rbp+57h+var_90], r15
0x1808c2527  call    cs:__imp_GetCurrentThreadId
0x1808c252d  lea     r9, [rbp+57h+var_90]
0x1808c2531  mov     ecx, 203h
0x1808c2536  mov     edx, eax
0x1808c2538  lea     r8, [rbp+57h+var_A8]
0x1808c253c  call    cs:__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z; LCIEGetTypedComponentFromThread(ulong,ulong,ulong *,_IsoComponent * *)
0x1808c2542  test    eax, eax
0x1808c2544  js      loc_1808C27A3
0x1808c254a  mov     rcx, [rbp+57h+var_90]
0x1808c254e  mov     ebx, 30014h
0x1808c2553  xor     r9d, r9d
0x1808c2556  mov     edx, ebx
0x1808c2558  mov     r8d, [rcx+10Ch]
0x1808c255f  call    cs:__imp_?IsoInProcessData@@YAPEAXPEAU_IsoArtifact@@KKPEAX@Z; IsoInProcessData(_IsoArtifact *,ulong,ulong,void *)
0x1808c2565  test    rax, rax
0x1808c2568  jz      loc_1808C27A3
0x1808c256e  mov     rcx, [rbp+57h+var_90]
0x1808c2572  xor     r9d, r9d
0x1808c2575  mov     [rbp+57h+ppvOut], r15
0x1808c2579  mov     edx, ebx
0x1808c257b  mov     [rbp+57h+punk], r15
0x1808c257f  mov     r8d, [rcx+10Ch]
0x1808c2586  call    cs:__imp_?IsoInProcessData@@YAPEAXPEAU_IsoArtifact@@KKPEAX@Z; IsoInProcessData(_IsoArtifact *,ulong,ulong,void *)
0x1808c258c  mov     r9, rax
0x1808c258f  lea     r8, [rbp+57h+punk]
0x1808c2593  lea     rdx, _GUID_d8d2dda0_fd33_4b6a_9a67_e8c9fb471034
0x1808c259a  mov     rcx, [rax]
0x1808c259d  mov     rax, [rcx]
0x1808c25a0  mov     rcx, r9
0x1808c25a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808c25a8  test    eax, eax
0x1808c25aa  js      short loc_1808C25ED
0x1808c25ac  mov     rcx, [rbp+57h+punk]; punk
0x1808c25b0  lea     r9, [rbp+57h+ppvOut]; ppvOut
0x1808c25b4  lea     r8, _GUID_5a625ea4_a89f_4eb2_a45a_9ad4e37d4b00; riid
0x1808c25bb  lea     rdx, IID_IWebBrowserApp; guidService
0x1808c25c2  call    cs:__imp_IUnknown_QueryService
0x1808c25c8  mov     rcx, [rbp+57h+punk]
0x1808c25cc  xor     r8d, r8d
0x1808c25cf  xor     edx, edx
0x1808c25d1  mov     rax, [rcx]
0x1808c25d4  mov     rax, [rax+18h]
0x1808c25d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808c25dd  mov     rcx, [rbp+57h+punk]
0x1808c25e1  mov     rax, [rcx]
0x1808c25e4  mov     rax, [rax+10h]
0x1808c25e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808c25ed  mov     rcx, cs:g_hProcessHeap
0x1808c25f4  mov     edx, 28h ; '('
0x1808c25f9  mov     edi, 8007000Eh
0x1808c25fe  call    ??$HeapAlloc@$0A@@MemoryProtection@@YAPEAXPEAX_K@Z; MemoryProtection::HeapAlloc<0>(void *,unsigned __int64)
0x1808c2603  mov     rbx, rax
0x1808c2606  test    rax, rax
0x1808c2609  jz      loc_1808C2791
0x1808c260f  mov     [rax], r15d
0x1808c2612  mov     [rax+8], r15
0x1808c2616  mov     [rax+10h], r15d
0x1808c261a  mov     [rax+18h], r15
0x1808c261e  mov     [rax+20h], r15
0x1808c2622  mov     edx, [rbp+57h+var_A8]
0x1808c2625  mov     [rax], edx
0x1808c2627  call    cs:__imp_GetCurrentThreadId
0x1808c262d  mov     rcx, r14; psz
0x1808c2630  mov     [rbx+10h], eax
0x1808c2633  call    cs:__imp_SysAllocString
0x1808c2639  mov     dword ptr [rbx+4], 4000h
0x1808c2640  mov     [rbx+8], rax
0x1808c2644  test    rsi, rsi
0x1808c2647  jz      loc_1808C2789
0x1808c264d  test    rax, rax
0x1808c2650  jz      loc_1808C2789
0x1808c2656  mov     rcx, rsi; this
0x1808c2659  call    ?GetCDoc@CBase@@QEAAPEAVCDoc@@XZ; CBase::GetCDoc(void)
0x1808c265e  mov     edi, 80004005h
0x1808c2663  mov     esi, edi
0x1808c2665  test    rax, rax
0x1808c2668  jz      loc_1808C2783
0x1808c266e  mov     rcx, [rax+40h]
0x1808c2672  test    rcx, rcx
0x1808c2675  jz      loc_1808C2783
0x1808c267b  mov     [rbp+57h+pUnk], r15
0x1808c267f  lea     r8, [rbp+57h+pUnk]
0x1808c2683  mov     rax, [rcx]
0x1808c2686  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x1808c268d  mov     rax, [rax]
0x1808c2690  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808c2695  mov     esi, eax
0x1808c2697  test    eax, eax
0x1808c2699  js      loc_1808C2783
0x1808c269f  mov     rdx, [rbp+57h+pUnk]; pUnk
0x1808c26a3  lea     r14, [rbx+18h]
0x1808c26a7  mov     r8, r14; ppStm
0x1808c26aa  lea     rcx, IID_IUnknown; riid
0x1808c26b1  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x1808c26b7  mov     rcx, [rbp+57h+pUnk]
0x1808c26bb  mov     esi, eax
0x1808c26bd  mov     rax, [rcx]
0x1808c26c0  mov     rax, [rax+10h]
0x1808c26c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808c26c9  test    esi, esi
0x1808c26cb  js      loc_1808C2783
0x1808c26d1  mov     rdx, [rbp+57h+ppvOut]; pUnk
0x1808c26d5  test    rdx, rdx
0x1808c26d8  jz      short loc_1808C26EB
0x1808c26da  lea     r8, [rbx+20h]; ppStm
0x1808c26de  lea     rcx, IID_IXMicTestMode; riid
0x1808c26e5  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x1808c26eb  mov     [rsp+0F0h+lpThreadId], r15; lpThreadId
0x1808c26f0  lea     r8, _LCIEBrokerRedirectUrlThreadProc; lpStartAddress
0x1808c26f7  mov     r9, rbx; lpParameter
0x1808c26fa  mov     [rsp+0F0h+dwCreationFlags], r15d; dwCreationFlags
0x1808c26ff  xor     edx, edx; dwStackSize
0x1808c2701  xor     ecx, ecx; lpThreadAttributes
0x1808c2703  call    cs:__imp_CreateThread
0x1808c2709  test    rax, rax
0x1808c270c  jz      short loc_1808C271C
0x1808c270e  mov     rcx, rax; hObject
0x1808c2711  call    cs:__imp_CloseHandle
0x1808c2717  mov     edi, r15d
0x1808c271a  jmp     short loc_1808C2791
0x1808c271c  mov     rcx, [r14]; pStm
0x1808c271f  lea     r8, [rbp+57h+ppv]; ppv
0x1808c2723  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; iid
0x1808c272a  mov     [rbp+57h+ppv], r15
0x1808c272e  call    cs:__imp_CoGetInterfaceAndReleaseStream
0x1808c2734  test    eax, eax
0x1808c2736  js      short loc_1808C2748
0x1808c2738  mov     rcx, [rbp+57h+ppv]
0x1808c273c  mov     rax, [rcx]
0x1808c273f  mov     rax, [rax+10h]
0x1808c2743  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808c2748  mov     rcx, [rbx+20h]; pStm
0x1808c274c  mov     [r14], r15
0x1808c274f  mov     [rbp+57h+pUnk], r15
0x1808c2753  test    rcx, rcx
0x1808c2756  jz      short loc_1808C277D
0x1808c2758  lea     r8, [rbp+57h+pUnk]; ppv
0x1808c275c  lea     rdx, _GUID_5a625ea4_a89f_4eb2_a45a_9ad4e37d4b00; iid
0x1808c2763  call    cs:__imp_CoGetInterfaceAndReleaseStream
0x1808c2769  test    eax, eax
0x1808c276b  js      short loc_1808C277D
0x1808c276d  mov     rcx, [rbp+57h+pUnk]
0x1808c2771  mov     rax, [rcx]
0x1808c2774  mov     rax, [rax+10h]
0x1808c2778  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808c277d  mov     [rbx+20h], r15
0x1808c2781  jmp     short loc_1808C2789
0x1808c2783  mov     edi, esi
0x1808c2785  test    esi, esi
0x1808c2787  jz      short loc_1808C2791
0x1808c2789  mov     rcx, rbx; this
0x1808c278c  call    ??_GLCIESRedirectUrlInfo@@QEAAPEAXI@Z; LCIESRedirectUrlInfo::`scalar deleting destructor'(uint)
0x1808c2791  mov     rcx, [rbp+57h+ppvOut]
0x1808c2795  test    rcx, rcx
0x1808c2798  jz      loc_1808C2926
0x1808c279e  jmp     loc_1808C291A
0x1808c27a3  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x1808c27a9  test    al, al
0x1808c27ab  jz      short loc_1808C27B3
0x1808c27ad  call    ?AssertionFailed@Abandonment@@SAXXZ; Abandonment::AssertionFailed(void)
0x1808c27b3  xorps   xmm0, xmm0
0x1808c27b6  mov     [rbp+57h+var_80], r15d
0x1808c27ba  movups  xmmword ptr [rbp+57h+var_58], xmm0
0x1808c27be  mov     esi, 800h
0x1808c27c3  mov     [rbp+57h+var_74], r15d
0x1808c27c7  mov     ebx, 1
0x1808c27cc  mov     [rbp+57h+var_7C], rsi
0x1808c27d0  movups  xmmword ptr [rbp+57h+var_58+0Ch], xmm0
0x1808c27d4  mov     [rbp+57h+var_70], rbx
0x1808c27d8  movups  [rbp+57h+var_68], xmm0
0x1808c27dc  call    cs:__imp_GetCurrentProcessId
0x1808c27e2  mov     ecx, ebx
0x1808c27e4  mov     dword ptr [rbp+57h+var_68], eax
0x1808c27e7  call    cs:__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z; IsoGetIntegrity(ulong)
0x1808c27ed  mov     ecx, 20000011h
0x1808c27f2  mov     dword ptr [rbp+57h+var_68+8], r15d
0x1808c27f6  and     eax, 7Fh
0x1808c27f9  mov     dword ptr [rbp+57h+var_68+4], eax
0x1808c27fc  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x1808c2802  mov     [rbp+57h+var_58], eax
0x1808c2805  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1808c280b  lea     rcx, [rbp+57h+pUnk]
0x1808c280f  mov     [rbp+57h+punk], r15
0x1808c2813  mov     [rbp+57h+pUnk], r15
0x1808c2817  movups  xmm0, xmmword ptr [rax]
0x1808c281a  movdqu  xmmword ptr [rbp+57h+var_58+0Ch], xmm0
0x1808c281f  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x1808c2825  mov     edi, eax
0x1808c2827  test    eax, eax
0x1808c2829  js      loc_1808C2926
0x1808c282f  mov     rcx, [rbp+57h+pUnk]
0x1808c2833  lea     r9, [rbp+57h+ppvOut]
0x1808c2837  mov     dword ptr [rbp+57h+ppvOut], r15d
0x1808c283b  xor     r8d, r8d
0x1808c283e  xor     edx, edx
0x1808c2840  mov     rax, [rcx]
0x1808c2843  mov     rax, [rax+18h]
0x1808c2847  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808c284c  mov     eax, dword ptr [rbp+57h+ppvOut]
0x1808c284f  or      ecx, 0FFFFFFFFh
0x1808c2852  test    eax, eax
0x1808c2854  cmovnz  ecx, eax; dwProcessId
0x1808c2857  call    cs:__imp_AllowSetForegroundWindow
0x1808c285d  mov     rcx, [rbp+57h+pUnk]
0x1808c2861  lea     r9, [rbp+57h+ppv]
0x1808c2865  mov     [rbp+57h+ppv], r15
0x1808c2869  lea     r8, IID_IUnknown
0x1808c2870  lea     rdx, CLSID_CShdocvwBroker
0x1808c2877  mov     rax, [rcx]
0x1808c287a  mov     rax, [rax+30h]
0x1808c287e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808c2883  mov     edi, eax
0x1808c2885  test    eax, eax
0x1808c2887  js      short loc_1808C28B5
0x1808c2889  mov     rcx, [rbp+57h+ppv]
0x1808c288d  lea     r8, [rbp+57h+punk]
0x1808c2891  lea     rdx, _GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42
0x1808c2898  mov     rax, [rcx]
0x1808c289b  mov     rax, [rax]
0x1808c289e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808c28a3  mov     rcx, [rbp+57h+ppv]
0x1808c28a7  mov     edi, eax
0x1808c28a9  mov     rax, [rcx]
0x1808c28ac  mov     rax, [rax+10h]
0x1808c28b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808c28b5  mov     rcx, [rbp+57h+pUnk]
0x1808c28b9  mov     rax, [rcx]
0x1808c28bc  mov     rax, [rax+10h]
0x1808c28c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808c28c5  test    edi, edi
0x1808c28c7  js      short loc_1808C2926
0x1808c28c9  mov     rax, [rbp+57h+punk]
0x1808c28cd  mov     rcx, [rax]
0x1808c28d0  mov     rbx, [rcx+4E8h]
0x1808c28d7  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1808c28dd  mov     rcx, [rbp+57h+punk]
0x1808c28e1  lea     rdx, [rbp+57h+ppv]
0x1808c28e5  movups  xmm0, xmmword ptr [rax]
0x1808c28e8  mov     rax, rbx
0x1808c28eb  movdqu  xmmword ptr [rbp+57h+ppv], xmm0
0x1808c28f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808c28f5  mov     rcx, [rbp+57h+punk]
0x1808c28f9  lea     r9, [rbp+57h+var_80]
0x1808c28fd  mov     r8d, esi
0x1808c2900  mov     qword ptr [rsp+0F0h+dwCreationFlags], r15
0x1808c2905  mov     rdx, r14
0x1808c2908  mov     rax, [rcx]
0x1808c290b  mov     rax, [rax+18h]
0x1808c290f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808c2914  mov     rcx, [rbp+57h+punk]
0x1808c2918  mov     edi, eax
0x1808c291a  mov     rax, [rcx]
0x1808c291d  mov     rax, [rax+10h]
0x1808c2921  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808c2926  mov     eax, edi
0x1808c2928  mov     rcx, [rbp+57h+var_30]
0x1808c292c  xor     rcx, rsp; StackCookie
0x1808c292f  call    __security_check_cookie
0x1808c2934  mov     rbx, [rsp+0F0h+arg_10]
0x1808c293c  add     rsp, 0D0h
0x1808c2943  pop     r15
0x1808c2945  pop     r14
0x1808c2947  pop     rdi
0x1808c2948  pop     rsi
0x1808c2949  pop     rbp
0x1808c294a  retn
```
