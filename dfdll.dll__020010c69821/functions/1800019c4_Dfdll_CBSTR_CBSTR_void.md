# Dfdll::CBSTR::~CBSTR(void)

- ea: `0x1800019c4`
- end: `0x1800019f6`
- name: `??1CBSTR@Dfdll@@UEAA@XZ`
- size: `50`
- prototype: `void __fastcall(Dfdll::CBSTR *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18001f03e`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800019db`
- `OLEAUT32!__imp_SysFreeString` at `0x1800019db`

## pseudocode

```c
void __fastcall Dfdll::CBSTR::~CBSTR(BSTR *this)
{
  *this = (BSTR)&Dfdll::CBSTR::`vftable';
  SysFreeString(this[1]);
  this[1] = 0;
  *this = (BSTR)&Dfdll::CObject::`vftable';
}

```

## disassembly

```asm
0x1800019c4  push    rbx
0x1800019c6  sub     rsp, 20h
0x1800019ca  mov     rbx, rcx
0x1800019cd  lea     rax, ??_7CBSTR@Dfdll@@6B@; const Dfdll::CBSTR::`vftable'
0x1800019d4  mov     [rcx], rax
0x1800019d7  mov     rcx, [rcx+8]; bstrString
0x1800019db  call    cs:__imp_SysFreeString
0x1800019e1  and     qword ptr [rbx+8], 0
0x1800019e6  lea     rax, ??_7CObject@Dfdll@@6B@; const Dfdll::CObject::`vftable'
0x1800019ed  mov     [rbx], rax
0x1800019f0  add     rsp, 20h
0x1800019f4  pop     rbx
0x1800019f5  retn
```
