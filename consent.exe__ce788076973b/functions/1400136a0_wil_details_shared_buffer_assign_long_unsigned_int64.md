# wil::details::shared_buffer::assign(long *,unsigned __int64)

- ea: `0x1400136a0`
- end: `0x1400136dc`
- name: `?assign@shared_buffer@details@wil@@AEAAXPEAJ_K@Z`
- size: `60`
- prototype: `void __fastcall(wil::details::shared_buffer *this, int *, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1400116fc`
- `0x140011768`
- `0x1400131ac`
- `0x1400137f0`

## callees

- `0x1400136a0`
- `0x140013790`

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
0x1400136a0  mov     [rsp+arg_0], rbx
0x1400136a5  mov     [rsp+arg_8], rsi
0x1400136aa  push    rdi
0x1400136ab  sub     rsp, 20h
0x1400136af  mov     rsi, r8
0x1400136b2  mov     rbx, rdx
0x1400136b5  mov     rdi, rcx
0x1400136b8  call    ?reset@shared_buffer@details@wil@@QEAAXXZ; wil::details::shared_buffer::reset(void)
0x1400136bd  test    rbx, rbx
0x1400136c0  jz      short loc_1400136CC
0x1400136c2  mov     [rdi], rbx
0x1400136c5  mov     [rdi+8], rsi
0x1400136c9  lock inc dword ptr [rbx]
0x1400136cc  mov     rbx, [rsp+28h+arg_0]
0x1400136d1  mov     rsi, [rsp+28h+arg_8]
0x1400136d6  add     rsp, 20h
0x1400136da  pop     rdi
0x1400136db  retn
```
