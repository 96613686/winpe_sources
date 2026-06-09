# Microsoft::HostGuardian::Client::HgService::HgService(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,_SVCHOST_GLOBAL_DATA *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>)

- ea: `0x180009300`
- end: `0x180009550`
- name: `??0HgService@Client@HostGuardian@Microsoft@@QEAA@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAU_SVCHOST_GLOBAL_DATA@@0@Z`
- size: `592`
- prototype: `char *__fastcall(char *lpContext, _QWORD *lpServiceName, __int64, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x180007920`

## callees

- `0x180001770`
- `0x180001794`
- `0x180001bb4`
- `0x180004274`
- `0x1800077a0`
- `0x180008760`
- `0x180008780`
- `0x180009300`
- `0x18000977c`
- `0x1800097f8`
- `0x180009fc8`
- `0x18000a7bc`
- `0x18000ba8c`
- `0x18000c574`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1800093e4`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1800093e4`

## string_xrefs

- `0x180009514`: `servercommon\base\securehostingservice\common\service\lib\hgservice.cpp`
- `0x18000952c`: `servercommon\base\securehostingservice\common\service\lib\hgservice.cpp`
- `0x18000953e`: `servercommon\base\securehostingservice\common\service\lib\hgservice.cpp`

## pseudocode

```c
char *__fastcall Microsoft::HostGuardian::Client::HgService::HgService(
        char *lpContext,
        _QWORD *lpServiceName,
        __int64 a3,
        __int64 a4)
{
  char v7; // al
  const WCHAR *v8; // rcx
  SERVICE_STATUS_HANDLE v9; // rax
  const char *v10; // r9
  __int64 v11; // rax
  const char *v12; // r9
  Microsoft::HostGuardian::Client::HgServiceController *v13; // rsi
  __int64 v14; // rcx
  __int64 v15; // r8
  int v17; // [rsp+20h] [rbp-49h]
  int v18; // [rsp+30h] [rbp-39h] BYREF
  _QWORD v19[2]; // [rsp+38h] [rbp-31h] BYREF
  char v20; // [rsp+48h] [rbp-21h]
  char *v21; // [rsp+50h] [rbp-19h]
  void *v22; // [rsp+58h] [rbp-11h]
  _QWORD *v23; // [rsp+60h] [rbp-9h]
  __int64 v24; // [rsp+68h] [rbp-1h]
  _BYTE v25[16]; // [rsp+70h] [rbp+7h] BYREF
  const wchar_t *v26; // [rsp+80h] [rbp+17h]
  __int64 v27; // [rsp+88h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v21 = lpContext;
  v23 = lpServiceName;
  v24 = a4;
  *(_OWORD *)lpContext = 0;
  *((_QWORD *)lpContext + 2) = 0;
  *((_QWORD *)lpContext + 3) = 7;
  *(_WORD *)lpContext = 0;
  *((_QWORD *)lpContext + 9) = a3;
  *((_QWORD *)lpContext + 10) = 0;
  *((_QWORD *)lpContext + 11) = 0;
  *((_QWORD *)lpContext + 12) = 2;
  *(_OWORD *)(lpContext + 120) = 0;
  *(_OWORD *)(lpContext + 136) = 0;
  *(_OWORD *)(lpContext + 152) = 0;
  *((_QWORD *)lpContext + 13) = 0;
  *((_QWORD *)lpContext + 14) = 0;
  *((_DWORD *)lpContext + 42) = -1;
  *((_DWORD *)lpContext + 43) = 0;
  *((_QWORD *)lpContext + 22) = 0;
  *((_QWORD *)lpContext + 23) = 0;
  *((_QWORD *)lpContext + 24) = 0;
  g_service = (struct Microsoft::HostGuardian::Client::HgService *)lpContext;
  if ( !lpServiceName[2] || (v7 = 0, !a3) )
    v7 = 1;
  if ( v7 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x30,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgservice.cpp",
      (const char *)0x80070057LL,
      v17);
  if ( lpServiceName[3] <= 7u )
    v8 = (const WCHAR *)lpServiceName;
  else
    v8 = (const WCHAR *)*lpServiceName;
  v9 = RegisterServiceCtrlHandlerExW(v8, Microsoft::HostGuardian::Client::HgService::ControlHandlerCallback, lpContext);
  *((_QWORD *)lpContext + 4) = v9;
  if ( !v9 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x34,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgservice.cpp",
      v10);
  std::wstring::operator=(lpContext, lpServiceName);
  *((_QWORD *)lpContext + 5) = 32;
  *((_QWORD *)lpContext + 6) = 0;
  *((_QWORD *)lpContext + 7) = 0;
  *((_DWORD *)lpContext + 16) = 6000;
  v18 = -2147467259;
  v19[0] = &v18;
  v19[1] = lpContext;
  v20 = 1;
  v22 = operator new(0x110u);
  v11 = Microsoft::HostGuardian::Client::HgServiceController::HgServiceController((__int64)v22, a4);
  v13 = (Microsoft::HostGuardian::Client::HgServiceController *)*((_QWORD *)lpContext + 24);
  *((_QWORD *)lpContext + 24) = v11;
  if ( v13 )
  {
    Microsoft::HostGuardian::Client::HgServiceController::~HgServiceController(v13);
    operator delete(v13);
  }
  if ( !*((_QWORD *)lpContext + 24) )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x53,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgservice.cpp",
      v12);
  Microsoft::HostGuardian::Client::HgService::SetStatus((Microsoft::HostGuardian::Client::HgService *)lpContext, 2u);
  if ( (Microsoft_Windows_HostGuardianClient_ServiceEnableBits & 2) != 0 )
  {
    v26 = L"Sent the start pending notification to SCM.";
    v27 = 88;
    McGenEventWrite_EventWriteTransfer(v14, ServiceDebugInformational, v15, 2, v25);
  }
  v18 = 0;
  v20 = 0;
  lambda_1f74f109121ab9be91b83fc81df6e03f_::operator()(v19);
  std::wstring::~wstring(lpServiceName);
  std::wstring::~wstring(a4);
  return lpContext;
}

```

