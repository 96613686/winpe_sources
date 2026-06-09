# AtlAssignNoThrow(ATL::CComBSTR &,ushort const *)

- ea: `0x18003a8b0`
- end: `0x18003a8ee`
- name: `?AtlAssignNoThrow@@YAXAEAVCComBSTR@ATL@@PEBG@Z`
- size: `62`
- prototype: `void __fastcall(BSTR *this, OLECHAR *psz)`
- caller_count: `8`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18003aa34`
- `0x18003ada8`
- `0x18003ae5c`
- `0x18003af30`
- `0x18003b034`
- `0x18003b254`
- `0x18003b930`
- `0x18003bb70`

## callees

- `0x18003a954`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18003a8d3`
- `OLEAUT32!__imp_SysAllocString` at `0x18003a8d3`
- `OLEAUT32!__imp_SysFreeString` at `0x18003a8c3`
- `OLEAUT32!__imp_SysFreeString` at `0x18003a8c3`

## pseudocode

```c
void __fastcall AtlAssignNoThrow(BSTR *this, OLECHAR *psz)
{
  unsigned __int16 *v4; // rax

  SysFreeString(*this);
  *this = 0;
  v4 = SysAllocString(psz);
  ATL::CComBSTR::Attach((ATL::CComBSTR *)this, v4);
}

```

## disassembly

```asm
0x18003a8b0  mov     [rsp+arg_0], rbx
0x18003a8b5  push    rdi
0x18003a8b6  sub     rsp, 20h
0x18003a8ba  mov     rdi, rcx
0x18003a8bd  mov     rbx, rdx
0x18003a8c0  mov     rcx, [rcx]; bstrString
0x18003a8c3  call    cs:__imp_SysFreeString
0x18003a8c9  mov     rcx, rbx; psz
0x18003a8cc  mov     qword ptr [rdi], 0
0x18003a8d3  call    cs:__imp_SysAllocString
0x18003a8d9  mov     rdx, rax; unsigned __int16 *
0x18003a8dc  mov     rcx, rdi; this
0x18003a8df  mov     rbx, [rsp+28h+arg_0]
0x18003a8e4  add     rsp, 20h
0x18003a8e8  pop     rdi
0x18003a8e9  jmp     ?Attach@CComBSTR@ATL@@QEAAXPEAG@Z; ATL::CComBSTR::Attach(ushort *)
```
