# _bstr_t::_bstr_t(wchar_t const *)

- ea: `0x18000544c`
- end: `0x18000549d`
- name: `??0_bstr_t@@QEAA@PEB_W@Z`
- size: `81`
- prototype: `_bstr_t *__fastcall(_bstr_t *this, const wchar_t *)`
- caller_count: `38`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800057ec`
- `0x180005df4`
- `0x180006bec`
- `0x180006ef0`
- `0x1800082b8`
- `0x180008380`
- `0x1800084d0`
- `0x180008d68`
- `0x180009420`
- `0x1800097c8`
- `0x18000a300`
- `0x18000aa80`
- `0x18000aea0`
- `0x18000b760`
- `0x18000bda0`
- `0x18000ce94`
- `0x18000d0e0`
- `0x18000d1a0`
- `0x18000d250`
- `0x18000d310`
- `0x18000d3d0`
- `0x18000d480`
- `0x18000d520`
- `0x180010590`
- `0x180010b60`
- `0x180010ea0`
- `0x180011160`
- `0x180011330`
- `0x180011778`
- `0x180011b60`
- `0x180012100`
- `0x180012770`
- `0x180012f40`
- `0x180015f38`
- `0x1800176ec`
- `0x18001792c`
- `0x180019230`
- `0x18001a358`

## callees

- `0x180005358`
- `0x18000544c`
- `0x180014920`
- `0x180014ae8`

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
0x18000544c  mov     [rsp+arg_8], rbx
0x180005451  push    rdi
0x180005452  sub     rsp, 20h
0x180005456  mov     rdi, rdx
0x180005459  mov     rbx, rcx
0x18000545c  mov     ecx, 18h; unsigned __int64
0x180005461  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180005466  mov     [rsp+28h+arg_0], rax
0x18000546b  test    rax, rax
0x18000546e  jz      short loc_18000547C
0x180005470  mov     rdx, rdi; wchar_t *
0x180005473  mov     rcx, rax; this
0x180005476  call    ??0Data_t@_bstr_t@@QEAA@PEB_W@Z; _bstr_t::Data_t::Data_t(wchar_t const *)
0x18000547b  nop
0x18000547c  mov     [rbx], rax
0x18000547f  test    rax, rax
0x180005482  jnz     short loc_18000548F
0x180005484  mov     ecx, 8007000Eh; int
0x180005489  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18000548f  mov     rax, rbx
0x180005492  mov     rbx, [rsp+28h+arg_8]
0x180005497  add     rsp, 20h
0x18000549b  pop     rdi
0x18000549c  retn
```
