# LoadSettings::GetIids(ulong *,_GUID * *)

- ea: `0x1800d31b0`
- end: `0x1800d320f`
- name: `?GetIids@LoadSettings@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `95`
- prototype: `HRESULT __fastcall(LoadSettings *this, unsigned int *iidCount, _GUID **iids)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800d2f58`
- `0x1800d31b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d31d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d31d2`

## pseudocode

```c
__int64 __fastcall LoadSettings::GetIids(LoadSettings *this, unsigned int *iidCount, _GUID **iids)
{
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Data::Xml::Dom::IXmlLoadSettings,IWeakReferenceSource,Microsoft::WRL::FtmBase> *v5; // rcx
  _GUID *v6; // r8
  __int64 result; // rax
  _GUID *v8; // r8
  unsigned int index; // [rsp+38h] [rbp+10h] BYREF

  *iids = 0;
  *iidCount = 0;
  v6 = (_GUID *)CoTaskMemAlloc(0x20u);
  if ( !v6 )
    return 2147942414LL;
  index = 0;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Data::Xml::Dom::IXmlLoadSettings,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(
    v5,
    &index,
    v6);
  *iidCount = 2;
  result = 0;
  *iids = v8;
  return result;
}

```

## disassembly

```asm
0x1800d31b0  mov     [rsp+arg_0], rbx
0x1800d31b5  push    rdi
0x1800d31b6  sub     rsp, 20h
0x1800d31ba  mov     qword ptr [iids], 0
0x1800d31c1  mov     ecx, 20h ; ' '; cb
0x1800d31c6  mov     dword ptr [iidCount], 0
0x1800d31cc  mov     rbx, iids
0x1800d31cf  mov     rdi, iidCount
0x1800d31d2  call    cs:__imp_CoTaskMemAlloc
0x1800d31d8  mov     iids, rax; iids
0x1800d31db  test    rax, rax
0x1800d31de  jnz     short loc_1800D31E7
0x1800d31e0  mov     eax, 8007000Eh
0x1800d31e5  jmp     short loc_1800D3204
0x1800d31e7  lea     iidCount, [rsp+28h+index]; index
0x1800d31ec  mov     [rsp+28h+index], 0
0x1800d31f4  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@UIXmlLoadSettings@Dom@Xml@Data@Windows@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Data::Xml::Dom::IXmlLoadSettings,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x1800d31f9  mov     dword ptr [rdi], 2
0x1800d31ff  xor     eax, eax
0x1800d3201  mov     [rbx], iids
0x1800d3204  mov     rbx, [rsp+28h+arg_0]
0x1800d3209  add     rsp, 20h
0x1800d320d  pop     rdi
0x1800d320e  retn
```
