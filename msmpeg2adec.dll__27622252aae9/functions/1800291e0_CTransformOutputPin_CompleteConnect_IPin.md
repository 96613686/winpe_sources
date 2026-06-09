# CTransformOutputPin::CompleteConnect(IPin *)

- ea: `0x1800291e0`
- end: `0x180029231`
- name: `?CompleteConnect@CTransformOutputPin@@UEAAJPEAUIPin@@@Z`
- size: `81`
- prototype: `__int64 __fastcall(CTransformOutputPin *__hidden this, struct IPin *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800291e0`
- `0x180088750`

## pseudocode

```c
__int64 __fastcall CTransformOutputPin::CompleteConnect(CTransformOutputPin *this, struct IPin *a2)
{
  __int64 result; // rax

  result = (*(__int64 (__fastcall **)(_QWORD, __int64, struct IPin *))(**((_QWORD **)this + 29) + 160LL))(
             *((_QWORD *)this + 29),
             1,
             a2);
  if ( (int)result >= 0 )
    return (*(__int64 (__fastcall **)(CTransformOutputPin *, _QWORD, char *))(*(_QWORD *)this + 112LL))(
             this,
             *((_QWORD *)this + 28),
             (char *)this + 216);
  return result;
}

```

## disassembly

```asm
0x1800291e0  push    rbx
0x1800291e2  sub     rsp, 20h
0x1800291e6  mov     rbx, rcx
0x1800291e9  mov     r8, rdx
0x1800291ec  mov     rcx, [rcx+0E8h]
0x1800291f3  mov     edx, 1
0x1800291f8  mov     rax, [rcx]
0x1800291fb  mov     rax, [rax+0A0h]
0x180029202  call    cs:__guard_dispatch_icall_fptr
0x180029208  test    eax, eax
0x18002920a  js      short loc_18002922A
0x18002920c  mov     rax, [rbx]
0x18002920f  lea     r8, [rbx+0D8h]
0x180029216  mov     rdx, [rbx+0E0h]
0x18002921d  mov     rcx, rbx
0x180029220  mov     rax, [rax+70h]
0x180029224  call    cs:__guard_dispatch_icall_fptr
0x18002922a  add     rsp, 20h
0x18002922e  pop     rbx
0x18002922f  retn
```
