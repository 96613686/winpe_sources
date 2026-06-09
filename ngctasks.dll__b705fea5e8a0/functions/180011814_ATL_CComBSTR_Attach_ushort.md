# ATL::CComBSTR::Attach(ushort *)

- ea: `0x180011814`
- end: `0x180011840`
- name: `?Attach@CComBSTR@ATL@@QEAAXPEAG@Z`
- size: `44`
- prototype: `void __fastcall(BSTR *this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800126e4`
- `0x180013e14`
- `0x180015abc`
- `0x1800161f4`

## callees

- `0x180011814`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18001182c`
- `OLEAUT32!__imp_SysFreeString` at `0x18001182c`

## pseudocode

```c
void __fastcall ATL::CComBSTR::Attach(BSTR *this, unsigned __int16 *a2)
{
  if ( *this != a2 )
  {
    SysFreeString(*this);
    *this = a2;
  }
}

```

## disassembly

```asm
0x180011814  mov     [rsp+arg_0], rbx
0x180011819  push    rdi
0x18001181a  sub     rsp, 20h
0x18001181e  mov     rbx, rdx
0x180011821  mov     rdi, rcx
0x180011824  cmp     [rcx], rdx
0x180011827  jz      short loc_180011835
0x180011829  mov     rcx, [rcx]; bstrString
0x18001182c  call    cs:__imp_SysFreeString
0x180011832  mov     [rdi], rbx
0x180011835  mov     rbx, [rsp+28h+arg_0]
0x18001183a  add     rsp, 20h
0x18001183e  pop     rdi
0x18001183f  retn
```
