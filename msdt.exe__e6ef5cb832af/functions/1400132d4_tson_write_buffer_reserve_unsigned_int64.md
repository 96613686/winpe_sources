# tson::write_buffer::reserve(unsigned __int64)

- ea: `0x1400132d4`
- end: `0x1400133a8`
- name: `?reserve@write_buffer@tson@@AEAA_N_K@Z`
- size: `212`
- prototype: `bool __fastcall(tson::write_buffer *__hidden this, unsigned __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x14000afe0`
- `0x14000b11c`
- `0x14000c6e4`
- `0x140012ea0`

## callees

- `0x140004da0`
- `0x140005014`
- `0x1400132d4`

## import_xrefs

- `msvcrt!memcpy_s` at `0x140013333`
- `msvcrt!memcpy_s` at `0x140013333`
- `ole32!CoTaskMemFree` at `0x140013354`
- `ole32!CoTaskMemFree` at `0x140013354`
- `ole32!CoTaskMemAlloc` at `0x140013305`
- `ole32!CoTaskMemAlloc` at `0x140013305`

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
0x1400132d4  mov     [rsp+arg_8], rbx
0x1400132d9  mov     [rsp+arg_10], rbp
0x1400132de  push    rsi
0x1400132df  push    rdi
0x1400132e0  push    r14
0x1400132e2  sub     rsp, 20h
0x1400132e6  mov     rax, [rcx+820h]
0x1400132ed  mov     rbx, rcx
0x1400132f0  sub     rax, [rcx+810h]
0x1400132f7  cmp     rax, rdx
0x1400132fa  cmova   rdx, rax
0x1400132fe  lea     r14, [rdx+rdx]
0x140013302  mov     rcx, r14; cb
0x140013305  call    cs:__imp_CoTaskMemAlloc
0x14001330c  nop     dword ptr [rax+rax+00h]
0x140013311  mov     rdi, rax
0x140013314  test    rax, rax
0x140013317  jz      short loc_14001338E
0x140013319  mov     r8, [rbx+810h]; Source
0x140013320  mov     rdx, r14; DestinationSize
0x140013323  mov     rsi, [rbx+818h]
0x14001332a  mov     rcx, rax; Destination
0x14001332d  sub     rsi, r8
0x140013330  mov     r9, rsi; SourceSize
0x140013333  call    cs:__imp_memcpy_s
0x14001333a  nop     dword ptr [rax+rax+00h]
0x14001333f  mov     rbp, [rbx]
0x140013342  test    rbp, rbp
0x140013345  jz      short loc_14001336A
0x140013347  lea     rcx, [rsp+38h+arg_0]; this
0x14001334c  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x140013351  mov     rcx, rbp; pv
0x140013354  call    cs:__imp_CoTaskMemFree
0x14001335b  nop     dword ptr [rax+rax+00h]
0x140013360  lea     rcx, [rsp+38h+arg_0]; this
0x140013365  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x14001336a  mov     [rbx], rdi
0x14001336d  lea     rax, [rsi+rdi]
0x140013371  mov     [rbx+818h], rax
0x140013378  lea     rax, [r14+rdi]
0x14001337c  mov     [rbx+820h], rax
0x140013383  mov     al, 1
0x140013385  mov     [rbx+810h], rdi
0x14001338c  jmp     short loc_140013394
0x14001338e  mov     byte ptr [rbx+8], 1
0x140013392  xor     al, al
0x140013394  mov     rbx, [rsp+38h+arg_8]
0x140013399  mov     rbp, [rsp+38h+arg_10]
0x14001339e  add     rsp, 20h
0x1400133a2  pop     r14
0x1400133a4  pop     rdi
0x1400133a5  pop     rsi
0x1400133a6  retn
```
