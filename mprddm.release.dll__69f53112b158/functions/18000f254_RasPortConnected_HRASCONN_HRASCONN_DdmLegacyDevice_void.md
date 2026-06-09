# RasPortConnected(HRASCONN__ *,HRASCONN__ *,DdmLegacyDevice *,void *)

- ea: `0x18000f254`
- end: `0x18000fee0`
- name: `?RasPortConnected@@YAKPEAUHRASCONN__@@0PEAVDdmLegacyDevice@@PEAX@Z`
- size: `3212`
- prototype: `unsigned int __fastcall(HRASCONN, HRASCONN, struct DdmLegacyDevice *, void *)`
- caller_count: `1`
- callee_count: `21`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000dc90`

## callees

- `0x180001328`
- `0x180002fcc`
- `0x180007d00`
- `0x180008b3c`
- `0x18000ace4`
- `0x18000b040`
- `0x18000f254`
- `0x18002ecb0`
- `0x18002ee74`
- `0x18002fb20`
- `0x1800304dc`
- `0x180030684`
- `0x180037218`
- `0x18003d278`
- `0x18003df58`
- `0x180075588`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`
- `0x180092b90`
- `0x180095010`

## import_xrefs

- `KERNEL32!SetEvent` at `0x18000fcaf`
- `KERNEL32!SetEvent` at `0x18000fcaf`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000f9b5`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000fc46`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000f9b5`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000fc46`
- `KERNEL32!LeaveCriticalSection` at `0x18000fd41`
- `KERNEL32!LeaveCriticalSection` at `0x18000fd41`
- `KERNEL32!EnterCriticalSection` at `0x18000f74e`
- `KERNEL32!EnterCriticalSection` at `0x18000fa1d`
- `KERNEL32!EnterCriticalSection` at `0x18000f74e`
- `KERNEL32!EnterCriticalSection` at `0x18000fa1d`
- `RASAPI32!RasGetEntryDialParamsW` at `0x18000fba5`
- `RASAPI32!RasGetEntryDialParamsW` at `0x18000fba5`
- `RASAPI32!RasConnectionNotificationW` at `0x18000f3de`
- `RASAPI32!RasConnectionNotificationW` at `0x18000f3de`
- `rasman!RasGetPortUserData` at `0x18000f8fb`
- `rasman!RasGetPortUserData` at `0x18000f8fb`
- `rasman!RasPortGetBundle` at `0x18000f4a2`
- `rasman!RasPortGetBundle` at `0x18000f4a2`
- `rasman!RasGetConnectionUserData` at `0x18000f796`
- `rasman!RasGetConnectionUserData` at `0x18000f796`

## string_xrefs

