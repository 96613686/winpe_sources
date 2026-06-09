# wil::details_abi::heap_buffer::ensure(unsigned __int64)

- ea: `0x18000a5e4`
- end: `0x18000a6b7`
- name: `?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `211`
- prototype: `bool __fastcall(wil::details_abi::heap_buffer *__hidden this, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180008178`
- `0x180008974`
- `0x180009970`
- `0x180009b40`

## callees

- `0x180008038`
- `0x18000a5e4`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000a666`
- `msvcrt!memcpy_s` at `0x18000a666`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a649`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a6a2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a649`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a6a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a625`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a625`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a679`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a679`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a687`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a687`

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
0x18000a5e4  push    rbx
0x18000a5e6  push    rbp
0x18000a5e7  push    rsi
0x18000a5e8  push    rdi
0x18000a5e9  push    r14
0x18000a5eb  push    r15
0x18000a5ed  sub     rsp, 28h
0x18000a5f1  mov     rdi, rcx
0x18000a5f4  mov     rbx, rdx
0x18000a5f7  mov     rcx, [rcx+10h]
0x18000a5fb  mov     rax, [rdi+8]
0x18000a5ff  sub     rax, [rdi]
0x18000a602  sub     rcx, [rdi]
0x18000a605  add     rax, rdx
0x18000a608  cmp     rax, rcx
0x18000a60b  jb      loc_18000A6A8
0x18000a611  lea     rax, [rcx+rcx]
0x18000a615  cmp     rdx, rax
0x18000a618  cmovb   rbx, rax
0x18000a61c  cmp     rcx, rbx
0x18000a61f  jnb     loc_18000A6A8
0x18000a625  call    cs:__imp_GetLastError
0x18000a62b  and     rbx, 0FFFFFFFFFFFFFFC0h
0x18000a62f  xor     ecx, ecx; dwFlags
0x18000a631  mov     esi, eax
0x18000a633  lea     r14, [rbx+40h]
0x18000a637  mov     rdx, r14; dwBytes
0x18000a63a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000a63f  mov     rbx, rax
0x18000a642  test    rax, rax
0x18000a645  jnz     short loc_18000A653
0x18000a647  mov     ecx, esi; dwErrCode
0x18000a649  call    cs:__imp_SetLastError
0x18000a64f  xor     al, al
0x18000a651  jmp     short loc_18000A6AA
0x18000a653  mov     r15, [rdi+8]
0x18000a657  mov     rdx, r14; DestinationSize
0x18000a65a  sub     r15, [rdi]
0x18000a65d  mov     rcx, rbx; Destination
0x18000a660  mov     r8, [rdi]; Source
0x18000a663  mov     r9, r15; SourceSize
0x18000a666  call    cs:__imp_memcpy_s
0x18000a66c  mov     rbp, [rdi+18h]
0x18000a670  mov     [rdi+18h], rbx
0x18000a674  test    rbp, rbp
0x18000a677  jz      short loc_18000A68D
0x18000a679  call    cs:__imp_GetProcessHeap
0x18000a67f  mov     r8, rbp; lpMem
0x18000a682  xor     edx, edx; dwFlags
0x18000a684  mov     rcx, rax; hHeap
0x18000a687  call    cs:__imp_HeapFree
0x18000a68d  lea     rax, [r15+rbx]
0x18000a691  mov     [rdi], rbx
0x18000a694  mov     [rdi+8], rax
0x18000a698  mov     ecx, esi; dwErrCode
0x18000a69a  lea     rax, [r14+rbx]
0x18000a69e  mov     [rdi+10h], rax
0x18000a6a2  call    cs:__imp_SetLastError
0x18000a6a8  mov     al, 1
0x18000a6aa  add     rsp, 28h
0x18000a6ae  pop     r15
0x18000a6b0  pop     r14
0x18000a6b2  pop     rdi
0x18000a6b3  pop     rsi
0x18000a6b4  pop     rbp
0x18000a6b5  pop     rbx
0x18000a6b6  retn
```
