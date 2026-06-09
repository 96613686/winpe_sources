# WaitForDeviceConfigurationIfNeeded(void *,_SP_DEVINFO_DATA *,ushort *)

- ea: `0x180016028`
- end: `0x1800162bf`
- name: `?WaitForDeviceConfigurationIfNeeded@@YAKPEAXPEAU_SP_DEVINFO_DATA@@PEAG@Z`
- size: `663`
- prototype: `unsigned int __fastcall(HDEVINFO DeviceInfoSet, PSP_DEVINFO_DATA DeviceInfoData, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x180013804`

## callees

- `0x180002830`
- `0x180002898`
- `0x18000d57c`
- `0x180016028`
- `0x180036664`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800160ae`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800160ae`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001613b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001613b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016166`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800161bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016210`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016166`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800161bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016210`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800161b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800161b3`
- `SETUPAPI!SetupDiSetDevicePropertyW` at `0x180016206`
- `SETUPAPI!SetupDiSetDevicePropertyW` at `0x180016206`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x180016079`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x180016079`
- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQueryFromId` at `0x180016129`
- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQueryFromId` at `0x180016129`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x180016189`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x180016189`

## string_xrefs

- `0x18001614c`: `Device installation query timed out!`
- `0x180016158`: `WaitForDeviceConfigurationIfNeeded`
- `0x180016176`: `WaitForDeviceConfigurationIfNeeded`
- `0x1800161a2`: `WaitForDeviceConfigurationIfNeeded`
- `0x180016220`: `WaitForDeviceConfigurationIfNeeded`
- `0x18001619b`: `DevCreateObjectQueryFromId failed! Error %d`
- `0x1800161c1`: `Failed to create hDeviceInstalledEvent event! Error %d`
- `0x180016216`: `Failed to set PKEY_Printer_DeviceInstallState: %d`

## pseudocode

```c
__int64 __fastcall WaitForDeviceConfigurationIfNeeded(
        HDEVINFO DeviceInfoSet,
        PSP_DEVINFO_DATA DeviceInfoData,
        unsigned __int16 *a3)
{
  __int64 v6; // rbx
  HANDLE EventW; // rdi
  int ObjectQueryFromId; // eax
  DWORD v9; // eax
  DWORD LastError; // eax
  unsigned __int16 *v11; // rdx
  DEVPROPTYPE v13; // [rsp+50h] [rbp-28h] BYREF
  __int64 v14; // [rsp+58h] [rbp-20h]
  int PropertyBuffer; // [rsp+98h] [rbp+20h] BYREF

  v13 = 0;
  LODWORD(v6) = 0;
  PropertyBuffer = 0;
  v14 = 0;
  if ( !SetupDiGetDevicePropertyW(
          DeviceInfoSet,
          DeviceInfoData,
          &stru_180041470,
          &v13,
          (PBYTE)&PropertyBuffer,
          4u,
          0,
          0)
    || v13 != 7
    || PropertyBuffer != 1 )
  {
    if ( PropertyBuffer == 2 )
      return (unsigned int)v6;
    PropertyBuffer = 2;
    if ( SetupDiSetDevicePropertyW(
           DeviceInfoSet,
           DeviceInfoData,
           &stru_180041470,
           7u,
           (const PBYTE)&PropertyBuffer,
           4u,
           0) )
    {
      return (unsigned int)v6;
    }
    LastError = GetLastError();
    v11 = L"Failed to set PKEY_Printer_DeviceInstallState: %d";
LABEL_18:
    LODWORD(v6) = LastError;
    ClassInstallerTelemetry::WriteDbgTraceError("WaitForDeviceConfigurationIfNeeded", v11, LastError);
    return (unsigned int)v6;
  }
  EventW = CreateEventW(0, 0, 0, 0);
  if ( !EventW )
  {
    LastError = GetLastError();
    v11 = L"Failed to create hDeviceInstalledEvent event! Error %d";
    goto LABEL_18;
  }
  if ( dword_180056040 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_180056040);
    if ( dword_180056040 == -1 )
    {
      *(DEVPROPKEY *)byte_180055DB0 = DEVPKEY_Device_InstanceId;
      dword_180055DC4 = 0;
      qword_180055DC8 = 0;
      xmmword_180055DD0 = (__int128)stru_180041470.fmtid;
      dword_180055DE0 = 7;
      dword_180055DE4 = 0;
      qword_180055DE8 = 0;
      Init_thread_footer(&dword_180056040);
    }
  }
  ObjectQueryFromId = DevCreateObjectQueryFromId(3, a3, 1);
  if ( ObjectQueryFromId < 0 )
  {
    v6 = (unsigned int)StatusFromHResult((unsigned int)ObjectQueryFromId);
    ClassInstallerTelemetry::WriteDbgTraceError(
      "WaitForDeviceConfigurationIfNeeded",
      L"DevCreateObjectQueryFromId failed! Error %d",
      v6);
  }
  else
  {
    v9 = WaitForSingleObject(EventW, 0x2BF20u);
    if ( v9 )
    {
      if ( v9 == 258 )
      {
        LODWORD(v6) = 1460;
        ClassInstallerTelemetry::WriteDbgTraceError(
          "WaitForDeviceConfigurationIfNeeded",
          L"Device installation query timed out!");
      }
      else
      {
        v6 = GetLastError();
        ClassInstallerTelemetry::WriteDbgTraceError(
          "WaitForDeviceConfigurationIfNeeded",
          L"WaitForSingleObject failed! Error %d",
          v6);
      }
    }
    DevCloseObjectQuery(v14);
  }
  CloseHandle(EventW);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180016028  mov     r11, rsp
