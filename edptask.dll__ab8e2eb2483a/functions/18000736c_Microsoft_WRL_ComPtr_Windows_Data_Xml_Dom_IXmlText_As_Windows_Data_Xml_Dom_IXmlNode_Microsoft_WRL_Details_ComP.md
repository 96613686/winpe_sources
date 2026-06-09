# Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlText>::As<Windows::Data::Xml::Dom::IXmlNode>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlNode>>)

- ea: `0x18000736c`
- end: `0x1800073c9`
- name: `??$As@UIXmlNode@Dom@Xml@Data@Windows@@@?$ComPtr@UIXmlText@Dom@Xml@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIXmlNode@Dom@Xml@Data@Windows@@@WRL@Microsoft@@@Details@12@@Z`
- size: `93`
- prototype: `__int64 __fastcall(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *), __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ac1c`

## callees

- `0x18000736c`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlText>::As<Windows::Data::Xml::Dom::IXmlNode>(
        __int64 (__fastcall ****a1)(_QWORD, GUID *, __int64 *),
        __int64 *a2)
{
  __int64 (__fastcall ***v3)(_QWORD, GUID *, __int64 *); // rdi
  __int64 (__fastcall *v4)(_QWORD, GUID *, __int64 *); // rsi
  __int64 v5; // rcx

  v3 = *a1;
  v4 = ***a1;
  v5 = *a2;
  if ( *a2 )
  {
    *a2 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  }
  return v4(v3, &GUID_1c741d59_2122_47d5_a856_83f3d4214875, a2);
}

```

## disassembly

```asm
0x18000736c  mov     [rsp+arg_0], rbx
0x180007371  mov     [rsp+arg_8], rsi
0x180007376  push    rdi
0x180007377  sub     rsp, 20h
0x18000737b  mov     rbx, rdx
0x18000737e  mov     rdi, [rcx]
0x180007381  mov     rax, [rdi]
0x180007384  mov     rsi, [rax]
0x180007387  mov     rcx, [rdx]
0x18000738a  test    rcx, rcx
0x18000738d  jz      short loc_1800073A3
0x18000738f  mov     qword ptr [rdx], 0
0x180007396  mov     rax, [rcx]
0x180007399  mov     rax, [rax+10h]
0x18000739d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073a2  nop
0x1800073a3  mov     r8, rbx
0x1800073a6  lea     rdx, _GUID_1c741d59_2122_47d5_a856_83f3d4214875
0x1800073ad  mov     rcx, rdi
0x1800073b0  mov     rax, rsi
0x1800073b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073b8  nop
0x1800073b9  mov     rbx, [rsp+28h+arg_0]
0x1800073be  mov     rsi, [rsp+28h+arg_8]
0x1800073c3  add     rsp, 20h
0x1800073c7  pop     rdi
0x1800073c8  retn
```
