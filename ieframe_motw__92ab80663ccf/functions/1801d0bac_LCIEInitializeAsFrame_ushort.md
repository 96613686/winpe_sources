# LCIEInitializeAsFrame(ushort *)

- ea: `0x1801d0bac`
- end: `0x1801d0dbf`
- name: `?LCIEInitializeAsFrame@@YAJPEAG@Z`
- size: `531`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800aa154`

## callees

- `0x1800a2320`
- `0x1800f90dc`
- `0x1800fe2b8`
- `0x180110f18`
- `0x18012894c`
- `0x1801ce39c`
- `0x1801d0bac`
- `0x1801d36b8`
- `0x1801d3c00`
- `0x1801d4a88`
- `0x1801d52dc`
- `0x1801e55c4`
- `0x180266048`

## import_xrefs

- `api-ms-win-downlevel-shlwapi-l1-1-0!StrTrimW` at `0x1801d0c99`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrTrimW` at `0x1801d0c99`
- `ole32!OleInitialize` at `0x1801d0c11`
- `ole32!OleInitialize` at `0x1801d0c11`
- `ole32!OleUninitialize` at `0x1801d0d3f`
- `ole32!OleUninitialize` at `0x1801d0d3f`
- `iertutil!__imp_?IsElevatedProcess@@YAHXZ` at `0x1801d0c25`
- `iertutil!__imp_?IsElevatedProcess@@YAHXZ` at `0x1801d0c25`
- `iertutil!__imp_?IAS_Close@@YAXXZ` at `0x1801d0d4b`
- `iertutil!__imp_?IAS_Close@@YAXXZ` at `0x1801d0d4b`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x1801d0cca`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x1801d0cca`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1801d0bd2`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1801d0be7`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1801d0c3f`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1801d0d71`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1801d0bd2`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1801d0be7`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1801d0c3f`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1801d0d71`
- `iertutil!__imp_?IEConfiguration_SetBool@@YAJW4IEConfigurationID@@_N@Z` at `0x1801d0d1d`
- `iertutil!__imp_?IEConfiguration_SetBool@@YAJW4IEConfigurationID@@_N@Z` at `0x1801d0db1`
- `iertutil!__imp_?IEConfiguration_SetBool@@YAJW4IEConfigurationID@@_N@Z` at `0x1801d0d1d`
- `iertutil!__imp_?IEConfiguration_SetBool@@YAJW4IEConfigurationID@@_N@Z` at `0x1801d0db1`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x1801d0d91`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x1801d0d91`
- `iertutil!__imp_?IEConfiguration_GetString@@YAPEBGW4IEConfigurationID@@@Z` at `0x1801d0caa`
- `iertutil!__imp_?IEConfiguration_GetString@@YAPEBGW4IEConfigurationID@@@Z` at `0x1801d0caa`

## pseudocode

