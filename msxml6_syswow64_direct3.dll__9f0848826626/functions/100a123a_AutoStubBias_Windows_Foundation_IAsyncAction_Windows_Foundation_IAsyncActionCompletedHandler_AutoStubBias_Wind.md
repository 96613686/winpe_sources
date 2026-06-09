# AutoStubBias<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler>::AutoStubBias<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler>(IRpcOptions *,Windows::Foundation::IAsyncAction *,Windows::Foundation::IAsyncActionCompletedHandler *)

- ea: `0x100a123a`
- end: `0x100a1292`
- name: `??0?$AutoStubBias@UIAsyncAction@Foundation@Windows@@UIAsyncActionCompletedHandler@23@@@QAE@PAUIRpcOptions@@PAUIAsyncAction@Foundation@Windows@@PAUIAsyncActionCompletedHandler@34@@Z`
- size: `88`
- prototype: `AutoStubBias<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler> *__thiscall(AutoStubBias<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler> *this, IRpcOptions *pRpcOptions, Windows::Foundation::IAsyncAction *stubInterface, Windows::Foundation::IAsyncActionCompletedHandler *delegateInterface)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x100a2250`
- `0x100b1e10`

## callees

- `0x10073ac9`
- `0x100a123a`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x100a125d`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x100a125d`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x100a1278`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x100a1278`

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
0x100a123a  mov     edi, edi
0x100a123c  push    ebp
0x100a123d  mov     ebp, esp
0x100a123f  push    esi
0x100a1240  mov     esi, this
0x100a1242  push    edi
0x100a1243  xor     edi, edi
0x100a1245  mov     [esi], edi
0x100a1247  mov     [esi+4], edi
0x100a124a  cmp     [ebp+pRpcOptions], edi
0x100a124d  jz      short loc_100A1283
0x100a124f  cmp     [ebp+delegateInterface], edi
0x100a1252  jz      short loc_100A1283
0x100a1254  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x100a1259  push    esi; ppstm
0x100a125a  push    1; fDeleteOnRelease
0x100a125c  push    edi; hGlobal
0x100a125d  call    ds:__imp__CreateStreamOnHGlobal@12; CreateStreamOnHGlobal(x,x,x)
0x100a1263  mov     [esi+4], eax
0x100a1266  test    eax, eax
0x100a1268  js      short loc_100A128A
0x100a126a  push    1; mshlflags
0x100a126c  push    edi; pvDestContext
0x100a126d  push    edi; dwDestContext
0x100a126e  push    [ebp+stubInterface]; pUnk
0x100a1271  push    offset __GUID_00000000_0000_0000_c000_000000000046; riid
0x100a1276  push    dword ptr [esi]; pStm
0x100a1278  call    ds:__imp__CoMarshalInterface@24; CoMarshalInterface(x,x,x,x,x,x)
0x100a127e  mov     [esi+4], eax
0x100a1281  jmp     short loc_100A128A
0x100a1283  mov     dword ptr [esi+4], 80004002h
0x100a128a  pop     edi
0x100a128b  mov     eax, esi
0x100a128d  pop     esi
0x100a128e  pop     ebp
0x100a128f  retn    0Ch
```
