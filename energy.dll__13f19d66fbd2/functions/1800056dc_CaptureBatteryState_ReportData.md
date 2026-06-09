# CaptureBatteryState(ReportData &)

- ea: `0x1800056dc`
- end: `0x1800058de`
- name: `?CaptureBatteryState@@YAJAEAUReportData@@@Z`
- size: `514`
- prototype: `__int64 __fastcall(struct ReportData *)`
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180005b40`
- `0x18004fddc`
- `0x180056040`
- `0x1800778f0`

## callees

- `0x1800056dc`
- `0x1800058e4`
- `0x180008740`
- `0x18004ca90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180005743`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180005743`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800058a3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800058a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800058bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800058bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005844`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005844`
- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQuery` at `0x180005833`
- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQuery` at `0x180005833`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x1800058b3`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x1800058b3`

## pseudocode

```c
__int64 __fastcall CaptureBatteryState(struct ReportData *a1)
{
  int v2; // ebx
  __int64 v3; // r9
  __int64 v5; // rdx
  __int64 v6; // r8
  signed int LastError; // eax
  char v8; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v9; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE hObject[3]; // [rsp+60h] [rbp-A0h] BYREF
  DEVPROPGUID fmtid; // [rsp+78h] [rbp-88h] BYREF
  __int128 pid; // [rsp+88h] [rbp-78h]
  __int64 v13; // [rsp+A0h] [rbp-60h] BYREF
  DEVPROPKEY v14; // [rsp+A8h] [rbp-58h]
  int v15; // [rsp+BCh] [rbp-44h]
  __int64 v16; // [rsp+C0h] [rbp-40h]
  int v17; // [rsp+C8h] [rbp-38h]
  int v18; // [rsp+CCh] [rbp-34h]
  GUID *v19; // [rsp+D0h] [rbp-30h]
  __int64 v20; // [rsp+D8h] [rbp-28h]
  DEVPROPKEY v21; // [rsp+E0h] [rbp-20h]
  int v22; // [rsp+F4h] [rbp-Ch]
  __int64 v23; // [rsp+F8h] [rbp-8h]
  int v24; // [rsp+100h] [rbp+0h]
  int v25; // [rsp+104h] [rbp+4h]
  char *v26; // [rsp+108h] [rbp+8h]

  hObject[2] = a1;
  v9 = 0;
  hObject[1] = 0;
  v8 = -1;
  fmtid = 0;
  pid = 0;
  hObject[0] = CreateEventW(0, 1, 0, 0);
  if ( hObject[0] )
  {
    v13 = 2;
    v16 = 0;
    v23 = 0;
    v14 = DEVPKEY_DeviceInterface_ClassGuid;
    v20 = 2;
    v19 = &GUID_DEVICE_BATTERY;
    v21 = DEVPKEY_DeviceInterface_Enabled;
    v26 = &v8;
    pid = DEVPKEY_Device_InstanceId.pid;
    v15 = 0;
    v17 = 13;
    v18 = 16;
    v22 = 0;
    v24 = 17;
    v25 = 1;
    fmtid = DEVPKEY_Device_InstanceId.fmtid;
    v2 = DevCreateObjectQuery(1, 0, 1, &fmtid, 2, &v13, CaptureBatteryStateCallback, hObject, &v9);
    if ( v2 >= 0 )
    {
      WaitForSingleObject(hObject[0], 0xFFFFFFFF);
      if ( !v9 )
        MicrosoftTelemetryAssertTriggeredNoArgs(0, v5, v6);
      DevCloseObjectQuery();
    }
    CloseHandle(hObject[0]);
    LOBYTE(v3) = 0;
    std::_Sort_unchecked<BatteryInfo *,std::less<void>>(
      *((_QWORD *)a1 + 31),
      *((_QWORD *)a1 + 32),
      0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)a1 + 32) - *((_QWORD *)a1 + 31)) >> 6),
      v3);
  }
  else
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800056dc  mov     [rsp-8+arg_8], rbx
0x1800056e1  mov     [rsp-8+arg_10], rdi
0x1800056e6  push    rbp
0x1800056e7  lea     rbp, [rsp-20h]
0x1800056ec  sub     rsp, 120h
0x1800056f3  mov     rax, cs:__security_cookie
0x1800056fa  xor     rax, rsp
0x1800056fd  mov     [rbp+20h+var_10], rax
0x180005701  xorps   xmm0, xmm0
0x180005704  mov     [rsp+120h+var_B0], rcx
0x180005709  xor     r9d, r9d; lpName
0x18000570c  mov     [rsp+120h+var_C8], 0
0x180005715  mov     rdi, rcx
0x180005718  mov     [rsp+120h+hObject], 0
0x180005721  xor     r8d, r8d; bInitialState
0x180005724  mov     [rsp+120h+var_B8], 0
0x18000572d  xor     ecx, ecx; lpEventAttributes
0x18000572f  mov     [rsp+120h+var_D0], 0FFh
0x180005734  lea     ebx, [r9+1]
0x180005738  mov     edx, ebx; bManualReset
0x18000573a  movups  [rsp+120h+var_A8], xmm0
0x18000573f  movups  [rbp+20h+var_98], xmm0
0x180005743  call    cs:__imp_CreateEventW
0x180005749  mov     [rsp+120h+hObject], rax
0x18000574e  test    rax, rax
0x180005751  jz      loc_1800058BB
0x180005757  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceInterface_ClassGuid.fmtid.Data1
0x18000575e  xor     eax, eax
0x180005760  mov     [rbp+20h+var_80], 2
0x180005768  mov     [rbp+20h+var_60], rax
0x18000576c  lea     edx, [rbx+1]
0x18000576f  mov     [rbp+20h+var_28], rax
0x180005773  lea     r9, [rsp+120h+var_A8]
0x180005778  mov     eax, cs:DEVPKEY_DeviceInterface_ClassGuid.pid
0x18000577e  mov     r8d, ebx
0x180005781  mov     [rbp+20h+var_68], eax
0x180005784  mov     ecx, ebx
0x180005786  lea     rax, GUID_DEVICE_BATTERY
0x18000578d  mov     [rbp+20h+var_48], 2
0x180005795  mov     [rbp+20h+var_50], rax
0x180005799  mov     eax, cs:DEVPKEY_DeviceInterface_Enabled.pid
0x18000579f  mov     [rbp+20h+var_30], eax
0x1800057a2  lea     rax, [rsp+120h+var_D0]
0x1800057a7  mov     [rbp+20h+var_18], rax
0x1800057ab  mov     eax, cs:DEVPKEY_Device_InstanceId.pid
0x1800057b1  mov     dword ptr [rbp+20h+var_98], eax
0x1800057b4  lea     rax, [rsp+120h+var_C8]
0x1800057b9  mov     [rsp+120h+var_E0], rax
0x1800057be  lea     rax, [rsp+120h+hObject]
0x1800057c3  mov     [rsp+120h+var_E8], rax
0x1800057c8  lea     rax, ?CaptureBatteryStateCallback@@YAXPEAUHDEVQUERY__@@PEAXPEBU_DEV_QUERY_RESULT_ACTION_DATA@@@Z; CaptureBatteryStateCallback(HDEVQUERY__ *,void *,_DEV_QUERY_RESULT_ACTION_DATA const *)
0x1800057cf  mov     [rsp+120h+var_F0], rax
0x1800057d4  lea     rax, [rbp+20h+var_80]
0x1800057d8  movups  [rbp+20h+var_78], xmm0
0x1800057dc  mov     [rsp+120h+var_F8], rax
0x1800057e1  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceInterface_Enabled.fmtid.Data1
0x1800057e8  mov     [rsp+120h+var_100], edx
0x1800057ec  xor     edx, edx
0x1800057ee  mov     [rbp+20h+var_64], 0
0x1800057f5  movaps  [rbp+20h+var_40], xmm0
0x1800057f9  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_InstanceId.fmtid.Data1
0x180005800  mov     [rbp+20h+var_58], 0Dh
0x180005807  mov     [rbp+20h+var_54], 10h
0x18000580e  mov     [rbp+20h+var_2C], 0
0x180005815  mov     [rbp+20h+var_20], 11h
0x18000581c  mov     [rbp+20h+var_1C], ebx
0x18000581f  mov     qword ptr [rbp+20h+var_98+8], 0
0x180005827  movups  [rsp+120h+var_A8], xmm0
0x18000582c  mov     dword ptr [rbp+20h+var_98+4], 0
0x180005833  call    cs:__imp_DevCreateObjectQuery
0x180005839  mov     ebx, eax
0x18000583b  test    eax, eax
0x18000583d  jns     short loc_18000589B
0x18000583f  mov     rcx, [rsp+120h+hObject]; hObject
0x180005844  call    cs:__imp_CloseHandle
0x18000584a  mov     rdx, [rdi+100h]
0x180005851  mov     rax, 0AAAAAAAAAAAAAAABh
0x18000585b  mov     rcx, [rdi+0F8h]
0x180005862  mov     r8, rdx
0x180005865  sub     r8, rcx
0x180005868  xor     r9b, r9b
0x18000586b  sar     r8, 6
0x18000586f  imul    r8, rax
0x180005873  call    ??$_Sort_unchecked@PEAUBatteryInfo@@U?$less@X@std@@@std@@YAXPEAUBatteryInfo@@0_JU?$less@X@0@@Z; std::_Sort_unchecked<BatteryInfo *,std::less<void>>(BatteryInfo *,BatteryInfo *,__int64,std::less<void>)
0x180005878  mov     eax, ebx
0x18000587a  mov     rcx, [rbp+20h+var_10]
0x18000587e  xor     rcx, rsp; StackCookie
0x180005881  call    __security_check_cookie
0x180005886  lea     r11, [rsp+120h+var_s0]
0x18000588e  mov     rbx, [r11+18h]
0x180005892  mov     rdi, [r11+20h]
0x180005896  mov     rsp, r11
0x180005899  pop     rbp
0x18000589a  retn
0x18000589b  mov     rcx, [rsp+120h+hObject]; hHandle
0x1800058a0  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800058a3  call    cs:__imp_WaitForSingleObject
0x1800058a9  mov     rcx, [rsp+120h+var_C8]
0x1800058ae  test    rcx, rcx
0x1800058b1  jz      short loc_1800058D2
0x1800058b3  call    cs:__imp_DevCloseObjectQuery
0x1800058b9  jmp     short loc_18000583F
0x1800058bb  call    cs:__imp_GetLastError
0x1800058c1  mov     ebx, eax
0x1800058c3  test    eax, eax
0x1800058c5  jle     short loc_180005878
0x1800058c7  movzx   ebx, ax
0x1800058ca  or      ebx, 80070000h
0x1800058d0  jmp     short loc_180005878
0x1800058d2  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800058d7  mov     rcx, [rsp+120h+var_C8]
0x1800058dc  jmp     short loc_1800058B3
```
