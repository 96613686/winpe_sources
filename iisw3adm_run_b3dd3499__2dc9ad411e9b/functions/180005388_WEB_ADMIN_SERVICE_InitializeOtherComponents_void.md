# WEB_ADMIN_SERVICE::InitializeOtherComponents(void)

- ea: `0x180005388`
- end: `0x18000568c`
- name: `?InitializeOtherComponents@WEB_ADMIN_SERVICE@@AEAAJXZ`
- size: `772`
- prototype: `__int64 __fastcall(WEB_ADMIN_SERVICE *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180006490`

## callees

- `0x1800042dc`
- `0x1800044d4`
- `0x180005388`
- `0x180005878`
- `0x1800113d4`
- `0x180011fec`
- `0x18002ca6c`
- `0x180060ba0`
- `0x180061060`

## import_xrefs

- `msvcrt!_ultow` at `0x1800054c1`
- `msvcrt!_ultow` at `0x1800054c1`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800053da`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800053da`
- `iisutil!PuDbgPrintError` at `0x18000541e`
- `iisutil!PuDbgPrintError` at `0x18000541e`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180005668`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180005668`
- `iisutil!ReadDwordParameterValueFromAnyService` at `0x180005453`
- `iisutil!ReadDwordParameterValueFromAnyService` at `0x180005511`
- `iisutil!ReadDwordParameterValueFromAnyService` at `0x1800055ee`
- `iisutil!ReadDwordParameterValueFromAnyService` at `0x180005653`
- `iisutil!ReadDwordParameterValueFromAnyService` at `0x180005453`
- `iisutil!ReadDwordParameterValueFromAnyService` at `0x180005511`
- `iisutil!ReadDwordParameterValueFromAnyService` at `0x1800055ee`
- `iisutil!ReadDwordParameterValueFromAnyService` at `0x180005653`
- `iisutil!ReadStringParameterValueFromAnyService` at `0x180005537`
- `iisutil!ReadStringParameterValueFromAnyService` at `0x180005580`
- `iisutil!ReadStringParameterValueFromAnyService` at `0x180005537`
- `iisutil!ReadStringParameterValueFromAnyService` at `0x180005580`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180005554`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180005554`

## string_xrefs

