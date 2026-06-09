# Microsoft::Windows::Performance::CWinSATEventTraceExtender::ProcessWinSATStore(_LARGE_INTEGER,ulong,ulong)

- ea: `0x180021484`
- end: `0x1800215e7`
- name: `?ProcessWinSATStore@CWinSATEventTraceExtender@Performance@Windows@Microsoft@@AEAAJT_LARGE_INTEGER@@KK@Z`
- size: `355`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CWinSATEventTraceExtender *__hidden this, union _LARGE_INTEGER, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180020ef0`

## callees

- `0x180007ea4`
- `0x18002101c`
- `0x180021484`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800214c5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800214c5`

## string_xrefs

- `0x1800215a9`: `WinSAT/SystemConfig`

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
  _QWORD v13[3]; // [rsp+50h] [rbp-18h] BYREF

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
    Instance = ((__int64 (__fastcall *)(struct IQueryRecentWinSATAssessment *, _QWORD *))ppv->lpVtbl->get_Info)(
                 ppv,
                 v13);
    if ( Instance < 0
      || (Instance = (*(__int64 (__fastcall **)(_QWORD, __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002 *))(*(_QWORD *)v13[0] + 64LL))(
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
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180021484  push    rbp
0x180021486  push    rbx
0x180021487  push    rsi
0x180021488  push    rdi
0x180021489  push    r14
0x18002148b  push    r15
0x18002148d  mov     rbp, rsp
0x180021490  sub     rsp, 68h
0x180021494  mov     esi, r9d
0x180021497  mov     r14d, r8d
0x18002149a  mov     rbx, rdx
0x18002149d  mov     r15, rcx
0x1800214a0  mov     [rbp+var_20], 0
0x1800214a8  lea     rax, [rbp+var_20]
0x1800214ac  mov     [rsp+68h+ppv], rax; ppv
0x1800214b1  lea     r9, _GUID_f8ad5d1f_3b47_4bdc_9375_7c6b1da4eca7; riid
0x1800214b8  xor     edx, edx; pUnkOuter
0x1800214ba  lea     r8d, [rdx+1]; dwClsContext
0x1800214be  lea     rcx, _GUID_f3bdfad3_f276_49e9_9b17_c474f48f0764; rclsid
0x1800214c5  call    cs:__imp_CoCreateInstance
0x1800214cc  nop     dword ptr [rax+rax+00h]
0x1800214d1  mov     edi, eax
0x1800214d3  test    eax, eax
0x1800214d5  js      loc_1800215CE
0x1800214db  mov     [rbp+var_28], 0
0x1800214e2  mov     [rbp+var_18], 0
0x1800214ea  mov     rcx, [rbp+var_20]
0x1800214ee  mov     rax, [rcx]
0x1800214f1  lea     rdx, [rbp+var_18]
0x1800214f5  mov     rax, [rax+40h]
0x1800214f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800214fe  mov     edi, eax
0x180021500  test    eax, eax
0x180021502  jns     short loc_180021512
0x180021504  lea     rcx, [rbp+var_18]
0x180021508  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002150d  jmp     loc_1800215CE
0x180021512  mov     rcx, [rbp+var_18]
0x180021516  mov     rax, [rcx]
0x180021519  lea     rdx, [rbp+var_28]
0x18002151d  mov     rax, [rax+40h]
0x180021521  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021526  mov     edi, eax
0x180021528  lea     rcx, [rbp+var_18]
0x18002152c  test    eax, eax
0x18002152e  js      short loc_180021508
0x180021530  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180021535  mov     [rsp+68h+var_30], esi; unsigned int
0x180021539  mov     [rsp+68h+var_38], r14d; unsigned int
0x18002153e  mov     qword ptr [rsp+68h+var_40], rbx; union _LARGE_INTEGER
0x180021543  lea     rax, aWinsatWinspr; "WinSAT/WinSPR"
0x18002154a  mov     [rsp+68h+ppv], rax; unsigned __int16 *
0x18002154f  mov     r9b, 20h ; ' '; unsigned __int8
0x180021552  mov     r8d, [rbp+var_28]; enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002
0x180021556  mov     rdx, [rbp+var_20]; struct IQueryRecentWinSATAssessment *
0x18002155a  mov     rcx, r15; this
0x18002155d  call    ?ProcessWinSATAssessmentInfo@CWinSATEventTraceExtender@Performance@Windows@Microsoft@@AEAAJPEAUIQueryRecentWinSATAssessment@@W4__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002@@EPEBGT_LARGE_INTEGER@@KK@Z; Microsoft::Windows::Performance::CWinSATEventTraceExtender::ProcessWinSATAssessmentInfo(IQueryRecentWinSATAssessment *,__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002,uchar,ushort const *,_LARGE_INTEGER,ulong,ulong)
0x180021562  test    eax, eax
0x180021564  jns     short loc_18002156A
0x180021566  mov     edi, eax
0x180021568  jmp     short loc_1800215CE
0x18002156a  mov     [rsp+68h+var_30], esi; unsigned int
0x18002156e  mov     [rsp+68h+var_38], r14d; unsigned int
0x180021573  mov     qword ptr [rsp+68h+var_40], rbx; union _LARGE_INTEGER
0x180021578  lea     rax, aWinsatMetrics; "WinSAT/Metrics"
0x18002157f  mov     [rsp+68h+ppv], rax; unsigned __int16 *
0x180021584  mov     r9b, 22h ; '"'; unsigned __int8
0x180021587  mov     r8d, [rbp+var_28]; enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002
0x18002158b  mov     rdx, [rbp+var_20]; struct IQueryRecentWinSATAssessment *
0x18002158f  mov     rcx, r15; this
0x180021592  call    ?ProcessWinSATAssessmentInfo@CWinSATEventTraceExtender@Performance@Windows@Microsoft@@AEAAJPEAUIQueryRecentWinSATAssessment@@W4__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002@@EPEBGT_LARGE_INTEGER@@KK@Z; Microsoft::Windows::Performance::CWinSATEventTraceExtender::ProcessWinSATAssessmentInfo(IQueryRecentWinSATAssessment *,__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002,uchar,ushort const *,_LARGE_INTEGER,ulong,ulong)
0x180021597  test    eax, eax
0x180021599  js      short loc_180021566
0x18002159b  mov     [rsp+68h+var_30], esi; unsigned int
0x18002159f  mov     [rsp+68h+var_38], r14d; unsigned int
0x1800215a4  mov     qword ptr [rsp+68h+var_40], rbx; union _LARGE_INTEGER
0x1800215a9  lea     rax, aWinsatSystemco; "WinSAT/SystemConfig"
0x1800215b0  mov     [rsp+68h+ppv], rax; unsigned __int16 *
0x1800215b5  mov     r9b, 24h ; '$'; unsigned __int8
0x1800215b8  mov     r8d, [rbp+var_28]; enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002
0x1800215bc  mov     rdx, [rbp+var_20]; struct IQueryRecentWinSATAssessment *
0x1800215c0  mov     rcx, r15; this
0x1800215c3  call    ?ProcessWinSATAssessmentInfo@CWinSATEventTraceExtender@Performance@Windows@Microsoft@@AEAAJPEAUIQueryRecentWinSATAssessment@@W4__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002@@EPEBGT_LARGE_INTEGER@@KK@Z; Microsoft::Windows::Performance::CWinSATEventTraceExtender::ProcessWinSATAssessmentInfo(IQueryRecentWinSATAssessment *,__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002,uchar,ushort const *,_LARGE_INTEGER,ulong,ulong)
0x1800215c8  test    eax, eax
0x1800215ca  js      short loc_180021566
0x1800215cc  xor     edi, edi
0x1800215ce  lea     rcx, [rbp+var_20]
0x1800215d2  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800215d7  mov     eax, edi
0x1800215d9  add     rsp, 68h
0x1800215dd  pop     r15
0x1800215df  pop     r14
0x1800215e1  pop     rdi
0x1800215e2  pop     rsi
0x1800215e3  pop     rbx
0x1800215e4  pop     rbp
0x1800215e5  retn
```
