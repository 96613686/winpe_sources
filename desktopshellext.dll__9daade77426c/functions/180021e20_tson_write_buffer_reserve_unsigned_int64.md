# tson::write_buffer::reserve(unsigned __int64)

- ea: `0x180021e20`
- end: `0x180021ee0`
- name: `?reserve@write_buffer@tson@@AEAA_N_K@Z`
- size: `192`
- prototype: `bool __fastcall(tson::write_buffer *__hidden this, unsigned __int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002f198`
- `0x18002fe04`
- `0x180032c38`
- `0x180032f80`

## callees

- `0x1800055d8`
- `0x180011a2c`
- `0x180015eb8`
- `0x180021e20`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021e51`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021e51`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021e93`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021e93`

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
    memcpy_s_1(v4, v3, v6, v7);
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
0x180021e20  mov     [rsp+arg_8], rbx
0x180021e25  mov     [rsp+arg_10], rbp
0x180021e2a  push    rsi
0x180021e2b  push    rdi
0x180021e2c  push    r14
0x180021e2e  sub     rsp, 20h
0x180021e32  mov     rax, [rcx+820h]
0x180021e39  mov     rbx, rcx
0x180021e3c  sub     rax, [rcx+810h]
0x180021e43  cmp     rax, rdx
0x180021e46  cmova   rdx, rax
0x180021e4a  lea     r14, [rdx+rdx]
0x180021e4e  mov     rcx, r14; cb
0x180021e51  call    cs:__imp_CoTaskMemAlloc
0x180021e57  mov     rdi, rax
0x180021e5a  test    rax, rax
0x180021e5d  jz      short loc_180021EC7
0x180021e5f  mov     r8, [rbx+810h]; Source
0x180021e66  mov     rdx, r14; DestinationSize
0x180021e69  mov     rsi, [rbx+818h]
0x180021e70  mov     rcx, rax; Destination
0x180021e73  sub     rsi, r8
0x180021e76  mov     r9, rsi; SourceSize
0x180021e79  call    memcpy_s_1
0x180021e7e  mov     rbp, [rbx]
0x180021e81  test    rbp, rbp
0x180021e84  jz      short loc_180021EA3
0x180021e86  lea     rcx, [rsp+38h+arg_0]; this
0x180021e8b  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180021e90  mov     rcx, rbp; pv
0x180021e93  call    cs:__imp_CoTaskMemFree
0x180021e99  lea     rcx, [rsp+38h+arg_0]; this
0x180021e9e  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180021ea3  mov     [rbx], rdi
0x180021ea6  lea     rax, [rsi+rdi]
0x180021eaa  mov     [rbx+818h], rax
0x180021eb1  lea     rax, [r14+rdi]
0x180021eb5  mov     [rbx+820h], rax
0x180021ebc  mov     al, 1
0x180021ebe  mov     [rbx+810h], rdi
0x180021ec5  jmp     short loc_180021ECD
0x180021ec7  mov     byte ptr [rbx+8], 1
0x180021ecb  xor     al, al
0x180021ecd  mov     rbx, [rsp+38h+arg_8]
0x180021ed2  mov     rbp, [rsp+38h+arg_10]
0x180021ed7  add     rsp, 20h
0x180021edb  pop     r14
0x180021edd  pop     rdi
0x180021ede  pop     rsi
0x180021edf  retn
```
