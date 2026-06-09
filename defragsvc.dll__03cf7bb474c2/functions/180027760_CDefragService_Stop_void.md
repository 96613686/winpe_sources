# CDefragService::Stop(void)

- ea: `0x180027760`
- end: `0x180027977`
- name: `?Stop@CDefragService@@QEAAJXZ`
- size: `535`
- prototype: `__int64 __fastcall(CDefragService *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800271f8`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x180027760`
- `0x180027980`
- `0x18002ca7c`
- `0x180038c3c`
- `0x180038f58`
- `0x180046494`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800277d6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800277d6`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x1800277b3`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x1800277b3`

## string_xrefs

- `0x180027786`: `CDefragService::Stop`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CDefragService::Stop(CDefragService *this)
{
  CDefragService *v1; // rcx
  LPVOID v2; // rcx
  CDefragService *v3; // rcx
  unsigned int v4; // eax
  unsigned int v5; // ebx
  int v7; // [rsp+40h] [rbp-40h] BYREF
  __int16 v8; // [rsp+44h] [rbp-3Ch]
  __int16 v9; // [rsp+46h] [rbp-3Ah]
  CDefragService *v10; // [rsp+90h] [rbp+10h] BYREF
  LPVOID ppv; // [rsp+98h] [rbp+18h] BYREF

  v10 = this;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v7, "CDefragService::Stop", 451, 1);
  ppv = 0;
  v10 = 0;
  if ( qword_180089AE8 )
    CM_Unregister_Notification();
  if ( CoCreateInstance(&CLSID_CDefragEngine, 0, 4u, &IID_IUnknown, &ppv) >= 0 )
  {
    if ( (**(int (__fastcall ***)(LPVOID, GUID *, CDefragService **))ppv)(ppv, &IID_IDefragEnginePriv, &v10) >= 0 )
    {
      (*(void (__fastcall **)(CDefragService *))(*(_QWORD *)v10 + 192LL))(v10);
      v1 = v10;
      if ( v10 )
      {
        v10 = 0;
        (*(void (__fastcall **)(CDefragService *))(*(_QWORD *)v1 + 16LL))(v1);
      }
    }
    v2 = ppv;
    if ( ppv )
    {
      ppv = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v2 + 16LL))(v2);
    }
  }
  v3 = (CDefragService *)::ppv;
  if ( ::ppv )
  {
    if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_9dfa55146e94391ee67982bf00c934b1_Traceguids);
      v3 = (CDefragService *)::ppv;
    }
    v4 = (*(__int64 (__fastcall **)(CDefragService *, __int64 (__fastcall *)(struct tagComCallData *), _QWORD, GUID *, int, _QWORD))(*(_QWORD *)v3 + 24LL))(
           v3,
           CDefragService::DisconnectCallback,
           0,
           &IID_IContextCallback,
           5,
           0);
    if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_9dfa55146e94391ee67982bf00c934b1_Traceguids, v4);
    }
    ATL::CComPtrBase<IContextCallback>::Release(&::ppv);
  }
  if ( byte_180089B40 )
    CSxSafeComPtr<IContextCallback>::Reset(&qword_180089B00);
  CDefragService::UninitializeCOM(v3);
  v5 = v7;
  if ( v7 >= 0 )
    v8 = 498;
  else
    v9 = 498;
  if ( v10 )
    (*(void (__fastcall **)(CDefragService *))(*(_QWORD *)v10 + 16LL))(v10);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v7);
  return v5;
}

