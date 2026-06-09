# CMapsUpdateTaskHandler::StartAutoCheckForUpdate(void)

- ea: `0x1800065c4`
- end: `0x18000698f`
- name: `?StartAutoCheckForUpdate@CMapsUpdateTaskHandler@@AEAAJXZ`
- size: `971`
- prototype: `__int64 __fastcall(CMapsUpdateTaskHandler *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800072f0`

## callees

- `0x180001be0`
- `0x180002612`
- `0x180004edc`
- `0x1800065c4`
- `0x180006ee4`
- `0x180007004`
- `0x180007144`

## import_xrefs

- `MosHostClient!OdmlGetAutoUpdateEnabled` at `0x180006815`
- `MosHostClient!OdmlGetAutoUpdateEnabled` at `0x180006815`
- `MosHostClient!OdmlStartCheckForUpdates` at `0x180006797`
- `MosHostClient!OdmlStartCheckForUpdates` at `0x180006797`
- `MosHostClient!MapsStorageOpen` at `0x180006885`
- `MosHostClient!MapsStorageOpen` at `0x180006885`
- `MosHostClient!OdmlStartInstallUpdate` at `0x18000683b`
- `MosHostClient!OdmlStartInstallUpdate` at `0x18000683b`
- `MosHostClient!OdmlOpen` at `0x18000674f`
- `MosHostClient!OdmlOpen` at `0x18000674f`
- `MosHostClient!MapsStorageGetCurrentLocation` at `0x1800068b6`
- `MosHostClient!MapsStorageGetCurrentLocation` at `0x1800068b6`
- `MosHostClient!MapsStorageClose` at `0x180006963`
- `MosHostClient!MapsStorageClose` at `0x180006963`
- `MosHostClient!OdmlClose` at `0x18000685d`
- `MosHostClient!OdmlClose` at `0x18000685d`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x1800068d2`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x1800068d2`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18000672e`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18000672e`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x180006642`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x1800068a1`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x180006642`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x1800068a1`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800066d8`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800067dc`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800066d8`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800067dc`
- `ntdll!NtQueryWnfStateData` at `0x180006694`
- `ntdll!NtQueryWnfStateData` at `0x180006694`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180006710`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180006710`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800066e0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800067e4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800066e0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800067e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800066cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800067d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800066cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800067d1`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x180006614`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x180006614`

## string_xrefs

- `0x180006725`: `CMapsUpdateTaskHandler::Subscribe`
- `0x18000663b`: `CMapsUpdateTaskHandler::StartAutoCheckForUpdate`
- `0x180006898`: `CMapsUpdateTaskHandler::SendTelemetry`
- `0x1800068c9`: `CMapsUpdateTaskHandler::SendTelemetry`
- `0x180006606`: `EnableOfflineMapsAutoUpdate`

## pseudocode

```c
__int64 __fastcall CMapsUpdateTaskHandler::StartAutoCheckForUpdate(CMapsUpdateTaskHandler *this)
{
  int PolicyInt; // eax
  int v3; // ecx
  int v4; // r8d
  int v5; // ecx
  int v6; // ebx
  bool v7; // r13
  int v8; // eax
  int v9; // r8d
  unsigned int v10; // r12d
  __int64 v11; // r15
  DWORD LastError; // edi
  __int64 v13; // rdi
  DWORD v14; // ebx
  int v15; // eax
  int CurrentLocation; // eax
  bool v17; // di
  _DWORD *v18; // rax
  OfflineMapsTelemetry *v19; // rax
  bool v20; // di
  _DWORD *v21; // rax
  OfflineMapsTelemetry *v22; // rax
  unsigned int v24; // [rsp+40h] [rbp-C0h] BYREF
  int v25; // [rsp+44h] [rbp-BCh] BYREF
  struct HMAPSSTORAGE__ *v26; // [rsp+48h] [rbp-B8h] BYREF
  struct HODML__ *v27; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v28[4]; // [rsp+60h] [rbp-A0h] BYREF
  int v29; // [rsp+64h] [rbp-9Ch]
  unsigned int v30; // [rsp+274h] [rbp+174h]
  unsigned int v31; // [rsp+6C0h] [rbp+5C0h]

  v25 = 0;
  v27 = 0;
  PolicyInt = PolicyManager_GetPolicyInt(L"Maps", L"EnableOfflineMapsAutoUpdate", &v25);
  if ( PolicyInt == -2147024769 )
  {
    v3 = 0xFFFF;
    v25 = 0xFFFF;
  }
  else
  {
    if ( PolicyInt < 0 )
    {
      v4 = 127;
LABEL_5:
      v5 = PolicyInt;
LABEL_6:
      v6 = ZTraceReportPropagation(v5, "CMapsUpdateTaskHandler::StartAutoCheckForUpdate", v4, this);
      goto LABEL_40;
    }
    v3 = v25;
  }
  if ( v3 )
  {
    v7 = v3 == 1;
    v24 = 0;
    LODWORD(v26) = 0;
    v8 = NtQueryWnfStateData(&WNF_MAPS_MAPLOADER_STATUS_CHANGE, 0, 0, &v24, 0, &v26);
    if ( (int)(v8 + 0x80000000) < 0 || v8 == -1073741789 )
    {
      v10 = v24;
      v11 = *((_QWORD *)this + 7);
      if ( v11 )
      {
        LastError = GetLastError();
        RtlUnsubscribeWnfNotificationWaitForCompletion(v11);
        SetLastError(LastError);
      }
      *((_QWORD *)this + 7) = 0;
      v8 = RtlSubscribeWnfStateChangeNotification(
             (char *)this + 56,
             WNF_MAPS_MAPLOADER_STATUS_CHANGE,
             v10,
             CMapsUpdateTaskHandler::UpdateCheckResultCallback,
             this,
             0,
             0,
             0);
      if ( v8 >= 0 )
      {
LABEL_18:
        PolicyInt = OdmlOpen(0, 5, &v27);
        if ( PolicyInt < 0 )
        {
          v4 = 145;
          goto LABEL_5;
        }
        PolicyInt = CMapsUpdateTaskHandler::WaitForNotification(this, 0x2710u);
        if ( PolicyInt < 0 )
        {
          v4 = 148;
          goto LABEL_5;
        }
        v5 = *((_DWORD *)this + 17);
        if ( v5 < 0 )
        {
          v4 = 151;
          goto LABEL_6;
        }
        PolicyInt = OdmlStartCheckForUpdates(v27);
        if ( PolicyInt < 0 )
        {
          v4 = 154;
          goto LABEL_5;
        }
        PolicyInt = CMapsUpdateTaskHandler::WaitForNotification(this, 0x7530u);
        if ( PolicyInt < 0 )
        {
          v4 = 157;
          goto LABEL_5;
        }
        v13 = *((_QWORD *)this + 7);
        if ( v13 )
        {
          v14 = GetLastError();
          RtlUnsubscribeWnfNotificationWaitForCompletion(v13);
          SetLastError(v14);
        }
        *((_QWORD *)this + 7) = 0;
        v5 = *((_DWORD *)this + 17);
        if ( v5 < 0 )
        {
          v4 = 163;
          goto LABEL_6;
        }
        if ( *((_DWORD *)this + 18) == 2 )
        {
          v24 = 0;
          PolicyInt = OdmlGetAutoUpdateEnabled(v27, (int *)&v24);
          if ( PolicyInt < 0 )
          {
            v4 = 171;
            goto LABEL_5;
          }
          if ( v24 || v7 )
          {
            PolicyInt = OdmlStartInstallUpdate(v27);
            if ( PolicyInt < 0 )
            {
              v4 = 175;
              goto LABEL_5;
            }
          }
        }
        goto LABEL_39;
      }
      v9 = 112;
    }
    else
    {
      v9 = 102;
    }
    PolicyInt = ZTraceReportOrigination(v8 | 0x10000000, "CMapsUpdateTaskHandler::Subscribe", v9, this);
    if ( PolicyInt < 0 )
    {
      v4 = 142;
      goto LABEL_5;
    }
    goto LABEL_18;
  }
LABEL_39:
  v6 = 0;
LABEL_40:
  if ( v27 )
    OdmlClose(v27);
  memset_0(v28, 0, 0x670u);
  v26 = 0;
  v15 = MapsStorageOpen(5, &v26);
  if ( v15 >= 0 )
  {
    CurrentLocation = MapsStorageGetCurrentLocation(v26, (struct _STORAGE_DEVICE_DATA *)v28);
    if ( CurrentLocation < 0 )
      ZTraceReportIgnore(CurrentLocation, "CMapsUpdateTaskHandler::SendTelemetry", 247, this);
    if ( v6 >= 0 )
    {
      v20 = v29 != 0;
      v21 = (_DWORD *)*((_QWORD *)OfflineMapsTelemetry::Instance() + 1);
      if ( v21 && *v21 )
      {
        v22 = OfflineMapsTelemetry::Instance();
        OfflineMapsTelemetry::UpdateTaskCompleted_(v22, v20, v30, v31);
      }
    }
    else
    {
      v17 = v29 != 0;
      v18 = (_DWORD *)*((_QWORD *)OfflineMapsTelemetry::Instance() + 1);
      if ( v18 && *v18 )
      {
        v19 = OfflineMapsTelemetry::Instance();
        OfflineMapsTelemetry::UpdateTaskFailed_(v19, v17, v30, v31, v6);
      }
    }
  }
  else
  {
    ZTraceReportPropagation(v15, "CMapsUpdateTaskHandler::SendTelemetry", 245, this);
  }
  if ( v26 )
    MapsStorageClose(v26);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800065c4  push    rbp
0x1800065c6  push    rbx
0x1800065c7  push    rsi
0x1800065c8  push    rdi
0x1800065c9  push    r12
0x1800065cb  push    r13
0x1800065cd  push    r14
0x1800065cf  push    r15
0x1800065d1  lea     rbp, [rsp-5E8h]
0x1800065d9  sub     rsp, 6E8h
0x1800065e0  mov     rax, cs:__security_cookie
0x1800065e7  xor     rax, rsp
0x1800065ea  mov     [rbp+620h+var_50], rax
0x1800065f1  mov     rsi, rcx
0x1800065f4  xor     r15d, r15d
0x1800065f7  mov     [rsp+720h+var_6DC], r15d
0x1800065fc  mov     [rsp+720h+var_6D0], r15
0x180006601  lea     r8, [rsp+720h+var_6DC]
0x180006606  lea     rdx, aEnableofflinem; "EnableOfflineMapsAutoUpdate"
0x18000660d  lea     rcx, aMaps; "Maps"
0x180006614  call    cs:__imp_PolicyManager_GetPolicyInt
0x18000661a  cmp     eax, 8007007Fh
0x18000661f  jnz     short loc_18000662C
0x180006621  mov     ecx, 0FFFFh
0x180006626  mov     [rsp+720h+var_6DC], ecx
0x18000662a  jmp     short loc_180006653
0x18000662c  test    eax, eax
0x18000662e  jns     short loc_18000664F
0x180006630  mov     r8d, 7Fh
0x180006636  mov     ecx, eax
0x180006638  mov     r9, rsi
0x18000663b  lea     rdx, aCmapsupdatetas_0; "CMapsUpdateTaskHandler::StartAutoCheckF"...
0x180006642  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x180006648  mov     ebx, eax
0x18000664a  jmp     loc_180006853
0x18000664f  mov     ecx, [rsp+720h+var_6DC]
0x180006653  test    ecx, ecx
0x180006655  jz      loc_180006850
0x18000665b  movzx   r13d, r15b
0x18000665f  mov     eax, 1
0x180006664  cmp     ecx, eax
0x180006666  cmovz   r13d, eax
0x18000666a  mov     [rsp+720h+var_6E0], r15d
0x18000666f  mov     dword ptr [rsp+720h+var_6D8], r15d
0x180006674  lea     rax, [rsp+720h+var_6D8]
0x180006679  mov     [rsp+720h+var_6F8], rax
0x18000667e  mov     qword ptr [rsp+720h+var_700], r15
0x180006683  lea     r9, [rsp+720h+var_6E0]
0x180006688  xor     r8d, r8d
0x18000668b  xor     edx, edx
0x18000668d  lea     rcx, WNF_MAPS_MAPLOADER_STATUS_CHANGE
0x180006694  call    cs:__imp_NtQueryWnfStateData
0x18000669a  mov     edx, 80000000h
0x18000669f  lea     ecx, [rax+rdx]
0x1800066a2  test    edx, ecx
0x1800066a4  jnz     short loc_1800066B5
0x1800066a6  cmp     eax, 0C0000023h
0x1800066ab  jz      short loc_1800066B5
0x1800066ad  mov     r8d, 66h ; 'f'
0x1800066b3  jmp     short loc_18000671E
0x1800066b5  mov     r12d, [rsp+720h+var_6E0]
0x1800066ba  mov     rbx, cs:WNF_MAPS_MAPLOADER_STATUS_CHANGE
0x1800066c1  lea     r14, [rsi+38h]
0x1800066c5  mov     r15, [r14]
0x1800066c8  test    r15, r15
0x1800066cb  jz      short loc_1800066E6
0x1800066cd  call    cs:__imp_GetLastError
0x1800066d3  mov     edi, eax
0x1800066d5  mov     rcx, r15
0x1800066d8  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x1800066de  mov     ecx, edi; dwErrCode
0x1800066e0  call    cs:__imp_SetLastError
0x1800066e6  xor     r15d, r15d
0x1800066e9  mov     [r14], r15
0x1800066ec  mov     [rsp+720h+var_6E8], r15d
0x1800066f1  mov     [rsp+720h+var_6F0], r15d
0x1800066f6  mov     [rsp+720h+var_6F8], r15
0x1800066fb  mov     qword ptr [rsp+720h+var_700], rsi
0x180006700  lea     r9, ?UpdateCheckResultCallback@CMapsUpdateTaskHandler@@CAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; CMapsUpdateTaskHandler::UpdateCheckResultCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x180006707  mov     r8d, r12d
0x18000670a  mov     rdx, rbx
0x18000670d  mov     rcx, r14
0x180006710  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x180006716  test    eax, eax
0x180006718  jns     short loc_180006743
0x18000671a  lea     r8d, [r15+70h]
0x18000671e  bts     eax, 1Ch
0x180006722  mov     r9, rsi
0x180006725  lea     rdx, aCmapsupdatetas_1; "CMapsUpdateTaskHandler::Subscribe"
0x18000672c  mov     ecx, eax
0x18000672e  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x180006734  test    eax, eax
0x180006736  jns     short loc_180006743
0x180006738  mov     r8d, 8Eh
0x18000673e  jmp     loc_180006636
0x180006743  lea     r8, [rsp+720h+var_6D0]
0x180006748  mov     edx, 5
0x18000674d  xor     ecx, ecx
0x18000674f  call    cs:__imp_?OdmlOpen@@YAJPEBGW4__MIDL___MIDL_itf_moshostapi_0000_0000_0001@@PEAPEAUHODML__@@@Z; OdmlOpen(ushort const *,__MIDL___MIDL_itf_moshostapi_0000_0000_0001,HODML__ * *)
0x180006755  test    eax, eax
0x180006757  jns     short loc_180006764
0x180006759  mov     r8d, 91h
0x18000675f  jmp     loc_180006636
0x180006764  mov     edx, 2710h; unsigned int
0x180006769  mov     rcx, rsi; this
0x18000676c  call    ?WaitForNotification@CMapsUpdateTaskHandler@@AEAAJK@Z; CMapsUpdateTaskHandler::WaitForNotification(ulong)
0x180006771  test    eax, eax
0x180006773  jns     short loc_180006780
0x180006775  mov     r8d, 94h
0x18000677b  jmp     loc_180006636
0x180006780  mov     ecx, [rsi+44h]
0x180006783  test    ecx, ecx
0x180006785  jns     short loc_180006792
0x180006787  mov     r8d, 97h
0x18000678d  jmp     loc_180006638
0x180006792  mov     rcx, [rsp+720h+var_6D0]
0x180006797  call    cs:__imp_?OdmlStartCheckForUpdates@@YAJPEAUHODML__@@@Z; OdmlStartCheckForUpdates(HODML__ *)
0x18000679d  test    eax, eax
0x18000679f  jns     short loc_1800067AC
0x1800067a1  mov     r8d, 9Ah
0x1800067a7  jmp     loc_180006636
0x1800067ac  mov     edx, 7530h; unsigned int
0x1800067b1  mov     rcx, rsi; this
0x1800067b4  call    ?WaitForNotification@CMapsUpdateTaskHandler@@AEAAJK@Z; CMapsUpdateTaskHandler::WaitForNotification(ulong)
0x1800067b9  test    eax, eax
0x1800067bb  jns     short loc_1800067C8
0x1800067bd  mov     r8d, 9Dh
0x1800067c3  jmp     loc_180006636
0x1800067c8  mov     rdi, [rsi+38h]
0x1800067cc  test    rdi, rdi
0x1800067cf  jz      short loc_1800067EA
0x1800067d1  call    cs:__imp_GetLastError
0x1800067d7  mov     ebx, eax
0x1800067d9  mov     rcx, rdi
0x1800067dc  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x1800067e2  mov     ecx, ebx; dwErrCode
0x1800067e4  call    cs:__imp_SetLastError
0x1800067ea  mov     [rsi+38h], r15
0x1800067ee  mov     ecx, [rsi+44h]
0x1800067f1  test    ecx, ecx
0x1800067f3  jns     short loc_180006800
0x1800067f5  mov     r8d, 0A3h
0x1800067fb  jmp     loc_180006638
0x180006800  cmp     dword ptr [rsi+48h], 2
0x180006804  jnz     short loc_180006850
0x180006806  mov     [rsp+720h+var_6E0], r15d
0x18000680b  lea     rdx, [rsp+720h+var_6E0]
0x180006810  mov     rcx, [rsp+720h+var_6D0]
0x180006815  call    cs:__imp_?OdmlGetAutoUpdateEnabled@@YAJPEAUHODML__@@PEAH@Z; OdmlGetAutoUpdateEnabled(HODML__ *,int *)
0x18000681b  test    eax, eax
0x18000681d  jns     short loc_18000682A
0x18000681f  mov     r8d, 0ABh
0x180006825  jmp     loc_180006636
0x18000682a  cmp     [rsp+720h+var_6E0], r15d
0x18000682f  jnz     short loc_180006836
0x180006831  test    r13b, r13b
0x180006834  jz      short loc_180006850
0x180006836  mov     rcx, [rsp+720h+var_6D0]
0x18000683b  call    cs:__imp_?OdmlStartInstallUpdate@@YAJPEAUHODML__@@@Z; OdmlStartInstallUpdate(HODML__ *)
0x180006841  test    eax, eax
0x180006843  jns     short loc_180006850
0x180006845  mov     r8d, 0AFh
0x18000684b  jmp     loc_180006636
0x180006850  mov     ebx, r15d
0x180006853  mov     rcx, [rsp+720h+var_6D0]
0x180006858  test    rcx, rcx
0x18000685b  jz      short loc_180006864
0x18000685d  call    cs:__imp_?OdmlClose@@YAJPEAUHODML__@@@Z; OdmlClose(HODML__ *)
0x180006863  nop
0x180006864  xor     edx, edx; Val
0x180006866  mov     r8d, 670h; Size
0x18000686c  lea     rcx, [rsp+720h+var_6C0]; void *
0x180006871  call    memset_0
0x180006876  mov     [rsp+720h+var_6D8], r15
0x18000687b  lea     rdx, [rsp+720h+var_6D8]
0x180006880  mov     ecx, 5
0x180006885  call    cs:__imp_?MapsStorageOpen@@YAJW4__MIDL___MIDL_itf_moshostapi_0000_0000_0001@@PEAPEAUHMAPSSTORAGE__@@@Z; MapsStorageOpen(__MIDL___MIDL_itf_moshostapi_0000_0000_0001,HMAPSSTORAGE__ * *)
0x18000688b  test    eax, eax
0x18000688d  jns     short loc_1800068AC
0x18000688f  mov     r9, rsi
0x180006892  mov     r8d, 0F5h
0x180006898  lea     rdx, aCmapsupdatetas_3; "CMapsUpdateTaskHandler::SendTelemetry"
0x18000689f  mov     ecx, eax
0x1800068a1  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x1800068a7  jmp     loc_180006959
0x1800068ac  lea     rdx, [rsp+720h+var_6C0]
0x1800068b1  mov     rcx, [rsp+720h+var_6D8]
0x1800068b6  call    cs:__imp_?MapsStorageGetCurrentLocation@@YAJPEAUHMAPSSTORAGE__@@PEAU_STORAGE_DEVICE_DATA@@@Z; MapsStorageGetCurrentLocation(HMAPSSTORAGE__ *,_STORAGE_DEVICE_DATA *)
0x1800068bc  test    eax, eax
0x1800068be  jns     short loc_1800068D8
0x1800068c0  mov     r9, rsi
0x1800068c3  mov     r8d, 0F7h
0x1800068c9  lea     rdx, aCmapsupdatetas_3; "CMapsUpdateTaskHandler::SendTelemetry"
0x1800068d0  mov     ecx, eax
0x1800068d2  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x1800068d8  test    ebx, ebx
0x1800068da  jns     short loc_18000691D
0x1800068dc  cmp     [rsp+720h+var_6BC], r15d
0x1800068e1  setnz   dil
0x1800068e5  call    ?Instance@OfflineMapsTelemetry@@KAPEAV1@XZ; OfflineMapsTelemetry::Instance(void)
0x1800068ea  mov     rax, [rax+8]
0x1800068ee  test    rax, rax
0x1800068f1  jz      short loc_180006959
0x1800068f3  mov     eax, [rax]
0x1800068f5  test    eax, eax
0x1800068f7  jz      short loc_180006959
0x1800068f9  call    ?Instance@OfflineMapsTelemetry@@KAPEAV1@XZ; OfflineMapsTelemetry::Instance(void)
0x1800068fe  mov     [rsp+720h+var_700], ebx; int
0x180006902  mov     r9d, [rbp+620h+var_60]; unsigned int
0x180006909  mov     r8d, [rbp+620h+var_4AC]; unsigned int
0x180006910  mov     dl, dil; bool
0x180006913  mov     rcx, rax; this
0x180006916  call    ?UpdateTaskFailed_@OfflineMapsTelemetry@@QEAAX_NIIJ@Z; OfflineMapsTelemetry::UpdateTaskFailed_(bool,uint,uint,long)
0x18000691b  jmp     short loc_180006959
0x18000691d  cmp     [rsp+720h+var_6BC], r15d
0x180006922  setnz   dil
0x180006926  call    ?Instance@OfflineMapsTelemetry@@KAPEAV1@XZ; OfflineMapsTelemetry::Instance(void)
0x18000692b  mov     rax, [rax+8]
0x18000692f  test    rax, rax
0x180006932  jz      short loc_180006959
0x180006934  mov     eax, [rax]
0x180006936  test    eax, eax
0x180006938  jz      short loc_180006959
0x18000693a  call    ?Instance@OfflineMapsTelemetry@@KAPEAV1@XZ; OfflineMapsTelemetry::Instance(void)
0x18000693f  mov     r9d, [rbp+620h+var_60]; unsigned int
0x180006946  mov     r8d, [rbp+620h+var_4AC]; unsigned int
0x18000694d  mov     dl, dil; bool
0x180006950  mov     rcx, rax; this
0x180006953  call    ?UpdateTaskCompleted_@OfflineMapsTelemetry@@QEAAX_NII@Z; OfflineMapsTelemetry::UpdateTaskCompleted_(bool,uint,uint)
0x180006958  nop
0x180006959  mov     rcx, [rsp+720h+var_6D8]
0x18000695e  test    rcx, rcx
0x180006961  jz      short loc_18000696A
0x180006963  call    cs:__imp_?MapsStorageClose@@YAJPEAUHMAPSSTORAGE__@@@Z; MapsStorageClose(HMAPSSTORAGE__ *)
0x180006969  nop
0x18000696a  mov     eax, ebx
0x18000696c  mov     rcx, [rbp+620h+var_50]
0x180006973  xor     rcx, rsp; StackCookie
0x180006976  call    __security_check_cookie
0x18000697b  add     rsp, 6E8h
0x180006982  pop     r15
0x180006984  pop     r14
0x180006986  pop     r13
0x180006988  pop     r12
0x18000698a  pop     rdi
0x18000698b  pop     rsi
0x18000698c  pop     rbx
0x18000698d  pop     rbp
0x18000698e  retn
```
