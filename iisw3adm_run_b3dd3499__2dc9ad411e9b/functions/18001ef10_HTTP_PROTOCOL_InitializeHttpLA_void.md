# HTTP_PROTOCOL::InitializeHttpLA(void)

- ea: `0x18001ef10`
- end: `0x18001f210`
- name: `?InitializeHttpLA@HTTP_PROTOCOL@@QEAAJXZ`
- size: `768`
- prototype: `__int64 __fastcall(HTTP_PROTOCOL *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000574c`

## callees

- `0x180001234`
- `0x1800058e4`
- `0x1800062d8`
- `0x1800073fc`
- `0x18001b568`
- `0x18001d018`
- `0x18001d170`
- `0x18001e7b0`
- `0x18001ef10`
- `0x18005f818`
- `0x18005f8e8`
- `0x18005fe10`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001f04b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001f04b`
- `iisutil!PuDbgPrintError` at `0x18001f0ab`
- `iisutil!PuDbgPrintError` at `0x18001f13c`
- `iisutil!PuDbgPrintError` at `0x18001f1a7`
- `iisutil!PuDbgPrintError` at `0x18001f0ab`
- `iisutil!PuDbgPrintError` at `0x18001f13c`
- `iisutil!PuDbgPrintError` at `0x18001f1a7`
- `iisutil!ReadDwordParameterValueFromAnyService` at `0x18001efee`
- `iisutil!ReadDwordParameterValueFromAnyService` at `0x18001efee`

## string_xrefs

- `0x18001f0a4`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\http_protocol.cxx`
- `0x18001f131`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\http_protocol.cxx`
- `0x18001f1a0`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\http_protocol.cxx`
- `0x18001ef71`: `Couldn't create the http wrapper`
- `0x18001f093`: `HTTP_PROTOCOL::InitializeHttpLA`
- `0x18001f125`: `HTTP_PROTOCOL::InitializeHttpLA`
- `0x18001f199`: `HTTP_PROTOCOL::InitializeHttpLA`
- `0x18001efe7`: `System\CurrentControlSet\Services\W3SVC\Parameters`
- `0x18001f087`: `Couldn't open UL control channel\n`

## pseudocode

```c
__int64 __fastcall HTTP_PROTOCOL::InitializeHttpLA(HTTP_PROTOCOL *this)
{
  HTTP_WRAPPER *v2; // rax
  int started; // ebx
  int v4; // eax
  unsigned int v5; // esi
  signed int v6; // eax
  int ControlChannel; // eax
  int v8; // eax
  void (__fastcall ***v9)(_QWORD, __int64); // rcx

  v2 = (HTTP_WRAPPER *)operator new(0x20u);
  if ( v2 )
  {
    *((_QWORD *)v2 + 1) = 1381453896;
    *(_QWORD *)v2 = &HTTP_WRAPPER::`vftable';
    *((_QWORD *)v2 + 2) = 0;
    *((_QWORD *)v2 + 3) = 0;
  }
  *((_QWORD *)this + 44) = v2;
  if ( v2 )
  {
    v4 = HTTP_WRAPPER::Initialize(v2);
    started = v4;
    if ( v4 )
    {
      if ( v4 > 0 )
        started = (unsigned __int16)v4 | 0x80070000;
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\http_protocol.cxx",
          963,
          "HTTP_PROTOCOL::InitializeHttpLA",
          started,
          "Couldn't initialize UL\n");
    }
    else
    {
      v5 = 1;
      if ( !*((_DWORD *)g_pWebAdminService + 412) )
      {
        if ( !ReadDwordParameterValueFromAnyService(
                L"System\\CurrentControlSet\\Services\\W3SVC\\Parameters",
                L"PerformanceCountersDisabled",
                0) )
          HTTP_PROTOCOL::ActivatePerfCounters(this);
        v6 = CASPPerfManager::Init((HTTP_PROTOCOL *)((char *)this + 392));
        if ( v6 >= 0 )
          *((_DWORD *)this + 92) = 1;
        else
          WEB_ADMIN_SERVICE::LogW3svcEvent(g_pWebAdminService, 0xC0000468, 0, 0, v6);
      }
      ControlChannel = HTTP_WRAPPER::CreateControlChannel(*((HTTP_WRAPPER **)this + 44));
      while ( 1 )
      {
        started = ControlChannel;
        if ( ControlChannel != 5 )
          break;
        if ( v5 > 5 )
          goto LABEL_22;
        Sleep(0x3E8u);
        ControlChannel = HTTP_WRAPPER::CreateControlChannel(*((HTTP_WRAPPER **)this + 44));
        ++v5;
      }
      if ( ControlChannel )
      {
LABEL_22:
        if ( ControlChannel > 0 )
          started = (unsigned __int16)ControlChannel | 0x80070000;
        if ( (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\http_protocol.cxx",
            1015,
            "HTTP_PROTOCOL::InitializeHttpLA",
            started,
            "Couldn't open UL control channel\n");
        WEB_ADMIN_SERVICE::LogW3svcEvent(g_pWebAdminService, 0xC000040D, 0, 0, started);
        goto LABEL_32;
      }
      v8 = HTTP_WRAPPER::SetControlChannelEndPointSharing(*((HTTP_WRAPPER **)this + 44), 1u);
      started = v8;
      if ( !v8 )
      {
        started = 0;
        HTTP_PROTOCOL::ApplyGlobalConfigChanges(this, 0);
        if ( (*((_BYTE *)g_pWebAdminService + 952) & 0x20) == 0
          || (started = WEB_ADMIN_SERVICE::StartHttpHandler(g_pWebAdminService), started >= 0) )
        {
          PROTOCOL::RequestConfiguration(this);
          WORK_QUEUE::GetAndQueueWorkItem(
            (WEB_ADMIN_SERVICE *)((char *)g_pWebAdminService + 16),
            g_pWebAdminService,
            0xCu);
          goto LABEL_41;
        }
        if ( (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\http_protocol.cxx",
            1105,
            "HTTP_PROTOCOL::InitializeHttpLA",
            started,
            "Failed start http_handler_container\n");
        goto LABEL_38;
      }
      if ( v8 > 0 )
        started = (unsigned __int16)v8 | 0x80070000;
      WEB_ADMIN_SERVICE::LogW3svcEvent(g_pWebAdminService, 0xC0000497, 0, 0, started);
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\http_protocol.cxx",
          1084,
          "HTTP_PROTOCOL::InitializeHttpLA",
          started,
          "Failed to enable endpoint sharing for control channel.\n");
    }
LABEL_32:
    if ( started >= 0 )
    {
LABEL_41:
      *((_DWORD *)this + 93) = 0;
      return (unsigned int)started;
    }
  }
  else
  {
    started = -2147024888;
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\http_protocol.cxx",
        945,
        "HTTP_PROTOCOL::InitializeHttpLA",
        -2147024888,
        "Couldn't create the http wrapper");
  }
