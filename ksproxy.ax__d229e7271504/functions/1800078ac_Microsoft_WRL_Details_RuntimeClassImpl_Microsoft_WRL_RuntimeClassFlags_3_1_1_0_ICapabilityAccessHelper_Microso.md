# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,ICapabilityAccessHelper,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,ICapabilityAccessHelper,Microsoft::WRL::FtmBase>(void)

- ea: `0x1800078ac`
- end: `0x1800078d4`
- name: `??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UICapabilityAccessHelper@@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ`
- size: `40`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180007838`
- `0x180042f00`
- `0x180043dbc`

## callees

- `0x1800078ac`
- `0x180007ae8`
- `0x18001ce50`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,ICapabilityAccessHelper,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,ICapabilityAccessHelper,Microsoft::WRL::FtmBase>(
        __int64 a1)
{
  __int64 v2; // rcx

  v2 = *(_QWORD *)(a1 + 64);
  if ( v2 < 0 )
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(2 * v2);
  return Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a1 + 48);
}

```

## disassembly

```asm
0x1800078ac  push    rbx
0x1800078ae  sub     rsp, 20h
0x1800078b2  mov     rbx, rcx
0x1800078b5  mov     rcx, [rcx+40h]
0x1800078b9  test    rcx, rcx
0x1800078bc  jns     short loc_1800078C6
0x1800078be  add     rcx, rcx
0x1800078c1  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x1800078c6  lea     rcx, [rbx+30h]
0x1800078ca  add     rsp, 20h
0x1800078ce  pop     rbx
0x1800078cf  jmp     ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
```
