# DDMDisconnectInterface

- ea: `0x18001a200`
- end: `0x18001add9`
- name: `DDMDisconnectInterface`
- size: `3033`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004130`

## callees

- `0x180007c0c`
- `0x180007d00`
- `0x180008efc`
- `0x18001a200`
- `0x18002f010`
- `0x1800304dc`
- `0x180030684`
- `0x18003d100`
- `0x18003d278`
- `0x180075588`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`
- `0x180092b90`
- `0x180095010`

## import_xrefs

- `KERNEL32!SetEvent` at `0x18001a732`
- `KERNEL32!SetEvent` at `0x18001ac15`
- `KERNEL32!SetEvent` at `0x18001a732`
- `KERNEL32!SetEvent` at `0x18001ac15`
- `KERNEL32!CloseHandle` at `0x18001a69d`
- `KERNEL32!CloseHandle` at `0x18001a718`
- `KERNEL32!CloseHandle` at `0x18001a69d`
- `KERNEL32!CloseHandle` at `0x18001a718`
- `KERNEL32!CreateEventW` at `0x18001a5ec`
- `KERNEL32!CreateEventW` at `0x18001a5ec`
- `KERNEL32!WaitForSingleObject` at `0x18001a6db`
- `KERNEL32!WaitForSingleObject` at `0x18001a6db`
- `KERNEL32!LeaveCriticalSection` at `0x18001a6c9`
- `KERNEL32!LeaveCriticalSection` at `0x18001ad31`
- `KERNEL32!LeaveCriticalSection` at `0x18001a6c9`
- `KERNEL32!LeaveCriticalSection` at `0x18001ad31`
- `KERNEL32!EnterCriticalSection` at `0x18001a682`
- `KERNEL32!EnterCriticalSection` at `0x18001a74e`
- `KERNEL32!EnterCriticalSection` at `0x18001a682`
- `KERNEL32!EnterCriticalSection` at `0x18001a74e`
- `RASAPI32!RasHangUpW` at `0x18001a991`
- `RASAPI32!RasHangUpW` at `0x18001ab38`
- `RASAPI32!RasHangUpW` at `0x18001a991`
- `RASAPI32!RasHangUpW` at `0x18001ab38`

## pseudocode

