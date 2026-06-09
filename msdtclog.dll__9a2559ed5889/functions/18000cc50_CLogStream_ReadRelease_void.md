# CLogStream::ReadRelease(void)

- ea: `0x18000cc50`
- end: `0x18000cca1`
- name: `?ReadRelease@CLogStream@@MEAAKXZ`
- size: `81`
- prototype: `__int64 __fastcall(CLogStream *this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180015010`

## pseudocode

```c
__int64 __fastcall CLogStream::ReadRelease(CLogStream *this)
{
  char *v1; // rsi
  unsigned int v3; // ebx

  v1 = (char *)this + 16;
  (**((void (__fastcall ***)(char *))this + 2))((char *)this + 16);
  v3 = *((_DWORD *)this + 18);
  --*((_DWORD *)this + 2);
  *((_DWORD *)this + 18) = v3 - 1;
  (*(void (__fastcall **)(char *))(*(_QWORD *)v1 + 8LL))(v1);
  return v3;
}

```

## disassembly

```asm
0x18000cc50  mov     [rsp+arg_0], rbx
0x18000cc55  mov     [rsp+arg_8], rsi
0x18000cc5a  push    rdi
0x18000cc5b  sub     rsp, 20h
0x18000cc5f  lea     rsi, [rcx+10h]
0x18000cc63  mov     rdi, rcx
0x18000cc66  mov     rax, [rsi]
0x18000cc69  mov     rcx, rsi
0x18000cc6c  mov     rax, [rax]
0x18000cc6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc74  mov     ebx, [rdi+48h]
0x18000cc77  mov     rcx, rsi
0x18000cc7a  dec     dword ptr [rdi+8]
0x18000cc7d  lea     edx, [rbx-1]
0x18000cc80  mov     [rdi+48h], edx
0x18000cc83  mov     rdx, [rsi]
0x18000cc86  mov     rax, [rdx+8]
0x18000cc8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc8f  mov     rsi, [rsp+28h+arg_8]
0x18000cc94  mov     eax, ebx
0x18000cc96  mov     rbx, [rsp+28h+arg_0]
0x18000cc9b  add     rsp, 20h
0x18000cc9f  pop     rdi
0x18000cca0  retn
```