```

## disassembly

```asm
0x180027760  mov     [rsp-8+arg_10], rbx
0x180027765  mov     [rsp-8+arg_18], rsi
0x18002776a  mov     [rsp-8+arg_0], rcx
0x18002776f  push    rbp
0x180027770  mov     rbp, rsp
0x180027773  sub     rsp, 80h
0x18002777a  mov     r9d, 1; unsigned __int16
0x180027780  mov     r8d, 1C3h; unsigned __int16
0x180027786  lea     rdx, aCdefragservice_0; "CDefragService::Stop"
0x18002778d  lea     rcx, [rbp+var_40]; this
0x180027791  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180027796  nop
0x180027797  mov     [rbp+arg_8], 0
0x18002779f  mov     [rbp+arg_0], 0
0x1800277a7  mov     rcx, cs:qword_180089AE8
0x1800277ae  test    rcx, rcx
0x1800277b1  jz      short loc_1800277B9
0x1800277b3  call    cs:__imp_CM_Unregister_Notification
0x1800277b9  lea     rax, [rbp+arg_8]
0x1800277bd  mov     [rsp+80h+ppv], rax; ppv
0x1800277c2  lea     r9, IID_IUnknown; riid
0x1800277c9  xor     edx, edx; pUnkOuter
0x1800277cb  lea     r8d, [rdx+4]; dwClsContext
0x1800277cf  lea     rcx, CLSID_CDefragEngine; rclsid
0x1800277d6  call    cs:__imp_CoCreateInstance
0x1800277dc  test    eax, eax
0x1800277de  js      short loc_18002784E
0x1800277e0  mov     rcx, [rbp+arg_8]
0x1800277e4  mov     rax, [rcx]
0x1800277e7  lea     r8, [rbp+arg_0]
0x1800277eb  lea     rdx, IID_IDefragEnginePriv
0x1800277f2  mov     rax, [rax]
0x1800277f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800277fa  test    eax, eax
0x1800277fc  js      short loc_180027830
0x1800277fe  mov     rcx, [rbp+arg_0]
0x180027802  mov     rax, [rcx]
0x180027805  mov     rax, [rax+0C0h]
0x18002780c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027811  nop
0x180027812  mov     rcx, [rbp+arg_0]
0x180027816  test    rcx, rcx
0x180027819  jz      short loc_180027830
0x18002781b  mov     [rbp+arg_0], 0
0x180027823  mov     rax, [rcx]
0x180027826  mov     rax, [rax+10h]
0x18002782a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002782f  nop
0x180027830  mov     rcx, [rbp+arg_8]
0x180027834  test    rcx, rcx
0x180027837  jz      short loc_18002784E
0x180027839  mov     [rbp+arg_8], 0
0x180027841  mov     rax, [rcx]
0x180027844  mov     rax, [rax+10h]
0x180027848  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002784d  nop
0x18002784e  mov     rcx, cs:ppv
0x180027855  test    rcx, rcx
0x180027858  jz      loc_1800278FA
0x18002785e  lea     rsi, WPP_GLOBAL_Control
0x180027865  mov     ebx, 8000000h
0x18002786a  mov     rax, cs:WPP_GLOBAL_Control
0x180027871  cmp     rax, rsi
0x180027874  jz      short loc_180027897
0x180027876  test    [rax+1Ch], ebx
0x180027879  jz      short loc_180027897
0x18002787b  mov     edx, 0Fh
0x180027880  lea     r8, WPP_9dfa55146e94391ee67982bf00c934b1_Traceguids
0x180027887  mov     rcx, [rax+10h]
0x18002788b  call    WPP_SF_
0x180027890  mov     rcx, cs:ppv
0x180027897  mov     rax, [rcx]
0x18002789a  mov     [rsp+80h+var_58], 0
0x1800278a3  mov     dword ptr [rsp+80h+ppv], 5
0x1800278ab  lea     r9, IID_IContextCallback
0x1800278b2  xor     r8d, r8d
0x1800278b5  lea     rdx, ?DisconnectCallback@CDefragService@@CAJPEAUtagComCallData@@@Z; CDefragService::DisconnectCallback(tagComCallData *)
0x1800278bc  mov     rax, [rax+18h]
0x1800278c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800278c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800278cc  cmp     rcx, rsi
0x1800278cf  jz      short loc_1800278EE
0x1800278d1  test    [rcx+1Ch], ebx
0x1800278d4  jz      short loc_1800278EE
0x1800278d6  mov     edx, 10h
0x1800278db  mov     r9d, eax
0x1800278de  lea     r8, WPP_9dfa55146e94391ee67982bf00c934b1_Traceguids
0x1800278e5  mov     rcx, [rcx+10h]
0x1800278e9  call    WPP_SF_d
0x1800278ee  lea     rcx, ppv
0x1800278f5  call    ?Release@?$CComPtrBase@UIContextCallback@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IContextCallback>::Release(void)
0x1800278fa  mov     al, cs:byte_180089B40
0x180027900  test    al, al
0x180027902  jz      short loc_180027910
0x180027904  lea     rcx, qword_180089B00
0x18002790b  call    ?Reset@?$CSxSafeComPtr@UIContextCallback@@@@QEAAJXZ; CSxSafeComPtr<IContextCallback>::Reset(void)
0x180027910  call    ?UninitializeCOM@CDefragService@@QEAAJXZ; CDefragService::UninitializeCOM(void)
0x180027915  mov     ebx, [rbp+var_40]
0x180027918  mov     eax, 1F2h
0x18002791d  test    ebx, ebx
0x18002791f  jns     short loc_180027927
0x180027921  mov     [rbp+var_3A], ax
0x180027925  jmp     short loc_18002792B
0x180027927  mov     [rbp+var_3C], ax
0x18002792b  mov     rcx, [rbp+arg_0]
0x18002792f  test    rcx, rcx
0x180027932  jz      short loc_180027941
0x180027934  mov     rax, [rcx]
0x180027937  mov     rax, [rax+10h]
0x18002793b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027940  nop
0x180027941  mov     rcx, [rbp+arg_8]
0x180027945  test    rcx, rcx
0x180027948  jz      short loc_180027957
0x18002794a  mov     rdx, [rcx]
0x18002794d  mov     rax, [rdx+10h]
0x180027951  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027956  nop
0x180027957  lea     rcx, [rbp+var_40]; this
0x18002795b  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180027960  mov     eax, ebx
0x180027962  lea     r11, [rsp+80h+var_s0]
0x18002796a  mov     rbx, [r11+20h]
0x18002796e  mov     rsi, [r11+28h]
0x180027972  mov     rsp, r11
0x180027975  pop     rbp
0x180027976  retn
```
