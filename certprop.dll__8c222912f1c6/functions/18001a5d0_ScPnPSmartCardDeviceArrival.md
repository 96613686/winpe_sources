# ScPnPSmartCardDeviceArrival

- ea: `0x18001a5d0`
- end: `0x18001add0`
- name: `ScPnPSmartCardDeviceArrival`
- size: `2048`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x180004600`
- `0x180016090`
- `0x180018b58`
- `0x180018bb4`
- `0x180018d78`
- `0x180019ed8`
- `0x18001a19c`
- `0x18001a5d0`
- `0x18001add8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001a993`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001abc1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001a993`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001abc1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001acfd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001ad14`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001ad32`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001ad44`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001acfd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001ad14`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001ad32`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001ad44`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a73d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ad5d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a73d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ad5d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a71d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001aa59`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a71d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001aa59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a76a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a7ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a86a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ab5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ac66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a76a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a7ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a86a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ab5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ac66`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Parent` at `0x18001a8de`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Parent` at `0x18001a8de`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_ID_Size` at `0x18001a930`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_ID_Size` at `0x18001a930`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_IDW` at `0x18001aa00`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_IDW` at `0x18001aa00`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x18001ab54`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x18001ac52`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x18001ab54`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x18001ac52`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x18001a860`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x18001a860`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x18001ace6`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x18001ace6`
- `SETUPAPI!SetupDiOpenDeviceInterfaceW` at `0x18001a7db`
- `SETUPAPI!SetupDiOpenDeviceInterfaceW` at `0x18001a7db`
- `SETUPAPI!SetupDiGetClassDevsW` at `0x18001a758`
- `SETUPAPI!SetupDiGetClassDevsW` at `0x18001a758`

## pseudocode

