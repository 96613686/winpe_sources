# Kd1394Connection::Initialize(ulong *)

- ea: `0x1804306f0`
- end: `0x180430a74`
- name: `?Initialize@Kd1394Connection@@UEAAJPEAK@Z`
- size: `900`
- prototype: `__int64 __fastcall(Kd1394Connection *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18007cf9c`
- `0x18008d550`
- `0x1800db3fc`
- `0x1800db578`
- `0x1800f0f40`
- `0x1801d1b24`
- `0x1803f62d0`
- `0x1803f6d38`
- `0x180416160`
- `0x1804306f0`
- `0x180430c80`
- `0x1804f4010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180430786`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180430786`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18043079e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1804307b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18043079e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1804307b8`
- `ntdll!NtSetTimerResolution` at `0x180430a06`
- `ntdll!NtSetTimerResolution` at `0x180430a06`

## string_xrefs

- `0x1804308b8`: `Opened %s\n`
- `0x18043094d`: `Opened %s\n`
- `0x18043095c`: `WARNING: This machine has the old debug driver installed.\nPlease uninstall the driver per the release notes instructions\nas this debugger will not work well with that driver.\n\n`
- `0x180430934`: `The 1394 debug driver may not be installed.\n`
- `0x180430983`: `Open attempt after driver install failed.  Giving up.\n\n`
- `0x18043098c`: `This channel has been opened by another instance of the debugger.\nPlease select a different channel.\n\n`
- `0x18043090a`: `Failed to open 1394 channel %d.  Error 0x%X.\n\n`
- `0x1804309e6`: `YOU MUST RUN AS ADMIN TO INSTALL THE 1394 DRIVER.\n\nDebugger installation aborted.\n\nPLEASE RERUN THE DEBUGGER AS ADMIN WITH FULL ELEVATION\nSO THAT DRIVER INSTALLATION CAN BE ATTEMPTED.\n\n`
- `0x180430811`: `Attempting 1394 debug driver installation now.\n\n`
- `0x1804309dd`: `\nPLEASE MAKE SURE YOU DON'T HAVE THIS MACHINE CONFIGURED AS\nA 1394 DEBUG TARGET. (Controller is banged out code 31 in this case.)\n\nRun bcdedit -dbgsettings from an elevated command prompt.\nIf the setting is 1394, then please switch the settings to serial or USB.\nIdeally also run bcdedit -debug off to turn off kernel debugging on this box.\nThen reboot the machine and rerun the debugger.\n\n`
- `0x18043086b`: `Driver installation successful.\nRetrying 1394 channel open.\n`
- `0x1804309ab`: `NOTE THAT HAVING A 1394 HUB PLUGGED IN MAY ALSO CAUSE\nTHIS DRIVER INSTALLATION FAILURE.\n\nPlease unplug all devices from the 1394 controller.\nUninstall the 1394 controller from device manager.\nThen reboot the machine and rerun the debugger.\n\n`
- `0x18043099c`: `\nPLEASE MAKE SURE YOU DON'T HAVE THIS MACHINE CONFIGURED AS\nA 1394 DEBUG TARGET.\n\nRun bcdedit -dbgsettings from an elevated command prompt.\nIf the setting is 1394, then please switch the settings to serial or USB.\nIdeally also run bcdedit -debug off to turn off kernel debugging on this box.\nThen reboot the machine and rerun the debugger.\n\n`

## pseudocode

