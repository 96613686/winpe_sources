# tson::write_buffer::reserve(unsigned __int64)

- ea: `0x1800f8624`
- end: `0x1800f86e4`
- name: `?reserve@write_buffer@tson@@AEAA_N_K@Z`
- size: `192`
- prototype: `bool __fastcall(tson::write_buffer *__hidden this, unsigned __int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800f6ad0`
- `0x1800f6b9c`
- `0x1800f7398`
- `0x1800f85b0`

## callees

- `0x180097c60`
- `0x180097c80`
- `0x1800f8624`
- `0x1800f9698`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f8697`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f8697`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800f8655`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800f8655`

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
    memcpy_s_2(v4, v3, v6, v7);
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
0x1800f8624  mov     [rsp+arg_8], rbx
0x1800f8629  mov     [rsp+arg_10], rbp
0x1800f862e  push    rsi
0x1800f862f  push    rdi
0x1800f8630  push    r14
0x1800f8632  sub     rsp, 20h
0x1800f8636  mov     rax, [rcx+820h]
0x1800f863d  mov     rbx, rcx
0x1800f8640  sub     rax, [rcx+810h]
0x1800f8647  cmp     rax, rdx
0x1800f864a  cmova   rdx, rax
0x1800f864e  lea     r14, [rdx+rdx]
0x1800f8652  mov     rcx, r14; cb
0x1800f8655  call    cs:__imp_CoTaskMemAlloc
0x1800f865b  mov     rdi, rax
0x1800f865e  test    rax, rax
0x1800f8661  jz      short loc_1800F86CB
0x1800f8663  mov     r8, [rbx+810h]; Source
0x1800f866a  mov     rdx, r14; DestinationSize
0x1800f866d  mov     rsi, [rbx+818h]
0x1800f8674  mov     rcx, rax; Destination
0x1800f8677  sub     rsi, r8
0x1800f867a  mov     r9, rsi; SourceSize
0x1800f867d  call    memcpy_s_2
0x1800f8682  mov     rbp, [rbx]
0x1800f8685  test    rbp, rbp
0x1800f8688  jz      short loc_1800F86A7
0x1800f868a  lea     rcx, [rsp+38h+arg_0]; this
0x1800f868f  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800f8694  mov     rcx, rbp; pv
0x1800f8697  call    cs:__imp_CoTaskMemFree
0x1800f869d  lea     rcx, [rsp+38h+arg_0]; this
0x1800f86a2  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800f86a7  mov     [rbx], rdi
0x1800f86aa  lea     rax, [rsi+rdi]
0x1800f86ae  mov     [rbx+818h], rax
0x1800f86b5  lea     rax, [r14+rdi]
0x1800f86b9  mov     [rbx+820h], rax
0x1800f86c0  mov     al, 1
0x1800f86c2  mov     [rbx+810h], rdi
0x1800f86c9  jmp     short loc_1800F86D1
0x1800f86cb  mov     byte ptr [rbx+8], 1
0x1800f86cf  xor     al, al
0x1800f86d1  mov     rbx, [rsp+38h+arg_8]
0x1800f86d6  mov     rbp, [rsp+38h+arg_10]
0x1800f86db  add     rsp, 20h
0x1800f86df  pop     r14
0x1800f86e1  pop     rdi
0x1800f86e2  pop     rsi
0x1800f86e3  retn
```
