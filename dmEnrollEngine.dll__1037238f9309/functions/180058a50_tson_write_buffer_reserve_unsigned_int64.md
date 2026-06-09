# tson::write_buffer::reserve(unsigned __int64)

- ea: `0x180058a50`
- end: `0x180058b17`
- name: `?reserve@write_buffer@tson@@AEAA_N_K@Z`
- size: `199`
- prototype: `bool __fastcall(tson::write_buffer *__hidden this, unsigned __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180054604`
- `0x1800546d0`
- `0x180054b74`
- `0x1800589c0`

## callees

- `0x18000d810`
- `0x18001f5c4`
- `0x180058a50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180058ad4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180058ad4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180058ac3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180058ac3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180058a81`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180058a81`

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
  DWORD dwErrCode; // [rsp+44h] [rbp+Ch]

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
      if ( !v10 )
        SetLastError(dwErrCode);
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
0x180058a50  mov     [rsp+arg_8], rbx
0x180058a55  mov     [rsp+arg_10], rbp
0x180058a5a  push    rsi
0x180058a5b  push    rdi
0x180058a5c  push    r14
0x180058a5e  sub     rsp, 20h
0x180058a62  mov     rax, [rcx+820h]
0x180058a69  mov     rbx, rcx
0x180058a6c  sub     rax, [rcx+810h]
0x180058a73  cmp     rax, rdx
0x180058a76  cmova   rdx, rax
0x180058a7a  lea     r14, [rdx+rdx]
0x180058a7e  mov     rcx, r14; cb
0x180058a81  call    cs:__imp_CoTaskMemAlloc
0x180058a87  mov     rdi, rax
0x180058a8a  test    rax, rax
0x180058a8d  jz      short loc_180058AFE
0x180058a8f  mov     r8, [rbx+810h]; Source
0x180058a96  mov     rdx, r14; DestinationSize
0x180058a99  mov     rsi, [rbx+818h]
0x180058aa0  mov     rcx, rax; Destination
0x180058aa3  sub     rsi, r8
0x180058aa6  mov     r9, rsi; SourceSize
0x180058aa9  call    memcpy_s
0x180058aae  mov     rbp, [rbx]
0x180058ab1  test    rbp, rbp
0x180058ab4  jz      short loc_180058ADA
0x180058ab6  lea     rcx, [rsp+38h+arg_0]; this
0x180058abb  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180058ac0  mov     rcx, rbp; pv
0x180058ac3  call    cs:__imp_CoTaskMemFree
0x180058ac9  cmp     [rsp+38h+arg_0], 0
0x180058ace  jnz     short loc_180058ADA
0x180058ad0  mov     ecx, [rsp+38h+dwErrCode]; dwErrCode
0x180058ad4  call    cs:__imp_SetLastError
0x180058ada  mov     [rbx], rdi
0x180058add  lea     rax, [rsi+rdi]
0x180058ae1  mov     [rbx+818h], rax
0x180058ae8  lea     rax, [r14+rdi]
0x180058aec  mov     [rbx+820h], rax
0x180058af3  mov     al, 1
0x180058af5  mov     [rbx+810h], rdi
0x180058afc  jmp     short loc_180058B04
0x180058afe  mov     byte ptr [rbx+8], 1
0x180058b02  xor     al, al
0x180058b04  mov     rbx, [rsp+38h+arg_8]
0x180058b09  mov     rbp, [rsp+38h+arg_10]
0x180058b0e  add     rsp, 20h
0x180058b12  pop     r14
0x180058b14  pop     rdi
0x180058b15  pop     rsi
0x180058b16  retn
```
