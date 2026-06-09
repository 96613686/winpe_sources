# CDefragService::_Initialize(void)

- ea: `0x18001b6a8`
- end: `0x18001ba3f`
- name: `?_Initialize@CDefragService@@AEAAJXZ`
- size: `919`
- prototype: `__int64 __fastcall(CDefragService *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800271f8`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x18001a630`
- `0x18001b6a8`
- `0x18001ba48`
- `0x18001bb0c`
- `0x18001be28`
- `0x180038c3c`
- `0x180067b0a`
- `0x180067b30`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x18001b827`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x18001b827`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b9a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b9a3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001b79d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001b886`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001b79d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001b886`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x18001b96f`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x18001b96f`

## string_xrefs

- `0x18001b6dc`: `CDefragService::_Initialize`

## pseudocode

```c
__int64 __fastcall CDefragService::_Initialize(CDefragService *this)
{
  CDefragService *v1; // rcx
  CDefragService *v2; // rcx
  int inited; // ebx
  __int16 v4; // ax
  __int64 v6; // rdx
  HANDLE WaitableTimer; // rbx
  __int64 v8; // r8
  __int64 v9; // r9
  HANDLE v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r9
  LPVOID ppv; // [rsp+40h] [rbp-C0h] BYREF
  int v16; // [rsp+48h] [rbp-B8h] BYREF
  __int16 v17; // [rsp+4Ch] [rbp-B4h]
  __int16 v18; // [rsp+4Eh] [rbp-B2h]
  _DWORD v19[4]; // [rsp+80h] [rbp-80h] BYREF
  GUID v20; // [rsp+90h] [rbp-70h]

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v16, "CDefragService::_Initialize", 818, 1);
  ppv = 0;
  memset_0(v19, 0, 0x1A0u);
  inited = CDefragService::InitializeCOM(v1, 0);
  v16 = inited;
  v4 = 824;
  if ( inited < 0 )
    goto LABEL_2;
  v17 = 824;
  inited = CDefragService::_InitComSecurity(v2);
  v16 = inited;
  v4 = 826;
  if ( inited < 0 )
    goto LABEL_2;
  v17 = 826;
  inited = CoCreateInstance(&CLSID_GlobalOptions, 0, 1u, &IID_IGlobalOptions, &ppv);
  v16 = inited;
  v4 = 832;
  if ( inited < 0 )
    goto LABEL_2;
  v17 = 832;
  inited = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)ppv + 24LL))(ppv, 1, 1);
  v16 = inited;
  v4 = 833;
  if ( inited < 0 )
    goto LABEL_2;
  v17 = 833;
  inited = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)ppv + 24LL))(ppv, 5, 1);
  v16 = inited;
  v4 = 834;
  if ( inited < 0 )
    goto LABEL_2;
  v17 = 834;
  WaitableTimer = CreateWaitableTimerExW(0, 0, 1u, 0x1F0003u);
  v10 = hTimer;
  if ( (char *)hTimer - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hTimer);
  hTimer = WaitableTimer;
  if ( !WaitableTimer )
  {
    inited = GetLastFailureAsHRESULT(v10, v6, v8, v9);
    v16 = inited;
    v4 = 838;
    goto LABEL_2;
  }
  v16 = 0;
  v17 = 838;
  inited = CoCreateInstance(&CLSID_ContextSwitcher, 0, 1u, &IID_IContextCallback, &::ppv);
  v16 = inited;
  v4 = 844;
  if ( inited < 0 )
    goto LABEL_2;
  v17 = 844;
  CSxSafeComPtr<IContextCallback>::Initialize(&qword_180089B00);
  if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_9dfa55146e94391ee67982bf00c934b1_Traceguids);
  }
  inited = (*(__int64 (__fastcall **)(LPVOID, __int64 (__fastcall *)(struct tagComCallData *), _QWORD, GUID *, int, _QWORD))(*(_QWORD *)::ppv + 24LL))(
             ::ppv,
             CDefragService::EnterCallback,
             0,
             &IID_IContextCallback,
             5,
             0);
  v16 = inited;
  v4 = 850;
  if ( inited < 0 )
    goto LABEL_2;
  v17 = 850;
  if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_9dfa55146e94391ee67982bf00c934b1_Traceguids);
  }
  memset_0(v19, 0, 0x1A0u);
  v19[0] = 416;
  v19[2] = 0;
  v20 = GUID_DEVINTERFACE_VOLUME;
  if ( (unsigned int)CM_Register_Notification(v19, 0, &CDefragService::_NotifyDeviceCallback, &qword_180089AE8) )
  {
    inited = GetLastFailureAsHRESULT(v12, v11, v13, v14);
    v16 = inited;
    v4 = 869;
LABEL_2:
    v18 = v4;
    goto LABEL_3;
  }
  v16 = 0;
  v17 = 869;
  if ( !qword_180089AE8 )
  {
    inited = GetLastFailureAsHRESULT(v12, v11, v13, v14);
    v16 = inited;
    v4 = 870;
    goto LABEL_2;
  }
  v16 = 0;
  v17 = 870;
  inited = 0;
