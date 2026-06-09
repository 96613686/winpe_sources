# DdmNotificationHandler::ProcessDialedOutConnectionNotification(_PROTOCOL_RESULT *,int *)

- ea: `0x180047ed4`
- end: `0x180048a45`
- name: `?ProcessDialedOutConnectionNotification@DdmNotificationHandler@@CAKPEAU_PROTOCOL_RESULT@@PEAH@Z`
- size: `2929`
- prototype: `unsigned int __fastcall(struct _PROTOCOL_RESULT *, int *)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180048e90`

## callees

- `0x180007d00`
- `0x180008efc`
- `0x180020130`
- `0x18003d100`
- `0x18003d278`
- `0x180047ed4`
- `0x180075588`
- `0x1800755b8`
- `0x1800771b8`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `msvcrt!time` at `0x1800486b3`
- `msvcrt!time` at `0x1800486b3`
- `msvcrt!rand` at `0x1800486e7`
- `msvcrt!rand` at `0x1800486e7`
- `msvcrt!srand` at `0x1800486c2`
- `msvcrt!srand` at `0x1800486c2`
- `KERNEL32!SetEvent` at `0x1800489b3`
- `KERNEL32!SetEvent` at `0x1800489b3`
- `KERNEL32!CreateEventW` at `0x18004855a`
- `KERNEL32!CreateEventW` at `0x18004855a`
- `KERNEL32!WaitForSingleObject` at `0x1800485d6`
- `KERNEL32!WaitForSingleObject` at `0x1800485d6`
- `KERNEL32!LeaveCriticalSection` at `0x1800480be`
- `KERNEL32!LeaveCriticalSection` at `0x1800485a2`
- `KERNEL32!LeaveCriticalSection` at `0x1800480be`
- `KERNEL32!LeaveCriticalSection` at `0x1800485a2`
- `KERNEL32!EnterCriticalSection` at `0x180048054`
- `KERNEL32!EnterCriticalSection` at `0x180048054`
- `rtutils!RouterLogEventStringW` at `0x18004897a`
- `rtutils!RouterLogEventStringW` at `0x18004897a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DdmNotificationHandler::ProcessDialedOutConnectionNotification(struct _PROTOCOL_RESULT *a1, int *a2)
{
  BOOL v3; // esi
  DWORD dwErrorCode; // r14d
  struct DdmDeviceTable *Instance; // rax
  _BYTE *v6; // rbx
  int v7; // edi
  struct _RTL_CRITICAL_SECTION *v9; // r15
  char v10; // r13
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  DWORD v16; // eax
  __int64 v17; // rdx
  __int64 (__fastcall *v18)(__int64, __int64); // rdi
  __int64 v19; // rax
  struct IDimInterface *v20; // rax
  struct IDimInterface *v21; // rsi
  void (__fastcall *v22)(struct IDimInterface *, _QWORD); // rdi
  int v23; // eax
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rdi
  __int64 v27; // rax
  struct IDimInterface *v28; // rcx
  bool v29; // zf
  __int64 (__fastcall *v30)(struct IDimInterface *, char *); // rax
  char *v31; // rdx
  __int128 *v32; // rax
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // rdi
  __int64 v36; // rax
  struct IDimInterface *v37; // rcx
  __int64 (__fastcall *v38)(struct IDimInterface *, char *); // rax
  char *v39; // rdx
  __int128 *v40; // rax
  HANDLE EventW; // r13
  __int64 v42; // rdi
  void (__fastcall *v43)(struct IDimInterface *, _QWORD); // rdi
  int v44; // eax
  unsigned int v45; // eax
  __int64 v46; // rax
  void (__fastcall *v47)(struct IDimInterface *, _QWORD); // rdi
  int v48; // eax
  void (__fastcall *v49)(struct IDimInterface *, _QWORD); // rdi
  int v50; // eax
  __int64 v51; // rax
  __int64 v52; // rdi
  int v53; // eax
  __int64 v54; // rdx
  __int64 v55; // rdx
  void *v56; // rax
  int v57; // ecx
  int v58; // ecx
  int v59; // ecx
  int v60; // ecx
  __int64 v61; // [rsp+48h] [rbp-B8h] BYREF
  int *v62; // [rsp+50h] [rbp-B0h]
  __int128 v63; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v64[16]; // [rsp+68h] [rbp-98h] BYREF
  char v65[16]; // [rsp+78h] [rbp-88h] BYREF
  char v66; // [rsp+88h] [rbp-78h] BYREF
  char v67[16]; // [rsp+98h] [rbp-68h] BYREF
  char v68; // [rsp+A8h] [rbp-58h] BYREF
  char v69[16]; // [rsp+B8h] [rbp-48h] BYREF
  char v70; // [rsp+C8h] [rbp-38h] BYREF
  char v71[16]; // [rsp+D8h] [rbp-28h] BYREF
  char v72; // [rsp+E8h] [rbp-18h] BYREF
  char v73[16]; // [rsp+F8h] [rbp-8h] BYREF
  LPWSTR plpszSubStringArray[3]; // [rsp+108h] [rbp+8h] BYREF
  int v75; // [rsp+120h] [rbp+20h] BYREF
  __int128 v76; // [rsp+124h] [rbp+24h]
  __int128 v77; // [rsp+134h] [rbp+34h]
  int v78; // [rsp+144h] [rbp+44h]
  _OWORD v79[4]; // [rsp+150h] [rbp+50h] BYREF
  __int64 v80; // [rsp+190h] [rbp+90h]
  int v81; // [rsp+198h] [rbp+98h]
  wchar_t v82; // [rsp+19Ch] [rbp+9Ch]
  __int16 v83; // [rsp+19Eh] [rbp+9Eh]
  int v84; // [rsp+1A0h] [rbp+A0h] BYREF
  char v85[2044]; // [rsp+1A4h] [rbp+A4h] BYREF

  v62 = a2;
  v3 = 0;
  dwErrorCode = 0;
  v61 = 0;
  v84 = 0;
  memset_0(v85, 0, sizeof(v85));
  v75 = 0;
  v76 = 0;
  v77 = 0;
  v78 = 0;
  v63 = 0;
  Instance = DdmDeviceTable::GetInstance(0x11u);
  DdmDeviceTable::FindDevice(Instance, *((_QWORD *)a1 + 2), &v61);
  v6 = (_BYTE *)v61;
  if ( !v61 )
  {
    if ( (byte_1800CF404 & 0x10) != 0 )
    {
      LOWORD(v84) = 0;
      LOWORD(v75) = 0;
      ConvertPortNoToString(&v75, *((unsigned int *)a1 + 4));
      FormatRRASErrorString(&v84, L"No device found for port: %ld", *((_QWORD *)a1 + 2));
      if ( (byte_1800CF404 & 0x10) != 0 )
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasDdmParamTraceInfo,
          (unsigned int)&v84,
          (unsigned int)&v63,
          0,
          (__int64)&v75);
    }
    dwErrorCode = 1168;
    goto LABEL_6;
  }
  v9 = (struct _RTL_CRITICAL_SECTION *)(v61 + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)(v61 + 16));
  v10 = 1;
  v11 = *((_DWORD *)a1 + 3);
  if ( v11 > 11 )
  {
    v57 = v11 - 12;
    if ( !v57 )
      goto LABEL_20;
    v58 = v57 - 1;
    if ( !v58 )
      goto LABEL_20;
    v59 = v58 - 1;
    if ( !v59 )
      goto LABEL_20;
    v60 = v59 - 1;
    if ( !v60 || (unsigned int)(v60 - 1) < 2 )
      goto LABEL_20;
    goto LABEL_91;
  }
  if ( v11 == 11 )
  {
LABEL_20:
    v7 = 1;
LABEL_21:
    LeaveCriticalSection(v9);
    goto LABEL_7;
  }
  if ( v11 )
  {
    v12 = v11 - 1;
    if ( v12 )
    {
      v13 = v12 - 2;
      if ( !v13 )
        goto LABEL_20;
      v14 = v13 - 1;
      if ( v14 )
      {
        v15 = v14 - 3;
        if ( v15 )
        {
          if ( v15 == 3 )
          {
            (*(void (__fastcall **)(_BYTE *, struct _PROTOCOL_RESULT *))(*(_QWORD *)v6 + 336LL))(v6, a1);
            goto LABEL_20;
          }
LABEL_91:
          v7 = 0;
          goto LABEL_21;
        }
        goto LABEL_20;
      }
      dwErrorCode = (*(__int64 (__fastcall **)(_BYTE *, struct _PROTOCOL_RESULT *))(*(_QWORD *)v6 + 328LL))(v6, a1);
      v3 = dwErrorCode != 0;
    }
    else
    {
      v16 = (*(__int64 (__fastcall **)(_BYTE *, struct _PROTOCOL_RESULT *))(*(_QWORD *)v6 + 320LL))(v6, a1);
      dwErrorCode = v16;
      if ( (v6[132] & 8) == 0 )
        goto LABEL_35;
      (*(void (__fastcall **)(_BYTE *, _QWORD))(*(_QWORD *)v6 + 80LL))(v6, v16);
    }
  }
  else
  {
    dwErrorCode = (*(__int64 (__fastcall **)(_BYTE *, struct _PROTOCOL_RESULT *))(*(_QWORD *)v6 + 312LL))(v6, a1);
    if ( !dwErrorCode )
      goto LABEL_20;
    if ( (byte_1800CF404 & 8) != 0 )
    {
      LOWORD(v84) = 0;
      LOWORD(v75) = 0;
      v17 = v6 ? *((unsigned int *)v6 + 24) : 0xFFFFFFFFLL;
      ConvertPortNoToString(&v75, v17);
      FormatRRASErrorString(&v84, L"Post connect processing failed. dwError=0x%x. Dicconnecting...", dwErrorCode);
      if ( (byte_1800CF404 & 8) != 0 )
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasDdmParamTraceError,
          (unsigned int)&v84,
          (unsigned int)&v63,
          0,
          (__int64)&v75);
    }
    v3 = 1;
  }
  if ( !v3 )
    goto LABEL_20;
LABEL_35:
  if ( (byte_1800CF404 & 8) != 0 )
  {
    LOWORD(v84) = 0;
    LOWORD(v75) = 0;
    ConvertPortNoToString(&v75, *((unsigned int *)a1 + 4));
    FormatRRASErrorString(
      &v84,
      L"S2S interface dialing out failed (hport: %ld): Error: %d",
      *((_QWORD *)a1 + 2),
      dwErrorCode);
    if ( (byte_1800CF404 & 8) != 0 )
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceError,
        (unsigned int)&v84,
        (unsigned int)&v63,
        0,
        (__int64)&v75);
  }
  (**(void (__fastcall ***)(__int64))g_pIDimInterfaceTable)(g_pIDimInterfaceTable);
  v18 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)g_pIDimInterfaceTable + 64LL);
  v19 = (*(__int64 (__fastcall **)(_BYTE *))(*(_QWORD *)v6 + 304LL))(v6);
  v20 = (struct IDimInterface *)v18(g_pIDimInterfaceTable, v19);
  v21 = v20;
  if ( !v20 )
  {
    dwErrorCode = 905;
    goto LABEL_84;
  }
  (**(void (__fastcall ***)(struct IDimInterface *))v20)(v20);
  v22 = *(void (__fastcall **)(struct IDimInterface *, _QWORD))(*(_QWORD *)v21 + 160LL);
  v23 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v21 + 152LL))(v21);
  v22(v21, (unsigned int)(v23 - 1));
  (*(void (__fastcall **)(struct IDimInterface *, _QWORD))(*(_QWORD *)v21 + 32LL))(v21, dwErrorCode);
  if ( !(*(unsigned int (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v21 + 152LL))(v21)
    && *((_DWORD *)v6 + 32) == 4
    && (*(unsigned int (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v21 + 40LL))(v21) == 2 )
  {
    goto LABEL_80;
  }
  if ( (byte_1800CF404 & 0x10) == 0 )
    goto LABEL_60;
  LOWORD(v84) = 0;
  LOWORD(v75) = 0;
  v24 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v21 + 264LL))(v21);
  ConvertPortNoToString(&v75, v24);
  v25 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v21 + 280LL))(v21);
  FormatRRASErrorString(
    &v84,
    L"%s:Could not connect to interface %ws",
    L"DdmNotificationHandler::ProcessDialedOutConnectionNotification",
    v25);
  if ( (byte_1800CF404 & 0x10) == 0 )
    goto LABEL_60;
  v26 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v21 + 280LL))(v21);
  v27 = (*(__int64 (__fastcall **)(struct IDimInterface *, char *))(*(_QWORD *)v21 + 360LL))(v21, v65);
  v28 = v21;
  v29 = v27 == 0;
  v30 = *(__int64 (__fastcall **)(struct IDimInterface *, char *))(*(_QWORD *)v21 + 360LL);
  if ( v29 )
  {
    if ( !v30(v21, v67) )
    {
      v32 = &v63;
      goto LABEL_51;
    }
    v31 = &v68;
    v28 = v21;
    v30 = *(__int64 (__fastcall **)(struct IDimInterface *, char *))(*(_QWORD *)v21 + 360LL);
  }
  else
  {
    v31 = &v66;
  }
  LODWORD(v32) = v30(v28, v31);
LABEL_51:
  McTemplateU0zjzz_EventWriteTransfer(
    (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
    (unsigned int)RasDdmParamTraceInfo,
    (unsigned int)&v84,
    (_DWORD)v32,
    v26,
    (__int64)&v75);
  if ( (byte_1800CF404 & 0x10) != 0 )
  {
    LOWORD(v84) = 0;
    LOWORD(v75) = 0;
    v33 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v21 + 264LL))(v21);
    ConvertPortNoToString(&v75, v33);
    v34 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v21 + 264LL))(v21);
    FormatRRASErrorString(
      &v84,
      L"%s: hanging up 0x%x",
      L"DdmNotificationHandler::ProcessDialedOutConnectionNotification",
      v34);
    if ( (byte_1800CF404 & 0x10) != 0 )
    {
      v35 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v21 + 280LL))(v21);
      v36 = (*(__int64 (__fastcall **)(struct IDimInterface *, char *))(*(_QWORD *)v21 + 360LL))(v21, v69);
      v37 = v21;
      v29 = v36 == 0;
      v38 = *(__int64 (__fastcall **)(struct IDimInterface *, char *))(*(_QWORD *)v21 + 360LL);
      if ( v29 )
      {
        if ( !v38(v21, v71) )
        {
          v40 = &v63;
          goto LABEL_59;
        }
        v39 = &v72;
        v37 = v21;
        v38 = *(__int64 (__fastcall **)(struct IDimInterface *, char *))(*(_QWORD *)v21 + 360LL);
      }
      else
      {
        v39 = &v70;
      }
      LODWORD(v40) = v38(v37, v39);
LABEL_59:
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceInfo,
        (unsigned int)&v84,
        (_DWORD)v40,
        v35,
        (__int64)&v75);
    }
  }
LABEL_60:
  EventW = (HANDLE)*((_QWORD *)v6 + 1431);
  if ( !EventW )
    EventW = CreateEventW(0, 1, 0, 0);
  if ( (*(unsigned int (__fastcall **)(_BYTE *, HANDLE))(*(_QWORD *)v6 + 160LL))(v6, EventW) != 600 )
  {
    v10 = 1;
LABEL_66:
    (**(void (__fastcall ***)(struct IDimInterface *))v21)(v21);
    (*(void (__fastcall **)(struct IDimInterface *, _QWORD))(*(_QWORD *)v21 + 272LL))(v21, 0);
    if ( !(*(unsigned __int8 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v21 + 56LL))(v21)
      && (*(unsigned int (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v21 + 184LL))(v21)
      && (*((_DWORD *)v6 + 33) & 0x100000) == 0 )
    {
      v43 = *(void (__fastcall **)(struct IDimInterface *, _QWORD))(*(_QWORD *)v21 + 192LL);
      v44 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v21 + 184LL))(v21);
      v43(v21, (unsigned int)(v44 - 1));
      v45 = time(0);
      srand(v45);
      LODWORD(v43) = 2 * (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v21 + 200LL))(v21) + 1;
      LODWORD(v43) = rand() % (unsigned int)v43;
      v46 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v21 + 16LL))(v21);
      if ( !(unsigned int)TimerQInsert(v46, (unsigned int)v43, ReConnectInterface) )
      {
        v47 = *(void (__fastcall **)(struct IDimInterface *, _QWORD))(*(_QWORD *)v21 + 112LL);
        v48 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v21 + 104LL))(v21);
        v47(v21, v48 | 0x800u);
      }
LABEL_82:
      (*(void (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v21 + 8LL))(v21);
      goto LABEL_83;
    }
    if ( !(*(unsigned __int8 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v21 + 56LL))(v21) )
    {
      v49 = *(void (__fastcall **)(struct IDimInterface *, _QWORD))(*(_QWORD *)v21 + 112LL);
      v50 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v21 + 104LL))(v21);
      v49(v21, v50 | 0x20u);
    }
    if ( (byte_1800CF404 & 0x10) != 0 )
    {
      LOWORD(v84) = 0;
      LOWORD(v75) = 0;
      v51 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v21 + 280LL))(v21);
      FormatRRASErrorString(
        &v84,
        L"%s: Marking interface '%ws' DISCONNECTED.",
        L"DdmNotificationHandler::ProcessDialedOutConnectionNotification",
        v51);
      if ( (byte_1800CF404 & 0x10) != 0 )
      {
        v52 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v21 + 280LL))(v21);
        v53 = (*(__int64 (__fastcall **)(struct IDimInterface *, char *))(*(_QWORD *)v21 + 360LL))(v21, v73);
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasDdmParamTraceInfo,
          (unsigned int)&v84,
          v53,
          v52,
          (__int64)&v75);
      }
    }
    InterfaceDisconnected(v21);
    (*(void (__fastcall **)(struct IDimInterface *, _QWORD, __int64, _QWORD))(*(_QWORD *)v21 + 440LL))(
      v21,
      0,
      1,
      (unsigned int)dword_1800CF658);
    if ( (*(unsigned __int8 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v21 + 56LL))(v21) )
    {
      LOBYTE(v54) = 1;
      (*(void (__fastcall **)(struct IDimInterface *, __int64, __int64, _QWORD))(*(_QWORD *)v21 + 440LL))(
        v21,
        v54,
        1,
        (unsigned int)dword_1800CF658);
    }
    (*(void (__fastcall **)(struct IDimInterface *, _QWORD))(*(_QWORD *)v21 + 32LL))(v21, dwErrorCode);
    v79[0] = *(_OWORD *)L"{00000000-0000-0000-0000-000000000000}";
    v79[1] = *(_OWORD *)L"0-0000-0000-0000-000000000000}";
    v79[2] = *(_OWORD *)L"000-0000-000000000000}";
    v79[3] = *(_OWORD *)L"-000000000000}";
    v80 = *(_QWORD *)L"00000}";
    v81 = *(_DWORD *)L"0}";
    v82 = a00000000000000[38];
    v83 = 0;
    (*(void (__fastcall **)(struct IDimInterface *, _BYTE *))(*(_QWORD *)v21 + 360LL))(v21, v64);
    MprConvertGuidToString(v64, v55, v79);
    plpszSubStringArray[0] = (LPWSTR)v79;
    plpszSubStringArray[1] = (LPWSTR)(*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v21 + 280LL))(v21);
    plpszSubStringArray[2] = (LPWSTR)(v6 + 714);
    if ( dword_1800CF4E4 )
      RouterLogEventStringW(hLogHandle, 1u, 0x4E8Fu, 3u, plpszSubStringArray, dwErrorCode, 3u);
LABEL_80:
    if ( (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v21 + 224LL))(v21) != -1 )
    {
      v56 = (void *)(*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v21 + 224LL))(v21);
      SetEvent(v56);
      (*(void (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v21 + 240LL))(v21);
    }
    goto LABEL_82;
  }
  v42 = (*(__int64 (__fastcall **)(_BYTE *))(*(_QWORD *)v6 + 304LL))(v6);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v6 + 16));
  (*(void (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v21 + 8LL))(v21);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)g_pIDimInterfaceTable + 16LL))(g_pIDimInterfaceTable);
  WaitForSingleObject(EventW, 0xFFFFFFFF);
  (**(void (__fastcall ***)(__int64))g_pIDimInterfaceTable)(g_pIDimInterfaceTable);
  v21 = (struct IDimInterface *)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)g_pIDimInterfaceTable + 64LL))(
                                  g_pIDimInterfaceTable,
                                  v42);
  v10 = 0;
  if ( v21 )
    goto LABEL_66;
  dwErrorCode = 905;
LABEL_83:
  v9 = (struct _RTL_CRITICAL_SECTION *)(v6 + 16);
LABEL_84:
  (*(void (__fastcall **)(__int64))(*(_QWORD *)g_pIDimInterfaceTable + 16LL))(g_pIDimInterfaceTable);
  if ( v10 )
    goto LABEL_20;
LABEL_6:
  v7 = 1;
LABEL_7:
  *v62 = v7;
  if ( v6 && _InterlockedExchangeAdd((volatile signed __int32 *)v6 + 2, 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(__int64, __int64))v61)(v61, 1);
  return dwErrorCode;
}

```

