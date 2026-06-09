# FveEasNetworkStatusChangeNotificationHandler::FveEasNetworkStatusChangeNotificationHandler(IFveEasNetworkStatusChangeAction * *,Microsoft::WRL::ComPtr<Windows::Networking::Connectivity::INetworkInformationStatics>)

- ea: `0x18001535c`
- end: `0x1800153ec`
- name: `??0FveEasNetworkStatusChangeNotificationHandler@@QEAA@PEAPEAVIFveEasNetworkStatusChangeAction@@V?$ComPtr@UINetworkInformationStatics@Connectivity@Networking@Windows@@@WRL@Microsoft@@@Z`
- size: `144`
- prototype: `__int64 __fastcall(__int64, _QWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800152a4`

## callees

- `0x180015348`
- `0x18001535c`
- `0x18001808c`
- `0x18002d010`

## pseudocode

```c
__int64 __fastcall FveEasNetworkStatusChangeNotificationHandler::FveEasNetworkStatusChangeNotificationHandler(
        __int64 a1,
        _QWORD *a2,
        __int64 *a3)
{
  __int64 v6; // rcx

  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Networking::Connectivity::INetworkStatusChangedEventHandler>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Networking::Connectivity::INetworkStatusChangedEventHandler>();
  *(_QWORD *)a1 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Networking::Connectivity::INetworkStatusChangedEventHandler>::`vftable';
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)a1 = &FveEasNetworkStatusChangeNotificationHandler::`vftable';
  *(_BYTE *)(a1 + 16) = 0;
  v6 = *a3;
  *(_QWORD *)(a1 + 32) = *a3;
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
  *(_QWORD *)(a1 + 40) = *a2;
  *a2 = 0;
  Microsoft::WRL::ComPtr<FveEasNetworkStatusChangeNotificationHandler>::InternalRelease(a3);
  return a1;
}

```

## disassembly

```asm
0x18001535c  mov     [rsp+arg_0], rbx
0x180015361  mov     [rsp+arg_8], rsi
0x180015366  push    rdi
0x180015367  sub     rsp, 20h
0x18001536b  mov     rdi, r8
0x18001536e  mov     rsi, rdx
0x180015371  mov     rbx, rcx
0x180015374  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UINetworkStatusChangedEventHandler@Connectivity@Networking@Windows@@@Details@WRL@Microsoft@@IEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Networking::Connectivity::INetworkStatusChangedEventHandler>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Networking::Connectivity::INetworkStatusChangedEventHandler>(void)
0x180015379  lea     rcx, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UINetworkStatusChangedEventHandler@Connectivity@Networking@Windows@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Networking::Connectivity::INetworkStatusChangedEventHandler>::`vftable'
0x180015380  mov     [rbx], rcx
0x180015383  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18001538a  test    rcx, rcx
0x18001538d  jz      short loc_18001539C
0x18001538f  mov     rax, [rcx]
0x180015392  mov     rax, [rax+8]
0x180015396  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001539b  nop
0x18001539c  lea     rax, ??_7FveEasNetworkStatusChangeNotificationHandler@@6B@; const FveEasNetworkStatusChangeNotificationHandler::`vftable'
0x1800153a3  mov     [rbx], rax
0x1800153a6  mov     byte ptr [rbx+10h], 0
0x1800153aa  mov     rcx, [rdi]
0x1800153ad  mov     [rbx+20h], rcx
0x1800153b1  test    rcx, rcx
0x1800153b4  jz      short loc_1800153C3
0x1800153b6  mov     rax, [rcx]
0x1800153b9  mov     rax, [rax+8]
0x1800153bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800153c2  nop
0x1800153c3  mov     rax, [rsi]
0x1800153c6  mov     [rbx+28h], rax
0x1800153ca  mov     qword ptr [rsi], 0
0x1800153d1  mov     rcx, rdi
0x1800153d4  call    ?InternalRelease@?$ComPtr@VFveEasNetworkStatusChangeNotificationHandler@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<FveEasNetworkStatusChangeNotificationHandler>::InternalRelease(void)
0x1800153d9  mov     rax, rbx
0x1800153dc  mov     rbx, [rsp+28h+arg_0]
0x1800153e1  mov     rsi, [rsp+28h+arg_8]
0x1800153e6  add     rsp, 20h
0x1800153ea  pop     rdi
0x1800153eb  retn
```