```c
__int64 __fastcall Kd1394Connection::Initialize(Kd1394Connection *this, unsigned int *a2, __int64 a3, int a4)
{
  unsigned int v6; // ebp
  unsigned int v7; // ebx
  HANDLE EventW; // rax
  signed int LastError; // eax
  unsigned int v10; // eax
  int i; // esi
  unsigned __int16 *v12; // rcx
  unsigned int v13; // eax
  signed int v14; // eax
  __int64 v15; // rcx
  __int64 v16; // rcx
  ULONG ActualResolution[4]; // [rsp+30h] [rbp-128h] BYREF
  _QWORD v19[3]; // [rsp+40h] [rbp-118h] BYREF
  char v20; // [rsp+58h] [rbp-100h] BYREF

  DbsDynamicString<unsigned short>::DbsDynamicString<unsigned short>((unsigned int)v19, (unsigned int)&v20, 100, a4, 1);
  v6 = *a2;
  ActualResolution[0] = 0;
  *a2 = 0;
  if ( !v6 )
  {
    LnkOut(1u, L"Using 1394 for debugging\n");
    v7 = KdConnection::Initialize(this, a2);
    if ( v7 )
      goto LABEL_45;
    EventW = CreateEventW(0, 1, 0, 0);
    *((_QWORD *)this + 84) = EventW;
    if ( !EventW )
    {
      if ( !GetLastError() )
      {
        v7 = -2147467259;
        goto LABEL_45;
      }
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_42;
    }
  }
  v10 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this - 2) + 56LL))((char *)this - 16);
  v7 = v10;
  if ( v10 == -2147024777 || v10 == -2147024894 )
    goto LABEL_12;
  if ( !v10 )
  {
    for ( i = 0; ; i = 1 )
    {
      if ( v6 )
      {
        v7 = 0;
        goto LABEL_45;
      }
      if ( *((_DWORD *)this + 49) < 2u )
        v15 = 0;
      else
        v15 = *((_QWORD *)this + 23);
      v7 = Open1394Channel(v15, *((unsigned int *)this + 44), v19, (char *)this + 32);
      if ( !v7 )
        LnkOut(1u, L"Opened %s\n", v19[0]);
      if ( !*((_DWORD *)this + 103) )
      {
        v16 = *((_DWORD *)this + 107) < 2u ? 0LL : *((_QWORD *)this + 52);
        if ( !(unsigned int)Open1394Channel(v16, *((unsigned int *)this + 44), v19, (char *)this + 640) )
        {
          LnkOut(1u, L"Opened %s\n", v19[0]);
          LnkOut(
            2u,
            L"WARNING: This machine has the old debug driver installed.\n"
             "Please uninstall the driver per the release notes instructions\n"
             "as this debugger will not work well with that driver.\n"
             "\n");
LABEL_34:
          *((_DWORD *)this + 102) = -1;
          v7 = Kd1394Connection::SwitchVirtualDebuggerDriverMode((Kd1394Connection *)((char *)this - 16), 0);
          goto LABEL_42;
        }
      }
      if ( !v7 )
        goto LABEL_34;
      LnkOut(2u, L"Failed to open 1394 channel %d.  Error 0x%X.\n\n", *((unsigned int *)this + 44), v7);
      if ( v7 == -2147024891 )
      {
        LnkOut(
          2u,
          L"This channel has been opened by another instance of the debugger.\nPlease select a different channel.\n\n");
        goto LABEL_45;
      }
      if ( i )
      {
        LnkOut(2u, L"Open attempt after driver install failed.  Giving up.\n\n");
        goto LABEL_45;
      }
      if ( v7 != -2147024894 )
        goto LABEL_45;
      LnkOut(2u, L"The 1394 debug driver may not be installed.\n");
LABEL_12:
      LnkOut(2u, L"Attempting 1394 debug driver installation now.\n\n");
      if ( !(unsigned int)IsUserAdmin() )
        break;
      v13 = Add1394DebugDevice(v12);
      v7 = v13;
      if ( v13 )
      {
        LnkOut(2u, L"\nFAILED TO ADD THE 1394 DEBUG DEVICE TO THE 1394 BUS. Error 0x%X.\n\n", v13);
        LnkOut(
          2u,
          L"\n"
           "PLEASE CHECK IN DEVICE MANAGER THAT THIS MACHINE HAS\n"
           "A PROPERLY ENABLED AND FUNCTIONING 1394 CONTROLLER.\n"
           "\n");
        LnkOut(
          2u,
          L"\n"
           "PLEASE MAKE SURE YOU DON'T HAVE THIS MACHINE CONFIGURED AS\n"
           "A 1394 DEBUG TARGET. (Controller is banged out code 31 in this case.)\n"
           "\n"
           "Run bcdedit -dbgsettings from an elevated command prompt.\n"
           "If the setting is 1394, then please switch the settings to serial or USB.\n"
           "Ideally also run bcdedit -debug off to turn off kernel debugging on this box.\n"
           "Then reboot the machine and rerun the debugger.\n"
           "\n");
        goto LABEL_45;
      }
      v14 = KdInstallDebugDriver((__int64)L"1394", (__int64)L"\\1394\\1394dbg.inf", (__int64)L"V1394\\HOST_DEBUGGER");
      v7 = v14;
      if ( v14 == -536870389 )
      {
        LnkOut(
          2u,
          L"\n"
           "PLEASE MAKE SURE YOU DON'T HAVE THIS MACHINE CONFIGURED AS\n"
           "A 1394 DEBUG TARGET.\n"
           "\n"
           "Run bcdedit -dbgsettings from an elevated command prompt.\n"
           "If the setting is 1394, then please switch the settings to serial or USB.\n"
           "Ideally also run bcdedit -debug off to turn off kernel debugging on this box.\n"
           "Then reboot the machine and rerun the debugger.\n"
           "\n");
        LnkOut(
          2u,
          L"NOTE THAT HAVING A 1394 HUB PLUGGED IN MAY ALSO CAUSE\n"
           "THIS DRIVER INSTALLATION FAILURE.\n"
           "\n"
           "Please unplug all devices from the 1394 controller.\n"
           "Uninstall the 1394 controller from device manager.\n"
           "Then reboot the machine and rerun the debugger.\n"
           "\n");
        goto LABEL_45;
      }
      if ( v14 )
        goto LABEL_45;
      LnkOut(1u, L"Driver installation successful.\nRetrying 1394 channel open.\n");
    }
    LnkOut(
      2u,
      L"YOU MUST RUN AS ADMIN TO INSTALL THE 1394 DRIVER.\n"
       "\n"
       "Debugger installation aborted.\n"
       "\n"
       "PLEASE RERUN THE DEBUGGER AS ADMIN WITH FULL ELEVATION\n"
       "SO THAT DRIVER INSTALLATION CAN BE ATTEMPTED.\n"
       "\n");
LABEL_42:
    if ( !v7 && NtSetTimerResolution(0x2710u, 1u, ActualResolution) >= 0 )
    {
      LnkOut(1u, L"Timer Resolution set to %d usec.\n", ActualResolution[0] / 0xA);
      *((_DWORD *)this + 171) = 1;
    }
  }
LABEL_45:
  DbsDynamicArray<CODE_CHUNK>::~DbsDynamicArray<CODE_CHUNK>(v19);
  return v7;
}

```

