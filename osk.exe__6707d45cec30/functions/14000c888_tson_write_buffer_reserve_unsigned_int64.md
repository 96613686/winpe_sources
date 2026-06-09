# tson::write_buffer::reserve(unsigned __int64)

- ea: `0x14000c888`
- end: `0x14000c949`
- name: `?reserve@write_buffer@tson@@AEAA_N_K@Z`
- size: `193`
- prototype: `bool __fastcall(tson::write_buffer *__hidden this, unsigned __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x14000346c`
- `0x140003534`
- `0x1400043a4`
- `0x14000c584`

## callees

- `0x140004b80`
- `0x140005460`
- `0x14000c888`

## import_xrefs

- `msvcrt!memcpy_s` at `0x14000c8e1`
- `msvcrt!memcpy_s` at `0x14000c8e1`
- `ole32!CoTaskMemAlloc` at `0x14000c8b9`
- `ole32!CoTaskMemAlloc` at `0x14000c8b9`
- `ole32!CoTaskMemFree` at `0x14000c8fc`
- `ole32!CoTaskMemFree` at `0x14000c8fc`

## pseudocode

```c
bool __fastcall tson::write_buffer::reserve(tson::write_buffer *this, unsigned __int64 a2)
{
  rsize_t v3; // r14
  char *v4; // rax
  char *v5; // rdi
  const void *v6; // r8
  rsize_t v7; // rsi
  void *v8; // rbp
  bool result; // al
  char v10; // [rsp+40h] [rbp+8h] BYREF

  if ( *((_QWORD *)this + 260) - *((_QWORD *)this + 258) > a2 )
    a2 = *((_QWORD *)this + 260) - *((_QWORD *)this + 258);
  v3 = 2 * a2;
  v4 = (char *)CoTaskMemAlloc(2 * a2);
  v5 = v4;
  if ( v4 )
  {
    v6 = (const void *)*((_QWORD *)this + 258);
    v7 = *((_QWORD *)this + 259) - (_QWORD)v6;
    memcpy_s(v4, v3, v6, v7);
    v8 = *(void **)this;
    if ( *(_QWORD *)this )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v10);
      CoTaskMemFree(v8);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v10);
    }
    *(_QWORD *)this = v5;
    *((_QWORD *)this + 259) = &v5[v7];
    *((_QWORD *)this + 260) = &v5[v3];
    result = 1;
    *((_QWORD *)this + 258) = v5;
  }
  else
  {
    *((_BYTE *)this + 8) = 1;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x14000c888  mov     [rsp+arg_8], rbx
0x14000c88d  mov     [rsp+arg_10], rbp
0x14000c892  push    rsi
0x14000c893  push    rdi
0x14000c894  push    r14
0x14000c896  sub     rsp, 20h
0x14000c89a  mov     rax, [rcx+820h]
0x14000c8a1  mov     rbx, rcx
0x14000c8a4  sub     rax, [rcx+810h]
0x14000c8ab  cmp     rax, rdx
0x14000c8ae  cmova   rdx, rax
0x14000c8b2  lea     r14, [rdx+rdx]
0x14000c8b6  mov     rcx, r14; cb
0x14000c8b9  call    cs:__imp_CoTaskMemAlloc
0x14000c8bf  mov     rdi, rax
0x14000c8c2  test    rax, rax
0x14000c8c5  jz      short loc_14000C930
0x14000c8c7  mov     r8, [rbx+810h]; Source
0x14000c8ce  mov     rdx, r14; DestinationSize
0x14000c8d1  mov     rsi, [rbx+818h]
0x14000c8d8  mov     rcx, rax; Destination
0x14000c8db  sub     rsi, r8
0x14000c8de  mov     r9, rsi; SourceSize
0x14000c8e1  call    cs:__imp_memcpy_s
0x14000c8e7  mov     rbp, [rbx]
0x14000c8ea  test    rbp, rbp
0x14000c8ed  jz      short loc_14000C90C
0x14000c8ef  lea     rcx, [rsp+38h+arg_0]; this
0x14000c8f4  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14000c8f9  mov     rcx, rbp; pv
0x14000c8fc  call    cs:__imp_CoTaskMemFree
0x14000c902  lea     rcx, [rsp+38h+arg_0]; this
0x14000c907  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x14000c90c  mov     [rbx], rdi
0x14000c90f  lea     rax, [rsi+rdi]
0x14000c913  mov     [rbx+818h], rax
0x14000c91a  lea     rax, [r14+rdi]
0x14000c91e  mov     [rbx+820h], rax
0x14000c925  mov     al, 1
0x14000c927  mov     [rbx+810h], rdi
0x14000c92e  jmp     short loc_14000C936
0x14000c930  mov     byte ptr [rbx+8], 1
0x14000c934  xor     al, al
0x14000c936  mov     rbx, [rsp+38h+arg_8]
0x14000c93b  mov     rbp, [rsp+38h+arg_10]
0x14000c940  add     rsp, 20h
0x14000c944  pop     r14
0x14000c946  pop     rdi
0x14000c947  pop     rsi
0x14000c948  retn
```
