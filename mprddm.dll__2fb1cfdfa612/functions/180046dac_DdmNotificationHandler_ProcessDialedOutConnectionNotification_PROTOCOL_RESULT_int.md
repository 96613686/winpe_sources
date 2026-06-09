# DdmNotificationHandler::ProcessDialedOutConnectionNotification(_PROTOCOL_RESULT *,int *)

- ea: `0x180046dac`
- end: `0x1800478f1`
- name: `?ProcessDialedOutConnectionNotification@DdmNotificationHandler@@CAKPEAU_PROTOCOL_RESULT@@PEAH@Z`
- size: `2885`
- prototype: `unsigned int __fastcall(struct _PROTOCOL_RESULT *, int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180047d20`

## callees

- `0x180007c50`
- `0x180008e08`
- `0x18001f4e0`
- `0x18003b7a8`
- `0x18003b8f4`
- `0x180046dac`
- `0x180071cec`
- `0x180073664`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `msvcrt!_itow_s` at `0x180046e73`
- `msvcrt!_itow_s` at `0x180046ffb`
- `msvcrt!_itow_s` at `0x18004713a`
- `msvcrt!_itow_s` at `0x180047285`
- `msvcrt!_itow_s` at `0x1800473a3`
- `msvcrt!_itow_s` at `0x180046e73`
- `msvcrt!_itow_s` at `0x180046ffb`
- `msvcrt!_itow_s` at `0x18004713a`
- `msvcrt!_itow_s` at `0x180047285`
- `msvcrt!_itow_s` at `0x1800473a3`
- `msvcrt!time` at `0x1800475e4`
- `msvcrt!time` at `0x1800475e4`
- `msvcrt!rand` at `0x18004760c`
- `msvcrt!rand` at `0x18004760c`
- `msvcrt!srand` at `0x1800475ed`
- `msvcrt!srand` at `0x1800475ed`
- `KERNEL32!SetEvent` at `0x1800478a6`
- `KERNEL32!SetEvent` at `0x1800478a6`
- `KERNEL32!CreateEventW` at `0x18004749e`
- `KERNEL32!CreateEventW` at `0x18004749e`
- `KERNEL32!WaitForSingleObject` at `0x180047511`
- `KERNEL32!WaitForSingleObject` at `0x180047511`
- `KERNEL32!LeaveCriticalSection` at `0x180046f42`
- `KERNEL32!LeaveCriticalSection` at `0x1800474e3`
- `KERNEL32!LeaveCriticalSection` at `0x180046f42`
- `KERNEL32!LeaveCriticalSection` at `0x1800474e3`
- `KERNEL32!EnterCriticalSection` at `0x180046ed5`
- `KERNEL32!EnterCriticalSection` at `0x180046ed5`
- `rtutils!RouterLogEventStringW` at `0x18004786d`
- `rtutils!RouterLogEventStringW` at `0x18004786d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DdmNotificationHandler::ProcessDialedOutConnectionNotification(struct _PROTOCOL_RESULT *a1, int *a2)
{
  struct DdmDeviceTable *Instance; // rax
  __int64 v4; // rsi
  int v5; // ecx
  DWORD dwErrorCode; // r14d
  int v7; // edi
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  struct _RTL_CRITICAL_SECTION *v13; // r13
  int v15; // ecx
  __int64 (__fastcall *v16)(__int64, __int64); // rbx
  __int64 v17; // rax
  struct IDimInterface *v18; // rax
  struct IDimInterface *v19; // rdi
  DWORD v20; // eax
  int v21; // ecx
  int v22; // ecx
  int v23; // ecx
  int v24; // ecx
  int v25; // ecx
  __int64 v26; // rbx
  int v27; // eax
  int v28; // eax
  __int64 v29; // rax
  __int64 v30; // rbx
  __int64 v31; // rax
  struct IDimInterface *v32; // rcx
  bool v33; // zf
  __int64 (__fastcall *v34)(struct IDimInterface *, LPWSTR *); // rax
  LPWSTR *v35; // rdx
  __int128 *v36; // rax
  int v37; // eax
  __int64 v38; // rax
  __int64 v39; // rbx
  __int64 v40; // rax
  struct IDimInterface *v41; // rcx
  __int64 (__fastcall *v42)(struct IDimInterface *, _BYTE *); // rax
  LPWSTR *v43; // rdx
  __int128 *v44; // rax
  HANDLE EventW; // r12
  __int64 v46; // rbx
  __int64 v47; // rbx
  int v48; // eax
  unsigned int v49; // eax
  __int64 v50; // rax
  __int64 v51; // rbx
  int v52; // eax
  __int64 v53; // rbx
  int v54; // eax
  __int64 v55; // rax
  __int64 v56; // rbx
  int v57; // eax
  __int64 v58; // rdx
  __int64 v59; // rdx
  void *v60; // rax
  char v61; // [rsp+40h] [rbp-C0h]
  int v62; // [rsp+44h] [rbp-BCh]
  __int64 v63; // [rsp+48h] [rbp-B8h] BYREF
  int *v64; // [rsp+50h] [rbp-B0h]
  __int128 v65; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v66[16]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v67[16]; // [rsp+78h] [rbp-88h] BYREF
  LPWSTR v68[2]; // [rsp+88h] [rbp-78h] BYREF
  LPWSTR plpszSubStringArray[2]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v70; // [rsp+A8h] [rbp-58h]
  wchar_t Buffer[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v72; // [rsp+B4h] [rbp-4Ch]
  __int128 v73; // [rsp+C4h] [rbp-3Ch]
  int v74; // [rsp+D4h] [rbp-2Ch]
  _OWORD v75[3]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v76[30]; // [rsp+110h] [rbp+10h]
  __int16 v77; // [rsp+12Eh] [rbp+2Eh]
  int v78; // [rsp+130h] [rbp+30h] BYREF
  char v79[2044]; // [rsp+134h] [rbp+34h] BYREF

  v64 = a2;
  v63 = 0;
  v62 = 1;
  v78 = 0;
  memset_0(v79, 0, sizeof(v79));
  *(_DWORD *)Buffer = 0;
  v72 = 0;
  v73 = 0;
  v74 = 0;
  v65 = 0;
  Instance = DdmDeviceTable::GetInstance(0x11u);
  DdmDeviceTable::FindDevice(Instance, *((_QWORD *)a1 + 2), &v63);
  v4 = v63;
  if ( v63 )
  {
    dwErrorCode = 0;
    v7 = 0;
    EnterCriticalSection((LPCRITICAL_SECTION)(v63 + 16));
    v8 = *((_DWORD *)a1 + 3);
    if ( v8 > 11 )
    {
      v22 = v8 - 12;
      if ( v22 )
      {
        v23 = v22 - 1;
        if ( v23 )
        {
          v24 = v23 - 1;
          if ( v24 )
          {
            v25 = v24 - 1;
            if ( v25 )
            {
              if ( (unsigned int)(v25 - 1) >= 2 )
                goto LABEL_48;
            }
          }
        }
      }
    }
    else if ( v8 != 11 )
    {
      if ( v8 )
      {
        v9 = v8 - 1;
        if ( !v9 )
        {
          v20 = (*(__int64 (__fastcall **)(__int64, struct _PROTOCOL_RESULT *))(*(_QWORD *)v4 + 320LL))(v4, a1);
          dwErrorCode = v20;
          if ( (*(_BYTE *)(v4 + 132) & 8) != 0 )
          {
            (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v4 + 80LL))(v4, v20);
            goto LABEL_17;
          }
          v61 = 1;
          goto LABEL_25;
        }
        v10 = v9 - 2;
        if ( !v10 )
        {
LABEL_17:
          v13 = (struct _RTL_CRITICAL_SECTION *)(v4 + 16);
LABEL_18:
          LeaveCriticalSection(v13);
          goto LABEL_19;
        }
        v11 = v10 - 1;
        if ( v11 )
        {
          v12 = v11 - 3;
          if ( v12 )
          {
            if ( v12 == 3 )
            {
              (*(void (__fastcall **)(__int64, struct _PROTOCOL_RESULT *))(*(_QWORD *)v4 + 336LL))(v4, a1);
              goto LABEL_17;
            }
LABEL_48:
            v62 = 0;
            goto LABEL_17;
          }
        }
        else
        {
          dwErrorCode = (*(__int64 (__fastcall **)(__int64, struct _PROTOCOL_RESULT *))(*(_QWORD *)v4 + 328LL))(v4, a1);
          LOBYTE(v7) = dwErrorCode != 0;
        }
      }
      else
      {
        dwErrorCode = (*(__int64 (__fastcall **)(__int64, struct _PROTOCOL_RESULT *))(*(_QWORD *)v4 + 312LL))(v4, a1);
        if ( dwErrorCode )
        {
          if ( (byte_1800C8404 & 8) != 0 )
          {
            LOWORD(v78) = 0;
            Buffer[0] = 0;
            if ( v4 )
            {
              v21 = *(_DWORD *)(v4 + 96);
              if ( v21 != -1 )
                _itow_s(v21, Buffer, 0x14u, 10);
            }
            FormatRRASErrorString(&v78, L"Post connect processing failed. dwError=0x%x. Dicconnecting...", dwErrorCode);
            if ( (byte_1800C8404 & 8) != 0 )
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RasDdmParamTraceError,
                (unsigned int)&v78,
                (unsigned int)&v65,
                0,
                (__int64)Buffer);
          }
          v7 = 1;
        }
      }
    }
    v61 = 1;
    if ( !v7 )
      goto LABEL_17;
LABEL_25:
    if ( (byte_1800C8404 & 8) != 0 )
    {
      LOWORD(v78) = 0;
      Buffer[0] = 0;
      v15 = *((_DWORD *)a1 + 4);
      if ( v15 != -1 )
        _itow_s(v15, Buffer, 0x14u, 10);
      FormatRRASErrorString(
        &v78,
        L"S2S interface dialing out failed (hport: %ld): Error: %d",
        *((_QWORD *)a1 + 2),
        dwErrorCode);
      if ( (byte_1800C8404 & 8) != 0 )
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasDdmParamTraceError,
          (unsigned int)&v78,
          (unsigned int)&v65,
          0,
          (__int64)Buffer);
    }
    (**(void (__fastcall ***)(__int64))g_pIDimInterfaceTable)(g_pIDimInterfaceTable);
    v16 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)g_pIDimInterfaceTable + 64LL);
    v17 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 304LL))(v4);
    v18 = (struct IDimInterface *)v16(g_pIDimInterfaceTable, v17);
    v19 = v18;
    if ( !v18 )
    {
      dwErrorCode = 905;
      v13 = (struct _RTL_CRITICAL_SECTION *)(v4 + 16);
      goto LABEL_99;
    }
    (**(void (__fastcall ***)(struct IDimInterface *))v18)(v18);
    v26 = *(_QWORD *)v19;
    v27 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v19 + 152LL))(v19);
    (*(void (__fastcall **)(struct IDimInterface *, _QWORD))(v26 + 160))(v19, (unsigned int)(v27 - 1));
    (*(void (__fastcall **)(struct IDimInterface *, _QWORD))(*(_QWORD *)v19 + 32LL))(v19, dwErrorCode);
    if ( !(*(unsigned int (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v19 + 152LL))(v19)
      && *(_DWORD *)(v4 + 128) == 4
      && (*(unsigned int (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v19 + 40LL))(v19) == 2 )
    {
      v13 = (struct _RTL_CRITICAL_SECTION *)(v4 + 16);
      goto LABEL_96;
    }
    if ( (byte_1800C8404 & 0x10) == 0 )
      goto LABEL_75;
    LOWORD(v78) = 0;
    Buffer[0] = 0;
    v28 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v19 + 264LL))(v19);
    if ( v28 == -1 )
      Buffer[0] = 0;
    else
      _itow_s(v28, Buffer, 0x14u, 10);
    v29 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v19 + 280LL))(v19);
    FormatRRASErrorString(
      &v78,
      L"%s:Could not connect to interface %ws",
      L"DdmNotificationHandler::ProcessDialedOutConnectionNotification",
      v29);
    if ( (byte_1800C8404 & 0x10) == 0 )
    {
LABEL_75:
      EventW = *(HANDLE *)(v4 + 11448);
      if ( !EventW )
        EventW = CreateEventW(0, 1, 0, 0);
      if ( (*(unsigned int (__fastcall **)(__int64, HANDLE))(*(_QWORD *)v4 + 160LL))(v4, EventW) == 600 )
      {
        v46 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 304LL))(v4);
        v13 = (struct _RTL_CRITICAL_SECTION *)(v4 + 16);
        LeaveCriticalSection((LPCRITICAL_SECTION)(v4 + 16));
        (*(void (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v19 + 8LL))(v19);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)g_pIDimInterfaceTable + 16LL))(g_pIDimInterfaceTable);
        WaitForSingleObject(EventW, 0xFFFFFFFF);
        (**(void (__fastcall ***)(__int64))g_pIDimInterfaceTable)(g_pIDimInterfaceTable);
        v19 = (struct IDimInterface *)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)g_pIDimInterfaceTable
                                                                                  + 64LL))(
                                        g_pIDimInterfaceTable,
                                        v46);
        v61 = 0;
        if ( !v19 )
        {
          dwErrorCode = 905;
          goto LABEL_99;
        }
      }
      else
      {
        v13 = (struct _RTL_CRITICAL_SECTION *)(v4 + 16);
      }
      (**(void (__fastcall ***)(struct IDimInterface *))v19)(v19);
      (*(void (__fastcall **)(struct IDimInterface *, _QWORD))(*(_QWORD *)v19 + 272LL))(v19, 0);
      if ( !(*(unsigned __int8 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v19 + 56LL))(v19)
        && (*(unsigned int (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v19 + 184LL))(v19)
        && (*(_DWORD *)(v4 + 132) & 0x100000) == 0 )
      {
        v47 = *(_QWORD *)v19;
        v48 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v19 + 184LL))(v19);
        (*(void (__fastcall **)(struct IDimInterface *, _QWORD))(v47 + 192))(v19, (unsigned int)(v48 - 1));
        v49 = time(0);
        srand(v49);
        LODWORD(v47) = 2 * (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v19 + 200LL))(v19) + 1;
        LODWORD(v47) = rand() % (unsigned int)v47;
        v50 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v19 + 16LL))(v19);
        if ( !(unsigned int)TimerQInsert(v50, (unsigned int)v47, ReConnectInterface) )
        {
          v51 = *(_QWORD *)v19;
          v52 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v19 + 104LL))(v19);
          (*(void (__fastcall **)(struct IDimInterface *, _QWORD))(v51 + 112))(v19, v52 | 0x800u);
        }
LABEL_98:
        (*(void (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v19 + 8LL))(v19);
LABEL_99:
        (*(void (__fastcall **)(__int64))(*(_QWORD *)g_pIDimInterfaceTable + 16LL))(g_pIDimInterfaceTable);
        if ( !v61 )
          goto LABEL_19;
        goto LABEL_18;
      }
      if ( !(*(unsigned __int8 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v19 + 56LL))(v19) )
      {
        v53 = *(_QWORD *)v19;
        v54 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v19 + 104LL))(v19);
        (*(void (__fastcall **)(struct IDimInterface *, _QWORD))(v53 + 112))(v19, v54 | 0x20u);
      }
      if ( (byte_1800C8404 & 0x10) != 0 )
      {
        LOWORD(v78) = 0;
        Buffer[0] = 0;
        v55 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v19 + 280LL))(v19);
        FormatRRASErrorString(
          &v78,
          L"%s: Marking interface '%ws' DISCONNECTED.",
          L"DdmNotificationHandler::ProcessDialedOutConnectionNotification",
          v55);
        if ( (byte_1800C8404 & 0x10) != 0 )
        {
          v56 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v19 + 280LL))(v19);
          v57 = (*(__int64 (__fastcall **)(struct IDimInterface *, LPWSTR *))(*(_QWORD *)v19 + 360LL))(
                  v19,
                  plpszSubStringArray);
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasDdmParamTraceInfo,
            (unsigned int)&v78,
            v57,
            v56,
            (__int64)Buffer);
        }
      }
      InterfaceDisconnected(v19);
      (*(void (__fastcall **)(struct IDimInterface *, _QWORD, __int64, _QWORD))(*(_QWORD *)v19 + 440LL))(
        v19,
        0,
        1,
        (unsigned int)dword_1800C8658);
      if ( (*(unsigned __int8 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v19 + 56LL))(v19) )
      {
        LOBYTE(v58) = 1;
        (*(void (__fastcall **)(struct IDimInterface *, __int64, __int64, _QWORD))(*(_QWORD *)v19 + 440LL))(
          v19,
          v58,
          1,
          (unsigned int)dword_1800C8658);
      }
      (*(void (__fastcall **)(struct IDimInterface *, _QWORD))(*(_QWORD *)v19 + 32LL))(v19, dwErrorCode);
      *(_OWORD *)plpszSubStringArray = 0;
      v70 = 0;
      v75[0] = *(_OWORD *)L"{00000000-0000-0000-0000-000000000000}";
      v75[1] = *(_OWORD *)L"0-0000-0000-0000-000000000000}";
      v75[2] = *(_OWORD *)L"000-0000-000000000000}";
      *(_OWORD *)v76 = *(_OWORD *)L"-000000000000}";
      *(_OWORD *)&v76[14] = *(_OWORD *)L"000000}";
      v77 = 0;
      (*(void (__fastcall **)(struct IDimInterface *, _BYTE *))(*(_QWORD *)v19 + 360LL))(v19, v66);
      MprConvertGuidToString(v66, v59, v75);
      plpszSubStringArray[0] = (LPWSTR)v75;
      plpszSubStringArray[1] = (LPWSTR)(*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v19 + 280LL))(v19);
      v70 = v4 + 714;
      if ( dword_1800C84E4 )
        RouterLogEventStringW(hLogHandle, 1u, 0x4E8Fu, 3u, plpszSubStringArray, dwErrorCode, 3u);
LABEL_96:
      if ( (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v19 + 224LL))(v19) != -1 )
      {
        v60 = (void *)(*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v19 + 224LL))(v19);
        SetEvent(v60);
        (*(void (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v19 + 240LL))(v19);
      }
      goto LABEL_98;
    }
    v30 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v19 + 280LL))(v19);
    v31 = (*(__int64 (__fastcall **)(struct IDimInterface *, _BYTE *))(*(_QWORD *)v19 + 360LL))(v19, v66);
    v32 = v19;
    v33 = v31 == 0;
    v34 = *(__int64 (__fastcall **)(struct IDimInterface *, LPWSTR *))(*(_QWORD *)v19 + 360LL);
    if ( v33 )
    {
      if ( !v34(v19, v68) )
      {
        v36 = &v65;
        goto LABEL_63;
      }
      v35 = plpszSubStringArray;
      v32 = v19;
      v34 = *(__int64 (__fastcall **)(struct IDimInterface *, LPWSTR *))(*(_QWORD *)v19 + 360LL);
    }
    else
    {
      v35 = (LPWSTR *)v67;
    }
    LODWORD(v36) = v34(v32, v35);
LABEL_63:
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasDdmParamTraceInfo,
      (unsigned int)&v78,
      (_DWORD)v36,
      v30,
      (__int64)Buffer);
    if ( (byte_1800C8404 & 0x10) == 0 )
      goto LABEL_75;
    LOWORD(v78) = 0;
    Buffer[0] = 0;
    v37 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v19 + 264LL))(v19);
    if ( v37 == -1 )
      Buffer[0] = 0;
    else
      _itow_s(v37, Buffer, 0x14u, 10);
    v38 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v19 + 264LL))(v19);
    FormatRRASErrorString(
      &v78,
      L"%s: hanging up 0x%x",
      L"DdmNotificationHandler::ProcessDialedOutConnectionNotification",
      v38);
    if ( (byte_1800C8404 & 0x10) == 0 )
      goto LABEL_75;
    v39 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v19 + 280LL))(v19);
    v40 = (*(__int64 (__fastcall **)(struct IDimInterface *, LPWSTR *))(*(_QWORD *)v19 + 360LL))(
            v19,
            plpszSubStringArray);
    v41 = v19;
    v33 = v40 == 0;
    v42 = *(__int64 (__fastcall **)(struct IDimInterface *, _BYTE *))(*(_QWORD *)v19 + 360LL);
    if ( v33 )
    {
      if ( !v42(v19, v67) )
      {
        v44 = &v65;
        goto LABEL_74;
      }
      v43 = v66;
      v41 = v19;
      v42 = *(__int64 (__fastcall **)(struct IDimInterface *, _BYTE *))(*(_QWORD *)v19 + 360LL);
    }
    else
    {
      v43 = v68;
    }
    LODWORD(v44) = v42(v41, (LPWSTR *)v43);
LABEL_74:
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasDdmParamTraceInfo,
      (unsigned int)&v78,
      (_DWORD)v44,
      v39,
      (__int64)Buffer);
    goto LABEL_75;
  }
  if ( (byte_1800C8404 & 0x10) != 0 )
  {
    LOWORD(v78) = 0;
    Buffer[0] = 0;
    v5 = *((_DWORD *)a1 + 4);
    if ( v5 != -1 )
      _itow_s(v5, Buffer, (unsigned int)(v63 + 20), v63 + 10);
    FormatRRASErrorString(&v78, L"No device found for port: %ld", *((_QWORD *)a1 + 2));
    if ( (byte_1800C8404 & 0x10) != 0 )
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceInfo,
        (unsigned int)&v78,
        (unsigned int)&v65,
        0,
        (__int64)Buffer);
  }
  dwErrorCode = 1168;
LABEL_19:
  *v64 = v62;
  if ( v4 && _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 8), 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(__int64, __int64))v4)(v4, 1);
  return dwErrorCode;
}

```

