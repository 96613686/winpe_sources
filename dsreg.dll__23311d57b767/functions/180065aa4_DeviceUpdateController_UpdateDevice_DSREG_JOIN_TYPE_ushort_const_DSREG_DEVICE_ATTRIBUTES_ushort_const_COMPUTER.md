# DeviceUpdateController::UpdateDevice(_DSREG_JOIN_TYPE,ushort const *,_DSREG_DEVICE_ATTRIBUTES,ushort const *,_COMPUTER_NAME_FORMAT)

- ea: `0x180065aa4`
- end: `0x180065c53`
- name: `?UpdateDevice@DeviceUpdateController@@SAJW4_DSREG_JOIN_TYPE@@PEBGW4_DSREG_DEVICE_ATTRIBUTES@@1W4_COMPUTER_NAME_FORMAT@@@Z`
- size: `431`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180049f50`

## callees

- `0x1800084f4`
- `0x18000bac0`
- `0x180065aa4`
- `0x180065c5c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065af4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065be6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065af4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065be6`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180065ae4`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180065ae4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180065b78`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180065b78`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180065bbc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180065bbc`

## string_xrefs

- `0x180065ab6`: `DeviceUpdateController::UpdateDevice`
- `0x180065b00`: `CreateEventEx`
- `0x180065c22`: `%s: DeviceUpdateController::UpdateDevice callback failed with error code 0x%08x`
- `0x180065c30`: `%s: DeviceUpdateController::UpdateDevice callback succeeded`
- `0x180065c01`: `%s: WaitForSingleObject timed out for DeviceUpdateController::UpdateDevice`
- `0x180065b95`: `%s: WaitForSingleObject returned unexpected wait status 0x%08x for DeviceUpdateController::UpdateDevice`

## pseudocode

```c
__int64 __fastcall DeviceUpdateController::UpdateDevice(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const unsigned __int16 *a4,
        int a5)
{
  int v6; // ebx
  DWORD LastError; // eax
  const wchar_t *v8; // r8
  int updated; // eax
  unsigned int v10; // edi
  DWORD v11; // eax
  HANDLE hHandle[3]; // [rsp+40h] [rbp-18h] BYREF

  v6 = 0;
  hHandle[0] = 0;
  Logger::TraceVerbose((wchar_t *)L"%s started", L"DeviceUpdateController::UpdateDevice");
  hHandle[1] = CreateEventExW(0, 0, 1u, 0x1F0003u);
  if ( !hHandle[1] )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError )
    {
      v8 = L"CreateEventEx";
LABEL_4:
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"DeviceUpdateController::UpdateDevice",
        v8,
        LastError);
      goto LABEL_22;
    }
  }
  updated = DeviceUpdateController::UpdateDevice(1u, 0, 3u, a4, a5, (__int64)SyncDeviceUpdateCallback, (__int64)hHandle);
  v10 = updated;
  if ( updated >= 0 )
  {
    v11 = WaitForSingleObject(hHandle[1], 0xFFFFFFFF);
    if ( v11 )
    {
      if ( v11 == 258 )
      {
        LOWORD(v6) = 1460;
        Logger::TraceError(
          L"%s: WaitForSingleObject timed out for DeviceUpdateController::UpdateDevice",
          L"DeviceUpdateController::UpdateDevice");
      }
      else
      {
        if ( v11 == -1 )
        {
          LastError = GetLastError();
          v6 = LastError;
          if ( !LastError )
            goto LABEL_12;
          v8 = L"WaitForSingleObject";
          goto LABEL_4;
        }
        LOWORD(v6) = 1460;
        Logger::TraceError(
          L"%s: WaitForSingleObject returned unexpected wait status 0x%08x for DeviceUpdateController::UpdateDevice",
          L"DeviceUpdateController::UpdateDevice",
          v11);
      }
LABEL_11:
      v10 = (unsigned __int16)v6 | 0x80070000;
      goto LABEL_12;
    }
    v10 = (unsigned int)hHandle[0];
    if ( SLODWORD(hHandle[0]) >= 0 )
      Logger::TraceVerbose(
        (wchar_t *)L"%s: DeviceUpdateController::UpdateDevice callback succeeded",
        L"DeviceUpdateController::UpdateDevice");
    else
      Logger::TraceError(
        L"%s: DeviceUpdateController::UpdateDevice callback failed with error code 0x%08x",
        L"DeviceUpdateController::UpdateDevice",
        LODWORD(hHandle[0]));
  }
  else
  {
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"DeviceUpdateController::UpdateDevice",
      L"DeviceUpdateController::UpdateDevice",
      (unsigned int)updated);
  }
  if ( !v6 )
    goto LABEL_12;
LABEL_22:
  if ( v6 > 0 )
    goto LABEL_11;
  v10 = v6;
LABEL_12:
  if ( hHandle[1] )
    CloseHandle(hHandle[1]);
  Logger::TraceVerbose((wchar_t *)L"%s - hr: 0x%08x", L"DeviceUpdateController::UpdateDevice", v10);
  return v10;
}

