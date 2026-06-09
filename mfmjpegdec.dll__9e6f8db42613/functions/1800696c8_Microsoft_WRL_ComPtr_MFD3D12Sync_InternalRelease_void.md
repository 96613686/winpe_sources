# Microsoft::WRL::ComPtr<MFD3D12Sync>::InternalRelease(void)

- ea: `0x1800696c8`
- end: `0x1800696e6`
- name: `?InternalRelease@?$ComPtr@VMFD3D12Sync@@@WRL@Microsoft@@IEAAKXZ`
- size: `30`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180066d24`
- `0x180066fc0`
- `0x180069b14`
- `0x18006cc58`

## callees

- `0x1800696c8`
- `0x18006ab30`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<MFD3D12Sync>::InternalRelease(volatile int **a1)
{
  volatile int *v1; // rdx
  __int64 result; // rax

  v1 = *a1;
  result = 0;
  if ( *a1 )
  {
    *a1 = 0;
    return Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IMFD3D12SynchronizationObjectCommands,IMFD3D12SynchronizationObject,IMFD3D12SynchronizationObjectCommandsInternal,IMFD3D11SynchronizationObjectCommands,Microsoft::WRL::FtmBase>::Release(
             (__int64)v1,
             v1);
  }
  return result;
}

```

## disassembly

```asm
0x1800696c8  sub     rsp, 28h
0x1800696cc  mov     rdx, [rcx]
0x1800696cf  xor     eax, eax
0x1800696d1  test    rdx, rdx
0x1800696d4  jz      short loc_1800696E1
0x1800696d6  mov     [rcx], rax
0x1800696d9  mov     rcx, rdx
0x1800696dc  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIMFD3D12SynchronizationObjectCommands@@UIMFD3D12SynchronizationObject@@UIMFD3D12SynchronizationObjectCommandsInternal@@UIMFD3D11SynchronizationObjectCommands@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IMFD3D12SynchronizationObjectCommands,IMFD3D12SynchronizationObject,IMFD3D12SynchronizationObjectCommandsInternal,IMFD3D11SynchronizationObjectCommands,Microsoft::WRL::FtmBase>::Release(void)
0x1800696e1  add     rsp, 28h
0x1800696e5  retn
```
