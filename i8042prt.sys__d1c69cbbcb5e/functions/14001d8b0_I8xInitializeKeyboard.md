# I8xInitializeKeyboard

- ea: `0x14001d8b0`
- end: `0x14001e6f5`
- name: `I8xInitializeKeyboard`
- size: `3653`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14001eea0`

## callees

- `0x140004530`
- `0x140005560`
- `0x1400059c0`
- `0x1400066d0`
- `0x140006950`
- `0x140007b10`
- `0x140008000`
- `0x140009840`
- `0x14000a394`
- `0x14000a410`
- `0x14000a48c`
- `0x14000a508`
- `0x14000a584`
- `0x14000a600`
- `0x14000daa0`
- `0x14001d8b0`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x14001d9ed`
- `ntoskrnl!KeDelayExecutionThread` at `0x14001d9ed`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001e120`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001e181`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001e120`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001e181`
- `ntoskrnl!KeQueryTimeIncrement` at `0x14001d9fc`
- `ntoskrnl!KeQueryTimeIncrement` at `0x14001d9fc`
- `ntoskrnl!ZwClose` at `0x14001e1fa`
- `ntoskrnl!ZwClose` at `0x14001e2f3`
- `ntoskrnl!ZwClose` at `0x14001e1fa`
- `ntoskrnl!ZwClose` at `0x14001e2f3`
- `ntoskrnl!ZwSetValueKey` at `0x14001e1ea`
- `ntoskrnl!ZwSetValueKey` at `0x14001e1ea`
- `ntoskrnl!ZwOpenKey` at `0x14001e101`
- `ntoskrnl!ZwOpenKey` at `0x14001e15f`
- `ntoskrnl!ZwOpenKey` at `0x14001e101`
- `ntoskrnl!ZwOpenKey` at `0x14001e15f`

## pseudocode

