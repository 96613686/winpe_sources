# CreateStreamAndMarshalPurgeTaskParameters(ITaskHandlerStatus *,ushort *,IStream * *)

- ea: `0x180038a44`
- end: `0x180038bb7`
- name: `?CreateStreamAndMarshalPurgeTaskParameters@@YAJPEAUITaskHandlerStatus@@PEAGPEAPEAUIStream@@@Z`
- size: `371`
- prototype: `HRESULT __fastcall(ITaskHandlerStatus *pTaskHandlerStatus, wchar_t *ppStream, IStream **pTaskHandlerStatus)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800393f0`

## callees

- `0x180002790`
- `0x18000b2f4`
- `0x180012748`
- `0x180038a44`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180038aa9`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180038aa9`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180038b06`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180038b06`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CreateStreamAndMarshalPurgeTaskParameters(
        ITaskHandlerStatus *pTaskHandlerStatus,
        wchar_t *ppStream,
        IStream **a3)
{
  HRESULT StreamOnHGlobal; // ebx
  IStream *p; // rax
  ATL::CComPtr<IStream> spStream; // [rsp+30h] [rbp-28h] BYREF

  spStream.p = 0;
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0xAu, WPP_22f7751ad0f63f57b41be0e929348283_Traceguids);
  }
  StreamOnHGlobal = CreateStreamOnHGlobal(0, 1, &spStream.p);
  if ( StreamOnHGlobal >= 0 )
  {
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0xBu, WPP_22f7751ad0f63f57b41be0e929348283_Traceguids);
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
        WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0xCu, WPP_22f7751ad0f63f57b41be0e929348283_Traceguids);
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
          WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0xDu, WPP_22f7751ad0f63f57b41be0e929348283_Traceguids);
        }
        p = spStream.p;
        spStream.p = 0;
        *a3 = p;
      }
    }
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((ATL::CComPtrBase<Windows::Networking::NetworkOperators::IMobileBroadbandNetwork> *)&spStream);
  return (unsigned int)StreamOnHGlobal;
}

