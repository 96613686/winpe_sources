# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>,Microsoft::WRL::FtmBase>::AddRef(void)

- ea: `0x140004fa0`
- end: `0x140004fc9`
- name: `?AddRef@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationCompletedHandler@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `41`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140004fd0`

## callees

- `0x140004fa0`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>,Microsoft::WRL::FtmBase>::AddRef(
        __int64 a1)
{
  unsigned int v1; // r9d
  signed __int32 v2; // r8d

  v1 = 0x7FFFFFFF;
  while ( 1 )
  {
    v2 = *(_DWORD *)(a1 + 44);
    if ( v2 == 0x7FFFFFFF )
      break;
    if ( v2 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 44), v2 + 1, v2) )
      return (unsigned int)(v2 + 1);
  }
  return v1;
}

```

## disassembly

```asm
0x140004fa0  mov     r9d, 7FFFFFFFh
0x140004fa6  jmp     short loc_140004FB6
0x140004fa8  lea     edx, [r8+1]
0x140004fac  mov     eax, r8d
0x140004faf  lock cmpxchg [rcx+2Ch], edx
0x140004fb4  jz      short loc_140004FC1
0x140004fb6  mov     r8d, [rcx+2Ch]
0x140004fba  cmp     r8d, r9d
0x140004fbd  jnz     short loc_140004FA8
0x140004fbf  jmp     short loc_140004FC5
0x140004fc1  lea     r9d, [r8+1]
0x140004fc5  mov     eax, r9d
0x140004fc8  retn
```
