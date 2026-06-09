# tson::write_buffer::reserve(unsigned __int64)

- ea: `0x18006a50c`
- end: `0x18006a5ed`
- name: `?reserve@write_buffer@tson@@AEAA_N_K@Z`
- size: `225`
- prototype: `bool __fastcall(tson::write_buffer *__hidden this, unsigned __int64)`
- caller_count: `12`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18006174c`
- `0x180064728`
- `0x180064a6c`
- `0x1800654a4`
- `0x180069474`
- `0x18006a318`
- `0x18006a5f4`
- `0x18006a690`
- `0x18006a72c`
- `0x18006ad14`
- `0x18006b970`
- `0x18006bb90`

## callees

- `0x18000f51c`
- `0x18006a50c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a57e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a57e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006a59d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006a59d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006a58f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006a58f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006a543`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006a543`

## pseudocode

```c
bool __fastcall tson::write_buffer::reserve(tson::write_buffer *this, unsigned __int64 a2)
{
  rsize_t v3; // rbp
  char *v4; // rax
  char *v5; // rsi
  const void *v6; // r8
  rsize_t v7; // r14
  void *v8; // r15
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
0x18006a50c  mov     [rsp+arg_0], rbx
0x18006a511  mov     [rsp+arg_8], rbp
0x18006a516  mov     [rsp+arg_10], rsi
0x18006a51b  push    rdi
0x18006a51c  push    r14
0x18006a51e  push    r15
0x18006a520  sub     rsp, 20h
0x18006a524  mov     rax, [rcx+820h]
0x18006a52b  mov     rdi, rcx
0x18006a52e  sub     rax, [rcx+810h]
0x18006a535  cmp     rax, rdx
0x18006a538  cmova   rdx, rax
0x18006a53c  lea     rbp, [rdx+rdx]
0x18006a540  mov     rcx, rbp; cb
0x18006a543  call    cs:__imp_CoTaskMemAlloc
0x18006a54a  nop     dword ptr [rax+rax+00h]
0x18006a54f  mov     rsi, rax
0x18006a552  test    rax, rax
0x18006a555  jz      short loc_18006A5CD
0x18006a557  mov     r8, [rdi+810h]; Source
0x18006a55e  mov     rdx, rbp; DestinationSize
0x18006a561  mov     r14, [rdi+818h]
0x18006a568  mov     rcx, rax; Destination
0x18006a56b  sub     r14, r8
0x18006a56e  mov     r9, r14; SourceSize
0x18006a571  call    memcpy_s
0x18006a576  mov     r15, [rdi]
0x18006a579  test    r15, r15
0x18006a57c  jz      short loc_18006A5A9
0x18006a57e  call    cs:__imp_GetLastError
0x18006a585  nop     dword ptr [rax+rax+00h]
0x18006a58a  mov     rcx, r15; pv
0x18006a58d  mov     ebx, eax
0x18006a58f  call    cs:__imp_CoTaskMemFree
0x18006a596  nop     dword ptr [rax+rax+00h]
0x18006a59b  mov     ecx, ebx; dwErrCode
0x18006a59d  call    cs:__imp_SetLastError
0x18006a5a4  nop     dword ptr [rax+rax+00h]
0x18006a5a9  mov     [rdi], rsi
0x18006a5ac  lea     rax, [r14+rsi]
0x18006a5b0  mov     [rdi+818h], rax
0x18006a5b7  lea     rax, [rsi+rbp]
0x18006a5bb  mov     [rdi+820h], rax
0x18006a5c2  mov     al, 1
0x18006a5c4  mov     [rdi+810h], rsi
0x18006a5cb  jmp     short loc_18006A5D3
0x18006a5cd  mov     byte ptr [rdi+8], 1
0x18006a5d1  xor     al, al
0x18006a5d3  mov     rbx, [rsp+38h+arg_0]
0x18006a5d8  mov     rbp, [rsp+38h+arg_8]
0x18006a5dd  mov     rsi, [rsp+38h+arg_10]
0x18006a5e2  add     rsp, 20h
0x18006a5e6  pop     r15
0x18006a5e8  pop     r14
0x18006a5ea  pop     rdi
0x18006a5eb  retn
```