## disassembly

```asm
0x1804306f0  mov     [rsp+arg_10], rbx
0x1804306f5  mov     [rsp+arg_18], rbp
0x1804306fa  push    rsi
0x1804306fb  push    rdi
0x1804306fc  push    r12
0x1804306fe  push    r13
0x180430700  push    r14
0x180430702  sub     rsp, 130h
0x180430709  mov     rax, cs:__security_cookie
0x180430710  xor     rax, rsp
0x180430713  mov     [rsp+158h+var_38], rax
0x18043071b  mov     r13d, 1
0x180430721  mov     rbx, rdx
0x180430724  mov     rdi, rcx
0x180430727  mov     [rsp+158h+var_138], r13b
0x18043072c  lea     rdx, [rsp+158h+var_100]
0x180430731  lea     rcx, [rsp+158h+var_118]
0x180430736  lea     r8d, [r13+63h]
0x18043073a  call    ??0?$DbsDynamicString@G@@QEAA@PEAGK_N1@Z; DbsDynamicString<ushort>::DbsDynamicString<ushort>(ushort *,ulong,bool,bool)
0x18043073f  mov     ebp, [rbx]
0x180430741  mov     [rsp+158h+ActualResolution], 0
0x180430749  mov     dword ptr [rbx], 0
0x18043074f  test    ebp, ebp
0x180430751  jnz     loc_1804307DC
0x180430757  lea     rdx, aUsing1394ForDe; "Using 1394 for debugging\n"
0x18043075e  mov     ecx, r13d; unsigned int
0x180430761  call    ?LnkOut@@YAXKPEBGZZ; LnkOut(ulong,ushort const *,...)
0x180430766  mov     rdx, rbx; unsigned int *
0x180430769  mov     rcx, rdi; this
0x18043076c  call    ?Initialize@KdConnection@@UEAAJPEAK@Z; KdConnection::Initialize(ulong *)
0x180430771  mov     ebx, eax
0x180430773  test    eax, eax
0x180430775  jnz     loc_180430A3B
0x18043077b  xor     r9d, r9d; lpName
0x18043077e  xor     r8d, r8d; bInitialState
0x180430781  mov     edx, r13d; bManualReset
0x180430784  xor     ecx, ecx; lpEventAttributes
0x180430786  call    cs:__imp_CreateEventW
0x18043078d  nop     dword ptr [rax+rax+00h]
0x180430792  mov     [rdi+2A0h], rax
0x180430799  test    rax, rax
0x18043079c  jnz     short loc_1804307DC
0x18043079e  call    cs:__imp_GetLastError
0x1804307a5  nop     dword ptr [rax+rax+00h]
0x1804307aa  test    eax, eax
0x1804307ac  jnz     short loc_1804307B8
0x1804307ae  mov     ebx, 80004005h
0x1804307b3  jmp     loc_180430A3B
0x1804307b8  call    cs:__imp_GetLastError
0x1804307bf  nop     dword ptr [rax+rax+00h]
0x1804307c4  mov     ebx, eax
0x1804307c6  test    eax, eax
0x1804307c8  jle     loc_1804309F5
0x1804307ce  movzx   ebx, ax
0x1804307d1  or      ebx, 80070000h
0x1804307d7  jmp     loc_1804309F5
0x1804307dc  lea     r14, [rdi-10h]
0x1804307e0  mov     rax, [r14]
0x1804307e3  mov     rcx, r14
0x1804307e6  mov     rax, [rax+38h]
0x1804307ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804307ef  mov     ebx, eax
0x1804307f1  mov     r12d, 2
0x1804307f7  cmp     eax, 80070077h
0x1804307fc  jz      short loc_180430811
0x1804307fe  cmp     eax, 80070002h
0x180430803  jz      short loc_180430811
0x180430805  test    eax, eax
0x180430807  jnz     loc_180430A3B
0x18043080d  xor     esi, esi
0x18043080f  jmp     short loc_18043087D
0x180430811  lea     rdx, aAttempting1394; "Attempting 1394 debug driver installati"...
0x180430818  mov     ecx, r12d; unsigned int
0x18043081b  call    ?LnkOut@@YAXKPEBGZZ; LnkOut(ulong,ushort const *,...)
0x180430820  call    ?IsUserAdmin@@YAHXZ; IsUserAdmin(void)
0x180430825  test    eax, eax
0x180430827  jz      loc_1804309E6
0x18043082d  call    ?Add1394DebugDevice@@YAJPEAG@Z; Add1394DebugDevice(ushort *)
0x180430832  mov     ebx, eax
0x180430834  test    eax, eax
0x180430836  jnz     loc_1804309BC
0x18043083c  lea     r8, aV1394HostDebug; "V1394\\HOST_DEBUGGER"
0x180430843  lea     rdx, a13941394dbgInf; "\\1394\\1394dbg.inf"
0x18043084a  lea     rcx, a1394_0; "1394"
0x180430851  call    KdInstallDebugDriver
0x180430856  mov     ebx, eax
0x180430858  cmp     eax, 0E000020Bh
0x18043085d  jz      loc_18043099C
0x180430863  test    eax, eax
0x180430865  jnz     loc_180430A3B
0x18043086b  lea     rdx, aDriverInstalla; "Driver installation successful.\nRetryi"...
0x180430872  mov     ecx, r13d; unsigned int
0x180430875  mov     esi, r13d
0x180430878  call    ?LnkOut@@YAXKPEBGZZ; LnkOut(ulong,ushort const *,...)
0x18043087d  test    ebp, ebp
0x18043087f  jnz     loc_180430995
0x180430885  cmp     [rdi+0C4h], r12d
0x18043088c  jb      short loc_180430897
0x18043088e  mov     rcx, [rdi+0B8h]
0x180430895  jmp     short loc_180430899
0x180430897  xor     ecx, ecx
0x180430899  mov     edx, [rdi+0B0h]
0x18043089f  lea     r9, [rdi+20h]
0x1804308a3  lea     r8, [rsp+158h+var_118]
0x1804308a8  call    ?Open1394Channel@@YAJPEBGKPEAV?$DbsDynamicString@G@@PEAPEAX@Z; Open1394Channel(ushort const *,ulong,DbsDynamicString<ushort> *,void * *)
0x1804308ad  mov     ebx, eax
0x1804308af  test    eax, eax
0x1804308b1  jnz     short loc_1804308C7
0x1804308b3  mov     r8, [rsp+158h+var_118]
0x1804308b8  lea     rdx, aOpenedS_0; "Opened %s\n"
0x1804308bf  mov     ecx, r13d; unsigned int
0x1804308c2  call    ?LnkOut@@YAXKPEBGZZ; LnkOut(ulong,ushort const *,...)
0x1804308c7  cmp     dword ptr [rdi+19Ch], 0
0x1804308ce  jnz     short loc_1804308FF
0x1804308d0  cmp     [rdi+1ACh], r12d
0x1804308d7  jb      short loc_1804308E2
0x1804308d9  mov     rcx, [rdi+1A0h]
0x1804308e0  jmp     short loc_1804308E4
0x1804308e2  xor     ecx, ecx
0x1804308e4  mov     edx, [rdi+0B0h]
0x1804308ea  lea     r9, [rdi+280h]
0x1804308f1  lea     r8, [rsp+158h+var_118]
0x1804308f6  call    ?Open1394Channel@@YAJPEBGKPEAV?$DbsDynamicString@G@@PEAPEAX@Z; Open1394Channel(ushort const *,ulong,DbsDynamicString<ushort> *,void * *)
0x1804308fb  test    eax, eax
0x1804308fd  jz      short loc_180430948
0x1804308ff  test    ebx, ebx
0x180430901  jz      short loc_18043096B
0x180430903  mov     r8d, [rdi+0B0h]
0x18043090a  lea     rdx, aFailedToOpen13; "Failed to open 1394 channel %d.  Error "...
0x180430911  mov     r9d, ebx
0x180430914  mov     ecx, r12d; unsigned int
0x180430917  call    ?LnkOut@@YAXKPEBGZZ; LnkOut(ulong,ushort const *,...)
0x18043091c  cmp     ebx, 80070005h
0x180430922  jz      short loc_18043098C
0x180430924  test    esi, esi
0x180430926  jnz     short loc_180430983
0x180430928  cmp     ebx, 80070002h
0x18043092e  jnz     loc_180430A3B
0x180430934  lea     rdx, aThe1394DebugDr; "The 1394 debug driver may not be instal"...
0x18043093b  mov     ecx, r12d; unsigned int
0x18043093e  call    ?LnkOut@@YAXKPEBGZZ; LnkOut(ulong,ushort const *,...)
0x180430943  jmp     loc_180430811
0x180430948  mov     r8, [rsp+158h+var_118]
0x18043094d  lea     rdx, aOpenedS_0; "Opened %s\n"
0x180430954  mov     ecx, r13d; unsigned int
0x180430957  call    ?LnkOut@@YAXKPEBGZZ; LnkOut(ulong,ushort const *,...)
0x18043095c  lea     rdx, aWarningThisMac; "WARNING: This machine has the old debug"...
0x180430963  mov     ecx, r12d; unsigned int
0x180430966  call    ?LnkOut@@YAXKPEBGZZ; LnkOut(ulong,ushort const *,...)
0x18043096b  xor     edx, edx; unsigned int
0x18043096d  mov     dword ptr [rdi+198h], 0FFFFFFFFh
0x180430977  mov     rcx, r14; this
0x18043097a  call    ?SwitchVirtualDebuggerDriverMode@Kd1394Connection@@QEAAJK@Z; Kd1394Connection::SwitchVirtualDebuggerDriverMode(ulong)
0x18043097f  mov     ebx, eax
0x180430981  jmp     short loc_1804309F5
0x180430983  lea     rdx, aOpenAttemptAft; "Open attempt after driver install faile"...
0x18043098a  jmp     short loc_1804309B2
0x18043098c  lea     rdx, aThisChannelHas; "This channel has been opened by another"...
0x180430993  jmp     short loc_1804309B2
0x180430995  xor     ebx, ebx
0x180430997  jmp     loc_180430A3B
0x18043099c  lea     rdx, aPleaseMakeSure; "\nPLEASE MAKE SURE YOU DON'T HAVE THIS "...
0x1804309a3  mov     ecx, r12d; unsigned int
0x1804309a6  call    ?LnkOut@@YAXKPEBGZZ; LnkOut(ulong,ushort const *,...)
0x1804309ab  lea     rdx, aNoteThatHaving; "NOTE THAT HAVING A 1394 HUB PLUGGED IN "...
0x1804309b2  mov     ecx, r12d; unsigned int
0x1804309b5  call    ?LnkOut@@YAXKPEBGZZ; LnkOut(ulong,ushort const *,...)
0x1804309ba  jmp     short loc_180430A3B
0x1804309bc  mov     r8d, eax
0x1804309bf  lea     rdx, aFailedToAddThe; "\nFAILED TO ADD THE 1394 DEBUG DEVICE T"...
0x1804309c6  mov     ecx, r12d; unsigned int
0x1804309c9  call    ?LnkOut@@YAXKPEBGZZ; LnkOut(ulong,ushort const *,...)
0x1804309ce  lea     rdx, aPleaseCheckInD; "\nPLEASE CHECK IN DEVICE MANAGER THAT T"...
0x1804309d5  mov     ecx, r12d; unsigned int
0x1804309d8  call    ?LnkOut@@YAXKPEBGZZ; LnkOut(ulong,ushort const *,...)
0x1804309dd  lea     rdx, aPleaseMakeSure_0; "\nPLEASE MAKE SURE YOU DON'T HAVE THIS "...
0x1804309e4  jmp     short loc_1804309B2
0x1804309e6  lea     rdx, aYouMustRunAsAd; "YOU MUST RUN AS ADMIN TO INSTALL THE 13"...
0x1804309ed  mov     ecx, r12d; unsigned int
0x1804309f0  call    ?LnkOut@@YAXKPEBGZZ; LnkOut(ulong,ushort const *,...)
0x1804309f5  test    ebx, ebx
0x1804309f7  jnz     short loc_180430A3B
0x1804309f9  lea     r8, [rsp+158h+ActualResolution]; ActualResolution
0x1804309fe  mov     dl, r13b; SetOrUnset
0x180430a01  mov     ecx, 2710h; RequestedResolution
0x180430a06  call    cs:__imp_NtSetTimerResolution
0x180430a0d  nop     dword ptr [rax+rax+00h]
0x180430a12  test    eax, eax
0x180430a14  js      short loc_180430A3B
0x180430a16  mov     eax, 0CCCCCCCDh
0x180430a1b  mov     ecx, r13d; unsigned int
0x180430a1e  mul     [rsp+158h+ActualResolution]
0x180430a22  shr     edx, 3
0x180430a25  mov     r8d, edx
0x180430a28  lea     rdx, aTimerResolutio_0; "Timer Resolution set to %d usec.\n"
0x180430a2f  call    ?LnkOut@@YAXKPEBGZZ; LnkOut(ulong,ushort const *,...)
0x180430a34  mov     [rdi+2ACh], r13d
0x180430a3b  lea     rcx, [rsp+158h+var_118]
0x180430a40  call    ??1?$DbsDynamicArray@UCODE_CHUNK@@@@QEAA@XZ; DbsDynamicArray<CODE_CHUNK>::~DbsDynamicArray<CODE_CHUNK>(void)
0x180430a45  mov     eax, ebx
0x180430a47  mov     rcx, [rsp+158h+var_38]
0x180430a4f  xor     rcx, rsp; StackCookie
0x180430a52  call    __security_check_cookie
0x180430a57  lea     r11, [rsp+158h+var_28]
0x180430a5f  mov     rbx, [r11+40h]
0x180430a63  mov     rbp, [r11+48h]
0x180430a67  mov     rsp, r11
0x180430a6a  pop     r14
0x180430a6c  pop     r13
0x180430a6e  pop     r12
0x180430a70  pop     rdi
0x180430a71  pop     rsi
0x180430a72  retn
```
