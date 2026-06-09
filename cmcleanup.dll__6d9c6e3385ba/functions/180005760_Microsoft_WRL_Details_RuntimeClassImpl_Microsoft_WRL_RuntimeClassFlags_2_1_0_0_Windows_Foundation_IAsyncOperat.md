# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>,Microsoft::WRL::FtmBase>::Release(void)

- ea: `0x180005760`
- end: `0x1800057c1`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `97`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800057d0`

## callees

- `0x180005760`
- `0x180009010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>,Microsoft::WRL::FtmBase>::Release(
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
0x180005760  push    rbx
0x180005762  sub     rsp, 20h
0x180005766  mov     r9d, 7FFFFFFFh
0x18000576c  jmp     short loc_18000577C
0x18000576e  lea     edx, [r8-1]
0x180005772  mov     eax, r8d
0x180005775  lock cmpxchg [rcx+2Ch], edx
0x18000577a  jz      short loc_180005785
0x18000577c  mov     r8d, [rcx+2Ch]
0x180005780  cmp     r8d, r9d
0x180005783  jnz     short loc_18000576E
0x180005785  lea     ebx, [r8-1]
0x180005789  test    ebx, ebx
0x18000578b  jnz     short loc_1800057B9
0x18000578d  test    rcx, rcx
0x180005790  jz      short loc_1800057A1
0x180005792  mov     rax, [rcx]
0x180005795  lea     edx, [rbx+1]
0x180005798  mov     rax, [rax+20h]
0x18000579c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057a1  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800057a8  test    rcx, rcx
0x1800057ab  jz      short loc_1800057B9
0x1800057ad  mov     rdx, [rcx]
0x1800057b0  mov     rax, [rdx+10h]
0x1800057b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057b9  mov     eax, ebx
0x1800057bb  add     rsp, 20h
0x1800057bf  pop     rbx
0x1800057c0  retn
```
