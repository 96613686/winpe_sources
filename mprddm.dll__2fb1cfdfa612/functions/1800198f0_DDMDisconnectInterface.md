# DDMDisconnectInterface

- ea: `0x1800198f0`
- end: `0x18001a506`
- name: `DDMDisconnectInterface`
- size: `3094`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180003fc0`

## callees

- `0x180007b7c`
- `0x180007c50`
- `0x180008e08`
- `0x1800198f0`
- `0x18002ce44`
- `0x18002e0ec`
- `0x18002e268`
- `0x18003b7a8`
- `0x18003b8f4`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `msvcrt!_itow_s` at `0x180019fc0`
- `msvcrt!_itow_s` at `0x18001a174`
- `msvcrt!_itow_s` at `0x180019fc0`
- `msvcrt!_itow_s` at `0x18001a174`
- `KERNEL32!SetEvent` at `0x180019e47`
- `KERNEL32!SetEvent` at `0x18001a341`
- `KERNEL32!SetEvent` at `0x180019e47`
- `KERNEL32!SetEvent` at `0x18001a341`
- `KERNEL32!CloseHandle` at `0x180019dbe`
- `KERNEL32!CloseHandle` at `0x180019ddc`
- `KERNEL32!CloseHandle` at `0x180019dbe`
- `KERNEL32!CloseHandle` at `0x180019ddc`
- `KERNEL32!CreateEventW` at `0x180019d39`
- `KERNEL32!CreateEventW` at `0x180019d39`
- `KERNEL32!WaitForSingleObject` at `0x180019e0e`
- `KERNEL32!WaitForSingleObject` at `0x180019e0e`
- `KERNEL32!LeaveCriticalSection` at `0x180019e02`
- `KERNEL32!LeaveCriticalSection` at `0x18001a465`
- `KERNEL32!LeaveCriticalSection` at `0x180019e02`
- `KERNEL32!LeaveCriticalSection` at `0x18001a465`
- `KERNEL32!EnterCriticalSection` at `0x180019dca`
- `KERNEL32!EnterCriticalSection` at `0x180019e61`
- `KERNEL32!EnterCriticalSection` at `0x180019dca`
- `KERNEL32!EnterCriticalSection` at `0x180019e61`
- `RASAPI32!RasHangUpW` at `0x18001a0b5`
- `RASAPI32!RasHangUpW` at `0x18001a26a`
- `RASAPI32!RasHangUpW` at `0x18001a0b5`
- `RASAPI32!RasHangUpW` at `0x18001a26a`

## pseudocode

```c
__int64 __fastcall DDMDisconnectInterface(__int64 a1, unsigned int a2)
{
  int v2; // r13d
  unsigned int v5; // esi
  char *v6; // r13
  __int64 v7; // r14
  char v8; // r12
  void (__fastcall **v9)(__int64); // rax
  __int64 *v10; // rax
  __int64 *v11; // rdi
  __int64 v12; // rax
  int v13; // ecx
  int v14; // ecx
  DdmConnection *v15; // rbx
  __int64 v16; // rax
  __int64 v17; // rbx
  int v18; // eax
  __int64 v19; // rax
  __int64 v20; // rbx
  int v21; // eax
  __int64 v22; // rax
  __int64 v23; // rbx
  int v24; // eax
  HANDLE EventW; // rdi
  struct DdmConnectionTable *Instance; // rax
  DdmConnection *v27; // rbx
  struct DdmDeviceTable *v28; // rax
  struct IDimInterface *v29; // rax
  __int64 v30; // r12
  struct IDimInterface *v31; // rdi
  __int64 v32; // rax
  int v33; // ecx
  int v34; // ecx
  int v35; // eax
  __int64 v36; // rax
  __int64 v37; // rbx
  bool v38; // zf
  struct IDimInterface *v39; // rcx
  __int64 (__fastcall *v40)(struct IDimInterface *, _BYTE *); // rax
  _BYTE *v41; // rdx
  __int128 *v42; // rax
  HRASCONN v43; // rax
  int v44; // eax
  __int64 v45; // rax
  __int64 v46; // rbx
  struct IDimInterface *v47; // rcx
  __int64 (__fastcall *v48)(struct IDimInterface *, struct _EVENT_DATA_DESCRIPTOR *); // rax
  struct _EVENT_DATA_DESCRIPTOR *v49; // rdx
  __int128 *v50; // rax
  HRASCONN v51; // rax
  __int64 v52; // rax
  __int64 v53; // rbx
  int v54; // eax
  void *v55; // rax
  __int64 v56; // rdx
  struct DdmConnectionTable *v57; // rax
  volatile signed __int32 *v58; // rbx
  __int64 v59; // r8
  char v61; // [rsp+30h] [rbp-D0h]
  DdmConnection *v62; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v63[2]; // [rsp+40h] [rbp-C0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v64; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v65; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v66[16]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v67[16]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v68; // [rsp+90h] [rbp-70h]
  struct _EVENT_DATA_DESCRIPTOR v69; // [rsp+A0h] [rbp-60h] BYREF
  int *v70; // [rsp+B0h] [rbp-50h]
  int v71; // [rsp+B8h] [rbp-48h]
  int v72; // [rsp+BCh] [rbp-44h]
  wchar_t Buffer[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v74; // [rsp+C4h] [rbp-3Ch]
  __int128 v75; // [rsp+D4h] [rbp-2Ch]
  int v76; // [rsp+E4h] [rbp-1Ch]
  int v77; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v78[2044]; // [rsp+F4h] [rbp-Ch] BYREF

  v5 = 0;
  v63[0] = 0;
  v61 = 0;
  if ( dword_1800C8654 )
  {
    v62 = 0;
    v77 = 0;
    v6 = 0;
    v7 = 0;
    v8 = 0;
    memset_0(v78, 0, sizeof(v78));
    v76 = 0;
    *(_DWORD *)Buffer = 0;
    v74 = 0;
    v9 = *(void (__fastcall ***)(__int64))g_pIDimInterfaceTable;
    v75 = 0;
    v68 = 0;
    (*v9)(g_pIDimInterfaceTable);
    v10 = (__int64 *)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)g_pIDimInterfaceTable + 64LL))(
                       g_pIDimInterfaceTable,
                       a1);
    v11 = v10;
    if ( !v10 )
    {
      v5 = 6;
LABEL_35:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)g_pIDimInterfaceTable + 16LL))(g_pIDimInterfaceTable);
      if ( v8 || v5 )
        return v5;
      EventW = CreateEventW(0, 1, 0, 0);
      if ( v61 )
      {
        v62 = 0;
        Instance = DdmConnectionTable::GetInstance();
        DdmConnectionTable::FindConnection(Instance, v63[0], &v62);
        v27 = v62;
        if ( v62 )
        {
          DdmConnection::Disconnect(v62, EventW);
LABEL_45:
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v27 + 2, 0xFFFFFFFF) == 1 && v27 )
            (**(void (__fastcall ***)(DdmConnection *, __int64))v27)(v27, 1);
          goto LABEL_48;
        }
      }
      else
      {
        v63[0] = 0;
        v28 = DdmDeviceTable::GetInstance(0x11u);
        DdmDeviceTable::FindDevice(v28, v62, v63);
        v27 = (DdmConnection *)v63[0];
        if ( v63[0] )
        {
          EnterCriticalSection((LPCRITICAL_SECTION)(v63[0] + 16LL));
          if ( *((_QWORD *)v27 + 1431) )
          {
            CloseHandle(EventW);
            EventW = (HANDLE)*((_QWORD *)v27 + 1431);
          }
          (*(void (__fastcall **)(DdmConnection *, HANDLE))(*(_QWORD *)v27 + 152LL))(v27, EventW);
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v27 + 16));
          WaitForSingleObject(EventW, 0xFFFFFFFF);
          goto LABEL_45;
        }
      }
      v5 = 87;
      CloseHandle(EventW);