```

## disassembly

```asm
0x180038a44  mov     [rsp+arg_8], rbx
0x180038a49  push    rsi
0x180038a4a  push    rdi
0x180038a4b  push    r15
0x180038a4d  sub     rsp, 40h
0x180038a51  mov     rax, cs:__security_cookie
0x180038a58  xor     rax, rsp
0x180038a5b  mov     [rsp+58h+var_20], rax
0x180038a60  mov     rsi, ppStream
0x180038a63  mov     rdi, pTaskHandlerStatus
0x180038a66  mov     [rsp+58h+spStream.p], 0
0x180038a6f  lea     r15, WPP_GLOBAL_Control; __annotation("TMF:",
0x180038a76  mov     pTaskHandlerStatus, cs:WPP_GLOBAL_Control
0x180038a7d  cmp     pTaskHandlerStatus, r15
0x180038a80  jz      short loc_180038A9D
0x180038a82  test    byte ptr [pTaskHandlerStatus+1Ch], 10h
0x180038a86  jz      short loc_180038A9D
0x180038a88  mov     edx, 0Ah; id
0x180038a8d  lea     ppStream, WPP_22f7751ad0f63f57b41be0e929348283_Traceguids; TraceGuid
0x180038a94  mov     pTaskHandlerStatus, [pTaskHandlerStatus+10h]; Logger
0x180038a98  call    WPP_SF_
0x180038a9d  lea     ppStream, [rsp+58h+spStream]; ppstm
0x180038aa2  mov     edx, 1; fDeleteOnRelease
0x180038aa7  xor     ecx, ecx; hGlobal
0x180038aa9  call    cs:__imp_CreateStreamOnHGlobal
0x180038aaf  mov     ebx, eax
0x180038ab1  test    eax, eax
0x180038ab3  js      loc_180038B90
0x180038ab9  mov     pTaskHandlerStatus, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180038ac0  cmp     pTaskHandlerStatus, r15
0x180038ac3  jz      short loc_180038AE0
0x180038ac5  test    byte ptr [pTaskHandlerStatus+1Ch], 10h
0x180038ac9  jz      short loc_180038AE0
0x180038acb  mov     edx, 0Bh; id
0x180038ad0  lea     ppStream, WPP_22f7751ad0f63f57b41be0e929348283_Traceguids; TraceGuid
0x180038ad7  mov     pTaskHandlerStatus, [pTaskHandlerStatus+10h]; Logger
0x180038adb  call    WPP_SF_
0x180038ae0  mov     [rsp+58h+mshlflags], 0; mshlflags
0x180038ae8  mov     [rsp+58h+pvDestContext], 0; pvDestContext
0x180038af1  mov     r9d, 3; dwDestContext
0x180038af7  mov     ppStream, rdi; pUnk
0x180038afa  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a; riid
0x180038b01  mov     pTaskHandlerStatus, [rsp+58h+spStream.p]; pStm
0x180038b06  call    cs:__imp_CoMarshalInterface
0x180038b0c  mov     ebx, eax
0x180038b0e  test    eax, eax
0x180038b10  js      short loc_180038B90
0x180038b12  mov     pTaskHandlerStatus, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180038b19  cmp     pTaskHandlerStatus, r15
0x180038b1c  jz      short loc_180038B39
0x180038b1e  test    byte ptr [pTaskHandlerStatus+1Ch], 10h
0x180038b22  jz      short loc_180038B39
0x180038b24  mov     edx, 0Ch; id
0x180038b29  lea     ppStream, WPP_22f7751ad0f63f57b41be0e929348283_Traceguids; TraceGuid
0x180038b30  mov     pTaskHandlerStatus, [pTaskHandlerStatus+10h]; Logger
0x180038b34  call    WPP_SF_
0x180038b39  mov     pTaskHandlerStatus, [rsp+58h+spStream.p]
0x180038b3e  xor     edx, edx
0x180038b40  mov     rax, [pTaskHandlerStatus]
0x180038b43  xor     r9d, r9d
0x180038b46  xor     r8d, r8d
0x180038b49  mov     rax, [rax+28h]
0x180038b4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038b52  mov     ebx, eax
0x180038b54  test    eax, eax
0x180038b56  js      short loc_180038B90
0x180038b58  mov     pTaskHandlerStatus, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180038b5f  cmp     pTaskHandlerStatus, r15
0x180038b62  jz      short loc_180038B7F
0x180038b64  test    byte ptr [pTaskHandlerStatus+1Ch], 10h
0x180038b68  jz      short loc_180038B7F
0x180038b6a  mov     edx, 0Dh; id
0x180038b6f  lea     ppStream, WPP_22f7751ad0f63f57b41be0e929348283_Traceguids; TraceGuid
0x180038b76  mov     pTaskHandlerStatus, [pTaskHandlerStatus+10h]; Logger
0x180038b7a  call    WPP_SF_
0x180038b7f  mov     rax, [rsp+58h+spStream.p]
0x180038b84  mov     [rsp+58h+spStream.p], 0
0x180038b8d  mov     [rsi], rax
0x180038b90  lea     pTaskHandlerStatus, [rsp+58h+spStream]; this
0x180038b95  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180038b9a  mov     eax, ebx
0x180038b9c  mov     pTaskHandlerStatus, [rsp+58h+var_20]
0x180038ba1  xor     pTaskHandlerStatus, rsp; StackCookie
0x180038ba4  call    __security_check_cookie
0x180038ba9  mov     rbx, [rsp+58h+arg_8]
0x180038bae  add     rsp, 40h
0x180038bb2  pop     r15
0x180038bb4  pop     rdi
0x180038bb5  pop     rsi
0x180038bb6  retn
```