```c
void __fastcall ScPnPSmartCardDeviceArrival(__int64 Instance, LPVOID *Context, PTP_WORK Work)
{
  DWORD v3; // ebx
  LPVOID *v4; // rdi
  STRSAFE_LPSTR v5; // rcx
  int v6; // r8d
  int v7; // r9d
  STRSAFE_LPSTR v8; // rcx
  int v9; // r15d
  int v10; // r8d
  int v11; // r9d
  HDEVINFO ClassDevsW; // rax
  __int64 v13; // rsi
  void *v14; // r13
  __int64 v15; // rcx
  const WCHAR *v16; // rdx
  WCHAR *v17; // r12
  void *v18; // r14
  __int64 v19; // rcx
  int v20; // r9d
  DWORD LastError; // eax
  __int64 v22; // rcx
  STRSAFE_LPSTR v23; // rcx
  int v24; // edx
  CONFIGRET Parent; // eax
  __int64 v26; // rcx
  CONFIGRET Device_ID_Size; // eax
  __int64 v28; // rcx
  WCHAR *v29; // rax
  __int64 v30; // rcx
  CONFIGRET Device_IDW; // eax
  __int64 v32; // rcx
  ULONGLONG i; // rdi
  char *v34; // rax
  signed __int64 v35; // r8
  int v36; // ecx
  int v37; // edx
  int v38; // eax
  STRSAFE_LPSTR v39; // rcx
  int v40; // edx
  DWORD v41; // eax
  __int64 v42; // rcx
  __int64 v43; // rdx
  int v44; // r9d
  DWORD PropertyBufferSize; // [rsp+48h] [rbp-61h] BYREF
  ULONG pulLen; // [rsp+4Ch] [rbp-5Dh] BYREF
  DEVNODE pdnDevInst; // [rsp+50h] [rbp-59h] BYREF
  DEVPROPTYPE PropertyType; // [rsp+54h] [rbp-55h] BYREF
  struct _SP_DEVINFO_DATA DeviceInfoData; // [rsp+58h] [rbp-51h] BYREF
  struct _SP_DEVICE_INTERFACE_DATA DeviceInterfaceData; // [rsp+78h] [rbp-31h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v52; // [rsp+98h] [rbp-11h] BYREF
  void *v53; // [rsp+A8h] [rbp-1h]
  DWORD v54; // [rsp+B0h] [rbp+7h]
  int v55; // [rsp+B4h] [rbp+Bh]

  v3 = 0;
  pulLen = 0;
  PropertyBufferSize = 0;
  v4 = Context;
  pdnDevInst = 0;
  PropertyType = 0;
  memset(&DeviceInterfaceData, 0, sizeof(DeviceInterfaceData));
  memset(&DeviceInfoData, 0, sizeof(DeviceInfoData));
  WppTraceIndent(Instance, 0);
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 101, &WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids, WPP_pszIndent);
  }
  if ( !v4 )
  {
    WppTraceIndent((__int64)v5, 2);
    LOBYTE(v3) = 4;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[28] & 1) != 0
      && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
    {
      WPP_SF_ss(*((_QWORD *)WPP_GLOBAL_Control + 2), 102, v6, v7, (__int64)"NULL != pPnpHandler");
    }
    goto LABEL_99;
  }
  if ( !*v4 )
  {
    v9 = 0;
    WppTraceIndent((__int64)v5, 2);
    LOBYTE(v3) = 4;
    if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[28] & 1) != 0
      && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
    {
      WPP_SF_ss(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        103,
        v10,
        v11,
        (__int64)"NULL != pPnpHandler->pwszSmartCardDeviceName");
    }
    goto LABEL_95;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_pScPnPState + 544));
  if ( *((_DWORD *)g_pScPnPState + 150) )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)g_pScPnPState + 544));
    v9 = 0;
    ClassDevsW = SetupDiGetClassDevsW(&GUID_DEVINTERFACE_SMARTCARD, 0, 0, 0x12u);
    v13 = -1;
    v14 = ClassDevsW;
    if ( ClassDevsW == (HDEVINFO)-1LL )
    {
      LOBYTE(v3) = GetLastError();
      WppTraceIndent(v15, 2);
      if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control[28] & 1) != 0
        && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
      {
        WPP_SF_sD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          104,
          (unsigned int)&WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids,
          WPP_pszIndent,
          v3);
      }
      goto LABEL_95;
    }
    v16 = (const WCHAR *)*v4;
    DeviceInterfaceData.cbSize = 32;
    v17 = 0;
    v18 = 0;
    if ( !SetupDiOpenDeviceInterfaceW(ClassDevsW, v16, 0, &DeviceInterfaceData) )
    {
      WppTraceIndent(v19, 2);
      LOBYTE(v3) = GetLastError();
      if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control[28] & 1) != 0
        && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
      {
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          105,
          (unsigned int)&WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids,
          v20,
          v3);
      }
      goto LABEL_91;
    }
    DeviceInfoData.cbSize = 32;
    if ( !SetupDiGetDeviceInterfaceDetailW(v14, &DeviceInterfaceData, 0, 0, 0, &DeviceInfoData) )
    {
      LastError = GetLastError();
      if ( LastError != 122 )
        v3 = LastError;
      if ( v3 )
      {
        WppTraceIndent(v22, 2);
        v23 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (STRSAFE_LPSTR)&WPP_GLOBAL_Control
          || (WPP_GLOBAL_Control[28] & 1) == 0
          || (unsigned __int8)WPP_GLOBAL_Control[25] < 2u )
        {
          goto LABEL_91;
        }
        v24 = 106;
        goto LABEL_34;
      }
    }
    Parent = CM_Get_Parent(&pdnDevInst, DeviceInfoData.DevInst, 0);
    LOBYTE(v3) = Parent;
    if ( Parent )
    {
      WppTraceIndent(v26, 2);
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (STRSAFE_LPSTR)&WPP_GLOBAL_Control
        || (WPP_GLOBAL_Control[28] & 1) == 0
        || (unsigned __int8)WPP_GLOBAL_Control[25] < 2u )
      {
        goto LABEL_91;
      }
      v24 = 107;
      goto LABEL_34;
    }
    Device_ID_Size = CM_Get_Device_ID_Size(&pulLen, pdnDevInst, 0);
    LOBYTE(v3) = Device_ID_Size;
    if ( Device_ID_Size )
    {
      WppTraceIndent(v28, 2);
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (STRSAFE_LPSTR)&WPP_GLOBAL_Control
        || (WPP_GLOBAL_Control[28] & 1) == 0
        || (unsigned __int8)WPP_GLOBAL_Control[25] < 2u )
      {
        goto LABEL_91;
      }
      v24 = 108;
      goto LABEL_34;
    }
    LOBYTE(v3) = 8;
    v29 = (WCHAR *)HeapAlloc(g_hHeap, 8u, 2LL * (pulLen + 1));
    v17 = v29;
    if ( !v29 )
    {
      WppTraceIndent(v30, 2);
      if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control[28] & 1) != 0
        && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          109,
          &WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids,
          WPP_pszIndent);
      }
      goto LABEL_91;
    }
    Device_IDW = CM_Get_Device_IDW(pdnDevInst, v29, pulLen, 0);
    LOBYTE(v3) = Device_IDW;
    if ( Device_IDW )
    {
      WppTraceIndent(v32, 2);
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (STRSAFE_LPSTR)&WPP_GLOBAL_Control
        || (WPP_GLOBAL_Control[28] & 1) == 0
        || (unsigned __int8)WPP_GLOBAL_Control[25] < 2u )
      {
        goto LABEL_91;
      }
      v24 = 110;
LABEL_34:
      WPP_SF_sD(
        *((_QWORD *)v23 + 2),
        v24,
        (unsigned int)&WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids,
        WPP_pszIndent,
        v3);
LABEL_91:
      SetupDiDestroyDeviceInfoList(v14);
      if ( v17 )
        HeapFree(g_hHeap, 0, v17);
      if ( v18 )
        HeapFree(g_hHeap, 0, v18);
      goto LABEL_95;
    }
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_pScPnPState + 544));
    v9 = 1;
    for ( i = *((_QWORD *)g_pScPnPState + 74); ; i = *(_QWORD *)(i + 240) )
    {
      if ( !i )
        goto LABEL_90;
      if ( *(_DWORD *)(i + 204) == 1 )
      {
        v34 = *(char **)(i + 208);
        v35 = (char *)v17 - v34;
        do
        {
          v36 = *(unsigned __int16 *)&v34[v35];
          v37 = *(unsigned __int16 *)v34 - v36;
          if ( v37 )
            break;
          v34 += 2;
        }
        while ( v36 );
        if ( !v37 )
          break;
      }
    }
    --*((_DWORD *)g_pScPnPState + 150);
    *(_DWORD *)(i + 204) = 0;
    v38 = I_ScPnPPulseReader((HANDLE *)i);
    LOBYTE(v3) = v38;
    if ( v38 )
    {
      WppTraceIndent(0, 2);
      v39 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control[28] & 1) != 0
        && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
      {
        v40 = 111;
LABEL_68:
        WPP_SF_sD(
          *((_QWORD *)v39 + 2),
          v40,
          (unsigned int)&WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids,
          WPP_pszIndent,
          v3);
        goto LABEL_90;
      }
      goto LABEL_90;
    }
    if ( !SetupDiGetDevicePropertyW(
            v14,
            &DeviceInfoData,
            &DEVPKEY_Device_FriendlyName,
            &PropertyType,
            0,
            0,
            &PropertyBufferSize,
            0) )
    {
      v41 = GetLastError();
      v3 = 0;
      if ( v41 != 122 )
        v3 = v41;
      if ( v3 )
      {
        WppTraceIndent(0, 2);
        v39 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control[28] & 1) != 0
          && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
        {
          v40 = 112;
          goto LABEL_68;
        }
LABEL_90:
        v4 = Context;
        goto LABEL_91;
      }
      LOBYTE(v3) = 0;
    }
    v18 = HeapAlloc(g_hHeap, 8u, PropertyBufferSize);
    if ( v18 )
    {
      if ( SetupDiGetDevicePropertyW(
             v14,
             &DeviceInfoData,
             &DEVPKEY_Device_FriendlyName,
             &PropertyType,
             (PBYTE)v18,
             PropertyBufferSize,
             &PropertyBufferSize,
             0) )
      {
        do
          ++v13;
        while ( *(_WORD *)(i + 2 * v13) );
        v52.Reserved = 0;
        v52.Size = 2 * v13 + 2;
        v55 = 0;
        v54 = PropertyBufferSize;
        v52.Ptr = i;
        v53 = v18;
        I_ScPnPEvtLogWrite(&EVENT_PNP_SUCCESS, v43, &v52);
      }
      else
      {
        WppTraceIndent(0, 2);
        LOBYTE(v3) = GetLastError();
        if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control[28] & 1) != 0
          && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
        {
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            114,
            (unsigned int)&WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids,
            v44,
            v3);
        }
      }
    }
    else
    {
      WppTraceIndent(v42, 2);
      LOBYTE(v3) = 8;
      if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control[28] & 1) != 0
        && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          113,
          &WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids,
          WPP_pszIndent);
      }
    }
    goto LABEL_90;
  }
  v9 = 1;
LABEL_95:
  if ( *v4 )
    HeapFree(g_hHeap, 0, *v4);
  HeapFree(g_hHeap, 0, v4);
  if ( v9 )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)g_pScPnPState + 544));
LABEL_99:
  WppTraceIndent((__int64)v8, 1);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      115,
      (unsigned int)&WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids,
      WPP_pszIndent,
      v3);
  }
}

```