LABEL_48:
      if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        SetEvent(v6);
      return v5;
    }
    (*(void (__fastcall **)(__int64 *))*v10)(v10);
    v12 = *v11;
    if ( a2 == -1 )
      (*(void (__fastcall **)(__int64 *, _QWORD))(v12 + 328))(v11, 0);
    else
      (*(void (__fastcall **)(__int64 *, _QWORD, _QWORD))(v12 + 320))(v11, a2, 0);
    v13 = (*(__int64 (__fastcall **)(__int64 *))(*v11 + 40))(v11);
    if ( v13 )
    {
      v14 = v13 - 1;
      if ( v14 )
      {
        if ( v14 != 1 )
        {
LABEL_12:
          v15 = 0;
LABEL_13:
          v6 = (char *)(*(__int64 (__fastcall **)(__int64 *))(*v11 + 224))(v11);
          if ( v61 )
          {
            if ( !v7 )
            {
              if ( (byte_1800C8404 & 0x10) != 0 )
              {
                LOWORD(v77) = 0;
                Buffer[0] = 0;
                v16 = (*(__int64 (__fastcall **)(__int64 *))(*v11 + 280))(v11);
                FormatRRASErrorString(&v77, L"DDMDisconnectInterface: hConnection is nullptr for interface %ws", v16);
                if ( (byte_1800C8404 & 0x10) != 0 )
                {
                  v17 = (*(__int64 (__fastcall **)(__int64 *))(*v11 + 280))(v11);
                  v18 = (*(__int64 (__fastcall **)(__int64 *, _BYTE *))(*v11 + 360))(v11, v64);
                  McTemplateU0zjzz_EventWriteTransfer(
                    (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                    (unsigned int)RasDdmParamTraceInfo,
                    (unsigned int)&v77,
                    v18,
                    v17,
                    (__int64)Buffer);
                }
              }
              v5 = 87;
            }
          }
          else if ( !v15 )
          {
            if ( (byte_1800C8404 & 0x10) != 0 )
            {
              LOWORD(v77) = 0;
              Buffer[0] = 0;
              v19 = (*(__int64 (__fastcall **)(__int64 *))(*v11 + 280))(v11);
              FormatRRASErrorString(&v77, L"DDMDisconnectInterface: hPort is nullptr for interface %ws", v19);
              if ( (byte_1800C8404 & 0x10) != 0 )
              {
                v20 = (*(__int64 (__fastcall **)(__int64 *))(*v11 + 280))(v11);
                v21 = (*(__int64 (__fastcall **)(__int64 *, _BYTE *))(*v11 + 360))(v11, v64);
                McTemplateU0zjzz_EventWriteTransfer(
                  (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                  (unsigned int)RasDdmParamTraceInfo,
                  (unsigned int)&v77,
                  v21,
                  v20,
                  (__int64)Buffer);
              }
            }
            v5 = 87;
            goto LABEL_34;
          }
          if ( !v5 )
          {
            (*(void (__fastcall **)(__int64 *))(*v11 + 64))(v11);
            (*(void (__fastcall **)(__int64 *, __int64))(*v11 + 752))(v11, 929);
          }
LABEL_34:
          (*(void (__fastcall **)(__int64 *))(*v11 + 8))(v11);
          goto LABEL_35;
        }
        if ( (*(unsigned __int8 (__fastcall **)(__int64 *))(*v11 + 312))(v11) )
        {
          v7 = (*(__int64 (__fastcall **)(__int64 *))(*v11 + 248))(v11);
          v63[0] = v7;
          v61 = 1;
          goto LABEL_12;
        }
      }
      else if ( (*(unsigned __int8 (__fastcall **)(__int64 *))(*v11 + 312))(v11) )
      {
        if ( ((*(__int64 (__fastcall **)(__int64 *))(*v11 + 104))(v11) & 1) != 0 )
        {
          v15 = (DdmConnection *)(*(__int64 (__fastcall **)(__int64 *))(*v11 + 264))(v11);
          v62 = v15;
          goto LABEL_13;
        }
        if ( (byte_1800C8404 & 0x10) != 0 )
        {
          LOWORD(v77) = 0;
          Buffer[0] = 0;
          v22 = (*(__int64 (__fastcall **)(__int64 *))(*v11 + 280))(v11);
          FormatRRASErrorString(
            &v77,
            L"DDMDisconnectInterface: Interface is\t\t\t\t\t\t\t\tin RISTATE_CONNECTING %ws",
            v22);
          if ( (byte_1800C8404 & 0x10) != 0 )
          {
            v23 = (*(__int64 (__fastcall **)(__int64 *))(*v11 + 280))(v11);
            v24 = (*(__int64 (__fastcall **)(__int64 *, _BYTE *))(*v11 + 360))(v11, v64);
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasDdmParamTraceInfo,
              (unsigned int)&v77,
              v24,
              v23,
              (__int64)Buffer);
          }
        }
        v5 = 906;
      }
    }
    v8 = 1;
    goto LABEL_34;
  }
  LOBYTE(v2) = 0;
  LODWORD(v62) = v2;
  EnterCriticalSection(&gblDeviceTable);
  v77 = 0;
  memset_0(v78, 0, sizeof(v78));
  *(_DWORD *)Buffer = 0;
  v76 = 0;
  v74 = 0;
  v75 = 0;
  v65 = 0;
  (**(void (__fastcall ***)(__int64))g_pIDimInterfaceTable)(g_pIDimInterfaceTable);
  v29 = (struct IDimInterface *)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)g_pIDimInterfaceTable + 64LL))(
                                  g_pIDimInterfaceTable,
                                  a1);
  v30 = -1;
  v31 = v29;
  if ( v29 )
  {
    (**(void (__fastcall ***)(struct IDimInterface *))v29)(v29);
    v32 = *(_QWORD *)v31;
    if ( a2 == -1 )
      (*(void (__fastcall **)(struct IDimInterface *, _QWORD))(v32 + 328))(v31, 0);
    else
      (*(void (__fastcall **)(struct IDimInterface *, _QWORD, _QWORD))(v32 + 320))(v31, a2, 0);
    v33 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v31 + 40LL))(v31);
    if ( !v33 )
      goto LABEL_97;
    v34 = v33 - 1;
    if ( v34 )
    {
      if ( v34 != 1 || !(*(unsigned __int8 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v31 + 312LL))(v31) )
        goto LABEL_97;
      if ( ((*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v31 + 104LL))(v31) & 1) == 0 )
        goto LABEL_73;
      (*(void (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v31 + 64LL))(v31);
      if ( (byte_1800C8404 & 0x10) == 0 )
        goto LABEL_72;
      LOWORD(v77) = 0;
      Buffer[0] = 0;
      v35 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v31 + 264LL))(v31);
      if ( v35 == -1 )
        Buffer[0] = 0;
      else
        _itow_s(v35, Buffer, 0x14u, 10);
      v36 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v31 + 264LL))(v31);
      FormatRRASErrorString(&v77, L"DDMDisconnectInterface: %d disconnecting 0x%x", 418, v36);
      if ( (byte_1800C8404 & 0x10) == 0 )
      {
LABEL_72:
        v43 = (HRASCONN)(*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v31 + 264LL))(v31);
        RasHangUpW(v43);
