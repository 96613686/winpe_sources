# tson::write_buffer::reserve(unsigned __int64)

- ea: `0x140025008`
- end: `0x1400250d2`
- name: `?reserve@write_buffer@tson@@AEAA_N_K@Z`
- size: `202`
- prototype: `bool __fastcall(tson::write_buffer *__hidden this, unsigned __int64)`
- caller_count: `16`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x14001e660`
- `0x14001e710`
- `0x14001e7d4`
- `0x14001ebfc`
- `0x14001ec94`
- `0x14001ed2c`
- `0x14001edc4`
- `0x14001ee54`
- `0x14001f2e8`
- `0x140024d44`
- `0x140024f94`
- `0x1400250d8`
- `0x1400256a8`
- `0x140025a50`
- `0x140025e88`
- `0x14002609c`

## callees

- `0x14000ded8`
- `0x140025008`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002506f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002506f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002508e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002508e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140025080`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140025080`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140025034`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140025034`

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
0x140025008  push    rbx
0x14002500a  push    rbp
0x14002500b  push    rsi
0x14002500c  push    rdi
0x14002500d  push    r14
0x14002500f  push    r15
0x140025011  sub     rsp, 28h
0x140025015  mov     rax, [rcx+820h]
0x14002501c  mov     rdi, rcx
0x14002501f  sub     rax, [rcx+810h]
0x140025026  cmp     rax, rdx
0x140025029  cmova   rdx, rax
0x14002502d  lea     r15, [rdx+rdx]
0x140025031  mov     rcx, r15; cb
0x140025034  call    cs:__imp_CoTaskMemAlloc
0x14002503b  nop     dword ptr [rax+rax+00h]
0x140025040  mov     rsi, rax
0x140025043  test    rax, rax
0x140025046  jz      short loc_1400250BE
0x140025048  mov     r8, [rdi+810h]; Source
0x14002504f  mov     rdx, r15; DestinationSize
0x140025052  mov     r14, [rdi+818h]
0x140025059  mov     rcx, rax; Destination
0x14002505c  sub     r14, r8
0x14002505f  mov     r9, r14; SourceSize
0x140025062  call    memcpy_s
0x140025067  mov     rbp, [rdi]
0x14002506a  test    rbp, rbp
0x14002506d  jz      short loc_14002509A
0x14002506f  call    cs:__imp_GetLastError
0x140025076  nop     dword ptr [rax+rax+00h]
0x14002507b  mov     rcx, rbp; pv
0x14002507e  mov     ebx, eax
0x140025080  call    cs:__imp_CoTaskMemFree
0x140025087  nop     dword ptr [rax+rax+00h]
0x14002508c  mov     ecx, ebx; dwErrCode
0x14002508e  call    cs:__imp_SetLastError
0x140025095  nop     dword ptr [rax+rax+00h]
0x14002509a  mov     [rdi], rsi
0x14002509d  lea     rax, [r14+rsi]
0x1400250a1  mov     [rdi+818h], rax
0x1400250a8  lea     rax, [r15+rsi]
0x1400250ac  mov     [rdi+820h], rax
0x1400250b3  mov     al, 1
0x1400250b5  mov     [rdi+810h], rsi
0x1400250bc  jmp     short loc_1400250C4
0x1400250be  mov     byte ptr [rdi+8], 1
0x1400250c2  xor     al, al
0x1400250c4  add     rsp, 28h
0x1400250c8  pop     r15
0x1400250ca  pop     r14
0x1400250cc  pop     rdi
0x1400250cd  pop     rsi
0x1400250ce  pop     rbp
0x1400250cf  pop     rbx
0x1400250d0  retn
```
