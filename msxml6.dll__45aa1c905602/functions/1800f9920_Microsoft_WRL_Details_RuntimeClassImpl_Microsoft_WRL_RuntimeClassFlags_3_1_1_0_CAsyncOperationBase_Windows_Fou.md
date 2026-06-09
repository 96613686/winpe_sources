# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,CAsyncOperationBase<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,&ushort const near * const SaveToFileAsyncOperationName>>::GetIids(ulong *,_GUID * *)

- ea: `0x1800f9920`
- end: `0x1800f999a`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@V?$CAsyncOperationBase@UIAsyncAction@Foundation@Windows@@UIAsyncActionCompletedHandler@23@$1?SaveToFileAsyncOperationName@@3QBGB@@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `122`
- prototype: `HRESULT __fastcall(SaveWorkItem *this, unsigned int *iidCount, _GUID **iids)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800f99a0`

## callees

- `0x1800f95e0`
- `0x1800f9920`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800f9942`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800f9942`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,CAsyncOperationBase<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,&unsigned short const near * const SaveToFileAsyncOperationName>>::GetIids(
        SaveWorkItem *this,
        unsigned int *iidCount,
        _GUID **iids)
{
  Microsoft::WRL::Implements<Windows::Foundation::IAsyncAction,Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::AsyncCausalityOptions<&SaveToFileAsyncOperationName,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > > *v5; // rcx
  _GUID *v6; // r8
  __int64 result; // rax
  _GUID *v8; // r8
  unsigned int index; // [rsp+38h] [rbp+10h] BYREF

  *iids = 0;
  *iidCount = 0;
  v6 = (_GUID *)CoTaskMemAlloc(0x30u);
  if ( !v6 )
    return 2147942414LL;
  index = 0;
  Microsoft::WRL::Implements<Windows::Foundation::IAsyncAction,Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const SaveToFileAsyncOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>::FillArrayWithIid(
    v5,
    &index,
    v6);
  result = 0;
  v8[index] = GUID_00000038_0000_0000_c000_000000000046;
  *iidCount = 3;
  *iids = v8;
  return result;
}

```

## disassembly

```asm
0x1800f9920  mov     [rsp+arg_0], rbx
0x1800f9925  push    rdi
0x1800f9926  sub     rsp, 20h
0x1800f992a  mov     qword ptr [iids], 0
0x1800f9931  mov     ecx, 30h ; '0'; cb
0x1800f9936  mov     dword ptr [iidCount], 0
0x1800f993c  mov     rbx, iids
0x1800f993f  mov     rdi, iidCount
0x1800f9942  call    cs:__imp_CoTaskMemAlloc
0x1800f9949  nop     dword ptr [rax+rax+00h]
0x1800f994e  mov     iids, rax; iids
0x1800f9951  test    rax, rax
0x1800f9954  jnz     short loc_1800F995D
0x1800f9956  mov     eax, 8007000Eh
0x1800f995b  jmp     short loc_1800F998E
0x1800f995d  lea     iidCount, [rsp+28h+index]; index
0x1800f9962  mov     [rsp+28h+index], 0
0x1800f996a  call    ?FillArrayWithIid@?$Implements@UIAsyncAction@Foundation@Windows@@V?$AsyncBaseFTM@UIAsyncActionCompletedHandler@Foundation@Windows@@$00U?$AsyncCausalityOptions@$1?SaveToFileAsyncOperationName@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@3@@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Implements<Windows::Foundation::IAsyncAction,Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const SaveToFileAsyncOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>::FillArrayWithIid(ulong *,_GUID *)
0x1800f996f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x1800f9976  mov     edx, [rsp+28h+index]
0x1800f997a  add     iidCount, iidCount
0x1800f997d  xor     eax, eax
0x1800f997f  movdqu  xmmword ptr [iids+iidCount*8], xmm1
0x1800f9985  mov     dword ptr [rdi], 3
0x1800f998b  mov     [rbx], iids
0x1800f998e  mov     rbx, [rsp+28h+arg_0]
0x1800f9993  add     rsp, 20h
0x1800f9997  pop     rdi
0x1800f9998  retn
```
