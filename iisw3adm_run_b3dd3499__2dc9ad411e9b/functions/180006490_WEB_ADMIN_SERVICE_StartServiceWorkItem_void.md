# WEB_ADMIN_SERVICE::StartServiceWorkItem(void)

- ea: `0x180006490`
- end: `0x180006790`
- name: `?StartServiceWorkItem@WEB_ADMIN_SERVICE@@AEAAJXZ`
- size: `768`
- prototype: `__int64 __fastcall(WEB_ADMIN_SERVICE *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180004cf0`

## callees

- `0x180001234`
- `0x180002bbc`
- `0x1800040bc`
- `0x1800041f4`
- `0x180004f34`
- `0x18000512c`
- `0x180005388`
- `0x1800060b8`
- `0x180006490`
- `0x180006f28`
- `0x18006101a`
- `0x180061060`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800066a6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800066a6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006707`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006707`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800066f0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800066f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000659f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000659f`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180006555`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180006555`
- `iisutil!PuDbgPrintError` at `0x1800064fa`
- `iisutil!PuDbgPrintError` at `0x180006622`
- `iisutil!PuDbgPrintError` at `0x1800064fa`
- `iisutil!PuDbgPrintError` at `0x180006622`

## string_xrefs

- `0x1800064f3`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\web_admin_service.cxx`
- `0x18000661b`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\web_admin_service.cxx`
- `0x1800064cf`: `Initializing internal components failed\n`
- `0x1800064ec`: `WEB_ADMIN_SERVICE::StartServiceWorkItem`
- `0x180006527`: `couldn't transition to service start pending\n`
- `0x18000658d`: `couldn't initialize subcomponents\n`
- `0x180006640`: `Finishing start service state transition failed\n`
- `0x18000660a`: `WEB_ADMIN_SERVICE::FinishStartService`

## pseudocode

