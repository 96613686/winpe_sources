# wil::details::shared_buffer::assign(long *,unsigned __int64)

- ea: `0x1400065e4`
- end: `0x140006620`
- name: `?assign@shared_buffer@details@wil@@AEAAXPEAJ_K@Z`
- size: `60`
- prototype: `void __fastcall(wil::details::shared_buffer *this, int *, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140003d74`
- `0x140003de0`
- `0x140005bf0`
- `0x1400067a0`

## callees

- `0x1400065e4`
- `0x14000673c`

## pseudocode

```c
void __fastcall wil::details::shared_buffer::assign(wil::details::shared_buffer *this, int *a2, __int64 a3)
{
  wil::details::shared_buffer::reset(this);
  if ( a2 )
  {
    *(_QWORD *)this = a2;
    *((_QWORD *)this + 1) = a3;
    _InterlockedIncrement(a2);
  }
}

```

## disassembly

```asm
0x1400065e4  mov     [rsp+arg_0], rbx
0x1400065e9  mov     [rsp+arg_8], rsi
0x1400065ee  push    rdi
0x1400065ef  sub     rsp, 20h
0x1400065f3  mov     rsi, r8
0x1400065f6  mov     rbx, rdx
0x1400065f9  mov     rdi, rcx
0x1400065fc  call    ?reset@shared_buffer@details@wil@@QEAAXXZ; wil::details::shared_buffer::reset(void)
0x140006601  test    rbx, rbx
0x140006604  jz      short loc_140006610
0x140006606  mov     [rdi], rbx
0x140006609  mov     [rdi+8], rsi
0x14000660d  lock inc dword ptr [rbx]
0x140006610  mov     rbx, [rsp+28h+arg_0]
0x140006615  mov     rsi, [rsp+28h+arg_8]
0x14000661a  add     rsp, 20h
0x14000661e  pop     rdi
0x14000661f  retn
```
