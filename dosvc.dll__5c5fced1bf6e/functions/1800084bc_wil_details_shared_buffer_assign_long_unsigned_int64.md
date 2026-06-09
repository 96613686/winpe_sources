# wil::details::shared_buffer::assign(long *,unsigned __int64)

- ea: `0x1800084bc`
- end: `0x1800084f8`
- name: `?assign@shared_buffer@details@wil@@AEAAXPEAJ_K@Z`
- size: `60`
- prototype: `void __fastcall(wil::details::shared_buffer *this, int *, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180006490`
- `0x1800064fc`
- `0x180007b88`
- `0x180008610`

## callees

- `0x1800084bc`
- `0x1800085ac`

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
0x1800084bc  mov     [rsp+arg_0], rbx
0x1800084c1  mov     [rsp+arg_8], rsi
0x1800084c6  push    rdi
0x1800084c7  sub     rsp, 20h
0x1800084cb  mov     rsi, r8
0x1800084ce  mov     rbx, rdx
0x1800084d1  mov     rdi, rcx
0x1800084d4  call    ?reset@shared_buffer@details@wil@@QEAAXXZ; wil::details::shared_buffer::reset(void)
0x1800084d9  test    rbx, rbx
0x1800084dc  jz      short loc_1800084E8
0x1800084de  mov     [rdi], rbx
0x1800084e1  mov     [rdi+8], rsi
0x1800084e5  lock inc dword ptr [rbx]
0x1800084e8  mov     rbx, [rsp+28h+arg_0]
0x1800084ed  mov     rsi, [rsp+28h+arg_8]
0x1800084f2  add     rsp, 20h
0x1800084f6  pop     rdi
0x1800084f7  retn
```
