# Microsoft::WRL::ComPtr<ABI::Windows::Foundation::Collections::IPropertySet>::As<ABI::Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ABI::Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>>)

- ea: `0x180014114`
- end: `0x18001415e`
- name: `??$As@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@ABI@@@?$ComPtr@UIPropertySet@Collections@Foundation@Windows@ABI@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@ABI@@@WRL@Microsoft@@@Details@12@@Z`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180015880`

## callees

- `0x180004dcc`
- `0x18001a010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<ABI::Windows::Foundation::Collections::IPropertySet>::As<ABI::Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(
        __int64 (__fastcall ****a1)(_QWORD, GUID *, __int64 *),
        __int64 *a2)
{
  __int64 (__fastcall ***v3)(_QWORD, GUID *, __int64 *); // rsi
  __int64 (__fastcall *v4)(_QWORD, GUID *, __int64 *); // rdi

  v3 = *a1;
  v4 = ***a1;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a2);
  return v4(v3, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, a2);
}

```

## disassembly

```asm
0x180014114  mov     [rsp+arg_0], rbx
0x180014119  mov     [rsp+arg_8], rsi
0x18001411e  push    rdi
0x18001411f  sub     rsp, 20h
0x180014123  mov     rbx, rdx
0x180014126  mov     rsi, [rcx]
0x180014129  mov     rax, [rsi]
0x18001412c  mov     rdi, [rax]
0x18001412f  mov     rcx, rdx
0x180014132  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180014137  mov     r8, rbx
0x18001413a  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x180014141  mov     rcx, rsi
0x180014144  mov     rax, rdi
0x180014147  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001414c  nop
0x18001414d  mov     rbx, [rsp+28h+arg_0]
0x180014152  mov     rsi, [rsp+28h+arg_8]
0x180014157  add     rsp, 20h
0x18001415b  pop     rdi
0x18001415c  retn
```
