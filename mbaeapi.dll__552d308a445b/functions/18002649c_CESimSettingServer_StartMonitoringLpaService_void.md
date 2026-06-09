# CESimSettingServer::StartMonitoringLpaService(void)

- ea: `0x18002649c`
- end: `0x180026723`
- name: `?StartMonitoringLpaService@CESimSettingServer@@AEAAJXZ`
- size: `647`
- prototype: `__int64 __fastcall(CESimSettingServer *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task`

## callers

- `0x18001f234`

## callees

- `0x18000178c`
- `0x1800024e0`
- `0x180009454`
- `0x180009474`
- `0x180009ffc`
- `0x18001105c`
- `0x1800172bc`
- `0x18001dd10`
- `0x18002649c`
- `0x180028560`
- `0x1800285b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026570`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026570`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026558`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026558`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800265b8`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800265c2`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800266d3`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800266dd`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800265b8`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800265c2`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800266d3`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800266dd`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180026512`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180026512`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800264ce`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800264ce`
- `api-ms-win-service-private-l1-1-0!SubscribeServiceChangeNotifications` at `0x18002660a`
- `api-ms-win-service-private-l1-1-0!SubscribeServiceChangeNotifications` at `0x18002660a`
- `luiapi!LuiOpenHandle` at `0x18002658d`
- `luiapi!LuiOpenHandle` at `0x18002658d`
- `luiapi!LuiCloseHandle` at `0x180026568`
- `luiapi!LuiCloseHandle` at `0x180026568`
- `luiapi!LuiRegisterForLpaNotifications` at `0x1800265da`
- `luiapi!LuiRegisterForLpaNotifications` at `0x1800265da`

## string_xrefs

- `0x18002667c`: `CESimSettingServer::StartMonitoringLpaService`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CESimSettingServer::StartMonitoringLpaService(CESimSettingServer *this)
{
  SC_HANDLE v2; // rax
  const char *v3; // r9
  SC_HANDLE v4; // rbx
  SC_HANDLE v6; // rdi
  const char *v7; // r9
  unsigned int LastError; // esi
  unsigned int v9; // r12d
  _QWORD *v10; // r15
  const unsigned __int16 *v11; // r13
  DWORD v12; // esi
  int v13; // eax
  int v14; // eax
  unsigned int v15; // eax
  void *v16; // rdx
  unsigned int v17; // r8d
  const struct _tlgProvider_t *v18; // rax
  __int64 v19; // r8
  __int64 v20; // r9
  int v21; // [rsp+20h] [rbp-69h]
  char *v22; // [rsp+20h] [rbp-69h]
  int v23; // [rsp+30h] [rbp-59h] BYREF
  unsigned __int16 *v24; // [rsp+38h] [rbp-51h] BYREF
  unsigned __int16 *v25[2]; // [rsp+40h] [rbp-49h] BYREF
  __int64 v26; // [rsp+50h] [rbp-39h]
  unsigned __int16 *v27[2]; // [rsp+58h] [rbp-31h] BYREF
  __int64 v28; // [rsp+68h] [rbp-21h]
  SC_HANDLE v29; // [rsp+70h] [rbp-19h]
  SC_HANDLE v30; // [rsp+78h] [rbp-11h]
  WCHAR ServiceName[8]; // [rsp+80h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v2 = OpenSCManagerW(0, 0, 1u);
  v4 = v2;
  v29 = v2;
  if ( !v2 )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x49,
             (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\esimsettingserver.cpp",
             v3);
  wcscpy(ServiceName, L"wlpasvc");
  v6 = OpenServiceW(v2, ServiceName, 4u);
  v30 = v6;
  if ( !v6 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x4D,
                  (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\esimsettingserver.cpp",
                  v7);
LABEL_9:
    CloseServiceHandle(v4);
    return LastError;
  }
  v9 = *((_BYTE *)this + 120) != 0 ? 2 : 0;
  v10 = (_QWORD *)((char *)this + 112);
  v11 = (const unsigned __int16 *)*((_QWORD *)this + 14);
  if ( v11 != (const unsigned __int16 *)-1LL )
  {
    v12 = GetLastError();
    v24 = (unsigned __int16 *)v11;
    LuiCloseHandle(&v24);
    SetLastError(v12);
  }
  *v10 = -1;
  v13 = LuiOpenHandle((char *)this + 112, v9, &CESimSettingServer::ProcessLpaCallback, this);
  LastError = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x56,
      (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\esimsettingserver.cpp",
      (const char *)(unsigned int)v13,
      v21);
    CloseServiceHandle(v6);
    goto LABEL_9;
  }
  v23 = 0;
  v14 = LuiRegisterForLpaNotifications(*v10, &v23);
  if ( v14 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x5A,
      (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\esimsettingserver.cpp",
      (const char *)(unsigned int)v14,
      v21);
  v22 = (char *)this + 128;
  v15 = SubscribeServiceChangeNotifications(v6, 2, CESimSettingServer::s_LpaServiceStateNotification, this);
  if ( v15 )
    wil::details::in1diag3::_FailFast_Win32(retaddr, v16, v17, (const char *)v15, (unsigned int)v22);
  *(_OWORD *)v27 = 0;
  v28 = 0;
  *(_OWORD *)v25 = 0;
  v26 = 0;
  std::vector<unsigned short>::resize(v27);
  std::vector<unsigned short>::resize(v25);
  StringCchPrintfW(v27[0], v27[1] - v27[0], L"LpaSvc monitoring started.");
  LODWORD(v22) = 96;
  StringCchPrintfW(v25[0], v25[1] - v25[0], L"%S(%d):%s", "CESimSettingServer::StartMonitoringLpaService", v22, v27[0]);
  v18 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v18 > 4u )
  {
    v24 = v25[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v18,
      (__int64)&dword_180075E6C,
      v19,
      v20,
      (const unsigned __int16 **)&v24);
  }
  std::vector<unsigned short>::~vector<unsigned short>((char **)v25);
  std::vector<unsigned short>::~vector<unsigned short>((char **)v27);
  CloseServiceHandle(v6);
  CloseServiceHandle(v4);
  return 0;
}

```