- `0x180005413`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\web_admin_service.cxx`
- `0x1800053f3`: `Initializing COM failed\n`
- `0x180005407`: `WEB_ADMIN_SERVICE::InitializeOtherComponents`
- `0x18000544c`: `System\CurrentControlSet\Services\WAS\Parameters\SystemSettings`
- `0x180005507`: `ConfigIsolationEnabled`
- `0x18000552a`: `ConfigIsolationPath`
- `0x180005573`: `ConfigIsolationPath`
- `0x1800054f7`: `System\CurrentControlSet\Services\WAS\Parameters`
- `0x1800055e4`: `CreateSharedMachineKeyLocation`
- `0x180005620`: `Initializing configuration manager failed\n`

## pseudocode

```c
__int64 __fastcall WEB_ADMIN_SERVICE::InitializeOtherComponents(WEB_ADMIN_SERVICE *this)
{
  HRESULT AppPoolIsolation; // ebx
  bool v3; // zf
  HRESULT StringParameterValueFromAnyService; // eax
  unsigned __int16 *v5; // rdx
  int v6; // eax
  BOOL v7; // eax
  __int64 v9; // [rsp+30h] [rbp-39h] BYREF
  unsigned __int16 *v10; // [rsp+38h] [rbp-31h] BYREF
  _QWORD v11[4]; // [rsp+40h] [rbp-29h] BYREF
  unsigned __int16 *v12; // [rsp+60h] [rbp-9h]
  int v13; // [rsp+68h] [rbp-1h]
  __int16 v14; // [rsp+6Ch] [rbp+3h]
  wchar_t Buffer[12]; // [rsp+70h] [rbp+7h] BYREF

  LODWORD(v9) = 0;
  v11[0] = 0;
  v13 = 32;
  v12 = (unsigned __int16 *)v11;
  v14 = 256;
  AppPoolIsolation = CoInitializeEx(0, 0);
  if ( AppPoolIsolation < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\web_admin_service.cxx",
        2788,
        "WEB_ADMIN_SERVICE::InitializeOtherComponents",
        AppPoolIsolation,
        "Initializing COM failed\n",
        v9);
    goto LABEL_38;
  }
  v3 = *((_DWORD *)this + 412) == 0;
  *((_DWORD *)this + 461) = 1;
  if ( v3 )
    WEB_ADMIN_SERVICE::CheckForIUsrs(this);
  APP_POOL::sm_dwIdentitiesAllowedValue = ReadDwordParameterValueFromAnyService(
                                            L"System\\CurrentControlSet\\Services\\WAS\\Parameters\\SystemSettings",
                                            L"AppPoolIdentitiesAllowed",
                                            0xFFFFFFFF);
  AppPoolIsolation = UL_AND_WORKER_MANAGER::Initialize((WEB_ADMIN_SERVICE *)((char *)this + 112));
  if ( AppPoolIsolation < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\web_admin_service.cxx",
        2842,
        "WEB_ADMIN_SERVICE::InitializeOtherComponents",
        AppPoolIsolation,
        "Initializing UL & Worker manager failed\n",
        v9);
    goto LABEL_38;
  }
  if ( !*((_DWORD *)this + 412) )
  {
    HIDWORD(v9) = 0;
    AppPoolIsolation = AddDomainMapping((unsigned int *)&v9 + 1);
    if ( AppPoolIsolation < 0 )
    {
      v10 = 0;
      _ultow(HIDWORD(v9), Buffer, 10);
      v10 = Buffer;
      WEB_ADMIN_SERVICE::LogEvent(
        g_pWebAdminService,
        0xC0001452,
        1u,
        (const unsigned __int16 **const)&v10,
        AppPoolIsolation);
      goto LABEL_38;
    }
  }
  if ( *((_DWORD *)this + 412)
    || !ReadDwordParameterValueFromAnyService(
          L"System\\CurrentControlSet\\Services\\WAS\\Parameters",
          L"ConfigIsolationEnabled",
          1u) )
  {
    v6 = 0;
  }
  else
  {
    LODWORD(v9) = v13;
    StringParameterValueFromAnyService = ReadStringParameterValueFromAnyService(
                                           L"System\\CurrentControlSet\\Services\\WAS\\Parameters",
                                           L"ConfigIsolationPath",
                                           v12,
                                           (unsigned int *)&v9);
    AppPoolIsolation = StringParameterValueFromAnyService;
    if ( StringParameterValueFromAnyService )
    {
      if ( StringParameterValueFromAnyService == -2147024662 )
      {
        if ( !BUFFER::Resize((BUFFER *)v11, v9 + 2) )
        {
          AppPoolIsolation = -2147024882;
          goto LABEL_38;
        }
        LODWORD(v9) = v13;
        AppPoolIsolation = ReadStringParameterValueFromAnyService(
                             L"System\\CurrentControlSet\\Services\\WAS\\Parameters",
                             L"ConfigIsolationPath",
                             v12,
                             (unsigned int *)&v9);
      }
      else if ( StringParameterValueFromAnyService != -2147024894 )
      {
        goto LABEL_38;
      }
    }
    v5 = 0;
    if ( !AppPoolIsolation )
      v5 = v12;
    AppPoolIsolation = WEB_ADMIN_SERVICE::CreateAppPoolIsolation(this, v5);
    if ( AppPoolIsolation < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\web_admin_service.cxx",
          2919,
          "WEB_ADMIN_SERVICE::InitializeOtherComponents",
          AppPoolIsolation,
          "Could not initialize App Pool Isolation\n",
          v9);
      goto LABEL_38;
    }
    v6 = 1;
  }
  *((_DWORD *)this + 457) = v6;
  v7 = !*((_DWORD *)this + 412)
    && ReadDwordParameterValueFromAnyService(
         L"System\\CurrentControlSet\\Services\\WAS\\Parameters",
         L"CreateSharedMachineKeyLocation",
         1u);
  *((_DWORD *)this + 460) = v7;
  AppPoolIsolation = CONFIG_AND_CONTROL_MANAGER::Initialize((WEB_ADMIN_SERVICE *)((char *)this + 688));
  if ( AppPoolIsolation >= 0 )
  {
    UL_AND_WORKER_MANAGER::ProcessApplicationPreload((WEB_ADMIN_SERVICE *)((char *)this + 112), 0);
    if ( *((_DWORD *)this + 412)
      || !ReadDwordParameterValueFromAnyService(
            L"System\\CurrentControlSet\\Services\\WAS\\Parameters",
            L"AlwaysLogEvents",
            0) )
    {
      *((_DWORD *)this + 396) = 1;
    }
  }
  else if ( (g_dwDebugFlags & 0xF) != 0 )
  {
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\web_admin_service.cxx",
      2958,
      "WEB_ADMIN_SERVICE::InitializeOtherComponents",
      AppPoolIsolation,
      "Initializing configuration manager failed\n",
      v9);
  }
