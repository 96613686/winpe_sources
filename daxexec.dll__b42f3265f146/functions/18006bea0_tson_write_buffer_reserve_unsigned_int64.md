# tson::write_buffer::reserve(unsigned __int64)

- ea: `0x18006bea0`
- end: `0x18006bf6a`
- name: `?reserve@write_buffer@tson@@AEAA_N_K@Z`
- size: `202`
- prototype: `bool __fastcall(tson::write_buffer *__hidden this, unsigned __int64)`
- caller_count: `14`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18006321c`
- `0x1800632e0`
- `0x180065c54`
- `0x180065f7c`
- `0x180066178`
- `0x18006654c`
- `0x180066eb4`
- `0x18006af18`
- `0x18006bcc4`
- `0x18006bf70`
- `0x18006c60c`
- `0x18006cacc`
- `0x18006d2f0`
- `0x18006d504`

## callees

- `0x18001108c`
- `0x18006bea0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006bf26`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006bf26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006bf07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006bf07`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006bf18`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006bf18`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006becc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006becc`

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
0x18006bea0  push    rbx
0x18006bea2  push    rbp
0x18006bea3  push    rsi
0x18006bea4  push    rdi
0x18006bea5  push    r14
0x18006bea7  push    r15
0x18006bea9  sub     rsp, 28h
0x18006bead  mov     rax, [rcx+820h]
0x18006beb4  mov     rdi, rcx
0x18006beb7  sub     rax, [rcx+810h]
0x18006bebe  cmp     rax, rdx
0x18006bec1  cmova   rdx, rax
0x18006bec5  lea     r15, [rdx+rdx]
0x18006bec9  mov     rcx, r15; cb
0x18006becc  call    cs:__imp_CoTaskMemAlloc
0x18006bed3  nop     dword ptr [rax+rax+00h]
0x18006bed8  mov     rsi, rax
0x18006bedb  test    rax, rax
0x18006bede  jz      short loc_18006BF56
0x18006bee0  mov     r8, [rdi+810h]; Source
0x18006bee7  mov     rdx, r15; DestinationSize
0x18006beea  mov     r14, [rdi+818h]
0x18006bef1  mov     rcx, rax; Destination
0x18006bef4  sub     r14, r8
0x18006bef7  mov     r9, r14; SourceSize
0x18006befa  call    memcpy_s
0x18006beff  mov     rbp, [rdi]
0x18006bf02  test    rbp, rbp
0x18006bf05  jz      short loc_18006BF32
0x18006bf07  call    cs:__imp_GetLastError
0x18006bf0e  nop     dword ptr [rax+rax+00h]
0x18006bf13  mov     rcx, rbp; pv
0x18006bf16  mov     ebx, eax
0x18006bf18  call    cs:__imp_CoTaskMemFree
0x18006bf1f  nop     dword ptr [rax+rax+00h]
0x18006bf24  mov     ecx, ebx; dwErrCode
0x18006bf26  call    cs:__imp_SetLastError
0x18006bf2d  nop     dword ptr [rax+rax+00h]
0x18006bf32  mov     [rdi], rsi
0x18006bf35  lea     rax, [r14+rsi]
0x18006bf39  mov     [rdi+818h], rax
0x18006bf40  lea     rax, [r15+rsi]
0x18006bf44  mov     [rdi+820h], rax
0x18006bf4b  mov     al, 1
0x18006bf4d  mov     [rdi+810h], rsi
0x18006bf54  jmp     short loc_18006BF5C
0x18006bf56  mov     byte ptr [rdi+8], 1
0x18006bf5a  xor     al, al
0x18006bf5c  add     rsp, 28h
0x18006bf60  pop     r15
0x18006bf62  pop     r14
0x18006bf64  pop     rdi
0x18006bf65  pop     rsi
0x18006bf66  pop     rbp
0x18006bf67  pop     rbx
0x18006bf68  retn
```
