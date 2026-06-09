# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>,Microsoft::WRL::FtmBase>::Release(void)

- ea: `0x14000afa0`
- end: `0x14000b002`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationCompletedHandler@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `98`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14000b010`

## callees

- `0x14000afa0`
- `0x14001a010`

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
0x14000afa0  push    rbx
0x14000afa2  sub     rsp, 20h
0x14000afa6  mov     r9d, 7FFFFFFFh
0x14000afac  jmp     short loc_14000AFBC
0x14000afae  lea     edx, [r8-1]
0x14000afb2  mov     eax, r8d
0x14000afb5  lock cmpxchg [rcx+2Ch], edx
0x14000afba  jz      short loc_14000AFC5
0x14000afbc  mov     r8d, [rcx+2Ch]
0x14000afc0  cmp     r8d, r9d
0x14000afc3  jnz     short loc_14000AFAE
0x14000afc5  lea     ebx, [r8-1]
0x14000afc9  test    ebx, ebx
0x14000afcb  jnz     short loc_14000AFF9
0x14000afcd  test    rcx, rcx
0x14000afd0  jz      short loc_14000AFE1
0x14000afd2  mov     rax, [rcx]
0x14000afd5  lea     edx, [rbx+1]
0x14000afd8  mov     rax, [rax+20h]
0x14000afdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000afe1  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x14000afe8  test    rcx, rcx
0x14000afeb  jz      short loc_14000AFF9
0x14000afed  mov     rdx, [rcx]
0x14000aff0  mov     rax, [rdx+10h]
0x14000aff4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000aff9  mov     eax, ebx
0x14000affb  add     rsp, 20h
0x14000afff  pop     rbx
0x14000b000  retn
```
