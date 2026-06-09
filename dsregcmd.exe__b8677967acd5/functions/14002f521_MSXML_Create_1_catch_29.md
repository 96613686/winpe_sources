# _MSXML::Create_::_1_::catch$29

- ea: `0x14002f521`
- end: `0x14002f5b1`
- name: `_MSXML::Create_::_1_::catch$29`
- size: `144`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x140005678`
- `0x14000598c`
- `0x1400081d8`
- `0x14001413c`
- `0x14002abe8`
- `0x14002c3e8`
- `0x14002f521`

## string_xrefs

- `0x14002f55f`: `Msxml2.DOMDocument.6.0`

## pseudocode

```c
void __fastcall __noreturn MSXML::Create_::_1_::catch_29(__int64 a1, _QWORD *a2)
{
  ResourceMsg *v3; // rax
  const wchar_t *v4; // rax
  const unsigned __int16 *v5; // rax

  if ( *(_DWORD *)(a2[11] + 8LL) == -2147221164 )
  {
    v3 = ResourceMsg::ResourceMsg((ResourceMsg *)(a2 + 27), 0x4AAE0014u);
    v4 = (const wchar_t *)std::unique_ptr<WebRequest>::operator->((__int64)v3);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
      a2 + 4,
      v4,
      L"Msxml2.DOMDocument.6.0",
      L"88d96a05-f192-11d4-a65f-0040963251e5");
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(a2 + 27);
    v5 = (const unsigned __int16 *)std::unique_ptr<WebRequest>::operator->((__int64)(a2 + 4));
    XmlException::XmlException((XmlException *)(a2 + 13), -895156223, v5);
    throw (XmlException *)(a2 + 13);
  }
  throw;
}

```

## disassembly

```asm
0x14002f521  mov     [rsp+arg_8], rdx
0x14002f526  push    rbp
0x14002f527  sub     rsp, 20h
0x14002f52b  mov     rbp, rdx
0x14002f52e  mov     rax, [rbp+58h]
0x14002f532  cmp     dword ptr [rax+8], 80040154h
0x14002f539  jnz     short loc_14002F5A7
0x14002f53b  mov     edx, 4AAE0014h; unsigned int
0x14002f540  lea     rcx, [rbp+0D8h]; this
0x14002f547  call    ??0ResourceMsg@@QEAA@K@Z; ResourceMsg::ResourceMsg(ulong)
0x14002f54c  nop
0x14002f54d  mov     rcx, rax
0x14002f550  call    ??C?$unique_ptr@VWebRequest@@U?$default_delete@VWebRequest@@@std@@@std@@QEBAPEAVWebRequest@@XZ; std::unique_ptr<WebRequest>::operator->(void)
0x14002f555  mov     rdx, rax
0x14002f558  lea     r9, a88d96a05F19211; "88d96a05-f192-11d4-a65f-0040963251e5"
0x14002f55f  lea     r8, aMsxml2Domdocum; "Msxml2.DOMDocument.6.0"
0x14002f566  lea     rcx, [rbp+20h]
0x14002f56a  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x14002f56f  nop
0x14002f570  lea     rcx, [rbp+0D8h]
0x14002f577  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x14002f57c  lea     rcx, [rbp+20h]
0x14002f580  call    ??C?$unique_ptr@VWebRequest@@U?$default_delete@VWebRequest@@@std@@@std@@QEBAPEAVWebRequest@@XZ; std::unique_ptr<WebRequest>::operator->(void)
0x14002f585  mov     r8, rax; unsigned __int16 *
0x14002f588  mov     edx, 0CAA50001h; unsigned int
0x14002f58d  lea     rcx, [rbp+68h]; this
0x14002f591  call    ??0XmlException@@QEAA@KPEBG@Z; XmlException::XmlException(ulong,ushort const *)
0x14002f596  lea     rdx, _TI2?AVXmlException@@; pThrowInfo
0x14002f59d  lea     rcx, [rbp+68h]; pExceptionObject
0x14002f5a1  call    _CxxThrowException_0
0x14002f5a7  xor     edx, edx; pThrowInfo
0x14002f5a9  xor     ecx, ecx; pExceptionObject
0x14002f5ab  call    _CxxThrowException_0
```
