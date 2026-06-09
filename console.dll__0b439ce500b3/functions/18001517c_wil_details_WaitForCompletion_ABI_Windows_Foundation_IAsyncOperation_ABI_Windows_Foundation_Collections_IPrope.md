# `wil::details::WaitForCompletion<ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Foundation::Collections::IPropertySet *> *>(ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Foundation::Collections::IPropertySet *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::~CompletionDelegate(void)

- ea: `0x18001517c`
- end: `0x1800151a3`
- name: `??1CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAUIPropertySet@Collections@Foundation@Windows@ABI@@@Foundation@Windows@ABI@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAUIPropertySet@Collections@Foundation@Windows@ABI@@@Foundation@Windows@ABI@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@UEAA@XZ`
- size: `39`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800152b0`

## callees

- `0x180003c24`
- `0x180004dcc`

## pseudocode

```c
__int64 __fastcall `wil::details::WaitForCompletion<ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Foundation::Collections::IPropertySet *> *>'::`2'::CompletionDelegate::~CompletionDelegate(
        __int64 a1)
{
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(a1 + 56);
  *(_DWORD *)(a1 + 44) = -1073741823;
  return Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)(a1 + 32));
}

```

## disassembly

```asm
0x18001517c  push    rbx
0x18001517e  sub     rsp, 20h
0x180015182  mov     rbx, rcx
0x180015185  add     rcx, 38h ; '8'
0x180015189  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001518e  lea     rcx, [rbx+20h]
0x180015192  mov     dword ptr [rbx+2Ch], 0C0000001h
0x180015199  add     rsp, 20h
0x18001519d  pop     rbx
0x18001519e  jmp     ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
```
