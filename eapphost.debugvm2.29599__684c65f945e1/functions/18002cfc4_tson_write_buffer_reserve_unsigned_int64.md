# tson::write_buffer::reserve(unsigned __int64)

- ea: `0x18002cfc4`
- end: `0x18002d084`
- name: `?reserve@write_buffer@tson@@AEAA_N_K@Z`
- size: `192`
- prototype: `bool __fastcall(tson::write_buffer *__hidden this, unsigned __int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180020320`
- `0x18002045c`
- `0x18002193c`
- `0x18002cc28`

## callees

- `0x180004b50`
- `0x180004fa4`
- `0x18000a1b4`
- `0x18002cfc4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002cff5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002cff5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002d037`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002d037`

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
0x18002cfc4  mov     [rsp+arg_8], rbx
0x18002cfc9  mov     [rsp+arg_10], rbp
0x18002cfce  push    rsi
0x18002cfcf  push    rdi
0x18002cfd0  push    r14
0x18002cfd2  sub     rsp, 20h
0x18002cfd6  mov     rax, [rcx+820h]
0x18002cfdd  mov     rbx, rcx
0x18002cfe0  sub     rax, [rcx+810h]
0x18002cfe7  cmp     rax, rdx
0x18002cfea  cmova   rdx, rax
0x18002cfee  lea     r14, [rdx+rdx]
0x18002cff2  mov     rcx, r14; cb
0x18002cff5  call    cs:__imp_CoTaskMemAlloc
0x18002cffb  mov     rdi, rax
0x18002cffe  test    rax, rax
0x18002d001  jz      short loc_18002D06B
0x18002d003  mov     r8, [rbx+810h]; Source
0x18002d00a  mov     rdx, r14; DestinationSize
0x18002d00d  mov     rsi, [rbx+818h]
0x18002d014  mov     rcx, rax; Destination
0x18002d017  sub     rsi, r8
0x18002d01a  mov     r9, rsi; SourceSize
0x18002d01d  call    memcpy_s_0
0x18002d022  mov     rbp, [rbx]
0x18002d025  test    rbp, rbp
0x18002d028  jz      short loc_18002D047
0x18002d02a  lea     rcx, [rsp+38h+arg_0]; this
0x18002d02f  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18002d034  mov     rcx, rbp; pv
0x18002d037  call    cs:__imp_CoTaskMemFree
0x18002d03d  lea     rcx, [rsp+38h+arg_0]; this
0x18002d042  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18002d047  mov     [rbx], rdi
0x18002d04a  lea     rax, [rsi+rdi]
0x18002d04e  mov     [rbx+818h], rax
0x18002d055  lea     rax, [r14+rdi]
0x18002d059  mov     [rbx+820h], rax
0x18002d060  mov     al, 1
0x18002d062  mov     [rbx+810h], rdi
0x18002d069  jmp     short loc_18002D071
0x18002d06b  mov     byte ptr [rbx+8], 1
0x18002d06f  xor     al, al
0x18002d071  mov     rbx, [rsp+38h+arg_8]
0x18002d076  mov     rbp, [rsp+38h+arg_10]
0x18002d07b  add     rsp, 20h
0x18002d07f  pop     r14
0x18002d081  pop     rdi
0x18002d082  pop     rsi
0x18002d083  retn
```
