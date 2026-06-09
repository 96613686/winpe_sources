# IsatapConfigurationChangeNotificationUnderLock

- ea: `0x180029d18`
- end: `0x180029f93`
- name: `IsatapConfigurationChangeNotificationUnderLock`
- size: `635`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180032e70`
- `0x180059740`

## callees

- `0x180009010`
- `0x18000d7c0`
- `0x180029d18`
- `0x18002b47c`
- `0x180034198`
- `0x18003ff58`
- `0x180041e6c`
- `0x18005a884`
- `0x18005a9c0`
- `0x18005aa54`
- `0x18005de70`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029f34`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029f4a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029f34`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029f4a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180029d91`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180029dc1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180029d91`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180029dc1`

## string_xrefs

- `0x180029d81`: `System\CurrentControlSet\Services\iphlpsvc\Config`
- `0x180029d4c`: `Entered: IsatapConfigurationChangeNotificationUnderLock`
- `0x180029f68`: `Leaving: IsatapConfigurationChangeNotificationUnderLock`

## pseudocode

```c
unsigned int IsatapConfigurationChangeNotificationUnderLock()
{
  unsigned int v0; // eax
  unsigned int v1; // ebx
  __int64 v2; // r8
  const wchar_t *v3; // rcx
  unsigned int Integer; // eax
  unsigned int result; // eax
  HKEY hKey; // [rsp+40h] [rbp+10h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp+18h] BYREF

  hKey = 0;
  phkResult = 0;
  if ( IpHlpSvcEtwEnabled && (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x800000) != 0 )
    McTemplateU0z_EventWriteTransfer(
      MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
      EVENT_IPHLPSVC_ETW_FUNCTION_ENTRY_EXIT_MESSAGE,
      L"Entered: IsatapConfigurationChangeNotificationUnderLock");
  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\iphlpsvc\\Config", 0, 1u, &hKey);
  phkResult = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  RegOpenKeyExW(
    HKEY_LOCAL_MACHINE,
    L"SOFTWARE\\Policies\\Microsoft\\Windows\\Tcpip\\v6Transition",
    0,
    0x20019u,
    &phkResult);
  v0 = GpQuery6to4orIsatapStateSetting(phkResult);
  v1 = v0;
  if ( v0 != 4 )
  {
    if ( v0 - 1 > 1 )
      goto LABEL_12;
    v2 = v0;
    v3 = L"GP";
    goto LABEL_11;
  }
  if ( (byte_1800CA104 & 4) != 0 )
  {
    v1 = 3;
    goto LABEL_12;
  }
  Integer = GetInteger(hKey, L"IsatapState", 0);
  v1 = Integer;
  if ( Integer - 1 <= 1 )
  {
    v2 = Integer;
    v3 = L"Reg";
LABEL_11:
    IsatapTelemetryWriteEnabled(v3, (unsigned int)dword_1800CA120, v2);
  }
LABEL_12:
  dword_1800CA108 = GetInteger(hKey, L"UndoOnStop", 2);
  if ( v1 == 2 )
  {
    dword_1800CA12C = 3;
  }
  else
  {
    dword_1800CA12C = 2;
    if ( v1 )
    {
      if ( v1 == 1 )
        v1 = 2;
    }
    else
    {
      v1 = 3;
    }
  }
  dword_1800CA124 = GetInteger(hKey, L"EnableIsatapResolution", 2);
  dword_1800CA128 = GetInteger(hKey, L"IsatapResolutionInterval", 60);
  result = IsatapQueryIsatapRouterName(v1, phkResult, hKey);
  if ( v1 == 2 )
  {
    if ( dword_1800CA120 == 2 )
    {
      result = IsatapRefresh();
    }
    else
    {
      result = IsatapStart();
      if ( !dword_1800CA978 )
      {
        result = RegisterNotificationHandlers(&g_ProtocolStateIsatap, &off_1800C8220, 192);
        if ( result )
          result = EventWrite0(0x2000000, L"RegisterNotificationHandlers FAILED. Error:%d", result);
        else
          dword_1800CA978 = 1;
      }
    }
  }
  else if ( dword_1800CA120 == 2 )
  {
    result = IsatapStop();
  }
  if ( hKey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    result = RegCloseKey(hKey);
  if ( phkResult != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    result = RegCloseKey(phkResult);
  if ( IpHlpSvcEtwEnabled )
  {
    if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x800000) != 0 )
      return McTemplateU0z_EventWriteTransfer(
               MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
               EVENT_IPHLPSVC_ETW_FUNCTION_ENTRY_EXIT_MESSAGE,
               L"Leaving: IsatapConfigurationChangeNotificationUnderLock");
  }
  return result;
}

```

