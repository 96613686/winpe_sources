# BCryptIsoDisableKeyguardProcessCallback

- ea: `0x18003ac40`
- end: `0x18003af49`
- name: `BCryptIsoDisableKeyguardProcessCallback`
- size: `777`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000af80`
- `0x180016ac8`
- `0x18001a1c0`
- `0x18001b154`
- `0x18001b634`
- `0x180023bc8`
- `0x1800248ac`
- `0x18002490c`
- `0x180025ea8`
- `0x18002831c`
- `0x180028a70`
- `0x180036150`
- `0x18003ac40`
- `0x18003f57c`
- `0x18003fd08`
- `0x1800406dc`

## import_xrefs

- `ntdll!RtlDllShutdownInProgress` at `0x18003ae7c`
- `ntdll!RtlDllShutdownInProgress` at `0x18003ae7c`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18003ae24`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18003ae24`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003ac53`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003ac53`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003ae56`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003ae56`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18003adfa`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18003adfa`

## string_xrefs

- `0x18003ad72`: `onecore\ds\security\cryptoapi\ncrypt\ium\lib\bcryptisotrustlet.cpp`
- `0x18003ad9f`: `onecore\ds\security\cryptoapi\ncrypt\ium\lib\bcryptisotrustlet.cpp`
- `0x18003ae3a`: `onecore\ds\security\cryptoapi\ncrypt\ium\lib\bcryptisotrustlet.cpp`

## pseudocode

```c
void __fastcall BCryptIsoDisableKeyguardProcessCallback(
        PTP_CALLBACK_INSTANCE Instance,
        PVOID Context,
        PTP_WAIT Wait,
        TP_WAIT_RESULT WaitResult)
{
  int v4; // ebx
  BOOL IsDisabledInRegistry; // eax
  __int64 v6; // r8
  HANDLE v7; // rdx
  _BOOL8 v8; // r9
  PVOID v9; // rcx
  int v10; // esi
  int v11; // eax
  int v12; // eax
  unsigned int v13; // eax
  __int64 v14; // rcx
  __int64 v15; // r8
  int KGRunningInProdMode; // [rsp+40h] [rbp-38h] BYREF
  __int64 v17; // [rsp+48h] [rbp-30h] BYREF
  __int64 v18; // [rsp+50h] [rbp-28h] BYREF
  __int64 v19; // [rsp+58h] [rbp-20h] BYREF
  _QWORD v20[3]; // [rsp+60h] [rbp-18h] BYREF

  AcquireSRWLockExclusive(&g_servicingLock);
  v4 = 0;
  IsDisabledInRegistry = BCryptIsoIsDisabledInRegistry();
  v7 = hProcess;
  v8 = IsDisabledInRegistry;
  g_keyguardRegistryData = IsDisabledInRegistry;
  if ( IsDisabledInRegistry && hProcess )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_a6b47fe3e7aa3dc67b817b99b29667f9_Traceguids);
    I_BCryptIsoUninitializeRpc(v9, v7, v6, v8);
    BCryptIsoRemoveAndInvalidateAllHandles();
    I_BCryptIsoStopProcess();
    v10 = 1;
  }
  else
  {
    v10 = 0;
    if ( IsDisabledInRegistry || hProcess )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, v6, IsDisabledInRegistry, hProcess != 0);
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_a6b47fe3e7aa3dc67b817b99b29667f9_Traceguids);
      v4 = I_BCryptIsoCheckRpc(0);
      if ( v4 < 0 )
      {
        v10 = 1;
        ((void (*)(void))I_BCryptIsoUninitializeRpc)();
        BCryptIsoRemoveAndInvalidateAllHandles();
        v4 = I_BCryptIsoInitializeRpc();
        if ( v4 < 0 )
        {
          v11 = I_BCryptIsoLaunchKeyGuard();
          if ( v11 >= 0 )
          {
            v12 = I_BCryptIsoInitializeRpc();
            v4 = v12;
            if ( v12 < 0 )
              DebugTraceError(
                (unsigned int)v12,
                "secStatus",
                "onecore\\ds\\security\\cryptoapi\\ncrypt\\ium\\lib\\bcryptisotrustlet.cpp",
                1462);
          }
          else
          {
            DebugTraceError(
              (unsigned int)v11,
              "ntStatus",
              "onecore\\ds\\security\\cryptoapi\\ncrypt\\ium\\lib\\bcryptisotrustlet.cpp",
              1451);
            v4 = -2146893767;
          }
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_a6b47fe3e7aa3dc67b817b99b29667f9_Traceguids);
      }
    }
  }
  SetThreadpoolWait(pwa, hEvent, 0);
  v13 = RegNotifyChangeKeyValue(hKey, 0, 0x10000004u, hEvent, 1);
  if ( v13 )
    DebugTraceError(v13, "lStatus", "onecore\\ds\\security\\cryptoapi\\ncrypt\\ium\\lib\\bcryptisotrustlet.cpp", 1487);
  ReleaseSRWLockExclusive(&g_servicingLock);
  if ( (unsigned int)I_BCryptIsoCanLaunchSecureProcess() )
  {
    if ( g_keyguardRegistryData
      && !RtlDllShutdownInProgress()
      && dword_180079128
      && tlgKeywordOn((__int64)&dword_180079128, 0x800000000000LL) )
    {
      v17 = 2048;
      KGRunningInProdMode = BCryptIsoGetKGRunningInProdMode(&g_keyguardRegistryData);
      v18 = 0;
      v19 = 0;
      v20[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        v14,
        (int)byte_18006FAE1,
        v15,
        (__int64)v20,
        (__int64)&v19,
        (__int64)&v18,
        (__int64)&KGRunningInProdMode,
        (__int64)&v17);
    }
    KGRunningInProdMode = 0;
    I_BCryptIsoCheckRpc(&KGRunningInProdMode);
    KeyGuardTelemetryReportCurrentState(1u, v10, g_keyguardRegistryData, KGRunningInProdMode, v4);
  }
}

