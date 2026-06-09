# RasPortConnected(HRASCONN__ *,HRASCONN__ *,DdmLegacyDevice *,void *)

- ea: `0x18000ed5c`
- end: `0x18000fa69`
- name: `?RasPortConnected@@YAKPEAUHRASCONN__@@0PEAVDdmLegacyDevice@@PEAX@Z`
- size: `3341`
- prototype: `unsigned int __fastcall(HRASCONN, HRASCONN, struct DdmLegacyDevice *, void *)`
- caller_count: `1`
- callee_count: `20`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000d840`

## callees

- `0x180001338`
- `0x180002bbe`
- `0x180002f58`
- `0x180007c50`
- `0x180008a44`
- `0x18000adb4`
- `0x18000ed5c`
- `0x18002cb30`
- `0x18002cce0`
- `0x18002d844`
- `0x18002e0ec`
- `0x18002e268`
- `0x1800355bc`
- `0x18003b8f4`
- `0x18003c594`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008c6f0`
- `0x18008e010`

## import_xrefs

- `msvcrt!_itow_s` at `0x18000ee49`
- `msvcrt!_itow_s` at `0x18000ef18`
- `msvcrt!_itow_s` at `0x18000efe1`
- `msvcrt!_itow_s` at `0x18000f046`
- `msvcrt!_itow_s` at `0x18000f0e9`
- `msvcrt!_itow_s` at `0x18000f1de`
- `msvcrt!_itow_s` at `0x18000f2e2`
- `msvcrt!_itow_s` at `0x18000f42e`
- `msvcrt!_itow_s` at `0x18000f579`
- `msvcrt!_itow_s` at `0x18000f92f`
- `msvcrt!_itow_s` at `0x18000ee49`
- `msvcrt!_itow_s` at `0x18000ef18`
- `msvcrt!_itow_s` at `0x18000efe1`
- `msvcrt!_itow_s` at `0x18000f046`
- `msvcrt!_itow_s` at `0x18000f0e9`
- `msvcrt!_itow_s` at `0x18000f1de`
- `msvcrt!_itow_s` at `0x18000f2e2`
- `msvcrt!_itow_s` at `0x18000f42e`
- `msvcrt!_itow_s` at `0x18000f579`
- `msvcrt!_itow_s` at `0x18000f92f`
- `KERNEL32!SetEvent` at `0x18000f847`
- `KERNEL32!SetEvent` at `0x18000f847`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000f4b0`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000f7e6`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000f4b0`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000f7e6`
- `KERNEL32!LeaveCriticalSection` at `0x18000f8c9`
- `KERNEL32!LeaveCriticalSection` at `0x18000f8c9`
- `KERNEL32!EnterCriticalSection` at `0x18000f265`
- `KERNEL32!EnterCriticalSection` at `0x18000f4f6`
- `KERNEL32!EnterCriticalSection` at `0x18000f265`
- `KERNEL32!EnterCriticalSection` at `0x18000f4f6`
- `RASAPI32!RasGetEntryDialParamsW` at `0x18000f6b7`
- `RASAPI32!RasGetEntryDialParamsW` at `0x18000f6b7`
- `RASAPI32!RasConnectionNotificationW` at `0x18000eed5`
- `RASAPI32!RasConnectionNotificationW` at `0x18000eed5`
- `rasman!RasGetPortUserData` at `0x18000f3e7`
- `rasman!RasGetPortUserData` at `0x18000f3e7`
- `rasman!RasPortGetBundle` at `0x18000efa3`
- `rasman!RasPortGetBundle` at `0x18000efa3`
- `rasman!RasGetConnectionUserData` at `0x18000f29e`
- `rasman!RasGetConnectionUserData` at `0x18000f29e`

## string_xrefs