LABEL_73:
        v63[0] = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v31 + 248LL))(v31);
        v61 = 1;
LABEL_97:
        if ( ((*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v31 + 104LL))(v31) & 0x10) != 0 )
        {
          LOBYTE(v2) = (_BYTE)v62;
          if ( ((*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v31 + 104LL))(v31) & 1) != 0 )
            LOBYTE(v2) = 1;
        }
        else
        {
          LOBYTE(v2) = (_BYTE)v62;
        }
        (*(void (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v31 + 8LL))(v31);
        goto LABEL_103;
      }
      v37 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v31 + 280LL))(v31);
      v38 = (*(__int64 (__fastcall **)(struct IDimInterface *, _BYTE *))(*(_QWORD *)v31 + 360LL))(v31, v64) == 0;
      v39 = v31;
      v40 = *(__int64 (__fastcall **)(struct IDimInterface *, _BYTE *))(*(_QWORD *)v31 + 360LL);
      if ( v38 )
      {
        if ( !v40(v31, v66) )
        {
          v42 = &v65;
          goto LABEL_71;
        }
        v41 = v67;
        v39 = v31;
        v40 = *(__int64 (__fastcall **)(struct IDimInterface *, _BYTE *))(*(_QWORD *)v31 + 360LL);
      }
      else
      {
        v41 = v63;
      }
      LODWORD(v42) = v40(v39, v41);
