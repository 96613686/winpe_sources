# _bstr_t::_bstr_t(ushort const *)

- ea: `0x180007628`
- end: `0x1800076ae`
- name: `??0_bstr_t@@QEAA@PEBG@Z`
- size: `134`
- prototype: `_bstr_t *(_bstr_t *__hidden this, const unsigned __int16 *)`
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800079fc`
- `0x1800081b8`
- `0x1800086c8`
- `0x180009af8`
- `0x18000a4a0`
- `0x18000b210`

## callees

- `0x180002310`
- `0x180007628`
- `0x18000db68`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180007666`
- `OLEAUT32!__imp_SysAllocString` at `0x180007666`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_bstr_t *__fastcall _bstr_t::_bstr_t(_bstr_t *this, const unsigned __int16 *a2)
{
  BSTR *v4; // rax
  BSTR *v5; // rbx
  BSTR v6; // rax

  v4 = (BSTR *)operator new(0x18u);
  v5 = v4;
  if ( v4 )
  {
    v4[1] = 0;
    *((_DWORD *)v4 + 4) = 1;
    v6 = SysAllocString(a2);
    *v5 = v6;
    if ( !v6 && a2 )
      _com_issue_error(-2147024882);
  }
  else
  {
    v5 = 0;
  }
  *(_QWORD *)this = v5;
  if ( !v5 )
    _com_issue_error(-2147024882);
  return this;
}

```

## disassembly

```asm
0x180007628  mov     [rsp+arg_0], rbx
0x18000762d  mov     [rsp+arg_8], rsi
0x180007632  push    rdi
0x180007633  sub     rsp, 20h
0x180007637  mov     rsi, rdx
0x18000763a  mov     rdi, rcx
0x18000763d  mov     ecx, 18h; Size
0x180007642  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007647  mov     rbx, rax
0x18000764a  mov     [rsp+28h+arg_10], rax
0x18000764f  test    rax, rax
0x180007652  jz      short loc_18000767B
0x180007654  mov     qword ptr [rax+8], 0
0x18000765c  mov     dword ptr [rax+10h], 1
0x180007663  mov     rcx, rsi; psz
0x180007666  call    cs:__imp_SysAllocString
0x18000766c  mov     [rbx], rax
0x18000766f  test    rax, rax
0x180007672  jnz     short loc_18000767D
0x180007674  test    rsi, rsi
0x180007677  jnz     short loc_1800076A3
0x180007679  jmp     short loc_18000767D
0x18000767b  xor     ebx, ebx
0x18000767d  mov     [rdi], rbx
0x180007680  test    rbx, rbx
0x180007683  jz      short loc_180007698
0x180007685  mov     rax, rdi
0x180007688  mov     rbx, [rsp+28h+arg_0]
0x18000768d  mov     rsi, [rsp+28h+arg_8]
0x180007692  add     rsp, 20h
0x180007696  pop     rdi
0x180007697  retn
0x180007698  mov     ecx, 8007000Eh; int
0x18000769d  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1800076a3  mov     ecx, 8007000Eh; int
0x1800076a8  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
