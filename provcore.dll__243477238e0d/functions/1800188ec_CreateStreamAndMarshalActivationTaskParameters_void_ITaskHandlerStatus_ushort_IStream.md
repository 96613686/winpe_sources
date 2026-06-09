# CreateStreamAndMarshalActivationTaskParameters(void *,ITaskHandlerStatus *,ushort *,IStream * *)

- ea: `0x1800188ec`
- end: `0x180018b5b`
- name: `?CreateStreamAndMarshalActivationTaskParameters@@YAJPEAXPEAUITaskHandlerStatus@@PEAGPEAPEAUIStream@@@Z`
- size: `623`
- prototype: `HRESULT __fastcall(void *CancelEvent, ITaskHandlerStatus *pTaskHandlerStatus, wchar_t *Data, IStream **ppStream)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180019810`

## callees

- `0x180002790`
- `0x18000b2f4`
- `0x180012748`
- `0x180012770`
- `0x180018564`
- `0x1800188ec`
- `0x180019ea4`
- `0x18006f010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180018a4f`
- `OLEAUT32!__imp_SysFreeString` at `0x180018a4f`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18001895b`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18001895b`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180018aa9`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180018aa9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CreateStreamAndMarshalActivationTaskParameters(
        void *CancelEvent,
        ITaskHandlerStatus *pTaskHandlerStatus,
        wchar_t *Data,
        IStream **ppStream)
{
  HRESULT StreamOnHGlobal; // ebx
  IStream *p; // rax
  void *v10; // [rsp+30h] [rbp-20h] BYREF
  ATL::CComPtr<IStream> spStream; // [rsp+38h] [rbp-18h] BYREF
  ATL::CComBSTR dataWrap; // [rsp+40h] [rbp-10h] BYREF

  v10 = CancelEvent;
  spStream.p = 0;
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0xAu, WPP_134a5cb9373134b19d236cc06387f3ce_Traceguids);
  }
  StreamOnHGlobal = CreateStreamOnHGlobal(0, 1, &spStream.p);
  if ( StreamOnHGlobal >= 0 )
  {
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0xBu, WPP_134a5cb9373134b19d236cc06387f3ce_Traceguids);
    }
    LODWORD(dataWrap.m_str) = 0;
    StreamOnHGlobal = spStream.p->Write(spStream.p, &v10, 8u, (unsigned int *)&dataWrap);
    if ( StreamOnHGlobal >= 0 )
    {
      if ( LODWORD(dataWrap.m_str) == 8 )
      {
        if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0xDu, WPP_134a5cb9373134b19d236cc06387f3ce_Traceguids);
        }
        dataWrap.m_str = 0;
        ATL::CComBSTR::Attach(&dataWrap, Data);
        StreamOnHGlobal = ATL::CComBSTR::WriteToStream(&dataWrap, spStream.p);
        SysFreeString(0);
        if ( StreamOnHGlobal >= 0 )
        {
          if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0xEu, WPP_134a5cb9373134b19d236cc06387f3ce_Traceguids);
          }
          StreamOnHGlobal = CoMarshalInterface(
                              spStream.p,
                              &GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a,
                              pTaskHandlerStatus,
                              3u,
                              0,
                              0);
          if ( StreamOnHGlobal >= 0 )
          {
            if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
              && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
            {
              WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0xFu, WPP_134a5cb9373134b19d236cc06387f3ce_Traceguids);
            }
            StreamOnHGlobal = ((__int64 (__fastcall *)(IStream *, _QWORD, _QWORD, _QWORD))spStream.p->Seek)(
                                spStream.p,
                                0,
                                0,
                                0);
            if ( StreamOnHGlobal >= 0 )
            {
              if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
                && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
              {
                WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x10u, WPP_134a5cb9373134b19d236cc06387f3ce_Traceguids);
              }
              p = spStream.p;
              spStream.p = 0;
              *ppStream = p;
            }
          }
        }
      }
      else
      {
        StreamOnHGlobal = -2147024774;
        if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control->ReserveSpace[28] & 2) != 0 )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->Control.Logger,
            0xCu,
            WPP_134a5cb9373134b19d236cc06387f3ce_Traceguids,
            -2147024774);
        }
      }
    }
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((ATL::CComPtrBase<Windows::Networking::NetworkOperators::IMobileBroadbandNetwork> *)&spStream);
  return (unsigned int)StreamOnHGlobal;
}

```

## disassembly

