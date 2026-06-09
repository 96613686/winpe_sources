# LCIEInitializeAsFrame(ushort *)

- ea: `0x1801baa0c`
- end: `0x1801babca`
- name: `?LCIEInitializeAsFrame@@YAJPEAG@Z`
- size: `446`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800a3df4`

## callees

- `0x18009aed0`
- `0x1800eeda8`
- `0x1800f38f0`
- `0x1801054b8`
- `0x18011bb1c`
- `0x1801b85b4`
- `0x1801baa0c`
- `0x1801bcf7c`
- `0x1801bd464`
- `0x1801be144`
- `0x1801be8c8`
- `0x1801cd94c`
- `0x1802479e8`

## import_xrefs

- `api-ms-win-downlevel-shlwapi-l1-1-0!StrTrimW` at `0x1801baadb`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrTrimW` at `0x1801baadb`
- `ole32!OleInitialize` at `0x1801baa65`
- `ole32!OleInitialize` at `0x1801baa65`
- `ole32!OleUninitialize` at `0x1801bab69`
- `ole32!OleUninitialize` at `0x1801bab69`
- `iertutil!__imp_?IsElevatedProcess@@YAHXZ` at `0x1801baa73`
- `iertutil!__imp_?IsElevatedProcess@@YAHXZ` at `0x1801baa73`
- `iertutil!__imp_?IAS_Close@@YAXXZ` at `0x1801bab6f`
- `iertutil!__imp_?IAS_Close@@YAXXZ` at `0x1801bab6f`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x1801bab00`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x1801bab00`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1801baa32`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1801baa41`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1801baa87`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1801bab8e`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1801baa32`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1801baa41`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1801baa87`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1801bab8e`
- `iertutil!__imp_?IEConfiguration_SetBool@@YAJW4IEConfigurationID@@_N@Z` at `0x1801bab4d`
- `iertutil!__imp_?IEConfiguration_SetBool@@YAJW4IEConfigurationID@@_N@Z` at `0x1801babc2`
- `iertutil!__imp_?IEConfiguration_SetBool@@YAJW4IEConfigurationID@@_N@Z` at `0x1801bab4d`
- `iertutil!__imp_?IEConfiguration_SetBool@@YAJW4IEConfigurationID@@_N@Z` at `0x1801babc2`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x1801baba8`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x1801baba8`
- `iertutil!__imp_?IEConfiguration_GetString@@YAPEBGW4IEConfigurationID@@@Z` at `0x1801baae6`
- `iertutil!__imp_?IEConfiguration_GetString@@YAPEBGW4IEConfigurationID@@@Z` at `0x1801baae6`

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
  StrTrimW(a1, asc_1805D56C0);
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
0x1801baa0c  mov     [rsp+arg_0], rbx
0x1801baa11  mov     [rsp+arg_10], rsi
0x1801baa16  push    rdi
0x1801baa17  sub     rsp, 20h
0x1801baa1b  mov     rsi, rcx
0x1801baa1e  call    _CreateIEFrameProcessConfiguration
0x1801baa23  mov     ebx, eax
0x1801baa25  test    eax, eax
0x1801baa27  js      loc_1801BAB75
0x1801baa2d  mov     ecx, 20000001h
0x1801baa32  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1801baa38  test    al, al
0x1801baa3a  jz      short loc_1801BAA4F
0x1801baa3c  mov     ecx, 20000004h
0x1801baa41  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1801baa47  test    al, al
0x1801baa49  jnz     loc_1801BAB75
0x1801baa4f  call    ?SetProcessDpiAwareness@@YAXXZ; SetProcessDpiAwareness(void)
0x1801baa54  call    ?IESetProcessExports@@YAXXZ; IESetProcessExports(void)
0x1801baa59  call    ?UpdateGlobalCompatibilityFlags@@YAXXZ; UpdateGlobalCompatibilityFlags(void)
0x1801baa5e  call    ?AttachShims@@YA_NXZ; AttachShims(void)
0x1801baa63  xor     ecx, ecx; pvReserved
0x1801baa65  call    cs:__imp_OleInitialize
0x1801baa6b  test    eax, eax
0x1801baa6d  js      loc_1801BAB6F
0x1801baa73  call    cs:__imp_?IsElevatedProcess@@YAHXZ; IsElevatedProcess(void)
0x1801baa79  test    eax, eax
0x1801baa7b  jnz     short loc_1801BAA82
0x1801baa7d  call    _InitializeCOMSecurity_ForFrameProcess
0x1801baa82  mov     ecx, 10000009h
0x1801baa87  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1801baa8d  test    al, al
0x1801baa8f  jz      loc_1801BAB87
0x1801baa95  mov     r8, rsi; unsigned __int16 *
0x1801baa98  lea     rdx, aWfrunstartmenu; "-wFRunStartMenu"
0x1801baa9f  mov     ecx, 0Fh; int
0x1801baaa4  call    ?FindAndRemoveBooleanCommandLineOption@@YA_NHPEAG0@Z; FindAndRemoveBooleanCommandLineOption(int,ushort *,ushort *)
0x1801baaa9  test    al, al
0x1801baaab  jz      short loc_1801BAAB4
0x1801baaad  mov     edi, 2
0x1801baab2  jmp     short loc_1801BAAD1
0x1801baab4  xor     edi, edi
0x1801baab6  lea     rdx, aWfrundragdrop; "-wFRunDragDrop"
0x1801baabd  mov     r8, rsi; unsigned __int16 *
0x1801baac0  lea     ecx, [rdi+0Eh]; int
0x1801baac3  call    ?FindAndRemoveBooleanCommandLineOption@@YA_NHPEAG0@Z; FindAndRemoveBooleanCommandLineOption(int,ushort *,ushort *)
0x1801baac8  test    al, al
0x1801baaca  jz      short loc_1801BAAE1
0x1801baacc  mov     edi, 1
0x1801baad1  lea     rdx, asc_1805D56C0; " \t"
0x1801baad8  mov     rcx, rsi; psz
0x1801baadb  call    cs:__imp_StrTrimW
0x1801baae1  mov     ecx, 1000000Ah
0x1801baae6  call    cs:__imp_?IEConfiguration_GetString@@YAPEBGW4IEConfigurationID@@@Z; IEConfiguration_GetString(IEConfigurationID)
0x1801baaec  mov     rcx, rax; unsigned __int16 *
0x1801baaef  call    ?_Init@CSiteModeInfo@@CAJPEBG@Z; CSiteModeInfo::_Init(ushort const *)
0x1801baaf4  mov     ebx, eax
0x1801baaf6  test    eax, eax
0x1801baaf8  js      short loc_1801BAB65
0x1801baafa  mov     cs:?s_SiteModeFirstRun@CSiteModeInfo@@0W4SM_FIRSTRUNTYPE@@A, edi; SM_FIRSTRUNTYPE CSiteModeInfo::s_SiteModeFirstRun
0x1801bab00  call    cs:__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ; LCIEIsCurrentProcessInPrivate(void)
0x1801bab06  test    al, al
0x1801bab08  jnz     short loc_1801BAB12
0x1801bab0a  cmp     cs:?s_fInPrivate@CSiteModeInfo@@0_NA, al; bool CSiteModeInfo::s_fInPrivate
0x1801bab10  jz      short loc_1801BAB1B
0x1801bab12  cmp     cs:?s_SiteModeFirstRun@CSiteModeInfo@@0W4SM_FIRSTRUNTYPE@@A, 0; SM_FIRSTRUNTYPE CSiteModeInfo::s_SiteModeFirstRun
0x1801bab19  jz      short loc_1801BAB2B
0x1801bab1b  cmp     cs:?s_fInit@CSiteModeInfo@@0_NA, 0; bool CSiteModeInfo::s_fInit
0x1801bab22  jz      short loc_1801BAB2B
0x1801bab24  mov     cs:?s_fDestinationListDirty@CSiteModeInfo@@0_NA, 1; bool CSiteModeInfo::s_fDestinationListDirty
0x1801bab2b  lea     rcx, [rsp+28h+arg_8]; bool *
0x1801bab30  mov     [rsp+28h+arg_8], 0
0x1801bab35  call    ?GetInPrivate@CSiteModeInfo@@SAJPEA_N@Z; CSiteModeInfo::GetInPrivate(bool *)
0x1801bab3a  mov     ebx, eax
0x1801bab3c  test    eax, eax
0x1801bab3e  js      short loc_1801BAB69
0x1801bab40  mov     dl, [rsp+28h+arg_8]
0x1801bab44  test    dl, dl
0x1801bab46  jz      short loc_1801BAB65
0x1801bab48  mov     ecx, 10000006h
0x1801bab4d  call    cs:__imp_?IEConfiguration_SetBool@@YAJW4IEConfigurationID@@_N@Z; IEConfiguration_SetBool(IEConfigurationID,bool)
0x1801bab53  mov     ebx, eax
0x1801bab55  test    eax, eax
0x1801bab57  js      short loc_1801BAB69
0x1801bab59  mov     ecx, 2
0x1801bab5e  call    ?DisableTelemetryForCurrentProcess@@YAJW4MarkProcessTelemetryStateFailed_Trigger@@@Z; DisableTelemetryForCurrentProcess(MarkProcessTelemetryStateFailed_Trigger)
0x1801bab63  mov     ebx, eax
0x1801bab65  test    ebx, ebx
0x1801bab67  jns     short loc_1801BAB75
0x1801bab69  call    cs:__imp_OleUninitialize
0x1801bab6f  call    cs:__imp_?IAS_Close@@YAXXZ; IAS_Close(void)
0x1801bab75  mov     rsi, [rsp+28h+arg_10]
0x1801bab7a  mov     eax, ebx
0x1801bab7c  mov     rbx, [rsp+28h+arg_0]
0x1801bab81  add     rsp, 20h
0x1801bab85  pop     rdi
0x1801bab86  retn
0x1801bab87  mov     ecx, 1000000Ch
0x1801bab8c  xor     ebx, ebx
0x1801bab8e  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1801bab94  test    al, al
0x1801bab96  jz      short loc_1801BAB75
0x1801bab98  call    ?IEAutomationManagerInitialize@@YAJXZ; IEAutomationManagerInitialize(void)
0x1801bab9d  mov     ebx, eax
0x1801bab9f  test    eax, eax
0x1801baba1  js      short loc_1801BAB69
0x1801baba3  mov     ecx, 1000000Dh
0x1801baba8  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x1801babae  test    al, 1
0x1801babb0  jz      short loc_1801BAB75
0x1801babb2  xor     edx, edx
0x1801babb4  mov     cl, 1
0x1801babb6  call    _SetHangRecoveryOptions
0x1801babbb  xor     edx, edx
0x1801babbd  mov     ecx, 10000004h
0x1801babc2  call    cs:__imp_?IEConfiguration_SetBool@@YAJW4IEConfigurationID@@_N@Z; IEConfiguration_SetBool(IEConfigurationID,bool)
0x1801babc8  jmp     short loc_1801BAB75
```
