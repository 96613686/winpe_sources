# tson::write_buffer::reserve(unsigned __int64)

- ea: `0x180047110`
- end: `0x1800471d0`
- name: `?reserve@write_buffer@tson@@AEAA_N_K@Z`
- size: `192`
- prototype: `bool __fastcall(tson::write_buffer *__hidden this, unsigned __int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180042804`
- `0x180043018`
- `0x180046f4c`
- `0x1800472ac`

## callees

- `0x180021d90`
- `0x180030e58`
- `0x180030ebc`
- `0x180047110`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180047141`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180047141`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047183`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047183`

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
0x180047110  mov     [rsp+arg_8], rbx
0x180047115  mov     [rsp+arg_10], rbp
0x18004711a  push    rsi
0x18004711b  push    rdi
0x18004711c  push    r14
0x18004711e  sub     rsp, 20h
0x180047122  mov     rax, [rcx+820h]
0x180047129  mov     rbx, rcx
0x18004712c  sub     rax, [rcx+810h]
0x180047133  cmp     rax, rdx
0x180047136  cmova   rdx, rax
0x18004713a  lea     r14, [rdx+rdx]
0x18004713e  mov     rcx, r14; cb
0x180047141  call    cs:__imp_CoTaskMemAlloc
0x180047147  mov     rdi, rax
0x18004714a  test    rax, rax
0x18004714d  jz      short loc_1800471B7
0x18004714f  mov     r8, [rbx+810h]; Source
0x180047156  mov     rdx, r14; DestinationSize
0x180047159  mov     rsi, [rbx+818h]
0x180047160  mov     rcx, rax; Destination
0x180047163  sub     rsi, r8
0x180047166  mov     r9, rsi; SourceSize
0x180047169  call    memcpy_s_0
0x18004716e  mov     rbp, [rbx]
0x180047171  test    rbp, rbp
0x180047174  jz      short loc_180047193
0x180047176  lea     rcx, [rsp+38h+arg_0]; this
0x18004717b  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180047180  mov     rcx, rbp; pv
0x180047183  call    cs:__imp_CoTaskMemFree
0x180047189  lea     rcx, [rsp+38h+arg_0]; this
0x18004718e  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180047193  mov     [rbx], rdi
0x180047196  lea     rax, [rsi+rdi]
0x18004719a  mov     [rbx+818h], rax
0x1800471a1  lea     rax, [r14+rdi]
0x1800471a5  mov     [rbx+820h], rax
0x1800471ac  mov     al, 1
0x1800471ae  mov     [rbx+810h], rdi
0x1800471b5  jmp     short loc_1800471BD
0x1800471b7  mov     byte ptr [rbx+8], 1
0x1800471bb  xor     al, al
0x1800471bd  mov     rbx, [rsp+38h+arg_8]
0x1800471c2  mov     rbp, [rsp+38h+arg_10]
0x1800471c7  add     rsp, 20h
0x1800471cb  pop     r14
0x1800471cd  pop     rdi
0x1800471ce  pop     rsi
0x1800471cf  retn
```
