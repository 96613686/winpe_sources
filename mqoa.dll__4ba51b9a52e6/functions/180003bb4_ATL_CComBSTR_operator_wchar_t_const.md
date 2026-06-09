# ATL::CComBSTR::operator=(wchar_t const *)

- ea: `0x180003bb4`
- end: `0x180003be7`
- name: `??4CComBSTR@ATL@@QEAAAEAV01@PEB_W@Z`
- size: `51`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180008960`
- `0x180022be0`
- `0x180022f80`
- `0x1800230fc`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180003bd0`
- `OLEAUT32!__imp_SysAllocString` at `0x180003bd0`
- `OLEAUT32!__imp_SysFreeString` at `0x180003bc7`
- `OLEAUT32!__imp_SysFreeString` at `0x180003bc7`

## pseudocode

```c
BSTR *__fastcall ATL::CComBSTR::operator=(BSTR *a1, const OLECHAR *a2)
{
  SysFreeString(*a1);
  *a1 = SysAllocString(a2);
  return a1;
}

```

## disassembly

```asm
0x180003bb4  mov     [rsp+arg_0], rbx
0x180003bb9  push    rdi
0x180003bba  sub     rsp, 20h
0x180003bbe  mov     rdi, rcx
0x180003bc1  mov     rbx, rdx
0x180003bc4  mov     rcx, [rcx]; bstrString
0x180003bc7  call    cs:__imp_SysFreeString
0x180003bcd  mov     rcx, rbx; psz
0x180003bd0  call    cs:__imp_SysAllocString
0x180003bd6  mov     rbx, [rsp+28h+arg_0]
0x180003bdb  mov     [rdi], rax
0x180003bde  mov     rax, rdi
0x180003be1  add     rsp, 20h
0x180003be5  pop     rdi
0x180003be6  retn
```