## disassembly

```asm
0x18002649c  push    rbp
0x18002649e  push    rbx
0x18002649f  push    rsi
0x1800264a0  push    rdi
0x1800264a1  push    r12
0x1800264a3  push    r13
0x1800264a5  push    r14
0x1800264a7  push    r15
0x1800264a9  lea     rbp, [rsp-1Fh]
0x1800264ae  sub     rsp, 0A8h
0x1800264b5  mov     rax, cs:__security_cookie
0x1800264bc  xor     rax, rsp
0x1800264bf  mov     [rbp+57h+var_50], rax
0x1800264c3  mov     r14, rcx
0x1800264c6  xor     edx, edx; lpDatabaseName
0x1800264c8  xor     ecx, ecx; lpMachineName
0x1800264ca  lea     r8d, [rdx+1]; dwDesiredAccess
0x1800264ce  call    cs:__imp_OpenSCManagerW
0x1800264d4  mov     rbx, rax
0x1800264d7  mov     [rbp+57h+var_70], rax
0x1800264db  test    rax, rax
0x1800264de  jnz     short loc_1800264F9
0x1800264e0  mov     rcx, [rbp+5Fh]; this
0x1800264e4  lea     r8, aOnecoreuapNetM_5; "onecoreuap\\net\\mobilebroadbandexperie"...
0x1800264eb  lea     edx, [rax+49h]; void *
0x1800264ee  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800264f3  nop
0x1800264f4  jmp     loc_1800266E5
0x1800264f9  movups  xmm0, xmmword ptr cs:aWlpasvc; "wlpasvc"
0x180026500  movdqu  xmmword ptr [rbp+57h+ServiceName], xmm0
0x180026505  mov     r8d, 4; dwDesiredAccess
0x18002650b  lea     rdx, [rbp+57h+ServiceName]; lpServiceName
0x18002650f  mov     rcx, rbx; hSCManager
0x180026512  call    cs:__imp_OpenServiceW
0x180026518  mov     rdi, rax
0x18002651b  mov     [rbp+57h+var_68], rax
0x18002651f  test    rax, rax
0x180026522  jnz     short loc_18002653E
0x180026524  mov     rcx, [rbp+5Fh]; this
0x180026528  lea     r8, aOnecoreuapNetM_5; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18002652f  lea     edx, [rax+4Dh]; void *
0x180026532  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180026537  mov     esi, eax
0x180026539  jmp     loc_1800265BF
0x18002653e  mov     al, [r14+78h]
0x180026542  neg     al
0x180026544  sbb     r12d, r12d
0x180026547  and     r12d, 2
0x18002654b  lea     r15, [r14+70h]
0x18002654f  mov     r13, [r15]
0x180026552  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x180026556  jz      short loc_180026576
0x180026558  call    cs:__imp_GetLastError
0x18002655e  mov     esi, eax
0x180026560  mov     [rbp+57h+var_A8], r13
0x180026564  lea     rcx, [rbp+57h+var_A8]
0x180026568  call    cs:__imp_LuiCloseHandle
0x18002656e  mov     ecx, esi; dwErrCode
0x180026570  call    cs:__imp_SetLastError
0x180026576  mov     qword ptr [r15], 0FFFFFFFFFFFFFFFFh
0x18002657d  mov     r9, r14
0x180026580  lea     r8, ?ProcessLpaCallback@CESimSettingServer@@SAXPEAX0W4__MIDL_imports_0004@@_KPEAE@Z; CESimSettingServer::ProcessLpaCallback(void *,void *,__MIDL_imports_0004,unsigned __int64,uchar *)
0x180026587  mov     edx, r12d
0x18002658a  mov     rcx, r15
0x18002658d  call    cs:__imp_LuiOpenHandle
0x180026593  mov     esi, eax
0x180026595  xor     r12d, r12d
0x180026598  test    eax, eax
0x18002659a  jns     short loc_1800265CF
0x18002659c  mov     rcx, [rbp+5Fh]; this
0x1800265a0  mov     r9d, eax; char *
0x1800265a3  lea     r8, aOnecoreuapNetM_5; "onecoreuap\\net\\mobilebroadbandexperie"...
0x1800265aa  lea     edx, [r12+56h]; void *
0x1800265af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800265b4  nop
0x1800265b5  mov     rcx, rdi; hSCObject
0x1800265b8  call    cs:__imp_CloseServiceHandle
0x1800265be  nop
0x1800265bf  mov     rcx, rbx; hSCObject
0x1800265c2  call    cs:__imp_CloseServiceHandle
0x1800265c8  mov     eax, esi
0x1800265ca  jmp     loc_1800266E5
0x1800265cf  mov     [rbp+57h+var_B0], r12d
0x1800265d3  lea     rdx, [rbp+57h+var_B0]
0x1800265d7  mov     rcx, [r15]
0x1800265da  call    cs:__imp_LuiRegisterForLpaNotifications
0x1800265e0  mov     rcx, [rbp+5Fh]; this
0x1800265e4  test    eax, eax
0x1800265e6  js      loc_18002670E
0x1800265ec  lea     rax, [r14+80h]
0x1800265f3  mov     qword ptr [rsp+0E0h+var_C0], rax; unsigned int
0x1800265f8  mov     r9, r14
0x1800265fb  lea     r8, ?s_LpaServiceStateNotification@CESimSettingServer@@CAXKPEAX@Z; CESimSettingServer::s_LpaServiceStateNotification(ulong,void *)
0x180026602  mov     edx, 2
0x180026607  mov     rcx, rdi
0x18002660a  call    cs:__imp_SubscribeServiceChangeNotifications
0x180026610  mov     rcx, [rbp+5Fh]; this
0x180026614  test    eax, eax
0x180026616  jnz     loc_180026705
0x18002661c  xorps   xmm0, xmm0
0x18002661f  movdqu  xmmword ptr [rbp+57h+var_88], xmm0
0x180026624  mov     [rbp+57h+var_78], r12
0x180026628  movdqu  xmmword ptr [rbp+57h+var_A0], xmm0
0x18002662d  mov     [rbp+57h+var_90], r12
0x180026631  lea     rcx, [rbp+57h+var_88]
0x180026635  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18002663a  lea     rcx, [rbp+57h+var_A0]
0x18002663e  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180026643  mov     rdx, [rbp+57h+var_88+8]
0x180026647  mov     rcx, [rbp+57h+var_88]; unsigned __int16 *
0x18002664b  sub     rdx, rcx
0x18002664e  sar     rdx, 1; unsigned __int64
0x180026651  lea     r8, aLpasvcMonitori_1; "LpaSvc monitoring started."
0x180026658  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002665d  mov     rdx, [rbp+57h+var_A0+8]
0x180026661  mov     rcx, [rbp+57h+var_A0]; unsigned __int16 *
0x180026665  sub     rdx, rcx
0x180026668  sar     rdx, 1; unsigned __int64
0x18002666b  mov     rax, [rbp+57h+var_88]
0x18002666f  mov     [rsp+0E0h+var_B8], rax
0x180026674  mov     [rsp+0E0h+var_C0], 60h ; '`'
0x18002667c  lea     r9, aCesimsettingse; "CESimSettingServer::StartMonitoringLpaS"...
0x180026683  lea     r8, aSDS; "%S(%d):%s"
0x18002668a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002668f  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180026694  mov     ecx, [rax]
0x180026696  cmp     ecx, 4
0x180026699  jbe     short loc_1800266BC
0x18002669b  mov     rcx, [rbp+57h+var_A0]
0x18002669f  mov     [rbp+57h+var_A8], rcx
0x1800266a3  lea     rcx, [rbp+57h+var_A8]
0x1800266a7  mov     qword ptr [rsp+0E0h+var_C0], rcx
0x1800266ac  lea     rdx, dword_180075E6C
0x1800266b3  mov     rcx, rax
0x1800266b6  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800266bb  nop
0x1800266bc  lea     rcx, [rbp+57h+var_A0]
0x1800266c0  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x1800266c5  nop
0x1800266c6  lea     rcx, [rbp+57h+var_88]
0x1800266ca  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x1800266cf  nop
0x1800266d0  mov     rcx, rdi; hSCObject
0x1800266d3  call    cs:__imp_CloseServiceHandle
0x1800266d9  nop
0x1800266da  mov     rcx, rbx; hSCObject
0x1800266dd  call    cs:__imp_CloseServiceHandle
0x1800266e3  xor     eax, eax
0x1800266e5  mov     rcx, [rbp+57h+var_50]
0x1800266e9  xor     rcx, rsp; StackCookie
0x1800266ec  call    __security_check_cookie
0x1800266f1  add     rsp, 0A8h
0x1800266f8  pop     r15
0x1800266fa  pop     r14
0x1800266fc  pop     r13
0x1800266fe  pop     r12
0x180026700  pop     rdi
0x180026701  pop     rsi
0x180026702  pop     rbx
0x180026703  pop     rbp
0x180026704  retn
0x180026705  mov     r9d, eax; char *
0x180026708  call    ?_FailFast_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_FailFast_Win32(void *,uint,char const *,ulong)
0x18002670e  mov     r9d, eax; char *
0x180026711  lea     r8, aOnecoreuapNetM_5; "onecoreuap\\net\\mobilebroadbandexperie"...
0x180026718  mov     edx, 5Ah ; 'Z'; void *
0x18002671d  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
