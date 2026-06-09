# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,CAsyncOperationBase<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,&ushort const near * const SaveToFileAsyncOperationName>>::GetIids(ulong *,_GUID * *)

- ea: `0x1800f73c0`
- end: `0x1800f7433`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@V?$CAsyncOperationBase@UIAsyncAction@Foundation@Windows@@UIAsyncActionCompletedHandler@23@$1?SaveToFileAsyncOperationName@@3QBGB@@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `115`
- prototype: `HRESULT __fastcall(SaveWorkItem *this, unsigned int *iidCount, _GUID **iids)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800f7440`

## callees

- `0x1800f7084`
- `0x1800f73c0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800f73e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800f73e2`

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
0x1800f73c0  mov     [rsp+arg_0], rbx
0x1800f73c5  push    rdi
0x1800f73c6  sub     rsp, 20h
0x1800f73ca  mov     qword ptr [iids], 0
0x1800f73d1  mov     ecx, 30h ; '0'; cb
0x1800f73d6  mov     dword ptr [iidCount], 0
0x1800f73dc  mov     rbx, iids
0x1800f73df  mov     rdi, iidCount
0x1800f73e2  call    cs:__imp_CoTaskMemAlloc
0x1800f73e8  mov     iids, rax; iids
0x1800f73eb  test    rax, rax
0x1800f73ee  jnz     short loc_1800F73F7
0x1800f73f0  mov     eax, 8007000Eh
0x1800f73f5  jmp     short loc_1800F7428
0x1800f73f7  lea     iidCount, [rsp+28h+index]; index
0x1800f73fc  mov     [rsp+28h+index], 0
0x1800f7404  call    ?FillArrayWithIid@?$Implements@UIAsyncAction@Foundation@Windows@@V?$AsyncBaseFTM@UIAsyncActionCompletedHandler@Foundation@Windows@@$00U?$AsyncCausalityOptions@$1?SaveToFileAsyncOperationName@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@3@@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Implements<Windows::Foundation::IAsyncAction,Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const SaveToFileAsyncOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>::FillArrayWithIid(ulong *,_GUID *)
0x1800f7409  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x1800f7410  mov     edx, [rsp+28h+index]
0x1800f7414  add     iidCount, iidCount
0x1800f7417  xor     eax, eax
0x1800f7419  movdqu  xmmword ptr [iids+iidCount*8], xmm1
0x1800f741f  mov     dword ptr [rdi], 3
0x1800f7425  mov     [rbx], iids
0x1800f7428  mov     rbx, [rsp+28h+arg_0]
0x1800f742d  add     rsp, 20h
0x1800f7431  pop     rdi
0x1800f7432  retn
```
