# CBaseList::RemoveAll(void)

- ea: `0x18002b684`
- end: `0x18002b6c2`
- name: `?RemoveAll@CBaseList@@QEAAXXZ`
- size: `62`
- prototype: `void __fastcall(CBaseList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180028480`
- `0x18002b5d0`

## callees

- `0x180001b80`
- `0x18002b684`

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
0x18002b684  mov     [rsp+arg_0], rbx
0x18002b689  push    rdi
0x18002b68a  sub     rsp, 20h
0x18002b68e  mov     rdi, [rcx]
0x18002b691  mov     rbx, rcx
0x18002b694  jmp     short loc_18002B6A7
0x18002b696  mov     rcx, rdi; Block
0x18002b699  mov     edx, 18h
0x18002b69e  mov     rdi, [rdi+8]
0x18002b6a2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002b6a7  test    rdi, rdi
0x18002b6aa  jnz     short loc_18002B696
0x18002b6ac  mov     [rbx+10h], edi
0x18002b6af  mov     [rbx+8], rdi
0x18002b6b3  mov     [rbx], rdi
0x18002b6b6  mov     rbx, [rsp+28h+arg_0]
0x18002b6bb  add     rsp, 20h
0x18002b6bf  pop     rdi
0x18002b6c0  retn
```
