# Microsoft::Windows::Performance::CWinSATEventTraceExtender::ProcessWinSATStore(_LARGE_INTEGER,ulong,ulong)

- ea: `0x180020774`
- end: `0x1800208d0`
- name: `?ProcessWinSATStore@CWinSATEventTraceExtender@Performance@Windows@Microsoft@@AEAAJT_LARGE_INTEGER@@KK@Z`
- size: `348`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CWinSATEventTraceExtender *__hidden this, union _LARGE_INTEGER, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180020210`

## callees

- `0x180007b34`
- `0x18002032c`
- `0x180020774`
- `0x180026010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800207b5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800207b5`

## string_xrefs

- `0x180020893`: `WinSAT/SystemConfig`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::Windows::Performance::CWinSATEventTraceExtender::ProcessWinSATStore(
        Microsoft::Windows::Performance::CWinSATEventTraceExtender *this,
        union _LARGE_INTEGER a2,
        unsigned int a3,
        unsigned int a4)
{
  HRESULT Instance; // edi
  int v9; // eax
  __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002 v11; // [rsp+40h] [rbp-28h] BYREF
  struct IQueryRecentWinSATAssessment *ppv; // [rsp+48h] [rbp-20h] BYREF
  __int64 v13[3]; // [rsp+50h] [rbp-18h] BYREF

  ppv = 0;
  Instance = CoCreateInstance(
               &GUID_f3bdfad3_f276_49e9_9b17_c474f48f0764,
               0,
               1u,
               &GUID_f8ad5d1f_3b47_4bdc_9375_7c6b1da4eca7,
               (LPVOID *)&ppv);
  if ( Instance >= 0 )
  {
    v11 = WINSAT_ASSESSMENT_STATE_MIN;
    v13[0] = 0;
    Instance = ((__int64 (__fastcall *)(struct IQueryRecentWinSATAssessment *, __int64 *))ppv->lpVtbl->get_Info)(
                 ppv,
                 v13);
    if ( Instance < 0
      || (Instance = (*(__int64 (__fastcall **)(__int64, __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002 *))(*(_QWORD *)v13[0] + 64LL))(
                       v13[0],
                       &v11),
          Instance < 0) )
    {
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v13);
    }
    else
    {
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v13);
      v9 = Microsoft::Windows::Performance::CWinSATEventTraceExtender::ProcessWinSATAssessmentInfo(
             this,
             ppv,
             v11,
             0x20u,
             L"WinSAT/WinSPR",
             a2,
             a3,
             a4);
      if ( v9 < 0
        || (v9 = Microsoft::Windows::Performance::CWinSATEventTraceExtender::ProcessWinSATAssessmentInfo(
                   this,
                   ppv,
                   v11,
                   0x22u,
                   L"WinSAT/Metrics",
                   a2,
                   a3,
                   a4),
            v9 < 0)
        || (v9 = Microsoft::Windows::Performance::CWinSATEventTraceExtender::ProcessWinSATAssessmentInfo(
                   this,
                   ppv,
                   v11,
                   0x24u,
                   L"WinSAT/SystemConfig",
                   a2,
                   a3,
                   a4),
            v9 < 0) )
      {
        Instance = v9;
      }
      else
      {
        Instance = 0;
      }
    }
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&ppv);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180020774  push    rbp
0x180020776  push    rbx
0x180020777  push    rsi
0x180020778  push    rdi
0x180020779  push    r14
0x18002077b  push    r15
0x18002077d  mov     rbp, rsp
0x180020780  sub     rsp, 68h
0x180020784  mov     esi, r9d
0x180020787  mov     r14d, r8d
0x18002078a  mov     rbx, rdx
0x18002078d  mov     r15, rcx
0x180020790  mov     [rbp+var_20], 0
0x180020798  lea     rax, [rbp+var_20]
0x18002079c  mov     [rsp+68h+ppv], rax; ppv
0x1800207a1  lea     r9, _GUID_f8ad5d1f_3b47_4bdc_9375_7c6b1da4eca7; riid
0x1800207a8  xor     edx, edx; pUnkOuter
0x1800207aa  lea     r8d, [rdx+1]; dwClsContext
0x1800207ae  lea     rcx, _GUID_f3bdfad3_f276_49e9_9b17_c474f48f0764; rclsid
0x1800207b5  call    cs:__imp_CoCreateInstance
0x1800207bb  mov     edi, eax
0x1800207bd  test    eax, eax
0x1800207bf  js      loc_1800208B8
0x1800207c5  mov     [rbp+var_28], 0
0x1800207cc  mov     [rbp+var_18], 0
0x1800207d4  mov     rcx, [rbp+var_20]
0x1800207d8  mov     rax, [rcx]
0x1800207db  lea     rdx, [rbp+var_18]
0x1800207df  mov     rax, [rax+40h]
0x1800207e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800207e8  mov     edi, eax
0x1800207ea  test    eax, eax
0x1800207ec  jns     short loc_1800207FC
0x1800207ee  lea     rcx, [rbp+var_18]
0x1800207f2  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800207f7  jmp     loc_1800208B8
0x1800207fc  mov     rcx, [rbp+var_18]
0x180020800  mov     rax, [rcx]
0x180020803  lea     rdx, [rbp+var_28]
0x180020807  mov     rax, [rax+40h]
0x18002080b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020810  mov     edi, eax
0x180020812  lea     rcx, [rbp+var_18]
0x180020816  test    eax, eax
0x180020818  js      short loc_1800207F2
0x18002081a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002081f  mov     [rsp+68h+var_30], esi; unsigned int
0x180020823  mov     [rsp+68h+var_38], r14d; unsigned int
0x180020828  mov     qword ptr [rsp+68h+var_40], rbx; union _LARGE_INTEGER
0x18002082d  lea     rax, aWinsatWinspr; "WinSAT/WinSPR"
0x180020834  mov     [rsp+68h+ppv], rax; unsigned __int16 *
0x180020839  mov     r9b, 20h ; ' '; unsigned __int8
0x18002083c  mov     r8d, [rbp+var_28]; enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002
0x180020840  mov     rdx, [rbp+var_20]; struct IQueryRecentWinSATAssessment *
0x180020844  mov     rcx, r15; this
0x180020847  call    ?ProcessWinSATAssessmentInfo@CWinSATEventTraceExtender@Performance@Windows@Microsoft@@AEAAJPEAUIQueryRecentWinSATAssessment@@W4__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002@@EPEBGT_LARGE_INTEGER@@KK@Z; Microsoft::Windows::Performance::CWinSATEventTraceExtender::ProcessWinSATAssessmentInfo(IQueryRecentWinSATAssessment *,__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002,uchar,ushort const *,_LARGE_INTEGER,ulong,ulong)
0x18002084c  test    eax, eax
0x18002084e  jns     short loc_180020854
0x180020850  mov     edi, eax
0x180020852  jmp     short loc_1800208B8
0x180020854  mov     [rsp+68h+var_30], esi; unsigned int
0x180020858  mov     [rsp+68h+var_38], r14d; unsigned int
0x18002085d  mov     qword ptr [rsp+68h+var_40], rbx; union _LARGE_INTEGER
0x180020862  lea     rax, aWinsatMetrics; "WinSAT/Metrics"
0x180020869  mov     [rsp+68h+ppv], rax; unsigned __int16 *
0x18002086e  mov     r9b, 22h ; '"'; unsigned __int8
0x180020871  mov     r8d, [rbp+var_28]; enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002
0x180020875  mov     rdx, [rbp+var_20]; struct IQueryRecentWinSATAssessment *
0x180020879  mov     rcx, r15; this
0x18002087c  call    ?ProcessWinSATAssessmentInfo@CWinSATEventTraceExtender@Performance@Windows@Microsoft@@AEAAJPEAUIQueryRecentWinSATAssessment@@W4__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002@@EPEBGT_LARGE_INTEGER@@KK@Z; Microsoft::Windows::Performance::CWinSATEventTraceExtender::ProcessWinSATAssessmentInfo(IQueryRecentWinSATAssessment *,__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002,uchar,ushort const *,_LARGE_INTEGER,ulong,ulong)
0x180020881  test    eax, eax
0x180020883  js      short loc_180020850
0x180020885  mov     [rsp+68h+var_30], esi; unsigned int
0x180020889  mov     [rsp+68h+var_38], r14d; unsigned int
0x18002088e  mov     qword ptr [rsp+68h+var_40], rbx; union _LARGE_INTEGER
0x180020893  lea     rax, aWinsatSystemco; "WinSAT/SystemConfig"
0x18002089a  mov     [rsp+68h+ppv], rax; unsigned __int16 *
0x18002089f  mov     r9b, 24h ; '$'; unsigned __int8
0x1800208a2  mov     r8d, [rbp+var_28]; enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002
0x1800208a6  mov     rdx, [rbp+var_20]; struct IQueryRecentWinSATAssessment *
0x1800208aa  mov     rcx, r15; this
0x1800208ad  call    ?ProcessWinSATAssessmentInfo@CWinSATEventTraceExtender@Performance@Windows@Microsoft@@AEAAJPEAUIQueryRecentWinSATAssessment@@W4__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002@@EPEBGT_LARGE_INTEGER@@KK@Z; Microsoft::Windows::Performance::CWinSATEventTraceExtender::ProcessWinSATAssessmentInfo(IQueryRecentWinSATAssessment *,__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002,uchar,ushort const *,_LARGE_INTEGER,ulong,ulong)
0x1800208b2  test    eax, eax
0x1800208b4  js      short loc_180020850
0x1800208b6  xor     edi, edi
0x1800208b8  lea     rcx, [rbp+var_20]
0x1800208bc  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800208c1  mov     eax, edi
0x1800208c3  add     rsp, 68h
0x1800208c7  pop     r15
0x1800208c9  pop     r14
0x1800208cb  pop     rdi
0x1800208cc  pop     rsi
0x1800208cd  pop     rbx
0x1800208ce  pop     rbp
0x1800208cf  retn
```