```c
__int64 __fastcall I8xInitializeKeyboard(__int64 *a1, int a2, __int64 a3, __int64 a4)
{
  unsigned __int8 v4; // r15
  char v5; // r13
  char v6; // r12
  int v8; // eax
  int v9; // edx
  __int64 v10; // rcx
  unsigned int v11; // r13d
  __int64 v12; // rdi
  int BytePolled; // r14d
  __int64 v14; // rbx
  int v15; // edx
  char v16; // di
  unsigned __int8 v17; // bl
  int v18; // ecx
  char v19; // r15
  __int64 v20; // r8
  __int64 v21; // r9
  int v22; // edx
  int v23; // ebx
  __int64 v24; // r8
  __int64 v25; // r9
  unsigned __int8 v26; // al
  __int64 v27; // r8
  int v28; // edx
  unsigned int v29; // ebx
  __int64 v30; // rdx
  __int64 v31; // rcx
  unsigned __int8 v32; // al
  int v33; // r14d
  int v34; // ebx
  __int64 v35; // r8
  __int64 v36; // r9
  int v37; // edx
  unsigned int v38; // ebx
  __int64 v39; // r8
  __int64 v40; // r9
  int v41; // r9d
  void (__fastcall *v42)(__int64, __int64, __int64 (__fastcall *)(), __int64 (__fastcall *)(), char *); // rax
  __int64 v43; // r8
  __int64 v44; // r9
  int v45; // ebx
  unsigned int v46; // eax
  int v47; // ecx
  int v48; // edx
  __int64 v49; // r8
  __int64 v50; // r9
  int v51; // edx
  int v52; // r8d
  int v53; // ecx
  int v54; // edx
  int v55; // edx
  int v56; // edx
  int v58; // r15d
  __int64 v59; // rcx
  ULONG DataSize; // [rsp+28h] [rbp-91h]
  char v61; // [rsp+40h] [rbp-79h]
  char v62[3]; // [rsp+41h] [rbp-78h] BYREF
  unsigned int v63; // [rsp+44h] [rbp-75h]
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-71h] BYREF
  char v65; // [rsp+58h] [rbp-61h] BYREF
  unsigned __int8 v66; // [rsp+59h] [rbp-60h]
  int Data; // [rsp+5Ch] [rbp-5Dh] BYREF
  __int64 v68; // [rsp+60h] [rbp-59h]
  __int64 v69; // [rsp+68h] [rbp-51h] BYREF
  int v70; // [rsp+70h] [rbp-49h]
  void *KeyHandle; // [rsp+78h] [rbp-41h] BYREF
  HANDLE Handle; // [rsp+80h] [rbp-39h] BYREF
  unsigned int v73; // [rsp+88h] [rbp-31h]
  union _LARGE_INTEGER Interval; // [rsp+90h] [rbp-29h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+98h] [rbp-21h] BYREF

  v62[0] = 0;
  LODWORD(Handle) = 0;
  v4 = 1;
  v69 = 0;
  v5 = 0;
  v70 = 0;
  LODWORD(KeyHandle) = 0;
  v6 = 0;
  Data = 0;
  v73 = 0;
  v63 = 0;
  Interval.QuadPart = 0;
  v65 = 1;
  v61 = 0;
  v66 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      15,
      33,
      (__int64)WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids);
  v68 = *a1;
  *(_QWORD *)&DestinationString.Length = 0;
  DestinationString.Buffer = 0;
LABEL_4:
  LOBYTE(a4) = -1;
  LOBYTE(a3) = 1;
  v8 = I8xPutBytePolled(0, v4, a3, a4);
  if ( v8 >= 0 )
    goto LABEL_8;
  v11 = v8;
  Data = v8;
  if ( *((_BYTE *)a1 + 954) )
  {
    v5 = 1;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v9,
        16,
        35,
        (__int64)WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids);
LABEL_8:
    Interval.QuadPart = -100;
    v12 = MEMORY[0xFFFFF78000000320];
    while ( 1 )
    {
      LOBYTE(v10) = 1;
      BytePolled = I8xGetBytePolled(v10, v62);
      if ( BytePolled >= 0 )
        break;
      if ( BytePolled != -1073741643 )
        goto LABEL_14;
      KeDelayExecutionThread(0, 0, &Interval);
      v14 = MEMORY[0xFFFFF78000000320];
      if ( (v14 - v12) * KeQueryTimeIncrement() >= 100000000 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            v15,
            17,
            36,
            (__int64)WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids);
LABEL_14:
        if ( v4 == 1 )
        {
          v4 = 0;
          goto LABEL_4;
        }
        v18 = BytePolled;
        v16 = 0;
        v63 = BytePolled;
        v19 = 0;
        v17 = 1;
LABEL_75:
        if ( v5 )
        {
          if ( v16 && v6 )
          {
            if ( *((_BYTE *)a1 + 954) == 1 )
            {
              *(_QWORD *)&ObjectAttributes.Length = 48;
              *(_QWORD *)&ObjectAttributes.Attributes = 576;
              ObjectAttributes.ObjectName = (PUNICODE_STRING)&WPP_MAIN_CB.Queue.Wcb.CurrentIrp;
              KeyHandle = 0;
              Handle = 0;
              DestinationString = 0;
              ObjectAttributes.RootDirectory = 0;
              *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
              if ( ZwOpenKey(&KeyHandle, 0xF003Fu, &ObjectAttributes) >= 0 )
              {
                RtlInitUnicodeString(&DestinationString, L"Parameters");
                ObjectAttributes.RootDirectory = KeyHandle;
                ObjectAttributes.Length = 48;
                ObjectAttributes.ObjectName = &DestinationString;
                ObjectAttributes.Attributes = 576;
                *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
                if ( ZwOpenKey(&Handle, 0xF003Fu, &ObjectAttributes) >= 0 )
                {
                  Data = 0;
                  RtlInitUnicodeString(&DestinationString, L"KeyboardFailedReset");
                  Data = 0;
                  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                    WPP_RECORDER_SF_(
                      WPP_GLOBAL_Control->DeviceExtension,
                      v54,
                      17,
                      51,
                      (__int64)WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids);
                  ZwSetValueKey(Handle, &DestinationString, 0, 4u, &Data, 4u);
                  ZwClose(Handle);
                }
                ZwClose(KeyHandle);
              }
            }
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              WPP_RECORDER_SF_(
                WPP_GLOBAL_Control->DeviceExtension,
                (unsigned int)&WPP_RECORDER_INITIALIZED,
                16,
                52,
                (__int64)WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids);
            BytePolled = -1073741667;
            **(_DWORD **)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels |= 0x4000u;
            if ( HIBYTE(WPP_MAIN_CB.Dpc.DeferredRoutine) )
            {
              I8xLogError(v68, 1074069536, 0, -1073741667, 0, 0);
              TraceLoggingDeviceNotConnected(3221225629LL);
            }
            goto LABEL_99;
          }
          v11 = Data;
LABEL_104:
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_D(
              WPP_GLOBAL_Control->DeviceExtension,
              (unsigned int)&WPP_RECORDER_INITIALIZED,
              17,
              53,
              (__int64)WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids,
              BytePolled);
          goto LABEL_106;
        }
        goto LABEL_109;
      }
    }
    if ( v62[0] == -86 )
    {
      v19 = 0;
    }
    else
    {
      v19 = 1;
      v73 = BytePolled;
      v61 = 1;
      v66 = v62[0];
    }
    WORD2(v69) = -16639;
    LODWORD(v69) = **(_DWORD **)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels;
    I8xTransmitControllerCommand(&v69);
    if ( v70 < 0 )
    {
      I8xTransmitControllerCommand(&v69);
      BytePolled = v70;
      if ( v70 < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            (unsigned int)&WPP_RECORDER_INITIALIZED,
            17,
            37,
            (__int64)WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids);
        v18 = v63;
        v16 = 0;
        v17 = 0;
        goto LABEL_75;
      }
    }
    LOBYTE(v20) = 1;
    LOBYTE(v21) = -13;
    v23 = I8xPutBytePolled(0, 1, v20, v21);
    if ( v23 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v22,
          16,
          38,
          (__int64)WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids);
      v16 = 1;
      LODWORD(KeyHandle) = v23;
    }
    else
    {
      v26 = I8xConvertTypematicParameters(*((unsigned __int16 *)a1 + 363), *((unsigned __int16 *)a1 + 364));
      LOBYTE(v27) = 1;
      v29 = I8xPutBytePolled(0, 1, v27, v26);
      if ( v29 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            v28,
            17,
            39,
            (__int64)WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids);
        v30 = *((unsigned __int16 *)a1 + 364);
        v31 = *((unsigned __int16 *)a1 + 363);
        *(_QWORD *)&DestinationString.Length = 1;
        LODWORD(DestinationString.Buffer) = 243;
        v32 = I8xConvertTypematicParameters(v31, v30);
        v33 = v68;
        HIDWORD(DestinationString.Buffer) = v32;
        I8xLogError(v68, -2147155949, 1540, v29, (__int64)&DestinationString, 4);
        TraceLoggingSetTypematicFailed(v29);
        v16 = 0;
LABEL_38:
        LOBYTE(v24) = 1;
        LOBYTE(v25) = -19;
        v34 = I8xPutBytePolled(0, 1, v24, v25);
        if ( v34 )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_(
              WPP_GLOBAL_Control->DeviceExtension,
              (unsigned int)&WPP_RECORDER_INITIALIZED,
              16,
              40,
              (__int64)WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids);
          v6 = 1;
          LODWORD(Handle) = v34;
        }
        else
        {
          LOBYTE(v35) = 1;
          v38 = I8xPutBytePolled(0, 1, v35, *((unsigned __int8 *)a1 + 732));
          if ( v38 )
          {
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              WPP_RECORDER_SF_(
                WPP_GLOBAL_Control->DeviceExtension,
                v37,
                17,
                41,
                (__int64)WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids);
            HIDWORD(DestinationString.Buffer) = *((unsigned __int16 *)a1 + 366);
            *(_QWORD *)&DestinationString.Length = 1;
            LODWORD(DestinationString.Buffer) = 237;
            I8xLogError(v33, -2147155948, 1550, v38, (__int64)&DestinationString, 4);
            TraceLoggingSetLedFailed(v38);
          }
        }
        BytePolled = 0;
        if ( *((_BYTE *)a1 + 688) == 7 && *((_BYTE *)a1 + 689) == 3 )
        {
          LOBYTE(v35) = 1;
          LOBYTE(v36) = -16;
          BytePolled = I8xPutBytePolled(0, 1, v35, v36);
          if ( BytePolled )
          {
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_53;
            WPP_RECORDER_SF_(
              WPP_GLOBAL_Control->DeviceExtension,
              (unsigned int)&WPP_RECORDER_INITIALIZED,
              17,
              42,
              (__int64)WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids);
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_53;
            v41 = 43;
LABEL_52:
            WPP_RECORDER_SF_(
              WPP_GLOBAL_Control->DeviceExtension,
              (unsigned int)&WPP_RECORDER_INITIALIZED,
              17,
              v41,
              (__int64)WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids);
LABEL_53:
            *((_WORD *)a1 + 345) = 3;
            goto LABEL_58;
          }
          LOBYTE(v39) = 1;
          LOBYTE(v40) = -126;
          BytePolled = I8xPutBytePolled(0, 1, v39, v40);
          if ( BytePolled )
          {
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_53;
            WPP_RECORDER_SF_(
              WPP_GLOBAL_Control->DeviceExtension,
              (unsigned int)&WPP_RECORDER_INITIALIZED,
              17,
              44,
              (__int64)WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids);
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_53;
            v41 = 45;
            goto LABEL_52;
          }
        }
LABEL_58:
        v42 = (void (__fastcall *)(__int64, __int64, __int64 (__fastcall *)(), __int64 (__fastcall *)(), char *))a1[115];
        if ( v42 )
          v42(a1[117], v68, I8xKeyboardSynchReadPort, I8xKeyboardSynchWritePort, &v65);
        if ( *((_WORD *)a1 + 345) == 1 && v65 )
        {
          WORD2(v69) = 0x4000;
          LODWORD(v69) = **(_DWORD **)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels;
          I8xTransmitControllerCommand(&v69);
          v45 = v70;
          if ( v70 >= 0 )
            goto LABEL_74;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_(
              WPP_GLOBAL_Control->DeviceExtension,
              (unsigned int)&WPP_RECORDER_INITIALIZED,
              17,
              46,
              (__int64)WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids);
          if ( v45 != -1073741668 )
          {
            v18 = v63;
            BytePolled = v45;
            v17 = 0;
            goto LABEL_75;
          }
          v46 = *((unsigned __int8 *)a1 + 688);
          if ( (unsigned __int8)v46 <= 8u )
          {
            v47 = 404;
            if ( _bittest(&v47, v46) )
            {
              LOBYTE(v43) = 1;
              LOBYTE(v44) = -16;
              BytePolled = I8xPutBytePolled(0, 1, v43, v44);
              if ( BytePolled >= 0 )
              {
                if ( *((_BYTE *)a1 + 688) != 7 || (LOBYTE(v50) = -127, *((_BYTE *)a1 + 689) != 3) )
                  LOBYTE(v50) = 1;
                LOBYTE(v49) = 1;
                BytePolled = I8xPutBytePolled(0, 1, v49, v50);
                if ( BytePolled >= 0 )
                  goto LABEL_74;
                if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                {
                  WPP_RECORDER_SF_(
                    WPP_GLOBAL_Control->DeviceExtension,
                    v55,
                    17,
                    49,
                    (__int64)WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids);
                  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                    WPP_RECORDER_SF_(
                      WPP_GLOBAL_Control->DeviceExtension,
                      v56,
                      17,
                      50,
                      (__int64)WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids);
                }
                *(_QWORD *)&DestinationString.Length = 1;
                v52 = 1560;
                HIDWORD(DestinationString.Buffer) = 1;
                DataSize = 4;
              }
              else
              {
                if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                {
                  WPP_RECORDER_SF_(
                    WPP_GLOBAL_Control->DeviceExtension,
                    v48,
                    17,
                    47,
                    (__int64)WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids);
                  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                    WPP_RECORDER_SF_(
                      WPP_GLOBAL_Control->DeviceExtension,
                      v51,
                      17,
                      48,
                      (__int64)WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids);
                }
                *(_QWORD *)&DestinationString.Length = 0;
                v52 = 1555;
                DataSize = 3;
              }
              v53 = v68;
              LODWORD(DestinationString.Buffer) = 240;
              *((_WORD *)a1 + 345) = 2;
              I8xLogError(v53, -2147155947, v52, BytePolled, (__int64)&DestinationString, DataSize);
              TraceLoggingSelectScansetFailed((unsigned int)BytePolled);
LABEL_74:
              v18 = v63;
              v17 = 0;
              goto LABEL_75;
            }
          }
        }
        v18 = v63;
        v17 = 0;
        goto LABEL_75;
      }
      v16 = 0;
    }
    v33 = v68;
    goto LABEL_38;
  }
  BytePolled = -1073741667;
  **(_DWORD **)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels |= 0x4000u;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v9,
      16,
      34,
      (__int64)WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids);
    v16 = 0;
    v17 = 0;
    goto LABEL_104;
  }
  v16 = 0;
  v17 = 0;
LABEL_106:
  if ( HIBYTE(WPP_MAIN_CB.Dpc.DeferredRoutine) )
  {
    *(_QWORD *)&DestinationString.Length = 0;
    LODWORD(DestinationString.Buffer) = 255;
    I8xLogError(v68, -2147155953, 1510, v11, (__int64)&DestinationString, 3);
    TraceLoggingResetCommandFailed(v11);
  }
  v18 = v63;
  v19 = v61;
LABEL_109:
  if ( v17 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      WPP_RECORDER_SF_dD(
        WPP_GLOBAL_Control->DeviceExtension,
        (unsigned int)&WPP_RECORDER_INITIALIZED,
        17,
        54,
        (__int64)WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids,
        BytePolled,
        v62[0]);
      v18 = v63;
    }
    v58 = v68;
    HIDWORD(DestinationString.Buffer) = v17;
    *(_DWORD *)&DestinationString.Length = 4;
    *(_DWORD *)(&DestinationString.MaximumLength + 1) = 1;
    LODWORD(DestinationString.Buffer) = 170;
    I8xLogError(v68, -2147155951, 1520, v18, (__int64)&DestinationString, 4);
    v59 = v63;
LABEL_113:
    TraceLoggingResetResponseFailed(v59);
    goto LABEL_119;
  }
  if ( v19 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        (unsigned int)&WPP_RECORDER_INITIALIZED,
        17,
        55,
        (__int64)WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids);
    v58 = v68;
    HIDWORD(DestinationString.Buffer) = v66;
    *(_DWORD *)&DestinationString.Length = 4;
    *(_DWORD *)(&DestinationString.MaximumLength + 1) = 1;
    LODWORD(DestinationString.Buffer) = 170;
    I8xLogError(v68, -2147155951, 1515, v73, (__int64)&DestinationString, 4);
    v59 = v73;
    goto LABEL_113;
  }
  v58 = v68;
LABEL_119:
  if ( v16 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        (unsigned int)&WPP_RECORDER_INITIALIZED,
        17,
        56,
        (__int64)WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids);
    *(_QWORD *)&DestinationString.Length = 0;
    LODWORD(DestinationString.Buffer) = 243;
    I8xLogError(v58, -2147155949, 1535, (_DWORD)KeyHandle, (__int64)&DestinationString, 3);
    TraceLoggingSetTypematicFailed((unsigned int)KeyHandle);
  }
  if ( v6 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        (unsigned int)&WPP_RECORDER_INITIALIZED,
        17,
        57,
        (__int64)WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids);
    *(_QWORD *)&DestinationString.Length = 0;
    LODWORD(DestinationString.Buffer) = 237;
    I8xLogError(v58, -2147155948, 1545, (_DWORD)Handle, (__int64)&DestinationString, 3);
    TraceLoggingSetLedFailed((unsigned int)Handle);
  }
  if ( (int)(BytePolled + 0x80000000) < 0 || BytePolled == -1073741667 )
LABEL_99:
    **(_DWORD **)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels |= 0x101u;
  else
    **(_DWORD **)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels &= 0xFFFFFEFE;
  *(__int64 *)((char *)a1 + 524) = 0;
  a1[64] = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      (unsigned int)&WPP_RECORDER_INITIALIZED,
      15,
      58,
      (__int64)WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids,
      BytePolled);
  return (unsigned int)BytePolled;
}

```

