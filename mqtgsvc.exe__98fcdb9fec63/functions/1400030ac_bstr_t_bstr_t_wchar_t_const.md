# _bstr_t::_bstr_t(wchar_t const *)

- ea: `0x1400030ac`
- end: `0x1400030fd`
- name: `??0_bstr_t@@QEAA@PEB_W@Z`
- size: `81`
- prototype: `_bstr_t *__fastcall(_bstr_t *this, const wchar_t *)`
- caller_count: `16`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400061d4`
- `0x1400076a8`
- `0x14000858c`
- `0x140009358`
- `0x14000a6dc`
- `0x14000b2f0`
- `0x14000b6f0`
- `0x14000baa8`
- `0x14000d00c`
- `0x14000d4a8`
- `0x14000d648`
- `0x14000eb04`
- `0x14000fbcc`
- `0x14000fe40`
- `0x1400115c8`
- `0x1400120e8`

## callees

- `0x140003058`
- `0x1400030ac`
- `0x14000ec24`
- `0x14000ed18`

## pseudocode

```c
_bstr_t *__fastcall _bstr_t::_bstr_t(_bstr_t *this, const wchar_t *a2)
{
  _bstr_t::Data_t *v4; // rax

  v4 = (_bstr_t::Data_t *)MmAllocate(0x18u);
  if ( v4 )
    v4 = (_bstr_t::Data_t *)_bstr_t::Data_t::Data_t(v4, a2);
  *(_QWORD *)this = v4;
  if ( !v4 )
    _com_issue_error(-2147024882);
  return this;
}

```

## disassembly

```asm
0x1400030ac  mov     [rsp+arg_8], rbx
0x1400030b1  push    rdi
0x1400030b2  sub     rsp, 20h
0x1400030b6  mov     rdi, rdx
0x1400030b9  mov     rbx, rcx
0x1400030bc  mov     ecx, 18h; unsigned __int64
0x1400030c1  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x1400030c6  mov     [rsp+28h+arg_0], rax
0x1400030cb  test    rax, rax
0x1400030ce  jz      short loc_1400030DC
0x1400030d0  mov     rdx, rdi; wchar_t *
0x1400030d3  mov     rcx, rax; this
0x1400030d6  call    ??0Data_t@_bstr_t@@QEAA@PEB_W@Z; _bstr_t::Data_t::Data_t(wchar_t const *)
0x1400030db  nop
0x1400030dc  mov     [rbx], rax
0x1400030df  test    rax, rax
0x1400030e2  jnz     short loc_1400030EF
0x1400030e4  mov     ecx, 8007000Eh; int
0x1400030e9  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1400030ef  mov     rax, rbx
0x1400030f2  mov     rbx, [rsp+28h+arg_8]
0x1400030f7  add     rsp, 20h
0x1400030fb  pop     rdi
0x1400030fc  retn
```
