# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,CAsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::Data::Xml::Dom::XmlDocument *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Data::Xml::Dom::XmlDocument *>,0>>::GetIids(ulong *,_GUID * *)

- ea: `0x1800ef460`
- end: `0x1800ef4da`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@V?$CAsyncOperationBase@U?$IAsyncOperation@PEAVXmlDocument@Dom@Xml@Data@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVXmlDocument@Dom@Xml@Data@Windows@@@23@$0A@@@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `122`
- prototype: `HRESULT __fastcall(LoadWorkItem *this, unsigned int *iidCount, _GUID **iids)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800ef4e0`

## callees

- `0x1800eefbc`
- `0x1800ef460`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800ef482`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800ef482`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,CAsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::Data::Xml::Dom::XmlDocument *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Data::Xml::Dom::XmlDocument *>,0>>::GetIids(
        LoadWorkItem *this,
        unsigned int *iidCount,
        _GUID **iids)
{
  Microsoft::WRL::Implements<Windows::Foundation::IAsyncOperation<Windows::Data::Xml::Dom::XmlDocument *>,Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Data::Xml::Dom::XmlDocument *>,1,Microsoft::WRL::AsyncCausalityOptions<0,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > > *v5; // rcx
  _GUID *v6; // r8
  __int64 result; // rax
  _GUID *v8; // r8
  unsigned int index; // [rsp+38h] [rbp+10h] BYREF

  *iids = 0;
  *iidCount = 0;
  v6 = (_GUID *)CoTaskMemAlloc(0x30u);
  if ( !v6 )
    return 2147942414LL;
  index = 0;
  Microsoft::WRL::Implements<Windows::Foundation::IAsyncOperation<Windows::Data::Xml::Dom::XmlDocument *>,Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Data::Xml::Dom::XmlDocument *>,1,Microsoft::WRL::AsyncCausalityOptions<0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>::FillArrayWithIid(
    v5,
    &index,
    v6);
  result = 0;
  v8[index] = GUID_00000038_0000_0000_c000_000000000046;
  *iidCount = 3;
  *iids = v8;
  return result;
}

```

## disassembly

```asm
0x1800ef460  mov     [rsp+arg_0], rbx
0x1800ef465  push    rdi
0x1800ef466  sub     rsp, 20h
0x1800ef46a  mov     qword ptr [iids], 0
0x1800ef471  mov     ecx, 30h ; '0'; cb
0x1800ef476  mov     dword ptr [iidCount], 0
0x1800ef47c  mov     rbx, iids
0x1800ef47f  mov     rdi, iidCount
0x1800ef482  call    cs:__imp_CoTaskMemAlloc
0x1800ef489  nop     dword ptr [rax+rax+00h]
0x1800ef48e  mov     iids, rax; iids
0x1800ef491  test    rax, rax
0x1800ef494  jnz     short loc_1800EF49D
0x1800ef496  mov     eax, 8007000Eh
0x1800ef49b  jmp     short loc_1800EF4CE
0x1800ef49d  lea     iidCount, [rsp+28h+index]; index
0x1800ef4a2  mov     [rsp+28h+index], 0
0x1800ef4aa  call    ?FillArrayWithIid@?$Implements@U?$IAsyncOperation@PEAVXmlDocument@Dom@Xml@Data@Windows@@@Foundation@Windows@@V?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAVXmlDocument@Dom@Xml@Data@Windows@@@Foundation@Windows@@$00U?$AsyncCausalityOptions@$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@3@@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Implements<Windows::Foundation::IAsyncOperation<Windows::Data::Xml::Dom::XmlDocument *>,Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Data::Xml::Dom::XmlDocument *>,1,Microsoft::WRL::AsyncCausalityOptions<0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>::FillArrayWithIid(ulong *,_GUID *)
0x1800ef4af  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x1800ef4b6  mov     edx, [rsp+28h+index]
0x1800ef4ba  add     iidCount, iidCount
0x1800ef4bd  xor     eax, eax
0x1800ef4bf  movdqu  xmmword ptr [iids+iidCount*8], xmm1
0x1800ef4c5  mov     dword ptr [rdi], 3
0x1800ef4cb  mov     [rbx], iids
0x1800ef4ce  mov     rbx, [rsp+28h+arg_0]
0x1800ef4d3  add     rsp, 20h
0x1800ef4d7  pop     rdi
0x1800ef4d8  retn
```