## disassembly

```asm
0x180047ed4  mov     [rsp-8+arg_10], rbx
0x180047ed9  push    rbp
0x180047eda  push    rsi
0x180047edb  push    rdi
0x180047edc  push    r12
0x180047ede  push    r13
0x180047ee0  push    r14
0x180047ee2  push    r15
0x180047ee4  lea     rbp, [rsp-8B0h]
0x180047eec  sub     rsp, 9B0h
0x180047ef3  mov     rax, cs:__security_cookie
0x180047efa  xor     rax, rsp
0x180047efd  mov     [rbp+8E0h+var_40], rax
0x180047f04  mov     [rsp+9E0h+var_990], rdx
0x180047f09  mov     rdi, rcx
0x180047f0c  xor     esi, esi
0x180047f0e  mov     r14d, esi
0x180047f11  mov     [rsp+9E0h+var_998], rsi
0x180047f16  mov     [rsp+9E0h+var_9A0], 1
0x180047f1e  mov     [rbp+8E0h+var_840], esi
0x180047f24  xor     edx, edx; Val
0x180047f26  mov     r8d, 7FCh; Size
0x180047f2c  lea     rcx, [rbp+8E0h+var_83C]; void *
0x180047f33  call    memset_0
0x180047f38  mov     [rbp+8E0h+var_8C0], esi
0x180047f3b  xorps   xmm0, xmm0
0x180047f3e  xor     eax, eax
0x180047f40  movups  [rbp+8E0h+var_8BC], xmm0
0x180047f44  movups  [rbp+8E0h+var_8AC], xmm0
0x180047f48  mov     [rbp+8E0h+var_89C], eax
0x180047f4b  movups  [rsp+9E0h+var_988], xmm0
0x180047f50  lea     ecx, [rsi+11h]; unsigned int
0x180047f53  call    ?GetInstance@DdmDeviceTable@@SAPEAV1@K@Z; DdmDeviceTable::GetInstance(ulong)
0x180047f58  lea     r8, [rsp+9E0h+var_998]
0x180047f5d  mov     rdx, [rdi+10h]
0x180047f61  mov     rcx, rax
0x180047f64  call    ?FindDevice@DdmDeviceTable@@QEAAXPEAXAEAV?$RasObjPtr@VDdmDevice@@@@@Z; DdmDeviceTable::FindDevice(void *,RasObjPtr<DdmDevice> &)
0x180047f69  mov     rbx, [rsp+9E0h+var_998]
0x180047f6e  test    rbx, rbx
0x180047f71  jnz     loc_18004804D
0x180047f77  mov     r15b, 10h
0x180047f7a  test    cs:byte_1800CF404, r15b
0x180047f81  jz      short loc_180047FE7
0x180047f83  mov     word ptr [rbp+8E0h+var_840], si
0x180047f8a  mov     word ptr [rbp+8E0h+var_8C0], si
0x180047f8e  mov     edx, [rdi+10h]
0x180047f91  lea     rcx, [rbp+8E0h+var_8C0]
0x180047f95  call    ConvertPortNoToString
0x180047f9a  mov     r8, [rdi+10h]
0x180047f9e  lea     rdx, aNoDeviceFoundF; "No device found for port: %ld"
0x180047fa5  lea     rcx, [rbp+8E0h+var_840]
0x180047fac  call    FormatRRASErrorString
0x180047fb1  test    cs:byte_1800CF404, r15b
0x180047fb8  jz      short loc_180047FE7
0x180047fba  lea     rax, [rbp+8E0h+var_8C0]
0x180047fbe  mov     qword ptr [rsp+9E0h+dwErrorCode], rax
0x180047fc3  mov     [rsp+9E0h+plpszSubStringArray], rsi
0x180047fc8  lea     r9, [rsp+9E0h+var_988]
0x180047fcd  lea     r8, [rbp+8E0h+var_840]
0x180047fd4  lea     rdx, RasDdmParamTraceInfo
0x180047fdb  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180047fe2  call    McTemplateU0zjzz_EventWriteTransfer
0x180047fe7  mov     r14d, 490h
0x180047fed  mov     edi, [rsp+9E0h+var_9A0]
0x180047ff1  mov     rax, [rsp+9E0h+var_990]
0x180047ff6  mov     [rax], edi
0x180047ff8  test    rbx, rbx
0x180047ffb  jz      short loc_18004801F
0x180047ffd  or      eax, 0FFFFFFFFh
0x180048000  lock xadd [rbx+8], eax
0x180048005  cmp     eax, 1
0x180048008  jnz     short loc_18004801F
0x18004800a  mov     rcx, [rsp+9E0h+var_998]
0x18004800f  mov     rax, [rcx]
0x180048012  mov     edx, 1
0x180048017  mov     rax, [rax]
0x18004801a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004801f  mov     eax, r14d
0x180048022  mov     rcx, [rbp+8E0h+var_40]
0x180048029  xor     rcx, rsp; StackCookie
0x18004802c  call    __security_check_cookie
0x180048031  mov     rbx, [rsp+9E0h+arg_10]
0x180048039  add     rsp, 9B0h
0x180048040  pop     r15
0x180048042  pop     r14
0x180048044  pop     r13
0x180048046  pop     r12
0x180048048  pop     rdi
0x180048049  pop     rsi
0x18004804a  pop     rbp
0x18004804b  retn
0x18004804d  lea     r15, [rbx+10h]
0x180048051  mov     rcx, r15; lpCriticalSection
0x180048054  call    cs:__imp_EnterCriticalSection
0x18004805b  nop     dword ptr [rax+rax+00h]
0x180048060  mov     r13b, 1
0x180048063  mov     [rsp+9E0h+var_99C], r13b
0x180048068  mov     ecx, [rdi+0Ch]
0x18004806b  cmp     ecx, 0Bh
0x18004806e  jg      loc_180048A05
0x180048074  jz      short loc_1800480B7
0x180048076  lea     r12, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004807d  test    ecx, ecx
0x18004807f  jz      loc_180048136
0x180048085  sub     ecx, 1
0x180048088  jz      short loc_1800480F7
0x18004808a  sub     ecx, 2
0x18004808d  jz      short loc_1800480B7
0x18004808f  sub     ecx, 1
0x180048092  jz      short loc_1800480CF
0x180048094  sub     ecx, 3
0x180048097  jz      short loc_1800480B7
0x180048099  cmp     ecx, 3
0x18004809c  jnz     loc_180048A3B
0x1800480a2  mov     rax, [rbx]
0x1800480a5  mov     rdx, rdi
0x1800480a8  mov     rcx, rbx
0x1800480ab  mov     rax, [rax+150h]
0x1800480b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800480b7  mov     edi, [rsp+9E0h+var_9A0]
0x1800480bb  mov     rcx, r15; lpCriticalSection
0x1800480be  call    cs:__imp_LeaveCriticalSection
0x1800480c5  nop     dword ptr [rax+rax+00h]
0x1800480ca  jmp     loc_180047FF1
0x1800480cf  mov     rax, [rbx]
0x1800480d2  mov     rdx, rdi
0x1800480d5  mov     rcx, rbx
0x1800480d8  mov     rax, [rax+148h]
0x1800480df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800480e4  mov     r14d, eax
0x1800480e7  xor     eax, eax
0x1800480e9  mov     esi, eax
0x1800480eb  test    r14d, r14d
0x1800480ee  setnz   sil
0x1800480f2  jmp     loc_1800481D1
0x1800480f7  mov     rax, [rbx]
0x1800480fa  mov     rdx, rdi
0x1800480fd  mov     rcx, rbx
0x180048100  mov     rax, [rax+140h]
0x180048107  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004810c  mov     r14d, eax
0x18004810f  test    byte ptr [rbx+84h], 8
0x180048116  jz      short loc_18004812F
0x180048118  mov     rax, [rbx]
0x18004811b  mov     edx, r14d
0x18004811e  mov     rcx, rbx
0x180048121  mov     rax, [rax+50h]
0x180048125  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004812a  jmp     loc_1800481CF
0x18004812f  xor     eax, eax
0x180048131  jmp     loc_1800481D9
0x180048136  mov     rax, [rbx]
0x180048139  mov     rdx, rdi
0x18004813c  mov     rcx, rbx
0x18004813f  mov     rax, [rax+138h]
0x180048146  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004814b  mov     r14d, eax
0x18004814e  xor     esi, esi
0x180048150  test    eax, eax
0x180048152  jz      loc_1800480B7
0x180048158  test    cs:byte_1800CF404, 8
0x18004815f  jz      short loc_1800481CA
0x180048161  mov     word ptr [rbp+8E0h+var_840], si
0x180048168  mov     word ptr [rbp+8E0h+var_8C0], si
0x18004816c  test    rbx, rbx
0x18004816f  jz      short loc_180048176
0x180048171  mov     edx, [rbx+60h]
0x180048174  jmp     short loc_180048179
0x180048176  or      edx, 0FFFFFFFFh
0x180048179  lea     rcx, [rbp+8E0h+var_8C0]
0x18004817d  call    ConvertPortNoToString
0x180048182  mov     r8d, r14d
0x180048185  lea     rdx, aPostConnectPro; "Post connect processing failed. dwError"...
0x18004818c  lea     rcx, [rbp+8E0h+var_840]
0x180048193  call    FormatRRASErrorString
0x180048198  test    cs:byte_1800CF404, 8
0x18004819f  jz      short loc_1800481CA
0x1800481a1  lea     rax, [rbp+8E0h+var_8C0]
0x1800481a5  mov     qword ptr [rsp+9E0h+dwErrorCode], rax
0x1800481aa  mov     [rsp+9E0h+plpszSubStringArray], rsi
0x1800481af  lea     r9, [rsp+9E0h+var_988]
0x1800481b4  lea     r8, [rbp+8E0h+var_840]
0x1800481bb  lea     rdx, RasDdmParamTraceError
0x1800481c2  mov     rcx, r12
0x1800481c5  call    McTemplateU0zjzz_EventWriteTransfer
0x1800481ca  mov     esi, 1
0x1800481cf  xor     eax, eax
0x1800481d1  test    esi, esi
0x1800481d3  jz      loc_1800480B7
0x1800481d9  test    cs:byte_1800CF404, 8
0x1800481e0  jz      short loc_180048247
0x1800481e2  mov     word ptr [rbp+8E0h+var_840], ax
0x1800481e9  mov     word ptr [rbp+8E0h+var_8C0], ax
0x1800481ed  mov     edx, [rdi+10h]
0x1800481f0  lea     rcx, [rbp+8E0h+var_8C0]
0x1800481f4  call    ConvertPortNoToString
0x1800481f9  mov     r9d, r14d
0x1800481fc  mov     r8, [rdi+10h]
0x180048200  lea     rdx, aS2sInterfaceDi; "S2S interface dialing out failed (hport"...
0x180048207  lea     rcx, [rbp+8E0h+var_840]
0x18004820e  call    FormatRRASErrorString
0x180048213  test    cs:byte_1800CF404, 8
0x18004821a  jz      short loc_180048247
0x18004821c  lea     rax, [rbp+8E0h+var_8C0]
0x180048220  mov     qword ptr [rsp+9E0h+dwErrorCode], rax
0x180048225  xor     edx, edx
0x180048227  mov     [rsp+9E0h+plpszSubStringArray], rdx
0x18004822c  lea     r9, [rsp+9E0h+var_988]
0x180048231  lea     r8, [rbp+8E0h+var_840]
0x180048238  lea     rdx, RasDdmParamTraceError
0x18004823f  mov     rcx, r12
0x180048242  call    McTemplateU0zjzz_EventWriteTransfer
0x180048247  mov     rcx, cs:g_pIDimInterfaceTable
0x18004824e  mov     rax, [rcx]
0x180048251  mov     rax, [rax]
0x180048254  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048259  mov     rax, cs:g_pIDimInterfaceTable
0x180048260  mov     rcx, [rax]
0x180048263  mov     rdi, [rcx+40h]
0x180048267  mov     rcx, [rbx]
0x18004826a  mov     rax, [rcx+130h]
0x180048271  mov     rcx, rbx
0x180048274  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048279  mov     rdx, rax
0x18004827c  mov     rcx, cs:g_pIDimInterfaceTable
0x180048283  mov     rax, rdi
0x180048286  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004828b  mov     rsi, rax
0x18004828e  test    rax, rax
0x180048291  jnz     short loc_18004829E
0x180048293  mov     r14d, 389h
0x180048299  jmp     loc_1800489E4
0x18004829e  mov     rax, [rsi]
0x1800482a1  mov     rcx, rsi
0x1800482a4  mov     rax, [rax]
0x1800482a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800482ac  mov     rcx, [rsi]
0x1800482af  mov     rdi, [rcx+0A0h]
0x1800482b6  mov     rax, [rcx+98h]
0x1800482bd  mov     rcx, rsi
0x1800482c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800482c5  lea     edx, [rax-1]
0x1800482c8  mov     rcx, rsi
0x1800482cb  mov     rax, rdi
0x1800482ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800482d3  mov     rax, [rsi]
0x1800482d6  mov     edx, r14d
0x1800482d9  mov     rcx, rsi
0x1800482dc  mov     rax, [rax+20h]
0x1800482e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800482e5  mov     rax, [rsi]
0x1800482e8  mov     rcx, rsi
0x1800482eb  mov     rax, [rax+98h]
0x1800482f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800482f7  test    eax, eax
0x1800482f9  jnz     short loc_18004831C
0x1800482fb  cmp     dword ptr [rbx+80h], 4
0x180048302  jnz     short loc_18004831C
0x180048304  mov     rax, [rsi]
0x180048307  mov     rcx, rsi
0x18004830a  mov     rax, [rax+28h]
0x18004830e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048313  cmp     eax, 2
0x180048316  jz      loc_180048986
0x18004831c  mov     al, cs:byte_1800CF404
0x180048322  mov     r15b, 10h
0x180048325  xor     r13d, r13d
0x180048328  test    r15b, al
0x18004832b  jz      loc_180048541
0x180048331  mov     word ptr [rbp+8E0h+var_840], r13w
0x180048339  mov     word ptr [rbp+8E0h+var_8C0], r13w
0x18004833e  mov     rax, [rsi]
0x180048341  mov     rcx, rsi
0x180048344  mov     rax, [rax+108h]
0x18004834b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048350  mov     rdx, rax
0x180048353  lea     rcx, [rbp+8E0h+var_8C0]
0x180048357  call    ConvertPortNoToString
0x18004835c  mov     rax, [rsi]
0x18004835f  mov     rcx, rsi
0x180048362  mov     rax, [rax+118h]
0x180048369  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004836e  mov     r9, rax
0x180048371  lea     r8, aDdmnotificatio; "DdmNotificationHandler::ProcessDialedOu"...
0x180048378  lea     rdx, aSCouldNotConne; "%s:Could not connect to interface %ws"
0x18004837f  lea     rcx, [rbp+8E0h+var_840]
0x180048386  call    FormatRRASErrorString
0x18004838b  mov     al, cs:byte_1800CF404
0x180048391  test    r15b, al
0x180048394  jz      loc_180048541
0x18004839a  mov     rax, [rsi]
0x18004839d  mov     rcx, rsi
0x1800483a0  mov     rax, [rax+118h]
0x1800483a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800483ac  mov     rdi, rax
0x1800483af  mov     rcx, [rsi]
0x1800483b2  mov     rax, [rcx+168h]
0x1800483b9  lea     rdx, [rsp+9E0h+var_968]
0x1800483be  mov     rcx, rsi
0x1800483c1  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