LABEL_3:
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v16);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18001b6a8  push    rbp
0x18001b6aa  push    rbx
0x18001b6ab  push    rsi
0x18001b6ac  push    r14
0x18001b6ae  lea     rbp, [rsp-138h]
0x18001b6b6  sub     rsp, 238h
0x18001b6bd  mov     rax, cs:__security_cookie
0x18001b6c4  xor     rax, rsp
0x18001b6c7  mov     [rbp+150h+var_30], rax
0x18001b6ce  mov     esi, 1
0x18001b6d3  mov     r9d, esi; unsigned __int16
0x18001b6d6  mov     r8d, 332h; unsigned __int16
0x18001b6dc  lea     rdx, aCdefragservice_12; "CDefragService::_Initialize"
0x18001b6e3  lea     rcx, [rsp+250h+var_208]; this
0x18001b6e8  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001b6ed  nop
0x18001b6ee  mov     [rsp+250h+var_210], 0
0x18001b6f7  xor     edx, edx; Val
0x18001b6f9  mov     r8d, 1A0h; Size
0x18001b6ff  lea     rcx, [rbp+150h+var_1D0]; void *
0x18001b703  call    memset_0
0x18001b708  xor     edx, edx; int
0x18001b70a  call    ?InitializeCOM@CDefragService@@QEAAJH@Z; CDefragService::InitializeCOM(int)
0x18001b70f  mov     ebx, eax
0x18001b711  mov     [rsp+250h+var_208], eax
0x18001b715  test    eax, eax
0x18001b717  mov     eax, 338h
0x18001b71c  jns     short loc_18001B762
0x18001b71e  mov     [rsp+250h+var_202], ax
0x18001b723  mov     rcx, [rsp+250h+var_210]
0x18001b728  test    rcx, rcx
0x18001b72b  jz      short loc_18001B73A
0x18001b72d  mov     rdx, [rcx]
0x18001b730  mov     rax, [rdx+10h]
0x18001b734  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b739  nop
0x18001b73a  lea     rcx, [rsp+250h+var_208]; this
0x18001b73f  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001b744  mov     eax, ebx
0x18001b746  mov     rcx, [rbp+150h+var_30]
0x18001b74d  xor     rcx, rsp; StackCookie
0x18001b750  call    __security_check_cookie
0x18001b755  add     rsp, 238h
0x18001b75c  pop     r14
0x18001b75e  pop     rsi
0x18001b75f  pop     rbx
0x18001b760  pop     rbp
0x18001b761  retn
0x18001b762  mov     [rsp+250h+var_204], ax
0x18001b767  call    ?_InitComSecurity@CDefragService@@AEAAJXZ; CDefragService::_InitComSecurity(void)
0x18001b76c  mov     ebx, eax
0x18001b76e  mov     [rsp+250h+var_208], eax
0x18001b772  test    eax, eax
0x18001b774  mov     eax, 33Ah
0x18001b779  js      short loc_18001B71E
0x18001b77b  mov     [rsp+250h+var_204], ax
0x18001b780  lea     rax, [rsp+250h+var_210]
0x18001b785  mov     [rsp+250h+ppv], rax; ppv
0x18001b78a  lea     r9, IID_IGlobalOptions; riid
0x18001b791  mov     r8d, esi; dwClsContext
0x18001b794  xor     edx, edx; pUnkOuter
0x18001b796  lea     rcx, CLSID_GlobalOptions; rclsid
0x18001b79d  call    cs:__imp_CoCreateInstance
0x18001b7a3  mov     ebx, eax
0x18001b7a5  mov     [rsp+250h+var_208], eax
0x18001b7a9  test    eax, eax
0x18001b7ab  mov     eax, 340h
0x18001b7b0  js      loc_18001B71E
0x18001b7b6  mov     [rsp+250h+var_204], ax
0x18001b7bb  mov     rcx, [rsp+250h+var_210]
0x18001b7c0  mov     rax, [rcx]
0x18001b7c3  mov     r8, rsi
0x18001b7c6  mov     edx, esi
0x18001b7c8  mov     rax, [rax+18h]
0x18001b7cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b7d1  mov     ebx, eax
0x18001b7d3  mov     [rsp+250h+var_208], eax
0x18001b7d7  test    eax, eax
0x18001b7d9  mov     eax, 341h
0x18001b7de  js      loc_18001B71E
0x18001b7e4  mov     [rsp+250h+var_204], ax
0x18001b7e9  mov     rcx, [rsp+250h+var_210]
0x18001b7ee  mov     rax, [rcx]
0x18001b7f1  mov     r8, rsi
0x18001b7f4  mov     edx, 5
0x18001b7f9  mov     rax, [rax+18h]
0x18001b7fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b802  mov     ebx, eax
0x18001b804  mov     [rsp+250h+var_208], eax
0x18001b808  test    eax, eax
0x18001b80a  mov     eax, 342h
0x18001b80f  js      loc_18001B71E
0x18001b815  mov     [rsp+250h+var_204], ax
0x18001b81a  mov     r9d, 1F0003h; dwDesiredAccess
0x18001b820  mov     r8d, esi; dwFlags
0x18001b823  xor     edx, edx; lpTimerName
0x18001b825  xor     ecx, ecx; lpTimerAttributes
0x18001b827  call    cs:__imp_CreateWaitableTimerExW
0x18001b82d  mov     rbx, rax
0x18001b830  mov     rcx, cs:hTimer; hObject
0x18001b837  lea     rax, [rcx-1]
0x18001b83b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001b83f  jbe     loc_18001B9A3
0x18001b845  mov     cs:hTimer, rbx
0x18001b84c  test    rbx, rbx
0x18001b84f  jz      loc_18001B98E
0x18001b855  mov     [rsp+250h+var_208], 0
0x18001b85d  mov     eax, 346h
0x18001b862  mov     [rsp+250h+var_204], ax
0x18001b867  lea     rax, ppv
0x18001b86e  mov     [rsp+250h+ppv], rax; ppv
0x18001b873  lea     r9, IID_IContextCallback; riid
0x18001b87a  mov     r8d, esi; dwClsContext
0x18001b87d  xor     edx, edx; pUnkOuter
0x18001b87f  lea     rcx, CLSID_ContextSwitcher; rclsid
0x18001b886  call    cs:__imp_CoCreateInstance
0x18001b88c  mov     ebx, eax
0x18001b88e  mov     [rsp+250h+var_208], eax
0x18001b892  test    eax, eax
0x18001b894  mov     eax, 34Ch
0x18001b899  js      loc_18001B71E
0x18001b89f  mov     [rsp+250h+var_204], ax
0x18001b8a4  mov     rdx, cs:ppv
0x18001b8ab  lea     rcx, qword_180089B00; ppv
0x18001b8b2  call    ?Initialize@?$CSxSafeComPtr@UIContextCallback@@@@QEAAJPEAUIContextCallback@@@Z; CSxSafeComPtr<IContextCallback>::Initialize(IContextCallback *)
0x18001b8b7  lea     r14, WPP_GLOBAL_Control
0x18001b8be  mov     esi, 8000000h
0x18001b8c3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b8ca  cmp     rcx, r14
0x18001b8cd  jnz     loc_18001B9AE
0x18001b8d3  mov     rcx, cs:ppv
0x18001b8da  mov     rax, [rcx]
0x18001b8dd  mov     [rsp+250h+var_228], 0
0x18001b8e6  mov     dword ptr [rsp+250h+ppv], 5
0x18001b8ee  lea     r9, IID_IContextCallback
0x18001b8f5  xor     r8d, r8d
0x18001b8f8  lea     rdx, ?EnterCallback@CDefragService@@CAJPEAUtagComCallData@@@Z; CDefragService::EnterCallback(tagComCallData *)
0x18001b8ff  mov     rax, [rax+18h]
0x18001b903  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b908  mov     ebx, eax
0x18001b90a  mov     [rsp+250h+var_208], eax
0x18001b90e  test    eax, eax
0x18001b910  mov     eax, 352h
0x18001b915  js      loc_18001B71E
0x18001b91b  mov     [rsp+250h+var_204], ax
0x18001b920  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b927  cmp     rcx, r14
0x18001b92a  jnz     loc_18001B9D1
0x18001b930  xor     edx, edx; Val
0x18001b932  mov     r8d, 1A0h; Size
0x18001b938  lea     rcx, [rbp+150h+var_1D0]; void *
0x18001b93c  call    memset_0
0x18001b941  mov     [rbp+150h+var_1D0], 1A0h
0x18001b948  mov     [rbp+150h+var_1C8], 0
0x18001b94f  movups  xmm0, xmmword ptr cs:GUID_DEVINTERFACE_VOLUME.Data1
0x18001b956  movdqu  [rbp+150h+var_1C0], xmm0
0x18001b95b  lea     r9, qword_180089AE8
0x18001b962  lea     r8, ?_NotifyDeviceCallback@CDefragService@@CAKPEAUHCMNOTIFICATION__@@PEAXW4_CM_NOTIFY_ACTION@@PEAU_CM_NOTIFY_EVENT_DATA@@K@Z; CDefragService::_NotifyDeviceCallback(HCMNOTIFICATION__ *,void *,_CM_NOTIFY_ACTION,_CM_NOTIFY_EVENT_DATA *,ulong)
0x18001b969  xor     edx, edx
0x18001b96b  lea     rcx, [rbp+150h+var_1D0]
0x18001b96f  call    cs:__imp_CM_Register_Notification
0x18001b975  test    eax, eax
0x18001b977  jz      short loc_18001B9F4
0x18001b979  call    GetLastFailureAsHRESULT
0x18001b97e  mov     ebx, eax
0x18001b980  mov     [rsp+250h+var_208], eax
0x18001b984  mov     eax, 365h
0x18001b989  jmp     loc_18001B71E
0x18001b98e  call    GetLastFailureAsHRESULT
0x18001b993  mov     ebx, eax
0x18001b995  mov     [rsp+250h+var_208], eax
0x18001b999  mov     eax, 346h
0x18001b99e  jmp     loc_18001B71E
0x18001b9a3  call    cs:__imp_CloseHandle
0x18001b9a9  jmp     loc_18001B845
0x18001b9ae  test    [rcx+1Ch], esi
0x18001b9b1  jz      loc_18001B8D3
0x18001b9b7  mov     edx, 13h
0x18001b9bc  lea     r8, WPP_9dfa55146e94391ee67982bf00c934b1_Traceguids
0x18001b9c3  mov     rcx, [rcx+10h]
0x18001b9c7  call    WPP_SF_
0x18001b9cc  jmp     loc_18001B8D3
0x18001b9d1  test    [rcx+1Ch], esi
0x18001b9d4  jz      loc_18001B930
0x18001b9da  mov     edx, 14h
0x18001b9df  lea     r8, WPP_9dfa55146e94391ee67982bf00c934b1_Traceguids
0x18001b9e6  mov     rcx, [rcx+10h]
0x18001b9ea  call    WPP_SF_
0x18001b9ef  jmp     loc_18001B930
0x18001b9f4  mov     [rsp+250h+var_208], 0
0x18001b9fc  mov     eax, 365h
0x18001ba01  mov     [rsp+250h+var_204], ax
0x18001ba06  cmp     cs:qword_180089AE8, 0
0x18001ba0e  jnz     short loc_18001BA25
0x18001ba10  call    GetLastFailureAsHRESULT
0x18001ba15  mov     ebx, eax
0x18001ba17  mov     [rsp+250h+var_208], eax
0x18001ba1b  mov     eax, 366h
0x18001ba20  jmp     loc_18001B71E
0x18001ba25  mov     [rsp+250h+var_208], 0
0x18001ba2d  mov     eax, 366h
0x18001ba32  mov     [rsp+250h+var_204], ax
0x18001ba37  xor     ebx, ebx
0x18001ba39  jmp     loc_18001B723
```
