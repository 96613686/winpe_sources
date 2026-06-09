# OleStartDragOperationInternal

- ea: `0x180095c30`
- end: `0x180095dfc`
- name: `OleStartDragOperationInternal`
- size: `460`
- prototype: `HRESULT __fastcall(IDataObject *pDataObject, int fCallerIsBroker, unsigned int dwOKEffects, IDragOperationInternal **ppDragOperation, int fWinRTDrag)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800959c0`

## callees

- `0x180005744`
- `0x18000a0e8`
- `0x18000c3dc`
- `0x1800470fc`
- `0x180052390`
- `0x18008e468`
- `0x18009595c`
- `0x180095c30`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095d24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095d24`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180095d03`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180095d03`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180095d42`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180095d4c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180095dc5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180095d42`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180095d4c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180095dc5`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180095d1a`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180095d1a`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x180095cb7`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x180095cb7`

## pseudocode

```c
__int64 __fastcall OleStartDragOperationInternal(
        IDataObject *pDataObject,
        int fCallerIsBroker,
        const _GUID *dwOKEffects,
        IDragOperationInternal **ppDragOperation,
        int fWinRTDrag)
{
  int v7; // ebx
  signed int LastError; // eax
  _MCGEN_TRACE_CONTEXT *v9; // rcx
  Microsoft::WRL::ComPtr<ITypeLibRegistrationReader> fBackgroundContainerDrag; // [rsp+40h] [rbp-11h] BYREF
  void *hPrimaryToken; // [rsp+48h] [rbp-9h] BYREF
  void *hProcess; // [rsp+50h] [rbp-1h] BYREF
  unsigned int v14; // [rsp+58h] [rbp+7h] BYREF
  void *hToken; // [rsp+60h] [rbp+Fh] BYREF
  IDataObject *v16; // [rsp+68h] [rbp+17h] BYREF
  _EVENT_DATA_DESCRIPTOR Descriptor; // [rsp+70h] [rbp+1Fh] BYREF

  *ppDragOperation = 0;
  v16 = pDataObject;
  v14 = (unsigned int)dwOKEffects;
  if ( (Microsoft_Windows_OLE_PerfEnableBits[0] & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(
      (_MCGEN_TRACE_CONTEXT *)pDataObject,
      &OLE_DragDrop_CreateDragOperationInternal_Start,
      dwOKEffects,
      1u,
      &Descriptor);
  hToken = 0;
  RegisterOLEAtoms();
  if ( !fCallerIsBroker )
    goto LABEL_14;
  fBackgroundContainerDrag.ptr_ = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&fBackgroundContainerDrag);
  v7 = CoGetCallContext(&GUID_68c6a1b9_de39_42c3_8d28_bf40a5126541, (void **)&fBackgroundContainerDrag.ptr_);
  if ( v7 >= 0 )
  {
    hProcess = 0;
    v7 = ((__int64 (__fastcall *)(ITypeLibRegistrationReader *, __int64, void **))fBackgroundContainerDrag.ptr_->lpVtbl[1].QueryInterface)(
           fBackgroundContainerDrag.ptr_,
           4096,
           &hProcess);
    if ( v7 >= 0 )
    {
      hPrimaryToken = 0;
      if ( !OpenProcessToken(hProcess, 0xEu, &hPrimaryToken)
        || !DuplicateToken(hPrimaryToken, SecurityImpersonation, &hToken) )
      {
        LastError = GetLastError();
        v7 = LastError;
        if ( LastError > 0 )
          v7 = (unsigned __int16)LastError | 0x80070000;
      }
      if ( hPrimaryToken )
        CloseHandle(hPrimaryToken);
      CloseHandle(hProcess);
    }
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&fBackgroundContainerDrag);
  if ( v7 >= 0 )
  {
LABEL_14:
    LODWORD(fBackgroundContainerDrag.ptr_) = IsContainerDragOperation();
    hPrimaryToken = 0;
    hProcess = &hToken;
    Descriptor.Ptr = 0;
    v7 = Microsoft::WRL::Details::MakeAndInitialize<CDragOperation,IDragOperationInternal,IDataObject * &,std::nullptr_t,unsigned long &,std::nullptr_t,int &,void * *,int &>(
           ppDragOperation,
           &v16,
           (__int16 *)&Descriptor,
           &v14,
           (__int16 *)&hPrimaryToken,
           &fWinRTDrag,
           (void ***)&hProcess,
           (int *)&fBackgroundContainerDrag);
  }
  v9 = (_MCGEN_TRACE_CONTEXT *)hToken;
  if ( hToken )
    CloseHandle(hToken);
  if ( (Microsoft_Windows_OLE_PerfEnableBits[0] & 1) != 0 )
    McTemplateU0d_EventWriteTransfer(v9, &OLE_DragDrop_CreateDragOperationInternal_Stop, v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180095c30  push    rbp
0x180095c32  push    rbx
0x180095c33  push    rdi
0x180095c34  lea     rbp, [rsp-3Fh]
0x180095c39  sub     rsp, 90h
0x180095c40  mov     rax, cs:__security_cookie
0x180095c47  xor     rax, rsp
0x180095c4a  mov     [rbp+4Fh+var_20], rax
0x180095c4e  mov     qword ptr [ppDragOperation], 0
0x180095c55  mov     rdi, ppDragOperation
0x180095c58  test    byte ptr cs:Microsoft_Windows_OLE_PerfEnableBits, 1
0x180095c5f  mov     ebx, fCallerIsBroker
0x180095c61  mov     [rbp+4Fh+var_38], pDataObject
0x180095c65  mov     [rbp+4Fh+var_48], dwOKEffects
0x180095c69  jz      short loc_180095C86
0x180095c6b  lea     rax, [rbp+4Fh+var_30]
0x180095c6f  mov     r9d, 1; Context
0x180095c75  lea     rdx, OLE_DragDrop_CreateDragOperationInternal_Start; EventDataCount
0x180095c7c  mov     [rsp+0A0h+Descriptor], rax; Descriptor
0x180095c81  call    McGenEventWrite_EventWriteTransfer
0x180095c86  mov     [rbp+4Fh+hToken], 0
0x180095c8e  call    ?RegisterOLEAtoms@@YAXXZ; RegisterOLEAtoms(void)
0x180095c93  test    ebx, ebx
0x180095c95  jz      loc_180095D5F
0x180095c9b  lea     pDataObject, [rbp+4Fh+fBackgroundContainerDrag]; this
0x180095c9f  mov     [rbp+4Fh+fBackgroundContainerDrag], 0
0x180095ca7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180095cac  lea     rdx, [rbp+4Fh+fBackgroundContainerDrag]; ppInterface
0x180095cb0  lea     pDataObject, _GUID_68c6a1b9_de39_42c3_8d28_bf40a5126541; riid
0x180095cb7  call    cs:__imp_CoGetCallContext
0x180095cbd  mov     ebx, eax
0x180095cbf  test    eax, eax
0x180095cc1  js      loc_180095D52
0x180095cc7  mov     pDataObject, [rbp+4Fh+fBackgroundContainerDrag]
0x180095ccb  lea     r8, [rbp+4Fh+hProcess]
0x180095ccf  mov     [rbp+4Fh+hProcess], 0
0x180095cd7  mov     fCallerIsBroker, 1000h
0x180095cdc  mov     rax, [pDataObject]
0x180095cdf  mov     rax, [rax+18h]
0x180095ce3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095ce8  mov     ebx, eax
0x180095cea  test    eax, eax
0x180095cec  js      short loc_180095D52
0x180095cee  mov     pDataObject, [rbp+4Fh+hProcess]; ProcessHandle
0x180095cf2  lea     r8, [rbp+4Fh+hPrimaryToken]; TokenHandle
0x180095cf6  mov     fCallerIsBroker, 0Eh; DesiredAccess
0x180095cfb  mov     [rbp+4Fh+hPrimaryToken], 0
0x180095d03  call    cs:__imp_OpenProcessToken
0x180095d09  test    eax, eax
0x180095d0b  jz      short loc_180095D24
0x180095d0d  mov     pDataObject, [rbp+4Fh+hPrimaryToken]; ExistingTokenHandle
0x180095d11  lea     r8, [rbp+4Fh+hToken]; DuplicateTokenHandle
0x180095d15  mov     fCallerIsBroker, 2; ImpersonationLevel
0x180095d1a  call    cs:__imp_DuplicateToken
0x180095d20  test    eax, eax
0x180095d22  jnz     short loc_180095D39
0x180095d24  call    cs:__imp_GetLastError
0x180095d2a  mov     ebx, eax
0x180095d2c  test    eax, eax
0x180095d2e  jle     short loc_180095D39
0x180095d30  movzx   ebx, ax
0x180095d33  or      ebx, 80070000h
0x180095d39  mov     pDataObject, [rbp+4Fh+hPrimaryToken]; hObject
0x180095d3d  test    pDataObject, pDataObject
0x180095d40  jz      short loc_180095D48
0x180095d42  call    cs:__imp_CloseHandle
0x180095d48  mov     pDataObject, [rbp+4Fh+hProcess]; hObject
0x180095d4c  call    cs:__imp_CloseHandle
0x180095d52  lea     pDataObject, [rbp+4Fh+fBackgroundContainerDrag]; this
0x180095d56  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180095d5b  test    ebx, ebx
0x180095d5d  js      short loc_180095DBC
0x180095d5f  call    ?IsContainerDragOperation@@YA_NXZ; IsContainerDragOperation(void)
0x180095d64  movzx   eax, al
0x180095d67  lea     ppDragOperation, [rbp+4Fh+var_48]; <args_2>
0x180095d6b  mov     dword ptr [rbp+4Fh+fBackgroundContainerDrag], eax
0x180095d6e  lea     r8, [rbp+4Fh+var_30]; <args_1>
0x180095d72  lea     rax, [rbp+4Fh+hToken]
0x180095d76  mov     [rbp+4Fh+hPrimaryToken], 0
0x180095d7e  mov     [rbp+4Fh+hProcess], rax
0x180095d82  lea     rdx, [rbp+4Fh+var_38]; <args_0>
0x180095d86  lea     rax, [rbp+4Fh+fBackgroundContainerDrag]
0x180095d8a  mov     [rbp+4Fh+var_30.Ptr], 0
0x180095d92  mov     [rsp+0A0h+var_68], rax; <args_6>
0x180095d97  mov     pDataObject, rdi; result
0x180095d9a  lea     rax, [rbp+4Fh+hProcess]
0x180095d9e  mov     [rsp+0A0h+var_70], rax; <args_5>
0x180095da3  lea     rax, [rbp+4Fh+arg_20]
0x180095da7  mov     [rsp+0A0h+var_78], rax; <args_4>
0x180095dac  lea     rax, [rbp+4Fh+hPrimaryToken]
0x180095db0  mov     [rsp+0A0h+Descriptor], rax; <args_3>
0x180095db5  call    ??$MakeAndInitialize@VCDragOperation@@UIDragOperationInternal@@AEAPEAUIDataObject@@$$TAEAK$$TAEAHPEAPEAXAEAH@Details@WRL@Microsoft@@YAJPEAPEAUIDragOperationInternal@@AEAPEAUIDataObject@@$$QEA$$TAEAK2AEAH$$QEAPEAPEAX4@Z
0x180095dba  mov     ebx, eax
0x180095dbc  mov     pDataObject, [rbp+4Fh+hToken]; hObject
0x180095dc0  test    pDataObject, pDataObject
0x180095dc3  jz      short loc_180095DCB
0x180095dc5  call    cs:__imp_CloseHandle
0x180095dcb  test    byte ptr cs:Microsoft_Windows_OLE_PerfEnableBits, 1
0x180095dd2  jz      short loc_180095DE3
0x180095dd4  mov     dwOKEffects, ebx; Context
0x180095dd7  lea     rdx, OLE_DragDrop_CreateDragOperationInternal_Stop; _Arg0
0x180095dde  call    McTemplateU0d_EventWriteTransfer
0x180095de3  mov     eax, ebx
0x180095de5  mov     pDataObject, [rbp+4Fh+var_20]
0x180095de9  xor     pDataObject, rsp; StackCookie
0x180095dec  call    __security_check_cookie
0x180095df1  add     rsp, 90h
0x180095df8  pop     rdi
0x180095df9  pop     rbx
0x180095dfa  pop     rbp
0x180095dfb  retn
```
