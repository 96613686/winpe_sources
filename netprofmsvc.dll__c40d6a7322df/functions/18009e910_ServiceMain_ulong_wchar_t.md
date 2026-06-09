# ServiceMain(ulong,wchar_t * *)

- ea: `0x18009e910`
- end: `0x18009ea97`
- name: `?ServiceMain@@YAXKPEAPEA_W@Z`
- size: `391`
- prototype: `void __fastcall(int, LPCWCH *, __int64, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180020d20`
- `0x1800713b8`
- `0x18008c08c`
- `0x18009e910`
- `0x18009eaa0`
- `0x18009eb98`
- `0x1800bba00`
- `0x1800bbc4c`
- `0x1800bc018`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18009e96f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18009e9f9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18009e96f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18009e9f9`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18009e98b`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18009ea25`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18009e98b`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18009ea25`

## string_xrefs

- `0x18009e933`: `onecore\net\netprofiles\service\src\host\dll\servicemain.cpp`
- `0x18009e9a7`: `onecore\net\netprofiles\service\src\host\dll\servicemain.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ServiceMain(int a1, LPCWCH *a2, __int64 a3, __int64 a4, unsigned int a5)
{
  __int64 v6; // r9
  __int64 v7; // rdx
  const char *v8; // r9
  __int64 v9; // rdx
  int started; // eax
  __int64 v11; // rcx
  int v12; // eax
  __int64 v13; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( !qword_1801C7E28 )
  {
    v6 = 13;
    v7 = 303;
LABEL_3:
    wil::details::in1diag3::Log_Win32(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\host\\dll\\servicemain.cpp",
      (const char *)v6,
      a5);
    return;
  }
  if ( !a1 )
  {
    v6 = 87;
    v7 = 309;
    goto LABEL_3;
  }
  if ( CompareStringOrdinal(*a2, -1, L"NlaSvc", -1, 1) == 2 )
  {
    qword_1801C7E18 = RegisterServiceCtrlHandlerExW(L"NlaSvc", NlaServiceControlHandler, 0);
    if ( !qword_1801C7E18 )
    {
      v9 = 321;
LABEL_9:
      wil::details::in1diag3::_Log_GetLastError(
        retaddr,
        (void *)v9,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\host\\dll\\servicemain.cpp",
        v8);
      return;
    }
    started = StartNlaService();
    v11 = (unsigned int)started;
    if ( started < 0 )
    {
      if ( (started & 0x1FFF0000) == 0x70000 )
        v11 = (unsigned __int16)started;
      StopNlaService(v11);
    }
  }
  else
  {
    if ( CompareStringOrdinal(*a2, -1, L"netprofm", -1, 1) != 2 )
    {
      v6 = 87;
      v7 = 335;
      goto LABEL_3;
    }
    hServiceStatus = RegisterServiceCtrlHandlerExW(L"netprofm", ServiceControlHandler, 0);
    if ( !hServiceStatus )
    {
      v9 = 342;
      goto LABEL_9;
    }
    if ( (unsigned int)IsSystemSetupInProgress() )
    {
      UpdateServiceStatus(1);
      hServiceStatus = 0;
    }
    else
    {
      UpdateServiceStatus(2);
      v12 = StartNetprofmService();
      v13 = (unsigned int)v12;
      if ( v12 < 0 )
      {
        if ( (v12 & 0x1FFF0000) == 0x70000 )
          v13 = (unsigned __int16)v12;
        StopNetprofmService(v13);
      }
    }
  }
}