```asm
0x1800188ec  mov     [rsp-28h+arg_10], rbx
0x1800188f1  push    rbp
0x1800188f2  push    rsi
0x1800188f3  push    rdi
0x1800188f4  push    r13
0x1800188f6  push    r14
0x1800188f8  mov     rbp, rsp
0x1800188fb  sub     rsp, 50h
0x1800188ff  mov     rax, cs:__security_cookie
0x180018906  xor     rax, rsp
0x180018909  mov     [rbp+var_8], rax
0x18001890d  mov     r14, ppStream
0x180018910  mov     rdi, Data
0x180018913  mov     rsi, pTaskHandlerStatus
0x180018916  mov     [rbp+var_20], CancelEvent
0x18001891a  mov     [rbp+spStream.p], 0
0x180018922  lea     r13, WPP_GLOBAL_Control; __annotation("TMF:",
0x180018929  mov     CancelEvent, cs:WPP_GLOBAL_Control
0x180018930  cmp     CancelEvent, r13
0x180018933  jz      short loc_180018950
0x180018935  test    byte ptr [CancelEvent+1Ch], 10h
0x180018939  jz      short loc_180018950
0x18001893b  mov     edx, 0Ah; id
0x180018940  lea     Data, WPP_134a5cb9373134b19d236cc06387f3ce_Traceguids; TraceGuid
0x180018947  mov     CancelEvent, [CancelEvent+10h]; Logger
0x18001894b  call    WPP_SF_
0x180018950  lea     Data, [rbp+spStream]; ppstm
0x180018954  mov     edx, 1; fDeleteOnRelease
0x180018959  xor     ecx, ecx; hGlobal
0x18001895b  call    cs:__imp_CreateStreamOnHGlobal
0x180018961  mov     ebx, eax
0x180018963  test    eax, eax
0x180018965  js      loc_180018B30
0x18001896b  mov     CancelEvent, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180018972  cmp     CancelEvent, r13
0x180018975  jz      short loc_180018992
0x180018977  test    byte ptr [CancelEvent+1Ch], 10h
0x18001897b  jz      short loc_180018992
0x18001897d  mov     edx, 0Bh; id
0x180018982  lea     Data, WPP_134a5cb9373134b19d236cc06387f3ce_Traceguids; TraceGuid
0x180018989  mov     CancelEvent, [CancelEvent+10h]; Logger
0x18001898d  call    WPP_SF_
0x180018992  mov     dword ptr [rbp+dataWrap.m_str], 0
0x180018999  mov     CancelEvent, [rbp+spStream.p]
0x18001899d  mov     rax, [CancelEvent]
0x1800189a0  lea     ppStream, [rbp+dataWrap]
0x1800189a4  mov     r8d, 8
0x1800189aa  lea     pTaskHandlerStatus, [rbp+var_20]
0x1800189ae  mov     rax, [rax+20h]
0x1800189b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800189b7  mov     ebx, eax
0x1800189b9  test    eax, eax
0x1800189bb  js      loc_180018B30
0x1800189c1  cmp     dword ptr [rbp+dataWrap.m_str], 8
0x1800189c5  jz      short loc_180018A03
0x1800189c7  mov     ebx, 8007007Ah
0x1800189cc  mov     CancelEvent, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800189d3  cmp     CancelEvent, r13
0x1800189d6  jz      loc_180018B30
0x1800189dc  test    byte ptr [CancelEvent+1Ch], 2
0x1800189e0  jz      loc_180018B30
0x1800189e6  mov     edx, 0Ch; id
0x1800189eb  mov     r9d, ebx; _a1
0x1800189ee  lea     Data, WPP_134a5cb9373134b19d236cc06387f3ce_Traceguids; TraceGuid
0x1800189f5  mov     CancelEvent, [CancelEvent+10h]; Logger
0x1800189f9  call    WPP_SF_d
0x1800189fe  jmp     loc_180018B30
0x180018a03  mov     CancelEvent, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180018a0a  cmp     CancelEvent, r13
0x180018a0d  jz      short loc_180018A2A
0x180018a0f  test    byte ptr [CancelEvent+1Ch], 10h
0x180018a13  jz      short loc_180018A2A
0x180018a15  mov     edx, 0Dh; id
0x180018a1a  lea     Data, WPP_134a5cb9373134b19d236cc06387f3ce_Traceguids; TraceGuid
0x180018a21  mov     CancelEvent, [CancelEvent+10h]; Logger
0x180018a25  call    WPP_SF_
0x180018a2a  mov     [rbp+dataWrap.m_str], 0
0x180018a32  mov     pTaskHandlerStatus, rdi; src
0x180018a35  lea     CancelEvent, [rbp+dataWrap]; this
0x180018a39  call    ?Attach@CComBSTR@ATL@@QEAAXPEAG@Z; ATL::CComBSTR::Attach(ushort *)
0x180018a3e  mov     pTaskHandlerStatus, [rbp+spStream.p]; pStream
0x180018a42  lea     CancelEvent, [rbp+dataWrap]; this
0x180018a46  call    ?WriteToStream@CComBSTR@ATL@@QEAAJPEAUIStream@@@Z; ATL::CComBSTR::WriteToStream(IStream *)
0x180018a4b  mov     ebx, eax
0x180018a4d  xor     ecx, ecx; bstrString
0x180018a4f  call    cs:__imp_SysFreeString
0x180018a55  test    ebx, ebx
0x180018a57  js      loc_180018B30
0x180018a5d  mov     CancelEvent, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180018a64  cmp     CancelEvent, r13
0x180018a67  jz      short loc_180018A84
0x180018a69  test    byte ptr [CancelEvent+1Ch], 10h
0x180018a6d  jz      short loc_180018A84
0x180018a6f  mov     edx, 0Eh; id
0x180018a74  lea     Data, WPP_134a5cb9373134b19d236cc06387f3ce_Traceguids; TraceGuid
0x180018a7b  mov     CancelEvent, [CancelEvent+10h]; Logger
0x180018a7f  call    WPP_SF_
0x180018a84  mov     [rsp+50h+mshlflags], 0; mshlflags
0x180018a8c  mov     [rsp+50h+pvDestContext], 0; pvDestContext
0x180018a95  mov     r9d, 3; dwDestContext
0x180018a9b  mov     Data, rsi; pUnk
0x180018a9e  lea     pTaskHandlerStatus, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a; riid
0x180018aa5  mov     CancelEvent, [rbp+spStream.p]; pStm
0x180018aa9  call    cs:__imp_CoMarshalInterface
0x180018aaf  mov     ebx, eax
0x180018ab1  test    eax, eax
0x180018ab3  js      short loc_180018B30
0x180018ab5  mov     CancelEvent, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180018abc  cmp     CancelEvent, r13
0x180018abf  jz      short loc_180018ADC
0x180018ac1  test    byte ptr [CancelEvent+1Ch], 10h
0x180018ac5  jz      short loc_180018ADC
0x180018ac7  mov     edx, 0Fh; id
0x180018acc  lea     Data, WPP_134a5cb9373134b19d236cc06387f3ce_Traceguids; TraceGuid
0x180018ad3  mov     CancelEvent, [CancelEvent+10h]; Logger
0x180018ad7  call    WPP_SF_
0x180018adc  mov     CancelEvent, [rbp+spStream.p]
0x180018ae0  xor     edx, edx
0x180018ae2  mov     rax, [CancelEvent]
0x180018ae5  xor     r9d, r9d
0x180018ae8  xor     r8d, r8d
0x180018aeb  mov     rax, [rax+28h]
0x180018aef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018af4  mov     ebx, eax
0x180018af6  test    eax, eax
0x180018af8  js      short loc_180018B30
0x180018afa  mov     CancelEvent, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180018b01  cmp     CancelEvent, r13
0x180018b04  jz      short loc_180018B21
0x180018b06  test    byte ptr [CancelEvent+1Ch], 10h
0x180018b0a  jz      short loc_180018B21
0x180018b0c  mov     edx, 10h; id
0x180018b11  lea     Data, WPP_134a5cb9373134b19d236cc06387f3ce_Traceguids; TraceGuid
0x180018b18  mov     CancelEvent, [CancelEvent+10h]; Logger
0x180018b1c  call    WPP_SF_
0x180018b21  mov     rax, [rbp+spStream.p]
0x180018b25  mov     [rbp+spStream.p], 0
0x180018b2d  mov     [r14], rax
0x180018b30  lea     CancelEvent, [rbp+spStream]; this
0x180018b34  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180018b39  mov     eax, ebx
0x180018b3b  mov     CancelEvent, [rbp+var_8]
0x180018b3f  xor     CancelEvent, rsp; StackCookie
0x180018b42  call    __security_check_cookie
0x180018b47  mov     rbx, [rsp+50h+arg_10]
0x180018b4f  add     rsp, 50h
0x180018b53  pop     r14
0x180018b55  pop     r13
0x180018b57  pop     rdi
0x180018b58  pop     rsi
0x180018b59  pop     rbp
0x180018b5a  retn
```