## disassembly

```asm
0x18001a5d0  push    rbp
0x18001a5d2  push    rbx
0x18001a5d3  push    rsi
0x18001a5d4  push    rdi
0x18001a5d5  push    r12
0x18001a5d7  push    r13
0x18001a5d9  push    r14
0x18001a5db  push    r15
0x18001a5dd  lea     rbp, [rsp-1Fh]
0x18001a5e2  sub     rsp, 0C8h
0x18001a5e9  mov     rax, cs:__security_cookie
0x18001a5f0  xor     rax, rsp
0x18001a5f3  mov     [rbp+57h+var_48], rax
0x18001a5f7  xor     ebx, ebx
0x18001a5f9  mov     [rbp+57h+var_C0], rdx
0x18001a5fd  xorps   xmm0, xmm0
0x18001a600  mov     [rbp+57h+pulLen], ebx
0x18001a603  xorps   xmm1, xmm1
0x18001a606  mov     [rbp+57h+PropertyBufferSize], ebx
0x18001a609  mov     rdi, rdx
0x18001a60c  mov     [rbp+57h+pdnDevInst], ebx
0x18001a60f  xor     edx, edx
0x18001a611  mov     [rbp+57h+PropertyType], ebx
0x18001a614  movups  xmmword ptr [rbp+57h+DeviceInterfaceData.cbSize], xmm0
0x18001a618  movups  xmmword ptr [rbp+57h+DeviceInterfaceData.InterfaceClassGuid.Data4+4], xmm0
0x18001a61c  movups  xmmword ptr [rbp+57h+var_A8.cbSize], xmm1
0x18001a620  movups  xmmword ptr [rbp+57h+var_A8.ClassGuid.Data4+4], xmm1
0x18001a624  call    WppTraceIndent
0x18001a629  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a630  lea     r12, WPP_GLOBAL_Control
0x18001a637  cmp     rcx, r12
0x18001a63a  jz      short loc_18001A662
0x18001a63c  test    byte ptr [rcx+1Ch], 2
0x18001a640  jz      short loc_18001A662
0x18001a642  cmp     byte ptr [rcx+19h], 5
0x18001a646  jb      short loc_18001A662
0x18001a648  mov     r9, cs:WPP_pszIndent
0x18001a64f  lea     edx, [rbx+65h]
0x18001a652  mov     rcx, [rcx+10h]
0x18001a656  lea     r8, WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids
0x18001a65d  call    WPP_SF_s
0x18001a662  test    rdi, rdi
0x18001a665  jnz     short loc_18001A6B5
0x18001a667  lea     edx, [rdi+2]
0x18001a66a  call    WppTraceIndent
0x18001a66f  mov     ebx, 80100004h
0x18001a674  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a67b  cmp     rcx, r12
0x18001a67e  jz      loc_18001AD63
0x18001a684  test    byte ptr [rcx+1Ch], 1
0x18001a688  jz      loc_18001AD63
0x18001a68e  cmp     byte ptr [rcx+19h], 2
0x18001a692  jb      loc_18001AD63
0x18001a698  mov     rcx, [rcx+10h]
0x18001a69c  lea     rax, aNullPpnphandle; "NULL != pPnpHandler"
0x18001a6a3  lea     edx, [rdi+66h]
0x18001a6a6  mov     [rsp+100h+RequiredSize], rax
0x18001a6ab  call    WPP_SF_ss
0x18001a6b0  jmp     loc_18001AD63
0x18001a6b5  cmp     [rdi], rbx
0x18001a6b8  jnz     short loc_18001A70F
0x18001a6ba  mov     edx, 2
0x18001a6bf  mov     r15d, ebx
0x18001a6c2  call    WppTraceIndent
0x18001a6c7  mov     ebx, 80100004h
0x18001a6cc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a6d3  cmp     rcx, r12
0x18001a6d6  jz      loc_18001AD21
0x18001a6dc  test    byte ptr [rcx+1Ch], 1
0x18001a6e0  jz      loc_18001AD21
0x18001a6e6  cmp     byte ptr [rcx+19h], 2
0x18001a6ea  jb      loc_18001AD21
0x18001a6f0  mov     rcx, [rcx+10h]
0x18001a6f4  lea     rax, aNullPpnphandle_1; "NULL != pPnpHandler->pwszSmartCardDevic"...
0x18001a6fb  mov     edx, 67h ; 'g'
0x18001a700  mov     [rsp+100h+RequiredSize], rax
0x18001a705  call    WPP_SF_ss
0x18001a70a  jmp     loc_18001AD21
0x18001a70f  mov     rcx, cs:g_pScPnPState
0x18001a716  add     rcx, 220h; lpCriticalSection
0x18001a71d  call    cs:__imp_EnterCriticalSection
0x18001a723  mov     rcx, cs:g_pScPnPState
0x18001a72a  cmp     [rcx+258h], ebx
0x18001a730  jz      loc_18001ADC5
0x18001a736  add     rcx, 220h; lpCriticalSection
0x18001a73d  call    cs:__imp_LeaveCriticalSection
0x18001a743  mov     r9d, 12h; Flags
0x18001a749  lea     rcx, GUID_DEVINTERFACE_SMARTCARD; ClassGuid
0x18001a750  xor     r8d, r8d; hwndParent
0x18001a753  xor     edx, edx; Enumerator
0x18001a755  mov     r15d, ebx
0x18001a758  call    cs:__imp_SetupDiGetClassDevsW
0x18001a75e  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001a762  mov     r13, rax
0x18001a765  cmp     rax, rsi
0x18001a768  jnz     short loc_18001A7C1
0x18001a76a  call    cs:__imp_GetLastError
0x18001a770  lea     edx, [rsi+3]
0x18001a773  mov     ebx, eax
0x18001a775  call    WppTraceIndent
0x18001a77a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a781  cmp     rcx, r12
0x18001a784  jz      loc_18001AD21
0x18001a78a  test    byte ptr [rcx+1Ch], 1
0x18001a78e  jz      loc_18001AD21
0x18001a794  cmp     byte ptr [rcx+19h], 2
0x18001a798  jb      loc_18001AD21
0x18001a79e  mov     r9, cs:WPP_pszIndent
0x18001a7a5  lea     edx, [rsi+69h]
0x18001a7a8  mov     rcx, [rcx+10h]
0x18001a7ac  lea     r8, WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids
0x18001a7b3  mov     dword ptr [rsp+100h+RequiredSize], ebx
0x18001a7b7  call    WPP_SF_sD
0x18001a7bc  jmp     loc_18001AD21
0x18001a7c1  mov     rdx, [rdi]; DevicePath
0x18001a7c4  lea     r9, [rbp+57h+DeviceInterfaceData]; DeviceInterfaceData
0x18001a7c8  xor     r8d, r8d; OpenFlags
0x18001a7cb  mov     [rbp+57h+DeviceInterfaceData.cbSize], 20h ; ' '
0x18001a7d2  mov     rcx, r13; DeviceInfoSet
0x18001a7d5  mov     r12, rbx
0x18001a7d8  mov     r14, rbx
0x18001a7db  call    cs:__imp_SetupDiOpenDeviceInterfaceW
0x18001a7e1  test    eax, eax
0x18001a7e3  jnz     short loc_18001A83E
0x18001a7e5  lea     edx, [rax+2]
0x18001a7e8  call    WppTraceIndent
0x18001a7ed  call    cs:__imp_GetLastError
0x18001a7f3  mov     ebx, eax
0x18001a7f5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a7fc  lea     rax, WPP_GLOBAL_Control
0x18001a803  cmp     rcx, rax
0x18001a806  jz      loc_18001ACE3
0x18001a80c  test    byte ptr [rcx+1Ch], 1
0x18001a810  jz      loc_18001ACE3
0x18001a816  cmp     byte ptr [rcx+19h], 2
0x18001a81a  jb      loc_18001ACE3
0x18001a820  mov     rcx, [rcx+10h]
0x18001a824  lea     r8, WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids
0x18001a82b  mov     edx, 69h ; 'i'
0x18001a830  mov     dword ptr [rsp+100h+RequiredSize], ebx
0x18001a834  call    WPP_SF_sd
0x18001a839  jmp     loc_18001ACE3
0x18001a83e  lea     rax, [rbp+57h+var_A8]
0x18001a842  mov     [rbp+57h+var_A8.cbSize], 20h ; ' '
0x18001a849  mov     [rsp+100h+DeviceInfoData], rax; DeviceInfoData
0x18001a84e  lea     rdx, [rbp+57h+DeviceInterfaceData]; DeviceInterfaceData
0x18001a852  xor     r9d, r9d; DeviceInterfaceDetailDataSize
0x18001a855  mov     [rsp+100h+RequiredSize], rbx; RequiredSize
0x18001a85a  xor     r8d, r8d; DeviceInterfaceDetailData
0x18001a85d  mov     rcx, r13; DeviceInfoSet
0x18001a860  call    cs:__imp_SetupDiGetDeviceInterfaceDetailW
0x18001a866  test    eax, eax
0x18001a868  jnz     short loc_18001A8D4
0x18001a86a  call    cs:__imp_GetLastError
0x18001a870  cmp     eax, 7Ah ; 'z'
0x18001a873  cmovnz  ebx, eax
0x18001a876  test    ebx, ebx
0x18001a878  jz      short loc_18001A8D4
0x18001a87a  mov     edx, 2
0x18001a87f  call    WppTraceIndent
0x18001a884  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a88b  lea     rax, WPP_GLOBAL_Control
0x18001a892  cmp     rcx, rax
0x18001a895  jz      loc_18001ACE3
0x18001a89b  test    byte ptr [rcx+1Ch], 1
0x18001a89f  jz      loc_18001ACE3
0x18001a8a5  cmp     byte ptr [rcx+19h], 2
0x18001a8a9  jb      loc_18001ACE3
0x18001a8af  mov     edx, 6Ah ; 'j'
0x18001a8b4  mov     r9, cs:WPP_pszIndent
0x18001a8bb  lea     r8, WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids
0x18001a8c2  mov     rcx, [rcx+10h]
0x18001a8c6  mov     dword ptr [rsp+100h+RequiredSize], ebx
0x18001a8ca  call    WPP_SF_sD
0x18001a8cf  jmp     loc_18001ACE3
0x18001a8d4  mov     edx, [rbp+57h+var_A8.DevInst]; dnDevInst
0x18001a8d7  lea     rcx, [rbp+57h+pdnDevInst]; pdnDevInst
0x18001a8db  xor     r8d, r8d; ulFlags
0x18001a8de  call    cs:__imp_CM_Get_Parent
0x18001a8e4  mov     ebx, eax
0x18001a8e6  test    eax, eax
0x18001a8e8  jz      short loc_18001A926
0x18001a8ea  mov     edx, 2
0x18001a8ef  call    WppTraceIndent
0x18001a8f4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a8fb  lea     rax, WPP_GLOBAL_Control
0x18001a902  cmp     rcx, rax
0x18001a905  jz      loc_18001ACE3
0x18001a90b  test    byte ptr [rcx+1Ch], 1
0x18001a90f  jz      loc_18001ACE3
0x18001a915  cmp     byte ptr [rcx+19h], 2
0x18001a919  jb      loc_18001ACE3
0x18001a91f  mov     edx, 6Bh ; 'k'
0x18001a924  jmp     short loc_18001A8B4
0x18001a926  mov     edx, [rbp+57h+pdnDevInst]; dnDevInst
0x18001a929  lea     rcx, [rbp+57h+pulLen]; pulLen
0x18001a92d  xor     r8d, r8d; ulFlags
0x18001a930  call    cs:__imp_CM_Get_Device_ID_Size
0x18001a936  mov     ebx, eax
0x18001a938  test    eax, eax
0x18001a93a  jz      short loc_18001A97B
0x18001a93c  mov     edx, 2
0x18001a941  call    WppTraceIndent
0x18001a946  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a94d  lea     rax, WPP_GLOBAL_Control
0x18001a954  cmp     rcx, rax
0x18001a957  jz      loc_18001ACE3
0x18001a95d  test    byte ptr [rcx+1Ch], 1
0x18001a961  jz      loc_18001ACE3
0x18001a967  cmp     byte ptr [rcx+19h], 2
0x18001a96b  jb      loc_18001ACE3
0x18001a971  mov     edx, 6Ch ; 'l'
0x18001a976  jmp     loc_18001A8B4
0x18001a97b  mov     r8d, [rbp+57h+pulLen]
0x18001a97f  mov     ebx, 8
0x18001a984  mov     rcx, cs:g_hHeap; hHeap
0x18001a98b  inc     r8d
0x18001a98e  add     r8, r8; dwBytes
0x18001a991  mov     edx, ebx; dwFlags
0x18001a993  call    cs:__imp_HeapAlloc
0x18001a999  mov     r12, rax
0x18001a99c  test    rax, rax
0x18001a99f  jnz     short loc_18001A9F3
0x18001a9a1  lea     edx, [rbx-6]
0x18001a9a4  call    WppTraceIndent
0x18001a9a9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a9b0  lea     rax, WPP_GLOBAL_Control
0x18001a9b7  cmp     rcx, rax
0x18001a9ba  jz      loc_18001ACE3
0x18001a9c0  test    byte ptr [rcx+1Ch], 1
0x18001a9c4  jz      loc_18001ACE3
0x18001a9ca  cmp     byte ptr [rcx+19h], 2
0x18001a9ce  jb      loc_18001ACE3
0x18001a9d4  mov     r9, cs:WPP_pszIndent
0x18001a9db  lea     edx, [rbx+65h]
0x18001a9de  mov     rcx, [rcx+10h]
0x18001a9e2  lea     r8, WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids
0x18001a9e9  call    WPP_SF_s
0x18001a9ee  jmp     loc_18001ACE3
0x18001a9f3  mov     r8d, [rbp+57h+pulLen]; BufferLen
0x18001a9f7  xor     r9d, r9d; ulFlags
0x18001a9fa  mov     ecx, [rbp+57h+pdnDevInst]; dnDevInst
0x18001a9fd  mov     rdx, r12; Buffer
0x18001aa00  call    cs:__imp_CM_Get_Device_IDW
0x18001aa06  mov     ebx, eax
0x18001aa08  test    eax, eax
0x18001aa0a  jz      short loc_18001AA4B
0x18001aa0c  mov     edx, 2
0x18001aa11  call    WppTraceIndent
0x18001aa16  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aa1d  lea     rax, WPP_GLOBAL_Control
0x18001aa24  cmp     rcx, rax
0x18001aa27  jz      loc_18001ACE3
0x18001aa2d  test    byte ptr [rcx+1Ch], 1
0x18001aa31  jz      loc_18001ACE3
0x18001aa37  cmp     byte ptr [rcx+19h], 2
0x18001aa3b  jb      loc_18001ACE3
0x18001aa41  mov     edx, 6Eh ; 'n'
0x18001aa46  jmp     loc_18001A8B4
0x18001aa4b  mov     rcx, cs:g_pScPnPState
0x18001aa52  add     rcx, 220h; lpCriticalSection
0x18001aa59  call    cs:__imp_EnterCriticalSection
0x18001aa5f  mov     r9, cs:g_pScPnPState
0x18001aa66  mov     r15d, 1
0x18001aa6c  xor     r10d, r10d
0x18001aa6f  mov     rdi, [r9+250h]
0x18001aa76  test    rdi, rdi
0x18001aa79  jz      loc_18001ACDF
0x18001aa7f  cmp     [rdi+0CCh], r15d
0x18001aa86  jnz     short loc_18001AAAD
0x18001aa88  mov     rax, [rdi+0D0h]
0x18001aa8f  mov     r8, r12
0x18001aa92  sub     r8, rax
0x18001aa95  movzx   edx, word ptr [rax]
0x18001aa98  movzx   ecx, word ptr [rax+r8]
0x18001aa9d  sub     edx, ecx
0x18001aa9f  jnz     short loc_18001AAA9
0x18001aaa1  add     rax, 2
0x18001aaa5  test    ecx, ecx
0x18001aaa7  jnz     short loc_18001AA95
0x18001aaa9  test    edx, edx
0x18001aaab  jz      short loc_18001AAB6
0x18001aaad  mov     rdi, [rdi+0F0h]
0x18001aab4  jmp     short loc_18001AA76
0x18001aab6  dec     dword ptr [r9+258h]
0x18001aabd  mov     rcx, rdi; lpInBuffer
0x18001aac0  mov     [rdi+0CCh], r10d
0x18001aac7  call    I_ScPnPPulseReader
0x18001aacc  xor     ecx, ecx
0x18001aace  mov     ebx, eax
0x18001aad0  test    eax, eax
0x18001aad2  jz      short loc_18001AB2C
0x18001aad4  lea     edx, [rcx+2]
0x18001aad7  call    WppTraceIndent
0x18001aadc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aae3  lea     rax, WPP_GLOBAL_Control
0x18001aaea  cmp     rcx, rax
0x18001aaed  jz      loc_18001ACDF
0x18001aaf3  test    [rcx+1Ch], r15b
0x18001aaf7  jz      loc_18001ACDF
  ... truncated ...
```