## disassembly

```asm
0x180009300  mov     [rsp-8+arg_10], rbx
0x180009305  push    rbp
0x180009306  push    rsi
0x180009307  push    rdi
0x180009308  push    r14
0x18000930a  push    r15
0x18000930c  lea     rbp, [rsp-37h]
0x180009311  sub     rsp, 0A0h
0x180009318  mov     rax, cs:__security_cookie
0x18000931f  xor     rax, rsp
0x180009322  mov     [rbp+57h+var_30], rax
0x180009326  mov     r14, r9
0x180009329  mov     rdi, rdx
0x18000932c  mov     rbx, rcx
0x18000932f  mov     [rbp+57h+var_70], rcx
0x180009333  mov     [rbp+57h+var_60], rdx
0x180009337  mov     [rbp+57h+var_58], r9
0x18000933b  xor     r15d, r15d
0x18000933e  xorps   xmm0, xmm0
0x180009341  movups  xmmword ptr [rcx], xmm0
0x180009344  mov     [rcx+10h], r15
0x180009348  mov     qword ptr [rcx+18h], 7
0x180009350  mov     [rcx], r15w
0x180009354  mov     [rcx+48h], r8
0x180009358  mov     [rcx+50h], r15
0x18000935c  mov     [rcx+58h], r15
0x180009360  mov     qword ptr [rcx+60h], 2
0x180009368  movups  xmmword ptr [rcx+78h], xmm0
0x18000936c  movups  xmmword ptr [rcx+88h], xmm0
0x180009373  movups  xmmword ptr [rcx+98h], xmm0
0x18000937a  mov     [rcx+68h], r15
0x18000937e  mov     [rcx+70h], r15
0x180009382  mov     dword ptr [rcx+0A8h], 0FFFFFFFFh
0x18000938c  mov     [rcx+0ACh], r15d
0x180009393  mov     [rcx+0B0h], r15
0x18000939a  mov     [rcx+0B8h], r15
0x1800093a1  mov     [rcx+0C0h], r15
0x1800093a8  mov     cs:?g_service@@3PEAVHgService@Client@HostGuardian@Microsoft@@EA, rcx; Microsoft::HostGuardian::Client::HgService * g_service
0x1800093af  cmp     [rdx+10h], r15
0x1800093b3  jz      short loc_1800093BD
0x1800093b5  test    r8, r8
0x1800093b8  mov     al, r15b
0x1800093bb  jnz     short loc_1800093BF
0x1800093bd  mov     al, 1
0x1800093bf  mov     rcx, [rbp+5Fh]; this
0x1800093c3  test    al, al
0x1800093c5  jnz     loc_180009526
0x1800093cb  cmp     qword ptr [rdx+18h], 7
0x1800093d0  jbe     short loc_1800093D7
0x1800093d2  mov     rcx, [rdx]
0x1800093d5  jmp     short loc_1800093DA
0x1800093d7  mov     rcx, rdi; lpServiceName
0x1800093da  mov     r8, rbx; lpContext
0x1800093dd  lea     rdx, ?ControlHandlerCallback@HgService@Client@HostGuardian@Microsoft@@KAKKKPEAX0@Z; lpHandlerProc
0x1800093e4  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x1800093ea  mov     [rbx+20h], rax
0x1800093ee  mov     rcx, [rbp+5Fh]; this
0x1800093f2  test    rax, rax
0x1800093f5  jz      loc_18000953E
0x1800093fb  mov     rdx, rdi
0x1800093fe  mov     rcx, rbx
0x180009401  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180009406  mov     qword ptr [rbx+28h], 20h ; ' '
0x18000940e  mov     [rbx+30h], r15
0x180009412  mov     [rbx+38h], r15
0x180009416  mov     dword ptr [rbx+40h], 1770h
0x18000941d  mov     [rbp+57h+var_90], 80004005h
0x180009424  lea     rax, [rbp+57h+var_90]
0x180009428  mov     [rbp+57h+var_88], rax
0x18000942c  mov     [rbp+57h+var_80], rbx
0x180009430  mov     [rbp+57h+var_78], 1
0x180009434  mov     ecx, 110h; Size
0x180009439  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000943e  mov     [rbp+57h+var_68], rax
0x180009442  mov     rdx, r14
0x180009445  mov     rcx, rax
0x180009448  call    ??0HgServiceController@Client@HostGuardian@Microsoft@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::HostGuardian::Client::HgServiceController::HgServiceController(std::wstring const &)
0x18000944d  nop
0x18000944e  mov     rsi, [rbx+0C0h]
0x180009455  mov     [rbx+0C0h], rax
0x18000945c  test    rsi, rsi
0x18000945f  jz      short loc_180009476
0x180009461  mov     rcx, rsi; this
0x180009464  call    ??1HgServiceController@Client@HostGuardian@Microsoft@@QEAA@XZ; Microsoft::HostGuardian::Client::HgServiceController::~HgServiceController(void)
0x180009469  mov     edx, 110h
0x18000946e  mov     rcx, rsi; Block
0x180009471  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180009476  mov     rcx, [rbp+5Fh]; this
0x18000947a  cmp     [rbx+0C0h], r15
0x180009481  jz      loc_180009514
0x180009487  mov     edx, 2; unsigned int
0x18000948c  mov     rcx, rbx; this
0x18000948f  call    ?SetStatus@HgService@Client@HostGuardian@Microsoft@@IEAAXK@Z; Microsoft::HostGuardian::Client::HgService::SetStatus(ulong)
0x180009494  test    byte ptr cs:Microsoft_Windows_HostGuardianClient_ServiceEnableBits, 2
0x18000949b  jz      short loc_1800094CB
0x18000949d  lea     rax, aSentTheStartPe; "Sent the start pending notification to "...
0x1800094a4  mov     [rbp+57h+var_40], rax
0x1800094a8  mov     [rbp+57h+var_38], 58h ; 'X'
0x1800094b0  lea     rax, [rbp+57h+var_50]
0x1800094b4  mov     qword ptr [rsp+0C0h+var_A0], rax
0x1800094b9  mov     r9d, 2
0x1800094bf  lea     rdx, ServiceDebugInformational
0x1800094c6  call    McGenEventWrite_EventWriteTransfer
0x1800094cb  mov     [rbp+57h+var_90], r15d
0x1800094cf  mov     [rbp+57h+var_78], r15b
0x1800094d3  lea     rcx, [rbp+57h+var_88]
0x1800094d7  call    _lambda_1f74f109121ab9be91b83fc81df6e03f___operator__
0x1800094dc  nop
0x1800094dd  mov     rcx, rdi
0x1800094e0  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800094e5  nop
0x1800094e6  mov     rcx, r14
0x1800094e9  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800094ee  mov     rax, rbx
0x1800094f1  mov     rcx, [rbp+57h+var_30]
0x1800094f5  xor     rcx, rsp; StackCookie
0x1800094f8  call    __security_check_cookie
0x1800094fd  mov     rbx, [rsp+0C0h+arg_10]
0x180009505  add     rsp, 0A0h
0x18000950c  pop     r15
0x18000950e  pop     r14
0x180009510  pop     rdi
0x180009511  pop     rsi
0x180009512  pop     rbp
0x180009513  retn
0x180009514  lea     r8, aServercommonBa_0; "servercommon\\base\\securehostingservic"...
0x18000951b  mov     edx, 53h ; 'S'; void *
0x180009520  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180009526  mov     r9d, 80070057h; char *
0x18000952c  lea     r8, aServercommonBa_0; "servercommon\\base\\securehostingservic"...
0x180009533  mov     edx, 30h ; '0'; void *
0x180009538  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000953e  lea     r8, aServercommonBa_0; "servercommon\\base\\securehostingservic"...
0x180009545  mov     edx, 34h ; '4'; void *
0x18000954a  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
