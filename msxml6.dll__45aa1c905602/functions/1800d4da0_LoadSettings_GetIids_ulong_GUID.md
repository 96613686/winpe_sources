# LoadSettings::GetIids(ulong *,_GUID * *)

- ea: `0x1800d4da0`
- end: `0x1800d4e06`
- name: `?GetIids@LoadSettings@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `102`
- prototype: `HRESULT __fastcall(LoadSettings *this, unsigned int *iidCount, _GUID **iids)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800d4b40`
- `0x1800d4da0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d4dc2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d4dc2`

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
0x1800d4da0  mov     [rsp+arg_0], rbx
0x1800d4da5  push    rdi
0x1800d4da6  sub     rsp, 20h
0x1800d4daa  mov     qword ptr [iids], 0
0x1800d4db1  mov     ecx, 20h ; ' '; cb
0x1800d4db6  mov     dword ptr [iidCount], 0
0x1800d4dbc  mov     rbx, iids
0x1800d4dbf  mov     rdi, iidCount
0x1800d4dc2  call    cs:__imp_CoTaskMemAlloc
0x1800d4dc9  nop     dword ptr [rax+rax+00h]
0x1800d4dce  mov     iids, rax; iids
0x1800d4dd1  test    rax, rax
0x1800d4dd4  jnz     short loc_1800D4DDD
0x1800d4dd6  mov     eax, 8007000Eh
0x1800d4ddb  jmp     short loc_1800D4DFA
0x1800d4ddd  lea     iidCount, [rsp+28h+index]; index
0x1800d4de2  mov     [rsp+28h+index], 0
0x1800d4dea  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@UIXmlLoadSettings@Dom@Xml@Data@Windows@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Data::Xml::Dom::IXmlLoadSettings,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x1800d4def  mov     dword ptr [rdi], 2
0x1800d4df5  xor     eax, eax
0x1800d4df7  mov     [rbx], iids
0x1800d4dfa  mov     rbx, [rsp+28h+arg_0]
0x1800d4dff  add     rsp, 20h
0x1800d4e03  pop     rdi
0x1800d4e04  retn
```
