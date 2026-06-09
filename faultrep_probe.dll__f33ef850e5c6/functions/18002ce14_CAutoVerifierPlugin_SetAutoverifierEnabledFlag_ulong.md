# CAutoVerifierPlugin::SetAutoverifierEnabledFlag(ulong)

- ea: `0x18002ce14`
- end: `0x18002d02c`
- name: `?SetAutoverifierEnabledFlag@CAutoVerifierPlugin@@AEAAJK@Z`
- size: `536`
- prototype: `__int64 __fastcall(CAutoVerifierPlugin *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002b3a0`
- `0x18002b4c4`

## callees

- `0x180009ed8`
- `0x180009f00`
- `0x18000a004`
- `0x18002ce14`
- `0x180036ec4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002cfd5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002cfd5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002ce81`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002cf48`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002ce81`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002cf48`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d00e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d01d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d00e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d01d`

## string_xrefs

- `0x18002ce52`: `Software\Microsoft\Windows\Windows Error Reporting\Plugins`

## pseudocode

```c
__int64 __fastcall CAutoVerifierPlugin::SetAutoverifierEnabledFlag(CAutoVerifierPlugin *this, int a2)
{
  HKEY *phkResult; // rax
  enum _ACCESS_MODE v3; // edx
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  unsigned int v6; // ebx
  int v7; // eax
  HKEY *v8; // rax
  enum _ACCESS_MODE v9; // edx
  int v10; // eax
  DWORD dwDisposition; // [rsp+70h] [rbp+18h] BYREF
  int v13; // [rsp+74h] [rbp+1Ch]
  int Data; // [rsp+78h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+80h] [rbp+28h] BYREF
  HKEY v16; // [rsp+88h] [rbp+30h] BYREF

  Data = a2;
  v13 = HIDWORD(this);
  v16 = 0;
  hKey = 0;
  dwDisposition = 0;
  phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  if ( RegCreateKeyExW(
         HKEY_CURRENT_USER,
         L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Plugins",
         0,
         0,
         0,
         0x60004u,
         0,
         phkResult,
         &dwDisposition) )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_6;
    v5 = 38;
LABEL_5:
    WPP_SF_(v4[2], v5, &WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids);
LABEL_6:
    v6 = -2147467259;
    goto LABEL_24;
  }
  v7 = WerPluginAdjustAppContainerAccessToKey(hKey, v3, 0x80000002);
  if ( v7 < 0 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      39,
      &WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids,
      (unsigned int)v7);
  v8 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v16);
  if ( RegCreateKeyExW(hKey, L"Autoverifier", 0, 0, 1u, 0x60002u, 0, v8, &dwDisposition) )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_6;
    v5 = 40;
    goto LABEL_5;
  }
  v10 = WerPluginAdjustAppContainerAccessToKey(hKey, v9, 0x80000002);
  if ( v10 < 0
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      41,
      &WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids,
      (unsigned int)v10);
  }
  if ( RegSetValueExW(v16, L"AutoverifierEnabled", 0, 4u, (const BYTE *)&Data, 4u) )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_6;
    v5 = 42;
    goto LABEL_5;
  }
  v6 = 0;
LABEL_24:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v16 )
    RegCloseKey(v16);
  return v6;
}

```

## disassembly