```c
__int64 __fastcall LCIEInitializeAsFrame(unsigned __int16 *a1)
{
  int IEFrameProcessConfiguration; // ebx
  int v3; // edi
  const unsigned __int16 *String; // rax
  __int64 v5; // rdx
  __int64 v7; // rcx
  bool v8; // [rsp+38h] [rbp+10h] BYREF

  IEFrameProcessConfiguration = CreateIEFrameProcessConfiguration(a1);
  if ( IEFrameProcessConfiguration < 0
    || (unsigned __int8)IEConfiguration_GetBool(536870913) && (unsigned __int8)IEConfiguration_GetBool(536870916) )
  {
    return (unsigned int)IEFrameProcessConfiguration;
  }
  SetProcessDpiAwareness();
  IESetProcessExports();
  UpdateGlobalCompatibilityFlags();
  AttachShims();
  if ( OleInitialize(0) < 0 )
  {
LABEL_25:
    IAS_Close();
    return (unsigned int)IEFrameProcessConfiguration;
  }
  if ( !IsElevatedProcess() )
    InitializeCOMSecurity_ForFrameProcess();
  if ( !(unsigned __int8)IEConfiguration_GetBool(268435465) )
  {
    IEFrameProcessConfiguration = 0;
    if ( !(unsigned __int8)IEConfiguration_GetBool(268435468) )
      return (unsigned int)IEFrameProcessConfiguration;
    IEFrameProcessConfiguration = IEAutomationManagerInitialize();
    if ( IEFrameProcessConfiguration < 0 )
      goto LABEL_24;
    if ( (IEConfiguration_GetDWORD(268435469) & 1) != 0 )
    {
      LOBYTE(v7) = 1;
      SetHangRecoveryOptions(v7, 0);
      IEConfiguration_SetBool(268435460, 0);
    }
    return (unsigned int)IEFrameProcessConfiguration;
  }
  if ( FindAndRemoveBooleanCommandLineOption(15, L"-wFRunStartMenu", a1) )
  {
    v3 = 2;
  }
  else
  {
    v3 = 0;
    if ( !FindAndRemoveBooleanCommandLineOption(14, L"-wFRunDragDrop", a1) )
      goto LABEL_13;
    v3 = 1;
  }
  StrTrimW(a1, asc_180619510);
LABEL_13:
  String = (const unsigned __int16 *)IEConfiguration_GetString(268435466);
  IEFrameProcessConfiguration = CSiteModeInfo::_Init(String);
  if ( IEFrameProcessConfiguration >= 0 )
  {
    CSiteModeInfo::s_SiteModeFirstRun = v3;
    if ( (!LCIEIsCurrentProcessInPrivate() && !CSiteModeInfo::s_fInPrivate || CSiteModeInfo::s_SiteModeFirstRun)
      && CSiteModeInfo::s_fInit )
    {
      CSiteModeInfo::s_fDestinationListDirty = 1;
    }
    v8 = 0;
    IEFrameProcessConfiguration = CSiteModeInfo::GetInPrivate(&v8);
    if ( IEFrameProcessConfiguration < 0 )
      goto LABEL_24;
    LOBYTE(v5) = v8;
    if ( v8 )
    {
      IEFrameProcessConfiguration = IEConfiguration_SetBool(268435462, v5);
      if ( IEFrameProcessConfiguration < 0 )
      {
LABEL_24:
        OleUninitialize();
        goto LABEL_25;
      }
      IEFrameProcessConfiguration = DisableTelemetryForCurrentProcess(2);
    }
  }
  if ( IEFrameProcessConfiguration < 0 )
    goto LABEL_24;
  return (unsigned int)IEFrameProcessConfiguration;
}

```

## disassembly

