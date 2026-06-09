# Microsoft::WRL::ActivationFactory<Windows::Networking::NetworkOperators::IProvisioningAgentStaticMethods,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetIids(ulong *,_GUID * *)

- ea: `0x18003f810`
- end: `0x18003f871`
- name: `?GetIids@?$ActivationFactory@UIProvisioningAgentStaticMethods@NetworkOperators@Networking@Windows@@VNil@Details@WRL@Microsoft@@V5678@$0A@@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `97`
- prototype: `HRESULT __fastcall(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<13>,0,1,0,IActivationFactory,Windows::Networking::NetworkOperators::IProvisioningAgentStaticMethods,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil> *this, unsigned int *iidCount, _GUID **iids)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003f880`

## callees

- `0x18003f810`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003f832`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003f832`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ActivationFactory<Windows::Networking::NetworkOperators::IProvisioningAgentStaticMethods,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetIids(
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<13>,0,1,0,IActivationFactory,Windows::Networking::NetworkOperators::IProvisioningAgentStaticMethods,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil> *this,
        unsigned int *iidCount,
        _GUID **iids)
{
  _GUID *v5; // rax

  *iids = 0;
  *iidCount = 0;
  v5 = (_GUID *)CoTaskMemAlloc(0x20u);
  if ( !v5 )
    return 2147942414LL;
  *v5 = GUID_00000035_0000_0000_c000_000000000046;
  v5[1] = GUID_217700e0_8101_11df_adb9_f4ce462d9137;
  *iidCount = 2;
  *iids = v5;
  return 0;
}

```

## disassembly

```asm
0x18003f810  mov     [rsp+arg_0], rbx
0x18003f815  push    rdi
0x18003f816  sub     rsp, 20h
0x18003f81a  mov     qword ptr [iids], 0
0x18003f821  mov     ecx, 20h ; ' '; cb
0x18003f826  mov     dword ptr [iidCount], 0
0x18003f82c  mov     rbx, iids
0x18003f82f  mov     rdi, iidCount
0x18003f832  call    cs:__imp_CoTaskMemAlloc
0x18003f838  test    rax, rax
0x18003f83b  jnz     short loc_18003F844
0x18003f83d  mov     eax, 8007000Eh
0x18003f842  jmp     short loc_18003F866
0x18003f844  movups  xmm0, xmmword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data1
0x18003f84b  movdqu  xmmword ptr [rax], xmm0
0x18003f84f  movups  xmm1, xmmword ptr cs:_GUID_217700e0_8101_11df_adb9_f4ce462d9137.Data1
0x18003f856  movdqu  xmmword ptr [rax+10h], xmm1
0x18003f85b  mov     dword ptr [rdi], 2
0x18003f861  mov     [rbx], rax
0x18003f864  xor     eax, eax
0x18003f866  mov     rbx, [rsp+28h+arg_0]
0x18003f86b  add     rsp, 20h
0x18003f86f  pop     rdi
0x18003f870  retn
```