```asm
0x18002ce14  mov     [rsp-10h+Data], edx
0x18002ce18  mov     qword ptr [rsp-10h+dwDisposition], rcx
0x18002ce1d  push    rbp
0x18002ce1e  push    rbx
0x18002ce1f  mov     rbp, rsp
0x18002ce22  sub     rsp, 58h
0x18002ce26  lea     rcx, [rbp+hKey]
0x18002ce2a  mov     [rbp+arg_18], 0
0x18002ce32  mov     [rbp+hKey], 0
0x18002ce3a  mov     [rbp+dwDisposition], 0
0x18002ce41  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x18002ce46  lea     rcx, [rbp+dwDisposition]
0x18002ce4a  xor     r9d, r9d; lpClass
0x18002ce4d  mov     [rsp+58h+lpdwDisposition], rcx; lpdwDisposition
0x18002ce52  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\Windows E"...
0x18002ce59  mov     [rsp+58h+phkResult], rax; phkResult
0x18002ce5e  xor     r8d, r8d; Reserved
0x18002ce61  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18002ce6a  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18002ce71  mov     [rsp+58h+samDesired], 60004h; samDesired
0x18002ce79  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18002ce81  call    cs:__imp_RegCreateKeyExW
0x18002ce87  test    eax, eax
0x18002ce89  jz      short loc_18002CEC3
0x18002ce8b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ce92  lea     rbx, WPP_GLOBAL_Control
0x18002ce99  cmp     rcx, rbx
0x18002ce9c  jz      short loc_18002CEB9
0x18002ce9e  test    byte ptr [rcx+1Ch], 1
0x18002cea2  jz      short loc_18002CEB9
0x18002cea4  mov     edx, 26h ; '&'
0x18002cea9  mov     rcx, [rcx+10h]
0x18002cead  lea     r8, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids
0x18002ceb4  call    WPP_SF_
0x18002ceb9  mov     ebx, 80004005h
0x18002cebe  jmp     loc_18002D005
0x18002cec3  mov     rcx, [rbp+hKey]; hKey
0x18002cec7  mov     r8d, 80000002h; unsigned int
0x18002cecd  call    ?WerPluginAdjustAppContainerAccessToKey@@YAJPEAUHKEY__@@W4_ACCESS_MODE@@K@Z; WerPluginAdjustAppContainerAccessToKey(HKEY__ *,_ACCESS_MODE,ulong)
0x18002ced2  lea     rbx, WPP_GLOBAL_Control
0x18002ced9  test    eax, eax
0x18002cedb  jns     short loc_18002CF07
0x18002cedd  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cee4  cmp     rcx, rbx
0x18002cee7  jz      short loc_18002CF07
0x18002cee9  test    byte ptr [rcx+1Ch], 2
0x18002ceed  jz      short loc_18002CF07
0x18002ceef  mov     rcx, [rcx+10h]
0x18002cef3  lea     r8, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids
0x18002cefa  mov     edx, 27h ; '''
0x18002ceff  mov     r9d, eax
0x18002cf02  call    WPP_SF_d
0x18002cf07  lea     rcx, [rbp+arg_18]
0x18002cf0b  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x18002cf10  lea     rcx, [rbp+dwDisposition]
0x18002cf14  xor     r9d, r9d; lpClass
0x18002cf17  mov     [rsp+58h+lpdwDisposition], rcx; lpdwDisposition
0x18002cf1c  lea     rdx, aAutoverifier; "Autoverifier"
0x18002cf23  mov     rcx, [rbp+hKey]; hKey
0x18002cf27  xor     r8d, r8d; Reserved
0x18002cf2a  mov     [rsp+58h+phkResult], rax; phkResult
0x18002cf2f  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18002cf38  mov     [rsp+58h+samDesired], 60002h; samDesired
0x18002cf40  mov     [rsp+58h+dwOptions], 1; dwOptions
0x18002cf48  call    cs:__imp_RegCreateKeyExW
0x18002cf4e  test    eax, eax
0x18002cf50  jz      short loc_18002CF76
0x18002cf52  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cf59  cmp     rcx, rbx
0x18002cf5c  jz      loc_18002CEB9
0x18002cf62  test    byte ptr [rcx+1Ch], 1
0x18002cf66  jz      loc_18002CEB9
0x18002cf6c  mov     edx, 28h ; '('
0x18002cf71  jmp     loc_18002CEA9
0x18002cf76  mov     rcx, [rbp+hKey]; hKey
0x18002cf7a  mov     r8d, 80000002h; unsigned int
0x18002cf80  call    ?WerPluginAdjustAppContainerAccessToKey@@YAJPEAUHKEY__@@W4_ACCESS_MODE@@K@Z; WerPluginAdjustAppContainerAccessToKey(HKEY__ *,_ACCESS_MODE,ulong)
0x18002cf85  test    eax, eax
0x18002cf87  jns     short loc_18002CFB3
0x18002cf89  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cf90  cmp     rcx, rbx
0x18002cf93  jz      short loc_18002CFB3
0x18002cf95  test    byte ptr [rcx+1Ch], 2
0x18002cf99  jz      short loc_18002CFB3
0x18002cf9b  mov     rcx, [rcx+10h]
0x18002cf9f  lea     r8, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids
0x18002cfa6  mov     edx, 29h ; ')'
0x18002cfab  mov     r9d, eax
0x18002cfae  call    WPP_SF_d
0x18002cfb3  mov     rcx, [rbp+arg_18]; hKey
0x18002cfb7  lea     rax, [rbp+Data]
0x18002cfbb  mov     r9d, 4; dwType
0x18002cfc1  lea     rdx, aAutoverifieren; "AutoverifierEnabled"
0x18002cfc8  mov     [rsp+58h+samDesired], r9d; cbData
0x18002cfcd  xor     r8d, r8d; Reserved
0x18002cfd0  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x18002cfd5  call    cs:__imp_RegSetValueExW
0x18002cfdb  test    eax, eax
0x18002cfdd  jz      short loc_18002D003
0x18002cfdf  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cfe6  cmp     rcx, rbx
0x18002cfe9  jz      loc_18002CEB9
0x18002cfef  test    byte ptr [rcx+1Ch], 1
0x18002cff3  jz      loc_18002CEB9
0x18002cff9  mov     edx, 2Ah ; '*'
0x18002cffe  jmp     loc_18002CEA9
0x18002d003  xor     ebx, ebx
0x18002d005  mov     rcx, [rbp+hKey]; hKey
0x18002d009  test    rcx, rcx
0x18002d00c  jz      short loc_18002D014
0x18002d00e  call    cs:__imp_RegCloseKey
0x18002d014  mov     rcx, [rbp+arg_18]; hKey
0x18002d018  test    rcx, rcx
0x18002d01b  jz      short loc_18002D023
0x18002d01d  call    cs:__imp_RegCloseKey
0x18002d023  mov     eax, ebx
0x18002d025  add     rsp, 58h
0x18002d029  pop     rbx
0x18002d02a  pop     rbp
0x18002d02b  retn
```
