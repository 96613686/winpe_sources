# wil::details::shared_buffer::assign(long *,unsigned __int64)

- ea: `0x180009a28`
- end: `0x180009a64`
- name: `?assign@shared_buffer@details@wil@@AEAAXPEAJ_K@Z`
- size: `60`
- prototype: `void __fastcall(wil::details::shared_buffer *this, int *, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180005734`
- `0x1800057a0`
- `0x180008ac8`
- `0x180009f80`

## callees

- `0x180009a28`
- `0x180009f28`

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
0x180009a28  mov     [rsp+arg_0], rbx
0x180009a2d  mov     [rsp+arg_8], rsi
0x180009a32  push    rdi
0x180009a33  sub     rsp, 20h
0x180009a37  mov     rsi, r8
0x180009a3a  mov     rbx, rdx
0x180009a3d  mov     rdi, rcx
0x180009a40  call    ?reset@shared_buffer@details@wil@@QEAAXXZ; wil::details::shared_buffer::reset(void)
0x180009a45  test    rbx, rbx
0x180009a48  jz      short loc_180009A54
0x180009a4a  mov     [rdi], rbx
0x180009a4d  mov     [rdi+8], rsi
0x180009a51  lock inc dword ptr [rbx]
0x180009a54  mov     rbx, [rsp+28h+arg_0]
0x180009a59  mov     rsi, [rsp+28h+arg_8]
0x180009a5e  add     rsp, 20h
0x180009a62  pop     rdi
0x180009a63  retn
```
