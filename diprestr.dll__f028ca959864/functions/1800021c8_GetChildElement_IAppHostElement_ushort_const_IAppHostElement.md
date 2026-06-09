# GetChildElement(IAppHostElement *,ushort const *,IAppHostElement * *)

- ea: `0x1800021c8`
- end: `0x180002227`
- name: `?GetChildElement@@YAJPEAUIAppHostElement@@PEBGPEAPEAU1@@Z`
- size: `95`
- prototype: `int(struct IAppHostElement *, const unsigned __int16 *, struct IAppHostElement **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002604`

## callees

- `0x1800021c8`
- `0x180007010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800021e0`
- `OLEAUT32!__imp_SysAllocString` at `0x1800021e0`
- `OLEAUT32!__imp_SysFreeString` at `0x18000220f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000220f`

## pseudocode

```c
__int64 __fastcall GetChildElement(struct IAppHostElement *a1, const unsigned __int16 *a2, struct IAppHostElement **a3)
{
  BSTR v5; // rax
  OLECHAR *v6; // rdi
  unsigned int v7; // ebx

  v5 = SysAllocString(a2);
  v6 = v5;
  if ( v5 )
  {
    v7 = ((__int64 (__fastcall *)(struct IAppHostElement *, BSTR, struct IAppHostElement **))a1->lpVtbl->GetElementByName)(
           a1,
           v5,
           a3);
    SysFreeString(v6);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v7;
}

```

## disassembly

```asm
0x1800021c8  mov     [rsp+arg_0], rbx
0x1800021cd  mov     [rsp+arg_8], rsi
0x1800021d2  push    rdi
0x1800021d3  sub     rsp, 20h
0x1800021d7  mov     rbx, rcx
0x1800021da  mov     rsi, r8
0x1800021dd  mov     rcx, rdx; psz
0x1800021e0  call    cs:__imp_SysAllocString
0x1800021e6  mov     rdi, rax
0x1800021e9  test    rax, rax
0x1800021ec  jnz     short loc_1800021F5
0x1800021ee  mov     ebx, 8007000Eh
0x1800021f3  jmp     short loc_180002215
0x1800021f5  mov     rax, [rbx]
0x1800021f8  mov     r8, rsi
0x1800021fb  mov     rdx, rdi
0x1800021fe  mov     rcx, rbx
0x180002201  mov     rax, [rax+50h]
0x180002205  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000220a  mov     ebx, eax
0x18000220c  mov     rcx, rdi; bstrString
0x18000220f  call    cs:__imp_SysFreeString
0x180002215  mov     rsi, [rsp+28h+arg_8]
0x18000221a  mov     eax, ebx
0x18000221c  mov     rbx, [rsp+28h+arg_0]
0x180002221  add     rsp, 20h
0x180002225  pop     rdi
0x180002226  retn
```