## disassembly

```asm
0x14001d8b0  push    rbp
0x14001d8b2  push    rbx
0x14001d8b3  push    rsi
0x14001d8b4  push    rdi
0x14001d8b5  push    r12
0x14001d8b7  push    r13
0x14001d8b9  push    r14
0x14001d8bb  push    r15
0x14001d8bd  lea     rbp, [rsp-1Fh]
0x14001d8c2  sub     rsp, 0D8h
0x14001d8c9  xor     r14d, r14d
0x14001d8cc  mov     [rbp+57h+var_CF], 0
0x14001d8d0  xor     eax, eax
0x14001d8d2  mov     dword ptr [rbp+57h+Handle], r14d
0x14001d8d6  mov     r15b, 1
0x14001d8d9  mov     [rbp+57h+var_A8], rax
0x14001d8dd  xor     r13b, r13b
0x14001d8e0  mov     [rbp+57h+var_A0], eax
0x14001d8e3  mov     dword ptr [rbp+57h+KeyHandle], r14d
0x14001d8e7  xor     r12b, r12b
0x14001d8ea  mov     [rbp+57h+var_B4], r14d
0x14001d8ee  mov     rsi, rcx
0x14001d8f1  mov     [rbp+57h+var_88], r14d
0x14001d8f5  mov     [rbp+57h+var_CC], r14d
0x14001d8f9  mov     qword ptr [rbp+57h+Interval], r14
0x14001d8fd  mov     [rbp+57h+var_B8], r15b
0x14001d901  mov     [rbp+57h+var_D0], al
0x14001d904  mov     [rbp+57h+var_B7], 0
0x14001d908  lea     rdi, WPP_RECORDER_INITIALIZED
0x14001d90f  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14001d916  lea     rax, WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids
0x14001d91d  jz      short loc_14001D940
0x14001d91f  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d926  mov     r9d, 21h ; '!'
0x14001d92c  mov     r8d, 0Fh
0x14001d932  mov     [rsp+110h+Data], rax
0x14001d937  mov     rcx, [rcx+40h]
0x14001d93b  call    WPP_RECORDER_SF_
0x14001d940  mov     rax, [rsi]
0x14001d943  mov     rbx, 0FFFFF78000000320h
0x14001d94d  mov     [rbp+57h+var_B0], rax
0x14001d951  mov     qword ptr [rbp+57h+DestinationString.Length], r14
0x14001d955  mov     [rbp+57h+DestinationString.Buffer], r14
0x14001d959  mov     r9b, 0FFh
0x14001d95c  mov     r8b, 1
0x14001d95f  movzx   edx, r15b
0x14001d963  xor     ecx, ecx
0x14001d965  call    I8xPutBytePolled
0x14001d96a  test    eax, eax
0x14001d96c  jns     short loc_14001D9B5
0x14001d96e  mov     r13d, eax
0x14001d971  mov     [rbp+57h+var_B4], eax
0x14001d974  cmp     [rsi+3BAh], r12b
0x14001d97b  jz      loc_14001DA77
0x14001d981  mov     r13b, 1
0x14001d984  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14001d98b  jz      short loc_14001D9B5
0x14001d98d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d994  lea     rax, WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids
0x14001d99b  mov     r9d, 23h ; '#'
0x14001d9a1  mov     [rsp+110h+Data], rax
0x14001d9a6  mov     r8d, 10h
0x14001d9ac  mov     rcx, [rcx+40h]
0x14001d9b0  call    WPP_RECORDER_SF_
0x14001d9b5  mov     qword ptr [rbp+57h+Interval], 0FFFFFFFFFFFFFF9Ch
0x14001d9bd  mov     rdi, [rbx]
0x14001d9c0  lea     rdx, [rbp+57h+var_CF]
0x14001d9c4  mov     cl, 1
0x14001d9c6  call    I8xGetBytePolled
0x14001d9cb  mov     r14d, eax
0x14001d9ce  mov     eax, 3
0x14001d9d3  test    r14d, r14d
0x14001d9d6  jns     loc_14001DAEE
0x14001d9dc  cmp     r14d, 0C00000B5h
0x14001d9e3  jnz     short loc_14001DA62
0x14001d9e5  lea     r8, [rbp+57h+Interval]; Interval
0x14001d9e9  xor     edx, edx; Alertable
0x14001d9eb  xor     ecx, ecx; WaitMode
0x14001d9ed  call    cs:__imp_KeDelayExecutionThread
0x14001d9f4  nop     dword ptr [rax+rax+00h]
0x14001d9f9  mov     rbx, [rbx]
0x14001d9fc  call    cs:__imp_KeQueryTimeIncrement
0x14001da03  nop     dword ptr [rax+rax+00h]
0x14001da08  sub     rbx, rdi
0x14001da0b  mov     eax, eax
0x14001da0d  imul    rax, rbx
0x14001da11  mov     rbx, 0FFFFF78000000320h
0x14001da1b  cmp     rax, 5F5E100h
0x14001da21  jl      short loc_14001D9C0
0x14001da23  lea     rdi, WPP_RECORDER_INITIALIZED
0x14001da2a  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14001da31  jz      short loc_14001DA5B
0x14001da33  mov     rcx, cs:WPP_GLOBAL_Control
0x14001da3a  lea     rax, WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids
0x14001da41  mov     r9d, 24h ; '$'
0x14001da47  mov     [rsp+110h+Data], rax
0x14001da4c  mov     r8d, 11h
0x14001da52  mov     rcx, [rcx+40h]
0x14001da56  call    WPP_RECORDER_SF_
0x14001da5b  mov     eax, 3
0x14001da60  jmp     short loc_14001DA69
0x14001da62  lea     rdi, WPP_RECORDER_INITIALIZED
0x14001da69  cmp     r15b, 1
0x14001da6d  jnz     short loc_14001DADB
0x14001da6f  xor     r15b, r15b
0x14001da72  jmp     loc_14001D959
0x14001da77  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x14001da7e  mov     r14d, 0C000009Dh
0x14001da84  or      dword ptr [rax], 4000h
0x14001da8a  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14001da91  jz      short loc_14001DAD1
0x14001da93  mov     rcx, cs:WPP_GLOBAL_Control
0x14001da9a  lea     r15, WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids
0x14001daa1  mov     r9d, 22h ; '"'
0x14001daa7  mov     [rsp+110h+Data], r15
0x14001daac  mov     r8d, 10h
0x14001dab2  mov     rcx, [rcx+40h]
0x14001dab6  call    WPP_RECORDER_SF_
0x14001dabb  xor     dil, dil
0x14001dabe  lea     rdx, WPP_RECORDER_INITIALIZED
0x14001dac5  xor     bl, bl
0x14001dac7  mov     eax, 3
0x14001dacc  jmp     loc_14001E402
0x14001dad1  xor     dil, dil
0x14001dad4  xor     bl, bl
0x14001dad6  jmp     loc_14001E431
0x14001dadb  mov     ecx, r14d
0x14001dade  xor     dil, dil
0x14001dae1  mov     [rbp+57h+var_CC], ecx
0x14001dae4  xor     r15b, r15b
0x14001dae7  mov     bl, 1
0x14001dae9  jmp     loc_14001E090
0x14001daee  movzx   eax, [rbp+57h+var_CF]
0x14001daf2  cmp     al, 0AAh
0x14001daf4  jz      short loc_14001DB06
0x14001daf6  mov     r15b, 1
0x14001daf9  mov     [rbp+57h+var_88], r14d
0x14001dafd  mov     [rbp+57h+var_D0], r15b
0x14001db01  mov     [rbp+57h+var_B7], al
0x14001db04  jmp     short loc_14001DB09
0x14001db06  xor     r15b, r15b
0x14001db09  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x14001db10  mov     word ptr [rbp+57h+var_A8+4], 0BF01h
0x14001db16  mov     ecx, [rax]
0x14001db18  mov     dword ptr [rbp+57h+var_A8], ecx
0x14001db1b  lea     rcx, [rbp+57h+var_A8]
0x14001db1f  call    I8xTransmitControllerCommand
0x14001db24  cmp     [rbp+57h+var_A0], 0
0x14001db28  jge     short loc_14001DB8D
0x14001db2a  lea     rcx, [rbp+57h+var_A8]
0x14001db2e  call    I8xTransmitControllerCommand
0x14001db33  mov     r14d, [rbp+57h+var_A0]
0x14001db37  test    r14d, r14d
0x14001db3a  jns     short loc_14001DB8D
0x14001db3c  lea     rdx, WPP_RECORDER_INITIALIZED
0x14001db43  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x14001db4a  jz      short loc_14001DB7B
0x14001db4c  mov     rcx, cs:WPP_GLOBAL_Control
0x14001db53  lea     rax, WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids
0x14001db5a  mov     r9d, 25h ; '%'
0x14001db60  mov     [rsp+110h+Data], rax
0x14001db65  mov     r8d, 11h
0x14001db6b  mov     rcx, [rcx+40h]
0x14001db6f  call    WPP_RECORDER_SF_
0x14001db74  lea     rdx, WPP_RECORDER_INITIALIZED
0x14001db7b  mov     ecx, [rbp+57h+var_CC]
0x14001db7e  xor     dil, dil
0x14001db81  xor     bl, bl
0x14001db83  mov     eax, 3
0x14001db88  jmp     loc_14001E097
0x14001db8d  mov     r8b, 1
0x14001db90  mov     r9b, 0F3h
0x14001db93  movzx   edx, r8b
0x14001db97  xor     ecx, ecx
0x14001db99  call    I8xPutBytePolled
0x14001db9e  mov     ebx, eax
0x14001dba0  test    eax, eax
0x14001dba2  jz      short loc_14001DBE7
0x14001dba4  lea     rax, WPP_RECORDER_INITIALIZED
0x14001dbab  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001dbb2  jz      short loc_14001DBDC
0x14001dbb4  mov     rcx, cs:WPP_GLOBAL_Control
0x14001dbbb  lea     rax, WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids
0x14001dbc2  mov     r9d, 26h ; '&'
0x14001dbc8  mov     [rsp+110h+Data], rax
0x14001dbcd  mov     r8d, 10h
0x14001dbd3  mov     rcx, [rcx+40h]
0x14001dbd7  call    WPP_RECORDER_SF_
0x14001dbdc  mov     dil, 1
0x14001dbdf  mov     dword ptr [rbp+57h+KeyHandle], ebx
0x14001dbe2  jmp     loc_14001DCB0
0x14001dbe7  movzx   edx, word ptr [rsi+2D8h]
0x14001dbee  movzx   ecx, word ptr [rsi+2D6h]
0x14001dbf5  call    I8xConvertTypematicParameters
0x14001dbfa  mov     r8b, 1
0x14001dbfd  movzx   r9d, al
0x14001dc01  movzx   edx, r8b
0x14001dc05  xor     ecx, ecx
0x14001dc07  call    I8xPutBytePolled
0x14001dc0c  mov     ebx, eax
0x14001dc0e  test    eax, eax
0x14001dc10  jz      loc_14001DCAD
0x14001dc16  lea     rax, WPP_RECORDER_INITIALIZED
0x14001dc1d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001dc24  jz      short loc_14001DC4E
0x14001dc26  mov     rcx, cs:WPP_GLOBAL_Control
0x14001dc2d  lea     rax, WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids
0x14001dc34  mov     r9d, 27h ; '''
0x14001dc3a  mov     [rsp+110h+Data], rax
0x14001dc3f  mov     r8d, 11h
0x14001dc45  mov     rcx, [rcx+40h]
0x14001dc49  call    WPP_RECORDER_SF_
0x14001dc4e  movzx   edx, word ptr [rsi+2D8h]
0x14001dc55  movzx   ecx, word ptr [rsi+2D6h]
0x14001dc5c  mov     qword ptr [rbp+57h+DestinationString.Length], 1
0x14001dc64  mov     dword ptr [rbp+57h+DestinationString.Buffer], 0F3h
0x14001dc6b  call    I8xConvertTypematicParameters
0x14001dc70  mov     r14, [rbp+57h+var_B0]
0x14001dc74  mov     r9d, ebx
0x14001dc77  movzx   eax, al
0x14001dc7a  mov     edx, 80050013h
0x14001dc7f  mov     dword ptr [rbp+57h+DestinationString.Buffer+4], eax
0x14001dc82  mov     r8d, 604h
0x14001dc88  lea     rax, [rbp+57h+DestinationString]
0x14001dc8c  mov     [rsp+110h+DataSize], 4
0x14001dc94  mov     rcx, r14
0x14001dc97  mov     [rsp+110h+Data], rax
0x14001dc9c  call    I8xLogError
0x14001dca1  mov     ecx, ebx
0x14001dca3  call    TraceLoggingSetTypematicFailed
0x14001dca8  xor     dil, dil
0x14001dcab  jmp     short loc_14001DCB4
0x14001dcad  xor     dil, dil
0x14001dcb0  mov     r14, [rbp+57h+var_B0]
0x14001dcb4  mov     r8b, 1
0x14001dcb7  mov     r9b, 0EDh
0x14001dcba  movzx   edx, r8b
0x14001dcbe  xor     ecx, ecx
0x14001dcc0  call    I8xPutBytePolled
0x14001dcc5  mov     ebx, eax
0x14001dcc7  test    eax, eax
0x14001dcc9  jz      short loc_14001DD15
0x14001dccb  lea     rdx, WPP_RECORDER_INITIALIZED
0x14001dcd2  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x14001dcd9  jz      short loc_14001DD0A
0x14001dcdb  mov     rcx, cs:WPP_GLOBAL_Control
0x14001dce2  lea     rax, WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids
0x14001dce9  mov     r9d, 28h ; '('
0x14001dcef  mov     [rsp+110h+Data], rax
0x14001dcf4  mov     r8d, 10h
0x14001dcfa  mov     rcx, [rcx+40h]
0x14001dcfe  call    WPP_RECORDER_SF_
0x14001dd03  lea     rdx, WPP_RECORDER_INITIALIZED
0x14001dd0a  mov     r12b, 1
0x14001dd0d  mov     dword ptr [rbp+57h+Handle], ebx
0x14001dd10  jmp     loc_14001DDB7
0x14001dd15  movzx   r9d, byte ptr [rsi+2DCh]
0x14001dd1d  mov     r8b, 1
0x14001dd20  movzx   edx, r8b
0x14001dd24  xor     ecx, ecx
0x14001dd26  call    I8xPutBytePolled
0x14001dd2b  mov     ebx, eax
0x14001dd2d  test    eax, eax
0x14001dd2f  jz      short loc_14001DDB0
0x14001dd31  lea     rax, WPP_RECORDER_INITIALIZED
0x14001dd38  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001dd3f  jz      short loc_14001DD69
0x14001dd41  mov     rcx, cs:WPP_GLOBAL_Control
0x14001dd48  lea     rax, WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids
0x14001dd4f  mov     r9d, 29h ; ')'
0x14001dd55  mov     [rsp+110h+Data], rax
0x14001dd5a  mov     r8d, 11h
0x14001dd60  mov     rcx, [rcx+40h]
0x14001dd64  call    WPP_RECORDER_SF_
0x14001dd69  movzx   eax, word ptr [rsi+2DCh]
0x14001dd70  mov     r9d, ebx
0x14001dd73  mov     dword ptr [rbp+57h+DestinationString.Buffer+4], eax
0x14001dd76  mov     edx, 80050014h
0x14001dd7b  lea     rax, [rbp+57h+DestinationString]
0x14001dd7f  mov     [rsp+110h+DataSize], 4
0x14001dd87  mov     r8d, 60Eh
0x14001dd8d  mov     [rsp+110h+Data], rax
0x14001dd92  mov     rcx, r14
0x14001dd95  mov     qword ptr [rbp+57h+DestinationString.Length], 1
0x14001dd9d  mov     dword ptr [rbp+57h+DestinationString.Buffer], 0EDh
0x14001dda4  call    I8xLogError
0x14001dda9  mov     ecx, ebx
0x14001ddab  call    TraceLoggingSetLedFailed
0x14001ddb0  lea     rdx, WPP_RECORDER_INITIALIZED
0x14001ddb7  xor     r14d, r14d
0x14001ddba  cmp     byte ptr [rsi+2B0h], 7
0x14001ddc1  jnz     loc_14001DED9
0x14001ddc7  cmp     byte ptr [rsi+2B1h], 3
0x14001ddce  jnz     loc_14001DED9
0x14001ddd4  mov     r8b, 1
0x14001ddd7  mov     r9b, 0F0h
0x14001ddda  movzx   edx, r8b
0x14001ddde  xor     ecx, ecx
0x14001dde0  call    I8xPutBytePolled
0x14001dde5  mov     r14d, eax
  ... truncated ...
```