LABEL_38:
  BUFFER::~BUFFER((BUFFER *)v11);
  return (unsigned int)AppPoolIsolation;
}

```

## disassembly

```asm
0x180005388  push    rbp
0x18000538a  push    rbx
0x18000538b  push    rsi
0x18000538c  push    rdi
0x18000538d  push    r12
0x18000538f  push    r15
0x180005391  lea     rbp, [rsp-2Fh]
0x180005396  sub     rsp, 98h
0x18000539d  mov     rax, cs:__security_cookie
0x1800053a4  xor     rax, rsp
0x1800053a7  mov     [rbp+57h+var_38], rax
0x1800053ab  xor     edx, edx; dwCoInit
0x1800053ad  mov     [rbp+57h+var_90], 0
0x1800053b4  mov     rdi, rcx
0x1800053b7  mov     [rbp+57h+var_80], 0
0x1800053bf  lea     rax, [rbp+57h+var_80]
0x1800053c3  mov     [rbp+57h+var_58], 20h ; ' '
0x1800053ca  xor     ecx, ecx; pvReserved
0x1800053cc  mov     [rbp+57h+var_60], rax
0x1800053d0  lea     r15d, [rdx+1]
0x1800053d4  mov     [rbp+57h+var_54], 100h
0x1800053da  call    cs:__imp_CoInitializeEx
0x1800053e0  mov     ebx, eax
0x1800053e2  test    eax, eax
0x1800053e4  jns     short loc_180005429
0x1800053e6  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800053ed  jz      loc_180005664
0x1800053f3  lea     rax, aInitializingCo_1; "Initializing COM failed\n"
0x1800053fa  mov     r8d, 0AE4h
0x180005400  mov     rcx, cs:g_pDebug
0x180005407  lea     r9, aWebAdminServic_24; "WEB_ADMIN_SERVICE::InitializeOtherCompo"...
0x18000540e  mov     [rsp+0C0h+var_98], rax
0x180005413  lea     rdx, aServercommonIn_44; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000541a  mov     [rsp+0C0h+var_A0], ebx
0x18000541e  call    cs:__imp_PuDbgPrintError
0x180005424  jmp     loc_180005664
0x180005429  cmp     dword ptr [rdi+670h], 0
0x180005430  mov     [rdi+734h], r15d
0x180005437  jnz     short loc_180005441
0x180005439  mov     rcx, rdi; this
0x18000543c  call    ?CheckForIUsrs@WEB_ADMIN_SERVICE@@AEAAXXZ; WEB_ADMIN_SERVICE::CheckForIUsrs(void)
0x180005441  or      r8d, 0FFFFFFFFh
0x180005445  lea     rdx, aApppoolidentit; "AppPoolIdentitiesAllowed"
0x18000544c  lea     rcx, aSystemCurrentc_3; "System\\CurrentControlSet\\Services\\WA"...
0x180005453  call    cs:__imp_?ReadDwordParameterValueFromAnyService@@YAKPEBG0K@Z; ReadDwordParameterValueFromAnyService(ushort const *,ushort const *,ulong)
0x180005459  lea     rcx, [rdi+70h]; this
0x18000545d  mov     cs:?sm_dwIdentitiesAllowedValue@APP_POOL@@0KA, eax; ulong APP_POOL::sm_dwIdentitiesAllowedValue
0x180005463  call    ?Initialize@UL_AND_WORKER_MANAGER@@QEAAJXZ; UL_AND_WORKER_MANAGER::Initialize(void)
0x180005468  mov     ebx, eax
0x18000546a  test    eax, eax
0x18000546c  jns     short loc_18000548D
0x18000546e  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180005475  jz      loc_180005664
0x18000547b  lea     rax, aInitializingUl; "Initializing UL & Worker manager failed"...
0x180005482  mov     r8d, 0B1Ah
0x180005488  jmp     loc_180005400
0x18000548d  cmp     dword ptr [rdi+670h], 0
0x180005494  jnz     short loc_1800054F0
0x180005496  lea     rcx, [rbp+57h+Value]; unsigned int *
0x18000549a  mov     [rbp+57h+Value], 0
0x1800054a1  call    ?AddDomainMapping@@YAJPEAK@Z; AddDomainMapping(ulong *)
0x1800054a6  mov     ebx, eax
0x1800054a8  test    eax, eax
0x1800054aa  jns     short loc_1800054F0
0x1800054ac  mov     ecx, [rbp+57h+Value]; Value
0x1800054af  lea     rdx, [rbp+57h+Buffer]; Buffer
0x1800054b3  mov     r8d, 0Ah; Radix
0x1800054b9  mov     [rbp+57h+var_88], 0
0x1800054c1  call    cs:__imp__ultow
0x1800054c7  mov     rcx, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; this
0x1800054ce  lea     rax, [rbp+57h+Buffer]
0x1800054d2  mov     r8d, r15d; unsigned __int16
0x1800054d5  mov     [rbp+57h+var_88], rax
0x1800054d9  lea     r9, [rbp+57h+var_88]; unsigned __int16 **
0x1800054dd  mov     [rsp+0C0h+var_A0], ebx; unsigned int
0x1800054e1  mov     edx, 0C0001452h; unsigned int
0x1800054e6  call    ?LogEvent@WEB_ADMIN_SERVICE@@QEAAXKGQEAPEBGK@Z; WEB_ADMIN_SERVICE::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x1800054eb  jmp     loc_180005664
0x1800054f0  cmp     dword ptr [rdi+670h], 0
0x1800054f7  lea     r12, aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\WA"...
0x1800054fe  jnz     loc_1800055D0
0x180005504  mov     r8d, r15d
0x180005507  lea     rdx, aConfigisolatio; "ConfigIsolationEnabled"
0x18000550e  mov     rcx, r12
0x180005511  call    cs:__imp_?ReadDwordParameterValueFromAnyService@@YAKPEBG0K@Z; ReadDwordParameterValueFromAnyService(ushort const *,ushort const *,ulong)
0x180005517  test    eax, eax
0x180005519  jz      loc_1800055D0
0x18000551f  mov     eax, [rbp+57h+var_58]
0x180005522  lea     r9, [rbp+57h+var_90]
0x180005526  mov     r8, [rbp+57h+var_60]
0x18000552a  lea     rdx, aConfigisolatio_1; "ConfigIsolationPath"
0x180005531  mov     rcx, r12
0x180005534  mov     [rbp+57h+var_90], eax
0x180005537  call    cs:__imp_?ReadStringParameterValueFromAnyService@@YAJPEBG00PEAK@Z; ReadStringParameterValueFromAnyService(ushort const *,ushort const *,ushort const *,ulong *)
0x18000553d  mov     ebx, eax
0x18000553f  test    eax, eax
0x180005541  jz      short loc_180005595
0x180005543  cmp     eax, 800700EAh
0x180005548  jnz     short loc_18000558A
0x18000554a  mov     edx, [rbp+57h+var_90]
0x18000554d  lea     rcx, [rbp+57h+var_80]
0x180005551  add     edx, 2
0x180005554  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18000555a  test    al, al
0x18000555c  jnz     short loc_180005568
0x18000555e  mov     ebx, 8007000Eh
0x180005563  jmp     loc_180005664
0x180005568  mov     eax, [rbp+57h+var_58]
0x18000556b  lea     r9, [rbp+57h+var_90]
0x18000556f  mov     r8, [rbp+57h+var_60]
0x180005573  lea     rdx, aConfigisolatio_1; "ConfigIsolationPath"
0x18000557a  mov     rcx, r12
0x18000557d  mov     [rbp+57h+var_90], eax
0x180005580  call    cs:__imp_?ReadStringParameterValueFromAnyService@@YAJPEBG00PEAK@Z; ReadStringParameterValueFromAnyService(ushort const *,ushort const *,ushort const *,ulong *)
0x180005586  mov     ebx, eax
0x180005588  jmp     short loc_180005595
0x18000558a  cmp     eax, 80070002h
0x18000558f  jnz     loc_180005664
0x180005595  xor     edx, edx
0x180005597  mov     rcx, rdi; this
0x18000559a  test    ebx, ebx
0x18000559c  cmovz   rdx, [rbp+57h+var_60]; unsigned __int16 *
0x1800055a1  call    ?CreateAppPoolIsolation@WEB_ADMIN_SERVICE@@AEAAJPEBG@Z; WEB_ADMIN_SERVICE::CreateAppPoolIsolation(ushort const *)
0x1800055a6  mov     ebx, eax
0x1800055a8  test    eax, eax
0x1800055aa  jns     short loc_1800055CB
0x1800055ac  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800055b3  jz      loc_180005664
0x1800055b9  lea     rax, aCouldNotInitia_3; "Could not initialize App Pool Isolation"...
0x1800055c0  mov     r8d, 0B67h
0x1800055c6  jmp     loc_180005400
0x1800055cb  mov     eax, r15d
0x1800055ce  jmp     short loc_1800055D2
0x1800055d0  xor     eax, eax
0x1800055d2  mov     [rdi+724h], eax
0x1800055d8  cmp     dword ptr [rdi+670h], 0
0x1800055df  jnz     short loc_1800055FD
0x1800055e1  mov     r8d, r15d
0x1800055e4  lea     rdx, aCreatesharedma; "CreateSharedMachineKeyLocation"
0x1800055eb  mov     rcx, r12
0x1800055ee  call    cs:__imp_?ReadDwordParameterValueFromAnyService@@YAKPEBG0K@Z; ReadDwordParameterValueFromAnyService(ushort const *,ushort const *,ulong)
0x1800055f4  test    eax, eax
0x1800055f6  jz      short loc_1800055FD
0x1800055f8  mov     eax, r15d
0x1800055fb  jmp     short loc_1800055FF
0x1800055fd  xor     eax, eax
0x1800055ff  lea     rcx, [rdi+2B0h]; this
0x180005606  mov     [rdi+730h], eax
0x18000560c  call    ?Initialize@CONFIG_AND_CONTROL_MANAGER@@QEAAJXZ; CONFIG_AND_CONTROL_MANAGER::Initialize(void)
0x180005611  mov     ebx, eax
0x180005613  test    eax, eax
0x180005615  jns     short loc_180005632
0x180005617  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000561e  jz      short loc_180005664
0x180005620  lea     rax, aInitializingCo_4; "Initializing configuration manager fail"...
0x180005627  mov     r8d, 0B8Eh
0x18000562d  jmp     loc_180005400
0x180005632  xor     edx, edx; unsigned int
0x180005634  lea     rcx, [rdi+70h]; this
0x180005638  call    ?ProcessApplicationPreload@UL_AND_WORKER_MANAGER@@QEAAXK@Z; UL_AND_WORKER_MANAGER::ProcessApplicationPreload(ulong)
0x18000563d  cmp     dword ptr [rdi+670h], 0
0x180005644  jnz     short loc_18000565D
0x180005646  xor     r8d, r8d
0x180005649  lea     rdx, aAlwayslogevent; "AlwaysLogEvents"
0x180005650  mov     rcx, r12
0x180005653  call    cs:__imp_?ReadDwordParameterValueFromAnyService@@YAKPEBG0K@Z; ReadDwordParameterValueFromAnyService(ushort const *,ushort const *,ulong)
0x180005659  test    eax, eax
0x18000565b  jnz     short loc_180005664
0x18000565d  mov     [rdi+630h], r15d
0x180005664  lea     rcx, [rbp+57h+var_80]
0x180005668  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000566e  mov     eax, ebx
0x180005670  mov     rcx, [rbp+57h+var_38]
0x180005674  xor     rcx, rsp; StackCookie
0x180005677  call    __security_check_cookie
0x18000567c  add     rsp, 98h
0x180005683  pop     r15
0x180005685  pop     r12
0x180005687  pop     rdi
0x180005688  pop     rsi
0x180005689  pop     rbx
0x18000568a  pop     rbp
0x18000568b  retn
```
