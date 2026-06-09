# wil::details::shared_buffer::assign(long *,unsigned __int64)

- ea: `0x180009f58`
- end: `0x180009f94`
- name: `?assign@shared_buffer@details@wil@@AEAAXPEAJ_K@Z`
- size: `60`
- prototype: `void __fastcall(wil::details::shared_buffer *this, int *, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180005bf0`
- `0x180005c5c`
- `0x180008ec8`
- `0x18000a1a0`

## callees

- `0x180009f58`
- `0x18000a144`

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
0x180009f58  mov     [rsp+arg_0], rbx
0x180009f5d  mov     [rsp+arg_8], rsi
0x180009f62  push    rdi
0x180009f63  sub     rsp, 20h
0x180009f67  mov     rsi, r8
0x180009f6a  mov     rbx, rdx
0x180009f6d  mov     rdi, rcx
0x180009f70  call    ?reset@shared_buffer@details@wil@@QEAAXXZ; wil::details::shared_buffer::reset(void)
0x180009f75  test    rbx, rbx
0x180009f78  jz      short loc_180009F84
0x180009f7a  mov     [rdi], rbx
0x180009f7d  mov     [rdi+8], rsi
0x180009f81  lock inc dword ptr [rbx]
0x180009f84  mov     rbx, [rsp+28h+arg_0]
0x180009f89  mov     rsi, [rsp+28h+arg_8]
0x180009f8e  add     rsp, 20h
0x180009f92  pop     rdi
0x180009f93  retn
```