LABEL_38:
  v9 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 44);
  if ( v9 )
  {
    (**v9)(v9, 1);
    *((_QWORD *)this + 44) = 0;
  }
  return (unsigned int)started;
}

```

## disassembly

```asm
0x18001ef10  mov     [rsp+arg_0], rbx
0x18001ef15  mov     [rsp+arg_8], rsi
0x18001ef1a  push    rdi
0x18001ef1b  sub     rsp, 30h
0x18001ef1f  mov     rdi, rcx
0x18001ef22  mov     ecx, 20h ; ' '; Size
0x18001ef27  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001ef2c  test    rax, rax
0x18001ef2f  jz      short loc_18001EF53
0x18001ef31  lea     rcx, ??_7HTTP_WRAPPER@@6B@; const HTTP_WRAPPER::`vftable'
0x18001ef38  mov     qword ptr [rax+8], 52575048h
0x18001ef40  mov     [rax], rcx
0x18001ef43  mov     qword ptr [rax+10h], 0
0x18001ef4b  mov     qword ptr [rax+18h], 0
0x18001ef53  mov     [rdi+160h], rax
0x18001ef5a  test    rax, rax
0x18001ef5d  jnz     short loc_18001EF90
0x18001ef5f  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18001ef66  mov     ebx, 80070008h
0x18001ef6b  jz      loc_18001F1AD
0x18001ef71  lea     rax, aCouldnTCreateT; "Couldn't create the http wrapper"
0x18001ef78  mov     r8d, 3B1h
0x18001ef7e  mov     [rsp+38h+var_10], rax
0x18001ef83  mov     [rsp+38h+var_18], 80070008h
0x18001ef8b  jmp     loc_18001F192
0x18001ef90  mov     rcx, rax; this
0x18001ef93  call    ?Initialize@HTTP_WRAPPER@@QEAAKXZ; HTTP_WRAPPER::Initialize(void)
0x18001ef98  mov     ebx, eax
0x18001ef9a  test    eax, eax
0x18001ef9c  jz      short loc_18001EFC8
0x18001ef9e  jle     short loc_18001EFA9
0x18001efa0  movzx   ebx, ax
0x18001efa3  or      ebx, 80070000h
0x18001efa9  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18001efb0  jz      loc_18001F142
0x18001efb6  lea     rax, aCouldnTInitial_1; "Couldn't initialize UL\n"
0x18001efbd  mov     r8d, 3C3h
0x18001efc3  jmp     loc_18001F11E
0x18001efc8  mov     rax, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x18001efcf  mov     esi, 1
0x18001efd4  cmp     dword ptr [rax+670h], 0
0x18001efdb  jnz     short loc_18001F033
0x18001efdd  xor     r8d, r8d
0x18001efe0  lea     rdx, aPerformancecou; "PerformanceCountersDisabled"
0x18001efe7  lea     rcx, aSystemCurrentc_4; "System\\CurrentControlSet\\Services\\W3"...
0x18001efee  call    cs:__imp_?ReadDwordParameterValueFromAnyService@@YAKPEBG0K@Z; ReadDwordParameterValueFromAnyService(ushort const *,ushort const *,ulong)
0x18001eff4  test    eax, eax
0x18001eff6  jnz     short loc_18001F000
0x18001eff8  mov     rcx, rdi; this
0x18001effb  call    ?ActivatePerfCounters@HTTP_PROTOCOL@@QEAAXXZ; HTTP_PROTOCOL::ActivatePerfCounters(void)
0x18001f000  lea     rcx, [rdi+188h]; this
0x18001f007  call    ?Init@CASPPerfManager@@QEAAJH@Z; CASPPerfManager::Init(int)
0x18001f00c  test    eax, eax
0x18001f00e  jns     short loc_18001F02D
0x18001f010  mov     rcx, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; this
0x18001f017  xor     r8d, r8d; unsigned __int16
0x18001f01a  xor     r9d, r9d; unsigned __int16 **
0x18001f01d  mov     [rsp+38h+var_18], eax; unsigned int
0x18001f021  mov     edx, 0C0000468h; unsigned int
0x18001f026  call    ?LogW3svcEvent@WEB_ADMIN_SERVICE@@QEAAXKGQEAPEBGK@Z; WEB_ADMIN_SERVICE::LogW3svcEvent(ulong,ushort,ushort const * * const,ulong)
0x18001f02b  jmp     short loc_18001F033
0x18001f02d  mov     [rdi+170h], esi
0x18001f033  mov     rcx, [rdi+160h]; this
0x18001f03a  call    ?CreateControlChannel@HTTP_WRAPPER@@QEAAKXZ; HTTP_WRAPPER::CreateControlChannel(void)
0x18001f03f  jmp     short loc_18001F05F
0x18001f041  cmp     esi, 5
0x18001f044  ja      short loc_18001F06A
0x18001f046  mov     ecx, 3E8h; dwMilliseconds
0x18001f04b  call    cs:__imp_Sleep
0x18001f051  mov     rcx, [rdi+160h]; this
0x18001f058  call    ?CreateControlChannel@HTTP_WRAPPER@@QEAAKXZ; HTTP_WRAPPER::CreateControlChannel(void)
0x18001f05d  inc     esi
0x18001f05f  mov     ebx, eax
0x18001f061  cmp     eax, 5
0x18001f064  jz      short loc_18001F041
0x18001f066  test    eax, eax
0x18001f068  jz      short loc_18001F0CE
0x18001f06a  test    ebx, ebx
0x18001f06c  jle     short loc_18001F077
0x18001f06e  movzx   ebx, bx
0x18001f071  or      ebx, 80070000h
0x18001f077  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18001f07e  jz      short loc_18001F0B1
0x18001f080  mov     rcx, cs:g_pDebug
0x18001f087  lea     rax, aCouldnTOpenUlC; "Couldn't open UL control channel\n"
0x18001f08e  mov     [rsp+38h+var_10], rax
0x18001f093  lea     r9, aHttpProtocolIn; "HTTP_PROTOCOL::InitializeHttpLA"
0x18001f09a  mov     r8d, 3F7h
0x18001f0a0  mov     [rsp+38h+var_18], ebx
0x18001f0a4  lea     rdx, aServercommonIn_29; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18001f0ab  call    cs:__imp_PuDbgPrintError
0x18001f0b1  mov     rcx, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; this
0x18001f0b8  xor     r8d, r8d; unsigned __int16
0x18001f0bb  xor     r9d, r9d; unsigned __int16 **
0x18001f0be  mov     [rsp+38h+var_18], ebx; unsigned int
0x18001f0c2  mov     edx, 0C000040Dh; unsigned int
0x18001f0c7  call    ?LogW3svcEvent@WEB_ADMIN_SERVICE@@QEAAXKGQEAPEBGK@Z; WEB_ADMIN_SERVICE::LogW3svcEvent(ulong,ushort,ushort const * * const,ulong)
0x18001f0cc  jmp     short loc_18001F142
0x18001f0ce  mov     rcx, [rdi+160h]; this
0x18001f0d5  mov     dl, 1; unsigned __int8
0x18001f0d7  call    ?SetControlChannelEndPointSharing@HTTP_WRAPPER@@QEAAKE@Z; HTTP_WRAPPER::SetControlChannelEndPointSharing(uchar)
0x18001f0dc  mov     ebx, eax
0x18001f0de  test    eax, eax
0x18001f0e0  jz      short loc_18001F14C
0x18001f0e2  jle     short loc_18001F0ED
0x18001f0e4  movzx   ebx, ax
0x18001f0e7  or      ebx, 80070000h
0x18001f0ed  mov     rcx, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; this
0x18001f0f4  xor     r8d, r8d; unsigned __int16
0x18001f0f7  xor     r9d, r9d; unsigned __int16 **
0x18001f0fa  mov     [rsp+38h+var_18], ebx; unsigned int
0x18001f0fe  mov     edx, 0C0000497h; unsigned int
0x18001f103  call    ?LogW3svcEvent@WEB_ADMIN_SERVICE@@QEAAXKGQEAPEBGK@Z; WEB_ADMIN_SERVICE::LogW3svcEvent(ulong,ushort,ushort const * * const,ulong)
0x18001f108  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18001f10f  jz      short loc_18001F142
0x18001f111  lea     rax, aFailedToEnable; "Failed to enable endpoint sharing for c"...
0x18001f118  mov     r8d, 43Ch
0x18001f11e  mov     rcx, cs:g_pDebug
0x18001f125  lea     r9, aHttpProtocolIn; "HTTP_PROTOCOL::InitializeHttpLA"
0x18001f12c  mov     [rsp+38h+var_10], rax
0x18001f131  lea     rdx, aServercommonIn_29; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18001f138  mov     [rsp+38h+var_18], ebx
0x18001f13c  call    cs:__imp_PuDbgPrintError
0x18001f142  test    ebx, ebx
0x18001f144  jns     loc_18001F1F4
0x18001f14a  jmp     short loc_18001F1AD
0x18001f14c  xor     edx, edx; struct GLOBAL_DATA_OBJECT *
0x18001f14e  mov     rcx, rdi; this
0x18001f151  xor     ebx, ebx
0x18001f153  call    ?ApplyGlobalConfigChanges@HTTP_PROTOCOL@@AEAAXPEAVGLOBAL_DATA_OBJECT@@@Z; HTTP_PROTOCOL::ApplyGlobalConfigChanges(GLOBAL_DATA_OBJECT *)
0x18001f158  mov     rcx, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; this
0x18001f15f  test    byte ptr [rcx+3B8h], 20h
0x18001f166  jz      short loc_18001F1D6
0x18001f168  call    ?StartHttpHandler@WEB_ADMIN_SERVICE@@QEAAJXZ; WEB_ADMIN_SERVICE::StartHttpHandler(void)
0x18001f16d  mov     ebx, eax
0x18001f16f  test    eax, eax
0x18001f171  jns     short loc_18001F1D6
0x18001f173  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18001f17a  jz      short loc_18001F1AD
0x18001f17c  lea     rax, aFailedStartHtt; "Failed start http_handler_container\n"
0x18001f183  mov     r8d, 451h
0x18001f189  mov     [rsp+38h+var_10], rax
0x18001f18e  mov     [rsp+38h+var_18], ebx
0x18001f192  mov     rcx, cs:g_pDebug
0x18001f199  lea     r9, aHttpProtocolIn; "HTTP_PROTOCOL::InitializeHttpLA"
0x18001f1a0  lea     rdx, aServercommonIn_29; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18001f1a7  call    cs:__imp_PuDbgPrintError
0x18001f1ad  mov     rcx, [rdi+160h]
0x18001f1b4  test    rcx, rcx
0x18001f1b7  jz      short loc_18001F1FE
0x18001f1b9  mov     rax, [rcx]
0x18001f1bc  mov     edx, 1
0x18001f1c1  mov     rax, [rax]
0x18001f1c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f1c9  mov     qword ptr [rdi+160h], 0
0x18001f1d4  jmp     short loc_18001F1FE
0x18001f1d6  mov     rcx, rdi; this
0x18001f1d9  call    ?RequestConfiguration@PROTOCOL@@QEAAXXZ; PROTOCOL::RequestConfiguration(void)
0x18001f1de  mov     rdx, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; struct WORK_DISPATCH *
0x18001f1e5  mov     r8d, 0Ch; unsigned __int64
0x18001f1eb  lea     rcx, [rdx+10h]; this
0x18001f1ef  call    ?GetAndQueueWorkItem@WORK_QUEUE@@QEAAJPEAVWORK_DISPATCH@@_K@Z; WORK_QUEUE::GetAndQueueWorkItem(WORK_DISPATCH *,unsigned __int64)
0x18001f1f4  mov     dword ptr [rdi+174h], 0
0x18001f1fe  mov     rsi, [rsp+38h+arg_8]
0x18001f203  mov     eax, ebx
0x18001f205  mov     rbx, [rsp+38h+arg_0]
0x18001f20a  add     rsp, 30h
0x18001f20e  pop     rdi
0x18001f20f  retn
```
