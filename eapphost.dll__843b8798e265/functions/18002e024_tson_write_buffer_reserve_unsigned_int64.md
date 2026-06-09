# tson::write_buffer::reserve(unsigned __int64)

- ea: `0x18002e024`
- end: `0x18002e0f1`
- name: `?reserve@write_buffer@tson@@AEAA_N_K@Z`
- size: `205`
- prototype: `bool __fastcall(tson::write_buffer *__hidden this, unsigned __int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180020f04`
- `0x180021040`
- `0x180022548`
- `0x18002dc30`

## callees

- `0x180004cc8`
- `0x1800050ec`
- `0x18000a658`
- `0x18002e024`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002e055`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002e055`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e09d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e09d`

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
0x18002e024  mov     [rsp+arg_8], rbx
0x18002e029  mov     [rsp+arg_10], rbp
0x18002e02e  push    rsi
0x18002e02f  push    rdi
0x18002e030  push    r14
0x18002e032  sub     rsp, 20h
0x18002e036  mov     rax, [rcx+820h]
0x18002e03d  mov     rbx, rcx
0x18002e040  sub     rax, [rcx+810h]
0x18002e047  cmp     rax, rdx
0x18002e04a  cmova   rdx, rax
0x18002e04e  lea     r14, [rdx+rdx]
0x18002e052  mov     rcx, r14; cb
0x18002e055  call    cs:__imp_CoTaskMemAlloc
0x18002e05c  nop     dword ptr [rax+rax+00h]
0x18002e061  mov     rdi, rax
0x18002e064  test    rax, rax
0x18002e067  jz      short loc_18002E0D7
0x18002e069  mov     r8, [rbx+810h]; Source
0x18002e070  mov     rdx, r14; DestinationSize
0x18002e073  mov     rsi, [rbx+818h]
0x18002e07a  mov     rcx, rax; Destination
0x18002e07d  sub     rsi, r8
0x18002e080  mov     r9, rsi; SourceSize
0x18002e083  call    memcpy_s_0
0x18002e088  mov     rbp, [rbx]
0x18002e08b  test    rbp, rbp
0x18002e08e  jz      short loc_18002E0B3
0x18002e090  lea     rcx, [rsp+38h+arg_0]; this
0x18002e095  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18002e09a  mov     rcx, rbp; pv
0x18002e09d  call    cs:__imp_CoTaskMemFree
0x18002e0a4  nop     dword ptr [rax+rax+00h]
0x18002e0a9  lea     rcx, [rsp+38h+arg_0]; this
0x18002e0ae  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18002e0b3  mov     [rbx], rdi
0x18002e0b6  lea     rax, [rsi+rdi]
0x18002e0ba  mov     [rbx+818h], rax
0x18002e0c1  lea     rax, [r14+rdi]
0x18002e0c5  mov     [rbx+820h], rax
0x18002e0cc  mov     al, 1
0x18002e0ce  mov     [rbx+810h], rdi
0x18002e0d5  jmp     short loc_18002E0DD
0x18002e0d7  mov     byte ptr [rbx+8], 1
0x18002e0db  xor     al, al
0x18002e0dd  mov     rbx, [rsp+38h+arg_8]
0x18002e0e2  mov     rbp, [rsp+38h+arg_10]
0x18002e0e7  add     rsp, 20h
0x18002e0eb  pop     r14
0x18002e0ed  pop     rdi
0x18002e0ee  pop     rsi
0x18002e0ef  retn
```