```c
__int64 __fastcall DDMDisconnectInterface(__int64 a1, unsigned int a2)
{
  unsigned int v4; // esi
  __int64 v5; // r13
  __int64 v6; // r14
  char v7; // r12
  void (__fastcall **v8)(__int64); // rax
  __int64 *v9; // rax
  __int64 *v10; // rdi
  __int64 v11; // rax
  int v12; // ecx
  int v13; // ecx
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rbx
  int v17; // eax
  __int64 v18; // rax
  __int64 v19; // rbx
  int v20; // eax
  char v21; // r14
  HANDLE EventW; // rdi
  struct DdmConnectionTable *Instance; // rax
  DdmConnection *v24; // rbx
  struct DdmDeviceTable *v25; // rax
  char v26; // r13
  struct IDimInterface *v27; // rax
  __int64 v28; // r12
  struct IDimInterface *v29; // rdi
  __int64 v30; // rax
  int v31; // ecx
  int v32; // ecx
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // rbx
  bool v36; // zf
  struct IDimInterface *v37; // rcx
  __int64 (__fastcall *v38)(struct IDimInterface *, DdmConnection **); // rax
  DdmConnection **v39; // rdx
  __int128 *v40; // rax
  HRASCONN v41; // rax
  __int64 v42; // rax
  __int64 v43; // rax
  __int64 v44; // rbx
  struct IDimInterface *v45; // rcx
  __int64 (__fastcall *v46)(struct IDimInterface *, _QWORD *); // rax
  DdmConnection **v47; // rdx
  __int128 *v48; // rax
  HRASCONN v49; // rax
  __int64 v50; // rax
  __int64 v51; // rbx
  int v52; // eax
  void *v53; // rax
  __int64 v54; // rdx
  struct DdmConnectionTable *v55; // rax
  volatile signed __int32 *v56; // rbx
  __int64 v57; // r8
  char v59; // [rsp+30h] [rbp-D0h]
  HANDLE hEvent; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v61; // [rsp+40h] [rbp-C0h]
  DdmConnection *v62[2]; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v63[2]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v64[16]; // [rsp+68h] [rbp-98h] BYREF
  __int128 v65; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v66[16]; // [rsp+88h] [rbp-78h] BYREF
  __int128 v67; // [rsp+98h] [rbp-68h]
  struct _EVENT_DATA_DESCRIPTOR v68; // [rsp+A8h] [rbp-58h] BYREF
  int *v69; // [rsp+B8h] [rbp-48h]
  int v70; // [rsp+C0h] [rbp-40h]
  int v71; // [rsp+C4h] [rbp-3Ch]
  int v72; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v73; // [rsp+CCh] [rbp-34h]
  __int128 v74; // [rsp+DCh] [rbp-24h]
  int v75; // [rsp+ECh] [rbp-14h]
  int v76; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v77; // [rsp+F4h] [rbp-Ch]
  __int128 v78; // [rsp+104h] [rbp+4h]
  int v79; // [rsp+114h] [rbp+14h]
  int v80; // [rsp+120h] [rbp+20h] BYREF
  char v81[2044]; // [rsp+124h] [rbp+24h] BYREF
  int v82; // [rsp+920h] [rbp+820h] BYREF
  char v83[2044]; // [rsp+924h] [rbp+824h] BYREF

  v4 = 0;
  v61 = 0;
  v59 = 0;
  if ( dword_1800CF654 )
  {
    hEvent = 0;
    v63[0] = 0;
    v82 = 0;
    v5 = 0;
    v6 = 0;
    v7 = 0;
    memset_0(v83, 0, sizeof(v83));
    v79 = 0;
    v76 = 0;
    v77 = 0;
    v8 = *(void (__fastcall ***)(__int64))g_pIDimInterfaceTable;
    v78 = 0;
    v67 = 0;
    (*v8)(g_pIDimInterfaceTable);
    v9 = (__int64 *)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)g_pIDimInterfaceTable + 64LL))(
                      g_pIDimInterfaceTable,
                      a1);
    v10 = v9;
    if ( !v9 )
    {
      v4 = 6;
LABEL_32:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)g_pIDimInterfaceTable + 16LL))(g_pIDimInterfaceTable);
      if ( v7 || v4 )
        return v4;
      v21 = 1;
      EventW = CreateEventW(0, 1, 0, 0);
      v62[0] = 0;
      if ( v59 )
      {
        Instance = DdmConnectionTable::GetInstance();
        DdmConnectionTable::FindConnection(Instance, v63[0], v62);
        v24 = v62[0];
        if ( v62[0] )
        {
          DdmConnection::Disconnect(v62[0], EventW);
          v21 = 0;
          goto LABEL_42;
        }
      }
      else
      {
        v25 = DdmDeviceTable::GetInstance(0x11u);
        DdmDeviceTable::FindDevice(v25, v61, v62);
        v24 = v62[0];
        if ( v62[0] )
        {
          EnterCriticalSection((LPCRITICAL_SECTION)((char *)v62[0] + 16));
          v21 = 0;
          if ( *((_QWORD *)v24 + 1431) )
          {
            CloseHandle(EventW);
            EventW = (HANDLE)*((_QWORD *)v24 + 1431);
          }
          (*(void (__fastcall **)(DdmConnection *, HANDLE))(*(_QWORD *)v24 + 152LL))(v24, EventW);
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v24 + 16));
          WaitForSingleObject(EventW, 0xFFFFFFFF);
          goto LABEL_42;
        }
      }
      v4 = 87;
LABEL_42:
      if ( v24 && _InterlockedExchangeAdd((volatile signed __int32 *)v24 + 2, 0xFFFFFFFF) == 1 )
        (**(void (__fastcall ***)(DdmConnection *, __int64))v62[0])(v62[0], 1);
      if ( v21 )
        CloseHandle(EventW);
      if ( (char *)hEvent - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        SetEvent(hEvent);
      return v4;
    }
    (*(void (__fastcall **)(__int64 *))*v9)(v9);
    v11 = *v10;
    if ( a2 == -1 )
      (*(void (__fastcall **)(__int64 *, _QWORD))(v11 + 328))(v10, 0);
    else
      (*(void (__fastcall **)(__int64 *, _QWORD, _QWORD))(v11 + 320))(v10, a2, 0);
    v12 = (*(__int64 (__fastcall **)(__int64 *))(*v10 + 40))(v10);
    if ( v12 )
    {
      v13 = v12 - 1;
      if ( v13 )
      {
        if ( v13 != 1 )
          goto LABEL_15;
        if ( (*(unsigned __int8 (__fastcall **)(__int64 *))(*v10 + 312))(v10) )
        {
          v6 = (*(__int64 (__fastcall **)(__int64 *))(*v10 + 248))(v10);
          v63[0] = v6;
          v59 = 1;
          goto LABEL_15;
        }
      }
      else if ( (*(unsigned __int8 (__fastcall **)(__int64 *))(*v10 + 312))(v10) )
      {
        if ( ((*(__int64 (__fastcall **)(__int64 *))(*v10 + 104))(v10) & 1) != 0 )
        {
          v5 = (*(__int64 (__fastcall **)(__int64 *))(*v10 + 264))(v10);
          v61 = v5;
LABEL_15:
          hEvent = (HANDLE)(*(__int64 (__fastcall **)(__int64 *))(*v10 + 224))(v10);
          if ( v59 )
          {
            if ( !v6 )
            {
              if ( (byte_1800CF404 & 0x10) != 0 )
              {
                LOWORD(v82) = 0;
                LOWORD(v76) = 0;
                v14 = (*(__int64 (__fastcall **)(__int64 *))(*v10 + 280))(v10);
                FormatRRASErrorString(&v82, L"DDMDisconnectInterface: hConnection is nullptr for interface %ws", v14);
                goto LABEL_22;
              }
              goto LABEL_24;
            }
          }
          else if ( !v5 )
          {
            if ( (byte_1800CF404 & 0x10) != 0 )
            {
              LOWORD(v82) = 0;
              LOWORD(v76) = 0;
              v15 = (*(__int64 (__fastcall **)(__int64 *))(*v10 + 280))(v10);
              FormatRRASErrorString(&v82, L"DDMDisconnectInterface: hPort is nullptr for interface %ws", v15);
LABEL_22:
              if ( (byte_1800CF404 & 0x10) != 0 )
              {
                v16 = (*(__int64 (__fastcall **)(__int64 *))(*v10 + 280))(v10);
                v17 = (*(__int64 (__fastcall **)(__int64 *, _BYTE *))(*v10 + 360))(v10, v64);
                McTemplateU0zjzz_EventWriteTransfer(
                  (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                  (unsigned int)RasDdmParamTraceInfo,
                  (unsigned int)&v82,
                  v17,
                  v16,
                  (__int64)&v76);
              }
            }
LABEL_24:
            v4 = 87;
LABEL_31:
            (*(void (__fastcall **)(__int64 *))(*v10 + 8))(v10);
            goto LABEL_32;
          }
          (*(void (__fastcall **)(__int64 *))(*v10 + 64))(v10);
          (*(void (__fastcall **)(__int64 *, __int64))(*v10 + 752))(v10, 929);
          goto LABEL_31;
        }
        if ( (byte_1800CF404 & 0x10) != 0 )
        {
          LOWORD(v82) = 0;
          LOWORD(v76) = 0;
          v18 = (*(__int64 (__fastcall **)(__int64 *))(*v10 + 280))(v10);
          FormatRRASErrorString(
            &v82,
            L"DDMDisconnectInterface: Interface is\t\t\t\t\t\t\t\tin RISTATE_CONNECTING %ws",
            v18);
          if ( (byte_1800CF404 & 0x10) != 0 )
          {
            v19 = (*(__int64 (__fastcall **)(__int64 *))(*v10 + 280))(v10);
            v20 = (*(__int64 (__fastcall **)(__int64 *, _BYTE *))(*v10 + 360))(v10, v64);
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasDdmParamTraceInfo,
              (unsigned int)&v82,
              v20,
              v19,
              (__int64)&v76);
          }
        }
        v4 = 906;
      }
    }
    v7 = 1;
    goto LABEL_31;
  }
  v26 = 0;
  EnterCriticalSection(&gblDeviceTable);
  v80 = 0;
  memset_0(v81, 0, sizeof(v81));
  v72 = 0;
  v75 = 0;
  v73 = 0;
  v74 = 0;
  v65 = 0;
  (**(void (__fastcall ***)(__int64))g_pIDimInterfaceTable)(g_pIDimInterfaceTable);
  v27 = (struct IDimInterface *)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)g_pIDimInterfaceTable + 64LL))(
                                  g_pIDimInterfaceTable,
                                  a1);
  v28 = -1;
  v29 = v27;
  if ( v27 )
  {
    (**(void (__fastcall ***)(struct IDimInterface *))v27)(v27);
    v30 = *(_QWORD *)v29;
    if ( a2 == -1 )
      (*(void (__fastcall **)(struct IDimInterface *, _QWORD))(v30 + 328))(v29, 0);
    else
      (*(void (__fastcall **)(struct IDimInterface *, _QWORD, _QWORD))(v30 + 320))(v29, a2, 0);
    v31 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v29 + 40LL))(v29);
    if ( !v31 )
      goto LABEL_90;
    v32 = v31 - 1;
    if ( v32 )
    {
      if ( v32 != 1 || !(*(unsigned __int8 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v29 + 312LL))(v29) )
        goto LABEL_90;
      if ( ((*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v29 + 104LL))(v29) & 1) == 0 )
        goto LABEL_69;
      (*(void (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v29 + 64LL))(v29);
      if ( (byte_1800CF404 & 0x10) == 0
        || (LOWORD(v80) = 0,
            LOWORD(v72) = 0,
            v33 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v29 + 264LL))(v29),
            ConvertPortNoToString(&v72, v33),
            v34 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v29 + 264LL))(v29),
            FormatRRASErrorString(&v80, L"DDMDisconnectInterface: %d disconnecting 0x%x", 418, v34),
            (byte_1800CF404 & 0x10) == 0) )
      {
LABEL_68:
        v41 = (HRASCONN)(*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v29 + 264LL))(v29);
        RasHangUpW(v41);
LABEL_69:
        v61 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v29 + 248LL))(v29);
        v59 = 1;
        goto LABEL_90;
      }
      v35 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v29 + 280LL))(v29);
      v36 = (*(__int64 (__fastcall **)(struct IDimInterface *, _BYTE *))(*(_QWORD *)v29 + 360LL))(v29, v64) == 0;
      v37 = v29;
      v38 = *(__int64 (__fastcall **)(struct IDimInterface *, DdmConnection **))(*(_QWORD *)v29 + 360LL);
      if ( v36 )
      {
        if ( !v38(v29, v62) )
        {
          v40 = &v65;
          goto LABEL_67;
        }
        v39 = v66;
        v37 = v29;
        v38 = *(__int64 (__fastcall **)(struct IDimInterface *, DdmConnection **))(*(_QWORD *)v29 + 360LL);
      }
      else
      {
        v39 = v63;
      }
      LODWORD(v40) = v38(v37, (DdmConnection **)v39);
LABEL_67:
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceInfo,
        (unsigned int)&v80,
        (_DWORD)v40,
        v35,
        (__int64)&v72);
      goto LABEL_68;
    }
    if ( (*(unsigned __int8 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v29 + 312LL))(v29) )
    {
      if ( ((*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v29 + 104LL))(v29) & 1) != 0 )
      {
        (*(void (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v29 + 64LL))(v29);
        if ( !(*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v29 + 264LL))(v29) )
          goto LABEL_83;
        if ( (byte_1800CF404 & 0x10) == 0
          || (LOWORD(v80) = 0,
              LOWORD(v72) = 0,
              v42 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v29 + 264LL))(v29),
              ConvertPortNoToString(&v72, v42),
              v43 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v29 + 264LL))(v29),
              FormatRRASErrorString(&v80, L"DDMDisconnectInterface: %d hanging up 0x%x", 366, v43),
              (byte_1800CF404 & 0x10) == 0) )
        {
LABEL_82:
          v49 = (HRASCONN)(*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v29 + 264LL))(v29);
          RasHangUpW(v49);
LABEL_83:
          if ( (byte_1800CF404 & 0x10) != 0 )
          {
            LOWORD(v80) = 0;
            LOWORD(v72) = 0;
            v50 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v29 + 280LL))(v29);
            FormatRRASErrorString(&v80, L"%s:Marking interface '%ws' DISCONNECTED.", L"DDMDisconnectInterface", v50);
            if ( (byte_1800CF404 & 0x10) != 0 )
            {
              v51 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v29 + 280LL))(v29);
              v52 = (*(__int64 (__fastcall **)(struct IDimInterface *, struct _EVENT_DATA_DESCRIPTOR *))(*(_QWORD *)v29 + 360LL))(
                      v29,
                      &v68);
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RasDdmParamTraceInfo,
                (unsigned int)&v80,
                v52,
                v51,
                (__int64)&v72);
            }
          }
          InterfaceDisconnected(v29);
          if ( (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v29 + 224LL))(v29) != -1 )
          {
            v53 = (void *)(*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v29 + 224LL))(v29);
            SetEvent(v53);
            (*(void (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v29 + 240LL))(v29);
          }
          (*(void (__fastcall **)(struct IDimInterface *, _QWORD, __int64, _QWORD))(*(_QWORD *)v29 + 440LL))(
            v29,
            0,
            1,
            (unsigned int)dword_1800CF658);
          LOBYTE(v54) = 1;
          (*(void (__fastcall **)(struct IDimInterface *, __int64, __int64, _QWORD))(*(_QWORD *)v29 + 440LL))(
            v29,
            v54,
            1,
            (unsigned int)dword_1800CF658);
          goto LABEL_90;
        }
        v44 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v29 + 280LL))(v29);
        v36 = (*(__int64 (__fastcall **)(struct IDimInterface *, _BYTE *))(*(_QWORD *)v29 + 360LL))(v29, v66) == 0;
        v45 = v29;
        v46 = *(__int64 (__fastcall **)(struct IDimInterface *, _QWORD *))(*(_QWORD *)v29 + 360LL);
        if ( v36 )
        {
          if ( !v46(v29, v63) )
          {
            v48 = &v65;
            goto LABEL_81;
          }
          v47 = v62;
          v45 = v29;
          v46 = *(__int64 (__fastcall **)(struct IDimInterface *, _QWORD *))(*(_QWORD *)v29 + 360LL);
        }
        else
        {
          v47 = (DdmConnection **)v64;
        }
        LODWORD(v48) = v46(v45, v47);
LABEL_81:
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasDdmParamTraceInfo,
          (unsigned int)&v80,
          (_DWORD)v48,
          v44,
          (__int64)&v72);
        goto LABEL_82;
      }
      v4 = 906;
    }
LABEL_90:
    if ( ((*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v29 + 104LL))(v29) & 0x10) != 0
      && ((*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v29 + 104LL))(v29) & 1) != 0 )
    {
      v26 = 1;
    }
    (*(void (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v29 + 8LL))(v29);
    goto LABEL_94;
  }
  v4 = 6;
LABEL_94:
  (*(void (__fastcall **)(__int64))(*(_QWORD *)g_pIDimInterfaceTable + 16LL))(g_pIDimInterfaceTable);
  if ( v59 )
  {
    hEvent = 0;
    v55 = DdmConnectionTable::GetInstance();
    DdmConnectionTable::FindConnection(v55, v61, &hEvent);
    v56 = (volatile signed __int32 *)hEvent;
    if ( hEvent )
    {
      if ( v26 )
        *((_DWORD *)hEvent + 20) |= 0x20u;
      DdmConnection::Disconnect((DdmConnection *)v56, 0);
      if ( v56 && _InterlockedExchangeAdd(v56 + 2, 0xFFFFFFFF) == 1 )
        (**(void (__fastcall ***)(HANDLE, __int64))hEvent)(hEvent, 1);
    }
  }
  LeaveCriticalSection(&gblDeviceTable);
  if ( (byte_1800CF404 & 0x10) != 0 )
  {
    LOWORD(v80) = 0;
    FormatRRASErrorString(&v80, L"DDMDisconnectInterface: dwError=%d", v4);
    if ( (byte_1800CF404 & 0x10) != 0 )
    {
      do
        ++v28;
      while ( *(_WORD *)&v81[2 * v28 - 4] );
      v71 = 0;
      v69 = &v80;
      v70 = 2 * v28 + 2;
      McGenEventWrite_EventWriteTransfer(
        (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (const EVENT_DESCRIPTOR *)RasDdmTraceInfo,
        v57,
        2u,
        &v68);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18001a200  mov     [rsp-8+arg_10], rbx
0x18001a205  push    rbp
0x18001a206  push    rsi
0x18001a207  push    rdi
0x18001a208  push    r12
0x18001a20a  push    r13
0x18001a20c  push    r14
0x18001a20e  push    r15
0x18001a210  lea     rbp, [rsp-1030h]
0x18001a218  mov     eax, 1130h
0x18001a21d  call    _alloca_probe
0x18001a222  sub     rsp, rax
0x18001a225  mov     rax, cs:__security_cookie
0x18001a22c  xor     rax, rsp
0x18001a22f  mov     [rbp+1060h+var_40], rax
0x18001a236  xor     r15d, r15d
0x18001a239  mov     ebx, edx
0x18001a23b  cmp     cs:dword_1800CF654, r15d
0x18001a242  mov     rdi, rcx
0x18001a245  mov     esi, r15d
0x18001a248  mov     [rsp+1160h+var_1120], r15
0x18001a24d  mov     [rsp+1160h+var_1130], r15b
0x18001a252  jz      loc_18001A743
0x18001a258  xor     edx, edx; Val
0x18001a25a  mov     [rsp+1160h+hEvent], r15
0x18001a25f  mov     r8d, 7FCh; Size
0x18001a265  mov     [rsp+1160h+var_1108], r15
0x18001a26a  lea     rcx, [rbp+1060h+var_83C]; void *
0x18001a271  mov     [rbp+1060h+var_840], r15d
0x18001a278  mov     r13d, r15d
0x18001a27b  mov     r14d, r15d
0x18001a27e  mov     r12b, r15b
0x18001a281  call    memset_0
0x18001a286  mov     rcx, cs:g_pIDimInterfaceTable
0x18001a28d  xor     eax, eax
0x18001a28f  xorps   xmm0, xmm0
0x18001a292  mov     [rbp+1060h+var_104C], eax
0x18001a295  mov     [rbp+1060h+var_1070], r15d
0x18001a299  movups  [rbp+1060h+var_106C], xmm0
0x18001a29d  mov     rax, [rcx]
0x18001a2a0  movups  [rbp+1060h+var_105C], xmm0
0x18001a2a4  movups  [rbp+1060h+var_10C8], xmm0
0x18001a2a8  mov     rax, [rax]
0x18001a2ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a2b0  mov     rcx, cs:g_pIDimInterfaceTable
0x18001a2b7  mov     rdx, rdi
0x18001a2ba  mov     rax, [rcx]
0x18001a2bd  mov     rax, [rax+40h]
0x18001a2c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a2c6  lea     r15d, [r14+1]
0x18001a2ca  mov     rdi, rax
0x18001a2cd  test    rax, rax
0x18001a2d0  jnz     short loc_18001A2DA
0x18001a2d2  lea     esi, [rax+6]
0x18001a2d5  jmp     loc_18001A5BB
0x18001a2da  mov     rax, [rdi]
0x18001a2dd  mov     rcx, rdi
0x18001a2e0  mov     rax, [rax]
0x18001a2e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a2e8  mov     rax, [rdi]
0x18001a2eb  mov     rcx, rdi
0x18001a2ee  cmp     ebx, 0FFFFFFFFh
0x18001a2f1  jnz     short loc_18001A303
0x18001a2f3  mov     rax, [rax+148h]
0x18001a2fa  xor     edx, edx
0x18001a2fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a301  jmp     short loc_18001A314
0x18001a303  mov     rax, [rax+140h]
0x18001a30a  xor     r8d, r8d
0x18001a30d  mov     edx, ebx
0x18001a30f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a314  mov     rax, [rdi]
0x18001a317  mov     rcx, rdi
0x18001a31a  mov     rax, [rax+28h]
0x18001a31e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a323  xor     ebx, ebx
0x18001a325  mov     ecx, eax
0x18001a327  test    eax, eax
0x18001a329  jz      loc_18001A5A9
0x18001a32f  sub     ecx, r15d
0x18001a332  jz      short loc_18001A378
0x18001a334  cmp     ecx, r15d
0x18001a337  jnz     loc_18001A3C4
0x18001a33d  mov     rax, [rdi]
0x18001a340  mov     rcx, rdi
0x18001a343  mov     rax, [rax+138h]
0x18001a34a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a34f  test    al, al
0x18001a351  jz      loc_18001A5A9
0x18001a357  mov     rax, [rdi]
0x18001a35a  mov     rcx, rdi
0x18001a35d  mov     rax, [rax+0F8h]
0x18001a364  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a369  mov     r14, rax
0x18001a36c  mov     [rsp+1160h+var_1108], rax
0x18001a371  mov     [rsp+1160h+var_1130], r15b
0x18001a376  jmp     short loc_18001A3C4
0x18001a378  mov     rax, [rdi]
0x18001a37b  mov     rcx, rdi
0x18001a37e  mov     rax, [rax+138h]
0x18001a385  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a38a  test    al, al
0x18001a38c  jz      loc_18001A5A9
0x18001a392  mov     rax, [rdi]
0x18001a395  mov     rcx, rdi
0x18001a398  mov     rax, [rax+68h]
0x18001a39c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a3a1  test    r15b, al
0x18001a3a4  jz      loc_18001A501
0x18001a3aa  mov     rax, [rdi]
0x18001a3ad  mov     rcx, rdi
0x18001a3b0  mov     rax, [rax+108h]
0x18001a3b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a3bc  mov     r13, rax
0x18001a3bf  mov     [rsp+1160h+var_1120], rax
0x18001a3c4  mov     rax, [rdi]
0x18001a3c7  mov     rcx, rdi
0x18001a3ca  mov     rax, [rax+0E0h]
0x18001a3d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a3d6  mov     [rsp+1160h+hEvent], rax
0x18001a3db  cmp     [rsp+1160h+var_1130], bl
0x18001a3df  jz      short loc_18001A420
0x18001a3e1  test    r14, r14
0x18001a3e4  jnz     loc_18001A4D6
0x18001a3ea  mov     r14b, 10h
0x18001a3ed  test    cs:byte_1800CF404, r14b
0x18001a3f4  jz      loc_18001A4CC
0x18001a3fa  mov     word ptr [rbp+1060h+var_840], bx
0x18001a401  mov     rcx, rdi
0x18001a404  mov     word ptr [rbp+1060h+var_1070], bx
0x18001a408  mov     rax, [rdi]
0x18001a40b  mov     rax, [rax+118h]
0x18001a412  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a417  lea     rdx, aDdmdisconnecti_0; "DDMDisconnectInterface: hConnection is "...
0x18001a41e  jmp     short loc_18001A45D
0x18001a420  test    r13, r13
0x18001a423  jnz     loc_18001A4D6
0x18001a429  mov     r14b, 10h
0x18001a42c  test    cs:byte_1800CF404, r14b
0x18001a433  jz      loc_18001A4CC
0x18001a439  mov     word ptr [rbp+1060h+var_840], bx
0x18001a440  mov     rcx, rdi
0x18001a443  mov     word ptr [rbp+1060h+var_1070], bx
0x18001a447  mov     rax, [rdi]
0x18001a44a  mov     rax, [rax+118h]
0x18001a451  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a456  lea     rdx, aDdmdisconnecti_4; "DDMDisconnectInterface: hPort is nullpt"...
0x18001a45d  mov     r8, rax
0x18001a460  lea     rcx, [rbp+1060h+var_840]
0x18001a467  call    FormatRRASErrorString
0x18001a46c  test    cs:byte_1800CF404, r14b
0x18001a473  jz      short loc_18001A4CC
0x18001a475  mov     rax, [rdi]
0x18001a478  mov     rcx, rdi
0x18001a47b  mov     rax, [rax+118h]
0x18001a482  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a487  mov     rbx, rax
0x18001a48a  lea     rdx, [rsp+1160h+var_10F8]
0x18001a48f  mov     rax, [rdi]
0x18001a492  mov     rcx, rdi
0x18001a495  mov     rax, [rax+168h]
0x18001a49c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a4a1  lea     rcx, [rbp+1060h+var_1070]
0x18001a4a5  mov     r9, rax
0x18001a4a8  mov     [rsp+1160h+var_1138], rcx
0x18001a4ad  lea     r8, [rbp+1060h+var_840]
0x18001a4b4  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001a4bb  mov     [rsp+1160h+var_1140], rbx
0x18001a4c0  lea     rdx, RasDdmParamTraceInfo
0x18001a4c7  call    McTemplateU0zjzz_EventWriteTransfer
0x18001a4cc  mov     esi, 57h ; 'W'
0x18001a4d1  jmp     loc_18001A5AC
0x18001a4d6  mov     rax, [rdi]
0x18001a4d9  mov     rcx, rdi
0x18001a4dc  mov     rax, [rax+40h]
0x18001a4e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a4e5  mov     rax, [rdi]
0x18001a4e8  mov     edx, 3A1h
0x18001a4ed  mov     rcx, rdi
0x18001a4f0  mov     rax, [rax+2F0h]
0x18001a4f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a4fc  jmp     loc_18001A5AC
0x18001a501  mov     r14b, 10h
0x18001a504  test    cs:byte_1800CF404, r14b
0x18001a50b  jz      loc_18001A5A4
0x18001a511  mov     word ptr [rbp+1060h+var_840], bx
0x18001a518  mov     rcx, rdi
0x18001a51b  mov     word ptr [rbp+1060h+var_1070], bx
0x18001a51f  mov     rax, [rdi]
0x18001a522  mov     rax, [rax+118h]
0x18001a529  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a52e  mov     r8, rax
0x18001a531  lea     rdx, aDdmdisconnecti_3; "DDMDisconnectInterface: Interface is\t"...
0x18001a538  lea     rcx, [rbp+1060h+var_840]
0x18001a53f  call    FormatRRASErrorString
0x18001a544  test    cs:byte_1800CF404, r14b
0x18001a54b  jz      short loc_18001A5A4
0x18001a54d  mov     rax, [rdi]
0x18001a550  mov     rcx, rdi
0x18001a553  mov     rax, [rax+118h]
0x18001a55a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a55f  mov     rbx, rax
0x18001a562  lea     rdx, [rsp+1160h+var_10F8]
0x18001a567  mov     rax, [rdi]
0x18001a56a  mov     rcx, rdi
0x18001a56d  mov     rax, [rax+168h]
0x18001a574  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a579  lea     rcx, [rbp+1060h+var_1070]
0x18001a57d  mov     r9, rax
0x18001a580  mov     [rsp+1160h+var_1138], rcx
0x18001a585  lea     r8, [rbp+1060h+var_840]
0x18001a58c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001a593  mov     [rsp+1160h+var_1140], rbx
0x18001a598  lea     rdx, RasDdmParamTraceInfo
0x18001a59f  call    McTemplateU0zjzz_EventWriteTransfer
0x18001a5a4  mov     esi, 38Ah
0x18001a5a9  mov     r12b, r15b
0x18001a5ac  mov     rax, [rdi]
0x18001a5af  mov     rcx, rdi
0x18001a5b2  mov     rax, [rax+8]
0x18001a5b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a5bb  mov     rcx, cs:g_pIDimInterfaceTable
0x18001a5c2  mov     rax, [rcx]
0x18001a5c5  mov     rax, [rax+10h]
0x18001a5c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a5ce  xor     ebx, ebx
0x18001a5d0  test    r12b, r12b
0x18001a5d3  jnz     loc_18001ADAC
0x18001a5d9  test    esi, esi
0x18001a5db  jnz     loc_18001ADAC
0x18001a5e1  xor     r9d, r9d; lpName
0x18001a5e4  xor     r8d, r8d; bInitialState
0x18001a5e7  mov     edx, r15d; bManualReset
0x18001a5ea  xor     ecx, ecx; lpEventAttributes
0x18001a5ec  call    cs:__imp_CreateEventW
0x18001a5f3  nop     dword ptr [rax+rax+00h]
0x18001a5f8  movzx   r13d, bl
0x18001a5fc  mov     r14b, r15b
0x18001a5ff  mov     rdi, rax
0x18001a602  mov     [rsp+1160h+var_1118], rbx
0x18001a607  mov     rax, [rsp+1160h+hEvent]
0x18001a60c  dec     rax
0x18001a60f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001a613  cmovbe  r13d, r15d
0x18001a617  cmp     [rsp+1160h+var_1130], bl
0x18001a61b  jz      short loc_18001A651
0x18001a61d  call    ?GetInstance@DdmConnectionTable@@SAPEAV1@XZ; DdmConnectionTable::GetInstance(void)
0x18001a622  mov     rdx, [rsp+1160h+var_1108]
0x18001a627  lea     r8, [rsp+1160h+var_1118]
0x18001a62c  mov     rcx, rax
0x18001a62f  call    ?FindConnection@DdmConnectionTable@@QEAAXPEAXAEAV?$RasObjPtr@VDdmConnection@@@@@Z; DdmConnectionTable::FindConnection(void *,RasObjPtr<DdmConnection> &)
0x18001a634  mov     rbx, [rsp+1160h+var_1118]
0x18001a639  test    rbx, rbx
0x18001a63c  jz      short loc_18001A677
0x18001a63e  mov     rdx, rdi; void *
0x18001a641  mov     rcx, rbx; this
0x18001a644  call    ?Disconnect@DdmConnection@@QEAAKPEAX@Z; DdmConnection::Disconnect(void *)
0x18001a649  xor     r14b, r14b
0x18001a64c  jmp     loc_18001A6E7
0x18001a651  mov     ecx, 11h; unsigned int
0x18001a656  call    ?GetInstance@DdmDeviceTable@@SAPEAV1@K@Z; DdmDeviceTable::GetInstance(ulong)
0x18001a65b  mov     rdx, [rsp+1160h+var_1120]
0x18001a660  lea     r8, [rsp+1160h+var_1118]
0x18001a665  mov     rcx, rax
0x18001a668  call    ?FindDevice@DdmDeviceTable@@QEAAXPEAXAEAV?$RasObjPtr@VDdmDevice@@@@@Z; DdmDeviceTable::FindDevice(void *,RasObjPtr<DdmDevice> &)
0x18001a66d  mov     rbx, [rsp+1160h+var_1118]
0x18001a672  test    rbx, rbx
0x18001a675  jnz     short loc_18001A67E
0x18001a677  mov     esi, 57h ; 'W'
0x18001a67c  jmp     short loc_18001A6E7
0x18001a67e  lea     rcx, [rbx+10h]; lpCriticalSection
0x18001a682  call    cs:__imp_EnterCriticalSection
0x18001a689  nop     dword ptr [rax+rax+00h]
0x18001a68e  xor     r14d, r14d
0x18001a691  cmp     [rbx+2CB8h], r14
0x18001a698  jz      short loc_18001A6B0
0x18001a69a  mov     rcx, rdi; hObject
0x18001a69d  call    cs:__imp_CloseHandle
0x18001a6a4  nop     dword ptr [rax+rax+00h]
0x18001a6a9  mov     rdi, [rbx+2CB8h]
0x18001a6b0  mov     rax, [rbx]
0x18001a6b3  mov     rdx, rdi
0x18001a6b6  mov     rcx, rbx
0x18001a6b9  mov     rax, [rax+98h]
0x18001a6c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a6c5  lea     rcx, [rbx+10h]; lpCriticalSection
0x18001a6c9  call    cs:__imp_LeaveCriticalSection
0x18001a6d0  nop     dword ptr [rax+rax+00h]
0x18001a6d5  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001a6d8  mov     rcx, rdi; hHandle
0x18001a6db  call    cs:__imp_WaitForSingleObject
0x18001a6e2  nop     dword ptr [rax+rax+00h]
0x18001a6e7  test    rbx, rbx
0x18001a6ea  jz      short loc_18001A710
0x18001a6ec  or      r12, 0FFFFFFFFFFFFFFFFh
0x18001a6f0  mov     eax, r12d
0x18001a6f3  lock xadd [rbx+8], eax
0x18001a6f8  add     eax, r12d
0x18001a6fb  jnz     short loc_18001A710
0x18001a6fd  mov     rcx, [rsp+1160h+var_1118]
  ... truncated ...
```
