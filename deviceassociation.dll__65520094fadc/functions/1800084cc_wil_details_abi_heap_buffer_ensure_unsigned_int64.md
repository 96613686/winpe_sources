# wil::details_abi::heap_buffer::ensure(unsigned __int64)

- ea: `0x1800084cc`
- end: `0x18000859f`
- name: `?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `211`
- prototype: `bool __fastcall(wil::details_abi::heap_buffer *__hidden this, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000629c`
- `0x1800068b0`
- `0x180007ae8`

## callees

- `0x1800061f8`
- `0x1800084cc`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000854e`
- `msvcrt!memcpy_s` at `0x18000854e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008561`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008561`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000856f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000856f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000850d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000850d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008531`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000858a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008531`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000858a`

## pseudocode

```c
char __fastcall wil::details_abi::heap_buffer::ensure(wil::details_abi::heap_buffer *this, unsigned __int64 a2)
{
  unsigned __int64 v3; // rbx
  unsigned __int64 v4; // rcx
  DWORD LastError; // esi
  unsigned __int64 v6; // r14
  char *v7; // rax
  char *v8; // rbx
  rsize_t v10; // r15
  void *v11; // rbp
  HANDLE ProcessHeap; // rax

  v3 = a2;
  v4 = *((_QWORD *)this + 2) - *(_QWORD *)this;
  if ( a2 + *((_QWORD *)this + 1) - *(_QWORD *)this >= v4 )
  {
    if ( a2 < 2 * v4 )
      v3 = 2 * v4;
    if ( v4 < v3 )
    {
      LastError = GetLastError();
      v6 = (v3 & 0xFFFFFFFFFFFFFFC0uLL) + 64;
      v7 = (char *)wil::details::ProcessHeapAlloc(0, v6);
      v8 = v7;
      if ( !v7 )
      {
        SetLastError(LastError);
        return 0;
      }
      v10 = *((_QWORD *)this + 1) - *(_QWORD *)this;
      memcpy_s(v7, v6, *(const void *const *)this, v10);
      v11 = (void *)*((_QWORD *)this + 3);
      *((_QWORD *)this + 3) = v8;
      if ( v11 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v11);
      }
      *(_QWORD *)this = v8;
      *((_QWORD *)this + 1) = &v8[v10];
      *((_QWORD *)this + 2) = &v8[v6];
      SetLastError(LastError);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x1800084cc  push    rbx
0x1800084ce  push    rbp
0x1800084cf  push    rsi
0x1800084d0  push    rdi
0x1800084d1  push    r14
0x1800084d3  push    r15
0x1800084d5  sub     rsp, 28h
0x1800084d9  mov     rdi, rcx
0x1800084dc  mov     rbx, rdx
0x1800084df  mov     rcx, [rcx+10h]
0x1800084e3  mov     rax, [rdi+8]
0x1800084e7  sub     rax, [rdi]
0x1800084ea  sub     rcx, [rdi]
0x1800084ed  add     rax, rdx
0x1800084f0  cmp     rax, rcx
0x1800084f3  jb      loc_180008590
0x1800084f9  lea     rax, [rcx+rcx]
0x1800084fd  cmp     rdx, rax
0x180008500  cmovb   rbx, rax
0x180008504  cmp     rcx, rbx
0x180008507  jnb     loc_180008590
0x18000850d  call    cs:__imp_GetLastError
0x180008513  and     rbx, 0FFFFFFFFFFFFFFC0h
0x180008517  xor     ecx, ecx; dwFlags
0x180008519  mov     esi, eax
0x18000851b  lea     r14, [rbx+40h]
0x18000851f  mov     rdx, r14; dwBytes
0x180008522  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180008527  mov     rbx, rax
0x18000852a  test    rax, rax
0x18000852d  jnz     short loc_18000853B
0x18000852f  mov     ecx, esi; dwErrCode
0x180008531  call    cs:__imp_SetLastError
0x180008537  xor     al, al
0x180008539  jmp     short loc_180008592
0x18000853b  mov     r15, [rdi+8]
0x18000853f  mov     rdx, r14; DestinationSize
0x180008542  sub     r15, [rdi]
0x180008545  mov     rcx, rbx; Destination
0x180008548  mov     r8, [rdi]; Source
0x18000854b  mov     r9, r15; SourceSize
0x18000854e  call    cs:__imp_memcpy_s
0x180008554  mov     rbp, [rdi+18h]
0x180008558  mov     [rdi+18h], rbx
0x18000855c  test    rbp, rbp
0x18000855f  jz      short loc_180008575
0x180008561  call    cs:__imp_GetProcessHeap
0x180008567  mov     r8, rbp; lpMem
0x18000856a  xor     edx, edx; dwFlags
0x18000856c  mov     rcx, rax; hHeap
0x18000856f  call    cs:__imp_HeapFree
0x180008575  lea     rax, [r15+rbx]
0x180008579  mov     [rdi], rbx
0x18000857c  mov     [rdi+8], rax
0x180008580  mov     ecx, esi; dwErrCode
0x180008582  lea     rax, [r14+rbx]
0x180008586  mov     [rdi+10h], rax
0x18000858a  call    cs:__imp_SetLastError
0x180008590  mov     al, 1
0x180008592  add     rsp, 28h
0x180008596  pop     r15
0x180008598  pop     r14
0x18000859a  pop     rdi
0x18000859b  pop     rsi
0x18000859c  pop     rbp
0x18000859d  pop     rbx
0x18000859e  retn
```
