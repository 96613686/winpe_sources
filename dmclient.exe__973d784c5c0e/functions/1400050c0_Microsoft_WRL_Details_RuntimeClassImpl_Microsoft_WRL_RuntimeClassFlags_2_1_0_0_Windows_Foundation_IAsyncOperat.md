# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>,Microsoft::WRL::FtmBase>::AddRef(void)

- ea: `0x1400050c0`
- end: `0x1400050e9`
- name: `?AddRef@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationCompletedHandler@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `41`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1400050f0`

## callees

- `0x1400050c0`

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
0x1400050c0  mov     r9d, 7FFFFFFFh
0x1400050c6  jmp     short loc_1400050D6
0x1400050c8  lea     edx, [r8+1]
0x1400050cc  mov     eax, r8d
0x1400050cf  lock cmpxchg [rcx+2Ch], edx
0x1400050d4  jz      short loc_1400050E1
0x1400050d6  mov     r8d, [rcx+2Ch]
0x1400050da  cmp     r8d, r9d
0x1400050dd  jnz     short loc_1400050C8
0x1400050df  jmp     short loc_1400050E5
0x1400050e1  lea     r9d, [r8+1]
0x1400050e5  mov     eax, r9d
0x1400050e8  retn
```
