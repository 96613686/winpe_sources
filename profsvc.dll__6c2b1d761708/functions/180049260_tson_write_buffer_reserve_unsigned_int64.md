# tson::write_buffer::reserve(unsigned __int64)

- ea: `0x180049260`
- end: `0x18004932d`
- name: `?reserve@write_buffer@tson@@AEAA_N_K@Z`
- size: `205`
- prototype: `bool __fastcall(tson::write_buffer *__hidden this, unsigned __int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180044318`
- `0x180044b2c`
- `0x180049084`
- `0x180049410`

## callees

- `0x180024db0`
- `0x180032894`
- `0x180032900`
- `0x180049260`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180049291`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180049291`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800492d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800492d9`

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
0x180049260  mov     [rsp+arg_8], rbx
0x180049265  mov     [rsp+arg_10], rbp
0x18004926a  push    rsi
0x18004926b  push    rdi
0x18004926c  push    r14
0x18004926e  sub     rsp, 20h
0x180049272  mov     rax, [rcx+820h]
0x180049279  mov     rbx, rcx
0x18004927c  sub     rax, [rcx+810h]
0x180049283  cmp     rax, rdx
0x180049286  cmova   rdx, rax
0x18004928a  lea     r14, [rdx+rdx]
0x18004928e  mov     rcx, r14; cb
0x180049291  call    cs:__imp_CoTaskMemAlloc
0x180049298  nop     dword ptr [rax+rax+00h]
0x18004929d  mov     rdi, rax
0x1800492a0  test    rax, rax
0x1800492a3  jz      short loc_180049313
0x1800492a5  mov     r8, [rbx+810h]; Source
0x1800492ac  mov     rdx, r14; DestinationSize
0x1800492af  mov     rsi, [rbx+818h]
0x1800492b6  mov     rcx, rax; Destination
0x1800492b9  sub     rsi, r8
0x1800492bc  mov     r9, rsi; SourceSize
0x1800492bf  call    memcpy_s_0
0x1800492c4  mov     rbp, [rbx]
0x1800492c7  test    rbp, rbp
0x1800492ca  jz      short loc_1800492EF
0x1800492cc  lea     rcx, [rsp+38h+arg_0]; this
0x1800492d1  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800492d6  mov     rcx, rbp; pv
0x1800492d9  call    cs:__imp_CoTaskMemFree
0x1800492e0  nop     dword ptr [rax+rax+00h]
0x1800492e5  lea     rcx, [rsp+38h+arg_0]; this
0x1800492ea  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800492ef  mov     [rbx], rdi
0x1800492f2  lea     rax, [rsi+rdi]
0x1800492f6  mov     [rbx+818h], rax
0x1800492fd  lea     rax, [r14+rdi]
0x180049301  mov     [rbx+820h], rax
0x180049308  mov     al, 1
0x18004930a  mov     [rbx+810h], rdi
0x180049311  jmp     short loc_180049319
0x180049313  mov     byte ptr [rbx+8], 1
0x180049317  xor     al, al
0x180049319  mov     rbx, [rsp+38h+arg_8]
0x18004931e  mov     rbp, [rsp+38h+arg_10]
0x180049323  add     rsp, 20h
0x180049327  pop     r14
0x180049329  pop     rdi
0x18004932a  pop     rsi
0x18004932b  retn
```