- `0x18000f04c`: `UpdateDeviceBundleMap returned %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall RasPortConnected(struct DdmLegacyDevice *a1, HRASCONN a2, struct DdmLegacyDevice *a3, void *a4)
{
  void *v4; // r13
  DdmConnection *v7; // rsi
  int v8; // r14d
  int *v9; // rbx
  HANDLE *v10; // rbx
  struct DdmDeviceTable *Instance; // rax
  DWORD Bundle; // ebx
  int v13; // ecx
  void **v15; // r12
  int v16; // ecx
  DdmDeviceTable *v17; // rax
  int v18; // ecx
  void (__fastcall ***v19)(_QWORD); // rax
  void (__fastcall ***v20)(_QWORD); // r15
  int v21; // ebx
  int v22; // r14d
  char v23; // dl
  int v24; // ecx
  struct DdmConnectionTable *v25; // rax
  DdmConnection *v26; // rax
  DdmConnection *v27; // rax
  char v28; // dl
  int v29; // ecx
  bool v30; // zf
  DdmConnectionTable *v31; // rax
  int v32; // ecx
  int v33; // ecx
  int v34; // eax
  unsigned int PortUserData; // ebx
  int v36; // ecx
  signed __int32 v37; // eax
  int v38; // ecx
  __int64 v39; // r12
  __int64 v40; // rbx
  WCHAR *v41; // rax
  __int64 v42; // r13
  __int64 v43; // r8
  WCHAR *szEntryName; // rdx
  WCHAR v45; // cx
  WCHAR *v46; // rcx
  __int64 v47; // rcx
  WCHAR *szUserName; // r8
  __int64 v49; // rdx
  WCHAR *v50; // rax
  WCHAR v51; // r9
  WCHAR *v52; // rcx
  __int64 v53; // rcx
  WCHAR *szDomain; // r9
  __int64 v55; // rdx
  WCHAR *v56; // rax
  WCHAR v57; // r8
  WCHAR *v58; // rcx
  __int16 *v59; // rax
  _WORD *v60; // rdx
  __int16 v61; // cx
  _WORD *v62; // rcx
  void *v63; // rax
  int v64; // eax
  int v65; // ecx
  WINBOOL v66[2]; // [rsp+30h] [rbp-D0h] BYREF
  int v67; // [rsp+38h] [rbp-C8h] BYREF
  DdmConnection *v68; // [rsp+40h] [rbp-C0h] BYREF
  struct DdmLegacyDevice *v69; // [rsp+48h] [rbp-B8h]
  HRASCONN v70; // [rsp+50h] [rbp-B0h] BYREF
  DdmConnection *v71; // [rsp+58h] [rbp-A8h]
  struct DdmLegacyDevice *v72; // [rsp+60h] [rbp-A0h]
  __int128 Buf1; // [rsp+68h] [rbp-98h] BYREF
  __int128 v74; // [rsp+78h] [rbp-88h] BYREF
  tagRASDIALPARAMSW v75; // [rsp+90h] [rbp-70h] BYREF
  wchar_t Buffer[2]; // [rsp+8E0h] [rbp+7E0h] BYREF
  __int128 v77; // [rsp+8E4h] [rbp+7E4h]
  __int128 v78; // [rsp+8F4h] [rbp+7F4h]
  int v79; // [rsp+904h] [rbp+804h]
  int v80; // [rsp+910h] [rbp+810h] BYREF
  char v81[2044]; // [rsp+914h] [rbp+814h] BYREF

  v4 = a4;
  *(_QWORD *)v66 = a4;
  v70 = a2;
  v69 = a1;
  v7 = 0;
  v68 = 0;
  v8 = *(_DWORD *)DdmDeviceTable::GetInstance(0x11u);
  v72 = a3;
  if ( a3 )
    _InterlockedIncrement((volatile signed __int32 *)a3 + 2);
  v80 = 0;
  memset_0(v81, 0, sizeof(v81));
  *(_DWORD *)Buffer = 0;
  v77 = 0;
  v78 = 0;
  v79 = 0;
  v74 = 0;
  if ( (byte_1800C8404 & 0x10) != 0 )
  {
    LOWORD(v80) = 0;
    Buffer[0] = 0;
    v9 = (int *)((char *)a3 + 96);
    if ( a3 && *v9 != -1 )
      _itow_s(*v9, Buffer, 0x14u, 10);
    FormatRRASErrorString(
      &v80,
      L"Registering for disconnect notification for hPort=%d, fFlag=0x%x",
      *(_QWORD *)v9,
      *((unsigned int *)a3 + 33));
    if ( (byte_1800C8404 & 0x10) != 0 )
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceInfo,
        (unsigned int)&v80,
        (unsigned int)&v74,
        0,
        (__int64)Buffer);
  }
  v10 = gblSupervisorEvents;
  Instance = DdmDeviceTable::GetInstance(0x11u);
  Bundle = RasConnectionNotificationW(a2, v10[*((_DWORD *)a3 + 24) % *(_DWORD *)Instance + 2 * (v8 + 3)], 2u);
  if ( Bundle )
  {
    if ( (byte_1800C8404 & 0x10) != 0 )
    {
      LOWORD(v80) = 0;
      Buffer[0] = 0;
      v13 = *((_DWORD *)a3 + 24);
      if ( v13 != -1 )
        _itow_s(v13, Buffer, 0x14u, 10);
      FormatRRASErrorString(&v80, L"RasConnectionNotification returned %d", Bundle);
LABEL_14:
      if ( (byte_1800C8404 & 0x10) != 0 )
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasDdmParamTraceInfo,
          (unsigned int)&v80,
          (unsigned int)&v74,
          0,
          (__int64)Buffer);
      goto LABEL_16;
    }
    goto LABEL_16;
  }
  v15 = (void **)((char *)a3 + 120);
  Bundle = RasPortGetBundle(0, *((_QWORD *)a3 + 12), (char *)a3 + 120);
  if ( Bundle )
  {
    if ( (byte_1800C8404 & 0x10) != 0 )
    {
      LOWORD(v80) = 0;
      Buffer[0] = 0;
      v16 = *((_DWORD *)a3 + 24);
      if ( v16 != -1 )
        _itow_s(v16, Buffer, 0x14u, 10);
      FormatRRASErrorString(&v80, L"RasPortGetBundle returned %d", Bundle);
      goto LABEL_14;
    }
LABEL_16:
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)a3 + 2, 0xFFFFFFFF) == 1 )
      (**(void (__fastcall ***)(struct DdmLegacyDevice *, __int64))a3)(a3, 1);
    return Bundle;
  }
  v17 = DdmDeviceTable::GetInstance(0x11u);
  Bundle = DdmDeviceTable::UpdateDeviceBundleMap(v17);
  if ( Bundle )
  {
    if ( (byte_1800C8404 & 0x10) != 0 )
    {
      LOWORD(v80) = 0;
      Buffer[0] = 0;
      v18 = *((_DWORD *)a3 + 24);
      if ( v18 != -1 )
        _itow_s(v18, Buffer, 0x14u, 10);
      FormatRRASErrorString(&v80, L"UpdateDeviceBundleMap returned %d", Bundle);
      goto LABEL_14;
    }
    goto LABEL_16;
  }
  (**(void (__fastcall ***)(__int64))g_pIDimInterfaceTable)(g_pIDimInterfaceTable);
  v19 = (void (__fastcall ***)(_QWORD))(*(__int64 (__fastcall **)(__int64, void *))(*(_QWORD *)g_pIDimInterfaceTable
                                                                                  + 64LL))(
                                         g_pIDimInterfaceTable,
                                         v4);
  v20 = v19;
  if ( !v19 )
  {
    v21 = 0;
    v22 = 905;
    goto LABEL_48;
  }
  (**v19)(v19);
  v21 = 1;
  if ( ((unsigned __int8 (__fastcall *)(_QWORD))(*v20)[7])(v20) )
  {
    v23 = byte_1800C8404;
    if ( (byte_1800C8404 & 0x10) != 0 )
    {
      Buffer[0] = 0;
      v24 = *((_DWORD *)a3 + 24);
      if ( v24 != -1 )
      {
        _itow_s(v24, Buffer, 0x14u, 10);
        v23 = byte_1800C8404;
      }
      if ( (v23 & 0x10) != 0 )
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasDdmParamTraceInfo,
          (unsigned int)L"RasPortConnected: Admin disconnected port",
          (unsigned int)&v74,
          0,
          (__int64)Buffer);
    }
    v22 = 619;
    goto LABEL_48;
  }
  v25 = DdmConnectionTable::GetInstance();
  DdmConnectionTable::FindConnection(v25, *v15, &v68);
  v22 = 8;
  v7 = v68;
  if ( v68 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)v68 + 16));
    if ( v4 != *((void **)v7 + 9) )
    {
      Bundle = 912;
      goto LABEL_134;
    }
    goto LABEL_80;
  }
  v67 = 0;
  Buf1 = 0;
  v26 = (DdmConnection *)operator new(0x5E0u);
  v71 = v26;
  if ( v26 )
    v27 = DdmConnection::DdmConnection(v26, v4, *v15);
  else
    v27 = 0;
  RasObjPtr<DdmDevice>::reset(&v68, v27);
  v7 = v68;
  if ( v68 )
  {
    if ( memcmp_0(&Buf1, (char *)a3 + 1076, 0x10u) )
      *(_OWORD *)((char *)v7 + 148) = *(_OWORD *)((char *)a3 + 1076);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)v7 + 16));
    v31 = DdmConnectionTable::GetInstance();
    DdmConnectionTable::AddConnection(v31);
    v67 = 224;
    Bundle = RasGetConnectionUserData(v69, 1, (char *)v7 + 1240, &v67);
    if ( Bundle )
    {
      if ( (byte_1800C8404 & 8) != 0 )
      {
        LOWORD(v80) = 0;
        Buffer[0] = 0;
        v32 = *((_DWORD *)v7 + 16);
        if ( v32 != -1 )
          _itow_s(v32, Buffer, 0x14u, 10);
        FormatRRASErrorString(
          &v80,
          L"RasPortConnected: RasGetConnectionUserData failed to retrieve the proojection info: %d",
          Bundle);
        if ( (byte_1800C8404 & 8) != 0 )
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasDdmParamTraceError,
            (unsigned int)&v80,
            (_DWORD)v7 + 1484,
            (__int64)v7 + 164,
            (__int64)Buffer);
      }
      if ( Bundle != 1168 )
        goto LABEL_134;
      goto LABEL_60;
    }
    if ( *((_DWORD *)v7 + 325) && *((_DWORD *)v7 + 311) )
    {
      if ( *((_WORD *)a3 + 68) != 16 )
        Bundle = 720;
      goto LABEL_134;
    }
    v33 = (unsigned __int16)*((_DWORD *)a3 + 34);
    if ( v33 == 15 )
    {
      *((_DWORD *)v7 + 20) = 128;
    }
    else
    {
      v34 = 1;
      if ( v33 == 16 )
        v34 = 512;
      *((_DWORD *)v7 + 20) = v34;
    }
    *((_QWORD *)v7 + 8) = *((_QWORD *)a3 + 12);
    if ( (*((_DWORD *)v7 + 20) & 0x200) == 0 && *((_WORD *)a3 + 68) != 14 )
    {
      v67 = 20;
      PortUserData = RasGetPortUserData(*((_QWORD *)a3 + 12), 13, (char *)v7 + 1356, &v67);
      if ( PortUserData )
      {
        if ( (byte_1800C8404 & 8) != 0 )
        {
          LOWORD(v80) = 0;
          Buffer[0] = 0;
          v36 = *((_DWORD *)v7 + 16);
          if ( v36 != -1 )
            _itow_s(v36, Buffer, 0x14u, 10);
          FormatRRASErrorString(
            &v80,
            L"RasPortConnected: RasGetPortUserData failed to retrieve endpoint info: %d",
            PortUserData);
          if ( (byte_1800C8404 & 8) != 0 )
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasDdmParamTraceError,
              (unsigned int)&v80,
              (_DWORD)v7 + 1484,
              (__int64)v7 + 164,
              (__int64)Buffer);
        }
        if ( PortUserData == 1168 )
        {
LABEL_60:
          Bundle = 629;
          goto LABEL_134;
        }
      }
    }
    LODWORD(v4) = v66[0];
LABEL_80:
    *((_QWORD *)a3 + 149) = v70;
    GetSystemTimeAsFileTime((LPFILETIME)a3 + 18);
    v69 = a3;
    _InterlockedIncrement((volatile signed __int32 *)a3 + 2);
    Bundle = DdmConnection::AddLink(v7);
    v37 = _InterlockedDecrement((volatile signed __int32 *)a3 + 2);
    if ( Bundle )
    {
      if ( !v37 )
        (**(void (__fastcall ***)(struct DdmLegacyDevice *, __int64))a3)(a3, 1);
    }
    else
    {
      if ( !v37 )
        (**(void (__fastcall ***)(struct DdmLegacyDevice *, __int64))a3)(a3, 1);
      if ( (*((_BYTE *)v7 + 80) & 8) == 0 )
      {
        memset_0(&v75, 0, 0x848u);
        v66[0] = 0;
        if ( (byte_1800C8404 & 0x10) != 0 )
        {
          LOWORD(v80) = 0;
          Buffer[0] = 0;
          v38 = *((_DWORD *)v7 + 16);
          if ( v38 != -1 )
            _itow_s(v38, Buffer, 0x14u, 10);
          FormatRRASErrorString(
            &v80,
            L"Marking interface as CONNECTED for dialout S2S connection at hport: %d.",
            *((_QWORD *)a3 + 12));
          if ( (byte_1800C8404 & 0x10) != 0 )
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasDdmParamTraceInfo,
              (unsigned int)&v80,
              (_DWORD)v7 + 1484,
              (__int64)v7 + 164,
              (__int64)Buffer);
        }
        v70 = 0;
        Bundle = IfObjectConnectedEx((_DWORD)v4, (unsigned int)*v15, (int)v7 + 1240, (unsigned int)&v70, 0);
        if ( Bundle )
          goto LABEL_134;
        *((_DWORD *)v7 + 20) |= 8u;
        if ( qword_1800C8698 )
        {
          v69 = (struct DdmLegacyDevice *)qword_1800C8698();
          LODWORD(v71) = 1;
        }
        else
        {
          LODWORD(v71) = 0;
          v69 = 0;
        }
        memset_0(v75.szEntryName, 0, 0x844u);
        v75.dwSize = 2120;
        v39 = 2147483646;
        v40 = 2147483646;
        v41 = (WCHAR *)((__int64 (__fastcall *)(_QWORD))(*v20)[35])(v20);
        v42 = 257;
        v43 = 257;
        szEntryName = v75.szEntryName;
        do
        {
          if ( !v40 )
            break;
          v45 = *v41;
          if ( !*v41 )
            break;
          ++v41;
          *szEntryName++ = v45;
          --v40;
          --v43;
        }
        while ( v43 );
        v46 = szEntryName - 1;
        if ( v43 )
          v46 = szEntryName;
        *v46 = 0;
        Bundle = RasGetEntryDialParamsW(gblpRouterPhoneBook, &v75, v66);
        if ( (_DWORD)v71 && qword_1800C86A0 )
          qword_1800C86A0(v69);
        if ( Bundle )
        {
          Bundle = 0;
        }
        else
        {
          v47 = 2147483646;
          szUserName = v75.szUserName;
          v49 = 257;
          v50 = (WCHAR *)((char *)v7 + 678);
          do
          {
            if ( !v47 )
              break;
            v51 = *szUserName;
            if ( !*szUserName )
              break;
            ++szUserName;
            *v50++ = v51;
            --v47;
            --v49;
          }
          while ( v49 );
          v52 = v50 - 1;
          if ( v49 )
            v52 = v50;
          *v52 = 0;
          v53 = 2147483646;
          szDomain = v75.szDomain;
          v55 = 16;
          v56 = (WCHAR *)((char *)v7 + 1192);
          do
          {
            if ( !v53 )
              break;
            v57 = *szDomain;
            if ( !*szDomain )
              break;
            ++szDomain;
            *v56++ = v57;
            --v53;
            --v55;
          }
          while ( v55 );
          v58 = v56 - 1;
          if ( v55 )
            v58 = v56;
          *v58 = 0;
          memset_0(&v75, 0, 0x848u);
        }
        v59 = (__int16 *)((__int64 (__fastcall *)(_QWORD))(*v20)[35])(v20);
        v60 = (_WORD *)((char *)v7 + 164);
        do
        {
          if ( !v39 )
            break;
          v61 = *v59;
          if ( !*v59 )
            break;
          ++v59;
          *v60++ = v61;
          --v39;
          --v42;
        }
        while ( v42 );
        v62 = v60 - 1;
        if ( v42 )
          v62 = v60;
        *v62 = 0;
        GetSystemTimeAsFileTime((LPFILETIME)a3 + 18);
        *((_QWORD *)v7 + 11) = *((_QWORD *)a3 + 18);
        *((_DWORD *)v7 + 36) = ((__int64 (__fastcall *)(_QWORD))(*v20)[9])(v20);
        ((void (__fastcall *)(void (__fastcall ***)(_QWORD), _QWORD))(*v20)[4])(v20, 0);
        if ( ((__int64 (__fastcall *)(_QWORD))(*v20)[28])(v20) != -1 )
        {
          v63 = (void *)((__int64 (__fastcall *)(_QWORD))(*v20)[28])(v20);
          SetEvent(v63);
          (*v20)[30](v20);
        }
      }
      v64 = *((_DWORD *)a3 + 33);
      if ( (v64 & 8) == 0 )
      {
        if ( (v64 & 0x40) != 0 )
          MediaObjRemoveFromTable((wchar_t *)a3 + 391);
        *((_DWORD *)a3 + 33) |= 8u;
        ++dword_1800C84B0;
      }
      (*(void (__fastcall **)(struct DdmLegacyDevice *, __int64))(*(_QWORD *)a3 + 640LL))(a3, 1);
    }
LABEL_134:
    if ( !Bundle )
    {
      DdmDevice::LogConnectEvent(a3, &v68, (char *)v7 + 1240);
      v7 = v68;
    }
    if ( v7 )
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v7 + 16));
    goto LABEL_138;
  }
  v28 = byte_1800C8404;
  if ( (byte_1800C8404 & 8) != 0 )
  {
    Buffer[0] = 0;
    v29 = *((_DWORD *)a3 + 24);
    if ( v29 != -1 )
    {
      _itow_s(v29, Buffer, (unsigned int)((_DWORD)v68 + 20), (_DWORD)v68 + 10);
      v28 = byte_1800C8404;
    }
    if ( (v28 & 8) != 0 )
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceError,
        (unsigned int)L"ConnObj Allocation failed",
        (unsigned int)&v74,
        0,
        (__int64)Buffer);
  }
LABEL_48:
  v30 = v21 == 0;
  Bundle = v22;
  if ( !v30 && v20 )
LABEL_138:
    (*v20)[1](v20);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)g_pIDimInterfaceTable + 16LL))(g_pIDimInterfaceTable);
  if ( Bundle )
  {
    if ( (byte_1800C8404 & 0x10) != 0 )
    {
      LOWORD(v80) = 0;
      Buffer[0] = 0;
      v65 = *((_DWORD *)a3 + 24);
      if ( v65 != -1 )
        _itow_s(v65, Buffer, 0x14u, 10);
      FormatRRASErrorString(&v80, L"RasPortConnected: Cleaning up hPort=%d, error %d", *((_QWORD *)a3 + 12), Bundle);
      if ( (byte_1800C8404 & 0x10) != 0 )
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasDdmParamTraceInfo,
          (unsigned int)&v80,
          (unsigned int)&v74,
          0,
          (__int64)Buffer);
    }
    (*(void (__fastcall **)(struct DdmLegacyDevice *, _QWORD))(*(_QWORD *)a3 + 160LL))(a3, 0);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)a3 + 2, 0xFFFFFFFF) == 1 )
      (**(void (__fastcall ***)(struct DdmLegacyDevice *, __int64))a3)(a3, 1);
    if ( v7 && _InterlockedExchangeAdd((volatile signed __int32 *)v7 + 2, 0xFFFFFFFF) == 1 )
      (**(void (__fastcall ***)(DdmConnection *, __int64))v7)(v7, 1);
    return Bundle;
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)a3 + 2, 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(struct DdmLegacyDevice *, __int64))a3)(a3, 1);
  if ( v7 && _InterlockedExchangeAdd((volatile signed __int32 *)v7 + 2, 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(DdmConnection *, __int64))v7)(v7, 1);
  return 0;
}

```

