# Dfdll::CBufferBase::Release(void)

- ea: `0x180003c40`
- end: `0x180003c77`
- name: `?Release@CBufferBase@Dfdll@@QEAAXXZ`
- size: `55`
- prototype: `void __fastcall(Dfdll::CBufferBase *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180007a7c`

## callees

- `0x18001efd0`

## pseudocode

```c
void __fastcall Dfdll::CBufferBase::Release(Dfdll::CBufferBase *this)
{
  _DWORD *v1; // rdi
  _QWORD *v2; // rbx

  v1 = (_DWORD *)((char *)this + 16);
  v2 = (_QWORD *)((char *)this + 8);
  (*(void (__fastcall **)(Dfdll::CBufferBase *, char *, char *))(*(_QWORD *)this + 88LL))(
    this,
    (char *)this + 8,
    (char *)this + 16);
  *v2 = 0;
  *v1 = 0;
}

```

## disassembly

```asm
0x180003c40  mov     [rsp+arg_0], rbx
0x180003c45  push    rdi
0x180003c46  sub     rsp, 20h
0x180003c4a  mov     rax, [rcx]
0x180003c4d  lea     rdi, [rcx+10h]
0x180003c51  lea     rbx, [rcx+8]
0x180003c55  mov     r8, rdi
0x180003c58  mov     rdx, rbx
0x180003c5b  mov     rax, [rax+58h]
0x180003c5f  call    cs:__guard_dispatch_icall_fptr
0x180003c65  and     qword ptr [rbx], 0
0x180003c69  and     dword ptr [rdi], 0
0x180003c6c  mov     rbx, [rsp+28h+arg_0]
0x180003c71  add     rsp, 20h
0x180003c75  pop     rdi
0x180003c76  retn
```
