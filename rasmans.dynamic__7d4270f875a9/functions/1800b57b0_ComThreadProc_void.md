# ComThreadProc(void *)

- ea: `0x1800b57b0`
- end: `0x1800b63b9`
- name: `?ComThreadProc@@YAKPEAX@Z`
- size: `3081`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800039ac`
- `0x180005bcc`
- `0x180005bfc`
- `0x180033b38`
- `0x1800b57b0`
- `0x1800b7f3c`
- `0x1800b9a80`
- `0x1800e8e96`
- `0x1800e8ef0`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b58f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b5973`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b59d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b61d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b58f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b5973`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b59d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b61d5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800b5dfd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800b619f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800b5dfd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800b619f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800b6146`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800b6146`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800b5a33`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800b5f18`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800b5a33`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800b5f18`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800b587b`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800b587b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800b634d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800b634d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800b6327`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800b633b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800b6327`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800b633b`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800b58de`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800b58de`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800b595a`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800b595a`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x1800b59c2`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x1800b6181`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x1800b59c2`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x1800b6181`

## string_xrefs

- `0x1800b58ce`: `ServicesActive`

## pseudocode

```c
__int64 __fastcall ComThreadProc(PVOID Parameter)
{
  struct IConnectionPoint *v1; // rdi
  struct IConnectionPoint *v2; // r13
  struct IConnectionPoint *v3; // r12
  _DWORD *v4; // rbx
  _DWORD *v5; // r15
  _DWORD *v6; // rsi
  SC_HANDLE v7; // r14
  HRESULT v8; // eax
  SC_HANDLE v9; // rax
  int LastError; // eax
  struct _LIST_ENTRY *v11; // rcx
  __int64 v12; // rdx
  SC_HANDLE v13; // rax
  int v14; // eax
  struct _LIST_ENTRY *v15; // rcx
  __int64 v16; // rdx
  _QWORD *v17; // rax
  _DWORD *v18; // rax
  struct _LIST_ENTRY *v19; // rcx
  _QWORD *v20; // rax
  int v21; // esi
  int v22; // r14d
  int Instance; // eax
  unsigned int ConnectionPoints; // eax
  unsigned int v25; // r14d
  struct _LIST_ENTRY *v26; // rcx
  __int64 v27; // rdx
  unsigned int v28; // eax
  unsigned int v29; // edi
  struct _LIST_ENTRY *v30; // rcx
  __int64 v31; // rdx
  unsigned int v32; // eax
  unsigned int v33; // esi
  unsigned int v34; // eax
  struct _LIST_ENTRY *v35; // rcx
  __int64 v36; // rdx
  unsigned int v37; // eax
  unsigned int v38; // edi
  struct _LIST_ENTRY *v39; // rcx
  __int64 v40; // rdx
  struct IConnectionPoint *v42; // [rsp+38h] [rbp-C8h]
  __int16 v43; // [rsp+40h] [rbp-C0h] BYREF
  struct INetworkListManager *ppv; // [rsp+48h] [rbp-B8h] BYREF
  int v45; // [rsp+50h] [rbp-B0h]
  int v46; // [rsp+54h] [rbp-ACh]
  int v47; // [rsp+58h] [rbp-A8h]
  unsigned int v48; // [rsp+5Ch] [rbp-A4h] BYREF
  unsigned int v49; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v50; // [rsp+64h] [rbp-9Ch] BYREF
  struct IConnectionPoint *v51; // [rsp+68h] [rbp-98h] BYREF
  _DWORD *v52; // [rsp+70h] [rbp-90h]
  SC_HANDLE hService; // [rsp+78h] [rbp-88h]
  int v54; // [rsp+80h] [rbp-80h] BYREF
  struct IConnectionPoint *v55; // [rsp+88h] [rbp-78h] BYREF
  struct IConnectionPoint *v56; // [rsp+90h] [rbp-70h] BYREF
  __int64 v57; // [rsp+98h] [rbp-68h] BYREF
  __int64 v58; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v59; // [rsp+A8h] [rbp-58h] BYREF
  SERVICE_NOTIFY_2W pNotifyBuffer; // [rsp+B0h] [rbp-50h] BYREF

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 152, &WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids);
  v43 = 0;
  v1 = 0;
  v51 = 0;
  v2 = 0;
  v55 = 0;
  v3 = 0;
  v56 = 0;
  ppv = 0;
  v4 = 0;
  v5 = 0;
  v57 = 0;
  v6 = 0;
  v58 = 0;
  v59 = 0;
  v7 = 0;
  v48 = 0;
  v49 = 0;
  v50 = 0;
  memset_0(&pNotifyBuffer, 0, sizeof(pNotifyBuffer));
  pNotifyBuffer.pContext = 0;
  v54 = 1;
  pNotifyBuffer.dwVersion = 1;
  g_NlmHandlerInitialized = 1;
  pNotifyBuffer.pfnNotifyCallback = (PFN_SC_NOTIFY_CALLBACK)NlmTriggerSvcNotify;
  v8 = CoInitializeEx(0, 4u);
  if ( v8 >= 0 )
  {
    v9 = OpenSCManagerW(0, L"ServicesActive", 1u);
    v42 = (struct IConnectionPoint *)v9;
    if ( !v9 )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
      {
        goto LABEL_169;
      }
      v12 = 154;
      goto LABEL_14;
    }
    v13 = OpenServiceW(v9, L"NetProfm", 4u);
    hService = v13;
    v7 = v13;
    if ( !v13 )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
      {
        goto LABEL_169;
      }
      v12 = 155;
      goto LABEL_14;
    }
    if ( NotifyServiceStatusChangeW(v13, 0xCu, &pNotifyBuffer) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
      {
        goto LABEL_169;
      }
      v12 = 156;
LABEL_14:
      WPP_SF_d(v11[1].Flink, v12, &WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids, (unsigned int)LastError);
LABEL_169:
      v1 = v42;
      LODWORD(v3) = 1;
      goto LABEL_170;
    }
    LastError = CoCreateInstance(&CLSID_NetworkListManager, 0, 1u, &IID_INetworkListManager, (LPVOID *)&ppv);
    if ( LastError < 0 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
      {
        goto LABEL_169;
      }
      v12 = 157;
      goto LABEL_14;
    }
    v14 = ((__int64 (__fastcall *)(struct INetworkListManager *, __int16 *))ppv->lpVtbl->get_IsConnectedToInternet)(
            ppv,
            &v43);
    if ( v14 >= 0 )
    {
      if ( !v14 && v43 == -1 )
        g_IsNlmInternetConnected = 1;
    }
    else if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
           && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 158, &WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids, (unsigned int)v14);
    }
    NlmNetworksEnum(&g_NlmNetwork, &v54);
    if ( g_lpfnNetworkChangeHandler )
    {
      LODWORD(v4) = g_lpfnNetworkChangeHandler(&g_NlmNetwork);
    }
    else
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) == 0 )
      {
LABEL_44:
        if ( g_lpfnNetworkConnectivityChangeHandler )
        {
          if ( !(_DWORD)v4 )
          {
            g_lpfnNetworkConnectivityChangeHandler();
            goto LABEL_54;
          }
          if ( v15 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v15[1].Blink) & 4) != 0 )
          {
            v16 = 160;
LABEL_53:
            WPP_SF_(v15[1].Flink, v16, &WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids);
          }
        }
        else if ( v15 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v15[1].Blink) & 4) != 0 )
        {
          v16 = 161;
          goto LABEL_53;
        }
