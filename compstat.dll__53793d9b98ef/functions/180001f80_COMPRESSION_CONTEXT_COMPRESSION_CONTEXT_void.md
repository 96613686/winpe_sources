# COMPRESSION_CONTEXT::COMPRESSION_CONTEXT(void)

- ea: `0x180001f80`
- end: `0x180001ff0`
- name: `??0COMPRESSION_CONTEXT@@QEAA@XZ`
- size: `112`
- prototype: `COMPRESSION_CONTEXT *__fastcall(COMPRESSION_CONTEXT *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001310`

## import_xrefs

- `iisutil!??0BUFFER@@QEAA@XZ` at `0x180001fac`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x180001fac`

## pseudocode

```c
COMPRESSION_CONTEXT *__fastcall COMPRESSION_CONTEXT::COMPRESSION_CONTEXT(COMPRESSION_CONTEXT *this)
{
  COMPRESSION_CONTEXT *result; // rax

  *(_QWORD *)this = &COMPRESSION_CONTEXT::`vftable';
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_DWORD *)this + 6) = 0;
  *((_QWORD *)this + 4) = 0;
  BUFFER::BUFFER((COMPRESSION_CONTEXT *)((char *)this + 40));
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 19) = (char *)this + 144;
  *((_QWORD *)this + 18) = (char *)this + 144;
  result = this;
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 17) = 0;
  *((_DWORD *)this + 40) = 0;
  *((_DWORD *)this + 41) = 1;
  return result;
}

```

## disassembly

```asm
0x180001f80  mov     [rsp+arg_0], rbx
0x180001f85  push    rdi
0x180001f86  sub     rsp, 20h
0x180001f8a  xor     edi, edi
0x180001f8c  lea     rax, ??_7COMPRESSION_CONTEXT@@6B@; const COMPRESSION_CONTEXT::`vftable'
0x180001f93  mov     [rcx], rax
0x180001f96  mov     rbx, rcx
0x180001f99  mov     [rcx+8], rdi
0x180001f9d  mov     [rcx+10h], rdi
0x180001fa1  mov     [rcx+18h], edi
0x180001fa4  mov     [rcx+20h], rdi
0x180001fa8  add     rcx, 28h ; '('
0x180001fac  call    cs:__imp_??0BUFFER@@QEAA@XZ; BUFFER::BUFFER(void)
0x180001fb2  lea     rax, [rbx+90h]
0x180001fb9  mov     [rbx+78h], rdi
0x180001fbd  mov     [rax+8], rax
0x180001fc1  mov     [rax], rax
0x180001fc4  mov     rax, rbx
0x180001fc7  mov     [rbx+80h], rdi
0x180001fce  mov     [rbx+88h], rdi
0x180001fd5  mov     [rbx+0A0h], edi
0x180001fdb  mov     dword ptr [rbx+0A4h], 1
0x180001fe5  mov     rbx, [rsp+28h+arg_0]
0x180001fea  add     rsp, 20h
0x180001fee  pop     rdi
0x180001fef  retn
```
