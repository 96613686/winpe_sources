# DdmNotificationHandler::DriverNotificationHandler(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x180046270`
- end: `0x180046d65`
- name: `?DriverNotificationHandler@DdmNotificationHandler@@CAKPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `2805`
- prototype: `unsigned int __fastcall(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WORK *)`
- caller_count: `0`
- callee_count: `19`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180007b7c`
- `0x180007c50`
- `0x180007dcc`
- `0x180025a9c`
- `0x180025f64`
- `0x1800261a4`
- `0x18003ab88`
- `0x18003acec`
- `0x18003b444`
- `0x18003b7a8`
- `0x18003b8f4`
- `0x18003bd08`
- `0x18003c594`
- `0x180046270`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008c6f0`
- `0x18008e010`

## import_xrefs

- `msvcrt!_itow_s` at `0x180046393`
- `msvcrt!_itow_s` at `0x180046507`
- `msvcrt!_itow_s` at `0x180046851`
- `msvcrt!_itow_s` at `0x180046a85`
- `msvcrt!_itow_s` at `0x180046b1a`
- `msvcrt!_itow_s` at `0x180046be8`
- `msvcrt!_itow_s` at `0x180046393`
- `msvcrt!_itow_s` at `0x180046507`
- `msvcrt!_itow_s` at `0x180046851`
- `msvcrt!_itow_s` at `0x180046a85`
- `msvcrt!_itow_s` at `0x180046b1a`
- `msvcrt!_itow_s` at `0x180046be8`
- `KERNEL32!LocalFree` at `0x180046582`
- `KERNEL32!LocalFree` at `0x180046582`
- `KERNEL32!LeaveCriticalSection` at `0x1800465db`
- `KERNEL32!LeaveCriticalSection` at `0x180046774`
- `KERNEL32!LeaveCriticalSection` at `0x1800468a9`
- `KERNEL32!LeaveCriticalSection` at `0x180046ab2`
- `KERNEL32!LeaveCriticalSection` at `0x180046b9e`
- `KERNEL32!LeaveCriticalSection` at `0x180046cb3`
- `KERNEL32!LeaveCriticalSection` at `0x1800465db`
- `KERNEL32!LeaveCriticalSection` at `0x180046774`
- `KERNEL32!LeaveCriticalSection` at `0x1800468a9`
- `KERNEL32!LeaveCriticalSection` at `0x180046ab2`
- `KERNEL32!LeaveCriticalSection` at `0x180046b9e`
- `KERNEL32!LeaveCriticalSection` at `0x180046cb3`
- `KERNEL32!EnterCriticalSection` at `0x1800465ba`
- `KERNEL32!EnterCriticalSection` at `0x1800465ea`
- `KERNEL32!EnterCriticalSection` at `0x18004662e`
- `KERNEL32!EnterCriticalSection` at `0x18004669e`
- `KERNEL32!EnterCriticalSection` at `0x180046797`
- `KERNEL32!EnterCriticalSection` at `0x1800467f8`
- `KERNEL32!EnterCriticalSection` at `0x1800469d0`
- `KERNEL32!EnterCriticalSection` at `0x180046b80`
- `KERNEL32!EnterCriticalSection` at `0x180046c98`
- `KERNEL32!EnterCriticalSection` at `0x1800465ba`
- `KERNEL32!EnterCriticalSection` at `0x1800465ea`
- `KERNEL32!EnterCriticalSection` at `0x18004662e`
- `KERNEL32!EnterCriticalSection` at `0x18004669e`
- `KERNEL32!EnterCriticalSection` at `0x180046797`
- `KERNEL32!EnterCriticalSection` at `0x1800467f8`
- `KERNEL32!EnterCriticalSection` at `0x1800469d0`
- `KERNEL32!EnterCriticalSection` at `0x180046b80`
- `KERNEL32!EnterCriticalSection` at `0x180046c98`
- `KERNEL32!HeapFree` at `0x180046cfc`
- `KERNEL32!HeapFree` at `0x180046d0e`
- `KERNEL32!HeapFree` at `0x180046cfc`
- `KERNEL32!HeapFree` at `0x180046d0e`

## string_xrefs

- `0x1800466e3`: `%s:MarkPortConnectComplete failed: %d`
- `0x180046bf8`: `%s:MarkPortConnectComplete failed: %d`
- `0x18004691f`: `Failed to create device object: %d`
- `0x180046a8b`: `DdmAcceptIncomingCall failed for port: %ld`
- `0x180046857`: `DdmAnswerIncomingCall failed for port: %ld`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DdmNotificationHandler::DriverNotificationHandler(
        struct _TP_CALLBACK_INSTANCE *a1,
        unsigned int *a2,
        struct _TP_WORK *a3)
{
  unsigned int v4; // r14d
  __int64 v5; // rdi
  __int64 v6; // r8
  int v7; // ecx
  unsigned int v8; // r15d
  __int64 i; // rbx
  int v10; // ecx
  struct DdmDeviceTable *v11; // rax
  struct _RTL_CRITICAL_SECTION *v12; // rcx
  struct DdmDeviceTable *v13; // rax
  struct DdmDeviceTable *v14; // rax
  struct DdmDeviceTable *v15; // rax
  unsigned int v16; // eax
  __int64 v17; // r8
  __int64 v18; // rax
  DdmDeviceTable *v19; // rax
  DWORD v20; // ecx
  struct DdmDeviceTable *v21; // rax
  __int64 v22; // rbx
  int v23; // ecx
  DdmDeviceTable *v24; // rax
  struct DdmDeviceTable *v25; // rax
  unsigned int v26; // eax
  __int64 v27; // r8
  __int64 v28; // rax
  DdmDeviceTable *v29; // rax
  DdmDeviceTable *v30; // rax
  __int64 v31; // rbx
  int v32; // ecx
  struct DdmDeviceTable *Instance; // rax
  int v34; // ecx
  int v35; // ecx
  DdmDeviceTable *v36; // rax
  DWORD v37; // ecx
  struct DdmDeviceTable *v38; // rax
  struct DdmDeviceTable *v39; // rax
  __int64 v41; // [rsp+28h] [rbp-D8h]
  __int64 v42; // [rsp+30h] [rbp-D0h] BYREF
  int v43; // [rsp+38h] [rbp-C8h]
  __int128 v44; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v45; // [rsp+50h] [rbp-B0h]
  _QWORD v46[2]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v47[8]; // [rsp+70h] [rbp-90h] BYREF
  __int16 v48; // [rsp+78h] [rbp-88h]
  int v49; // [rsp+7Ch] [rbp-84h]
  __int128 v50; // [rsp+1C40h] [rbp+1B40h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v51; // [rsp+1C50h] [rbp+1B50h] BYREF
  const wchar_t *v52; // [rsp+1C60h] [rbp+1B60h]
  __int64 v53; // [rsp+1C68h] [rbp+1B68h]
  wchar_t Buffer[2]; // [rsp+1C70h] [rbp+1B70h] BYREF
  __int128 v55; // [rsp+1C74h] [rbp+1B74h]
  __int128 v56; // [rsp+1C84h] [rbp+1B84h]
  int v57; // [rsp+1C94h] [rbp+1B94h]
  int v58; // [rsp+1CA0h] [rbp+1BA0h] BYREF
  _BYTE v59[2044]; // [rsp+1CA4h] [rbp+1BA4h] BYREF

  v4 = 0;
  v5 = 0;
  v42 = 0;
  v58 = 0;
  memset_0(v59, 0, sizeof(v59));
  *(_DWORD *)Buffer = 0;
  v55 = 0;
  v56 = 0;
  v57 = 0;
  v50 = 0;
  if ( !a2 )
  {
    if ( (byte_1800C8404 & 0x10) != 0 )
    {
      v52 = L"Invalid Parameter";
      v53 = 36;
      McGenEventWrite_EventWriteTransfer(
        (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (const EVENT_DESCRIPTOR *)RasDdmTraceInfo,
        v6,
        2u,
        &v51);
    }
    goto LABEL_101;
  }
  msgdbgprint(1, 2, a2);
  if ( (byte_1800C8404 & 0x10) != 0 )
  {
    LOWORD(v58) = 0;
    Buffer[0] = 0;
    v7 = a2[2];
    if ( v7 != -1 )
      _itow_s(v7, Buffer, 0x14u, 10);
    FormatRRASErrorString(
      &v58,
      L"Processing Message (Id:%d) for hPort=%I64u, hCall=%I64u",
      *a2,
      *((_QWORD *)a2 + 1),
      *((_QWORD *)a2 + 2));
    if ( (byte_1800C8404 & 0x10) != 0 )
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceInfo,
        (unsigned int)&v58,
        (unsigned int)&v50,
        0,
        (__int64)Buffer);
  }
  if ( *a2 == 1 )
  {
    Instance = DdmDeviceTable::GetInstance(0x11u);
    DdmDeviceTable::FindDevice(Instance, *((_QWORD *)a2 + 1), &v42);
    v5 = v42;
    if ( v42 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(v42 + 16));
      v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 448LL))(v5);
      LeaveCriticalSection((LPCRITICAL_SECTION)(v5 + 16));
      if ( v4 )
      {
        if ( (byte_1800C8404 & 8) != 0 )
        {
          LOWORD(v58) = 0;
          Buffer[0] = 0;
          if ( v5 )
          {
            v35 = *(_DWORD *)(v5 + 96);
            if ( v35 != -1 )
              _itow_s(v35, Buffer, 0x14u, 10);
          }
          FormatRRASErrorString(
            &v58,
            L"%s:MarkPortConnectComplete failed: %d",
            L"DdmNotificationHandler::DriverNotificationHandler",
            v4);
          if ( (byte_1800C8404 & 8) != 0 )
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasDdmParamTraceError,
              (unsigned int)&v58,
              (unsigned int)&v50,
              0,
              (__int64)Buffer);
        }
      }
      else
      {
        v43 = 0;
        v36 = DdmDeviceTable::GetInstance(0x11u);
        DdmDeviceTable::UpdateDeviceBundleMap(v36);
        ExecuteComponentTest(v37);
        if ( *(_WORD *)(v5 + 136) == 15 )
        {
          v38 = DdmDeviceTable::GetInstance(0x11u);
          (**((void (__fastcall ***)(__int64))v38 + 20))((__int64)v38 + 160);
          v43 = 1;
        }
        EnterCriticalSection((LPCRITICAL_SECTION)(v5 + 16));
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 344LL))(v5);
        LeaveCriticalSection((LPCRITICAL_SECTION)(v5 + 16));
        if ( v43 )
        {
          v39 = DdmDeviceTable::GetInstance(0x11u);
          (*(void (__fastcall **)(__int64))(*((_QWORD *)v39 + 20) + 16LL))((__int64)v39 + 160);
        }
      }
      goto LABEL_26;
    }
    goto LABEL_80;
  }
  if ( *a2 != 2 )
  {
    if ( *a2 != 3 )
    {
      switch ( *a2 )
      {
        case 4u:
          v15 = DdmDeviceTable::GetInstance(0x11u);
          DdmDeviceTable::FindDevice(v15, *((_QWORD *)a2 + 1), &v42);
          v5 = v42;
          if ( v42 )
          {
            EnterCriticalSection((LPCRITICAL_SECTION)(v42 + 16));
            v16 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 448LL))(v5);
            v4 = v16;
            if ( v16 )
            {
              if ( (byte_1800C8404 & 8) != 0 )
              {
                LOWORD(v58) = 0;
                FormatRRASErrorString(
                  &v58,
                  L"%s:MarkPortConnectComplete failed: %d",
                  L"DdmNotificationHandler::DriverNotificationHandler",
                  v16);
                if ( (byte_1800C8404 & 8) != 0 )
                {
                  v18 = -1;
                  do
                    ++v18;
                  while ( *(_WORD *)&v59[2 * v18 - 4] );
                  v52 = (const wchar_t *)&v58;
                  v53 = (unsigned int)(2 * v18 + 2);
                  McGenEventWrite_EventWriteTransfer(
                    (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                    (const EVENT_DESCRIPTOR *)RasDdmTraceError,
                    v17,
                    2u,
                    &v51);
                }
              }
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 176LL))(v5);
            }
            else
            {
              LeaveCriticalSection((LPCRITICAL_SECTION)(v5 + 16));
              v19 = DdmDeviceTable::GetInstance(0x11u);
              DdmDeviceTable::UpdateDeviceBundleMap(v19);
              ExecuteComponentTest(v20);
              EnterCriticalSection((LPCRITICAL_SECTION)(v5 + 16));
              v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 88LL))(v5);
              if ( !v4 )
                v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 96LL))(v5);
            }
            v12 = (struct _RTL_CRITICAL_SECTION *)(v5 + 16);
            goto LABEL_37;
          }
          break;
        case 5u:
          goto LABEL_41;
        case 6u:
          v13 = DdmDeviceTable::GetInstance(0x11u);
          DdmDeviceTable::FindDevice(v13, *((_QWORD *)a2 + 1), &v42);
          v5 = v42;
          if ( v42 )
          {
            EnterCriticalSection((LPCRITICAL_SECTION)(v42 + 16));
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 360LL))(v5);
            goto LABEL_36;
          }
          break;
        case 7u:
LABEL_41:
          v14 = DdmDeviceTable::GetInstance(0x11u);
          DdmDeviceTable::FindDevice(v14, *((_QWORD *)a2 + 1), &v42);
          v5 = v42;
          if ( v42 )
          {
            EnterCriticalSection((LPCRITICAL_SECTION)(v42 + 16));
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 104LL))(v5);
            goto LABEL_36;
          }
          break;
        case 8u:
          v11 = DdmDeviceTable::GetInstance(0x11u);
          DdmDeviceTable::FindDevice(v11, *((_QWORD *)a2 + 1), &v42);
          v5 = v42;
          if ( v42 )
          {
            EnterCriticalSection((LPCRITICAL_SECTION)(v42 + 16));
            (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v5 + 120LL))(v5, *((_QWORD *)a2 + 4), a2[6]);
LABEL_36:
            v12 = (struct _RTL_CRITICAL_SECTION *)(v5 + 16);
LABEL_37:
            LeaveCriticalSection(v12);
            goto LABEL_26;
          }
          break;
        case 9u:
          v8 = 0;
          if ( !a2[6] )
            goto LABEL_26;
          v4 = 0;
          do
          {
            v46[0] = 14;
            v46[1] = 0;
            memset_0(v47, 0, 0x1BD0u);
            v48 = a2[2 * v8 + 7];
            v49 = (a2[2 * v8 + 8] != 1) + 1;
            for ( i = 0; i != 3; ++i )
            {
              if ( HIDWORD(protocolEngineParams[10 * i + 3]) == 1 )
                ((void (__fastcall *)(_QWORD *))protocolEngineParams[10 * i + 9])(v46);
            }
            ++v8;
          }
          while ( v8 < a2[6] );
          goto LABEL_25;
        default:
          goto LABEL_26;
      }
LABEL_80:
      if ( (byte_1800C8404 & 0x10) != 0 )
      {
        v34 = a2[2];
        LOWORD(v58) = 0;
        Buffer[0] = 0;
        if ( v34 != -1 )
          _itow_s(v34, Buffer, 0x14u, 10);
        FormatRRASErrorString(&v58, L"No device found for port: %ld", *((_QWORD *)a2 + 1));
        if ( (byte_1800C8404 & 0x10) != 0 )
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasDdmParamTraceInfo,
            (unsigned int)&v58,
            (unsigned int)&v50,
            0,
            (__int64)Buffer);
      }
      v4 = 1168;
      goto LABEL_26;
    }
    v21 = DdmDeviceTable::GetInstance(0x11u);
    DdmDeviceTable::FindDevice(v21, *((_QWORD *)a2 + 1), &v42);
    v5 = v42;
    if ( !v42 )
      goto LABEL_80;
    EnterCriticalSection((LPCRITICAL_SECTION)(v42 + 16));
    v4 = DdmAnswerIncomingCall(&v42);
    if ( v4 )
    {
      v22 = v42;
      if ( (byte_1800C8404 & 8) != 0 )
      {
        LOWORD(v58) = 0;
        Buffer[0] = 0;
        if ( v42 )
        {
          v23 = *(_DWORD *)(v42 + 96);
          if ( v23 != -1 )
            _itow_s(v23, Buffer, 0x14u, 10);
        }
        FormatRRASErrorString(&v58, L"DdmAnswerIncomingCall failed for port: %ld", *(_QWORD *)(v22 + 96));
LABEL_61:
        if ( (byte_1800C8404 & 8) != 0 )
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasDdmParamTraceError,
            (unsigned int)&v58,
            (unsigned int)&v50,
            0,
            (__int64)Buffer);
        goto LABEL_63;
      }
      goto LABEL_63;
    }
    v5 = v42;
LABEL_78:
    LeaveCriticalSection((LPCRITICAL_SECTION)(v5 + 16));
    goto LABEL_26;
  }
  v25 = DdmDeviceTable::GetInstance(0x11u);
  v26 = DdmDeviceTable::CreateNewDevice(v25, a2[6], &v42, 0);
  v4 = v26;
  v5 = v42;
  if ( !v42 )
  {
    if ( (byte_1800C8404 & 8) != 0 )
    {
      LOWORD(v58) = 0;
      FormatRRASErrorString(&v58, L"Failed to create device object: %d", v26);
      if ( (byte_1800C8404 & 8) != 0 )
      {
        v28 = -1;
        do
          ++v28;
        while ( *(_WORD *)&v59[2 * v28 - 4] );
        v52 = (const wchar_t *)&v58;
        v53 = (unsigned int)(2 * v28 + 2);
        McGenEventWrite_EventWriteTransfer(
          (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (const EVENT_DESCRIPTOR *)RasDdmTraceError,
          v27,
          2u,
          &v51);
      }
    }
    goto LABEL_26;
  }
  v29 = DdmDeviceTable::GetInstance(0x11u);
  DdmDeviceTable::AddDevice(v29);
  v30 = DdmDeviceTable::GetInstance(0x11u);
  DdmDeviceTable::AddDeviceCallMap(v30);
  v31 = v42;
  EnterCriticalSection((LPCRITICAL_SECTION)(v42 + 16));
  (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v31 + 248LL))(v31, a2[7], *((_QWORD *)a2 + 4));
  v44 = *(_OWORD *)(a2 + 15);
  v45 = a2[19];
  v51 = *(struct _EVENT_DATA_DESCRIPTOR *)(a2 + 10);
  LODWORD(v52) = a2[14];
  (*(void (__fastcall **)(__int64, struct _EVENT_DATA_DESCRIPTOR *, __int128 *))(*(_QWORD *)v31 + 528LL))(
    v31,
    &v51,
    &v44);
  v4 = DdmAcceptIncomingCall(&v42, a2[4]);
  if ( !v4 )
  {
    v5 = v42;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 352LL))(v42);
    goto LABEL_78;
  }
  v22 = v42;
  if ( (byte_1800C8404 & 8) != 0 )
  {
    LOWORD(v58) = 0;
    Buffer[0] = 0;
    if ( v42 )
    {
      v32 = *(_DWORD *)(v42 + 96);
      if ( v32 != -1 )
        _itow_s(v32, Buffer, 0x14u, 10);
    }
    FormatRRASErrorString(&v58, L"DdmAcceptIncomingCall failed for port: %ld", *(_QWORD *)(v22 + 96));
    goto LABEL_61;
  }
LABEL_63:
  LeaveCriticalSection((LPCRITICAL_SECTION)(v22 + 16));
  v24 = DdmDeviceTable::GetInstance(0x11u);
  DdmDeviceTable::RemoveDevice(v24);
LABEL_25:
  v5 = v42;
LABEL_26:
  if ( (byte_1800C8404 & 0x10) != 0 )
  {
    LOWORD(v58) = 0;
    Buffer[0] = 0;
    v10 = a2[2];
    if ( v10 != -1 )
      _itow_s(v10, Buffer, 0x14u, 10);
    LODWORD(v41) = v4;
    FormatRRASErrorString(
      &v58,
      L"Processing Done for Message (Id:%d) for hPort=%I64u, hCall=%I64u. Error: %d",
      *a2,
      *((_QWORD *)a2 + 1),
      *((_QWORD *)a2 + 2),
      v41);
    if ( (byte_1800C8404 & 0x10) != 0 )
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceInfo,
        (unsigned int)&v58,
        (unsigned int)&v50,
        0,
        (__int64)Buffer);
  }
  if ( *a2 == 8 )
  {
    if ( a2[6] )
      LocalFree(*((HLOCAL *)a2 + 4));
  }
  else if ( *a2 == 2 && a2[7] )
  {
    HeapFree(hHeap, 0, *((LPVOID *)a2 + 4));
  }
  HeapFree(hHeap, 0, a2);
LABEL_101:
  if ( v5 && _InterlockedExchangeAdd((volatile signed __int32 *)(v5 + 8), 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(__int64, __int64))v5)(v5, 1);
  return v4;
}

```

