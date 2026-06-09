# IsatapConfigurationChangeNotificationUnderLock

- ea: `0x180029d08`
- end: `0x180029f83`
- name: `IsatapConfigurationChangeNotificationUnderLock`
- size: `635`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180032e60`
- `0x180059720`

## callees

- `0x180009000`
- `0x18000d7b0`
- `0x180029d08`
- `0x18002b46c`
- `0x180034188`
- `0x18003ff98`
- `0x180041eac`
- `0x18005a864`
- `0x18005a9a0`
- `0x18005aa34`
- `0x18005de50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029f24`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029f3a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029f24`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029f3a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180029d81`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180029db1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180029d81`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180029db1`

## string_xrefs

- `0x180029d71`: `System\CurrentControlSet\Services\iphlpsvc\Config`
- `0x180029d3c`: `Entered: IsatapConfigurationChangeNotificationUnderLock`
- `0x180029f58`: `Leaving: IsatapConfigurationChangeNotificationUnderLock`

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
0x180029d08  mov     [rsp-8+arg_10], rbx
0x180029d0d  mov     [rsp-8+arg_18], rsi
0x180029d12  push    rbp
0x180029d13  mov     rbp, rsp
0x180029d16  sub     rsp, 30h
0x180029d1a  cmp     cs:IpHlpSvcEtwEnabled, 0
0x180029d21  mov     [rbp+hKey], 0
0x180029d29  mov     [rbp+arg_8], 0
0x180029d31  jz      short loc_180029D56
0x180029d33  cmp     byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, 0
0x180029d3a  jge     short loc_180029D56
0x180029d3c  lea     r8, aEnteredIsatapc; "Entered: IsatapConfigurationChangeNotif"...
0x180029d43  lea     rdx, EVENT_IPHLPSVC_ETW_FUNCTION_ENTRY_EXIT_MESSAGE
0x180029d4a  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x180029d51  call    McTemplateU0z_EventWriteTransfer
0x180029d56  lea     rax, [rbp+hKey]
0x180029d5a  mov     [rbp+hKey], 0FFFFFFFFFFFFFFFFh
0x180029d62  mov     rbx, 0FFFFFFFF80000002h
0x180029d69  mov     [rsp+30h+phkResult], rax; phkResult
0x180029d6e  mov     rcx, rbx; hKey
0x180029d71  lea     rdx, aSystemCurrentc_5; "System\\CurrentControlSet\\Services\\ip"...
0x180029d78  mov     r9d, 1; samDesired
0x180029d7e  xor     r8d, r8d; ulOptions
0x180029d81  call    cs:__imp_RegOpenKeyExW
0x180029d88  nop     dword ptr [rax+rax+00h]
0x180029d8d  lea     rax, [rbp+arg_8]
0x180029d91  mov     [rbp+arg_8], 0FFFFFFFFFFFFFFFFh
0x180029d99  mov     r9d, 20019h; samDesired
0x180029d9f  mov     [rsp+30h+phkResult], rax; phkResult
0x180029da4  xor     r8d, r8d; ulOptions
0x180029da7  lea     rdx, aSoftwarePolici; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x180029dae  mov     rcx, rbx; hKey
0x180029db1  call    cs:__imp_RegOpenKeyExW
0x180029db8  nop     dword ptr [rax+rax+00h]
0x180029dbd  mov     rcx, [rbp+arg_8]; hKey
0x180029dc1  xor     edx, edx
0x180029dc3  call    GpQuery6to4orIsatapStateSetting
0x180029dc8  mov     ebx, eax
0x180029dca  cmp     eax, 4
0x180029dcd  jz      short loc_180029DE2
0x180029dcf  dec     eax
0x180029dd1  cmp     eax, 1
0x180029dd4  ja      short loc_180029E24
0x180029dd6  mov     r8d, ebx
0x180029dd9  lea     rcx, aGp; "GP"
0x180029de0  jmp     short loc_180029E19
0x180029de2  test    cs:byte_1800CA104, 4
0x180029de9  jz      short loc_180029DF2
0x180029deb  mov     ebx, 3
0x180029df0  jmp     short loc_180029E24
0x180029df2  mov     rcx, [rbp+hKey]
0x180029df6  lea     rdx, aIsatapstate; "IsatapState"
0x180029dfd  xor     r8d, r8d
0x180029e00  call    GetInteger
0x180029e05  mov     ebx, eax
0x180029e07  lea     ecx, [rax-1]
0x180029e0a  cmp     ecx, 1
0x180029e0d  ja      short loc_180029E24
0x180029e0f  mov     r8d, eax
0x180029e12  lea     rcx, aReg; "Reg"
0x180029e19  mov     edx, cs:dword_1800CA120
0x180029e1f  call    IsatapTelemetryWriteEnabled
0x180029e24  mov     rcx, [rbp+hKey]
0x180029e28  lea     rdx, aUndoonstop; "UndoOnStop"
0x180029e2f  mov     esi, 2
0x180029e34  mov     r8d, esi
0x180029e37  call    GetInteger
0x180029e3c  mov     cs:dword_1800CA108, eax
0x180029e42  cmp     ebx, esi
0x180029e44  jnz     short loc_180029E52
0x180029e46  mov     cs:dword_1800CA12C, 3
0x180029e50  jmp     short loc_180029E69
0x180029e52  mov     cs:dword_1800CA12C, esi
0x180029e58  test    ebx, ebx
0x180029e5a  jnz     short loc_180029E63
0x180029e5c  mov     ebx, 3
0x180029e61  jmp     short loc_180029E69
0x180029e63  cmp     ebx, 1
0x180029e66  cmovz   ebx, esi
0x180029e69  mov     rcx, [rbp+hKey]
0x180029e6d  lea     rdx, aEnableisatapre; "EnableIsatapResolution"
0x180029e74  mov     r8d, esi
0x180029e77  call    GetInteger
0x180029e7c  mov     rcx, [rbp+hKey]
0x180029e80  lea     rdx, aIsatapresoluti; "IsatapResolutionInterval"
0x180029e87  mov     r8d, 3Ch ; '<'
0x180029e8d  mov     cs:dword_1800CA124, eax
0x180029e93  call    GetInteger
0x180029e98  mov     r8, [rbp+hKey]
0x180029e9c  mov     ecx, ebx
0x180029e9e  mov     rdx, [rbp+arg_8]
0x180029ea2  mov     cs:dword_1800CA128, eax
0x180029ea8  call    IsatapQueryIsatapRouterName
0x180029ead  cmp     ebx, esi
0x180029eaf  jnz     short loc_180029F0D
0x180029eb1  cmp     cs:dword_1800CA120, esi
0x180029eb7  jnz     short loc_180029EC0
0x180029eb9  call    IsatapRefresh
0x180029ebe  jmp     short loc_180029F1A
0x180029ec0  call    IsatapStart
0x180029ec5  cmp     cs:dword_1800CA978, 0
0x180029ecc  jnz     short loc_180029F1A
0x180029ece  mov     r8d, 0C0h
0x180029ed4  lea     rdx, off_1800C8220
0x180029edb  lea     rcx, g_ProtocolStateIsatap
0x180029ee2  call    RegisterNotificationHandlers
0x180029ee7  test    eax, eax
0x180029ee9  jz      short loc_180029F01
0x180029eeb  mov     r8d, eax
0x180029eee  lea     rdx, aRegisternotifi; "RegisterNotificationHandlers FAILED. Er"...
0x180029ef5  mov     ecx, 2000000h
0x180029efa  call    EventWrite0
0x180029eff  jmp     short loc_180029F1A
0x180029f01  mov     cs:dword_1800CA978, 1
0x180029f0b  jmp     short loc_180029F1A
0x180029f0d  cmp     cs:dword_1800CA120, esi
0x180029f13  jnz     short loc_180029F1A
0x180029f15  call    IsatapStop
0x180029f1a  mov     rcx, [rbp+hKey]; hKey
0x180029f1e  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180029f22  jz      short loc_180029F30
0x180029f24  call    cs:__imp_RegCloseKey
0x180029f2b  nop     dword ptr [rax+rax+00h]
0x180029f30  mov     rcx, [rbp+arg_8]; hKey
0x180029f34  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180029f38  jz      short loc_180029F46
0x180029f3a  call    cs:__imp_RegCloseKey
0x180029f41  nop     dword ptr [rax+rax+00h]
0x180029f46  cmp     cs:IpHlpSvcEtwEnabled, 0
0x180029f4d  jz      short loc_180029F72
0x180029f4f  cmp     byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, 0
0x180029f56  jge     short loc_180029F72
0x180029f58  lea     r8, aLeavingIsatapc_1; "Leaving: IsatapConfigurationChangeNotif"...
0x180029f5f  lea     rdx, EVENT_IPHLPSVC_ETW_FUNCTION_ENTRY_EXIT_MESSAGE
0x180029f66  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x180029f6d  call    McTemplateU0z_EventWriteTransfer
0x180029f72  mov     rbx, [rsp+30h+arg_10]
0x180029f77  mov     rsi, [rsp+30h+arg_18]
0x180029f7c  add     rsp, 30h
0x180029f80  pop     rbp
0x180029f81  retn
```
