# _bstr_t::_bstr_t(ushort const *)

- ea: `0x18000aa2c`
- end: `0x18000aab2`
- name: `??0_bstr_t@@QEAA@PEBG@Z`
- size: `134`
- prototype: `_bstr_t *__fastcall(_bstr_t *this, const unsigned __int16 *)`
- caller_count: `11`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000ac08`
- `0x180012664`
- `0x180012ed4`
- `0x180016ca8`
- `0x180018c6c`
- `0x180019560`
- `0x180019abc`
- `0x180019e58`
- `0x18001a25c`
- `0x18001aa50`
- `0x18001b094`

## callees

- `0x1800034ac`
- `0x18000aa2c`
- `0x1800117c8`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000aa6a`
- `OLEAUT32!__imp_SysAllocString` at `0x18000aa6a`

## pseudocode

```c
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
0x18000aa2c  mov     [rsp+arg_0], rbx
0x18000aa31  mov     [rsp+arg_8], rsi
0x18000aa36  push    rdi
0x18000aa37  sub     rsp, 20h
0x18000aa3b  mov     rsi, rdx
0x18000aa3e  mov     rdi, rcx
0x18000aa41  mov     ecx, 18h; Size
0x18000aa46  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000aa4b  mov     rbx, rax
0x18000aa4e  mov     [rsp+28h+arg_10], rax
0x18000aa53  test    rax, rax
0x18000aa56  jz      short loc_18000AA7F
0x18000aa58  mov     qword ptr [rax+8], 0
0x18000aa60  mov     dword ptr [rax+10h], 1
0x18000aa67  mov     rcx, rsi; psz
0x18000aa6a  call    cs:__imp_SysAllocString
0x18000aa70  mov     [rbx], rax
0x18000aa73  test    rax, rax
0x18000aa76  jnz     short loc_18000AA81
0x18000aa78  test    rsi, rsi
0x18000aa7b  jnz     short loc_18000AAA7
0x18000aa7d  jmp     short loc_18000AA81
0x18000aa7f  xor     ebx, ebx
0x18000aa81  mov     [rdi], rbx
0x18000aa84  test    rbx, rbx
0x18000aa87  jz      short loc_18000AA9C
0x18000aa89  mov     rax, rdi
0x18000aa8c  mov     rbx, [rsp+28h+arg_0]
0x18000aa91  mov     rsi, [rsp+28h+arg_8]
0x18000aa96  add     rsp, 20h
0x18000aa9a  pop     rdi
0x18000aa9b  retn
0x18000aa9c  mov     ecx, 8007000Eh; int
0x18000aaa1  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18000aaa7  mov     ecx, 8007000Eh; int
0x18000aaac  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
