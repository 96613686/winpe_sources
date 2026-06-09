# tson::write_buffer::reserve(unsigned __int64)

- ea: `0x1800b26d8`
- end: `0x1800b27d1`
- name: `?reserve@write_buffer@tson@@AEAA_N_K@Z`
- size: `249`
- prototype: `bool __fastcall(tson::write_buffer *__hidden this, unsigned __int64)`
- caller_count: `13`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800ad35c`
- `0x1800ae114`
- `0x1800ae1ac`
- `0x1800ae240`
- `0x1800ae3c0`
- `0x1800ae82c`
- `0x1800b1afc`
- `0x1800b2628`
- `0x1800b27d8`
- `0x1800b2e74`
- `0x1800b33c0`
- `0x1800b39f8`
- `0x1800b3c0c`

## callees

- `0x180009e16`
- `0x180009efc`
- `0x180009f14`
- `0x1800b26d8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800b2755`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800b2768`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800b2755`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800b2768`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b2794`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b2794`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2781`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2781`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b278c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b278c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b2704`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b2704`

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
0x1800b26d8  push    rbx
0x1800b26da  push    rbp
0x1800b26db  push    rsi
0x1800b26dc  push    rdi
0x1800b26dd  push    r14
0x1800b26df  push    r15
0x1800b26e1  sub     rsp, 28h
0x1800b26e5  mov     rax, [rcx+820h]
0x1800b26ec  mov     rdi, rcx
0x1800b26ef  sub     rax, [rcx+810h]
0x1800b26f6  cmp     rax, rdx
0x1800b26f9  cmova   rdx, rax
0x1800b26fd  lea     r14, [rdx+rdx]
0x1800b2701  mov     rcx, r14; cb
0x1800b2704  call    cs:__imp_CoTaskMemAlloc
0x1800b270a  mov     rbp, rax
0x1800b270d  test    rax, rax
0x1800b2710  jz      loc_1800B27BE
0x1800b2716  mov     rbx, [rdi+810h]
0x1800b271d  mov     rsi, [rdi+818h]
0x1800b2724  sub     rsi, rbx
0x1800b2727  jz      short loc_1800B2779
0x1800b2729  test    rbx, rbx
0x1800b272c  jz      short loc_1800B2743
0x1800b272e  cmp     r14, rsi
0x1800b2731  jb      short loc_1800B2743
0x1800b2733  mov     r8, rsi; Size
0x1800b2736  mov     rdx, rbx; Src
0x1800b2739  mov     rcx, rax; void *
0x1800b273c  call    memcpy_0
0x1800b2741  jmp     short loc_1800B2779
0x1800b2743  mov     r8, r14; Size
0x1800b2746  xor     edx, edx; Val
0x1800b2748  mov     rcx, rbp; void *
0x1800b274b  call    memset_0
0x1800b2750  test    rbx, rbx
0x1800b2753  jnz     short loc_1800B2763
0x1800b2755  call    cs:__imp__o__errno
0x1800b275b  mov     dword ptr [rax], 16h
0x1800b2761  jmp     short loc_1800B2774
0x1800b2763  cmp     r14, rsi
0x1800b2766  jnb     short loc_1800B2779
0x1800b2768  call    cs:__imp__o__errno
0x1800b276e  mov     dword ptr [rax], 22h ; '"'
0x1800b2774  call    _invalid_parameter_noinfo
0x1800b2779  mov     r15, [rdi]
0x1800b277c  test    r15, r15
0x1800b277f  jz      short loc_1800B279A
0x1800b2781  call    cs:__imp_GetLastError
0x1800b2787  mov     rcx, r15; pv
0x1800b278a  mov     ebx, eax
0x1800b278c  call    cs:__imp_CoTaskMemFree
0x1800b2792  mov     ecx, ebx; dwErrCode
0x1800b2794  call    cs:__imp_SetLastError
0x1800b279a  mov     [rdi], rbp
0x1800b279d  lea     rax, [rsi+rbp]
0x1800b27a1  mov     [rdi+818h], rax
0x1800b27a8  lea     rax, [r14+rbp]
0x1800b27ac  mov     [rdi+820h], rax
0x1800b27b3  mov     al, 1
0x1800b27b5  mov     [rdi+810h], rbp
0x1800b27bc  jmp     short loc_1800B27C4
0x1800b27be  mov     byte ptr [rdi+8], 1
0x1800b27c2  xor     al, al
0x1800b27c4  add     rsp, 28h
0x1800b27c8  pop     r15
0x1800b27ca  pop     r14
0x1800b27cc  pop     rdi
0x1800b27cd  pop     rsi
0x1800b27ce  pop     rbp
0x1800b27cf  pop     rbx
0x1800b27d0  retn
```
