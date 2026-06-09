# CBaseList::RemoveAll(void)

- ea: `0x180006fc0`
- end: `0x180006ffd`
- name: `?RemoveAll@CBaseList@@QEAAXXZ`
- size: `61`
- prototype: `void __fastcall(CBaseList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180006350`
- `0x180006f10`

## callees

- `0x180001008`
- `0x180006fc0`

## pseudocode

```c
void __fastcall CBaseList::RemoveAll(CBaseList *this)
{
  _QWORD *v1; // rdi
  void *v3; // rcx

  v1 = *(_QWORD **)this;
  while ( v1 )
  {
    v3 = v1;
    v1 = (_QWORD *)v1[1];
    operator delete(v3);
  }
  *((_DWORD *)this + 4) = 0;
  *((_QWORD *)this + 1) = 0;
  *(_QWORD *)this = 0;
}

```

## disassembly

```asm
0x180006fc0  mov     [rsp+arg_0], rbx
0x180006fc5  push    rdi
0x180006fc6  sub     rsp, 20h
0x180006fca  mov     rdi, [rcx]
0x180006fcd  mov     rbx, rcx
0x180006fd0  jmp     short loc_180006FE3
0x180006fd2  mov     rcx, rdi; void *
0x180006fd5  mov     edx, 18h; unsigned __int64
0x180006fda  mov     rdi, [rdi+8]
0x180006fde  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180006fe3  test    rdi, rdi
0x180006fe6  jnz     short loc_180006FD2
0x180006fe8  mov     [rbx+10h], edi
0x180006feb  mov     [rbx+8], rdi
0x180006fef  mov     [rbx], rdi
0x180006ff2  mov     rbx, [rsp+28h+arg_0]
0x180006ff7  add     rsp, 20h
0x180006ffb  pop     rdi
0x180006ffc  retn
```