```

## disassembly

```asm
0x180065aa4  mov     [rsp+arg_0], rbx
0x180065aa9  mov     [rsp+arg_8], rsi
0x180065aae  push    rdi
0x180065aaf  sub     rsp, 50h
0x180065ab3  xorps   xmm0, xmm0
0x180065ab6  lea     rsi, aDeviceupdateco_5; "DeviceUpdateController::UpdateDevice"
0x180065abd  mov     rdx, rsi
0x180065ac0  lea     rcx, aSStarted; "%s started"
0x180065ac7  mov     rdi, r9
0x180065aca  xor     ebx, ebx
0x180065acc  movups  xmmword ptr [rsp+58h+hHandle], xmm0
0x180065ad1  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180065ad6  xor     edx, edx; lpName
0x180065ad8  lea     r8d, [rbx+1]; dwFlags
0x180065adc  xor     ecx, ecx; lpEventAttributes
0x180065ade  mov     r9d, 1F0003h; dwDesiredAccess
0x180065ae4  call    cs:__imp_CreateEventExW
0x180065aea  mov     [rsp+58h+hHandle+8], rax
0x180065aef  test    rax, rax
0x180065af2  jnz     short loc_180065B1E
0x180065af4  call    cs:__imp_GetLastError
0x180065afa  mov     ebx, eax
0x180065afc  test    eax, eax
0x180065afe  jz      short loc_180065B1E
0x180065b00  lea     r8, aCreateeventex; "CreateEventEx"
0x180065b07  mov     r9d, eax
0x180065b0a  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x180065b11  mov     rdx, rsi
0x180065b14  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180065b19  jmp     loc_180065C44
0x180065b1e  xor     edx, edx
0x180065b20  lea     rax, [rsp+58h+hHandle]
0x180065b25  mov     [rsp+58h+var_28], rax
0x180065b2a  mov     r9, rdi
0x180065b2d  lea     rax, ?SyncDeviceUpdateCallback@@YAX_KJ@Z; SyncDeviceUpdateCallback(unsigned __int64,long)
0x180065b34  mov     [rsp+58h+var_30], rax
0x180065b39  mov     eax, [rsp+58h+arg_20]
0x180065b40  lea     ecx, [rdx+1]
0x180065b43  lea     r8d, [rdx+3]
0x180065b47  mov     [rsp+58h+var_38], eax
0x180065b4b  call    ?UpdateDevice@DeviceUpdateController@@SAJW4_DSREG_JOIN_TYPE@@PEBGW4_DSREG_DEVICE_ATTRIBUTES@@1W4_COMPUTER_NAME_FORMAT@@P6AX_KJ@Z4@Z; DeviceUpdateController::UpdateDevice(_DSREG_JOIN_TYPE,ushort const *,_DSREG_DEVICE_ATTRIBUTES,ushort const *,_COMPUTER_NAME_FORMAT,void (*)(unsigned __int64,long),unsigned __int64)
0x180065b50  mov     edi, eax
0x180065b52  test    eax, eax
0x180065b54  jns     short loc_180065B70
0x180065b56  mov     r9d, eax
0x180065b59  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x180065b60  mov     r8, rsi
0x180065b63  mov     rdx, rsi
0x180065b66  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180065b6b  jmp     loc_180065C3C
0x180065b70  mov     rcx, [rsp+58h+hHandle+8]; hHandle
0x180065b75  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180065b78  call    cs:__imp_WaitForSingleObject
0x180065b7e  test    eax, eax
0x180065b80  jz      loc_180065C14
0x180065b86  cmp     eax, 102h
0x180065b8b  jz      short loc_180065BFE
0x180065b8d  cmp     eax, 0FFFFFFFFh
0x180065b90  jz      short loc_180065BE6
0x180065b92  mov     r8d, eax
0x180065b95  lea     rcx, aSWaitforsingle_4; "%s: WaitForSingleObject returned unexpe"...
0x180065b9c  mov     rdx, rsi
0x180065b9f  mov     ebx, 5B4h
0x180065ba4  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180065ba9  movzx   edi, bx
0x180065bac  or      edi, 80070000h
0x180065bb2  mov     rcx, [rsp+58h+hHandle+8]; hObject
0x180065bb7  test    rcx, rcx
0x180065bba  jz      short loc_180065BC2
0x180065bbc  call    cs:__imp_CloseHandle
0x180065bc2  mov     r8d, edi
0x180065bc5  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x180065bcc  mov     rdx, rsi
0x180065bcf  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180065bd4  mov     rbx, [rsp+58h+arg_0]
0x180065bd9  mov     eax, edi
0x180065bdb  mov     rsi, [rsp+58h+arg_8]
0x180065be0  add     rsp, 50h
0x180065be4  pop     rdi
0x180065be5  retn
0x180065be6  call    cs:__imp_GetLastError
0x180065bec  mov     ebx, eax
0x180065bee  test    eax, eax
0x180065bf0  jz      short loc_180065BB2
0x180065bf2  lea     r8, aWaitforsingleo; "WaitForSingleObject"
0x180065bf9  jmp     loc_180065B07
0x180065bfe  mov     rdx, rsi
0x180065c01  lea     rcx, aSWaitforsingle_1; "%s: WaitForSingleObject timed out for D"...
0x180065c08  mov     ebx, 5B4h
0x180065c0d  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180065c12  jmp     short loc_180065BA9
0x180065c14  mov     edi, dword ptr [rsp+58h+hHandle]
0x180065c18  mov     rdx, rsi
0x180065c1b  test    edi, edi
0x180065c1d  jns     short loc_180065C30
0x180065c1f  mov     r8d, edi
0x180065c22  lea     rcx, aSDeviceupdatec_1; "%s: DeviceUpdateController::UpdateDevic"...
0x180065c29  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180065c2e  jmp     short loc_180065C3C
0x180065c30  lea     rcx, aSDeviceupdatec; "%s: DeviceUpdateController::UpdateDevic"...
0x180065c37  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180065c3c  test    ebx, ebx
0x180065c3e  jz      loc_180065BB2
0x180065c44  test    ebx, ebx
0x180065c46  jg      loc_180065BA9
0x180065c4c  mov     edi, ebx
0x180065c4e  jmp     loc_180065BB2
```
