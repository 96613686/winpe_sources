# AutoStubBias<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler>::AutoStubBias<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler>(IRpcOptions *,Windows::Foundation::IAsyncAction *,Windows::Foundation::IAsyncActionCompletedHandler *)

- ea: `0x100a1148`
- end: `0x100a11a0`
- name: `??0?$AutoStubBias@UIAsyncAction@Foundation@Windows@@UIAsyncActionCompletedHandler@23@@@QAE@PAUIRpcOptions@@PAUIAsyncAction@Foundation@Windows@@PAUIAsyncActionCompletedHandler@34@@Z`
- size: `88`
- prototype: `AutoStubBias<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler> *__thiscall(AutoStubBias<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler> *this, IRpcOptions *pRpcOptions, Windows::Foundation::IAsyncAction *stubInterface, Windows::Foundation::IAsyncActionCompletedHandler *delegateInterface)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x100a2140`
- `0x100b1d00`

## callees

- `0x10073a99`
- `0x100a1148`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x100a116b`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x100a116b`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x100a1186`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x100a1186`

## pseudocode

```c
AutoStubBias<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler> *__thiscall AutoStubBias<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler>::AutoStubBias<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler>(
        AutoStubBias<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler> *this,
        IRpcOptions *pRpcOptions,
        Windows::Foundation::IAsyncAction *stubInterface,
        Windows::Foundation::IAsyncActionCompletedHandler *delegateInterface)
{
  int StreamOnHGlobal; // eax

  this->spStream_.ptr_ = 0;
  this->hr_ = 0;
  if ( pRpcOptions && delegateInterface )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)this);
    StreamOnHGlobal = CreateStreamOnHGlobal(0, 1, &this->spStream_.ptr_);
    this->hr_ = StreamOnHGlobal;
    if ( StreamOnHGlobal >= 0 )
      this->hr_ = CoMarshalInterface(
                    this->spStream_.ptr_,
                    &_GUID_00000000_0000_0000_c000_000000000046,
                    stubInterface,
                    0,
                    0,
                    1u);
  }
  else
  {
    this->hr_ = -2147467262;
  }
  return this;
}

```

## disassembly

```asm
0x100a1148  mov     edi, edi
0x100a114a  push    ebp
0x100a114b  mov     ebp, esp
0x100a114d  push    esi
0x100a114e  mov     esi, this
0x100a1150  push    edi
0x100a1151  xor     edi, edi
0x100a1153  mov     [esi], edi
0x100a1155  mov     [esi+4], edi
0x100a1158  cmp     [ebp+pRpcOptions], edi
0x100a115b  jz      short loc_100A1191
0x100a115d  cmp     [ebp+delegateInterface], edi
0x100a1160  jz      short loc_100A1191
0x100a1162  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x100a1167  push    esi; ppstm
0x100a1168  push    1; fDeleteOnRelease
0x100a116a  push    edi; hGlobal
0x100a116b  call    ds:__imp__CreateStreamOnHGlobal@12; CreateStreamOnHGlobal(x,x,x)
0x100a1171  mov     [esi+4], eax
0x100a1174  test    eax, eax
0x100a1176  js      short loc_100A1198
0x100a1178  push    1; mshlflags
0x100a117a  push    edi; pvDestContext
0x100a117b  push    edi; dwDestContext
0x100a117c  push    [ebp+stubInterface]; pUnk
0x100a117f  push    offset __GUID_00000000_0000_0000_c000_000000000046; riid
0x100a1184  push    dword ptr [esi]; pStm
0x100a1186  call    ds:__imp__CoMarshalInterface@24; CoMarshalInterface(x,x,x,x,x,x)
0x100a118c  mov     [esi+4], eax
0x100a118f  jmp     short loc_100A1198
0x100a1191  mov     dword ptr [esi+4], 80004002h
0x100a1198  pop     edi
0x100a1199  mov     eax, esi
0x100a119b  pop     esi
0x100a119c  pop     ebp
0x100a119d  retn    0Ch
```
