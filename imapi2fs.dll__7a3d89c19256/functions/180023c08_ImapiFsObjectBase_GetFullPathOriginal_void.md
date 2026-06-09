# ImapiFsObjectBase::GetFullPathOriginal(void)

- ea: `0x180023c08`
- end: `0x180023c3e`
- name: `?GetFullPathOriginal@ImapiFsObjectBase@@QEAAAEBVCComBSTR@ATL@@XZ`
- size: `54`
- prototype: `const struct ATL::CComBSTR *__fastcall(ImapiFsObjectBase *__hidden this)`
- caller_count: `25`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005d7c`
- `0x180007e80`
- `0x1800096bc`
- `0x18000a34c`
- `0x18000d200`
- `0x18000eac0`
- `0x18000f28c`
- `0x180013d64`
- `0x180014d94`
- `0x18001647c`
- `0x180019b40`
- `0x18001c4fc`
- `0x1800208a0`
- `0x1800223c0`
- `0x180022b74`
- `0x180033d5c`
- `0x18003c660`
- `0x18003c9f0`
- `0x18003cdc0`
- `0x18003ee20`
- `0x180040230`
- `0x180040380`
- `0x180043404`
- `0x180044afc`
- `0x180047400`

## callees

- `0x180051fbc`
- `0x180052900`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180023c2e`
- `OLEAUT32!__imp_SysFreeString` at `0x180023c2e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
const struct ATL::CComBSTR *__fastcall ImapiFsObjectBase::GetFullPathOriginal(ImapiFsObjectBase *this)
{
  __int64 InternalFullPathOriginal; // rax
  BSTR bstrString; // [rsp+30h] [rbp+8h] BYREF

  InternalFullPathOriginal = ImapiFsObjectBase::GetInternalFullPathOriginal(this, &bstrString);
  ATL::CComBSTR::operator=((char *)this + 96, InternalFullPathOriginal);
  SysFreeString(bstrString);
  return (ImapiFsObjectBase *)((char *)this + 96);
}

```

## disassembly

```asm
0x180023c08  push    rbx
0x180023c0a  sub     rsp, 20h
0x180023c0e  mov     rbx, rcx
0x180023c11  lea     rdx, [rsp+28h+bstrString]
0x180023c16  call    ?GetInternalFullPathOriginal@ImapiFsObjectBase@@AEAA?AVCComBSTR@ATL@@XZ; ImapiFsObjectBase::GetInternalFullPathOriginal(void)
0x180023c1b  nop
0x180023c1c  mov     rdx, rax
0x180023c1f  lea     rcx, [rbx+60h]
0x180023c23  call    ??4CComBSTR@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CComBSTR::operator=(ATL::CComBSTR const &)
0x180023c28  nop
0x180023c29  mov     rcx, [rsp+28h+bstrString]; bstrString
0x180023c2e  call    cs:__imp_SysFreeString
0x180023c34  lea     rax, [rbx+60h]
0x180023c38  add     rsp, 20h
0x180023c3c  pop     rbx
0x180023c3d  retn
```
