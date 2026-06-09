# CDwmAppHost::Initialize(HINSTANCE__ *)

- ea: `0x140002fbc`
- end: `0x1400031d8`
- name: `?Initialize@CDwmAppHost@@QEAAJPEAUHINSTANCE__@@@Z`
- size: `540`
- prototype: `__int64 __fastcall(CDwmAppHost *__hidden this, HINSTANCE)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14000215c`

## callees

- `0x140001fb0`
- `0x140002988`
- `0x140002e6c`
- `0x140002fbc`
- `0x140003d40`
- `0x140006304`
- `0x1400065cc`
- `0x14000c514`
- `0x14000cb90`
- `0x14000cc90`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000302f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000302f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003046`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000312a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003046`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000312a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140002fcd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140002fcd`
- `api-ms-win-composition-redirection-l1-1-0!DwmInitializePort` at `0x140003010`
- `api-ms-win-composition-redirection-l1-1-0!DwmInitializePort` at `0x140003010`
- `api-ms-win-rtcore-ntuser-private-l1-1-0!RegisterSessionPort` at `0x14000303c`
- `api-ms-win-rtcore-ntuser-private-l1-1-0!RegisterSessionPort` at `0x14000303c`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1400030f7`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1400030f7`
- `ext-ms-win-ntuser-keyboard-l1-1-0!RegisterHotKey` at `0x140003120`
- `ext-ms-win-ntuser-keyboard-l1-1-0!RegisterHotKey` at `0x140003120`
- `ext-ms-win-composition-ghost-l1-1-0!DWMGhostInitialize` at `0x1400030d7`
- `ext-ms-win-composition-ghost-l1-1-0!DWMGhostInitialize` at `0x1400030d7`

## pseudocode

```c
__int64 __fastcall CDwmAppHost::Initialize(CDwmAppHost *this, HINSTANCE a2)
{
  CDwmAppHost *v2; // rcx
  int v3; // eax
  unsigned int v4; // ebx
  CDwmAppHost *v5; // rcx
  signed int LastError; // eax
  CDwmAppHost *v7; // rcx
  signed int v8; // eax
  CDwmAppHost *v9; // rcx
  __int64 v10; // rcx
  signed int v11; // eax
  CDwmAppHost *v12; // rcx
  const unsigned __int16 *v14; // [rsp+20h] [rbp-18h]
  unsigned int v15; // [rsp+20h] [rbp-18h]
  CDwmAppHost *v16; // [rsp+40h] [rbp+8h] BYREF

  v16 = this;
  hInstance = a2;
  HIDWORD(qword_14001C060) = GetCurrentThreadId();
  CSettingsManager::RefreshPreferencesAndPolicies((CSettingsManager *)&qword_14001C078);
  v3 = CDwmAppHost::InitializeWindow(v2);
  v4 = v3;
  if ( v3 < 0 )
  {
    v15 = 43;
    goto LABEL_26;
  }
  v3 = DwmInitializePort(&g_dwmAppHost, CDwmAppHost::s_LpcCommandHandler, &hInstance + 1, &dword_14001C068);
  v4 = v3;
  if ( v3 < 0 )
  {
    v15 = 46;
LABEL_26:
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, &qword_140012DB0, 2u, v3, v15, 0);
    return v4;
  }
  if ( !dword_14001C068 )
  {
    SetLastError(0);
    if ( !(unsigned int)RegisterSessionPort(*(&hInstance + 1)) )
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      if ( (v4 & 0x80000000) == 0 )
        v4 = -2003304445;
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, &qword_140012DB0, 2u, v4, 0x36u, 0);
      CDwmAppHost::ReportEventWithDword(v7, 1u, 0xC0002344, v4);
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, &qword_140012DB0, 2u, v4, 0x42u, 0);
      return v4;
    }
    CDwmAppHost::ReportEventW(v5, 4u, 0x40002343u, 0, v14);
  }
  if ( (unsigned __int8)IsDWMGhostHandleGhostMsgPresent() )
  {
    DWMGhostInitialize();
    *(&uExitCode + 1) = 1;
  }
  v4 = 0;
  LODWORD(v16) = 0;
  RtlGetDeviceFamilyInfoEnum(0, &v16, 0);
  if ( (unsigned __int8)IsRegisterHotKeyPresent() && (_DWORD)v16 == 3 && !RegisterHotKey(hWnd, 0, 0x400Eu, 0x42u) )
  {
    v8 = GetLastError();
    if ( v8 > 0 )
      v8 = (unsigned __int16)v8 | 0x80070000;
    CDwmAppHost::ReportEventWithDword(v9, 2u, 0x8000234B, v8);
  }
  if ( (_DWORD)v16 == 16 )
  {
    v10 = g_spHotkeyCallback;
    g_spHotkeyCallback = 0;
    if ( v10 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Internal::Text::IHotKeyClientOwner>::Release();
    v11 = Microsoft::WRL::Details::MakeAndInitialize<HotKeyCallback,HotKeyCallback,>(&g_spHotkeyCallback);
    if ( v11 < 0 )
      CDwmAppHost::ReportEventWithDword(v12, 2u, 0x8000234B, v11);
  }
  return v4;
}

