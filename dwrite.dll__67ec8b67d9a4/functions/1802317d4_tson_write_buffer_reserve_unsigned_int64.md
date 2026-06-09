# tson::write_buffer::reserve(unsigned __int64)

- ea: `0x1802317d4`
- end: `0x180231894`
- name: `?reserve@write_buffer@tson@@AEAA_N_K@Z`
- size: `192`
- prototype: `bool __fastcall(tson::write_buffer *__hidden this, unsigned __int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18022fcac`
- `0x18022fe28`
- `0x18023010c`
- `0x180231578`

## callees

- `0x1801fa81c`
- `0x180211b8c`
- `0x180211c10`
- `0x1802317d4`

## import_xrefs

- `combase!CoTaskMemFree` at `0x180231847`
- `combase!CoTaskMemFree` at `0x180231847`
- `combase!CoTaskMemAlloc` at `0x180231805`
- `combase!CoTaskMemAlloc` at `0x180231805`

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
0x1802317d4  mov     [rsp+arg_8], rbx
0x1802317d9  mov     [rsp+arg_10], rbp
0x1802317de  push    rsi
0x1802317df  push    rdi
0x1802317e0  push    r14
0x1802317e2  sub     rsp, 20h
0x1802317e6  mov     rax, [rcx+820h]
0x1802317ed  mov     rbx, rcx
0x1802317f0  sub     rax, [rcx+810h]
0x1802317f7  cmp     rax, rdx
0x1802317fa  cmova   rdx, rax
0x1802317fe  lea     r14, [rdx+rdx]
0x180231802  mov     rcx, r14; cb
0x180231805  call    cs:__imp_CoTaskMemAlloc
0x18023180b  mov     rdi, rax
0x18023180e  test    rax, rax
0x180231811  jz      short loc_18023187B
0x180231813  mov     r8, [rbx+810h]; Source
0x18023181a  mov     rdx, r14; DestinationSize
0x18023181d  mov     rsi, [rbx+818h]
0x180231824  mov     rcx, rax; Destination
0x180231827  sub     rsi, r8
0x18023182a  mov     r9, rsi; SourceSize
0x18023182d  call    memcpy_s
0x180231832  mov     rbp, [rbx]
0x180231835  test    rbp, rbp
0x180231838  jz      short loc_180231857
0x18023183a  lea     rcx, [rsp+38h+arg_0]; this
0x18023183f  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180231844  mov     rcx, rbp; pv
0x180231847  call    cs:__imp_CoTaskMemFree
0x18023184d  lea     rcx, [rsp+38h+arg_0]; this
0x180231852  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180231857  mov     [rbx], rdi
0x18023185a  lea     rax, [rsi+rdi]
0x18023185e  mov     [rbx+818h], rax
0x180231865  lea     rax, [r14+rdi]
0x180231869  mov     [rbx+820h], rax
0x180231870  mov     al, 1
0x180231872  mov     [rbx+810h], rdi
0x180231879  jmp     short loc_180231881
0x18023187b  mov     byte ptr [rbx+8], 1
0x18023187f  xor     al, al
0x180231881  mov     rbx, [rsp+38h+arg_8]
0x180231886  mov     rbp, [rsp+38h+arg_10]
0x18023188b  add     rsp, 20h
0x18023188f  pop     r14
0x180231891  pop     rdi
0x180231892  pop     rsi
0x180231893  retn
```
