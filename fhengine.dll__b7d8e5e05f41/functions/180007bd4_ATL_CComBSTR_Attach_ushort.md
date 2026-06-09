# ATL::CComBSTR::Attach(ushort *)

- ea: `0x180007bd4`
- end: `0x180007c00`
- name: `?Attach@CComBSTR@ATL@@QEAAXPEAG@Z`
- size: `44`
- prototype: `void __fastcall(BSTR *this, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180009008`
- `0x1800090f8`

## callees

- `0x180007bd4`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180007bec`
- `OLEAUT32!__imp_SysFreeString` at `0x180007bec`

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
0x180007bd4  mov     [rsp+arg_0], rbx
0x180007bd9  push    rdi
0x180007bda  sub     rsp, 20h
0x180007bde  mov     rbx, rdx
0x180007be1  mov     rdi, rcx
0x180007be4  cmp     [rcx], rdx
0x180007be7  jz      short loc_180007BF5
0x180007be9  mov     rcx, [rcx]; bstrString
0x180007bec  call    cs:__imp_SysFreeString
0x180007bf2  mov     [rdi], rbx
0x180007bf5  mov     rbx, [rsp+28h+arg_0]
0x180007bfa  add     rsp, 20h
0x180007bfe  pop     rdi
0x180007bff  retn
```