```asm
0x1801d0bac  mov     [rsp+arg_0], rbx
0x1801d0bb1  mov     [rsp+arg_10], rsi
0x1801d0bb6  push    rdi
0x1801d0bb7  sub     rsp, 20h
0x1801d0bbb  mov     rsi, rcx
0x1801d0bbe  call    _CreateIEFrameProcessConfiguration
0x1801d0bc3  mov     ebx, eax
0x1801d0bc5  test    eax, eax
0x1801d0bc7  js      loc_1801D0D57
0x1801d0bcd  mov     ecx, 20000001h
0x1801d0bd2  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1801d0bd9  nop     dword ptr [rax+rax+00h]
0x1801d0bde  test    al, al
0x1801d0be0  jz      short loc_1801D0BFB
0x1801d0be2  mov     ecx, 20000004h
0x1801d0be7  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1801d0bee  nop     dword ptr [rax+rax+00h]
0x1801d0bf3  test    al, al
0x1801d0bf5  jnz     loc_1801D0D57
0x1801d0bfb  call    ?SetProcessDpiAwareness@@YAXXZ; SetProcessDpiAwareness(void)
0x1801d0c00  call    ?IESetProcessExports@@YAXXZ; IESetProcessExports(void)
0x1801d0c05  call    ?UpdateGlobalCompatibilityFlags@@YAXXZ; UpdateGlobalCompatibilityFlags(void)
0x1801d0c0a  call    ?AttachShims@@YA_NXZ; AttachShims(void)
0x1801d0c0f  xor     ecx, ecx; pvReserved
0x1801d0c11  call    cs:__imp_OleInitialize
0x1801d0c18  nop     dword ptr [rax+rax+00h]
0x1801d0c1d  test    eax, eax
0x1801d0c1f  js      loc_1801D0D4B
0x1801d0c25  call    cs:__imp_?IsElevatedProcess@@YAHXZ; IsElevatedProcess(void)
0x1801d0c2c  nop     dword ptr [rax+rax+00h]
0x1801d0c31  test    eax, eax
0x1801d0c33  jnz     short loc_1801D0C3A
0x1801d0c35  call    _InitializeCOMSecurity_ForFrameProcess
0x1801d0c3a  mov     ecx, 10000009h
0x1801d0c3f  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1801d0c46  nop     dword ptr [rax+rax+00h]
0x1801d0c4b  test    al, al
0x1801d0c4d  jz      loc_1801D0D6A
0x1801d0c53  mov     r8, rsi; unsigned __int16 *
0x1801d0c56  lea     rdx, aWfrunstartmenu; "-wFRunStartMenu"
0x1801d0c5d  mov     ecx, 0Fh; int
0x1801d0c62  call    ?FindAndRemoveBooleanCommandLineOption@@YA_NHPEAG0@Z; FindAndRemoveBooleanCommandLineOption(int,ushort *,ushort *)
0x1801d0c67  test    al, al
0x1801d0c69  jz      short loc_1801D0C72
0x1801d0c6b  mov     edi, 2
0x1801d0c70  jmp     short loc_1801D0C8F
0x1801d0c72  xor     edi, edi
0x1801d0c74  lea     rdx, aWfrundragdrop; "-wFRunDragDrop"
0x1801d0c7b  mov     r8, rsi; unsigned __int16 *
0x1801d0c7e  lea     ecx, [rdi+0Eh]; int
0x1801d0c81  call    ?FindAndRemoveBooleanCommandLineOption@@YA_NHPEAG0@Z; FindAndRemoveBooleanCommandLineOption(int,ushort *,ushort *)
0x1801d0c86  test    al, al
0x1801d0c88  jz      short loc_1801D0CA5
0x1801d0c8a  mov     edi, 1
0x1801d0c8f  lea     rdx, asc_180619510; " \t"
0x1801d0c96  mov     rcx, rsi; psz
0x1801d0c99  call    cs:__imp_StrTrimW
0x1801d0ca0  nop     dword ptr [rax+rax+00h]
0x1801d0ca5  mov     ecx, 1000000Ah
0x1801d0caa  call    cs:__imp_?IEConfiguration_GetString@@YAPEBGW4IEConfigurationID@@@Z; IEConfiguration_GetString(IEConfigurationID)
0x1801d0cb1  nop     dword ptr [rax+rax+00h]
0x1801d0cb6  mov     rcx, rax; unsigned __int16 *
0x1801d0cb9  call    ?_Init@CSiteModeInfo@@CAJPEBG@Z; CSiteModeInfo::_Init(ushort const *)
0x1801d0cbe  mov     ebx, eax
0x1801d0cc0  test    eax, eax
0x1801d0cc2  js      short loc_1801D0D3B
0x1801d0cc4  mov     cs:?s_SiteModeFirstRun@CSiteModeInfo@@0W4SM_FIRSTRUNTYPE@@A, edi; SM_FIRSTRUNTYPE CSiteModeInfo::s_SiteModeFirstRun
0x1801d0cca  call    cs:__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ; LCIEIsCurrentProcessInPrivate(void)
0x1801d0cd1  nop     dword ptr [rax+rax+00h]
0x1801d0cd6  test    al, al
0x1801d0cd8  jnz     short loc_1801D0CE2
0x1801d0cda  cmp     cs:?s_fInPrivate@CSiteModeInfo@@0_NA, al; bool CSiteModeInfo::s_fInPrivate
0x1801d0ce0  jz      short loc_1801D0CEB
0x1801d0ce2  cmp     cs:?s_SiteModeFirstRun@CSiteModeInfo@@0W4SM_FIRSTRUNTYPE@@A, 0; SM_FIRSTRUNTYPE CSiteModeInfo::s_SiteModeFirstRun
0x1801d0ce9  jz      short loc_1801D0CFB
0x1801d0ceb  cmp     cs:?s_fInit@CSiteModeInfo@@0_NA, 0; bool CSiteModeInfo::s_fInit
0x1801d0cf2  jz      short loc_1801D0CFB
0x1801d0cf4  mov     cs:?s_fDestinationListDirty@CSiteModeInfo@@0_NA, 1; bool CSiteModeInfo::s_fDestinationListDirty
0x1801d0cfb  lea     rcx, [rsp+28h+arg_8]; bool *
0x1801d0d00  mov     [rsp+28h+arg_8], 0
0x1801d0d05  call    ?GetInPrivate@CSiteModeInfo@@SAJPEA_N@Z; CSiteModeInfo::GetInPrivate(bool *)
0x1801d0d0a  mov     ebx, eax
0x1801d0d0c  test    eax, eax
0x1801d0d0e  js      short loc_1801D0D3F
0x1801d0d10  mov     dl, [rsp+28h+arg_8]
0x1801d0d14  test    dl, dl
0x1801d0d16  jz      short loc_1801D0D3B
0x1801d0d18  mov     ecx, 10000006h
0x1801d0d1d  call    cs:__imp_?IEConfiguration_SetBool@@YAJW4IEConfigurationID@@_N@Z; IEConfiguration_SetBool(IEConfigurationID,bool)
0x1801d0d24  nop     dword ptr [rax+rax+00h]
0x1801d0d29  mov     ebx, eax
0x1801d0d2b  test    eax, eax
0x1801d0d2d  js      short loc_1801D0D3F
0x1801d0d2f  mov     ecx, 2
0x1801d0d34  call    ?DisableTelemetryForCurrentProcess@@YAJW4MarkProcessTelemetryStateFailed_Trigger@@@Z; DisableTelemetryForCurrentProcess(MarkProcessTelemetryStateFailed_Trigger)
0x1801d0d39  mov     ebx, eax
0x1801d0d3b  test    ebx, ebx
0x1801d0d3d  jns     short loc_1801D0D57
0x1801d0d3f  call    cs:__imp_OleUninitialize
0x1801d0d46  nop     dword ptr [rax+rax+00h]
0x1801d0d4b  call    cs:__imp_?IAS_Close@@YAXXZ; IAS_Close(void)
0x1801d0d52  nop     dword ptr [rax+rax+00h]
0x1801d0d57  mov     rsi, [rsp+28h+arg_10]
0x1801d0d5c  mov     eax, ebx
0x1801d0d5e  mov     rbx, [rsp+28h+arg_0]
0x1801d0d63  add     rsp, 20h
0x1801d0d67  pop     rdi
0x1801d0d68  retn
0x1801d0d6a  mov     ecx, 1000000Ch
0x1801d0d6f  xor     ebx, ebx
0x1801d0d71  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1801d0d78  nop     dword ptr [rax+rax+00h]
0x1801d0d7d  test    al, al
0x1801d0d7f  jz      short loc_1801D0D57
0x1801d0d81  call    ?IEAutomationManagerInitialize@@YAJXZ; IEAutomationManagerInitialize(void)
0x1801d0d86  mov     ebx, eax
0x1801d0d88  test    eax, eax
0x1801d0d8a  js      short loc_1801D0D3F
0x1801d0d8c  mov     ecx, 1000000Dh
0x1801d0d91  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x1801d0d98  nop     dword ptr [rax+rax+00h]
0x1801d0d9d  test    al, 1
0x1801d0d9f  jz      short loc_1801D0D57
0x1801d0da1  xor     edx, edx
0x1801d0da3  mov     cl, 1
0x1801d0da5  call    _SetHangRecoveryOptions
0x1801d0daa  xor     edx, edx
0x1801d0dac  mov     ecx, 10000004h
0x1801d0db1  call    cs:__imp_?IEConfiguration_SetBool@@YAJW4IEConfigurationID@@_N@Z; IEConfiguration_SetBool(IEConfigurationID,bool)
0x1801d0db8  nop     dword ptr [rax+rax+00h]
0x1801d0dbd  jmp     short loc_1801D0D57
```
