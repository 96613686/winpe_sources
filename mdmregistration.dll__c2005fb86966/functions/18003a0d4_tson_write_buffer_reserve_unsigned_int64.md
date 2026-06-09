# tson::write_buffer::reserve(unsigned __int64)

- ea: `0x18003a0d4`
- end: `0x18003a19e`
- name: `?reserve@write_buffer@tson@@AEAA_N_K@Z`
- size: `202`
- prototype: `bool __fastcall(tson::write_buffer *__hidden this, unsigned __int64)`
- caller_count: `15`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800308c4`
- `0x180030974`
- `0x180030a38`
- `0x180030ad0`
- `0x180030b68`
- `0x180030c00`
- `0x180030c90`
- `0x18003111c`
- `0x180039e10`
- `0x18003a060`
- `0x18003a1a4`
- `0x18003a7c4`
- `0x18003ab98`
- `0x18003b224`
- `0x18003b438`

## callees

- `0x180013bfc`
- `0x18003a0d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a13b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a13b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003a15a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003a15a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003a100`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003a100`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a14c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a14c`

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
0x18003a0d4  push    rbx
0x18003a0d6  push    rbp
0x18003a0d7  push    rsi
0x18003a0d8  push    rdi
0x18003a0d9  push    r14
0x18003a0db  push    r15
0x18003a0dd  sub     rsp, 28h
0x18003a0e1  mov     rax, [rcx+820h]
0x18003a0e8  mov     rdi, rcx
0x18003a0eb  sub     rax, [rcx+810h]
0x18003a0f2  cmp     rax, rdx
0x18003a0f5  cmova   rdx, rax
0x18003a0f9  lea     r15, [rdx+rdx]
0x18003a0fd  mov     rcx, r15; cb
0x18003a100  call    cs:__imp_CoTaskMemAlloc
0x18003a107  nop     dword ptr [rax+rax+00h]
0x18003a10c  mov     rsi, rax
0x18003a10f  test    rax, rax
0x18003a112  jz      short loc_18003A18A
0x18003a114  mov     r8, [rdi+810h]; Source
0x18003a11b  mov     rdx, r15; DestinationSize
0x18003a11e  mov     r14, [rdi+818h]
0x18003a125  mov     rcx, rax; Destination
0x18003a128  sub     r14, r8
0x18003a12b  mov     r9, r14; SourceSize
0x18003a12e  call    memcpy_s
0x18003a133  mov     rbp, [rdi]
0x18003a136  test    rbp, rbp
0x18003a139  jz      short loc_18003A166
0x18003a13b  call    cs:__imp_GetLastError
0x18003a142  nop     dword ptr [rax+rax+00h]
0x18003a147  mov     rcx, rbp; pv
0x18003a14a  mov     ebx, eax
0x18003a14c  call    cs:__imp_CoTaskMemFree
0x18003a153  nop     dword ptr [rax+rax+00h]
0x18003a158  mov     ecx, ebx; dwErrCode
0x18003a15a  call    cs:__imp_SetLastError
0x18003a161  nop     dword ptr [rax+rax+00h]
0x18003a166  mov     [rdi], rsi
0x18003a169  lea     rax, [r14+rsi]
0x18003a16d  mov     [rdi+818h], rax
0x18003a174  lea     rax, [r15+rsi]
0x18003a178  mov     [rdi+820h], rax
0x18003a17f  mov     al, 1
0x18003a181  mov     [rdi+810h], rsi
0x18003a188  jmp     short loc_18003A190
0x18003a18a  mov     byte ptr [rdi+8], 1
0x18003a18e  xor     al, al
0x18003a190  add     rsp, 28h
0x18003a194  pop     r15
0x18003a196  pop     r14
0x18003a198  pop     rdi
0x18003a199  pop     rsi
0x18003a19a  pop     rbp
0x18003a19b  pop     rbx
0x18003a19c  retn
```
