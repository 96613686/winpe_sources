# tson::write_buffer::reserve(unsigned __int64)

- ea: `0x18000d160`
- end: `0x18000d259`
- name: `?reserve@write_buffer@tson@@AEAA_N_K@Z`
- size: `249`
- prototype: `bool __fastcall(tson::write_buffer *__hidden this, unsigned __int64)`
- caller_count: `14`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000ae80`
- `0x18000af44`
- `0x18000afdc`
- `0x18000b070`
- `0x18000b104`
- `0x18000b194`
- `0x18000b5c0`
- `0x18000ce60`
- `0x18000d0b0`
- `0x18000d260`
- `0x18000d8fc`
- `0x18000dce4`
- `0x18000e224`
- `0x18000e438`

## callees

- `0x180002666`
- `0x1800026c8`
- `0x18000d160`
- `0x180011c6c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000d1dd`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000d1f0`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000d1dd`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000d1f0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d21c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d21c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d209`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d209`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d214`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d214`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d18c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d18c`

## pseudocode

```c
bool __fastcall tson::write_buffer::reserve(tson::write_buffer *this, unsigned __int64 a2)
{
  size_t v3; // r14
  char *v4; // rax
  char *v5; // rbp
  __int64 v6; // rbx
  size_t v7; // rsi
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  void *v11; // r15
  DWORD LastError; // ebx
  bool result; // al

  if ( *((_QWORD *)this + 260) - *((_QWORD *)this + 258) > a2 )
    a2 = *((_QWORD *)this + 260) - *((_QWORD *)this + 258);
  v3 = 2 * a2;
  v4 = (char *)CoTaskMemAlloc(2 * a2);
  v5 = v4;
  if ( !v4 )
  {
    *((_BYTE *)this + 8) = 1;
    return 0;
  }
  v6 = *((_QWORD *)this + 258);
  v7 = *((_QWORD *)this + 259) - v6;
  if ( v7 )
  {
    if ( !v6 || v3 < v7 )
    {
      memset_0(v4, 0, v3);
      if ( v6 )
      {
        if ( v3 >= v7 )
          goto LABEL_13;
        *(_DWORD *)_o__errno(v9, v8, v10) = 34;
      }
      else
      {
        *(_DWORD *)_o__errno(v9, v8, v10) = 22;
      }
      invalid_parameter_noinfo();
      goto LABEL_13;
    }
    memcpy_0(v4, *((const void **)this + 258), v7);
  }
LABEL_13:
  v11 = *(void **)this;
  if ( *(_QWORD *)this )
  {
    LastError = GetLastError();
    CoTaskMemFree(v11);
    SetLastError(LastError);
  }
  *(_QWORD *)this = v5;
  *((_QWORD *)this + 259) = &v5[v7];
  *((_QWORD *)this + 260) = &v5[v3];
  result = 1;
  *((_QWORD *)this + 258) = v5;
  return result;
}

```

## disassembly

```asm
0x18000d160  push    rbx
0x18000d162  push    rbp
0x18000d163  push    rsi
0x18000d164  push    rdi
0x18000d165  push    r14
0x18000d167  push    r15
0x18000d169  sub     rsp, 28h
0x18000d16d  mov     rax, [rcx+820h]
0x18000d174  mov     rdi, rcx
0x18000d177  sub     rax, [rcx+810h]
0x18000d17e  cmp     rax, rdx
0x18000d181  cmova   rdx, rax
0x18000d185  lea     r14, [rdx+rdx]
0x18000d189  mov     rcx, r14; cb
0x18000d18c  call    cs:__imp_CoTaskMemAlloc
0x18000d192  mov     rbp, rax
0x18000d195  test    rax, rax
0x18000d198  jz      loc_18000D246
0x18000d19e  mov     rbx, [rdi+810h]
0x18000d1a5  mov     rsi, [rdi+818h]
0x18000d1ac  sub     rsi, rbx
0x18000d1af  jz      short loc_18000D201
0x18000d1b1  test    rbx, rbx
0x18000d1b4  jz      short loc_18000D1CB
0x18000d1b6  cmp     r14, rsi
0x18000d1b9  jb      short loc_18000D1CB
0x18000d1bb  mov     r8, rsi; Size
0x18000d1be  mov     rdx, rbx; Src
0x18000d1c1  mov     rcx, rax; void *
0x18000d1c4  call    memcpy_0
0x18000d1c9  jmp     short loc_18000D201
0x18000d1cb  mov     r8, r14; Size
0x18000d1ce  xor     edx, edx; Val
0x18000d1d0  mov     rcx, rbp; void *
0x18000d1d3  call    memset_0
0x18000d1d8  test    rbx, rbx
0x18000d1db  jnz     short loc_18000D1EB
0x18000d1dd  call    cs:__imp__o__errno
0x18000d1e3  mov     dword ptr [rax], 16h
0x18000d1e9  jmp     short loc_18000D1FC
0x18000d1eb  cmp     r14, rsi
0x18000d1ee  jnb     short loc_18000D201
0x18000d1f0  call    cs:__imp__o__errno
0x18000d1f6  mov     dword ptr [rax], 22h ; '"'
0x18000d1fc  call    _invalid_parameter_noinfo
0x18000d201  mov     r15, [rdi]
0x18000d204  test    r15, r15
0x18000d207  jz      short loc_18000D222
0x18000d209  call    cs:__imp_GetLastError
0x18000d20f  mov     rcx, r15; pv
0x18000d212  mov     ebx, eax
0x18000d214  call    cs:__imp_CoTaskMemFree
0x18000d21a  mov     ecx, ebx; dwErrCode
0x18000d21c  call    cs:__imp_SetLastError
0x18000d222  mov     [rdi], rbp
0x18000d225  lea     rax, [rsi+rbp]
0x18000d229  mov     [rdi+818h], rax
0x18000d230  lea     rax, [r14+rbp]
0x18000d234  mov     [rdi+820h], rax
0x18000d23b  mov     al, 1
0x18000d23d  mov     [rdi+810h], rbp
0x18000d244  jmp     short loc_18000D24C
0x18000d246  mov     byte ptr [rdi+8], 1
0x18000d24a  xor     al, al
0x18000d24c  add     rsp, 28h
0x18000d250  pop     r15
0x18000d252  pop     r14
0x18000d254  pop     rdi
0x18000d255  pop     rsi
0x18000d256  pop     rbp
0x18000d257  pop     rbx
0x18000d258  retn
```