## disassembly

```asm
0x180029d18  mov     [rsp-8+arg_10], rbx
0x180029d1d  mov     [rsp-8+arg_18], rsi
0x180029d22  push    rbp
0x180029d23  mov     rbp, rsp
0x180029d26  sub     rsp, 30h
0x180029d2a  cmp     cs:IpHlpSvcEtwEnabled, 0
0x180029d31  mov     [rbp+hKey], 0
0x180029d39  mov     [rbp+arg_8], 0
0x180029d41  jz      short loc_180029D66
0x180029d43  cmp     byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, 0
0x180029d4a  jge     short loc_180029D66
0x180029d4c  lea     r8, aEnteredIsatapc; "Entered: IsatapConfigurationChangeNotif"...
0x180029d53  lea     rdx, EVENT_IPHLPSVC_ETW_FUNCTION_ENTRY_EXIT_MESSAGE
0x180029d5a  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x180029d61  call    McTemplateU0z_EventWriteTransfer
0x180029d66  lea     rax, [rbp+hKey]
0x180029d6a  mov     [rbp+hKey], 0FFFFFFFFFFFFFFFFh
0x180029d72  mov     rbx, 0FFFFFFFF80000002h
0x180029d79  mov     [rsp+30h+phkResult], rax; phkResult
0x180029d7e  mov     rcx, rbx; hKey
0x180029d81  lea     rdx, aSystemCurrentc_5; "System\\CurrentControlSet\\Services\\ip"...
0x180029d88  mov     r9d, 1; samDesired
0x180029d8e  xor     r8d, r8d; ulOptions
0x180029d91  call    cs:__imp_RegOpenKeyExW
0x180029d98  nop     dword ptr [rax+rax+00h]
0x180029d9d  lea     rax, [rbp+arg_8]
0x180029da1  mov     [rbp+arg_8], 0FFFFFFFFFFFFFFFFh
0x180029da9  mov     r9d, 20019h; samDesired
0x180029daf  mov     [rsp+30h+phkResult], rax; phkResult
0x180029db4  xor     r8d, r8d; ulOptions
0x180029db7  lea     rdx, aSoftwarePolici; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x180029dbe  mov     rcx, rbx; hKey
0x180029dc1  call    cs:__imp_RegOpenKeyExW
0x180029dc8  nop     dword ptr [rax+rax+00h]
0x180029dcd  mov     rcx, [rbp+arg_8]; hKey
0x180029dd1  xor     edx, edx
0x180029dd3  call    GpQuery6to4orIsatapStateSetting
0x180029dd8  mov     ebx, eax
0x180029dda  cmp     eax, 4
0x180029ddd  jz      short loc_180029DF2
0x180029ddf  dec     eax
0x180029de1  cmp     eax, 1
0x180029de4  ja      short loc_180029E34
0x180029de6  mov     r8d, ebx
0x180029de9  lea     rcx, aGp; "GP"
0x180029df0  jmp     short loc_180029E29
0x180029df2  test    cs:byte_1800CA104, 4
0x180029df9  jz      short loc_180029E02
0x180029dfb  mov     ebx, 3
0x180029e00  jmp     short loc_180029E34
0x180029e02  mov     rcx, [rbp+hKey]
0x180029e06  lea     rdx, aIsatapstate; "IsatapState"
0x180029e0d  xor     r8d, r8d
0x180029e10  call    GetInteger
0x180029e15  mov     ebx, eax
0x180029e17  lea     ecx, [rax-1]
0x180029e1a  cmp     ecx, 1
0x180029e1d  ja      short loc_180029E34
0x180029e1f  mov     r8d, eax
0x180029e22  lea     rcx, aReg; "Reg"
0x180029e29  mov     edx, cs:dword_1800CA120
0x180029e2f  call    IsatapTelemetryWriteEnabled
0x180029e34  mov     rcx, [rbp+hKey]
0x180029e38  lea     rdx, aUndoonstop; "UndoOnStop"
0x180029e3f  mov     esi, 2
0x180029e44  mov     r8d, esi
0x180029e47  call    GetInteger
0x180029e4c  mov     cs:dword_1800CA108, eax
0x180029e52  cmp     ebx, esi
0x180029e54  jnz     short loc_180029E62
0x180029e56  mov     cs:dword_1800CA12C, 3
0x180029e60  jmp     short loc_180029E79
0x180029e62  mov     cs:dword_1800CA12C, esi
0x180029e68  test    ebx, ebx
0x180029e6a  jnz     short loc_180029E73
0x180029e6c  mov     ebx, 3
0x180029e71  jmp     short loc_180029E79
0x180029e73  cmp     ebx, 1
0x180029e76  cmovz   ebx, esi
0x180029e79  mov     rcx, [rbp+hKey]
0x180029e7d  lea     rdx, aEnableisatapre; "EnableIsatapResolution"
0x180029e84  mov     r8d, esi
0x180029e87  call    GetInteger
0x180029e8c  mov     rcx, [rbp+hKey]
0x180029e90  lea     rdx, aIsatapresoluti; "IsatapResolutionInterval"
0x180029e97  mov     r8d, 3Ch ; '<'
0x180029e9d  mov     cs:dword_1800CA124, eax
0x180029ea3  call    GetInteger
0x180029ea8  mov     r8, [rbp+hKey]
0x180029eac  mov     ecx, ebx
0x180029eae  mov     rdx, [rbp+arg_8]
0x180029eb2  mov     cs:dword_1800CA128, eax
0x180029eb8  call    IsatapQueryIsatapRouterName
0x180029ebd  cmp     ebx, esi
0x180029ebf  jnz     short loc_180029F1D
0x180029ec1  cmp     cs:dword_1800CA120, esi
0x180029ec7  jnz     short loc_180029ED0
0x180029ec9  call    IsatapRefresh
0x180029ece  jmp     short loc_180029F2A
0x180029ed0  call    IsatapStart
0x180029ed5  cmp     cs:dword_1800CA978, 0
0x180029edc  jnz     short loc_180029F2A
0x180029ede  mov     r8d, 0C0h
0x180029ee4  lea     rdx, off_1800C8220
0x180029eeb  lea     rcx, g_ProtocolStateIsatap
0x180029ef2  call    RegisterNotificationHandlers
0x180029ef7  test    eax, eax
0x180029ef9  jz      short loc_180029F11
0x180029efb  mov     r8d, eax
0x180029efe  lea     rdx, aRegisternotifi; "RegisterNotificationHandlers FAILED. Er"...
0x180029f05  mov     ecx, 2000000h
0x180029f0a  call    EventWrite0
0x180029f0f  jmp     short loc_180029F2A
0x180029f11  mov     cs:dword_1800CA978, 1
0x180029f1b  jmp     short loc_180029F2A
0x180029f1d  cmp     cs:dword_1800CA120, esi
0x180029f23  jnz     short loc_180029F2A
0x180029f25  call    IsatapStop
0x180029f2a  mov     rcx, [rbp+hKey]; hKey
0x180029f2e  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180029f32  jz      short loc_180029F40
0x180029f34  call    cs:__imp_RegCloseKey
0x180029f3b  nop     dword ptr [rax+rax+00h]
0x180029f40  mov     rcx, [rbp+arg_8]; hKey
0x180029f44  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180029f48  jz      short loc_180029F56
0x180029f4a  call    cs:__imp_RegCloseKey
0x180029f51  nop     dword ptr [rax+rax+00h]
0x180029f56  cmp     cs:IpHlpSvcEtwEnabled, 0
0x180029f5d  jz      short loc_180029F82
0x180029f5f  cmp     byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, 0
0x180029f66  jge     short loc_180029F82
0x180029f68  lea     r8, aLeavingIsatapc_1; "Leaving: IsatapConfigurationChangeNotif"...
0x180029f6f  lea     rdx, EVENT_IPHLPSVC_ETW_FUNCTION_ENTRY_EXIT_MESSAGE
0x180029f76  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x180029f7d  call    McTemplateU0z_EventWriteTransfer
0x180029f82  mov     rbx, [rsp+30h+arg_10]
0x180029f87  mov     rsi, [rsp+30h+arg_18]
0x180029f8c  add     rsp, 30h
0x180029f90  pop     rbp
0x180029f91  retn
```