```

## disassembly

```asm
0x18009e910  push    rbx
0x18009e912  sub     rsp, 30h
0x18009e916  cmp     cs:qword_1801C7E28, 0
0x18009e91e  mov     rbx, rdx
0x18009e921  jnz     short loc_18009E944
0x18009e923  mov     r9d, 0Dh; char *
0x18009e929  mov     edx, 12Fh; void *
0x18009e92e  mov     rcx, [rsp+38h]; this
0x18009e933  lea     r8, aOnecoreNetNetp_5; "onecore\\net\\netprofiles\\service\\src"...
0x18009e93a  add     rsp, 30h
0x18009e93e  pop     rbx
0x18009e93f  jmp     ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x18009e944  cmp     ecx, 1
0x18009e947  jnb     short loc_18009E956
0x18009e949  mov     r9d, 57h ; 'W'
0x18009e94f  mov     edx, 135h
0x18009e954  jmp     short loc_18009E92E
0x18009e956  mov     r8, cs:lpServiceName; lpString2
0x18009e95d  or      r9d, 0FFFFFFFFh; cchCount2
0x18009e961  mov     rcx, [rbx]; lpString1
0x18009e964  or      edx, r9d; cchCount1
0x18009e967  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x18009e96f  call    cs:__imp_CompareStringOrdinal
0x18009e975  cmp     eax, 2
0x18009e978  jnz     short loc_18009E9E0
0x18009e97a  mov     rcx, cs:lpServiceName; lpServiceName
0x18009e981  lea     rdx, ?NlaServiceControlHandler@@YAKKKPEAX0@Z; lpHandlerProc
0x18009e988  xor     r8d, r8d; lpContext
0x18009e98b  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x18009e991  mov     cs:qword_1801C7E18, rax
0x18009e998  test    rax, rax
0x18009e99b  jnz     short loc_18009E9B8
0x18009e99d  mov     edx, 141h; void *
0x18009e9a2  mov     rcx, [rsp+38h]; this
0x18009e9a7  lea     r8, aOnecoreNetNetp_5; "onecore\\net\\netprofiles\\service\\src"...
0x18009e9ae  add     rsp, 30h
0x18009e9b2  pop     rbx
0x18009e9b3  jmp     ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18009e9b8  call    StartNlaService
0x18009e9bd  mov     ecx, eax
0x18009e9bf  test    eax, eax
0x18009e9c1  jns     loc_18009EA91
0x18009e9c7  and     eax, 1FFF0000h
0x18009e9cc  cmp     eax, 70000h
0x18009e9d1  jnz     short loc_18009E9D6
0x18009e9d3  movzx   ecx, cx
0x18009e9d6  add     rsp, 30h
0x18009e9da  pop     rbx
0x18009e9db  jmp     StopNlaService
0x18009e9e0  mov     r8, cs:lpString2; lpString2
0x18009e9e7  or      r9d, 0FFFFFFFFh; cchCount2
0x18009e9eb  mov     rcx, [rbx]; lpString1
0x18009e9ee  or      edx, r9d; cchCount1
0x18009e9f1  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x18009e9f9  call    cs:__imp_CompareStringOrdinal
0x18009e9ff  cmp     eax, 2
0x18009ea02  jz      short loc_18009EA14
0x18009ea04  mov     r9d, 57h ; 'W'
0x18009ea0a  mov     edx, 14Fh
0x18009ea0f  jmp     loc_18009E92E
0x18009ea14  mov     rcx, cs:lpString2; lpServiceName
0x18009ea1b  lea     rdx, ?ServiceControlHandler@@YAKKKPEAX0@Z; lpHandlerProc
0x18009ea22  xor     r8d, r8d; lpContext
0x18009ea25  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x18009ea2b  mov     cs:hServiceStatus, rax
0x18009ea32  test    rax, rax
0x18009ea35  jnz     short loc_18009EA41
0x18009ea37  mov     edx, 156h
0x18009ea3c  jmp     loc_18009E9A2
0x18009ea41  call    IsSystemSetupInProgress
0x18009ea46  test    eax, eax
0x18009ea48  jz      short loc_18009EA68
0x18009ea4a  mov     edx, 15h
0x18009ea4f  lea     ecx, [rdx-14h]
0x18009ea52  call    UpdateServiceStatus
0x18009ea57  mov     cs:hServiceStatus, 0
0x18009ea62  add     rsp, 30h
0x18009ea66  pop     rbx
0x18009ea67  retn
0x18009ea68  xor     edx, edx
0x18009ea6a  lea     ecx, [rdx+2]
0x18009ea6d  call    UpdateServiceStatus
0x18009ea72  call    StartNetprofmService
0x18009ea77  mov     ecx, eax
0x18009ea79  test    eax, eax
0x18009ea7b  jns     short loc_18009EA91
0x18009ea7d  and     eax, 1FFF0000h
0x18009ea82  cmp     eax, 70000h
0x18009ea87  jnz     short loc_18009EA8C
0x18009ea89  movzx   ecx, cx
0x18009ea8c  call    StopNetprofmService
0x18009ea91  add     rsp, 30h
0x18009ea95  pop     rbx
0x18009ea96  retn
```
