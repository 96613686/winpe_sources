# Microsoft::WRL::Details::RuntimeClass<Microsoft::WRL::Details::InterfaceListHelper<Windows::Data::Xml::Dom::IXmlDomImplementation>,Microsoft::WRL::RuntimeClassFlags<4103>,0,1,0>::GetIids(ulong *,_GUID * *)

- ea: `0x1800f6490`
- end: `0x1800f64e5`
- name: `?GetIids@?$RuntimeClass@U?$InterfaceListHelper@UIXmlDomImplementation@Dom@Xml@Data@Windows@@@Details@WRL@Microsoft@@U?$RuntimeClassFlags@$0BAAH@@34@$0A@$00$0A@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `85`
- prototype: `HRESULT __fastcall(Microsoft::WRL::Details::RuntimeClass<Microsoft::WRL::Details::InterfaceListHelper<Windows::Data::Xml::Dom::IXmlDomImplementation>,Microsoft::WRL::RuntimeClassFlags<4103>,0,1,0> *this, unsigned int *iidCount, _GUID **iids)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800f6490`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800f64b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800f64b2`

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
0x1800f6490  mov     [rsp+arg_0], rbx
0x1800f6495  push    rdi
0x1800f6496  sub     rsp, 20h
0x1800f649a  mov     qword ptr [iids], 0
0x1800f64a1  mov     ecx, 10h; cb
0x1800f64a6  mov     dword ptr [iidCount], 0
0x1800f64ac  mov     rbx, iids
0x1800f64af  mov     rdi, iidCount
0x1800f64b2  call    cs:__imp_CoTaskMemAlloc
0x1800f64b8  test    rax, rax
0x1800f64bb  jnz     short loc_1800F64C4
0x1800f64bd  mov     eax, 8007000Eh
0x1800f64c2  jmp     short loc_1800F64DA
0x1800f64c4  movups  xmm0, xmmword ptr cs:_GUID_6de58132_f11d_4fbb_8cc6_583cba93112f.Data1
0x1800f64cb  movdqu  xmmword ptr [rax], xmm0
0x1800f64cf  mov     dword ptr [rdi], 1
0x1800f64d5  mov     [rbx], rax
0x1800f64d8  xor     eax, eax
0x1800f64da  mov     rbx, [rsp+28h+arg_0]
0x1800f64df  add     rsp, 20h
0x1800f64e3  pop     rdi
0x1800f64e4  retn
```
