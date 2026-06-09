# CreateStreamAndMarshalTaskParameters(ITaskHandlerStatus *,ushort *,IStream * *)

- ea: `0x1800369a4`
- end: `0x180036b76`
- name: `?CreateStreamAndMarshalTaskParameters@@YAJPEAUITaskHandlerStatus@@PEAGPEAPEAUIStream@@@Z`
- size: `466`
- prototype: `HRESULT __fastcall(ITaskHandlerStatus *pTaskHandlerStatus, wchar_t *Data, IStream **ppStream)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180037540`

## callees

- `0x180002790`
- `0x18000b2f4`
- `0x180012748`
- `0x180018564`
- `0x180019ea4`
- `0x1800369a4`
- `0x18006f010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180036a6f`
- `OLEAUT32!__imp_SysFreeString` at `0x180036a6f`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180036a13`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180036a13`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180036ac6`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180036ac6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CreateStreamAndMarshalTaskParameters(
        ITaskHandlerStatus *pTaskHandlerStatus,
        wchar_t *Data,
        IStream **ppStream)
{
  HRESULT StreamOnHGlobal; // ebx
  IStream *p; // rax
  ATL::CComBSTR dataWrap; // [rsp+30h] [rbp-48h] BYREF
  ATL::CComPtr<IStream> spStream; // [rsp+38h] [rbp-40h] BYREF

  spStream.p = 0;
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0xAu, WPP_0ed40dcb6852371d76e9e4c46355112e_Traceguids);
  }
  StreamOnHGlobal = CreateStreamOnHGlobal(0, 1, &spStream.p);
  if ( StreamOnHGlobal >= 0 )
  {
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0xBu, WPP_0ed40dcb6852371d76e9e4c46355112e_Traceguids);
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
        WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0xCu, WPP_0ed40dcb6852371d76e9e4c46355112e_Traceguids);
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
          WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0xDu, WPP_0ed40dcb6852371d76e9e4c46355112e_Traceguids);
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
            WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0xEu, WPP_0ed40dcb6852371d76e9e4c46355112e_Traceguids);
          }
          p = spStream.p;
          spStream.p = 0;
          *ppStream = p;
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
0x1800369a4  mov     [rsp+arg_8], rbx
0x1800369a9  push    rsi
0x1800369aa  push    rdi
0x1800369ab  push    r12
0x1800369ad  push    r13
0x1800369af  push    r14
0x1800369b1  sub     rsp, 50h
0x1800369b5  mov     rax, cs:__security_cookie
0x1800369bc  xor     rax, rsp
0x1800369bf  mov     [rsp+78h+var_38], rax
0x1800369c4  mov     r14, ppStream
0x1800369c7  mov     rdi, Data
0x1800369ca  mov     rsi, pTaskHandlerStatus
0x1800369cd  mov     [rsp+78h+spStream.p], 0
0x1800369d6  lea     r12, WPP_GLOBAL_Control; __annotation("TMF:",
0x1800369dd  lea     r13, WPP_0ed40dcb6852371d76e9e4c46355112e_Traceguids
0x1800369e4  mov     pTaskHandlerStatus, cs:WPP_GLOBAL_Control
0x1800369eb  cmp     pTaskHandlerStatus, r12
0x1800369ee  jz      short loc_180036A07
0x1800369f0  test    byte ptr [pTaskHandlerStatus+1Ch], 10h
0x1800369f4  jz      short loc_180036A07
0x1800369f6  mov     edx, 0Ah; id
0x1800369fb  mov     ppStream, r13; TraceGuid
0x1800369fe  mov     pTaskHandlerStatus, [pTaskHandlerStatus+10h]; Logger
0x180036a02  call    WPP_SF_
0x180036a07  lea     ppStream, [rsp+78h+spStream]; ppstm
0x180036a0c  mov     edx, 1; fDeleteOnRelease
0x180036a11  xor     ecx, ecx; hGlobal
0x180036a13  call    cs:__imp_CreateStreamOnHGlobal
0x180036a19  mov     ebx, eax
0x180036a1b  test    eax, eax
0x180036a1d  js      loc_180036B48
0x180036a23  mov     pTaskHandlerStatus, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180036a2a  cmp     pTaskHandlerStatus, r12
0x180036a2d  jz      short loc_180036A46
0x180036a2f  test    byte ptr [pTaskHandlerStatus+1Ch], 10h
0x180036a33  jz      short loc_180036A46
0x180036a35  mov     edx, 0Bh; id
0x180036a3a  mov     ppStream, r13; TraceGuid
0x180036a3d  mov     pTaskHandlerStatus, [pTaskHandlerStatus+10h]; Logger
0x180036a41  call    WPP_SF_
0x180036a46  mov     [rsp+78h+dataWrap.m_str], 0
0x180036a4f  mov     Data, rdi; src
0x180036a52  lea     pTaskHandlerStatus, [rsp+78h+dataWrap]; this
0x180036a57  call    ?Attach@CComBSTR@ATL@@QEAAXPEAG@Z; ATL::CComBSTR::Attach(ushort *)
0x180036a5c  mov     Data, [rsp+78h+spStream.p]; pStream
0x180036a61  lea     pTaskHandlerStatus, [rsp+78h+dataWrap]; this
0x180036a66  call    ?WriteToStream@CComBSTR@ATL@@QEAAJPEAUIStream@@@Z; ATL::CComBSTR::WriteToStream(IStream *)
0x180036a6b  mov     ebx, eax
0x180036a6d  xor     ecx, ecx; bstrString
0x180036a6f  call    cs:__imp_SysFreeString
0x180036a75  test    ebx, ebx
0x180036a77  js      loc_180036B48
0x180036a7d  mov     pTaskHandlerStatus, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180036a84  cmp     pTaskHandlerStatus, r12
0x180036a87  jz      short loc_180036AA0
0x180036a89  test    byte ptr [pTaskHandlerStatus+1Ch], 10h
0x180036a8d  jz      short loc_180036AA0
0x180036a8f  mov     edx, 0Ch; id
0x180036a94  mov     ppStream, r13; TraceGuid
0x180036a97  mov     pTaskHandlerStatus, [pTaskHandlerStatus+10h]; Logger
0x180036a9b  call    WPP_SF_
0x180036aa0  mov     [rsp+78h+mshlflags], 0; mshlflags
0x180036aa8  mov     [rsp+78h+pvDestContext], 0; pvDestContext
0x180036ab1  mov     r9d, 3; dwDestContext
0x180036ab7  mov     ppStream, rsi; pUnk
0x180036aba  lea     Data, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a; riid
0x180036ac1  mov     pTaskHandlerStatus, [rsp+78h+spStream.p]; pStm
0x180036ac6  call    cs:__imp_CoMarshalInterface
0x180036acc  mov     ebx, eax
0x180036ace  test    eax, eax
0x180036ad0  js      short loc_180036B48
0x180036ad2  mov     pTaskHandlerStatus, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180036ad9  cmp     pTaskHandlerStatus, r12
0x180036adc  jz      short loc_180036AF5
0x180036ade  test    byte ptr [pTaskHandlerStatus+1Ch], 10h
0x180036ae2  jz      short loc_180036AF5
0x180036ae4  mov     edx, 0Dh; id
0x180036ae9  mov     ppStream, r13; TraceGuid
0x180036aec  mov     pTaskHandlerStatus, [pTaskHandlerStatus+10h]; Logger
0x180036af0  call    WPP_SF_
0x180036af5  mov     pTaskHandlerStatus, [rsp+78h+spStream.p]
0x180036afa  xor     edx, edx
0x180036afc  mov     rax, [pTaskHandlerStatus]
0x180036aff  xor     r9d, r9d
0x180036b02  xor     r8d, r8d
0x180036b05  mov     rax, [rax+28h]
0x180036b09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036b0e  mov     ebx, eax
0x180036b10  test    eax, eax
0x180036b12  js      short loc_180036B48
0x180036b14  mov     pTaskHandlerStatus, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180036b1b  cmp     pTaskHandlerStatus, r12
0x180036b1e  jz      short loc_180036B37
0x180036b20  test    byte ptr [pTaskHandlerStatus+1Ch], 10h
0x180036b24  jz      short loc_180036B37
0x180036b26  mov     edx, 0Eh; id
0x180036b2b  mov     ppStream, r13; TraceGuid
0x180036b2e  mov     pTaskHandlerStatus, [pTaskHandlerStatus+10h]; Logger
0x180036b32  call    WPP_SF_
0x180036b37  mov     rax, [rsp+78h+spStream.p]
0x180036b3c  mov     [rsp+78h+spStream.p], 0
0x180036b45  mov     [r14], rax
0x180036b48  lea     pTaskHandlerStatus, [rsp+78h+spStream]; this
0x180036b4d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180036b52  mov     eax, ebx
0x180036b54  mov     pTaskHandlerStatus, [rsp+78h+var_38]
0x180036b59  xor     pTaskHandlerStatus, rsp; StackCookie
0x180036b5c  call    __security_check_cookie
0x180036b61  mov     rbx, [rsp+78h+arg_8]
0x180036b69  add     rsp, 50h
0x180036b6d  pop     r14
0x180036b6f  pop     r13
0x180036b71  pop     r12
0x180036b73  pop     rdi
0x180036b74  pop     rsi
0x180036b75  retn
```