LABEL_71:
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceInfo,
        (unsigned int)&v77,
        (_DWORD)v42,
        v37,
        (__int64)Buffer);
      goto LABEL_72;
    }
    if ( !(*(unsigned __int8 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v31 + 312LL))(v31) )
      goto LABEL_97;
    if ( ((*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v31 + 104LL))(v31) & 1) == 0 )
    {
      v5 = 906;
      goto LABEL_97;
    }
    (*(void (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v31 + 64LL))(v31);
    if ( !(*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v31 + 264LL))(v31) )
    {
LABEL_90:
      if ( (byte_1800C8404 & 0x10) != 0 )
      {
        LOWORD(v77) = 0;
        Buffer[0] = 0;
        v52 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v31 + 280LL))(v31);
        FormatRRASErrorString(&v77, L"%s:Marking interface '%ws' DISCONNECTED.", L"DDMDisconnectInterface", v52);
        if ( (byte_1800C8404 & 0x10) != 0 )
        {
          v53 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v31 + 280LL))(v31);
          v54 = (*(__int64 (__fastcall **)(struct IDimInterface *, struct _EVENT_DATA_DESCRIPTOR *))(*(_QWORD *)v31 + 360LL))(
                  v31,
                  &v69);
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasDdmParamTraceInfo,
            (unsigned int)&v77,
            v54,
            v53,
            (__int64)Buffer);
        }
      }
      InterfaceDisconnected(v31);
      if ( (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v31 + 224LL))(v31) != -1 )
      {
        v55 = (void *)(*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v31 + 224LL))(v31);
        SetEvent(v55);
        (*(void (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v31 + 240LL))(v31);
      }
      (*(void (__fastcall **)(struct IDimInterface *, _QWORD, __int64, _QWORD))(*(_QWORD *)v31 + 440LL))(
        v31,
        0,
        1,
        (unsigned int)dword_1800C8658);
      LOBYTE(v56) = 1;
      (*(void (__fastcall **)(struct IDimInterface *, __int64, __int64, _QWORD))(*(_QWORD *)v31 + 440LL))(
        v31,
        v56,
        1,
        (unsigned int)dword_1800C8658);
      goto LABEL_97;
    }
    if ( (byte_1800C8404 & 0x10) == 0 )
      goto LABEL_89;
    LOWORD(v77) = 0;
    Buffer[0] = 0;
    v44 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v31 + 264LL))(v31);
    if ( v44 == -1 )
      Buffer[0] = 0;
    else
      _itow_s(v44, Buffer, 0x14u, 10);
    v45 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v31 + 264LL))(v31);
    FormatRRASErrorString(&v77, L"DDMDisconnectInterface: %d hanging up 0x%x", 366, v45);
    if ( (byte_1800C8404 & 0x10) == 0 )
    {
LABEL_89:
      v51 = (HRASCONN)(*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v31 + 264LL))(v31);
      RasHangUpW(v51);
      goto LABEL_90;
    }
    v46 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v31 + 280LL))(v31);
    v38 = (*(__int64 (__fastcall **)(struct IDimInterface *, _BYTE *))(*(_QWORD *)v31 + 360LL))(v31, v67) == 0;
    v47 = v31;
    v48 = *(__int64 (__fastcall **)(struct IDimInterface *, struct _EVENT_DATA_DESCRIPTOR *))(*(_QWORD *)v31 + 360LL);
    if ( v38 )
    {
      if ( !v48(v31, (struct _EVENT_DATA_DESCRIPTOR *)v64) )
      {
        v50 = &v65;
        goto LABEL_88;
      }
      v49 = &v69;
      v47 = v31;
      v48 = *(__int64 (__fastcall **)(struct IDimInterface *, struct _EVENT_DATA_DESCRIPTOR *))(*(_QWORD *)v31 + 360LL);
    }
    else
    {
      v49 = (struct _EVENT_DATA_DESCRIPTOR *)v66;
    }
    LODWORD(v50) = v48(v47, v49);