```

## disassembly

```asm
0x18003ac40  push    rbp
0x18003ac42  push    rbx
0x18003ac43  push    rsi
0x18003ac44  push    rdi
0x18003ac45  mov     rbp, rsp
0x18003ac48  sub     rsp, 78h
0x18003ac4c  lea     rcx, ?g_servicingLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x18003ac53  call    cs:__imp_AcquireSRWLockExclusive
0x18003ac5a  nop     dword ptr [rax+rax+00h]
0x18003ac5f  xor     ebx, ebx
0x18003ac61  call    ?BCryptIsoIsDisabledInRegistry@@YAHXZ; BCryptIsoIsDisabledInRegistry(void)
0x18003ac66  mov     rdx, cs:hProcess
0x18003ac6d  mov     r9d, eax
0x18003ac70  mov     cs:?g_keyguardRegistryData@@3U_KEYGUARD_REGISTRY_DATA@@A, eax; _KEYGUARD_REGISTRY_DATA g_keyguardRegistryData
0x18003ac76  test    eax, eax
0x18003ac78  jz      short loc_18003ACC4
0x18003ac7a  test    rdx, rdx
0x18003ac7d  jz      short loc_18003ACC4
0x18003ac7f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ac86  lea     rdi, WPP_GLOBAL_Control
0x18003ac8d  cmp     rcx, rdi
0x18003ac90  jz      short loc_18003ACAB
0x18003ac92  test    byte ptr [rcx+1Ch], 8
0x18003ac96  jz      short loc_18003ACAB
0x18003ac98  mov     rcx, [rcx+10h]
0x18003ac9c  lea     edx, [rbx+19h]
0x18003ac9f  lea     r8, WPP_a6b47fe3e7aa3dc67b817b99b29667f9_Traceguids
0x18003aca6  call    WPP_SF_
0x18003acab  call    I_BCryptIsoUninitializeRpc
0x18003acb0  call    ?BCryptIsoRemoveAndInvalidateAllHandles@@YAXXZ; BCryptIsoRemoveAndInvalidateAllHandles(void)
0x18003acb5  call    I_BCryptIsoStopProcess
0x18003acba  mov     esi, 1
0x18003acbf  jmp     loc_18003ADE9
0x18003acc4  xor     esi, esi
0x18003acc6  test    r9d, r9d
0x18003acc9  jnz     loc_18003ADB6
0x18003accf  test    rdx, rdx
0x18003acd2  jnz     loc_18003ADB6
0x18003acd8  mov     rcx, cs:WPP_GLOBAL_Control
0x18003acdf  lea     rdi, WPP_GLOBAL_Control
0x18003ace6  cmp     rcx, rdi
0x18003ace9  jz      short loc_18003AD04
0x18003aceb  test    byte ptr [rcx+1Ch], 8
0x18003acef  jz      short loc_18003AD04
0x18003acf1  mov     rcx, [rcx+10h]
0x18003acf5  lea     edx, [rsi+1Ah]
0x18003acf8  lea     r8, WPP_a6b47fe3e7aa3dc67b817b99b29667f9_Traceguids
0x18003acff  call    WPP_SF_
0x18003ad04  xor     ecx, ecx
0x18003ad06  call    I_BCryptIsoCheckRpc
0x18003ad0b  mov     ebx, eax
0x18003ad0d  test    eax, eax
0x18003ad0f  js      short loc_18003AD45
0x18003ad11  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ad18  cmp     rcx, rdi
0x18003ad1b  jz      loc_18003ADE9
0x18003ad21  test    byte ptr [rcx+1Ch], 8
0x18003ad25  jz      loc_18003ADE9
0x18003ad2b  mov     rcx, [rcx+10h]
0x18003ad2f  lea     r8, WPP_a6b47fe3e7aa3dc67b817b99b29667f9_Traceguids
0x18003ad36  mov     edx, 1Bh
0x18003ad3b  call    WPP_SF_
0x18003ad40  jmp     loc_18003ADE9
0x18003ad45  mov     esi, 1
0x18003ad4a  call    I_BCryptIsoUninitializeRpc
0x18003ad4f  call    ?BCryptIsoRemoveAndInvalidateAllHandles@@YAXXZ; BCryptIsoRemoveAndInvalidateAllHandles(void)
0x18003ad54  call    I_BCryptIsoInitializeRpc
0x18003ad59  mov     ebx, eax
0x18003ad5b  test    eax, eax
0x18003ad5d  jns     loc_18003ADE9
0x18003ad63  call    I_BCryptIsoLaunchKeyGuard
0x18003ad68  test    eax, eax
0x18003ad6a  jns     short loc_18003AD8E
0x18003ad6c  mov     r9d, 5ABh
0x18003ad72  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003ad79  lea     rdx, aNtstatus; "ntStatus"
0x18003ad80  mov     ecx, eax
0x18003ad82  call    DebugTraceError
0x18003ad87  mov     ebx, 80090039h
0x18003ad8c  jmp     short loc_18003ADE9
0x18003ad8e  call    I_BCryptIsoInitializeRpc
0x18003ad93  mov     ebx, eax
0x18003ad95  test    eax, eax
0x18003ad97  jns     short loc_18003ADE9
0x18003ad99  mov     r9d, 5B6h
0x18003ad9f  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003ada6  lea     rdx, aSecstatus; "secStatus"
0x18003adad  mov     ecx, eax
0x18003adaf  call    DebugTraceError
0x18003adb4  jmp     short loc_18003ADE9
0x18003adb6  mov     rcx, cs:WPP_GLOBAL_Control
0x18003adbd  lea     rdi, WPP_GLOBAL_Control
0x18003adc4  cmp     rcx, rdi
0x18003adc7  jz      short loc_18003ADE9
0x18003adc9  test    byte ptr [rcx+1Ch], 1
0x18003adcd  jz      short loc_18003ADE9
0x18003adcf  mov     rcx, [rcx+10h]
0x18003add3  xor     eax, eax
0x18003add5  test    rdx, rdx
0x18003add8  mov     edx, 1Ch
0x18003addd  setnz   al
0x18003ade0  mov     [rsp+78h+fAsynchronous], eax
0x18003ade4  call    WPP_SF_dd
0x18003ade9  mov     rdx, cs:hEvent; h
0x18003adf0  xor     r8d, r8d; pftTimeout
0x18003adf3  mov     rcx, cs:pwa; pwa
0x18003adfa  call    cs:__imp_SetThreadpoolWait
0x18003ae01  nop     dword ptr [rax+rax+00h]
0x18003ae06  mov     r9, cs:hEvent; hEvent
0x18003ae0d  xor     edx, edx; bWatchSubtree
0x18003ae0f  mov     rcx, cs:hKey; hKey
0x18003ae16  mov     r8d, 10000004h; dwNotifyFilter
0x18003ae1c  mov     [rsp+78h+fAsynchronous], 1; fAsynchronous
0x18003ae24  call    cs:__imp_RegNotifyChangeKeyValue
0x18003ae2b  nop     dword ptr [rax+rax+00h]
0x18003ae30  test    eax, eax
0x18003ae32  jz      short loc_18003AE4F
0x18003ae34  mov     r9d, 5CFh
0x18003ae3a  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003ae41  lea     rdx, aLstatus; "lStatus"
0x18003ae48  mov     ecx, eax
0x18003ae4a  call    DebugTraceError
0x18003ae4f  lea     rcx, ?g_servicingLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x18003ae56  call    cs:__imp_ReleaseSRWLockExclusive
0x18003ae5d  nop     dword ptr [rax+rax+00h]
0x18003ae62  call    I_BCryptIsoCanLaunchSecureProcess
0x18003ae67  test    eax, eax
0x18003ae69  jz      loc_18003AF3F
0x18003ae6f  cmp     cs:?g_keyguardRegistryData@@3U_KEYGUARD_REGISTRY_DATA@@A, 0; _KEYGUARD_REGISTRY_DATA g_keyguardRegistryData
0x18003ae76  jz      loc_18003AF17
0x18003ae7c  call    cs:__imp_RtlDllShutdownInProgress
0x18003ae83  nop     dword ptr [rax+rax+00h]
0x18003ae88  test    al, al
0x18003ae8a  jnz     loc_18003AF17
0x18003ae90  mov     eax, cs:dword_180079128
0x18003ae96  test    eax, eax
0x18003ae98  jz      short loc_18003AF17
0x18003ae9a  mov     rdx, 800000000000h
0x18003aea4  lea     rcx, dword_180079128
0x18003aeab  call    _tlgKeywordOn
0x18003aeb0  test    al, al
0x18003aeb2  jz      short loc_18003AF17
0x18003aeb4  lea     rcx, ?g_keyguardRegistryData@@3U_KEYGUARD_REGISTRY_DATA@@A; _KEYGUARD_REGISTRY_DATA g_keyguardRegistryData
0x18003aebb  mov     [rbp+var_30], 800h
0x18003aec3  call    BCryptIsoGetKGRunningInProdMode
0x18003aec8  mov     [rbp+var_38], eax
0x18003aecb  lea     r9, [rbp+var_18]
0x18003aecf  lea     rax, [rbp+var_30]
0x18003aed3  mov     [rbp+var_28], 0
0x18003aedb  mov     [rsp+78h+var_40], rax
0x18003aee0  lea     rdx, byte_18006FAE1
0x18003aee7  lea     rax, [rbp+var_38]
0x18003aeeb  mov     [rbp+var_20], 0
0x18003aef3  mov     [rsp+78h+var_48], rax
0x18003aef8  lea     rax, [rbp+var_28]
0x18003aefc  mov     [rsp+78h+var_50], rax
0x18003af01  lea     rax, [rbp+var_20]
0x18003af05  mov     qword ptr [rsp+78h+fAsynchronous], rax
0x18003af0a  mov     [rbp+var_18], 0
0x18003af12  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBX1IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteAgg@@YAJ011I2@ZPEBX@@SAJPEBU_tlgProvider_t@@PEBX1AEBU?$_tlgWrapperByVal@$07@@22AEBU?$_tlgWrapperByVal@$03@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,void const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18003af17  lea     rcx, [rbp+var_38]
0x18003af1b  mov     [rbp+var_38], 0
0x18003af22  call    I_BCryptIsoCheckRpc
0x18003af27  mov     r9d, [rbp+var_38]; int
0x18003af2b  mov     edx, esi; int
0x18003af2d  mov     r8d, cs:?g_keyguardRegistryData@@3U_KEYGUARD_REGISTRY_DATA@@A; int
0x18003af34  mov     cl, 1; unsigned __int8
0x18003af36  mov     [rsp+78h+fAsynchronous], ebx; int
0x18003af3a  call    ?KeyGuardTelemetryReportCurrentState@@YAXEHHJJ@Z; KeyGuardTelemetryReportCurrentState(uchar,int,int,long,long)
0x18003af3f  add     rsp, 78h
0x18003af43  pop     rdi
0x18003af44  pop     rsi
0x18003af45  pop     rbx
0x18003af46  pop     rbp
0x18003af47  retn
```
