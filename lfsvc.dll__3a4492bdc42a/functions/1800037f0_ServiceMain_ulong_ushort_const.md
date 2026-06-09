# ServiceMain(ulong,ushort * * const)

- ea: `0x1800037f0`
- end: `0x180003ad5`
- name: `?ServiceMain@@YAXKQEAPEAG@Z`
- size: `741`
- prototype: `void __fastcall(int, LPCWSTR *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1800023d0`
- `0x18000301c`
- `0x1800037f0`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800038d3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800038d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003893`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800038e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003893`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800038e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003aac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003aac`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180003881`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180003881`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180003a8b`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180003a8b`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x180003962`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x180003a75`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x180003962`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x180003a75`
- `LocationFramework!SvcLocationInitServerLock` at `0x180003932`
- `LocationFramework!SvcLocationInitServerLock` at `0x180003932`
- `LocationFramework!RegisterLocationCOMServer` at `0x180003986`
- `LocationFramework!RegisterLocationCOMServer` at `0x180003986`

## string_xrefs

- `0x180003826`: `onecoreuap\drivers\mobilepc\location\product\core\service\lfsvc\servicemain.cpp`
- `0x1800039ac`: `onecoreuap\drivers\mobilepc\location\product\core\service\lfsvc\servicemain.cpp`
- `0x180003a3e`: `onecoreuap\drivers\mobilepc\location\product\core\service\lfsvc\servicemain.cpp`
- `0x180003832`: `ServiceMain`
- `0x1800039a1`: `ServiceMain`
- `0x180003a45`: `ServiceMain`
- `0x1800038ff`: `CreateEvent`
- `0x1800038ad`: `RegisterServiceCtrlHandlerEx`
- `0x180003914`: `g_serviceHostGlobalData == nullptr`
- `0x180003995`: `RegisterLocationCOMServer`

## pseudocode

```c
void __fastcall ServiceMain(int a1, LPCWSTR *a2)
{
  int v3; // edi
  signed int v4; // eax
  signed int v5; // ebx
  __int64 v6; // rdx
  const char *v7; // r11
  signed int LastError; // eax
  int inited; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  char *v13; // [rsp+28h] [rbp-40h]
  const char *v14; // [rsp+38h] [rbp-30h]
  _OWORD v15[2]; // [rsp+40h] [rbp-28h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+68h] [rbp+0h]

  if ( !a1 )
  {
    LODWORD(v13) = -2147024736;
    wil::details::in1diag5::Log_IfFailedMsg(
      retaddr,
      (void *)0xF3,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\service\\lfsvc\\servicemain.cpp",
      "ServiceMain",
      "hr",
      v13,
      (int)"argc == 0",
      v14);
    goto LABEL_27;
  }
  ServiceStatus.dwServiceType = 32;
  memset(v15, 0, 20);
  v3 = 0;
  *(_OWORD *)&ServiceStatus.dwCurrentState = *(_OWORD *)((char *)v15 + 4);
  *(_QWORD *)&ServiceStatus.dwCheckPoint = *(_OWORD *)&_mm_unpackhi_pd((__m128d)0LL, (__m128d)0LL);
  hServiceStatus = RegisterServiceCtrlHandlerExW(*a2, ServiceHandler, 0);
  if ( hServiceStatus )
  {
    SvcEngUpdateServiceStatus(2u, 0, 0x2710u);
    hObject = CreateEventW(0, 0, 0, 0);
    if ( hObject )
    {
      if ( !qword_180012450 )
      {
        LODWORD(v13) = -2147418113;
        wil::details::in1diag5::Log_IfFailedMsg(
          retaddr,
          (void *)0x112,
          (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\service\\lfsvc\\servicemain.cpp",
          "ServiceMain",
          "hr",
          v13,
          (int)"g_serviceHostGlobalData == nullptr",
          v14);
        goto LABEL_27;
      }
      inited = SvcLocationInitServerLock();
      if ( inited < 0 )
      {
        LODWORD(v13) = inited;
        wil::details::in1diag5::Log_IfFailedMsg(
          retaddr,
          (void *)0x11C,
          (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\service\\lfsvc\\servicemain.cpp",
          "ServiceMain",
          "hr",
          v13,
          (int)"SvcLocationInitServerLock",
          v14);
        goto LABEL_27;
      }
      v10 = CoRegisterServerShutdownDelay(hObject, 10000);
      if ( v10 < 0 )
      {
        LODWORD(v13) = v10;
        wil::details::in1diag5::Log_IfFailedMsg(
          retaddr,
          (void *)0x123,
          (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\service\\lfsvc\\servicemain.cpp",
          "ServiceMain",
          "hr",
          v13,
          (int)"CoRegisterServerShutdownDelay",
          v14);
        goto LABEL_27;
      }
      v11 = RegisterLocationCOMServer();
      if ( v11 < 0 )
      {
        LODWORD(v13) = v11;
        wil::details::in1diag5::Log_IfFailedMsg(
          retaddr,
          (void *)0x12E,
          (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\service\\lfsvc\\servicemain.cpp",
          "ServiceMain",
          "hr",
          v13,
          (int)"RegisterLocationCOMServer",
          v14);
LABEL_26:
        CoRegisterServerShutdownDelay(0, 0);
        goto LABEL_27;
      }
      SvcEngUpdateServiceStatus(4u, 0, 0);
      v12 = (*(__int64 (__fastcall **)(HANDLE *, LPCWSTR, HANDLE, __int64 (__fastcall *)(), _QWORD, int))(qword_180012450 + 192))(
              &WaitHandle,
              *a2,
              hObject,
              ServiceCallbackOnStopping,
              0,
              24);
      v5 = v12;
      if ( !v12 )
        return;
      v3 = 1;
      if ( v12 > 0 )
        v5 = (unsigned __int16)v12 | 0x80070000;
      v6 = 318;
      v7 = "RegisterStopCallback";
    }
    else
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      v6 = 267;
      v7 = "CreateEvent";
    }
  }
  else
  {
    v4 = GetLastError();
    v5 = v4;
    if ( v4 > 0 )
      v5 = (unsigned __int16)v4 | 0x80070000;
    v6 = 257;
    v7 = "RegisterServiceCtrlHandlerEx";
  }
  LODWORD(v13) = v5;
  wil::details::in1diag5::Log_IfFailedMsg(
    retaddr,
    (void *)v6,
    (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\service\\lfsvc\\servicemain.cpp",
    "ServiceMain",
    "hr",
    v13,
    (int)v7,
    v14);
  if ( v5 >= 0 )
    return;
  if ( v3 )
    goto LABEL_26;
LABEL_27:
  if ( WaitHandle && UnregisterWaitEx(WaitHandle, (HANDLE)0xFFFFFFFFFFFFFFFFLL) )
    WaitHandle = 0;
  if ( hObject )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  SvcEngUpdateServiceStatus(1u, 0, 0);
}

```

## disassembly

```asm
0x1800037f0  mov     [rsp+arg_0], rbx
0x1800037f5  push    rdi
0x1800037f6  sub     rsp, 60h
0x1800037fa  mov     rbx, rdx
0x1800037fd  test    ecx, ecx
0x1800037ff  jnz     short loc_180003843
0x180003801  lea     rax, aArgc0; "argc == 0"
0x180003808  mov     edx, 0F3h; void *
0x18000380d  mov     qword ptr [rsp+68h+var_38], rax; int
0x180003812  mov     dword ptr [rsp+68h+var_40], 800700A0h; char *
0x18000381a  mov     rcx, [rsp+68h]; this
0x18000381f  lea     rax, aHr; "hr"
0x180003826  lea     r8, aOnecoreuapDriv; "onecoreuap\\drivers\\mobilepc\\location"...
0x18000382d  mov     [rsp+68h+var_48], rax; char *
0x180003832  lea     r9, aServicemain_0; "ServiceMain"
0x180003839  call    ?Log_IfFailedMsg@in1diag5@details@wil@@YAJPEAXIPEBD11J1ZZ; wil::details::in1diag5::Log_IfFailedMsg(void *,uint,char const *,char const *,char const *,long,char const *,...)
0x18000383e  jmp     loc_180003A7B
0x180003843  xorps   xmm1, xmm1
0x180003846  mov     cs:ServiceStatus.dwServiceType, 20h ; ' '
0x180003850  movups  [rsp+68h+var_28], xmm1
0x180003855  xor     r8d, r8d; lpContext
0x180003858  lea     rdx, ServiceHandler; lpHandlerProc
0x18000385f  movups  [rsp+68h+var_28+0Ch], xmm1
0x180003864  xor     edi, edi
0x180003866  movups  xmm0, [rsp+68h+var_28+4]
0x18000386b  unpckhpd xmm1, xmm1
0x18000386f  movups  xmmword ptr cs:ServiceStatus.dwCurrentState, xmm0
0x180003876  movsd   qword ptr cs:ServiceStatus.dwCheckPoint, xmm1
0x18000387e  mov     rcx, [rbx]; lpServiceName
0x180003881  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180003887  mov     cs:hServiceStatus, rax
0x18000388e  test    rax, rax
0x180003891  jnz     short loc_1800038B9
0x180003893  call    cs:__imp_GetLastError
0x180003899  mov     ebx, eax
0x18000389b  test    eax, eax
0x18000389d  jle     short loc_1800038A8
0x18000389f  movzx   ebx, ax
0x1800038a2  or      ebx, 80070000h
0x1800038a8  mov     edx, 101h
0x1800038ad  lea     r11, aRegisterservic; "RegisterServiceCtrlHandlerEx"
0x1800038b4  jmp     loc_180003A39
0x1800038b9  xor     edx, edx; unsigned int
0x1800038bb  mov     r8d, 2710h; unsigned int
0x1800038c1  lea     ecx, [rdx+2]; unsigned int
0x1800038c4  call    ?SvcEngUpdateServiceStatus@@YAJKKK@Z; SvcEngUpdateServiceStatus(ulong,ulong,ulong)
0x1800038c9  xor     r9d, r9d; lpName
0x1800038cc  xor     r8d, r8d; bInitialState
0x1800038cf  xor     edx, edx; bManualReset
0x1800038d1  xor     ecx, ecx; lpEventAttributes
0x1800038d3  call    cs:__imp_CreateEventW
0x1800038d9  mov     cs:hObject, rax
0x1800038e0  test    rax, rax
0x1800038e3  jnz     short loc_18000390B
0x1800038e5  call    cs:__imp_GetLastError
0x1800038eb  mov     ebx, eax
0x1800038ed  test    eax, eax
0x1800038ef  jle     short loc_1800038FA
0x1800038f1  movzx   ebx, ax
0x1800038f4  or      ebx, 80070000h
0x1800038fa  mov     edx, 10Bh
0x1800038ff  lea     r11, aCreateevent; "CreateEvent"
0x180003906  jmp     loc_180003A39
0x18000390b  cmp     cs:qword_180012450, rdi
0x180003912  jnz     short loc_180003932
0x180003914  lea     rax, aGServicehostgl; "g_serviceHostGlobalData == nullptr"
0x18000391b  mov     edx, 112h
0x180003920  mov     qword ptr [rsp+68h+var_38], rax
0x180003925  mov     dword ptr [rsp+68h+var_40], 8000FFFFh
0x18000392d  jmp     loc_18000381A
0x180003932  call    cs:__imp_?SvcLocationInitServerLock@@YAJXZ; SvcLocationInitServerLock(void)
0x180003938  test    eax, eax
0x18000393a  jns     short loc_180003956
0x18000393c  lea     rdx, aSvclocationini; "SvcLocationInitServerLock"
0x180003943  mov     qword ptr [rsp+68h+var_38], rdx
0x180003948  mov     edx, 11Ch
0x18000394d  mov     dword ptr [rsp+68h+var_40], eax
0x180003951  jmp     loc_18000381A
0x180003956  mov     rcx, cs:hObject
0x18000395d  mov     edx, 2710h
0x180003962  call    cs:__imp_CoRegisterServerShutdownDelay
0x180003968  test    eax, eax
0x18000396a  jns     short loc_180003986
0x18000396c  lea     rdx, aCoregisterserv; "CoRegisterServerShutdownDelay"
0x180003973  mov     qword ptr [rsp+68h+var_38], rdx
0x180003978  mov     edx, 123h
0x18000397d  mov     dword ptr [rsp+68h+var_40], eax
0x180003981  jmp     loc_18000381A
0x180003986  call    cs:__imp_?RegisterLocationCOMServer@@YAJXZ; RegisterLocationCOMServer(void)
0x18000398c  test    eax, eax
0x18000398e  jns     short loc_1800039CE
0x180003990  mov     rcx, [rsp+68h]; this
0x180003995  lea     rdx, aRegisterlocati; "RegisterLocationCOMServer"
0x18000399c  mov     qword ptr [rsp+68h+var_38], rdx; int
0x1800039a1  lea     r9, aServicemain_0; "ServiceMain"
0x1800039a8  mov     dword ptr [rsp+68h+var_40], eax; char *
0x1800039ac  lea     r8, aOnecoreuapDriv; "onecoreuap\\drivers\\mobilepc\\location"...
0x1800039b3  lea     rax, aHr; "hr"
0x1800039ba  mov     edx, 12Eh; void *
0x1800039bf  mov     [rsp+68h+var_48], rax; char *
0x1800039c4  call    ?Log_IfFailedMsg@in1diag5@details@wil@@YAJPEAXIPEBD11J1ZZ; wil::details::in1diag5::Log_IfFailedMsg(void *,uint,char const *,char const *,char const *,long,char const *,...)
0x1800039c9  jmp     loc_180003A71
0x1800039ce  xor     edx, edx; unsigned int
0x1800039d0  xor     r8d, r8d; unsigned int
0x1800039d3  lea     ecx, [rdx+4]; unsigned int
0x1800039d6  call    ?SvcEngUpdateServiceStatus@@YAJKKK@Z; SvcEngUpdateServiceStatus(ulong,ulong,ulong)
0x1800039db  mov     rax, cs:qword_180012450
0x1800039e2  lea     r9, ServiceCallbackOnStopping
0x1800039e9  mov     r8, cs:hObject
0x1800039f0  lea     rcx, WaitHandle
0x1800039f7  mov     rdx, [rbx]
0x1800039fa  mov     dword ptr [rsp+68h+var_40], 18h
0x180003a02  mov     rax, [rax+0C0h]
0x180003a09  mov     [rsp+68h+var_48], rdi
0x180003a0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a13  mov     ebx, eax
0x180003a15  test    eax, eax
0x180003a17  jz      loc_180003ACA
0x180003a1d  mov     edi, 1
0x180003a22  jle     short loc_180003A2D
0x180003a24  movzx   ebx, ax
0x180003a27  or      ebx, 80070000h
0x180003a2d  mov     edx, 13Eh; void *
0x180003a32  lea     r11, aRegisterstopca; "RegisterStopCallback"
0x180003a39  mov     rcx, [rsp+68h]; this
0x180003a3e  lea     r8, aOnecoreuapDriv; "onecoreuap\\drivers\\mobilepc\\location"...
0x180003a45  lea     r9, aServicemain_0; "ServiceMain"
0x180003a4c  mov     r10d, ebx
0x180003a4f  lea     rax, aHr; "hr"
0x180003a56  mov     qword ptr [rsp+68h+var_38], r11; int
0x180003a5b  mov     dword ptr [rsp+68h+var_40], ebx; char *
0x180003a5f  mov     [rsp+68h+var_48], rax; char *
0x180003a64  call    ?Log_IfFailedMsg@in1diag5@details@wil@@YAJPEAXIPEBD11J1ZZ; wil::details::in1diag5::Log_IfFailedMsg(void *,uint,char const *,char const *,char const *,long,char const *,...)
0x180003a69  test    ebx, ebx
0x180003a6b  jns     short loc_180003ACA
0x180003a6d  test    edi, edi
0x180003a6f  jz      short loc_180003A7B
0x180003a71  xor     edx, edx
0x180003a73  xor     ecx, ecx
0x180003a75  call    cs:__imp_CoRegisterServerShutdownDelay
0x180003a7b  mov     rcx, cs:WaitHandle; WaitHandle
0x180003a82  test    rcx, rcx
0x180003a85  jz      short loc_180003AA0
0x180003a87  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180003a8b  call    cs:__imp_UnregisterWaitEx
0x180003a91  test    eax, eax
0x180003a93  jz      short loc_180003AA0
0x180003a95  mov     cs:WaitHandle, 0
0x180003aa0  mov     rcx, cs:hObject; hObject
0x180003aa7  test    rcx, rcx
0x180003aaa  jz      short loc_180003ABD
0x180003aac  call    cs:__imp_CloseHandle
0x180003ab2  mov     cs:hObject, 0
0x180003abd  xor     edx, edx; unsigned int
0x180003abf  xor     r8d, r8d; unsigned int
0x180003ac2  lea     ecx, [rdx+1]; unsigned int
0x180003ac5  call    ?SvcEngUpdateServiceStatus@@YAJKKK@Z; SvcEngUpdateServiceStatus(ulong,ulong,ulong)
0x180003aca  mov     rbx, [rsp+68h+arg_0]
0x180003acf  add     rsp, 60h
0x180003ad3  pop     rdi
0x180003ad4  retn
```