LABEL_54:
        v17 = operator new(0x10u);
        v4 = v17;
        if ( !v17 )
        {
          v4 = 0;
          goto LABEL_169;
        }
        *v17 = &CNetListManagerEventSink::`vftable';
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control[1].Flink, 210, &WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids);
        }
        v4[2] = 0;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control[1].Flink, 211, &WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids);
        }
        LastError = (**(__int64 (__fastcall ***)(_DWORD *, GUID *, __int64 *))v4)(v4, &IID_IUnknown, &v57);
        if ( LastError < 0 )
        {
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
          {
            goto LABEL_169;
          }
          v12 = 162;
          goto LABEL_14;
        }
        v18 = operator new(0x10u);
        v5 = v18;
        if ( !v18 )
        {
          v5 = 0;
          goto LABEL_169;
        }
        v18[2] = 0;
        *(_QWORD *)v18 = &CNetCostManagerEventSink::`vftable';
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        {
          if ( (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control[1].Flink, 225, &WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids);
            v19 = WPP_GLOBAL_Control;
          }
          if ( v19 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v19[1].Blink) & 8) != 0 )
            WPP_SF_(v19[1].Flink, 226, &WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids);
        }
        LastError = (**(__int64 (__fastcall ***)(_DWORD *, GUID *, __int64 *))v5)(v5, &IID_IUnknown, &v58);
        if ( LastError < 0 )
        {
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
          {
            goto LABEL_169;
          }
          v12 = 163;
          goto LABEL_14;
        }
        v20 = operator new(0x10u);
        v52 = v20;
        v6 = v20;
        if ( !v20 )
        {
          v6 = 0;
          goto LABEL_169;
        }
        *v20 = &CNetProfileEventSink::`vftable';
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control[1].Flink, 240, &WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids);
        }
        v6[2] = 0;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control[1].Flink, 241, &WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids);
        }
        LastError = (**(__int64 (__fastcall ***)(_DWORD *, GUID *, __int64 *))v6)(v6, &IID_IUnknown, &v59);
        if ( LastError < 0 )
        {
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
          {
            goto LABEL_169;
          }
          v12 = 164;
          goto LABEL_14;
        }
        v21 = 0;
        v45 = 0;
        v22 = 0;
        v47 = 0;
        v46 = 0;
        if ( WaitForSingleObjectEx(g_hNotifyThreadStopEvent, 0xFFFFFFFF, 1) )
        {
          while ( 1 )
          {
            if ( pNotifyBuffer.ServiceStatus.dwCurrentState == 4 )
            {
              while ( 1 )
              {
                if ( ppv )
                {
                  ((void (__fastcall *)(struct INetworkListManager *))ppv->lpVtbl->Release)(ppv);
                  ppv = 0;
                }
                if ( v21 == 1 )
                {
                  ((void (__fastcall *)(struct IConnectionPoint *, _QWORD))v1->lpVtbl->Unadvise)(v1, v48);
                  v21 = 0;
                  v45 = 0;
                }
                if ( v1 )
                {
                  ((void (__fastcall *)(struct IConnectionPoint *))v1->lpVtbl->Release)(v1);
                  v1 = 0;
                  v51 = 0;
                }
                if ( v22 == 1 )
                {
                  ((void (__fastcall *)(struct IConnectionPoint *, _QWORD))v2->lpVtbl->Unadvise)(v2, v49);
                  v22 = 0;
                  v46 = 0;
                }
                if ( v2 )
                {
                  ((void (__fastcall *)(struct IConnectionPoint *))v2->lpVtbl->Release)(v2);
                  v2 = 0;
                  v55 = 0;
                }
                if ( v47 == 1 )
                {
                  ((void (__fastcall *)(struct IConnectionPoint *, _QWORD))v3->lpVtbl->Unadvise)(v3, v50);
                  v47 = 0;
                }
                if ( v3 )
                {
                  ((void (__fastcall *)(struct IConnectionPoint *))v3->lpVtbl->Release)(v3);
                  v3 = 0;
                  v56 = 0;
                }
                Instance = CoCreateInstance(&CLSID_NetworkListManager, 0, 1u, &IID_INetworkListManager, (LPVOID *)&ppv);
                if ( Instance < 0 )
                {
                  v39 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
                  {
                    v40 = 165;
                    goto LABEL_155;
                  }
                  goto LABEL_156;
                }
                ConnectionPoints = HrGetConnectionPoints(ppv, &IID_INetworkListManagerEvents, &v51);
                v25 = ConnectionPoints;
                if ( ConnectionPoints )
                {
                  v26 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 2) != 0 )
                  {
                    v27 = 167;
                    goto LABEL_113;
                  }
                }
                else
                {
                  ConnectionPoints = ((__int64 (__fastcall *)(struct IConnectionPoint *, __int64, unsigned int *))v51->lpVtbl->Advise)(
                                       v51,
                                       v57,
                                       &v48);
                  v25 = ConnectionPoints;
                  if ( !ConnectionPoints )
                  {
                    v45 = 1;
                    goto LABEL_114;
                  }
                  v26 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 2) != 0 )
                  {
                    v27 = 166;
LABEL_113:
                    WPP_SF_d(v26[1].Flink, v27, &WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids, ConnectionPoints);
                  }
                }
LABEL_114:
                v28 = HrGetConnectionPoints(ppv, &IID_INetworkCostManagerEvents, &v55);
                v2 = v55;
                v29 = v28;
                if ( v28 )
                {
                  v30 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 2) != 0 )
                  {
                    v31 = 169;
                    goto LABEL_123;
                  }
                }
                else
                {
                  v28 = ((__int64 (__fastcall *)(struct IConnectionPoint *, __int64, unsigned int *))v55->lpVtbl->Advise)(
                          v55,
                          v58,
                          &v49);
                  v29 = v28;
                  if ( !v28 )
                  {
                    v46 = 1;
                    goto LABEL_124;
                  }
                  v30 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 2) != 0 )
                  {
                    v31 = 168;
LABEL_123:
                    WPP_SF_d(v30[1].Flink, v31, &WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids, v28);
                  }
                }
LABEL_124:
                v32 = HrGetConnectionPoints(ppv, &IID_INetworkEvents, &v56);
                v3 = v56;
                v33 = v32;
                if ( v32 )
                {
                  v35 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 2) != 0 )
                  {
                    v36 = 171;
                    goto LABEL_133;
                  }
                }
                else
                {
                  v34 = ((__int64 (__fastcall *)(struct IConnectionPoint *, __int64, unsigned int *))v56->lpVtbl->Advise)(
                          v56,
                          v59,
                          &v50);
                  v35 = WPP_GLOBAL_Control;
                  v33 = v34;
                  if ( !v34 )
                  {
                    v47 = 1;
                    goto LABEL_134;
                  }
                  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 2) != 0 )
                  {
                    v36 = 170;
LABEL_133:
                    WPP_SF_d(v35[1].Flink, v36, &WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids, v33);
                    v35 = WPP_GLOBAL_Control;
                  }
                }
LABEL_134:
                v37 = v25;
                if ( v25 != -2147483638 )
                  v37 = v29;
                v38 = v33;
                if ( v33 != -2147483638 )
                  v38 = v37;
                if ( v35 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v35[1].Blink) & 4) != 0 )
                  WPP_SF_ddd(v35[1].Flink, 172, &WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids, v38, v25, v33);
                if ( v38 != -2147483638 )
                {
                  v1 = v51;
                  v21 = v45;
                  v22 = v46;
                  break;
                }
                Sleep(0xFAu);
                v1 = v51;
                v21 = v45;
                v22 = v46;
              }
            }
            if ( NotifyServiceStatusChangeW(hService, 0xCu, &pNotifyBuffer) )
              break;
            if ( !WaitForSingleObjectEx(g_hNotifyThreadStopEvent, 0xFFFFFFFF, 1) )
              goto LABEL_156;
          }
          Instance = GetLastError();
          if ( Instance > 0 )
            Instance = (unsigned __int16)Instance | 0x80070000;
          v39 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
          {
            v40 = 173;
LABEL_155:
            WPP_SF_d(v39[1].Flink, v40, &WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids, (unsigned int)Instance);
          }
LABEL_156:
          if ( v21 == 1 )
            ((void (__fastcall *)(struct IConnectionPoint *, _QWORD))v1->lpVtbl->Unadvise)(v1, v48);
          if ( v1 )
            ((void (__fastcall *)(struct IConnectionPoint *))v1->lpVtbl->Release)(v1);
          if ( v22 == 1 )
            ((void (__fastcall *)(struct IConnectionPoint *, _QWORD))v2->lpVtbl->Unadvise)(v2, v49);
          if ( v2 )
            ((void (__fastcall *)(struct IConnectionPoint *))v2->lpVtbl->Release)(v2);
          if ( v47 == 1 )
            ((void (__fastcall *)(struct IConnectionPoint *, _QWORD))v3->lpVtbl->Unadvise)(v3, v50);
          if ( v3 )
            ((void (__fastcall *)(struct IConnectionPoint *))v3->lpVtbl->Release)(v3);
        }
        v6 = v52;
        v7 = hService;
        goto LABEL_169;
      }
      WPP_SF_(WPP_GLOBAL_Control[1].Flink, 159, &WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids);
    }
    v15 = WPP_GLOBAL_Control;
    goto LABEL_44;
  }
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 153, &WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids, (unsigned int)v8);
LABEL_170:
  if ( ppv )
  {
    ((void (__fastcall *)(struct INetworkListManager *))ppv->lpVtbl->Release)(ppv);
    ppv = 0;
  }
  if ( v4 )
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v4 + 16LL))(v4);
  if ( v5 )
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v5 + 16LL))(v5);
  if ( v6 )
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v6 + 16LL))(v6);
  if ( v7 )
    CloseServiceHandle(v7);
  if ( v1 )
    CloseServiceHandle((SC_HANDLE)v1);
  if ( (_DWORD)v3 == 1 )
    CoUninitialize();
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 174, &WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x1800b57b0  push    rbp
0x1800b57b2  push    rbx
0x1800b57b3  push    rsi
0x1800b57b4  push    rdi
0x1800b57b5  push    r12
0x1800b57b7  push    r13
0x1800b57b9  push    r14
0x1800b57bb  push    r15
0x1800b57bd  lea     rbp, [rsp-18h]
0x1800b57c2  sub     rsp, 118h
0x1800b57c9  mov     rax, cs:__security_cookie
0x1800b57d0  xor     rax, rsp
0x1800b57d3  mov     [rbp+50h+var_50], rax
0x1800b57d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b57de  lea     rax, WPP_GLOBAL_Control
0x1800b57e5  cmp     rcx, rax
0x1800b57e8  jz      short loc_1800B5805
0x1800b57ea  test    byte ptr [rcx+1Ch], 8
0x1800b57ee  jz      short loc_1800B5805
0x1800b57f0  mov     rcx, [rcx+10h]
0x1800b57f4  lea     r8, WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids
0x1800b57fb  mov     edx, 98h
0x1800b5800  call    WPP_SF_
0x1800b5805  xor     ecx, ecx
0x1800b5807  xor     edx, edx; Val
0x1800b5809  mov     [rsp+150h+var_110], cx
0x1800b580e  mov     edi, ecx
0x1800b5810  mov     [rsp+150h+var_E8], rcx
0x1800b5815  mov     r13d, ecx
0x1800b5818  mov     [rbp+50h+var_C8], rcx
0x1800b581c  mov     r12d, ecx
0x1800b581f  lea     r8d, [rcx+50h]; Size
0x1800b5823  mov     [rbp+50h+var_C0], rcx
0x1800b5827  mov     [rsp+150h+var_108], rcx
0x1800b582c  mov     ebx, ecx
0x1800b582e  mov     r15d, ecx
0x1800b5831  mov     [rbp+50h+var_B8], rcx
0x1800b5835  mov     esi, ecx
0x1800b5837  mov     [rbp+50h+var_B0], rcx
0x1800b583b  mov     [rbp+50h+var_A8], rcx
0x1800b583f  mov     r14d, ecx
0x1800b5842  mov     [rsp+150h+var_F4], ecx
0x1800b5846  mov     [rsp+150h+var_F0], ecx
0x1800b584a  mov     [rsp+150h+var_EC], ecx
0x1800b584e  lea     rcx, [rbp+50h+pNotifyBuffer]; void *
0x1800b5852  call    memset_0
0x1800b5857  lea     ecx, [r14+1]
0x1800b585b  mov     [rbp+50h+pNotifyBuffer.pContext], rbx
0x1800b585f  mov     [rbp+50h+var_D0], ecx
0x1800b5862  lea     rax, ?NlmTriggerSvcNotify@@YAXPEAX@Z; NlmTriggerSvcNotify(void *)
0x1800b5869  mov     [rbp+50h+pNotifyBuffer.dwVersion], ecx
0x1800b586c  lea     edx, [rcx+3]; dwCoInit
0x1800b586f  mov     cs:?g_NlmHandlerInitialized@@3HA, ecx; int g_NlmHandlerInitialized
0x1800b5875  xor     ecx, ecx; pvReserved
0x1800b5877  mov     [rbp+50h+pNotifyBuffer.pfnNotifyCallback], rax
0x1800b587b  call    cs:__imp_CoInitializeEx
0x1800b5882  nop     dword ptr [rax+rax+00h]
0x1800b5887  test    eax, eax
0x1800b5889  jns     short loc_1800B58C9
0x1800b588b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b5892  lea     r13, WPP_GLOBAL_Control
0x1800b5899  cmp     rcx, r13
0x1800b589c  jz      loc_1800B62C4
0x1800b58a2  test    byte ptr [rcx+1Ch], 1
0x1800b58a6  jz      loc_1800B62C4
0x1800b58ac  mov     rcx, [rcx+10h]
0x1800b58b0  lea     r8, WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids
0x1800b58b7  mov     edx, 99h
0x1800b58bc  mov     r9d, eax
0x1800b58bf  call    WPP_SF_d
0x1800b58c4  jmp     loc_1800B62C4
0x1800b58c9  mov     eax, 1
0x1800b58ce  lea     rdx, aServicesactive_0; "ServicesActive"
0x1800b58d5  mov     r8d, eax; dwDesiredAccess
0x1800b58d8  mov     [rsp+150h+var_120], eax
0x1800b58dc  xor     ecx, ecx; lpMachineName
0x1800b58de  call    cs:__imp_OpenSCManagerW
0x1800b58e5  nop     dword ptr [rax+rax+00h]
0x1800b58ea  mov     [rsp+150h+var_118], rax
0x1800b58ef  test    rax, rax
0x1800b58f2  jnz     short loc_1800B594A
0x1800b58f4  call    cs:__imp_GetLastError
0x1800b58fb  nop     dword ptr [rax+rax+00h]
0x1800b5900  test    eax, eax
0x1800b5902  jle     short loc_1800B590C
0x1800b5904  movzx   eax, ax
0x1800b5907  or      eax, 80070000h
0x1800b590c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b5913  lea     r13, WPP_GLOBAL_Control
0x1800b591a  cmp     rcx, r13
0x1800b591d  jz      loc_1800B62BA
0x1800b5923  test    byte ptr [rcx+1Ch], 1
0x1800b5927  jz      loc_1800B62BA
0x1800b592d  mov     edx, 9Ah
0x1800b5932  mov     rcx, [rcx+10h]
0x1800b5936  lea     r8, WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids
0x1800b593d  mov     r9d, eax
0x1800b5940  call    WPP_SF_d
0x1800b5945  jmp     loc_1800B62BA
0x1800b594a  mov     r8d, 4; dwDesiredAccess
0x1800b5950  lea     rdx, aNetprofm; "NetProfm"
0x1800b5957  mov     rcx, rax; hSCManager
0x1800b595a  call    cs:__imp_OpenServiceW
0x1800b5961  nop     dword ptr [rax+rax+00h]
0x1800b5966  mov     [rsp+150h+hService], rax
0x1800b596b  mov     r14, rax
0x1800b596e  test    rax, rax
0x1800b5971  jnz     short loc_1800B59B6
0x1800b5973  call    cs:__imp_GetLastError
0x1800b597a  nop     dword ptr [rax+rax+00h]
0x1800b597f  test    eax, eax
0x1800b5981  jle     short loc_1800B598B
0x1800b5983  movzx   eax, ax
0x1800b5986  or      eax, 80070000h
0x1800b598b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b5992  lea     r13, WPP_GLOBAL_Control
0x1800b5999  cmp     rcx, r13
0x1800b599c  jz      loc_1800B62BA
0x1800b59a2  test    byte ptr [rcx+1Ch], 1
0x1800b59a6  jz      loc_1800B62BA
0x1800b59ac  mov     edx, 9Bh
0x1800b59b1  jmp     loc_1800B5932
0x1800b59b6  lea     r8, [rbp+50h+pNotifyBuffer]; pNotifyBuffer
0x1800b59ba  mov     edx, 0Ch; dwNotifyMask
0x1800b59bf  mov     rcx, rax; hService
0x1800b59c2  call    cs:__imp_NotifyServiceStatusChangeW
0x1800b59c9  nop     dword ptr [rax+rax+00h]
0x1800b59ce  test    eax, eax
0x1800b59d0  jz      short loc_1800B5A15
0x1800b59d2  call    cs:__imp_GetLastError
0x1800b59d9  nop     dword ptr [rax+rax+00h]
0x1800b59de  test    eax, eax
0x1800b59e0  jle     short loc_1800B59EA
0x1800b59e2  movzx   eax, ax
0x1800b59e5  or      eax, 80070000h
0x1800b59ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b59f1  lea     r13, WPP_GLOBAL_Control
0x1800b59f8  cmp     rcx, r13
0x1800b59fb  jz      loc_1800B62BA
0x1800b5a01  test    byte ptr [rcx+1Ch], 1
0x1800b5a05  jz      loc_1800B62BA
0x1800b5a0b  mov     edx, 9Ch
0x1800b5a10  jmp     loc_1800B5932
0x1800b5a15  xor     edx, edx; pUnkOuter
0x1800b5a17  lea     rax, [rsp+150h+var_108]
0x1800b5a1c  lea     r9, IID_INetworkListManager; riid
0x1800b5a23  mov     [rsp+150h+ppv], rax; ppv
0x1800b5a28  lea     rcx, CLSID_NetworkListManager; rclsid
0x1800b5a2f  lea     r8d, [rdx+1]; dwClsContext
0x1800b5a33  call    cs:__imp_CoCreateInstance
0x1800b5a3a  nop     dword ptr [rax+rax+00h]
0x1800b5a3f  test    eax, eax
0x1800b5a41  jns     short loc_1800B5A6E
0x1800b5a43  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b5a4a  lea     r13, WPP_GLOBAL_Control
0x1800b5a51  cmp     rcx, r13
0x1800b5a54  jz      loc_1800B62BA
0x1800b5a5a  test    byte ptr [rcx+1Ch], 1
0x1800b5a5e  jz      loc_1800B62BA
0x1800b5a64  mov     edx, 9Dh
0x1800b5a69  jmp     loc_1800B5932
0x1800b5a6e  mov     rcx, [rsp+150h+var_108]
0x1800b5a73  lea     rdx, [rsp+150h+var_110]
0x1800b5a78  mov     rax, [rcx]
0x1800b5a7b  mov     rax, [rax+58h]
0x1800b5a7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5a84  test    eax, eax
0x1800b5a86  jns     short loc_1800B5ABB
0x1800b5a88  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b5a8f  lea     rdx, WPP_GLOBAL_Control
0x1800b5a96  cmp     rcx, rdx
0x1800b5a99  jz      short loc_1800B5ACF
0x1800b5a9b  test    byte ptr [rcx+1Ch], 1
0x1800b5a9f  jz      short loc_1800B5ACF
0x1800b5aa1  mov     rcx, [rcx+10h]
0x1800b5aa5  lea     r8, WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids
0x1800b5aac  mov     edx, 9Eh
0x1800b5ab1  mov     r9d, eax
0x1800b5ab4  call    WPP_SF_d
0x1800b5ab9  jmp     short loc_1800B5ACF
0x1800b5abb  jnz     short loc_1800B5ACF
0x1800b5abd  cmp     [rsp+150h+var_110], 0FFFFh
0x1800b5ac3  jnz     short loc_1800B5ACF
0x1800b5ac5  mov     cs:?g_IsNlmInternetConnected@@3HA, 1; int g_IsNlmInternetConnected
0x1800b5acf  lea     rdx, [rbp+50h+var_D0]; int *
0x1800b5ad3  lea     rcx, ?g_NlmNetwork@@3U_LIST_ENTRY@@A; struct _LIST_ENTRY *
0x1800b5ada  call    ?NlmNetworksEnum@@YAJPEAU_LIST_ENTRY@@PEAH@Z; NlmNetworksEnum(_LIST_ENTRY *,int *)
0x1800b5adf  mov     rax, cs:?g_lpfnNetworkChangeHandler@@3P6AHPEAU_LIST_ENTRY@@@ZEA; int (*g_lpfnNetworkChangeHandler)(_LIST_ENTRY *)
0x1800b5ae6  test    rax, rax
0x1800b5ae9  jz      short loc_1800B5AFB
0x1800b5aeb  lea     rcx, ?g_NlmNetwork@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_NlmNetwork
0x1800b5af2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5af7  mov     ebx, eax
0x1800b5af9  jmp     short loc_1800B5B29
0x1800b5afb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b5b02  lea     rdx, WPP_GLOBAL_Control
0x1800b5b09  cmp     rcx, rdx
0x1800b5b0c  jz      short loc_1800B5B37
0x1800b5b0e  test    byte ptr [rcx+1Ch], 4
0x1800b5b12  jz      short loc_1800B5B37
0x1800b5b14  mov     rcx, [rcx+10h]
0x1800b5b18  lea     r8, WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids
0x1800b5b1f  mov     edx, 9Fh
0x1800b5b24  call    WPP_SF_
0x1800b5b29  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b5b30  lea     rdx, WPP_GLOBAL_Control
0x1800b5b37  mov     rax, cs:?g_lpfnNetworkConnectivityChangeHandler@@3P6AXXZEA; void (*g_lpfnNetworkConnectivityChangeHandler)(void)
0x1800b5b3e  test    rax, rax
0x1800b5b41  jz      short loc_1800B5B60
0x1800b5b43  test    ebx, ebx
0x1800b5b45  jnz     short loc_1800B5B4E
0x1800b5b47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5b4c  jmp     short loc_1800B5B80
0x1800b5b4e  cmp     rcx, rdx
0x1800b5b51  jz      short loc_1800B5B80
0x1800b5b53  test    byte ptr [rcx+1Ch], 4
0x1800b5b57  jz      short loc_1800B5B80
0x1800b5b59  mov     edx, 0A0h
0x1800b5b5e  jmp     short loc_1800B5B70
0x1800b5b60  cmp     rcx, rdx
0x1800b5b63  jz      short loc_1800B5B80
0x1800b5b65  test    byte ptr [rcx+1Ch], 4
0x1800b5b69  jz      short loc_1800B5B80
0x1800b5b6b  mov     edx, 0A1h
0x1800b5b70  mov     rcx, [rcx+10h]
0x1800b5b74  lea     r8, WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids
0x1800b5b7b  call    WPP_SF_
0x1800b5b80  mov     ecx, 10h; Size
0x1800b5b85  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b5b8a  mov     rbx, rax
0x1800b5b8d  test    rax, rax
0x1800b5b90  jz      loc_1800B63B2
0x1800b5b96  lea     rax, ??_7CNetListManagerEventSink@@6B@; const CNetListManagerEventSink::`vftable'
0x1800b5b9d  mov     [rbx], rax
0x1800b5ba0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b5ba7  lea     rax, WPP_GLOBAL_Control
0x1800b5bae  cmp     rcx, rax
0x1800b5bb1  jz      short loc_1800B5BD5
0x1800b5bb3  test    byte ptr [rcx+1Ch], 8
0x1800b5bb7  jz      short loc_1800B5BD5
0x1800b5bb9  mov     rcx, [rcx+10h]
0x1800b5bbd  lea     r8, WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids
0x1800b5bc4  mov     edx, 0D2h
0x1800b5bc9  call    WPP_SF_
0x1800b5bce  lea     rax, WPP_GLOBAL_Control
0x1800b5bd5  mov     [rbx+8], esi
0x1800b5bd8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b5bdf  cmp     rcx, rax
0x1800b5be2  jz      short loc_1800B5BFF
0x1800b5be4  test    byte ptr [rcx+1Ch], 8
0x1800b5be8  jz      short loc_1800B5BFF
0x1800b5bea  mov     rcx, [rcx+10h]
0x1800b5bee  lea     r8, WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids
0x1800b5bf5  mov     edx, 0D3h
0x1800b5bfa  call    WPP_SF_
0x1800b5bff  mov     rax, [rbx]
0x1800b5c02  lea     r8, [rbp+50h+var_B8]
0x1800b5c06  lea     rdx, IID_IUnknown
0x1800b5c0d  mov     rcx, rbx
0x1800b5c10  mov     rax, [rax]
0x1800b5c13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5c18  test    eax, eax
0x1800b5c1a  jns     short loc_1800B5C47
0x1800b5c1c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b5c23  lea     r13, WPP_GLOBAL_Control
0x1800b5c2a  cmp     rcx, r13
0x1800b5c2d  jz      loc_1800B62BA
0x1800b5c33  test    byte ptr [rcx+1Ch], 1
0x1800b5c37  jz      loc_1800B62BA
0x1800b5c3d  mov     edx, 0A2h
0x1800b5c42  jmp     loc_1800B5932
0x1800b5c47  mov     ecx, 10h; Size
0x1800b5c4c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b5c51  mov     r15, rax
0x1800b5c54  test    rax, rax
0x1800b5c57  jz      loc_1800B63AA
0x1800b5c5d  lea     rax, ??_7CNetCostManagerEventSink@@6B@; const CNetCostManagerEventSink::`vftable'
0x1800b5c64  mov     [r15+8], esi
0x1800b5c68  mov     [r15], rax
0x1800b5c6b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b5c72  lea     rax, WPP_GLOBAL_Control
0x1800b5c79  cmp     rcx, rax
0x1800b5c7c  jz      short loc_1800B5CC7
0x1800b5c7e  test    byte ptr [rcx+1Ch], 8
0x1800b5c82  jz      short loc_1800B5CA7
0x1800b5c84  mov     rcx, [rcx+10h]
0x1800b5c88  lea     r8, WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids
0x1800b5c8f  mov     edx, 0E1h
0x1800b5c94  call    WPP_SF_
0x1800b5c99  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b5ca0  lea     rax, WPP_GLOBAL_Control
0x1800b5ca7  cmp     rcx, rax
0x1800b5caa  jz      short loc_1800B5CC7
0x1800b5cac  test    byte ptr [rcx+1Ch], 8
0x1800b5cb0  jz      short loc_1800B5CC7
0x1800b5cb2  mov     rcx, [rcx+10h]
0x1800b5cb6  lea     r8, WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids
0x1800b5cbd  mov     edx, 0E2h
0x1800b5cc2  call    WPP_SF_
0x1800b5cc7  mov     rax, [r15]
  ... truncated ...
```
