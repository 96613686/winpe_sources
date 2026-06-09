# CDefragService::ServiceMain(void)

- ea: `0x1800271f8`
- end: `0x1800273a5`
- name: `?ServiceMain@CDefragService@@QEAAJXZ`
- size: `429`
- prototype: `__int64 __fastcall(CDefragService *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, service_task`

## callers

- `0x18004a920`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x18001457c`
- `0x18001a630`
- `0x18001b6a8`
- `0x1800271f8`
- `0x1800275f8`
- `0x1800276d8`
- `0x180027760`
- `0x180038c3c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180027294`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180027294`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1800272bc`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1800272bc`

## string_xrefs

- `0x180027211`: `CDefragService::ServiceMain`
- `0x18002728d`: `defragsvc.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDefragService::ServiceMain(CDefragService *this)
{
  __int64 v1; // rdx
  CDefragService *v2; // rcx
  __int64 v3; // r8
  __int64 v4; // r9
  CDefragService *v5; // rcx
  __int16 v6; // ax
  CDefragService *v7; // rcx
  CDefragService *v8; // rcx
  unsigned int v9; // ebx
  signed int LastFailureAsHRESULT; // [rsp+20h] [rbp-40h] BYREF
  __int16 v12; // [rsp+24h] [rbp-3Ch]
  __int16 v13; // [rsp+26h] [rbp-3Ah]

  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&LastFailureAsHRESULT,
    "CDefragService::ServiceMain",
    345,
    1);
  qword_180089A40 = 0;
  WPP_MAIN_CB = 0;
  qword_180089A48 = 1;
  WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_ControlGuid;
  WPP_GLOBAL_Control = (CSxGlobalTracer *)&WPP_MAIN_CB;
  WppInitUm();
  if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_9dfa55146e94391ee67982bf00c934b1_Traceguids);
  }
  g_hInstance = GetModuleHandleW(L"defragsvc.dll");
  ServiceStatus.dwCurrentState = 2;
  hServiceStatus = RegisterServiceCtrlHandlerExW(L"DEFRAGSVC", HandlerEx, 0);
  if ( !hServiceStatus )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v2, v1, v3, v4);
    v6 = 358;
LABEL_6:
    v13 = v6;
    goto LABEL_12;
  }
  LastFailureAsHRESULT = 0;
  v12 = 358;
  LastFailureAsHRESULT = CDefragService::_SetServiceStatus(v2, 2u);
  v6 = 361;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_6;
  v12 = 361;
  LastFailureAsHRESULT = CDefragService::_Initialize((CDefragService *)&_Module);
  v6 = 364;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_6;
  v12 = 364;
  ServiceStatus.dwControlsAccepted = 69;
  LastFailureAsHRESULT = CDefragService::_SetServiceStatus(v5, 4u);
  v6 = 372;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_6;
  v12 = 372;
  LastFailureAsHRESULT = CDefragService::Run(v5);
  v6 = 376;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_6;
  v12 = 376;
LABEL_12:
  CDefragService::_SetServiceStatus(v5, 3u);
  CDefragService::Stop(v7);
  if ( LastFailureAsHRESULT < 0 )
  {
    ServiceStatus.dwWin32ExitCode = 1066;
    ServiceStatus.dwServiceSpecificExitCode = LastFailureAsHRESULT;
  }
  CDefragService::_SetServiceStatus(v8, 1u);
  v9 = LastFailureAsHRESULT;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT);
  return v9;
}

```

## disassembly

