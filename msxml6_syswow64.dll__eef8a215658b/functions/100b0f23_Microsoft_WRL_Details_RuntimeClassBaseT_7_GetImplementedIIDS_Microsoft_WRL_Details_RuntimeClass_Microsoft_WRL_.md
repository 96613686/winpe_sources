# Microsoft::WRL::Details::RuntimeClassBaseT<7>::GetImplementedIIDS<Microsoft::WRL::Details::RuntimeClass<Microsoft::WRL::Details::InterfaceListHelper<Windows::Data::Xml::Dom::IXmlDomImplementation>,Microsoft::WRL::RuntimeClassFlags<4103>,0,1,0>>(Microsoft::WRL::Details::RuntimeClass<Microsoft::WRL::Details::InterfaceListHelper<Windows::Data::Xml::Dom::IXmlDomImplementation>,Microsoft::WRL::RuntimeClassFlags<4103>,0,1,0> *,ulong *,_GUID * *)

- ea: `0x100b0f23`
- end: `0x100b0f6e`
- name: `??$GetImplementedIIDS@V?$RuntimeClass@U?$InterfaceListHelper@UIXmlDomImplementation@Dom@Xml@Data@Windows@@@Details@WRL@Microsoft@@U?$RuntimeClassFlags@$0BAAH@@34@$0A@$00$0A@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$06@Details@WRL@Microsoft@@KGJPAV?$RuntimeClass@U?$InterfaceListHelper@UIXmlDomImplementation@Dom@Xml@Data@Windows@@@Details@WRL@Microsoft@@U?$RuntimeClassFlags@$0BAAH@@34@$0A@$00$0A@@123@PAKPAPAU_GUID@@@Z`
- size: `75`
- prototype: `HRESULT __userpurge@<eax>(Microsoft::WRL::Details::RuntimeClass<Microsoft::WRL::Details::InterfaceListHelper<Windows::Data::Xml::Dom::IXmlDomImplementation>,Microsoft::WRL::RuntimeClassFlags<4103>,0,1,0> *iidCount@<edx>, unsigned int *iids, _GUID **implements)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x100b10d0`

## callees

- `0x100b0f23`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x100b0f3c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x100b0f3c`

## pseudocode

```c
HRESULT __userpurge Microsoft::WRL::Details::RuntimeClassBaseT<7>::GetImplementedIIDS<Microsoft::WRL::Details::RuntimeClass<Microsoft::WRL::Details::InterfaceListHelper<Windows::Data::Xml::Dom::IXmlDomImplementation>,Microsoft::WRL::RuntimeClassFlags<4103>,0,1,0>>@<eax>(
        Microsoft::WRL::Details::RuntimeClass<Microsoft::WRL::Details::InterfaceListHelper<Windows::Data::Xml::Dom::IXmlDomImplementation>,Microsoft::WRL::RuntimeClassFlags<4103>,0,1,0> *iidCount@<edx>,
        _GUID **iids,
        _GUID **implements)
{
  GUID *v4; // eax

  *iids = 0;
  iidCount->__vftable = 0;
  v4 = (GUID *)CoTaskMemAlloc(0x10u);
  if ( !v4 )
    return -2147024882;
  *v4 = _GUID_6de58132_f11d_4fbb_8cc6_583cba93112f;
  iidCount->__vftable = (Microsoft::WRL::Details::RuntimeClass<Microsoft::WRL::Details::InterfaceListHelper<Windows::Data::Xml::Dom::IXmlDomImplementation>,Microsoft::WRL::RuntimeClassFlags<4103>,0,1,0>_vtbl *)1;
  *iids = v4;
  return 0;
}

```

## disassembly

```asm
0x100b0f23  mov     edi, edi
0x100b0f25  push    ebp
0x100b0f26  mov     ebp, esp
0x100b0f28  mov     eax, [ebp+iids]
0x100b0f2b  push    ebx
0x100b0f2c  mov     ebx, iidCount
0x100b0f2e  push    10h; cb
0x100b0f30  mov     dword ptr [eax], 0
0x100b0f36  mov     dword ptr [ebx], 0
0x100b0f3c  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x100b0f42  test    eax, eax
0x100b0f44  jnz     short loc_100B0F4D
0x100b0f46  mov     eax, 8007000Eh
0x100b0f4b  jmp     short loc_100B0F69
0x100b0f4d  mov     ecx, [ebp+iids]
0x100b0f50  push    esi
0x100b0f51  push    edi
0x100b0f52  mov     edi, eax
0x100b0f54  mov     esi, offset __GUID_6de58132_f11d_4fbb_8cc6_583cba93112f
0x100b0f59  movsd
0x100b0f5a  movsd
0x100b0f5b  movsd
0x100b0f5c  movsd
0x100b0f5d  mov     dword ptr [ebx], 1
0x100b0f63  pop     edi
0x100b0f64  mov     [ecx], eax
0x100b0f66  xor     eax, eax
0x100b0f68  pop     esi
0x100b0f69  pop     ebx
0x100b0f6a  pop     ebp
0x100b0f6b  retn    4
```