- `0x18000f55e`: `UpdateDeviceBundleMap returned %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall RasPortConnected(HRASCONN a1, HRASCONN a2, struct DdmLegacyDevice *a3, void *a4)
{
  DdmConnection *v6; // rbx
  int v7; // r14d
  unsigned int v8; // r13d
  __int64 v9; // rdx
  HANDLE *v10; // rdi
  struct DdmDeviceTable *Instance; // rax
  DWORD Bundle; // r14d
  void **v14; // r12
  DdmDeviceTable *v15; // rax
  void *v16; // r14
  void (__fastcall ***v17)(_QWORD); // rax
  void (__fastcall ***v18)(_QWORD); // r15
  int v19; // r12d
  struct DdmConnectionTable *v20; // rax
  DdmConnection *v21; // rax
  DdmConnection *v22; // rax
  DdmConnectionTable *v23; // rax
  __int64 v24; // rax
  _OWORD *v25; // r9
  int v26; // ecx
  int v27; // eax
  unsigned int PortUserData; // r14d
  __int64 v29; // r13
  const wchar_t *v30; // rax
  const wchar_t *v31; // rax
  void *v32; // rax
  int v33; // eax
  int v34; // [rsp+30h] [rbp-D0h]
  DdmConnection *v35; // [rsp+38h] [rbp-C8h] BYREF
  int v36; // [rsp+40h] [rbp-C0h] BYREF
  int v37; // [rsp+44h] [rbp-BCh]
  int v38; // [rsp+48h] [rbp-B8h]
  HRASCONN v39; // [rsp+50h] [rbp-B0h] BYREF
  WINBOOL v40[2]; // [rsp+58h] [rbp-A8h] BYREF
  void *v41; // [rsp+60h] [rbp-A0h]
  struct DdmLegacyDevice *v42; // [rsp+68h] [rbp-98h]
  struct DdmLegacyDevice *v43; // [rsp+70h] [rbp-90h]
  __int64 v44; // [rsp+78h] [rbp-88h]
  DdmConnection *v45; // [rsp+80h] [rbp-80h]
  _OWORD v46[2]; // [rsp+88h] [rbp-78h] BYREF
  tagRASDIALPARAMSW v47; // [rsp+B0h] [rbp-50h] BYREF
  int v48; // [rsp+900h] [rbp+800h] BYREF
  __int128 v49; // [rsp+904h] [rbp+804h]
  __int128 v50; // [rsp+914h] [rbp+814h]
  int v51; // [rsp+924h] [rbp+824h]
  int v52; // [rsp+930h] [rbp+830h] BYREF
  _BYTE v53[2044]; // [rsp+934h] [rbp+834h] BYREF

  v41 = a4;
  *(_QWORD *)v40 = a2;
  v39 = a1;
  v6 = 0;
  v35 = 0;
  v37 = 0;
  v44 = 0;
  v38 = 0;
  v34 = 0;
  v7 = *(_DWORD *)DdmDeviceTable::GetInstance(0x11u);
  v42 = a3;
  if ( a3 )
  {
    _InterlockedIncrement((volatile signed __int32 *)a3 + 2);
    v6 = v35;
  }
  v52 = 0;
  memset_0(v53, 0, sizeof(v53));
  v48 = 0;
  v49 = 0;
  v50 = 0;
  v51 = 0;
  v46[0] = 0;
  v8 = -1;
  if ( (byte_1800CF404 & 0x10) != 0 )
  {
    LOWORD(v52) = 0;
    LOWORD(v48) = 0;
    v9 = a3 ? *((unsigned int *)a3 + 24) : 0xFFFFFFFFLL;
    ConvertPortNoToString(&v48, v9);
    FormatRRASErrorString(
      &v52,
      L"Registering for disconnect notification for hPort=%d, fFlag=0x%x",
      *((_QWORD *)a3 + 12),
      *((unsigned int *)a3 + 33));
    if ( (byte_1800CF404 & 0x10) != 0 )
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceInfo,
        (unsigned int)&v52,
        (unsigned int)v46,
        0,
        (__int64)&v48);
  }
  v10 = gblSupervisorEvents;
  Instance = DdmDeviceTable::GetInstance(0x11u);
  Bundle = RasConnectionNotificationW(a2, v10[*((_DWORD *)a3 + 24) % *(_DWORD *)Instance + 2 * (v7 + 3)], 2u);
  if ( Bundle )
  {
    if ( (byte_1800CF404 & 0x10) == 0 )
      goto LABEL_13;
    LOWORD(v52) = 0;
    LOWORD(v48) = 0;
    ConvertPortNoToString(&v48, *((unsigned int *)a3 + 24));
    FormatRRASErrorString(&v52, L"RasConnectionNotification returned %d", Bundle);
    if ( (byte_1800CF404 & 0x10) == 0 )
      goto LABEL_13;
    goto LABEL_12;
  }
  v14 = (void **)((char *)a3 + 120);
  Bundle = RasPortGetBundle(0, *((_QWORD *)a3 + 12), (char *)a3 + 120);
  if ( Bundle )
  {
    if ( (byte_1800CF404 & 0x10) == 0 )
      goto LABEL_13;
    LOWORD(v52) = 0;
    LOWORD(v48) = 0;
    ConvertPortNoToString(&v48, *((unsigned int *)a3 + 24));
    FormatRRASErrorString(&v52, L"RasPortGetBundle returned %d", Bundle);
    goto LABEL_19;
  }
  v15 = DdmDeviceTable::GetInstance(0x11u);
  Bundle = DdmDeviceTable::UpdateDeviceBundleMap(v15);
  if ( Bundle )
  {
    if ( (byte_1800CF404 & 0x10) == 0 )
      goto LABEL_13;
    LOWORD(v52) = 0;
    LOWORD(v48) = 0;
    ConvertPortNoToString(&v48, *((unsigned int *)a3 + 24));
    FormatRRASErrorString(&v52, L"UpdateDeviceBundleMap returned %d", Bundle);
LABEL_19:
    if ( (byte_1800CF404 & 0x10) != 0 )
LABEL_12:
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceInfo,
        (unsigned int)&v52,
        (unsigned int)v46,
        0,
        (__int64)&v48);
LABEL_13:
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)a3 + 2, 0xFFFFFFFF) == 1 )
      (**(void (__fastcall ***)(struct DdmLegacyDevice *, __int64))a3)(a3, 1);
    return Bundle;
  }
  (**(void (__fastcall ***)(__int64))g_pIDimInterfaceTable)(g_pIDimInterfaceTable);
  v16 = v41;
  v17 = (void (__fastcall ***)(_QWORD))(*(__int64 (__fastcall **)(__int64, void *))(*(_QWORD *)g_pIDimInterfaceTable
                                                                                  + 64LL))(
                                         g_pIDimInterfaceTable,
                                         v41);
  v18 = v17;
  if ( !v17 )
  {
    Bundle = 905;
    goto LABEL_104;
  }
  (**v17)(v17);
  v38 = 1;
  if ( !((unsigned __int8 (__fastcall *)(_QWORD))(*v18)[7])(v18) )
  {
    v20 = DdmConnectionTable::GetInstance();
    DdmConnectionTable::FindConnection(v20, *v14, &v35);
    v6 = v35;
    if ( v35 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)v35 + 16));
      v19 = 1;
      v34 = 1;
      if ( v16 != *((void **)v6 + 9) )
      {
        Bundle = 912;
        goto LABEL_105;
      }
    }
    else
    {
      v36 = 0;
      v46[1] = 0;
      v21 = (DdmConnection *)operator new(0x5E0u);
      v45 = v21;
      if ( v21 )
        v22 = DdmConnection::DdmConnection(v21, v16, *v14);
      else
        v22 = 0;
      RasObjPtr<DdmDevice>::reset(&v35, v22);
      v6 = v35;
      if ( !v35 )
      {
        if ( (byte_1800CF404 & 8) != 0 )
        {
          LOWORD(v48) = 0;
          ConvertPortNoToString(&v48, *((unsigned int *)a3 + 24));
          if ( (byte_1800CF404 & 8) != 0 )
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasDdmParamTraceError,
              (unsigned int)L"ConnObj Allocation failed",
              (unsigned int)v46,
              0,
              (__int64)&v48);
        }
        Bundle = 8;
        goto LABEL_104;
      }
      if ( *(_QWORD *)((char *)a3 + 1076)
        || _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0] != *(_QWORD *)((char *)a3 + 1084) )
      {
        *(_OWORD *)((char *)v35 + 148) = *(_OWORD *)((char *)a3 + 1076);
      }
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)v6 + 16));
      v19 = 1;
      v34 = 1;
      v23 = DdmConnectionTable::GetInstance();
      DdmConnectionTable::AddConnection(v23);
      v36 = 224;
      Bundle = RasGetConnectionUserData(v39, 1, (char *)v6 + 1240, &v36);
      if ( Bundle )
      {
        if ( (byte_1800CF404 & 8) != 0 )
        {
          LOWORD(v52) = 0;
          LOWORD(v48) = 0;
          if ( v6 )
            v8 = *((_DWORD *)v6 + 16);
          ConvertPortNoToString(&v48, v8);
          FormatRRASErrorString(
            &v52,
            L"RasPortConnected: RasGetConnectionUserData failed to retrieve the proojection info: %d",
            Bundle);
          if ( (byte_1800CF404 & 8) != 0 )
          {
            v24 = (__int64)v6 + 164;
            if ( v6 )
            {
              LODWORD(v25) = (_DWORD)v6 + 1484;
            }
            else
            {
              v24 = 0;
              v25 = v46;
            }
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasDdmParamTraceError,
              (unsigned int)&v52,
              (_DWORD)v25,
              v24,
              (__int64)&v48);
          }
        }
        if ( Bundle != 1168 )
          goto LABEL_105;
        goto LABEL_53;
      }
      if ( *((_DWORD *)v6 + 325) && *((_DWORD *)v6 + 311) )
      {
        if ( *((_WORD *)a3 + 68) != 16 )
          Bundle = 720;
        goto LABEL_105;
      }
      v26 = (unsigned __int16)*((_DWORD *)a3 + 34);
      if ( v26 == 15 )
      {
        *((_DWORD *)v6 + 20) = 128;
      }
      else
      {
        v27 = 1;
        if ( v26 == 16 )
          v27 = 512;
        *((_DWORD *)v6 + 20) = v27;
      }
      *((_QWORD *)v6 + 8) = *((_QWORD *)a3 + 12);
      if ( (*((_DWORD *)v6 + 20) & 0x200) == 0 && *((_WORD *)a3 + 68) != 14 )
      {
        v36 = 20;
        PortUserData = RasGetPortUserData(*((_QWORD *)a3 + 12), 13, (char *)v6 + 1356, &v36);
        if ( PortUserData )
        {
          if ( (byte_1800CF404 & 8) != 0 )
          {
            LOWORD(v52) = 0;
            LOWORD(v48) = 0;
            ConvertPortNoToString(&v48, *((unsigned int *)v6 + 16));
            FormatRRASErrorString(
              &v52,
              L"RasPortConnected: RasGetPortUserData failed to retrieve endpoint info: %d",
              PortUserData);
            if ( (byte_1800CF404 & 8) != 0 )
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RasDdmParamTraceError,
                (unsigned int)&v52,
                (_DWORD)v6 + 1484,
                (__int64)v6 + 164,
                (__int64)&v48);
          }
          if ( PortUserData == 1168 )
          {
LABEL_53:
            Bundle = 629;
            goto LABEL_105;
          }
        }
      }
    }
    *((_QWORD *)a3 + 149) = *(_QWORD *)v40;
    GetSystemTimeAsFileTime((LPFILETIME)a3 + 18);
    v43 = a3;
    if ( a3 )
    {
      _InterlockedIncrement((volatile signed __int32 *)a3 + 2);
      v6 = v35;
    }
    Bundle = DdmConnection::AddLink(v6);
    if ( Bundle )
    {
      if ( a3 )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)a3 + 2, 0xFFFFFFFF) == 1 )
          (**(void (__fastcall ***)(struct DdmLegacyDevice *, __int64))a3)(a3, 1);
        v6 = v35;
      }
    }
    else
    {
      if ( a3 )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)a3 + 2, 0xFFFFFFFF) == 1 )
          (**(void (__fastcall ***)(struct DdmLegacyDevice *, __int64))a3)(a3, 1);
        v6 = v35;
      }
      if ( (*((_BYTE *)v6 + 80) & 8) == 0 )
      {
        memset_0(&v47, 0, 0x848u);
        v40[0] = 0;
        if ( (byte_1800CF404 & 0x10) != 0 )
        {
          LOWORD(v52) = 0;
          LOWORD(v48) = 0;
          ConvertPortNoToString(&v48, *((unsigned int *)v6 + 16));
          FormatRRASErrorString(
            &v52,
            L"Marking interface as CONNECTED for dialout S2S connection at hport: %d.",
            *((_QWORD *)a3 + 12));
          if ( (byte_1800CF404 & 0x10) != 0 )
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasDdmParamTraceInfo,
              (unsigned int)&v52,
              (_DWORD)v6 + 1484,
              (__int64)v6 + 164,
              (__int64)&v48);
        }
        v39 = 0;
        Bundle = IfObjectConnectedEx((_DWORD)v41, *((_QWORD *)a3 + 15), (int)v6 + 1240, (unsigned int)&v39, 0);
        if ( Bundle )
          goto LABEL_104;
        *((_DWORD *)v6 + 20) |= 8u;
        if ( qword_1800CF698 )
        {
          v29 = qword_1800CF698();
          v37 = 1;
        }
        else
        {
          v29 = v44;
        }
        v47.dwSize = 2120;
        v30 = (const wchar_t *)((__int64 (__fastcall *)(_QWORD))(*v18)[35])(v18);
        StringCbCopyW(v47.szEntryName, 0x202u, v30);
        Bundle = RasGetEntryDialParamsW(gblpRouterPhoneBook, &v47, v40);
        if ( v37 && qword_1800CF6A0 )
          qword_1800CF6A0(v29);
        if ( Bundle )
        {
          Bundle = 0;
        }
        else
        {
          StringCbCopyW((STRSAFE_LPWSTR)v6 + 339, 0x202u, v47.szUserName);
          StringCbCopyW((STRSAFE_LPWSTR)v6 + 596, 0x20u, v47.szDomain);
          memset_0(&v47, 0, 0x848u);
        }
        v31 = (const wchar_t *)((__int64 (__fastcall *)(_QWORD))(*v18)[35])(v18);
        StringCbCopyW((STRSAFE_LPWSTR)v6 + 82, 0x202u, v31);
        GetSystemTimeAsFileTime((LPFILETIME)a3 + 18);
        *((_QWORD *)v6 + 11) = *((_QWORD *)a3 + 18);
        *((_DWORD *)v6 + 36) = ((__int64 (__fastcall *)(_QWORD))(*v18)[9])(v18);
        ((void (__fastcall *)(void (__fastcall ***)(_QWORD), _QWORD))(*v18)[4])(v18, 0);
        if ( ((__int64 (__fastcall *)(_QWORD))(*v18)[28])(v18) != -1 )
        {
          v32 = (void *)((__int64 (__fastcall *)(_QWORD))(*v18)[28])(v18);
          SetEvent(v32);
          (*v18)[30](v18);
        }
      }
      v33 = *((_DWORD *)a3 + 33);
      if ( (v33 & 8) == 0 )
      {
        if ( (v33 & 0x40) != 0 )
          MediaObjRemoveFromTable((wchar_t *)a3 + 391);
        *((_DWORD *)a3 + 33) |= 8u;
        ++dword_1800CF4B0;
      }
      (*(void (__fastcall **)(struct DdmLegacyDevice *, __int64))(*(_QWORD *)a3 + 640LL))(a3, 1);
    }
LABEL_104:
    v19 = v34;
    goto LABEL_105;
  }
  Bundle = 619;
  if ( (byte_1800CF404 & 0x10) == 0 )
    goto LABEL_104;
  LOWORD(v48) = 0;
  ConvertPortNoToString(&v48, *((unsigned int *)a3 + 24));
  if ( (byte_1800CF404 & 0x10) != 0 )
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasDdmParamTraceInfo,
      (unsigned int)L"RasPortConnected: Admin disconnected port",
      (unsigned int)v46,
      0,
      (__int64)&v48);
  v19 = 0;
LABEL_105:
  if ( v6 && !Bundle )
  {
    DdmDevice::LogConnectEvent(a3, &v35, (char *)v6 + 1240);
    v6 = v35;
  }
  if ( v19 && v6 )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v6 + 16));
  if ( v38 && v18 )
    (*v18)[1](v18);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)g_pIDimInterfaceTable + 16LL))(g_pIDimInterfaceTable);
  if ( Bundle )
  {
    if ( (byte_1800CF404 & 0x10) != 0 )
    {
      LOWORD(v52) = 0;
      LOWORD(v48) = 0;
      ConvertPortNoToString(&v48, *((unsigned int *)a3 + 24));
      FormatRRASErrorString(&v52, L"RasPortConnected: Cleaning up hPort=%d, error %d", *((_QWORD *)a3 + 12), Bundle);
      if ( (byte_1800CF404 & 0x10) != 0 )
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasDdmParamTraceInfo,
          (unsigned int)&v52,
          (unsigned int)v46,
          0,
          (__int64)&v48);
    }
    (*(void (__fastcall **)(struct DdmLegacyDevice *, _QWORD))(*(_QWORD *)a3 + 160LL))(a3, 0);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)a3 + 2, 0xFFFFFFFF) == 1 )
      (**(void (__fastcall ***)(struct DdmLegacyDevice *, __int64))a3)(a3, 1);
    if ( v35 && _InterlockedExchangeAdd((volatile signed __int32 *)v35 + 2, 0xFFFFFFFF) == 1 )
      (**(void (__fastcall ***)(DdmConnection *, __int64))v35)(v35, 1);
    return Bundle;
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)a3 + 2, 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(struct DdmLegacyDevice *, __int64))a3)(a3, 1);
  if ( v35 && _InterlockedExchangeAdd((volatile signed __int32 *)v35 + 2, 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(DdmConnection *, __int64))v35)(v35, 1);
  return 0;
}

```