## disassembly

```asm
0x18000ed5c  push    rbp
0x18000ed5e  push    rbx
0x18000ed5f  push    rsi
0x18000ed60  push    rdi
0x18000ed61  push    r12
0x18000ed63  push    r13
0x18000ed65  push    r14
0x18000ed67  push    r15
0x18000ed69  lea     rbp, [rsp-1028h]
0x18000ed71  mov     eax, 1128h
0x18000ed76  call    _alloca_probe
0x18000ed7b  sub     rsp, rax
0x18000ed7e  mov     rax, cs:__security_cookie
0x18000ed85  xor     rax, rsp
0x18000ed88  mov     [rbp+1060h+var_50], rax
0x18000ed8f  mov     r13, r9
0x18000ed92  mov     qword ptr [rsp+1160h+var_1130], r9
0x18000ed97  mov     rdi, r8
0x18000ed9a  mov     r15, rdx
0x18000ed9d  mov     [rsp+1160h+var_1110], rdx
0x18000eda2  mov     [rsp+1160h+var_1118], rcx
0x18000eda7  xor     r12d, r12d
0x18000edaa  mov     esi, r12d
0x18000edad  mov     [rsp+1160h+var_1120], r12
0x18000edb2  lea     ecx, [r12+11h]; unsigned int
0x18000edb7  call    ?GetInstance@DdmDeviceTable@@SAPEAV1@K@Z; DdmDeviceTable::GetInstance(ulong)
0x18000edbc  mov     r14d, [rax]
0x18000edbf  mov     [rsp+1160h+var_1100], rdi
0x18000edc4  test    rdi, rdi
0x18000edc7  jz      short loc_18000EDCD
0x18000edc9  lock inc dword ptr [rdi+8]
0x18000edcd  mov     [rbp+1060h+var_850], r12d
0x18000edd4  xor     edx, edx; Val
0x18000edd6  mov     r8d, 7FCh; Size
0x18000eddc  lea     rcx, [rbp+1060h+var_84C]; void *
0x18000ede3  call    memset_0
0x18000ede8  mov     dword ptr [rbp+1060h+Buffer], r12d
0x18000edef  xorps   xmm0, xmm0
0x18000edf2  xor     eax, eax
0x18000edf4  movups  [rbp+1060h+var_87C], xmm0
0x18000edfb  movups  [rbp+1060h+var_86C], xmm0
0x18000ee02  mov     [rbp+1060h+var_85C], eax
0x18000ee08  movups  [rsp+1160h+var_10E8], xmm0
0x18000ee0d  test    cs:byte_1800C8404, 10h
0x18000ee14  jz      loc_18000EEA5
0x18000ee1a  mov     word ptr [rbp+1060h+var_850], r12w
0x18000ee22  mov     [rbp+1060h+Buffer], r12w
0x18000ee2a  lea     rbx, [rdi+60h]
0x18000ee2e  test    rdi, rdi
0x18000ee31  jz      short loc_18000EE4F
0x18000ee33  cmp     dword ptr [rbx], 0FFFFFFFFh
0x18000ee36  jz      short loc_18000EE4F
0x18000ee38  lea     r9d, [rax+0Ah]; Radix
0x18000ee3c  lea     r8d, [rax+14h]; BufferCount
0x18000ee40  lea     rdx, [rbp+1060h+Buffer]; Buffer
0x18000ee47  mov     ecx, [rbx]; Value
0x18000ee49  call    cs:__imp__itow_s
0x18000ee4f  mov     r9d, [rdi+84h]
0x18000ee56  mov     r8, [rbx]
0x18000ee59  lea     rdx, aRegisteringFor; "Registering for disconnect notification"...
0x18000ee60  lea     rcx, [rbp+1060h+var_850]
0x18000ee67  call    FormatRRASErrorString
0x18000ee6c  test    cs:byte_1800C8404, 10h
0x18000ee73  jz      short loc_18000EEA5
0x18000ee75  lea     rax, [rbp+1060h+Buffer]
0x18000ee7c  mov     [rsp+1160h+var_1138], rax
0x18000ee81  mov     [rsp+1160h+var_1140], r12
0x18000ee86  lea     r9, [rsp+1160h+var_10E8]
0x18000ee8b  lea     r8, [rbp+1060h+var_850]
0x18000ee92  lea     rdx, RasDdmParamTraceInfo
0x18000ee99  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000eea0  call    McTemplateU0zjzz_EventWriteTransfer
0x18000eea5  mov     rbx, cs:gblSupervisorEvents
0x18000eeac  mov     ecx, 11h; unsigned int
0x18000eeb1  call    ?GetInstance@DdmDeviceTable@@SAPEAV1@K@Z; DdmDeviceTable::GetInstance(ulong)
0x18000eeb6  mov     rcx, rax
0x18000eeb9  mov     eax, [rdi+60h]
0x18000eebc  xor     edx, edx
0x18000eebe  div     dword ptr [rcx]
0x18000eec0  add     r14d, 3
0x18000eec4  lea     eax, [rdx+r14*2]
0x18000eec8  mov     r8d, 2; DWORD
0x18000eece  mov     rdx, [rbx+rax*8]; HANDLE
0x18000eed2  mov     rcx, r15; HRASCONN
0x18000eed5  call    cs:__imp_RasConnectionNotificationW
0x18000eedb  mov     ebx, eax
0x18000eedd  xor     r14d, r14d
0x18000eee0  test    eax, eax
0x18000eee2  jz      loc_18000EF96
0x18000eee8  test    cs:byte_1800C8404, 10h
0x18000eeef  jz      short loc_18000EF6E
0x18000eef1  mov     word ptr [rbp+1060h+var_850], r14w
0x18000eef9  mov     [rbp+1060h+Buffer], r14w
0x18000ef01  mov     ecx, [rdi+60h]; Value
0x18000ef04  cmp     ecx, 0FFFFFFFFh
0x18000ef07  jz      short loc_18000EF1E
0x18000ef09  lea     r9d, [r14+0Ah]; Radix
0x18000ef0d  lea     r8d, [r14+14h]; BufferCount
0x18000ef11  lea     rdx, [rbp+1060h+Buffer]; Buffer
0x18000ef18  call    cs:__imp__itow_s
0x18000ef1e  lea     rdx, aRasconnectionn; "RasConnectionNotification returned %d"
0x18000ef25  mov     r8d, ebx
0x18000ef28  lea     rcx, [rbp+1060h+var_850]
0x18000ef2f  call    FormatRRASErrorString
0x18000ef34  test    cs:byte_1800C8404, 10h
0x18000ef3b  jz      short loc_18000EF6E
0x18000ef3d  lea     rax, [rbp+1060h+Buffer]
0x18000ef44  mov     [rsp+1160h+var_1138], rax
0x18000ef49  mov     [rsp+1160h+var_1140], r14
0x18000ef4e  lea     r9, [rsp+1160h+var_10E8]
0x18000ef53  lea     r8, [rbp+1060h+var_850]
0x18000ef5a  lea     rdx, RasDdmParamTraceInfo
0x18000ef61  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000ef68  call    McTemplateU0zjzz_EventWriteTransfer
0x18000ef6d  nop
0x18000ef6e  or      eax, 0FFFFFFFFh
0x18000ef71  lock xadd [rdi+8], eax
0x18000ef76  cmp     eax, 1
0x18000ef79  jnz     short loc_18000EF8F
0x18000ef7b  mov     rax, [rdi]
0x18000ef7e  mov     edx, 1
0x18000ef83  mov     rcx, rdi
0x18000ef86  mov     rax, [rax]
0x18000ef89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef8e  nop
0x18000ef8f  mov     eax, ebx
0x18000ef91  jmp     loc_18000FA46
0x18000ef96  lea     r12, [rdi+78h]
0x18000ef9a  mov     r8, r12
0x18000ef9d  mov     rdx, [rdi+60h]
0x18000efa1  xor     ecx, ecx
0x18000efa3  call    cs:__imp_RasPortGetBundle
0x18000efa9  mov     ebx, eax
0x18000efab  test    eax, eax
0x18000efad  jz      short loc_18000EFF3
0x18000efaf  test    cs:byte_1800C8404, 10h
0x18000efb6  jz      short loc_18000EF6E
0x18000efb8  mov     word ptr [rbp+1060h+var_850], r14w
0x18000efc0  mov     [rbp+1060h+Buffer], r14w
0x18000efc8  mov     ecx, [rdi+60h]; Value
0x18000efcb  cmp     ecx, 0FFFFFFFFh
0x18000efce  jz      short loc_18000EFE7
0x18000efd0  mov     r9d, 0Ah; Radix
0x18000efd6  lea     r8d, [r9+0Ah]; BufferCount
0x18000efda  lea     rdx, [rbp+1060h+Buffer]; Buffer
0x18000efe1  call    cs:__imp__itow_s
0x18000efe7  lea     rdx, aRasportgetbund; "RasPortGetBundle returned %d"
0x18000efee  jmp     loc_18000EF25
0x18000eff3  mov     ecx, 11h; unsigned int
0x18000eff8  call    ?GetInstance@DdmDeviceTable@@SAPEAV1@K@Z; DdmDeviceTable::GetInstance(ulong)
0x18000effd  lea     rdx, [rsp+1160h+var_1100]
0x18000f002  mov     rcx, rax; this
0x18000f005  call    ?UpdateDeviceBundleMap@DdmDeviceTable@@QEAAKAEAV?$RasObjPtr@VDdmDevice@@@@@Z; DdmDeviceTable::UpdateDeviceBundleMap(RasObjPtr<DdmDevice> &)
0x18000f00a  mov     ebx, eax
0x18000f00c  test    eax, eax
0x18000f00e  jz      short loc_18000F058
0x18000f010  test    cs:byte_1800C8404, 10h
0x18000f017  jz      loc_18000EF6E
0x18000f01d  mov     word ptr [rbp+1060h+var_850], r14w
0x18000f025  mov     [rbp+1060h+Buffer], r14w
0x18000f02d  mov     ecx, [rdi+60h]; Value
0x18000f030  cmp     ecx, 0FFFFFFFFh
0x18000f033  jz      short loc_18000F04C
0x18000f035  mov     r9d, 0Ah; Radix
0x18000f03b  lea     r8d, [r9+0Ah]; BufferCount
0x18000f03f  lea     rdx, [rbp+1060h+Buffer]; Buffer
0x18000f046  call    cs:__imp__itow_s
0x18000f04c  lea     rdx, aUpdatedevicebu; "UpdateDeviceBundleMap returned %d"
0x18000f053  jmp     loc_18000EF25
0x18000f058  mov     rcx, cs:g_pIDimInterfaceTable
0x18000f05f  mov     rax, [rcx]
0x18000f062  mov     rax, [rax]
0x18000f065  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f06a  mov     rcx, cs:g_pIDimInterfaceTable
0x18000f071  mov     rax, [rcx]
0x18000f074  mov     rdx, r13
0x18000f077  mov     rax, [rax+40h]
0x18000f07b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f080  mov     r15, rax
0x18000f083  test    rax, rax
0x18000f086  jnz     short loc_18000F099
0x18000f088  mov     ebx, r14d
0x18000f08b  mov     r14d, 389h
0x18000f091  xor     r13d, r13d
0x18000f094  jmp     loc_18000F21F
0x18000f099  mov     rax, [rax]
0x18000f09c  mov     rcx, r15
0x18000f09f  mov     rax, [rax]
0x18000f0a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f0a7  mov     ebx, 1
0x18000f0ac  mov     rax, [r15]
0x18000f0af  mov     rcx, r15
0x18000f0b2  mov     rax, [rax+38h]
0x18000f0b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f0bb  test    al, al
0x18000f0bd  jz      short loc_18000F135
0x18000f0bf  mov     dl, cs:byte_1800C8404
0x18000f0c5  test    dl, 10h
0x18000f0c8  jz      short loc_18000F12A
0x18000f0ca  mov     [rbp+1060h+Buffer], r14w
0x18000f0d2  mov     ecx, [rdi+60h]; Value
0x18000f0d5  cmp     ecx, 0FFFFFFFFh
0x18000f0d8  jz      short loc_18000F0F5
0x18000f0da  lea     r9d, [rbx+9]; Radix
0x18000f0de  lea     r8d, [rbx+13h]; BufferCount
0x18000f0e2  lea     rdx, [rbp+1060h+Buffer]; Buffer
0x18000f0e9  call    cs:__imp__itow_s
0x18000f0ef  mov     dl, cs:byte_1800C8404
0x18000f0f5  test    dl, 10h
0x18000f0f8  jz      short loc_18000F12A
0x18000f0fa  lea     rax, [rbp+1060h+Buffer]
0x18000f101  mov     [rsp+1160h+var_1138], rax
0x18000f106  mov     [rsp+1160h+var_1140], r14
0x18000f10b  lea     r9, [rsp+1160h+var_10E8]
0x18000f110  lea     r8, aRasportconnect_1; "RasPortConnected: Admin disconnected po"...
0x18000f117  lea     rdx, RasDdmParamTraceInfo
0x18000f11e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000f125  call    McTemplateU0zjzz_EventWriteTransfer
0x18000f12a  mov     r14d, 26Bh
0x18000f130  jmp     loc_18000F091
0x18000f135  call    ?GetInstance@DdmConnectionTable@@SAPEAV1@XZ; DdmConnectionTable::GetInstance(void)
0x18000f13a  lea     r8, [rsp+1160h+var_1120]
0x18000f13f  mov     rdx, [r12]
0x18000f143  mov     rcx, rax
0x18000f146  call    ?FindConnection@DdmConnectionTable@@QEAAXPEAXAEAV?$RasObjPtr@VDdmConnection@@@@@Z; DdmConnectionTable::FindConnection(void *,RasObjPtr<DdmConnection> &)
0x18000f14b  mov     r14d, 8
0x18000f151  mov     rsi, [rsp+1160h+var_1120]
0x18000f156  test    rsi, rsi
0x18000f159  jnz     loc_18000F4F2
0x18000f15f  mov     [rsp+1160h+var_1128], esi
0x18000f163  xorps   xmm0, xmm0
0x18000f166  movups  [rsp+1160h+Buf1], xmm0
0x18000f16b  mov     ecx, 5E0h; Size
0x18000f170  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f175  mov     [rsp+1160h+var_1108], rax
0x18000f17a  test    rax, rax
0x18000f17d  jz      short loc_18000F193
0x18000f17f  mov     r8, [r12]; void *
0x18000f183  mov     rdx, r13; void *
0x18000f186  mov     rcx, rax; this
0x18000f189  call    ??0DdmConnection@@QEAA@PEAX0@Z; DdmConnection::DdmConnection(void *,void *)
0x18000f18e  xor     r13d, r13d
0x18000f191  jmp     short loc_18000F199
0x18000f193  xor     r13d, r13d
0x18000f196  mov     eax, r13d
0x18000f199  mov     rdx, rax
0x18000f19c  lea     rcx, [rsp+1160h+var_1120]
0x18000f1a1  call    ?reset@?$RasObjPtr@VDdmDevice@@@@QEAAXPEAVDdmDevice@@@Z; RasObjPtr<DdmDevice>::reset(DdmDevice *)
0x18000f1a6  mov     rsi, [rsp+1160h+var_1120]
0x18000f1ab  test    rsi, rsi
0x18000f1ae  jnz     loc_18000F238
0x18000f1b4  mov     dl, cs:byte_1800C8404
0x18000f1ba  test    r14b, dl
0x18000f1bd  jz      short loc_18000F21F
0x18000f1bf  mov     [rbp+1060h+Buffer], r13w
0x18000f1c7  mov     ecx, [rdi+60h]; Value
0x18000f1ca  cmp     ecx, 0FFFFFFFFh
0x18000f1cd  jz      short loc_18000F1EA
0x18000f1cf  lea     r9d, [rsi+0Ah]; Radix
0x18000f1d3  lea     r8d, [rsi+14h]; BufferCount
0x18000f1d7  lea     rdx, [rbp+1060h+Buffer]; Buffer
0x18000f1de  call    cs:__imp__itow_s
0x18000f1e4  mov     dl, cs:byte_1800C8404
0x18000f1ea  test    r14b, dl
0x18000f1ed  jz      short loc_18000F21F
0x18000f1ef  lea     rax, [rbp+1060h+Buffer]
0x18000f1f6  mov     [rsp+1160h+var_1138], rax
0x18000f1fb  mov     [rsp+1160h+var_1140], r13
0x18000f200  lea     r9, [rsp+1160h+var_10E8]
0x18000f205  lea     r8, aConnobjAllocat; "ConnObj Allocation failed"
0x18000f20c  lea     rdx, RasDdmParamTraceError
0x18000f213  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000f21a  call    McTemplateU0zjzz_EventWriteTransfer
0x18000f21f  test    ebx, ebx
0x18000f221  mov     ebx, r14d
0x18000f224  jz      loc_18000F8DE
0x18000f22a  test    r15, r15
0x18000f22d  jz      loc_18000F8DE
0x18000f233  jmp     loc_18000F8CF
0x18000f238  lea     rbx, [rdi+434h]
0x18000f23f  mov     r8d, 10h; Size
0x18000f245  mov     rdx, rbx; Buf2
0x18000f248  lea     rcx, [rsp+1160h+Buf1]; Buf1
0x18000f24d  call    memcmp_0
0x18000f252  test    eax, eax
0x18000f254  jz      short loc_18000F261
0x18000f256  movups  xmm0, xmmword ptr [rbx]
0x18000f259  movdqu  xmmword ptr [rsi+94h], xmm0
0x18000f261  lea     rcx, [rsi+10h]; lpCriticalSection
0x18000f265  call    cs:__imp_EnterCriticalSection
0x18000f26b  call    ?GetInstance@DdmConnectionTable@@SAPEAV1@XZ; DdmConnectionTable::GetInstance(void)
0x18000f270  lea     rdx, [rsp+1160h+var_1120]
0x18000f275  mov     rcx, rax; this
0x18000f278  call    ?AddConnection@DdmConnectionTable@@QEAAXAEAV?$RasObjPtr@VDdmConnection@@@@@Z; DdmConnectionTable::AddConnection(RasObjPtr<DdmConnection> &)
0x18000f27d  mov     [rsp+1160h+var_1128], 0E0h
0x18000f285  lea     r13, [rsi+4D8h]
0x18000f28c  lea     r9, [rsp+1160h+var_1128]
0x18000f291  mov     r8, r13
0x18000f294  mov     edx, 1
0x18000f299  mov     rcx, [rsp+1160h+var_1118]
  ... truncated ...
```
