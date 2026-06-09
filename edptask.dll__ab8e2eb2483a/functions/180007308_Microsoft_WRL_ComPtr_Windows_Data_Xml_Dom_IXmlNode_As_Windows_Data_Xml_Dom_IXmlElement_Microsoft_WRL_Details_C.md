# Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlNode>::As<Windows::Data::Xml::Dom::IXmlElement>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlElement>>)

- ea: `0x180007308`
- end: `0x180007365`
- name: `??$As@UIXmlElement@Dom@Xml@Data@Windows@@@?$ComPtr@UIXmlNode@Dom@Xml@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIXmlElement@Dom@Xml@Data@Windows@@@WRL@Microsoft@@@Details@12@@Z`
- size: `93`
- prototype: `__int64 __fastcall(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *), __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ac1c`

## callees

- `0x180007308`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlNode>::As<Windows::Data::Xml::Dom::IXmlElement>(
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
  return v4(v3, &GUID_2dfb8a1f_6b10_4ef8_9f83_efcce8faec37, a2);
}

```

## disassembly

```asm
0x180007308  mov     [rsp+arg_0], rbx
0x18000730d  mov     [rsp+arg_8], rsi
0x180007312  push    rdi
0x180007313  sub     rsp, 20h
0x180007317  mov     rbx, rdx
0x18000731a  mov     rdi, [rcx]
0x18000731d  mov     rax, [rdi]
0x180007320  mov     rsi, [rax]
0x180007323  mov     rcx, [rdx]
0x180007326  test    rcx, rcx
0x180007329  jz      short loc_18000733F
0x18000732b  mov     qword ptr [rdx], 0
0x180007332  mov     rax, [rcx]
0x180007335  mov     rax, [rax+10h]
0x180007339  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000733e  nop
0x18000733f  mov     r8, rbx
0x180007342  lea     rdx, _GUID_2dfb8a1f_6b10_4ef8_9f83_efcce8faec37
0x180007349  mov     rcx, rdi
0x18000734c  mov     rax, rsi
0x18000734f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007354  nop
0x180007355  mov     rbx, [rsp+28h+arg_0]
0x18000735a  mov     rsi, [rsp+28h+arg_8]
0x18000735f  add     rsp, 20h
0x180007363  pop     rdi
0x180007364  retn
```