## disassembly

```asm
0x18000f254  push    rbp
0x18000f256  push    rbx
0x18000f257  push    rsi
0x18000f258  push    rdi
0x18000f259  push    r12
0x18000f25b  push    r13
0x18000f25d  push    r14
0x18000f25f  push    r15
0x18000f261  lea     rbp, [rsp-1058h]
0x18000f269  mov     eax, 1158h
0x18000f26e  call    _alloca_probe
0x18000f273  sub     rsp, rax
0x18000f276  movaps  [rsp+1190h+var_50], xmm6
0x18000f27e  mov     rax, cs:__security_cookie
0x18000f285  xor     rax, rsp
0x18000f288  mov     [rbp+1090h+var_60], rax
0x18000f28f  mov     [rsp+1190h+var_1130], r9
0x18000f294  mov     rsi, r8
0x18000f297  mov     r15, rdx
0x18000f29a  mov     qword ptr [rsp+1190h+var_1138], rdx
0x18000f29f  mov     [rsp+1190h+var_1140], rcx
0x18000f2a4  xor     r12d, r12d
0x18000f2a7  mov     ebx, r12d
0x18000f2aa  mov     [rsp+1190h+var_1158], rbx
0x18000f2af  mov     [rsp+1190h+var_114C], r12d
0x18000f2b4  mov     [rsp+1190h+var_1118], r12
0x18000f2b9  mov     [rsp+1190h+var_1148], r12d
0x18000f2be  mov     [rsp+1190h+var_1160], r12d
0x18000f2c3  lea     ecx, [r12+11h]; unsigned int
0x18000f2c8  call    ?GetInstance@DdmDeviceTable@@SAPEAV1@K@Z; DdmDeviceTable::GetInstance(ulong)
0x18000f2cd  mov     r14d, [rax]
0x18000f2d0  mov     [rsp+1190h+var_1128], rsi
0x18000f2d5  test    rsi, rsi
0x18000f2d8  jz      short loc_18000F2E3
0x18000f2da  lock inc dword ptr [rsi+8]
0x18000f2de  mov     rbx, [rsp+1190h+var_1158]
0x18000f2e3  mov     [rbp+1090h+var_860], r12d
0x18000f2ea  xor     edx, edx; Val
0x18000f2ec  mov     r8d, 7FCh; Size
0x18000f2f2  lea     rcx, [rbp+1090h+var_85C]; void *
0x18000f2f9  call    memset_0
0x18000f2fe  mov     [rbp+1090h+var_890], r12d
0x18000f305  xorps   xmm0, xmm0
0x18000f308  xor     eax, eax
0x18000f30a  movups  [rbp+1090h+var_88C], xmm0
0x18000f311  movups  [rbp+1090h+var_87C], xmm0
0x18000f318  mov     [rbp+1090h+var_86C], eax
0x18000f31e  movups  [rbp+1090h+var_1108], xmm0
0x18000f322  or      r13d, 0FFFFFFFFh
0x18000f326  test    cs:byte_1800CF404, 10h
0x18000f32d  jz      short loc_18000F3AE
0x18000f32f  mov     word ptr [rbp+1090h+var_860], r12w
0x18000f337  mov     word ptr [rbp+1090h+var_890], r12w
0x18000f33f  test    rsi, rsi
0x18000f342  jz      short loc_18000F349
0x18000f344  mov     edx, [rsi+60h]
0x18000f347  jmp     short loc_18000F34C
0x18000f349  mov     edx, r13d
0x18000f34c  lea     rcx, [rbp+1090h+var_890]
0x18000f353  call    ConvertPortNoToString
0x18000f358  mov     r9d, [rsi+84h]
0x18000f35f  mov     r8, [rsi+60h]
0x18000f363  lea     rdx, aRegisteringFor; "Registering for disconnect notification"...
0x18000f36a  lea     rcx, [rbp+1090h+var_860]
0x18000f371  call    FormatRRASErrorString
0x18000f376  test    cs:byte_1800CF404, 10h
0x18000f37d  jz      short loc_18000F3AE
0x18000f37f  lea     rax, [rbp+1090h+var_890]
0x18000f386  mov     [rsp+1190h+var_1168], rax
0x18000f38b  mov     [rsp+1190h+var_1170], r12
0x18000f390  lea     r9, [rbp+1090h+var_1108]
0x18000f394  lea     r8, [rbp+1090h+var_860]
0x18000f39b  lea     rdx, RasDdmParamTraceInfo
0x18000f3a2  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000f3a9  call    McTemplateU0zjzz_EventWriteTransfer
0x18000f3ae  mov     rdi, cs:gblSupervisorEvents
0x18000f3b5  mov     ecx, 11h; unsigned int
0x18000f3ba  call    ?GetInstance@DdmDeviceTable@@SAPEAV1@K@Z; DdmDeviceTable::GetInstance(ulong)
0x18000f3bf  mov     rcx, rax
0x18000f3c2  xor     edx, edx
0x18000f3c4  mov     eax, [rsi+60h]
0x18000f3c7  div     dword ptr [rcx]
0x18000f3c9  add     r14d, 3
0x18000f3cd  lea     eax, [rdx+r14*2]
0x18000f3d1  mov     r8d, 2; DWORD
0x18000f3d7  mov     rdx, [rdi+rax*8]; HANDLE
0x18000f3db  mov     rcx, r15; HRASCONN
0x18000f3de  call    cs:__imp_RasConnectionNotificationW
0x18000f3e5  nop     dword ptr [rax+rax+00h]
0x18000f3ea  mov     r14d, eax
0x18000f3ed  test    eax, eax
0x18000f3ef  jz      loc_18000F495
0x18000f3f5  test    cs:byte_1800CF404, 10h
0x18000f3fc  jz      short loc_18000F46C
0x18000f3fe  mov     word ptr [rbp+1090h+var_860], r12w
0x18000f406  mov     word ptr [rbp+1090h+var_890], r12w
0x18000f40e  mov     edx, [rsi+60h]
0x18000f411  lea     rcx, [rbp+1090h+var_890]
0x18000f418  call    ConvertPortNoToString
0x18000f41d  mov     r8d, r14d
0x18000f420  lea     rdx, aRasconnectionn; "RasConnectionNotification returned %d"
0x18000f427  lea     rcx, [rbp+1090h+var_860]
0x18000f42e  call    FormatRRASErrorString
0x18000f433  test    cs:byte_1800CF404, 10h
0x18000f43a  jz      short loc_18000F46C
0x18000f43c  lea     rax, [rbp+1090h+var_890]
0x18000f443  mov     [rsp+1190h+var_1168], rax
0x18000f448  mov     [rsp+1190h+var_1170], r12
0x18000f44d  lea     r9, [rbp+1090h+var_1108]
0x18000f451  lea     r8, [rbp+1090h+var_860]
0x18000f458  lea     rdx, RasDdmParamTraceInfo
0x18000f45f  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000f466  call    McTemplateU0zjzz_EventWriteTransfer
0x18000f46b  nop
0x18000f46c  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000f470  mov     eax, edi
0x18000f472  lock xadd [rsi+8], eax
0x18000f477  add     eax, edi
0x18000f479  jnz     short loc_18000F48D
0x18000f47b  mov     rax, [rsi]
0x18000f47e  lea     edx, [rdi+2]
0x18000f481  mov     rcx, rsi
0x18000f484  mov     rax, [rax]
0x18000f487  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f48c  nop
0x18000f48d  mov     eax, r14d
0x18000f490  jmp     loc_18000FEB4
0x18000f495  lea     r12, [rsi+78h]
0x18000f499  mov     r8, r12
0x18000f49c  mov     rdx, [rsi+60h]
0x18000f4a0  xor     ecx, ecx
0x18000f4a2  call    cs:__imp_RasPortGetBundle
0x18000f4a9  nop     dword ptr [rax+rax+00h]
0x18000f4ae  mov     r14d, eax
0x18000f4b1  xor     edi, edi
0x18000f4b3  test    eax, eax
0x18000f4b5  jz      short loc_18000F516
0x18000f4b7  test    cs:byte_1800CF404, 10h
0x18000f4be  jz      short loc_18000F46C
0x18000f4c0  mov     word ptr [rbp+1090h+var_860], di
0x18000f4c7  mov     word ptr [rbp+1090h+var_890], di
0x18000f4ce  mov     edx, [rsi+60h]
0x18000f4d1  lea     rcx, [rbp+1090h+var_890]
0x18000f4d8  call    ConvertPortNoToString
0x18000f4dd  lea     rdx, aRasportgetbund; "RasPortGetBundle returned %d"
0x18000f4e4  mov     r8d, r14d
0x18000f4e7  lea     rcx, [rbp+1090h+var_860]
0x18000f4ee  call    FormatRRASErrorString
0x18000f4f3  test    cs:byte_1800CF404, 10h
0x18000f4fa  jz      loc_18000F46C
0x18000f500  lea     rax, [rbp+1090h+var_890]
0x18000f507  mov     [rsp+1190h+var_1168], rax
0x18000f50c  mov     [rsp+1190h+var_1170], rdi
0x18000f511  jmp     loc_18000F44D
0x18000f516  mov     ecx, 11h; unsigned int
0x18000f51b  call    ?GetInstance@DdmDeviceTable@@SAPEAV1@K@Z; DdmDeviceTable::GetInstance(ulong)
0x18000f520  lea     rdx, [rsp+1190h+var_1128]
0x18000f525  mov     rcx, rax; this
0x18000f528  call    ?UpdateDeviceBundleMap@DdmDeviceTable@@QEAAKAEAV?$RasObjPtr@VDdmDevice@@@@@Z; DdmDeviceTable::UpdateDeviceBundleMap(RasObjPtr<DdmDevice> &)
0x18000f52d  mov     r14d, eax
0x18000f530  test    eax, eax
0x18000f532  jz      short loc_18000F56A
0x18000f534  test    cs:byte_1800CF404, 10h
0x18000f53b  jz      loc_18000F46C
0x18000f541  mov     word ptr [rbp+1090h+var_860], di
0x18000f548  mov     word ptr [rbp+1090h+var_890], di
0x18000f54f  mov     edx, [rsi+60h]
0x18000f552  lea     rcx, [rbp+1090h+var_890]
0x18000f559  call    ConvertPortNoToString
0x18000f55e  lea     rdx, aUpdatedevicebu; "UpdateDeviceBundleMap returned %d"
0x18000f565  jmp     loc_18000F4E4
0x18000f56a  mov     rcx, cs:g_pIDimInterfaceTable
0x18000f571  mov     rax, [rcx]
0x18000f574  mov     rax, [rax]
0x18000f577  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f57c  mov     rcx, cs:g_pIDimInterfaceTable
0x18000f583  mov     rax, [rcx]
0x18000f586  mov     r14, [rsp+1190h+var_1130]
0x18000f58b  mov     rdx, r14
0x18000f58e  mov     rax, [rax+40h]
0x18000f592  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f597  mov     r15, rax
0x18000f59a  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000f59e  test    rax, rax
0x18000f5a1  jnz     short loc_18000F5B1
0x18000f5a3  mov     r14d, 389h
0x18000f5a9  xor     r13d, r13d
0x18000f5ac  jmp     loc_18000FD0B
0x18000f5b1  mov     rax, [rax]
0x18000f5b4  mov     rcx, r15
0x18000f5b7  mov     rax, [rax]
0x18000f5ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f5bf  mov     [rsp+1190h+var_1148], 1
0x18000f5c7  mov     rax, [r15]
0x18000f5ca  mov     rcx, r15
0x18000f5cd  mov     rax, [rax+38h]
0x18000f5d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f5d6  test    al, al
0x18000f5d8  jz      short loc_18000F647
0x18000f5da  mov     r14d, 26Bh
0x18000f5e0  xor     r13d, r13d
0x18000f5e3  test    cs:byte_1800CF404, 10h
0x18000f5ea  jz      loc_18000FD0B
0x18000f5f0  mov     word ptr [rbp+1090h+var_890], r13w
0x18000f5f8  mov     edx, [rsi+60h]
0x18000f5fb  lea     rcx, [rbp+1090h+var_890]
0x18000f602  call    ConvertPortNoToString
0x18000f607  test    cs:byte_1800CF404, 10h
0x18000f60e  jz      short loc_18000F63F
0x18000f610  lea     rax, [rbp+1090h+var_890]
0x18000f617  mov     [rsp+1190h+var_1168], rax
0x18000f61c  mov     [rsp+1190h+var_1170], r13
0x18000f621  lea     r9, [rbp+1090h+var_1108]
0x18000f625  lea     r8, aRasportconnect_1; "RasPortConnected: Admin disconnected po"...
0x18000f62c  lea     rdx, RasDdmParamTraceInfo
0x18000f633  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000f63a  call    McTemplateU0zjzz_EventWriteTransfer
0x18000f63f  mov     r12d, r13d
0x18000f642  jmp     loc_18000FD10
0x18000f647  call    ?GetInstance@DdmConnectionTable@@SAPEAV1@XZ; DdmConnectionTable::GetInstance(void)
0x18000f64c  lea     r8, [rsp+1190h+var_1158]
0x18000f651  mov     rdx, [r12]
0x18000f655  mov     rcx, rax
0x18000f658  call    ?FindConnection@DdmConnectionTable@@QEAAXPEAXAEAV?$RasObjPtr@VDdmConnection@@@@@Z; DdmConnectionTable::FindConnection(void *,RasObjPtr<DdmConnection> &)
0x18000f65d  mov     rbx, [rsp+1190h+var_1158]
0x18000f662  test    rbx, rbx
0x18000f665  jnz     loc_18000FA19
0x18000f66b  mov     [rsp+1190h+var_1150], ebx
0x18000f66f  xorps   xmm6, xmm6
0x18000f672  movups  [rbp+1090h+var_10F8], xmm6
0x18000f676  mov     ecx, 5E0h; Size
0x18000f67b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f680  mov     [rbp+1090h+var_1110], rax
0x18000f684  test    rax, rax
0x18000f687  jz      short loc_18000F69A
0x18000f689  mov     r8, [r12]; void *
0x18000f68d  mov     rdx, r14; void *
0x18000f690  mov     rcx, rax; this
0x18000f693  call    ??0DdmConnection@@QEAA@PEAX0@Z; DdmConnection::DdmConnection(void *,void *)
0x18000f698  jmp     short loc_18000F69D
0x18000f69a  mov     rax, rbx
0x18000f69d  mov     rdx, rax
0x18000f6a0  lea     rcx, [rsp+1190h+var_1158]
0x18000f6a5  call    ?reset@?$RasObjPtr@VDdmDevice@@@@QEAAXPEAVDdmDevice@@@Z; RasObjPtr<DdmDevice>::reset(DdmDevice *)
0x18000f6aa  mov     rbx, [rsp+1190h+var_1158]
0x18000f6af  test    rbx, rbx
0x18000f6b2  jnz     short loc_18000F71A
0x18000f6b4  xor     r13d, r13d
0x18000f6b7  test    cs:byte_1800CF404, 8
0x18000f6be  jz      short loc_18000F70F
0x18000f6c0  mov     word ptr [rbp+1090h+var_890], r13w
0x18000f6c8  mov     edx, [rsi+60h]
0x18000f6cb  lea     rcx, [rbp+1090h+var_890]
0x18000f6d2  call    ConvertPortNoToString
0x18000f6d7  test    cs:byte_1800CF404, 8
0x18000f6de  jz      short loc_18000F70F
0x18000f6e0  lea     rax, [rbp+1090h+var_890]
0x18000f6e7  mov     [rsp+1190h+var_1168], rax
0x18000f6ec  mov     [rsp+1190h+var_1170], r13
0x18000f6f1  lea     r9, [rbp+1090h+var_1108]
0x18000f6f5  lea     r8, aConnobjAllocat; "ConnObj Allocation failed"
0x18000f6fc  lea     rdx, RasDdmParamTraceError
0x18000f703  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000f70a  call    McTemplateU0zjzz_EventWriteTransfer
0x18000f70f  mov     r14d, 8
0x18000f715  jmp     loc_18000FD0B
0x18000f71a  movq    rax, xmm6
0x18000f71f  cmp     rax, [rsi+434h]
0x18000f726  jnz     short loc_18000F73B
0x18000f728  psrldq  xmm6, 8
0x18000f72d  movq    rax, xmm6
0x18000f732  cmp     rax, [rsi+43Ch]
0x18000f739  jz      short loc_18000F74A
0x18000f73b  movups  xmm0, xmmword ptr [rsi+434h]
0x18000f742  movdqu  xmmword ptr [rbx+94h], xmm0
0x18000f74a  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000f74e  call    cs:__imp_EnterCriticalSection
0x18000f755  nop     dword ptr [rax+rax+00h]
0x18000f75a  mov     r14d, 1
0x18000f760  mov     r12d, r14d
0x18000f763  mov     [rsp+1190h+var_1160], r14d
0x18000f768  call    ?GetInstance@DdmConnectionTable@@SAPEAV1@XZ; DdmConnectionTable::GetInstance(void)
0x18000f76d  lea     rdx, [rsp+1190h+var_1158]
0x18000f772  mov     rcx, rax; this
0x18000f775  call    ?AddConnection@DdmConnectionTable@@QEAAXAEAV?$RasObjPtr@VDdmConnection@@@@@Z; DdmConnectionTable::AddConnection(RasObjPtr<DdmConnection> &)
0x18000f77a  mov     [rsp+1190h+var_1150], 0E0h
0x18000f782  lea     r8, [rbx+4D8h]
0x18000f789  lea     r9, [rsp+1190h+var_1150]
0x18000f78e  mov     edx, r14d
0x18000f791  mov     rcx, [rsp+1190h+var_1140]
0x18000f796  call    cs:__imp_RasGetConnectionUserData
0x18000f79d  nop     dword ptr [rax+rax+00h]
0x18000f7a2  mov     r14d, eax
0x18000f7a5  xor     eax, eax
0x18000f7a7  test    r14d, r14d
0x18000f7aa  jz      loc_18000F869
0x18000f7b0  test    cs:byte_1800CF404, 8
0x18000f7b7  jz      loc_18000F84E
0x18000f7bd  mov     word ptr [rbp+1090h+var_860], ax
0x18000f7c4  mov     word ptr [rbp+1090h+var_890], ax
  ... truncated ...
```
