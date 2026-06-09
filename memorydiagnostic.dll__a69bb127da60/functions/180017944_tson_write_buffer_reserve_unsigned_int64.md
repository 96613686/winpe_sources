# tson::write_buffer::reserve(unsigned __int64)

- ea: `0x180017944`
- end: `0x1800179f5`
- name: `?reserve@write_buffer@tson@@AEAA_N_K@Z`
- size: `177`
- prototype: `bool __fastcall(tson::write_buffer *__hidden this, unsigned __int64)`
- caller_count: `13`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180003f2c`
- `0x1800041cc`
- `0x1800066a8`
- `0x180006740`
- `0x1800067d4`
- `0x180006954`
- `0x18000741c`
- `0x180016954`
- `0x180017780`
- `0x1800179fc`
- `0x18001807c`
- `0x180019308`
- `0x18001951c`

## callees

- `0x180017944`
- `0x1800196f0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800179a5`
- `KERNEL32!GetLastError` at `0x1800179a5`
- `KERNEL32!SetLastError` at `0x1800179b8`
- `KERNEL32!SetLastError` at `0x1800179b8`
- `ole32!CoTaskMemAlloc` at `0x180017970`
- `ole32!CoTaskMemAlloc` at `0x180017970`
- `ole32!CoTaskMemFree` at `0x1800179b0`
- `ole32!CoTaskMemFree` at `0x1800179b0`

## pseudocode

```c
bool __fastcall tson::write_buffer::reserve(tson::write_buffer *this, unsigned __int64 a2)
{
  rsize_t v3; // r15
  char *v4; // rax
  char *v5; // rsi
  const void *v6; // r8
  rsize_t v7; // r14
  void *v8; // rbp
  DWORD LastError; // ebx
  bool result; // al

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
      LastError = GetLastError();
      CoTaskMemFree(v8);
      SetLastError(LastError);
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
0x180017944  push    rbx
0x180017946  push    rbp
0x180017947  push    rsi
0x180017948  push    rdi
0x180017949  push    r14
0x18001794b  push    r15
0x18001794d  sub     rsp, 28h
0x180017951  mov     rax, [rcx+820h]
0x180017958  mov     rdi, rcx
0x18001795b  sub     rax, [rcx+810h]
0x180017962  cmp     rax, rdx
0x180017965  cmova   rdx, rax
0x180017969  lea     r15, [rdx+rdx]
0x18001796d  mov     rcx, r15; cb
0x180017970  call    cs:__imp_CoTaskMemAlloc
0x180017976  mov     rsi, rax
0x180017979  test    rax, rax
0x18001797c  jz      short loc_1800179E2
0x18001797e  mov     r8, [rdi+810h]; Source
0x180017985  mov     rdx, r15; DestinationSize
0x180017988  mov     r14, [rdi+818h]
0x18001798f  mov     rcx, rax; Destination
0x180017992  sub     r14, r8
0x180017995  mov     r9, r14; SourceSize
0x180017998  call    memcpy_s
0x18001799d  mov     rbp, [rdi]
0x1800179a0  test    rbp, rbp
0x1800179a3  jz      short loc_1800179BE
0x1800179a5  call    cs:__imp_GetLastError
0x1800179ab  mov     rcx, rbp; pv
0x1800179ae  mov     ebx, eax
0x1800179b0  call    cs:__imp_CoTaskMemFree
0x1800179b6  mov     ecx, ebx; dwErrCode
0x1800179b8  call    cs:__imp_SetLastError
0x1800179be  mov     [rdi], rsi
0x1800179c1  lea     rax, [r14+rsi]
0x1800179c5  mov     [rdi+818h], rax
0x1800179cc  lea     rax, [r15+rsi]
0x1800179d0  mov     [rdi+820h], rax
0x1800179d7  mov     al, 1
0x1800179d9  mov     [rdi+810h], rsi
0x1800179e0  jmp     short loc_1800179E8
0x1800179e2  mov     byte ptr [rdi+8], 1
0x1800179e6  xor     al, al
0x1800179e8  add     rsp, 28h
0x1800179ec  pop     r15
0x1800179ee  pop     r14
0x1800179f0  pop     rdi
0x1800179f1  pop     rsi
0x1800179f2  pop     rbp
0x1800179f3  pop     rbx
0x1800179f4  retn
```
