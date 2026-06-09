# OleStartDragOperationInternal

- ea: `0x180094930`
- end: `0x180094b12`
- name: `OleStartDragOperationInternal`
- size: `482`
- prototype: `HRESULT __fastcall(IDataObject *pDataObject, int fCallerIsBroker, unsigned int dwOKEffects, IDragOperationInternal **ppDragOperation, int fWinRTDrag)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800946b0`

## callees

- `0x1800085a8`
- `0x18000a690`
- `0x18001d12c`
- `0x180046460`
- `0x1800899e4`
- `0x1800921cc`
- `0x18009464c`
- `0x180094930`
- `0x1800d8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094a27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094a27`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800949fa`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800949fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180094a4b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180094a5b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180094ad4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180094a4b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180094a5b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180094ad4`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180094a17`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180094a17`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x1800949ae`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x1800949ae`

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
  bool v9; // al
  _MCGEN_TRACE_CONTEXT *v10; // rcx
  Microsoft::WRL::ComPtr<ITypeLibRegistrationReader> fBackgroundContainerDrag; // [rsp+40h] [rbp-11h] BYREF
  void *hPrimaryToken; // [rsp+48h] [rbp-9h] BYREF
  void *hProcess; // [rsp+50h] [rbp-1h] BYREF
  unsigned int v15; // [rsp+58h] [rbp+7h] BYREF
  void *hToken; // [rsp+60h] [rbp+Fh] BYREF
  IDataObject *v17; // [rsp+68h] [rbp+17h] BYREF
  _EVENT_DATA_DESCRIPTOR Descriptor; // [rsp+70h] [rbp+1Fh] BYREF

  *ppDragOperation = 0;
  v17 = pDataObject;
  v15 = (unsigned int)dwOKEffects;
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
    v9 = IsContainerDragOperation();
    hPrimaryToken = 0;
    Descriptor.Ptr = 0;
    LODWORD(fBackgroundContainerDrag.ptr_) = v9;
    hProcess = &hToken;
    v7 = Microsoft::WRL::Details::MakeAndInitialize<CDragOperation,IDragOperationInternal,IDataObject * &,std::nullptr_t,unsigned long &,std::nullptr_t,int &,void * *,int &>(
           ppDragOperation,
           &v17,
           (__int16 *)&Descriptor,
           &v15,
           (__int16 *)&hPrimaryToken,
           &fWinRTDrag,
           (void ***)&hProcess,
           (int *)&fBackgroundContainerDrag);
  }
  v10 = (_MCGEN_TRACE_CONTEXT *)hToken;
  if ( hToken )
    CloseHandle(hToken);
  if ( (Microsoft_Windows_OLE_PerfEnableBits[0] & 1) != 0 )
    McTemplateU0d_EventWriteTransfer(v10, &OLE_DragDrop_CreateDragOperationInternal_Stop, v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180094930  push    rbp
0x180094932  push    rbx
0x180094933  push    rdi
0x180094934  lea     rbp, [rsp-3Fh]
0x180094939  sub     rsp, 90h
0x180094940  mov     rax, cs:__security_cookie
0x180094947  xor     rax, rsp
0x18009494a  mov     [rbp+4Fh+var_20], rax
0x18009494e  and     qword ptr [ppDragOperation], 0
0x180094952  mov     rdi, ppDragOperation
0x180094955  test    byte ptr cs:Microsoft_Windows_OLE_PerfEnableBits, 1
0x18009495c  mov     ebx, fCallerIsBroker
0x18009495e  mov     [rbp+4Fh+var_38], pDataObject
0x180094962  mov     [rbp+4Fh+var_48], dwOKEffects
0x180094966  jz      short loc_180094983
0x180094968  lea     rax, [rbp+4Fh+var_30]
0x18009496c  mov     r9d, 1; Context
0x180094972  lea     rdx, OLE_DragDrop_CreateDragOperationInternal_Start; EventDataCount
0x180094979  mov     [rsp+0A0h+Descriptor], rax; Descriptor
0x18009497e  call    McGenEventWrite_EventWriteTransfer
0x180094983  and     [rbp+4Fh+hToken], 0
0x180094988  call    ?RegisterOLEAtoms@@YAXXZ; RegisterOLEAtoms(void)
0x18009498d  test    ebx, ebx
0x18009498f  jz      loc_180094A74
0x180094995  and     [rbp+4Fh+fBackgroundContainerDrag], 0
0x18009499a  lea     pDataObject, [rbp+4Fh+fBackgroundContainerDrag]; this
0x18009499e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800949a3  lea     rdx, [rbp+4Fh+fBackgroundContainerDrag]; ppInterface
0x1800949a7  lea     pDataObject, _GUID_68c6a1b9_de39_42c3_8d28_bf40a5126541; riid
0x1800949ae  call    cs:__imp_CoGetCallContext
0x1800949b5  nop     dword ptr [rax+rax+00h]
0x1800949ba  mov     ebx, eax
0x1800949bc  test    eax, eax
0x1800949be  js      loc_180094A67
0x1800949c4  mov     pDataObject, [rbp+4Fh+fBackgroundContainerDrag]
0x1800949c8  lea     r8, [rbp+4Fh+hProcess]
0x1800949cc  and     [rbp+4Fh+hProcess], 0
0x1800949d1  mov     fCallerIsBroker, 1000h
0x1800949d6  mov     rax, [pDataObject]
0x1800949d9  mov     rax, [rax+18h]
0x1800949dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800949e2  mov     ebx, eax
0x1800949e4  test    eax, eax
0x1800949e6  js      short loc_180094A67
0x1800949e8  mov     pDataObject, [rbp+4Fh+hProcess]; ProcessHandle
0x1800949ec  lea     r8, [rbp+4Fh+hPrimaryToken]; TokenHandle
0x1800949f0  and     [rbp+4Fh+hPrimaryToken], 0
0x1800949f5  mov     fCallerIsBroker, 0Eh; DesiredAccess
0x1800949fa  call    cs:__imp_OpenProcessToken
0x180094a01  nop     dword ptr [rax+rax+00h]
0x180094a06  test    eax, eax
0x180094a08  jz      short loc_180094A27
0x180094a0a  mov     pDataObject, [rbp+4Fh+hPrimaryToken]; ExistingTokenHandle
0x180094a0e  lea     r8, [rbp+4Fh+hToken]; DuplicateTokenHandle
0x180094a12  mov     fCallerIsBroker, 2; ImpersonationLevel
0x180094a17  call    cs:__imp_DuplicateToken
0x180094a1e  nop     dword ptr [rax+rax+00h]
0x180094a23  test    eax, eax
0x180094a25  jnz     short loc_180094A42
0x180094a27  call    cs:__imp_GetLastError
0x180094a2e  nop     dword ptr [rax+rax+00h]
0x180094a33  mov     ebx, eax
0x180094a35  test    eax, eax
0x180094a37  jle     short loc_180094A42
0x180094a39  movzx   ebx, ax
0x180094a3c  or      ebx, 80070000h
0x180094a42  mov     pDataObject, [rbp+4Fh+hPrimaryToken]; hObject
0x180094a46  test    pDataObject, pDataObject
0x180094a49  jz      short loc_180094A57
0x180094a4b  call    cs:__imp_CloseHandle
0x180094a52  nop     dword ptr [rax+rax+00h]
0x180094a57  mov     pDataObject, [rbp+4Fh+hProcess]; hObject
0x180094a5b  call    cs:__imp_CloseHandle
0x180094a62  nop     dword ptr [rax+rax+00h]
0x180094a67  lea     pDataObject, [rbp+4Fh+fBackgroundContainerDrag]; this
0x180094a6b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180094a70  test    ebx, ebx
0x180094a72  js      short loc_180094ACB
0x180094a74  call    ?IsContainerDragOperation@@YA_NXZ; IsContainerDragOperation(void)
0x180094a79  and     [rbp+4Fh+hPrimaryToken], 0
0x180094a7e  lea     ppDragOperation, [rbp+4Fh+var_48]; <args_2>
0x180094a82  and     [rbp+4Fh+var_30.Ptr], 0
0x180094a87  lea     r8, [rbp+4Fh+var_30]; <args_1>
0x180094a8b  movzx   eax, al
0x180094a8e  lea     rdx, [rbp+4Fh+var_38]; <args_0>
0x180094a92  mov     dword ptr [rbp+4Fh+fBackgroundContainerDrag], eax
0x180094a95  mov     pDataObject, rdi; result
0x180094a98  lea     rax, [rbp+4Fh+hToken]
0x180094a9c  mov     [rbp+4Fh+hProcess], rax
0x180094aa0  lea     rax, [rbp+4Fh+fBackgroundContainerDrag]
0x180094aa4  mov     [rsp+0A0h+var_68], rax; <args_6>
0x180094aa9  lea     rax, [rbp+4Fh+hProcess]
0x180094aad  mov     [rsp+0A0h+var_70], rax; <args_5>
0x180094ab2  lea     rax, [rbp+4Fh+arg_20]
0x180094ab6  mov     [rsp+0A0h+var_78], rax; <args_4>
0x180094abb  lea     rax, [rbp+4Fh+hPrimaryToken]
0x180094abf  mov     [rsp+0A0h+Descriptor], rax; <args_3>
0x180094ac4  call    ??$MakeAndInitialize@VCDragOperation@@UIDragOperationInternal@@AEAPEAUIDataObject@@$$TAEAK$$TAEAHPEAPEAXAEAH@Details@WRL@Microsoft@@YAJPEAPEAUIDragOperationInternal@@AEAPEAUIDataObject@@$$QEA$$TAEAK2AEAH$$QEAPEAPEAX4@Z
0x180094ac9  mov     ebx, eax
0x180094acb  mov     pDataObject, [rbp+4Fh+hToken]; hObject
0x180094acf  test    pDataObject, pDataObject
0x180094ad2  jz      short loc_180094AE0
0x180094ad4  call    cs:__imp_CloseHandle
0x180094adb  nop     dword ptr [rax+rax+00h]
0x180094ae0  test    byte ptr cs:Microsoft_Windows_OLE_PerfEnableBits, 1
0x180094ae7  jz      short loc_180094AF8
0x180094ae9  mov     dwOKEffects, ebx; Context
0x180094aec  lea     rdx, OLE_DragDrop_CreateDragOperationInternal_Stop; _Arg0
0x180094af3  call    McTemplateU0d_EventWriteTransfer
0x180094af8  mov     eax, ebx
0x180094afa  mov     pDataObject, [rbp+4Fh+var_20]
0x180094afe  xor     pDataObject, rsp; StackCookie
0x180094b01  call    __security_check_cookie
0x180094b06  add     rsp, 90h
0x180094b0d  pop     rdi
0x180094b0e  pop     rbx
0x180094b0f  pop     rbp
0x180094b10  retn
```
