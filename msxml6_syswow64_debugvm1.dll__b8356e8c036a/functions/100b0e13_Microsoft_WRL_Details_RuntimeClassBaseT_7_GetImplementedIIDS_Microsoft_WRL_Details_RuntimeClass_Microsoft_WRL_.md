# Microsoft::WRL::Details::RuntimeClassBaseT<7>::GetImplementedIIDS<Microsoft::WRL::Details::RuntimeClass<Microsoft::WRL::Details::InterfaceListHelper<Windows::Data::Xml::Dom::IXmlDomImplementation>,Microsoft::WRL::RuntimeClassFlags<4103>,0,1,0>>(Microsoft::WRL::Details::RuntimeClass<Microsoft::WRL::Details::InterfaceListHelper<Windows::Data::Xml::Dom::IXmlDomImplementation>,Microsoft::WRL::RuntimeClassFlags<4103>,0,1,0> *,ulong *,_GUID * *)

- ea: `0x100b0e13`
- end: `0x100b0e5e`
- name: `??$GetImplementedIIDS@V?$RuntimeClass@U?$InterfaceListHelper@UIXmlDomImplementation@Dom@Xml@Data@Windows@@@Details@WRL@Microsoft@@U?$RuntimeClassFlags@$0BAAH@@34@$0A@$00$0A@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$06@Details@WRL@Microsoft@@KGJPAV?$RuntimeClass@U?$InterfaceListHelper@UIXmlDomImplementation@Dom@Xml@Data@Windows@@@Details@WRL@Microsoft@@U?$RuntimeClassFlags@$0BAAH@@34@$0A@$00$0A@@123@PAKPAPAU_GUID@@@Z`
- size: `75`
- prototype: `HRESULT __userpurge@<eax>(Microsoft::WRL::Details::RuntimeClass<Microsoft::WRL::Details::InterfaceListHelper<Windows::Data::Xml::Dom::IXmlDomImplementation>,Microsoft::WRL::RuntimeClassFlags<4103>,0,1,0> *iidCount@<edx>, unsigned int *iids, _GUID **implements)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x100b0fc0`

## callees

- `0x100b0e13`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x100b0e2c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x100b0e2c`

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
0x100b0e13  mov     edi, edi
0x100b0e15  push    ebp
0x100b0e16  mov     ebp, esp
0x100b0e18  mov     eax, [ebp+iids]
0x100b0e1b  push    ebx
0x100b0e1c  mov     ebx, iidCount
0x100b0e1e  push    10h; cb
0x100b0e20  mov     dword ptr [eax], 0
0x100b0e26  mov     dword ptr [ebx], 0
0x100b0e2c  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x100b0e32  test    eax, eax
0x100b0e34  jnz     short loc_100B0E3D
0x100b0e36  mov     eax, 8007000Eh
0x100b0e3b  jmp     short loc_100B0E59
0x100b0e3d  mov     ecx, [ebp+iids]
0x100b0e40  push    esi
0x100b0e41  push    edi
0x100b0e42  mov     edi, eax
0x100b0e44  mov     esi, offset __GUID_6de58132_f11d_4fbb_8cc6_583cba93112f
0x100b0e49  movsd
0x100b0e4a  movsd
0x100b0e4b  movsd
0x100b0e4c  movsd
0x100b0e4d  mov     dword ptr [ebx], 1
0x100b0e53  pop     edi
0x100b0e54  mov     [ecx], eax
0x100b0e56  xor     eax, eax
0x100b0e58  pop     esi
0x100b0e59  pop     ebx
0x100b0e5a  pop     ebp
0x100b0e5b  retn    4
```
