# _bstr_t::operator+=(_bstr_t const &)

- ea: `0x180007894`
- end: `0x180007932`
- name: `??Y_bstr_t@@QEAAAEAV0@AEBV0@@Z`
- size: `158`
- prototype: `__int64 __fastcall(struct _bstr_t *, struct _bstr_t *)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000784c`
- `0x1800093cc`
- `0x180009af8`

## callees

- `0x180002310`
- `0x180007370`
- `0x180007894`

## import_xrefs

- `msvcrt!free` at `0x180007905`
- `msvcrt!free` at `0x180007916`
- `msvcrt!free` at `0x180007905`
- `msvcrt!free` at `0x180007916`
- `OLEAUT32!__imp_SysFreeString` at `0x1800078ef`
- `OLEAUT32!__imp_SysFreeString` at `0x1800078ef`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct _bstr_t *__fastcall _bstr_t::operator+=(struct _bstr_t *a1, struct _bstr_t *a2)
{
  _bstr_t::Data_t *v4; // rax
  __int64 v5; // rsi
  __int64 v6; // rbx
  void *v7; // rcx

  v4 = (_bstr_t::Data_t *)operator new(0x18u);
  if ( v4 )
    v5 = _bstr_t::Data_t::Data_t(v4, a1, a2);
  else
    v5 = 0;
  v6 = *(_QWORD *)a1;
  if ( *(_QWORD *)a1 && _InterlockedExchangeAdd((volatile signed __int32 *)(v6 + 16), 0xFFFFFFFF) == 1 )
  {
    if ( *(_QWORD *)v6 )
    {
      SysFreeString(*(BSTR *)v6);
      *(_QWORD *)v6 = 0;
    }
    v7 = *(void **)(v6 + 8);
    if ( v7 )
    {
      free(v7);
      *(_QWORD *)(v6 + 8) = 0;
    }
    free((void *)v6);
  }
  *(_QWORD *)a1 = v5;
  return a1;
}

```

## disassembly

```asm
0x180007894  mov     [rsp+arg_8], rbx
0x180007899  mov     [rsp+arg_10], rsi
0x18000789e  push    rdi
0x18000789f  sub     rsp, 20h
0x1800078a3  mov     rbx, rdx
0x1800078a6  mov     rdi, rcx
0x1800078a9  mov     ecx, 18h; Size
0x1800078ae  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800078b3  mov     [rsp+28h+arg_0], rax
0x1800078b8  test    rax, rax
0x1800078bb  jz      short loc_1800078D0
0x1800078bd  mov     r8, rbx; struct _bstr_t *
0x1800078c0  mov     rdx, rdi; struct _bstr_t *
0x1800078c3  mov     rcx, rax; this
0x1800078c6  call    ??0Data_t@_bstr_t@@QEAA@AEBV1@0@Z; _bstr_t::Data_t::Data_t(_bstr_t const &,_bstr_t const &)
0x1800078cb  mov     rsi, rax
0x1800078ce  jmp     short loc_1800078D2
0x1800078d0  xor     esi, esi
0x1800078d2  mov     rbx, [rdi]
0x1800078d5  test    rbx, rbx
0x1800078d8  jz      short loc_18000791C
0x1800078da  or      eax, 0FFFFFFFFh
0x1800078dd  lock xadd [rbx+10h], eax
0x1800078e2  cmp     eax, 1
0x1800078e5  jnz     short loc_18000791C
0x1800078e7  mov     rcx, [rbx]; bstrString
0x1800078ea  test    rcx, rcx
0x1800078ed  jz      short loc_1800078FC
0x1800078ef  call    cs:__imp_SysFreeString
0x1800078f5  mov     qword ptr [rbx], 0
0x1800078fc  mov     rcx, [rbx+8]; Block
0x180007900  test    rcx, rcx
0x180007903  jz      short loc_180007913
0x180007905  call    cs:__imp_free
0x18000790b  mov     qword ptr [rbx+8], 0
0x180007913  mov     rcx, rbx; Block
0x180007916  call    cs:__imp_free
0x18000791c  mov     [rdi], rsi
0x18000791f  mov     rax, rdi
0x180007922  mov     rbx, [rsp+28h+arg_8]
0x180007927  mov     rsi, [rsp+28h+arg_10]
0x18000792c  add     rsp, 20h
0x180007930  pop     rdi
0x180007931  retn
```
