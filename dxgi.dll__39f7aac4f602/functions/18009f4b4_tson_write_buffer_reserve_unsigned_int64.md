# tson::write_buffer::reserve(unsigned __int64)

- ea: `0x18009f4b4`
- end: `0x18009f574`
- name: `?reserve@write_buffer@tson@@AEAA_N_K@Z`
- size: `192`
- prototype: `bool __fastcall(tson::write_buffer *__hidden this, unsigned __int64)`
- caller_count: `3`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18009b5e4`
- `0x18009f440`
- `0x18009f5a4`

## callees

- `0x180058c1c`
- `0x18005b0c0`
- `0x18009f4b4`
- `0x1800a064c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009f4e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009f4e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009f527`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009f527`

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
    memcpy_s_0(v4, v3, v6, v7);
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
0x18009f4b4  mov     [rsp+arg_8], rbx
0x18009f4b9  mov     [rsp+arg_10], rbp
0x18009f4be  push    rsi
0x18009f4bf  push    rdi
0x18009f4c0  push    r14
0x18009f4c2  sub     rsp, 20h
0x18009f4c6  mov     rax, [rcx+820h]
0x18009f4cd  mov     rbx, rcx
0x18009f4d0  sub     rax, [rcx+810h]
0x18009f4d7  cmp     rax, rdx
0x18009f4da  cmova   rdx, rax
0x18009f4de  lea     r14, [rdx+rdx]
0x18009f4e2  mov     rcx, r14; cb
0x18009f4e5  call    cs:__imp_CoTaskMemAlloc
0x18009f4eb  mov     rdi, rax
0x18009f4ee  test    rax, rax
0x18009f4f1  jz      short loc_18009F55B
0x18009f4f3  mov     r8, [rbx+810h]; Source
0x18009f4fa  mov     rdx, r14; DestinationSize
0x18009f4fd  mov     rsi, [rbx+818h]
0x18009f504  mov     rcx, rax; Destination
0x18009f507  sub     rsi, r8
0x18009f50a  mov     r9, rsi; SourceSize
0x18009f50d  call    memcpy_s_0
0x18009f512  mov     rbp, [rbx]
0x18009f515  test    rbp, rbp
0x18009f518  jz      short loc_18009F537
0x18009f51a  lea     rcx, [rsp+38h+arg_0]; this
0x18009f51f  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18009f524  mov     rcx, rbp; pv
0x18009f527  call    cs:__imp_CoTaskMemFree
0x18009f52d  lea     rcx, [rsp+38h+arg_0]; this
0x18009f532  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18009f537  mov     [rbx], rdi
0x18009f53a  lea     rax, [rsi+rdi]
0x18009f53e  mov     [rbx+818h], rax
0x18009f545  lea     rax, [r14+rdi]
0x18009f549  mov     [rbx+820h], rax
0x18009f550  mov     al, 1
0x18009f552  mov     [rbx+810h], rdi
0x18009f559  jmp     short loc_18009F561
0x18009f55b  mov     byte ptr [rbx+8], 1
0x18009f55f  xor     al, al
0x18009f561  mov     rbx, [rsp+38h+arg_8]
0x18009f566  mov     rbp, [rsp+38h+arg_10]
0x18009f56b  add     rsp, 20h
0x18009f56f  pop     r14
0x18009f571  pop     rdi
0x18009f572  pop     rsi
0x18009f573  retn
```
