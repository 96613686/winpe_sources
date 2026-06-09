# Dfdll::CBufferBase::Allocate(uint)

- ea: `0x180001fc8`
- end: `0x18000203f`
- name: `?Allocate@CBufferBase@Dfdll@@QEAAJI@Z`
- size: `119`
- prototype: `__int64 __fastcall(Dfdll::CBufferBase *__hidden this, unsigned int)`
- caller_count: `12`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800020d4`
- `0x180002238`
- `0x180002b80`
- `0x180002e44`
- `0x180002ff8`
- `0x180003b58`
- `0x180003e88`
- `0x180007a7c`
- `0x18001138c`
- `0x18001140c`
- `0x18001179c`
- `0x180012140`

## callees

- `0x180001fc8`
- `0x18001efd0`

## pseudocode

```c
__int64 __fastcall Dfdll::CBufferBase::Allocate(Dfdll::CBufferBase *this, unsigned int a2)
{
  unsigned int *v2; // rsi
  __int64 *v3; // rdi
  __int64 v6; // rax
  __int64 v7; // rax

  v2 = (unsigned int *)((char *)this + 16);
  v3 = (__int64 *)((char *)this + 8);
  (*(void (__fastcall **)(Dfdll::CBufferBase *, char *, char *))(*(_QWORD *)this + 88LL))(
    this,
    (char *)this + 8,
    (char *)this + 16);
  v6 = *(_QWORD *)this;
  *v3 = 0;
  *v2 = 0;
  v7 = (*(__int64 (__fastcall **)(Dfdll::CBufferBase *, _QWORD))(v6 + 80))(this, a2);
  *v3 = v7;
  if ( v7 )
  {
    *v2 = a2;
    return 0;
  }
  else
  {
    *v2 = 0;
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180001fc8  mov     [rsp+arg_0], rbx
0x180001fcd  mov     [rsp+arg_8], rbp
0x180001fd2  mov     [rsp+arg_10], rsi
0x180001fd7  push    rdi
0x180001fd8  sub     rsp, 20h
0x180001fdc  mov     rax, [rcx]
0x180001fdf  lea     rsi, [rcx+10h]
0x180001fe3  lea     rdi, [rcx+8]
0x180001fe7  mov     ebp, edx
0x180001fe9  mov     r8, rsi
0x180001fec  mov     rdx, rdi
0x180001fef  mov     rbx, rcx
0x180001ff2  mov     rax, [rax+58h]
0x180001ff6  call    cs:__guard_dispatch_icall_fptr
0x180001ffc  mov     rax, [rbx]
0x180001fff  mov     edx, ebp
0x180002001  and     qword ptr [rdi], 0
0x180002005  mov     rcx, rbx
0x180002008  and     dword ptr [rsi], 0
0x18000200b  mov     rax, [rax+50h]
0x18000200f  call    cs:__guard_dispatch_icall_fptr
0x180002015  mov     [rdi], rax
0x180002018  test    rax, rax
0x18000201b  jnz     short loc_180002026
0x18000201d  and     [rsi], eax
0x18000201f  mov     eax, 8007000Eh
0x180002024  jmp     short loc_18000202A
0x180002026  mov     [rsi], ebp
0x180002028  xor     eax, eax
0x18000202a  mov     rbx, [rsp+28h+arg_0]
0x18000202f  mov     rbp, [rsp+28h+arg_8]
0x180002034  mov     rsi, [rsp+28h+arg_10]
0x180002039  add     rsp, 20h
0x18000203d  pop     rdi
0x18000203e  retn
```
