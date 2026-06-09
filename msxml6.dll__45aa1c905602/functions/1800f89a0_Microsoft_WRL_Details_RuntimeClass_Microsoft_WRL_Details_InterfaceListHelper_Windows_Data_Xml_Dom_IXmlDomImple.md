# Microsoft::WRL::Details::RuntimeClass<Microsoft::WRL::Details::InterfaceListHelper<Windows::Data::Xml::Dom::IXmlDomImplementation>,Microsoft::WRL::RuntimeClassFlags<4103>,0,1,0>::GetIids(ulong *,_GUID * *)

- ea: `0x1800f89a0`
- end: `0x1800f89fc`
- name: `?GetIids@?$RuntimeClass@U?$InterfaceListHelper@UIXmlDomImplementation@Dom@Xml@Data@Windows@@@Details@WRL@Microsoft@@U?$RuntimeClassFlags@$0BAAH@@34@$0A@$00$0A@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `92`
- prototype: `HRESULT __fastcall(Microsoft::WRL::Details::RuntimeClass<Microsoft::WRL::Details::InterfaceListHelper<Windows::Data::Xml::Dom::IXmlDomImplementation>,Microsoft::WRL::RuntimeClassFlags<4103>,0,1,0> *this, unsigned int *iidCount, _GUID **iids)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800f89a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800f89c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800f89c2`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClass<Microsoft::WRL::Details::InterfaceListHelper<Windows::Data::Xml::Dom::IXmlDomImplementation>,Microsoft::WRL::RuntimeClassFlags<4103>,0,1,0>::GetIids(
        Microsoft::WRL::Details::RuntimeClass<Microsoft::WRL::Details::InterfaceListHelper<Windows::Data::Xml::Dom::IXmlDomImplementation>,Microsoft::WRL::RuntimeClassFlags<4103>,0,1,0> *this,
        unsigned int *iidCount,
        _GUID **iids)
{
  _GUID *v5; // rax

  *iids = 0;
  *iidCount = 0;
  v5 = (_GUID *)CoTaskMemAlloc(0x10u);
  if ( !v5 )
    return 2147942414LL;
  *v5 = GUID_6de58132_f11d_4fbb_8cc6_583cba93112f;
  *iidCount = 1;
  *iids = v5;
  return 0;
}

```

## disassembly

```asm
0x1800f89a0  mov     [rsp+arg_0], rbx
0x1800f89a5  push    rdi
0x1800f89a6  sub     rsp, 20h
0x1800f89aa  mov     qword ptr [iids], 0
0x1800f89b1  mov     ecx, 10h; cb
0x1800f89b6  mov     dword ptr [iidCount], 0
0x1800f89bc  mov     rbx, iids
0x1800f89bf  mov     rdi, iidCount
0x1800f89c2  call    cs:__imp_CoTaskMemAlloc
0x1800f89c9  nop     dword ptr [rax+rax+00h]
0x1800f89ce  test    rax, rax
0x1800f89d1  jnz     short loc_1800F89DA
0x1800f89d3  mov     eax, 8007000Eh
0x1800f89d8  jmp     short loc_1800F89F0
0x1800f89da  movups  xmm0, xmmword ptr cs:_GUID_6de58132_f11d_4fbb_8cc6_583cba93112f.Data1
0x1800f89e1  movdqu  xmmword ptr [rax], xmm0
0x1800f89e5  mov     dword ptr [rdi], 1
0x1800f89eb  mov     [rbx], rax
0x1800f89ee  xor     eax, eax
0x1800f89f0  mov     rbx, [rsp+28h+arg_0]
0x1800f89f5  add     rsp, 20h
0x1800f89f9  pop     rdi
0x1800f89fa  retn
```