LABEL_88:
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasDdmParamTraceInfo,
      (unsigned int)&v77,
      (_DWORD)v50,
      v46,
      (__int64)Buffer);
    goto LABEL_89;
  }
  v5 = 6;
LABEL_103:
  (*(void (__fastcall **)(__int64))(*(_QWORD *)g_pIDimInterfaceTable + 16LL))(g_pIDimInterfaceTable);
  if ( v61 )
  {
    v62 = 0;
    v57 = DdmConnectionTable::GetInstance();
    DdmConnectionTable::FindConnection(v57, v63[0], &v62);
    v58 = (volatile signed __int32 *)v62;
    if ( v62 )
    {
      if ( (_BYTE)v2 )
        *((_DWORD *)v62 + 20) |= 0x20u;
      DdmConnection::Disconnect((DdmConnection *)v58, 0);
      if ( _InterlockedExchangeAdd(v58 + 2, 0xFFFFFFFF) == 1 && v58 )
        (**(void (__fastcall ***)(volatile signed __int32 *, __int64))v58)(v58, 1);
    }
  }
  LeaveCriticalSection(&gblDeviceTable);
  if ( (byte_1800C8404 & 0x10) != 0 )
  {
    LOWORD(v77) = 0;
    FormatRRASErrorString(&v77, L"DDMDisconnectInterface: dwError=%d", v5);
    if ( (byte_1800C8404 & 0x10) != 0 )
    {
      do
        ++v30;
      while ( *(_WORD *)&v78[2 * v30 - 4] );
      v72 = 0;
      v70 = &v77;
      v71 = 2 * v30 + 2;
      McGenEventWrite_EventWriteTransfer(
        (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (const EVENT_DESCRIPTOR *)RasDdmTraceInfo,
        v59,
        2u,
        &v69);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x1800198f0  mov     [rsp-8+arg_10], rbx
0x1800198f5  push    rbp
0x1800198f6  push    rsi
0x1800198f7  push    rdi
0x1800198f8  push    r12
0x1800198fa  push    r13
0x1800198fc  push    r14
0x1800198fe  push    r15
0x180019900  lea     rbp, [rsp-800h]
0x180019908  sub     rsp, 900h
0x18001990f  mov     rax, cs:__security_cookie
0x180019916  xor     rax, rsp
0x180019919  mov     [rbp+830h+var_40], rax
0x180019920  xor     r15d, r15d
0x180019923  mov     ebx, edx
0x180019925  cmp     cs:dword_1800C8654, r15d
0x18001992c  mov     rdi, rcx
0x18001992f  mov     esi, r15d
0x180019932  mov     [rsp+930h+var_8F0], r15
0x180019937  mov     [rsp+930h+var_900], r15b
0x18001993c  jz      loc_180019E52
0x180019942  xor     edx, edx; Val
0x180019944  mov     [rsp+930h+var_8F8], r15
0x180019949  mov     r8d, 7FCh; Size
0x18001994f  mov     [rbp+830h+var_840], r15d
0x180019953  lea     rcx, [rbp+830h+var_83C]; void *
0x180019957  mov     r13d, r15d
0x18001995a  mov     r14d, r15d
0x18001995d  mov     r12b, r15b
0x180019960  call    memset_0
0x180019965  mov     rcx, cs:g_pIDimInterfaceTable
0x18001996c  xor     eax, eax
0x18001996e  xorps   xmm0, xmm0
0x180019971  mov     [rbp+830h+var_84C], eax
0x180019974  mov     dword ptr [rbp+830h+Buffer], r15d
0x180019978  movups  [rbp+830h+var_86C], xmm0
0x18001997c  mov     rax, [rcx]
0x18001997f  movups  [rbp+830h+var_85C], xmm0
0x180019983  movups  [rbp+830h+var_8A0], xmm0
0x180019987  mov     rax, [rax]
0x18001998a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001998f  mov     rcx, cs:g_pIDimInterfaceTable
0x180019996  mov     rdx, rdi
0x180019999  mov     rax, [rcx]
0x18001999c  mov     rax, [rax+40h]
0x1800199a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800199a5  lea     r15d, [r14+1]
0x1800199a9  mov     rdi, rax
0x1800199ac  test    rax, rax
0x1800199af  jnz     short loc_1800199B9
0x1800199b1  lea     esi, [rax+6]
0x1800199b4  jmp     loc_180019D03
0x1800199b9  mov     rax, [rax]
0x1800199bc  mov     rcx, rdi
0x1800199bf  mov     rax, [rax]
0x1800199c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800199c7  mov     rax, [rdi]
0x1800199ca  mov     rcx, rdi
0x1800199cd  cmp     ebx, 0FFFFFFFFh
0x1800199d0  jnz     short loc_1800199E2
0x1800199d2  mov     rax, [rax+148h]
0x1800199d9  xor     edx, edx
0x1800199db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800199e0  jmp     short loc_1800199F3
0x1800199e2  mov     rax, [rax+140h]
0x1800199e9  xor     r8d, r8d
0x1800199ec  mov     edx, ebx
0x1800199ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800199f3  mov     rax, [rdi]
0x1800199f6  mov     rcx, rdi
0x1800199f9  mov     rax, [rax+28h]
0x1800199fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019a02  mov     ecx, eax
0x180019a04  test    eax, eax
0x180019a06  jz      loc_180019CF1
0x180019a0c  sub     ecx, r15d
0x180019a0f  jz      loc_180019B52
0x180019a15  cmp     ecx, r15d
0x180019a18  jnz     short loc_180019A53
0x180019a1a  mov     rax, [rdi]
0x180019a1d  mov     rcx, rdi
0x180019a20  mov     rax, [rax+138h]
0x180019a27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019a2c  test    al, al
0x180019a2e  jz      loc_180019CF1
0x180019a34  mov     rax, [rdi]
0x180019a37  mov     rcx, rdi
0x180019a3a  mov     rax, [rax+0F8h]
0x180019a41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019a46  mov     r14, rax
0x180019a49  mov     [rsp+930h+var_8F0], rax
0x180019a4e  mov     [rsp+930h+var_900], r15b
0x180019a53  mov     rbx, rsi
0x180019a56  mov     rax, [rdi]
0x180019a59  mov     rcx, rdi
0x180019a5c  mov     rax, [rax+0E0h]
0x180019a63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019a68  xor     ecx, ecx
0x180019a6a  mov     r13, rax
0x180019a6d  cmp     [rsp+930h+var_900], cl
0x180019a71  jz      loc_180019BA3
0x180019a77  test    r14, r14
0x180019a7a  jnz     loc_180019B1F
0x180019a80  mov     r14b, 10h
0x180019a83  test    cs:byte_1800C8404, r14b
0x180019a8a  jz      loc_180019B1A
0x180019a90  mov     word ptr [rbp+830h+var_840], cx
0x180019a94  mov     [rbp+830h+Buffer], cx
0x180019a98  mov     rcx, rdi
0x180019a9b  mov     rax, [rdi]
0x180019a9e  mov     rax, [rax+118h]
0x180019aa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019aaa  mov     r8, rax
0x180019aad  lea     rdx, aDdmdisconnecti_0; "DDMDisconnectInterface: hConnection is "...
0x180019ab4  lea     rcx, [rbp+830h+var_840]
0x180019ab8  call    FormatRRASErrorString
0x180019abd  test    cs:byte_1800C8404, r14b
0x180019ac4  jz      short loc_180019B1A
0x180019ac6  mov     rax, [rdi]
0x180019ac9  mov     rcx, rdi
0x180019acc  mov     rax, [rax+118h]
0x180019ad3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019ad8  mov     rbx, rax
0x180019adb  lea     rdx, [rsp+930h+var_8E0]
0x180019ae0  mov     rax, [rdi]
0x180019ae3  mov     rcx, rdi
0x180019ae6  mov     rax, [rax+168h]
0x180019aed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019af2  lea     rcx, [rbp+830h+Buffer]
0x180019af6  mov     r9, rax
0x180019af9  mov     [rsp+930h+var_908], rcx
0x180019afe  lea     r8, [rbp+830h+var_840]
0x180019b02  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180019b09  mov     [rsp+930h+var_910], rbx
0x180019b0e  lea     rdx, RasDdmParamTraceInfo
0x180019b15  call    McTemplateU0zjzz_EventWriteTransfer
0x180019b1a  mov     esi, 57h ; 'W'
0x180019b1f  test    esi, esi
0x180019b21  jnz     loc_180019CF4
0x180019b27  mov     rax, [rdi]
0x180019b2a  mov     rcx, rdi
0x180019b2d  mov     rax, [rax+40h]
0x180019b31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019b36  mov     rax, [rdi]
0x180019b39  mov     edx, 3A1h
0x180019b3e  mov     rcx, rdi
0x180019b41  mov     rax, [rax+2F0h]
0x180019b48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019b4d  jmp     loc_180019CF4
0x180019b52  mov     rax, [rdi]
0x180019b55  mov     rcx, rdi
0x180019b58  mov     rax, [rax+138h]
0x180019b5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019b64  test    al, al
0x180019b66  jz      loc_180019CF1
0x180019b6c  mov     rax, [rdi]
0x180019b6f  mov     rcx, rdi
0x180019b72  mov     rax, [rax+68h]
0x180019b76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019b7b  test    r15b, al
0x180019b7e  jz      loc_180019C50
0x180019b84  mov     rax, [rdi]
0x180019b87  mov     rcx, rdi
0x180019b8a  mov     rax, [rax+108h]
0x180019b91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019b96  mov     rbx, rax
0x180019b99  mov     [rsp+930h+var_8F8], rax
0x180019b9e  jmp     loc_180019A56
0x180019ba3  test    rbx, rbx
0x180019ba6  jnz     loc_180019B1F
0x180019bac  mov     r14b, 10h
0x180019baf  test    cs:byte_1800C8404, r14b
0x180019bb6  jz      loc_180019C46
0x180019bbc  mov     word ptr [rbp+830h+var_840], cx
0x180019bc0  mov     [rbp+830h+Buffer], cx
0x180019bc4  mov     rcx, rdi
0x180019bc7  mov     rax, [rdi]
0x180019bca  mov     rax, [rax+118h]
0x180019bd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019bd6  mov     r8, rax
0x180019bd9  lea     rdx, aDdmdisconnecti_4; "DDMDisconnectInterface: hPort is nullpt"...
0x180019be0  lea     rcx, [rbp+830h+var_840]
0x180019be4  call    FormatRRASErrorString
0x180019be9  test    cs:byte_1800C8404, r14b
0x180019bf0  jz      short loc_180019C46
0x180019bf2  mov     rax, [rdi]
0x180019bf5  mov     rcx, rdi
0x180019bf8  mov     rax, [rax+118h]
0x180019bff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019c04  mov     rbx, rax
0x180019c07  lea     rdx, [rsp+930h+var_8E0]
0x180019c0c  mov     rax, [rdi]
0x180019c0f  mov     rcx, rdi
0x180019c12  mov     rax, [rax+168h]
0x180019c19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019c1e  lea     rcx, [rbp+830h+Buffer]
0x180019c22  mov     r9, rax
0x180019c25  mov     [rsp+930h+var_908], rcx
0x180019c2a  lea     r8, [rbp+830h+var_840]
0x180019c2e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180019c35  mov     [rsp+930h+var_910], rbx
0x180019c3a  lea     rdx, RasDdmParamTraceInfo
0x180019c41  call    McTemplateU0zjzz_EventWriteTransfer
0x180019c46  mov     esi, 57h ; 'W'
0x180019c4b  jmp     loc_180019CF4
0x180019c50  mov     r14b, 10h
0x180019c53  test    cs:byte_1800C8404, r14b
0x180019c5a  jz      loc_180019CEC
0x180019c60  xor     eax, eax
0x180019c62  mov     rcx, rdi
0x180019c65  mov     word ptr [rbp+830h+var_840], ax
0x180019c69  mov     [rbp+830h+Buffer], ax
0x180019c6d  mov     rax, [rdi]
0x180019c70  mov     rax, [rax+118h]
0x180019c77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019c7c  mov     r8, rax
0x180019c7f  lea     rdx, aDdmdisconnecti_3; "DDMDisconnectInterface: Interface is\t"...
0x180019c86  lea     rcx, [rbp+830h+var_840]
0x180019c8a  call    FormatRRASErrorString
0x180019c8f  test    cs:byte_1800C8404, r14b
0x180019c96  jz      short loc_180019CEC
0x180019c98  mov     rax, [rdi]
0x180019c9b  mov     rcx, rdi
0x180019c9e  mov     rax, [rax+118h]
0x180019ca5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019caa  mov     rbx, rax
0x180019cad  lea     rdx, [rsp+930h+var_8E0]
0x180019cb2  mov     rax, [rdi]
0x180019cb5  mov     rcx, rdi
0x180019cb8  mov     rax, [rax+168h]
0x180019cbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019cc4  lea     rcx, [rbp+830h+Buffer]
0x180019cc8  mov     r9, rax
0x180019ccb  mov     [rsp+930h+var_908], rcx
0x180019cd0  lea     r8, [rbp+830h+var_840]
0x180019cd4  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180019cdb  mov     [rsp+930h+var_910], rbx
0x180019ce0  lea     rdx, RasDdmParamTraceInfo
0x180019ce7  call    McTemplateU0zjzz_EventWriteTransfer
0x180019cec  mov     esi, 38Ah
0x180019cf1  mov     r12b, r15b
0x180019cf4  mov     rax, [rdi]
0x180019cf7  mov     rcx, rdi
0x180019cfa  mov     rax, [rax+8]
0x180019cfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019d03  mov     rcx, cs:g_pIDimInterfaceTable
0x180019d0a  mov     rax, [rcx]
0x180019d0d  mov     rax, [rax+10h]
0x180019d11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019d16  test    r12b, r12b
0x180019d19  jnz     loc_18001A4DA
0x180019d1f  xor     r12d, r12d
0x180019d22  test    esi, esi
0x180019d24  jnz     loc_18001A4DA
0x180019d2a  xor     r9d, r9d; lpName
0x180019d2d  movzx   r14d, r12b
0x180019d31  xor     r8d, r8d; bInitialState
0x180019d34  mov     edx, r15d; bManualReset
0x180019d37  xor     ecx, ecx; lpEventAttributes
0x180019d39  call    cs:__imp_CreateEventW
0x180019d3f  mov     rdi, rax
0x180019d42  lea     rax, [r13-1]
0x180019d46  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180019d4a  cmovbe  r14d, r15d
0x180019d4e  cmp     [rsp+930h+var_900], r12b
0x180019d53  jz      short loc_180019D8B
0x180019d55  mov     [rsp+930h+var_8F8], r12
0x180019d5a  call    ?GetInstance@DdmConnectionTable@@SAPEAV1@XZ; DdmConnectionTable::GetInstance(void)
0x180019d5f  mov     rdx, [rsp+930h+var_8F0]
0x180019d64  lea     r8, [rsp+930h+var_8F8]
0x180019d69  mov     rcx, rax
0x180019d6c  call    ?FindConnection@DdmConnectionTable@@QEAAXPEAXAEAV?$RasObjPtr@VDdmConnection@@@@@Z; DdmConnectionTable::FindConnection(void *,RasObjPtr<DdmConnection> &)
0x180019d71  mov     rbx, [rsp+930h+var_8F8]
0x180019d76  test    rbx, rbx
0x180019d79  jz      short loc_180019DB6
0x180019d7b  mov     rdx, rdi; void *
0x180019d7e  mov     rcx, rbx; this
0x180019d81  call    ?Disconnect@DdmConnection@@QEAAKPEAX@Z; DdmConnection::Disconnect(void *)
0x180019d86  jmp     loc_180019E14
0x180019d8b  mov     ecx, 11h; unsigned int
0x180019d90  mov     [rsp+930h+var_8F0], r12
0x180019d95  call    ?GetInstance@DdmDeviceTable@@SAPEAV1@K@Z; DdmDeviceTable::GetInstance(ulong)
0x180019d9a  mov     rdx, [rsp+930h+var_8F8]
0x180019d9f  lea     r8, [rsp+930h+var_8F0]
0x180019da4  mov     rcx, rax
0x180019da7  call    ?FindDevice@DdmDeviceTable@@QEAAXPEAXAEAV?$RasObjPtr@VDdmDevice@@@@@Z; DdmDeviceTable::FindDevice(void *,RasObjPtr<DdmDevice> &)
0x180019dac  mov     rbx, [rsp+930h+var_8F0]
0x180019db1  test    rbx, rbx
0x180019db4  jnz     short loc_180019DC6
0x180019db6  mov     rcx, rdi; hObject
0x180019db9  mov     esi, 57h ; 'W'
0x180019dbe  call    cs:__imp_CloseHandle
0x180019dc4  jmp     short loc_180019E3B
0x180019dc6  lea     rcx, [rbx+10h]; lpCriticalSection
0x180019dca  call    cs:__imp_EnterCriticalSection
0x180019dd0  cmp     [rbx+2CB8h], r12
0x180019dd7  jz      short loc_180019DE9
0x180019dd9  mov     rcx, rdi; hObject
0x180019ddc  call    cs:__imp_CloseHandle
0x180019de2  mov     rdi, [rbx+2CB8h]
  ... truncated ...
```