## disassembly

```asm
0x180046270  push    rbp
0x180046272  push    rbx
0x180046273  push    rsi
0x180046274  push    rdi
0x180046275  push    r12
0x180046277  push    r13
0x180046279  push    r14
0x18004627b  push    r15
0x18004627d  lea     rbp, [rsp-23B8h]
0x180046285  mov     eax, 24B8h
0x18004628a  call    _alloca_probe
0x18004628f  sub     rsp, rax
0x180046292  mov     rax, cs:__security_cookie
0x180046299  xor     rax, rsp
0x18004629c  mov     [rbp+23F0h+var_50], rax
0x1800462a3  mov     rsi, rdx
0x1800462a6  xor     ebx, ebx
0x1800462a8  mov     r14d, ebx
0x1800462ab  mov     edi, ebx
0x1800462ad  mov     [rsp+24F0h+var_24C0], rbx
0x1800462b2  mov     [rbp+23F0h+var_850], ebx
0x1800462b8  xor     edx, edx; Val
0x1800462ba  mov     r8d, 7FCh; Size
0x1800462c0  lea     rcx, [rbp+23F0h+var_84C]; void *
0x1800462c7  call    memset_0
0x1800462cc  mov     dword ptr [rbp+23F0h+Buffer], ebx
0x1800462d2  xorps   xmm0, xmm0
0x1800462d5  xor     eax, eax
0x1800462d7  movups  [rbp+23F0h+var_87C], xmm0
0x1800462de  movups  [rbp+23F0h+var_86C], xmm0
0x1800462e5  mov     [rbp+23F0h+var_85C], eax
0x1800462eb  movups  [rbp+23F0h+var_8B0], xmm0
0x1800462f2  test    rsi, rsi
0x1800462f5  jnz     short loc_180046345
0x1800462f7  test    cs:byte_1800C8404, 10h
0x1800462fe  jz      loc_180046D15
0x180046304  lea     rax, aInvalidParamet; "Invalid Parameter"
0x18004630b  mov     [rbp+23F0h+var_890], rax
0x180046312  mov     [rbp+23F0h+var_888], 24h ; '$'
0x18004631d  lea     rax, [rbp+23F0h+var_8A0]
0x180046324  mov     [rsp+24F0h+var_24D0], rax
0x180046329  lea     r9d, [rbx+2]
0x18004632d  lea     rdx, RasDdmTraceInfo
0x180046334  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004633b  call    McGenEventWrite_EventWriteTransfer
0x180046340  jmp     loc_180046D15
0x180046345  mov     edx, 2
0x18004634a  lea     ecx, [rdx-1]
0x18004634d  mov     r8, rsi
0x180046350  call    msgdbgprint
0x180046355  lea     r13, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004635c  mov     r12b, 10h
0x18004635f  test    cs:byte_1800C8404, r12b
0x180046366  jz      loc_1800463F3
0x18004636c  mov     word ptr [rbp+23F0h+var_850], bx
0x180046373  mov     [rbp+23F0h+Buffer], bx
0x18004637a  mov     ecx, [rsi+8]; Value
0x18004637d  cmp     ecx, 0FFFFFFFFh
0x180046380  jz      short loc_180046399
0x180046382  mov     r9d, 0Ah; Radix
0x180046388  lea     r8d, [r9+0Ah]; BufferCount
0x18004638c  lea     rdx, [rbp+23F0h+Buffer]; Buffer
0x180046393  call    cs:__imp__itow_s
0x180046399  mov     rax, [rsi+10h]
0x18004639d  mov     [rsp+24F0h+var_24D0], rax
0x1800463a2  mov     r9, [rsi+8]
0x1800463a6  mov     r8d, [rsi]
0x1800463a9  lea     rdx, aProcessingMess; "Processing Message (Id:%d) for hPort=%I"...
0x1800463b0  lea     rcx, [rbp+23F0h+var_850]
0x1800463b7  call    FormatRRASErrorString
0x1800463bc  test    cs:byte_1800C8404, r12b
0x1800463c3  jz      short loc_1800463F3
0x1800463c5  lea     rax, [rbp+23F0h+Buffer]
0x1800463cc  mov     [rsp+24F0h+var_24C8], rax
0x1800463d1  mov     [rsp+24F0h+var_24D0], rbx
0x1800463d6  lea     r9, [rbp+23F0h+var_8B0]
0x1800463dd  lea     r8, [rbp+23F0h+var_850]
0x1800463e4  lea     rdx, RasDdmParamTraceInfo
0x1800463eb  mov     rcx, r13
0x1800463ee  call    McTemplateU0zjzz_EventWriteTransfer
0x1800463f3  mov     ecx, [rsi]
0x1800463f5  sub     ecx, 1
0x1800463f8  jz      loc_180046ABD
0x1800463fe  sub     ecx, 1
0x180046401  jz      loc_1800468D6
0x180046407  sub     ecx, 1
0x18004640a  jz      loc_1800467C7
0x180046410  sub     ecx, 1
0x180046413  jz      loc_18004666A
0x180046419  sub     ecx, 1
0x18004641c  jz      loc_180046640
0x180046422  sub     ecx, 1
0x180046425  jz      loc_180046601
0x18004642b  sub     ecx, 1
0x18004642e  jz      loc_180046640
0x180046434  sub     ecx, 1
0x180046437  jz      loc_18004658D
0x18004643d  cmp     ecx, 1
0x180046440  jnz     loc_1800464D3
0x180046446  mov     r15d, ebx
0x180046449  cmp     [rsi+18h], ebx
0x18004644c  jbe     loc_1800464D3
0x180046452  xor     r14d, r14d
0x180046455  lea     rdi, protocolEngineParams
0x18004645c  mov     [rsp+24F0h+var_2490], 0Eh
0x180046465  mov     [rsp+24F0h+var_2488], r14
0x18004646a  xor     edx, edx; Val
0x18004646c  mov     r8d, 1BD0h; Size
0x180046472  lea     rcx, [rsp+24F0h+var_2480]; void *
0x180046477  call    memset_0
0x18004647c  mov     ecx, r15d
0x18004647f  movzx   eax, word ptr [rsi+rcx*8+1Ch]
0x180046484  mov     [rsp+24F0h+var_2478], ax
0x180046489  mov     eax, r14d
0x18004648c  cmp     dword ptr [rsi+rcx*8+20h], 1
0x180046491  setnz   al
0x180046494  inc     eax
0x180046496  mov     [rsp+24F0h+var_2474], eax
0x18004649a  mov     rbx, r14
0x18004649d  lea     rax, [rbx+rbx*4]
0x1800464a1  add     rax, rax
0x1800464a4  cmp     dword ptr [rdi+rax*8+1Ch], 1
0x1800464a9  jnz     short loc_1800464BA
0x1800464ab  lea     rcx, [rsp+24F0h+var_2490]
0x1800464b0  mov     rax, [rdi+rax*8+48h]
0x1800464b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800464ba  inc     rbx
0x1800464bd  cmp     rbx, 3
0x1800464c1  jnz     short loc_18004649D
0x1800464c3  inc     r15d
0x1800464c6  cmp     r15d, [rsi+18h]
0x1800464ca  jb      short loc_18004645C
0x1800464cc  mov     rdi, [rsp+24F0h+var_24C0]
0x1800464d1  xor     ebx, ebx
0x1800464d3  test    cs:byte_1800C8404, r12b
0x1800464da  jz      loc_18004656C
0x1800464e0  mov     word ptr [rbp+23F0h+var_850], bx
0x1800464e7  mov     [rbp+23F0h+Buffer], bx
0x1800464ee  mov     ecx, [rsi+8]; Value
0x1800464f1  cmp     ecx, 0FFFFFFFFh
0x1800464f4  jz      short loc_18004650D
0x1800464f6  mov     r9d, 0Ah; Radix
0x1800464fc  lea     r8d, [r9+0Ah]; BufferCount
0x180046500  lea     rdx, [rbp+23F0h+Buffer]; Buffer
0x180046507  call    cs:__imp__itow_s
0x18004650d  mov     dword ptr [rsp+24F0h+var_24C8], r14d
0x180046512  mov     rax, [rsi+10h]
0x180046516  mov     [rsp+24F0h+var_24D0], rax
0x18004651b  mov     r9, [rsi+8]
0x18004651f  mov     r8d, [rsi]
0x180046522  lea     rdx, aProcessingDone; "Processing Done for Message (Id:%d) for"...
0x180046529  lea     rcx, [rbp+23F0h+var_850]
0x180046530  call    FormatRRASErrorString
0x180046535  test    cs:byte_1800C8404, r12b
0x18004653c  jz      short loc_18004656C
0x18004653e  lea     rax, [rbp+23F0h+Buffer]
0x180046545  mov     [rsp+24F0h+var_24C8], rax
0x18004654a  mov     [rsp+24F0h+var_24D0], rbx
0x18004654f  lea     r9, [rbp+23F0h+var_8B0]
0x180046556  lea     r8, [rbp+23F0h+var_850]
0x18004655d  lea     rdx, RasDdmParamTraceInfo
0x180046564  mov     rcx, r13
0x180046567  call    McTemplateU0zjzz_EventWriteTransfer
0x18004656c  cmp     dword ptr [rsi], 8
0x18004656f  jnz     loc_180046CE5
0x180046575  cmp     [rsi+18h], ebx
0x180046578  jbe     loc_180046D02
0x18004657e  mov     rcx, [rsi+20h]; hMem
0x180046582  call    cs:__imp_LocalFree
0x180046588  jmp     loc_180046D02
0x18004658d  mov     ecx, 11h; unsigned int
0x180046592  call    ?GetInstance@DdmDeviceTable@@SAPEAV1@K@Z; DdmDeviceTable::GetInstance(ulong)
0x180046597  lea     r8, [rsp+24F0h+var_24C0]
0x18004659c  mov     rdx, [rsi+8]
0x1800465a0  mov     rcx, rax
0x1800465a3  call    ?FindDevice@DdmDeviceTable@@QEAAXPEAXAEAV?$RasObjPtr@VDdmDevice@@@@@Z; DdmDeviceTable::FindDevice(void *,RasObjPtr<DdmDevice> &)
0x1800465a8  mov     rdi, [rsp+24F0h+var_24C0]
0x1800465ad  test    rdi, rdi
0x1800465b0  jz      loc_180046AEA
0x1800465b6  lea     rcx, [rdi+10h]; lpCriticalSection
0x1800465ba  call    cs:__imp_EnterCriticalSection
0x1800465c0  mov     rax, [rdi]
0x1800465c3  mov     r8d, [rsi+18h]
0x1800465c7  mov     rdx, [rsi+20h]
0x1800465cb  mov     rcx, rdi
0x1800465ce  mov     rax, [rax+78h]
0x1800465d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800465d7  lea     rcx, [rdi+10h]; lpCriticalSection
0x1800465db  call    cs:__imp_LeaveCriticalSection
0x1800465e1  jmp     loc_1800464D1
0x1800465e6  lea     rcx, [rdi+10h]; lpCriticalSection
0x1800465ea  call    cs:__imp_EnterCriticalSection
0x1800465f0  mov     rax, [rdi]
0x1800465f3  mov     rax, [rax+68h]
0x1800465f7  mov     rcx, rdi
0x1800465fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800465ff  jmp     short loc_1800465D7
0x180046601  mov     ecx, 11h; unsigned int
0x180046606  call    ?GetInstance@DdmDeviceTable@@SAPEAV1@K@Z; DdmDeviceTable::GetInstance(ulong)
0x18004660b  lea     r8, [rsp+24F0h+var_24C0]
0x180046610  mov     rdx, [rsi+8]
0x180046614  mov     rcx, rax
0x180046617  call    ?FindDevice@DdmDeviceTable@@QEAAXPEAXAEAV?$RasObjPtr@VDdmDevice@@@@@Z; DdmDeviceTable::FindDevice(void *,RasObjPtr<DdmDevice> &)
0x18004661c  mov     rdi, [rsp+24F0h+var_24C0]
0x180046621  test    rdi, rdi
0x180046624  jz      loc_180046AEA
0x18004662a  lea     rcx, [rdi+10h]; lpCriticalSection
0x18004662e  call    cs:__imp_EnterCriticalSection
0x180046634  mov     rax, [rdi]
0x180046637  mov     rax, [rax+168h]
0x18004663e  jmp     short loc_1800465F7
0x180046640  mov     ecx, 11h; unsigned int
0x180046645  call    ?GetInstance@DdmDeviceTable@@SAPEAV1@K@Z; DdmDeviceTable::GetInstance(ulong)
0x18004664a  lea     r8, [rsp+24F0h+var_24C0]
0x18004664f  mov     rdx, [rsi+8]
0x180046653  mov     rcx, rax
0x180046656  call    ?FindDevice@DdmDeviceTable@@QEAAXPEAXAEAV?$RasObjPtr@VDdmDevice@@@@@Z; DdmDeviceTable::FindDevice(void *,RasObjPtr<DdmDevice> &)
0x18004665b  mov     rdi, [rsp+24F0h+var_24C0]
0x180046660  test    rdi, rdi
0x180046663  jnz     short loc_1800465E6
0x180046665  jmp     loc_180046AEA
0x18004666a  mov     r15d, 11h
0x180046670  mov     ecx, r15d; unsigned int
0x180046673  call    ?GetInstance@DdmDeviceTable@@SAPEAV1@K@Z; DdmDeviceTable::GetInstance(ulong)
0x180046678  lea     r8, [rsp+24F0h+var_24C0]
0x18004667d  mov     rdx, [rsi+8]
0x180046681  mov     rcx, rax
0x180046684  call    ?FindDevice@DdmDeviceTable@@QEAAXPEAXAEAV?$RasObjPtr@VDdmDevice@@@@@Z; DdmDeviceTable::FindDevice(void *,RasObjPtr<DdmDevice> &)
0x180046689  mov     rdi, [rsp+24F0h+var_24C0]
0x18004668e  test    rdi, rdi
0x180046691  jz      loc_180046AEA
0x180046697  lea     rbx, [rdi+10h]
0x18004669b  mov     rcx, rbx; lpCriticalSection
0x18004669e  call    cs:__imp_EnterCriticalSection
0x1800466a4  mov     rax, [rdi]
0x1800466a7  mov     rcx, rdi
0x1800466aa  mov     rax, [rax+1C0h]
0x1800466b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800466b6  mov     r14d, eax
0x1800466b9  test    eax, eax
0x1800466bb  jz      loc_180046771
0x1800466c1  test    cs:byte_1800C8404, 8
0x1800466c8  jz      loc_180046757
0x1800466ce  xor     r15d, r15d
0x1800466d1  mov     word ptr [rbp+23F0h+var_850], r15w
0x1800466d9  mov     r9d, eax
0x1800466dc  lea     r8, aDdmnotificatio_0; "DdmNotificationHandler::DriverNotificat"...
0x1800466e3  lea     rdx, aSMarkportconne; "%s:MarkPortConnectComplete failed: %d"
0x1800466ea  lea     rcx, [rbp+23F0h+var_850]
0x1800466f1  call    FormatRRASErrorString
0x1800466f6  test    cs:byte_1800C8404, 8
0x1800466fd  jz      short loc_180046757
0x1800466ff  lea     rcx, [rbp+23F0h+var_850]
0x180046706  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004670a  inc     rax
0x18004670d  cmp     [rcx+rax*2], r15w
0x180046712  jnz     short loc_18004670A
0x180046714  lea     eax, ds:2[rax*2]
0x18004671b  lea     rcx, [rbp+23F0h+var_850]
0x180046722  mov     [rbp+23F0h+var_890], rcx
0x180046729  mov     dword ptr [rbp+23F0h+var_888], eax
0x18004672f  mov     dword ptr [rbp+23F0h+var_888+4], r15d
0x180046736  lea     rax, [rbp+23F0h+var_8A0]
0x18004673d  mov     [rsp+24F0h+var_24D0], rax
0x180046742  mov     r9d, 2
0x180046748  lea     rdx, RasDdmTraceError
0x18004674f  mov     rcx, r13
0x180046752  call    McGenEventWrite_EventWriteTransfer
0x180046757  mov     rax, [rdi]
0x18004675a  mov     rcx, rdi
0x18004675d  mov     rax, [rax+0B0h]
0x180046764  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046769  mov     rcx, rbx
0x18004676c  jmp     loc_1800465DB
0x180046771  mov     rcx, rbx; lpCriticalSection
0x180046774  call    cs:__imp_LeaveCriticalSection
0x18004677a  mov     ecx, r15d; unsigned int
0x18004677d  call    ?GetInstance@DdmDeviceTable@@SAPEAV1@K@Z; DdmDeviceTable::GetInstance(ulong)
0x180046782  lea     rdx, [rsp+24F0h+var_24C0]
0x180046787  mov     rcx, rax; this
0x18004678a  call    ?UpdateDeviceBundleMap@DdmDeviceTable@@QEAAKAEAV?$RasObjPtr@VDdmDevice@@@@@Z; DdmDeviceTable::UpdateDeviceBundleMap(RasObjPtr<DdmDevice> &)
0x18004678f  call    ExecuteComponentTest
0x180046794  mov     rcx, rbx; lpCriticalSection
0x180046797  call    cs:__imp_EnterCriticalSection
0x18004679d  mov     rax, [rdi]
0x1800467a0  mov     rcx, rdi
0x1800467a3  mov     rax, [rax+58h]
0x1800467a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800467ac  mov     r14d, eax
0x1800467af  test    eax, eax
0x1800467b1  jnz     short loc_180046769
0x1800467b3  mov     rax, [rdi]
0x1800467b6  mov     rcx, rdi
0x1800467b9  mov     rax, [rax+60h]
0x1800467bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800467c2  mov     r14d, eax
0x1800467c5  jmp     short loc_180046769
0x1800467c7  mov     r15d, 11h
0x1800467cd  mov     ecx, r15d; unsigned int
0x1800467d0  call    ?GetInstance@DdmDeviceTable@@SAPEAV1@K@Z; DdmDeviceTable::GetInstance(ulong)
  ... truncated ...
```
