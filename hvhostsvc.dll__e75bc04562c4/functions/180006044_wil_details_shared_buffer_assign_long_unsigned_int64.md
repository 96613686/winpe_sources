# wil::details::shared_buffer::assign(long *,unsigned __int64)

- ea: `0x180006044`
- end: `0x180006080`
- name: `?assign@shared_buffer@details@wil@@AEAAXPEAJ_K@Z`
- size: `60`
- prototype: `void __fastcall(wil::details::shared_buffer *this, int *, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180003620`
- `0x18000368c`
- `0x1800056c8`
- `0x180006190`

## callees

- `0x180006044`
- `0x180006134`

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
0x180006044  mov     [rsp+arg_0], rbx
0x180006049  mov     [rsp+arg_8], rsi
0x18000604e  push    rdi
0x18000604f  sub     rsp, 20h
0x180006053  mov     rsi, r8
0x180006056  mov     rbx, rdx
0x180006059  mov     rdi, rcx
0x18000605c  call    ?reset@shared_buffer@details@wil@@QEAAXXZ; wil::details::shared_buffer::reset(void)
0x180006061  test    rbx, rbx
0x180006064  jz      short loc_180006070
0x180006066  mov     [rdi], rbx
0x180006069  mov     [rdi+8], rsi
0x18000606d  lock inc dword ptr [rbx]
0x180006070  mov     rbx, [rsp+28h+arg_0]
0x180006075  mov     rsi, [rsp+28h+arg_8]
0x18000607a  add     rsp, 20h
0x18000607e  pop     rdi
0x18000607f  retn
```
