# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>,Microsoft::WRL::FtmBase>::Release(void)

- ea: `0x14000acb0`
- end: `0x14000ad11`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationCompletedHandler@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `97`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14000ad20`

## callees

- `0x14000acb0`
- `0x140019010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>,Microsoft::WRL::FtmBase>::Release(
        volatile signed __int32 *a1)
{
  __int64 v1; // r9
  __int64 v2; // r8
  unsigned int v3; // ebx

  v1 = 0x7FFFFFFF;
  do
    v2 = *((unsigned int *)a1 + 11);
  while ( (_DWORD)v2 != 0x7FFFFFFF && (_DWORD)v2 != _InterlockedCompareExchange(a1 + 11, v2 - 1, v2) );
  v3 = v2 - 1;
  if ( (_DWORD)v2 == 1 )
  {
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int32 *, __int64, __int64, __int64))(*(_QWORD *)a1 + 32LL))(
        a1,
        1,
        v2,
        0x7FFFFFFF);
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *, _QWORD, __int64, __int64))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_ + 16LL))(
        Microsoft::WRL::Details::ModuleBase::module_,
        *(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_,
        v2,
        v1);
  }
  return v3;
}

```

## disassembly

```asm
0x14000acb0  push    rbx
0x14000acb2  sub     rsp, 20h
0x14000acb6  mov     r9d, 7FFFFFFFh
0x14000acbc  jmp     short loc_14000ACCC
0x14000acbe  lea     edx, [r8-1]
0x14000acc2  mov     eax, r8d
0x14000acc5  lock cmpxchg [rcx+2Ch], edx
0x14000acca  jz      short loc_14000ACD5
0x14000accc  mov     r8d, [rcx+2Ch]
0x14000acd0  cmp     r8d, r9d
0x14000acd3  jnz     short loc_14000ACBE
0x14000acd5  lea     ebx, [r8-1]
0x14000acd9  test    ebx, ebx
0x14000acdb  jnz     short loc_14000AD09
0x14000acdd  test    rcx, rcx
0x14000ace0  jz      short loc_14000ACF1
0x14000ace2  mov     rax, [rcx]
0x14000ace5  lea     edx, [rbx+1]
0x14000ace8  mov     rax, [rax+20h]
0x14000acec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000acf1  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x14000acf8  test    rcx, rcx
0x14000acfb  jz      short loc_14000AD09
0x14000acfd  mov     rdx, [rcx]
0x14000ad00  mov     rax, [rdx+10h]
0x14000ad04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ad09  mov     eax, ebx
0x14000ad0b  add     rsp, 20h
0x14000ad0f  pop     rbx
0x14000ad10  retn
```