```

## disassembly

```asm
0x140002fbc  mov     [rsp+arg_0], rcx
0x140002fc1  push    rbx
0x140002fc2  sub     rsp, 30h
0x140002fc6  mov     qword ptr cs:hInstance, rdx
0x140002fcd  call    cs:__imp_GetCurrentThreadId
0x140002fd3  lea     rcx, qword_14001C078; this
0x140002fda  mov     dword ptr cs:qword_14001C060+4, eax
0x140002fe0  call    ?RefreshPreferencesAndPolicies@CSettingsManager@@QEAAXXZ; CSettingsManager::RefreshPreferencesAndPolicies(void)
0x140002fe5  call    ?InitializeWindow@CDwmAppHost@@AEAAJXZ; CDwmAppHost::InitializeWindow(void)
0x140002fea  mov     ebx, eax
0x140002fec  test    eax, eax
0x140002fee  js      loc_1400031A6
0x140002ff4  lea     r9, dword_14001C068
0x140002ffb  lea     r8, hInstance+8
0x140003002  lea     rdx, ?s_LpcCommandHandler@CDwmAppHost@@CAJPEAUIPortMessage@@PEBUPORT_CONTEXT@@PEAH2@Z; CDwmAppHost::s_LpcCommandHandler(IPortMessage *,PORT_CONTEXT const *,int *,int *)
0x140003009  lea     rcx, ?g_dwmAppHost@@3VCDwmAppHost@@A; CDwmAppHost g_dwmAppHost
0x140003010  call    cs:__imp_DwmInitializePort
0x140003016  mov     ebx, eax
0x140003018  test    eax, eax
0x14000301a  js      loc_140003193
0x140003020  cmp     cs:dword_14001C068, 0
0x140003027  jnz     loc_1400030CE
0x14000302d  xor     ecx, ecx; dwErrCode
0x14000302f  call    cs:__imp_SetLastError
0x140003035  mov     rcx, qword ptr cs:hInstance+8
0x14000303c  call    cs:__imp_RegisterSessionPort
0x140003042  test    eax, eax
0x140003044  jnz     short loc_1400030BB
0x140003046  call    cs:__imp_GetLastError
0x14000304c  mov     ebx, eax
0x14000304e  test    eax, eax
0x140003050  jle     short loc_14000305B
0x140003052  movzx   ebx, ax
0x140003055  or      ebx, 80070000h
0x14000305b  mov     r8d, 2; unsigned int
0x140003061  mov     [rsp+38h+var_10], 0; void *
0x14000306a  mov     eax, 88980003h
0x14000306f  mov     dword ptr [rsp+38h+var_18], 36h ; '6'; unsigned int
0x140003077  test    ebx, ebx
0x140003079  lea     rdx, qword_140012DB0; int *
0x140003080  cmovns  ebx, eax
0x140003083  lea     ecx, [r8+12h]; unsigned int
0x140003087  mov     r9d, ebx; int
0x14000308a  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x14000308f  mov     edx, 1; unsigned __int16
0x140003094  mov     r9d, ebx; unsigned int
0x140003097  mov     r8d, 0C0002344h; unsigned int
0x14000309d  call    ?ReportEventWithDword@CDwmAppHost@@AEAAXGKK@Z; CDwmAppHost::ReportEventWithDword(ushort,ulong,ulong)
0x1400030a2  mov     [rsp+38h+var_10], 0
0x1400030ab  mov     r9d, ebx
0x1400030ae  mov     dword ptr [rsp+38h+var_18], 42h ; 'B'
0x1400030b6  jmp     loc_1400031BA
0x1400030bb  mov     edx, 4; unsigned __int16
0x1400030c0  xor     r9d, r9d; unsigned __int16 *
0x1400030c3  mov     r8d, 40002343h; unsigned int
0x1400030c9  call    ?ReportEventW@CDwmAppHost@@AEAAXGKPEBG0@Z; CDwmAppHost::ReportEventW(ushort,ulong,ushort const *,ushort const *)
0x1400030ce  call    IsDWMGhostHandleGhostMsgPresent
0x1400030d3  test    al, al
0x1400030d5  jz      short loc_1400030E7
0x1400030d7  call    cs:__imp_DWMGhostInitialize
0x1400030dd  mov     dword ptr cs:uExitCode+4, 1
0x1400030e7  xor     ebx, ebx
0x1400030e9  lea     rdx, [rsp+38h+arg_0]
0x1400030ee  xor     r8d, r8d
0x1400030f1  mov     dword ptr [rsp+38h+arg_0], ebx
0x1400030f5  xor     ecx, ecx
0x1400030f7  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x1400030fd  call    IsRegisterHotKeyPresent
0x140003102  test    al, al
0x140003104  jz      short loc_14000314F
0x140003106  cmp     dword ptr [rsp+38h+arg_0], 3
0x14000310b  jnz     short loc_14000314F
0x14000310d  mov     rcx, cs:hWnd; hWnd
0x140003114  lea     r9d, [rbx+42h]; vk
0x140003118  xor     edx, edx; id
0x14000311a  mov     r8d, 400Eh; fsModifiers
0x140003120  call    cs:__imp_RegisterHotKey
0x140003126  test    eax, eax
0x140003128  jnz     short loc_14000314F
0x14000312a  call    cs:__imp_GetLastError
0x140003130  test    eax, eax
0x140003132  jle     short loc_14000313C
0x140003134  movzx   eax, ax
0x140003137  or      eax, 80070000h
0x14000313c  mov     edx, 2; unsigned __int16
0x140003141  mov     r9d, eax; unsigned int
0x140003144  mov     r8d, 8000234Bh; unsigned int
0x14000314a  call    ?ReportEventWithDword@CDwmAppHost@@AEAAXGKK@Z; CDwmAppHost::ReportEventWithDword(ushort,ulong,ulong)
0x14000314f  cmp     dword ptr [rsp+38h+arg_0], 10h
0x140003154  jnz     short loc_1400031D0
0x140003156  mov     rcx, cs:?g_spHotkeyCallback@@3V?$com_ptr_t@VHotKeyCallback@@Uerr_returncode_policy@wil@@@wil@@A; wil::com_ptr_t<HotKeyCallback,wil::err_returncode_policy> g_spHotkeyCallback
0x14000315d  mov     cs:?g_spHotkeyCallback@@3V?$com_ptr_t@VHotKeyCallback@@Uerr_returncode_policy@wil@@@wil@@A, rbx; wil::com_ptr_t<HotKeyCallback,wil::err_returncode_policy> g_spHotkeyCallback
0x140003164  test    rcx, rcx
0x140003167  jz      short loc_14000316E
0x140003169  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIHotKeyClientOwner@Text@Internal@UI@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Internal::Text::IHotKeyClientOwner>::Release(void)
0x14000316e  lea     rcx, ?g_spHotkeyCallback@@3V?$com_ptr_t@VHotKeyCallback@@Uerr_returncode_policy@wil@@@wil@@A; wil::com_ptr_t<HotKeyCallback,wil::err_returncode_policy> g_spHotkeyCallback
0x140003175  call    ??$MakeAndInitialize@VHotKeyCallback@@V1@$$V@Details@WRL@Microsoft@@YAJPEAPEAVHotKeyCallback@@@Z; Microsoft::WRL::Details::MakeAndInitialize<HotKeyCallback,HotKeyCallback,>(HotKeyCallback * *)
0x14000317a  test    eax, eax
0x14000317c  jns     short loc_1400031D0
0x14000317e  mov     edx, 2; unsigned __int16
0x140003183  mov     r9d, eax; unsigned int
0x140003186  mov     r8d, 8000234Bh; unsigned int
0x14000318c  call    ?ReportEventWithDword@CDwmAppHost@@AEAAXGKK@Z; CDwmAppHost::ReportEventWithDword(ushort,ulong,ulong)
0x140003191  jmp     short loc_1400031D0
0x140003193  mov     [rsp+38h+var_10], 0
0x14000319c  mov     dword ptr [rsp+38h+var_18], 2Eh ; '.'
0x1400031a4  jmp     short loc_1400031B7
0x1400031a6  mov     [rsp+38h+var_10], 0; void *
0x1400031af  mov     dword ptr [rsp+38h+var_18], 2Bh ; '+'; unsigned int
0x1400031b7  mov     r9d, eax; int
0x1400031ba  mov     r8d, 2; unsigned int
0x1400031c0  lea     rdx, qword_140012DB0; int *
0x1400031c7  lea     ecx, [r8+12h]; unsigned int
0x1400031cb  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1400031d0  mov     eax, ebx
0x1400031d2  add     rsp, 30h
0x1400031d6  pop     rbx
0x1400031d7  retn
```