0x18001602b  mov     [r11+8], rbx
0x18001602f  mov     [r11+10h], rbp
0x180016033  push    rsi
0x180016034  push    rdi
0x180016035  push    r14
0x180016037  sub     rsp, 60h
0x18001603b  xor     r14d, r14d
0x18001603e  lea     rax, [r11+20h]
0x180016042  mov     [r11-40h], r14d
0x180016046  lea     r9, [r11-28h]; PropertyType
0x18001604a  mov     [r11-48h], r14
0x18001604e  mov     rbp, r8
0x180016051  mov     [rsp+78h+PropertyBufferSize], 4; PropertyBufferSize
0x180016059  lea     r8, stru_180041470; PropertyKey
0x180016060  mov     [r11-58h], rax
0x180016064  mov     rdi, rdx
0x180016067  mov     rsi, rcx
0x18001606a  mov     [r11-28h], r14d
0x18001606e  mov     ebx, r14d
0x180016071  mov     [r11+20h], r14d
0x180016075  mov     [r11-20h], r14
0x180016079  call    cs:__imp_SetupDiGetDevicePropertyW
0x18001607f  lea     r9d, [r14+7]; PropertyType
0x180016083  test    eax, eax
0x180016085  jz      loc_1800161CA
0x18001608b  cmp     [rsp+78h+var_28], r9d
0x180016090  jnz     loc_1800161CA
0x180016096  cmp     [rsp+78h+arg_18], 1
0x18001609e  jnz     loc_1800161CA
0x1800160a4  xor     r9d, r9d; lpName
0x1800160a7  xor     r8d, r8d; bInitialState
0x1800160aa  xor     edx, edx; bManualReset
0x1800160ac  xor     ecx, ecx; lpEventAttributes
0x1800160ae  call    cs:__imp_CreateEventW
0x1800160b4  mov     rdi, rax
0x1800160b7  test    rax, rax
0x1800160ba  jz      loc_1800161BB
0x1800160c0  mov     ecx, cs:_tls_index
0x1800160c6  mov     rax, gs:58h
0x1800160cf  mov     edx, 4
0x1800160d4  mov     rax, [rax+rcx*8]
0x1800160d8  mov     eax, [rdx+rax]
0x1800160db  cmp     cs:dword_180056040, eax
0x1800160e1  jg      loc_180016245
0x1800160e7  mov     r9d, 2
0x1800160ed  lea     rax, [rsp+78h+var_20]
0x1800160f2  mov     [rsp+78h+var_30], rax
0x1800160f7  mov     rdx, rbp
0x1800160fa  mov     [rsp+78h+var_38], rdi
0x1800160ff  lea     rax, s_DeviceQueryCallback
0x180016106  mov     [rsp+78h+var_40], rax
0x18001610b  lea     rax, byte_180055DB0
0x180016112  mov     qword ptr [rsp+78h+Flags], r14
0x180016117  lea     r8d, [r9-1]
0x18001611b  mov     [rsp+78h+PropertyBufferSize], r14d
0x180016120  lea     ecx, [r9+1]
0x180016124  mov     [rsp+78h+PropertyBuffer], rax
0x180016129  call    cs:__imp_DevCreateObjectQueryFromId
0x18001612f  test    eax, eax
0x180016131  js      short loc_180016191
0x180016133  mov     edx, 2BF20h; dwMilliseconds
0x180016138  mov     rcx, rdi; hHandle
0x18001613b  call    cs:__imp_WaitForSingleObject
0x180016141  test    eax, eax
0x180016143  jz      short loc_180016184
0x180016145  cmp     eax, 102h
0x18001614a  jnz     short loc_180016166
0x18001614c  lea     rdx, aDeviceInstalla; "Device installation query timed out!"
0x180016153  mov     ebx, 5B4h
0x180016158  lea     rcx, aWaitfordevicec; "WaitForDeviceConfigurationIfNeeded"
0x18001615f  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180016164  jmp     short loc_180016184
0x180016166  call    cs:__imp_GetLastError
0x18001616c  mov     r8d, eax
0x18001616f  lea     rdx, aWaitforsingleo; "WaitForSingleObject failed! Error %d"
0x180016176  lea     rcx, aWaitfordevicec; "WaitForDeviceConfigurationIfNeeded"
0x18001617d  mov     ebx, eax
0x18001617f  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180016184  mov     rcx, [rsp+78h+var_20]
0x180016189  call    cs:__imp_DevCloseObjectQuery
0x18001618f  jmp     short loc_1800161B0
0x180016191  mov     ecx, eax
0x180016193  call    StatusFromHResult
0x180016198  mov     r8d, eax
0x18001619b  lea     rdx, aDevcreateobjec_0; "DevCreateObjectQueryFromId failed! Erro"...
0x1800161a2  lea     rcx, aWaitfordevicec; "WaitForDeviceConfigurationIfNeeded"
0x1800161a9  mov     ebx, eax
0x1800161ab  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800161b0  mov     rcx, rdi; hObject
0x1800161b3  call    cs:__imp_CloseHandle
0x1800161b9  jmp     short loc_18001622E
0x1800161bb  call    cs:__imp_GetLastError
0x1800161c1  lea     rdx, aFailedToCreate; "Failed to create hDeviceInstalledEvent "...
0x1800161c8  jmp     short loc_18001621D
0x1800161ca  cmp     [rsp+78h+arg_18], 2
0x1800161d2  jz      short loc_18001622E
0x1800161d4  mov     [rsp+78h+Flags], r14d; Flags
0x1800161d9  lea     rax, [rsp+78h+arg_18]
0x1800161e1  mov     [rsp+78h+PropertyBufferSize], 4; PropertyBufferSize
0x1800161e9  lea     r8, stru_180041470; PropertyKey
0x1800161f0  mov     rdx, rdi; DeviceInfoData
0x1800161f3  mov     [rsp+78h+PropertyBuffer], rax; PropertyBuffer
0x1800161f8  mov     rcx, rsi; DeviceInfoSet
0x1800161fb  mov     [rsp+78h+arg_18], 2
0x180016206  call    cs:__imp_SetupDiSetDevicePropertyW
0x18001620c  test    eax, eax
0x18001620e  jnz     short loc_18001622E
0x180016210  call    cs:__imp_GetLastError
0x180016216  lea     rdx, aFailedToSetPke; "Failed to set PKEY_Printer_DeviceInstal"...
0x18001621d  mov     r8d, eax
0x180016220  lea     rcx, aWaitfordevicec; "WaitForDeviceConfigurationIfNeeded"
0x180016227  mov     ebx, eax
0x180016229  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18001622e  lea     r11, [rsp+78h+var_18]
0x180016233  mov     eax, ebx
0x180016235  mov     rbx, [r11+20h]
0x180016239  mov     rbp, [r11+28h]
0x18001623d  mov     rsp, r11
0x180016240  pop     r14
0x180016242  pop     rdi
0x180016243  pop     rsi
0x180016244  retn
0x180016245  lea     rcx, dword_180056040
0x18001624c  call    _Init_thread_header
0x180016251  cmp     cs:dword_180056040, 0FFFFFFFFh
0x180016258  jnz     loc_1800160E7
0x18001625e  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_InstanceId.fmtid.Data1
0x180016265  mov     eax, cs:DEVPKEY_Device_InstanceId.pid
0x18001626b  lea     rcx, dword_180056040
0x180016272  mov     dword ptr cs:byte_180055DB0+10h, eax
0x180016278  mov     eax, cs:stru_180041470.pid
0x18001627e  movaps  xmmword ptr cs:byte_180055DB0, xmm0
0x180016285  movups  xmm0, xmmword ptr cs:stru_180041470.fmtid.Data1
0x18001628c  mov     cs:dword_180055DC4, r14d
0x180016293  mov     cs:qword_180055DC8, r14
0x18001629a  movaps  cs:xmmword_180055DD0, xmm0
0x1800162a1  mov     cs:dword_180055DE0, eax
0x1800162a7  mov     cs:dword_180055DE4, r14d
0x1800162ae  mov     cs:qword_180055DE8, r14
0x1800162b5  call    _Init_thread_footer
0x1800162ba  jmp     loc_1800160E7
```
