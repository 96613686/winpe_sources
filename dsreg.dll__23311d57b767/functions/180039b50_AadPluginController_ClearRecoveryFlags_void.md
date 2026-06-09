# AadPluginController::ClearRecoveryFlags(void)

- ea: `0x180039b50`
- end: `0x180039c6c`
- name: `?ClearRecoveryFlags@AadPluginController@@SAJXZ`
- size: `284`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180049f70`
- `0x180053630`
- `0x180054738`

## callees

- `0x1800084f4`
- `0x180008530`
- `0x18000bac0`
- `0x180031ae0`
- `0x1800372c4`
- `0x180039b50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180039b9e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180039b9e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180039c43`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180039c43`

## string_xrefs

- `0x180039b76`: `AadPluginController::OpenAadIdpRegistrationKey`
- `0x180039bb4`: `RegDeleteValueW`
- `0x180039b7d`: `AadPluginController::ClearRecoveryFlags`
- `0x180039bbb`: `AadPluginController::ClearRecoveryFlags`
- `0x180039c26`: `AadPluginController::ClearRecoveryFlags`
- `0x180039c4c`: `AadPluginController::ClearRecoveryFlags`
- `0x180039c10`: `Logger::WriteRecoveryFlagsResetFailureEvent`
- `0x180039c09`: `EventWriteRecoveryFlagsResetFailureEvent`
- `0x180039c2d`: `%s: Resetting RunRecovery registry value failed with error code: 0x%08x.`

## pseudocode

```c
__int64 AadPluginController::ClearRecoveryFlags(void)
{
  int v0; // eax
  unsigned int v1; // ebx
  unsigned int v2; // eax
  signed int v3; // edi
  unsigned int v4; // eax
  HKEY hKey; // [rsp+30h] [rbp+8h] BYREF

  hKey = 0;
  v0 = AadPluginController::OpenAadIdpRegistrationKey(&hKey);
  v1 = v0;
  if ( v0 >= 0 )
  {
    v2 = RegDeleteValueW(hKey, L"RunRecovery");
    v3 = v2;
    if ( (v2 & 0xFFFFFFFD) == 0 )
      goto LABEL_12;
    Logger::TraceError(
      L"%s: %s failed with win32 error code: 0x%08x.",
      L"AadPluginController::ClearRecoveryFlags",
      L"RegDeleteValueW",
      v2);
    v1 = v3 > 0 ? (unsigned __int16)v3 | 0x80070000 : v3;
    if ( (v1 & 0x80000000) == 0 )
      goto LABEL_12;
  }
  else
  {
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"AadPluginController::ClearRecoveryFlags",
      L"AadPluginController::OpenAadIdpRegistrationKey",
      (unsigned int)v0);
  }
  if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 4) != 0 )
  {
    v4 = McTemplateU0q_EventWriteTransfer(
           &UserDeviceRegistrationEventProvider_Context,
           RecoveryFlagsResetFailureEvent,
           v1);
    if ( v4 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"Logger::WriteRecoveryFlagsResetFailureEvent",
        L"EventWriteRecoveryFlagsResetFailureEvent",
        v4);
  }
  Logger::TraceWarning(
    (wchar_t *)L"%s: Resetting RunRecovery registry value failed with error code: 0x%08x.",
    L"AadPluginController::ClearRecoveryFlags",
    v1);
LABEL_12:
  if ( hKey )
    RegCloseKey(hKey);
  Logger::TraceVerbose((wchar_t *)L"%s - hr: 0x%08x", L"AadPluginController::ClearRecoveryFlags", v1);
  return v1;
}

```

## disassembly

```asm
0x180039b50  mov     [rsp+arg_8], rbx
0x180039b55  push    rdi
0x180039b56  sub     rsp, 20h
0x180039b5a  lea     rcx, [rsp+28h+hKey]; HKEY *
0x180039b5f  mov     [rsp+28h+hKey], 0
0x180039b68  call    ?OpenAadIdpRegistrationKey@AadPluginController@@CAJPEAPEAUHKEY__@@@Z; AadPluginController::OpenAadIdpRegistrationKey(HKEY__ * *)
0x180039b6d  mov     ebx, eax
0x180039b6f  test    eax, eax
0x180039b71  jns     short loc_180039B92
0x180039b73  mov     r9d, eax
0x180039b76  lea     r8, aAadplugincontr_1; "AadPluginController::OpenAadIdpRegistra"...
0x180039b7d  lea     rdx, aAadplugincontr_12; "AadPluginController::ClearRecoveryFlags"
0x180039b84  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x180039b8b  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180039b90  jmp     short loc_180039BE3
0x180039b92  mov     rcx, [rsp+28h+hKey]; hKey
0x180039b97  lea     rdx, aRunrecovery; "RunRecovery"
0x180039b9e  call    cs:__imp_RegDeleteValueW
0x180039ba4  mov     edi, eax
0x180039ba6  test    eax, 0FFFFFFFDh
0x180039bab  jz      loc_180039C39
0x180039bb1  mov     r9d, eax
0x180039bb4  lea     r8, aRegdeletevalue; "RegDeleteValueW"
0x180039bbb  lea     rdx, aAadplugincontr_12; "AadPluginController::ClearRecoveryFlags"
0x180039bc2  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x180039bc9  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180039bce  test    edi, edi
0x180039bd0  jg      short loc_180039BD6
0x180039bd2  mov     ebx, edi
0x180039bd4  jmp     short loc_180039BDF
0x180039bd6  movzx   ebx, di
0x180039bd9  or      ebx, 80070000h
0x180039bdf  test    ebx, ebx
0x180039be1  jns     short loc_180039C39
0x180039be3  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 4
0x180039bea  jz      short loc_180039C23
0x180039bec  mov     r8d, ebx
0x180039bef  lea     rdx, RecoveryFlagsResetFailureEvent
0x180039bf6  lea     rcx, UserDeviceRegistrationEventProvider_Context
0x180039bfd  call    McTemplateU0q_EventWriteTransfer
0x180039c02  test    eax, eax
0x180039c04  jz      short loc_180039C23
0x180039c06  mov     r9d, eax
0x180039c09  lea     r8, aEventwritereco_0; "EventWriteRecoveryFlagsResetFailureEven"...
0x180039c10  lea     rdx, aLoggerWriterec_0; "Logger::WriteRecoveryFlagsResetFailureE"...
0x180039c17  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x180039c1e  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180039c23  mov     r8d, ebx
0x180039c26  lea     rdx, aAadplugincontr_12; "AadPluginController::ClearRecoveryFlags"
0x180039c2d  lea     rcx, aSResettingRunr; "%s: Resetting RunRecovery registry valu"...
0x180039c34  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x180039c39  mov     rcx, [rsp+28h+hKey]; hKey
0x180039c3e  test    rcx, rcx
0x180039c41  jz      short loc_180039C49
0x180039c43  call    cs:__imp_RegCloseKey
0x180039c49  mov     r8d, ebx
0x180039c4c  lea     rdx, aAadplugincontr_12; "AadPluginController::ClearRecoveryFlags"
0x180039c53  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x180039c5a  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180039c5f  mov     eax, ebx
0x180039c61  mov     rbx, [rsp+28h+arg_8]
0x180039c66  add     rsp, 20h
0x180039c6a  pop     rdi
0x180039c6b  retn
```