## disassembly

```asm
0x180046dac  mov     [rsp-8+arg_10], rbx
0x180046db1  mov     [rsp-8+arg_18], rsi
0x180046db6  push    rbp
0x180046db7  push    rdi
0x180046db8  push    r12
0x180046dba  push    r13
0x180046dbc  push    r14
0x180046dbe  lea     rbp, [rsp-840h]
0x180046dc6  sub     rsp, 940h
0x180046dcd  mov     rax, cs:__security_cookie
0x180046dd4  xor     rax, rsp
0x180046dd7  mov     [rbp+860h+var_30], rax
0x180046dde  mov     [rsp+960h+var_910], rdx
0x180046de3  mov     rbx, rcx
0x180046de6  mov     [rsp+960h+var_918], 0
0x180046def  mov     [rsp+960h+var_91C], 1
0x180046df7  xor     eax, eax
0x180046df9  mov     [rbp+860h+var_830], eax
0x180046dfc  xor     edx, edx; Val
0x180046dfe  mov     r8d, 7FCh; Size
0x180046e04  lea     rcx, [rbp+860h+var_82C]; void *
0x180046e08  call    memset_0
0x180046e0d  xor     eax, eax
0x180046e0f  mov     dword ptr [rbp+860h+Buffer], eax
0x180046e12  xorps   xmm0, xmm0
0x180046e15  movups  [rbp+860h+var_8AC], xmm0
0x180046e19  movups  [rbp+860h+var_89C], xmm0
0x180046e1d  mov     [rbp+860h+var_88C], eax
0x180046e20  movups  [rsp+960h+var_908], xmm0
0x180046e25  lea     ecx, [rax+11h]; unsigned int
0x180046e28  call    ?GetInstance@DdmDeviceTable@@SAPEAV1@K@Z; DdmDeviceTable::GetInstance(ulong)
0x180046e2d  lea     r8, [rsp+960h+var_918]
0x180046e32  mov     rdx, [rbx+10h]
0x180046e36  mov     rcx, rax
0x180046e39  call    ?FindDevice@DdmDeviceTable@@QEAAXPEAXAEAV?$RasObjPtr@VDdmDevice@@@@@Z; DdmDeviceTable::FindDevice(void *,RasObjPtr<DdmDevice> &)
0x180046e3e  mov     rsi, [rsp+960h+var_918]
0x180046e43  test    rsi, rsi
0x180046e46  jnz     loc_180046ECC
0x180046e4c  test    cs:byte_1800C8404, 10h
0x180046e53  jz      short loc_180046EC4
0x180046e55  xor     eax, eax
0x180046e57  mov     word ptr [rbp+860h+var_830], ax
0x180046e5b  mov     [rbp+860h+Buffer], ax
0x180046e5f  mov     ecx, [rbx+10h]; Value
0x180046e62  cmp     ecx, 0FFFFFFFFh
0x180046e65  jz      short loc_180046E79
0x180046e67  lea     r9d, [rsi+0Ah]; Radix
0x180046e6b  lea     r8d, [rsi+14h]; BufferCount
0x180046e6f  lea     rdx, [rbp+860h+Buffer]; Buffer
0x180046e73  call    cs:__imp__itow_s
0x180046e79  mov     r8, [rbx+10h]
0x180046e7d  lea     rdx, aNoDeviceFoundF; "No device found for port: %ld"
0x180046e84  lea     rcx, [rbp+860h+var_830]
0x180046e88  call    FormatRRASErrorString
0x180046e8d  test    cs:byte_1800C8404, 10h
0x180046e94  jz      short loc_180046EC4
0x180046e96  lea     rax, [rbp+860h+Buffer]
0x180046e9a  mov     qword ptr [rsp+960h+dwErrorCode], rax
0x180046e9f  mov     [rsp+960h+plpszSubStringArray], 0
0x180046ea8  lea     r9, [rsp+960h+var_908]
0x180046ead  lea     r8, [rbp+860h+var_830]
0x180046eb1  lea     rdx, RasDdmParamTraceInfo
0x180046eb8  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180046ebf  call    McTemplateU0zjzz_EventWriteTransfer
0x180046ec4  mov     r14d, 490h
0x180046eca  jmp     short loc_180046F48
0x180046ecc  xor     r14d, r14d
0x180046ecf  xor     edi, edi
0x180046ed1  lea     rcx, [rsi+10h]; lpCriticalSection
0x180046ed5  call    cs:__imp_EnterCriticalSection
0x180046edb  mov     ecx, [rbx+0Ch]
0x180046ede  lea     r12d, [r14+0Ah]
0x180046ee2  lea     r13d, [r14+14h]
0x180046ee6  cmp     ecx, 0Bh
0x180046ee9  jg      loc_180047190
0x180046eef  jz      loc_180046FC9
0x180046ef5  test    ecx, ecx
0x180046ef7  jz      loc_1800470F0
0x180046efd  sub     ecx, 1
0x180046f00  jz      loc_1800470AE
0x180046f06  sub     ecx, 2
0x180046f09  jz      short loc_180046F3B
0x180046f0b  sub     ecx, 1
0x180046f0e  jz      loc_180046FAB
0x180046f14  sub     ecx, 3
0x180046f17  jz      loc_180046FC9
0x180046f1d  cmp     ecx, 3
0x180046f20  jnz     loc_1800471C6
0x180046f26  mov     rax, [rsi]
0x180046f29  mov     rdx, rbx
0x180046f2c  mov     rcx, rsi
0x180046f2f  mov     rax, [rax+150h]
0x180046f36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046f3b  lea     r13, [rsi+10h]
0x180046f3f  mov     rcx, r13; lpCriticalSection
0x180046f42  call    cs:__imp_LeaveCriticalSection
0x180046f48  mov     eax, [rsp+960h+var_91C]
0x180046f4c  mov     rcx, [rsp+960h+var_910]
0x180046f51  mov     [rcx], eax
0x180046f53  test    rsi, rsi
0x180046f56  jz      short loc_180046F7D
0x180046f58  or      eax, 0FFFFFFFFh
0x180046f5b  lock xadd [rsi+8], eax
0x180046f60  cmp     eax, 1
0x180046f63  jnz     short loc_180046F7D
0x180046f65  test    rsi, rsi
0x180046f68  jz      short loc_180046F7D
0x180046f6a  mov     rax, [rsi]
0x180046f6d  mov     edx, 1
0x180046f72  mov     rcx, rsi
0x180046f75  mov     rax, [rax]
0x180046f78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046f7d  mov     eax, r14d
0x180046f80  mov     rcx, [rbp+860h+var_30]
0x180046f87  xor     rcx, rsp; StackCookie
0x180046f8a  call    __security_check_cookie
0x180046f8f  lea     r11, [rsp+960h+var_20]
0x180046f97  mov     rbx, [r11+40h]
0x180046f9b  mov     rsi, [r11+48h]
0x180046f9f  mov     rsp, r11
0x180046fa2  pop     r14
0x180046fa4  pop     r13
0x180046fa6  pop     r12
0x180046fa8  pop     rdi
0x180046fa9  pop     rbp
0x180046faa  retn
0x180046fab  mov     rax, [rsi]
0x180046fae  mov     rdx, rbx
0x180046fb1  mov     rcx, rsi
0x180046fb4  mov     rax, [rax+148h]
0x180046fbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046fc0  mov     r14d, eax
0x180046fc3  test    eax, eax
0x180046fc5  setnz   dil
0x180046fc9  mov     [rsp+960h+var_920], 1
0x180046fce  test    edi, edi
0x180046fd0  jz      loc_180046F3B
0x180046fd6  test    cs:byte_1800C8404, 8
0x180046fdd  jz      short loc_18004704F
0x180046fdf  xor     eax, eax
0x180046fe1  mov     word ptr [rbp+860h+var_830], ax
0x180046fe5  mov     [rbp+860h+Buffer], ax
0x180046fe9  mov     ecx, [rbx+10h]; Value
0x180046fec  cmp     ecx, 0FFFFFFFFh
0x180046fef  jz      short loc_180047001
0x180046ff1  mov     r9d, r12d; Radix
0x180046ff4  mov     r8, r13; BufferCount
0x180046ff7  lea     rdx, [rbp+860h+Buffer]; Buffer
0x180046ffb  call    cs:__imp__itow_s
0x180047001  mov     r9d, r14d
0x180047004  mov     r8, [rbx+10h]
0x180047008  lea     rdx, aS2sInterfaceDi; "S2S interface dialing out failed (hport"...
0x18004700f  lea     rcx, [rbp+860h+var_830]
0x180047013  call    FormatRRASErrorString
0x180047018  test    cs:byte_1800C8404, 8
0x18004701f  jz      short loc_18004704F
0x180047021  lea     rax, [rbp+860h+Buffer]
0x180047025  mov     qword ptr [rsp+960h+dwErrorCode], rax
0x18004702a  mov     [rsp+960h+plpszSubStringArray], 0
0x180047033  lea     r9, [rsp+960h+var_908]
0x180047038  lea     r8, [rbp+860h+var_830]
0x18004703c  lea     rdx, RasDdmParamTraceError
0x180047043  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004704a  call    McTemplateU0zjzz_EventWriteTransfer
0x18004704f  mov     rcx, cs:g_pIDimInterfaceTable
0x180047056  mov     rax, [rcx]
0x180047059  mov     rax, [rax]
0x18004705c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047061  mov     rax, cs:g_pIDimInterfaceTable
0x180047068  mov     rcx, [rax]
0x18004706b  mov     rbx, [rcx+40h]
0x18004706f  mov     rcx, [rsi]
0x180047072  mov     rax, [rcx+130h]
0x180047079  mov     rcx, rsi
0x18004707c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047081  mov     rdx, rax
0x180047084  mov     rcx, cs:g_pIDimInterfaceTable
0x18004708b  mov     rax, rbx
0x18004708e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047093  mov     rdi, rax
0x180047096  test    rax, rax
0x180047099  jnz     loc_1800471CF
0x18004709f  mov     r14d, 389h
0x1800470a5  lea     r13, [rsi+10h]
0x1800470a9  jmp     loc_1800478CD
0x1800470ae  mov     rax, [rsi]
0x1800470b1  mov     rdx, rbx
0x1800470b4  mov     rcx, rsi
0x1800470b7  mov     rax, [rax+140h]
0x1800470be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800470c3  mov     r14d, eax
0x1800470c6  test    byte ptr [rsi+84h], 8
0x1800470cd  jnz     short loc_1800470D9
0x1800470cf  mov     [rsp+960h+var_920], 1
0x1800470d4  jmp     loc_180046FD6
0x1800470d9  mov     rax, [rsi]
0x1800470dc  mov     edx, r14d
0x1800470df  mov     rcx, rsi
0x1800470e2  mov     rax, [rax+50h]
0x1800470e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800470eb  jmp     loc_180046F3B
0x1800470f0  mov     rax, [rsi]
0x1800470f3  mov     rdx, rbx
0x1800470f6  mov     rcx, rsi
0x1800470f9  mov     rax, [rax+138h]
0x180047100  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047105  mov     r14d, eax
0x180047108  test    eax, eax
0x18004710a  jz      loc_180046FC9
0x180047110  test    cs:byte_1800C8404, 8
0x180047117  jz      short loc_180047186
0x180047119  xor     eax, eax
0x18004711b  mov     word ptr [rbp+860h+var_830], ax
0x18004711f  mov     [rbp+860h+Buffer], ax
0x180047123  test    rsi, rsi
0x180047126  jz      short loc_180047140
0x180047128  mov     ecx, [rsi+60h]; Value
0x18004712b  cmp     ecx, 0FFFFFFFFh
0x18004712e  jz      short loc_180047140
0x180047130  mov     r9d, r12d; Radix
0x180047133  mov     r8, r13; BufferCount
0x180047136  lea     rdx, [rbp+860h+Buffer]; Buffer
0x18004713a  call    cs:__imp__itow_s
0x180047140  mov     r8d, r14d
0x180047143  lea     rdx, aPostConnectPro; "Post connect processing failed. dwError"...
0x18004714a  lea     rcx, [rbp+860h+var_830]
0x18004714e  call    FormatRRASErrorString
0x180047153  test    cs:byte_1800C8404, 8
0x18004715a  jz      short loc_180047186
0x18004715c  lea     rax, [rbp+860h+Buffer]
0x180047160  mov     qword ptr [rsp+960h+dwErrorCode], rax
0x180047165  mov     [rsp+960h+plpszSubStringArray], rdi
0x18004716a  lea     r9, [rsp+960h+var_908]
0x18004716f  lea     r8, [rbp+860h+var_830]
0x180047173  lea     rdx, RasDdmParamTraceError
0x18004717a  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180047181  call    McTemplateU0zjzz_EventWriteTransfer
0x180047186  mov     edi, 1
0x18004718b  jmp     loc_180046FC9
0x180047190  sub     ecx, 0Ch
0x180047193  jz      loc_180046FC9
0x180047199  sub     ecx, 1
0x18004719c  jz      loc_180046FC9
0x1800471a2  sub     ecx, 1
0x1800471a5  jz      loc_180046FC9
0x1800471ab  sub     ecx, 1
0x1800471ae  jz      loc_180046FC9
0x1800471b4  sub     ecx, 1
0x1800471b7  jz      loc_180046FC9
0x1800471bd  cmp     ecx, 1
0x1800471c0  jz      loc_180046FC9
0x1800471c6  mov     [rsp+960h+var_91C], edi
0x1800471ca  jmp     loc_180046F3B
0x1800471cf  mov     rax, [rax]
0x1800471d2  mov     rcx, rdi
0x1800471d5  mov     rax, [rax]
0x1800471d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800471dd  mov     rbx, [rdi]
0x1800471e0  mov     rcx, rdi
0x1800471e3  mov     rax, [rbx+98h]
0x1800471ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800471ef  lea     edx, [rax-1]
0x1800471f2  mov     rcx, rdi
0x1800471f5  mov     rax, [rbx+0A0h]
0x1800471fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047201  mov     rax, [rdi]
0x180047204  mov     edx, r14d
0x180047207  mov     rcx, rdi
0x18004720a  mov     rax, [rax+20h]
0x18004720e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047213  mov     rax, [rdi]
0x180047216  mov     rcx, rdi
0x180047219  mov     rax, [rax+98h]
0x180047220  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047225  test    eax, eax
0x180047227  jnz     short loc_18004724A
0x180047229  cmp     dword ptr [rsi+80h], 4
0x180047230  jnz     short loc_18004724A
0x180047232  mov     rax, [rdi]
0x180047235  mov     rcx, rdi
0x180047238  mov     rax, [rax+28h]
0x18004723c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047241  cmp     eax, 2
0x180047244  jz      loc_180047875
0x18004724a  mov     al, cs:byte_1800C8404
0x180047250  test    al, 10h
0x180047252  jz      loc_180047485
0x180047258  xor     eax, eax
0x18004725a  mov     word ptr [rbp+860h+var_830], ax
0x18004725e  mov     [rbp+860h+Buffer], ax
0x180047262  mov     rax, [rdi]
0x180047265  mov     rcx, rdi
0x180047268  mov     rax, [rax+108h]
0x18004726f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047274  cmp     eax, 0FFFFFFFFh
0x180047277  jz      short loc_18004728D
0x180047279  mov     r9d, r12d; Radix
0x18004727c  mov     r8, r13; BufferCount
0x18004727f  lea     rdx, [rbp+860h+Buffer]; Buffer
0x180047283  mov     ecx, eax; Value
  ... truncated ...
```
