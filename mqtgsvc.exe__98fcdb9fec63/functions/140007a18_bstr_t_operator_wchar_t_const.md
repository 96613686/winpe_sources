# _bstr_t::operator=(wchar_t const *)

- ea: `0x140007a18`
- end: `0x140007a5e`
- name: `??4_bstr_t@@QEAAAEAV0@PEB_W@Z`
- size: `70`
- prototype: `_bstr_t *__fastcall(_bstr_t *, const wchar_t *)`
- caller_count: `11`
- callee_count: `4`
- tags: ``

## callers

- `0x1400076a8`
- `0x140009994`
- `0x14000f6e0`
- `0x14000fbcc`
- `0x14000fe40`
- `0x1400108d0`
- `0x1400109e0`
- `0x1400120e8`
- `0x140015aec`
- `0x140015c38`
- `0x140016024`

## callees

- `0x140003058`
- `0x140003868`
- `0x140007a18`
- `0x14000ed18`

## pseudocode

```c
_bstr_t *__fastcall _bstr_t::operator=(_bstr_t *a1, const wchar_t *a2)
{
  _bstr_t::Data_t *v4; // rax

  _bstr_t::_Free(a1);
  v4 = (_bstr_t::Data_t *)MmAllocate(0x18u);
  if ( v4 )
    v4 = (_bstr_t::Data_t *)_bstr_t::Data_t::Data_t(v4, a2);
  *(_QWORD *)a1 = v4;
  return a1;
}

```

## disassembly

```asm
0x140007a18  mov     [rsp+arg_8], rbx
0x140007a1d  push    rdi
0x140007a1e  sub     rsp, 20h
0x140007a22  mov     rdi, rdx
0x140007a25  mov     rbx, rcx
0x140007a28  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x140007a2d  mov     ecx, 18h; unsigned __int64
0x140007a32  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x140007a37  mov     [rsp+28h+arg_0], rax
0x140007a3c  test    rax, rax
0x140007a3f  jz      short loc_140007A4D
0x140007a41  mov     rdx, rdi; wchar_t *
0x140007a44  mov     rcx, rax; this
0x140007a47  call    ??0Data_t@_bstr_t@@QEAA@PEB_W@Z; _bstr_t::Data_t::Data_t(wchar_t const *)
0x140007a4c  nop
0x140007a4d  mov     [rbx], rax
0x140007a50  mov     rax, rbx
0x140007a53  mov     rbx, [rsp+28h+arg_8]
0x140007a58  add     rsp, 20h
0x140007a5c  pop     rdi
0x140007a5d  retn
```
