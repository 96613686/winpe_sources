# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x18000a680`
- end: `0x18000a6df`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIActivationFactoryContractRedirectorContext@Contracts@Foundation@Internal@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `95`
- prototype: `__int64 __fastcall(__int64, _DWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180009b7c`
- `0x18000a680`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a6a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a6a2`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext,Microsoft::WRL::FtmBase>::GetIids(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  __int64 v5; // rcx
  LPVOID v6; // r8
  __int64 result; // rax
  __int64 v8; // r8
  int v9; // [rsp+38h] [rbp+10h] BYREF

  *a3 = 0;
  *a2 = 0;
  v6 = CoTaskMemAlloc(0x20u);
  if ( !v6 )
    return 2147942414LL;
  v9 = 0;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,0,Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(
    v5,
    &v9,
    v6);
  *a2 = 2;
  result = 0;
  *a3 = v8;
  return result;
}

```

## disassembly

```asm
0x18000a680  mov     [rsp+arg_0], rbx
0x18000a685  push    rdi
0x18000a686  sub     rsp, 20h
0x18000a68a  mov     qword ptr [r8], 0
0x18000a691  mov     ecx, 20h ; ' '; cb
0x18000a696  mov     dword ptr [rdx], 0
0x18000a69c  mov     rbx, r8
0x18000a69f  mov     rdi, rdx
0x18000a6a2  call    cs:__imp_CoTaskMemAlloc
0x18000a6a8  mov     r8, rax
0x18000a6ab  test    rax, rax
0x18000a6ae  jnz     short loc_18000A6B7
0x18000a6b0  mov     eax, 8007000Eh
0x18000a6b5  jmp     short loc_18000A6D4
0x18000a6b7  lea     rdx, [rsp+28h+arg_8]
0x18000a6bc  mov     [rsp+28h+arg_8], 0
0x18000a6c4  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$0A@UIActivationFactoryContractRedirectorContext@Contracts@Foundation@Internal@Windows@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,0,Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x18000a6c9  mov     dword ptr [rdi], 2
0x18000a6cf  xor     eax, eax
0x18000a6d1  mov     [rbx], r8
0x18000a6d4  mov     rbx, [rsp+28h+arg_0]
0x18000a6d9  add     rsp, 20h
0x18000a6dd  pop     rdi
0x18000a6de  retn
```
