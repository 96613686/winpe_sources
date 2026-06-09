# CxCodeVideoProcMFT::GetIids(ulong *,_GUID * *)

- ea: `0x18005ff50`
- end: `0x18005ffaf`
- name: `?GetIids@CxCodeVideoProcMFT@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `95`
- prototype: `__int64 __fastcall(CxCodeVideoProcMFT *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18005f020`
- `0x18005ff50`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005ff72`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005ff72`

## pseudocode

```c
__int64 __fastcall CxCodeVideoProcMFT::GetIids(CxCodeVideoProcMFT *this, unsigned int *a2, struct _GUID **a3)
{
  __int64 v5; // rcx
  LPVOID v6; // r8
  __int64 result; // rax
  struct _GUID *v8; // r8
  int v9; // [rsp+38h] [rbp+10h] BYREF

  *a3 = 0;
  *a2 = 0;
  v6 = CoTaskMemAlloc(0xB0u);
  if ( !v6 )
    return 2147942414LL;
  v9 = 0;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,0,Windows::Media::IMediaExtension,IWeakReferenceSource,CMFTBase,IMFRealTimeClientEx,Microsoft::WRL::ChainInterfaces<IMFVideoProcessorControlInternal,IMFVideoProcessorControl3,IMFVideoProcessorControl2,IMFVideoProcessorControl,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IMFGetService,IMFObjectInformation,IMFTelemetryComponent>::FillArrayWithIid(
    v5,
    &v9,
    v6);
  *a2 = 11;
  result = 0;
  *a3 = v8;
  return result;
}

```

## disassembly

```asm
0x18005ff50  mov     [rsp+arg_0], rbx
0x18005ff55  push    rdi
0x18005ff56  sub     rsp, 20h
0x18005ff5a  mov     qword ptr [r8], 0
0x18005ff61  mov     ecx, 0B0h; cb
0x18005ff66  mov     dword ptr [rdx], 0
0x18005ff6c  mov     rbx, r8
0x18005ff6f  mov     rdi, rdx
0x18005ff72  call    cs:__imp_CoTaskMemAlloc
0x18005ff78  mov     r8, rax
0x18005ff7b  test    rax, rax
0x18005ff7e  jnz     short loc_18005FF87
0x18005ff80  mov     eax, 8007000Eh
0x18005ff85  jmp     short loc_18005FFA4
0x18005ff87  lea     rdx, [rsp+28h+arg_8]
0x18005ff8c  mov     [rsp+28h+arg_8], 0
0x18005ff94  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$0A@UIMediaExtension@Media@Windows@@UIWeakReferenceSource@@VCMFTBase@@UIMFRealTimeClientEx@@U?$ChainInterfaces@UIMFVideoProcessorControlInternal@@UIMFVideoProcessorControl3@@UIMFVideoProcessorControl2@@UIMFVideoProcessorControl@@VNil@Details@WRL@Microsoft@@V5678@V5678@V5678@V5678@V5678@@23@UIMFGetService@@UIMFObjectInformation@@UIMFTelemetryComponent@@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,0,Windows::Media::IMediaExtension,IWeakReferenceSource,CMFTBase,IMFRealTimeClientEx,Microsoft::WRL::ChainInterfaces<IMFVideoProcessorControlInternal,IMFVideoProcessorControl3,IMFVideoProcessorControl2,IMFVideoProcessorControl,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IMFGetService,IMFObjectInformation,IMFTelemetryComponent>::FillArrayWithIid(ulong *,_GUID *)
0x18005ff99  mov     dword ptr [rdi], 0Bh
0x18005ff9f  xor     eax, eax
0x18005ffa1  mov     [rbx], r8
0x18005ffa4  mov     rbx, [rsp+28h+arg_0]
0x18005ffa9  add     rsp, 20h
0x18005ffad  pop     rdi
0x18005ffae  retn
```