```asm
0x1800271f8  mov     [rsp-8+arg_0], rbx
0x1800271fd  push    rbp
0x1800271fe  mov     rbp, rsp
0x180027201  sub     rsp, 60h
0x180027205  mov     r9d, 1; unsigned __int16
0x18002720b  mov     r8d, 159h; unsigned __int16
0x180027211  lea     rdx, aCdefragservice_9; "CDefragService::ServiceMain"
0x180027218  lea     rcx, [rbp+var_40]; this
0x18002721c  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180027221  nop
0x180027222  xor     ebx, ebx
0x180027224  mov     cs:qword_180089A40, rbx
0x18002722b  mov     cs:WPP_MAIN_CB, rbx
0x180027232  mov     cs:qword_180089A48, 1
0x18002723d  lea     rax, WPP_ThisDir_CTLGUID_ControlGuid
0x180027244  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x18002724b  lea     rax, WPP_MAIN_CB
0x180027252  mov     cs:WPP_GLOBAL_Control, rax
0x180027259  call    WppInitUm
0x18002725e  lea     rax, WPP_GLOBAL_Control
0x180027265  mov     rcx, cs:WPP_GLOBAL_Control
0x18002726c  cmp     rcx, rax
0x18002726f  jz      short loc_18002728D
0x180027271  test    dword ptr [rcx+1Ch], 8000000h
0x180027278  jz      short loc_18002728D
0x18002727a  lea     edx, [rbx+0Dh]
0x18002727d  lea     r8, WPP_9dfa55146e94391ee67982bf00c934b1_Traceguids
0x180027284  mov     rcx, [rcx+10h]
0x180027288  call    WPP_SF_
0x18002728d  lea     rcx, ModuleName; "defragsvc.dll"
0x180027294  call    cs:__imp_GetModuleHandleW
0x18002729a  mov     cs:?g_hInstance@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hInstance
0x1800272a1  mov     cs:ServiceStatus.dwCurrentState, 2
0x1800272ab  xor     r8d, r8d; lpContext
0x1800272ae  lea     rdx, HandlerEx; lpHandlerProc
0x1800272b5  lea     rcx, ?s_wszSvcName@CDefragService@@0QBGB; "DEFRAGSVC"
0x1800272bc  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x1800272c2  mov     cs:hServiceStatus, rax
0x1800272c9  test    rax, rax
0x1800272cc  jnz     short loc_1800272E1
0x1800272ce  call    GetLastFailureAsHRESULT
0x1800272d3  mov     [rbp+var_40], eax
0x1800272d6  mov     eax, 166h
0x1800272db  mov     [rbp+var_3A], ax
0x1800272df  jmp     short loc_18002735C
0x1800272e1  mov     [rbp+var_40], ebx
0x1800272e4  mov     eax, 166h
0x1800272e9  mov     [rbp+var_3C], ax
0x1800272ed  mov     edx, 2; unsigned int
0x1800272f2  call    ?_SetServiceStatus@CDefragService@@AEAAJK@Z; CDefragService::_SetServiceStatus(ulong)
0x1800272f7  mov     [rbp+var_40], eax
0x1800272fa  test    eax, eax
0x1800272fc  mov     eax, 169h
0x180027301  js      short loc_1800272DB
0x180027303  mov     [rbp+var_3C], ax
0x180027307  lea     rcx, ?_Module@@3VCDefragService@@A; this
0x18002730e  call    ?_Initialize@CDefragService@@AEAAJXZ; CDefragService::_Initialize(void)
0x180027313  mov     [rbp+var_40], eax
0x180027316  test    eax, eax
0x180027318  mov     eax, 16Ch
0x18002731d  js      short loc_1800272DB
0x18002731f  mov     [rbp+var_3C], ax
0x180027323  mov     cs:ServiceStatus.dwControlsAccepted, 45h ; 'E'
0x18002732d  mov     edx, 4; unsigned int
0x180027332  call    ?_SetServiceStatus@CDefragService@@AEAAJK@Z; CDefragService::_SetServiceStatus(ulong)
0x180027337  mov     [rbp+var_40], eax
0x18002733a  test    eax, eax
0x18002733c  mov     eax, 174h
0x180027341  js      short loc_1800272DB
0x180027343  mov     [rbp+var_3C], ax
0x180027347  call    ?Run@CDefragService@@QEAAJXZ; CDefragService::Run(void)
0x18002734c  mov     [rbp+var_40], eax
0x18002734f  test    eax, eax
0x180027351  mov     eax, 178h
0x180027356  js      short loc_1800272DB
0x180027358  mov     [rbp+var_3C], ax
0x18002735c  mov     edx, 3; unsigned int
0x180027361  call    ?_SetServiceStatus@CDefragService@@AEAAJK@Z; CDefragService::_SetServiceStatus(ulong)
0x180027366  call    ?Stop@CDefragService@@QEAAJXZ; CDefragService::Stop(void)
0x18002736b  mov     eax, [rbp+var_40]
0x18002736e  test    eax, eax
0x180027370  jns     short loc_180027382
0x180027372  mov     cs:ServiceStatus.dwWin32ExitCode, 42Ah
0x18002737c  mov     cs:ServiceStatus.dwServiceSpecificExitCode, eax
0x180027382  mov     edx, 1; unsigned int
0x180027387  call    ?_SetServiceStatus@CDefragService@@AEAAJK@Z; CDefragService::_SetServiceStatus(ulong)
0x18002738c  mov     ebx, [rbp+var_40]
0x18002738f  lea     rcx, [rbp+var_40]; this
0x180027393  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180027398  mov     eax, ebx
0x18002739a  mov     rbx, [rsp+60h+arg_0]
0x18002739f  add     rsp, 60h
0x1800273a3  pop     rbp
0x1800273a4  retn
```