```c
__int64 __fastcall WEB_ADMIN_SERVICE::StartServiceWorkItem(struct _RTL_CRITICAL_SECTION *this)
{
  int v2; // ebx
  const char *v3; // rax
  __int64 v4; // r8
  signed int LastError; // eax
  int v6; // esi
  char v7; // al
  WEB_ADMIN_SERVICE *v8; // rcx
  char *v9; // rbx
  void (__fastcall ***v10)(_QWORD, __int64); // rcx
  _OSVERSIONINFOW VersionInformation; // [rsp+30h] [rbp-138h] BYREF
  char v13; // [rsp+14Ah] [rbp-1Eh]

  v2 = WEB_ADMIN_SERVICE::InitializeInternalComponents(this);
  if ( v2 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) == 0 )
      goto LABEL_31;
    v3 = "Initializing internal components failed\n";
    v4 = 1339;
LABEL_4:
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\web_admin_service.cxx",
      v4,
      "WEB_ADMIN_SERVICE::StartServiceWorkItem",
      v2,
      v3);
LABEL_31:
    LODWORD(this[39].DebugInfo) = v2;
    if ( !(unsigned int)CheckWASIsStopping() )
    {
      EnterCriticalSection(&g_critsecWebAdminService);
      g_fWASStoppingInProgress = 1;
      LeaveCriticalSection(&g_critsecWebAdminService);
      WEB_ADMIN_SERVICE::Shutdown((WEB_ADMIN_SERVICE *)this);
    }
    return (unsigned int)v2;
  }
  v2 = WEB_ADMIN_SERVICE::BeginStateTransition((WEB_ADMIN_SERVICE *)this, 2u);
  if ( v2 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) == 0 )
      goto LABEL_31;
    v3 = "couldn't transition to service start pending\n";
    v4 = 1352;
    goto LABEL_4;
  }
  memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
  VersionInformation.dwOSVersionInfoSize = 284;
  if ( GetVersionExW(&VersionInformation) )
  {
    HIDWORD(this[40].OwningThread) = v13 == 1;
  }
  else
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
    if ( v2 < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) == 0 )
        goto LABEL_31;
      v3 = "couldn't figure out what version of the OS is running\n";
      v4 = 1365;
      goto LABEL_4;
    }
  }
  v2 = WEB_ADMIN_SERVICE::InitializeOtherComponents((WEB_ADMIN_SERVICE *)this);
  if ( v2 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) == 0 )
      goto LABEL_31;
    v3 = "couldn't initialize subcomponents\n";
    v4 = 1378;
    goto LABEL_4;
  }
  v6 = WEB_ADMIN_SERVICE::FinishStateTransition((WEB_ADMIN_SERVICE *)this, 4u, 2u);
  v7 = g_dwDebugFlags;
  if ( v6 < 0 && (g_dwDebugFlags & 0xF) != 0 )
  {
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\web_admin_service.cxx",
      1471,
      "WEB_ADMIN_SERVICE::FinishStartService",
      v6,
      "Couldn't finish transition into the running state\n");
    v7 = g_dwDebugFlags;
    v2 = v6;
    goto LABEL_23;
  }
  v2 = v6;
  if ( v6 < 0 )
  {
LABEL_23:
    if ( (v7 & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\web_admin_service.cxx",
        1390,
        "WEB_ADMIN_SERVICE::StartServiceWorkItem",
        v6,
        "Finishing start service state transition failed\n");
    goto LABEL_31;
  }
  if ( *((_DWORD *)g_pWebAdminService + 412) )
    return (unsigned int)v2;
  WEB_ADMIN_SERVICE::WriteSqmData((WEB_ADMIN_SERVICE *)this);
  v9 = (char *)operator new(0x78u);
  if ( v9 )
  {
    *((_QWORD *)v9 + 1) = 0;
    *(_QWORD *)v9 = &WAS_SQM_WRITER::`vftable';
    *((_DWORD *)v9 + 4) = 0;
    InitializeCriticalSection((LPCRITICAL_SECTION)v9 + 2);
    *(_OWORD *)(v9 + 20) = 0;
    *(_OWORD *)(v9 + 36) = 0;
    *(_OWORD *)(v9 + 52) = 0;
    *(_QWORD *)(v9 + 68) = 0;
  }
  else
  {
    v9 = 0;
  }
  *(_QWORD *)&this[46].LockCount = v9;
  if ( !v9 )
  {
    v2 = -2147024888;
    goto LABEL_31;
  }
  v2 = WEB_ADMIN_SERVICE::BeginTimer(
         v8,
         (struct _TP_TIMER **)v9 + 1,
         (void (*)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_TIMER *))WAS_SQM_WRITER::DataCollectCallback,
         0x36EE80u,
         1,
         v9);
  if ( v2 < 0 )
  {
    v10 = *(void (__fastcall ****)(_QWORD, __int64))&this[46].LockCount;
    if ( v10 )
      (**v10)(v10, 1);
    *(_QWORD *)&this[46].LockCount = 0;
    return 0;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180006490  mov     [rsp+arg_8], rbx
0x180006495  mov     [rsp+arg_10], rsi
0x18000649a  push    rdi
0x18000649b  sub     rsp, 160h
0x1800064a2  mov     rax, cs:__security_cookie
0x1800064a9  xor     rax, rsp
0x1800064ac  mov     [rsp+168h+var_18], rax
0x1800064b4  mov     rdi, rcx
0x1800064b7  call    ?InitializeInternalComponents@WEB_ADMIN_SERVICE@@AEAAJXZ; WEB_ADMIN_SERVICE::InitializeInternalComponents(void)
0x1800064bc  mov     ebx, eax
0x1800064be  test    eax, eax
0x1800064c0  jns     short loc_180006505
0x1800064c2  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800064c9  jz      loc_1800066D6
0x1800064cf  lea     rax, aInitializingIn; "Initializing internal components failed"...
0x1800064d6  mov     r8d, 53Bh
0x1800064dc  mov     [rsp+168h+var_140], rax
0x1800064e1  mov     [rsp+168h+var_148], ebx
0x1800064e5  mov     rcx, cs:g_pDebug
0x1800064ec  lea     r9, aWebAdminServic_4; "WEB_ADMIN_SERVICE::StartServiceWorkItem"
0x1800064f3  lea     rdx, aServercommonIn_44; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800064fa  call    cs:__imp_PuDbgPrintError
0x180006500  jmp     loc_1800066D6
0x180006505  mov     esi, 2
0x18000650a  mov     rcx, rdi; this
0x18000650d  mov     edx, esi; unsigned int
0x18000650f  call    ?BeginStateTransition@WEB_ADMIN_SERVICE@@AEAAJK@Z; WEB_ADMIN_SERVICE::BeginStateTransition(ulong)
0x180006514  mov     ebx, eax
0x180006516  test    eax, eax
0x180006518  jns     short loc_180006536
0x18000651a  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180006521  jz      loc_1800066D6
0x180006527  lea     rax, aCouldnTTransit_1; "couldn't transition to service start pe"...
0x18000652e  mov     r8d, 548h
0x180006534  jmp     short loc_1800064DC
0x180006536  xor     edx, edx; Val
0x180006538  lea     rcx, [rsp+168h+VersionInformation.dwMajorVersion]; void *
0x18000653d  mov     r8d, 118h; Size
0x180006543  call    memset_0
0x180006548  lea     rcx, [rsp+168h+VersionInformation]; lpVersionInformation
0x18000654d  mov     [rsp+168h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x180006555  call    cs:__imp_GetVersionExW
0x18000655b  test    eax, eax
0x18000655d  jz      short loc_18000659F
0x18000655f  xor     eax, eax
0x180006561  cmp     [rsp+168h+var_1E], 1
0x180006569  setz    al
0x18000656c  mov     [rdi+654h], eax
0x180006572  mov     rcx, rdi; this
0x180006575  call    ?InitializeOtherComponents@WEB_ADMIN_SERVICE@@AEAAJXZ; WEB_ADMIN_SERVICE::InitializeOtherComponents(void)
0x18000657a  mov     ebx, eax
0x18000657c  test    eax, eax
0x18000657e  jns     short loc_1800065D7
0x180006580  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180006587  jz      loc_1800066D6
0x18000658d  lea     rax, aCouldnTInitial_0; "couldn't initialize subcomponents\n"
0x180006594  mov     r8d, 562h
0x18000659a  jmp     loc_1800064DC
0x18000659f  call    cs:__imp_GetLastError
0x1800065a5  mov     ebx, eax
0x1800065a7  test    eax, eax
0x1800065a9  jle     short loc_1800065B4
0x1800065ab  movzx   ebx, ax
0x1800065ae  or      ebx, 80070000h
0x1800065b4  test    ebx, ebx
0x1800065b6  jns     short loc_180006572
0x1800065b8  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800065bf  jz      loc_1800066D6
0x1800065c5  lea     rax, aCouldnTFigureO; "couldn't figure out what version of the"...
0x1800065cc  mov     r8d, 555h
0x1800065d2  jmp     loc_1800064DC
0x1800065d7  mov     r8d, esi; unsigned int
0x1800065da  mov     edx, 4; unsigned int
0x1800065df  mov     rcx, rdi; this
0x1800065e2  call    ?FinishStateTransition@WEB_ADMIN_SERVICE@@AEAAJKK@Z; WEB_ADMIN_SERVICE::FinishStateTransition(ulong,ulong)
0x1800065e7  mov     esi, eax
0x1800065e9  mov     eax, cs:g_dwDebugFlags
0x1800065ef  test    esi, esi
0x1800065f1  jns     short loc_180006632
0x1800065f3  test    al, 0Fh
0x1800065f5  jz      short loc_180006632
0x1800065f7  mov     rcx, cs:g_pDebug
0x1800065fe  lea     rax, aCouldnTFinishT_0; "Couldn't finish transition into the run"...
0x180006605  mov     [rsp+168h+var_140], rax
0x18000660a  lea     r9, aWebAdminServic_21; "WEB_ADMIN_SERVICE::FinishStartService"
0x180006611  mov     r8d, 5BFh
0x180006617  mov     [rsp+168h+var_148], esi
0x18000661b  lea     rdx, aServercommonIn_44; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180006622  call    cs:__imp_PuDbgPrintError
0x180006628  mov     eax, cs:g_dwDebugFlags
0x18000662e  mov     ebx, esi
0x180006630  jmp     short loc_180006638
0x180006632  mov     ebx, esi
0x180006634  test    esi, esi
0x180006636  jns     short loc_18000665B
0x180006638  test    al, 0Fh
0x18000663a  jz      loc_1800066D6
0x180006640  lea     rax, aFinishingStart; "Finishing start service state transitio"...
0x180006647  mov     r8d, 56Eh
0x18000664d  mov     [rsp+168h+var_140], rax
0x180006652  mov     [rsp+168h+var_148], esi
0x180006656  jmp     loc_1800064E5
0x18000665b  mov     rax, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x180006662  cmp     dword ptr [rax+670h], 0
0x180006669  jnz     loc_180006769
0x18000666f  mov     rcx, rdi; this
0x180006672  call    ?WriteSqmData@WEB_ADMIN_SERVICE@@AEAAJXZ; WEB_ADMIN_SERVICE::WriteSqmData(void)
0x180006677  mov     ecx, 78h ; 'x'; Size
0x18000667c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006681  mov     rbx, rax
0x180006684  test    rax, rax
0x180006687  jz      short loc_1800066C3
0x180006689  lea     rax, ??_7WAS_SQM_WRITER@@6B@; const WAS_SQM_WRITER::`vftable'
0x180006690  mov     qword ptr [rbx+8], 0
0x180006698  lea     rcx, [rbx+50h]; lpCriticalSection
0x18000669c  mov     [rbx], rax
0x18000669f  mov     dword ptr [rbx+10h], 0
0x1800066a6  call    cs:__imp_InitializeCriticalSection
0x1800066ac  xorps   xmm0, xmm0
0x1800066af  xor     eax, eax
0x1800066b1  movups  xmmword ptr [rbx+14h], xmm0
0x1800066b5  movups  xmmword ptr [rbx+24h], xmm0
0x1800066b9  movups  xmmword ptr [rbx+34h], xmm0
0x1800066bd  mov     [rbx+44h], rax
0x1800066c1  jmp     short loc_1800066C5
0x1800066c3  xor     ebx, ebx
0x1800066c5  mov     [rdi+738h], rbx
0x1800066cc  test    rbx, rbx
0x1800066cf  jnz     short loc_180006717
0x1800066d1  mov     ebx, 80070008h
0x1800066d6  mov     [rdi+618h], ebx
0x1800066dc  call    ?CheckWASIsStopping@@YAHXZ; CheckWASIsStopping(void)
0x1800066e1  test    eax, eax
0x1800066e3  jnz     loc_180006769
0x1800066e9  lea     rcx, ?g_critsecWebAdminService@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800066f0  call    cs:__imp_EnterCriticalSection
0x1800066f6  lea     rcx, ?g_critsecWebAdminService@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800066fd  mov     cs:?g_fWASStoppingInProgress@@3HA, 1; int g_fWASStoppingInProgress
0x180006707  call    cs:__imp_LeaveCriticalSection
0x18000670d  mov     rcx, rdi; this
0x180006710  call    ?Shutdown@WEB_ADMIN_SERVICE@@AEAAXXZ; WEB_ADMIN_SERVICE::Shutdown(void)
0x180006715  jmp     short loc_180006769
0x180006717  lea     rdx, [rbx+8]; struct _TP_TIMER **
0x18000671b  mov     [rsp+168h+var_140], rbx; void *
0x180006720  mov     r9d, 36EE80h; unsigned int
0x180006726  mov     [rsp+168h+var_148], 1; int
0x18000672e  lea     r8, ?DataCollectCallback@WAS_SQM_WRITER@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; void (*)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_TIMER *)
0x180006735  call    ?BeginTimer@WEB_ADMIN_SERVICE@@QEAAJPEAPEAU_TP_TIMER@@P6AXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU2@@ZKH2@Z; WEB_ADMIN_SERVICE::BeginTimer(_TP_TIMER * *,void (*)(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *),ulong,int,void *)
0x18000673a  mov     ebx, eax
0x18000673c  test    eax, eax
0x18000673e  jns     short loc_180006769
0x180006740  mov     rcx, [rdi+738h]
0x180006747  test    rcx, rcx
0x18000674a  jz      short loc_18000675C
0x18000674c  mov     rax, [rcx]
0x18000674f  mov     edx, 1
0x180006754  mov     rax, [rax]
0x180006757  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000675c  mov     qword ptr [rdi+738h], 0
0x180006767  xor     ebx, ebx
0x180006769  mov     eax, ebx
0x18000676b  mov     rcx, [rsp+168h+var_18]
0x180006773  xor     rcx, rsp; StackCookie
0x180006776  call    __security_check_cookie
0x18000677b  lea     r11, [rsp+168h+var_8]
0x180006783  mov     rbx, [r11+18h]
0x180006787  mov     rsi, [r11+20h]
0x18000678b  mov     rsp, r11
0x18000678e  pop     rdi
0x18000678f  retn
```
